---
title: "Zadání kódů IMEI | Microsoft Intune"
description: "Microsoft Intune umožňuje správcům importovat kódy IMEI pro platformy mobilních zařízení, aby dokázali identifikovat mobilní zařízení patřící společnosti."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 289e6019aa1a17deb91b38ed32f0432af0902a9d
ms.openlocfilehash: 14ba34d46df4b4ff9de4427800b146e383f8a3d2


---

# <a name="specify-corporateowned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Určení podnikem vlastněných zařízení podle kódů IMEI (International Mobile Equipment Identity)
Microsoft Intune umožňuje správcům importovat kódy IMEI (International Mobile Equipment Identity) pro platformy mobilních zařízení, aby pomocí těchto kódů mohli identifikovat mobilní zařízení patřící společnosti. Po registraci zařízení v Intune se můžete na zařízení s importovanými kódy IMEI podívat v části **Skupiny** > **Přehled** > **Všechna zařízení**. Zařízení s importovanými kódy IMEI mají v seznamu **Skupina zařízení** ve sloupci **Vlastnictví** údaj **Firemní**.

1. V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) zvolte **Skupiny** &gt; **Všechna zařízení** &gt; **Firemní předregistrovaná zařízení ** &gt; **Podle IMEI (všechny platformy)** a pak zvolte **Přidat zařízení**. Zařízení můžete přidat dvěma způsoby:

    -   **Nahráním souboru .csv se sériovými čísly** – Vytvořte seznam oddělený čárkami (.csv), který bude mít dva sloupce, a nebude mít záhlaví. Soubor .csv může obsahovat maximálně 5000 zařízení, ale jeho velikost nesmí překročit 5 MB.

        |||
        |-|-|
        |&lt;IMEI č. 1&gt;|&lt;Podrobnosti o zařízení č. 1&gt;|
        |&lt;IMEI č. 2&gt;|&lt;Podrobnosti o zařízení č. 2&gt;|
        V textovém editoru vypadá soubor .csv takhle:

        ```
        AABBBBBBCCCCCCD,PO 1234
        AABBBBBBCCCCCCE,PO 1234
        ```

    -   **Přidáním podrobností o zařízení ručně** – Zadejte kód IMEI a podrobnosti až o pěti zařízeních.

   *Podrobnosti * jsou pro účely správy, abyste mohli zjistit, jaký kód IMEI je zařízení přiřazený. Tyto informace se neodesílají do zařízení, ale zobrazí se v konzole Intune.

2.   Vyberte **Další**.
3.  V podokně **Zkontrolovat zařízení** můžete potvrdit kódy IMEI importovaných zařízení. Můžete také rozhodnout, zda mají být při opětovném importu kódů IMEI přepsané **Podrobnosti**. Pokud chcete zachovat aktuální podrobnosti, zrušte zaškrtnutí pole **Přepsat**. Zvolením **Dokončit ** naimportujete čísla IMEI.
4.  Importované kódy IMEI a popisy se přidají do seznamu **Podle IMEI (všechny platformy)**.

Když se zařízení s kódem IMEI zaregistruje v Intune, většinou když uživatel instaluje aplikaci Portál společnosti a dokončuje registraci, bude zařízení označeno jako majetek společnosti a zobrazí se jako zaregistrované ve skupině **Zařízení IMEI**.



<!--HONumber=Nov16_HO1-->


