---
title: Archiv novinek | Microsoft Intune
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 861b5ea3bb0772d2853942e2b3f11f607dad3774
ms.openlocfilehash: 25128cfe93280e38a03779a7e6f38ddeb3c15612


---
# <a name="whats-new-archive"></a>Archiv novinek

Tato stránka představuje archiv nedávných oznámení uvedených na stránce s [novinkami v Microsoft Intune](whats-new-in-microsoft-intune.md).

## <a name="september-2016"></a>Září 2016
### <a name="new-features-announcements-and-information"></a>Nové funkce, oznámení a informace
* [Podmíněný přístup pro Windows](#windows-conditional-access)
* [Podpora pro iOS 10](#ios-10-support)
* [Nástroj App Wrapping podporuje MAM bez registrace zařízení pro Android a iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Přechod od skupin Intune ke skupinám Azure Active Directory od září](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Integrace aplikace Lookout pro ochranu zařízení s Androidem](#lookout-integration-to-protect-android-devices)
* [Aktualizace aplikace Portál společnosti pro Android, iOS a Windows](#company-portal-updates)
* [Glosář služby Intune](#intune-glossary)
* [Co připravujeme](#whats-coming)

### <a name="windows-conditional-access"></a>Podmíněný přístup pro Windows
Nově můžete přes konzolu správce Intune vytvářet zásady podmíněného přístupu, které budou počítačům s Windows blokovat přístup ke službám Exchange Online a SharePoint Online. Taky můžete vytvářet zásady podmíněného přístupu, které budou blokovat přístup k desktopovým a univerzálním aplikacím Office.

### <a name="ios-10-support"></a>Podpora pro iOS 10
Stávající scénáře Intune MDM a MAM jsou kompatibilní se systémem iOS 10. Tipy naleznete na [blogu týmu podpory služby Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>Nástroj App Wrapping podporuje MAM bez registrace zařízení pro Android a iOS
Nástroj Intune App Wrapping je nástroj příkazového řádku, který slouží k aktivaci Intune MAM v obchodních aplikacích (LOB) pro iOS a Android. Jedná se o nejjednodušší způsob, jak začlenit sadu Intune MAM SDK do vaší aplikace, aby vaše aplikace vynucoval zásady MAM nasazené prostřednictvím služby Intune. Zásady MAM vám umožňují:

1. Zašifrovat data aplikace.
2. Požadovat, aby informační pracovník při spuštění aplikace zadal PIN.
3. Povolit aplikaci přenášet data pouze do ostatních spravovaných aplikací.
4. Zabránit aplikaci zálohovat data do Androidu, iTunes a iCloudu.
5. Povolit vyjmutí, kopírování a vložení z a do pouze ostatních spravovaných aplikací.

Veřejná verze Preview aktualizovaného nástroje Intune App Wrapping nyní podporuje MAM bez registrace zařízení na interních obchodních aplikacích v systémech iOS a Android. To znamená, že koncoví uživatelé mohou používat obchodní aplikace s podporou MAM, aniž by museli svá zařízení registrovat ve službě Intune.

Tuto veřejnou verzi Preview si může kdokoli vyzkoušet a přečíst si užitečnou dokumentaci na GitHubu ve složce msintuneappsdk:

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Před instalací předběžné verze nástroje Microsoft Intune App Wrapper pro Android a iOS si musíte:

* Znovu projít licenční podmínky společnosti Microsoft pro předběžnou verzi nástroje Microsoft Intune App Wrapping pro Android a iOS
* Vytisknout a uchovat pro své záznamy kopii licenčních podmínek. Stažením a používáním předběžné verze nástroje Microsoft Intune App Wrapping pro Android s těmito licenčními podmínkami souhlasíte. Pokud je nepřijímáte, software nepoužívejte.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>Přechod od skupin Intune ke skupinám Azure Active Directory od září
Některé nové účty Intune budou namísto skupin uživatelů Intune používat skupiny zabezpečení služby Azure Active Directory. Budete vědět, že pracujete se skupinami zabezpečení, jelikož stránka se skupinami na portálu Intune bude obsahovat odkaz na portál pro správu Azure.

### <a name="lookout-integration-to-protect-android-devices"></a>Integrace aplikace Lookout pro ochranu zařízení s Androidem
Společnost Microsoft integruje řešení ochrany před mobilními hrozbami v aplikaci Lookout za účelem ochrany mobilních zařízení s Androidem pomocí zjišťování malwaru, riskantních aplikací a dalších problémů na zařízení. Řešení Lookout vám pomůže určit úroveň ohrožení, která je konfigurovatelná. Ve službě Intune můžete vytvořit pravidlo zásad dodržování předpisů na základě vyhodnocování rizik aplikací Lookout. Pomocí zásad podmíněného přístupu můžete povolit nebo blokovat přístup k prostředkům společnosti na základě stavu dodržování předpisů pro zařízení.

Koncoví uživatelé zařízení nesplňujících požadavky budou vyzvání k registraci. Dále si budou muset před získáním přístupu nainstalovat na zařízení s Androidem aplikaci Lookout for Work, aktivovat ji a opravit hrozby nahlášené aplikací Lookout for Work. Další informace najdete v článku [Omezení přístupu na základě rizika zařízení, sítě a aplikace](restrict-access-based-on-device-network-app-risk.md).


### <a name="company-portal-updates"></a>Aktualizace Portálu společnosti

__Android__

<p style="margin-left: 40px">**Přidání oznámení do aplikace Portál společnosti pro Android**<br/>
<p style="margin-left: 40px">Na domovskou stránku aplikace Portál společnosti pro Android byla přidaná nová ikona oznámení. Klepnutí na tuto ikonu otevře stránku Oznámení, kde se koncovým uživatelům zobrazí všechny položky, které v aplikaci Portál společnosti vyžadují pozornost (například že nějaké zařízení nedodržuje předpisy, zpráva o aktualizaci registrací nebo aktivaci registrací). Aplikace Portál společnosti pro iOS už tato oznámení má. Po zavedení stránky Oznámení se už při každém spuštění nebo obnovení aplikace Portál společnosti pro Android nezobrazí stránka Nastavení firemního přístupu, pokud je zařízení už zaregistrované. Pokud vytvoříte vlastní návod pro koncové uživatele, nezapomeňte tuto změnu do dokumentace promítnout. Aktualizované snímky obrazovky najdete [tady](https://aka.ms/androidcpupdate).  

__iOS__
<p style="margin-left: 40px">**Změny v podpoře pro aplikaci Portál společnosti pro iOS**<br/>
<p style="margin-left: 40px">Od všech uživatelů aplikace Portál společnosti pro iOS se nyní vyžaduje, aby používali její nejnovější verzi. Noví uživatelé si mohou stáhnout jenom nejnovější verzi a aktuální uživatelé si musí aplikaci aktualizovat. Nejnovější verze vyžaduje iOS 8.0 nebo novější, takže zařízení se starší verzí iOS nemohou Portál společnosti používat ani nebudou moct zařízení zaregistrovat, dokud si v něm neaktualizují operační systém na iOS 8.0 nebo novější a následně neaktualizují i aplikaci Portál společnosti na nejnovější verzi. Zaregistrovaná zařízení se systémem iOS starším 8.0 se budou spravovat i nadále a budou se zobrazovat v konzole správce Intune.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Vylepšení způsobu, kterým koncoví uživatelé iOS získávají svoje aplikace**<br/>
<p style="margin-left: 40px">Pro dlaždice aplikací v aplikaci Portál společnosti pro iOS byly provedeny následující změny tak, aby uživatele u všech aplikací odkazovaly na různá zobrazení v jednom umístění – na webu Portál společnosti. Omezení společnosti Apple zakazují, aby se obchodní a spravované aplikace z App Storu zobrazovaly v aplikaci Portál společnosti. Uživatel tak k vyhledání všech svých aplikací musí použít několik zobrazení.

<p style="margin-left: 40px">Dlaždice **Firemní aplikace** dříve odkazovala na seznam všech aplikací na kartě VŠE na webu Portál společnosti a bude tak fungovat i dál. Název dlaždice byl změněn na **Všechny aplikace**.

<p style="margin-left: 40px">Dlaždice **Ostatní aplikace** dříve odkazovala na zobrazení v aplikaci Portál společnosti, ve kterém je uvedený seznam všech aplikací, které Apple aplikaci Portál společnosti povoluje zobrazit. Název dlaždice byl změněn na **Doporučené aplikace**. Po klepnutí na tuto dlaždici uživatelé přejdou na kartu DOPORUČENÉ na webu Portál společnosti.

<p style="margin-left: 40px">Dlaždice **Kategorie** dříve odkazovala na zobrazení v aplikaci Portál společnosti, ve kterém je uvedený seznam kategorií aplikací. Název této dlaždice nebyl změněn, ale nyní odkazuje na kartu KATEGORIE na webu Portál společnosti. Aktualizované snímky obrazovky najdete [tady](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
  <!---TFS 1317133--->

<p style="margin-left: 40px">**Výzva k instalaci aplikace Spravovaný prohlížeč pro iOS, pokud IT specialista nastavil tento požadavek pro aplikaci**<br/>
<p style="margin-left: 40px">Pokud jste nakonfigurovali webový klip tak, aby se otevíral jenom ve spravovaném prohlížeči, a spravovaný prohlížeč není v zařízení nainstalovaný, aplikace Portál společnosti vyzve uživatele, aby nejdřív nainstaloval spravovaný prohlížeč. Teprve potom bude možné nainstalovat příslušný webový klip.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**Přidání tlačítka pro odeslání názoru do aplikace Portál společnosti pro Windows Phone 8.1**<br/>
<p style="margin-left: 40px">Portál společnosti pro Windows Phone 8.1 koncovým uživatelům umožňuje odeslat zpětnou vazbu o aplikaci. Slouží k tomu tlačítko „Odeslat názor“. Tlačítko najdete tak, že klepnete na třítečkovou nabídku v dolní pravé části obrazovky aplikace Portál společnosti a potom na **Odeslat názor**. Shromážděná anonymizovaná zpětná vazba pomůže Microsoftu zlepšit prostředí aplikace Portál společnosti.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Glosář služby Intune</br>
Do knihovny jsme přidali nové téma [Glosář](https://docs.microsoft.com/intune/understand-explore/intune-glossary), abychom vám pomohli správně chápat některé termíny používané ve službě Intune.

### <a name="see-also"></a>Viz taky
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Nov16_HO2-->


