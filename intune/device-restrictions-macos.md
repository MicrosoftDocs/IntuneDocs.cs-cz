---
title: nastavení zařízení macOS v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Přidání, konfigurace nebo vytvoření nastavení na zařízeních macOS, abyste omezili funkce, včetně nastavení požadavků na heslo, řízení uzamčené obrazovky, používání integrovaných aplikací, přidávání omezených nebo schválených aplikací, zpracování zařízení Bluetooth, připojení ke cloudu pro zálohování a úložiště, povolit celoobrazovkový režim, přidat domény a řídit, jak uživatelé pracují s webovým prohlížečem Safari v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/10/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d32224581c16325f0b060608409aa422cbf49d90
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71302359"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>macOS nastavení zařízení pro povolení nebo omezení funkcí pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek obsahuje seznam a popisuje různá nastavení, která můžete řídit na zařízeních macOS. V rámci řešení pro správu mobilních zařízení (MDM) pomocí těchto nastavení můžete povolit nebo zakázat funkce, nastavit pravidla pro hesla, povolit nebo omezit konkrétní aplikace a další.

Tato nastavení se přidají do konfiguračního profilu zařízení v Intune a pak se přiřadí nebo nasadí do zařízení macOS.

## <a name="before-you-begin"></a>Před zahájením

[Vytvoří konfigurační profil omezení zařízení](device-restrictions-configure.md).

> [!NOTE]
> Tato nastavení platí pro různé typy registrace. Další informace o různých typech registrace najdete v tématu [registrace MacOS](macos-enroll.md).

## <a name="general"></a>Obecné

### <a name="settings-apply-to-device-enrollment"></a>Nastavení platí pro: Registrace zařízení

