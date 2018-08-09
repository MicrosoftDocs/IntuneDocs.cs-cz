---
title: Časná edice
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ab6c808fc860491ddece5751983071d40864c8dd
ms.sourcegitcommit: 8f68cd3112a71d1cd386da6ecdae3cb014d570f2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2018
ms.locfileid: "39575079"
---
# <a name="the-early-edition-for-microsoft-intune---august-2018"></a>Časná edice Microsoft Intune – srpen 2018

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

<!-- 1808 start -->

### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Windows Hello bude cílit na uživatele a zařízení <!-- 1106609 -->
Když vytvoříte zásady [Windows Hello pro firmy](windows-hello.md), bude platit pro všechny uživatele v organizaci (v celém tenantovi). Po této aktualizaci se tyto zásady s využitím zásad konfigurace zařízení budou dát použít také pro konkrétní uživatele nebo konkrétní zařízení (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Identity Protection** > **Windows Hello pro firmy**).

V Intune na portálu Azure budou konfigurace a nastavení Windows Hello k dispozici v částech **Registrace zařízení** i **Konfigurace zařízení**. **Registrace zařízení** cílí na celou organizaci (celého tenanta) a podporuje program Windows AutoPilot (OOBE). **Konfigurace zařízení** cílí na zařízení a uživatele používající zásadu aplikovanou při přihlášení.

Platí pro:  
- Windows 10 a novější
- Windows Holographic for Business

### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Řízení režimu S v zařízeních se systémem Windows 10 a novějších – verze Public Preview <!-- 1958649 -->
Budete moct vytvořit profil konfigurace zařízení, který přepne zařízení s Windows 10 z režimu S nebo uživatelům v přepnutí zařízení z režimu S zabrání. Funkce bude dostupná v části Intune > **Konfigurace zařízení** > **Profily** >  **Windows 10 a novější** > **Upgrade edice a přepnutí režimu**.
Článek [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode) (Představení Windows 10 v režimu S) poskytuje o režimu S podrobnější informace.
Platí pro: Windows 10 a novější (verze 1809 a novější)

### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Aktualizace podpory moderních sítí VPN pro iOS <!-- 2459928, 1819876, and 2650856 -->
Připravovaná aktualizace bude podporovat následující klienty VPN pro iOS: 
- F5 Access (verze 3.0.1 a vyšší)
- Citrix SSO
- Palo Alto Networks GlobalProtect (verze 5.0 a vyšší) Další změny v připravované aktualizaci:
- Stávající připojení typu **F5 Access** se přejmenují na **F5 Access Legacy** (podle aktualizace značky F5)
- Stávající připojení typu **Palo Alto Networks GlobalProtect** se přejmenují na **Legacy Palo Alto Networks GlobalProtect** (podle aktualizace značky Palo Alto). 

Stávající profily s těmito typy připojení budou i nadále fungovat se starší verzí klienta VPN. Pokud v iOS používáte klienty Cisco Legacy AnyConnect, F5 Access Legacy, Citrix VPN nebo Legacy Palo Alto Networks GlobalProtect, doporučujeme přejít na nové aplikace. Proveďte to co nejdříve, abyste zařízením s iOSem zajistili přístup k síti VPN i po aktualizaci na verzi iOS 12.

### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Uzamčení aplikace Portál společnosti v režimu jedné aplikace do přihlášení uživatele <!--1067692 --> 
Pokud během registrace DEP neověřujete uživatele pomocí Průvodce nastavením, ale prostřednictvím aplikace Portál společnosti, budete mít možnost aplikaci Portál společnosti spustit v režimu Jedna aplikace. Tato možnost ihned po dokončení chodu Průvodce nastavením uzamkne zařízení a uživatel k němu získá přístup až po přihlášení. Tak je zajištěno, že se u zařízení dokončí fáze zavádění a nezůstane osamocené ve stavu, kdy není svázáno s žádným uživatelem.

