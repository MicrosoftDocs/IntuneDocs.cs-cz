---
title: "Co je nového | Microsoft Intune"
description: "Zjistěte, co je nového v aktualizací služby Microsoft Intune v tomto měsíci nebo dříve"
keywords: 
author: Lindavr
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 03a5dd14b854fedf7e2cb5b949580960a0eab9de
ms.openlocfilehash: 1d09e5a0adb3ecfa8f2d64f668ea7ff16bdf31fa


---

# Co je nového v Microsoft Intune – září
Zjistěte, co je nového v této verzi Microsoft Intune. Můžete také získat informace o nadcházejících změnách, se kterými byste měli počítat, a o minulých verzích.

Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

>[!IMPORTANT]
>Příspěvek blogu – aktualizace mobilních zařízení pomocí Microsoft Intune<br>
>S ohledem na nedávné útoky malwaru Trident na zařízení s iOS jsme zveřejnili nový příspěvek blogu věnovaný [zajištění aktuálnosti mobilních zařízení pomocí Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/). Pomůže vám seznámit se s různými způsoby, kterými Intune může zajistit zabezpečení a aktuálnost vašich zařízení.

## Podpora pro iOS 10
Stávající scénáře Intune MDM a MAM jsou kompatibilní se systémem iOS 10. Tipy naleznete na [blogu týmu podpory služby Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

## Nástroj App Wrapping podporuje MAM bez registrace zařízení pro Android a iOS
Nástroj Intune App Wrapping je nástroj příkazového řádku, který slouží k aktivaci Intune MAM v obchodních aplikacích (LOB) pro iOS a Android. Jedná se o nejjednodušší způsob, jak začlenit sadu Intune MAM SDK do vaší aplikace, aby vaše aplikace vynucoval zásady MAM nasazené prostřednictvím služby Intune. Zásady MAM vám umožňují:

1. Zašifrovat data aplikace.
2. Požadovat, aby informační pracovník při spuštění aplikace zadal PIN.
3. Povolit aplikaci přenášet data pouze do ostatních spravovaných aplikací.
4. Zabránit aplikaci zálohovat data do Androidu, iTunes a iCloudu.
5. Povolit vyjmutí, kopírování a vložení z a do pouze ostatních spravovaných aplikací.

Veřejná verze Preview aktualizovaného nástroje Intune App Wrapping nyní podporuje MAM bez registrace zařízení na interních obchodních aplikacích v systémech iOS a Android. To znamená, že koncoví uživatelé mohou používat obchodní aplikace s podporou MAM, aniž by museli svá zařízení registrovat ve službě Intune.

Tuto veřejnou verzi Preview si může kdokoli vyzkoušet a přečíst si užitečnou dokumentaci na GitHubu ve složce msintuneappsdk:

http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Před instalací předběžné verze nástroje Microsoft Intune App Wrapper pro Android a iOS si musíte:

* Znovu projít licenční podmínky společnosti Microsoft pro předběžnou verzi nástroje Microsoft Intune App Wrapping pro Android a iOS
* Vytisknout a uchovat pro své záznamy kopii licenčních podmínek. Stažením a používáním předběžné verze nástroje Microsoft Intune App Wrapping pro Android s těmito licenčními podmínkami souhlasíte. Pokud je nepřijímáte, software nepoužívejte.
<!---TFS 1235607--->

## Přechod od skupin Intune ke skupinám Azure Active Directory od září
Některé nové účty Intune budou namísto skupin uživatelů Intune používat skupiny zabezpečení služby Azure Active Directory. Budete vědět, že pracujete se skupinami zabezpečení, jelikož stránka se skupinami na portálu Intune bude obsahovat odkaz na portál pro správu Azure.

## Integrace aplikace Lookout pro ochranu zařízení s Androidem
Společnost Microsoft integruje řešení ochrany před mobilními hrozbami v aplikaci Lookout za účelem ochrany mobilních zařízení s Androidem pomocí zjišťování malwaru, riskantních aplikací a dalších problémů na zařízení. Řešení Lookout vám pomůže určit úroveň ohrožení, která je konfigurovatelná. Ve službě Intune můžete vytvořit pravidlo zásad dodržování předpisů na základě vyhodnocování rizik aplikací Lookout. Pomocí zásad podmíněného přístupu můžete povolit nebo blokovat přístup k prostředkům společnosti na základě stavu dodržování předpisů pro zařízení.

Koncoví uživatelé zařízení nesplňujících požadavky budou vyzvání k registraci. Dále si budou muset před získáním přístupu nainstalovat na zařízení s Androidem aplikaci Lookout for Work, aktivovat ji a opravit hrozby nahlášené aplikací Lookout for Work. Další informace najdete v článku [Omezení přístupu na základě rizika zařízení, sítě a aplikace](restrict-access-based-on-device-network-app-risk.md).


## Aktualizace aplikace Portál společnosti

### Android

**Přidání oznámení do aplikace Portál společnosti pro Android**<br/>
Na domovskou stránku aplikace Portál společnosti pro Android byla přidaná nová ikona oznámení. Klepnutí na tuto ikonu otevře stránku Oznámení, kde se koncovým uživatelům zobrazí všechny položky, které v aplikaci Portál společnosti vyžadují pozornost (například že nějaké zařízení nedodržuje předpisy, zpráva o aktualizaci registrací nebo aktivaci registrací). Aplikace Portál společnosti pro iOS už tato oznámení má. Po zavedení stránky Oznámení se už při každém spuštění nebo obnovení aplikace Portál společnosti pro Android nezobrazí stránka Nastavení firemního přístupu, pokud je zařízení už zaregistrované. Pokud vytvoříte vlastní návod pro koncové uživatele, nezapomeňte tuto změnu do dokumentace promítnout. Aktualizované snímky obrazovky najdete [tady](https://aka.ms/androidcpupdate).  
<!---TFS 1095560--->


### iOS
**Změny v podpoře pro aplikaci Portál společnosti pro iOS**<br/>
Od všech uživatelů aplikace Portál společnosti pro iOS se nyní vyžaduje, aby používali její nejnovější verzi. Noví uživatelé si mohou stáhnout jenom nejnovější verzi a aktuální uživatelé si musí aplikaci aktualizovat. Nejnovější verze vyžaduje iOS 8.0 nebo novější, takže zařízení se starší verzí iOS nemohou Portál společnosti používat ani nebudou moct zařízení zaregistrovat, dokud si v něm neaktualizují operační systém na iOS 8.0 nebo novější a následně neaktualizují i aplikaci Portál společnosti na nejnovější verzi. Zaregistrovaná zařízení se systémem iOS starším 8.0 se budou spravovat i nadále a budou se zobrazovat v konzole správce Intune.
<!---TFS 1283165--->

**Vylepšení toho, jak koncoví uživatelé iOS získají svoje aplikace**<br/>
Pro dlaždice aplikací v aplikaci Portál společnosti pro iOS byly provedeny následující změny tak, aby uživatele u všech aplikací odkazovaly na různá zobrazení v jednom umístění – na webu Portál společnosti. Omezení společnosti Apple zakazují, aby se obchodní a spravované aplikace z App Storu zobrazovaly v aplikaci Portál společnosti. Uživatel tak k vyhledání všech svých aplikací musí použít několik zobrazení.

- Dlaždice **Firemní aplikace** dříve odkazovala na seznam všech aplikací na kartě VŠE na webu Portál společnosti a bude tak fungovat i dál. Název dlaždice byl změněn na **Všechny aplikace**.
- Dlaždice **Ostatní aplikace** dříve odkazovala na zobrazení v aplikaci Portál společnosti, ve kterém je uvedený seznam všech aplikací, které Apple aplikaci Portál společnosti povoluje zobrazit. Název dlaždice byl změněn na **Doporučené aplikace**. Po klepnutí na tuto dlaždici uživatelé přejdou na kartu DOPORUČENÉ na webu Portál společnosti.
-  Dlaždice **Kategorie** dříve odkazovala na zobrazení v aplikaci Portál společnosti, ve kterém je uvedený seznam kategorií aplikací. Název této dlaždice nebyl změněn, ale nyní odkazuje na kartu KATEGORIE na webu Portál společnosti.
Aktualizované snímky obrazovky najdete [tady](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

**Výzva k instalaci aplikace Spravovaný prohlížeč pro iOS, pokud IT specialista tento požadavek pro aplikaci nastavil**<br/>
Pokud jste nakonfigurovali webový klip tak, aby se otevíral jenom ve spravovaném prohlížeči, a spravovaný prohlížeč není v zařízení nainstalovaný, aplikace Portál společnosti vyzve uživatele, aby nejdřív nainstaloval spravovaný prohlížeč. Teprve potom bude možné nainstalovat příslušný webový klip. 
<!---TFS 1228570--->

### Windows
**Přidání tlačítka pro odeslání zpětné vazby do aplikace Portál společnosti pro Windows Phone 8.1**<br/>
Portál společnosti pro Windows Phone 8.1 koncovým uživatelům umožňuje odeslat zpětnou vazbu o aplikaci. Slouží k tomu tlačítko „Odeslat názor“. Tlačítko najdete tak, že klepnete na třítečkovou nabídku v dolní pravé části obrazovky aplikace Portál společnosti a potom na **Odeslat názor**. Shromážděná anonymizovaná zpětná vazba pomůže Microsoftu zlepšit prostředí aplikace Portál společnosti.
<!---TFS 1317806--->


## Co připravujeme

### Přechod od skupin Intune ke skupinám Azure Active Directory
Intune vytváří nové prostředí pro správu skupin, které využívá skupiny zabezpečení Azure Active Directory (AAD) a skupiny uživatelů a zařízení v Intune. Tyto skupiny se budou využívat pro veškerou správu skupin a nasazování zásad a profilů, **až zavedeme nový portál pro správu Intune s využitím Azure**.

Toto nové prostředí vás zbaví nutnosti mít mezi službami duplicitní skupiny, **umožní přístup k některým novým funkcím skupin Azure Active Directory Premium (AADP)** a zajistí možnosti rozšíření prostřednictvím PowerShellu a Graphu. Sjednotí se tak i prostředí správy skupin napříč správou podnikové mobility.

Pro zajištění přechodu ke skupinám zabezpečení dojde v **aktuální konzole pro správu** k určitým úpravám. **Tyto změny a také použití skupin zabezpečení AAD budou popsané v dokumentaci k Intune**.

Zákazníci, kteří s Intune začínají, se s **některými změnami skupin zabezpečení setkají dříve než aktuální tenanti**.

Kromě změn ve správě skupin se také **přestanou používat následující funkce**:
- Vyloučení členů nebo skupin při vytvoření nové skupiny
- Skupiny **Neseskupení uživatelé** a **Neseskupená zařízení**
- **Správa skupin** v roli Správce služby
- Vlastní výstrahy na základě skupin pro pravidla oznámení
- Přesun skupin v sestavách
<!--- TFS 1295329--->

### Nové zásady podmíněného přístupu aplikací pro Exchange Online a SharePoint Online
Budete moci omezit přístup ke službám Exchange Online a SharePoint Online tak, aby k nim bylo možné přistupovat jenom z mobilních aplikací Office, jako jsou Outlook, Word, Excel a OneDrive. Tato nová funkce vhodně doplňuje zásady správy mobilních aplikací (MAM) Intune, protože vám umožní blokovat přístup do integrovaných klientů elektronické pošty nebo dalších aplikací, které nebyly nakonfigurovány na vynucování zásad Intune MAM. Tím zajistíte, že uživatelé mají přístup k datům vaší organizace prostřednictvím aplikací, které mohou být chráněny pomocí služby Intune MAM. Se správou mobilních aplikací Intune můžete začít prostřednictvím webu Azure Portal. V okně Nastavení hledejte novou sekci Podmíněný přístup.



### Zastaralá služba

- **Aplikace Portál společnosti pro Windows 8 a Windows Phone 8 se přestanou používat** <br/>
Od října 2016 přestane Microsoft Intune poskytovat podporu aplikacím Portál společnosti pro Windows 8 a Windows Phone 8. Microsoft Intune také přestat poskytovat podporu pro platformu Windows Phone 8. V důsledku toho nebude možné registrovat ani aktualizovat žádná zařízení Windows Phone 8. Zařízení Windows Phone 8 a Windows 8, která jsou již zaregistrována, můžete nadále spravovat. Pokud budete chtít do zařízení s těmito systémy dál bez přerušení distribuovat aplikace, aktualizujte si zařízení Windows 8 a Windows Phone 8 na Windows 8.1 a Windows Phone 8.1 a začněte používat odpovídající aplikaci Portál společnosti pro Windows 8.1 a Windows Phone 8.1.



### Průvodce cloudem
Udržujte si přehled o budoucích novinkách pro Intune díky [průvodci cloudovou platformou](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).


## Předchozí verze Intune
Informace o tom, co bylo vydáno v rámci Intune během posledních šest měsíců, najdete v článku [Předchozí verze Intune](previous-intune-releases.md).

### Související témata
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Sep16_HO3-->


