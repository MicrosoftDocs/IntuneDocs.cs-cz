---
title: Upgrade zařízení s Windows 10 nebo použití jejich režimu S v Microsoft Intune – Azure | Microsoft Docs
description: Pokud chcete zařízení s Windows 10 upgradovat na jinou edici, vytvořte v Microsoft Intune profil zařízení. Můžete upgradovat třeba z Windows 10 Professional na Windows 10 Enterprise. K aktivaci režimu S nebo přepnutí zařízení z tohoto režimu také můžete použít konfigurační profil. Najdete zde také podporované možnosti upgradu pro Windows 10 Pro, N Edition, Education, Cloud, Enterprise, Core, Holographic a Mobile.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f0e4ba42559a068ebefb453aba18060803dc36e0
ms.sourcegitcommit: f3974c810e172f345853dacd7f2ca0abc11b1a5b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/11/2018
ms.locfileid: "44389621"
---
# <a name="use-a-configuration-profile-to-upgrade-windows-10-or-switch-from-s-mode-in-intune"></a>Použití konfiguračního profilu k upgradu Windows 10 nebo k přepnutí z režimu S v Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Konfigurujte v Intune profil upgradu k automatickému upgradování zařízení, která používají edici Windows 10, na jinou edici. Podívejte se také na podporované možnosti upgradu.

## <a name="before-you-begin"></a>Před zahájením
Před upgradem zařízení na nejnovější verzi budete potřebovat:

- Platný kód Product Key k instalaci aktualizované verze Windows na všechna zařízení, na která touto zásadou cílíte (pro edice Windows 10 Desktop). Můžete využít klíče k vícenásobné aktivaci (MAK) nebo kódy serveru správy klíčů (KMS). V edicích Windows 10 Mobile a Windows 10 Holographic použijte licenční soubor Microsoftu, který obsahuje licenční údaje potřebné k instalaci aktualizované verze Windows na všechna zařízení, kterých se tato zásada týká.
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


<!-- Testing a new table on 3/5/18 

The following lists provide the supported upgrade paths for the Windows 10 edition upgrade profile. The Windows 10 edition to upgrade to is in bold followed by the list of supported editions that you can upgrade from:

**Windows 10 Education**
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 10 Cloud
- Windows 10 Enterprise
- Windows 10 Core
    
**Windows 10 Education N edition**    
- Windows 10 Pro N edition
- Windows 10 Pro Education N edition
- Windows 10 Cloud N edition
- Windows 10 Enterprise N edition
- Windows 10 Core N edition
    
**Windows 10 Enterprise**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Enterprise N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition
    
**Windows 10 Pro**
- Windows 10 Cloud
    
**Windows 10 Pro N edition**
- Windows 10 Cloud N edition
    
**Windows 10 Pro Education**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Pro Education N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition

**Windows 10 Holographic for Business**
- Windows 10 Holographic

**Windows 10 Mobile Enterprise**
- Windows 10 Mobile -->

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

## <a name="upgrade-the-edition"></a>Upgrade edice

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte **název** a **popis** profilu. Zadejte třeba `Windows 10 edition upgrade`.
4. V poli **Platforma** vyberte **Windows 10 a novější**.
5. V poli **Typ profilu** vyberte **Upgrade edice**.
6. Ve vlastnostech **Upgradu edice** zadejte tato nastavení:

   - **Edice, na kterou se má upgradovat:** Vyberte edici Windows 10, na kterou upgradujete. Zařízení, pro která zásada platí, se upgradují na vámi vybranou edici.
   - **Kód Product Key:** Zadejte kód Product Key, který jste dostali od Microsoftu. Po vytvoření zásady s kódem Product Key nepůjde kód aktualizovat. Kód je také z bezpečnostních důvodů skrytý. Pokud chcete kód Product Key změnit, zadejte ho celý znovu.
   - **Soubor s licencí**: U edice **Windows 10 Holographic for Business** nebo **Windows 10 Mobile** zvolte **Procházet** a vyberte licenční soubor, který jste dostali od Microsoftu. Tento licenční soubor obsahuje licenční údaje o edicích, na které upgradujete cílová zařízení.

7. Výběrem **OK** uložte změny. Volbou **Vytvořit** vytvořte profil.

## <a name="switch-out-of-s-mode"></a>Přepnutí z režimu S

[Režim S systému Windows 10](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) byl navržen kvůli zabezpečení a výkonu. Pokud máte na zařízeních spuštěné jenom aplikace z Microsoft Storu, můžete režim S použít k zabezpečení zařízení. Pokud na zařízeních potřebujete aplikace, které nejsou dostupné v Microsoft Storu, přepněte z režimu S. Přepnutí z režimu S se nedá vrátit. Jakmile se přepnete z režimu S, nemůžete se do tohoto režimu Windows 10 vrátit.

Následující postup slouží k vytvoření profilu, který na zařízeních s Windows 10 (1809 nebo novější) řídí režim S.

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte **název** a **popis** profilu. Zadejte třeba `Windows 10 switch off S mode`.
4. V poli **Platforma** vyberte **Windows 10 a novější**.
5. V poli **Typ profilu** vyberte **Upgrade edice**.
6. Vyberte **Přepínač režimů (jen Windows Insider)** a nastavte vlastnost **Přepnout z režimu S**. Možnosti:

    - **Žádná konfigurace:** Zařízení v režimu S zůstane v tomto režimu. Koncový uživatel může zařízení přepnout z režimu S.
    - **Zůstat v režimu S:** Zakáže koncovému uživateli přepnutí zařízení z režimu S.
    - **Přepínač:** Přepne zařízení z režimu S.

7. Výběrem **OK** uložte změny. Volbou **Vytvořit** vytvořte profil.

Profil se vytvoří a zobrazí se v seznamu profilů.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](device-profile-assign.md) svým skupinám.

>[!NOTE]
>Pokud později přiřazenou zásadu odeberete, verze Windows, která je v zařízení, se nevrátí zpět, ale bude dál normálně fungovat.
