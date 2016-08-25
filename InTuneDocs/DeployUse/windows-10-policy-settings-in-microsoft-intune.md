---
title: "Nastavení zásad pro Windows 10 | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
ms.sourcegitcommit: 1cccafa5f740bad50779ae36c899fd23ee7dc5f3
ms.openlocfilehash: 70347776f72a3534a4c384957aef01a909767b99


---

# Nastavení zásad pro Windows 10 v Microsoft Intune

Nastavení zásad, která jsou uvedena v tomto tématu, vám pomohou nakonfigurovat nastavení pro zaregistrované počítače s Windows 10 a zařízení Windows 10 Mobile.

## Obecná nastavení zásad konfigurace

Ke konfiguraci nastavení pro zaregistrovaná zařízení se systémem Windows 10 Desktop a Windows 10 Mobile použijte **obecné zásady konfigurace** služby Microsoft Intune pro Windows 10. Tyto zásady nejde použít, pokud spravujete počítače se systémem Windows 10 pomocí klientského softwaru Intune.


### Heslo

|Název nastavení|Podrobnosti|
|----------------|----------------------|
|**Vyžadovat heslo k odemknutí zařízení**|Vyžaduje heslo na podporovaných zařízeních.|
|**Vyžadovaný typ hesla**|Určuje typ hesla, které se bude vyžadovat, například jenom číslice nebo alfanumerické znaky.|
|**Vyžadovaný typ hesla** - **Minimální počet znakových sad**|Používají se čtyři znakové sady: malá písmena, velká písmena, číslice a symboly. Toto nastavení určuje, kolik různých znakových sad musí být v hesle zahrnutých.|
|**Minimální délka hesla**|Určuje minimální počet znaků, které musí mít heslo zařízení.<br>(jenom Windows 10 Mobile)|
|**Počet povolených opakovaných neúspěšných přihlášení, než bude zařízení vymazáno**|Vymaže zařízení, pokud tento počet pokusů o přihlášení selže.|
|**Počet minut nečinnosti před vypnutím displeje**|Určuje dobu, kterou musí být zařízení v nečinnosti, než se uzamkne jeho obrazovka.|
|**Omezená platnost hesla (ve dnech)**|Toto nastavení určuje dobu, po jejímž uplynutí je třeba změnit heslo k zařízení.|
|**Pamatovat si historii hesel**|Určuje, jestli chcete uživatelům zabránit ve vytváření hesel, která používali dřív.|
|**Pamatovat si historii hesel** - **Zabránit opětovnému použití předchozích hesel**|Určuje počet dříve použitých hesel, která se na zařízení zapamatovávají.|
|**Povolit obrázkové heslo a PIN**|Umožňuje použít pro přihlášení jednoduchá gesta na obrázku nebo jednoduchý PIN kód.<br>(jenom Windows 10 Desktop)|
|**Po návratu zařízení ze stavu nečinnosti vyžadovat heslo**|Pokud je povoleno, musí uživatel zadat heslo k odemknutí zařízení ze stavu nečinnosti.<br>(jenom Windows 10 Mobile)|

### Encryption

|Název nastavení|Podrobnosti|
|----------------|----------------------|
|**Vyžadovat šifrování u mobilního zařízení**|Povoluje šifrování na cílových zařízeních.<br>(jenom Windows 10 Mobile)|

### Systému

|Název nastavení|Podrobnosti|
|----------------|----------------------|
|**Povolit snímek obrazovky**|Umožňuje uživateli zachytit obrazovku zařízení v podobě obrázku.<br>(jenom Windows 10 Mobile)|
|**Povolit manuální zrušení zápisu**|Umožňuje uživateli ze zařízení ručně odstranit pracovní účet.|
|**Umožnit ruční instalaci kořenového certifikátu**|Určuje, jestli uživatel může ručně instalovat kořenové certifikáty.<br>(jenom Windows 10 Mobile)|
|**Povolit odesílání diagnostických dat a dat o použití do Microsoftu**|Určuje objem diagnostických dat a dat využití, který se odesílá společnosti Microsoft ze zařízení.<br><br>**Ne:** Microsoftu se neodešlou žádná data.<br>**Základní:** Zařízení odesílá Microsoftu jenom omezené množství informací.<br>**Rozšířené:** Odesílá Microsoftu rozšířená diagnostická data.<br>**Úplné (doporučeno):** Odešle stejná data jako možnost **Rozšířené** a k tomu navíc údaje o stavu zařízení.|


