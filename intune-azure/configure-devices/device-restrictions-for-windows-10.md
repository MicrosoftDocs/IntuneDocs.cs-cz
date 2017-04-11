---
title: "Nastavení omezení pro zařízení s Windows 10 v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 74f99d5e2d4eef8d42ccd2c7bc34e0ed7b6f0d51
ms.lasthandoff: 02/18/2017


---

# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení pro zařízení Windows 10 a novější v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Obecné
-     **Snímek obrazovky** – Umožňuje uživateli zachytit obrazovku zařízení v podobě obrázku. (jenom Windows 10 Mobile)
-     **Kopírování a vložení (jen mobilní)** – Povolí akce kopírování a vkládání mezi aplikacemi na zařízení.
-     **Ruční zrušení zápisu** – Umožňuje uživateli ze zařízení ručně odstranit pracovní účet.
-     **Ruční instalace kořenového certifikátu** -     
-     **Odeslání diagnostických dat** – Možné hodnoty jsou:
    -         **Žádné:** Do Microsoftu se nepošlou žádná data.
    -         **Základní:** Do Microsoftu se pošle omezené množství dat.
    -         **Rozšířené:** Do Microsoftu se pošlou rozšířená data pro diagnostiku.
    -         **Úplné:** Pošle stejná data jako možnost Rozšířené a k tomu navíc údaje o stavu zařízení.
-     **Kamera** – Povolí nebo zablokuje použití fotoaparátu v zařízení.
-     **Vyměnitelné úložiště** – Určuje, jestli je možné se zařízením použít zařízení externího úložiště, jako jsou SD karty.
-     **Zeměpisná poloha** – Určuje, jestli zařízení může používat informace služeb určování polohy.
-     **Sdílení internetu** – Povolí používat sdílení internetového připojení na zařízení.
-     **Obnovení továrního nastavení telefonu** – Určuje, jestli uživatel může na svém zařízení obnovit tovární nastavení.
-     **Připojení USB** – Určuje, jestli má zařízení přístup k zařízením externího úložiště prostřednictvím připojení USB.
-     **Režim AntiTheft** – Umožňuje nakonfigurovat, jestli má být povolený režim Windows AntiTheft.
-     **Oznámení Centra akcí** – Povolí nebo zakáže oznámení Centra akcí na zamykací obrazovce zařízení (jenom Windows 10 Mobile).
-     **Cortana** – Povolí nebo zakáže hlasovou asistentku Cortanu.
-     **Záznam hlasu** – Povolí nebo zablokuje použití záznamu hlasu na zařízení.

## <a name="password"></a>Heslo
-     **Zadání hesla nutné** – Vyžaduje, aby koncový uživatel zadal heslo k přístupu k zařízení.
-     **Požadovaný typ hesla** – Určuje, jestli musí být heslo složené jen z čísel, nebo z čísel a písmen.
-     **Minimální délka hesla** – Platí jenom pro Windows 10 Mobile.
-     **Počet neúspěšných přihlášení před vymazáním obsahu zařízení** – Pro zařízení s Windows 10: Pokud má zařízení povolený nástroj BitLocker, přejde do režimu obnovení nástroje BitLocker v případě, že se nepodaří přihlásit v rámci určeného počtu pokusů. Pokud zařízení nemá povolený nástroj BitLocker, toto nastavení se na něho nevztahuje.
Pro zařízení s Windows 10: Jakmile se nepovede určený počet pokusů o přihlášení, zařízení bude vymazáno.
-     **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka** – Určuje dobu, po kterou musí být zařízení v nečinnosti, než se zamkne obrazovka.
-     **Konec platnosti hesla (dny)** – Určuje dobu, po jejímž uplynutí je třeba změnit heslo k zařízení.
-     **Znemožnit opakované použití předchozích hesel** – Určuje počet dříve použitých hesel, která se na zařízení zapamatovávají.
-     **Vyžadovat heslo při návratu zařízení ze stavu nečinnosti** – Určuje, že uživatel musí zadat heslo k odemknutí zařízení (jenom Windows 10 Mobile).
-     **Šifrování** – Povolí šifrování na cílových zařízeních (jenom Windows 10 Mobile).
## <a name="app-store"></a>App Store

-     **App Store (jen mobilní)** – Povolí nebo zablokuje použití App Storu na zařízeních s Windows 10 Mobile.
## <a name="edge-browser"></a>Prohlížeč Edge
-     **Prohlížeč Microsoft Edge (jenom mobilní zařízení)** – Povolí používání webového prohlížeče Edge na zařízení.
-     **Filtr SmartScreen** – Povolí nebo zakáže filtr SmartScreen, který blokuje podvodné weby.
-     **Odesílat hlavičky Do Not Track** – Nakonfiguruje prohlížeč Edge tak, aby se webům, které uživatelé navštíví, posílaly hlavičky DNT (Do Not Track).
-     **Soubory cookie** – Umožní prohlížeči ukládat internetové soubory cookie do zařízení.
-     **JavaScript** – Umožní, aby se v prohlížeči Edge mohly spouštět skripty, třeba JavaScript.
-     **Automaticky otevíraná okna** – Zablokuje automaticky otevíraná okna v prohlížeči.<br>(Platí jenom pro Windows 10 Desktop.)
-     **Návrhy hledání** – Umožní, aby vám vyhledávací web při psaní hledaného textu navrhoval weby.
-     **Odesílat intranetové přenosy do Internet Exploreru** – Umožní uživatelům otevírat intranetové weby v Internet Exploreru. <br>(jenom Windows 10 Desktop)
-     **Automatické vyplňování** – Umožní uživatelům měnit nastavení automatického dokončování v prohlížeči.<br>(jenom Windows 10 Desktop)
-     **Správce hesel** – Povolí nebo zakáže funkci Správce hesel v Edgi.
-     **Umístění seznamu webů využívajících Režim rozlehlé sítě** – Určuje, kde najít seznam webů, které se otevřou v podnikovém režimu rozlehlé sítě. Uživatelé nemohou tento seznam upravovat.<br>(jenom Windows 10 Desktop)
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
-     **Bezkontaktní komunikace (NFC)** – Umožní uživateli povolit a konfigurovat na zařízení možnosti bezkontaktní komunikace.
-     **Wi-Fi** – Umožní uživateli povolit a konfigurovat Wi-Fi na zařízení (jenom Windows 10 Mobile).
-     **Automaticky se připojovat k Wi-Fi hotspotům** – Umožní zařízení automaticky se připojovat k volným Wi-Fi hotspotům a automaticky pro připojení přijímat jakékoli podmínky a ujednání.
-     **Ruční konfigurace Wi-Fi** – Určuje, jestli může uživatel nakonfigurovat svoje vlastní Wi-Fi připojení, nebo jestli může použít jenom připojení nakonfigurovaná v rámci profilu Wi-Fi sítě (jenom Windows 10 Mobile).
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

