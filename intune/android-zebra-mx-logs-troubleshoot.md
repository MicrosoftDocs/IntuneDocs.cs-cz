---
title: Použití StageNow protokoly na zařízeních s Androidem Zebra v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Při použití StageNow na zařízeních s Androidem v Microsoft Intune, naleznete v tématu běžné problémy a jejich řešení. Také zjistěte, jak získat protokoly a podívejte se na příklady toho, jak číst protokoly úspěchu nebo chyby.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
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
ms.openlocfilehash: 36476820805c00cefafcd9f64dd2f08a014762c0
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490537"
---
# <a name="troubleshoot-and-see-potential-issues-on-android-zebra-devices-in-microsoft-intune"></a>Řešení potíží a podívejte se na potenciální problémy na zařízeních s Androidem Zebra v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

V Microsoft Intune, můžete použít [Zebra Mobility rozšíření (MX) ke správě zařízení s Androidem Zebra](android-zebra-mx-overview.md). Při použití Zebra zařízení, vytvořte profily v StageNow ke správě nastavení a jejich nahrávání do Intune. Intune používá aplikace StageNow aplikaci nastavení na zařízení. StageNow aplikace také vytvoří soubor protokolu podrobné na zařízení, která se používá k řešení.

Tato funkce platí pro:

- Android

Například můžete vytvořit profil v StageNow ke konfiguraci zařízení. Při vytváření profilu StageNow poslední krok generuje soubor pro test profilu. Můžete využívat tento soubor s StageNow aplikací na zařízení.

Například vytvořit profil v StageNow a testování. V Intune přidat profil StageNow a pak ji přiřaďte Zebra zařízení. Při kontrole stavu přiřazeného profilu, profil, který se zobrazuje základní stav.

V obou těchto případech můžete získat další podrobnosti ze souboru protokolu StageNow, který se ukládá v zařízení pokaždé, když platí StageNow profilu.

Některé problémy s nesouvisejí se obsah StageNow profilu a se neprojeví v protokolech.

Tento článek popisuje, jak číst protokoly StageNow a uvádí některé možné problémy s Zebra zařízení, která nemusí být zobrazí v protokolech.

[Použití a správa zařízení Zebra s příponami Mobility Zebra](android-zebra-mx-overview.md) obsahuje další informace o této funkci.

## <a name="get-the-logs"></a>Získání protokolů

### <a name="use-the-stagenow-app-on-the-device"></a>Použití StageNow aplikace na zařízení
Při testování profilu přímo pomocí StageNow v počítači, namísto použití [nasazení profilu Intune](android-zebra-mx-overview.md#step-4-create-a-device-management-profile-in-stagenow), StageNow aplikace na zařízení uloží protokoly z testu. Chcete-li získat soubor protokolu, použijte **(...)**  možnost v aplikaci StageNow na zařízení.

### <a name="get-logs-using-android-debug-bridge"></a>Získání protokolů pomocí Android Debug Bridge
Pokud chcete získat protokoly po profil, který je už nasazená s Intune, připojte zařízení k počítači s [Android Debug Bridge (adb)](https://developer.android.com/studio/command-line/adb) (otevře web pro Android).

Na zařízení protokoly se ukládají do `/sdcard/Android/data/com.microsoft.windowsintune.companyportal/files`

### <a name="get-logs-from-email"></a>Získání protokolů z e-mailu
Pokud chcete získat protokoly po profil, který je už nasazená s Intune, koncovým uživatelům může poslat e-mail přihlásí pomocí e-mailové aplikace na zařízení. Zebra zařízení otevřete aplikaci portál společnosti a [odeslat protokoly](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). Pomocí funkce Odeslat protokoly také vytvoří PowerLift incidentu ID, které můžete využít, pokud se obrátíte na podporu Microsoftu.

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

## <a name="other-potential-issues-with-zebra-devices"></a>Ostatní potenciální potíže se zařízeními Zebra

Tato část uvádí další informace o možných problémech, které se můžete setkat při používání Zebra zařízení pomocí Správce zařízení. V protokolech StageNow nezobrazují, tyto problémy.

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
