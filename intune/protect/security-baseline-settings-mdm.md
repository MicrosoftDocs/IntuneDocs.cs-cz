---
title: Nastavení standardních hodnot zabezpečení Intune pro Windows 10
titleSuffix: Microsoft Intune
description: Projděte si výchozí a dostupná nastavení, která najdete v základní úrovni zabezpečení Windows MDM pro zařízení s Windows 10, která spravujete v Intune.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ROBOTS: NOINDEX
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0d673650a26f3917fa32babba42e5e2054c87e59
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/05/2019
ms.locfileid: "74060026"
---
# <a name="mdm-security-baseline-settings-for-intune"></a>Nastavení standardních hodnot zabezpečení MDM pro Intune  

Zobrazení nastavení základní hodnoty zabezpečení MDM, která jsou Microsoft Intune podporovaná v zařízeních se systémem Windows 10 nebo novějším. Výchozí hodnoty pro nastavení v tomto směrném plánu reprezentují doporučenou konfiguraci pro příslušná zařízení a nemusí odpovídat výchozím hodnotám z jiných standardních hodnot zabezpečení.  

Nejnovější základní verze je základní hodnota **zabezpečení MDM pro květen 2019**  

Informace o tom, co se změnilo v nejnovější verzi tohoto směrného plánu z předchozí verze, najdete v tématu [co se změnilo v nové šabloně](#whats-changed-in-the-new-template).  

> [!NOTE]  
> V červnu 2019 se základní verze Preview ochrany MDM nahradila vydáním *směrného plánu zabezpečení MDM pro šablonu květen 2019* , která je obecně dostupná (není ve verzi Preview). Profily, které byly vytvořeny před dostupností *směrného plánu zabezpečení MDM pro květen 2019* , se nebudou aktualizovat tak, aby odrážely nastavení a hodnoty, které jsou v směrném plánu zabezpečení MDM pro verzi květen 2019.  I když nemůžete vytvořit nové profily založené na šabloně Preview, můžete upravit a pokračovat v používání profilů, které jste vytvořili dříve, a to na základě šablony ve verzi Preview.   
  
Další informace o používání standardních hodnot zabezpečení s Intune najdete v tématu [použití standardních hodnot zabezpečení](security-baselines.md).  


   
## <a name="above-lock"></a>Nad zámkem  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) .  

- **Blokovat zobrazování oznámení informačních zpráv**  
  Toto nastavení zásad umožňuje zabránit zobrazování oznámení aplikace na zamykací obrazovce. Pokud toto nastavení zásad povolíte, na zamykací obrazovce se nezobrazí žádná oznámení aplikací. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, uživatelé budou moci zvolit, které aplikace budou zobrazovat oznámení na zamykací obrazovce.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067101)  

  **Výchozí**: Ano  

- **Hlasové aktivace aplikací z uzamčené obrazovky**  

  **Výchozí**: zakázáno

## <a name="app-runtime"></a>Modul runtime aplikace    
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) .  

- **Volitelné účty Microsoft pro aplikace pro Windows Store**  
  Nastavení této zásady umožňuje řídit, jestli jsou účty Microsoft volitelné pro aplikace pro Windows Store, které vyžadují účet pro přihlášení. Tato zásada ovlivňuje pouze aplikace pro Windows Store, které ji podporují. Pokud toto nastavení zásad povolíte, aplikace pro Windows Store, které obvykle vyžadují účet Microsoft pro přihlášení, umožní uživatelům přihlásit se místo toho podnikovým účtem. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, uživatelé se musí přihlašovat pomocí účet Microsoft.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067104)  
  
  **Výchozí**: povoleno  

## <a name="application-management"></a>Správa aplikací   
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) .  

- **Blokovat uživatelský ovládací prvek pro instalace**  
  Nastavení této zásady umožňuje uživatelům změnit možnosti instalace, které jsou obvykle k dispozici pouze správcům systému. Pokud toto nastavení zásad povolíte, přeskočí se některé funkce zabezpečení Instalační služba systému Windows. Umožňuje dokončení instalací, které by jinak bylo zastaveno z důvodu porušení zabezpečení. Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, funkce zabezpečení Instalační služba systému Windows zabrání uživatelům měnit možnosti instalace obvykle rezervované pro správce systému, jako je například určení adresáře, do kterého jsou soubory nainstalovány. Pokud Instalační služba systému Windows zjistí, že instalační balíček povolil uživateli změnu chráněné možnosti, zastaví instalaci a zobrazí zprávu. Tyto funkce zabezpečení fungují pouze v případě, že instalační program běží v privilegovaném kontextu zabezpečení, ve kterém má přístup k adresářům odepřeným uživateli. Nastavení této zásady je určené pro méně omezující prostředí. Dá se použít k obcházení chyb v instalačním programu, který brání instalaci softwaru.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067060)  

  **Výchozí**: Ano

- **Blokovat instalaci MSI aplikace se zvýšenými oprávněními**  
  Nastavení této zásady směruje Instalační služba systému Windows, aby při instalaci jakéhokoli programu do systému používala zvýšená oprávnění.  
  - *Pokud nastavení této zásady povolíte*, budou se oprávnění rozšířit na všechny programy. Tato oprávnění jsou obvykle vyhrazena pro programy, které byly přiřazeny uživateli (které jsou nabízeny na ploše), přiřazené k počítači (automaticky nainstalovány) f nebo zpřístupněny v ovládacím panelu Přidat nebo odebrat programy. Toto nastavení profilu umožňuje uživatelům instalovat programy, které vyžadují přístup k adresářům, které uživatel nemusí mít oprávnění k zobrazení nebo změně, včetně adresářů na vysoce omezených počítačích.
  - *Pokud toto nastavení zásad zakážete nebo*nenakonfigurujete, použije systém při instalaci programů, které správce systému nedistribuuje nebo nenabízí, oprávnění aktuálního uživatele. Poznámka: nastavení této zásady se zobrazuje jak v konfiguraci počítače, tak ve složkách Konfigurace uživatele. Aby bylo nastavení této zásady účinné, musíte je povolit v obou složkách. Upozornění: zkušení uživatelé můžou využít výhod oprávnění, která tato zásada umožňuje změnit jejich oprávnění a získat trvalý přístup k souborům a složkám s omezeným přístupem. Upozorňujeme, že není zaručené zabezpečení verze konfigurace uživatele u tohoto nastavení zásad.  
  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067134)    

  **Výchozí**: Ano

- **Blokovat hru DVR (jenom Desktop)**  
  Konfiguruje, zda je povoleno nahrávání a vysílání her.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067056)  
  
  **Výchozí**: Ano  

## <a name="auto-play"></a>Automatické přehrávání   
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – automatické přehrávání](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) .  

- **Automatické přehrání výchozího chování při automatickém spuštění**  
  Toto nastavení má vliv na výchozí chování pro příkazy automatického spouštění. Příkazy automatického spuštění jsou uložené v souborech Autorun. inf a můžou spouštět instalační programy nebo jiné rutiny. Pokud je tato možnost *povolená*, můžou správci změnit výchozí chování při automatickém spouštění na zařízení, na kterém běží Windows Vista nebo novější. Chování může být nastaveno na: a) zcela zakázat příkazy Autorun nebo b) vrátit se zpátky k chování Pre-Windows Vista s automatickým spuštěním příkazu Autorun. Pokud je nastavené na *zakázáno* nebo *není nakonfigurováno*, zařízení se systémem Windows Vista nebo novějším vyzvat uživatele k zadání, zda má být spuštěn příkaz Autorun.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067133)       
  
  **Výchozí**: nespouštět  
  
- **Režim automatického přehrávání**  
  Toto nastavení zásad umožňuje vypnout funkci automatického přehrávání. Automatické přehrávání začne číst z jednotky hned po vložení média do jednotky. V důsledku toho se hned spustí instalační soubor programů a hudba na zvukovém médiu. Před verzí Windows XP SP2 je automatické přehrávání ve výchozím nastavení zakázáno na vyměnitelných jednotkách, jako je disketová jednotka (ale ne jednotka CD-ROM) a na síťových jednotkách. Od verze Windows XP SP2 je automatické přehrávání povolené pro vyměnitelné jednotky, včetně jednotek zip a některých velkokapacitních paměťových zařízení USB. Pokud nastavení této zásady povolíte, bude automatické přehrávání na discích CD-ROM a na vyměnitelných jednotkách nebo na všech jednotkách zakázané. Nastavením této zásady zakážete automatické přehrávání na dalších typech jednotek. Toto nastavení nemůžete použít, pokud chcete povolit automatické přehrávání na jednotkách, na kterých je ve výchozím nastavení zakázané. Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, bude povoleno automatické přehrávání. Poznámka: nastavení této zásady se zobrazuje jak v konfiguraci počítače, tak ve složkách Konfigurace uživatele. Pokud dojde ke konfliktu nastavení zásad, nastavení zásad v konfiguraci počítače má přednost před nastavením zásad v konfiguraci uživatele.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2066793)  
  
  **Výchozí**: zakázáno

- **Blokovat automatické přehrávání u zařízení bez svazků**  
  Toto nastavení zásad nepovoluje automatické přehrávání pro zařízení MTP, jako jsou kamery nebo telefony. Pokud nastavení této zásady povolíte, funkce automatického přehrávání není povolená pro zařízení MTP, jako jsou kamery nebo telefony. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, bude pro zařízení bez svazků povolené automatické přehrávání.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067106)    
  
  **Výchozí**: povoleno  

## <a name="bitlocker"></a>Zapnut    
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – BitLocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) .  

- **Zásada pro vyměnitelné jednotky služby bit Lock**  
  Toto nastavení zásad slouží k řízení metody šifrování a složitosti šifry. Hodnoty této zásady určují sílu šifry, kterou BitLocker používá k šifrování. Podniky můžou chtít řídit úroveň šifrování pro zvýšené zabezpečení (AES-256 je silnější než AES-128). Pokud povolíte toto nastavení, budete moct nakonfigurovat šifrovací algoritmus a složitou složitost klíče pro pevné datové jednotky, jednotky operačního systému a vyměnitelné datové jednotky jednotlivě. U pevných jednotek operačního systému doporučujeme použít algoritmus XTS-AES. U vyměnitelných jednotek byste měli použít algoritmus AES-CBC 128-bit nebo AES-CBC 256-bit, pokud se jednotka používá v jiných zařízeních, na kterých běží Windows 10, verze 1511 nebo novější. Změna metody šifrování nemá žádný vliv, pokud je jednotka již zašifrovaná nebo pokud probíhá šifrování. V těchto případech se nastavení této zásady ignoruje.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067140) 

  V případě zásad vyměnitelného disku pro službu bit Lock nakonfigurujte následující nastavení:

  - **Vyžadovat šifrování pro přístup pro zápis**  
    **Výchozí**: Ano  
  

## <a name="browser"></a>Prohlížeč  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – prohlížeč](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) .  

- **Vyžadovat filtr SmartScreen pro Microsoft Edge**  
  Microsoft Edge používá filtr SmartScreen v programu Microsoft Defender (zapnutý) k ochraně uživatelů před potenciálními podvodnými zprávami a škodlivým softwarem ve výchozím nastavení. Ve výchozím nastavení uživatelé také nemůžou zakázat (vypnout) filtr SmartScreen v programu Microsoft Defender. Povolením této zásady dojde k vypnutí filtru SmartScreen v programu Microsoft Defender a zabránění uživatelům v jeho zapnutí. Nekonfigurujte tuto zásadu, aby uživatelům umožnila zvolit nebo vypnout filtr SmartScreen v programu Microsoft Defender.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067029)   
  
  **Výchozí**: Ano  
  
- **Blokovat přístup ke škodlivému webu**  
  Ve výchozím nastavení umožňuje Microsoft Edge uživatelům obejít (Ignorovat) upozornění filtru SmartScreen v programu Microsoft Defender týkající se potenciálně škodlivých webů, což jim umožní pokračovat v lokalitě. Pomocí této zásady můžete ale nakonfigurovat Microsoft Edge, aby uživatelé nemohli obejít upozornění, a zablokovat tak, aby pokračovali na tomto webu.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067040)   
  
  **Výchozí**: Ano  
  
- **Blokovat stahování neověřených souborů**  
  Ve výchozím nastavení umožňuje Microsoft Edge uživatelům obejít (Ignorovat) upozornění filtru SmartScreen v programu Microsoft Defender týkající se potenciálně škodlivých souborů, což jim umožní pokračovat v stahování neověřených souborů. Když se tyto zásady povolí, zabráníte tak uživatelům v obcházení upozornění a znemožníte jim stahování neověřených souborů.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067023)  
  
  **Výchozí**: Ano  
  
- **Blokovat Správce hesel**  
  Ve výchozím nastavení používá Microsoft Edge správce hesel automaticky a umožňuje uživatelům vytvářet hesla na základě místních správců. Zakázáním této zásady omezíte používání Správce hesel na Microsoft Edge. Tuto zásadu nekonfigurujte, pokud chcete uživatelům umožnit, aby ukládali a spravovali hesla místně pomocí Správce hesel.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067128)  
  
  **Výchozí**: Ano  
  
- **Zabránit přepsání chyb certifikátu**  
  Nastavení této zásady brání uživateli ignorovat SSL (Secure Sockets Layer)/TLS (Transport Layer Security), které přeruší procházení (například vypršela platnost, odvolaná zpráva nebo "Neshoda názvů") v aplikaci Internet Explorer. Pokud nastavení této zásady povolíte, uživatel nebude moci pokračovat v procházení. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, uživatel se může rozhodnout ignorovat chyby certifikátů a pokračovat v procházení.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067126)  
  
  **Výchozí**: Ano  

## <a name="connectivity"></a>Připojení  
Další informace najdete v dokumentaci k Windows v dokumentaci k [zásadě CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) .  

- **Blokovat stažení z Internetu pro publikování na webu a Průvodce online řazením**  
  Nastavení této zásady určuje, jestli má systém Windows stáhnout seznam poskytovatelů pro Průvodce pro publikování na webu a online řazení. Tito průvodci umožňují uživatelům vybrat ze seznamu společností, které poskytují služby, jako je online úložiště a fotografický tisk. Ve výchozím nastavení Windows zobrazuje kromě poskytovatelů uvedených v registru také poskytovatele stažené z webu Windows. Pokud nastavení této zásady povolíte, Windows nestáhne poskytovatele a jenom poskytovatele služeb, které jsou uložené v místním registru. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, zobrazí se seznam zprostředkovatelů, které se stáhnou, když uživatel použije průvodce publikováním na webu nebo online řazení. Další informace, které obsahují podrobnosti o určení poskytovatelů služeb v registru, najdete v dokumentaci pro Průvodce pro publikování na webu a online objednávky.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067136)  
  
  **Výchozí**: povoleno  

- **Konfigurace zabezpečeného přístupu k cestám UNC**  
  Nastavením této zásady lze nakonfigurovat zabezpečený přístup k cestám UNC. Pokud tuto zásadu povolíte, systém Windows povolí přístup k zadaným cestám UNC jenom po splnění dalších požadavků na zabezpečení.
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067243) 

  **Výchozí**: Nakonfigurujte systém Windows tak, aby povoloval přístup k zadaným cestám UNC jenom po splnění dalších požadavků na zabezpečení.
  
  Když *nastavíte systém Windows tak, aby povoloval přístup k zadaným cestám UNC jenom po výběru splnění dalších požadavků na zabezpečení* , můžete nakonfigurovat seznam cest UNC *Hardended.
  - **Seznam cest pro zpřísněnou cestu UNC**  
    Vyberte **Přidat** a zadejte dalších bezpečnostní příznaky a cesty na serveru.  

- **Blokovat stahování ovladačů tisku přes protokol HTTP**  
  Nastavení této zásady určuje, jestli chcete, aby tento klient mohl stahovat balíčky ovladačů tiskáren přes HTTP. Aby bylo možné nastavit tisk přes protokol HTTP, je nutné stáhnout ovladače, které nejsou doručeny přes protokol HTTP. Poznámka: Toto nastavení zásad nebrání klientovi v tisku na tiskárny v intranetu ani na internetu přes HTTP. Zakazuje jenom stahování ovladačů, které ještě nejsou nainstalované místně. Pokud nastavení této zásady povolíte, nebude možné stáhnout ovladače tisku přes HTTP. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, uživatelé mohou stahovat ovladače tisku přes protokol HTTP.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067141)  
  
  **Výchozí**: povoleno  

## <a name="credentials-delegation"></a>Delegování přihlašovacích údajů  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) .  

- **Vzdálený hostitel delegování neexportovatelných přihlašovacích údajů**  
  Vzdálený hostitel umožňuje delegování neexportovatelných přihlašovacích údajů. Při použití delegování přihlašovacích údajů zařízení poskytují exportovatelné verze přihlašovacích údajů ke vzdálenému hostiteli, který uživatelům zveřejňuje riziko krádeže přihlašovacích údajů od útočníků na vzdáleném hostiteli. Pokud nastavení této zásady povolíte, hostitel podporuje režim omezené správy nebo vzdáleného Credential Guard. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, režim omezené správy a ochrana před vzdáleným přihlašovacími údaji se nepodporuje. Uživatel bude vždycky muset předat přihlašovací údaje k hostiteli.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067103)   
  
  **Výchozí**: povoleno  

## <a name="credentials-ui"></a>Přihlašovací uživatelské rozhraní  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) .  

- Zobrazení **výčtu správců** Nastavení této zásady určuje, jestli se účty správců zobrazí, když se uživatel pokusí zvýšit úroveň spuštěné aplikace. Ve výchozím nastavení se účty správců nezobrazují, když se uživatel pokusí zvýšit úroveň spuštěné aplikace. Pokud nastavení této zásady povolíte, zobrazí se všechny účty místních správců v počítači, aby si uživatel mohl vybrat heslo a zadat správné heslo. Pokud nastavení této zásady zakážete, budou uživatelé vždycky muset zadat uživatelské jméno a heslo, aby se mohli zvýšit.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067021)

  
  **Výchozí**: zakázáno  

## <a name="data-protection"></a>Data Protection  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) .  

- **Zablokovat přímý přístup do paměti**  
  Toto nastavení zásad umožňuje zablokovat přímý přístup do paměti (DMA) pro všechny horké porty PCI pro příjem po dobu, než se uživatel do Windows přihlásí. Jakmile se uživatel přihlásí, Windows Vypíše zařízení PCI připojená k portům plug-in hostitele PCI. Pokaždé, když uživatel zamkne počítač, je přímý přístup do zásuvky na konektorech PCI bez podřízených zařízení blokovaný, dokud se uživatel znovu nepřipojí. Zařízení, která už jsou ve výčtu, když se počítač odemkne, bude dál fungovat, dokud nebude odpojený. Nastavení této zásady se vynutilo jenom v případě, že je povolené BitLocker nebo šifrování zařízení.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067031)     
  
  **Výchozí**: Ano  

## <a name="device-guard"></a>Device Guard  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) .  

- **Credential Guard**  
  Toto nastavení umožňuje uživatelům zapnout ochranu Credential Guard se zabezpečením na základě virtualizace, které pomáhá chránit přihlašovací údaje při příštím restartování počítače.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067044)
   
  **Výchozí**: Povolit s ZÁMKem UEFI 

- **Povolit  zabezpečení na základě virtualizace**  
  Při příštím restartování zapne zabezpečení na základě virtualizace (VBS). Zabezpečení na základě virtualizace nabízí podporu služeb zabezpečení pomocí hypervisoru Windows.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067066)  
  
  **Výchozí**: Ano  


- **Spustit   ochrany systému**  
  **Výchozí**: povoleno  

## <a name="device-installation"></a>Instalace zařízení  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) .  

- **Instalace hardwarových zařízení podle identifikátorů zařízení**  
  Toto nastavení zásad umožňuje zadat seznam technologie Plug and Play ID hardwaru a kompatibilní ID pro zařízení, na která systém Windows znemožňuje instalaci. Nastavení této zásady má přednost před jinými nastaveními zásad, která umožňují systému Windows nainstalovat zařízení. Pokud nastavení této zásady povolíte, systém Windows nebude moci instalovat zařízení, jehož ID hardwaru nebo kompatibilní ID se zobrazí v seznamu, který vytvoříte. Pokud nastavení této zásady povolíte na vzdáleném počítači, nastavení zásad bude mít vliv na přesměrování zadaných zařízení z klienta vzdálené plochy na server vzdálené plochy. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, zařízení se můžou instalovat a aktualizovat tak, aby se povolila nebo zabránila jiným nastavením zásad.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2066794)  
  
  **Výchozí**: blokovat instalaci hardwarového zařízení  

  Když je vybraná možnost *blokovat instalaci hardwarového zařízení* , jsou k dispozici následující nastavení.

  - **Odebrat shodná hardwarová zařízení**   
    Toto nastavení je dostupné, jenom když je *Instalace hardwarového zařízení podle identifikátorů zařízení* nastavená tak, aby *blokovala instalaci hardwarového zařízení*.
    
    **Výchozí**: Ano

  - **Blokované identifikátory hardwarových zařízení**  
    Toto nastavení je dostupné, jenom když je *Instalace hardwarového zařízení podle identifikátorů zařízení* nastavená tak, aby *blokovala instalaci hardwarového zařízení*.
    
    **Výchozí**: Ano  
  
- **Instalace hardwarových zařízení pomocí tříd instalace**  
  Nastavení této zásady umožňuje zadat seznam globálně jedinečných identifikátorů (GUID) třídy nastavení zařízení pro ovladače zařízení, které systém Windows znemožňuje nainstalovat. Nastavení této zásady má přednost před jinými nastaveními zásad, která umožňují systému Windows nainstalovat zařízení. Pokud nastavení této zásady povolíte, systém Windows nebude instalovat ani aktualizovat ovladače zařízení, jejichž identifikátory GUID třídy nastavení zařízení se zobrazí v seznamu, který vytvoříte. Pokud nastavení této zásady povolíte na vzdáleném počítači, nastavení zásad bude mít vliv na přesměrování zadaných zařízení z klienta vzdálené plochy na server vzdálené plochy. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, může systém Windows instalovat a aktualizovat zařízení podle povolených nebo zabránících jiným nastavením zásad.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067048)  
  
  **Výchozí**: blokovat instalaci hardwarového zařízení  

  Když je vybraná možnost *blokovat instalaci hardwarového zařízení* , jsou k dispozici následující nastavení.
  - **Odebrat shodná hardwarová zařízení**    
    Toto nastavení je dostupné, jenom když je *Instalace hardwarového zařízení podle instalačních tříd* nastavená tak, aby *blokovala instalaci hardwarového zařízení*.  

    **Výchozí**: *žádná výchozí konfigurace*  

  - **Blokované identifikátory hardwarových zařízení**  
    Toto nastavení je dostupné, jenom když je *Instalace hardwarového zařízení podle instalačních tříd* nastavená tak, aby *blokovala instalaci hardwarového zařízení*.
    
    **Výchozí**: *žádná výchozí konfigurace*  

## <a name="device-lock"></a>Zámek zařízení  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) .  

- **Zabránit použití kamery**  
  Zakáže přepínač kamery zamykací obrazovky v nastavení počítače a zabraňuje tomu, aby se kamera vyvolala na zamykací obrazovce. Ve výchozím nastavení můžou uživatelé povolit vyvolání dostupné kamery na zamykací obrazovce. Pokud toto nastavení povolíte, uživatelé již nebudou moci povolit nebo zakázat přístup k fotoaparátu zamykací obrazovky v nastavení počítače a fotoaparát nelze vyvolat na zamykací obrazovce.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067052)
  
  **Výchozí**: povoleno  

- **Vyžadovat heslo**  
  Určuje, jestli je povolený zámek zařízení.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067049)  
  
  **Výchozí**: Ano  
  
  Pokud je možnost *vyžadovat heslo* nastavená na *hodnotu Ano*, jsou k dispozici následující nastavení.

  - **Minimální počet znakových sad pro heslo**  
    Počet komplexních typů prvků (velká a malá písmena, číslice a interpunkční znaménka) vyžadované pro silný kód PIN nebo heslo. PIN kód vynutil následující chování pro stolní a mobilní zařízení: 1-číslice pouze 2 – číslice a malá písmena jsou vyžadována 3 číslicemi, malými písmeny a velkými písmeny. Nepodporováno v účtech Microsoft Desktop a doménových účtů. vyžadují se 4 číslice, malá písmena, Velká písmena a speciální znaky. Nepodporuje se v desktopu. Výchozí hodnota je 1.  
    [Další informace](https://go.microsoft.com/fwlink/?linkid=2067055)  
    
    **Výchozí hodnota**: 3  

  - **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**  
    Počet povolených neúspěšných ověření, než se zařízení vymaže. Hodnota 0 zakáže funkci vymazání zařízení.  
    [Další informace](https://go.microsoft.com/fwlink/?linkid=2067030)  
      
    **Výchozí**: 10  

  - **Vypršení platnosti hesla (dny)**  
    Nastavení zásad maximální stáří hesla určuje, jak dlouho (ve dnech) se dá heslo použít, než systém vyžaduje, aby ho uživatel změnil. Můžete nastavit, aby platnost hesla vyprší po uplynutí počtu dní od 1 do 999, nebo můžete zadat, že hesla budou nikdy vypršet nastavením počtu dní na hodnotu 0. Pokud je maximální stáří hesla mezi 1 a 999 dny, minimální stáří hesla musí být kratší než maximální stáří hesla. Pokud je maximální stáří hesla nastavené na 0, minimální stáří hesla může být libovolná hodnota mezi 0 a 998 dny.  
    [Další informace](https://go.microsoft.com/fwlink/?linkid=2067028)  
    
    **Výchozí**: 60  

  - **Požadovaný typ hesla**  
    Určuje typ kódu PIN nebo hesla, které se vyžaduje.  
    [Další informace](https://go.microsoft.com/fwlink/?linkid=2067027)  
    
    **Výchozí**: alfanumerické  

  - **Minimální délka hesla**  
    Nastavení zásad minimální délky hesla určuje nejmenší počet znaků, které mohou vytvořit heslo pro uživatelský účet. Můžete nastavit hodnotu v rozmezí 1 až 14 znaků nebo můžete určit, že není vyžadováno žádné heslo nastavením počtu znaků na 0.  
    [Další informace](https://go.microsoft.com/fwlink/?linkid=2067024)  
    
    **Výchozí**: 8  

  - **Blokovat jednoduchá hesla**  
    Určuje, jestli jsou povolené PIN kódy nebo hesla, jako je "1111" nebo "1234". Pro plochu také řídí použití hesel s obrázkem.  
    [Další informace](https://go.microsoft.com/fwlink/?linkid=2067127) 
    
    **Výchozí**: Ano  
      *Nastavení Ano zabraňuje použití jednoduchých hesel.* 

  - **Znemožnit opakované použití předchozích hesel**  
    Určuje, kolik hesel může být uloženo v historii, kterou nelze použít. Hodnota zahrnuje aktuální heslo uživatele. Například když se nastaví hodnota *1* , nemůže uživatel při volbě nového hesla znovu použít svoje aktuální heslo. Nastavení *5* znamená, že uživatel nemůže nastavit nové heslo na aktuální heslo nebo předchozí čtyři hesla.  
    [Další informace](https://go.microsoft.com/fwlink/?linkid=2066795)  
    
    **Výchozí hodnota**: 24  

- **Zabránit zobrazení prezentace**  
  Zakáže nastavení prezentace snímků zamykací obrazovky v nastavení počítače a zabrání přehrávání prezentace na zamykací obrazovce. Ve výchozím nastavení mohou uživatelé povolit zobrazení prezentace, které se spustí poté, co počítač zamkne. Pokud toto nastavení povolíte, uživatelé nebudou moct měnit nastavení prezentace v nastavení počítače a nebude možné spustit žádné zobrazení prezentace.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067105) 
  
  **Výchozí**: povoleno  
  *Nastavení Enabled zabraňuje spuštění snímků.* 

- **Minimální stáří hesla ve dnech**  
  Nastavení zásad minimální stáří hesla určuje dobu (ve dnech), po kterou se heslo musí používat, než ho uživatel může změnit. Můžete nastavit hodnotu v rozmezí od 1 do 998 dnů nebo můžete změny hesel okamžitě zakázat nastavením počtu dnů na 0. Minimální stáří hesla musí být kratší než maximální stáří hesla, pokud je maximální stáří hesla nastaveno na hodnotu 0, což znamená, že hesla nebudou nikdy vypršet. Pokud je maximální stáří hesla nastavené na 0, minimální stáří hesla se dá nastavit na libovolnou hodnotu mezi 0 a 998.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067022) 
  
  **Výchozí hodnota**: 1  

## <a name="dma-guard"></a>Ochrana DMA  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – DmaGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard) .
- **Výčet externích zařízení nekompatibilních s režimem ochrany DMA v jádře**  
  Cílem této zásady je zajistit další zabezpečení proti externímu zařízení podporujícím technologii DMA. Umožňuje lepší kontrolu nad výčtem externích zařízení s technologií DMA, která nejsou kompatibilní s přemapováním DMA/izolací paměti zařízení a sandboxing. Tato zásada se projeví jenom v případě, že je ochrana DMA pro jádro podporovaná a povolená systémovým firmwarem. Ochrana pomocí jádra DMA je funkce platformy, kterou nelze řídit pomocí zásad nebo koncového uživatele. Musí být podporován systémem v době výroby. Pokud chcete zjistit, jestli systém podporuje ochranu před nejenom jádrem, zkontrolujte prosím na stránce Souhrn v souboru MSINFO32. exe pole ochrana za jádro DMA.  
  [Další informace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  **Výchozí**: Blokovat vše   

## <a name="event-log-service"></a>Služba protokolu událostí  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) .  

- **Maximální velikost souboru protokolu zabezpečení v KB**  
  Nastavení této zásady určuje maximální velikost souboru protokolu v kilobajtech. Pokud nastavení této zásady povolíte, můžete nakonfigurovat maximální velikost souboru protokolu na 1 megabajt (1024 kilobajtů) a 2 terabajty (2147483647 kilobajtů) v kilobajtech. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, bude maximální velikost souboru protokolu nastavena na místně konfigurovanou hodnotu. Tuto hodnotu může změnit místní správce pomocí dialogu Vlastnosti protokolu a výchozí hodnota je 20 megabajtů.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067042)  
  
   **Výchozí**: 196608  

- **Maximální velikost souboru protokolu systému v KB**  
  Nastavení této zásady určuje maximální velikost souboru protokolu v kilobajtech. Pokud nastavení této zásady povolíte, můžete nakonfigurovat maximální velikost souboru protokolu na 1 megabajt (1024 kilobajtů) a 2 terabajty (2147483647 kilobajtů) v kilobajtech. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, bude maximální velikost souboru protokolu nastavena na místně konfigurovanou hodnotu. Tuto hodnotu může změnit místní správce pomocí dialogu Vlastnosti protokolu a výchozí hodnota je 20 megabajtů.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2066798)  
  
  **Výchozí**: 32768  

- **Maximální velikost souboru protokolu aplikace v KB**  
  Nastavení této zásady určuje maximální velikost souboru protokolu v kilobajtech. Pokud nastavení této zásady povolíte, můžete nakonfigurovat maximální velikost souboru protokolu na 1 megabajt (1024 kilobajtů) a 2 terabajty (2147483647 kilobajtů) v kilobajtech. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, bude maximální velikost souboru protokolu nastavena na místně konfigurovanou hodnotu. Tuto hodnotu může změnit místní správce pomocí dialogu Vlastnosti protokolu a výchozí hodnota je 20 megabajtů.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067125)  
  
  **Výchozí**: 32768  

## <a name="experience"></a>Prostředí  
Další informace najdete v dokumentaci k Windows v tématu [zásady pro poskytovatele cloudu](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) .  

- **Blokování Windows Spotlightu**  
  Umožňuje správcům IT vypnout všechny funkce Windows Spotlight – okno Spotlight na zamykací obrazovce, tipy pro Windows, funkce Microsoftu pro zákazníky a další související funkce.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067037)  
  
  **Výchozí**: Ano  

  Pokud je u možnosti *blokovat Windows Spotlight* nastavená hodnota *Ano*, jsou k dispozici následující nastavení.
  
  - **Zablokovat návrhy třetích stran ve Windows Spotlightu**  
    Určuje, jestli se mají povolit návrhy aplikací a obsahu od vydavatelů softwaru třetích stran ve funkcích Windows Spotlight, jako je Spotlight na zamykací obrazovce, navrhované aplikace v nabídce Start a tipy pro Windows. Uživatelé se pořád můžou podívat na návrhy funkcí, aplikací a služeb Microsoftu.  
    [Další informace](https://go.microsoft.com/fwlink/?linkid=2067045)  
      
    **Výchozí**: Ano  
  - **Zablokovat funkce specifické pro uživatele**  
    Umožňuje správcům IT zapnout prostředí, která jsou typicky jenom pro příjemce, jako jsou návrhy spuštění, oznámení o členství, instalace aplikace po POČÁTEČNÍm startu a přesměrovat dlaždice.  
    [Další informace](https://go.microsoft.com/fwlink/?linkid=2067054)  
     
    **Výchozí**: Ano  

## <a name="exploit-guard"></a>Zneužití Guard  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) .  

- **XML ochrany před zneužitím**  
  Umožňuje správci IT doručovat konfiguraci, která představuje požadované možnosti pro zmírnění rizika systému a aplikace pro všechna zařízení v organizaci. Konfigurace je reprezentovaná kódem XML. Ochrana před zneužitím pomáhá chránit zařízení před malwarem, který využívá zneužití k rozšíření a nakazit. Pomocí aplikace zabezpečení systému Windows nebo PowerShellu vytvoříte sadu zmírnění hrozeb (označované jako konfigurace). Tuto konfiguraci pak můžete exportovat jako soubor XML a sdílet ho s více počítači ve vaší síti, aby všichni měli stejnou sadu nastavení pro zmírnění rizik. Existující konfigurační soubor XML nástroje EMET můžete také převést a importovat do konfiguračního souboru XML ochrany před zneužitím.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067035)  
  
  **Výchozí**: *je zadaný ukázkový kód XML* . 
 
## <a name="file-explorer"></a>Průzkumník souborů  
Další informace najdete v dokumentaci k systému Windows v tématu [zásady CSP – Průzkumník](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) souborů.  

- **Zabránění spuštění dat blokování**  
  Zakázání prevence spuštění dat může některé starší verze modulů plug-in umožňovat fungování bez ukončení Průzkumníka.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067043)  
  
  **Výchozí**: zakázáno  
   
- **Blokovat ukončení haldy při poškození**  
  Vypnutí ukončení haldy při poškození může některým starším aplikacím modulu plug-in fungovat bez okamžitého ukončení Průzkumníka, i když se Průzkumník může stále neočekávaně ukončit později.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067107)  
  
  **Výchozí**: zakázáno  
    

## <a name="internet-explorer"></a>Internet Explorer  
Další informace najdete v dokumentaci k Windows v dokumentaci k [zásadě CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) .  

- **Aktualizace zóny s omezeným přístupem aplikace Internet Explorer na stavovém řádku prostřednictvím skriptu**  
  Toto nastavení zásad umožňuje spravovat, jestli může skript aktualizovat stavový řádek v rámci zóny. 
  - *Pokud nastavení této zásady povolíte*, může skript aktualizovat stavový řádek.
  - *Pokud toto nastavení zásad zakážete nebo*nenakonfigurujete, nebude moct skript aktualizovat stavový řádek.  

  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067074)  

  **Výchozí**: zakázáno

- **Internet Explorer zóna Internetu přetahování nebo kopírování a vkládání souborů**  
  Toto nastavení zásad umožňuje spravovat, jestli uživatelé můžou přetahovat soubory nebo kopírovat a vkládat soubory ze zdroje v rámci zóny. Pokud nastavení této zásady povolíte, budou uživatelé moci automaticky přetahovat soubory nebo kopírovat a vkládat soubory z této zóny. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, zobrazí se uživatelům dotaz, zda chcete soubory přetáhnout nebo zkopírovat z této zóny. Pokud nastavení této zásady zakážete, uživatelé nebudou moci přetahovat soubory nebo kopírovat a vkládat soubory z této zóny. Pokud nastavení této zásady nenakonfigurujete, uživatelé mohou automaticky přetahovat soubory nebo kopírovat a vkládat soubory z této zóny.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067076)  

  **Výchozí**: zakázat

- **Zóna s omezeným přístupem v Internet exploreru .NET Framework závislé součásti**    
  Toto nastavení zásad umožňuje spravovat, jestli .NET Framework komponenty, které nejsou podepsané pomocí technologie Authenticode, se dají spouštět z Internet Exploreru. Mezi tyto komponenty patří spravované ovládací prvky, na které se odkazuje ze značky objektu a spravované spustitelné soubory, na které odkazuje odkaz. Pokud nastavení této zásady povolíte, bude aplikace Internet Explorer spouštět nepodepsané spravované součásti. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, Internet Explorer vyzve uživatele, aby určil, zda mají být spuštěny nepodepsané spravované součásti. Pokud nastavení této zásady zakážete, nebude aplikace Internet Explorer spouštět nepodepsané spravované součásti. Pokud nastavení této zásady nenakonfigurujete, nebude aplikace Internet Explorer spouštět nepodepsané spravované součásti.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067077)

  **Výchozí**: zakázat


- **Zóna místního počítače v aplikaci Internet Explorer nespouští antimalware proti ovládacím prvkům ActiveX**  
  Nastavení této zásady určuje, jestli aplikace Internet Explorer spouští antimalwarové programy proti ovládacím prvkům ActiveX, aby zkontrolovala, jestli se dají bezpečně načíst na stránkách. Pokud nastavení této zásady povolíte, aplikace Internet Explorer nebude u antimalwarového programu kontrolovat, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, bude aplikace Internet Explorer vždy kontrolovat váš Antimalwarový program, aby bylo možné zjistit, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer nebude kontrolovat váš Antimalwarový program, aby bylo možné zjistit, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Uživatelé můžou toto chování zapnout nebo vypnout pomocí nastavení zabezpečení Internet Exploreru.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067152)

  **Výchozí**: zakázáno

