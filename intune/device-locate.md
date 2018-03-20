---
title: "Vyhledání ztracených zařízení s iOSem pomocí Microsoft Intune – Azure | Microsoft Docs"
description: "Ztracená nebo odcizená zařízení s iOSem můžete vyhledat pomocí funkce Najít zařízení v Microsoft Intune. Tato funkce vám umožní zjistit podrobnosti o zabezpečení a ochraně osobních údajů."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4bc51ef7f9af9cc97fd4c11408a1857679aee665
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Vyhledání ztracených nebo odcizených zařízení s iOSem přes Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pokud chcete zjistit polohu ztraceného nebo odcizeného zařízení s iOSem na mapě, použijte akci **Najít zařízení**. Musí se jednat o zařízení s iOSem ve vlastnictví firmy, které je zaregistrované prostřednictvím programu registrace zařízení a je v režimu pod dohledem. Než použijete tuto akci, zkontrolujte, že je zařízení v [režimu ztráty](device-lost-mode.md).

## <a name="supported-platforms"></a>Podporované platformy

- iOS 9.3 nebo novější

Tato funkce se **nepodporuje** u následujících systémů: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="locate-a-lost-or-stolen-device"></a>Vyhledání ztraceného nebo odcizeného zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** a potom **Všechna zařízení**.
4. V seznamu zařízení, která spravujete, zvolte zařízení s iOSem, zvolte **Více** a pak zvolte vzdálenou akci **Najít zařízení**.
5. Po vyhledání zařízení se jeho poloha zobrazí v části **Najít zařízení**.
    ![Vyhledání zařízení pomocí Intune v Azure](./media/locate-device.png)

>[!NOTE]
>Pro účely ochrany osobních údajů je míra zvětšení mapy omezená.

## <a name="security-and-privacy-information-for-lost-mode-and-locate-device-actions"></a>Informace o zabezpečení a ochraně osobních údajů pro akce Režim ztráty a Najít zařízení
- Dokud tuto akci nezapnete, neodesílají se do Intune žádné informace o poloze zařízení.
- Když použijete akci Najít zařízení, údaje o poloze zařízení – zeměpisná šířka a délka – se odešlou do Intune a zobrazí se na portálu Azure Portal.
- Tady tyto údaje zůstanou uložené 24 hodin a pak se odeberou. Údaje o poloze se nedají ručně odebrat.
- Údaje o poloze jsou při uložení i při přenosu zašifrované.
- Při konfiguraci režimu ztráty můžete přizpůsobit zprávu, která se zobrazí na zamykací obrazovce. V této zprávě určené osobě, která ztracené zařízení najde, nezapomeňte uvést konkrétní podrobnosti o vrácení ztraceného zařízení.

## <a name="next-steps"></a>Další kroky

Pokud se chcete podívat na stav povolení funkce Najít zařízení, otevřete **Zařízení** a vyberte **Akce zařízení**.
