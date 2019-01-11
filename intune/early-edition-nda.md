---
title: Časná edice – Microsoft Intune
titlesuffix: ''
description: Časná edice Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 0efc84da6a9efb594600b9ca33aa5eb7622c8101
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203429"
---
# <a name="the-early-edition-for-microsoft-intune---january-2019"></a>Časná edice Microsoft Intune – leden 2019

> [!Note]
> Smlouvu NDA pro oznámení: Následující změny v Intune jsou ve vývoji. Tyto informace jsou sdíleny ve velmi omezeném rozsahu a platí pro ně dohoda o mlčenlivosti (NDA). Nepublikujte žádné z těchto informací na sociálních sítích nebo veřejných webech, jako jsou Twitter, UserVoice, Reddit apod. 

**Časná edice** poskytuje seznam funkcí, sdílený na základě dohody o mlčenlivosti (NDA), které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány v omezené míře a můžou podléhat změnám. Tyto informace netweetujte, nepublikujte na webu UserVoice ani jinak nesdílejte mimo vaši společnost. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a můžou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moct zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se na příslušný kontakt pro skupinu produktů společnosti Microsoft.

Tato stránka se pravidelně aktualizuje. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune na portálu Azure Portal

<!-- 1901 start -->

### <a name="android-enterprise-apps----1352553----"></a>Aplikace Android Enterprise <!-- 1352553  -->
Budete moct odstranit spravované aplikace Google Play v Microsoft Intune. Pokud chcete odstranit spravovanou aplikaci služby Google Play, se otevře Microsoft Intune v Azure portal a vyberte **klientské aplikace** > **aplikace**. Ze seznamu aplikací vyberte symbol tří teček (...) napravo od spravované aplikace Google Play a potom vyberte **odstranit** ze zobrazeného seznamu. Když odstraníte spravované aplikace Google Play ze seznamu aplikací, je automaticky neschválených spravované aplikace Google Play.

