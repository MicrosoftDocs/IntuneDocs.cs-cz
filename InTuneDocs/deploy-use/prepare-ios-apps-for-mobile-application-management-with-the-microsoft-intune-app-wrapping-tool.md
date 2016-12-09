---
title: "Zabalení aplikací pro iOS nástrojem Intune App Wrapping | Microsoft Intune"
description: "V tomto tématu se naučíte balit aplikace pro iOS bez změny samotného kódu aplikace. Připravte aplikace, abyste mohli použít zásady správy mobilních aplikací."
keywords: 
author: mtillman
ms.author: mtillman
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
ms.sourcegitcommit: ee7e0491c0635c45cbc0377a5de01d5eba851132
ms.openlocfilehash: 0eee40c3c3c6bdfc3da2e715ef7b46e8408ba319


---

# <a name="prepare-ios-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a>Příprava aplikací pro iOS na správu mobilních aplikací pomocí nástroje Intune App Wrapping Tool

Pokud chcete změnit chování interních aplikací pro iOS beze změny samotného kódu těchto aplikací, použijte nástroj Microsoft Intune App Wrapping Tool pro iOS.

Tento nástroj je vlastně aplikace příkazového řádku systému Mac OS, která vytvoří obálku aplikace. Po zpracování aplikace můžete v Intune změnit její funkce pomocí [zásad správy mobilních aplikací](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md), které nasadil správce IT.

Nástroj si můžete stáhnout na stránce [Microsoft Intune App Wrapping Tool pro iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) v GitHubu.



## <a name="fulfill-the-prerequisites-for-the-app-wrapping-tool"></a>Splnění požadavků pro nástroj App Wrapping Tool
Další informace o tom, jak splnit požadavky pro tento nástroj, najdete v blogovém příspěvku [How to obtain prerequisites for the Intune App Wrapping Tool for iOS](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/) (Jak splnit požadavky pro nástroj Intune App Wrapping Tool pro iOS).

