---
title: Vymazání dat pomocí akce přístupu zásad ochrany aplikací
titleSuffix: Microsoft Intune
description: Zjistěte, jak můžete v Intune selektivně vymazat data pomocí akcí přístupu zásad ochrany aplikací.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 490c7312f510651cafc6ade516e5f7dca8131b3a
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66043958"
---
# <a name="selectively-wipe-data-using-app-protection-policy-access-actions-in-intune"></a>Selektivní vymazání dat pomocí akcí přístupu zásad ochrany aplikací v Intune

Pomocí zásad ochrany aplikací můžete v Intune nakonfigurovat nastavení, která koncovým uživatelům zablokují přístup k podnikové aplikaci nebo účtu. Tato nastavení se zaměřují na přemístění dat a požadavky na přístup, které vaše organizace stanovila například pro zařízení s jailbreakem a minimální verze operačního systému.
 
S využitím těchto nastavení můžete explicitně vymazat podniková data ze zařízení koncového uživatele jako akci, která se má provést při nedodržení předpisů. U některých nastavení budete moci nakonfigurovat více akcí (například zablokování přístupu a vymazání dat) na základě různých zadaných hodnot.

## <a name="create-an-app-protection-policy-using-access-actions"></a>Vytvoření zásad ochrany aplikací využívajících akce přístupu

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**.  
    Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** vyberte **Klientské aplikace** > **Zásady ochrany aplikací**.
4. Klikněte na **Přidat zásadu** (můžete také upravit některou existující zásadu). 
5. Kliknutím na **Konfigurovat požadovaná nastavení** zobrazíte seznam dostupných nastavení, která se mají pro tuto zásadu konfigurovat. 
6. Když se v podokně Nastavení posunete dolů, uvidíte oddíl s názvem **Akce přístupu** s tabulkou, kterou můžete upravit.

    ![Snímek obrazovky akcí přístupu ochrany aplikací v Intune](./media/apps-selective-wipe-access-actions01.png)

7. Vyberte **Nastavení** a do sloupce **Hodnota** zadejte hodnotu, kterou uživatelé musí splnit, aby se přihlásili k firemní aplikaci. 
8. Ve sloupci **Akce** vyberte akci, která se má provést, pokud uživatelé nesplňují požadavky. V některých případech lze pro jedno nastavení nakonfigurovat více akcí. Další informace najdete v tématu [Vytvoření a přiřazení zásad ochrany aplikací](app-protection-policies.md).

>[!NOTE]
> Pokud chcete použít nastavení **Modely zařízení nebo Výrobci zařízení**, zadejte seznam identifikátorů modelů s hodnotami oddělenými středníkem. Do seznamů s více hodnotami nevkládejte mezery. U těchto hodnot se nerozlišují velká a malá písmena. 

## <a name="policy-settings"></a>Nastavení zásad 

Tabulka s nastavením zásad ochrany aplikací obsahuje sloupce **Nastavení**, **Hodnota** a **Akce**.

### <a name="ios-policy-settings"></a>Nastavení zásad pro iOS
Pro iOS budete moci pomocí rozevíracího seznamu **Nastavení** nakonfigurovat akce pro následující nastavení:
-  Maximální počet pokusů o zadání PIN kódu
-  Offline období odkladu
-  Zařízení s jailbreakem nebo rootem
-  Minimální verze operačního systému
-  Minimální verze aplikace
-  Minimální verze sady SDK
-  Modely zařízení

