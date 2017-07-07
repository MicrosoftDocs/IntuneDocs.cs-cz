---
title: "Zřizovací profily aplikací"
description: "Intune poskytuje nástroje pro proaktivní nasazení nových zásad zřizovacích profilů do zařízení, ve kterých se aplikace blíží vypršení data platnosti."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 86fbe736-7bdb-4f5e-ae21-13c91eb2462c
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6e975aa7ee22f826c7a0a60d637d651fd347bc54
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="use-ios-mobile-provisioning-profile-policies-to-prevent-your-apps-from-expiring"></a>Pomocí mobilních zásad zřizovacích profilů pro iOS zabráníte vypršení platnosti aplikací.

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Mobilní obchodní aplikace pro Apple iOS nasazené do iPhonů a iPadů obsahují zřizovací profil a kód podepsaný certifikátem. Když se taková aplikace spustí, iOS potvrdí její integritu a vynutí zásady definované zřizovacím profilem. Provedou se k následující ověření:

- **Integrita instalačního souboru** – iOS porovná podrobné informace o aplikaci s veřejným klíčem podpisového certifikátu společnosti. Pokud se liší, je možné, že se obsah aplikace změnil, a její spuštění se nepovolí.
- **Vynucení schopností** – iOS se pokusí vynutit schopnosti aplikace ze zřizovacího profilu společnosti (ne z individuálních zřizovacích profilů vývojářů) obsaženého v instalačním souboru aplikace (.ipa).


Podpisový certifikát společnosti, který se používá k podepisování aplikací, má obvykle platnost tři roky. Platnost zřizovacího profilu ale vyprší už po roce. Když je certifikát stále platný, Intune poskytuje nástroje pro proaktivní nasazení nových zásad zřizovacích profilů do zařízení, ve kterých se aplikace blíží vypršení data platnosti.
Po vypršení platnosti certifikátu musíte aplikaci znovu podepsat pomocí nového certifikátu a vložit nový zřizovací profil s klíčem tohoto nového certifikátu.



## <a name="how-to-find-out-when-a-line-of-business-app-will-expire"></a>Jak zjistit, kdy vyprší platnost obchodní aplikace

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Aplikace** > **Aplikace**.
2. V seznamu aplikací se ve sloupci **Datum vypršení platnosti** zobrazuje, kdy vyprší platnost příslušné aplikace. Můžete taky v rozevíracím seznamu **Filtry** nastavit **Platnost vypršela nebo brzo vyprší** a zobrazit jenom ty aplikace, které vyžadují nějakou akci.

## <a name="how-to-create-an-ios-mobile-provisioning-profile-policy"></a>Jak vytvořit zásady mobilních zřizovacích profilů pro iOS


1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Zásady** > **Přehled** > **Přidat zásadu**.
2. V dialogovém okně **Vytvořit novou zásadu** zvolte **iOS** > **Zásady pro mobilní zřizovací profil** a potom zvolte **Vytvořit zásadu**.
3. Na stránce **Obecné** nakonfigurujte tyto hodnoty:
    - **Název** – Zadejte název pro tuto zásadu mobilních zřizovacích profilů.
    - **Popis** – Volitelně zadejte popis pro tuto zásadu.
    - **Soubor konfiguračního profilu** – Klikněte na **Import** a potom zvolte soubor mobilního konfiguračního profilu Apple (s příponou **.mobileprovision**), který jste stáhli z webu pro vývojáře Apple.
4. Po dokončení vyberte **Uložit zásadu**.
5. Potom nasaďte zásadu na požadovaná zařízení s iOSem. Další informace najdete v tématu [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).
