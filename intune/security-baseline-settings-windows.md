---
title: Nastavení směrné plány zabezpečení Windows Intune
titleSuffix: Microsoft Intune
description: Windows security základní nastavení zkonstruovat pomocí Intune
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 58a57b14387ae6f366c4ac022bdacae7111fc1da
ms.sourcegitcommit: dde9e1e1d15c412751a186410c2a04974ff1b102
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/04/2019
ms.locfileid: "55690846"
---
# <a name="windows-security-baseline-settings-for-intune"></a>Základní nastavení zabezpečení Windows Intune  

Zobrazení [nastavení standardních hodnot zabezpečení Windows](security-baselines.md) , který podporuje Microsoft Intune.  


## <a name="above-lock"></a>Nad zámkem  
Další informace najdete v tématu [zásady CSP – AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) v dokumentaci k Windows.  

- **Blokovat zobrazování informační zprávy**  
  Nastavení této zásady umožňuje zabránit oznámení aplikací povolí, na zamykací obrazovce. Pokud nastavení této zásady povolíte, žádná oznámení. aplikace se zobrazí na zamykací obrazovce. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, uživatelé aplikace, které mohou zobrazovat oznámení na zamykací obrazovce.
  - **Výchozí**: Ano  

## <a name="app-runtime"></a>Modul Runtime aplikace    
Další informace najdete v tématu [zásady CSP – AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) v dokumentaci k Windows.  

- **Účty Microsoft, volitelné pro aplikace Windows Store**  
  Nastavení této zásady umožňuje řídit, zda jsou účty Microsoft volitelné pro aplikace Windows Store, které vyžadují účet pro přihlášení. Tyto zásady ovlivní pouze aplikace Windows Store, které ji podporují. Pokud povolíte toto nastavení zásad, aplikací Windows Store, které obvykle vyžadují účet Microsoft pro přihlášení vám umožní uživatelům přihlašovat se místo toho se pomocí účtu organizace. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, uživatelé budou potřebovat k přihlášení pomocí účtu Microsoft.  
  - **Výchozí**: Povoleno  

## <a name="application-management"></a>Správa aplikací   
Další informace najdete v tématu [zásady CSP – ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) v dokumentaci k Windows.  

- **Blokovat záznam ze hry (jenom desktopové verze)**  
  Nakonfiguruje, jestli je povolené záznam a vysílání z her.
  - **Výchozí**: Ano  

## <a name="auto-play"></a>Auto Play   
Další informace najdete v tématu [zásady – CSP pro automatické přehrání](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay
) v dokumentaci k Windows.  

- **Automatické přehrávání automaticky výchozí chování při spuštění**  
  Toto nastavení má vliv na výchozí chování pro automatické spouštění příkazů. Příkazy automatického spuštění jsou uloženy v souborech autorun.inf a můžete spustit instalační programy nebo jiných rutin. Když *povoleno*, Správce může změnit výchozí chování automatického spuštění na zařízení se systémem Windows Vista nebo novější. Chování může být nastaven na: a) zcela zakázat příkazy automatického spuštění, nebo (b) vrátit zpět k než Windows Vista chování automaticky spouští se příkaz automatického spuštění. Pokud je nastavena na *zakázané* nebo *Nenakonfigurováno*, zařízení, na kterých běží Windows Vista nebo novější řádku uživatele o tom, zda automatického spuštění má příkaz spustit.
  - **Výchozí**: Neprovádět je  
  
- **Režim automatického přehrávání**  
  Nastavení této zásady umožňuje vypnout funkci automatického přehrávání. Automatické přehrávání zahájí čtení z disku jako vložte médium do jednotky. V důsledku toho instalační soubor programů a hudbu na médiu zvuku spustit okamžitě. Před Windows XP SP2 je zakázané automatické přehrávání ve výchozím nastavení na vyměnitelné jednotky, jako je například disketové jednotky (ale ne jednotce CD-ROM) a na síťové jednotky. Od verze Windows XP SP2, automatické přehrávání je povolený pro vyměnitelné jednotky, včetně jednotky Zip a některé velkokapacitního paměťového zařízení USB. Pokud povolíte toto nastavení zásad, automatické přehrávání je zakázáno na disku CD-ROM a vyměnitelných jednotek nebo zakázaná na všech jednotkách. Nastavení této zásady se zakáže automatické přehrávání na dalších typů jednotek. Nelze pomocí tohoto nastavení můžete povolit automatické přehrávání na diskové jednotky, na kterých je ve výchozím nastavení zakázána. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, je povoleno automatické přehrávání. Poznámka: Nastavení této zásady se zobrazí ve složkách Konfigurace počítače a konfigurace uživatele. Pokud nastavení zásad jsou v konfliktu, nastavení zásad Konfigurace počítače má přednost před nastavení zásad Konfigurace uživatele.
  - **Výchozí**: Zakázáno

- **Blokovat automatické přehrávání pro zařízení bez svazku**  
  Nastavení této zásady zakazuje automatické přehrávání pro zařízení MTP, jako jsou kamery a telefonů. Pokud povolíte toto nastavení zásad, automatické přehrávání není povolena pro zařízení MTP, jako jsou kamery a telefonů. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, automatické přehrávání je povolený pro zařízení bez svazku.
  - **Výchozí**: Povoleno  

## <a name="bitlocker"></a>Nástroj BitLocker    
Další informace najdete v tématu [zásady CSP – Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) v dokumentaci k Windows.  

- **Bit locker vyměnitelnou jednotku zásad**  
  Nastavení této zásady umožňuje řídit metodu, šifrování a šifer síly. Hodnoty těchto zásad určuje sílu šifra, která používá nástroj BitLocker k šifrování. Podniky může chtít řídit úroveň šifrování (AES-256 je silnější než AES-128) zvýšené zabezpečení. Pokud povolíte toto nastavení, bude možné nakonfigurovat jednotlivě šifrovací algoritmus a klíče úroveň šifrování pro pevné datové jednotky, jednotky s operačním systémem a vyměnitelné datové jednotky. Oprava a provozní systémové jednotky doporučujeme použít algoritmus XTS-AES. Vyměnitelných jednotek měli byste použít AES-CBC 128-bit nebo AES-CBC oborového 256bitového Pokud na jednotce se použijí v jiných zařízení se systémem Windows 10 verze 1511 nebo novější. Změna metoda šifrování nemá žádný účinek, pokud už zašifrovaná disku nebo šifrování probíhá. V těchto případech toto nastavení zásad se ignoruje.

    - **Vyžadovat šifrování pro zápis**
      - **Výchozí**: Ano  

    - **Metoda šifrování**
      - **Výchozí**: AES 256bit CBC  

- **Bit locker pevnou jednotku zásad**  
  Nastavení této zásady umožňuje řídit metodu, šifrování a šifer síly. Hodnoty těchto zásad určuje sílu šifra, která používá nástroj BitLocker k šifrování. Podniky může chtít řídit úroveň šifrování (AES-256 je silnější než AES-128) zvýšené zabezpečení. Pokud povolíte toto nastavení, bude možné nakonfigurovat jednotlivě šifrovací algoritmus a klíče úroveň šifrování pro pevné datové jednotky, jednotky s operačním systémem a vyměnitelné datové jednotky. Oprava a provozní systémové jednotky doporučujeme použít algoritmus XTS-AES. Vyměnitelných jednotek měli byste použít AES-CBC 128-bit nebo AES-CBC oborového 256bitového Pokud na jednotce se použijí v jiných zařízení se systémem Windows 10 verze 1511 nebo novější. Změna metoda šifrování nemá žádný účinek, pokud už zašifrovaná disku nebo šifrování probíhá. V těchto případech toto nastavení zásad se ignoruje.  
 
  - **Metoda šifrování**
    - **Výchozí**: AES 256 bitů XTS  

- **Bit locker systémové jednotky zásady**  
  Nastavení této zásady umožňuje řídit metodu, šifrování a šifer síly. Hodnoty těchto zásad určuje sílu šifra, která používá nástroj BitLocker k šifrování. Podniky může chtít řídit úroveň šifrování (AES-256 je silnější než AES-128) zvýšené zabezpečení. Pokud povolíte toto nastavení, bude možné nakonfigurovat jednotlivě šifrovací algoritmus a klíče úroveň šifrování pro pevné datové jednotky, jednotky s operačním systémem a vyměnitelné datové jednotky. Oprava a provozní systémové jednotky doporučujeme použít algoritmus XTS-AES. Vyměnitelných jednotek měli byste použít AES-CBC 128-bit nebo AES-CBC oborového 256bitového Pokud na jednotce se použijí v jiných zařízení se systémem Windows 10 verze 1511 nebo novější. Změna metoda šifrování nemá žádný účinek, pokud už zašifrovaná disku nebo šifrování probíhá. V těchto případech toto nastavení zásad se ignoruje.  

  - **Metoda šifrování**  
    - **Výchozí**: AES 256 bitů XTS  

## <a name="browser"></a>Prohlížeč  
Další informace najdete v tématu [zásady CSP – prohlížeč](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) v dokumentaci k Windows.  

- **Vyžadovat SmartScreen pro Microsoft Edge**  
  Microsoft Edge používá k ochraně uživatelů před podvodných potenciální a škodlivým softwarem ve výchozím nastavení Windows Defender SmartScreen (zapnuto). Ve výchozím nastavení, také uživatele nelze zakázat (vypnout) Windows Defender SmartScreen. Když se tyto zásady vypne Windows Defender SmartScreen a zabrání uživatelům ho zapnout. Nekonfigurujte tato zásada umožňuje uživatelům zvolit program Windows defender SmartScreen zapnout nebo vypnout.  
  - **Výchozí**: Ano  
  
- **Blokovat přístup na škodlivý web**  
  Ve výchozím nastavení, Microsoft Edge umožňují uživatelům obejít (Ignorovat) upozornění filtru Windows Defender SmartScreen potenciálně škodlivé weby, což jim umožní pokračovat na příslušný web. K této zásadě ale můžete nakonfigurovat Microsoft Edge uživatelům zabránit v obejít upozornění, blokování pokračování k webu.
  - **Výchozí**: Ano  
  
- **Blokovat stahování neověřených souborů**  </br>
  Ve výchozím nastavení, Microsoft Edge umožňují uživatelům obejít (Ignorovat) upozornění filtru Windows Defender SmartScreen na potenciálně škodlivých souborů, což jim umožní pokračovat ve stahování neověřených souborů. Když se tyto zásady zabrání uživatelům obejít upozornění, blokování stahování neověřených souborů.
  - **Výchozí**: Ano  
  
- **Blokovat správce hesel**  </br>
  Ve výchozím nastavení Microsoft Edge použije správce hesel automaticky, umožní tak místně hesla správce. V případě jejího zakázání brání použití hesla správce Microsoft Edge. Pokud chcete umožnit uživatelům ukládat a spravovat hesla místně s použitím správce hesel, nekonfigurujte tuto zásadu.
  - **Výchozí**: Ano  
  
- **Zabránit přepsání Chyba certifikátu**  </br>
  Nastavení této zásady zabrání uživateli možnost Ignorovat chyby certifikátů Secure Sockets Layer/Transport Layer Security (SSL/TLS), které přerušení procházení (jako "prošlé", "zrušeno" nebo "došlo k neshodě názvů" chyby) v aplikaci Internet Explorer. Pokud nastavení této zásady povolíte, uživatel nemůže pokračovat v procházení. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, uživatel můžete rozhodnout ignorovat chyby certifikátů a pokračovat v procházení.
  - **Výchozí**: Ano  

## <a name="connectivity"></a>Připojení  
Další informace najdete v tématu [zásady CSP – připojení](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) v dokumentaci k Windows.  

- **Stahování z Internetu bloku pro webové, publikování a online objednáním**  
  Nastavení této zásady určuje, zda by měl Windows stáhnout seznam poskytovatelů pro weby, publikování a online objednáním. Tito průvodci povolit uživatelům výběr ze seznamu společností, které poskytují služby, jako je online úložiště a tisk fotografií. Ve výchozím nastavení zobrazí stažené z webu Windows kromě poskytovatelů uvedený v registru Windows. Pokud nastavení této zásady povolíte, Windows nebude stahovat poskytovatele a zobrazují se pouze poskytovatelé služeb, které jsou uložené v mezipaměti v místním registru. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, seznam zprostředkovatelů se stáhne, pokud uživatel použije webového publikování nebo online objednáním. Další informace včetně podrobností o zadání poskytovatelů služeb v registru naleznete v dokumentaci pro weby, publikování a online objednáním.  
  - **Výchozí**: Povoleno  

- **Blokovat stahování ovladačů tiskáren pomocí protokolu HTTP**  
  Nastavení této zásady určuje, jestli se má povolit tohoto klienta stáhnout balíčky ovladače tiskárny přes protokol HTTP. Nastavení HTTP tisk, ovladače doručené pošty není třeba stahovat přes protokol HTTP. Poznámka: Nastavení této zásady nebrání Klient tisku na tiskárnách na intranetu nebo Internetu přes protokol HTTP. Zakazuje pouze stahování ovladačů, které nejsou nainstalovány místně. Pokud nastavení této zásady povolíte, nejde stáhnout ovladačů tiskárny přes protokol HTTP. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, uživatelé můžou stahovat ovladačů tiskárny přes protokol HTTP.
  - **Výchozí**: Povoleno  

## <a name="credentials-delegation"></a>Delegování přihlašovacích údajů  
Další informace najdete v tématu [zásady CSP – CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) v dokumentaci k Windows.  

- **Vzdálený hostitel delegování neexportovatelného přihlašovacích údajů**  
  Vzdálený hostitel povoluje delegování neexportovatelného přihlašovacích údajů. Při použití delegování přihlašovacích údajů, zařízení poskytují exportovatelné verzi přihlašovací údaje ke vzdálenému hostiteli. Tato třída zveřejňuje uživatelé riziku krádeže přihlašovacích údajů z útočníci na vzdáleného hostitele. Pokud nastavení této zásady povolíte, hostitel podporuje režim Restrictedadmin nebo vzdálené Credential Guard. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad správy s omezeným přístupem a režim vzdáleného Credential Guard nejsou podporovány. Uživatel bude muset vždy předat své přihlašovací údaje k hostiteli.  

  - **Výchozí**: Povoleno  

## <a name="credentials-ui"></a>Přihlašovací údaje uživatelského rozhraní  
Další informace najdete v tématu [zásady CSP – CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) v dokumentaci k Windows.  

- **Zobrazení výčtu správci**    
  Tato zásada, nastavení ovládacích prvků, jestli účty správce se zobrazí, když se uživatel pokusí zvýšit běžící aplikaci. Ve výchozím nastavení nejsou zobrazeny účty správců, když se uživatel pokusí zvýšit běžící aplikaci. Pokud povolíte toto nastavení zásad, takže uživatel může zvolit jednu a zadejte správné heslo se zobrazí všechny účty oprávnění místního správce na počítači. Pokud nastavení této zásady zakážete, uživatelé se vždy třeba zadat uživatelské jméno a heslo pro zvýšení oprávnění.  

  - **Výchozí**: Zakázáno  

## <a name="data-protection"></a>Data Protection  
Další informace najdete v tématu [zásady CSP – DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) v dokumentaci k Windows.  

- **Blokovat přímý přístup do paměti**   
  Nastavení této zásady umožňuje blokovat přímý přístup do paměti (DMA) pro všechny aktivní modulární PCI podřízené porty dokud se uživatel přihlásí do Windows. Jakmile se uživatel přihlásí, bude Windows výčet PCI zařízení připojená k portům PCI moduly hostitele. Pokaždé, když se uživatel uzamkne na počítači, přímý přístup do paměti se zablokuje na portech PCI připojitelný s žádné podřízené položky zařízení dokud znovu přihlásí uživatel. Zařízení, které byly již uvedené, když je počítač se odemkl. bude nadále fungovat, dokud byl odpojen. Nastavení této zásady se vynucují jenom, když je povolené šifrování nástrojem BitLocker nebo zařízení.
  
  - **Výchozí**: Ano  

## <a name="device-guard"></a>Device Guard  
Další informace najdete v tématu [zásady CSP – DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) v dokumentaci k Windows.  

- **Credential Guard**  
  Toto nastavení umožňuje zapnout Credential Guard se zabezpečením na základě virtualizace k ochraně přihlašovací údaje při příštím restartování.
  
  - **Výchozí**: Povolit se zámkem UEFI 

- **Povolit zabezpečení na základě virtualizace**  </br>
  Zapne virtualizace na základě při příštím restartování zabezpečení (VBS). Zabezpečení na základě virtualizace nabízí podporu služeb zabezpečení pomocí hypervisoru Windows.
  - **Výchozí**: Ano  

- **Povolení zabezpečeného spouštění DMA**  
  Mezi příkazy, které následují můžete použít nastavení pro zabezpečené spouštění a zabezpečené spouštění s přímý přístup do paměti. Ve většině případů doporučujeme, abyste zvolili možnost zabezpečeného spouštění. Tato možnost poskytuje zabezpečené spouštění s co nejvíce protection podporuje danou počítačový hardware. Počítače s jednotkami správy paměti vstup/výstup (IOMMUs) bude mít zabezpečené spouštění s ochranou přímý přístup do paměti. Počítač bez IOMMUs jednoduše bude mít povolené zabezpečené spouštění. Naproti tomu se zabezpečeným spouštěním DMA bude toto nastavení Povolit zabezpečené spouštění – a VBS samotný – jenom na počítač, který podporuje přímý přístup do paměti, to znamená, že počítač s IOMMUs. S tímto nastavením nemají jakýkoli počítač bez IOMMUs VBS nebo HVCI ochranu, i když mají stále WDAC povolena.
  
  - **Výchozí**: Ano  
  
- **Spusťte systém guard**  
  - **Výchozí**: Povoleno  

## <a name="device-installation"></a>Instalace zařízení  
Další informace najdete v tématu [zásady CSP – DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) v dokumentaci k Windows.  

- **Instalace hardwaru zařízení pomocí identifikátorů zařízení**  
  Nastavení této zásady umožňuje zadat seznam ID Plug and Play hardwaru a kompatibilní ID pro zařízení, že je Windows zabráněno v instalaci. Toto nastavení zásad má přednost před jiného nastavení zásad, který umožňuje nainstalovat zařízení Windows. Pokud nastavení této zásady povolíte, je Windows zabránily instalaci zařízení, jejichž hardware kompatibilní ID nebo ID se zobrazí v seznamu, který vytvoříte. Pokud povolíte toto nastavení zásad v serveru vzdálené plochy, nastavení zásad má vliv přesměrování zadané zařízení z klienta vzdálené plochy k serveru vzdálené plochy. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, se můžou nainstalovat a aktualizovat, protože povolené nebo mu podle dalších nastavení zásad zařízení.
  - **Výchozí**: Instalace bloku hardwaru zařízení  
  
    - **Odeberte odpovídající hardwarové zařízení**  
      Toto nastavení je dostupná jenom v případě *instalace zařízení hardwaru pomocí identifikátorů zařízení* je nastavena na *služba neblokuje instalaci zařízení hardwaru*.
      - **Výchozí**: *Žádná výchozí konfigurace*
  
    - **Identifikátory hardwaru zařízení, které jsou blokovány**  </br>
      Toto nastavení je dostupná jenom v případě *instalace zařízení hardwaru pomocí identifikátorů zařízení* je nastavena na *služba neblokuje instalaci zařízení hardwaru*.
      - **Výchozí**: *Žádná výchozí konfigurace*  
  
- **Instalace hardwaru zařízení v nastavení tříd**  
  Nastavení této zásady umožňuje určit seznam zařízení nastavení třídy globálně jedinečné identifikátory (GUID) pro ovladače zařízení, že je Windows zabráněno v instalaci. Toto nastavení zásad má přednost před jiného nastavení zásad, který umožňuje nainstalovat zařízení Windows. Pokud nastavení této zásady povolíte, je Windows nebudou instalujete nebo aktualizujete ovladače zařízení, jehož třída instalace zařízení v seznamu se zobrazí identifikátory GUID vytvoříte. Pokud povolíte toto nastavení zásad v serveru vzdálené plochy, nastavení zásad má vliv přesměrování zadané zařízení z klienta vzdálené plochy k serveru vzdálené plochy. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, můžete nainstalovat Windows a aktualizace zařízení povolený, nebo z důvodu dalších nastavení zásad.
  - **Výchozí**: Instalace bloku hardwaru zařízení  
  
    - **Odeberte odpovídající hardwarové zařízení**  </br>
      Toto nastavení je dostupná jenom v případě *instalace hardwaru zařízení v nastavení tříd* je nastavena na *služba neblokuje instalaci zařízení hardwaru*.
      - **Výchozí**: *Žádná výchozí konfigurace*  
  
    - **Identifikátory hardwaru zařízení, které jsou blokovány**  </br>
      Toto nastavení je dostupná jenom v případě *instalace hardwaru zařízení v nastavení tříd* je nastavena na *služba neblokuje instalaci zařízení hardwaru*.
      - **Výchozí**: *Žádná výchozí konfigurace*  

## <a name="device-lock"></a>Uzamčení zařízení  
Další informace najdete v tématu [zásady CSP – DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) v dokumentaci k Windows.  

- **Zakázat použití fotoaparátu**  
  Zakáže přepínač zámek obrazovky fotoaparát v nastavení počítače a zabraňuje kamera vyvolání na zamykací obrazovce. Ve výchozím nastavení můžete uživatelům povolit volání k dispozici fotoaparátu na zamykací obrazovce. Pokud toto nastavení povolíte, uživatelé už nebudou moct povolit nebo zakázat přístup k fotoaparátu zámek obrazovky v nastavení počítače a fotoaparátu/kamery nelze vyvolat na zamykací obrazovce.  
  - **Výchozí**: Povoleno  

