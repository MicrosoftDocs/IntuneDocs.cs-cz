---
title: "Nastavení omezení pro zařízení s Windows 10 v Intune"
titlesuffix: Azure portal
description: "Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s Windows 10."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 903ba99a747689dd8882acedcb24fef2dd00a01d
ms.sourcegitcommit: af958afce3070a3044aafea490c8afc55301d9df
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení pro zařízení Windows 10 a novější v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Obecné
-   **Snímek obrazovky (jenom mobilní verze)** – Umožňuje uživateli zachytit obrazovku zařízení v podobě obrázku.
-   **Kopírování a vložení (jenom mobilní verze)** – Povolí akce kopírování a vkládání mezi aplikacemi na zařízení.
-   **Ruční zrušení zápisu** – Umožňuje uživateli ze zařízení ručně odstranit pracovní účet.
-   **Ruční instalace kořenového certifikátu (jenom mobilní verze)** – Zabrání uživateli v ruční instalaci kořenových certifikátů a zprostředkujících certifikátů CAP.
-   **Odeslání diagnostických dat** – Možné hodnoty jsou:
    - **Žádné** – Microsoftu se nepošlou žádná data.
    - **Základní** – Microsoftu se pošlou omezené informace.
    - **Rozšířené** – Microsoftu se pošlou rozšířená data pro diagnostiku.
    - **Úplné:** Pošle stejná data jako možnost Rozšířené a k tomu navíc údaje o stavu zařízení.
-   **Kamera** – Povolí nebo zablokuje použití fotoaparátu v zařízení.
-   **Synchronizace souboru OneDrivu** – Zablokuje zařízení možnost synchronizovat soubory s OneDrivem.
-   **Vyměnitelné úložiště** – Určuje, jestli je možné v zařízení používat externí úložiště, jako jsou karty SD.
-   **Zeměpisná poloha** – Určuje, jestli zařízení může používat informace služeb určování polohy.
-   **Sdílení internetu** – Povolí používat sdílení internetového připojení na zařízení.
-   **Obnovení továrního nastavení telefonu** – Určuje, jestli uživatel může na svém zařízení obnovit tovární nastavení.
-   **Připojení USB (jenom mobilní zařízení)** – Určuje, jestli má zařízení přístup k zařízením externího úložiště prostřednictvím připojení USB.
-   **Režim AntiTheft (jenom mobilní verze)** – Umožňuje nakonfigurovat, jestli má být povolený režim Windows Antitheft.
-   **Cortana** – Povolí nebo zakáže hlasovou asistentku Cortanu.
-   **Záznam hlasu (jenom mobilní verze)** – Povolí nebo zablokuje na zařízení použití hlasového záznamu.
-   **Změny názvu zařízení** – Zabrání koncovému uživateli ve změně názvu zařízení (jenom Windows 10 Mobile).
-   **Přidávat zřizovací balíčky** – Blokuje agenta konfigurace modulu runtime, který instaluje zřizovací balíčky.
-   **Odebírat zřizovací balíčky** – Blokuje agenta konfigurace modulu runtime, který odebírá zřizovací balíčky.
-   **Zjišťování zařízení** – Zablokuje zjišťování zařízení jinými zařízeními.
-   **Přepínání úloh (jenom mobilní verze)** – Zablokuje přepínání úloh na zařízení.
-   **Chybový dialog SIM karty (jenom mobilní verze)** – Zablokuje zobrazování chybových zpráv na zařízení, pokud se nezjistí žádná SIM karta.


## <a name="password"></a>Heslo
-   **Heslo** – Vyžaduje, aby koncový uživatel zadal heslo pro přístup k zařízení.
    -   **Požadovaný typ hesla** – Určuje, jestli musí být heslo složené jen z čísel, nebo z čísel a písmen.
    -   **Minimální délka hesla** – Platí jenom pro Windows 10 Mobile.
    -   **Počet neúspěšných přihlášení před vymazáním obsahu zařízení** – Pro zařízení s Windows 10: Pokud má zařízení povolený nástroj BitLocker, přejde do režimu obnovení nástroje BitLocker v případě, že se nepovede určený počet pokusů o přihlášení. Pokud zařízení nemá povolený nástroj BitLocker, toto nastavení se na něho nevztahuje.
