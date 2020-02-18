---
title: zahrnout soubor
description: zahrnout soubor
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 11/19/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: d360fa5efe2deba2d19cd67e6ed9f8cbb7f864d9
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415080"
---
Tato oznámení obsahují důležité informace, které vám pomůžou připravit se na budoucí změny a funkce Intune.

### <a name="plan-for-change-change-in-experience-when-enrolling-android-enterprise-dedicated-devices-in-intune--6114580--"></a>Plánování změn: Změna prostředí při registraci vyhrazených zařízení s Androidem Enterprise v Intune<!--6114580-->
Sdíleli jsme se v listopadu vydané verzi, kterou přidáváme podporu pro nasazení certifikátu SCEP na vyhrazená zařízení s Androidem Enterprise, aby bylo možné povolit přístup k profilům Wi-Fi pomocí certifikátů. Tato změna se týká některých drobných změn toků registrace pro vyhrazená podniková zařízení s Androidem. S nadcházející aktualizací Service Update nebo 2003 jsou k dispozici několik dalších změn, o kterých bychom rádi vědomi.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pokud ve svém prostředí spravujete vyhrazená zařízení s Androidem Enterprise, začnete v březnu zobrazovat některé změny.
- Stávající zařízení s Androidem zaregistrovaná před vydáním 22. listopadu 2019 nebo aktualizace služby 1911: na těchto zařízeních je nainstalovaná aplikace Microsoft Intune. Až se změny back-endu zavádějí do služby Intune v březnu, začnou se používat certifikáty SCEP nasazené do zařízení a přidružená k profilům sítě Wi-Fi.
- Pro zařízení, která byla zaregistrována po 22. listopadu 2019 a před tím, než se tato změna vrátí do března: na těchto zařízeních je nainstalovaná aplikace Microsoft Intune. Certifikáty SCEP nasazené do zařízení a přidružených k profilům sítě Wi-Fi budou nadále platit.
- Nové registrace vyhrazených zařízení s Androidem Enterprise po provedení změny v březnu: koncovým uživatelům se během registrace zobrazí jiná sada kroků na zařízeních. Registrace pořád spustí způsob, jakým v současnosti funguje (s identifikátorem QR, NFC, nulovým dotykem nebo identifikátorem zařízení), ale neproběhne žádný povinný krok instalace aplikace. Místo toho se aplikace Microsoft Intune automaticky nainstaluje na zařízení. Kromě toho nebudou muset koncoví uživatelé v průběhu tohoto toku používat možnost Povolit agenta Intune. Certifikáty SCEP přidružené k profilům Wi-Fi můžou být nasazené na tato zařízení.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Můžete si aktualizovat pokyny pro koncové uživatele a dát vaší technickému pracovníkovi informace o této změně. Naši stránku novinky aktualizujeme a upozorníme vás centrem zpráv, když se tato změna začne zavádět.

