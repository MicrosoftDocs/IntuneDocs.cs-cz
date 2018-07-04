---
title: Časná edice
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0500194f5afaba11f37b84bbdf606e6167632a71
ms.sourcegitcommit: afa2e84d5cadf5542ecabc26e61dc71919992a22
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2018
ms.locfileid: "37340174"
---
# <a name="the-early-edition-for-microsoft-intune---july-2018"></a>Časná edice Microsoft Intune – červenec 2018

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

<!-- 1807 start -->

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Resetování hesel zařízení z aplikace Portál společnosti pro Windows 10 <!-- 2101282 --> 
Vaši zaměstnanci si už brzy budou moct resetovat PIN kód nebo heslo ke svému zařízení přímo z aplikace Portál společnosti pro Windows 10. Tato funkce bude dostupná pro vzdálená i místní zařízení spravovaná pomocí Intune, která podporují resetování hesla. V závislosti na typu zařízení se při žádosti zadané pro vzdálené zařízení buď odebere aktuální heslo k zařízení, nebo se vytvoří dočasné heslo. Uživatelé, kteří vyžadují resetování pro místní zařízení, budou přesměrováni do aplikace Nastavení daného zařízení.

### <a name="use-smime-to-encrypt-and-sign-a-users-multiple-devices-----1333642---"></a>Použití S/MIME k šifrování a podepsání více zařízení uživatele <!-- 1333642 -->
Budoucí aktualizace bude zahrnovat šifrování S/MIME e-mailů pomocí nového profilu importovaného certifikátu (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > vyberte platformu > **Importovaný certifikát PKCS** typ profilu). V Intune můžete importovat certifikáty ve formátu PFX. Intune pak může doručit stejné certifikáty do více zařízení zaregistrovaných jedním uživatelem. To také zahrnuje:

- Nativní e-mailový profil v iOS podporuje povolení šifrování S/MIME pomocí importovaných certifikátů ve formátu PFX.
- Nativní poštovní aplikace na zařízeních se systémem Windows Phone 10 automaticky použije certifikát S/MIME.
- Privátní certifikáty je možné doručit na různé platformy. Některé e-mailové aplikace ale S/MIME nepodporují.
- Na jiných platformách může být nutné ručně nakonfigurovat e-mailovou aplikaci a povolit S/MIME.  
- E-mailové aplikace, které podporují šifrování S/MIME, můžou zpracovávat načítání certifikátů pro šifrování S/MIME e-mailů způsobem, který MDM nepodporuje (například ho načítají z úložiště certifikátů svého vydavatele).

Podporováno v systémech: Windows, Windows Phone 10, macOS, iOS, Android

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>Použití licencí zařízení z programu VPP k předběžnému zřízení portálu společnosti během registrace do programu DEP <!-- 1608345 -->
Licence zařízení z programu VPP (Volume Purchase Program) budete moct použít k předběžnému zřízení portálu společnosti během registrace do programu DEP (Device Enrollment Program neboli Program registrace zařízení). Pokud toho chcete využít, zadejte při vytváření nebo úpravě registračního profilu token VPP, který chcete použít k instalaci aplikace Portál společnosti. Dbejte na to, aby tokenu nevypršela platnost a abyste měli dost licencí pro aplikaci Portál společnosti. V případech, kdy platnost tokenu vyprší nebo dojdou licence, nabídne Intune instalaci aplikace Portál společnost z App Storu (při které se zobrazí výzva k zadání Apple ID).

### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Hromadné odstranění zařízení v okně Zařízení <!-- 1793693 -->
V okně Zařízení bude možné odstranit více zařízení najednou. Zvolte **Zařízení** > **Všechna zařízení** > vyberte zařízení, která chcete odstranit > **Odstranit**. U zařízení, která nejde odstranit, se zobrazí upozornění.

### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Nový konfigurační profil Wi-Fi zařízení pro Windows 10 a novější <!-- 1879077 -->
V současné době můžete importovat a exportovat profily Wi-Fi pomocí souborů XML. Nově bude možné vytvořit konfigurační profil Wi-Fi zařízení přímo v Intune, podobně jako na některých jiných platformách.

Pokud chcete vytvořit profil, otevřete položku **Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** > **Wi-Fi**. 

Platí pro Windows 10 a novější.

###  <a name="windows-line-of-business-lob-apps-file-extension-rename----1884873---"></a>Přejmenování přípon souborů obchodních aplikací pro Windows <!-- 1884873 -->
Přípony souborů obchodních aplikací pro Windows se přejmenují z *.appx* a *.appxbundle* na *.msix* a *.msixbundle*. Aplikaci můžete v Microsoft Intune přidat výběrem možností **Mobilní aplikace** > **Aplikace** > **Přidat**. Zobrazí se podokno **Přidat aplikaci**, které vám umožní vybrat **Typ aplikace**. Pro obchodní aplikace pro Windows vyberte jako typ aplikace **Obchodní aplikace**, vyberte **Soubor balíčku aplikace** a pak zadejte instalační soubor s příslušnou příponou.

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Automatické přidání konfiguračního balíčku Ochrany ATP v programu Windows Defender do konfiguračního profilu <!-- 2144658 -->
Když používáte [Rozšířenou ochranu před internetovými útoky (ATP) a připojujete](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) zařízení k Intune, musíte si v současné době stáhnout konfigurační balíček a přidat ho do konfiguračního profilu. V budoucí aktualizaci bude Intune automaticky načítat balíček z Centra zabezpečení v programu Windows Defender a přidávat ho do profilu za vás.

Platí pro Windows 10 a novější.

### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>Položka Veřejný terminál (zastaralé) se zobrazí šedě a nebude umožňovat změny <!-- 2149998 -->
[Funkce Veřejný terminál](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** > **Omezení zařízení**) se označí jako zastaralá a nahradí ji [nastavení veřejného terminálu pro Windows 10 a novější](kiosk-settings.md). Položka **Veřejný terminál (zastaralé)** se zobrazí šedě a uživatelské rozhraní nebude umožňovat změny ani aktualizace. 

Pokud budete chtít povolit režim veřejného terminálu, podívejte se na článek[Nastavení veřejného terminálu pro Windows 10 a novější](kiosk-settings.md).

Platí pro: Windows 10 a novější, Windows Holographic for Business.

### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>Rozhraní API budou používat nezávislé certifikační autority <!-- 2184013 -->
K dispozici bude rozhraní API založené na Javě, které umožní integraci nezávislých certifikačních autorit s Intune a protokolem SCEP. Uživatelé pak budou moct přidat certifikát SCEP do profilu a použít ho pro zařízení využívající MDM.

V současné době Intune podporuje [žádosti protokolu SCEP používající Active Directory Certificate Services](certificates-scep-configure.md).

### <a name="check-for-sccm-compliance----2192052---"></a>Kontrola dodržování předpisů SCCM <!-- 2192052 -->
Budoucí aktualizace bude obsahovat nové nastavení dodržování předpisů System Center Configuration Manageru (SCCM): **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**  > **Windows 10**. SCCM bude posílat signály funkci dodržování předpisů v Intune. Pomocí nastavení v Intune můžete vyžadovat, aby všechny signály z SCCM hlásily stav vyhovující předpisům.

Můžete například vyžadovat, aby v zařízeních byly nainstalované všechny aktualizace softwaru. V SCCM má tento požadavek stav Nainstalováno. Pokud některé programy v zařízení budou v neznámém stavu, bude se zařízení v Intune považovat za nevyhovující předpisům.