Pro zařízení s Windows 10: Jakmile se nepovede určený počet pokusů o přihlášení, zařízení bude vymazáno.
    -   **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka** – Určuje dobu, po kterou musí být zařízení v nečinnosti, než se zamkne obrazovka.
    -   **Konec platnosti hesla (dny)** – Určuje dobu, po jejímž uplynutí je třeba změnit heslo k zařízení.
    -   **Znemožnit opakované použití předchozích hesel** – Určuje počet dříve použitých hesel, která se na zařízení zapamatovávají.
    -   **Vyžadovat heslo při návratu zařízení ze stavu nečinnosti (jenom mobilní verze)** – Určuje, že uživatel musí zadat heslo k odemknutí zařízení (jenom Windows 10 Mobile).
    -   **Jednoduchá hesla** – Umožňuje používat jednoduchá hesla, třeba 1111 nebo 1234. Toto nastavení také povolí obrázková hesla Windows (nebo je zablokuje).
-   **Šifrování** – Povoluje šifrování na cílových zařízeních.

## <a name="personalization"></a>Přizpůsobení

-   **Adresa URL obrázku na pozadí plochy (jenom desktopové verze)** – Určuje adresu URL obrázku ve formátu PNG, JPG nebo JPEG, který se použije jako tapeta na ploše Windows. Uživatelé ji nebudou moct změnit.

## <a name="privacy"></a>Ochrana osobních údajů

-   **Přizpůsobení vstupu** – Zakáže použití cloudových hlasových služeb pro Cortanu, diktování nebo aplikace z Microsoft Storu. Pokud tyto služby povolíte, může Microsoft kvůli vylepšení služby shromažďovat hlasová data.
-   **Automatické přijetí párování a výzev k udělení souhlasu uživatele s ochranou osobních údajů** – Umožňuje Windows u spuštěných aplikací automaticky potvrzovat zprávy o párování a ochraně osobních údajů.


## <a name="locked-screen-experience"></a>Prostředí zamknuté obrazovky


-   **Oznámení Centra akcí (jenom mobilní verze)** – Povolí zobrazovat oznámení centra akcí na zamykací obrazovce zařízení (jenom Windows 10 Mobile).
-   **Adresa URL obrázku pro zamknutou obrazovku (jenom desktopové verze)** – Určuje adresu URL obrázku ve formátu PNG, JPG nebo JPEG, který se použije jako tapeta zamknuté obrazovky Windows. Uživatelé ji nebudou moct změnit.
-   **Uživatelem konfigurovatelný časový limit obrazovky (jenom mobilní verze)** – Umožňuje uživatelům konfigurovat časový limit. 
-   **Cortana na zamknuté obrazovce (jenom stolní počítač)** – Nepovolí uživateli pracovat s Cortanou, když je na zařízení aktivovaná zamykací obrazovka (jenom Windows 10 Desktop).
-   **Informační zprávy na zamknuté obrazovce** – Blokuje zobrazení upozornění na zamykací obrazovce zařízení.
-   **Časový limit obrazovky (jenom mobilní verze)** – Určuje, za jak dlouho (v sekundách) po uzamčení se obrazovka vypne.



## <a name="app-store"></a>App Store

-   **App Store (jenom mobilní verze)** – Povolí nebo zablokuje použití App Storu na zařízeních s Windows 10 Mobile.
-   **Automaticky aktualizovat aplikace ze Storu** – Povolí automatickou aktualizaci aplikací nainstalovaných z Microsoft Storu.
-   **Instalace důvěryhodné aplikace** – Povolí, aby se aplikace podepsané důvěryhodným certifikátem instalovaly bokem.
-   **Odemčení pro vývojáře** – Povolí nastavení pro vývojáře Windows, například možnost povolit koncovým uživatelům provádět změny aplikací nainstalovaných bokem.
-   **Sdílená data aplikací uživatele** – Povolí aplikacím sdílet data mezi různými uživateli na stejném zařízení.
-   **Použít pouze privátní úložiště** – Tuto možnost povolte, pokud chcete koncovým uživatelům povolit jenom stahování aplikací z vašeho privátního úložiště.
-   **Spuštění aplikace pocházející ze Storu** – Slouží k zákazu všech aplikací předinstalovaných na zařízení nebo stažených z Microsoft Storu.
-   **Nainstalovat data aplikací na systémový svazek** – Zabrání aplikacím ukládat data na systémový svazek zařízení.
-   **Nainstalovat aplikace na systémovou jednotku** – Zabrání aplikacím ukládat data na systémovou jednotku zařízení.
-   **Záznam ze hry (jenom desktopové verze)** – Umožňuje nakonfigurovat, zda jsou povolené záznam a vysílání z her.
-   **Jen aplikace ze Storu** – Nakonfiguruje, jestli uživatelé můžou instalovat aplikace odjinud než z obchodu s aplikacemi.