- **Vyhledávání definic**: **Blok** znemožní uživateli zvýraznit slovo a pak na zařízení vyhledá jeho definici. **Není nakonfigurováno** (výchozí) umožňuje přístup k funkci vyhledávání definic.
- **Diktování**: **Blok** zabrání uživateli v zadávání textu pomocí hlasového vstupu. **Není nakonfigurováno** (výchozí) umožní uživateli používat vstup diktování.
- **Ukládání obsahu do mezipaměti**: Pokud chcete povolit ukládání obsahu do mezipaměti, vyberte **nenakonfigurované** (výchozí). Ukládání obsahu do mezipaměti ukládá data aplikací, data webového prohlížeče, soubory ke stažení a další místně na zařízení. Vyberte možnost **blokovat** , pokud chcete zabránit ukládání těchto dat do mezipaměti.

  Další informace o ukládání obsahu do mezipaměti v macOS najdete v tématu [Správa ukládání obsahu do mezipaměti na Macu](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (otevře další web).

  Tato funkce platí pro:  
  - macOS 10,13 a novější

- **Odložit aktualizace softwaru**: Pokud je nastavené na **Nenakonfigurováno** (výchozí nastavení), v zařízení se zobrazí aktualizace softwaru, které Apple uvolňuje. Pokud se třeba aktualizace macOS uvolní od společnosti Apple k určitému datu, tato aktualizace se přirozeně zobrazuje na zařízení v datu vydání verze. Aktualizace sestavení v počátečním nasazení jsou povoleny bez zpoždění.

  **Možnost Povolit** umožňuje prodlevu při zobrazení aktualizací softwaru na zařízeních, od 0-90 dnů. Toto nastavení neřídí, kdy jsou aktualizace nebo nejsou nainstalovány. 

  - **Zpoždění viditelnosti aktualizací softwaru**: Zadejte hodnotu od 0-90 dnů. Po vypršení zpoždění budou uživatelé dostávat oznámení o aktualizaci na nejstarší verzi operačního systému, která je k dispozici při spuštění zpoždění.

    Pokud je například macOS aktualizace k dispozici **1. ledna**a je **zpoždění viditelnosti** nastaveno na **5 dní**, aktualizace se nezobrazí jako dostupná aktualizace. Po **šestém dni** od vydání je tato aktualizace dostupná a koncoví uživatelé ji můžou nainstalovat.

    Tato funkce platí pro:  
    - macOS 10.13.4 a novější

- **Snímky obrazovky**: Zařízení musí být zaregistrované v automatickém zápisu zařízení (DEP) společnosti Apple. Když se nastaví **blokování**, uživatelé nemůžou Uložit snímek obrazovky obrazovky. Zabraňuje také aplikaci učeben v pozorování vzdálených obrazovek. **Není nakonfigurováno** (výchozí) umožňuje uživatelům zachytit snímky obrazovky a povolit aplikaci učeben zobrazovat vzdálené obrazovky.

### <a name="settings-apply-to-automated-device-enrollment"></a>Nastavení platí pro: Automatický zápis zařízení

- **Sledování vzdálené obrazovky prostřednictvím aplikace učebny**: Možnost **Zakázat** znemožní učitelům v používání aplikace učebny zobrazit své obrazovky studentů. **Není nakonfigurováno** (výchozí) umožňuje učitelům zobrazit obrazovky studentů.

  Chcete-li použít toto nastavení, nastavte nastavení **snímky obrazovky** na **Nenakonfigurováno** (snímky obrazovky jsou povoleny).

- **Nezobrazilo se sledování obrazovky podle aplikace učebny**: Možnost **dovolit** umožní učitelům zobrazit své studenty, aniž by museli studenta souhlasit. **Není nakonfigurováno** (výchozí) vyžaduje, aby student souhlasil, než uvidí obrazovky učitel.

  Chcete-li použít toto nastavení, nastavte nastavení **snímky obrazovky** na **Nenakonfigurováno** (snímky obrazovky jsou povoleny).

- **Studenti musí požádat o oprávnění k opuštění třídy učeben**: **Vyžadovat** , aby studenti, kteří se zaregistrovali v nespravované učebně učební, získali ke kurzu schválení učitelů. **Není nakonfigurováno** (výchozí) umožňuje studentovi opustit kurz pokaždé, když student zvolí.

- **Učitelé můžou automaticky uzamknout zařízení nebo aplikace v aplikaci učebny**: Při použití hodnoty **Povolit** mohou učitelé uzamknout zařízení nebo aplikaci studenta bez schválení studenta. **Není nakonfigurováno** (výchozí) vyžaduje, aby student souhlasil před tím, než učitel může zařízení nebo aplikaci uzamknout.

- **Studenti můžou automaticky připojit třídu učeben**: Možnost **Allow** umožňuje studentům připojit se ke třídě bez zobrazení výzvy učitelům. **Není nakonfigurováno** (výchozí) vyžaduje schválení učitelů pro připojení ke třídě.

## <a name="password"></a>Heslo

### <a name="settings-apply-to-device-enrollment"></a>Nastavení platí pro: Registrace zařízení

- **Heslo**: **Vyžaduje** , aby koncový uživatel zadal heslo pro přístup k zařízení. **Není nakonfigurováno** (výchozí) nevyžaduje heslo. Také nevynucuje žádná omezení, jako je například blokování jednoduchých hesel nebo nastavení minimální délky.
  - **Požadovaný typ hesla**: Určete, zda může být heslo pouze číselné nebo zda musí být alfanumerické (obsahovat písmena a čísla).

    Tato funkce platí pro:  
    - macOS 10.10.3 a novější

  - **Počet nealfanumerických znaků v hesle**: Určete požadovaný počet složitých znaků v hesle (**0** až **4**).<br>Složitý znak je symbol, například **?** .
  - **Minimální délka hesla**: Zadejte minimální délku hesla, které uživatel musí nakonfigurovat (mezi **4** a **16** znaky).
  - **Jednoduchá hesla**: Umožněte použít jednoduchá hesla, jako je **0000** nebo **1234**.
  - **Maximální počet minut po uzamčení obrazovky, než se požaduje heslo**: Určete, jak dlouho musí být počítač neaktivní, aby k jeho odemčení bylo potřeba heslo.
  - **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**: Zadejte dobu, po kterou musí být počítač nečinný, než se zamkne obrazovka.
  - **Vypršení platnosti hesla (dny)** : Určete, jak dlouho si může uživatel nechat stejné heslo, než ho bude muset změnit (**1** až **255** dnů).
  - **Zakázat opakované použití předchozích hesel**: Zadejte počet dříve použitých hesel, která se nesmí znovu použít, od **1** do **24**.

- **Zablokovat uživateli změnu hesla**: Vyberte možnost **blok** a zastavte změnu, přidání nebo odebrání hesla. **Není nakonfigurováno** (výchozí) umožňuje přidávat, měnit a odebírat hesla.
- **Zablokovat odemčení otiskem prstu**: Vyberte možnost **blokovat** , pokud chcete zabránit použití otisku prstu k odemknutí zařízení. **Není nakonfigurováno** (výchozí) povolí uživateli odemknout zařízení pomocí otisku prstu.

- **Zablokovat automatické vyplňování hesla**: Vyberte možnost **blokovat** , pokud chcete zabránit použití funkce automatického vyplňování hesel na MacOS. Výběr **bloku** má také následující dopad:

  - Uživatelům se nezobrazí výzva k použití uloženého hesla v Safari nebo ve všech aplikacích.
  - Automatická silná hesla jsou zakázaná a silná hesla se uživatelům nedoporučují.

  **Není nakonfigurováno** (výchozí) tyto funkce povolují.

- **Zablokovat žádosti o blízkost hesla**: Zvolit **blok** , aby zařízení uživatele nepožadovalo hesla z blízkých zařízení. **Není nakonfigurováno** (výchozí) povolí tyto požadavky na heslo.

- **Zablokovat sdílení hesla**: **Blok** zabraňuje sdílení hesel mezi zařízeními pomocí přetažení. **Není nakonfigurováno** (výchozí) umožňuje sdílet hesla.

## <a name="built-in-apps"></a>Integrované aplikace

### <a name="settings-apply-to-device-enrollment"></a>Nastavení platí pro: Registrace zařízení

- **Blokovat automatické vyplňování prohlížeče Safari**: **Blok** zakáže funkci automatického vyplňování v prohlížeči Safari na zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům změnit nastavení automatického dokončování ve webovém prohlížeči.
- **Blokovat kameru**: Vyberte možnost **blokovat** , pokud chcete zabránit přístupu k fotoaparátu na zařízení. **Není nakonfigurováno** (výchozí) povolí přístup k kameře zařízení.
- **Blokování Apple Music**: **Blok** vrátí aplikaci Hudba do klasického režimu a zakáže hudební službu. **Není nakonfigurováno** (výchozí) umožňuje použití aplikace Apple Music.
- **Zablokovat výsledky hledání na internetu pro Spotlight**: **Zablokování** zastaví vrácení jakýchkoli výsledků z hledání na internetu z Spotlightu. **Není nakonfigurováno** (výchozí) umožňuje vyhledávání Spotlightu připojit se k Internetu a poskytnout tak výsledky hledání.
- **Blokovat přenos souborů pomocí iTunes**: **Blokování** zakáže služby pro sdílení souborů aplikací. **Není nakonfigurováno** (výchozí) povolí služby pro sdílení souborů aplikací.

  Tato funkce platí pro:  
  - macOS 10,13 a novější

## <a name="restricted-apps"></a>Omezené aplikace

### <a name="settings-apply-to-device-enrollment"></a>Nastavení platí pro: Registrace zařízení

- **Typ seznamu omezených aplikací**: Vytvoří seznam aplikací, které uživatelé nemůžou instalovat ani používat. Možnosti:

  - **Není nakonfigurováno** (výchozí): Neexistují žádná omezení od Intune. Uživatelé mají přístup k aplikacím, které přiřadíte, a k integrovaným aplikacím.
  - **Zakázané aplikace**: Aplikace nespravované přes Intune, které nechcete instalovat na zařízení. Uživatelům není instalace zakázané aplikace znemožněna. Pokud ale uživatel z tohoto seznamu nainstaluje aplikaci, nahlásí se v Intune.
  - **Schválené aplikace**: Aplikace, které můžou uživatelé instalovat. Uživatelé nesmí instalovat aplikace, které nejsou uvedené. Aplikace, které spravuje Intune, jsou povolené automaticky. Uživatelům není znemožněna instalace aplikace, která není na seznamu schválených. Pokud tomu tak je, nahlásí se v Intune.
- **ID sady prostředků aplikace**: Zadejte [ID sady prostředků](bundle-ids-built-in-ios-apps.md) aplikace, kterou chcete. Můžete zobrazit nebo skrýt integrované aplikace a obchodní aplikace. Na webu společnosti Apple je seznam [integrovaných aplikací Apple](https://support.apple.com/HT208094).
- **Název aplikace**: Zadejte název aplikace, kterou chcete. Můžete zobrazit nebo skrýt integrované aplikace a obchodní aplikace. Na webu společnosti Apple je seznam [integrovaných aplikací Apple](https://support.apple.com/HT208094).
- **Vydavatel**: Zadejte vydavatele aplikace, kterou chcete.

Pokud chcete do těchto seznamů přidat aplikace, můžete:

- **Přidat**: Tuto možnost vyberte, pokud chcete vytvořit seznam aplikací.
- **Importujte** soubor CSV s podrobnostmi o aplikaci, včetně adresy URL. Použijte formát `<app bundle ID>, <app name>, <app publisher>`. Případně můžete **exportovat** a vytvořit seznam aplikací, které jste přidali, ve stejném formátu.

## <a name="connected-devices"></a>Připojená zařízení

### <a name="settings-apply-to-device-enrollment"></a>Nastavení platí pro: Registrace zařízení

- **Blokovat přetažení**: **Blok** zabraňuje použití přerušení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje použití funkce prohodit při výměně obsahu s blízkými zařízeními.
- **Zablokovat automatické odemknutí Apple Watch**: **Blok** zabraňuje uživatelům odemknout zařízení MacOS s jejich Apple Watch. **Není nakonfigurováno** (výchozí) umožňuje uživatelům odemknout zařízení macOS pomocí jejich Apple Watch.

## <a name="cloud-and-storage"></a>Cloud a úložiště

### <a name="settings-apply-to-device-enrollment"></a>Nastavení platí pro: Registrace zařízení

- **Blokovat synchronizaci řetězce klíčů iCloud**: Zvolením možnosti **blokovat** zakážete synchronizaci přihlašovacích údajů uložených v řetězci klíčů do iCloud. **Není nakonfigurováno** (výchozí) umožňuje uživatelům synchronizovat tyto přihlašovací údaje.
- **Zablokovat synchronizaci dokumentu iCloud**: **Blok** zabraňuje iCloud synchronizaci dokumentů a dat. **Není nakonfigurováno** (výchozí) povolí synchronizaci dokumentu a klíč-hodnota do iCloud prostoru úložiště.
- **Zablokovat zálohování pošty iCloud**: **Blok** zabraňuje synchronizaci iCloud do aplikace MacOS mail. **Není nakonfigurováno** (výchozí) umožňuje synchronizaci pošty s iCloud.
- **Zablokovat zálohování kontaktů iCloud**: **Blok** zabraňuje iCloud synchronizaci kontaktů zařízení. **Není nakonfigurováno** (výchozí) umožňuje synchronizaci kontaktů pomocí iCloud.
- **Zablokovat zálohování kalendáře iCloud**: **Blok** zabraňuje synchronizaci iCloud do aplikace kalendáře MacOS. **Není nakonfigurováno** (výchozí) umožňuje synchronizaci kalendáře do iCloud.
- **Zablokovat zálohování připomenutí iCloud**: **Blok** zabraňuje synchronizaci iCloud do aplikace MacOS připomenutí. **Není nakonfigurováno** (výchozí) umožňuje synchronizaci připomenutí do iCloud.
- **Zablokovat zálohování záložek iCloud**: **Blok** zabraňuje iCloud synchronizaci záložek zařízení. **Není nakonfigurováno** (výchozí) umožňuje synchronizaci záložek iCloud.
- **Zablokovat zálohování poznámek iCloud**: **Blok** zabraňuje iCloud synchronizaci poznámek zařízení. **Není nakonfigurováno** (výchozí) umožňuje synchronizaci poznámek s iCloud.
- **Blokovat knihovnu fotografií iCloud**: **Blokování** zakáže knihovnu fotografií iCloud a zabraňuje iCloud synchronizaci fotek zařízení. Všechny fotky, které nejsou plně stažené z knihovny fotografií iCloud, se z místního úložiště na zařízení odeberou. **Není nakonfigurováno** (výchozí) umožňuje synchronizovat fotky mezi zařízením a knihovnou fotek iCloud.
- **Předání**: **Není nakonfigurováno** (výchozí) umožňuje uživatelům začít pracovat na zařízení macOS a potom pokračovat v práci, kterou zahájili na jiném zařízení s iOS nebo macOS. **Blok** zabraňuje funkci předání na zařízení. 

  Tato funkce platí pro:  
  - macOS 10,15 a novější

## <a name="domains"></a>Domény

### <a name="settings-apply-to-device-enrollment"></a>Nastavení platí pro: Registrace zařízení

- **Adresa URL e-mailové domény**: **Přidejte** do seznamu jednu nebo více adres URL. Když uživatelé dostanou e-mail z jiné domény než z toho, kterou jste nakonfigurovali, označí se v aplikaci macOS mail e-mail jako nedůvěryhodný.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Na zařízeních s [iOS](device-restrictions-ios.md) můžete taky omezit funkce a nastavení zařízení.
