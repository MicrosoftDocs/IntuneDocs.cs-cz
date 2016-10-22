---
title: "Co je nového | Microsoft Intune"
description: "Zjistěte, co je nového v aktualizací služby Microsoft Intune v tomto měsíci nebo dříve"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 503719953031bf5079b2bf5bc84a0497d708f79a
ms.openlocfilehash: 730809e0841a248b90f5fe157f2c6338bfd32b2d


---
# Co je nového v Microsoft Intune – říjen 2016
Zjistěte, co je nového v této verzi Microsoft Intune. Můžete také získat informace o nadcházejících změnách, se kterými byste měli počítat, a o minulých verzích.

Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## Co je nového

### Podmíněný přístup pro správu mobilních aplikací
Budete moct omezit přístup k Exchangi Online, takže přístup bude možný jenom z aplikací, které podporují zásady správy mobilních aplikací Intune, jako je Outlook. [Tato nová funkce](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) vhodně doplňuje zásady správy mobilních aplikací (MAM) Intune, protože vám umožní blokovat přístup k integrovaným poštovním klientům nebo jiným aplikacím, u kterých nebyly nakonfigurovány zásady Intune MAM. Tím zajistíte, že uživatelé mají přístup k datům vaší organizace prostřednictvím aplikací, které mohou být chráněny pomocí služby Intune MAM. Se správou mobilních aplikací Intune můžete začít prostřednictvím webu Azure Portal. V okně Nastavení hledejte novou sekci Podmíněný přístup.

### Podmíněný přístup pro počítače s Windows
Nově můžete přes konzolu správce Intune vytvářet zásady podmíněného přístupu, které budou počítačům s Windows blokovat přístup k [Exchangi Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) a [SharePointu Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Taky můžete vytvářet zásady podmíněného přístupu, které budou blokovat přístup k desktopovým a univerzálním aplikacím Office.

### Podpora programu Android for Work
Intune je teď součástí programu Android for Work. Podporu funkcí Android for Work začneme do Intune zavádět od tohoto měsíce.
[Přečtěte si prohlášení Microsoftu o podpoře Intune pro Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Následující témata pro Intune jsou nová nebo aktualizovaná o informace týkající se Androidu for Work:

Pro IT specialisty:
- [Nastavení Androidu for Work](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Omezení přístupu k Exchangi Online a novému vyhrazeném prostředí Exchange Online s Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Omezení přístupu k e-mailu v místním systému Exchange a starším vyhrazeném prostředí Exchange Online v Microsoft Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Nastavení zásad dodržování předpisů pro Android for Work](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Jak nasadit aplikace pro Android for Work](/intune/deploy-use/android-for-work-apps)
- [Konfigurace aplikací pro Android for Work pomocí zásad konfigurace mobilních aplikací](/intune/deploy-use/afw-app-configuration-policy)
- [Nastavení zásad Android for Work](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Pro koncové uživatele:
- [Co se stane při vytvoření pracovního profilu](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Vytvoření pracovního profilu a registrace zařízení v Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### Integrace služby Lookout pro ochranu zařízení s iOS
V říjnu společnost Microsoft integruje řešení ochrany před mobilními hrozbami ve službě Lookout s cílem chránit pomocí zjišťování malwaru, riskantních aplikací a dalších problémů mobilní zařízení s iOS. Řešení Lookout vám pomůže určit úroveň ohrožení, která je konfigurovatelná. Ve službě Intune můžete vytvořit pravidlo zásad dodržování předpisů na základě vyhodnocování rizik aplikací Lookout. Pomocí zásad podmíněného přístupu můžete povolit nebo blokovat přístup k prostředkům společnosti na základě stavu dodržování předpisů pro zařízení.

Koncoví uživatelé zařízení s iOS nesplňujících požadavky budou vyzvaní k registraci. Dále si budou muset před získáním přístupu k firemním datům nainstalovat na svoje zařízení aplikaci Lookout for Work, aktivovat ji a opravit hrozby nahlášené aplikací Lookout for Work. Přečtěte si téma [Konfigurace a nasazení aplikací Lookout for Work](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### Nástroj Intune App Wrapping Tool pro Android
Pomocí nástroje Intune App Wrapping Tool svým aplikacím umožníte používat zásady správy mobilních aplikací (MAM) služby Intune. Podpora zásad Intune MAM je nyní dostupná bez nutnosti registrace zařízení.

### Správa tisku z aplikací spravovaných pomocí zásad MAM
Nově je možné zabránit tisku firemních dat z aplikací se zásadami MAM. Toto nastavení je dostupné na webu [Azure Portal](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) a podporují ho zařízení s [iOS](/Intune/deploy-use/ios-mam-policy-settings) i [Androidem](/Intune/deploy-use/android-mam-policy-settings).
<!--TFS 1014328-->

## Sdělení

### Kompatibilita systému Android Samsung KNOX s Intune
Některé modely telefonů Samsung Galaxy Ace nejde spravovat pomocí Intune jako zařízení se systémem Samsung KNOX. Pokud tato zařízení zaregistrujete v Intune, budou se spravovat jako standardní zařízení s Androidem.

Jde o tyto modely:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Vy a vaši koncoví uživatelé nemusíte nic dělat. Další informace najdete na webu [Samsung KNOX](https://www.samsungknox.com).

### Aplikace Portál společnosti pro Windows 8 je zastaralá, podpora pro platformy Windows Phone 8 a Windows RT se přestává používat
Od října 2016 přestane Microsoft Intune poskytovat podporu pro Portál společnosti pro Windows 8. Microsoft Intune také přestat poskytovat podporu pro platformy Windows Phone 8 a Windows RT. V důsledku toho nebude možné registrovat ani aktualizovat žádná zařízení s Windows Phone 8 nebo Windows RT.

Zařízení s Windows Phone 8 a Windows 8, která jsou už zaregistrovaná, můžete nadále spravovat. Pokud budete chtít do zařízení s těmito systémy dál bez přerušení distribuovat aplikace, aktualizujte si zařízení Windows 8 a Windows Phone 8 na Windows 8.1 a Windows Phone 8.1 a začněte používat odpovídající aplikaci Portál společnosti pro Windows 8.1 a Windows Phone 8.1.

Od listopadu 2016 přestaneme poskytovat podporu pro Portál společnosti pro Windows Phone 8.
<!--TFS 1255391-->

## Co připravujeme

### Nový Portál společnosti Microsoft Intune pro zařízení s Windows 10
Společnost Microsoft vydává nový Portál společnosti Microsoft Intune pro zařízení s Windows 10. Tato aplikace, která využívá nový univerzální formát Windows 10, poskytne uživatelům aktualizované prostředí, které je identické napříč všemi zařízeními s Windows 10, ať už jsou to počítače, nebo mobilní zařízení, a nabídne přitom stejné funkce, které v současnosti využívají.

Tato nová aplikace také uživatelům umožní využít v zařízeních s Windows 10 další funkce platformy, jako je jednotné přihlašování (SSO) a ověřování na základě certifikátů. Tato aplikace bude dostupná jako upgrade stávající aplikace Portál společnosti Windows 8.1 a Portál společnosti Windows Phone 8.1 a instaluje se z Windows Storu. Další podrobnosti najdete na adrese [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

### Související témata
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Předchozí verze Intune](previous-intune-releases.md)



<!--HONumber=Oct16_HO3-->


