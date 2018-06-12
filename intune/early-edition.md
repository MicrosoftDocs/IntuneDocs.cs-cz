---
title: Časná edice
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 95ad588b084319cd8a0f5f5c5d92da0e892eed50
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745039"
---
# <a name="the-early-edition-for-microsoft-intune---june-2018"></a>Časná edice Microsoft Intune – červen 2018

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

<!-- 1806 start -->

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

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nová aktualizace uživatelského prostředí pro web Portál společnosti <!--2000968 -->
Na základě názorů zákazníků přidáváme na web Portál společnosti nové funkce. Na svých zařízeních s Androidem, iOSem a Windows zaznamenáte značné vylepšení stávající funkčnosti a použitelnosti. Oblasti webu – jako třeba podrobnosti o zařízení, váš názor a podpora a přehled zařízení – získají nový, moderní a živý vzhled. Další vylepšení:

- Zjednodušené pracovní postupy na všech platformách zařízení
- Vylepšené průběhy identifikace a registrace zařízení
- Další užitečné chybové zprávy
- Příjemnější jazyk, méně technického žargonu
- Možnost sdílet přímé odkazy na aplikace
- Vylepšený výkon u velkých katalogů aplikací
- Lepší přístupnost pro všechny uživatele

### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Úpravy nasazení aplikací Office 365 Pro Plus <!-- 2150145 -->
Jako správce Microsoft Intune budete mít větší možnost upravovat nasazení aplikací Office 365 Pro Plus. Na portálu Azure Portal vyberte **Microsoft Intune** > **Mobilní aplikace** > **Aplikace**. V seznamu aplikací vyberte vaši sadu Office 365 Pro Plus.  

### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794---"></a>Kontrola nahraných duplicitních identifikátorů firemních (podnikových) zařízení po řádcích <!-- 2203794 -->
Při nahrávání firemních ID poskytne Intune seznam duplicit a nabídne možnost nahradit nebo ponechat existující informace. Sestava se zobrazí, pokud vzniknou duplicity, když zvolíte **Registrace zařízení** > **Identifikátory podnikových zařízení** > **Přidat identifikátory**. 

### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Ruční přidání identifikátorů firemních (podnikových) zařízení <!-- 2203803 -->
Budete moct ručně přidávat ID firemních zařízení. Zvolte **Registrace zařízení** > **Identifikátory podnikových zařízení** > **Přidat**.

### <a name="new-status-for-devices-in-device-configuration----2308882---"></a>Nové stavy pro zařízení v konfiguraci zařízení <!-- 2308882 -->
V části **Konfigurace zařízení** > **Přehled** budou přidané tyto nové stavy:
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

### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680-eeready----"></a>Podpora profilů VPN Palo Alto Networks GlobalProtect<!-- 1333680 eeready ! -->

S touto aktualizací můžete zvolit Palo Alto Networks GlobalProtect jako typ připojení VPN pro profily VPN v Intune (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Typ profilu** > **VPN**). V této vydané verzi se podporují následující platformy: 

- iOS
- Windows 10

### <a name="set-compliance-by-device-location----851881----"></a>Nastavení dodržování předpisů podle umístění zařízení <!-- 851881 ! -->
Někdy můžete chtít omezit přístup k podnikovým prostředkům na konkrétní umístění definovaná podle síťového připojení. Budete moct vytvořit zásady dodržování předpisů (**Dodržování předpisů zařízením** > **Umístění**) na základě IP adresy zařízení. Pokud se zařízení přesune mimo rozsah IP adres, nebude moct přistupovat k podnikovým prostředkům.

Platí pro: Zařízení s Androidem verze 6.0 a novější s aktualizovanou aplikací Portál společnosti

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

### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Povolení beznabídkového režimu na zařízeních s Windows 10 <!-- 1560072 ! -->
Na zařízeních s Windows 10 můžete vytvořit konfigurační profil a povolit beznabídkový režim (**Konfigurace zařízení** > **Profily** > **Vytvořit profil**  >  **Windows 10** > **Omezení zařízení** > **Beznabídkový režim**). V této aktualizaci je nastavení **Beznabídkový režim (Preview)** přejmenováno na **Beznabídkový režim (zastaralé)**. **Beznabídkový režim (zastaralé)** už nedoporučujeme používat, do červnové aktualizace ale zůstane funkční. **Beznabídkový režim (zastaralé)** se nahrazuje novým typem profilu **Beznabídkový režim** (**Vytvořit profil** > **Windows 10**  >  **Beznabídkový režim (Preview)**), který bude obsahovat nastavení pro konfiguraci beznabídkového režimu na systému Windows 10 RS4 a novějším.

