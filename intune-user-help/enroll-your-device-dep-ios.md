---
title: Registrace zařízení s iOSem poskytnutého vaší organizací do správy | Dokumenty Microsoft
description: Tento článek popisuje, jak zaregistrovat v Intune zařízení s iOSem, které zakoupila a poskytla vaše organizace.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f4e7d87e-56d1-43e4-8e88-2f62cf0999e2
searchScope:
- User help
ROBOTS: ''
ms.reviewer: japoehlm
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40fe8f1f54779d3ab0a49951ad13c0cb2d0f0ff5
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71166792"
---
# <a name="enroll-your-organization-provided-ios-device-in-management"></a>Registrace zařízení s iOSem poskytnutého vaší organizací do správy

Přečtěte si, jak začít spravovat nové zařízení s iOSem v Intune.  

Zařízení s iOSem, která vám poskytne váš zaměstnavatel nebo škola, bývají často nakonfigurovaná předem. Když zařízení zapnete a poprvé se přihlásíte, vaše organizace do něho tato předem nakonfigurovaná nastavení pošle. Jakmile zařízení nastavení dokončí, budete mít přístup k pracovním nebo školním prostředkům.  

Aby se nastavení zahájilo, zapněte zařízení a přihlaste se pomocí pracovních nebo školních přihlašovacích údajů. Zbytek tohoto článku popisuje kroky a obrazovky, které uvidíte při procházení Průvodce nastavením. 

## <a name="what-is-apple-dep"></a>Co je Apple DEP?

Je možné, že si vaše organizace zakoupila zařízení prostřednictvím programu s názvem *Program registrace zařízení Apple* (DEP). Tento program umožňuje organizacím nakupovat velká množství zařízení s iOSem nebo macOS. Organizace pak můžou zařízení konfigurovat a spravovat v rámci svého upřednostňovaného poskytovatele správy mobilních zařízení, jako je Intune. Pokud jste správce a chcete získat o programu Apple DEP další informace, podívejte se na článek [Automatická registrace zařízení s iOSem pomocí Programu registrace zařízení společnosti Apple](https://docs.microsoft.com/intune/device-enrollment-program-enroll-ios.md).  

## <a name="set-up-your-ios-device"></a>Nastavení zařízení s iOSem

Pokud nepoužíváte zařízení s iOSem poskytnuté organizací, ale svoje vlastní zařízení, postupujte podle pokynů k [osobním a vlastním zařízením uživatelů](enroll-your-device-in-intune-ios.md).  

1. Zapněte zařízení s iOSem.
2. Po výběru **jazyka** připojte zařízení k Wi-Fi.
3. Na obrazovce **Set up iOS device** (Nastavit zařízení s iOSem) zvolte, co chcete udělat:
   - **Set Up as New device** (Nastavit jako nové zařízení)
   - **Restore from iCloud backup** (Obnovit ze zálohy v iCloudu)
   - **Restore from iCloud backup** (Obnovit ze zálohy v iTunes)

4. Po připojení k Wi-Fi se zobrazí obrazovka pro **konfiguraci**. Bude obsahovat informace o tom, že **[vaše společnost] automaticky nakonfiguruje vaše zařízení**.

   **Configuration allows [Your Organization] to manage this device over the air. An administrator can help you set up email and network accounts, install and configure apps, and manage settings remotely. An administrator may disable features, install and remove apps, monitor and restrict your Internet traffic and remotely erase this device.** (Konfigurace umožňuje vaší organizaci spravovat toto zařízení bezdrátově. Správce vám na dálku pomůže nastavit e-mailové a síťové účty, instalovat a konfigurovat aplikace a spravovat nastavení. Správce může zakázat funkce, instalovat a odebírat aplikace, monitorovat a omezit váš internetový provoz nebo na dálku zařízení vymazat.)
 
   **Configuration is provided by: [Your Company's] iOS Team [Address]** (Konfiguraci zajišťuje: iOS tým [vaší společnosti] [adresa])

5. Přihlaste se svým Apple ID. Přihlášení vám umožní nainstalovat aplikaci Portál společnosti a profil správy, který vaší společnosti umožní přístup k firemním prostředkům, jako jsou e-mail a aplikace.
6. Odsouhlaste **podmínky a ujednání** a rozhodněte se, jestli chcete posílat diagnostické informace do společnosti Apple.
7. Po registraci může vaše zařízení zobrazit výzvu k provedení dalších akcí. Některé z těchto kroků mohou zahrnovat zadání hesla pro přístup k e-mailu nebo nastavení hesla.

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).