- **Přístup k některým zdrojům dat Internet Exploreru Internet Exploreru**  
  Toto nastavení zásad umožňuje spravovat, jestli Internet Explorer může získat přístup k datům z jiné zóny zabezpečení pomocí analyzátoru MSXML (Microsoft XML Parser) nebo rozhraní ADO (ActiveX Data Objects) (ADO). Pokud nastavení této zásady povolíte, uživatelé mohou načíst stránku v zóně, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud v rozevíracím seznamu vyberete příkaz Dotázat se na uživatele, zobrazí se dotaz, jestli chcete, aby se stránka načetla do zóny, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud nastavení této zásady zakážete, uživatelé nemůžou načíst stránku v zóně, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud nastavení této zásady nenakonfigurujete, uživatelé nebudou moci načíst stránku v zóně, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067078)  
  
  **Výchozí**: zakázat  
  
- **Zóna s omezeným přístupem v Internet Exploreru přetahování obsahu z různých domén v rámci Windows**  
  Toto nastavení zásad umožňuje nastavit možnosti pro přetahování obsahu z jedné domény do jiné domény, pokud je zdroj a cíl ve stejném okně. Pokud nastavení této zásady povolíte a kliknete na tlačítko Povolit, mohou uživatelé přetahovat obsah z jedné domény do jiné domény, když se zdroj a cíl nacházejí ve stejném okně. Uživatelé toto nastavení nemůžou změnit. Pokud nastavení této zásady povolíte a kliknete na zakázat, uživatelé nemůžou přetahovat obsah z jedné domény do jiné domény, pokud je zdroj a cíl ve stejném okně. Uživatelé nemůžou toto nastavení změnit v dialogovém okně Možnosti Internetu. Pokud v Internet Exploreru 10 toto nastavení zásad zakážete nebo nenakonfigurujete, uživatelé nemůžou přetahovat obsah z jedné domény do jiné domény, když se zdroj a cíl nacházejí ve stejném okně. Uživatelé můžou toto nastavení změnit v dialogovém okně Možnosti Internetu. Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, uživatelé mohou v aplikaci Internet Explorer 9 a starších verzích přetahovat obsah z jedné domény do jiné domény, pokud je zdroj a cíl ve stejném okně. Uživatelé nemůžou toto nastavení změnit v dialogovém okně Možnosti Internetu.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067079)  
  
  **Výchozí**: zakázáno
  
- **Upozornění na neshodu adresy certifikátu Internet Exploreru**  
  Toto nastavení zásad umožňuje zapnout upozornění zabezpečení neshody adres certifikátů. Když je toto nastavení zásad zapnuté, zobrazí se uživateli upozornění při návštěvě zabezpečených webů protokolu HTTP (HTTPS), které prezentují certifikáty vydané pro jinou adresu webu. Toto upozornění pomáhá zabránit útokům s falešnou identitou. Pokud nastavení této zásady povolíte, zobrazí se vždy upozornění neshoda adres certifikátu. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, uživatel může zvolit, zda se zobrazí upozornění neshoda adres certifikátu (pomocí stránky Upřesnit v ovládacím panelu Internet).  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067153)  
  
  **Výchozí**: povoleno 
  
- **Méně privilegované weby v zóně s omezeným přístupem aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat, jestli weby z méně privilegovaných zón, jako jsou třeba internetové weby, můžou přejít do této zóny. Pokud nastavení této zásady povolíte, weby z méně privilegovaných zón můžou otevřít nová okna v systému nebo přejít do této zóny. Zóna zabezpečení se spustí bez přidané úrovně zabezpečení, která je k dispozici v rámci funkce zabezpečení z důvodu zvýšení úrovně ochrany zóny. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, uživateli se zobrazí upozornění, že dojde k potenciálně rizikové navigaci. Pokud nastavení této zásady zakážete, je možné, že bude znemožněna škodlivá navigace. Funkce zabezpečení aplikace Internet Explorer je v této zóně zapnutá na základě ochrany před řízením funkcí zvýšení úrovně zóny. Pokud nastavení této zásady nenakonfigurujete, mohou být potenciálně škodlivé navigační části znemožněny. Funkce zabezpečení aplikace Internet Explorer je v této zóně zapnutá na základě ochrany před řízením funkcí zvýšení úrovně zóny.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067148)  
  
  **Výchozí**: zakázat  
  
- **Automaticky vyzvat ke stažení souborů pro zónu omezeného Internet Exploreru**  
  Nastavení této zásady určuje, jestli se uživatelům zobrazí výzva k zadání souborů ke stažení, který není inicializovaný uživatelem. Bez ohledu na toto nastavení budou uživatelé dostávat dialogy pro stažení souborů pro uživatelem iniciované soubory ke stažení. Pokud povolíte toto nastavení, uživatelé obdrží dialog pro stažení souboru pro automatické pokusy o stažení. Pokud toto nastavení zakážete nebo nenakonfigurujete, soubory ke stažení, které nejsou inicializované uživatelem, se zablokují a uživatelům se zobrazí oznamovací panel místo dialogového okna pro stažení souboru. Uživatelé pak můžou kliknout na oznamovací pruh, aby se povolilo zobrazení výzvy ke stažení souboru.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067150)  
  
  **Výchozí**: zakázáno
  
- **Internet Explorer Internet Zone .NET Framework závislé součásti**  
  Toto nastavení zásad umožňuje spravovat, jestli .NET Framework komponenty, které nejsou podepsané přes technologii Authenticode, se dají spouštět z Internet Exploreru. Mezi tyto komponenty patří spravované ovládací prvky, na které se odkazuje ze značky objektu a spravované spustitelné soubory, na které odkazuje odkaz. Pokud nastavení této zásady povolíte, bude aplikace Internet Explorer spouštět nepodepsané spravované součásti. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, Internet Explorer vyzve uživatele, aby určil, zda mají být spuštěny nepodepsané spravované součásti. Pokud nastavení této zásady zakážete, nebude aplikace Internet Explorer spouštět nepodepsané spravované součásti. Pokud nastavení této zásady nenakonfigurujete, bude aplikace Internet Explorer spouštět nepodepsané spravované součásti.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067073)  
  
  **Výchozí**: zakázat 
  
- **Internet Explorer Internet Zone povoluje pouze schválené domény, aby používaly ovládací prvky ovládacích prvků ActiveX (ORS).**  
  Nastavení této zásady určuje, jestli uživatel může na webových stránkách spustit ovládací prvek ActiveX ORS. Pokud nastavení této zásady povolíte, ovládací prvek ActiveX ORS se nebude spouštět z webů v této zóně. Pokud nastavení této zásady zakážete, bude se ovládací prvek ORS aktivních X spouštět ze všech lokalit v této zóně.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067151)
  
  **Výchozí**: povoleno 
  
- **Windows Explorer – spuštěný skript zóny s omezeným přístupem**  
  Toto nastavení zásad umožňuje spravovat omezení pro automaticky otevíraná okna spouštěná skriptem a okna, která obsahují nadpis a stavové řádky. Pokud nastavení této zásady povolíte, nebude se zabezpečení na této zóně vztahovat na Windows. Zóna zabezpečení se spouští bez přidané úrovně zabezpečení, kterou poskytuje tato funkce. Pokud nastavení této zásady zakážete, budou možné škodlivé akce obsažené v automaticky otevíraných oknech a oknech spouštěných skriptem, které obsahují název a stavové řádky, které nejdou spustit. Tato funkce zabezpečení aplikace Internet Explorer je v této zóně zapnutá nastavením řízení funkcí skriptovaná omezení zabezpečení systému Windows pro daný proces. Pokud nastavení této zásady nenakonfigurujete, možné škodlivé akce obsažené v automaticky otevíraných oknech a oknech spouštěných skriptem, které obsahují název a stavové řádky, nemůžou běžet. Tato funkce zabezpečení aplikace Internet Explorer je v této zóně zapnutá nastavením řízení funkcí skriptovaná omezení zabezpečení systému Windows pro daný proces.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067075)  
  
  **Výchozí**: zakázáno 
  
- **Internetová zóna Internet Exploreru zahrnuje místní cestu při nahrávání souborů na server.**  
  Nastavení této zásady určuje, jestli se mají odesílat informace o místní cestě, když uživatel nahrává soubor prostřednictvím formuláře HTML. Pokud se odesílají informace o místní cestě, můžou být některé informace neúmyslně odhaleny serveru. Například soubory odeslané z plochy uživatele mohou obsahovat uživatelské jméno jako součást cesty. Pokud toto nastavení zásad povolíte, odesílají se informace o cestě, když uživatel nahraje soubor prostřednictvím formuláře HTML. Pokud toto nastavení zásad zakážete, informace o cestě se odeberou, když uživatel nahraje soubor prostřednictvím formuláře HTML. Pokud nastavení této zásady nenakonfigurujete, může uživatel zvolit, zda budou informace o cestě odesílány při odeslání souboru prostřednictvím formuláře HTML. Ve výchozím nastavení jsou odesílány informace o cestě.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067072)  
  
  **Výchozí**: zakázáno 
  
- **Aplikace Internet Explorer zakazuje procesy v rozšířeném chráněném režimu**  
  Nastavení této zásady určuje, jestli Internet Explorer 11 používá 64 procesy (pro vyšší zabezpečení) nebo 32 procesy (pro zajištění vyšší kompatibility) při spuštění v rozšířeném chráněném režimu na 64 bitových verzí Windows. Důležité: některé ovládací prvky ActiveX a panely nástrojů nemusí být k dispozici, když se používají 64 procesy. Pokud toto nastavení zásad povolíte, bude aplikace Internet Explorer 11 při spuštění v rozšířeném chráněném režimu na 64 verzích systému Windows používat 64 procesů na kartě bitů. Pokud toto nastavení zásad zakážete, bude aplikace Internet Explorer 11 při spuštění v rozšířeném chráněném režimu na 64 verzích systému Windows používat 32 procesů na kartě bitů. Pokud nastavení této zásady nenakonfigurujete, uživatelé mohou tuto funkci zapnout nebo vypnout pomocí nastavení aplikace Internet Explorer. Tato funkce je ve výchozím nastavení vypnutá.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067149)  
  
  **Výchozí**: povoleno 
  
- **Ignorovat chyby certifikátů v aplikaci Internet Explorer**  
  Nastavení této zásady brání uživateli ignorovat SSL (Secure Sockets Layer)/TLS (Transport Layer Security), které přeruší procházení (například vypršela platnost, odvolaná zpráva nebo "Neshoda názvů") v aplikaci Internet Explorer. Pokud nastavení této zásady povolíte, uživatel nebude moci pokračovat v procházení. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, uživatel se může rozhodnout ignorovat chyby certifikátů a pokračovat v procházení.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067071)  
  
  **Výchozí**: zakázáno 
  
- **Načítání souborů XAML v Internet Exploreru Internet Zone**  
  Toto nastavení zásad umožňuje spravovat načítání souborů jazyk Extensible Application Markup Language (XAML) (XAML). XAML je deklarativní značkovací jazyk založený na jazyce XML, který se běžně používá k vytváření bohatých uživatelských rozhraní a grafiky, které využívají Windows Presentation Foundation. Pokud nastavení této zásady povolíte a nastavíte rozevírací nabídku na povolit, soubory XAML se automaticky načtou v aplikaci Internet Explorer. Uživatel nemůže toto chování změnit. Pokud nastavíte rozevírací seznam na dotazování, uživateli se zobrazí výzva k načtení souborů XAML. Pokud toto nastavení zásad zakážete, soubory XAML nejsou načteny do aplikace Internet Explorer. Uživatel nemůže toto chování změnit. Pokud nastavení této zásady nenakonfigurujete, uživatel se může rozhodnout, zda mají být soubory XAML načteny v aplikaci Internet Explorer.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067147)  
  
  **Výchozí**: zakázat 
  
- **Automatické vyzvat k stažení souborů v Internet Exploreru Internet Zone**  
  Nastavení této zásady určuje, jestli se uživatelům zobrazí výzva k zadání souborů ke stažení, který není inicializovaný uživatelem. Bez ohledu na toto nastavení budou uživatelé dostávat dialogy pro stažení souborů pro uživatelem iniciované soubory ke stažení. Pokud povolíte toto nastavení, uživatelé obdrží dialog pro stažení souboru pro automatické pokusy o stažení. Pokud toto nastavení zakážete nebo nenakonfigurujete, soubory ke stažení, které nejsou inicializované uživatelem, se zablokují a uživatelům se zobrazí oznamovací panel místo dialogového okna pro stažení souboru. Uživatelé pak můžou kliknout na oznamovací pruh, aby se povolilo zobrazení výzvy ke stažení souboru.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067117)  
  
  **Výchozí**: zakázáno  
  
- **Upozornění zabezpečení zóny s omezeným přístupem v Internet Exploreru pro potenciálně nebezpečné soubory**  
  Toto nastavení zásad určuje, jestli se při pokusu uživatele o otevření spustitelných souborů nebo jiných potenciálně nebezpečných souborů (z intranetového sdílení souborů pomocí Průzkumníka souborů) zobrazí zpráva "otevření souboru – upozornění zabezpečení". Pokud nastavení této zásady povolíte a nastavíte rozevírací nabídku na povolit, tyto soubory se otevřou bez upozornění zabezpečení. Pokud nastavíte rozevírací seznam na dotazování, zobrazí se před otevřením souborů upozornění zabezpečení. Pokud nastavení této zásady zakážete, tyto soubory se neotevřou. Pokud nastavení této zásady nenakonfigurujete, může uživatel nakonfigurovat, jak tento počítač zpracovává tyto soubory. Ve výchozím nastavení jsou tyto soubory zablokované v zóně s omezeným přístupem, které jsou povolené v zónách intranetu a místní počítač, a nastavte, aby se zobrazila výzva v Internetu a v důvěryhodných zónách.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2066797)  
  
  **Výchozí**: zakázat  
  
- **Filtr skriptování mezi weby internetové zóny Internet Exploreru**  
  Tato zásada řídí, zda filtr skriptování mezi weby (XSS) detekuje a zabraňuje vkládání skriptu mezi weby do webů v této zóně. Pokud toto nastavení zásad povolíte, bude pro weby v této zóně zapnutý filtr XSS a filtr XSS se pokusí zablokovat vkládání skriptu mezi weby. Pokud toto nastavení zásad zakážete, je filtr XSS pro weby v této zóně vypnutý a Internet Explorer povoluje vkládání skriptů mezi weby.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067053) 
  
  **Výchozí**: povoleno 
  
- **Přechod do SSL3 z Internet Exploreru**  
  Toto nastavení zásad umožňuje zablokovat nezabezpečený přechod na SSL 3,0. Pokud je tato zásada povolená, Internet Explorer se pokusí připojit k webům pomocí protokolu SSL 3,0 nebo níže, když se TLS 1,0 nebo novější nezdaří. Doporučujeme Nepovolit nezabezpečenou zálohu, aby se zabránilo útoku prostředníkem. Tato zásada nemá vliv na to, které protokoly zabezpečení jsou povolené. Pokud tuto zásadu zakážete, použijí se výchozí nastavení systému.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067118)  
  
  **Výchozí**: žádné lokality  

- **Podpora šifrování v aplikaci Internet Explorer**  
  Toto nastavení zásad umožňuje vypnout podporu protokolu TLS (Transport Layer Security) 1,0, TLS 1,1, TLS 1,2, SSL (Secure Sockets Layer) (SSL) 2,0 nebo SSL 3,0 v prohlížeči. TLS a SSL jsou protokoly, které vám pomůžou chránit komunikaci mezi prohlížečem a cílovým serverem. Když se prohlížeč pokusí nastavit chráněnou komunikaci s cílovým serverem, prohlížeč a server vyjednají, který protokol a verze se mají použít. Prohlížeč a server se snaží porovnat seznam podporovaných protokolů a verzí každého druhého a vybere upřednostňovanou shodu. Pokud toto nastavení zásad povolíte, bude prohlížeč vyjednávat šifrovací tunel pomocí metod šifrování, které vyberete v rozevíracím seznamu, nebo ho nevyjednávat. Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, uživatel může vybrat metodu šifrování, kterou prohlížeč podporuje.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067057)

  **Výchozí**: 2 položky: TLS v 1.1 a TLS v 1.2  
  *Výběrem šipky dolů zobrazíte možnosti, které můžete pro toto nastavení vybrat.*
  
- **Internet Explorer uzamkl inteligentní obrazovka internetové zóny**  
  Nastavení této zásady určuje, zda bude filtr SmartScreen kontrolovat stránky v této zóně na škodlivý obsah. Pokud toto nastavení zásad povolíte, vyhledá filtr SmartScreen stránky v této zóně pro škodlivý obsah. Pokud nastavení této zásady zakážete, filtr SmartScreen nebude skenovat stránky v této zóně pro škodlivý obsah. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, zda má filtr SmartScreen kontrolovat stránky v této zóně pro škodlivý obsah. Poznámka: v Internet Exploreru 7 Toto nastavení zásad určuje, jestli má filtr útoků phishing kontrolovat stránky v této zóně pro škodlivý obsah.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067059)  
  
  **Výchozí**: povoleno 
  
- **Zóna s omezeným přístupem Internet Exploreru spouští aplikace a soubory v iFrame.**  
  Toto nastavení zásad umožňuje spravovat, jestli můžou být aplikace spuštěné, a z odkazu na IFRAME v HTML stránek v této zóně se můžou stahovat soubory. Pokud nastavení této zásady povolíte, můžou uživatelé spouštět aplikace a stahovat soubory z IFRAME na stránkách v této zóně bez zásahu uživatele. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, zobrazí se uživatelům dotaz, zda chcete spouštět aplikace a stahovat soubory z prvků IFRAME na stránkách v této zóně. Pokud toto nastavení zásad zakážete, budou se uživatelé moci spouštět aplikace a stahovat soubory z IFRAME na stránkách v této zóně. Pokud nastavení této zásady nenakonfigurujete, uživatelé budou moci spouštět aplikace a stahovat soubory z prvků IFRAME na stránkách v této zóně.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067061)  
  
  **Výchozí**: zakázat 
  
- **Internet Explorer obejít upozornění na inteligentní obrazovku na Neběžné soubory**  
  Nastavení této zásady určuje, jestli uživatel může obejít upozornění z filtru SmartScreen. Filtr SmartScreen uživatele upozorní na spustitelné soubory, které uživatelé Internet Exploreru nestahují běžným z Internetu. Pokud toto nastavení zásad povolíte, upozornění filtru SmartScreen blokují uživatele. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, může uživatel obejít upozornění filtru SmartScreen.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067068)  
  
  **Výchozí**: zakázáno  
  
- **Blokování automaticky otevíraných oken internetové zóny Internet Exploreru**  
  Toto nastavení zásad umožňuje spravovat, jestli se zobrazí nežádoucí automaticky otevíraná okna. Automaticky otevíraná okna, která se otevřou, když koncový uživatel klikne na odkaz, se nezablokuje. Pokud nastavení této zásady povolíte, nebudete moci zobrazovat většinu nežádoucích překryvných oken. Pokud nastavení této zásady zakážete, automaticky otevíraná okna se nebudou bránit v zobrazování. Pokud nastavení této zásady nenakonfigurujete, nebudete moci zobrazovat většinu nežádoucích překryvných oken.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067069)  
  
  **Výchozí**: Povolit  
  
- **Aplikace Internet Explorer zpracovává konzistentní zpracování MIME**  
  Internet Explorer obsahuje dynamické binární chování: komponenty, které zapouzdřují konkrétní funkce pro prvky HTML, ke kterým jsou připojené. Nastavení této zásady určuje, jestli se má zakázat nebo povolit nastavení omezení zabezpečení binárního chování. Pokud nastavení této zásady povolíte, binární chování se zabrání pro procesy v Průzkumníkovi souborů a v aplikaci Internet Explorer. Pokud toto nastavení zásad zakážete, pro procesy Průzkumníka souborů a aplikace Internet Explorer jsou povoleny binární chování. Pokud nastavení této zásady nenakonfigurujete, binární chování se zabrání pro procesy v Průzkumníkovi souborů a v aplikaci Internet Explorer.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067144)  
  
  **Výchozí**: povoleno  
  
- **Oprávnění pro přístup k zóně Java v Internet Exploreru**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety v jazyce Java. Pokud nastavení této zásady povolíte, můžete v rozevíracím seznamu zvolit možnosti. Vlastní pro řízení nastavení oprávnění individuálně. Nízké zabezpečení umožňuje apletům provádět všechny operace. Střední zabezpečení umožňuje apletům běžet v izolovaném prostoru (sandboxu) (oblast v paměti mimo rámec toho, že program nemůže provádět volání) a navíc funkce, jako je například pomocné místo (bezpečná a zabezpečená oblast úložiště v klientském počítači) a uživatelem řízený vstup/výstup souborů. Vysoké zabezpečení umožňuje, aby se applety spouštěly v izolovaném prostoru. Zakáže Java, aby se zabránilo spuštění všech apletů. Pokud nastavení této zásady zakážete, aplety Java nepůjde spustit. Pokud nastavení této zásady nenakonfigurujete, aplety Java budou zakázané.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067132)  
  
  **Výchozí**: zakázat Java  
    
  
- **Ovládací prvky ActiveX aplikace Internet Explorer v chráněném režimu**  
  Nastavení této zásady zabraňuje spuštění ovládacích prvků ActiveX v chráněném režimu, je-li povolen Rozšířený chráněný režim. Když má uživatel nainstalovaný ovládací prvek ActiveX, který není kompatibilní s rozšířeným chráněným režimem a web se pokusí načíst ovládací prvek, Internet Explorer uživatele upozorní a nabídne možnost spustit web v normálním chráněném režimu. Nastavení této zásady zakáže toto oznámení a vynutí spuštění všech webů v rozšířeném chráněném režimu. Rozšířený chráněný režim poskytuje dodatečnou ochranu před škodlivými weby pomocí 64 procesů na 64 verzích systému Windows. V počítačích s minimálně Windows 8 se v rozšířeném chráněném režimu taky omezují umístění, ze kterých může Internet Explorer číst v registru a v systému souborů. Pokud je povolený Rozšířený chráněný režim a uživatel se nachází na webu, který se pokusí načíst ovládací prvek ActiveX, který není kompatibilní se zapnutým rozšířeným chráněným režimem, Internet Explorer uživatele upozorní a nabídne možnost zakázat Rozšířený chráněný režim pro konkrétní web. Pokud toto nastavení zásad povolíte, uživateli Internet Exploreru nebude umožněno zakázat Rozšířený chráněný režim. Všechny weby s chráněným režimem budou spouštěny v rozšířeném chráněném režimu. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, Internet Explorer upozorní uživatele a nabídne možnost spouštět weby s nekompatibilními ovládacími prvky ActiveX v normálním chráněném režimu.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067145)  
  
  **Výchozí**: zakázáno  
  
- **Načítání souborů XAML v zóně s omezeným přístupem v aplikaci Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat načítání souborů jazyk Extensible Application Markup Language (XAML) (XAML). XAML je deklarativní značkovací jazyk založený na jazyce XML, který se běžně používá k vytváření bohatých uživatelských rozhraní a grafiky, které využívají Windows Presentation Foundation. Pokud nastavení této zásady povolíte a nastavíte rozevírací nabídku na povolit, soubory XAML se automaticky načtou v aplikaci Internet Explorer. Uživatel nemůže toto chování změnit. Pokud nastavíte rozevírací seznam na dotazování, uživateli se zobrazí výzva k načtení souborů XAML. Pokud toto nastavení zásad zakážete, soubory XAML nejsou načteny do aplikace Internet Explorer. Uživatel nemůže toto chování změnit. Pokud nastavení této zásady nenakonfigurujete, uživatel se může rozhodnout, zda mají být soubory XAML načteny v aplikaci Internet Explorer.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067070)  
  
  **Výchozí**: zakázat  
  
- **Aplikace Internet Explorer zpracovává omezení zabezpečení oken pomocí skriptů.**  
  Internet Explorer umožňuje skriptům otevírání, změny velikosti a přemístění oken různých typů prostřednictvím kódu programu. Funkce zabezpečení omezení okna omezuje místní okna a zakáže zobrazování skriptů v oknech, ve kterých se nezobrazuje název a stavové řádky uživatele nebo zakazují jiné tituly a stavy oken. Pokud nastavení této zásady povolíte, budou se v oknech s použitím skriptů pro všechny procesy omezovat. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, nezobrazí se v oknech s použitím skriptů.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067146)  
  
  **Výchozí**: povoleno   
  
- **Zóna s omezeným přístupem pro Internet Explorer spouští ovládací prvky a moduly plug-in**  
  Toto nastavení zásad umožňuje spravovat, jestli se můžou ovládací prvky ActiveX a moduly plug-in spouštět na stránkách ze zadané zóny. Pokud nastavení této zásady povolíte, ovládací prvky a moduly plug-in se můžou spouštět bez zásahu uživatele. Pokud jste vybrali možnost zobrazit v rozevíracím seznamu, zobrazí se uživatelům výzva, aby zvolili, zda mají být ovládací prvky nebo modul plug-in spuštěny. Pokud nastavení této zásady zakážete, ovládací prvky a moduly plug-in se nebudou spouštět. Pokud nastavení této zásady nenakonfigurujete, nebudou moci ovládací prvky a moduly plug-in běžet.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067114) 
  
  **Výchozí**: zakázat  
  
- **Ovládací prvky služby Active X s omezeným přístupem v Internet Exploreru označené jako bezpečné pro skriptování**  
  Toto nastavení zásad umožňuje spravovat, jestli ovládací prvek ActiveX označený jako bezpečný pro skriptování může komunikovat se skriptem. Pokud nastavení této zásady povolíte, bude se interakce skriptu automaticky vyskytnout bez zásahu uživatele. Pokud v rozevíracím seznamu vyberete možnost Dotázat se na uživatele, zobrazí se dotaz, jestli chcete, aby byla povolena interakce skriptu. Pokud nastavení této zásady zakážete, nebude možné docházet k interakci skriptu. Pokud nastavení této zásady nenakonfigurujete, nebudete mít k interakci s skriptem zabráněno.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067062)  
  
  **Výchozí**: zakázat  
  
- **Možnosti přihlášení k zóně omezeného Internet Exploreru**  
  Toto nastavení zásad umožňuje spravovat nastavení možností přihlášení. Pokud nastavení této zásady povolíte, můžete si vybrat z následujících možností přihlášení. 
  - *Anonymní* – pomocí anonymního přihlášení můžete zakázat ověřování protokolem HTTP a použít účet hosta jenom pro protokol CIFS (Common Internet File System). 
  - *Výzva* – pomocí výzvy k zadání uživatelského jména a hesla můžete zadávat dotazy uživatelů na ID a hesla uživatelů. Po zadání dotazu na uživatele lze tyto hodnoty použít v tichém režimu pro zbytek relace. 
  - *Automatické přihlašování pouze v zóně intranetu* – pomocí této možnosti můžete zadávat dotazy uživatelů na uživatelská ID a hesla v jiných zónách. Po zadání dotazu na uživatele lze tyto hodnoty použít v tichém režimu pro zbytek relace. 
  - *Automatické přihlašování pomocí aktuálního uživatelského jména a hesla*– tuto možnost použijte, pokud se chcete pokusit přihlásit pomocí výzvy Windows NT Challenge Response (označované také jako ověřování NTLM). Pokud server podporuje reakci na výzvu systému Windows NT, přihlašování používá uživatelské jméno a heslo uživatele v síti pro přihlášení. Pokud server nepodporuje reakci Windows NT Challenge, je uživatel dotazován na zadání uživatelského jména a hesla. 

  Pokud nastavení této zásady zakážete, přihlašování se nastaví na *Automatické přihlašování jenom v zóně intranetu*. Pokud nastavení této zásady nenakonfigurujete, přihlašování se nastaví tak, aby se *zobrazilo výzva k zadání* uživatelského jména a hesla.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067110)  
  
  **Výchozí**: anonymní  
  
- **Inicializace důvěryhodné zóny Internet Exploreru a skriptování aktivních X ovládacích prvků není označeno jako bezpečné**  
  Toto nastavení zásad umožňuje spravovat ovládací prvky ActiveX, které nejsou označeny jako bezpečné. Pokud nastavení této zásady povolíte, budou ovládací prvky ActiveX spouštěny, načteny s parametry a pomocí skriptů bez nastavení bezpečnosti objektů pro nedůvěryhodná data nebo skripty. Toto nastavení se nedoporučuje, s výjimkou zabezpečených a spravovaných zón. Toto nastavení způsobí, že budou inicializovány nebezpečné i bezpečné ovládací prvky a budou skriptované, ignorování ovládacích prvků ActiveX skriptu označených jako bezpečné pro možnost skriptování. Pokud nastavení této zásady povolíte a v rozevíracím seznamu vyberete možnost zobrazit výzvu, uživatelé se dotazují, jestli chcete ovládacímu prvku povolit načtení pomocí parametrů nebo skriptu. Pokud nastavení této zásady zakážete, nebudou se ovládací prvky ActiveX, které se dají bezpečně nastavit, načítat pomocí parametrů nebo skriptu. Pokud nastavení této zásady nenakonfigurujete, budou uživatelé dotazováni na to, zda má ovládací prvek načíst s parametry nebo pomocí skriptu.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067137)  
  
  **Výchozí**: zakázat  
  
- **Aplikace Internet Explorer kontroluje odvolání certifikátu serveru.**  
  Toto nastavení zásad umožňuje spravovat, jestli Internet Explorer bude kontrolovat stav odvolání certifikátů serverů. Certifikáty jsou odvolány, když jsou ohroženy nebo již nejsou platné, a tato možnost chrání uživatele před odesláním důvěrných dat do webu, který může být podvodný nebo není zabezpečený. Pokud toto nastavení zásad povolíte, bude aplikace Internet Explorer kontrolovat, zda byly certifikáty serveru odvolány. Pokud nastavení této zásady zakážete, aplikace Internet Explorer nebude kontrolovat certifikáty serveru, aby zjistila, jestli se odvolala. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer nebude kontrolovat certifikáty serveru a zjistí, zda byly odvolány.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067046)  
  
  **Výchozí**: povoleno 
  
- **Méně privilegované weby Internet Exploreru Internet Zone**  
  Toto nastavení zásad umožňuje spravovat, jestli weby z méně privilegovaných zón, jako jsou servery s omezeným přístupem, můžou přejít do této zóny. Pokud nastavení této zásady povolíte, weby z méně privilegovaných zón můžou otevřít nová okna v systému nebo přejít do této zóny. Zóna zabezpečení se spustí bez přidané úrovně zabezpečení, která je k dispozici v rámci funkce zabezpečení z důvodu zvýšení úrovně ochrany zóny. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, uživateli se zobrazí upozornění, že dojde k potenciálně rizikové navigaci. Pokud nastavení této zásady zakážete, mohou být potenciálně škodlivé navigační části znemožněny. Funkce zabezpečení aplikace Internet Explorer je v této zóně zapnutá na základě ochrany před řízením funkcí zvýšení úrovně zóny. Pokud nastavení této zásady nenakonfigurujete, můžou weby z méně privilegovaných zón otevřít nová okna v systému nebo přejít do této zóny.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067109)  
  
  **Výchozí**: zakázat  
  
- **Stažení souborů zóny s omezeným přístupem aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat, jestli se mají v zóně povolit stahování souborů. Tato možnost je určena zónou stránky s odkazem způsobující stahování, nikoli zónou, ze které je soubor doručen. Pokud toto nastavení zásad povolíte, soubory je možné stáhnout ze zóny. Pokud nastavení této zásady zakážete, nebudou se soubory ze zóny stahovat. Pokud nastavení této zásady nenakonfigurujete, nebude možné soubory ze zóny stahovat.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067038)  
  
  **Výchozí**: zakázat  
  
- **Internetová zóna Internet Exploreru spouští .NET Framework závislé součásti podepsané pomocí technologie Authenticode**  
  Toto nastavení zásad umožňuje spravovat, jestli .NET Framework součásti, které jsou podepsané pomocí technologie Authenticode, se dají spouštět z Internet Exploreru. Mezi tyto komponenty patří spravované ovládací prvky, na které se odkazuje ze značky objektu a spravované spustitelné soubory, na které odkazuje odkaz. Pokud toto nastavení zásad povolíte, aplikace Internet Explorer spustí podepsané spravované součásti. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, Internet Explorer vyzve uživatele, aby určil, zda mají být spuštěny podepsané spravované součásti. Pokud nastavení této zásady zakážete, aplikace Internet Explorer neprovede podepsané spravované součásti. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer neprovede podepsané spravované součásti.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067033)  
  
  **Výchozí**: zakázat  
  
- **Zakázat instalaci ovládacích prvků X v aplikaci Internet Explorer na základě uživatele**  
  Toto nastavení zásad umožňuje zabránit instalaci ovládacích prvků ActiveX na základě jednotlivých uživatelů. Pokud toto nastavení zásad povolíte, nebudete moct ovládací prvky ActiveX instalovat individuálně pro jednotlivé uživatele. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, bude možné ovládací prvky ActiveX nainstalovat na základě jednotlivých uživatelů.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067058)  
  
  **Výchozí**: povoleno  
  
- **Zabránit správě filtru Smart Screen v aplikaci Internet Explorer**  
  Nastavení této zásady zabrání uživateli ve správě filtru SmartScreen, který uživatele upozorní, pokud je web, který navštíví, známý pro podvodné pokusy o shromáždění osobních údajů prostřednictvím "phishing" nebo je známý pro hostování malwaru. Pokud nastavení této zásady povolíte, nezobrazí se uživateli výzva k zapnutí filtru SmartScreen. Všechny webové adresy, které nejsou na seznamu povolených filtrů, se automaticky odesílají do Microsoftu bez vyzvání uživatele. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, uživateli se zobrazí výzva k rozhodnutí, zda zapnout filtr SmartScreen během prvního spuštění.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067135)  
  
  **Výchozí**: Povolit  
  
- **Aplikace Internet Explorer zpracovává funkci bezpečnosti sledování toku MIME**  
  Nastavení této zásady určuje, zda bude služba Internet Explorer MIME zabráněno povýšení souboru jednoho typu na více než nebezpečný typ souboru. Pokud nastavení této zásady povolíte, nebude se v kódování MIME nikdy propagovat soubor jednoho typu na více než nebezpečný typ souboru. Pokud nastavení této zásady zakážete, budou procesy aplikace Internet Explorer umožňovat, aby se pro určitý typ souboru s více než nebezpečným typem souborů mohl sledovat protokol MIME. Pokud nastavení této zásady nenakonfigurujete, nebude monitorování v kódování MIME nikdy podporovat soubor jednoho typu na více než nebezpečný typ souboru.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067124)  
  
  **Výchozí**: povoleno  
  
- **Stažení zóny s omezeným přístupem pro Internet Explorer bylo podepsané aktivní X ovládací prvky**  
  Toto nastavení zásad umožňuje spravovat, jestli uživatelé můžou stahovat podepsané ovládací prvky ActiveX ze stránky v zóně. Pokud tuto zásadu povolíte, můžou uživatelé stahovat podepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, uživatelé se dotazují, zda mají stahovat ovládací prvky podepsané vydavateli, kteří nejsou považováni za důvěryhodné. Kód podepsaný důvěryhodnými vydavateli se tiše stáhne. Pokud nastavení zásad zakážete, nepůjde stáhnout podepsané ovládací prvky. Pokud nastavení této zásady nenakonfigurujete, budou se uživatelé dotazovat, zda mají stahovat ovládací prvky podepsané vydavateli, kteří nejsou považováni za důvěryhodné. Kód podepsaný důvěryhodnými vydavateli se tiše stáhne.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067120) 
  
  **Výchozí**: zakázat  
  
- **Automatické dokončení aplikace Internet Explorer**  
  Tato funkce automatického dokončování si může pamatovat a navrhovat uživatelská jména a hesla ve formulářích. Pokud povolíte toto nastavení, uživatel nemůže změnit uživatelské jméno a heslo ve formulářích nebo zobrazit výzvu k uložení hesel. Funkce automatického dokončování pro uživatelská jména a hesla ve formulářích je zapnutá. Musíte rozhodnout, jestli chcete, aby se zobrazila výzva k uložení hesel. Pokud toto nastavení zakážete, uživatel nemůže změnit uživatelské jméno a heslo ve formulářích nebo zobrazit výzvu k uložení hesel. Funkce automatického dokončování pro uživatelská jména a hesla ve formulářích je vypnuta. Uživatel se taky nemůže rozhodnout, že se má zobrazit výzva k uložení hesel. Pokud toto nastavení nenakonfigurujete, bude mít uživatel volnost zapínat automatické dokončování pro uživatelské jméno a hesla ve formulářích a možnost zobrazovat výzvy k uložení hesel. Chcete-li tuto možnost zobrazit, uživatelé otevřou dialogové okno Možnosti Internetu, klikněte na kartu obsah a klikněte na tlačítko nastavení.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067122)  
  
  **Výchozí**: zakázáno  
  
- **Internet Explorer Internet Zone umožňuje spuštění jazyka VBscript**  
  Nastavení této zásady umožňuje určit, jestli se může VBScript spouštět na stránkách v určitých zónách Internet Exploreru. Vaše možnosti jsou: 
  - *Enable* – jazyk VBScript běží na stránkách v určitých zónách bez jakékoli interakce. 
  - *Výzva* – zaměstnanci se zobrazí dotaz, jestli chcete, aby se v zóně spouštěl jazyk VBScript. 
  - *Disable* – v zóně není možné spouštět skripty VBScript. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, VBScript se spustí bez jakékoli interakce v zadané zóně.    

  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067119)  
  
  **Výchozí**: zakázat  
  
