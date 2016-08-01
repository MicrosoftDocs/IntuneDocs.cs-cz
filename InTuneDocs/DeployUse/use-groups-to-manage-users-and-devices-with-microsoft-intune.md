---
title: "Použití skupin pro správu uživatelů a zařízení | Microsoft Intune"
description: "Vytvářejte a spravujte skupiny pomocí pracovního prostoru Skupiny."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 06/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ms.reviewer: lpatha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: 42328ee749517fd5abf923db35e7b13747e9f14b


---

# Vytvoření skupin pro správu uživatelů a zařízení s Microsoft Intune

Pokud chcete vytvořit a spravovat skupiny, použijte pracovní prostor **Skupiny** v konzole pro správu Microsoft Intune. Stránka **Přehled skupin** obsahuje souhrny stavů, které vám pomůžou identifikovat problémy vyžadující vaši pozornost a určit jejich prioritu:

-   Výstrahy
-   Aktualizace softwaru
-   Endpoint Protection
-   Zásady
-   Správa softwaru

Hierarchie skupiny se navíc zobrazí se souhrny stavu, které vám pomohou identifikovat a vyřešit problémy členů vybrané skupiny.


> [!TIP]
> Při vytváření skupin vezměte v úvahu, jak použijete zásady. Můžete mít třeba zásady specifické pro operační systémy zařízení a zásady specifické pro různé role ve vaší organizaci nebo pro organizační jednotky, které jste už v Active Directory definovali. Někdo považuje za užitečné používat skupiny zařízení specifické pro iOS, Android a Windows a skupiny uživatelů pro každou organizační roli.
>
> Budete chtít nejspíš vytvořit výchozí zásadu, která platí pro všechny skupiny a zařízení, pro zajištění základních požadavků na dodržování předpisů ve vaší společnosti. Potom vytvořte konkrétnější zásady pro nejširší kategorie uživatele a zařízení, například zásady e-mailu pro každý operační systém zařízení.
>
> Pečlivě zásady pojmenujte, abyste je později mohli snadno identifikovat. Dobrý název zásady je třeba **Zásada e-mailů WP pro celou firmu**.
>
> Při každém vytvoření omezující zásady budete chtít tuto zásadu sdělit uživatelům, takže doporučujeme, abyste po vytvoření obecnějších skupin a zásad věnovali pozornost tomu, jak vytváříte menší skupiny, aby se redukovala zbytečná komunikace.


## Vytvoření skupiny zařízení

1.  V konzole pro správu Intune zvolte **Skupiny** &gt; **Přehled** &gt; **Vytvořit skupinu**.

2.  Zadejte název skupiny a její nepovinný popis a vyberte skupinu zařízení jako nadřazenou skupinu. Vyberte **Další**.

3.  Na stránce **Definovat kritéria členství** vyberte typ zařízení, který bude skupina obsahovat. Další možnosti konfigurace skupiny závisí na vybraném typu zařízení:

    -   **Počítač:** Určete, jestli se mají zahrnout všichni členové nadřazené skupiny, a organizační jednotky (OU) a domény, které chcete zahrnout nebo vyloučit. Informace o organizačních jednotkách a doménách počítače se získávají z inventáře.

    -   **Mobilní:** Určete, jestli se mají zahrnout jenom mobilní zařízení spravovaná Intune, zařízení spravovaná Exchange ActiveSync, nebo obojí.

    -   **Všechna zařízení:** Tato možnost zahrne všechna zařízení, bez vyloučení na základě kritérií.

4.  Na stránce **Definovat přímé členství** zahrňte nebo vylučte jednotlivá zařízení, která určíte kliknutím na **Procházet**. Pokud použijete možnost pro výběr zařízení, která nejsou ve vámi určené nadřazené skupině, přidají se tato zařízení do nadřazené skupiny automaticky.


5.  Na stránce **Souhrn** si prohlédněte akce, které se provedou. Klikněte na **Dokončit**.

