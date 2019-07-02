---
title: Nastavení směrné plány zabezpečení Intune pro Windows 10
titleSuffix: Microsoft Intune
description: Základní nastavení zabezpečení Intune pro správu systému Windows 10
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/20/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 56e1a1e07a403afa4db405d276c55be1ef8ddfd8
ms.sourcegitcommit: 116ef72b9da4d114782d4b8dd9f57556c9b01511
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2019
ms.locfileid: "67494555"
---
# <a name="mdm-security-baseline-settings-for-intune"></a>Základní nastavení zabezpečení MDM Intune  

Zobrazte nastavení standardních hodnot zabezpečení MDM, které jsou podporované v Microsoft Intune pro zařízení se systémem Windows 10 nebo novější. Výchozí hodnoty pro nastavení v těchto standardních hodnot představovat doporučenou konfiguraci pro příslušné zařízení a nemusí odpovídat výchozí hodnoty směrného plánu z dalších standardních hodnot zabezpečení.  

Nejnovější základní verzi je **MDM standardních hodnot zabezpečení pro Spring 2019 aktualizace (19 hod. 1)**  

Další informace o co se změnilo v nejnovější verzi tohoto směrného plánu z předchozí verze, najdete v článku [co se změnilo v nové šabloně](#whats-changed-in-the-new-template).  

> [!NOTE]  
> V červnu. 2019 byl směrný plán zabezpečení MDM ve verzi preview nahrazuje vydání *MDM standardních hodnot zabezpečení pro Spring 2019 aktualizace (19 hod. 1)* šablonu, která je generaly (nejsou ve verzi preview) k dispozici. Profily, které byly vytvořeny před dostupnost *MDM standardních hodnot zabezpečení pro Spring 2019 aktualizace (19 hod. 1)* směrného plánu neaktualizuje a neodráží skutečnost nastavení a hodnoty, které jsou v MDM základního zabezpečení pro Spring 2019 aktualizace (19 hod. 1 ) verze.  I když nelze vytvořit nové profily založené na šabloně ve verzi preview, můžete upravit a pokračovat v používání profilů, které jste dříve vytvořili, které jsou založeny na šabloně ve verzi preview.   
  
Další informace o použití standardních hodnot zabezpečení s Intune, najdete v článku [používat směrné plány zabezpečení](security-baselines.md).  


   
## <a name="above-lock"></a>Nad zámkem  
Další informace najdete v tématu [zásady CSP – AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) v dokumentaci k Windows.  

- **Blokovat zobrazování informační zprávy**  
  Nastavení této zásady umožňuje zabránit oznámení aplikací povolí, na zamykací obrazovce. Pokud nastavení této zásady povolíte, žádná oznámení. aplikace se zobrazí na zamykací obrazovce. Pokud zakážete nebo není pro toto nastavení zásad, uživatelé aplikace, které mohou zobrazovat oznámení na zamykací obrazovce.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067101)  

  **Výchozí**: Ano  

- **Hlasové aktivovat aplikace na uzamčené obrazovce**  

  **Výchozí**: Zakázáno

## <a name="app-runtime"></a>Modul Runtime aplikace    
Další informace najdete v tématu [zásady CSP – AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) v dokumentaci k Windows.  

- **Účty Microsoft, volitelné pro aplikace Windows Store**  
  Nastavení této zásady umožňuje řídit, zda jsou účty Microsoft volitelné pro aplikace Windows Store, které vyžadují účet pro přihlášení. Tyto zásady ovlivní pouze aplikace Windows Store, které ji podporují. Pokud povolíte toto nastavení zásad, aplikací Windows Store, které obvykle vyžadují účet Microsoft pro přihlášení vám umožní uživatelům přihlašovat se místo toho se pomocí účtu organizace. Pokud zakážete nebo není pro toto nastavení zásad, musíte se přihlásit uživatele pomocí účtu Microsoft.  
    [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067104)  
  
  **Výchozí**: Enabled  

## <a name="application-management"></a>Správa aplikací   
Další informace najdete v tématu [zásady CSP – ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) v dokumentaci k Windows.  

- **Blok kontrola uživatele nad instalací**  
  Nastavení této zásady umožňuje uživatelům změnit možnosti instalace, které jsou obvykle k dispozici pouze pro správce systému. Pokud nastavení této zásady povolíte, některé funkce zabezpečení Windows Installer obejít. IT specialistovi instalace, které by jinak byly ukončeny z důvodu narušení zabezpečení. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, funkce zabezpečení Windows Installer zabrání uživatelům změnit možnosti instalace, obvykle vyhrazena pro správce systému, jako je zadání adresáře, do které jsou nainstalovány soubory. Pokud instalační služby systému Windows zjistí, že instalačního balíčku povolil uživatelům měnit chráněný možnost, instalace se zastaví a zobrazí zprávu. Tyto funkce zabezpečení fungovat, pouze když instalační program běží v kontextu zabezpečení privilegovaného, ve kterém je uživateli odepřen přístup k adresářům. Toto nastavení zásad je navržená pro méně omezující prostředí. Je možné obejít chyby v instalačním programu, který brání instalaci softwaru.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067060)  

    **Výchozí**: Ano

- **Instalace aplikací MSI bloku se zvýšenými oprávněními**  
  Nastavení této zásady instruuje Instalační služby systému Windows použít zvýšenou úroveň oprávnění při instalaci libovolné aplikace v systému.  
  - *Pokud povolíte toto nastavení zásad*, oprávnění jsou rozšířeny, aby všechny programy. Tato oprávnění jsou obvykle vyhrazena pro programy, které byla přiřazena uživateli (nabízených v klientských počítačích), přiřazená f počítače (automaticky), nebo k dispozici na panelu Přidat nebo odebrat programy v Ovládacích panelech. Toto nastavení profilu umožňuje uživatelům s instalací programy, které vyžadují přístup k adresářům, že uživatel možná nemáte oprávnění k zobrazení nebo změny, včetně adresářů na vysoce omezenou počítačích.
  - *Pokud zakážete nebo nenakonfigurujete toto nastavení zásad*, systém použije aktuální uživatel oprávnění při instalaci programy, které správce systému distribuovat nebo nabídky. Poznámka: Nastavení této zásady se zobrazí v konfiguraci počítače a konfigurace uživatele. Chcete-li toto nastavení zásad efektivní, povolte ho v obě složky. Upozornění: Zkušení uživatelé mohou využít výhod oprávnění uděluje měnit jejich oprávnění a trvalé přístup odkudkoli k souborům s omezeným přístupem a složky nastavení této zásady. Všimněte si, že toto nastavení zásad Konfigurace uživatele verze není zaručeno zabezpečení.  
  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067134)    

  **Výchozí**: Ano

- **Blokovat záznam ze hry (jenom desktopové verze)**  
  Nakonfiguruje, jestli je povolené záznam a vysílání z her.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067056)  
  
  **Výchozí**: Ano  

## <a name="auto-play"></a>Auto Play   
Další informace najdete v tématu [zásady – CSP pro automatické přehrání](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) v dokumentaci k Windows.  

- **Automatické přehrávání automaticky výchozí chování při spuštění**  
  Toto nastavení má vliv na výchozí chování pro automatické spouštění příkazů. Příkazy automatického spuštění jsou uloženy v souborech autorun.inf a můžete spustit instalační programy nebo jiných rutin. Když *povoleno*, Správce může změnit výchozí chování automatického spuštění na zařízení se systémem Windows Vista nebo novější. Chování může být nastaven na: a) zcela zakázat příkazy automatického spuštění, nebo (b) vrátit zpět k než Windows Vista chování automaticky spouští se příkaz automatického spuštění. Pokud je nastavena na *zakázané* nebo *Nenakonfigurováno*, zařízení, na kterých běží Windows Vista nebo novější řádku uživatele o tom, zda automatického spuštění má příkaz spustit.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067133)       
  
  **Výchozí**: Neprovádět je  
  
- **Režim automatického přehrávání**  
  Nastavení této zásady umožňuje vypnout funkci automatického přehrávání. Automatické přehrávání zahájí čtení z disku jako vložte médium do jednotky. V důsledku toho instalační soubor programů a hudbu na médiu zvuku spustit okamžitě. Před Windows XP SP2 je zakázané automatické přehrávání ve výchozím nastavení na vyměnitelné jednotky, jako je například disketové jednotky (ale ne jednotce CD-ROM) a na síťové jednotky. Od verze Windows XP SP2, automatické přehrávání je povolený pro vyměnitelné jednotky, včetně jednotky Zip a některé velkokapacitního paměťového zařízení USB. Pokud povolíte toto nastavení zásad, automatické přehrávání je zakázáno na disku CD-ROM a vyměnitelných jednotek nebo zakázaná na všech jednotkách. Nastavení této zásady se zakáže automatické přehrávání na dalších typů jednotek. Nelze pomocí tohoto nastavení můžete povolit automatické přehrávání na diskové jednotky, na kterých je ve výchozím nastavení zakázána. Pokud zakážete nebo není pro toto nastavení zásad, je povoleno automatické přehrávání. Poznámka: Nastavení této zásady se zobrazí ve složkách Konfigurace počítače a konfigurace uživatele. Pokud nastavení zásad jsou v konfliktu, nastavení zásad Konfigurace počítače má přednost před nastavení zásad Konfigurace uživatele.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2066793)  
  
  **Výchozí**: Zakázáno

- **Blokovat automatické přehrávání pro zařízení bez svazku**  
  Nastavení této zásady zakazuje automatické přehrávání pro zařízení MTP, jako jsou kamery a telefonů. Pokud povolíte toto nastavení zásad, automatické přehrávání není povolena pro zařízení MTP, jako jsou kamery a telefonů. Pokud zakážete nebo není pro toto nastavení zásad, automatické přehrávání je povolený pro zařízení bez svazku.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067106)    
  
  **Výchozí**: Enabled  

## <a name="bitlocker"></a>Nástroj BitLocker    
Další informace najdete v tématu [zásady CSP – Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) v dokumentaci k Windows.  

- **Bit locker vyměnitelnou jednotku zásad**  
  Nastavení této zásady umožňuje řídit metodu, šifrování a šifer síly. Hodnoty těchto zásad určuje sílu šifra, která používá nástroj BitLocker k šifrování. Podniky může chtít řídit úroveň šifrování (AES-256 je silnější než AES-128) zvýšené zabezpečení. Pokud povolíte toto nastavení, budete moct nakonfigurovat šifrovací algoritmus a klíče úroveň šifrování pro pevné datové jednotky, jednotky s operačním systémem a vyměnitelných datových jednotkách jednotlivě. Oprava a provozní systémové jednotky doporučujeme použít algoritmus XTS-AES. Vyměnitelných jednotek měli byste použít AES-CBC 128-bit nebo AES-CBC oborového 256bitového Pokud na jednotce se používá v jiných zařízení se systémem Windows 10 verze 1511 nebo novější. Změna metoda šifrování nemá žádný účinek, pokud už zašifrovaná disku nebo šifrování probíhá. V těchto případech toto nastavení zásad se ignoruje.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067140) 

  Bit locker vyměnitelnou jednotku zásady nakonfigurujte následující nastavení:

    - **Vyžadovat šifrování pro zápis**  
      **Výchozí**: Ano  
  

## <a name="browser"></a>Browser  
Další informace najdete v tématu [zásady CSP – prohlížeč](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) v dokumentaci k Windows.  

- **Vyžadovat SmartScreen pro Microsoft Edge**  
  Microsoft Edge používá k ochraně uživatelů před podvodných potenciální a škodlivým softwarem ve výchozím nastavení Windows Defender SmartScreen (zapnuto). Ve výchozím nastavení, také uživatele nelze zakázat (vypnout) Windows Defender SmartScreen. Když se tyto zásady vypne Windows Defender SmartScreen a zabrání uživatelům ho zapnout. Nekonfigurujte tato zásada umožňuje uživatelům zvolit program Windows defender SmartScreen zapnout nebo vypnout.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067029)   
  
  **Výchozí**: Ano  
  
- **Blokovat přístup na škodlivý web**  
  Ve výchozím nastavení, Microsoft Edge umožňují uživatelům obejít (Ignorovat) upozornění filtru Windows Defender SmartScreen potenciálně škodlivé weby, což jim umožní pokračovat na příslušný web. K této zásadě ale můžete nakonfigurovat Microsoft Edge uživatelům zabránit v obejít upozornění, blokování pokračování k webu.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067040)   
  
  **Výchozí**: Ano  
  
- **Blokovat stahování neověřených souborů**  
  Ve výchozím nastavení, Microsoft Edge umožňují uživatelům obejít (Ignorovat) upozornění filtru Windows Defender SmartScreen na potenciálně škodlivých souborů, což jim umožní pokračovat ve stahování neověřených souborů. Když se tyto zásady zabrání uživatelům obejít upozornění, blokování stahování neověřených souborů.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067023)  
  
  **Výchozí**: Ano  
  
- **Blokovat správce hesel**  
  Ve výchozím nastavení Microsoft Edge použije správce hesel automaticky, umožní tak místně hesla správce. V případě jejího zakázání brání použití hesla správce Microsoft Edge. Pokud chcete umožnit uživatelům ukládat a spravovat hesla místně s použitím správce hesel, nekonfigurujte tuto zásadu.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067128)  
  
  **Výchozí**: Ano  
  
- **Zabránit přepsání Chyba certifikátu**  
  Nastavení této zásady zabrání uživateli možnost Ignorovat chyby certifikátů Secure Sockets Layer/Transport Layer Security (SSL/TLS), které přerušení procházení (jako "prošlé", "zrušeno" nebo "došlo k neshodě názvů" chyby) v aplikaci Internet Explorer. Pokud nastavení této zásady povolíte, uživatel nemůže pokračovat v procházení. Pokud zakážete nebo není pro toto nastavení zásad, uživatele můžete rozhodnout ignorovat chyby certifikátů a pokračovat v procházení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067126)  
  
  **Výchozí**: Ano  

## <a name="connectivity"></a>Připojení  
Další informace najdete v tématu [zásady CSP – připojení](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) v dokumentaci k Windows.  

- **Stahování z Internetu bloku pro webové, publikování a online objednáním**  
  Nastavení této zásady určuje, zda by měl Windows stáhnout seznam poskytovatelů pro weby, publikování a online objednáním. Tito průvodci povolit uživatelům výběr ze seznamu společností, které poskytují služby, jako je online úložiště a tisk fotografií. Ve výchozím nastavení zobrazí stažené z webu Windows kromě poskytovatelů uvedený v registru Windows. Pokud nastavení této zásady povolíte, nebude Windows stáhnout poskytovatele a pouze poskytovatelé služeb, které jsou uložené v mezipaměti v místním registru zobrazení. Pokud zakážete nebo není pro toto nastavení zásad, seznamu zprostředkovatelů stáhne, pokud uživatel použije webového publikování nebo online objednáním. Další informace, který obsahuje informace o určení poskytovatelů služeb v registru naleznete v dokumentaci pro weby, publikování a online objednáním.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067136)  
  
  **Výchozí**: Enabled  

- **Blokovat stahování ovladačů tiskáren pomocí protokolu HTTP**  
  Nastavení této zásady určuje, jestli se má povolit tohoto klienta stáhnout balíčky ovladače tiskárny přes protokol HTTP. Nastavení HTTP tisk, ovladače doručené pošty není třeba stahovat přes protokol HTTP. Poznámka: Nastavení této zásady nezabrání Klient tisku na tiskárnách na intranetu nebo Internetu přes protokol HTTP. Zakazuje pouze stahování ovladačů, které nejsou nainstalovány místně. Pokud nastavení této zásady povolíte, nejde stáhnout ovladačů tiskárny přes protokol HTTP. Pokud zakážete nebo není pro toto nastavení zásad, uživatelé můžou stahovat ovladačů tiskárny přes protokol HTTP.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067141)  
  
  **Výchozí**: Enabled  

## <a name="credentials-delegation"></a>Delegování přihlašovacích údajů  
Další informace najdete v tématu [zásady CSP – CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) v dokumentaci k Windows.  

- **Vzdálený hostitel delegování neexportovatelného přihlašovacích údajů**  
  Vzdálený hostitel povoluje delegování neexportovatelného přihlašovacích údajů. Při použití delegování přihlašovacích údajů, zařízení poskytují exportovatelné verzi přihlašovací údaje ke vzdálenému hostiteli, která poskytuje uživatelům riziku krádeže přihlašovacích údajů proti útokům na vzdáleného hostitele. Pokud nastavení této zásady povolíte, hostitel podporuje režim Restrictedadmin nebo vzdálené Credential Guard. Pokud zakážete nebo není pro toto nastavení zásad správy s omezeným přístupem a režim vzdáleného Credential Guard nejsou podporovány. Uživatel bude muset vždy předat své přihlašovací údaje k hostiteli.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067103)   
  
  **Výchozí**: Enabled  

## <a name="credentials-ui"></a>Přihlašovací údaje uživatelského rozhraní  
Další informace najdete v tématu [zásady CSP – CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) v dokumentaci k Windows.  

- **Zobrazení výčtu správci** tato zásada, nastavení ovládacích prvků, jestli účty správce zobrazit, když se uživatel pokusí zvýšit běžící aplikaci. Ve výchozím nastavení nejsou zobrazeny účty správců, když se uživatel pokusí zvýšit běžící aplikaci. Pokud nastavení této zásady povolíte, zobrazí všechny účty oprávnění místního správce na počítači, uživatel může zvolit jednu a zadejte správné heslo. Pokud nastavení této zásady zakážete, uživatelé se vždy třeba zadat uživatelské jméno a heslo pro zvýšení oprávnění.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067021)

  
  **Výchozí**: Zakázáno  

## <a name="data-protection"></a>Data Protection  
Další informace najdete v tématu [zásady CSP – DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) v dokumentaci k Windows.  

- **Blokovat přímý přístup do paměti**  
  Nastavení této zásady umožňuje blokovat přímý přístup do paměti (DMA) pro všechny aktivní modulární PCI podřízené porty dokud se uživatel přihlásí do Windows. Jakmile se uživatel přihlásí, bude Windows výčet PCI zařízení připojená k portům PCI moduly hostitele. Pokaždé, když se uživatel uzamkne na počítači, DMA na portech PCI připojitelný zablokována se žádná zařízení. podřízené položky dokud znovu přihlásí uživatel. Zařízení, které byly již uvedené, když je počítač se odemkl. bude nadále fungovat, dokud byl odpojen. Nastavení této zásady se vynucují jenom, když je povolené šifrování nástrojem BitLocker nebo zařízení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067031)     
  
  **Výchozí**: Ano  

## <a name="device-guard"></a>Device Guard  
Další informace najdete v tématu [zásady CSP – DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) v dokumentaci k Windows.  

- **Credential Guard**  
  Toto nastavení umožňuje zapnout Credential Guard se zabezpečením na základě virtualizace k ochraně přihlašovací údaje při příštím restartování.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067044)
   
  **Výchozí**: Povolit se zámkem UEFI 

- **Povolit zabezpečení na základě virtualizace**   
  Zapne založené na virtualizaci zabezpečení (VBS) při příštím restartování. Zabezpečení na základě virtualizace nabízí podporu služeb zabezpečení pomocí hypervisoru Windows.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067066)  
  
  **Výchozí**: Ano  


- **Spusťte systém guard**    
  **Výchozí**: Enabled  

## <a name="device-installation"></a>Instalace zařízení  
Další informace najdete v tématu [zásady CSP – DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) v dokumentaci k Windows.  

- **Instalace hardwaru zařízení pomocí identifikátorů zařízení**  
  Nastavení této zásady umožňuje zadat seznam ID Plug and Play hardwaru a kompatibilní ID pro zařízení, že je Windows zabráněno v instalaci. Toto nastavení zásad má přednost před jiného nastavení zásad, který umožňuje nainstalovat zařízení Windows. Pokud nastavení této zásady povolíte, je Windows zabránily instalaci zařízení, jejichž hardware kompatibilní ID nebo ID se zobrazí v seznamu, který vytvoříte. Pokud povolíte toto nastavení zásad v serveru vzdálené plochy, nastavení zásad má vliv přesměrování zadané zařízení z klienta vzdálené plochy k serveru vzdálené plochy. Pokud zakážete nebo není pro toto nastavení zásad zařízení můžete instalovat a aktualizovat jako povolené nebo mu nastavením jiné zásady.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2066794)  
  
  **Výchozí**: Instalace bloku hardwaru zařízení  

    Když *služba neblokuje instalaci hardwaru zařízení* je vybráno, tato nastavení jsou k dispozici.
  
    - **Odeberte odpovídající hardwarové zařízení**   
    Toto nastavení je dostupná jenom v případě *instalace zařízení hardwaru pomocí identifikátorů zařízení* je nastavena na *služba neblokuje instalaci zařízení hardwaru*.
      
      **Výchozí**: Ano
  
    - **Identifikátory hardwaru zařízení, které jsou blokovány**  
       Toto nastavení je dostupná jenom v případě *instalace zařízení hardwaru pomocí identifikátorů zařízení* je nastavena na *služba neblokuje instalaci zařízení hardwaru*.
      
      **Výchozí**: Ano  
  
- **Instalace hardwaru zařízení v nastavení tříd**  
  Nastavení této zásady umožňuje určit seznam zařízení nastavení třídy globálně jedinečné identifikátory (GUID) pro ovladače zařízení, že je Windows zabráněno v instalaci. Toto nastavení zásad má přednost před jiného nastavení zásad, který umožňuje nainstalovat zařízení Windows. Pokud nastavení této zásady povolíte, je Windows nebudou instalujete nebo aktualizujete ovladače zařízení, jehož třída instalace zařízení v seznamu se zobrazí identifikátory GUID vytvoříte. Pokud povolíte toto nastavení zásad v serveru vzdálené plochy, nastavení zásad má vliv přesměrování zadané zařízení z klienta vzdálené plochy k serveru vzdálené plochy. Pokud zakážete nebo není pro toto nastavení zásad, můžete nainstalovat Windows a aktualizace zařízení povolený, nebo z důvodu dalších nastavení zásad.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067048)  
  
  **Výchozí**: Instalace bloku hardwaru zařízení  

    Když *služba neblokuje instalaci hardwaru zařízení* je vybráno, tato nastavení jsou k dispozici.
    - **Odeberte odpovídající hardwarové zařízení**    
    Toto nastavení je dostupná jenom v případě *instalace hardwaru zařízení v nastavení tříd* je nastavena na *služba neblokuje instalaci zařízení hardwaru*.  

      **Výchozí**: *Žádná výchozí konfigurace*  
  
    - **Identifikátory hardwaru zařízení, které jsou blokovány**  
      Toto nastavení je dostupná jenom v případě *instalace hardwaru zařízení v nastavení tříd* je nastavena na *služba neblokuje instalaci zařízení hardwaru*.
      
      **Výchozí**: *Žádná výchozí konfigurace*  

## <a name="device-lock"></a>Uzamčení zařízení  
Další informace najdete v tématu [zásady CSP – DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) v dokumentaci k Windows.  

- **Zakázat použití fotoaparátu**  
  Zakáže přepínač zámek obrazovky fotoaparát v nastavení počítače a zabraňuje kamera vyvolání na zamykací obrazovce. Ve výchozím nastavení můžete uživatelům povolit volání k dispozici fotoaparátu na zamykací obrazovce. Pokud toto nastavení povolíte, uživatelé už nebudou moct povolit nebo zakázat přístup k fotoaparátu zámek obrazovky v nastavení počítače a fotoaparátu/kamery nelze vyvolat na zamykací obrazovce.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067052)
  
  **Výchozí**: Enabled  

