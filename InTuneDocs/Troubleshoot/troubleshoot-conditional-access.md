---
title: "Řešení potíží s podmíněným přístupem | Dokumentace Microsoftu"
description: "Popisuje, co dělat, pokud se vašim uživatelům nedaří získat přístup k prostředkům prostřednictvím podmíněného přístupu Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: cc14d6a44b3dcb6234cc77cb463098a9d2f4c5b8
ms.lasthandoff: 04/14/2017


---

# <a name="troubleshoot-conditional-access"></a>Řešení potíží s podmíněným přístupem

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Obvykle se uživatel pokusí o přístup k e-mailu nebo ke službě SharePoint a obdrží výzvu k registraci. Prostřednictvím této výzvy přejde uživatele na portál společnosti.

Toto téma popisuje, co dělat, pokud se vašim uživatelům nedaří získat přístup k prostředkům prostřednictvím podmíněného přístupu Intune.


## <a name="the-basics-for-success-in-conditional-access"></a>Základní informace potřebné pro úspěšné využívání podmíněného přístupu

Aby bylo možné využívat podmíněný přístup, je třeba splnit následující podmínky:

-    Zařízení musí být spravované pomocí Intune.
-    Zařízení musí být zaregistrované v Azure Active Directory (AAD). Za normálních okolností se tato registrace provede automaticky během registrace v Intune.
-    Zařízení musí vyhovovat zásadám dodržování předpisů Intune, a to pro zařízení i pro uživatele tohoto zařízení.  Pokud neexistují žádné zásady dodržování předpisů, je registrace v Intune dostatečná.
-    V zařízení musí být aktivovaný protokol Exchange ActiveSync, pokud uživatel načítá e-mail prostřednictvím nativního poštovního klienta, a nikoli prostřednictvím aplikace Outlook.     K tomu dojde automaticky pro zařízení se systémy iOS, Windows Phone a Android nebo KNOX Standard.
-    Intune Exchange Connector by měl být správně nakonfigurovaný. Další informace najdete v tématu [Odstraňování potíží Exchange Connectoru v Microsoft Intune](troubleshoot-exchange-connector.md).

Tyto podmínky lze zobrazit pro každé zařízení v portálu pro správu Azure a v sestavě inventáře zařízení.

## <a name="enrollment-issues"></a>Problémy s registrací

 -  Zařízení není zaregistrované, takže registrace tento problém odstraní.
 -  Uživatel zařízení zaregistroval, ale připojení k pracovišti se nezdařilo. Uživatel by měl aktualizovat registraci z portálu společnosti.

