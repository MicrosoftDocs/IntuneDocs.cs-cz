---
title: Nastavení standardních hodnot zabezpečení v Intune pro rozšířenou ochranu před internetovými útoky v programu Microsoft Defender
titleSuffix: Microsoft Intune
description: Nastavení standardních hodnot zabezpečení, které Intune podporuje pro správu rozšířené ochrany před internetovými útoky v programu Microsoft Defender
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2019
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
ms.openlocfilehash: eee3d4187dd513cd3945e86aff478fe96b341660
ms.sourcegitcommit: 1d4aec7b79c70d35ec3fc29df6ff9c6a1403412e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2019
ms.locfileid: "68491919"
---
# <a name="microsoft-defender-advanced-threat-protection-baseline-settings-for-intune"></a>Základní nastavení pro Intune v programu Microsoft Defender Advanced Threat Protection

Podívejte se na základní nastavení služby Microsoft Defender Advanced Threat Protection (dříve v programu Windows Defender Advanced Threat Protection), které podporuje Microsoft Intune. Výchozí hodnoty standardních hodnot rozšířené ochrany před internetovými útoky (ATP) znázorňují doporučenou konfiguraci ATP a nemusí odpovídat výchozím hodnotám pro jiné standardní hodnoty zabezpečení.  

Směrný plán rozšířené ochrany před internetovými útoky v programu Microsoft Defender je dostupný, když vaše prostředí splňuje požadavky na používání [rozšířené ochrany před internetovými útoky v programu Microsoft Defender](advanced-threat-protection.md#prerequisites). 

Tato standardní hodnota je optimalizovaná pro fyzická zařízení a v tuto chvíli se nedoporučuje používat na virtuálních počítačích (VM) nebo koncových bodech VDI. Určitá nastavení standardních hodnot můžou mít vliv na vzdálené interaktivní relace ve virtualizovaných prostředích. Další informace najdete v dokumentaci k Windows v tématu [zvýšení dodržování předpisů pro základní hodnoty zabezpečení služby Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline) .


> [!NOTE]  
> Základní nastavení ATP je ve **verzi Preview**. I když je ve verzi Preview seznam dostupných nastavení a pořadí, ve kterém tento obsah prezentuje tato nastavení, nemusí odpovídat tomu, co je dostupné na portálu.  
>
> Pokud jsou nastavení standardních hodnot mimo verzi Preview, bude se tento obsah aktualizovat tak, aby odrážel aktuální seznam nastavení standardních hodnot zabezpečení, které Intune podporuje.

## <a name="application-guard"></a>Ochrana Application Guard  
Další informace najdete v tématu [WINDOWSDEFENDERAPPLICATIONGUARD CSP](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp) v dokumentaci k systému Windows.  

Při používání Microsoft Edge Aplikace Microsoft Defender Application Guard chrání vaše prostředí od webů, které nedůvěřují vaší organizaci. Když uživatelé navštíví weby, které nejsou uvedené ve vaší izolované síti, lokality se otevřou v rámci virtuální relace procházení technologie Hyper-V. Důvěryhodné lokality jsou definovány pomocí hranice sítě.  

- **Nastavení ochrany Application Guard** -  */AllowWindowsDefenderApplicationGuard*  
  Pokud chcete tuto funkci zapnout, vyberte *Ano* . tím se otevřou nedůvěryhodné weby v kontejneru procházení virtualizované technologie Hyper-V. Pokud je nastavená na nenakonfigurovaná, v zařízení se otevře libovolná lokalita (důvěryhodná a nedůvěryhodná), a ne v virtualizovaném kontejneru.  

  **Výchozí**: Ano
 
  - **Externí obsah na podnikových serverech** - *Nastavení/BlockNonEnterpriseContent*  
    Vyberte *Ano* , pokud chcete zablokovat obsah před načtením z neschválených webů. Pokud je nastavené na *není nakonfigurované*, můžou se v zařízení otevřít nepodnikové lokality. 
 
    **Výchozí**: Ano

  - **Nastavení chování** - schránky */ClipboardSettings*  
    Vyberte, které akce kopírování a vkládání jsou povolené mezi místním počítačem a virtuálním prohlížečem Application Guard.  Vaše možnosti jsou:
    - *Není nakonfigurováno*  
    - *Blokování obou* dat: mezi počítačem a virtuálním prohlížečem nejde přenášet data.  
    - *Blokovat hostitele do kontejneru* – data nejde přenést z počítače do virtuálního prohlížeče.
    - *Blokování kontejneru do hostitele* – data se nemůžou přenášet z virtuálního prohlížeče na hostitelský počítač.
    - *Blokovat žádné* – žádný blok pro obsah neexistuje.  

    **Výchozí**: Blokovat obojí  

- **Zásady izolace sítě Windows – názvy podnikových síťových domén**  
  Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – NetworkIsolation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-networkisolation) .
  
  Zadejte seznam podnikových prostředků jako domény, rozsahy IP adres a hranice sítě, které jsou hostované v cloudu, který Application Guard považuje za podnikové lokality.  

  **Výchozí**: SecurityCenter.Windows.com

## <a name="application-reputation"></a>Reputace aplikace  

Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – filtr](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) .

- **Zablokovat provádění neověřených souborů**  
    Zablokuje uživateli spouštění neověřených souborů. Pokud je nastavení nastaveno na Nenakonfigurováno, zaměstnanci můžou ignorovat upozornění filtru SmartScreen a spouštět škodlivé soubory. Nastavte na *Ano* , aby zaměstnanci nemohli ignorovat upozornění filtru SmartScreen a spouštět škodlivé soubory.  
  
    **Výchozí**: Ano

- **Vyžadovat filtr SmartScreen pro aplikace a soubory**  
  Nastavte na *Ano* , pokud chcete povolit filtr SmartScreen pro Windows.  

  **Výchozí**: Ano

## <a name="attack-surface-reduction"></a>Omezení možností útoku  

