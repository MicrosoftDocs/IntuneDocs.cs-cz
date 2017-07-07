---
title: "Nastavení zásad podmínek a ujednání"
description: "Pro skupiny uživatelů můžete nasadit podmínky a ujednání Intune a vysvětlit jim tak, jaký vliv má registrace, přístup k pracovním prostředkům a používání aplikace Portálu společnosti na zařízení a uživatele."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6edf0ac1-4f46-4543-a9e5-f484ac37e9a5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2e8028abe5f25e4a05d79ae543d3029490c01668
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="terms-and-condition-policy-settings-in-microsoft-intune"></a>Nastavení zásad podmínek a ujednání v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pro skupiny uživatelů můžete nasadit podmínky a ujednání Intune a vysvětlit jim tak, jaký vliv má registrace, přístup k pracovním prostředkům a aplikace Portál společnosti na zařízení a uživatele. Uživatelé musí podmínky použití přijmout, aby mohli pomocí Portálu společnosti zaregistrovat svoje zařízení a získat přístup k prostředkům, které potřebují k práci.

Můžete vytvořit a nasadit různé zásady obsahující různé podmínky a ujednání. Můžete také vytvořit několik verzí stejných podmínek a ujednání v různých jazycích a ty pak implementovat do svých příslušných skupin.

## <a name="create-a-terms-and-conditions-policy"></a>Vytvoření zásad podmínek a ujednání

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) klikněte na **Zásady** &gt; **Podmínky a ujednání**.

    ![Snímky obrazovky podmínek a ujednání](./media/pol-sa-terms-conditions.png)

2.  Pokud chcete vytvořit novou zásadu podmínek a ujednání, klikněte na **Přidat**.

    Můžete také **upravit** nebo **odstranit** existující zásady.

3.  Na stránce **Vytvořit podmínky a ujednání** zadejte následující informace:

    -   **Název**&mdash;Jedinečný název zásady zobrazovaný v konzole služby Intune

    -   **Popis**&mdash;Podrobnosti, které vám pomůžou identifikovat zásadu v konzole služby Intune

    -   **Nadpis**&mdash;Nadpis, který uživatelé uvidí na portálu společnosti

    -   **Text, který vysvětluje význam toho, když uživatel přijme podmínky**&mdash;Popisek týkající se přijetí podmínek a ujednání, který uživatelé uvidí. Například: „Souhlasím s podmínkami a ujednáními.“

4.  Po dokončení klikněte na **Uložit**. Nová zásada se zobrazí v uzlu **Podmínky a ujednání** pracovního prostoru **Zásady**.

## <a name="deploy-a-terms-and-conditions-policy"></a>Nasazení zásady podmínek a ujednání

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) klikněte na **Zásady** &gt; **Podmínky a ujednání**.

2.  V seznamu **Zásady podmínek a ujednání** vyberte zásadu, kterou chcete nasadit, a klikněte na **Spravovat nasazení**.

3.  V dialogovém okně **Spravovat nasazení** vyberte skupiny uživatelů, pro které chcete zásadu nasadit, a klikněte na **OK**.

    Když cíloví uživatelé použijí Portál společnosti, zobrazí se jim podmínky a ujednání služby Intune, které jste nasadili. Uživatelé tyto podmínky musí přijmout, aby mohli mít přístup k prostředkům společnosti.

## <a name="monitor-a-terms-and-conditions-policy"></a>Monitorování zásad podmínek a ujednání

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) klikněte na **Zásady** &gt; **Podmínky a ujednání**.

2.  V okně **Vytvořit novou sestavu** klikněte na **Zobrazit sestavu**. Sestava se otevře s podrobnostmi o tom, kteří uživatelé přijali podmínky a ujednání, které jste nasadili.

### <a name="updates-and-version-control-for-terms-and-conditions"></a>Aktualizace a správa verzí pro podmínky a ujednání
Při úpravách existujících zásad podmínek a ujednání můžete zvolit chování při nasazování zásad. Následující postup vám pomůže aktualizovat existující zásady podmínek a ujednání.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Práce s více verzemi podmínek a ujednání

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) klikněte na **Zásady** &gt; **Podmínky a ujednání**.

2.  Vyberte zásadu podmínek a ujednání, kterou chcete upravit, a potom klikněte na **Upravit**.

3.  Na stránce **Upravit podmínky a ujednání** proveďte veškeré požadované úpravy a pak určete, jestli tato nová verze vyžaduje, aby podmínky a ujednání přijali všichni uživatelé, nebo jestli se nová verze zobrazí jenom novým uživatelům.

    Doporučujeme zvýšit číslo verze a požadovat přijetí podmínek a ujednání vždy, když v podmínkách a ujednáních provedete významné změny. Aktuální verzi zachovejte, pokud například opravujete překlepy nebo měníte formátování.

### <a name="see-also"></a>Viz taky
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
