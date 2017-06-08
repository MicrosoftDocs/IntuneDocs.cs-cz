---
title: "Nastavení omezení pro zařízení s Windows 10 v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 88910c6628bb356e4a757cbdb4cf63b0acf60040
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení pro zařízení Windows 10 a novější v Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="general"></a>Obecné
-     **Snímek obrazovky (jenom mobilní verze)** – Umožňuje uživateli zachytit obrazovku zařízení v podobě obrázku.
-     **Kopírování a vložení (jenom mobilní verze)** – Povolí akce kopírování a vkládání mezi aplikacemi na zařízení.
-     **Ruční zrušení zápisu** – Umožňuje uživateli ze zařízení ručně odstranit pracovní účet.
-     **Ruční instalace kořenového certifikátu (jenom mobilní verze)** – Zabrání uživateli v ruční instalaci kořenových certifikátů a zprostředkujících certifikátů CAP.
-     **Odeslání diagnostických dat** – Možné hodnoty jsou:
    -         **Žádné:** Do Microsoftu se nepošlou žádná data.
    -         **Základní:** Do Microsoftu se pošle omezené množství dat.
    -         **Rozšířené:** Do Microsoftu se pošlou rozšířená data pro diagnostiku.
    -         **Úplné:** Pošle stejná data jako možnost Rozšířené a k tomu navíc údaje o stavu zařízení.
-     **Kamera** – Povolí nebo zablokuje použití fotoaparátu v zařízení.
-     **Synchronizace souboru OneDrivu** – Zablokuje zařízení možnost synchronizovat soubory s OneDrivem.
-     **Vyměnitelné úložiště** – Určuje, jestli je možné se zařízením použít zařízení externího úložiště, jako jsou SD karty.
-     **Zeměpisná poloha** – Určuje, jestli zařízení může používat informace služeb určování polohy.
-     **Sdílení internetu** – Povolí používat sdílení internetového připojení na zařízení.
-     **Obnovení továrního nastavení telefonu** – Určuje, jestli uživatel může na svém zařízení obnovit tovární nastavení.
-     **Připojení USB (jenom mobilní zařízení)** – Určuje, jestli má zařízení přístup k zařízením externího úložiště prostřednictvím připojení USB.
-     **Režim AntiTheft (jenom mobilní verze)** – Umožňuje nakonfigurovat, jestli má být povolený režim Windows Antitheft.
-     **Oznámení centra akcí (jenom mobilní verze)** – Povolí nebo zakáže oznámení Centra akcí na zamykací obrazovce zařízení (jenom Windows 10 Mobile).
-     **Cortana** – Povolí nebo zakáže hlasovou asistentku Cortanu.
-     **Záznam hlasu (jenom mobilní verze)** – Povolí nebo zablokuje použití záznamu hlasu na zařízení.
-     **Změny nastavení napájení a režimu spánku (jenom desktopové verze)** – Zabrání koncovému uživateli ve změně nastavení napájení a režimu spánku na zařízení.
-     **Změny nastavení oblasti (jenom desktopové verze)** – Zabrání koncovému uživateli ve změně nastavení oblasti na zařízení.
-     **Změny nastavení oblasti (jenom desktopové verze)** – Zabrání uživateli ve změně nastavení jazyka na zařízení.
-     **Změny systémového času** – Zabrání koncovému uživateli ve změně data a času zařízení.
-     **Změny názvu zařízení** – Zabrání koncovému uživateli ve změně názvu zařízení.
-     **Přidávat zřizovací balíčky** – Blokuje agenta konfigurace modulu runtime, který instaluje zřizovací balíčky.
-     **Odebírat zřizovací balíčky** – Blokuje agenta konfigurace modulu runtime, který odebírá zřizovací balíčky.
-     **Zjišťování zařízení** – Zablokuje zjišťování zařízení jinými zařízeními.
-     **Přepínání úloh (jenom mobilní verze)** – Zablokuje přepínání úloh na zařízení.
-     **Chybový dialog SIM karty (jenom mobilní verze)** – Zablokuje zobrazování chybových zpráv na zařízení, pokud se nezjistí žádná SIM karta.