|Požadavek|Další informace|
|---------------|--------------------------------|
|Podporované operační systémy a sady nástrojů | Nástroj App Wrapping musíte spustit na počítači s Mac OS, na kterém běží OS X 10.8.5 nebo novější a je na něm nainstalovaná sada nástrojů XCode verze 5 nebo novější.|
|Podpisový certifikát a profil pro zřizování | Musíte mít podpisový certifikát Apple a profil pro zřizování. Informace najdete v [dokumentaci pro vývojáře Apple](https://developer.apple.com/).|
|Zpracování aplikace pomocí nástroje App Wrapping  |Aplikaci musí vyvinout a podepsat vaše společnost nebo nezávislý výrobce softwaru (ISV). Tento nástroj se nedá používat ke zpracování aplikací z Apple Storu. Aplikace musí být napsané pro iOS 8.0 nebo novější. Aplikace také musí být ve formátu Position Independent Executable (PIE). Další informace o formátu PIE najdete v dokumentaci pro vývojáře Apple. Aplikace musí mít příponu **.app** nebo **.ipa**.|
|Aplikace, které nástroj nedokáže zpracovat | Zašifrované aplikace, nepodepsané aplikace a aplikace s rozšířenými atributy souborů.|
|Nastavení nároků pro vaši aplikaci|Než aplikaci zabalíte, musíte nastavit oprávnění, se kterými získá další oprávnění a možnosti přesahující běžný rámec. Pokyny najdete v části [Nastavení nároků aplikace](#setting-app-entitlements).|

## <a name="install-the-app-wrapping-tool"></a>Instalace nástroje App Wrapping Tool

1.  Stáhněte si soubory pro nástroj App Wrapping Tool z [GitHubu](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) do počítače s macOS.

2.  Poklikejte na soubor **Microsoft Intune App Wrapping Tool for iOS.dmg**. Zobrazí se okno s licenční smlouvou s koncovým uživatelem (EULA). Dokument si pozorně přečtěte.

3. Výběrem možnosti **Souhlasím** přijměte podmínky smlouvy EULA. Tím připojíte balíček k počítači.

4.  Otevřete složku **IntuneMAMPackager** a uložte její obsah do počítače s macOS. Teď můžete nástroj App Wrapping spustit.

## <a name="run-the-app-wrapping-tool"></a>Spuštění nástroje App Wrapping Tool

### <a name="use-terminal"></a>Použití terminálu

Otevřete okno Terminálu na počítači s macOS a přejděte do složky, do které jste uložili soubory nástroje pro zabalení aplikace. Spustitelný soubor má název IntuneMAMPackager a nachází se ve složce IntuneMAMPackager/Contents/MacOS. Spusťte následující příkaz:

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c <SHA1 hash of the certificate> [-b [<output app build string>]] [-v] [-e] [-x /<array of extension provisioning profile paths>]
```

> [!NOTE]
> Některé parametry jsou volitelné, jak je vidět v následující tabulce.

**Příklad:** V tomto ukázkovém příkazu se nástroj App Wrapping Tool spouští v aplikaci s názvem MyApp.ipa. Profil zřizování a algoritmus hash SHA-1 podepisujícího certifikátu jsou definovány a použijí se k podepsání zabalené aplikace. Vytvoří se výstupní aplikace (MyApp_Wrapped.ipa), která se uloží do složky Desktop.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i ~/Desktop/MyApp.ipa -o ~/Desktop/MyApp_Wrapped.ipa -p ~/Desktop/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB  -v true
```

### <a name="command-line-parameters"></a>Parametry příkazového řádku
V nástroji App Wrapping Tool můžete používat následující parametry příkazového řádku:

|Vlastnost|Jak ji použít|
|---------------|--------------------------------|
|**-i**|`<Path of the input native iOS application file>`. Název souboru musí končit na .app nebo .ipa. |
|**-o**|`<Path of the wrapped output application>` |
|**-p**|`<Path of your provisioning profile for iOS apps>`|
|**-c**|`<SHA1 hash of the signing certificate>`|
|**-h**|Zobrazí podrobné informace o použití dostupných vlastností příkazového řádku nástroje App Wrapping.|
|**-v**|(Nepovinná) Zobrazí v konzole podrobné zprávy.|
|**-e**| (Nepovinná) Tímto příznakem zajistíte, že nástroj App Wrapping při zpracování aplikace odebere chybějící oprávnění. Další informace najdete v části Nastavení oprávnění aplikace.|
|**-xe**| (Nepovinná) Zobrazí informace o rozšířeních iOS v aplikaci a o oprávněních, která potřebujete k jejich používání. Další informace najdete v části Nastavení oprávnění aplikace. |
|**-x**| (Nepovinná) `<An array of paths to extension provisioning profiles>` Tuto vlastnost použijte v případě, že vaše aplikace potřebuje zřizovací profily rozšíření.|
|**-f**|(Nepovinná) `<Path to a plist file specifying arguments.>` Pokud se rozhodnete zadat zbývající vlastnosti nástroje IntuneMAMPackager, jako je -i, -o a -p, šablonou plist, použijte tento příznak před souborem [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html). Další informace najdete v části, která vysvětluje použití souboru plist k zadání argumentů. |
|**-b**|(Nepovinná) Pokud chcete, aby měla zabalená výstupní aplikace stejnou verzi balíčku jako vstupní aplikace, použijte vlastnost -b bez argumentu (nedoporučuje se to). <br/><br/> Když chcete, aby měla zabalená aplikace vlastní verzi balíčku (CFBundleVersion), použijte vlastnost `-b <custom bundle version>`. Pokud se rozhodnete zadat vlastní verzi balíčku CFBundleVersion, doporučujeme zvýšit nejméně důležitou část hodnoty CFBundleVersion nativní aplikace, třeba z 1.0.0 na 1.0.1. |

### <a name="use-a-plist-to-input-arguments"></a>Zadání argumentů pomocí souboru plist
App Wrapping Tool se dá jednoduše spustit zadáním všech argumentů příkazu do souboru [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html). Formát souboru plist je podobný formátu XML. Můžete ho použít k zadání argumentů příkazového řádku s využitím rozhraní formuláře.

Ve složce IntuneMAMPackager/Contents/MacOS otevřete `Parameters.plist` (prázdná šablona souboru plist). Použijte k tomu textový editor nebo Xcode. Zadejte požadované argumenty následujících klíčů:

| Klíč souboru plist |  Výchozí hodnota| Poznámky |
|------------------|--------------|-----|
| Input Application Package Path  |Prázdná| Odpovídá vlastnosti -i.|
| Output Application Package Path |Prázdná| Odpovídá vlastnosti -o.|
| Provisioning Profile Path |Prázdná| Odpovídá vlastnosti -p.|
| SHA-1 Certificate Hash |Prázdná| Odpovídá vlastnosti -c.|
| Verbose Enabled |nepravda| Odpovídá vlastnosti -v.|
| Remove Missing Entitlements | nepravda| Odpovídá vlastnosti -c.|
| Prevent Default Build |nepravda | Odpovídá použití vlastnosti -b bez argumentů.|
|Build String Override | Prázdná| Vlastní verze balíčku (CFBundleVersion) zabalené výstupní aplikace |
|Extension Provisioning Profile Paths | Prázdná| Pole zřizovacích profilů rozšíření pro aplikaci


Spusťte nástroj IntuneMAMPackager a jako jediný argument použijte soubor plist:

```bash
./IntuneMAMPackager –f Parameters.plist
```

### <a name="post-wrapping"></a>Po zabalení

Po dokončení procesu zabalení se zobrazí zpráva The application was successfully wrapped (Zabalení aplikace proběhlo úspěšně.). V případě chyby najdete nápovědu v tématu věnovaném [chybovým zprávám](#error-messages-and-log-files).

Zabalená aplikace se uloží do výstupní složky, kterou jste určili předtím. Aplikaci můžete nahrát do konzoly pro správu Intune a přidružit ji k zásadě správy mobilní aplikace.

> [!IMPORTANT]
> Pokud je už v Intune nasazená starší (zabalená nebo nativní) verze aplikace, můžete tuto starší verzi zkusit při nahrávání zabalené aplikace aktualizovat. Když se to nepovede, nahrajte aplikaci jako novou a starší verzi odstraňte.

Teď můžete aplikaci nasadit do skupin uživatelů a zásad ochrany cílové aplikace. Aplikace se bude spouštět na zařízení pomocí zásad ochrany aplikace, které jste určili.

## <a name="error-messages-and-log-files"></a>Chybové zprávy a soubory protokolu
K řešení potíží s nástrojem App Wrapping použijte následující informace.

### <a name="error-messages"></a>Chybovými zprávami
Pokud se nástroji App Wrapping nepodaří aplikaci zabalit, zobrazí konzola některou z následujících chybových zpráv:

|Chybová zpráva|Další informace|
|-----------------|--------------------|
|Je nutné zadat platný profil zřizování iOS.|Váš profil zřizování nemusí být platný. Zkontrolujte, že máte pro zařízení správná oprávnění a že máte správně zaměřený profil pro vývoj nebo distribuci. Je taky možné, že vypršela platnost vašeho profilu zřizování.|
|Zadejte platný vstupní název aplikace.|Ujistěte se, že je správný název vstupní aplikace, který jste zadali.|
|Zadejte platnou cestu k výstupní aplikaci.|Ujistěte se, jestli existuje cesta k výstupní aplikace, kterou jste zadali, a jestli je správná.|
|Zadejte platný vstupní profil zřizování.|Ujistěte se, jestli jste zadali platný název a příponu profilu zřizování. V profilu zřizování mohou chybět oprávnění nebo jste neuvedli parametr příkazového řádku –p.|
|Nenašla se zadaná vstupní aplikace. Zadejte platný název a cestu vstupní aplikace.|Přesvědčte se, jestli je cesta ke vstupní aplikaci platná a existuje. Ujistěte se, jestli vstupní aplikace existuje v tomto umístění.|
|Zadaný soubor vstupního profilu zřizování se nenašel. Zadejte platný soubor vstupního profilu zřizování.|Ujistěte se, jestli je cesta k vstupnímu souboru profilu zřizování platná a jestli existuje soubor, který jste zadali.|
|Zadaná složka výstupní aplikace se nenašla. Zadejte platnou cestu k výstupní aplikaci.|Ujistěte se, jestli je zadaná výstupní cesta platná a existuje.|
|Výsledná aplikace nemá příponu **.ipa**.|Nástroj App Wrapping přijímá jenom aplikace s příponou **.app** a **.ipa**. Ujistěte se, že výstupní má platnou příponu.|
|Je zadaný neplatný podpisový certifikát. Zadejte platný podpisový certifikát Apple.|Ujistěte se, jestli jste stáhli správný podpisový certifikát stažený z portálu pro vývojáře Apple. Platnost vašeho certifikátu nejspíš vypršela nebo je možné, že chybí veřejný nebo privátní klíč. Pokud můžete certifikát Apple a zřizovací profil použít ke správnému podepsání aplikace v Xcodu, platí tyto položky i pro nástroj App Wrapping.|
|Zadaná vstupní aplikace je neplatná. Zadejte platnou aplikaci.|Ujistěte se, že máte platnou aplikaci iOS, která je kompilovaná jako soubor .app nebo .ipa.|
|Zadaná vstupní aplikace je zašifrovaná. Zadejte platnou nezašifrovanou aplikaci.|Nástroj App Wrapping nepodporuje šifrované aplikace. Použijte aplikaci, která šifrovaná není.|
|Zadaná vstupní aplikace není ve formátu Position Independent Executable (PIE). Zadejte platnou aplikaci ve formátu PIE.|Aplikace ve formátu Position Independent Executable (PIE) je možné při spuštění načíst s náhodnou adresou v paměti. Může to být výhodné kvůli zabezpečení. Další informace o výhodách týkajících se zabezpečení najdete v dokumentaci pro vývojáře Apple.|
|Zadaná vstupní aplikace už je zabalená. Zadejte platnou nezabalenou aplikaci.|Nejde zpracovat aplikaci, kterou už nástroj zpracoval. Pokud chcete ke aplikaci znovu zpracovat, spusťte nástroj pomocí původní verze aplikace.|
|Zadaná vstupní aplikace není podepsaná. Zadejte platnou podepsanou aplikaci.|Nástroj pro zabalení aplikace vyžaduje, aby aplikace byla podepsaná. Vyhledejte v dokumentaci pro vývojáře, jak podepsat zabalenou aplikaci.|
|Zadaná vstupní aplikace musí být ve formátu .ipa nebo .app.|Nástroj pro zabalení aplikace přijímá jenom přípony .app a .ipa. Ujistěte se, že vstupní soubor má platnou příponu a je kompilovaný jako soubor .app nebo .ipa.|
|Vstupní aplikace, kterou jste zadali, už je zabalená a má nejnovější verzi šablony zásad.|Nástroj App Wrapping znovu nezabalí stávající zabalenou aplikaci do nejnovější verze šablony zásad.|
|UPOZORNĚNÍ: Nezadali jste hash SHA1 certifikátu. Ujistěte se, že zabalená aplikace je před nasazením podepsaná.|Ověřte, že jste za příznakem příkazového řádku –c zadali platný hash SHA1. |

### <a name="log-files-for-the-app-wrapping-tool"></a>Soubory protokolu pro nástroj App Wrapping
Aplikace zabalené nástrojem App Wrapping generují protokoly, které jsou zapsané do konzoly klientského zařízení s iOS. Tyto informace jsou užitečné, pokud máte s aplikací potíže a potřebujete zjistit, jestli nesouvisí s nástrojem App Wrapping. Pro načtení těchto informací použijte následující kroky:

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


### <a name="certificate-provisioning-profile-and-authentication-requirements"></a>Požadavky na certifikát, profil pro zřizování a ověřování

Aby bylo možné zaručit plnou funkčnost nástroje App Wrapping Tool pro iOS, je potřeba splnit určité požadavky.

|Požadavek|Podrobnosti|
|---------------|-----------|
|Profil pro zřizování iOS|Zkontrolujte platnost zřizovacího profilu, než ho zahrnete. Při zpracování aplikace pro iOS nástroj App Wrapping nekontroluje, jestli vypršela platnost zřizovacího profilu. Když je zadaný profil zřizování s ukončenou platností, bude nástroj pro zabalení aplikace zahrnovat tento profil a vy nepoznáte, jestli existuje problém, dokud neselže instalace aplikace na zařízení s iOS.|
|Podpisový certifikát iOS|Před zadáním podpisového certifikátu zkontrolujte jeho platnost. Nástroj při zpracování aplikací pro iOS nekontroluje, jestli nevypršela platnost certifikátu. Pokud je zadaný hash pro prošlý certifikát, nástroj zpracuje a podepíše aplikaci, ale nenainstaluje ji na zařízení.<br /><br />Zkontrolujte, jestli se certifikát dodaný k podpisu zabalené aplikace shoduje se zřizovacím profilem. Nástroj neověřuje, jestli pro certifikát poskytnutý k podepsání zabalené aplikace existuje shoda ve zřizovacím profilu.|
|Ověřování|Aby šifrování fungovalo, musí mít zařízení PIN. Když se uživatel zařízení, do kterého jste nasadili zabalenou aplikaci, dotkne stavového řádku, musí se znovu přihlásit přes svůj pracovní nebo školní účet. Podle výchozí zásady zabalené aplikace probíhá *ověřování při opakovaném spuštění*. V iOS se každé externí oznámení (třeba při telefonním hovoru) zpracuje tak, že se aplikace ukončí a potom znovu spustí.


## <a name="setting-app-entitlements"></a>Nastavení nároků aplikace
Než aplikaci zabalíte, můžete jí udělit taková *oprávnění*, kterými získá další oprávnění a funkce nad rámec obvyklých možností. Při podepisování kódu se pomocí *souboru oprávnění* určí v aplikaci speciální oprávnění (například přístup ke sdílenému řetězci klíčů). Při vývoji aplikace jsou v prostředí Xcode povolené určité služby aplikace, pro které se také používá označení *schopnosti*. Jakmile se tyto schopnosti povolí, odrazí se to v souboru oprávnění. Další informace o oprávněních a schopnostech najdete v článku věnovaném [přidání schopností](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) na webu iOS Developer Library. Úplný seznam podporovaných schopností najdete v části [Podporované schopnosti](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html).

### <a name="supported-capabilities-for-the-app-wrapping-tool-for-ios"></a>Podporované schopnosti nástroje App Wrapping pro iOS

|Funkce|Popis|Doporučené pokyny|
|--------------|---------------|------------------------|
|Skupiny aplikací|Ve skupinách aplikací můžete více aplikacím povolit přístup ke sdíleným kontejnerům a povolit mezi aplikacemi další komunikaci na úrovni procesů.<br /><br />Pokud chcete povolit skupiny aplikací, otevřete podokno **Schopnosti** a v části **Skupiny aplikací** klikněte na **ZAPNUTO**. Můžete přidat nové skupiny aplikací nebo vybrat stávající.|U skupin aplikací používejte zpětný zápis DNS:<br /><br />*group.com.companyName.AppGroup*|
|Režimy pozadí|Pokud povolíte režimy pozadí, může vaše aplikace pro iOS běžet dál na pozadí.||
|Ochrana dat|Ochrana dat přidá do souborů, které aplikace iOS uložení na disk, úroveň zabezpečení. Ochrana dat využívá integrovaný šifrovací hardware přítomný v určitých zařízeních k ukládání souborů na disk v zašifrovaném formátu. Pokud má vaše aplikace používat ochranu dat, musí být zřízená.||
|Nákupy v aplikaci|Nákupy v aplikaci vloží přímo do aplikace obchod tím, že vám umožní připojit se k obchodu a bezpečně zpracovávat platby uživatele. Nákupy v aplikaci umožňují inkasovat platby za rozšířené funkce a další obsah využitelný v aplikaci.||
|Sdílení řetězce klíčů|Pokud povolíte sdílení řetězce klíčů, můžete aplikace pomocí řetězce klíčů sdílet hesla s jinými aplikacemi, které vyvinul váš tým.|Při sdílení řetězce klíčů použijte zpětný způsob zápisu DNS:<br /><br />*com.companyName.KeychainGroup*|
|Osobní síť VPN|Můžete povolit osobní síť VPN, aby mohla vaše aplikace vytvářet a řídit vlastní systémovou konfiguraci sítě VPN s využitím rámce pro rozšíření sítě.||
|Nabízená oznámení|Služba APNs (Apple Push Notification service) umožňuje aplikaci, která není spuštěná v popředí, zobrazit uživateli oznámení o dostupných informacích.|Nabízená oznámení fungují jenom tehdy, když pro konkrétní aplikaci použijete profil zřizování.<br /><br />Postupujte podle návodu v [dokumentaci pro vývojáře Apple](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html).|
|Konfigurace bezdrátového příslušenství|Když povolíte konfiguraci bezdrátového příslušenství, přidáte do svého projektu rozhraní externího příslušenství a umožníte tím aplikaci nastavit příslušenství MFi s připojením Wi-Fi.||

### <a name="steps-to-enable-entitlements"></a>Postup pro povolení oprávnění

1.  Povolení schopností v aplikaci:

    a.  V prostředí Xcode přejděte do cíle aplikace a klikněte na **Schopnosti**.

    b.  Zapněte příslušné schopnosti. Podrobné informace o jednotlivých schopnostech a o tom, jak určit správné hodnoty, najdete v článku věnovaném [přidání schopností](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) na webu iOS Developer Library.

    c.  Poznamenejte si všechna ID, která v průběhu procesu vytvoříte.

    d.  Sestavte a podepište aplikaci, kterou chcete zabalit.

2.  Ve svém profilu pro zřizování povolte oprávnění:

    a.  Přihlaste se do Centra pro vývojáře Apple.

    b.  Vytvořte pro svoji aplikaci profil pro zřizování. Pokyny najdete v článku věnovaném [splnění předpokladů pro nástroj Intune App Wrapping pro iOS](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/).

    c.  V profilu pro zřizování povolte stejná oprávnění, jaká máte ve své aplikaci. Budete muset zadat stejná ID, která jste zadali během vývoje aplikace.

    d.  Dokončete průvodce zřizovacím profilem a stáhněte si soubor.

3.  Ujistěte se, že jste splnili všechny předpoklady, a zabalte aplikaci.

### <a name="troubleshoot-common-errors-with-entitlements"></a>Řešení potíží s běžnými chybami spojenými s oprávněními
Pokud nástroj App Wrapping pro iOS zobrazí chybu oprávnění, zkuste vyřešit potíže následujícími postupy.

|Problém|Příčina|Řešení|
|---------|---------|--------------|
|Nepodařilo se analyzovat oprávnění vygenerovaná vstupní aplikací.|Nástroj App Wrapping nemůže přečíst soubor oprávnění extrahovaný z aplikace. Soubor oprávnění může být poškozený.|Zkontrolujte soubor oprávnění pro svoji aplikaci. Následující pokyny vysvětlují postup. Při kontrole souboru oprávnění hledejte případy poškozené syntaxe. Soubor by měl být ve formátu XML.|
|V profilu pro zřizování chybí oprávnění (s uvedením chybějících oprávnění). Znovu zabalte aplikaci pomocí profilu pro zřizování, který má tato oprávnění.|Oprávnění povolená v profilu pro zřizování neodpovídají schopnostem povoleným v aplikaci. Tyto rozdíly platí také pro ID přidružená k určitým schopnostem (například skupiny aplikací a přístup k řetězci klíčů).|Obecně platí, že můžete vytvořit nový profil pro zřizování, který povolí stejné schopnosti jako aplikace. Pokud ID v profilu neodpovídají ID v aplikaci, nástroj App Wrapping tato ID nahradí, pokud to bude možné. Pokud se chyba zobrazuje i po vytvoření nového zřizovacího profilu, můžete zkusit aplikaci odebrat oprávnění parametrem –e (viz část Použití parametru –e k odebrání oprávnění z aplikace).|

### <a name="find-the-existing-entitlements-of-a-signed-app"></a>Vyhledání stávajících oprávnění v podepsané aplikaci
Postup pro kontrolu oprávnění v podepsané aplikaci a profilu pro zřizování:

1.  Najděte soubor .ipa a změňte jeho příponu na .zip.

2.  Rozbalte soubor .zip. Vznikne tak složka datové části, která obsahuje sadu .app.

3.  Ke kontrole oprávnění u sady .app použijte nástroj na podpis kódu, kde `YourApp.app` je skutečný název vaší sady .app:

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```

4.  Ke kontrole oprávnění u vloženého zřizovacího profilu aplikace použijte bezpečnostní nástroj, kde `YourApp.app` je skutečný název vaší sady .app:

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```

### <a name="remove-entitlements-from-an-app-by-using-the-e-parameter"></a>Použití parametru –e k odebrání oprávnění z aplikace
Tento příkaz odebere z aplikace všechny povolené schopnosti, které nejsou v souboru oprávnění. Pokud odeberete oprávnění, které aplikace využívá, může ji to poškodit. Příkladem, kdy je možné odebrat chybějící schopnosti, je aplikace vytvořená dodavatelem, která má ve výchozím nastavení všechny schopnosti.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## <a name="security-and-privacy-for-the-app-wrapping-tool"></a>Zabezpečení a ochrana osobních údajů nástrojem App Wrapping
Při používání nástroje App Wrapping použijte následující doporučené postupy pro zabezpečení a ochranu osobních údajů.

-   Podpisový certifikát, zřizovací profil a obchodní aplikace, které zadáte, musí být na stejném počítači s Mac OS, na jakém spouštíte nástroj App Wrapping. Pokud soubory leží na cestě UNC, ověřte, že jsou pro počítač s Mac OS přístupné. Cesta musí být zabezpečená pomocí protokolu IPsec nebo podepsání SMB.

    Zabalená aplikace naimportovaná do konzoly pro správu by měla být na počítači, na kterém jste nástroj spustili. Pokud je soubor v cestě UNC, zajistěte, aby byl přístupný na počítači se spuštěnou konzolou pro správu. Cesta musí být zabezpečená pomocí protokolu IPsec nebo podepsání SMB.

-   Prostředí, do kterého nástroj App Wrapping stahujete z úložiště GitHubu, musí být zabezpečené protokolem IPsec nebo SMB.

-   Zpracovávaná aplikace musí kvůli zajištění ochrany před útoky pocházet z důvěryhodného zdroje.

-   Zkontrolujte, že výstupní složka zadaná v nástroji App Wrapping je zabezpečená. To platí zejména v případě, že jde o vzdálenou složku.

-   V aplikacích pro iOS s dialogovým oknem pro nahrávání souborů mohou uživatelé obejít omezení aplikace, která se vztahují na vyjmutí, kopírování a vložení. Uživatel může například pomocí dialogového okna pro nahrání souboru nahrát snímek obrazovky dat aplikace.

-   Když ze zabalené aplikace monitorujete složku dokumentů v zařízení, může se zobrazit složka s názvem .msftintuneapplauncher. Pokud tuto složku změníte nebo odstraníte, může to mít vliv na správné fungování omezených aplikací.

### <a name="see-also"></a>Viz taky
- [Rozhodování o způsobu přípravy aplikací na jejich správu v Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [Použití sady SDK k povolení správy mobilních aplikací pro aplikace](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Dec16_HO2-->


