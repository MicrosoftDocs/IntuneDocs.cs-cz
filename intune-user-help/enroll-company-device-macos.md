---
title: Registrace zařízení s macOS poskytnutého vaší organizací do správy | Microsoft Docs
description: Tento článek popisuje, jak zaregistrovat v Intune zařízení s macOS, které zakoupila a poskytla vaše organizace.
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
ms.openlocfilehash: 603a501ff8b8b3ebc6b142a823b1c5bea4e48b98
ms.sourcegitcommit: 77540295381a59918eb638ce9c1870209cf8af02
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2018
ms.locfileid: "46505746"
---
# <a name="enroll-your-organization-provided-macos-device-in-management"></a>Registrace zařízení s macOS poskytnutého vaší organizací do správy

Přečtěte si, jak začít spravovat nové zařízení s macOS v Intune.  

Zařízení, která vám poskytne váš zaměstnavatel nebo škola, bývají často nakonfigurovaná předem. Když zařízení zapnete a poprvé se přihlásíte, vaše organizace do něho tato předem nakonfigurovaná nastavení pošle. Jakmile zařízení nastavení dokončí, budete mít přístup k pracovním nebo školním prostředkům. 

Aby se nastavení správy zahájilo, zapněte zařízení a přihlaste se pomocí pracovních nebo školních přihlašovacích údajů. Zbytek tohoto článku popisuje kroky a obrazovky, které uvidíte při procházení Průvodce nastavením.   

## <a name="what-is-apple-dep"></a>Co je Apple DEP?
Je možné, že si vaše organizace zakoupila zařízení prostřednictvím programu s názvem *Program registrace zařízení Apple* (DEP). Tento program umožňuje organizacím nakupovat velká množství zařízení s iOSem nebo macOS. Organizace pak můžou zařízení konfigurovat a spravovat v rámci svého upřednostňovaného poskytovatele správy mobilních zařízení, jako je Intune. Pokud jste správce a chcete získat o programu Apple DEP další informace, podívejte se na článek [Automatická registrace zařízení s macOS do Programu registrace zařízení Apple](https://docs.microsoft.com/intune/device-enrollment-program-enroll-macos).  

## <a name="get-your-device-managed"></a>Nastavení spravovaného zařízení 
Zařízení s macOS zaregistrujete do správy provedením následujících kroků. Pokud nepoužíváte zařízení poskytnuté organizací, ale svoje vlastní zařízení, postupujte podle pokynů k [osobním a vlastním zařízením uživatelů](enroll-your-device-in-intune-macos-cp.md).  

1. Zapněte zařízení s macOS. 
2. Vyberte svou zemi a klikněte na **Pokračovat**.  

   ![Snímek uvítací obrazovky Průvodce nastavením zařízení s macOS, na které je seznam jazyků na výběr](./media/macos-dep-welcome-1808.png)   
3. Zvolte rozložení klávesnice. Seznam obsahuje jednu nebo více možností podle toho, jakou zemi vyberete. Pokud chcete zobrazit všechny možnosti rozložení bez ohledu na vybranou zemi, klikněte na **Zobrazit vše**. Až budete hotovi, klikněte na **Pokračovat**.  

   ![Snímek obrazovky Průvodce nastavením zařízení s macOS s rozložením klávesnice, na které je seznam jazyků klávesnice na výběr, možnost Zobrazit vše a tlačítka Zpět a Pokračovat](./media/macos-dep-keyboard-1808.png)  
4. Vyberte vaši síť Wi-Fi. Abyste mohli pokračovat v nastavení, musíte mít připojení k internetu. Pokud vaši síť nevidíte nebo se potřebujete připojit přes drátovou síť, klikněte na tlačítko **Další možnosti sítě**. Až budete hotovi, klikněte na **Pokračovat**.  

   ![Snímek obrazovky Průvodce nastavením zařízení s macOS pro výběr sítě Wi-Fi, na které je seznam dostupných sítí na výběr a také tlačítka Další možnosti sítě, Zpět a Pokračovat](./media/macos-dep-wifi-1808.png)  
5. Po připojení k síti Wi-Fi se objeví obrazovka **Vzdálená správa**. Vzdálená správa umožňuje správci organizace vzdáleně nakonfigurovat na vašem zařízení účty, nastavení, aplikace a sítě požadované společností. Přečtěte si vysvětlení vzdálené správy, abyste porozuměli, jak bude zařízení spravované. Potom klikněte na **Pokračovat**.  

   ![Snímek obrazovky Průvodce nastavením zařízení s macOS pro vzdálenou správu, na které je text vysvětlující vzdálenou správu a odkaz na dokumentaci s dalšími informacemi a také tlačítka Zpět a Pokračovat](./media/macos-dep-remote-management-1-1808.png)  
6. Po zobrazení výzvy se přihlaste pomocí svého pracovního nebo školního účtu. Po ověření se do zařízení nainstaluje profil správy. Tento profil nakonfiguruje a umožní váš přístup k prostředkům organizace.  
7. Přečtěte si o ikoně ochrany osobních údajů, abyste později poznali, když se shromažďují osobní informace. Potom klikněte na **Pokračovat**.  

   ![Snímek obrazovky Průvodce nastavením zařízení s macOS pro ochranu osobních údajů, na které je obrázek dvou lidí podávajících si ruce, popis používání osobních informací společností Apple a také tlačítka Zpět a Pokračovat](./media/macos-dep-apple-data-privacy-1808.png)  
8. Až bude zařízení zaregistrované, může být potřeba udělat ještě další kroky. Kroky, které se vám zobrazí, závisejí na tom, jak vaše organizace přizpůsobila prostředí nastavení. Můžete být požádáni:
    * Přihlásit se k účtu Apple
    * Odsouhlasit podmínky a ujednání
    * Vytvořit účet počítače
    * Projít expresním nastavením
    * Nastavit váš Mac  
## <a name="get-the-company-portal-app"></a>Získání aplikace Portál společnosti      
Stáhněte si do svého zařízení aplikaci Portál společnosti Intune pro macOS. Tato aplikace vám umožní monitorovat, synchronizovat, přidat nebo odebrat zařízení ze správy a nainstalovat aplikace. V tomto postupu je také popsané, zaregistrovat zařízení na Portálu společnosti.  
1. Na zařízení s macOS přejděte na http://portal.manage.microsoft.com/EnrollmentRedirect.aspx.
2. Přihlaste se na web Portál společnosti přes svůj pracovní nebo školní účet. 
3. Klikněte na **Získat aplikaci** a stáhněte si instalační program aplikace Portál společnosti pro macOS.
4. Po zobrazení výzvy otevřete soubor .pkg a dokončete instalační kroky.
4. Otevřete aplikaci Portál společnosti a přihlaste se pomocí svého pracovního nebo školního účtu.
5. Najděte své zařízení a klikněte na **Zaregistrovat**.
6. Klikněte na **Pokračovat** > **Hotovo**. Vaše zařízení by se mělo zobrazit v aplikaci Portál společnosti jako vyhovující firemní zařízení.

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).