Platí pro Windows 10 a novější.

### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Načtení ID modelu uživatele přidružené aplikace (AUMID) pro aplikace pro Microsoft Store pro firmy v beznabídkovém režimu <!-- 1560077 ! -->
Intune bude moct načíst identifikátory AUMID pro aplikace Microsoft Store pro firmy (WSfB), aby bylo možné poskytnout vylepšenou konfiguraci profilu beznabídkového režimu.

Další informace o aplikacích pro Microsoft Store pro firmy najdete v článku [Správa aplikací z Microsoft Storu pro firmy](windows-store-for-business.md).

### <a name="access-actions-for-app-protection-policies----1483510-eeready---"></a>Akce přístupu pro zásady ochrany aplikací <!-- 1483510 EEready -->
Brzy budete moct nakonfigurovat zásady ochrany aplikací tak, aby mohly explicitně vymazat, blokovat nebo upozornit zařízení, která zásady nedodržují. Nejnovější akce *vymazání* odebere ze zařízení podniková data vaší společnosti. Pokud dojde k vymazání, je uživatel zařízení informován o důvodu vymazání a o postupu nápravy. U některých nastavení, jako je například minimální verze operačního systému, bude možné použít více akcí, třeba blokování a vymazání. Tyto akce se aktivují při spuštění aplikace.

### <a name="new-inventory-information-for-windows-devices----1333569-eeready---"></a>Nové informace o inventáři pro zařízení s Windows <!-- 1333569 eeready -->

Pro zařízení s Windows budou k dispozici následující informace o inventáři na kartě **Hardware** (**Skupiny** > **Všechna mobilní zařízení** > **Zařízení** > vyberte zařízení uživatele > **Zobrazit vlastnosti** > **Hardware**):
- Čip TPM
- Antivirus
- Antispyware
- Brána firewall
- Řízení uživatelských účtů
- Baterie
- Název domény

