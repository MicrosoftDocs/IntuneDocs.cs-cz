---
title: "Použití spravovaných aplikací na zařízení s iOSem | Dokumentace Microsoftu"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3232c5c1-cb9f-45ca-806f-7e74eeb3533e
searchScope: User help
ROBOTS: 
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 8c3d9285408f2cfa394ed31ec36fcaea47306eb5
ms.sourcegitcommit: f2f147a1177d1cf5bbc8001701eb8f44dd833b7d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/12/2017
---
# <a name="use-managed-apps-on-your-ios-device"></a>Použití spravovaných aplikací na zařízení s iOSem

Spravované aplikace jsou aplikace, které může vaše firemní podpora nastavit tak, aby lépe chránily firemní data, ke kterým v dané aplikaci získáváte přístup. Pokud získáváte přístup k datům ve spravované aplikaci v zařízení s iOSem, můžete si všimnout, že aplikace funguje trochu jinak, než čekáte. Nebudete třeba moct kopírovat a vkládat chráněná firemní data nebo tato data nebudete moct uložit do určitých umístění.

Několik spravovaných aplikací také může na vašem zařízení spolupracovat, abyste mohli provádět běžné úkoly při zachování ochrany firemních dat. Například pokud otevřete firemní soubor v jedné spravované aplikaci a k jeho zobrazení je potřeba jiná spravovaná aplikace, automaticky se otevře spravovaná aplikace, která umožňuje zobrazení souboru. Pokud není požadovaná aplikace dostupná, nemusíte mít přístup k určitým akcím, jako je otevření dokumentu nebo přístup k webovému odkazu ze spravovaného dokumentu.

Při přístupu k firemním datům ve spravované aplikaci se zobrazí zpráva podobná té následující, která oznamuje, že otevíráte spravovanou aplikaci.

![managed-apps-message-ios](./media/managed-apps-message.png)

### <a name="how-do-i-get-managed-apps"></a>Jak získám spravované aplikace?
Spravované aplikace můžete získat několika různými způsoby:

-   Při registraci zařízení v Microsoft Intune buď nainstalujete aplikaci z aplikace Portál společnosti nebo webu Portál společnosti, nebo ji na vaše zařízení nainstaluje firemní podpora. Další informace o registraci najdete v tématu [Registrace zařízení s macOS do Intune](enroll-your-device-in-intune-ios.md) nebo [Registrace zařízení s iOSem do Intune](enroll-your-device-in-intune-macos.md).

-   Nainstalujte aplikaci z App Storu a potom se přihlaste pomocí svého firemního uživatelského účtu spravovaného službou Intune.

Vaše firemní podpora může někdy nakoupit pro aplikaci, kterou instalujete, více licencí. Pokud se zobrazí zpráva, že máte přijmout smlouvu Apple Volume Purchase Program, není to nic nezvyklého a můžete ji přijmout. Pokud ji nepřijmete, nebudete si moct aplikaci nainstalovat.

### <a name="what-can-my-company-support-manage-in-an-app"></a>Co může firemní podpora spravovat v mé aplikaci?
Tady jsou některé příklady možností, které může firemní podpora spravovat v aplikaci a které můžou ovlivnit vaši interakci s firemními daty na zařízení:

-   Přístup k určitým webům

-   Přenos dat mezi aplikacemi

-   Ukládání souborů

-   Operace kopírování a vkládání

-   Požadavky na přístup chráněný kódem PIN

-   Vaše přihlášení pomocí přihlašovacích údajů společnosti

-   Schopnost zálohovat do cloudu

-   Schopnost pořizovat snímky obrazovky

-   Požadavky na šifrování dat

Další informace o spravovaných aplikacích na vašem zařízení vám poskytne firemní podpora. Kontaktní údaje najdete na [webu Portál společnosti](https://portal.manage.microsoft.com#HelpDeskDialog).