## <a name="edge-browser"></a>Prohlížeč Edge

-   **Prohlížeč Microsoft Edge (jenom mobilní verze)** – Povolí používání webového prohlížeče Edge na zařízení.
-   **Rozevírání panelu Adresa (jenom stolní počítače)** – Tímto nastavením zastavíte Edge, aby v rozevíracím seznamu při psaní zobrazoval seznam návrhů. Pomůžete tím minimalizovat používanou šířku pásma sítě mezi Edgem a službami Microsoftu.
-   **Synchronizovat oblíbené položky mezi prohlížeči Microsoft (jenom stolní počítače)** – Umožňuje Windows synchronizovat oblíbené položky mezi Internet Explorerem a Edgem.
-   **Odesílat hlavičky Do Not Track** – Nakonfiguruje prohlížeč Edge tak, aby se webům, které uživatelé navštíví, posílaly hlavičky DNT (Do Not Track).
-   **Soubory cookie** – Umožní prohlížeči ukládat internetové soubory cookie do zařízení.
-   **JavaScript** – Umožní, aby se v prohlížeči Edge mohly spouštět skripty, třeba JavaScript.
-   **Automaticky otevíraná okna** – Blokuje automaticky otevíraná okna v prohlížeči (platí jenom pro Windows 10 Desktop).
-   **Návrhy hledání** – Umožní, aby vám vyhledávací web při psaní hledaného textu navrhoval weby.
-   **Odesílat intranetové přenosy do Internet Exploreru** – Umožňuje uživatelům otevírat intranetové weby v Internet Exploreru (jenom Windows 10 Desktop).
-   **Automatické vyplňování** – Umožňuje uživatelům měnit nastavení automatického dokončování v prohlížeči (jenom Windows 10 Desktop).
-   **Správce hesel** – Povolí nebo zakáže funkci Správce hesel v Edgi.
-   **Umístění seznamu webů využívajících Režim rozlehlé sítě** – Určuje, kde najít seznam webů, které se otevřou v podnikovém režimu rozlehlé sítě. Uživatelé nemohou tento seznam upravovat.<br>(jenom Windows 10 Desktop)
-   **Vývojářské nástroje** – Zabrání koncovému uživateli v otevření vývojářských nástrojů Edge.
-   **Rozšíření** – Povolí koncovému uživateli nainstalovat rozšíření Edge na zařízení.
-   **Procházení InPrivate** – Zabrání koncovému uživateli v otevírání relací procházení InPrivate.
-   **Zobrazit stránku prvního spuštění** – Zastaví zobrazování úvodní stránky při prvním spuštění Edge.
    -   **Adresa URL při prvním spuštění** – Určuje adresu URL stránky, která se uživateli zobrazí při prvním spuštění Edge (jenom Windows 10 Mobile).
-   **Domovské stránky** – Přidá seznam webů, které chcete v prohlížeči Edge použít jako domovské stránky (jenom desktopové verze).
-   **Změny domovské stránky** – Umožňuje uživatelům změnit počáteční stránky, které se zobrazí při otevření Edge. K vytvoření stránky nebo seznamu stránek, které se otevřou při spuštění Edge, použijte nastavení Domovské stránky.
-   **Blokovat přístup k značkám s informacemi** – Zabrání koncovému uživateli v přístupu ke stránce about:flags v Edgi, která obsahuje vývojářské a experimentální nastavení.
-   **IP adresa LocalHost pro WebRtc** – Zablokuje zobrazení IP adresy LocalHost uživatele při telefonování pomocí protokolu WebRTC.
-   **Výchozí vyhledávací web** – Určuje výchozí vyhledávací web, který se má použít. Koncoví uživatelé mohou tuto hodnotu kdykoli změnit.
-   **Vymazat údaje o procházení při ukončení** – Vymaže historii a údaje o procházení, když uživatel zavře Edge.
-   **Shromažďování dat pro živé dlaždice** – Zastaví ve Windows shromažďování informací pro živé dlaždice, když uživatelé v Edgi připnou web k nabídce Start.

