---
title: Nastavení podmínek a ujednání v Microsoft Intune
titlesuffix: ''
description: Nastavte si podmínky a ujednání, které uvidí uživatelé na Portálu společnosti pro Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1b0571ad6196277ee2bc257d72cc4db24fcc3424
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2019
ms.locfileid: "57237941"
---
# <a name="terms-and-conditions-for-user-access"></a>Podmínky a ujednání pro přístup uživatelů

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Správce Intune může uživatele požádat, aby před použitím Portálu společnosti přijali podmínky a ujednání společnosti, aby mohli:
- registrovat zařízení,
- přistupovat k prostředkům, jako jsou aplikace a e-mail společnosti.    
Konfigurace podmínek a ujednání je volitelná.

Můžete vytvořit více sad podmínek a přiřadit je různým skupinám, abyste například zajistili podporu různých jazyků.

Existují dva způsoby, jak vytvořit podmínky a ujednání společnosti:
- Můžete použít Intune spolu s postupem, který je popsaný v tomto článku.
- Nebo můžete použít [funkci podmínek použití v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou). Pokud chcete zjistit, jaká metoda je pro vás nejvhodnější, přečtěte si [blogový příspěvek o výběru správného řešení pro tvorbu podmínek vaší organizace](https://go.microsoft.com/fwlink/?linkid=2010506&clcid=0x409). 

## <a name="create-terms-and-conditions"></a>Vytvoření podmínek a ujednání
Pokud chcete vytvořit podmínky a ujednání, dokončete tento postup. Zobrazovaný název a popis jsou určené pro správu, zatímco vlastnosti podmínek se zobrazují uživatelům na Portálu společnosti.

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Registrace zařízení** > **Podmínky**.
2. Zvolte **Vytvořit**.
![Snímek obrazovky Azure Portalu zobrazující tlačítko Vytvořit pro podmínky a ujednání](media/terms-create-terms.png)
3. V rozbaleném podokně zadejte tyto informace:

   - **Zobrazovaný název**: Název pro podmínky na webu Azure Portal. Tento název se uživatelům nezobrazuje.

   - **Popis**: Volitelné podrobnosti, které vám pomůžou identifikovat tuto sadu podmínek na webu Azure Portal.

4. Když vyberete šipku vedle **definování podmínek použití**, otevře se podokno podmínek a ujednání, ve kterém zadejte tyto informace:

   ![Snímek obrazovky s přijetím podmínek a ujednání koncovým uživatelem se souhrnným zněním podmínek](./media/terms-summary-create.png)

   - **Název**: Název vašich podmínek, který uživatelé uvidí na portálu společnosti nad **Souhrn**.
   - **Souhrn podmínek**: Text, který vysvětluje význam toho, když uživatelé přijmou podmínky. Příklad: „Registrací svého zařízení souhlasíte s podmínkami použití stanovenými společností Contoso. Než budete pokračovat, pečlivě si podmínky prostudujte.
   - **Podmínky a ujednání**: Podmínky a ujednání, které uživatelé naleznete v tématu a musí přijmout nebo odmítnout.

5. Zvolte **OK** > **Vytvořit**.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Prohlížení podmínek, jak se zobrazují uživatelům
V následujícím příkladu je vidět **Nadpis** a **Souhrn podmínek** v konzole pro správu a na Portálu společnosti.

![Snímek obrazovky s nadpisem a souhrnem podmínek v konzole pro správu a na Portálu společnosti](./media/terms-summary-terms.png)

V následujícím příkladu jsou vidět podmínky a ujednání v konzole pro správu a na Portálu společnosti.

![Snímek obrazovky s podmínkami a ujednáními v konzole pro správu a na Portálu společnosti](./media/terms-properties-terms.png)

## <a name="assign-terms-and-conditions"></a>Přiřazení podmínek a ujednání

Podmínky a ujednání můžete přiřadit skupinám uživatelů, kteří je před použitím Portálu společnosti musí přijmout.

1. Na Azure Portalu zvolte **Registrace zařízení** a pak zvolte **Podmínky**.
2. V seznamu podmínek a ujednání zvolte podmínky, které chcete přiřadit > **Spravovat** > **Přiřazení**.
![Snímek obrazovky portálu Azure Portal s podoknem Přiřadit skupinu a tlačítky Vybrat skupinu a Vybrat pro přiřazení podmínek a ujednání](media/terms-assign-groups.png)
3. Zvolte **Vybrat skupiny, které se zahrnou** > zvolte skupiny, kterým chcete podmínky přiřadit > **Vybrat**. Podmínky a ujednání nemůžete přiřadit dynamickým skupinám.
4. V podokně **Přiřazené skupiny** zvolte **Uložit**.  Podmínky a ujednání jsou teď přiřazené uživatelům ve vybraných skupinách. Uživatelům se při příštím přístupu k portálu společnosti zobrazí výzva k přijetí podmínek. Podmínky a ujednání stačí přijmout jen jednou. Uživatelé, kteří mají několik zařízení, je nemusejí přijímat na každém z nich.


## <a name="monitor-terms-and-conditions"></a>Monitorování podmínek a ujednání

1. Na portálu Azure Portal zvolte **Všechny služby** > **Monitorování a správa** > **Intune**. 
1. V podokně Intune zvolte **Registrace zařízení** > **Podmínky**.
2. V seznamu podmínek a ujednání zvolte podmínky, u kterých chcete zobrazit jejich přijetí > **Generování sestav o přijetí**.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Práce s více verzemi podmínek a ujednání
Podmínky a ujednání můžete upravit a spravovat jejich verze. Po každé významnější změně podmínek a ujednání byste měli:
- Zvýšit číslo verze.
- Požádat uživatele o přijetí nových podmínek a ujednání. Aktuální číslo verze můžete nechat, pokud jste třeba jenom opravili překlepy nebo změnili formátování.

1. Na portálu Azure Portal zvolte **Všechny služby** > **Monitorování a správa** > **Intune**.

2. V podokně Intune zvolte **Registrace zařízení** > **Podmínky** > zvolte podmínky a ujednání, které chcete změnit > **Vlastnosti**.

4. V podokně **Vlastnosti** zvolte **Podmínky** a podle potřeby změňte **Nadpis**, **Souhrn podmínek** a **Podmínky**. Pokud je potřeba, aby provedené změny uživatelé znovu přijali jako nové podmínky, zvolte **Požaduje opětovné přijetí od uživatelů a zvýší číslo verze na**.

4.  Zvolte **OK** > **Uložit**.

Uživatelé musí přijmout aktualizované podmínky a ujednání jenom jednou. Uživatelé, kteří mají několik zařízení, je nemusejí přijímat na každém z nich.
