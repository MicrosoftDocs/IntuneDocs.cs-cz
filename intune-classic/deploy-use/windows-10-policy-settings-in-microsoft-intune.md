---
title: "Nastavení zásad pro Windows 10"
description: "Nastavení zásad, která jsou uvedena v tomto tématu, vám pomůžou nakonfigurovat předdefinovaná a vlastní nastavení pro zaregistrované počítače s Windows 10 a zařízení Windows 10 Mobile."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1f19b7e9d57350f90baca96562a99b2fde66f91a
ms.sourcegitcommit: 00352501833818a08479758ba1c9efdf7223e264
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/05/2017
---
# <a name="intune-policy-settings-for-windows-10-devices-in-microsoft-intune"></a>Nastavení zásad Intune pro zařízení s Windows 10 v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Informace v tomto tématu vám pomůžou pochopit nastavení zásad Intune, které je možné použít ke správě zařízení s Windows 10. Přečtěte si toto téma i postupy uvedené v článku [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](/intune-classic/get-started/windows-pc-management-capabilities-in-microsoft-intune).

Můžete si vybrat ze dvou typů zásad:

- **Vlastní zásady**: **Vlastní zásady** Microsoft Intune pro Windows 10 a Windows 10 Mobile použijte, pokud chcete nasadit nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier), s jehož pomocí se dají ovládat funkce na zařízeních. Ve Windows 10 je přístupná řada nastavení CSP, například [poskytovatel konfiguračních služeb pro zásady (CSP pro zásady)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Obecné zásady konfigurace**: Tento typ zásad použijte, pokud chcete nastavení vybrat z předdefinovaného seznamu dodávaného s Microsoft Intune.

## <a name="custom-policy-settings"></a>Nastavení vlastních zásad

Při nastavování vlastních zásad zadejte následující údaje.

### <a name="general-settings"></a>Obecná nastavení

Zadejte název a volitelně i popis zásady, který vám pomůže při její identifikaci v konzole Intune.

### <a name="oma-uri-settings"></a>Nastavení OMA-URI

Ke každému nastavení OMA-URI, které chcete přidat, zadejte následující informace:

- **Název nastavení**: Zadejte jedinečný název nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení. Další informace o nastavení URI najdete v článku [Poskytovatel konfiguračních služeb pro zásady (CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Popis nastavení**: Volitelně zadejte popis nastavení.
- **Datový typ**: Zvolte z následujících datových typů:
    - **Řetězec**
    - **Řetězec (XML)**
    - **Datum a čas**
    - **Celé číslo**
    - **Číslo s plovoucí desetinnou čárkou**
    - **Logická hodnota**
- **OMA-URI (rozlišuje velká a malá písmena)**: Uveďte, který OMA-URI chcete nastavit.
- **Hodnota**: Zadejte hodnotu, která má být k uvedenému OMA-URI přidružena.

### <a name="example"></a>Příklad
Na následujícím snímku obrazovky je nastavení **Connectivity/AllowVPNOverCellular** povolené. To umožňuje zařízení s Windows 10 spustit připojení VPN přes mobilní síť.

> ![Příklad vlastní zásady, která obsahuje nastavení VPN](./media/custom-policy-example.png)

### <a name="how-to-find-the-policies-you-can-configure"></a>Jak najít zásady, které můžete nakonfigurovat

Úplný seznam všech poskytovatelů konfiguračních služeb (CSP), které systém Windows 10 podporuje, najdete v [referencích poskytovatelů konfiguračních služeb](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) v knihovně dokumentace systému Windows.

Ne všechna nastavení jsou kompatibilní se všemi verzemi Windows 10. V tabulce v tématu Windows zjistíte, které verze se pro jednotlivé CSP podporují.

Intune navíc nepodporuje všechna nastavení uvedená v tomto tématu. Pokud chcete zjistit, jestli Intune podporuje vámi požadované nastavení, otevřete si téma pro dané nastavení. Jednotlivé stránky nastavení zobrazují podporované operace. Aby dané nastavení fungovalo s Intune, musí podporovat operace **Přidat** nebo **Nahradit**.

## <a name="general-configuration-policy-settings"></a>Obecná nastavení zásad konfigurace

Ke konfiguraci nastavení pro zaregistrovaná zařízení se systémem Windows 10 Desktop a Windows 10 Mobile použijte **obecné zásady konfigurace** Microsoft Intune pro Windows 10.

### <a name="password"></a>Heslo

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|
|**Vyžadovat heslo k odemknutí zařízení**|-|
|**Vyžadovaný typ hesla**|Určuje, jestli musí být heslo složené z čísel a písmen, nebo jen z čísel.|
|**Vyžadovaný typ hesla** - **Minimální počet znakových sad**| Určuje, kolik znakových sad (malá písmena, velká písmena, číslice a symboly) musí heslo obsahovat.|
|**Minimální délka hesla**|Platí jen pro Windows 10 Mobile.|
|**Počet povolených opakovaných neúspěšných přihlášení, než se zařízení vymaže**|Pro zařízení s Windows 10: Pokud má zařízení povolený nástroj BitLocker, přejde do režimu obnovení nástroje BitLocker v případě, že se nepovede určený počet pokusů o přihlášení. Pokud zařízení nemá povolený nástroj BitLocker, toto nastavení se na něho nevztahuje.<br>Pro zařízení s Windows 10: Jakmile se nepovede určený počet pokusů o přihlášení, zařízení bude vymazáno.|
|**Počet minut nečinnosti před vypnutím displeje**|Určuje dobu, kterou musí být zařízení v nečinnosti, než se uzamkne jeho obrazovka.|
|**Vypršení platnosti hesla (dny)**|Toto nastavení určuje dobu, po jejímž uplynutí je třeba změnit heslo k zařízení.|
|**Pamatovat si historii hesel**|Určuje, jestli se má uživateli zabránit ve vytváření hesel, která používal dříve.|
|**Pamatovat si historii hesel** - **Zabránit opětovnému použití předchozích hesel**|Určuje počet dříve použitých hesel, která si zařízení pamatuje.|
|**Po návratu zařízení ze stavu nečinnosti vyžadovat heslo**|Určuje, že uživatel musí zadat heslo k odemknutí zařízení (jenom Windows 10 Mobile).|

### <a name="encryption"></a>Šifrování

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|
|**Vyžadovat šifrování u mobilního zařízení**|Povoluje šifrování na cílových zařízeních.<br>(jenom Windows 10 Mobile)|

### <a name="system"></a>Systému

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|
|**Povolit snímek obrazovky**|Umožňuje uživateli zachytit obrazovku zařízení v podobě obrázku (jenom Windows 10 mobile).|
|**Povolit manuální zrušení zápisu**|Umožňuje uživateli ze zařízení ručně odstranit pracovní účet.|
|**Umožnit ruční instalaci kořenového certifikátu**|Platí pro Windows 10 Mobile.|
|**Povolit odesílání diagnostických dat a dat o použití do Microsoftu**|Možné hodnoty:<br><br>**Ne:** Microsoftu se neodešlou žádná data.<br>**Základní:** Microsoftu se odešle omezené množství dat.<br>**Rozšířené:** Microsoftu se odešlou rozšířená data pro diagnostiku.<br>**Úplné (doporučeno):** Odešle stejná data jako možnost **Rozšířené** a k tomu navíc údaje o stavu zařízení.|


### <a name="account-and-synchronization"></a>Účet a synchronizace

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|---------------------|
|**Povolit účet Microsoft**|Umožňuje uživateli přidružit k zařízení účet Microsoft.|
|**Povolit ruční přidávání jiných účtů, než jsou účty Microsoft**|Umožní uživateli přidat do zařízení e-mailové účty, které nejsou přidružené k účtu Microsoft.|
|**Povolit synchronizaci nastavení u účtů Microsoft**|Povolí synchronizaci nastavení zařízení a aplikací přidružených k účtu Microsoft mezi zařízeními.|

### <a name="microsoft-edge"></a>Microsoft Edge

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|
|**Povolit webový prohlížeč**|Umožňuje na zařízení používat webový prohlížeč Edge.<br>(jenom Windows 10 Mobile)|
|**Povolit návrhy vyhledávání v panelu Adresa**|Umožňuje, aby vám vyhledávací web při psaní hledaného textu navrhoval weby.|
|**Povolit odesílání intranetového provozu do Internet Exploreru**|Umožňuje uživatelům otevírat intranetové weby v Internet Exploreru.<br>(jenom Windows 10 Desktop)|
|**Povolit Do Not Track**|Nakonfiguruje prohlížeč Microsoft tak, aby se webům, které uživatelé navštíví, odesílaly hlavičky DNT (Do Not Track).|
|**Povolit filtr SmartScreen**||
|**Povolit aktivní skriptování**|Umožňuje, aby se v prohlížeči Edge mohly spustit skripty, třeba JavaScript.|
|**Povolit automaticky otevíraná okna**|Platí jen pro Windows 10 Desktop|
|**Povolit soubory cookie**||
|**Povolit automatické vyplňování**|Umožňuje uživatelům změnit nastavení automatického dokončování v prohlížeči.<br>(jenom Windows 10 Desktop)|
|**Povolit správce hesel**|Umožňuje v Edgi povolit nebo zakázat funkci správce hesel.|
|**Umístění webů podnikového režimu**|Určuje, kde najít seznam webů, které se otevřou v podnikovém režimu. Uživatelé nemůžou tento seznam upravovat.<br>(jenom Windows 10 Desktop)|

### <a name="apps"></a>Aplikace

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|---------------------|
|**Povolit obchod s aplikacemi**|Platí jen pro Windows 10 Mobile.|



### <a name="cellular"></a>Mobilní služby

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|---------------------|
|**Povolit datový roaming**|Povoluje roaming mezi sítěmi při přístupu k datům.|
|**Povolit VPN v mobilní síti**|Určuje, jestli zařízení může při připojení k mobilní síti získat přístup k připojením VPN.|
|**Povolit VPN v mobilní síti v roamingu**|Určuje, jestli zařízení může při roamingu v mobilní síti získat přístup k připojením VPN.|

### <a name="hardware"></a>Hardware

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|
|**Povolit fotoaparát**|-|
|**Povolit vyměnitelné úložiště**|Určuje, jestli je možné se zařízením použít zařízení externího úložiště, jako jsou SD karty.|
|**Povolit Wi-Fi**|Platí jen pro Windows 10 Mobile.|
|**Povolit sdílení internetu**|Povoluje používat sdílení internetového připojení na zařízení.|
|**Povolit ruční konfiguraci připojení Wi-Fi**|Určuje, jestli může uživatel nakonfigurovat svoje vlastní Wi-Fi připojení, nebo jestli může použít jenom připojení nakonfigurovaná v rámci profilu Wi-Fi sítě.<br>(jenom Windows 10 Mobile)|
|**Povolit automatické připojení k bezplatným Wi-Fi hotspotům**|Umožňuje zařízení automaticky se připojovat k volným Wi-Fi hotspotům a automaticky pro připojení přijímat jakékoli podmínky a ujednání.|
|**Povolit zeměpisnou polohu**|Určuje, jestli zařízení může používat informace služeb určování polohy.|
|**Povolit komunikaci NFC**|Umožňuje zařízení využívat jeho funkce NFC.|
|**Povolit Bluetooth**|-|
|**Povolit zjistitelný režim Bluetooth**|Umožňuje nastavit, aby bylo toto zařízení zjistitelné jinými zařízeními podporujícími technologii Bluetooth.|
|**Povolit reklamu přes Bluetooth**|Umožňuje zařízení přijímat reklamu přes Bluetooth.|
|**Povolit obnovení továrního nastavení telefonu**|Určuje, jestli uživatel může na svém zařízení obnovit tovární nastavení.|
|**Povolit připojení USB**|Určuje, jestli má zařízení přístup k zařízením externího úložiště prostřednictvím připojení USB.|
|**Povolit režim AntiTheft**|Umožňuje nakonfigurovat, jestli má být povolený režim Windows AntiTheft.|

### <a name="features"></a>Funkce:

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|---------------------|
|**Povolit kopírování a vkládání**|Platí jen pro Windows 10 Mobile.|
|**Povolit záznam hlasu**|Platí jen pro Windows 10 Mobile.|
|**Povolit Cortanu**|Povolí nebo zakáže hlasového asistenta Cortany.|
|**Povolit oznámení centra akcí**|Povolí nebo zakáže oznámení Centra akcí na zamykací obrazovce zařízení.<br>(jenom Windows 10 Mobile)|

### <a name="windows-defender"></a>Windows Defender

Všechna nastavení jsou jenom pro Windows 10 Desktop.

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|---------------------|
|**Povolit monitorování v reálném čase**|Umožňuje v reálném čase zjišťovat výskyt malwaru, spywaru a dalšího nežádoucího softwaru.|
|**Povolit monitorování chování**|Umožňuje programu Defender zjišťovat výskyt určitých známých vzorců podezřelých aktivit na zařízeních.|
|**Povolit systém kontroly sítě**|Systém kontroly sítě (NIS) pomáhá chránit zařízení před zneužitím prostřednictvím sítě, a to pomocí signatur známých chyb zabezpečení z konzoly Microsoft Endpoint Protection Center. Tímto způsobem dokáže detekovat a blokovat nebezpečný přenos dat.|
|**Kontrolovat všechny stahované soubory**|Určuje, jestli má Defender kontrolovat všechny soubory stahované z internetu.|
|**Povolit kontrolu skriptů**|Umožňuje programu Defender kontrolovat skripty, které se používají v Internet Exploreru.|
|**Monitorovat aktivitu souborů a programů**|Umožňuje programu Defender monitorovat aktivitu souborů a programů v zařízení.|
|**Kolik dnů sledovat rozpoznaný malware**|Umožňuje programu Defender dál sledovat rozpoznaný malware po vámi určený počet dní, aby bylo možné ručně zkontrolovat dříve zasažená zařízení. Pokud nastavíte počet dnů **0**, malware zůstane ve složce karantény a automaticky se neodebere. |
|**Umožnit přístup k uživatelskému rozhraní klienta**|Určuje, jestli se bude uživatelům zobrazovat uživatelské rozhraní Windows Defenderu.<br>Pokud toto nastavení změníte, projeví se při příštím restartování počítače uživatele.|
|**Naplánovat každodenní rychlou kontrolu**|Umožňuje vám naplánovat rychlou kontrolu, ke které dochází denně v době, kterou vyberete.|
|**Naplánovat úplnou kontrolu**|Umožňuje naplánovat úplnou nebo rychlou systémovou kontrolu, která probíhá pravidelně v den a čas, který vyberete.|
|**Omezit využití procesoru při prověřování**|Umožňuje nastavit maximální procento využití procesoru, které je možné využívat k provádění kontrol (od **1** do **100**).|
|**Prohledat archivní soubory**|Umožňuje Defenderu zkontrolovat soubory archivu, jako jsou soubory Zip nebo Cab.|
|**Kontrolovat e-mailové zprávy**|Umožňuje programu Defender kontrolovat e-mailové zprávy při jejich doručení na zařízení.|
|**Kontrolovat vyměnitelné jednotky**|Umožňuje programu Defender kontrolovat vyměnitelné jednotky, jako jsou USB flash disky.|
|**Kontrolovat namapované síťové jednotky**|Umožňuje Defenderu kontrolovat soubory na namapované síťové jednotce.<br>Pokud jsou soubory na disku jen pro čtení, nebude z nich Defender schopen odebrat žádný malware, který v nich najde.|
|**Kontrolovat soubory otevřené ze síťových sdílených složek**|Umožňuje Defenderu zkontrolovat soubory na sdílených síťových jednotkách (například na těch, ke kterým se získává přístup pomocí cesty UNC).<br>Pokud jsou soubory na disku jen pro čtení, nebude z nich Defender schopen odebrat žádný malware, který v nich najde.|
|**Interval aktualizace signatur**|Určuje interval, ve kterém má Defender zjišťovat dostupnost nových souborů signatur.|
|**Povolit cloudovou ochranu**|Umožňuje službě Microsoft Active Protection Service povolit nebo blokovat příjem informací o činnosti malwaru ze zařízení, která spravujete. Tyto informace slouží k budoucímu vylepšování služby.|
|**Dotázat se uživatelů na odesílání vzorků**|Určuje, jestli se mají do Microsoftu automaticky odesílat soubory, které by mohly vyžadovat další analýzu, aby bylo určeno, jestli jsou škodlivé.|
|**Detekce potenciálně nežádoucích aplikací**|Chrání zaregistrovaná stolní zařízení s Windows před spuštěním softwaru, který Windows Defender klasifikuje jako potenciálně nežádoucí. Můžete nastavit ochranu před spuštěním těchto aplikací nebo pomocí režimu auditu upozornit, když se potenciálně nežádoucí aplikace nainstaluje.|
|**Soubory a složky, které mají být vyloučeny z kontroly a ochrany v reálném čase**|Umožňuje do seznamu vyloučení přidat soubory a složky, například **C:\Cesta** nebo **%ProgramFiles%\Cesta\název_souboru.exe**. Tyto soubory a složky nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.|
|**Vyloučit přípony souborů při použití prověřování nebo ochrany v reálném čase**|Umožňuje do seznamu vyloučení přidat přípony souborů, například **jpg** nebo **txt**. Soubory s těmito příponami nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.|
|**Vyloučit procesy při použití prověřování nebo ochrany v reálném čase**|Umožňuje do seznamu vyloučení přidat procesy typu **.exe**, **.com** nebo **.scr**. Tyto procesy nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.|


### <a name="updates"></a>Updates

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|---------------|
|**Povolit automatické aktualizace**|Povolí automatické aktualizace. Nakonfigurováním jednoho z následujících nastavení můžete řídit chování aktualizací:<br />**Upozornění na stahování**<br />**Automaticky nainstalovat v době údržby**<br />**Automaticky nainstalovat a restartovat v době údržby**<br />**Automaticky nainstalovat a restartovat v plánovaném čase**: Pokud je vybraná tato možnost, můžete také nakonfigurovat nastavení **Potlačit oznámení pro koncového uživatele** a **Definujte den instalace pro plánované aktualizace**.<br>(jenom Windows 10 Desktop)|
|**Povolit předběžné verze funkcí**|Umožňuje Microsoftu do zařízení nasadit předběžné funkce a nastavení do zařízení s Windows 10. Můžete vybrat, že se povolí jenom nastavení, nebo že se nainstalují všechny předběžné funkce a nastavení.|

### <a name="see-also"></a>Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
