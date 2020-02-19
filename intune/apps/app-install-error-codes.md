---
title: Kódy chyb instalace aplikace
titleSuffix: Microsoft Intune
description: Použijte kódy chyb instalace aplikace, které vám pomůžou při řešení problémů s instalací aplikací.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/27/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1a9ce1a881e9a30d0f18cb676e7f7f11c4b5c8b1
ms.sourcegitcommit: ecaff388038fb800f2e646f8efcf8f3b1e2fd1b1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/18/2020
ms.locfileid: "77437830"
---
# <a name="intune-app-installation-error-reference"></a>Reference k chybě instalace aplikace Intune

Kromě kroků uvedených v následujících krocích při řešení chyb aplikací můžete také zjistit konkrétní chyby aplikací na základě vrácených kódů chyb. Po porovnání kódu chyby použijte další popis a informace, které vám pomůžou chybu vyřešit.

## <a name="android-app-installation-errors"></a>Chyby instalace aplikace pro Android

V této části se zmiňují Správce zařízení (DA) i registrace Samsung KNOX. Další informace najdete v tématu [registrace Správce zařízení s Androidem](../enrollment/android-enroll-device-administrator.md) a [Automatická registrace zařízení s Androidem pomocí zápisu mobilních zařízení Samsung pro Samsung](../enrollment/android-samsung-knox-mobile-enroll.md). 

