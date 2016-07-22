---
title: "Určení podnikem vlastněných zařízení podle kódů IMEI (International Mobile Equipment Identity) | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 590b8bc5a307e238ba41d32f98f6878daebf1185
ms.openlocfilehash: 7df281a3e35ac563f7b82e4b13407b413f8a7e4a


---

# Určení podnikem vlastněných zařízení podle kódů IMEI (International Mobile Equipment Identity)
Microsoft Intune umožňuje správcům importovat identifikační kódy IMEI (International Mobile Equipment Identity) pro platformy mobilních zařízení vybavených kódy IMEI. Ty jim pomůžou identifikovat mobilní zařízení patřící společnosti. Po registraci v Intune lze zařízení s importovanými čísly IMEI zobrazit v části **Skupiny** > **Přehled** > **Všechna zařízení** > **Firemní předregistrovaná zařízení** > **Podle IMEI (všechny platformy)**.

1. V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) zvolte **Skupiny** &gt; **Všechna zařízení** &gt; **Firemní předregistrovaná zařízení ** &gt; **Podle IMEI (všechny platformy)** a pak zvolte **Přidat zařízení**. Zařízení můžete přidat dvěma způsoby:

    -   **Odesláním souboru CSV se sériovými čísly** – Vytvořte seznam oddělený čárkami (.csv), který bude mít dva sloupce a bude bez záhlaví. Soubor může obsahovat maximálně 5000 zařízení a nesmí být větší než 5 MB.

        |||
        |-|-|
        |&lt;IMEI č. 1&gt;|&lt;Podrobnosti o zařízení č. 1&gt;|
        |&lt;IMEI č. 2&gt;|&lt;Podrobnosti o zařízení č. 2&gt;|
        V textovém editoru vypadá soubor .csv takhle:

        ```
        AABBBBBBCCCCCCD,PO 1234
        AABBBBBBCCCCCCE,PO 1234
        ```

    -   **Ručním přidáním podrobností o zařízeních** – Zadejte kód IMEI a podrobnosti až o pěti zařízeních.

   *Podrobnosti * jsou určené pro administrativní použití, aby bylo možné určit, který kód IMEI je přiřazený k zařízení. Tyto informace se neodesílají do zařízení, ale zobrazí se v konzole Intune.

2.   Vyberte **Další**.
3.  V podokně **Zkontrolovat zařízení** můžete potvrdit, které kódy IMEI zařízení se importují. Můžete také rozhodnout, zda mají být při opětovném importu kódů IMEI přepsané **Podrobnosti**. Pokud chcete zachovat aktuální podrobnosti, můžete zrušit zaškrtnutí pole **Přepsat**. Zvolením **Dokončit ** naimportujete čísla IMEI.
4.  Přidané kódy IMEI a popisy se přidají do seznamu **Podle IMEI (všechny platformy)**.

Při registraci zařízení s tímto kódem IMEI, nejčastěji při instalaci aplikace portálu společnosti a dokončení procesu registrace, se zařízení označí jako vlastněné firmou a zobrazí se jako registrované ve skupině **Zařízení IMEI**.



<!--HONumber=Jul16_HO3-->


