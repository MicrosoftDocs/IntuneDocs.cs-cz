---
title: "Začínáme se skupinami na portálu Intune Azure Preview"
titleSuffix: Intune Azure preview
description: "Seznamte se s novinkami ohledně skupin na portálu Intune Azure Portal Preview."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angerobe
ms.date: 01/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 0b3ef70a54c5d91922cecbf07f864c94c559061e
ms.lasthandoff: 02/18/2017


---

# <a name="get-started-with-groups"></a>Začínáme se skupinami

[!INCLUDE[azure preview](../includes/azure_preview.md)]

Vyslyšeli jsme vaše názory a změnili jsme způsob práce se skupinami v Microsoft Intune.
Pokud Intune používáte z portálu Azure Portal, pak se vaše skupiny Intune migrovaly do skupin zabezpečení Azure Active Directory.

Výhoda pro vás spočívá v tom, že teď používáte stejné prostředí skupin ve všech aplikacích Enterprise Mobility + Security a Azure AD. Kromě toho budete moct použít rozhraní API prostředí PowerShell a Graph a tuto novou funkci si rozšířit a přizpůsobit.

Skupiny zabezpečení služby Azure AD podporují všechny typy nasazení Intune pro uživatele i zařízení. Kromě toho můžete používat dynamické skupiny Azure AD, které se automaticky aktualizují na základě atributů, které zadáte. Můžete například vytvořit skupinu zařízení se systémem iOS 9. Vždycky, když se zařízení se systémem iOS 9 zaregistruje, zobrazí se toto zařízení automaticky v dynamické skupině.

## <a name="what-is-not-available"></a>Co není dostupné?

Některé možnosti skupin Intune, které jste dříve možná používali, nejsou v Azure AD dostupné:

- Nejsou už dostupné skupiny Intune **Neseskupení uživatelé** a **Neseskupená zařízení**.
- Možnost **Vyloučit konkrétní členy** ze skupiny na portálu Azure Portal neexistuje. Toto chování ale můžete nahradit pomocí skupiny zabezpečení Azure AD s rozšířenými pravidly. Pokud například chcete vytvořit rozšířené pravidlo, které do skupiny zabezpečení zahrne všechny pracovníky vašeho prodejního oddělení, kromě těch, kteří mají v názvu pracovní pozice slovo asistent, můžete použít toto rozšířené pravidlo:

  `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- Skupina **Všechna zařízení spravovaná prostřednictvím protokolu Exchange ActiveSync** na konzole Intune se do Azure AD nemigrovala. K informacím o zařízeních spravovaných přes EAS však stále máte přístup z portálu Azure Portal.

## <a name="how-to-get-started"></a>Jak začít?

- Přečtěte si následující témata, kde najdete další informace o skupinách zabezpečení služby Azure AD a jak fungují:
    -  [Správa přístupu k prostředkům prostřednictvím skupin Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)
    -  [Správa skupin ve službě Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)
    -  [Vytváření pokročilých pravidel pomocí atributů](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)
-  Všechny správce, kteří potřebují vytvářet skupiny, je potřeba přidat do role Azure AD **Správce služby Intune**. Role správce služby Azure AD nemá oprávnění **Spravovat skupinu**.
-  Pokud vaše skupiny Intune použily možnost **Vyloučit konkrétní členy**, rozhodněte se, jestli chcete tyto skupiny znovu vytvořit bez vyloučení nebo jestli potřebujete rozšířená pravidla, abyste vyhověli potřebám firmy.


## <a name="what-happened-to-intune-groups"></a>Co se stalo se skupinami Intune?
Při migraci skupin z klasického portálu Intune na Azure Portal se použijí následující pravidla:

| Skupiny v Intune|Skupiny v Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statická skupina uživatelů|Statická skupina zabezpečení Azure AD|
|Dynamická skupina uživatelů|Statické skupiny zabezpečení služby Azure AD s hierarchií skupiny zabezpečení služby Azure AD|
|Statická skupina zařízení|Statická skupina zabezpečení Azure AD|
|Dynamická skupina zařízení|Dynamická skupina zabezpečení Azure AD|
|Skupina s podmínkou zahrnutí|Statická skupina zabezpečení Azure AD obsahující všechny statické nebo dynamické členy z podmínky zahrnutí v Intune|
|Skupina s podmínkou vyloučení|Nemigruje se.|
|Předdefinované skupiny:<br>- **Všichni uživatelé**<br>- **Neseskupení uživatelé**<br>- **Všechna zařízení**<br>- **Neseskupená zařízení**<br>- **Všechny počítače**<br>- **Všechna mobilní zařízení**<br>- **Všechna zařízení spravovaná přes MDM**<br>- **Všechna zařízení spravovaná přes EAS**|Skupiny zabezpečení služby Azure AD|

## <a name="group-hierarchy"></a>Hierarchie skupin

V klasické konzole Intune měly všechny skupiny nadřazenou skupinu. Skupiny mohly obsahovat jenom členy ze svojí nadřazené skupiny. V Azure AD můžou podřízené skupiny obsahovat členy, které nejsou v jejich nadřazené skupině.

## <a name="group-attributes"></a>Atributy skupin
Atributy jsou vlastnosti zařízení, které se dají použít při definování skupin. Tato tabulka popisuje, jak budou tato kritéria migrována na skupiny zabezpečení služby Azure AD.

| Atribut v Intune|Atribut v Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Atribut OU (organizační jednotky) pro skupiny zařízení|Atribut OU pro dynamické skupiny.|
|Atribut názvu domény pro skupiny zařízení|Atribut názvu domény pro dynamické skupiny.|
|Skupina zabezpečení jako atribut pro skupiny uživatelů|Skupiny nemohou být atributy v dynamických dotazech služby Azure AD. Dynamické skupiny můžou obsahovat jenom atributy specifické pro uživatele nebo zařízení.|
|Atribut Manager pro skupiny uživatelů|Rozšířené pravidlo pro atribut *manager* v dynamických skupinách|
|Všichni uživatelé z nadřazené skupiny uživatelů|Statická skupina s touto skupinou jako členem|
|Všechna mobilní zařízení z nadřazené skupiny zařízení|Statická skupina s touto skupinou jako členem|
|Veškerá mobilní zařízení spravovaná přes Intune|Atribut Management Type s MDM jako hodnotou pro dynamickou skupinu|
|Vnořené skupiny v rámci statických skupin |Vnořené skupiny v rámci statických skupin|
|Vnořené skupiny v rámci dynamických skupin|Dynamická skupina s jednou úrovní vnoření|

## <a name="what-happens-to-policies-and-apps-you-previously-deployed"></a>Co se stane se zásadami a aplikacemi, které jste už nasadili?

Zásady a aplikace jsou i nadále nasazené do skupin, stejně jako dříve. Tyto skupiny teď ovšem budete spravovat z portálu Azure Portal místo z konzoly Intune Classic.

