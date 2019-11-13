---
title: Konfigurace zásad aktualizace softwaru iOS v Microsoft Intune – Azure | Microsoft Docs
description: V Microsoft Intune vytvořte nebo přidejte zásady konfigurace, které budou omezovat, kdy se aktualizace softwaru automaticky instalují na zařízení s iOS. Můžete zvolit datum a čas, kdy se aktualizace nemají instalovat. Můžete tyto zásady také přiřadit skupinám, uživatelům nebo zařízením a vyhledat případné chyby instalace.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0f9750603d19d9b19697c7d2660351c4586432f6
ms.sourcegitcommit: a7c35efb31c4efd816bd4aba29240013965aee92
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/13/2019
ms.locfileid: "73984186"
---
# <a name="add-ios-software-update-policies-in-intune"></a>Přidání zásad aktualizace softwaru pro iOS do Intune

Zásady aktualizací softwaru vám umožňují vynutit, aby se na zařízení s iOSem, která jsou pod dohledem, automaticky instalovala nejnovější dostupná aktualizace operačního systému. Při konfiguraci zásad můžete přidat dny a časy, kdy nechcete, aby se na zařízení instalovala aktualizace.

Tato funkce platí pro:

- iOS 10,3 a novější (pod dohledem)

Zařízení se přihlašuje k Intune přibližně každých 8 hodin. Pokud je aktualizace k dispozici, zařízení ji stáhne a nainstaluje, s výjimkou během časových omezení. I když proces aktualizace obvykle nezahrnuje interakci s uživatelem, pokud má zařízení heslo, bude uživatel muset zadat jeho zadání, aby mohl spustit aktualizaci softwaru. To platí pro iOS 10,3 a novější verze. Zásady nebrání tomu, aby uživatel aktualizoval operační systém ručně.

## <a name="configure-the-policy"></a>Konfigurace zásad

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Aktualizace softwaru** > **Aktualizovat zásady pro iOS** > **Vytvořit**.
3. Na kartě **základy** zadejte název této zásady, zadejte popis (volitelné) a pak vyberte **Další**.

   ![Karta základy](./media/software-updates-ios/basics-tab.png) 

