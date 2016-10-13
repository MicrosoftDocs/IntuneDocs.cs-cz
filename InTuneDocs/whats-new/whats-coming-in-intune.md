---
title: "Časná edice | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a5c4b0f15456a9f24c95954d669a17c63f96a459
ms.openlocfilehash: 273016d4fe114bbe60e9cebc06e89584c8f91f0b


---

# Co se chystá v Microsoft Intune – říjen
**Časná edice** poskytuje seznam funkcí, které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány na základě smlouvy o utajení (NDA) ve velmi omezené míře a mohou podléhat změnám. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a mohou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moci zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se prosím na příslušný kontakt (Intune/PM).

Tato stránka se pravidelně aktualizuje. Vracejte se na ni, abyste zjistili, jaké aktualizace připravujeme.

Následující změny v Intune jsou ve vývoji. Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

### Správa tisku z aplikací spravovaných pomocí zásad MAM
Nově je možné zabránit tisku firemních dat z aplikací se zásadami MAM. Toto nastavení je dostupné na webu [Azure Portal](..deployuse/create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) a podporují ho zařízení s [iOS](..deployuse/ios-mam-policy-settings) i [Androidem](..deployuse/android-mam-policy-settings).
<!--TFS 1014328-->

### Nový Portál společnosti Microsoft Intune pro zařízení s Windows 10
Společnost Microsoft vydává nový Portál společnosti Microsoft Intune pro zařízení s Windows 10. Tato aplikace, která využívá nový univerzální formát Windows 10, poskytne uživatelům aktualizované prostředí, které je identické napříč všemi zařízeními s Windows 10, ať už jsou to počítače, nebo mobilní zařízení, a nabídne přitom stejné funkce, které v současnosti využívají.

Tato nová aplikace také uživatelům umožní využít v zařízeních s Windows 10 další funkce platformy, jako je jednotné přihlašování (SSO) a ověřování na základě certifikátů. Tato aplikace bude dostupná jako upgrade stávající aplikace Portál společnosti Windows 8.1 a Portál společnosti Windows Phone 8.1 a instaluje se z Windows Storu.
<!--TFS 1016502-->

### Podpora programu Android for Work