## <a name="edge-browser-smartscreen"></a>SmartScreen prohlížeče Edge

-   **SmartScreen** – Povolí nebo zakáže filtr SmartScreen, který blokuje podvodné weby.
-   **Přepsání výzvy SmartScreen** – Povolí koncovému uživateli obejít upozornění filtru SmartScreen na potenciálně škodlivé weby.
-   **Přepsání výzvy SmartScreen pro soubory** – Povolí koncovému uživateli obejít upozornění filtru SmartScreen na stažení potenciálně škodlivých souborů.

## <a name="search"></a>Hledat
- **Bezpečné vyhledávání (jenom mobilní verze)** – Řídí, jak Cortana filtruje ve výsledcích obsah pro dospělé. Můžete vybrat možnost **Striktní**, **Pokročilé** nebo povolit koncovým uživatelům, aby si zvolili vlastní nastavení.

## <a name="cloud-and-storage"></a>Cloud a úložiště
-   **Účet Microsoft** – Umožní uživateli přidružit k zařízení účet Microsoft.
-   **Jiný účet než účet Microsoft** – Umožní uživateli přidat do zařízení e-mailové účty, které nejsou přidružené k účtu Microsoft.
-   **Synchronizace nastavení pro účet Microsoft** – Povolí synchronizaci nastavení zařízení a aplikací přidružených k účtu Microsoft mezi zařízeními.

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení

-   **Mobilní datový kanál** – Zakáže uživatelům používat data, třeba k procházení webu, když jsou připojeni k mobilní síti. 
-   **Datový roaming** – Povolí roaming mezi sítěmi při práci s daty.
-   **VPN přes mobilní síť** – Určuje, jestli zařízení může při připojení k mobilní síti získat přístup k připojením VPN.
-   **VPN v mobilní síti při roamingu** – Určuje, jestli zařízení může při roamingu v mobilní síti získat přístup k připojením VPN.
-   **Bluetooth** – Určuje, jestli uživatel může povolit a konfigurovat Bluetooth na zařízení.
-   **Zjistitelnost zařízení Bluetooth** – Umožní, aby bylo toto zařízení zjistitelné jinými zařízeními podporujícími Bluetooth.
-   **Párování Bluetooth předem** – Umožní automatické párování určitých zařízení Bluetooth se zařízením hostitele.
-   **Reklama přes Bluetooth** – Umožní zařízení přijímat přes Bluetooth inzerci.
-   **Služba připojených zařízení** – Umožní vybrat, jestli povolíte službu připojených zařízení, abyste mohli zjišťovat jiná zařízení Bluetooth a připojovat se k nim.
-   **Bezkontaktní komunikace (NFC)** – Umožní uživateli povolit a konfigurovat na zařízení možnosti bezkontaktní komunikace.
-   **Wi-Fi** – Umožní uživateli povolit a konfigurovat Wi-Fi na zařízení (jenom Windows 10 Mobile).
-   **Automaticky se připojovat k Wi-Fi hotspotům** – Umožní zařízení automaticky se připojovat k volným Wi-Fi hotspotům a automaticky pro připojení přijímat jakékoli podmínky a ujednání.
-   **Ruční konfigurace Wi-Fi** – Určuje, jestli může uživatel nakonfigurovat svoje vlastní Wi-Fi připojení, nebo jestli může použít jenom připojení nakonfigurovaná v rámci profilu Wi-Fi sítě (jenom Windows 10 Mobile).
-   **Interval hledání Wi-Fi** – Určuje, jak často zařízení skenují sítě Wi-Fi. Zadejte hodnotu v intervalu 1 (nejčastěji) až 500 (nejméně často).
-   **Povolené služby Bluetooth** – Zadejte seznam povolených služeb a profilů Bluetooth (v podobě hexadecimálních řetězců).


## <a name="control-panel-and-settings"></a>Ovládací panely a nastavení