### <a name="scope-tags-for-policies---1081974-eeready--"></a>Značky oboru pro zásady <!--1081974 eeready-->

Budete moct vytvářet značky oboru a omezovat s jejich pomocí přístup k prostředkům Intune. Přidejte značku oboru k přiřazení role a poté přidejte značku oboru ke konfiguračnímu profilu. Daná role bude mít přístup pouze k prostředkům s konfiguračními profily, které mají odpovídající značky oboru (nebo žádnou značku oboru).
Pokud chcete vytvořit značku oboru, vyberte **Role Intune** > **Obor (značky)** > **Vytvořit**.
Značku oboru přidáte k přiřazení role tak, že zvolíte **Role Intune** > **Všechny role** > **Správce zásad a profilů** > **Přiřazení** > **Obor (značky)**.
Ke konfiguračnímu profilu přidáte značku oboru tak, zvolíte **Konfigurace zařízení** > **Profily** > vyberete profil > **Vlastnosti** > **Obor (značky)**.

### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Přiřazení uživatele a popisného názvu k zařízení AutoPilot <!--1346521 -->
Budoucí verze Public Preview umožní správcům přiřadit uživatele k jedinému zařízení AutoPilot.  Správci budou také moct dávat zařízením v programu AutoPilot popisné názvy, které uživatele při nastavování přivítají.

Platí pro: Windows Insider 1809 nebo novější buildy (v období platnosti verze Preview).

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token Apple VPP používá jiný produkt MDM <!-- 1488946 -->
Intune rozpozná situaci, kdy se token programu hromadných nákupů (VPP) společnosti Apple používá v Intune a zároveň v jiném produktu MDM, a zobrazí podrobnosti.

### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Podpora tunelu pro pakety u profilů VPN pro jednotlivé aplikace iOS u vlastních typů připojení a připojení Pulse Secure <!-- 1520957 -->
Pokud používáte profily VPN pro jednotlivé aplikace iOS, budete moct použít tunelování v aplikační vrstvě (proxy aplikace) nebo na úrovni paketů (tunel pro pakety). Tyto možnosti budou dostupné u následujících typů připojení:
- Vlastní VPN
- Pulse Secure Pokud si nejste jisti, jakou hodnotu použít, vyhledejte informace v dokumentaci poskytovatele připojení VPN.
Platí pro: iOS

### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858-eeready---"></a>Pro profily sítě VPN v iOS je dostupné připojení Zscaler <!-- 1769858 eeready -->
Při vytváření konfiguračního profilu VPN pro zařízení s iOSem (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **iOS** platforma > typ profilu **VPN**) existuje několik typů připojení, mimo jiné Cisco, Citrix a další. Budoucí aktualizace přidá mezi typy připojení Zscaler. 
Dostupné typy připojení jsou uvedeny v části [Nastavení sítě VPN pro zařízení s iOSem](vpn-settings-ios.md).

### <a name="block-windows-personal-device-enrollments----1849498---"></a>Blokování registrace osobních zařízení s Windows <!-- 1849498 -->
V Intune budete moct blokovat registraci osobních zařízení s Windows do [správy mobilních zařízení](windows-enroll.md). Pomocí této funkce se nedají blokovat zařízení zaregistrovaná prostřednictvím [agenta Intune pro počítače](manage-windows-pcs-with-microsoft-intune.md).
Funkce je dostupná v části **Registrace zařízení** > **Omezení zařízení**.
Zapnutí tohoto omezení nijak neovlivní už zaregistrovaná zařízení.
Po zapnutí omezení se v Intune u každého nového požadavku na registraci zařízení s Windows bude kontrolovat, zda je autorizován jako registrace ve společnosti. K registraci ve společnosti jsou povoleny následující metody:
- Uživatel se registruje pomocí [účtu správce registrace zařízení]( device-enrollment-manager-enroll.md).