Pokud chcete použít nastavení **Modely zařízení**, zadejte seznam identifikátorů modelů iOS a oddělte je středníkem. Identifikátor modelu iOS najdete ve sloupci Device Type (Typ zařízení) v [ dokumentaci podpory aplikace HockeyApp](https://support.hockeyapp.net/kb/client-integration-ios-mac-os-x-tvos/ios-device-types).<br>
Příklad zadání: *iPhone5,2;iPhone5,3*

Na zařízeních koncových uživatelů by klient Intune provedl akci založenou na jednoduché shodě řetězců modelu zařízení zadaných v okně Intune pro zásady ochrany aplikací. Párování zcela závisí na tom, co zařízení ohlásí. Jako správci IT vám doporučujeme toto nastavení otestovat na zařízeních od různých výrobcích a na různých modelech zařízení u malé skupiny uživatelů, abyste si ověřili, že se nastavení chová, jak má. Výchozí hodnotou je **Nenakonfigurováno**.<br>
Nastavte jednu z následujících akcí: 
- Povolit zadané (blokovat nezadané)
- Povolit zadané (vymazat nezadané)

**Co se stane, když správce zadá seznam identifikátorů modelů iOS, který se v různých zásadách pro stejné aplikace pro stejného uživatele Intune liší?**<br>
Pokud mezi dvěma zásadami ochrany aplikací dojde ke konfliktu nakonfigurovaných hodnot, Intune obvykle zvolí nejvíce omezující přístup. Výsledná zásada odeslaná do cílové aplikace, kterou otevírá cílový uživatel Intune, by tedy byla průsečík identifikátorů modelů iOS uvedených v seznamu v *Zásadě A* a *Zásadě B*, které cílí na stejnou kombinaci aplikace a uživatele. *Zásada A* například určuje iPhone5,2;iPhone5,3 a *Zásada B* určuje iPhone5,3. Výsledná zásada, která se uplatní u příslušného uživatele, na kterého cílí současně *Zásada A* i *Zásada B*, bude iPhone5,3. 

### <a name="android-policy-settings"></a>Nastavení zásad pro Android

Pro Android budete moci pomocí rozevíracího seznamu **Nastavení** nakonfigurovat akce pro následující nastavení:
-  Maximální počet pokusů o zadání PIN kódu
-  Offline období odkladu
-  Zařízení s jailbreakem nebo rootem
-  Minimální verze operačního systému
-  Minimální verze aplikace
-  Minimální verze opravy
-  Výrobci zařízení
-  V rámci ověření zařízení SafetyNet
-  Kontrola ohrožení aplikací

Pokud chcete použít nastavení **Výrobci zařízení**, zadejte seznam výrobců zařízení s Androidem oddělených středníkem. Výrobce zařízení s Androidem najdete v nastavení zařízení.<br>
Příklad vstupu: *Výrobce A; Výrobce B* 

>[!NOTE]
> Toto jsou některé běžné výrobci nahlásila zařízení pomocí Intune a může sloužit jako vstup: Asus;Blackberry;Bq;Gionee;Google;Hmd global;Htc;Huawei;Infinix;Kyocera;Lemobile;Lenovo;Lge;Motorola;Oneplus;Oppo;Samsung;Sharp;Sony;Tecno;Vivo;Vodafone;Xiaomi;Zte;Zuk

Na zařízeních koncových uživatelů by klient Intune provedl akci založenou na jednoduché shodě řetězců modelu zařízení zadaných v okně Intune pro zásady ochrany aplikací. Párování zcela závisí na tom, co zařízení ohlásí. Jako správci IT vám doporučujeme toto nastavení otestovat na zařízeních od různých výrobcích a na různých modelech zařízení u malé skupiny uživatelů, abyste si ověřili, že se nastavení chová, jak má. Výchozí hodnotou je **Nenakonfigurováno**.<br>
Nastavte jednu z následujících akcí: 
- Povolit zadané (blokovat nezadané)
- Povolit zadané (vymazat nezadané)

**Co se stane, když správce zadá seznam výrobců zařízení s Androidem, který se v různých zásadách pro stejné aplikace pro stejného uživatele Intune liší?**<br>
Pokud mezi dvěma zásadami ochrany aplikací dojde ke konfliktu nakonfigurovaných hodnot, Intune obvykle zvolí nejvíce omezující přístup. Výsledná zásada odeslaná do cílové aplikace, kterou otevírá cílový uživatel Intune, by tedy byla průsečíkem výrobců zařízení s Androidem uvedených v seznamu v *Zásadě A* a *Zásadě B*, které cílí na stejnou kombinaci aplikace a uživatele. *Zásada A* například určuje Google;Samsung a *Zásada B* určuje Google. Výsledná zásada, která se uplatní u příslušného uživatele Intune, na kterého cílí současně *Zásada A* i *Zásada B*, bude Google. 

### <a name="additional-settings-and-actions"></a>Další nastavení a akce 

Pokud má nastavení **Vyžadovat pro přístup PIN kód** hodnotu **Ano**, bude mít tabulka standardně vyplněné řádky **Offline období odkladu** a **Maximální počet pokusů o zadání PIN kódu**.
 
Pokud chcete konfigurovat některé nastavení, vyberte ho v rozevíracím seznamu ve sloupci **Nastavení**. Po výběru nastavení se na stejném řádku zpřístupní upravitelné textové pole ve sloupci **Hodnota**, pokud je potřeba nastavit hodnotu. Zároveň se zpřístupní rozevírací seznam ve sloupci **Akce** se sadou podmíněně spuštěných akcí použitelných pro dané nastavení. 

Následující seznam obsahuje nejčastější akce:
-  **Blokovat přístup** – zablokuje koncovému uživateli přístup k podnikové aplikaci.
-  **Vymazat data** – vymaže ze zařízení koncového uživatele podniková data.
-  **Upozornit** – zobrazí koncovému uživateli dialogové okno s upozorněním.

V některých případech, jako u nastavení **Minimální verze operačního systému**, můžete nakonfigurovat, aby se provedly všechny použitelné akce na základě různých čísel verzí. 

![Snímek obrazovky s app protection přístup akce – verze operačního systému Min](./media/apps-selective-wipe-access-actions05.png)

Jakmile je nastavení plně nakonfigurované, objeví se řádek v zobrazení jen pro čtení a bude možné ho kdykoli upravit. Ve sloupci **Nastavení** bude u tohoto řádku dostupný rozevírací seznam pro výběr. Nastavení, která už jsou nakonfigurovaná a neumožňují více akcí, nebudou v tomto rozevíracím seznamu dostupná k výběru.

## <a name="next-steps"></a>Další postup

Další informace o zásadách ochrany aplikací v Intune zjistíte zde:
- [Vytvoření a přiřazení zásad ochrany aplikací](app-protection-policies.md)
- [Nastavení zásad ochrany aplikací pro iOS](app-protection-policy-settings-ios.md)
- [Nastavení zásad ochrany aplikací pro Android v Microsoft Intune](app-protection-policy-settings-android.md) 
