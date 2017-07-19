---
title: "Postup přiřazení aplikací do skupin"
titleSuffix: Intune on Azure
description: "Po přidání aplikace do Intune bude vhodné ji přiřadit do skupin uživatelů nebo zařízení."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 059c6d2c65c78b6a94f93c26d606abe0451edbbb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Přiřazení aplikací do skupin pomocí Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Po přidání aplikace do Intune ji můžete přiřadit k uživatelům a zařízením.

Aplikace se dají přiřadit k zařízením, ať už jsou spravované službou Intune nebo ne. Následující tabulka vám pomůže pochopit různé možnosti pro přiřazení aplikací uživatelům a zařízením:

||||
|-|-|-|-|
|&nbsp;|Zařízení zaregistrovaná v Intune|Zařízení nezaregistrovaná v Intune|
|Přiřadit uživatelům|Ano|Ano|
|Přiřadit zařízením|Ano|Ne|
|Přiřadit zabalené aplikace nebo aplikace obsahující sadu Intune SDK (kvůli zásadám ochrany aplikací)|Ano|Ano|
|Přiřadit aplikace jako K dispozici|Ano|Ano|
|Přiřadit aplikace jako Povinné|Ano|Ne|
|Odinstalovat aplikace|Ano|Ne|
|Koncoví uživatelé instalují dostupné aplikace z aplikace Portál společnosti.|Ano|Ne|
|Koncoví uživatelé instalují dostupné aplikace z webového Portálu společnosti.|Ano|Ano|

> [!NOTE]
> V současné době můžete přiřadit aplikace pro iOS a Android (firemní i koupené ve Storu) k zařízením, která nejsou zaregistrovaná v Intune.

## <a name="how-to-assign-an-app"></a>Postup přiřazení aplikace

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
1. V úloze **Mobilní aplikace** zvolte **Spravovat** > **Aplikace**.
2. V okně se seznamem aplikací klikněte na aplikaci, kterou chcete přiřadit.
3. V okně <*název aplikace*> – **přehled** zvolte **Spravovat** > **Přiřazení**.
4. Zvolte **Vybrat skupiny** a potom v okně **Vybrat skupiny** zvolte skupiny Azure AD, do kterých chcete přiřadit aplikaci.
5. Pro každou zvolenou aplikaci zvolte **typ přiřazení**:
    - **K dispozici** – Uživatelé instalují aplikaci z aplikace nebo webu Portál společnosti.
    - **Nelze použít** – Aplikace není nainstalovaná nebo se na Portálu společnosti nezobrazuje.
    - **Povinné** – Aplikace se nainstaluje na zařízení ve vybraných skupinách.
    - **Odinstalovat** – Aplikace se odinstaluje ze zařízení ve vybraných skupinách.
    - **K dispozici s registrací i bez ní** – Přiřadí tuto aplikaci do skupin uživatelů, jejichž zařízení nejsou zaregistrovaná v Intune.
6. Až to budete mít, zvolte **Uložit**.

Aplikace je teď přiřazená do skupiny, kterou jste vybrali.

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Řešení konfliktů mezi záměry aplikace

Někdy je tatáž aplikace přiřazena více skupinám, ale s různými záměry. V těchto případech si můžete dohledat výsledný záměr v níže uvedené tabulce.

||||
|-|-|-|
|Záměr skupiny 1|Záměr skupiny 2|Výsledný záměr|
|Uživatel: Povinné|Uživatel: K dispozici|Povinné a K dispozici|
|Uživatel: Povinné|Uživatel: Není k dispozici|Povinné|
|Uživatel: Povinné|Uživatel: Odinstalace|Povinné|
|Uživatel: K dispozici|Uživatel: Není k dispozici|Není k dispozici|
|Uživatel: K dispozici|Uživatel: Odinstalace|Odinstalace|
|Uživatel: Není k dispozici|Uživatel: Odinstalace|Odinstalace
|Uživatel: Povinné|Zařízení: Povinné|Existuje obojí, zpracování bránou je povinné 
|Uživatel: Povinné|Zařízení: Odinstalace|Existuje obojí, řešení bránou je povinné 
|Uživatel: K dispozici|Zařízení: Povinné|Existuje obojí, řešení bránou je povinné (Povinné a K dispozici)
|Uživatel: K dispozici|Zařízení: Odinstalace|Existuje obojí, řešení bránou je k dispozici<br>Aplikace se zobrazí na Portálu společnosti.<br>Pokud je už aplikace nainstalovaná (jako požadovaná aplikace s předchozím záměrem), pak se aplikace odinstaluje.<br>Pokud ale uživatel klikne na portálu společnosti na instalaci, aplikace se instaluje a záměr odinstalace není dodržen.|
|Uživatel: Není k dispozici|Zařízení: Povinné|Povinné|
|Uživatel: Není k dispozici|Zařízení: Odinstalace|Odinstalace|
|Uživatel: Odinstalace|Zařízení: Povinné|Existuje obojí, řešení bránou je povinné|
|Uživatel: Odinstalace|Zařízení: Odinstalace|Existuje obojí, řešení bránou prostřednictvím odinstalace|
|Zařízení: Povinné|Zařízení: Odinstalace|Povinné|
|Uživatel: Povinné a K dispozici|Uživatel: K dispozici|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Uživatel: Odinstalace|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Uživatel: Není k dispozici|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Zařízení: Povinné|Existuje obojí, Povinné a K dispozici
|Uživatel: Povinné a K dispozici|Zařízení: Není k dispozici|Povinné a K dispozici|
|Uživatel: Povinné a K dispozici|Zařízení: Odinstalace|Existuje obojí, řešení bránou je povinné Povinné + K dispozici
|Uživatel: Není k dispozici|Zařízení: Není k dispozici|Není k dispozici|
|Uživatel: K dispozici|Zařízení: Není k dispozici|K dispozici|
|Uživatel: Povinné|Zařízení: Není k dispozici|Povinné|
|Uživatel: K dispozici bez registrace|Uživatel: Povinné a K dispozici|Povinné a K dispozici
|Uživatel: K dispozici bez registrace|Uživatel: Povinné|Povinné
|Uživatel: K dispozici bez registrace|Uživatel: Není k dispozici|Není k dispozici
|Uživatel: K dispozici bez registrace|Uživatel: K dispozici|K dispozici|
|Uživatel: K dispozici bez registrace|Zařízení: Povinné|Povinné a K dispozici bez registrace|
|Uživatel: K dispozici bez registrace|Zařízení: Není k dispozici|K dispozici bez registrace|
|Uživatel: K dispozici bez registrace|Zařízení: Odinstalace|Odinstalace a K dispozici bez registrace.<br>Pokud uživatel nenainstaloval aplikaci z portálu společnosti, bude provedena odinstalace.<br>Pokud uživatel aplikaci nainstaluje z portálu společnosti, bude mít instalace prioritu před odinstalací.|

>[!NOTE]
>Pouze pro spravované aplikace pro App Store (iOS) platí, že pokud je přidáte do Intune a přiřadíte jako Povinné, vytvoří se automaticky se záměry Povinné i K dispozici.

## <a name="next-steps"></a>Další kroky

Informace, s kterými budete moct lépe sledovat přiřazování aplikací, najdete v článku [Jak sledovat přiřazení aplikací](apps-monitor.md).