- **Vyžadovat heslo**  
  Určuje, zda je povoleno uzamčení zařízení.
  - **Výchozí**: Ano  
  
  - **Minimální znak hesla nastavit počet**  
    Počet typů komplexních prvků (velká a malá písmena, číslice a interpunkční znaménka) požadované pro silný PIN kód nebo heslo. PIN kód vynucuje toto chování pro stolní počítače a mobilní zařízení: 1 - číslice pouze 2 - číslice a malá písmena jsou požadované 3 - číslice a malá písmena a velká písmena se vyžadují. Nepodporováno v klasické pracovní plochy účty Microsoft a účty domény. 4 - číslice, malá písmena, velká písmena a speciální znaky jsou povinné. Není podporován v desktopu. Výchozí hodnota je 1. 
    - **Výchozí**: 3  
  
  - **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**  
    Počet chyb ověřování povolené předtím, než zařízení bude vymazáno. Hodnota 0 zakáže funkci vymazání zařízení.
    - **Výchozí**: 10  
  
  - **Vypršení platnosti hesla (dny)**  
    Určuje nastavení zásad pro stáří hesla maximální dobu (ve dnech), po kterou může být heslo použít předtím, než bude systém vyžadovat uživateli ji změnit. Můžete nastavit hesla vyprší po uplynutí počtu dnů mezi 1 a 999, nebo můžete určit, že platnost hesel nikdy nevypršela tak, že nastavíte časový interval na hodnotu 0. Pokud je maximální stáří hesla mezi 1 a 999 dní, minimální stáří hesla musí být menší než je maximální stáří hesla. Pokud je maximální stáří hesla nastavená na hodnotu 0, může být minimální stáří hesla libovolnou hodnotu mezi 0 a 998 dnů.
    - **Výchozí**: 60  
  
  - **Požadovaný typ hesla**  
    Určuje typ kódu PIN nebo heslem.
    - **Výchozí**: Alfanumerické znaky  
  
  - **Minimální délka hesla**  
    Nastavení zásad délka hesel minimální Určuje nejmenší počet znaků, které můžete vytvořit heslo pro uživatelský účet. Můžete nastavit hodnotu mezi 1 a 14 znaků, nebo vám pomůže zajistit, že není požadováno žádné heslo tak, že počet znaků, které nastavíte na hodnotu 0.
    - **Výchozí**: 8  
  
  - **Blokovat jednoduchá hesla**  
    Určuje, zda jsou povolena PIN kódy nebo hesla, jako je například "1111" nebo "1234". Pro stolní počítače se řídí navíc i použití obrázkových hesel.
    - **Výchozí**: Ano  
       *Nastavení na Ano brání použití jednoduchých hesel.* 

  - **Znemožnit opakované použití předchozích hesel**  
    Určuje, kolik hesel mohou být uloženy v historii, který nelze použít. Tato hodnota zahrnuje aktuální heslo uživatele. To znamená, že s nastavením 1 uživatel nemůže znovu použít své aktuální heslo při výběru nové heslo, při nastavení *5* znamená, že nelze uživatel nastavit nové heslo pro jejich aktuální heslo nebo některý z jejich předchozí čtyři hesla.
    - **Výchozí**: 24  

- **Zabránit prezentace**  
  Zakáže nastavení zamykací obrazovky prezentace v nastavení počítače a prezentace brání přehrávání na zamykací obrazovce. Ve výchozím nastavení můžete uživatelům povolit prezentace, která se spustí po jejich uzamčení počítače. Pokud toto nastavení povolíte, uživatelé už nebudou moct změnit nastavení prezentace v nastavení počítače a někdy se spustí bez zobrazení snímku.
  - **Výchozí**: Povoleno  
    *Nastavení povoleno prezentace zabraňuje spuštění.* 

- **Minimální stáří hesla ve dnech**  
  Nastavení minimální stáří hesla zásady určuje dobu (ve dnech), po kterou musí být heslo použít předtím, než ho uživatel může změnit. Můžete nastavit hodnotu v rozmezí 1 až 998 dnů nebo změny hesla můžete povolit okamžitě tak, že nastavíte časový interval na hodnotu 0. Minimální stáří hesla musí být menší než maximální stáří hesla, pokud je maximální stáří hesla je nastaven na hodnotu 0 označující, že hesla nikdy nevyprší. Pokud je maximální stáří hesla je nastavena na hodnotu 0, minimální stáří hesla můžete nastavit na libovolnou hodnotu mezi 0 a 998.
  - **Výchozí**: 1  

## <a name="event-log-service"></a>Služba Protokol událostí  
Další informace najdete v tématu [zásady CSP – EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) v dokumentaci k Windows.  

- **Maximální velikost protokolu zabezpečení v článku KB**  
  Nastavení této zásady určuje v kilobajtech maximální velikost souboru protokolu. Pokud nastavení této zásady povolíte, můžete nakonfigurovat maximální velikost souboru protokolu být v rozmezí 1 MB (1 024 kB) a 2 terabajty (2147483647 kilobajtů) v přírůstcích po kilobajtů. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, nastaví maximální velikost souboru protokolu pro místně konfigurovaná hodnota. Tuto hodnotu můžete změnit místní správce v dialogovém okně Vlastnosti protokolu a výchozí hodnota 20 megabajtů.
  - **Výchozí**: 196608  

- **Systém protokolu maximální velikost v KB**  
  Nastavení této zásady určuje v kilobajtech maximální velikost souboru protokolu. Pokud nastavení této zásady povolíte, můžete nakonfigurovat maximální velikost souboru protokolu být v rozmezí 1 MB (1 024 kB) a 2 terabajty (2147483647 kilobajtů) v přírůstcích po kilobajtů. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, nastaví maximální velikost souboru protokolu pro místně konfigurovaná hodnota. Tuto hodnotu můžete změnit místní správce v dialogovém okně Vlastnosti protokolu a výchozí hodnota 20 megabajtů.
  - **Výchozí**: 32768  

- **Aplikace protokolu maximální velikost v KB**  
  Nastavení této zásady určuje v kilobajtech maximální velikost souboru protokolu. Pokud nastavení této zásady povolíte, můžete nakonfigurovat maximální velikost souboru protokolu být v rozmezí 1 MB (1 024 kB) a 2 terabajty (2147483647 kilobajtů) v přírůstcích po kilobajtů. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, nastaví maximální velikost souboru protokolu pro místně konfigurovaná hodnota. Tuto hodnotu můžete změnit místní správce v dialogovém okně Vlastnosti protokolu a výchozí hodnota 20 megabajtů.
  - **Výchozí**: 32768  

## <a name="experience"></a>Prostředí  
Další informace najdete v tématu [zásady CSP – prostředí](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) v dokumentaci k Windows.  

- **Blokovat Windows Spotlight**  
  Umožňuje správcům IT vypnout všechny Windows Spotlight funkce – Windows spotlight na zamykací obrazovce, tipy Windows, Microsoft uživatelské funkce a další související funkce.
  - **Výchozí**: Ano  
  
  - **Blokovat návrhy třetích stran ve Windows Spotlightu**  
    Určuje, zda povolit návrhy aplikací a obsahu z jiných výrobců softwaru vydavateli ve Windows spotlight funkce, jako je spotlight zámek obrazovky, navrhované aplikace v nabídce Start a tipy Windows. Uživatelé můžou pořád ještě považuje návrhy funkcí, aplikací a služeb společnosti Microsoft.
     - **Výchozí**: Ano  
  - **Blokovat konkrétní uživatelské funkce**  
    Umožňuje správcům IT zapnout prostředí, které jsou obvykle jenom uživatelům, jako jsou návrhy nabídky Start, oznámení o členství, instalace aplikací příspěvek prvním spuštění počítače a dlaždice pro přesměrování.
    - **Výchozí**: Ano  


## <a name="exploit-guard"></a>Ochrana Exploit Guard  
Další informace najdete v tématu [zásady CSP – ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) v dokumentaci k Windows.  

- **Ochrana Exploit protection XML**  
  Umožňuje správci IT vydat konfigurace představující požadovaný systém, omezení rizik možnosti aplikace pro všechna zařízení v organizaci. Představuje konfiguraci XML. Ochranu před zneužitím platí, pomáhá chránit zařízení před malwarem, který zneužití šíří a terčem útoků. Použijete aplikace Windows zabezpečení nebo prostředí PowerShell k vytvoření sadu omezení rizik (označované jako konfigurace). Pak můžete exportovat tuto konfiguraci jako soubor XML a sdílet ho s více počítači ve vaší síti všechny mají stejnou sadu nastavení zmírňování. Můžete také převést a importovat existující sada nástrojů EMET konfigurační soubor XML do konfiguraci ochrany před zneužitím XML.
  - **Výchozí**: *Ukázkové xml je k dispozici* 
 
## <a name="file-explorer"></a>Průzkumník souborů  
Další informace najdete v tématu [zásady CSP – Průzkumník souborů](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) v dokumentaci k Windows.  

- **Zabránění spuštění dat bloku**  
  Zakázání zabránění spuštění dat můžete povolit určité starší modul plug-in aplikace fungovat bez ukončující Průzkumníka.
  - **Výchozí**: Zakázáno  
   
- **Ukončení bloku haldy na poškození**  
  Zakázání ukončení poškození haldy můžete povolit určité starší modul plug-in aplikace fungovat okamžitě, bez ukončujícího znaku Explorer, ačkoli Průzkumník může stále dojde k neočekávanému ukončení později.
  - **Výchozí**: Zakázáno  
    

## <a name="internet-explorer"></a>Internet Explorer  
Další informace najdete v tématu [zásady CSP – Internet Explorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) v dokumentaci k Windows.  

- **Kontrolovat příchozí e-mailové zprávy**  
  Povolí nebo zakáže kontrolu e-mailu.
  - **Výchozí**: Zakázáno  
  
- **Aplikace Office spusťte podřízený proces typ**  
  Aplikace Office nebudou moct vytvářet podřízené procesy. To zahrnuje Word, Excel, PowerPoint, OneNote a přístup. Toto je chování typické malware, hlavně pro útoky – makro, které se snaží používat aplikace Office spouštět ani se stahování škodlivého spustitelné soubory.
  - **Výchozí**: Zakázat  
  
- **Typ souhlasu odeslání vzorku defenderu**  
  Kontroly pro uživatele souhlas úrovni v programu Windows Defender odesílat data. Pokud již bylo uděleno vyžaduje souhlas, program Windows Defender odešle je. Pokud tomu tak není (a pokud uživatel zadal nikdy se zeptat), požádejte ho o souhlas uživatele (Pokud je povoleno Defender/AllowCloudProtection) před odesláním údajů se spustí uživatelské rozhraní.
  - **Výchozí**: Zakázat  
  
- **Interval aktualizace podpisu (v hodinách)**  
  Interval aktualizace podpisu Defender v hodinách
  - **Výchozí**: Zakázáno  
  
- **Přístup k zóny Internetu aplikace Internet Explorer ke zdrojům dat**  
  Nastavení této zásady umožňuje určit, zda aplikace Internet Explorer můžete přistupovat k datům z jiné zóny zabezpečení pomocí Microsoft XML Parser (MSXML) nebo objekty ADO (ActiveX Data OBJECTS). Pokud nastavení této zásady povolíte, uživatelé můžou načítat stránku v oblasti, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat zvolit, jestli se má povolit stránky, který se má načíst v zóně, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud nastavení této zásady zakážete, uživatelé nelze načíst stránku v oblasti, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud nastavení této zásady nenakonfigurujete, uživateli nelze načíst stránku v oblasti, která používá pro přístup k datům z jiné lokality v zóně MSXML nebo ADO.
  - **Výchozí**: Zakázat  
  
- **Zóny s omezeným přístupem v Internet Exploreru přetáhněte obsah z jiných domén v rámci systému windows**  
  Nastavení této zásady umožňuje nastavit možnosti pro přetažení obsah z jedné domény do jiné domény, pokud zdroj a cíl nacházejí ve stejném okně. Pokud povolíte toto nastavení zásad a klikněte na možnost povolit, uživatelé můžete přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl nacházejí ve stejném okně. Uživatelé nemohou změnit toto nastavení. Pokud povolíte toto nastavení zásad a klikněte na možnost zakázat, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl nacházejí ve stejném okně. Uživatelé nemohou změnit toto nastavení v dialogovém okně Možnosti Internetu. V Internet Exploreru 10 Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl nacházejí ve stejném okně. Uživatelé mohou změnit toto nastavení v dialogovém okně Možnosti Internetu. V aplikaci Internet Explorer 9 a starší Pokud toto nastavení zásad zakážete nebo nenakonfigurujete, uživatelé můžete přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí ve stejném okně. Uživatelé nemohou změnit toto nastavení v dialogovém okně Možnosti Internetu.
  - **Výchozí**: Zakázáno
  
- **Upozornění o neshodě certifikátu adresa aplikace Internet Explorer**  
  Nastavení této zásady umožňuje zapnout upozornění zabezpečení neshoda adresy certifikátu. Pokud nastavení této zásady je zapnuté, uživatel je upozorněn při návštěvě této k dispozici certifikáty vydané pro jiný web adresu weby Secure HTTP (HTTPS). Toto upozornění zabraňuje podvodným útokům. Pokud nastavení této zásady povolíte, certifikát adresu neshoda upozornění vždy se zobrazí. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, uživatel může zvolit, zda se zobrazí upozornění o neshodě adresu certifikát (s použitím pokročilé stránky Internet ovládacího panelu).
  - **Výchozí**: Povoleno 
  
- **Aplikace Internet Explorer s omezeným přístupem zóna menší privilegované webů**  
  Nastavení této zásady umožňuje určit, zda webů z méně privilegovaným zóny, jako jsou internetové weby se můžete dostat do této zóny. Pokud nastavení této zásady povolíte, webové servery ze zóny méně privilegovaným můžete otevřít v nových oknech, nebo přejít do této zóny. Zóna zabezpečení se spustí bez další úroveň zabezpečení, které poskytuje ochranu před funkci zabezpečení ke zvýšení úrovně oprávnění zóny. Pokud v rozevíracím seznamu vyberte řádek, objeví se upozornění pro uživatele, které potenciálně nebezpečné navigace se použije. Pokud nastavení této zásady zakážete, nebudou další potenciálně škodlivé navigaci. Funkce zabezpečení aplikace Internet Explorer, bude na v této zóně úmluvu ochranu ze zóny zvýšení funkce správy. Pokud nastavení této zásady nenakonfigurujete, nebudou další potenciálně škodlivé navigaci. Funkce zabezpečení aplikace Internet Explorer, bude na v této zóně úmluvu ochranu ze zóny zvýšení funkce správy.
  - **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer zakázané zóny automatické řádku pro soubor ke stažení**  </br>
  Nastavení této zásady určuje, zda uživatelům se zobrazí výzva pro stahování souborů bez zahájená uživatelem. Bez ohledu na toto nastavení, uživatelé dostanou dialogová okna Stažení souboru pro uživatelem iniciované soubory ke stažení. Pokud toto nastavení povolíte, uživatelům se zobrazí dialogové okno Stažení souboru pro pokusy o automatické stahování. Pokud zakážete nebo nenakonfigurujete toto nastavení zablokuje stahování souborů, které nejsou uživatelem iniciované a uživatelům se zobrazí oznamovací pruh místo dialogu stažení souboru. Uživatelům můžete pak kliknout na oznamovací pruh umožňuje výzva ke stažení souboru.
  - **Výchozí**: Zakázáno
  
- **Spolehlivé součásti aplikace Internet Explorer internetové zóny rozhraní .NET Framework**  
  Nastavení této zásady umožňuje určit, zda mohou být spuštěny součásti rozhraní .NET Framework, které nejsou podepsané pomocí technologie Authenticode aplikace Internet Explorer. Mezi tyto komponenty patří spravované ovládací prvky, které odkazuje objektu značku a spravované spustitelné soubory, které na něj odkazovat z odkazu. Pokud nastavení této zásady povolíte, Internet Explorer se spustí bez znaménka spravované součásti. Pokud v rozevíracím seznamu vyberte řádek, Internet Explorer vyzve uživatele k určení, jestli se má provést bez znaménka spravované součásti. Pokud nastavení této zásady zakážete, aplikace Internet Explorer nespustí, bez znaménka spravované součásti. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer se spustí bez znaménka spravované součásti.
  - **Výchozí**: Zakázat 
  
- **Povolit zóny Internetu aplikace Internet Explorer schválí jen tehdy, domén používat ovládací prvky ActiveX ORS**  </br>
  Toto nastavení zásady řídí, jestli uživatel smí spouštět ovládací prvek ActiveX ORS na webech. Pokud nastavení této zásady povolíte, ovládací prvek ActiveX ORS nespustí z webů v této zóně. Pokud nastavení této zásady zakážete, ovládací prvek ActiveX ORS se spustí ze všech lokalit v této zóně.
  - **Výchozí**: Povoleno 
  
- **Skript zóny s omezením pomocí specifikátoru aplikace Internet Explorer inicioval systému windows**  
  Toto nastavení zásad umožňuje spravovat omezení iniciované skriptu automaticky otevíraná okna a okna, která zahrnují panely názvu a stavu. Pokud nastavení této zásady povolíte, nebude v této zóně použít Windows omezení zabezpečení. Zóna zabezpečení se spustí bez další úroveň zabezpečení poskytované touto funkcí. Pokud nastavení této zásady zakážete, je to možné škodlivých akcí, které jsou součástí iniciované skriptu automaticky otevíraná okna a okna, která zahrnují panely názvu a stavu nelze spustit. Tuto funkci zabezpečení aplikace Internet Explorer bude na v této zóně určený nastavení pro proces řízení funkci skripty Windows bezpečnostní omezení. Pokud nastavení této zásady nenakonfigurujete, je to možné škodlivých akcí, které jsou součástí iniciované skriptu automaticky otevíraná okna a okna, která zahrnují panely názvu a stavu nelze spustit. Tuto funkci zabezpečení aplikace Internet Explorer bude na v této zóně určený nastavení pro proces řízení funkci skripty Windows bezpečnostní omezení.
  - **Výchozí**: Zakázáno 
  
- **Zóny Internetu aplikace Internet Explorer zahrnují místní cesty při nahrávání souborů do serveru**  </br>
  Nastavení této zásady určuje, zda je či není místní cesta informace se odešle, když uživatel je nahrát soubor přes formulář HTML. Pokud se pošle informace o místní cestu a některé informace mohou neúmyslně odhalena k serveru. Soubory odeslané z plochy uživatele, může obsahovat uživatelské jméno jako součást cesty. Pokud nastavení této zásady povolíte, informace o cestě se odešle, když uživatel je nahrát soubor přes formulář HTML. Pokud nastavení této zásady zakážete, informace o cestě se odebere, pokud uživatel odesílá soubory přes formulář HTML. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, zda informace o cestě se odešle, když při nahrávání souborů přes formulář HTML. Ve výchozím nastavení je odeslána informace o cestě.
  - **Výchozí**: Zakázáno 
  
- **Zakázat procesy v rozšířený chráněný režim Internet Exploreru**  
  Nastavení této zásady určuje, zda aplikace Internet Explorer 11 používá 64bitové procesy (kvůli lepšímu zabezpečení) nebo 32bitové procesy (pro lepší kompatibilita s) při spuštění v rozšířeným chráněným režimem v 64bitových verzích Windows. Důležité: Některé ovládací prvky ActiveX a panelů nástrojů nemusí být k dispozici, pokud jsou použity 64bitové procesy. Pokud nastavení této zásady povolíte, bude aplikace Internet Explorer 11 používat procesy karty 64-bit při spuštění v rozšířeným chráněným režimem na 64bitovými verzemi Windows. Pokud nastavení této zásady zakážete, bude aplikace Internet Explorer 11 používat procesy karty 32-bit při spuštění v rozšířeným chráněným režimem na 64bitovými verzemi Windows. Pokud nastavení této zásady nenakonfigurujete, uživatelé tuto funkci můžete zapnout nebo vypnout pomocí nastavení aplikace Internet Explorer. Tato funkce je ve výchozím nastavení vypnuté.
  - **Výchozí**: Povoleno 
  
- **Aplikace Internet Explorer ignorovat chyby certifikátů**  </br>
  Nastavení této zásady zabrání uživateli možnost Ignorovat chyby certifikátů Secure Sockets Layer/Transport Layer Security (SSL/TLS), které přerušení procházení (jako "prošlé", "zrušeno" nebo "došlo k neshodě názvů" chyby) v aplikaci Internet Explorer. Pokud nastavení této zásady povolíte, uživatel nemůže pokračovat v procházení. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, uživatel můžete rozhodnout ignorovat chyby certifikátů a pokračovat v procházení.
  - **Výchozí**: Zakázáno 
  
- **Načítání zóny Internetu aplikace Internet Explorer souborů XAML**  
  Toto nastavení zásad umožňuje spravovat načítání souborů Extensible Application Markup Language (XAML). XAML je založený na formátu XML deklarativní značkovací jazyk běžně používají k vytváření pro uživatelská rozhraní bohatá a grafiku, které využívají výhod Windows Presentation Foundation. Pokud povolíte toto nastavení zásad a nastavte rozevírací seznam na povolit, jsou automaticky načteny soubory XAML v aplikaci Internet Explorer. Toto chování nelze změnit uživatele. Pokud nastavíte rozevíracího seznamu na řádku, bude uživatel vyzván k načítání souborů XAML. Pokud nastavení této zásady zakážete, soubory XAML nejsou načtené v Internet Exploreru. Toto chování nelze změnit uživatele. Pokud nastavení této zásady nenakonfigurujete, může se rozhodnout, jestli se má načíst soubory XAML v aplikaci Internet Explorer.
  - **Výchozí**: Zakázat 
  
