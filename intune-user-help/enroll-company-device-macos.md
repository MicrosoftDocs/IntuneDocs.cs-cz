---
title: Registrace zařízení macOS poskytovaných vaší organizací do správy | Microsoft Docs
description: Popisuje, jak zaregistrovat zařízení macOS v Intune zakoupené a poskytované vaší organizací.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: japoehlm
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: f2e2ecc79cd24a68c1a5642f64474f2d31217bd7
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721023"
---
# <a name="enroll-your-organization-provided-macos-device-in-management"></a>Registrace zařízení macOS poskytovaných vaší organizací do správy

Naučte se, jak v Intune začít spravovat vaše nové zařízení macOS.  

Zařízení, která jsou k dispozici ve vaší práci nebo ve škole, jsou často předem nakonfigurovaná předtím, než se dostanou. Vaše organizace pošle Tato předem nakonfigurovaná nastavení do vašeho zařízení po jeho zapnutí a přihlášení poprvé. Až zařízení dokončí instalaci, dostanete přístup k pracovním nebo školním prostředkům.

Pokud chcete začít s nastavením správy, zapněte zařízení a přihlaste se pomocí svých pracovních nebo školních přihlašovacích údajů. Zbývající část tohoto článku popisuje kroky a obrazovky, které se zobrazí při procházení průvodce nastavením.

## <a name="what-is-apple-dep"></a>Co je Apple DEP?

Vaše organizace si mohla koupit svoje zařízení pomocí nějakého programu *Apple program registrace zařízení* (DEP). Apple DEP umožňuje organizacím koupit velké množství zařízení se systémem iOS nebo macOS. Organizace pak můžou tato zařízení nakonfigurovat a spravovat v rámci preferovaného poskytovatele správy mobilních zařízení, jako je třeba Intune. Pokud jste správce a chcete získat další informace o programu Apple DEP, přečtěte si téma [Automatická registrace zařízení MacOS pomocí program registrace zařízení společnosti Apple](https://docs.microsoft.com/intune/enrollment/device-enrollment-program-enroll-macos.md).  

## <a name="get-your-device-managed"></a>Získání spravovaného zařízení

Provedením následujících kroků zaregistrujete zařízení macOS ve správě. Pokud místo zařízení poskytovaného organizací používáte vlastní zařízení, postupujte podle kroků pro [osobní a vlastní zařízení](enroll-your-device-in-intune-macos-cp.md).  

1. Zapněte zařízení macOS.
2. Vyberte zemi nebo oblast a klikněte na **pokračovat**.  

   ![Obrazovka úvodní obrazovky pomocníka s nastavením zařízení macOS a zobrazuje seznam jazyků, ze kterých se mají vybírat](./media/macos-dep-welcome-1808.png)
3. Vyberte rozložení klávesnice. V seznamu se zobrazí jedna nebo více možností na základě vybrané země nebo oblasti. Chcete-li zobrazit všechny možnosti rozložení bez ohledu na zvolenou zemi nebo oblast, klikněte na tlačítko **Zobrazit vše**. Až skončíte, klikněte na **pokračovat.**  

   ![Obrazovka rozložení klávesnice pomocníka s nastavením zařízení macOS, která zobrazuje seznam jazyků klávesnice, které se mají vybrat, možnost nezaškrtnuto Zobrazit vše a tlačítko zpět a pokračovat.](./media/macos-dep-keyboard-1808.png)  
4. Vyberte síť Wi-Fi. Aby bylo možné pokračovat v instalaci, je nutné připojení k Internetu. Pokud se vaše síť nezobrazí nebo pokud se potřebujete připojit přes drátovou síť, klikněte na **Další možnosti sítě**. Až skončíte, klikněte na **pokračovat**.  

   ![Snímek obrazovky s průvodcem nastavením zařízení macOS vyberte obrazovku sítě Wi-Fi, která zobrazuje seznam dostupných sítí, ze kterých si můžete vybrat. Také se zobrazí další tlačítko Možnosti sítě, tlačítko zpět a tlačítko pokračovat.](./media/macos-dep-wifi-1808.png)  
5. Po připojení k Wi-Fi se zobrazí obrazovka **Vzdálená správa** . Vzdálená správa umožňuje správcům vaší organizace vzdáleně nakonfigurovat vaše zařízení pomocí účtů, nastavení, aplikací a sítí vyžadovaných společností. Přečtěte si vysvětlení vzdálené správy, které vám pomůže pochopit, jak je vaše zařízení spravované. Pak klikněte na **pokračovat**.  

   ![Obrazovka obrazovky pro vzdálenou správu pomocníka s nastavením zařízení macOS s textem vysvětlujícím vzdálenou správu a odkazem na dokumentaci, kde najdete další informace. Také zobrazí tlačítko zpět a tlačítko pokračovat.](./media/macos-dep-remote-management-1-1808.png)  
6. Po zobrazení výzvy se přihlaste pomocí svého pracovního nebo školního účtu. Po ověření bude zařízení instalovat profil správy. Profil konfiguruje a umožňuje přístup k prostředkům vaší organizace.  
7. Přečtěte si o ikoně ochrany osobních údajů pro Apple data &, abyste mohli později zjistit, kdy se shromažďují osobní údaje. Pak klikněte na **pokračovat**.  

   ![Snímek obrazovky s obrazovkou & Průvodce nastavením zařízení macOS obrazovka ochrany osobních údajů na obrazovce, na které se zobrazuje ilustrace dvou lidí potřesící ruce a popis používání osobních údajů od společnosti Apple. Zobrazí také tlačítko zpět a pokračovat.](./media/macos-dep-apple-data-privacy-1808.png)  
8. Po registraci zařízení je možné, že budete muset provést další kroky. Postup najdete v závislosti na tom, jak vaše organizace vlastní nastavení prostředí. Může vyžadovat:
    * Přihlášení k účtu Apple
    * Vyjádřit souhlas s podmínkami a ujednáními
    * Vytvoření účtu počítače
    * Projít si expresním nastavením
    * Nastavení počítače Mac

## <a name="get-the-company-portal-app"></a>Získat aplikaci Portál společnosti

Stáhněte si aplikaci Portál společnosti Intune pro macOS na svém zařízení. Aplikace umožňuje monitorovat, synchronizovat, přidávat a odebírat zařízení ze správy a instalovat aplikace. Tento postup také popisuje, jak zaregistrovat zařízení pomocí Portál společnosti.

1. Na zařízení macOS přejít na [https://portal.manage.microsoft.com/EnrollmentRedirect.aspx](https://portal.manage.microsoft.com/EnrollmentRedirect.aspx).
2. Přihlaste se k webu Portál společnosti pomocí svého pracovního nebo školního účtu. 
3. Klikněte na **získat aplikaci** a Stáhněte si instalační program portál společnosti pro MacOS.
4. Po zobrazení výzvy otevřete soubor. pkg a dokončete kroky instalace.
5. Otevřete aplikaci Portál společnosti a přihlaste se pomocí svého pracovního nebo školního účtu.
6. Najděte své zařízení a klikněte na **zaregistrovat**.
7. Klikněte na **pokračovat** > **Hotovo**. Vaše zařízení by se teď mělo zobrazit v aplikaci Portál společnosti jako firemní a vyhovující zařízení.

Ještě potřebujete pomáhat? Obraťte se na firemní podporu. Kontaktní informace najdete na [webu portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).
