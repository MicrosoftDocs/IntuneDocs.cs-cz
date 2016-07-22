---
title: "Správa výstrah | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74dc4ce4-21da-4f40-a07f-3eea34561eee
ROBOTS: noindex,nofollow
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f33a86c51320c75ce74d20e0cac2b9581990ecec
ms.openlocfilehash: bfea7213f67b55807045bfd8b29fdb083b841a56


---

# Správa výstrah v Microsoft Intune
K posouzení celkového stavu zařízení ve vaší organizaci a identifikaci problémů použijte pracovní prostor **Výstrahy** v konzole správy Intune.

#### Zobrazení aktivních výstrah

1.  V konzole správce Intune proveďte jednu z těchto věcí:

    -   **Pokud chcete zobrazit obecné informace o výstrahách** včetně prvních třech výstrah a celkového počtu aktivních výstrah, klikněte na **Přehled systému**. Kliknutím na odkazy v těchto výstrahách můžete zobrazit podrobnější informace.

    -   **Pokud chcete zobrazit souhrnná data pro výstrahy**, klikněte na **Výstrahy &gt; Přehled**. Oblast **Souhrn výstrah podle typu** na stránce **Přehled výstrah** zobrazuje souhrn výstrah. Jako první jsou zobrazené kritické výstrahy. Kliknutím na odkazy v těchto výstrahách můžete zobrazit podrobnější informace.

        > [!NOTE]
        > V některých případech se typ výstrahy může na seznamu **Souhrn výstrah podle typu** zobrazovat více než jednou.
        > 
        > Na seznamu se můžou zobrazit třeba následující instance typu výstrahy Volného místa logického disku:
        > 
        > -   3 Volné místo logického disku
        > -   2 Volné místo logického disku
        > 
        > K tomuto chování dochází při vygenerování výstrahy stejného typu pro zařízení, která používají různé operační systémy. V uvedeném příkladu mohla být první instance typu výstrahy Volné místo logického disku, 3 Volné místo logického disku, vygenerovaná počítači s Windows® 7. Druhou instanci typu výstrahy Volné místo logického disku mohly vygenerovat počítače s Windows Vista®.

    -   **Pokud chcete zobrazit všechny aktivní výstrahy**, klikněte na **Výstrahy &gt; Všechny výstrahy**. Na stránce **Výstrahy** se zobrazí seznam všech aktivních výstrah s těmito sloupci:

        1.  **Název** – název typu generované výstrahy.

        2.  **Zdroj** – odkaz na zdroj výstrahy. Pokud je prahová hodnota zobrazení typu výstrahy nastavená na **Zobrazit všechny**, pak tento odkaz zobrazí jedno zařízení. Pokud je prahová hodnota zobrazení typu výstrahy nastavená na nějakou hodnotu, pak tento odkaz zobrazí seznam všech zařízení, která jsou touto výstrahou ovlivněná.

        3.  **Poslední aktualizace** – ukazuje čas poslední změny výstrahy. Pokud je výstraha zavřená, zobrazuje se čas zavření výstrahy.

        4.  **Závažnost** – určuje závažnost výstrahy

## Zobrazení výstrah na vývěsce
Výstrahy na vývěsce poskytují důležitá oznámení o službách, například nadcházející upgrade služby, údržbu nebo výpadek. Pomocí tohoto postupu můžete výstrahy na vývěsce zobrazit a spravovat.

#### Zobrazení a správa výstrah na vývěsce

1.  V konzole správce Intune klikněte na **Přehled systému**.

2.  Pokud existují důležitá oznámení týkající se služeb, jsou zobrazená v oblasti **Vývěska**.

3.  Pokud chcete výstrahu na vývěsce exportovat do souboru s hodnotami oddělenými čárkou (CSV) nebo souboru HTML, v konzole správy Intune klikněte na **Výstrahy &gt; Všechny výstrahy &gt; Sdělení**. Vyberte oznámení, klikněte na ikonu exportování seznamu a pak postupujte podle pokynů.

## Kontrola stavů služby Intune
V pracovním prostoru **Přehled systému** si můžete zobrazit souhrny Stavu systému pro službu Endpoint Protection, aktualizace, stav agenta, zásady a software, abyste mohli identifikovat a upřednostnit problémy, které vyžadují okamžitou pozornost. Odkaz na souhrn **Stav služby** se nachází taky v chybových zprávách, když dojde k přerušení systému. Souhrn **Stav služby** zobrazuje podrobnosti o problému v každém umístění a vždy zobrazuje čas poslední aktualizace.

#### Zobrazení stavu předplatného

1.  V konzole správce Intune klikněte na **Přehled systému**.

2.  V **oblasti Stav systému** můžete zkontrolovat stav různých součástí Microsoft Intune. Mnoho položek obsahuje odkazy, které umožňují zobrazit další informace. Třeba v části **Endpoint Protection** můžete výběrem počtu instancí zobrazit pracovní prostor **Endpoint Protection** se seznamem zjištěného malwaru. Výběrem počtu zařízení zobrazíte pracovní prostor **Skupiny** se seznamem zařízení, na kterých byl zjištěn malware.

## Zavření a opětovná aktivace výstrah
Výstrahy Intune zůstávají aktivní, dokud nenastane některá z následujících událostí:

-   Problém, který způsobil vygenerování výstrahy, se vyřeší.

-   Výstrahu ručně zavřete.

-   Uplyne 5 dnů od vygenerovaní výstrahy. Po 45 dnech vyprší platnost výstrahy a ta se automaticky zavře.

Výstrahy, které jsou označené jako zavřené, se po 90 dnech trvale odstraní.

#### Ruční zavření výstrahy

1.  V konzole správce Intune proveďte jednu z těchto věcí:

    1.  **Zavření výstrahy ze seznamu výstrah** – klikněte na **Výstrahy &gt; Všechny výstrahy**. Vyberte výstrahu a pak klikněte na **Zavřít výstrahu**.

    2.  **Zavření výstrahy pro konkrétní zařízení** – klikněte na **Skupiny &gt; Všechna zařízení**. Vyberte zařízení a klikněte na **Zobrazit vlastnosti**. Pak na kartě **Výstrahy** vyberte výstrahu a klikněte na **Zavřít výstrahu**.

    3.  **Zavření výstrahy na vývěsce** – klikněte na **Přehled systému**. Klikněte na **X** vedle výstrahy na vývěsce.

#### Zobrazení a opětovná aktivace zavřené výstrahy

1.  V konzole správce Intune klikněte na **Výstrahy&gt; Všechny výstrahy**.

2.  V seznamu **Filtry** klikněte na **Zavřené**.

    V podokně seznamu pro správu se zobrazí názvy a další informace o výstrahách. Podrobnosti o zvolené výstraze se zobrazí v podokně náhledu.

3.  Pokud chcete vybranou výstrahu znovu aktivovat, klikněte na **Znovu aktivovat výstrahu**.

### Související témata
[Upozorňování pomocí výstrah služby Microsoft Intune](get-notified-by-alerts.md)




<!--HONumber=Jun16_HO4-->