Nově vytvořenou skupinu najdete v seznamu **Skupiny** v pracovním prostoru **Skupiny** v rámci nadřazené skupiny. Tady můžete skupinu i upravit nebo odstranit.

## Vytvoření skupiny uživatelů

1.  V konzole pro správu Intune zvolte **Skupiny** &gt; **Přehled** &gt; **Vytvořit skupinu**.

2.  Zadejte název skupiny a její nepovinný popis a vyberte skupinu uživatelů jako nadřazenou skupinu. Vyberte **Další**.

3.  Na stránce **Definovat kritéria členství** určete, jestli se mají zahrnout všichni členové nadřazené skupiny, nebo jestli se má začít s prázdnou skupinou.  Potom můžete zahrnout nebo vyloučit členy na základě nastavení **Skupiny uživatelů**, které ručně nakonfigurujete v [Centru pro správu Office 365](http://go.microsoft.com/fwlink/?LinkId=698854) nebo které se synchronizuje z vaší místní služby Active Directory. Pokud se změní členství ve skupině zabezpečení, může se změnit i členství ve skupinách uživatelů založených na této skupině zabezpečení.

    > [!IMPORTANT]
    > Teď platí, že pokud vaše skupina obsahuje členy z konkrétní skupiny zabezpečení nebo manažera a zároveň vyloučíte členy z konkrétních skupin, dojde k odebrání členů, které jste na začátku zahrnuli. Pokud chcete vytvořit skupinu, která má zahrnuté i vyloučené členy, doporučujeme nejdřív vytvořit nadřazenou skupinu se zahrnutými členy a pak k této skupině vytvořit podřízenou skupinu, ve které uvedete vyloučené členy. Podřízenou skupinu pak můžete podle potřeby využít pro zásady Intune, profily a distribuci aplikací.

    > [!NOTE]
    > Na portálu pro správu Azure můžete vytvořit skupinu podle manažera, kterému uživatelé podléhají. Skupina se bude dynamicky měnit podle toho, jak se do týmu daného manažera ve službě Azure Active Directory přidávají zaměstnanci nebo se z něj naopak odebírají. Postup pro vytvoření skupiny Azure podle manažera najdete v článku [Vytváření rozšířených pravidel pomocí atributů](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) v části **Konfigurace skupiny manažera**.


4.  Na stránce **Definovat přímé členství** zahrňte nebo vylučte jednotlivé uživatele, které určíte kliknutím na **Procházet**. Pokud použijete možnost pro výběr uživatelů, kteří nejsou ve vámi určené nadřazené skupině, přidají se tito uživatelé do nadřazené skupiny automaticky. V dolní části dialogového okna **Vybrat členy** najdete možnost ručního přidání uživatele. To je užitečné, pokud chcete přidat uživatele, který dosud nemá zaregistrované zařízení.


5.  Na stránce **Souhrn** si prohlédněte akce, které se provedou. Klikněte na **Dokončit**.

Nově vytvořenou skupinu najdete v seznamu **Skupiny** v pracovním prostoru **Skupiny** v rámci nadřazené skupiny. Tady můžete skupinu i upravit nebo odstranit.

> [!TIP]
> Skupiny zabezpečení jsou skvělým zdrojem pro naplnění skupin uživatelů. Protože vaše skupiny zabezpečení definují, kdo má k jakým prostředkům přístup, jsou srozumitelné pro skupiny uživatelů Intune. Skupiny zabezpečení, které jsou synchronizované z Active Directory do Azure Active Directory nebo které jsou vytvořené přímo v Azure Active Directory pomocí Centra pro správu Office 365 nebo portálu pro správu Azure, jsou všechny dostupné pro vytváření skupin uživatelů ve službě Intune.

## Přizpůsobení zobrazení pro role správce
Filtrovaná zobrazení skupin vám umožní přizpůsobit zobrazení, která správci můžou zobrazit na základě jejich role, a omezit, které skupiny můžou jednotliví správci IT spravovat. To může být užitečné, když:

-   Vaši správci IT mají možnost nasadit položky jenom u konkrétních uživatelů a zařízení.

-   Chcete pro každého správce IT zobrazit jenom relevantní skupiny.

Filtrovaná zobrazení skupin pro správce služeb můžete nakonfigurovat v konzole pro správu Intune. Podrobnosti najdete v tématu [Co potřebujete vědět, než začnete s Microsoft Intune](/intune/get-started/what-to-know-before-you-start-microsoft-intune).

Po dokončení konfigurace filtrovaných zobrazení skupin pro správce služby tento správce:

-   Může zobrazit a vybrat jenom skupiny, které jste při nasazení softwaru nebo zásad nebo pomocí sestav zadali.

-   Neobdrží informace o stavu na následujících stránkách konzoly pro správu:

    -   **Přehled systému**

    -   **Přehled skupin**

    -   **Přehled služby Endpoint Protection**

    -   **Přehled výstrah**

    -   **Přehled softwaru**

    -   **Přehled zásad**

### Konfigurace filtrovaných zobrazení skupin

1.  V konzole pro správu Intune zvolte **Správce** &gt; **Správa správců** &gt; **Správci služeb**.

2.  Vyberte správce služeb, pro kterého chcete filtrovat skupiny, a pak klikněte na **Spravovat skupiny**.

3.  V dialogovém okně **Vyberte skupiny, které budou pro tohoto správce služeb viditelné** přidejte skupiny, ke kterým bude moct vybraný správce služeb přistupovat, a pak klikněte na **OK**.

Po dokončení konfigurace filtrovaných zobrazení skupiny, bude správce IT moct zobrazit a vybrat jenom vámi zvolené skupiny.

## Správa skupin
Po vytvoření vlastních skupin je budete moct dále spravovat podle potřeb vaší organizace.

Skupinu můžete upravit tak, aby se změnil její název a popis a také členové, které obsahuje.

Skupinu, která už neslouží potřebám vaší organizace, můžete odstranit. Odstraněním skupiny nedojde k odstranění uživatelů, kteří do této skupiny patří.

## Další kroky

### Kontrola návrhu
Po nastavení skupin a zásad ověřte praktický dopad vytvořeného návrhu kontrolou položek **Zamýšlená hodnota** a **Stav**.

1. Vyberte jakákoli zařízení ze skupiny zařízení a procházejte kategorie informací v horní části obrazovky.
2. Vyberte **Zásada** . Zobrazí se snímek obrazovky nastavení zásady zařízení Android podobný následujícímu.

![Příklad zásady nastavení iOS](../media/Intune-Device-Policy-v.2.jpg)

Každá zásada má **určenou hodnotu** a **Stav**. Určená hodnota označuje to, čeho chcete dosáhnout při přiřazování zásady. Stav označuje to, čeho skutečně dosáhnete, když jsou společně zvažovány všechny zásady, které u zařízení použijete, a všechna omezení a požadavky na hardware a operační systém.  Na snímku obrazovky vidíte dva jasné příklady:

-   Možnost **Povolit jednoduchá hesla** je nastavená na **Ano**, jak ukazuje sloupec **Určená hodnota**, ale její **Stav** je **Nepoužívá se**. Důvodem je, že se na zařízeních s Androidem nepodporují jednoduchá hesla.

-   Podobně pak u tohoto zařízení není použitá rozšířená položka zásad **Nastavení e-mailu pro zařízení se systémem iOS**, protože to je zařízení s Androidem.

> [!NOTE]
> Mějte na paměti, že když použijete dvě zásady s různými úrovněmi omezení na stejné zařízení nebo uživatele, v praxi se uplatní víc omezující zásada.



<!--HONumber=Jul16_HO3-->


