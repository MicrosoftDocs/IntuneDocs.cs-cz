---
title: Nastavení dodržování předpisů Windows 10 v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zobrazit seznam všech nastavení, které můžete použít při nastavení dodržování předpisů pro zařízení s Windows 10, Windows Holographic a Surface Hub v Microsoft Intune. Zkontrolovat dodržování předpisů na minimální a maximální verzi operačního systému, omezení pro heslo sadu a délku, vyhledat partnera řešení (AV) antivirový program, povolit šifrování na úložiště dat a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d956526d483a74ca5929180a48ea2dcd8b3eab7
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423624"
---
# <a name="windows-10-and-later-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Nastavení Windows 10 a novější se zařízení označí jako vyhovující nebo nevyhovující předpisům pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek uvádí a popisuje nastavení různých dodržování předpisů, které můžete nakonfigurovat na Windows 10 a novější zařízení v Intune. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete vyžadovat BitLocker, nastavte minimální a maximální operačního systému, nastavit úroveň rizika pomocí Windows Defenderu Advanced Threat Protection (ATP) a další.

Tato funkce platí pro:

- Windows 10 a novější
- Windows Holographic for Business
- Surface Hub

Jako správce Intune pomocí těchto nastavení dodržování předpisů pomáhají chránit prostředky organizace. Další informace o zásadách dodržování předpisů a jaké, viz [Začínáme s dodržováním předpisů zařízeními](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte zásadu dodržování předpisů](create-compliance-policy.md#create-the-policy). V poli **Platforma** vyberte **Windows 10 a novější**.

## <a name="device-health"></a>Device health

- **Vyžadovat BitLocker**: Pokud je nastavena na **vyžadují**, zařízení může chránit data uložená na disku před neoprávněným přístupem, pokud je systém vypnutý nebo přejde do režimu spánku. Nástroj Windows BitLocker Drive Encryption zašifruje všechna data uložená na svazku operačního systému Windows. BitLocker používá k ochraně operačního systému Windows a uživatelských dat čip TPM. Pomáhá také potvrďte, že počítačem nemanipulovalo, i když levý režimu ztráty nebo odcizení. Pokud je počítač vybavený kompatibilním čipem TPM, nástroj BitLocker pomocí čipu TPM uzamkne šifrovací klíče, které chrání data. Klíče v důsledku toho nelze přistupovat, dokud čip TPM ověřuje stav počítače.

  Pokud je nastavena na **Nenakonfigurováno** (výchozí), toto nastavení se nevyhodnotí dodržování předpisů nebo nedodržení předpisů.

- **Vyžadovat, aby na zařízení povolené zabezpečené spuštění**: Pokud je nastavena na **vyžadují**, musí se systém spouštět do důvěryhodného stavu z výroby. Pokud povolená, musí mít komponenty jádra sloužící ke spuštění počítače správné kryptografické podpisy, které jsou důvěryhodné organizací, která vyrobenými zařízení. Firmware UEFI nejdříve ověří podpis a až potom povolí spuštění počítače. Pokud se všechny soubory se manipulovalo, které dojde k porušení jejich podpisu, nebude spuštění systému.

  Pokud je nastavena na **Nenakonfigurováno** (výchozí), toto nastavení se nevyhodnotí dodržování předpisů nebo nedodržení předpisů.

  > [!NOTE]
  > **Vyžadovat zabezpečené spouštění, aby na zařízení byla povolená** nastavení je podporováno na některé TPM 1.2 a 2.0 zařízení. Pokud zařízení nepodporují TPM 2.0 nebo novější, zobrazí se v Intune stav zásady jako **nevyhovující**. Další informace o podporovaných verzích najdete v tématu [ověření stavu zařízení](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Vyžadovat integritu kódu**: Integrita kódu je funkce, která ověřuje integritu ovladače nebo systémového souboru pokaždé, když je načten do paměti. Pokud je nastavena na **vyžadují**, integrita kódu zjistí-li nepodepsaný ovladač nebo systémový soubor se načítá do jádra. Zjistí také, zda je soubor systému změny škodlivým softwarem spuštěným pomocí uživatelského účtu s oprávněními správce.

  Pokud je nastavena na **Nenakonfigurováno** (výchozí), toto nastavení se nevyhodnotí dodržování předpisů nebo nedodržení předpisů.

Další materiály:

- [Poskytovatel CSP služby Health Attestation](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp) obsahuje podrobnosti o tom, jak služba HAS funguje.
- [Tip podporu: Použití nastavení pro ověření stavu zařízení jako součást zásad dodržování předpisů Intune ](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Using-Device-Health-Attestation-Settings-as-Part-of/ba-p/282643)

## <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální verze operačního systému**: Zadejte minimální povolenou verzi ve **číslo major.minor.build.CU** formátu. Správnou hodnotu získáte, když otevřete příkazový řádek a zadáte `ver`. Příkaz `ver` vrátí verzi v následujícím formátu:

  `Microsoft Windows [Version 10.0.17134.1]`

  Pokud má zařízení starší verze než verze operačního systému můžete zadat, uvede se jako nedodržující předpisy. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel může zvolit upgrade svého zařízení. Po upgradu, bude přístup k prostředkům společnosti.

- **Maximální verze operačního systému**: Zadejte maximální povolenou verzi ve **major.minor.build.revision číslo** formátu. Správnou hodnotu získáte, když otevřete příkazový řádek a zadáte `ver`. Příkaz `ver` vrátí verzi v následujícím formátu:

  `Microsoft Windows [Version 10.0.17134.1]`

  Když zařízení používá verzi operačního systému novější než verze zadaná, přístup k prostředkům organizace, je blokován. Koncovému uživateli se zobrazí výzva, chcete-li kontaktovat správce IT. Zařízení nemá přístup k prostředkům organizace, dokud pravidla se změní na verzi operačního systému povolí.

- **Minimální požadovaný operační systém pro mobilní zařízení**: Zadejte minimální povolenou verzi ve formátu major.minor.build.

  Pokud má zařízení starší verzi, verze operačního systému můžete zadat, uvede se jako nedodržující předpisy. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel může zvolit upgrade svého zařízení. Po upgradu, bude přístup k prostředkům společnosti.

- **Maximální verze operačního systému pro mobilní zařízení**: Zadejte maximální povolenou verzi ve formátu Major.minor.Build.

  Když zařízení používá verzi operačního systému novější než verze zadaná, přístup k prostředkům organizace, je blokován. Koncovému uživateli se zobrazí výzva, chcete-li kontaktovat správce IT. Zařízení nemá přístup k prostředkům organizace, dokud pravidla se změní na verzi operačního systému povolí.

- **Platná sestavení operačního systému**: Zadejte rozsah povolené verze operačního systému, včetně minimální a maximální. Seznam vyhovujících čísel buildů operačních systémů také můžete **exportovat** do textového souboru CSV s oddělovači.

## <a name="configuration-manager-compliance"></a>Dodržování předpisů v Configuration Manageru

Platí pouze pro spoluspravovaná zařízení se systémem Windows 10 a novější. Není k dispozici stav vrácení zařízení jen pro Intune.

- **Vyžadovat dodržování předpisů zařízením ze System Center Configuration Manager**: Zvolte **vyžadují** přinutit všechna nastavení (položky konfigurace) v System Center Configuration Manager, aby vyhovovala. 

  Můžete například vyžadovat, aby v zařízeních byly nainstalované všechny aktualizace softwaru. V Configuration Manageru má tento požadavek stav Nainstalováno. Pokud jsou všechny programy na zařízení v neznámém stavu, je zařízení nedodržují předpisy v Intune.
  
  Když **Nenakonfigurováno**, Intune nezkontroluje pro některé z nastavení nástroje Configuration Manager pro dodržování předpisů.

## <a name="system-security"></a>Zabezpečení systému

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadovat** uživatelé zadat heslo, než bude moct svoje zařízení.
- **Jednoduchá hesla**: Nastavte na **bloku** , uživatelé nemůžou vytvářet jednoduchá hesla, jako například **1234** nebo **1111**. Pokud chcete uživatelům umožnit vytváření hesel jako **1234** nebo **1111**, nastavte na **Nenakonfigurováno**.
- **Typ hesla**: Zvolte, jestli má heslo obsahovat pouze **číselné** znaků, nebo jestli má obsahovat kombinaci čísel a dalších znaků (**alfanumerické**).

  - **Počet nealfanumerických znaků v hesle**: Pokud se **Požadovaný typ hesla** nastaví na **Alfanumerické**, toto nastavení určuje nejmenší počet znakových sad, které musí heslo obsahovat. Jde o tyto čtyři znakové sady:
    - Malá písmena
    - Velká písmena
    - Symboly
    - Numbers

    Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo.

- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Maximální počet minut nečinnosti před vyžádáním hesla**: Zadejte dobu nečinnosti, než uživatel musí znovu zadat heslo.
- **Vypršení platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která zakázat opakované použití**: Zadejte počet dříve použitých hesel, která nelze použít.
- **Vyžadovat heslo při návratu zařízení ze stavu nečinnosti (Mobile a Holographic)**: Vynutí zadání hesla při každém návratu zařízení ze stavu nečinnosti.

### <a name="encryption"></a>Šifrování

- **Šifrování datového úložiště na zařízení**: Zvolte **vyžadují** a zašifrujte úložiště dat na vašich zařízeních.

  > [!NOTE]
  > Nastavení **Šifrování datového úložiště na zařízení** kontroluje obecnou přítomnost šifrování v zařízení. Pokud chcete nastavení šifrování zkontrolovat důkladněji, použijte možnost **Vyžadovat BitLocker**, která k ověření stavu BitLockeru na úrovni čipu TPM používá službu Ověření stavu zařízení s Windows.

### <a name="device-security"></a>Zabezpečení zařízení

- **Antivirová ochrana v programu**: Pokud je nastavena na **vyžadují**, můžete zkontrolovat dodržování předpisů pomocí antivirových řešení, které jsou registrovány [Windows Security Center](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), jako je například Symantec a programem Windows Defender. Pokud **není nakonfigurovaná**, nezjišťuje Intune žádná antivirová řešení nainstalovaná v zařízení.
- **AntiSpyware**: Pokud je nastavena na **vyžadují**, můžete zkontrolovat dodržování předpisů pomocí antispywaru řešení, které jsou registrovány [Windows Security Center](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), jako je například Symantec a programem Windows Defender. Pokud **není nakonfigurovaná**, nezjišťuje Intune žádná antispywarová řešení nainstalovaná v zařízení.

## <a name="windows-defender-atp"></a>Ochrana ATP v programu Windows Defender

- **Vyžadovat, aby zařízení bylo na nebo za skóre rizika počítače**: Toto nastavení použijte k vyhodnocování rizika z vaší ochrany před mobilními hrozbami služby jako podmínku dodržování předpisů. Vyberte maximální povolenou úroveň hrozby:

  - **Vymazat**: Tato možnost je nejbezpečnější, protože zařízení nesmí být nijak ohroženo zabezpečení. Pokud zařízení zjistí libovolná úroveň hrozeb, vyhodnotí se jako nedodržující předpisy.
  - **Nízká**: Zařízení je vyhodnoceno jako vyhovující, pokud jen hrozby nízké úrovně jsou k dispozici. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední**: Zařízení je vyhodnoceno jako vyhovující, pokud se existující hrozby v zařízení se střední nebo nízké úrovni. Pokud se zařízení zjistí hrozby vysoké úrovně, má vyhodnotí jako nevyhovující.
  - **Vysoká**: Tato možnost je nejméně bezpečná a umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.
  
  Pokud chcete Ochranu ATP v programu Windows Defender (rozšířenou ochranu před internetovými útoky) nastavit jako službu ochrany před hrozbami, přečtěte si téma [Povolení Ochrany ATP v programu Windows Defender s podmíněným přístupem](advanced-threat-protection.md).

Vyberte **OK** > **Vytvořit** a změny uložte.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Windows Holographic for Business používá platformu **Windows 10 a novější**. Windows Holographic for Business podporuje následující nastavení:

- **Zabezpečení systému** > **Šifrování** > **Šifrování datového úložiště na zařízení**.

Pokud chcete ověřit šifrování u zařízení Microsoft HoloLens, přečtěte si článek [Ověření šifrování zařízení](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption).

## <a name="surface-hub"></a>Surface Hub

Surface Hub používá platformu **Windows 10 a novější**. Zařízení Surface Hub podporují dodržování předpisů i podmíněný přístup. Povolení těchto funkcí pro Surface Huby, doporučujeme [povolit automatickou registraci Windows 10](windows-enroll.md) v Intune (vyžaduje Azure Active Directory (Azure AD)) a cílit na zařízení Surface Hub jako na skupiny zařízení. Zařízení Surface hub se musí být připojená k Azure AD pro dodržování předpisů a podmíněný přístup do práce.

Pokyny najdete v článku [Nastavení registrace pro zařízení s Windows](windows-enroll.md).

## <a name="next-steps"></a>Další postup

- [Přidání akcí pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [pomocí značky oboru filtru zásad](scope-tags.md).
- [Monitorovat zásady dodržování předpisů](compliance-policy-monitor.md).
- Zobrazit [nastavení zásad dodržování předpisů pro Windows 8.1](compliance-policy-create-windows-8-1.md) zařízení.