Platí pro Windows 10 a novější.

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Upozornění na vypršení platnosti tokenu VPP nebo docházející licence pro aplikaci Portál společnosti <!-- 2237572 -->
Jestliže pomocí programu VPP (Volume Purchase Program) předběžně zřizujete portál společnosti během registrace do programu DEP, Intune vás upozorní, pokud se bude blížit konec platnosti tokenu VPP nebo pokud bude docházet počet licencí pro aplikaci Portál společnosti.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Vyžadování potvrzení odstranění tokenu VPP používaného k předběžnému zřízení portálu společnosti <!-- 2237634 -->
Bude se vyžadovat potvrzení odstranění tokenu VPP (Volume Purchase Program), pokud se používá k předběžnému zřízení portálu společnosti během registrace do programu DEP.

### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Automatické označení zařízení s Androidem registrovaných pomocí technologie Samsung Knox Mobile Enrollment jako firemních <!-- 2404851 -->
Ve výchozím nastavení budou mít zařízení s Androidem registrovaná pomocí technologie Samsung Knox Mobile Enrollment v poli **Vlastnictví zařízení** označení **Firemní**. Před registrací pomocí technologie Knox Mobile Enrollment nebudete muset firemní zařízení identifikovat ručně pomocí IMEI nebo sériových čísel.

### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>Přepínač pro zobrazení nebo nezobrazení tlačítka pro ukončení relace v prohlížeči Kiosk <!-- 2455253 -->
Budete moct nakonfigurovat, jestli se má v prohlížečích Kiosk zobrazovat tlačítko pro ukončení relace. Tento ovládací prvek najdete v části **Konfigurace zařízení** > **Beznabídkový režim (Preview)** > **Kiosk Web Browser**. Pokud toto tlačítko zapnete a uživatel na něj klikne, zobrazí aplikace výzvu k potvrzení ukončení relace. Po potvrzení prohlížeč vymaže všechny údaje o procházení a přejde zpátky na výchozí adresu URL.

### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>Vytvoření mobilního konfiguračního profilu eSIM <!-- 2564077 -->
V části **Konfigurace zařízení** budete moct vytvořit mobilní profil eSIM. Můžete naimportovat soubor, který obsahuje mobilní aktivační kódy poskytnuté vaším mobilním operátorem. Pak můžete tyto profily nasadit do zařízení s Windows 10 podporujících eSIM LTE, jako je například Surface Pro LTE a další zařízení podporující eSIM.