-   **Aplikace Nastavení** – Zablokuje přístup k aplikaci Nastavení Windows.
    -   **Systém** – Zablokuje přístup k systémové oblasti v aplikaci Nastavení.
        -   **Změny nastavení napájení a režimu spánku (jenom desktopové verze)** – Zabrání koncovému uživateli ve změně nastavení napájení a režimu spánku na zařízení.
    -   **Zařízení** – Zablokuje přístup k oblasti zařízení v aplikaci Nastavení.
    -   **Síť a internet** – Zablokuje přístup k oblasti sítě a internetu v aplikaci Nastavení.
    -   **Přizpůsobení** – Zablokuje přístup k oblasti přizpůsobení v aplikaci Nastavení.
    -   **Účty** – Zablokuje přístup k oblasti účtů v aplikaci Nastavení.
    -   **Čas a jazyk** – Zablokuje přístup k oblasti času a jazyka v aplikaci Nastavení.
        -   **Změny systémového času** – Zabrání koncovému uživateli ve změně data a času zařízení.
        -   **Změny nastavení oblasti (jenom desktopové verze)** – Zabrání koncovému uživateli ve změně nastavení oblasti na zařízení.
        -   **Změny nastavení oblasti (jenom desktopové verze)** – Zabrání uživateli ve změně nastavení jazyka na zařízení.
    -   **Hry** – Zablokuje přístup k aplikaci Hry v Nastavení.
    -   **Usnadnění přístupu** – Zablokuje přístup k oblasti usnadnění přístupu v aplikaci Nastavení.
    -   **Soukromí** – Zablokuje přístup k oblasti soukromí v aplikaci Nastavení.
    -   **Aktualizace a zabezpečení** – Zablokuje přístup k oblasti aktualizací a zabezpečení v aplikaci Nastavení.

## <a name="kiosk"></a>Veřejný terminál

