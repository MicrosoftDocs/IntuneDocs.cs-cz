---
title: Konfigurace zásad aktualizace softwaru iOS v Microsoft Intune – Azure | Microsoft Docs
description: V Microsoft Intune můžete vytvořit nebo přidat zásady konfigurace, které omezují, kdy se na zařízení s iOSem, která spravuje Intune nebo která jsou pod dohledem, mají automaticky instalovat aktualizace softwaru. Můžete zvolit datum a čas, kdy se aktualizace nemají instalovat. Můžete tyto zásady také přiřadit skupinám, uživatelům nebo zařízením a vyhledat případné chyby instalace.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/06/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: d39f4c541fd7ccf5ab2d09fdcf4f871ba3ee639c
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742393"
---
# <a name="add-ios-software-update-policies-in-intune"></a>Přidání zásad aktualizace softwaru iOS v Intune

Zásady aktualizací softwaru vám umožňují vynutit, aby se na zařízení s iOSem, která jsou pod dohledem, automaticky instalovala nejnovější dostupná aktualizace operačního systému. Při konfiguraci zásad můžete přidat dny a časy, kdy nechcete, aby se na zařízení instalovala aktualizace. 

Tato funkce platí pro:

- s Iosem 10.3 a novějším (pod dohledem)

Zařízení se přihlašuje k Intune přibližně každých 8 hodin. Pokud je dostupná nějaká aktualizace a není to v zakázaném čase, zařízení stáhne a nainstaluje nejnovější aktualizaci operačního systému. Pro aktualizaci zařízení nemusí uživatel nic udělat. Zásady nebrání tomu, aby uživatel aktualizoval operační systém ručně.

## <a name="configure-the-policy"></a>Konfigurace zásad

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **Aktualizace softwaru** > **Aktualizovat zásady pro iOS** > **Vytvořit**.
3. Zadejte následující nastavení:

    - **Název**: Zadejte název pro vaše zásady aktualizace softwaru. Zadejte například `iOS restricted update times`.
    - **Popis**: Zadejte popis zásady. Toto nastavení není povinné, ale doporučujeme ho zadat.

4. Vyberte **Nastavení > Konfigurace**. Zadejte následující nastavení:

    - **Vyberte časy, kdy chcete zakázat instalaci aktualizací**: Aktualizace se neinstalují nuceně zadejte omezený časový rámec. Při nastavování omezený časový rámec, zadejte následující údaje:

      - **Dny**: Vyberte dny v týdnu, kdy aktualizace se neinstalují. Třeba zkontrolujte pondělí, středu a pátek, aby se zabránilo aktualizace instalovaly v tyto dny.
      - **Časové pásmo**: Vyberte časové pásmo.
      - **Počáteční čas**: Zvolte čas zahájení omezený časový rámec. Zadejte například 5: 00, nenainstalují se aktualizace od 5: 00.
      - **Čas ukončení**: Zvolte koncový čas s omezeným přístupem časový rámec. Například zadejte 1: 00, můžou aktualizace instalovat počínaje 1: 00.

    - **Zpoždění viditelnost aktualizací softwaru pro koncové uživatele myší bez nutnosti změn plánovaných aktualizací (dny)**: 

      **Toto nastavení přesunuta do [omezení zařízení](device-restrictions-ios.md#general). Odebere se z tohoto umístění na portálu**. Krátkou dobu můžete zde změnit existující zásady. Po přibližně jeden měsíc, toto nastavení se odebere z existujících zásad.

      Chcete-li omezit dopad, doporučujeme:
        - Odeberte existující zásady z tohoto umístění na portálu.
        - Vytvořte nový [zásadu omezení pro zařízení](device-restrictions-ios.md#general).
        - Cílit na stejné uživatele jako původní zásadou.

      Pokud dojde ke konfliktu, toto nastavení nemá žádný účinek *Pokud* dvě hodnoty jsou identické. Aby se zabránilo konfliktu, nezapomeňte změnit nebo odebrat existující zásady z tohoto umístění na portálu.

5. Vyberte **OK** > **vytvořit** uložte provedené změny a vytvoříte zásadu.

Profil se vytvoří a zobrazí se v seznamu zásad. 

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

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).