### <a name="managed-google-play-app-type----1352580---"></a>Typ aplikace Google Play spravované <!-- 1352580 -->
**Spravované Google Play** typ aplikace vám umožní konkrétně přidat [spravované aplikace Google Play](https://play.google.com/work/search?q=microsoft&c=apps) do Intune. Jako správce Intune budou teď procházet, Hledat, schválit, synchronizovat a přiřazení aplikací v Intune schválené spravovaného obchodu Google Play. Je potřeba už spravovanou konzolu Google Play vyhledejte samostatně a už máte donutit k. V Intune, vyberte **klientské aplikace** > **aplikace** > **přidat**. V **typ aplikace** seznamu vyberte **spravovaný obchod Google Play** jako typ aplikace.

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Ve verzi Preview podpory pro vlastněných společností, plně spravovaná zařízení s Androidem <!-- 1574342  -->
Intune bude podporovat plně spravovaná zařízení s Androidem vlastnictví "vlastník zařízení" scénář, ve kterém zařízení úzce spravuje IT a jste spojeni jednotlivým uživatelům. To umožňuje správcům spravovat celé zařízení, vynucovat ochranu před rozsahem rozšířené ovládací prvky zásad, není k dispozici pro pracovní profily a instalaci aplikací ze spravovaného obchodu Google Play pouze omezení pro uživatele. K nastavení plně spravovaná zařízení s Androidem, budou moct **registrace zařízení** > **registrace zařízení s Androidem** > **uživatele vlastněné společností, plně spravovaná zařízení** . Mějte prosím na paměti, že tato funkce je ve verzi preview. Některé funkce Intune, jako jsou certifikáty, dodržování předpisů a podmíněného přístupu nejsou aktuálně k dispozici pro Android je plně spravovaná zařízení uživatelů.

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Nasazení služby online licenci pro obchodní aplikace pro Microsoft Store <!-- 1672660  -->
Budete moct přiřadit vyžaduje online licencovaných Microsoft Store pro obchodní aplikace v kontextu zařízení. Nasazení Microsoft Store pro firmy díky tomu umožní aplikaci nainstalují pro všechny uživatele v zařízení. Tento krok platí jenom na Windows 10 RS4 + desktopových zařízeních. Možnost instalace v kontextu zařízení je k dispozici na stránce pro přiřazení klientské aplikace pro MSFB Online licencované aplikace.

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470----"></a>Konfigurace profilu tak, aby se v Průvodci nastavením přeskočily některé obrazovky <!-- 2276470  -->
Když vytvoříte profil registrace s macOS, bude možné a nakonfigurujte ho na některý z následujících obrazovky přeskočit, když uživatel prochází Pomocníka pro instalaci:
- Migrace zařízení s Androidem
- Tón zobrazení
- Ochrana osobních údajů
- iCloudStorage

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522----"></a>Přiřazení profilů Autopilotu virtuální skupině Všechna zařízení <!--2715522  -->
Profily Autopilotu budete moct přiřadit virtuální skupině Všechna zařízení. Uděláte to tak, že vyberete **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > vyberte profil > **Přiřazení** > v části **Přiřadit k** vyberte **Všechna zařízení**. Další informace o profilech Autopilotu najdete v článku [Registrace zařízení s Windows pomocí Windows Autopilotu](enrollment-autopilot.md).

### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324----"></a>Přizpůsobení tapeta na zařízeních s Iosem pod dohledem pomocí konfiguračního profilu zařízení <!-- 2809324  -->
Když vytvoříte profil konfigurace zařízení pro zařízení s Iosem, budete moct povolit a omezit některá nastavení v **konfigurace zařízení** > **profily**  >  **Vytvořit profil** > **iOS** pro platformu > **omezení zařízení** pro typy profilů. Tato aktualizace zahrnuje nové **tapeta** nastavení, které umožňují správcům se použije jako tapeta, PNG, JPG nebo JPEG image ve verzi preview na obrázku a zablokovat uživatelům možnost měnit tapetu. Tapeta nastavení platí pouze pro zařízení pod dohledem. Seznam nastavení najdete v tématu [nastavení omezení zařízení s Iosem](device-restrictions-ios.md).

### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Informační zprávy pro aplikace Win32 <!-- 3136566   -->
Budete moct potlačit oznámení informační zpráva zobrazující koncový uživatel jednotlivé přiřazení aplikace. V Intune, vyberte **klientské aplikace** > **aplikace** > vyberte aplikaci > **Assignemnts** > **zahrnout skupiny**. 

### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396---"></a>Sdílení kontaktů přes Bluetooth se už v omezení zařízení > vlastník zařízení pro Android Enterprise <!-- 3598396 -->
Když vytvoříte profil omezení zařízení pro zařízení s Androidem Enterprise, je **sdílení kontaktů přes Bluetooth** nastavení. V této aktualizaci **sdílení kontaktů přes Bluetooth** bude třeba odebrat nastavení (**konfigurace zařízení** > **profily**  >  **Vytvořit profil** > **Androidu Enterprise** pro platformu > **omezení zařízení > vlastník zařízení** pro typy profilů >  **Obecné**). 

**Sdílení kontaktů přes Bluetooth** nastavení není podporováno pro vlastníka zařízení s Androidem Enterprise management. Takže při odebrání tohoto nastavení neovlivní žádné zařízení ani tenantů, i když toto nastavení je povolena a konfigurována ve vašem prostředí.

Pokud chcete zobrazit aktuální seznam nastavení, přejděte na [nastavení zařízení s Androidem Enterprise a povolení nebo zakázání funkce](device-restrictions-android-for-work.md).

Platí pro: Vlastník zařízení s androidem Enterprise

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Aplikace pro Android Enterprise-jsme nasazení aplikace <!-- 1171203 -->
Pro zařízení s Androidem v neregistrovaných ochrany zásady bez registrace aplikace (APP-jsme) scénář nasazení, které budete moct pomocí spravovaného obchodu Google Play můžete nasadit aplikace pro store a obchodní aplikace pro uživatele. Konkrétně může oddělení IT koncovým uživatelům poskytnout aplikaci katalogu a instalace prostředí, které už vyžaduje, aby koncoví uživatelé zmírnit stav zabezpečení svých zařízeních tím, že instalace z neznámých zdrojů. Kromě toho tento scénář nasazení bude poskytovat Vylepšené uživatelské prostředí.

### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Intune App SDK bude podporovat 256bitových šifrovacích klíčů <!-- 1832174 -->
Sady Intune App SDK pro Android bude používat 256bitových šifrovacích klíčů, když je povoleno šifrování pomocí zásad ochrany aplikací. Sady SDK bude dále poskytovat podpora 128bitových klíčů z důvodu kompatibility s obsahem a aplikace, které používají starší verze sady SDK.


### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Aktualizovat zásady Intune metodu ověřování a instalace aplikace portál společnosti  <!-- 1927359 -->
Na zařízení už zaregistrované prostřednictvím pomocníka prostřednictvím jednoho z metody registrace podnikového zařízení společnosti Apple Intune nebude podporovat aplikace portál společnosti nainstalovaný ručně koncovými uživateli z app storu. Tato změna platí pouze v Apple Pomocníka s nastavením ověřování během registrace. Tato změna ovlivní také pouze zařízení s Iosem zaregistrovaná prostřednictvím:  
* Apple configurator
* Obchodní ředitel společnosti Apple
* Apple School Manager
* Program registrace zařízení Apple (DEP)

Pokud je uživatelé nainstalovat aplikaci portál společnosti z App storu a potom se pokuste registraci těchto zařízení jeho prostřednictvím, dojde k chybě. Tato zařízení bude očekávat, jenom když ho se převede, automaticky, pomocí Intune během registrace použijí portál společnosti. Profily registrace v Intune na portálu Azure portal bude aktualizován, takže můžete určit, jak ověřovat zařízení a pokud se zobrazí v aplikaci portál společnosti. Pokud chcete, aby uživatelé zařízení DEP budou používat aplikaci portál společnosti, musíte zadat předvolby v registrační profil. Kromě toho **identifikaci vašeho zařízení** obrazovky v aplikaci portál společnosti bude brzo zastaralá.  
Chcete-li nainstalovat portál společnosti na již zaregistrované zařízení DEP, budete muset přejít do Intune > klientských aplikací a poslat ho jako spravovaná aplikace pomocí zásad Konfigurace aplikací. Podrobnosti o tom, jak provést tyto kroky budou uvedené v budoucích dokumentace.

### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379---"></a>Non-správci mohou povolit nástroj BitLocker na zařízeních s Windows 10 připojená k Azure AD<!-- 2147379 -->
Když povolíte nastavení nástroje BitLocker na zařízeních s Windows 10 (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **Windows 10 a novější** pro platformu > **Endpoint protection** pro typy profilů > **šifrování Windows**), přidejte nastavení Bitlockeru. Tato aktualizace zahrnuje nové nastavení nástroje BitLocker umožňuje standardní uživatelé (bez oprávnění správce), aby šifrování povolil. Aktuální nastavení najdete v tématu [nastavení služby Endpoint protection pro Windows 10](endpoint-protection-windows-10.md#windows-encryption).


### <a name="additional-settings-for-outlook----3301182---"></a>Další nastavení pro aplikaci Outlook <!-- 3301182 -->
Teď můžete nakonfigurovat další nastavení pro aplikaci Outlook pro iOS a Android pomocí Intune.  Nastavení zahrnují následující:
- Povolte jenom pracovní nebo školní účty, který se má použít v aplikaci Outlook v Iosu a Androidu
- Nasazení moderní ověřování Office 365 a hybridním moderním ověřováním místních účtů
- Použití `SAMAccountName` pro pole uživatelské jméno v e-mailový profil, pokud je vybrána základní ověřování
- Povolit kontakty, které chcete uložit
- Konfigurace upozornění než odešlete externím příjemcům
- Konfigurace **zaměřuje doručené pošty**
- Vyžadovat biometrické údaje pro přístup k aplikaci Outlook pro iOS 
- Blokovat externí obrázky

> [!NOTE]
> Pokud používáte zásady ochrany aplikací Intune pro správu přístupu pro podnikové identity, měli byste zvážit, ne povolení **vyžadují biometrika**. Další informace najdete v tématu **vyžadovat pro přístup podnikové přihlašovací údaje** pro [iOS požadavky na přístup](app-protection-policy-settings-ios.md#access-settings) a [požadavky na přístup Android](app-protection-policy-settings-android.md#access-settings).

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Šablony pro správu jsou ve verzi public preview a přesunout do své vlastní konfigurační profil <!-- 3322847 -->
Šablony pro správu v Intune (**konfigurace zařízení** > **šablony pro správu**) jsou aktuálně ve verzi private preview. Od této aktualizace: Šablony pro správu zahrnuje přibližně 300 nastavení, které jde spravovat v Intune. Dříve tato nastavení existuje pouze v editoru zásad skupiny.
Šablony pro správu jsou k dispozici ve verzi public preview pro správu šablon se přesouvají z **konfigurace zařízení** > **šablony pro správu** k **zařízení konfigurace** > **profily** >**vytvořit profil** > v **platformy**, zvolte  **Windows 10 a novější**v **typ profilu**, zvolte **šablony pro správu**.
Je povoleno oznamování platí pro: Windows 10 a novější

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>MacOS tmavě režimu portál společnosti Intune <!-- 3300524 -->
Portál společnosti pro macOS Intune teď podporuje tmavě režim pro macOS. Když zapnete režim tmavé na zařízení s macOS 10.14 +, portál společnosti bude upravit vzhled na barvy zrcadlení tohoto režimu.

<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Použití Microsoftem doporučených nastavení se standardními hodnotami zabezpečení <!-- 2055484 -->
Intune se integruje s dalšími službami, které se zaměřují na zabezpečení, včetně Ochrany ATP v programu Windows Defender a Ochrany ATP v Office 365. Zákazníci požadují ve službách Microsoft 365 společnou strategii a soudržnější sadu ucelených bezpečnostních pracovních postupů. Naším cílem je srovnat strategie tak, abychom mohli vytvářet řešení přemosťující operace zabezpečení a běžné úlohy správy. V Intune se snažíme tohoto cíle dosáhnout prostřednictvím publikování sady Standardních hodnot zabezpečení doporučených Microsoftem (**Intune** > **Standardní hodnoty zabezpečení**).  Správce bude moct vytvářet zásady zabezpečení přímo z těchto standardních hodnot a potom je nasazovat svým uživatelům. Doporučení osvědčených postupů může upravit tak, aby vyhovovala potřebám jeho organizace. Intune zajišťuje, že zařízení zůstávají v souladu s těmito standardními hodnotami, a upozorní správce, pokud uživatelé nebo zařízení tyto hodnoty nedodržují.

### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Nasazené zásady WIP bez registrace uživatele <!-- 1434452 -->
Zásady Windows Information Protection (WIP) budou k dispozici pro nasazení, aniž by se vyžadovalo, aby si uživatelé MDM zaregistrovali svá zařízení s Windows 10. Tato konfigurace umožňuje společnostem chránit jejich podnikové dokumenty na základě konfigurace WIP a zároveň umožňuje uživatelům uchovat si správu svých vlastních zařízení s Windows. Jakmile jsou dokumenty chráněny zásadami WIP, mohou být chráněná data selektivně vymazána správcem služby Intune. Výběrem uživatele a zařízení a odesláním žádosti o vymazání se veškerá data chráněná prostřednictvím zásad WIP stanou nepoužitelnými. V Intune na portálu Azure Portal vyberte **Mobilní aplikace** > **Selektivní vymazání aplikace**.


<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Nastavení zásady ochrany aplikací (APP) pro webová data <!-- 2662995 -->
Nastavení zásad ochrany aplikací (APP) pro webový obsah na zařízeních s Androidem a iOS bude aktualizované, aby lépe pracovalo s webovými odkazy http a https a také s přenosy dat prostřednictvím univerzálních odkazů iOS a odkazů aplikací pro Android.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token Apple VPP používá jiný produkt MDM <!-- 1488946 -->
Intune rozpozná situaci, kdy se token programu hromadných nákupů (VPP) společnosti Apple používá v Intune a zároveň v jiném produktu MDM, a zobrazí podrobnosti.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Vyřazená zařízení na řídicím panelu Dodržování předpisů zařízením <!-- 1981119 -->
V budoucí aktualizaci se z řídicího panelu Dodržování předpisů zařízením odeberou vyřazená zařízení. Změní se tím číselné údaje týkající se dodržování předpisů.



<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Kontrola Configuration Manageru z hlediska dodržování předpisů <!-- 2192052 -->
Budoucí aktualizace bude obsahovat nové nastavení pro dodržování předpisů System Center Configuration Manageru (**Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**  > **Windows 10**). Configuration Manager bude posílat signály funkci dodržování předpisů v Intune. V Intune můžete nastavit požadavek, aby všechny signály Configuration Manageru hlásily vyhovující stav.

Můžete například vyžadovat, aby v zařízeních byly nainstalované všechny aktualizace softwaru. V Configuration Manageru má tento požadavek stav Nainstalováno. Pokud některé programy v zařízení budou v neznámém stavu, bude se zařízení v Intune považovat za nevyhovující předpisům.

Platí pro Windows 10 a novější.



## <a name="notices"></a>Sdělení

V současné době nejsou aktivní žádná sdělení.

### <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).