4. Na kartě **aktualizovat nastavení zásad** zadejte časový rámec, v němž nejsou vynuceně nainstalovány aktualizace.  
   - Bloky v noci nejsou podporované a nemusí fungovat. Například nekonfigurujte zásadu s *počátečním časem* 8 ODP a *koncovým časem* 6 dop.
   - Zásada, která začíná v rozmezí od 12:00 do 12:00 a končí 12., se vyhodnocuje jako 0 hodin a ne za 24 hodin. Tato konfigurace nevede k žádnému omezení.

   Při nastavování časového rámce s omezením zadejte následující podrobnosti:

   - **Dnů**: Vyberte dny v týdnu, kdy se aktualizace nenainstalují. Například pokud chcete zabránit tomu, aby se aktualizace nainstalovaly na tyto dny, podívejte se na pondělí, středu a pátek.
   - **Časové pásmo**: Vyberte časové pásmo.
   - **Čas spuštění**: Vyberte čas spuštění omezeného časového rámce. Zadejte například 5 AM, takže aktualizace nejsou nainstalovány od 5.
   - **Koncový čas**: vyberte koncový čas časového rámce s omezeným časem. Zadejte například 1, aby bylo možné aktualizace instalovat od 1.
  
   > [!IMPORTANT]  
   > Zásada, která má *čas spuštění* a čas *ukončení* nastavenou na hodnotu 12, se vyhodnotí jako 0 hodin a ne za 24 hodin. Výsledkem není žádné omezení.  
    
   Pokud chcete v zařízeních se systémem iOS odložit viditelnost aktualizací softwaru po určitou dobu, nakonfigurujte tato nastavení v části [omezení zařízení](../configuration/device-restrictions-ios.md#general). Zásady aktualizace softwaru přepíšou všechna omezení zařízení. Při nastavování zásad aktualizace softwaru i omezení pro zpoždění viditelnosti aktualizací softwaru vynutí zařízení aktualizaci softwaru na základě zásad. Toto omezení platí tak, aby se uživatelům nezobrazila možnost aktualizovat samotné zařízení a aktualizace se odeslala v prvním časovém intervalu, jak je definováno v zásadách aktualizace pro iOS.

   Po nakonfigurování *nastavení zásad aktualizace*vyberte **Další**. 

5. Na kartě **značky oboru** vyberte **+ Vybrat rozsah značky** a otevřete tak podokno *Vybrat značky* , pokud je chcete použít pro zásady aktualizace.
   
   - V podokně **Vybrat značky** vyberte jednu nebo více značek a kliknutím na tlačítko **Vybrat** je přidejte do zásad a vraťte se do podokna *značky oboru* .  

   Až budete připraveni, vyberte **Další** a pokračujte v *přiřazení*.

6. Na kartě **přiřazení** zvolte **+ Vybrat skupiny, které se mají zahrnout** , a potom přiřaďte zásadu aktualizace k jedné nebo více skupinám. Pomocí **+ Vyberte skupiny, které se vyloučí** , abyste mohli přiřazení vyladit. Až budete připraveni, klikněte na tlačítko **Další** a pokračujte. 

   U zařízení používaných uživateli, na které zásady cílí, se vyhodnotí dodržování předpisů pro aktualizace. Tyto zásady podporují také zařízení bez uživatelů.

7. Na kartě **Revize + vytvořit** zkontrolujte nastavení a potom vyberte **vytvořit** , jakmile budete připraveni Uložit zásady aktualizace pro iOS. Vaše nová zásada se zobrazí v seznamu zásad aktualizace pro iOS.


Pokyny z týmu podpory pro Intune najdete v tématu [zpoždění viditelnosti aktualizací softwaru v Intune pro zařízení pod dohledem](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753).

> [!NOTE]
> Apple MDM neumožňuje vynutit, aby se aktualizace nainstalovaly na zařízení do určitého času nebo data.

## <a name="edit-a-policy"></a>Upravit zásadu
Můžete upravit existující zásadu, včetně změny časových omezení:

1. V části **aktualizace softwaru**vyberte možnost **aktualizovat zásady pro iOS** a pak vyberte zásadu, kterou chcete upravit.

2. Při prohlížení **vlastností**zásad vyberte **Upravit** pro stránku zásady, kterou chcete upravit.  
   ![upravit policejní](./media/software-updates-ios/edit-policy.png)   

3. Po zavedení změny vyberte **zkontrolovat + uložit**  > **Uložit** , aby se změny uložily, a vraťte se do *vlastností*zásad.  
 
> [!NOTE]
> Pokud je **čas spuštění** i **čas ukončení** nastavený na 12 DOP, Intune nekontroluje při instalaci aktualizací omezení. To znamená, že všechny konfigurace, které máte k dispozici pro **dobu výběru** , se budou ignorovat a aktualizace se můžou nainstalovat kdykoli.  


## <a name="monitor-device-installation-failures"></a>Monitorování chyb instalace na zařízeních
<!-- 1352223 -->
**Aktualizace softwaru** > **chyby instalace pro zařízení s iOS** zobrazují seznam zařízení s iOS, která cílí na zásady aktualizace, se pokusily o aktualizaci a nešlo je aktualizovat. U každého zařízení můžete zobrazit, proč se automaticky neaktualizovalo. Zařízení, která jsou v pořádku a aktuální, se v seznamu nezobrazují. „Aktuální“ zařízení obsahují nejnovější aktualizaci, kterou samotné zařízení podporuje.

## <a name="next-steps"></a>Další kroky

[Monitorujte svůj stav](../configuration/device-profile-monitor.md).
