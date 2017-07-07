---
title: "Aktivace režimu ztráty v iOS přes Intune"
titleSuffix: Intune on Azure
description: "Informace o tom, jak u ztracených nebo odcizených zařízení s iOSem aktivovat režim ztráty přes Intune"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a34d008ae76355578c6f24a932c9e1e501d5b46b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="activate-lost-mode-on-ios-devices"></a>Aktivace režimu ztráty u zařízení s iOSem


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce zařízení **Režim ztráty** usnadňuje aktivaci režimu ztráty u ztracených nebo odcizených zařízení s iOSem. Tento režim umožňuje zadat zprávu a telefonní číslo, které se zobrazí na zamykací obrazovce zařízení.

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení s iOSem a potom zvolte vzdálenou akci **Režim ztráty**.
6. V okně **Režim ztráty** zapněte režim ztráty, zadejte zprávu, která se má zobrazit, a volitelně také kontaktní telefonní číslo.
7. Klikněte na **OK**.

Když zapnete režim ztráty, zablokujete veškeré možnosti použití zařízení. Koncový uživatel nebude mít k zařízení přístup, dokud režim ztráty nevypnete. Když je režim ztráty zapnutý, můžete pomocí akce **Najít zařízení** zjistit, kde se zařízení nachází.
Pokud chcete použít režim ztráty, musí se jednat o zařízení s iOSem ve vlastnictví firmy, které je zaregistrované prostřednictvím programu DEP a je v režimu dohledu.

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení a skupiny** zvolíte **Akce zařízení**.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informace o zabezpečení a ochraně osobních údajů pro akce Režim ztráty a Najít zařízení
- Do Intune se neodesílají žádné informace o poloze zařízení, dokud tuto akci nezapnete.
- Když použijete akci Najít zařízení, údaje o poloze zařízení – zeměpisná šířka a délka – se odešlou do Intune a zobrazí se na portálu Azure Portal.
- Tady tyto údaje zůstanou uložené 24 hodin a pak se odeberou. Údaje o poloze se nedají ručně odebrat.
- Údaje o poloze jsou při uložení i při přenosu zašifrované.
- Doporučujeme, abyste při konfiguraci režimu ztráty zadali do zprávy, která se má zobrazit na zamykací obrazovce, informace, které případnému nálezci usnadní vrácení zařízení.

