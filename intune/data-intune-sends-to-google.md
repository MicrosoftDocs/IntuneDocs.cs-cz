---
title: "Data z Intune odesílaná Googlu"
titleSuffix: Microsoft Intune
description: "Seznam dat, která Intune odesílá Googlu"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 63f1b07d13daad7512dff8e53f9acbafa7bffdd3
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/17/2018
---
# <a name="data-intune-sends-to-google"></a>Data z Intune odesílaná Googlu

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pokud se na zařízení povolí správa zařízení s Androidem, Microsoft Intune naváže spojení s Googlem a bude s ním sdílet informace o uživateli a o zařízení: Aby mohla služba Microsoft Intune navázat spojení, je napřed nutné vytvořit účet Google.

Následující tabulka uvádí data, která Microsoft Intune odesílá do Googlu, když je na daném zařízení povolená správa zařízení:


| Data odesílaná Googlu | Podrobnosti | Používáno pro | Příklad |
|:---:|:---:|:---:|:---:|
| EnterpriseId | Vytvoří se v Googlu po vytvoření vazby účtu Gmail s Intune. | Primární identifikátor používaný ke komunikaci mezi Intune a Googlem.  Tato komunikace zahrnuje nastavení zásad, správu zařízení a vytvoření nebo zrušení vazby Androidu s Intune. | Jedinečný identifikátor, příklad formátu: LC04eik8a6 |
| Text zásad | Vytvoří se v Intune při ukládání nových zásad aplikací nebo konfigurace. | Přiřazení zásad pro zařízení | Jde o kolekci všech nakonfigurovaných nastavení pro zásady aplikace nebo konfigurace. Může obsahovat informace o zákaznících, pokud se poskytly v rámci zásad, například názvy sítí, názvy aplikací a nastavení pro konkrétní aplikace. |
| Data zařízení | U zařízení pro scénáře s pracovními profily se začíná registrací do Intune. U zařízení pro scénáře se spravovanými zařízeními se začíná registrací v Googlu. | Informace o datech zařízení se posílají mezi Intune a Googlem při různých akcích, například při použití zásad, při správě zařízení a při obecném vykazování. | **Jedinečný identifikátor, který představuje název zařízení.** Příklad: enterprises/LC04ebru7b/devices/3592d971168f9ae4<br>**Jedinečný identifikátor, který představuje uživatelské jméno.** Příklad: Enterprises/LC04ebru7b/users/116838519924207449711<br>**Stav zařízení.** Příklady: Active (Aktivní), Disabled (Zakázáno), Provisioning (Zřizuje se).<br>**Stavy dodržování předpisů.** Příklady: Nastavení není podporováno, chybí požadované aplikace<br>**Informace o softwaru.** Příklady: verze softwaru a úroveň oprav.<br>**Informace o síti.** Příklady: IMEI, MEID, WifiMacAddress<br>**Nastavení zařízení.** Příklady: Informace o úrovních šifrování a o tom, jestli zařízení povoluje neznámé aplikace.<br> Příklad zprávy JSON najdete níže. |
| newPassword | Vytvoří se v Intune. | Resetuje heslo zařízení. | Řetězec představující nové heslo. |
| Uživatel Googlu | Google | Spravuje pracovní profil pro scénáře s pracovními profily (BYOD). | Jedinečný identifikátor, který představuje propojený účet Gmail. Příklad: 114223373813435875042 |
| Data aplikací | Vytvoří se v Intune při ukládání zásad aplikací. |  | Řetězec názvu aplikace. Příklad: app:com.microsoft.windowsintune.companyportal |
| Účet služby Enterprise | Vytvoří se v Googlu na žádost služby Intune. | Používá se u transakcí zahrnujících daného zákazníka pro ověřování mezi Intune a Googlem. | Má několik částí:<br> **Enterprise Id**: Bylo už popsáno.<br>**UPN**: Vygenerovaný hlavní název uživatele (UPN), který se používá při ověřování jménem zákazníka.<br>Příklad: w49d77900526190e26708c31c9e8a0@pfwp-commicrosoftonedfmdm2.google.com.iam.gserviceaccount.com<br>**Key**: Objekt blob s kódováním Base64, který se používá v žádostech o ověření, je uložený jako šifrovaný v této službě a vypadá takto:<br> Jedinečný identifikátor, který představuje klíč zákazníka.<br>Příklad: a70d4d53eefbd781ce7ad6a6495c65eb15e74f1f |

