---
# required metadata

title: Seznámení se zařízeními s inventářem v Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Seznámení se zařízeními s inventářem v Microsoft Intune
Microsoft Intune umožňuje zobrazit inventář zaregistrovaných zařízení a počítačů s Windows, na kterých je spuštěn klientský software Intune.

## Co se shromažďuje ze zaregistrovaných zařízení?
Pokud chcete zobrazit inventář, který shromažďují mobilní zařízení, spusťte [Sestavy inventáře mobilních zařízení](understand-microsoft-intune-operations-by-using-reports.md). Intune shromažďuje ze zaregistrovaných zařízení následující inventář:

|Vlastnost|Shromážděno z|
|------------|-----------------------|
|**Název**|Všechna zařízení|
|**Operační systém**|Všechna zařízení|
|**Výrobce**|Všechna zařízení|
|**Model**|Všechna zařízení|
|**Kanál pro správu**|Všechna zařízení|
|**Zaregistrováno v AAD**|Všechna zařízení kromě Mac OS X|
|**Vyhovuje**|Všechna zařízení|
|**EAS aktivované**|Všechna zařízení kromě Mac OS X|
|**ID aktivace EAS**|Všechna zařízení kromě Mac OS X|
|**Čas aktivace EAS**|Všechna zařízení kromě Mac OS X|
|**Stav správy**|Všechna zařízení|
|**E-mailová adresa**|Všechna zařízení|
|**ID protokolu Exchange ActiveSync**|Všechna zařízení|
|**Zařízení s jailbreakem nebo rootem**|Pouze zařízení s iOS a Androidem|
|**Jedinečné ID zařízení**|Všechna zařízení kromě Exchange ActiveSync|
|**Sériové číslo**|Zařízení s iOS, Mac OS X, Androidem, Windows 8.1, Windows 10|
|**Celkový úložný prostor**|Zařízení s iOS, Mac OS X, Windows 8.1, Windows 10|
|**Volný úložný prostor**|Zařízení s iOS, Mac OS X, Windows 8.1, Windows 10|
|**Telefonní číslo**<br>Telefony zařazené do kategorie Podnikové jsou označeny úplným telefonním číslem, když například spustíte sestavu inventáře mobilních zařízení. Telefonní čísla vlastních zařízení zaměstnanců (BYOD) jsou maskována pomocí &#42;, zobrazují se pouze poslední 4 číslice.|Zařízení s iOS, Androidem a Windows Phone|
|**IMEI**|Zařízení s Exchange ActiveSync, iOS, Androidem a Windows Phone|
|**MEID**<br>Identifikátor mobilního zařízení|Pouze zařízení s iOS|
|**Wi-Fi MAC**|Všechna zařízení kromě Exchange ActiveSync|
|**Poskytovatel předplatného**|Pouze zařízení s iOS a Androidem|
|**Mobilní technologie**|Pouze zařízení s iOS a Androidem|
|**Pod dohledem**|Pouze zařízení s iOS|
|**Stav zámku aktivace**|Pouze zařízení s iOS|
|**Datum zápisu**|Všechna zařízení|
|**Poslední aktualizace**|Všechna zařízení|
|**Ethernetová adresa MAC**|Pouze zařízení s Mac OS X|
|**Zámek aktivace povolený**|Pouze zařízení s iOS|
|**Šifrování povolené**|Všechna zařízení|

## Co je shromažďováno z počítačů s Windows
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

### Viz také
[Monitorování a sestavy v Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=May16_HO1-->