- **Soubory ke stažení zóny Internetu aplikace Internet Explorer pro soubor automatické řádku.**  </br>
  Nastavení této zásady určuje, zda uživatelům se zobrazí výzva pro stahování souborů bez zahájená uživatelem. Bez ohledu na toto nastavení, uživatelé dostanou dialogová okna Stažení souboru pro uživatelem iniciované soubory ke stažení. Pokud toto nastavení povolíte, uživatelům se zobrazí dialogové okno Stažení souboru pro pokusy o automatické stahování. Pokud zakážete nebo nenakonfigurujete toto nastavení zablokuje stahování souborů, které nejsou uživatelem iniciované a uživatelům se zobrazí oznamovací pruh místo dialogu stažení souboru. Uživatelům můžete pak kliknout na oznamovací pruh umožňuje výzva ke stažení souboru.
  - **Výchozí**: Povoleno  
  
- **Upozornění zabezpečení aplikace Internet Explorer s omezením pomocí specifikátoru zóny pro potenciálně nebezpečná soubory**  
  Nastavení této zásady určuje, zda se zobrazí zpráva "Otevření souboru – upozornění zabezpečení", když se uživatel pokusí otevřít spustitelné soubory nebo další potenciálně nebezpečná soubory (z intranetu sdílenou složku s použitím Průzkumníka souborů, například). Pokud povolíte toto nastavení zásad a nastavte rozevírací seznam na povolit, otevřete tyto soubory bez upozornění zabezpečení. Pokud nastavíte rozevíracího seznamu na příkazový řádek, zobrazí upozornění zabezpečení před otevřete soubory. Pokud nastavení této zásady zakážete, tyto soubory neotevírejte. Pokud nastavení této zásady nenakonfigurujete, může uživatel nakonfigurovat způsob, jakým zpracovává tyto soubory do počítače. Ve výchozím nastavení jsou tyto soubory blokované v zóně s omezeným přístupem, povolené v zóně intranetu a místního počítače a nastavit na výzvu v zóně Internet a důvěryhodné.
  - **Výchozí**: Zakázat  
  
- **Zóny Internetu aplikace Internet Explorer křížový filtr skriptování**  
  Tato zásada určuje, zda se filtr skriptování mezi weby (XSS) odhalování a prevenci injektáže skriptu webů do webů v této zóně. Pokud nastavení této zásady povolíte, je zapnutá filtr skriptování mezi weby pro servery v této zóně a filtr XSS, pokusí se zablokovat injektáže skriptu webů. Pokud nastavení této zásady zakážete, XSS filtru je vypnuté pro servery v této zóně a Internet Explorer povoluje injektáže skriptu webů.
  - **Výchozí**: Povoleno 
  
- **Aplikace Internet Explorer nouzového řešení ověření pomocí SSL3**  
  Nastavení této zásady umožňuje blokovat nezabezpečeného použití náhradní lokality pro protokol SSL 3.0. Když se povolí tyto zásady, aplikace Internet Explorer se pokusí připojit k webům pomocí protokolu SSL 3.0 nebo pod TLS 1.0 nebo vyšší v případě selhání. Doporučujeme, abyste neumožňují nezabezpečené záložní prevence útok man-in-the-middle. Tato zásada nemá vliv, které bezpečnostní protokoly jsou povolené. Pokud tuto zásadu zakážete, použije se výchozí systémové nastavení.
  - **Výchozí**: Žádné weby 
  
- **Uzamčené obrazovky inteligentní zóny Internetu aplikace Internet Explorer**  
  Tato zásada, nastavení ovládacích prvků, zda filtr SmartScreen vyhledá stránky v této zóně na škodlivý obsah. Pokud nastavení této zásady povolíte, filtr SmartScreen prohledává stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady zakážete, filtr SmartScreen neprovádí kontrolu stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, jestli kontrolovat filtru SmartScreen stránkách v této zóně na škodlivý obsah. Poznámka: V aplikaci Internet Explorer 7 nastavení této zásady určuje, zda filtr útoků Phishing kontrolovat stránkách v této zóně na škodlivý obsah.
  - **Výchozí**: Povoleno 
  
- **Aplikace Internet Explorer s omezením pomocí specifikátoru zóny spuštění aplikace a soubory v elementu iFrame**  
  Nastavení této zásady umožňuje určit, zda aplikace mohou být spuštěny a soubory stáhnout z odkazu na element IFRAME ve formátu HTML stránek v této zóně. Pokud nastavení této zásady povolíte, uživatelé můžou spouštět aplikace a stahovat soubory z prvky IFRAME na stránkách v této zóně bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat zvolit, jestli se má spouštět aplikace a stahovat soubory z prvky IFRAME na stránkách v této zóně. Pokud nastavení této zásady zakážete, uživatelé nebudou moci spouštění aplikací a stahování souborů z prvky IFRAME na stránkách v této zóně. Pokud nastavení této zásady nenakonfigurujete, budou uživatelé moct spouštění aplikací a stahování souborů z prvky IFRAME na stránkách v této zóně.
  - **Výchozí**: Zakázat 
  
- **Aplikace Internet Explorer obejít upozornění SmartScreen běžné soubory** nastavení této zásady určuje, jestli uživatel může obejít upozornění filtru SmartScreen. Filtr SmartScreen uživatele upozorní na spustitelné soubory, které uživatele aplikace Internet Explorer nestahovat běžně z Internetu. Pokud nastavení této zásady povolíte, uživateli blokovat upozornění filtru SmartScreen. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, můžete uživateli obejít upozornění filtru SmartScreen.
  - **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer Internetová zóna blokování automaticky otevíraných oken**  
  Nastavení této zásady umožňuje určit, zda nežádoucí automaticky otevíraných oken. Automaticky otevíraná okna, které jsou otevřeny, když koncový uživatel klepne na odkaz nejsou blokované. Pokud nastavení této zásady povolíte, většina nežádoucích automaticky otevíraná okna bránit v zobrazení. Pokud nastavení této zásady zakážete, ji povolí automaticky otevíraná okna. Pokud nastavení této zásady nenakonfigurujete, většina nežádoucích automaticky otevíraná okna bránit v zobrazení.
  - **Výchozí**: Povolení  
  
- **Aplikace Internet Explorer zpracovává konzistentní zpracování MIME**  
  Aplikace Internet Explorer obsahuje dynamické binární chování: komponenty, které zapouzdřují funkce specifická pro elementy HTML, ke kterým jsou připojené. Tato zásada, nastavení ovládacích prvků, jestli je nastavení binární omezení zabezpečení chování zabránit nebo povolené. Pokud povolíte toto nastavení zásad, nebudou další binární chování pro procesy Průzkumníka souborů a prohlížeče Internet Explorer. Pokud nastavení této zásady zakážete, binární chování jsou povoleny pro procesy Průzkumníka souborů a prohlížeče Internet Explorer. Pokud nastavení této zásady nenakonfigurujete, nebudou další binární chování pro procesy Průzkumníka souborů a prohlížeče Internet Explorer.
  - **Výchozí**: Povoleno  
  
- **Aplikace Internet Explorer omezená oprávnění java zóny** toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, aplety jsou zakázané.
  - **Výchozí**: Zakázat java  
    
  
- **Internet Explorer ovládací prvky ActiveX v chráněném režimu**  
  Nastavení této zásady zabrání ve spuštění v chráněném režimu při zapnutém rozšířeným chráněným režimem ovládací prvky ActiveX. Pokud má uživatel nainstalovat ovládací prvek ActiveX, který není kompatibilní s rozšířeným chráněným režimem a web, pokusí se načíst ovládací prvek, Internet Explorer upozorní uživatele a nabízí možnost spustit na web v pravidelných chráněný režim. Nastavení této zásady zakážete toto oznámení a vynutí všechny weby pro spuštění v rozšířeným chráněným režimem. Rozšířený chráněný režim nabízí další ochranu před škodlivým webům pomocí 64bitové procesy v 64bitových verzích Windows. Pro počítače se systémem nejméně Windows 8, rozšířeným chráněným režimem omezení, které aplikace Internet Explorer můžete číst z umístění v registru a systému souborů. Pokud je zapnuto rozšířeným chráněným režimem a uživatel zaznamená web, který se pokusí načíst ovládací prvek ActiveX, který není kompatibilní s rozšířeným chráněným režimem, Internet Explorer upozorní uživatele a poskytuje možnost zakázat rozšířeným chráněným režimem pro daný konkrétní web. Pokud nastavení této zásady povolíte, nebude se aplikace Internet Explorer dát uživateli možnost zakázat rozšířeným chráněným režimem. Všechny weby chráněný režim poběží v rozšířeným chráněným režimem. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, Internet Explorer upozorní uživatele a nabízí možnost spustit webů s nekompatibilní ovládacích prvků ActiveX v pravidelných chráněný režim. Toto je výchozí chování.
  - **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer zakázané zóny načítání souborů XAML**  
  Toto nastavení zásad umožňuje spravovat načítání souborů Extensible Application Markup Language (XAML). XAML je založený na formátu XML deklarativní značkovací jazyk běžně používají k vytváření pro uživatelská rozhraní bohatá a grafiku, které využívají výhod Windows Presentation Foundation. Pokud povolíte toto nastavení zásad a nastavte rozevírací seznam na povolit, jsou automaticky načteny soubory XAML v aplikaci Internet Explorer. Toto chování nelze změnit uživatele. Pokud nastavíte rozevíracího seznamu na řádku, bude uživatel vyzván k načítání souborů XAML. Pokud nastavení této zásady zakážete, soubory XAML nejsou načtené v Internet Exploreru. Toto chování nelze změnit uživatele. Pokud nastavení této zásady nenakonfigurujete, může se rozhodnout, jestli se má načíst soubory XAML v aplikaci Internet Explorer.
  - **Výchozí**: Zakázat  
  
- **Zpracovává skriptované okno omezení zabezpečení aplikace Internet Explorer**  
  Aplikace Internet Explorer umožňuje skripty prostřednictvím kódu programu otevřete, změny velikosti a přemístění windows podle různých typů. Funkce zabezpečení okno omezení omezuje zobrazována místní okna a zakazuje skripty zobrazování windows ve kterých pruhy názvu a stavu nejsou viditelné pro uživatele nebo obfuskaci jiných Windows nadpis a stavové řádky. Pokud nastavení této zásady povolíte, jsou skriptované windows s omezeným přístupem pro všechny procesy. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, nejsou oken s omezeným přístupem.
  - **Výchozí**: Povoleno   
  
- **Zakázané zóny Internet Explorer spustit ovládací prvky ActiveX a moduly plug-in**  
  Nastavení této zásady umožňuje určit, zda ovládací prvky ActiveX a moduly plug-in může běžet na stránkách z určené zóny. Pokud nastavení této zásady povolíte, můžete spustit ovládací prvky a moduly plug-in bez zásahu uživatele. Pokud jste vybrali v rozevíracím seznamu řádku, jsou uživatelé zvolit, jestli chce použít ovládací prvky ke správě nebo modulu plug-in pro spuštění. Pokud nastavení této zásady zakážete, ovládací prvky a moduly plug-in bránit spouštění. Pokud nastavení této zásady nenakonfigurujete, ovládací prvky a moduly plug-in nebudou spouštění.
  - **Výchozí**: Zakázat  
  
- **Skript zóny Internet Exploreru s omezením pomocí specifikátoru, ovládací prvky ActiveX označeny jako bezpečné pro skriptování**  
  Nastavení této zásady umožňuje určit, zda ovládací prvek ActiveX označeny jako bezpečné pro skriptování, můžete pracovat pomocí skriptu. Pokud nastavení této zásady povolíte, skript interakce může dojít automaticky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat zvolit, jestli chcete povolit interakci skriptu. Pokud nastavení této zásady zakážete, nebude interakce skriptu ke kterým dochází. Pokud nastavení této zásady nenakonfigurujete, skript interakce je zabráněno ke kterým dochází.
  - **Výchozí**: Zakázat  
  
- **Možnosti přihlášení zóny Internet Exploreru s omezením pomocí specifikátoru**  
  Toto nastavení zásad umožňuje spravovat nastavení pro možnosti přihlášení. Pokud nastavení této zásady povolíte, můžete z těchto možností přihlášení. Anonymní přihlášení k zakázání ověřování pomocí protokolu HTTP a používat účet guest jenom pro protokol Common Internet File System (CIFS). Vyzve k zadání uživatelského jména a hesla pro uživatele dotazu pro ID uživatele a hesla. Jakmile je uživatel vyzván, tyto hodnoty je možné tiše zbytek relace. Automatické přihlášení pouze do zóny sítě Intranet uživatelům dotazu pro ID uživatele a hesla v jiné zóně. Jakmile je uživatel vyzván, tyto hodnoty je možné tiše zbytek relace. Automatické přihlašování se aktuální uživatelské jméno a heslo pokusu o přihlášení pomocí odpověď výzvy systému Windows NT (označované také jako ověřování protokolem NTLM). Pokud je podporovaná odpověď výzvy systému Windows NT na serveru, používá přihlášení uživatele síťové uživatelské jméno a heslo pro přihlášení. Pokud server není podporována odpověď výzvy systému Windows NT, uživatel vyzván k zadání uživatelského jména a hesla. Pokud nastavení této zásady zakážete, přihlášení nastavená na automatické přihlášení pouze do zóny sítě Intranet. Pokud nastavení této zásady nenakonfigurujete, přihlášení nastavená na příkazový řádek pro uživatelské jméno a heslo.
  - **Výchozí**: Anonymní  
  
- **Důvěryhodné zóny inicializovat a skript, který ovládací prvky ActiveX neoznačené jako bezpečné aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat ovládací prvky ActiveX neoznačené jako bezpečné. Pokud nastavení této zásady povolíte, ovládací prvky ActiveX jsou spuštění načíst s parametry a skriptované bez nastavení zabezpečení objektů pro nedůvěryhodná data nebo skripty. Toto nastavení se nedoporučuje, s výjimkou zabezpečený a spravovaný zóny. Toto nastavení způsobí, že nebezpečné a bezpečné ovládací prvky k inicializaci a skripty, ignoruje ovládací prvky skriptu ActiveX označeny jako bezpečné pro skriptování – možnost. Pokud povolíte toto nastavení zásad a v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli chce použít ovládací prvek, který má být načten s parametry nebo skripty. Pokud nastavení této zásady zakážete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načtena s parametry nebo skripty. Pokud nastavení této zásady nenakonfigurujete, jsou uživatelé dotazovat, jestli chce použít ovládací prvek, který má být načten s parametry nebo skripty.
  - **Výchozí**: Zakázat  
  
- **Odvolání certifikátů serveru zkontrolujte aplikaci Internet Explorer**  
  Nastavení této zásady umožňuje určit, zda aplikace Internet Explorer se zkontrolovat stav odvolání certifikátů serverů. Certifikáty byly odvolány, když mohlo dojít k ohrožení nebo už nejsou platné, a tato možnost chrání uživatelé před odesláním důvěrná data do lokality, který může být podvodné nebo nezabezpečenou. Pokud nastavení této zásady povolíte, Internet Explorer zkontroluje, pokud byl odvolán certifikát serveru. Pokud nastavení této zásady zakážete, nebude aplikace Internet Explorer zkontrolovat certifikáty serveru, pokud chcete zobrazit, pokud byl odvolán. Pokud nastavení této zásady nenakonfigurujete, nebudou aplikace Internet Explorer zkontrolovat certifikáty serveru, pokud chcete zobrazit, pokud byl odvolán.
  - **Výchozí**: Povoleno 
  
- **Zóna Internetu aplikace Internet Explorer menší privilegované webů**  
  Nastavení této zásady umožňuje určit, zda webové stránky z méně privilegovaným zóny, jako jsou servery s omezeným přístupem, se můžete dostat do této zóny. Pokud nastavení této zásady povolíte, webové servery ze zóny méně privilegovaným můžete otevřít v nových oknech, nebo přejít do této zóny. Zóna zabezpečení se spustí bez další úroveň zabezpečení, které poskytuje ochranu před funkci zabezpečení ke zvýšení úrovně oprávnění zóny. Pokud v rozevíracím seznamu vyberte řádek, objeví se upozornění pro uživatele, které potenciálně nebezpečné navigace se použije. Pokud nastavení této zásady zakážete, nebudou další potenciálně škodlivé navigaci. Funkce zabezpečení aplikace Internet Explorer, bude na v této zóně úmluvu ochranu ze zóny zvýšení funkce správy. Pokud nastavení této zásady nenakonfigurujete, webové servery ze zóny méně privilegovaným můžete otevřít v nových oknech, nebo přejít do této zóny.
  - **Výchozí**: Zakázat  

- **Soubory ke stažení souboru s omezeným přístupem zóny Internet Exploreru**  </br>
  Nastavení této zásady umožňuje určit, zda jsou povolena stahování souborů ze zóny. Tato možnost se určuje podle zóny stránky pomocí odkazu, způsobí stažení nejsou zónově, ze kterého se doručí souboru. Pokud nastavení této zásady povolíte, soubory můžete stáhnout ze zóny. Pokud nastavení této zásady zakážete, soubory nebudou stahují ze zóny. Pokud nastavení této zásady nenakonfigurujete, nebudou soubory stahují ze zóny.
  - **Výchozí**: Zakázat  
  
- **Zóny Internetu aplikace Internet Explorer spustit s podpisem Authenticode spolehlivé součásti .NET Framework**  
  Nastavení této zásady umožňuje určit, zda mohou být spuštěny součásti rozhraní .NET Framework, které jsou podepsané pomocí technologie Authenticode aplikace Internet Explorer. Mezi tyto komponenty patří spravované ovládací prvky, které odkazuje objektu značku a spravované spustitelné soubory, které na něj odkazovat z odkazu. Pokud nastavení této zásady povolíte, spustí aplikaci Internet Explorer podepsaný spravované součásti. Pokud v rozevíracím seznamu vyberte řádek, Internet Explorer vyzve uživatele k určení, jestli se má spouštět podepsané spravované součásti. Pokud nastavení této zásady zakážete, aplikace Internet Explorer nespustí, podepsaný spravované součásti. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer nespustí, podepsaný spravované součásti.
  - **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer zabránit za instalaci uživatelské ovládací prvky ActiveX**  </br>
  Nastavení této zásady umožňuje zabránit v instalaci ovládací prvky ActiveX pro jednotlivé uživatele zvlášť. Pokud nastavení této zásady povolíte, ovládací prvky ActiveX nelze nainstalovat na jednotlivé uživatele. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, ovládací prvky ActiveX lze nainstalovat na jednotlivé uživatele.
  - **Výchozí**: Povoleno  
  
- **Aplikace Internet Explorer zabránit správě filtru SmartScreen**  </br>
  Nastavení této zásady zabrání uživateli ve správě filtru SmartScreen, který upozorní uživatele, pokud je známá podvodné pokusy o shromáždění osobních informací prostřednictvím "phishing" webu jsou zobrazeny, nebo je znám hostiteli malware. Pokud nastavení této zásady povolíte, uživatel není vyzván k zapnutí filtru SmartScreen. Všechny webové adresy, které nejsou na filtru povolit seznamu jsou automaticky odesílány společnosti Microsoft bez výzvy pro uživatele. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, bude uživatel vyzván k rozhodování, jestli se má zapnutí filtru SmartScreen během prvního spuštění.
  - **Výchozí**: Povolení  
  
- **Aplikace Internet Explorer zpracovává MIME analýzy rozšíření bezpečnostní funkce**  
  Nastavení této zásady určuje, zda pro analýzu sítě Internet Explorer MIME zabrání povýšení soubor jednoho typu k více nebezpečné typ souboru. Pokud nastavení této zásady povolíte, MIME pro analýzu sítě nikdy povýšit soubor jednoho typu na více nebezpečné typ souboru. Pokud nastavení této zásady zakážete, aplikace Internet Explorer procesů vám umožní MIME monitorování podpora souboru jednoho typu na více nebezpečné typ souboru. Pokud nastavení této zásady nenakonfigurujete, MIME pro analýzu sítě nikdy povýšit soubor jednoho typu na více nebezpečné typ souboru.
  - **Výchozí**: Povoleno  
  
- **Stažení aplikace Internet Explorer zakázané zóny podepsané ovládací prvky ActiveX**  </br>
  Nastavení této zásady umožňuje určit, zda uživatelé mohou stáhnout podepsané ovládací prvky ActiveX ze stránky v zóně. Pokud tuto zásadu povolíte, uživatelé můžou Stahovat podepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli se má stáhnout ovládací prvky, které jsou podepsány vydavatelé, kteří nejsou důvěryhodné. Bezobslužná stažením kódu podepsány Důvěryhodní vydavatelé. Pokud nastavení zásad zakážete, podepsané ovládací prvky nelze stáhnout. Pokud nastavení této zásady nenakonfigurujete, uživateli se generuje dotaz na, jestli se má stáhnout ovládací prvky, které jsou podepsány vydavatelé, kteří nejsou důvěryhodné. Bezobslužná stažením kódu podepsány Důvěryhodní vydavatelé.
  - **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer automatické dokončování**  </br>
  Tato funkce automatického dokončování můžete mějte na paměti a navrhují uživatelských jmen a hesel ve formulářích. Pokud povolíte toto nastavení, uživatel nemůže změnit "uživatelského jména a hesla na formulářích" nebo "výzvy k uložení hesla". Automatické dokončování funkce pro uživatelská jména a hesla ve formulářích bude zapnutá. Musíte se rozhodnout, jestli se má vybrat "výzvy k uložení hesla". Pokud toto nastavení zakážete uživatel nemůže změnit "uživatelského jména a hesla na formulářích" nebo "výzvy k uložení hesla". Funkci Automatické dokončování pro uživatelská jména a hesla na formulářích je vypnutý. Uživatel také nelze rozhodnout vyzváni k uložení hesla. Pokud toto nastavení nenakonfigurujete, má uživatel svobody zapnutí automatického dokončení zadání uživatelského jména a hesla ve formulářích a možnost zobrazení výzvy k uložení hesla. Pokud chcete zobrazit tuto možnost, uživatelé otevřít dialogové okno Možnosti Internetu, klikněte na kartu obsah a klikněte na tlačítko nastavení.
  - **Výchozí**: Zakázat  
  
