---
title: Časná edice
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 72585982cd27962981f581a99f0ea361642df0ee
ms.sourcegitcommit: ba0699cc351954960b222223c60c4ecd50edc829
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49652134"
---
# <a name="the-early-edition-for-microsoft-intune---october-2018"></a>Časná edice Microsoft Intune – říjen 2018

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

<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Použití Microsoftem doporučených nastavení se standardními hodnotami zabezpečení <!-- 2055484 -->
Intune se integruje s dalšími službami, které se zaměřují na zabezpečení, včetně Ochrany ATP v programu Windows Defender a Ochrany ATP v Office 365. Zákazníci požadují ve službách Microsoft 365 společnou strategii a soudržnější sadu ucelených bezpečnostních pracovních postupů. Naším cílem je srovnat strategie tak, abychom mohli vytvářet řešení přemosťující operace zabezpečení a běžné úlohy správy. V Intune se snažíme tohoto cíle dosáhnout prostřednictvím publikování sady Standardních hodnot zabezpečení doporučených Microsoftem (**Intune** > **Standardní hodnoty zabezpečení**).  Správce bude moct vytvářet zásady zabezpečení přímo z těchto standardních hodnot a potom je nasazovat svým uživatelům. Doporučení osvědčených postupů může upravit tak, aby vyhovovala potřebám jeho organizace. Intune zajišťuje, že zařízení zůstávají v souladu s těmito standardními hodnotami, a upozorní správce, pokud uživatelé nebo zařízení tyto hodnoty nedodržují.

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices----1048100---"></a>Podpora Autopilotu pro zařízení připojená k hybridní službě Azure Active Directory <!-- 1048100 -->
Zařízení připojená k hybridní službě Azure Active Directory si budete moct nastavit pomocí Autopilotu. Zařízení musí být připojená do vaší podnikové sítě, aby mohla použít hybridní funkci Autopilotu.

### <a name="scope-tags-for-apps---1081941---"></a>Značky oboru pro aplikace <!--1081941 -->
Budete moct vytvářet značky oboru a omezovat s jejich pomocí přístup k prostředkům Intune. Přidejte značku oboru k přiřazení role a poté přidejte značku oboru ke konfiguračnímu profilu. Daná role bude mít přístup pouze k prostředkům s konfiguračními profily, které mají odpovídající značky oboru (nebo žádnou značku oboru).
Pokud chcete vytvořit značku oboru, vyberte **Role Intune** > **Obor (značky)** > **Vytvořit**.
Značku oboru přidáte k přiřazení role tak, že zvolíte **Role Intune** > **Všechny role** > **Správce zásad a profilů** > **Přiřazení** > **Obor (značky)**.
Ke konfiguračnímu profilu přidáte značku oboru tak, zvolíte **Konfigurace zařízení** > **Profily** > vyberete profil > **Vlastnosti** > **Obor (značky)**.

