---
title: Řešení potíží se službou Endpoint Protection v Intune – Azure | Microsoft Docs
description: Řešení problémů během používání služby Microsoft Intune Endpoint Protection.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8eddf9af16e0218733f1e0445d85ab7e0176ed27
ms.sourcegitcommit: fb2ca28ab0cf89202c935da3f9d98adcea20566d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57461414"
---
# <a name="troubleshoot-endpoint-protection-in-intune"></a>Řešení potíží se službou Endpoint Protection v Intune

Informace uvedené v tomto článku vám můžou pomoct při řešení problémů, ke kterým dochází při používání služby Endpoint Protection. [Při řešení potíží s antivirovou ochranou v programu Windows Defender si také můžete projít protokoly událostí a kódy chyb](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Pokud vám tyto informace nepomohly, můžete také [získat podporu pro Microsoft Intune](get-support.md).

### <a name="error-messages"></a>Chybové zprávy
V této části se popisují možné příčiny následujících chyb a varování a jejich řešení.

|Položka stavu|Možné příčiny|Možná řešení|
|---------------|--------------------|-----------------------|
|**Modul služby Endpoint Protection není k dispozici.**|Modul Endpoint Protection služby Intune je poškozený nebo odstraněný.|Pokud je modul Endpoint Protection služby Intune poškozený, můžete zkusit příslušný software aktualizovat nebo přeinstalovat.<br /><br />Pokud chcete vynutit okamžitou aktualizaci, zvolte v klientském softwaru Endpoint Protection **Aktualizovat** (tuto možnost najdete na hlavním panelu spravovaných počítačů).<br /><br />Pokud se modul Endpoint Protection nedá aktualizovat, musíte ho přeinstalovat.<br /><br />V seznamu nainstalovaných programů v Ovládacích panelech spravovaného počítače najděte položku **Microsoft Intune Endpoint Protection Agent** a pak tuto aplikaci odinstalujte.<br /><br />Při další synchronizaci aktualizací zjistí program Microsoft Online Management Update Manager chybějící program a v další naplánované době pro instalace ho nainstaluje znova.|
|**Služba Endpoint Protection je zakázána.**|Správce zakázal službu Intune Endpoint Protection pomocí konfiguračního profilu, nebo ji na spravovaném počítači zakázal uživatel.|Povolte službu Endpoint Protection. Viz [přidání nastavení služby Endpoint Protection](endpoint-protection-configure.md) v Intune nebo [zapnutí přístupu k prostředkům společnosti pro program Windows Defender](/intune-user-help/turn-on-defender-windows).|
|**Ochrana v reálném čase je zakázána.**|Ochranu v reálném čase zakázal správce pomocí profilu, nebo ji na spravovaném počítači zakázal uživatel.|Povolte službu Endpoint Protection. Viz [antivirová ochrana v programu Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus) v Intune nebo [zapnutí ochrany v reálném čase pro přístup k prostředkům společnosti](/intune-user-help/turn-on-defender-windows). |
|**Kontrola stahování zakázána**|Kontrolu stahování zakázal správce pomocí profilu, nebo ji na spravovaném počítači zakázal uživatel.|Povolte kontrolu. Viz [antivirová ochrana v programu Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus) v Intune nebo [zapnutí ochrany v reálném čase pro přístup k prostředkům společnosti](/intune-user-help/turn-on-defender-windows). |
|**Monitorování aktivit souborů a programů zakázáno**|Monitorování aktivit souborů a programů zakázal správce pomocí profilu, nebo ho na spravovaném počítači zakázal uživatel.|Povolte monitorování aktivit souborů a programů. Viz [antivirová ochrana v programu Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus) v Intune nebo [zapnutí ochrany v reálném čase pro přístup k prostředkům společnosti](/intune-user-help/turn-on-defender-windows). |
|**Monitorování chování zakázáno**|Monitorování chování zakázal správce pomocí profilu, nebo ho na spravovaném počítači zakázal uživatel.|Povolte monitorování chování. Viz [antivirová ochrana v programu Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus) v Intune nebo [zapnutí ochrany v reálném čase pro přístup k prostředkům společnosti](/intune-user-help/turn-on-defender-windows). |
|**Kontrola skriptů zakázána**|Kontrolu skriptů zakázal správce pomocí profilu, nebo ji na spravovaném počítači zakázal uživatel.|Povolte kontrolu skriptů. Viz [antivirová ochrana v programu Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus) v Intune nebo [zapnutí ochrany v reálném čase pro přístup k prostředkům společnosti](/intune-user-help/turn-on-defender-windows). |
|**Systém kontroly sítě zakázán**|Systém kontroly sítě zakázal správce pomocí profilu, nebo ho na spravovaném počítači zakázal uživatel.|Povolte systém kontroly sítě (NIS). Viz [antivirová ochrana v programu Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus) v Intune nebo [zapnutí ochrany v reálném čase pro přístup k prostředkům společnosti](/intune-user-help/turn-on-defender-windows). |
|**Definice malwaru nejsou aktuální.**|Počítač mohl být delší dobu odpojený od internetu a jeho definice malwaru se nejspíš ještě neaktualizovaly. Tato stavová zpráva se zobrazuje, když jsou definice malwaru na počítači staré 14 dnů a víc.|Pokud jsou definice malwaru zastaralé, můžete je aktualizovat pomocí [antivirové ochrany v programu Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus).|
|**Zpožděna úplná kontrola**|14 dnů se kompletně neudělala úplná kontrola. Může to být tím, že se počítač během úplné kontroly restartoval.|Pokud je úplná kontrola zpožděná, můžete spustit jednorázovou úplnou kontrolu nebo naplánovat úplné kontroly, které budou probíhat opakovaně. Viz [antivirová ochrana v programu Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus). |
|**Zpožděna rychlá kontrola**|14 dnů se kompletně neudělala rychlá kontrola. Může to být způsobené restartováním během rychlé kontroly.|Pokud je rychlá kontrola zpožděná, můžete spustit jednorázovou rychlou kontrolu nebo naplánovat rychlé kontroly, které budou probíhat opakovaně. Viz [antivirová ochrana v programu Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus).|
|**Je spuštěna jiná aplikace ochrany koncových bodů.**|Je spuštěná jiná aplikace ochrany koncových bodů a počítač je v pořádku.|Ve výchozím nastavení platí, že když je nainstalovaná jiná aplikace ochrany koncových bodů a Intune tuto aplikaci rozpozná, může se zařízení stát nestabilním.|

### <a name="next-steps"></a>Další postup
Pokud vám tyto informace nepomohly, můžete také [získat podporu pro Microsoft Intune](get-support.md).