- **Povolit zóny Internetu aplikace Internet Explorer VBscript ke spuštění**  </br>
  Nastavení této zásady umožňuje určit, zda VBScript, můžete spustit na stránkách v určité zóny Internet Exploreru. Pokud povolíte toto nastavení zásad (výchozí), musíte také vybrat jednu z následujících možností v rozevíracím seznamu možnosti: Povolte. Spustí jazyk VBScript na stránkách v konkrétních oblastech, bez nutnosti zásahu. Výzvu. Zaměstnanci zobrazí výzva, jestli se má povolit VBScript ke spuštění v zóně. Zakážete. VBScript je zabráněno ve spuštění v zóně. Pokud zakážete nebo není pro toto nastavení zásad, bez nutnosti zásahu v určené zóně spouští VBScript
  - **Výchozí**: Zakázat  
  
- **Povolit zakázané zóny Internet Exploreru schválí jen tehdy, domény určený ORS ovládací prvky ActiveX**  </br>
  Toto nastavení zásady řídí, jestli uživatel smí spouštět ovládací prvek ActiveX ORS na webech. Pokud nastavení této zásady povolíte, ovládací prvek ActiveX ORS nespustí z webů v této zóně. Pokud nastavení této zásady zakážete, ovládací prvek ActiveX ORS se spustí ze všech lokalit v této zóně.
  - **Výchozí**: Povoleno  
  
- **Zóny důvěryhodných serverů Internet Exploreru nespouštějte antimalwarové proti ovládací prvky ActiveX**   </br>
  Nastavení této zásady určuje, jestli aplikace Internet Explorer se spouští antimalwarové programy proti ovládací prvky ActiveX, a zkontrolujte, zda jsou bezpečné pro načtení na stránkách. Pokud nastavení této zásady povolíte, nebude Internet Exploreru zkontrolujte s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Uživatele můžete vypnout toto chování zapnout nebo vypnout pomocí nastavení zabezpečení aplikace Internet Explorer.
  - **Výchozí**: Zakázáno 
  
- **Oprávnění aplikace Internet Explorer místního počítače zóny java**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, je oprávnění nastaveno na střední bezpečnosti.
  - **Výchozí**: Zakázat java 
  
- **Zóny intranetu aplikace Internet Explorer nespustí antimalwarové proti ovládací prvky ActiveX**  </br>
  Nastavení této zásady určuje, jestli aplikace Internet Explorer se spouští antimalwarové programy proti ovládací prvky ActiveX, a zkontrolujte, zda jsou bezpečné pro načtení na stránkách. Pokud nastavení této zásady povolíte, nebude Internet Exploreru zkontrolujte s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, nebudou Internet Exploreru zkontrolujte s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Uživatele můžete vypnout toto chování zapnout nebo vypnout pomocí nastavení zabezpečení aplikace Internet Explorer.
  - **Výchozí**: Zakázáno  

- **Internet Explorer s omezením pomocí specifikátoru skriptlety zóny**  
  Nastavení této zásady umožňuje určit, zda uživatel může spustit skriptlety. Pokud nastavení této zásady povolíte, uživatel může spustit skriptlety. Pokud nastavení této zásady zakážete, uživatel nemůže spustit skriptlety. Pokud nastavení této zásady nenakonfigurujete, uživateli můžete povolit nebo zakázat skriptlety.
  - **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer procesy oznamovací pruh**  </br>  
  Nastavení této zásady umožňuje určit, zda oznamovací pruh se zobrazí pro procesy aplikace Internet Explorer, když se nainstaluje soubor nebo kód s omezeným přístupem. Ve výchozím nastavení zobrazí se oznamovací pruh pro procesy aplikace Internet Explorer. Pokud nastavení této zásady povolíte, zobrazí se oznamovací pruh pro Internet Explorer procesy. Pokud nastavení této zásady zakážete, oznamovací pruh se nezobrazí pro procesy aplikace Internet Explorer. Pokud nastavení této zásady nenakonfigurujete, zobrazí se oznamovací pruh pro Internet Explorer procesy.
  - **Výchozí**: Povoleno  
  
- **Stažení zóny Internetu aplikace Internet Explorer podepsané ovládací prvky ActiveX**  </br>
  Nastavení této zásady umožňuje určit, zda uživatelé mohou stáhnout podepsané ovládací prvky ActiveX ze stránky v zóně. Pokud tuto zásadu povolíte, uživatelé můžou Stahovat podepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli se má stáhnout ovládací prvky, které jsou podepsány vydavatelé, kteří nejsou důvěryhodné. Bezobslužná stažením kódu podepsány Důvěryhodní vydavatelé. Pokud nastavení zásad zakážete, podepsané ovládací prvky nelze stáhnout. Pokud nastavení této zásady nenakonfigurujete, uživateli se generuje dotaz na, jestli se má stáhnout ovládací prvky, které jsou podepsány vydavatelé, kteří nejsou důvěryhodné. Bezobslužná stažením kódu podepsány Důvěryhodní vydavatelé.
  - **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer zakázané zóny SmartScreen**  
  Tato zásada, nastavení ovládacích prvků, zda filtr SmartScreen vyhledá stránky v této zóně na škodlivý obsah. Pokud nastavení této zásady povolíte, filtr SmartScreen prohledává stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady zakážete, filtr SmartScreen neprovádí kontrolu stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, jestli kontrolovat filtru SmartScreen stránkách v této zóně na škodlivý obsah. Poznámka: V aplikaci Internet Explorer 7 nastavení této zásady určuje, zda filtr útoků Phishing kontrolovat stránkách v této zóně na škodlivý obsah.
  - **Výchozí**: Povoleno  
  
- **Odebrat aplikaci Internet Explorer spustili toto tlačítko čas pro zastaralé ovládací prvky ActiveX**  </br>
  Nastavení této zásady umožňuje zabránit uživatelům v zobrazení na tlačítko "Spustit nyní" a ve spuštění konkrétních zastaralé ovládacích prvků ActiveX v Internet Exploreru. Pokud nastavení této zásady povolíte, uživatelé nebudou "Spustit nyní" na tlačítko Zobrazit upozornění, které se zobrazí, když aplikace Internet Explorer zablokuje zastaralé ovládacího prvku ActiveX. Pokud zakážete nebo není pro toto nastavení zásady, uživatelům se zobrazí tlačítko "Spustit nyní" na upozornění, které se zobrazí, když aplikace Internet Explorer zablokuje zastaralé ovládacího prvku ActiveX. Kliknutím na toto tlačítko umožňuje uživateli spustit jednou zastaralé ovládacího prvku ActiveX. Další informace najdete v tématu "Zastaralé ovládací prvky ActiveX" v knihovně Internet Explorer TechNet.
  - **Výchozí**: Povoleno 
  
- **Spuštění aplikace Internet Explorer zóny a soubory v elementu iframe**  
  Nastavení této zásady umožňuje určit, zda aplikace mohou být spuštěny a soubory stáhnout z odkazu na element IFRAME ve formátu HTML stránek v této zóně. Pokud nastavení této zásady povolíte, uživatelé můžou spouštět aplikace a stahovat soubory z prvky IFRAME na stránkách v této zóně bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat zvolit, jestli se má spouštět aplikace a stahovat soubory z prvky IFRAME na stránkách v této zóně. Pokud nastavení této zásady zakážete, uživatelé nebudou moci spouštění aplikací a stahování souborů z prvky IFRAME na stránkách v této zóně. Pokud nastavení této zásady nenakonfigurujete, jsou uživatelé dotazovat zvolit, jestli se má spouštět aplikace a stahovat soubory z prvky IFRAME na stránkách v této zóně
  - **Výchozí**: Zakázat 
  
- **Zóny s omezeným přístupem v Internet Exploreru přejděte v různých doménách windows a snímků**  </br>
  Nastavení této zásady umožňuje nastavit možnosti pro přetažení obsah z jedné domény do jiné domény, pokud zdroj a cíl nacházejí v různých systému windows. Pokud povolíte toto nastavení zásad a klikněte na možnost povolit, uživatelé můžete přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl nacházejí v různých systému windows. Uživatelé nemohou změnit toto nastavení. Pokud povolíte toto nastavení zásad a klikněte na možnost zakázat, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl v různých systému windows. Uživatelé nemohou změnit toto nastavení. V Internet Exploreru 10 je-li toto nastavení zásad zakážete nebo nenakonfigurujete, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí v různých systému windows. Uživatelé mohou změnit toto nastavení v dialogovém okně Možnosti Internetu. V aplikaci Internet Explorer 9 a dřívějších verzích Pokud tuto zásadu zakážete nebo nenakonfigurujete, uživatelé přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí v různých systému windows. Uživatelé nemohou změnit toto nastavení.
  - **Výchozí**: Zakázat  
  
- **Inteligentní obrazovce zóny Internetu aplikace Internet Explorer**  
  Tato zásada, nastavení ovládacích prvků, zda filtr SmartScreen vyhledá stránky v této zóně na škodlivý obsah. Pokud nastavení této zásady povolíte, filtr SmartScreen prohledává stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady zakážete, filtr SmartScreen neprovádí kontrolu stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, jestli kontrolovat filtru SmartScreen stránkách v této zóně na škodlivý obsah. Poznámka: V aplikaci Internet Explorer 7 nastavení této zásady určuje, zda filtr útoků Phishing kontrolovat stránkách v této zóně na škodlivý obsah.
  - **Výchozí**: Povoleno  
  
- **Uzamčené oprávnění pro jazyk java zóny důvěryhodných serverů Internet Exploreru**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, aplety jsou zakázané.
  - **Výchozí**: Zakázat java 
  
- **Aplikace Internet Explorer zkontrolovat podpisy stažených programů**  
  Nastavení této zásady umožňuje určit, zda aplikace Internet Explorer zkontroluje digitální podpisy (který určuje vydavatele softwaru podepsané barvy a ověřuje nebyl byl změněn nebo úmyslně) v počítačích uživatelů před stažením spustitelné programy. Pokud nastavení této zásady povolíte, Internet Explorer zkontroluje digitální podpisy spustitelné programy a zobrazí jejich identity před stažením do počítačů uživatelů. Pokud nastavení této zásady zakážete, nebude aplikace Internet Explorer zkontrolujte digitální podpisy spustitelné programy nebo zobrazení jejich identity před stažením do počítačů uživatelů. Pokud tuto zásadu nenakonfigurujete, nebudou aplikace Internet Explorer zkontrolujte digitální podpisy spustitelné programy nebo zobrazení jejich identity před stažením do počítačů uživatelů.
  - **Výchozí**: Povoleno  
  
- **Aplikace Internet Explorer s omezením pomocí specifikátoru skriptování v zóně ovládacích prvků webového prohlížeče**  
  Nastavení této zásady určuje, zda na stránku můžete řídit vložené WebBrowser – ovládací prvky pomocí skriptu. Pokud nastavení této zásady povolíte, je povolen skript přístup k ovládacímu prvku WebBrowser. Pokud nastavení této zásady zakážete, není povolen přístup skript do ovládacího prvku WebBrowser. Pokud nastavení této zásady nenakonfigurujete, uživateli můžete povolit nebo zakázat přístup skript do ovládacího prvku WebBrowser. Ve výchozím nastavení je povolen skript přístup k ovládacímu prvku WebBrowser pouze v místním počítači a zóny intranetu.
  - **Výchozí**: Zakázáno  
  
- **Zóny s omezeným přístupem v Internet Exploreru křížový filtr skriptování**  
  Tato zásada určuje, zda se filtr skriptování mezi weby (XSS) odhalování a prevenci injektáže skriptu webů do webů v této zóně. Pokud nastavení této zásady povolíte, je zapnutá filtr skriptování mezi weby pro servery v této zóně a filtr XSS, pokusí se zablokovat injektáže skriptu webů. Pokud nastavení této zásady zakážete, XSS filtru je vypnuté pro servery v této zóně a Internet Explorer povoluje injektáže skriptu webů.
  - **Výchozí**: Povoleno  
  
- **Binární s omezeným přístupem zóny Internet Exploreru a chování skriptu**  
  Toto nastavení zásad umožňuje spravovat chování dynamické binární soubor a skriptu: komponenty, které zapouzdřují funkce specifická pro elementy HTML, do kterých byla připojena. Pokud nastavení této zásady povolíte, chování binárních souborů a skriptů jsou k dispozici. Pokud jste vybrali v rozevíracím seznamu schválení správcem, jsou k dispozici pouze chování, které jsou uvedeny v chování schválení správce v části zásady omezení zabezpečení binární chování. Pokud nastavení této zásady zakážete, binární soubor a skript chování nejsou k dispozici, pokud implementovali vlastní zabezpečení Správce aplikací. Pokud nastavení této zásady nenakonfigurujete, binární soubor a skript chování nejsou k dispozici, pokud implementovali vlastní zabezpečení Správce aplikací.
  - **Výchozí**: Zakázat  
  
- **Kontrola nastavení zabezpečení aplikace Internet Explorer**  </br>
  Nastavení této zásady vypne funkce Kontrola nastavení zabezpečení, která zkontroluje nastavení zabezpečení aplikace Internet Explorer můžete určit, kdy nastavení ohrozit aplikace Internet Explorer. Pokud nastavení této zásady povolíte, tato funkce je vypnuta. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, tato funkce je zapnutá.
  - **Výchozí**: Povoleno  
  
- **Upozornění v Internet Exploreru zóny zabezpečení Internetu potenciálně nebezpečná souborů**  
  Nastavení této zásady určuje, zda se zobrazí zpráva "Otevření souboru – upozornění zabezpečení", když se uživatel pokusí otevřít spustitelné soubory nebo další potenciálně nebezpečná soubory (z intranetu sdílenou složku s použitím Průzkumníka souborů, například). Pokud povolíte toto nastavení zásad a nastavte rozevírací seznam na povolit, otevřete tyto soubory bez upozornění zabezpečení. Pokud nastavíte rozevíracího seznamu na příkazový řádek, zobrazí upozornění zabezpečení před otevřete soubory. Pokud nastavení této zásady zakážete, tyto soubory neotevírejte. Pokud nastavení této zásady nenakonfigurujete, může uživatel nakonfigurovat způsob, jakým zpracovává tyto soubory do počítače. Ve výchozím nastavení jsou tyto soubory blokované v zóně s omezeným přístupem, povolené v zóně intranetu a místního počítače a nastavit na výzvu v zóně Internet a důvěryhodné.
  - **Výchozí**: Výzva  
  
- **Oprávnění java zóny intranetu aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, je oprávnění nastaveno na střední bezpečnosti.
  - **Výchozí**: Vysoké zabezpečení 
  
- **Aplikace Internet Explorer blokovat zastaralé ovládací prvky ActiveX**  </br>
  Nastavení této zásady určuje, zda aplikace Internet Explorer bloky konkrétní zastaralé ovládací prvky ActiveX. Zastaralé ovládací prvky ActiveX jsou nikdy blokována v zóně intranetu. Pokud nastavení této zásady povolíte, přestane aplikace Internet Explorer blokovat zastaralé ovládací prvky ActiveX. Pokud zakážete nebo není pro toto nastavení zásad, pokračuje aplikace Internet Explorer blokovat konkrétní zastaralé ovládací prvky ActiveX. Další informace najdete v tématu "Zastaralé ovládací prvky ActiveX" v knihovně Internet Explorer TechNet.
  - **Výchozí**: Povoleno  
  
- **Aplikace Internet Explorer s omezením pomocí specifikátoru zóny blokování automaticky otevíraných oken**  
  Nastavení této zásady umožňuje určit, zda nežádoucí automaticky otevíraných oken. Automaticky otevíraná okna, které jsou otevřeny, když koncový uživatel klepne na odkaz nejsou blokované. Pokud nastavení této zásady povolíte, většina nežádoucích automaticky otevíraná okna bránit v zobrazení. Pokud nastavení této zásady zakážete, ji povolí automaticky otevíraná okna. Pokud nastavení této zásady nenakonfigurujete, většina nežádoucích automaticky otevíraná okna bránit v zobrazení.
  - **Výchozí**: Povolení  
  
- **Omezení pro protokol zabezpečení aplikace Internet Explorer procesy MK**  
  Nastavení zásad omezení zabezpečení protokolu MK snižuje zabráněním protokolu MK možností útoku. Prostředky, které jsou hostované na protokol MK se nezdaří. Pokud nastavení této zásady povolíte, MK protokol je zabráněno z Průzkumníka souborů a prohlížeče Internet Explorer a prostředky, které jsou hostované na protokol MK se nezdaří. Pokud nastavení této zásady zakážete, aplikace můžete použít protokol MK rozhraní API. Prostředky, které jsou hostované na protokol MK bude fungovat pro procesy Průzkumníka souborů a prohlížeče Internet Explorer. Pokud nastavení této zásady nenakonfigurujete, MK protokol je zabráněno z Průzkumníka souborů a prohlížeče Internet Explorer a prostředky, které jsou hostované na protokol MK se nezdaří.
  - **Výchozí**: Povoleno  
  
- **Oprávnění pro jazyk java aplikace Internet Explorer důvěryhodné zóny**  </br>
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, je oprávnění nastaveno nízká bezpečnosti.
  - **Výchozí**: Vysoké zabezpečení  
  
- **Aplikace Internet Explorer s omezením pomocí specifikátoru zóny skriptování aplety**  
  Nastavení této zásady umožňuje určit, zda jsou vystaveny aplety skripty v rámci zóny. Pokud nastavení této zásady povolíte, dostanete skripty aplety automaticky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, jsou zvolit, jestli se tak, aby pro přístup k aplety dotazovat uživatele. Pokud nastavení této zásady zakážete, nemají přístup k aplety skripty. Pokud nastavení této zásady nenakonfigurujete, nemají přístup k aplety skripty.
  - **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer uzamčen oprávnění pro jazyk java zakázané zóny**  </br>
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, aplety jsou zakázané.
  - **Výchozí**: Zakázat java 
  
- **Povolit zóny Internetu aplikace Internet Explorer schválí jen tehdy, domén používat ovládací prvky ActiveX**  </br>
  Toto nastavení zásady řídí, jestli je uživatel vyzván k povolit ovládacích prvků ActiveX ke spuštění ve službě websites než webu, nainstalované ovládacího prvku ActiveX. Pokud nastavení této zásady povolíte, bude uživatel vyzván, ovládací prvky ActiveX lze spustit z webů v této zóně. Uživatel může zvolit, aby ovládací prvek pro spuštění z aktuální lokality nebo ze všech lokalit. Pokud nastavení této zásady zakážete, uživatel neuvidí řádku ActiveX podle webu a ovládací prvky ActiveX lze spustit ze všech lokalit v této zóně.
  - **Výchozí**: Povoleno  
  
- **Aplikace Internet Explorer zahrnout všechny síťové cesty**  
  Aplikace Internet Explorer zahrnout všechny síťové cesty
  - **Výchozí**: Zakázáno 
  
- **Zóny Internetu aplikace Internet Explorer chráněný režim**  
  Nastavení této zásady umožňuje zapnout v chráněném režimu. Chráněný režim pomáhá chránit aplikace Internet Explorer z odstranění zneužité chyby zabezpečení snížením umístění, které aplikace Internet Explorer můžete zapsat do registru a systému souborů. Pokud nastavení této zásady povolíte, chráněný režim zapnutý. Uživatele nelze vypnout chráněný režim. Pokud nastavení této zásady zakážete, chráněný režim je vypnutý. Uživatele nelze zapnout chráněný režim. Pokud nastavení této zásady nenakonfigurujete, uživatel může zapnout nebo vypnout chráněný režim.
  - **Výchozí**: Povolení 
  
- **Inicializovat zóny Internetu aplikace Internet Explorer a skript, který ovládací prvky ActiveX neoznačené jako bezpečné**  
  Toto nastavení zásad umožňuje spravovat ovládací prvky ActiveX neoznačené jako bezpečné. Pokud nastavení této zásady povolíte, ovládací prvky ActiveX jsou spuštění načíst s parametry a skriptované bez nastavení zabezpečení objektů pro nedůvěryhodná data nebo skripty. Toto nastavení se nedoporučuje, s výjimkou zabezpečený a spravovaný zóny. Toto nastavení způsobí, že nebezpečné a bezpečné ovládací prvky k inicializaci a skripty, ignoruje ovládací prvky skriptu ActiveX označeny jako bezpečné pro skriptování – možnost. Pokud povolíte toto nastavení zásad a v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli chce použít ovládací prvek, který má být načten s parametry nebo skripty. Pokud nastavení této zásady zakážete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načtena s parametry nebo skripty. Pokud nastavení této zásady nenakonfigurujete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načteny s parametry nebo skripty.
  - **Výchozí**: Zakázat 
  
