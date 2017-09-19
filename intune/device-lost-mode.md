---
title: "Aktivace režimu ztráty v iOS přes Intune"
titlesuffix: Azure portal
description: "Informace o tom, jak u ztracených nebo odcizených zařízení s iOSem aktivovat režim ztráty přes Intune"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5f16bd212c7a23d847da0929933fbd4b497099d0
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2017
---
# <a name="activate-lost-mode-on-ios-devices"></a>Aktivace režimu ztráty u zařízení s iOSem


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce zařízení **Režim ztráty** usnadňuje aktivaci režimu ztráty u ztracených nebo odcizených zařízení s iOSem. Tento režim vám umožňuje zadat zprávu a telefonní číslo, které se zobrazuje na zamykací obrazovce zařízení.

## <a name="supported-platforms"></a>Podporované platformy

- Windows – nepodporováno
- Windows Phone – nepodporováno
- iOS – podporováno v iOS 9.3 a novější verzi, pod dohledem a ve vlastnictví firmy
- macOS – nepodporováno
- Android – nepodporováno

## <a name="how-to-activate-lost-mode"></a>Jak aktivovat režim ztráty

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení s iOSem a potom zvolte vzdálenou akci **Režim ztráty**.
6. V okně **Režim ztráty** povolte režim ztráty. Pak zadejte zprávu, která se má zobrazovat, a volitelně kontaktní telefonní číslo.
7. Klikněte na **OK**.

Když zapnete režim ztráty, zablokujete veškeré možnosti použití zařízení. Koncový uživatel nebude mít k zařízení přístup, dokud režim ztráty nevypnete. Když je režim ztráty zapnutý, můžete pomocí akce **Najít zařízení** zjistit, kde se zařízení nachází.
Abyste mohli režim ztráty použít, musí se jednat o zařízení s iOS ve vlastnictví firmy, které je v režimu dohledu.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informace o zabezpečení a ochraně osobních údajů pro akce Režim ztráty a Najít zařízení
- Dokud tuto akci nezapnete, neodesílají se do Intune žádné informace o poloze zařízení.
- Když použijete akci Najít zařízení, údaje o poloze zařízení – zeměpisná šířka a délka – se odešlou do Intune a zobrazí se na portálu Azure Portal.
- Tady tyto údaje zůstanou uložené 24 hodin a pak se odeberou. Údaje o poloze se nedají ručně odebrat.
- Údaje o poloze jsou při uložení i při přenosu zašifrované.
- Doporučujeme, abyste do zprávy, která se má zobrazit na zamykací obrazovce, zadali informace, které případnému nálezci usnadní vrácení zařízení.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení a skupiny** zvolíte **Akce zařízení**.

