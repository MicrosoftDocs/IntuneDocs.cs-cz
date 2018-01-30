---
title: "Zřizovací profily aplikací"
titlesuffix: Azure portal
description: "Intune poskytuje nástroje pro proaktivní přiřazení nového zřizovacího profilu k zařízením s aplikacemi, kterým brzy vyprší platnost."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 96ae009abe8d8351052ede4efca779add01dc335
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="use-ios-mobile-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Jak zabránit vypršení platnosti aplikací pomocí mobilních zřizovacích profilů pro iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a>Úvod

Obchodní aplikace pro Apple iOS, které jsou přiřazené k iPhonům a iPadům, obsahují zřizovací profil a kód podepsaný certifikátem. Když se taková aplikace spustí, iOS potvrdí její integritu a vynutí zásady definované zřizovacím profilem. Provedou se k následující ověření:

- **Integrita instalačního souboru** – iOS porovná podrobné informace o aplikaci s veřejným klíčem podpisového certifikátu společnosti. Pokud se liší, je možné, že se obsah aplikace změnil, a její spuštění se nepovolí.
- **Vynucení schopností** – iOS se pokusí vynutit schopnosti aplikace ze zřizovacího profilu společnosti (ne z individuálních zřizovacích profilů vývojářů) obsaženého v instalačním souboru aplikace (.ipa).


Podpisový certifikát společnosti, který se používá k podepisování aplikací, má obvykle platnost tři roky. Platnost zřizovacího profilu ale vyprší už po roce. Během platnosti certifikátu poskytuje Intune nástroje k proaktivnímu přiřazení nového zřizovacího profilu k zařízením s aplikacemi, kterým brzy vyprší platnost.
Po vypršení platnosti certifikátu musíte aplikaci znovu podepsat pomocí nového certifikátu a vložit nový zřizovací profil s klíčem tohoto nového certifikátu.


## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>Jak vytvořit mobilní zřizovací profil aplikace pro iOS

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
1.  V úloze **Mobilní aplikace** zvolte **Spravovat** > **Zřizovací profily iOS**.
2.  V okně se seznamem profilů zvolte **Vytvořit profil**.
3. V okně **Vytvořit profil** nakonfigurujte následující hodnoty:
    - **Název** – Zadejte název tohoto mobilního zřizovacího profilu.
    - **Popis** – Volitelně zadejte popis pro tuto zásadu.
    - **Odeslat soubor profilu** – Zvolte **Importovat** a pak zvolte soubor mobilního konfiguračního profilu Apple (s příponou **.mobileprovision**), který jste stáhli z webu pro vývojáře Apple.
4. Až skončíte, zvolte **Vytvořit**.

## <a name="next-steps"></a>Další kroky

Přiřaďte profil k požadovaným zařízením s iOSem. Další informace najdete v postupu v článku [Přiřazení profilů zařízení](device-profile-assign.md).