- **Aplikace Internet Explorer uzamčené obrazovky inteligentní zakázané zóny**  </br>
  Tato zásada, nastavení ovládacích prvků, zda filtr SmartScreen vyhledá stránky v této zóně na škodlivý obsah. Pokud nastavení této zásady povolíte, filtr SmartScreen prohledává stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady zakážete, filtr SmartScreen neprovádí kontrolu stránkách v této zóně na škodlivý obsah. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, jestli kontrolovat filtru SmartScreen stránkách v této zóně na škodlivý obsah. Poznámka: V aplikaci Internet Explorer 7 nastavení této zásady určuje, zda filtr útoků Phishing kontrolovat stránkách v této zóně na škodlivý obsah.
  - **Výchozí**: Povoleno  
  
- **Detekce chybového ukončení Internet Exploreru**  
  Toto nastavení zásad umožňuje spravovat funkce rozpoznávání chyb správy doplňku. Pokud nastavení této zásady povolíte, při selhání v aplikaci Internet Explorer se chovat nalezen ve Windows XP Professional Service Pack 1 a starší, konkrétně k vyvolání zasílání zpráv o chybách Windows. Všechna nastavení zásad pro zasílání zpráv o chybách Windows pokračovat v používání. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, bude tato funkce detekce chyb pro správu doplňku funkční.
  - **Výchozí**: Zakázáno  
  
- **Oprávnění java zóny Internetu aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, je oprávnění nastaveno na vysokou bezpečnost.
  - **Výchozí**: Zakázat java  
  
- **Aplikace Internet Explorer s omezením pomocí specifikátoru aktivní skriptování v zóně**  
  Nastavení této zásady umožňuje určit, zda je spuštěn kód skriptu na stránkách v zóně. Pokud nastavení této zásady povolíte, můžete automaticky spouštět kód skriptu na stránkách v zóně. Pokud v rozevíracím seznamu vyberte řádek, jsou dotazováním uživatelé vybrat, jestli povolíte kód skriptu na stránkách v zóně ke spuštění. Pokud zakážete toto nastavení zásad, kód skriptu na stránkách v zóně zabránily spuštění. Pokud nastavení této zásady nenakonfigurujete, je kód skriptu na stránkách v zóně zabránily spuštění.
  - **Výchozí**: Zakázat  
  
- **Možnosti přihlášení zóny Internetu aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat nastavení protokolu na možnosti. Pokud nastavení této zásady povolíte, můžete z protokolu následující možnosti. Anonymní Přihlaste se k zakázání ověřování pomocí protokolu HTTP a použijte účet hosta jenom pro protokol Common Internet File System (CIFS). Vyzve k zadání uživatelského jména a hesla pro uživatele dotazu pro ID uživatele a hesla. Jakmile je uživatel vyzván, tyto hodnoty je možné tiše zbytek relace. Automatické přihlášení pouze do zóny sítě Intranet uživatelům dotazu pro ID uživatele a hesla v jiné zóně. Jakmile je uživatel vyzván, tyto hodnoty je možné tiše zbytek relace. Automatické přihlášení s aktuální uživatelské jméno a heslo se pokusit přihlásit pomocí odpověď výzvy systému Windows NT (označované také jako ověřování protokolem NTLM). Pokud je podporovaná odpověď výzvy systému Windows NT na serveru, pro přihlášení používá síťové uživatelské jméno a heslo uživatele pro přihlášení. Pokud server není podporována odpověď výzvy systému Windows NT, uživatel vyzván k zadání uživatelského jména a hesla. Pokud nastavení této zásady zakážete, přihlášení nastavená na automatické protokolu na pouze do zóny sítě Intranet. Pokud nastavení této zásady nenakonfigurujete, přihlášení nastavená na automatické protokolu na pouze do zóny sítě Intranet.
  - **Výchozí**: Výzva  
  
- **Povolit jazyk vbscript ke spuštění s omezeným přístupem zóny Internet Exploreru**  </br>  
  Nastavení této zásady umožňuje určit, zda VBScript může běžet na stránkách z určené zóny v aplikaci Internet Explorer. Pokud jste vybrali v rozevíracím seznamu povolit, VBScript spustit bez zásahu uživatele. Pokud jste vybrali v rozevíracím seznamu řádku, jsou uživatelé vyzváni k vybrat, jestli povolíte VBScript ke spuštění. Pokud jste vybrali v rozevíracím seznamu zakázat, VBScript zabránily spuštění. Pokud nenakonfigurujete nebo zakážete nastavením této zásady, VBScript zabránily spuštění.
  - **Výchozí**: Zakázat  
  
- **Zóny Internetu aplikace Internet Explorer tažením obsah z jiných domén systému windows**  
  Nastavení této zásady umožňuje nastavit možnosti pro přetažení obsah z jedné domény do jiné domény, pokud zdroj a cíl nacházejí v různých systému windows. Pokud povolíte toto nastavení zásad a klikněte na možnost povolit, uživatelé můžete přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl nacházejí v různých systému windows. Uživatelé nemohou změnit toto nastavení. Pokud povolíte toto nastavení zásad a klikněte na možnost zakázat, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl v různých systému windows. Uživatelé nemohou změnit toto nastavení. V Internet Exploreru 10 je-li toto nastavení zásad zakážete nebo nenakonfigurujete, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí v různých systému windows. Uživatelé mohou změnit toto nastavení v dialogovém okně Možnosti Internetu. V aplikaci Internet Explorer 9 a dřívějších verzích Pokud tuto zásadu zakážete nebo nenakonfigurujete, uživatelé přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí v různých systému windows. Uživatelé nemohou změnit toto nastavení.
  - **Výchozí**: Zakázáno 
  
- **Inicializovat zóny intranetu aplikace Internet Explorer a skript, který ovládací prvky ActiveX neoznačené jako bezpečné**  
  Toto nastavení zásad umožňuje spravovat ovládací prvky ActiveX neoznačené jako bezpečné. Pokud nastavení této zásady povolíte, ovládací prvky ActiveX jsou spuštění načíst s parametry a skriptované bez nastavení zabezpečení objektů pro nedůvěryhodná data nebo skripty. Toto nastavení se nedoporučuje, s výjimkou zabezpečený a spravovaný zóny. Toto nastavení způsobí, že nebezpečné a bezpečné ovládací prvky k inicializaci a skripty, ignoruje ovládací prvky skriptu ActiveX označeny jako bezpečné pro skriptování – možnost. Pokud povolíte toto nastavení zásad a v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli chce použít ovládací prvek, který má být načten s parametry nebo skripty. Pokud nastavení této zásady zakážete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načtena s parametry nebo skripty. Pokud nastavení této zásady nenakonfigurujete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načteny s parametry nebo skripty.
  - **Výchozí**: Zakázat 
  
- **Aplikace Internet Explorer stahování příloh**  
  Toto nastavení zásad znemožní uživateli s skříně (soubory příloh) stažené z informačního kanálu na počítači uživatele. Pokud nastavení této zásady povolíte, uživateli nelze nastavit synchronizační modul informačního kanálu stáhnout přílohu prostřednictvím stránky vlastností informačního kanálu. Vývojář nelze změnit nastavení stahování přes rozhraní API informačního kanálu. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, může uživatel nastavit synchronizační modul informačního kanálu stáhnout přílohu prostřednictvím stránky vlastností informačního kanálu. Vývojář můžete změnit nastavení stahování přes rozhraní API informačního kanálu.
  - **Výchozí**: Zakázáno  
  
- **Zakázané zóny Internet Explorer stahování bez znaménka ovládací prvky ActiveX**  </br>
  Nastavení této zásady umožňuje určit, zda uživatelé mohou stáhnout nepodepsané ovládací prvky ActiveX ze zóny. Takový kód je potenciálně škodlivých, zejména v případě, že pocházejí z nedůvěryhodné zóny. Pokud povolíte toto nastavení zásad, můžou uživatelé spouštět nepodepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, uživatelé se dotazováním vyberte, jestli chcete povolit spuštění bez znaménka ovládacího prvku. Pokud nastavení této zásady zakážete, uživatelé nemůžou spouštět nepodepsané ovládací prvky. Pokud nastavení této zásady nenakonfigurujete, uživatelé nemůžou spouštět nepodepsané ovládací prvky.
  - **Výchozí**: Zakázat  
  
- **Zóny Internetu aplikace Internet Explorer přetáhnout obsah z jiných domén v rámci systému windows**  
  Nastavení této zásady umožňuje určit, zda uživatelé mohou stáhnout nepodepsané ovládací prvky ActiveX ze zóny. Takový kód je potenciálně škodlivých, zejména v případě, že pocházejí z nedůvěryhodné zóny. Pokud povolíte toto nastavení zásad, můžou uživatelé spouštět nepodepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, uživatelé se dotazováním vyberte, jestli chcete povolit spuštění bez znaménka ovládacího prvku. Pokud nastavení této zásady zakážete, uživatelé nemůžou spouštět nepodepsané ovládací prvky. Pokud nastavení této zásady nenakonfigurujete, uživatelé nemůžou spouštět nepodepsané ovládací prvky.
  - **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer procesy omezit Active X install**  </br>
  Nastavení této zásady umožňuje aplikacím hostujícím ovládací prvek webového prohlížeče k blokování Automatické dotazování instalace ovládacího prvku ActiveX. Pokud nastavení této zásady povolíte, bude ovládací prvek webového prohlížeče blokovat Automatické dotazování instalace ovládacího prvku ActiveX pro všechny procesy. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, ovládací prvek webového prohlížeče nebude blokovat Automatické dotazování instalace ovládacího prvku ActiveX pro všechny procesy.
  - **Výchozí**: Povoleno  
  
- **Skriptlety zóny Internetu aplikace Internet Explorer** nastavení této zásady umožňuje určit, zda uživatel může spustit skriptlety. Pokud nastavení této zásady povolíte, uživatel může spustit skriptlety. Pokud nastavení této zásady zakážete, uživatel nemůže spustit skriptlety. Pokud nastavení této zásady nenakonfigurujete, uživateli můžete povolit nebo zakázat skriptlety.
  - **Výchozí**: Zakázat  
  
- **Zóny s omezeným přístupem v Internet Exploreru přetahování nebo zkopírujte a vložte soubory**  
  Nastavení této zásady umožňuje určit, zda uživatele lze přetáhnout soubory nebo kopírování a vkládání souborů ze zdroje v rámci zóny. Pokud nastavení této zásady povolíte, uživatelé můžete přetáhnout soubory nebo zkopírovat a vkládat soubory z této zóny automaticky. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat rozhodnout, jestli jej přetáhnout nebo zkopírovat soubory z této zóny. Pokud nastavení této zásady zakážete, uživatelé nebudou moci soubory přetažením nebo zkopírováním a vložením soubory z této zóny. Pokud nastavení této zásady nenakonfigurujete, jsou uživatelé dotazovat rozhodnout, jestli jej přetáhnout nebo zkopírovat soubory z této zóny.
  - **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer softwaru při podpis je neplatný.** </br>
  Nastavení této zásady umožňuje určit, zda je software, jako je například ovládací prvky ActiveX a stahování souborů, můžete nainstalovat nebo spustit uživatel i v případě, že podpis je neplatný. Neplatný podpis může znamenat, že někdo nemanipuloval s souboru. Pokud nastavení této zásady povolíte, uživatelé budou vyzváni k nainstalovat nebo spustit soubory s neplatným podpisem. Pokud nastavení této zásady zakážete, uživatelé nemohou spustit nebo instalovat soubory s neplatným podpisem. Pokud tuto zásadu nenakonfigurujete, uživatelé mohou spustit nebo instalovat soubory s neplatným podpisem.
  - **Výchozí**: Zakázáno  
  
- **Internet Explorer s omezením pomocí specifikátoru zóny kopírování a vkládání přes skript** </br> Nastavení této zásady umožňuje určit, zda skripty můžete provést operaci schránky (například vyjmout, kopírovat a vložit) v určité oblasti. Pokud nastavení této zásady povolíte, skriptu můžete provést operaci schránky. Pokud v rozevíracím seznamu vyberte řádek, uživatelé se generuje dotaz na tom, jestli se má provést operace schránky. Pokud nastavení této zásady zakážete, skriptu nelze provést operaci schránky. Pokud nastavení této zásady nenakonfigurujete, skriptu nelze provést operaci schránky.
  - **Výchozí**: Zakázat  
  
- **Zóny s omezeným přístupem v Internet Exploreru proveďte operaci přetažení obsah z jiných domén přes windows**  
  Nastavení této zásady umožňuje nastavit možnosti pro přetažení obsah z jedné domény do jiné domény, pokud zdroj a cíl nacházejí v různých systému windows. Pokud povolíte toto nastavení zásad a klikněte na možnost povolit, uživatelé můžete přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl nacházejí v různých systému windows. Uživatelé nemohou změnit toto nastavení. Pokud povolíte toto nastavení zásad a klikněte na možnost zakázat, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény po zdroj a cíl v různých systému windows. Uživatelé nemohou změnit toto nastavení. V Internet Exploreru 10 je-li toto nastavení zásad zakážete nebo nenakonfigurujete, uživatelé nelze přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí v různých systému windows. Uživatelé mohou změnit toto nastavení v dialogovém okně Možnosti Internetu. V aplikaci Internet Explorer 9 a dřívějších verzích Pokud tuto zásadu zakážete nebo nenakonfigurujete, uživatelé přetáhnout obsah z jedné domény do jiné domény při zdroj a cíl nacházejí v různých systému windows. Uživatelé nemohou změnit toto nastavení.
  - **Výchozí**: Zakázáno  
  
- **Přidání serverů uživatele aplikace Internet Explorer**  
  Zabrání uživatelům přidávat nebo odebírat servery ze zóny zabezpečení. Zóny zabezpečení je skupina webových stránek se stejnou úrovní zabezpečení. Pokud tuto zásadu povolit, nastavení serveru správy pro zóny zabezpečení jsou zakázané. (Zobrazíte Správa lokality nastavení zóny zabezpečení, v dialogovém okně Možnosti Internetu klikněte na kartu zabezpečení a potom klikněte na tlačítko weby.) Pokud tuto zásadu zakážete nebo nenakonfigurujete, můžete uživatele přidat weby nebo odebrat servery ze zóny důvěryhodných serverů a serverů s omezeným přístupem, a upravit nastavení pro zóny místního intranetu. Tato zásada zabraňuje uživatelům možnost měnit nastavení řízení lokality pro zóny zabezpečení nastavená správcem. Poznámka: "Zakázat na stránce zabezpečení" zásady (umístěné v \User Configuration\Administrative pro správu\Součásti systému Windows\Internet Explorer\Ovládací ovládací panely), tím se odebere z rozhraní na kartě zabezpečení, mají přednost před tuto zásadu. Pokud je povolena, tato zásada je ignorována. Další informace naleznete "zóny zabezpečení: Použití pouze nastavení počítače"zásad.
  - **Výchozí**: Zakázáno  
  
- **Skript zóny Internetu aplikace Internet Explorer inicioval systému windows**  
  Toto nastavení zásad umožňuje spravovat omezení iniciované skriptu automaticky otevíraná okna a okna, která zahrnují panely názvu a stavu. Pokud nastavení této zásady povolíte, nebude v této zóně použít Windows omezení zabezpečení. Zóna zabezpečení se spustí bez další úroveň zabezpečení poskytované touto funkcí. Pokud nastavení této zásady zakážete, je to možné škodlivých akcí, které jsou součástí iniciované skriptu automaticky otevíraná okna a okna, která zahrnují panely názvu a stavu nelze spustit. Tuto funkci zabezpečení aplikace Internet Explorer bude na v této zóně určený nastavení pro proces řízení funkci skripty Windows bezpečnostní omezení. Pokud nastavení této zásady nenakonfigurujete, je to možné škodlivých akcí, které jsou součástí iniciované skriptu automaticky otevíraná okna a okna, která zahrnují panely názvu a stavu nelze spustit. Tuto funkci zabezpečení aplikace Internet Explorer bude na v této zóně určený nastavení pro proces řízení funkci skripty Windows bezpečnostní omezení.
  - **Výchozí**: Zakázáno  
  
- **Zóny zabezpečení aplikace Internet Explorer použijte pouze nastavení počítače**  
  Informace o zóně zabezpečení se vztahuje na všechny uživatele stejném počítači. Zóny zabezpečení je skupina webových stránek se stejnou úrovní zabezpečení. Pokud tuto zásadu povolit, budou změny, které uživatel provede do zóny zabezpečení platí pro všechny uživatele tohoto počítače. Pokud tuto zásadu zakážete nebo nenakonfigurujete, uživateli stejném počítači můžete vytvořit vlastní nastavení zóny zabezpečení. Tato zásada určena zajistíte, že nastavení zóny zabezpečení platí jednotně na stejný počítač a se neliší od uživatele k uživateli. Další informace naleznete "zóny zabezpečení: Nepovolte uživatelům měnit zásady"zásady.
  - **Výchozí**: Povoleno  
  
- **Aplikace Internet Explorer uzamčen oprávnění pro jazyk java zóna místního počítače**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, jsou zakázané aplety
  - **Výchozí**: Zakázat java 
  
- **Zóny s omezeným přístupem v Internet Exploreru nespouštějte antimalwarové proti ovládací prvky ActiveX**  </br>
  Nastavení této zásady určuje, jestli aplikace Internet Explorer se spouští antimalwarové programy proti ovládací prvky ActiveX, a zkontrolujte, zda jsou bezpečné pro načtení na stránkách. Pokud nastavení této zásady povolíte, nebude Internet Exploreru zkontrolujte s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Uživatele můžete vypnout toto chování zapnout nebo vypnout pomocí nastavení zabezpečení aplikace Internet Explorer.
  - **Výchozí**: Zakázáno  
  
- **Spustit s podpisem authenticode spolehlivé součásti .NET Framework s omezeným přístupem zóny Internet Exploreru**  
  Nastavení této zásady umožňuje určit, zda mohou být spuštěny součásti rozhraní .NET Framework, které jsou podepsané pomocí technologie Authenticode aplikace Internet Explorer. Mezi tyto komponenty patří spravované ovládací prvky, které odkazuje objektu značku a spravované spustitelné soubory, které na něj odkazovat z odkazu. Pokud nastavení této zásady povolíte, spustí aplikaci Internet Explorer podepsaný spravované součásti. Pokud v rozevíracím seznamu vyberte řádek, Internet Explorer vyzve uživatele k určení, jestli se má spouštět podepsané spravované součásti. Pokud nastavení této zásady zakážete, aplikace Internet Explorer nespustí, podepsaný spravované součásti. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer nespustí, podepsaný spravované součásti.
  - **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer s omezením pomocí specifikátoru zóny přístup ke zdrojům dat**  
  Nastavení této zásady umožňuje určit, zda aplikace Internet Explorer můžete přistupovat k datům z jiné zóny zabezpečení pomocí Microsoft XML Parser (MSXML) nebo objekty ADO (ActiveX Data OBJECTS). Pokud nastavení této zásady povolíte, uživatelé můžou načítat stránku v oblasti, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat zvolit, jestli se má povolit stránky, který se má načíst v zóně, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud nastavení této zásady zakážete, uživatelé nelze načíst stránku v oblasti, která používá MSXML nebo ADO pro přístup k datům z jiné lokality v zóně. Pokud nastavení této zásady nenakonfigurujete, uživateli nelze načíst stránku v oblasti, která používá pro přístup k datům z jiné lokality v zóně MSXML nebo ADO.
  - **Výchozí**: Zakázat 
  
- **Zóny Internetu aplikace Internet Explorer nespustí antimalwarové proti ovládací prvky ActiveX**  </br>
  Nastavení této zásady určuje, jestli aplikace Internet Explorer se spouští antimalwarové programy proti ovládací prvky ActiveX, a zkontrolujte, zda jsou bezpečné pro načtení na stránkách. Pokud nastavení této zásady povolíte, nebude Internet Exploreru zkontrolujte s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady zakážete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Pokud nastavení této zásady nenakonfigurujete, aplikace Internet Explorer vždy kontroluje s vaším programem antimalwaru, jestli je bezpečný pro vytvoření instance ovládacího prvku ActiveX. Uživatele můžete vypnout toto chování zapnout nebo vypnout pomocí nastavení zabezpečení aplikace Internet Explorer.
  - **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer internetové zóny kopírování a vkládání přes skript** </br> Nastavení této zásady umožňuje určit, zda skripty můžete provést operaci schránky (například vyjmout, kopírovat a vložit) v určité oblasti. Pokud nastavení této zásady povolíte, skriptu můžete provést operaci schránky. Pokud v rozevíracím seznamu vyberte řádek, uživatelé se generuje dotaz na tom, jestli se má provést operace schránky. Pokud nastavení této zásady zakážete, skriptu nelze provést operaci schránky. Pokud nastavení této zásady nenakonfigurujete, skript provádět operaci schránky.
  - **Výchozí**: Zakázat  
  
- **Aplikace Internet Explorer použijte Active X instalační služba**  </br>
  Nastavení této zásady umožňuje určit, jak jsou nainstalovány – ovládací prvky ActiveX. Pokud nastavení této zásady povolíte, ovládací prvky ActiveX jsou nainstalovány pouze v případě, že je k dispozici instalační služba ActiveX a není nakonfigurovaná k povolení instalace ovládacích prvků ActiveX. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, nainstaluje se ovládací prvky ActiveX, včetně uživatelských ovládacích prvků, prostřednictvím standardního procesu instalace.
  - **Výchozí**: Povoleno  
  
