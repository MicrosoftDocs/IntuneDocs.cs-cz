---
title: "Co je nového | Microsoft Intune"
description: "Zjistěte, co je nového v aktualizací služby Microsoft Intune v tomto měsíci nebo dříve"
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: ef0210d7ca2d44608c5baa8f48ef56a2b9b5ce3a


---

# Co je nového v Microsoft Intune
Zjistěte, co je nového v této verzi Microsoft Intune. Můžete také získat informace o nadcházejících změnách, se kterými byste měli počítat, a o minulých verzích.

Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Červenec 2016
## Správa aplikací
### Vylepšení prostředí aktualizace zřizovacího profilu aplikace
Mobilní obchodní aplikace pro Apple iOS jsou vytvořeny tak, že obsahují zřizovací profil a kód podepsaný certifikátem. Když se taková aplikace spustí na zařízení s iOS, iOS potvrdí její integritu a vynutí zásady jejím definované zřizovacím profilem.

Podpisový certifikát společnosti, který se používá k podepisování aplikací, má obvykle platnost 3 roky. Platnost zřizovacího profilu ale vyprší už po jednom roce. Prostřednictvím této aktualizace Intune poskytuje nástroje pro proaktivní nasazení nových zásad zřizovacích profilů do zařízení, ve kterých se aplikace blíží vypršení data platnosti, ale certifikát je stále platný. Další informace najdete v tématu věnovaném [použití mobilních zásad zřizovacích profilů pro iOS k zajištění aktuálnosti obchodních aplikací](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->
### Je dostupná sada Xamarin SDK pro aplikace Intune
Komponenta Intune App SDK Xamarin umožňuje v mobilních aplikacích pro iOS a Android vytvořených pomocí Xamarinu povolit funkce správy mobilních aplikací Intune. Tuto komponentu najdete v [Xamarin Storu](https://components.xamarin.com/view/Microsoft.Intune.MAM) nebo na [stránce Microsoft Intune Githubu](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

## Správa zařízení
### Zvýšené limity pro registraci zařízení
Služba Intune zvýšila maximální limit pro registraci zařízení z 5 na 15 zařízení na uživatele.
<!---TFS 1289896 --->



## Aktualizace Portálu společnosti
### Web portálu společnosti
- **Vylepšené prostředí při registraci zařízení s Windows**<br/>
Na webu Portál společnosti byly upřesněny kroky registrace pro Windows 8.1, Windows 10 Desktop a Windows 10 Mobile při použití podmíněného přístupu. Uživatelům se nyní zobrazí samostatné kroky Registrace zařízení a Workplace Join. Snáz tak zjistí stav svého zařízení a dokončí celý proces v případě, že dojde k chybě Workplace Join (WPJ). Očekává se, že tyto samostatné kroky také zjednoduší proces řešení potíží pro správce IT. Když se dříve uživatelé pokusili zaregistrovat a všechny kroky registrace se provedly úspěšně s výjimkou WPJ, zaregistrované zařízení se nezobrazilo v seznamu zařízení a uživatele to mátlo.

### Android
- **Aplikace Portál společnosti pro Android**<br/>
Když se koncovému uživateli Androidu zobrazí zpráva, která uvádí, že v zařízení chybí certifikát, může kliknutím na tlačítko Jak to vyřešit zobrazit [kroky](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) pro instalaci chybějícího certifikátu. Pokud uživatel dokončí tyto kroky, ale zobrazí se mu další chybová zpráva typu chybějící certifikát, měl by kontaktovat správce IT a poskytnout mu tento [odkaz](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), který obsahuje kroky, jejichž prostřednictvím správce může potíže s certifikátem vyřešit.

- **Omezení instalací zkušebně načtených aplikací jenom na registrovaná zařízení**<br/>
Zařízení s Androidem už nemohou instalovat aplikace prostřednictvím webu Portál společnosti, pokud nejsou v Intune zaregistrovaná pomocí aplikace Portál společnosti Intune pro Android.
<!---TFS 1299082--->

### iOS
- **Změny účtů Správců registrace zařízení v aplikaci Portál společnosti pro iOS**<br/>
Za účelem zvýšení výkonu a možností škálování už Intune v aplikaci Portál společnosti pro iOS v podokně **Moje zařízení** nezobrazuje všechna zařízení Správce registrace zařízení. Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to pouze v případě, že je zaregistrováno prostřednictvím aplikace Portál společnosti.

    Uživatel Správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálenou správu jiných zaregistrovaných zařízení je možné provádět pouze z konzoly správce Intune. Kromě toho se v Intune místo účtů DEM začne používat buď program Apple DEP (Device Enrollment Program), nebo nástroj Apple Configurator. Obě tyto metody registrace již podporují registrace bez zásahu uživatele pro sdílená zařízení s iOS.

    Účty Správce registrace zařízení používejte pouze v případě, že registrace sdílených zařízení bez zásahu uživatele není dostupná. Další informace najdete v části [Registrace firemních zařízení pomocí správce registrace zařízení v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

## Změna názvů pro funkce Windows
- [Microsoft Passport pro Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) teď znáte jako **Windows Hello pro firmy**.
- [Ochrana podnikových dat](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) se nyní označuje jako **Windows Information Protection**.

## Co připravujeme
### Přechod od skupin Intune ke skupinám Azure Active Directory od srpna 2016
Intune vytváří nové prostředí pro správu skupin, které využívá skupiny zabezpečení Azure Active Directory (AAD). Tyto skupiny zabezpečení využívající Azure AD mohou obsahovat uživatele i zařízení a budou se využívat pro veškerou správu skupin a nasazování zásad a profilů, až zavedeme nový portál pro správu Intune s využitím Azure.

Toto nové prostředí:
- Vás zbaví nutnosti mít mezi službami duplicitní skupiny.
- Umožní přístup k některým novým funkcím skupin Azure Active Directory Premium (AADP).
- Zajistí možnosti rozšíření prostřednictvím PowerShellu a Graphu.
- Sjednotí prostředí správy skupin napříč správou podnikové mobility.

Pro umožnění přechodu ke skupinám zabezpečení dojde v aktuální konzole pro správu k určitým úpravám. Tyto změny a také použití skupin zabezpečení Azure budou popsané v dokumentaci k Intune.

Zákazníci, kteří s Intune začínají, se s některými změnami skupin zabezpečení setkají dříve než aktuální tenanti.

Kromě změn ve správě skupin se také přestanou používat následující funkce:
- Vyloučení členů nebo skupin při vytvoření nové skupiny
- Skupiny **Neseskupení uživatelé** a **Neseskupená zařízení**
- **Správa skupin** v roli Správce služby
- Vlastní výstrahy na základě skupin pro pravidla oznámení
- Přesun skupin v sestavách

Další informace o tom, jak je možné dopady těchto vyřazení zmírnit, budou vydány v srpnu.

### Přidání oznámení na Portál společnosti pro Android
V srpnu vydáváme aktualizaci Portálu společnosti pro Android, která zavádí novou ikonu **Oznámení** na domovské stránce. Klepnutí na tuto ikonu zpřístupní stránku **Oznámení**, kde se koncovým uživatelům zobrazí všechny položky, které v aplikaci Portál společnosti vyžadují pozornost, jako je třeba to, že zařízení nedodržuje předpisy, aktualizace nebo aktivace registrace. Pokud používáte také aplikaci Portál společnosti pro iOS, už jste se s těmito oznámeními setkali. Po zavedení stránky **Oznámení** se při každém spuštění nebo obnovení Portálu společnosti pro Android už nezobrazí stránka **Nastavení firemního přístupu**, pokud je zařízení už zaregistrované. Slyšeli jsme, že celá řada z vás vytvořila pokyny pro koncové uživatele a oceníte, pokud vás předem upozorníme, že vaše pokyny nebo snímky obrazovky mohou vyžadovat aktualizaci. Proveďte prosím aktualizaci dokumentace tak, aby tuto chystanou změnu odrážela. Aktualizované snímky obrazovky najdete tady: https://aka.ms/androidcpupdate.  



### Průvodce cloudem
Udržujte si přehled o budoucích novinkách pro Intune díky [průvodci cloudovou platformou](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Zastaralá služba
- **Změny v podpoře pro aplikaci Portál společnosti pro iOS**<br/>
Od července se začne vyžadovat, aby všichni uživatelé aplikace Portál společnosti Microsoft Intune pro iOS používali její nejnovější verzi. Noví uživatelé si budou moct stáhnout jenom nejnovější verzi a aktuální uživatelé si budou muset aplikaci aktualizovat. Nejnovější verze vyžaduje iOS 8.0 nebo novější, takže zařízení se starší verzí iOS nebudou moct Portál společnosti používat ani nebudou moct zařízení zaregistrovat, dokud si v něm neaktualizují operační systém na iOS 8.0 nebo novější a následně neaktualizují i aplikaci Portál společnosti na nejnovější verzi. Zaregistrovaná zařízení se systémem iOS starším 8.0 se budou spravovat i nadále a budou se zobrazovat v konzole správce Intune.  

- **Minimální verze iOS pro Managed Browser byla aktualizovaná na 8.0**<br/>
V srpnu Intune vydá aktualizovanou aplikaci Microsoft Intune Managed Browser pro iOS, která bude podporovat jenom zařízení se systémem iOS 8.0 nebo novějším. Přestože v zařízeních s iOS 7.1 bude i dál možné využívat stávající aplikaci Managed Browser, doporučte prosím svým uživatelům, aby aktualizovali na iOS 8.0 nebo novější a mohli plně využít výhody nových funkcí Managed Browseru.  
<!---TFS 1313253--->

- **Aplikace Portál společnosti pro Windows 8 a Windows Phone 8 se od září 2016 přestanou používat** <br/>
Od září 2016 přestane Microsoft Intune podporovat aplikace Portál společnosti Microsoft Intune pro platformy Windows Phone 8 a Windows 8. Pokud budete chtít do zařízení s těmito systémy dál distribuovat aplikace, aktualizujte si zařízení na Windows 8.1 a Windows Phone 8.1 a začněte používat odpovídající aplikaci Portál společnosti pro Windows 8.1 a Windows Phone 8.1.
<!---TFS 1255391--->

- **Aplikace Intune Viewer** <br/>
V souvislosti s vydáním nové aplikace Sdílení RMS odebíráme od srpna 2016 následující aplikace Intune Viewer:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer pro Android z Google Play

  Místo použití aplikací Intune Viewer vám doporučujeme používat novou aplikaci [Rights Management (sdílení RMS) pro Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), která pro bezpečné prohlížení firemních souborů na zařízeních s Androidem umožňuje nasadit jednu aplikaci (namísto tří samostatných aplikací). Až se aplikace Intune Viewer už nebude podporovat, bude odebrána z Google Storu a nebude už dostupná pro budoucí použití.

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



<!--HONumber=Jul16_HO4-->