- **Vyžadovat heslo**  
  Určuje, zda je povoleno uzamčení zařízení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067049)  
  
  **Výchozí**: Ano  
  
    Když *vyžadovat heslo* je nastavena na *Ano*, jsou dostupná následující nastavení.

    - **Minimální znak hesla nastavit počet**  
      Počet typů komplexních prvků (velká a malá písmena, číslice a interpunkční znaménka) požadované pro silný PIN kód nebo heslo. PIN kód vynucuje toto chování pro stolní počítače a mobilní zařízení: 1 - číslice pouze 2 - číslice a malá písmena jsou požadované 3 - číslice a malá písmena a velká písmena se vyžadují. Nepodporováno v klasické pracovní plochy účty Microsoft a účty domény. 4 - číslice, malá písmena, velká písmena a speciální znaky jsou povinné. Není podporován v desktopu. Výchozí hodnota je 1.  
      [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067055)  
      
      **Výchozí**: 3  
  
    - **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**  
      Počet chyb ověřování povolené předtím, než se zařízení vymaže. Hodnota 0 zakáže funkci vymazání zařízení.  
      [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067030)  
        
      **Výchozí**: 10  
  
    - **Vypršení platnosti hesla (dny)**  
      Nastavení maximální stáří hesla zásad určuje, jak dlouho (ve dnech), že heslo lze využít, než bude systém vyžadovat uživateli ji změnit. Můžete nastavit hesla vyprší po uplynutí počtu dnů mezi 1 a 999, nebo můžete určit, že platnost hesel nikdy nevypršela tak, že nastavíte časový interval na hodnotu 0. Pokud je maximální stáří hesla mezi 1 a 999 dní, minimální stáří hesla musí být menší než je maximální stáří hesla. Pokud je maximální stáří hesla nastavená na hodnotu 0, může být minimální stáří hesla libovolnou hodnotu mezi 0 a 998 dnů.  
      [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067028)  
      
      **Výchozí**: 60  
  
    - **Požadovaný typ hesla**  
      Určuje typ kódu PIN nebo heslem.  
      [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067027)  
      
      **Výchozí**: Alfanumerické znaky  
  
    - **Minimální délka hesla**  
      Nastavení zásad délka hesel minimální Určuje nejmenší počet znaků, které můžete vytvořit heslo pro uživatelský účet. Můžete nastavit hodnotu mezi 1 a 14 znaků, nebo vám pomůže zajistit, že není požadováno žádné heslo tak, že počet znaků, které nastavíte na hodnotu 0.  
      [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067024)  
      
      **Výchozí**: 8  
  
    - **Blokovat jednoduchá hesla**  
      Určuje, zda jsou povolena PIN kódy nebo hesla, jako je například "1111" nebo "1234". Pro stolní počítače se řídí navíc i použití obrázkových hesel.  
      [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067127) 
      
      **Výchozí**: Ano  
        *Nastavení na Ano brání použití jednoduchých hesel.* 

  - **Znemožnit opakované použití předchozích hesel**  
    Určuje, kolik hesel mohou být uloženy v historii, který nelze použít. Tato hodnota zahrnuje aktuální heslo uživatele. Například s nastavením *1* uživatel nemůže znovu použít své aktuální heslo při výběru nového hesla. Nastavení *5* znamená, že uživatel nelze nastavit nové heslo na jejich aktuální heslo nebo některý z předchozí čtyři hesla.  
    [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2066795)  
    
    **Výchozí**: 24  

- **Zabránit prezentace**  
  Zakáže nastavení zamykací obrazovky prezentace v nastavení počítače a prezentace brání přehrávání na zamykací obrazovce. Ve výchozím nastavení můžete uživatelům povolit prezentace, která se spustí po jejich uzamčení počítače. Pokud toto nastavení povolíte, uživatelé nemohou upravovat nastavení prezentace v nastavení počítače a může začít žádné prezentace.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067105) 
  
  **Výchozí**: Enabled  
  *Nastavení povoleno prezentace zabraňuje spuštění.* 

- **Minimální stáří hesla ve dnech**  
  Nastavení minimální stáří hesla zásady určuje dobu (ve dnech), po kterou musí být heslo použít předtím, než ho uživatel může změnit. Můžete nastavit hodnotu v rozmezí 1 až 998 dnů nebo změny hesla můžete povolit okamžitě tak, že nastavíte časový interval na hodnotu 0. Minimální stáří hesla musí být menší než maximální stáří hesla, pokud je maximální stáří hesla je nastaven na hodnotu 0 označující, že hesla nikdy nevyprší. Pokud je maximální stáří hesla je nastavena na hodnotu 0, minimální stáří hesla můžete nastavit na libovolnou hodnotu mezi 0 a 998.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067022) 
  
  **Výchozí**: 1  

## <a name="dma-guard"></a>Ochrany DMA Guard  
Další informace najdete v tématu [zásady CSP – DmaGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard) v dokumentaci k Windows.
- **Výčet externích zařízení nekompatibilní s ochranou DMA jádra**  
  Tato zásada je určena pro zvýšení zabezpečení proti externí DMA zařízení. To umožňuje používat pro větší kontrolu nad výčet externích zařízení DMA kompatibilní s izolace paměti DMA přemapování/zařízení a izolace (sandbox). Tyto zásady platí pouze při ochrany DMA jádra je podporován a povolený už ve firmwaru systému. Ochrany DMA jádra je funkce platformy, která nelze řídit pomocí zásad nebo koncovým uživatelem. Musí být podporovaný systémem v době výrobní. Chcete-li zkontrolovat, jestli systém podporuje ochrany DMA jádra, zkontrolujte pole ochrany DMA jádra na stránce souhrnu MSINFO32.exe.  
  [Víc se uč](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  **Výchozí**: Blokovat veškerý   

## <a name="event-log-service"></a>Služba Protokol událostí  
Další informace najdete v tématu [zásady CSP – EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) v dokumentaci k Windows.  

- **Maximální velikost protokolu zabezpečení v článku KB**  
  Nastavení této zásady určuje v kilobajtech maximální velikost souboru protokolu. Pokud nastavení této zásady povolíte, můžete nakonfigurovat maximální velikost souboru protokolu být v rozmezí 1 MB (1 024 kB) a 2 terabajty (2147483647 kilobajtů) v přírůstcích po kilobajtů. Pokud zakážete nebo není pro toto nastavení zásady maximální velikost souboru protokolu nastavená na místně konfigurovaná hodnota. Tuto hodnotu můžete změnit místní správce v dialogovém okně Vlastnosti protokolu a výchozí hodnota 20 megabajtů.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067042)  
  
   **Výchozí**: 196608  

- **Systém protokolu maximální velikost v KB**  
  Nastavení této zásady určuje v kilobajtech maximální velikost souboru protokolu. Pokud nastavení této zásady povolíte, můžete nakonfigurovat maximální velikost souboru protokolu být v rozmezí 1 MB (1 024 kB) a 2 terabajty (2147483647 kilobajtů) v přírůstcích po kilobajtů. Pokud zakážete nebo není pro toto nastavení zásady maximální velikost souboru protokolu nastavená na místně konfigurovaná hodnota. Tuto hodnotu můžete změnit místní správce v dialogovém okně Vlastnosti protokolu a výchozí hodnota 20 megabajtů.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2066798)  
  
  **Výchozí**: 32768  

- **Aplikace protokolu maximální velikost v KB**  
  Nastavení této zásady určuje v kilobajtech maximální velikost souboru protokolu. Pokud nastavení této zásady povolíte, můžete nakonfigurovat maximální velikost souboru protokolu být v rozmezí 1 MB (1 024 kB) a 2 terabajty (2147483647 kilobajtů) v přírůstcích po kilobajtů. Pokud zakážete nebo není pro toto nastavení zásady maximální velikost souboru protokolu nastavená na místně konfigurovaná hodnota. Tuto hodnotu můžete změnit místní správce v dialogovém okně Vlastnosti protokolu a výchozí hodnota 20 megabajtů.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067125)  
  
  **Výchozí**: 32768  

## <a name="experience"></a>Prostředí  
Další informace najdete v tématu [zásady CSP – prostředí](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) v dokumentaci k Windows.  

- **Blokovat Windows Spotlight**  
  Umožňuje správcům IT vypnout všechny Windows Spotlight funkce – Windows spotlight na zamykací obrazovce, tipy Windows, Microsoft uživatelské funkce a další související funkce.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067037)  
  
  **Výchozí**: Ano  

  Když *blokovat Windows Spotlight* je nastavena na *Ano*, jsou dostupná následující nastavení.
  
  - **Blokovat návrhy třetích stran ve Windows Spotlightu**  
    Určuje, zda povolit návrhy aplikací a obsahu z jiných výrobců softwaru vydavateli ve Windows spotlight funkce, jako je spotlight zámek obrazovky, navrhované aplikace v nabídce Start a tipy Windows. Uživatelé můžou pořád ještě považuje návrhy funkcí, aplikací a služeb společnosti Microsoft.  
    [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067045)  
      
    **Výchozí**: Ano  
  - **Blokovat konkrétní uživatelské funkce**  
    Umožňuje správcům IT zapnout prostředí, které jsou obvykle jenom uživatelům, jako jsou návrhy nabídky Start, oznámení o členství, instalace aplikací příspěvek prvním spuštění počítače a dlaždice pro přesměrování.  
    [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067054)  
     
    **Výchozí**: Ano  

## <a name="exploit-guard"></a>Ochrana Exploit Guard  
Další informace najdete v tématu [zásady CSP – ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) v dokumentaci k Windows.  

- **Ochrana Exploit protection XML**  
  Umožňuje správci IT vydat konfiguraci, která představuje požadované systému a možnosti omezení rizik aplikací pro všechna zařízení v organizaci. Představuje konfiguraci XML. Ochrana Exploit protection pomáhá chránit zařízení před malwarem, který zneužití šíří a terčem útoků. Použijete aplikace Windows zabezpečení nebo prostředí PowerShell k vytvoření sadu omezení rizik (označované jako konfigurace). Pak můžete exportovat tuto konfiguraci jako soubor XML a sdílet ho s více počítači ve vaší síti všechny mají stejnou sadu nastavení zmírňování. Můžete také převést a importovat existující sada nástrojů EMET konfigurační soubor XML do konfiguraci ochrany před zneužitím XML.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067035)  
  
  **Výchozí**: *Ukázkové xml je k dispozici* 
 
## <a name="file-explorer"></a>Průzkumník souborů  
Další informace najdete v tématu [zásady CSP – Průzkumník souborů](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) v dokumentaci k Windows.  

- **Zabránění spuštění dat bloku**  
  Zakázání zabránění spuštění dat můžete povolit určité starší modul plug-in aplikace fungovat bez ukončující Průzkumníka.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067043)  
  
  **Výchozí**: Zakázáno  
   
- **Ukončení bloku haldy na poškození**  
  Zakázání ukončení poškození haldy můžete povolit určité starší modul plug-in aplikace fungovat okamžitě, bez ukončujícího znaku Explorer, ačkoli Průzkumník může stále dojde k neočekávanému ukončení později.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067107)  
  
  **Výchozí**: Zakázáno  
    

## <a name="internet-explorer"></a>Internet Explorer  
Další informace najdete v tématu [zásady CSP – Internet Explorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) v dokumentaci k Windows.  

- **Aktualizace zóny Internet Exploreru s omezením pomocí specifikátoru na stavovém řádku prostřednictvím skriptu**  
  Nastavení této zásady umožňuje určit, zda smí skript aktualizace stavového řádku v rámci zóny. 
  - *Pokud povolíte toto nastavení zásad*, můžou aktualizovat stavový řádek skriptu.
  - *Pokud zakážete nebo nenakonfigurujete toto nastavení zásad*, skriptu není povolena aktualizace stavového řádku.  

  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067074)  

  **Výchozí**: Zakázáno

- **Zóny Internetu aplikace Internet Explorer přetáhněte nebo zkopírujte a vložte soubory**  
  Nastavení této zásady umožňuje určit, zda uživatele lze přetáhnout soubory nebo kopírování a vkládání souborů ze zdroje v rámci zóny. Pokud nastavení této zásady povolíte, uživatelé můžete přetáhnout soubory nebo zkopírovat a vkládat soubory z této zóny automaticky. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat rozhodnout, jestli jej přetáhnout nebo zkopírovat soubory z této zóny. Pokud nastavení této zásady zakážete, uživatelé nebudou moci soubory přetažením nebo zkopírováním a vložením soubory z této zóny. Pokud nastavení této zásady nenakonfigurujete, uživatelé můžete přetáhnout soubory nebo zkopírovat a vložit soubory z této zóny automaticky.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067076)  

  **Výchozí**: Zakázat

- **Spolehlivé součásti .NET Framework aplikace Internet Explorer s omezením pomocí specifikátoru zóny**    
  Nastavení této zásady umožňuje určit, zda mohou být spuštěny součásti rozhraní .NET Framework, které nejsou podepsané pomocí technologie Authenticode aplikace Internet Explorer. Mezi tyto komponenty patří spravované ovládací prvky, které odkazuje objektu značku a spravované spustitelné soubory, které na něj odkazovat z odkazu. Pokud nastavení této zásady povolíte, Internet Explorer se spustí bez znaménka spravované součásti. Pokud v rozevíracím seznamu vyberte řádek, Internet Explorer vyzve uživatele k určení, jestli se má provést bez znaménka spravované součásti. Pokud nastavení této zásady zakážete, aplikace Internet Explorer nespustí, bez znaménka spravované součásti. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer nespustí, bez znaménka spravované součásti.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067077)

  **Výchozí**: Zakázat


- **Místní počítač zóny Internet Exploreru nespouštějte antimalwarové proti ovládací prvky ActiveX**  
  Nastavení této zásady určuje, jestli aplikace Internet Explorer se spouští antimalwarové programy proti ovládací prvky ActiveX, a zkontrolujte, zda jsou bezpečné pro načtení na stránkách. Pokud nastavení této zásady povolíte, nebude Internet Exploreru zkontrolujte s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, nebudou Internet Exploreru zkontrolujte s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Uživatele můžete vypnout toto chování zapnout nebo vypnout pomocí nastavení zabezpečení aplikace Internet Explorer.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067152)

  **Výchozí**: Zakázáno

- **Přístup k zóny Internetu aplikace Internet Explorer ke zdrojům dat**  
  Nastavení této zásady umožňuje určit, zda aplikace Internet Explorer můžete přistupovat k datům z jiné zóny zabezpečení pomocí Microsoft XML Parser (MSXML) nebo objekty ADO (ActiveX Data OBJECTS). Pokud nastavení této zásady povolíte, uživatelé můžou načítat stránku v oblasti, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat zvolit, jestli se má povolit stránky načíst v zóně, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud nastavení této zásady zakážete, uživatelé nelze načíst stránku v oblasti, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud nastavení této zásady nenakonfigurujete, uživateli nelze načíst stránku v oblasti, která používá pro přístup k datům z jiné lokality v zóně MSXML nebo ADO.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067078)  
  
  **Výchozí**: Zakázat  
  
- **Zóny s omezeným přístupem v Internet Exploreru přetáhněte obsah z jiných domén v rámci systému windows**  
  Nastavení této zásady umožňuje nastavit možnosti pro přetažení obsah z jedné domény do jiné domény, pokud zdroj a cíl nacházejí ve stejném okně. Pokud povolíte toto nastavení zásad a klikněte na možnost povolit, uživatelé můžete přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl nacházejí ve stejném okně. Uživatelé nemohou změnit toto nastavení. Pokud povolíte toto nastavení zásad a klikněte na možnost zakázat, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl nacházejí ve stejném okně. Uživatelé nemohou změnit toto nastavení v dialogovém okně Možnosti Internetu. V Internet Exploreru 10 Pokud nastavení této zásady zakážete nebo nekonfigurujte, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl nacházejí ve stejném okně. Uživatelé mohou změnit toto nastavení v dialogovém okně Možnosti Internetu. V aplikaci Internet Explorer 9 a starší Pokud nastavení této zásady zakážete nebo nekonfigurujte, uživatelé můžete přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí ve stejném okně. Uživatelé nemohou změnit toto nastavení v dialogovém okně Možnosti Internetu.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067079)  
  
  **Výchozí**: Zakázáno
  
- **Upozornění o neshodě certifikátu adresa aplikace Internet Explorer**  
  Nastavení této zásady umožňuje zapnout upozornění zabezpečení neshoda adresy certifikátu. Pokud nastavení této zásady je zapnuté, uživatel je upozorněn při návštěvě této k dispozici certifikáty vydané pro jiný web adresu weby Secure HTTP (HTTPS). Toto upozornění zabraňuje podvodným útokům. Pokud nastavení této zásady povolíte, certifikát adresu neshoda upozornění vždy se zobrazí. Pokud zakážete nebo není pro toto nastavení zásad, uživatel může zvolit, zda se zobrazí upozornění o neshodě adresu certifikát (s použitím pokročilé stránky Internet ovládacího panelu).  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067153)  
  
  **Výchozí**: Enabled 
  
- **Aplikace Internet Explorer s omezeným přístupem zóna menší privilegované webů**  
  Nastavení této zásady umožňuje určit, zda webů z méně privilegovaným zóny, jako jsou internetové weby se můžete dostat do této zóny. Pokud nastavení této zásady povolíte, webové servery ze zóny méně privilegovaným můžete otevřít v nových oknech, nebo přejít do této zóny. Zóna zabezpečení se spustí bez další úroveň zabezpečení, které poskytuje ochranu před funkci zabezpečení ke zvýšení úrovně oprávnění zóny. Pokud v rozevíracím seznamu vyberte řádek, objeví se upozornění pro uživatele, které potenciálně nebezpečné navigace se použije. Pokud nastavení této zásady zakážete, je zabráněno potenciálně škodlivé navigace. Funkce zabezpečení aplikace Internet Explorer je na v této zóně úmluvu ochranu ze zóny zvýšení funkce správy. Pokud nastavení této zásady nenakonfigurujete, nebudou další potenciálně škodlivé navigaci. Funkce zabezpečení aplikace Internet Explorer je na v této zóně úmluvu ochranu ze zóny zvýšení funkce správy.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067148)  
  
  **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer zakázané zóny automatické řádku pro soubor ke stažení**  
  Nastavení této zásady určuje, jestli se uživatelům výzva pro stahování souborů bez zahájená uživatelem. Bez ohledu na toto nastavení, uživatelé dostanou dialogová okna Stažení souboru pro uživatelem iniciované soubory ke stažení. Pokud toto nastavení povolíte, uživatelům se zobrazí dialogové okno Stažení souboru pro pokusy o automatické stahování. Pokud zakážete nebo toto nastavení nemusíte konfigurovat, jsou blokovány stahování souborů, které nejsou v uživatelem iniciované a uživatelům se zobrazí oznamovací pruh místo dialogu stažení souboru. Uživatelům můžete pak kliknout na oznamovací pruh umožňuje výzva ke stažení souboru.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067150)  
  
  **Výchozí**: Zakázáno
  
- **Spolehlivé součásti aplikace Internet Explorer internetové zóny rozhraní .NET Framework**  
  Nastavení této zásady umožňuje určit, zda mohou být spuštěny součásti rozhraní .NET Framework, které nejsou podepsané pomocí technologie Authenticode aplikace Internet Explorer. Mezi tyto komponenty patří spravované ovládací prvky, které odkazuje objektu značku a spravované spustitelné soubory, které na něj odkazovat z odkazu. Pokud nastavení této zásady povolíte, Internet Explorer se spustí bez znaménka spravované součásti. Pokud v rozevíracím seznamu vyberte řádek, Internet Explorer vyzve uživatele k určení, jestli se má provést bez znaménka spravované součásti. Pokud nastavení této zásady zakážete, aplikace Internet Explorer nespustí, bez znaménka spravované součásti. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer se spustí bez znaménka spravované součásti.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067073)  
  
  **Výchozí**: Zakázat 
  
- **Povolit zóny Internetu aplikace Internet Explorer schválí jen tehdy, domén používat ovládací prvky ActiveX ORS**  
  Toto nastavení zásady řídí, jestli uživatel může spustit ovládací prvek ActiveX ORS na webech. Pokud nastavení této zásady povolíte, ovládací prvek ActiveX ORS nespustí z webů v této zóně. Pokud nastavení této zásady zakážete, ovládací prvek ActiveX ORS se spustí ze všech lokalit v této zóně.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067151)
  
  **Výchozí**: Enabled 
  
- **Skript zóny s omezením pomocí specifikátoru aplikace Internet Explorer inicioval systému windows**  
  Toto nastavení zásad umožňuje spravovat omezení iniciované skriptu automaticky otevíraná okna a okna, která zahrnují panely názvu a stavu. Pokud nastavení této zásady povolíte, nebude v této zóně použít Windows omezení zabezpečení. Zóna zabezpečení se spustí bez další úroveň zabezpečení poskytované touto funkcí. Pokud nastavení této zásady zakážete, je to možné škodlivých akcí, které jsou součástí iniciované skriptu automaticky otevíraná okna a okna, která zahrnují panely názvu a stavu nelze spustit. Tuto funkci zabezpečení aplikace Internet Explorer je na v této zóně určený nastavení pro proces řízení funkci skripty Windows bezpečnostní omezení. Pokud nastavení této zásady nenakonfigurujete, je to možné škodlivých akcí, které jsou součástí iniciované skriptu automaticky otevíraná okna a okna, která zahrnují panely názvu a stavu nelze spustit. Tuto funkci zabezpečení aplikace Internet Explorer je na v této zóně určený nastavení pro proces řízení funkci skripty Windows bezpečnostní omezení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067075)  
  
  **Výchozí**: Zakázáno 
  
- **Zóny Internetu aplikace Internet Explorer zahrnují místní cesty při nahrávání souborů do serveru**  
  Toto nastavení zásady řídí, jestli místní cesta informace získá odesílá se, když uživatel je nahrát soubor přes formulář HTML. Pokud se pošle informace o místní cestu a některé informace mohou neúmyslně odhalena k serveru. Soubory odeslané z plochy uživatele, může obsahovat uživatelské jméno jako součást cesty. Pokud nastavení této zásady povolíte, informace o cestě se odešle, když uživatel je nahrát soubor přes formulář HTML. Pokud nastavení této zásady zakážete, informace o cestě se odebere, pokud uživatel odesílá soubory přes formulář HTML. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, zda informace o cestě odeslán při uložení souboru přes formulář HTML. Ve výchozím nastavení je odeslána informace o cestě.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067072)  
  
  **Výchozí**: Zakázáno 
  
- **Zakázat procesy v rozšířený chráněný režim Internet Exploreru**  
  Nastavení této zásady určuje, zda aplikace Internet Explorer 11 používá 64bitové procesy (kvůli lepšímu zabezpečení) nebo 32bitové procesy (pro lepší kompatibilita s) při spuštění v rozšířeným chráněným režimem v 64bitových verzích Windows. Důležité: Některé ovládací prvky ActiveX a panelů nástrojů nemusí být k dispozici, pokud jsou použity 64bitové procesy. Pokud nastavení této zásady povolíte, bude aplikace Internet Explorer 11 používat procesy karty 64-bit při spuštění v rozšířeným chráněným režimem na 64bitovými verzemi Windows. Pokud nastavení této zásady zakážete, bude aplikace Internet Explorer 11 používat procesy karty 32-bit při spuštění v rozšířeným chráněným režimem na 64bitovými verzemi Windows. Pokud nastavení této zásady nenakonfigurujete, uživatelé tuto funkci můžete zapnout nebo vypnout pomocí nastavení aplikace Internet Explorer. Tato funkce je ve výchozím nastavení vypnuté.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067149)  
  
  **Výchozí**: Enabled 
  
- **Aplikace Internet Explorer ignorovat chyby certifikátů**  
  Nastavení této zásady zabrání uživateli možnost Ignorovat chyby certifikátů Secure Sockets Layer/Transport Layer Security (SSL/TLS), které přerušení procházení (jako "prošlé", "zrušeno" nebo "došlo k neshodě názvů" chyby) v aplikaci Internet Explorer. Pokud nastavení této zásady povolíte, uživatel nemůže pokračovat v procházení. Pokud zakážete nebo není pro toto nastavení zásad, uživatele můžete rozhodnout ignorovat chyby certifikátů a pokračovat v procházení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067071)  
  
  **Výchozí**: Zakázáno 
  
- **Načítání zóny Internetu aplikace Internet Explorer souborů XAML**  
  Toto nastavení zásad umožňuje spravovat načítání souborů Extensible Application Markup Language (XAML). XAML je založený na formátu XML deklarativní značkovací jazyk běžně používají k vytváření pro uživatelská rozhraní bohatá a grafiku, které využívají výhod Windows Presentation Foundation. Pokud povolíte toto nastavení zásad a nastavte rozevírací seznam na povolit, jsou automaticky načteny soubory XAML v aplikaci Internet Explorer. Toto chování nelze změnit uživatele. Pokud nastavíte rozevíracího seznamu na řádku, bude uživatel vyzván k načítání souborů XAML. Pokud nastavení této zásady zakážete, soubory XAML nejsou načtené v Internet Exploreru. Toto chování nelze změnit uživatele. Pokud nastavení této zásady nenakonfigurujete, může se rozhodnout, jestli se má načíst soubory XAML v aplikaci Internet Explorer.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067147)  
  
  **Výchozí**: Zakázat 
  
