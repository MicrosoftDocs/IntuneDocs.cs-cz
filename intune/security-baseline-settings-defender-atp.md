---
title: Nastavení zabezpečení směrné plány pro Microsoft Defender Advanced Threat Protection Intune
titleSuffix: Microsoft Intune
description: Základní nastavení zabezpečení podporovaných službou Intune pro správu Microsoft Defender Advanced Threat Protection
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/29/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: karthib
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c6feae4d7caeeefbf9638e5018ba7b653a260f5c
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66373498"
---
# <a name="microsoft-defender-advanced-threat-protection-baseline-settings-for-intune"></a>Microsoft Defender Advanced Threat Protection základní nastavení Intune

Zobrazte nastavení směrného plánu Microsoft Defender Advanced Threat Protection (dříve Windows Defender Advanced Threat Protection), které podporuje Microsoft Intune. Výchozí hodnoty v tomto článku představují výchozí směrného plánu konfigurace pro Intune. Tyto výchozí hodnoty představují doporučenou konfiguraci pro Intune a výchozí nastavení Windows se nemusí shodovat.

  The Microsoft Defender Advanced Threat Protection směrného plánu je k dispozici, pokud vaše prostředí splňuje předpoklady pro použití [Microsoft Defender Advanced Threat Protection](advanced-threat-protection.md#prerequisites)).




> [!NOTE]  
> Standardní nastavení WDATP jsou v **ve verzi Preview**. Ve verzi Preview, seznam dostupných nastavení a pořadí, ve kterém tento obsah představuje tato nastavení nemusí odpovídat co je k dispozici na portálu. 
>
> Po standardní nastavení z verze Preview se bude tento obsah aktualizovat tak, aby odrážela aktuální seznam nastavení standardních hodnot zabezpečení, které Intune podporuje.

## <a name="application-guard"></a>Ochrana Application Guard  
Další informace najdete v tématu [WindowsDefenderApplicationGuard CSP](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp) v dokumentaci k Windows.  

Při použití Microsoft Edge, ochranu Application Guard v programu Defender Microsoftu chrání vaše prostředí z webů, které nejsou důvěryhodné ve vaší organizaci. Když uživatelé navštíví weby, které nejsou uvedené v ohraničení vaší izolované sítě, weby otevřete v relaci virtuálního procházení Hyper-V. Ohraničení sítě jsou definovány důvěryhodných serverů.  

- **Ochrana Application Guard** - *nastavení/AllowWindowsDefenderApplicationGuard*  
  Vyberte *Ano* zapnout tuto funkci, která se otevře nedůvěryhodné weby v technologií Hyper-V kontejneru procházení virtualizovaném pomocí. Pokud je nastavena na *Nenakonfigurováno*, kterékoli lokality (důvěryhodné a nedůvěryhodné) otevře v zařízení a ne v kontejneru virtualizované.  

  **Výchozí**: Ano
 
  - **Externí obsah na firemních webech** - *nastavení/BlockNonEnterpriseContent*  
    Vyberte *Ano* k bloku obsahu z neschválených webů načítání. Pokud je nastavena na *Nenakonfigurováno*, mimo kategorii enterprise serverů můžete otevřít na zařízení. 
 
    **Výchozí**: Ano

  - **Chování schránky** - *nastavení/ClipboardSettings*  
    Zvolte, které akce kopírování a vkládání jsou povolené mezi místním Počítačem a virtuálním prohlížeči ochrany Application Guard.  Vaše možnosti jsou:
    - *Není nakonfigurováno*  
    - *Blokovat obě* -nelze za přenosy dat mezi Počítačem a virtuálním prohlížeči.  
    - *Blok hostitele do kontejneru* -nelze přenosu dat z počítače do virtuální prohlížeče.
    - *Blokového kontejneru do hostitele* -nelze přenosu dat z virtuálního prohlížeče do hostitelského počítače.
    - *Blokovat žádná* – bez blokování obsahu existence.  

    **Výchozí**: Blokovat obojí  

- **Zásady izolace sítě Windows – názvy podnikových síťových domén**  
  Další informace najdete v tématu [zásady CSP – NetworkIsolation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-networkisolation) v dokumentaci k Windows.
  
  Zadejte seznam podnikových zdrojů jako domény, rozsahy IP adres a hranice sítě, které jsou hostované v cloudu, který ochrany Application Guard považuje za weby podnikové sítě.  

  **Výchozí**: securitycenter.windows.com

## <a name="application-reputation"></a>Hodnocení aplikace podle  

Další informace najdete v tématu [zásady CSP – SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) v dokumentaci k Windows.

- **Zablokovat spuštění neověřených souborů**  
    Brání uživateli ve spuštění neověřených souborů. Pokud je nastavena na *Nenakonfigurováno*, zaměstnanci můžou ignorovat upozornění filtru SmartScreen a spouštět škodlivé soubory. Nastavte na *Ano* tak, aby zaměstnanci nelze ignorovat upozornění filtru SmartScreen a spouštět škodlivé soubory.  
  
    **Výchozí**: Ano

- **Vyžadovat SmartScreen pro aplikace a soubory**  
  Nastavte na *Ano* Povolit filtr SmartScreen pro Windows.  

  **Výchozí**: Ano

## <a name="attach-surface-reduction"></a>Omezení možností připojení  

- **Aplikace Office spusťte podřízený proces typ**  
  [Pravidla pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Pokud je nastavena na *bloku*, aplikace Office nebudou moct vytvářet podřízené procesy. Aplikace Office zahrnují Word, Excel, PowerPoint, OneNote a přístup. Vytvoření podřízeného procesu je chování typické malware, hlavně pro útoky – makro, které se snaží používat aplikace Office spouštět ani se stahování škodlivého spustitelné soubory.  

  **Výchozí**: Zablokovat

- **Skript se stáhne typ spuštění datové části**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection) – zadejte úroveň zjištění pro potenciálně nežádoucí aplikace, které stáhnout nebo se pokusíte nainstalovat.  

  **Výchozí**: Zablokovat 

- **Zabránit typ zcizování přihlašovacích údajů**  
  Nastavte na *povolit* k [ochrana odvozených přihlašovacích údajů domény pomocí Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard). Windows Defender Credential Guard používá zabezpečení založené na virtualizaci k izolování tajných kódů tak, aby k nim měli přístup pouze oprávněný systémový software. Neoprávněný přístup k těmto tajným kódům může vést k útokům využívajícím krádež přihlašovacích údajů, jako je například Pass-the-Hash nebo Pass-The-Ticket. Windows Defender Credential Guard zabraňuje těmto útokům Díky ochraně hodnot hash hesel protokolů NTLM, lístků TGT protokolu Kerberos a přihlašovací údaje uložené aplikace jako přihlašovací údaje domény.  

  **Výchozí**: Povolení

- **Typ obsahu provádění e-mailu**  
  [Pravidla pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Pokud je nastavena na *bloku*, tato pravidla bloky následující typy spuštění nebo spuštění z e-mailu v aplikaci Microsoft Outlook nebo webové pošty (například Gmail.com nebo Outlook.com) souborů:  

  - Spustitelné soubory (například .exe, .dll nebo .scr)  
  - Soubory skriptu (například PS prostředí PowerShell, VisualBasic .vbs nebo soubor .js JavaScript)  
  - Skript archivní soubory  

  **Výchozí**: Zablokovat

- **Adobe Reader spuštění v podřízený proces**  
  [Pravidla pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – *povolit* tohoto pravidla pro blokování Adobe Reader ve vytváření podřízeného procesu. Přes sociální inženýrství nebo zneužití před škodlivým softwarem můžete stáhnout a spustit další datové části a přerušit ze Adobe Reader.  

  **Výchozí**: Povolení

- **Skript obfuskovaný kód typu – makro**  
  [Pravidla pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – malwarem a dalšími hrozbami můžete pokusit obfuskaci nebo skrytí jejich škodlivý kód v některé soubory skriptu. Toto pravidlo brání skripty, které se zdají být matoucí spouštění.  
    
  **Výchozí**: Zablokovat

- **Typ procesu nedůvěryhodné USB**  
  [Pravidla pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Pokud je nastavena na *bloku*, spustitelný soubor bez znaménka nebo nedůvěryhodných souborů z vyměnitelné jednotky USB a nelze spustit, SD karty.

  Spustitelné soubory patří:
  - Spustitelné soubory (například .exe, .dll nebo .scr)
  - Soubory skriptu (například PS prostředí PowerShell, VisualBasic .vbs nebo soubor .js JavaScript)  

  **Výchozí**: Zablokovat

- **Aplikace Office jiných zpracovat typ vkládání**  
  [Pravidla pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Pokud je nastavena na *bloku*, aplikace Office, Word, Excel, PowerPoint a OneNote, včetně nelze vložit kód do jiných procesů. Injektáž kódu se obvykle používá malware spustit škodlivý kód ve snaze skrýt aktivita z antivirového prověřovacích modulů.  

  **Výchozí**: Zablokovat

- **Povolit typ importy Win32 kódu maker v Office**  
  [Pravidla pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Pokud je nastavena na *bloku*, toto pravidlo se pokusí zablokovat soubory Office, které obsahují – makro kód, který můžete importovat Win32 DLL. Soubory Office zahrnují Word, Excel, PowerPoint a OneNote. Malware můžete použít kódu maker v souborech Office pro import a načíst dll Win32, které se pak použije k volání rozhraní API, která umožní další infekce v celém systému.  

  **Výchozí**: Zablokovat

- **Spuštění aplikace Office komunikace v podřízený proces**  
  [Pravidla pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Pokud je nastavena na *povolit*, toto pravidlo zabraňuje vytváření podřízených procesů. Toto pravidlo zákonné zodpovědnosti organizací blokováním vytváření podřízeného procesu, chrání před útoky sociálního inženýrství a brání zneužití kódu zneužije chyby zabezpečení v aplikaci Outlook.  

  **Výchozí**: Povolení

- **Office aplikace spustitelný soubor vytvoření nebo spuštění typ obsahu**  
  [Pravidla pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Pokud je nastavena na *bloku*, aplikace Office nejde vytvořit spustitelného obsahu. Aplikace Office zahrnují Word, Excel, PowerPoint, OneNote a přístup.  

  Toto pravidlo zaměřuje na typické chování používané podezřelé a škodlivý doplňky a skripty (rozšíření), které vytvářet nebo spouštět spustitelné soubory. Jde o techniku typické malware. Rozšíření jsou blokovány z používán podle aplikace Office. Tato rozšíření obvykle používají Windows Scripting Host (soubory WSH) ke spouštění skriptů, které zautomatizovat určité úlohy nebo poskytují uživatel vytvořil doplňkové funkce.

  **Výchozí**: Zablokovat

## <a name="bitlocker"></a>BitLocker  

Další informace najdete [nastavení zásad skupiny bitlockeru určují](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) v dokumentaci k Windows.  

- **Šifrování zařízení**  
  Vyberte *Ano* povolíte šifrování nástrojem BitLocker zařízení. V závislosti na hardwaru zařízení a verzi Windows možná třeba uživatelům zařízení potvrďte, že neexistuje žádné šifrování třetí strany na zařízení. Zapnutí šifrování Windows šifrování třetí strany je aktivní zařízení bude nestabilní.  

   **Výchozí**: Ano

- **Bit locker vyměnitelnou jednotku zásad**  
  Hodnoty pro tyto zásady určují sílu šifra, která používá nástroj BitLocker k šifrování vyměnitelných jednotek. Podniky řídit úroveň šifrování (AES-256 je silnější než AES-128) zvýšené zabezpečení. Pokud vyberete *Ano* k povolení tohoto nastavení můžete nakonfigurovat šifrovací algoritmus a klíče úroveň šifrování pro jednotky operačního systému pevných datových jednotkách a vyměnitelných datových jednotkách jednotlivě. Oprava a provozní systémové jednotky doporučujeme použít algoritmus XTS-AES. Vyměnitelných jednotek měli byste použít AES-CBC 128-bit nebo AES-CBC oborového 256bitového Pokud na jednotce se používá v jiných zařízení se systémem Windows 10 verze 1511 nebo novější. Změna metoda šifrování nemá žádný účinek, pokud už zašifrovaná disku nebo šifrování probíhá. V těchto případech toto nastavení zásad se ignoruje. 

  Bit locker vyměnitelnou jednotku zásady nakonfigurujte následující nastavení:

    - **Vyžadovat šifrování pro zápis**  
      **Výchozí**: Ano

    - **Metoda šifrování**  
      **Výchozí**: AES 128bit CBC

- **Bit locker pevnou jednotku zásad**  
  Hodnoty pro tyto zásady určují sílu šifra, která používá nástroj BitLocker k šifrování pevných jednotek. Podniky můžete řídit úroveň šifrování (AES-256 je silnější než AES-128) zvýšené zabezpečení. Pokud povolíte toto nastavení, můžete nakonfigurovat šifrovací algoritmus a klíče úroveň šifrování pro pevné datové jednotky, jednotky s operačním systémem a vyměnitelných datových jednotkách jednotlivě. Oprava a provozní systémové jednotky doporučujeme použít algoritmus XTS-AES. Vyměnitelných jednotek měli byste použít AES-CBC 128-bit nebo AES-CBC oborového 256bitového Pokud na jednotce se používá v jiných zařízení se systémem Windows 10 verze 1511 nebo novější. Změna metoda šifrování nemá žádný účinek, pokud už zašifrovaná disku nebo šifrování probíhá. V těchto případech toto nastavení zásad se ignoruje.

  Bit schránku na pověření pevnou jednotku zásady nakonfigurujte následující nastavení:

    - **Vyžadovat šifrování pro zápis**  
      **Výchozí**: Ano

    - **Metoda šifrování**  
      **Výchozí**: AES 128 bitů XTS

- **Bit locker systémové jednotky zásady**  
  Hodnoty pro tyto zásady určují sílu šifra, která BitLocker používá k šifrování systémového disku. Podniky může chtít řídit úroveň šifrování (AES-256 je silnější než AES-128) zvýšené zabezpečení. Pokud povolíte toto nastavení, můžete nakonfigurovat šifrovací algoritmus a klíče úroveň šifrování pro pevné datové jednotky, jednotky s operačním systémem a vyměnitelných datových jednotkách jednotlivě. Oprava a provozní systémové jednotky doporučujeme použít algoritmus XTS-AES. Vyměnitelných jednotek měli byste použít AES-CBC 128-bit nebo AES-CBC oborového 256bitového Pokud na jednotce se používá v jiných zařízení se systémem Windows 10 verze 1511 nebo novější. Změna metoda šifrování nemá žádný účinek, pokud už zašifrovaná disku nebo šifrování probíhá. V těchto případech toto nastavení zásad se ignoruje.  

  Bit locker systémové jednotky zásady nakonfigurujte následující nastavení:  

  - **Metoda šifrování**  
    **Výchozí**: AES 128 bitů XTS

## <a name="device-control"></a>Řízení zařízení  

- **Během úplné kontroly kontrolovat vyměnitelné jednotky**  
  [Defender/AllowFullScanRemovableDriveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) – Pokud je nastavena na *Ano*, bude Defender kontrolovat škodlivým a nežádoucí software v vyměnitelné jednotky, jako jsou flash disky, při spuštění úplné kontroly. Antivirová ochrana v programu Defender kontrolovat všechny soubory na jiná zařízení USB než můžete spustit soubory v zařízení USB.

  Související nastavení v tomto seznamu: *Defender/AllowFullScanOnMappedNetworkDrives*  

  **Výchozí**: Ano

- **Výčet externích zařízení nekompatibilní s ochranou DMA jádra**  
   Zobrazit *DmaGuard/DeviceEnumerationPolicy* v [zásad CSP – DmaGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  Tato zásada poskytuje dodatečné zabezpečení proti externí DMA zařízení. To umožňuje používat pro větší kontrolu nad výčet externí DMA zařízení, které nejsou kompatibilní s izolací paměti DMA zařízení a izolace (sandbox).

  Tyto zásady platí pouze při ochrany DMA jádra je podporován a povolený už ve firmwaru systému. Ochrany DMA jádra je funkce platformy, která nelze řídit pomocí zásad nebo uživatel zařízení. Musí podporovat v systému v době výroby. 

  Pokud chcete zkontrolovat, jestli systém podporuje ochrany DMA jádra, spusťte MSINFO32.exe v systému a přečtěte si *ochrany DMA jádra* pole na stránce Souhrn.  

  Vaše možnosti jsou: 
  - *Výchozí ze zařízení* – po přihlášení nebo odemknutí obrazovky zařízení s DMA přemapování kompatibilních ovladačů můžou vytvořit výčet kdykoli. Bude po uživateli odemkne obrazovky pouze uvedené zařízení DMA přemapování kompatibilní ovladače
  - *Povolit všechny* – všechny externí DMA PCIe zařízení se budou uvedené v každém okamžiku
  - *Blokovat veškerý* -DMA přemapování kompatibilních ovladačů zařízení můžou zobrazit výčet kdykoli. Zařízení DMA přemapování nekompatibilních ovladačů se nikdy povoleno spuštění a provést DMA kdykoli.

  **Výchozí**: Výchozí ze zařízení

- **Instalace hardwaru zařízení pomocí identifikátorů zařízení**  
  [DeviceInstallation/PreventInstallationOfMatchingDeviceIDs](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceids) – s touto zásadou, zadáte seznam technologie Plug and Play ID hardwaru a kompatibilní ID pro zařízení, že je Windows zabráněno v instalaci. Toto nastavení zásad má přednost před jiného nastavení zásad, který umožňuje nainstalovat zařízení Windows. Pokud povolíte toto nastavení zásad (nastavena na *služba neblokuje instalaci zařízení hardwaru*), Windows je zabránily instalaci zařízení, jejichž ID hardwaru nebo kompatibilní ID se zobrazí v seznamu, který vytvoříte. Pokud povolíte toto nastavení zásad v serveru vzdálené plochy, ovlivňuje zásady přesměrování zadané zařízení z klienta vzdálené plochy k serveru vzdálené plochy. Pokud zakážete nebo není pro toto nastavení zásad (nastavena na *povolit instalaci zařízení hardwaru*), můžete instalovat a aktualizovat jako povolené nebo mu podle dalších nastavení zásad zařízení.  

  **Výchozí**: Instalace bloku hardwaru zařízení  

  Když *služba neblokuje instalaci hardwaru zařízení* je vybráno, tato nastavení jsou k dispozici.
  - **Odeberte odpovídající hardwarové zařízení**  
    Toto nastavení je dostupná jenom v případě *instalace zařízení hardwaru pomocí identifikátorů zařízení* je nastavena na *služba neblokuje instalaci zařízení hardwaru*.  

    **Výchozí**: *Žádná výchozí konfigurace*

  - **Identifikátory hardwaru zařízení, které jsou blokovány**  
    Toto nastavení je dostupná jenom v případě *instalace zařízení hardwaru pomocí identifikátorů zařízení* je nastavena na *služba neblokuje instalaci zařízení hardwaru*. Pokud chcete nakonfigurovat toto nastavení, rozbalte možnost, vyberte **+ přidat**, a pak zadejte identifikátor hardwaru zařízení chcete blokovat.  

    **Výchozí**: *Žádné zařízení jsou zablokovaná*  

- **Blokovat přímý přístup do paměti**  
  [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess) – použití tohoto nastavení zásad můžete blokovat přímý přístup do paměti (DMA) pro všechny aktivní modulární PCI podřízené porty v zařízení, dokud se uživatel přihlásí do Windows. Jakmile se uživatel přihlásí, bude Windows výčet PCI zařízení připojená k portům PCI moduly hostitele. Pokaždé, když se uživatel uzamkne na počítači, DMA na portech PCI připojitelný zablokována se žádná zařízení. podřízené položky dokud znovu přihlásí uživatel. Zařízení, které byly již uvedené, když je počítač se odemkl. bude nadále fungovat, dokud byl odpojen. 

  Nastavení této zásady se vynucují jenom, když je povolené šifrování nástrojem BitLocker nebo zařízení.  

  **Výchozí**: Ano


- **Instalace hardwaru zařízení v nastavení tříd**  
  [DeviceInstallation/AllowInstallationOfMatchingDeviceSetupClasses](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdevicesetupclasses) – pomocí této zásady můžete určit seznam zařízení nastavit třídy globálně jedinečné identifikátory (GUID) pro ovladače zařízení, že je Windows zabráněno v instalaci. Toto nastavení zásad má přednost před jiného nastavení zásad, který umožňuje nainstalovat zařízení Windows. Pokud povolíte toto nastavení zásad (nastavena na *služba neblokuje instalaci zařízení hardwaru*), Windows je zabráněno v instalaci nebo aktualizaci ovladače zařízení, jehož zařízení nastavit třídy GUID se zobrazí v seznamu můžete vytvořit. Pokud povolíte toto nastavení zásad v serveru vzdálené plochy, nastavení zásad má vliv přesměrování zadané zařízení z klienta vzdálené plochy k serveru vzdálené plochy. Pokud zakážete nebo není pro toto nastavení zásad (nastavena na *povolit instalaci zařízení hardwaru*), můžete nainstalovat Windows a aktualizace zařízení povolený, nebo z důvodu dalších nastavení zásad.  

  **Výchozí**: Instalace bloku hardwaru zařízení

  Když *služba neblokuje instalaci hardwaru zařízení* je vybráno, tato nastavení jsou k dispozici.  

  - **Odeberte odpovídající hardwarové zařízení**  
    Toto nastavení je dostupná jenom v případě *instalace hardwaru zařízení v nastavení tříd* je nastavena na *služba neblokuje instalaci zařízení hardwaru*.  
 
    **Výchozí**: *Žádná výchozí konfigurace*  

  - **Identifikátory hardwaru zařízení, které jsou blokovány**  
    Toto nastavení je dostupné jenom v případě, že instalace hardwaru zařízení v nastavení tříd je nastavené blokování instalace hardwaru zařízení. Pokud chcete nakonfigurovat toto nastavení, rozbalte možnost, vyberte **+ přidat**, a pak zadejte identifikátor hardwaru zařízení chcete blokovat.  
 
    **Výchozí**: *Žádné zařízení jsou zablokovaná*

## <a name="endpoint-detection-and-response"></a>Koncový bod zjišťování a reakci  
Další informace najdete v tématu [WindowsAdvancedThreatProtection CSP](https://docs.microsoft.com/windows/client-management/mdm/windowsadvancedthreatprotection-csp) v dokumentaci k Windows.  

- **Zvýšit četnost hlášení telemetrie** - *konfigurace/TelemetryReportingFrequency*  

  Zvýšit četnost hlášení telemetrie rozšířené ochrany před internetovými útoky Defender Microsoft.  

  **Výchozí**: Ano

- **Sdílení ukázky pro všechny soubory** - *konfigurace/SampleSharing*  

  Vrátí nebo nastaví parametr konfigurace Microsoft Defender Advanced Threat Protection sdílení ukázky.  

  **Výchozí**: Ano

## <a name="exploit-protection"></a>Ochrana Exploit Protection  

- **Ochrana Exploit protection XML**  
  Další informace najdete v tématu [Import, export a nasaďte Konfigurace ochrany před zneužitím ](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/import-export-exploit-protection-emet-xml) v dokumentaci k Windows.  

  Umožňuje správci IT vydat konfigurace představující požadovaný systém, omezení rizik možnosti aplikace pro všechna zařízení v organizaci. Představuje konfiguraci XML. 

  Ochranu před zneužitím platí, pomáhá chránit zařízení před malwarem, který zneužití šíří a terčem útoků. Použijete aplikace Windows zabezpečení nebo prostředí PowerShell k vytvoření sadu omezení rizik (označované jako konfigurace). Pak můžete exportovat tuto konfiguraci jako soubor XML a sdílet ho s více počítači ve vaší síti všechny mají stejnou sadu nastavení zmírňování.
 
  Můžete také převést a importovat existující sada nástrojů EMET konfigurační soubor XML do konfiguraci ochrany před zneužitím XML.

- **Blok exploit protection přepsání**  
  [WindowsDefenderSecurityCenter/DisallowExploitProtectionOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsdefendersecuritycenter#windowsdefendersecuritycenter-disallowexploitprotectionoverride) – nastavte na *Ano* uživatelům zabránit v provádění změn oblast nastavení ochrany před zneužitím v Centru zabezpečení systému Windows Defender. Pokud zakážete nebo není pro toto nastavení, mohou místní uživatelé provádět změny v oblasti nastavení ochrany před zneužitím.  
  **Výchozí**: Ano  

- **Řízený přístup ke složkám**  
  Zobrazit [Defender/ControlledFolderAccessAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessallowedapplications) a [Defender/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) 
  
   Umožňuje chránit soubory a složky před neautorizovanými změnami od neznámých aplikací.

  **Výchozí**: Režim auditování

## <a name="web-network-protection"></a>Ochrana před webovými sítě  

- **Typ ochrany sítě**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) -této zásady umožňuje zapnout ochranu sítě nebo vypnout v systému Windows Defender Exploit Guard. Ochrana sítě je funkce Windows Defender ochrany Exploit Guard, která chrání zaměstnanci libovolnou aplikaci z podvodných přistupující, servery hostující zneužití a škodlivý obsah na Internetu. To zahrnuje, znemožní připojení k nebezpečné lokalit prohlížeče třetích stran.  

  Pokud je nastavena na hodnotu *povolit* nebo *režimu auditování*, uživatelé se nedá vypnout ochranu sítě a Windows Defender Security Center můžete použít k zobrazení informací o pokusy o připojení.  
 
  - *Povolit* zablokují, uživatelé a aplikace v připojení k doménám nebezpečné.  
  - *Režim auditování* nebrání uživatelů a aplikací v připojení k doménám nebezpečné.  

  Pokud je nastavena na *uživatelem definované*, uživatelů a aplikací nejsou blokované bránily v připojení k doménám nebezpečné a informace o připojení není k dispozici ve službě Windows Defender Security Center.  

  **Výchozí**: Režim auditování

- **Vyžadovat SmartScreen pro Microsoft Edge**  
  [Prohlížeč/AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) – Microsoft Edge k ochraně uživatelů před podvodných potenciální a škodlivým softwarem ve výchozím nastavení používá Windows Defender SmartScreen (zapnuto). Ve výchozím nastavení, je tato zásada povolená (nastavena na *Ano*) a obrysů zabraňuje uživatelům v vypnutí filtru Windows Defender SmartScreen.  Pokud platné zásady pro zařízení se rovná není nakonfigurováno, uživatelé ji vypnout Windows Defender SmartScreen, což zanechá zařízení bez ochrany.  

  **Výchozí**: Ano
  
- **Blokovat přístup na škodlivý web**  
  [Prohlížeč/PreventSmartScreenPromptOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride) – Microsoft Edge ve výchozím nastavení, umožňují uživatelům obejít (Ignorovat) upozornění filtru Windows Defender SmartScreen potenciálně škodlivé weby, uživatelé si můžou pokračovat na web. Tato zásada povolená (nastavena na *Ano*), Microsoft Edge zabraňuje uživatelům obcházet upozornění a blokuje pokračování k webu.  

  **Výchozí**: Ano

- **Blokovat stahování neověřených souborů**  
  [Prohlížeč/PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles) – Microsoft Edge ve výchozím nastavení, umožňují uživatelům obejít (Ignorovat) upozornění filtru Windows Defender SmartScreen o potenciálně škodlivých souborů, což jim umožní pokračovat ve stahování neověřených soubory. Tato zásada povolená (nastavena na *Ano*), uživatelé nemají obejít upozornění a nemůže stahovat neověřené soubory.  

  **Výchozí**: Ano

## <a name="windows-defender-anti-virus----settings-review-pending-for-this-section"></a>Windows Defender antivirový program [Nastavení kontroly až do této části]

Další informace najdete v tématu [zásady CSP – Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) v dokumentaci k Windows.

- **Kontrolovat skripty načtené do webových prohlížečů Microsoftu**  
  [Defender/AllowScriptScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning) – nastavte na *Ano* povolit prověřování skriptů Windows Defender funkce.  

  **Výchozí**: Ano

- **Kontrolovat příchozí e-mailové zprávy**  
  [Defender/AllowEmailScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) – nastavte na *Ano* umožňuje Windows Defenderu kontrolovat e-mailu.  

  **Výchozí**: Ano

- **Typ souhlasu odeslání vzorku defenderu**  
  [Defender/SubmitSamplesConsent](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) – úroveň v programu Windows Defender k odesílání dat souhlas kontroly pro daného uživatele. Pokud již bylo uděleno vyžaduje souhlas, program Windows Defender odešle je. Pokud tomu tak není (a pokud uživatel zadal nikdy se zeptat), požádejte ho o souhlas uživatele se spustí uživatelské rozhraní (při *Cloudová ochrana* je nastavena na *Ano*) před odesláním údajů.  

  **Výchozí**: Posílat bezpečné vzorky automaticky

- **Systém kontroly sítě (NIS)**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) – blokovat nebezpečný provoz detekovaný podle podpisů v systému kontroly sítě (NIS).  
 
  **Výchozí**: Ano

- **Interval aktualizace podpisu (v hodinách)**  
  [Defender/SignatureUpdateInterval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) – zadejte v řádu hodin, jak často zařízení vyhledává nové aktualizace signatura Defenderu.  
 
  **Výchozí**: 4

- **Konfigurace s nízkou prioritou procesoru pro plánované kontroly**  
  [Defender/EnableLowCPUPriority](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority) – Pokud je nastavena na *Ano*, priorita procesoru pro kontroly nastavená na nízkou prioritu. Když *Nenakonfigurováno*, nebudou provedeny žádné změny k Priorita procesoru pro plánované kontroly.  

    **Výchozí**: Ano

- **Blok Defender ochrana při přístupu**  
  [Defender/AllowOnAccessProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowonaccessprotection) – Pokud je nastavena na *Ano*, je povoleno na přístup k ochraně programu Windows Defender.  

  **Výchozí**: Ano

- **Typ systémové kontroly k provedení**  
  [Defender/ScanParameter](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter) -Defender typu.  

  **Výchozí**: Rychlá kontrola

- **Kontrolovat všechny stahované soubory**  
  [Defender/AllowIOAVProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection) – Pokud je nastavena na *Ano*, bude Defender kontrolovat všechny stahované soubory a přílohy.  

  **Výchozí**: Ano

- **Počet dní před odstraněním malwaru v karanténě**  
  [Defender/DaysToRetainCleanedMalware](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) – zadejte počet dnů do zachovat položky karantény v systému, než se automaticky odstraní. Pokud je nastavený na hodnotu nula, jsou položky v karanténě nikdy automaticky odstraní.  

  **Výchozí**: 0

- **Čas zahájení naplánovaných prohledávání**  
  [Defender/ScheduleScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime) – naplánovat čas programu Defender kontrolovat zařízení. 
  
  Příslušnou možnost v tomto seznamu: *Defender/ScheduleScanDay*   

  **Výchozí**: 2 AM

- **Cloudová ochrana**  
  [Defender/AllowCloudProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) – Pokud je nastavena na *Ano*, program Windows Defender odesílá společnosti Microsoft informace o všech problémech, které nalezne. Microsoft tyto informace analyzuje, další informace o problémy s vámi a další zákazníky a nabízet lepší řešení.

  Pokud je tato zásada nastavená na *Ano*, můžete použít *typ souhlasu odeslání vzorku Defender* a poskytuje tak uživatelům kontrolu nad odesílání informací ze svého zařízení.  

  **Výchozí**: Ano

- **Defender potenciálně nežádoucí aplikace akce**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection) – antivirové ochrany v programu Windows Defender může identifikovat a blokovat *potenciálně nežádoucí aplikace* (ochraně) zablokovat stahování a instalaci na koncových bodech vaší sítě. 
 
  - Pokud je nastavena na *bloku*, blokuje ochraně programu Windows Defender a seznamů v historii spolu s dalšími hrozbami.
  - Pokud je nastavena na *auditu*, program Windows defender zjistí ochraně, ale nebude bránit. Informace o aplikacích, které program Windows Defender by trvalo opatření proti najdete tak, že pro události, které byly vytvořeny pomocí programu Windows Defender v události prohlížeč.  
  - Pokud je nastavena na *výchozí ze zařízení*, PUA ochrany je vypnuté.  
 
  **Výchozí**: Zablokovat

- **Cloud Defender rozšířené vypršení časového limitu**  
  [Defender/CloudExtendedTimeout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout) -zadat maximální dobu, další dobu, kterou je antivirová ochrana v programu Windows Defender měla blokovat soubor při čekání na výsledek z cloudu. Základní množství času, které program Windows Defender čeká je 10 sekund. Dodatečná doba, kterou zde zadáte (až 50 sekund) se přidá k těmto 10 sekundám. Ve většině případů kontrola trvá méně času než maximální délka. Prodloužení doby umožňuje, aby cloud podezřelé soubory důkladně prozkoumal.  

  Ve výchozím nastavení je rozbalený časová hodnota 0 (zakázáno). Doporučuje se v Intune povolíte toto nastavení a zadat alespoň 20 dalších sekund.  
 
  **Výchozí**: 0

- **Prohledat archivní soubory**  
  [Defender/AllowArchiveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning) – nastavte na *Ano* mít Windows Defenderu kontrolovat archivované soubory.  

  **Výchozí**: Ano

- **Naplánování prohledání systému defenderu**  
  [Defender/ScheduleScanDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday) -plán den, kdy bude Defender kontrolovat zařízení. 
 
  Příslušnou možnost v tomto seznamu: *Defender/ScheduleScanTime*

  **Výchozí**: definováno uživatelem

- **Monitorování chování**  
  [Defender/AllowBehaviorMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring) – nastavte na *Ano* zapnout funkci monitorování chování Windows Defender. Vložený ve Windows 10, monitorování chování Windows Defender senzorů shromažďovat a zpracovávat chování signály od operačního systému a odesílat tato data ze senzorů k vaší instanci cloudu privátní, izolované, z ochrany ATP v programu Defender Microsoft.  

  **Výchozí**: Ano

- **Kontrolovat soubory otevřené ze síťových složek**  
  [Defender/AllowScanningNetworkFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) – nastavte na *Ano* mít Windows Defenderu kontrolovat soubory v síti. Uživatel nebude možné odebrání zjištěného malwaru souborů jen pro čtení.  

  **Výchozí**: Ano

- **Defender cloudu blok úroveň**  
  [Defender/CloudBlockLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel) – použijte tato zásada určit způsob, jakým agresivní antivirové ochrany Windows Defender je blokuje a skenování podezřelé soubory. Vaše možnosti jsou:

  - Vysoká - agresivně blokovat neznámé soubory a optimalizovat výkon klienta (větší pravděpodobnost výskytu falešně pozitivních testů)
  - Vysoká plus - agresivně blokovat neznámé soubory a použití dalšími ochrannými opatřeními (může mít vliv na výkon klienta)
  - Žádná tolerance – blokovat všechny neznámé spustitelné soubory

  **Výchozí**: Nenakonfigurováno

- **Monitorování v reálném čase**  
  [Defender/AllowRealtimeMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring) – nastavte na *Ano* povolit monitorování v reálném čase Windows Defender.  

  **Výchozí**: Ano

- **Limit využití procesoru při prověřování**  
  [Defender/AvgCPULoadFactor](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor) – určete maximální, průměrné zatížení procesoru % využití, program Windows Defender můžete použít při kontrole.  

  **Výchozí**: 50

- **Kontrolovat namapované síťové jednotky během úplného prohledávání**  
  [Defender/AllowFullScanOnMappedNetworkDrives](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanonmappednetworkdrives) – nastavte na *Ano* mít Windows Defenderu kontrolovat soubory v síti. Uživatel nemůže odebrat zjištěného malwaru ze souborů jen pro čtení

  Související nastavení v tomto seznamu: *Defender/AllowScanningNetworkFiles*

  **Výchozí**: Ano

- **Blokovat přístup koncového uživatele k Defenderu**  
  [Defender/AllowUserUIAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowuseruiaccess) – nastavte na *Ano* a koncovým uživatelům zablokovat přístup na uživatelské rozhraní Windows Defenderu na svém zařízení.  

  **Výchozí**: Ano

- **Počáteční čas rychlé kontroly**  
  [Defender/ScheduleQuickScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) -naplánovat denní dobu pro Defender tak, aby spustila rychlou kontrolu.  

  **Výchozí**: 2 AM

## <a name="windows-defender-firewall"></a>Firewall v programu Windows Defender
Další informace najdete v tématu [CSP brány Firewall](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) v dokumentaci k Windows.

- **Doba nečinnosti přidružení zabezpečení před odstraněním** - *MdmStore/Global/SaIdleTime*   
  Přidružení zabezpečení se odstraní po síťový provoz se nezobrazuje pro tento počet sekund.  
  **Výchozí**: 300

- **File Transfer Protocol** - *MdmStore/Global/DisableStatefulFtp*   
  Zablokuje stavový protokol FTP (File Transfer).  
  **Výchozí**: Ano

- **Fronty paketů** - *MdmStore/Global/EnablePacketQueue*    
  Určete, jak povoluje škálování softwaru na straně příjmu se šifrovaným příjmem a předáváním nešifrovaného textu pro scénář bránu tunelového propojení IPsec. Tím se zajistí zachování pořadí paketů.  
  **Výchozí**: Výchozí ze zařízení

- **Brány firewall na profil domény** - *FirewallRules/FirewallRuleName/profily*  
  Určuje profily, do kterých se pravidlo patří: Domain, Private, Public. Tato hodnota představuje profil sítě, které jsou připojené k doménám.  

  Dostupná nastavení:  
  - **Jednosměrové odpovědi na vícesměrová vysílání vyžaduje**  
    **Výchozí**: Ano

  - **Sloučení pravidel autorizovaných aplikací ze zásad skupiny**  
    **Výchozí**: Ano

  - **Příchozí upozornění blokované**  
    **Výchozí**: Ano

  - **Sloučení pravidel globální portu ze zásad skupiny**  
    **Výchozí**: Ano

  - **Neviditelný režim blokované**  
    **Výchozí**: Ano

  - **Povolenou bránu firewall**  
    **Výchozí**: Povoleno

  - **Pravidla zabezpečení připojení ze zásad skupiny, které nebyly sloučeny**  
    **Výchozí**: Ano

  - **Pravidla zásad ze zásad skupiny, které nebyly sloučeny**  
    **Výchozí**: Ano

- **Veřejný profil s branou firewall** - *FirewallRules/FirewallRuleName/profily*  
  Určuje profily, do kterých se pravidlo patří: Domain, Private, Public. Tato hodnota představuje profil pro veřejné sítě. Tyto sítě jsou klasifikovány jako veřejné správci v hostitelském serveru. Klasifikace se stane při prvním hostitele připojí k síti. Obvykle se tyto sítě na letištích, kavárny a jiných veřejných místech, kde nejsou partnerské uzly v síti nebo správce sítě důvěryhodné.  

  Dostupná nastavení:

  - **Příchozí připojení blokováno**  
    **Výchozí**: Ano 

  - **Jednosměrové odpovědi na vícesměrová vysílání vyžaduje**  
    **Výchozí**: Ano  

  - **Neviditelný režim vyžadované**  
    **Výchozí**: Ano 
 
  - **Odchozí připojení vyžaduje**  
    **Výchozí**: Ano  

  - **Sloučení pravidel autorizovaných aplikací ze zásad skupiny**  
    **Výchozí**: Ano  

  - **Příchozí upozornění blokované**  
    **Výchozí**: Ano  

  - **Sloučení pravidel globální portu ze zásad skupiny**  
    **Výchozí**: Ano

  - **Neviditelný režim blokované**  
    **Výchozí**: Ano

  - **Povolenou bránu firewall**  
    **Výchozí**: Povoleno  

  - **Pravidla zabezpečení připojení ze zásad skupiny, které nebyly sloučeny**  
    **Výchozí**: Ano  

  - **Příchozí provoz vyžaduje**  
    **Výchozí**: Ano

  - **Pravidla zásad ze zásad skupiny, které nebyly sloučeny**  
    **Výchozí**: Ano  

- **Privátní profil brány firewall** - *FirewallRules/FirewallRuleName/profily*  
  Určuje profily, do kterých se pravidlo patří: Domain, Private, Public. Tato hodnota představuje profil pro privátní sítě.  

  Dostupná nastavení: 

  - **Příchozí připojení blokováno**  
    **Výchozí**: Ano

  - **Jednosměrové odpovědi na vícesměrová vysílání vyžaduje**  
    **Výchozí**: Ano

  - **Neviditelný režim vyžadované**  
    **Výchozí**: Ano

  - **Odchozí připojení vyžaduje**  
    **Výchozí**: Ano

  - **Příchozí upozornění blokované**  
    **Výchozí**: Ano

  - **Sloučení pravidel globální portu ze zásad skupiny**  
    **Výchozí**: Ano

  - **Neviditelný režim blokované**  
    **Výchozí**: Ano  

  - **Povolenou bránu firewall**  
    **Výchozí**: Povoleno

  - **Pravidla autorizovaných aplikací ze zásad skupiny, které nebyly sloučeny**  
    **Výchozí**: Ano

  - **Pravidla zabezpečení připojení ze zásad skupiny, které nebyly sloučeny**  
    **Výchozí**: Ano

  - **Příchozí provoz vyžaduje**  
    **Výchozí**: Ano

  - **Pravidla zásad ze zásad skupiny, které nebyly sloučeny**  
    **Výchozí**: Ano  

- **Brána firewall pre sdílené klíče kódování – metoda**  
  **Výchozí**: UTF8

- **Ověření seznamu odvolaných certifikátů**  
  **Výchozí**: Výchozí ze zařízení

## <a name="windows-hello-for-business"></a>Windows Hello pro firmy  

Další informace najdete v tématu [PassportForWork CSP](https://docs.microsoft.com/windows/client-management/mdm/passportforwork-csp) v dokumentaci k Windows.

- **Konfigurovat Windows Hello pro firmy** - *TenantId/zásady/UsePassportForWork*    
  Windows Hello pro firmy je alternativní metoda pro přihlašování do Windows tak, že nahradíte hesla, čipové karty a virtuální čipové karty.  

  Pokud povolíte nebo není pro toto nastavení zásad zařízení zřídí Windows Hello pro firmy. Pokud nastavení této zásady zakážete, zařízení nezřizuje Windows Hello pro firmy pro libovolného uživatele.

  Intune nepodporuje zakázat Windows Hello. Místo toho můžete nakonfigurovat zásady Povolit Windows Hello pro firmy (Ano) nebo konfigurovat Windows Hello přímo (Nenakonfigurováno). Pokud není nakonfigurováno, zařízení může získat konfiguraci prostřednictvím jiné zásady, které může povolit nebo zakázat tuto funkci.  

  **Výchozí**: Ano  

- **Vyžadovat v PIN kódu malá písmena** - *TenantId/zásady/PINComplexity/LowercaseLetters*  
  **Výchozí**: Povoleno  

- **Vyžadovat v PIN kódu speciální znaky** - *TenantId/zásady/PINComplexity/SpecialCharacters*  
  **Výchozí**: Povoleno  

- **Vyžadovat v PIN kódu velká písmena** - *TenantId/zásady/PINComplexity/UppercaseLetters*   
  **Výchozí**: Povoleno  

