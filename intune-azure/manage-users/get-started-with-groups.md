---
title: "Začínáme se skupinami na portálu Intune Azure Portal Preview | Dokumentace Microsoftu"
description: "Seznamte se s novinkami ohledně skupin na portálu Intune Azure Portal Preview."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 01/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 27a9c9d8269b302fa9735972056d38e7919f42b5


---

# <a name="get-started-with-groups"></a>Začínáme se skupinami

[!INCLUDE[azure preview](../includes/azure_preview.md)]

Vyslyšeli jsme vaše názory a změnili jsme způsob práce se skupinami v Microsoft Intune.
Pokud Intune používáte z portálu Azure Portal, pak se vaše skupiny Intune migrovaly do skupin zabezpečení Azure Active Directory.

Výhoda pro vás spočívá v tom, že teď budete používat stejné prostředí skupin ve všech aplikacích Enterprise Mobility + Security a Azure AD. Kromě toho budete moct použít rozhraní API prostředí PowerShell a Graph a tuto novou funkci si rozšířit a přizpůsobit.

Skupiny zabezpečení služby Azure AD podporují všechny typy nasazení Intune pro uživatele i zařízení. Kromě toho můžete používat dynamické skupiny Azure AD, které se automaticky aktualizují na základě atributů, které zadáte. Můžete například vytvořit skupinu zařízení se systémem iOS 9. Vždy, když se zaregistruje nové zařízení s iOSem 9, přidá se automaticky do této dynamické skupiny.

## <a name="what-is-not-available"></a>Co není dostupné?

Některé možnosti skupin Intune, které jste dříve možná používali, nejsou v Azure AD dostupné:

- Nejsou už dostupné skupiny Intune **Neseskupení uživatelé** a **Neseskupená zařízení**.
- Možnost **Vyloučit konkrétní členy** ze skupiny na portálu Azure Portal neexistuje. Toto chování ale můžete nahradit pomocí skupiny zabezpečení Azure AD s pokročilými pravidly. Mohli byste například vytvořit pokročilé pravidlo, které zahrne do skupiny zabezpečení všechny osoby ve vašem prodejním oddělení, ale ne ty, které mají ve funkci slovo „asistent“. Toto pokročilé pravidlo bude vypadat takto: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- Skupina **Všechna zařízení spravovaná prostřednictvím protokolu Exchange ActiveSync**, která je integrovaná do konzoly Intune, se do Azure AD nemigrovala. K informacím o zařízeních spravovaných přes EAS však stále máte přístup z portálu Azure Portal.


## <a name="how-to-get-started"></a>Jak začít?

- Přečtěte si následující témata k Azure AD, kde najdete další informace o skupinách zabezpečení služby Azure AD a jak fungují:
    -  [Správa přístupu k prostředkům prostřednictvím skupin Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)
    -  [Správa skupin ve službě Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)
    -  [Vytváření pokročilých pravidel pomocí atributů](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)
-  Zajistěte, aby byli do role Azure AD **Správce služby Intune** přidaní všichni správci, kteří potřebují vytvářet skupiny. Nezapomeňte, že role správce služby Azure AD nemá oprávnění **Spravovat skupinu**.
-  Pokud jste používali skupiny s možností **Vyloučit konkrétní členy**, zvažte, jestli by nešlo tyto skupiny upravit, aby vyloučení nebyla potřebná, nebo jestli můžete stejného výsledku dosáhnout použitím pokročilých pravidel v dotazu do Azure AD.


## <a name="what-happened-to-intune-groups"></a>Co se stalo se skupinami Intune?

| Skupiny v Intune|Skupiny v Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statická skupina uživatelů|Statická skupina zabezpečení Azure AD|
|Dynamická skupina uživatelů|Statické skupiny zabezpečení služby Azure AD s hierarchií skupiny zabezpečení služby Azure AD|
|Statická skupina zařízení|Statická skupina zabezpečení Azure AD|
|Dynamická skupina zařízení|Dynamická skupina zabezpečení Azure AD|
|Skupina s podmínkou zahrnutí|Statická skupina zabezpečení Azure AD obsahující všechny statické nebo dynamické členy z podmínky zahrnutí v Intune|
|Skupina s podmínkou vyloučení|Nemigruje se.|
|Integrované skupiny **Všichni uživatelé**, **Neseskupení uživatelé**, **Všechna zařízení**, **Neseskupená zařízení**, **Všechny počítače**, **Všechna mobilní zařízení**, **Všechna zařízení spravovaná prostřednictvím MDM** a **Všechna zařízení spravovaná prostřednictvím protokolu Exchange ActiveSync**|Skupiny zabezpečení služby Azure AD|

Všechny skupiny v Intune musí mít nadřazenou skupinu. Skupiny můžou obsahovat jenom členy ze své nadřazené skupiny. V Azure AD můžou podřízené skupiny obsahovat členy, které nadřazena skupina nemá.

Atributy jsou vlastnosti zařízení, které se dají použít při definování skupin. Tato tabulka popisuje, jak budou tato kritéria migrována na skupiny zabezpečení služby Azure AD.

| Atribut v Intune|Atribut v Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Atribut OU (organizační jednotky) pro skupiny zařízení|Atribut OU pro dynamické skupiny.|
|Atribut názvu domény pro skupiny zařízení|Atribut názvu domény pro dynamické skupiny.|
|Skupina zabezpečení jako atribut pro skupiny uživatelů|Skupiny nemohou být atributy v dynamických dotazech služby Azure AD. Dynamické skupiny mohou obsahovat pouze atributy specifické pro uživatele nebo zařízení.|
|Atribut Manager pro skupiny uživatelů|Rozšířené pravidlo pro atribut *manager* v dynamických skupinách|
|Všichni uživatelé z nadřazené skupiny uživatelů|Statická skupina s touto skupinou jako členem|
|Všechna mobilní zařízení z nadřazené skupiny zařízení|Statická skupina s touto skupinou jako členem|
|Veškerá mobilní zařízení spravovaná přes Intune|Atribut Management Type s MDM jako hodnotou pro dynamickou skupinu|
|Vnořené skupiny v rámci statických skupin |Vnořené skupiny v rámci statických skupin|
|Vnořené skupiny v rámci dynamických skupin|Dynamická skupina s jednou úrovní vnoření|

## <a name="what-happens-to-policies-and-apps-you-previously-deployed"></a>Co se stane se zásadami a aplikacemi, které jste už nasadili?

Zásady a aplikace jsou i nadále nasazené do skupin, stejně jako dříve. Tyto skupiny teď ovšem budete spravovat z portálu Azure Portal místo z konzoly Intune Classic.



<!--HONumber=Feb17_HO1-->