### Účet a synchronizace

|Název nastavení|Podrobnosti|
|----------------|----------------------|---------------------|
|**Povolit účet Microsoft**|Umožňuje uživateli přidružit k zařízení účet Microsoft.|
|**Povolit ruční přidávání jiných účtů, než jsou účty Microsoft**|Umožní uživateli přidat do zařízení e-mailové účty, které nejsou přidružené k účtu Microsoft.|
|**Povolit synchronizaci nastavení u účtů Microsoft**|Povolí synchronizaci nastavení zařízení a aplikací přidružených k účtu Microsoft mezi zařízeními.|

### Nastavení e-mailu

|Název nastavení|Podrobnosti|
|----------------|----------------------|---------------------|
|**Nastavit účet Microsoft jako volitelný v aplikaci Windows Pošta**|Nakonfigurováním této možnosti odeberete požadavek na používání účtu Microsoft v aplikaci Pošta Windows.<br>Jenom Windows 10 Desktop|



### Microsoft Edge

|Název nastavení|Podrobnosti|
|----------------|----------------------|
|**Povolit webový prohlížeč**|Umožňuje na zařízení používat webový prohlížeč Edge.<br>(jenom Windows 10 Mobile)|
|**Povolit návrhy vyhledávání v panelu Adresa**|Umožňuje, aby vám vyhledávací web při psaní hledaného textu navrhoval weby.|
|**Povolit odesílání intranetového provozu do Internet Exploreru**|Umožňuje uživatelům otevírat intranetové weby v Internet Exploreru.<br>(jenom Windows 10 Desktop)|
|**Povolit Do Not Track**|Nakonfiguruje prohlížeč Edge tak, aby se webům, které uživatelé navštíví, odesílaly hlavičky DNT (Do Not Track).|
|**Povolit SmartScreen**|Povoluje na zařízeních nastavení SmartScreen prohlížeče.|
|**Povolit aktivní skriptování**|Umožňuje, aby se v prohlížeči Edge mohly spustit skripty, například Javascripty.|
|**Povolit automaticky otevíraná okna**|Povolí nebo zakáže blokování automaticky otevíraných oken v prohlížeči.<br>(jenom Windows 10 Desktop)|
|**Povolit soubory cookie**|Povolí nebo zakáže soubory cookie.|
|**Povolit automatické vyplňování**|Umožňuje uživatelům změnit nastavení automatického dokončování v prohlížeči.<br>(jenom Windows 10 Desktop)|
|**Povolit správce hesel**|Umožňuje povolit nebo zakázat funkci Povolit správce hesel.|
|**Umístění webů podnikového režimu**|Určuje, kde najít seznam webů, které se otevřou v podnikovém režimu. Uživatelé nemohou tento seznam upravovat.<br>(jenom Windows 10 Desktop)|

### Aplikace

|Název nastavení|Podrobnosti|
|----------------|----------------------|---------------------|
|**Povolit obchod s aplikacemi**|Povolí uživatelům přístup do obchodu s aplikacemi na zařízení.<br>(jenom Windows 10 Mobile)|



### Mobilní služby

|Název nastavení|Podrobnosti|
|----------------|----------------------|---------------------|
|**Povolit datový roaming**|Povoluje roaming mezi sítěmi při přístupu k datům.|
|**Povolit VPN v mobilní síti**|Určuje, jestli zařízení může při připojení k mobilní síti získat přístup k připojením VPN.|
|**Povolit VPN v mobilní síti v roamingu**|Určuje, jestli zařízení může při roamingu v mobilní síti získat přístup k připojením VPN.|

### Hardware