- **Typ podřízeného procesu, který spouští aplikace Office**  
  [Pravidlo pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Pokud je tato možnost nastavená na *blokovat*, nebudou moct aplikace Office vytvářet podřízené procesy. Aplikace Office zahrnují Word, Excel, PowerPoint, OneNote a Access. Vytvoření podřízeného procesu je typické chování při malwaru, zejména u útoků založených na makrech, které se pokoušejí použít aplikace Office ke spouštění nebo stahování škodlivých spustitelných souborů.  

  **Výchozí**: Zablokovat

- **Typ spuštění datové části staženého skriptu**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection) – určete úroveň detekce potenciálně nežádoucích aplikací, které se stahují nebo pokoušejí nainstalovat.  

  **Výchozí**: Zablokovat 

- **Zabránit krádeži pověření typu**  
  Nastavením této  možnost povolíte [ochranu odvozených přihlašovacích údajů domény s ochranou přihlašovacích údajů](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard). Ochrana Credential Guard v programu Windows Defender používá zabezpečení na základě virtualizace k izolaci tajných kódů, aby k nim měli přístup jenom privilegovaný systémový software. Neoprávněný přístup k těmto tajným kódům může vést k útokům využívajícím krádež přihlašovacích údajů, jako je například Pass-the-Hash nebo Pass-The-Ticket. Ochrana Credential Guard v programu Windows Defender brání těmto útokům ochranou hodnot hash hesel protokolu NTLM, lístků pro udělení lístku Kerberos a přihlašovacích údajů uložených aplikacemi jako přihlašovací údaje domény.  

  **Výchozí**: Povolení

