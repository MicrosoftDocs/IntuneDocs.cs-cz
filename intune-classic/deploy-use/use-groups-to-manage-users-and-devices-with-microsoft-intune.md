---
title: "Použití skupin pro správu uživatelů a zařízení"
description: "Vytvářejte a spravujte skupiny pomocí pracovního prostoru Skupiny."
keywords: 
author: Mtillman
ms.author: mtillman
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ms.reviewer: lpatha
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 13c8946dd75d6bdede0e2a8941030250c6b12ef6
ms.contentlocale: cs-cz
ms.lasthandoff: 06/08/2017


---
# <a name="use-groups-to-manage-users-and-devices-in-microsoft-intune"></a>Použití skupin pro správu uživatelů a zařízení v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Toto téma popisuje, jak vytvořit skupiny v Intune. Poskytuje také informace o změně správy skupin, která se chystá v nadcházejících měsících. 

>[!IMPORTANT]
>
>Pokud se vám na portálu Intune po otevření pracovního prostoru Skupiny zobrazí odkaz na portál Azure Active Directory (Azure AD), znamená to, že používáte *nový* přístup ke správě skupin v Intune – na základě skupin zabezpečení Azure AD. Jeho popis najdete v tématu [Migrace skupin Azure Active Directory](migrating-groups-to-azure-active-directory.md). Pokud chcete vytvářet a spravovat skupiny, klikněte na odkaz na portál Azure AD.
>
>![Snímek obrazovky s odkazem na správu skupin Azure](../media/groups-link-azure.png) 
>
>Pokud odkaz na portál Azure AD nevidíte, stále používáte *současný* přístup ke správě skupin popsaný v tomto tématu v části [Vytvoření skupin pro správu uživatelů a zařízení pomocí Microsoft Intune](#Create-groups-to-manage-users-and-devices-with-Microsoft-Intune).

Toto téma popisuje, jak vytvořit skupiny Intune v konzole pro správu Intune.

Skupiny můžete vytvářet a spravovat v pracovním prostoru **Skupiny** v konzole pro správu Microsoft Intune. Stránka **Přehled skupin** zobrazuje souhrny stavů, které vám pomůžou identifikovat problémy vyžadující vaši pozornost a určit jejich prioritu. Souhrny stavů pokrývají tyto oblasti:

-   Výstrahy
-   Aktualizace softwaru
-   Endpoint Protection
-   Zásady
-   Správa softwaru

Hierarchie skupiny navíc zobrazí souhrny stavu, které vám pomůžou identifikovat a vyřešit problémy členů vybrané skupiny.

## <a name="create-groups"></a>Vytváření skupin

> [!TIP]
> Při vytváření skupin vezměte v úvahu, jak použijete zásady. Můžete mít například zásady specifické pro operační systém zařízení a zásady specifické pro různé role ve vaší organizaci nebo organizační jednotky, které už jste ve službě Active Directory definovali dříve. Může být užitečné používat oddělené skupiny zařízení pro iOS, Android a Windows a oddělené skupiny uživatelů pro jednotlivé organizační role.
>
> Budete taky nejspíš chtít vytvořit výchozí zásady, které budou platit pro všechny skupiny a zařízení, aby se stanovily základní požadavky na dodržování předpisů vaší organizace. Poté můžete vytvořit konkrétnější zásady pro nejširší kategorie uživatelů a zařízení. Můžete například vytvořit zásady e-mailů pro každý operační systém zvlášť.
>
> Pečlivě zásady pojmenujte, abyste je později mohli snadno identifikovat. Dobrý a popisný název zásady je třeba **Zásada e-mailů WP pro celou firmu**.
>
> Pokaždé, když vytvoříte omezující zásadu, budete o tom chtít informovat uživatele. Po vytvoření obecnějších skupin a zásad věnujte pozornost tomu, jak vytváříte menší skupiny, aby se redukovala zbytečná komunikace.

## <a name="to-create-a-device-group"></a>Vytvoření skupiny zařízení

1.  V konzole pro správu Intune zvolte **Skupiny** &gt; **Přehled** &gt; **Vytvořit skupinu**.

2.  Zadejte název skupiny a její popis (nepovinné) a pak vyberte skupinu zařízení jako nadřazenou skupinu. Vyberte **Další**.

3.  Na stránce **Definovat kritéria členství** vyberte typ zařízení, který má skupina obsahovat. Na základě typů zařízení, která budete chtít zahrnout, pro vás budou dostupné další možnosti konfigurace skupiny:

    -   **Počítač**. Rozhodněte, jestli se mají zahrnout všichni členové nadřazené skupiny, a vyberte organizační jednotky a domény, které chcete zahrnout nebo vyloučit. Organizační jednotky a informace o doménách pro počítač můžete získat z inventáře.

    -   **Mobilní**. Vyberte, jestli se mají zahrnout jenom mobilní zařízení spravovaná službou Intune, jenom zařízení spravovaná službou Exchange ActiveSync, nebo obojí.

    -   **Všechna zařízení**. Tato možnost zahrnuje všechna zařízení, nepoužívají se žádná kritéria k vyloučení.

4.  Na stránce **Definovat přímé členství** klikněte na **Procházet** a vyberte, která zařízení chcete zahrnout a která vyloučit. Pokud vyberete zařízení, která nejsou ve vámi určené nadřazené skupině, přidá Intune tato zařízení do nadřazené skupiny automaticky.

5.  Na stránce **Souhrn** zkontrolujte své výběry a klikněte na **Dokončit**.

Nově vytvořená skupina se zobrazí v seznamu **Skupiny** v pracovním prostoru **Skupiny** pod příslušnou nadřazenou skupinou. Tady taky můžete skupinu upravit nebo odstranit.

## <a name="to-create-a-user-group"></a>Vytvoření skupiny uživatelů

1.  V konzole pro správu Intune zvolte **Skupiny** &gt; **Přehled** &gt; **Vytvořit skupinu**.

2.  Zadejte název skupiny a její popis (nepovinné) a pak vyberte nadřazenou skupinu uživatelů. Vyberte **Další**.

3.  Na stránce **Definovat kritéria členství** vyberte, jestli se mají zahrnout všichni členové nadřazené skupiny, nebo jestli se má začít s prázdnou skupinou. Potom zahrňte nebo vylučte členy na základě uživatelských skupin zabezpečení, které buď ručně nakonfigurujete v [Centru pro správu Office 365](http://go.microsoft.com/fwlink/?LinkId=698854), nebo synchronizujete z Active Directory. Pokud se změní členství ve skupině zabezpečení, může se změnit i členství ve skupinách uživatelů založených na této skupině zabezpečení.

    > [!IMPORTANT]
    > Pokud nyní skupina obsahuje členy z konkrétních skupin zabezpečení nebo skupin manažerů a vy z nějakých skupin členy vyloučíte, dojde k odebrání členů, které jste původně zahrnuli. Pokud chcete vytvořit skupinu, která obsahuje zahrnuté i vyloučené členy, doporučujeme, abyste nejdříve vytvořili nadřazenou skupinu se zahrnutými členy. Pak vytvořte podřízenou skupinu této nadřazené skupiny. Do nové podřízené skupiny přidejte vyloučené členy. Podřízenou skupinu pak používejte ke správě zásad Intune, profilů a distribuce aplikací.

    > [!NOTE]
    > Na webu Azure Portal můžete vytvořit skupiny založené na tom, pod jakého manažera uživatelé spadají. Tento typ skupiny je dynamický a bude se měnit v závislosti na tom, jak se do týmu daného manažera ve službě Azure Active Directory přidávají zaměstnanci nebo se z něj naopak odebírají. Návod, jak vytvořit skupinu Azure na základě jména manažera, najdete v článku [Vytváření rozšířených pravidel pomocí atributů](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) v části **Konfigurace skupiny manažera**.

4.  Na stránce **Definovat přímé členství** klikněte na **Procházet** a vyberte, které uživatele chcete zahrnout a které vyloučit. Pokud vyberete uživatele, kteří nejsou ve vámi určené nadřazené skupině, přidají se tito uživatelé do nadřazené skupiny automaticky. Možnost ručně přidat uživatele najdete v dolní části dialogu **Vybrat členy**. To je užitečné, pokud chcete přidat uživatele, který dosud nemá zaregistrované zařízení.

5.  Na stránce **Souhrn** zkontrolujte zvolené možnosti a klikněte na **Dokončit**.

Nově vytvořená skupina se zobrazí v seznamu **Skupiny** v pracovním prostoru **Skupiny** pod příslušnou nadřazenou skupinou. Tady taky můžete skupinu upravit nebo odstranit.

> [!TIP]
> Skupiny zabezpečení jsou dobrý prostředek pro naplňování skupin uživatelů. Vzhledem k tomu, že skupiny zabezpečení definují, kdo má přístup k jakým prostředkům, jsou dobře převeditelné i na skupiny uživatelů Intune. Skupiny zabezpečení, které jsou synchronizované z Active Directory do Azure Active Directory nebo které vytvoříte přímo v Azure Active Directory pomocí Centra pro správu Office 365 nebo webu Azure Portal, můžete použít k vytváření skupin uživatelů ve službě Intune.

## <a name="filter-admin-views-by-role"></a>Filtrování zobrazení správce podle rolí
Ve filtrovaných zobrazeních skupiny můžete určit, co správce IT uvidí, na základě jeho role. Můžete taky pro jednotlivé správce IT omezit, které skupiny můžou spravovat. To může být užitečné, když:

-   Chcete, aby vaši správci IT měli možnost nasadit položky jenom u konkrétních uživatelů a zařízení
-   Chcete, aby vaši správci IT viděli jenom skupiny, které jsou pro ně relevantní

Filtrovaná zobrazení skupin pro jednotlivé správce služby můžete nakonfigurovat v konzole pro správu Intune. Podrobnosti najdete v tématu [Co potřebujete vědět, než začnete s Microsoft Intune](/intune/supported-devices-browsers).

Jakmile pro správce služby nastavíte filtrovaná zobrazení skupin, bude daný správce při nasazování softwaru či zásad nebo spouštění sestav moci zobrazit a vybrat pouze skupiny, které jste určili. Správce také neuvidí informace o stavu na následujících stránkách konzoly pro správu:

-   **Přehled systému**
-   **Přehled skupin**
-   **Přehled produktu Endpoint Protection**
-   **Přehled výstrah**
-   **Přehled softwaru**
-   **Přehled zásad**

### <a name="to-create-a-filtered-group-view"></a>Vytvoření filtrovaného zobrazení skupiny

1.  V konzole pro správu Intune zvolte **Správce** &gt; **Správa správců** &gt; **Správci služeb**.

2.  Vyberte správce služeb, pro kterého chcete vytvořit filtrované zobrazení skupiny, a klikněte na **Spravovat skupiny**.

3.  V dialogu **Vyberte skupiny, které budou viditelné pro tohoto správce služeb** přidejte skupiny, ke kterým bude moct správce služeb přistupovat, a pak klikněte na **OK**.

Jakmile filtrovaná zobrazení skupiny nastavíte, bude tento správce IT moct zobrazit a vybrat jenom vámi označené skupiny.

## <a name="manage-your-groups"></a>Správa skupin
Po vytvoření vlastních skupin je budete moct dále spravovat podle potřeb vaší organizace.

Skupinu můžete upravit tak, že změníte její název či popis nebo členy, kteří do ní patří.

Skupinu, která už neslouží potřebám vaší organizace, můžete odstranit. Odstraněním skupiny nedojde k odstranění uživatelů, kteří do této skupiny patří.

## <a name="next-steps"></a>Další kroky
Po nastavení skupin a zásad ověřte praktický dopad vytvořeného návrhu kontrolou položek **Zamýšlená hodnota** a **Stav**.

### <a name="to-check-your-design"></a>Kontrola návrhu

1. Vyberte jakékoli zařízení ze skupiny zařízení a projděte kategorie informací v horní části stránky.
2. Vyberte **Zásady**. Zobrazí se snímek obrazovky nastavení zásady zařízení Android podobný následujícímu.

![Příklad zásad nastavení pro Android](../media/Intune-Device-Policy-v.2.jpg)

U každé zásady je **Zamýšlená hodnota** a **Stav**. Zamýšlená hodnota je to, čeho jste při přiřazování zásady chtěli dosáhnout. Stav označuje to, čeho skutečně dosáhnete, když se zohlední všechny zásady použité u zařízení a všechna omezení a požadavky na hardware a operační systém. Tento snímek obrazovky ukazuje dva jasné příklady:

-   Možnost **Povolit jednoduchá hesla** je nastavená na **Ano**, jak ukazuje sloupec **Zamýšlená hodnota**, ale její **Stav** je **Nepoužívá se**. Důvodem je, že se na zařízeních s Androidem nepodporují jednoduchá hesla.
-   Podobně pak u tohoto zařízení není použitá rozšířená položka zásad **Nastavení e-mailu pro zařízení se systémem iOS**, protože se jedná o zařízení s Androidem.

> [!NOTE]
> Mějte na paměti, že když použijete na stejné zařízení nebo uživatele dvě zásady s různými úrovněmi omezení, v praxi se uplatní víc omezující zásada.