|Název nastavení|Podrobnosti|
|----------------|----------------------|
|**Povolit fotoaparát**|Určuje, jestli je možné použít fotoaparát zařízení.|
|**Povolit vyměnitelné úložiště**|Určuje, jestli je možné se zařízením použít zařízení externího úložiště, jako jsou SD karty.|
|**Povolit Wi-Fi**|Umožňuje využívat možnosti Wi-Fi zařízení.<br>(jenom Windows 10 Mobile)|
|**Povolit sdílení internetu**|Povolí sdílení internetového připojení v zařízení.|
|**Povolit ruční konfiguraci připojení Wi-Fi**|Určuje, jestli může uživatel nakonfigurovat svoje vlastní Wi-Fi připojení nebo jestli může použít pouze připojení nakonfigurovaná v rámci profilu Wi-Fi sítě.<br>(jenom Windows 10 Mobile)|
|**Povolit automatické připojení k bezplatným Wi-Fi hotspotům**|Umožňuje zařízení automaticky se připojovat k volným Wi-Fi hotspotům a automaticky pro připojení přijímat jakékoli podmínky a ujednání.|
|**Povolit zeměpisnou polohu**|Určuje, jestli zařízení může používat informace služeb určování polohy.|
|**Povolit komunikaci NFC**|Umožňuje zařízení využívat jeho funkce NFC.|
|**Povolit Bluetooth**|Umožňuje na zařízení využívat možnosti Bluetooth.|
|**Povolit zjistitelný režim Bluetooth**|Umožňuje nastavit, aby bylo toto zařízení zjistitelné jinými zařízeními podporujícími technologii Bluetooth.|
|**Povolit reklamu přes Bluetooth**|Umožňuje zařízení přijímat reklamu přes Bluetooth.|
|**Povolit režim umožňující připojení k Bluetooth**|**Důležité:** Toto nastavení už Windows 10 nepodporuje a v budoucnu se odebere.|
|**Povolit obnovení továrního nastavení telefonu**|Určuje, jestli uživatel může na svém zařízení obnovit tovární nastavení.|
|**Povolit připojení USB**|Určuje, jestli má zařízení přístup k zařízením externího úložiště prostřednictvím připojení USB.|
|**Povolit režim AntiTheft**|Umožňuje nakonfigurovat, jestli má být povolený režim Windows Antitheft.|

### Funkce:

|Název nastavení|Podrobnosti|
|----------------|----------------------|---------------------|
|**Povolit kopírování a vkládání**|Povolí nebo zakáže na zařízení používání kopírování a vkládání.<br>(jenom Windows 10 Mobile)|
|**Povolit záznam hlasu**|Povolí nebo zakáže na zařízení funkce hlasového záznamu.<br>(jenom Windows 10 Mobile)|
|**Povolit Cortanu**|Povolí nebo zakáže hlasového asistenta Cortany.|
|**Povolit oznámení centra akcí**|Povolí nebo zakáže oznámení Centra akcí na zamykací obrazovce zařízení.<br>(jenom Windows 10 Mobile)|

### Defender

Všechna nastavení jsou jenom pro Windows 10 Desktop.

