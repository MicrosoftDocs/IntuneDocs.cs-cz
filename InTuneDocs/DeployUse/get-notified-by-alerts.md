---
title: "Upozorňování pomocí výstrah | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 396ea714-0433-4bd5-a934-8d0b477f28e4
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e929a95d95b71e22d46e124f1a423af7046b0539
ms.openlocfilehash: f1dd166b7b1278003ac8785b8be07c29396dfe8c


---

# Upozorňování pomocí výstrah služby Microsoft Intune
Výstrahy umožňují neustále vědět, co se děje v Microsoft Intune.

Výstrahy vás můžou informovat například o následujících událostech:

-   Potíže se součástí Exchange Connector, které ovlivňují správu mobilních zařízení

-   Malware zjištěný v počítači

-   Zjištění konfliktu mezi dvěma zásadami Intune


## Jak výstrahy fungují
Výstrahy jsou generované na základě **typů výstrah**. To je sada předkonfigurovaných pravidel integrovaných do Intune. Například výstraha typu **Cloudové úložiště má 10 % volného místa nebo méně** upozorňuje na skutečnost, že v cloudu přestáváte mít dost místa pro ukládání aplikací. Jednotlivé typy výstrah můžete povolit nebo zakázat a také můžete nakonfigurovat jejich vlastnosti. Například u výše uvedeného typu výstrahy můžete nakonfigurovat:

-   **Stav:** To, jestli je tento typ výstrahy povolený nebo zakázaný.

-   **Závažnost:** Jak závažná je tato výstraha?


|Závažnost|Podrobnosti|
|--------|-------|
    |![Kritická výstraha](../media/Critical-Alert.jpg)|Označuje závažné potíže, které byste měli prozkoumat co nejdřív, například zjištění malwaru v počítači.|
    |![Upozorňující výstraha](../media/Warning-Alert.jpg)|Označuje potíže, které ještě nejsou závažné, ale mohly by se závažnými stát, když jim nebudete věnovat pozornost, například aktualizace zabezpečení čekající na instalaci.|
    |![Informativní výstraha](../media/Informational-Alert.jpg)|Označuje informace, které nejsou pro vaši práci nepostradatelné, například dostupnost nové verze součásti Exchange Connector.|

Ostatní typy výstrah můžou obsahovat různé položky, které můžete konfigurovat, například procento zařízení, které musí být konkrétními potížemi ovlivněné, aby byla vygenerovaná výstraha.

**Při splnění kritérií pro typ výstrahy se vygeneruje příslušná výstraha a zobrazí se v konzole správce Intune.**

Navíc můžete Intune nakonfigurovat tak, abyste na vytvoření výstrahy byli upozorněni.

## Konfigurace výstrah
V [konzole správce Microsoft Intune](https://manage.microsoft.com) vyberte **Správa** &gt; **Výstrahy a oznámení** a pak vyberte jednu z těchto konfiguračních úloh:

|Úloha|Popis|
|--------|---------------|
|**Typy výstrah**|Zvolte typ výstrahy, který chcete nakonfigurovat, a poté proveďte jednu z následujících akcí:<br /><br />Zvolte **Konfigurace**. V dialogovém okně **Konfigurace typu výstrahy** nakonfigurujte požadované nastavení a pak vyberte **OK**.<br /><br />**Povolit** nebo **Zakázat** výstrahy.<br /><br />Rozbalte uzel **Typ výstrahy**. Výběrem kategorie zobrazíte jen typy výstrah, které do této kategorie spadají.|
|**Příjemci**|Výběrem **Přidat** přidáte novou e-mailovou adresu, která bude dostávat nakonfigurovaná e-mailová oznámení.<br /><br />Můžete taky **upravit** nebo **odstranit** stávající příjemce.<br /><br />Pro příjem oznámení musíte taky přidat tuto e-mailovou adresu jako příjemce v části **Pravidla oznámení**.|
|**Pravidla oznámení**|Nakonfiguruje pravidla, která definují, komu se budou odesílat e-mailové výstrahy. Máte tyto možnosti:<br /><br />**Zvolit existující pravidlo** – Vyberte pravidlo a vyberte **Vybrat příjemce**. Pak můžete vybrat všechny příjemce, kteří budou obdrží e-mail, když se vygeneruje výstraha splňující toto pravidlo.<br /><br />**Vytvořit nové pravidlo** – zadejte název pravidla, vyberte kategorii a závažnost výstrahy, které se na tato pravidla vztahují, vyberte skupiny zařízení, na které se toto pravidlo vztahuje, a vyberte uživatele, kteří dostanou e-mail při vygenerování výstrahy.<br /><br />Můžete taky **povolit**, **zakázat**, **upravit**nebo **odstranit** existující pravidlo.|

## Práce s výstrahami
Následující možnosti vám pomohou při práci s výstrahami z konzoly pro správu Intune.

|Možnost|Popis|
|----------|---------------|
|**Zobrazení aktivních výstrah**|Vyberte jednu z možností:<br /><br />**Zobrazit přehled výstrah** – V pracovním prostoru **Řídicí panel** se hlavní chyby zobrazují v podokně Výstrahy. Výběrem podokna zobrazíte podrobnější informace.<br /><br />Souhrn výstrah můžete taky zobrazit na stránce **Přehled** pracovního prostoru **Výstrahy** .<br /><br />**Zobrazit všechny výstrahy** – V pracovním prostoru **Výstrahy** vyberte **Všechny výstrahy**.|
|**Zobrazení oznámení**|Vyberte jednu z možností:<br /><br />V pracovním prostoru **Řídicí panel** vyberte **Oznámení**.<br /><br />V pracovním prostoru **Výstrahy** vyberte **Všechny výstrahy** &gt; **Oznámení**.|
|**Zavření výstrahy**|V seznamu výstrah vyberte výstrahu, kterou chcete zavřít, a vyberte **Zavřít výstrahu**.<br /><br />Zavřené výstrahy jsou trvale odstraněny po 90 dnech.|
|**Znovu aktivovat zavřenou výstrahu**|V seznamu výstrah nastavte rozevírací seznam **Filtry** na **Uzavřené**.<br /><br />V seznamu uzavřených výstrah vyberte výstrahu, kterou chcete znovu aktivovat, a pak vyberte **Znovu aktivovat výstrahu**.|
Výstrahy Intune zůstanou aktivní do doby, než:

-   Problém, který způsobil výstrahu, se vyřeší.

-   Výstrahu ručně zavřete.

-   Od vygenerování výstrahy uplynulo 45 dní.

> [!TIP]
> Pokud je stejná výstraha generovaná zařízeními s různým operačním systémem, je pravděpodobné, že se v seznamu výstrah zobrazí několik verzí téže výstrahy.

### Související témata
[Monitorování a sestavy v Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


