---
title: Nastavení dodržování předpisů pro Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na seznam všech nastavení, která můžete použít při nastavování dodržování předpisů pro zařízení s Windows 10, Windows holografickými a Surface Hub v Microsoft Intune. Podívejte se na dodržování předpisů pro minimální a maximální operační systém, nastavte omezení a délku hesla, vyhledejte řešení partnerů pro ochranu proti virům (AV), povolte šifrování u úložiště dat a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/12/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cda6c5f5ffa2244376e318e81a38a1ed410a443f
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/23/2019
ms.locfileid: "71305050"
---
# <a name="windows-10-and-later-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Nastavení Windows 10 a novějších označení zařízení jako kompatibilních nebo nekompatibilních s Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek obsahuje seznam a popis různých nastavení dodržování předpisů, která můžete konfigurovat v zařízeních s Windows 10 a novějším v Intune. Jako součást řešení správy mobilních zařízení (MDM) použijte Tato nastavení k vyžadování nástroje BitLocker, nastavení minimálního a maximálního operačního systému, nastavení úrovně rizika pomocí rozšířené ochrany před internetovými útoky v programu Microsoft Defender (ATP) a dalších.

Tato funkce platí pro:

- Windows 10 a novější
- Windows Holographic for Business
- Surface Hub

Jako správce Intune můžete pomocí těchto nastavení dodržování předpisů ochránit prostředky vaší organizace. Další informace o zásadách dodržování předpisů a o tom, co dělají, najdete v tématu [Začínáme s dodržováním předpisů pro zařízení](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte zásadu dodržování předpisů](create-compliance-policy.md#create-the-policy). V poli **Platforma** vyberte **Windows 10 a novější**.

## <a name="device-health"></a>Device health

- **Vyžadovat nástroj BitLocker**: Pokud nastavíte možnost **vyžadovat**, zařízení může chránit data uložená na disku před neoprávněným přístupem, když je systém vypnutý nebo je v režimu hibernace. Nástroj Windows BitLocker Drive Encryption zašifruje všechna data uložená na svazku operačního systému Windows. BitLocker používá k ochraně operačního systému Windows a uživatelských dat čip TPM. Pomáhá také ověřit, že počítač není úmyslně poškozen, a to ani v případě, že je jeho levý bezobslužný, ztracený nebo odcizený. Pokud je počítač vybavený kompatibilním čipem TPM, nástroj BitLocker pomocí čipu TPM uzamkne šifrovací klíče, které chrání data. K těmto klíčům proto nelze přistupovat, dokud čip TPM neověří stav počítače.

  Pokud je nastavené na **Nenakonfigurováno** (výchozí nastavení), toto nastavení se nevyhodnotí pro dodržování předpisů nebo nedodržování předpisů.

- **Vyžadovat, aby na zařízení bylo povolené zabezpečené spouštění**: Pokud je nastavení **vyžadováno**, je nutné spustit systém do důvěryhodného stavu výroby. Pokud je tato možnost povolená, musí mít základní součásti používané k restartování počítače správné kryptografické podpisy, které jsou důvěryhodné pro organizaci, která zařízení vyrobila. Firmware UEFI nejdříve ověří podpis a až potom povolí spuštění počítače. Pokud jsou nějaké soubory úmyslně poškozeny, což přeruší svůj podpis, systém se nespustí.

  Pokud je nastavené na **Nenakonfigurováno** (výchozí nastavení), toto nastavení se nevyhodnotí pro dodržování předpisů nebo nedodržování předpisů.

  > [!NOTE]
  > U některých zařízení s čipem TPM 1,2 a 2,0 je nastavení **vyžadovat, aby bylo povolené zabezpečené spuštění na zařízení** . Pokud zařízení nepodporují TPM 2.0 nebo novější, zobrazí se v Intune stav zásady jako **nevyhovující**. Další informace o podporovaných verzích najdete v tématu [ověření stavu zařízení](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Vyžadovat integritu kódu**: Integrita kódu je funkce, která ověřuje integritu ovladače nebo systémového souboru pokaždé, když je načten do paměti. Pokud je nastaveno na **vyžadovat**, integrity kódu zjistí, jestli se do jádra nenačítá nepodepsaný ovladač nebo systémový soubor. Také zjistí, zda je systémový soubor změněn škodlivým softwarem spuštěným pomocí uživatelského účtu s oprávněními správce.

  Pokud je nastavené na **Nenakonfigurováno** (výchozí nastavení), toto nastavení se nevyhodnotí pro dodržování předpisů nebo nedodržování předpisů.

Další zdroje informací:

- [Zprostředkovatel kryptografických služeb ověření stavu](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp) obsahuje podrobné informace o tom, jak služba funguje.
- [Tip podpory: Použití nastavení Ověření stavu zařízení jako součást zásad dodržování předpisů v Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Using-Device-Health-Attestation-Settings-as-Part-of/ba-p/282643)

## <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální verze operačního systému**: Zadejte minimální povolenou verzi ve formátu **čísla major.minor.Build.cu** . Správnou hodnotu získáte, když otevřete příkazový řádek a zadáte `ver`. Příkaz `ver` vrátí verzi v následujícím formátu:

  `Microsoft Windows [Version 10.0.17134.1]`

  Pokud má zařízení starší verzi, než je zadaná verze operačního systému, nahlásí se jako nedodržující předpisy. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel si může upgradovat svoje zařízení. Po upgradu budou mít přístup k prostředkům společnosti.

- **Maximální verze OS**: Zadejte maximální povolenou verzi v **číselném formátu hlavní_verze. podverze. Build. Revision** . Správnou hodnotu získáte, když otevřete příkazový řádek a zadáte `ver`. Příkaz `ver` vrátí verzi v následujícím formátu:

  `Microsoft Windows [Version 10.0.17134.1]`

  Pokud zařízení používá verzi operačního systému, která je novější než zadaná verze, bude přístup k prostředkům organizace blokovaný. Koncovému uživateli se zobrazí výzva, aby kontaktoval správce IT. Zařízení nemá přístup k prostředkům organizace, dokud se nezmění pravidlo, které umožňuje verzi operačního systému.

- **Minimální požadovaný operační systém pro mobilní zařízení**: Zadejte minimální povolenou verzi ve formátu hlavní. podverze. sestavení.

  Pokud má zařízení starší verzi operačního systému, kterou zadáte, nahlásí se jako nedodržující předpisy. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel si může upgradovat svoje zařízení. Po upgradu budou mít přístup k prostředkům společnosti.

- **Maximální požadovaný operační systém pro mobilní zařízení**: Zadejte maximální povolenou verzi v hlavní číslo. podverze. sestavení.

  Pokud zařízení používá verzi operačního systému, která je novější než zadaná verze, bude přístup k prostředkům organizace blokovaný. Koncovému uživateli se zobrazí výzva, aby kontaktoval správce IT. Zařízení nemá přístup k prostředkům organizace, dokud se nezmění pravidlo, které umožňuje verzi operačního systému.

- **Platná sestavení operačního systému**: Zadejte rozsah pro přijatelné verze operačních systémů, včetně minimální a maximální hodnoty. Seznam vyhovujících čísel buildů operačních systémů také můžete **exportovat** do textového souboru CSV s oddělovači.

## <a name="configuration-manager-compliance"></a>Configuration Manager dodržování předpisů

Platí jenom pro spoluspravovaná zařízení s Windows 10 a novějším. Zařízení jenom v Intune vracejí stav není k dispozici.

- **Vyžadovat System Center Configuration Manager dodržování předpisů zařízením**: Vyberte **vyžadovat** , pokud chcete vynutit, aby všechna nastavení (konfigurační položky) v System Center Configuration Manager splňovala předpisy. 

  Můžete například vyžadovat, aby v zařízeních byly nainstalované všechny aktualizace softwaru. V Configuration Manageru má tento požadavek stav Nainstalováno. Pokud jsou některé programy v zařízení v neznámém stavu, zařízení nedodržuje předpisy v Intune.
  
  Pokud **není nakonfigurovaný**, Intune nekontroluje žádné nastavení Configuration Manager pro dodržování předpisů.

## <a name="system-security"></a>Zabezpečení systému

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžaduje** , aby uživatel zadal heslo, než bude mít přístup ke svému zařízení. Pokud **není nakonfigurovaný**, Intune zařízení nevyhodnotí pro dodržování předpisů v nastavení hesla.
- **Jednoduchá hesla**: Nastavte **blokování** , aby uživatelé nemohli vytvářet jednoduchá hesla, například **1234** nebo **1111**. Pokud chcete uživatelům umožnit vytváření hesel jako **1234** nebo **1111**, nastavte na **Nenakonfigurováno**.
- **Typ hesla**: Vyberte požadovaný typ hesla nebo PIN kódu. Možnosti:

  - **Výchozí nastavení zařízení**: Vyžadovat heslo, číselný kód PIN nebo alfanumerický kód PIN
  - **Číselná**: Vyžadovat heslo nebo číselný PIN kód
  - **Alfanumerické znaky**: Vyžadovat heslo nebo alfanumerický kód PIN Také vyberte **složitost hesla**: 
    
    - **Vyžadovat číslice a malá písmena**
    - **Vyžadovat číslice, malá písmena a velká písmena**
    - **Vyžadovat číslice, malá písmena, Velká písmena a speciální znaky**

    > [!TIP]
    > Alfanumerické zásady hesel můžou být složité. Doporučujeme správcům, aby si přečetli CSP pro další informace:
    >
    > - [CSP DeviceLock/AlphanumericDevicePasswordRequired](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired)
    > - [CSP DeviceLock/MinDevicePasswordComplexCharacters](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-mindevicepasswordcomplexcharacters)

- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo obsahovat.
- **Maximální počet minut nečinnosti před vyžadováním hesla**: Zadejte dobu nečinnosti, než uživatel musí znovu zadat heslo.
- **Vypršení platnosti hesla (dny)** : Zadejte počet dní do vypršení platnosti hesla a musí vytvořit nové, od 1-730.
- **Počet předchozích hesel, která zabrání opakovanému použití**: Zadejte počet dříve použitých hesel, která se nedají použít.
- **Vyžadovat heslo při návratu zařízení ze stavu nečinnosti (mobilní a holografická)** : Vynutí, aby uživatelé zadali heslo pokaždé, když se zařízení vrátí ze stavu nečinnosti.

  > [!IMPORTANT]
  > Když se požadavek na heslo změní na plochu Windows, uživatelé budou mít vliv na jeho příštím přihlášení, protože to znamená, že zařízení přestane být aktivní. Uživatelům s hesly, kteří splňují požadavky, se stále zobrazí výzva ke změně hesla.

### <a name="encryption"></a>Šifrování

- **Šifrování datového úložiště na zařízení**: Vyberte **vyžadovat** pro šifrování úložiště dat na vašich zařízeních.

  > [!NOTE]
  > Nastavení **Šifrování datového úložiště na zařízení** kontroluje obecnou přítomnost šifrování v zařízení. Pokud chcete nastavení šifrování zkontrolovat důkladněji, použijte možnost **Vyžadovat BitLocker**, která k ověření stavu BitLockeru na úrovni čipu TPM používá službu Ověření stavu zařízení s Windows.

### <a name="device-security"></a>Zabezpečení zařízení

- **Brána firewall**: Nastavte, aby se **vyžadovalo** zapnutí firewallu v programu Microsoft Defender, a zabraňte uživatelům v jeho vypnutí. **Není nakonfigurováno** (výchozí) neřídí firewall v programu Microsoft Defender ani nemění stávající nastavení.

  [Zprostředkovatel CSP brány firewall](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp)

- **Čip TPM (Trusted Platform Module)** : Pokud je nastavené na **vyžadovat**, Intune zkontroluje verzi pro dodržování předpisů. Zařízení splňuje předpisy, pokud je verze čipu TPM větší než 0 (nula). Zařízení nedodržuje předpisy, pokud na zařízení není verze TPM. Pokud **není nakonfigurovaný**, Intune v zařízení nekontroluje verzi čipu TPM.

  [DeviceStatus CSP – DeviceStatus/TPM/SpecificationVersion uzel](https://docs.microsoft.com/windows/client-management/mdm/devicestatus-csp)
  
- **Antivirová ochrana**: Pokud nastavíte hodnotu **vyžadovat**, můžete ověřit dodržování předpisů pomocí antivirových řešení, která jsou zaregistrovaná v [systému Windows Security Center](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), například Symantec a Microsoft Defender. Pokud **není nakonfigurovaná**, nezjišťuje Intune žádná antivirová řešení nainstalovaná v zařízení.
- **Antispywarový**program: Pokud nastavíte možnost **vyžadovat**, můžete ověřit dodržování předpisů pomocí antispywarových řešení, která jsou zaregistrovaná v [systému Windows Security Center](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), jako je například Symantec a Microsoft Defender. Pokud **není nakonfigurovaná**, nezjišťuje Intune žádná antispywarová řešení nainstalovaná v zařízení.

### <a name="defender"></a>Defender

- **Antimalware v programu Microsoft Defender**: Nastavte, aby se **vyžadovalo** zapnutí služby anti-malware v programu Microsoft Defender a zabránění uživatelům v jejich vypnutí. **Není nakonfigurováno** (výchozí) neřídí službu ani nemění stávající nastavení.
- **Minimální verze antimalwaru v programu Microsoft Defender**: Zadejte minimální povolenou verzi služby Microsoft Defender anti-malware. Zadejte například `4.11.0.0`. Pokud je ponecháno prázdné, bude možné použít jakoukoli verzi služby Microsoft Defender anti-malware.
- **Microsoft Defender antimalwar Security –** přehledy v aktuálním stavu: Řídí aktualizace ochrany proti virům a hrozbám zabezpečení systému Windows na zařízeních. **Vyžadovat** , aby byly analytické údaje v programu Microsoft Defender aktuální. **Není nakonfigurováno** (výchozí) neuplatňuje žádné požadavky.

  [Aktualizace Security Intelligence pro antivirovou ochranu a další antimalware Microsoftu](https://www.microsoft.com/en-us/wdsi/defenderupdates) obsahují další informace o Security Intelligence.

- **Ochrana v reálném čase**: **Vyžaduje** zapnutí ochrany v reálném čase, která vyhledává malware, spyware a další nežádoucí software. **Není nakonfigurováno** (výchozí) neřídí tuto funkci ani nemění stávající nastavení.

  [Defender/AllowRealtimeMonitoring CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring)

## <a name="microsoft-defender-atp"></a>Microsoft Defender ATP

- **Vyžadovat, aby zařízení bylo na nebo pod hodnocením rizika počítače**: Toto nastavení použijte, pokud chcete jako podmínku dodržování předpisů převzít vyhodnocení rizik ze služeb ochrany před hrozbami. Vyberte maximální povolenou úroveň hrozby:

  - **Vymazat**: Tato možnost je nejbezpečnější, protože zařízení nemůže mít žádné hrozby. Pokud se zjistí, že zařízení má jakoukoli úroveň hrozeb, vyhodnotí se jako nedodržující předpisy.
  - **Nízká úroveň**: Zařízení se vyhodnotí jako vyhovující, pokud jsou přítomny jenom hrozby nízké úrovně. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední**: Zařízení se vyhodnotí jako vyhovující, pokud jsou stávající hrozby v zařízení na nízké nebo střední úrovni. Pokud se zjistí, že zařízení bude mít hrozby vysoké úrovně, je zjištěno, že nedodržuje předpisy.
  - **Vysoká**: Tato možnost je nejméně bezpečná a umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.
  
  Informace o nastavení ochrany ATP Microsoft Defenderu (Rozšířená ochrana před internetovými útoky) jako služby ochrany před hrozbami najdete v tématu [Povolení ATP Microsoft Defenderu s podmíněným přístupem](advanced-threat-protection.md).

Vyberte **OK** > **Vytvořit** a změny uložte.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Windows Holographic for Business používá platformu **Windows 10 a novější**. Windows Holographic for Business podporuje následující nastavení:

- **Zabezpečení systému** > **Šifrování** > **Šifrování datového úložiště na zařízení**.

Pokud chcete ověřit šifrování u zařízení Microsoft HoloLens, přečtěte si článek [Ověření šifrování zařízení](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption).

## <a name="surface-hub"></a>Surface Hub

Surface Hub používá platformu **Windows 10 a novější**. Centra Surface jsou podporovaná pro dodržování předpisů i pro podmíněný přístup. Pokud chcete tyto funkce na Surface Hub povolit, doporučujeme [Povolit automatickou registraci Windows 10](windows-enroll.md) v Intune (vyžaduje Azure Active Directory (Azure AD)) a cílit na Surface Hub zařízení jako na skupiny zařízení. Rozbočovače Surface musí být připojená k Azure AD pro dodržování předpisů a podmíněný přístup pro práci.

Pokyny najdete v článku [Nastavení registrace pro zařízení s Windows](windows-enroll.md).

## <a name="next-steps"></a>Další kroky

- [Přidejte akce pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [použijte značky oboru k filtrování zásad](scope-tags.md).
- [Monitorujte zásady dodržování předpisů](compliance-policy-monitor.md).
- Podívejte se na [nastavení zásad dodržování předpisů pro zařízení Windows 8.1](compliance-policy-create-windows-8-1.md) .