|Název nastavení|Podrobnosti|
|-|-|
|**Povolit monitorování v reálném čase**|Umožňuje v reálném čase zjišťovat v počítači existenci malwaru, spywaru a dalšího nežádoucího softwaru.|
|**Povolit monitorování chování**|Umožňuje programu Defender zjišťovat výskyt určitých známých vzorců podezřelých aktivit na zařízeních.|
|**Povolit systém kontroly sítě**|Systém kontroly sítě (NIS) pomáhá chránit zařízení před zneužitím prostřednictvím sítě, a to pomocí signatur známých chyb zabezpečení z konzoly Microsoft Endpoint Protection Center. Tímto způsobem dokáže detekovat a blokovat škodlivý přenos dat.|
|**Kontrolovat všechny stahované soubory**|Určuje, jestli bude Defender kontrolovat všechny soubory stahované z internetu.|
|**Povolit kontrolu skriptů**|Umožňuje programu Defender kontrolovat skripty, které se používají v Internet Exploreru.|
|**Monitorovat aktivitu souborů a programů**|Povolením tohoto nastavení můžete programu Defender umožnit monitorování aktivity souborů a programů v zařízení.|
|**Kolik dnů sledovat rozpoznaný malware**|Umožňuje programu Defender dál sledovat rozpoznaný malware po vámi určený počet dní, aby bylo možné ručně zkontrolovat dříve zasažená zařízení. Pokud nastavíte počet dnů **0**, malware zůstane ve složce karantény a automaticky se neodebere. |
|**Umožnit přístup k uživatelskému rozhraní klienta**|Určuje, jestli se bude koncovým uživatelům zobrazovat uživatelské rozhraní Windows Defenderu.<br>Pokud toto nastavení změníte, projeví se při příštím restartování počítače koncového uživatele.|
|**Naplánovat každodenní rychlou kontrolu**|Umožňuje vám naplánovat rychlou kontrolu, ke kterému dochází denně v době, kterou vyberete.|
|**Naplánovat úplnou kontrolu**|Umožňuje naplánovat úplnou nebo rychlou systémovou kontrolu, která probíhá pravidelně v den a čas, který vyberete.|
|**Omezit využití procesoru při prověřování**|Umožňuje nastavit maximální procento využití procesoru, které je možné využívat k provádění kontrol (od **1** do **100**).|
|**Prohledat archivní soubory**|Umožňuje programu Defender zkontrolovat soubory archivu, jako jsou soubory Zip nebo Cab.|
|**Kontrolovat e-mailové zprávy**|Umožňuje programu Defender kontrolovat e-mailové zprávy při jejich doručování na zařízení.|
|**Kontrolovat vyměnitelné jednotky**|Umožňuje programu Defender kontrolovat vyměnitelné jednotky, jako jsou USB flash disky.|
|**Kontrolovat namapované síťové jednotky**|Umožňuje programu Defender kontrolovat soubory na namapované síťové jednotce.<br>Pokud jsou soubory na disku jen pro čtení, nebude z nich Defender schopen odebrat žádný malware, který v nich najde.|
|**Kontrolovat soubory otevřené ze síťových sdílených složek**|Umožňuje programu Defender zkontrolovat soubory na sdílených síťových jednotkách (například na těch, ke kterým se získává přístup pomocí cesty UNC).<br>Pokud jsou soubory na disku jen pro čtení, nebude z nich Defender schopen odebrat žádný malware, který v nich najde.|
|**Interval aktualizace signatur**|Zadejte interval, ve kterém bude Defender zjišťovat dostupnost nových souborů signatur.|
|**Povolit cloudovou ochranu**|Umožňuje službě Microsoft Active Protection Service povolit nebo blokovat příjem informací o činnosti malwaru ze zařízení, která spravujete. Tyto informace slouží k budoucímu vylepšování služby.|
|**Dotázat se uživatelů na odesílání vzorků**|Určuje, jestli se mají do Microsoftu automaticky odesílat soubory, které by mohly vyžadovat další analýzu, aby bylo určeno, zda jsou škodlivé.|
|**Detekce potenciálně nežádoucích aplikací**|Pomocí tohoto nastavení lze chránit zaregistrované stolní počítače s Windows před spuštěním softwaru, který Windows Defender klasifikuje jako potenciálně nežádoucí. Můžete nastavit ochranu před spuštěním těchto aplikací nebo pomocí režimu auditu upozornit, když se potenciálně nežádoucí aplikace nainstaluje.|
|**Soubory a složky, které mají být vyloučeny z kontroly a ochrany v reálném čase**|Umožňuje do seznamu vyloučení přidat soubory a složky, například **C:\Cesta** nebo **%ProgramFiles%\Cesta\název_souboru.exe**. Tyto soubory a složky nebudou zahrnuty do kontrol probíhajících v reálném čase ani do plánovaných kontrol.|
|**Vyloučit přípony souborů při použití prověřování nebo ochrany v reálném čase**|Umožňuje do seznamu vyloučení přidat přípony souborů, například **jpg** nebo **txt**. Soubory s těmito příponami nebudou zahrnuty do kontrol probíhajících v reálném čase ani do plánovaných kontrol.|
|**Vyloučit procesy při použití prověřování nebo ochrany v reálném čase**|Umožňuje do seznamu vyloučení přidat procesy typu **.exe**, **.com** nebo **.scr**. Tyto procesy nebudou zahrnuty do kontrol probíhajících v reálném čase ani do plánovaných kontrol.| 


### Nastavení aktualizací