## <a name="password"></a>Heslo
-     **Heslo** – Vyžaduje, aby koncový uživatel zadal heslo pro přístup k zařízení.
    -     **Požadovaný typ hesla** – Určuje, jestli musí být heslo složené jen z čísel, nebo z čísel a písmen.
    -     **Minimální délka hesla** – Platí jenom pro Windows 10 Mobile.
    -     **Počet neúspěšných přihlášení před vymazáním obsahu zařízení** – Pro zařízení s Windows 10: Pokud má zařízení povolený nástroj BitLocker, přejde do režimu obnovení nástroje BitLocker v případě, že se nepodaří přihlásit v rámci určeného počtu pokusů. Pokud zařízení nemá povolený nástroj BitLocker, toto nastavení se na něho nevztahuje.
Pro zařízení s Windows 10: Jakmile se nepovede určený počet pokusů o přihlášení, zařízení bude vymazáno.
    -     **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka** – Určuje dobu, po kterou musí být zařízení v nečinnosti, než se zamkne obrazovka.
    -     **Konec platnosti hesla (dny)** – Určuje dobu, po jejímž uplynutí je třeba změnit heslo k zařízení.
    -     **Znemožnit opakované použití předchozích hesel** – Určuje počet dříve použitých hesel, která se na zařízení zapamatovávají.
    -     **Vyžadovat heslo při návratu zařízení ze stavu nečinnosti** – Určuje, že uživatel musí zadat heslo k odemknutí zařízení (jenom Windows 10 Mobile).
-     **Šifrování** – Povolí šifrování na cílových zařízeních (jenom Windows 10 Mobile).

## <a name="personalization"></a>Přizpůsobení

-     **Adresa URL obrázku na pozadí plochy (jenom desktopové verze)** – Určuje adresu URL obrázku ve formátu PNG, JPG nebo JPEG, který se použije jako tapeta v desktopových verzích Windows. Uživatelé ji nebudou moct změnit.

## <a name="locked-screen-experience"></a>Prostředí zamknuté obrazovky

-     **Adresa URL obrázku pro zamknutou obrazovku (jenom desktopové verze)** – Určuje adresu URL obrázku ve formátu PNG, JPG nebo JPEG, který se použije jako tapeta zamknuté obrazovky Windows. Uživatelé ji nebudou moct změnit.


## <a name="app-store"></a>App Store

-     **App Store (jenom mobilní verze)** – Povolí nebo zablokuje použití App Storu na zařízeních s Windows 10 Mobile.
-     **Automaticky aktualizovat aplikace ze Storu** – Povolí automatickou aktualizaci aplikací nainstalovaných z Windows Storu.
-     **Instalace důvěryhodné aplikace** – Povolí, aby se aplikace podepsané důvěryhodným certifikátem instalovaly bokem.
-     **Odemčení pro vývojáře** – Povolí nastavení pro vývojáře Windows, například možnost povolit koncovým uživatelům provádět změny aplikací nainstalovaných bokem.
-     **Sdílená data aplikací uživatele** – Povolí aplikacím sdílet data mezi různými uživateli na stejném zařízení.
-     **Použít pouze privátní úložiště** – Tuto možnost povolte, pokud chcete koncovým uživatelům povolit jenom stahování aplikací z vašeho privátního úložiště.
-     **Spuštění aplikace pocházející ze Storu** – Slouží k zákazu všech aplikací předinstalovaných na zařízení nebo stažených z Windows Storu.
-     **Nainstalovat data aplikací na systémový svazek** – Zabrání aplikacím ukládat data na systémový svazek zařízení.
-     **Nainstalovat aplikace na systémovou jednotku** – Zabrání aplikacím ukládat data na systémovou jednotku zařízení.
-     **Záznam ze hry (jenom desktopové verze)** – Umožňuje nakonfigurovat, zda jsou povolené záznam a vysílání z her.