### <a name="tenant-health-dashboard----1124854---"></a>Řídicí panel Stav tenanta <!-- 1124854 -->
Stránka Stav tenanta v Intune vám poskytne informace o stavu tenanta na jednom místě. Stránka je rozdělená do 4 částí:  
- **Podrobnosti o tenantovi**: obsahuje informace, jako je například autorita MDM, celkový počet zařízení zaregistrovaných ve vašem tenantovi a počet vašich licencí. Tato část také obsahuje aktuální vydanou verzi služby pro vašeho tenanta.
- **Stav konektoru**: obsahuje informace pro nakonfigurované konektory, jako je třeba Apple VPP, Windows Store pro firmy a konektory Certificate Connectors. Na základě jejich aktuálního stavu jsou konektory označené jako *V pořádku*, *Upozornění* nebo *Není v pořádku*.
- **Stav služby Intune**: obsahuje aktivní incidenty nebo výpadky vašeho tenanta. Informace v této části se načítají přímo z centra zpráv Office ([https://portal.office.com](https://portal.office.com)).
- **Novinky v Intune**: obsahuje aktivní zprávy pro vašeho tenanta, které zahrnují například oznámení, že váš tenant obdržel nejnovější funkce Intune. Informace v této části se načítají přímo z centra zpráv Office ([https://portal.office.com](https://portal.office.com)).

### <a name="enrollment-abandonment-report----1382924---"></a>Sestava opuštění registrace <!-- 1382924 -->
Nová sestava, která poskytuje podrobné informace o opuštěných registracích, bude k dispozici v části **Registrace zařízení** > **Monitorování**.

### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Nasazené zásady WIP bez registrace uživatele <!-- 1434452 -->
Zásady Windows Information Protection (WIP) budou k dispozici pro nasazení, aniž by se vyžadovalo, aby si uživatelé MDM zaregistrovali svá zařízení s Windows 10. Tato konfigurace umožňuje společnostem chránit jejich podnikové dokumenty na základě konfigurace WIP a zároveň umožňuje uživatelům uchovat si správu svých vlastních zařízení s Windows. Jakmile jsou dokumenty chráněny zásadami WIP, mohou být chráněná data selektivně vymazána správcem služby Intune. Výběrem uživatele a zařízení a odesláním žádosti o vymazání se veškerá data chráněná prostřednictvím zásad WIP stanou nepoužitelnými. V Intune na portálu Azure Portal vyberte **Mobilní aplikace** > **Selektivní vymazání aplikace**.


### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Přidání vlastní firemní image pro aplikaci Portál společnosti <!-- 1916266 -->
Jako správce služby Microsoft Intune budete mít možnost nahrát vlastní firemní image, která se bude zobrazovat jako obrázek pozadí na stránce profilu uživatele v aplikaci Portál společnosti. Další informace o konfiguraci aplikace Portál společnosti najdete v tématu [Konfigurace aplikace Portál společnosti služby Microsoft Intune](company-portal-app.md).

### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Seskupení zařízení zaregistrovaných ve Windows Autopilotu podle ID korelátoru <!-- 2075110 -->
Intune bude podporovat seskupování zařízení s Windows podle ID korelátoru, pokud budou zaregistrovaná s použitím [Autopilotu pro existující zařízení](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) v nástroji Configuration Manager. ID korelátoru je parametr konfiguračního souboru Autopilotu. Intune automaticky nastaví [atribut enrollmentProfileName zařízení služby Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) tak, aby odpovídal nastavení OfflineAutopilotprofile-\<ID korelátoru\>. Umožní se tím, aby se pro offline registrace Autopilotu vytvořily libovolné dynamické skupiny Azure AD na základě ID korelátoru prostřednictvím atributu enrollmentprofileName. 


### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Podpora iOS 12 OAuth v e-mailových profilech systému iOS <!--2155106 -->
E-mailové profily iOS služby Intune budou podporovat iOS 12 OAuth. Pokud chcete tuto funkci zobrazit, vyberte **Intune** > **Konfigurace zařízení** > **Profily** > **Vytvořit profil**  > **OAuth**. Pokud je toto nastavení zapnuté, stanou se dvě věci:
1. Zařízením, která už jsou zacílená, se vystaví nový profil.
2. Koncovým uživatelům se znovu zobrazí výzva k zadání přihlašovacích údajů.

### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nové výchozí nastavení Požadovaný typ hesla pro Android, Android Enterprise <!-- 2649963 -->
Když vytvoříte nové zásady dodržování předpisů (**Intune** > **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu** > **Android** nebo **Android Enterprise** pro Platforma > Zabezpečení systému), výchozí hodnota pro **Požadovaný typ hesla** se změní: Aktuální výchozí nastavení: Výchozí ze zařízení Nová výchozí hodnota: Aspoň číslice Platí pro: Android, Android Enterprise

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522---"></a>Přiřazení profilů Autopilotu virtuální skupině Všechna zařízení <!--2715522 -->
Profily Autopilotu budete moct přiřadit virtuální skupině Všechna zařízení. Uděláte to tak, že vyberete **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > vyberte profil > **Přiřazení** > v části **Přiřadit k** vyberte **Všechna zařízení**.

### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Nová funkce podmínek použití služby Azure Active Directory <!-- 2870393 -->
Azure Active Directory bude mít funkci podmínek použití, kterou budete moct využít místo stávajících podmínek a ujednání služby Intune. Funkce podmínek použití služby Azure AD poskytuje větší flexibilitu ohledně toho, které podmínky a kdy se mají zobrazovat, lepší podporu lokalizace, větší kontrolu nad tím, jak se podmínky vykreslují, a vylepšené generování sestav. Funkce podmínek použití služby Azure AD vyžaduje Azure Active Directory Premium P1, která je také součástí sady Enterprise Mobility + Security E3.


### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Intune bude udržovat lokalizovaný jazyk Office při aktualizaci Office na počítačích koncových uživatelů <!-- 2971030 -->
Když Intune nainstaluje Office na počítače koncových uživatelů, získají koncoví uživatelé automaticky stejné jazykové sady, které měli s předchozími instalacemi Office .MSI. 

<!-- 1809 start -->  

### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Nastavení Intune APP pro přenos dat na zařízeních s iOS zaregistrovaných v MDM <!-- 2244713 -->
Ovládání nastavení Intune APP pro přenos dat na zařízeních s iOS zaregistrovaných v MDM můžete oddělit od zadání identity registrovaného uživatele. Správci, kteří nepoužívají aplikaci IntuneMAMUPN, nezaznamenají změnu chování. Pokud je tato funkce k dispozici, musí správci, kteří k řízení chování při přenosech dat na registrovaných zařízeních používají Intune MAMUPN, zkontrolovat nové nastavení a podle potřeby aktualizovat nastavení APP.

### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Použití předsdíleného klíče v profilu sítě Wi-Fi ve Windows 10 <!-- 2662938 -->
K ověření konfiguračního profilu sítě Wi-Fi pro Windows 10 můžete použít předsdílený klíč (PSK) s protokolem zabezpečení WPA/WPA2-osobní.
Pokud chcete použít předsdílený klíč, musíte v současnosti importovat profil Wi-Fi nebo vytvořit vlastní profil. Seznam aktuálních nastavení je v [nastavení sítě Wi-Fi pro Windows 10](wi-fi-settings-windows.md). 

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Nastavení zásady ochrany aplikací (APP) pro webová data <!-- 2662995 -->
Nastavení zásad ochrany aplikací (APP) pro webový obsah na zařízeních s Androidem a iOS bude aktualizované, aby lépe pracovalo s webovými odkazy http a https a také s přenosy dat prostřednictvím univerzálních odkazů iOS a odkazů aplikací pro Android.  

### <a name="autopilot-device-sync-frequency-increasing-to-every-12-hours----2753673---"></a>Frekvence synchronizace zařízení Autopilot zkrácená na 12 hodin <!-- 2753673 -->
Zařízení Autopilot se budou synchronizovat každých 12 hodin místo původních 24 hodin.

### <a name="intune-landing-page-updates-and-node-rename---2867309---"></a>Aktualizace vstupní stránky Intune a přejmenování uzlu <!--2867309 -->
K aktualizacím vstupní stránky Intune patří i nové a změněné monitorovací dlaždice a grafy pro lepší znázornění dat. Uzel **Mobilní aplikace** se mění na **Klientské aplikace**.

### <a name="increased-end-user-access-using-the-company-portal-app----772203---"></a>Větší přístup koncových uživatelů v aplikaci Portál společnosti <!-- 772203 -->
Koncoví uživatelé budou mít přístup ke klíčovým akcím účtu, jako je resetování hesla nebo profil AAD, z aplikace Portál společnosti.  

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

<!-- 1807 start -->

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Vylepšené prostředí aplikace Portál společnosti pro správce registrace zařízení <!-- 675800 -->
Když se správce registrace zařízení přihlásí k aplikaci Portál společnosti pro Windows, bude v této aplikaci uvedeno jen jeho aktuální spuštěné zařízení. Tímto vylepšením se omezí vypršení časového limitu, ke kterým dříve docházelo, když se aplikace snažila načíst všechna zařízení zaregistrovaná správcem.  

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Kontrola Configuration Manageru z hlediska dodržování předpisů <!-- 2192052 -->
Budoucí aktualizace bude obsahovat nové nastavení pro dodržování předpisů System Center Configuration Manageru (**Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**  > **Windows 10**). Configuration Manager bude posílat signály funkci dodržování předpisů v Intune. V Intune můžete nastavit požadavek, aby všechny signály Configuration Manageru hlásily vyhovující stav.

Můžete například vyžadovat, aby v zařízeních byly nainstalované všechny aktualizace softwaru. V Configuration Manageru má tento požadavek stav Nainstalováno. Pokud některé programy v zařízení budou v neznámém stavu, bude se zařízení v Intune považovat za nevyhovující předpisům.

Platí pro Windows 10 a novější.

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Upozornění na vypršení platnosti tokenu VPP nebo docházející licence pro aplikaci Portál společnosti <!-- 2237572 -->
Jestliže pomocí programu VPP (Volume Purchase Program) předběžně zřizujete portál společnosti během registrace do programu DEP, Intune vás upozorní, pokud se bude blížit konec platnosti tokenu VPP nebo pokud bude docházet počet licencí pro aplikaci Portál společnosti.

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Nastavením zásad ochrany aplikací v iOSu se dají zablokovat klávesnice jiných výrobců <!-- 1248481 -->
Na zařízeních s iOSem budou moct správci Intune zablokovat použití klávesnic jiných výrobců pro přístup k datům organizace z aplikací chráněných zásadami. Když budou nastavené Zásady ochrany aplikací (APP) k blokování klávesnic jiných výrobců, uživatelům zařízení se při první interakci s firemními daty pomocí klávesnice jiného výrobce zobrazí zpráva. Všechny jiné možnosti než nativní klávesnice budou zablokované a uživatelům zařízení se nezobrazí. Uživatelům se dialog se zprávou zobrazí jenom jednou. 

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