- **Zóna s omezeným přístupem v aplikaci Internet Explorer povoluje použít pouze schválené domény ovládací prvky ORS aktivní X.**  
  Nastavení této zásady určuje, jestli uživatel může na webových stránkách spustit ovládací prvek ActiveX ORS. Pokud nastavení této zásady povolíte, ovládací prvek ActiveX ORS se nebude spouštět z webů v této zóně. Pokud nastavení této zásady zakážete, bude se ovládací prvek ORS aktivních X spouštět ze všech lokalit v této zóně.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067032)  
  
  **Výchozí**: povoleno  
  
- **Důvěryhodná zóna aplikace Internet Explorer nespouští antimalware proti ovládacím prvkům ActiveX**  
  Nastavení této zásady určuje, jestli aplikace Internet Explorer spouští antimalwarové programy proti ovládacím prvkům ActiveX, aby zkontrolovala, jestli se dají bezpečně načíst na stránkách. Pokud nastavení této zásady povolíte, aplikace Internet Explorer nebude u antimalwarového programu kontrolovat, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, bude aplikace Internet Explorer vždy kontrolovat váš Antimalwarový program, aby bylo možné zjistit, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, bude aplikace Internet Explorer vždy kontrolovat váš Antimalwarový program, aby bylo možné zjistit, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Uživatelé můžou toto chování zapnout nebo vypnout pomocí nastavení zabezpečení Internet Exploreru.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067115)  
  
  **Výchozí**: zakázáno 
  
- **Oprávnění pro zónu místního počítače s Internet Explorerem v prostředí Java**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety v jazyce Java. Pokud nastavení této zásady povolíte, můžete v rozevíracím seznamu zvolit možnosti. Vlastní pro řízení nastavení oprávnění individuálně. Nízké zabezpečení umožňuje apletům provádět všechny operace. Střední zabezpečení umožňuje apletům běžet v izolovaném prostoru (sandboxu) (oblast v paměti mimo rámec toho, že program nemůže provádět volání) a navíc funkce, jako je například pomocné místo (bezpečná a zabezpečená oblast úložiště v klientském počítači) a uživatelem řízený vstup/výstup souborů. Vysoké zabezpečení umožňuje, aby se applety spouštěly v izolovaném prostoru. Zakáže Java, aby se zabránilo spuštění všech apletů. Pokud nastavení této zásady zakážete, aplety Java nepůjde spustit. Pokud nastavení této zásady nenakonfigurujete, bude oprávnění nastaveno na střední úroveň zabezpečení.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067113)  
  
  **Výchozí**: zakázat Java 
  
- **Intranetová zóna Internet Exploreru nespouští antimalware proti ovládacím prvkům ActiveX**  
  Nastavení této zásady určuje, jestli aplikace Internet Explorer spouští antimalwarové programy proti ovládacím prvkům ActiveX, aby zkontrolovala, jestli se dají bezpečně načíst na stránkách. Pokud nastavení této zásady povolíte, aplikace Internet Explorer nebude u antimalwarového programu kontrolovat, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, bude aplikace Internet Explorer vždy kontrolovat váš Antimalwarový program, aby bylo možné zjistit, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer nebude kontrolovat váš Antimalwarový program, aby bylo možné zjistit, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Uživatelé můžou toto chování zapnout nebo vypnout pomocí nastavení zabezpečení Internet Exploreru.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067138)  
  
  **Výchozí**: zakázáno  

- **Skriptlety zóny s omezeným přístupem aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat, jestli může uživatel spustit skriptlety. Pokud nastavení této zásady povolíte, může uživatel spustit skriptlety. Pokud nastavení této zásady zakážete, nemůže uživatel spustit skriptlety. Pokud nastavení této zásady nenakonfigurujete, uživatel může povolit nebo zakázat skriptlety.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067112)  
  
  **Výchozí**: zakázáno  
  
- **Oznamovací panel procesů aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat, zda se má oznamovací panel zobrazovat pro procesy aplikace Internet Explorer, když jsou instalace souborů nebo kódu omezené. Ve výchozím nastavení se zobrazuje oznamovací pruh pro procesy aplikace Internet Explorer. Pokud toto nastavení zásad povolíte, zobrazí se pro procesy aplikace Internet Explorer oznamovací panel. Pokud nastavení této zásady zakážete, nezobrazí se pro procesy aplikace Internet Explorer oznamovací panel. Pokud nastavení této zásady nenakonfigurujete, oznamovací panel se nezobrazí pro procesy aplikace Internet Explorer.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067139)  
  
  **Výchozí**: povoleno  
  
- **Stažení podepsaných ovládacích prvků ActiveX na internetovou zónu Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat, jestli uživatelé můžou stahovat podepsané ovládací prvky ActiveX ze stránky v zóně. Pokud tuto zásadu povolíte, můžou uživatelé stahovat podepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, uživatelé se dotazují, zda mají stahovat ovládací prvky podepsané vydavateli, kteří nejsou považováni za důvěryhodné. Kód podepsaný důvěryhodnými vydavateli se tiše stáhne. Pokud nastavení zásad zakážete, nepůjde stáhnout podepsané ovládací prvky. Pokud nastavení této zásady nenakonfigurujete, budou se uživatelé dotazovat, zda mají stahovat ovládací prvky podepsané vydavateli, kteří nejsou považováni za důvěryhodné. Kód podepsaný důvěryhodnými vydavateli se tiše stáhne.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067064)  
  
  **Výchozí**: zakázat  
  
- **Inteligentní obrazovka zóny s omezeným přístupem v Internet Exploreru**  
  Nastavení této zásady určuje, zda bude filtr SmartScreen kontrolovat stránky v této zóně na škodlivý obsah. Pokud toto nastavení zásad povolíte, vyhledá filtr SmartScreen stránky v této zóně pro škodlivý obsah. Pokud nastavení této zásady zakážete, filtr SmartScreen nebude skenovat stránky v této zóně pro škodlivý obsah. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, zda má filtr SmartScreen kontrolovat stránky v této zóně pro škodlivý obsah. Poznámka: v Internet Exploreru 7 Toto nastavení zásad určuje, jestli má filtr útoků phishing kontrolovat stránky v této zóně pro škodlivý obsah.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067034)  
  
  **Výchozí**: povoleno  
  
- **Tlačítko pro odebrání spuštění aplikace Internet Explorer pro zastaralé ovládací prvky X**  
  Toto nastavení zásad umožňuje zabránit uživatelům v prohlížení tlačítka Spustit tento čas a spouštět konkrétní zastaralé ovládací prvky ActiveX v aplikaci Internet Explorer. Pokud nastavení této zásady povolíte, nebudou se uživatelům zobrazovat tlačítka Spustit tento čas u zprávy s upozorněním, která se zobrazí, když Internet Explorer zablokuje zastaralý ovládací prvek ActiveX. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, uživatelům se zobrazí tlačítko Spustit tento čas u varovné zprávy, která se zobrazí, když aplikace Internet Explorer zablokuje zastaralý ovládací prvek ActiveX. Kliknutím na toto tlačítko umožníte uživateli spustit zastaralý ovládací prvek ActiveX jednou. Další informace najdete v tématu "zastaralé ovládací prvky ActiveX" v knihovně TechNet aplikace Internet Explorer.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067123)  
  
  **Výchozí**: povoleno 
  
- **Internet Explorer Internet Zone spustit aplikace a soubory v iframe**  
  Toto nastavení zásad umožňuje spravovat, jestli můžou být aplikace spuštěné, a z odkazu na IFRAME v HTML stránek v této zóně se můžou stahovat soubory. Pokud nastavení této zásady povolíte, můžou uživatelé spouštět aplikace a stahovat soubory z IFRAME na stránkách v této zóně bez zásahu uživatele. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, zobrazí se uživatelům dotaz, zda chcete spouštět aplikace a stahovat soubory z prvků IFRAME na stránkách v této zóně. Pokud toto nastavení zásad zakážete, budou se uživatelé moci spouštět aplikace a stahovat soubory z IFRAME na stránkách v této zóně. Pokud nastavení této zásady nenakonfigurujete, budou se uživatelé dotazovat, jestli chcete spouštět aplikace a stahovat soubory z IFRAME na stránkách v této zóně.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067020)  
  
  **Výchozí**: zakázat 
  
- **Omezená zóna Internet Exploreru navigace ve Windows a snímcích napříč různými doménami**  
  Toto nastavení zásad umožňuje nastavit možnosti pro přetahování obsahu z jedné domény do jiné domény, pokud je zdroj a cíl v různých oknech. Pokud nastavení této zásady povolíte a kliknete na tlačítko Povolit, mohou uživatelé přetahovat obsah z jedné domény do jiné domény, když se zdroj a cíl nacházejí v různých oknech. Uživatelé toto nastavení nemůžou změnit. Pokud nastavení této zásady povolíte a kliknete na zakázat, uživatelé nemůžou přetahovat obsah z jedné domény do jiné domény, pokud je zdroj i cíl v různých oknech. Uživatelé toto nastavení nemůžou změnit. Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, uživatelé nebudou moci přetahovat obsah z jedné domény do jiné domény, pokud je zdroj a cíl v různých oknech, a to v aplikaci Internet Explorer 10. Uživatelé můžou toto nastavení změnit v dialogovém okně Možnosti Internetu. Pokud v aplikaci Internet Explorer 9 a starších verzích zakážete tuto zásadu nebo ji nenakonfigurujete, uživatelé mohou přetahovat obsah z jedné domény do jiné domény, pokud je zdroj a cíl v různých oknech. Uživatelé toto nastavení nemůžou změnit.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067050)  
  
  **Výchozí**: zakázat  
  
- **Inteligentní obrazovka internetové zóny Internet Exploreru**  
  Nastavení této zásady určuje, zda bude filtr SmartScreen kontrolovat stránky v této zóně na škodlivý obsah. Pokud toto nastavení zásad povolíte, vyhledá filtr SmartScreen stránky v této zóně pro škodlivý obsah. Pokud nastavení této zásady zakážete, filtr SmartScreen nebude skenovat stránky v této zóně pro škodlivý obsah. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, zda má filtr SmartScreen kontrolovat stránky v této zóně pro škodlivý obsah. Poznámka: v Internet Exploreru 7 Toto nastavení zásad určuje, jestli má filtr útoků phishing kontrolovat stránky v této zóně pro škodlivý obsah.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067047)  
  
  **Výchozí**: povoleno  
  
- **Internet Explorer uzamkl oprávnění pro přístup k důvěryhodné zóně Java**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety v jazyce Java. Pokud nastavení této zásady povolíte, můžete v rozevíracím seznamu zvolit možnosti. Vlastní pro řízení nastavení oprávnění individuálně. Nízké zabezpečení umožňuje apletům provádět všechny operace. Střední zabezpečení umožňuje apletům běžet v izolovaném prostoru (sandboxu) (oblast v paměti mimo rámec toho, že program nemůže provádět volání) a navíc funkce, jako je například pomocné místo (bezpečná a zabezpečená oblast úložiště v klientském počítači) a uživatelem řízený vstup/výstup souborů. Vysoké zabezpečení umožňuje, aby se applety spouštěly v izolovaném prostoru. Zakáže Java, aby se zabránilo spuštění všech apletů. Pokud nastavení této zásady zakážete, aplety Java nepůjde spustit. Pokud nastavení této zásady nenakonfigurujete, aplety Java budou zakázané.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067142)  
  
  
  **Výchozí**: zakázat Java 
  
- **Aplikace Internet Explorer kontrolovat podpisy stažených programů**  
  Toto nastavení zásad umožňuje spravovat, jestli Internet Explorer před stažením spustitelných programů kontroluje digitální podpisy (které identifikují vydavatele podepsaného softwaru a před tím, než je někdo změnil nebo neoprávněný) na počítačích uživatelů. Pokud nastavení této zásady povolíte, bude aplikace Internet Explorer kontrolovat digitální podpisy spustitelných programů a zobrazovat jejich identity před jejich stažením do uživatelských počítačů. Pokud nastavení této zásady zakážete, aplikace Internet Explorer nebude kontrolovat digitální podpisy spustitelných programů nebo zobrazovat jejich identity před jejich stažením do uživatelských počítačů. Pokud tuto zásadu nenakonfigurujete, aplikace Internet Explorer nebude kontrolovat digitální podpisy spustitelných programů nebo zobrazovat jejich identity před jejich stažením do uživatelských počítačů.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067051)  
  
  **Výchozí**: povoleno  
  
- **Skript omezeného skriptování pro Internet Explorer v zóně ovládacích prvků webového prohlížeče**  
  Nastavení této zásady určuje, zda může stránka řídit vložené ovládací prvky WebBrowser prostřednictvím skriptu. Pokud nastavení této zásady povolíte, je povolený přístup ke skriptu ovládacího prvku WebBrowser. Pokud nastavení této zásady zakážete, nebude přístup k skriptu k ovládacímu prvku WebBrowser povolen. Pokud nastavení této zásady nenakonfigurujete, uživatel může povolit nebo zakázat přístup k skriptu ovládacímu prvku WebBrowser. Ve výchozím nastavení je přístup ke skriptu k ovládacímu prvku WebBrowser povolen pouze v zónách místní počítač a intranet.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067098)  
  
  **Výchozí**: zakázáno  
  
- **Filtr skriptování mezi weby v zóně s omezeným přístupem v Internet Exploreru**  
  Tato zásada řídí, zda filtr skriptování mezi weby (XSS) detekuje a zabraňuje vkládání skriptu mezi weby do webů v této zóně. Pokud toto nastavení zásad povolíte, bude pro weby v této zóně zapnutý filtr XSS a filtr XSS se pokusí zablokovat vkládání skriptu mezi weby. Pokud toto nastavení zásad zakážete, je filtr XSS pro weby v této zóně vypnutý a Internet Explorer povoluje vkládání skriptů mezi weby.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067178)  
  
  **Výchozí**: povoleno  
  
- **Binární chování zóny se zakázaným Internet Explorerem a skriptováním**  
  Toto nastavení zásad umožňuje spravovat dynamické chování binárních souborů a skriptů: komponenty, které zapouzdřují konkrétní funkce pro prvky HTML, ke kterým byly připojeny. Pokud nastavení této zásady povolíte, budou k dispozici binární chování a chování skriptů. Pokud v rozevíracím seznamu vyberete schválit správce, jsou k dispozici pouze chování uvedená v chování schválená správcem v části binární chování zásady omezení zabezpečení. Pokud toto nastavení zásad zakážete, nebude binární a chování skriptu k dispozici, pokud aplikace neimplementují vlastního správce zabezpečení. Pokud nastavení této zásady nenakonfigurujete, nebude binární chování a chování skriptu k dispozici, pokud aplikace neimplementují vlastního správce zabezpečení.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067224)  
  
  **Výchozí**: zakázat  
  
- **Ověření nastavení zabezpečení aplikace Internet Explorer**  
  Nastavením této zásady dojde k vypnutí funkce kontroly nastavení zabezpečení, která kontroluje nastavení zabezpečení aplikace Internet Explorer a určí, kdy nastavení Internet Explorer ohroženo. Pokud nastavení této zásady povolíte, funkce je vypnutá. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, je tato funkce zapnutá.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067182)  
  
  **Výchozí**: povoleno  
  
- **Upozornění zabezpečení Internetové zóny Internet Exploreru pro potenciálně nebezpečné soubory**  
  Toto nastavení zásad určuje, jestli se při pokusu uživatele o otevření spustitelných souborů nebo jiných potenciálně nebezpečných souborů (z intranetového sdílení souborů pomocí Průzkumníka souborů) zobrazí zpráva "otevření souboru – upozornění zabezpečení". Pokud nastavení této zásady povolíte a nastavíte rozevírací nabídku na povolit, tyto soubory se otevřou bez upozornění zabezpečení. Pokud nastavíte rozevírací seznam na dotazování, zobrazí se před otevřením souborů upozornění zabezpečení. Pokud nastavení této zásady zakážete, tyto soubory se neotevřou. Pokud nastavení této zásady nenakonfigurujete, může uživatel nakonfigurovat, jak tento počítač zpracovává tyto soubory. Ve výchozím nastavení jsou tyto soubory zablokované v zóně s omezeným přístupem, které jsou povolené v zónách intranetu a místní počítač, a nastavte, aby se zobrazila výzva v Internetu a v důvěryhodných zónách.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067204)  
  
  **Výchozí**: dotázat se  
  
- **Oprávnění pro intranetovou zónu Internet Exploreru**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety v jazyce Java. Pokud nastavení této zásady povolíte, můžete v rozevíracím seznamu zvolit možnosti. Vlastní pro řízení nastavení oprávnění individuálně. Nízké zabezpečení umožňuje apletům provádět všechny operace. Střední zabezpečení umožňuje apletům běžet v izolovaném prostoru (sandboxu) (oblast v paměti mimo rámec toho, že program nemůže provádět volání) a navíc funkce, jako je například pomocné místo (bezpečná a zabezpečená oblast úložiště v klientském počítači) a uživatelem řízený vstup/výstup souborů. Vysoké zabezpečení umožňuje, aby se applety spouštěly v izolovaném prostoru. Zakáže Java, aby se zabránilo spuštění všech apletů. Pokud nastavení této zásady zakážete, aplety Java nepůjde spustit. Pokud nastavení této zásady nenakonfigurujete, bude oprávnění nastaveno na střední úroveň zabezpečení.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067206)  
  
  **Výchozí**: vysoká úroveň zabezpečení 
  
- **Aplikace Internet Explorer blokuje zastaralé ovládací prvky aktivní X**   
  Nastavení této zásady určuje, jestli Internet Explorer blokuje určité zastaralé ovládací prvky ActiveX. Zastaralé ovládací prvky ActiveX nejsou nikdy blokované v zóně intranetu. Pokud nastavení této zásady povolíte, aplikace Internet Explorer zastaví blokování zastaralých ovládacích prvků ActiveX. Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, bude aplikace Internet Explorer nadále blokovat určité zastaralé ovládací prvky ActiveX. Další informace najdete v tématu "zastaralé ovládací prvky ActiveX" v knihovně TechNet aplikace Internet Explorer.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067203)  
  
  **Výchozí**: povoleno  
  
- **Blokování automaticky otevíraných oken zóny s omezeným přístupem aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat, jestli se zobrazí nežádoucí automaticky otevíraná okna. Automaticky otevíraná okna, která se otevřou, když koncový uživatel klikne na odkaz, se nezablokuje. Pokud nastavení této zásady povolíte, nebudete moci zobrazovat většinu nežádoucích překryvných oken. Pokud nastavení této zásady zakážete, automaticky otevíraná okna se nebudou bránit v zobrazování. Pokud nastavení této zásady nenakonfigurujete, nebudete moci zobrazovat většinu nežádoucích překryvných oken.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067180)  
  
  **Výchozí**: Povolit  
  
- **Aplikace Internet Explorer zpracovává omezení zabezpečení protokolu MK**  
  Nastavení zásad omezení zabezpečení protokolu MK omezuje prostor pro útoky tím, že brání protokolu MK. Prostředky hostované v protokolu MK nebudou úspěšné. Pokud nastavení této zásady povolíte, protokol MK se zabrání pro Průzkumníka souborů a Internet Explorer a prostředky hostované v protokolu v rámci služby MK nebudou úspěšné. Pokud nastavení této zásady zakážete, můžou aplikace používat rozhraní API protokolu MK. Prostředky hostované v protokolu MK budou fungovat pro procesy Průzkumníka souborů a Internet Exploreru. Pokud nastavení této zásady nenakonfigurujete, nebude možné v Průzkumníkovi souborů a v aplikaci Internet Explorer zabráněno protokolu MK a prostředky hostované v protokolu MK selžou.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067179)  
  
  **Výchozí**: povoleno  
  
- **Přístupová oprávnění k důvěryhodné zóně aplikace Internet Explorer**   
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety v jazyce Java. Pokud nastavení této zásady povolíte, můžete v rozevíracím seznamu zvolit možnosti. Vlastní pro řízení nastavení oprávnění individuálně. Nízké zabezpečení umožňuje apletům provádět všechny operace. Střední zabezpečení umožňuje apletům běžet v izolovaném prostoru (sandboxu) (oblast v paměti mimo rámec toho, že program nemůže provádět volání) a navíc funkce, jako je například pomocné místo (bezpečná a zabezpečená oblast úložiště v klientském počítači) a uživatelem řízený vstup/výstup souborů. Vysoké zabezpečení umožňuje, aby se applety spouštěly v izolovaném prostoru. Zakáže Java, aby se zabránilo spuštění všech apletů. Pokud nastavení této zásady zakážete, aplety Java nepůjde spustit. Pokud nastavení této zásady nenakonfigurujete, oprávnění je nastaveno na možnost nízká úroveň zabezpečení.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067200)  
  
  **Výchozí**: vysoká úroveň zabezpečení  
  
- **Skriptování zóny s omezeným přístupem v aplikaci Internet Explorer v apletech Java**  
  Toto nastavení zásad umožňuje spravovat, jestli jsou aplety vystavené pro skripty v rámci zóny. Pokud toto nastavení zásad povolíte, skripty budou mít přístup k apletům automaticky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberete možnost Dotázat se na uživatele, zobrazí se dotaz, jestli chcete, aby skripty mohly přistupovat k appletům. Pokud nastavení této zásady zakážete, budou se skripty bránit v přístupu k appletům. Pokud nastavení této zásady nenakonfigurujete, budou se skripty bránit v přístupu k appletům.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067202)  
  
  **Výchozí**: zakázat  
  
- **Aplikace Internet Explorer byla uzamčena s omezenou zónou oprávnění java**   
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety v jazyce Java. Pokud nastavení této zásady povolíte, můžete v rozevíracím seznamu zvolit možnosti. Vlastní pro řízení nastavení oprávnění individuálně. Nízké zabezpečení umožňuje apletům provádět všechny operace. Střední zabezpečení umožňuje apletům běžet v izolovaném prostoru (sandboxu) (oblast v paměti mimo rámec toho, že program nemůže provádět volání) a navíc funkce, jako je například pomocné místo (bezpečná a zabezpečená oblast úložiště v klientském počítači) a uživatelem řízený vstup/výstup souborů. Vysoké zabezpečení umožňuje, aby se applety spouštěly v izolovaném prostoru. Zakáže Java, aby se zabránilo spuštění všech apletů. Pokud nastavení této zásady zakážete, aplety Java nepůjde spustit. Pokud nastavení této zásady nenakonfigurujete, aplety Java budou zakázané.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067181)  
  
  **Výchozí**: zakázat Java 
  
- **Internetová zóna Internet Exploreru povoluje použití ovládacích prvků ActiveX pouze schválené domény**   
  Nastavení této zásady určuje, jestli se uživateli zobrazí výzva, aby se povolilo spouštění ovládacích prvků ActiveX na jiných webech, než na webu, který nainstaloval ovládací prvek ActiveX. Pokud nastavení této zásady povolíte, zobrazí se uživateli výzva před spuštěním ovládacích prvků ActiveX z webů v této zóně. Uživatel může zvolit, že se má ovládací prvek spouštět z aktuálního webu nebo ze všech lokalit. Pokud nastavení této zásady zakážete, uživatel nebude zobrazovat výzvu ActiveX pro jednotlivé lokality a ovládací prvky ActiveX lze spouštět ze všech lokalit v této zóně.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067091)  
  
  **Výchozí**: povoleno  
  
- **Internet Explorer zahrnuje všechny síťové cesty**  
  Internet Explorer zahrnuje všechny síťové cesty.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067090)  
  
  **Výchozí**: zakázáno 
  
- **Režim chráněný internetovou zónou Internet Exploreru**  
  Toto nastavení zásad umožňuje zapnout chráněný režim. Chráněný režim pomáhá chránit Internet Explorer před zneužitím ohrožení zabezpečení tím, že snižuje umístění, do kterých aplikace Internet Explorer může zapisovat do registru a systému souborů. Pokud nastavení této zásady povolíte, je chráněný režim zapnutý. Uživatel nemůže vypnout chráněný režim. Pokud nastavení této zásady zakážete, je chráněný režim vypnutý. Uživatel nemůže zapnout chráněný režim. Pokud nastavení této zásady nenakonfigurujete, může uživatel zapnout nebo vypnout chráněný režim.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067171)  
  
  **Výchozí**: Povolit 
  
- **Inicializovat internetovou zónu Internet Explorer a skriptovat aktivní X ovládací prvky, které nejsou označeny jako bezpečné**  
  Toto nastavení zásad umožňuje spravovat ovládací prvky ActiveX, které nejsou označeny jako bezpečné. Pokud nastavení této zásady povolíte, budou ovládací prvky ActiveX spouštěny, načteny s parametry a pomocí skriptů bez nastavení bezpečnosti objektů pro nedůvěryhodná data nebo skripty. Toto nastavení se nedoporučuje, s výjimkou zabezpečených a spravovaných zón. Toto nastavení způsobí, že budou inicializovány nebezpečné i bezpečné ovládací prvky a budou skriptované, ignorování ovládacích prvků ActiveX skriptu označených jako bezpečné pro možnost skriptování. Pokud nastavení této zásady povolíte a v rozevíracím seznamu vyberete možnost zobrazit výzvu, uživatelé se dotazují, jestli chcete ovládacímu prvku povolit načtení pomocí parametrů nebo skriptu. Pokud nastavení této zásady zakážete, nebudou se ovládací prvky ActiveX, které se dají bezpečně nastavit, načítat pomocí parametrů nebo skriptu. Pokud nastavení této zásady nenakonfigurujete, nebudou se ovládací prvky ActiveX, které se dají bezpečně nastavit, načítat pomocí parametrů nebo skriptu.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067170)  
  
  **Výchozí**: zakázat 
  
- **Aplikace Internet Explorer je uzamčena na inteligentní obrazovku zóny s omezeným přístupem**   
  Nastavení této zásady určuje, zda bude filtr SmartScreen kontrolovat stránky v této zóně na škodlivý obsah. Pokud toto nastavení zásad povolíte, vyhledá filtr SmartScreen stránky v této zóně pro škodlivý obsah. Pokud nastavení této zásady zakážete, filtr SmartScreen nebude skenovat stránky v této zóně pro škodlivý obsah. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, zda má filtr SmartScreen kontrolovat stránky v této zóně pro škodlivý obsah. Poznámka: v Internet Exploreru 7 Toto nastavení zásad určuje, jestli má filtr útoků phishing kontrolovat stránky v této zóně pro škodlivý obsah.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067092)  
  
  **Výchozí**: povoleno  
  
- **Detekce selhání aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat funkci detekce chyb v doplňku pro správu. Pokud nastavení této zásady povolíte, dojde k chybě v aplikaci Internet Explorer v systému Windows XP Professional Service Pack 1 nebo starším, a to proto, aby bylo možné vyvolat Zasílání zpráv o chybách systému Windows. Všechna nastavení zásad pro Zasílání zpráv o chybách systému Windows nadále platí. Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, funkce detekce chyb pro správu doplňku je funkční.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067094)  
  
  **Výchozí**: zakázáno  
  
- **Oprávnění Java pro internetovou zónu Internet Exploreru**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety v jazyce Java. Pokud nastavení této zásady povolíte, můžete v rozevíracím seznamu zvolit možnosti. Vlastní pro řízení nastavení oprávnění individuálně. Nízké zabezpečení umožňuje apletům provádět všechny operace. Střední zabezpečení umožňuje apletům běžet v izolovaném prostoru (sandboxu) (oblast v paměti mimo rámec toho, že program nemůže provádět volání) a navíc funkce, jako je například pomocné místo (bezpečná a zabezpečená oblast úložiště v klientském počítači) a uživatelem řízený vstup/výstup souborů. Vysoké zabezpečení umožňuje, aby se applety spouštěly v izolovaném prostoru. Zakáže Java, aby se zabránilo spuštění všech apletů. Pokud nastavení této zásady zakážete, aplety Java nepůjde spustit. Pokud nastavení této zásady nenakonfigurujete, bude oprávnění nastaveno na vysokou úroveň zabezpečení.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067174)  
  
  **Výchozí**: zakázat Java  
  
- **Aktivní skriptování zóny omezeného Internet Exploreru**  
  Toto nastavení zásad umožňuje spravovat, jestli je na stránkách v zóně spuštěný Kód skriptu. Pokud toto nastavení zásad povolíte, bude možné automaticky spouštět kód skriptu na stránkách v zóně. Pokud v rozevíracím seznamu vyberete příkaz Dotázat se na uživatele, zobrazí se dotaz, jestli chcete, aby se na stránkách v zóně mohl spustit kód skriptu. Pokud nastavení této zásady zakážete, nebudete moci spouštět kód skriptu na stránkách v zóně. Pokud nastavení této zásady nenakonfigurujete, nebudete moci spouštět kód skriptu na stránkách v zóně.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067172)  
  
  **Výchozí**: zakázat  
  
- **Možnosti přihlášení k internetové zóně Internet Exploreru**  
  Toto nastavení zásad umožňuje spravovat nastavení možností přihlášení. Pokud nastavení této zásady povolíte, můžete si vybrat z následujících možností přihlášení. Anonymní přihlášení za účelem zakázání ověřování HTTP a použití účtu hosta pouze pro protokol CIFS (Common Internet File System). Vyzvat k zadání uživatelského jména a hesla k dotazování uživatelů na ID a hesla uživatele Po zadání dotazu na uživatele lze tyto hodnoty použít v tichém režimu pro zbytek relace. Automatické přihlašování pouze v zóně intranetu pro dotazování uživatelů na ID uživatelů a hesla v jiných zónách. Po zadání dotazu na uživatele lze tyto hodnoty použít v tichém režimu pro zbytek relace. Automatické přihlášení pomocí aktuálního uživatelského jména a hesla k pokusu o přihlášení pomocí výzvy Windows NT Challenge Response (označované také jako ověřování NTLM). Pokud server podporuje reakci na výzvu systému Windows NT, přihlašování používá uživatelské jméno a heslo uživatele v síti pro přihlášení. Pokud server nepodporuje reakci Windows NT Challenge, je uživatel dotazován na zadání uživatelského jména a hesla. Pokud nastavení této zásady zakážete, možnost přihlásit se nastaví na automatické přihlašování jenom v zóně intranetu. Pokud nastavení této zásady nenakonfigurujete, možnost přihlásit se nastaví na automatické přihlašování jenom v zóně intranetu.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067194)  
  
  **Výchozí**: dotázat se  
  
- **Zóna s omezeným přístupem pro Internet Explorer umožňuje spuštění jazyka vbscript**   
  Toto nastavení zásad umožňuje spravovat, jestli můžete na stránkách ze zadané zóny v Internet Exploreru spouštět VBScript. Pokud jste v rozevíracím seznamu vybrali možnost povolit, bude možné spustit jazyk VBScript bez zásahu uživatele. Pokud jste vybrali možnost zobrazit v rozevíracím seznamu, zobrazí se uživatelům výzva k výběru, zda má být spuštěn jazyk VBScript. Pokud jste v rozevíracím seznamu vybrali možnost zakázat, nebude možné spustit jazyk VBScript. Pokud nastavení této zásady nenakonfigurujete nebo zakážete, nebude se skript VBScript moci spustit.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067173)  
  
  **Výchozí**: zakázat  
  
- **Internetová zóna Internet Exploreru přetažení obsahu z různých domén v rámci Windows**  
  Toto nastavení zásad umožňuje nastavit možnosti pro přetahování obsahu z jedné domény do jiné domény, pokud je zdroj a cíl v různých oknech. Pokud nastavení této zásady povolíte a kliknete na tlačítko Povolit, mohou uživatelé přetahovat obsah z jedné domény do jiné domény, když se zdroj a cíl nacházejí v různých oknech. Uživatelé toto nastavení nemůžou změnit. Pokud nastavení této zásady povolíte a kliknete na zakázat, uživatelé nemůžou přetahovat obsah z jedné domény do jiné domény, pokud je zdroj i cíl v různých oknech. Uživatelé toto nastavení nemůžou změnit. Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, uživatelé nebudou moci přetahovat obsah z jedné domény do jiné domény, pokud je zdroj a cíl v různých oknech, a to v aplikaci Internet Explorer 10. Uživatelé můžou toto nastavení změnit v dialogovém okně Možnosti Internetu. Pokud v aplikaci Internet Explorer 9 a starších verzích zakážete tuto zásadu nebo ji nenakonfigurujete, uživatelé mohou přetahovat obsah z jedné domény do jiné domény, pokud je zdroj a cíl v různých oknech. Uživatelé toto nastavení nemůžou změnit.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067093)  
  
  **Výchozí**: zakázáno 
  
- **Inicializovat intranetovou zónu v Internet Exploreru a skriptovat aktivní X ovládací prvky, které nejsou označené jako bezpečné**  
  Toto nastavení zásad umožňuje spravovat ovládací prvky ActiveX, které nejsou označeny jako bezpečné. Pokud nastavení této zásady povolíte, budou ovládací prvky ActiveX spouštěny, načteny s parametry a pomocí skriptů bez nastavení bezpečnosti objektů pro nedůvěryhodná data nebo skripty. Toto nastavení se nedoporučuje, s výjimkou zabezpečených a spravovaných zón. Toto nastavení způsobí, že budou inicializovány nebezpečné i bezpečné ovládací prvky a budou skriptované, ignorování ovládacích prvků ActiveX skriptu označených jako bezpečné pro možnost skriptování. Pokud nastavení této zásady povolíte a v rozevíracím seznamu vyberete možnost zobrazit výzvu, uživatelé se dotazují, jestli chcete ovládacímu prvku povolit načtení pomocí parametrů nebo skriptu. Pokud nastavení této zásady zakážete, nebudou se ovládací prvky ActiveX, které se dají bezpečně nastavit, načítat pomocí parametrů nebo skriptu. Pokud nastavení této zásady nenakonfigurujete, nebudou se ovládací prvky ActiveX, které se dají bezpečně nastavit, načítat pomocí parametrů nebo skriptu.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067175)  
  
  **Výchozí**: zakázat 
  
- **Stažené skříně aplikace Internet Explorer**  
  Nastavení této zásady zabrání uživateli v zahrnutí (příloh souborů) z informačního kanálu do počítače uživatele. Pokud nastavení této zásady povolíte, nemůže uživatel nastavit modul synchronizace informačního kanálu tak, aby stáhl skříňku prostřednictvím stránky vlastností informačního kanálu. Vývojář nemůže změnit nastavení stahování prostřednictvím rozhraní API informačního kanálu. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, může uživatel nastavit modul synchronizace informačního kanálu tak, aby stáhl skříňku prostřednictvím stránky vlastností informačního kanálu. Vývojář může změnit nastavení stahování prostřednictvím rozhraní API informačního kanálu.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067245)  
  
  **Výchozí**: zakázáno  
  
- **Nepodepsané aktivní ovládací prvky pro stažení zóny s omezeným přístupem aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat, jestli uživatelé můžou stahovat nepodepsané ovládací prvky ActiveX ze zóny. Takový kód je potenciálně škodlivý, zejména když přichází z nedůvěryhodné zóny. Pokud nastavení této zásady povolíte, můžou uživatelé spouštět nepodepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, zobrazí se uživatelům dotaz, zda chcete, aby bylo možné spustit nepodepsaný ovládací prvek. Pokud nastavení této zásady zakážete, uživatelé nemůžou spouštět nepodepsané ovládací prvky. Pokud nastavení této zásady nenakonfigurujete, uživatelé nemůžou spouštět nepodepsané ovládací prvky.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067177)  
  
  **Výchozí**: zakázat  
  
- **Internetová zóna Internet Exploreru přetahování obsahu z různých domén v rámci Windows**  
  Toto nastavení zásad umožňuje spravovat, jestli uživatelé můžou stahovat nepodepsané ovládací prvky ActiveX ze zóny. Takový kód je potenciálně škodlivý, zejména když přichází z nedůvěryhodné zóny. Pokud nastavení této zásady povolíte, můžou uživatelé spouštět nepodepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, zobrazí se uživatelům dotaz, zda chcete, aby bylo možné spustit nepodepsaný ovládací prvek. Pokud nastavení této zásady zakážete, uživatelé nemůžou spouštět nepodepsané ovládací prvky. Pokud nastavení této zásady nenakonfigurujete, uživatelé nemůžou spouštět nepodepsané ovládací prvky.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067095)  
  
  **Výchozí**: zakázáno  
  
- **Procesy aplikace Internet Explorer omezují aktivní instalaci X**   
  Nastavení této zásady umožňuje aplikacím, které hostují ovládací prvek webového prohlížeče, blokovat automatické zobrazování výzev k instalaci ovládacího prvku ActiveX. Pokud toto nastavení zásad povolíte, bude ovládací prvek webového prohlížeče blokovat automatické zobrazování výzev k instalaci ovládacího prvku ActiveX pro všechny procesy. Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, ovládací prvek webového prohlížeče nebude blokovat automatické zobrazování výzev k instalaci ovládacího prvku ActiveX pro všechny procesy.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067250)  
  
  **Výchozí**: povoleno  
  
- **Internet Explorer skriptlety Internet Zone**  
  Toto nastavení zásad umožňuje spravovat, jestli může uživatel spustit skriptlety. Pokud nastavení této zásady povolíte, může uživatel spustit skriptlety. Pokud nastavení této zásady zakážete, nemůže uživatel spustit skriptlety. Pokud nastavení této zásady nenakonfigurujete, uživatel může povolit nebo zakázat skriptlety.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067176)  
  
  **Výchozí**: zakázat  
  