- Zařízení se registruje prostřednictvím programu [Windows AutoPilot](enrollment-autopilot.md).
- Číslo IMEI zařízení je uvedené v seznamu **Registrace zařízení** > **[Identifikátory podnikových zařízení]( corporate-identifiers-add.md)**).
- Zařízení se registruje v rámci [balíčku hromadného zřizování](windows-bulk-enroll.md).
- Zařízení se registruje prostřednictvím [automatické registrace z centra SCCM ke spolusprávě](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management).
Neautorizované registrace se zablokují.
Následující registrace služba Intune sice označuje jako registrace ve společnosti, ale budou zablokovány vzhledem k tomu, že správci Intune neumožňují kontrolu na úrovni jednotlivých zařízení:
- [Automatická registrace MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) s [připojením k Azure Active Directory během instalace Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).
- [Automatická registrace MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) s [připojením k Azure Active Directory z instalace Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).
Zablokují se také následující metody osobní registrace:
- [Automatická registrace MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) s [přidáním pracovního účtu z nastavení Windows](https://docs.microsoft.com/azure/active-directory/user-help/device-management-azuread-registered-devices-windows10-setup).

- Volba [Jen registrace MDM]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) v nastavení Windows.

### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Určení vzorů pro názvy počítačů v profilu AutoPIlot <!--1849855-->
Budete moct zadat šablonu pro názvy počítačů, podle které se během registrace pomocí řešení AutoPilot vygeneruje a nastaví [název počítače](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp). Tuto šablonu je nutné zadat v profilu AutoPilot umístěném v části **Registrace zařízení** > **Registrace zařízení s Windows** > **Služba Windows AutoPilot Deployment** > **Profily**. Používat se můžou jenom alfanumerické znaky a spojovníky.
Platí pro: Windows Insider 1809 nebo novější buildy (v období platnosti verze Preview).

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>Zobrazuje se číslo verze iOS a číslo buildu <!-- 1892471 -->
V části **Dodržování předpisů zařízení** > **Dodržování předpisů zařízení** se zobrazí verze operačního systému iOS. V budoucí aktualizaci se zobrazí také číslo buildu.
Při vydání aktualizací zabezpečení společnost Apple obvykle ponechává stávající číslo verze, ale aktualizuje číslo buildu. Když znáte číslo buildu, jednoduše ověříte, jestli je nainstalována aktualizace řešící ohrožení zabezpečení.

### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>U profilů Windows AutoPilot se na stránce firemního přihlášení a na stránce chyby domény dají skrýt volby pro změnu účtu <!--1901669 -->
Verze Public Preview bude obsahovat nové možnosti profilů Windows AutoPilot, které správcům dovolí skrýt na stránce firemního přihlášení a na stránce chyby domény volby pro změnu účtu. Předpokladem skrytí těchto možností je, aby v Azure Active Directory byla nakonfigurována funkce Branding společnosti. Platí pro: Windows Insider 1809 nebo novější buildy (v období verze Preview).

### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Zpoždění při zobrazení aktualizací softwaru iOS na zařízení <!-- 1949583 -->
V části Intune > **Aktualizace softwaru** > **Aktualizovat zásady pro iOS** můžete nakonfigurovat dny a časy, kdy se na zařízení nemají instalovat žádné aktualizace. V budoucí aktualizaci budete moct odložit čas, kdy se aktualizace softwaru viditelně zobrazí v zařízení, o 1–90 dní. 
Aktuální nastavení jsou uvedena v části [Konfigurace zásad aktualizace iOS v Microsoft Intune](software-updates-ios.md).

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Vyřazená zařízení na řídicím panelu Dodržování předpisů zařízením <!-- 1981119 -->
V budoucí aktualizaci se z řídicího panelu Dodržování předpisů zařízením odeberou vyřazená zařízení. Změní se tím číselné údaje týkající se dodržování předpisů.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nová aktualizace uživatelského prostředí pro web Portál společnosti <!--2000968 -->
Na web Portál společnosti přidáme nové funkce vycházející z názorů a připomínek zákazníků. Na svých zařízeních s Androidem, iOSem a Windows zaznamenáte značné vylepšení stávající funkčnosti a použitelnosti. Oblasti webu – jako třeba podrobnosti o zařízení, váš názor a podpora a přehled zařízení – získají nový, moderní a živý vzhled. Další vylepšení:
- Zjednodušené pracovní postupy na všech platformách zařízení
- Vylepšené průběhy identifikace a registrace zařízení
- Další užitečné chybové zprávy
- Příjemnější jazyk, méně technického žargonu
- Možnost sdílet přímé odkazy na aplikace
- Vylepšený výkon u velkých katalogů aplikací
- Lepší přístupnost pro všechny uživatele

