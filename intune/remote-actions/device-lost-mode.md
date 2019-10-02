---
title: Aktivace režimu ztráty u zařízení s iOSem pomocí Microsoft Intune – Azure | Microsoft Docs
description: Pomocí Microsoft Intune můžete zapnout nebo spustit režim ztráty a přizpůsobit zprávu, která se zobrazí na zamykací obrazovce ztraceného nebo odcizeného zařízení s iOSem. Při použití akce Režim ztráty získáte také podrobnosti o zabezpečení a ochraně osobních údajů.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/25/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ac83160e6604b7a679e03bb244e1dd5081a5fc5
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732646"
---
# <a name="enable-lost-mode-on-ios-devices-with-intune"></a>Zapnutí režimu ztráty u zařízení s iOSem pomocí Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Akce zařízení **Režim ztráty** usnadňuje aktivaci režimu ztráty u ztracených nebo odcizených zařízení s iOSem. Tento režim vám umožňuje zadat zprávu a telefonní číslo, které se zobrazuje na zamykací obrazovce zařízení. Abyste mohli režim ztráty použít, musí se jednat o zařízení s iOS ve vlastnictví firmy, které je v režimu dohledu.

## <a name="supported-platforms"></a>Podporované platformy

- iOS 9.3 nebo novější

Tato funkce není podporovaná pro: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="enable-lost-mode"></a>Zapnutí režimu ztráty

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
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
