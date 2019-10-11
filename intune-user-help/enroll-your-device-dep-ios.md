---
title: V rámci správy Zaregistrujte svoje zařízení s iOS poskytované vaší organizací. | Microsoft Docs
description: Popisuje, jak zaregistrovat zařízení s iOS v Intune, které si koupil a poskytla vaše organizace.
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
ms.openlocfilehash: 0719aca1dbb84358b0c54fbfac57143d2a77c0de
ms.sourcegitcommit: 884654da8e72a63bfaea6b5def6c7891b065f251
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/09/2019
ms.locfileid: "72163456"
---
# <a name="enroll-your-organization-provided-ios-device-in-management"></a>Registrace zařízení s iOS poskytovaných vaší organizací v rámci správy

Naučte se, jak v Intune získat nové spravované zařízení s iOS.  

Zařízení s iOS, která máte v práci nebo ve škole, jsou často předem nakonfigurovaná předtím, než se dostanou. Vaše organizace pošle Tato předem nakonfigurovaná nastavení do vašeho zařízení po jeho zapnutí a přihlášení poprvé. Až zařízení dokončí instalaci, dostanete přístup k pracovním nebo školním prostředkům.  

Pokud chcete spustit instalační program, zapněte zařízení a přihlaste se pomocí svých pracovních nebo školních přihlašovacích údajů. Zbývající část tohoto článku popisuje kroky a obrazovky, které se zobrazí při procházení průvodce nastavením.

## <a name="what-is-apple-dep"></a>Co je Apple DEP?

Vaše organizace si mohla koupit svoje zařízení pomocí nějakého programu *Apple program registrace zařízení* (DEP). Apple DEP umožňuje organizacím koupit velké množství zařízení se systémem iOS nebo macOS. Organizace pak můžou tato zařízení nakonfigurovat a spravovat v rámci preferovaného poskytovatele správy mobilních zařízení, jako je třeba Intune. Pokud jste správce a chcete získat další informace o programu Apple DEP, přečtěte si téma [Automatická registrace zařízení s iOS pomocí program registrace zařízení společnosti Apple](/intune/enrollment/device-enrollment-program-enroll-ios).

## <a name="set-up-your-ios-device"></a>Nastavení zařízení s iOS

Pokud používáte vlastní zařízení se systémem iOS, nikoli organizaci, postupujte podle kroků pro [osobní a vlastní zařízení](enroll-your-device-in-intune-ios.md).  

1. Zapněte zařízení s iOS.
2. Po výběru **jazyka**připojte zařízení k Wi-Fi.
3. Na obrazovce **nastavení zařízení se systémem iOS** vyberte, zda chcete:
   - **Nastavit jako nové zařízení**
   - **Obnovení ze zálohy iCloud**
   - **Obnovení ze zálohy iTunes**

4. Po připojení k Wi-Fi se zobrazí obrazovka **Konfigurace** . To znamená, že **[vaše společnost] bude vaše zařízení automaticky konfigurovat.**

   **Konfigurace umožňuje [vaší společnosti] spravovat toto zařízení v ovzduší. Správce vám může pomáhat nastavit e-mailové a síťové účty, instalovat a konfigurovat aplikace a spravovat nastavení vzdáleně. Správce může zakázat funkce, instalovat a odebírat aplikace, monitorovat a omezovat internetový provoz a vzdáleně vymazat toto zařízení.**

   **Konfiguraci poskytuje: [vaše společnost] tým iOS [adresa]**

5. Přihlaste se pomocí Apple ID. Přihlášení vám umožní nainstalovat aplikaci Portál společnosti a nainstalovat profil správy, který vaší společnosti umožní přístup k jejich prostředkům, jako je e-mail a aplikace.
6. Vyjádřit souhlas s **podmínkami a ujednáními** a rozhodněte se, jestli chcete odeslat diagnostické informace společnosti Apple.
7. Po dokončení registrace vám vaše zařízení může zobrazit výzvu k provedení dalších akcí. Některé z těchto kroků můžou být zadáním hesla pro přístup k e-mailu nebo nastavením hesla.

Ještě potřebujete pomáhat? Obraťte se na firemní podporu. Kontaktní informace najdete na [webu portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).
