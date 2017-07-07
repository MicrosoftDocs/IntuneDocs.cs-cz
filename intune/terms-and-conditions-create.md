---
title: "Nastavení podmínek a ujednání v Microsoft Intune"
titleSuffix: Intune on Azure
description: "Nastavte si podmínky a ujednání, které uvidí uživatelé na Portálu společnosti pro Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0262b8068ddf134de5ffec0965476fb513ceb9ab
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="ensure-users-accept-company-terms-for-access"></a>Ujistěte se, že uživatelé přijmou firemní podmínky pro přístup.

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Správce Intune může od uživatelů vyžadovat, aby před použitím Portálu společnosti k registraci svých zařízení a přístupu k prostředkům společnosti, jako jsou aplikace a e-mail, přijali podmínky společnosti. Konfigurace podmínek a ujednání je volitelná.

Můžete vytvořit více sad podmínek a přiřadit je různým skupinám, abyste například zajistili podporu různých jazyků.

## <a name="create-terms-and-conditions"></a>Vytvoření podmínek a ujednání
Pokud chcete vytvořit podmínky a ujednání, dokončete tento postup. Zobrazovaný název a popis jsou určené pro správu, zatímco vlastnosti podmínek se zobrazují uživatelům na Portálu společnosti.

1. Na portálu Intune zvolte **Registrace zařízení** a pak zvolte **Podmínky**.
2. Vyberte **Vytvořit**.
![Snímek obrazovky portálu Intune zobrazující tlačítko Vytvořit pro podmínky a ujednání](media/terms-create-terms.png)
3. V rozbaleném okně zadejte následující informace:

   - **Zobrazovaný název**: Název pro podmínky na portálu Intune. Tento název se uživatelům nezobrazuje.

   - **Popis**: Volitelné podrobnosti, které vám pomůžou identifikovat tuto sadu podmínek na portálu Intune.

4. Vyberte šipku vedle Definice podmínek použití. Otevře se okno Podmínky. Potom zadejte následující informace:

   ![Snímek obrazovky s přijetím podmínek a ujednání koncovým uživatelem se souhrnným zněním podmínek](./media/terms-summary-create.png)

   - **Nadpis**: Název vašich podmínek, který uživatelé uvidí na Portálu společnosti nad **Souhrnem**.
   - **Souhrn podmínek**: Text, který vysvětluje, jaký význam má pro uživatele přijetí podmínek. Příklad:„Registrací svého zařízení souhlasíte s podmínkami použití nastavenými společností Contoso. Než budete pokračovat, pečlivě si podmínky prostudujte.
   - **Podmínky**: Podmínky, které se zobrazí uživatelům a které musí uživatelé přijmout nebo odmítnout.

5. Vyberte **OK** a pak vyberte **Vytvořit**.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Prohlížení podmínek, jak se zobrazují uživatelům
V následujícím příkladu je vidět **Nadpis** a **Souhrn podmínek** v konzole pro správu a na Portálu společnosti.

![Snímek obrazovky s nadpisem a souhrnem podmínek v konzole pro správu a na Portálu společnosti](./media/terms-summary-terms.png)

V následujícím příkladu jsou vidět podmínky a ujednání v konzole pro správu a na Portálu společnosti.

![Snímek obrazovky s podmínkami a ujednáními v konzole pro správu a na Portálu společnosti](./media/terms-properties-terms.png)

## <a name="assign-terms-and-conditions"></a>Přiřazení podmínek a ujednání

Podmínky a ujednání můžete přiřadit skupinám uživatelů, kteří je před použitím Portálu společnosti musí přijmout.

1. Na portálu Intune zvolte **Registrace zařízení** a pak zvolte **Podmínky**.
2. Podmínky, které chcete přiřadit, vyberte v seznamu podmínek a ujednání a potom vyberte **Přiřazené skupiny**.
![Snímek obrazovky portálu Intune s oknem Přiřadit skupinu a tlačítky Vybrat skupinu a Vybrat pro přiřazení podmínek a ujednání](media/terms-assign-groups.png)
3. Klikněte na tlačítko **Vybrat skupinu** a v okně **Vybrat skupiny** vyberte skupiny, kterým chcete podmínky přiřadit. Pak klikněte na **Vybrat**. Podmínky a ujednání nemůžete přiřadit dynamickým skupinám.
4. V okně **Přiřazené skupiny** klikněte na **Uložit**.  Podmínky a ujednání jsou teď přiřazené uživatelům ve vybraných skupinách. Uživatelům se při příštím přístupu k portálu společnosti zobrazí výzva k přijetí podmínek. Podmínky a ujednání stačí přijmout jenom jednou. Uživatelé, kteří mají několik zařízení, je nemusejí přijímat na každém z nich.


## <a name="monitor-terms-and-conditions"></a>Monitorování podmínek a ujednání

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**. V okně Intune zvolte **Registrace zařízení** a pak zvolte **Podmínky**.
2. V seznamu podmínek a ujednání vyberte podmínky, u kterých chcete zobrazit jejich přijetí, a pak vyberte **Stavy přijetí**.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Práce s více verzemi podmínek a ujednání
Podmínky a ujednání můžete upravit a spravovat jejich verze. Doporučujeme zvýšit číslo verze a požadovat přijetí podmínek a ujednání vždy, když v podmínkách a ujednáních provedete významné změny. Aktuální verzi zachovejte, pokud například opravujete překlepy nebo měníte formátování.

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune vyberte **Registrace zařízení**, vyberte **Podmínky**, vyberte podmínky a ujednání, které chcete upravit, a potom vyberte **Vlastnosti**.

4. V okně **Vlastnosti** vyberte **Podmínky** a potom podle potřeby změňte **Nadpis**, **Souhrn podmínek** a **Podmínky**. Pokud je potřeba, aby provedené změny uživatelé znovu přijali jako nové podmínky, klikněte na **Požaduje opětovné přijetí od uživatelů a zvýší číslo verze na**.

4.  Vyberte **OK** a pak vyberte **Uložit**.

Uživatelé musí přijmout aktualizované podmínky a ujednání jenom jednou. Uživatelé, kteří mají několik zařízení, je nemusejí přijímat na každém z nich.