- **Soubory ke stažení zóny Internetu aplikace Internet Explorer pro soubor automatické řádku.**  
  Nastavení této zásady určuje, jestli se uživatelům výzva pro stahování souborů bez zahájená uživatelem. Bez ohledu na toto nastavení, uživatelé dostanou dialogová okna Stažení souboru pro uživatelem iniciované soubory ke stažení. Pokud toto nastavení povolíte, uživatelům se zobrazí dialogové okno Stažení souboru pro pokusy o automatické stahování. Pokud zakážete nebo toto nastavení nemusíte konfigurovat, jsou blokovány stahování souborů, které nejsou v uživatelem iniciované a uživatelům se zobrazí oznamovací pruh místo dialogu stažení souboru. Uživatelům můžete pak kliknout na oznamovací pruh umožňuje výzva ke stažení souboru.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067117)  
  
  **Výchozí**: Zakázáno  
  
- **Upozornění zabezpečení aplikace Internet Explorer s omezením pomocí specifikátoru zóny pro potenciálně nebezpečná soubory**  
  Nastavení této zásady řídí, jestli se zobrazí zpráva "Otevření souboru – upozornění zabezpečení" když se uživatel pokusí otevřít spustitelné soubory nebo další potenciálně nebezpečná soubory (z intranetu sdílenou složku s použitím Průzkumníka souborů, například). Pokud povolíte toto nastavení zásad a nastavte rozevírací seznam na povolit, otevřete tyto soubory bez upozornění zabezpečení. Pokud nastavíte rozevíracího seznamu na příkazový řádek, zobrazí upozornění zabezpečení před otevřete soubory. Pokud nastavení této zásady zakážete, tyto soubory neotevírat. Pokud nastavení této zásady nenakonfigurujete, může uživatel nakonfigurovat způsob, jakým zpracovává tyto soubory do počítače. Ve výchozím nastavení jsou tyto soubory blokované v zóně s omezeným přístupem, povolené v zóně intranetu a místního počítače a nastavit na výzvu v zóně Internet a důvěryhodné.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2066797)  
  
  **Výchozí**: Zakázat  
  
- **Zóny Internetu aplikace Internet Explorer křížový filtr skriptování**  
  Tato zásada řídí, jestli se filtr skriptování mezi weby (XSS) odhalování a prevenci injektáže skriptu webů do webů v této zóně. Pokud nastavení této zásady povolíte, je zapnutá filtr skriptování mezi weby pro servery v této zóně a filtr XSS, pokusí se zablokovat injektáže skriptu webů. Pokud nastavení této zásady zakážete, XSS filtru je vypnuté pro servery v této zóně a Internet Explorer povoluje injektáže skriptu webů.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067053) 
  
  **Výchozí**: Enabled 
  
- **Aplikace Internet Explorer nouzového řešení ověření pomocí SSL3**  
  Nastavení této zásady umožňuje blokovat nezabezpečeného použití náhradní lokality pro protokol SSL 3.0. Když se povolí tyto zásady, aplikace Internet Explorer se pokusí připojit k webům pomocí protokolu SSL 3.0 nebo pod TLS 1.0 nebo vyšší v případě selhání. Doporučujeme vám, že není Povolit nezabezpečené zálohu prevence útok man-in-the-middle. Tato zásada nemá vliv, které bezpečnostní protokoly jsou povolené. Pokud tato zásada se používají výchozí systémové nastavení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067118)  
  
  **Výchozí**: Žádné weby  

- **Podpora šifrování aplikace Internet Explorer**  
  Nastavení této zásady umožňuje podporu pro zabezpečení TLS (Transport Layer) 1.0, TLS 1.1, TLS 1.2, vrstvy SSL (Secure Sockets) 2.0 nebo SSL 3.0 v prohlížeči vypnout. TLS a SSL jsou protokoly, které pomáhají chránit komunikace mezi prohlížečem a cílový server. Když se v prohlížeči se pokusí nastavit chráněné komunikaci s cílovým serverem, prohlížečem a serverem vyjednávání, které protokolu a verze se má použít. Prohlížečem a serverem pokus o porovnání druhé strany seznam podporovaných protokolů a verzí a vyberou upřednostňovaným shoda. Pokud nastavení této zásady povolíte, prohlížeče, vyjedná nebo nevyjednává tunelu šifrování pomocí metody šifrování, které jste vybrali v rozevíracím seznamu. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, může uživatel vybrat šifrování, které podporuje metodu v prohlížeči.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067057)

  **Výchozí**: položek: 2:  Verze protokolu TLS 1.1 a TLS verze 1.2  
  *Vyberte šipku dolů a zobrazte možnosti, které vyberete pro toto nastavení.*
  
- **Uzamčené obrazovky inteligentní zóny Internetu aplikace Internet Explorer**  
  Tato zásada, nastavení ovládacích prvků, zda filtr SmartScreen vyhledá stránky v této zóně na škodlivý obsah. Pokud nastavení této zásady povolíte, filtr SmartScreen prohledává stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady zakážete, nebude kontrolovat filtru SmartScreen stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, jestli kontrolovat filtru SmartScreen stránkách v této zóně na škodlivý obsah. Poznámka: V aplikaci Internet Explorer 7 nastavení této zásady určuje, zda filtr útoků Phishing kontrolovat stránkách v této zóně na škodlivý obsah.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067059)  
  
  **Výchozí**: Enabled 
  
- **Aplikace Internet Explorer s omezením pomocí specifikátoru zóny spuštění aplikace a soubory v elementu iFrame**  
  Nastavení této zásady umožňuje určit, zda aplikace mohou být spuštěny a soubory stáhnout z odkazu na element IFRAME ve formátu HTML stránek v této zóně. Pokud nastavení této zásady povolíte, uživatelé můžou spouštět aplikace a stahovat soubory z prvky IFRAME na stránkách v této zóně bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat zvolit, jestli se má spouštět aplikace a stahovat soubory z prvky IFRAME na stránkách v této zóně. Pokud nastavení této zásady zakážete, uživatelé nebudou moci spouštění aplikací a stahování souborů z prvky IFRAME na stránkách v této zóně. Pokud nastavení této zásady nenakonfigurujete, uživatelé nebudou moci spouštění aplikací a stahování souborů z prvky IFRAME na stránkách v této zóně.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067061)  
  
  **Výchozí**: Zakázat 
  
- **Aplikace Internet Explorer obejít upozornění SmartScreen běžné soubory**  
  Nastavení této zásady určuje, zda uživatel může obejít upozornění filtru SmartScreen. Filtr SmartScreen uživatele upozorní na spustitelné soubory, které uživatele aplikace Internet Explorer není běžně stáhnout z Internetu. Pokud nastavení této zásady povolíte, uživateli blokovat upozornění filtru SmartScreen. Pokud zakážete nebo není pro toto nastavení zásad, můžete uživateli obejít upozornění filtru SmartScreen.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067068)  
  
  **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer Internetová zóna blokování automaticky otevíraných oken**  
  Nastavení této zásady umožňuje určit, zda nežádoucí automaticky otevíraných oken. Automaticky otevíraná okna, které jsou otevřeny, když koncový uživatel klepne na odkaz nejsou blokované. Pokud nastavení této zásady povolíte, většina nežádoucích automaticky otevíraná okna bránit v zobrazení. Pokud nastavení této zásady zakážete, ji povolí automaticky otevíraná okna. Pokud nastavení této zásady nenakonfigurujete, většina nežádoucích automaticky otevíraná okna bránit v zobrazení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067069)  
  
  **Výchozí**: Povolení  
  
- **Aplikace Internet Explorer zpracovává konzistentní zpracování MIME**  
  Aplikace Internet Explorer obsahuje dynamické binární chování: komponenty, které zapouzdřují funkce specifická pro elementy HTML, které jsou připojeny. Tato zásada, nastavení ovládacích prvků, jestli je nastavení binární omezení zabezpečení chování zabránit nebo povolené. Pokud povolíte toto nastavení zásad, nebudou další binární chování pro procesy Průzkumníka souborů a prohlížeče Internet Explorer. Pokud nastavení této zásady zakážete, binární chování jsou povoleny pro procesy Průzkumníka souborů a prohlížeče Internet Explorer. Pokud nastavení této zásady nenakonfigurujete, nebudou další binární chování pro procesy Průzkumníka souborů a prohlížeče Internet Explorer.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067144)  
  
  **Výchozí**: Enabled  
  
- **Aplikace Internet Explorer omezená oprávnění java zóny**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, aplety jsou zakázané.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067132)  
  
  **Výchozí**: Zakázat java  
    
  
- **Internet Explorer ovládací prvky ActiveX v chráněném režimu**  
  Nastavení této zásady zabrání ve spuštění v chráněném režimu při zapnutém rozšířeným chráněným režimem ovládací prvky ActiveX. Pokud má uživatel ovládacího prvku ActiveX nainstalovány, který není kompatibilní s rozšířeným chráněným režimem a pokusí se načíst ovládací prvek webu, aplikace Internet Explorer upozorní uživatele a nabízí možnost spustit na web v pravidelných chráněný režim. Nastavení této zásady zakážete toto oznámení a vynutí všechny weby pro spuštění v rozšířeným chráněným režimem. Rozšířený chráněný režim nabízí další ochranu před škodlivým webům pomocí 64bitové procesy v 64bitových verzích Windows. Pro počítače se systémem nejméně Windows 8, rozšířeným chráněným režimem omezení, které aplikace Internet Explorer můžete číst z umístění v registru a systému souborů. Pokud je zapnuto rozšířeným chráněným režimem a uživatel se dodává přes web, který se pokusí načíst ovládací prvek ActiveX, který není kompatibilní s rozšířeným chráněným režimem, Internet Explorer upozorní uživatele a poskytuje možnost zakázat rozšířeným chráněným režimem pro Tento konkrétní web. Pokud nastavení této zásady povolíte, nebude se aplikace Internet Explorer dát uživateli možnost zakázat rozšířeným chráněným režimem. Všechny weby chráněný režim poběží v rozšířeným chráněným režimem. Pokud zakážete nebo není pro toto nastavení zásad, Internet Explorer upozorní uživatele a nabízí možnost spustit webů s nekompatibilní ovládacích prvků ActiveX v pravidelných chráněný režim.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067145)  
  
  **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer zakázané zóny načítání souborů XAML**  
  Toto nastavení zásad umožňuje spravovat načítání souborů Extensible Application Markup Language (XAML). XAML je založený na formátu XML deklarativní značkovací jazyk běžně používají k vytváření pro uživatelská rozhraní bohatá a grafiku, které využívají výhod Windows Presentation Foundation. Pokud povolíte toto nastavení zásad a nastavte rozevírací seznam na povolit, jsou automaticky načteny soubory XAML v aplikaci Internet Explorer. Toto chování nelze změnit uživatele. Pokud nastavíte rozevíracího seznamu na řádku, bude uživatel vyzván k načítání souborů XAML. Pokud nastavení této zásady zakážete, soubory XAML nejsou načtené v Internet Exploreru. Toto chování nelze změnit uživatele. Pokud nastavení této zásady nenakonfigurujete, může se rozhodnout, jestli se má načíst soubory XAML v aplikaci Internet Explorer.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067070)  
  
  **Výchozí**: Zakázat  
  
- **Zpracovává skriptované okno omezení zabezpečení aplikace Internet Explorer**  
  Aplikace Internet Explorer umožňuje skripty prostřednictvím kódu programu otevřete, změny velikosti a přemístění windows podle různých typů. Funkce zabezpečení okno omezení omezuje zobrazována místní okna a zakazuje skripty zobrazování windows ve kterých pruhy názvu a stavu nejsou viditelné pro uživatele nebo obfuskaci jiných Windows nadpis a stavové řádky. Pokud nastavení této zásady povolíte, jsou skriptované windows s omezeným přístupem pro všechny procesy. Pokud zakážete nebo není pro toto nastavení zásad, oken nejsou s omezeným přístupem.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067146)  
  
  **Výchozí**: Enabled   
  
- **Zakázané zóny Internet Explorer spustit ovládací prvky ActiveX a moduly plug-in**  
  Nastavení této zásady umožňuje určit, zda ovládací prvky ActiveX a moduly plug-in můžete spustit na stránkách z určené zóny. Pokud nastavení této zásady povolíte, můžete spustit ovládací prvky a moduly plug-in bez zásahu uživatele. Pokud jste vybrali v rozevíracím seznamu řádku, jsou uživatelé zvolit, jestli chce použít ovládací prvky ke správě nebo modulu plug-in pro spuštění. Pokud nastavení této zásady zakážete, ovládací prvky a moduly plug-in bránit spouštění. Pokud nastavení této zásady nenakonfigurujete, ovládací prvky a moduly plug-in bránit spouštění.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067114) 
  
  **Výchozí**: Zakázat  
  
- **Skript zóny Internet Exploreru s omezením pomocí specifikátoru, ovládací prvky ActiveX označeny jako bezpečné pro skriptování**  
  Nastavení této zásady umožňuje určit, zda ovládací prvek ActiveX označeny jako bezpečné pro skriptování, můžete pracovat pomocí skriptu. Pokud nastavení této zásady povolíte, skript interakce může dojít automaticky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat zvolit, jestli chcete povolit interakci skriptu. Pokud nastavení této zásady zakážete, nebude interakce skriptu ke kterým dochází. Pokud nastavení této zásady nenakonfigurujete, skript interakce je zabráněno ke kterým dochází.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067062)  
  
  **Výchozí**: Zakázat  
  
- **Možnosti přihlášení zóny Internet Exploreru s omezením pomocí specifikátoru**  
  Toto nastavení zásad umožňuje spravovat nastavení pro možnosti přihlášení. Pokud nastavení této zásady povolíte, můžete z následující možnosti přihlášení. 
  - *Anonymní* – anonymní přihlášení pro aplikaci zakázat ověřování pomocí protokolu HTTP a použít účet guest jenom pro protokol Common Internet File System (CIFS). 
  - *Řádek* – použití řádku pro uživatelské jméno a heslo pro uživatele dotazu pro ID uživatele a hesla. Jakmile je uživatel vyzván, tyto hodnoty je možné bez upozornění pro ostatní relace. 
  - *Automatické přihlášení pouze do zóny sítě Intranet* – pomocí této možnosti můžete uživatelům dotazu pro ID uživatele a hesla v jiné zóně. Jakmile je uživatel vyzván, tyto hodnoty je možné bez upozornění pro ostatní relace. 
  - *Automatické Přihlaste se pomocí aktuálního uživatelského jména a hesla*– pomocí této možnosti můžete pokusit přihlásit pomocí odpověď výzvy systému Windows NT (označované také jako ověřování protokolem NTLM). Pokud server podporuje odpověď výzvy systému Windows NT, přihlášení používá uživatelské sítě uživatelské jméno a heslo pro přihlášení. Pokud server nepodporuje odpověď výzvy systému Windows NT, uživatel vyzván k zadání uživatelského jména a hesla. 

  Pokud nastavení této zásady zakážete, přihlášení nastavená na *automatické přihlášení pouze do zóny sítě Intranet*. Pokud nastavení této zásady nenakonfigurujete, přihlášení nastavená na *výzvy* uživatelské jméno a heslo.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067110)  
  
  **Výchozí**: Anonymní  
  
- **Důvěryhodné zóny inicializovat a skript, který ovládací prvky ActiveX neoznačené jako bezpečné aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat ovládací prvky ActiveX neoznačené jako bezpečné. Pokud nastavení této zásady povolíte, ovládací prvky ActiveX spuštění načíst s parametry a skriptované bez nastavování objektu zabezpečení pro nedůvěryhodná data nebo skripty. Toto nastavení se nedoporučuje, s výjimkou zabezpečený a spravovaný zóny. Toto nastavení způsobí, že nebezpečné a bezpečné ovládací prvky k inicializaci a skripty, ignoruje ovládací prvky skriptu ActiveX označeny jako bezpečné pro skriptování – možnost. Pokud povolíte toto nastavení zásad a v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli chce použít ovládací prvek pro zatížení s parametry nebo skripty. Pokud nastavení této zásady zakážete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načtena s parametry nebo skripty. Pokud nastavení této zásady nenakonfigurujete, jsou uživatelé dotazovat, jestli chce použít ovládací prvek pro zatížení s parametry nebo skripty.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067137)  
  
  **Výchozí**: Zakázat  
  
- **Odvolání certifikátů serveru zkontrolujte aplikaci Internet Explorer**  
  Nastavení této zásady umožňuje určit, zda aplikace Internet Explorer se zkontrolovat stav odvolání certifikátů serverů. Certifikáty byly odvolány, když jsou rizikům, nebo již nejsou platné, a tato možnost chrání uživatelé před odesláním důvěrná data do lokality, který může být podvodné nebo nezabezpečenou. Pokud nastavení této zásady povolíte, Internet Explorer zkontroluje, pokud byl odvolán certifikát serveru. Pokud nastavení této zásady zakážete, nebude aplikace Internet Explorer zkontrolovat certifikáty serveru, pokud chcete zobrazit, pokud byl odvolán. Pokud nastavení této zásady nenakonfigurujete, nebudou aplikace Internet Explorer zkontrolovat certifikáty serveru, pokud chcete zobrazit, pokud byl odvolán.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067046)  
  
  **Výchozí**: Enabled 
  
- **Zóna Internetu aplikace Internet Explorer menší privilegované webů**  
  Nastavení této zásady umožňuje určit, zda webové stránky z méně privilegovaným zóny, jako jsou servery s omezeným přístupem, se můžete dostat do této zóny. Pokud nastavení této zásady povolíte, webové servery ze zóny méně privilegovaným můžete otevřít v nových oknech, nebo přejít do této zóny. Zóna zabezpečení se spustí bez další úroveň zabezpečení, které poskytuje ochranu před funkci zabezpečení ke zvýšení úrovně oprávnění zóny. Pokud v rozevíracím seznamu vyberte řádek, objeví se upozornění pro uživatele, které potenciálně nebezpečné navigace se použije. Pokud nastavení této zásady zakážete, nebudou další potenciálně škodlivé navigaci. Funkce zabezpečení aplikace Internet Explorer je na v této zóně úmluvu ochranu ze zóny zvýšení funkce správy. Pokud nastavení této zásady nenakonfigurujete, webové servery ze zóny méně privilegovaným můžete otevřít v nových oknech, nebo přejít do této zóny.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067109)  
  
  **Výchozí**: Zakázat  
  
- **Soubory ke stažení souboru s omezeným přístupem zóny Internet Exploreru**  
  Nastavení této zásady umožňuje určit, zda jsou povolena stahování souborů ze zóny. Tato možnost získá určené zóně stránky pomocí odkazu, způsobí stažení nejsou zónově, ze kterého se doručí souboru. Pokud nastavení této zásady povolíte, soubory můžete stáhnout ze zóny. Pokud nastavení této zásady zakážete, soubory nebudou stahují ze zóny. Pokud nastavení této zásady nenakonfigurujete, nebudou moci soubory stahují ze zóny.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067038)  
  
  **Výchozí**: Zakázat  
  
- **Zóny Internetu aplikace Internet Explorer spustit s podpisem Authenticode spolehlivé součásti .NET Framework**  
  Nastavení této zásady umožňuje určit, zda mohou být spuštěny součásti rozhraní .NET Framework, které jsou podepsané pomocí technologie Authenticode aplikace Internet Explorer. Mezi tyto komponenty patří spravované ovládací prvky, které odkazuje objektu značku a spravované spustitelné soubory, které na něj odkazovat z odkazu. Pokud nastavení této zásady povolíte, spustí aplikaci Internet Explorer podepsaný spravované součásti. Pokud v rozevíracím seznamu vyberte řádek, Internet Explorer vyzve uživatele k určení, jestli se má spouštět podepsané spravované součásti. Pokud nastavení této zásady zakážete, aplikace Internet Explorer nespustí, podepsaný spravované součásti. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer nespustí, podepsaný spravované součásti.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067033)  
  
  **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer zabránit za instalaci uživatelské ovládací prvky ActiveX**  
  Nastavení této zásady umožňuje zabránit v instalaci ovládací prvky ActiveX pro jednotlivé uživatele zvlášť. Pokud nastavení této zásady povolíte, ovládací prvky ActiveX nelze nainstalovat na jednotlivé uživatele. Pokud zakážete nebo není pro toto nastavení zásad, ovládací prvky ActiveX lze nainstalovat na jednotlivé uživatele.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067058)  
  
  **Výchozí**: Enabled  
  
- **Aplikace Internet Explorer zabránit správě filtru SmartScreen**  
  Nastavení této zásady zabrání uživateli ve správě filtru SmartScreen, který upozorní uživatele, pokud je známá podvodné pokusy o shromáždění osobních informací prostřednictvím "phishing" návštěvě webu, nebo je znám hostiteli malware. Pokud nastavení této zásady povolíte, uživatel není vyzván k zapnutí filtru SmartScreen. Všechny webové adresy, které nejsou na filtrech povolit seznamu jsou automaticky odesílány společnosti Microsoft bez výzvy pro uživatele. Pokud zakážete nebo není pro toto nastavení zásad, získá uživatel vyzván k rozhodování, jestli se má zapnutí filtru SmartScreen během prvního spuštění.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067135)  
  
  **Výchozí**: Povolení  
  
- **Aplikace Internet Explorer zpracovává MIME analýzy rozšíření bezpečnostní funkce**  
  Nastavení této zásady určuje, zda pro analýzu sítě Internet Explorer MIME zabrání povýšení soubor jednoho typu k více nebezpečné typ souboru. Pokud nastavení této zásady povolíte, MIME pro analýzu sítě nikdy povýšit soubor jednoho typu na více nebezpečné typ souboru. Pokud nastavení této zásady zakážete, aplikace Internet Explorer procesů vám umožní MIME monitorování podpora souboru jednoho typu na více nebezpečné typ souboru. Pokud nastavení této zásady nenakonfigurujete, MIME pro analýzu sítě nikdy podporovat soubor jednoho typu na více nebezpečné typ souboru.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067124)  
  
  **Výchozí**: Enabled  
  
- **Stažení aplikace Internet Explorer zakázané zóny podepsané ovládací prvky ActiveX**  
  Nastavení této zásady umožňuje určit, zda uživatelé mohou stáhnout podepsané ovládací prvky ActiveX ze stránky v zóně. Pokud tuto zásadu povolíte, uživatelé můžou Stahovat podepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli se má stáhnout ovládací prvky, které jsou podepsány vydavatelé, kteří nejsou důvěryhodné. Bezobslužná stažením kódu podepsány Důvěryhodní vydavatelé. Pokud nastavení zásad zakážete, podepsané ovládací prvky nelze stáhnout. Pokud nastavení této zásady nenakonfigurujete, uživateli se generuje dotaz na, jestli se má stáhnout ovládací prvky, které jsou podepsány vydavatelé, kteří nejsou důvěryhodné. Bezobslužná stažením kódu podepsány Důvěryhodní vydavatelé.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067120) 
  
  **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer automatické dokončování**  
  Tato funkce automatického dokončování můžete mějte na paměti a navrhují uživatelských jmen a hesel ve formulářích. Pokud povolíte toto nastavení, uživatel nemůže změnit "uživatelského jména a hesla na formulářích" nebo "výzvy k uložení hesla". Automatické dokončování funkce pro uživatelská jména a hesla na formulářích je zapnutá. Musíte se rozhodnout, jestli se má vybrat "výzvy k uložení hesla". Pokud toto nastavení zakážete uživatel nemůže změnit "uživatelského jména a hesla na formulářích" nebo "výzvy k uložení hesla". Funkci Automatické dokončování pro uživatelská jména a hesla na formulářích je vypnutý. Uživatel také nelze rozhodnout vyzváni k uložení hesla. Pokud toto nastavení nenakonfigurujete, má uživatel svobody zapnutí automatického dokončení zadání uživatelského jména a hesla ve formulářích a možnost zobrazení výzvy k uložení hesla. Pokud chcete zobrazit tuto možnost, uživatelé otevřít dialogové okno Možnosti Internetu, klikněte na kartu obsah a klikněte na tlačítko nastavení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067122)  
  
  **Výchozí**: Zakázáno  
  
- **Povolit zóny Internetu aplikace Internet Explorer VBscript ke spuštění**  
  Nastavení této zásady umožňuje určit, zda VBScript, můžete spustit na stránkách v určité zóny Internet Exploreru. Vaše možnosti jsou: 
  - *Povolit* -VBScript běží na stránkách v konkrétních oblastech, bez nutnosti zásahu. 
  - *Příkazový řádek* -zaměstnancům zobrazí výzva, jestli se má povolit VBScript ke spuštění v zóně. 
  - *Zakázat* -VBScript je zabráněno ve spuštění v zóně. Pokud zakážete nebo není pro toto nastavení zásad, bez nutnosti zásahu v určené zóně spouští VBScript.    

  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067119)  
  
  **Výchozí**: Zakázat  
  
