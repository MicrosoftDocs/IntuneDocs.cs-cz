---
title: "Seznámení se zařízeními s inventářem | Dokumentace Microsoftu"
description: "Použijte Intune k zobrazení informací o hardwaru zařízení, která spravujete."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 3ae5809f8506e2255d9443d3587f2564bc863066


---

# <a name="understand-your-devices-with-inventory-in-microsoft-intune"></a>Seznámení se zařízeními s inventářem v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune umožňuje zobrazit inventář zaregistrovaných zařízení a počítačů s Windows, na kterých je spuštěn klientský software Intune.
Intune obvykle shromažďuje inventář ze spravovaných zařízení každých 7 dní. Z tohoto důvodu může dojít ke zpoždění, než sestavy ukážou výsledky nedávných změn, ke kterým na zařízeních došlo, například ke změně názvu zařízení nebo změně volného úložného prostoru.

## <a name="whats-collected-from-enrolled-devices"></a>Co se shromažďuje ze zaregistrovaných zařízení?
Pokud chcete zobrazit inventář, který shromažďují mobilní zařízení, spusťte [Sestavy inventáře mobilních zařízení](understand-microsoft-intune-operations-by-using-reports.md). Intune shromažďuje ze zaregistrovaných zařízení následující inventář:

|Vlastnost|Shromážděno z|
|------------|-----------------------|
|**Název**|Všechna zařízení|
|**Operační systém**|Všechna zařízení|
|**Výrobce**|Všechna zařízení|
|**Model**|Všechna zařízení|
|**Kanál pro správu**|Všechna zařízení|
|**Zaregistrováno v AAD**|Všechna zařízení kromě Mac OS X|
|**Kompatibilní:**|Všechna zařízení|
|**EAS aktivované**|Všechna zařízení kromě Mac OS X|
|**ID aktivace EAS**|Všechna zařízení kromě Mac OS X|
|**Čas aktivace EAS**|Všechna zařízení kromě Mac OS X|
|**Stav správy**|Všechna zařízení|
|**E-mailová adresa**|Všechna zařízení|
|**ID protokolu Exchange ActiveSync**|Všechna zařízení|
|**Zařízení s jailbreakem nebo rootem**|Pouze zařízení s iOSem a Androidem|
|**Jedinečné ID zařízení**|Všechna zařízení kromě Exchange ActiveSync|
|**Sériové číslo**|Zařízení s iOSem, Mac OS X, Androidem, Windows 8.1 a Windows 10 pro počítače|
|**Celkový úložný prostor**|Zařízení s iOSem, Mac OS X, Androidem, Windows 8.1 a Windows 10 pro počítače a mobily|
|**Volný úložný prostor**|Zařízení s iOSem, Mac OS X, Windows 8.1 a Windows 10 pro počítače|
|**Telefonní číslo**<br>Telefony zařazené do kategorie Podnikové jsou identifikovány úplným telefonním číslem (například když spustíte sestavu inventáře mobilních zařízení). Telefonní čísla vlastních zařízení zaměstnanců (BYOD) jsou maskována pomocí znaků &#42;, zobrazují se pouze poslední 4 číslice.|Zařízení s iOS, Androidem a Windows Phone|
|**IMEI**|Zařízení s Exchange ActiveSync, iOS, Androidem a Windows Phone|
|**MEID**<br>Identifikátor mobilního zařízení|Pouze zařízení s iOS|
|**Wi-Fi MAC**|Všechna zařízení kromě Exchange ActiveSync|
|**Poskytovatel předplatného**|Pouze zařízení s iOSem a Androidem|
|**Mobilní technologie**|Pouze zařízení s iOSem a Androidem|
|**Pod dohledem**|Pouze zařízení s iOS|
|**Stav zámku aktivace**|Pouze zařízení s iOS|
|**Datum zápisu**|Všechna zařízení|
|**Poslední aktualizace**|Všechna zařízení|
|**Ethernetová adresa MAC**|Pouze zařízení s Mac OS X|
|**Zámek aktivace povolený**|Pouze zařízení s iOS|
|**Šifrování povolené**|Všechna zařízení|

## <a name="whats-collected-from-windows-pcs"></a>Co je shromažďováno z počítačů s Windows?
> [!IMPORTANT]
> Tato část se týká pouze počítačů s Windows, na kterých je spuštěn klientský software Windows PC Intune.

Chcete-li zobrazit inventář shromážděný z počítačů s Windows, spusťte [Sestavy inventáře počítačů](understand-microsoft-intune-operations-by-using-reports.md). Intune shromažďuje z počítačů s Windows následující inventář:

-   **Název**

-   **Typ skříně**

-   **Výrobce**

-   **Model**

-   **Operační systém**

-   **Verze čipu TPM**

-   **Celkové místo na disku**

-   **Využité místo na disku**

-   **Volné místo na disku**

-   **Název disku operačního systému**

-   **Místo na disku operačního systému**

-   **Volné místo na disku operačního systému**

-   **Fyzická paměť**

-   **Název procesoru**

-   **Architektura procesoru**

-   **Rychlost procesoru**

-   **IP adresa**

-   **Sériové číslo**

-   **Naposledy přihlášený uživatel**

-   **Přiřazený uživatel**

-   **Poslední aktualizace**

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->



<!--HONumber=Dec16_HO2-->