### <a name="office-365-proplus-version----2213968-eeready---"></a>Verze Office 365 ProPlus <!-- 2213968 eeready -->
Při přiřazování aplikací Office 365 ProPlus k zařízením s Windows 10 pomocí Intune budete moct vybrat verzi Office. Na portálu Azure Portal vyberte **Microsoft Intune** > **Aplikace** > **Přidat aplikaci**. Potom z rozevíracího seznamu **Typ** vyberte **Office 365 ProPlus Suite (Windows 10)**. Volbou **Nastavení sady aplikací** otevřete související okno. V části **Aktualizační kanál** nastavte požadovanou hodnotu, například **Měsíčně**. Volitelně můžete odebrat ze zařízení koncových uživatelů jiné verze Office (msi) tak, že vyberete **Ano**. Vyberte **Konkrétní** a nainstalujte tak pro vybraný kanál na zařízeních koncových uživatelů konkrétní verzi Office. V tomto okamžiku můžete vybrat **konkrétní verzi** Office, která se má použít. Dostupné verze se budou v průběhu času měnit. Při vytváření nového nasazení tedy můžou být dostupné novější verze a některé starší verze nemusí být k dispozici. Aktuální nasazení budou dál nasazovat starší verzi, ale seznam verzí se bude průběžně aktualizovat podle kanálu. Další informace najdete v článku [Základní informace o aktualizačních kanálech Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Konfigurace profilu tak, aby se v Průvodci nastavením přeskočily některé obrazovky <!-- 2276470 -->
Při vytváření budete moct profil registrace zařízení s macOS nakonfigurovat tak, aby při procházení Průvodce nastavením přeskočil některé z následujících obrazovek:
- Migrace zařízení s Androidem
- Tón zobrazení
- Ochrana osobních údajů
- iCloudStorage

### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Změna v procesu aktualizace pro místní konektory <!-- 2277554 -->
Na základě zpětné vazby od zákazníků se změní způsob, jak se aktualizují místní konektory. Po prvotní instalaci místního konektoru budou aktualizace probíhat automaticky. Tato změna začne s novým konektor certifikátu PFX pro Microsoft Intune a následně bude zavedena u dalších typů místních konektorů. 

### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Podpora nastavení Registrovat pomocí DNS pro VPN ve Windows 10 <!-- 2282852 -->
Profily sítě VPN ve Windows 10 budete moct nakonfigurovat tak, aby dynamicky registrovaly IP adresy přiřazené k rozhraní sítě VPN pomocí interní služby DNS bez nutnosti používat vlastní profily.
Aktuální dostupná nastavení profilů VPN jsou uvedena v seznamu [Nastavení sítě VPN ve Windows 10](vpn-settings-windows-10.md). 

### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-for-work-devices----2451462---"></a>Omezení přístupu k aplikacím a blokování přístupu k firemním prostředkům v zařízeních s iOSem a Androidem for Work <!-- 2451462 -->
V části **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu** > **Android for Work** > **Zabezpečení systému** bude k dispozici nové nastavení **Aplikace s omezeným přístupem**. Toto nové nastavení pomocí zásad dodržování předpisů blokuje přístup k firemním prostředkům, pokud jsou v zařízení nainstalované některé aplikace. Zařízení se považuje za neodpovídající předpisům, dokud se z něj aplikace s omezeným přístupem neodeberou.
Platí pro: 
- iOS

### <a name="export-azure-classic-portal-compliance-policies-to-csv-file----2469637---"></a>Export zásad dodržování předpisů z portálu Azure Classic do souboru CSV <!-- 2469637 -->
Zásady dodržování předpisů vytvořené na portálu Azure Classic se přestanou používat.  Až k tomu dojde, budete si moct prohlédnout existující zásady a odstranit je. Zásady nepůjde aktualizovat. Můžete je exportovat jako soubor hodnot oddělených čárkami (CSV). Podrobnosti ze souboru potom můžete využít k opětovnému vytvoření těchto zásad v Intune na portálu Azure Portal.
> [!IMPORTANT]
> Po vyřazení portálu Azure Classic z provozu ztratíte k zásadám přístup a nebudete je moct ani zobrazit. Proto zásady nezapomeňte exportovat a znovu vytvořit na webu Azure Portal dříve, než bude provoz portálu Azure Classic ukončen.

<!-- 1807 start -->

### <a name="more-sync-opportunities-in-the-company-portal-app-for-windows----2683177---"></a>Další možnosti synchronizace v aplikaci Portál společnosti pro Windows <!-- 2683177 -->
Aplikace Portál společnosti pro Windows přidává akci synchronizace zařízení na hlavní panel systému Windows a do seznamů odkazů v nabídce Start. Z kteréhokoli umístění můžete kliknout a rychle synchronizovat zařízení a získat přístup k firemním prostředkům.  

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Resetování hesel zařízení z aplikace Portál společnosti pro Windows 10 <!-- 2101282 --> 
Vaši zaměstnanci si už brzy budou moct resetovat PIN kód nebo heslo ke svému zařízení přímo z aplikace Portál společnosti pro Windows 10. Tato funkce bude dostupná pro vzdálená i místní zařízení spravovaná pomocí Intune, která podporují resetování hesla. V závislosti na typu zařízení se při žádosti zadané pro vzdálené zařízení buď odebere aktuální heslo k zařízení, nebo se vytvoří dočasné heslo. Uživatelé, kteří vyžadují resetování pro místní zařízení, budou přesměrováni do aplikace Nastavení daného zařízení.  

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows----2317227---"></a>Nové možnosti procházení v aplikaci Portál společnosti pro Windows <!-- 2317227 -->  
Při procházení nebo hledání aplikací v aplikaci Portál společnosti pro Windows budete moci přepnout mezi existujícím zobrazením **dlaždic** a nově přidaným zobrazením **podrobností**. Toto nové zobrazení obsahuje podrobnosti aplikace, například název, vydavatele, datum publikování a stav instalace.  

Na stránce **Aplikace** se představí zobrazení **Nainstalované**, kde si můžete prohlédnout podrobnosti o dokončených a probíhajících instalacích aplikací. Chcete se s námi podělit o názory nebo nápady k novým změnám? Pošlete nám je v aplikaci Portál společnosti.

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Vylepšené prostředí aplikace Portál společnosti pro správce registrace zařízení <!-- 675800 -->
Když se správce registrace zařízení přihlásí k aplikaci Portál společnosti pro Windows, bude v této aplikaci uvedeno jen jeho aktuální spuštěné zařízení. Tímto vylepšením se omezí vypršení časového limitu, ke kterým dříve docházelo, když se aplikace snažila načíst všechna zařízení zaregistrovaná správcem.  

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>Použití licencí zařízení z programu VPP k předběžnému zřízení portálu společnosti během registrace do programu DEP <!-- 1608345 -->
Licence zařízení z programu VPP (Volume Purchase Program) budete moct použít k předběžnému zřízení portálu společnosti během registrace do programu DEP (Device Enrollment Program neboli Program registrace zařízení). Pokud toho chcete využít, zadejte při vytváření nebo úpravě registračního profilu token VPP, který chcete použít k instalaci aplikace Portál společnosti. Dbejte na to, aby tokenu nevypršela platnost a abyste měli dost licencí pro aplikaci Portál společnosti. V případech, kdy platnost tokenu vyprší nebo dojdou licence, nabídne Intune instalaci aplikace Portál společnost z App Storu (při které se zobrazí výzva k zadání Apple ID).

###  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Přípony souborů obchodních aplikací pro Windows <!-- 1884873 -->
Přípony souborů obchodních aplikací pro Windows teď budou zahrnovat *.msi*, *.appx*, *.appxbundle*, *.msix* a *.msixbundle*. Aplikaci můžete v Microsoft Intune přidat výběrem možností **Mobilní aplikace** > **Aplikace** > **Přidat**. Zobrazí se podokno **Přidat aplikaci**, které vám umožní vybrat **Typ aplikace**. Pro obchodní aplikace pro Windows vyberte jako typ aplikace **Obchodní aplikace**, vyberte **Soubor balíčku aplikace** a pak zadejte instalační soubor s příslušnou příponou.

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Automatické přidání konfiguračního balíčku Ochrany ATP v programu Windows Defender do konfiguračního profilu <!-- 2144658 -->
Když používáte [Rozšířenou ochranu před internetovými útoky (ATP) a připojujete](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) zařízení k Intune, musíte si v současné době stáhnout konfigurační balíček a přidat ho do konfiguračního profilu. V budoucí aktualizaci bude Intune automaticky načítat balíček z Centra zabezpečení v programu Windows Defender a přidávat ho do profilu za vás.

Platí pro Windows 10 a novější.

### <a name="check-for-sccm-compliance----2192052---"></a>Kontrola dodržování předpisů SCCM <!-- 2192052 -->
Budoucí aktualizace bude obsahovat nové nastavení dodržování předpisů System Center Configuration Manageru (SCCM): **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**  > **Windows 10**. SCCM bude posílat signály funkci dodržování předpisů v Intune. Pomocí nastavení v Intune můžete vyžadovat, aby všechny signály z SCCM hlásily stav vyhovující předpisům.

Můžete například vyžadovat, aby v zařízeních byly nainstalované všechny aktualizace softwaru. V SCCM má tento požadavek stav Nainstalováno. Pokud některé programy v zařízení budou v neznámém stavu, bude se zařízení v Intune považovat za nevyhovující předpisům.

Platí pro Windows 10 a novější.

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Upozornění na vypršení platnosti tokenu VPP nebo docházející licence pro aplikaci Portál společnosti <!-- 2237572 -->
Jestliže pomocí programu VPP (Volume Purchase Program) předběžně zřizujete portál společnosti během registrace do programu DEP, Intune vás upozorní, pokud se bude blížit konec platnosti tokenu VPP nebo pokud bude docházet počet licencí pro aplikaci Portál společnosti.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Vyžadování potvrzení odstranění tokenu VPP používaného k předběžnému zřízení portálu společnosti <!-- 2237634 -->
Bude se vyžadovat potvrzení odstranění tokenu VPP (Volume Purchase Program), pokud se používá k předběžnému zřízení portálu společnosti během registrace do programu DEP.

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Nastavení dalšího zabezpečení pro Instalační službu systému Windows <!-- 2282430 -->
Budete moct uživatelům povolit ovládání instalace aplikací. Pokud je tato možnost povolená, instalace, které by se jinak kvůli narušení zabezpečení zastavily, budou moct pokračovat. Budete moct Instalační službu systému Windows nastavit tak, aby při instalaci libovolné aplikace do systému používala zvýšenou úroveň oprávnění. Dále budete moct povolit, aby se položky WIP (Windows Information Protection) indexovaly a aby se metadata o nich ukládala do nešifrovaného umístění. Pokud je tato zásada zakázaná, chráněné položky WIP se nebudou indexovat a ve výsledcích v Cortaně nebo v Průzkumníkovi souborů se nezobrazí. Funkčnost těchto možností bude ve výchozím nastavení zakázaná. 

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Nastavením zásad ochrany aplikací v iOSu se dají zablokovat klávesnice jiných výrobců <!-- 1248481 -->
Na zařízeních s iOSem budou moct správci Intune zablokovat použití klávesnic jiných výrobců pro přístup k datům organizace z aplikací chráněných zásadami. Když budou nastavené Zásady ochrany aplikací (APP) k blokování klávesnic jiných výrobců, uživatelům zařízení se při první interakci s firemními daty pomocí klávesnice jiného výrobce zobrazí zpráva. Všechny jiné možnosti než nativní klávesnice budou zablokované a uživatelům zařízení se nezobrazí. Uživatelům se dialog se zprávou zobrazí jenom jednou. 

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Vyžadování nebiometrického hesla při spuštění aplikace a vypršení časového limitu <!-- 1506985 -->

Vyžadováním nebiometrického hesla při spuštění aplikace a po vypršení časového limitu určeného správcem bude Intune poskytovat lepší zabezpečení aplikací s podporou Správy mobilních aplikací (MAM), protože omezí použití biometrické identifikace pro přístup k firemním datům. Toto nastavení bude mít vliv na uživatele, kteří pro přístup k aplikacím s podporou APP/MAM budou používat Touch ID (iOS), Face ID (iOS), Biometriku Androidu nebo jiné budoucí způsoby biometrického ověřování. S tímto nastavením budou mít správci Intune přesnější kontrolu nad přístupem uživatelů, takže budou moct vyloučit případy, kdy zařízení s více otisky prstů nebo jinými biometrickými metodami přístupu může odhalit firemní data nesprávnému uživateli. Na portálu Azure Portal otevřete **Microsoft Intune**. Vyberte **Mobilní aplikace** > **Zásady ochrany aplikací** > **Přidat zásadu** > **Nastavení**. Najděte část **Přístup** s konkrétními nastaveními.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Jazykové sady Office 365 Pro Plus <!-- 1833450 -->
Jako správce Intune budete moct nasadit další jazyky pro aplikace Office 365 Pro Plus spravované prostřednictvím Intune. Seznam dostupných jazyků zahrnuje **Typ** jazykové sady (Základní, Částečná a Kontrola pravopisu). Na portálu Azure Portal vyberte **Microsoft Intune** > **Mobilní aplikace** > **Aplikace** > **Přidat**. V okně **Přidat aplikaci** v seznamu **Typ aplikace** vyberte v části **Sada Office 365** možnost **Windows 10**. V okně **Nastavení sady aplikací** vyberte **Jazyky**.

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

<!-- 1805 start -->

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Vyžadování nebiometrického hesla při úplném spuštění aplikace a vypršení časového limitu <!-- 1506985 --> 

Vyžadováním nebiometrického hesla při úplném spuštění aplikace a po vypršení časového limitu určeného správcem bude Intune poskytovat lepší zabezpečení aplikací s podporou Správy mobilních aplikací (MAM), protože omezí použití biometrické identifikace pro přístup k firemním datům. Toto nastavení bude mít vliv na uživatele, kteří pro přístup k aplikacím s podporou APP/MAM budou používat Touch ID (iOS), Face ID (iOS), Biometriku Androidu nebo jiné budoucí způsoby biometrického ověřování. S tímto nastavením budou mít správci Intune přesnější kontrolu nad přístupem uživatelů, takže budou moct vyloučit případy, kdy zařízení s více otisky prstů nebo jinými biometrickými metodami přístupu může odhalit firemní data nesprávnému uživateli. Na portálu Azure Portal otevřete **Microsoft Intune**. Vyberte **Mobilní aplikace** > **Zásady ochrany aplikací** > **Přidat zásadu** > **Nastavení**. Najděte část **Přístup** s konkrétními nastaveními.

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



