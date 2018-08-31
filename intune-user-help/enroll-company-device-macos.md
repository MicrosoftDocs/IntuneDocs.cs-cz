---
title: Registrace zařízení s macOS vlastněného nebo poskytnutého vaší společností do správy | Microsoft Docs
description: Tento článek popisuje, jak zaregistrovat v Intune zařízení s macOS, které zakoupila a poskytla vaše organizace.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/24/2018
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
ms.openlocfilehash: 272a82f7d3d62d117fa5506ccf446b3169ff514f
ms.sourcegitcommit: bb56ada81e6d4950f130415918c4acc455bb52dd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/27/2018
ms.locfileid: "43016223"
---
# <a name="get-your-company-owned-macos-device-managed"></a>Zahrnutí zařízení s macOS vlastněné vaší společností do správy

Zjistěte, jak nové zařízení s macOS automaticky spravovat v Intune.

Pracovní a školní zařízení jsou často předem nakonfigurovaná, než je obdržíte. Když zařízení zapnete a poprvé se přihlásíte, vaše organizace do něho pošle předem nakonfigurované nastavení. Až zařízení dokončí nastavení, budete mít přístup k pracovním nebo školním prostředkům. 

Aby se nastavení správy zahájilo, zapněte zařízení a přihlaste se pomocí pracovních nebo školních přihlašovacích údajů. Zbytek tohoto článku popisuje kroky a obrazovky, které uvidíte při procházení Průvodce nastavením.   

## <a name="what-is-apple-dep"></a>Co je Apple DEP?
Pokud máte zařízení vlastněné společností, bylo možná zakoupené v rámci programu Apple DEP (Device Enrollment Program). Některé organizace nakupují velká množství zařízení s iOSem nebo macOS prostřednictvím programu Apple DEP. Organizace pak můžou zařízení konfigurovat a spravovat v rámci svého upřednostňovaného poskytovatele správy mobilních zařízení, jako je Intune. Pokud jste správce a chcete získat o programu Apple DEP další informace, podívejte se na článek [Automatická registrace zařízení s macOS do Programu registrace zařízení Apple](https://docs.microsoft.com/intune/device-enrollment-program-enroll-macos).  

## <a name="set-up-your-macos-device"></a>Nastavení zařízení s macOS  
Zařízení s macOS zaregistrujete do správy provedením následujících kroků. Pokud nepoužíváte zařízení vlastněné společností, ale svoje vlastní zařízení, postupujte podle pokynů k [osobním a vlastním zařízením uživatelů](enroll-your-device-in-intune-macos-cp.md).  

1. Zapněte zařízení s macOS. 
2. Zvolte váš **Jazyk** a klikněte na **Pokračovat**.  

   ![Snímek uvítací obrazovky Průvodce nastavením zařízení s macOS, na které je seznam jazyků na výběr](./media/macos-dep-welcome-1808.png)   
3. Zvolte rozložení klávesnice. Seznam obsahuje jednu nebo více možností podle toho, jaký jazyk jste vybrali. Pokud chcete zobrazit všechny možnosti rozložení bez ohledu na vybraný jazyk, klikněte na **Zobrazit vše**. Až budete hotovi, klikněte na **Pokračovat**.  

   ![Snímek obrazovky Průvodce nastavením zařízení s macOS s rozložením klávesnice, na které je seznam jazyků klávesnice na výběr, možnost Zobrazit vše a tlačítka Zpět a Pokračovat](./media/macos-dep-keyboard-1808.png)  
4. Vyberte vaši síť Wi-Fi. Abyste mohli pokračovat v nastavení, musíte mít připojení k internetu. Pokud vaši síť nevidíte nebo se potřebujete připojit přes drátovou síť, klikněte na tlačítko **Další možnosti sítě**. Až budete hotovi, klikněte na **Pokračovat**.  

   ![Snímek obrazovky Průvodce nastavením zařízení s macOS pro výběr sítě Wi-Fi, na které je seznam dostupných sítí na výběr a také tlačítka Další možnosti sítě, Zpět a Pokračovat](./media/macos-dep-wifi-1808.png)  
5. Po připojení k síti Wi-Fi se objeví obrazovka **Vzdálená správa**. Vzdálená správa umožňuje správci organizace vzdáleně nakonfigurovat na vašem zařízení účty, nastavení, aplikace a sítě požadované společností. Než budete pokračovat, přečtěte si dokumentaci o správě zařízení. Potom klikněte na **Pokračovat**.  

   ![Snímek obrazovky Průvodce nastavením zařízení s macOS pro vzdálenou správu, na které je text vysvětlující vzdálenou správu a odkaz na dokumentaci s dalšími informacemi a také tlačítka Zpět a Pokračovat](./media/macos-dep-remote-management-1-1808.png)  
6. Po zobrazení výzvy se přihlaste pomocí svého pracovního nebo školního účtu. Po vašem ověření nainstaluje vaše zařízení profil správy. Tento profil nakonfiguruje a umožní váš přístup k prostředkům organizace.  
7. Přečtěte si o ikoně ochrany osobních údajů, abyste později poznali, když se shromažďují osobní informace. Potom klikněte na **Pokračovat**.  

   ![Snímek obrazovky Průvodce nastavením zařízení s macOS pro ochranu osobních údajů, na které je obrázek dvou lidí podávajících si ruce, popis používání osobních informací společností Apple a také tlačítka Zpět a Pokračovat](./media/macos-dep-apple-data-privacy-1808.png)  
8. Až bude zařízení zaregistrované, může být potřeba udělat ještě další kroky. Kroky, které se vám zobrazí, závisejí na tom, jak vaše organizace přizpůsobila prostředí nastavení. Můžete být požádáni:
    * Přihlásit se k účtu Apple
    * Odsouhlasit podmínky a ujednání
    * Vytvořit účet počítače
    * Projít expresním nastavením
    * Nastavit váš Mac  
## <a name="get-the-company-portal-app"></a>Získání aplikace Portál společnosti      
Abyste na své zařízení získali aplikaci Portál společnosti Intune, přejděte do App Storu. Tato aplikace vám umožní monitorovat, synchronizovat, přidat nebo odebrat zařízení ze správy a nainstalovat aplikace.

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://portal.manage.microsoft.com#HelpDeskDialog).
