---
title: Časná edice
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f3cbfad85e4a7a97d9bbf98e2ad239fda7cc29e4
ms.sourcegitcommit: d40bfb6af66f2ce7026c0151ace98ec23f1cf76e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="the-early-edition-for-microsoft-intune---may-2018"></a>Časná edice Microsoft Intune – květen 2018

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

<!-- 1805 start -->

### <a name="set-compliance-by-device-location----851881----"></a>Nastavení dodržování předpisů podle umístění zařízení <!-- 851881 ! -->
Někdy můžete chtít omezit přístup k podnikovým prostředkům na konkrétní umístění definovaná podle síťového připojení. Budete moct vytvořit zásady dodržování předpisů (**Dodržování předpisů zařízením** > **Umístění**) na základě IP adresy zařízení. Pokud se zařízení přesune mimo rozsah IP adres, nebude moct přistupovat k podnikovým prostředkům.

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Vylepšené řešení potíží pro instalace aplikací <!-- 928990 -->
U zařízení spravovaných pomocí Microsoft Intune MDM může občas dojít k chybě instalace. Když k těmto chybám instalace dojde, může být obtížné pochopit, proč k nim došlo nebo je odstranit. Spouštíme verzi Public Preview našich funkcí řešení potíží s aplikacemi. U každého jednotlivého zařízení si všimnete nového uzlu **Spravované aplikace**. Jedná se o seznam aplikací, které byly dodány prostřednictvím MDM Intune. Uvnitř uzlu uvidíte seznam stavů instalací aplikací. Pokud vyberete konkrétní aplikaci, uvidíte zobrazení řešení potíží pro tuto konkrétní aplikaci. V zobrazení řešení potíží se zobrazí úplný životní cyklus aplikace, například kdy byla aplikace vytvořena, upravena, zacílena a dodána do zařízení. Pokud navíc nebyla instalace aplikace úspěšná, zobrazí se vám kód chyby a užitečná zpráva týkající se příčiny chyby. 

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
Brzy budete moct nakonfigurovat zásady ochrany aplikací tak, aby mohly explicitně vymazat, blokovat nebo upozornit zařízení, která zásady nedodržují. Nejnovější akce *vymazání* odebere ze zařízení podniková data vaší společnosti. Pokud dojde k vymazání, je uživatel zařízení informován o důvodu vymazání a o postupu nápravy. U některých nastavení, jako je například minimální verze operačního systému, bude možné použít více akcí, třeba blokování a vymazání.

### <a name="new-inventory-information-for-windows-devices----1333569-eeready---"></a>Nové informace o inventáři pro zařízení s Windows <!-- 1333569 eeready -->

Pro zařízení s Windows budou k dispozici následující informace o inventáři na kartě **Hardware** (**Skupiny** > **Všechna mobilní zařízení** > **Zařízení** > vyberte zařízení uživatele > **Zobrazit vlastnosti** > **Hardware**):
- Čip TPM
- Antivirus
- Antispyware
- Brána firewall
- Řízení uživatelských účtů
- Baterie
- Název domény

Další informace o tom, jakým způsobem tato data načítá zprostředkovatel konfiguračních služeb (CSP), najdete v položkách DeviceGuard v článku [DeviceStatus CSP](https://docs.microsoft.com/en-us/windows/client-management/mdm/devicestatus-csp).

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
Všechny uživatele, všechna zařízení a všechny uživatele a zařízení budete moct přiřadit ve skupinách oborů.

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Přesunutí profilů AutoPilot do cílení na skupinu <!-- 1877935 -->
V současné době je možné profily nasazení AutoPilot přiřadit vybraným zařízení. Jakmile budete tato funkce přístupná, budete moct tyto profily přiřadit takto:
- Vytvoření skupin (Azure AD), které obsahují zařízení AutoPilot.
- Přiřazení požadovaných profilů ke skupině Azure AD. Profil AutoPilot se nyní přiřadí k zařízení AutoPilot v dané skupině.

### <a name="management-name-field-will-be-editable----1875989---"></a>Pole Název správy bude možné upravovat <!-- 1875989 -->
Budete moct upravovat pole s názvem správy v okně **Vlastnosti** zařízení. Pokud chcete toto pole upravit, vyberte **Zařízení** > **Všechna zařízení** > vyberte zařízení > **Vlastnosti**. Pole s názvem správy můžete použít k jednoznačné identifikaci zařízení.

<!-- 1804 start -->


### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Další nastavení možností místního zabezpečení zařízení <!-- 1403702 -->
U zařízení s Windows 10 budete moct nakonfigurovat další nastavení možností místního zabezpečení zařízení. Další nastavení budou dostupná v oblasti Klienta sítě Microsoft, Serveru sítě Microsoft, zabezpečení sítě a přístupu k ní a interaktivního přihlášení. Tato nastavení najdete v kategorii Ochrana koncového bodu při vytváření zásad konfigurace zařízení s Windows 10.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Nutnost instalace zásad, aplikací a profilů certifikátů a sítí <!-- 1553555 -->
Správci budou moct koncovým uživatelům zablokovat přístup k desktopu Windows 10 RS4, dokud Intune nenainstaluje zásady, aplikace a profily certifikátů a sítí při zřizování zařízení AutoPilot.

### <a name="rules-for-removing-devices----1609459---"></a>Pravidla odebírání zařízení <!-- 1609459 -->
Budou k dispozici nová pravidla, která vám umožní automaticky odebrat zařízení, která nebyla vrácena se změnami po uplynutí nastaveného počtu dnů. Pokud se na nové pravidlo chcete podívat, přejděte do okna **Intune** vyberte **Zařízení** a vyberte **Device removal rules** (Pravidla pro odebrání zařízení).

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Blokování uživatelských aplikací a prostředí na zařízeních Windows 10 Enterprise RS4 AutoPilot<!-- 1621980 -->
Budete moct zabránit v instalaci uživatelských aplikací a prostředí na zařízeních Windows 10 Enterprise RS4 AutoPilot. Pokud se chcete podívat na tuto funkci, přejděte na **Intune** > **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily Windows AutoPilot** > **Vytvořit nový** > **Nastavení registrace**. 

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

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Webové stránky Azure Active Directory můžou vyžadovat aplikaci Intune Managed Browser a podporovat jednotné přihlašování pro Managed Browser (Public Preview) <!-- 710595 -->   
Pomocí Azure Active Directory (Azure AD) budete moct přístup k webovým stránkám na mobilních zařízeních omezit na aplikaci Intune Managed Browser. V Managed Browseru zůstanou data webových stránek zabezpečená a oddělená od osobních dat koncových uživatelů. Kromě toho bude Managed Browser podporovat možnosti jednotného přihlašování pro weby chráněné pomocí Azure AD. Přihlášení k Managed Browseru nebo jeho používání na zařízení s jinou aplikací, kterou spravuje Intune, umožňuje, aby měl Managed Browser přístup k podnikovým webům chráněným pomocí Azure AD, aniž by uživatel musel zadávat své přihlašovací údaje. Tato funkce se vztahuje na weby jako Outlook Web Access (OWA) a SharePoint Online i na jiné podnikové weby jako prostředky v intranetu, ke kterým se přistupuje prostřednictvím proxy aplikace Azure.


## <a name="notices"></a>Sdělení

V současné době nejsou aktivní žádná sdělení.

### <a name="see-also"></a>Viz taky
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).