- **Povolit zakázané zóny Internet Exploreru schválí jen tehdy, domény určený ORS ovládací prvky ActiveX**  
  Toto nastavení zásady řídí, jestli uživatel může spustit ovládací prvek ActiveX ORS na webech. Pokud nastavení této zásady povolíte, ovládací prvek ActiveX ORS nespustí z webů v této zóně. Pokud nastavení této zásady zakážete, ovládací prvek ActiveX ORS se spustí ze všech lokalit v této zóně.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067032)  
  
  **Výchozí**: Enabled  
  
- **Zóny důvěryhodných serverů Internet Exploreru při spuštění antimalwarové proti ovládací prvky ActiveX**  
  Nastavení této zásady určuje, jestli aplikace Internet Explorer se spouští antimalwarové programy proti ovládací prvky ActiveX, a zkontrolujte, zda jsou bezpečné pro načtení na stránkách. Pokud nastavení této zásady povolíte, nebude Internet Exploreru zkontrolujte s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Uživatele můžete vypnout toto chování zapnout nebo vypnout pomocí nastavení zabezpečení aplikace Internet Explorer.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067115)  
  
  **Výchozí**: Zakázáno 
  
- **Oprávnění aplikace Internet Explorer místního počítače zóny java**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, je oprávnění nastaveno na střední bezpečnosti.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067113)  
  
  **Výchozí**: Zakázat java 
  
- **Zóny intranetu aplikace Internet Explorer nespustí antimalwarové proti ovládací prvky ActiveX**  
  Nastavení této zásady určuje, jestli aplikace Internet Explorer se spouští antimalwarové programy proti ovládací prvky ActiveX, a zkontrolujte, zda jsou bezpečné pro načtení na stránkách. Pokud nastavení této zásady povolíte, nebude Internet Exploreru zkontrolujte s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, nebudou Internet Exploreru zkontrolujte s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Uživatele můžete vypnout toto chování zapnout nebo vypnout pomocí nastavení zabezpečení aplikace Internet Explorer.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067138)  
  
  **Výchozí**: Zakázáno  

- **Internet Explorer s omezením pomocí specifikátoru skriptlety zóny**  
  Nastavení této zásady umožňuje určit, zda uživatel může spustit skriptlety. Pokud nastavení této zásady povolíte, uživatel může spustit skriptlety. Pokud nastavení této zásady zakážete, uživatel nemůže spustit skriptlety. Pokud nastavení této zásady nenakonfigurujete, uživateli můžete povolit nebo zakázat skriptlety.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067112)  
  
  **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer procesy oznamovací pruh**  
  Nastavení této zásady umožňuje určit, zda oznamovací pruh se zobrazí pro procesy aplikace Internet Explorer, když se nainstaluje soubor nebo kód s omezeným přístupem. Ve výchozím nastavení zobrazí se oznamovací pruh pro procesy aplikace Internet Explorer. Pokud nastavení této zásady povolíte, zobrazí se oznamovací pruh pro procesy, které Internet Explorer. Pokud nastavení této zásady zakážete, oznamovací pruh se nezobrazí pro procesy aplikace Internet Explorer. Pokud nastavení této zásady nenakonfigurujete, oznamovací pruh nezobrazuje pro Internet Explorer procesy.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067139)  
  
  **Výchozí**: Enabled  
  
- **Stažení zóny Internetu aplikace Internet Explorer podepsané ovládací prvky ActiveX**  
  Nastavení této zásady umožňuje určit, zda uživatelé mohou stáhnout podepsané ovládací prvky ActiveX ze stránky v zóně. Pokud tuto zásadu povolíte, uživatelé můžou Stahovat podepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli se má stáhnout ovládací prvky, které jsou podepsány vydavatelé, kteří nejsou důvěryhodné. Bezobslužná stažením kódu podepsány Důvěryhodní vydavatelé. Pokud nastavení zásad zakážete, podepsané ovládací prvky nelze stáhnout. Pokud nastavení této zásady nenakonfigurujete, uživateli se generuje dotaz na, jestli se má stáhnout ovládací prvky, které jsou podepsány vydavatelé, kteří nejsou důvěryhodné. Bezobslužná stažením kódu podepsány Důvěryhodní vydavatelé.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067064)  
  
  **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer zakázané zóny SmartScreen**  
  Tato zásada, nastavení ovládacích prvků, zda filtr SmartScreen vyhledá stránky v této zóně na škodlivý obsah. Pokud nastavení této zásady povolíte, filtr SmartScreen prohledává stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady zakážete, nebude kontrolovat filtru SmartScreen stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, jestli kontrolovat filtru SmartScreen stránkách v této zóně na škodlivý obsah. Poznámka: V aplikaci Internet Explorer 7 nastavení této zásady určuje, zda filtr útoků Phishing kontrolovat stránkách v této zóně na škodlivý obsah.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067034)  
  
  **Výchozí**: Enabled  
  
- **Odebrat aplikaci Internet Explorer spustili toto tlačítko čas pro zastaralé ovládací prvky ActiveX**  
  Nastavení této zásady umožňuje zabránit uživatelům v zobrazení na tlačítko "Spustit nyní" a ve spuštění konkrétních zastaralé ovládacích prvků ActiveX v Internet Exploreru. Pokud nastavení této zásady povolíte, uživatelé nebudou "Spustit nyní" na tlačítko Zobrazit upozornění, které se zobrazí, když aplikace Internet Explorer zablokuje zastaralé ovládacího prvku ActiveX. Pokud zakážete nebo není pro toto nastavení zásady, uživatelům se zobrazí tlačítko "Spustit nyní" na upozornění, které se zobrazí, když aplikace Internet Explorer zablokuje zastaralé ovládacího prvku ActiveX. Kliknutím na toto tlačítko umožňuje uživateli spustit jednou zastaralé ovládacího prvku ActiveX. Další informace najdete v tématu "Zastaralé ovládací prvky ActiveX" v knihovně Internet Explorer TechNet.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067123)  
  
  **Výchozí**: Enabled 
  
- **Spuštění aplikace Internet Explorer zóny a soubory v elementu iframe**  
  Nastavení této zásady umožňuje určit, zda aplikace mohou být spuštěny a soubory stáhnout z odkazu na element IFRAME ve formátu HTML stránek v této zóně. Pokud nastavení této zásady povolíte, uživatelé můžou spouštět aplikace a stahovat soubory z prvky IFRAME na stránkách v této zóně bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat zvolit, jestli se má spouštět aplikace a stahovat soubory z prvky IFRAME na stránkách v této zóně. Pokud nastavení této zásady zakážete, uživatelé nebudou moci spouštění aplikací a stahování souborů z prvky IFRAME na stránkách v této zóně. Pokud nastavení této zásady nenakonfigurujete, dotazovat jsou uživatelé zvolit, jestli se má spouštět aplikace a stahovat soubory z prvky IFRAME na stránkách v této zóně.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067020)  
  
  **Výchozí**: Zakázat 
  
- **Zóny s omezeným přístupem v Internet Exploreru přejděte v různých doménách windows a snímků**  
  Nastavení této zásady umožňuje nastavit možnosti pro přetažení obsah z jedné domény do jiné domény, pokud zdroj a cíl nacházejí v různých systému windows. Pokud povolíte toto nastavení zásad a klikněte na možnost povolit, uživatelé můžete přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl nacházejí v různých systému windows. Uživatelé nemohou změnit toto nastavení. Pokud povolíte toto nastavení zásad a klikněte na možnost zakázat, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl v různých systému windows. Uživatelé nemohou změnit toto nastavení. V Internet Exploreru 10 Pokud nastavení této zásady zakážete nebo nekonfigurujte, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí v různých systému windows. Uživatelé mohou změnit toto nastavení v dialogovém okně Možnosti Internetu. V aplikaci Internet Explorer 9 a starší Pokud tato zásada nebo nekonfigurujte, uživatelé můžete přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí v různých systému windows. Uživatelé nemohou změnit toto nastavení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067050)  
  
  **Výchozí**: Zakázat  
  
- **Inteligentní obrazovce zóny Internetu aplikace Internet Explorer**  
  Tato zásada, nastavení ovládacích prvků, zda filtr SmartScreen vyhledá stránky v této zóně na škodlivý obsah. Pokud nastavení této zásady povolíte, filtr SmartScreen prohledává stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady zakážete, nebude kontrolovat filtru SmartScreen stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, jestli kontrolovat filtru SmartScreen stránkách v této zóně na škodlivý obsah. Poznámka: V aplikaci Internet Explorer 7 nastavení této zásady určuje, zda filtr útoků Phishing kontrolovat stránkách v této zóně na škodlivý obsah.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067047)  
  
  **Výchozí**: Enabled  
  
- **Uzamčené oprávnění pro jazyk java zóny důvěryhodných serverů Internet Exploreru**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, aplety jsou zakázané.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067142)  
  
  
  **Výchozí**: Zakázat java 
  
- **Aplikace Internet Explorer zkontrolovat podpisy stažených programů**  
  Nastavení této zásady umožňuje určit, zda aplikace Internet Explorer zkontroluje digitální podpisy (který určuje vydavatele softwaru podepsané barvy a ověřuje nebyl byl změněn nebo úmyslně) v počítačích uživatelů před stažením spustitelné programy. Pokud nastavení této zásady povolíte, Internet Explorer zkontroluje digitální podpisy spustitelné programy a zobrazí jejich identity před stažením do počítačů uživatelů. Pokud nastavení této zásady zakážete, nebude aplikace Internet Explorer zkontrolujte digitální podpisy spustitelné programy nebo zobrazení jejich identity před stažením do počítačů uživatelů. Pokud tuto zásadu nenakonfigurujete, nebudou aplikace Internet Explorer zkontrolujte digitální podpisy spustitelné programy nebo zobrazení jejich identity před stažením do počítačů uživatelů.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067051)  
  
  **Výchozí**: Enabled  
  
- **Aplikace Internet Explorer s omezením pomocí specifikátoru skriptování v zóně ovládacích prvků webového prohlížeče**  
  Nastavení této zásady určuje, zda na stránku můžete řídit vložené WebBrowser – ovládací prvky pomocí skriptu. Pokud nastavení této zásady povolíte, je povolen skript přístup k ovládacímu prvku WebBrowser. Pokud nastavení této zásady zakážete, není povolen přístup skript do ovládacího prvku WebBrowser. Pokud nastavení této zásady nenakonfigurujete, uživateli můžete povolit nebo zakázat přístup skript do ovládacího prvku WebBrowser. Ve výchozím nastavení je povolen skript přístup k ovládacímu prvku WebBrowser pouze v místním počítači a zóny intranetu.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067098)  
  
  **Výchozí**: Zakázáno  
  
- **Zóny s omezeným přístupem v Internet Exploreru křížový filtr skriptování**  
  Tato zásada řídí, jestli se filtr skriptování mezi weby (XSS) odhalování a prevenci injektáže skriptu webů do webů v této zóně. Pokud nastavení této zásady povolíte, je zapnutá filtr skriptování mezi weby pro servery v této zóně a filtr XSS, pokusí se zablokovat injektáže skriptu webů. Pokud nastavení této zásady zakážete, XSS filtru je vypnuté pro servery v této zóně a Internet Explorer povoluje injektáže skriptu webů.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067178)  
  
  **Výchozí**: Enabled  
  
- **Binární s omezeným přístupem zóny Internet Exploreru a chování skriptu**  
  Toto nastavení zásad umožňuje spravovat chování dynamické binární soubor a skriptu: komponenty, které zapouzdřují funkce specifická pro elementy HTML, do kterých byla připojena. Pokud nastavení této zásady povolíte, chování binárních souborů a skriptů jsou k dispozici. Pokud jste vybrali v rozevíracím seznamu schválení správcem, jsou k dispozici pouze chování, které jsou uvedeny v chování schválení správce v části zásady omezení zabezpečení binární chování. Pokud nastavení této zásady zakážete, binární soubor a skript chování nejsou dostupné, pokud aplikace implementovali vlastní security manager. Pokud nastavení této zásady nenakonfigurujete, binární soubor a skript chování nejsou dostupné, pokud aplikace implementovali vlastní security manager.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067224)  
  
  **Výchozí**: Zakázat  
  
- **Kontrola nastavení zabezpečení aplikace Internet Explorer**  
  Nastavení této zásady vypne funkce Kontrola nastavení zabezpečení, která zkontroluje nastavení zabezpečení aplikace Internet Explorer můžete určit, kdy nastavení ohrozit aplikace Internet Explorer. Pokud nastavení této zásady povolíte, tato funkce je vypnuta. Pokud zakážete nebo není pro toto nastavení zásad, tato funkce je zapnutá.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067182)  
  
  **Výchozí**: Enabled  
  
- **Upozornění v Internet Exploreru zóny zabezpečení Internetu potenciálně nebezpečná souborů**  
  Nastavení této zásady řídí, jestli se zobrazí zpráva "Otevření souboru – upozornění zabezpečení" když se uživatel pokusí otevřít spustitelné soubory nebo další potenciálně nebezpečná soubory (z intranetu sdílenou složku s použitím Průzkumníka souborů, například). Pokud povolíte toto nastavení zásad a nastavte rozevírací seznam na povolit, otevřete tyto soubory bez upozornění zabezpečení. Pokud nastavíte rozevíracího seznamu na příkazový řádek, zobrazí upozornění zabezpečení před otevřete soubory. Pokud nastavení této zásady zakážete, tyto soubory neotevírat. Pokud nastavení této zásady nenakonfigurujete, může uživatel nakonfigurovat způsob, jakým zpracovává tyto soubory do počítače. Ve výchozím nastavení jsou tyto soubory blokované v zóně s omezeným přístupem, povolené v zóně intranetu a místního počítače a nastavit na výzvu v zóně Internet a důvěryhodné.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067204)  
  
  **Výchozí**: Výzva  
  
- **Oprávnění java zóny intranetu aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, je oprávnění nastaveno na střední bezpečnosti.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067206)  
  
  **Výchozí**: Vysoké zabezpečení 
  
- **Aplikace Internet Explorer blokovat zastaralé ovládací prvky ActiveX**   
  Nastavení této zásady určuje, zda aplikace Internet Explorer bloky konkrétní zastaralé ovládací prvky ActiveX. Zastaralé ovládací prvky ActiveX jsou nikdy blokována v zóně intranetu. Pokud nastavení této zásady povolíte, přestane aplikace Internet Explorer blokovat zastaralé ovládací prvky ActiveX. Pokud zakážete nebo není pro toto nastavení zásad, pokračuje aplikace Internet Explorer blokovat konkrétní zastaralé ovládací prvky ActiveX. Další informace najdete v tématu "Zastaralé ovládací prvky ActiveX" v knihovně Internet Explorer TechNet.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067203)  
  
  **Výchozí**: Enabled  
  
- **Aplikace Internet Explorer s omezením pomocí specifikátoru zóny blokování automaticky otevíraných oken**  
  Nastavení této zásady umožňuje určit, zda nežádoucí automaticky otevíraných oken. Automaticky otevíraná okna, které jsou otevřeny, když koncový uživatel klepne na odkaz nejsou blokované. Pokud nastavení této zásady povolíte, většina nežádoucích automaticky otevíraná okna bránit v zobrazení. Pokud nastavení této zásady zakážete, ji povolí automaticky otevíraná okna. Pokud nastavení této zásady nenakonfigurujete, většina nežádoucích automaticky otevíraná okna bránit v zobrazení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067180)  
  
  **Výchozí**: Povolení  
  
- **Omezení pro protokol zabezpečení aplikace Internet Explorer procesy MK**  
  Nastavení zásad omezení zabezpečení protokolu MK snižuje zabráněním protokolu MK možností útoku. Prostředky, které jsou hostované na protokol MK se nezdaří. Pokud nastavení této zásady povolíte, MK protokol je zabráněno z Průzkumníka souborů a prohlížeče Internet Explorer a prostředky, které jsou hostované na protokol MK se nezdaří. Pokud nastavení této zásady zakážete, aplikace můžete použít protokol MK rozhraní API. Prostředky, které jsou hostované na protokol MK bude fungovat pro procesy Průzkumníka souborů a prohlížeče Internet Explorer. Pokud nastavení této zásady nenakonfigurujete, MK protokol je zabráněno z Průzkumníka souborů a prohlížeče Internet Explorer a prostředky, které jsou hostované na protokol MK se nezdaří.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067179)  
  
  **Výchozí**: Enabled  
  
- **Oprávnění pro jazyk java aplikace Internet Explorer důvěryhodné zóny**   
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, je oprávnění nastaveno nízká bezpečnosti.  
    [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067200)  
  
  **Výchozí**: Vysoké zabezpečení  
  
- **Aplikace Internet Explorer s omezením pomocí specifikátoru zóny skriptování aplety**  
  Nastavení této zásady umožňuje určit, zda jsou vystaveny aplety skripty v rámci zóny. Pokud nastavení této zásady povolíte, dostanete skripty aplety automaticky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, jsou zvolit, jestli se tak, aby pro přístup k aplety dotazovat uživatele. Pokud nastavení této zásady zakážete, nemají přístup k aplety skripty. Pokud nastavení této zásady nenakonfigurujete, nemají přístup k aplety skripty.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067202)  
  
  **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer uzamčen oprávnění pro jazyk java zakázané zóny**   
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, aplety jsou zakázané.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067181)  
  
  **Výchozí**: Zakázat java 
  
- **Povolit zóny Internetu aplikace Internet Explorer schválí jen tehdy, domén používat ovládací prvky ActiveX**   
  Toto nastavení zásady řídí, jestli uživatel je vyzván k povolit ovládacích prvků ActiveX ke spuštění ve službě websites než webu, nainstalované ovládacího prvku ActiveX. Pokud nastavení této zásady povolíte, bude uživatel vyzván, ovládací prvky ActiveX lze spustit z webů v této zóně. Uživatel může zvolit, aby ovládací prvek pro spuštění z aktuální lokality nebo ze všech lokalit. Pokud nastavení této zásady zakážete, uživatel nebude zobrazí výzva ActiveX podle webu a ovládací prvky ActiveX lze spustit ze všech lokalit v této zóně.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067091)  
  
  **Výchozí**: Enabled  
  
- **Aplikace Internet Explorer zahrnout všechny síťové cesty**  
  Aplikace Internet Explorer zahrnout všechny síťové cesty.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067090)  
  
  **Výchozí**: Zakázáno 
  
- **Zóny Internetu aplikace Internet Explorer chráněný režim**  
  Nastavení této zásady umožňuje zapnout v chráněném režimu. Chráněný režim pomáhá chránit aplikace Internet Explorer z odstranění zneužité chyby zabezpečení snížením umístění, které aplikace Internet Explorer můžete zapsat do registru a systému souborů. Pokud nastavení této zásady povolíte, chráněný režim zapnutý. Uživatele nelze vypnout chráněný režim. Pokud nastavení této zásady zakážete, chráněný režim je vypnutý. Uživatele nelze zapnout chráněný režim. Pokud nastavení této zásady nenakonfigurujete, uživatel může zapnout nebo vypnout chráněný režim.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067171)  
  
  **Výchozí**: Povolení 
  
- **Inicializovat zóny Internetu aplikace Internet Explorer a skript, který ovládací prvky ActiveX neoznačené jako bezpečné**  
  Toto nastavení zásad umožňuje spravovat ovládací prvky ActiveX neoznačené jako bezpečné. Pokud nastavení této zásady povolíte, ovládací prvky ActiveX spuštění načíst s parametry a skriptované bez nastavování objektu zabezpečení pro nedůvěryhodná data nebo skripty. Toto nastavení se nedoporučuje, s výjimkou zabezpečený a spravovaný zóny. Toto nastavení způsobí, že nebezpečné a bezpečné ovládací prvky k inicializaci a skripty, ignoruje ovládací prvky skriptu ActiveX označeny jako bezpečné pro skriptování – možnost. Pokud povolíte toto nastavení zásad a v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli chce použít ovládací prvek pro zatížení s parametry nebo skripty. Pokud nastavení této zásady zakážete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načtena s parametry nebo skripty. Pokud nastavení této zásady nenakonfigurujete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načtena s parametry nebo skripty.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067170)  
  
  **Výchozí**: Zakázat 
  
- **Aplikace Internet Explorer uzamčené obrazovky inteligentní zakázané zóny**   
  Tato zásada, nastavení ovládacích prvků, zda filtr SmartScreen vyhledá stránky v této zóně na škodlivý obsah. Pokud nastavení této zásady povolíte, filtr SmartScreen prohledává stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady zakážete, nebude kontrolovat filtru SmartScreen stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, jestli kontrolovat filtru SmartScreen stránkách v této zóně na škodlivý obsah. Poznámka: V aplikaci Internet Explorer 7 nastavení této zásady určuje, zda filtr útoků Phishing kontrolovat stránkách v této zóně na škodlivý obsah.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067092)  
  
  **Výchozí**: Enabled  
  
- **Detekce chybového ukončení Internet Exploreru**  
  Toto nastavení zásad umožňuje spravovat funkce rozpoznávání chyb správy doplňku. Pokud nastavení této zásady povolíte, při selhání v aplikaci Internet Explorer se chovat nalezen ve Windows XP Professional Service Pack 1 a starší, konkrétně k vyvolání zasílání zpráv o chybách Windows. Všechna nastavení zásad pro zasílání zpráv o chybách Windows pokračovat v používání. Pokud zakážete nebo není pro toto nastavení zásad, funkce rozpoznávání chyb pro správu doplňku je funkční.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067094)  
  
  **Výchozí**: Zakázáno  
  
- **Oprávnění java zóny Internetu aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, je oprávnění nastaveno na vysokou bezpečnost.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067174)  
  
  **Výchozí**: Zakázat java  
  
- **Aplikace Internet Explorer s omezením pomocí specifikátoru aktivní skriptování v zóně**  
  Nastavení této zásady umožňuje určit, zda je spuštěn kód skriptu na stránkách v zóně. Pokud nastavení této zásady povolíte, můžete automaticky spouštět kód skriptu na stránkách v zóně. Pokud v rozevíracím seznamu vyberte řádek, jsou dotazováním uživatelé vybrat, jestli povolíte kód skriptu na stránkách v zóně ke spuštění. Pokud zakážete toto nastavení zásad, kód skriptu na stránkách v zóně zabránily spuštění. Pokud nastavení této zásady nenakonfigurujete, je kód skriptu na stránkách v zóně zabránily spuštění.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067172)  
  
  **Výchozí**: Zakázat  
  
- **Možnosti přihlášení zóny Internetu aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat nastavení pro možnosti přihlášení. Pokud nastavení této zásady povolíte, můžete z následující možnosti přihlášení. Anonymní Přihlaste se k zakázání ověřování pomocí protokolu HTTP a použijte účet hosta jenom pro protokol Common Internet File System (CIFS). Vyzve k zadání uživatelského jména a hesla pro uživatele dotazu pro ID uživatele a hesla. Jakmile je uživatel vyzván, tyto hodnoty je možné tiše zbytek relace. Automatické přihlášení pouze do zóny sítě Intranet uživatelům dotazu pro ID uživatele a hesla v jiné zóně. Jakmile je uživatel vyzván, tyto hodnoty je možné bez upozornění pro ostatní relace. Automatické Přihlaste se pomocí aktuálního uživatelského jména a hesla se pokusit přihlásit pomocí odpověď výzvy systému Windows NT (označované také jako ověřování protokolem NTLM). Pokud server podporuje odpověď výzvy systému Windows NT, přihlášení používá uživatelské sítě uživatelské jméno a heslo pro přihlášení. Pokud server nepodporuje odpověď výzvy systému Windows NT, uživatel vyzván k zadání uživatelského jména a hesla. Pokud nastavení této zásady zakážete, přihlášení nastavená na automatické protokolu na pouze do zóny sítě Intranet. Pokud nastavení této zásady nenakonfigurujete, přihlášení je nastavena na automatické přihlášení do pouze do zóny sítě Intranet.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067194)  
  
  **Výchozí**: Výzva  
  
- **Povolit jazyk vbscript ke spuštění s omezeným přístupem zóny Internet Exploreru**   
  Nastavení této zásady umožňuje určit, zda VBScript může běžet na stránkách z určené zóny v aplikaci Internet Explorer. Pokud jste vybrali v rozevíracím seznamu povolit, VBScript spustit bez zásahu uživatele. Pokud jste vybrali v rozevíracím seznamu řádku, jsou uživatelé vyzváni k vybrat, jestli povolíte VBScript ke spuštění. Pokud jste vybrali v rozevíracím seznamu zakázat, VBScript zabránily spuštění. Pokud nechcete nastavit či vypnout nastavení této zásady, VBScript zabránily spuštění.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067173)  
  
  **Výchozí**: Zakázat  
  
