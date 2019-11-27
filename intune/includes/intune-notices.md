---
title: zahrnout soubor
description: zahrnout soubor
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 11/19/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: fa2b1c5c9d267b9f860da2268d03c928ebf7693b
ms.sourcegitcommit: 1cf063c98e1caae00a6e6fab821cc3254562bca9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2019
ms.locfileid: "74309799"
---
Tato oznámení obsahují důležité informace, které vám pomůžou připravit se na budoucí změny a funkce Intune.

### <a name="end-support-for-windows-phone-81--3544909--"></a>Koncová podpora pro Windows Phone 8,1<!--3544909-->
Hlavní podpora Microsoftu pro Windows Phone 8,1 skončila v červenci 2017 a rozšířená podpora skončila v červnu 2019. Aplikace Portál společnosti pro Windows Phone 8,1 byla v režimu Sustained od října 2017. Microsoft Intune bude nyní ukončena 20. února 2020 pro Windows Phone 8,1.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Po 20. února 2020 tato zařízení neobdrží žádné aktualizace zabezpečení a nebudete moct zaregistrovat žádná nová zařízení. Stávající zařízení Windows Phone 8,1 zůstanou zaregistrovaná (zásady, aplikace, vytváření sestav), ale Všimněte si, že po tomto datu nebude podporováno jakékoli řešení potíží s existující registrací, protože celá řada komponent, jako jsou například certifikáty třetích stran, již ukončila podporu pro platformy. Intune ukončí testování kompatibility s Intune a Windows Phone 8,1.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Můžete si prohlédnout sestavy Intune a zjistit, která zařízení nebo uživatelé to mohou mít vliv. Přejděte na Zařízení > Všechna zařízení a vyfiltrujte si je podle operačního systému. Můžete přidat další sloupce, které vám pomůžou určit, kdo ve vaší organizaci má zařízení s Windows Phone 8,1. Požádejte koncové uživatele, aby svá zařízení upgradovali na podporovanou verzi operačního systému.

### <a name="update-your-intune-outlook-app-protection-policies-app--2576686--"></a>Aktualizace zásad ochrany aplikací Intune Outlook (aplikace)<!--2576686-->
Pokud jste v centru zpráv přijali MC195618, možná budete muset provést akci. Jak se sdílí v Microsoft 365 najdete ID funkcí v plánu: 56325 a 56326, Intune a Outlook pro iOS a Android vycházejí z podpory omezování citlivých dat v oznámeních e-mailů a v kalendářích. V důsledku těchto vylepšení bude Outlook pro iOS a Android odebírat podporu pro několik konfiguračních klíčů aplikace ochrany dat, které v tuto chvíli používáte ke správě oznámení.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
I když se nové funkce nedodaly, následující konfigurační klíče aplikace už nebudou fungovat v Outlooku pro iOS a Android:
- com. Microsoft. Outlook. mail. NotificationsEnabled
- com. Microsoft. Outlook. mail. NotificationsEnabled. UserChangeAllowed
- com. Microsoft. Outlook. Calendar. NotificationsEnabled
- com. Microsoft. Outlook. Calendar. NotificationsEnabled. UserChangeAllowed

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Doporučujeme, abyste pro tuto novou funkci nakonfigurovali nastavení ochrany dat pro Intune App Protection zásady organizace s hodnotou "blokovat org data". Od 16. prosince 2019 budou v Outlooku pro iOS a Android začínat nastavení Ochrana dat pro data organizace a už nebude podporovat výše uvedené klíče. Konfigurace tohoto nového nastavení zajistí, že citlivá data nebudou převrácena, pokud výše uvedené konfigurační klíče již nejsou podporovány. Kromě toho Outlook poskytuje další členitost, pokud je nastavení ochrany dat "e-mailová oznámení" nastavená na "blokovat org data" s nastavením další konfigurace aplikace, "oznámení v kalendáři". Kombinace nastavení zásad ochrany aplikací a nastavení konfigurace této aplikace omezuje citlivé informace v oznámeních e-mailů, a přitom vystavuje citlivé informace v oznámeních o kalendáři, aby se uživatelé mohli dostat na své schůze na základě přehledu rychle v oznámení nebo centru oznámení.

#### <a name="additional-information"></a>Další informace
Další informace o nastavení aplikace a nastavení aplikace Outlook najdete tady:
- [Nastavení zásad ochrany aplikací, Android](../apps/app-protection-policy-settings-android.md)
- [Nastavení zásad ochrany aplikací, iOS](../apps/app-protection-policy-settings-ios.md)
- [Nasazení Outlooku pro iOS a nastavení konfigurace aplikací pro Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune)


