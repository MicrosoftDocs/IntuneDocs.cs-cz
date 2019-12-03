---
title: Použití OEMConfig na zařízeních s Androidem Enterprise v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí Microsoft Intune můžete spravovat a používat zařízení se systémem Android Enterprise pomocí OEMConfig. Podívejte se na všechny kroky, včetně přehledu, informace o požadavcích, vytvoření konfiguračního profilu v Intune a zobrazení seznamu podporovaných aplikací OEMConfig.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 075e7a99f72de30e83447a2869154859e33356b9
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390840"
---
# <a name="use-and-manage-android-enterprise-devices-with-oemconfig-in-microsoft-intune"></a>Používání a Správa zařízení s Androidem Enterprise pomocí OEMConfig v Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

V Microsoft Intune můžete použít OEMConfig k přidání, vytvoření a přizpůsobení nastavení pro zařízení s Androidem Enterprise, která jsou specifická pro výrobce OEM. OEMConfig se obvykle používá ke konfiguraci nastavení, která nejsou integrovaná do Intune. Různí výrobci OEM (Original Equipment Manufacturer) zahrnují různá nastavení. Dostupná nastavení závisí na tom, co výrobce OEM zahrnuje do své aplikace OEMConfig.

Tato funkce platí pro:  

- Android Enterprise

Tento článek popisuje OEMConfig, seznam požadavků, ukazuje, jak vytvořit konfigurační profil a seznam podporovaných aplikací OEMConfig v Intune.

## <a name="overview"></a>Overview

