---
title: Novinky v Microsoft Intune – Azure | Microsoft Docs
titlesuffix: ''
description: Zjistěte, jaké novinky přináší portál Intune Azure.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/09/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: c929fd8c01eda062d54b818996bebe02807e2f55
ms.sourcegitcommit: dec09e9c91322ca347276785aca3c50036956f32
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/17/2018
ms.locfileid: "51859558"
---
# <a name="whats-new-in-microsoft-intune"></a>Co je nového v Microsoft Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zjistěte, jaké novinky každý týden přináší Microsoft Intune. Najdete zde také chystané změny, [důležitá sdělení](#notices) a informace o [předchozích verzích](whats-new-archive.md). Některé funkce můžou vycházet v průběhu několika týdnů a nemusí být k dispozici všem zákazníkům hned první týden.

> [!Note]
> Informace o nových funkcích v hybridní správě mobilních zařízení (MDM) najdete na [stránce s novinkami pro hybridní MDM](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->     
## <a name="week-of-november-5-2018"></a>Týden od 5. listopadu 2018

### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Podpora iOS 12 OAuth v e-mailových profilech systému iOS <!--2155106 -->

E-mailové profily Intune pro iOS podporují OAuth (Open Authorization) v iOS 12. Pokud chcete tuto funkci zobrazit, vytvořte nový profil (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **iOS** jako platforma > **E-mail** jako typ profilu), nebo aktualizujte existující e-mailový profil iOS. Pokud OAuth povolíte v profilu, který už je nasazený uživatelům, jsou uživatelé vyzváni k opětovnému ověření a stažení svých e-mailů.

[E-mailové profily pro iOS](email-settings-ios.md) obsahují více informací o použití OAuth.

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview----1048100--"></a>Podpora Autopilotu pro zařízení připojená k hybridní službě Azure Active Directory (Preview) <!-- 1048100-->
Zařízení připojená k hybridní službě Azure Active Directory si teď můžete nastavit pomocí Autopilotu. Zařízení musí být připojená do vaší podnikové sítě, aby mohla použít hybridní funkci Autopilotu. Další informace najdete v článku o [nasazení zařízení připojených k hybridní službě Azure AD pomocí Intune a Windows Autopilotu](windows-autopilot-hybrid.md).
Tato funkce se bude zavádět pro uživatelskou základnu v průběhu několika dalších dnů. Následující postup bude možné provést až po jejím zavedení pro váš účet.

### <a name="app-protection-policy-app-settings-for-web-data----2662995----"></a>Nastavení zásady ochrany aplikací (APP) pro webová data <!-- 2662995  -->
Nastavení zásad ochrany aplikací (APP) pro webový obsah na zařízeních s Androidem a iOSem je aktualizované, aby lépe pracovalo s webovými odkazy http a https a také s přenosy dat prostřednictvím univerzálních odkazů iOS a odkazů na aplikace pro Android.  

## <a name="week-of-october-29-2018"></a>Týden od 29. října 2018


### <a name="app-management"></a>Správa aplikací

#### <a name="require-non-biometric-pin-after-a-specified-timeout----1506985---"></a>Po uplynutí časového limitu se vyžaduje nebiometrický kód PIN <!-- 1506985 -->
Po uplynutí časového limitu určeného správcem Intune požaduje nebiometrický kód PIN. Služba tak lépe zabezpečí aplikace s podporou Správy mobilních aplikací (MAM), protože omezí použití biometrické identifikace pro přístup k firemním datům. Toto nastavení má vliv na uživatele, kteří pro přístup k aplikacím s podporou APP/MAM používají Touch ID (iOS), Face ID (iOS), Biometriku Androidu nebo jiné budoucí způsoby biometrického ověřování. S tímto nastavením mají správci Intune přesnější kontrolu nad přístupem uživatelů, takže mohou vyloučit případy, kdy zařízení s více otisky prstů nebo jinými biometrickými metodami přístupu může odhalit firemní data nesprávnému uživateli. Na portálu Azure Portal otevřete **Microsoft Intune**. Vyberte **Klientské aplikace** > **Zásady ochrany aplikací** > **Přidat zásadu** > **Nastavení**. Najděte část **Přístup** s konkrétními nastaveními. Informace o nastavení přístupu najdete v [nastavení iOSu](app-protection-policy-settings-ios.md#access-settings) a [nastavení Androidu](app-protection-policy-settings-android.md#access-settings).

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Nastavení Intune APP pro přenos dat na zařízeních s iOS zaregistrovaných v MDM <!-- 2244713 -->
Ovládání nastavení Intune APP pro přenos dat na zařízeních s iOSem zaregistrovaných v MDM můžete oddělit od zadání identity registrovaného uživatele, která se označuje také jako hlavní název uživatele (UPN). Správci, kteří nepoužívají aplikaci IntuneMAMUPN, nezaznamenají změnu chování. Pokud je tato funkce k dispozici, musí správci, kteří k řízení chování při přenosech dat na registrovaných zařízeních používají Intune MAMUPN, zkontrolovat nové nastavení a podle potřeby aktualizovat nastavení APP.

#### <a name="windows-10-win32-apps----2617325---"></a>Aplikace Win32 pro Windows 10 <!-- 2617325 -->
Aplikace Win32 můžete nakonfigurovat tak, aby se instalovaly v kontextu uživatele pro jednotlivé uživatele, nebo pro všechny uživatele zařízení.

#### <a name="windows-win32-apps-and-powershell-scripts----2617330---"></a>Aplikace Win32 pro Windows a powershellové skripty <!-- 2617330 -->
Koncoví uživatelé už nemusí být kvůli instalaci aplikací Win32 nebo spouštění powershellových skriptů přihlášení k zařízení. 

#### <a name="troubleshooting-client-app-installation----1363711---"></a>Řešení potíží s instalací klientských aplikací <!-- 1363711 -->
Potíže s instalací klientských aplikací můžete řešit tak, že se podíváte do sloupce s názvem **Instalace aplikace** v okně **Řešení potíží**. Okno **Řešení potíží** zobrazíte tak, že na portálu Intune vyberete **Řešení potíží** v části **Nápověda a podpora**.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="network-access-control-support-on-ios-vpn-clients----1333693-wnready---"></a>Podpora řízení přístupu k síti na klientech VPN v iOSu <!-- 1333693 wnready -->
V této aktualizaci zavádíme nové nastavení, kterým můžete při vytváření konfiguračního profilu VPN pro Cisco AnyConnect, F5 Access a Citrix SSO pro iOS povolit řízení přístupu k síti (NAC). Toto nastavení umožní zahrnutí ID NAC zařízení do profilu VPN. V současné době neexistují žádní klienti VPN ani partnerská řešení NAC podporující toto nové ID NAC, ale jakmile se tak stane, budeme vás informovat prostřednictvím [blogového příspěvku o podpoře](ttps://aka.ms/iOS12_and_vpn).

Abyste mohli používat NAC, budete muset:
1. vyjádřením výslovného souhlasu povolit službě Intune zahrnout ID zařízení do profilů VPN,
2. aktualizovat software nebo firmware poskytovatele NAC pomocí pokynů, které získáte přímo od svého poskytovatele NAC.

Informace o tomto nastavení v profilu VPN v iOSu najdete v článku, který se zabývá [přidáním nastavení VPN v zařízeních s iOSem v Microsoft Intune](vpn-settings-ios.md). Další informace o řízení přístupu k síti najdete v článku [Integrace řešení pro řízení přístupu k síti (NAC) do Intune](network-access-control-integrate.md). 

Platí pro: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>Odebrání e-mailového profilu ze zařízení, i když je na zařízení jenom jen jeden takový profil <!-- 1818139 -->
Dříve nebylo možné ze zařízení odebrat e-mailový profil, *pokud* jich tam nebylo více. S touto aktualizací se toto chování změní. Teď můžete e-mailový profil odebrat, i když na zařízení není žádný další. Podrobnosti najdete v tématu [Přidání e-mailového nastavení na zařízení pomocí Intune](email-settings-configure.md).

#### <a name="powershell-scripts-and-aad----2309469---"></a>Powershellové skripty a AAD <!-- 2309469 -->
Cílem powershellových skriptů v Intune mohou být skupiny zabezpečení zařízení služby AAD.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nové výchozí nastavení Požadovaný typ hesla pro Android, Android Enterprise <!-- 2649963 -->
Když vytvoříte nové zásady dodržování předpisů (**Intune** > **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu** > **Android** nebo **Android Enterprise** pro Platforma > Zabezpečení systému), výchozí hodnota pro **Požadovaný typ hesla** se změní:

z: Výchozí ze zařízení na: Aspoň číslice.

Platí pro Android, Android Enterprise.

Pokud se chcete podívat na tato nastavení, přejděte do [Androidu](compliance-policy-create-android.md) nebo [Androidu Enterprise](compliance-policy-create-android-for-work.md).

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Použití předsdíleného klíče v profilu sítě Wi-Fi ve Windows 10 <!-- 2662938 -->
S touto aktualizací můžete k ověření konfiguračního profilu sítě Wi-Fi pro Windows 10 použít předsdílený klíč (PSK) s protokolem zabezpečení WPA/WPA2-osobní. U zařízení s Windows 10 a aktualizací ze října 2018 můžete také zadat konfiguraci nákladů pro síť s měřením dat.

Pokud chcete použít předsdílený klíč, musíte v současnosti importovat profil Wi-Fi nebo vytvořit vlastní profil. Seznam aktuálních nastavení je v [nastavení sítě Wi-Fi pro Windows 10](wi-fi-settings-windows.md). 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>Odebrání certifikátů PKCS a SCEP ze zařízení <!-- 3218390 -->
V některých scénářích zůstávaly certifikáty PKCS a SCEP na zařízeních i po odebrání zásad ze skupiny, odstranění nasazené konfigurace nebo nastavení pro dodržování předpisů nebo aktualizaci existujícího profilu SCEP nebo PKCS správcem. Tato aktualizace toto chování mění. Budou existovat určité scénáře, kdy se certifikáty PKCS a SCEP ze zařízení odeberou, a jiné scénáře, kdy tyto certifikáty zůstanou na zařízení. Tyto scénáře najdete v tématu [Odebrání certifikátů SCEP a PKCS v Microsoft Intune](remove-certificates.md).

#### <a name="use-gatekeeper-on-macos-devices-for-compliance----2504381---"></a>Použití Gatekeeperu na řízení s macOS za účelem dodržování předpisů <!-- 2504381 -->
Tato aktualizace zahrnuje Gatekeeper pro macOS, který umožňuje u zařízení vyhodnotit dodržování předpisů. Pokud chcete nastavit vlastnost Gatekeeper, přejděte na článek [Přidání zásad dodržování předpisů pro zařízení s macOS v Intune](compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="enrollment-abandonment-report----1382924---"></a>Sestava opuštění registrace <!-- 1382924 -->
Nová sestava, která poskytuje podrobné informace o opuštěných registracích, je k dispozici v části **Registrace zařízení** > **Monitorování**. Další informace najdete v článku, který se věnuje [sestavě opuštění Portálu společnosti](enrollment-report-company-portal-abandon.md).

#### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Nová funkce podmínek použití služby Azure Active Directory <!-- 2870393 -->
Azure Active Directory má funkci podmínek použití, kterou můžete využít místo stávajících podmínek a ujednání služby Intune. Funkce podmínek použití služby Azure AD poskytuje větší flexibilitu ohledně toho, které podmínky a kdy se mají zobrazovat, lepší podporu lokalizace, větší kontrolu nad tím, jak se podmínky vykreslují, a vylepšené generování sestav. Funkce podmínek použití služby Azure AD vyžaduje Azure Active Directory Premium P1, která je také součástí sady Enterprise Mobility + Security E3. Další informace najdete v článku [Správa firemních podmínek a ujednání pro přístup uživatelů](terms-and-conditions-create.md).

### <a name="android-device-owner-mode-support---3188762--"></a>Podpora režimu vlastníka zařízení Android <!--3188762-->
U registrace mobilního zařízení Samsung Knox teď Intune podporuje registraci zařízení do režimu správy Vlastník zařízení Android. Uživatelé připojení prostřednictvím Wi-Fi nebo mobilních sítí mohou svá zařízení při prvním zapnutí registrovat několika klepnutími. Další informace najdete v článku věnovaném [automatické registraci zařízení s Androidem pomocí technologie Knox Mobile Enrollment od Samsungu](android-samsung-knox-mobile-enroll.md).

### <a name="device-management"></a>Správa zařízení

### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Seskupení zařízení zaregistrovaných ve Windows Autopilotu podle ID korelátoru <!-- 2075110 -->
Intune teď podporuje seskupování zařízení s Windows podle ID korelátoru, pokud jsou zaregistrovaná pomocí [Autopilotu pro existující zařízení](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) v nástroji Configuration Manager. ID korelátoru je parametr konfiguračního souboru Autopilotu. Intune automaticky nastaví [atribut enrollmentProfileName zařízení služby Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) tak, aby odpovídal nastavení OfflineAutopilotprofile-<correlator ID>. Umožní se tím, aby se pro offline registrace Autopilotu vytvořily libovolné dynamické skupiny Azure AD na základě ID korelátoru prostřednictvím atributu enrollmentprofileName. Další informace najdete v tématu [Windows Autopilot pro existující zařízení](enrollment-autopilot.md#windows-autopilot-for-existing-devices).

### <a name="intune-app-protection-policies----2984657---"></a>Zásady ochrany aplikací Intune <!-- 2984657 -->
Zásady ochrany aplikací Intune umožňují pro aplikace chráněné přes Intune (například Microsoft Outlook a Microsoft Word) nakonfigurovat různá nastavení ochrany dat. Změnili jsme vzhled těchto nastavení jak pro [iOS](app-protection-policy-settings-ios.md), tak i pro [Android](app-protection-policy-settings-android.md), abychom usnadnili vyhledání jednotlivých nastavení. Existují tři kategorie nastavení zásad:
- **Přemístění dat** – tato skupina obsahuje kontrolní mechanismy ochrany před únikem informací, například omezení operací Vyjmout, Kopírovat, Vložit a Uložit jako. Tato nastavení určují, jak uživatelé pracují s daty v aplikacích.
- **Požadavky na přístup** – tato skupina obsahuje možnosti kódu PIN pro jednotlivé aplikace, které určují, jak koncový uživatel získá přístup k aplikacím v pracovním kontextu.  
- **Podmíněné spouštění** – tato skupina obsahuje nastavení, jako je minimální verze operačního systému, detekce zařízení s jailbreakem a rootem a období odkladu pro offline režim.  
  
Funkčnost těchto nastavení se nemění, ale bude snazší je vyhledat při vytváření zásad.

### <a name="new-intune-device-subscription-sku---3312071--"></a>Nová skladová položka pro předplatné Intune na základě zařízení !--3312071-->
Abychom v podnicích pomohli snížit náklady na správu zařízení, nabízíme teď novou skladovou položku pro předplatné na základě zařízení. Tato skladová položka je licencovaná měsíčně podle počtu zařízení. Ceny se liší podle licenčního programu. Je dostupná přes přímý kanál, smlouvu Enterprise (EA), program MPSA (Microsoft Products and Services) a programy Open a Cloud Solution Provider (CSP).

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps----1727158---"></a>Intune bude u obchodních aplikací podporovat maximální velikost balíčku 8 GB <!-- 1727158 -->
Služba Intune zvýšila maximální velikost balíčku u obchodních aplikací na 8 GB. Další informace najdete v článku [Přidání aplikací do Microsoft Intune](apps-add.md).

#### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Přidání vlastní firemní image pro aplikaci Portál společnosti <!-- 1916266 -->
Správce služby Microsoft Intune může nahrát obrázek vlastní značky, který se v aplikaci Portál společnosti pro iOS zobrazí jako pozadí stránky s profilem uživatele. Další informace o konfiguraci aplikace Portál společnosti najdete v tématu [Konfigurace aplikace Portál společnosti služby Microsoft Intune](company-portal-app.md).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Intune bude udržovat lokalizovaný jazyk Office při aktualizaci Office na počítačích koncových uživatelů <!-- 2971030 -->
Když Intune nainstaluje Office na počítače koncových uživatelů, získají koncoví uživatelé automaticky stejné jazykové sady, které měli s předchozími instalacemi Office .MSI. Další informace najdete v článku [Přiřazení aplikací Office 365 k zařízením s Windows 10 pomocí Microsoft Intune](apps-add-office365.md).

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal----3076965---"></a>Nové prostředí pro podporu v Intune na portálu Správa zařízení Microsoft 365 <!-- 3076965 -->
Na [portálu Správa zařízení Microsoft 365]( http://devicemanagement.microsoft.com) zavádíme nové prostředí pro nápovědu a podporu Intune. Nové prostředí vám umožňuje popsat problém vlastními slovy a získat přehled možností řešení potíží a postupy z webu, jak problém opravit. Tato řešení jsou nabízena prostřednictvím algoritmů strojového učení založeného na pravidlech, které se řídí dotazy uživatelů.  

Kromě pokynů ke konkrétnímu problému můžete také využít nového pracovního postupu vytváření případů a otevřít případ podpory e-mailem nebo telefonicky.  

U zákazníků v této vlně nasazení toto nové prostředí nahradí aktuální prostředí pro nápovědu a podporu, které obsahuje statickou skupinu předem vybraných možností. Ty jsou založené na oblasti konzoly, ve které se nacházíte při otevření nápovědy a podpory.  

*Toto nové prostředí pro nápovědu a správu zavádíme pro některé, ale ne všechny tenanty, a najdete ho na portálu Správa zařízení. Účastníci nasazení tohoto nového prostředí jsou náhodně vybráni z dostupných tenantů Intune. Nové tenanty budeme přidávat postupně tak, jak budeme nasazení rozšiřovat.*  

Další informace najdete v tématu [Nové prostředí pro nápovědu a podporu](get-support.md#new-help-and-support-experience) v článku Jak získat podporu pro Microsoft Intune.  

### <a name="powershell-module-for-intune--preview-available----wnready-951068---"></a>Modul prostředí PowerShell pro Intune – k dispozici ve verzi Preview <!-- wnready 951068 -->
Nový modul prostředí PowerShell, který poskytuje podporu pro rozhraní Intune API prostřednictvím Microsoft Graphu, je teď dostupný ve verzi Preview na [GitHubu]( https://aka.ms/intunepowershell). Podrobnosti o tom, jak tento modul používat, najdete v souboru README v uvedeném umístění. 


## <a name="week-of-october-15-2018"></a>Týden od 15. října 2018

### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>Výzva k zadání kódu PIN po změnách otisků prstů nebo Face ID na zařízení s iOSem <!-- 2637704  -->
Uživatelům se teď po provedení biometrických změn na zařízení s iOSem zobrazuje výzva k zadání kódu PIN. Týká se to i změn zaregistrovaných otisků prstů nebo Face ID. Načasování výzvy závisí na konfiguraci časového limitu *Překontrolovat požadavky na přístup za (minuty)*.  Pokud není kód PIN nastavený, zobrazí se uživateli výzva k jeho nastavení. 
 
Tato funkce je dostupná jen pro iOS a vyžaduje zapojení aplikací, které integrují sadu Intune APP SDK pro iOS verze 9.0.1 nebo novější. Integrace této sady SDK je nezbytná kvůli vynucení tohoto chování u cílových aplikací. K této integraci dochází průběžně a závisí na týmech konkrétních aplikací. Mezi zapojené aplikace patří například WXP, Outlook, Managed Browser a Yammer.


## <a name="week-of-october-1-2018"></a>Týden od 1. října 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Přístup ke klíčovým vlastnostem profilu pomocí aplikace Portál společnosti <!-- 772203 -->
Koncoví uživatelé teď mají přístup ke klíčovým vlastnostem účtu a akcím, jako je například resetování hesla, z aplikace Portál společnosti. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Nastavením zásad ochrany aplikací v iOSu se dají zablokovat klávesnice jiných výrobců <!-- 1248481 -->
Na zařízeních s iOSem můžou správci Intune zablokovat použití klávesnic jiných výrobců pro přístup k datům organizace z aplikací chráněných zásadami. Když budou nastavené Zásady ochrany aplikací (APP) k blokování klávesnic jiných výrobců, uživatelům zařízení se při první interakci s firemními daty pomocí klávesnice jiného výrobce zobrazí zpráva. Všechny jiné možnosti než nativní klávesnice budou zablokované a uživatelům zařízení se nezobrazí. Uživatelům se dialog se zprávou zobrazí jenom jednou. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>Přístup uživatelského účtu k aplikacím Intune na spravovaných zařízeních s Androidem a iOSem <!-- 1248496 -->
Jako správce Microsoft Intune můžete řídit, které uživatelské účty se přidají do aplikací Microsoft Office na spravovaných zařízeních. Můžete omezit přístup jenom na povolené uživatelské účty organizace a zablokovat osobní účty na zaregistrovaných zařízeních. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>Zásada konfigurace aplikace Outlook pro iOS a Android <!--1828527 -->
Teď můžete vytvořit zásadu konfigurace aplikace Outlook pro iOS a Android pro místní uživatele, kteří využívají základní ověřování pomocí protokolu ActiveSync. Další nastavení konfigurace se přidají po jejich povolení pro Outlook pro iOS a Android.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Jazykové sady Office 365 Pro Plus <!-- 1833450 -->
Jako správce Intune budete moct nasadit další jazyky pro aplikace Office 365 Pro Plus spravované prostřednictvím Intune. Seznam dostupných jazyků zahrnuje **Typ** jazykové sady (Základní, Částečná a Kontrola pravopisu). Na portálu Azure Portal vyberte **Microsoft Intune** > **Klientské aplikace** > **Aplikace** > **Přidat**. V okně **Přidat aplikaci** v seznamu **Typ aplikace** vyberte v části **Sada Office 365** možnost **Windows 10**. V okně **Nastavení sady aplikací** vyberte **Jazyky**.

####  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Přípony souborů obchodních aplikací pro Windows <!-- 1884873 -->
Přípony souborů obchodních aplikací pro Windows teď budou zahrnovat *.msi*, *.appx*, *.appxbundle*, *.msix* a *.msixbundle*. Aplikaci můžete v Microsoft Intune přidat výběrem možností **Klientské aplikace** > **Aplikace** > **Přidat**. Zobrazí se podokno **Přidat aplikaci**, které vám umožní vybrat **Typ aplikace**. Pro obchodní aplikace pro Windows vyberte jako typ aplikace **Obchodní aplikace**, vyberte **Soubor balíčku aplikace** a pak zadejte instalační soubor s příslušnou příponou.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Nasazení aplikací pro Windows 10 pomocí Intune <!-- 2309001 -->
S využitím stávající podpory obchodních aplikací a Microsoft Storu pro obchodní aplikace mohou správci prostřednictvím Intune nasadit většinu svých firemních aplikací koncovým uživatelům, kteří používají zařízení s Windows 10. Správci mohou přidávat, instalovat a odinstalovávat aplikace pro uživatele Windows 10 v různých formátech, jako jsou MSI, Setup.exe nebo MSP. Před stažením a instalací Intune vyhodnotí pravidla požadavků a prostřednictvím centra akcí Windows 10 upozorní koncové uživatele na stav nebo požadavky na restartování. Tato funkce účinně uvolňuje ruce organizacím, které chtějí přesunout tuto úlohu do Intune a do cloudu. Tato funkce je v tuto chvíli ve veřejné verzi Preview. Očekáváme, že během několik dalších měsíců přidáme k této funkci důležité nové schopnosti. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Místní nabídka zařízení a aplikací koncových uživatelů <!-- 2771453 -->
Koncoví uživatelé teď můžou pomocí místní nabídky zařízení a aplikací aktivovat běžné akce, jako jsou například přejmenování zařízení nebo kontrola dodržování předpisů. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>Klávesové zkratky v Portálu společnosti pro Windows <!-- 2771518 -->
Koncoví uživatelé teď budou moct aktivovat akce aplikací a zařízení v aplikaci Portál společnosti pro Windows pomocí klávesových zkratek (akcelerátorů).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>Vytvoření přípon DNS v konfiguračních profilech sítě VPN na zařízeních s Windows 10 <!-- 1333668 -->
Při vytváření profilu konfigurace zařízení v síti VPN (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** Platforma > **VPN** pro typ profilu), zadáváte nastavení DNS. S touto aktualizací můžete také zadat v Intune více **přípon DNS**. Pokud použijete přípony DNS, můžete k vyhledání síťového prostředku použít jeho krátký název místo plně kvalifikovaného názvu domény (FQDN). V této aktualizaci můžete v Intune změnit pořadí přípon DNS.
Seznam aktuálních nastavení DNS je v [nastavení sítě VPN ve Windows 10](vpn-settings-windows-10.md#dns-settings).
Platí pro: zařízení s Windows 10

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Podpora neustále aktivních pracovních profilů sítě VPN pro Android Enterprise <!-- 1333705 -->
V této aktualizaci můžete využít neustále aktivní připojení VPN na zařízeních s Androidem Enterprise, která používají spravované pracovní profily. Neustále aktivní připojení VPN zůstávají ve spojení nebo se ihned znovu připojí, jakmile uživatel odemkne zařízení, zařízení se restartuje nebo se změní bezdrátová síť. Připojení také můžete přepnout do „zamčeného“ režimu, který blokuje veškerý síťový provoz, dokud není připojení VPN zase aktivní.
Neustále aktivní připojení VPN můžete povolit v nastavení **Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Android Enterprise** pro platformu > **Omezení zařízení** > **Možnosti připojení**.

#### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>Vydání certifikátů SCEP zařízením bez uživatele <!-- 1744554 -->
Certifikáty se v současnosti vydávají jenom uživatelům. S touto aktualizací můžete certifikáty SCEP vydat i zařízením, včetně zařízení bez uživatelů, jako jsou terminály (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** pro platformu > **Certifikát SCEP** pro profil). Další aktualizace zahrnují:
- Vlastnost **Subjekt** v profilu SCEP je nyní vlastní textové pole, které může obsahovat nové proměnné. 
- Vlastnost **Alternativní název subjektu (SAN)** v profilu SCEP má nyní formát tabulky a může obsahovat nové proměnné. Správce může do tabulky přidat atribut a vyplnit hodnotu vlastního textového pole. Alternativní název subjektu (SAN) podporuje následující atributy: 
  - DNS
  - E-mailová adresa
  - UPN

  Tyto nové proměnné můžete přidat jako statický text do textového pole s vlastní hodnotou. Například atribut DNS můžete přidat jako `DNS = {{AzureADDeviceId}}.domain.com`.

  > [!NOTE]
  > Ve statickém textu alternativního názvu subjektu (SAN) nejdou použít složené závorky, středníky ani svislé čáry (|). Do složených závorek můžete uzavřít jenom jednu z nových proměnných certifikátu zařízení, aby mohla být přijata jako `Subject` nebo `Subject alternative name`. 

Nové proměnné certifikátu zařízení:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
>  - `{{FullyQualifiedDomainName}}` funguje jenom pro Windows a zařízení připojená k doméně. 
>  -  Když do subjektu nebo alternativního názvu subjektu (SAN) pro certifikát zařízení zadáváte vlastnosti zařízení, jako je IMEI, sériové číslo a plně kvalifikovaný název domény, uvědomte si, že osoba, která má k zařízení přístup, může tyto vlastnosti zfalšovat. 

V části [Vytvoření profilu certifikátu SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile) je seznam aktuálních proměnných při vytvoření konfiguračního profilu SCEP. 

Platí pro: Windows 10 a novější a iOS, podporuje síť Wi-Fi

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Vzdálené zamčení nevyhovujících zařízení <!-- 2064495 -->
Pokud zařízení nevyhovuje, můžete vytvořit akci, která vychází ze zásady dodržování předpisů a která zařízení vzdáleně zamkne. V Intune vyberte **Dodržování předpisů zařízením**, vytvořte novou nebo vyberte některou ze stávajících zásad > **Vlastnosti**. Vyberte **Akce při nedodržení předpisů** > **Přidat** a zvolte, že chcete zařízení vzdáleně zamknout.
Podporované platformy: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8.1 nebo novější 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>Vylepšení profilu zařízení s beznabídkovým režimem se systémem Windows 10 a novějším na webu Azure Portal <!-- 2748224 -->
Tato aktualizace zahrnuje následující vylepšení konfiguračního profilu zařízení s beznabídkovým režimem s Windows 10 (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** pro platformu > **Beznabídkový režim (Preview)** pro typ profilu): 
- V současnosti můžete na stejném zařízení vytvářet více profilů beznabídkového režimu. Po této aktualizaci bude Intune u každého zařízení podporovat jenom jeden profil. Pokud přesto potřebujete více profilů beznabídkového režimu, můžete použít vlastní identifikátor URI.
- V profilu **Beznabídkový režim s více aplikacemi** můžete vybrat velikost dlaždice aplikace a určit pořadí **rozložení nabídky Start** v mřížce aplikace. Pokud chcete provádět vlastní úpravy většího rozsahu, pokračujte k odeslání souboru XML.
- Nastavení aplikace Kiosk Browser se přesouvají do nastavení **Veřejný terminál**. V současnosti má nastavení **Kiosk Web Browser** na webu Azure Portal vlastní kategorii.
Platí pro: Windows 10 a novější




### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Použití profilu Autopilotu u zaregistrovaných zařízení s Windows 10, která nejsou zaregistrovaná v Autopilotu <!-- 1558983 -->
Profily Autopilotu můžete použít u zaregistrovaných zařízení s Windows 10, která nejsou zaregistrovaná do Autopilotu. V profilu Autopilotu zvolte možnost **Převést všechna cílová zařízení na AutoPilot**, abyste mohli k automatické registraci zařízení bez Autopilotu použít službu nasazení Autopilotu. Vyřízení registrace trvá 48 hodin. Jakmile bude registrace zařízení zrušena a zařízení bude resetováno, Autopilot zajistí registraci.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Vytvoření více profilů stránky o stavu registrace a jejich přiřazení skupinám Azure AD <!-- 2526564 -->
Nově můžete [vytvořit a přiřadit](windows-enrollment-status.md) více profilů stránky o stavu registrace skupinám Azure ADD.

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>Migrace z Programu registrace zařízení na Apple Business Manager v Intune <!--2748613-->
V Intune funguje Apple Business Manager (ABM), takže je možné upgradovat účet z Programu registrace zařízení (DEP) na ABM. Proces v Intune je stejný. Pokud chcete účet Apple upgradovat z DEP na ABM, přejděte na [ https://support.apple.com/en-us/HT208817]( https://support.apple.com/en-us/HT208817).

### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Karty pro upozornění a stav registrace na stránce s přehledem registrace zařízení <!--2748656-->
Na stránce s přehledem registrace zařízení se teď zobrazují upozornění a chyby registrace na samostatných kartách.

### <a name="device-management"></a>Správa zařízení

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Omezení aplikací a blokování přístupu k prostředkům společnosti na zařízení s Androidem <!-- 2451462  -->  
V části **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu** > **Android** > **Zabezpečení systému** v oddílu *Zabezpečení zařízení* existuje nové nastavení s názvem **Omezené aplikace**. Nastavení **Omezené aplikace** pomocí zásad dodržování předpisů blokuje přístup k firemním prostředkům, pokud jsou v zařízení nainstalované některé aplikace. Zařízení se považuje za neodpovídající předpisům, dokud se z něj aplikace s omezeným přístupem neodeberou.
Platí pro: 
- Android




## <a name="week-of-september-24-2018"></a>Týden od 24. září 2018

### <a name="microsoft-365-device-management-administration-center----3078424---"></a>Centrum pro správu Microsoft 365 Device Management <!-- 3078424 -->
Jedním z příslibů Microsoft 365 je zjednodušená správa a v průběhu let jsme integrovali back-endové služby Microsoft 365 tak, aby poskytovaly ucelený komplet, jako je podmíněný přístup Intune a Azure AD. Nové [centrum pro správu Microsoft 365](http://devicemanagement.microsoft.com) je místem, kde můžete konsolidovat, zjednodušovat a integrovat prostředí pro správu. Pracovní prostor pro specialisty na správu zařízení poskytuje snadný přístup ke všem úkolům a informacím o správě zařízení a aplikací a úloh, které vaše organizace potřebuje. Očekáváme, že se stane primárním pracovním prostorem na cloudu pro výpočetní týmy koncových uživatelů organizací.

### <a name="support-for-more-third-party-certification-authorities-ca----3093107---"></a>Podpora více externích certifikačních autorit <!-- 3093107 -->
Když použijete protokol SCEP (Simple Certificate Enrollment Protocol), můžete teď vydat nové certifikáty a prodloužit platnost certifikátů na mobilních zařízeních s Windows, iOS, Androidem a macOS.

### <a name="intune-moves-to-support-ios-10-and-later----2454656---"></a>Intune přechází k podpoře iOSu 10 a novějších verzí <!-- 2454656 -->  
Registrace Intune, Portál společnosti a spravovaný prohlížeč nyní podporují pouze zařízení s iOSem verze 10 a novějších. Pokud chcete zjistit, na která zařízení nebo uživatele ve vaší organizaci to bude mít vliv, přejděte do Intune na webu Azure Portal > **Zařízení** > **Všechna zařízení**. Podrobnosti o verzi operačního systému zobrazíte tak, že si vyfiltrujete operační systém a potom kliknete na **Sloupce**. Požádejte tyto uživatele, aby si upgradovali zařízení na podporovanou verzi operačního systému.  

Pokud máte některé z níže uvedených zařízení nebo chcete některé z těchto zařízení zaregistrovat, mějte na paměti, že tato zařízení podporují jenom iOS 9 a dřívější verze.  Pokud chcete dále používat Portál společnosti Intune, je nutné tato zařízení upgradovat na zařízení podporující iOS 10 nebo novější verze:  

* iPhone 4S 
* ipodu Touch  
* iPad 2 
* iPad (3. generace) 
* iPad Mini (1. generace)  

## <a name="week-of-september-17-2018"></a>Týden od 17. září 2018

### <a name="app-management"></a>Správa aplikací

### <a name="remove-duplication-of-app-protection-status-tiles----3083391---"></a>Odebrání duplicity dlaždic se stavem ochrany aplikací <!-- 3083391 -->
Dlaždice **Stav uživatele pro iOS** a **Stav uživatele pro Android** se vyskytovaly na stránce **Klientské aplikace – přehled** i na stránce **Klientské aplikace – stav ochrany aplikace**. Dlaždice stavu byly odebrány ze stánky **Klientské aplikace – přehled**, aby se zabránilo duplicitě. 

## <a name="week-of-august-27-2018"></a>Týden od 27. srpna 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Podpora tunelu pro pakety u profilů VPN pro jednotlivé aplikace iOS u vlastních typů připojení a připojení Pulse Secure <!-- 1520957 -->
Pokud používáte profily VPN pro jednotlivé aplikace pro iOS, můžete použít tunelování v aplikační vrstvě (proxy aplikace) nebo na úrovni paketů (tunel pro pakety). Tyto možnosti jsou dostupné u následujících typů připojení:
- Vlastní VPN
- Pulse Secure Pokud si nejste jisti, jakou hodnotu použít, vyhledejte informace v dokumentaci poskytovatele připojení VPN.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Zpoždění při zobrazení aktualizací softwaru iOS na zařízení <!-- 1949583 -->
V části Intune > **Aktualizace softwaru** > **Aktualizovat zásady pro iOS** můžete nakonfigurovat dny a časy, kdy se na zařízení nemají instalovat žádné aktualizace. V budoucí aktualizaci budete moct odložit čas, kdy se aktualizace softwaru viditelně zobrazí v zařízení, o 1–90 dní. 
Aktuální nastavení jsou uvedena v části [Konfigurace zásad aktualizace iOS v Microsoft Intune](software-updates-ios.md).

#### <a name="office-365-proplus-version----2213968---"></a>Verze Office 365 ProPlus <!-- 2213968 -->
Při přiřazování aplikací Office 365 ProPlus k zařízením s Windows 10 pomocí Intune si můžete vybrat verzi Office. Na portálu Azure Portal vyberte **Microsoft Intune** > **Aplikace** > **Přidat aplikaci**. Potom z rozevíracího seznamu **Typ** vyberte **Office 365 ProPlus Suite (Windows 10)**. Volbou **Nastavení sady aplikací** otevřete související okno. V části **Aktualizační kanál** nastavte požadovanou hodnotu, například **Měsíčně**. Volitelně můžete odebrat ze zařízení koncových uživatelů jiné verze Office (msi) tak, že vyberete **Ano**. Vyberte **Konkrétní** a nainstalujte tak pro vybraný kanál na zařízeních koncových uživatelů konkrétní verzi Office. V tomto okamžiku můžete vybrat **konkrétní verzi** Office, která se má použít. Dostupné verze se budou v průběhu času měnit. Při vytváření nového nasazení tedy můžou být dostupné novější verze a některé starší verze nemusí být k dispozici. Aktuální nasazení budou dál nasazovat starší verzi, ale seznam verzí se bude průběžně aktualizovat podle kanálu. Další informace najdete v článku [Základní informace o aktualizačních kanálech Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Podpora nastavení Registrovat pomocí DNS pro VPN ve Windows 10 <!-- 2282852 -->
Od této aktualizace můžete profily sítě VPN ve Windows 10 nakonfigurovat tak, aby dynamicky registrovaly IP adresy přiřazené k rozhraní sítě VPN pomocí interní služby DNS bez nutnosti používat vlastní profily.
Informace o aktuálně dostupných nastaveních profilů VPN najdete v seznamu [Nastavení sítě VPN ve Windows 10](vpn-settings-windows-10.md). 

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name---2652728--"></a>Instalační program Portálu společnosti pro macOS nově obsahuje číslo verze v názvu svého souboru <!--2652728-->

#### <a name="ios-automatic-app-updates----2729759-wnready---"></a>Automatické aktualizace aplikací pro iOS <!-- 2729759 wnready -->
Automatické aktualizace aplikací fungují u aplikací licencovaných pro zařízení i uživatele v iOSu verze 11.0 a novějších.




### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Windows Hello bude cílit na uživatele a zařízení <!-- 1106609 -->
Když vytvoříte zásady [Windows Hello pro firmy](windows-hello.md), bude platit pro všechny uživatele v organizaci (v celém tenantovi). Po této aktualizaci se tyto zásady s využitím zásad konfigurace zařízení budou dát použít také pro konkrétní uživatele nebo konkrétní zařízení (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Identity Protection** > **Windows Hello pro firmy**).
V Intune na portálu Azure Portal je konfigurace a nastavení Windows Hello nově k dispozici v částech **Registrace zařízení** i **Konfigurace zařízení**. **Registrace zařízení** cílí na celou organizaci (celého tenanta) a podporuje program Windows AutoPilot (OOBE). **Konfigurace zařízení** cílí na zařízení a uživatele používající zásadu aplikovanou při přihlášení.
Tato funkce platí pro:  
- Windows 10 a novější
- Windows Holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858---"></a>Pro profily sítě VPN v iOS je dostupné připojení Zscaler <!-- 1769858 -->
Při vytváření konfiguračního profilu VPN pro zařízení s iOSem (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **iOS** platforma > typ profilu **VPN**) existuje několik typů připojení, mimo jiné Cisco, Citrix a další. S touto aktualizací se mezi typy připojení přidává Zscaler. 
Dostupné typy připojení jsou uvedeny v části [Nastavení sítě VPN pro zařízení s iOSem](vpn-settings-ios.md).

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10----1879077---"></a>Režim FIPS pro podnikové profily Wi-Fi pro Windows 10 <!-- 1879077 -->
Nově můžete pro podnikové profily Wi-Fi pro Windows 10 povolit na portálu Intune Azure režim FIPS (Federal Information Processing Standards). Pokud režim FIPS na vašich profilech Wi-Fi povolíte, ujistěte se, že je povolený v infrastruktuře sítě Wi-Fi.
Postup vytvoření profilu Wi-Fi najdete v článku [Nastavení Wi-Fi pro zařízení s Windows 10 a novější verzí v Intune](wi-fi-settings-windows.md).

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Řízení režimu S v zařízeních se systémem Windows 10 a novějších – verze Public Preview <!-- 1958649 -->
Od této aktualizace funkcí můžete vytvářet profil konfigurace zařízení, který přepne zařízení s Windows 10 z režimu S nebo uživatelům v přepnutí zařízení z režimu S zabrání. Funkci najdete v části Intune > **Konfigurace zařízení** > **Profily** >  **Windows 10 a novější** > **Upgrade edice a přepnutí režimu**.
Článek [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode) (Představení Windows 10 v režimu S) poskytuje o režimu S podrobnější informace.
Platí pro: nejnovější build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (v období verze Preview).


#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Automatické přidání konfiguračního balíčku Ochrany ATP v programu Windows Defender do konfiguračního profilu <!-- 2144658 -->
Když používáte [Rozšířenou ochranu před internetovými útoky (ATP) a připojujete](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) zařízení k Intune, museli jste si dříve stáhnout konfigurační balíček a přidat ho do konfiguračního profilu. Od této aktualizace Intune automaticky načítá balíček z Centra zabezpečení v programu Windows Defender a přidává ho do profilu za vás.
Platí pro Windows 10 a novější.

#### <a name="require-users-to-connect-during-device-setup---2311457--"></a>Povinnost připojit se během nastavení zařízení <!--2311457-->
Nyní můžete nastavit profily zařízení tak, aby se během instalace Windows 10 muselo zařízení ještě před opuštěním stránky Síť připojit k síti. Funkce je sice ve verzi Preview, ale ve Windows Insider sestavení 1809 nebo novějších je toto nastavení povinné.
Platí pro: nejnovější build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (v období verze Preview).


#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices----2451462---"></a>Omezení přístupu k aplikacím a blokování přístupu k firemním prostředkům v zařízeních s iOSem a Androidem Enterprise <!-- 2451462 -->
V části **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu** > **iOS** > **Zabezpečení systému** je k dispozici nové nastavení **Aplikace s omezeným přístupem**. Toto nové nastavení pomocí zásad dodržování předpisů blokuje přístup k firemním prostředkům, pokud jsou v zařízení nainstalované některé aplikace. Zařízení se považuje za neodpovídající předpisům, dokud se z něj aplikace s omezeným přístupem neodeberou.
Platí pro: iOS

#### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Aktualizace podpory moderních sítí VPN pro iOS <!-- 2459928, 1819876, and 2650856 -->
S touto aktualizací se přidává podpora následujících klientů VPN pro iOS: 
- F5 Access (verze 3.0.1 a vyšší)
- Citrix SSO
- Palo Alto Networks GlobalProtect verze 5.0 a vyšší – další změny v aktualizaci:
- Stávající připojení typu **F5 Access** se v iOSu přejmenovalo na **Starší verze F5 Access**.
- Stávající připojení typu **Palo Alto Networks GlobalProtect** se v iOSu přejmenovalo na **Palo Alto Networks GlobalProtect (starší verze)**.
Stávající profily s těmito typy připojení budou i nadále fungovat s příslušnou starší verzí klienta VPN. Pokud v iOSu používáte klienty Cisco Legacy AnyConnect, Starší verze F5 Access, Citrix VPN nebo Palo Alto Networks GlobalProtect verze 4.1 a starší, doporučujeme přejít na nové aplikace. Proveďte to co nejdříve, abyste zařízením s iOSem zajistili přístup k síti VPN i po aktualizaci na verzi iOS 12.
Podrobnosti o iOSu 12 a profilech VPN najdete na [blogu technické podpory Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2013806).

#### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal----2469637---"></a>Export zásad dodržování předpisů z portálu Azure Classic pro jejich opětovné vytvoření na portálu Intune Azure <!-- 2469637 -->
Zásady dodržování předpisů vytvořené na portálu Azure Classic se přestanou používat. Existující zásady si můžete prohlédnout a odstranit je, nelze je ale aktualizovat. Pokud potřebujete jakékoli zásady dodržování předpisů z aktuálního portálu Intune Azure migrovat, můžete je vyexportovat do souboru hodnot oddělených čárkami (*.csv*). Podrobnosti ze souboru potom můžete využít k opětovnému vytvoření těchto zásad v Intune na portálu Azure Portal.

> [!IMPORTANT]
> Po vyřazení portálu Azure Classic už k zásadám nebudete mít přístup, ani si je nebudete moci prohlížet. Proto zásady nezapomeňte exportovat a znovu vytvořit na webu Azure Portal dříve, než bude provoz portálu Azure Classic ukončen.

#### <a name="better-mobile---new-mobile-threat-defense-partner----22662717---"></a>Better Mobile – nový partner ochrany před mobilními hrozbami <!-- 22662717 -->
Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Better Mobile. Je to řešení ochrany před mobilními hrozbami, které se integruje s Microsoft Intune.

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Uzamčení aplikace Portál společnosti v režimu jedné aplikace do přihlášení uživatele <!--1067692 --> 
Pokud během registrace DEP neověřujete uživatele pomocí Průvodce nastavením, ale prostřednictvím aplikace Portál společnosti, máte nyní možnost aplikaci Portál společnosti spustit v režimu Jedna aplikace. Tato možnost ihned po dokončení chodu Průvodce nastavením uzamkne zařízení a uživatel k němu získá přístup až po přihlášení. Tak je zajištěno, že se u zařízení dokončí fáze zavádění a nezůstane osamocené ve stavu, kdy není svázáno s žádným uživatelem.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Přiřazení uživatele a jednoduchého názvu zařízení Autopilot <!--1346521 -->
Nově můžete [přiřadit uživatele k jedinému zařízení Autopilot](enrollment-autopilot.md). Správci budou také moct dávat zařízením v programu AutoPilot popisné názvy, které uživatele při nastavování přivítají.
Platí pro: nejnovější build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (v období verze Preview).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>Použití licencí zařízení z programu VPP k předběžnému zřízení portálu společnosti během registrace do programu DEP <!-- 1608345 -->
Licence zařízení z programu VPP (Volume Purchase Program) můžete teď použít k předběžnému zřízení Portálu společnosti během registrace do programu DEP (Device Enrollment Program neboli Program registrace zařízení). Pokud to chcete udělat, zadejte při [vytváření nebo úpravě profilu registrace](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) token VPP, který chcete použít k instalaci aplikace Portál společnosti. Dbejte na to, aby tokenu nevypršela platnost a abyste měli dost licencí pro aplikaci Portál společnosti. V případech, kdy platnost tokenu vyprší nebo dojdou licence, nabídne Intune instalaci aplikace Portál společnost z App Storu (při které se zobrazí výzva k zadání Apple ID).

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Vyžadování potvrzení odstranění tokenu VPP používaného k předběžnému zřízení portálu společnosti <!-- 2237634 -->
Vyžaduje se potvrzení odstranění tokenu VPP (Volume Purchase Program), pokud se používá k předběžnému zřízení portálu společnosti během registrace do programu DEP.

#### <a name="block-windows-personal-device-enrollments----1849498---"></a>Blokování registrace osobních zařízení s Windows <!-- 1849498 -->
V Intune můžete [blokovat registraci osobních zařízení s Windows](enrollment-restrictions-set.md#set-device-type-restrictions) do [ správy mobilních zařízení](windows-enroll.md). Pomocí této funkce se nedají blokovat zařízení zaregistrovaná prostřednictvím [agenta Intune pro počítače](manage-windows-pcs-with-microsoft-intune.md). Tato funkce se bude vydávat v příštích několika týdnech, takže ji v uživatelském rozhraní nemusíte vidět hned.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Zadání vzoru pro názvy počítačů v profilu Autopilot <!--1849855-->
Můžete [zadat šablonu pro názvy počítačů](enrollment-autopilot.md#create-an-autopilot-deployment-profile), která se použije ke generování a nastavení [názvu počítače](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) při registraci do programu AutoPilot. Platí pro: nejnovější build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (v období verze Preview).


#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>Skrytí volby změny účtu v profilech Windows Autopilot na přihlašovací stránce společnosti a na chybové stránce domény <!--1901669 -->
Nyní jsou k dispozici [nové možnosti profilu Windows AutoPilot](enrollment-autopilot.md#create-an-autopilot-deployment-profile), které správcům umožňují na přihlašovací stránce společnosti a na chybové stránce domény skrýt volbu změny účtu. Předpokladem skrytí těchto možností je, aby v Azure Active Directory byla nakonfigurována funkce Branding společnosti. Platí pro: nejnovější build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (v období verze Preview).



### <a name="device-management"></a>Správa zařízení

#### <a name="delete-jamf-devices----2653306--"></a>Odstranění zařízení Jamf <!-- 2653306-->
Zařízení spravovaná prostřednictvím JAMF můžete odstranit tak, že přejdete na **Zařízení** > zvolíte zařízení Jamf > **Odstranit**.

#### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Změna terminologie na „vyřazení“ a „vymazání“ <!-- 2175759 -->
V uživatelském rozhraní Intune a v dokumentaci k Intune jsme změnili kvůli sjednocení s Graph API následující výrazy:
- **Odebrání firemních dat** se mění na „vyřazení“.
- **Obnovení továrního nastavení** se mění na **vymazání**.

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate----297909500--"></a>Dialogové okno potvrzení zobrazené správci při pokusu o odstranění certifikátu MDM Push Certificate <!-- 297909500-->
Pokud se jakýkoliv uživatel pokusí odstranit certifikát Apple MDM Push Certificate, zobrazí se v dialogovém okně potvrzení počet souvisejících zařízení s iOSem a macOS. Dojde-li k odstranění certifikátu, musí se tato zařízení znovu zaregistrovat.

### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Nastavení dalšího zabezpečení pro Instalační službu systému Windows <!-- 2282430 -->
Můžete uživatelům umožnit ovládání instalace aplikací. Pokud je tato možnost povolená, instalace, které by se jinak kvůli narušení zabezpečení zastavily, budou moct pokračovat. Můžete Instalační službu systému Windows nastavit tak, aby při instalaci libovolné aplikace do systému používala zvýšenou úroveň oprávnění. Dále můžete povolit, aby se položky WIP (Windows Information Protection) indexovaly a aby se metadata o nich ukládala do nešifrovaného umístění. Pokud je tato zásada zakázaná, chráněné položky WIP se neindexují a ve výsledcích v Cortaně nebo v Průzkumníkovi souborů se nezobrazují. Funkčnost těchto možností je ve výchozím nastavení zakázaná. 

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nová aktualizace uživatelského prostředí pro web Portál společnosti <!--2000968 -->
Na základě názorů zákazníků jsme přidali na web Portál společnosti nové funkce. Na svých zařízeních si všimnete značného vylepšení stávající funkčnosti a použitelnosti. Oblasti webu – jako třeba podrobnosti o zařízení, váš názor a podpora a přehled zařízení – získaly nový, moderní a živý vzhled. Další vylepšení:

- Zjednodušené pracovní postupy na všech platformách zařízení
- Vylepšené průběhy identifikace a registrace zařízení
- Další užitečné chybové zprávy
- Příjemnější jazyk, méně technického žargonu
- Možnost sdílet přímé odkazy na aplikace
- Vylepšený výkon u velkých katalogů aplikací
- Lepší přístupnost pro všechny uživatele  

Aktualizovali jsme [dokumentaci na Portálu společnosti Intune](https://docs.microsoft.com/intune-user-help/using-the-intune-company-portal-website), aby reflektovala tyto změny. Pokud si chcete prohlédnout ukázku vylepšených aplikací, přejděte na článek [Aktualizace uživatelského rozhraní pro aplikace Intune pro koncové uživatele](whats-new-app-ui.md).  

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Vylepšená detekce jailbreaků při generování sestav dodržování předpisů <!-- 2198738 -->
Vylepšené stavy nastavení detekce jailbreaků se nově zobrazují při veškerém generování sestav dodržování předpisů v konzole správce.

### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="scope-tags-for-policies---1081974---"></a>Značky oboru pro zásady <!--1081974 -->
Nově můžete [vytvářet značky oboru](scope-tags.md) a omezovat s jejich pomocí přístup k prostředkům Intune. Přidejte značku oboru k přiřazení role a poté přidejte značku oboru ke konfiguračnímu profilu. Daná role bude mít přístup pouze k prostředkům s konfiguračními profily, které mají odpovídající značky oboru (nebo žádnou značku oboru).

## <a name="week-of-august-14-2018"></a>Týden od 14. srpna 2018

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>Podpora Programu registrace zařízení (DEP) společnosti Apple pro zařízení s macOSem<!-- 747651 -->
Intune teď podporuje registraci zařízení s macOS do Programu registrace zařízení (DEP) společnosti Apple. Další informace najdete v článku [Automatická registrace zařízení s macOS do Programu registrace zařízení Apple](device-enrollment-program-enroll-macos.md).

## <a name="week-of-july-23-2018"></a>Týden od 23. července 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>Podpora obchodních aplikací (LOB) pro macOS <!-- 1895847 -->
Microsoft Intune umožňuje nasazovat obchodní aplikace pro macOS jako **povinné** nebo **k dispozici s registrací**. Koncoví uživatelé můžou aplikace nasazovat jako **povinné** prostřednictvím Portálu společnosti pro macOS nebo [webu Portál společnosti](https://portal.manage.microsoft.com).

#### <a name="ios-built-in-app-support-for-kiosk-mode----2051098---"></a>Podpora integrovaných iOS aplikací v celoobrazovkovém režimu <!-- 2051098 -->
Kromě aplikací ze Storu a spravovaných aplikací můžete nyní vybrat i integrovanou aplikaci (jako je Safari), která poběží na zařízení s iOSem v celoobrazovkovém režimu.

#### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Úpravy nasazení aplikací Office 365 Pro Plus <!-- 2150145 -->
Jako správce Microsoft Intune máte širší možnosti úpravy nasazování aplikací Office 365 Pro Plus. Kromě toho už kvůli změně vlastností sady nemusíte odstraňovat svá nasazení. Na portálu Azure Portal vyberte **Microsoft Intune** > **Klientské aplikace** > **Aplikace**. V seznamu aplikací vyberte vaši sadu Office 365 Pro Plus.  


#### <a name="updated-intune-app-sdk-for-android-is-now-available----2744271--"></a>K dispozici je aktualizovaná sada Intune App SDK pro Android <!-- 2744271-->

K dispozici je aktualizovaná verze sady Intune App SDK pro Android, která podporuje vydanou verzi Android P. Pokud jste vývojáři aplikací a používáte sadu Intune SDK pro Android, musíte si nainstalovat aktualizovanou verzi sady Intune App SDK. Tím zajistíte, že funkce Intune budou v aplikacích pro Android fungovat očekávaným způsobem, a to i na zařízeních s Androidem P. Tato verze sady Intune App SDK nabízí integrovaný plug-in, který aktualizuje sadu SDK, abyste nemuseli přepisovat stávající integrovaný kód. Podrobné informace najdete v tématu o [sadě Intune SDK pro Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). Pokud používáte staré označení Intune, doporučujeme použít ikonu aktovky. Podrobné informace najdete v [tomto úložišti GitHub](https://github.com/msintuneappsdk/intune-app-partner-badge).


### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="use-smime-to-encrypt-and-sign-a-users-multiple-devices-----1333642---"></a>Použití S/MIME k šifrování a podepsání více zařízení uživatele <!-- 1333642 -->
Tato aktualizace zahrnuje šifrování S/MIME e-mailů pomocí nového profilu importovaného certifikátu (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > vyberte platformu > typ profilu **Importovaný certifikát PKCS**). V Intune můžete importovat certifikáty ve formátu PFX. Intune pak může doručit stejné certifikáty do více zařízení zaregistrovaných jedním uživatelem. To také zahrnuje:

- Nativní e-mailový profil v iOS podporuje povolení šifrování S/MIME pomocí importovaných certifikátů ve formátu PFX.
- Nativní poštovní aplikace na zařízeních se systémem Windows Phone 10 automaticky použije certifikát S/MIME.
- Privátní certifikáty je možné doručit na různé platformy. Některé e-mailové aplikace ale S/MIME nepodporují.
- Na jiných platformách může být nutné ručně nakonfigurovat e-mailovou aplikaci a povolit S/MIME.  
- E-mailové aplikace, které podporují šifrování S/MIME, můžou zpracovávat načítání certifikátů pro šifrování S/MIME e-mailů způsobem, který MDM nepodporuje (například ho načítají z úložiště certifikátů svého vydavatele).

Podporováno v systémech: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Vytváření zásad dodržování předpisů pro zařízení pomocí nastavení Firewall na zařízeních s macOSem <!-- 1497640 -->
Při vytváření nových zásad dodržování předpisů systému macOS (**Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu** > **Platforma: macOS** > **Zabezpečení systému**) jsou dostupná některá nová nastavení pro **bránu firewall**: 

- **Firewall:** Umožňuje konfigurovat způsob zpracování příchozích připojení ve vašem prostředí.
- **Příchozí připojení:** **Blokuje** všechna příchozí připojení s výjimkou připojení potřebných pro základní internetové služby, jako je DHCP, Bonjour a IPSec. Toto nastavení blokuje také všechny služby sdílení.
- **Neviditelný režim:** **Aktivací** neviditelného režimu zakážete zařízení odpovídat na zjišťovací požadavky. Oprávněným aplikacím bude zařízení dále odpovídat na příchozí žádosti.

Platí pro: macOS 10.12 a novější

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Nový konfigurační profil Wi-Fi zařízení pro Windows 10 a novější <!-- 1879077 -->
V současné době můžete importovat a exportovat profily Wi-Fi pomocí souborů XML. S touto aktualizací můžete vytvořit konfigurační profil Wi-Fi zařízení přímo v Intune, podobně jako na některých jiných platformách.

Pokud chcete vytvořit profil, otevřete položku **Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** > **Wi-Fi**. 

Platí pro Windows 10 a novější.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>Položka Veřejný terminál (zastaralé) se zobrazí šedě a nebude umožňovat změny <!-- 2149998 -->
[Funkce Veřejný terminál](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** > **Omezení zařízení**) je nyní zastaralá a nahrazuje ji [nastavení veřejného terminálu pro Windows 10 a novější](kiosk-settings.md). Položka **Veřejný terminál (zastaralé)** se v této aktualizaci zobrazuje šedě a uživatelské rozhraní neumožňuje změny ani aktualizace. 

Pokud budete chtít povolit režim veřejného terminálu, podívejte se na článek[Nastavení veřejného terminálu pro Windows 10 a novější](kiosk-settings.md).

Platí pro: Windows 10 a novější, Windows Holographic for Business.

#### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>Rozhraní API budou používat nezávislé certifikační autority <!-- 2184013 -->
V této aktualizaci je k dispozici rozhraní API založené na Javě, které umožňuje integraci nezávislých certifikačních autorit s Intune a protokolem SCEP. Uživatelé pak budou moct přidat certifikát SCEP do profilu a použít ho pro zařízení využívající MDM.

V současné době Intune podporuje [žádosti protokolu SCEP používající Active Directory Certificate Services](certificates-scep-configure.md).

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>Přepínač pro zobrazení nebo nezobrazení tlačítka pro ukončení relace v prohlížeči Kiosk <!-- 2455253 -->
Nyní můžete nakonfigurovat, jestli se má v prohlížečích Kiosk zobrazovat tlačítko pro ukončení relace. Tento ovládací prvek najdete v části **Konfigurace zařízení** > **Beznabídkový režim (Preview)** > **Kiosk Web Browser**. Pokud toto tlačítko zapnete a uživatel na něj klikne, zobrazí aplikace výzvu k potvrzení ukončení relace. Po potvrzení prohlížeč vymaže všechny údaje o procházení a přejde zpátky na výchozí adresu URL.

#### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>Vytvoření mobilního konfiguračního profilu eSIM <!-- 2564077 -->
V části **Konfigurace zařízení** můžete vytvořit mobilní profil eSIM. Můžete naimportovat soubor, který obsahuje mobilní aktivační kódy poskytnuté vaším mobilním operátorem. Pak můžete tyto profily nasadit do zařízení s Windows 10 podporujících eSIM LTE, jako je například Surface Pro LTE a další zařízení podporující eSIM.

Zkontrolujte, jestli vaše [zařízení podporuje profily eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Platí pro Windows 10 a novější. 




### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Automatické označení zařízení s Androidem registrovaných pomocí technologie Samsung Knox Mobile Enrollment jako firemních <!-- 2404851 -->
Ve výchozím nastavení se zařízení s Androidem registrovaná pomocí technologie Samsung Knox Mobile Enrollment označují v poli **Vlastnictví zařízení** jako **Firemní**. Před registrací pomocí technologie Knox Mobile Enrollment nemusíte firemní zařízení identifikovat ručně pomocí IMEI nebo sériových čísel.

### <a name="device-management"></a>Správa zařízení

#### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Hromadné odstranění zařízení v okně Zařízení <!-- 1793693 -->

V okně Zařízení můžete odstranit více zařízení najednou. Zvolte **Zařízení** > **Všechna zařízení** > vyberte zařízení, která chcete odstranit > **Odstranit**. U zařízení, která nejde odstranit, se zobrazí upozornění.

## <a name="week-of-july-16-2018"></a>Týden od 16. července 2018  

### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Další možnosti synchronizace v aplikaci Portál společnosti pro Windows  
Aplikace Portál společnosti pro Windows teď umožňuje zahájit synchronizaci přímo z hlavního panelu Windows a z nabídky Start. Tato funkce je užitečná hlavně v případě, že vaším jediným úkolem je synchronizace zařízení a získání přístupu k podnikovým prostředkům. Pokud chcete tuto novou funkci použít, klikněte pravým tlačítkem na ikonu Portál společnosti, která je připnutá na hlavní panel nebo v nabídce Start. V možnostech nabídky (označuje se také jako seznam odkazů) vyberte **Synchronizovat toto zařízení**. V aplikaci Portál společnosti se otevře stránka **Nastavení** a zahájí se synchronizace. Nové funkce najdete v tématu [Aktualizace uživatelského rozhraní pro aplikace Intune pro koncové uživatele](whats-new-app-ui.md).   

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Nové možnosti procházení v aplikaci Portál společnosti pro Windows  

Při procházení nebo hledání aplikací v aplikaci Portál společnosti pro Windows teď můžete přepínat mezi stávajícím zobrazením **dlaždic** a nově přidaným zobrazením **podrobností**. Toto nové zobrazení obsahuje podrobnosti aplikace, například název, vydavatele, datum publikování a stav instalace.  

Na stránce **Aplikace** si v zobrazení **Nainstalované** můžete prohlédnout podrobnosti o dokončených a probíhajících instalacích aplikací. Vzhled nového zobrazení najdete v tématu [Aktualizace uživatelského rozhraní pro aplikace Intune pro koncové uživatele](whats-new-app-ui.md).  
### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Vylepšené prostředí aplikace Portál společnosti pro správce registrace zařízení  
Když se správce registrace zařízení přihlásí k aplikaci Portál společnosti pro Windows, bude se od teď v této aplikaci uvádět jen jeho aktuální spuštěné zařízení. Tímto vylepšením se omezí vypršení časového limitu, ke kterým dříve docházelo, když se aplikace snažila zobrazit všechna zařízení zaregistrovaná správcem.  


## <a name="week-of-july-9-2018"></a>Týden od 9. července 2018

### <a name="app-management"></a>Správa aplikací

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Blokování přístupu k aplikacím na základě neschválených dodavatelů zařízení a modelů <!-- 1425689 ! -->
Správce IT v Intune může vynutit konkrétní seznam výrobců zařízení s Androidem a/nebo modelů s iOSem prostřednictvím zásad Intune App Protection. Správce IT může poskytnout středníky oddělený seznam výrobců pro zásady Androidu a modelů zařízení pro zásady iOS. Zásady Intune App Protection jsou pouze pro Android a iOS. V tomto konkrétním seznamu můžete provést dvě samostatné akce:
- Budete moct blokovat přístup k aplikacím na zařízeních, která nejsou specifikována.
- Nebo selektivně vymazat podniková data na zařízeních, která nejsou specifikována. 

Uživatel nebude moct přistupovat k cílové aplikaci, pokud nebudou splněny požadavky prostřednictvím zásad. Na základě nastavení může být uživatel zablokován nebo mu mohou být v aplikaci vymazána podniková data. Na zařízeních s iOSem tato funkce vyžaduje zapojení aplikací (jako jsou WXP, Outlook, Managed Browser, Yammer), aby integrovaly sadu Intune App SDK. V opačném případě nebude možné vynutit tuto funkci v cílových aplikacích. K této integraci dochází průběžně a závisí na týmech konkrétních aplikací. Na Androidu tato funkce vyžaduje nejnovější verzi Portálu společnosti. 

Na zařízeních koncových uživatelů klient Intune provede akci založenou na jednoduché shodě řetězců zadaných v okně Intune pro zásady ochrany aplikací. Závisí to zcela na hodnotě, kterou zařízení vykazuje. Doporučujeme správci IT, aby zajistil přesnost zamýšleného chování. Toho se dá dosáhnout testováním tohoto nastavení na základě různých výrobců a modelů zacílených na malé skupiny uživatelů. Pokud si chcete zobrazit a přidat zásady ochrany aplikací, vyberte v Microsoft Intune **Klientské aplikace** > **Zásady ochrany aplikací**. Další informace o zásadách ochrany aplikací najdete v článku [Co jsou zásady ochrany aplikací](app-protection-policy.md) a [Selektivní vymazání dat pomocí akcí přístupu zásad ochrany aplikací v Intune](app-protection-policies-access-actions.md).

### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>Přístup k předběžnému buildu Portálu společnosti v systému macOS <!-- 1734766 -->
Pomocí aplikace Microsoft AutoUpdate se můžete zapojit do programu Insider a získávat tak buildy dříve. Registrace vám umožní používat aktualizovaný Portál společnosti předtím, než bude k dispozici koncovým uživatelům. Další informace najdete na [blogu Microsoft Intune](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/).

## <a name="week-of-july-2-2018"></a>Týden od 2. července 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="monitor-ios--app-configuration-status-per-device----880037---"></a>Monitorování stavu konfigurace aplikací pro iOS podle zařízení <!-- 880037 -->
Jako správce Microsoft Intune můžete monitorovat stav konfigurace aplikací pro iOS pro každé spravované zařízení. V části **Microsoft Intune** na portálu Azure Portal vyberte **Zařízení** > **Všechna zařízení**. V seznamu spravovaných zařízení vyberte konkrétní zařízení a zobrazte tak okno pro toto zařízení. V okně zařízení vyberte **Konfigurace aplikace**.

#### <a name="access-actions-for-app-protection-policies----1483510---"></a>Akce přístupu pro zásady ochrany aplikací <!-- 1483510 -->
Můžete nakonfigurovat zásady ochrany aplikací tak, aby mohly explicitně vymazat, blokovat nebo upozornit zařízení, která zásady nedodržují. Akce *vymazání* odebere ze zařízení podniková data vaší společnosti. Pokud dojde k vymazání, je uživatel zařízení informován o důvodu vymazání a o postupu nápravy. U některých nastavení, jako je například minimální verze operačního systému, bude možné použít více akcí, třeba blokování a vymazání. Upozorňujeme, že tyto akce se aktivují při spuštění aplikace.

#### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Selektivní vymazání dat aplikací organizace <!-- 1507030 -->
Správci můžou nakonfigurovat selektivní vymazání dat organizace jako novou akci pro případ, že nebudou splněné podmínky nastavení Zásad ochrany aplikací (APP).  Tato funkce umožní správcům automaticky chránit a odebírat citlivá data organizace z aplikací na základě předem nakonfigurovaných kritérií.

#### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>Odvolání aplikace pro iOS zakoupené přes VPP <!-- 1777384 -->
Jako správce Microsoft Intune můžete odvolat všechny licence pro vybrané aplikace pro iOS zakoupené přes Volume Purchase Program (VPP). Uživatele můžete upozornit, že už aplikaci pro licencovaného uživatele nemají přiřazenou. Odvoláním licence aplikace se příslušná aplikace VPP neodinstaluje ze zařízení. Pokud chcete odinstalovat aplikaci VPP, musíte nastavit akci přiřazení na **Odinstalovat**. Počet uvolněných licencí se v Intune projeví v uzlu **Licencované aplikace** v úloze **Aplikace**. Další informace týkající se aplikací VPP pro iOS najdete v tématu [o správě aplikací pro iOS zakoupených přes Volume Purchase Program v Microsoft Intune](vpp-apps-ios.md).

#### <a name="updates-to-out-of-compliance-messages-in-company-portal-app----1832222---"></a>Aktualizace zpráv o nedodržování předpisů v aplikaci Portál společnosti <!-- 1832222 -->
Revidovali jsme zprávy, které se zobrazují uživatelům zařízení, když zařízení nedodržuje předpisy. Zprávy si zachovávají svůj původní význam, ale jsou aktualizované tak, aby byly lépe srozumitelné a méně technické. Aktualizovali jsme také odkazy na dokumentaci a postupy pro odstranění problémů.
Následující texty „Před“ a „Po“ jsou jedním z příkladů vylepšení zpráv, kterých si můžete všimnout:
- **Před**: *Toto zařízení nekontaktovalo službu Intune v zadaném časovém období vyžadovaném vaším správcem IT. Pokud chcete tento problém vyřešit, otevřete prosím aplikaci Portál společnosti na svém zařízení a klikněte na tlačítko Zkontrolovat dodržování předpisů.*
- **Po**: *Vaše zařízení se už nějakou dobu neohlásilo organizaci. Pokud chcete znovu navázat spojení, otevřete na zařízení aplikaci Portál společnosti a pro dané zařízení klepněte na Zkontrolovat nastavení.*

#### <a name="revoke-ios-vpp-app-license----1863797---"></a>Odvolání licence aplikace VPP pro iOS <!-- 1863797 -->
Jako správce můžete uvolnit licenci aplikace VPP pro iOS přiřazenou uživateli nebo zařízení. Licenci aplikace budete moct uvolnit také odinstalováním aplikace VPP pro iOS. Před odinstalací aplikace je potřeba odebrat uživatele nebo zařízení ze skupiny, na kterou daná aplikace cílí. Odebráním uživatele nebo zařízení z příslušné skupiny se vyhnete opětovné instalaci této aplikace. Po dokončení těchto kroků můžete licenci aplikace přiřadit dalšímu uživateli nebo zařízení. Další informace o licencích aplikací VPP pro iOS najdete v tématu [o správě aplikací pro iOS zakoupených přes Volume Purchase Program v Microsoft Intune](vpp-apps-ios.md).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>Výběr kategorií zařízení pomocí nastavení Přístup do práce nebo do školy <!-- 1058963 eenotready --> 
Pokud jste povolili [mapování skupin zařízení](https://docs.microsoft.com/intune/device-group-mapping), uživatelům s Windows 10 se teď po registraci prostřednictvím tlačítka **Připojit** v **Nastavení** > **Účty** > **Přístup do práce nebo do školy** zobrazí výzva k výběru kategorie zařízení. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Použití atributu sAMAccountName jako uživatelského jména účtu pro e-mailové profily <!-- 1500307 -->
Můžete používat místní **sAMAccountName** jako uživatelské jméno účtu pro e-mailové profily v Androidu, iOSu a Windows 10. Můžete také získat doménu z atributu `domain` nebo `ntdomain` v Azure Active Directory (Azure AD). Nebo budete moct zadat vlastní statickou doménu.

Pokud chcete tuto funkci používat, musíte atribut `sAMAccountName` synchronizovat z místního prostředí Active Directory do Azure AD.

Platí pro [Android](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 a novější](email-settings-windows-10.md).

#### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Zobrazení konfliktních konfiguračních profilů zařízení <!-- 1556983 -->
V části **Konfigurace zařízení** se zobrazuje seznam existujících profilů. S touto aktualizací se přidá nový sloupec, který bude poskytovat podrobné informace o profilech, u kterých došlo ke konfliktu. Výběrem řádku s konfliktem můžete zobrazit nastavení a profil, u kterého se konflikt vyskytl. 

Přečtěte si další informace o [správě konfiguračních profilů](device-profile-monitor.md#view-conflicts).

#### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Nové stavy pro zařízení na stránce Dodržování předpisů zařízením <!-- 2308882 -->
Na stránku **Dodržování předpisů zařízením** > **Zásady** > vyberte zásadu > **Přehled** jsou přidané následující nové stavy:
- Úspěšné
- Chyba
- Konflikt
- Čekající na vyřízení
- Nepoužitelné Také se zobrazí obrázek, který ukazuje počet zařízení s jinou platformou. Když se třeba díváte na profil iOSu, na nové dlaždici se zobrazí počet zařízení s jiným systémem než iOS, která jsou také přiřazená k tomuto profilu. Viz [Zásady dodržování předpisů zařízením](compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Dodržování předpisů zařízením podporuje antivirová řešení jiných výrobců <!-- 2325484 -->
Při vytváření zásad dodržování předpisů zařízením (**Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu** > **Platforma: Windows 10 nebo novější** > **Nastavení** > **Zabezpečení systému**) jsou dostupné nové možnosti **[Zabezpečení zařízení](compliance-policy-create-windows.md#windows-10-and-later-policy-settings)**: 
- **Antivirus:** Když je tato možnost nastavená na **Vyžadovat**, můžete dodržování předpisů kontrolovat pomocí antivirových řešení, která jsou registrovaná Centrem zabezpečení systému Windows, jako je Symantec nebo Windows Defender. 
- **Antispyware**: Když je tato možnost nastavená na **Vyžadovat**, můžete dodržování předpisů kontrolovat pomocí antispywarových řešení (například Symantec nebo Windows Defender), která jsou registrovaná Centrem zabezpečení Windows. 

Platí pro: Windows 10 a novější 

### <a name="device-enrollment"></a>Registrace zařízení

####  <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens----1853904---"></a>Sloupec Zařízení bez profilů v seznamu tokenů programu registrace <!-- 1853904 -->
V seznamu tokenů programu registrace se nachází nový sloupec, který zobrazuje počet zařízení bez přiřazeného profilu. Pomáhá správcům při přiřazování profilů těmto zařízením před jejich přidělením uživatelům. Pokud chcete tento nový sloupec zobrazit, přejděte na **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace**.

### <a name="device-management"></a>Správa zařízení

#### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Změny názvů Android for Work a Play for Work společnosti Google <!--842873 -->
Intune aktualizoval terminologii „Android for Work“ tak, aby odrážela změny brandingu společnosti Google. Termíny „Android for Work“ a „Play for Work“ se už nepoužívají. V závislosti na kontextu se používá jiná terminologie:
- Termín „Android Enterprise“ označuje celkovou moderní sadu správy Androidu.
- Termín „Pracovní profil“ nebo „Vlastník profilu“ označuje vlastní zařízení uživatelů (BYOD) spravovaná pomocí pracovních profilů.
- Termín „Spravovaný obchod Google Play“ označuje Google App Store.

#### <a name="rules-for-removing-devices----1609459---"></a>Pravidla odebírání zařízení <!-- 1609459 -->
Jsou k dispozici nová pravidla, která vám umožňují automaticky odebrat zařízení, která se nastavený počet dnů neohlásila. Pokud chcete nové pravidlo zobrazit, přejděte do podokna **Intune** a vyberte **Zařízení** a **Pravidla čištění zařízení**.

#### <a name="corporate-owned-single-use-support-for-android-devices----1630973---"></a>Podpora zařízení s Androidem ve vlastnictví firmy pro použití s jednou aplikací <!-- 1630973 -->

Intune teď podporuje zamykatelná zařízení s beznabídkovým režimem Androidu a s vysokou úrovní správy. To správcům umožní další uzamčení použití zařízení na jednu aplikaci nebo malou sadu aplikací a zabrání uživatelům povolit na zařízení jiné aplikace nebo na něm provádět jiné akce. Pokud chcete nastavit beznabídkový režim Androidu, přejděte do Intune > **Registrace zařízení** > **Registrace Androidu** > **Beznabídkový režim a registrace zařízení úloh**. Další informace najdete v článku o [nastavení registrace zařízení s beznabídkovým režimem Androidu Enterprise](android-kiosk-enroll.md).

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794--"></a>Kontrola nahraných duplicitních identifikátorů firemních (podnikových) zařízení po řádcích <!-- 2203794-->
Při nahrávání firemních ID teď Intune poskytuje seznam duplicit a nabídne možnost nahradit nebo ponechat existující informace. Sestava se zobrazí, pokud vzniknou duplicity, když zvolíte **Registrace zařízení** > **Identifikátory podnikových zařízení** > **Přidat identifikátory**. 

#### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Ruční přidání identifikátorů firemních (podnikových) zařízení <!-- 2203803 -->
Teď je možné přidat ID podnikových zařízení ručně. Zvolte **Registrace zařízení** > **Identifikátory podnikových zařízení** > **Přidat**. 

## <a name="week-of-june-25-2018"></a>Týden od 25. června 2018

### <a name="pradeo---new-mobile-threat-defense-partner----1169249---"></a>Pradeo – nový partner ochrany před mobilními hrozbami <!-- 1169249 -->

Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Pradeo. Je to řešení ochrany před mobilními hrozbami integrované ve službě Microsoft Intune.

## <a name="week-of-june-18-2018"></a>Týden od 18. června 2018

### <a name="microsoft-edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Podpora zásad ochrany aplikací Intune v mobilní verzi prohlížeče Microsoft Edge <!-- 1817882 -->

Prohlížeč Microsoft Edge pro mobilní zařízení nyní podporuje zásady ochrany aplikací definované v Intune.

## <a name="week-of-june-11-2018"></a>Týden od 11. června 2018

### <a name="use-fips-mode-with-the-ndes-certificate-connector----1333688---"></a>Použití režimu FIPS s konektorem NDES Certificate <!-- 1333688 -->
Když jste nainstalovali konektor NDES Certificate na počítač se zapnutým režimem FIPS (Federal Information Processing Standard), vydávání a odvolávání certifikátů nefungovalo podle očekávání. Díky této aktualizaci bude konektor NDES Certificate standard FIPS podporovat. 

Tato aktualizace také zahrnuje:

- Konektor NDES Certificate vyžaduje rozhraní .NET 4.5 Framework, které je automaticky součástí Windows Serveru 2016 a Windows Serveru 2012 R2. Dříve bylo minimální požadovanou verzí rozhraní .NET 3.5 Framework.
- NDES Certificate Connector podporuje také protokol TLS 1.2. Pokud server s nainstalovaným NDES Certificate Connectorem podporuje TLS 1.2, použije se TLS 1.2. Pokud server nepodporuje TLS 1.2, použije se TLS 1.1. V současnosti se k ověřování zařízení a serveru používá protokol TLS 1.1.

Další informace najdete v tématech o [konfiguraci a použití certifikátů SCEP](certificates-scep-configure.md) a [konfiguraci a použití certifikátů PKCS](certficates-pfx-configure.md).

## <a name="week-of-june-4-2018"></a>Týden od 4. června 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Načtení ID modelu uživatele přidružené aplikace (AUMID) pro aplikace pro Microsoft Store pro firmy v beznabídkovém režimu <!-- 1560077 ! -->
Intune teď může načíst identifikátory AUMID pro aplikace Microsoft Store pro firmy (WSfB), aby bylo možné poskytnout vylepšenou konfiguraci profilu beznabídkového režimu.

Další informace o aplikacích pro Microsoft Store pro firmy najdete v článku [Správa aplikací z Microsoft Storu pro firmy](windows-store-for-business.md).

#### <a name="new-company-portal-branding-page----1916370---"></a>Nová stránka brandingu Portálu společnosti <!-- 1916370 -->
Stránka brandingu Portálu společnosti obsahuje nové rozložení, zprávy a popisky.


### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680----"></a>Podpora profilů VPN Palo Alto Networks GlobalProtect<!-- 1333680 ! -->
S touto aktualizací můžete zvolit Palo Alto Networks GlobalProtect jako typ připojení VPN pro profily VPN v Intune (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Typ profilu** > **VPN**). V této vydané verzi se podporují následující platformy: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Další nastavení možností místního zabezpečení zařízení <!-- 1403702 -->
U zařízení s Windows 10 teď můžete nakonfigurovat další nastavení možností místního zabezpečení zařízení. Další nastavení jsou dostupná v oblastech Klient sítě Microsoft, Server sítě Microsoft, Přístup k síti a zabezpečení a Interaktivní přihlášení. Tato nastavení najdete v kategorii Ochrana koncového bodu při vytváření zásad konfigurace zařízení s Windows 10.

#### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Povolení beznabídkového režimu na zařízeních s Windows 10 <!-- 1560072 ! -->
Na zařízeních s Windows 10 můžete vytvořit konfigurační profil a povolit beznabídkový režim (**Konfigurace zařízení** > **Profily** > **Vytvořit profil**  >  **Windows 10** > **Omezení zařízení** > **Beznabídkový režim**). V této aktualizaci je nastavení **Beznabídkový režim (Preview)** přejmenováno na **Beznabídkový režim (zastaralé)**. **Beznabídkový režim (zastaralé)** už nedoporučujeme používat, do červnové aktualizace ale zůstane funkční. **Beznabídkový režim (zastaralé)** se nahrazuje novým typem profilu **Beznabídkový režim** (**Vytvořit profil** > **Windows 10**  >  **Beznabídkový režim (Preview)**), který bude obsahovat nastavení pro konfiguraci beznabídkového režimu na systému Windows 10 RS4 a novějším.

Platí pro Windows 10 a novější.

#### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Uživatelský graf profilu zařízení je zpět <!-- 2160133 -->
Při vylepšování číselných počtů zobrazených v grafu profilu zařízení (**Konfigurace zařízení** > **Profily** > vyberte existující profil > **Přehled**) byl uživatelský graf dočasně odebrán.

V této aktualizaci se uživatelský graf vrací a zobrazuje se na portálu Azure Portal.

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication----1165118-wnready---"></a>Podpora pro registraci pomocí řešení Windows Autopilot bez ověření uživatele <!-- 1165118 wnready -->
Intune teď podporuje registraci pomocí řešení Windows Autopilot bez ověření uživatele. Je to nová možnost v profilu nasazení Windows Autopilot, která nastavuje režim automatického nasazení.  Pokud chcete úspěšně dokončit tento typ registrace, musí zařízení běžet na sestavení Windows 10 Insider Preview 17672 nebo novějším a musí mít čip TPM 2.0. Vzhledem k tomu, že se nevyžaduje žádné ověřování uživatelů, byste tuto možnost měli přiřazovat jenom pro zařízení, nad kterými máte fyzickou kontrolu.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Nové nastavení jazyka/oblasti při konfiguraci možností při prvním spuštění počítače pro Autopilot <!-- 1821766 -->
Nové nastavení konfigurace je dostupné pro nastavení jazyka a oblasti pro profily Autopilot během prvního spuštění počítače. Když chcete toto nové nastavení zobrazit, zvolte **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > **Vytvořit profil** > **Režim nasazení** = **Nasazení sebou samým** > **Nakonfigurovaly se výchozí hodnoty**.

#### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nové nastavení pro konfiguraci klávesnice zařízení <!-- 1821768 -->
Nové nastavení bude dostupné pro konfiguraci klávesnice pro profily Autopilot během prvního spuštění počítače. Když chcete toto nové nastavení zobrazit, zvolte **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > **Vytvořit profil** > **Režim nasazení** = **Nasazení sebou samým** > **Nakonfigurovaly se výchozí hodnoty**.

#### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Přesunutí profilů AutoPilot do cílení na skupinu <!-- 1877935 -->
Profily nasazení AutoPilot můžete přiřadit skupinám Azure AD, které obsahují zařízení AutoPilot.

### <a name="device-management"></a>Správa zařízení

#### <a name="set-compliance-by-device-location----851881----"></a>Nastavení dodržování předpisů podle umístění zařízení <!-- 851881 ! -->
Někdy můžete chtít omezit přístup k podnikovým prostředkům na konkrétní umístění definovaná podle síťového připojení. Teď můžete vytvořit zásady dodržování předpisů (**Dodržování předpisů zařízením** > **Umístění**) na základě IP adresy zařízení. Pokud se zařízení přesune mimo rozsah IP adres, nebude moct přistupovat k podnikovým prostředkům.

Platí pro: Zařízení s Androidem verze 6.0 a novější s aktualizovanou aplikací Portál společnosti

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Blokování uživatelských aplikací a prostředí na zařízeních Windows 10 Enterprise RS4 AutoPilot<!-- 1621980 -->
Budete moct zabránit v instalaci uživatelských aplikací a prostředí na zařízeních Windows 10 Enterprise RS4 AutoPilot. Když chcete tuto funkci zobrazit, přejděte na **Intune** > **Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Platforma** = **Windows 10 nebo novější** > **Typ profilu** = **Omezení zařízení** > **Konfigurovat** > **Windows Spotlight** > **Uživatelské funkce**. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948---"></a>Odinstalace nejnovější aktualizace softwaru Windows 10 <!-- 1732948 -->
Pokud na počítačích s Windows 10 najdete problém způsobující chybu, můžete se rozhodnout odinstalovat (vrátit zpět) nejnovější aktualizaci funkcí nebo nejnovější aktualizaci kvality. Odinstalace aktualizace funkcí nebo kvality je dostupná jenom pro kanál pro údržbu, ve kterém se dané zařízení nachází. Při odinstalaci se aktivují zásady, které na počítačích s Windows 10 obnoví předchozí aktualizaci. Konkrétně u aktualizací funkcí je možné omezit dobu 2 až 60 dnů, po kterou lze provést odinstalaci nejnovější verze. Pokud chcete nastavit možnosti odinstalace aktualizací softwaru, vyberte na webu Azure Portal v okně **Microsoft Intune** možnost **Aktualizace softwaru**. Pak v okně **Aktualizace softwaru** vyberte **Aktualizační kanály Windows 10**. Pak můžete v části **Přehled** zvolit možnost **Odinstalovat**.

#### <a name="search-all-devices-for-imei-and-serial-number----1793685---"></a>Hledání IMEI a sériového čísla v okně Všechna zařízení <!-- 1793685 -->
Teď můžete hledat IMEI a sériová čísla v okně Všechna zařízení (pole pro e-mail, hlavní název uživatele (UPN), název zařízení a název správy jsou nadále dostupná). V Intune zvolte **Zařízení** > **Všechna zařízení** a do vyhledávacího pole zadejte hledanou položku.

#### <a name="management-name-field-will-be-editable----1875989---"></a>Pole Název správy bude možné upravovat <!-- 1875989 -->
Teď můžete v okně **Vlastnosti** příslušného zařízení upravovat pole Název správy. Pokud chcete toto pole upravit, vyberte **Zařízení** > **Všechna zařízení** > vyberte zařízení > **Vlastnosti**. Pole s názvem správy můžete použít k jednoznačné identifikaci zařízení.

#### <a name="new-all-devices-filter-device-category----1878520---"></a>Nový filtr Všechna zařízení: Kategorie zařízení <!-- 1878520 -->
Teď můžete filtrovat seznam **Všechna zařízení** podle kategorie zařízení. Když to chcete udělat, zvolte **Zařízení** > **Všechna zařízení** > **Filtrovat** > **Kategorie zařízení**.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>Použití TeamVieweru ke sdílení obrazovek na zařízeních s iOSem a MacOS<!-- 1985547 -->
Správci se teď můžou připojit k [TeamVieweru](device-profile-android-teamviewer.md) a spustit relaci sdílení obrazovky se zařízeními s iOSem a macOS. Uživatelé iPhonů, iPadů a zařízení s macOS mohou své obrazovky živě sdílet s libovolnými jinými stolními nebo mobilními zařízeními. 

#### <a name="multiple-exchange-connector-support----2070451---"></a>Podpora více Exchange Connectorů <!-- 2070451 -->
Už neplatí omezení v podobě jednoho Microsoft Intune Exchange Connectoru na každého tenanta. Intune teď podporuje více Exchange Connectorů, takže můžete nastavit podmíněný přístup Intune s více organizacemi místního Exchange.

S místním konektorem Exchange v Intune můžete spravovat přístup zařízení k místním poštovním schránkám Exchange podle toho, jestli je zařízení zaregistrované v Intune a splňuje zásady dodržování předpisů zařízením. Konektor nastavíte tak, že místní konektor Exchange v Intune stáhnete z portálu Azure Portal a nainstalujete ho na server v organizaci Exchange. Na řídicím panelu Microsoft Intune zvolte **Místní přístup** a pak v **Nastavení** vyberte **Konektor Exchange ActiveSync**. Stáhněte místní konektor Exchange a nainstalujte ho na server v organizaci Exchange. Protože už teď neplatí omezení v podobě jednoho konektoru Exchange na každého tenanta, pokud máte další organizace Exchange, můžete stejným postupem stáhnout a nainstalovat konektor pro každou další organizaci Exchange.

#### <a name="new-device-hardware-detail-ccid----2156657---"></a>Nový údaj o hardwaru zařízení: CCID <!-- 2156657 -->
U každého zařízení je teď uvedený údaj CCID (Chip Card Interface Device). Když ho chcete zobrazit, zvolte **Zařízení** > **Všechna zařízení** > zvolte zařízení > **Hardware** a zkontrolujte část **Podrobnosti o síti**>.

#### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Přiřazení všech uživatelů a všech zařízení jako skupin oborů <!-- 2196803 -->
Všechny uživatele, všechna zařízení a všechny uživatele a zařízení teď můžete přiřadit do skupin oborů. Když to chcete udělat, zvolte **Role Intune** > **Všechny role** > **Správce zásad a profilů** > **Přiřazení** > zvolte přiřazení > **Rozsah (Skupiny)**.

#### <a name="udid-information-now-included-for-ios-and-macos-devices----2219806-wnready--"></a>U zařízení s iOSem a macOS je teď uvedený identifikátor UDID <!-- 2219806 wnready-->
Když chcete identifikátor UDID (Unique Device Identifier) pro zařízení s iOSem a macOS zobrazit, přejděte na **Zařízení** > **Všechna zařízení** > zvolte zařízení > **Hardware**. Identifikátor UDID je dostupný jenom pro firemní zařízení (podle nastavení v části **Zařízení** > **Všechna zařízení** > zvolte zařízení > **Vlastnosti** > **Vlastnictví zařízení**).

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Vylepšené řešení potíží pro instalace aplikací <!-- 928990 -->
U zařízení spravovaných pomocí Microsoft Intune MDM může občas dojít k chybě instalace. Když k těmto chybám instalace dojde, může být obtížné pochopit, proč k nim došlo nebo je odstranit. Spouštíme verzi Public Preview našich funkcí řešení potíží s aplikacemi. U každého jednotlivého zařízení si všimnete nového uzlu **Spravované aplikace**. Jedná se o seznam aplikací, které byly dodány prostřednictvím MDM Intune. Uvnitř uzlu uvidíte seznam stavů instalací aplikací. Pokud vyberete konkrétní aplikaci, uvidíte zobrazení řešení potíží pro tuto konkrétní aplikaci. V zobrazení řešení potíží se zobrazí úplný životní cyklus aplikace, například kdy byla aplikace vytvořena, upravena, zacílena a dodána do zařízení. Pokud navíc nebyla instalace aplikace úspěšná, zobrazí se vám kód chyby a užitečná zpráva týkající se příčiny chyby. 

#### <a name="intune-app-protection-policies-and-microsoft-edge----1818968---"></a>Zásady ochrany aplikací Intune a Microsoft Edge <!-- 1818968 -->
Prohlížeč Microsoft Edge pro mobilní zařízení (iOS a Android) teď podporuje zásady ochrany aplikací Microsoft Intune. Uživatelé zařízení s iOSem a Androidem, kteří se přihlásí svými podnikovými účty Azure AD k aplikaci Edge, budou chráněni službou Intune. Na zařízeních s iOSem umožní zásada **Vyžadovat spravovaný prohlížeč pro webový obsah** uživatelům otevírat odkazy v Microsoft Edgi, pokud je spravovaný.

## <a name="week-of-may-14-2018"></a>Týden od 14. května 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Nutnost instalace zásad, aplikací a profilů certifikátů a sítí <!-- 1553555 -->

Správci mohou koncovým uživatelům zablokovat přístup k desktopu Windows 10 RS4, dokud Intune nenainstaluje zásady, aplikace a profily certifikátů a sítí při zřizování zařízení AutoPilot. Další informace najdete v článku [Nastavení stránky stavu registrace](windows-enrollment-status.md).

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Konfigurace zásad ochrany aplikací <!-- 2144597 Part 2 -->

Na portálu Azure Portal nyní přejdete přímo do Intune a nikoli do okna služby Intune App Protection. Pro zásady ochrany aplikací v rámci Intune nově existuje pouze jedno umístění. Všimněte si, že všechny vaše zásady ochrany aplikací se nacházejí v okně **Mobilní aplikace** v Intune v části **Zásady ochrany aplikací**. Tato integrace usnadňuje práci se správou cloudu. Nezapomeňte, že všechny zásady ochrany aplikací jsou už přenesené do Intune a kterékoli z předem nakonfigurovaných zásad můžete upravit. Zásady ochrany aplikací Intune a podmíněného přístupu se nově nacházejí v části **Podmíněný přístup**, kterou najdete v části **Spravovat** v okně **Microsoft Intune** nebo v části **Zabezpečení** v okně **Azure Active Directory**. Podrobnosti o úpravách zásad podmíněného přístupu najdete v tématu [Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Další informace viz téma [Co jsou zásady ochrany aplikací](app-protection-policy.md).

## <a name="week-of-may-7-2018"></a>Týden od 7. května 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Podpora technologie Samsung Knox Mobile Enrollment <!--1112863-->

Pokud Intune používáte s technologií Samsung Knox Mobile Enrollment (KME), můžete registrovat velké počty zařízení s Androidem vlastněné společností. Uživatelé připojení prostřednictvím Wi-Fi nebo mobilních sítí mohou svá zařízení při prvním zapnutí registrovat několika klepnutími. Při použití aplikace Knox Deployment App se mohou zařízení registrovat pomocí Bluetooth nebo NFC. Další informace najdete v článku věnovaném [automatické registraci zařízení s Androidem pomocí technologie Knox Mobile Enrollment od Samsungu](android-samsung-knox-mobile-enroll.md).

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Žádost o nápovědu na Portálu společnosti pro Windows 10 <!-- 1874137 -->

Portál společnosti pro Windows 10 teď odesílá protokoly aplikace přímo Microsoftu, když uživatel iniciuje pracovní postup pro získání pomoci s problémem. Usnadní se tak řešení problémů, které jsou předávány Microsoftu.

## <a name="week-of-april-23-2018"></a>Týden od 23. dubna 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Podpora hesla pro kód PIN MAM na Androidu<!-- 1438086 -->

Správci Intune mohou nastavit požadavek, aby se při spuštění aplikace povinně zadávalo heslo místo číselného kódu PIN MAM. Při takové konfiguraci musí uživatel po zobrazení výzvy nastavit a používat heslo, aby získal přístup k aplikacím s podporou MAM. Heslo je definované jako číselný kód PIN s aspoň jedním speciálním znakem nebo velkým/malým písmenem. Intune podporuje heslo podobným způsobem jako existující číselný kód PIN, umožňuje stanovit minimální délku a povoluje opakování znaků a sekvencí prostřednictvím konzoly pro správu. Tato funkce vyžaduje nejnovější verzi Portálu společnosti na Androidu. Tato funkce je už k dispozici pro iOS.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Podpora obchodních aplikací (LOB) pro macOS <!-- 1473977 -->
Microsoft Intune bude poskytovat možnost instalace obchodních aplikací pro macOS z portálu Azure Portal. Do Intune budete moct přidat obchodní aplikaci pro masOS poté, co ji předběžně zpracoval nástroj dostupný v GitHubu. Na portálu Azure Portal v okně **Intune** zvolte **Klientské aplikace**. V okně **Klientské aplikace** zvolte **Aplikace** > **Přidat**. V okně **Přidat aplikaci** vyberte **Obchodní aplikace**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-enterprise-work-profile-app-assignment----1813073---"></a>Předdefinované skupiny Všichni uživatelé a Všechna zařízení pro přiřazení aplikace pracovního profilu Android Enterprise <!-- 1813073 -->
K přiřazení aplikace pracovního profilu Android Enterprise můžete použít předdefinované skupiny **Všichni uživatelé** a **Všechna zařízení**. Podrobnosti najdete v tématu [Zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune](apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Intune přeinstaluje požadované aplikace, které odinstalovali uživatelé <!-- 1947010 -->
Pokud koncový uživatel odinstaluje některou z povinných aplikací, Intune nečeká na sedmidenní cyklus vyhodnocení a během 24 hodin ji automaticky znovu nainstaluje.

### <a name="device-configuration"></a>Konfigurace zařízení

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153---"></a>Graf profilu zařízení a seznam stavů zobrazují všechna zařízení ve skupině <!-- 1449153 -->
Při konfiguraci profilu zařízení (**Konfigurace zařízení** > **Profily**) vyberete profil zařízení, například iOS. Tento profil přiřadíte ke skupině, která obsahuje zařízení s iOSem a zařízení s jiným systémem. Počet v grafu zobrazuje, že profil je použitý u zařízení s iOSem *a* u zařízení s jiným systémem (**Konfigurace zařízení** > **Profily** > vyberte existující profil > **Přehled**). Když vyberete graf na kartě **Přehled** zobrazí se v části **Stav zařízení** seznam všech zařízení ve skupině, nikoli pouze seznam zařízení s iOSem. 

Po této aktualizaci se v grafu (**Konfigurace zařízení** > **Profily** > vyberte stávající profil > **Přehled**) zobrazí jenom počet odpovídající určitému profilu zařízení. Pokud například konfigurační profil zařízení platí pro zařízení s iOSem, zobrazí se v grafu pouze počet zařízení s iOSem. Když vyberete graf a otevřete **Stav zařízení**, zobrazí se pouze zařízení s iOSem.

Během přípravy této aktualizace je uživatelský graf dočasně nedostupný. 

#### <a name="always-on-vpn-for-windows-10---1333666---"></a>VPN Always On pro Windows 10 <!--1333666 -->

V současné době je možné [Always On](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) použít na zařízeních s Windows 10 prostřednictvím vlastního profilu VPN vytvořeného pomocí OMA-URI.

Po této aktualizaci mohou správci přímo v Intune na webu Azure Portal povolit profily sítě VPN Always On pro Windows 10. Profily VPN Always On se automaticky připojí v těchto případech:

- Při přihlášení uživatelů do zařízení
- Při změně sítě na zařízení
- Při opětovném zapnutí obrazovky na zařízení po vypnutí

#### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nové nastavení tiskárny pro vzdělávací profily <!-- 1308900 -->

Ve vzdělávacích profilech je k dispozici nové nastavení v kategorii **Tiskárny**: **Tiskárny**, **Výchozí tiskárna**, **Přidat nové tiskárny**.

#### <a name="show-caller-id-in-personal-profile---android-enterprise-work-profile---1098984---"></a>Zobrazení ID volajícího v osobním profilu – pracovní profil Android Enterprise <!--1098984 -->
Při použití osobního profilu na zařízení nemusí koncoví uživatelé vidět podrobnosti ID volajícího z pracovního kontaktu. 

Od této aktualizace je v části **Android Enterprise** > **Omezení zařízení** > **Nastavení pracovního profilu** k dispozici nové nastavení:
- Zobrazit v osobním profilu ID volajícího pracovního kontaktu

Pokud je povoleno (nenakonfigurováno), podrobnosti volajícího pracovního kontaktu se v osobním profilu zobrazují. V případě blokování se číslo volajícího pracovního kontaktu v osobním profilu nezobrazuje. 

Platí pro: Zařízení s pracovním profilem Android v systému Android OS v6.0 a novějších.

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Nové nastavení Ochrany Credential Guard v programu Windows Defender přidaná do nastavení ochrany koncového bodu <!--1102252 --><!--from 1802 and 1804-->

V této aktualizaci zahrnuje [ochrana Credential Guard v programu Windows Defender](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Konfigurace zařízení** > **Profily** > **Ochrana koncového bodu**) následující nastavení: 

- **Ochrana Credential Guard v programu Windows Defender**: Zapne ochranu přihlašovacích údajů Credential Guard se zabezpečením na základě virtualizace. Pokud je tato funkce zapnutá, budou po dalším restartování přihlašovací údaje chráněny **úrovní zabezpečení platformy, která je nastavená na zabezpečené spouštění,** a zapnutým **zabezpečením založeným na virtualizaci**. Vaše možnosti jsou:
  - **Zakázáno**: Pokud byla ochrana Credential Guard dříve zapnutá možností **Povoleno bez zámku**, vzdáleně vypne ochranu Credential Guard.

  - **Povoleno s uzamčením UEFI**: Zajistí, že ochrana Credential Guard nepůjde vypnout v klíčích registru ani v zásadách skupiny. Pokud jste použili toto nastavení a chcete ochranu Credential Guard zakázat, musíte nastavit zásady skupiny na Zakázáno. Potom bezpečnostní funkci odeberte z každého počítače, u kterého je uživatel fyzicky přítomen. Tyto kroky smažou konfiguraci uloženou v rozhraní UEFI. Dokud je uložená konfigurace UEFI, je povolená i ochrana přihlašovacích údajů Credential Guard.

  - **Povoleno bez zámku**: Umožňuje vzdáleně zakázat ochranu Credential Guard v zásadách skupiny. Na zařízeních s tímto nastavením musí běžet přinejmenším Windows 10 (verze 1511).

Následující související technologie se při konfiguraci ochrany přihlašovacích údajů Credential Guard zapnou automaticky: 

  - **Povolit zabezpečení na základě virtualizace (VBS)**: Při příštím restartování povolí zabezpečení na základě virtualizace (VBS). Zabezpečení na základě virtualizace nabízí podporu služeb zabezpečení pomocí hypervisoru Windows a vyžaduje zabezpečené spouštění.
  - **Zabezpečené spouštění s přímým přístupem do paměti (DMA)**: Zapne VBS se zabezpečeným spouštěním a přímým přístupem k paměti. Ochrana DMA vyžaduje hardwarovou podporu a povolí se jenom na správně nakonfigurovaných zařízeních. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Použití vlastního názvu subjektu u certifikátu SCEP <!-- 2064190 -->
V profilu certifikátu SCEP můžete u vlastního subjektu použít běžný název **OnPremisesSamAccountName**. Můžete například použít `CN={OnPremisesSamAccountName})`.

####  <a name="block-camera-and-screen-captures-on-android-enterprise-work-profiles----1098977---"></a>Blokování kamery a snímků obrazovky v pracovních profilech Android Enterprise <!-- 1098977 -->
Při konfiguraci omezení zařízení s Androidem jsou k dispozici dvě nové vlastnosti umožňující blokování: 
- Kamera: Blokování přístupu ke všem kamerám na zařízení
- Snímek obrazovky: Blokování vytváření snímků obrazovky a tím také ochrana obsahu před zobrazením na zobrazovacích zařízení, která nemají zabezpečený výstup videa

Platí pro pracovní profily Android Enterprise.


### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nové kroky registrace pro uživatele používající zařízení s macOS High Sierra 10.13.2+ <!--1734567 -->
Systém macOS high Sierra 10.13.2 představil nový koncept registrace MDM, který vyžaduje schválení uživatelem (User Approved). Schválené registrace umožňují v Intune spravovat některá citlivá nastavení zabezpečení. Další informace najdete v dokumentaci podpory Apple tady: https://support.apple.com/HT208019.

Zařízení zaregistrovaná v aplikaci Portál společnosti pro macOS se považují za neschválená uživatelem, dokud koncový uživatel neotevře předvolby systému a neschválí je ručně. Z tohoto důvodu nyní Portál společnosti pro macOS instruuje uživatele systému macOS 10.13.2 a novějšího, aby na konci procesu registrace přešli do příslušného umístění a ručně registraci schválili. Konzola správce Intune oznámí, zda je zaregistrované zařízení schváleno uživatelem.



### <a name="device-management"></a>Správa zařízení

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----1629303---"></a>Rozšířená ochrana před internetovými útoky (ATP) a Intune jsou plně integrované <!-- 1629303 -->

[Rozšířená ochrana před internetovými útoky (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) zobrazuje úroveň rizika u zařízení s Windows 10. V Centru zabezpečení v programu Windows Defender (portál ATP) můžete vytvořit připojení k Microsoft Intune. Jakmile se vytvoří, pomocí zásad dodržování předpisů Intune se určí přijatelná úroveň ohrožení. Pokud se úroveň ohrožení překročí, zásady podmíněného přístupu služby Azure Active Directory (AD) můžou zablokovat přístup k různým aplikacím v organizaci.

Tato funkce umožňuje ochraně ATP kontrolovat soubory, zjišťovat hrozby a ohlašovat jakákoli rizika pro zařízení s Windows 10.

Přečtěte si článek o [povolení ochrany ATP s podmíněným přístupem v Intune](advanced-threat-protection.md).

#### <a name="support-for-user-less-devices----1637553---"></a>Podpora pro zařízení bez určeného uživatele <!-- 1637553 -->
U zařízení bez určeného uživatele, jako je Microsoft Surface Hub, podporuje Intune hodnocení dodržování předpisů. Zásady dodržování předpisů mohou cílit na konkrétní zařízení. Dodržování (a nedodržování) předpisů je tedy možné stanovit i u zařízení, která nemají přiřazené uživatele.

#### <a name="delete-autopilot-devices----1713650---"></a>Odstranění zařízení AutoPilot <!-- 1713650 -->
Správci Intune mohou [odstranit zařízení AutoPilot](enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Vylepšené prostředí pro odstraňování zařízení <!--1832333 -->
Před [odstraněním zařízení z Intune](devices-wipe.md#delete-devices-from-the-intune-portal) už nemusíte odebírat firemní data ani na zařízení obnovovat tovární nastavení.

Pokud se chcete podívat na nové prostředí, přihlaste se k Intune a vyberte **Zařízení** > **Všechna zařízení** > název zařízení > **Odstranit**.

Pokud i nadále chcete potvrzovat vymazání nebo vyřazení, můžete použít standardní cestu životního cyklu zařízení a před **odstraněním** vybrat možnost **Odebrat firemní data** a **Obnovení továrního nastavení**. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Přehrávání zvuků v iOSu v režimu ztráty <!-- 1947769 -->
Pokud jsou sledovaná zařízení s iOSem v [režimu ztráty](device-lost-mode.md) MDM (Mobile Device Management), můžete [přehrát zvuk](device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Zařízení** > **Všechna zařízení** > vyberte zařízení s iOSem > **Přehled** > **Další**). Zvuk se přehrává, dokud je zařízení v režimu ztráty nebo na něm uživatel nevypne zvuk. Platí pro zařízení s iOSem 9.3 nebo novějším.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Blokování nebo povolení webových výsledků hledání na zařízení spravovaném v Intune <!--1972804-->

Správci teď mohou na zařízení blokovat webové výsledky hledání.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Vylepšené zasílání chybových zpráv při chybě odeslání certifikátu Apple MDM Push Certificate <!-- 2172331 -->

Chybová zpráva vysvětluje, že při obnovení stávajícího certifikátu MDM je potřeba použít stejné Apple ID.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>Testování aplikace Portál společnosti pro macOS na virtuálních počítačích <!-- 2216679 -->

Zveřejnili jsme pokyny, které správcům IT pomůžou testovat aplikaci Portál společnosti pro macOS na virtuálních počítačích s aplikacemi Parallels Desktop a VMware Fusion. Další informace najdete v článku [Registrace virtuálních počítačů s macOS pro účely testování](macos-enroll.md#enroll-virtual-macos-machines-for-testing).


### <a name="user-interface"></a>Uživatelské rozhraní

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Vylepšené dlaždice zařízení v aplikaci Portál společnosti pro Windows 10 <!--2213364 -->

Aktualizovali jsme dlaždice, aby je dokázali přečíst i uživatelé se zhoršeným zrakem a aby fungovaly lépe s nástroji na čtení obrazovky.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Odesílání diagnostických hlášení v aplikaci Portál společnosti pro macOS <!-- 2216677 -->
Aktualizovali jsme aplikaci Portál společnosti pro zařízení s macOS a zlepšili jsme způsob, jakým uživatelé nahlašují chyby týkající se Intune. Co aplikace Portál společnosti zaměstnancům umožňuje:

- Posílat diagnostická hlášení přímo vývojovému týmu Microsoft.
- Posílat e-mailem ID incidentů týmu IT podpory vaší společnosti.

Další informace najdete v článku o [posílání chyb ze zařízení s macOS](/intune-user-help/send-errors-macos).

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010-wnready---"></a>Aplikace Portál společnosti Intune pro Windows 10 používá systém návrhu FDS (Fluent Design System) <!-- 1195010 WNready -->
Aplikace Portál společnosti Intune pro Windows 10 byla aktualizována o [navigační zobrazení systému návrhu FDS](https://docs.microsoft.com/windows/uwp/design/basics/navigation-basics). Po straně aplikace je statický svislý seznam všech hlavních stránek. Když na odkaz kliknete, stránka se rychle zobrazí nebo můžete mezi stránkami přepínat. Jde o první z řady aktualizací, které jsou výsledkem naší trvalé snahy o vytvoření přizpůsobivého, empatického a známého prostředí Intune. Pokud si chcete nový vzhled prohlédnout, přejděte na [Co je nového v uživatelském rozhraní aplikace](whats-new-app-ui.md).

## <a name="week-of-april-16-2018"></a>Týden od 16. dubna 2018

#### <a name="use-cisco-anyconnect-client-for-ios----1333708---"></a>Použití klienta Cisco AnyConnect pro iOS <!-- 1333708 -->

Když vytváříte nový profil VPN pro iOS, jsou teď k dispozici dvě možnosti: **Cisco AnyConnect** a **Cisco Legacy AnyConnect**. Profily Cisco AnyConnect podporují verzi 4.0.7x a novější. Stávající profily VPN Cisco AnyConnect pro iOS jsou označené jako **Cisco Legacy AnyConnect** a budou dál fungovat s Cisco AnyConnect 4.0.5x stejně jako dnes.

> [!NOTE]
> Tato změna platí jen pro iOS. Pro Android, pracovní profily Android Enterprise a macOS bude dál existovat jenom jedna možnost Cisco AnyConnect.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>Zařízení s macOSem zaregistrovaná do Jamf se teď registrují do Intune <!-- 2370684 -->

Verze 1.3 a 1.4 portálu společnosti macOS neregistrovaly zařízení Jamf do Intune úspěšně. Verze 1.4.2 portálu macOS tento problém řeší.


## <a name="week-of-april-9-2018"></a>Týden od 9. dubna 2018  
#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Aktualizované prostředí nápovědy aplikace Portál společnosti pro Android <!-- 1631531 -->

Aktualizovali jsme prostředí nápovědy v aplikaci Portál společnosti pro Android, aby bylo v souladu s osvědčenými postupy pro platformu Android. Když teď dojde k potížím s aplikací, může uživatel klepnout na **Nabídka** > **Nápověda** a:
- Odeslat Microsoftu diagnostický protokol
- Odeslat e-mail s popisem problému a ID incidentu pracovníkovi podpory ve své společnosti  

Pokud si chcete aktualizované prostředí nápovědy prohlédnout, přejděte na [Odeslání protokolů e-mailem](/intune-user-help/send-logs-to-your-it-admin-by-email-android) a [Odeslání chyb do Microsoftu](/intune-user-help/send-logs-to-microsoft-android).


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nový graf trendu neúspěšných registrací a tabulka důvodů selhání <!-- 1471783 -->

Na stránce s přehledem registrací můžete vidět trend neúspěšných registrací a pět nejčastějších příčin selhání. Kliknutím na tento graf nebo tabulku můžete přejít k podrobnostem a najít rady pro řešení problémů a návrhy vedoucí k nápravě.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Aktualizace místa, kde konfigurujete zásady ochrany aplikací <!-- 2144597 -->

Na portálu Azure Portal v rámci služby Microsoft Intune vás dočasně přesměrujeme z okna služby **Intune App Protection** do okna **Mobilní aplikace**. Všechny vaše zásady ochrany aplikací se už nacházejí v okně **Mobilní aplikace** v Intune v oblasti konfigurace aplikací. Místo přechodu na službu Intune App Protection přejdete přímo na Intune. V dubnu 2018 toto přesměrování ukončíme a okno služby **Intune App Protection** úplně odebereme, aby se zásady ochrany aplikací nacházely v Intune jen na jednom místě. 

**Co to pro mě znamená?**
Tato změna ovlivní jak zákazníky samostatné verze Intune, tak zákazníky hybridní verze (Intune s Configuration Managerem). Tato integrace pomůže zjednodušit práci se správou cloudu.

**Jak se mám na tuto změnu připravit?**
Místo okna služby **Intune App Protection** si do oblíbených položek přidejte **Intune** a seznamte se s pracovním postupem zásad ochrany aplikací v okně **Mobilní aplikace** v Intune. Po krátkém období přesměrování okno **App Protection** odebereme. Nezapomeňte, že všechny zásady ochrany aplikací jsou už přenesené do Intune a kterékoli ze zásad podmíněného přístupu můžete upravit. Podrobnosti o úpravách zásad podmíněného přístupu najdete v tématu [Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Další informace viz téma [Co jsou zásady ochrany aplikací](app-protection-policy.md). 


## <a name="week-of-april-2-2018"></a>Týden od 2. dubna 2018

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>Aktualizace uživatelského prostředí aplikace Portál společnosti pro iOS <!--1412866 -->
Vydali jsme důležitou aktualizaci uživatelského prostředí aplikace Portál společnosti pro iOS. Tato aktualizace nabízí zcela přepracovaný vzhled aplikace, včetně modernějšího vzhledu a chování. Zachovali jsme funkčnost aplikace, ale zvýšili její využitelnost a přístupnost.  

Další vylepšení:
- Podpora pro iPhone X
- Rychlejší spouštění aplikace a odezva při načítání, které uživateli šetří čas
- Další indikátory průběhu, které uživatelům poskytují aktuální informace o stavu
- Vylepšené nahrávání protokolů, které usnadňuje hlášení vzniklých problémů  

Pokud si chcete nový vzhled prohlédnout, přejděte na [Co je nového v uživatelském rozhraní aplikace](whats-new-app-ui.md).

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca----1056954---"></a>Ochrana místních dat systému Exchange pomocí zásad ochrany aplikací Intune a podmíněného přístupu <!-- 1056954 -->
Nově můžete chránit přístup k místním datům systému Exchange z Outlooku Mobile prostřednictvím zásad ochrany aplikací Intune a podmíněného přístupu. Pokud chcete na portálu Azure Portal přidat nebo upravit zásady ochrany aplikací, vyberte **Microsoft Intune** > **Klientské aplikace** > **Zásady ochrany aplikací**. Ještě než začnete tuto funkci využívat, zkontrolujte, že splňujete [požadavky na Outlook pro iOS a Android](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx).

## <a name="notices"></a>Sdělení

### <a name="plan-for-change-performance-updates-to-intune-for-education---1750215--"></a>Plánovaná změna: Aktualizace výkonu pro Intune for Education <!--1750215-->
Do Intune for Education přidáváme určité aktualizace, které zvyšují rychlost a spolehlivost při přiřazování nastavení uživatelům nebo zařízením. V rámci této změny přesuneme koncem listopadu přiřazení vašich zásad nebo nastavení do nových skupin.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?

Jako zákazník Intune for Education máte dvě dynamické skupiny služby Azure Active Directory (Azure AD): „Všichni uživatelé“ a „Všechna zařízení“. S těmito aktualizacemi už skupiny služby Azure AD „Všichni uživatelé“ a „Všechna zařízení“ nebudou viditelné v konzole Intune for Education. Budou ale pořád viditelné v konzole Intune v Azure a přejmenují se na „Všichni uživatelé (zastaralé, nepoužívat)“ a „Všechna zařízení (zastaralé, nepoužívat)“.

Po zavedení těchto aktualizací už nebudete muset k přiřazení aplikací a nastavení v Intune používat skupiny služby Azure AD. Místo toho přesuneme přiřazení vašich nastavení do nových skupin v konzole Intune for Education, které za vás vytvoříme a které se budou jmenovat „Všichni uživatelé“ a „Všechna zařízení“ jako dříve. Tyto změny se odehrávají v back-endu, takže si v konzole Intune for Education nevšimnete žádných odlišností. Neočekává se žádný vliv na vaše koncové uživatele a zaregistrovaná zařízení. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Během přesouvání přiřazení zásad nemusíte nic dělat. Pokud momentálně přiřazujete zásady v konzole Intune for Education, pokračujte v tom i nadále.

Pokud momentálně přiřazujete zásady k výše uvedeným skupinám služby Azure AD v Intune v Azure, začněte je místo toho přiřazovat ke skupině Všichni uživatelé a Všechna zařízení v konzole Intune for Education. Až v konzole uvidíte tyto skupiny služby Azure AD přejmenované na zastaralé, přestaňte zásady přiřazovat ve službě Azure AD. Pokud v současnosti nepoužíváte přejmenované skupiny k žádnému jinému účelu, měli byste je odstranit.


### <a name="plan-for-change-intune-will-move-to-support-macos-1012-and-higher-in-december---2970975--"></a>Plánovaná změna: V Intune se začne podporovat macOS 10.12 a vyšší v prosinci <!--2970975--> 

Apple právě vydal macOS 10.14. Následně Intune začne podporovat macOS 10.12 a vyšší v prosinci 2018. 

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?

Od prosince koncoví uživatelé zařízení s macOS 10.11 a staršími nebudou moci používat portál společnosti k registraci do Intune. Budou muset upgradovat svoje zařízení s macOS 10.12 nebo vyšší a upgradovat aplikaci Portál společnosti na nejnovější verzi, aby mohli i nadále přijímat podporu a nové funkce. 

macOS verze 10.12 a vyšší se aktuálně podporuje na: 
- MacBook (konec roku 2009 nebo novější) 
- iMac (konec roku 2009 nebo novější)
- MacBook Air (konec roku 2010 nebo novější)  
- MacBook Pro (konec roku 2010 nebo novější) 
- Mac Mini (konec roku 2010 nebo novější) 
- Mac Pro (konec roku 2010 nebo novější) 

Po prosinci nebudou mít koncoví uživatelé, kteří mají zařízení kromě těch, která jsou uvedená výše, přístup k nejnovější verzi aplikace Portál společnosti pro macOS. Stávající zaregistrovaná zařízení s nepodporovanými verzemi macOS staršími než 10.12 se budou spravovat a zobrazovat i nadále v konzole správce Intune.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?

- Požádejte vaše koncové uživatele, aby si do prosince 2018 upgradovali zařízení na podporovanou verzi operačního systému. 
- Podívejte se do sestav Intune v konzole Intune v Azure a zkontrolujte, jakých zařízení nebo uživatelů se to může týkat. Přejděte na Zařízení > Všechna zařízení a vyfiltrujte si je podle operačního systému. Můžete přidat dodatečné sloupce, které vám pomůžou identifikovat, kdo ve vaší organizaci má zařízení s macOS 10.11. 
- Pokud používáte hybridní správu mobilních zařízení (MDM), přejděte v konzole nástroje Configuration Manager na Prostředky a kompatibilita > Zařízení, klikněte pravým tlačítkem na sloupce, abyste mohli přidat sloupce Operační systém a Verze klienta, a seřaďte je podle operačního systému. Připomínáme, že hybridní MDM je už zastaralé a měli byste co nejdříve přejít na Intune v Azure. 
 
#### <a name="additional-information"></a>Další informace
Další informace najdete v tématu [Registrace zařízení s macOS v Intune pomocí aplikace Portál společnosti](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp).
 

### <a name="plan-for-change-new-intune-support-experience-for-premier-customers"></a>Plánovaná změna: nové prostředí pro podporu Intune u zákazníků Premier 
Jako zákazník Microsoft Premier aktuálně můžete používat portál Microsoft Premier Online (MPO) (premier.microsoft.com) a Intune v Azure (portal.azure.com) k vytváření žádostí o podporu pro Intune. Od 3. prosince 2018 si budete moct vytvářet žádosti o podporu jenom v Intune v Azure, pokud si budete chtít dál vylepšovat prostředí podpory Premier.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Po 3. prosinci nebudete moct vytvářet žádosti o podporu v MPO.  Když se o to pokusíte, zobrazí se vám výzva, kterou nebude možné zrušit, k přesměrování na Intune v Azure. Zde můžete vytvořit žádost o podporu, která se bude směrovat na podporu Microsoftu vyhrazenou pro Intune, k včasnému diagnostikování a vyřešení vašeho problému. Žádosti o podporu vytvořené v MPO nelze zobrazit na webu Azure Portal, takže byste měli vytváření žádosti o podporu v MPO zastavit.  

Pokud používáte hybridní správu mobilních zařízení (hybridní MDM) nebo spolusprávu, můžete nadále používat MPO k vytváření žádostí o podporu pro nástroj ConfigMgr, ale žádosti o podporu pro Intune vytvářejte pomocí webu Azure Portal. Připomínáme, že hybridní MDM je zastaralé a měli byste si co nejdříve naplánovat přechod na Intune v Azure. Další informace najdete v tématu o [přechodu z hybridní správy mobilních zařízení na Intune v Azure](https://aka.ms/hybrid_notification).

Všimněte si, že pouze uživatelé s rolí Globální správce, Správce služby Intune a Správce podpory služeb můžou vytvářet lístky podpory na webu Azure Portal.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
- Přestaňte vytvářet a spravovat všechny žádosti o podporu Intune pomocí portálu Microsoft Premier Online (MPO) a používejte k tomu Intune v Azure.  
- Upozorněte helpdesk a aktualizujte v případě potřeby dokumentaci.
- Pokud máte uživatele bez role Globální správce nebo Správce služby Intune, kteří momentálně vytvářejí žádosti o podporu v MPO, přiřaďte jim v Azure Active Directory roli Správce podpory služeb, aby mohli i nadále vytvářet lístky podpory na webu Azure Portal.
- Další informace a užitečné odkazy získáte kliknutím na Další informace.

#### <a name="additional-information"></a>Další informace
Další informace najdete v [blogovém příspěvku technické podpory pro Microsoft Intune](https://aka.ms/IntuneSupport_MPO_to_Azure).


### <a name="take-action-please-update-your-android-device-restriction-or-compliance-policy-password-settings-in-intune"></a>Provedení akce: Aktualizujte prosím v Intune nastavení hesla v zásadách omezení nebo dodržování předpisů u zařízení s Androidem
Intune pro zařízení s Androidem 4.4 nebo vyšším odebere dostupný typ hesla Výchozí ze zařízení (Výchozí nastavení zařízení). Vzhledem k rozdílům v platformách Android a výchozích nastaveních zařízení nakládá zařízení s těmito zásadami často jako s volitelnými. Abychom odstranili nejasnost, kdy je toto nastavení v Androidu vynucované, v nadcházející verzi toto nastavení odebereme. 
#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
- Pokud máte v úmyslu vyžadovat na zařízeních heslo, doporučujeme abyste místo použití typu Výchozí ze zařízení upravili profily vaší platformy Android tak, aby jasně vyjadřovaly požadovaný typ hesla.
- Pokud máte v úmyslu nechat koncového uživatele rozhodnout, jestli vytvořit heslo, vyberte tlačítko Nenakonfigurováno. Když toto nastavení z uživatelského rozhraní odeberete, ale je stále nastavené, při příští úpravě profilu budete vyzváni, abyste zvolili jinou hodnotu než Výchozí ze zařízení.
Jak se mám na tuto změnu připravit?
Zkontrolujte nastavení hesla ve vašem Androidu a v podnikových zásadách omezení a dodržování předpisů u zařízení s Androidem. Tato nastavení jsou pro Zásady dodržování předpisů uvedená v rámci Zabezpečení systému a pro Omezení zařízení v rámci nastavení Hesla zařízení nebo Pracovního profilu. Další informace obsahují odkaz na další podrobnosti a snímky obrazovek, které ukazují, kde se tato nastavení konfigurují.
#### <a name="additional-information"></a>Další informace
https://aka.ms/PasswordSettings 

### <a name="plan-for-change-change-password-at-next-auth-added-to-intune---1873216---"></a>Plánovaná změna: Do Intune přibude nastavení Změnit heslo při příštím ověření<!-- 1873216 -->
V zářijovém vydání služby se do Intune chystáme integrovat nové nastavení společnosti Apple **Změnit heslo při příštím ověření** určené pro zařízení s macOS ve verzi 10.13 a novější. Před uvedením tohoto nastavení nemůžou poskytovatelé řešení MDM ověřit, že heslo zařízení bylo změněno tak, aby vyhovovalo předpisům. Zásady konfigurace a dodržování předpisů v Intune pouze ověřují, zda je heslo zařízení při příští změně označeno jako vyhovující. Po přidání této nové funkce Apple obdrží uživatelé zařízení s macOS žádost o aktualizaci hesla i v případě, že jejich heslo odpovídá zásadám.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Tato změna se dotýká prostředí, kde se pomocí Intune uplatňují zásady pro zařízení s macOS, a prostředí s hybridní správou mobilních zařízení. S tímto novým nastavením **Změnit heslo při příštím ověření** od Applu teď Intune může při doručení zásady hesel vynutit od uživatelů aktualizaci hesla. Pokud blokujete firemní prostředky do doby, než bude zařízení označeno jako vyhovující, můžou mít koncoví uživatelé zablokovaný přístup k firemním prostředkům, jako je e-mail nebo sharepointové weby, dokud si neresetují heslo. V budoucnu veškeré aktualizace zásad konfigurace a dodržování předpisů týkající se hesel vynutí u cílových uživatelů aktualizaci hesla.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Informujte váš tým technické podpory. Pokud tuto zásadu pro zařízení s macOS nechcete vynucovat, doporučujeme zrušit přiřazení stávajících zásad pro macOS nebo je odstranit. Z průzkumu mezi zákazníky vyplývá, že většiny z nich se tato změna nedotkne. Většina koncových uživatelů si po přijetí žádosti o registraci s heslem aktualizuje heslo, případně jej resetuje, aby vyhovovalo podmínkám.

### <a name="plan-for-change-intune-moving-to-tls-12"></a>Plánovaná změna: Přechod Intune na TLS 1.2
Od 31. října 2018 bude Intune podporovat protokol TLS (Transport Layer Security) ve verzi 1.2, který zajistí nejlepší šifrování ve své třídě, aby byla naše služba bezpečnější a v souladu s jinými službami Microsoftu, jako je Microsoft Office 365. Office tuto změnu oznámil v MC128929.

Portál společnosti také začne podporovat protokol TLS 1.2 31. října 2018.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Od 31. října 2018 už nebude Intune podporovat protokol TLS ve verzích 1.0 a 1.1. Všechny kombinace klient-server a prohlížeč-server by měly používat protokol TLS ve verzi 1.2, aby nedošlo k potížím s připojením k Intune. Tato změna ovlivní zařízení koncových uživatelů, které už Intune nepodporují, ale stále přijímají prostřednictvím Intune zásady, a které nemohou protokol TLS verze 1.2 používat. Patří sem například zařízení se systémem Android 4.3 a starší. Seznam ovlivněných zařízení a prohlížečů najdete níže v části Další informace.

Pokud budete mít po 31. říjnu 2018 problém s použitím staré verze protokolu TLS, bude součástí řešení aktualizace na protokol TLS 1.2 nebo přechod na zařízení, které tento protokol podporuje.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Doporučujeme vám proaktivně ve vašich prostředích rušit závislosti na protokolech TLS 1.0 a 1.1 a tam, kde je to možné, zakázat protokoly TLS 1.0 a 1.1 na úrovni operačního systému. Začněte plánovat migraci na protokol TLS 1.2 už dnes. Přečtěte si níže uvedený blogový příspěvek o podpoře se seznamem zařízení, které Intune aktuálně nepodporuje, ale přesto mohou přijímat zásady, a které nebudou moct prostřednictvím protokolu TLS verze 1.2 komunikovat. Dané koncové uživatele budete muset upozornit, že přijdou o přístup k podnikovým prostředkům.

**Další informace**: [Přechod Intune na šifrování TLS 1.2](https://blogs.technet.microsoft.com/intunesupport/2018/06/05/intune-moving-to-tls-1-2-for-encryption/)


### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Plánovaná změna: Ke správě MDM se teď používá Intune v Azure <!-- 1227338 -->
Před více než rokem jsme oznámili vydání [Intune ve verzi Public Preview na platformě Azure](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) a pak před šesti měsíci [obecnou dostupnost nového prostředí pro správu](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) Intune. Od 31. srpna 2018 vypínáme správu mobilních zařízení (MDM) v klasické konzole Silverlight pro zákazníky, kteří používají Intune samostatně. Místo toho můžete ke svým potřebám MDM používat [Intune v Azure](https://aka.ms/Intune_on_Azure). Pokud k MDM ještě používáte klasickou konzolu, přestaňte ji prosím používat a seznamte se s Intune v Azure. Neočekáváme, že tato změna bude mít nějaký dopad na koncové uživatele. Klasická správa počítačů zůstane v Silverlightu. Další informace o této změně a o jejím dopadu na vás najdete [tady](https://aka.ms/Intune_on_Azure_mdm).

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple bude vyžadovat aktualizace ATS (Application Transport Security) <!--748318-->
Apple oznámil, že začne vynucovat specifické požadavky na ATS (Application Transport Security). ATS se používá k vynucení vyššího zabezpečení veškeré komunikace aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune, kteří používají aplikace Portál společnosti pro iOS. S podrobnostmi vás seznámíme na [blogu podpory Intune](https://aka.ms/compportalats).



## <a name="see-also"></a>Viz také
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](https://www.microsoft.com/cloud-platform/roadmap)
* [Co je nového v uživatelském rozhraní Portálu společnosti](whats-new-app-ui.md)
* [Novinky v předchozích měsících](whats-new-archive.md)