## <a name="edge-browser"></a>Prohlížeč Edge
-     **Prohlížeč Microsoft Edge (jenom mobilní verze)** – Povolí používání webového prohlížeče Edge na zařízení.
-     **Filtr SmartScreen** – Povolí nebo zakáže filtr SmartScreen, který blokuje podvodné weby.
-     **Odesílat hlavičky Do Not Track** – Nakonfiguruje prohlížeč Edge tak, aby se webům, které uživatelé navštíví, posílaly hlavičky DNT (Do Not Track).
-     **Soubory cookie** – Umožní prohlížeči ukládat internetové soubory cookie do zařízení.
-     **JavaScript** – Umožní, aby se v prohlížeči Edge mohly spouštět skripty, třeba JavaScript.
-     **Automaticky otevíraná okna** – Blokuje automaticky otevíraná okna v prohlížeči (platí jenom pro Windows 10 Desktop).
-     **Návrhy hledání** – Umožní, aby vám vyhledávací web při psaní hledaného textu navrhoval weby.
-     **Odesílat intranetové přenosy do Internet Exploreru** – Umožňuje uživatelům otevírat intranetové weby v Internet Exploreru (jenom Windows 10 Desktop).
-     **Automatické vyplňování** – Umožňuje uživatelům měnit nastavení automatického dokončování v prohlížeči (jenom Windows 10 Desktop).
-     **Správce hesel** – Povolí nebo zakáže funkci Správce hesel v Edgi.
-     **Umístění seznamu webů využívajících Režim rozlehlé sítě** – Určuje, kde najít seznam webů, které se otevřou v podnikovém režimu rozlehlé sítě. Uživatelé nemohou tento seznam upravovat.<br>(jenom Windows 10 Desktop)
-     **Vývojářské nástroje** – Zabrání koncovému uživateli v otevření vývojářských nástrojů Edge.
-     **Rozšíření** – Povolí koncovému uživateli nainstalovat rozšíření Edge na zařízení.
-     **Procházení InPrivate** – Zabrání koncovému uživateli v otevírání relací procházení InPrivate.
-     **Adresa URL při prvním spuštění** – Umožňuje zadat adresu URL, kterou prohlížeč Edge otevře při svém prvním spuštění (jenom mobilní verze).
-     **Domovské stránky** – Umožňuje přidat seznam webů, které se budou používat jako domovské stránky v prohlížeči Edge (jenom desktopové verze).
-     **Blokovat přístup k značkám s informacemi** – Zabrání koncovému uživateli v přístupu ke stránce about:flags v Edgi, která obsahuje vývojářské a experimentální nastavení.
-     **Přepsání výzvy SmartScreen** – Povolí koncovému uživateli obejít upozornění filtru SmartScreen na potenciálně škodlivé weby.
-     **Přepsání výzvy SmartScreen pro soubory** – Povolí koncovému uživateli obejít upozornění filtru SmartScreen na stažení potenciálně škodlivých souborů.
-     **IP adresa LocalHost pro WebRtc** – Zablokuje zobrazení IP adresy LocalHost uživatele při telefonování pomocí protokolu WebRTC.
-     **Výchozí vyhledávací web** – Určuje výchozí vyhledávací web, který se má použít. Koncoví uživatelé mohou tuto hodnotu kdykoli změnit.

## <a name="search"></a>Hledat
- **Bezpečné vyhledávání (jenom mobilní verze)** – Řídí, jak Cortana filtruje ve výsledcích obsah pro dospělé. Můžete vybrat možnost **Striktní**, **Pokročilé** nebo povolit koncovým uživatelům, aby si zvolili vlastní nastavení.