|Název nastavení|Podrobnosti|
|----------------|---------------|
|**Povolit automatické aktualizace**|Toto nastavení povolte, pokud chcete povolit automatické aktualizace. Pak nakonfigurováním jedno z následujících nastavení můžete řídit chování aktualizací:<br /><br />**Upozornění na stahování**<br /><br />**Automaticky nainstalovat v době údržby**<br /><br />**Automaticky nainstalovat a restartovat v době údržby**<br /><br />**Automaticky nainstalovat a restartovat v plánovaném čase** **Poznámka:** Pokud je vybraná tato možnost, můžete také nakonfigurovat nastavení **Potlačit oznámení pro koncového uživatele** a **Definujte den instalace pro plánované aktualizace**.<br>(jenom Windows 10 Desktop)|

## Nastavení vlastních zásad
Pomocí **vlastní zásady konfigurace** Microsoft Intune systémů Windows 10 a Windows 10 Mobile nasaďte nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier), které se dá používat k ovládání funkcí na zařízeních s Windows 10 a Windows 10 Mobile. Jsou to standardní nastavení, která k ovládání funkcí zařízení používá spousta výrobců mobilních zařízení.

Díky této vlastnosti můžete nasadit nastavení Windows 10, která nejdou konfigurovat obecnými zásadami konfigurace Intune.



### Obecná nastavení vlastních zásad

|Název nastavení|Podrobnosti|
    |----------------|--------------------|
    |**Název**|Zadejte jedinečný název vlastní zásady, abyste ji mohli v konzole Intune snadno identifikovat.|
    |**Popis**|Zadejte popis, který zásadu vystihne, a uveďte jakékoli další důležité informace, které vám pomůžou zásadu najít.|

### Nastavení OMA-URI vlastních zásad

|Název nastavení|Podrobnosti|
    |--------|--------------------|
    |**Název nastavení**|Zadejte jedinečný název nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.|
    |**Popis nastavení**|Zadejte popis, který nastavení přehledně vystihne, a další důležité informace, které vám ho pomůžou najít.|
    |**Datový typ**|Vyberte datový typ, ve kterém toto nastavení OMA-URI určíte. Vybírejte z těchto možností:<br /><br />-   **Řetězec**<br />-   **Řetězec (XML)**<br />-   **Datum a čas**<br />-   **Celé číslo**<br />-   **Číslo s plovoucí desetinnou čárkou**<br />-   **Logická hodnota**|
    |**OMA-URI (rozlišuje velká a malá písmena)**|Zadejte OMA-URI, pro který chcete zadat nastavení.|
    |**Hodnota**|Zadejte hodnotu pro přidružení k OMA-URI, který jste zadali dřív.|


## Vlastní nastavení URI pro zařízení s Windows 10
Toto téma obsahuje seznam nastavení, která se dají konfigurovat pro zařízení s Windows 10 a Windows 10 Mobile ve **vlastních zásadách Microsoft Intune pro Windows 10**.

Pokud chcete používat vlastní zásadu URI Windows, musí se všechna zařízení zaregistrovat v Intune.

### Nastavení URI zásady