- **Zóny Internetu aplikace Internet Explorer tažením obsah z jiných domén systému windows**  
  Nastavení této zásady umožňuje nastavit možnosti pro přetažení obsah z jedné domény do jiné domény, pokud zdroj a cíl nacházejí v různých systému windows. Pokud povolíte toto nastavení zásad a klikněte na možnost povolit, uživatelé můžete přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl nacházejí v různých systému windows. Uživatelé nemohou změnit toto nastavení. Pokud povolíte toto nastavení zásad a klikněte na možnost zakázat, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl v různých systému windows. Uživatelé nemohou změnit toto nastavení. V Internet Exploreru 10 Pokud nastavení této zásady zakážete nebo nekonfigurujte, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí v různých systému windows. Uživatelé mohou změnit toto nastavení v dialogovém okně Možnosti Internetu. V aplikaci Internet Explorer 9 a starší Pokud tato zásada nebo nekonfigurujte, uživatelé můžete přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí v různých systému windows. Uživatelé nemohou změnit toto nastavení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067093)  
  
  **Výchozí**: Zakázáno 
  
- **Inicializovat zóny intranetu aplikace Internet Explorer a skript, který ovládací prvky ActiveX neoznačené jako bezpečné**  
  Toto nastavení zásad umožňuje spravovat ovládací prvky ActiveX neoznačené jako bezpečné. Pokud nastavení této zásady povolíte, ovládací prvky ActiveX spuštění načíst s parametry a skriptované bez nastavování objektu zabezpečení pro nedůvěryhodná data nebo skripty. Toto nastavení se nedoporučuje, s výjimkou zabezpečený a spravovaný zóny. Toto nastavení způsobí, že nebezpečné a bezpečné ovládací prvky k inicializaci a skripty, ignoruje ovládací prvky skriptu ActiveX označeny jako bezpečné pro skriptování – možnost. Pokud povolíte toto nastavení zásad a v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli chce použít ovládací prvek pro zatížení s parametry nebo skripty. Pokud nastavení této zásady zakážete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načtena s parametry nebo skripty. Pokud nastavení této zásady nenakonfigurujete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načtena s parametry nebo skripty.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067175)  
  
  **Výchozí**: Zakázat 
  
- **Aplikace Internet Explorer stahování příloh**  
  Toto nastavení zásad znemožní uživateli s skříně (soubory příloh) stažené z informačního kanálu na počítači uživatele. Pokud nastavení této zásady povolíte, uživateli nelze nastavit synchronizační modul informačního kanálu stáhnout přílohu prostřednictvím stránky vlastností informačního kanálu. Vývojář nelze změnit nastavení stahování přes rozhraní API informačního kanálu. Pokud zakážete nebo není pro toto nastavení zásad, může uživatel nastavit synchronizační modul informačního kanálu stáhnout přílohu prostřednictvím stránky vlastností informačního kanálu. Vývojář můžete změnit nastavení stahování přes rozhraní API informačního kanálu.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067245)  
  
  **Výchozí**: Zakázáno  
  
- **Zakázané zóny Internet Explorer stahování bez znaménka ovládací prvky ActiveX**  
  Nastavení této zásady umožňuje určit, zda uživatelé mohou stáhnout nepodepsané ovládací prvky ActiveX ze zóny. Takový kód je potenciálně škodlivých, zejména v případě, že pocházejí z nedůvěryhodné zóny. Pokud povolíte toto nastavení zásad, můžou uživatelé spouštět nepodepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, uživatelé se dotazováním vyberte, jestli chcete povolit spuštění bez znaménka ovládacího prvku. Pokud nastavení této zásady zakážete, uživatelé nemůžou spouštět nepodepsané ovládací prvky. Pokud nastavení této zásady nenakonfigurujete, uživatelé nemůžou spouštět nepodepsané ovládací prvky.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067177)  
  
  **Výchozí**: Zakázat  
  
- **Zóny Internetu aplikace Internet Explorer přetáhnout obsah z jiných domén v rámci systému windows**  
  Nastavení této zásady umožňuje určit, zda uživatelé mohou stáhnout nepodepsané ovládací prvky ActiveX ze zóny. Takový kód je potenciálně škodlivých, zejména v případě, že pocházejí z nedůvěryhodné zóny. Pokud povolíte toto nastavení zásad, můžou uživatelé spouštět nepodepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, uživatelé se dotazováním vyberte, jestli chcete povolit spuštění bez znaménka ovládacího prvku. Pokud nastavení této zásady zakážete, uživatelé nemůžou spouštět nepodepsané ovládací prvky. Pokud nastavení této zásady nenakonfigurujete, uživatelé nemůžou spouštět nepodepsané ovládací prvky.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067095)  
  
  **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer procesy omezit Active X install**   
  Nastavení této zásady umožňuje aplikacím hostujícím ovládací prvek webového prohlížeče k blokování Automatické dotazování instalace ovládacího prvku ActiveX. Pokud nastavení této zásady povolíte, bude ovládací prvek webového prohlížeče blokovat Automatické dotazování instalace ovládacího prvku ActiveX pro všechny procesy. Pokud zakážete nebo není pro toto nastavení zásad, ovládací prvek webového prohlížeče nebude blokovat Automatické dotazování instalace ovládacího prvku ActiveX pro všechny procesy.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067250)  
  
  **Výchozí**: Enabled  
  
- **Skriptlety zóny Internetu aplikace Internet Explorer**  
  Nastavení této zásady umožňuje určit, zda uživatel může spustit skriptlety. Pokud nastavení této zásady povolíte, uživatel může spustit skriptlety. Pokud nastavení této zásady zakážete, uživatel nemůže spustit skriptlety. Pokud nastavení této zásady nenakonfigurujete, uživateli můžete povolit nebo zakázat skriptlety.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067176)  
  
  **Výchozí**: Zakázat  
  
- **Zóny s omezeným přístupem v Internet Exploreru přetahování nebo zkopírujte a vložte soubory**  
  Nastavení této zásady umožňuje určit, zda uživatele lze přetáhnout soubory nebo kopírování a vkládání souborů ze zdroje v rámci zóny. Pokud nastavení této zásady povolíte, uživatelé můžete přetáhnout soubory nebo zkopírovat a vkládat soubory z této zóny automaticky. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat rozhodnout, jestli jej přetáhnout nebo zkopírovat soubory z této zóny. Pokud nastavení této zásady zakážete, uživatelé nebudou moci soubory přetažením nebo zkopírováním a vložením soubory z této zóny. Pokud nastavení této zásady nenakonfigurujete, jsou uživatelé dotazovat rozhodnout, jestli jej přetáhnout nebo zkopírovat soubory z této zóny.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067096)  
  
  **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer softwaru při podpis je neplatný.**  
  Nastavení této zásady umožňuje určit, zda je software, jako je například ovládací prvky ActiveX a stahování souborů, můžete nainstalovat nebo spustit uživatel i v případě, že podpis je neplatný. Neplatný podpis může znamenat, že někdo nemanipuloval s souboru. Pokud nastavení této zásady povolíte, uživatelům se výzva k nainstalovat nebo spustit soubory s neplatným podpisem. Pokud nastavení této zásady zakážete, uživatelé nemohou spustit nebo instalovat soubory s neplatným podpisem. Pokud tuto zásadu nenakonfigurujete, uživatelé mohou spustit nebo instalovat soubory s neplatným podpisem.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067201)
  
  **Výchozí**: Zakázáno  
  
- **Internet Explorer s omezením pomocí specifikátoru zóny kopírování a vkládání přes skript**  
  Nastavení této zásady umožňuje určit, zda skripty můžete provést operaci schránky (například vyjmout, kopírovat a vložit) v určité oblasti. Pokud nastavení této zásady povolíte, skriptu můžete provést operaci schránky. Pokud v rozevíracím seznamu vyberte řádek, uživatelé se generuje dotaz na tom, jestli se má provést operace schránky. Pokud nastavení této zásady zakážete, skriptu nelze provést operaci schránky. Pokud nastavení této zásady nenakonfigurujete, skriptu nelze provést operaci schránky.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067165)  
  
  **Výchozí**: Zakázat  
  
- **Zóny s omezeným přístupem v Internet Exploreru proveďte operaci přetažení obsah z jiných domén přes windows**  
  Nastavení této zásady umožňuje nastavit možnosti pro přetažení obsah z jedné domény do jiné domény, pokud zdroj a cíl nacházejí v různých systému windows. Pokud povolíte toto nastavení zásad a klikněte na možnost povolit, uživatelé můžete přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl nacházejí v různých systému windows. Uživatelé nemohou změnit toto nastavení. Pokud povolíte toto nastavení zásad a klikněte na možnost zakázat, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl v různých systému windows. Uživatelé nemohou změnit toto nastavení. V Internet Exploreru 10 Pokud nastavení této zásady zakážete nebo nekonfigurujte, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí v různých systému windows. Uživatelé mohou změnit toto nastavení v dialogovém okně Možnosti Internetu. V aplikaci Internet Explorer 9 a starší Pokud tato zásada nebo nekonfigurujte, uživatelé můžete přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí v různých systému windows. Uživatelé nemohou změnit toto nastavení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067166)   

  **Výchozí**: Zakázáno  
  
- **Přidání serverů uživatele aplikace Internet Explorer**  
  Zabrání uživatelům přidávat nebo odebírat servery ze zóny zabezpečení. Zóny zabezpečení je skupina webových stránek se stejnou úrovní zabezpečení. Pokud tuto zásadu povolit, nastavení serveru správy pro zóny zabezpečení jsou zakázané. (Zobrazíte Správa lokality nastavení zóny zabezpečení, v dialogovém okně Možnosti Internetu klikněte na kartu zabezpečení a potom klikněte na tlačítko weby.) Pokud tato zásada nebo nemusíte konfigurovat, uživatelé mohou přidávat webové servery nebo odebrat servery ze zóny důvěryhodných serverů a serverů s omezeným přístupem, a upravit nastavení pro zóny místního intranetu. Tato zásada zabraňuje uživatelům možnost měnit nastavení řízení lokality pro zóny zabezpečení nastavená správcem. Poznámka: "Zakázat na stránce zabezpečení" zásady (umístěné v \User Configuration\Administrative pro správu\Součásti systému Windows\Internet Explorer\Ovládací ovládací panely), tím se odebere z rozhraní na kartě zabezpečení, mají přednost před tuto zásadu. Pokud je povolena, tato zásada je ignorována. Další informace naleznete "zóny zabezpečení: Použití pouze nastavení počítače"zásad.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067167)  
  
  **Výchozí**: Zakázáno  
  
- **Skript zóny Internetu aplikace Internet Explorer inicioval systému windows**  
  Toto nastavení zásad umožňuje spravovat omezení iniciované skriptu automaticky otevíraná okna a okna, která zahrnují panely názvu a stavu. Pokud nastavení této zásady povolíte, nebude v této zóně použít Windows omezení zabezpečení. Zóna zabezpečení se spustí bez další úroveň zabezpečení poskytované touto funkcí. Pokud nastavení této zásady zakážete, je to možné škodlivých akcí, které jsou součástí iniciované skriptu automaticky otevíraná okna a okna, která zahrnují panely názvu a stavu nelze spustit. Tuto funkci zabezpečení aplikace Internet Explorer je na v této zóně určený nastavení pro proces řízení funkci skripty Windows bezpečnostní omezení. Pokud nastavení této zásady nenakonfigurujete, je to možné škodlivých akcí, které jsou součástí iniciované skriptu automaticky otevíraná okna a okna, která zahrnují panely názvu a stavu nelze spustit. Tuto funkci zabezpečení aplikace Internet Explorer je na v této zóně určený nastavení pro proces řízení funkci skripty Windows bezpečnostní omezení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067088)  
  
  **Výchozí**: Zakázáno  
  
- **Zóny zabezpečení aplikace Internet Explorer použijte pouze nastavení počítače**  
  Informace o zóně zabezpečení se vztahuje na všechny uživatele stejném počítači. Zóny zabezpečení je skupina webových stránek se stejnou úrovní zabezpečení. Pokud tuto zásadu povolit, budou změny, které uživatel provede do zóny zabezpečení platí pro všechny uživatele tohoto počítače. Pokud tato zásada nebo nemusíte konfigurovat, uživatelé stejném počítači můžete vytvořit vlastní nastavení zóny zabezpečení. Pomocí této zásady zajistíte, že nastavení zóny zabezpečení platí jednotně na stejném počítači a nemusíte se liší od uživatelů. Další informace naleznete "zóny zabezpečení: Nepovolovat uživatelům změnit zásady" zásady.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067086)  
  
  **Výchozí**: Enabled  
  
- **Aplikace Internet Explorer uzamčen oprávnění pro jazyk java zóna místního počítače**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, aplety jsou zakázané.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067253) 
  
  **Výchozí**: Zakázat java 
  
- **Zóny s omezeným přístupem v Internet Exploreru nespouštějte antimalwarové proti ovládací prvky ActiveX**   
  Nastavení této zásady určuje, jestli aplikace Internet Explorer se spouští antimalwarové programy proti ovládací prvky ActiveX, a zkontrolujte, zda jsou bezpečné pro načtení na stránkách. Pokud nastavení této zásady povolíte, nebude Internet Exploreru zkontrolujte s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Uživatele můžete vypnout toto chování zapnout nebo vypnout pomocí nastavení zabezpečení aplikace Internet Explorer.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067089)
  
  **Výchozí**: Zakázáno  
  
- **Spustit s podpisem authenticode spolehlivé součásti .NET Framework s omezeným přístupem zóny Internet Exploreru**  
  Nastavení této zásady umožňuje určit, zda mohou být spuštěny součásti rozhraní .NET Framework, které jsou podepsané pomocí technologie Authenticode aplikace Internet Explorer. Mezi tyto komponenty patří spravované ovládací prvky, které odkazuje objektu značku a spravované spustitelné soubory, které na něj odkazovat z odkazu. Pokud nastavení této zásady povolíte, spustí aplikaci Internet Explorer podepsaný spravované součásti. Pokud v rozevíracím seznamu vyberte řádek, Internet Explorer vyzve uživatele k určení, jestli se má spouštět podepsané spravované součásti. Pokud nastavení této zásady zakážete, aplikace Internet Explorer nespustí, podepsaný spravované součásti. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer nespustí, podepsaný spravované součásti.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067169)  
  
  **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer s omezením pomocí specifikátoru zóny přístup ke zdrojům dat**  
  Nastavení této zásady umožňuje určit, zda aplikace Internet Explorer můžete přistupovat k datům z jiné zóny zabezpečení pomocí Microsoft XML Parser (MSXML) nebo objekty ADO (ActiveX Data OBJECTS). Pokud nastavení této zásady povolíte, uživatelé můžou načítat stránku v oblasti, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat zvolit, jestli se má povolit stránky načíst v zóně, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud nastavení této zásady zakážete, uživatelé nelze načíst stránku v oblasti, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud nastavení této zásady nenakonfigurujete, uživateli nelze načíst stránku v oblasti, která používá pro přístup k datům z jiné lokality v zóně MSXML nebo ADO.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067161)  
  
  **Výchozí**: Zakázat 
  
- **Zóny Internetu aplikace Internet Explorer při spuštění antimalwarové proti ovládací prvky ActiveX**  
  Nastavení této zásady určuje, jestli aplikace Internet Explorer se spouští antimalwarové programy proti ovládací prvky ActiveX, a zkontrolujte, zda jsou bezpečné pro načtení na stránkách. Pokud nastavení této zásady povolíte, nebude Internet Exploreru zkontrolujte s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Uživatele můžete vypnout toto chování zapnout nebo vypnout pomocí nastavení zabezpečení aplikace Internet Explorer.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067162)  
  
  **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer internetové zóny kopírování a vkládání přes skript**  
  Nastavení této zásady umožňuje určit, zda skripty můžete provést operaci schránky (například vyjmout, kopírovat a vložit) v určité oblasti. Pokud nastavení této zásady povolíte, skriptu můžete provést operaci schránky. Pokud v rozevíracím seznamu vyberte řádek, uživatelé se generuje dotaz na tom, jestli se má provést operace schránky. Pokud nastavení této zásady zakážete, skriptu nelze provést operaci schránky. Pokud nastavení této zásady nenakonfigurujete, skriptu můžete provést operaci schránky.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067084)  
  
  **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer použijte Active X instalační služba**  
  Nastavení této zásady umožňuje určit, jak jsou nainstalovány – ovládací prvky ActiveX. Pokud nastavení této zásady povolíte, ovládací prvky ActiveX jsou nainstalovány pouze v případě, že je k dispozici instalační služba ActiveX a není nakonfigurovaná k povolení instalace ovládacích prvků ActiveX. Pokud zakážete nebo není pro toto nastavení zásad, nainstaluje se ovládací prvky ActiveX, včetně uživatelských ovládacích prvků, prostřednictvím standardního procesu instalace.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067163)
  
  **Výchozí**: Enabled  
  
- **Aplikace Internet Explorer zpracovává ochranu proti zvýšení oprávnění zóny**  
  Na každé webové stránky, otevře se aplikace Internet Explorer umístí omezení. Omezení jsou závislé na umístění webové stránky (Internetu, intranetu, zóna místního počítače a tak dále). Například webové stránky v místním počítači máte nejmíň bezpečnostní omezení a jsou v místním počítači zóně zabezpečení místního počítače zóna prvotní cíle uživateli se zlými úmysly. Pokud nastavení této zásady povolíte, se dají chránit všechny zóny ze zóny ke zvýšení úrovně oprávnění pro všechny procesy. Pokud zakážete nebo není pro toto nastavení zásady, procesy než Internet Explorer nebo hodnotami uvedenými v seznamu proces přijímat žádná taková ochrana.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067160)  
  
  **Výchozí**: Enabled  
  
- **Zóny Internetu aplikace Internet Explorer stahování bez znaménka ovládací prvky ActiveX**   
  Nastavení této zásady umožňuje určit, zda uživatelé mohou stáhnout nepodepsané ovládací prvky ActiveX ze zóny. Takový kód je potenciálně škodlivých, zejména v případě, že pocházejí z nedůvěryhodné zóny. Pokud povolíte toto nastavení zásad, můžou uživatelé spouštět nepodepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, uživatelé se dotazováním vyberte, jestli chcete povolit spuštění bez znaménka ovládacího prvku. Pokud nastavení této zásady zakážete, uživatelé nemůžou spouštět nepodepsané ovládací prvky. Pokud nastavení této zásady nenakonfigurujete, uživatelé nemůžou spouštět nepodepsané ovládací prvky.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067325)
  
  **Výchozí**: Zakázat  
  
- **Zóny Internetu aplikace Internet Explorer přejděte v různých doménách systému windows a snímků**   
  Toto nastavení zásad umožňuje spravovat otevírání windows a snímků a přístup k aplikacím v různých doménách. Pokud nastavení této zásady povolíte, uživatelé mohou otevřít windows a snímků z jiných domén a přístup k aplikacím z jiných domén. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli se má povolit windows a snímky s cílem získat přístup k aplikacím z jiných domén. Pokud nastavení této zásady zakážete, nelze otevřít uživatelům windows a snímky s cílem získat přístup k aplikacím z různých domén. Pokud nastavení této zásady nenakonfigurujete, uživatelé mohou otevřít windows a snímků z jiných domén a přístup k aplikacím z jiných domén.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067083)  
  
  **Výchozí**: Zakázat  
  
- **Aktualizace zóny Internetu aplikace Internet Explorer na stavovém řádku prostřednictvím skriptu**  
  Nastavení této zásady umožňuje určit, zda skript můžete aktualizovat stavového řádku v rámci zóny. Pokud nastavení této zásady povolíte, můžete aktualizovat skripty stavový řádek. Pokud zakážete nebo není pro toto nastavení zásad, skriptu není povoleno aktualizovat na stavovém řádku.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067087)  
  
  **Výchozí**: Zakázáno  
  
- **Zóny Internet Exploreru s omezeným přístupem zahrnují místní cesty při nahrávání souborů do serveru**  
  Toto nastavení zásady řídí, jestli místní cesta informace se odešle, když uživatel je nahrát soubor přes formulář HTML. Pokud se pošle informace o místní cestu a některé informace mohou neúmyslně odhalena k serveru. Soubory odeslané z plochy uživatele, může obsahovat uživatelské jméno jako součást cesty. Pokud nastavení této zásady povolíte, informace o cestě se odešle, když uživatel je nahrát soubor přes formulář HTML. Pokud nastavení této zásady zakážete, informace o cestě se odebere, pokud uživatel odesílá soubory přes formulář HTML. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, zda informace o cestě se odešle, když při nahrávání souborů přes formulář HTML. Ve výchozím nastavení je odeslána informace o cestě.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067085)  
  
  **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer procesy omezit stahování souborů**   
  Nastavení této zásady umožňuje aplikacím hostujícím ovládací prvek webového prohlížeče k blokování Automatické dotazování stahování souborů, které nejsou iniciované uživatelem. Pokud nastavení této zásady povolíte, bude ovládací prvek webového prohlížeče blokovat Automatické dotazování stahování souborů, které nejsou uživatelem iniciované pro všechny procesy. Pokud nastavení této zásady zakážete, nebude blokovat Automatické dotazování stahování souborů, které nejsou uživatelem iniciované pro všechny procesy ovládací prvek WebBrowser.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067164)  
  
  **Výchozí**: Enabled  
  
- **Povolit zakázané zóny Internet Exploreru schválí jen tehdy, domény použít ovládací prvky ActiveX**   
  Toto nastavení zásady řídí, jestli uživatel je vyzván k povolit ovládacích prvků ActiveX ke spuštění ve službě websites než webu, nainstalované ovládacího prvku ActiveX. Pokud nastavení této zásady povolíte, bude uživatel vyzván, ovládací prvky ActiveX lze spustit z webů v této zóně. Uživatel může zvolit, aby ovládací prvek pro spuštění z aktuální lokality nebo ze všech lokalit. Pokud nastavení této zásady zakážete, uživatel nebude zobrazí výzva ActiveX podle webu a ovládací prvky ActiveX lze spustit ze všech lokalit v této zóně.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067233)  
  
  **Výchozí**: Enabled  
  
- **Inicializace s omezeným přístupem zóny Internet Exploreru a skript, který ovládací prvky ActiveX neoznačené jako bezpečné**  
  Toto nastavení zásad umožňuje spravovat ovládací prvky ActiveX neoznačené jako bezpečné. Pokud nastavení této zásady povolíte, ovládací prvky ActiveX spuštění načíst s parametry a skriptované bez nastavování objektu zabezpečení pro nedůvěryhodná data nebo skripty. Toto nastavení se nedoporučuje, s výjimkou zabezpečený a spravovaný zóny. Toto nastavení způsobí, že nebezpečné a bezpečné ovládací prvky k inicializaci a skripty, ignoruje ovládací prvky skriptu ActiveX označeny jako bezpečné pro skriptování – možnost. Pokud povolíte toto nastavení zásad a v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli chce použít ovládací prvek pro zatížení s parametry nebo skripty. Pokud nastavení této zásady zakážete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načtena s parametry nebo skripty. Pokud nastavení této zásady nenakonfigurujete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načtena s parametry nebo skripty.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067097)  
  
  **Výchozí**: Zakázat  
  
- **Změna zásad uživatele aplikace Internet Explorer**  
  Zabrání uživatelům možnost měnit nastavení zóny zabezpečení. Zóny zabezpečení je skupina webových stránek se stejnou úrovní zabezpečení. Pokud tuto zásadu povolit, jsou zakázané tlačítko Vlastní úroveň a úroveň zabezpečení posuvník na kartě zabezpečení v dialogovém okně Možnosti Internetu. Pokud tato zásada nebo nemusíte konfigurovat, uživatelé mohou změnit nastavení zóny zabezpečení. Tato zásada zabraňuje uživatelům možnost měnit nastavení zóny zabezpečení nastavená správcem. Poznámka: "Zakázat na stránce zabezpečení" zásady (umístěné v \User Configuration\Administrative pro správu\Součásti systému Windows\Internet Explorer\Ovládací ovládací panely), tím se odebere z aplikace Internet Explorer v Ovládacích panelech na kartě zabezpečení, má přednost před Tyto zásady. Pokud je povolena, tato zásada je ignorována. Další informace naleznete "zóny zabezpečení: Použití pouze nastavení počítače"zásad.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067155)  
    
  **Výchozí**: Zakázáno  
  
