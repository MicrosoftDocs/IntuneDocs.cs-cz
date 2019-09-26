---
title: Zřizovací profily pro aplikace iOS v Microsoft Intune
titleSuffix: ''
description: Intune poskytuje nástroje umožňující proaktivně přiřadit nový zřizovací profil k zařízením s aplikacemi, kterým brzy vyprší platnost.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fcc4939e5469cd69914d59af33be84beff9b2cf1
ms.sourcegitcommit: 6b5907046f920279bbda3ee6c93e98594624c05c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/19/2019
ms.locfileid: "71304183"
---
# <a name="use-ios-app-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Jak zabránit vypršení platnosti aplikací pomocí zřizovacích profilů pro aplikace pro iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a>Úvod

Obchodní aplikace pro Apple iOS, které jsou přiřazené k iPhonům a iPadům, obsahují zřizovací profil a kód podepsaný certifikátem. Když se taková aplikace spustí, iOS potvrdí její integritu a vynutí zásady definované zřizovacím profilem. Provedou se k následující ověření:

- **Integrita instalačního souboru** – iOS porovná podrobné informace o aplikaci s veřejným klíčem podpisového certifikátu společnosti. Pokud se liší, je možné, že se obsah aplikace změnil, a její spuštění se nepovolí.
- **Vynucení schopností** – iOS se pokusí vynutit schopnosti aplikace ze zřizovacího profilu společnosti (ne z individuálních zřizovacích profilů vývojářů) obsaženého v instalačním souboru aplikace (.ipa).


Podpisový certifikát společnosti, který se používá k podepisování aplikací, má obvykle platnost tři roky. Platnost zřizovacího profilu ale vyprší už po roce. Během platnosti certifikátu poskytuje Intune nástroje k proaktivnímu přiřazení nového zřizovacího profilu k zařízením s aplikacemi, kterým brzy vyprší platnost.
Po vypršení platnosti certifikátu musíte aplikaci znovu podepsat pomocí nového certifikátu a vložit nový zřizovací profil s klíčem tohoto nového certifikátu.

Jako správce můžete podle potřeby zahrnout nebo vyloučit skupiny zabezpečení a přiřadit jim konfiguraci zřizování aplikací pro iOS. Můžete například přiřadit konfiguraci zřizování aplikací pro iOS skupině Všichni uživatelé, ale vyloučit skupinu vedoucích pracovníků.

## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>Jak vytvořit mobilní zřizovací profil aplikace pro iOS

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** zvolte **Klientské aplikace**.
1. V úloze **Klientské aplikace** zvolte **Spravovat** > **Zřizovací profily aplikací pro iOS**.
2. V podokně se seznamem profilů zvolte **Vytvořit profil**.
3. V podokně **Vytvořit profil** nakonfigurujte následující hodnoty:
    - **Název** – Zadejte název tohoto mobilního zřizovacího profilu.
    - **Popis** – Volitelně zadejte popis pro tuto zásadu.
    - **Odeslat soubor profilu** – zvolte ikonu **otevřít** a pak zvolte soubor konfiguračního profilu Apple Mobile (s rozšířením `.mobileprovision`), který jste stáhli z webu pro [vývojáře Apple](https://developer.apple.com/).
4. Až skončíte, zvolte **Vytvořit**.

## <a name="next-steps"></a>Další kroky

Přiřaďte profil k požadovaným zařízením s iOSem. Další informace najdete v postupu v článku [Přiřazení profilů zařízení](device-profile-assign.md).
