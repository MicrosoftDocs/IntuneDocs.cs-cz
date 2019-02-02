---
title: Konfigurace zásad aktualizace softwaru iOS v Microsoft Intune – Azure | Microsoft Docs
description: V Microsoft Intune můžete vytvořit nebo přidat zásady konfigurace, které omezují, kdy se na zařízení s iOSem, která spravuje Intune nebo která jsou pod dohledem, mají automaticky instalovat aktualizace softwaru. Můžete zvolit datum a čas, kdy se aktualizace nemají instalovat. Můžete tyto zásady také přiřadit skupinám, uživatelům nebo zařízením a vyhledat případné chyby instalace.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
search.appverid: MET150
ms.openlocfilehash: d73dc96c966b93f26269cc53527a787824c94d3b
ms.sourcegitcommit: 00fe2b601e3becbe5d644fcbd35a706da3b43af2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/02/2019
ms.locfileid: "55652625"
---
# <a name="configure-ios-update-policies-in-intune"></a>Konfigurace zásad aktualizací pro iOS v Intune

Zásady aktualizací softwaru vám umožňují vynutit, aby se na zařízení s iOSem, která jsou pod dohledem, automaticky instalovala nejnovější dostupná aktualizace operačního systému. Tato funkce je dostupná jenom pro zařízení pod dohledem. Při konfiguraci zásad můžete přidat dny a časy, kdy nechcete, aby se na zařízení instalovala aktualizace. 

Zařízení se přihlašuje k Intune přibližně každých 8 hodin. Pokud je dostupná nějaká aktualizace a není to v zakázaném čase, zařízení stáhne a nainstaluje nejnovější aktualizaci operačního systému. Pro aktualizaci zařízení nemusí uživatel nic udělat. Zásady nebrání tomu, aby uživatel aktualizoval operační systém ručně.

Tato funkce podporuje zařízení s iOSem 10.3 a novějšími verzemi. Nastavení zpoždění je k dispozici v iOSu 11.3 a novějších verzích.

## <a name="configure-the-policy"></a>Konfigurace zásad
1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Aktualizace softwaru** > **Aktualizovat zásady pro iOS** > **Vytvořit**.
4. Zadejte název a popis zásad.
5. Vyberte **Nastavení**. 

    Zadejte podrobnosti o časech, kdy se nemá u zařízení s iOSem vynucovat instalace nejnovějších aktualizací. Toto nastavení vytvoří časový rámec omezení. Můžete nakonfigurovat **dny** v týdnu, **časové pásmo**, **počáteční čas**, **koncový čas** a možnost **podržet zpřístupnění aktualizací softwaru (dny)** pro uživatele. Dále můžete vybrat pozdržení aktualizací softwaru v rozsahu 1 až 90 dní. Když vyprší platnost zpoždění, uživatelé získají oznámení, které nejstarší verzi operačního systému, která byla k dispozici při aktivaci zpoždění. Pokud chcete pozdržení aktualizací softwaru vypnout, zadejte hodnotu 0. Tato nastavení aktualizací se uplatní jen na zařízeních s iOSem pod dohledem.
  
    Například pokud iOS 12a je k dispozici na **1. ledna** a máte **aktualizace operačního systému zpoždění** nastavena na **5 dní**, tuto konkrétní verzi nebude zobrazovat jako dostupná aktualizace na žádné straně uživatel zařízení přiřazená k tomuto profilu. Na **šestý den** následující verzi, že aktualizace zobrazí jako dostupné a všichni koncoví uživatelé jsou zdarma k zahájení aktualizace.


6. Vyberte **OK** uložte provedené změny. Výběrem **Vytvořit** vytvořte tyto zásady.

Profil se vytvoří a zobrazí se v seznamu zásad. Apple MDM neumožňuje vynutit, aby se aktualizace nainstalovaly na zařízení do určitého času nebo data. 

## <a name="change-the-restricted-times-for-the-policy"></a>Změna časů s omezeným přístupem u zásady

1. V části **Aktualizace softwaru** vyberte **Aktualizovat zásady pro iOS**.
2. Zvolte existující zásady > **Vlastnosti**.
3. Aktualizace zakázaného času:
    
    1. Vyberte dny v týdnu.
    2. Zvolte časové pásmo, ve kterém se tyto zásady použijí.
    3. Zadejte počáteční a koncový čas pro zakázané hodiny.

    > [!NOTE]
    > Pokud jsou **počáteční čas** i **koncový čas** nastavené na 12:00, je ovládací prvek pro dobu údržby vypnutý.

## <a name="assign-the-policy-to-users"></a>Přiřazení zásad uživatelům

Existující zásady se přiřazují skupinám, uživatelům nebo zařízením. Po přiřazení začnou zásady platit.

1. V části **Aktualizace softwaru** vyberte **Aktualizovat zásady pro iOS**.
2. Zvolte existující zásady > **Přiřazení**. 
3. Vyberte skupiny, uživatele nebo zařízení Azure Active Directory, které se mají zahrnout nebo vyloučit z těchto zásad.
4. Volbou **Uložit** zásady nasadíte u určených skupin.

U zařízení používaných uživateli, na které zásady cílí, se vyhodnotí dodržování předpisů pro aktualizace. Tyto zásady podporují také zařízení bez uživatelů.

## <a name="monitor-device-installation-failures"></a>Monitorování chyb instalace na zařízeních
Možnost <!-- 1352223 -->
**Aktualizace softwaru** > **Chyby instalace pro zařízení s iOSem** zobrazuje seznam zařízení s iOSem, která jsou pod dohledem a na která zásady aktualizace cílí, na kterých se provedl pokus o aktualizaci a která se nepodařilo aktualizovat. U každého zařízení můžete zobrazit, proč se automaticky neaktualizovalo. Zařízení, která jsou v pořádku a aktuální, se v seznamu nezobrazují. „Aktuální“ zařízení obsahují nejnovější aktualizaci, kterou samotné zařízení podporuje.

