---
title: "Co je nového v Microsoft Intune"
titleSuffix: Intune on Azure
description: "Zjistěte, jaké novinky přináší portál Intune Azure."
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/17/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca98230a54ba7c2067062676420e9e06ff9bf7d7
ms.sourcegitcommit: 21a9db380956a50031dbea360b4c76664cbc2768
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/17/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Co je nového v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zjistěte, jaké novinky každý týden přináší Microsoft Intune. Můžete také získat informace o [nadcházejících změnách](#whats-coming), [důležitá oznámení](#notices) o službě a informace o [minulých verzích](whats-new-archive.md).

> [!Note]
> Mnohé z těchto funkcí budou nakonec podporované pro hybridní nasazení pomocí Configuration Manageru. Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Role-based access control
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
-->   



## <a name="week-of-june-26th-2017"></a>Týden od 26. června 2017

### <a name="role-based-access-control"></a>Řízení přístupu na základě role
#### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Přístup pro správu na základě nové role pro správce Intune   <!-- 1099990 -->  
Přidáváme novou roli správce podmíněného přístupu, která umožňuje zobrazit, vytvořit, upravit a odstranit zásady podmíněného přístupu Azure AD. Dříve měli toto oprávnění jenom globální správci a správci zabezpečení. Oprávnění této role se může udělit správcům Intune, kteří pak mají přístup k zásadám podmíněného přístupu.


### <a name="device-enrollment"></a>Registrace zařízení
#### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Označení zařízení vlastněných podnikem pomocí sériového čísla <!-- 1215070 -->  
Intune nyní podporuje ukládání sériových čísel v systémech iOS, macOS a Android jako identifikátorů podnikových zařízení. Sériová čísla nemůžete používat k blokování registrace osobních zařízení, protože sériová čísla se při registraci neověřují. Blokování osobních zařízení podle sériového čísla bude dostupné v blízké budoucnosti.


### <a name="device-management"></a>Správa zařízení
#### <a name="new-remote-actions-for-ios-devices----854689---"></a>Nové vzdálené akce pro zařízení s iOSem <!-- 854689 -->
V této verzi jsme přidali dvě nové akce vzdáleného zařízení pro sdílené iPady, které spravují aplikaci Apple Classroom:

-   [Odhlásit aktuálního uživatele](device-logout-user.md) – odhlásí aktuálního uživatele na vybraném zařízení s iOSem.
-   [Odebrat uživatele](device-remove-user.md) – odstraní vybraného uživatele z místní mezipaměti zařízení s iOSem.


#### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Podpora pro sdílené iPady s aplikací Classroom pro iOS<!-- 1044681 -->
V této verzi jsme rozšířili podporu správy aplikace Classroom pro iOS tak, aby zahrnovala studenty, kteří se přihlásí do sdílených iPadů pomocí svých spravovaných Apple ID.


### <a name="app-management"></a>Správa aplikací  

#### <a name="changes-to-intune-built-in-apps----1332306---"></a>Změny integrovaných aplikací Intune <!-- 1332306 -->

Dříve služba Intune obsahovala řadu integrovaných aplikací, které jste mohli rychle přiřadit. Na základě vaší zpětné vazby jsme tento seznam odebrali a integrované aplikace už neuvidíte.
Pokud jste už ale nějaké integrované aplikace přiřadili, budou se v seznamu aplikací dál zobrazovat. Tyto aplikace můžete dál přiřazovat podle potřeby.
V novější verzi plánujeme přidat jednodušší způsob výběru a přiřazování integrovaných aplikací z portálu Intune.

#### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Snadnější instalace aplikací Office 365 <!--- 1121362 --->
Nový typ aplikace **Office 365 ProPlus** vám usnadní přiřazování aplikací Office 365 ProPlus 2016 na vámi spravovaná zařízení, na kterých běží nejnovější verze Windows 10. Pokud vlastníte příslušné licence, můžete si také nainstalovat Microsoft Project a Microsoft Visio. Požadované aplikace jsou spojeny dohromady a v seznamu aplikací v konzole Intune se zobrazují jako jedna aplikace.
Další informace najdete v tématu [Jak přidat aplikace Office 365 pro Windows 10](apps-add-office365.md).


#### <a name="support-for-offline-apps-from-the-windows-store-for-business-----777044----"></a>Podpora pro offline aplikace z Windows Storu pro firmy <!--- 777044 --->
Offline aplikace zakoupené ve Windows Storu pro firmy, se nyní budou synchronizovat na portálu Intune. Tyto aplikace můžete nasadit pro skupiny zařízení nebo skupiny uživatelů. Offline aplikace bude instalovat služba Intune, nikoli Store.

#### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Aplikace Microsoft Teams je nyní součástí seznamu schválených aplikací pro zásady podmíněného přístupu na podle aplikací   <!-- 1257019 -->

Aplikace Microsoft Teams pro iOS a Android je nyní součástí schválených aplikací pro zásady podmíněného přístupu podle aplikací pro Exchange a SharePoint Online. Aplikaci lze nakonfigurovat prostřednictvím okna Intune App Protection na portálu Azure Portal pro všechny tenanty aktuálně používající podmíněný přístup podle aplikací.

#### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Spravovaný prohlížeč (Managed Browser) a integrace proxy aplikace <!-- 1287310 -->
 Spravovaný prohlížeč Intune Managed Browser je nyní možné integrovat do služby Azure AD Application Proxy, což umožní uživatelům získat přístup k interním webům, i když pracují vzdáleně. Uživatelé prohlížeče jako obvykle zadají adresu URL webu a Managed Browser požadavek prostřednictvím webové brány proxy aplikace přesměruje. Další informace najdete v tématu [Správa přístupu k internetu pomocí zásad spravovaného prohlížeče](app-configuration-managed-browser.md).


#### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Nová nastavení konfigurace aplikace pro Intune Managed Browser <!-- 682951 -->
V této verzi jsme pro aplikaci Intune Managed Browser pro iOS a Android přidali další konfigurace. Pomocí zásad konfigurace aplikace nyní můžete prohlížeči nakonfigurovat výchozí domovskou stránku a záložky.
Další informace najdete v tématu [Správa přístupu k internetu pomocí zásad spravovaného prohlížeče](app-configuration-managed-browser.md).




### <a name="device-configuration"></a>Konfigurace zařízení  
#### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Nastavení nástroje BitLocker pro Windows 10  <!-- 951707 -->
Nyní můžete nastavení nástroje BitLocker konfigurovat pro zařízení s Windows 10 pomocí nového profilu zařízení Intune. Například můžete vyžadovat, aby se zařízení šifrovala, a také nakonfigurovat další nastavení, která se použijí při zapnutí nástroje BitLocker.
Další informace najdete v tématu o [nastavení služby Endpoint Protection pro Windows 10 a novější](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Nová nastavení pro profil omezení zařízení s Windows 10 <!--- 978527,  978550, 978569, 1050031, 1058611,  --->

V této verzi jsme přidali nová nastavení pro profil omezení zařízení s Windows 10 v následujících kategoriích:

-  Windows Defender
-  Mobilní síť a připojení
-  Prostředí zamknuté obrazovky
-  Ochrana osobních údajů
-  Hledat
-  Windows Spotlight
-  Prohlížeč Edge

Další informace o nastavení Windows 10 najdete v tématu [Nastavení omezení pro zařízení Windows 10 a novější](device-restrictions-windows-10.md).

## <a name="week-of-june-12-2017"></a>Týden 12. června 2017

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Aplikace Portál společnosti pro Android má teď novou činnost koncového uživatele pro zásady ochrany aplikací <!--1305217-->
Na základě zpětné vazby od zákazníků jsme aplikaci Portál společnosti pro Android upravili tak, aby zobrazovala tlačítko **Přístup k obsahu společnosti**. Naším záměrem je předejít zbytečné registraci koncových uživatelů, když pouze potřebují přístup k aplikacím s podporou zásad ochrany aplikací – funkce správy mobilních aplikací Intune. Tyto změny najdete na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nová akce nabídky ke snadnému odebrání Portálu společnosti <!--1164569-->
Na základě zpětné vazby od uživatelů jsme do aplikace Portál společnosti pro Android přidali novou akci nabídky k zahájení odebrání Portálu společnosti ze zařízení. Tato akce odebere zařízení ze správy Intune, aby uživatel mohl aplikaci ze zařízení odebrat. Tyto změny najdete na stránce [novinek v uživatelském rozhraní aplikace](whats-new-app-ui.md) a v [dokumentaci pro koncové uživatele Androidu](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Vylepšení synchronizace aplikace s Windows 10 Creators Update <!--676505-->

Aplikace Portál společnosti pro Windows 10 teď automaticky zahájí synchronizaci pro požadavky na instalaci zařízení s Windows 10 Creators Update (verze 1703). Omezí se tím potíže s pozastavením instalací aplikace ve stavu čekající synchronizace. Uživatelé navíc budou moct synchronizaci zahájit ručně uvnitř aplikace. Tyto změny najdete na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nové prostředí s asistencí pro portál společnosti s Windows 10 <!---1058938--->

Aplikace Portál společnosti pro Windows 10 bude obsahovat návod s pokyny Intune pro zařízení, která nejsou identifikovaná nebo zaregistrovaná. Nové prostředí obsahuje podrobné pokyny, které provedou uživatele registrací do Azure Active Directory (která je nutná pro funkce podmíněného přístupu), a zápis do MDM (který je nutný pro funkce správy zařízení). Prostředí s asistencí bude přístupné z domovské stránky portálu společnosti. Uživatelé můžou aplikaci dál používat, i když registraci a zápis neprovedou, ale budou mít k dispozici omezené funkce.

Tato aktualizace se zobrazí pouze na zařízení s Windows 10 Anniversary Update (build 1607) a novějšími verzemi. Tyto změny najdete na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md).

## <a name="week-of-june-5-2017"></a>Týden 5. června 2017

### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Konzoly správců Microsoft Intune a podmíněného přístupu jsou obecně dostupné

Oznamujeme obecnou dostupnost nové konzoly správce Intune v Azure a konzoly správce podmíněného přístupu. Prostřednictvím Intune v Azure teď můžete spravovat všechny možnosti Intune MAM a MDM v jednom sjednoceném prostředí pro správce a využívat seskupování a cílení Azure AD. Podmíněný přístup v Azure přináší bohaté možnosti v rámci Azure AD a Intune společně v jedné sjednocené konzole. A z prostředí pro správu vám přechod na platformu Azure umožňuje používat moderní prohlížeče.

Intune je teď v konzole Azure na portal.azure.com vidět bez popisku **Preview**.

Pokud jste v centru zpráv nedostali některou z řady zpráv požadující provedení nějaké akce, abychom mohli migrovat vaše skupiny, nemusíte jako stávající zákazníci nic dělat. Možná jste také v centru zpráv dostali oznámení, že migrace trvá déle z důvodu chyb na naší straně. Usilovně pokračujeme v práci na migraci všech ovlivněných zákazníků.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Vylepšení dlaždic aplikací v aplikaci Portál společnosti pro iOS
Aktualizovali jsme vzhled dlaždic aplikací na domovské stránce tak, aby odrážely barvu brandingu nastavenou v Portálu společnosti. Další informace najdete v [novinkách v uživatelském rozhraní aplikace](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Pro aplikaci Portál společnosti pro iOS je teď dostupný výběr účtu
Uživatelům zařízení s iOSem se při přihlašování do Portálu společnosti může zobrazit náš nový výběr účtu, pokud k přihlašování do jiných aplikací Microsoftu používají svůj pracovní nebo školní účet. Další informace najdete v [novinkách v uživatelském rozhraní aplikace](whats-new-app-ui.md).

## <a name="week-of-may-29-2017"></a>Týden 29. května 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Změna autority pro správu mobilních zařízení bez zrušení registrace spravovaných zařízení <!--1103950-->

Autoritu pro správu mobilních zařízení teď můžete změnit, aniž byste museli kontaktovat podporu Microsoftu a zrušit registraci a provést novou registraci stávajících spravovaných zařízení. V konzole Configuration Manageru můžete [změnit autoritu pro správu mobilních zařízení](/sccm/mdm/deploy-use/change-mdm-authority) z Nastavit na nástroj Configuration Manager (hybridní) na Microsoft Intune (samostatné) a naopak.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Vylepšené oznámení pro spouštěcí PIN kódy Samsungu KNOX <!--1087143-->
Když budou koncoví uživatelé potřebovat nastavit spouštěcí PIN kód na zařízeních Samsung KNOX, aby byla kompatibilní se šifrováním, zobrazené oznámení je po klepnutí na ně odkáže přímo na místo v aplikaci Nastavení.  Dříve oznámení odkázalo koncové uživatele na obrazovku pro změnu hesla.


### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Podpora Apple School Manageru (ASM) se sdíleným iPadem <!-- 748864, 770395-->

Pro první registraci zařízení s iOSem teď Intune místo programu Apple Device Enrollment Program podporuje použití Apple School Manageru (ASM). K použití aplikace Classroom pro sdílené iPady a k povolení synchronizace dat z ASM do Azure Active Directory prostřednictvím služby Synchronizace školních dat Microsoftu se vyžaduje zprovoznění ASM. Další informace najdete v tématu [Povolení registrace zařízení s iOSem pomocí Apple School Manageru](apple-school-manager-set-up-ios.md).

> [!NOTE]
> Konfigurace fungování sdílených iPadů s aplikací Classroom vyžaduje konfigurace iOS Education v Azure, které ještě nejsou k dispozici.  Tato funkce bude brzy přidána.

### <a name="device-management"></a>Správa zařízení

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Poskytování vzdálené pomoci na zařízeních s Androidem pomocí TeamVieweru <!-- 675418 -->

Intune vám teď pomocí softwaru [TeamViewer](https://www.teamviewer.com), který se prodává zvlášť, umožňuje poskytovat vzdálenou pomoc uživatelům používajícím zařízení s Androidem. Další informace najdete v článku o [poskytování vzdálené pomoci pro zařízení s Androidem, která se spravují přes Intune](device-profile-android-teamviewer.md).

### <a name="app-management"></a>Správa aplikací

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>Nové podmínky zásad ochrany aplikace pro MAM <!-- 679864 -->

Teď můžete nastavit požadavek pro MAM bez uživatelů registrace, který vynucuje tyto zásady:

- Minimální verzi aplikací
- Minimální verzi operačního systému
- Minimální verzi Intune APP SDK cílové aplikace (pouze iOS)

Tato funkce je k dispozici pro Android i iOS. Intune podporuje vynucení minimální verze pro verze platformy OS, verze aplikací a Intune APP SDK. V iOSu můžou aplikace s integrovanou sadou SDK také nastavit vynucení minimální veze na úrovni SDK. Pokud nebudou splněny minimální požadavky prostřednictvím zásad ochrany aplikace na třech různých úrovních uvedených výše, uživatel nebude moct k cílové aplikaci přistupovat. Uživatel teď může odebrat svůj účet (pro aplikace s více identitami), zavřít aplikaci nebo aktualizovat verzi operačního systému nebo aplikace.

Můžete také nakonfigurovat další nastavení, abyste poskytovali neblokující oznámení, které bude doporučovat upgrade operačního systému nebo aplikace. Toto oznámení se dá zavřít a aplikace se dá používat jako obvykle.

Další informace najdete v [Nastavení zásad ochrany aplikací pro iOS](app-protection-policy-settings-ios.md) a [Nastavení zásad ochrany aplikací pro Android](app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Konfigurace aplikací pro Android for Work <!-- 621621 -->
Některé aplikace pro Android z obchodu podporují možnosti spravované konfigurace, které správci IT umožňují řídit, jak aplikace běží v pracovním profilu. S Intune teď můžete zobrazit konfigurace podporované aplikací a nakonfigurovat je z portálu Intune pomocí návrháře konfigurace nebo editoru JSON. Další informace najdete v článku o [používání konfigurací aplikací pro Android for Work](app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Nová možnost konfigurace aplikací pro MAM bez registrace <!-- 677969 -->

Teď můžete vytvářet zásady konfigurace aplikací prostřednictvím MAM bez kanálu registrace. Tato funkce je ekvivalentní zásadám konfigurace aplikací dostupným v konfiguraci aplikací ve správě mobilních zařízení (MDM). Příklad konfigurace aplikací pomocí MAM bez registrace najdete v článku o [správě přístupu k internetu pomocí zásad Managed Browseru v Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Konfigurace seznamů povolených a blokovaných adres URL pro Managed Browser <!-- 682960 -->

Teď můžete nakonfigurovat seznam povolených a blokovaných domén a adres URL pro Intune Managed Browser pomocí nastavení konfigurace aplikací na portálu Azure Portal. Tato nastavení jde nakonfigurovat bez ohledu na to, jestli se používá na spravovaném nebo nespravovaném zařízení. Další informace najdete v článku o [správě přístupu k internetu pomocí zásad Managed Browseru v Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Zobrazení zásad ochrany aplikací v helpdesku <!-- 1069473 -->

Uživatelé IT Helpdesku teď můžou zkontrolovat stav licencí uživatelů a stav zásad ochrany aplikací přiřazených uživatelům v okně Řešení potíží. Podrobnosti najdete v tématu o [řešení potíží](./help-desk-operators.md).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Řízení navštěvování webů na zařízeních s iOSem <!-- 723832 -->

Můžete teď řídit, které webové stránky můžou uživatelé zařízení s iOSem navštívit, a to pomocí jedné z těchto dvou metod:

- Přidejte povolené a blokované adresy URL pomocí integrovaného filtru webového obsahu od společnosti Apple.

- Povolte přístup z prohlížeče Safari jenom k určeným webovým stránkám. V Safari se vytvoří záložky pro weby, které určíte.

Další informace najdete v článku o [nastavení filtru webového obsahu pro zařízení s iOSem](web-content-filter-settings-ios.md).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Konfigurace oprávnění zařízení pro aplikace Android for Work <!-- 621614 -->

U aplikací nasazených do pracovních profilů zařízení Android for Work můžete teď nakonfigurovat stav oprávnění pro jednotlivé aplikace.  Aplikace pro Android, které vyžadují oprávnění zařízení, jako je například přístup k umístění nebo fotoaparátu zařízení, ve výchozím nastavení vyzvou uživatele, aby oprávnění přijali nebo odmítli.  Pokud například aplikace používá mikrofon zařízení, potom bude koncový uživatel vyzván, aby aplikaci udělil oprávnění používat mikrofon. Tato funkce umožňuje definovat oprávnění jménem koncového uživatele.  Můžete nakonfigurovat oprávnění k a) automatickému odmítnutí bez upozornění uživatele, b) automatickému schválení bez upozornění uživatele nebo c) vyzvání uživatele k přijmutí nebo odmítnutí. Další informace najdete v článku [Nastavení omezení pro zařízení s Androidem for Work v Microsoft Intune](device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Definice PIN kódu aplikace pro zařízení s Androidem for Work <!-- 728976, 1102534 -->

Zařízení s Androidem 7.0 a vyšším s pracovním profilem spravovaným jako zařízení s Androidem for Work umožňují správci definovat zásady hesla, které se vztahují jenom na aplikace v pracovním profilu.  Vaše možnosti jsou:

- Definovat jenom zásady hesla pro celé zařízení – jedná se o heslo, které musí uživatel používat k odemknutí celého zařízení.
- Definovat jenom zásady hesla pracovního profilu – uživatelé budou vyzváni k zadání hesla při každém otevření jakékoli aplikace v pracovním profilu.
- Definovat zásady hesla pro zařízení i pro pracovní profil – správce IT má možnost definovat zásady hesla zařízení a pracovního profilu o různé síle (třeba čtyřmístný PIN kód pro odemknutí zařízení a šestimístný PIN kód pro otevření libovolné pracovní aplikace).

Další informace najdete v článku [Nastavení omezení pro zařízení s Androidem for Work v Microsoft Intune](device-restrictions-android-for-work.md).

> [!NOTE]
> Tyto možnosti jsou k dispozici jenom u Androidu 7.0 a vyššího.  Ve výchozím nastavení může koncový uživatel použít dva samostatně definované PIN kódy, nebo se může rozhodnout zkombinovat tyto dva nadefinované PIN kódy do silnějšího z nich.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Nová nastavení pro zařízení s Windows 10 <!-- 978585 -->

Přidali jsme nová [nastavení omezení zařízení s Windows](device-restrictions-windows-10.md), která řídí funkce, jako jsou bezdrátové displeje, zjišťování zařízení, přepínání úloh a chybové zprávy SIM karet.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Aktualizace konfigurace certifikátu <!-- 918991 and 823198 -->

Při vytváření profilu certifikátu SCEP je pro **Formát názvu subjektu** dostupná možnost **Vlastní** pro zařízení s iOSem, Androidem a Windows. Před touto aktualizací bylo pole **Vlastní** k dispozici jenom pro zařízení s iOSem. Další informace najdete v tématu [Vytvoření profilu certifikátu SCEP] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile).

Při vytváření profilu certifikátu PKCS je pro **Alternativní název subjektu** dostupná možnost **Vlastní atribut Azure AD**. Když vyberete **Vlastní atribut Azure AD**, je dostupná možnost **Oddělení**. Další informace najdete v tématu [Vytvoření profilu certifikátu PKCS] (certficates-pfx-configure.md#how-to-create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Konfigurace víc aplikací, které můžou být spuštěné, když je zařízení s Androidem v režimu veřejného terminálu (kiosku) <!-- 662059 -->

Když je zařízení s Androidem v režimu veřejného terminálu, mohli jste dřív konfigurovat jenom jednu aplikaci, která mohla být spuštěná. Teď můžete konfigurovat víc aplikací pomocí ID aplikace, adresy URL obchodu nebo výběrem aplikace pro Android, kterou už spravujete. Další informace najdete v tématu o [nastavení režimu veřejného terminálu (kiosku)](device-restrictions-android.md#kiosk).


## <a name="notices"></a>Sdělení

### <a name="ip-addresses-for-intune-updated----1175274---"></a>IP adresy pro Intune aktualizovány <!-- 1175274 -->

K dispozici je [aktualizovaný seznam názvů DNS a IP adres](/intune/network-bandwidth-use) pro nastavení proxy serveru brány firewall.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Používání Azure Active Directory pro podmíněný přístup <!-- 967947 -->

Podmíněný přístup je k dispozici v sekci Azure Active Directory konzoly Azure a poskytuje výkonnější a flexibilnější rozhraní pro nastavení zásad pro cloudové aplikace jako Office 365 Exchange Online a SharePoint Online.  Místo klasické konzoly Intune použijte ke konfiguraci nastavení zásad okno **Podmíněný přístup v Azure Active Directory**. Existující zásady v klasické konzole Intune se musí v konzole Azure znovu vytvořit. Další informace najdete v článku o [vytvoření zásad podmíněného přístupu Azure AD](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Přímý přístup ke scénářům registrace Apple <!--951869-->

U účtů Intune vytvořených po lednu 2017 umožňuje Intune přímý přístup ke scénářům registrace Apple pomocí úlohy Registrovat zařízení na portálu Azure Portal. Náhled na registraci Apple byl předtím přístupný přes odkazy na portálu klasické služby Intune. Zpřístupnění těchto funkcí v Azure vyžaduje u účtů Intune vytvořených před lednem 2017 jednorázovou migraci. Plán této migrace zatím nebyl oznámen, podrobnosti ale budou zpřístupněny co nejdříve. Pokud váš existující účet nemá k portálu Azure Portal přístup, k otestování tohoto nového prostředí důrazně doporučujeme vytvořit zkušební účet.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Nahrazení rolí správy na portálu Azure Portal

Existující role pro správu mobilních aplikací (MAM) (Přispěvatel, Vlastník a Jen pro čtení) používané v klasickém portálu Intune (Silverlight) byly na portálu Azure Portal pro Intune nahrazeny celou řadou nových možností řízení přístupu na základě role (RBAC). Jakmile migrujete na portál Azure Portal, bude potřeba, abyste svým správcům přiřadili tyto nové role správy. Další informace o RBAC a nových rolích najdete v článku [Řízení přístupu na základě role pro Microsoft Intune](/intune/role-based-access-control).

## <a name="whats-coming"></a>Co připravujeme

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Konec podpory pro Android verze 4.3 a nižší <!---1171127, 1326920 --->
Spravované aplikace a aplikace Portál společnosti pro Android budou pro přístup k firemním prostředkům vyžadovat operační systém Android 4.4 nebo novější. Zařízení, která nebudou do začátku října aktualizována, již nebudou mít k těmto aplikacím nebo k Portálu společnosti přístup. Od prosince budou všechna zaregistrovaná zařízení vyřazena, čímž dojde ke ztrátě přístupu k firemním prostředkům. Pokud používáte zásady ochrany aplikací bez správy mobilních zařízení MDM, aplikace nebudou získávat aktualizace a kvalita jejich činnosti bude časem upadat.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017"></a>Připomenutí podpory platformy: všeobecná podpora Windows Phone 8.1 končí 11. července 2017
<!-- 1327781 -->

11. července 2017 končí všeobecná podpora platformy Windows Phone 8.1. Podporu počítačů s Windows 8.1 to neovlivní.

Na žádné zařízení s Windows Phone 8.1, které je spravováno službou Intune, to nebude mít okamžitý vliv. Zaregistrovaná zařízení budou nadále fungovat a všechny zásady, konfigurace a aplikace také. Všimněte si, že pro aplikaci Portál společnosti pro Windows Phone 8.1 ani pro platformu Windows Phone 8.1 v rámci služby Intune neexistují žádná cílená vylepšení.

Doporučujeme vám, abyste při nejbližší příležitosti způsobilá zařízení s Windows Phone 8.1 upgradovali na Windows 10 Mobile. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Změny v podpoře pro aplikaci Portál společnosti Intune pro iOS  <!-- 1164474  -->


Již brzy bude dostupná nová verze aplikace Portál společnosti Microsoft Intune pro iOS, která bude podporovat pouze zařízení se systémem iOS 9.0 nebo novějším. Verze podporující iOS 8 bude ještě na krátkou dobu k dispozici. Upozorňujeme vás, že pokud také používáte iOS aplikace s podporou MAM, podporujeme je pouze u verze iOS 9.0 a novější. Proto zajistěte, aby vaši koncoví uživatelé provedli aktualizaci na nejnovější verzi operačního systému. 

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Přestože nemáme konkrétní datum, dáváme vám to vědět předem, abyste měli čas si to naplánovat. Zajistěte, aby vaši uživatelé měli iOS 9.0 nebo novější, a jakmile vyjde nová verze aplikace Portál společnosti, požádejte své koncové uživatele, aby tuto aplikaci aktualizovali.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?

Upozorněte své uživatele, že aby mohli naplno využívat nových funkcí služby Intune, musí si iOS aktualizovat na verzi 9.0 nebo novější.  Vyzvěte uživatele, aby si nainstalovali novou verzi aplikace Portál společnosti a mohli využívat nově nabízených funkcí.

Na portálu Azure Portal přejděte do služby Intune, zobrazte si Zařízení > Všechna zařízení a vyfiltrujte si je podle verze systému iOS, abyste viděli všechna zařízení s operačními systémy staršími než iOS 9.

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Vylepšené přihlašování k aplikacím Portál společnosti na všech platformách <!--User Story 1132123-->

Avizujeme změnu, kterou uvedeme během několika nadcházejících měsíců a která vylepší přihlašování k aplikacím Portál společnosti Intune v systémech Android, iOS a Windows. Nové uživatelské prostředí se automaticky zobrazí na všech platformách pro aplikaci Portál společnosti, až Azure AD tuto změnu provede. Kromě toho se teď uživatelé můžou k Portálu společnosti přihlašovat z jiného zařízení pomocí vygenerovaného kódu na jedno použití. To se hodí hlavně v případech, kdy se uživatelé potřebují přihlásit bez přihlašovacích údajů.

Snímky obrazovky předchozího způsobu přihlašování, nového způsobu přihlašování pomocí přihlašovacích údajů a nového způsobu přihlašování z jiného zařízení najdete v [novinkách v uživatelském rozhraní aplikací](/intune/whats-new-app-ui).

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Plánovaná změna: Intune mění způsob fungování portálu Intune Partner Portal<!-- 1050016 -->

Počínaje aktualizací služby v polovině května 2017 odstraníme stránku Intune Partner z manage.microsoft.com.  

Pokud jste partnerským správcem, nebude už moct stránku Intune Partner zobrazit a provádět z ní jménem vašich zákazníků kroky, ale místo toho se budete muset přihlásit k jednomu ze dvou dalších partnerských portálů Microsoftu.

K účtům zákazníků, které spravujete, se budete moct přihlásit z [Partnerského centra Microsoftu](https://partnercenter.microsoft.com/) a [Centra pro partnerskou správu Office 365](https://portal.office.com/). V budoucnu jako partneři prosím ke správě svých zákazníků používejte jeden z těchto webů.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple bude vyžadovat aktualizace ATS (Application Transport Security) <!--748318-->

Apple oznámil, že začne vynucovat specifické požadavky na ATS (Application Transport Security). ATS se používá k vynucení vyššího zabezpečení veškeré komunikace aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune, kteří používají aplikace Portál společnosti pro iOS.

Prostřednictvím programu Apple TestFlight, který vynucuje nové požadavky na ATS, jsme zpřístupnili verzi aplikace Portál společnosti pro iOS. Pokud si ji chcete vyzkoušet a otestovat, jestli ATS dodržujete, napište nám na adresu <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> zprávu s vaším jménem a příjmením, e-mailovou adresou a názvem společnosti. Další podrobnosti najdete v [blogu podpory služby Intune](https://aka.ms/compportalats).

### <a name="see-also"></a>Viz taky
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co je nového v uživatelském rozhraní Portálu společnosti](whats-new-app-ui.md)
* [Novinky v předchozích měsících](whats-new-archive.md)