| Kód chyby (Hex) | Kód chyby (prosinec) | Chybová zpráva/kód | Popis |
|--------------------|------------------|---------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0xC7D14FB5 | -942583883 | Aplikaci se nepovedlo nainstalovat.  | Tato chybová zpráva se zobrazí, když Intune nemůže určit hlavní příčinu chyby instalace aplikace pro Android. V systému Android nebyly během selhání poskytnuty žádné informace. Tato chyba se vrátí po úspěšném stažení APK, ale instalace aplikace se nezdařila. K této chybě může často docházet z důvodu chybného souboru APK, který nelze do zařízení nainstalovat. Možnou příčinou může být to, že když Google Play chránit, zablokuje instalaci aplikace kvůli bezpečnostním obavám.   Další možnou příčinou této chyby je, když zařízení aplikaci nepodporuje. Například pokud aplikace vyžaduje rozhraní API verze 21 + a zařízení aktuálně má rozhraní API verze 19. Intune vrátí tuto chybu pro zařízení DIRECTACCESS i KNOX, i když se může jednat o oznámení, že uživatelé můžou kliknout a zkusit to znovu, pokud dojde k nějakému problému s APK, nebude se nikdy dál zdařit. Pokud je aplikace dostupnou aplikací, oznámení může být zavřeno. Pokud je však aplikace požadována, nelze ji zrušit. |
| 0xC7D14FBA | -942583878 | Instalace aplikace se zrušila, protože instalační soubor (APK) se po stažení, ale před instalací, odstranil.  | Soubor APK se úspěšně stáhl, ale byl odebrán ze zařízení ještě předtím, než uživatel nainstaloval aplikaci. K tomu může dojít, pokud došlo k velkému rozdílu mezi stažením a instalací. Například uživatel zrušil původní instalaci, čekal a pak kliknul na oznámení a zkusí to znovu.   Tato chybová zpráva se vrátí jenom pro scénáře DA. Scénáře KNOX se dají dělat Tichě. Připravujeme oznámení, aby se mohl uživatel přijmout, místo aby mohl operaci zrušit. Pokud je aplikace dostupnou aplikací, oznámení může být zavřeno. Pokud je ale aplikace požadovaná, oznámení nelze zavřít. |
| 0xC7D14FBB | -942583877 | Instalace aplikace se zrušila, protože během instalace se proces restartoval.  | Zařízení se restartovalo během procesu instalace APK, což vedlo k zrušené instalaci. Tato chybová zpráva se vrátí pro zařízení DIRECTACCESS i KNOX. Intune prezentuje oznámení, že uživatelé můžou kliknout a zkusit to znovu. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít. |
| 0x87D1041C | -2016345060 | Aplikace nebyla po úspěšném dokončení instalace zjištěna.  | Uživatel aplikaci explicitně odinstaloval. Tuto chybu nevrací klient. Jedná se o chybu, ke které dojde, pokud se aplikace na jednom místě nainstalovala, ale uživatel ji pak odinstaloval. K této chybě by mělo docházet jenom u požadovaných aplikací. Uživatelé můžou odinstalovat aplikace, které nejsou požadované. K této chybě může dojít jenom v DA. KNOX blokuje odinstalaci spravovaných aplikací. Další synchronizace znovu odešle oznámení na zařízení, aby ho uživatel mohl nainstalovat. Uživatel může oznámení ignorovat. Tato chyba bude nadále hlášena, dokud uživatel nenainstaluje aplikaci. |
| 0xC7D14FB2 | -942583886 | Stažení se nezdařilo z důvodu neznámé chyby.  | Tato chyba se zobrazí, když se stažení nezdaří. K této chybě může běžně docházet při problémech s Wi-Fi nebo při pomalém připojení. Tato chyba se vrátí jenom pro scénáře DA. V případě scénářů KNOX není uživatel vyzván k instalaci, a to lze provést v tichém režimu. Intune prezentuje oznámení, že uživatelé můžou kliknout a zkusit to znovu. Pokud je aplikace dostupnou aplikací, oznámení může být zavřeno.   Pokud je ale aplikace požadovaná, oznámení nelze zavřít. |
| 0xC7D15078 | -942583688 | Stažení se nezdařilo z důvodu neznámé chyby. Při příští synchronizaci zařízení se zásady zopakují.  | Tato chyba se zobrazí, když se stažení nezdaří. K této chybě může běžně docházet při problémech s Wi-Fi nebo při pomalém připojení. Tato chyba se vrátí jenom pro scénáře DA. V případě scénářů KNOX není uživatel vyzván k instalaci, a to lze provést v tichém režimu. |
| 0xC7D14FB1 | -942583887 | Koncový uživatel zrušil instalaci aplikace.  | Uživatel aplikaci explicitně odinstaloval. Tato chyba se vrátí, když uživatel zruší aktivitu instalace operačního systému Android. Uživatel po zobrazení výzvy operačního systému k instalaci stiskl tlačítko Zrušit nebo klikl mimo zobrazenou výzvu. Tato chyba se vrátí jenom pro scénáře DA. V případě scénářů KNOX není uživatel vyzván k instalaci, a to lze provést v tichém režimu. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud je aplikace dostupnou aplikací, oznámení může být zavřeno. Pokud je však aplikace požadována, nelze ji zrušit. Požádejte uživatele, aby instalaci nezrušil. |
| 0xC7D15015 | -942583787 | Proces stahování souboru se neočekávaně zastavil.  | Operační systém zastavil proces stahování před jeho dokončením. K této chybě může dojít při nízkém stavu baterie v zařízení nebo když stahování trvá moc dlouho. Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud je aplikace dostupnou aplikací, oznámení může být zavřeno. Pokud je však aplikace požadována, nelze ji zrušit. Ujistěte se, že zařízení má spolehlivé síťové připojení. |
| 0xC7D1507C | -942583684 | Služba Stažení souboru se neočekávaně zastavila. Při příští synchronizaci zařízení se zásady zopakují.  | Operační systém ukončil proces stahování před jeho dokončením. K této chybě může dojít při nízkém stavu baterie v zařízení nebo když stahování trvá moc dlouho. Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení. Ručně synchronizujte zařízení nebo počkejte 24 hodin a ověřte stav. |
| 0xc7d14fb8 | -942583880 | Aplikaci se nepovedlo odinstalovat.  | Tato chyba je obecná chyba při odinstalaci. Operační systém neurčil, proč se aplikaci nepovedlo odinstalovat. Některé aplikace pro správu nejdou jednoduše odinstalovat. Zkontrolujte, jestli je možné aplikaci odinstalovat ručně a shromažďovat protokoly Portál společnosti, pokud se odinstalace nepovede. |
| 0xc7d14fb7 | -942583881 | Instalační soubor APK aplikace, který se používá pro upgrade, se neshoduje s podpisem aktuální aplikace v zařízení.  | Operační systém Android má omezení, které vyžaduje, aby podpisový certifikát pro verzi upgradu byl přesně stejný jako certifikát použitý k podepsání stávající verze. Pokud vývojář nemůže použít stejný certifikát k podepsání nové verze, bude nutné odinstalovat existující aplikaci a znovu nasadit novou aplikaci místo upgradu stávající aplikace. |
| 0xc7d14fb9 | -942583879 | Koncový uživatel zrušil instalaci aplikace.  | Informujte uživatele o přijetí aplikace nasazené v Intune a po zobrazení výzvy aplikaci nainstalujte. |
| 0xc7d14fbc | -942583876 | Odinstalace aplikace se zrušila, protože během instalace se proces restartoval.  | Proces instalace aplikace byl ukončen operačním systémem nebo se zařízení restartovalo.   Pokud k této chybě dojde znovu, zkuste nainstalovat a shromažďovat protokoly Portál společnosti. |
| 0xc7d14fb6 | -942583882 | Instalační soubor aplikace APK nejde nainstalovat, protože nebyl podepsaný.  | Android OS standardně vyžaduje, aby byly aplikace podepsané. Před nasazením zajistěte, aby byla aplikace podepsaná. |
| 0xC7D14FB1  | -942583887 | Koncový uživatel zrušil instalaci aplikace. | Uživatel aplikaci explicitně odinstaloval. Tato chyba se vrátí, když uživatel zruší aktivitu instalace operačního systému Android. Uživatel po zobrazení výzvy operačního systému k instalaci stiskl tlačítko Zrušit nebo klikl mimo zobrazenou výzvu. Tato chyba se vrátí jenom pro scénáře DA. V případě scénářů KNOX není uživatel vyzván k instalaci, a to lze provést v tichém režimu. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud je aplikace dostupnou aplikací, oznámení může být zavřeno. Pokud je však aplikace požadována, nelze ji zrušit. Požádejte uživatele, aby instalaci nezrušil. |
| 0xC7D14FB9 | -942583879 | Koncový uživatel zrušil instalaci aplikace. (Na příkazovém řádku Accept) | Informujte uživatele o přijetí aplikace nasazené v Intune a po zobrazení výzvy aplikaci nainstalujte. |