- **Omezená zóna Internet Exploreru přetahování nebo kopírování a vkládání souborů**  
  Toto nastavení zásad umožňuje spravovat, jestli uživatelé můžou přetahovat soubory nebo kopírovat a vkládat soubory ze zdroje v rámci zóny. Pokud nastavení této zásady povolíte, budou uživatelé moci automaticky přetahovat soubory nebo kopírovat a vkládat soubory z této zóny. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, zobrazí se uživatelům dotaz, zda chcete soubory přetáhnout nebo zkopírovat z této zóny. Pokud nastavení této zásady zakážete, uživatelé nebudou moci přetahovat soubory nebo kopírovat a vkládat soubory z této zóny. Pokud nastavení této zásady nenakonfigurujete, zobrazí se uživatelům dotaz, zda chcete soubory z této zóny přetáhnout nebo zkopírovat.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067096)  
  
  **Výchozí**: zakázat  
  
- **Software aplikace Internet Explorer, pokud je podpis neplatný**  
  Toto nastavení zásad umožňuje spravovat, jestli může uživatel nainstalovat nebo spustit software, jako jsou ovládací prvky ActiveX a soubory ke stažení, i když signatura není platná. Neplatný podpis může indikovat, že někdo záměrně soubor úmyslně udělal. Pokud nastavení této zásady povolíte, budou uživatelé vyzváni k instalaci nebo spuštění souborů s neplatným podpisem. Pokud nastavení této zásady zakážete, uživatelé nemůžou spouštět nebo instalovat soubory s neplatným podpisem. Pokud tuto zásadu nenakonfigurujete, můžou uživatelé spouštět nebo instalovat soubory s neplatným podpisem.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067201)
  
  **Výchozí**: zakázáno  
  
- **Kopírování a vkládání zóny s omezeným přístupem v aplikaci Internet Explorer prostřednictvím skriptu**  
  Toto nastavení zásad umožňuje spravovat, jestli můžou skripty provádět operace se schránkou (například vyjmutí, kopírování a vložení) v zadané oblasti. Pokud nastavení této zásady povolíte, skript může provést operaci se schránkou. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, zobrazí se uživatelům dotaz, zda chcete provést operace se schránkou. Pokud nastavení této zásady zakážete, skript nemůže provést operaci schránky. Pokud nastavení této zásady nenakonfigurujete, skript nemůže provést operaci schránky.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067165)  
  
  **Výchozí**: zakázat  
  
- **Zóna s omezeným přístupem v Internet Exploreru přetahování obsahu z různých domén ve Windows**  
  Toto nastavení zásad umožňuje nastavit možnosti pro přetahování obsahu z jedné domény do jiné domény, pokud je zdroj a cíl v různých oknech. Pokud nastavení této zásady povolíte a kliknete na tlačítko Povolit, mohou uživatelé přetahovat obsah z jedné domény do jiné domény, když se zdroj a cíl nacházejí v různých oknech. Uživatelé toto nastavení nemůžou změnit. Pokud nastavení této zásady povolíte a kliknete na zakázat, uživatelé nemůžou přetahovat obsah z jedné domény do jiné domény, pokud je zdroj i cíl v různých oknech. Uživatelé toto nastavení nemůžou změnit. Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, uživatelé nebudou moci přetahovat obsah z jedné domény do jiné domény, pokud je zdroj a cíl v různých oknech, a to v aplikaci Internet Explorer 10. Uživatelé můžou toto nastavení změnit v dialogovém okně Možnosti Internetu. Pokud v aplikaci Internet Explorer 9 a starších verzích zakážete tuto zásadu nebo ji nenakonfigurujete, uživatelé mohou přetahovat obsah z jedné domény do jiné domény, pokud je zdroj a cíl v různých oknech. Uživatelé toto nastavení nemůžou změnit.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067166)   

  **Výchozí**: zakázáno  
  
- **Uživatelé Internet Exploreru přidávají weby**  
  Zabrání uživatelům přidávat nebo odebírat weby ze zón zabezpečení. Zóna zabezpečení je skupina webů se stejnou úrovní zabezpečení. Pokud tuto zásadu povolíte, nastavení správy lokality pro zóny zabezpečení bude zakázáno. (Pokud chcete zobrazit nastavení správy lokality pro zóny zabezpečení, klikněte v dialogovém okně Možnosti Internetu na kartu zabezpečení a pak klikněte na tlačítko weby.) Pokud tuto zásadu zakážete nebo nenakonfigurujete, můžou uživatelé přidat weby do zón důvěryhodných lokalit a serverů s omezeným přístupem nebo je z nich odebírat a změnit nastavení pro zónu místního intranetu. Tato zásada zabraňuje uživatelům měnit nastavení správy lokality pro zóny zabezpečení zřízené správcem. Poznámka: zásada "Zakázat stránku zabezpečení" (nacházející se v Ovládacích panelech \ Šablony pro správu \ součásti systému Windows\internet Explorer\Internet), která odebere kartu zabezpečení z rozhraní, má přednost před touto zásadou. Pokud je tato zásada povolená, ignoruje se. Podívejte se také na zásady zóny zabezpečení: použít jenom nastavení počítače.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067167)  
  
  **Výchozí**: zakázáno  
  
- **Windows Internet Explorer – spuštění skriptu Internet Zone**  
  Toto nastavení zásad umožňuje spravovat omezení pro automaticky otevíraná okna spouštěná skriptem a okna, která obsahují nadpis a stavové řádky. Pokud nastavení této zásady povolíte, nebude se zabezpečení na této zóně vztahovat na Windows. Zóna zabezpečení se spouští bez přidané úrovně zabezpečení, kterou poskytuje tato funkce. Pokud nastavení této zásady zakážete, budou možné škodlivé akce obsažené v automaticky otevíraných oknech a oknech spouštěných skriptem, které obsahují název a stavové řádky, které nejdou spustit. Tato funkce zabezpečení aplikace Internet Explorer je v této zóně zapnutá nastavením řízení funkcí skriptovaná omezení zabezpečení systému Windows pro daný proces. Pokud nastavení této zásady nenakonfigurujete, možné škodlivé akce obsažené v automaticky otevíraných oknech a oknech spouštěných skriptem, které obsahují název a stavové řádky, nemůžou běžet. Tato funkce zabezpečení aplikace Internet Explorer je v této zóně zapnutá nastavením řízení funkcí skriptovaná omezení zabezpečení systému Windows pro daný proces.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067088)  
  
  **Výchozí**: zakázáno  
  
- **Zóny zabezpečení aplikace Internet Explorer používají pouze nastavení počítače.**  
  Aplikuje informace o zóně zabezpečení pro všechny uživatele stejného počítače. Zóna zabezpečení je skupina webů se stejnou úrovní zabezpečení. Pokud tuto zásadu povolíte, budou se změny, které uživatel provede v zóně zabezpečení, vztahovat na všechny uživatele tohoto počítače. Pokud tuto zásadu zakážete nebo nenakonfigurujete, můžou uživatelé stejného počítače vytvořit vlastní nastavení zóny zabezpečení. Pomocí této zásady zajistíte, aby se nastavení zón zabezpečení používalo jednotně pro stejný počítač a nelišilo se od uživatele k uživateli. Podívejte se také na téma zóny zabezpečení: Nepovolit uživatelům měnit zásady.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067086)  
  
  **Výchozí**: povoleno  
  
- **Aplikace Internet Explorer byla uzamčena v zóně místního počítače oprávnění Java**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety v jazyce Java. Pokud nastavení této zásady povolíte, můžete v rozevíracím seznamu zvolit možnosti. Vlastní pro řízení nastavení oprávnění individuálně. Nízké zabezpečení umožňuje apletům provádět všechny operace. Střední zabezpečení umožňuje apletům běžet v izolovaném prostoru (sandboxu) (oblast v paměti mimo rámec toho, že program nemůže provádět volání) a navíc funkce, jako je například pomocné místo (bezpečná a zabezpečená oblast úložiště v klientském počítači) a uživatelem řízený vstup/výstup souborů. Vysoké zabezpečení umožňuje, aby se applety spouštěly v izolovaném prostoru. Zakáže Java, aby se zabránilo spuštění všech apletů. Pokud nastavení této zásady zakážete, aplety Java nepůjde spustit. Pokud nastavení této zásady nenakonfigurujete, aplety Java budou zakázané.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067253) 
  
  **Výchozí**: zakázat Java 
  
- **Zóna s omezeným přístupem v aplikaci Internet Explorer nespouští antimalware proti ovládacím prvkům** ActiveX   
  Nastavení této zásady určuje, jestli aplikace Internet Explorer spouští antimalwarové programy proti ovládacím prvkům ActiveX, aby zkontrolovala, jestli se dají bezpečně načíst na stránkách. Pokud nastavení této zásady povolíte, aplikace Internet Explorer nebude u antimalwarového programu kontrolovat, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, bude aplikace Internet Explorer vždy kontrolovat váš Antimalwarový program, aby bylo možné zjistit, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, bude aplikace Internet Explorer vždy kontrolovat váš Antimalwarový program, aby bylo možné zjistit, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Uživatelé můžou toto chování zapnout nebo vypnout pomocí nastavení zabezpečení Internet Exploreru.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067089)
  
  **Výchozí**: zakázáno  
  
- **Zóna s omezeným přístupem v aplikaci Internet Explorer spouštějte .NET Framework závislé součásti podepsané pomocí technologie Authenticode**  
  Toto nastavení zásad umožňuje spravovat, jestli .NET Framework součásti, které jsou podepsané pomocí technologie Authenticode, se dají spouštět z Internet Exploreru. Mezi tyto komponenty patří spravované ovládací prvky, na které se odkazuje ze značky objektu a spravované spustitelné soubory, na které odkazuje odkaz. Pokud toto nastavení zásad povolíte, aplikace Internet Explorer spustí podepsané spravované součásti. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, Internet Explorer vyzve uživatele, aby určil, zda mají být spuštěny podepsané spravované součásti. Pokud nastavení této zásady zakážete, aplikace Internet Explorer neprovede podepsané spravované součásti. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer neprovede podepsané spravované součásti.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067169)  
  
  **Výchozí**: zakázat  
  
- **Přístup k zóně s omezeným přístupem Internet Explorer ke zdrojům dat**  
  Toto nastavení zásad umožňuje spravovat, jestli Internet Explorer může získat přístup k datům z jiné zóny zabezpečení pomocí analyzátoru MSXML (Microsoft XML Parser) nebo rozhraní ADO (ActiveX Data Objects) (ADO). Pokud nastavení této zásady povolíte, uživatelé mohou načíst stránku v zóně, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud v rozevíracím seznamu vyberete příkaz Dotázat se na uživatele, zobrazí se dotaz, jestli chcete, aby se stránka načetla do zóny, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud nastavení této zásady zakážete, uživatelé nemůžou načíst stránku v zóně, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud nastavení této zásady nenakonfigurujete, uživatelé nebudou moci načíst stránku v zóně, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067161)  
  
  **Výchozí**: zakázat 
  
- **Internetová zóna Internet Exploreru nespouští Antimalwarový program proti ovládacím prvkům ActiveX**  
  Nastavení této zásady určuje, jestli aplikace Internet Explorer spouští antimalwarové programy proti ovládacím prvkům ActiveX, aby zkontrolovala, jestli se dají bezpečně načíst na stránkách. Pokud nastavení této zásady povolíte, aplikace Internet Explorer nebude u antimalwarového programu kontrolovat, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, bude aplikace Internet Explorer vždy kontrolovat váš Antimalwarový program, aby bylo možné zjistit, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, bude aplikace Internet Explorer vždy kontrolovat váš Antimalwarový program, aby bylo možné zjistit, zda je bezpečné vytvořit instanci ovládacího prvku ActiveX. Uživatelé můžou toto chování zapnout nebo vypnout pomocí nastavení zabezpečení Internet Exploreru.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067162)  
  
  **Výchozí**: zakázáno  
  
- **Kopírování a vkládání internetových zón Internet Exploreru prostřednictvím skriptu**  
  Toto nastavení zásad umožňuje spravovat, jestli můžou skripty provádět operace se schránkou (například vyjmutí, kopírování a vložení) v zadané oblasti. Pokud nastavení této zásady povolíte, skript může provést operaci se schránkou. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, zobrazí se uživatelům dotaz, zda chcete provést operace se schránkou. Pokud nastavení této zásady zakážete, skript nemůže provést operaci schránky. Pokud nastavení této zásady nenakonfigurujete, skript může provést operaci se schránkou.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067084)  
  
  **Výchozí**: zakázat  
  
- **Internet Explorer používat službu Active X Installer**  
  Nastavení této zásady umožňuje určit, jak jsou ovládací prvky ActiveX nainstalovány. Pokud nastavení této zásady povolíte, budou se ovládací prvky ActiveX instalovat jenom v případě, že je k dispozici instalační služba ActiveX a je nakonfigurovaná tak, aby umožňovala instalaci ovládacích prvků ActiveX. Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, budou ovládací prvky ActiveX, včetně ovládacích prvků pro jednotlivé uživatele, nainstalovány prostřednictvím standardního procesu instalace.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067163)
  
  **Výchozí**: povoleno  
  
- **Aplikace Internet Explorer zpracovává ochranu před zvýšením úrovně zóny**  
  Aplikace Internet Explorer umisťuje omezení na každou webovou stránku, kterou otevře. Tato omezení závisí na umístění webové stránky (Internet, intranet, zóna místní počítač atd.). Například webové stránky v místním počítači mají nejnižší bezpečnostní omezení a jsou v zóně místního počítače, takže zóna zabezpečení místního počítače má primární cíl pro uživatele se zlými úmysly. Pokud nastavení této zásady povolíte, může být jakákoli zóna chráněná před zvýšením úrovně pásma pro všechny procesy. Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, procesy jiné než Internet Explorer nebo, které jsou uvedeny v seznamu procesů, neobdrží takovou ochranu.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067160)  
  
  **Výchozí**: povoleno  
  
- **Internet Explorer Internet Zone stahuje nepodepsané ovládací prvky ActiveX**   
  Toto nastavení zásad umožňuje spravovat, jestli uživatelé můžou stahovat nepodepsané ovládací prvky ActiveX ze zóny. Takový kód je potenciálně škodlivý, zejména když přichází z nedůvěryhodné zóny. Pokud nastavení této zásady povolíte, můžou uživatelé spouštět nepodepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, zobrazí se uživatelům dotaz, zda chcete, aby bylo možné spustit nepodepsaný ovládací prvek. Pokud nastavení této zásady zakážete, uživatelé nemůžou spouštět nepodepsané ovládací prvky. Pokud nastavení této zásady nenakonfigurujete, uživatelé nemůžou spouštět nepodepsané ovládací prvky.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067325)
  
  **Výchozí**: zakázat  
  
- **Internet Explorer Internet Zone navigovat okna a rámce napříč různými doménami**   
  Toto nastavení zásad umožňuje spravovat otevírání oken a rámců a přístup k aplikacím v různých doménách. Pokud nastavení této zásady povolíte, můžou uživatelé otevřít Windows a snímky z jiných domén a přistupovat k aplikacím z jiných domén. Pokud v rozevíracím seznamu vyberete možnost zobrazit výzvu, uživatelům se zobrazí dotaz, zda mají okna a rámce umožňovat přístup k aplikacím z jiných domén. Pokud nastavení této zásady zakážete, uživatelé nemůžou otevřít Windows a snímky pro přístup k aplikacím z různých domén. Pokud nastavení této zásady nenakonfigurujete, můžou uživatelé otevřít Windows a snímky z jiných domén a přistupovat k aplikacím z jiných domén.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067083)  
  
  **Výchozí**: zakázat  
  
- **Aktualizace internetových zón Internet Exploreru na stavovém řádku prostřednictvím skriptu**  
  Toto nastavení zásad umožňuje spravovat, jestli skript může aktualizovat stavový řádek v rámci zóny. Pokud nastavení této zásady povolíte, můžou skripty aktualizovat stavový řádek. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, skript nebude moct aktualizovat stavový řádek.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067087)  
  
  **Výchozí**: zakázáno  
  
- **Zóna s omezeným přístupem v Internet Exploreru zahrnuje místní cestu při nahrávání souborů na server.**  
  Nastavení této zásady určuje, jestli se mají odesílat informace o místní cestě, když uživatel nahrává soubor prostřednictvím formuláře HTML. Pokud se odesílají informace o místní cestě, můžou být některé informace neúmyslně odhaleny serveru. Například soubory odeslané z plochy uživatele mohou obsahovat uživatelské jméno jako součást cesty. Pokud toto nastavení zásad povolíte, odesílají se informace o cestě, když uživatel nahraje soubor prostřednictvím formuláře HTML. Pokud toto nastavení zásad zakážete, informace o cestě se odeberou, když uživatel nahraje soubor prostřednictvím formuláře HTML. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, zda budou informace o cestě odesílány při nahrávání souboru prostřednictvím formuláře HTML. Ve výchozím nastavení jsou odesílány informace o cestě.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067085)  
  
  **Výchozí**: zakázáno  
  
- **Aplikace Internet Explorer zpracovává omezení stahování souborů**   
  Nastavení této zásady umožňuje aplikacím, které hostují ovládací prvek webového prohlížeče, blokovat automatické zobrazování výzev ke stažení souborů, které neinicioval uživatel. Pokud nastavení této zásady povolíte, bude ovládací prvek webového prohlížeče blokovat automatické zobrazování výzev ke stažení souborů, které neinicioval uživatel pro všechny procesy. Pokud toto nastavení zásad zakážete, nebude ovládací prvek webového prohlížeče blokovat automatické zobrazování výzev ke stažení souborů, které neinicioval uživatel pro všechny procesy.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067164)  
  
  **Výchozí**: povoleno  
  
- **Zóna s omezeným přístupem v aplikaci Internet Explorer povoluje používat pouze schválené domény s ovládacími prvky** ActiveX   
  Nastavení této zásady určuje, jestli se uživateli zobrazí výzva, aby se povolilo spouštění ovládacích prvků ActiveX na jiných webech, než na webu, který nainstaloval ovládací prvek ActiveX. Pokud nastavení této zásady povolíte, zobrazí se uživateli výzva před spuštěním ovládacích prvků ActiveX z webů v této zóně. Uživatel může zvolit, že se má ovládací prvek spouštět z aktuálního webu nebo ze všech lokalit. Pokud nastavení této zásady zakážete, uživatel nebude zobrazovat výzvu ActiveX pro jednotlivé lokality a ovládací prvky ActiveX lze spouštět ze všech lokalit v této zóně.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067233)  
  
  **Výchozí**: povoleno  
  
- **Inicializovat zónu s omezeným přístupem a skripty Active X v aplikaci Internet Explorer nejsou označeny jako bezpečné**  
  Toto nastavení zásad umožňuje spravovat ovládací prvky ActiveX, které nejsou označeny jako bezpečné. Pokud nastavení této zásady povolíte, budou ovládací prvky ActiveX spouštěny, načteny s parametry a pomocí skriptů bez nastavení bezpečnosti objektů pro nedůvěryhodná data nebo skripty. Toto nastavení se nedoporučuje, s výjimkou zabezpečených a spravovaných zón. Toto nastavení způsobí, že budou inicializovány nebezpečné i bezpečné ovládací prvky a budou skriptované, ignorování ovládacích prvků ActiveX skriptu označených jako bezpečné pro možnost skriptování. Pokud nastavení této zásady povolíte a v rozevíracím seznamu vyberete možnost zobrazit výzvu, uživatelé se dotazují, jestli chcete ovládacímu prvku povolit načtení pomocí parametrů nebo skriptu. Pokud nastavení této zásady zakážete, nebudou se ovládací prvky ActiveX, které se dají bezpečně nastavit, načítat pomocí parametrů nebo skriptu. Pokud nastavení této zásady nenakonfigurujete, nebudou se ovládací prvky ActiveX, které se dají bezpečně nastavit, načítat pomocí parametrů nebo skriptu.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067097)  
  
  **Výchozí**: zakázat  
  
- **Uživatelé aplikace Internet Explorer měnící zásady**  
  Zabrání uživatelům měnit nastavení zón zabezpečení. Zóna zabezpečení je skupina webů se stejnou úrovní zabezpečení. Pokud tuto zásadu povolíte, na kartě zabezpečení v dialogovém okně Možnosti Internetu jsou zakázaná tlačítka vlastní úroveň a posuvník úrovně zabezpečení. Pokud tuto zásadu zakážete nebo nenakonfigurujete, můžou uživatelé změnit nastavení zón zabezpečení. Tato zásada zabraňuje uživatelům měnit nastavení zón zabezpečení vytvořená správcem. Poznámka: zásada "Zakázat stránku zabezpečení" (nacházející se v Ovládacích panelech \ Šablony pro správu \ součásti systému Windows\internet Explorer\Internet), která odebere kartu zabezpečení z Internet Exploreru v Ovládacích panelech, má přednost nad touto zásadou. Pokud je tato zásada povolená, ignoruje se. Podívejte se také na zásady zóny zabezpečení: použít jenom nastavení počítače.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067155)  
    
  **Výchozí**: zakázáno  
  
- **Chráněný režim chráněné zóny Internet Exploreru**  
  Toto nastavení zásad umožňuje zapnout chráněný režim. Chráněný režim pomáhá chránit Internet Explorer před zneužitím ohrožení zabezpečení tím, že snižuje umístění, do kterých aplikace Internet Explorer může zapisovat do registru a systému souborů. Pokud nastavení této zásady povolíte, je chráněný režim zapnutý. Uživatel nemůže vypnout chráněný režim. Pokud nastavení této zásady zakážete, je chráněný režim vypnutý. Uživatel nemůže zapnout chráněný režim. Pokud nastavení této zásady nenakonfigurujete, může uživatel zapnout nebo vypnout chráněný režim.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067080)  
  
  **Výchozí**: Povolit  
  
- **Trvalost uživatelských dat pro internetovou zónu Internet Exploreru**  
  Toto nastavení zásad umožňuje spravovat uchovávání informací v historii prohlížeče, v oblíbených položkách v úložišti XML nebo přímo na webové stránce uložené na disku. Když se uživatel vrátí na trvalou stránku, může se stát, že se stav stránky obnoví, pokud je toto nastavení zásad vhodně nakonfigurované. Pokud nastavení této zásady povolíte, mohou uživatelé uchovávat informace v historii prohlížeče, v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uložené na disk. Pokud nastavení této zásady zakážete, uživatelé nebudou moci uchovávat informace v historii prohlížeče, v oblíbených položkách v úložišti XML nebo přímo na webové stránce uložené na disku. Pokud nastavení této zásady nenakonfigurujete, mohou uživatelé uchovávat informace v historii prohlížeče, v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uložené na disk.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067156)  
  
  **Výchozí**: zakázáno  
  
- **Internet Explorer Internet Zone skriptování ovládacích prvků webového prohlížeče**  
 
  Nastavení této zásady určuje, zda může stránka řídit vložené ovládací prvky WebBrowser prostřednictvím skriptu. Pokud nastavení této zásady povolíte, je povolený přístup ke skriptu ovládacího prvku WebBrowser. Pokud nastavení této zásady zakážete, nebude přístup k skriptu k ovládacímu prvku WebBrowser povolen. Pokud nastavení této zásady nenakonfigurujete, uživatel může povolit nebo zakázat přístup k skriptu ovládacímu prvku WebBrowser. Ve výchozím nastavení je přístup ke skriptu k ovládacímu prvku WebBrowser povolen pouze v zónách místní počítač a intranet.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067157)  
  
  **Výchozí**: zakázáno  
  
- **Trvalost uživatelských dat zóny s omezeným přístupem aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat uchovávání informací v historii prohlížeče, v oblíbených položkách v úložišti XML nebo přímo na webové stránce uložené na disku. Když se uživatel vrátí na trvalou stránku, může se stát, že se stav stránky obnoví, pokud je toto nastavení zásad vhodně nakonfigurované. Pokud nastavení této zásady povolíte, mohou uživatelé uchovávat informace v historii prohlížeče, v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uložené na disk. Pokud nastavení této zásady zakážete, uživatelé nebudou moci uchovávat informace v historii prohlížeče, v oblíbených položkách v úložišti XML nebo přímo na webové stránce uložené na disku. Pokud nastavení této zásady nenakonfigurujete, uživatelé nebudou moci zachovat informace v historii prohlížeče, v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uložené na disk.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067081)  
  
  **Výchozí**: zakázáno  
  
- **Aplikace Internet Explorer byla uzamčena v intranetové zóně oprávnění Java**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety v jazyce Java. Pokud nastavení této zásady povolíte, můžete v rozevíracím seznamu zvolit možnosti. Vlastní pro řízení nastavení oprávnění individuálně. Nízké zabezpečení umožňuje apletům provádět všechny operace. Střední zabezpečení umožňuje apletům běžet v izolovaném prostoru (sandboxu) (oblast v paměti mimo rámec toho, že program nemůže provádět volání) a navíc funkce, jako je například pomocné místo (bezpečná a zabezpečená oblast úložiště v klientském počítači) a uživatelem řízený vstup/výstup souborů. Vysoké zabezpečení umožňuje, aby se applety spouštěly v izolovaném prostoru. Zakáže Java, aby se zabránilo spuštění všech apletů. Pokud nastavení této zásady zakážete, aplety Java nepůjde spustit. Pokud nastavení této zásady nenakonfigurujete, aplety Java budou zakázané.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067082)  
  
  **Výchozí**: zakázat Java  
  
- **Rozšířený chráněný režim aplikace Internet Explorer**  
  Rozšířený chráněný režim poskytuje dodatečnou ochranu před škodlivými weby pomocí 64 procesů na 64 verzích systému Windows. V počítačích s minimálně Windows 8 se v rozšířeném chráněném režimu taky omezují umístění, ze kterých může Internet Explorer číst v registru a v systému souborů. Pokud nastavení této zásady povolíte, je zapnutý režim Enhanced Protected. Všechny zóny, které mají povolený chráněný režim, budou používat Rozšířený chráněný režim. Uživatelé nebudou moct zakázat Rozšířený chráněný režim. Pokud nastavení této zásady zakážete, je vypnutý Rozšířený chráněný režim. Všechny zóny s povoleným chráněným režimem budou používat verzi chráněného režimu představenou v aplikaci Internet Explorer 7 pro systém Windows Vista. Pokud tuto zásadu nenakonfigurujete, uživatelé můžou zapnout nebo vypnout Rozšířený chráněný režim na kartě Upřesnit dialogového okna Možnosti Internetu.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067158)  
  
  **Výchozí**: povoleno  
  
- **Upozornění na inteligentní obrazovku nepoužívat Internet Explorer**  
  Nastavení této zásady určuje, jestli uživatel může obejít upozornění z filtru SmartScreen. Filtr SmartScreen uživatele upozorní na spustitelné soubory, které uživatelé Internet Exploreru nestahují běžným z Internetu. Pokud toto nastavení zásad povolíte, upozornění filtru SmartScreen blokují uživatele. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, může uživatel obejít upozornění filtru SmartScreen.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067159)  
  
  **Výchozí**: zakázáno  
  
- **Meta aktualizace zóny s omezeným přístupem v aplikaci Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat, jestli je možné prohlížeč uživatele přesměrovat na jinou webovou stránku, pokud autor webové stránky používá nastavení Meta Refresh (tag) k přesměrování prohlížečů na jinou webovou stránku. Pokud nastavení této zásady povolíte, bude prohlížeč uživatele, který načte stránku obsahující aktivní nastavení Meta Refresh, přesměrovat na jinou webovou stránku. Pokud nastavení této zásady zakážete, nebude možné přesměrovat prohlížeč uživatele, který načte stránku obsahující aktivní nastavení Meta Refresh, na jinou webovou stránku. Pokud nastavení této zásady nenakonfigurujete, nebude možné přesměrovat prohlížeč uživatele, který načte stránku obsahující aktivní nastavení Meta Refresh, na jinou webovou stránku.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067154)  
  
  **Výchozí**: zakázáno  
  
## <a name="local-policies-security-options"></a>Možnosti zabezpečení místních zásad
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) . 

- **Omezit anonymní přístup k pojmenovaným kanálům a sdíleným složkám**  
  Když je toto nastavení zabezpečení povolené, omezí anonymní přístup ke sdíleným složkám a kanálům na nastavení pro: (1) pojmenované kanály, ke kterým se dá přistupovat anonymně (2) ke sdíleným složkám, ke kterým se dá přistupovat anonymně.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067212)  
  
  **Výchozí**: Ano  
  
- **Minimální zabezpečení relace pro servery založené na NTLM SSP**  
  Toto nastavení zabezpečení umožňuje serveru vyžadovat vyjednávání 128ho šifrování nebo zabezpečení relace NTLMv2. Tyto hodnoty jsou závislé na hodnotě nastavení zabezpečení na úrovni ověřování v programu LAN Manager. Možnosti: vyžadovat zabezpečení relace NTLMv2: připojení selže, pokud není vyjednána integrita zprávy. Vyžadovat 128 bitů šifrování. Pokud není vyjednáno silné šifrování (128 bitů), připojení se nezdaří.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067246) 
  
  **Výchozí**: vyžadování protokolu NTLM V2 a 128 bitového šifrování  
  
- **Počet minut nečinnosti uzamčené obrazovky, než se aktivuje spořič obrazovky**  
  Systém Windows zaznamená nečinnost relace přihlášení, a pokud neaktivní doba překračuje limit nečinnosti, pak se spustí šetřič obrazovky, který relaci uzamkne.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067210)  
  
  **Výchozí**: 15
  
- **Vyžadovat od klienta vždycky digitálně podepsat komunikaci** Toto nastavení zabezpečení určuje, zda musí být veškerý provoz zabezpečeného kanálu iniciované členem domény podepsán nebo zašifrován. Když se počítač připojí k doméně, vytvoří se účet počítače. Po tom, co se systém spustí, se pomocí hesla účtu počítače vytvoří zabezpečený kanál s řadičem domény pro svoji doménu. Tento zabezpečený kanál se používá k provádění operací, jako je ověřování pomocí protokolu NTLM Pass over, identifikátor SID/název LSA a další. Toto nastavení určuje, zda veškerý provoz zabezpečeného kanálu iniciované členem domény splňuje minimální požadavky na zabezpečení. Konkrétně určuje, zda je nutné všechny přenosy zabezpečeného kanálu spuštěné členem domény podepsat nebo zašifrovat. Pokud je tato zásada povolená, zabezpečený kanál se nevytvoří, pokud se nepoužije podepisování nebo šifrování veškerého provozu zabezpečeného kanálu. Pokud je tato zásada zakázaná, pak se šifrování a podepisování veškerého provozu zabezpečeného kanálu vyjednávají s řadičem domény. v takovém případě závisí úroveň podepisování a šifrování na verzi řadiče domény a nastavení následujících dvou zásady: člen domény: digitálně zašifrovat data zabezpečeného kanálu (Pokud je to možné) člen domény: digitálně podepsat data zabezpečeného kanálu (Pokud je to možné).  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067187) 
  
  **Výchozí**: Ano
  
- **Úroveň ověřování**  
  Toto nastavení zabezpečení určuje, který ověřovací protokol pro ověření výzvou a odpovědí se používá pro přihlášení k síti. Tato volba ovlivňuje úroveň protokolu ověřování používaného klienty, úroveň vyjednané zabezpečení relace a úroveň ověřování, kterou tyto servery akceptují:  
  - *Posílání odpovědí LM a NTLM* – klienti používají ověřování LM a NTLM a nikdy nepoužívají zabezpečení relace NTLMv2; řadiče domény přijímají ověřování LM, NTLM a NTLM. 
  - *Odeslat LM a NTLM-NTLMv2, pokud jsou vyjednáno* – klienti používají ověřování LM a NTLM a používají zabezpečení relace NTLMv2, pokud je server podporuje; řadiče domény přijímají ověřování LM, NTLM a NTLM. 
  - *Poslat jenom odpovědi NTLM* – klienti používají jenom ověřování NTLM a používají zabezpečení relace NTLMv2, pokud je server podporuje. řadiče domény přijímají ověřování LM, NTLM a NTLM. 
  - *Poslat jenom odpovědi NTLMv2* – klienti používají jenom ověřování NTLMv2 a v případě, že ho Server podporuje, používá zabezpečení relace NTLMv2. řadiče domény přijímají ověřování LM, NTLM a NTLM. 
  - *Poslat jenom odpověď NTLMv2 Odmítat LM* – klienti používají pouze ověřování NTLMv2 a používají zabezpečení relace NTLMv2, pokud je server podporuje. řadiče domény odmítnou LM (přijímá pouze ověřování NTLM a NTLM). 
  - *Poslat jenom odpověď NTLMv2 Odmítat LM a NTLM* – klienti používají jenom ověřování NTLMv2 a v případě, že ho Server podporuje, použijte zabezpečení relace NTLMv2. řadiče domény odmítnou LM a NTLM (přijímají pouze ověřování NTLMv2).  

  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067189)   
    
  **Výchozí**: odeslat pouze odpověď NTLMv2. Odmítat LM a NTLM
  
- **Zabránit klientům v posílání nezašifrovaných hesel serverům SMB třetích stran**  
  Pokud je toto nastavení zabezpečení povolené, přesměrovači protokolu SMB (Server Message Block) může posílat hesla ve formátu prostého textu na servery SMB jiných společností než Microsoft, které při ověřování nepodporují šifrování hesla. Posílání nezašifrovaných hesel je bezpečnostní riziko.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067235)  
  
  **Výchozí**: Ano
  
- **Vyžadovat komunikaci s digitálním podpisem serveru vždycky**  
  Toto nastavení zabezpečení určuje, jestli se klient SMB pokusí vyjednat podepisování paketů SMB. Protokol SMB (Server Message Block) poskytuje základ pro sdílení souborů a tiskáren společnosti Microsoft a mnoho dalších síťových operací, například vzdálenou správu systému Windows. Aby nedocházelo k útokům prostředníkem, které mění pakety SMB při přenosu, podporuje protokol SMB digitální podepisování paketů SMB. Nastavení této zásady určuje, jestli se součást klienta protokolu SMB pokusí vyjednat podepisování paketů SMB při připojení k serveru SMB. Pokud je toto nastavení povolené, bude klient sítě Microsoftu požádat server, aby při nastavení relace prováděl podepisování paketů SMB. Pokud je na serveru podepisování paketů povolené, podepisování paketů se vyjedná. Pokud je tato zásada zakázaná, klient SMB nebude nikdy vyjednávat podepisování paketů SMB.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067319)  
  
  **Výchozí**: Ano
  
- **Chování výzvy ke zvýšení úrovně oprávnění správce**  
  Toto nastavení zásady řídí chování výzvy ke zvýšení oprávnění pro správce. Možnosti: 
  - *Zvýšení oprávnění bez výzvy* – umožňuje privilegovaným účtům provést operaci, která vyžaduje zvýšení oprávnění bez vyžadování souhlasu nebo přihlašovacích údajů. Poznámka: tuto možnost použijte jenom v nejvíc omezených prostředích. 
  - *Vyzvat k zadání přihlašovacích údajů na zabezpečené ploše* – Pokud operace vyžaduje zvýšení oprávnění, zobrazí se uživateli výzva k zadání privilegovaného uživatelského jména a hesla na zabezpečené ploše. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s největším dostupným oprávněním uživatele. 
  - *Vyzvat k vyjádření souhlasu na zabezpečené ploše* – Pokud operace vyžaduje zvýšení oprávnění, zobrazí se uživateli výzva na zabezpečené ploše, aby bylo možné vybrat možnost povolit nebo odepřít. Pokud uživatel vybere povolit, operace pokračuje s největším dostupným oprávněním uživatele. 
  - *Vyzvat k zadání přihlašovacích údajů* – Pokud operace vyžaduje zvýšení oprávnění, zobrazí se uživateli výzva k zadání uživatelského jména a hesla pro správu. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s příslušným oprávněním. 
  - *Vyzvat k vyjádření souhlasu* – Pokud operace vyžaduje zvýšení oprávnění, zobrazí se uživateli výzva k výběru možnost povolit nebo odepřít. Pokud uživatel vybere povolit, operace pokračuje s největším dostupným oprávněním uživatele.  
  - *Vyzvat k vyjádření souhlasu s binárními soubory, které nejsou v systému Windows* – Pokud operace pro aplikaci od jiného výrobce než od Microsoftu vyžaduje zvýšení oprávnění, zobrazí se uživateli výzva k výběru možnost povolit nebo zamítnout. Pokud uživatel vybere povolit, operace pokračuje s největším dostupným oprávněním uživatele. 
  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067215)   
  
  **Výchozí**: vyzvat k vyjádření souhlasu na zabezpečené ploše
  
- **Minimální zabezpečení relace pro klienty založené na NTLM SSP**  
  Toto nastavení zabezpečení umožňuje klientovi vyžadovat vyjednávání 128ho šifrování nebo zabezpečení relace NTLMv2. Tyto hodnoty jsou závislé na hodnotě nastavení zabezpečení na úrovni ověřování v programu LAN Manager. Možnosti:
  - *Vyžadovat zabezpečení relace NTLMv2* – Pokud není protokol NTLMv2 vyjednávat, připojení se nezdaří. 
  - *Vyžadovat 128 bitů* – připojení selže, pokud se vyjednává silné šifrování (128 bitů).
  - *Vyžadovat šifrování NTLMv2 a 128 bitů*.  

  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067324)  

  **Výchozí**: vyžadovat šifrování NTLM v2 128
  