## <a name="cloud-and-storage"></a>Cloud a úložiště
-     **Účet Microsoft** – Umožní uživateli přidružit k zařízení účet Microsoft.
-     **Jiný účet než účet Microsoft** – Umožní uživateli přidat do zařízení e-mailové účty, které nejsou přidružené k účtu Microsoft.
-     **Synchronizace nastavení pro účet Microsoft** – Povolí synchronizaci nastavení zařízení a aplikací přidružených k účtu Microsoft mezi zařízeními.

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení
-     **Datový roaming** – Povolí roaming mezi sítěmi při práci s daty.
-     **VPN přes mobilní síť** – Určuje, jestli zařízení může při připojení k mobilní síti získat přístup k připojením VPN.
-     **VPN v mobilní síti při roamingu** – Určuje, jestli zařízení může při roamingu v mobilní síti získat přístup k připojením VPN.
-     **Bluetooth** – Určuje, jestli uživatel může povolit a konfigurovat Bluetooth na zařízení.
-     **Zjistitelnost zařízení Bluetooth** – Umožní, aby bylo toto zařízení zjistitelné jinými zařízeními podporujícími Bluetooth.
-     **Reklama přes Bluetooth** – Umožní zařízení přijímat přes Bluetooth inzerci.
-     **Název zařízení Bluetooth** – Umožňuje zadat pro zařízení název Bluetooth.
-     **Bezkontaktní komunikace (NFC)** – Umožní uživateli povolit a konfigurovat na zařízení možnosti bezkontaktní komunikace.
-     **Wi-Fi** – Umožní uživateli povolit a konfigurovat Wi-Fi na zařízení (jenom Windows 10 Mobile).
-     **Automaticky se připojovat k Wi-Fi hotspotům** – Umožní zařízení automaticky se připojovat k volným Wi-Fi hotspotům a automaticky pro připojení přijímat jakékoli podmínky a ujednání.
-     **Ruční konfigurace Wi-Fi** – Určuje, jestli může uživatel nakonfigurovat svoje vlastní Wi-Fi připojení, nebo jestli může použít jenom připojení nakonfigurovaná v rámci profilu Wi-Fi sítě (jenom Windows 10 Mobile).
-     **Interval hledání Wi-Fi** – Umožňuje zadat, jak často mají zařízení vyhledávat Wi-Fi sítě.

## <a name="control-panel-and-settings"></a>Ovládací panely a nastavení

-     **Aplikace Nastavení** – Zablokuje přístup k aplikaci Nastavení Windows.
    -     **Systém** – Zablokuje přístup k systémové oblasti v aplikaci Nastavení.
    -     **Zařízení** – Zablokuje přístup k oblasti zařízení v aplikaci Nastavení.
    -     **Síť a internet** – Zablokuje přístup k oblasti sítě a internetu v aplikaci Nastavení.
    -     **Přizpůsobení** – Zablokuje přístup k oblasti přizpůsobení v aplikaci Nastavení.
    -     **Účty** – Zablokuje přístup k oblasti účtů v aplikaci Nastavení.
    -     **Čas a jazyk** – Zablokuje přístup k oblasti času a jazyka v aplikaci Nastavení.
    -     **Usnadnění přístupu** – Zablokuje přístup k oblasti usnadnění přístupu v aplikaci Nastavení.
    -     **Soukromí** – Zablokuje přístup k oblasti soukromí v aplikaci Nastavení.
    -     **Aktualizace a zabezpečení** – Zablokuje přístup k oblasti aktualizací a zabezpečení v aplikaci Nastavení.

## <a name="defender"></a>Defender

