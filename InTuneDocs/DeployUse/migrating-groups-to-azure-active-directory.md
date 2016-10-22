---
title: Migrace na skupiny Azure Active Directory| Microsoft Intune
description: "Jak budou vaše skupiny migrovány z Intune do Azure AD"
keywords: 
author: nbigman
manager: angerobe
ms.date: 10/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
translationtype: Human Translation
ms.sourcegitcommit: d92c9ffe42b36770a32c28941de3c402aec9dd68
ms.openlocfilehash: 08bcc258f64e6385ae6fa648ddb8f2b5fe68942e


---

## Nový způsob správy skupin
    
Na základě vašich žádostí o jednotnou správu skupin a cílení v oblastech Enterprise Mobility a Security převádíme skupiny Intune na skupiny zabezpečení založené na Azure Active Directory. Tím se sjednotí správa skupin v rámci Intune a Azure Active Directory (Azure AD). Toto nové prostředí vás zbaví nutnosti mít v jednotlivých službách duplicitní skupiny a zajistí možnosti rozšíření prostřednictvím PowerShellu a Graphu. 

### Jak a kdy bude můj účet migrován do nového prostředí skupin?
Současní zákazníci budou nejdříve od prosince 2016 postupně migrováni. Před migrací vašich skupin dostanete upozornění. Pokud máte k migraci jakékoli otázky, obraťte se na náš tým migrace na adrese [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### Jaké nové funkce mi změna přinese?
Tady je přehled nových funkcí: 
 
-    Skupiny zabezpečení služby Azure AD budou v Intune podporované pro všechny typy nasazení. 
-    Skupiny zabezpečení služby Azure AD budou podporovat seskupování zařízení (vedle uživatelů).
-    Skupiny zabezpečení služby Azure AD budou podporovat dynamické skupiny s atributy zařízení z Intune. Například budete moci dynamicky seskupit zařízení podle platformy, například iOS. To znamená, že při registraci nového zařízení iOS ve vaší organizaci bude zařízení automaticky přidáno do dynamické skupiny zařízení iOS.
-    Sjednocené prostředí správy skupin v Azure AD a Intune.
- Do Azure AD bude přidána *role Správce služby Intune*, aby správci služby Intune mohli provádět úlohy správy skupin v Azure AD.

 
### Které funkce Intune přestanou být dostupné?
Ačkoli se prostředí správy skupin zlepší, po migraci přestanou být dostupné některé současné funkce Intune.

#### Funkce správy skupin

-   Při vytváření nové skupiny nebude možné vyloučit členy nebo skupiny. Funkce dynamických skupin Azure AD vám ale umožní použít atributy k vytvoření rozšířených pravidel vylučujících členy na základě kritérií. Můžete například vytvořit rozšířené pravidlo, které do jedné skupiny zahrne všechny členy vašeho prodejního oddělení, kromě těch, kteří mají v pracovním titulu slovo „Assistant“. Toto pravidlo by vypadalo takto: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`. Další informace najdete v článku [Vytváření rozšířených pravidel pomocí atributů](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-   Nebudou podporované skupiny **Neseskupení uživatelé** a **Neseskupená zařízení**. Tyto skupiny nebudou migrovány.

#### Funkce závislé na konkrétních skupinách

-   Role Správce služby nebude mít oprávnění **Správa skupin**.
-   Nebude možné vytvořit skupinu zařízení Exchange ActiveSync.  Vaše skupina **všech zařízení spravovaných pomocí EAS** bude ze skupiny převedena na zobrazení sestavy.
-  Přesun skupin v sestavách nebude dostupný.
-  Vlastní pravidla cílení oznámení na skupiny nebudou dostupná.

### Jak se mám na tyto změny připravit?
 Máme několik doporučení, která vám tento přechod usnadní:
 
- Před migrací odstraňte všechny nežádoucí nebo nepotřebné skupiny Intune.
- Použití vyloučení ve skupinách vždy pečlivě zvažte. Obecně bývá vhodnější skupiny přepracovat tak, abyste vyloučení použít nemuseli, případně abyste stejného účelu dosáhli pomocí rozšířených pravidel.
-  Pokud máte správce, kteří nemají oprávnění k vytváření skupin ve službě Azure AD, požádejte správce Azure AD o jejich přidání do role **Správce služby Intune** v Azure AD.

Také můžete zjistit bližší informace o skupinách zabezpečení služby Azure AD:
-  Přehled najdete v článku [Správa přístupu k prostředkům pomocí skupin Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
-  Informace, jak vytvářet a spravovat skupiny Azure AD, najdete v článku [Správa skupin ve službě Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
-  Další informace o rozšířených pravidlech pro skupiny zabezpečení najdete v článku [Používání atributů k vytváření pokročilých pravidel](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).

> [!NOTE]
Můžete si všimnout, že dokumentace skupiny zabezpečení služby Azure AD se nezabývá vytvářením skupin pro zařízení. Tato funkce bude ve službě Azure AD aktivována ještě předtím, než začne migrace skupin Intune.

## Informace o migraci
Zde uvádíme podrobnější informace, jak budou skupiny Intune migrovány na skupiny zabezpečení služby Azure AD.

### Migrace existujících skupin

| Skupina Intune se stává...|...skupinou zabezpečení služby Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statické skupiny uživatelů, které jsou cílem zásad Intune|Statické skupiny zabezpečení služby Azure AD obsahující stejné uživatele|
|Dynamické skupiny uživatelů, které jsou cílem zásad Intune|Statické skupiny zabezpečení služby Azure AD s hierarchií skupiny zabezpečení služby Azure AD|
|Statické skupiny zařízení, které jsou cílem zásad Intune|Statické skupiny zabezpečení služby Azure AD se zařízeními|
|Dynamické skupiny zařízení s atributy zařízení, které jsou cílem zásad Intune|Dynamické skupiny zabezpečení služby Azure AD s atributy zařízení|
|Skupina s podmínkou zahrnutí|Samostatná statická skupina zabezpečení služby Azure AD, která bude obsahovat skupinu + jakékoli další statické či dynamické členy, které podmínka zahrnutí v Intune povolila|
|Skupina s podmínkou vyloučení|...nebude migrována. Při vytváření statických skupin ve službě Azure AD nejsou podmínky vyloučení podporovány. Podmínku vyloučení je možné použít při vytváření dynamické skupiny ve službě Azure AD.|
|Výchozí skupiny **Všichni uživatelé**, **Neseskupení uživatelé**, **Všechna zařízení**, **Neseskupená zařízení**, **Všechny počítače**, **Všechna mobilní zařízení**, **Všechna zařízení s MDM** a **Všechna zařízení s EAS**, které používáte v rámci zásad Intune  |Skupiny zabezpečení služby Azure AD. Výchozí skupiny, které nejsou používány, by měl zákazník vytvořit, pokud potřebuje používat dynamické skupiny.|

### Změny v hierarchických zobrazeních
Hierarchické zobrazení skupin v Intune, kde se nadřazené a podřízené skupiny řídily vztahem nadmnožina–podmnožina, se ve službě Azure AD nepoužívá. V podřízené skupině můžou být objekty, které se v nadřazené skupině nenacházejí. Skupiny ve službě Azure AD také mohou být cyklické povahy – nadřazená skupina může být podřízená své podřízené skupině.

### Konverze atributů během migrace
Atributy jsou vlastnosti zařízení, které se dají použít při definování skupin. Tato tabulka popisuje, jak budou tato kritéria migrována na skupiny zabezpečení služby Azure AD.

| Atribut Intune|Atribut Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Atribut OU (organizační jednotky) pro skupiny zařízení|Atribut OU pro dynamické skupiny. Hodnoty atributů jsou zpřístupněné správci vztahujícímu se ke každému tenantovi tak, že jsou přidány jako jedna z tenantových komponent pro zobrazení.|
|Atribut názvu domény pro skupiny zařízení|Atribut názvu domény pro dynamické skupiny. Hodnoty atributů jsou zpřístupněné správci vztahujícímu se ke každému tenantovi tak, že jsou přidány jako jedna z tenantových komponent pro zobrazení|
|Skupina zabezpečení jako atribut pro skupiny uživatelů|Skupiny nemohou být atributy v dynamických dotazech služby Azure AD. Dynamické skupiny mohou obsahovat pouze atributy specifické pro uživatele nebo zařízení.|
|Atribut Manager pro skupiny uživatelů|Rozšířené pravidlo pro atribut *manager* v dynamických skupinách|
|Všichni uživatelé z nadřazené skupiny uživatelů|Statická skupina s touto skupinou jako členem|
|Všechna mobilní zařízení z nadřazené skupiny zařízení|Statická skupina s touto skupinou jako členem|
|Všechna mobilní zařízení spravovaná přes přímou správu Microsoft Intune|Atribut Management Type s MDM jako hodnotou pro dynamickou skupinu|
|Veškerá mobilní zařízení spravovaná EAS|Zařízení EAS se nedají v Azure AD seskupit. Vaše skupina **všech zařízení spravovaných pomocí EAS** bude ze skupiny převedena na zobrazení sestavy.|
|Vnořené skupiny v rámci statických skupin |Vnořené skupiny v rámci statických skupin|
|Vnořené skupiny v rámci dynamických skupin|Dynamická skupina s jednou úrovní vnoření|


## Migrace zásad
Zatímco bude probíhat migrace skupin, v konzole Intune budete moci i nadále spravovat své zásady. Konzola Intune bude obsahovat odkaz na konzolu správy služby Azure, kde budete moci spravovat své skupiny. Vaše zásady budou i nadále nasazovány do migrovaných skupin zabezpečení služby Azure AD, které budou fungovat stejně jako vaše staré skupiny Intune.

Až budou veškeré funkce Intune migrovány na portál správy služby Azure (zhruba v prvním čtvrtletí 2017), budete moci své zásady a skupiny spravovat zde.

     
### Viz taky
[Správa přístupu k prostředkům pomocí skupin Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)

[Správa skupin v Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)

[Vytváření rozšířených pravidel pomocí atributů](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)



<!--HONumber=Oct16_HO2-->