- **Chování při odebrání čipové karty**  
  Toto nastavení zabezpečení určuje, co se stane, když se čipová karta přihlášeného uživatele odebere z čtecího zařízení s čipovou kartou. Možnosti:
  - *Žádná akce*. 
  - *Zamknout pracovní stanici* – pracovní stanice je při odebrání čipové karty uzamčená a umožňuje uživatelům opustit oblast, přebírat jejich čipové karty a zachovat chráněnou relaci.
  - *Vynutit odhlášení* – při odebrání čipové karty se uživatel automaticky odhlásí.
  - *Odpojit relaci vzdálené plochy* – odebrání čipové karty odpojí relaci bez odhlášení uživatele. To umožňuje uživateli vložit čipovou kartu a později pokračovat v relaci nebo na jiném počítači vybaveném čtečkou čipových karet, aniž by se museli znovu přihlašovat. Pokud je relace místní, funguje tato zásada stejně jako možnost Zamknout pracovní stanici.
  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067331) 
    
  **Výchozí**: zamknout pracovní stanici
  
- **Blokuje anonymní výčet účtů SAM a sdílených složek.**  
  Toto nastavení zabezpečení určuje, zda má být povoleno anonymní výčet účtů SAM a sdílených složek. Systém Windows umožňuje anonymním uživatelům provádět určité aktivity, jako je například vytváření výčtu názvů doménových účtů a síťových sdílených složek. To je užitečné, například když chce správce udělit přístup uživatelům v důvěryhodné doméně, které neudržují vzájemnou důvěryhodnost. Pokud nechcete povolit anonymní výčet účtů SAM a sdílených složek, nastavte tuto zásadu na *Ano*.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067191)  
  
  **Výchozí**: Ano
  
- **Blokovat vzdálené přihlášení s prázdným heslem**  
  Toto nastavení zabezpečení určuje, zda lze místní účty, které nejsou chráněny heslem, použít k přihlášení z jiných umístění, než je konzola fyzického počítače. Pokud je povoleno, přihlaste se k místnímu účtu, který není chráněn heslem, pomocí klávesnice počítače. 

  *Upozornění*: počítače, které nejsou v fyzicky zabezpečených umístěních, by měly vždy vyhovět silným zásadám hesel pro všechny místní uživatelské účty. V opačném případě může kdokoli s fyzickým přístupem k počítači přihlásit pomocí uživatelského účtu, který nemá heslo. To je zvlášť důležité u přenosných počítačů. 

  Pokud použijete tuto zásadu zabezpečení pro skupinu Everyone, nikdo se nemůže přihlásit přes službu Vzdálená plocha. Toto nastavení nemá vliv na přihlášení, která používají účty domény. Pro aplikace, které používají vzdálené interaktivní přihlášení, je možné toto nastavení obejít.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067219)  
  
  **Výchozí**: Ano
  
- **Standardní chování výzvy ke zvýšení úrovně uživatele**  
  Toto nastavení zásady řídí chování výzvy ke zvýšení oprávnění pro standardní uživatele. 
  - *Automaticky odepřít žádosti o zvýšení oprávnění* – Pokud operace vyžaduje zvýšení oprávnění, zobrazí se chybová zpráva konfigurovatelný přístup byl odepřen. Podnik, na kterém běží stolní počítače jako standardní uživatel, může zvolit toto nastavení, aby se snížila volání helpdesku. 
  - *Vyzvat k zadání přihlašovacích údajů na zabezpečené ploše* – Pokud operace vyžaduje zvýšení oprávnění, zobrazí se uživateli výzva k zadání jiného uživatelského jména a hesla na zabezpečené ploše. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s příslušným oprávněním. 
  - *Vyzvat k zadání přihlašovacích údajů* – Pokud operace vyžaduje zvýšení oprávnění, zobrazí se uživateli výzva k zadání uživatelského jména a hesla pro správu. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s příslušným oprávněním.  

  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067183)  
  
  **Výchozí**: automaticky zamítnout žádosti o zvýšení oprávnění
  
- **Vyžadovat režim schválení správce pro správce**  
  Toto nastavení zásady řídí chování všech nastavení zásad řízení uživatelských účtů (UAC) v počítači. Pokud toto nastavení zásad změníte, musíte restartovat počítač. Možnosti:   
  - *Nenakonfigurováno* – režim schválení správce a všechna související nastavení zásad nástroje řízení uživatelských účtů jsou zakázaná. Poznámka: Pokud je toto nastavení zásad zakázané, Security Center vás upozorní, že celkové zabezpečení operačního systému bylo omezené. 
  - *Ano* – režim schválení správcem je povolen. Tato zásada musí být povolená a související nastavení zásad řízení uživatelských účtů musí být nastavené tak, aby umožňovala předdefinovaný účet správce a všechny ostatní uživatele, kteří jsou členy skupiny Administrators, ke spuštění v režimu schválení správcem.  

  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067184)  
  
  **Výchozí**: Ano
  
- **Zabránit anonymnímu výčtu účtů SAM**  
  Toto nastavení zabezpečení určuje, jaká další oprávnění budou udělena anonymním připojením k počítači. Systém Windows umožňuje anonymním uživatelům provádět určité aktivity, jako je například vytváření výčtu názvů doménových účtů a síťových sdílených složek. To je užitečné, například když chce správce udělit přístup uživatelům v důvěryhodné doméně, které neudržují vzájemnou důvěryhodnost. Tato možnost zabezpečení umožňuje umístit do anonymních připojení další omezení následujícím způsobem: 
  - *Ano* – Nepovolit výčet účtů SAM. Tato možnost nahrazuje všechny ověřené uživatele v oprávnění zabezpečení pro prostředky.
  - *Nenakonfigurováno* – žádná další omezení. Spoléhá se na výchozí oprávnění.  
  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067318)  

  **Výchozí**: Ano
  
- **Povolení vzdálených volání do správce účtů zabezpečení**  
  Toto nastavení zásad umožňuje omezit vzdálená připojení RPC k SAM. Pokud není vybraná, použije se výchozí popisovač zabezpečení.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067209)  
  
  **Výchozí**: *O:Bag: Bad: (A;; RC;;; BA)*

- **Použít režim schválení správce**  
  Toto nastavení zásady řídí chování režimu schválení správcem pro předdefinovaný účet správce. Možnosti: 
  - *Ano* – integrovaný účet správce používá režim schválení správcem. Ve výchozím nastavení vyzve uživatel ke schválení operace všechny operace, které vyžadují zvýšení oprávnění. 
  - *Nenakonfigurováno* – integrovaný účet správce spouští všechny aplikace s úplnými oprávněními správce. 

  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067186)  

  **Výchozí**: Ano
  
- **Povolení přístupu aplikací uživatelského rozhraní k zabezpečeným umístěním**  
  Nastavení této zásady určuje, jestli programy pro usnadnění přístupu k uživatelskému rozhraní (UIAccess nebo UIA) můžou automaticky zakázat zabezpečenou plochu pro výzvy ke zvýšení oprávnění používané standardním uživatelem. 
  - *Ano* – UIA programy, včetně vzdálené pomoci Windows, automaticky zakažte zabezpečenou plochu pro výzvy ke zvýšení oprávnění. Pokud nezakážete řízení uživatelských účtů: při zobrazení výzvy ke zvýšení oprávnění přepnout na zabezpečenou plochu, zobrazí se výzva na ploše interaktivního uživatele místo na zabezpečené ploše. 
  - *Nenakonfigurováno*: zabezpečená plocha může být zakázaná jenom uživatelem interaktivní plochy nebo zakázáním možnosti řízení uživatelských účtů: při zobrazení výzvy ke zvýšení oprávnění přepnout na zabezpečenou plochu.  

  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067185)  

  **Výchozí**: Ano

- **Zjištění instalace aplikace a výzva ke zvýšení oprávnění**  
  Toto nastavení zásady řídí chování detekce instalace aplikace pro daný počítač. Možnosti: 
  - *Povoleno* – při zjištění instalačního balíčku aplikace, který vyžaduje zvýšení oprávnění, se uživateli zobrazí výzva k zadání uživatelského jména a hesla pro správu. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s příslušným oprávněním. 
  - *Zakázané* – instalační balíčky aplikací se nerozpoznají a zobrazí se výzva ke zvýšení oprávnění. U podniků, ve kterých běží standardní stolní počítače a využívají technologie delegované instalace, například Zásady skupiny pro instalaci softwaru nebo Systems Management Server (SMS), by měli toto nastavení zásad zakázat. V takovém případě je zjišťování instalační služby zbytečné.  
  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067208)  

  **Výchozí**: Ano
  
- **Zabránit ukládání hodnoty hash systému LAN Manager při příští změně hesla**  
  Toto nastavení zabezpečení určuje, jestli se při další změně hesla uloží hodnota hash LAN Manageru (LM) pro nové heslo. Hodnota hash LM je poměrně slabá a náchylná k útokům v porovnání s kryptograficky silnější hodnotou hash systému Windows NT. Vzhledem k tomu, že je hodnota hash LM uložená v místním počítači v databázi zabezpečení, můžou se hesla napadnout, pokud je databáze zabezpečení napadená.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067213)  
  
  **Výchozí**: Ano

- **Virtualizovat selhání zápisu souborů a registru do umístění jednotlivých uživatelů**  
  Nastavení této zásady určuje, zda jsou chyby zápisu aplikace přesměrovány do definovaného registru a umístění systému souborů. Nastavení této zásady snižuje riziko aplikací spouštěných jako správce a zápis dat aplikace za běhu do *% ProgramFiles%* , *% windir%* , *%windir%\System32*nebo *HKLM\Software*.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067321)  
  
  **Výchozí**: Ano

## <a name="ms-security-guide"></a>Průvodce zabezpečením MS  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) .  

- **Použití omezení nástroje řízení uživatelských účtů u místních účtů při přihlášení k síti**  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067188)  

  **Výchozí**: povoleno
  
- **Konfigurace spuštění ovladače klienta protokolu SMB v1**  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067214) 
 
  **Výchozí**: zakázaný ovladač
  
- **Server SMB v1**  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067190)  

  **Výchozí**: zakázáno
  
- **Ověřování hodnotou hash**  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067193) 
 
  **Výchozí**: zakázáno
  
- **Ochrana před přepsáním strukturovaného zpracování výjimek**  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067217)  

  **Výchozí**: povoleno
  
## <a name="mss-legacy"></a>MSS – starší  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) .  

- **Úroveň ochrany směrování zdroje IP adresy sítě**  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067220)  
  
  **Výchozí**: nejvyšší ochrana  
  
- **Síť ignoruje žádosti o vydání názvů NetBIOS s výjimkou serverů WINS**  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067218)  
 
  **Výchozí**: povoleno
  
- **Úroveň ochrany směrování zdroje síťového protokolu IPv6**  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067216)  

  **Výchozí**: nejvyšší ochrana

- **Přesměrování sítě protokolu ICMP přesměruje vygenerované protokolem OSPF**  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067326)  

  **Výchozí**: zakázáno
  
## <a name="power"></a>Napájení  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – napájení](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) .  

- **Vyžadovat heslo při probuzení při napájení ze sítě**  
  Nastavení této zásady určuje, jestli se uživateli zobrazí výzva k zadání hesla, když se systém obnoví z režimu spánku. Pokud nastavení této zásady povolíte nebo nenakonfigurujete, bude uživatel vyzván k zadání hesla, když se systém obnoví z režimu spánku. Pokud nastavení této zásady zakážete, uživatel nebude vyzván k zadání hesla, když se systém obnoví z režimu spánku.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067221)  
  
  **Výchozí**: povoleno
  
- **Pohotovostní stav při přechodu do režimu spánku při napájení z baterie**  
  Toto nastavení zásad spravuje, jestli systém Windows může použít pohotovostní stav při uvedení počítače do režimu spánku. Pokud nastavení této zásady povolíte nebo nenakonfigurujete, systém Windows použije pohotovostní stav k uvedení počítače do režimu spánku. Pokud toto nastavení zásad zakážete, nepovolí se pohotovostní stav (S1 – S3).  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067195)  
  
  **Výchozí**: zakázáno
  
- **Pohotovostní stav při přechodu do režimu spánku během napájení**  
  Toto nastavení zásad spravuje, jestli systém Windows může použít pohotovostní stav při uvedení počítače do režimu spánku. Pokud nastavení této zásady povolíte nebo nenakonfigurujete, systém Windows použije pohotovostní stav k uvedení počítače do režimu spánku. Pokud toto nastavení zásad zakážete, nepovolí se pohotovostní stav (S1 – S3).  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067196)  
  
  **Výchozí**: zakázáno
  
- **Vyžadovat heslo při probuzení při napájení z baterie**  
  Nastavení této zásady určuje, jestli se uživateli zobrazí výzva k zadání hesla, když se systém obnoví z režimu spánku. Pokud nastavení této zásady povolíte nebo nenakonfigurujete, bude uživatel vyzván k zadání hesla, když se systém obnoví z režimu spánku. Pokud nastavení této zásady zakážete, uživatel nebude vyzván k zadání hesla, když se systém obnoví z režimu spánku.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067322)  
  
  **Výchozí**: povoleno

## <a name="remote-assistance"></a>Vzdálená pomoc
- **Vyžádané vzdálené pomoci**  
  Toto nastavení zásad umožňuje zapnout nebo vypnout funkci vyžádaná (požádat o) o vzdálenou pomoc na tomto počítači. 
  - *Pokud nastavení této zásady povolíte*, mohou uživatelé v tomto počítači použít e-mail nebo přenos souborů a požádat někoho o pomoc. Uživatelé můžou taky používat programy pro rychlé zasílání zpráv k povolení připojení k tomuto počítači a můžete nakonfigurovat další nastavení vzdálené pomoci. 
  - *Pokud nastavení této zásady zakážete*, uživatelé v tomto počítači nebudou moct pomocí e-mailu nebo přenosu souborů požádat někoho o pomoc. Uživatelé navíc nemohou použít programy pro rychlé zasílání zpráv k povolení připojení k tomuto počítači. 
  - *Pokud nastavení této zásady*nenakonfigurujete, uživatelé můžou v Ovládacích panelech zapnout nebo vypnout funkci vyžádaná (požádat o) pro vzdálenou pomoc na ovládacím panelu Vlastnosti systému. Uživatelé můžou taky nakonfigurovat nastavení vzdálené pomoci. 

  Pokud toto nastavení zásad povolíte, budete mít dva způsoby, jak pomocníkům umožnit poskytování vzdálené pomoci: "Povolit pomocníkům pouze zobrazit počítač" nebo "Povolit pomoc při vzdáleném řízení počítače." Nastavení "maximální doba lístku" Nastavuje omezení pro dobu, po kterou může být otevřené pozvání vzdálené pomoci vytvořené pomocí e-mailu nebo přenosu souborů. Nastavení vyberte metodu pro odesílání e-mailových pozvánek určuje, která e-mailová norma se má použít k odeslání pozvání vzdálené pomoci. V závislosti na e-mailovém programu můžete použít buď Standard mailto (příjemce pozvánky prostřednictvím připojení k Internetu), nebo rozhraní SMAPI (Simple MAPI) Standard (Pozvánka je připojená k vaší e-mailové zprávě). Nastavení této zásady není k dispozici v systému Windows Vista, protože rozhraní SMAPI je jedinou podporovanou metodou. Pokud nastavení této zásady povolíte, měli byste taky povolit příslušné výjimky brány firewall, aby bylo možné povolit komunikaci vzdálené pomoci.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067198)

  **Výchozí**: zakázat vzdálenou pomoc

  Pokud je nastavená možnost *Povolit vzdálenou pomoc*, nakonfigurujte následující další nastavení:  
  - **Žádosti o vzdálenou pomoc – vyžádaná oprávnění**  
    **Výchozí**: zobrazení  

  - **Maximální hodnota času lístku**  
    **Výchozí**: *Nenakonfigurováno*  

  - **Maximální časové období lístku**  
    **Výchozí**: minuty    

  - **Metoda pozvánky e-mailu**  
    **Výchozí**: jednoduché rozhraní MAPI

  
## <a name="remote-desktop-services"></a>Vzdálená plocha  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) .  

- **Blokovat ukládání hesla**  
  Určuje, jestli je možné ukládat hesla na tomto počítači z Připojení ke vzdálené ploše. Pokud povolíte toto nastavení, zaškrtávací políčko pro uložení hesla v Připojení ke vzdálené ploše je zakázané a uživatelé nebudou moct ukládat hesla. Když uživatel otevře soubor RDP pomocí Připojení ke vzdálené ploše a uloží jeho nastavení, odstraní se všechna hesla, která dříve existovala v souboru RDP. Pokud toto nastavení zakážete nebo necháte není nakonfigurované, může uživatel ukládat hesla pomocí Připojení ke vzdálené ploše.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067301)  
  
   **Výchozí**: povoleno
  
- **Zabezpečená komunikace RPC**  
  Určuje, jestli Hostitel relace vzdálené plochy Server vyžaduje zabezpečenou komunikaci RPC se všemi klienty, nebo umožňuje nezabezpečenou komunikaci. Pomocí tohoto nastavení můžete posílit zabezpečení komunikace RPC s klienty tím, že povolíte jenom ověřené a šifrované požadavky. Pokud je stav nastaven na povoleno, služba Vzdálená plocha přijímá žádosti od klientů RPC, které podporují zabezpečené požadavky, a nepovoluje nezabezpečenou komunikaci s nedůvěryhodnými klienty. Pokud je stav nastaven na zakázáno, služba Vzdálená plocha vždy vyžádá zabezpečení pro všechny přenosy RPC. Pro klienty RPC, kteří na žádost nereagují, se ale povoluje nezabezpečená komunikace. Pokud je stav nastavený na Nenakonfigurováno, je povolená nezabezpečená komunikace. Poznámka: rozhraní RPC se používá pro správu a konfiguraci služby Vzdálená plocha.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067248)  
  
  **Výchozí**: povoleno
  
- **Blokovat přesměrování jednotky**  
  Nastavení této zásady určuje, jestli se má zabránit mapování klientských jednotek v relaci vzdálené plochy (přesměrování jednotky). Ve výchozím nastavení server Hostitel relace VP mapuje jednotky klienta automaticky po připojení. Mapované jednotky se zobrazí ve stromu složky relace v Průzkumníkovi souborů nebo v počítači ve formátu *\<písmeno_jednotky >* v *\<ComputerName >* . Toto chování můžete přepsat pomocí tohoto nastavení zásad. Pokud toto nastavení zásad povolíte, přesměrování jednotky klienta není v relacích služby Vzdálená plocha povoleno a přesměrování kopírování souborů ve schránce není povoleno v počítačích se systémem Windows Server 2003, Windows 8 a Windows XP. Pokud nastavení této zásady zakážete, přesměrování klientské jednotky je vždycky povolené. I když je povolené přesměrování schránky, přesměrování kopírování souborů ve schránce je vždycky povolené. Pokud nastavení této zásady nenakonfigurujete, přesměrování jednotky klienta a přesměrování kopírování souborů ve schránce nejsou zadané na úrovni Zásady skupiny.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067197)  
  
  **Výchozí**: povoleno
  
- **Vyzvat k zadání hesla při připojení**  
  Nastavení této zásady určuje, jestli služba Vzdálená plocha vždy po připojení vyzve klienta k zadání hesla. Toto nastavení můžete použít k vykonání výzvy k zadání hesla pro uživatele přihlášené ke vzdálené ploše, i když už heslo zadali v Připojení ke vzdálené ploše klientovi. Ve výchozím nastavení služba Vzdálená plocha umožňuje uživatelům, aby se automaticky přihlásili zadáním hesla v klientovi Připojení ke vzdálené ploše. Pokud nastavení této zásady povolíte, nebudou se uživatelé automaticky přihlašovat ke službě Vzdálená plocha zadáním hesel v klientovi Připojení ke vzdálené ploše. při přihlášení se zobrazí výzva k zadání hesla. Pokud nastavení této zásady zakážete, uživatelé se budou moct kdykoli přihlásit ke vzdálené ploše tak, že poskytnou svá hesla v klientovi Připojení ke vzdálené ploše. Pokud nastavení této zásady nenakonfigurujete, automatické přihlašování se na úrovni Zásady skupiny nezadá.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067328)  
  
  **Výchozí**: povoleno
  
- **Úroveň šifrování připojení klienta služby Vzdálená plocha**  
  Určuje, jestli se má vyžadovat použití konkrétní úrovně šifrování k zabezpečení komunikace mezi klientskými počítači a Hostitel relace VP servery během připojení protokol RDP (Remote Desktop Protocol) (RDP). Tato zásada platí jenom v případě, že používáte nativní šifrování RDP. Nativní šifrování RDP (na rozdíl od šifrování SSL) se ale nedoporučuje. Tato zásada se nevztahuje na šifrování SSL. Pokud nastavení této zásady povolíte, musí být při všech komunikacích mezi klienty a Hostitel relace VP servery používána metoda šifrování uvedená v tomto nastavení. Ve výchozím nastavení je úroveň šifrování nastavena na hodnotu Vysoká. K dispozici jsou následující metody šifrování:  
  - *Vysoká* – vysoká hodnota nastavení šifruje data odesílaná z klienta na server a ze serveru do klienta pomocí silného 128-bitového šifrování. Tato úroveň šifrování se používá v prostředích, která obsahují jenom 128 klientů (například klientů se spuštěným Připojení ke vzdálené ploše). Klienti, kteří tuto úroveň šifrování nepodporují, se nemohou připojit k Hostitel relace VPm serverům.  
  - *Kompatibilní s klientem* – nastavení kompatibilní s klientem šifruje data odesílaná mezi klientem a serverem s maximální silou klíče podporovanou klientem. Tato úroveň šifrování se používá v prostředích, která zahrnují klienty, kteří nepodporují 128 bitů šifrování.  
  - *Nízká* – nastavení nízká šifruje pouze data odesílaná z klienta na server pomocí 56 bitového šifrování.  
  
  Pokud toto nastavení zakážete nebo nenakonfigurujete, úroveň šifrování, která se má použít pro vzdálené připojení k Hostitel relace VP servery, nebude využívána prostřednictvím Zásady skupiny. Důležité dodržování předpisů FIPS je možné nakonfigurovat prostřednictvím kryptografie systému. Použijte algoritmy kompatibilní se standardem FIPS pro nastavení šifrování, hashování a podepisování v Zásady skupiny (v části počítač \ zabezpečení \ \ Policies\Security možnosti.) Nastavení kompatibilní se standardem FIPS šifruje a dešifruje data odesílaná z klienta na server a ze serveru do klienta se šifrovacími algoritmy FIPS (Federal Information Processing Standard) 140 pomocí kryptografických modulů Microsoftu. Tato úroveň šifrování se používá v případě, že komunikace mezi klienty a Hostitel relace VP servery vyžaduje nejvyšší úroveň šifrování.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067222)  
  
  **Výchozí**: vysoká
  
## <a name="remote-management"></a>Vzdálená správa  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) .  

- **Blokovat ukládání přihlašovacích údajů spustit jako**  
  Základní ověřování klienta.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067300)  
  
  **Výchozí**: povoleno
  
- **Základní ověřování**  
  Toto nastavení zásad umožňuje spravovat, jestli služba Vzdálená správa systému Windows (WinRM) akceptuje základní ověřování od vzdáleného klienta. Pokud nastavení této zásady povolíte, služba WinRM přijme základní ověřování od vzdáleného klienta. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, služba WinRM nepřijme základní ověřování ze vzdáleného klienta.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067223)  
  
  **Výchozí**: zakázáno
  
- **Blokovat ověřování algoritmem Digest klienta**  
  Toto nastavení zásad umožňuje spravovat, jestli klient Vzdálená správa systému Windows (WinRM) používá ověřování hodnotou hash. Pokud nastavení této zásady povolíte, klient WinRM nebude používat ověřování hodnotou hash. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, bude klient WinRM používat ověřování hodnotou hash.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067302)  
  
  **Výchozí**: povoleno
  
- **Nešifrovaný provoz**  
  Toto nastavení zásad umožňuje spravovat, jestli služba Vzdálená správa systému Windows (WinRM) odesílá a přijímá nešifrované zprávy přes síť. Pokud nastavení této zásady povolíte, klient WinRM odesílá a přijímá nešifrované zprávy přes síť. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, bude klient WinRM odesílat nebo přijímat pouze šifrované zprávy přes síť.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067226)  
  
  **Výchozí**: zakázáno
  
- **Nešifrovaný provoz klienta**  
  Toto nastavení zásad umožňuje spravovat, jestli klient Vzdálená správa systému Windows (WinRM) odesílá a přijímá nešifrované zprávy přes síť. Pokud nastavení této zásady povolíte, klient WinRM odesílá a přijímá nešifrované zprávy přes síť. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, bude klient WinRM odesílat nebo přijímat pouze šifrované zprávy přes síť.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067304)  
  
  **Výchozí**: zakázáno
  
- **Základní ověřování klienta**  
  Toto nastavení zásad umožňuje spravovat, jestli klient Vzdálená správa systému Windows (WinRM) používá základní ověřování. Pokud nastavení této zásady povolíte, bude klient WinRM používat základní ověřování. Pokud je služba WinRM nakonfigurovaná tak, aby používala přenos přes protokol HTTP, uživatelské jméno a heslo se přes síť odesílají jako nešifrovaný text. Pokud nastavení této zásady zakážete nebo nenakonfigurujete, klient WinRM nebude používat základní ověřování.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067252)  
  
  **Výchozí**: zakázáno
  
## <a name="remote-procedure-call"></a>Vzdálené volání procedur  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) .  

- **Možnosti neověřeného klienta RPC**  
  Nastavení této zásady určuje, jak bude modul runtime serveru RPC zpracovávat neověřené klienty RPC připojující se k serverům RPC. Nastavení této zásady má vliv na všechny aplikace RPC. V prostředí domény použijte nastavení této zásady opatrně, protože může mít vliv na celou řadu funkcí, včetně samotného zpracování zásad skupiny. Vrácení změny nastavení této zásady může vyžadovat ruční zásah na každém dotčeném počítači. Nastavení této zásady by se nikdy nemělo použít na řadič domény. Pokud nastavení této zásady zakážete, bude modul runtime serveru RPC používat hodnotu "Ověřený" v klientovi Windows a hodnotu "žádné" ve verzích Windows serveru, které podporují toto nastavení zásad. Pokud nastavení této zásady nenakonfigurujete, zůstane zakázané. Modul runtime serveru RPC se chová, jako by byl povolen s hodnotou "ověřené" používané pro klienta Windows, a s hodnotou "none" použitou pro skladové položky serveru, které podporují toto nastavení zásad. Pokud nastavení této zásady povolíte, přesměruje modul runtime serveru RPC, aby omezil neověřené klienty RPC připojující se k serverům RPC běžícím v počítači. Klient se považuje za ověřeného klienta, pokud používá pojmenovaný kanál ke komunikaci se serverem nebo v případě, že používá zabezpečení RPC. Rozhraní RPC, která jsou výslovně vyžadovaná k přístupu neověřeným klientům, můžou být z tohoto omezení vyloučená v závislosti na zvolené hodnotě pro toto nastavení zásad.  
  - *Žádné* umožňuje všem klientům RPC připojit se k serverům RPC běžícím na počítači, na kterém je nastavení zásad použito. 
  - Možnost *ověřeno* umožňuje připojit se k serverům RPC běžícím na počítači, na kterém je nastavená zásada, jenom ověřeným klientům RPC (podle definice výše). Výjimky jsou udělovány rozhraním, která je požaduje. 
  - *Ověřování bez výjimek* umožňuje připojit se k serverům RPC běžícím na počítači, na kterém je nastavená zásada, jenom ověřeným klientům RPC (podle definice výše). Nejsou povoleny žádné výjimky. Poznámka: nastavení této zásady se nepoužije, dokud se systém nerestartuje.  

  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067225)  

  **Výchozí**: ověřeno

## <a name="search"></a>Hledat 
Další informace najdete v tématu [zásady CSP – hledání](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) v dokumentaci k Windows.  

- **Zakázat indexování šifrovaných položek**  
  Tato zásada povolí nebo zakáže indexování položek. Tento přepínač je určen pro indexer služby Windows Search, který určuje, zda budou zašifrovány položky, například soubory chráněné jako Windows Information Protection (nedokončené výroby). Pokud je tato zásada povolená, chráněné položky WIP se indexují a metadata o nich se ukládají do nešifrovaného umístění. Součástí metadat jsou takové položky jako cesta k souboru a datum změny. Když je zásada zakázaná, položky chráněné při nedokončené výrobě nejsou indexované a nezobrazují se ve výsledcích v Cortana nebo v Průzkumníkovi souborů. Pokud se v zařízení nachází mnoho souborů médií chráněných WIP, může to mít také dopad na výkon fotografií a aplikací Groove.  
  [Další informace]( https://go.microsoft.com/fwlink/?linkid=2067303)  
  
  **Výchozí**: Ano
  
## <a name="smart-screen"></a>Smart Screen  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – filtr](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) .  

- **Zablokovat provádění neověřených souborů**  
  Zablokuje uživateli spouštění neověřených souborů. 
  - *Nenakonfigurováno* – zaměstnanci můžou ignorovat upozornění filtru SmartScreen a spouštět škodlivé soubory. 
  - *Ano* – zaměstnanci nemůžou ignorovat upozornění filtru SmartScreen a spouštět škodlivé soubory.

  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067228)  
  
  **Výchozí**: Ano

- **Vyžadovat filtr SmartScreen pro aplikace a soubory**  
  Umožňuje správcům IT konfigurovat filtr SmartScreen pro Windows.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067168)  

  **Výchozí**: Ano
  
## <a name="system"></a>Systému  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – systém](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) .  

- **Inicializace ovladače spuštění systému**  
  Nastavení této zásady umožňuje určit, které spouštěcí ovladače se mají inicializovat, na základě klasifikace, která je určená ovladačem spuštění antimalwarového spuštění od předčasného spuštění. Spouštěcí ovladač předčasného spuštění antimalwarového spuštění může pro každý ovladač spouštěcího spuštění vrátit následující klasifikace: 
  - *Dobrá* – ovladač je podepsaný a nebyl zfalšován.  
  - *Chybné* – ovladač byl identifikován jako malware. Doporučujeme, abyste nepovolili inicializaci známých špatných ovladačů. 
  - *Chybné, ale vyžaduje se pro spuštění* – ovladač byl identifikován jako malware, ale počítač nemůže úspěšně spustit bez načtení tohoto ovladače. 
  - *Neznámý* – tento ovladač se nezískal na základě vaší aplikace pro detekci malwaru a neklasifikovaný ovladačem spuštění antimalwarového spuštění antimalwarového programu.  

  Pokud nastavení této zásady povolíte, můžete zvolit, které ovladače spouštěcího spuštění se mají inicializovat při příštím spuštění počítače. Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, budou ovladače spouštění pro spuštění správné, neznámé nebo chybné, ale kritické pro spouštění a inicializace ovladačů, které byly zjištěny jako chybné, budou vynechány. Pokud vaše aplikace pro detekci malwaru neobsahuje počáteční ovladač spuštění antimalwarové spouštěcí sady nebo pokud je vypnutý ovladač počátečního spuštění antimalwarové služby, nemá toto nastavení žádný vliv a všechny ovladače spouštěcího spuštění jsou inicializované.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067307)   
  
  **Výchozí**: dobrý neznámý a špatný kritický


## <a name="wi-fi"></a>Wi-Fi  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – WiFi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) .  

- **Blokovat sdílení internetu**  
  Určuje, jestli je na zařízení možné sdílení internetu.   
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067327)   

  **Výchozí**: Ano  

- **Blokovat automatické připojení k Wi-Fi hotspotům**  
  Povolí nebo zakáže, aby se zařízení automaticky připojovala k Wi-Fi hotspotům.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067320)   

  **Výchozí**: Ano  
  
## <a name="windows-connection-manager"></a>Správce připojení k Windows  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) .  

- **Blokovat připojení k sítím mimo doménu**  
  Nastavení této zásady zabraňuje počítačům v připojení k síti založené na doméně i k síti, která není založená na doméně. Pokud je toto nastavení zásad povolené, počítač reaguje na automatické a ruční pokusy o připojení k síti na základě následujících okolností: 
  - Automatické pokusy o připojení, pokud je počítač již připojen k síti založené na doméně, jsou blokovány všechny automatické pokusy o připojení k sítím, které nejsou v doméně. Pokud je počítač již připojen k síti založené na doméně, jsou blokovány automatické pokusy o připojení do sítí založených na doméně. 
  - Ruční pokusy o připojení, když je počítač už připojený k síti, která není založená na doméně, nebo k síti založené na doméně přes jiné médium než Ethernet a uživatel se pokusí vytvořit ruční připojení k další síti v rozporu s touto zásadou. nastavení se odpojí stávající síťové připojení a povolí se ruční připojení. Pokud je počítač již připojen k síti založené na doméně nebo k síti založené na doméně přes síť Ethernet a uživatel se pokusí vytvořit ruční připojení k další síti v rozporu s nastavením této zásady, stávající připojení k síti Ethernet je Údržba a ruční pokus o připojení je zablokovaný.  

  Pokud nastavení této zásady není nakonfigurované nebo je zakázané, počítače se můžou současně připojit k doméně i k sítím, které nejsou v doméně.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067323)  

  **Výchozí**: povoleno
  
## <a name="microsoft-defender"></a>Microsoft Defender  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) .  

- **Kontrolovat příchozí e-mailové zprávy**  
  Povolí nebo zakáže kontrolu e-mailu.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067116)  
  
  **Výchozí**: Ano  

- **Typ podřízeného procesu, který spouští aplikace Office**  
  Aplikace Office nemůžou vytvářet podřízené procesy. K tomu patří Word, Excel, PowerPoint, OneNote a Access. Toto je typické chování malwaru, zejména u útoků založených na makrech, které se pokoušejí použít aplikace Office ke spouštění nebo stahování škodlivých spustitelných souborů.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067121)  
  
  **Výchozí**: blok
  
- **Typ souhlasu pro odeslání ukázky v programu Defender**  
  Kontroluje, jestli se na úrovni souhlasu uživatele v programu Microsoft Defender odesílají data. Pokud je požadovaný souhlas již udělen, Microsoft Defender je odešle. V takovém případě se uživatelské rozhraní spustí, aby požádalo o souhlas uživatele (když je povolený program Defender/AllowCloudProtection) před odesláním dat.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067131)  
  
  **Výchozí**: automaticky odesílat bezpečné vzorky 
  
- **Interval aktualizace podpisu (v hodinách)**  
  Interval aktualizace signatury Defenderu v hodinách
  
  **Výchozí**: 4
  
- **Typ spuštění datové části staženého skriptu**  
  Typ spuštění datové části staženého skriptu Defenderu
  
  **Výchozí**: blok
  
- **Zabránit krádeži pověření typu**  
  Ochrana přihlašovacích údajů v programu Microsoft Defender používá zabezpečení na základě virtualizace k izolaci tajných kódů, aby k nim měli přístup jenom privilegovaný systémový software. Neoprávněný přístup k těmto důvěrným informacím může vést k útokům zahrnujícím krádeže přihlašovacích údajů, jako je například Pass-the-Hash nebo Pass-The-Ticket. Ochrana přihlašovacích údajů v programu Microsoft Defender brání těmto útokům ochranou hodnot hash hesla NTLM, lístků pro udělení lístku Kerberos a přihlašovacích údajů uložených aplikacemi jako přihlašovací údaje domény.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067065)  
  
  **Výchozí**: Povolit

- **Typ provedení obsahu e-mailu**  
  Toto pravidlo blokuje spouštění nebo spouštění těchto typů souborů z e-mailu, který se zobrazuje v aplikaci Microsoft Outlook nebo webové pošty (například Gmail.com nebo Outlook.com): spustitelné soubory (například. exe,. dll nebo. scr) soubory skriptu (například PowerShell. PS, VisualBasic. vbs, nebo soubor JavaScript. js). soubory archivu skriptu.  
  [Další informace](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-executable-content-from-email-client-and-webmail) 
  
  **Výchozí**: blok

- **Spuštění aplikace Adobe Reader v podřízeném procesu**  

  **Výchozí**: Povolit

- **Typ ochrany sítě**  
  Tato zásada umožňuje zapnout ochranu sítě (blokovat/audit) nebo vypnout v programu Microsoft Defender zneužití Guard. Ochrana sítě je funkcí ochrany před zneužitím v programu Microsoft Defender, která chrání zaměstnance pomocí libovolné aplikace v přístupu k podvodným podvodům, webům pro zneužití a škodlivému obsahu na internetu. To zahrnuje prevenci prohlížeče třetích stran v připojení k nebezpečným webům. Typ hodnoty je celé číslo. Pokud povolíte toto nastavení, bude zapnutá ochrana sítě a zaměstnanci ji nebudou moct vypnout. Jeho chování se dá řídit následujícími možnostmi: blokování a audit. Pokud povolíte tuto zásadu s možností blokovat, uživatelé a aplikace budou mít zablokovaný připojení k nebezpečným doménám. Tuto aktivitu vidíte v programu Microsoft Defender Security Center. Pokud povolíte tuto zásadu s možností audit, uživatelé nebo aplikace nebudou mít možnost se připojit k nebezpečným doménám. Tato aktivita se ale pořád zobrazuje v programu Microsoft Defender Security Center. Pokud tuto zásadu zakážete, nebudou se uživatelé nebo aplikace zablokovat z připojení k nebezpečným doménám. V programu Microsoft Defender Security Center neuvidíte žádné síťové aktivity. Pokud tuto zásadu nenakonfigurujete, blokování sítě je ve výchozím nastavení zakázané.  
  [Další informace](/windows/security/threat-protection/microsoft-defender-atp/enable-network-protection)  
  
  **Výchozí**: Povolit
  
- **Den kontroly plánu Defenderu**  
  Den kontroly plánu Defenderu
  
  **Výchozí**: každý den
  
