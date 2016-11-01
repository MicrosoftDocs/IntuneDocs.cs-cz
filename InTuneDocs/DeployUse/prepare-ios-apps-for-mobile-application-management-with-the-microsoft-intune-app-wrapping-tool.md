---
title: "Zabalení aplikací pro iOS pomocí nástroje App Wrapping Tool | Microsoft Intune"
description: "Informace v tomto tématu popisují, jak zabalit aplikace pro iOS beze změny vlastního kódu aplikace. Připravte aplikace, abyste mohli použít zásady správy mobilních aplikací."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c67a5042fd177a4c5bd897092e84281db0977f5e
ms.openlocfilehash: 2c187b61b8fe25b2870d0cbc62f8352494583fc2


---

# Příprava aplikací pro iOS na správu mobilních aplikací pomocí nástroje Intune App Wrapping Tool
Pokud chcete změnit chování aplikací iOS na pracovišti, abyste mohli nastavovat omezení funkcí aplikace beze změny kódu aplikace, použijte nástroj **Microsoft Intune App Wrapping pro iOS**.

Jde o nástroj příkazového řádku systému Mac OS, který okolo aplikace vytvoří tzv. „obálku“. Po zpracování aplikace pak můžete změnit její funkce pomocí [zásad správy mobilních aplikací](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) Intune, které nakonfigurujete.

Nástroj si můžete stáhnout na stránce [Microsoft Intune App Wrapping Tool for iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios).



## Krok 1: Splnění požadavků na používání nástroje pro zabalení aplikace
Další informace o požadavcích a postupu při jejich nastavení najdete v [tomto příspěvku blogu](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).

