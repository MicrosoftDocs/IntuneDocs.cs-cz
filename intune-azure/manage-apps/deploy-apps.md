---
title: "Postup přiřazení aplikací do skupin | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Po přidání aplikace do Intune bude vhodné ji přiřadit do skupin uživatelů nebo zařízení."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 638ad0d87c19c9e40e96b42d18e5c4342f40a156
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Přiřazení aplikací do skupin pomocí Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Po přidání aplikace do Intune ji budete chtít dostat k uživatelům a do zařízení. To uděláte jejím přiřazením.

Aplikace se dají přiřadit k zařízením, ať už jsou spravované službou Intune nebo ne. Následující tabulka vám pomůže pochopit různé možnosti pro přiřazení aplikací uživatelům a zařízením:

||||
|-|-|-|-|
|&nbsp;|Zařízení zaregistrovaná v Intune|Zařízení nezaregistrovaná v Intune|
|Přiřadit uživatelům|Ano|Ano|
|Přiřadit zařízením|Ano|Ne|
|Přiřadit zabalené aplikace nebo aplikace obsahující sadu Intune SDK (kvůli zásadám ochrany aplikací)|Ano|Ano|
|Přiřadit aplikace jako dostupné|Ano|Ano|
|Přiřadit aplikace jako vyžadované|Ano|Ne|
|Odinstalovat aplikace|Ano|Ano|
|Koncoví uživatelé instalují dostupné aplikace z aplikace Portál společnosti.|Ano|Ne|
|Koncoví uživatelé instalují dostupné aplikace z webového Portálu společnosti.|Ano|Ano|

> [!NOTE]
> V současné době můžete přiřadit aplikace pro iOS a Android (firemní i koupené ve Storu) k zařízením, která nejsou zaregistrovaná v Intune.

## <a name="how-to-assign-an-app"></a>Postup přiřazení aplikace

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Spravovat aplikace**.
1. V úloze **Spravovat aplikace** zvolte **Spravovat** > **Aplikace**.
2. V okně se seznamem aplikací klikněte na aplikaci, kterou chcete přiřadit.
3. V okně <*název aplikace*> – **přehled** zvolte **Spravovat** > **Přiřazení**.
4. Zvolte **Vybrat skupiny** a potom v okně **Vybrat skupiny** zvolte skupiny Azure AD, do kterých chcete přiřadit aplikaci.
5. Pro každou zvolenou aplikaci zvolte **typ přiřazení**:
    - **K dispozici** – Uživatelé instalují aplikaci z aplikace nebo webu Portál společnosti.
    - **Neužívá se** – Aplikace není nainstalovaná nebo se na Portálu společnosti nezobrazuje.
    - **Povinné** – Aplikace se nainstaluje na zařízení ve vybraných skupinách.
    - **Odinstalovat** – Aplikace se odinstaluje ze zařízení ve vybraných skupinách.
    - **K dispozici s registrací i bez ní** – Přiřadí tuto aplikaci do skupin uživatelů, jejichž zařízení nejsou zaregistrovaná v Intune. Nápovědu najdete v tabulce výše.
6. Až to budete mít, zvolte **Uložit**.

Aplikace je teď přiřazená do skupiny, kterou jste zvolili.

Informace, s kterými budete moct lépe sledovat přiřazování aplikací, najdete v článku [Jak sledovat přiřazení aplikací](monitor-apps.md).

