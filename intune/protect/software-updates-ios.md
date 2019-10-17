---
title: Konfigurace zásad aktualizace softwaru iOS v Microsoft Intune – Azure | Microsoft Docs
description: V Microsoft Intune můžete vytvořit nebo přidat zásady konfigurace, které omezují, kdy se na zařízení s iOSem, která spravuje Intune nebo která jsou pod dohledem, mají automaticky instalovat aktualizace softwaru. Můžete zvolit datum a čas, kdy se aktualizace nemají instalovat. Můžete tyto zásady také přiřadit skupinám, uživatelům nebo zařízením a vyhledat případné chyby instalace.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: c5313cae6aa903af910471cb79f021e30a3263dd
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503718"
---
# <a name="add-ios-software-update-policies-in-intune"></a>Přidání zásad aktualizace softwaru pro iOS do Intune

Zásady aktualizací softwaru vám umožňují vynutit, aby se na zařízení s iOSem, která jsou pod dohledem, automaticky instalovala nejnovější dostupná aktualizace operačního systému. Při konfiguraci zásad můžete přidat dny a časy, kdy nechcete, aby se na zařízení instalovala aktualizace.

Tato funkce platí pro:

- iOS 10,3 a novější (pod dohledem)

Zařízení se přihlašuje k Intune přibližně každých 8 hodin. Pokud je dostupná nějaká aktualizace a není to v zakázaném čase, zařízení stáhne a nainstaluje nejnovější aktualizaci operačního systému. Pro aktualizaci zařízení nemusí uživatel nic udělat. Zásady nebrání tomu, aby uživatel aktualizoval operační systém ručně.

## <a name="configure-the-policy"></a>Konfigurace zásad

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Aktualizace softwaru** > **Aktualizovat zásady pro iOS** > **Vytvořit**.
3. Zadejte následující nastavení:

    - **Název**: zadejte název pro zásady aktualizace softwaru. Zadejte například `iOS restricted update times`.
    - **Popis**: zadejte popis zásady. Toto nastavení není povinné, ale doporučujeme ho zadat.

4. Vyberte **nastavení > nakonfigurovat**. Zadejte následující nastavení:

    - **Vyberte dobu, po kterou se zabrání instalaci aktualizací**: zadejte omezený časový rámec v případě, že aktualizace nejsou vynuceně nainstalovány.
      - Bloky v noci nejsou podporované a nemusí fungovat. Například nekonfigurujte zásadu s *počátečním časem* 8 ODP a *koncovým časem* 6 dop.
      - Zásada, která začíná v rozmezí od 12:00 do 12:00 a končí 12., se vyhodnocuje jako 0 hodin a ne za 24 hodin, což nevede k omezení.

      Při nastavování časového rámce s omezením zadejte následující podrobnosti:

      - **Dnů**: Vyberte dny v týdnu, kdy se aktualizace nenainstalují. Například pokud chcete zabránit tomu, aby se aktualizace nainstalovaly na tyto dny, podívejte se na pondělí, středu a pátek.
      - **Časové pásmo**: Vyberte časové pásmo.
      - **Čas spuštění**: Vyberte čas spuštění omezeného časového rámce. Zadejte například 5 AM, takže aktualizace nejsou nainstalovány od 5.
      - **Koncový čas**: vyberte koncový čas časového rámce s omezeným časem. Zadejte například 1, aby bylo možné aktualizace instalovat od 1.

    - **Zpoždění viditelnosti aktualizací softwaru u koncových uživatelů bez změny v naplánovaných aktualizacích v zásadách aktualizace softwaru (dny)** : 

      \* * Pokud chcete zpozdit viditelnost aktualizací softwaru po určitou dobu na zařízeních s iOS pod dohledem, nakonfigurujte tato nastavení v části [omezení zařízení](../configuration/device-restrictions-ios.md#general). Zásady aktualizace softwaru přepíšou všechna omezení zařízení. Pokud jste obě nastavili, zásada aktualizace softwaru se bude nacházet napřed pokaždé.

      > [!IMPORTANT]  
      > Zásada, která má *čas spuštění* a čas *ukončení* nastavenou na hodnotu 12, se vyhodnotí jako 0 hodin a ne za 24 hodin. Výsledkem není žádné omezení.  

5. Výběrem **OK** > **vytvořit** uložte změny a vytvořte zásadu.

Profil se vytvoří a zobrazí se v seznamu zásad.

Pokyny z týmu podpory pro Intune najdete v tématu [zpoždění viditelnosti aktualizací softwaru v Intune pro zařízení pod dohledem](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753).

> [!NOTE]
> Apple MDM neumožňuje vynutit, aby se aktualizace nainstalovaly na zařízení do určitého času nebo data.

## <a name="change-the-restricted-times-for-the-policy"></a>Změna časů s omezeným přístupem u zásady

1. V části **Aktualizace softwaru** vyberte **Aktualizovat zásady pro iOS**.
2. Zvolte existující zásady > **Vlastnosti**.
3. Aktualizace zakázaného času:

    1. Vyberte dny v týdnu.
    2. Zvolte časové pásmo, ve kterém se tyto zásady použijí.
    3. Zadejte počáteční a koncový čas pro zakázané hodiny.

    > [!NOTE]
    > Pokud je **čas spuštění** a **čas ukončení** nastavený na 12am, pak Intune nekontroluje omezení, kdy se mají aktualizace instalovat. To znamená, že všechny konfigurace, které máte k dispozici pro **dobu výběru** , se budou ignorovat a aktualizace se můžou nainstalovat kdykoli.  

## <a name="assign-the-policy-to-users"></a>Přiřazení zásad uživatelům

Existující zásady se přiřazují skupinám, uživatelům nebo zařízením. Po přiřazení začnou zásady platit.

1. V části **Aktualizace softwaru** vyberte **Aktualizovat zásady pro iOS**.
2. Zvolte existující zásady > **Přiřazení**.
3. Vyberte skupiny, uživatele nebo zařízení Azure Active Directory, které se mají zahrnout nebo vyloučit z těchto zásad.
4. Volbou **Uložit** zásady nasadíte u určených skupin.

U zařízení používaných uživateli, na které zásady cílí, se vyhodnotí dodržování předpisů pro aktualizace. Tyto zásady podporují také zařízení bez uživatelů.

## <a name="monitor-device-installation-failures"></a>Monitorování chyb instalace na zařízeních
<!-- 1352223 -->
**Aktualizace softwaru** > **chyby instalace pro zařízení s iOS** zobrazují seznam zařízení s iOS, která cílí na zásady aktualizace, se pokusily o aktualizaci a nešlo je aktualizovat. U každého zařízení můžete zobrazit, proč se automaticky neaktualizovalo. Zařízení, která jsou v pořádku a aktuální, se v seznamu nezobrazují. „Aktuální“ zařízení obsahují nejnovější aktualizaci, kterou samotné zařízení podporuje.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](../configuration/device-profile-assign.md) a [monitorujte jeho stav](../configuration/device-profile-monitor.md).