Zásady OEMConfig jsou speciálním typem zásad konfigurace zařízení, které se podobají [zásadám konfigurace aplikací](../apps/app-configuration-policies-overview.md). OEMConfig je standard definovaný společností Google, který využívá konfiguraci aplikací v Androidu k odesílání nastavení zařízení do aplikací napsaných výrobci OEM (Original Equipment Manufacturer). Tento standard umožňuje výrobcům OEM a žádnou Emms (Enterprise Mobility Management) vytvářet a podporovat standardizované funkce specifické pro výrobce OEM. [Přečtěte si další informace o OEMConfig](https://blog.google/products/android-enterprise/oemconfig-supports-enterprise-device-features/).

V minulosti žádnou Emms, jako je třeba Intune, ruční sestavení podpory pro funkce specifické pro výrobce OEM po jejich zavedení výrobcem OEM. Tento přístup vede k duplicitnímu úsilí a pomalému přijetí.

Pomocí OEMConfig vytvoří výrobce OEM schéma, které definuje funkce pro správu specifické pro výrobce OEM. Výrobce OEM vloží schéma do aplikace a pak tuto aplikaci vloží do Google Play. Modul EMM načte schéma z aplikace a zpřístupní schéma v konzole pro správu modulu EMM. Konzola umožňuje správcům Intune konfigurovat nastavení ve schématu.

Když se aplikace OEMConfig nainstaluje na zařízení, použije se nastavení nakonfigurovaná v konzole pro správu modulu EMM ke správě zařízení. Nastavení na zařízení spouští aplikace OEMConfig místo agenta MDM vytvořeného modulem EMM.

Když výrobce OEM přidá a vylepšuje funkce správy, výrobce OEM také aktualizuje aplikaci v Google Play. Jako správce získáte tyto nové funkce a aktualizace (včetně oprav), aniž byste čekali, až žádnou Emms tyto aktualizace zahrnou.

> [!TIP]
> OEMConfig můžete použít jenom u zařízení, která tuto funkci podporují, a mít odpovídající aplikaci OEMConfig. Konkrétní podrobnosti získáte od výrobce OEM.

## <a name="before-you-begin"></a>Před zahájením

Při používání OEMConfig si pamatujte na následující informace:

- Intune zpřístupňuje schéma aplikace OEMConfig, abyste ho mohli nakonfigurovat. Intune neověřuje ani nemění schéma, které poskytuje aplikace. Takže pokud je schéma nesprávné nebo obsahuje nepřesná data, jsou tato data pořád odesílána do zařízení. Pokud narazíte na problém, který pochází z schématu, obraťte se na výrobce OEM s pokyny.
- Intune neovlivňuje ani neovládá obsah schématu aplikace. Intune například nemá žádnou kontrolu nad řetězci, jazykem, povolenými akcemi a tak dále. Doporučujeme obrátit se na výrobce OEM, kde najdete podrobnosti a osvědčené postupy pro správu jejich zařízení pomocí OEMConfig.
- Výrobci OEM můžou kdykoli aktualizovat své podporované funkce a schémata a nahrát novou aplikaci do Google Play. Intune vždycky synchronizuje nejnovější verzi aplikace OEMConfig z Google Play. Intune neudržuje starší verze schématu nebo aplikace. Pokud narazíte na konflikty verzí, doporučujeme, abyste se obrátili na výrobce OEM, kde najdete další informace.
- Přiřaďte zařízení jeden profil OEMConfig. Pokud je ke stejnému zařízení přiřazeno několik profilů, může se zobrazit nekonzistentní chování. Model OEMConfig podporuje pouze jednu zásadu na zařízení.

## <a name="prerequisites"></a>Předpoklady

Pokud chcete na svých zařízeních používat OEMConfig, ujistěte se, že máte následující požadavky:

- Zařízení s Androidem Enterprise zaregistrované v Intune.
- Aplikace OEMConfig vytvořená výrobcem OEM a nahraná do Google Play. Pokud se nepoužívá Google Play, obraťte se na výrobce OEM, kde najdete další informace.
- Správce Intune má oprávnění řízení přístupu na základě role (RBAC) pro **mobilní aplikace**, **Konfigurace zařízení**a oprávnění číst v **Androidu for Work**. Tato oprávnění jsou povinná, protože profily OEMConfig používají konfigurace spravovaných aplikací ke správě konfigurací zařízení.

## <a name="prepare-the-oemconfig-app"></a>Příprava aplikace OEMConfig

Ujistěte se, že zařízení podporuje OEMConfig, do Intune se přidá správná aplikace OEMConfig a aplikace se nainstaluje do zařízení. Pro tyto informace se obraťte na výrobce OEM.

> [!TIP] 
> Aplikace OEMConfig jsou specifické pro výrobce OEM. Například aplikace Sony OEMConfig nainstalovaná na zařízení technologie Zebra nedělá cokoli.

1. Získejte aplikaci OEMConfig ze spravovaného Obchod Google Play. [Přidání spravovaných aplikací Google Play do zařízení se systémem Android Enterprise](../apps/apps-add-android-for-work.md) seznam kroků
2. Někteří výrobci OEM můžou dodávat zařízení s předem nainstalovanou aplikací OEMConfig. Pokud aplikace není předinstalována, [přidejte aplikaci do zařízení](../apps/apps-deploy.md)pomocí Intune.

## <a name="create-an-oemconfig-profile"></a>Vytvoření profilu OEMConfig

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **zařízení** > **konfiguračních profilech** > **vytvořit profil**.
3. Zadejte následující vlastnosti:

    - **Název**: Zadejte popisný název nového profilu.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: vyberte **Android Enterprise**.
    - **Typ profilu**: vyberte **OEMConfig**.

4. Vyberte **přidružená aplikace**, vyberte existující aplikaci OEMConfig, kterou jste dříve přidali > **OK**. Ujistěte se, že jste zvolili správnou aplikaci OEMConfig pro zařízení, ke kterým přiřadíte zásadu.

    Pokud nevidíte žádné uvedené aplikace, nastavte spravované Google Play a Získejte aplikace ze spravovaného Google Play Storu. [Přidání spravovaných aplikací Google Play do zařízení se systémem Android Enterprise](../apps/apps-add-android-for-work.md) seznam kroků

    > [!IMPORTANT]
    > Pokud jste přidali aplikaci OEMConfig a synchronizovaly ji do Google Play, ale není uvedená jako **přidružená aplikace**, možná budete muset kontaktovat Intune, aby se aplikace připojila. Viz [Přidání nové aplikace](#supported-oemconfig-apps) (v tomto článku).

5. V části **Konfigurovat nastavení pomocí**vyberte možnost použití **Návrháře konfigurace** nebo **editoru JSON**:

    > [!TIP]
    > Přečtěte si dokumentaci OEM a ujistěte se, že jste správně nakonfigurovali vlastnosti. Tyto vlastnosti aplikace jsou součástí výrobce OEM, nikoli Intune. Intune provede minimální ověření vlastností nebo to, co zadáte. Pokud například zadáte `abcd` pro číslo portu, profil se uloží tak, jak je, a nasadí se do vašich zařízení s hodnotami, které nakonfigurujete. Ujistěte se, že zadáváte správné informace.

    - **Návrhář konfigurace**: po výběru této možnosti se zobrazí vlastnosti dostupné v rámci schématu aplikace, které můžete nakonfigurovat.

      - Kontextové nabídky v Návrháři konfigurace označují, že jsou k dispozici další možnosti. Například místní nabídka vám může umožnit přidání, odstranění a změnu pořadí nastavení. Tyto možnosti jsou zahrnuty v výrobci OEM. Nezapomeňte si přečíst dokumentaci k aplikaci pro výrobce OEM, kde se dozvíte, jak se tyto možnosti mají použít k vytváření profilů.

      - Mnoho nastavení má výchozí hodnoty, které dodává výrobce OEM. Pokud chcete zjistit, jestli je výchozí hodnota, najeďte myší na ikonu informace vedle nastavení. Popisek zobrazuje výchozí hodnoty pro toto nastavení (Pokud je k dispozici) a další podrobnosti poskytované výrobcem OEM.

      - Kliknutím na tlačítko **Vymazat** odstraníte nastavení z profilu. Pokud nastavení není v profilu, při použití profilu se jeho hodnota v zařízení nezmění.

      - Pokud vytvoříte prázdnou (nenakonfigurovanou) sadu prostředků v Návrháři konfigurace, odstraní se při přepnutí do editoru JSON.

    - **Editor JSON**: Když vyberete tuto možnost, otevře se Editor JSON se šablonou pro úplné schéma konfigurace vložené do aplikace. V editoru Přizpůsobte šablonu pomocí hodnot pro různá nastavení. Použijete-li **Návrháře konfigurace** ke změně hodnot, Editor JSON přepíše šablonu hodnotami z návrháře konfigurace.

      - Pokud aktualizujete existující profil, Editor JSON zobrazí nastavení, které bylo naposledy uloženo s profilem.

      - Schémata OEMConfig můžou být velká a složitá. Pokud dáváte přednost aktualizaci těchto nastavení pomocí jiného editoru, vyberte tlačítko **Stáhnout šablonu JSON** . Pomocí editoru dle vašeho výběru přidejte do šablony konfigurační hodnoty. Pak zkopírujte a vložte aktualizovaný kód JSON do vlastnosti **Editor JSON** .

      - K vytvoření zálohy konfigurace můžete použít Editor JSON. Po nakonfigurování nastavení použijte tuto funkci k získání nastavení JSON s hodnotami. Zkopírujte a vložte JSON do souboru a uložte ho. Nyní máte záložní soubor.

    Všechny změny provedené v Návrháři konfigurace jsou také automaticky provedeny v editoru JSON. Podobně všechny změny provedené v editoru JSON se automaticky provedou v Návrháři konfigurace. Pokud vstup obsahuje neplatné hodnoty, nemůžete přepínat mezi návrhářem konfigurace a editorem JSON, dokud problémy neopravíte.

6. Vyberte **OK** > **Přidat** a uložte provedené změny. Zásada se vytvoří a zobrazí se v seznamu.

Nezapomeňte [profil přiřadit](device-profile-assign.md) a [monitorovat jeho stav](device-profile-monitor.md).

 > [!NOTE]
 > Přiřaďte každému zařízení jeden profil. Model OEMConfig podporuje pouze jednu zásadu na zařízení.

Až zařízení příště zkontroluje aktualizace konfigurace, nakonfigurované nastavení specifické pro výrobce OEM se použije na aplikaci OEMConfig.

> [!NOTE]
> OEMConfig Standard aktuálně neobsahuje vytváření sestav o stavu. Ve výchozím nastavení profily ukazují stav čeká na **vyřízení** .

## <a name="supported-oemconfig-apps"></a>Podporované aplikace OEMConfig

V porovnání se standardními aplikacemi aplikace OEMConfig rozšiřují oprávnění spravovaných konfigurací udělená společností Google, aby podporovala složitější schémata. Intune aktuálně podporuje tyto aplikace OEMConfig:

-----------------

| OEM | ID sady prostředků | Dokumentace OEM (je-li k dispozici) |
| --- | --- | ---|
| Samsung | com.samsung.android.knox.kpu | [Příručka pro správce modulů plug-in služby Knox](https://docs.samsungknox.com/knox-service-plugin/admin-guide/index.htm) |
| Zebra technologie | com. zebra. oemconfig. Common | [Zebra OEMConfig – přehled](http://techdocs.zebra.com/oemconfig ) |
| Datalogic | com. Datalogic. oemconfig | [Dokumentace uživatele pro Datalogic OEMConfig](https://datalogic.github.io/oemconfig/) |
| Honeywell | com. Honeywell. oemconfig |  |
| Tiskárny | JP. Kyocera. enterprisedeviceconfig |  |
| Spectralink – čárové kódy | com. Spectralink. čárový kód. Service |  |
| Spectralink – tlačítka | com. Spectralink. Buttons |  |
| Spectralink – zařízení | com. Spectralink. slnkdevicesettings  |  |
| Spectralink – protokolování | com. Spectralink. slnklogger |  |
| Spectralink - VQO | com. Spectralink. slnkvqo |  |

-----------------

Pokud aplikace OEMConfig pro vaše zařízení existuje, ale není v tabulce výše, nebo se nezobrazuje v konzole Intune, pošlete prosím e-mail `IntuneOEMConfig@microsoft.com`.

> [!NOTE]
> Aby bylo možné nakonfigurovat aplikace OEMConfig pomocí profilů OEMConfig, musí být na zprovoznění služby Intune. Jakmile je aplikace podporovaná, nemusíte od Microsoftu kontaktovat žádné informace o jeho nastavování ve vašem tenantovi. Stačí postupovat podle pokynů na této stránce.

## <a name="next-steps"></a>Další kroky

- [Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).