- **Ochrana Doručená v cloudu**  
  Aby se Váš počítač mohl nejlépe chránit, Microsoft Defender pošle Microsoftu informace o všech zjištěných problémech. Microsoft bude tyto informace analyzovat, získat další informace o problémech, které mají vliv na vás a jiné zákazníky, a nabízí Vylepšená řešení.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067039)
  
  **Výchozí**: Ano  

- **Akce potenciálně nežádoucí aplikace v Defenderu**  
  Funkce ochrany potenciálně nežádoucí aplikace (PUA) v antivirové ochraně v programu Microsoft Defender může identifikovat a blokovat PUAs ze stahování a instalace do koncových bodů ve vaší síti. Tyto aplikace nejsou považovány za viry, malware nebo jiné typy hrozeb, ale mohou provádět akce s koncovými body, které nepříznivě ovlivňují jejich výkon nebo použití. PUA může také odkazovat na aplikace, které se považují za nekvalitní pověst. Typické chování PUA zahrnuje různé typy softwaru, které se provedou vypsáním do ovladačů pro webové prohlížeče a optimalizace registru, které zjišťují problémy, vyžádají si platbu, aby opravila chyby, ale zůstaly na koncovém bodu a neobsahují žádné změny ani optimalizace (označované taky jako). programy neautorizovaných antivirových programů). Tyto aplikace můžou zvýšit riziko napadení vaší sítě malwarem, způsobit obtížnější nákazu malwaru a může obcházet prostředky IT při čištění aplikací.  
  [Další informace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection)    
  
  **Výchozí**: blok  

- **Typ kódu makra zakódováného skriptu**  
  Malware a další hrozby se mohou pokusit dekódovat nebo skrýt škodlivý kód v některých souborech skriptu. Toto pravidlo zabrání spuštění skriptů, které se jeví jako nepoužívané.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067026)  
  
  **Výchozí**: blok
  
- **Kontrolovat vyměnitelné jednotky během úplného prohledávání**  
  Umožňuje, aby Microsoft Defender během úplného prohledávání kontroloval škodlivý a nežádoucí software v vyměnitelných jednotkách (například jednotky Flash). Antivirová ochrana v programu Microsoft Defender před spuštěním kontroluje všechny soubory na zařízeních USB.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067036)  
  
  **Výchozí**: Ano  
  
- **Prohledat archivní soubory**  
  Defender prohledává archivní soubory.
  
  **Výchozí**: Ano
  
- **Monitorování chování**  
  Povolí nebo zakáže funkci monitorování chování programu Microsoft Defender. V systému Windows 10 tyto senzory shromažďují a zpracovávají signály chování z operačního systému a odesílají tato data ze senzorů do vaší privátní a izolované cloudové instance ATP v programu Microsoft Defender.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067111)  
  
  **Výchozí**: Ano

- **Kontrolovat soubory otevřené ze síťových složek**  
  Pokud jsou soubory jen pro čtení, uživatel nebude moct odebrat zjištěný malware.
  
  **Výchozí**: Ano

- **Nedůvěryhodný typ procesu USB**  
  Pomocí tohoto pravidla můžou správci zabránit spuštění nepodepsaných nebo nedůvěryhodných spustitelných souborů z vyměnitelných jednotek USB, včetně karet SD.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067100)  
  
  **Výchozí**: blok
  
- **Typ injektáže jiného procesu aplikací Office**  
  Aplikace Office, včetně Wordu, Excelu, PowerPointu a OneNotu, nebudou moct vkládat kód do jiných procesů. Většinou ho malware používá ke spouštění škodlivého kódu při pokusu o skrytí aktivity z skenovacích modulů antivirového programu.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067019)  
  
  **Výchozí**: blok
  
- **Kód makra Office Allow import typu Win32**  
  Malware může pomocí kódu makra v souborech Office importovat a načítat knihovny DLL Win32, které se pak dají použít k umožnění dalších infekcí v celém systému. Toto pravidlo se pokusí zablokovat soubory Office, které obsahují kód makra schopný importovat knihovny DLL Win32. K tomu patří Word, Excel, PowerPoint a OneNote.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067130)  
  
  **Výchozí**: blok  
  
- **Úroveň blokování cloudu Defenderu**  
  Úroveň bloku cloudu Defenderu
  
  **Výchozí**: Nenakonfigurováno

- **Sledování v reálném čase**  
  Defender vyžaduje sledování v reálném čase.
  
  **Výchozí**: Ano
 
- **Aplikace Office Communications se spouští v podřízeném procesu**  

  **Výchozí**: Povolit

- **Typ vytvoření nebo spuštění obsahu aplikací Office**  
  Toto pravidlo cílí na typické chování používané podezřelými a zlomyslnými doplňky a skripty (rozšíření), které vytvářejí nebo spouštějí spustitelné soubory. Toto je typická antimalwarová technika. Používání rozšíření je pro aplikace Office blokované. Tato rozšíření obvykle používají skripty Windows Scripting Host (soubory. WSH) ke spouštění skriptů, které automatizují určité úlohy nebo poskytují uživatelsky vytvořené funkce doplňků.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067108)  
  
  **Výchozí**: blok

## <a name="microsoft-defender-firewall"></a>Firewall v programu Microsoft Defender  
Další informace najdete v tématu [2.2.2 FW_PROFILE_TYPOE]( https://docs.microsoft.com/openspecs/windows_protocols/ms-fasp/7704e238-174d-4a5e-b809-5f3787dd8acc) v dokumentaci k Windows Protocols.  

- **Doména profilu brány firewall**  
  Určuje profily, do kterých pravidlo patří: doména, soukromá, veřejná. Tato hodnota představuje profil pro sítě, které jsou připojené k doménám.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2066796)  

  - **Blokovaná příchozí připojení**  
    **Výchozí**: Ano

  - **Vyžadují se odchozí připojení.**  
    **Výchozí**: Ano 

  - **Blokovaná příchozí oznámení**  
    **Výchozí**: Ano

  - **Povolená brána firewall**  
    **Výchozí**: povoleno

- **Veřejný profil brány firewall**  
  Určuje profily, do kterých pravidlo patří: doména, soukromá, veřejná. Tato hodnota představuje profil pro veřejné sítě. Tyto sítě jsou klasifikovány jako veřejné správci v hostiteli serveru. Klasifikace proběhne při prvním připojení hostitele k síti. Tyto sítě jsou obvykle na letištích, v kavárnách a na jiných veřejných místech, kde jsou tito partneři v síti nebo správce sítě nedůvěryhodní.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067143)  

  - **Blokovaná příchozí připojení**  
    **Výchozí**: Ano

  - **Vyžadují se odchozí připojení.**  
    **Výchozí**: Ano 

  - **Blokovaná příchozí oznámení**  
    **Výchozí**: Ano

  - **Povolená brána firewall**  
    **Výchozí**: povoleno

  - **Pravidla zabezpečení připojení ze zásad skupiny nejsou sloučena.**  
    **Výchozí**: Ano

  - **Pravidla zásad ze zásad skupiny nejsou sloučena.**  
    **Výchozí**: Ano

- **Profil brány firewall Private**  
  Určuje profily, do kterých pravidlo patří: doména, soukromá, veřejná. Tato hodnota představuje profil privátních sítí.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067041)  

  - **Blokovaná příchozí připojení**  
    **Výchozí**: Ano

  - **Vyžadují se odchozí připojení.**  
    **Výchozí**: Ano 

  - **Blokovaná příchozí oznámení**  
    **Výchozí**: Ano

  - **Povolená brána firewall**  
    **Výchozí**: povoleno

## <a name="windows-hello-for-business"></a>Windows Hello pro firmy  
- **Vyžadovat rozšířenou ochranu proti falšování identity, pokud je dostupná**  
  Pokud ano, zařízení budou používat rozšířenou ochranu proti falšování identity, pokud jsou k dispozici. V případě ne se zablokuje ochrana proti falšování identity. Nenakonfigurované budou respektovat konfigurace provedené na klientovi.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067192)

  **Výchozí**: Ano

- **Konfigurace  Windows Hello pro firmy**  
    Windows Hello pro firmy je alternativní metoda pro přihlašování do systému Windows tím, že nahrazujete hesla, čipové karty a virtuální čipové karty.  

  - Když nastavíte *Ano*, povolíte tuto zásadu a zřídí zařízení Windows Hello pro firmy.  
  - Pokud je nastavené na *Nenakonfigurováno*, standardní hodnoty nebudou mít vliv na nastavení zásad daného zařízení. To znamená, že pokud je Windows Hello pro firmy v zařízení zakázané, zůstane zakázané. Pokud je povolená, zůstane povolený. 

  Nemůžete zakázat Windows Hello pro firmy prostřednictvím tohoto směrného plánu. Windows Hello pro firmy můžete zakázat při konfiguraci [registrace systému Windows](windows-hello.md)nebo jako součást profilu konfigurace zařízení pro [ochranu identity](identity-protection-configure.md).  

  **Výchozí**: Ano

- **Vyžadovat v PIN kódu malá písmena**  
  V případě potřeby musí kód PIN uživatele obsahovat aspoň jedno malé písmeno.

  **Výchozí**: povoleno

- **Vyžadovat speciální znaky v PIN kódu**  
  V případě potřeby musí kód PIN uživatele zahrnovat aspoň jeden speciální znak.

  **Výchozí**: povoleno

- **Minimální délka PIN kódu**  
  Minimální délka kódu PIN musí být mezi 4 a 127.

  **Výchozí hodnota**: 6

- **Vyžadovat v PIN kódu velká písmena**  
  Pokud se to vyžaduje, PIN kód uživatele musí obsahovat aspoň jedno velké písmeno.

  **Výchozí**: povoleno

## <a name="windows-ink-workspace"></a>Pracovní prostor Windows Ink  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) .  

- **Pracovní prostor Ink**  
  Určuje, jestli má uživatel přístup k pracovnímu prostoru rukopisu. 
  - *Zakázáno* – přístup k pracovnímu prostoru Ink je zakázán. Tato funkce je vypnutá.
  - *Povoleno* – funkce pracovní prostor rukopisu je zapnutá, ale uživatel k ní nemá přístup nad zamykací obrazovkou.
  - *Nenakonfigurováno* – funkce pracovní prostor rukopisu je zapnutá a uživatel ji může použít nad zamykací obrazovkou.  

  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067241)  

  **Výchozí**: povoleno
 
## <a name="windows-powershell"></a>Windows PowerShell  
Další informace najdete v dokumentaci k Windows v tématu [zásady CSP – WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) .  