-     **Monitorování v reálném čase** – Umožní v reálném čase zjišťovat výskyt malwaru, spywaru a dalšího nežádoucího softwaru.
-     **Monitorování chování** – Umožní programu Defender zjišťovat na zařízeních výskyt určitých známých vzorců podezřelých aktivit.
-     **Systém kontroly sítě (NIS)** – Systém kontroly sítě (NIS) pomáhá chránit zařízení před zneužitím prostřednictvím sítě, a to pomocí signatur známých chyb zabezpečení z konzoly Microsoft Endpoint Protection Center. Tímto způsobem dokáže zjistit a blokovat nebezpečný přenos dat.
-     **Kontrolovat všechna stahování** – Určuje, jestli bude Defender kontrolovat všechny soubory stahované z internetu.
-     **Kontrolovat skripty načtené do webových prohlížečů Microsoftu** – Umožní Defenderu kontrolovat skripty, které se používají v Internet Exploreru.
-     **Přístup koncového uživatele k programu Defender** – Určuje, jestli se bude koncovým uživatelům zobrazovat uživatelské rozhraní Windows Defenderu.
Pokud toto nastavení změníte, projeví se při příštím restartování počítače koncového uživatele.
-     **Interval aktualizace podpisu (v hodinách)** – Zadejte interval, ve kterém bude Defender zjišťovat dostupnost nových souborů signatur.
-     **Monitorovat aktivity spojené se soubory a programy** – Umožní Defenderu monitorovat aktivitu souborů a programů v zařízeních.
-     **Počet dní před odstraněním malwaru v karanténě** – Umožní Defenderu dál sledovat rozpoznaný malware po vámi určený počet dní, aby bylo možné ručně zkontrolovat dříve zasažená zařízení. Pokud nastavíte počet dnů **0**, malware zůstane ve složce karantény a automaticky se neodebere.
-     **Limit využití procesoru při kontrole** – Umožňuje nastavit maximální procento využití procesoru, které je možné využívat k provádění kontrol (od **1** do **100**).
-     **Kontrolovat archivované soubory** – Umožní Defenderu kontrolovat archivované soubory, jako jsou soubory Zip nebo Cab.
-     **Kontrolovat příchozí e-mailové zprávy** – Umožní Defenderu kontrolovat e-mailové zprávy při jejich doručení na zařízení.
-     **Při spuštění úplné kontroly kontrolovat vyměnitelné jednotky** – Umožní Defenderu kontrolovat vyměnitelné jednotky, jako jsou jednotky USB Flash.
-     **Při spuštění úplné kontroly kontrolovat namapované síťové jednotky** – Umožní Defenderu kontrolovat soubory na namapovaných síťových jednotkách.<br>Pokud jsou soubory na disku jen pro čtení, nebude z nich Defender schopen odebrat žádný malware, který v nich najde.
-     **Kontrolovat soubory otevřené ze síťových složek** – Umožní Defenderu kontrolovat soubory na sdílených síťových jednotkách (například na těch, ke kterým se získává přístup pomocí cesty UNC).
Pokud jsou soubory na disku jen pro čtení, nebude z nich Defender schopen odebrat žádný malware, který v nich najde.
-     **Cloudová ochrana** – Umožňuje službě Microsoft Active Protection Service povolit nebo blokovat příjem informací o činnosti malwaru ze zařízení, která spravujete. Tyto informace slouží k budoucímu vylepšování služby.
-     **Dotázat se uživatele před odesláním vzorku** – Určuje, jestli se mají do Microsoftu automaticky posílat soubory, které by mohly vyžadovat další analýzu, aby se určilo, jestli jsou škodlivé.
-     **Čas, kdy se má provést rychlá denní kontrola** – Umožní vám naplánovat rychlou kontrolu, ke které dochází denně v době, kterou vyberete.
-     **Typ systémové kontroly, který se má provést** – Umožní vám určit úroveň prohledávání, které se provede v době, na kdy naplánujete systémovou kontrolu.

## <a name="defender-exclusions"></a>Výjimky Defenderu

-     **Soubory a složky, které chcete vyloučit z kontrol a ochrany v reálném čase** – Umožňuje do seznamu vyloučení přidat jeden nebo více souborů a složek, například **C:\Cesta** nebo **%ProgramFiles%\Cesta\název_souboru.exe**. Tyto soubory a složky nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.
-     **Přípony souborů, které chcete vyloučit z kontrol a ochrany v reálném čase** – Umožňuje přidat do seznamu vyloučení jednu nebo více přípon souborů jako **jpg** nebo **txt**. Soubory s těmito příponami nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.
-     **Procesy, které chcete vyloučit z kontrol a ochrany v reálném čase** – Umožňuje přidat do seznamu vyloučení jeden nebo více procesů typu **.exe**, **.com** nebo **.scr**. Tyto procesy nebudou zahrnuty do kontrol probíhajících v reálném čase ani do plánovaných kontrol.


