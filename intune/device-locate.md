---
title: Vyhledání ztracených zařízení s iOSem pomocí Microsoft Intune – Azure | Microsoft Docs
description: Vyhledejte ztracené nebo odcizené zařízení s iOSem pomocí funkce Najít zařízení v Microsoft Intune. Získejte podrobnosti o zabezpečení a ochraně osobních údajů při používání akce Najít zařízení.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: da8bb19db8c2da2d5854c3f991ccce4d124d594c
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Vyhledání ztracených nebo odcizených zařízení s iOSem přes Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pokud chcete zjistit polohu ztraceného nebo odcizeného zařízení s iOSem na mapě, použijte akci **Najít zařízení**. Musí se jednat o zařízení s iOSem ve vlastnictví firmy, které je zaregistrované prostřednictvím programu registrace zařízení a je v režimu pod dohledem. Než použijete tuto akci, zkontrolujte, že je zařízení v [režimu ztráty](device-lost-mode.md).

## <a name="supported-platforms"></a>Podporované platformy

- iOS 9.3 nebo novější

Tato funkce není podporovaná pro tyto systémy: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="locate-a-lost-or-stolen-device"></a>Vyhledání ztraceného nebo odcizeného zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** a potom **Všechna zařízení**.
4. Ze seznamu zařízení, která spravujete, vyberte zařízení s iOSem a vyberte **...Další**. Pak zvolte vzdálenou akci **Najít zařízení**.
5. Po nalezení zařízení se jeho poloha zobrazí v části **Najít zařízení**.
    ![Snímek obrazovky z funkcí Najít zařízení pomocí Intune v Azure](./media/locate-device.png)

>[!NOTE]
>Z důvodu ochrany osobních údajů je míra zvětšení mapy omezená.

## <a name="security-and-privacy-information-for-lost-mode-and-locate-device-actions"></a>Informace o zabezpečení a ochraně osobních údajů pro akce Režim ztráty a Najít zařízení
- Dokud tuto akci nezapnete, neodesílají se do Intune žádné informace o poloze zařízení.
- Když použijete akci Najít zařízení, údaje o poloze zařízení – zeměpisná šířka a délka – se odešlou do Intune a zobrazí se na portálu Azure Portal.
- Tady tyto údaje zůstanou uložené 24 hodin a pak se odeberou. Údaje o poloze se nedají ručně odebrat.
- Údaje o poloze jsou při uložení i při přenosu zašifrované.
- Při konfiguraci režimu ztráty můžete přizpůsobit zprávu, která se zobrazí na zamykací obrazovce. V této zprávě určené osobě, která ztracené zařízení najde, nezapomeňte uvést konkrétní podrobnosti o vrácení ztraceného zařízení.

## <a name="next-steps"></a>Další kroky

Pokud se chcete podívat na stav povolení funkce Najít zařízení, otevřete **Zařízení** a vyberte **Akce zařízení**.