|Název zásady|Podrobnosti|
|---------------|------------|-----------|
|**​Povolit automatickou aktualizaci**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** - **5** (výchozí: **1**)|
|**Den plánované instalace**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Každý den (výchozí)<br>**1** – Neděle<br>**2** – Pondělí<br>**3** – Úterý<br>**4** – Středa<br>**5** – Čtvrtek<br>**6** – Pátek<br>**7** – Sobota|
|**Čas plánované instalace**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0**-**23** hodin (**0** je půlnoc) (výchozí: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Uživatel nemůže nastavovat časovač období odkladu hesla a hodnota je nastavená na „pokaždé“.<br>**1** – Uživatel může nastavovat časovač období odkladu hesla.|
|**Wi-Fi/AllowWiFi**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovolit **použití připojení Wi-Fi**<br>**1** – **Povolit použití připojení Wi-Fi**|
|**Wi-Fi/AllowInternetSharing**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovolit sdílení internetu<br>**1** – Povolit sdílení internetu (výchozí)|
|**Wi-Fi/AllowAutoConnectToWiFiSenseHotspots**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Wi-Fi/AllowManualWiFiConfiguration**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se žádné Wi-Fi připojení mimo těch zřízených v MDM.<br>**1** – Povoluje se přidávání nových SSID sítí nad rámec těch, které jsou už zřízené v MDM.|
|**Systém/AllowLocation**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**System/AllowTelemetry**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – nepovoluje se (nastavení pouze v Enterprise)<br>**1** – omezená<br>**2** – úplná (výchozí)<br>**3** – úplná plus diagnostické informace|
|**System/AllowExperimentation**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – nepovoluje se<br>**1** – pouze nastavení (výchozí)<br>**2** – nastavení a experimentování|
|**Security/AntiTheftMode**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – nepovolit režim Anti Theft<br>**1** – předvolba uživatele (výchozí)|
|**Connectivity/AllowUSBConnection**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**System/AllowUserToResetPhone**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Connectivity/AllowCellularDataRoaming**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Connectivity/AllowVPNOverCellular**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – VPN přes mobilní síť se nepovoluje.<br>**1** – VPN může použít jakékoli připojení, včetně mobilního.|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Connectivity/AllowBluetooth**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovolit uživateli zapnout Bluetooth.<br>**1** – Vyhrazeno. Uživatel můžete zapnout a konfigurovat Bluetooth (nepodporované ve Windows Phone 8.1 pro MDM, EAS, Windows 10 desktop a Windows 10 Mobile)<br>**2** – Povoleno. Uživatel můžete zapnout a nakonfigurovat Bluetooth (výchozí).|
|**Experience/AllowScreenCapture**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Experience/AllowTaskSwitcher**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Experience/AllowVoiceRecording**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Experience/AllowSyncMySettings**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovolit roaming<br>**1** – Povolit roaming (výchozí)|
|**Experience/AllowManualMDMUnenrollment**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Accounts/AllowMicrosoftAccountConnection**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Security/AllowManualRootCertificateInstallation**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Security/AllowAddProvisioningPackages**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Search/DisableBackoff**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** (výchozí)<br>**1**|
|**Search/PreventRemoteQueries**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0**<br>**1** (výchozí)|
|**Search/AllowUsingDiacritics**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br> **0** (výchozí)<br>**1**|
|**Search/AlwaysUseAutoLangDetection**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** (výchozí)<br>**1**|
|**Search/DisableRemovableDriveIndexing**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** (výchozí)<br>**1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0**<br>**1** (výchozí)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** (výchozí)<br>**1**|
|**Security/AllowRemoveProvisioningPackage**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Security/RequireProvisioningPackageSignature**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** (výchozí)<br>**1**|
|**AboveLock/AllowActionCenterNotifications**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**TextInput/AllowIMENetworkAccess**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovolit<br>Slovník Open Extended Dictionary je vypnutý.<br>Uživatel nemůže:<br>Přidat nový slovník Open Extended Dictionary<br /><br />Přidat nový soubor konfigurace integrace vyhledávání<br>Používat funkci kandidáta cloudu<br>Odesílat uživatelem registrované slovo<br>A dále:<br>Slovník Open Extended Dictionary, který se přidal před povolením této zásady, se nepoužije pro převod.<br>Soubor konfigurace integrace vyhledávání, který se nainstaloval před povolením této zásady, se nepoužije.<br>**1** – Povolit<br>Slovník Open Extended Dictionary se může přidat a používat jako výchozí. Také funkce integrace vyhledávání se dá používat ve výchozím nastavení.<br>Uživatel může:<br>Používat funkci kandidáta cloudu<br>Odesílat uživatelem registrované slovo|
|**TextInput/AllowIMELogging**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Protokolování neúspěšných převodů je vypnuté. Automaticky laděná data a historie vstupů se neukládá do souboru.<br>**1** – Protokolování neúspěšných převodů je zapnuté. Automaticky laděná data a historie vstupů se ukládají do souboru (výchozí).|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**TextInput/AllowJapaneseIVSCharacters**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**TextInput/AllowJapaneseUserDictionary**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nefiltrují se žádné znaky (výchozí).<br>**1** – Filtruje se všechno kromě znaků Shift JIS.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br /><br />**0** – Nefiltrují se žádné znaky (výchozí).<br>**1** – Filtruje se všechno kromě znaků JIS0208.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nefiltrují se žádné znaky (výchozí).<br>**1** – Filtruje se všechno kromě znaků JIS0208 nebo EUDC.|
|**TextInput/AllowInputPanel**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Bluetooth/AllowDiscoverableMode**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Bluetooth/AllowAdvertising**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Settings/AllowDataSense**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Settings/AllowVPN**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Settings/AllowWorkplace**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Settings/AllowDateTime**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Settings/AllowLanguage**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Settings/AllowRegion**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Settings/AllowSignInOptions**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Settings/AllowYourAccount**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Settings/AllowPowerSleep**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Settings/AllowAutoPlay**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Experience/AllowCortana**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Search/SafeSearchPermissions**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Striktní, největší filtrování obsahu pro dospělé<br>**1** – Střední, střední filtrování obsahu pro dospělé (platné výsledky vyhledávání se nebudou filtrovat – výchozí)|
|**Experience/AllowCopyPaste**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**Force Start Size**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Povolit změnu velikosti uživatelem (výchozí)<br>**1** – Vynutit režim v okně<br>**2** – Vynutit celoobrazovkový režim|
|**Update/RequireDeferUpgrade**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0**: Neodkládat upgrade (zůstat v CB – výchozí)<br>**1**: Povolit odložení aktualizací a upgradů (zařízení postupuje podle pravidel aktuální větve pro podnikání, CBB)<br /><br />Více informací najdete v následujících tématech:<br>[Úvod do údržby Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plán pro nasazení Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>(Desktop a Mobile)|**Popis:** Zásada umožňující odložení aktualizací softwaru až o 4 týdny<br /><br />**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br> **0**: Použít aktualizace okamžitě (výchozí)<br>**1**-**4**: Počet týdnů odložení aktualizací softwaru<br /><br />Více informací najdete v následujících tématech:<br>[Úvod do údržby Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plán pro nasazení Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>(Desktop a Mobile)|**Popis:** Zásada umožňující odložení upgradu funkcí až o 8 měsíců<br /><br />**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0**: Použít aktualizace okamžitě (výchozí)<br>**1**-**8**: Počet měsíců odložení upgradu funkcí<br /><br />Více informací najdete v následujících tématech:<br>[Úvod do údržby Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plán pro nasazení Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>(Desktop a Mobile)|**Popis:** Umožňuje počítači CBB zastavit přijímání aktualizací a upgradů až po dobu 5 týdnů. Tato možnost by měla být použitá v případě, že nastane problém s aktualizací.<br /><br />**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0**: Použít aktualizace okamžitě (výchozí)<br>**1**: Pozastavit aktualizace a upgrady (platnost po 5 týdnech vyprší)|

### Nastavení URI programu Windows Defender

|Název zásady|Podrobnosti|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**AllowBehaviorMonitoring**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**AllowIntrusionPreventionSystem**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**AllowIOAVProtection**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**AllowScriptScanning**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**AllowOnAccessProtection**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**RealTimeScanDirection**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Monitorovat všechny soubory (obousměrně – výchozí)<br>**1** – Monitorovat příchozí soubory<br>**2** – Monitorovat odchozí soubory|
|**DaysToRetainCleanedMalware**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** - **90** – Představuje dobu, po kterou se bude uchovávat malware.<br>**Výchozí hodnota:** **0** – Uchová složku karantény navždy, automaticky se neodstraní.|
|**AllowUserUIAccess**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**ScanParameter**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**1** – Rychlé prohledání (výchozí)<br>**2** – Úplné prohledání|
|**ScheduleScanDay**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Každý den (výchozí)<br>**1** – Pondělí<br>**2** – Úterý<br>**3** – Středa<br>**4** – Čtvrtek<br>**5** – Pátek<br>**6** – Sobota<br>**7** – Neděle<br>**8** – Prohledání není naplánované|
|**ScheduleScanTime**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – 12:00<br>**60** – 1:00<br>**120** – 2:00 (výchozí)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1381** – Časové období údržby|
|**ScheduleQuickScanTime**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br>**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – 12:00<br>**60** – 1:00<br>**120** – 2:00 (výchozí)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1380** – 23:00|
|**AVGCPULoadFactor**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty: 0** - **100** (výchozí: **50**)|
|**AllowArchiveScanning**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**AllowEmailScanning**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Datový typ:** Celé číslo<br>**Povolené hodnoty:**<br>**0** – Nepovoluje se (výchozí)<br>**1** – Povoluje se|
|**AllowFullScanRemovableDriveScanning**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se (výchozí)<br>**1** – Povoluje se|
|**AllowFullScanOnMappedNetworkDrives**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**AllowScanningNetworkFiles**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí) – poběží i v případě, že je zapnutý protokol RTP.|
|**SignatureUpdateInterval**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nekontrolovat signatury v intervalu<br>**1** – Kontrolovat signatury každou hodinu<br>**2** – Kontrolovat signatury každé 2 hodiny atd.<br>**24** – Kontrolovat signatury každý den<br>**Výchozí hodnota:** 8 – Kontrolovat signatury každých 8 hodin|
|**AllowCloudProtection**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Povoluje se (výchozí)|
|**SubmitSamplesConsent**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Vždycky se zeptat (výchozí)<br>**1** – Posílat bezpečné vzorky automaticky<br>**2** – Nikdy neposílat<br>**3** – Posílat všechny vzorky automaticky|
|**ExcludedExtensions**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Datový typ:** Řetězec<br /><br />**Povolené hodnoty:**<br>*&lt;seznam přípon oddělený středníkem&gt;* Např. **obj;lib**<br>**Výchozí:** Nevylučují se žádné přípony.|
|**ExcludedPaths**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Datový typ:** Řetězec<br /><br />**Povolené hodnoty:**<br /><br />*&lt;seznam cest oddělený středníkem&gt;*<br /><br />Příklad: **c:\test;c:\test1.exe**<br /><br />**Výchozí hodnota:** Nevylučují se žádné cesty.|
|**ExcludedProcesses**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Datový typ:** Řetězec<br /><br />**Povolené hodnoty:**<br>*&lt;seznam cest oddělený středníkem&gt;*<br>Příklad: **c:\test.exe;c:\test1.exe**<br>**Výchozí hodnota:** Nevylučují se žádné procesy.|

### Nastavení URI prohlížeče Edge

|Název zásady|Podrobnosti|
|---------------|------------|-----------|
|**Povolit prohlížeč**<br>(jenom Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Procházení je vypnuté.<br>**1** – Procházení je zapnuté (výchozí).|
|**AllowSearchSuggestionsinAddressBar**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nezobrazovat návrhy vyhledávání<br>**1** – Zobrazovat návrhy vyhledávání (výchozí)|
|**SendIntranetTraffictoInternetExplorer**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Zakázáno (otevřít intranetové servery v prohlížeči Edge)<br>**1**– Povoleno (otevřít intranetové servery v Internet Exploreru)|
|**Povolit Do Not Track**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Zakázáno (DNT se neodešle – výchozí)<br>**1** – Povoleno (odeslat DNT)|
|**Konfigurovat SmartScreen**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Nepovolit<br>**1** – Povolit (výchozí)|
|**Povolit automaticky otevíraná okna**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Blokovat automaticky otevíraná okna (výchozí)<br>**1** – Povolit automaticky otevíraná okna|
|**Povolit soubory cookie**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Neblokovat. povolit soubory cookie ze všech webů (výchozí)<br>**1** – Blokovat jenom soubory cookie třetích stran<br>**2** – Blokovat všechny soubory cookie|
|**Povolit uložení hesla**<br>(Desktop a Mobile)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Správce hesel je zakázaný. <br>**1** – Správce hesel je povolený (výchozí).|
|**Povolit automatické vyplňování**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Datový typ:** Celé číslo<br /><br />**Povolené hodnoty:**<br>**0** – Zakázáno (výchozí)<br>**1** – Povoleno|
|**Konfigurovat seznam webů podnikového režimu**<br>(jenom Desktop)|**Úplná cesta URI:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Datový typ:** Řetězec<br /><br />**Povolené hodnoty:<br>0** – Není nakonfigurováno<br>**1** – Použít seznam webů podnikového režimu prohlížeče IE, pokud je nakonfigurovaný (výchozí)<br>**2** – Určit umístění seznamu webů podnikového režimu|

### Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jun16_HO3-->