**Příklad dat zařízení**

Zde je ukázková zpráva zařízení JSON z Googlu:



```
'{
  "name": "enterprises/LC02dhxx1r/devices/3195483be017acdc",
  "userId": "114223373813435875042",
  "adminType": "DEVICE_OWNER",
  "state": "ACTIVE",
  "appliedState": "ACTIVE",
  "policyCompliant": true,
  "enrollmentTime": "2017-10-06T15:17:41.702Z",
  "lastStatusReportTime": "2017-10-06T15:18:10.325Z",
  "lastPolicyComplianceReportTime": "2017-10-06T15:18:11.665Z",
  "lastPolicySyncTime": "2017-10-06T15:18:07.852Z",
  "appliedPolicyVersion": "2",
  "apiLevel": 26,
  "enrollmentTokenData": "brew 30 day token",
  "enrollmentTokenId": "yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs",
  "softwareInfo": {
    "androidVersion": "8.0.0",
    "cloudDpcVersionCode": 55314,
    "cloudDpcVersionName": "bv00553-rc14",
    "androidBuildNumber": "OPR4.170623.009",
    "deviceKernelVersion": "3.10.73-ga51b1600b7f8",
    "bootloaderVersion": "BHZ21c",
    "androidBuildTime": "2017-08-28T18:57:48Z",
    "securityPatchLevel": "2017-10-05",
    "androidBuildType": "user",
    "buildUser": "android-build"
  },
  "hardwareInfo": {
    "brand": "google",
    "hardware": "bullhead",
    "deviceBasebandVersion": "M8994F-2.6.39.3.03",
    "manufacturer": "LGE",
    "serialNumber": "01ed07873b3c20cd",
    "model": "Nexus 5X",
    "batteryShutdownTemperatures": [60.0],
    "batteryThrottlingTemperatures": [-3.4028235E38],
    "cpuShutdownTemperatures": [115.0, 115.0, 115.0, 115.0, 115.0, 115.0],
    "cpuThrottlingTemperatures": [60.0, 60.0, 60.0, 60.0, 60.0, 60.0],
    "gpuShutdownTemperatures": [-3.4028235E38],
    "gpuThrottlingTemperatures": [-3.4028235E38],
    "skinShutdownTemperatures": [-3.4028235E38],
    "skinThrottlingTemperatures": [37.0]
  },
  "displays": [{
    "name": "Built-in Screen",
    "refreshRate": 60,
    "state": "ON",
    "width": 1080,
    "height": 1920,
    "density": 420
  }],
  "appliedPolicyName": "enterprises/LC02dhxx1r/policies/default",
  "networkInfo": {
    "imei": "353626070676775",
    "wifiMacAddress": "02:00:00:00:00:00"
  },
  "memoryInfo": {
    "totalRam": "1902936064",
    "totalInternalStorage": "3169611776"
  },
  "memoryEvents": [{
    "eventType": "EXTERNAL_STORAGE_DETECTED",
    "createTime": "2017-10-06T15:18:09.959Z",
    "byteCount": "26720919552"
  }],
  "powerManagementEvents": [{
    "eventType": "BATTERY_LEVEL_COLLECTED",
    "createTime": "2017-10-06T15:18:09.939Z",
    "batteryLevel": 95.0
  }],
  "userName": "enterprises/LC02dhxx1r/users/114223373813435875042",
  "enrollmentTokenName": "enterprises/LC02dhxx1r/enrollmentTokens/yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs"
}'
```

Pokud chcete ukončit používání správy zařízení s Androidem v Microsoft Intune a odstranit data, je nutné deaktivovat správu zařízení s Androidem v Intune a také odstranit váš účet Google. Vyhledejte si v účtu Google postup pro správu účtu.


