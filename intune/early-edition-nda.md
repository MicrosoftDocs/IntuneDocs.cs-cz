---
title: Časná edice
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0f6447f4a5cfb2638278a59414e83f744adb8c81
ms.sourcegitcommit: ed97b68f08c1a8469f0b45bc1c839a0b5f5c71e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/18/2018
ms.locfileid: "45978259"
---
# <a name="the-early-edition-for-microsoft-intune---september-2018"></a>Časná edice Microsoft Intune – září 2018

> [!Note]
> Upozornění na dohodu o mlčenlivosti (NDA): Následující změny v Intune jsou ve vývoji. Tyto informace jsou sdíleny ve velmi omezeném rozsahu a platí pro ně dohoda o mlčenlivosti (NDA). Nepublikujte žádné z těchto informací na sociálních sítích nebo veřejných webech, jako jsou Twitter, UserVoice, Reddit apod. 

**Časná edice** poskytuje seznam funkcí, sdílený na základě dohody o mlčenlivosti (NDA), které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány v omezené míře a můžou podléhat změnám. Tyto informace netweetujte, nepublikujte na webu UserVoice ani jinak nesdílejte mimo vaši společnost. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a můžou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moct zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se na příslušný kontakt pro skupinu produktů společnosti Microsoft.

Tato stránka se pravidelně aktualizuje. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune na portálu Azure Portal

<!-- 1809 start -->

### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices-----1248496----"></a>Přístup uživatelského účtu k aplikacím Intune na spravovaných zařízeních s Androidem a iOSem <!-- ! 1248496  -->

Jako správce Microsoft Intune můžete řídit, jaké uživatelské účty budou přidané do aplikací Microsoft Office na spravovaných zařízeních. Budete moct omezit přístup jenom na uživatelské účty povolené organizace a zablokovat osobní účty zaregistrovaných zařízení. 

### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10----1333668---"></a>Vytvoření přípon DNS v konfiguračních profilech sítě VPN na zařízeních s Windows 10 <!-- 1333668 -->
Při vytváření profilu konfigurace zařízení v síti VPN (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** Platforma > **VPN** pro typ profilu), zadáváte nastavení DNS. V Intune můžete zadat více **přípon DNS**. Pokud použijete přípony DNS, můžete k vyhledání síťového prostředku použít jeho krátký název místo plně kvalifikovaného názvu domény (FQDN). V této aktualizaci můžete v Intune změnit pořadí přípon DNS.
Seznam aktuálních nastavení DNS je v [nastavení sítě VPN ve Windows 10](vpn-settings-windows-10.md#dns-settings).
Platí pro: zařízení s Windows 10

### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Podpora neustále aktivních pracovních profilů sítě VPN pro Android Enterprise <!-- 1333705 -->
Neustále aktivní připojení VPN můžete použít na zařízeních s Androidem Enterprise, která používají spravované pracovní profily. Neustále aktivní připojení VPN zůstávají ve spojení nebo se ihned znovu připojí, jakmile uživatel odemkne zařízení, zařízení se restartuje nebo se změní bezdrátová síť. Připojení také můžete přepnout do „zamčeného“ režimu, který blokuje veškerý síťový provoz, dokud není připojení VPN zase aktivní.
Nastavení neustále aktivního připojení VPN najdete tady: **Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Android Enterprise** pro danou platformu > **Omezení zařízení** v části **Jen pracovní profil** pro typ profilu > **Možnosti připojení**. 

### <a name="outlook-for-ios-and-android-app-configuration-policy---1828527---"></a>Zásada konfigurace aplikace Outlook pro iOS a Android <!--1828527 -->
Můžete také vytvořit zásadu konfigurace pro aplikaci Outlook pro iOS a Android. Další nastavení konfigurace budou přidána, jakmile je povolíte Outlooku pro iOS a Android.

###  <a name="windows-line-of-business-lob-app-file-extensions----1884873---"></a>Přípony souborů obchodní aplikace pro Windows <!-- 1884873 -->
K příponám souborů obchodních aplikací pro Windows patří *.msi*, *.appx*, *.appxbundle*, *.msix* a *.msixbundle*. V Microsoft Intune můžete aplikaci přidat, když vyberete **Klientské aplikace** > **Aplikace** > **Přidat**. Zobrazí se podokno **Přidat aplikaci**, ve kterém můžete vybrat **typ aplikace**. V případě obchodních aplikací pro Windows vyberte jako typ aplikace **Obchodní aplikace**, vyberte **Soubor balíčku aplikace** a pak zadejte instalační soubor s příslušnou příponou.

### <a name="remotely-lock-noncompliant-devices----2064495---"></a>Vzdálené zamčení nevyhovujících zařízení <!-- 2064495 -->
Pokud zařízení nevyhovuje, můžete vytvořit akci, která vychází ze zásady dodržování předpisů a která zařízení vzdáleně zamkne. V Intune vyberte **Dodržování předpisů zařízením** a vytvořte novou nebo vyberte některou ze stávajících zásad. Vyberte **Akce při nedodržení předpisů** > **Přidat** a zvolte, že chcete zařízení vzdáleně zamknout.
Podporované platformy: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8.1 nebo novější 

### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Nastavení Intune APP pro přenos dat na zařízeních s iOS zaregistrovaných v MDM <!-- 2244713 -->
Ovládání nastavení Intune APP pro přenos dat na zařízeních s iOS zaregistrovaných v MDM můžete oddělit od zadání identity registrovaného uživatele. Správci, kteří nepoužívají aplikaci IntuneMAMUPN, nezaznamenají změnu chování. Pokud je tato funkce k dispozici, musí správci, kteří k řízení chování při přenosech dat na registrovaných zařízeních používají Intune MAMUPN, zkontrolovat nové nastavení a podle potřeby aktualizovat nastavení APP.

### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Použití předsdíleného klíče v profilu sítě Wi-Fi ve Windows 10 <!-- 2662938 -->
K ověření konfiguračního profilu sítě Wi-Fi pro Windows 10 můžete použít předsdílený klíč (PSK) s protokolem zabezpečení WPA/WPA2-osobní.
Pokud chcete použít předsdílený klíč, musíte v současnosti importovat profil Wi-Fi nebo vytvořit vlastní profil. Seznam aktuálních nastavení je v [nastavení sítě Wi-Fi pro Windows 10](wi-fi-settings-windows.md). 

### <a name="app-protection-policy-app-settings-for-web-data----2662995-eeready---"></a>Nastavení zásady ochrany aplikací (APP) pro webová data <!-- 2662995 eeready -->
Nastavení zásad ochrany aplikací (APP) pro webový obsah na zařízeních s Androidem a iOS bude aktualizované, aby lépe pracovalo s webovými odkazy http a https a také s přenosy dat prostřednictvím univerzálních odkazů iOS a odkazů aplikací pro Android.  

### <a name="autopilot-device-sync-frequency-increasing-to-every-12-hours----2753673---"></a>Frekvence synchronizace zařízení Autopilot zkrácená na 12 hodin <!-- 2753673 -->
Zařízení Autopilot se budou synchronizovat každých 12 hodin místo původních 24 hodin.

### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Použití profilu Autopilotu u zaregistrovaných zařízení s Windows 10, která nejsou zaregistrovaná v Autopilotu <!-- 1558983 -->
Profily Autopilotu můžete použít u zaregistrovaných zařízení s Windows 10, která nejsou zaregistrovaná do Autopilotu. V profilu Autopilotu zvolte možnost **Převést všechna cílová zařízení na AutoPilot**, abyste mohli k automatické registraci zařízení bez Autopilotu použít službu nasazení Autopilotu. Vyřízení registrace trvá 48 hodin. Jakmile bude registrace zařízení zrušena a zařízení bude resetováno, Autopilot zajistí registraci. 

### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564--"></a>Vytvoření více profilů stránky o stavu registrace a jejich přiřazení skupinám Azure AD <!-- 2526564-->
Pro skupiny uživatelů Azure AAD můžete vytvořit více profilů stránky o stavu registrace, které jim můžete přiřadit.

### <a name="intune-landing-page-updates-and-node-rename---2867309---"></a>Aktualizace vstupní stránky Intune a přejmenování uzlu <!--2867309 -->
K aktualizacím vstupní stránky Intune patří i nové a změněné monitorovací dlaždice a grafy pro lepší znázornění dat. Uzel **Mobilní aplikace** se mění na **Klientské aplikace**.

### <a name="increased-end-user-access-using-the-company-portal-app----772203---"></a>Větší přístup koncových uživatelů v aplikaci Portál společnosti <!-- 772203 -->
Koncoví uživatelé budou mít přístup ke klíčovým akcím účtu, jako je resetování hesla nebo profil AAD, z aplikace Portál společnosti.

### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>Vydání certifikátů SCEP zařízením bez uživatele <!-- 1744554 -->
Certifikáty se v současnosti vydávají jenom uživatelům. Certifikáty SCEP budete moct vydat i zařízením, včetně zařízení bez uživatelů, jako jsou terminály (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** pro platformu > **Certifikát SCEP** pro profil). Další aktualizace:
- Vlastnost **Subjekt** v profilu SCEP je nyní vlastní textové pole, které může obsahovat nové proměnné. 
- Vlastnost **Alternativní název subjektu (SAN)** v profilu SCEP má nyní formát tabulky a může obsahovat nové proměnné. Správce může do tabulky přidat atribut a vyplnit hodnotu vlastního textového pole. Alternativní název subjektu (SAN) podporuje následující atributy: 
  - DNS
  - E-mailová adresa
  - Hlavní název uživatele (UPN) Tyto nové proměnné můžete přidat jako statický text do textového pole s vlastní hodnotou. Například atribut DNS můžete přidat jako `DNS = {{AzureADDeviceId}}.domain.com`.
  > [!NOTE]
  > Ve statickém textu alternativního názvu subjektu (SAN) nejdou použít složené závorky, středníky ani svislé čáry (|). Do složených závorek můžete uzavřít jenom jednu z nových proměnných certifikátu zařízení, aby mohla být přijata jako `Subject` nebo `Subject alternative name`. Nové proměnné certifikátu zařízení:  
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



<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token Apple VPP používá jiný produkt MDM <!-- 1488946 -->
Intune rozpozná situaci, kdy se token programu hromadných nákupů (VPP) společnosti Apple používá v Intune a zároveň v jiném produktu MDM, a zobrazí podrobnosti.

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>Zobrazuje se číslo verze iOS a číslo buildu <!-- 1892471 -->
V části **Dodržování předpisů zařízení** > **Dodržování předpisů zařízení** se zobrazí verze operačního systému iOS. V budoucí aktualizaci se zobrazí také číslo buildu.
Při vydání aktualizací zabezpečení společnost Apple obvykle ponechává stávající číslo verze, ale aktualizuje číslo buildu. Když znáte číslo buildu, jednoduše ověříte, jestli je nainstalována aktualizace řešící ohrožení zabezpečení.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Vyřazená zařízení na řídicím panelu Dodržování předpisů zařízením <!-- 1981119 -->
V budoucí aktualizaci se z řídicího panelu Dodržování předpisů zařízením odeberou vyřazená zařízení. Změní se tím číselné údaje týkající se dodržování předpisů.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Změna v procesu aktualizace pro místní konektory <!-- 2277554 -->
Na základě zpětné vazby od zákazníků se změní způsob, jak se aktualizují místní konektory. Po prvotní instalaci místního konektoru budou aktualizace probíhat automaticky. Tato změna začne s novým konektor certifikátu PFX pro Microsoft Intune a následně bude zavedena u dalších typů místních konektorů. 

### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224-eeready---"></a>Vylepšení profilu zařízení s beznabídkovým režimem se systémem Windows 10 a novějším na webu Azure Portal <!-- 2748224 eeready -->
Vylepšení konfiguračního profilu zařízení s beznabídkovým režimem s Windows 10 (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** pro platformu > **Beznabídkový režim (Preview)** pro typ profilu): 
- V současnosti můžete na stejném zařízení vytvářet více profilů beznabídkového režimu. Po této aktualizaci bude Intune u každého zařízení podporovat jenom jeden profil. Pokud přesto potřebujete více profilů beznabídkového režimu, můžete použít vlastní identifikátor URI.
V profilu **Beznabídkový režim s více aplikacemi** můžete vybrat velikost dlaždice aplikace a určit pořadí **rozložení nabídky Start** v mřížce aplikace. Pokud chcete provádět vlastní úpravy většího rozsahu, pokračujte k odeslání souboru XML.
- Nastavení aplikace Kiosk Browser se přesouvají do nastavení **Veřejný terminál**. V současnosti má nastavení **Kiosk Web Browser** na webu Azure Portal vlastní kategorii.
Platí pro: Windows 10 a novější

<!-- 1807 start -->

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Vylepšené prostředí aplikace Portál společnosti pro správce registrace zařízení <!-- 675800 -->
Když se správce registrace zařízení přihlásí k aplikaci Portál společnosti pro Windows, bude v této aplikaci uvedeno jen jeho aktuální spuštěné zařízení. Tímto vylepšením se omezí vypršení časového limitu, ke kterým dříve docházelo, když se aplikace snažila načíst všechna zařízení zaregistrovaná správcem.  

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Kontrola Configuration Manageru z hlediska dodržování předpisů <!-- 2192052 -->
Budoucí aktualizace bude obsahovat nové nastavení pro dodržování předpisů System Center Configuration Manageru (**Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**  > **Windows 10**). Configuration Manager bude posílat signály funkci dodržování předpisů v Intune. V Intune můžete nastavit požadavek, aby všechny signály Configuration Manageru hlásily vyhovující stav.

Můžete například vyžadovat, aby v zařízeních byly nainstalované všechny aktualizace softwaru. V Configuration Manageru má tento požadavek stav Nainstalováno. Pokud některé programy v zařízení budou v neznámém stavu, bude se zařízení v Intune považovat za nevyhovující předpisům.

Platí pro Windows 10 a novější.

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Upozornění na vypršení platnosti tokenu VPP nebo docházející licence pro aplikaci Portál společnosti <!-- 2237572 -->
Jestliže pomocí programu VPP (Volume Purchase Program) předběžně zřizujete portál společnosti během registrace do programu DEP, Intune vás upozorní, pokud se bude blížit konec platnosti tokenu VPP nebo pokud bude docházet počet licencí pro aplikaci Portál společnosti.

### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Nastavení dalšího zabezpečení pro Instalační službu systému Windows <!-- 2282430 -->
Uživatelům budete moct povolit, aby ovládali instalaci aplikací. Pokud je tato možnost povolená, instalace, které by se jinak kvůli narušení zabezpečení zastavily, budou moct pokračovat. Instalační službu systému Windows budete moct nastavit tak, aby při instalaci libovolné aplikace do systému používala zvýšenou úroveň oprávnění. Dále budete moct povolit, aby se položky WIP (Windows Information Protection) indexovaly a metadata o nich se ukládala do nešifrovaného umístění. Pokud je tato zásada zakázaná, chráněné položky WIP se nebudou indexovat a ve výsledcích v Cortaně nebo v Průzkumníkovi souborů se nezobrazí. Funkčnost těchto možností bude ve výchozím nastavení zakázaná. 

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Nastavením zásad ochrany aplikací v iOSu se dají zablokovat klávesnice jiných výrobců <!-- 1248481 -->
Na zařízeních s iOSem budou moct správci Intune zablokovat použití klávesnic jiných výrobců pro přístup k datům organizace z aplikací chráněných zásadami. Když budou nastavené Zásady ochrany aplikací (APP) k blokování klávesnic jiných výrobců, uživatelům zařízení se při první interakci s firemními daty pomocí klávesnice jiného výrobce zobrazí zpráva. Všechny jiné možnosti než nativní klávesnice budou zablokované a uživatelům zařízení se nezobrazí. Uživatelům se dialog se zprávou zobrazí jenom jednou. 

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Jazykové sady Office 365 Pro Plus <!-- 1833450 -->
Jako správce Intune budete moct nasadit další jazyky pro aplikace Office 365 Pro Plus spravované prostřednictvím Intune. Seznam dostupných jazyků zahrnuje **Typ** jazykové sady (Základní, Částečná a Kontrola pravopisu). Na portálu Azure Portal vyberte **Microsoft Intune** > **Mobilní aplikace** > **Aplikace** > **Přidat**. V okně **Přidat aplikaci** v seznamu **Typ aplikace** vyberte v části **Sada Office 365** možnost **Windows 10**. V okně **Nastavení sady aplikací** vyberte **Jazyky**.

<!-- 1805 start -->

### <a name="require-non-biometric-after-specified-timeout----1506985---"></a>Po uplynutí časového limitu se vyžaduje nebiometrická identifikace <!-- 1506985 --> 

Po uplynutí časového limitu určeného správcem bude Intune požadovat nebiometrický kód PIN. Služba tak lépe zabezpečí aplikace s podporou Správy mobilních aplikací (MAM), protože omezí použití biometrické identifikace pro přístup k firemním datům. Toto nastavení bude mít vliv na uživatele, kteří pro přístup k aplikacím s podporou APP/MAM budou používat Touch ID (iOS), Face ID (iOS), Biometriku Androidu nebo jiné budoucí způsoby biometrického ověřování. S tímto nastavením budou mít správci Intune přesnější kontrolu nad přístupem uživatelů, takže budou moct vyloučit případy, kdy zařízení s více otisky prstů nebo jinými biometrickými metodami přístupu může odhalit firemní data nesprávnému uživateli. Na portálu Azure Portal otevřete **Microsoft Intune**. Vyberte **Mobilní aplikace** > **Zásady ochrany aplikací** > **Přidat zásadu** > **Nastavení**. Najděte část **Přístup** s konkrétními nastaveními.

<!-- 1803 start -->

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Aktualizace prostředí nápovědy a odeslání názoru v aplikaci Portál společnosti pro Android <!--1631531 -->

Budeme aktualizovat prostředí nápovědy a odeslání názoru v aplikaci Portál společnosti pro Android, aby bylo v souladu s osvědčenými postupy pro aplikace pro Android. Během příštích pár měsíců budeme aktualizovat aplikaci Portál společnosti pro Android, abychom rozdělili položku nabídky **Nápověda a odeslání názoru** na samostatné položky **Nápověda** a **Odeslat názor**. Stránka **Nápověda** bude obsahovat sekci **Nejčastější dotazy** a tlačítko **E-mailová podpora**, které koncovým uživatelům umožní odeslat protokoly do Microsoftu a podpoře společnosti zaslat e-mail s popisem problému. **Odeslat názor** uživatele provede standardním odesláním zpětné vazby Microsoftu. Uživateli se zobrazí výzva, aby zvolil „Něco se mi líbí“, „Něco se mi nelíbí“ nebo „Mám nápad“.



<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Sdělení

V současné době nejsou aktivní žádná sdělení.

### <a name="see-also"></a>Viz taky
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).