- **Chráněný režim s omezeným přístupem zóny Internet Exploreru**  
  Nastavení této zásady umožňuje zapnout v chráněném režimu. Chráněný režim pomáhá chránit aplikace Internet Explorer z odstranění zneužité chyby zabezpečení snížením umístění, které aplikace Internet Explorer můžete zapsat do registru a systému souborů. Pokud nastavení této zásady povolíte, chráněný režim zapnutý. Uživatele nelze vypnout chráněný režim. Pokud nastavení této zásady zakážete, chráněný režim je vypnutý. Uživatele nelze zapnout chráněný režim. Pokud nastavení této zásady nenakonfigurujete, uživatel může zapnout nebo vypnout chráněný režim.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067080)  
  
  **Výchozí**: Povolení  
  
- **Trvalost dat uživatele zóny Internetu aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat uchovávání informací v prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk. Když se uživatel vrátí na stránku trvalé, je možné obnovit stav stránky, pokud nastavení této zásady je správně nakonfigurovaný. Pokud nastavení této zásady povolíte, uživatelé můžete zachovat informace o prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk. Pokud nastavení této zásady zakážete, uživatelé nelze uchovávat informace v prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk. Pokud nastavení této zásady nenakonfigurujete, uživatelé mohou uchovávat informace v prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067156)  
  
  **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer skriptování zóny Internetu ovládacích prvků webového prohlížeče**  
 
  Nastavení této zásady určuje, zda na stránku můžete řídit vložené WebBrowser – ovládací prvky pomocí skriptu. Pokud nastavení této zásady povolíte, je povolen skript přístup k ovládacímu prvku WebBrowser. Pokud nastavení této zásady zakážete, není povolen přístup skript do ovládacího prvku WebBrowser. Pokud nastavení této zásady nenakonfigurujete, uživateli můžete povolit nebo zakázat přístup skript do ovládacího prvku WebBrowser. Ve výchozím nastavení je povolen skript přístup k ovládacímu prvku WebBrowser pouze v místním počítači a zóny intranetu.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067157)  
  
  **Výchozí**: Zakázáno  
  
- **Trvalost dat uživatele s omezením pomocí specifikátoru aplikace Internet Explorer zóny**  
  Toto nastavení zásad umožňuje spravovat uchovávání informací v prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk. Když se uživatel vrátí na stránku trvalé, je možné obnovit stav stránky, pokud nastavení této zásady je správně nakonfigurovaný. Pokud nastavení této zásady povolíte, uživatelé můžete zachovat informace o prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk. Pokud nastavení této zásady zakážete, uživatelé nelze uchovávat informace v prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk. Pokud nastavení této zásady nenakonfigurujete, uživateli nelze uchovávat informace v prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067081)  
  
  **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer uzamčen oprávnění java zóny intranetu**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, aplety jsou zakázané.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067082)  
  
  **Výchozí**: Zakázat java  
  
- **Internet Explorer rozšířeného chráněný režim**  
  Rozšířený chráněný režim nabízí další ochranu před škodlivým webům pomocí 64bitové procesy v 64bitových verzích Windows. Pro počítače se systémem nejméně Windows 8, rozšířeným chráněným režimem omezení, které aplikace Internet Explorer můžete číst z umístění v registru a systému souborů. Pokud nastavení této zásady povolíte, rozšířeným chráněným režimem zapnutý. Všechny zóny s povoleným režimem chráněné použije rozšířeným chráněným režimem. Uživatelé nebudou moct zakázat rozšířeným chráněným režimem. Pokud nastavení této zásady zakážete, rozšířeným chráněným režimem je vypnutý. Všechny zóny s povoleným režimem chráněné budou používat verzi chráněný režim zavedený aplikace Internet Explorer 7 pro Windows Vista. Pokud tuto zásadu nenakonfigurujete, uživateli můžete zapnout nebo vypnout rozšířeným chráněným režimem na kartě Upřesnit v dialogovém okně Možnosti Internetu.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067158)  
  
  **Výchozí**: Enabled  
  
- **Aplikace Internet Explorer obejít upozornění SmartScreen**  
  Nastavení této zásady určuje, zda uživatel může obejít upozornění filtru SmartScreen. Filtr SmartScreen uživatele upozorní na spustitelné soubory, které uživatele aplikace Internet Explorer není běžně stáhnout z Internetu. Pokud nastavení této zásady povolíte, uživateli blokovat upozornění filtru SmartScreen. Pokud zakážete nebo není pro toto nastavení zásad, můžete uživateli obejít upozornění filtru SmartScreen.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067159)  
  
  **Výchozí**: Zakázáno  
  
- **Aktualizace metadat zóny Internet Exploreru s omezením pomocí specifikátoru**  
  Nastavení této zásady umožňuje určit, zda prohlížeče uživatele je možné přesměrovat do jiné webové stránky, pokud autor webové stránky používá nastavení Meta Refresh (značky) pro přesměrování prohlížeče na jiný web. Pokud nastavení této zásady povolíte, prohlížeče uživatele, který načte stránku obsahující aktivní nastavení Meta Refresh můžete přesměrovat na jinou webovou stránku. Pokud nastavení této zásady zakážete, prohlížeče uživatele, který načte stránku obsahující aktivní nastavení Meta Refresh nelze přesměrovat na jinou webovou stránku. Pokud nastavení této zásady nenakonfigurujete, prohlížeče uživatele, který načte stránku obsahující aktivní nastavení Meta Refresh nelze přesměrovat na jinou webovou stránku.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067154)  
  
  **Výchozí**: Zakázáno  
  
## <a name="local-policies-security-options"></a>Možnosti místní zásady zabezpečení
Další informace najdete v tématu [zásady CSP – LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) v dokumentaci k Windows. 

- **Omezení anonymní přístup k pojmenované kanály a sdílené složky**  
  Když je povoleno, toto nastavení zabezpečení omezuje anonymní přístup ke sdíleným složkám a kanálům k nastavením pro: (1) pojmenované kanály, které lze přistupovat anonymně sdílené složky (2), které se dá přistupovat anonymně.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067212)  
  
  **Výchozí**: Ano  
  
- **Minimální zabezpečení relace pro NTLM SSP podle serverů**  
  Toto nastavení zabezpečení umožňuje serveru požadovat vyjednávání 128bitové šifrování a/nebo NTLMv2 relace zabezpečení. Tyto hodnoty jsou závislé na hodnotě nastavení zabezpečení úroveň ověřování pro systém LAN Manager. Možnosti: Vyžadovat NTLMv2 relace zabezpečení: Připojení se nezdaří, pokud není vyjedná integrity zprávy. Vyžadovat 128bitové šifrování. Pokud není vyjedná silné šifrování (128-bit), připojení se nezdaří.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067246) 
  
  **Výchozí**: Vyžadovat NTLM V2 a 128bitové šifrování  
  
- **Počet minut nečinnosti zámek obrazovky, dokud se aktivuje šetřič obrazovky**  
  Systém Windows zaznamená nečinnost relace přihlášení, a pokud neaktivní doba překračuje limit nečinnosti, pak se spustí šetřič obrazovky, který relaci uzamkne.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067210)  
  
  **Výchozí**: 15
  
- **Vyžadovat klient vždy digitálně podepsat komunikaci** toto nastavení zabezpečení určuje, zda veškerý provoz zabezpečený kanál iniciovaných člena domény musí být podepsána nebo zašifrována. Když počítač připojí k doméně, vytvoří se účet počítače. Heslo účtu počítače je při spuštění systému používá k vytvoření zabezpečeného kanálu s řadičem domény pro příslušné domény. Tento zabezpečený kanál slouží k provádění operací, jako je protokol NTLM předávání ověřování, LSA SID/názvu vyhledávání a další. Toto nastavení určuje, zda veškerý provoz zabezpečený kanál iniciovaná členem domény, splňuje minimální požadavky na zabezpečení. Konkrétně určuje, zda veškerý provoz zabezpečený kanál tím, že člena domény musí být podepsána nebo zašifrována. Pokud je tato zásada povolená, nebude zabezpečený kanál vytvořen, pokud se vyjedná podepisování nebo šifrování veškeré komunikace zabezpečený kanál. Pokud tato zásada je zakázána, je šifrování a se vyjedná podepisování veškerého provozu zabezpečený kanál s řadičem domény. v takovém případě úroveň podepisování a šifrování závisí na verzi řadičem domény a nastavení z následujících dvou zásady: Člen domény: Digitálně zašifrovat data zabezpečeného kanálu (Pokud je to možné) člen domény: Digitálně podepsat data zabezpečeného kanálu (Pokud je to možné).  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067187) 
  
  **Výchozí**: Ano
  
- **Úroveň ověřování**  
  Toto nastavení zabezpečení určuje, který protokol ověřování požadavku a odpovědi se používá pro přihlášení k síti. Tato volba ovlivňuje úroveň ověřování protokolu používané klienty, úroveň zabezpečení relace vyjednávat a úroveň ověřování přijal servery následujícím způsobem:  
  - *Odeslání odpovědi LM a NTLM* – klienti používají ověřování LM a NTLM a nikdy NTLMv2 relace zabezpečení; přijmout LM, ověřování protokolů NTLM a ověřování NTLMv2 řadiče domény. 
  - *Odeslat LM a protokol NTLM – NTLMv2 ponechat* – klienti používat ověřování LM a NTLM a NTLMv2 relace zabezpečení, pokud je server podporuje; přijmout LM, ověřování protokolů NTLM a ověřování NTLMv2 řadiče domény. 
  - *Poslat odpověď protokolu NTLM pouze* – klienti používají pouze ověřování NTLM a NTLMv2 relace zabezpečení, pokud je server podporuje; přijmout LM, ověřování protokolů NTLM a ověřování NTLMv2 řadiče domény. 
  - *Poslat odpověď NTLMv2 pouze* – klienti používat jenom ověřování NTLMv2 a NTLMv2 relace zabezpečení, pokud je server podporuje; přijmout LM, ověřování protokolů NTLM a ověřování NTLMv2 řadiče domény. 
  - *Odeslat pouze NTLMv2 odpovědi. Odmítnout LM* – klienti používat jenom ověřování NTLMv2 a NTLMv2 relace zabezpečení, pokud je server podporuje; řadiče domény odmítnout LM (přijímat pouze ověřování NTLM a ověřování NTLMv2). 
  - *Odeslat pouze NTLMv2 odpovědi. Odmítnout LM a NTLM* – klienti používat jenom ověřování NTLMv2 a NTLMv2 relace zabezpečení, pokud je server podporuje; řadiče domény odmítnout LM a NTLM (přijímat pouze ověřování NTLM verze 2).  

  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067189)   
    
  **Výchozí**: Odeslat pouze NTLMv2 odpovědi. Odmítnout LM a NTLM
  
- **Zabráníte klientům v odesílání nešifrovaná hesla serverům SMB třetích stran**  
  Pokud je povolené toto nastavení zabezpečení, přesměrovače zprávy bloku SMB (Server) posílat nešifrovaná hesla serverům SMB mimo Microsoft, které nepodporují šifrování hesel během ověřování. Odesílání nešifrovaná hesla je bezpečnostním rizikem.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067235)  
  
  **Výchozí**: Ano
  
- **Vyžadovat po serveru vždy digitálně podepíše komunikace**  
  Toto nastavení zabezpečení určuje, zda klient SMB pokouší vyjednat podepisování paketů SMB. Protokol server message block (SMB) poskytuje základ pro sdílení Microsoft souborů a tiskáren a mnoho dalších síťových operací, jako je vzdálené správy Windows. Aby se zabránilo útokům man-in-the-middle úpravě paketů SMB při přenosu, protokolu SMB podporuje digitálnímu podepisování paketů SMB. Nastavení této zásady určuje, zda klient SMB pokouší při připojení k serveru SMB podepisování paketů SMB vyjednávat. Pokud je toto nastavení povolené, klient sítě Microsoft požádá server, aby po nastavení relace podepisování paketů SMB. Pokud je na serveru podepisování paketů povolené, podepisování paketů se vyjedná. Pokud tyto zásady zakážou, klient SMB nikdy vyjednat podepisování paketů SMB.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067319)  
  
  **Výchozí**: Ano
  
- **Chování výzvy ke zvýšení úrovně oprávnění správce**  
  Toto nastavení zásady řídí chování výzvy ke zvýšení oprávnění pro správce. Možnosti: 
    - *Zvýšit oprávnění bez dotazu* – umožňuje privilegované účty se provést operaci, která vyžaduje zvýšení oprávnění bez nutnosti souhlas nebo přihlašovací údaje. Poznámka: Tuto možnost použijte pouze v nejvíce omezených prostředích. 
    - *Příkazový řádek pro přihlašovací údaje na zabezpečené ploše* – Pokud operace vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván na zabezpečené ploše zadejte privilegovaných uživatelské jméno a heslo. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s nejvyšší dostupná oprávnění uživatele. 
    - *Vyzvat k souhlas na zabezpečené ploše* – Pokud operace vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván na zabezpečené ploše a vyberte Povolit nebo odepřít. Pokud si uživatel vybere povolení, operace pokračuje s nejvyšší dostupná oprávnění uživatele. 
    - *Výzva pro pověření* – Pokud operace vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván k zadání uživatelské jméno správce a heslo. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s příslušnými oprávněními. 
    - *Výzva k vyjádření souhlasu* – Pokud operace vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván k výběru povolení nebo odepření. Pokud si uživatel vybere povolení, operace pokračuje s nejvyšší dostupná oprávnění uživatele.  
    - *Vyzvat k souhlas pro binární soubory bez Windows* – při operaci pro aplikaci od jiných výrobců vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván na zabezpečené ploše a vyberte Povolit nebo odepřít. Pokud si uživatel vybere povolení, operace pokračuje s nejvyšší dostupná oprávnění uživatele. 
  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067215)   
  
  **Výchozí**: Požádat o souhlas na zabezpečené ploše
  
- **Klienty založené na minimální zabezpečení relace pro NTLM SSP**  
  Toto nastavení umožňuje klientovi tak, aby vyžadovala vyjednávání 128bitové šifrování a/nebo NTLMv2 relace zabezpečení. Tyto hodnoty jsou závislé na hodnotě nastavení zabezpečení úroveň ověřování pro systém LAN Manager. Možnosti:
  - *Vyžadovat NTLMv2 relace zabezpečení* – připojení se nezdaří, pokud není vyjednaný protokolem NTLMv2. 
  - *Vyžadovat 128bitové šifrování* – připojení se nezdaří, pokud není vyjedná silné šifrování (128-bit).
  - *Vyžadovat NTLMv2 a 128bitové šifrování*.  

  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067324)  

  **Výchozí**: Vyžadovat šifrování NTLM V2 128
  
- **Chování při vyjmutí čipové karty**  
    Toto nastavení zabezpečení určuje, co se stane, když se čipová karta přihlášeného uživatele se odebere ze čtečky čipových karet. Možnosti:
     - *Žádná akce*. 
     - *Zamknout pracovní stanici* -pracovní stanice uzamkne při odebrání čipové karty, uživatelé si můžou zůstat zálohovacím jejich čipové karty s nimi a přitom zachovává chráněné relace.
     - *Vynutit odhlášení* – uživatel je automaticky odhlášen při odebrání čipové karty.
     - *Odpojit relaci vzdálené plochy* – odebrání čipové karty odpojí relaci bez odhlášení uživatele. To umožňuje uživateli vložení čipové karty a obnovení relace později nebo v jiném čipových karet odpojena počítači, aniž byste museli znovu přihlašovat. Pokud je relace místní, funguje tato zásada stejně jako možnost Zamknout pracovní stanici.
  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067331) 
    
  **Výchozí**: Zamknout pracovní stanici
  
- **Blok anonymní výčty účtů SAM a sdílených složek**  
  Toto nastavení zabezpečení určuje, jestli se má povolit anonymní výčet SAM, účty a sdílené složky. Windows umožňuje anonymním uživatelům provádět určité aktivity, jako je například výčet názvů účtů domén a sdílených síťových složek. To je praktické, například, pokud chce správce udělit přístup uživatelům v důvěryhodné doméně, která nebude spravovat vzájemnou důvěryhodnost. Pokud nechcete povolit anonymní výčet SAM, účty a sdílené složky, nastavte tuto zásadu na *Ano*.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067191)  
  
  **Výchozí**: Ano
  
- **Blok vzdáleného přihlášení s prázdným heslem**  
  Toto nastavení zabezpečení určuje, jestli místní účty, které nejsou chráněné heslem je použít k přihlášení z umístění jiných než konzole fyzického počítače. Pokud je povoleno, musíte použít místní účty, které nejsou chráněné heslem klávesnice počítače pro přihlášení. 

  *Upozornění*: Počítače, které nejsou ve fyzicky zabezpečeném umístění by měl vždy prosazujte zásady silných hesel pro všechny místní uživatelské účty. Jinak každý, kdo má fyzický přístup k počítači může přihlásit pomocí uživatelského účtu, který nemá heslo. To je obzvláště důležité pro přenosné počítače. 

  Pokud použijete tuto zásadu zabezpečení Everyone skupině, nikdo přihlášení prostřednictvím vzdálené plochy. Toto nastavení nemá vliv přihlášení pomocí účtů domény. Je možné pro aplikace, které používají Vzdálená interaktivní přihlášení obejít tato nastavení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067219)  
  
  **Výchozí**: Ano
  
- **Standardní uživatel chování výzvy ke zvýšení úrovně oprávnění**  
  Toto nastavení zásady řídí chování výzvy ke zvýšení oprávnění pro standardní uživatele. 
  - *Automaticky zamítnout požadavky na zvýšení* – Pokud operace vyžaduje zvýšení úrovně oprávnění, konfigurovatelné přístup odepřen, zobrazí se chybová zpráva. Organizace, na kterém běží stolní počítače, protože standardní uživatel může zvolit tohoto nastavení může snížit volání služby HelpDesk. 
  - *Příkazový řádek pro přihlašovací údaje na zabezpečené ploše* – Pokud operace vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván na zabezpečené ploše zadejte jiné uživatelské jméno a heslo. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s příslušnými oprávněními. 
  - *Výzva pro pověření* – Pokud operace vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván k zadání uživatelské jméno správce a heslo. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s příslušnými oprávněními.  

  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067183)  
  
  **Výchozí**: Automaticky zamítnout požadavky na zvýšení
  
- **Vyžaduje režim schválení správcem pro správce**  
  Toto nastavení zásady řídí chování všechna nastavení zásad řízení uživatelských účtů (UAC) v počítači. Pokud změníte toto nastavení zásad, musíte restartovat počítač. Možnosti:   
  - *Není nakonfigurováno* -režim schválení správcem a všechny související zásady nastavení nástroje Řízení uživatelských účtů jsou zakázané. Poznámka: Pokud nastavení této zásady je zakázané, Security Center vás upozorní, snížil celkové zabezpečení operačního systému. 
  - *Ano* -je povolený režim schválení správcem. Tato zásada musí být povolená a související zásady nastavení nástroje Řízení uživatelských účtů musí být správně nastavena umožňující předdefinovaného účtu Administrator a všichni uživatelé, kteří jsou členy skupiny Administrators spouštět v režimu schválení správcem.  

  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067184)  
  
  **Výchozí**: Ano
  
- **Zakázat anonymní výčty účtů SAM**  
  Toto nastavení zabezpečení určuje, jaké další oprávnění jsou udělena pro anonymní připojení k počítači. Windows umožňuje anonymním uživatelům provádět určité aktivity, jako je například výčet názvů účtů domén a sdílených síťových složek. To je praktické, například, pokud chce správce udělit přístup uživatelům v důvěryhodné doméně, která nebude spravovat vzájemnou důvěryhodnost. Tato možnost zabezpečení umožňuje další omezení umístit na anonymní připojení následujícím způsobem: 
  - *Ano* – Nepovolit výčet SAM účty. Tato možnost nahradí všechny Authenticated Users oprávnění zabezpečení pro prostředky.
  - *Není nakonfigurováno* – žádná další omezení. Spolehněte se na výchozí oprávnění.  
  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067318)  

  **Výchozí**: Ano
  
- **Povolit vzdálené volání správce zabezpečení účtů**  
  Nastavení této zásady umožňuje omezit připojení vzdáleného rpc k SAM. Pokud není vybrána, použije se výchozí popisovač zabezpečení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067209)  
  
  **Výchozí**: *O:BAG:BAD:(A;;RC;;;BA)*

- **Použít režim schválení správcem**  
  Toto nastavení zásady řídí chování režim schválení správcem pro předdefinovaný účet Administrator. Možnosti: 
  - *Ano* -předdefinovaný účet správce používá režim schválení správcem. Ve výchozím nastavení všechny operace, která vyžaduje zvýšení úrovně oprávnění se zobrazí výzva ke schválení operaci. 
  - *Není nakonfigurováno* -předdefinovaného účtu správce spustí všechny aplikace s plný administrativní oprávnění. 

  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067186)  

  **Výchozí**: Ano
  
- **Povolit přístup k aplikacím uživatelského rozhraní pro zabezpečené umístění**  
  Tato zásada, nastavení ovládacích prvků, jestli programy User Interface Accessibility (UIAccess nebo také UIA) můžete automaticky vypnout zabezpečenou plochu používá standardní uživatelské výzvy ke zvýšení oprávnění. 
  - *Ano* – aplikace UIA, včetně vzdálené pomoci pro Windows, automaticky vypnout zabezpečenou plochu výzvy ke zvýšení oprávnění. Pokud nechcete zakázat "Řízení uživatelských účtů: Při zobrazení výzvy ke zvýšení oprávnění přepnout na zabezpečenou plochu"nastavení zásad, výzvy se zobrazí na ploše interaktivního uživatele místo zabezpečené ploše. 
  - *Není nakonfigurováno*:-zabezpečenou plochu může zakázat jen uživatel interaktivní plochy nebo vypnutí "Řízení uživatelských účtů: Při zobrazení výzvy ke zvýšení oprávnění přepnout na zabezpečenou plochu"nastavení zásad.  

  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067185)  

  **Výchozí**: Ano

- **Zjistit instalace aplikací a zobrazit výzvu ke zvýšení oprávnění**  
  Toto nastavení zásady řídí chování zjišťování instalace aplikací pro počítače. Možnosti: 
  - *Povolené* – při instalaci balíčku aplikace se zjistí, která vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván k zadání uživatelské jméno správce a heslo. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s příslušnými oprávněními. 
  - *Zakázané* -instalační balíčky aplikací nejsou zjištěny a zobrazení výzvy ke zvýšení oprávnění. Podnikům, které jsou spuštěny ploch standardních uživatelů a používat delegovaná instalace technologie, jako je instalace softwaru zásad skupiny nebo Systems Management Server (SMS) byste zakázat toto nastavení zásad. V takovém případě detekci Instalační služby systému je zbytečné.  
  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067208)  

  **Výchozí**: Ano
  
- **Zabránit ukládání hodnoty hash LAN Manageru při příští změně hesla**  
  Toto nastavení zabezpečení určuje, zda při příští změně hesla, hodnoty hash LAN Manager (LM) pro nové heslo je uložena. Hodnota hash LM je poměrně malý a náchylné k útokům, mezi hodnota hash kryptograficky silnější Windows NT. Protože hodnota hash LM jsou uloženy v místním počítači v databázi zabezpečení může být ohrožena hesla při napadení zabezpečení databáze.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067213)  
  
  **Výchozí**: Ano

- **Virtualizovat souborů a registrů zápisu chyby do podle umístění uživatele**  
  Toto nastavení řídí, jestli se chyby zápisu aplikace přesměrují na definovaná umístění registru a souborů systému zásad. Nastavení této zásady snižuje riziko zneužití aplikací, které spustit jako správce a zápis dat za běhu aplikace k *% ProgramFiles %* , *% Windir %* , *%Windir%\system32*, nebo *Klíče HKLM\Software*.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067321)  
  
  **Výchozí**: Ano

## <a name="ms-security-guide"></a>Příručka zabezpečení MS  
Další informace najdete v tématu [zásady CSP – MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) v dokumentaci k Windows.  

- **Místní účty na přihlášení k síti použít omezení nástroje Řízení uživatelských účtů**  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067188)  

  **Výchozí**: Enabled
  
- **Konfigurace spuštění ovladače klienta v1 SMB**  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067214) 
 
  **Výchozí**: Zakázané ovladače
  