#### <a name="additional-information"></a>Další informace
[Podpora certifikátů SCEP na vyhrazených zařízeních s Androidem Enterprise](https://aka.ms/Dedicated_devices_enrollment)

### <a name="updated-support-statement-for-adobe-acrobat-reader-for-intune-mobile-app--5746776--"></a>Aktualizovaný příkaz Support pro mobilní aplikaci Adobe Acrobat Reader pro Intune<!--5746776-->
V MC188653 jsme na konci srpna sdíleli, že mobilní aplikace Adobe Acrobat Reader pro Intune dosáhla konce životnosti 1. prosince 2019 a že Adobe plánuje v rámci své hlavní aplikace Acrobat Readeru podporovat zásady ochrany aplikací v Intune. Od té doby jsme dostali zpětnou vazbu od zákazníků, kterou jsme potřebovali k tomu, aby bylo možné pokračovat ve povolování IT správců, a koncovým uživatelům začít používat aplikaci Adobe Acrobat Reader pro Intune. Vzhledem k vysokému využití aplikace Adobe Acrobat Reader pro Intune na zařízeních koncových uživatelů a jejich důležitosti v podnikových scénářích chceme zajistit, aby všechny zkušenosti splňovaly požadavky vaší organizace na ochranu aplikací. 

I když ve vašich zásadách stále doporučujeme cílit na obecnou mobilní aplikaci Acrobat Reader, protože mobilní aplikace Acrobat Reader podporuje zásady ochrany aplikací a integruje sadu Intune SDK, bude i nadále podporována aplikace Adobe Acrobat Reader pro Intune. do 31. března 2020. 

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Tuto zprávu dostáváte, protože naše generování sestav indikuje, že jedna nebo více zásad ve vaší organizaci cílí na aplikaci Adobe Acrobat Reader pro Intune nebo jste dostali předchozí konce ŘÁDKUou komunikaci. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Dejte koncovým uživatelům a helpdesku o této změně. K vytvoření kanálu pro otázky související s Intune můžete použít [funkci informace o podpoře portál společnosti](../apps/company-portal-app.md#support-information) .

#### <a name="additional-information"></a>Další informace
https://helpx.adobe.com/acrobat/kb/intune-app-end-of-life.html


### <a name="end-support-for-windows-phone-81--3544909--"></a>Koncová podpora pro Windows Phone 8,1<!--3544909-->
Hlavní podpora Microsoftu pro Windows Phone 8,1 skončila v červenci 2017 a rozšířená podpora skončila v červnu 2019. Aplikace Portál společnosti pro Windows Phone 8,1 byla v režimu Sustained od října 2017. Microsoft Intune bude nyní ukončena 20. února 2020 pro Windows Phone 8,1.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Po 20. února 2020 tato zařízení neobdrží žádné aktualizace zabezpečení a nebudete moct zaregistrovat žádná nová zařízení. Stávající zařízení Windows Phone 8,1 zůstanou zaregistrovaná (zásady, aplikace, vytváření sestav), ale Všimněte si, že po tomto datu se nebude podporovat jakékoli řešení potíží s existující registrací, protože celá řada komponent, jako jsou certifikáty třetích stran, už ukončila podporu pro platformy. Intune ukončí testování kompatibility s Intune a Windows Phone 8,1.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Můžete si prohlédnout sestavy Intune a zjistit, která zařízení nebo uživatelé to mohou mít vliv. Přejděte na Zařízení > Všechna zařízení a vyfiltrujte si je podle operačního systému. Můžete přidat další sloupce, které vám pomůžou určit, kdo ve vaší organizaci má zařízení s Windows Phone 8,1. Požádejte koncové uživatele, aby svá zařízení upgradovali na podporovanou verzi operačního systému.


### <a name="take-action-use-microsoft-edge-for-your-protected-intune-browser-experience--5728447--"></a>Provést akci: použití Microsoft Edge pro chráněné prostředí Intune Browser<!--5728447-->
Vzhledem k tomu, že jsme provedli sdílení v průběhu minulého roku, Microsoft Edge Mobile podporuje stejnou sadu funkcí správy jako Managed Browser a přitom nabízí mnohem lepší prostředí pro koncové uživatele. Pro zajištění robustních funkcí poskytovaných Microsoft Edgeem Intune Managed Browser vyřazení z provozu. Od 27. ledna 2020 už Intune nebude podporovat Intune Managed Browser.  

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená? 
Od 1. února 2020 už nebude Intune Managed Browser k dispozici v Obchod Google Play nebo v obchodě s aplikacemi pro iOS. V tuto chvíli budete mít i nadále na Intune Managed Browser zacílit nové zásady ochrany aplikací, i když noví uživatelé nebudou moct aplikaci Intune Managed Browser stáhnout. V systému iOS se navíc nové webové klipy, které se odešlou do zařízení zaregistrovaného na MDM, otevřou v Microsoft Edge místo Intune Managed Browser.  

Od března 31 2020 se Intune Managed Browser odebere z konzoly Azure. To znamená, že už nebudete moct vytvářet nové zásady pro Intune Managed Browser. Pokud jste nastavili existující zásady Intune Managed Browser, nebudou ovlivněny. Intune Managed Browser se v konzole zobrazí jako obchodní aplikace bez ikony a stávající zásady se budou zobrazovat jako cílené pro aplikaci. V tuto chvíli také odebereme možnost přesměrovat webový obsah do Intune Managed Browser v části Ochrana dat v zásadách ochrany aplikací.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit? 
K zajištění hladkého přechodu z Intune Managed Browser na Microsoft Edge doporučujeme proaktivně provést následující kroky: 

1. Zaměřte se na Microsoft Edge pro iOS a Android pomocí zásad ochrany aplikací (také označovaných jako MAM) a nastavení konfigurace aplikace. Můžete znovu použít zásady Intune Managed Browser pro Microsoft Edge tím, že tyto existující zásady zacílíte i na Microsoft Edge.  
2. Zajistěte, aby všechny aplikace chráněné MAM ve vašem prostředí měly zásadu ochrany aplikací s nastavením omezit přenos webového obsahu s ostatními aplikacemi nastavenou na prohlížeče spravované zásadami. 
3. Zaměřte se na všechna MAM chráněná nastavením konfigurace spravované aplikace "com. Microsoft. Intune. useEdge" nastavenou na hodnotu true. Počínaje dalším měsícem s vydáním 1911 budete moct provádět kroky 2 a 3 jednoduše tak, že v části Ochrana dat v zásadách ochrany aplikací nastavíte možnost omezit přenos webových obsahu na jiné aplikace. . 

Připravujeme podporu pro webové klipy v iOS a Androidu. Až se tato podpora uvolní, budete muset změnit cílení na existující webové klipy, abyste se ujistili, že se otevřou na Microsoft Edge místo Managed Browser. 

#### <a name="additional-information"></a>Další informace
Další informace najdete v našich dokumentech o [používání Microsoft Edge se zásadami ochrany aplikací](../apps/manage-microsoft-edge.md) , nebo si prohlédněte náš [příspěvek blogu o podpoře](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Use-Microsoft-Edge-for-your-Protected-Intune-Browser-Experience/ba-p/1004269).


### <a name="end-of-support-for-legacy-pc-management"></a>Konec podpory pro správu starších počítačů

Podpora starší verze správy počítačů od 15. října 2020. Upgradujte zařízení na Windows 10 a znovu je zaregistrujte jako zařízení pro správu mobilních zařízení (MDM), abyste je mohli spravovat přes Intune.

[Další informace](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator"></a>Snížení podpory pro správce zařízení s Androidem 
Správce zařízení s Androidem (někdy označovaný jako "starší verze" správy Androidu a vydaný s Androidem 2,2) je způsob, jak spravovat zařízení s Androidem. Vylepšené funkce správy jsou teď ale k dispozici v [Androidu Enterprise](../enrollment/connect-intune-android-enterprise.md) (vydané s androidem 5,0). V úsilí o přechod na moderní, bohatou a bezpečnější správu zařízení bude Google v nových verzích Androidu snížit podporu Správce zařízení.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Vzhledem k těmto změnám od společnosti Google budou mít uživatelé Intune tyto možnosti:  
- Intune bude moct poskytovat úplnou podporu pro zařízení s Androidem spravovaná pomocí Správce zařízení s Androidem 10 nebo novějším prostřednictvím nástroje Q2 CY2020. Zařízení spravovaná správcem zařízení, na kterých běží Android 10 nebo novější, se nebudou moct zcela spravovat. Zvláště ovlivněná zařízení nebudou dostávat nové požadavky na heslo.
    - V tomto období nebude mít vliv na zařízení Samsung KNOX, protože prostřednictvím integrace Intune s platformou Knox je zajištěná Rozšířená podpora. Získáte tak více času k naplánování přechodu mimo správu správy zařízení.    
- Zařízení s Androidem spravovaná správcem zařízení, která zůstávají ve verzích Androidu pod Androidem 10, nebudou ovlivněná a můžou se dál spravovat pomocí Správce zařízení.    
- Pro všechna zařízení s Androidem 10 nebo novějším má Google možnost agentů správy zařízení, jako je Portál společnosti získat přístup k informacím o identifikátoru zařízení. Toto omezení má vliv na následující funkce Intune po aktualizaci zařízení na Android 10 nebo novější:  
    - Řízení přístupu k síti pro VPN už nebude fungovat.   
    - Identifikace zařízení jako vlastněných společností pomocí IMEI nebo sériového čísla nebude automaticky označovat zařízení jako ve vlastnictví firmy.  
    - IMEI a sériové číslo se už nebudou zobrazovat správcům IT v Intune. 
        > [!NOTE]
        > To má vliv jenom na zařízení spravovaná správcem zařízení s Androidem 10 a novějším a nemá vliv na zařízení spravovaná jako Android Enterprise. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Abyste se vyhnuli omezení funkčnosti přicházejícím se do třetího CY2020, doporučujeme následující:
- Nepřidávejte nová zařízení do správy Správce zařízení.
- Pokud se očekává, že zařízení obdrží aktualizaci pro Android 10, migruje ji ze správy správců zařízení na zásady pro Android Enterprise Management a/nebo ochranu aplikací.

#### <a name="additional-information"></a>Další informace
- [Pokyny pro migraci ze strany správce zařízení na Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Dokumentace ke službě Google v plánu pro zařazování rozhraní API pro správce zařízení](https://developers.google.com/android/work/device-admin-deprecation)

### <a name="plan-for-change-intune-app-sdk-and-app-protection-policies-for-android-moving-to-support-android-50-and-higher-in-an-upcoming-release---4911065---"></a>Plánování změn: sada Intune App SDK a zásady ochrany aplikací pro Android, které se přesunou na podporu Android 5,0 a vyšší v nadcházející verzi <!--4911065 -->
V nadcházející verzi se Intune přesune na podporu Androidu 5. x (Lupa) a vyšší. Aktualizujte všechny zabalené aplikace pomocí nejnovější sady Intune App SDK a aktualizujte svá zařízení.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pokud nepoužíváte nebo plánujete použít sadu SDK nebo aplikaci pro Android, tato změna vás nijak neovlivní. Pokud používáte sadu Intune App SDK, nezapomeňte aktualizovat na nejnovější verzi a také aktualizovat zařízení na Android 5. x a vyšší. Pokud aktualizace neaktualizujete, nebudou aplikace dostávat aktualizace a kvalita jejich prostředí se v průběhu času bude zmenšovat.

Níže najdete seznam běžných zařízení zaregistrovaných v Intune, na kterých běží Android verze 4. x. Pokud máte jedno z těchto zařízení, proveďte příslušné kroky, abyste se ujistili, že toto zařízení bude podporovat Android verze 5,0 nebo vyšší nebo že bude nahrazeno zařízením, které podporuje Android verze 5,0 nebo novější. Tento seznam není vyčerpávající pro všechna zařízení, která může být potřeba vyhodnotit:

- Samsung SM – T561  
- Samsung SM – T365
- Samsung GT – I9195
- Samsung SM – G800F
- Samsung SM – G357FZ
- Společnost Motorola XT1080
- Samsung GT – I9305
- Samsung SM – T231

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Zabalte své aplikace pomocí nejnovější sady Intune App SDK. Můžete také nastavit podmíněné nastavení "vyžadovat minimální verzi operačního systému (pouze upozornění)", které upozorní koncové uživatele na osobní zařízení k upgradu.