## <a name="ios-app-installation-errors"></a>chyby instalace aplikace pro iOS

Následující chybové zprávy a popisy poskytují podrobné informace o chybách instalace pro iOS/iPadOS. 

| Kód chyby (Hex) | Kód chyby (prosinec) | Chybová zpráva/kód | Popis a tipy pro řešení potíží |
|--------------------|------------------|------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0x87D12906 | -2016335610 | Chyba agenta Apple MDM: příkaz instalace aplikace se nezdařil bez zadání důvodu chyby. Zkuste instalaci aplikace znovu. | Agent Apple MDM vrátil oznámení, že instalační příkaz selhal. |
| 0x87D1313C | -2016333508 | Síťové připojení na klientovi bylo ztraceno nebo přerušeno. Pozdější pokusy by měly být úspěšné v lepším síťovém prostředí. | Při odesílání aktualizované adresy URL služby stažení do zařízení došlo ke ztrátě síťového připojení. Konkrétně se nepodařilo najít server s určeným názvem hostitele. |
| 0x87D11388 | -2016341112 | zařízení s iOS/iPadOS je momentálně zaneprázdněné.  | Zařízení s iOS/iPadOS bylo zaneprázdněné, což vedlo k chybě. Zařízení bylo uzamčené. Uživatel musí zařízení odemknout, aby se nainstalovala aplikace. |
| 0x87D13B64 | -2016330908 | Instalace aplikace se nezdařila.  | Došlo k chybě instalace aplikace. k odstranění této chyby je potřeba protokol konzoly iOS/iPadOS. |
| 0x87D13B66 | -2016330906 | Aplikace je spravovaná, ale její platnost vypršela nebo odebrala uživatel.  | Buď uživatel explicitně odinstaloval aplikaci, nebo vypršela platnost aplikace, ale stahování se nepovedlo, nebo se detekce aplikace neshoduje s odpovědí ze zařízení.   K této chybě může dojít také v závislosti na chybě platformy iOS/iPadOS 9.2.2. |
| 0x87D13B60 | -2016330912 | Aplikace má naplánovanou instalaci, ale k dokončení transakce potřebuje kód pro uplatnění.  | K této chybě obvykle dochází u aplikací pro iOS Store, které jsou placené. |
| 0x87D1041C | -2016345060 | Aplikace nebyla po úspěšném dokončení instalace zjištěna.  | Proces detekce aplikace se neshodoval s odpovědí ze zařízení. |
| 0x87D13B62 | -2016330910 | Uživatel odmítl nabídku na instalaci aplikace.  | Uživatel během úvodní instalace aplikace klikl na tlačítko Zrušit. Požádejte uživatele, aby požadavek na instalaci přijal příště. |
| 0x87D13B63 | -2016330909 | Uživatel odmítl nabídku na aktualizaci aplikace.  | Koncový uživatel kliknul na zrušit během procesu aktualizace. Nasaďte podle potřeby nebo dodáte uživateli souhlas s výzvou k upgradu. |
| 0x87D103E8 | -2016345112 | Neznámá chyba  | Došlo k neznámé chybě instalace aplikace. Toto je výsledná chyba v případě, že nedošlo k jiným chybám. |
| 0x87D13B93 | -2016330861 | Aplikace VPP se dají instalovat jenom na sdíleném iPadu. | Aplikace se musí získat pomocí Apple Volume Purchase Program k instalaci na sdíleném iPadu. |
| 0x87D13B94 | -2016330860 | Nejde nainstalovat aplikace, když je App Store zakázaný. | Aby uživatel mohl nainstalovat aplikaci, musí být povolený obchod s aplikacemi. |
| 0x87D13B95 | -2016330859 | Nejde najít licenci VPP pro aplikaci. | Zkuste odvolat a znovu přiřadit licenci aplikace. |
| 0x87D13B96 | -2016330858 | Nejde nainstalovat systémové aplikace s vaším poskytovatelem MDM. | Instalace aplikací, které jsou předem nainstalované operačním systémem iOS/iPadOS, není podporovaný scénář. |
| 0x87D13B97 | -2016330857 | Nejde nainstalovat aplikace, když je zařízení v režimu ztráty. | Veškeré použití zařízení je v režimu ztráty blokované. Pokud chcete nainstalovat aplikace, zakažte režim ztráty. |
| 0x87D13B98 | -2016330856 | Nejde nainstalovat aplikace, když je zařízení v celoobrazovkovém režimu. | Pokud chcete nainstalovat aplikace, zkuste toto zařízení přidat do skupiny vyloučení pro zásady konfigurace celoobrazovkového režimu. |
| 0x87D13B9C | -2016330852 | Na tomto zařízení nejde nainstalovat 32-bitové aplikace. | Zařízení nepodporuje instalaci 32 aplikací. Zkuste nasadit 64 verzi aplikace. |
| 0x87D13B99 | -2016330855 | Uživatel se musí přihlásit k App Storu. | Aby bylo možné aplikaci nainstalovat, musí se uživatel přihlásit do App Storu. |
| 0x87D13B9A | -2016330854 | Neznámý problém. Zkuste to prosím znovu. | Instalace aplikace se nezdařila z neznámého důvodu. Opakujte akci později. |
| 0x87D13B9B | -2016330853 | Instalace aplikace se nezdařila. Intune se to pokusí znovu při příští synchronizaci zařízení. | Při instalaci aplikace došlo k chybě zařízení. Synchronizujte zařízení a zkuste aplikaci znovu nainstalovat. |
| 0x87d13b7e | -2016330882 | Přiřazení licence se nezdařilo. Chyba Apple: nejsou zbývající licence VPP.  | Toto chování je záměrné. Pokud to chcete vyřešit, Zakupte další licence VPP nebo licence od uživatelů, které už nejsou cílené. |
| 0x87d13b6e | -2016330898 | Chyba instalace aplikace 12024: Neznámá příčina  | Společnost Apple ještě nedali dostatek informací, abychom zjistili, proč se instalace nezdařila.   Nic k sestavování. |
| 0x87d13b7f | -2016330881 | Nejsou k dispozici požadované zásady konfigurace aplikace, zajistěte, aby byly zásady cílené na stejné skupiny.  | Aplikace vyžaduje konfiguraci aplikace, ale necílí na žádnou konfiguraci aplikace. Správce by měl mít jistotu, že skupiny, na které je aplikace cílena, má také požadovanou konfiguraci aplikace, která je cílem těchto skupin. |
| 0x87d13b69 | -2016330903 | Licencování VPP zařízení se vztahuje jenom na zařízení se systémem iOS/iPadOS 9.0 +.  | Upgrade ovlivněných zařízení se systémem iOS/iPadOS na iOS/iPadOS 9.0 +. |
| 0x87d13b8f | -2016330865 | Aplikace je nainstalována na zařízení, ale není spravována.  | K této chybě dochází pouze v obchodních aplikacích. Aplikace se nainstalovala mimo Intune. Pokud chcete tuto chybu vyřešit, odinstalujte aplikaci ze zařízení. Až dojde k dalšímu synchronizaci zařízení, zařízení by mělo aplikaci nainstalovat z Intune. |
| 0x87d13b68 | -2016330904 | Uživatel odmítl správu aplikací.  | Požádejte uživatele, aby přijal správu aplikací. |
| 0x87d1279d | -2016335971 | Neznámá chyba.  | K této chybě dochází v aplikacích pro iOS Store, ale scénář chyby je neznámý. |
| 0x87D13B9D | -2016330851 | Poslední verzi aplikace se nepovedlo aktualizovat ze starší verze.  | Tato chybová zpráva se zobrazí, pokud je aplikace nainstalovaná a spravovaná, ale má na zařízení nesprávnou verzi. Tato situace zahrnuje situaci, kdy zařízení obdrželo příkaz k aktualizaci aplikace, ale nová verze ještě není nainstalovaná a nahlášená zpět. Tato chyba bude hlášena při prvním vrácení se změnami zařízení po nasazení upgradu a provede se, dokud zařízení neoznámí, že je nainstalována nová verze, nebo dojde k chybě z důvodu jiné chyby. |
| 0x87D13B6F | -2016330897 | Vypršel časový limit vašeho připojení k Intune.  | Chyba ověření manifestu aplikace z důvodu připojení k síti (časový limit) |
| 0x87D13B70 | -2016330896 | Ztratili jste připojení k Internetu.  | Nepovedlo se ověřit manifest aplikace kvůli připojení k síti (nedá se najít hostitel). |
| 0x87D13B72 | -2016330894 | Ztratili jste připojení k Internetu.  | Ověření manifestu aplikace se nezdařilo z důvodu připojení k síti (ztráta připojení). |
| 0x87D13B73 | -2016330893 | Ztratili jste připojení k Internetu.  | Ověření manifestu aplikace se nezdařilo z důvodu síťového připojení (nepřipojeného k Internetu). |
| 0x87D13B77 | -2016330889 | Zabezpečené připojení selhalo.  | Ověření manifestu aplikace se nezdařilo z důvodu připojení k síti (zabezpečené připojení selhalo). |
| 0x87D13B80 | -2016330880 | CannotConnectToITunesStoreError | Instalace aplikace se nezdařila z důvodu neúspěšného připojení k obchodu ITunes |
| 0x87D13B9F  | -2016330849 | Aplikace VPP má k dispozici aktualizaci. | Tento kód se vrátí, když je nainstalována aplikace VPP, ale je k dispozici novější verze. |