Zkontrolujte, jestli vaše [zařízení podporuje profily eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Platí pro Windows 10 a novější. 




<!-- 1806 start -->

### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Zobrazení konfliktních konfiguračních profilů zařízení <!-- 1556983 -->
V části **Konfigurace zařízení** se zobrazuje seznam existujících profilů. S touto aktualizací se přidá nový sloupec, který bude poskytovat podrobné informace o profilech, u kterých došlo ke konfliktu. Výběrem řádku s konfliktem můžete zobrazit nastavení a profil, u kterého se konflikt vyskytl. 

Přečtěte si další informace o [konfiguračních profilech zařízení](device-profiles.md).

### <a name="corporate-owned-single-use-cosu-support-for-android-devices----1630973---"></a>Podpora zařízení s Androidem ve vlastnictví firmy, pro použití s jednou aplikací (COSU) <!-- 1630973 -->

Intune bude podporovat zamykatelná zařízení s vysokou úrovní správy, ve stylu veřejného terminálu, se systémem Android. To správcům umožní další uzamčení použití zařízení na jednu aplikaci nebo malou sadu aplikací a zabrání uživatelům povolit na zařízení jiné aplikace nebo na něm provádět jiné akce.

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>Podpora Programu registrace zařízení (DEP) společnosti Apple pro zařízení s macOSem<!-- 747651 -->

Intune bude podporovat registraci zařízení s macOSem do Programu registrace zařízení (DEP) společnosti Apple. Postupujte následovně:

1. Na webu deploy.apple.com přiřaďte serveru MDM sériová čísla macOSu.
2. Importujte sériová čísla do Intune.
3. Vytvořte profil registrace specifický pro zařízení s macOSem.

### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Změny názvů Android for Work a Play for Work společnosti Google <!--842873 -->
Intune bude aktualizovat terminologii „Android for Work“ tak, aby odrážela změny brandingu společnosti Google.  Termíny „Android for Work“ a „Play for Work“ se už nebudou používat. V závislosti na kontextu se bude používat jiná terminologie:

- Termín „Android Enterprise“ označuje celkovou moderní sadu správy Androidu.
- Termín „Pracovní profil“ nebo „Vlastník profilu“ označuje vlastní zařízení uživatelů (BYOD) spravovaná pomocí pracovních profilů.
- Termín „Spravovaný obchod Google Play“ označuje Google App Store.

### <a name="monitor-ios--app-configuration-status-per-device----880037-eeready-eestaged---"></a>Monitorování stavu konfigurace aplikací pro iOS podle zařízení <!-- 880037 eeready eestaged -->

Jako správce Microsoft Intune budete moct monitorovat stav konfigurace aplikací pro iOS pro každé spravované zařízení. V části **Microsoft Intune** na portálu Azure Portal vyberte **Zařízení** > **Všechna zařízení**. V seznamu spravovaných zařízení vyberte konkrétní zařízení a zobrazte tak okno pro toto zařízení. V okně zařízení vyberte **Konfigurace aplikace**.  

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Nastavením zásad ochrany aplikací v iOSu se dají zablokovat klávesnice jiných výrobců <!-- 1248481 -->
Na zařízeních s iOSem budou moct správci Intune zablokovat použití klávesnic jiných výrobců pro přístup k datům organizace z aplikací chráněných zásadami. Když budou nastavené Zásady ochrany aplikací (APP) k blokování klávesnic jiných výrobců, uživatelům zařízení se při první interakci s firemními daty pomocí klávesnice jiného výrobce zobrazí zpráva. Všechny jiné možnosti než nativní klávesnice budou zablokované a uživatelům zařízení se nezobrazí. Uživatelům se dialog se zprávou zobrazí jenom jednou. 

### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Vytváření zásad dodržování předpisů pro zařízení pomocí nastavení Firewall na zařízeních s macOSem <!-- 1497640 -->
Při vytváření nových zásad dodržování předpisů systému macOS (**Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu** > **Platforma: macOS** > **Zabezpečení systému**) budou dostupná některá nová nastavení pro **firewall**: 
- **Firewall:** Umožňuje konfigurovat způsob zpracování příchozích připojení ve vašem prostředí.
- **Příchozí připojení:** **Blokuje** všechna příchozí připojení s výjimkou připojení potřebných pro základní internetové služby, jako je DHCP, Bonjour a IPSec. Toto nastavení blokuje také všechny služby sdílení.
- **Neviditelný režim:** **Aktivací** neviditelného režimu zakážete zařízení odpovídat na zjišťovací požadavky. Oprávněným aplikacím bude zařízení dále odpovídat na příchozí žádosti.

Platí pro: macOS 10.12 a novější

### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Použití atributu sAMAccountName jako uživatelského jména účtu pro e-mailové profily <!-- 1500307 -->

Budete moct používat místní **sAMAccountName** jako uživatelské jméno účtu pro e-mailové profily v Androidu, iOSu a Windows 10. Také budete moct získat doménu z atributu `domain` nebo `ntdomain` v Azure Active Directory (Azure AD). Nebo budete moct zadat vlastní statickou doménu.

Pokud chcete tuto funkci používat, musíte atribut `sAMAccountName` synchronizovat z místního prostředí Active Directory do Azure AD.

Platí pro: Android, iOS, Windows 10 a novější

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Vyžadování nebiometrického hesla při spuštění aplikace a vypršení časového limitu <!-- 1506985 -->

Vyžadováním nebiometrického hesla při spuštění aplikace a po vypršení časového limitu určeného správcem bude Intune poskytovat lepší zabezpečení aplikací s podporou Správy mobilních aplikací (MAM), protože omezí použití biometrické identifikace pro přístup k firemním datům. Toto nastavení bude mít vliv na uživatele, kteří pro přístup k aplikacím s podporou APP/MAM budou používat Touch ID (iOS), Face ID (iOS), Biometriku Androidu nebo jiné budoucí způsoby biometrického ověřování. S tímto nastavením budou mít správci Intune přesnější kontrolu nad přístupem uživatelů, takže budou moct vyloučit případy, kdy zařízení s více otisky prstů nebo jinými biometrickými metodami přístupu může odhalit firemní data nesprávnému uživateli. Na portálu Azure Portal otevřete **Microsoft Intune**. Vyberte **Mobilní aplikace** > **Zásady ochrany aplikací** > **Přidat zásadu** > **Nastavení**. Najděte část **Přístup** s konkrétními nastaveními.

### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Selektivní vymazání dat aplikací organizace <!-- 1507030 -->
Správci budou moct nakonfigurovat selektivní vymazání dat organizace jako novou akci pro případ, že nebudou splněné podmínky nastavení Zásad ochrany aplikací (APP).  Tato funkce umožní správcům automaticky chránit a odebírat citlivá data organizace z aplikací na základě předem nakonfigurovaných kritérií.

### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>Odvolání aplikace pro iOS zakoupené přes VPP <!-- 1777384 -->
Jako správce Microsoft Intune budete moct odvolat licence pro vybrané aplikace pro iOS zakoupené přes Volume Purchase Program (VPP). Uživatele můžete upozornit, že už nemají aplikaci přiřazenou. Odvoláním licence aplikace se příslušná aplikace VPP neodinstaluje ze zařízení. Pokud chcete odinstalovat aplikaci VPP, musíte nastavit akci přiřazení na **Odinstalovat**. Počet uvolněných licencí se v Intune projeví v uzlu **Licencované aplikace** v úloze **Aplikace**. Další informace týkající se aplikací VPP pro iOS najdete v tématu [o správě aplikací pro iOS zakoupených přes Volume Purchase Program v Microsoft Intune](vpp-apps-ios.md).

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Jazykové sady Office 365 Pro Plus <!-- 1833450 -->
Jako správce Intune budete moct nasadit další jazyky pro aplikace Office 365 Pro Plus spravované prostřednictvím Intune. Seznam dostupných jazyků zahrnuje **Typ** jazykové sady (Základní, Částečná a Kontrola pravopisu). Na portálu Azure Portal vyberte **Microsoft Intune** > **Mobilní aplikace** > **Aplikace** > **Přidat**. V okně **Přidat aplikaci** v seznamu **Typ aplikace** vyberte v části **Sada Office 365** možnost **Windows 10**. V okně **Nastavení sady aplikací** vyberte **Jazyky**.

### <a name="revoke-ios-vpp-app-license----1863797---"></a>Odvolání licence aplikace VPP pro iOS <!-- 1863797 -->
Jako správce budete moct uvolnit licenci aplikace VPP pro iOS přiřazenou uživateli nebo zařízení. Licenci aplikace budete moct uvolnit také odinstalováním aplikace VPP pro iOS. Licenci aplikace pak můžete přiřadit jinému uživateli nebo zařízení. Další informace o licencích aplikací VPP pro iOS najdete v tématu [o správě aplikací pro iOS zakoupených přes Volume Purchase Program v Microsoft Intune](vpp-apps-ios.md).

### <a name="preview-a-new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nová aktualizace uživatelského prostředí pro web Portál společnosti ve verzi Preview <!--2000968 -->
Na základě ohlasů od zákazníků přidáváme nové funkce na web Portál společnosti a do katalogu aplikací pro iOS. Na svých zařízeních s Androidem, iOSem a Windows zaznamenáte značné vylepšení stávající funkčnosti a použitelnosti. Oblasti webu – jako třeba podrobnosti o zařízení, váš názor a podpora a přehled zařízení – získají nový, moderní a živý vzhled. Další vylepšení:

- Zjednodušené pracovní postupy na všech platformách zařízení
- Vylepšené průběhy identifikace a registrace zařízení
- Další užitečné chybové zprávy
- Příjemnější jazyk, méně technického žargonu
- Možnost sdílet přímé odkazy na aplikace
- Vylepšený výkon u velkých katalogů aplikací
- Lepší přístupnost pro všechny uživatele

Tato aktualizace je v současnosti ve verzi Preview. K používání verze Preview se můžete zaregistrovat na adrese http://aka.ms/webcpflighting.

### <a name="updates-to-out-of-compliance-messages-in-company-portal-app----1832222---"></a>Aktualizace zpráv o nedodržování předpisů v aplikaci Portál společnosti <!-- 1832222 -->
Revidujeme zprávy, které se zobrazí uživatelům zařízení, když zařízení nedodržuje předpisy. Zprávy si zachovají svůj původní význam, ale zaktualizujeme je tak, aby byly lépe srozumitelné a méně technické. Aktualizujeme také odkazy na dokumentaci a postupy pro odstranění problémů.  

Následující texty „Před“ a „Po“ jsou jedním z příkladů vylepšení zpráv, kterých si můžete všimnout:  

Před: *Toto zařízení nekontaktovalo službu Intune v zadaném časovém období vyžadovaném vaším správcem IT. Pokud chcete tento problém vyřešit, otevřete prosím aplikaci Portál společnosti na svém zařízení a klikněte na tlačítko Zkontrolovat dodržování předpisů.*  

Po: *Vaše zařízení se už nějakou dobu neohlásilo organizaci. Pokud chcete znovu navázat spojení, otevřete na zařízení aplikaci Portál společnosti a pro dané zařízení klepněte na Zkontrolovat nastavení.*  

### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Úpravy nasazení aplikací Office 365 Pro Plus <!-- 2150145 -->
Jako správce Microsoft Intune budete mít větší možnost upravovat nasazení aplikací Office 365 Pro Plus. Na portálu Azure Portal vyberte **Microsoft Intune** > **Mobilní aplikace** > **Aplikace**. V seznamu aplikací vyberte vaši sadu Office 365 Pro Plus.  

### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794---"></a>Kontrola nahraných duplicitních identifikátorů firemních (podnikových) zařízení po řádcích <!-- 2203794 -->
Při nahrávání firemních ID poskytne Intune seznam duplicit a nabídne možnost nahradit nebo ponechat existující informace. Sestava se zobrazí, pokud vzniknou duplicity, když zvolíte **Registrace zařízení** > **Identifikátory podnikových zařízení** > **Přidat identifikátory**. 

### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Ruční přidání identifikátorů firemních (podnikových) zařízení <!-- 2203803 -->
Budete moct ručně přidávat ID firemních zařízení. Zvolte **Registrace zařízení** > **Identifikátory podnikových zařízení** > **Přidat**.

### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Nové stavy pro zařízení na stránce Dodržování předpisů zařízením <!-- 2308882 -->
Na stránku **Dodržování předpisů zařízením** > **Zásady** > vyberte zásadu > **Přehled** se přidají následující nové stavy:
- Úspěšné
- Chyba
- Konflikt
- Čeká se na zadání
- Nepoužitelné

Také se zobrazí obrázek, který ukazuje počet zařízení s jinou platformou. Když se třeba díváte na profil iOSu, na nové dlaždici se zobrazí počet zařízení s jiným systémem než iOS, která jsou také přiřazená k tomuto profilu. 

### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Dodržování předpisů zařízením podporuje antivirová řešení jiných výrobců <!-- 2325484 -->
Při vytváření zásad dodržování předpisů zařízením (**Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu** > **Platforma: Windows 10 nebo novější** > **Nastavení** > **Zabezpečení systému**) jsou dostupné nové možnosti **Zabezpečení zařízení**: 
- **Antivirus:** Když je tato možnost nastavená na **Vyžadovat**, můžete dodržování předpisů kontrolovat pomocí antivirových řešení, která jsou registrovaná Centrem zabezpečení systému Windows, třeba od Symantecu. 
- **Antispyware:** Když je tato možnost nastavená na **Vyžadovat**, můžete dodržování předpisů kontrolovat pomocí antispywarových řešení, která jsou registrovaná Centrem zabezpečení systému Windows, třeba od Symantecu. 

Platí pro: Windows 10 a novější 

<!-- 1805 start -->

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Vylepšené řešení potíží pro instalace aplikací <!-- 928990 -->
U zařízení spravovaných pomocí Microsoft Intune MDM může občas dojít k chybě instalace. Když k těmto chybám instalace dojde, může být obtížné pochopit, proč k nim došlo nebo je odstranit. Spouštíme verzi Public Preview našich funkcí řešení potíží s aplikacemi. U každého jednotlivého zařízení si všimnete nového uzlu **Spravované aplikace**. Jedná se o seznam aplikací, které byly dodány prostřednictvím MDM Intune. Uvnitř uzlu uvidíte seznam stavů instalací aplikací. Pokud vyberete konkrétní aplikaci, uvidíte zobrazení řešení potíží pro tuto konkrétní aplikaci. V zobrazení řešení potíží se zobrazí úplný životní cyklus aplikace, například kdy byla aplikace vytvořena, upravena, zacílena a dodána do zařízení. Pokud navíc nebyla instalace aplikace úspěšná, zobrazí se vám kód chyby a užitečná zpráva týkající se příčiny chyby.

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Vyžadování nebiometrického hesla při úplném spuštění aplikace a vypršení časového limitu <!-- 1506985 --> 

Vyžadováním nebiometrického hesla při úplném spuštění aplikace a po vypršení časového limitu určeného správcem bude Intune poskytovat lepší zabezpečení aplikací s podporou Správy mobilních aplikací (MAM), protože omezí použití biometrické identifikace pro přístup k firemním datům. Toto nastavení bude mít vliv na uživatele, kteří pro přístup k aplikacím s podporou APP/MAM budou používat Touch ID (iOS), Face ID (iOS), Biometriku Androidu nebo jiné budoucí způsoby biometrického ověřování. S tímto nastavením budou mít správci Intune přesnější kontrolu nad přístupem uživatelů, takže budou moct vyloučit případy, kdy zařízení s více otisky prstů nebo jinými biometrickými metodami přístupu může odhalit firemní data nesprávnému uživateli. Na portálu Azure Portal otevřete **Microsoft Intune**. Vyberte **Mobilní aplikace** > **Zásady ochrany aplikací** > **Přidat zásadu** > **Nastavení**. Najděte část **Přístup** s konkrétními nastaveními.

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Blokování přístupu k aplikacím na základě neschválených dodavatelů zařízení a modelů <!-- 1425689 ! -->
Správce IT v Intune bude moct vynutit konkrétní seznam výrobců zařízení s Androidem a/nebo modelů se systémem iOS prostřednictvím zásad Intune App Protection. Správce IT může poskytnout středníky oddělený seznam výrobců pro zásady Androidu a modelů zařízení pro zásady iOS. Zásady Intune App Protection jsou pouze pro Android a iOS. V tomto konkrétním seznamu budete moct provést dvě samostatné akce:
- Budete moct blokovat přístup k aplikacím na zařízeních, která nejsou specifikována.
- Nebo selektivně vymazat podniková data na zařízeních, která nejsou specifikována. 

Uživatel nebude moct přistupovat k cílové aplikaci, pokud nebudou splněny požadavky prostřednictvím zásad. Na základě nastavení může být uživatel zablokován nebo mu mohou být v aplikaci vymazána podniková data. Na zařízeních s iOSem tato funkce vyžaduje zapojení aplikací (např. WXP, Outlook, Managed Browser, Yammer), aby integrovaly sadu Intune APP SDK za účelem vynucení nastavení minimální verze pro cílové aplikace. K této integraci dochází průběžně a závisí na týmech konkrétních aplikací. Na Androidu tato funkce vyžaduje nejnovější verzi Portálu společnosti. 

Na zařízeních koncových uživatelů by klient Intune provedl akci založenou na jednoduché shodě řetězců zadaných v okně Intune pro zásady ochrany aplikací. Závisí to zcela na hodnotě, kterou zařízení vykazuje. Doporučujeme správci IT, aby zajistil přesnost zamýšleného chování. Toho se dá dosáhnout testováním tohoto nastavení na základě různých výrobců a modelů zacílených na malé skupiny uživatelů. V Microsoft Intune vyberte **Mobilní aplikace** > **Zásady ochrany aplikací**, abyste si mohli zobrazit a přidat zásady ochrany aplikací. Další informace o zásadách ochrany aplikací najdete v tématu vysvětlujícím, [co jsou zásady ochrany aplikací](app-protection-policy.md).

### <a name="access-actions-for-app-protection-policies----1483510-eeready---"></a>Akce přístupu pro zásady ochrany aplikací <!-- 1483510 EEready -->
Brzy budete moct nakonfigurovat zásady ochrany aplikací tak, aby mohly explicitně vymazat, blokovat nebo upozornit zařízení, která zásady nedodržují. Nejnovější akce *vymazání* odebere ze zařízení podniková data vaší společnosti. Pokud dojde k vymazání, je uživatel zařízení informován o důvodu vymazání a o postupu nápravy. U některých nastavení, jako je například minimální verze operačního systému, bude možné použít více akcí, třeba blokování a vymazání. Tyto akce se aktivují při spuštění aplikace.

<!-- 1804 start -->

### <a name="rules-for-removing-devices----1609459---"></a>Pravidla odebírání zařízení <!-- 1609459 -->
Budou k dispozici nová pravidla, která vám umožní automaticky odebrat zařízení, která nebyla vrácena se změnami po uplynutí nastaveného počtu dnů. Pokud se na nové pravidlo chcete podívat, přejděte do okna **Intune** vyberte **Zařízení** a vyberte **Device removal rules** (Pravidla pro odebrání zařízení).

<!-- 1803 start -->

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Možnost nasadit požadované obchodní aplikace pro všechny uživatele na zařízeních s Windows 10 Desktop <!-- 1627835 RS4 -->
Zákazníci budou moct nasazovat požadované obchodní aplikace pro Windows 10 k instalaci v kontextech zařízení. Tyto akce tak budou k dispozici pro všechny uživatele v zařízení. Platí to jenom na zařízeních s Windows 10 Desktop.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Aktualizace prostředí nápovědy a odeslání názoru v aplikaci Portál společnosti pro Android <!--1631531 -->

Budeme aktualizovat prostředí nápovědy a odeslání názoru v aplikaci Portál společnosti pro Android, aby bylo v souladu s osvědčenými postupy pro aplikace pro Android. Během příštích pár měsíců budeme aktualizovat aplikaci Portál společnosti pro Android, abychom rozdělili položku nabídky **Nápověda a odeslání názoru** na samostatné položky **Nápověda** a **Odeslat názor**. Stránka **Nápověda** bude obsahovat sekci **Nejčastější dotazy** a tlačítko **E-mailová podpora**, které koncovým uživatelům umožní odeslat protokoly do Microsoftu a podpoře společnosti zaslat e-mail s popisem problému. **Odeslat názor** uživatele provede standardním odesláním zpětné vazby Microsoftu. Uživateli se zobrazí výzva, aby zvolil „Něco se mi líbí“, „Něco se mi nelíbí“ nebo „Mám nápad“.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Zásady ochrany aplikací  <!-- 679615 -->
Zásady Intune App Protection nabízejí možnost vytvoření globálních výchozích zásad, které rychle aktivují ochranu přes všechny uživatele v celém tenantovi.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Sdělení

V současné době nejsou aktivní žádná sdělení.

### <a name="see-also"></a>Viz taky
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).