- **Aplikace Internet Explorer zpracovává ochranu proti zvýšení oprávnění zóny**  
  Na každé webové stránky, otevře se aplikace Internet Explorer umístí omezení. Omezení jsou závislé na umístění webové stránky (Internetu, intranetu, zóna místního počítače a tak dále). Například webové stránky v místním počítači máte nejmíň bezpečnostní omezení a jsou umístěny v zóně Místní počítač zóna prvotní cíle uživateli se zlými úmysly zabezpečení místního počítače. Pokud nastavení této zásady povolíte, se dají chránit všechny zóny ze zóny ke zvýšení úrovně oprávnění pro všechny procesy. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, zobrazí se procesy než Internet Explorer nebo hodnotami uvedenými v seznamu proces žádná taková ochrana.
  - **Výchozí**: Povoleno  
  
- **Zóny Internetu aplikace Internet Explorer stahování bez znaménka ovládací prvky ActiveX**  </br>
  Nastavení této zásady umožňuje určit, zda uživatelé mohou stáhnout nepodepsané ovládací prvky ActiveX ze zóny. Takový kód je potenciálně škodlivých, zejména v případě, že pocházejí z nedůvěryhodné zóny. Pokud povolíte toto nastavení zásad, můžou uživatelé spouštět nepodepsané ovládací prvky bez zásahu uživatele. Pokud v rozevíracím seznamu vyberte řádek, uživatelé se dotazováním vyberte, jestli chcete povolit spuštění bez znaménka ovládacího prvku. Pokud nastavení této zásady zakážete, uživatelé nemůžou spouštět nepodepsané ovládací prvky. Pokud nastavení této zásady nenakonfigurujete, uživatelé nemůžou spouštět nepodepsané ovládací prvky.
  - **Výchozí**: Zakázat  
  
- **Zóny Internetu aplikace Internet Explorer přejděte v různých doménách systému windows a snímků**  </br>
  Toto nastavení zásad umožňuje spravovat otevírání windows a snímků a přístup k aplikacím v různých doménách. Pokud nastavení této zásady povolíte, uživatelé mohli otevřít windows a snímků z jiné domény a přístup k aplikacím z jiných domén. Pokud v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli se má povolit windows a snímky s cílem získat přístup k aplikacím z jiných domén. Pokud nastavení této zásady zakážete, nelze otevřít uživatelům windows a snímky s cílem získat přístup k aplikacím z různých domén. Pokud nastavení této zásady nenakonfigurujete, uživatelé mohou otevřít windows a snímků z jiných domén a přístup k aplikacím z jiných domén.
  - **Výchozí**: Zakázat  
  
- **Aktualizace zóny Internetu aplikace Internet Explorer na stavovém řádku prostřednictvím skriptu**  
  Nastavení této zásady umožňuje určit, zda smí skript aktualizace stavového řádku v rámci zóny. Pokud povolíte toto nastavení zásad, můžou aktualizovat stavový řádek skriptu. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, skriptu není povoleno aktualizovat na stavovém řádku.
  - **Výchozí**: Zakázáno  
  
- **Zóny Internet Exploreru s omezeným přístupem zahrnují místní cesty při nahrávání souborů do serveru**  </br> Nastavení této zásady určuje, zda je či není místní cesta informace se odešle, když uživatel je nahrát soubor přes formulář HTML. Pokud se pošle informace o místní cestu a některé informace mohou neúmyslně odhalena k serveru. Soubory odeslané z plochy uživatele, může obsahovat uživatelské jméno jako součást cesty. Pokud nastavení této zásady povolíte, informace o cestě se odešle, když uživatel je nahrát soubor přes formulář HTML. Pokud nastavení této zásady zakážete, informace o cestě se odebere, pokud uživatel odesílá soubory přes formulář HTML. Pokud nastavení této zásady nenakonfigurujete, uživatel může zvolit, zda informace o cestě se odešle, když při nahrávání souborů přes formulář HTML. Ve výchozím nastavení je odeslána informace o cestě.
  - **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer procesy omezit stahování souborů**  </br> Nastavení této zásady umožňuje aplikacím hostujícím ovládací prvek webového prohlížeče k blokování Automatické dotazování stahování souborů, které nejsou iniciované uživatelem. Pokud nastavení této zásady povolíte, bude ovládací prvek webového prohlížeče blokovat Automatické dotazování stahování souborů, které nejsou uživatelem iniciované pro všechny procesy. Pokud nastavení této zásady zakážete, nebude blokovat Automatické dotazování stahování souborů, které nejsou uživatelem iniciované pro všechny procesy ovládací prvek WebBrowser.
  - **Výchozí**: Povoleno  
  
- **Povolit zakázané zóny Internet Exploreru schválí jen tehdy, domény použít ovládací prvky ActiveX**  </br>
  Toto nastavení zásady řídí, jestli je uživatel vyzván k povolit ovládacích prvků ActiveX ke spuštění ve službě websites než webu, nainstalované ovládacího prvku ActiveX. Pokud nastavení této zásady povolíte, bude uživatel vyzván, ovládací prvky ActiveX lze spustit z webů v této zóně. Uživatel může zvolit, aby ovládací prvek pro spuštění z aktuální lokality nebo ze všech lokalit. Pokud nastavení této zásady zakážete, uživatel neuvidí řádku ActiveX podle webu a ovládací prvky ActiveX lze spustit ze všech lokalit v této zóně.
  - **Výchozí**: Povoleno  
  
- **Inicializace s omezeným přístupem zóny Internet Exploreru a skript, který ovládací prvky ActiveX neoznačené jako bezpečné**  
  Toto nastavení zásad umožňuje spravovat ovládací prvky ActiveX neoznačené jako bezpečné. Pokud nastavení této zásady povolíte, ovládací prvky ActiveX jsou spuštění načíst s parametry a skriptované bez nastavení zabezpečení objektů pro nedůvěryhodná data nebo skripty. Toto nastavení se nedoporučuje, s výjimkou zabezpečený a spravovaný zóny. Toto nastavení způsobí, že nebezpečné a bezpečné ovládací prvky k inicializaci a skripty, ignoruje ovládací prvky skriptu ActiveX označeny jako bezpečné pro skriptování – možnost. Pokud povolíte toto nastavení zásad a v rozevíracím seznamu vyberte řádek, jsou uživatelé dotazovat, jestli chce použít ovládací prvek, který má být načten s parametry nebo skripty. Pokud nastavení této zásady zakážete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načtena s parametry nebo skripty. Pokud nastavení této zásady nenakonfigurujete, ovládací prvky ActiveX, které nejde provést bezpečné nejsou načteny s parametry nebo skripty.
  - **Výchozí**: Zakázat  
  
- **Změna zásad uživatele aplikace Internet Explorer**  
    Zabrání uživatelům možnost měnit nastavení zóny zabezpečení. Zóny zabezpečení je skupina webových stránek se stejnou úrovní zabezpečení. Pokud tuto zásadu povolit, jsou zakázané tlačítko Vlastní úroveň a úroveň zabezpečení posuvník na kartě zabezpečení v dialogovém okně Možnosti Internetu. Pokud tuto zásadu zakážete nebo nenakonfigurujete, uživatelé mohou změnit nastavení zóny zabezpečení. Tato zásada zabraňuje uživatelům možnost měnit nastavení zóny zabezpečení nastavená správcem. Poznámka: "Zakázat na stránce zabezpečení" zásady (umístěné v \User Configuration\Administrative pro správu\Součásti systému Windows\Internet Explorer\Ovládací ovládací panely), tím se odebere z aplikace Internet Explorer v Ovládacích panelech na kartě zabezpečení, má přednost před Tyto zásady. Pokud je povolena, tato zásada je ignorována. Další informace naleznete "zóny zabezpečení: Použití pouze nastavení počítače"zásad.
    - **Výchozí**: Zakázáno  
  
- **Chráněný režim s omezeným přístupem zóny Internet Exploreru**  
  Nastavení této zásady umožňuje zapnout v chráněném režimu. Chráněný režim pomáhá chránit aplikace Internet Explorer z odstranění zneužité chyby zabezpečení snížením umístění, které aplikace Internet Explorer můžete zapsat do registru a systému souborů. Pokud nastavení této zásady povolíte, chráněný režim zapnutý. Uživatele nelze vypnout chráněný režim. Pokud nastavení této zásady zakážete, chráněný režim je vypnutý. Uživatele nelze zapnout chráněný režim. Pokud nastavení této zásady nenakonfigurujete, uživatel může zapnout nebo vypnout chráněný režim.
  - **Výchozí**: Povolení  
  
- **Trvalost dat uživatele zóny Internetu aplikace Internet Explorer**  
  Toto nastavení zásad umožňuje spravovat uchovávání informací v prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk. Když se uživatel vrátí na stránku trvalé, je možné obnovit stav stránky, pokud nastavení této zásady je správně nakonfigurovaný. Pokud nastavení této zásady povolíte, uživatelé můžete zachovat informace o prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk. Pokud nastavení této zásady zakážete, uživatelé nelze uchovávat informace v prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk. Pokud nastavení této zásady nenakonfigurujete, uživatelé mohou uchovávat informace v prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk.
  - **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer skriptování zóny Internetu ovládacích prvků webového prohlížeče**  
 
  Nastavení této zásady určuje, zda na stránku můžete řídit vložené WebBrowser – ovládací prvky pomocí skriptu. Pokud nastavení této zásady povolíte, je povolen skript přístup k ovládacímu prvku WebBrowser. Pokud nastavení této zásady zakážete, není povolen přístup skript do ovládacího prvku WebBrowser. Pokud nastavení této zásady nenakonfigurujete, uživateli můžete povolit nebo zakázat přístup skript do ovládacího prvku WebBrowser. Ve výchozím nastavení je povolen skript přístup k ovládacímu prvku WebBrowser pouze v místním počítači a zóny intranetu.
  - **Výchozí**: Zakázáno  
  
- **Trvalost dat uživatele s omezením pomocí specifikátoru aplikace Internet Explorer zóny**  
    Toto nastavení zásad umožňuje spravovat uchovávání informací v prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk. Když se uživatel vrátí na stránku trvalé, je možné obnovit stav stránky, pokud nastavení této zásady je správně nakonfigurovaný. Pokud nastavení této zásady povolíte, uživatelé můžete zachovat informace o prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk. Pokud nastavení této zásady zakážete, uživatelé nelze uchovávat informace v prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk. Pokud nastavení této zásady nenakonfigurujete, uživateli nelze uchovávat informace v prohlížeči historie v oblíbených položkách v úložišti XML nebo přímo v rámci webové stránky uloženo na disk.  
  - **Výchozí**: Zakázáno  
  
- **Aplikace Internet Explorer uzamčen oprávnění java zóny intranetu**  
  Toto nastavení zásad umožňuje spravovat oprávnění pro aplety. Pokud nastavení této zásady povolíte, můžete z rozevíracího seznamu možnosti. Vlastní, řídit oprávnění nastavení jednotlivě. Nízká bezpečnosti umožňuje aplety provádět všechny operace. Střední úroveň zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru (oblast v paměti mimo který program nelze provést volání), a navíc možnosti, jako jsou pomocné místo (bezpečné a zabezpečené úložiště v klientském počítači) a soubor řízené uživatelem vstupně-výstupních operací. Vysoké zabezpečení umožňuje aplety ke spuštění v jejich izolovaného prostoru. Zakážete Java žádné aplety Zabraňte jejich spuštění. Pokud nastavení této zásady zakážete, aplety nelze spustit. Pokud nastavení této zásady nenakonfigurujete, aplety jsou zakázané.
  - **Výchozí**: Zakázat java  
  
- **Internet Explorer rozšířeného chráněný režim**  
  Rozšířený chráněný režim nabízí další ochranu před škodlivým webům pomocí 64bitové procesy v 64bitových verzích Windows. Pro počítače se systémem nejméně Windows 8, rozšířeným chráněným režimem omezení, které aplikace Internet Explorer můžete číst z umístění v registru a systému souborů. Pokud nastavení této zásady povolíte, rozšířeným chráněným režimem zapnuté. Všechny zóny s povoleným režimem chráněné použije rozšířeným chráněným režimem. Uživatelé nebudou moct zakázat rozšířeným chráněným režimem. Pokud nastavení této zásady zakážete, rozšířeným chráněným režimem se vypne. Všechny zóny s povoleným režimem chráněné budou používat verzi chráněný režim zavedený aplikace Internet Explorer 7 pro Windows Vista. Pokud tuto zásadu nenakonfigurujete, budou uživatelé moct zapnout nebo vypnout rozšířeným chráněným režimem na kartě Upřesnit v dialogovém okně Možnosti Internetu.
  - **Výchozí**: Povoleno  
  
- **Aplikace Internet Explorer obejít upozornění SmartScreen**  
  Nastavení této zásady určuje, zda uživatel může obejít upozornění filtru SmartScreen. Filtr SmartScreen uživatele upozorní na spustitelné soubory, které uživatele aplikace Internet Explorer nestahovat běžně z Internetu. Pokud nastavení této zásady povolíte, uživateli blokovat upozornění filtru SmartScreen. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, můžete uživateli obejít upozornění filtru SmartScreen.
  - **Výchozí**: Zakázáno  
  
- **Aktualizace metadat zóny Internet Exploreru s omezením pomocí specifikátoru**  
  Nastavení této zásady umožňuje určit, zda prohlížeče uživatele je možné přesměrovat do jiné webové stránky, pokud autor webové stránky používá nastavení Meta Refresh (značky) pro přesměrování prohlížeče na jiný web. Pokud nastavení této zásady povolíte, prohlížeče uživatele, který načte stránku obsahující aktivní nastavení Meta Refresh můžete přesměrovat na jinou webovou stránku. Pokud nastavení této zásady zakážete, prohlížeče uživatele, který načte stránku obsahující aktivní nastavení Meta Refresh nelze přesměrovat na jinou webovou stránku. Pokud nastavení této zásady nenakonfigurujete, prohlížeče uživatele, který načte stránku obsahující aktivní nastavení Meta Refresh nelze přesměrovat na jinou webovou stránku.
  - **Výchozí**: Zakázáno  
  
## <a name="local-policies-security-options"></a>Možnosti místní zásady zabezpečení
Další informace najdete v tématu [zásady CSP – LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) v dokumentaci k Windows. 

- **Omezení anonymní přístup k pojmenované kanály a sdílené složky**  
  Když je povoleno, toto nastavení zabezpečení omezuje anonymní přístup ke sdíleným složkám a kanálům k nastavením pro: (1) pojmenované kanály, které lze přistupovat anonymně. sdílené složky (2), které se dá přistupovat anonymně
  - **Výchozí**: Ano  
  
- **Minimální zabezpečení relace pro NTLM SSP podle serverů**  
  Toto nastavení zabezpečení umožňuje serveru požadovat vyjednávání 128bitové šifrování a/nebo NTLMv2 relace zabezpečení. Tyto hodnoty jsou závislé na hodnotě nastavení zabezpečení úroveň ověřování pro systém LAN Manager. Možnosti: Vyžadovat NTLMv2 relace zabezpečení: Připojení se nezdaří, pokud není vyjedná integrity zprávy. Vyžadovat 128bitové šifrování. Pokud není vyjedná silné šifrování (128-bit), připojení se nezdaří.
  - **Výchozí**: Vyžadovat NTLM V2 a 128bitové šifrování  
  
- **Počet minut nečinnosti zámek obrazovky, dokud se aktivuje šetřič obrazovky**  
  Systém Windows zaznamená nečinnost relace přihlášení, a pokud neaktivní doba překračuje limit nečinnosti, pak se spustí šetřič obrazovky, který relaci uzamkne.
  - **Výchozí**: 15
  
- **Vyžadovat klient vždy digitálně podepsat komunikaci** toto nastavení zabezpečení určuje, zda veškerý provoz zabezpečený kanál iniciovaných člena domény musí být podepsána nebo zašifrována. Když počítač připojí k doméně, vytvoří se účet počítače. Heslo účtu počítače je při spuštění systému používá k vytvoření zabezpečeného kanálu s řadičem domény pro příslušné domény. Tento zabezpečený kanál slouží k provádění operací, jako je protokol NTLM předávání ověřování, LSA SID/názvu vyhledávání atd. Toto nastavení určuje, zda veškerý provoz zabezpečený kanál iniciovaná členem domény, splňuje minimální požadavky na zabezpečení. Konkrétně určuje, zda veškerý provoz zabezpečený kanál iniciovaných člena domény musí být podepsána nebo zašifrována. Pokud je tato zásada povolená, nebude zabezpečený kanál vytvořen, pokud se vyjedná podepisování nebo šifrování veškeré komunikace zabezpečený kanál. Pokud tato zásada je zakázána, je šifrování a se vyjedná podepisování veškerého provozu zabezpečený kanál s řadičem domény. v takovém případě úroveň podepisování a šifrování závisí na verzi řadičem domény a nastavení z následujících dvou zásady: Člen domény: Digitálně zašifrovat data zabezpečeného kanálu (Pokud je to možné) člen domény: Digitálně podepsat data zabezpečeného kanálu (Pokud je to možné)
  - **Výchozí**: Ano
  
- **Úroveň ověřování**  
  Toto nastavení zabezpečení určuje, který protokol ověřování požadavku a odpovědi se používá pro přihlášení k síti. Tato volba ovlivňuje úroveň ověřování protokolu používané klienty, úroveň zabezpečení relace vyjednávat a úroveň ověřování přijal servery následujícím způsobem: Odeslání odpovědi LM a protokol NTLM: Klienti používají ověřování LM a NTLM a nikdy NTLMv2 relace zabezpečení. řadiče domény přijmout LM, ověřování protokolů NTLM a ověřování NTLMv2. Odeslat LM a NTLM – v případě vyjedná použít NTLMv2 relace zabezpečení: Klienti používají ověřování LM a NTLM a NTLMv2 relace zabezpečení, pokud server podporuje. řadiče domény přijmout LM, ověřování protokolů NTLM a ověřování NTLMv2. Odeslat pouze ověřování NTLM odpovědi: Klienti používají pouze ověřování NTLM a NTLMv2 relace zabezpečení, pokud server podporuje. řadiče domény přijmout LM, ověřování protokolů NTLM a ověřování NTLMv2. Odeslat pouze NTLMv2 odpovědi: Klienti používají pouze ověřování NTLMv2 a NTLMv2 relace zabezpečení, pokud server podporuje. řadiče domény přijmout LM, ověřování protokolů NTLM a ověřování NTLMv2. Poslat odpověď NTLMv2 LM – odmítat odpovědi: Klienti používají pouze ověřování NTLMv2 a NTLMv2 relace zabezpečení, pokud server podporuje. řadiče domény odmítnout LM (přijímat pouze ověřování NTLM a ověřování NTLMv2). Odeslat odmítat NTLMv2 odpovědi odpovědi LM a protokol NTLM: Klienti používají pouze ověřování NTLMv2 a NTLMv2 relace zabezpečení, pokud server podporuje. řadiče domény odmítnout LM a NTLM (přijímat pouze ověřování NTLM verze 2).
  - **Výchozí**: Odeslat pouze NTLMv2 odpovědi. Odmítnout LM a NTLM
  
- **Zabráníte klientům v odesílání nešifrovaná hesla serverům SMB třetích stran**  
  Pokud je povolené toto nastavení zabezpečení, přesměrovače zprávy bloku SMB (Server) může posílat nešifrovaná hesla serverům SMB mimo Microsoft, které nepodporují šifrování hesel během ověřování. Odesílání nešifrovaná hesla je bezpečnostním rizikem.
  - **Výchozí**: Ano
  
- **Zakázat server vždy digitálně podepíše komunikace**  
  Toto nastavení zabezpečení určuje, zda klient SMB pokouší vyjednat podepisování paketů SMB. Protokol server message block (SMB) poskytuje základ pro sdílení Microsoft souborů a tiskáren a mnoho dalších síťových operací, jako je vzdálené správy Windows. Aby se zabránilo útokům man-in-the-middle úpravě paketů SMB při přenosu, protokolu SMB podporuje digitálnímu podepisování paketů SMB. Nastavení této zásady určuje, zda klient SMB pokouší při připojení k serveru SMB podepisování paketů SMB vyjednávat. Pokud je toto nastavení povolené, klient sítě Microsoft požádá server, aby po nastavení relace podepisování paketů SMB. Pokud byly na serveru povoleno podepisování paketů, podepisování paketů se vyjedná. Pokud tyto zásady zakážou, klient SMB nikdy vyjednat podepisování paketů SMB.
  - **Výchozí**: Ano
  
- **Chování výzvy ke zvýšení úrovně oprávnění správce**  
  Toto nastavení zásady řídí chování výzvy ke zvýšení oprávnění pro správce. Možnosti: 0 – zvýšit oprávnění bez dotazu: Umožňuje privilegované účty se provést operaci, která vyžaduje zvýšení oprávnění bez nutnosti souhlas nebo přihlašovací údaje. Poznámka: Tuto možnost použijte pouze v nejvíce omezených prostředích. 1 - výzvu k zadání přihlašovacích údajů na zabezpečené ploše: Pokud operace vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván na zabezpečené ploše zadejte privilegovaných uživatelské jméno a heslo. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s nejvyšší dostupná oprávnění uživatele. 2 - požádat o souhlas na zabezpečené ploše: Pokud operace vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván na zabezpečené ploše a vyberte Povolit nebo odepřít. Pokud si uživatel vybere povolení, operace pokračuje s nejvyšší dostupná oprávnění uživatele. 3 – výzva k zadání přihlašovacích údajů: Pokud operace vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván k zadání uživatelské jméno správce a heslo. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s příslušnými oprávněními. 4 – výzva k zadání souhlasu: Pokud operace vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván k výběru povolení nebo odepření. Pokud si uživatel vybere povolení, operace pokračuje s nejvyšší dostupná oprávnění uživatele. 5 - požádat o souhlas pro binární soubory bez Windows: (Výchozí) Při operaci pro aplikaci od jiných výrobců vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván na zabezpečené ploše a vyberte Povolit nebo odepřít. Pokud si uživatel vybere povolení, operace pokračuje s nejvyšší dostupná oprávnění uživatele
  - **Výchozí**: Požádat o souhlas na zabezpečené ploše
  