- **Server s protokolem SMB verze 1**  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067190)  

  **Výchozí**: Zakázáno
  
- **Ověřování algoritmem Digest**  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067193) 
 
  **Výchozí**: Zakázáno
  
- **Strukturované zpracování výjimek přepsat ochrany**  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067217)  

  **Výchozí**: Enabled
  
## <a name="mss-legacy"></a>Starší verze MSS  
Další informace najdete v tématu [zásady CSP – MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) v dokumentaci k Windows.  

- **Zdroj protokolu IP sítě směrování úroveň ochrany**  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067220)  
  
  **Výchozí**: Nejvyšší ochrany  
  
- **Ignorovat síťové požadavky na verzi název rozhraní NetBIOS s výjimkou ze serverů WINS**  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067218)  
 
  **Výchozí**: Enabled
  
- **IPv6 zdroj směrování úroveň ochrany sítě**  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067216)  

  **Výchozí**: Nejvyšší ochrany

- **Přesměrování protokolu ICMP sítě přepsat generované protokolu OSPF**  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067326)  

  **Výchozí**: Zakázáno
  
## <a name="power"></a>Napájení  
Další informace najdete v tématu [zásady CSP - Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) v dokumentaci k Windows.  

- **Vyžadovat heslo při probuzení, zatímco napájen ze sítě**  
  Nastavení této zásady určuje, pokud bude uživatel vyzván k zadání hesla, když se systém obnoví z režimu spánku. Pokud povolíte nebo není pro toto nastavení zásad, bude uživatel vyzván k zadání hesla, když se systém obnoví z režimu spánku. Pokud nastavení této zásady zakážete, není uživatel vyzván k zadání hesla, když se systém obnoví z režimu spánku.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067221)  
  
  **Výchozí**: Enabled
  
- **Úsporné při režimu spánku, když jste na baterie**  
  Toto nastavení zásad spravuje, pokud Windows může používat úsporné režimy při uvedení počítače do režimu spánku. Pokud povolíte nebo není pro toto nastavení zásad, pomocí Windows úsporné počítač přepnout do režimu spánku. Pokud nastavení této zásady zakážete, úsporné (S1 S3) nejsou povoleny.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067195)  
  
  **Výchozí**: Zakázáno
  
- **Úsporné při režimu spánku, zatímco napájen ze sítě**  
  Toto nastavení zásad spravuje, pokud Windows může používat úsporné režimy při uvedení počítače do režimu spánku. Pokud povolíte nebo není pro toto nastavení zásad, pomocí Windows úsporné počítač přepnout do režimu spánku. Pokud nastavení této zásady zakážete, úsporné (S1 S3) nejsou povoleny.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067196)  
  
  **Výchozí**: Zakázáno
  
- **Vyžadovat heslo při probuzení na baterie**  
  Nastavení této zásady určuje, pokud bude uživatel vyzván k zadání hesla, když se systém obnoví z režimu spánku. Pokud povolíte nebo není pro toto nastavení zásad, bude uživatel vyzván k zadání hesla, když se systém obnoví z režimu spánku. Pokud nastavení této zásady zakážete, není uživatel vyzván k zadání hesla, když se systém obnoví z režimu spánku.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067322)  
  
  **Výchozí**: Enabled

## <a name="remote-assistance"></a>Vzdálená pomoc
- **Vzdálená pomoc, vyžádaná**  
  Nastavení této zásady umožňuje zapnout nebo vypnout Solicited (požádat o), vzdálené pomoci na tomto počítači. 
  - *Pokud povolíte toto nastavení zásad*, uživatelé na tomto počítači můžete použít e-mail nebo soubor přenos někoho požádáte o pomoc. Navíc uživatelé můžou povolit připojení k tomuto počítači pomocí programů pro rychlé zasílání zpráv a můžete nakonfigurovat další nastavení vzdálené pomoci. 
  - *Pokud nastavení této zásady zakážete*, uživatelé na tomto počítači nelze použít e-mail nebo soubor přenos někoho požádáte o pomoc. Navíc uživatelé nemůžou používat rychlé zasílání zpráv programy umožňující připojení k tomuto počítači. 
  - *Pokud nastavení této zásady nenakonfigurujete*, uživatelů můžete zapnout nebo vypnout Solicited (požádat o), vzdálené pomoci sami v systémových vlastnostech v Ovládacích panelech. Uživatelé mohou také nakonfigurovat nastavení vzdálené pomoci. 

  Pokud nastavení této zásady povolíte, máte dva způsoby, jak povolit poskytovat vzdálenou pomoc: "Povolit k zobrazení pouze počítače" nebo "Povolit vzdálené řízení počítače." "Maximální lístek čas" nastavení zásad nastavuje limit množství času, který žádost o vzdálenou pomoc vytvořené pomocí e-mailu nebo přenosu souborů. může zůstat otevřené. "Vyberte metodu pro odesílání e-mailové pozvánky" nastavení určuje, které standard e-mailu. Pokud chcete používat k odesílání pozvánky Vzdálená pomoc. V závislosti na vaší e-mailový program můžete použít standardní Mailto (pozvánku příjemce připojuje prostřednictvím internetového odkazu) nebo rozhraní SMAPI společnosti (jednoduché rozhraní MAPI) standardní (e-mailové pozvánce je připojené k vaší e-mailové zprávy). Nastavení této zásady není k dispozici ve Windows Vista, protože rozhraní SMAPI je jedinou metodou podporováno. Pokud povolíte toto nastavení zásad byste měli taky povolit příslušné brány firewall výjimky umožňující komunikaci o vzdálenou pomoc.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067198)

  **Výchozí**: Zakázání vzdálené pomoci

  Pokud je nastavena na *povolení funkce Vzdálená pomoc*, nakonfigurujte následující další nastavení:  
  - **Vzdálená pomoc, vyžádaná oprávnění**  
    **Výchozí**: Zobrazení  

  - **Hodnota času maximální lístek**  
    **Výchozí**: *Není nakonfigurováno*  

  - **Maximální lístek časové období**  
    **Výchozí**: Minut    

  - **E-mailovou pozvánku – metoda**  
    **Výchozí**: Jednoduché rozhraní MAPI

  
## <a name="remote-desktop-services"></a>Vzdálená plocha  
Další informace najdete v tématu [zásady CSP – RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) v dokumentaci k Windows.  

- **Blokování ukládání hesel**  
  Určuje, zda hesla lze uložit na tento počítač z připojení ke vzdálené ploše. Pokud povolíte toto nastavení hesla ukládání zaškrtávacího políčka v připojení ke vzdálené ploše je zakázané a uživatelé nebudou moci ukládat hesla. Když uživatel otevře soubor RDP pomocí připojení ke vzdálené ploše a uloží jejich nastavení, se odstraní všechna hesla, která dříve byla uložena v souboru RDP. Pokud toto nastavení zakážete nebo ponechte není nakonfigurované, může uživatel uložit hesla, pomocí připojení ke vzdálené ploše.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067301)  
  
   **Výchozí**: Enabled
  
- **Zabezpečená komunikace RPC**  
  Určuje, jestli server hostitele relace vzdálené plochy vyžaduje zabezpečené komunikace RPC se všemi klienty nebo umožňuje nezabezpečenou komunikaci. Toto nastavení můžete použít k posílení zabezpečení protokolu RPC komunikaci s klienty tím, že jenom ověřený a šifrovaný požadavky. Pokud je stav nastaven na povoleno, služby Vzdálená plocha přijímá požadavky od klientů vzdáleného volání Procedur, které podporuje požadavky na zabezpečení a neumožňuje nezabezpečenou komunikaci s nedůvěryhodné klienty. Pokud je stav nastaven na hodnotu zakázáno, služby Vzdálená plocha vždy požadavky zabezpečení pro všechny přenosy RPC. Zabezpečená komunikace je však povoleno pro klienty vzdáleného volání Procedur, které nemáte odpověď na žádost o. Pokud je stav nastaven není nakonfigurováno, zabezpečená komunikace bude povolena. Poznámka: Rozhraní RPC se používá ke správě a konfiguraci služby Vzdálená plocha.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067248)  
  
  **Výchozí**: Enabled
  
- **Jednotku přesměrování bloku**  
  Nastavení této zásady určuje, zda bude bráněno mapování jednotky klienta v relaci vzdálené plochy (přesměrování jednotek). Ve výchozím nastavení serveru hostitele relace VP mapuje klientské jednotky automaticky po připojení. Připojené jednotky se objeví ve stromové struktuře relace složek v Průzkumníku souborů nebo počítače ve formátu  *\<písmeno_jednotky >* na  *\<název_počítače >* . Nastavení této zásady můžete použít k přepsání tohoto chování. Pokud nastavení této zásady povolíte, přesměrování klienta jednotky není povoleno v relace služby Vzdálená plocha a přesměrování kopie souboru schránky není povolené v počítačích se systémem Windows Server 2003, Windows 8 a Windows XP. Pokud nastavení této zásady zakážete, přesměrování jednotek je vždycky povolená. Navíc je vždycky povolená přesměrování kopie souborů schránky. Pokud je povoleno přesměrování schránky. Pokud nastavení této zásady nenakonfigurujete, nejsou zadány jednotky přesměrování klientů a přesměrování kopie souboru schránky na úrovni zásad skupiny.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067197)  
  
  **Výchozí**: Enabled
  
- **Výzva k zadání hesla při připojení**  
  Nastavení této zásady určuje, zda služby Vzdálená plocha vždy vyzve k zadání hesla při připojení klienta. Toto nastavení slouží k vynucení výzva k zadání hesla pro uživatele přihlášení do služby Vzdálená plocha, i v případě, že se už zadali heslo v klientovi připojení ke vzdálené ploše. Ve výchozím nastavení služby Vzdálená plocha umožňuje uživatelům přihlásit se automaticky tak, že zadáte heslo klienta připojení ke vzdálené ploše. Pokud nastavení této zásady povolíte, uživatelé nemohou přihlásit automaticky k vzdálené ploše zadáním hesla do klienta připojení ke vzdálené ploše. se výzva k zadání hesla k přihlášení. Pokud nastavení této zásady zakážete, můžete vždy přihlášení k vzdálené ploše automaticky zadáním hesla do klienta připojení ke vzdálené ploše. Pokud nastavení této zásady nenakonfigurujete, není zadán automatické přihlášení na úrovni zásad skupiny.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067328)  
  
  **Výchozí**: Enabled
  
- **Úroveň šifrování připojení klienta služby Vzdálená plocha**  
  Určuje, jestli se vyžaduje použití úrovně konkrétní šifrování pro zabezpečení komunikace mezi klientskými počítači a servery hostitele relace VP během připojení protokolu RDP (Remote Desktop). Tyto zásady platí jenom při použití nativní šifrování protokolu RDP. Však není doporučeno nativní šifrování protokolu RDP (na rozdíl od šifrování SSL). Tyto zásady neplatí pro šifrování SSL. Pokud nastavení této zásady povolíte, musí veškerá komunikace mezi klienty a servery hostitele relace VP během vzdálené připojení použijte metodu šifrování zadané v tomto nastavení. Ve výchozím nastavení úrovně šifrování nastavena na hodnotu Vysoká. Jsou dostupné tyto metody šifrování:  
  - *Vysoká* – The vysokou nastavení zašifruje data odesílaná z klienta na serveru a ze serveru klientovi pomocí silného 128bitové šifrování. Použijte tuto úroveň šifrování v prostředích, která obsahují pouze klienty se 128-bit (třeba klienti, na kterých běží připojení ke vzdálené ploše). Klienti, kteří nepodporují tato úroveň šifrování se nemůže připojit k serverům hostitele relace VP.  
  - *Kompatibilní s klientem* -kompatibilní klientské nastavení šifruje data odesílaná mezi klientem a serverem nejsilnějšího klíče podporované klientem. Použijte tuto úroveň šifrování v prostředí, které obsahují klienty, kteří nepodporují 128bitové šifrování.  
  - *Nízká* – The nízká nastavení šifruje jenom data odeslaných z klienta na server s využitím 56bitové šifrování.  
  
  Pokud zakážete nebo toto nastavení nemusíte konfigurovat, úrovně šifrování se použije pro připojení k serverům hostitele relace VP se vynucuje prostřednictvím zásad skupiny. Důležité kompatibilita se standardem FIPS, je možné nakonfigurovat pomocí kryptografický modul systému. Používat algoritmy odpovídající standardu FIPS pro šifrování, hašování a podpisování nastavení v zásadách skupiny (v počítači Konfigurace počítače\Nastavení systému Windows\Místní Policies\Security Options.) Kompatibilní se standardem FIPS nastavení šifruje a dešifruje data odesílaná z klienta na serveru a ze serveru klientovi s federální informace o zpracování Standard (FIPS) 140 šifrovací algoritmy, a používá kryptografické moduly Microsoftu. Používejte tuto úroveň šifrování komunikace mezi klienty a servery hostitele relace VP vyžaduje nejvyšší úroveň šifrování.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067222)  
  
  **Výchozí**: Vysoká
  
## <a name="remote-management"></a>Vzdálená správa  
Další informace najdete v tématu [zásady CSP – RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) v dokumentaci k Windows.  

- **Blokování ukládání spustit jako přihlašovací údaje**  
  Základní ověřování klienta.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067300)  
  
  **Výchozí**: Enabled
  
- **Základní ověřování**  
  Nastavení této zásady umožňuje určit, zda služba Vzdálená správa Windows (WinRM) přijme základní ověřování ze vzdáleného klienta. Pokud nastavení této zásady povolíte, Služba WinRM přijme základní ověřování ze vzdáleného klienta. Pokud zakážete nebo není pro toto nastavení zásad služby WinRM nepřijme základní ověřování ze vzdáleného klienta.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067223)  
  
  **Výchozí**: Zakázáno
  
- **Ověřování hodnotou hash bloku klienta**  
  Nastavení této zásady umožňuje určit, zda klient vzdálené správy Windows (WinRM) používá ověřování hodnotou hash. Pokud nastavení této zásady povolíte, Klient WinRM nepoužívá ověřování hodnotou hash. Pokud zakážete nebo není pro toto nastavení zásad, používá Klient WinRM ověřování hodnotou hash.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067302)  
  
  **Výchozí**: Enabled
  
- **Nešifrované přenosy**  
  Nastavení této zásady umožňuje určit, zda služba Vzdálená správa Windows (WinRM) odesílá a přijímá nezašifrované zprávy přes síť. Pokud nastavení této zásady povolíte, Klient WinRM odesílá a přijímá nezašifrované zprávy přes síť. Pokud zakážete nebo není pro toto nastavení zásad, Klient WinRM odesílá nebo přijímá jenom šifrované zprávy přes síť.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067226)  
  
  **Výchozí**: Zakázáno
  
- **Komunikace s klienty bez šifrování**  
  Nastavení této zásady umožňuje určit, zda klient vzdálené správy Windows (WinRM) odesílá a přijímá nezašifrované zprávy přes síť. Pokud nastavení této zásady povolíte, Klient WinRM odesílá a přijímá nezašifrované zprávy přes síť. Pokud zakážete nebo není pro toto nastavení zásad, Klient WinRM odesílá nebo přijímá jenom šifrované zprávy přes síť.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067304)  
  
  **Výchozí**: Zakázáno
  
- **Základní ověřování klienta**  
  Nastavení této zásady umožňuje určit, zda klient vzdálené správy Windows (WinRM) používá základní ověřování. Pokud nastavení této zásady povolíte, Klient WinRM používá základní ověřování. Pokud je Služba WinRM konfigurován pro použití přenos pomocí protokolu HTTP, uživatelského jména a hesla odešlou přes síť jako prostý text. Pokud zakážete nebo není pro toto nastavení zásad, Klient WinRM nepoužívá základní ověřování.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067252)  
  
  **Výchozí**: Zakázáno
  
## <a name="remote-procedure-call"></a>Vzdálené volání procedur  
Další informace najdete v tématu [zásady CSP – RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) v dokumentaci k Windows.  

- **Možnosti klienta vzdáleného volání Procedur nebyl ověřen**  
  Toto nastavení zásady řídí způsob, jakým modul runtime serveru RPC zpracovává neověřené klienty vzdáleného volání Procedur připojení k serverům RPC. Toto nastavení zásad má vliv na všechny aplikace RPC. V prostředí domény pomocí tohoto nastavení zásad opatrně, protože můžou ovlivnit širokou škálu funkcí, včetně samotného zpracování zásad skupiny. Návrat ke změně nastavení této zásady může vyžadovat ruční zásahy, na každý napadeného počítače. Nastavení této zásady nikdy použito k řadiči domény. Pokud nastavení této zásady zakážete, modul runtime serveru RPC používá hodnotu "Authenticated" na klientovi Windows a hodnota "None" ve verzích Windows serveru, které podporují tuto zásadu. Pokud nastavení této zásady nenakonfigurujete, zůstane zakázaná. Modul runtime serveru RPC se chová jako by byl povolen s hodnotou "Authenticated" používá se pro klienta Windows a hodnota "None" použít Server skladová jednotka, která podporuje nastavení této zásady. Pokud nastavení této zásady povolíte, bude směrovat modul runtime serveru RPC pro omezení neověřené RPC klienti připojení k vzdálené volání Procedur servery spuštěné na počítači. Klient se považuje za ověřený klient, pokud pojmenovaný kanál používá ke komunikaci se serverem nebo pokud používá zabezpečení protokolu RPC. Rozhraní RPC, který požádaly konkrétně přístupný neověřené klienty může být z tohoto omezení, v závislosti na vybrané hodnoty pro nastavení této zásady vyloučit.  
  - *Žádný* umožní všem klientům RPC pro připojení k serverům RPC spuštěné na počítači, na které nastavení zásad se použije. 
  - *Ověření* umožňuje pouze ověřeným RPC klientů (na výše uvedená definice) pro připojení k serverům RPC spuštěné na počítači, na které nastavení zásad se použije. Výjimky jsou udělena rozhraní, které si vyžádali. 
  - *Ověření bez výjimky* umožňuje pouze ověřeným RPC klientů (na výše uvedená definice) pro připojení k serverům RPC spuštěné na počítači, na které nastavení zásad se použije. Jsou povoleny žádné výjimky. Poznámka: Toto nastavení zásad se projeví až po restartování systému.  

  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067225)  

  **Výchozí**: Ověření

## <a name="search"></a>Search 
Další informace najdete v tématu [zásady CSP – hledání](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) v dokumentaci k Windows.  

- **Zakázání indexování šifrované položky**  
  Tato zásada povolí nebo zakáže indexování položek. Tento přepínač je pro Windows Search indexerem a určuje, zda se budou indexovat šifrované, jako jsou soubory Windows Information Protection (WIP) chráněné položky. Pokud je tato zásada povolená, chráněné položky WIP se indexují a metadata o nich se ukládají do nešifrovaného umístění. Součástí metadat jsou takové položky jako cesta k souboru a datum změny. Pokud je tato zásada zakázaná, chráněné položky WIP se indexují a nejsou zobrazena ve výsledcích v Cortaně nebo v Průzkumníkovi souborů. Pokud se v zařízení nachází mnoho souborů médií chráněných WIP, může to mít také dopad na výkon fotografií a aplikací Groove.  
  [Víc se uč]( https://go.microsoft.com/fwlink/?linkid=2067303)  
  
  **Výchozí**: Ano
  
## <a name="smart-screen"></a>SmartScreen  
Další informace najdete v tématu [zásady CSP – SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) v dokumentaci k Windows.  

- **Zablokovat spuštění neověřených souborů**  
  Brání uživateli ve spuštění neověřených souborů. 
  - *Není nakonfigurováno* -zaměstnanci můžou ignorovat upozornění filtru SmartScreen a spouštět škodlivé soubory. 
  - *Ano* – zaměstnanci nelze ignorovat upozornění filtru SmartScreen a spouštět škodlivé soubory.

  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067228)  
  
  **Výchozí**: Ano

- **Vyžadovat SmartScreen pro aplikace a soubory**  
  Umožňuje správcům IT Konfigurovat filtr SmartScreen pro Windows.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067168)  

  **Výchozí**: Ano
  
## <a name="system"></a>Systém  
Další informace najdete v tématu [zásady CSP – systém](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) v dokumentaci k Windows.  

- **Inicializace ovladače start spuštění systému**  
  Nastavení této zásady umožňuje zadat spouštění ovladače, které jsou inicializovány podle klasifikace určené ovladači Antimalware prvotního spuštění Elam spouštění. Antimalware prvotního spuštění Elam spouštění ovladač může vrátit následující klasifikace pro každý ovladač spouštění: 
  - *Dobré* -ovladač byl podepsán a nebylo manipulováno.  
  - *Chybný* -ovladač má byly identifikovány jako malware. Doporučujeme vám, že Nepovolit známé chybné ovladače mají být inicializovány. 
  - *Chybný, ale vyžaduje pro spuštění* – ovladače má byly identifikovány jako malware, ale počítač nelze bez načtení tento ovladač úspěšně spustil. 
  - *Neznámý* -tento ovladač nebyla ověřena k aplikací detekce malwaru a ještě nebyl klasifikován ovladačem Antimalware prvotního spuštění Elam spouštění.  

  Pokud nastavení této zásady povolíte, můžete které spouštění ovladače k inicializaci při příštím spuštění počítače. Pokud zakážete nebo nekonfigurujte tuto zásadu nastavení, ovladače pro zahájení spouštění, jestli se má být funkční, neznámý nebo chybný ale spouštěcí kritické jsou inicializovány a inicializace ovladače určena jako chybný se přeskočila. Pokud vaše aplikace detekce malwaru neobsahuje ovladači Antimalware prvotního spuštění Elam spouštění nebo ovladač spouštění Antimalware prvotního spuštění Elam bylo zakázáno, toto nastavení nemá žádný vliv a inicializací všech spouštění ovladačů.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067307)   
  
  **Výchozí**: Dobré neznámé a špatný kritické


## <a name="wi-fi"></a>Wi-Fi  
Další informace najdete v tématu [zásady CSP – Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) v dokumentaci k Windows.  

- **Blokovat sdílení Internetu**  
  Určuje, zda je na zařízení možné sdílení Internetu.   
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067327)   

  **Výchozí**: Ano  

- **Automaticky blokovat připojení k Wi-Fi hotspotům**  
  Povolí nebo zakáže zařízení automaticky se připojovat k Wi-Fi hotspotům.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067320)   

  **Výchozí**: Ano  
  
## <a name="windows-connection-manager"></a>Správce připojení k Windows  
Další informace najdete v tématu [zásady CSP – WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) v dokumentaci k Windows.  

- **Blokovat připojení k doméně sítím**  
  Nastavení této zásady zabrání počítačům bránily v připojení k doménové síti i doméně na základě sítě ve stejnou dobu. Pokud nastavení této zásady je povoleno, počítač reaguje na pokusy o automatické a ruční síťové připojení podle následujících okolností: 
  - Pokusy o automatické připojení při počítači je již připojen k síti založené na doméně, všechny pokusy o automatické připojení k sítím nedoménové jsou zablokované. Když počítač je už připojený k síti založené na doméně, pokusy o automatické připojení k sítím založený na doméně jsou zablokované. 
  - Ruční připojení pokusy, kdy počítač je již připojen k buď doméně na základě sítě nebo sítě založené na doméně přes médium jiné než Ethernetu a uživatel se pokusí vytvořit připojení k další síti ručně v porušení těchto podmínek nastavení, odpojí existující připojení k síti a ruční připojení je povoleno. Když počítač je již připojen k buď mimo doménu na základě sítě nebo sítě založené na doméně přes síť Ethernet a uživatel se pokusí vytvořit připojení k další síti ručně v rozporu s nastavením této zásady je existující připojení k síti Ethernet udržuje a pokus o ruční připojení je blokován.  

  Pokud nastavení této zásady není nakonfigurována nebo je zakázána, jsou povoleny počítačů současně připojit k doméně a doméně sítě.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067323)  

  **Výchozí**: Enabled
  
## <a name="windows-defender"></a>Windows Defender  
Další informace najdete v tématu [zásady CSP – Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) v dokumentaci k Windows.  

- **Kontrolovat příchozí e-mailové zprávy**  
  Povolí nebo zakáže kontrolu e-mailu.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067116)  
  
  **Výchozí**: Ano  

- **Aplikace Office spusťte podřízený proces typ**  
  Aplikace Office nebudou moct vytvářet podřízené procesy. To zahrnuje Word, Excel, PowerPoint, OneNote a přístup. Toto je chování typické malware, hlavně pro útoky – makro, které se snaží používat aplikace Office spouštět ani se stahování škodlivého spustitelné soubory.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067121)  
  
  **Výchozí**: Zablokovat
  
