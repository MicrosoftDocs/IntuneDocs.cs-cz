---
title: Použít OEMConfig na zařízeních s Androidem Enterprise v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Pomocí Microsoft Intune spravujete a používáte zařízení s Androidem Enterprise v OEMConfig. Zobrazit všechny kroky, včetně přehledu, naleznete v tématu požadavky, v Intune vytvořit profil konfigurace a zobrazit seznam podporovaných aplikací OEMConfig.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/17/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 022bbcf98a5e00888f33e22941515ca03c5f6995
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59901768"
---
# <a name="use-and-manage-android-enterprise-devices-with-oemconfig-in-microsoft-intune"></a>Použití a správa zařízení s Androidem Enterprise v OEMConfig v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

V Microsoft Intune vám pomůže OEMConfig přidat, vytvořit a upravit nastavení specifické pro výrobce OEM pro zařízení s Androidem Enterprise. OEMConfig se obvykle používá ke konfiguraci nastavení, které nejsou součástí Intune. Jiný výrobce OEM zahrnují různá nastavení. Takže dostupná nastavení závisí na výrobce OEM zahrnuje ve své aplikaci OEMConfig.

Tato funkce platí pro:  

- Android Enterprise

Tento článek popisuje OEMConfig, co to dělá, obsahuje seznam předpokladů, ukazuje, jak vytvořit konfigurační profil a uvádí podporované OEMConfig aplikací v Intune.

## <a name="overview"></a>Přehled