## <a name="network-proxy"></a>Síťový proxy server

-     **Automaticky zjišťovat nastavení proxy serveru** – Pokud je tato možnost povolena, zařízení se pokusí vyhledat cestu ke skriptu PAC.
-     **Použít skript proxy serveru** – Tuto možnost vyberte, pokud chcete zadat cestu ke skriptům PAC a nakonfigurovat proxy server.
    -     **Nastavení adresy URL skriptu** – Zadejte adresu URL skriptu PAC, pomocí kterého chcete nakonfigurovat proxy server.
-     **Použít ruční proxy server** – Tuto možnost vyberte, pokud chcete informace o proxy serveru zadat ručně.
    -     **Adresa** – Zadejte název nebo IP adresu proxy serveru.
    -     **Číslo portu** – Zadejte číslo portu vašeho proxy serveru.
    -     **Výjimky proxy serveru** – Zadejte adresy URL, které nesmí používat proxy server. Jednotlivé položky oddělte středníkem.
    -     **Obejít proxy server pro místní adresy** – Tuto možnost povolte, pokud nechcete proxy server používat pro místní adresy na vašem intranetu.


## <a name="windows-spotlight"></a>Windows Spotlight

-     **Windows Spotlight** – Povolí nebo zablokuje Windows Spotlight poskytující funkce, jako jsou tipy a triky, zprávy na zamykací obrazovce Windows a další.
    -     **Tipy Windows** – Umožňuje zablokovat zobrazování automaticky otevíraných tipů ve Windows.
    -     **Uživatelské funkce** – Umožňuje zablokovat uživatelské funkce, jako jsou návrhy nabídky Start a oznámení o členství.

## <a name="display"></a>Zobrazit

- **Uživatelský vstup z přijímačů bezdrátového zobrazení** – Zablokuje uživatelský vstup z přijímačů bezdrátového zobrazení.
- **Promítání na tento počítač** – Zabrání ostatním zařízením, aby zjišťovala tento počítač pro promítání.
- **Při párování požadovat PIN kód** – Vyžaduje PIN kód při připojení k promítacímu zařízení.

## <a name="start"></a>Začátek

- **Odepínání aplikací z hlavního panelu** – Zabrání uživateli v odepínání aplikací z nabídky Start.
- **Dokumenty v nabídce Start** – Umožňuje skrýt nebo zobrazit složku Dokumenty v nabídce Windows Start.
- **Stažené soubory v nabídce Start** – Umožňuje skrýt nebo zobrazit složku Stažené soubory v nabídce Windows Start.
- **Průzkumník souborů v nabídce Start** – Umožňuje skrýt nebo zobrazit aplikaci Průzkumník souborů v nabídce Windows Start.
- **Domácí skupina v nabídce Start** – Umožňuje skrýt nebo zobrazit složku Domácí skupina v nabídce Windows Start.
- **Hudba v nabídce Start** – Umožňuje skrýt nebo zobrazit složku Hudba v nabídce Windows Start.
- **Síť v nabídce Start** – Umožňuje skrýt nebo zobrazit složku Síť v nabídce Windows Start.
- **Složka Osobní v nabídce Start** – Umožňuje skrýt nebo zobrazit složku Osobní v nabídce Windows Start.
- **Obrázky v nabídce Start** – Umožňuje skrýt nebo zobrazit složku s obrázky v nabídce Windows Start.
- **Nastavení v nabídce Start** – Umožňuje skrýt nebo zobrazit aplikaci Nastavení v nabídce Windows Start.
- **Videa v nabídce Start** – Umožňuje skrýt nebo zobrazit složku s videi v nabídce Windows Start.