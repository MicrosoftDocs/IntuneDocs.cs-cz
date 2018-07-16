---
title: Selektivní vymazání dat pomocí akcí přístupu zásad ochrany aplikací
titleSuffix: Microsoft Intune
description: Zjistěte, jak můžete v Intune selektivně vymazat data pomocí akcí přístupu zásad ochrany aplikací.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2cfd426a0ae7165a7aae60a90d104852fd834db6
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909112"
---
# <a name="selectively-wipe-data-using-app-protection-policy-access-actions-in-intune"></a>Selektivní vymazání dat pomocí akcí přístupu zásad ochrany aplikací v Intune

Pomocí zásad ochrany aplikací můžete v Intune nakonfigurovat nastavení, která koncovým uživatelům zablokují přístup k podnikové aplikaci nebo účtu. Tato nastavení se zaměřují na přemístění dat a požadavky na přístup, které vaše organizace stanovila například pro zařízení s jailbreakem a minimální verze operačního systému.
 
S využitím těchto nastavení můžete explicitně vymazat podniková data ze zařízení koncového uživatele jako akci, která se má provést při nedodržení předpisů. U některých nastavení budete moci nakonfigurovat více akcí (například zablokování přístupu a vymazání dat) na základě různých zadaných hodnot.

## <a name="create-an-app-protection-policy-using-access-actions"></a>Vytvoření zásad ochrany aplikací využívajících akce přístupu

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**.  
    Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** vyberte **Mobilní aplikace** > **Zásady ochrany aplikací**.
4. Klikněte na **Přidat zásadu** (můžete také upravit některou existující zásadu). 
5. Kliknutím na **Konfigurovat požadovaná nastavení** zobrazíte seznam dostupných nastavení, která se mají pro tuto zásadu konfigurovat. 
6. Když se v podokně **Nastavení** posunete dolů, uvidíte oddíl s názvem **Akce přístupu** s upravitelnou tabulkou.

    ![Snímek obrazovky akcí přístupu ochrany aplikací v Intune](./media/apps-selective-wipe-access-actions01.png)

7. Vyberte **Nastavení** a do sloupce **Hodnota** zadejte hodnotu, kterou uživatelé musí splnit, aby se přihlásili k firemní aplikaci. 
8. Ve sloupci **Akce** vyberte akci, která se má provést, pokud uživatelé nesplňují požadavky. V některých případech lze pro jedno nastavení nakonfigurovat více akcí. Další informace najdete v tématu [Vytvoření a přiřazení zásad ochrany aplikací](app-protection-policies.md).

>[!NOTE]
> Pokud chcete použít nastavení **Modely zařízení**, zadejte středníkem oddělený seznam identifikátorů modelů. 

## <a name="policy-settings"></a>Nastavení zásad 

Tabulka s nastavením zásad ochrany aplikací obsahuje sloupce **Nastavení**, **Hodnota** a **Akce**.

Pro iOS budete moci pomocí rozevíracího seznamu **Nastavení** nakonfigurovat akce pro následující nastavení:
-  Maximální počet pokusů o zadání PIN kódu
-  Offline období odkladu
-  Zařízení s jailbreakem nebo rootem
-  Minimální verze operačního systému
-  Minimální verze aplikace
-  Minimální verze sady SDK
-  Modely zařízení

Pro Android budete moci pomocí rozevíracího seznamu **Nastavení** nakonfigurovat akce pro následující nastavení:
-  Maximální počet pokusů o zadání PIN kódu
-  Offline období odkladu
-  Zařízení s jailbreakem nebo rootem
-  Minimální verze operačního systému
-  Minimální verze aplikace
-  Minimální verze opravy
-  Výrobci zařízení

Pokud má nastavení **Vyžadovat pro přístup PIN kód** hodnotu **Ano**, bude mít tabulka standardně vyplněné řádky **Offline období odkladu** a **Maximální počet pokusů o zadání PIN kódu**.
 
Pokud chcete konfigurovat některé nastavení, vyberte ho v rozevíracím seznamu ve sloupci **Nastavení**. Po výběru nastavení se na stejném řádku zpřístupní upravitelné textové pole ve sloupci **Hodnota**, pokud je potřeba nastavit hodnotu. Zároveň se zpřístupní rozevírací seznam ve sloupci **Akce** se sadou podmíněně spuštěných akcí použitelných pro dané nastavení. 

Následující seznam obsahuje nejčastější akce:
-  **Blokovat přístup** – zablokuje koncovému uživateli přístup k podnikové aplikaci.
-  **Vymazat data** – vymaže ze zařízení koncového uživatele podniková data.
-  **Upozornit** – zobrazí koncovému uživateli dialogové okno s upozorněním.

### <a name="additional-settings-and-actions"></a>Další nastavení a akce 

V některých případech, jako u nastavení **Minimální verze operačního systému**, můžete nakonfigurovat, aby se provedly všechny použitelné akce na základě různých čísel verzí. 

![Snímek obrazovky akcí přístupu ochrany aplikací v Intune – Minimální verze operačního systému](./media/apps-selective-wipe-access-actions05.png)

Jakmile je nastavení plně nakonfigurované, objeví se řádek v zobrazení jen pro čtení a bude možné ho kdykoli upravit. Ve sloupci **Nastavení** bude u tohoto řádku dostupný rozevírací seznam pro výběr. Nastavení, která už jsou nakonfigurovaná a neumožňují více akcí, nebudou v tomto rozevíracím seznamu dostupná k výběru.

## <a name="next-steps"></a>Další kroky

Další informace o zásadách ochrany aplikací v Intune zjistíte zde:
- [Vytvoření a přiřazení zásad ochrany aplikací](app-protection-policies.md)
- [Nastavení zásad ochrany aplikací pro iOS](app-protection-policy-settings-ios.md)
- [Nastavení zásad ochrany aplikací pro Android v Microsoft Intune](app-protection-policy-settings-android.md) 