### <a name="intune-plan-for-change-windows-10-version-1703-company-portal-moving-out-of-support--5026679--"></a>Naplánování změny v Intune: Windows 10, verze 1703 Portál společnosti přesun mimo podporu<!--5026679-->
Windows 10 verze 1703 (označované také jako Windows 10, RS2) se od 8. října 2019 pro edice Enterprise a EDU přesunula mimo službu. Intune ukončí podporu pro odpovídající aplikaci Portál společnosti pro RS2/RS1 od 26. prosince 2019.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Dál, v konkrétní verzi Portál společnosti aplikace se nezobrazí nové funkce, i když budeme dál podporovat tuto verzi aplikace Portál společnosti až do 26. prosince 2019, včetně poskytování všech aktualizací zabezpečení pro Portál společnosti aplikaci jako vyžadována. Vzhledem k tomu, že Windows 10 verze 1703 neobdrží žádné aktualizace zabezpečení po přesunutí ze údržby, důrazně doporučujeme, abyste si aktualizovali zařízení s Windows na novější verzi Windows a zajistili, že jste na nejnovější aplikaci Portál společnosti, abyste mohli dál získat nové funkce a další funkce.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Postup závisí na tom, jak je vaše prostředí nakonfigurované. Obecně byste měli určit zařízení, která mají starší verzi operačního systému, nebo Portál společnosti na svém zařízení a aktualizovat. Pokud chcete nastavit aktualizační kanály Windows 10, přihlaste se k Intune – > aktualizace softwaru – aktualizační kanály Windows 10. Nejnovější verze Portál společnosti je 10.3.5601.0 verze. Požádejte uživatele, aby si ho získali od Microsoft Store, aby se v budoucích verzích stále dosáhlo. Intune taky můžete použít k instalaci nejnovějšího prostředí do zařízení s Windows prostřednictvím [Microsoft Store pro firmy](https://docs.microsoft.com/intune/windows-store-for-business).

#### <a name="additional-information"></a>Další informace
[Ruční přidání aplikace Portál společnosti pro Windows 10 pomocí Microsoft Intune](https://docs.microsoft.com/intune/store-apps-company-portal-app)


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

Připravujeme podporu pro webové klipy v iOS a Androidu. Až se tato podpora uvolní, budete muset změnit cílení na existující webové klipy, abyste se ujistili, že jsou otevřené v Microsoft Edge místo Managed Browser. 

#### <a name="additional-information"></a>Další informace
Další informace najdete v našich dokumentech o [používání Microsoft Edge se zásadami ochrany aplikací](../apps/manage-microsoft-edge.md) , nebo si prohlédněte náš [příspěvek blogu o podpoře](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Use-Microsoft-Edge-for-your-Protected-Intune-Browser-Experience/ba-p/1004269).

### <a name="plan-for-change-updated-experience-when-enrolling-android-enterprise-dedicated-devices-in-intune--5198878--"></a>Plánování změn: aktualizované prostředí při registraci vyhrazených zařízení s Androidem Enterprise v Intune<!--5198878-->
Od verze listopadu nebo 1911 do Intune přidáváme podporu nasazení certifikátu zařízení SCEP pro zařízení s Androidem Enterprise vyhrazená pro povolení přístupu k profilům Wi-Fi pomocí certifikátů. Tato změna zahrnuje také některé menší změny toku při registraci vyhrazených zařízení s Androidem Enterprise.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pokud ve svém prostředí spravujete vyhrazená zařízení s Androidem Enterprise, začnete v listopadu zobrazovat některé změny.

- Pro nové registrace zařízení se systémem Android Enterprise: koncoví uživatelé uvidí během registrace jinou sadu kroků na zařízeních. Registrace pořád spustí způsob, jakým v současné době funguje (se QR, NFC, nulou nebo identifikátorem zařízení), ale po vydání služby bude povinný krok instalace aplikace.
- Stávající zařízení s Androidem zaregistrovaná jako vyhrazená zařízení: Intune začne automaticky instalovat aplikaci Microsoft Intune do zařízení počínaje začátkem listopadu. Nemusíte provádět žádnou akci. Aplikace se automaticky stáhne a nainstaluje na zařízení. 

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Měli byste naplánovat, abyste si aktualizovali pokyny pro koncové uživatele a věděli, že vám tato změna poznala helpdesk. Kliknutím na Další informace zobrazíte další podrobnosti a snímky obrazovky. Až se tato změna začne zavádět, aktualizujeme naši stránku co je nového.

#### <a name="additional-information"></a>Další informace
[https://aka.ms/Dedicated_devices_enrollment](https://aka.ms/Dedicated_devices_enrollment)

### <a name="end-of-support-for-legacy-pc-management"></a>Konec podpory pro správu starších počítačů

Podpora starší verze správy počítačů od 15. října 2020. Upgradujte zařízení na Windows 10 a znovu je zaregistrujte jako zařízení pro správu mobilních zařízení (MDM), abyste je mohli spravovat přes Intune.

[Další informace](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator"></a>Snížení podpory pro správce zařízení s Androidem 
Správce zařízení s Androidem (někdy označovaný jako "starší verze" správy Androidu a vydaný s Androidem 2,2) je způsob, jak spravovat zařízení s Androidem. Vylepšené funkce správy jsou teď ale k dispozici v [Androidu Enterprise](../enrollment/connect-intune-android-enterprise.md) (vydané s androidem 5,0). V úsilí o přechod na moderní, bohatou a bezpečnější správu zařízení bude Google v nových verzích Androidu snížit podporu Správce zařízení.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Vzhledem k těmto změnám od společnosti Google budou mít uživatelé Intune tyto možnosti:  
- Intune bude moct poskytovat podporu jenom pro zařízení s Androidem spravovaná pomocí Správce zařízení s Androidem 10 nebo novějším (označovanou taky jako Android Q) až do letního 2020. Toto datum se očekává, že se má uvolnit další hlavní verze Androidu.   
- Zařízení spravovaná správcem zařízení se systémem Android 10 nebo novějším po léto 2020 již nebudou moci být zcela spravována.       
- Zařízení s Androidem spravovaná správcem zařízení, která zůstávají ve verzích Androidu pod Androidem 10, nebudou ovlivněná a můžou se dál spravovat pomocí Správce zařízení.    
- Pro všechna zařízení s Androidem 10 nebo novějším má Google možnost agentů správy zařízení, jako je Portál společnosti získat přístup k informacím o identifikátoru zařízení. Toto omezení má vliv na následující funkce Intune po aktualizaci zařízení na Android 10 nebo novější:  
    - Řízení přístupu k síti pro VPN už nebude fungovat.   
    - Identifikace zařízení jako vlastněných společností pomocí IMEI nebo sériového čísla nebude automaticky označovat zařízení jako ve vlastnictví firmy.  
    - IMEI a sériové číslo se už nebudou zobrazovat správcům IT v Intune. 
        > [!NOTE]
        > To má vliv jenom na zařízení spravovaná správcem zařízení s Androidem 10 a novějším a nemá vliv na zařízení spravovaná jako Android Enterprise. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Abyste se vyhnuli snížení funkčnosti, které přichází v létě 2020, doporučujeme následující:
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

### <a name="intune-plan-for-change-nearing-end-of-support-for-windows-7---3042987---"></a>Plán změny v Intune: blíží se konec podpory pro Windows 7.<!-- 3042987 -->
Stejně jako v MC148476, který jsme odeslali v, od poslední září 2018 a znovu v MC176794 zpátky v březnu 2019, Windows 7 dosáhne konce rozšířené podpory 14. ledna 2020. V tuto chvíli Intune vyřadí podporu pro zařízení s Windows 7, takže můžeme soustředit na naši investici do podpory novějších technologií a zajistit Skvělé nové prostředí pro koncové uživatele. Po tomto datu se v Intune už nebude k dispozici technická pomoc a automatické aktualizace, které vám pomůžou chránit počítač s Windows 7. Společnost Microsoft důrazně doporučuje přejít na Windows 10 před lednem 2020, aby nedocházelo k situaci, kdy potřebujete službu nebo podporu, která už není dostupná. Další informace o životním cyklu podpory pro Windows [najdete tady](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Tuto zprávu dostáváte, protože aktuálně spravujete počítače se systémem Windows 7 pomocí starší verze softwarového agenta Intune pro počítače. Vzhledem k tomu, že zbývá méně než rok, než je prodloužená podpora Windows 7, důrazně doporučujeme vaší organizaci začít upgradovat na Windows 10, jakmile to bude možné.  

Možnosti správy počítačů se vytvářejí přímo v operačním systému Windows 10 a už nemusíte instalovat klientského agenta, jako je softwarový klient Intune pro Windows 7. Od Windows 8.1 používá společnost Microsoft architekturu správy mobilních zařízení (MDM) ke zřízení, konfiguraci, aktualizaci a správě počítačů s Windows. Když nastavíte Intune, můžete zjednodušit registraci zařízení s Windows 10 tak, že [do Intune zaregistrujete počítače s Windows 10](..\windows-enroll.md) prostřednictvím kanálu MDM. Pro správu počítačů s Windows 10 doporučujeme použít toto řešení správy MDM bez agenta.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Doporučujeme, aby vaše organizace okamžitě zvážila tento akční plán:

- Naplánujte a upgradujte loďstev Windows 7 na Windows 10 do 14. ledna 2020.
- V článku [Podpora nasazení Windows 10](https://docs.microsoft.com/windows/deployment/) najdete další informace o tom, jak upgradovat stávající loďstvo počítačů s Windows 7 na Windows 10.
- Seznamte se s tím, jak [desktopová aplikace](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure?rtc=1) nabízí nabídku inFastTrack, která vám pomůže s příslibem kompatibility aplikací Microsoftu.
- Převeďte stávající starší verze spravovaných softwarových klientů Intune do řešení doporučeného společností Microsoft pro správu Windows 10 pomocí správy MDM. Zaregistrujte všechny nové počítače s Windows 10 pomocí správy MDM pro Intune v Azure Portal.

Další informace najdete v tomto [blogovém příspěvku](https://aka.ms/Windows7_Intune) .