- **Protokolování bloku skriptu prostředí Power Shell**  
  Nastavením této zásady lze povolit protokolování veškerého vstupu skriptu PowerShell do protokolu Microsoft-Windows-PowerShell/Operational Event Log. Pokud toto nastavení zásad povolíte, bude Windows PowerShell protokolovat zpracování příkazů, bloků skriptu, funkcí a skriptů – ať už se vyvolají interaktivně nebo prostřednictvím automatizace. Pokud nastavení této zásady zakážete, protokolování vstupu skriptu PowerShellu je zakázané. Pokud povolíte protokolování volání bloku skriptu, PowerShell kromě toho při vyvolání příkazu, bloku skriptu, funkce nebo skriptu spustí nebo zastaví protokol události. Povolení protokolování vyvolání generuje velké množství protokolů událostí. Poznámka: Toto nastavení zásad existuje v editoru Zásady skupiny v části Konfigurace počítače i Konfigurace uživatele. Nastavení zásad konfigurace počítače má přednost před nastavením zásad konfigurace uživatele.  
  [Další informace](https://go.microsoft.com/fwlink/?linkid=2067330)  

  **Výchozí**: povoleno

## <a name="whats-changed-in-the-new-template"></a>Co se změnilo v nové šabloně
Šablona *základní hodnoty zabezpečení MDM pro šablonu květen 2019* obsahuje následující změny v šabloně *Preview* .

### <a name="changes-to-the-baseline-settings"></a>Změny nastavení standardních hodnot
Následující nastavení:
- *Novinka* v této nejnovější verzi směrného plánu.
- *Odebral* z této nejnovější základní verze, ale byly k dispozici v předchozí verzi.
- *V některém ze způsobů, jak* se nastavení objevilo v předchozí verzi. 

*[New]* [**nad zámkem**](#above-lock):
- **Hlasové aktivace aplikací z uzamčené obrazovky**    

*[Nový]* [**Správa aplikací**](#application-management): 
- **Blokovat uživatelský ovládací prvek pro instalace**  
- **Blokovat instalaci MSI aplikace se zvýšenými oprávněními**  

*[Odebrané]* [**BitLocker**](#bitlocker):  
- Zásada pro vyměnitelná jednotka služby BitLocker > **Metoda šifrování**
- **Zásada pro pevný disk zámku** *(všechna nastavení)*
- **Zásady systémových jednotek systému bitových zámků** *(všechna nastavení)*

*[Nové]* [**připojení**](#connectivity):
- **Konfigurace zabezpečeného přístupu k cestám UNC**

*[Novinka]* [**Ochrana zařízení**](#device-guard):
- **Zabezpečení na základě virtualizace**


*[Nové]* [**ochrana DMA**](#dma-guard):
- **Výčet externích zařízení nekompatibilních s režimem ochrany DMA v jádře**  

*[Nové]* [**Internet Explorer**](#internet-explorer):
- **Aktualizace internetových zón v Průzkumníkovi na stavový řádek prostřednictvím skriptu**
- **Internet Explorer zóna Internetu přetahování nebo kopírování a vkládání souborů**  
- **Zóna s omezeným přístupem v Internet Exploreru .NET Framework závislé součásti**  
- **Zóna místního počítače v aplikaci Internet Explorer nespouští antimalware proti ovládacím prvkům ActiveX**
- **Podpora šifrování v aplikaci Internet Explorer**  

*[Revidované]* [**Internet Explorer**](#internet-explorer):
- **Automaticky vyzvat k stažení souborů** v Internet Exploreru internet Zone > výchozí hodnota je teď **zakázaná**. Ve verzi Preview byl tento stav nastavený na povoleno.

*[Nová]* [**Vzdálená pomoc**](#remote-assistance):  
- **Vyžádané vzdálené pomoci** 
  - **Žádosti o vzdálenou pomoc – vyžádaná oprávnění**
  - **Maximální hodnota času lístku**  
  - **Maximální časové období lístku**  
  - **Metoda pozvánky e-mailu**


*[Novinka]* [**Microsoft Defender**](#microsoft-defender):
- **Spuštění aplikace Adobe Reader v podřízeném procesu**  
- **Aplikace Office Communications se spouští v podřízeném procesu** 

*[Novinka]* [ **firewall v programu Microsoft Defender**](#microsoft-defender-firewall)
- **Doména profilu brány firewall**  
  - **Blokovaná příchozí připojení**  
  - **Vyžadují se odchozí připojení.**  
  - **Blokovaná příchozí oznámení**  
  - **Povolená brána firewall**  
- **Veřejný profil brány firewall**  
  - **Blokovaná příchozí připojení**  
  - **Vyžadují se odchozí připojení.**  
  - **Blokovaná příchozí oznámení**  
  - **Povolená brána firewall** 
  - **Pravidla zabezpečení připojení ze zásad skupiny nejsou sloučena.**   
  - **Pravidla zásad ze zásad skupiny nejsou sloučena.**  
- **Profil brány firewall Private**  
  - **Blokovaná příchozí připojení**  
  - **Vyžadují se odchozí připojení.**  
  - **Blokovaná příchozí oznámení**  
  - **Povolená brána firewall**  

*[Nové]* [**Windows Hello pro firmy**](#windows-hello-for-business):  
- **Vyžadovat rozšířenou ochranu proti falšování identity, pokud je dostupná**  
- **Konfigurace Windows Hello pro firmy**  
- **Vyžadovat v PIN kódu malá písmena** 
- **Vyžadovat speciální znaky v PIN kódu** 
- **Minimální délka PIN kódu**  
- **Vyžadovat v PIN kódu velká písmena** 



<!-- The following settings were available in the Preview Baseline.   

   
## Above Lock  
For more information, see [Policy CSP - AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) in the Windows documentation.  

- **Block display of toast notifications**  
  This policy setting allows you to prevent app notifications from appearing on the lock screen. If you enable this policy setting, no app notifications are displayed on the lock screen. If you disable or don't configure this policy setting, users can choose which apps display notifications on the lock screen.
  
  **Default**: Yes  

## App Runtime    
For more information, see [Policy CSP - AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) in the Windows documentation.  

- **Microsoft accounts optional for Windows Store apps**  
  This policy setting lets you control whether Microsoft accounts are optional for Windows Store apps that require an account to sign in. This policy only affects Windows Store apps that support it. If you enable this policy setting, Windows Store apps that typically require a Microsoft account to sign in will allow users to sign in with an enterprise account instead. If you disable or don't configure this policy setting, users must sign in with a Microsoft account.  
  
  **Default**: Enabled  

## Application Management   
For more information, see [Policy CSP - ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) in the Windows documentation.  

- **Block game DVR (desktop only)**  
  Configures whether recording and broadcasting of games is allowed.
  
  **Default**: Yes  

## Auto Play   
For more information, see [Policy CSP - Autoplay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) in the Windows documentation.  

- **Auto play default auto run behavior**  
  This setting affects the default behavior for Autorun commands. Autorun commands are stored in autorun.inf files and can launch installation programs or other routines. When *Enabled*, Administrators can change the default autorun behavior on a device that runs Windows Vista or later. Behavior can be set to: a) completely disable autorun commands, or b) revert back to pre-Windows Vista behavior of automatically executing the autorun command. When set to *Disabled* or *Not Configured*, devices that run Windows Vista or later prompt the user as to whether an autorun command should run.
  
  **Default**: Do not execute  
  
- **Auto play mode**  
  This policy setting allows you to turn off the Autoplay feature. Autoplay begins reading from a drive as soon as you insert media in the drive. As a result, the setup file of programs and the music on audio media start immediately. Prior to Windows XP SP2, Autoplay is disabled by default on removable drives, such as the floppy disk drive (but not the CD-ROM drive), and on network drives. Starting with Windows XP SP2, Autoplay is enabled for removable drives as well, including Zip drives and some USB mass storage devices. If you enable this policy setting, Autoplay is disabled on CD-ROM and removable media drives, or disabled on all drives. This policy setting disables Autoplay on additional types of drives. You can't use this setting to enable Autoplay on drives on which it's disabled by default. If you disable or don't configure this policy setting, AutoPlay is enabled. Note: This policy setting appears in both the Computer Configuration and User Configuration folders. If the policy settings conflict, the policy setting in Computer Configuration takes precedence over the policy setting in User Configuration.
  
  **Default**: Disabled

- **Block auto play for non-volume devices**  
  This policy setting disallows AutoPlay for MTP devices like cameras or phones. If you enable this policy setting, AutoPlay isn't allowed for MTP devices like cameras or phones. If you disable or don't configure this policy setting, AutoPlay is enabled for non-volume devices.
  
  **Default**: Enabled  

## Bitlocker    
For more information, see [Policy CSP - Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) in the Windows documentation.  

- **Bit locker removable drive policy**  
  This policy setting is used to control the encryption method and cipher strength. The values of this policy determine the strength of the cipher that BitLocker uses for encryption. Enterprises may want to control the encryption level for increased security (AES-256 is stronger than AES-128). If you enable this setting, you'll be able to configure an encryption algorithm and key cipher strength for fixed data drives, operating system drives, and removable data drives individually. For fixed and operating system drives, we recommend that you use the XTS-AES algorithm. For removable drives, you should use AES-CBC 128-bit or AES-CBC 256-bit if the drive is used in other devices that aren't running Windows 10, version 1511 or later. Changing the encryption method has no effect if the drive is already encrypted or if encryption is in progress. In these cases, this policy setting is ignored.

  For Bit locker removable drive policy, configure the following settings:

    - **Require encryption for write access**  
      **Default**: Yes  
  
    - **Encryption method**  
      **Default**: AES 256bit CBC  

- **Bit locker fixed drive policy**  
  This policy setting is used to control the encryption method and cipher strength. The values of this policy determine the strength of the cipher that BitLocker uses for encryption. Enterprises may want to control the encryption level for increased security (AES-256 is stronger than AES-128). If you enable this setting, you can configure an encryption algorithm and key cipher strength for fixed data drives, operating system drives, and removable data drives individually. For fixed and operating system drives, we recommend that you use the XTS-AES algorithm. For removable drives, you should use AES-CBC 128-bit or AES-CBC 256-bit if the drive is used in other devices that aren't running Windows 10, version 1511 or later. Changing the encryption method has no effect if the drive is already encrypted or if encryption is in progress. In these cases, this policy setting is ignored.  
 
   For Bit locker fixed drive policy, configure the following settings: 
   - **Encryption method**
     **Default**: AES 256bit XTS  

- **Bit locker system drive policy**  
  This policy setting is used to control the encryption method and cipher strength. The values of this policy determine the strength of the cipher that BitLocker uses for encryption. Enterprises may want to control the encryption level for increased security (AES-256 is stronger than AES-128). If you enable this setting, you can configure an encryption algorithm and key cipher strength for fixed data drives, operating system drives, and removable data drives individually. For fixed and operating system drives, we recommend that you use the XTS-AES algorithm. For removable drives, you should use AES-CBC 128-bit or AES-CBC 256-bit if the drive is used in other devices that aren't running Windows 10, version 1511 or later. Changing the encryption method has no effect if the drive is already encrypted or if encryption is in progress. In these cases, this policy setting is ignored.  

   For Bit locker system drive policy, configure the following settings:
  - **Encryption method**  
    **Default**: AES 256bit XTS  

## Browser  
For more information, see [Policy CSP - Browser](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) in the Windows documentation.  

- **Require SmartScreen for Microsoft Edge**  
  Microsoft Edge uses Microsoft Defender SmartScreen (turned on) to protect users from potential phishing scams and malicious software by default. Also, by default, users can't disable (turn off) Microsoft Defender SmartScreen. Enabling this policy turns off Microsoft Defender SmartScreen and prevent users from turning it on. Don’t configure this policy to let users choose to turn Microsoft defender SmartScreen on or off.  
  
  **Default**: Yes  
  
- **Block malicious site access**  
  By default, Microsoft Edge allows users to bypass (ignore) the Microsoft Defender SmartScreen warnings about potentially malicious sites, allowing them to continue to the site. With this policy though, you can configure Microsoft Edge to prevent users from bypassing the warnings, blocking them from continuing to the site.
  
  **Default**: Yes  
  
- **Block unverified file download**
  By default, Microsoft Edge allows users to bypass (ignore) the Microsoft Defender SmartScreen warnings about potentially malicious files, allowing them to continue downloading the unverified file(s). Enabling this policy prevents users from bypassing the warnings, blocking them from downloading of the unverified file(s).
  
  **Default**: Yes  
  
- **Block Password Manager**  
  By default, Microsoft Edge uses Password Manager automatically, allowing users to manager passwords locally. Disabling this policy restricts Microsoft Edge from using Password Manager. Don’t configure this policy if you want to let users choose to save and manage passwords locally using Password Manager.
  
  **Default**: Yes  
  
- **Prevent certificate error overrides**  
  This policy setting prevents the user from ignoring Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificate errors that interrupt browsing (such as "expired", "revoked", or "name mismatch" errors) in Internet Explorer. If you enable this policy setting, the user can't continue browsing. If you disable or don't configure this policy setting, the user can choose to ignore certificate errors and continue browsing.
  
  **Default**: Yes  

## Connectivity  
For more information, see [Policy CSP - Connectivity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) in the Windows documentation.  

- **Block Internet download for web publishing and online ordering wizards**  
  This policy setting specifies whether Windows should download a list of providers for the web publishing and online ordering wizards. These wizards allow users to select from a list of companies that provide services such as online storage and photographic printing. By default, Windows displays providers downloaded from a Windows website in addition to providers specified in the registry. If you enable this policy setting, Windows doesn't download providers, and only the service providers that are cached in the local registry display. If you disable or don't configure this policy setting, a list of providers downloads when the user uses the web publishing or online ordering wizards. For more information that includes details on specifying service providers in the registry, see the documentation for the web publishing and online ordering wizards.  
  
  **Default**: Enabled  

- **Block downloading of print drivers over HTTP**  
  This policy setting specifies whether to allow this client to download print driver packages over HTTP. To set up HTTP printing, non-inbox drivers need to be downloaded over HTTP. Note: This policy setting doesn't prevent the client from printing to printers on the Intranet or the Internet over HTTP. It only prohibits downloading drivers that aren't already installed locally. If you enable this policy setting, print drivers can't be downloaded over HTTP. If you disable or don't configure this policy setting, users can download print drivers over HTTP.
  
  **Default**: Enabled  

## Credentials Delegation  
For more information, see [Policy CSP - CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) in the Windows documentation.  

- **Remote host delegation of non-exportable credentials**  
  Remote host allows delegation of non-exportable credentials. When using credential delegation, devices provide an exportable version of credentials to the remote host, which exposes users to the risk of credential theft from attackers on the remote host. If you enable this policy setting, the host supports Restricted Admin or Remote Credential Guard mode. If you disable or don't configure this policy setting, Restricted Administration and Remote Credential Guard mode aren't supported. User will always need to pass their credentials to the host.  

  
  **Default**: Enabled  

## Credentials UI  
For more information, see [Policy CSP - CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) in the Windows documentation.  

- **Enumerate administrators** 
  This policy setting controls whether administrator accounts display when a user attempts to elevate a running application. By default, administrator accounts aren't displayed when the user attempts to elevate a running application. If you enable this policy setting, all local administrator accounts on the PC display so the user can choose one and enter the correct password. If you disable this policy setting, users will always be required to type a user name and password to elevate.  

  
  **Default**: Disabled  

## Data Protection  
For more information, see [Policy CSP - DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) in the Windows documentation.  

- **Block direct memory access**  
  This policy setting allows you to block direct memory access (DMA) for all hot pluggable PCI downstream ports until a user logs into Windows. Once a user logs in, Windows will enumerate the PCI devices connected to the host plug PCI ports. Every time the user locks the machine, DMA is blocked on hot plug PCI ports with no children devices until the user logs in again. Devices that were already enumerated when the machine was unlocked will continue to function until unplugged. This policy setting is only enforced when BitLocker or device encryption is enabled.
  
  
  **Default**: Yes  

## Device Guard  
For more information, see [Policy CSP - DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) in the Windows documentation.  

- **Credential Guard**  
  This setting lets users turn on Credential Guard with virtualization-based security to help protect credentials at next reboot.
   
  **Default**: Enable with UEFI lock 

- **Enable virtualization based security**   
  Turns on virtualization-based security (VBS) at the next reboot. Virtualization-based security uses the Windows Hypervisor to provide support for security services.
  
  **Default**: Yes  


- **Launch system guard**    
  **Default**: Enabled  

## Device Installation  
For more information, see [Policy CSP - DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) in the Windows documentation.  

- **Hardware device installation by device identifiers**  
  This policy setting allows you to specify a list of Plug and Play hardware IDs and compatible IDs for devices that Windows is prevented from installing. This policy setting takes precedence over any other policy setting that allows Windows to install a device. If you enable this policy setting, Windows is prevented from installing a device whose hardware ID or compatible ID appears in the list you create. If you enable this policy setting on a remote desktop server, the policy setting affects redirection of the specified devices from a remote desktop client to the remote desktop server. If you disable or don't configure this policy setting, devices can install and update as allowed or prevented by other policy settings.
  
  **Default**: Block hardware device installation  

    When *Block hardware device installation* is selected, the following settings are available.
  
    - **Remove matching hardware devices**   
    This setting is available only when *Hardware device installation by device identifiers* is set to *Block hardware device installation*.
      
      **Default**: Yes
  
    - **Hardware device identifiers that are blocked**  
       This setting is available only when *Hardware device installation by device identifiers* is set to *Block hardware device installation*.
      
      **Default**: Yes  
  
- **Hardware device installation by setup classes**  
  This policy setting allows you to specify a list of device setup class globally unique identifiers (GUIDs) for device drivers that Windows is prevented from installing. This policy setting takes precedence over any other policy setting that allows Windows to install a device. If you enable this policy setting, Windows is prevented from installing or updating device drivers whose device setup class GUIDs appear in the list you create. If you enable this policy setting on a remote desktop server, the policy setting affects redirection of the specified devices from a remote desktop client to the remote desktop server. If you disable or don't configure this policy setting, Windows can install and update devices as allowed or prevented by other policy settings.
  
  **Default**: Block hardware device installation  

    When *Block hardware device installation* is selected, the following settings are available.
    - **Remove matching hardware devices**    
    This setting is available only when *Hardware device installation by setup classes* is set to *Block hardware device installation*.  

      **Default**: *No default configuration*  
  
    - **Hardware device identifiers that are blocked**  
      This setting is available only when *Hardware device installation by setup classes* is set to *Block hardware device installation*.
      
      **Default**: *No default configuration*  

## Device Lock  
For more information, see [Policy CSP - DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) in the Windows documentation.  

- **Prevent use of camera**  
  Disables the lock screen camera toggle switch in PC Settings and prevents a camera from being invoked on the lock screen. By default, users can enable invocation of an available camera on the lock screen. If you enable this setting, users will no longer be able to enable or disable lock screen camera access in PC Settings, and the camera can't be invoked on the lock screen. 
  
  **Default**: Enabled  

- **Require password**  
  Specifies whether device lock is enabled.
  
  **Default**: Yes  
  
    When *Require password* is set to *Yes*, the following settings are available.

    - **Password minimum character set count**  
      The number of complex element types (uppercase and lowercase letters, numbers, and punctuation) required for a strong PIN or password. PIN enforces the following behavior for desktop and mobile devices: 1 - Digits only 2 - Digits and lowercase letters are required 3 - Digits, lowercase letters, and uppercase letters are required. Not supported in desktop Microsoft accounts and domain accounts. 4 - Digits, lowercase letters, uppercase letters, and special characters are required. Not supported in desktop. The default value is 1. 
      
      **Default**: 3  
  
    - **Number of sign-in failures before wiping device**  
      The number of authentication failures allowed before the device is wiped. A value of 0 disables device wipe functionality.
        
      **Default**: 10  
  
    - **Password expiration (days)**  
      The Maximum password age policy setting determines how long (in days) that a password can be used before the system requires the user to change it. You can set passwords to expire after a number of days between 1 and 999, or you can specify that passwords never expire by setting the number of days to 0. If Maximum password age is between 1 and 999 days, the minimum password age must be less than the maximum password age. If Maximum password age is set to 0, Minimum password age can be any value between 0 and 998 days.
      
      **Default**: 60  
  
    - **Required password type**  
      Determines the type of PIN or password required.
      
      **Default**: Alphanumeric  
  
    - **Minimum password length**  
      The Minimum password length policy setting determines the least number of characters that can make up a password for a user account. You can set a value of between 1 and 14 characters, or you can establish that no password is required by setting the number of characters to 0.
      
      **Default**: 8  
  
    - **Block simple passwords**  
      Specifies whether PINs or passwords such as "1111" or "1234" are allowed. For the desktop, it also controls the use of picture passwords.
      
      **Default**: Yes  
        *A setting of Yes prevents use of simple passwords.* 

  - **Prevent reuse of previous passwords**  
    Specifies how many passwords can be stored in the history that can’t be used. The value includes the user's current password. For example, with a setting of *1* the user can't reuse their current password when choosing a new password. A setting of *5* means that a user can't set their new password to their current password or any of their previous four passwords.
    
    **Default**: 24  

- **Prevent slide show**  
  Disables the lock screen slide show settings in PC Settings and prevents a slide show from playing on the lock screen. By default, users can enable a slide show that will run after they lock the machine. If you enable this setting, users can't modify slide show settings in PC Settings, and no slide show can start.
  
    **Default**: Enabled  
    *A setting of Enabled prevents slide shows from running.* 

- **Password minimum age in days**  
  The Minimum password age policy setting determines the period of time (in days) that a password must be used before the user can change it. You can set a value between 1 and 998 days, or you can allow password changes immediately by setting the number of days to 0. The minimum password age must be less than the Maximum password age, unless the maximum password age is set to 0, indicating that passwords will never expire. If the maximum password age is set to 0, the minimum password age can be set to any value between 0 and 998.
  
    **Default**: 1  

## Event Log Service  
For more information, see [Policy CSP - EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) in the Windows documentation.  

- **Security log maximum file size in KB**  
  This policy setting specifies the maximum size of the log file in kilobytes. If you enable this policy setting, you can configure the maximum log file size to be between 1 megabyte (1024 kilobytes) and 2 terabytes (2147483647 kilobytes) in kilobyte increments. If you disable or don't configure this policy setting, the maximum size of the log file is set to the locally configured value. This value can be changed by the local administrator using the Log Properties dialog and it defaults to 20 megabytes.
  
   **Default**: 196608  

- **System log maximum file size in KB**  
  This policy setting specifies the maximum size of the log file in kilobytes. If you enable this policy setting, you can configure the maximum log file size to be between 1 megabyte (1024 kilobytes) and 2 terabytes (2147483647 kilobytes) in kilobyte increments. If you disable or don't configure this policy setting, the maximum size of the log file is set to the locally configured value. This value can be changed by the local administrator using the Log Properties dialog and it defaults to 20 megabytes.
  
  **Default**: 32768  

- **Application log maximum file size in KB**  
  This policy setting specifies the maximum size of the log file in kilobytes. If you enable this policy setting, you can configure the maximum log file size to be between 1 megabyte (1024 kilobytes) and 2 terabytes (2147483647 kilobytes) in kilobyte increments. If you disable or don't configure this policy setting, the maximum size of the log file is set to the locally configured value. This value can be changed by the local administrator using the Log Properties dialog and it defaults to 20 megabytes.
  
  **Default**: 32768  

## Experience  
For more information, see [Policy CSP - Experience](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) in the Windows documentation.  

- **Block Windows Spotlight**  
  Allows IT admins to turn off all Windows Spotlight Features - Window spotlight on lock screen, Windows Tips, Microsoft consumer features, and other related features.
  
  **Default**: Yes  

  When *Block Windows Spotlight* is set to *Yes*, the following settings are available.
  
  - **Block third-party suggestions in Windows Spotlight**  
    Specifies whether to allow app and content suggestions from third-party software publishers in Windows spotlight features like lock screen spotlight, suggested apps in the Start menu, and Windows tips. Users may still see suggestions for Microsoft features, apps, and services.
      
    **Default**: Yes  
   - **Block consumer specific features**  
      Allows IT admins to turn on experiences that are typically for consumers only, such as Start suggestions, Membership notifications, Post-OOBE app install, and redirect tiles.
      
     **Default**: Yes  


## Exploit Guard  
For more information, see [Policy CSP - ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) in the Windows documentation.  

- **Exploit protection XML**  
  Enables the IT admin to push out a configuration that represents the desired system and application mitigation options to all the devices in the organization. The configuration is represented by an XML. Exploit protection helps protect devices from malware that use exploits to spread and infect. You use the Windows Security app or PowerShell to create a set of mitigations (known as a configuration). You can then export this configuration as an XML file and share it with multiple machines on your network so they all have the same set of mitigation settings. You can also convert and import an existing EMET configuration XML file into an exploit protection configuration XML.
  
  **Default**: *Sample xml is provided* 
 
## File Explorer  
For more information, see [Policy CSP - FileExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) in the Windows documentation.  

- **Block data execution prevention**  
  Disabling data execution prevention can allow certain legacy plug-in applications to function without terminating Explorer.
  
  **Default**: Disabled  
   
- **Block heap termination on corruption**  
  Disabling heap termination on corruption can allow certain legacy plug-in applications to function without terminating Explorer immediately, although Explorer may still terminate unexpectedly later.
  
  **Default**: Disabled  
    

## Internet Explorer  
For more information, see [Policy CSP - InternetExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) in the Windows documentation.  


- **Internet Explorer internet zone access to data sources**  
  This policy setting allows you to manage whether Internet Explorer can access data from another security zone using the Microsoft XML Parser (MSXML) or ActiveX Data Objects (ADO). If you enable this policy setting, users can load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you select Prompt in the drop-down box, users are queried to choose whether to allow a page to load in the zone that uses MSXML or ADO to access data from another site in the zone. If you disable this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you don't configure this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone drag content from different domains within windows**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in the same window. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in the same window. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when the source and destination are in the same window. Users can't change this setting in the Internet Options dialog. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in the same window. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy setting or don't configure it, users can drag content from one domain to a different domain when the source and destination are in the same window. Users can't change this setting in the Internet Options dialog.
  
  **Default**: Disabled
  
- **Internet Explorer certificate address mismatch warning**  
  This policy setting allows you to turn on the certificate address mismatch security warning. When this policy setting is turned on, the user is warned when visiting Secure HTTP (HTTPS) websites that present certificates issued for a different website address. This warning helps prevent spoofing attacks. If you enable this policy setting, the certificate address mismatch warning always appears. If you disable or don't configure this policy setting, the user can choose whether the certificate address mismatch warning appears (by using the Advanced page in the Internet Control panel).
  
  **Default**: Enabled 
  
- **Internet Explorer restricted zone less privileged sites**  
  This policy setting allows you to manage whether Web sites from less privileged zones, such as Internet sites, can navigate into this zone. If you enable this policy setting, Web sites from less privileged zones can open new windows in, or navigate into, this zone. The security zone will run without the added layer of security that is provided by the Protection from Zone Elevation security feature. If you select Prompt in the drop-down box, a warning is issued to the user that potentially risky navigation is about to occur. If you disable this policy setting, possibly harmful navigation is prevented. The Internet Explorer security feature is on in this zone as set by Protection from Zone Elevation feature control. If you don't configure this policy setting, the possibly harmful navigations are prevented. The Internet Explorer security feature is on in this zone as set by Protection from Zone Elevation feature control.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone automatic prompt for file downloads**  
  This policy setting determines whether users are prompted for non user-initiated file downloads. Regardless of this setting, users will receive file download dialogs for user-initiated downloads. If you enable this setting, users will receive a file download dialog for automatic download attempts. If you disable or don't configure this setting, file downloads that aren't user-initiated are blocked, and users will see the Notification bar instead of the file download dialog. Users can then click the Notification bar to allow the file download prompt.
  
  **Default**: Disabled
  
- **Internet Explorer internet zone .NET Framework reliant components**  
  This policy setting allows you to manage whether .NET Framework components that aren't signed with Authenticode can be executed from Internet Explorer. These components include managed controls referenced from an object tag and managed executables referenced from a link. If you enable this policy setting, Internet Explorer will execute unsigned managed components. If you select Prompt in the drop-down box, Internet Explorer will prompt the user to determine whether to execute unsigned managed components. If you disable this policy setting, Internet Explorer won't execute unsigned managed components. If you don't configure this policy setting, Internet Explorer will execute unsigned managed components.
  
  **Default**: Disable 
  
- **Internet Explorer internet zone allow only approved domains to use tdc ActiveX controls**  
  This policy setting controls if the user can run the TDC ActiveX control on websites. If you enable this policy setting, the TDC ActiveX control won't run from websites in this zone. If you disable this policy setting, the TDC Active X control will run from all sites in this zone.
  
  **Default**: Enabled 
  
- **Internet Explorer restricted zone script initiated windows**  
  This policy setting allows you to manage restrictions on script-initiated pop-up windows and windows that include the title and status bars. If you enable this policy setting, Windows Restrictions security won't apply in this zone. The security zone runs without the added layer of security provided by this feature. If you disable this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process. If you don't configure this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process.
  
  **Default**: Disabled 
  
- **Internet Explorer internet zone include local path when uploading files to server**  
  This policy setting controls if local path information gets sent when the user is uploading a file via an HTML form. If the local path information is sent, some information may be unintentionally revealed to the server. For instance, files sent from the user's desktop may contain the user name as a part of the path. If you enable this policy setting, path information is sent when the user is uploading a file via an HTML form. If you disable this policy setting, path information is removed when the user is uploading a file via an HTML form. If you don't configure this policy setting, the user can choose whether path information gets sent when they upload a file via an HTML form. By default, path information is sent.
  
  **Default**: Disabled 
  
- **Internet Explorer disable processes in enhanced protected mode**  
  This policy setting determines whether Internet Explorer 11 uses 64-bit processes (for greater security) or 32-bit processes (for greater compatibility) when running in Enhanced Protected Mode on 64-bit versions of Windows. Important: Some ActiveX controls and toolbars may not be available when 64-bit processes are used. If you enable this policy setting, Internet Explorer 11 will use 64-bit tab processes when running in Enhanced Protected Mode on 64-bit versions of Windows. If you disable this policy setting, Internet Explorer 11 will use 32-bit tab processes when running in Enhanced Protected Mode on 64-bit versions of Windows. If you don't configure this policy setting, users can turn this feature on or off using Internet Explorer settings. This feature is turned off by default.
  
  **Default**: Enabled 
  
- **Internet Explorer ignore certificate errors**  
  This policy setting prevents the user from ignoring Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificate errors that interrupt browsing (such as "expired", "revoked", or "name mismatch" errors) in Internet Explorer. If you enable this policy setting, the user can't continue browsing. If you disable or don't configure this policy setting, the user can choose to ignore certificate errors and continue browsing.
  
  **Default**: Disabled 
  
- **Internet Explorer internet zone loading of XAML files**  
  This policy setting allows you to manage the loading of Extensible Application Markup Language (XAML) files. XAML is an XML-based declarative markup language commonly used for creating rich user interfaces and graphics that take advantage of the Windows Presentation Foundation. If you enable this policy setting and set the drop-down box to Enable, XAML files are automatically loaded inside Internet Explorer. The user can't change this behavior. If you set the drop-down box to Prompt, the user is prompted for loading XAML files. If you disable this policy setting, XAML files aren't loaded inside Internet Explorer. The user can't change this behavior. If you don't configure this policy setting, the user can decide whether to load XAML files inside Internet Explorer.
  
  **Default**: Disable 
  
- **Internet Explorer internet zone automatic prompt for file downloads**  
  This policy setting determines whether users are prompted for non user-initiated file downloads. Regardless of this setting, users will receive file download dialogs for user-initiated downloads. If you enable this setting, users will receive a file download dialog for automatic download attempts. If you disable or don't configure this setting, file downloads that aren't user-initiated are blocked, and users will see the Notification bar instead of the file download dialog. Users can then click the Notification bar to allow the file download prompt.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone security warning for potentially unsafe files**  
  This policy setting controls if the "Open File - Security Warning" message appears when the user tries to open executable files or other potentially unsafe files (from an intranet file share by using File Explorer, for example). If you enable this policy setting and set the drop-down box to Enable, these files open without a security warning. If you set the drop-down box to Prompt, a security warning appears before the files open. If you disable this policy setting, these files don't open. If you don't configure this policy setting, the user can configure how the computer handles these files. By default, these files are blocked in the Restricted zone, enabled in the Intranet and Local Computer zones, and set to prompt in the Internet and Trusted zones.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone cross site scripting filter**  
  This policy controls if the Cross-Site Scripting (XSS) Filter will detect and prevent cross-site script injections into websites in this zone. If you enable this policy setting, the XSS Filter is turned on for sites in this zone, and the XSS Filter attempts to block cross-site script injections. If you disable this policy setting, the XSS Filter is turned off for sites in this zone, and Internet Explorer permits cross-site script injections.
  
  **Default**: Enabled 
  
- **Internet Explorer fallback to SSL3**  
  This policy setting allows you to block an insecure fallback to SSL 3.0. When this policy is enabled, Internet Explorer will attempt to connect to sites using SSL 3.0 or below when TLS 1.0 or greater fails. We recommend that you don't allow insecure fallback in order to prevent a man-in-the-middle attack. This policy doesn't affect which security protocols are enabled. If you disable this policy, system defaults are used.
  
  **Default**: No sites 
  
- **Internet Explorer locked down internet zone smart screen**  
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled 
  
- **Internet Explorer restricted zone launch applications and files in an iFrame**  
  This policy setting allows you to manage whether applications may be run and files may be downloaded from an IFRAME reference in the HTML of the pages in this zone. If you enable this policy setting, users can run applications and download files from IFRAMEs on the pages in this zone without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to run applications and download files from IFRAMEs on the pages in this zone. If you disable this policy setting, users are prevented from running applications and downloading files from IFRAMEs on the pages in this zone. If you don't configure this policy setting, users are prevented from running applications and downloading files from IFRAMEs on the pages in this zone.
  
  **Default**: Disable 
  
- **Internet Explorer bypass smart screen warnings about uncommon files**  
  This policy setting determines whether the user can bypass warnings from SmartScreen Filter. SmartScreen Filter warns the user about executable files that Internet Explorer users don't commonly download from the Internet. If you enable this policy setting, SmartScreen Filter warnings block the user. If you disable or don't configure this policy setting, the user can bypass SmartScreen Filter warnings.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone popup blocker**  
  This policy setting allows you to manage whether unwanted pop-up windows appear. Pop-up windows that are opened when the end user clicks a link aren't blocked. If you enable this policy setting, most unwanted pop-up windows are prevented from appearing. If you disable this policy setting, pop-up windows aren't prevented from appearing. If you don't configure this policy setting, most unwanted pop-up windows are prevented from appearing.
  
  **Default**: Enable  
  
- **Internet Explorer processes consistent MIME handling**  
  Internet Explorer contains dynamic binary behaviors: components that encapsulate specific functionality for the HTML elements to which they're attached. This policy setting controls whether the Binary Behavior Security Restriction setting is prevented or allowed. If you enable this policy setting, binary behaviors are prevented for the File Explorer and Internet Explorer processes. If you disable this policy setting, binary behaviors are allowed for the File Explorer and Internet Explorer processes. If you don't configure this policy setting, binary behaviors are prevented for the File Explorer and Internet Explorer processes.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java  
    
  
- **Internet Explorer Active X controls in protected mode**  
  This policy setting prevents ActiveX controls from running in Protected Mode when Enhanced Protected Mode is enabled. When a user has an ActiveX control installed that isn't compatible with Enhanced Protected Mode and a website attempts to load the control, Internet Explorer notifies the user and gives the option to run the website in regular Protected Mode. This policy setting disables this notification and forces all websites to run in Enhanced Protected Mode. Enhanced Protected Mode provides additional protection against malicious websites by using 64-bit processes on 64-bit versions of Windows. For computers running at least Windows 8, Enhanced Protected Mode also limits the locations Internet Explorer can read from in the registry and the file system. When Enhanced Protected Mode is enabled, and a user comes across a website that attempts to load an ActiveX control that isn't compatible with Enhanced Protected Mode, Internet Explorer notifies the user and gives the option to disable Enhanced Protected Mode for that particular website. If you enable this policy setting, Internet Explorer won't give the user the option to disable Enhanced Protected Mode. All Protected Mode websites will run in Enhanced Protected Mode. If you disable or don't configure this policy setting, Internet Explorer notifies users and provides an option to run websites with incompatible ActiveX controls in regular Protected Mode.  
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone loading of XAML files**  
  This policy setting allows you to manage the loading of Extensible Application Markup Language (XAML) files. XAML is an XML-based declarative markup language commonly used for creating rich user interfaces and graphics that take advantage of the Windows Presentation Foundation. If you enable this policy setting and set the drop-down box to Enable, XAML files are automatically loaded inside Internet Explorer. The user can't change this behavior. If you set the drop-down box to Prompt, the user is prompted for loading XAML files. If you disable this policy setting, XAML files aren't loaded inside Internet Explorer. The user can't change this behavior. If you don't configure this policy setting, the user can decide whether to load XAML files inside Internet Explorer.
  
  **Default**: Disable  
  
- **Internet Explorer processes scripted window security restrictions**  
  Internet Explorer allows scripts to programmatically open, resize, and reposition windows of various types. The Window Restrictions security feature restricts popup windows and prohibits scripts from displaying windows in which the title and status bars aren't visible to the user or obfuscate other Windows' title and status bars. If you enable this policy setting, scripted windows are restricted for all processes. If you disable or don't configure this policy setting, scripted windows aren't restricted.
  
  **Default**: Enabled   
  
- **Internet Explorer restricted zone run Active X controls and plugins**  
  This policy setting allows you to manage whether ActiveX controls and plug-ins can run on pages from the specified zone. If you enable this policy setting, controls and plug-ins can run without user intervention. If you selected Prompt in the drop-down box, users are asked to choose whether to allow the controls or plug-in to run. If you disable this policy setting, controls and plug-ins are prevented from running. If you don't configure this policy setting, controls and plug-ins are prevented from running.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone script Active X controls marked safe for scripting**  
  This policy setting allows you to manage whether an ActiveX control marked safe for scripting can interact with a script. If you enable this policy setting, script interaction can occur automatically without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow script interaction. If you disable this policy setting, script interaction is prevented from occurring. If you don't configure this policy setting, script interaction is prevented from occurring.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone logon options**  
  This policy setting allows you to manage settings for sign in options. If you enable this policy setting, you can choose from the following sign in options. 
  - *Anonymous*  - Use anonymous sign in to disable HTTP authentication and use the guest account only for the Common Internet File System (CIFS) protocol. 
  - *Prompt* - Use prompt for user name and password to query users for user IDs and passwords. After a user is queried, these values can be used silently for the rest of the session. 
  - *Automatic sign in only in Intranet zone* - Use this option to query users for user IDs and passwords in other zones. After a user is queried, these values can be used silently for the rest of the session. 
  - *Automatic sign in with current user name and password*- Use this option to attempt sign in using Windows NT Challenge Response (also known as NTLM authentication). If the server supports Windows NT Challenge Response, the sign in uses the user's network user name and password for sign in. If the server doesn't support Windows NT Challenge Response, the user is queried to provide the user name and password. 

  If you disable this policy setting, sign-in is set to *Automatic sign in only in Intranet zone*. If you don't configure this policy setting, sign-in is set to *Prompt* for username and password.
  
  **Default**: Anonymous  
  
- **Internet Explorer trusted zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, users are queried whether to allow the control to load with parameters or scripted.
  
  **Default**: Disable  
  
- **Internet Explorer check server certificate revocation**  
  This policy setting allows you to manage whether Internet Explorer will check revocation status of servers' certificates. Certificates are revoked when they are compromised or no longer valid, and this option protects users from submitting confidential data to a site that may be fraudulent or not secure. If you enable this policy setting, Internet Explorer will check to see if server certificates have been revoked. If you disable this policy setting, Internet Explorer won't check server certificates to see if they have been revoked. If you don't configure this policy setting, Internet Explorer won't check server certificates to see if they have been revoked.
  
  **Default**: Enabled 
  
- **Internet Explorer internet zone less privileged sites**  
  This policy setting allows you to manage whether Web sites from less privileged zones, such as Restricted Sites, can navigate into this zone. If you enable this policy setting, Web sites from less privileged zones can open new windows in, or navigate into, this zone. The security zone will run without the added layer of security that is provided by the Protection from Zone Elevation security feature. If you select Prompt in the drop-down box, a warning is issued to the user that potentially risky navigation is about to occur. If you disable this policy setting, the possibly harmful navigations are prevented. The Internet Explorer security feature is on in this zone as set by Protection from Zone Elevation feature control. If you don't configure this policy setting, Web sites from less privileged zones can open new windows in, or navigate into, this zone.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone file downloads**  
  This policy setting allows you to manage whether file downloads are permitted from the zone. This option gets determined by the zone of the page with the link causing the download, not the zone from which the file is delivered. If you enable this policy setting, files can be downloaded from the zone. If you disable this policy setting, files are prevented from being downloaded from the zone. If you don't configure this policy setting, files are prevented from being downloaded from the zone.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone run .NET Framework reliant components signed with Authenticode**  
  This policy setting allows you to manage whether .NET Framework components that are signed with Authenticode can be executed from Internet Explorer. These components include managed controls referenced from an object tag and managed executables referenced from a link. If you enable this policy setting, Internet Explorer will execute signed managed components. If you select Prompt in the drop-down box, Internet Explorer will prompt the user to determine whether to execute signed managed components. If you disable this policy setting, Internet Explorer won't execute signed managed components. If you don't configure this policy setting, Internet Explorer won't execute signed managed components.
  
  **Default**: Disable  
  
- **Internet Explorer prevent per user installation of Active X controls**  
  This policy setting allows you to prevent the installation of ActiveX controls on a per-user basis. If you enable this policy setting, ActiveX controls can't be installed on a per-user basis. If you disable or don't configure this policy setting, ActiveX controls can be installed on a per-user basis.
  
  **Default**: Enabled  
  
- **Internet Explorer prevent managing smart screen filter**  
  This policy setting prevents the user from managing SmartScreen Filter, which warns the user if the website they visit is known for fraudulent attempts to gather personal information through "phishing," or is known to host malware. If you enable this policy setting, the user isn't prompted to turn on SmartScreen Filter. All website addresses that aren't on the filters allow list are sent automatically to Microsoft without prompting the user. If you disable or don't configure this policy setting, the user gets prompted to decide whether to turn on SmartScreen Filter during the first-run experience.
  
  **Default**: Enable  
  
- **Internet Explorer processes MIME sniffing safety feature**  
  This policy setting determines whether Internet Explorer MIME sniffing will prevent promotion of a file of one type to a more dangerous file type. If you enable this policy setting, MIME sniffing will never promote a file of one type to a more dangerous file type. If you disable this policy setting, Internet Explorer processes will allow a MIME sniff promoting a file of one type to a more dangerous file type. If you don't configure this policy setting, MIME sniffing will never promote a file of one type to a more dangerous file type.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone download signed Active X controls**  
  This policy setting allows you to manage whether users may download signed ActiveX controls from a page in the zone. If you enable this policy, users can download signed controls without user intervention. If you select Prompt in the drop-down box, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded. If you disable the policy setting, signed controls can't download. If you don't configure this policy setting, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded.
  
  **Default**: Disable  
  
- **Internet Explorer auto complete**  
  This Auto-Complete feature can remember and suggest User names and passwords on Forms. If you enable this setting, the user can't change "User name and passwords on forms" or "prompt me to save passwords". The Auto Complete feature for User names and passwords on Forms is turned on. You have to decide whether to select "prompt me to save passwords". If you disable this setting the user can't change "User name and passwords on forms" or "prompt me to save passwords". The Auto Complete feature for User names and passwords on Forms is turned off. The user also can't opt to be prompted to save passwords. If you don't configure this setting, the user has the freedom of turning on Auto complete for User name and passwords on forms and the option of prompting to save passwords. To display this option, the users open the Internet Options dialog box, click the Contents Tab, and click the Settings button.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone allow VBscript to run**  
  This policy setting lets you decide whether VBScript can run on pages in specific Internet Explorer zones. Options include: 
  - *Enable* - VBScript runs on pages in specific zones, without any interaction. 
  - *Prompt* - Employees are prompted whether to allow VBScript to run in the zone. 
  - *Disable* - VBScript is prevented from running in the zone. If you disable or don’t configure this policy setting, VBScript runs without any interaction in the specified zone. 
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone allow only approved domains to use tdc Active X controls**  
  This policy setting controls if the user can run the TDC ActiveX control on websites. If you enable this policy setting, the TDC ActiveX control won't run from websites in this zone. If you disable this policy setting, the TDC Active X control will run from all sites in this zone.
  
  **Default**: Enabled  
  
- **Internet Explorer trusted zone don't run antimalware against Active X controls**  
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled 
  
- **Internet Explorer local machine zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to Medium Safety.
  
  **Default**: Disable java 
  
- **Internet Explorer intranet zone do not run antimalware against Active X controls**
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled  

- **Internet Explorer restricted zone scriptlets**  
  This policy setting allows you to manage whether the user can run scriptlets. If you enable this policy setting, the user can run scriptlets. If you disable this policy setting, the user can't run scriptlets. If you don't configure this policy setting, the user can enable or disable scriptlets.
  
  **Default**: Disabled  
  
- **Internet Explorer processes notification bar**  
  This policy setting allows you to manage whether the Notification bar is displayed for Internet Explorer processes when file or code installs are restricted. By default, the Notification bar is displayed for Internet Explorer processes. If you enable this policy setting, the Notification bar displays for the Internet Explorer Processes. If you disable this policy setting, the Notification bar won't be displayed for Internet Explorer processes. If you don't configure this policy setting, the Notification bar doesn't display for Internet Explorer Processes.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone download signed ActiveX controls**  
  This policy setting allows you to manage whether users may download signed ActiveX controls from a page in the zone. If you enable this policy, users can download signed controls without user intervention. If you select Prompt in the drop-down box, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded. If you disable the policy setting, signed controls can't download. If you don't configure this policy setting, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone smart screen**  
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled  
  
- **Internet Explorer remove run this time button for outdated Active X controls**  
  This policy setting allows you to stop users from seeing the "Run this time" button and from running specific outdated ActiveX controls in Internet Explorer. If you enable this policy setting, users won't see the "Run this time" button on the warning message that appears when Internet Explorer blocks an outdated ActiveX control. If you disable or don't configure this policy setting, users will see the "Run this time" button on the warning message that appears when Internet Explorer blocks an outdated ActiveX control. Clicking this button lets the user run the outdated ActiveX control once. For more information, see "Outdated ActiveX Controls" in the Internet Explorer TechNet library.
  
  **Default**: Enabled 
  
- **Internet Explorer internet zone launch applications and files in an iframe**  
  This policy setting allows you to manage whether applications may be run and files may be downloaded from an IFRAME reference in the HTML of the pages in this zone. If you enable this policy setting, users can run applications and download files from IFRAMEs on the pages in this zone without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to run applications and download files from IFRAMEs on the pages in this zone. If you disable this policy setting, users are prevented from running applications and downloading files from IFRAMEs on the pages in this zone. If you don't configure this policy setting, users are queried to choose whether to run applications and download files from IFRAMEs on the pages in this zone
  
  **Default**: Disable 
  
- **Internet Explorer restricted zone navigate windows and frames across different domains**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in different windows. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when both the source and destination are in different windows. Users can't change this setting. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in different windows. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy or don't configure it, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone smart screen**  
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled  
  
- **Internet Explorer locked down trusted zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java 
  
- **Internet Explorer check signatures on downloaded programs**  
  This policy setting allows you to manage whether Internet Explorer checks for digital signatures (which identifies the publisher of signed software and verifies it hasn't been modified or tampered with) on user computers before downloading executable programs. If you enable this policy setting, Internet Explorer will check the digital signatures of executable programs and display their identities before downloading them to user computers. If you disable this policy setting, Internet Explorer won't check the digital signatures of executable programs or display their identities before downloading them to user computers. If you don't configure this policy, Internet Explorer won't check the digital signatures of executable programs or display their identities before downloading them to user computers.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone scripting of web browser controls**  
  This policy setting determines whether a page can control embedded WebBrowser controls via script. If you enable this policy setting, script access to the WebBrowser control is allowed. If you disable this policy setting, script access to the WebBrowser control isn't allowed. If you don't configure this policy setting, the user can enable or disable script access to the WebBrowser control. By default, script access to the WebBrowser control is allowed only in the Local Machine and Intranet zones.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone cross site scripting filter**  
  This policy controls if the Cross-Site Scripting (XSS) Filter will detect and prevent cross-site script injections into websites in this zone. If you enable this policy setting, the XSS Filter is turned on for sites in this zone, and the XSS Filter attempts to block cross-site script injections. If you disable this policy setting, the XSS Filter is turned off for sites in this zone, and Internet Explorer permits cross-site script injections.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone binary and script behaviors**  
  This policy setting allows you to manage dynamic binary and script behaviors: components that encapsulate specific functionality for HTML elements to which they were attached. If you enable this policy setting, binary and script behaviors are available. If you select Administrator approved in the drop-down box, only behaviors listed in the Admin-approved Behaviors under Binary Behaviors Security Restriction policy are available. If you disable this policy setting, binary and script behaviors aren't available unless applications have implemented a custom security manager. If you don't configure this policy setting, binary and script behaviors aren't available unless applications have implemented a custom security manager.
  
  **Default**: Disable  
  
- **Internet Explorer security settings check**  
  This policy setting turns off the Security Settings Check feature, which checks Internet Explorer security settings to determine when the settings put Internet Explorer at risk. If you enable this policy setting, the feature is turned off. If you disable or don't configure this policy setting, the feature is turned on.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone security warning for potentially unsafe files**  
  This policy setting controls if the "Open File - Security Warning" message appears when the user tries to open executable files or other potentially unsafe files (from an intranet file share by using File Explorer, for example). If you enable this policy setting and set the drop-down box to Enable, these files open without a security warning. If you set the drop-down box to Prompt, a security warning appears before the files open. If you disable this policy setting, these files don't open. If you don't configure this policy setting, the user can configure how the computer handles these files. By default, these files are blocked in the Restricted zone, enabled in the Intranet and Local Computer zones, and set to prompt in the Internet and Trusted zones.
  
  **Default**: Prompt  
  
- **Internet Explorer intranet zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to Medium Safety.
  
  **Default**: High safety 
  
- **Internet Explorer block outdated Active X controls**  
  This policy setting determines whether Internet Explorer blocks specific outdated ActiveX controls. Outdated ActiveX controls are never blocked in the Intranet Zone. If you enable this policy setting, Internet Explorer stops blocking outdated ActiveX controls. If you disable or don't configure this policy setting, Internet Explorer continues to block specific outdated ActiveX controls. For more information, see "Outdated ActiveX Controls" in the Internet Explorer TechNet library.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone popup blocker**  
  This policy setting allows you to manage whether unwanted pop-up windows appear. Pop-up windows that are opened when the end user clicks a link aren't blocked. If you enable this policy setting, most unwanted pop-up windows are prevented from appearing. If you disable this policy setting, pop-up windows aren't prevented from appearing. If you don't configure this policy setting, most unwanted pop-up windows are prevented from appearing.
  
  **Default**: Enable  
  
- **Internet Explorer processes MK protocol security restriction**  
  The MK Protocol Security Restriction policy setting reduces attack surface area by preventing the MK protocol. Resources hosted on the MK protocol will fail. If you enable this policy setting, the MK Protocol is prevented for File Explorer and Internet Explorer, and resources hosted on the MK protocol will fail. If you disable this policy setting, applications can use the MK protocol API. Resources hosted on the MK protocol will work for the File Explorer and Internet Explorer processes. If you don't configure this policy setting, the MK Protocol is prevented for File Explorer and Internet Explorer, and resources hosted on the MK protocol will fail.
  
  **Default**: Enabled  
  
- **Internet Explorer trusted zone java permissions**   
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to Low Safety.
  
  **Default**: High safety  
  
- **Internet Explorer restricted zone scripting of java applets**  
  This policy setting allows you to manage whether applets are exposed to scripts within the zone. If you enable this policy setting, scripts can access applets automatically without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow scripts to access applets. If you disable this policy setting, scripts are prevented from accessing applets. If you don't configure this policy setting, scripts are prevented from accessing applets.
  
  **Default**: Disable  
  
- **Internet Explorer locked down restricted zone java permissions**   
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java 
  
- **Internet Explorer internet zone allow only approved domains to use ActiveX controls**   
  This policy setting controls if the user is prompted to allow ActiveX controls to run on websites other than the website that installed the ActiveX control. If you enable this policy setting, the user is prompted before ActiveX controls can run from websites in this zone. The user can choose to allow the control to run from the current site or from all sites. If you disable this policy setting, the user doesn't see the per-site ActiveX prompt, and ActiveX controls can run from all sites in this zone.
  
  **Default**: Enabled  
  
- **Internet Explorer include all network paths**  
  Internet Explorer include all network paths
  
  **Default**: Disabled 
  
- **Internet Explorer internet zone protected mode**  
  This policy setting allows you to turn on Protected Mode. Protected Mode helps protect Internet Explorer from exploited vulnerabilities by reducing the locations that Internet Explorer can write to in the registry and the file system. If you enable this policy setting, Protected Mode is turned on. The user can't turn off Protected Mode. If you disable this policy setting, Protected Mode is turned off. The user can't turn on Protected Mode. If you don't configure this policy setting, the user can turn on or turn off Protected Mode.
  
  **Default**: Enable 
  
- **Internet Explorer internet zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted.
  
  **Default**: Disable 
  
- **Internet Explorer locked down restricted zone smart screen**   
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled  
  
- **Internet Explorer crash detection**  
  This policy setting allows you to manage the crash detection feature of add-on Management. If you enable this policy setting, a crash in Internet Explorer will exhibit behavior found in Windows XP Professional Service Pack 1 and earlier, namely to invoke Windows Error Reporting. All policy settings for Windows Error Reporting continue to apply. If you disable or don't configure this policy setting, the crash detection feature for add-on management is functional.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to High Safety.
  
  **Default**: Disable java  
  
- **Internet Explorer restricted zone active scripting**  
  This policy setting allows you to manage whether script code on pages in the zone is run. If you enable this policy setting, script code on pages in the zone can run automatically. If you select Prompt in the drop-down box, users are queried to choose whether to allow script code on pages in the zone to run. If you disable this policy setting, script code on pages in the zone is prevented from running. If you don't configure this policy setting, script code on pages in the zone is prevented from running.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone logon options**  
  This policy setting allows you to manage settings for sign in options. If you enable this policy setting, you can choose from the following sign in options. Anonymous log on to disable HTTP authentication and use the guest account only for the Common Internet File System (CIFS) protocol. Prompt for user name and password to query users for user IDs and passwords. After a user is queried, these values can be used silently for the remainder of the session. Automatic log on only in Intranet zone to query users for user IDs and passwords in other zones. After a user is queried, these values can be used silently for the rest of the session. Automatic sign in with current user name and password to attempt log on using Windows NT Challenge Response (also known as NTLM authentication). If the server supports Windows NT Challenge Response, the sign in uses the user's network user name and password for log on. If the server doesn't support Windows NT Challenge Response, the user is queried to provide the user name and password. If you disable this policy setting, sign in is set to Automatic log on only in Intranet zone. If you don't configure this policy setting, sign in is set to Automatic sign in only in Intranet zone.
  
  **Default**: Prompt  
  
- **Internet Explorer restricted zone allow vbscript to run**  
  This policy setting allows you to manage whether VBScript can be run on pages from the specified zone in Internet Explorer. If you selected Enable in the drop-down box, VBScript can run without user intervention. If you selected Prompt in the drop-down box, users are asked to choose whether to allow VBScript to run. If you selected Disable in the drop-down box, VBScript is prevented from running. If you don't configure or disable this policy setting, VBScript is prevented from running.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone drag content from different domains across windows**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in different windows. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when both the source and destination are in different windows. Users can't change this setting. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in different windows. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy or don't configure it, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting.
  
  **Default**: Disabled 
  
- **Internet Explorer intranet zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted.
  
  **Default**: Disable 
  
- **Internet Explorer download enclosures**  
  This policy setting prevents the user from having enclosures (file attachments) downloaded from a feed to the user's computer. If you enable this policy setting, the user can't set the Feed Sync Engine to download an enclosure through the Feed property page. A developer can't change the download setting through the Feed APIs. If you disable or don't configure this policy setting, the user can set the Feed Sync Engine to download an enclosure through the Feed property page. A developer can change the download setting through the Feed APIs.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone download unsigned Active X controls**   
  This policy setting allows you to manage whether users may download unsigned ActiveX controls from the zone. Such code is potentially harmful, especially when coming from an untrusted zone. If you enable this policy setting, users can run unsigned controls without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow the unsigned control to run. If you disable this policy setting, users can't run unsigned controls. If you don't configure this policy setting, users can't run unsigned controls.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone drag content from different domains within windows**  
  This policy setting allows you to manage whether users may download unsigned ActiveX controls from the zone. Such code is potentially harmful, especially when coming from an untrusted zone. If you enable this policy setting, users can run unsigned controls without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow the unsigned control to run. If you disable this policy setting, users can't run unsigned controls. If you don't configure this policy setting, users can't run unsigned controls.
  
  **Default**: Disabled  
  
- **Internet Explorer processes restrict Active X install**   
  This policy setting enables applications hosting the Web Browser Control to block automatic prompting of ActiveX control installation. If you enable this policy setting, the Web Browser Control will block automatic prompting of ActiveX control installation for all processes. If you disable or don't configure this policy setting, the Web Browser Control won't block automatic prompting of ActiveX control installation for all processes.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone scriptlets**
  This policy setting allows you to manage whether the user can run scriptlets. If you enable this policy setting, the user can run scriptlets. If you disable this policy setting, the user can't run scriptlets. If you don't configure this policy setting, the user can enable or disable scriptlets.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone drag and drop or copy and paste files**  
  This policy setting allows you to manage whether users can drag files or copy and paste files from a source within the zone. If you enable this policy setting, users can drag files or copy and paste files from this zone automatically. If you select Prompt in the drop-down box, users are queried to choose whether to drag or copy files from this zone. If you disable this policy setting, users are prevented from dragging files or copying and pasting files from this zone. If you don't configure this policy setting, users are queried to choose whether to drag or copy files from this zone.
  
  **Default**: Disable  
  
- **Internet Explorer software when signature is invalid**   
  This policy setting allows you to manage whether software, such as ActiveX controls and file downloads, can be installed or run by the user even though the signature is invalid. An invalid signature might indicate that someone has tampered with the file. If you enable this policy setting, users are prompted to install or run files with an invalid signature. If you disable this policy setting, users can't run or install files with an invalid signature. If you don't configure this policy, users can choose to run or install files with an invalid signature.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone copy and paste via script**   
  This policy setting allows you to manage whether scripts can perform a clipboard operation (for example, cut, copy, and paste) in a specified region. If you enable this policy setting, a script can perform a clipboard operation. If you select Prompt in the drop-down box, users are queried as to whether to perform clipboard operations. If you disable this policy setting, a script can't perform a clipboard operation. If you don't configure this policy setting, a script can't perform a clipboard operation.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone drag content from different domains across windows**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in different windows. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when both the source and destination are in different windows. Users can't change this setting. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in different windows. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy or don't configure it, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting.   
  **Default**: Disabled  
  
- **Internet Explorer users adding sites**  
  Prevents users from adding or removing sites from security zones. A security zone is a group of Web sites with the same security level. If you enable this policy, the site management settings for security zones are disabled. (To see the site management settings for security zones, in the Internet Options dialog box, click the Security tab, and then click the Sites button.) If you disable this policy or don't configure it, users can add Web sites to or remove sites from the Trusted Sites and Restricted Sites zones, and alter settings for the Local Intranet zone. This policy prevents users from changing site management settings for security zones established by the administrator. Note: The "Disable the Security page" policy (located in \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel), which removes the Security tab from the interface, takes precedence over this policy. If it's enabled, this policy is ignored. Also, see the "Security zones: Use only machine settings" policy.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone script initiated windows**  
  This policy setting allows you to manage restrictions on script-initiated pop-up windows and windows that include the title and status bars. If you enable this policy setting, Windows Restrictions security won't apply in this zone. The security zone runs without the added layer of security provided by this feature. If you disable this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process. If you don't configure this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process.
  
  **Default**: Disabled  
  
- **Internet Explorer security zones use only machine settings**  
  Applies security zone information to all users of the same computer. A security zone is a group of Web sites with the same security level. If you enable this policy, changes that the user makes to a security zone will apply to all users of that computer. If you disable this policy or don't configure it, users of the same computer can establish their own security zone settings. Use this policy to ensure that security zone settings apply uniformly to the same computer and don't vary from user to user. Also, see the "Security zones: don't allow users to change policies" policy.
  
  **Default**: Enabled  
  
- **Internet Explorer locked down local machine zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled
  
  **Default**: Disable java 
  
- **Internet Explorer restricted zone do not run antimalware against Active X controls**   
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone run .NET Framework reliant components signed with authenticode**  
  This policy setting allows you to manage whether .NET Framework components that are signed with Authenticode can be executed from Internet Explorer. These components include managed controls referenced from an object tag and managed executables referenced from a link. If you enable this policy setting, Internet Explorer will execute signed managed components. If you select Prompt in the drop-down box, Internet Explorer will prompt the user to determine whether to execute signed managed components. If you disable this policy setting, Internet Explorer won't execute signed managed components. If you don't configure this policy setting, Internet Explorer won't execute signed managed components.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone access to data sources**  
  This policy setting allows you to manage whether Internet Explorer can access data from another security zone using the Microsoft XML Parser (MSXML) or ActiveX Data Objects (ADO). If you enable this policy setting, users can load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you select Prompt in the drop-down box, users are queried to choose whether to allow a page to load in the zone that uses MSXML or ADO to access data from another site in the zone. If you disable this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you don't configure this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone.
  
  **Default**: Disable 
  
- **Internet Explorer internet zone don't run antimalware against ActiveX controls**   
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone copy and paste via script**  
  This policy setting allows you to manage whether scripts can perform a clipboard operation (for example, cut, copy, and paste) in a specified region. If you enable this policy setting, a script can perform a clipboard operation. If you select Prompt in the drop-down box, users are queried as to whether to perform clipboard operations. If you disable this policy setting, a script can't perform a clipboard operation. If you don't configure this policy setting, a script can perform a clipboard operation.
  
  **Default**: Disable  
  
- **Internet Explorer use Active X installer service**   
  This policy setting allows you to specify how ActiveX controls are installed. If you enable this policy setting, ActiveX controls are installed only if the ActiveX Installer Service is present and has been configured to allow the installation of ActiveX controls. If you disable or don't configure this policy setting, ActiveX controls, including per-user controls, are installed through the standard installation process.
  
  **Default**: Enabled  
  
- **Internet Explorer processes protection from zone elevation**  
  Internet Explorer places restrictions on each Web page it opens. The restrictions are dependent upon the location of the Web page (Internet, Intranet, Local Machine zone, and so on). For example, Web pages on the local computer have the fewest security restrictions and are in the Local Machine zone, making the Local Machine security zone a prime target for malicious users. If you enable this policy setting, any zone can be protected from zone elevation for all processes. If you disable or don't configure this policy setting, processes other than Internet Explorer or those listed in the Process List receive no such protection.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone download unsigned ActiveX controls**   
  This policy setting allows you to manage whether users may download unsigned ActiveX controls from the zone. Such code is potentially harmful, especially when coming from an untrusted zone. If you enable this policy setting, users can run unsigned controls without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow the unsigned control to run. If you disable this policy setting, users can't run unsigned controls. If you don't configure this policy setting, users can't run unsigned controls.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone navigate windows and frames across different domains**   
  This policy setting allows you to manage the opening of windows and frames and access of applications across different domains. If you enable this policy setting, users can open windows and frames from other domains and access applications from other domains. If you select Prompt in the drop-down box, users are queried whether to allow windows and frames to access applications from other domains. If you disable this policy setting, users can't open windows and frames to access applications from different domains. If you don't configure this policy setting, users can open windows and frames from other domains and access applications from other domains.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone updates to status bar via script**  
  This policy setting allows you to manage whether a script can update the status bar within the zone. If you enable this policy setting, scripts can update the status bar. If you disable or don't configure this policy setting, script isn't allowed to update the status bar.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone include local path when uploading files to server**  
  This policy setting controls if local path information is sent when the user is uploading a file via an HTML form. If the local path information is sent, some information may be unintentionally revealed to the server. For instance, files sent from the user's desktop may contain the user name as a part of the path. If you enable this policy setting, path information is sent when the user is uploading a file via an HTML form. If you disable this policy setting, path information is removed when the user is uploading a file via an HTML form. If you don't configure this policy setting, the user can choose whether path information is sent when they are uploading a file via an HTML form. By default, path information is sent.
  
  **Default**: Disabled  
  
- **Internet Explorer processes restrict file download**   
  This policy setting enables applications hosting the Web Browser Control to block automatic prompting of file downloads that aren't user initiated. If you enable this policy setting, the Web Browser Control will block automatic prompting of file downloads that aren't user initiated for all processes. If you disable this policy setting, the Web Browser Control won't block automatic prompting of file downloads that aren't user initiated for all processes.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone allow only approved domains to use Active X controls**   
  This policy setting controls if the user is prompted to allow ActiveX controls to run on websites other than the website that installed the ActiveX control. If you enable this policy setting, the user is prompted before ActiveX controls can run from websites in this zone. The user can choose to allow the control to run from the current site or from all sites. If you disable this policy setting, the user doesn't see the per-site ActiveX prompt, and ActiveX controls can run from all sites in this zone.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted.
  
  **Default**: Disable  
  
- **Internet Explorer users changing policies**  
    Prevents users from changing security zone settings. A security zone is a group of Web sites with the same security level. If you enable this policy, the Custom Level button and security-level slider on the Security tab in the Internet Options dialog box are disabled. If you disable this policy or don't configure it, users can change the settings for security zones. This policy prevents users from changing security zone settings established by the administrator. Note: The "Disable the Security page" policy (located in \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel), which removes the Security tab from Internet Explorer in Control Panel, takes precedence over this policy. If it's enabled, this policy is ignored. Also, see the "Security zones: Use only machine settings" policy.
    
  **Default**: Disabled  
  
- **Internet Explorer restricted zone protected mode**  
  This policy setting allows you to turn on Protected Mode. Protected Mode helps protect Internet Explorer from exploited vulnerabilities by reducing the locations that Internet Explorer can write to in the registry and the file system. If you enable this policy setting, Protected Mode is turned on. The user can't turn off Protected Mode. If you disable this policy setting, Protected Mode is turned off. The user can't turn on Protected Mode. If you don't configure this policy setting, the user can turn on or turn off Protected Mode.
  
  **Default**: Enable  
  
- **Internet Explorer internet zone user data persistence**  
  This policy setting allows you to manage the preservation of information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. When a user returns to a persisted page, the state of the page can be restored if this policy setting is appropriately configured. If you enable this policy setting, users can preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you disable this policy setting, users can't preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you don't configure this policy setting, users can preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone scripting of web browser controls**  
 
  This policy setting determines whether a page can control embedded WebBrowser controls via script. If you enable this policy setting, script access to the WebBrowser control is allowed. If you disable this policy setting, script access to the WebBrowser control isn't allowed. If you don't configure this policy setting, the user can enable or disable script access to the WebBrowser control. By default, script access to the WebBrowser control is allowed only in the Local Machine and Intranet zones.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone user data persistence**  
    This policy setting allows you to manage the preservation of information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. When a user returns to a persisted page, the state of the page can be restored if this policy setting is appropriately configured. If you enable this policy setting, users can preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you disable this policy setting, users can't preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you don't configure this policy setting, users can't preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk.  
  
  **Default**: Disabled  
  
- **Internet Explorer locked down intranet zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java  
  
- **Internet Explorer enhanced protected mode**  
  Enhanced Protected Mode provides additional protection against malicious websites by using 64-bit processes on 64-bit versions of Windows. For computers running at least Windows 8, Enhanced Protected Mode also limits the locations Internet Explorer can read from in the registry and the file system. If you enable this policy setting, Enhanced Protected Mode is turned on. Any zone that has Protected Mode enabled will use Enhanced Protected Mode. Users won't be able to disable Enhanced Protected Mode. If you disable this policy setting, Enhanced Protected Mode is turned off. Any zone that has Protected Mode enabled will use the version of Protected Mode introduced in Internet Explorer 7 for Windows Vista. If you don't configure this policy, users can turn on or turn off Enhanced Protected Mode on the Advanced tab of the Internet Options dialog.
  
  **Default**: Enabled  
  
- **Internet Explorer bypass smart screen warnings**  
  This policy setting determines whether the user can bypass warnings from SmartScreen Filter. SmartScreen Filter warns the user about executable files that Internet Explorer users don't commonly download from the Internet. If you enable this policy setting, SmartScreen Filter warnings block the user. If you disable or don't configure this policy setting, the user can bypass SmartScreen Filter warnings.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone meta refresh**  
  This policy setting allows you to manage whether a user's browser can be redirected to another Web page if the author of the Web page uses the Meta Refresh setting (tag) to redirect browsers to another Web page. If you enable this policy setting, a user's browser that loads a page containing an active Meta Refresh setting can be redirected to another Web page. If you disable this policy setting, a user's browser that loads a page containing an active Meta Refresh setting can't be redirected to another Web page. If you don't configure this policy setting, a user's browser that loads a page containing an active Meta Refresh setting can't be redirected to another Web page.
  
  **Default**: Disabled  
  
## Local Policies Security Options
For more information, see [Policy CSP - LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) in the Windows documentation. 

- **Restrict anonymous access to named pipes and shares**  
  When enabled, this security setting restricts anonymous access to shares and pipes to the settings for: (1) Named pipes that can be accessed anonymously (2) Shares that can be accessed anonymously
  
  **Default**: Yes  
  
- **Minimum session security for NTLM SSP based servers**  
  This security setting allows a server to require the negotiation of 128-bit encryption and/or NTLMv2 session security. These values are dependent on the LAN Manager Authentication Level security setting value. The options are: Require NTLMv2 session security: The connection will fail if message integrity isn't negotiated. Require 128-bit encryption. The connection will fail if strong encryption (128-bit) isn't negotiated.
  
  **Default**: Require NTLM V2 and 128 bit encryption  
  
- **Minutes of lock screen inactivity until screen saver activates**  
  Windows notices inactivity of a logon session, and if the amount of inactive time exceeds the inactivity limit, then the screen saver will run, locking the session.
  
  **Default**: 15
  
- **Require client to always digitally sign communications** 
  This security setting determines whether all secure channel traffic initiated by the domain member must be signed or encrypted. When a computer joins a domain, a computer account is created. After that, when the system starts, it uses the computer account password to create a secure channel with a domain controller for its domain. This secure channel is used to perform operations such as NTLM pass through authentication, LSA SID/name Lookup and more. This setting determines if all secure channel traffic initiated by the domain member meets minimum security requirements. Specifically it determines whether all secure channel traffic started by the domain member must be signed or encrypted. If this policy is enabled, then the secure channel won't be established unless either signing or encryption of all secure channel traffic is negotiated. If this policy is disabled, then encryption and signing of all secure channel traffic is negotiated with the Domain Controller in which case the level of signing and encryption depends on the version of the Domain Controller and the settings of the following two policies: Domain member: Digitally encrypt secure channel data (when possible) Domain member: Digitally sign secure channel data (when possible)
  
  **Default**: Yes
  
- **Authentication level**  
  This security setting determines which challenge/response authentication protocol is used for network logons. This choice affects the level of authentication protocol used by clients, the level of session security negotiated, and the level of authentication accepted by servers as follows:  
  - *Send LM and NTLM responses*: Clients use LM and NTLM authentication and never use NTLMv2 session security; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send LM and NTLM - NTLMv2 if negotiated*: Clients use LM and NTLM authentication and use NTLMv2 session security if the server supports it; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send NTLM response only*: Clients use NTLM authentication only and use NTLMv2 session security if the server supports it; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send NTLMv2 response only*: Clients use NTLMv2 authentication only and use NTLMv2 session security if the server supports it; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send NTLMv2 response only. Refuse LM*: Clients use NTLMv2 authentication only and use NTLMv2 session security if the server supports it; domain controllers refuse LM (accept only NTLM and NTLMv2 authentication). 
  - *Send NTLMv2 response only. Refuse LM and NTLM*: Clients use NTLMv2 authentication only and use NTLMv2 session security if the server supports it; domain controllers refuse LM and NTLM (accept only NTLMv2 authentication). 
    
  **Default**: Send NTLMv2 response only. Refuse LM and NTLM
  
- **Prevent clients from sending unencrypted passwords to third party SMB servers**  
  If this security setting is enabled, the Server Message Block (SMB) redirector can send plaintext passwords to non-Microsoft SMB servers that don't support password encryption during authentication. Sending unencrypted passwords is a security risk.
  
  **Default**: Yes
  
- **Disable server digitally signing communications always**  
  This security setting determines whether the SMB client attempts to negotiate SMB packet signing. The server message block (SMB) protocol provides the basis for Microsoft file and print sharing and many other networking operations, such as remote Windows administration. To prevent man-in-the-middle attacks that modify SMB packets in transit, the SMB protocol supports the digital signing of SMB packets. This policy setting determines whether the SMB client component attempts to negotiate SMB packet signing when it connects to an SMB server. If this setting is enabled, the Microsoft network client will ask the server to perform SMB packet signing upon session setup. If packet signing has been enabled on the server, packet signing is negotiated. If this policy is disabled, the SMB client will never negotiate SMB packet signing.
  
  **Default**: Yes
  
- **Administrator elevation prompt behavior**  
  This policy setting controls the behavior of the elevation prompt for administrators. The options are: 
    - *Elevate without prompting*: Allows privileged accounts to perform an operation that requires elevation without requiring consent or credentials. Note: Use this option only in the most constrained environments. 
    - *Prompt for credentials on the secure desktop*: When an operation requires elevation of privilege, the user is prompted on the secure desktop to enter a privileged user name and password. If the user enters valid credentials, the operation continues with the user's highest available privilege. 
    - *Prompt for consent on the secure desktop*: When an operation requires elevation of privilege, the user is prompted on the secure desktop to select either Permit or Deny. If the user selects Permit, the operation continues with the user's highest available privilege. 
    - *Prompt for credentials*: When an operation requires elevation of privilege, the user is prompted to enter an administrative user name and password. If the user enters valid credentials, the operation continues with the applicable privilege. 
    - *Prompt for consent*: When an operation requires elevation of privilege, the user is prompted to select either Permit or Deny. If the user selects Permit, the operation continues with the user's highest available privilege.  
    - *Prompt for consent for non-Windows binaries*: When an operation for a non-Microsoft application requires elevation of privilege, the user is prompted on the secure desktop to select either Permit or Deny. If the user selects Permit, the operation continues with the user's highest available privilege.   
  
  **Default**: Prompt for consent on the secure desktop
  
- **Minimum session security for NTLM SSP based clients**  
  This security setting allows a client to require the negotiation of 128-bit encryption and/or NTLMv2 session security. These values are dependent on the LAN Manager Authentication Level security setting value. The options are:
  - Require NTLMv2 session security: The connection will fail if NTLMv2 protocol isn't negotiated. 
  - *Require 128-bit encryption*: The connection will fail if strong encryption (128-bit) isn't negotiated.
  - *Require NTLMv2 and 128-bit encryption*. 

  **Default**: Require NTLM V2 128 encryption
  
- **Smart card removal behavior**  
    This security setting determines what happens when the smart card for a logged-on user is removed from the smart card reader. The options are:
     - *No action*. 
     - *Lock Workstation* - The workstation is locked when the smart card is removed, allowing users to leave the area, take their smart card with them, and still maintain a protected session.
     - *Force Logoff* - the user is automatically logged off when the smart card is removed.
     - *Disconnect Remote Desktop session* - Removal of the smart card disconnects the session without logging the user off. This allows the user to insert the smart card and resume the session later, or at another smart card reader-equipped computer, without having to log on again. If the session is local, this policy functions identically to Lock Workstation.   
    
  **Default**: Lock workstation
  
- **Block anonymous enumeration of SAM accounts and shares**  
  This security setting determines whether to allow anonymous enumeration of SAM accounts and shares. Windows allows anonymous users to perform certain activities, such as enumerating the names of domain accounts and network shares. This is convenient, for example, when an administrator wants to grant access to users in a trusted domain that doesn't maintain a reciprocal trust. If you don't want to allow anonymous enumeration of SAM accounts and shares, then set this policy to *Yes*.
  
  **Default**: Yes
  
- **Block remote logon with blank password**  
  This security setting determines whether local accounts that aren't password protected can be used to log on from locations other than the physical computer console. If enabled, local accounts that aren't password protected must use the computer's keyboard to log on. 

  *Warning*: Computers that aren't in physically secure locations should always enforce strong password policies for all local user accounts. Otherwise, anyone with physical access to the computer can log on by using a user account that doesn't have a password. This is especially important for portable computers. 

  If you apply this security policy to the Everyone group, no one can log on through Remote Desktop Services. This setting doesn't affect logons that use domain accounts. It's possible for applications that use remote interactive logons to bypass this setting.
  
  **Default**: Yes
  
- **Standard user elevation prompt behavior**  
  This policy setting controls the behavior of the elevation prompt for standard users. 
  - *Automatically deny elevation requests*: When an operation requires elevation of privilege, a configurable access denied error message is displayed. An enterprise that is running desktops as standard user may choose this setting to reduce help desk calls. 
  - *Prompt for credentials on the secure desktop*: When an operation requires elevation of privilege, the user is prompted on the secure desktop to enter a different user name and password. If the user enters valid credentials, the operation continues with the applicable privilege. 
  - *Prompt for credentials*: When an operation requires elevation of privilege, the user is prompted to enter an administrative user name and password. If the user enters valid credentials, the operation continues with the applicable privilege.  
  
  **Default**: Automatically deny elevation requests
  
- **Require admin approval mode for administrators**  
  This policy setting controls the behavior of all User Account Control (UAC) policy settings for the computer. If you change this policy setting, you must restart your computer. The options are:   
  - *Not configured*: Admin Approval Mode and all related UAC policy settings are disabled. Note: If this policy setting is disabled, the Security Center notifies you that the overall security of the operating system has been reduced. 
  - *Yes*: Admin Approval Mode is enabled. This policy must be enabled and related UAC policy settings must be set appropriately to allow the built-in Administrator account and all other users who are members of the Administrators group to run in Admin Approval Mode.  
  
  **Default**: Yes
  
- **Prevent anonymous enumeration of SAM accounts**  
  This security setting determines what additional permissions are granted for anonymous connections to the computer. Windows allows anonymous users to perform certain activities, such as enumerating the names of domain accounts and network shares. This is convenient, for example, when an administrator wants to grant access to users in a trusted domain that doesn't maintain a reciprocal trust. This security option allows additional restrictions to be placed on anonymous connections as follows: 
  - *Yes*: Don't allow enumeration of SAM accounts. This option replaces Everyone with Authenticated Users in the security permissions for resources.
  - *Not configured*: No additional restrictions. Rely on default permissions.  
  
  **Default**: Yes
  
- **Allow remote calls to security accounts manager**  
  This policy setting allows you to restrict remote rpc connections to SAM. If not selected, the default security descriptor is used.
  
  **Default**: *O:BAG:BAD:(A;;RC;;;BA)*

- **Use admin approval mode**  
  This policy setting controls the behavior of Admin Approval Mode for the built-in Administrator account. The options are: 
  - *Yes*: The built-in Administrator account uses Admin Approval Mode. By default, any operation that requires elevation of privilege will prompt the user to approve the operation. 
  - *Not Configured*: The built-in Administrator account runs all applications with full administrative privilege.  

  **Default**: Yes
  
- **Allow UI access applications for secure locations**  
  This policy setting controls whether User Interface Accessibility (UIAccess or UIA) programs can automatically disable the secure desktop for elevation prompts used by a standard user. 
  - *Yes*: UIA programs, including Windows Remote Assistance, automatically disable the secure desktop for elevation prompts. If you don't disable the "User Account Control: Switch to the secure desktop when prompting for elevation" policy setting, the prompts appear on the interactive user's desktop instead of the secure desktop. 
  - *Not Configured*: The secure desktop can be disabled only by the user of the interactive desktop or by disabling the "User Account Control: Switch to the secure desktop when prompting for elevation" policy setting.  

  **Default**: Yes

- **Detect application installations and prompt for elevation**  
  This policy setting controls the behavior of application installation detection for the computer. The options are: 
  - *Enabled*: When an application installation package is detected that requires elevation of privilege, the user is prompted to enter an administrative user name and password. If the user enters valid credentials, the operation continues with the applicable privilege. 
  - *Disabled*: Application installation packages aren't detected and prompted for elevation. Enterprises that are running standard user desktops and use delegated installation technologies such as Group Policy Software Installation or Systems Management Server (SMS) should disable this policy setting. In this case, installer detection is unnecessary.  
  
  **Default**: Yes
  
- **Prevent storing LAN manager hash value on next password change**  
  This security setting determines if, at the next password change, the LAN Manager (LM) hash value for the new password is stored. The LM hash is relatively weak and prone to attack, as compared with the cryptographically stronger Windows NT hash. Since the LM hash is stored on the local computer in the security database the passwords can be compromised if the security database is attacked.
  
  **Default**: Yes

- **Virtualize file and registry write failures to per user locations**  
  This policy setting controls whether application write failures are redirected to defined registry and file system locations. This policy setting mitigates applications that run as administrator and write run-time application data to *%ProgramFiles%*, *%Windir%*, *%Windir%\system32*, or *HKLM\Software*.
  
  **Default**: Yes

## MS Security Guide  
For more information, see [Policy CSP - MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) in the Windows documentation.  

- **Apply UAC restrictions to local accounts on network logon**  
  **Default**: Enabled
  
- **SMB v1 client driver start configuration**  
  **Default**: Disabled driver
  
- **SMB v1 server**  
  **Default**: Disabled
  
- **Digest authentication**  
  **Default**: Disabled
  
- **Structured exception handling overwrite protection**  
  **Default**: Enabled
  
## MSS Legacy  
For more information, see [Policy CSP - MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) in the Windows documentation.  

- **Network IP source routing protection level**  
  **Default**: Highest protection  
  
- **Network ignore NetBIOS name release requests except from WINS servers**  
  **Default**: Enabled
  
- **Network IPv6 source routing protection level**  
  **Default**: Highest protection

- **Network ICMP redirects override OSPF generated**  
  **Default**: Disabled
  
## Power  
For more information, see [Policy CSP - Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) in the Windows documentation.  

- **Require password on wake while plugged in**  
  This policy setting specifies if the user is prompted for a password when the system resumes from sleep. If you enable or don't configure this policy setting, the user is prompted for a password when the system resumes from sleep. If you disable this policy setting, the user isn't prompted for a password when the system resumes from sleep.
  
  **Default**: Enabled
  
- **Standby states when sleeping while on battery**  
  This policy setting manages if Windows can use standby states when putting the computer in a sleep state. If you enable or don't configure this policy setting, Windows uses standby states to put the computer in a sleep state. If you disable this policy setting, standby states (S1-S3) aren't allowed.
  
  **Default**: Disabled
  
- **Standby states when sleeping while plugged in**  
  This policy setting manages if Windows can use standby states when putting the computer in a sleep state. If you enable or don't configure this policy setting, Windows uses standby states to put the computer in a sleep state. If you disable this policy setting, standby states (S1-S3) aren't allowed.
  
  **Default**: Disabled
  
- **Require password on wake while on battery**  
  This policy setting specifies if the user is prompted for a password when the system resumes from sleep. If you enable or don't configure this policy setting, the user is prompted for a password when the system resumes from sleep. If you disable this policy setting, the user isn't prompted for a password when the system resumes from sleep.
  
  **Default**: Enabled
  
## Remote Desktop Services  
For more information, see [Policy CSP - RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) in the Windows documentation.  

- **Block password saving**  
  Controls whether passwords can be saved on this computer from Remote Desktop Connection. If you enable this setting the password saving checkbox in Remote Desktop Connection is disabled and users won't be able to save passwords. When a user opens an RDP file using Remote Desktop Connection and saves their settings, any password that previously existed in the RDP file are deleted. If you disable this setting or leave it not configured, the user can save passwords using Remote Desktop Connection.
  
   **Default**: Enabled
  
- **Secure RPC communication**  
  Specifies whether a Remote Desktop Session Host server requires secure RPC communication with all clients or allows unsecured communication. You can use this setting to strengthen the security of RPC communication with clients by allowing only authenticated and encrypted requests. If the status is set to Enabled, Remote Desktop Services accepts requests from RPC clients that support secure requests, and doesn't allow unsecured communication with untrusted clients. If the status is set to Disabled, Remote Desktop Services always requests security for all RPC traffic. However, unsecured communication is allowed for RPC clients that don't respond to the request. If the status is set to Not Configured, unsecured communication is allowed. Note: The RPC interface is used for administering and configuring Remote Desktop Services.
  
  **Default**: Enabled
  
- **Block drive redirection**  
  This policy setting specifies whether to prevent the mapping of client drives in a Remote Desktop Services session (drive redirection). By default, an RD Session Host server maps client drives automatically upon connection. Mapped drives appear in the session folder tree in File Explorer or Computer in the format *\<driveletter>* on *\<computername>*. You can use this policy setting to override this behavior. If you enable this policy setting, client drive redirection isn't allowed in Remote Desktop Services sessions, and Clipboard file copy redirection isn't allowed on computers running Windows Server 2003, Windows 8, and Windows XP. If you disable this policy setting, client drive redirection is always allowed. Also, Clipboard file copy redirection is always allowed if Clipboard redirection is allowed. If you don't configure this policy setting, client drive redirection and Clipboard file copy redirection aren't specified at the Group Policy level.
  
  **Default**: Enabled
  
- **Prompt for password upon connection**  
  This policy setting specifies whether Remote Desktop Services always prompts the client for a password upon connection. You can use this setting to enforce a password prompt for users logging on to Remote Desktop Services, even if they already provided the password in the Remote Desktop Connection client. By default, Remote Desktop Services allows users to automatically log on by entering a password in the Remote Desktop Connection client. If you enable this policy setting, users can't automatically log on to Remote Desktop Services by supplying their passwords in the Remote Desktop Connection client. they're prompted for a password to log on. If you disable this policy setting, users can always log on to Remote Desktop Services automatically by supplying their passwords in the Remote Desktop Connection client. If you don't configure this policy setting, automatic logon isn't specified at the Group Policy level. 
  
  **Default**: Enabled
  
- **Remote desktop services client connection encryption level**  
  Specifies whether to require the use of a specific encryption level to secure communications between client computers and RD Session Host servers during Remote Desktop Protocol (RDP) connections. This policy only applies when you're using native RDP encryption. However, native RDP encryption (as opposed to SSL encryption) isn't recommended. This policy doesn't apply to SSL encryption. If you enable this policy setting, all communications between clients and RD Session Host servers during remote connections must use the encryption method specified in this setting. By default, the encryption level is set to High. The following encryption methods are available:  
  - *High*: The High setting encrypts data sent from the client to the server and from the server to the client by using strong 128-bit encryption. Use this encryption level in environments that contain only 128-bit clients (for example, clients that run Remote Desktop Connection). Clients that don't support this encryption level can't connect to RD Session Host servers.  
  - *Client Compatible*: The Client Compatible setting encrypts data sent between the client and the server at the maximum key strength supported by the client. Use this encryption level in environments that include clients that don't support 128-bit encryption.  
  - *Low*: The Low setting encrypts only data sent from the client to the server by using 56-bit encryption.  
  
  If you disable or don't configure this setting, the encryption level to be used for remote connections to RD Session Host servers isn't enforced through Group Policy. Important FIPS compliance can be configured through the System cryptography. Use FIPS-compliant algorithms for encryption, hashing, and signing settings in Group Policy (under Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options.) The FIPS-compliant setting encrypts and decrypts data sent from the client to the server and from the server to the client, with the Federal Information Processing Standard (FIPS) 140 encryption algorithms, by using Microsoft cryptographic modules. Use this encryption level when communications between clients and RD Session Host servers requires the highest level of encryption.
  
  **Default**: High
  
## Remote Management  
For more information, see [Policy CSP - RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) in the Windows documentation.  

- **Block storing run as credentials**  
  Client basic authentication
  
  **Default**: Enabled
  
- **Basic authentication**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) service accepts Basic authentication from a remote client. If you enable this policy setting, the WinRM service accepts Basic authentication from a remote client. If you disable or don't configure this policy setting, the WinRM service doesn't accept Basic authentication from a remote client.
  
  **Default**: Disabled
  
- **Block client digest authentication**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) client uses Digest authentication. If you enable this policy setting, the WinRM client doesn't use Digest authentication. If you disable or don't configure this policy setting, the WinRM client uses Digest authentication.
  
  **Default**: Enabled
  
- **Unencrypted traffic**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) service sends and receives unencrypted messages over the network. If you enable this policy setting, the WinRM client sends and receives unencrypted messages over the network. If you disable or don't configure this policy setting, the WinRM client sends or receives only encrypted messages over the network.  
  
  **Default**: Disabled
  
- **Client unencrypted traffic**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) client sends and receives unencrypted messages over the network. If you enable this policy setting, the WinRM client sends and receives unencrypted messages over the network. If you disable or don't configure this policy setting, the WinRM client sends or receives only encrypted messages over the network.
  
  **Default**: Disabled
  
- **Client basic authentication**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) client uses Basic authentication. If you enable this policy setting, the WinRM client uses Basic authentication. If WinRM is configured to use HTTP transport, the user name and password are sent over the network as clear text. If you disable or don't configure this policy setting, the WinRM client doesn't use Basic authentication.
  
  **Default**: Disabled
  

## Remote Procedure Call  
For more information, see [Policy CSP - RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) in the Windows documentation.  

- **RPC unauthenticated client options**  
  This policy setting controls how the RPC server runtime handles unauthenticated RPC clients connecting to RPC servers. This policy setting impacts all RPC applications. In a domain environment, use this policy setting with caution as it can impact a wide range of functionality including group policy processing itself. Reverting a change to this policy setting can require manual intervention on each affected machine. This policy setting should never be applied to a domain controller. If you disable this policy setting, the RPC server runtime uses the value of "Authenticated" on Windows Client, and the value of "None" on Windows Server versions that support this policy setting. If you don't configure this policy setting, it remains disabled. The RPC server runtime behaves as though it was enabled with the value of "Authenticated" used for Windows Client and the value of "None" used for Server SKUs that support this policy setting. If you enable this policy setting, it directs the RPC server runtime to restrict unauthenticated RPC clients connecting to RPC servers running on a machine. A client is considered an authenticated client if it uses a named pipe to communicate with the server or if it uses RPC Security. RPC Interfaces that have specifically requested to be accessible by unauthenticated clients may be exempt from this restriction, depending on the selected value for this policy setting.  
  - *None* allows all RPC clients to connect to RPC Servers running on the machine on which the policy setting is applied. 
  - *Authenticated* allows only authenticated RPC Clients (per the definition above) to connect to RPC Servers running on the machine on which the policy setting is applied. Exemptions are granted to interfaces that have requested them. 
  - *Authenticated without exceptions* allows only authenticated RPC Clients (per the definition above) to connect to RPC Servers running on the machine on which the policy setting is applied. No exceptions are allowed. Note: This policy setting won't be applied until the system is rebooted.  

  **Default**: Authenticated

## Search 
For more information, see [Policy CSP - Search](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) in the Windows documentation.  

- **Disable indexing encrypted items**  
  Allows or disallows the indexing of items. This switch is for the Windows Search Indexer, which controls whether it will index items that are encrypted, such as the Windows Information Protection (WIP) protected files. When the policy is enabled, WIP protected items are indexed and the metadata about them are stored in an unencrypted location. The metadata includes things like file path and date modified. When the policy is disabled, the WIP protected items aren't indexed and don't show up in the results in Cortana or file explorer. There may also be a performance impact on photos and Groove apps if there are many WIP protected media files on the device.
  
**Default**: Yes
  
## Smart Screen  
For more information, see [Policy CSP - SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) in the Windows documentation.  

- **Block execution of unverified files**  
  Block user from running unverified files. 
  - *Not Configured* - Employees can ignore SmartScreen warnings and run malicious files. 
  - *Yes* – Employees can't ignore SmartScreen warnings and run malicious files.

  **Default**: Yes

- **Require SmartScreen for apps and files**  
  Allows IT Admins to configure SmartScreen for Windows.

  **Default**: Yes
  
## System  
For more information, see [Policy CSP - System](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) in the Windows documentation.  

- **System boot start driver initialization**  
  This policy setting allows you to specify which boot-start drivers are initialized based on a classification determined by an Early Launch Antimalware boot-start driver. The Early Launch Antimalware boot-start driver can return the following classifications for each boot-start driver: 
  - *Good*: The driver has been signed and hasn't been tampered with.  
  - *Bad* - The driver has been identified as malware. We recommend that you don't allow known bad drivers to be initialized. 
  - *Bad, but required for boot*: The driver has been identified as malware, but the computer can't successfully boot without loading this driver. 
  - *Unknown* - This driver hasn't been attested to by your malware detection application and hasn't been classified by the Early Launch Antimalware boot-start driver.  

  If you enable this policy setting, you can choose which boot-start drivers to initialize the next time the computer is started. If you disable or don't configure this policy setting, the boot start drivers determined to be Good, Unknown, or Bad but Boot Critical are initialized and the initialization of drivers determined to be Bad is skipped. If your malware detection application doesn't include an Early Launch Antimalware boot-start driver or if your Early Launch Antimalware boot-start driver has been disabled, this setting has no effect and all boot-start drivers are initialized.  
  
  **Default**: Good unknown and bad critical


## Wi-Fi  
For more information, see [Policy CSP - Wifi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) in the Windows documentation.  

- **Block Internet sharing**  
  Specifies whether internet sharing is possible on the device.  

  **Default**: Yes  

- **Block Automatically connecting to Wi-Fi hotspots**  
  Allow or disallow the device to automatically connect to Wi-Fi hotspots.  

  **Default**: Yes  
  
## Windows Connection Manager  
For more information, see [Policy CSP - WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) in the Windows documentation.  

- **Block connection to non-domain networks**  
  This policy setting prevents computers from connecting to both a domain-based network and a non-domain based network at the same time. If this policy setting is enabled, the computer responds to automatic and manual network connection attempts based on the following circumstances: 
  - Automatic connection attempts When the computer is already connected to a domain-based network, all automatic connection attempts to non-domain networks are blocked. When the computer is already connected to a non-domain based network, automatic connection attempts to domain-based networks are blocked. 
  - Manual connection attempts When the computer is already connected to either a non-domain based network or a domain-based network over media other than Ethernet, and a user attempts to create a manual connection to an additional network in violation of this policy setting, the existing network connection disconnects and the manual connection is allowed. When the computer is already connected to either a non-domain based network or a domain-based network over Ethernet, and a user attempts to create a manual connection to an additional network in violation of this policy setting, the existing Ethernet connection is maintained and the manual connection attempt is blocked.  

  If this policy setting isn't configured or is disabled, computers are allowed to connect simultaneously to both domain and non-domain networks.  

  **Default**: Enabled
  
## Microsoft Defender  
For more information, see [Policy CSP - Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) in the Windows documentation.  

- **Scan incoming mail messages**  
  Allows or disallows scanning of email.
  
  **Default**: Yes  

- **Office apps launch child process type**  
  Office apps won't be allowed to create child processes. This includes Word, Excel, PowerPoint, OneNote, and Access. This is a typical malware behavior, especially for macro-based attacks that attempt to use Office apps to launch or download malicious executables.
  
  **Default**: Block
  
- **Defender sample submission consent type**  
  Checks for the user consent level in WinMMicrosofticrosoftdows Defender to send data. If the required consent has already been granted, Microsoft Defender submits them. If not, (and if the user has specified never to ask), the UI is launched to ask for user consent (when Defender/AllowCloudProtection is allowed) before sending data.
  
  **Default**: Send safe samples automatically 
  
- **Signature update interval (in hours)**  
  Defender signature update interval in hours
  
  **Default**: 4
  
- **Script downloaded payload execution type**  
  Defender script downloaded payload execution type
  
  **Default**: Block
  
- **Prevent credential stealing type**  
  Microsoft Defender Credential Guard uses virtualization-based security to isolate secrets so that only privileged system software can access them. Unauthorized access to these secrets can lead to credential theft attacks, such as Pass-the-Hash or Pass-The-Ticket. Microsoft Defender Credential Guard prevents these attacks by protecting NTLM password hashes, Kerberos Ticket Granting Tickets, and credentials stored by applications as domain credentials.
  
  **Default**: Enable

- **Email content execution type**  
  This rule blocks the following file types from being run or launched from an email seen in either Microsoft Outlook or webmail (such as Gmail.com or Outlook.com): Executable files (such as .exe, .dll, or .scr) Script files (such as a PowerShell .ps, VisualBasic .vbs, or JavaScript .js file) Script archive files.
  
  **Default**: Block
  
- **Network protection type**  
  This policy allows you to turn on network protection (block/audit) or off in Microsoft Defender Exploit Guard. Network protection is a feature of Microsoft Defender Exploit Guard that protects employees using any app from accessing phishing scams, exploit-hosting sites, and malicious content on the Internet. This includes preventing third-party browsers from connecting to dangerous sites. Value type is integer. If you enable this setting, network protection is turned on and employees can't turn it off. Its behavior can be controlled by the following options: Block and Audit. If you enable this policy with the "Block" option, users and apps are blocked from connecting to dangerous domains. You can see this activity in Microsoft Defender Security Center. If you enable this policy with the "Audit" option, users/apps won't be blocked from connecting to dangerous domains. However, you'll still see this activity in Microsoft Defender Security Center. If you disable this policy, users/apps won't be blocked from connecting to dangerous domains. You'll not see any network activity in Microsoft Defender Security Center. If you don't configure this policy, network blocking is disabled by default.
  
  **Default**: Enable
  
- **Defender schedule scan day**  
  Defender schedule scan day.
  
  **Default**: Everyday
  
- **Cloud-delivered protection**  
  To best protect your PC, Microsoft Defender will send information to Microsoft about any problems it finds. Microsoft will analyze that information, learn more about problems affecting you and other customers, and offer improved solutions.
  
  **Default**:  Yes  

- **Defender potentially unwanted app action**  
  The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can identify and block PUAs from downloading and installing on endpoints in your network. These applications aren't considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use. PUA can also refer to applications that are considered to have a poor reputation. Typical PUA behavior includes: Various types of software bundling Ad injection into web browsers Driver and registry optimizers that detect issues, request payment to fix the errors, but remain on the endpoint and make no changes or optimizations (also known as "rogue antivirus" programs). These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.  
  
  **Default**: Block  

- **Script obfuscated macro code type**  
  Malware and other threats can attempt to obfuscate or hide their malicious code in some script files. This rule prevents scripts that appear to be obfuscated from running.
  
  **Default**: Block
  
- **Scan removable drives during a full scan**  
  Allows Microsoft Defender to scan for malicious and unwanted software in removable drives (for example, flash drives) during a full scan. Microsoft Defender Antivirus scans all files on USB devices before execution.
  
  **Default**: Yes  
  
- **Scan archive files**  
  Defender scan archive files.
  
  **Default**: Yes
  
- **Behavior monitoring**  
  Allows or disallows Microsoft Defender Behavior Monitoring functionality.Embedded in Windows 10, these sensors collect and process behavioral signals from the operating system and sends this sensor data to your private, isolated, cloud instance of Microsoft Defender ATP.
  
  **Default**: Yes

- **Scan files opened from network folders**  
  If files are read-only, user won't be able to remove any detected malware.
  
  **Default**: Yes

- **Untrusted USB process type**  
  With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.
  
  **Default**: Block
  
- **Office apps other process injection type**  
  Office apps, including Word, Excel, PowerPoint, and OneNote, won't be able to inject code into other processes. This is typically used by malware to run malicious code in an attempt to hide the activity from antivirus scanning engines.
  
  **Default**:  Block
  
- **Office macro code allow Win32 imports type**  
  Malware can use macro code in Office files to import and load Win32 DLLs, which can then be used to make API calls to allow further infection throughout the system. This rule attempts to block Office files that contain macro code that is capable of importing Win32 DLLs. This includes Word, Excel, PowerPoint, and OneNote.
  
  **Default**: Block  
  
- **Defender cloud block level**  
  Defender cloud block level.
  
  **Default**: Not Configured

- **Real-time monitoring**  
  Defender requires real-time monitoring.
  
  **Default**: Yes
  
- **Office apps executable content creation or launch type**  
  This rule targets typical behaviors used by suspicious and malicious add-ons and scripts (extensions) that create or launch executable files. This is a typical malware technique. Extensions are blocked from being used by Office apps. Typically these extensions use the Windows Scripting Host (.wsh files) to run scripts that automate certain tasks or provide user-created add-on features
  
  **Default**: Block

## Windows Ink Workspace  
For more information, see [Policy CSP - WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) in the Windows documentation.  

- **Ink Workspace**  
  Specifies whether to allow the user to access the ink workspace. 
  - *Disabled* - access to ink workspace is disabled. The feature is turned off.
  - *Enabled* - The Ink Workspace feature is turned on, but the user can't access it above the lock screen.
  - *Not Configured* - The Ink Workspace feature is turned on, and the user can use it above the lock screen.  

  **Default**: Enabled
 
## Windows PowerShell  
For more information, see [Policy CSP - WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) in the Windows documentation.  

- **Power shell shell script block logging**  
  This policy setting enables logging of all PowerShell script input to the Microsoft-Windows-PowerShell/Operational event log. If you enable this policy setting, Windows PowerShell will log the processing of commands, script blocks, functions, and scripts - whether invoked interactively, or through automation. If you disable this policy setting, logging of PowerShell script input is disabled. If you enable the Script Block Invocation Logging, PowerShell additionally logs events when invocation of a command, script block, function, or script starts or stops. Enabling Invocation Logging generates a high volume of event logs. Note: This policy setting exists under both Computer Configuration and User Configuration in the Group Policy Editor. The Computer Configuration policy setting takes precedence over the User Configuration policy setting.
  
  **Default**: Enabled
 

End of PReview baseilne list  -->