|Požadavek|Další informace|
|---------------|--------------------------------|
|Podporované operační systémy a sady nástrojů|Nástroj pro zabalení aplikace musíte spustit na počítači s macOS, na kterém běží OS X 10.8.5 nebo novější a je na něm nainstalovaná sada nástrojů XCode verze 5 nebo novější.|
|Podpisový certifikát a profil pro zřizování|Musíte mít podpisový certifikát Apple a profil pro zřizování. Informace najdete v [dokumentaci pro vývojáře Apple](https://developer.apple.com/).|
|Zpracování aplikace pomocí nástroje App Wrapping|Aplikace musela vyvinout a podepsat vaše společnost nebo nezávislý dodavatel softwaru (ISV). Tento nástroj se nedá používat ke zpracování aplikací z Apple Storu. Aplikace musí být napsané pro iOS 8.0 nebo novější. Aplikace také musí být ve formátu Position Independent Executable (PIE). Další informace o formátu PIE najdete v dokumentaci pro vývojáře Apple. A konečně aplikace musí mít příponu **.app**nebo **.ipa**.|
|Aplikace, které nástroj App Wrapping nedokáže zpracovat|Zašifrované aplikace, nepodepsané aplikace a aplikace s rozšířenými atributy souborů.|
|Nastavení nároků pro vaši aplikaci|Před zabalením aplikace je potřeba nastavit oprávnění, která poskytnou aplikaci další práva a schopnosti nad běžný rámec. Pokyny najdete v části [Nastavení nároků aplikace](#setting-app-entitlements).|

## Krok 2: Instalace nástroje pro zabalení aplikace

1.  Z úložiště **Microsoft Intune App Wrapping Tool for iOS** [ hostovaného na GitHubu](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) si stáhněte soubory nástroje k místnímu zabalení aplikace pro místní počítač macOS.

2.  Poklikejte na instalační soubor **Microsoft Intune App Wrapping Tool for iOS.dmg**. Zobrazí se okno s licenční smlouvou s koncovým uživatelem (EULA). Dokument si pozorně přečtěte.

3. Výběrem možnosti **Souhlasím** přijměte podmínky smlouvy EULA. Tím připojíte balíček k počítači.

4.  Otevřete balíček **IntuneMAMPackager** a uložte soubory do místní složky v počítači s macOS. Teď můžete nástroj pro zabalení aplikace spustit.

## Krok 3. Spuštění nástroje pro zabalení aplikace
* Na počítači s macOS otevřete okno Terminálu a přejděte do složky, do které jste uložili soubory nástroje pro zabalení aplikace. Spustitelný soubor má název **IntuneMAMPackager** a nachází se ve složce **IntuneMAMPackager/Contents/MacOS**. Příkaz budete muset spustit takto:

    ```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c <SHA1 hash of the certificate> [-b [<output app build string>]] [-v] [-e] [-x /<array of extension provisioning profile paths>]

    ```

    > [!NOTE]
    > Některé parametry jsou volitelné. Viz následující tabulka.

    **Příklad:** V tomto ukázkovém příkazu se nástroj pro zabalení aplikace spouští v aplikaci s názvem **MyApp.ipa**. Je zadaný profil zřizování a hash SHA-1. Vytvoří se zpracovaná aplikace s názvem **MyApp_Wrapped.ipa** a uloží se do složky Desktop příslušného uživatele.

    ```
    ./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i ~/Desktop/MyApp.ipa -o ~/Desktop/MyApp_Wrapped.ipa -p ~/Desktop/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB  -v true
    ```
    S nástrojem pro zabalení aplikace můžete používat následující vlastnosti příkazového řádku:

    |Vlastnost|Jak ji použít|
  |------------|--------------------|
  |**-i**|`<Path of the input native iOS application file>`. Soubor musí končit příponou .app nebo .ipa. |
  |**-o**|`<Path of the wrapped output application>` |
  |**-p**|`<Path of your provisioning profile for iOS apps>`|
  |**-c**|`<SHA1 hash of the signing certificate>`|
    |-h|Zobrazí podrobné informace o použití dostupných vlastností příkazového řádku nástroje pro zabalení aplikace.|
  |-v|(Nepovinná, ale užitečná) Zobrazí v konzole podrobné zprávy.|
  |-e | (Nepovinná) Tímto příznakem můžete zajistit, aby nástroj pro zabalení aplikace odebral při zpracování aplikace chybějící nároky. Více podrobností najdete v části Nastavení nároků aplikace.|
  |-xe| (Nepovinná) Zobrazí informace o rozšířeních iOS v aplikaci a o nárocích, které musí být splněné, aby je bylo možné používat. Více podrobností najdete v části Nastavení nároků aplikace. |
  |-x| (Nepovinná) `<An array of paths to extension provisioning profiles>` Tuto vlastnost použijte v případě, že vaše aplikace potřebuje zřizovací profily rozšíření.|
  |-f |(Nepovinná) `<Path to a plist file specifying arguments.>` Pokud se rozhodnete zadat zbývající vlastnosti nástroje IntuneMAMPackager (-i, -o, -p atd.) pomocí šablony plist, použijte před souborem [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html) tento příznak. Více podrobností najdete v části Zadání argumentů pomocí souboru plist. |
  |-b|(Nepovinná) Pokud chcete, aby měla zabalená výstupní aplikace stejnou verzi balíčku jako vstupní aplikace, použijte vlastnost -b bez argumentu (nedoporučuje se to). <br/><br/> Když chcete, aby měla zabalená aplikace vlastní verzi balíčku (CFBundleVersion), použijte vlastnost `-b <custom bundle version>`. Pokud se rozhodnete zadat vlastní verzi balíčku (CFBundleVersion), doporučujeme zvýšit ve verzi balíčku nativní aplikace číslo pro komponentu s nejmenší důležitostí, třeba takto: 1.0.0 -> 1.0.1. |


###Zadání argumentů pomocí souboru plist
App Wrapping Tool se dá jednoduše spustit zadáním všech argumentů příkazu do souboru [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html). Formát souboru plist je podobný formátu XML a umožňuje nám zadat argumenty našeho příkazového řádku s využitím rozhraní formuláře.

V textovém editoru nebo prostředí Xcode otevřete prázdnou šablonu `Parameters.plist` ze složky **IntuneMAMPackager/Contents/MacOS**. Zadejte požadované argumenty následujících klíčů:

| Klíč souboru plist |  Výchozí hodnota| Poznámky |
|------------------|--------------|-----|
| Input Application Package Path  |Prázdná| Odpovídá vlastnosti -i. |
| Output Application Package Path |Prázdná| Odpovídá vlastnosti -o.|
| Provisioning Profile Path |Prázdná| Odpovídá vlastnosti -p. |
| SHA-1 Certificate Hash |Prázdná| Odpovídá vlastnosti -c. |
| Verbose Enabled |nepravda| Odpovídá vlastnosti -v. |
| Remove Missing Entitlements | nepravda| Odpovídá vlastnosti -c.|
| Prevent Default Build |nepravda | Je ekvivalentní s použitím vlastnosti -b bez argumentů. |
|Build String Override | Prázdná| Vlastní verze balíčku (CFBundleVersion) zabalené výstupní aplikace |
|Extension Provisioning Profile Paths | Prázdná| Pole zřizovacích profilů rozšíření pro aplikaci
  

Nakonec spusťte nástroj IntuneMAMPackager a jako jediný argument použijte plist:

```
./IntuneMAMPackager –f Parameters.plist
```

* Po dokončení zpracování se zobrazí zpráva **The application was successfully wrapped** (Zabalení aplikace proběhlo úspěšně.).

    V případě chyby najdete nápovědu v tématu věnovaném [chybovým zprávám](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#error-messages).

*   Zabalená aplikace se uloží do výstupní složky, kterou jste určili předtím. Teď můžete aplikaci nahrát do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] a přidružit k zásadám správy mobilní aplikace.

    > [!IMPORTANT]
    > Pokud je už v Intune nasazená starší (zabalená nebo nativní) verze aplikace, můžete tuto starší verzi zkusit při nahrávání zabalené aplikace aktualizovat. Když se to nepovede, nahrajte aplikaci jako novou a starší verzi odstraňte.

    Teď můžete aplikaci nasadit do skupin [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] a aplikace se bude spouštět v zařízení s omezeními, která určíte.

## Chybové zprávy a soubory protokolu
K řešení potíží s nástrojem App Wrapping použijte následující informace.

### Chybovými zprávami
Pokud se nástroji pro zabalení aplikace nepovede aplikaci zabalit, zobrazí se v konzole některá z následujících chybových zpráv:

|Chybová zpráva|Další informace|
|-----------------|--------------------|
|Je nutné zadat platný profil zřizování iOS.|Váš profil zřizování nemusí být platný. Ověřte, jestli máte správná oprávnění pro zařízení a jestli je váš profil správně zacílený na vývoj nebo distribuci. Je taky možné, že vypršela platnost vašeho profilu zřizování.|
|Zadejte platný vstupní název aplikace.|Ujistěte se, že je správný název vstupní aplikace, který jste zadali.|
|Zadejte platnou cestu k výstupní aplikaci.|Ujistěte se, jestli existuje cesta k výstupní aplikace, kterou jste zadali, a jestli je správná.|
|Zadejte platný vstupní profil zřizování.|Ujistěte se, jestli jste zadali platný název a příponu profilu zřizování. V profilu zřizování můžou chybět oprávnění nebo jste nezahrnuli možnost příkazového řádku **–p**.|
|Nenašla se zadaná vstupní aplikace. Zadejte platný název a cestu vstupní aplikace.|Přesvědčte se, jestli je cesta ke vstupní aplikaci platná a existuje. Ujistěte se, jestli vstupní aplikace existuje v tomto umístění.|
|Zadaný soubor vstupního profilu zřizování se nenašel. Zadejte platný soubor vstupního profilu zřizování.|Ujistěte se, jestli je cesta k vstupnímu souboru profilu zřizování platná a jestli existuje soubor, který jste zadali.|
|Zadaná složka výstupní aplikace se nenašla. Zadejte platnou cestu k výstupní aplikaci.|Ujistěte se, jestli je zadaná výstupní cesta platná a existuje.|
|Výstupní aplikace nemá příponu .ipa.|Nástroj pro zabalení aplikace přijímá jenom aplikace s příponou **.app** a **.ipa**. Ujistěte se, že výstupní má platnou příponu.|
|Je zadaný neplatný podpisový certifikát. Zadejte platný podpisový certifikát Apple.|Ujistěte se, jestli jste stáhli správný podpisový certifikát stažený z portálu pro vývojáře Apple. Platnost vašeho certifikátu nejspíš vypršela nebo je možné, že chybí veřejný nebo privátní klíč. Pokud se dá váš profil certifikátu a zřizování apple použít ke správnému podepsání aplikace v rámci Xcodu, pak jsou platné pro nástroj pro zabalení aplikace.|
|Zadaná vstupní aplikace je neplatná. Zadejte platnou aplikaci.|Ujistěte se, že máte platnou aplikaci iOS, která je kompilovaná jako soubor .app nebo .ipa.|
|Zadaná vstupní aplikace je zašifrovaná. Zadejte platnou nezašifrovanou aplikaci.|Nástroj pro zabalení aplikace nepodporuje šifrované aplikace. Použijte aplikaci, která šifrovaná není.|
|Zadaná vstupní aplikace není ve formátu Position Independent Executable (PIE). Zadejte platnou aplikaci ve formátu PIE.|Aplikace Position Independent Executable (PIE) se dají při spuštění nahrát s náhodnou adresou paměti. To je výhodné pro zabezpečení. Další informace najdete v Dokumentaci pro vývojáře Apple.|
|Zadaná vstupní aplikace už je zabalená. Zadejte platnou nezabalenou aplikaci.|Nejde zpracovat aplikaci, kterou už nástroj zpracoval. Pokud chcete ke aplikaci znovu zpracovat, spusťte nástroj pomocí původní verze aplikace.|
|Zadaná vstupní aplikace není podepsaná. Zadejte platnou podepsanou aplikaci.|Nástroj pro zabalení aplikace vyžaduje, aby aplikace byla podepsaná. Vyhledejte v dokumentaci pro vývojáře, jak podepsat zabalenou aplikaci.|
|Zadaná vstupní aplikace musí být ve formátu .ipa nebo .app.|Nástroj pro zabalení aplikace přijímá jenom přípony .app a .ipa. Ujistěte se, že vstupní soubor má platnou příponu a je kompilovaný jako soubor .app nebo .ipa.|
|Vstupní aplikace, kterou jste zadali, už je zabalená a má nejnovější verzi šablony zásad.|Nástroj pro zabalení aplikace znovu nezabalí existující zabalenou aplikaci s nejnovější verzí šablony zásad.|
|UPOZORNĚNÍ: Nezadali jste hash SHA1 certifikátu. Ujistěte se, že zabalená aplikace je před nasazením podepsaná.|Pomocí příznaku **-c** příkazového řádku zadejte platnou hodnotu hash SHA1. |

### Soubory protokolu pro nástroj sbalení aplikace
Aplikace zabalené pomocí nástroje pro zabalení aplikace generují protokoly zapsané do konzoly klientského zařízení s iOS. Tyto informace jsou užitečné v případě, že máte s aplikací problémy a potřebujete zjistit, jestli nesouvisí s nástrojem pro zabalení aplikace. Pro načtení těchto informací použijte následující kroky:

1.  Reprodukujte problém spuštěním aplikace.

2.  Shromážděte výstup konzoly podle pokynů společnosti Apple k [ladění nasazených aplikací iOS](https://developer.apple.com/library/ios/qa/qa1747/_index.html).

3.  Vyfiltrujte uložené protokoly pro výstup omezení aplikace zadáním následujícího skriptu do konzoly:

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    Filtrované protokoly můžete odeslat do Microsoftu.

    > [!NOTE]
    > Položka verze buildu v souboru protokolu označuje verzi buildu pro Xcode.

    Zabalené aplikace taky uživatelům nabídnou možnost odeslat protokoly přímo ze zařízení prostřednictvím e-mailu v případě chyby aplikace. Protokoly můžou uživatelé poslat ke kontrole vám a vy je případně můžete přeposlat Microsoftu.


### Požadavky na certifikát, profil pro zřizování a ověřování

Plná funkčnost nástroje pro zabalení aplikace je zaručená jenom při splnění určitých požadavků.

|Požadavek|Podrobnosti|
|---------------|-----------|
|Profil pro zřizování|**Před zahrnutím zřizovacího profilu zkontrolujte, jestli je platný.** Nástroj pro zabalení aplikace při zpracování aplikace pro iOS nekontroluje, jestli nevypršela platnost zřizovacího profilu. Když je zadaný profil zřizování s ukončenou platností, bude nástroj pro zabalení aplikace zahrnovat tento profil a vy nepoznáte, jestli existuje problém, dokud neselže instalace aplikace na zařízení s iOS.|
|Certifikát|**Před zadáním certifikátu zkontrolujte, jestli je platný.** Nástroj při zpracování aplikací pro iOS nekontroluje, jestli nevypršela platnost certifikátu. Pokud je zadaný hash pro prošlý certifikát, nástroj zpracuje a podepíše aplikaci, ale nenainstaluje ji na zařízení.<br /><br />**Zkontrolujte, jestli pro certifikát poskytnutý k podepsání zabalené aplikace existuje shoda ve zřizovacím profilu.** Nástroj neověřuje, jestli pro certifikát poskytnutý k podepsání zabalené aplikace existuje shoda ve zřizovacím profilu.|
|Ověřování|Aby šifrování fungovalo, musí mít zařízení PIN. Když se uživatel na zařízeních, na která jste nasadili zabalenou aplikaci, dotkne stavového řádku, bude muset proběhnout jeho opakované ověření u [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Podle výchozí zásady zabalené aplikace probíhá *ověřování při opakovaném spuštění*. V iOSu se při každém externím oznámení (třeba  při telefonním hovoru) aplikace ukončí a potom znovu spustí.


## Nastavení nároků aplikace
Před zabalením aplikace můžete udělit **oprávnění**, která aplikaci poskytnou další práva a schopnosti nad běžný rámec.  Při podepisování kódu se pomocí **souboru oprávnění** určí v aplikaci speciální oprávnění (například přístup ke sdílenému řetězci klíčů). Během vývoje aplikace se v prostředí Xcode povolí konkrétní aplikační služby, pro které se používá označení **schopnosti**. Jakmile se tyto schopnosti povolí, odrazí se to v souboru oprávnění. Další informace o oprávněních a schopnostech najdete v článku věnovaném [přidání schopností](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) na webu iOS Developer Library. Úplný seznam podporovaných schopností najdete v části [Podporované schopnosti](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html).

### Podporované schopnosti nástroje App Wrapping pro iOS

|Funkce|Popis|Doporučené pokyny|
|--------------|---------------|------------------------|
|Skupiny aplikací|Pomocí skupin aplikací můžete více aplikacím povolit přístup ke sdíleným kontejnerům a povolit meziprocesovou komunikaci mezi aplikacemi.<br /><br />Pokud chcete povolit skupiny aplikací, otevřete podokno **Schopnosti** a klikněte na přepínač **ZAPNOUT** v části **Skupiny aplikací**. Můžete přidat nové skupiny aplikací nebo vybrat stávající.|U skupin aplikací používejte zpětný zápis DNS:<br /><br />*skupina.com.nazev_spolecnosti.skupina_aplikaci*|
|Režimy pozadí|Pokud povolíte režimy pozadí, vaše aplikace iOS bude moct být spuštěná na pozadí.||
|Data Protection|Ochrana dat přidá do souborů, které aplikace iOS uložení na disk, úroveň zabezpečení. Ochrana dat využívá integrovaný šifrovací hardware přítomný v určitých zařízeních k ukládání souborů na disk v zašifrovaném formátu. Pokud má vaše aplikace používat ochranu dat, musí být zřízená.||
|Nákupy v aplikaci|Funkce Nákupy v aplikaci vloží přímo do aplikace obchod, takže se budete moct připojit k obchodu a zpracovávat zabezpečené platby od uživatele. Pomocí funkce Nákupy v aplikaci můžete vybírat platby za rozšířené funkce nebo další obsah, který se dá v aplikaci použít.||
|Sdílení řetězce klíčů|Pokud povolíte sdílení řetězce klíčů, bude moct vaše aplikace sdílet hesla v řetězci klíčů s jinými aplikacemi vyvinutými vaším týmem.|Pokud používáte sdílení řetězce klíčů, použijte zpětný zápis DNS:<br /><br />*com.nazev_spolecnosti.skupina_retezcu_klicu*|
|Osobní síť VPN|Můžete povolit osobní síť VPN, aby mohla vaše aplikace vytvářet a řídit vlastní systémovou konfiguraci sítě VPN s využitím rámce pro rozšíření sítě.||
|Nabízená oznámení|Služba APNs (Apple Push Notification service) umožňuje aplikaci, která není spuštěná v popředí, zobrazit uživateli oznámení o dostupných informacích.|Nabízená oznámení fungují jenom tehdy, když pro konkrétní aplikaci použijete profil zřizování.<br /><br />Postupujte podle návodu v [dokumentaci pro vývojáře Apple](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html).|
|Konfigurace bezdrátového příslušenství|Povolením konfigurace bezdrátového příslušenství přidáte do svého projektu rámec externích příslušenství a umožníte své aplikaci konfigurovat příslušenství MFi s připojením Wi-Fi.||

### Postup pro povolení oprávnění

1.  Povolení schopností v aplikaci:

    1.  V prostředí Xcode přejděte na cíl své aplikace a klikněte na podokno **Schopnosti**.

    2.  Zapněte příslušné schopnosti. Podrobné informace o jednotlivých schopnostech a o tom, jak určit správné hodnoty, najdete v článku věnovaném [přidání schopností](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) na webu iOS Developer Library.

    3.  Poznamenejte si všechna ID, která v průběhu procesu vytvoříte.

    4.  Sestavte a podepište aplikaci, kterou chcete zabalit.

2.  Ve svém profilu pro zřizování povolte oprávnění:

    1.  Přihlaste do Centra pro vývojáře Apple.

    2.  Vytvořte pro svoji aplikaci profil pro zřizování. Pokyny najdete v článku věnovaném [splnění předpokladů pro nástroj Intune App Wrapping pro iOS](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/).

    3.  V profilu pro zřizování povolte stejná oprávnění, jaká máte ve své aplikaci. Budete muset zadat stejná ID, která jste zadali během vývoje aplikace.

    4.  Dokončete průvodce profilem pro zřizování a stáhněte soubor.

3.  Ujistěte se, že jste splnili všechny předpoklady, a zabalte aplikaci.

### Řešení potíží s běžnými chybami spojenými s oprávněními
Pokud nástroj App Wrapping pro iOS zobrazí chybu oprávnění, vyzkoušejte následující postupy pro řešení potíží.

|Problém|Příčina|Řešení|
|---------|---------|--------------|
|Nepodařilo se analyzovat oprávnění vygenerovaná vstupní aplikací.|Nástroj App Wrapping nemůže přečíst soubor oprávnění extrahovaný z aplikace. Soubor oprávnění může být poškozený.|Zkontrolujte soubor oprávnění pro svoji aplikaci. Postupujte podle níže uvedených pokynů. Při kontrole souboru oprávnění hledejte případy poškozené syntaxe. Soubor by měl být ve formátu XML.|
|V profilu pro zřizování chybí oprávnění (s uvedením chybějících oprávnění). Znovu zabalte aplikaci pomocí profilu pro zřizování, který má tato oprávnění.|Oprávnění povolená v profilu pro zřizování neodpovídají schopnostem povoleným v aplikaci. Tato neshoda se týká také ID přidružených k určitým schopnostem (tedy skupin aplikací, přístupu k řetězcům klíčů atd.).|Obecně platí, že můžete vytvořit nový profil pro zřizování, který povolí stejné schopnosti jako aplikace. Pokud ID v profilu neodpovídají ID v aplikaci, nástroj App Wrapping tato ID nahradí, pokud to bude možné. Pokud se tato chyba zobrazí i po vytvoření nového profilu zřizování, můžete zkusit odebrat oprávnění z aplikace pomocí parametru **–e** (viz část Použití parametru –e k odebrání oprávnění z aplikace, kterou najdete níž).|

### Vyhledání stávajících oprávnění v podepsané aplikaci
Postup pro kontrolu oprávnění v podepsané aplikaci a profilu pro zřizování:

1.  Najděte soubor .ipa a změňte jeho příponu na .zip.

2.  Rozbalte soubor .zip. Vznikne tak složka datové části, která obsahuje sadu .app.

3.  Pomocí nástroje codesign ověřte oprávnění k sadě .app:

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```
    kde `YourApp.app` je skutečný název vaší sady .app.

4.  Pomocí nástroje security ověřte oprávnění k vloženému profilu pro zřizování aplikace:

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```
    kde `YourApp.app` je skutečný název vaší sady .app.

### Použití parametru –e k odebrání oprávnění z aplikace, kterou najdete níž).
Tento příkaz odebere z aplikace všechny povolené schopnosti, které nejsou v souboru oprávnění. Pokud odeberete oprávnění, které aplikace využívá, může ji to poškodit. Příkladem, kdy je možné odebrat chybějící schopnosti, je třeba situace, kdy máte dodavatelsky vytvořenou aplikaci, která má ve výchozím nastavení všechny schopnosti.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## Zabezpečení a ochrana osobních údajů nástroje pro zabalení aplikace
Při používání nástroje pro zabalení aplikace použijte následující doporučené postupy pro zabezpečení a ochranu osobních údajů.

-   Podpisový certifikát, zřizovací profil a obchodní aplikace, které zadáte, musí být na stejném počítači s macOS, na jakém spouštíte nástroj pro zabalení aplikace. Pokud jsou soubory v cestě UNC, je potřeba, aby se k nim dalo z počítače s macOS dostat. Cesta musí být zabezpečená pomocí protokolu IPsec nebo podepsání SMB.

    Zabalená aplikace naimportovaná do konzoly [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] by měla být na stejném počítači, na kterém jste nástroj spustili. Pokud je soubor v cestě UNC, zajistěte, aby byl přístupný na počítači se spuštěnou konzolou [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Cesta musí být zabezpečená pomocí protokolu IPsec nebo podepsání SMB.

-   Prostředí, kam se nástroj pro zabalení aplikace z úložiště GitHubu stahuje, musí být zabezpečené pomocí protokolu IPsec nebo podepisování SMB.

-   Zpracovávaná aplikace musí kvůli zajištění ochrany před útoky pocházet z důvěryhodného zdroje.

-   Zadaná výstupní složka v nástroji pro zabalení aplikace musí být zabezpečená, zvlášť pokud je to vzdálená složka.

-   V aplikacích pro iOS, které obsahují dialog pro nahrávání souborů, můžou uživatelé omezení aplikace vztahující se na vyjmutí, zkopírování a vložení obejít. Uživatel může například pomocí dialogového okna pro nahrání souboru nahrát snímek obrazovky dat aplikace.

-   Když uživatelé sledují složku dokumentů na zařízení ze zabalené aplikace, může se jim zobrazit složka **.msftintuneapplauncher**. Pokud tuto složku změníte nebo odstraníte, může to mít vliv na správné fungování aplikací s omezeními.

### Související témata
- [Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [Použití sady SDK k povolení správy mobilních aplikací pro aplikace](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Oct16_HO2-->