## <a name="compliance-issues"></a>Problémy se shodou

 -  Zařízení nevyhovuje zásadám Intune. K běžným problémům patří požadavky na šifrování a heslo. Uživatel bude přesměrován na portál společnosti, kde může nakonfigurovat zařízení tak, aby vyhovovalo požadavkům.
 -  Registrace informací o shodě pro zařízení může trvat nějakou dobu. Počkejte několik minut a zkuste akci zopakovat.
 -  Pro zařízení s iOS:
     -   Existující e-mailový profil vytvořený uživatelem bude blokovat nasazení profilu Intune vytvořeného správcem. Tento problém je běžný, protože uživatelé s iOSem obvykle vytvoří e-mailový profil a potom se zaregistrují. Portál společnosti bude uživatele informovat o tom, že požadavky nejsou splněny kvůli ručně nakonfigurovanému e-mailovému profilu a vyzve uživatele k odebrání příslušného profilu. Uživatel by měl svůj e-mailový profil odebrat, aby bylo možné nasadit profil Intune. Chcete-li problémům zabránit, požádejte své uživatele, aby se zaregistrovali bez instalace e-mailového profilu a aby Intune povolili nasazení profilu.
     -     Zařízení s iOSem můžou uváznout ve stavu kontroly dodržování předpisů bránit uživateli v inicializaci jiné kontroly. Restartování Portálu společnosti může problém vyřešit a stav dodržování předpisů bude odrážet stav zařízení v Intune. Po shromáždění všech dat ze synchronizace zařízení je kontrola dodržování předpisů rychlá a trvá v průměru méně než půl sekundy.

        Obvyklým důvodem toho, že zařízení zůstanou v tomto stavu, jsou potíže s připojením ke službě nebo dlouhotrvající synchronizace.  Pokud potíže přetrvávají v různých síťových konfigurací (mobilní, Wi-Fi, VPN) i po restartech zařízení a po ověření, že zprostředkovatel SSP je v zařízení aktuální, obraťte se na podporu Microsoftu podle popisu v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

 - Zařízení s Androidem:
     - Některá zařízení s Androidem můžou působit jako zašifrovaná, ale aplikace Portál společnosti tato zařízení rozpozná jako nezašifrovaná. 
    
        -    Zařízení, která jsou v tomto stavu, vyžadují, aby uživatel nastavil bezpečné heslo pro spuštění. Uživateli se zobrazí oznámení aplikace Portál společnosti s výzvou k nastavení hesla pro spuštění zařízení. Po klepnutí na oznámení a potvrzení stávajícího PIN kódu nebo hesla zvolte na obrazovce **Zabezpečené spouštění** možnost **Požadovat PIN pro spuštění zařízení**. Pak v aplikaci Portál společnosti klepněte na tlačítko **Zkontrolovat dodržování předpisů** pro dané zařízení. Zařízení by se teď mělo rozpoznat jako zašifrované.
    
        -     Někteří výrobci zařízení používají k zašifrování svých zařízení místo tajného PIN kódu nastaveného uživatelem výchozí PIN. Intune považuje šifrování pomocí výchozího PIN kódu jako nezabezpečené, protože tato metoda šifrování dat na zařízení představuje riziko, pokud uživatelé se zlými úmysly mají fyzický přístup k danému zařízení. V případě tohoto problému zvažte použití [zásad ochrany aplikací](https://docs.microsoft.com/intune/deploy-use/azure-portal-for-microsoft-intune-mam-policies).

## <a name="policy-issues"></a>problémy se zásadami;

Když vytvoříte zásady dodržování předpisů a propojíte je se zásadami e-mailů, musí být obojí zásady nasazeny pro téhož uživatele. Buďte proto opatrní při plánování, které zásady skupiny budou nasazeny pro které skupiny. Uživatelé s jedinou použitou zásadou pravděpodobně zjistí, že jejich zařízení nevyhovují.


## <a name="exchange-activesync-issues"></a>Problémy protokolu Exchange ActiveSync

### <a name="compliant-android-device-gets-quarantine-notice"></a>Kompatibilní zařízení s Androidem obdrží oznámení o karanténě.
- Zařízení s Androidem, které je zaregistrované a vyhovující, může i přesto obdržet oznámení o karanténě při pokusu o přístup k podnikovým prostředkům. Před zvolením odkazu s textem **Začít** by uživatel měl ověřit, že při pokusu o přístup k prostředkům nebyl portál společnosti otevřený. Uživatelé by měli zavřít portál společnosti, znovu se pokusit o přístup k prostředkům a pak zvolit odkaz **Začít**.

### <a name="retired-device-continues-to-have-access"></a>Vyřazené zařízení má nadále přístup.
- Když používáte Exchange Online, může mít vyřazené zařízení stále přístup i několik hodin po vyřazení. Důvodem je skutečnost, že Exchange ukládá přístupová práva do mezipaměti na 6 hodin. Zvažte možnost použití jiných způsobů ochrany dat na vyřazených zařízení v tomto scénáři.

### <a name="device-is-compliant-and-registered-with-aad-but-still-blocked"></a>Zařízení je zaregistrované v AAD a vyhovuje předpisům, ale je pořád blokované.
- V některých případech je zřízení ID protokolu Exchange ActiveSync (EASID) v AAD zpožděné. Obvyklou příčinou tohoto problému je omezování, proto počkejte několik minut a zkuste akci zopakovat.

### <a name="device-blocked"></a>Zařízení je blokované.

Zařízení může mít zablokovaný podmíněný přístup bez přijetí aktivačního e-mailu.

- Existuje výchozí pravidlo Exchange, které dává zařízení do karantény nebo je blokuje? Pokud výchozí pravidlo blokuje zařízení nebo je dává do karantény, zařízení nebudou moct přijímat aktivační e-maily Exchange Connectoru. Jedná se o účel.
- Je účet pro oznámení správně nakonfigurovaný podle popisu v základní konfiguraci?
- Je zařízení přítomné v konzole pro správu Intune jako zařízení protokolu Exchange ActiveSync? Pokud ne, je pravděpodobné, že je zjišťování tohoto zařízení neúspěšné, pravděpodobně kvůli problémům synchronizace Exchange Connectoru. Podívejte se do části Server Exchange nezjistil zařízení s Exchange ActiveSync.
- Zkontrolujte v protokolech Exchange Connectoru aktivitu odesílání e-mailu a vyhledejte chyby. Příkladem hledaného příkazu je SendEmail z účtu pro oznámení na e-mailovou adresu uživatele.
- Než Exchange Connector začne blokovat zařízení, odešle aktivační e-mail. Pokud je zařízení offline, nemusí aktivační e-mail obdržet. Zkontrolujte, jestli e-mailový klient v zařízení přijímá e-maily pomocí operace Push, a ne Poll, protože to může také způsobit, že uživatel nedostane e-mail. Přepněte na Poll a zkontrolujte, jestli zařízení obdrží e-mail.

## <a name="non-compliant-device-not-blocked"></a>Zařízení nevyhovující předpisům není blokované.

Pokud narazíte na zařízení, které nevyhovuje předpisům, ale má nadále přístup, proveďte následující kroky.

- Zkontrolujte cílovou skupinu a skupinu pro vyloučení. Pokud uživatel není ve správné cílové skupině nebo je ve skupině pro vyloučení, nebude blokován. Vyhovování předpisům se kontroluje jenom u zařízení uživatelů, kteří jsou v cílové skupině.
- Zkontrolujte, že se zařízení zjišťuje. Směřuje Exchange Connector na CAS pro Exchange 2010, zatímco je uživatel na serveru Exchange 2013? V takovém případě pokud je výchozí pravidlo Exchange nastavené na povolení, i když je uživatel v cílové skupině, Intune nemůže vědět o připojení zařízení k Exchangi.
- Kontrola stavu existence a přístupu k zařízení v Exchangi:
    - Pokud chcete získat seznam všech mobilních zařízení pro poštovní schránku, použijte tuto rutinu PowerShellu: Get-ActiveSyncDeviceStatistics -mailbox mbx. Pokud zařízení není uvedené, pak nepřistupuje k Exchangi.
    - Pokud zařízení je uvedené, pomocí rutiny Get-CASmailbox -identity:’upn’ | fl získejte podrobné informace o jeho stavu přístupu a předejte tyto informace podpoře Microsoftu.

## <a name="before-you-open-a-support-ticket"></a>Než otevřete lístek podpory
Pokud tyto postupy pro řešení potíží problém nevyřeší, může vás podpora Microsoftu vyzvat k poskytnutí některých informací, jako jsou protokoly poštovní schránky aplikace OWA nebo protokoly Exchange Connectoru.

### <a name="collecting-owa-mailbox-logs"></a>Shromažďování protokolů poštovní schránky aplikace OWA

1. Přihlaste se prostřednictvím aplikace OWA a zvolte symbol nastavení (ozubené kolečko) vedle vašeho jména v pravém horním rohu.
2. Zvolte **Možnosti**
3. Ve sloupci na levé straně zvolte **Telefon** (může být uvedeno **Mobilní zařízení**).
4. V hlavní nabídce zvolte **Mobilní zařízení**.
5. V seznamu zvolte příslušné zařízení a pak zvolte **Spustit protokolování**.
6. Po zobrazení výzvy zvolte v místním dialogovém okně **Ano**.
7. Proveďte akci, která způsobila problém, abyste ho znovu vyvolali.
8. Počkejte jednu nebo dvě minuty, než přejděte zpátky na telefonní seznam v aplikaci OWA. Ověřte, že je váš telefon v seznamu vybraný, a pak z hlavní nabídky zvolte **Načíst protokol**.
9. Nyní byste měli od sebe sama obdržet e-mail s přílohou. Při otevření lístku podpory předejte obsah e-mailu podpoře společnosti Microsoft.

### <a name="exchange-connector-logs"></a>Protokoly Exchange Connectoru

#### <a name="general-log-information"></a>Obecné informace o protokolech
Pokud chcete zobrazit protokoly Exchange Connectoru, použijte nástroj Server Trace Viewer Tool (https://msdn.microsoft.com/library/ms732023(v=vs.110).aspx'). Tento nástroj vyžaduje, abyste si stáhli sadu Windows Server SDK.

>[!NOTE]
>Protokoly jsou umístěné v adresáři C:\ProgramData\Microsoft\Windows Intune Exchange Connector\Logs. Protokoly jsou obsažené v posloupnosti 30 souborů, začínající souborem *Connector0.log* a končící souborem *Connector29.log*. Protokoly přecházejí na další po nahromadění 10 MB dat v protokolu. Jakmile se protokoly dostanou k souboru Connector29, začnou zase od Connector0 a budou přepisovat předchozí soubory protokolu.

#### <a name="locating-sync-logs"></a>Vyhledání protokolů synchronizace

-    Vyhledejte v protokolech úplnou synchronizaci vyhledáním textu **full sync**. Začátek úplné synchronizace je označený tímto textem:

    „Handling command: Getting the mobile device list without a time filter (full sync) for <number> users“

    Konec protokolu úplné synchronizace vypadá takto:

    „Getting the mobile device list without a time filter (full sync) for 4 users completed successfully.“ Details: Inventory command result - Devices synced: 0 Commmand ID: commandIDGUID' Exchange health: 'Server health 'Name: 'PowerShellExchangeServer: <Name=název_poštovního_serveru>' Status: Connected','

-    Vyhledejte v protokolech rychlou (rozdílovou) synchronizaci vyhledáním textu **quick sync**.

##### <a name="exceptions-in-get-next-command"></a>Výjimky v příkazu Get next
Vyhledejte v protokolech Exchange Connectoru výjimky v **příkazu Get next** a poskytněte je podpoře Microsoftu.

#### <a name="verbose-logging"></a>Podrobné protokolování

Zapnutí podrobného protokolování:

1.    Otevřete konfigurační soubor trasování Exchange Connectoru. Soubor je v následujícím umístění: %ProgramData%\Microsoft\Windows Intune Exchange Connector\TracingConfiguration.xml.
2.    Vyhledejte TraceSourceLine s následujícím klíčem: OnPremisesExchangeConnectorService
3.    Změňte hodnotu uzlu **SourceLevel** z **Warning ActivityTracing** (výchozí) na **Verbose ActivityTracing**, jak je uvedeno dál.

    <TraceSourceLine>
          <Key xsi:type="xsd:string">OnPremisesExchangeConnectorService</Key>
          <Value xsi:type="TraceSource">
            <SourceLevel>All</SourceLevel>
            <Listeners>
              <Listener>
                <ListenerType>CircularTraceListener</ListenerType>
                <SourceLevel>Verbose ActivityTracing</SourceLevel>
                <FileSizeQuotaInBytes>10000000</FileSizeQuotaInBytes>
                <FileName>Microsoft\Windows Intune Exchange Connector\Logs\Connector.svclog</FileName>
                <FileQuota>30</FileQuota>
              </Listener>
            </Listeners>
          </Value>
    </TraceSourceLine>



### <a name="next-steps"></a>Další kroky
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