- **Klienty založené na minimální zabezpečení relace pro NTLM SSP**  
  Toto nastavení umožňuje klientovi tak, aby vyžadovala vyjednávání 128bitové šifrování a/nebo NTLMv2 relace zabezpečení. Tyto hodnoty jsou závislé na hodnotě nastavení zabezpečení úroveň ověřování pro systém LAN Manager. Možnosti: Vyžadovat NTLMv2 relace zabezpečení: Připojení se nezdaří, pokud není vyjednaný protokolem NTLMv2. Vyžadovat 128bitové šifrování: Pokud není vyjedná silné šifrování (128-bit), připojení se nezdaří.
  - **Výchozí**: Vyžadovat šifrování NTLM V2 128
  
- **Chování při vyjmutí čipové karty**  
  Toto nastavení zabezpečení určuje, co se stane, když se čipová karta přihlášeného uživatele se odebere ze čtečky čipových karet. Možnosti: Žádná akce uzamčení pracovní stanice Vynutit odhlášení odpojit, pokud relace služby Vzdálená plocha, vyberete-li zamknout pracovní stanici ve vlastnostech dialogové okno pro tyto zásady, pracovní stanice uzamkne při odebrání čipové karty, uživatelé si tak nechat oblasti, můžou využít svoje čipové karty s nimi a přitom zachovává chráněné relace. Pokud klepnete na tlačítko v dialogovém okně Vlastnosti pro tuto zásadu Vynutit odhlášení časový limit, automaticky odhlášením uživatele při odebrání čipové karty. Pokud kliknete na odpojit, pokud relace služby Vzdálená plocha, odebrání čipové karty odpojí relaci bez odhlášení uživatele. To umožňuje uživateli vložení čipové karty a obnovení relace později nebo v jiném čipových karet odpojena počítači, aniž byste museli znovu přihlašovat. Pokud je relace místní, funguje tato zásada stejně jako možnost Zamknout pracovní stanici.
  - **Výchozí**: Zamknout pracovní stanici
  
- **Blok anonymní výčty účtů SAM a sdílených složek**  
  Toto nastavení zabezpečení určuje, jestli je povolené anonymní výčty účtů SAM a sdílených složek. Windows umožňuje anonymním uživatelům provádět určité aktivity, jako je například výčet názvů účtů domén a sdílených síťových složek. To je praktické, například, pokud chce správce udělit přístup uživatelům v důvěryhodné doméně, která nespravuje vzájemnou důvěryhodnost. Pokud nechcete povolit anonymní výčet SAM, účty a sdílených složek, povolte tyto zásady.
  - **Výchozí**: Ano
  
- **Blok vzdáleného přihlášení s prázdným heslem**  
  Toto nastavení zabezpečení určuje, jestli místní účty, které se nechrání pomocí hesla je použít k přihlášení z umístění jiných než konzole fyzického počítače. Pokud je povoleno, místní účty, které se nechrání pomocí hesla budou moci pouze přihlášení na klávesnice počítače. Upozornění: Počítače, které nejsou ve fyzicky zabezpečeném umístění by měl vždy prosazujte zásady silných hesel pro všechny místní uživatelské účty. Jinak každý, kdo má fyzický přístup k počítači může přihlásit pomocí uživatelského účtu, který nemá žádné heslo. To je obzvláště důležité pro přenosné počítače. Pokud použijete tuto zásadu zabezpečení Everyone skupině, nebude moci přihlásit prostřednictvím služby Vzdálená plocha. Toto nastavení nemá vliv na přihlášení pomocí účtů domény. Je možné pro aplikace, které používají Vzdálená interaktivní přihlášení obejít tato nastavení.
  - **Výchozí**: Ano
  
- **Standardní uživatel chování výzvy ke zvýšení úrovně oprávnění**  
  Toto nastavení zásady řídí chování výzvy ke zvýšení oprávnění pro standardní uživatele. 0 – automaticky zamítnout požadavky na zvýšení oprávnění: Pokud operace vyžaduje zvýšení úrovně oprávnění, konfigurovat odepřením přístupu se zobrazí chybová zpráva. Organizace, na kterém běží stolní počítače, protože standardní uživatel může zvolit tohoto nastavení může snížit volání služby HelpDesk. 1 - výzvu k zadání přihlašovacích údajů na zabezpečené ploše: Pokud operace vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván na zabezpečené ploše zadejte jiné uživatelské jméno a heslo. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s příslušnými oprávněními. 3 (výchozí) – výzva k zadání pověření: Pokud operace vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván k zadání uživatelské jméno správce a heslo. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s příslušnými oprávněními.
  - **Výchozí**: Automaticky zamítnout požadavky na zvýšení
  
- **Vyžaduje režim schválení správcem pro správce**  
  Toto nastavení zásady řídí chování všechna nastavení zásad řízení uživatelských účtů (UAC) v počítači. Pokud změníte toto nastavení zásad, musíte restartovat počítač. Možnosti: 0 – zakázáno: Režim schválení správcem a všechna nastavení souvisejících zásad nástroje Řízení uživatelských účtů jsou zakázané. Poznámka: Pokud nastavení této zásady je zakázané, Security Center vás upozorní, snížil celkové zabezpečení operačního systému. 1 – povoleno: (Výchozí) Je povolené režim schválení správcem. Tato zásada musí být povolená a související zásady nastavení nástroje Řízení uživatelských účtů musí být také správně nastavena umožňující předdefinovaného účtu Administrator a všichni uživatelé, kteří jsou členy skupiny Administrators spouštět v režimu schválení správcem.
  - **Výchozí**: Ano
  
- **Zakázat anonymní výčty účtů SAM**  
  Toto nastavení zabezpečení určuje, jaké další oprávnění budou mít pro anonymní připojení k počítači. Windows umožňuje anonymním uživatelům provádět určité aktivity, jako je například výčet názvů účtů domén a sdílených síťových složek. To je praktické, například, pokud chce správce udělit přístup uživatelům v důvěryhodné doméně, která nespravuje vzájemnou důvěryhodnost. Tato možnost zabezpečení umožňuje další omezení umístit na anonymní připojení následujícím způsobem: Povoleno: Nepovolit výčet SAM účtů. Tato možnost nahradí všechny Authenticated Users oprávnění zabezpečení pro prostředky. Zakázáno: Žádná další omezení. Spolehněte se na výchozí oprávnění. Výchozí na pracovní stanice: Povolené. Výchozí na serveru: Povolené.
  - **Výchozí**: Ano
  
- **Povolit vzdálené volání správce zabezpečení účtů**  
  Nastavení této zásady umožňuje omezit připojení vzdáleného rpc k SAM. Pokud není vybrána, použije se výchozí popisovač zabezpečení.
  - **Výchozí**: *O:BAG:BAD:(A;;RC;;;BA)*

- **Použít režim schválení správcem**  
  Toto nastavení zásady řídí chování režim schválení správcem pro předdefinovaný účet Administrator. Možnosti jsou: • povoleno: Předdefinovaný účet správce používá režim schválení správcem. Ve výchozím nastavení všechny operace, která vyžaduje zvýšení úrovně oprávnění se zobrazí výzva ke schválení operaci. • Zakázáno: (Výchozí) Předdefinovaný účet správce spustí všechny aplikace s plný administrativní oprávnění.
  - **Výchozí**: Ano
  
- **Povolit přístup k aplikacím uživatelského rozhraní pro zabezpečené umístění**  
  Tato zásada, nastavení ovládacích prvků, jestli programy User Interface Accessibility (UIAccess nebo také UIA) můžete automaticky vypnout zabezpečenou plochu používá standardní uživatelské výzvy ke zvýšení oprávnění. Povoleno: Účelem programů UIA, včetně vzdálené pomoci pro Windows, automaticky vypnout zabezpečenou plochu výzvy ke zvýšení oprávnění. Pokud není zakázána "Řízení uživatelských účtů: Při zobrazení výzvy ke zvýšení oprávnění přepnout na zabezpečenou plochu"nastavení zásad, výzvy se zobrazí na ploše interaktivního uživatele místo zabezpečené ploše. Zakázáno: (Výchozí) Zabezpečenou plochu může zakázat jen uživatel interaktivní plochy nebo vypnutí "Řízení uživatelských účtů: Při zobrazení výzvy ke zvýšení oprávnění přepnout na zabezpečenou plochu"nastavení zásad.
  - **Výchozí**: Ano

- **Zjistit instalace aplikací a zobrazit výzvu ke zvýšení oprávnění**  
  Toto nastavení zásady řídí chování zjišťování instalace aplikací pro počítače. Možnosti: Povoleno: (Výchozí) Při zjištění instalačního balíčku aplikace, který vyžaduje zvýšení úrovně oprávnění, bude uživatel vyzván k zadejte uživatelské jméno správce a heslo. Pokud uživatel zadá platné přihlašovací údaje, operace pokračuje s příslušnými oprávněními. Zakázáno: Instalační balíčky aplikací nejsou zjištěny a zobrazení výzvy ke zvýšení oprávnění. Podnikům, které jsou spuštěny ploch standardních uživatelů a používat delegovaná instalace technologie, jako je instalace softwaru zásad skupiny nebo Systems Management Server (SMS) byste zakázat toto nastavení zásad. V takovém případě detekci Instalační služby systému je zbytečné.
  - **Výchozí**: Ano
  
- **Zabránit ukládání hodnoty hash LAN Manageru při příští změně hesla**  
  Toto nastavení zabezpečení určuje, zda při příští změně hesla, hodnoty hash LAN Manager (LM) pro nové heslo je uložena. Hodnota hash LM je poměrně malý a náchylné k útokům, mezi hodnota hash kryptograficky silnější Windows NT. Protože hodnota hash LM jsou uloženy v místním počítači v databázi zabezpečení může být ohrožena hesla při napadení zabezpečení databáze.
  - **Výchozí**: Ano

- **Virtualizovat souborů a registrů zápisu chyby do podle umístění uživatele**  
  Toto nastavení řídí, jestli se chyby zápisu aplikace přesměrují na definovaná umístění registru a souborů systému zásad. Nastavení této zásady snižuje riziko zneužití aplikací, které spustit jako správce a zapisovat do % ProgramFiles %, % Windir %, % Windir%\system32 nebo klíče HKLM\Software dat za běhu aplikace.
  - **Výchozí**: Ano

## <a name="ms-security-guide"></a>Příručka zabezpečení MS  
Další informace najdete v tématu [zásady CSP – MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) v dokumentaci k Windows.  

- **Místní účty na přihlášení k síti použít omezení nástroje Řízení uživatelských účtů**  
    - **Výchozí**: Povoleno
  
- **Konfigurace spuštění ovladače klienta v1 SMB**  
  - **Výchozí**: Zakázané ovladače
  
- **Server s protokolem SMB verze 1**  
  - **Výchozí**: Zakázáno
  
- **Ověřování algoritmem Digest**  
  - **Výchozí**: Zakázáno
  
- **Strukturované zpracování výjimek přepsat ochrany**  
  - **Výchozí**: Povoleno
  
## <a name="mss-legacy"></a>Starší verze MSS  
Další informace najdete v tématu [zásady CSP – MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) v dokumentaci k Windows.  

- **Zdroj protokolu IP sítě směrování úroveň ochrany**  
  - **Výchozí**: Nejvyšší ochrany 
  
- **Ignorovat síťové požadavky na verzi název rozhraní NetBIOS s výjimkou ze serverů WINS**  
  - **Výchozí**: Povoleno
  
- **IPv6 zdroj směrování úroveň ochrany sítě**  
  - **Výchozí**: Nejvyšší ochrany

- **Přesměrování protokolu ICMP sítě přepsat generované protokolu OSPF**  
  - **Výchozí**: Zakázáno
  
## <a name="power"></a>Napájení  
Další informace najdete v tématu [zásady CSP - Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) v dokumentaci k Windows.  

- **Vyžadovat heslo při probuzení, zatímco napájen ze sítě**  
  Nastavení této zásady určuje, zda uživatel je vyzván k zadání hesla, když se systém obnoví z režimu spánku. Pokud povolíte nebo nastavení této zásady nenakonfigurujete, bude uživatel vyzván k zadání hesla, když se systém obnoví z režimu spánku. Pokud nastavení této zásady zakážete, není uživatel vyzván k zadání hesla, když se systém obnoví z režimu spánku.
  - **Výchozí**: Povoleno
  
- **Úsporné při režimu spánku, když jste na baterie**  
  Toto nastavení zásad spravuje, jestli Windows může používat úsporné režimy při uvedení počítače do režimu spánku. Je-li povolit nebo nenakonfigurujete toto nastavení zásad, používá Windows úsporné k uvedení počítače do režimu spánku. Pokud nastavení této zásady zakážete, úsporné (S1 S3) nejsou povoleny.
  - **Výchozí**: Zakázáno
  
- **Úsporné při režimu spánku, zatímco napájen ze sítě**  
  Toto nastavení zásad spravuje, jestli Windows může používat úsporné režimy při uvedení počítače do režimu spánku. Je-li povolit nebo nenakonfigurujete toto nastavení zásad, používá Windows úsporné k uvedení počítače do režimu spánku. Pokud nastavení této zásady zakážete, úsporné (S1 S3) nejsou povoleny.
  - **Výchozí**: Zakázáno
  
- **Vyžadovat heslo při probuzení na baterie**  
  Nastavení této zásady určuje, zda uživatel je vyzván k zadání hesla, když se systém obnoví z režimu spánku. Pokud povolíte nebo nastavení této zásady nenakonfigurujete, bude uživatel vyzván k zadání hesla, když se systém obnoví z režimu spánku. Pokud nastavení této zásady zakážete, není uživatel vyzván k zadání hesla, když se systém obnoví z režimu spánku.
  - **Výchozí**: Povoleno
  
## <a name="remote-desktop-services"></a>Vzdálená plocha  
Další informace najdete v tématu [zásady CSP – RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) v dokumentaci k Windows.  

- **Blokování ukládání hesel**  
  Určuje, zda hesla lze uložit na tento počítač z připojení ke vzdálené ploše. Pokud povolíte toto nastavení zakáže heslo ukládání zaškrtávacího políčka v připojení ke vzdálené ploše a uživatelé už nebudou moct ukládat hesla. Když uživatel otevře soubor RDP pomocí připojení ke vzdálené ploše a uloží jeho nastavení, budou odstraněna všechna hesla, která dříve byla uložena v souboru RDP. Pokud toto nastavení zakážete nebo necháte není nakonfigurováno, bude uživatel moci ukládat hesla pomocí připojení ke vzdálené ploše.
  - **Výchozí**: Povoleno
  
- **Zabezpečená komunikace RPC**  
  Určuje, jestli server hostitele relace vzdálené plochy vyžaduje zabezpečené komunikace RPC se všemi klienty nebo umožňuje nezabezpečenou komunikaci. Toto nastavení můžete použít k posílení zabezpečení protokolu RPC komunikaci s klienty tím, že jenom ověřený a šifrovaný požadavky. Pokud je stav nastaven na povoleno, služby Vzdálená plocha přijímá požadavky od klientů vzdáleného volání Procedur, které podporuje požadavky na zabezpečení a neumožňuje nezabezpečenou komunikaci s nedůvěryhodné klienty. Pokud je stav nastaven na hodnotu zakázáno, služby Vzdálená plocha vždy požadavky zabezpečení pro všechny přenosy RPC. Zabezpečená komunikace je však povoleno pro klienty vzdáleného volání Procedur, které neodpoví na požadavek. Pokud je stav nastaven není nakonfigurováno, zabezpečená komunikace bude povolena. Poznámka: Rozhraní RPC se používá ke správě a konfiguraci služby Vzdálená plocha.
  - **Výchozí**: Povoleno
  
- **Jednotku přesměrování bloku**  
  Nastavení této zásady určuje, zda bude bráněno mapování jednotky klienta v relaci vzdálené plochy (přesměrování jednotek). Ve výchozím nastavení serveru hostitele relace VP mapuje klientské jednotky automaticky po připojení. Připojené jednotky se objeví ve stromové struktuře relace složek v Průzkumníku souborů nebo počítače ve formátu  *\<písmeno_jednotky >* na  *\<název_počítače >*. Nastavení této zásady můžete použít k přepsání tohoto chování. Pokud nastavení této zásady povolíte, přesměrování klienta jednotky není povoleno v relace služby Vzdálená plocha a přesměrování kopie souboru schránky není povolené v počítačích se systémem Windows Server 2003, Windows 8 a Windows XP. Pokud nastavení této zásady zakážete, přesměrování jednotek je vždycky povolená. Kromě toho je vždycky povolená přesměrování kopie souborů schránky. Pokud je povoleno přesměrování schránky. Pokud nastavení této zásady nenakonfigurujete, nejsou zadány jednotky přesměrování klientů a přesměrování kopie souboru schránky na úrovni zásad skupiny.
  - **Výchozí**: Povoleno
  
- **Výzva k zadání hesla při připojení**  
  Nastavení této zásady určuje, zda služby Vzdálená plocha vždy vyzve k zadání hesla při připojení klienta. Toto nastavení slouží k vynucení výzva k zadání hesla pro uživatele přihlášení do služby Vzdálená plocha, i v případě, že se už zadali heslo v klientovi připojení ke vzdálené ploše. Ve výchozím nastavení služby Vzdálená plocha umožňuje uživatelům přihlásit se automaticky tak, že zadáte heslo klienta připojení ke vzdálené ploše. Pokud nastavení této zásady povolíte, uživatelé nemohou přihlásit automaticky k vzdálené ploše zadáním hesla do klienta připojení ke vzdálené ploše. Zobrazí se výzva k zadání hesla k přihlášení. Pokud nastavení této zásady zakážete, můžete vždy přihlášení k vzdálené ploše automaticky zadáním hesla do klienta připojení ke vzdálené ploše. Pokud nastavení této zásady nenakonfigurujete, není zadán automatické přihlášení na úrovni zásad skupiny. 
  - **Výchozí**: Povoleno
  
- **Úroveň šifrování připojení klienta služby Vzdálená plocha**  
  Určuje, jestli se vyžaduje použití úrovně konkrétní šifrování pro zabezpečení komunikace mezi klientskými počítači a servery hostitele relace VP během připojení protokolu RDP (Remote Desktop). Tyto zásady platí jenom při použití nativní šifrování protokolu RDP. Však není doporučeno nativní šifrování protokolu RDP (na rozdíl od šifrování SSL). Tyto zásady se nevztahují na šifrování SSL. Pokud nastavení této zásady povolíte, musí veškerá komunikace mezi klienty a servery hostitele relace VP během vzdálené připojení použijte metodu šifrování zadané v tomto nastavení. Ve výchozím nastavení úrovně šifrování nastavena na hodnotu Vysoká. Jsou dostupné tyto metody šifrování:  
  - *Vysoká*: Nastavení Vysoká šifruje data odesílaná z klienta na serveru a ze serveru klientovi pomocí silného 128bitové šifrování. Použijte tuto úroveň šifrování v prostředích, která obsahují pouze klienty se 128-bit (třeba klienti, na kterých běží připojení ke vzdálené ploše). Klienti, kteří nepodporují tato úroveň šifrování se nemůže připojit k serverům hostitele relace VP.  
  - *Kompatibilní s klientem*: Klient kompatibilní nastavení šifruje data odesílaná mezi klientem a serverem nejsilnějšího klíče podporované klientem. Použijte tuto úroveň šifrování v prostředí, které obsahují klienty, kteří nepodporují 128bitové šifrování.  
  - *Nízká*: Nastavení Nízká šifruje jenom data odeslaných z klienta na server s využitím 56bitové šifrování.  
  
  Pokud zakážete nebo nenakonfigurujete toto nastavení, úrovně šifrování se použije pro připojení k serverům hostitele relace VP se vynucuje prostřednictvím zásad skupiny. Důležité kompatibilita se standardem FIPS, je možné nakonfigurovat pomocí kryptografický modul systému. Používat algoritmy odpovídající standardu FIPS pro šifrování, hašování a podpisování nastavení v zásadách skupiny (v počítači Konfigurace počítače\Nastavení systému Windows\Místní Policies\Security Options.) Kompatibilní se standardem FIPS nastavení šifruje a dešifruje data odesílaná z klienta na serveru a ze serveru klientovi s federální informace o zpracování Standard (FIPS) 140 šifrovací algoritmy, a používá kryptografické moduly Microsoftu. Používejte tuto úroveň šifrování komunikace mezi klienty a servery hostitele relace VP vyžaduje nejvyšší úroveň šifrování.
  - **Výchozí**: Vysoká
  
## <a name="remote-management"></a>Vzdálená správa  
Další informace najdete v tématu [zásady CSP – RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) v dokumentaci k Windows.  

- **Blokování ukládání spustit jako přihlašovací údaje**  
  Základní ověřování klienta
  - **Výchozí**: Povoleno
  
