---
title: "Zadání kódů IMEI | Dokumentace Microsoftu"
description: "Microsoft Intune umožňuje správcům importovat kódy IMEI pro platformy mobilních zařízení, aby dokázali identifikovat mobilní zařízení patřící společnosti."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 51f9d7bad6a1411ff68fa94c62421e2c0a43ab5a
ms.openlocfilehash: 97bedfdd2d756ae79350496f54076c16ada64def
ms.lasthandoff: 02/25/2017


---

# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Určení podnikem vlastněných zařízení podle kódů IMEI (International Mobile Equipment Identity)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

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

    -   **Přidáním podrobností o zařízení ručně** – Zadejte kód IMEI a podrobnosti až o 15 zařízeních.

   Pole *Podrobnosti* se používá pro účely správy. Můžete sem zadat podrobnosti, které usnadní identifikaci zařízení v seznamu zařízení vlastněných společností, která jsou uvedená podle ID hardwaru. Tyto informace se neodesílají do zařízení, ale zobrazí se v konzole Intune.

2.   Vyberte **Další**.
3.  V podokně **Zkontrolovat zařízení** můžete potvrdit kódy IMEI importovaných zařízení. Můžete také rozhodnout, zda mají být při opětovném importu kódů IMEI přepsané **Podrobnosti**. Pokud chcete zachovat aktuální podrobnosti, zrušte zaškrtnutí pole **Přepsat**. Zvolením **Dokončit ** naimportujete čísla IMEI.
4.  Importované kódy IMEI a popisy se přidají do seznamu **Podle IMEI (všechny platformy)**.

> [!IMPORTANT]
> Když importujete kód IMEI zařízení s Androidem, uvědomte si, že některá zařízení s Androidem můžou mít více kódů IMEI. Pokud importujete kód IMEI, který ale není kódem IMEI, který zařízení oznámilo službě Intune, bude zařízení označené jako osobní, a ne jako firemní.

Když se zařízení s kódem IMEI zaregistruje v Intune, většinou když uživatel instaluje aplikaci Portál společnosti a dokončuje registraci, bude zařízení označeno jako majetek společnosti a zobrazí se jako zaregistrované ve skupině **Zařízení IMEI**.

>[!NOTE]
> Když organizaci v blízké budoucnosti migrujete na nový portál Azure Portal, uvidíte v této funkci změnu. V existující konzole správce Intune můžou správci přijímat přidružené podrobnosti z nahraného CSV a přepsat existující podrobnosti pro jednotlivé identifikátory hardwaru. V novém portálu Azure Portal bude možné automaticky přepsat podrobnosti pro všechny identifikátory hardwaru nebo ignorovat všechny nové podrobnosti pro existující identifikátory.

