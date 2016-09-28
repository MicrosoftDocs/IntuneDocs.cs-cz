---
title: "Použití skupin pro správu uživatelů a zařízení | Microsoft Intune"
description: "Vytvářejte a spravujte skupiny pomocí pracovního prostoru Skupiny."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ms.reviewer: lpatha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8c474810f8d3c7db4784c38c45c85c83b647860b
ms.openlocfilehash: fa0c235d3ab5f9dde04f8345e7e28fdd00603e58


---
# Použití skupin pro správu uživatelů a zařízení v Microsoft Intune

Toto téma popisuje, jak vytvořit skupiny v Intune. Poskytuje také informace o změně správy skupin, která se chystá v nadcházejících měsících. 

>[!IMPORTANT]
>
>Pokud se vám po otevření pracovního prostoru Skupiny na portálu Intune zobrazí odkaz na portál Azure Active Directory (Azure AD), znamená to, že už používáte *nový* přístup ke správě skupin v Intune – na základě skupin zabezpečení Azure AD. Ten podrobněji popisujeme v části [Oznámení o připravovaných vylepšeních správy skupin](#notice-of-upcoming-improvements-to-the-admin-experience-for-groups). Pokud chcete vytvářet a spravovat skupiny, klikněte na odkaz na portál Azure AD. Další informace o tom, jak pracovat se skupinami zabezpečení Azure AD, najdete v článku [Správa přístupu k prostředkům pomocí skupin Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
>
>Pokud odkaz na portál Azure AD nevidíte, stále používáte *současný* přístup ke správě skupin popsaný v tomto tématu v části [Vytvoření skupin pro správu uživatelů a zařízení pomocí Microsoft Intune](#Create-groups-to-manage-users-and-devices-with-Microsoft-Intune).


## Oznámení o připravovaných vylepšeních správy skupin

Sdělili jste nám, že chcete jednotnou správu skupin a cílení pro Enterprise Mobility a Security. Vyslyšeli jsme vás. Na základě vaší zpětné vazby začneme brzy převádět skupiny Intune na skupiny zabezpečení založené na Azure Active Directory. Tato změna sjednotí správu skupin v rámci Intune a Azure Active Directory (Azure AD). S novým prostředím už nebudete muset pro jednotlivé služby vytvářet duplicitní skupiny. A možnost použít Windows PowerShell a Microsoft Graph navíc zvýší rozšiřitelnost.

### Co to pro mne teď znamená?
V tuto chvíli vás tato změna neovlivní. Ale připravujeme následující:

-   V září 2016 budou nové účty, zřízené po vydání měsíční aktualizace služby, používat skupiny zabezpečení služby Azure AD místo skupin uživatelů Intune.   
-   V říjnu 2016 budou nové účty, zřízené po vydání měsíční aktualizace služby, spravovat jak skupiny uživatelů, tak i skupiny zařízení, na portálu Azure AD. Na stávající zákazníky to zatím nebude mít žádný dopad.
-   V listopadu 2016 začne produktový tým Intune s migrací stávajících zákazníků na novou správu skupin na základě skupin Azure AD. Všechny současné skupiny uživatelů a zařízení, které v Intune jsou, budou migrovány na skupiny zabezpečení Azure AD. Migraci budeme provádět v dávkách, začneme s tím v listopadu 2016. Migraci zahájíme až ve chvíli, kdy co nejvíce minimalizujeme veškerý dopad, který by mohla mít na vaši každodenní práci. Očekáváme, že na vaše uživatele nebude mít dopad žádný. Před zahájením migrace vašeho účtu vám navíc pošleme upozornění.


### Jak a kdy bude můj účet migrován do nového prostředí skupin?
Současné zákazníky služby Intune budeme migrovat průběžně. Plán této migrace právě dokončujeme a během několika týdnů přineseme další informace. Na zahájení migrace vás s předstihem upozorníme. Pokud máte k migraci jakékoli otázky, obraťte se na náš tým migrace na adrese <intunegrps@microsoft.com>.

### Co se stane s mými existujícími skupinami uživatelů a zařízení?
 Skupiny uživatelů a skupiny zařízení, které jste vytvořili ve službě Intune, budou migrovat na skupiny zabezpečení Azure AD. Výchozí skupiny Intune, jako například Všichni uživatelé, zahrneme do migrace pouze tehdy, pokud je vaše nasazení skutečně používá (posoudí se v okamžiku migrace). Migrace může být u některých skupin složitější. Dáme vám vědět, pokud budou k migraci u vaší organizace potřeba nějaké další kroky.

### Jaké nové funkce mi změna přinese?
V rámci migrace z Intune do Azure Active Directory zavedeme novou funkci:

-    Skupiny zabezpečení Azure AD budou v Intune podporované pro všechny typy nasazení.
-    Skupiny zabezpečení Azure AD budou podporovat seskupování zařízení i uživatelů.
-    Skupiny zabezpečení Azure AD budou podporovat dynamické skupiny, které mají atributy zařízení z Intune. Budete moct například dynamicky seskupit zařízení podle platformy (jako iOS). Při registraci nového zařízení iOS ve vaší organizaci bude zařízení automaticky přidáno do dynamické skupiny zařízení s iOS.
-    Budete mít sjednocené prostředí správy skupin v Azure AD a Intune.
- Do Azure AD bude přidána role Správce služby Intune, aby správci služby Intune mohli provádět úkoly správy skupin v Azure AD.

### Které funkce Intune přestanou být dostupné?
Správa skupin se celkově zlepší, ale některé funkce Intune přestanou být po migraci vaší organizace ze skupin Intune na skupiny zabezpečení Azure AD dostupné.

#### Funkce správy skupin

-   Po migraci už při vytváření nové skupiny nebude možné vyloučit členy nebo skupiny. S dynamickými skupinami Azure AD ale budete moct pomocí atributů vytvořit rozšířená pravidla, která lze použít k vyloučení uživatelů ze skupiny na základě nastavených kritérií.
-   Skupiny Neseskupení uživatelé a Neseskupená zařízení nebudou podporovány. Tyto skupiny nebudou součástí migrace z Intune do Azure AD.


#### Funkce závislé na konkrétních skupinách

-   Role Správce služby nebude mít oprávnění **Správa skupin**.
-   Nebude možné vytvořit skupinu zařízení Exchange ActiveSync. Vaše skupina všech zařízení spravovaných pomocí EAS bude ze skupiny převedena na zobrazení sestavy.
-  Přesun skupin v sestavách nebude dostupný.
-  Vlastní pravidla cílení oznámení na skupiny nebudou dostupná.

### Jak se mám na tyto změny připravit?
 Máme několik doporučení, která vám tento přechod usnadní:

- Před migrací odstraňte všechny nežádoucí nebo nepotřebné skupiny Intune.
- Vyhodnoťte využívání funkce vyloučení ve skupinách a zvažte změnu návrhu skupin, abyste se bez této funkce obešli.
-  Pokud máte nějaké správce, kteří nemají oprávnění k vytváření skupin ve službě Azure AD, požádejte správce Azure AD, aby je přidal do role Správce služby Intune v Azure AD.


## Vytvoření skupin pro správu uživatelů a zařízení s Microsoft Intune

Tato část popisuje, jak vytvořit skupiny Intune v konzole pro správu Intune.

Skupiny můžete vytvářet a spravovat v pracovním prostoru **Skupiny** v konzole pro správu Microsoft Intune. Stránka **Přehled skupin** zobrazuje souhrny stavů, které vám pomůžou identifikovat problémy vyžadující vaši pozornost a určit jejich prioritu. Souhrny stavů pokrývají tyto oblasti:

-   Výstrahy
-   Aktualizace softwaru
-   Endpoint Protection
-   Zásady
-   Správa softwaru

Hierarchie skupiny navíc zobrazí souhrny stavu, které vám pomůžou identifikovat a vyřešit problémy členů vybrané skupiny.

## Vytváření skupin

> [!TIP]
> Při vytváření skupin vezměte v úvahu, jak použijete zásady. Můžete mít například zásady specifické pro operační systém zařízení a zásady specifické pro různé role ve vaší organizaci nebo organizační jednotky, které už jste ve službě Active Directory definovali dříve. Může být užitečné používat oddělené skupiny zařízení pro iOS, Android a Windows a oddělené skupiny uživatelů pro jednotlivé organizační role.
>
> Budete taky nejspíš chtít vytvořit výchozí zásady, které budou platit pro všechny skupiny a zařízení, aby se stanovily základní požadavky na dodržování předpisů vaší organizace. Poté můžete vytvořit konkrétnější zásady pro nejširší kategorie uživatelů a zařízení. Můžete například vytvořit zásady e-mailů pro každý operační systém zvlášť.
>
> Pečlivě zásady pojmenujte, abyste je později mohli snadno identifikovat. Dobrý a popisný název zásady je třeba **Zásada e-mailů WP pro celou firmu**.
>
> Pokaždé, když vytvoříte omezující zásadu, budete o tom chtít informovat uživatele. Po vytvoření obecnějších skupin a zásad věnujte pozornost tomu, jak vytváříte menší skupiny, aby se redukovala zbytečná komunikace.

### Vytvoření skupiny zařízení

1.  V konzole pro správu Intune zvolte **Skupiny** &gt; **Přehled** &gt; **Vytvořit skupinu**.

2.  Zadejte název skupiny a její popis (nepovinné) a pak vyberte skupinu zařízení jako nadřazenou skupinu. Vyberte **Další**.

3.  Na stránce **Definovat kritéria členství** vyberte typ zařízení, který má skupina obsahovat. Na základě typů zařízení, která budete chtít zahrnout, pro vás budou dostupné další možnosti konfigurace skupiny:

    -   **Počítač**. Rozhodněte, jestli se mají zahrnout všichni členové nadřazené skupiny, a vyberte organizační jednotky a domény, které chcete zahrnout nebo vyloučit. Organizační jednotky a informace o doménách pro počítač můžete získat z inventáře.

    -   **Mobilní**. Vyberte, jestli se mají zahrnout jenom mobilní zařízení spravovaná službou Intune, jenom zařízení spravovaná službou Exchange ActiveSync, nebo obojí.

    -   **Všechna zařízení**. Tato možnost zahrnuje všechna zařízení, nepoužívají se žádná kritéria k vyloučení.

4.  Na stránce **Definovat přímé členství** klikněte na **Procházet** a vyberte, která zařízení chcete zahrnout a která vyloučit. Pokud vyberete zařízení, která nejsou ve vámi určené nadřazené skupině, přidá Intune tato zařízení do nadřazené skupiny automaticky.

5.  Na stránce **Souhrn** zkontrolujte své výběry a klikněte na **Dokončit**.

Nově vytvořená skupina se zobrazí v seznamu **Skupiny** v pracovním prostoru **Skupiny** v rámci nadřazené skupiny. Tady taky můžete skupinu upravit nebo odstranit.

### Vytvoření skupiny uživatelů

1.  V konzole pro správu Intune zvolte **Skupiny** &gt; **Přehled** &gt; **Vytvořit skupinu**.

2.  Zadejte název skupiny a její popis (nepovinné) a pak vyberte nadřazenou skupinu uživatelů. Vyberte **Další**.

3.  Na stránce **Definovat kritéria členství** vyberte, jestli se mají zahrnout všichni členové nadřazené skupiny, nebo jestli se má začít s prázdnou skupinou. Potom zahrňte nebo vylučte členy na základě uživatelských skupin zabezpečení, které buď ručně nakonfigurujete v [Centru pro správu Office 365](http://go.microsoft.com/fwlink/?LinkId=698854), nebo synchronizujete z Active Directory. Pokud se změní členství ve skupině zabezpečení, může se změnit i členství ve skupinách uživatelů založených na této skupině zabezpečení.

    > [!IMPORTANT]
    > Pokud nyní skupina obsahuje členy z konkrétních skupin zabezpečení nebo skupin manažerů a vy z nějakých skupin členy vyloučíte, dojde k odebrání členů, které jste původně zahrnuli. Pokud chcete vytvořit skupinu, která obsahuje zahrnuté i vyloučené členy, doporučujeme, abyste nejdříve vytvořili nadřazenou skupinu se zahrnutými členy. Pak vytvořte podřízenou skupinu této nadřazené skupiny. Do nové podřízené skupiny přidejte vyloučené členy. Podřízenou skupinu pak používejte ke správě zásad Intune, profilů a distribuce aplikací.

    > [!NOTE]
    > Na webu Azure Portal můžete vytvořit skupiny založené na tom, pod jakého manažera uživatelé spadají. Tento typ skupiny je dynamický a bude se měnit v závislosti na tom, jak se do týmu daného manažera ve službě Azure Active Directory přidávají zaměstnanci nebo se z něj naopak odebírají. Návod, jak vytvořit skupinu Azure na základě jména manažera, najdete v článku [Vytváření rozšířených pravidel pomocí atributů](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) v části **Konfigurace skupiny manažera**.

4.  Na stránce **Definovat přímé členství** klikněte na **Procházet** a vyberte, které uživatele chcete zahrnout a které vyloučit. Pokud vyberete uživatele, kteří nejsou ve vámi určené nadřazené skupině, přidají se tito uživatelé do nadřazené skupiny automaticky. Možnost ručně přidat uživatele najdete v dolní části dialogu **Vybrat členy**. To je užitečné, pokud chcete přidat uživatele, který dosud nemá zaregistrované zařízení.

5.  Na stránce **Souhrn** zkontrolujte zvolené možnosti a klikněte na **Dokončit**.

Nově vytvořená skupina se zobrazí v seznamu **Skupiny** v pracovním prostoru **Skupiny** pod příslušnou nadřazenou skupinou. Tady taky můžete skupinu upravit nebo odstranit.

> [!TIP]
> Skupiny zabezpečení jsou dobrý prostředek pro naplňování skupin uživatelů. Vzhledem k tomu, že skupiny zabezpečení definují, kdo má přístup k jakým prostředkům, jsou dobře převeditelné i na skupiny uživatelů Intune. Skupiny zabezpečení, které jsou synchronizované z Active Directory do Azure Active Directory nebo které vytvoříte přímo v Azure Active Directory pomocí Centra pro správu Office 365 nebo webu Azure Portal, můžete použít k vytváření skupin uživatelů ve službě Intune.

## Filtrování zobrazení správce podle rolí
Ve filtrovaných zobrazeních skupiny můžete určit, co správce IT uvidí, na základě jeho role. Můžete taky pro jednotlivé správce IT omezit, které skupiny můžou spravovat. To může být užitečné, když:

-   Chcete, aby vaši správci IT měli možnost nasadit položky jenom u konkrétních uživatelů a zařízení
-   Chcete, aby vaši správci IT viděli jenom skupiny, které jsou pro ně relevantní

Filtrovaná zobrazení skupin pro jednotlivé správce služby můžete nakonfigurovat v konzole pro správu Intune. Podrobnosti najdete v tématu [Co potřebujete vědět, než začnete s Microsoft Intune](/intune/get-started/what-to-know-before-you-start-microsoft-intune).

Jakmile pro správce služby nastavíte filtrovaná zobrazení skupin, bude daný správce při nasazování softwaru či zásad nebo spouštění sestav moci zobrazit a vybrat pouze skupiny, které jste určili. Správce také neuvidí informace o stavu na následujících stránkách konzoly pro správu:

-   **Přehled systému**
-   **Přehled skupin**
-   **Přehled služby Endpoint Protection**
-   **Přehled výstrah**
-   **Přehled softwaru**
-   **Přehled zásad**

### Vytvoření filtrovaného zobrazení skupiny

1.  V konzole pro správu Intune zvolte **Správce** &gt; **Správa správců** &gt; **Správci služeb**.

2.  Vyberte správce služeb, pro kterého chcete vytvořit filtrované zobrazení skupiny, a klikněte na **Spravovat skupiny**.

3.  V dialogu **Vyberte skupiny, které budou viditelné pro tohoto správce služeb** přidejte skupiny, ke kterým bude moct správce služeb přistupovat, a pak klikněte na **OK**.

Jakmile filtrovaná zobrazení skupiny nastavíte, bude tento správce IT moct zobrazit a vybrat jenom vámi označené skupiny.

## Správa skupin
Po vytvoření vlastních skupin je budete moct dále spravovat podle potřeb vaší organizace.

Skupinu můžete upravit tak, že změníte její název či popis nebo členy, kteří do ní patří.

Skupinu, která už neslouží potřebám vaší organizace, můžete odstranit. Odstraněním skupiny nedojde k odstranění uživatelů, kteří do této skupiny patří.

## Další kroky
Po nastavení skupin a zásad ověřte praktický dopad vytvořeného návrhu kontrolou položek **Zamýšlená hodnota** a **Stav**.

### Kontrola návrhu

1. Vyberte jakékoli zařízení ze skupiny zařízení a projděte kategorie informací v horní části stránky.
2. Vyberte **Zásady**. Zobrazí se snímek obrazovky nastavení zásady zařízení Android podobný následujícímu.

![Příklad zásad nastavení pro Android](../media/Intune-Device-Policy-v.2.jpg)

U každé zásady je **Zamýšlená hodnota** a **Stav**. Zamýšlená hodnota je to, čeho jste při přiřazování zásady chtěli dosáhnout. Stav označuje to, čeho skutečně dosáhnete, když se zohlední všechny zásady použité u zařízení a všechna omezení a požadavky na hardware a operační systém. Tento snímek obrazovky ukazuje dva jasné příklady:

-   Možnost **Povolit jednoduchá hesla** je nastavená na **Ano**, jak ukazuje sloupec **Zamýšlená hodnota**, ale její **Stav** je **Nepoužívá se**. Důvodem je, že se na zařízeních s Androidem nepodporují jednoduchá hesla.
-   Podobně pak u tohoto zařízení není použitá rozšířená položka zásad **Nastavení e-mailu pro zařízení se systémem iOS**, protože se jedná o zařízení s Androidem.

> [!NOTE]
> Mějte na paměti, že když použijete na stejné zařízení nebo uživatele dvě zásady s různými úrovněmi omezení, v praxi se uplatní víc omezující zásada.



<!--HONumber=Sep16_HO2-->


