---
title: Aktivace režimu ztráty u zařízení s iOSem pomocí Microsoft Intune – Azure | Microsoft Docs
description: Pomocí Microsoft Intune můžete zapnout nebo spustit režim ztráty a přizpůsobit zprávu, která se zobrazí na zamykací obrazovce ztraceného nebo odcizeného zařízení s iOSem. Při použití akce Režim ztráty získáte také podrobnosti o zabezpečení a ochraně osobních údajů.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2da88a6146080014b79fbdc1b8c553eae5705195
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/20/2018
---
# <a name="enable-lost-mode-on-ios-devices-with-intune"></a>Zapnutí režimu ztráty u zařízení s iOSem pomocí Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce zařízení **Režim ztráty** usnadňuje aktivaci režimu ztráty u ztracených nebo odcizených zařízení s iOSem. Tento režim vám umožňuje zadat zprávu a telefonní číslo, které se zobrazuje na zamykací obrazovce zařízení. Abyste mohli režim ztráty použít, musí se jednat o zařízení s iOS ve vlastnictví firmy, které je v režimu dohledu.

## <a name="supported-platforms"></a>Podporované platformy

- iOS 9.3 nebo novější

Tato funkce není podporovaná pro: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="enable-lost-mode"></a>Zapnutí režimu ztráty

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** a potom **Všechna zařízení**.
4. Ze seznamu zařízení, která spravujete, vyberte zařízení s iOSem a vyberte **...Další**. Pak zvolte vzdálenou akci **Režim ztráty**.
5. V **režimu ztráty** zapněte tuto funkci. Pak zadejte zprávu, která se má zobrazovat, a kontaktní telefonní číslo.
6. Výběrem **OK** uložte změny.

Když zapnete režim ztráty, zablokujete veškeré možnosti použití zařízení. Koncový uživatel nebude mít k zařízení přístup, dokud režim ztráty nevypnete. Když je režim ztráty zapnutý, můžete pomocí akce [Najít zařízení](device-locate.md) zjistit, kde se zařízení nachází.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informace o zabezpečení a ochraně osobních údajů pro akce Režim ztráty a Najít zařízení
- Dokud tuto akci nezapnete, neodesílají se do Intune žádné informace o poloze zařízení.
- Když použijete akci Najít zařízení, údaje o poloze zařízení – zeměpisná šířka a délka – se odešlou do Intune a zobrazí se na portálu Azure Portal.
- Tady tyto údaje zůstanou uložené 24 hodin a pak se odeberou. Údaje o poloze se nedají ručně odebrat.
- Údaje o poloze jsou při uložení i při přenosu zašifrované.
- Ve zprávě, která se zobrazí na zamykací obrazovce, nezapomeňte uvést konkrétní podrobnosti o vrácení ztraceného zařízení.

## <a name="next-steps"></a>Další kroky

Pokud se chcete podívat na stav zapnutí režimu ztráty, otevřete **Zařízení** a vyberte **Akce zařízení**.