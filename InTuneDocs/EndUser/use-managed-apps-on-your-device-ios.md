---
title: "Použití spravovaných aplikací na zařízení s iOS | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3232c5c1-cb9f-45ca-806f-7e74eeb3533e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: maxles
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9ddbcde20fac83289c4622f69538ff00fa0cb65b
ms.openlocfilehash: c051fe1128f2156943eac7eb4d4fa5983ed90771


---


# <a name="use-managed-apps-on-your-ios-device"></a>Použití spravovaných aplikací na zařízení s iOS

Spravované aplikace jsou aplikace, které může váš správce IT nastavit tak, aby lépe chránily firemní data, ke kterým v dané aplikaci získáváte přístup. Pokud získáváte přístup k datům ve spravované aplikaci v zařízení s iOS, můžete si všimnout, že aplikace funguje trochu jinak, než čekáte. Nebudete třeba moct kopírovat a vkládat chráněná firemní data nebo tato data nebudete moct uložit do určitých umístění.

Několik spravovaných aplikací také může na vašem zařízení spolupracovat, abyste mohli provádět běžné úkoly při zachování ochrany firemních dat. Například pokud otevřete firemní soubor v jedné spravované aplikaci a k jeho zobrazení je potřeba jiná spravovaná aplikace, automaticky se otevře spravovaná aplikace, která umožňuje zobrazení souboru. Pokud není požadovaná aplikace dostupná, nemusíte mít přístup k určitým akcím, jako je otevření dokumentu nebo přístup k webovému odkazu ze spravovaného dokumentu.

Při přístupu k firemním datům ve spravované aplikaci se zobrazí zpráva podobná té následující, která oznamuje, že otevíráte spravovanou aplikaci.

![managed-apps-message-ios](./media/managed-apps-message.png)

### <a name="how-do-i-get-managed-apps"></a>Jak získám spravované aplikace?
Spravované aplikace můžete získat několika různými způsoby:

-   Při registraci zařízení v Microsoft Intune buď nainstalujete aplikaci z aplikace Portál společnosti nebo webu Portál společnosti, nebo ji na vaše zařízení nainstaluje správce IT. Další informace o registraci najdete v tématu [Registrace zařízení se systémem Mac OS X v Intune](enroll-your-device-in-intune-ios.md) nebo [Registrace zařízení se systémem iOS do Intune](enroll-your-device-in-intune-mac-os-x.md).

-   Nainstalujte aplikaci z App Storu a potom se přihlaste pomocí svého firemního uživatelského účtu spravovaného službou Intune.

### <a name="what-can-my-it-admin-manage-in-an-app"></a>Co může správce IT spravovat v mé aplikaci?
Tady jsou některé příklady možností, které může správce IT spravovat v aplikaci a které můžou ovlivnit vaši interakci s firemními daty na zařízení:

-   Přístup k určitým webům

-   Přenos dat mezi aplikacemi

-   Ukládání souborů

-   Operace kopírování a vkládání

-   Požadavky na přístup chráněný kódem PIN

-   Vaše přihlášení pomocí přihlašovacích údajů společnosti

-   Schopnost zálohovat do cloudu

-   Schopnost pořizovat snímky obrazovky

-   Požadavky na šifrování dat


Další informace o spravovaných aplikacích na vašem zařízení vám poskytne správce IT. Kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).



<!--HONumber=Nov16_HO1-->


