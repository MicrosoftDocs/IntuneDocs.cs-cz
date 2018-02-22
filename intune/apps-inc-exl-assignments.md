---
title: "Zahrnutí a vyloučení přiřazení aplikací"
titlesuffix: Microsoft Intune
description: "Zjistěte, jak pomocí Intune zahrnout nebo vyloučit přiřazení aplikací."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/29/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca1f45c3203645dc474fcb6411a8ad598ff83714
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/03/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune

Pomocí Intune můžete na základě přiřazení do skupin nebo vyloučení určit, kdo má přístup k aplikaci. Zahrnutí a vyloučení u přiřazení aplikací ke skupině uživatelů nebo zařízení zadáte pomocí kombinace zahrnutí a vyloučení. Jakmile vyberete aplikaci, můžete vybrat způsob jejího přiřazení. Tato možnost může být užitečná, když aplikaci zpřístupníte zahrnutím velké skupiny a následně upřesníte vybrané uživatele vyloučením menší skupiny. U menší skupiny se může jednat například o testovací skupinu nebo skupinu vedoucích pracovníků. 

Při vyloučení skupin z přiřazení je nutné vyloučit buď skupiny uživatelů, nebo zařízení, není možné tyto skupiny kombinovat. Při vyloučení skupin se v Intune nebere v úvahu přiřazení uživatelů k zařízením. Pokud zahrnete skupiny uživatelů a současně vyloučíte skupiny zařízení, nebudou výsledky takové, jako očekáváte, protože zahrnutí má přednost před vyloučením. Pokud například nastavíte u aplikace pro iOS možnost **Všichni uživatelé** a vyloučíte **Všechna zařízení iPad**, budou moct ve výsledku danou aplikaci používat všichni uživatelé, kteří používají iPad. Pokud ale nastavíte u aplikace pro iOS možnost **Všechna zařízení** a vyloučíte **Všechna zařízení iPad**, bude nasazení úspěšné.  

>[!NOTE]
>Při nastavování přiřazení skupiny pro aplikaci se přestal používat typ **Neužívá se** a nahradila ho funkce vyloučení skupiny. 
>
>V Intune máte v konzole pohodlně k dispozici předem vytvořené skupiny **Všichni uživatelé** a **Všechna zařízení** s integrovanými optimalizacemi. Důrazně doporučujeme, abyste pro cílení na všechny uživatele a zařízení používali tyto skupiny a nepoužívali žádné skupiny Všichni uživatelé nebo Všechna zařízení, které byste sami vytvořili.  

## <a name="including-and-excluding-groups-when-assigning-apps"></a>Zahrnutí a vyloučení skupin při přiřazování aplikací 
Přiřazení aplikace ke skupinám pomocí zahrnutí a vyloučení přiřazení:
1. V okně Microsoft Intune vyberte **Mobilní aplikace**.
2. V okně **Mobilní aplikace** vyberte **Aplikace**. Zobrazí se seznam přidaných aplikací.
3. Vyberte aplikaci, kterou chcete přiřadit. Zobrazí se řídicí panel související s aplikací. 
4. V části **Správa** vyberte **Přiřazení**. 

    ![Přiřazení aplikací Intune](./media/apps-inc-exl-01.png)
5. Pokud chcete přidat skupiny uživatelů, kteří jsou přiřazení k aplikaci, vyberte **Přidat skupinu**. 
6. V okně **Přidat skupinu** vyberte **Typ přiřazení** z dostupných typů přiřazení.
7. Jako typ přiřazení vyberte **K dispozici s registrací i bez ní**.

    ![Přiřazení aplikací Intune – přidání skupiny](./media/apps-inc-exl-02.png)
8. Pokud chcete vybrat skupinu uživatelů, které chcete zpřístupnit tuto aplikaci, vyberte **Zahrnuté skupiny**.

    >[!NOTE]
    >Pokud přidáváte skupinu a pro daný typ přiřazení už byla zahrnuta jakákoliv jiná skupina, bude pro ostatní typy zahrnutí přiřazení předem vybraná a nebude ji možné změnit. Tuto použitou skupinu tedy není možné použít jako zahrnutou skupinu.

9. Pokud chcete tuto aplikaci zpřístupnit všem uživatelům, vyberte **Ano**.

    ![Přiřazení aplikací Intune – zahrnutí skupin](./media/apps-inc-exl-03.png)
10. Pokud chcete nastavit skupinu k zahrnutí, klikněte na tlačítko **OK**.
11. Pokud chcete vybrat skupiny uživatelů, které nemají mít přístup k této aplikaci, vyberte **Vyloučené skupiny**. 
12. Vyberte skupiny, které chcete vyloučit, a zamezte tak jejich přístupu k aplikaci.

    ![Přiřazení aplikací Intune – vyloučení skupin](./media/apps-inc-exl-04.png)
13. Kliknutím na tlačítko **Vybrat** dokončete výběr skupin.
14. Klikněte na tlačítko **OK** v okně **Přidat skupinu**. Zobrazí se seznam **Přiřazení** aplikací.
15. Klikněte na **Uložit** a aktivujte tak přiřazení skupin pro tuto aplikaci.

Při vytváření přiřazení skupin budou skupiny, které již jsou přiřazeny nebo vybrány, zakázané. Pokud chcete vybrat skupinu, která je aktuálně zakázaná, odeberte ji ze seznamu přiřazení k aplikaci. Přiřazení můžete upravit ze seznamu **Přiřazení** aplikací tak, že vyberete řádek, který obsahuje konkrétní přiřazení, které chcete změnit. Kromě toho můžete odebrat přiřazení tak, že kliknete na tři tečky (...) na konci řádku a vyberete **Odebrat**. Zobrazení seznamu **Přiřazení** můžete zobrazit také tak, že vyberete možnost seskupení podle možnosti **Typ přiřazení** nebo **Zahrnuto/Vyloučeno**.

![Přiřazení aplikací Intune – dokončení](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Další kroky

* Další informace o zahrnutí a vyloučení přiřazení skupin pro aplikace najdete v [blogu k Microsoft Intune](https://aka.ms/new_app_assignment_process).