Intune je nyní součástí programu [Android for Work](https://enterprise.google.com/android/partners/). Podporu funkcí Android for Work začneme do Intune zavádět od tohoto měsíce.

[Přečtěte si prohlášení Microsoftu o podpoře Intune pro Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

<!---This month, some newly provisioned Intune tenants will start seeing the Android for Work features. We will announce later when existing tenants will begin to see this feature.--->
<!--TFS 1043303-->

### Kompatibilita systému Android Samsung KNOX s Intune

Některé modely telefonů Samsung Galaxy Ace nejde spravovat pomocí Intune jako zařízení se systémem Samsung KNOX. Pokud tato zařízení zaregistrujete v Intune, budou se spravovat jako standardní zařízení s Androidem.
Jde o tyto modely:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Vy a vaši koncoví uživatelé nemusíte nic dělat.
Další informace najdete na webu [Samsung KNOX](https://www.samsungknox.com).

<!--TFS 1173566 iX blurb provided by Barry; requires PM signoff

### Multi-factor authentication for Android and iOS enrollment

In addition to Windows 8.1 and later, administrators can now enable multi-factor authentication for Android and iOS devices in the Microsoft Intune Enrollment application. -->    

### Aplikace Portál společnosti pro Windows 8 je zastaralá, podpora pro platformy Windows Phone 8 a Windows RT se přestává používat
Od října 2016 přestane Microsoft Intune poskytovat podporu pro Portál společnosti pro Windows 8. Microsoft Intune také přestat poskytovat podporu pro platformy Windows Phone 8 a Windows RT. V důsledku toho nebude možné registrovat ani aktualizovat žádná zařízení s Windows Phone 8 nebo Windows RT.

Zařízení s Windows Phone 8 a Windows 8, která jsou už zaregistrovaná, můžete nadále spravovat. Pokud budete chtít do zařízení s těmito systémy dál bez přerušení distribuovat aplikace, aktualizujte si zařízení Windows 8 a Windows Phone 8 na Windows 8.1 a Windows Phone 8.1 a začněte používat odpovídající aplikaci Portál společnosti pro Windows 8.1 a Windows Phone 8.1.

Od listopadu 2016 přestaneme poskytovat podporu pro Portál společnosti pro Windows Phone 8.
<!--TFS 1255391-->

### Podmíněný přístup pro správu mobilních aplikací
Nově můžete vytvářet zásady podmíněného přístupu, které budou nespravovaným mobilním aplikacím blokovat přístup ke službám [Exchange Online](..deployuse/restrict-access-to-exchange-online-with-microsoft-intune.md) a [SharePoint Online](..deployuse/restrict-access-to-sharepoint-online-with-microsoft-intune.md). Pomocí Intune App SDK můžete blokovat integrované poštovní klienty a aplikace bez podpory MAM.  Pomocí webu Azure Portal vytvořte zásady podmíněného přístupu a zadejte aplikace, které mají mít přístup ke službám Exchange Online a SharePoint Online.
<!--TFS 1317673-->

<!--TFS 1318014; awaiting approval in notes as to whether to proceed

### "Default" policy is deprecated

To minimize unintentionally assigned profiles, Intune is removing support for the "default" Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) device serial numbers in the new Azure console. Serial numbers synchronized from an Apple DEP account will initially have no Corporate Device Enrollment profile assigned.  A profile must be assigned manually after synchronization. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

<!--TFS 1318023; awaiting approval in notes as to whether to proceed

### Deprecation of row-by-row iOS Details review for iOS device CSV uploads

In order to streamline uploading IMEI numbers for Corporate devices and Apple serial numbers for Configurator enrollment, Intune is removing the row by row review of hardware identifiers already found in the system. This review allows the IT Pro to accept associated Details from the CSV to overwrite the existing details for a hardware identifier already in the system. The review will be replaced by a single option to automatically overwrite Details for all hardware identifiers or ignore new details for existing identifiers. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

### Integrace služby Lookout pro ochranu zařízení s iOS
V říjnu společnost Microsoft integruje řešení ochrany před mobilními hrozbami ve službě Lookout s cílem chránit pomocí zjišťování malwaru, riskantních aplikací a dalších problémů mobilní zařízení s iOS. Řešení Lookout vám pomůže určit úroveň ohrožení, která je konfigurovatelná. Ve službě Intune můžete vytvořit pravidlo zásad dodržování předpisů na základě vyhodnocování rizik aplikací Lookout. Pomocí zásad podmíněného přístupu můžete povolit nebo blokovat přístup k prostředkům společnosti na základě stavu dodržování předpisů pro zařízení.

Koncoví uživatelé zařízení s iOS nesplňujících požadavky budou vyzvaní k registraci. Dále si budou muset před získáním přístupu k firemním datům nainstalovat na svoje zařízení aplikaci Lookout for Work, aktivovat ji a opravit hrozby nahlášené aplikací Lookout for Work.
<!--TFS 1319493-->

### Intune App SDK a nástroj App Wrapping pro Android
Svým aplikacím můžete umožnit použití zásad správy mobilních aplikací (MAM) služby Intune buď prostřednictvím nástroje Intune App Wrapping, nebo pomocí sady Intune App SDK. Nové aktualizace nástroje App Wrapping a sady SDK budou zahrnovat:

* Podporu pro Android N
* Podporu pro zásady Intune MAM bez nutnosti registrace zařízení
* Podporu pro aplikace pro Android využívající Xamarin

MAM bez registrace zařízení a podporu Xamarinu ve veřejné verzi Preview nástroje Android App Wrapping si můžete otestovat tady: [https://github.com/msintuneappsdk/intune-app-wrapper-android-preview](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview).
<!--TFS 1319511; please create new TFS entry for WN text associated with this TFS item-->

<!--TFS 1319613; no iX review on PM text blurb

### Private preview customers using MAM Conditional Access will have their policies reset

Due to changes in the policy structure for Conditional Access for Mobile App Management, any existing policies that were set by customers through the private preview will be removed. Customers will need to set new policies once the change is made. The timing will coincide with the October service update.
-->

### Související témata
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Oct16_HO1-->


