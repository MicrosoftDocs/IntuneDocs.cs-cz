---
title: Zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune
titleSuffix: ''
description: Zjistěte, jak pomocí Microsoft Intune zahrnout nebo vyloučit přiřazení aplikací.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f073c8ad7a8e087a791ee756683011fac6947162
ms.sourcegitcommit: 23e9c48348a6eba494d072a2665b7481e5b5c84e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2019
ms.locfileid: "74547969"
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune

Přiřazením skupin uživatelů, které se mají zahrnout nebo vyloučit, můžete v Intune určit, kdo má přístup k aplikaci. Než skupiny k aplikaci přiřadíte, musíte nastavit typ přiřazení aplikace. Typ přiřazení nastaví aplikaci jako dostupnou, požadovanou nebo ji odinstaluje. 

Abyste nastavili dostupnost aplikace, zahrnete a vyloučíte její přiřazení ke skupině uživatelů nebo zařízení pomocí kombinace skupinových přiřazení pro zahrnutí a vyloučení. Tato možnost může být užitečná, když aplikaci zpřístupníte zahrnutím velké skupiny a následně upřesníte vybrané uživatele vyloučením menší skupiny. Menší skupina může být testovací skupina nebo skupinu vedoucích pracovníků. 

Osvědčeným postupem je vytvářet a přiřazovat aplikace konkrétně pro vaše skupiny uživatelů a samostatně pro skupiny zařízení. Další informace o skupinách najdete v tématu [Přidání skupin pro uspořádání uživatelů a zařízení](~/fundamentals/groups-add.md).  

Existují důležité scénáře při zahrnutí nebo vyloučení přiřazení aplikací:

- Vyloučení má přednost před zahrnutím do následujících scénářů stejného typu skupiny:
    - Zahrnutí skupin uživatelů a vyloučení skupin uživatelů při přiřazování aplikací
    - Zahrnutí skupin zařízení a vyloučení skupiny zařízení při přiřazování aplikací

    Pokud například přiřadíte skupinu zařízení skupině **uživatelů všichni firemní uživatelé** , ale vyloučíte členy ve skupině uživatelů **správce vyšších zaměstnanců** , **Všichni firemní uživatelé** s výjimkou **pracovníků hlavní správy** získají přiřazení, protože obě skupiny jsou skupiny uživatelů.
- Intune nevyhodnocuje vztahy mezi uživateli a zařízeními. Pokud přiřadíte aplikace do smíšených skupin, výsledky nemusí být to, co chcete, nebo očekávat.

    Například pokud přiřadíte skupinu zařízení skupině uživatelů **Všichni uživatelé** , ale vyloučíte skupinu zařízení **všechna osobní zařízení** . V tomto kombinovaném přiřazení aplikace skupiny získají **Všichni uživatelé** aplikaci. Vyloučení nelze použít.

V důsledku toho se nedoporučuje přiřazovat aplikace do smíšených skupin.

> [!NOTE]
> Při nastavování přiřazení skupiny pro aplikaci se přestal používat typ **Neužívá se** a nahradila ho funkce vyloučení skupiny. 
>
> V Intune máte v konzole k dispozici předem vytvořené skupiny **Všichni uživatelé** a **Všechna zařízení**. Skupiny mají integrované optimalizace, které vám usnadní práci. Důrazně doporučujeme, abyste pro cílení na všechny uživatele a zařízení používali tyto skupiny a nepoužívali skupiny Všichni uživatelé nebo Všechna zařízení, které byste sami vytvořili.  
>
> Android Enterprise podporuje zahrnutí a vyloučení skupin. K přiřazení aplikace Android Enterprise můžete použít předdefinované skupiny **Všichni uživatelé** a **Všechna zařízení**. 

## <a name="include-and-exclude-groups-when-assigning-apps"></a>Zahrnutí a vyloučení skupin při přiřazování aplikací 
Přiřazení aplikace ke skupinám pomocí zahrnutí a vyloučení přiřazení:
1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V podokně **Klientské aplikace** vyberte **Aplikace**. Zobrazí se seznam přidaných aplikací.
5. Vyberte aplikaci, kterou chcete přiřadit. V řídicím panelu se zobrazí informace o aplikaci. 
6. V části nabídky **Spravovat** vyberte **Přiřazení**. 

    ![Zahrnout přiřazení aplikací při přiřazování aplikací](./media/apps-inc-exl-assignments/apps-inc-exl-01.png)
7. Pokud chcete přidat skupiny uživatelů, kteří jsou přiřazení k aplikaci, vyberte **Přidat skupinu**. 
8. V podokně **Přidat skupinu** vyberte **Typ přiřazení** z dostupných typů přiřazení.
9. Jako typ přiřazení vyberte **K dispozici s registrací i bez ní**.

    ![Přiřazení aplikací Intune – přidání skupiny](./media/apps-inc-exl-assignments/apps-inc-exl-02.png)
10. Pokud chcete vybrat skupinu uživatelů, které chcete zpřístupnit tuto aplikaci, vyberte **Zahrnuté skupiny**.

    > [!NOTE]
    > Pokud přidáváte skupinu a pro konkrétní typ přiřazení už byla zahrnuta jakákoliv jiná skupina, je pro ostatní typy zahrnutí přiřazení předem vybraná a není ji možné změnit. Použitou skupinu není možné použít jako zahrnutou skupinu.

11. Pokud chcete tuto aplikaci zpřístupnit všem uživatelům, vyberte **Ano**.

    ![Přiřazení aplikací Intune – zahrnutí skupin](./media/apps-inc-exl-assignments/apps-inc-exl-03.png)
12. Pokud chcete nastavit skupinu k zahrnutí, vyberte **OK**.
13. Pokud chcete vybrat skupiny uživatelů, které nemají mít přístup k této aplikaci, vyberte **Vyloučené skupiny**. 
14. Vyberte skupiny, které chcete vyloučit. Tím se aplikace stane pro tyto skupiny nedostupnou.

    ![Přiřazení aplikací Intune – vyloučení skupin](./media/apps-inc-exl-assignments/apps-inc-exl-04.png)
15. Pomocí **Vybrat** dokončete výběr skupin.
16. V podokně **Přidat skupinu** vyberte **OK**. Zobrazí se seznam **Přiřazení** aplikací.
17. Klikněte na **Uložit** a aktivujte tak přiřazení skupin pro tuto aplikaci.

Když provedete přiřazení skupin, pak už přiřazené skupiny nejsou k dispozici pro změny. Pokud chcete vybrat skupinu, která aktuálně není dostupná, nejdřív ji odeberte ze seznamu přiřazení k aplikaci. 

Přiřazení můžete upravit tak, že ze seznamu **Přiřazení** aplikací vyberete řádek obsahující konkrétní přiřazení, které chcete změnit. Kromě toho můžete odebrat přiřazení tak, že kliknete na tři tečky ( **...** ) na konci řádku a vyberete **Odebrat**. Zobrazení seznamu **Přiřazení** můžete změnit seskupením podle možnosti **Typ přiřazení** nebo **Zahrnuto/Vyloučeno**.

![Přiřazení aplikací Intune – dokončení](./media/apps-inc-exl-assignments/apps-inc-exl-05.png)

## <a name="next-steps"></a>Další kroky

- Další informace o zahrnutí a vyloučení přiřazení skupin pro aplikace najdete v [blogu k Microsoft Intune](https://aka.ms/new_app_assignment_process).
- Přečtěte si, jak [monitorovat informace a přiřazení aplikace](apps-monitor.md).
