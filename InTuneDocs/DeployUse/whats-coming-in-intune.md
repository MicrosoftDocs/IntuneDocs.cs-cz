---
title: "Co připravujeme | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 500cc93b595e04cea987bda699abf94ae010443a
ms.openlocfilehash: f45fc02003c6b40cc15fabeffff35cf0cde1a830


---

# Co v Microsoft Intune připravujeme – srpen
Tyto informace jsou poskytovány na základě smlouvy o utajení (NDA) ve velmi omezené míře a mohou podléhat změnám. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a mohou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moci zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se prosím na příslušný kontakt (Intune/PM).

Tato stránka se pravidelně aktualizuje. Vracejte se na ni, abyste zjistili, jaké aktualizace připravujeme.

Následující změny v Intune jsou ve vývoji. Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Správa aplikací
### Skryté a zobrazené aplikace pro iOS 9.3
U zařízení se systémem iOS 9.3 nebo novějším, která jsou pod dohledem, bude možné využít seznam skrytých a zobrazených aplikací v zásadách obecné konfigurace iOS k těmto akcím:
- Určení seznamu aplikací, které budou uživatelům skryté. Uživatelé nebudou moci tyto aplikace zobrazit ani spustit.
- Určení seznamu aplikací, které uživatelé mohou zobrazit a spustit. Žádné jiné aplikace nebude možné zobrazit ani spustit.

Mezi aplikace, které můžete zadat, patří aplikace, které jste nasadili, a integrované aplikace pro iOS, jako jsou Zprávy a Poznámky.
<!---TFS 1279009--->

### Zásady povolených a blokovaných aplikací pro zařízení se systémem Samsung KNOX

Nyní můžete pro zařízení se systémem Samsung KNOX nakonfigurovat vlastní zásady, které umožňují vytvořit:
- Seznam aplikací, u kterých je v příslušném zařízení blokované spuštění. Aplikace, které jsou definované v seznamu blokovaných aplikací, nejde na zařízení aktivovat, ani když jsou nainstalované.
- Seznam aplikací, které si uživatelé příslušného zařízení mohou nainstalovat z obchodu Google Play. Z tohoto obchodu nejde nainstalovat žádné další aplikace.

Tato nastavení mohou využívat jenom zařízení se systémem Samsung KNOX.
<!--- For details, see [Use custom policies to allow and block apps for Samsung KNOX devices]( custom-policy-to-allow-and-block-samsung-knox-apps.md)--->
<!---TFS 1311629 --->

### Nové aplikace kompatibilní se zásadami správy mobilních aplikací (MAM)
Aplikace Yammer pro [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) a [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) bude kompatibilní se [zásadami správy mobilních aplikací (MAM) služby Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) bez ohledu na to, jestli je zařízení zaregistrované.

