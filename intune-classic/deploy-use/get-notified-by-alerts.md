---
title: "Upozorňování pomocí výstrah | Dokumentace Microsoftu"
description: "Přečtěte si, jak výstrahy umožňují neustále vědět, co se děje v Microsoft Intune."
keywords: 
author: nathbarn
ms.author: angrobe
manager: angrobe
ms.date: 8/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft intune
ms.technology: 
ms.assetid: 396ea714 0433 4bd5 a934 8d0b477f28e4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune classic
ms.openlocfilehash: 7f8f914e9b7b0e2db2da3f9c8317485208d97574
ms.sourcegitcommit: 2d67df51af66ec859587b66a6ce3965461601c29
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/01/2017
---
#  <a name="use-alerts-to-get-notified-by-microsoft-intune"></a>Upozorňování pomocí výstrah služby Microsoft Intune

[!INCLUDE[classic portal](../includes/classic-portal.md)]

Výstrahy umožňují neustále vědět, co se děje v Microsoft Intune. Výstrahy vás můžou informovat například o následujících událostech:
- Potíže se součástí Exchange Connector, které ovlivňují správu mobilních zařízení
- V počítači byl zjištěný malware
- Zjištění konfliktu mezi dvěma zásadami Intune
- Nasazení softwarového klienta Intune se nezdaří

## <a name="how-alerts-work"></a>Jak výstrahy fungují

Výstrahy jsou generované na základě **typů výstrah**. To je sada předkonfigurovaných pravidel integrovaných do Intune. Například výstraha typu **Cloudové úložiště má 10 % volného místa nebo méně** upozorňuje na skutečnost, že v cloudu přestáváte mít dost místa pro ukládání aplikací. Jednotlivé typy výstrah můžete povolit nebo zakázat a také můžete nakonfigurovat jejich vlastnosti. Například u výše uvedeného typu výstrahy můžete nakonfigurovat:

- **Stav:** To, jestli je tento typ výstrahy povolený nebo zakázaný.
- **Závažnost:** Jak závažná je tato výstraha?

|Závažnost|Podrobnosti|
|--|---|
|**Kritická výstraha**|Označuje závažné potíže, které byste měli prozkoumat co nejdřív, například zjištění malwaru v počítači.|
|**Upozorňující výstraha**|Označuje potíže, které ještě nejsou závažné, ale mohly by se závažnými stát, když jim nebudete věnovat pozornost, například aktualizace zabezpečení čekající na instalaci.|
|**Informační výstraha**|Označuje informace, které nejsou pro vaši práci nepostradatelné, například dostupnost nové verze součásti Exchange Connector.|

Ostatní typy výstrah můžou mít různé konfigurovatelné položky, například procento zařízení, které musí být konkrétními potížemi ovlivněné, aby se vygenerovala výstraha.

**Při splnění kritérií pro typ výstrahy se vygeneruje příslušná výstraha a zobrazí se v konzole správce Intune.**

Navíc můžete Intune nakonfigurovat tak, abyste na vytvoření výstrahy byli upozorněni.

## <a name="set-up-alerts"></a>Nastavení výstrah

V [konzole správce Microsoft Intune](https://manage.microsoft.com) zvolte **Správa** &gt; **Výstrahy a oznámení** a pak vyberte jednu z těchto úloh:

|Úloha|Popis|
|---|------|
|**Typy výstrah**|Zvolte typ výstrahy, který chcete nakonfigurovat, a poté proveďte jednu z následujících akcí:<br /><br />Zvolte **Konfigurace**. V dialogovém okně **Konfigurace typu výstrahy** nakonfigurujte požadované nastavení a pak zvolte **OK**.<br /><br />**Povolit** nebo **Zakázat** výstrahy.<br /><br />Rozbalte uzel **Typy výstrah**. Výběrem kategorie zobrazíte jen typy výstrah, které do této kategorie spadají.|
|**Příjemci**|Výběrem **Přidat** přidáte novou e-mailovou adresu, která bude dostávat e-mailová oznámení, která nastavujete.<br /><br />Můžete taky **upravit** nebo **odstranit** stávající příjemce.<br /><br />Pro příjem oznámení musíte taky přidat tuto e-mailovou adresu jako příjemce v části **Pravidla oznámení**.|
|**Pravidla oznámení**|Nakonfiguruje pravidla, která definují, komu se budou odesílat e-mailové výstrahy. Máte tyto možnosti:<br /><br />**Vybrat existující pravidlo:** Vyberte pravidlo a pak zvolte **Vybrat příjemce**. Pak můžete vybrat všechny příjemce, kteří budou obdrží e-mail, když se vygeneruje výstraha splňující toto pravidlo.<br /><br />**Vytvořit nové pravidlo:** Zadejte název pravidla, vyberte kategorii a závažnost výstrahy, které se na tato pravidla vztahují, vyberte skupiny zařízení, na které se toto pravidlo vztahuje, a vyberte uživatele, kteří dostanou e-mail při vygenerování výstrahy.<br /><br />Můžete taky **povolit**, **zakázat**, **upravit**nebo **odstranit** existující pravidlo.|

## <a name="working-with-alerts"></a>Práce s výstrahami

Následující možnosti vám pomohou při práci s výstrahami z konzoly pro správu Intune.

|Možnost|Popis|
|-----|----|
|**Zobrazení aktivních výstrah**|Vyberte jednu z možností:<br /><br />**Zobrazit přehled výstrah:** V pracovním prostoru **Řídicí panel** se hlavní chyby zobrazují v podokně Výstrahy. Výběrem podokna zobrazíte podrobnější informace.<br /><br />Souhrn výstrah můžete taky zobrazit na stránce **Přehled** pracovního prostoru **Výstrahy** .<br /><br />**Zobrazit všechny výstrahy:** V pracovním prostoru **Výstrahy** vyberte **Všechny výstrahy**.|
|**Zobrazení oznámení**|Vyberte jednu z možností:<br /><br />V pracovním prostoru **Řídicí panel** vyberte **Oznámení**.<br /><br />V pracovním prostoru **Výstrahy** vyberte **Všechny výstrahy** &gt; **Oznámení**.|
|**Zavření výstrahy**|V seznamu výstrah vyberte výstrahu, kterou chcete zavřít, a vyberte **Zavřít výstrahu**.<br /><br />Zavřené výstrahy jsou trvale odstraněny po 90 dnech.|
|**Opětovná aktivace zavřené výstrahy**|V seznamu výstrah nastavte rozevírací seznam **Filtry** na **Uzavřené**.<br /><br />V seznamu uzavřených výstrah vyberte výstrahu, kterou chcete znovu aktivovat, a pak vyberte **Znovu aktivovat výstrahu**.|

Výstrahy Intune zůstanou aktivní do doby, než:

- Dojde k vyřešení problému, který výstrahu způsobil.
- Výstrahu ručně zavřete.
- Od vygenerování výstrahy uplynulo 45 dní.

> [!TIP]
> Pokud je stejná výstraha generovaná zařízeními s různým operačním systémem, je pravděpodobné, že se v seznamu výstrah zobrazí několik verzí téže výstrahy.