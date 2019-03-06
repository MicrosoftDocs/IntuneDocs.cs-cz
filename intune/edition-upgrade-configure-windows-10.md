---
title: Upgrade nebo použít S režimu na zařízeních s Windows 10 – Microsoft Intune – Azure | Dokumentace Microsoftu
description: Pomocí Microsoft Intune pro upgrade zařízení s Windows 10 na jinou edici nebo povolit režim S. Správci slouží k upgradu na Windows 10 Enterprise, Windows 10 Professional a povolit nebo přepněte z režimu S profil konfigurace zařízení. V tématu podporované cesty upgradu pro Windows 10 Pro, N Edition, Education, Cloud, Enterprise, Core, Holographic a Mobile.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5b206cfca048416b1e859e9230f037e1158d46ec
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57388705"
---
# <a name="upgrade-windows-10-editions-or-enable-s-mode-on-devices-using-microsoft-intune"></a>Upgrade edice Windows 10 nebo povolit S režimu na zařízeních pomocí Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako součást řešení správy mobilních zařízení můžete upgradovat zařízení s Windows 10. Například chcete provést upgrade zařízení s Windows 10 Professional pro Windows 10 Enterprise. Nebo, které chcete povolit mobilní zařízení S tak zařízení spouštět pouze aplikace z Microsoft Store.

[Režim S systému Windows 10](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) byl navržen kvůli zabezpečení a výkonu. Pokud máte na zařízeních spuštěné jenom aplikace z Microsoft Storu, můžete režim S použít k zabezpečení zařízení. Pokud vaše zařízení používat aplikace, které nejsou dostupné v Microsoft Store, pak přepnutí z režimu S. Přepnutí z režimu S se nedá vrátit. Jakmile se přepnete z režimu S, nemůžete se do tohoto režimu Windows 10 vrátit.

Tato funkce platí pro:

- Windows 10 a novější
- Windows 10 1809 nebo novější S režimu
- Windows Holographic for Business

Tyto funkce jsou dostupné v Intune a jsou konfigurovatelné správcem. Intune používá "konfiguračních profily" vytvořit a přizpůsobit nastavení pro potřeby vaší organizace. Po přidání těchto funkcí v profilu, můžete pak push, nebo nasadit profil pro zařízení s Windows 10 ve vaší organizaci. Při nasazení profilu Intune automaticky upgraduje zařízení nebo umožňuje režim S.

Tento článek obsahuje seznam podporovaných způsobech upgradu a ukazuje, jak vytvořit profil konfigurace zařízení. Můžete také zobrazit všechny dostupné upgradu a nastavení režimu S [Windows 10](edition-upgrade-windows-settings.md).

> [!NOTE]
> Pokud později přiřazení zásady odeberete, se nevrátí verze Windows na zařízení. Zařízení dál normálně fungovat.

## <a name="prerequisites"></a>Požadavky

Před upgradováním zařízení, ujistěte se, že jsou splněné následující požadavky:

- Platný kód Product Key k instalaci aktualizované verze Windows na všechna zařízení, na která touto zásadou cílíte (pro edice Windows 10 Desktop). Můžete využít klíče k vícenásobné aktivaci (MAK) nebo kódy serveru správy klíčů (KMS).
- Pro edice Windows 10 Mobile a Windows 10 Holographic můžete použít licenční soubor od Microsoftu. Licenční soubor obsahuje licenční informace pro instalaci aktualizované verze na všech zařízeních, na která cílíte touto zásadou.
- Zařízení s Windows 10, kterým zásady přiřazujete, jsou zaregistrovaná v Microsoft Intune. Zásadu upgradu edice nemůžete použít u počítačů s klientským softwarem Intune pro počítače.

## <a name="supported-upgrade-paths"></a>Podporované možnosti upgradu

V následující tabulce jsou podporované cesty upgradu pro profil upgradu edice Windows 10.

| Upgrade z | Upgrade na |
|---|---|
| Windows 10 Pro | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education |
| Edice Windows 10 Pro N | Edice Windows 10 Education N <br/>Edice Windows 10 Enterprise N <br/>Edice Windows 10 Pro Education N | 
| Windows 10 Pro Education | Windows 10 Education | 
| Edice Windows 10 Pro Education N | Edice Windows 10 Education N |
| Windows 10 Cloud | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro <br/>Windows 10 Pro Education | 
| Edice Windows 10 Cloud N | Edice Windows 10 Education N <br/>Edice Windows 10 Enterprise N <br/>Edice Windows 10 Pro N <br/>Edice Windows 10 Pro Education N | 
| Windows 10 Enterprise | Windows 10 Education | 
| Edice Windows 10 Enterprise N | Edice Windows 10 Education N | 
| Windows 10 Core | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education | 
| Edice Windows 10 Core N | Edice Windows 10 Education N <br/>Edice Windows 10 Enterprise N <br/>Edice Windows 10 Pro Education N | 
| Windows 10 Holographic | Windows 10 Holographic for Business |
| Windows 10 Mobile | Windows 10 Mobile Enterprise |

<!--The following table provides information about the supported upgrade paths for Windows 10 editions in this policy:

![supported](./media/check_grn.png)  (X) = not supported    
![unsupported](./media/x_blk.png)    (green checkmark) = supported    

|Upgrade from edition\Upgrade to edition|Education|Education N|Pro Education|Pro Education N|Enterprise|Enterprise N|Professional|Professional N|Mobile Enterprise|Holographic for Business|
|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
|Pro|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)   |![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Mobile|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|
|Holographic|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png) -->

## <a name="create-the-profile"></a>Vytvoření profilu

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

    - **Název**: Zadejte popisný název pro nový profil. Zadejte například vypadat `Windows 10 edition upgrade profile` nebo `Windows 10 switch off S mode`.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Vyberte platformu:  

        - **Windows 10 a novější**

    - **Typ profilu**: Vyberte **upgrade edice**.
    - **Nastavení**: Zadejte nastavení, které chcete konfigurovat. Seznam všech nastavení, a co dělají naleznete v tématu:

        - [Upgrade Windows 10 a režim S](edition-upgrade-windows-settings.md)
        - [Windows Holographic for Business](holographic-upgrade.md)

4. Vyberte **OK** > **Vytvořit** a změny uložte. 

Profil se vytvoří a zobrazí v seznamu. Nezapomeňte [přiřadit profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).

## <a name="next-steps"></a>Další postup

Po vytvoření profilu je připraven k přiřazení. Dále [přiřadit profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).

Zobrazení upgradu a nastavení režimu S [Windows 10](edition-upgrade-windows-settings.md) a [Windows Holographic for Business](holographic-upgrade.md) zařízení.