- **Základní ověřování**  
  Nastavení této zásady umožňuje určit, zda služba Vzdálená správa Windows (WinRM) přijme základní ověřování ze vzdáleného klienta. Pokud nastavení této zásady povolíte, Služba WinRM přijme základní ověřování ze vzdáleného klienta. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad služby WinRM nepřijímá základní ověřování ze vzdáleného klienta.
  - **Výchozí**: Zakázáno
  
- **Ověřování hodnotou hash bloku klienta**  
  Nastavení této zásady umožňuje určit, zda klient vzdálené správy Windows (WinRM) používá ověřování hodnotou hash. Pokud nastavení této zásady povolíte, Klient WinRM nepoužívá ověřování hodnotou hash. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, používá Klient WinRM ověřování hodnotou hash.
  - **Výchozí**: Povoleno
  
- **Ověřování hodnotou hash bloku klienta**  
  Nastavení této zásady umožňuje určit, zda služba Vzdálená správa Windows (WinRM) odesílá a přijímá nezašifrované zprávy přes síť. Pokud nastavení této zásady povolíte, Klient WinRM odesílá a přijímá nezašifrované zprávy přes síť. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, Klient WinRM odesílá nebo přijímá jenom šifrované zprávy přes síť.
  - **Výchozí**: Zakázáno
  
- **Ověřování hodnotou hash bloku klienta**  
  Nastavení zásad Ttento umožňuje určit, zda služba Vzdálená správa Windows (WinRM) odesílá a přijímá nezašifrované zprávy přes síť. Pokud nastavení této zásady povolíte, Klient WinRM odesílá a přijímá nezašifrované zprávy přes síť. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, Klient WinRM odesílá nebo přijímá jenom šifrované zprávy přes síť.
  - **Výchozí**: Zakázáno
  
- **Základní ověřování klienta**  
  Nastavení této zásady umožňuje určit, zda klient vzdálené správy Windows (WinRM) používá základní ověřování. Pokud nastavení této zásady povolíte, Klient WinRM používá základní ověřování. Pokud je Služba WinRM konfigurován pro použití přenos pomocí protokolu HTTP, uživatelského jména a hesla odešlou přes síť jako prostý text. Pokud zakážete nebo nenakonfigurujete toto nastavení zásad, nebude klient služby WinRM používat základní ověřování.
  - **Výchozí**: Zakázáno
  

## <a name="remote-procedure-call"></a>Vzdálené volání procedur  
Další informace najdete v tématu [zásady CSP – RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) v dokumentaci k Windows.  

- **Možnosti klienta vzdáleného volání Procedur nebyl ověřen**  
  Toto nastavení zásady řídí způsob, jakým modul runtime serveru RPC zpracovává neověřené klienty vzdáleného volání Procedur připojení k serverům RPC. Toto nastavení zásad má vliv na všechny aplikace RPC. V prostředí domény, toto nastavení zásad by měla sloužit opatrně, protože můžou ovlivnit širokou škálu funkcí, včetně samotného zpracování zásad skupiny. Návrat ke změně nastavení této zásady může vyžadovat ruční zásahy, na každý napadeného počítače. Nastavení této zásady nikdy použito k řadiči domény. Pokud nastavení této zásady zakážete, modul runtime serveru RPC používá hodnotu "Authenticated" na klientovi Windows a hodnota "None" ve verzích Windows serveru, které podporují tuto zásadu. Pokud nastavení této zásady nenakonfigurujete, zůstane zakázaná. Modul runtime serveru RPC se bude chovat, jako by byl povolen s hodnotou "Authenticated" používá se pro klienta Windows a hodnota "None" použít Server skladová jednotka, která podporuje nastavení této zásady. Pokud nastavení této zásady povolíte, bude směrovat modul runtime serveru RPC pro omezení neověřené RPC klienti připojení k vzdálené volání Procedur servery spuštěné na počítači. Klient se považuje za ověřený klient, pokud pojmenovaný kanál používá ke komunikaci se serverem nebo pokud používá zabezpečení protokolu RPC. Rozhraní RPC, který požádaly konkrétně přístupný neověřené klienty může být z tohoto omezení, v závislosti na vybrané hodnoty pro nastavení této zásady vyloučit.  
  - *Žádný* umožní všem klientům RPC pro připojení k serverům RPC spuštěné na počítači, na které nastavení zásad se použije. 
  - *Ověření* umožňuje pouze ověřeným RPC klientů (na výše uvedená definice) pro připojení k serverům RPC spuštěné na počítači, na které nastavení zásad se použije. Výjimky jsou udělena rozhraní, které si vyžádali. 
  - *Ověření bez výjimky* umožňuje pouze ověřeným RPC klientů (na výše uvedená definice) pro připojení k serverům RPC spuštěné na počítači, na které nastavení zásad se použije. Jsou povoleny žádné výjimky. Poznámka: Toto nastavení zásad se projeví až po restartování systému.  

  - **Výchozí**: Ověření

## <a name="search"></a>Search 
Další informace najdete v tématu [zásady CSP – hledání](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) v dokumentaci k Windows.  

- **Zakázání indexování šifrované položky**  
  Tato zásada povolí nebo zakáže indexování položek. Tento přepínač je pro Windows Search indexerem a určuje, zda se budou indexovat šifrované, jako jsou soubory Windows Information Protection (WIP) chráněné položky. Pokud je tato zásada povolená, chráněné položky WIP se indexují a metadata o nich se ukládají do nešifrovaného umístění. Součástí metadat jsou takové položky jako cesta k souboru a datum změny. Pokud je tato zásada zakázaná, chráněné položky WIP se neindexují a ve výsledcích v Cortaně nebo v Průzkumníkovi souborů se nezobrazují. Může to mít také dopad na výkon na fotky a Groove aplikace, pokud existuje celá řada možných WIP chráněné soubory médií v zařízení.
  - **Výchozí**: Ano
  
## <a name="smart-screen"></a>SmartScreen  
Další informace najdete v tématu [zásady CSP – SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) v dokumentaci k Windows.  

- **Zablokovat spuštění neověřených souborů**  
  Brání uživateli ve spuštění neověřených souborů. 0 – zaměstnanci můžou ignorovat upozornění filtru SmartScreen a spouštět škodlivé soubory. 1 – zaměstnanci nelze ignorovat upozornění filtru SmartScreen a spouštět škodlivé soubory.
  - **Výchozí**: Ano

- **Blokovat stahování neověřených souborů**  
  Ve výchozím nastavení, Microsoft Edge umožňují uživatelům obejít (Ignorovat) upozornění filtru Windows Defender SmartScreen na potenciálně škodlivých souborů, což jim umožní pokračovat ve stahování neověřených souborů. Když se tyto zásady zabrání uživatelům obejít upozornění, blokování stahování neověřených souborů.
  - **Výchozí**: Ano
  
- **Vyžadovat SmartScreen pro aplikace a soubory**  
  Umožňuje správcům IT Konfigurovat filtr SmartScreen pro Windows.
  - **Výchozí**: Ano
  
## <a name="system"></a>Systém  
Další informace najdete v tématu [zásady CSP – systém](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) v dokumentaci k Windows.  

- **Inicializace ovladače start spuštění systému**  
  Nastavení této zásady umožňuje zadat spouštění ovladače, které jsou inicializovány podle klasifikace určené ovladači Antimalware prvotního spuštění Elam spouštění. Antimalware prvotního spuštění Elam spouštění ovladač může vrátit následující klasifikace pro každý ovladač spouštění: - kvalitní: Ovladač byl podepsán a nebylo manipulováno.  
  - *Chybný* -ovladač má byly identifikovány jako malware. Doporučuje se zakázat známé chybné ovladače mají být inicializovány. -Chybný, ale vyžaduje pro spuštění: Ovladač byl identifikován jako malware, ale počítač nelze bez načtení tento ovladač úspěšně spustil. 
  - *Neznámý* -tento ovladač nebyla ověřena k aplikací detekce malwaru a ještě nebyl klasifikován ovladačem Antimalware prvotního spuštění Elam spouštění.  

  Pokud nastavení této zásady povolíte, budou moct zvolit spouštění ovladače, které k inicializaci při příštím spuštění počítače. Pokud zakážete nebo nakonfigurujete tuto zásadu nastavení, ovladače pro zahájení spouštění, jestli se má být funkční, neznámý nebo chybný ale spouštěcí kritické jsou inicializovány a inicializace ovladače určena jako chybný se přeskočila. Pokud vaše aplikace detekce malwaru neobsahuje ovladači Antimalware prvotního spuštění Elam spouštění nebo ovladač spouštění Antimalware prvotního spuštění Elam bylo zakázáno, toto nastavení nemá žádný vliv a inicializací všech spouštění ovladačů.  
  - **Výchozí**: Dobré neznámé a špatný kritické

## <a name="wi-fi"></a>Wi-Fi  
Další informace najdete v tématu [zásady CSP – Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) v dokumentaci k Windows.  

- **Wi-Fi**  
  Určuje, zda je na zařízení možné sdílení Internetu.
  - **Výchozí**: Ano  

- **Automaticky blokovat připojení k Wi-Fi hotspotům**  
  Povolí nebo zakáže zařízení automaticky se připojovat k Wi-Fi hotspotům.  
  - **Výchozí**: Ano  
  
## <a name="windows-connection-manager"></a>Správce připojení k Windows  
Další informace najdete v tématu [zásady CSP – WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) v dokumentaci k Windows.  

- **Blokovat připojení k doméně sítím**  
  Nastavení této zásady zabrání počítačům bránily v připojení k doménové síti i doméně na základě sítě ve stejnou dobu. Pokud nastavení této zásady je povoleno, počítač reaguje na pokusy o automatické a ruční síťové připojení podle následujících okolností: 
  - Pokusy o automatické připojení při počítači je již připojen k síti založené na doméně, všechny pokusy o automatické připojení k sítím nedoménové jsou zablokované. Když počítač je už připojený k síti založené na doméně, pokusy o automatické připojení k sítím založený na doméně jsou zablokované. 
  - Ruční připojení pokusy, kdy počítač je již připojen k buď doméně na základě sítě nebo sítě založené na doméně přes médium jiné než Ethernetu a uživatel se pokusí vytvořit připojení k další síti ručně v porušení těchto podmínek nastavení existující připojení k síti a ruční připojení je povoleno. Když počítač je již připojen k buď mimo doménu na základě sítě nebo sítě založené na doméně přes síť Ethernet a uživatel se pokusí vytvořit připojení k další síti ručně v rozporu s nastavením této zásady je existující připojení k síti Ethernet udržuje a pokus o ruční připojení je blokován.  

  Pokud nastavení této zásady není nakonfigurována nebo je zakázána, jsou povoleny počítačů současně připojit k doméně a doméně sítě.
  - **Výchozí**: Povoleno
  
## <a name="windows-defender"></a>Windows Defender  
Další informace najdete v tématu [zásady CSP – Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) v dokumentaci k Windows.  

- **Kontrolovat příchozí e-mailové zprávy**  
  Povolí nebo zakáže kontrolu e-mailu.
  - **Výchozí**: Ano  

- **Aplikace Office spusťte podřízený proces typ**  
  Aplikace Office nebudou moct vytvářet podřízené procesy. To zahrnuje Word, Excel, PowerPoint, OneNote a přístup. Toto je chování typické malware, hlavně pro útoky – makro, které se snaží používat aplikace Office spouštět ani se stahování škodlivého spustitelné soubory.
  - **Výchozí**: Zablokovat
  
- **Typ souhlasu odeslání vzorku defenderu**  
  Kontroly pro uživatele souhlas úrovni v programu Windows Defender odesílat data. Pokud již bylo uděleno vyžaduje souhlas, program Windows Defender odešle je. V opačném případě (a pokud uživatel zadal nikdy se zeptat), požádejte ho o souhlas uživatele (Pokud je povoleno Defender/AllowCloudProtection) před odesláním údajů se spustí uživatelské rozhraní.
  - **Výchozí**: Posílat bezpečné vzorky automaticky 
  
- **Interval aktualizace podpisu (v hodinách)**  
  Interval aktualizace podpisu Defender v hodinách
  - **Výchozí**: 4
  
- **Skript se stáhne typ spuštění datové části**  
  Defender skript stáhne typ spuštění datové části
  - **Výchozí**: Zablokovat
  
- **Zabránit typ zcizování přihlašovacích údajů**  
  Windows Defender Credential Guard používá zabezpečení založené na virtualizaci k izolování tajných kódů tak, aby k nim měli přístup pouze oprávněný systémový software. Neoprávněný přístup k těmto tajným kódům může vést k útokům využívajícím krádež přihlašovacích údajů, jako je například Pass-the-Hash nebo Pass-The-Ticket. Windows Defender Credential Guard zabraňuje těmto útokům Díky ochraně hodnot hash hesel protokolů NTLM, lístků TGT protokolu Kerberos a přihlašovací údaje uložené aplikace jako přihlašovací údaje domény.
  - **Výchozí**: Povolení

- **Typ obsahu provádění e-mailu**  
  Toto pravidlo blokuje tomu nebudou tyto typy souborů, spuštění nebo spuštění z e-mailu v aplikaci Microsoft Outlook nebo webové pošty (například Gmail.com nebo Outlook.com): Spustitelný soubor, soubory (například .exe, .dll nebo .scr) skriptu (například PS prostředí PowerShell, VisualBasic .vbs nebo soubor .js JavaScript) archivní soubory skriptu.
  - **Výchozí**: Zablokovat
  
- **Typ ochrany sítě**  
  Tato zásada umožňuje zapnout ochranu sítě (bloku nebo auditu) nebo vypnout v systému Windows Defender Exploit Guard. Ochrana sítě je funkce Windows Defender ochrany Exploit Guard, která chrání zaměstnanci libovolnou aplikaci z podvodných přistupující, servery hostující zneužití a škodlivý obsah na Internetu. To zahrnuje, znemožní připojení k nebezpečné lokalit prohlížeče třetích stran. Typ hodnoty je celé číslo. Pokud povolíte toto nastavení, je zapnutá ochrana sítě a zaměstnanci nedá se zase vypnout. Její chování je řídit následující možnosti: Blok a auditu. Pokud povolíte tuto zásadu s parametrem "Blok", uživatele nebo aplikace se zablokují bránily v připojení k doménám nebezpečné. Budete moct zobrazit tuto aktivitu ve službě Windows Defender Security Center. Pokud povolíte tuto zásadu s parametrem "Auditu", nebude blokován uživatele/aplikace v připojení k doménám nebezpečné. Nicméně stále uvidíte této aktivity ve službě Windows Defender Security Center. Pokud tuto zásadu zakážete, nebude blokován uživatele/aplikace v připojení k doménám nebezpečné. Neuvidíte žádné síťové aktivity ve službě Windows Defender Security Center. Pokud tuto zásadu nenakonfigurujete, bude ve výchozím nastavení zakázán blokování sítě.
  - **Výchozí**: Povolení
  
- **Defender naplánovat den kontroly**  
  Naplánovat den kontroly Defender.
  - **Výchozí**: každý den
  
- **Cloudová ochrana**  
  Nejlepší chránit váš počítač, program Windows Defender vám zašleme informace společnosti Microsoft o všech problémech, které nalezne. Microsoft tyto informace analyzuje, další informace o problémy s vámi a další zákazníky a nabízet lepší řešení.
  - **Výchozí**:  Ano  

- **Defender potenciálně nežádoucí aplikace akce**  
  Funkce ochrany potenciálně nežádoucí aplikace (PUA) v antivirové ochrany v programu Windows Defender může identifikovat a ochraně zablokovat stahování a instalaci na koncových bodech vaší sítě. Tyto aplikace nejsou považovány za viry, malwaru nebo jiných typů hrozeb, ale může provádět akce na koncové body, které nepříznivě ovlivnit výkon nebo použít. PUA najdete také na aplikace, které jsou považovány za špatné pověst. Chování typické PUA zahrnuje: Software sdružování Ad injektáž do různých typů webových prohlížečů ovladač a registru nástroje, které rozpoznávání problémů, žádosti o platby a opravte chyby, ale zůstávají v koncovém bodě a provést žádné změny nebo optimalizace (označované také jako programy "podvodný antivirové ochrany v programu"), tyto aplikace může zvýšit riziko sítí infekce malwarem a způsobit, že napadení malwarem bude obtížnější k identifikaci a plýtvat IT prostředky v vymazání aplikace.  
  - **Výchozí**: Zablokovat  

- **Skript obfuskovaný kód typu – makro**  
  Před škodlivým softwarem a dalšími hrozbami můžete zkusit obfuskaci nebo skrytí jejich škodlivý kód v některé soubory skriptu. Toto pravidlo brání skripty, které se zdají být matoucí spouštění.
  - **Výchozí**: Zablokovat
  
- **Během úplné kontroly kontrolovat vyměnitelné jednotky**  
  Umožňuje programu Windows Defender můžete spustit kontrolu škodlivého a nežádoucí software na vyměnitelných jednotkách (například flash disky) při spuštění úplné kontroly. Antivirová ochrana v programu Windows Defender kontrolovat všechny soubory v zařízení USB před spuštěním.
  - **Výchozí**: Ano  
  
- **Prohledat archivní soubory**  
  Defenderu kontrolovat archivní soubory.
  - **Výchozí**: Ano
  
- **Monitorování chování**  
  Povolí nebo zakáže funkci monitorování chování Windows Defender. Vložený ve Windows 10, tyto senzory shromažďovat a zpracovávat chování signály od operačního systému a odešle tato data ze senzorů do privátního izolovaného, cloudu instance ochrany ATP v programu Windows Defender.
  - **Výchozí**: Ano

- **Kontrolovat soubory otevřené ze síťových složek**  
  Pokud jsou soubory jen pro čtení, uživatel nebude moct odebrat žádný zjištěný malware.
  - **Výchozí**: Ano

- **Typ procesu nedůvěryhodné USB**  
  S tímto pravidlem můžou správci bránit spouštění z vyměnitelné jednotky USB, včetně karet SD bez znaménka nebo nedůvěryhodné spustitelné soubory.
  - **Výchozí**: Zablokovat
  
- **Aplikace Office jiných zpracovat typ vkládání**  
  Aplikace Office, Word, Excel, PowerPoint a OneNote, včetně nebude možné vloží kód do jiných procesů. To se obvykle používá malware spustit škodlivý kód ve snaze skrýt aktivita z antivirového prověřovacích modulů.
  - **Výchozí**:  Zablokovat
  
- **Povolit typ importy Win32 kódu maker v Office**  
  Malware můžete použít kódu maker v souborech Office pro import a načíst dll Win32, které lze použít k volání rozhraní API umožňující další infekce v celém systému. Toto pravidlo se pokusí zablokovat soubory Office, které obsahují kód makra, které podporují import knihoven DLL Win32. To zahrnuje Word, Excel, PowerPoint a OneNote.
  - **Výchozí**: Zablokovat  
  
- **Defender cloudu blok úroveň**  
  Defender cloudu blok úroveň.
  - **Výchozí**: Nenakonfigurováno

- **Monitorování v reálném čase**  
  Defender vyžaduje monitorování v reálném čase.
  - **Výchozí**: Ano
  
- **Office aplikace spustitelný soubor vytvoření nebo spuštění typ obsahu**  
  Toto pravidlo zaměřuje na typické chování používané podezřelé a škodlivý doplňky a skripty (rozšíření), které vytvářet nebo spouštět spustitelné soubory. Jde o techniku typické malware. Rozšíření se zablokuje použití podle aplikace Office. Obvykle tato rozšíření používat Windows Scripting Host (soubory WSH) ke spouštění skriptů, které zautomatizovat určité úlohy nebo poskytují uživatel vytvořil doplňkové funkce
  - **Výchozí**: Zablokovat

## <a name="windows-ink-workspace"></a>Pracovní prostor Windows Ink  
Další informace najdete v tématu [zásady CSP – WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) v dokumentaci k Windows.  

- **Pracovní prostor Ink**  
  Určuje, jestli smí uživatel pro přístup k pracovnímu prostoru ink. 0 – je zakázán přístup k pracovní prostor ink. Tato funkce je vypnuta. 1 - ink pracovní prostor povolený (funkce je zapnutá), ale uživatel nemůže přejít nad zamykací obrazovkou. 2 (výchozí) – pracovní prostor ink povolený (funkce je zapnutá) a uživatel může používat nad zamykací obrazovkou.
  - **Výchozí**: Povoleno
 
## <a name="windows-powershell"></a>Windows PowerShell  
Další informace najdete v tématu [zásady CSP – WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) v dokumentaci k Windows.  

- **Power shell skript prostředí blokovat protokolování**  
  Nastavení této zásady umožňuje protokolování veškerý vstup skriptu prostředí PowerShell do protokolu událostí Microsoft-Windows-PowerShell/Operational. Pokud nastavení této zásady povolíte, prostředí Windows PowerShell bude protokolovat zpracování příkazů, bloky skriptu, funkce a skripty – zda vyvolat interaktivně nebo prostřednictvím automatizace. Pokud nastavení této zásady zakážete, protokolování vstupu skriptu prostředí PowerShell je zakázáno. Pokud povolíte protokolování vyvolání blok skriptu, prostředí PowerShell také protokoluje události při vyvolání příkazu, blok skriptu, funkce nebo skriptu, spuštění nebo zastavení. Povolení protokolování vyvolání generuje k velkému počtu protokoly událostí. Poznámka: Toto nastavení zásad existuje v rámci konfigurace počítače a konfigurace uživatele v editoru zásad skupiny. Nastavení zásad Konfigurace počítače má přednost před nastavením zásad Konfigurace uživatele.
  - **Výchozí**: Povoleno
 