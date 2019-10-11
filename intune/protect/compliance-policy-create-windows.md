---
title: Nastavení dodržování předpisů pro Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na seznam všech nastavení, která můžete použít při nastavování dodržování předpisů pro zařízení s Windows 10, Windows holografickými a Surface Hub v Microsoft Intune. Podívejte se na dodržování předpisů pro minimální a maximální operační systém, nastavte omezení a délku hesla, vyhledejte řešení partnerů pro ochranu proti virům (AV), povolte šifrování u úložiště dat a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/10/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 493db6299aa8242d0ca6ab669b313e85d0dc14c6
ms.sourcegitcommit: b1e97211db7cb949eb39be6776b3a11d434fdab0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2019
ms.locfileid: "72251586"
---
# <a name="windows-10-and-later-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Nastavení Windows 10 a novějších označení zařízení jako kompatibilních nebo nekompatibilních s Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Tento článek obsahuje seznam a popis různých nastavení dodržování předpisů, která můžete konfigurovat v zařízeních s Windows 10 a novějším v Intune. Jako součást řešení správy mobilních zařízení (MDM) použijte Tato nastavení k vyžadování nástroje BitLocker, nastavení minimálního a maximálního operačního systému, nastavení úrovně rizika pomocí rozšířené ochrany před internetovými útoky v programu Microsoft Defender (ATP) a dalších.

Tato funkce se týká:

- Windows 10 a novější
- Windows Holografick pro firmy
- Surface Hub