-   **Beznabídkový režim** – Identifikuje typ [režimu veřejného terminálu](https://docs.microsoft.com/en-us/windows/configuration/kiosk-shared-pc) podporovaného zásadami.  Vaše možnosti jsou:

      - **Nenakonfigurováno** (výchozí) – Zásady nepovolují režim veřejného terminálu. 
      - **Veřejný terminál s jednou aplikací** – Profil povoluje zařízení jako veřejný terminál s jednou aplikací.
      - **Veřejný terminál s více aplikacemi** – Profil povoluje zařízení jako veřejný terminál s více aplikacemi.

    Veřejný terminál s jednou aplikací vyžaduje následující nastavení:

      - **Uživatelský účet** – Určuje místní uživatelský účet (v zařízení) nebo přihlášení k účtu Azure AD přidružené k aplikaci veřejného terminálu.  Pro účty připojené k doménám Azure AD zadejte účet ve tvaru `domain\\username@tenant.org`.

         Pro zařízení ve veřejných prostředích použijte účty s minimálními oprávněními, abyste zabránili autorizované aktivitě.  

      - **ID modelu uživatele aplikace (AUMID) dané aplikace** – Určuje AUMID aplikace veřejného terminálu.  Další informace najdete v tématu [Jak najít ID modelu uživatele aplikace (AUMID) nainstalované aplikace](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

    Veřejné terminály s více aplikacemi vyžadují konfiguraci veřejného terminálu.  Použijte tlačítko **Přidat** a vytvořte konfiguraci veřejného terminálu, nebo vyberte existující konfiguraci.

    Konfigurace veřejných terminálů s více aplikacemi zahrnují následující nastavení:

    - **Název konfigurace veřejného terminálu** – Popisný název, pomocí kterého se daná konfigurace identifikuje.

    - Jedna nebo více **aplikací veřejného terminálu**, které tvoří:

        - **Typ aplikace** – Určuje typ aplikace veřejného terminálu.  Mezi podporované hodnoty patří:   

            - **Aplikace Win32** – Tradiční desktopová aplikace.  (Budete potřebovat plně kvalifikovanou (absolutní) cestu ke spustitelnému souboru, s ohledem na zařízení.)

            - **Aplikace pro UPW** – Univerzální aplikace pro Windows.  Budete potřebovat [AUMID aplikace](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

        - **Identifikátor aplikace** – Určuje buď plně kvalifikovanou (absolutní) cestu spustitelného souboru (u aplikací Win32), nebo [AUMID aplikace](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (u aplikací pro UPW).

    - **Hlavní panel** – Určuje, jestli má být na veřejném terminálu hlavní panel zobrazený (**Povoleno**), nebo skrytý (**Nenakonfigurováno**).

    - **Rozložení nabídky Start** – Určuje soubor XML, který popisuje, jak se mají aplikace [zobrazit v nabídce Start](https://docs.microsoft.com/en-us/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file).

    - **Přiřazení uživatelé** – Určuje jeden nebo více uživatelských účtů přidružených ke konfiguraci veřejného terminálu.  Účet může být místní (v zařízení) nebo přihlášení k účtu Azure AD přidružené k aplikaci veřejného terminálu.  Účty připojené k doménám zadejte ve tvaru `domain\\username@tenant.org`.

## <a name="defender"></a>Defender

-   **Monitorování v reálném čase** – Umožní v reálném čase zjišťovat výskyt malwaru, spywaru a dalšího nežádoucího softwaru.
-   **Monitorování chování** – Umožní programu Defender zjišťovat na zařízeních výskyt určitých známých vzorců podezřelých aktivit.
-   **Systém kontroly sítě (NIS)** – Systém NIS pomáhá chránit zařízení proti síťovým hrozbám. Používá signatury známých slabých míst z Centra Microsoftu pro ochranu koncových bodů ke zjištění a blokování škodlivého síťového provozu.
-   **Kontrolovat všechna stahování** – Určuje, jestli bude Defender kontrolovat všechny soubory stahované z internetu.
-   **Kontrolovat skripty načtené do webových prohlížečů Microsoftu** – Umožní Defenderu kontrolovat skripty, které se používají v Internet Exploreru.
-   **Přístup koncového uživatele k programu Defender** – Určuje, jestli se bude koncovým uživatelům zobrazovat uživatelské rozhraní Windows Defenderu.
Když toto nastavení změníte, projeví se změna až při příštím restartování počítače koncovým uživatelem.
-   **Interval aktualizace podpisu (v hodinách)** – Zadejte interval, ve kterém bude Defender kontrolovat dostupnost nových souborů s podpisem.
-   **Monitorovat aktivity spojené se soubory a programy** – Umožní Defenderu monitorovat aktivitu souborů a programů v zařízeních.
-   **Počet dní před odstraněním malwaru v karanténě** – Umožní Defenderu dál sledovat rozpoznaný malware po vámi určený počet dní, aby bylo možné ručně zkontrolovat dříve zasažená zařízení. Pokud nastavíte počet dnů **0**, malware zůstane ve složce karantény a automaticky se neodebere.
-   **Limit využití procesoru při kontrole** – Umožňuje nastavit maximální procento využití procesoru, které je možné využívat k provádění kontrol (od **1** do **100**).
-   **Kontrolovat archivované soubory** – Umožní Defenderu kontrolovat archivované soubory, jako jsou soubory Zip nebo Cab.
-   **Kontrolovat příchozí e-mailové zprávy** – Umožní Defenderu kontrolovat e-mailové zprávy při jejich doručení na zařízení.
-   **Při spuštění úplné kontroly kontrolovat vyměnitelné jednotky** – Umožní Defenderu kontrolovat vyměnitelné jednotky, jako jsou jednotky USB Flash.
-   **Při spuštění úplné kontroly kontrolovat namapované síťové jednotky** – Umožní Defenderu kontrolovat soubory na namapovaných síťových jednotkách.<br>Pokud jsou soubory na jednotce určené jen pro čtení, nemůže z nich Defender odebrat žádný malware, který v nich najde.
-   **Kontrolovat soubory otevřené ze síťových složek** –Umožní Defenderu kontrolovat soubory na sdílených síťových jednotkách (například na těch, ke kterým se získává přístup pomocí cesty UNC).
Pokud jsou soubory na jednotce určené jen pro čtení, nemůže z nich Defender odebrat žádný malware, který v nich najde.
-   **Cloudová ochrana** – Umožňuje službě Microsoft Active Protection Service povolit nebo blokovat příjem informací o činnosti malwaru ze zařízení, která spravujete. Tyto informace slouží k budoucímu vylepšování služby.
-   **Dotázat se uživatele před odesláním vzorku** – Určuje, jestli se mají Microsoftu k další analýze automaticky posílat potenciálně škodlivé soubory.
-   **Čas, kdy se má provést rychlá denní kontrola** – Umožní vám naplánovat rychlou kontrolu, ke které dochází denně v době, kterou vyberete.
-   **Typ systémové kontroly, který se má provést** – Umožní vám určit hloubku kontroly při plánované kontrole systému.
-   **Zjišťovat potenciálně nežádoucí aplikace** – Zvolte stupeň ochrany, pokud Windows zjistí potenciálně nežádoucí aplikace z těchto zdrojů:
        - **Blokováno**
        - **Audit** Další informace o potenciálně nežádoucích aplikacích najdete v [tomto tématu](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
-   **Akce ohledně zjištěných malwarových hrozeb** – Tuto možnost povolte, pokud chcete zadat akce, které má Defender provést při zjištění hrozby určité úrovně (nízká, střední, vysoká a vážná). Mohou být provedeny tyto akce:
    -   **Vyčistit**
    -   **Karanténa**
    -   **Odebrat**
    -   **Povoleno**
    -   **Definováno uživatelem**
    -   **Blokováno**



## <a name="defender-exclusions"></a>Výjimky Defenderu

-   **Soubory a složky, které chcete vyloučit z kontrol a ochrany v reálném čase** – Umožňuje do seznamu vyloučení přidat jeden nebo více souborů a složek, například **C:\Cesta** nebo **%ProgramFiles%\Cesta\název_souboru.exe**. Tyto soubory a složky nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.
-   **Přípony souborů, které chcete vyloučit z kontrol a ochrany v reálném čase** – Umožňuje přidat do seznamu vyloučení jednu nebo více přípon souborů jako **jpg** nebo **txt**. Soubory s těmito příponami nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.
-   **Procesy, které chcete vyloučit z kontrol a ochrany v reálném čase** – Umožňuje přidat do seznamu vyloučení jeden nebo více procesů typu **.exe**, **.com** nebo **.scr**. Tyto procesy nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.


## <a name="network-proxy"></a>Síťový proxy server

-   **Automaticky zjišťovat nastavení proxy serveru** – Pokud je tato možnost povolena, zařízení se pokusí najít cestu ke skriptu PAC.
-   **Použít skript proxy serveru** – Tuto možnost vyberte, pokud chcete zadat cestu ke skriptům PAC a nakonfigurovat proxy server.
    -   **Nastavení adresy URL skriptu** – Zadejte adresu URL skriptu PAC, pomocí kterého chcete nakonfigurovat proxy server.
-   **Použít ruční proxy server** – Tuto možnost vyberte, pokud chcete informace o proxy serveru zadat ručně.
    -   **Adresa** – Zadejte název nebo IP adresu proxy serveru.
    -   **Číslo portu** – Zadejte číslo portu vašeho proxy serveru.
    -   **Výjimky proxy serveru** – Zadejte adresy URL, které nesmí používat proxy server. Jednotlivé položky oddělte středníkem.
    -   **Obejít proxy server pro místní adresy** – Tuto možnost povolte, pokud nechcete proxy server používat pro místní adresy na vašem intranetu.


## <a name="windows-spotlight"></a>Windows Spotlight


- **Windows Spotlight** – Toto nastavení použijte k zablokování všech funkcí Windows Spotlight na zařízeních s Windows 10. Pokud toto nastavení zablokujete, nebudou následující nastavení k dispozici.
    - **Windows Spotlight na zamykací obrazovce** – Zastaví zobrazování informací z Windows Spotlight na zamykací obrazovce zařízení.
    - **Návrhy třetích stran ve Windows Spotlightu** – Zastaví ve Windows Spotlightu návrhy obsahu, který nebyl vydán Microsoftem.
    - **Uživatelské funkce** – Umožňuje zablokovat uživatelské funkce, jako jsou návrhy nabídky Start a oznámení o členství.
    - **Tipy Windows** – Umožňuje zablokovat zobrazování automaticky otevíraných tipů ve Windows.
    - **Windows Spotlight v centru akcí** – Zablokuje zobrazování návrhů Windows Spotlightu na nové aplikace nebo obsah týkající se zabezpečení v Centru akcí systému Windows.
    - **Přizpůsobení Windows Spotlightu** – Zastaví přizpůsobování výsledků ve Windows Spotlightu na základě použití zařízení.
    - **Prostředí uvítání systémem Windows** – Zablokuje prostředí uvítání systémem Windows, které uživateli zobrazuje informace o nových nebo aktualizovaných funkcích.


## <a name="projection"></a>Promítání

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
