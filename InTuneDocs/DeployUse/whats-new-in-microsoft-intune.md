---
title: "Co je nového | Microsoft Intune"
description: "Zjistěte, co je nového v aktualizací služby Microsoft Intune v tomto měsíci nebo dříve"
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c636efee82331d6feac75153b872526f7af7c882
ms.openlocfilehash: 814312b0ac6055ffff2efad2ddbdaa8664f84fde


---

# Co je nového v Microsoft Intune
Zjistěte, co je nového v této verzi Microsoft Intune. Můžete také získat informace o nadcházejících změnách, se kterými byste měli počítat, a o minulých verzích.

Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

>[!IMPORTANT] 
>Příspěvek blogu – aktualizace mobilních zařízení pomocí Microsoft Intune<br>
>S ohledem na nedávné útoky malwaru Trident na zařízení s iOS jsme zveřejnili nový příspěvek blogu věnovaný [zajištění aktuálnosti mobilních zařízení pomocí Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/). Pomůže vám seznámit se s různými způsoby, kterými Intune může zajistit zabezpečení a aktuálnost vašich zařízení.

## Září 2016

## Aktualizace Portálu společnosti
### Android

**Přidání oznámení do aplikace Portál společnosti pro Android**

Na domovskou stránku aplikace Portál společnosti pro Android byla přidaná nová ikona oznámení. Klepnutí na tuto ikonu otevře stránku Oznámení, kde se koncovým uživatelům zobrazí všechny položky, které v aplikaci Portál společnosti vyžadují pozornost (například že nějaké zařízení nedodržuje předpisy, zpráva o aktualizaci registrací nebo aktivaci registrací). Aplikace Portál společnosti pro iOS už tato oznámení má. Po zavedení stránky Oznámení se už při každém spuštění nebo obnovení aplikace Portál společnosti pro Android nezobrazí stránka Nastavení firemního přístupu, pokud je zařízení už zaregistrované. Pokud vytvoříte vlastní návod pro koncové uživatele, nezapomeňte tuto změnu do dokumentace promítnout. Aktualizované snímky obrazovky najdete [tady](https://aka.ms/androidcpupdate).  
<!---TFS 1095560--->

### Windows
**Přidání tlačítka pro odeslání zpětné vazby do aplikace Portál společnosti pro Windows Phone 8.1**

Portál společnosti pro Windows Phone 8.1 koncovým uživatelům umožňuje odeslat zpětnou vazbu o aplikaci. Slouží k tomu tlačítko „Odeslat názor“. Tlačítko najdete tak, že klepnete na třítečkovou nabídku v dolní pravé části obrazovky aplikace Portál společnosti a potom na **Odeslat názor**. Shromážděná anonymizovaná zpětná vazba pomůže Microsoftu zlepšit prostředí aplikace Portál společnosti.
<!---TFS 1317806--->

## Srpen 2016
## Správa aplikací
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### Skryté a zobrazené aplikace pro iOS 9.3
U dozorovaných zařízení se systémem iOS 9.3 nebo novějším můžete využít seznam skrytých a zobrazených aplikací v zásadách obecné konfigurace iOS k těmto akcím:
- Určení seznamu aplikací, které budou uživatelům skryté. Uživatelé nebudou moci tyto aplikace zobrazit ani spustit.
- Určení seznamu aplikací, které uživatelé mohou zobrazit a spustit. Žádné jiné aplikace nebude možné zobrazit ani spustit.

Mezi aplikace, které můžete zadat, patří aplikace, které jste nasadili, a integrované aplikace pro iOS, jako jsou Zprávy a Poznámky. Podrobnosti najdete v tématu [Nastavení zásad pro iOS v Microsoft Intune]( https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
### Zásady povolených a blokovaných aplikací pro zařízení se systémem Samsung KNOX
Nyní můžete pro zařízení se systémem Samsung KNOX nakonfigurovat vlastní zásady, které umožňují vytvořit:
- Seznam aplikací, u kterých je v příslušném zařízení blokované spuštění. Aplikace, které jsou definované v seznamu blokovaných aplikací, nejde na zařízení aktivovat, ani když jsou nainstalované.
- Seznam aplikací, které si uživatelé příslušného zařízení mohou nainstalovat z obchodu Google Play. Z tohoto obchodu nejde nainstalovat žádné další aplikace.

Tato nastavení mohou využívat jenom zařízení se systémem Samsung KNOX.
Podrobnosti viz [Použití vlastních zásad povolených a blokovaných aplikací pro zařízení se systémem Samsung KNOX]( custom-policy-to-allow-and-block-samsung-knox-apps.md).
<!---TFS 1311629 checked --->
### Nové aplikace kompatibilní se zásadami správy mobilních aplikací (MAM)
Aplikace Yammer pro [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) a [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) je teď kompatibilní se [zásadami správy mobilních aplikací (MAM) služby Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) bez ohledu na to, jestli je zařízení zaregistrované.

Kompletní seznam aplikací kompatibilních s MAM najdete na webu [aplikací pro Microsoft Intune od partnerů](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

### Aplikace Intune Viewer
V souvislosti s vydáním nové aplikace pro sdílení RMS odebíráme od srpna 2016 následující aplikace Intune Viewer:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer pro Android z Google Play

Místo použití aplikací Intune Viewer vám doporučujeme používat novou aplikaci [Rights Management (sdílení RMS) pro Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), která pro bezpečné prohlížení firemních souborů na zařízeních s Androidem umožňuje nasadit jednu aplikaci (namísto tří samostatných aplikací). Až se aplikace Intune Viewer už nebude podporovat, bude odebrána z Google Storu a nebude už dostupná pro budoucí použití.

## Správa zařízení
### Podpora pro Android 7.0
Intune poskytuje podporu „dne 0“ pro připravovaný operační systém Android 7.0 pro mobilní zařízení.
<!---TFS 1262053--->
### Odebrání funkce pro vzdálené resetování hesla v zařízeních se systémem Android 7.0
Google odebírá správcům IT a koncovým uživatelům možnost vzdáleně resetovat hesla na zařízeních se systémem Android 7.0. V předchozích verzích mohli správci vzdáleně resetovat heslo uživatele e koncoví uživatelé mohli k resetování svých hesel využívat web Portál společnosti.



## Aktualizace Portálu společnosti
### Web portálu společnosti
- **Odkaz pro zasílání názorů společnosti Microsoft na webu Portál společnosti** <br/>
Portál společnosti umožňuje koncovým uživatelům klepnout na nový odkaz Zpětná vazba v dolní části stránky a poslat společnosti Microsoft názory na tuto stránku a zkušenosti s ní. Shromážděná anonymizovaná zpětná vazba pomůže Microsoftu zlepšit prostředí webu Portál společnosti.
<!--- TFS 1313657 checked--->

### iOS
- **Minimální verze iOS pro Managed Browser byla aktualizovaná na 8.0**<br/>
Aplikaci Microsoft Intune Managed Browser pro iOS byla aktualizována a podporuje zařízení se systémem iOS 8.0 nebo novějším. Přestože v zařízeních s iOS 7.1 můžou využívat stávající aplikaci Managed Browser, doporučte prosím svým uživatelům, aby aktualizovali na iOS 8.0 nebo novější a mohli plně využít výhody nových funkcí Managed Browseru.  
<!---TFS 1313253 checked--->

## Co připravujeme

### Podpora pro iOS 10
Intune bude plně podporovat iOS 10. Další informace zveřejníme po vydání iOS 10.

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

### Přidání oznámení na Portál společnosti pro Android
V září vydáváme aktualizaci Portálu společnosti pro Android, která zavádí novou ikonu **Oznámení** na domovské stránce. Klepnutí na tuto ikonu zpřístupní stránku **Oznámení**, kde se koncovým uživatelům zobrazí všechny položky, které v aplikaci Portál společnosti vyžadují pozornost, jako je třeba to, že zařízení nedodržuje předpisy, aktualizace nebo aktivace registrace. Pokud používáte také aplikaci Portál společnosti pro iOS, už jste se s těmito oznámeními setkali. Po zavedení stránky **Oznámení** se při každém spuštění nebo obnovení Portálu společnosti pro Android už nezobrazí stránka **Nastavení firemního přístupu**, pokud je zařízení už zaregistrované. Slyšeli jsme, že celá řada z vás vytvořila pokyny pro koncové uživatele a oceníte, pokud vás předem upozorníme, že vaše pokyny nebo snímky obrazovky mohou vyžadovat aktualizaci. Proveďte prosím aktualizaci dokumentace tak, aby tuto chystanou změnu odrážela. Aktualizované snímky obrazovky najdete tady: https://aka.ms/androidcpupdate.  

### Vylepšení toho, jak koncoví uživatelé iOS získají svoje aplikace
Pro dlaždice aplikací v aplikaci Portál společnosti pro iOS se budou v září provádět následující změny tak, aby uživatele u všech aplikací odkazovaly na různá zobrazení v jednom umístění – na webu Portál společnosti. Apple v současnosti zakazuje, aby se obchodní a spravované aplikace z App Storu zobrazovaly v aplikaci Portál společnosti. Uživatel tak k vyhledání všech svých aplikací musí použít několik zobrazení.

- Dlaždice **Firemní aplikace** v současnosti odkazuje na seznam všech aplikací na kartě VŠE na webu Portál společnosti a bude tak fungovat i dál. Název této dlaždice se změní na **Všechny aplikace**.
- Dlaždice **Ostatní aplikace** v současnosti odkazuje v aplikaci Portál společnosti na zobrazení, ve kterém je uvedený seznam všech aplikací, které Apple aplikaci Portál společnosti povoluje zobrazit. Název dlaždice se změní na **Doporučené aplikace**. Po klepnutí na tuto dlaždici uživatelé přejdou na kartu DOPORUČENÉ na webu Portál společnosti.
-  Dlaždice **Kategorie** v současnosti odkazuje v aplikaci Portál společnosti na zobrazení, ve kterém je uvedený seznam kategorií aplikací. Název této dlaždice se nezmění, ale bude teď na webu Portál společnosti odkazovat na kartu KATEGORIE. Aktualizované snímky obrazovky najdete [tady](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

### Průvodce cloudem
Udržujte si přehled o budoucích novinkách pro Intune díky [průvodci cloudovou platformou](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Zastaralá služba
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Změny v podpoře pro aplikaci Portál společnosti pro iOS**<br/>
Od září se začne vyžadovat, aby všichni uživatelé aplikace Portál společnosti Microsoft Intune pro iOS používali její nejnovější verzi. Noví uživatelé si budou moct stáhnout jenom nejnovější verzi a aktuální uživatelé si budou muset aplikaci aktualizovat. Nejnovější verze vyžaduje iOS 8.0 nebo novější, takže zařízení se starší verzí iOS nebudou moct Portál společnosti používat ani nebudou moct zařízení zaregistrovat, dokud si v něm neaktualizují operační systém na iOS 8.0 nebo novější a následně neaktualizují i aplikaci Portál společnosti na nejnovější verzi. Zaregistrovaná zařízení se systémem iOS starším 8.0 se budou spravovat i nadále a budou se zobrazovat v konzole správce Intune.  

- **Minimální verze iOS pro Managed Browser byla aktualizovaná na 8.0**<br/>
V srpnu Intune vydá aktualizovanou aplikaci Microsoft Intune Managed Browser pro iOS, která bude podporovat jenom zařízení se systémem iOS 8.0 nebo novějším. Přestože v zařízeních s iOS 7.1 bude i dál možné využívat stávající aplikaci Managed Browser, doporučte prosím svým uživatelům, aby aktualizovali na iOS 8.0 nebo novější a mohli plně využít výhody nových funkcí Managed Browseru.  
<!---TFS 1313253--->

- **Aplikace Portál společnosti pro Windows 8 a Windows Phone 8 se přestanou používat** <br/>
Od října 2016 přestane Microsoft Intune poskytovat podporu aplikacím Portál společnosti pro Windows 8 a Windows Phone 8. Microsoft Intune také přestat poskytovat podporu pro platformu Windows Phone 8. V důsledku toho nebude možné registrovat ani aktualizovat žádná zařízení Windows Phone 8. Zařízení Windows Phone 8 a Windows 8, která jsou již zaregistrována, můžete nadále spravovat. Pokud budete chtít do zařízení s těmito systémy dál bez přerušení distribuovat aplikace, aktualizujte si zařízení Windows 8 a Windows Phone 8 na Windows 8.1 a Windows Phone 8.1 a začněte používat odpovídající aplikaci Portál společnosti pro Windows 8.1 a Windows Phone 8.1.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->



## Předchozí verze Intune
Informace o tom, co bylo vydáno v rámci Intune během posledních šest měsíců, najdete v článku [Předchozí verze Intune](previous-intune-releases.md).

### Související témata
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Sep16_HO2-->