Jako správce Intune můžete pomocí těchto nastavení dodržování předpisů ochránit prostředky vaší organizace. Další informace o zásadách dodržování předpisů a o tom, co dělají, najdete v tématu [Začínáme s dodržováním předpisů pro zařízení](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Než začnete

[Vytvořte zásady dodržování předpisů](create-compliance-policy.md#create-the-policy). V části **platforma**vyberte **Windows 10 a novější**.

## <a name="device-health"></a>Stav zařízení

- **Vyžadovat BitLocker**: když se nastaví na **vyžadovat**, zařízení může chránit data uložená na disku před neoprávněným přístupem, když je systém vypnutý nebo hibernace. Windows nástroj BitLocker Drive Encryption šifruje všechna data uložená na svazku operačního systému Windows. BitLocker používá čip TPM k ochraně operačního systému Windows a uživatelských dat. Pomáhá také ověřit, že počítač není úmyslně poškozen, a to ani v případě, že je jeho levý bezobslužný, ztracený nebo odcizený. Pokud je počítač vybavený kompatibilním čipem TPM, BitLocker použije čip TPM k uzamknutí šifrovacích klíčů, které chrání data. K těmto klíčům proto nelze přistupovat, dokud čip TPM neověří stav počítače.

  Pokud je nastavené na **Nenakonfigurováno** (výchozí nastavení), toto nastavení se nevyhodnotí pro dodržování předpisů nebo nedodržování předpisů.

- **Vyžadovat, aby na zařízení bylo povolené zabezpečené spouštění**: Pokud je nastavené na **vyžadovat**, musí se systém spustit do důvěryhodného stavu výroby. Pokud je tato možnost povolená, musí mít základní součásti používané k restartování počítače správné kryptografické podpisy, které jsou důvěryhodné pro organizaci, která zařízení vyrobila. Firmware UEFI ověří podpis předtím, než umožní počítači spuštění. Pokud jsou nějaké soubory úmyslně poškozeny, což přeruší svůj podpis, systém se nespustí.

  Pokud je nastavené na **Nenakonfigurováno** (výchozí nastavení), toto nastavení se nevyhodnotí pro dodržování předpisů nebo nedodržování předpisů.

  > [!NOTE]
  > U některých zařízení s čipem TPM 1,2 a 2,0 je nastavení **vyžadovat, aby bylo povolené zabezpečené spuštění na zařízení** . U zařízení, která nepodporují čip TPM 2,0 nebo novější, se stav zásad v Intune zobrazuje jako **nevyhovující**. Další informace o podporovaných verzích najdete v tématu [ověření stavu zařízení](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Vyžadovat integritu kódu**: integrita kódu je funkce, která ověřuje integritu ovladače nebo systémového souboru pokaždé, když je načten do paměti. Pokud je nastaveno na **vyžadovat**, integrity kódu zjistí, jestli se do jádra nenačítá nepodepsaný ovladač nebo systémový soubor. Také zjistí, zda je systémový soubor změněn škodlivým softwarem spuštěným pomocí uživatelského účtu s oprávněními správce.

  Pokud je nastavené na **Nenakonfigurováno** (výchozí nastavení), toto nastavení se nevyhodnotí pro dodržování předpisů nebo nedodržování předpisů.

Další zdroje informací:

- [Zprostředkovatel kryptografických služeb ověření stavu](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp) obsahuje podrobné informace o tom, jak služba funguje.
- [Tip podpory: použití nastavení Ověření stavu zařízení jako součást zásad dodržování předpisů v Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Using-Device-Health-Attestation-Settings-as-Part-of/ba-p/282643)

## <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální verze operačního systému**: zadejte minimální povolenou verzi ve formátu **čísla major.minor.Build.cu** . Chcete-li získat správnou hodnotu, otevřete příkazový řádek a zadejte `ver`. Příkaz `ver` vrátí verzi v následujícím formátu:

  `Microsoft Windows [Version 10.0.17134.1]`

  Pokud má zařízení starší verzi, než je zadaná verze operačního systému, nahlásí se jako nedodržující předpisy. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může upgradovat svoje zařízení. Po upgradu budou mít přístup k prostředkům společnosti.

- **Maximální verze OS**: zadejte maximální povolenou verzi v **číselném formátu hlavní_verze. podverze. Build. Revision** . Chcete-li získat správnou hodnotu, otevřete příkazový řádek a zadejte `ver`. Příkaz `ver` vrátí verzi v následujícím formátu:

  `Microsoft Windows [Version 10.0.17134.1]`

  Pokud zařízení používá verzi operačního systému, která je novější než zadaná verze, bude přístup k prostředkům organizace blokovaný. Koncovému uživateli se zobrazí výzva, aby kontaktoval správce IT. Zařízení nemá přístup k prostředkům organizace, dokud se nezmění pravidlo, které umožňuje verzi operačního systému.

- **Minimální požadovaný operační systém pro mobilní zařízení**: zadejte minimální povolenou verzi ve formátu hlavní. podverze. sestavení.

  Pokud má zařízení starší verzi operačního systému, kterou zadáte, nahlásí se jako nedodržující předpisy. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může upgradovat svoje zařízení. Po upgradu budou mít přístup k prostředkům společnosti.

- **Maximální požadavky na operační systém pro mobilní zařízení**: zadejte maximální povolenou verzi v poli Hlavní. podverze. číslo sestavení.

  Pokud zařízení používá verzi operačního systému, která je novější než zadaná verze, bude přístup k prostředkům organizace blokovaný. Koncovému uživateli se zobrazí výzva, aby kontaktoval správce IT. Zařízení nemá přístup k prostředkům organizace, dokud se nezmění pravidlo, které umožňuje verzi operačního systému.

- **Platná sestavení operačního systému**: zadejte rozsah přijatelných verzí operačních systémů, včetně minimální a maximální hodnoty. Můžete také **exportovat** seznam souborů hodnot oddělených čárkami (CSV) těchto přijatelných čísel sestavení operačního systému.

## <a name="configuration-manager-compliance"></a>Configuration Manager dodržování předpisů

Platí jenom pro spoluspravovaná zařízení s Windows 10 a novějším. Zařízení jenom v Intune vracejí stav není k dispozici.

- **Vyžadovat kompatibilitu zařízení od System Center Configuration Manager**: vyberte **vyžadovat** , pokud chcete vynutit, aby všechna nastavení (konfigurační položky) v System Center Configuration Manager splňovala předpisy. 

  Například budete vyžadovat, aby byly všechny aktualizace softwaru nainstalovány na zařízeních. V Configuration Manager má tento požadavek stav nainstalováno. Pokud jsou některé programy v zařízení v neznámém stavu, zařízení nedodržuje předpisy v Intune.
  
  Pokud **není nakonfigurovaný**, Intune nekontroluje žádné nastavení Configuration Manager pro dodržování předpisů.

## <a name="system-security"></a>Zabezpečení systému

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **vyžaduje** , aby uživatelé zadali heslo, aby mohli získat přístup ke svému zařízení. Pokud **není nakonfigurovaný**, Intune zařízení nevyhodnotí pro dodržování předpisů v nastavení hesla.
- **Jednoduchá hesla**: nastavte **blokování** , aby uživatelé nemohli vytvářet jednoduchá hesla, například **1234** nebo **1111**. Nastavte na **Nenakonfigurováno** , aby uživatelé mohli vytvářet hesla, například **1234** nebo **1111**.
- **Typ hesla**: vyberte požadovaný typ hesla nebo PIN kódu. Vaše možnosti:

  - **Výchozí nastavení zařízení**: vyžadovat heslo, číselný kód PIN nebo alfanumerický kód PIN
  - **Číslice**: vyžadovat heslo nebo číselný PIN kód
  - **Alfanumerické znaky**: vyžaduje heslo, nebo alfanumerický kód PIN. Také vyberte **složitost hesla**: 
    
    - **Vyžadovat číslice a malá písmena**
    - **Vyžadovat číslice, malá písmena a velká písmena**
    - **Vyžadovat číslice, malá písmena, Velká písmena a speciální znaky**

    > [!TIP]
    > Alfanumerické zásady hesel můžou být složité. Doporučujeme správcům, aby si přečetli CSP pro další informace:
    >
    > - [CSP DeviceLock/AlphanumericDevicePasswordRequired](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired)
    > - [CSP DeviceLock/MinDevicePasswordComplexCharacters](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-mindevicepasswordcomplexcharacters)

- **Minimální délka hesla**: zadejte minimální počet číslic nebo znaků, které musí heslo obsahovat.
- **Maximální počet minut nečinnosti před vyžadováním hesla**: zadejte dobu nečinnosti, než uživatel musí znovu zadat heslo.
- **Vypršení platnosti hesla (dny)** : zadejte počet dní do vypršení platnosti hesla a musí vytvořit nové, od 1-730.
- **Počet předchozích hesel, která se nedají použít znovu**: zadejte počet dříve použitých hesel, která se nedají použít.
- **Vyžadovat heslo při návratu zařízení ze stavu nečinnosti (mobilní a holografické)** : vynutí, aby uživatelé zadali heslo pokaždé, když se zařízení vrátí ze stavu nečinnosti.

  > [!IMPORTANT]
  > Když se požadavek na heslo změní na plochu Windows, uživatelé budou mít vliv na jeho příštím přihlášení, protože to znamená, že zařízení přestane být aktivní. Uživatelům s hesly, kteří splňují požadavky, se stále zobrazí výzva ke změně hesla.

### <a name="encryption"></a>Šifrování

- **Šifrování úložiště dat na zařízení**: vyberte **vyžadovat** a Zašifrujte úložiště dat v zařízeních.

  > [!NOTE]
  > **Šifrování úložiště dat v zařízení** obecně kontroluje přítomnost šifrování v zařízení. Pro robustnější nastavení šifrování zvažte použití **nástroje vyžadovat BitLocker**, který využívá ověření stavu zařízení Windows k ověření stavu BitLockeru na úrovni čipu TPM.

### <a name="device-security"></a>Zabezpečení zařízení

- **Firewall**: Nastavte, aby se **vyžadovalo** zapnutí firewallu v programu Microsoft Defender, a zabraňte uživatelům v jeho vypnutí. **Nenakonfigurováno** (výchozí) neřídí firewall v programu Microsoft Defender ani nemění stávající nastavení.

  [Zprostředkovatel CSP brány firewall](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp)

  > [!NOTE]
  > Pokud se zařízení hned po restartování synchronizuje nebo hned synchronizuje probuzení z režimu spánku, toto nastavení se může hlásit jako **Chyba**. Tento scénář nemusí mít vliv na celkový stav dodržování předpisů zařízením. Pokud chcete znovu vyhodnotit stav dodržování předpisů, proveďte ruční [synchronizaci zařízení](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).

- **Čip TPM (Trusted Platform Module)** : Pokud je nastavený na **vyžádání**, Intune zkontroluje kompatibilitu verze. Zařízení splňuje předpisy, pokud je verze čipu TPM větší než 0 (nula). Zařízení nedodržuje předpisy, pokud na zařízení není verze TPM. Pokud **není nakonfigurovaný**, Intune v zařízení nekontroluje verzi čipu TPM.

  [DeviceStatus CSP – DeviceStatus/TPM/SpecificationVersion uzel](https://docs.microsoft.com/windows/client-management/mdm/devicestatus-csp)
  
- **Antivirová ochrana**: Pokud nastavíte možnost **vyžadovat**, můžete ověřit dodržování předpisů pomocí antivirových řešení, která jsou zaregistrovaná v [systému Windows Security Center](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), například Symantec a Microsoft Defender. Pokud **není nakonfigurovaný**, Intune nehledá žádná řešení AV nainstalovaná v zařízení.
- **Antispywarový**program: Pokud nastavíte možnost **vyžadovat**, můžete ověřit dodržování předpisů pomocí antispywarových řešení, která jsou zaregistrovaná v [systému Windows Security Center](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), jako jsou Symantec a Microsoft Defender. Pokud **není nakonfigurovaný**, Intune nekontroluje žádná antispywarová řešení nainstalovaná v zařízení.

### <a name="defender"></a>Defender

- **Antimalware v programu Microsoft Defender**: Nastavte, aby bylo **nutné** zapnout službu Microsoft Defender anti-malware a zabránit uživatelům v jejich vypnutí. **Nenakonfigurováno** (výchozí) neřídí službu ani nemění stávající nastavení.
- **Minimální verze antimalwaru v programu Microsoft Defender**: zadejte minimální povolenou verzi služby Microsoft Defender anti-malware. Zadejte například `4.11.0.0`. Pokud je ponecháno prázdné, bude možné použít jakoukoli verzi služby Microsoft Defender anti-malware.
- Analýza **antimalwarového zabezpečení v programu Microsoft Defender je aktuální**: řídí aktualizace ochrany před viry a hrozbami v zabezpečení systému Windows na zařízeních. **Vyžadovat** , aby byly analytické údaje v programu Microsoft Defender aktuální. **Nenakonfigurováno** (výchozí) neuplatňuje žádné požadavky.

  [Aktualizace Security Intelligence pro antivirovou ochranu a další antimalware Microsoftu](https://www.microsoft.com/en-us/wdsi/defenderupdates) obsahují další informace o Security Intelligence.

- **Ochrana v reálném**čase: **vyžadovat** zapnutí ochrany v reálném čase, která vyhledává malware, spyware a další nežádoucí software. **Nenakonfigurováno** (výchozí) neřídí tuto funkci ani nemění stávající nastavení.

  [Defender/AllowRealtimeMonitoring CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring)

## <a name="microsoft-defender-atp"></a>Microsoft Defender ATP

- **Vyžadovat, aby zařízení bylo na nebo pod hodnocením rizika počítače**: pomocí tohoto nastavení můžete jako podmínku pro dodržování předpisů využít hodnocení rizik ze služeb ochrany před hrozbami. Vyberte maximální povolenou úroveň hrozby:

  - **Vymazat**: Tato možnost je nejbezpečnější, protože zařízení nemůže mít žádné hrozby. Pokud se zjistí, že zařízení má jakoukoli úroveň hrozeb, vyhodnotí se jako nedodržující předpisy.
  - **Nízká**: zařízení se vyhodnotí jako vyhovující, pokud jsou přítomny jenom hrozby nízké úrovně. Cokoli vyšší znamená, že zařízení je v nekompatibilním stavu.
  - **Střední**: zařízení se vyhodnotí jako vyhovující, pokud jsou stávající hrozby v zařízení na nízké nebo střední úrovni. Pokud se zjistí, že zařízení bude mít hrozby vysoké úrovně, je zjištěno, že nedodržuje předpisy.
  - **Vysoká**: Tato možnost je nejméně bezpečná a umožňuje všechny úrovně hrozeb. To může být užitečné, pokud toto řešení používáte pouze pro účely vytváření sestav.
  
  Informace o nastavení ochrany ATP Microsoft Defenderu (Rozšířená ochrana před internetovými útoky) jako služby ochrany před hrozbami najdete v tématu [Povolení ATP Microsoft Defenderu s podmíněným přístupem](advanced-threat-protection.md).

Vyberte **OK** > **vytvořit** a uložte provedené změny.

## <a name="windows-holographic-for-business"></a>Windows Holografick pro firmy

Windows Holografick pro firmy používá platformu **Windows 10 a novější** . Windows Holografick pro firmy podporuje následující nastavení:

- **Zabezpečení systému** > **šifrování** > **šifrování datového úložiště na zařízení**.

Pokud chcete ověřit šifrování zařízení v Microsoft HoloLens, přečtěte si téma [ověření šifrování zařízení](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption).

## <a name="surface-hub"></a>Surface Hub

Surface Hub používá platformu **Windows 10 a novější** . Centra Surface jsou podporovaná pro dodržování předpisů i pro podmíněný přístup. Pokud chcete tyto funkce na Surface Hub povolit, doporučujeme [Povolit automatickou registraci Windows 10](../enrollment/windows-enroll.md) v Intune (vyžaduje Azure Active Directory (Azure AD)) a cílit na Surface Hub zařízení jako na skupiny zařízení. Rozbočovače Surface musí být připojená k Azure AD pro dodržování předpisů a podmíněný přístup pro práci.

Pokyny najdete v tématu [Nastavení registrace pro zařízení s Windows](../enrollment/windows-enroll.md) .

## <a name="next-steps"></a>Další kroky

- [Přidejte akce pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [použijte značky oboru k filtrování zásad](../fundamentals/scope-tags.md).
- [Monitorujte zásady dodržování předpisů](compliance-policy-monitor.md).
- Podívejte se na [nastavení zásad dodržování předpisů pro zařízení Windows 8.1](compliance-policy-create-windows-8-1.md) .
