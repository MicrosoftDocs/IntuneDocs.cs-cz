---
title: Určení podnikem vlastněných zařízení podle kódů IMEI (International Mobile Equipment Identity)
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
author: NathBarn
---
# Určení podnikem vlastněných zařízení podle kódů IMEI (International Mobile Equipment Identity)
Microsoft Intune umožňuje správcům importovat identifikační kódy IMEI (International Mobile Equipment Identity) pro platformy mobilních zařízení vybavených kódy IMEI. Ty jim pomůžou identifikovat mobilní zařízení patřící společnosti. Po registraci do Intune jsou zařízení s importovanými kódy IMEI označená jako firemní. Tato informace se dá využít k uplatnění zásad, které se liší od zásad používaných na soukromých zařízeních.
## Přidání kódů IMEI (International Mobile Equipment Identity) do Intune
1. V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Skupiny** &gt; **Všechna zařízení** &gt; **Všechna zařízení ve vlastnictví firmy** &gt; **Podle kódu IMEI (všechny platformy)** a klikněte na **Přidat zařízení…**. Zařízení můžete přidat dvěma způsoby:

    -   **Odesláním souboru CSV se sériovými čísly** – Vytvořte seznam oddělený čárkami (.csv), který bude mít dva sloupce a bude bez záhlaví. Soubor může obsahovat maximálně 5000 zařízení a nesmí být větší než 5 MB.

        |||
        |-|-|
        |&lt;IMEI č.1&gt;|&lt;Podrobnosti o zařízení č. 1&gt;|
        |&lt;IMEI č.2&gt;|&lt;Podrobnosti o zařízení č. 2&gt;|
        V textovém editoru vypadá soubor .csv takhle:

        ```
        AA-BBBBBB-CCCCCC-D,PO 1234
        AA-BBBBBB-CCCCCC-E,PO 1234
        ```

    -   **Ručním přidáním podrobností o zařízeních** – Zadejte kód IMEI a podrobnosti až o pěti zařízeních.

   *Podrobnosti * jsou určené pro administrativní použití, aby bylo možné určit, který kód IMEI je přiřazený k zařízení. Tyto informace se neodesílají do zařízení, ale zobrazí se v konzole Intune. 

2.   Klikněte na **Další**.
3.  V podokně **Zkontrolovat zařízení** můžete potvrdit, které kódy IMEI zařízení se importují. Můžete také rozhodnout, zda mají být při opětovném importu kódů IMEI přepsané **Podrobnosti**. Pokud chcete zachovat aktuální podrobnosti, můžete zrušit zaškrtnutí pole **Přepsat**. Kliknutím na **Dokončit ** naimportujete kódy IMEI.
4.  Přidané kódy IMEI a popisy se přidají do seznamu **Podle IMEI (všechny platformy)**. 

Při registraci zařízení s tímto kódem IMEI, nejčastěji při instalaci aplikace portálu společnosti a dokončení procesu registrace, se zařízení označí jako vlastněné firmou a zobrazí se jako registrované ve skupině **Zařízení IMEI**.



<!--HONumber=Apr16_HO4-->


