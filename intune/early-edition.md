---
title: Časná edice
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 99b1436fdf718b54f54f7e90835668d4a632b7ce
ms.sourcegitcommit: 390a4be5aa36007c36fb6a5abcfe8d20bc862a4b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="the-early-edition-for-microsoft-intune---march-2018"></a>Časná edice Microsoft Intune – březen 2018

**Časná edice** poskytuje seznam funkcí, které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány v omezené míře a můžou podléhat změnám. Nesdílejte tyto informace mimo společnost. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a můžou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moct zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se na příslušný kontakt pro skupinu produktů společnosti Microsoft.

Tato stránka se pravidelně aktualizuje. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.

> [!Note]
>Následující změny v Intune jsou ve vývoji. Další informace o nových funkcích pro hybridní nasazení najdete na naší stránce věnované [novinkám pro hybridní nasazení](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->

## <a name="intune-in-the-azure-portal"></a>Intune na portálu Azure Portal

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Podpora více Exchange Connectorů <!-- 2070451 -->

Už nebude platit omezení v podobě jednoho Microsoft Intune Exchange Connectoru na každého tenanta. Intune bude podporovat více Exchange Connectorů, abyste mohli nastavit podmíněný přístup Intune s více organizacemi místního Exchange.

S místním konektorem Exchange v Intune můžete spravovat přístup zařízení k místním poštovním schránkám Exchange podle toho, jestli je zařízení zaregistrované v Intune a splňuje zásady dodržování předpisů zařízením. Konektor nastavíte tak, že místní konektor Exchange v Intune stáhnete z portálu Azure Portal a nainstalujete ho na server v organizaci Exchange. Na řídicím panelu Microsoft Intune zvolte **Místní přístup** a pak v **Nastavení** vyberte **Konektor Exchange ActiveSync**. Stáhněte místní konektor Exchange a nainstalujte ho na server v organizaci Exchange. Protože už teď neplatí omezení v podobě jednoho konektoru Exchange na každého tenanta, pokud máte další organizace Exchange, můžete stejným postupem stáhnout a nainstalovat konektor pro každou další organizaci Exchange.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>Připravuje se podpora pro nového klienta Cisco AnyConnect pro iOS <!-- 1333708 -->

Nové profily sítě VPN vytvořené pro Cisco AnyConnect pro iOS budou fungovat s Cisco AnyConnect 4.0.7x a vyššími verzemi. Stávající profily sítě VPN Cisco AnyConnect pro iOS budou označené **Cisco Legacy AnyConnect** a budou dál fungovat s Cisco AnyConnect 4.0.5x stejně jako dnes.

> [!NOTE]
> Tato změna je jenom pro iOS. Pro Android, Android for Work a macOS bude dál jenom jedna možnost Cisco AnyConnect.

#### <a name="more-information"></a>Další informace

Musíte vytvořit nový profil sítě VPN Cisco AnyConnect pro iOS pro podporu nové aplikace, protože nová aplikace Cisco AnyConnect a aplikace Cisco Legacy AnyConnect jsou samostatné aplikace. Pokud ve svém prostředí spravujete klienta AnyConnect, musíte nasadit také novou aplikaci Cisco AnyConnect. Pokud chcete upgrade provést, musíte také odstranit profil sítě VPN Cisco Legacy AnyConnect a odebrat aplikaci Cisco Legacy AnyConnect.

Integrace řízení přístupu k síti (NAC) nebude pro nového klienta AnyConnect v počáteční verzi fungovat. Pracujeme se společností Cisco na tom, abychom zajistili integraci NAC v budoucí verzi Intune.

### <a name="enhanced-jailbreak-detection----846515---"></a>Vylepšené zjišťování jailbreaků <!-- 846515 -->

Vylepšené zjišťování jailbreaků je novým nastavením dodržování předpisů, které zlepší způsob, jak Intune vyhodnocuje zařízení s jailbreakem. Toto nastavení způsobí, že se zařízení bude k Intune hlásit častěji. K tomu se budou využívat polohové služby a bude to mít vliv na vybíjení baterie.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Možnost nasadit požadované obchodní aplikace pro všechny uživatele na zařízeních s Windows 10 Desktop <!-- 1627835 RS4 -->
Zákazníci budou moct nasazovat požadované obchodní aplikace pro Windows 10 k instalaci v kontextech zařízení. Tyto akce tak budou k dispozici pro všechny uživatele v zařízení. Platí to jenom na zařízeních s Windows 10 Desktop.

### <a name="expiring-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Vypršení platnosti obchodních aplikací pro Microsoft Intune <!-- 748789 -->
Na portálu Azure Portal vás Intune upozorní na obchodní aplikace, jejichž platnost brzy vyprší. Při nahrání nové verze obchodní aplikace Intune oznámení o vypršení platnosti ze seznamu aplikací odebere.

### <a name="company-portal-enrollment-improved----1874230--"></a>Vylepšená registrace pomocí Portálu společnosti <!-- 1874230-->
Uživatelé, kteří registrují zařízení pomocí Portálu společnosti ve Windows 10 sestavení 1703 a vyšším, budou moct dokončit první krok registrace bez opuštění aplikace.

### <a name="new-management-name-column----1333586---"></a>Nový sloupec Název správy <!-- 1333586 -->
V okně zařízení přibude nový sloupec s názvem **Název správy**. Půjde o automaticky generovaný název bez možnosti úprav, který bude přiřazený podle zařízení na základě tohoto vzorce:
- Výchozí název pro všechna zařízení: <username>_<devicetype>_<enrollmenttimestamp>
- Pro hromadně přidaná zařízení: <PackageId/ProfileId>_<DeviceType>_<EnrollmentTime>

Je to volitelný sloupec v okně zařízení. Nebude k dispozici ve výchozím nastavení a přístup k němu bude jenom přes výběr sloupců. Na název zařízení nemá tento nový sloupec vliv.

### <a name="new-settings-for-windows-defender-security-center-notifications-device-configuration-profile----1631906---"></a>Nová nastavení pro profil konfigurace zařízení pro oznámení Centra zabezpečení v programu Windows Defender <!-- 1631906 -->

V profilu konfigurace zařízení pro oznámení Centra zabezpečení v programu Windows Defender (WDSC) přibudou tři nová nastavení.

Správci budou moct:

- Skrýt pilíř Identita
- Skrýt pilíř Hardware a jeho dílčí nastavení
- Skrýt pilíř Ransomware (obnovení souborů OneDrive pro firmy)

Když tyto pilíře z aplikace WDSC skryjete, koncoví uživatelé nebudou moct tato nastavení konfigurovat a nevygenerují se žádná oznámení spojená se skrytými součástmi.

### <a name="mam-policies-targeted-based-on-management-state----1665993---"></a>Cílení na zásady MAM na základě stavu správy <!-- 1665993 -->

Budete moct cílit na zásady MAM na základě stavu správy zařízení:

- **Zařízení s iOSem** – bude možné cílit na nespravovaná zařízení (jenom MAM) nebo zařízení spravovaná v Intune.
- **Zařízení s Androidem** – bude možné cílit na nespravovaná zařízení, zařízení spravovaná v Intune a Android Enterprise Profiles spravované v Intune (dříve Android for Work).

### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459--"></a>Konfigurace Gatekeepera ke kontrole nad zdrojem stahování aplikací pro macOS <!-- 1690459-->

Budete moct konfigurovat Gatekeepera, aby vaše zařízení chránil před aplikacemi díky kontrole nad tím, odkud je možné aplikace stahovat. Bude možné konfigurovat tyto zdroje stahování: **Mac App Store**, **Mac App Store a identifikovaní vývojáři** nebo **Kdekoliv**. Bude také možné nakonfigurovat, jestli můžou uživatelé aplikaci nainstalovat pomocí kliknutí s klávesou Control, které umožní tuto kontrolu Gatekeepera přepsat.

Tato nastavení najdete v části **Konfigurace zařízení** -> **Vytvořit profil** -> **macOS** -> **Ochrana koncového bodu**.

### <a name="configure-the-mac-application-firewall----1690461---"></a>Konfigurace brány firewall pro aplikace pro Mac <!-- 1690461 -->

Bude možné nakonfigurovat bránu firewall pro aplikace pro Mac. Můžete to využít k řízení připojení na základě jednotlivých aplikací místo na základě portů. Díky tomu snadněji využijete výhod ochrany pomocí brány firewall a pomůže vám to zabránit nežádoucím aplikacím v převzetí kontroly nad síťovými porty otevřenými pro oprávněné aplikace.

Tuto funkci najdete v části **Konfigurace zařízení** -> **Vytvořit profil** -> **macOS** -> **Ochrana koncového bodu**.

Jakmile nastavení brány firewall povolíte, můžete ji nakonfigurovat pomocí dvou strategií:

- Blokovat všechna příchozí připojení

   Můžete blokovat všechna příchozí připojení u cílových zařízení. Pokud se k tomu rozhodnete, zablokují se příchozí připojení u všech aplikací.

- Povolit nebo blokovat konkrétní aplikace

   Můžete povolit nebo blokovat příjem příchozích připojení u konkrétních aplikací. Můžete také povolit neviditelný režim, který zabrání odpovědím na zjišťovací požadavky.

#### <a name="more-information"></a>Další informace

- Blokovat všechna příchozí připojení

   Tím se zablokuje příjem příchozích připojení u všech služeb sdílení (jako sdílení souborů a obrazovky). Služby systému, které mají příjem příchozích připojení stále povolený, jsou:
   - configd – implementuje DHCP a další služby konfigurace sítě
   - mDNSResponder – implementuje Bonjour
   - racoon – implementuje protokol IPSec

   Abyste mohli služby sdílení používat, musí být **Příchozí připojení** nastavené na **Nenakonfigurováno** (ne **Blokovat**).

- Neviditelný režim

   Povolením zabráníte počítači v odpovídání na zjišťovací požadavky. Počítač bude nadále odpovídat na požadavky oprávněných aplikací. Neočekávané požadavky, jako je ICMP (ping), se ignorují.


### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Aktualizace prostředí nápovědy a odeslání názoru v aplikaci Portál společnosti pro Android <!--1631531 -->

Budeme aktualizovat prostředí nápovědy a odeslání názoru v aplikaci Portál společnosti pro Android, aby bylo v souladu s osvědčenými postupy pro aplikace pro Android. Během příštích pár měsíců budeme aktualizovat aplikaci Portál společnosti pro Android, abychom rozdělili položku nabídky **Nápověda a odeslání názoru** na samostatné položky **Nápověda** a **Odeslat názor**. Stránka **Nápověda** bude obsahovat sekci **Nejčastější dotazy** a tlačítko **E-mailová podpora**, které koncovým uživatelům umožní odeslat protokoly do Microsoftu a podpoře společnosti zaslat e-mail s popisem problému. **Odeslat názor** uživatele provede standardním odesláním zpětné vazby Microsoftu. Uživateli se zobrazí výzva, aby zvolil „Něco se mi líbí“, „Něco se mi nelíbí“ nebo „Mám nápad“.

### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Vlastní kategorie e-knih v rámci programu VPP (volume-purchase program) <!-- 1488911 -->
Bude možné vytvořit vlastní kategorie e-knih a pak k nim přiřadit e-knihy v rámci programu VPP. Koncoví uživatelé pak uvidí nově vytvořené kategorie e-knih a knihy k nim přiřazené.

### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868--"></a>V seznamech zařízení <!--1725868--> se teď zobrazují HoloLens a Surface Hub

Do aplikace Portál společnosti pro Android přidáváme podporu zobrazení zařízení HoloLens a Surface Hub zaregistrovaných v Intune.

### <a name="edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Podpora zásad Intune App Protection v mobilní verzi prohlížeče Edge <!-- 1817882 -->

Prohlížeč Microsoft Edge pro mobilní zařízení bude podporovat zásady ochrany aplikací definované v Intune.

### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763-eeready--"></a>Použití plně rozlišujícího názvu jako subjektu certifikátu SCEP <!--2221763 eeready-->
Při vytváření profilu certifikátu SCEP zadáváte název subjektu. Jako subjekt budete moci použít plně rozlišující název. Jako **Název subjektu** vyberte **Vlastní** a pak zadejte `CN={{OnPrem_Distinguished_Name}}`. Pokud chcete použít proměnnou `{{OnPrem_Distinguished_Name}}`, nezapomeňte synchronizovat atribut uživatele `onpremisesdistingishedname` pomocí služby [Azure Active Directory (AD) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) se službou Azure AD.

### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837-eeready--"></a>Zařízením s iOSem se zobrazuje výzva k zadání PINu každých 15 minut <!--1550837 eeready-->
Po použití zásad dodržování předpisů nebo konfigurace u zařízení s iOSem se uživatelům bude každých 15 minut zobrazovat výzva k zadání PINu. Uživatelům se výzva bude zobrazovat tak dlouho, dokud nenastaví PIN.

### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983-eeready--"></a>Povolení sdílení kontaktů přes Bluetooth – Android for Work <!--1098983 eeready-->
Ve výchozím nastavení Android brání v synchronizaci kontaktů v pracovním profilu se zařízeními Bluetooth. V důsledku toho se kontakty pracovního profilu nezobrazují na ID volajícího u zařízení Bluetooth.

V části **Android for Work** > **Omezení zařízení** > **Nastavení pracovního profilu** bude k dispozici nové nastavení:
- Sdílení kontaktů přes Bluetooth

Správce Intune může toto nastavení nakonfigurovat a povolit sdílení. Toto nastavení je užitečné při párování zařízení se zařízením Bluetooth do auta, které zobrazuje ID volajícího při použití hands-free. Pokud je nastavení povoleno, kontakty pracovního profilu se zobrazí. Pokud není nastavení povoleno, kontakty pracovního profilu se nezobrazí.

Platí pro: Zařízení s pracovním profilem Android v systému Android OS v6.0 a novějších.

### <a name="schedule-your-automatic-updates---1805514---"></a>Plánování automatických aktualizací <!--1805514 -->

Pomocí [nastavení aktualizačního okruhu Windows](windows-update-for-business-configure.md) máte v Intune možnost řídit instalaci automatických aktualizací. Budete moci naplánovat opakované aktualizace na základě týdne, dne a času.

### <a name="disable-checks-on-device-restart---1805490---"></a>Zákaz kontrol při restartování zařízení <!--1805490 -->

V Intune máte možnost řídit [správu aktualizací softwaru](windows-update-for-business-configure.md). Přidá se vlastnost **Kontroly při restartu** a ve výchozím nastavení se povolí. Pokud chcete přeskočit typické kontroly, které se provádí při restartu zařízení (například aktivní uživatelé, stav baterie a další), vyberte **Přeskočit**.

<!-- 1802 start -->

### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nový graf trendu neúspěšných registrací a tabulka důvodů selhání <!-- 1471783 -->

Na stránce s přehledem registrací uvidíte trend neúspěšných registrací a pět nejčastějších příčin selhání. Kliknutím na tento graf nebo tabulku můžete přejít k podrobnostem a najít rady pro řešení problémů a návrhy vedoucí k nápravě.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Přizpůsobení motivů Portálu společnosti pomocí šestnáctkových kódů <!--1049561 -->

Pomocí šestnáctkových kódů si budete moct přizpůsobit barvu motivu v aplikacích Portál společnosti. Když zadáte šestnáctkový kód, Intune určí barvu textu, která poskytuje nejvyšší úroveň kontrastu mezi barvou textu a barvou pozadí podle [standardů WCAG 2.0](http://www.w3.org/TR/WCAG20). Můžete si zobrazit náhled barvy textu a loga společnosti oproti barvě v části **Mobilní aplikace** > **Portál společnosti**.

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Nové nastavení Ochrany Credential Guard v programu Windows Defender přidaná do nastavení ochrany koncového bodu <!--1102252 -->

Do části **Konfigurace zařízení** > **Profily** > **Ochrana koncového bodu** se přidají nová nastavení [Ochrana Credential Guard v programu Windows Defender](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard]. Budou přidána následující nastavení:

- Úroveň zabezpečení platformy: Zadejte, zda se při příštím restartování povolí úroveň zabezpečení platformy. Zabezpečení na základě virtualizace vyžaduje Zabezpečené spuštění. Zabezpečení na základě virtualizace je možné volitelně povolit s použitím ochran přímého přístupu do paměti (DMA). Ochrany DMA vyžadují hardwarovou podporu a povolí se jenom na správně nakonfigurovaných zařízeních.
- Zabezpečení na základě virtualizace: Zadejte, zda se při příštím restartování povolí zabezpečení na základě virtualizace.
- Ochrana Credential Guard v programu Windows Defender: Zapněte ochranu Credential Guard se zabezpečením na základě virtualizace, abyste pomohli ochránit přihlašovací údaje při příštím restartování v případě, že jsou povoleny úroveň zabezpečení platformy se Zabezpečeným spuštěním a zabezpečení na základě virtualizace. Dostupné možnosti zahrnují **Zakázáno**, **Povoleno s uzamčením UEFI**, **Povoleno bez uzamčení** a **Nenakonfigurováno**.
  - Možnost Zakázáno vzdáleně vypne ochranu Credential Guard, pokud byla dříve zapnutá pomocí možnosti Povoleno bez uzamčení.

  - Možnost Povoleno s uzamčením UEFI zajistí, že ochranu Credential Guard nebude možné zakázat pomocí klíče registru nebo pomocí zásad skupiny. Pokud chcete zakázat ochranu Credential Guard po použití tohoto nastavení, musíte zásady skupiny nastavit na Zakázáno a odebrat funkci zabezpečení z jednotlivých počítačů za osobní přítomnosti uživatele, aby bylo možné vymazat konfiguraci trvale uloženou v UEFI. Dokud je konfigurace UEFI trvale uložena, je ochrana Credential Guard povolena.

  - Možnost Povoleno bez uzamčení umožní vzdálené zakázání ochrany Credential Guard pomocí zásad skupiny. Na zařízeních s tímto nastavením musí běžet přinejmenším Windows 10 (verze 1511).

  - Možnost Nenakonfigurováno ponechá nastavení zásad nedefinované. Zásady skupiny nezapíšou nastavení zásad do registru, a proto počítače ani uživatele nijak neovlivní. Pokud v registru existuje aktuální nastavení, zůstane beze změny.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Resetování hesel pro zařízení s Androidem O <!-- 1238299 -->
U zaregistrovaných zařízení s Androidem O budete moct resetovat hesla. Když do zařízení s Androidem O pošlete žádost o resetování hesla, nastaví se aktuálnímu uživateli nové heslo pro odemčení zařízení nebo výzva spravovaného profilu. Heslo nebo výzva se pošle na základě toho, zda má zařízení vlastníka profilu nebo vlastníka zařízení, a projeví se okamžitě.

### <a name="local-device-security-option-settings----1251887---"></a>Nastavení možnosti místního zabezpečení zařízení <!-- 1251887 -->
Pomocí nového nastavení možnosti místního zabezpečení zařízení budete moct povolit nastavení zabezpečení na zařízeních s Windows 10. Tato nastavení najdete v kategorii Ochrana koncového bodu při vytváření zásad konfigurace zařízení s Windows 10.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nové nastavení tiskárny pro vzdělávací profily <!-- 1308900 -->

Pro vzdělávací profily bude nové nastavení k dispozici v kategorii **Tiskárny**: **Tiskárny**, **Výchozí tiskárna**, **Přidat nové tiskárny**.

### <a name="ios-app-provisioning-configuration----1581650---"></a>Konfigurace zřizování aplikací pro iOS <!-- 1581650 -->
Pomocí zahrnutí nebo vyloučení skupin zabezpečení budete moct přiřadit zřizovací profily aplikací pro iOS a zabránit tak vypršení platnosti aplikací.

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nové nastavení Ochrany Application Guard v programu Windows Defender <!-- 1631890 -->

- **Enable graphics acceleration** (Povolit akceleraci grafiky)

Správci budou moct pro Ochranu Application Guard v programu Windows Defender povolit virtuální grafický procesor. Toto nastavení umožní procesoru přesunout vykreslování grafiky na virtuální grafický procesor. Může zlepšit výkon při práci s graficky náročnými weby nebo při sledování videa v kontejneru.

- **SaveFilestoHost**

Správci budou moct povolit předávání souborů z Microsoft Edge, který běží v kontejneru, do hostitelského souborového systému. Zapnutím tohoto nastavení umožníte uživatelům stahovat soubory z Microsoft Edge v kontejneru do hostitelského souborového systému.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Zahrnutí a vyloučení přiřazení aplikací na základě skupin pro Android Enterprise <!-- 1813081 -->
Během přiřazení aplikace a po výběru typu přiřazení bude Android Enterprise (dříve Android for Work) podporovat funkci vyloučení.

<!-- the following are present prior to 1802 -->

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Cílení zásad dodržování předpisů na zařízení ve skupinách zařízení <!--1307012 -->

Budete moct cílit zásady dodržování předpisů na uživatele ve skupinách uživatelů. Budete moct cílit zásady dodržování předpisů na zařízení ve skupinách zařízení.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Zásady ochrany aplikací  <!-- 679615 -->
Zásady Intune App Protection nabízejí možnost vytvoření globálních výchozích zásad, které rychle aktivují ochranu přes všechny uživatele v celém tenantovi.

### <a name="configure-an-ios-app-pin----1586774---"></a>Konfigurace kódu PIN pro aplikaci pro iOS <!-- 1586774 -->
Už brzy budete moct u cílených aplikací pro iOS vyžadovat kód PIN. Na portálu Azure Portal můžete nakonfigurovat požadavek na kód PIN a datum vypršení jeho platnosti (ve dnech). V případě potřeby bude uživatel muset nastavit a použít nový kód PIN, aby se dostal k aplikaci pro iOS. Tuto funkci budou podporovat jenom aplikace pro iOS, u kterých je povolená ochrana aplikace pomocí sady Intune App SDK.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Webové stránky Azure Active Directory můžou vyžadovat aplikaci Intune Managed Browser a podporovat jednotné přihlašování pro Managed Browser (Public Preview) <!-- 710595 -->   
Pomocí Azure Active Directory (Azure AD) budete moct přístup k webovým stránkám na mobilních zařízeních omezit na aplikaci Intune Managed Browser. V Managed Browseru zůstanou data webových stránek zabezpečená a oddělená od osobních dat koncových uživatelů. Kromě toho bude Managed Browser podporovat možnosti jednotného přihlašování pro weby chráněné pomocí Azure AD. Přihlášení k Managed Browseru nebo jeho používání na zařízení s jinou aplikací, kterou spravuje Intune, umožňuje, aby měl Managed Browser přístup k podnikovým webům chráněným pomocí Azure AD, aniž by uživatel musel zadávat své přihlašovací údaje. Tato funkce se vztahuje na weby jako Outlook Web Access (OWA) a SharePoint Online i na jiné podnikové weby jako prostředky v intranetu, ke kterým se přistupuje prostřednictvím proxy aplikace Azure.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-the-new-company-portal-app---1380728--"></a>Přesměrování uživatelů macOS na novou aplikaci Portál společnosti <!--1380728-->   
Když se koncový uživatel přihlásí k webu Portál společnosti, aby zaregistroval svoje zařízení s macOS, bude přesměrován na to, aby proces dokončil stažením nové aplikace Portál společnosti pro macOS. K tomu dojde na zařízeních s macOS používajících OS X El Capitan 10.11 nebo novější. 

<!-- the following are present prior to 1709 -->

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Vylepšená chybová zpráva, když uživatel dosáhne maximálního povoleného počtu zařízení k registraci <!-- 1270370 -->
Místo obecné chybové zprávy se koncovým uživatelům používajícím zařízení s Androidem zobrazí popisná chybová zpráva, na kterou se dá reagovat: „Zaregistrovali jste maximální počet zařízení, který povoluje váš IT správce. Odeberte prosím zaregistrované zařízení, nebo se obraťte s žádostí o pomoc na IT správce.“



## <a name="notices"></a>Sdělení

V současné době nejsou aktivní žádná sdělení.



### <a name="see-also"></a>Viz taky
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).