- **Typ provedení obsahu e-mailu**  
  [Pravidlo pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Pokud je nastaveno na *blokovat*, toto pravidlo blokuje spouštění nebo spouštění těchto typů souborů z e-mailu, který se zobrazuje v aplikaci Microsoft Outlook nebo webové pošty (například Gmail.com nebo Outlook.com):  

  - Spustitelné soubory (například. exe,. dll nebo. scr)  
  - Soubory skriptu (například PowerShell. PS, VisualBasic. vbs nebo JavaScript. js)  
  - Soubory archivu skriptu  

  **Výchozí**: Zablokovat

- **Spuštění aplikace Adobe Reader v podřízeném procesu**  
  [Pravidlo pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – *Povolit* tomuto pravidlu blokovat vytváření podřízeného procesu aplikaci Adobe Reader. Prostřednictvím sociálního inženýrství nebo zneužití může malware stahovat a spouštět další datové části a přerušit z aplikace Adobe Reader.  

  **Výchozí**: Povolení

- **Typ kódu makra zakódováného skriptu**  
  [Pravidlo pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – malware a další hrozby se mohou pokusit dekódovat nebo skrýt škodlivý kód v některých souborech skriptu. Toto pravidlo zabrání spuštění skriptů, které se jeví jako nepoužívané.  
    
  **Výchozí**: Zablokovat

- **Nedůvěryhodný typ procesu USB**  
  [Pravidlo pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – když se nastaví *blokování*, nepodepsané nebo nedůvěryhodné spustitelné soubory z vyměnitelných jednotek USB a karty SD nejdou spustit.

  Mezi spustitelné soubory patří:
  - Spustitelné soubory (například. exe,. dll nebo. scr)
  - Soubory skriptu (například PowerShell. PS, VisualBasic. vbs nebo JavaScript. js)  

  **Výchozí**: Zablokovat

- **Typ injektáže jiného procesu aplikací Office**  
  [Pravidlo pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – když se nastaví *blokování*, aplikace Office, včetně Wordu, Excelu, PowerPointu a OneNotu, nejde vložit kód do jiných procesů. Vkládání kódu obvykle používá malware ke spouštění škodlivého kódu při pokusu o skrytí aktivity z skenovacích modulů antivirového programu.  

  **Výchozí**: Zablokovat

- **Kód makra Office Allow import typu Win32**  
  [Pravidlo pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Pokud je nastaveno na *blokovat*, toto pravidlo se pokusí blokovat soubory Office, které obsahují kód makra, který může importovat knihovny DLL Win32. Soubory Office zahrnují Word, Excel, PowerPoint a OneNote. Malware může pomocí kódu makra v souborech Office importovat a načítat knihovny DLL Win32, které se pak používají k umožnění dalších infekcí v celém systému v rámci volání rozhraní API.  

  **Výchozí**: Zablokovat

- **Aplikace Office Communications se spouští v podřízeném procesu**  
  [Pravidlo pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Pokud je nastaveno na *Povolit*, toto pravidlo zabrání aplikaci Outlook v vytváření podřízených procesů. Blokováním vytvoření podřízeného procesu toto pravidlo chrání proti útokům prostřednictvím sociálního inženýrství a brání zneužití kódu v aplikaci Outlook k zneužití ohrožení zabezpečení.  

  **Výchozí**: Povolení

- **Typ vytvoření nebo spuštění obsahu aplikací Office**  
  [Pravidlo pro omezení možností útoku](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Pokud je nastavené *blokování*, aplikace Office nemůžou vytvářet spustitelný obsah. Aplikace Office zahrnují Word, Excel, PowerPoint, OneNote a Access.  

  Toto pravidlo cílí na typické chování používané podezřelými a zlomyslnými doplňky a skripty (rozšíření), které vytvářejí nebo spouštějí spustitelné soubory. Toto je typická antimalwarová technika. Používání rozšíření je pro aplikace Office blokované. Tato rozšíření obvykle používají skripty Windows Scripting Host (soubory. WSH) ke spouštění skriptů, které automatizují určité úlohy nebo poskytují uživatelsky vytvořené funkce doplňku.

  **Výchozí**: Zablokovat

## <a name="bitlocker"></a>BitLocker  

Další informace najdete v dokumentaci k Windows v části [nastavení zásady skupiny BitLockeru](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) .  

- **Šifrovat zařízení**  
  Vyberte *Ano* , pokud chcete povolit šifrování zařízení nástrojem BitLocker. V závislosti na hardwaru zařízení a verzi Windows můžou být uživatelé zařízení požádáni o potvrzení, že zařízení nemá žádné šifrování třetích stran. Zapnutí šifrování Windows, když je aktivní šifrování třetích stran, vykreslí nestabilní zařízení.  

   **Výchozí**: Ano

- **Zásada pro vyměnitelné jednotky služby bit Lock**  
  Hodnoty pro tuto zásadu určují sílu šifry, kterou BitLocker používá k šifrování vyměnitelných jednotek. Podniky řídí úroveň šifrování pro zvýšené zabezpečení (AES-256 je silnější než AES-128). Pokud pro povolení tohoto nastavení vyberete *Ano* , můžete nakonfigurovat šifrovací algoritmus a složitost klíče pro pevné datové jednotky, jednotky operačního systému a vyměnitelné datové jednotky jednotlivě. U pevných jednotek operačního systému doporučujeme použít algoritmus XTS-AES. U vyměnitelných jednotek byste měli použít algoritmus AES-CBC 128-bit nebo AES-CBC 256-bit, pokud se jednotka používá v jiných zařízeních, na kterých běží Windows 10, verze 1511 nebo novější. Změna metody šifrování nemá žádný vliv, pokud je jednotka již zašifrovaná nebo pokud probíhá šifrování. V těchto případech se nastavení této zásady ignoruje. 

  V případě zásad vyměnitelného disku pro službu bit Lock nakonfigurujte následující nastavení:

  - **Vyžadovat šifrování pro přístup pro zápis**  
    **Výchozí**: Ano

  - **Metoda šifrování**  
    **Výchozí**: 128bit CBC AES

- **Zásada pro pevný disk pro nastavení bitových zámků**  
  Hodnoty pro tuto zásadu určují sílu šifry, kterou BitLocker používá k šifrování pevných jednotek. Podniky můžou řídit úroveň šifrování pro zvýšené zabezpečení (AES-256 je silnější než AES-128). Pokud povolíte toto nastavení, můžete nakonfigurovat šifrovací algoritmus a složitost klíče pro pevné datové jednotky, jednotky operačního systému a vyměnitelné datové jednotky. U pevných jednotek operačního systému doporučujeme použít algoritmus XTS-AES. U vyměnitelných jednotek byste měli použít algoritmus AES-CBC 128-bit nebo AES-CBC 256-bit, pokud se jednotka používá v jiných zařízeních, na kterých běží Windows 10, verze 1511 nebo novější. Změna metody šifrování nemá žádný vliv, pokud je jednotka již zašifrovaná nebo pokud probíhá šifrování. V těchto případech se nastavení této zásady ignoruje.

  U zásad pevného disku pro pevný zámek nakonfigurujte následující nastavení:

  - **Vyžadovat šifrování pro přístup pro zápis**  
    **Výchozí**: Ano

  - **Metoda šifrování**  
    **Výchozí**: 128bit XTS AES

- **Zásady systémových jednotek systému bitových zámků**  
  Hodnoty pro tuto zásadu určují sílu šifry, kterou BitLocker používá k šifrování systémové jednotky. Podniky můžou chtít řídit úroveň šifrování pro zvýšené zabezpečení (AES-256 je silnější než AES-128). Pokud povolíte toto nastavení, můžete nakonfigurovat šifrovací algoritmus a složitost klíče pro pevné datové jednotky, jednotky operačního systému a vyměnitelné datové jednotky. U pevných jednotek operačního systému doporučujeme použít algoritmus XTS-AES. U vyměnitelných jednotek byste měli použít algoritmus AES-CBC 128-bit nebo AES-CBC 256-bit, pokud se jednotka používá v jiných zařízeních, na kterých běží Windows 10, verze 1511 nebo novější. Změna metody šifrování nemá žádný vliv, pokud je jednotka již zašifrovaná nebo pokud probíhá šifrování. V těchto případech se nastavení této zásady ignoruje.  

  U zásad systémových jednotek systému bitových zámků nakonfigurujte následující nastavení:  

  - **Metoda šifrování**  
    **Výchozí**: 128bit XTS AES

## <a name="device-control"></a>Řízení zařízení  

- **Kontrolovat vyměnitelné jednotky během úplného prohledávání**  
  [Defender/AllowFullScanRemovableDriveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) – Pokud je tato hodnota nastavená na *Ano*, Defender při úplné kontrole vyhledává škodlivý a nežádoucí software ve vyměnitelných jednotkách, jako jsou jednotky Flash. Antivirová ochrana v programu Defender kontroluje všechny soubory na zařízeních USB předtím, než je možné spustit soubory na zařízení USB.

  Související nastavení v tomto seznamu: *Defender/AllowFullScanOnMappedNetworkDrives*  

  **Výchozí**: Ano

- **Výčet externích zařízení nekompatibilních s režimem ochrany DMA v jádře**  
   Viz *DmaGuard/DeviceEnumerationPolicy* v [zásadách CSP – DmaGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  Tato zásada poskytuje další zabezpečení proti externímu zařízení podporujícím technologii DMA. Umožňuje lepší kontrolu nad výčtem externích zařízení podporujících technologii DMA, která nejsou kompatibilní s izolací paměti zařízení DMA a sandboxing.

  Tato zásada se projeví jenom v případě, že je ochrana DMA pro jádro podporovaná a povolená systémovým firmwarem. Ochrana před/s rozhraním DMA je funkce platformy, kterou nemůže řídit zásada ani uživatel zařízení. Musí být podporovaný systémem v době výroby. 

  Chcete-li zkontrolovat, zda systém podporuje ochranu před režimem DMA, spusťte příkaz MSINFO32. exe v systému a na stránce Souhrn zkontrolujte pole *ochrana jádra DMA* .  

  Vaše možnosti jsou: 
  - *Výchozí nastavení zařízení* – po přihlášení nebo odemknutí obrazovky se můžou kdykoli zobrazit výčet zařízení s přemapováním DMA na kompatibilní ovladače. Zařízení s přemapováním DMA na nekompatibilní ovladače se zobrazí jenom poté, co uživatel odemkne obrazovku.
  - Možnost *povolení všech* externích zařízení s podporou přímého přístupu do paměti (DMA) se v každém okamžiku vyčíslí.
  - *Blokování všech* zařízení s přemapováním DMA kompatibilních ovladačů se smí kdykoli zobrazit. Zařízení s přemapováním DMA na nekompatibilní ovladače nikdy nebudou moct spouštět a používat DMA kdykoli.

  **Výchozí**: Výchozí nastavení zařízení

- **Instalace hardwarových zařízení podle identifikátorů zařízení**  
  [DeviceInstallation/PreventInstallationOfMatchingDeviceIDs](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceids) – pomocí této zásady určíte seznam technologie Plug and Play ID hardwaru a kompatibilní ID pro zařízení, na která se systém Windows brání v instalaci. Nastavení této zásady má přednost před jinými nastaveními zásad, která umožňují systému Windows nainstalovat zařízení. Pokud toto nastavení zásad povolíte (nastavíte k *blokování instalace hardwarového zařízení*), Windows se znemožní nainstalovat zařízení, jehož ID hardwaru nebo kompatibilní ID se zobrazí v seznamu, který vytvoříte. Pokud nastavení této zásady povolíte na vzdáleném počítači, zásada má vliv na přesměrování zadaných zařízení z klienta vzdálené plochy na server vzdálené plochy. Pokud nastavení této zásady zakážete nebo nenakonfigurujete (nastavíte možnost *Povolit instalaci hardwarového zařízení*), zařízení mohou instalovat a aktualizovat, jak je povoleno nebo zakázáno jinými nastaveními zásad.  

  **Výchozí**: Blokovat instalaci hardwarového zařízení  

  Když je vybraná možnost *blokovat instalaci hardwarového zařízení* , jsou k dispozici následující nastavení.
  - **Odebrat shodná hardwarová zařízení**  
    Toto nastavení je dostupné, jenom když je *Instalace hardwarového zařízení podle identifikátorů zařízení* nastavená tak, aby *blokovala instalaci hardwarového zařízení*.  

    **Výchozí**: *Žádná výchozí konfigurace*

  - **Blokované identifikátory hardwarových zařízení**  
    Toto nastavení je dostupné, jenom když je *Instalace hardwarového zařízení podle identifikátorů zařízení* nastavená tak, aby *blokovala instalaci hardwarového zařízení*. Pokud chcete nakonfigurovat toto nastavení, rozbalte možnost, vyberte **+ Přidat**a pak zadejte identifikátor hardwarového zařízení, který chcete blokovat.  

    **Výchozí**: *Žádná zařízení nejsou blokovaná.*  

- **Zablokovat přímý přístup do paměti**  
  [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess) – pomocí tohoto nastavení zásad můžete zablokovat přímý přístup do paměti (DMA) pro všechny horké porty PCI pro příjem dat na zařízení, dokud se uživatel nepřipojí do Windows. Jakmile se uživatel přihlásí, Windows Vypíše zařízení PCI připojená k portům plug-in hostitele PCI. Pokaždé, když uživatel zamkne počítač, je přímý přístup do zásuvky na konektorech PCI bez podřízených zařízení blokovaný, dokud se uživatel znovu nepřipojí. Zařízení, která už jsou ve výčtu, když se počítač odemkne, bude dál fungovat, dokud nebude odpojený. 

  Nastavení této zásady se vynutilo jenom v případě, že je povolené BitLocker nebo šifrování zařízení.  

  **Výchozí**: Ano


- **Instalace hardwarových zařízení pomocí tříd instalace**  
  [DeviceInstallation/AllowInstallationOfMatchingDeviceSetupClasses](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdevicesetupclasses) – pomocí této zásady můžete zadat seznam globálně jedinečných identifikátorů (GUID) třídy nastavení zařízení pro ovladače zařízení, které systém Windows znemožňuje nainstalovat. Nastavení této zásady má přednost před jinými nastaveními zásad, která umožňují systému Windows nainstalovat zařízení. Pokud toto nastavení zásad povolíte (nastavíte k *blokování instalace hardwarového zařízení*), systém Windows znemožní instalaci nebo aktualizaci ovladačů zařízení, jejichž identifikátory GUID třídy nastavení zařízení se zobrazí v seznamu, který vytvoříte. Pokud nastavení této zásady povolíte na vzdáleném počítači, nastavení zásad bude mít vliv na přesměrování zadaných zařízení z klienta vzdálené plochy na server vzdálené plochy. Pokud nastavení této zásady zakážete nebo nenakonfigurujete (nastavíte možnost *Povolit instalaci hardwarového zařízení*), může systém Windows instalovat a aktualizovat zařízení podle povolených nebo zabránících jiným nastavením zásad.  

  **Výchozí**: Blokovat instalaci hardwarového zařízení

  Když je vybraná možnost *blokovat instalaci hardwarového zařízení* , jsou k dispozici následující nastavení.  

  - **Odebrat shodná hardwarová zařízení**  
    Toto nastavení je dostupné, jenom když je *Instalace hardwarového zařízení podle instalačních tříd* nastavená tak, aby *blokovala instalaci hardwarového zařízení*.  
 
    **Výchozí**: *Žádná výchozí konfigurace*  

  - **Blokované identifikátory hardwarových zařízení**  
    Toto nastavení je dostupné, jenom když je instalace hardwarového zařízení podle instalačních tříd nastavená tak, aby blokovala instalaci hardwarového zařízení. Pokud chcete nakonfigurovat toto nastavení, rozbalte možnost, vyberte **+ Přidat**a pak zadejte identifikátor hardwarového zařízení, který chcete blokovat.  
 
    **Výchozí**: *Žádná zařízení nejsou blokovaná.*

## <a name="endpoint-detection-and-response"></a>Zjištění a odpověď koncového bodu  
Další informace najdete v tématu [WINDOWSADVANCEDTHREATPROTECTION CSP](https://docs.microsoft.com/windows/client-management/mdm/windowsadvancedthreatprotection-csp) v dokumentaci k systému Windows.  

- **Urychlení** - Konfigurace četnosti generování sestav telemetrie */TelemetryReportingFrequency*  

  Urychlení generování sestav telemetrie rozšířené ochrany před internetovými útoky v programu Microsoft Defender  

  **Výchozí**: Ano

- **Sdílení ukázky pro všechny soubory** - *Konfigurace/SampleSharing*  

  Vrátí nebo nastaví parametr konfigurace sdílení ukázky rozšířené ochrany před internetovými útoky v programu Microsoft Defender.  

  **Výchozí**: Ano

## <a name="exploit-protection"></a>Ochrana před zneužitím  

- **XML ochrany před zneužitím**  
  Další informace najdete v tématu [Import, export a nasazení konfigurací ochrany před](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/import-export-exploit-protection-emet-xml) zneužitím v dokumentaci k Windows.  

  Umožňuje správci IT nabízet konfiguraci, která představuje požadované možnosti zmírnění systému a aplikace pro všechna zařízení v organizaci. Konfigurace je reprezentovaná kódem XML. 

  Použití ochrany před zneužitím pomáhá chránit zařízení před malwarem, který využívá zneužití k rozšíření a nakazit. Pomocí aplikace zabezpečení systému Windows nebo PowerShellu vytvoříte sadu zmírnění hrozeb (označované jako konfigurace). Tuto konfiguraci pak můžete exportovat jako soubor XML a sdílet ho s více počítači ve vaší síti, aby všichni měli stejnou sadu nastavení pro zmírnění rizik.
 
  Existující konfigurační soubor XML nástroje EMET můžete také převést a importovat do konfiguračního souboru XML ochrany před zneužitím.

- **Přepsat ochranu před zneužitím blokování**  
  [WindowsDefenderSecurityCenter/DisallowExploitProtectionOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsdefendersecuritycenter#windowsdefendersecuritycenter-disallowexploitprotectionoverride) – nastavte na *hodnotu Ano* , pokud chcete uživatelům zabránit v provádění změn v oblasti nastavení ochrany před zneužitím v Security Center programu Windows Defender. Pokud toto nastavení zakážete nebo nenakonfigurujete, místní uživatelé mohou provádět změny v oblasti nastavení ochrany před zneužitím.  
  **Výchozí**: Ano  

- **Řízený přístup ke složkám**  
  Viz [Defender/ControlledFolderAccessAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessallowedapplications) a [Defender/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) 
  
   Umožňuje chránit soubory a složky před neautorizovanými změnami od neznámých aplikací.

  **Výchozí**: Režim auditování

## <a name="web--network-protection"></a>Ochrana webového & sítě  

- **Typ ochrany sítě**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) – tato zásada vám umožní zapnout nebo vypnout ochranu sítě pomocí ochrany před zneužitím v programu Windows Defender. Ochrana sítě je funkcí ochrany před zneužitím v programu Windows Defender, která chrání zaměstnance pomocí libovolné aplikace v přístupu k podvodným podvodům, webům pro zneužití a škodlivému obsahu na internetu. To zahrnuje prevenci prohlížeče třetích stran v připojení k nebezpečným webům.  

  Když nastavíte režim *Povolit* nebo *audit*, uživatelé nemůžou vypnout ochranu sítě a k zobrazení informací o pokusůch o připojení můžete použít Security Center programu Windows Defender.  
 
  - Při *Povolení* bude zablokováno uživatelům a aplikacím v připojení k nebezpečným doménám.  
  - *Režim auditování* neblokuje uživatelům a aplikacím připojení k nebezpečným doménám.  

  Když nastavíte *uživatelsky definovaného uživatele*, uživatelé a aplikace se nebudou moct připojit k nebezpečným doménám a informace o připojeních nejsou k dispozici v Security Center Windows Defenderu.  

  **Výchozí**: Režim auditování

- **Vyžadovat filtr SmartScreen pro Microsoft Edge**  
  [Browser/AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) – Microsoft Edge používá filtr SmartScreen v programu Windows Defender (zapnutý) k ochraně uživatelů před potenciálními podvodnými zprávami a škodlivým softwarem ve výchozím nastavení. Ve výchozím nastavení je tato zásada povolená (nastavená na *Ano*) a pokud je tato možnost povolená, zakáže uživatelům vypnutí filtru SmartScreen v programu Windows Defender.  Pokud jsou platné zásady pro zařízení rovny nenakonfigurovaným, můžou uživatelé vypnout filtr SmartScreen v programu Windows Defender, který zůstane bez ochrany zařízení.  

  **Výchozí**: Ano
  
- **Blokovat přístup ke škodlivému webu**  
  [Prohlížeč/PreventSmartScreenPromptOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride) – ve výchozím nastavení umožňuje Microsoft Edge uživatelům obejít upozornění programu Windows Defender SmartScreen na potenciálně škodlivé weby a umožnit tak uživatelům pokračovat v lokalitě. Když je tato zásada povolená (nastavená na *Ano*), Microsoft Edge znemožní uživatelům obejít upozornění a zablokuje jejich pokračování na webu.  

  **Výchozí**: Ano

- **Blokovat stahování neověřených souborů**  
  [Prohlížeč/PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles) – ve výchozím nastavení umožňuje Microsoft Edge uživatelům obejít upozornění na potenciálně škodlivé soubory v programu Windows Defender SmartScreen, což jim umožní pokračovat ve stahování neověřených souborů. Když je tato zásada povolená (nastavená na *Ano*), uživatelům se zabrání v obcházení upozornění a nemůžou stahovat neověřené soubory.  

  **Výchozí**: Ano

## <a name="windows-defender-anti-virus----settings-review-pending-for-this-section"></a>Antivirová ochrana v programu Windows Defender – antivirová [Kontrola nastavení čeká na tuto část]

Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) .

- **Kontrolovat skripty načtené do webových prohlížečů Microsoftu**  
  [Defender/AllowScriptScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning) – nastavte na *Ano* , pokud chcete funkci prohledávání skriptů v programu Windows Defender zakázat.  

  **Výchozí**: Ano

- **Kontrolovat příchozí e-mailové zprávy**  
  [Defender/AllowEmailScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) – nastavte na *Ano* , pokud chcete, aby Windows Defender mohl kontrolovat e-mail.  

  **Výchozí**: Ano

- **Typ souhlasu pro odeslání ukázky v programu Defender**  
  [Defender/SubmitSamplesConsent](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) -kontroluje úroveň souhlasu uživatele v programu Windows Defender, aby odesílala data. Pokud je požadovaný souhlas již udělen, program Windows Defender je odešle. Pokud ne (a pokud si uživatel není nikdy požádán), uživatelské rozhraní se spustí, aby požádalo o souhlas uživatele (při nastavení *ochrany* před odesláním cloudu na *Ano*).  

  **Výchozí**: Posílat bezpečné vzorky automaticky

- **Systém kontroly sítě (NIS)**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) – blokování škodlivého provozu zjištěného signaturami ve službě systém kontroly sítě (NIS).  
 
  **Výchozí**: Ano

- **Interval aktualizace podpisu (v hodinách)**  
  [Defender/SignatureUpdateInterval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) – zadejte v hodinách, jak často bude zařízení kontrolovat nové aktualizace signatury Defenderu.  
 
  **Výchozí**: 4

- **Konfigurace nízké priority procesoru pro naplánovaná prohledávání**  
  [Defender/EnableLowCPUPriority](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority) – Pokud je nastavená hodnota *Ano*, priorita procesoru pro kontroly je nastavena na hodnotu Nízká. Pokud *není nakonfigurováno*, nebudou provedeny žádné změny priority procesoru pro naplánovaná prohledávání.  

    **Výchozí**: Ano

- **Blok aplikace Defender při ochraně přístupu**  
  [Defender/AllowOnAccessProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowonaccessprotection) – Pokud je nastavená hodnota *Ano*, je povolená možnost Windows Defender na ochraně přístupu.  

  **Výchozí**: Ano

- **Typ Systémové kontroly, který se má provést**  
  Typ vyhledávání [Defender/ScanParameter](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter) -Defender  

  **Výchozí**: Rychlá kontrola

- **Kontrolovat všechny stahované soubory**  
  [Defender/AllowIOAVProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection) – Pokud je tato hodnota nastavená na *Ano*, Defender zkontroluje všechny stažené soubory a přílohy.  

  **Výchozí**: Ano

- **Dny před odstraněním malwaru v karanténě**  
  [Defender/DaysToRetainCleanedMalware](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) – určuje počet dní, po které se mají zachovat položky v karanténě v systému, než se automaticky odstraní. Pokud nastavíte hodnotu nula, položky v karanténě se nikdy automaticky neodstraní.  

  **Výchozí**: 0

- **Čas zahájení naplánované kontroly**  
  [Defender/ScheduleScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime) – Naplánujte denní dobu, po kterou Defender bude kontrolovat zařízení. 
  
  Související možnost v tomto seznamu: *Defender/ScheduleScanDay*   

  **Výchozí**: 2 DOP.

- **Ochrana Doručená v cloudu**  
  [Defender/AllowCloudProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) – Pokud je tato hodnota nastavená na *Ano*, Windows Defender pošle společnosti Microsoft informace o všech nalezených problémech. Microsoft bude tyto informace analyzovat, získat další informace o problémech, které mají vliv na vás a jiné zákazníky, a nabízí Vylepšená řešení.

  Pokud je tato zásada nastavená na *hodnotu Ano*, můžete k tomu, aby uživatelé mohli řídit odesílání informací ze svého zařízení, použít *typ souhlasu ukázka odeslání ukázky* v programu Defender.  

  **Výchozí**: Ano

- **Akce potenciálně nežádoucí aplikace v Defenderu**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection) – antivirová ochrana v programu Windows Defender může identifikovat a blokovat *potenciálně nežádoucí aplikace* (PUAs) ze stahování a instalace na koncových bodech ve vaší síti. 
 
  - Když se nastaví *blokování*, program Windows Defender blokuje PUAs a zobrazí je v historii spolu s dalšími hrozbami.
  - Při nastavení *auditování*program Windows Defender detekuje PUAs, ale neblokuje je. Informace o aplikacích, které v programu Windows Defender převzaly akce, se dají najít hledáním událostí, které vytvořil program Windows Defender v Prohlížeč událostí.  
  - Když se nastaví na *výchozí nastavení zařízení*, ochrana PUA je vypnutá.  
 
  **Výchozí**: Zablokovat

- **Rozšířený časový limit pro Cloud Defenderu**  
  [Defender/CloudExtendedTimeout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout) – určete maximální dobu, po kterou by antivirová ochrana v programu Windows Defender měla blokovat soubor při čekání na výsledek z cloudu. Základní doba čekání programu Windows Defender je 10 sekund. Do těchto 10 sekund se přidá každý další čas, který zde zadáte (až 50 sekund). Ve většině případů hledání trvá méně času než maximum. Prodloužení doby umožňuje, aby cloud podezřelé soubory důkladně prozkoumal.  

  Ve výchozím nastavení je rozšířená hodnota času 0 (zakázáno). Intune doporučuje povolit toto nastavení a zadat aspoň 20 dalších sekund.  
 
  **Výchozí**: 0

- **Prohledat archivní soubory**  
  [Defender/AllowArchiveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning) – nastavte na *Ano* , pokud chcete, aby program Windows Defender kontroloval archivní soubory.  

  **Výchozí**: Ano

- **Plán kontroly systémových úloh Defenderu**  
  [Defender/ScheduleScanDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday) – naplánování, který den v Defenderu prohledává zařízení. 
 
  Související možnost v tomto seznamu: *Defender/ScheduleScanTime*

  **Výchozí**: Definováno uživatelem

- **Monitorování chování**  
  [Defender/AllowBehaviorMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring) – nastavte na *Ano* , pokud chcete zapnout funkci monitorování chování v programu Windows Defender. Ve Windows 10 se v programu Windows Defender monitorují senzory, které sledují a zpracovávají signály z operačního systému a odesílají tato data ze senzorů do vaší privátní a izolované cloudové instance ATP v programu Microsoft Defender.  

  **Výchozí**: Ano

- **Kontrolovat soubory otevřené ze síťových složek**  
  [Defender/AllowScanningNetworkFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) – nastavte na *Ano* , pokud chcete, aby program Windows Defender kontroloval soubory v síti. Uživatel nebude moct odebrat zjištěný malware ze souborů jen pro čtení.  

  **Výchozí**: Ano

- **Úroveň blokování cloudu Defenderu**  
  [Defender/CloudBlockLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel) – pomocí této zásady můžete určit, jak agresivní antivirová ochrana v programu Windows Defender blokuje a kontroluje podezřelé soubory. Vaše možnosti jsou:

  - Vysoce agresivní blokování neznámých souborů při optimalizaci výkonu klienta (větší šance na falešně pozitivní)
  - Vysoká plus – agresivní blokování neznámých souborů a uplatnění dalších ochranných opatření (může ovlivnit výkon klienta)
  - Nulová tolerance – blokování všech neznámých spustitelných souborů

  **Výchozí**: Nenakonfigurováno

- **Sledování v reálném čase**  
  [Defender/AllowRealtimeMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring) – nastavte na *Ano* , pokud chcete, aby monitorování v reálném čase programu Windows Defender bylo povolené.  

  **Výchozí**: Ano

- **Limit využití procesoru při kontrole**  
  [Defender/AvgCPULoadFactor](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor) – zadejte maximální průměrné využití procesoru%, které může program Windows Defender během kontroly použít.  

  **Výchozí**: 50

- **Při úplné kontrole kontrolovat namapované síťové jednotky**  
  [Defender/AllowFullScanOnMappedNetworkDrives](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanonmappednetworkdrives) – nastavte na *Ano* , pokud chcete, aby program Windows Defender kontroloval soubory v síti. Uživatel nemůže odebrat zjištěný malware ze souborů, které jsou jen pro čtení,

  Související nastavení v tomto seznamu: *Defender/AllowScanningNetworkFiles*

  **Výchozí**: Ano

- **Zablokovat přístup koncovým uživatelům k programu Defender**  
  [Defender/AllowUserUIAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowuseruiaccess) – nastavte na *Ano* , pokud chcete zablokovat přístup koncových uživatelů k uživatelskému rozhraní programu Windows Defender na svém zařízení.  

  **Výchozí**: Ano

- **Čas zahájení rychlé kontroly**  
  [Defender/ScheduleQuickScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) – naplánování denního času pro spuštění rychlé kontroly v programu Defender  

  **Výchozí**: 2 DOP.

## <a name="windows-defender-firewall"></a>Firewall v programu Windows Defender
Další informace najdete v dokumentaci k Windows v tématu [zprostředkovatel CSP brány firewall](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) .

- **Doba nečinnosti přidružení zabezpečení před odstraněním** - *MdmStore/globální/SaIdleTime*   
  Přidružení zabezpečení se odstraní, jakmile se síťový provoz nezobrazuje po tento počet sekund.  
  **Výchozí**: 300

- ProtokolFTP(FileTransferProtocol) - *MdmStore/globální/DisableStatefulFtp*   
  Blokuje stavovou protokol FTP (File Transfer Protocol) (FTP).  
  **Výchozí**: Ano

- **Řízení front** - paketů*MdmStore/globální/EnablePacketQueue*    
  Určete, jak se má pro daný software na straně příjmu Povolit šifrované přijímání a prostý text před scénářem brány IPsec pro tunelové připojení. Tím se zajistí zachování pořadí paketů.  
  **Výchozí**: Výchozí nastavení zařízení

- **Profil brány firewall***FirewallRules/FirewallRuleName/profily*  -   
  Určuje profily, do kterých pravidlo patří: Doména, soukromý, veřejný. Tato hodnota představuje profil pro sítě, které jsou připojené k doménám.  

  Dostupná nastavení:  
  - **Vyžadují se jednosměrové odpovědi na všesměrová vysílání vícesměrového vysílání.**  
    **Výchozí**: Ano

  - **Pravidla autorizovaných aplikací ze sloučených zásad skupiny**  
    **Výchozí**: Ano

  - **Blokovaná příchozí oznámení**  
    **Výchozí**: Ano

  - **Globální pravidla portů ze sloučených zásad skupiny**  
    **Výchozí**: Ano

  - **Zakázaný neviditelný režim**  
    **Výchozí**: Ano

  - **Povolená brána firewall**  
    **Výchozí**: Povoleno

  - **Pravidla zabezpečení připojení ze zásad skupiny nejsou sloučena.**  
    **Výchozí**: Ano

  - **Pravidla zásad ze zásad skupiny nejsou sloučena.**  
    **Výchozí**: Ano

- **Profil brány firewall Public** - *FirewallRules/FirewallRuleName/Profiles*  
  Určuje profily, do kterých pravidlo patří: Doména, soukromý, veřejný. Tato hodnota představuje profil pro veřejné sítě. Tyto sítě jsou klasifikovány jako veřejné správci v hostiteli serveru. Klasifikace proběhne při prvním připojení hostitele k síti. Tyto sítě jsou obvykle na letištích, v kavárnách a na jiných veřejných místech, kde nejsou důvěryhodní partneři v síti nebo správci sítě.  

  Dostupná nastavení:

  - **Blokovaná příchozí připojení**  
    **Výchozí**: Ano 

  - **Vyžadují se jednosměrové odpovědi na všesměrová vysílání vícesměrového vysílání.**  
    **Výchozí**: Ano  

  - **Je vyžadován neviditelný režim.**  
    **Výchozí**: Ano 
 
  - **Vyžadují se odchozí připojení.**  
    **Výchozí**: Ano  

  - **Pravidla autorizovaných aplikací ze sloučených zásad skupiny**  
    **Výchozí**: Ano  

  - **Blokovaná příchozí oznámení**  
    **Výchozí**: Ano  

  - **Globální pravidla portů ze sloučených zásad skupiny**  
    **Výchozí**: Ano

  - **Zakázaný neviditelný režim**  
    **Výchozí**: Ano

  - **Povolená brána firewall**  
    **Výchozí**: Povoleno  

  - **Pravidla zabezpečení připojení ze zásad skupiny nejsou sloučena.**  
    **Výchozí**: Ano  

  - **Vyžaduje se příchozí provoz**  
    **Výchozí**: Ano

  - **Pravidla zásad ze zásad skupiny nejsou sloučena.**  
    **Výchozí**: Ano  

- **Profil brány firewall privátní** - *FirewallRules/FirewallRuleName/profily*  
  Určuje profily, do kterých pravidlo patří: Doména, soukromý, veřejný. Tato hodnota představuje profil privátních sítí.  

  Dostupná nastavení: 

  - **Blokovaná příchozí připojení**  
    **Výchozí**: Ano

  - **Vyžadují se jednosměrové odpovědi na všesměrová vysílání vícesměrového vysílání.**  
    **Výchozí**: Ano

  - **Je vyžadován neviditelný režim.**  
    **Výchozí**: Ano

  - **Vyžadují se odchozí připojení.**  
    **Výchozí**: Ano

  - **Blokovaná příchozí oznámení**  
    **Výchozí**: Ano

  - **Globální pravidla portů ze sloučených zásad skupiny**  
    **Výchozí**: Ano

  - **Zakázaný neviditelný režim**  
    **Výchozí**: Ano  

  - **Povolená brána firewall**  
    **Výchozí**: Povoleno

  - **Pravidla autorizovaných aplikací ze zásad skupiny nejsou sloučena.**  
    **Výchozí**: Ano

  - **Pravidla zabezpečení připojení ze zásad skupiny nejsou sloučena.**  
    **Výchozí**: Ano

  - **Vyžaduje se příchozí provoz**  
    **Výchozí**: Ano

  - **Pravidla zásad ze zásad skupiny nejsou sloučena.**  
    **Výchozí**: Ano  

- **Metoda kódování předsdíleného klíče brány firewall**  
  **Výchozí**: UTF8

- **Ověření seznamu odvolaných certifikátů**  
  **Výchozí**: Výchozí nastavení zařízení

## <a name="windows-hello-for-business"></a>Windows Hello pro firmy  

Další informace najdete v tématu [PASSPORTFORWORK CSP](https://docs.microsoft.com/windows/client-management/mdm/passportforwork-csp) v dokumentaci k systému Windows.

- **Konfigurace Windows Hello pro firmy** - *TenantId/policies/UsePassportForWork*    
  Windows Hello pro firmy je alternativní metoda pro přihlašování do systému Windows tím, že nahrazujete hesla, čipové karty a virtuální čipové karty.  

  - Když nastavíte *Ano*, povolíte tuto zásadu a zřídí zařízení Windows Hello pro firmy.  
  - Pokud je nastavené na Nenakonfigurováno, standardní hodnoty nebudou mít vliv na nastavení zásad daného zařízení. To znamená, že pokud je Windows Hello pro firmy v zařízení zakázané, zůstane zakázané. Pokud je povolená, zůstane povolený. 

  Nemůžete zakázat Windows Hello pro firmy prostřednictvím tohoto směrného plánu. Windows Hello pro firmy můžete zakázat při konfiguraci [registrace systému Windows](windows-hello.md)nebo jako součást profilu konfigurace zařízení pro [ochranu identity](identity-protection-configure.md).  

Windows Hello pro firmy je alternativní metoda pro přihlašování do systému Windows tím, že nahrazujete hesla, čipové karty a virtuální čipové karty.  

  Pokud nastavení této zásady povolíte nebo nenakonfigurujete, zařízení zřídí Windows Hello pro firmy. Pokud nastavení této zásady zakážete, zařízení nezřídí Windows Hello pro firmy pro žádného uživatele.

  Intune nepodporuje zakázání Windows Hello. Místo toho můžete nakonfigurovat zásady, které povolí Windows Hello pro firmy (Ano), nebo nemusíte konfigurovat Windows Hello přímo (není nakonfigurované). Pokud není nakonfigurováno, může zařízení přijmout konfiguraci prostřednictvím jiných zásad, které tuto funkci můžou povolit nebo zakázat.  

  **Výchozí**: Ano  

- **Vyžadovat malá písmena v PIN** - *TenantId/policies/PINComplexity/LowercaseLetters*  
  **Výchozí**: Povoleno  

- **Vyžadovat speciální znaky v PIN** - *TenantId/policies/PINComplexity/SpecialCharacters*  
  **Výchozí**: Povoleno  

- **Vyžadovat v PIN kódu** - *TenantId/policies/PINComplexity/UppercaseLetters* velká písmena   
  **Výchozí**: Povoleno  