Kompletní seznam aplikací kompatibilních s MAM najdete na webu [aplikací pro Microsoft Intune od partnerů](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336--->

## Správa zařízení
### Podpora pro Android 7.0
V srpnu bude Intune poskytovat podporu „dne 0“ pro chystaný operační systém Android 7.0 pro mobilní zařízení.
<!---TFS 1262053--->
### Odebrání funkce pro vzdálené resetování hesla v zařízeních se systémem Android 7.0
Google odebírá správcům IT a koncovým uživatelům možnost vzdáleně resetovat hesla na zařízeních se systémem Android 7.0. V předchozích verzích mohli správci vzdáleně resetovat heslo uživatele e koncoví uživatelé mohli k resetování svých hesel využívat web Portál společnosti.

## Správa skupin
### Přechod od skupin Intune ke skupinám Azure Active Directory od září 2016
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

## Portál společnosti

### Odkaz pro zasílání názorů společnosti Microsoft na webu Portál společnosti
Web Portál společnosti nyní koncovým uživatelům umožní klepnout na nový odkaz Zpětná vazba v dolní části stránky a poslat společnosti Microsoft svoje názory na tuto stránku a zkušenosti s ní. Shromážděná anonymizovaná zpětná vazba pomůže Microsoftu zlepšit prostředí webu Portál společnosti.
<!--- TFS 1313657--->

### Přidání oznámení na Portál společnosti pro Android
V září vydáváme aktualizaci Portálu společnosti pro Android, která zavádí novou ikonu **Oznámení** na domovské stránce. Klepnutí na tuto ikonu zpřístupní stránku **Oznámení**, kde se koncovým uživatelům zobrazí všechny položky, které v aplikaci Portál společnosti vyžadují pozornost, jako je třeba to, že zařízení nedodržuje předpisy, aktualizace nebo aktivace registrace. Pokud používáte také aplikaci Portál společnosti pro iOS, už jste se s těmito oznámeními setkali. Po zavedení stránky **Oznámení** se při každém spuštění nebo obnovení Portálu společnosti pro Android už nezobrazí stránka **Nastavení firemního přístupu**, pokud je zařízení už zaregistrované. Slyšeli jsme, že celá řada z vás vytvořila pokyny pro koncové uživatele a oceníte, pokud vás předem upozorníme, že vaše pokyny nebo snímky obrazovky mohou vyžadovat aktualizaci. Proveďte prosím aktualizaci dokumentace tak, aby tuto chystanou změnu odrážela. Aktualizované snímky obrazovky najdete tady: https://aka.ms/androidcpupdate.  

### Vylepšení toho, jak koncoví uživatelé iOS získají svoje aplikace
Pro dlaždice aplikací v aplikaci Portál společnosti pro iOS se budou v září provádět následující změny tak, aby uživatele u všech aplikací odkazovaly na různá zobrazení v jednom umístění – na webu Portál společnosti. Apple v současnosti zakazuje, aby se obchodní a spravované aplikace z App Storu zobrazovaly v aplikaci Portál společnosti. Uživatel tak k vyhledání všech svých aplikací musí použít několik zobrazení.

- Dlaždice **Firemní aplikace** v současnosti odkazuje na seznam všech aplikací na kartě VŠE na webu Portál společnosti a bude tak fungovat i dál. Název této dlaždice se změní na **Všechny aplikace**.
- Dlaždice **Ostatní aplikace** v současnosti odkazuje v aplikaci Portál společnosti na zobrazení, ve kterém je uvedený seznam všech aplikací, které Apple aplikaci Portál společnosti povoluje zobrazit. Název dlaždice se změní na **Doporučené aplikace**. Po klepnutí na tuto dlaždici uživatelé přejdou na kartu DOPORUČENÉ na webu Portál společnosti.
-  Dlaždice **Kategorie** v současnosti odkazuje v aplikaci Portál společnosti na zobrazení, ve kterém je uvedený seznam kategorií aplikací. Název této dlaždice se nezmění, ale bude teď na webu Portál společnosti odkazovat na kartu KATEGORIE.
Aktualizované snímky obrazovky najdete [tady](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

### Výzva k instalaci aplikace Spravovaný prohlížeč pro iOS, pokud IT specialista tento požadavek pro aplikaci nastavil
Pokud jste nakonfigurovali webový klip tak, aby se otevíral jenom ve spravovaném prohlížeči, a spravovaný prohlížeč není v zařízení nainstalovaný, zářijová verze aplikace Portál společnosti pro iOS vyzve uživatele, aby nejdřív nainstaloval spravovaný prohlížeč, a teprve potom bude možné nainstalovat příslušný webový klip. 
<!---TFS 1228570--->

## Zastaralá služba
### Aplikace Portál společnosti pro Windows 8 a Windows Phone 8 se od září 2016 přestávají používat
Od října 2016 přestane Microsoft Intune poskytovat podporu aplikacím Portál společnosti pro Windows 8 a Windows Phone 8. Microsoft Intune také přestat poskytovat podporu pro platformu Windows Phone 8. V důsledku toho nebude možné registrovat ani aktualizovat žádná zařízení Windows Phone 8. Zařízení Windows Phone 8 a Windows 8, která jsou již zaregistrována, můžete nadále spravovat. Pokud budete chtít do zařízení s těmito systémy dál bez přerušení distribuovat aplikace, aktualizujte si zařízení Windows 8 a Windows Phone 8 na Windows 8.1 a Windows Phone 8.1 a začněte používat odpovídající aplikaci Portál společnosti pro Windows 8.1 a Windows Phone 8.1.
<!---TFS 1255391--->

### Odebrání možnosti cílení pravidel oznámení na vlastní skupiny
Pravidla oznámení Intune definují, komu se budou z Intune odesílat e-mailové výstrahy. V současnosti můžete nakonfigurovat pravidla oznámení pro odesílání e-mailů všem uživatelům zařízení nebo skupině zařízení služby Intune, kterou jste vytvořili. Od června 2016 se cílení na uživatelsky vytvořené skupiny už nebude podporovat.

Předběžná časová osa pro tuto změnu je následující:
- V září 2016 se novým tenantům v Průvodci vytvořením pravidla oznámení nezobrazí krok 2. Stávající tenanty to neovlivní.
- Zhruba v říjnu 2016 se některým tenantům v tomto průvodci nezobrazí možnost Vybrat skupiny zařízení.
- Později očekáváme, že se možnost Vybrat skupiny zařízení v tomto průvodci nezobrazí žádným tenantům.

<!---   TFS 1278864--->
### Změny v podpoře pro aplikaci Portál společnosti pro iOS
Od září se začne vyžadovat, aby všichni uživatelé aplikace Portál společnosti Microsoft Intune pro iOS používali její nejnovější verzi. Noví uživatelé si budou moct stáhnout jenom nejnovější verzi a aktuální uživatelé si budou muset aplikaci aktualizovat. Nejnovější verze vyžaduje iOS 8.0 nebo novější, takže zařízení se starší verzí iOS nebudou moct Portál společnosti používat ani nebudou moct zařízení zaregistrovat, dokud si v něm neaktualizují operační systém na iOS 8.0 nebo novější a následně neaktualizují i aplikaci Portál společnosti na nejnovější verzi. Zaregistrovaná zařízení se systémem iOS starším 8.0 se budou spravovat i nadále a budou se zobrazovat v konzole správce Intune.

<!---TFS 1283165--->


### Aplikace Intune Viewer
V souvislosti s vydáním nové aplikace Sdílení RMS odebíráme od srpna 2016 tyto aplikace Intune Viewer:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer pro Android z Google Play

Místo použití aplikací Intune Viewer vám doporučujeme používat novou aplikaci Rights Management (sdílení RMS) pro Android, která pro bezpečné prohlížení firemních souborů na zařízeních s Androidem umožňuje nasadit jednu aplikaci (namísto tří samostatných aplikací). Přečtěte si víc o [aplikaci Sdílení RMS](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app).
<!--- goes in 1608 What's New--->


### Viz taky
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Aug16_HO5-->


