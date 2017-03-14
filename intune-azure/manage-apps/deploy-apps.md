---
title: "Postup přiřazení aplikací do skupin"
titleSuffix: Intune Azure preview
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
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b372d4ee505ca39a4739069e5798918ecde134ea
ms.openlocfilehash: abf45b835d13ef5fe4acb769194542611448504e
ms.lasthandoff: 02/18/2017

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
|Přiřadit aplikace jako K dispozici|Ano|Ano|
|Přiřadit aplikace jako Povinné|Ano|Ne|
|Odinstalovat aplikace|Ano|Ano|
|Koncoví uživatelé instalují dostupné aplikace z aplikace Portál společnosti.|Ano|Ne|
|Koncoví uživatelé instalují dostupné aplikace z webového Portálu společnosti.|Ano|Ano|

> [!NOTE]
> V současné době můžete přiřadit aplikace pro iOS a Android (firemní i koupené ve Storu) k zařízením, která nejsou zaregistrovaná v Intune.

## <a name="changes-to-how-you-assign-apps-to-groups-in-the-intune-preview"></a>Změny způsobu přiřazování aplikací do skupin v Intune Preview

V Intune Azure Preview se k přiřazování aplikací už nepoužívají skupiny Intune. Nyní se používají skupiny zabezpečení Azure Active Directory (Azure AD). Z tohoto důvodu budete potřebovat informace o některých změnách týkajících se způsobu, jakým přiřazování aplikací funguje, zejména pokud jste aplikace přiřadili do podřízených skupin Intune.
Nejdůležitější informací, které byste si měli všimnout, je to, že v Azure AD neexistuje koncept podřízených skupin. Některé skupiny však mohou obsahovat stejné členy. V tomto případě se chování služby Intune Classic od chování Intune Azure Preview liší. Je to znázorněno v následující tabulce:

||||||
|-|-|-|-|-|
|**Služba Intune Classic (před migrací tenanta)**|-|**Intune Azure (po dokončení migrace tenanta)**|-|**Další informace**|
|**Záměr nasazení nadřazené skupiny**|**Záměr nasazení podřízené skupiny**|**Výsledný záměr přiřazení pro společné členy předchozí nadřazené a podřízené skupiny**|**Akce pro výsledný záměr přiřazení pro členy nadřazené skupiny**|-|    
|K dispozici|Povinné|Povinné a K dispozici|K dispozici|Povinné a K dispozici znamená, že aplikace přiřazené jako povinné je možné také prohlížet v aplikaci Portál společnosti.
|Nelze použít|K dispozici|Nelze použít|Nelze použít|Alternativní řešení: Z nadřazené skupiny Intune odeberte záměr nasazení Nelze použít.
|Povinné|K dispozici|Povinné a K dispozici|Povinné|-|
|Povinné a K dispozici<sup>1</sup>|K dispozici|Povinné a K dispozici|Povinné a K dispozici|-|    
|Povinné|Nelze použít|Povinné|Povinné|-|    
|Povinné a K dispozici|Nelze použít|Povinné a K dispozici|Povinné a K dispozici|-|    
|Povinné|Odinstalace|Povinné|Povinné|-|    
|Povinné a K dispozici|Odinstalace|Povinné a K dispozici|Povinné a K dispozici|-|
<sup>1</sup> Pouze pro spravované aplikace pro App Store (iOS) platí, že pokud je přidáte do Intune a nasadíte jako Povinné, vytvoří se automaticky se záměrem Povinné i K dispozici.

Můžete provést následující akce, aby nedocházelo ke konfliktům nasazení:

1.    Pokud jste dříve nasadili aplikace do souvisejících nadřazených a podřízených skupin Intune, zvažte odebrání těchto nasazení před zahájením migrace tenanta.
2.    Odeberte podřízené skupiny z nadřazených skupin a vytvořte novou skupinu obsahující členy původní podřízené skupiny. Pak můžete vytvořit nové nasazení aplikací do této skupiny.
Poznámky: Pokud předchozí nadřazená skupina byla typu Všichni uživatelé, budete muset vytvořit novou dynamickou skupinu, která neobsahuje členy podřízené skupiny.
Pro skupiny uživatelů a zařízení musíte veškeré změny provést na portálu [Azure Portal](https://portal.azure.com/). [Klasický portál Azure Portal](https://manage.windowsazure.com/) vám umožní provádět pouze změny skupin uživatelů.


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
    - **Nelze použít** – Aplikace není nainstalovaná nebo se na Portálu společnosti nezobrazuje.
    - **Povinné** – Aplikace se nainstaluje na zařízení ve vybraných skupinách.
    - **Odinstalovat** – Aplikace se odinstaluje ze zařízení ve vybraných skupinách.
    - **K dispozici s registrací i bez ní** – Přiřadí tuto aplikaci do skupin uživatelů, jejichž zařízení nejsou zaregistrovaná v Intune. Nápovědu najdete v tabulce výše.
6. Až to budete mít, zvolte **Uložit**.

Aplikace je teď přiřazená do skupiny, kterou jste zvolili.

Informace, s kterými budete moct lépe sledovat přiřazování aplikací, najdete v článku [Jak sledovat přiřazení aplikací](monitor-apps.md).