## <a name="other-installation-errors"></a>Další chyby instalace

| Kód chyby (Hex) | Kód chyby (prosinec) | Chybová zpráva/kód | Popis |
|--------------------|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0x80073CFF | -2147009281 | (Chyba klienta) | Pro instalaci této aplikace musíte mít systém s podporou zkušebního načtení. Ujistěte se, že je balíček aplikace podepsaný důvěryhodným podpisem a nainstalovaný na zařízení připojeném k doméně, které má povolenou zásadu AllowAllTrustedApps, nebo zařízení, které má licenci pro zkušební načtení systému Windows s povolenou zásadou AllowAllTrustedApps. Další informace najdete v tématu řešení potíží s balíčkem, nasazením a dotazy aplikací pro Windows Store. |
| 0x80CF201C  | -2133909476 | (Chyba klienta) | Pro instalaci této aplikace musíte mít systém s podporou zkušebního načtení. Ujistěte se, že je balíček aplikace podepsaný důvěryhodným podpisem a nainstalovaný na zařízení připojeném k doméně, které má povolenou zásadu AllowAllTrustedApps, nebo zařízení, které má licenci pro zkušební načtení systému Windows s povolenou zásadou AllowAllTrustedApps. Další informace najdete v tématu řešení potíží s balíčkem, nasazením a dotazy aplikací pro Windows Store. |
| 0x80073CF0 | -2147009296 | Balíček je nepodepsaný.     Název vydavatele neodpovídá subjektu podpisového certifikátu.     Informace najdete v protokolu událostí AppxPackagingOM. Další informace najdete v tématu řešení potíží s balíčkem, nasazením a dotazy aplikací pro Windows Store. | Balíček se nepovedlo otevřít. Možné příčiny: |
| 0x80073CF3 | -2147009296 | Příchozí balíček je v konfliktu s nainstalovaným balíčkem.     Nebyla nalezena zadaná závislost balíčku.     Balíček nepodporuje správnou architekturu procesoru.     Informace najdete v protokolu událostí AppXDeployment-Server. Další informace najdete v tématu řešení potíží s balíčkem, nasazením a dotazy aplikací pro Windows Store. | Ověření aktualizace, závislostí nebo konfliktů balíčku se nezdařilo. Možné příčiny: |
| 0x80073CFB | -2147009285 | Zvyšte číslo verze aplikace a pak znovu sestavte a znovu podepište balíček.     Před instalací nového balíčku Odeberte starý balíček pro každého uživatele v systému.     Další informace najdete v tématu řešení potíží s balíčkem, nasazením a dotazy aplikací pro Windows Store.      | Zadaný balíček je už nainstalovaný a přeinstalace balíčku je zablokovaná. Tato chyba se může zobrazit při instalaci balíčku, který není totožný s balíčkem, který už je nainstalovaný. Potvrďte, že digitální podpis je také součástí balíčku. Pokud se balíček znovu vytvoří nebo znovu podepíše, tento balíček už není stejný jako bitový totožný s dřív nainstalovaným balíčkem. Tuto chybu můžete odstranit jedním ze dvou způsobů: |
| 0x87D1041C | -2016345060 | Koncový uživatel tuto aplikaci neodinstaluje.     Informace o identitě v balíčku se neshodují se zprávami o zařízení pro špatné aplikace.     V případě automatických aktualizací MSIs verze produktu neodpovídá informacím aplikace po aktualizaci mimo Intune.     Dejte uživateli pokyn, aby aplikaci znovu nainstaloval z portálu společnosti. Všimněte si, že požadované aplikace se znovu nainstalují automaticky při příštím ověření zařízení. | Instalace aplikace byla úspěšná, ale aplikace se nerozpoznala. Aplikace byla úspěšně nasazena službou Intune a následně odinstalována. Mezi důvody pro odinstalování aplikace patří: |
| 0x8000FFFF | -2147418113 |   | Během instalace došlo k neočekávané chybě. Další informace najdete v protokolech instalace. |

## <a name="next-steps"></a>Další kroky

- Další informace o řešení potíží s Intune najdete v článku [Použití portálu pro řešení potíží k poskytování pomoci uživatelům ve vaší společnosti](../fundamentals/help-desk-operators.md). 
- Zjistěte další informace o známých problémech v Microsoft Intune. Další informace najdete v tématu [úspěšnost zákazníka v Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess).
- Potřebujete další pomoc? Přečtěte si téma [Jak získat podporu pro Microsoft Intune](../fundamentals/get-support.md).