Další informace o tom, jakým způsobem tato data načítá zprostředkovatel konfiguračních služeb (CSP), najdete v položkách DeviceStatus v článku [DeviceStatus CSP](https://docs.microsoft.com/en-us/windows/client-management/mdm/devicestatus-csp).

### <a name="intune-and-the-microsoft-edge-browser----1818969---"></a>Intune a prohlížeč Microsoft Edge <!-- 1818969 -->
Prohlížeč Microsoft Edge pro mobilní zařízení (iOS a Android) nyní podporuje zásady Intune App Protection. Uživatelé, kteří se přihlásí svými podnikovými účty Azure AD v aplikaci prohlížeče Edge, budou chráněni službou Intune. 

### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Nové nastavení jazyka/oblasti při konfiguraci možností při prvním spuštění počítače pro Autopilot <!-- 1821766 -->
Nové nastavení konfigurace bude dostupné pro nastavení jazyka a oblasti pro profily Autopilot během prvního spuštění počítače.

### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nové nastavení pro konfiguraci klávesnice zařízení <!-- 1821768 -->
Nové nastavení bude dostupné pro konfiguraci klávesnice pro profily Autopilot během prvního spuštění počítače.

### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>Použití TeamVieweru ke sdílení obrazovek na zařízeních s iOSem a MacOS<!-- 1985547 -->
Momentálně můžete TeamViewer používat ke vzdálené správě [zařízení se systémem Android a Windows spravovaných v Intune](device-profile-android-teamviewer.md).

Správci se budou moct připojit k TeamVieweru a spustit relace sdílení obrazovky se zařízeními s iOSem a macOS. Uživatelé iPhonů, iPadů a zařízení s macOS mohou své obrazovky živě sdílet s libovolnými jinými stolními nebo mobilními zařízeními. 

### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Uživatelský graf profilu zařízení je zpět <!-- 2160133 -->
Při vylepšování číselných počtů zobrazených v grafu profilu zařízení (**Konfigurace zařízení** > **Profily** > vyberte existující profil > **Přehled**) byl uživatelský graf dočasně odebrán.

V této aktualizaci se uživatelský graf vrací a zobrazuje se na portálu Azure Portal.

### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Přiřazení všech uživatelů a všech zařízení jako skupin oborů <!-- 2196803 -->
Všechny uživatele, všechna zařízení a všechny uživatele a zařízení budete moct přiřadit ve skupinách oborů. Když to chcete udělat, zvolte **Role Intune** > **Všechny role** > **Správce zásad a profilů** > **Přiřazení** > zvolte přiřazení > **Obor (skupiny)**.

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Přesunutí profilů AutoPilot do cílení na skupinu <!-- 1877935 -->
V současné době je možné profily nasazení AutoPilot přiřadit vybraným zařízení. Jakmile budete tato funkce přístupná, budete moct tyto profily přiřadit takto:
- Vytvoření skupin (Azure AD), které obsahují zařízení AutoPilot.
- Přiřazení požadovaných profilů ke skupině Azure AD. Profil AutoPilot se nyní přiřadí k zařízení AutoPilot v dané skupině.

### <a name="management-name-field-will-be-editable----1875989---"></a>Pole Název správy bude možné upravovat <!-- 1875989 -->
Budete moct upravovat pole s názvem správy v okně **Vlastnosti** zařízení. Pokud chcete toto pole upravit, vyberte **Zařízení** > **Všechna zařízení** > vyberte zařízení > **Vlastnosti**. Pole s názvem správy můžete použít k jednoznačné identifikaci zařízení.

<!-- 1804 start -->

### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Další nastavení možností místního zabezpečení zařízení <!-- 1403702 -->
U zařízení s Windows 10 budete moct nakonfigurovat další nastavení možností místního zabezpečení zařízení. Další nastavení budou dostupná v oblasti Klienta sítě Microsoft, Serveru sítě Microsoft, zabezpečení sítě a přístupu k ní a interaktivního přihlášení. Tato nastavení najdete v kategorii Ochrana koncového bodu při vytváření zásad konfigurace zařízení s Windows 10.

### <a name="rules-for-removing-devices----1609459---"></a>Pravidla odebírání zařízení <!-- 1609459 -->
Budou k dispozici nová pravidla, která vám umožní automaticky odebrat zařízení, která nebyla vrácena se změnami po uplynutí nastaveného počtu dnů. Pokud se na nové pravidlo chcete podívat, přejděte do okna **Intune** vyberte **Zařízení** a vyberte **Device removal rules** (Pravidla pro odebrání zařízení).

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Blokování uživatelských aplikací a prostředí na zařízeních Windows 10 Enterprise RS4 AutoPilot<!-- 1621980 -->
Budete moct zabránit v instalaci uživatelských aplikací a prostředí na zařízeních Windows 10 Enterprise RS4 AutoPilot. Pokud se chcete podívat na tuto funkci, přejděte na **Intune** > **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily Windows AutoPilot** > **Vytvořit nový** > **Nastavení registrace**. 

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Podpora více Exchange Connectorů <!-- 2070451 -->

Už nebude platit omezení v podobě jednoho Microsoft Intune Exchange Connectoru na každého tenanta. Intune bude podporovat více Exchange Connectorů, abyste mohli nastavit podmíněný přístup Intune s více organizacemi místního Exchange.

S místním konektorem Exchange v Intune můžete spravovat přístup zařízení k místním poštovním schránkám Exchange podle toho, jestli je zařízení zaregistrované v Intune a splňuje zásady dodržování předpisů zařízením. Konektor nastavíte tak, že místní konektor Exchange v Intune stáhnete z portálu Azure Portal a nainstalujete ho na server v organizaci Exchange. Na řídicím panelu Microsoft Intune zvolte **Místní přístup** a pak v **Nastavení** vyberte **Konektor Exchange ActiveSync**. Stáhněte místní konektor Exchange a nainstalujte ho na server v organizaci Exchange. Protože už teď neplatí omezení v podobě jednoho konektoru Exchange na každého tenanta, pokud máte další organizace Exchange, můžete stejným postupem stáhnout a nainstalovat konektor pro každou další organizaci Exchange.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Možnost nasadit požadované obchodní aplikace pro všechny uživatele na zařízeních s Windows 10 Desktop <!-- 1627835 RS4 -->
Zákazníci budou moct nasazovat požadované obchodní aplikace pro Windows 10 k instalaci v kontextech zařízení. Tyto akce tak budou k dispozici pro všechny uživatele v zařízení. Platí to jenom na zařízeních s Windows 10 Desktop.

### <a name="company-portal-enrollment-improved----1874230--"></a>Vylepšená registrace pomocí Portálu společnosti <!-- 1874230-->
Uživatelé, kteří registrují zařízení pomocí Portálu společnosti ve Windows 10 sestavení 1703 a vyšším, budou moct dokončit první krok registrace bez opuštění aplikace.

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



