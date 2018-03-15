---
title: "Vyhledání ztracených zařízení s iOSem přes Intune"
titlesuffix: Azure portal
description: "Informace o tom, jak vyhledat ztracená nebo odcizená zařízení s iOSem přes Intune"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 864d528091de7a6113485347304b0dc254af2c7d
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Vyhledání ztracených nebo odcizených zařízení s iOSem přes Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce **Najít zařízení** umožňuje zobrazit polohu ztraceného nebo odcizeného zařízení s iOSem na mapě. Musí se jednat o zařízení s iOSem ve vlastnictví firmy, které je zaregistrované prostřednictvím programu DEP a je v režimu dohledu. Než tuto akci použijete, musíte pro zařízení zapnout [režim ztráty](device-lost-mode.md).

## <a name="supported-platforms"></a>Podporované platformy

- Windows – nepodporováno
- Windows Phone – nepodporováno
- iOS – podporováno v iOS 9.3 a novějších verzích (v režimu ztráty), u zařízení pod dohledem a ve vlastnictví firmy
- macOS – nepodporováno
- Android – nepodporováno

## <a name="how-to-locate-a-lost-or-stolen-device"></a>Vyhledání ztraceného nebo odcizeného zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení s iOSem, zvolte **Více** a pak zvolte vzdálenou akci **Najít zařízení**.
6. Poloha nalezeného zařízení se zobrazí v okně **Najít zařízení**.
    ![Okno Najít zařízení](./media/locate-device.png)

>[!NOTE]
>Pro účely ochrany osobních údajů je míra zvětšení mapy omezená.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informace o zabezpečení a ochraně osobních údajů pro akce Režim ztráty a Najít zařízení
- Do Intune se neodesílají žádné informace o poloze zařízení, dokud tuto akci nezapnete.
- Když použijete akci Najít zařízení, údaje o poloze zařízení – zeměpisná šířka a délka – se odešlou do Intune a zobrazí se na portálu Azure Portal.
- Tady tyto údaje zůstanou uložené 24 hodin a pak se odeberou. Údaje o poloze se nedají ručně odebrat.
- Údaje o poloze jsou při uložení i při přenosu zašifrované.
- Doporučujeme, abyste při konfiguraci režimu ztráty zadali do zprávy, která se má zobrazit na zamykací obrazovce, informace, které případnému nálezci usnadní vrácení zařízení.


## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení** zvolíte **Akce zařízení**.