- **Typ souhlasu odeslání vzorku defenderu**  
  Kontroly pro uživatele souhlas úrovni v programu Windows Defender odesílat data. Pokud již bylo uděleno vyžaduje souhlas, program Windows Defender odešle je. V opačném případě (a pokud uživatel zadal nikdy se zeptat), požádejte ho o souhlas uživatele (Pokud je povoleno Defender/AllowCloudProtection) před odesláním údajů se spustí uživatelské rozhraní.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067131)  
  
  **Výchozí**: Posílat bezpečné vzorky automaticky 
  
- **Interval aktualizace podpisu (v hodinách)**  
  Interval aktualizace podpisu Defender v hodinách
  
  **Výchozí**: 4
  
- **Skript se stáhne typ spuštění datové části**  
  Defender skript stáhne typ spuštění datové části
  
  **Výchozí**: Zablokovat
  
- **Zabránit typ zcizování přihlašovacích údajů**  
  Windows Defender Credential Guard používá zabezpečení založené na virtualizaci k izolování tajných kódů tak, aby k nim měli přístup pouze oprávněný systémový software. Neoprávněný přístup k těmto tajným kódům může vést k útokům využívajícím krádež přihlašovacích údajů, jako je například Pass-the-Hash nebo Pass-The-Ticket. Windows Defender Credential Guard zabraňuje těmto útokům Díky ochraně hodnot hash hesel protokolů NTLM, lístků TGT protokolu Kerberos a přihlašovací údaje uložené aplikace jako přihlašovací údaje domény.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067065)  
  
  **Výchozí**: Povolení

- **Typ obsahu provádění e-mailu**  
  Toto pravidlo blokuje tomu nebudou tyto typy souborů, spuštění nebo spuštění z e-mailu v aplikaci Microsoft Outlook nebo webové pošty (například Gmail.com nebo Outlook.com): Spustitelný soubor, soubory (například .exe, .dll nebo .scr) skriptu (například PS prostředí PowerShell, VisualBasic .vbs nebo soubor .js JavaScript) archivní soubory skriptu.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067063)  
  
  **Výchozí**: Zablokovat

- **Adobe Reader spustíte podřízený proces**  

  **Výchozí**: Povolení

- **Typ ochrany sítě**  
  Tato zásada umožňuje zapnout ochranu sítě (bloku nebo auditu) nebo vypnout v systému Windows Defender Exploit Guard. Ochrana sítě je funkce Windows Defender ochrany Exploit Guard, která chrání zaměstnanci libovolnou aplikaci z podvodných přistupující, servery hostující zneužití a škodlivý obsah na Internetu. To zahrnuje, znemožní připojení k nebezpečné lokalit prohlížeče třetích stran. Typ hodnoty je celé číslo. Pokud povolíte toto nastavení, je zapnutá ochrana sítě a zaměstnanci nedá se zase vypnout. Její chování je řídit následující možnosti: Blok a auditu. Pokud povolíte tuto zásadu s možností "Blokovat", zablokuje se bránily v připojení k doménám nebezpečné uživatelů a aplikací. Zobrazí se tato aktivita ve službě Windows Defender Security Center. Pokud povolíte tuto zásadu s parametrem "Auditu", nebude blokován uživatele/aplikace v připojení k doménám nebezpečné. Nicméně stále uvidíte této aktivity ve službě Windows Defender Security Center. Pokud tuto zásadu zakážete, nebude blokován uživatele/aplikace v připojení k doménám nebezpečné. Uvidíte není žádné síťové aktivity ve službě Windows Defender Security Center. Pokud tuto zásadu nenakonfigurujete, blokování sítě je ve výchozím nastavení zakázána.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067102)  
  
  **Výchozí**: Povolení
  
- **Defender naplánovat den kontroly**  
  Naplánovat den kontroly Defender.
  
  **Výchozí**: každý den
  
- **Cloudová ochrana**  
  Nejlepší chránit váš počítač, program Windows Defender vám zašleme informace společnosti Microsoft o všech problémech, které nalezne. Microsoft tyto informace analyzuje, další informace o problémy s vámi a další zákazníky a nabízet lepší řešení.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067039)
  
  **Výchozí**:  Ano  

- **Defender potenciálně nežádoucí aplikace akce**  
  Funkce ochrany potenciálně nežádoucí aplikace (PUA) v antivirové ochrany v programu Windows Defender může identifikovat a ochraně zablokovat stahování a instalaci na koncových bodech vaší sítě. Tyto aplikace nejsou považovány za viry, malwaru nebo jiných typů hrozeb, ale může provádět akce na koncové body, které nepříznivě ovlivnit výkon nebo použít. PUA najdete také na aplikace, které jsou považovány za špatné pověst. Chování typické PUA zahrnuje: Různé typy sdružování injektáž Ad do webových prohlížečů ovladač a registru nástroje software, který detekovat problémy, žádost o platbu opravit chyby, ale zůstávají v koncovém bodě a provést žádné změny nebo optimalizace (označované také jako "podvodný antivirový" programy). Tyto aplikace může zvýšit riziko sítí infekce malwarem a způsobit, že napadení malwarem bude obtížnější k identifikaci a plýtvat IT prostředky v vymazání aplikace.  
  [Víc se uč](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection)    
  
  **Výchozí**: Zablokovat  

- **Skript obfuskovaný kód typu – makro**  
  Před škodlivým softwarem a dalšími hrozbami můžete zkusit obfuskaci nebo skrytí jejich škodlivý kód v některé soubory skriptu. Toto pravidlo brání skripty, které se zdají být matoucí spouštění.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067026)  
  
  **Výchozí**: Zablokovat
  
- **Během úplné kontroly kontrolovat vyměnitelné jednotky**  
  Umožňuje programu Windows Defender můžete spustit kontrolu škodlivého a nežádoucí software na vyměnitelných jednotkách (například flash disky) při spuštění úplné kontroly. Antivirová ochrana v programu Windows Defender kontrolovat všechny soubory v zařízení USB před spuštěním.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067036)  
  
  **Výchozí**: Ano  
  
- **Prohledat archivní soubory**  
  Defenderu kontrolovat archivní soubory.
  
  **Výchozí**: Ano
  
- **Monitorování chování**  
  Povolí nebo zakáže funkci monitorování chování Windows Defender. Vložený ve Windows 10, tyto senzory shromažďovat a zpracovávat chování signály od operačního systému a odešle tato data ze senzorů do privátního izolovaného, cloudu instance ochrany ATP v programu Defender Microsoft.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067111)  
  
  **Výchozí**: Ano

- **Kontrolovat soubory otevřené ze síťových složek**  
  Pokud jsou soubory jen pro čtení, uživatel nebude moct odebrat žádný zjištěný malware.
  
  **Výchozí**: Ano

- **Typ procesu nedůvěryhodné USB**  
  S tímto pravidlem můžou správci bránit spouštění z vyměnitelné jednotky USB, včetně karet SD bez znaménka nebo nedůvěryhodné spustitelné soubory.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067100)  
  
  **Výchozí**: Zablokovat
  
- **Aplikace Office jiných zpracovat typ vkládání**  
  Aplikace Office, Word, Excel, PowerPoint a OneNote, včetně nebude možné vloží kód do jiných procesů. To se obvykle používá malware spustit škodlivý kód ve snaze skrýt aktivita z antivirového prověřovacích modulů.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067019)  
  
  **Výchozí**:  Zablokovat
  
- **Povolit typ importy Win32 kódu maker v Office**  
  Malware můžete použít kódu maker v souborech Office pro import a načíst dll Win32, které lze použít k volání rozhraní API umožňující další infekce v celém systému. Toto pravidlo se pokusí zablokovat soubory Office, které obsahují kód makra, které podporují import knihoven DLL Win32. To zahrnuje Word, Excel, PowerPoint a OneNote.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067130)  
  
  **Výchozí**: Zablokovat  
  
- **Defender cloudu blok úroveň**  
  Defender cloudu blok úroveň.
  
  **Výchozí**: Nenakonfigurováno

- **Monitorování v reálném čase**  
  Defender vyžaduje monitorování v reálném čase.
  
  **Výchozí**: Ano
 
- **Spuštění aplikace Office komunikace v podřízený proces**  

  **Výchozí**:  Povolení

- **Office aplikace spustitelný soubor vytvoření nebo spuštění typ obsahu**  
  Toto pravidlo zaměřuje na typické chování používané podezřelé a škodlivý doplňky a skripty (rozšíření), které vytvářet nebo spouštět spustitelné soubory. Jde o techniku typické malware. Rozšíření jsou blokovány z používán podle aplikace Office. Tato rozšíření obvykle používají Windows Scripting Host (soubory WSH) ke spouštění skriptů, které zautomatizovat určité úlohy nebo poskytují uživatel vytvořil doplňkové funkce.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067108)  
  
  **Výchozí**: Zablokovat

## <a name="windows-defender-firewall"></a>Firewall v programu Windows Defender  
Další informace najdete v tématu [2.2.2 FW_PROFILE_TYPOE]( https://docs.microsoft.com/openspecs/windows_protocols/ms-fasp/7704e238-174d-4a5e-b809-5f3787dd8acc) v dokumentaci k Windows protokoly.  

- **Brány firewall na profil domény**  
  Určuje profily, do kterých se pravidlo patří: Domain, Private, Public. Tato hodnota představuje profil sítě, které jsou připojené k doménám.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2066796)  

  - **Příchozí připojení blokováno**  
    **Výchozí**: Ano

  - **Odchozí připojení vyžaduje**  
    **Výchozí**: Ano 

  - **Příchozí upozornění blokované**  
    **Výchozí**: Ano

  - **Povolenou bránu firewall**  
    **Výchozí**: Povoleno

- **Veřejný profil firewallu v programu**  
  Určuje profily, do kterých se pravidlo patří: Domain, Private, Public. Tato hodnota představuje profil pro veřejné sítě. Tyto sítě jsou klasifikovány jako veřejné správci v hostitelském serveru. Klasifikace se stane při prvním hostitele připojí k síti. Tyto sítě jsou obvykle ty na letištích, kavárny a jiných veřejných místech, kde partneři v síti nebo správce sítě nejsou důvěryhodné.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067143)  

  - **Příchozí připojení blokováno**  
    **Výchozí**: Ano

  - **Odchozí připojení vyžaduje**  
    **Výchozí**: Ano 

  - **Příchozí upozornění blokované**  
    **Výchozí**: Ano

  - **Povolenou bránu firewall**  
    **Výchozí**: Povoleno

  - **Pravidla zabezpečení připojení ze zásad skupiny, které nebyly sloučeny**  
    **Výchozí**: Ano

  - **Pravidla zásad ze zásad skupiny, které nebyly sloučeny**  
    **Výchozí**: Ano

- **Privátní profil firewallu v programu**  
  Určuje profily, do kterých se pravidlo patří: Domain, Private, Public. Tato hodnota představuje profil pro privátní sítě.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067041)  

   - **Příchozí připojení blokováno**  
    **Výchozí**: Ano

  - **Odchozí připojení vyžaduje**  
    **Výchozí**: Ano 

  - **Příchozí upozornění blokované**  
    **Výchozí**: Ano

  - **Povolenou bránu firewall**  
    **Výchozí**: Povoleno

## <a name="windows-hello-for-business"></a>Windows Hello pro firmy  
- **Vyžadují rozšířenou ochranu proti falšování identity, pokud je k dispozici**  
  Pokud ano, zařízení bude používat rozšířenou ochranu proti falšování identity, pokud je k dispozici. Pokud ne, ochranu proti falšování identity se zablokuje. Není nakonfigurovaná, budou respektovat konfigurace nastavené v klientovi.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067192)

  **Výchozí**: Ano

- **Konfigurovat Windows Hello pro firmy**   
  Windows Hello pro firmy je alternativní metoda pro přihlašování do Windows tak, že nahradíte hesla, čipové karty a virtuální čipové karty. Je-li povolit nebo nenakonfigurujete toto nastavení zásad, zařízení zřídí Windows Hello pro firmy. Pokud nastavení této zásady zakážete, zařízení není Windows Hello pro firmy zřídit pro všechny uživatele.

  **Výchozí**: Ano

- **Vyžadovat v PIN kódu malá písmena**  
  Pokud je to nutné, PIN kód uživatele musí obsahovat aspoň jedno malé písmeno.

  **Výchozí**: Povoleno

- **Vyžadovat speciální znaky v PIN kódu**  
  Pokud je to nutné, PIN kód uživatele musí obsahovat aspoň jeden speciální znak.

  **Výchozí**: Povoleno

- **Minimální délka PIN kódu**  
  Minimální délka PIN kódu musí být v rozmezí od 4 do 127.

  **Výchozí**: 6

- **Vyžadovat v PIN kódu velká písmena**  
  Pokud je to nutné, PIN kód uživatele musí obsahovat aspoň jedno velké písmeno.

  **Výchozí**: Povoleno

## <a name="windows-ink-workspace"></a>Pracovní prostor Windows Ink  
Další informace najdete v tématu [zásady CSP – WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) v dokumentaci k Windows.  

- **Pracovní prostor Ink**  
  Určuje, jestli smí uživatel pro přístup k pracovnímu prostoru ink. 
  - *Zakázané* – přístup k pracovní prostor ink je zakázán. Tato funkce je vypnuta.
  - *Povolené* – pracovní prostor Ink funkce je zapnutá, ale uživatel nemůže přejít nad zamykací obrazovkou.
  - *Není nakonfigurováno* – pracovní prostor Ink funkce je zapnutá a uživatel ho může používat nad zamykací obrazovkou.  

  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067241)  

  **Výchozí**: Enabled
 
## <a name="windows-powershell"></a>Windows PowerShell  
Další informace najdete v tématu [zásady CSP – WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) v dokumentaci k Windows.  

- **Power shell skript prostředí blokovat protokolování**  
  Nastavení této zásady umožňuje protokolování veškerý vstup skriptu prostředí PowerShell do protokolu událostí Microsoft-Windows-PowerShell/Operational. Pokud nastavení této zásady povolíte, prostředí Windows PowerShell bude protokolovat zpracování příkazů, bloky skriptu, funkce a skripty – zda vyvolat interaktivně nebo prostřednictvím automatizace. Pokud nastavení této zásady zakážete, protokolování vstupu skriptu prostředí PowerShell je zakázáno. Pokud povolíte protokolování vyvolání blok skriptu, prostředí PowerShell také protokoluje události při vyvolání příkazu, blok skriptu, funkce nebo skriptu, spuštění nebo zastavení. Povolení protokolování vyvolání generuje k velkému počtu protokoly událostí. Poznámka: Toto nastavení zásad existuje v rámci konfigurace počítače a konfigurace uživatele v editoru zásad skupiny. Nastavení zásad Konfigurace počítače má přednost před nastavením zásad Konfigurace uživatele.  
  [Víc se uč](https://go.microsoft.com/fwlink/?linkid=2067330)  

  **Výchozí**: Enabled

## <a name="whats-changed-in-the-new-template"></a>Co se změnilo v nové šablony
*MDM standardních hodnot zabezpečení pro Spring 2019 aktualizace (19 hod. 1)* šablony obsahuje následující změny z *ve verzi preview* šablony.

### <a name="changes-to-the-baseline-settings"></a>Změny nastavení směrného plánu
Buď jsou následující nastavení:
- *Nové* v nejnovější verzi standardních hodnot.
- *Odebrat* z nejnovější základní verzi, ale nalezený počet byl v předchozí verzi.
- *Revidované téma* nějakým způsobem z vzhledu nastavení v předchozí verzi. 

*[Nové]*  [ **Nad zámkem**](#above-lock):
-  **Hlasové aktivovat aplikace na uzamčené obrazovce**    

*[Nové]*  [ **Správy aplikací**](#application-management): 
- **Blok kontrola uživatele nad instalací**  
- **Instalace aplikací MSI bloku se zvýšenými oprávněními**  

*[Odebrat]*  [ **Bitlocker**](#bitlocker):  
- Bit zásad schránky vyměnitelnou jednotku > **metoda šifrování**
- **Bit locker pevnou jednotku zásad** *(všechna nastavení)*
- **Bit locker systémové jednotky zásady** *(všechna nastavení)*

*[Nové]*  [ **Připojení**](#connectivity):
- **Konfigurace zabezpečeného přístupu k cesty UNC**

*[Nové]*  [ **Device Guard**](#device-guard):
- **Zabezpečení na základě virtualizace**


*[Nové]*  [ **DMA Guard**](#dma-guard):
- **Výčet externích zařízení nekompatibilní s ochranou DMA jádra**  

*[Nové]*  [ **Aplikace Internet Explorer**](#internet-explorer):
- **Aktualizace zóny internet Explorer na stavovém řádku prostřednictvím skriptu**
- **Zóny Internetu aplikace Internet Explorer přetáhněte nebo zkopírujte a vložte soubory**  
- **Spolehlivé součásti .NET Framework aplikace Internet Explorer s omezením pomocí specifikátoru zóny**  
- **Místní počítač zóny Internet Exploreru nespouštějte antimalwarové proti ovládací prvky ActiveX**
- **Podpora šifrování aplikace Internet Explorer**  

*[Revize]*  [ **Aplikace Internet Explorer**](#internet-explorer):
- **Automatické řádku aplikace Internet Explorer internetové zóny pro stahování souborů** > Výchozí hodnota je nyní **zakázané**. Ve verzi preview bylo nastavené na povoleno.

*[Nové]*  [ **Vzdálené pomoci**](#remote-assistance):  
- **Vzdálená pomoc, vyžádaná** 
  - **Vzdálená pomoc, vyžádaná oprávnění**
  - **Hodnota času maximální lístek**  
  - **Maximální lístek časové období**  
  - **E-mailovou pozvánku – metoda**


*[Nové]*  [ **Programu WIndows Defender**](#windows-defender):
- **Adobe Reader spustíte podřízený proces**  
- **Spuštění aplikace Office komunikace v podřízený proces** 

*[Nové]*  [ **Firewallu v programu Windows Defender**](#windows-defender-firewall)
- **Brány firewall na profil domény**  
  - **Příchozí připojení blokováno**  
  - **Odchozí připojení vyžaduje**  
  - **Příchozí upozornění blokované**  
  - **Povolenou bránu firewall**  
- **Veřejný profil firewallu v programu**  
  - **Příchozí připojení blokováno**  
  - **Odchozí připojení vyžaduje**  
  - **Příchozí upozornění blokované**  
  - **Povolenou bránu firewall** 
  - **Pravidla zabezpečení připojení ze zásad skupiny, které nebyly sloučeny**   
  - **Pravidla zásad ze zásad skupiny, které nebyly sloučeny**  
- **Privátní profil firewallu v programu**  
  - **Příchozí připojení blokováno**  
  - **Odchozí připojení vyžaduje**  
  - **Příchozí upozornění blokované**  
  - **Povolenou bránu firewall**  

*[Nové]*  [ **Windows Hello pro firmy**](#windows-hello-for-business):  
- **Vyžadují rozšířenou ochranu proti falšování identity, pokud je k dispozici**  
- **Konfigurovat Windows Hello pro firmy**  
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
  Microsoft Edge uses Windows Defender SmartScreen (turned on) to protect users from potential phishing scams and malicious software by default. Also, by default, users can't disable (turn off) Windows Defender SmartScreen. Enabling this policy turns off Windows Defender SmartScreen and prevent users from turning it on. Don’t configure this policy to let users choose to turn Windows defender SmartScreen on or off.  
  
  **Default**: Yes  
  
- **Block malicious site access**  
  By default, Microsoft Edge allows users to bypass (ignore) the Windows Defender SmartScreen warnings about potentially malicious sites, allowing them to continue to the site. With this policy though, you can configure Microsoft Edge to prevent users from bypassing the warnings, blocking them from continuing to the site.
  
  **Default**: Yes  
  
- **Block unverified file download**
  By default, Microsoft Edge allows users to bypass (ignore) the Windows Defender SmartScreen warnings about potentially malicious files, allowing them to continue downloading the unverified file(s). Enabling this policy prevents users from bypassing the warnings, blocking them from downloading of the unverified file(s).
  
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
  
## Windows Defender  
For more information, see [Policy CSP - Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) in the Windows documentation.  

- **Scan incoming mail messages**  
  Allows or disallows scanning of email.
  
  **Default**: Yes  

- **Office apps launch child process type**  
  Office apps won't be allowed to create child processes. This includes Word, Excel, PowerPoint, OneNote, and Access. This is a typical malware behavior, especially for macro-based attacks that attempt to use Office apps to launch or download malicious executables.
  
  **Default**: Block
  
- **Defender sample submission consent type**  
  Checks for the user consent level in Windows Defender to send data. If the required consent has already been granted, Windows Defender submits them. If not, (and if the user has specified never to ask), the UI is launched to ask for user consent (when Defender/AllowCloudProtection is allowed) before sending data.
  
  **Default**: Send safe samples automatically 
  
- **Signature update interval (in hours)**  
  Defender signature update interval in hours
  
  **Default**: 4
  
- **Script downloaded payload execution type**  
  Defender script downloaded payload execution type
  
  **Default**: Block
  
- **Prevent credential stealing type**  
  Windows Defender Credential Guard uses virtualization-based security to isolate secrets so that only privileged system software can access them. Unauthorized access to these secrets can lead to credential theft attacks, such as Pass-the-Hash or Pass-The-Ticket. Windows Defender Credential Guard prevents these attacks by protecting NTLM password hashes, Kerberos Ticket Granting Tickets, and credentials stored by applications as domain credentials.
  
  **Default**: Enable

- **Email content execution type**  
  This rule blocks the following file types from being run or launched from an email seen in either Microsoft Outlook or webmail (such as Gmail.com or Outlook.com): Executable files (such as .exe, .dll, or .scr) Script files (such as a PowerShell .ps, VisualBasic .vbs, or JavaScript .js file) Script archive files.
  
  **Default**: Block
  
- **Network protection type**  
  This policy allows you to turn on network protection (block/audit) or off in Windows Defender Exploit Guard. Network protection is a feature of Windows Defender Exploit Guard that protects employees using any app from accessing phishing scams, exploit-hosting sites, and malicious content on the Internet. This includes preventing third-party browsers from connecting to dangerous sites. Value type is integer. If you enable this setting, network protection is turned on and employees can't turn it off. Its behavior can be controlled by the following options: Block and Audit. If you enable this policy with the "Block" option, users and apps are blocked from connecting to dangerous domains. You can see this activity in Windows Defender Security Center. If you enable this policy with the "Audit" option, users/apps won't be blocked from connecting to dangerous domains. However, you'll still see this activity in Windows Defender Security Center. If you disable this policy, users/apps won't be blocked from connecting to dangerous domains. You'll not see any network activity in Windows Defender Security Center. If you don't configure this policy, network blocking is disabled by default.
  
  **Default**: Enable
  
- **Defender schedule scan day**  
  Defender schedule scan day.
  
  **Default**: Everyday
  
- **Cloud-delivered protection**  
  To best protect your PC, Windows Defender will send information to Microsoft about any problems it finds. Microsoft will analyze that information, learn more about problems affecting you and other customers, and offer improved solutions.
  
  **Default**:  Yes  

- **Defender potentially unwanted app action**  
  The potentially unwanted application (PUA) protection feature in Windows Defender Antivirus can identify and block PUAs from downloading and installing on endpoints in your network. These applications aren't considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use. PUA can also refer to applications that are considered to have a poor reputation. Typical PUA behavior includes: Various types of software bundling Ad injection into web browsers Driver and registry optimizers that detect issues, request payment to fix the errors, but remain on the endpoint and make no changes or optimizations (also known as "rogue antivirus" programs). These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.  
  
  **Default**: Block  

- **Script obfuscated macro code type**  
  Malware and other threats can attempt to obfuscate or hide their malicious code in some script files. This rule prevents scripts that appear to be obfuscated from running.
  
  **Default**: Block
  
- **Scan removable drives during a full scan**  
  Allows Windows Defender to scan for malicious and unwanted software in removable drives (for example, flash drives) during a full scan. Windows Defender Antivirus scans all files on USB devices before execution.
  
  **Default**: Yes  
  
- **Scan archive files**  
  Defender scan archive files.
  
  **Default**: Yes
  
- **Behavior monitoring**  
  Allows or disallows Windows Defender Behavior Monitoring functionality.Embedded in Windows 10, these sensors collect and process behavioral signals from the operating system and sends this sensor data to your private, isolated, cloud instance of Microsoft Defender ATP.
  
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