Zásady OEMConfig jsou speciální typ zásad konfigurace zařízení, které jsou velmi podobné [zásady Konfigurace aplikací](app-configuration-policies-overview.md). OEMConfig je standard definovaný podle [AppConfig komunity](https://www.appconfig.org/android-oemconfig/) (otevře jiný web), který umožňuje výrobce OEM (original equipment manufacturer) a EMMs (enterprise mobility management) k vývoji a podpoře funkce specifické pro výrobce OEM v standardizovaný způsob. V minulosti EMMs, jako je například Intune, ruční vytvoření podpora pro funkce specifické pro výrobce OEM po už zavedené výrobcem OEM. Tento přístup vede k duplicitní úsilí a pomalé přijetí.

Výrobce OEM OEMConfig, vytvoří schéma definující funkce správy specifické pro výrobce OEM. Výrobce OEM vloží schéma do aplikace a pak vloží tuto aplikaci na webu Google Play. EMM přečte schéma z aplikace a zpřístupňuje schématu v konzole pro správu EMM. Konzole umožňuje správcům Intune nakonfigurovat nastavení ve schématu.

Když OEMConfig aplikace nainstaluje na zařízení, můžete nastavení nakonfigurovaná v konzole pro správu EMM ke správě zařízení. Nastavení v zařízení provádějí OEMConfig aplikací, místo agenta MDM vytvořených EMM.

Pokud výrobce OEM přidá a zlepšuje funkce správy, výrobce OEM rovněž aktualizuje aplikaci na webu Google Play. Jako správce získat těchto nových funkcí a aktualizací (včetně oprav) bez čekání na EMMs. Chcete-li zahrnout tyto aktualizace.

> [!TIP]
> OEMConfig můžete použít pouze se zařízeními, která tuto funkci podporovat a mít odpovídající OEMConfig aplikace. Konkrétní podrobnosti naleznete vašeho OEM dodavatele.

## <a name="before-you-begin"></a>Před zahájením

Při použití OEMConfig, mějte na paměti následující informace:

- Intune poskytuje schéma OEMConfig aplikace, můžete ho nakonfigurovat. Intune nepodporuje ověřování nebo změně schématu poskytovaném aplikací. Takže pokud schéma je nesprávný nebo obsahuje nesprávná data, pak tato data stále odešlou do zařízení. Pokud narazíte na potíže, které mohou být ve schématu, požádejte o pokyny výrobce OEM.
- Intune nepodporuje ovlivnit nebo řídit obsah schématu aplikací. Například Intune nemá žádné kontrolu nad řetězce, jazyka, akce povolené a tak dále. Doporučujeme vám, podrobnosti a doporučené postupy pro správu zařízení s OEMConfig kontaktovat výrobce OEM.
- Kdykoli můžete výrobci OEM aktualizovat jejich podporované funkce a schémata a nahrát novou aplikaci na web Google Play. Intune synchronizuje vždy nejnovější verzi aplikace OEMConfig na webu Google Play. Intune nepodporuje zachovat starší verze schématu nebo aplikace. Pokud narazíte na konflikty verzí, doporučujeme kontaktovat výrobce OEM pro další informace.
- By měl pouze jeden OEMConfig profil přiřadíte k zařízení. Pokud více profilů přiřazených do stejného zařízení, může se zobrazit nekonzistentní chování. OEMConfig model podporuje jenom jednu zásadu na zařízení.

## <a name="prerequisites"></a>Požadavky

Použití OEMConfig v zařízeních, ujistěte se, že máte následující požadavky:

- Zaregistrovaná zařízení s Androidem Enterprise v Intune.
- OEMConfig aplikace sestavena výrobce OEM a nahrána do Google Play. Pokud není na webu Google Play, obraťte se na výrobce OEM pro další informace.
- Správce Intune má oprávnění řízení přístupu na základě rolí pro **mobilní aplikace** a **konfigurace zařízení**. Důvodem je, že zkontrolujte profily OEMConfig použití konfigurací spravovaných aplikací ke správě konfigurací zařízení.

## <a name="prepare-the-oemconfig-app"></a>Příprava aplikace OEMConfig

Ujistěte se, že zařízení podporuje OEMConfig přidaný správné OEMConfig aplikace do Intune a nainstalované aplikace v zařízení. Tyto informace získáte od výrobce OEM.

> [!TIP] 
> OEMConfig aplikace jsou specifické pro výrobce OEM. Například Sony OEMConfig aplikaci nainstalovanou na zařízení s technologií Zebra nic nedělá.

1. Stáhněte si aplikaci OEMConfig ze spravované Store Google Play. [Přidání aplikací spravovaný obchod Google Play na zařízení s Androidem enterprise](apps-add-android-for-work.md) jsou uvedené kroky.
2. Někteří výrobci OEM může dodávat zařízení s předinstalovanými OEMConfig aplikací. Pokud není předinstalované aplikace, použijte Intune k [přidat a nasadit aplikace do zařízení](apps-deploy.md).

## <a name="create-an-oemconfig-profile"></a>Vytvoření profilu OEMConfig

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

    - **Název**: Zadejte popisný název pro nový profil.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Vyberte **Androidu enterprise**.
    - **Typ profilu**: Vyberte **OEMConfig**.

4. Vyberte **přidružené aplikace**a vyberte stávající aplikaci OEMConfig jste přidali dříve. Nezapomeňte vybrat správnou OEMConfig aplikací pro zařízení, která přiřazujete zásady tak, aby.

    Pokud nevidíte všechny aplikace, uvedená, nastavit spravovaný obchod Google Play a získat aplikace z obchodu spravovaný obchod Google Play. [Přidání aplikací spravovaný obchod Google Play na zařízení s Androidem enterprise](apps-add-android-for-work.md) jsou uvedené kroky.

    > [!IMPORTANT]
    > Pokud Přidání OEMConfig aplikace a synchronizované do Google Play, ale není uvedený jako **přidružené aplikace**, možná budete muset kontaktovat Intune k připojení aplikace. Zobrazit [přidává se nová aplikace](#supported-oemconfig-apps) (v tomto článku).

5. Vyberte **konfigurace** kartu.

    Pomocí šablony pro schéma konfigurace, které jsou součástí aplikace se otevře JSON editor. V editoru přizpůsobte šablonu s hodnotami pro jinou konfiguraci nastavení. 
    
    Protože schémata OEMConfig mohou být velké a složité, můžete použít **stáhnout šablonu JSON** tlačítko získat šablonu do souboru. Nakonfigurujte tento soubor šablony v editoru podle vašeho výběru a pak zkopírovat obsah do konzoly pro správu Intune.

6. Vyberte **OK** > **přidat** uložte provedené změny. Zásada se vytvoří a zobrazí v seznamu.

Nezapomeňte [přiřadit profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).
    
 > [!NOTE]
 > Přiřadíte každé zařízení v jednom profilu. OEMConfig model podporuje jenom jedny zásady podle zařízení.

Nastavení specifické pro výrobce OEM, který jste nakonfigurovali při příštím zařízení kontroluje aktualizace konfigurace, použijí se OEMConfig aplikace.

## <a name="supported-oemconfig-apps"></a>Podporované OEMConfig aplikace

Ve srovnání s standardní aplikace, aplikace OEMConfig rozbalte spravované konfigurace oprávněních udělených systémem Google pro podporu složitější schémata. Intune aktuálně podporuje následující OEMConfig aplikace:

-----------------

| OEM | ID sady prostředků |
| --- | --- |
| Samsung | com.samsung.android.knox.kpu |

-----------------

Chcete-li požádat o novou aplikaci OEMConfig být zprovozněná, e-mailu `IntuneOEMConfig@microsoft.com`.

> [!NOTE]
> Aplikace OEMConfig musí zprovozněná v Intune předtím, než se dají konfigurovat pomocí profilů OEMConfig.

## <a name="next-steps"></a>Další postup

- [Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
