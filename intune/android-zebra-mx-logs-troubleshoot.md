---
title: Použití StageNow protokoly na zařízeních s Androidem Zebra v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Při použití StageNow na zařízeních s Androidem v Microsoft Intune, naleznete v tématu běžné problémy a jejich řešení. Také zjistěte, jak získat protokoly a podívejte se na příklady toho, jak číst protokoly úspěchu nebo chyby.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5edc528abf5c3cb58200e2d0511fac3220cfad11
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58395252"
---
# <a name="use-stagenow-logs-to-troubleshoot-and-see-potential-issues-on-android-zebra-devices-in-microsoft-intune"></a>Řešení potíží s pomocí StageNow protokoly a podívejte se na potenciální problémy na zařízeních s Androidem Zebra v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

V Microsoft Intune, můžete použít [ **Zebra Mobility rozšíření (MX)** ke správě zařízení s Androidem Zebra](android-zebra-mx-overview.md). Při použití Zebra zařízení, vytvořte profily v StageNow ke správě nastavení a jejich nahrávání do Intune. Intune používá aplikace StageNow aplikaci nastavení na zařízení. StageNow aplikace také vytvoří soubor protokolu podrobné na zařízení, která se používá k řešení.

Tato funkce platí pro:

- Android

Například můžete vytvořit profil v StageNow ke konfiguraci zařízení. Při vytváření profilu StageNow poslední krok generuje soubor pro test profilu. Můžete využívat tento soubor s StageNow aplikací na zařízení.

Například vytvořit profil v StageNow a testování. V Intune přidat profil StageNow a pak ji přiřaďte Zebra zařízení. Při kontrole stavu přiřazeného profilu, profil, který se zobrazuje základní stav. Chcete podrobnosti na další.

V obou těchto případech můžete získat další podrobnosti ze souboru protokolu StageNow, který se ukládá v zařízení pokaždé, když platí StageNow profilu.

Tento článek popisuje, jak číst protokoly StageNow a uvádí některé možné problémy s Zebra zařízení.

[Použití a správa zařízení Zebra s příponami Mobility Zebra](android-zebra-mx-overview.md) obsahuje další informace o této funkci.

## <a name="read-the-logs"></a>Přečtěte si protokoly

Při hledání v protokolech, dojde k chybě pokaždé, když se zobrazí `<characteristic-error>` značky. Podrobnosti o chybě jsou zapsány do `<parm-error>` značka > `desc` vlastnost.

## <a name="error-types"></a>Typy chyb

Zebra zařízení zahrnují různé zpráv o chybách úrovně:

- Zprostředkovatel kryptografických služeb není podporován na zařízení. Například zařízení není mobilní zařízení a nemá mobilní správce.
- MX nebo OSX verze se neshoduje. Jednotlivé CSP se systémovou správou verzí. Plná podpora matice, naleznete v tématu [dokumentaci společnosti Zebra](http://techdocs.zebra.com/mx/) (otevře web společnosti Zebra).
- Zařízení odesílá jiný problém nebo chyba.

## <a name="examples"></a>Příklady

Například máte následující vstupní profil:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

V protokolu je stejný jako vstupní soubor XML. Tento výstup odpovídající znamená, že profil úspěšně použila na zařízení bez chyb:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock" version="6.0">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

Například máte následující vstup:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2" >
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic type="AppMgr" version="4.2" >
        <parm name="Action" value="Install"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic>
</wap-provisioningdoc>
```

Protokol obsahuje chybu, protože obsahuje `<characteristic-error>` značky. V tomto scénáři profil pokusili instalovat balíček Android (APK), která neexistuje v zadané cestě:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2">
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic-error type="AppMgr" version="5.1" desc="missing">
        <parm-error name="Action" value="Install" desc="apk doesnot exist in the path"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic-error>
</wap-provisioningdoc>
```

## <a name="potential-issues-with-zebra-devices"></a>Možné problémy s Zebra zařízení

Tato část uvádí informace o možných problémech, které můžete narazit při používání Zebra zařízení pomocí Správce zařízení.

### <a name="android-system-webview-is-out-of-date"></a>Android System WebView je zastaralá

Když starší zařízení přihlásit pomocí aplikace portál společnosti, může se zobrazit uživatele, zprávu, že součást System WebView je zastaralá a je třeba upgradovat. Pokud má zařízení Google Play nainstalována, připojení k Internetu a vyhledat aktualizace. Pokud zařízení nemá nainstalovaný Google Play, získali aktualizovanou verzi komponenty a použít ho k zařízením. Nebo aktualizovat na nejnovější vydané Zebra operačního systému zařízení.

### <a name="management-actions-take-a-long-time"></a>Akce správy trvat dlouhou dobu

Pokud nejsou k dispozici aplikace služby Google Play, některé úlohy trvat až 8 hodin. [Aplikace portál společnosti Intune omezení pro Android](https://support.microsoft.com/help/3211588/limitations-of-intune-company-portal-app-for-android-in-china) (otevře jiný web společnosti Microsoft) může být dobrým zdrojem informací je.

### <a name="device-spoofing-suspected-shows-in-intune"></a>"Zařízení falšování podezřelý" se zobrazí v Intune

Tato chyba znamená, že Intune má podezření, že jeho model a výrobce jako Zebra zařízení hlásí bez - Zebra zařízení s Androidem.

### <a name="company-portal-app-is-older-than-minimum-required-version"></a>Aplikace portál společnosti je starší než minimální požadovaná verze

Intune může aktualizovat minimální požadovaná verze aplikace portál společnosti. Pokud Google Play není nainstalovaný na zařízení, nebude automaticky aktualizovat aplikaci portál společnosti. Pokud minimální požadovaná verze je novější než nainstalovaná verze, aplikace portál společnosti přestane fungovat. Aktualizace na nejnovější aplikaci portál společnosti pomocí [zkušební načtení před prodejem na zařízeních Zebra](android-zebra-mx-overview.md#sideload-the-company-portal-app).

## <a name="next-steps"></a>Další postup

[Zebra diskusní vývěsky](https://developer.zebra.com/community/home/discussions) (otevře Zebra pro web)

[Použití a správa zařízení Zebra s příponami Zebra nastavení mobilních zařízení v Intune](android-zebra-mx-overview.md)
