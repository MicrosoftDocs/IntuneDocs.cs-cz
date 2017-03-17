---
title: Migrace do skupin Azure Active Directory | Dokumentace Microsoftu
description: "Jak budou vaše skupiny migrovány z Intune do Azure AD"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 12/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 911d2887791cf16d4290c3ac5189aa44086f4603
ms.openlocfilehash: d3b4b823683196148d4fb8aa296b59c9c712e99f
ms.lasthandoff: 03/11/2017


---

# <a name="a-new-way-of-using-groups-in-intune"></a>Nový způsob používání skupin v Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vyslyšeli jsme vaše názory a měníme způsob práce se skupinami v Microsoft Intune.
V současné době probíhá migrace všech skupin Intune našich zákazníků do skupin zabezpečení služby Azure Active Directory.

Výhoda pro vás spočívá v tom, že teď budete používat stejné prostředí skupin ve všech aplikacích Enterprise Mobility + Security a Azure AD. Kromě toho budete moct použít rozhraní API prostředí PowerShell a Graph a tuto novou funkci si rozšířit a přizpůsobit.

Skupiny zabezpečení služby Azure AD podporují všechny typy nasazení Intune pro uživatele i zařízení. Kromě toho můžete používat dynamické skupiny Azure AD, které se automaticky aktualizují na základě atributů, které zadáte. Můžete například vytvořit skupinu zařízení se systémem iOS 9. Vždy, když se zaregistruje nové zařízení s iOSem 9, přidá se automaticky do této dynamické skupiny.

## <a name="when-is-this-happening"></a>Kdy k tomu dochází?

Proces migrace právě probíhá. Před jeho dokončením vám dáme vědět.
Pokud u vás už migrace proběhla, zobrazí se vám při pokusu o přístup do skupin z klasické konzole Intune zpráva podobná této:

![Zpráva, která se zobrazí, když proběhne migrace skupin.](http://i.imgur.com/72KRaXj.png)

## <a name="what-wont-be-available"></a>Co nebude k dispozici?

Některé stávající schopnosti skupin Intune nejsou v Azure AD k dispozici:

- Nemigrují se skupiny Intune **Neseskupení uživatelé** a **Neseskupená zařízení**.
- Možnost **Vyloučit konkrétní členy** ze skupiny, které aktuálně existuje v konzole Intune, na portálu Azure Portal neexistuje. Toto chování ale můžete nahradit pomocí skupiny zabezpečení Azure AD s pokročilými pravidly. Mohli byste například vytvořit pokročilé pravidlo, které zahrne do skupiny zabezpečení všechny osoby ve vašem prodejním oddělení, ale ne ty, které mají ve funkci slovo „asistent“. Toto pokročilé pravidlo bude vypadat takto: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- Skupina **Všechna zařízení spravovaná prostřednictvím protokolu Exchange ActiveSync**, která je integrovaná do konzoly Intune, se do Azure AD nemigruje. K informacím o zařízeních spravovaných přes EAS však stále máte přístup z portálu Azure Portal.
- V klasické konzole Intune nebudete moct filtrovat sestavy podle skupin.
<!--- - Custom group targeting of notification rules will not be available. ROB I took this out as I couldn't replicate the behavior. --->

## <a name="how-to-get-ready"></a>Jak se připravit

- Přečtěte si následující témata k Azure AD, kde najdete další informace o skupinách zabezpečení služby Azure AD a jak fungují:
    -  [Správa přístupu k prostředkům prostřednictvím skupin Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)
    -  [Správa skupin ve službě Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)
    -  [Vytváření pokročilých pravidel pomocí atributů](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)
- Před migrací zvažte odebrání všech skupin Intune, které už nepoužíváte.
-  Zajistěte, aby byli do role Azure AD **Správce služby Intune** přidaní všichni správci, kteří potřebují vytvářet skupiny. Nezapomeňte, že role správce služby Azure AD nemá oprávnění **Spravovat skupinu**.
-  Pokud používáte skupiny s možností **Vyloučit konkrétní členy**, zvažte, jestli by nešlo tyto skupiny upravit, aby vyloučení nebyla potřebná, nebo jestli můžete použít pokročilá pravidla v dotazu do Azure AD, abyste dosáhli stejného výsledku.


## <a name="what-happens-to-intune-groups"></a>Co se stane se skupinami Intune?

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

## <a name="what-happens-to-policies-and-apps-youve-already-deployed"></a>Co se stane se zásadami a aplikacemi, které jste už nasadili?

Zásady a aplikace jsou i nadále nasazené do skupin, stejně jako dříve. Tyto skupiny teď ovšem budete spravovat z portálu Azure Portal místo z konzoly Intune Classic.
 

