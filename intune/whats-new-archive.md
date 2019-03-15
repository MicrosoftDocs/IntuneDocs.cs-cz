---
title: Novinky v Microsoft Intune – Azure za předchozí měsíce | Microsoft Docs
titlesuffix: ''
description: Zkontrolujte starší oznámení ze stránky novinek Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 2/25/2019
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ceefcfbcdf48cf8d450f5a74274bc1beea951cc5
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57461545"
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Novinky v Microsoft Intune – předchozí měsíce

[!INCLUDE [azure_portal](./includes/azure_portal.md)]


<!-- ########################## -->
## <a name="september-2018"></a>Září 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="remove-duplication-of-app-protection-status-tiles----3083391---"></a>Odebrat duplicity dlaždic stavu ochrany aplikací <!-- 3083391 -->
Dlaždice **Stav uživatele pro iOS** a **Stav uživatele pro Android** se vyskytovaly na stránce **Klientské aplikace – přehled** i na stránce **Klientské aplikace – stav ochrany aplikace**. Dlaždice stavu byly odebrány ze stánky **Klientské aplikace – přehled**, aby se zabránilo duplicitě. 

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="support-for-more-third-party-certification-authorities-ca----3093107---"></a>Podpora pro další třetích stran certifikační autority (CA) <!-- 3093107 -->
Když použijete protokol SCEP (Simple Certificate Enrollment Protocol), můžete teď vydat nové certifikáty a prodloužit platnost certifikátů na mobilních zařízeních s Windows, iOS, Androidem a macOS.

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="intune-moves-to-support-ios-10-and-later----2454656---"></a>Intune se přesouvá do podporovat iOS 10 a novější <!-- 2454656 -->  
Registrace Intune, Portál společnosti a spravovaný prohlížeč nyní podporují pouze zařízení s iOSem verze 10 a novějších. Pokud chcete zjistit, na která zařízení nebo uživatele ve vaší organizaci to bude mít vliv, přejděte do Intune na webu Azure Portal > **Zařízení** > **Všechna zařízení**. Podrobnosti o verzi operačního systému zobrazíte tak, že si vyfiltrujete operační systém a potom kliknete na **Sloupce**. Požádejte tyto uživatele, aby si upgradovali zařízení na podporovanou verzi operačního systému.  

Pokud máte některé z níže uvedených zařízení nebo chcete některé z těchto zařízení zaregistrovat, mějte na paměti, že tato zařízení podporují jenom iOS 9 a dřívější verze.  Pokud chcete dále používat Portál společnosti Intune, je nutné tato zařízení upgradovat na zařízení podporující iOS 10 nebo novější verze:  

* iPhone 4S 
* ipodu Touch  
* iPad 2 
* iPad (3. generace) 
* iPad Mini (1. generace)  

### <a name="device-management"></a>Správa zařízení

#### <a name="microsoft-365-device-management-administration-center----3078424---"></a>Centrum pro správu správu zařízení Microsoft 365 <!-- 3078424 -->
Jedním z příslibů Microsoft 365 je zjednodušená správa a v průběhu let jsme integrovali back-endové služby Microsoft 365 tak, aby poskytovaly ucelený komplet, jako je podmíněný přístup Intune a Azure AD. Nové [centrum pro správu Microsoft 365](http://devicemanagement.microsoft.com) je místem, kde můžete konsolidovat, zjednodušovat a integrovat prostředí pro správu. Pracovní prostor pro specialisty na správu zařízení poskytuje snadný přístup ke všem úkolům a informacím o správě zařízení a aplikací a úloh, které vaše organizace potřebuje. Očekáváme, že se stane primárním pracovním prostorem na cloudu pro výpočetní týmy koncových uživatelů organizací.


<!-- ########################## -->
## <a name="august-2018"></a>Srpen 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Tunelové propojení podporu paketů pro profily sítě VPN pro aplikaci systému iOS pro vlastní a typy připojení Pulse Secure <!-- 1520957 -->
Pokud používáte profily VPN pro jednotlivé aplikace pro iOS, můžete použít tunelování v aplikační vrstvě (proxy aplikace) nebo na úrovni paketů (tunel pro pakety). Tyto možnosti jsou dostupné u následujících typů připojení:
- Vlastní VPN
- Pulse Secure Pokud si nejste jisti, jakou hodnotu použít, vyhledejte informace v dokumentaci poskytovatele připojení VPN.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Zpoždění při zobrazení aktualizací softwaru iOS v zařízení <!-- 1949583 -->
V části Intune > **Aktualizace softwaru** > **Aktualizovat zásady pro iOS** můžete nakonfigurovat dny a časy, kdy se na zařízení nemají instalovat žádné aktualizace. V budoucí aktualizaci budete moct odložit čas, kdy se aktualizace softwaru viditelně zobrazí v zařízení, o 1–90 dní. 
Aktuální nastavení jsou uvedena v části [Konfigurace zásad aktualizace iOS v Microsoft Intune](software-updates-ios.md).

#### <a name="office-365-proplus-version----2213968---"></a>Office 365 ProPlus version <!-- 2213968 -->
Při přiřazování aplikací Office 365 ProPlus k zařízením s Windows 10 pomocí Intune si můžete vybrat verzi Office. Na portálu Azure Portal vyberte **Microsoft Intune** > **Aplikace** > **Přidat aplikaci**. Potom z rozevíracího seznamu **Typ** vyberte **Office 365 ProPlus Suite (Windows 10)**. Volbou **Nastavení sady aplikací** otevřete související okno. V části **Aktualizační kanál** nastavte požadovanou hodnotu, například **Měsíčně**. Volitelně můžete odebrat ze zařízení koncových uživatelů jiné verze Office (msi) tak, že vyberete **Ano**. Vyberte **Konkrétní** a nainstalujte tak pro vybraný kanál na zařízeních koncových uživatelů konkrétní verzi Office. V tomto okamžiku můžete vybrat **konkrétní verzi** Office, která se má použít. Dostupné verze se budou v průběhu času měnit. Při vytváření nového nasazení tedy můžou být dostupné novější verze a některé starší verze nemusí být k dispozici. Aktuální nasazení budou dál nasazovat starší verzi, ale seznam verzí se bude průběžně aktualizovat podle kanálu. Další informace najdete v článku [Základní informace o aktualizačních kanálech Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Podpora pro nastavení registrace DNS pro VPN ve Windows 10 <!-- 2282852 -->
Od této aktualizace můžete profily sítě VPN ve Windows 10 nakonfigurovat tak, aby dynamicky registrovaly IP adresy přiřazené k rozhraní sítě VPN pomocí interní služby DNS bez nutnosti používat vlastní profily.
Informace o aktuálně dostupných nastaveních profilů VPN najdete v seznamu [Nastavení sítě VPN ve Windows 10](vpn-settings-windows-10.md). 

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name---2652728--"></a>Instalační program portálu společnosti pro macOS teď obsahuje číslo verze v názvu souboru instalačního programu <!--2652728-->

#### <a name="ios-automatic-app-updates----2729759---"></a>iOS automatické aktualizace aplikací <!-- 2729759 -->
Automatické aktualizace aplikací fungují u aplikací licencovaných pro zařízení i uživatele v iOSu verze 11.0 a novějších.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Windows Hello zaměřené na uživatele a zařízení <!-- 1106609 -->
Když vytvoříte zásady [Windows Hello pro firmy](windows-hello.md), bude platit pro všechny uživatele v organizaci (v celém tenantovi). Po této aktualizaci se tyto zásady s využitím zásad konfigurace zařízení budou dát použít také pro konkrétní uživatele nebo konkrétní zařízení (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Identity Protection** > **Windows Hello pro firmy**).
V Intune na portálu Azure Portal je konfigurace a nastavení Windows Hello nově k dispozici v částech **Registrace zařízení** i **Konfigurace zařízení**. **Registrace zařízení** cílí na celou organizaci (celého tenanta) a podporuje program Windows AutoPilot (OOBE). **Konfigurace zařízení** cílí na zařízení a uživatele používající zásadu aplikovanou při přihlášení.
Tato funkce platí pro:  
- Windows 10 a novější
- Windows Holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858---"></a>Se Zscalerem dostupné připojení pro profily sítě VPN v iOS <!-- 1769858 -->
Při vytváření konfiguračního profilu VPN pro zařízení s iOSem (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **iOS** platforma > typ profilu **VPN**) existuje několik typů připojení, mimo jiné Cisco, Citrix a další. S touto aktualizací se mezi typy připojení přidává Zscaler. 
Dostupné typy připojení jsou uvedeny v části [Nastavení sítě VPN pro zařízení s iOSem](vpn-settings-ios.md).

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10----1879077---"></a>Režim FIPS pro profily rozlehlé sítě Wi-Fi pro Windows 10 <!-- 1879077 -->
Nově můžete pro podnikové profily Wi-Fi pro Windows 10 povolit na portálu Intune Azure režim FIPS (Federal Information Processing Standards). Pokud režim FIPS na vašich profilech Wi-Fi povolíte, ujistěte se, že je povolený v infrastruktuře sítě Wi-Fi.
Postup vytvoření profilu Wi-Fi najdete v článku [Nastavení Wi-Fi pro zařízení s Windows 10 a novější verzí v Intune](wi-fi-settings-windows.md).

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Ovládací prvek S režimu ve Windows 10 a novější zařízení – ve verzi public preview <!-- 1958649 -->
Od této aktualizace funkcí můžete vytvářet profil konfigurace zařízení, který přepne zařízení s Windows 10 z režimu S nebo uživatelům v přepnutí zařízení z režimu S zabrání. Funkci najdete v části Intune > **Konfigurace zařízení** > **Profily** >  **Windows 10 a novější** > **Upgrade edice a přepnutí režimu**.
Článek [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode) (Představení Windows 10 v režimu S) poskytuje o režimu S podrobnější informace.
Platí pro: nejnovější build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (v období verze Preview).

#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Balíček pro konfiguraci ochrany ATP v programu Windows Defender automaticky přidá do konfiguračního profilu <!-- 2144658 -->
Když používáte [Rozšířenou ochranu před internetovými útoky (ATP) a připojujete](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) zařízení k Intune, museli jste si dříve stáhnout konfigurační balíček a přidat ho do konfiguračního profilu. Od této aktualizace Intune automaticky načítá balíček z Centra zabezpečení v programu Windows Defender a přidává ho do profilu za vás.
Platí pro Windows 10 a novější.

#### <a name="require-users-to-connect-during-device-setup---2311457--"></a>Vyžadovat, aby uživatelé pro připojení během nastavování zařízení <!--2311457-->
Nyní můžete nastavit profily zařízení tak, aby se během instalace Windows 10 muselo zařízení ještě před opuštěním stránky Síť připojit k síti. Funkce je sice ve verzi Preview, ale ve Windows Insider sestavení 1809 nebo novějších je toto nastavení povinné.
Platí pro: nejnovější build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (v období verze Preview).

#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices----2451462---"></a>Omezí aplikace a zablokovat přístup k prostředkům společnosti na zařízení s iOS a Android Enterprise <!-- 2451462 -->
V části **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu** > **iOS** > **Zabezpečení systému** je k dispozici nové nastavení **Aplikace s omezeným přístupem**. Toto nové nastavení pomocí zásad dodržování předpisů blokuje přístup k firemním prostředkům, pokud jsou v zařízení nainstalované některé aplikace. Zařízení se považuje za neodpovídající předpisům, dokud se z něj aplikace s omezeným přístupem neodeberou.
Platí pro: iOS

#### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Moderní VPN podporu aktualizací pro iOS <!-- 2459928, 1819876, and 2650856 -->
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

#### <a name="better-mobile---new-mobile-threat-defense-partner----22662717---"></a>Lepší Mobile – nový partner ochrany před mobilními hrozbami <!-- 22662717 -->
Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Better Mobile. Je to řešení ochrany před mobilními hrozbami, které se integruje s Microsoft Intune.

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Uzamčení aplikace portál společnosti v režimu jedné aplikace do přihlášení uživatele <!--1067692 --> 
Pokud během registrace DEP neověřujete uživatele pomocí Průvodce nastavením, ale prostřednictvím aplikace Portál společnosti, máte nyní možnost aplikaci Portál společnosti spustit v režimu Jedna aplikace. Tato možnost ihned po dokončení chodu Průvodce nastavením uzamkne zařízení a uživatel k němu získá přístup až po přihlášení. Tak je zajištěno, že se u zařízení dokončí fáze zavádění a nezůstane osamocené ve stavu, kdy není svázáno s žádným uživatelem.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Přiřadit uživatele a popisný název zařízení Autopilot <!--1346521 -->
Nově můžete [přiřadit uživatele k jedinému zařízení Autopilot](enrollment-autopilot.md). Správci budou také moct dávat zařízením v programu AutoPilot popisné názvy, které uživatele při nastavování přivítají.
Platí pro: nejnovější build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (v období verze Preview).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>Použít licence programu VPP zařízení k předběžnému přidělení během registrace DEP na portálu společnosti <!-- 1608345 -->
Licence zařízení z programu VPP (Volume Purchase Program) můžete teď použít k předběžnému zřízení Portálu společnosti během registrace do programu DEP (Device Enrollment Program neboli Program registrace zařízení). Pokud to chcete udělat, zadejte při [vytváření nebo úpravě profilu registrace](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) token VPP, který chcete použít k instalaci aplikace Portál společnosti. Dbejte na to, aby tokenu nevypršela platnost a abyste měli dost licencí pro aplikaci Portál společnosti. V případech, kdy platnost tokenu vyprší nebo dojdou licence, nabídne Intune instalaci aplikace Portál společnost z App Storu (při které se zobrazí výzva k zadání Apple ID).

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Vyžaduje se odstranit token VPP, který se používá pro portál společnosti předběžným zřizováním potvrzení <!-- 2237634 -->
Vyžaduje se potvrzení odstranění tokenu VPP (Volume Purchase Program), pokud se používá k předběžnému zřízení portálu společnosti během registrace do programu DEP.

#### <a name="block-windows-personal-device-enrollments----1849498---"></a>Registrace osobních zařízení Windows bloku <!-- 1849498 -->
V Intune můžete [blokovat registraci osobních zařízení s Windows](enrollment-restrictions-set.md#set-device-type-restrictions) do [ správy mobilních zařízení](windows-enroll.md). Pomocí této funkce se nedají blokovat zařízení zaregistrovaná prostřednictvím [agenta Intune pro počítače](manage-windows-pcs-with-microsoft-intune.md). Tato funkce se bude vydávat v příštích několika týdnech, takže ji v uživatelském rozhraní nemusíte vidět hned.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Určete vzory názvů počítačů v profilu Autopilot <!--1849855-->
Můžete [zadat šablonu pro názvy počítačů](enrollment-autopilot.md#create-an-autopilot-deployment-profile), která se použije ke generování a nastavení [názvu počítače](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) při registraci do programu AutoPilot. Platí pro: nejnovější build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (v období verze Preview).

#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>Profily Windows Autopilot skryjete možnosti účtu změnit na přihlašovací stránku společnosti a domény chybovou stránku <!--1901669 -->
Nyní jsou k dispozici [nové možnosti profilu Windows AutoPilot](enrollment-autopilot.md#create-an-autopilot-deployment-profile), které správcům umožňují na přihlašovací stránce společnosti a na chybové stránce domény skrýt volbu změny účtu. Předpokladem skrytí těchto možností je, aby v Azure Active Directory byla nakonfigurována funkce Branding společnosti. Platí pro: nejnovější build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (v období verze Preview).

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>macOS podpora programu Apple Device Enrollment Program <!-- 747651 -->
Intune teď podporuje registraci zařízení s macOS do Programu registrace zařízení (DEP) společnosti Apple. Další informace najdete v článku [Automatická registrace zařízení s macOS do Programu registrace zařízení Apple](device-enrollment-program-enroll-macos.md).

### <a name="device-management"></a>Správa zařízení

#### <a name="delete-jamf-devices----2653306--"></a>Odstranit zařízení Jamf <!-- 2653306-->
Zařízení spravovaná prostřednictvím JAMF můžete odstranit tak, že přejdete na **Zařízení** > zvolíte zařízení Jamf > **Odstranit**.

#### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Změnit terminologie "vyřadit z provozu" a "Vymazat" <!-- 2175759 -->
V uživatelském rozhraní Intune a v dokumentaci k Intune jsme změnili kvůli sjednocení s Graph API následující výrazy:
- **Odebrání firemních dat** se mění na „vyřazení“.
- **Obnovení továrního nastavení** se mění na **vymazání**.

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate----297909500--"></a>Potvrzovací dialogové okno, pokud se správce pokusí odstranit MDM Push Certificate <!-- 297909500-->
Pokud se jakýkoliv uživatel pokusí odstranit certifikát Apple MDM Push Certificate, zobrazí se v dialogovém okně potvrzení počet souvisejících zařízení s iOSem a macOS. Dojde-li k odstranění certifikátu, musí se tato zařízení znovu zaregistrovat.

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Nastavení dalšího zabezpečení pro Instalační službu systému Windows <!-- 2282430 -->
Můžete uživatelům umožnit ovládání instalace aplikací. Pokud je tato možnost povolená, instalace, které by se jinak kvůli narušení zabezpečení zastavily, budou moct pokračovat. Můžete Instalační službu systému Windows nastavit tak, aby při instalaci libovolné aplikace do systému používala zvýšenou úroveň oprávnění. Dále můžete povolit, aby se položky WIP (Windows Information Protection) indexovaly a aby se metadata o nich ukládala do nešifrovaného umístění. Pokud je tato zásada zakázaná, chráněné položky WIP se neindexují a ve výsledcích v Cortaně nebo v Průzkumníkovi souborů se nezobrazují. Funkčnost těchto možností je ve výchozím nastavení zakázaná. 

#### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nové aktualizace uživatelského prostředí na webu portál společnosti <!--2000968 -->
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

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Vylepšené zjišťování jailbreaků v generování sestav dodržování předpisů<!-- 2198738 -->
Vylepšené stavy nastavení detekce jailbreaků se nově zobrazují při veškerém generování sestav dodržování předpisů v konzole správce.

### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="scope-tags-for-policies---1081974---"></a>Značky oboru pro zásady <!--1081974 -->
Nově můžete [vytvářet značky oboru](scope-tags.md) a omezovat s jejich pomocí přístup k prostředkům Intune. Přidejte značku oboru k přiřazení role a poté přidejte značku oboru ke konfiguračnímu profilu. Daná role bude mít přístup pouze k prostředkům s konfiguračními profily, které mají odpovídající značky oboru (nebo žádnou značku oboru).





<!-- ########################## -->
## <a name="july-2018"></a>Červenec 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>Podpora aplikací – obchodní (LOB) pro macOS <!-- 1895847 -->
Microsoft Intune umožňuje nasazovat obchodní aplikace pro macOS jako **povinné** nebo **k dispozici s registrací**. Koncoví uživatelé můžou aplikace nasazovat jako **povinné** prostřednictvím Portálu společnosti pro macOS nebo [webu Portál společnosti](https://portal.manage.microsoft.com).

#### <a name="ios-built-in-app-support-for-kiosk-mode----2051098---"></a>Podpora Integrovaná aplikace pro iOS pro celoobrazovkový režim <!-- 2051098 -->
Kromě aplikací ze Storu a spravovaných aplikací můžete nyní vybrat i integrovanou aplikaci (jako je Safari), která poběží na zařízení s iOSem v celoobrazovkovém režimu.

#### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Upravit nasazení aplikací Office 365 Pro Plus <!-- 2150145 -->
Jako správce Microsoft Intune máte širší možnosti úpravy nasazování aplikací Office 365 Pro Plus. Kromě toho už kvůli změně vlastností sady nemusíte odstraňovat svá nasazení. Na portálu Azure Portal vyberte **Microsoft Intune** > **Klientské aplikace** > **Aplikace**. V seznamu aplikací vyberte vaši sadu Office 365 Pro Plus.  

#### <a name="updated-intune-app-sdk-for-android-is-now-available----2744271--"></a>Aktualizované sady Intune App SDK pro Android je teď dostupná <!-- 2744271-->
K dispozici je aktualizovaná verze sady Intune App SDK pro Android, která podporuje vydanou verzi Android P. Pokud jste vývojáři aplikací a používáte sadu Intune SDK pro Android, musíte si nainstalovat aktualizovanou verzi sady Intune App SDK. Tím zajistíte, že funkce Intune budou v aplikacích pro Android fungovat očekávaným způsobem, a to i na zařízeních s Androidem P. Tato verze sady Intune App SDK nabízí integrovaný plug-in, který aktualizuje sadu SDK, abyste nemuseli přepisovat stávající integrovaný kód. Podrobné informace najdete v tématu o [sadě Intune SDK pro Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). Pokud používáte staré označení Intune, doporučujeme použít ikonu aktovky. Podrobné informace najdete v [tomto úložišti GitHub](https://github.com/msintuneappsdk/intune-app-partner-badge).

#### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Další možnosti synchronizace v aplikaci Portál společnosti pro Windows  
Aplikace Portál společnosti pro Windows teď umožňuje zahájit synchronizaci přímo z hlavního panelu Windows a z nabídky Start. Tato funkce je užitečná hlavně v případě, že vaším jediným úkolem je synchronizace zařízení a získání přístupu k podnikovým prostředkům. Pokud chcete tuto novou funkci použít, klikněte pravým tlačítkem na ikonu Portál společnosti, která je připnutá na hlavní panel nebo v nabídce Start. V možnostech nabídky (označuje se také jako seznam odkazů) vyberte **Synchronizovat toto zařízení**. V aplikaci Portál společnosti se otevře stránka **Nastavení** a zahájí se synchronizace. Nové funkce najdete v tématu [Aktualizace uživatelského rozhraní pro aplikace Intune pro koncové uživatele](whats-new-app-ui.md).   

#### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Nové možnosti procházení v aplikaci Portál společnosti pro Windows  
Při procházení nebo hledání aplikací v aplikaci Portál společnosti pro Windows teď můžete přepínat mezi stávajícím zobrazením **dlaždic** a nově přidaným zobrazením **podrobností**. Toto nové zobrazení obsahuje podrobnosti aplikace, například název, vydavatele, datum publikování a stav instalace.  

Na stránce **Aplikace** si v zobrazení **Nainstalované** můžete prohlédnout podrobnosti o dokončených a probíhajících instalacích aplikací. Vzhled nového zobrazení najdete v tématu [Aktualizace uživatelského rozhraní pro aplikace Intune pro koncové uživatele](whats-new-app-ui.md).  

#### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Vylepšené prostředí aplikace Portál společnosti pro správce registrace zařízení  
Když se správce registrace zařízení přihlásí k aplikaci Portál společnosti pro Windows, bude se od teď v této aplikaci uvádět jen jeho aktuální spuštěné zařízení. Tímto vylepšením se omezí vypršení časového limitu, ke kterým dříve docházelo, když se aplikace snažila zobrazit všechna zařízení zaregistrovaná správcem.  

#### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Blokovat přístup aplikace na základě neschválených zařízení a modelů  <!-- 1425689 ! -->
Správce IT v Intune může vynutit konkrétní seznam výrobců zařízení s Androidem a/nebo modelů s iOSem prostřednictvím zásad Intune App Protection. Správce IT může poskytnout středníky oddělený seznam výrobců pro zásady Androidu a modelů zařízení pro zásady iOS. Zásady Intune App Protection jsou pouze pro Android a iOS. V tomto konkrétním seznamu můžete provést dvě samostatné akce:
- Budete moct blokovat přístup k aplikacím na zařízeních, která nejsou specifikována.
- Nebo selektivně vymazat podniková data na zařízeních, která nejsou specifikována. 

Uživatel nebude moct přistupovat k cílové aplikaci, pokud nebudou splněny požadavky prostřednictvím zásad. Na základě nastavení může být uživatel zablokován nebo mu mohou být v aplikaci vymazána podniková data. Na zařízeních s iOSem tato funkce vyžaduje zapojení aplikací (jako jsou WXP, Outlook, Managed Browser, Yammer), aby integrovaly sadu Intune App SDK. V opačném případě nebude možné vynutit tuto funkci v cílových aplikacích. K této integraci dochází průběžně a závisí na týmech konkrétních aplikací. Na Androidu tato funkce vyžaduje nejnovější verzi Portálu společnosti. 

Na zařízeních koncových uživatelů klient Intune provede akci založenou na jednoduché shodě řetězců zadaných v okně Intune pro zásady ochrany aplikací. Závisí to zcela na hodnotě, kterou zařízení vykazuje. Doporučujeme správci IT, aby zajistil přesnost zamýšleného chování. Toho se dá dosáhnout testováním tohoto nastavení na základě různých výrobců a modelů zacílených na malé skupiny uživatelů. Pokud si chcete zobrazit a přidat zásady ochrany aplikací, vyberte v Microsoft Intune **Klientské aplikace** > **Zásady ochrany aplikací**. Další informace o zásadách ochrany aplikací najdete v článku [Co jsou zásady ochrany aplikací](app-protection-policy.md) a [Selektivní vymazání dat pomocí akcí přístupu zásad ochrany aplikací v Intune](app-protection-policies-access-actions.md).

#### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>Přístup k systému macOS portál společnosti předběžné verze sestavení <!-- 1734766 -->
Pomocí aplikace Microsoft AutoUpdate se můžete zapojit do programu Insider a získávat tak buildy dříve. Registrace vám umožní používat aktualizovaný Portál společnosti předtím, než bude k dispozici koncovým uživatelům. Další informace najdete na [blogu Microsoft Intune](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Vytvoření zásad dodržování předpisů zařízení pomocí nastavení brány Firewall na zařízeních s macOS <!-- 1497640 -->
Při vytváření nových zásad dodržování předpisů systému macOS (**Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu** > **Platforma: macOS** > **Zabezpečení systému**) jsou dostupná některá nová nastavení pro **bránu firewall**: 

- **Brána firewall**: Nakonfigurovat jak příchozí připojení jsou zpracovávány ve vašem prostředí.
- **Příchozí připojení**: **Blok** všechna příchozí připojení s výjimkou souborů požadovaných pro základní internetové služby, například DHCP, Bonjour a IPSec. Toto nastavení blokuje také všechny služby sdílení.
- **Neviditelný režim**: **Povolit** neviditelný režim, který zabrání zařízení v odpovídání na zjišťovací požadavky. Oprávněným aplikacím bude zařízení dále odpovídat na příchozí žádosti.

Platí pro: macOS 10.12 a novější

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Nový profil Wi-Fi zařízení konfigurace pro Windows 10 a novější <!-- 1879077 -->
V současné době můžete importovat a exportovat profily Wi-Fi pomocí souborů XML. S touto aktualizací můžete vytvořit konfigurační profil Wi-Fi zařízení přímo v Intune, podobně jako na některých jiných platformách.

Pokud chcete vytvořit profil, otevřete položku **Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** > **Wi-Fi**. 

Platí pro Windows 10 a novější.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>Beznabídkový režim – zastaralé je zobrazena šedě a nelze změnit <!-- 2149998 -->
Beznabídkový režim (preview) funkce (**konfigurace zařízení** > **profily** > **vytvořit profil**  >   **Windows 10 a novější** > **omezení zařízení**) je zastaralý a nahrazen [nastavení beznabídkového režimu pro Windows 10 a novější](kiosk-settings.md). Položka **Veřejný terminál (zastaralé)** se v této aktualizaci zobrazuje šedě a uživatelské rozhraní neumožňuje změny ani aktualizace. 

Pokud budete chtít povolit režim veřejného terminálu, podívejte se na článek[Nastavení veřejného terminálu pro Windows 10 a novější](kiosk-settings.md).

Platí pro: Windows 10 a novější, Windows Holographic for Business.

#### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>Rozhraní API používat 3. stran certifikační autority <!-- 2184013 -->
V této aktualizaci je k dispozici rozhraní API založené na Javě, které umožňuje integraci nezávislých certifikačních autorit s Intune a protokolem SCEP. Uživatelé pak budou moct přidat certifikát SCEP do profilu a použít ho pro zařízení využívající MDM.

V současné době Intune podporuje [žádosti protokolu SCEP používající Active Directory Certificate Services](certificates-scep-configure.md).

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>Přepnout zobrazení nebo není zobrazeno tlačítko Ukončit relaci v prohlížeči Kiosk <!-- 2455253 -->
Nyní můžete nakonfigurovat, jestli se má v prohlížečích Kiosk zobrazovat tlačítko pro ukončení relace. Tento ovládací prvek najdete v části **Konfigurace zařízení** > **Beznabídkový režim (Preview)** > **Kiosk Web Browser**. Pokud toto tlačítko zapnete a uživatel na něj klikne, zobrazí aplikace výzvu k potvrzení ukončení relace. Po potvrzení prohlížeč vymaže všechny údaje o procházení a přejde zpátky na výchozí adresu URL.

#### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>Vytvoření mobilní konfigurace profilu karty eSIM <!-- 2564077 -->
V části **Konfigurace zařízení** můžete vytvořit mobilní profil eSIM. Můžete naimportovat soubor, který obsahuje mobilní aktivační kódy poskytnuté vaším mobilním operátorem. Pak můžete tyto profily nasadit do zařízení s Windows 10 podporujících eSIM LTE, jako je například Surface Pro LTE a další zařízení podporující eSIM.

Zkontrolujte, jestli vaše [zařízení podporuje profily eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Platí pro Windows 10 a novější. 

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>Výběr kategorií zařízení pomocí nastavení přístup do práce nebo do školy <!-- 1058963 eenotready --> 
Pokud jste povolili [mapování skupin zařízení](https://docs.microsoft.com/intune/device-group-mapping), uživatelům s Windows 10 se teď po registraci prostřednictvím tlačítka **Připojit** v **Nastavení** > **Účty** > **Přístup do práce nebo do školy** zobrazí výzva k výběru kategorie zařízení. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Použít sAMAccountName jako uživatelské jméno účtu e-mailových profilů <!-- 1500307 -->
Můžete používat místní **sAMAccountName** jako uživatelské jméno účtu pro e-mailové profily v Androidu, iOSu a Windows 10. Můžete také získat doménu z atributu `domain` nebo `ntdomain` v Azure Active Directory (Azure AD). Nebo budete moct zadat vlastní statickou doménu.

Pokud chcete tuto funkci používat, musíte atribut `sAMAccountName` synchronizovat z místního prostředí Active Directory do Azure AD.

Platí pro [Android](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 a novější](email-settings-windows-10.md).

#### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Zobrazení profilů konfigurace zařízení v konfliktu <!-- 1556983 -->
V části **Konfigurace zařízení** se zobrazuje seznam existujících profilů. S touto aktualizací se přidá nový sloupec, který bude poskytovat podrobné informace o profilech, u kterých došlo ke konfliktu. Výběrem řádku s konfliktem můžete zobrazit nastavení a profil, u kterého se konflikt vyskytl. 

Přečtěte si další informace o [správě konfiguračních profilů](device-profile-monitor.md#view-conflicts).

#### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Nový stav pro zařízení v dodržování předpisů zařízením <!-- 2308882 -->
Na stránku **Dodržování předpisů zařízením** > **Zásady** > vyberte zásadu > **Přehled** jsou přidané následující nové stavy:
- Úspěšné
- Chyba
- Konflikt
- Čekající na vyřízení
- Nepoužitelné Také se zobrazí obrázek, který ukazuje počet zařízení s jinou platformou. Když se třeba díváte na profil iOSu, na nové dlaždici se zobrazí počet zařízení s jiným systémem než iOS, která jsou také přiřazená k tomuto profilu. Viz [Zásady dodržování předpisů zařízením](compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Dodržování předpisů u zařízení podporuje 3. stran antivirových řešení <!-- 2325484 -->
Když vytvoříte zásadu dodržování předpisů (**dodržování předpisů zařízením** > **zásady** > **vytvořit zásadu**  >  **Platformy: Windows 10 a novější** > **nastavení** > **zabezpečení systému**), existují nové **[zabezpečení zařízení](compliance-policy-create-windows.md#windows-10-and-later-policy-settings)** možnosti: 
- **Antivirová ochrana v programu**: Pokud je nastavena na **vyžadují**, můžete zkontrolovat dodržování předpisů pomocí antivirových řešení, které jsou registrovány Windows Security Center, jako je například Symantec a programem Windows Defender. 
- **AntiSpyware**: Pokud je nastavena na **vyžadují**, můžete zkontrolovat dodržování předpisů pomocí antispywaru řešení, které jsou registrovány v systému Windows Security Center, jako je například Symantec a programem Windows Defender. 

Platí pro: Windows 10 a novější 

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Automatické označení zařízení s Androidem registrovaných pomocí technologie Samsung Knox Mobile Enrollment jako firemních <!-- 2404851 -->
Ve výchozím nastavení se zařízení s Androidem registrovaná pomocí technologie Samsung Knox Mobile Enrollment označují v poli **Vlastnictví zařízení** jako **Firemní**. Před registrací pomocí technologie Knox Mobile Enrollment nemusíte firemní zařízení identifikovat ručně pomocí IMEI nebo sériových čísel.

####  <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens----1853904---"></a>Zařízení bez profilů sloupec v seznamu tokeny programu registrace <!-- 1853904 -->
V seznamu tokenů programu registrace se nachází nový sloupec, který zobrazuje počet zařízení bez přiřazeného profilu. Pomáhá správcům při přiřazování profilů těmto zařízením před jejich přidělením uživatelům. Pokud chcete tento nový sloupec zobrazit, přejděte na **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace**.

### <a name="device-management"></a>Správa zařízení

#### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Hromadné odstranění zařízení v okně zařízení <!-- 1793693 -->
V okně Zařízení můžete odstranit více zařízení najednou. Zvolte **Zařízení** > **Všechna zařízení** > vyberte zařízení, která chcete odstranit > **Odstranit**. U zařízení, která nejde odstranit, se zobrazí upozornění.

#### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Změny názvů Google pro zařízení s Androidem for Work a Play for Work <!--842873 -->
Intune aktualizoval terminologii „Android for Work“ tak, aby odrážela změny brandingu společnosti Google. Termíny „Android for Work“ a „Play for Work“ se už nepoužívají. V závislosti na kontextu se používá jiná terminologie:
- Termín „Android Enterprise“ označuje celkovou moderní sadu správy Androidu.
- Termín „Pracovní profil“ nebo „Vlastník profilu“ označuje vlastní zařízení uživatelů (BYOD) spravovaná pomocí pracovních profilů.
- Termín „Spravovaný obchod Google Play“ označuje Google App Store.

#### <a name="rules-for-removing-devices----1609459---"></a>Pravidla odebírání zařízení <!-- 1609459 -->
Jsou k dispozici nová pravidla, která vám umožňují automaticky odebrat zařízení, která se nastavený počet dnů neohlásila. Pokud chcete nové pravidlo zobrazit, přejděte do podokna **Intune** a vyberte **Zařízení** a **Pravidla čištění zařízení**.

#### <a name="corporate-owned-single-use-support-for-android-devices----1630973---"></a>Podpora použití vlastněné společností, jeden pro zařízení s Androidem <!-- 1630973 -->

Intune teď podporuje zamykatelná zařízení s beznabídkovým režimem Androidu a s vysokou úrovní správy. To správcům umožní další uzamčení použití zařízení na jednu aplikaci nebo malou sadu aplikací a zabrání uživatelům povolit na zařízení jiné aplikace nebo na něm provádět jiné akce. Pokud chcete nastavit beznabídkový režim Androidu, přejděte do Intune > **Registrace zařízení** > **Registrace Androidu** > **Beznabídkový režim a registrace zařízení úloh**. Další informace najdete v článku o [nastavení registrace zařízení s beznabídkovým režimem Androidu Enterprise](android-kiosk-enroll.md).

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794--"></a>Nahrát na řádek přehled identifikátory podnikových zařízení duplicitní <!-- 2203794-->
Při nahrávání firemních ID teď Intune poskytuje seznam duplicit a nabídne možnost nahradit nebo ponechat existující informace. Sestava se zobrazí, pokud vzniknou duplicity, když zvolíte **Registrace zařízení** > **Identifikátory podnikových zařízení** > **Přidat identifikátory**. 

#### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Ručně přidat identifikátory podnikových zařízení <!-- 2203803 -->
Teď je možné přidat ID podnikových zařízení ručně. Zvolte **Registrace zařízení** > **Identifikátory podnikových zařízení** > **Přidat**. 


<!-- ########################## -->
## <a name="june-2018"></a>Červen 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="microsoft-edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Mobilní podpora Microsoft Edge pro zásady ochrany aplikací Intune <!-- 1817882 -->
Prohlížeč Microsoft Edge pro mobilní zařízení nyní podporuje zásady ochrany aplikací definované v Intune.

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Načtení uživatelského modelu aplikace přidružené ID (AUMID) pro Microsoft Store pro obchodní aplikace v celoobrazovkovém režimu. <!-- 1560077 ! -->
Intune teď může načíst identifikátory AUMID pro aplikace Microsoft Store pro firmy (WSfB), aby bylo možné poskytnout vylepšenou konfiguraci profilu beznabídkového režimu.

Další informace o aplikacích pro Microsoft Store pro firmy najdete v článku [Správa aplikací z Microsoft Storu pro firmy](windows-store-for-business.md).

#### <a name="new-company-portal-branding-page----1916370---"></a>Přizpůsobení prostředí značce stránku portálu společnosti New <!-- 1916370 -->
Stránka brandingu Portálu společnosti obsahuje nové rozložení, zprávy a popisky.


### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="pradeo---new-mobile-threat-defense-partner----1169249---"></a>Pradeo – nový partner ochrany před mobilními hrozbami <!-- 1169249 -->
Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Pradeo. Je to řešení ochrany před mobilními hrozbami integrované ve službě Microsoft Intune.

#### <a name="use-fips-mode-with-the-ndes-certificate-connector----1333688---"></a>Použití režimu FIPS s konektorem NDES certifikátu <!-- 1333688 -->
Když jste nainstalovali konektor NDES Certificate na počítač se zapnutým režimem FIPS (Federal Information Processing Standard), vydávání a odvolávání certifikátů nefungovalo podle očekávání. Díky této aktualizaci bude konektor NDES Certificate standard FIPS podporovat. 

Tato aktualizace také zahrnuje:

- Konektor NDES Certificate vyžaduje rozhraní .NET 4.5 Framework, které je automaticky součástí Windows Serveru 2016 a Windows Serveru 2012 R2. Dříve bylo minimální požadovanou verzí rozhraní .NET 3.5 Framework.
- NDES Certificate Connector podporuje také protokol TLS 1.2. Pokud server s nainstalovaným NDES Certificate Connectorem podporuje TLS 1.2, použije se TLS 1.2. Pokud server nepodporuje TLS 1.2, použije se TLS 1.1. V současnosti se k ověřování zařízení a serveru používá protokol TLS 1.1.

Další informace najdete v tématech o [konfiguraci a použití certifikátů SCEP](certificates-scep-configure.md) a [konfiguraci a použití certifikátů PKCS](certficates-pfx-configure.md).

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680----"></a>Podporu pro Palo Alto Networks GlobalProtect VPN profily <!-- 1333680 ! -->
S touto aktualizací můžete zvolit Palo Alto Networks GlobalProtect jako typ připojení VPN pro profily VPN v Intune (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Typ profilu** > **VPN**). V této vydané verzi se podporují následující platformy: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Další nastavení možností místního zabezpečení zařízení <!-- 1403702 -->
U zařízení s Windows 10 teď můžete nakonfigurovat další nastavení možností místního zabezpečení zařízení. Další nastavení jsou dostupná v oblastech Klient sítě Microsoft, Server sítě Microsoft, Přístup k síti a zabezpečení a Interaktivní přihlášení. Tato nastavení najdete v kategorii Ochrana koncového bodu při vytváření zásad konfigurace zařízení s Windows 10.

#### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Povolit režim veřejného terminálu na zařízeních s Windows 10 <!-- 1560072 ! -->
Na zařízeních s Windows 10 můžete vytvořit konfigurační profil a povolit beznabídkový režim (**Konfigurace zařízení** > **Profily** > **Vytvořit profil**  >  **Windows 10** > **Omezení zařízení** > **Beznabídkový režim**). V této aktualizaci je nastavení **Beznabídkový režim (Preview)** přejmenováno na **Beznabídkový režim (zastaralé)**. **Beznabídkový režim (zastaralé)** už nedoporučujeme používat, do červnové aktualizace ale zůstane funkční. **Beznabídkový režim (zastaralé)** se nahrazuje novým typem profilu **Beznabídkový režim** (**Vytvořit profil** > **Windows 10**  >  **Beznabídkový režim (Preview)**), který bude obsahovat nastavení pro konfiguraci beznabídkového režimu na systému Windows 10 RS4 a novějším.

Platí pro Windows 10 a novější.

#### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Graf grafického uživatelského profilu zařízení je zpět <!-- 2160133 -->
Při vylepšování číselných počtů zobrazených v grafu profilu zařízení (**Konfigurace zařízení** > **Profily** > vyberte existující profil > **Přehled**) byl uživatelský graf dočasně odebrán.

V této aktualizaci se uživatelský graf vrací a zobrazuje se na portálu Azure Portal.

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication----1165118---"></a>Podpora pro registraci Windows Autopilotu bez ověřování uživatelů <!-- 1165118 -->
Intune teď podporuje registraci pomocí řešení Windows Autopilot bez ověření uživatele. Je to nová možnost v profilu nasazení Windows Autopilot, která nastavuje režim automatického nasazení.  Pokud chcete úspěšně dokončit tento typ registrace, musí zařízení běžet na sestavení Windows 10 Insider Preview 17672 nebo novějším a musí mít čip TPM 2.0. Vzhledem k tomu, že se nevyžaduje žádné ověřování uživatelů, byste tuto možnost měli přiřazovat jenom pro zařízení, nad kterými máte fyzickou kontrolu.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Nové nastavení jazyk a oblast, při konfiguraci OOBE pro Autopilot <!-- 1821766 -->
Nové nastavení konfigurace je dostupné pro nastavení jazyka a oblasti pro profily Autopilot během prvního spuštění počítače. Když chcete toto nové nastavení zobrazit, zvolte **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > **Vytvořit profil** > **Režim nasazení** = **Nasazení sebou samým** > **Nakonfigurovaly se výchozí hodnoty**.

#### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nové nastavení pro konfiguraci zařízení klávesnice <!-- 1821768 -->
Nové nastavení bude dostupné pro konfiguraci klávesnice pro profily Autopilot během prvního spuštění počítače. Když chcete toto nové nastavení zobrazit, zvolte **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > **Vytvořit profil** > **Režim nasazení** = **Nasazení sebou samým** > **Nakonfigurovaly se výchozí hodnoty**.

#### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Přesunutí profilů AutoPilot do cílení na skupiny <!-- 1877935 -->
Profily nasazení AutoPilot můžete přiřadit skupinám Azure AD, které obsahují zařízení AutoPilot.

### <a name="device-management"></a>Správa zařízení

#### <a name="set-compliance-by-device-location----851881----"></a>Nastavit dodržování předpisů podle umístění zařízení <!-- 851881 ! -->
Někdy můžete chtít omezit přístup k podnikovým prostředkům na konkrétní umístění definovaná podle síťového připojení. Teď můžete vytvořit zásady dodržování předpisů (**Dodržování předpisů zařízením** > **Umístění**) na základě IP adresy zařízení. Pokud se zařízení přesune mimo rozsah IP adres, nebude moct přistupovat k podnikovým prostředkům.

Platí pro: Používejte zařízení s Androidem verze 6.0 nebo novější s aktualizovanou aplikací Portál společnosti.

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Zabránit uživatelských aplikací a prostředí na zařízeních s Windows 10 Enterprise RS4 Autopilot<!-- 1621980 -->
Budete moct zabránit v instalaci uživatelských aplikací a prostředí na zařízeních Windows 10 Enterprise RS4 AutoPilot. Když chcete tuto funkci zobrazit, přejděte na **Intune** > **Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Platforma** = **Windows 10 nebo novější** > **Typ profilu** = **Omezení zařízení** > **Konfigurovat** > **Windows Spotlight** > **Uživatelské funkce**. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948---"></a>Odinstalace nejnovější aktualizace softwaru Windows 10 <!-- 1732948 -->
Pokud na počítačích s Windows 10 najdete problém způsobující chybu, můžete se rozhodnout odinstalovat (vrátit zpět) nejnovější aktualizaci funkcí nebo nejnovější aktualizaci kvality. Odinstalace aktualizace funkcí nebo kvality je dostupná jenom pro kanál pro údržbu, ve kterém se dané zařízení nachází. Při odinstalaci se aktivují zásady, které na počítačích s Windows 10 obnoví předchozí aktualizaci. Konkrétně u aktualizací funkcí je možné omezit dobu 2 až 60 dnů, po kterou lze provést odinstalaci nejnovější verze. Pokud chcete nastavit možnosti odinstalace aktualizací softwaru, vyberte na webu Azure Portal v okně **Microsoft Intune** možnost **Aktualizace softwaru**. Pak v okně **Aktualizace softwaru** vyberte **Aktualizační kanály Windows 10**. Pak můžete v části **Přehled** zvolit možnost **Odinstalovat**.

#### <a name="search-all-devices-for-imei-and-serial-number----1793685---"></a>Vyhledávání všech zařízení IMEI a sériové číslo <!-- 1793685 -->
Teď můžete hledat IMEI a sériová čísla v okně Všechna zařízení (pole pro e-mail, hlavní název uživatele (UPN), název zařízení a název správy jsou nadále dostupná). V Intune zvolte **Zařízení** > **Všechna zařízení** a do vyhledávacího pole zadejte hledanou položku.

#### <a name="management-name-field-will-be-editable----1875989---"></a>Pole s názvem Management bude možné upravovat <!-- 1875989 -->
Teď můžete v okně **Vlastnosti** příslušného zařízení upravovat pole Název správy. Pokud chcete toto pole upravit, vyberte **Zařízení** > **Všechna zařízení** > vyberte zařízení > **Vlastnosti**. Pole s názvem správy můžete použít k jednoznačné identifikaci zařízení.

#### <a name="new-all-devices-filter-device-category----1878520---"></a>Nové všechna zařízení filtru: Kategorie zařízení <!-- 1878520 -->
Teď můžete filtrovat seznam **Všechna zařízení** podle kategorie zařízení. Když to chcete udělat, zvolte **Zařízení** > **Všechna zařízení** > **Filtrovat** > **Kategorie zařízení**.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>Použití Teamvieweru pro iOS sdílení obrazovky a zařízení s MacOS <!-- 1985547 -->
Správci se teď můžou připojit k [TeamVieweru](device-profile-android-teamviewer.md) a spustit relaci sdílení obrazovky se zařízeními s iOSem a macOS. Uživatelé iPhonů, iPadů a zařízení s macOS mohou své obrazovky živě sdílet s libovolnými jinými stolními nebo mobilními zařízeními. 

#### <a name="multiple-exchange-connector-support----2070451---"></a>Podpora více Exchange Connectorů <!-- 2070451 -->
Už neplatí omezení v podobě jednoho Microsoft Intune Exchange Connectoru na každého tenanta. Intune teď podporuje více Exchange Connectorů, takže můžete nastavit podmíněný přístup Intune s více organizacemi místního Exchange.

S místním konektorem Exchange v Intune můžete spravovat přístup zařízení k místním poštovním schránkám Exchange podle toho, jestli je zařízení zaregistrované v Intune a splňuje zásady dodržování předpisů zařízením. Konektor nastavíte tak, že místní konektor Exchange v Intune stáhnete z portálu Azure Portal a nainstalujete ho na server v organizaci Exchange. Na řídicím panelu Microsoft Intune zvolte **Místní přístup** a pak v **Nastavení** vyberte **Konektor Exchange ActiveSync**. Stáhněte místní konektor Exchange a nainstalujte ho na server v organizaci Exchange. Protože už teď neplatí omezení v podobě jednoho konektoru Exchange na každého tenanta, pokud máte další organizace Exchange, můžete stejným postupem stáhnout a nainstalovat konektor pro každou další organizaci Exchange.

#### <a name="new-device-hardware-detail-ccid----2156657---"></a>Nové podrobnosti o hardwaru zařízení: CCID <!-- 2156657 -->
U každého zařízení je teď uvedený údaj CCID (Chip Card Interface Device). Když ho chcete zobrazit, zvolte **Zařízení** > **Všechna zařízení** > zvolte zařízení > **Hardware** a zkontrolujte část **Podrobnosti o síti**>.

#### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Přiřadit jako obor skupiny všichni uživatelé a všechna zařízení <!-- 2196803 -->
Všechny uživatele, všechna zařízení a všechny uživatele a zařízení teď můžete přiřadit do skupin oborů. Když to chcete udělat, zvolte **Role Intune** > **Všechny role** > **Správce zásad a profilů** > **Přiřazení** > zvolte přiřazení > **Rozsah (Skupiny)**.

#### <a name="udid-information-now-included-for-ios-and-macos-devices----2219806---"></a>Informace o UDID zahrnuté pro zařízení s Iosem a macOS <!-- 2219806 -->
Když chcete identifikátor UDID (Unique Device Identifier) pro zařízení s iOSem a macOS zobrazit, přejděte na **Zařízení** > **Všechna zařízení** > zvolte zařízení > **Hardware**. Identifikátor UDID je dostupný jenom pro firemní zařízení (podle nastavení v části **Zařízení** > **Všechna zařízení** > zvolte zařízení > **Vlastnosti** > **Vlastnictví zařízení**).

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Vylepšení odstraňování potíží pro instalaci aplikace <!-- 928990 -->
U zařízení spravovaných pomocí Microsoft Intune MDM může občas dojít k chybě instalace. Když k těmto chybám instalace dojde, může být obtížné pochopit, proč k nim došlo nebo je odstranit. Spouštíme verzi Public Preview našich funkcí řešení potíží s aplikacemi. U každého jednotlivého zařízení si všimnete nového uzlu **Spravované aplikace**. Jedná se o seznam aplikací, které byly dodány prostřednictvím MDM Intune. Uvnitř uzlu uvidíte seznam stavů instalací aplikací. Pokud vyberete konkrétní aplikaci, uvidíte zobrazení řešení potíží pro tuto konkrétní aplikaci. V zobrazení řešení potíží se zobrazí úplný životní cyklus aplikace, například kdy byla aplikace vytvořena, upravena, zacílena a dodána do zařízení. Pokud navíc nebyla instalace aplikace úspěšná, zobrazí se vám kód chyby a užitečná zpráva týkající se příčiny chyby. 

#### <a name="intune-app-protection-policies-and-microsoft-edge----1818968---"></a>Zásady ochrany aplikací Intune a Microsoft Edge <!-- 1818968 -->
Prohlížeč Microsoft Edge pro mobilní zařízení (iOS a Android) teď podporuje zásady ochrany aplikací Microsoft Intune. Uživatelé zařízení s iOSem a Androidem, kteří se přihlásí svými podnikovými účty Azure AD k aplikaci Edge, budou chráněni službou Intune. Na zařízeních s iOSem umožní zásada **Vyžadovat spravovaný prohlížeč pro webový obsah** uživatelům otevírat odkazy v Microsoft Edgi, pokud je spravovaný.

<!-- ########################## -->
## <a name="may-2018"></a>Květen 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Konfigurace zásad ochrany aplikací <!-- 2144597 Part 2 -->

Na portálu Azure Portal nyní přejdete přímo do Intune a nikoli do okna služby Intune App Protection. Pro zásady ochrany aplikací v rámci Intune nově existuje pouze jedno umístění. Všimněte si, že všechny vaše zásady ochrany aplikací se nacházejí v okně **Mobilní aplikace** v Intune v části **Zásady ochrany aplikací**. Tato integrace usnadňuje práci se správou cloudu. Nezapomeňte, že všechny zásady ochrany aplikací jsou už přenesené do Intune a kterékoli z předem nakonfigurovaných zásad můžete upravit. Zásady ochrany aplikací Intune a podmíněného přístupu se nově nacházejí v části **Podmíněný přístup**, kterou najdete v části **Spravovat** v okně **Microsoft Intune** nebo v části **Zabezpečení** v okně **Azure Active Directory**. Podrobnosti o úpravách zásad podmíněného přístupu najdete v tématu [Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Další informace viz téma [Co jsou zásady ochrany aplikací](app-protection-policy.md).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Vyžadovat instalaci profily zásad, aplikací, certifikátů a sítí <!-- 1553555 -->
Správci můžou blokovat koncovým uživatelům v přístupu k desktopu Windows 10 RS4, dokud Intune nenainstaluje zásady, aplikace a profily certifikátů a sítí při zřizování zařízení AutoPilot. Další informace najdete v článku [Nastavení stránky stavu registrace](windows-enrollment-status.md).

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Podpora mobilních registrace Samsung Knox <!--1112863-->
Pokud Intune používáte s technologií Samsung Knox Mobile Enrollment (KME), můžete registrovat velké počty zařízení s Androidem vlastněné společností. Uživatelé připojení prostřednictvím Wi-Fi nebo mobilních sítí mohou svá zařízení při prvním zapnutí registrovat několika klepnutími. Při použití aplikace Knox Deployment App se mohou zařízení registrovat pomocí Bluetooth nebo NFC. Další informace najdete v článku věnovaném [automatické registraci zařízení s Androidem pomocí technologie Knox Mobile Enrollment od Samsungu](android-samsung-knox-mobile-enroll.md).

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží 

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Prosím o pomoc v aplikaci portál společnosti pro Windows 10 <!-- 1874137 -->
Portál společnosti pro Windows 10 teď odesílá protokoly aplikace přímo Microsoftu, když uživatel iniciuje pracovní postup pro získání pomoci s problémem. Usnadní se tak řešení problémů, které jsou předávány Microsoftu.

<!-- ########################## -->
## <a name="april-2018"></a>Duben 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Podpora hesla pro kód PIN MAM na Androidu<!-- 1438086 -->

Správci Intune mohou nastavit požadavek, aby se při spuštění aplikace povinně zadávalo heslo místo číselného kódu PIN MAM. Při takové konfiguraci musí uživatel po zobrazení výzvy nastavit a používat heslo, aby získal přístup k aplikacím s podporou MAM. Heslo je definované jako číselný kód PIN s aspoň jedním speciálním znakem nebo velkým/malým písmenem. Intune podporuje heslo podobným způsobem jako existující číselný kód PIN, umožňuje stanovit minimální délku a povoluje opakování znaků a sekvencí prostřednictvím konzoly pro správu. Tato funkce vyžaduje nejnovější verzi Portálu společnosti na Androidu. Tato funkce je už k dispozici pro iOS.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Podpora aplikací – obchodní (LOB) pro macOS <!-- 1473977 -->
Microsoft Intune bude poskytovat možnost instalace obchodních aplikací pro macOS z portálu Azure Portal. Do Intune budete moct přidat obchodní aplikaci pro masOS poté, co ji předběžně zpracoval nástroj dostupný v GitHubu. Na portálu Azure Portal v okně **Intune** zvolte **Klientské aplikace**. V okně **Klientské aplikace** zvolte **Aplikace** > **Přidat**. V okně **Přidat aplikaci** vyberte **Obchodní aplikace**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-enterprise-work-profile-app-assignment----1813073---"></a>Přiřazení profilu aplikace fungovat integrované všichni uživatelé a všechny skupiny zařízení pro Android Enterprise <!-- 1813073 -->
K přiřazení aplikace pracovního profilu Android Enterprise můžete použít předdefinované skupiny **Všichni uživatelé** a **Všechna zařízení**. Podrobnosti najdete v tématu [Zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune](apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Intune přeinstaluje požadované aplikace, které odinstalovali uživatelé <!-- 1947010 -->
Pokud koncový uživatel odinstaluje některou z povinných aplikací, Intune nečeká na sedmidenní cyklus vyhodnocení a během 24 hodin ji automaticky znovu nainstaluje.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Aktualizace místa, kde konfigurujete zásady ochrany aplikací <!-- 2144597 -->

Na portálu Azure Portal v rámci služby Microsoft Intune vás dočasně přesměrujeme z okna služby **Intune App Protection** do okna **Mobilní aplikace**. Všechny vaše zásady ochrany aplikací se už nacházejí v okně **Mobilní aplikace** v Intune v oblasti konfigurace aplikací. Místo přechodu na službu Intune App Protection přejdete přímo na Intune. V dubnu 2018 toto přesměrování ukončíme a okno služby **Intune App Protection** úplně odebereme, aby se zásady ochrany aplikací nacházely v Intune jen na jednom místě. 

**Co to pro mě znamená?**
Tato změna ovlivní jak zákazníky samostatné verze Intune, tak zákazníky hybridní verze (Intune s Configuration Managerem). Tato integrace pomůže zjednodušit práci se správou cloudu.

**Jak se mám na tuto změnu připravit?**
Místo okna služby **Intune App Protection** si do oblíbených položek přidejte **Intune** a seznamte se s pracovním postupem zásad ochrany aplikací v okně **Mobilní aplikace** v Intune. Po krátkém období přesměrování okno **App Protection** odebereme. Nezapomeňte, že všechny zásady ochrany aplikací jsou už přenesené do Intune a kterékoli ze zásad podmíněného přístupu můžete upravit. Podrobnosti o úpravách zásad podmíněného přístupu najdete v tématu [Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Další informace viz téma [Co jsou zásady ochrany aplikací](app-protection-policy.md). 

### <a name="device-configuration"></a>Konfigurace zařízení

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153---"></a>Zařízení profil graf a seznam stavů zobrazují všechna zařízení ve skupině <!-- 1449153 -->
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

Pro vzdělávací profily jsou k dispozici v rámci nové nastavení **tiskárny** kategorie: **Tiskárny**, **výchozí tiskárna**, **přidat nové tiskárny**.

#### <a name="show-caller-id-in-personal-profile---android-enterprise-work-profile---1098984---"></a>Zobrazení ID volajícího v osobním profilu – pracovní profil Androidu Enterprise <!--1098984 -->
Při použití osobního profilu na zařízení nemusí koncoví uživatelé vidět podrobnosti ID volajícího z pracovního kontaktu. 

Od této aktualizace je v části **Android Enterprise** > **Omezení zařízení** > **Nastavení pracovního profilu** k dispozici nové nastavení:
- Zobrazit v osobním profilu ID volajícího pracovního kontaktu

Pokud je povoleno (nenakonfigurováno), podrobnosti volajícího pracovního kontaktu se v osobním profilu zobrazují. V případě blokování se číslo volajícího pracovního kontaktu v osobním profilu nezobrazuje. 

Platí pro: Zařízení s pracovním profilem Android v systému Android OS v6.0 a novějších

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Nové nastavení Credential Guard Windows Defender přidaná do nastavení ochrany koncového bodu <!--1102252 --><!--from 1802 and 1804-->

V této aktualizaci zahrnuje [ochrana Credential Guard v programu Windows Defender](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Konfigurace zařízení** > **Profily** > **Ochrana koncového bodu**) následující nastavení: 

- **Windows Defender Credential Guard**: Zapne Credential Guard se zabezpečením na základě virtualizace. Pokud je tato funkce zapnutá, budou po dalším restartování přihlašovací údaje chráněny **úrovní zabezpečení platformy, která je nastavená na zabezpečené spouštění,** a zapnutým **zabezpečením založeným na virtualizaci**. Vaše možnosti jsou:
  - **Zakázané**: Pokud Credential Guard byla dříve zapnutá pomocí **povoleno bez zámku**"možnost, pak ji vypne Credential Guard vzdáleně.

  - **Povoleno s uzamčením UEFI**: Zajišťuje, že Credential Guard nejde zakázat pomocí klíče registru nebo pomocí zásad skupiny. Pokud jste použili toto nastavení a chcete ochranu Credential Guard zakázat, musíte nastavit zásady skupiny na Zakázáno. Potom bezpečnostní funkci odeberte z každého počítače, u kterého je uživatel fyzicky přítomen. Tyto kroky smažou konfiguraci uloženou v rozhraní UEFI. Dokud je uložená konfigurace UEFI, je povolená i ochrana přihlašovacích údajů Credential Guard.

  - **Povoleno bez zámku**: Umožňuje Credential Guard zakázat vzdáleně pomocí zásad skupiny. Na zařízeních s tímto nastavením musí běžet přinejmenším Windows 10 (verze 1511).

Následující související technologie se při konfiguraci ochrany přihlašovacích údajů Credential Guard zapnou automaticky: 

  - **Povolit zabezpečení na základě virtualizace (VBS)**: Zapne založené na virtualizaci zabezpečení (VBS) při příštím restartování počítače. Zabezpečení na základě virtualizace nabízí podporu služeb zabezpečení pomocí hypervisoru Windows a vyžaduje zabezpečené spouštění.
  - **Zabezpečené spouštění s přímý přístup do paměti (DMA)**: Zapne VBS se zabezpečeným spouštěním a přímý přístup do paměti. Ochrana DMA vyžaduje hardwarovou podporu a povolí se jenom na správně nakonfigurovaných zařízeních. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Použijte název vlastního subjektu u certifikátu SCEP <!-- 2064190 -->
V profilu certifikátu SCEP můžete u vlastního subjektu použít běžný název **OnPremisesSamAccountName**. Můžete například použít `CN={OnPremisesSamAccountName})`.

####  <a name="block-camera-and-screen-captures-on-android-enterprise-work-profiles----1098977---"></a>Blokování kamery a snímků obrazovky na pracovní profily Androidu Enterprise <!-- 1098977 -->
Při konfiguraci omezení zařízení s Androidem jsou k dispozici dvě nové vlastnosti umožňující blokování: 
- Kamera: Blokuje přístup ke všem kamerám na zařízení
- Snímek obrazovky: Blokovat snímek obrazovky a tím také ochrana obsahu před zobrazením na zobrazovacích zařízeních, která nemají zabezpečený výstup videa

Platí pro pracovní profily Android Enterprise.

#### <a name="use-cisco-anyconnect-client-for-ios----1333708---"></a>Použití klienta Cisco AnyConnect pro iOS <!-- 1333708 -->

Když vytvoříte nový profil VPN pro iOS, jsou teď dvě možnosti: **Cisco AnyConnect** a **Cisco Legacy AnyConnect**. Profily Cisco AnyConnect podporují verzi 4.0.7x a novější. Stávající profily VPN Cisco AnyConnect pro iOS jsou označené jako **Cisco Legacy AnyConnect** a budou dál fungovat s Cisco AnyConnect 4.0.5x stejně jako dnes.

> [!NOTE]
> Tato změna platí jen pro iOS. Pro Android, pracovní profily Android Enterprise a macOS bude dál existovat jenom jedna možnost Cisco AnyConnect.


### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nové kroky registrace pro uživatele na zařízeních s macOS High Sierra 10.13.2+ <!--1734567 -->
Systém macOS high Sierra 10.13.2 představil nový koncept registrace MDM, který vyžaduje schválení uživatelem (User Approved). Schválené registrace umožňují v Intune spravovat některá citlivá nastavení zabezpečení. Další informace najdete v dokumentaci podpory Apple tady: https://support.apple.com/HT208019.

Zařízení zaregistrovaná v aplikaci Portál společnosti pro macOS se považují za neschválená uživatelem, dokud koncový uživatel neotevře předvolby systému a neschválí je ručně. Z tohoto důvodu nyní Portál společnosti pro macOS instruuje uživatele systému macOS 10.13.2 a novějšího, aby na konci procesu registrace přešli do příslušného umístění a ručně registraci schválili. Konzola správce Intune oznámí, zda je zaregistrované zařízení schváleno uživatelem.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>Nyní můžete zaregistrovat zařízení s macOS zaregistrovaných v Jamf s Intune <!-- 2370684 -->
Verze 1.3 a 1.4 portálu společnosti macOS neregistrovaly zařízení Jamf do Intune úspěšně. Verze 1.4.2 portálu macOS tento problém řeší.

#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Aktualizované prostředí nápovědy v aplikaci portál společnosti pro Android <!-- 1631531 -->
Aktualizovali jsme prostředí nápovědy v aplikaci Portál společnosti pro Android, aby bylo v souladu s osvědčenými postupy pro platformu Android. Když teď dojde k potížím s aplikací, může uživatel klepnout na **Nabídka** > **Nápověda** a:
- Odeslat Microsoftu diagnostický protokol
- Odeslat e-mail s popisem problému a ID incidentu pracovníkovi podpory ve své společnosti  

Pokud si chcete aktualizované prostředí nápovědy prohlédnout, přejděte na [Odeslání protokolů e-mailem](/intune-user-help/send-logs-to-your-it-admin-by-email-android) a [Odeslání chyb do Microsoftu](/intune-user-help/send-logs-to-microsoft-android).


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nové registrace selhání trend graf a tabulka důvodů selhání <!-- 1471783 -->
Na stránce s přehledem registrací můžete vidět trend neúspěšných registrací a pět nejčastějších příčin selhání. Kliknutím na tento graf nebo tabulku můžete přejít k podrobnostem a najít rady pro řešení problémů a návrhy vedoucí k nápravě.


### <a name="device-management"></a>Správa zařízení

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----1629303---"></a>Rozšířené ochrany před internetovými útoky (ATP) a Intune jsou plně integrované <!-- 1629303 -->

[Rozšířená ochrana před internetovými útoky (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) zobrazuje úroveň rizika u zařízení s Windows 10. V Centru zabezpečení v programu Windows Defender (portál ATP) můžete vytvořit připojení k Microsoft Intune. Jakmile se vytvoří, pomocí zásad dodržování předpisů Intune se určí přijatelná úroveň ohrožení. Pokud se úroveň ohrožení překročí, zásady podmíněného přístupu služby Azure Active Directory (AD) můžou zablokovat přístup k různým aplikacím v organizaci.

Tato funkce umožňuje ochraně ATP kontrolovat soubory, zjišťovat hrozby a ohlašovat jakákoli rizika pro zařízení s Windows 10.

Přečtěte si článek o [povolení ochrany ATP s podmíněným přístupem v Intune](advanced-threat-protection.md).

#### <a name="support-for-user-less-devices----1637553---"></a>Podpora pro zařízení bez uživatele <!-- 1637553 -->
U zařízení bez určeného uživatele, jako je Microsoft Surface Hub, podporuje Intune hodnocení dodržování předpisů. Zásady dodržování předpisů mohou cílit na konkrétní zařízení. Dodržování (a nedodržování) předpisů je tedy možné stanovit i u zařízení, která nemají přiřazené uživatele.

#### <a name="delete-autopilot-devices----1713650---"></a>Odstranění zařízení Autopilot <!-- 1713650 -->
Správci Intune mohou [odstranit zařízení AutoPilot](enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Vylepšené zařízení odstranění prostředí <!--1832333 -->
Před [odstraněním zařízení z Intune](devices-wipe.md#delete-devices-from-the-intune-portal) už nemusíte odebírat firemní data ani na zařízení obnovovat tovární nastavení.

Pokud se chcete podívat na nové prostředí, přihlaste se k Intune a vyberte **Zařízení** > **Všechna zařízení** > název zařízení > **Odstranit**.

Pokud i nadále chcete potvrzovat vymazání nebo vyřazení, můžete použít standardní cestu životního cyklu zařízení a před **odstraněním** vybrat možnost **Odebrat firemní data** a **Obnovení továrního nastavení**. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Přehrávání zvuků v Iosu v režimu ztráty <!-- 1947769 -->
Pokud jsou sledovaná zařízení s iOSem v [režimu ztráty](device-lost-mode.md) MDM (Mobile Device Management), můžete [přehrát zvuk](device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Zařízení** > **Všechna zařízení** > vyberte zařízení s iOSem > **Přehled** > **Další**). Zvuk se přehrává, dokud je zařízení v režimu ztráty nebo na něm uživatel nevypne zvuk. Platí pro zařízení s iOSem 9.3 nebo novějším.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Blokování nebo povolení webových výsledků hledání na zařízení s Intune <!--1972804-->

Správci teď mohou na zařízení blokovat webové výsledky hledání.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Vylepšené zasílání zpráv pro chybě odeslání certifikátu Apple MDM Push Certificate <!-- 2172331 -->

Chybová zpráva vysvětluje, že při obnovení stávajícího certifikátu MDM je potřeba použít stejné Apple ID.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>Testování aplikace portál společnosti pro macOS na virtuálních počítačích <!-- 2216679 -->

Zveřejnili jsme pokyny, které správcům IT pomůžou testovat aplikaci Portál společnosti pro macOS na virtuálních počítačích s aplikacemi Parallels Desktop a VMware Fusion. Další informace najdete v článku [Registrace virtuálních počítačů s macOS pro účely testování](macos-enroll.md#enroll-virtual-macos-machines-for-testing).

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>Aktualizace uživatelského prostředí aplikace portál společnosti pro iOS <!--1412866 -->
Vydali jsme důležitou aktualizaci uživatelského prostředí aplikace Portál společnosti pro iOS. Tato aktualizace nabízí zcela přepracovaný vzhled aplikace, včetně modernějšího vzhledu a chování. Zachovali jsme funkčnost aplikace, ale zvýšili její využitelnost a přístupnost.  

Další vylepšení:
- Podpora pro iPhone X
- Rychlejší spouštění aplikace a odezva při načítání, které uživateli šetří čas
- Další indikátory průběhu, které uživatelům poskytují aktuální informace o stavu
- Vylepšené nahrávání protokolů, které usnadňuje hlášení vzniklých problémů  

Pokud si chcete nový vzhled prohlédnout, přejděte na [Co je nového v uživatelském rozhraní aplikace](whats-new-app-ui.md).

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca----1056954---"></a>Ochrana dat v místním systému Exchange pomocí aplikace v Intune a certifikační Autority <!-- 1056954 -->
Nově můžete chránit přístup k místním datům systému Exchange z Outlooku Mobile prostřednictvím zásad ochrany aplikací Intune a podmíněného přístupu. Pokud chcete na portálu Azure Portal přidat nebo upravit zásady ochrany aplikací, vyberte **Microsoft Intune** > **Klientské aplikace** > **Zásady ochrany aplikací**. Ještě než začnete tuto funkci využívat, zkontrolujte, že splňujete [požadavky na Outlook pro iOS a Android](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx).


### <a name="user-interface"></a>Uživatelské rozhraní

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Vylepšené dlaždice zařízení v aplikaci portál společnosti pro Windows 10 <!--2213364 -->

Aktualizovali jsme dlaždice, aby je dokázali přečíst i uživatelé se zhoršeným zrakem a aby fungovaly lépe s nástroji na čtení obrazovky.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Odesílání diagnostických hlášení v aplikaci portál společnosti pro macOS <!-- 2216677 -->
Aktualizovali jsme aplikaci Portál společnosti pro zařízení s macOS a zlepšili jsme způsob, jakým uživatelé nahlašují chyby týkající se Intune. Co aplikace Portál společnosti zaměstnancům umožňuje:

- Posílat diagnostická hlášení přímo vývojovému týmu Microsoft.
- Posílat e-mailem ID incidentů týmu IT podpory vaší společnosti.

Další informace najdete v článku o [posílání chyb ze zařízení s macOS](/intune-user-help/send-errors-macos).

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010---"></a>Intune se přizpůsobí Fluent Design System v aplikaci portál společnosti pro Windows 10 <!-- 1195010 -->
Aplikace Portál společnosti Intune pro Windows 10 byla aktualizována o [navigační zobrazení systému návrhu FDS](https://docs.microsoft.com/windows/uwp/design/basics/navigation-basics). Po straně aplikace je statický svislý seznam všech hlavních stránek. Když na odkaz kliknete, stránka se rychle zobrazí nebo můžete mezi stránkami přepínat. Jde o první z řady aktualizací, které jsou výsledkem naší trvalé snahy o vytvoření přizpůsobivého, empatického a známého prostředí Intune. Pokud si chcete nový vzhled prohlédnout, přejděte na [Co je nového v uživatelském rozhraní aplikace](whats-new-app-ui.md).

<!-- ########################## -->
## <a name="march-2018"></a>Březen 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Výstrahy, u nichž vyprší platnost – obchodní (LOB) pro aplikace pro iOS pro Microsoft Intune <!-- 748789 -->

Na portálu Azure Portal vás Intune upozorní na obchodní aplikace pro iOS, jejichž platnost brzy vyprší. Při nahrání nové verze obchodní aplikace pro iOS Intune oznámení o vypršení platnosti ze seznamu aplikací odebere. Toto oznámení o vypršení platnosti bude aktivní jen u nově nahraných obchodních aplikací pro iOS. 30 dní před vypršením platnosti profilu pro zřizování obchodních aplikací pro iOS se zobrazí upozornění. Potom se výstraha změní na Platnost vypršela.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Přizpůsobení motivů portálu společnosti pomocí šestnáctkových kódů <!--1049561 -->

Pomocí šestnáctkových kódů si můžete přizpůsobit barvu motivu v aplikacích Portál společnosti. Když zadáte šestnáctkový kód, Intune určí barvu textu, která poskytuje nejvyšší úroveň kontrastu mezi barvou textu a barvou pozadí. Můžete si zobrazit náhled barvy textu a loga společnosti oproti barvě v části **Klientské aplikace** > **Portál společnosti**.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Zahrnutí a vyloučení přiřazení aplikací na základě skupin pro Android Enterprise <!-- 1813081 -->

Android Enterprise (dříve Android for Work) umožňuje zahrnout nebo vyloučit skupiny, ale nepodporuje vytvořené integrované skupiny **Všichni uživatelé** a **Všechna zařízení**. Podrobnosti najdete v tématu [Zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune](apps-inc-exl-assignments.md).


### <a name="device-management"></a>Správa zařízení

### <a name="export-all-devices-into-csv-files-in-ie-microsoft-edge-or-chrome----2258071---"></a>Exportovat – všechna zařízení do souborů CSV v Internet Exploreru, Microsoft Edge nebo Chrome <!-- 2258071 -->
V části **Zařízení** > **Všechna zařízení** můžete **exportovat** zařízení do seznamu ve formátu CSV. Uživatelé Internet Exploreru s více než 10 000 zařízeními můžou zařízení úspěšně vyexportovat do více souborů. Každý z nich může obsahovat až 10 000 zařízení.

Uživatelé prohlížečů Edge a Chrome s více než 30 000 zařízeními můžou zařízení úspěšně vyexportovat do více souborů. Každý z nich může obsahovat až 30 000 zařízení.

V tématu [Správa zařízení](device-management.md) se dozvíte podrobnosti o tom, co můžete se spravovanými zařízeními dělat.

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Nová vylepšení zabezpečení ve službě Intune  <!-- 1637539 -->   

Do Intune v Azure jsme přidali přepínací tlačítko, pomocí kterého můžou zákazníci samostatné verze Intune zacházet se zařízením bez přiřazených zásad, jako by bylo **Vyhovující předpisům** (funkce zabezpečení vypnutá), nebo **Nevyhovující předpisům** (funkce zabezpečení zapnutá). To zajistí přístup k prostředkům až po vyhodnocení dodržování předpisů zařízením.

Dopad této funkce závisí na tom, zda už máte přiřazené zásady dodržování předpisů nebo nikoliv.

- Pokud patříte mezi nové nebo stávající účty a nemáte ke svým zařízením přiřazené žádné zásady dodržování předpisů, je tento přepínač automaticky nastaven na **Vyhovující předpisům**. V konzole bude je funkce ve výchozím nastavení vypnutá. Na koncové uživatele to nemá žádný vliv.
- Pokud patříte mezi stávající účty a máte nějaká zařízení, ke kterým jsou přiřazené zásady dodržování předpisů, je tento přepínač automaticky nastaven na **Nevyhovující předpisům**. Od zavedení březnové aktualizace je tato funkce ve výchozím nastavení zapnutá.

Pokud používáte zásady dodržování předpisů s podmíněným přístupem a tato funkce je zapnutá, jsou teď všechna zařízení bez alespoň jedné přiřazené zásady dodržování předpisů blokovaná podmíněným přístupem. Koncoví uživatelé přidružení k těmto zařízením, kteří měli předtím přístup k e-mailu, o tento přístup přijdou, dokud všem zařízením nepřiřadíte alespoň jednu zásadu dodržování předpisů.   

Mějte na paměti, že ačkoliv se výchozí stav tlačítka zobrazí v uživatelském rozhraní bezprostředně po březnových aktualizacích služby Intune, nevynutí se okamžitě. Veškeré provedené změny přepínacího tlačítka ovlivní dodržování předpisů zařízením až poté, co tlačítko na vašem účtu aktivujeme. Jakmile aktivaci dokončíme, informujeme vás prostřednictvím Centra zpráv. Po provedení březnových aktualizací to může trvat několik dní.

**Další informace**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Vylepšené zjišťování jailbreaků <!-- 846515 -->

Vylepšené zjišťování jailbreaků je novým nastavením dodržování předpisů, které zlepší způsob, jak Intune vyhodnocuje zařízení s jailbreakem. Toto nastavení způsobí, že se zařízení bude k Intune hlásit častěji. Využívají se k tomu polohové služby a ovlivňuje to vybíjení baterie.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Resetování hesel pro zařízení s Androidem O <!-- 1238299 -->
U zaregistrovaných zařízení s Androidem 8.0 a pracovním profilem můžete resetovat hesla. Když do zařízení s Androidem 8.0 pošlete žádost o resetování hesla, nastaví se aktuálnímu uživateli nové heslo pro odemčení zařízení nebo výzva spravovaného profilu. Po zaslání se heslo nebo výzva okamžitě projeví.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Cílení zásad dodržování předpisů k zařízením ve skupinách zařízení <!--1307012 -->

Můžete cílit zásady dodržování předpisů na uživatele ve skupinách uživatelů. Od této aktualizace můžete cílit zásady dodržování předpisů na zařízení ve skupinách zařízení. Zařízení cílená jako součást skupiny zařízení nebudou přijímat akce při nedodržení předpisů.

#### <a name="new-management-name-column----1333586---"></a>Nový sloupec název správy <!-- 1333586 -->
 V okně zařízení přibyl nový sloupec s názvem **Název správy**. Půjde o automaticky generovaný název bez možnosti úprav, který bude přiřazený podle zařízení na základě tohoto vzorce:
- Výchozí název pro všechna zařízení: <username><em><devicetype></em><enrollmenttimestamp>
- Pro hromadně přidaná zařízení: <PackageId/ProfileId><em><DeviceType></em><EnrollmentTime>

Je to volitelný sloupec v okně zařízení. Není k dispozici ve výchozím nastavení a přístup k němu je jen přes výběr sloupců. Na název zařízení nemá tento nový sloupec vliv.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837---"></a>zařízení s Iosem se výzva k zadání PINU každých 15 minut <!--1550837 -->
Po použití zásad dodržování předpisů nebo konfigurace u zařízení s iOSem se uživatelům každých 15 minut zobrazí výzva k zadání PINu. Uživatelům se výzva zobrazuje tak dlouho, dokud PIN nenastaví.

#### <a name="schedule-your-automatic-updates---1805514---"></a>Plánování automatických aktualizací <!--1805514 -->
Pomocí [nastavení aktualizačního okruhu Windows](windows-update-for-business-configure.md) máte v Intune možnost řídit instalaci automatických aktualizací. Od této aktualizace můžete naplánovat opakované aktualizace na základě týdne, dne a času.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763---"></a>Použití plně rozlišujícího názvu jako subjektu certifikátu SCEP <!--2221763 -->
Při vytváření profilu certifikátu SCEP zadáváte název subjektu. Od této aktualizace můžete jako subjekt použít plně rozlišující název. Jako **Název subjektu** vyberte **Vlastní** a pak zadejte `CN={{OnPrem_Distinguished_Name}}`. Pokud chcete použít proměnnou `{{OnPrem_Distinguished_Name}}`, nezapomeňte synchronizovat atribut uživatele `onpremisesdistingishedname` pomocí služby [Azure Active Directory (AD) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) se službou Azure AD.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983---"></a>Povolit kontaktů přes Bluetooth sdílení – Android for Work <!--1098983 -->
Ve výchozím nastavení Android brání v synchronizaci kontaktů v pracovním profilu se zařízeními Bluetooth. V důsledku toho se kontakty pracovního profilu nezobrazují na ID volajícího u zařízení Bluetooth.

Od této aktualizace je v části **Android for Work** > **Omezení zařízení** > **Nastavení pracovního profilu** k dispozici nové nastavení:
- Sdílení kontaktů přes Bluetooth

Správce Intune může toto nastavení nakonfigurovat a povolit sdílení. Toto nastavení je užitečné při párování zařízení se zařízením Bluetooth do auta, které zobrazuje ID volajícího při použití hands-free. Pokud je nastavení povoleno, kontakty pracovního profilu se zobrazí. Pokud není nastavení povoleno, kontakty pracovního profilu se nezobrazí.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459---"></a>Konfigurace Gatekeepera ke zdrojem stahování aplikací pro macOS ovládacího prvku <!-- 1690459 -->

Můžete konfigurovat Gatekeepera, aby vaše zařízení chránil před aplikacemi díky kontrole nad tím, odkud je možné aplikace stahovat. Můžete nakonfigurovat tyto zdroje stahování: **Mac App Store**, **Mac App Store a identifikovaní vývojáři**, nebo **kdekoli**. Kromě toho je možné nakonfigurovat, jestli uživatelé smí nainstalovat aplikaci kliknutím se stisknutou klávesou Control, které tuto kontrolu Gatekeepera přepíše.

Tato nastavení najdete v části **Konfigurace zařízení** -> **Vytvořit profil** -> **macOS** -> **Ochrana koncového bodu**.

#### <a name="configure-the-mac-application-firewall----1690461---"></a>Konfigurace brány firewall aplikace Mac <!-- 1690461 -->

Je možné nakonfigurovat bránu firewall pro aplikace pro Mac. Můžete to využít k řízení připojení na základě jednotlivých aplikací místo na základě portů. Díky tomu snadněji využijete výhod ochrany pomocí brány firewall a pomůže vám to zabránit nežádoucím aplikacím v převzetí kontroly nad síťovými porty otevřenými pro oprávněné aplikace.

Tuto funkci najdete v části **Konfigurace zařízení** -> **Vytvořit profil** -> **macOS** -> **Ochrana koncového bodu**.

Jakmile nastavení brány firewall povolíte, můžete ji nakonfigurovat pomocí dvou strategií:

- Blokovat všechna příchozí připojení

   Můžete blokovat všechna příchozí připojení u cílových zařízení. Pokud se k tomu rozhodnete, zablokují se příchozí připojení u všech aplikací.

- Povolit nebo blokovat konkrétní aplikace

   Můžete povolit nebo blokovat příjem příchozích připojení u konkrétních aplikací. Můžete také povolit neviditelný režim, který zabrání odpovědím na zjišťovací požadavky.

####  <a name="detailed-error-codes-and-messages----1376342---"></a>Podrobné chybové kódy a zpráv <!-- 1376342 -->

V Konfiguraci zařízení jsou k dispozici podrobnější kódy chyb a chybové zprávy. Toto vylepšené generování sestav obsahuje nastavení, stav těchto nastavení a podrobnosti o řešení potíží.

##### <a name="more-information"></a>Další informace

- Blokovat všechna příchozí připojení

   Tím se zablokuje příjem příchozích připojení u všech služeb sdílení (jako sdílení souborů a obrazovky). Služby systému, které mají příjem příchozích připojení stále povolený, jsou:
  - configd – implementuje DHCP a další služby konfigurace sítě
  - mDNSResponder – implementuje Bonjour
  - racoon – implementuje protokol IPSec

    Abyste mohli služby sdílení používat, musí být **Příchozí připojení** nastavené na **Nenakonfigurováno** (ne **Blokovat**).

- Neviditelný režim

   Povolením zabráníte počítači v odpovídání na zjišťovací požadavky. Počítač bude nadále odpovídat na požadavky oprávněných aplikací. Neočekávané požadavky, jako je ICMP (ping), se ignorují.

#### <a name="disable-checks-on-device-restart---1805490---"></a>Zákaz kontrol při restartování zařízení <!--1805490 -->
V Intune máte možnost řídit [správu aktualizací softwaru](windows-update-for-business-configure.md). Od této aktualizace je k dispozici vlastnost <strong>Kontroly při restartu</strong>, která je ve výchozím nastavení povolená. Pokud chcete přeskočit typické kontroly, které se provádí při restartu zařízení (například aktivní uživatelé, stav baterie a další), vyberte <strong>Přeskočit</strong>.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Nové kanály Windows 10 Insider Preview pro kanály nasazení <!-- 1746293 -->
Nově můžete při vytváření aktualizačního kanálu nasazení Windows 10 vybrat tyto kanály pro údržbu Windows 10 Insider Preview:
- Sestavení Windows Insider – Fast
- Sestavení Windows Insider – Slow
- Sestavení Windows Insider – Release 

Podrobnosti o těchto kanálech najdete v tématu [Správa sestavení Insider Preview](https://insider.windows.com/for-business-organization-admin/).   
Informace o vytváření kanálů nasazení v Intune najdete v tématu [Správa softwarových aktualizací v Intune](windows-update-for-business-configure.md).

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Nová nastavení ochrany Windows Defender Exploit Guard <!-- 1631893 -->

Šest nových <strong>omezení možností útoku</strong> nastavení a rozšířené <strong>řízený přístup ke složkám: Ochrana složek</strong> možnosti jsou teď k dispozici. Tato nastavení najdete na následujících stránkách: Zařízení\profily\
Vytvořit profil\Ochrana koncového bodu\Ochrana Exploit Guard v programu Windows Defender.

#### <a name="attack-surface-reduction"></a>Omezení možností útoku

|Název nastavení  |Možnosti nastavení  |Popis  |
|---------|---------|---------|
|Advanced ransomware protection (Rozšířená ochrana před ransonwarem)|Povoleno, Audit, Nenakonfigurováno|Umožňuje použít agresivní ochranu před ransomwarem.|
|Flag credential stealing from the Windows local security authority subsystem (Označit příznakem použití jiných přihlašovacích údajů ze subsystému Windows Local Security Authority)|Povoleno, Audit, Nenakonfigurováno|Umožňuje označit příznakem použití jiných přihlašovacích údajů ze subsystému Windows Local Security Authority (lsass.exe).|
|Process creation from PSExec and WMI commands (Vytvoření procesů z příkazů PSExec a WMI)|Blokovat, Audit, Nenakonfigurováno|Umožňuje zablokovat vytváření procesů pocházejících z příkazů PSExec a WMI.|
|Untrusted and unsigned processes that run from USB (Nedůvěryhodné a nepodepsané procesy spouštěné z USB)|Blokovat, Audit, Nenakonfigurováno|Umožňuje zablokovat nedůvěryhodné a nepodepsané procesy, které se spouští z USB.|
|Executables that don’t meet a prevalence, age, or trusted list criteria (Spustitelné soubory, které nesplňují kritéria prevalence, stáří nebo seznamu důvěryhodných položek)|Blokovat, Audit, Nenakonfigurováno|Umožňuje zablokovat spuštění spustitelných souborů, dokud nesplní kritéria prevalence, stáří nebo seznamu důvěryhodných položek.|

#### <a name="controlled-folder-access"></a>Řízený přístup ke složkám

|              Název nastavení               |                                                              Možnosti nastavení                                                              | Popis |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Ochrana složek (již implementováno) | Nenakonfigurováno, Povolit, Pouze audit (již implementováno)<br><br> <strong>Nové</strong><br>Block disk modification (Blokovat změny disku), Audit disk modification (Auditovat změny disku) |             |

Umožňuje chránit soubory a složky před neautorizovanými změnami od neznámých aplikací.<br><br>**Povolit**: Brání nedůvěryhodným aplikacím ve změnách nebo odstranění souborů v chráněných složkách a možnost zapisovat do sektorů disku.<br><br>
**Block disk modification only** (Blokovat jenom změny disku):<br>Umožňuje zablokovat nedůvěryhodným aplikacím možnost zapisovat do sektorů disku. Nedůvěryhodné aplikace stále můžou změnit nebo odstranit soubory v chráněných složkách.|

### <a name="intune-apps"></a>Aplikace Intune

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Webové stránky Azure Active Directory můžou vyžadovat aplikaci Intune Managed Browser a podporovat jednotné přihlašování pro Managed Browser (Public Preview) <!-- 710595 -->

Pomocí Azure Active Directory (Azure AD) můžete přístup k webovým stránkám na mobilních zařízeních omezit na aplikaci Intune Managed Browser. V Managed Browseru zůstanou data webových stránek zabezpečená a oddělená od osobních dat koncových uživatelů. Kromě toho bude Managed Browser podporovat možnosti jednotného přihlašování pro weby chráněné pomocí Azure AD. Přihlášení k Managed Browseru nebo jeho používání na zařízení s jinou aplikací, kterou spravuje Intune, umožňuje, aby měl Managed Browser přístup k podnikovým webům chráněným pomocí Azure AD, aniž by uživatel musel zadávat své přihlašovací údaje. Tato funkce se vztahuje na weby jako Outlook Web Access (OWA) a SharePoint Online i na jiné podnikové weby jako prostředky v intranetu, ke kterým se přistupuje prostřednictvím proxy aplikace Azure. Další informace najdete v článku o [ovládacích prvcích přístupu u podmíněného přístupu Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Aplikace portál společnosti pro Android vizuální aktualizace <!--976944 -->

Aktualizovali jsme aplikaci Portál společnosti pro Android v souladu s pokyny pro [Material Design](https://material.io/) Androidu. Obrázky nových ikon najdete v [novinkách v uživatelském rozhraní aplikací](whats-new-app-ui.md).

#### <a name="company-portal-enrollment-improved----1874230-eeready--"></a>Vylepšená registrace pomocí portálu společnosti <!-- 1874230 eeready-->
Uživatelé, kteří registrují zařízení pomocí Portálu společnosti ve Windows 10 sestavení 1703 a vyšším, teď můžou dokončit první krok registrace bez opuštění aplikace.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868---"></a>HoloLens a Surface Hub teď budou zobrazovat v seznamech zařízení <!--1725868 -->
Do aplikace Portál společnosti pro Android jsme přidali podporu zobrazení zařízení HoloLens a Surface Hub zaregistrovaných v Intune.

#### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Vlastní kategorie e-knih pro volume purchase program (VPP) <!-- 1488911 -->
Můžete vytvářet vlastní kategorie e-knih a pak k nim přiřadit e-knihy v rámci programu VPP. Koncoví uživatelé pak uvidí nově vytvořené kategorie e-knih a knihy k nim přiřazené. Podrobnosti najdete v tématu [Správa aplikací a knih zakoupených v rámci multilicenčního programu pomocí Microsoft Intune](vpp-apps.md).  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option----2070166---"></a>Změny podpory pro aplikaci portál společnosti pro Windows odeslat zpětnou vazbu možnost <!-- 2070166 -->
Od 30. dubna 2018 bude možnost **Váš názor** v aplikaci Portál společnosti pro Windows fungovat pouze u zařízení se systémem Windows 10 Anniversary Update (1607) a novějším. Možnost odeslání názoru se už nebude podporovat při použití aplikace Portál společnosti pro Windows se systémem:  
- Windows 10, verze 1507  
- Windows 10, verze 1511  
- Windows Phone 8.1 

Pokud vaše zařízení používá Windows 10 RS1 nebo novější, stáhněte si nejnovější verzi aplikace Portál společnosti pro Windows ze Storu. Pokud používáte nepodporovanou verzi, odesílejte své názory prostřednictvím následujících kanálů: 
- Aplikace Centrum Feedback ve Windows 10
- E-mail WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nová nastavení ochrany Windows Defender Application Guard <!-- 1631890 -->

- **Povolit akceleraci grafiky**: Správci mohou pro ochranu Application Guard Windows Defender povolit virtuální grafický procesor. Toto nastavení umožní procesoru přesunout vykreslování grafiky na virtuální grafický procesor. Může zlepšit výkon při práci s graficky náročnými weby nebo při sledování videa v kontejneru.

- **SaveFilestoHost**: Správci mohou povolit předávání souborů z Microsoft Edge, který běží v kontejneru do hostitelského souborového systému. Zapnutím tohoto nastavení umožníte uživatelům stahovat soubory z Microsoft Edge v kontejneru do hostitelského souborového systému.

#### <a name="mam-protection-policies-targeted-based-on-management-state----1665993---"></a>Zásady ochrany MAM cílové správy na základě stavu <!-- 1665993 -->
Můžete cílit na zásady MAM na základě stavu správy zařízení:
- **Zařízení s Androidem**: Je možné cílit na nespravovaná zařízení, zařízení spravovaná v Intune a Android Enterprise Profiles spravované v Intune (dříve Android for Work).
- **Zařízení s iOS**: Je možné cílit na nespravovaná zařízení (jen MAM) nebo zařízení spravovaná v Intune.

    > [!NOTE]
    > - Podporu této funkce pro iOS budeme zavádět v průběhu dubna 2018.

Podrobnosti najdete v tématu [Cílení zásad ochrany aplikací na základě stavu správy zařízení](app-protection-policies.md).

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Vylepšení jazyka v aplikaci portál společnosti pro Windows <!-- 1683758 -->
Vylepšili jsme jazyk v aplikaci Portál společnosti pro Windows 10 tak, aby byl uživatelsky přívětivější a lépe přizpůsobený vaší firmě. Obrázky s ukázkami změn najdete v tématu [Co je nového v uživatelském rozhraní aplikací](whats-new-app-ui.md).

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Nově přidané informace budou dokumenty týkající se ochrany osobních údajů uživatele <!-- 1440709 -->
V rámci naší snahy poskytnout koncovým uživatelům větší kontrolu nad jejich daty a ochranou osobních údajů jsme zaktualizovali naše dokumenty, v nichž vysvětlujeme, jak zobrazit a odebrat data lokálně uložená aplikacemi Portál společnosti. Tyto novinky najdete zde:

- **Android**: [Odebrání zařízení s Androidem z Intune](/intune-user-help/unenroll-your-device-from-intune-android)
- **Android, pokud uživatel odmítnul podmínky použití**: [Odebrání správy zařízení, pokud odmítnete "Podmínky použití"](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android)
- **iOS**: [Odebrání zařízení s Iosem v Intune](/intune-user-help/unenroll-your-device-from-intune-ios)
- **Windows:** [Odebrání zařízení s Windows z Intune](/intune-user-help/unenroll-your-device-from-intune-windows)

<!-- ########################## -->
## <a name="february-2018"></a>Únor 2018

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Podpora služby Intune pro více Apple DEP nebo Apple School Manageru účty <!-- 747685 -->

Intune teď podporuje registraci zařízení z až 100 různých účtů [Apple Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) nebo [Apple School Manager](apple-school-manager-set-up-ios.md). Pro každý nahraný token lze profily registrace a zařízení spravovat samostatně. K jednotlivým nahraným tokenům DEP nebo School Manager lze automaticky přiřadit různé profily registrace. Pokud je nahraných více tokenů School Manager, může se v každém okamžiku sdílet pomocí služby Microsoft School Data Sync jenom jeden.

Po dokončení migrace už nebudou fungovat beta verze rozhraní Graph API a publikované skripty pro správu Apple DEP nebo ASM přes rozhraní Graph. Nové beta verze rozhraní Graph API jsou ve vývoji a budou se vydávat po dokončení migrace.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Omezení registrace na uživatele <!-- 1634444 eeready wnready -->
V okně **Řešení potíží** teď můžete zobrazit platná [omezení registrace](enrollment-restrictions-set.md) pro jednotlivé uživatele tak, že v seznamu **Přiřazení** vyberete **Omezení registrace**.

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Nová možnost pro ověřování uživatelů pro hromadné registraci Apple <!-- 747625 eeready -->

> [!NOTE]
> U nových tenantů se projeví okamžitě. U stávajících tenantů bude tato funkce zavedena v průběhu dubna. Až do zavedení nemusíte mít k těmto novým funkcím přístup.

Intune teď nabízí možnost ověřovat zařízení pomocí aplikace Portál společnosti u těchto metod registrace:

- Program Apple Device Enrollment Program
- Apple School Manager
- Registrace Apple Configuratoru

Při použití možnosti Portálu společnosti lze vynutit vícefaktorové ověřování Azure Active Directory bez blokování těchto metod registrace.

Při použití možnosti Portálu společnosti pro registraci přidružení uživatelů přeskočí Intune ověřování uživatelů v Pomocníkovi s nastavením iOSu. To znamená, že zařízení se napřed zaregistruje jako zařízení bez uživatelů a neobdrží tedy konfigurace ani zásady pro skupiny uživatelů. Obdrží jenom konfigurace a zásady pro skupiny zařízení. Intune ale na toto zařízení automaticky nainstaluje aplikaci Portál společnosti. První uživatel, který aplikaci Portál společnosti spustí a přihlásí se do ní, se v Intune přidruží k tomuto zařízení. V tomto okamžiku pak obdrží konfigurace a zásady dané skupiny uživatelů. Přidružení uživatelů není možné změnit bez opětovné registrace.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Podpora služby Intune pro více Apple DEP nebo Apple School Manageru účty <!-- 747685 eeready -->

Intune teď podporuje registraci zařízení z až 100 různých účtů Apple DEP (Device Enrollment Program) nebo Apple School Manager. Pro každý nahraný token lze profily registrace a zařízení spravovat samostatně. K jednotlivým nahraným tokenům DEP nebo School Manager lze automaticky přiřadit různé profily registrace. Pokud je nahraných více tokenů School Manager, může se v každém okamžiku sdílet pomocí služby Microsoft School Data Sync jenom jeden.

Po dokončení migrace už nebudou fungovat beta verze rozhraní Graph API a publikované skripty pro správu Apple DEP nebo ASM přes rozhraní Graph. Nové beta verze rozhraní Graph API jsou ve vývoji a budou se vydávat po dokončení migrace.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Vzdálený tisk přes zabezpečenou síť <!-- 1709994  -->
Řešení PrinterOn pro bezdrátový mobilní tisk umožní uživatelům vzdáleně tisknout odkudkoli a kdykoli přes zabezpečenou síť. PrinterOn se integruje s Intune App SDK pro iOS i Android. Zásady ochrany aplikací budete moct cílit na tuto aplikaci pomocí okna **Zásady ochrany aplikací** v Intune v konzole pro správu. Koncoví uživatelé si budou moct stáhnout aplikaci PrinterOn for Microsoft prostřednictvím Obchodu Play nebo iTunes a pak ji používat ve svém ekosystému Intune.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Portál společnosti pro macOS podpora registrací přes správce registrace zařízení <!-- 1352411 -->

Uživatelé teď můžou používat Správce registrace zařízení při registraci na Portálu společnosti v macOS.

### <a name="device-management"></a>Správa zařízení

#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Windows defender stavu hrozby a zprávy o stavu <!--854704 -->

Klíčem ke správě počítačů s Windows je pochopení stavu programu Windows Defender.  Touto aktualizací Intune přidá do stavu agenta Windows Defender nové sestavy a akce. Pomocí souhrnné sestavy stavu v [úloze dodržování předpisů zařízením](compliance-policy-monitor.md) zjistíte, která zařízení vyžadují:
- aktualizaci signatur,
- Restart
- ruční zásah,
- úplnou kontrolu,
- stavy ostatních agentů vyžadujících zásah.

Podrobná sestava pro jednotlivé kategorie stavu uvádí jednotlivé počítače, které vyžadují pozornost, nebo ty, které jsou **čisté**.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Nové nastavení ochrany osobních údajů pro omezení zařízení <!--1308926 -->
Pro zařízení jsou k dispozici [dvě nová nastavení ochrany osobních údajů](device-restrictions-windows-10.md#privacy):
- **Publikovat aktivity uživatele**: Nastavte na **bloku** zabránit sdílení a zjišťování naposledy použitých prostředků v přepínání úloh.
- **Jen místní aktivity**: Nastavte na **bloku** zabránit sdílení a zjišťování naposledy použitých prostředků při přepínání úloh jen u místní aktivity.

#### <a name="new-settings-for-the-microsoft-edge-browser---1469166---"></a>Nové nastavení prohlížeče Microsoft Edge <!--1469166 -->
[Dvě nová nastavení](device-restrictions-windows-10.md#microsoft-edge-browser) jsou teď dostupné pro zařízení s prohlížečem Microsoft Edge: **Cesta k souboru oblíbených položek** a **změny oblíbených položek**.

### <a name="app-management"></a>Správa aplikací

#### <a name="protocol-exceptions-for-applications---1035509---"></a>Výjimky protokolu pro aplikace <!--1035509 -->

Můžete teď vytvořit výjimky ze zásady přenosu dat ve správě mobilních dat Intune, abyste mohli otevřít konkrétní nespravované aplikace. Tyto aplikace musí být pro IT důvěryhodné. Pokud zásady přenosu dat nastavíte **jenom na spravované aplikace**, bude kromě vytvořených výjimek přenos dat i nadále omezený jen na aplikace, které se spravují přes Intune. Tato omezení můžete vytvořit pomocí protokolů (iOS) nebo balíčků (Android).

Do zásad přenosu aplikací MAM můžete například přidat jako výjimku balíček Webex. To umožní, aby se odkazy Webex ve spravované outlookové e-mailové zprávě otevíraly přímo v aplikaci Webex. V ostatních nespravovaných aplikacích bude přenos dat i nadále omezen. Další informace najdete v tématu [Výjimky zásad přenosu dat pro aplikace](app-protection-policies-exception.md).

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Výsledky hledání data zašifrovaná Windows Information Protection (WIP) ve Windows <!-- 1469193 -->
Nastavení v zásadách Windows Information Protection (WIP) vám teď umožňuje řídit, jestli se mají do výsledků hledání ve Windows zahrnovat šifrovaná data WIP. Tuto možnost zásad ochrany aplikací nastavíte tak, že v zásadách Windows Information Protection v části **Upřesnit nastavení** vyberete **Povolit Windows Search Indexeru prohledávat šifrované položky**. Zásady ochrany aplikací musí být nastavené pro platformu *Windows 10* a možnost **Stav registrace** musí být nastavená na hodnotu **S registrací**. Další informace najdete v části týkající se možnosti [Povolit Windows Search Indexeru prohledávat šifrované položky](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Konfigurace automatických aktualizací mobilní aplikace MSI <!-- 1740840 -->
Známou automaticky aktualizovanou mobilní aplikaci MSI můžete nakonfigurovat tak, aby ignorovala proces kontroly verzí. Tato možnost je užitečná, když chcete předejít konfliktu časování. K tomuto typu konfliktu časování může například dojít, když aplikaci automaticky aktualizuje vývojář a současně Intune. Jak vývojář, tak Intune můžou vynucovat verzi aplikace na klientovi Windows, což může způsobit konflikt. Pro tyto automaticky aktualizované aplikace MSI můžete v okně **Informace o aplikaci** nakonfigurovat nastavení **Ignorovat verzi aplikace**. Po přepnutí tohoto nastavení na **Ano** bude Microsoft Intune ignorovat verzi aplikace, která je nainstalovaná na klientovi Windows.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Související sady licencí aplikací v Intune podporované <!-- 1864117 -->
Intune na portálu Azure Portal teď podporuje související sady licencí aplikací jako jedinou položku aplikace v uživatelském rozhraní. Kromě toho všechny aplikace licencované offline a synchronizované z Microsoft Storu pro firmy se sloučí do jediné položky aplikace a všechny podrobnosti nasazení z jednotlivých balíčků se budou migrovat do jediné položky. Pokud se chcete podívat na související sady licencí aplikací na portálu Azure Portal, vyberte **Licence aplikací** v okně **Klientské aplikace**.

### <a name="device-configuration"></a>Konfigurace zařízení
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Přípony souborů Windows Information Protection (WIP) pro automatické šifrování <!-- 1463582 -->
Nastavení v zásadách Windows Information Protection (WIP) teď umožňuje určit, které přípony souborů se při kopírování ze sdílené složky SMB (Server Message Block) v rámci hranic firmy definovaných zásadami WIP mají automaticky šifrovat.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Konfigurace nastavení účtu prostředku pro Surface Huby

Můžete teď vzdáleně nakonfigurovat nastavení účtu prostředku pro Surface Huby.

Surface Hub využívá účet prostředku k ověření u Skypu nebo Exchange, aby bylo možné se připojit ke schůzce.
Můžete vytvořit jedinečný účet prostředku, aby se Surface Hub mohl zobrazit ve schůzce jako konferenční místnost.
Účet prostředku se například může zobrazit jako **Konferenční místnost B41/6233**.

> [!NOTE]
> - Pokud pole ponecháte prázdná, přepíšete dříve nakonfigurované atributy na zařízení.
>
> - Vlastnosti účtu prostředku se můžou na Surface Hubu dynamicky měnit. Jedná se například o případ zapnutí rotace hesla. Proto je možné, že bude chvíli trvat, než se realita na zařízení promítne u hodnot v konzole Azure.
>
>   Pokud chcete zjistit, co je aktuálně nakonfigurováno na Surface Hubu, můžete zahrnout informace o účtu prostředku do inventáře hardwaru (který už má sedmidenní interval) nebo jako vlastnosti jen pro čtení. Z důvodu vyšší přesnosti po provedení vzdálené akce můžete získat stav parametrů ihned po spuštění akce aktualizace účtu nebo parametrů na Surface Hubu.

##### <a name="attack-surface-reduction"></a>Omezení možností útoku

|Název nastavení  |Možnosti nastavení  |Popis  |
|---------|---------|---------|
|Execution of password-protected executable content from email (Spuštění spustitelného obsahu chráněného heslem z e-mailu)|Blokovat, Audit, Nenakonfigurováno|Umožňuje zabránit spuštění spustitelných souborů chráněných heslem, které se stáhly prostřednictvím e-mailu.|
|Advanced ransomware protection (Rozšířená ochrana před ransonwarem)|Povoleno, Audit, Nenakonfigurováno|Umožňuje použít agresivní ochranu před ransomwarem.|
|Flag credential stealing from the Windows local security authority subsystem (Označit příznakem použití jiných přihlašovacích údajů ze subsystému Windows Local Security Authority)|Povoleno, Audit, Nenakonfigurováno|Umožňuje označit příznakem použití jiných přihlašovacích údajů ze subsystému Windows Local Security Authority (lsass.exe).|
|Process creation from PSExec and WMI commands (Vytvoření procesů z příkazů PSExec a WMI)|Blokovat, Audit, Nenakonfigurováno|Umožňuje zablokovat vytváření procesů pocházejících z příkazů PSExec a WMI.|
|Untrusted and unsigned processes that run from USB (Nedůvěryhodné a nepodepsané procesy spouštěné z USB)|Blokovat, Audit, Nenakonfigurováno|Umožňuje zablokovat nedůvěryhodné a nepodepsané procesy, které se spouští z USB.|
|Executables that don’t meet a prevalence, age, or trusted list criteria (Spustitelné soubory, které nesplňují kritéria prevalence, stáří nebo seznamu důvěryhodných položek)|Blokovat, Audit, Nenakonfigurováno|Umožňuje zablokovat spuštění spustitelných souborů, dokud nesplní kritéria prevalence, stáří nebo seznamu důvěryhodných položek.|

##### <a name="controlled-folder-access"></a>Řízený přístup ke složkám

|              Název nastavení               |                                                              Možnosti nastavení                                                              | Popis |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Ochrana složek (již implementováno) | Nenakonfigurováno, Povolit, Pouze audit (již implementováno)<br><br> <strong>Nové</strong><br>Block disk modification (Blokovat změny disku), Audit disk modification (Auditovat změny disku) |             |

Umožňuje chránit soubory a složky před neautorizovanými změnami od neznámých aplikací.<br><br>**Povolit**: Brání nedůvěryhodným aplikacím ve změnách nebo odstranění souborů v chráněných složkách a možnost zapisovat do sektorů disku.<br><br>
**Block disk modification only** (Blokovat jenom změny disku):<br>Umožňuje zablokovat nedůvěryhodným aplikacím možnost zapisovat do sektorů disku. Nedůvěryhodné aplikace stále můžou změnit nebo odstranit soubory v chráněných složkách.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Další nastavení zabezpečení systému Windows 10 a novější zásady dodržování předpisů <!--1704133-->

Teď jsou dostupná další nastavení dodržování předpisů pro Windows 10, včetně vyžadování brány firewall a Antivirové ochrany v programu Windows Defender.

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>Podpora pro offline aplikace z Microsoft Store pro firmy <!--1222672-->
Aplikace Offline zakoupené v Microsoft Storu pro firmy se teď synchronizují na portálu Azure Portal. Tyto aplikace můžete nasadit pro skupiny zařízení nebo skupiny uživatelů. Offline aplikace instaluje Intune, nikoli Store.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Znemožněte koncovým uživatelům ručně přidávali nebo odebírali účty v pracovním profilu <!-- 1728700 -->

Když nasadíte aplikaci Gmail do profilu Android for Work, můžete teď zabránit tomu, aby koncoví uživatelé ručně přidávali nebo odebírali účty v pracovním profilu s použitím nastavení **Přidat nebo odebrat účty** v profilu omezení pro zařízení s Androidem for Work.

<!-- ########################## -->
## <a name="january-2018"></a>Leden 2018

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Upozornění na vypršení platnosti tokenů a tokeny, které budou brzy vyprší <!-- 1639263 -->
Na stránce s přehledem se nyní zobrazují upozornění na tokeny, jejichž platnost vypršela nebo brzy vyprší. Když kliknete na upozornění pro jeden token, přejdete na stránku s podrobnostmi o daném tokenu.  Když kliknete na upozornění s více tokeny, přejdete na seznam všech tokenů s jejich stavem. Správci by měli tokeny obnovovat před datem vypršení jejich platnosti.

### <a name="device-management"></a>Správa zařízení

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>Vzdálená podpora příkaz "Vymazání" pro zařízení s macOS <!-- 1438084 -->

Správci můžou vydat příkaz pro vzdálené vymazání zařízení s macOS.

> [!IMPORTANT]
> Příkaz pro vymazání se nedá vrátit zpět, a proto by se měl používat s rozvahou.

Příkaz pro vymazání odebere ze zařízení všechna data včetně operačního systému. Zároveň se tím dané zařízení odebere ze správy v Intune. Uživateli se nezobrazí žádné upozornění a mazání začne okamžitě po spuštění příkazu.

Je nutné nakonfigurovat 6místný PIN kód pro obnovení. Tento PIN kód lze použít k odemknutí vymazaného zařízení, po kterém se zahájí opětovná instalace operačního systému. Když mazání začne, zobrazí se PIN kód ve stavovém řádku v okně přehledu daného zařízení v Intune. PIN kód zůstane zobrazený, dokud probíhá mazání. Po dokončení mazání zařízení úplně zmizí ze správy Intune. Nezapomeňte si PIN kód pro obnovení poznamenat, aby se dal v případě potřeby použít k obnovení zařízení.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Odvolání licencí pro token Volume Purchasing Program iOS <!-- 820870 -->
Pro daný token VPP můžete odvolat licenci všech aplikací pro iOS koupených přes Volume Purchase Program (VPP).

### <a name="app-management"></a>Správa aplikací

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Odvolání aplikací programu Volume Purchase Program pro iOS  <!-- 820863 -->
Pro dané zařízení, které má jednu nebo více aplikací pro iOS koupených přes Volume Purchase Program (VPP), můžete odvolat licenci aplikace přidruženou na základě zařízení. Odvoláním licence aplikace se příslušná aplikace VPP neodinstaluje ze zařízení. Pokud chcete odinstalovat aplikaci VPP, musíte nastavit akci přiřazení na **Odinstalovat**. Další informace najdete v tématu [Správa aplikací pro systém iOS nakoupených prostřednictvím programu hromadného nákupu pomocí Microsoft Intune](vpp-apps-ios.md).

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Přiřazení mobilních aplikací Office 365 do zařízení iOS a Androidem pomocí integrovaného typu aplikace <!-- 1332318 -->
**Integrovaný** typ aplikace usnadňuje vytvoření aplikací Office 365 a jejich přiřazení k zařízením s iOSem a Androidem, která spravujete. Mezi tyto aplikace O365 se řadí například Word, Excel, PowerPoint a OneDrive. K typu aplikace můžete přiřadit konkrétní aplikace a pak upravit konfiguraci informací o aplikaci.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Zahrnutí a vyloučení přiřazení aplikací na základě skupin <!-- 1406920 -->

Během přiřazování aplikací a po výběru typu přiřazení můžete vybrat skupiny, které se mají zahrnout, a také skupiny, které se mají vyloučit.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>Zásady Konfigurace aplikace můžete přiřadit ke skupinám pomocí zahrnutí a vyloučení přiřazení  <!-- 1480316 -->

Zásady konfigurace aplikace můžete přiřadit skupině uživatelů a zařízení s použitím kombinace zahrnutí a vyloučení přiřazení. Je možné zvolit přiřazení ve formě vlastního výběru skupin nebo virtuální skupiny. Virtuální skupina může zahrnovat možnosti **Všichni uživatelé**, **Všechna zařízení** nebo **Všichni uživatelé a všechna zařízení**.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Podpora pro zásady upgradu edice Windows 10   <!-- 903672(archived), 1119689 -->  
Můžete vytvořit zásady upgradu edice Windows 10, které zařízení s Windows 10 upgradují na Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education a Windows 10 Professional Education N. Podrobnosti o upgradech edicí Windows 10 najdete v článku [Jak nakonfigurovat upgrady edicí Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Zásady podmíněného přístupu pro Intune je dostupná pouze z webu Azure portal  <!-- 1737088 1634311 -->

Od této verze je možné zásady podmíněného přístupu konfigurovat a spravovat jenom na portálu [Azure Portal](https://portal.azure.com) v části **Azure Active Directory** > **Podmíněný přístup**. Na toto okno se také pohodlně dostanete z Intune na portálu Azure Portal přes **Intune** > **Podmíněný přístup**.

#### <a name="updates-to-compliance-emails---1637547---"></a>Aktualizace dodržování předpisů e-mailů <!--1637547 -->

E-mail, ve kterém se odesílá hlášení o zařízení nesplňujícím požadavky, obsahuje podrobnosti o tomto zařízení.

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Nové funkce pro akci "Řešení" pro zařízení s Androidem <!--1583480-->

Aplikace Portál společnosti pro Android rozšiřuje akci Vyřešit pro možnost **Aktualizovat nastavení zařízení** tak, aby bylo možné řešit [problémy se šifrováním zařízení](/intune-user-help/encrypt-your-device-android).

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Vzdálené uzamčení k dispozici v aplikaci portál společnosti pro Windows 10 <!--676506-->
Koncoví uživatelé teď můžou vzdáleně uzamknout svoje zařízení z aplikace Portál společnosti pro Windows 10. To se nezobrazí pro místní zařízení, které aktivně používají.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Snadnější řešení problémů s dodržováním předpisů pro aplikace portál společnosti pro Windows 10 <!--676546-->
Koncoví uživatelé, kteří používají zařízení s Windows, budou moct v aplikaci Portál společnosti klepnout na důvod nedodržení předpisů. Pokud to bude možné, přejdou tímto klepnutím přímo do správného umístění v aplikaci Nastavení, aby mohli problém vyřešit.

<!-- ########################## -->
## <a name="december-2017"></a>Prosinec 2017

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Nové nastavení automatické opětovné nasazení <!-- 1469168 -->
Nastavení **Automatické opětovné nasazení** umožňuje uživatelům s právy správce odstranit všechna uživatelská data a nastavení pomocí klávesové zkratky **CTRL+Win+R** na zamykací obrazovce zařízení. Zařízení se automaticky překonfiguruje a znovu zaregistruje ke správě. Toto nastavení najdete v části Windows 10 > Omezení zařízení > Obecné > Automatické opětovné nasazení. Podrobnosti popisuje článek [Nastavení omezení pro zařízení s Windows 10 v Intune](device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Podpora dalších zdrojových edic v zásadách upgradu edice Windows 10  <!-- 903672,  1119689 -->
Zásady upgradu edice Windows 10 teď můžete použít k upgradu z dalších edic Windows 10 (Windows 10 Pro, Windows 10 Pro Education, Windows 10 Cloud atd.). Před touto verzí bylo podporováno méně cest upgradu. Podrobné informace najdete v článku o [konfiguraci upgradů edice Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Nové nastavení profilu konfigurace zařízení Windows Defender Security Center (WDSC) <!-- 1335507 -->

Intune přidá nový oddíl nastavení profilu konfigurace zařízení v části Endpoint Protection s názvem **Centrum zabezpečení v programu Windows Defender**. Správci IT mohou nakonfigurovat, ke kterým pilířům aplikace Centrum zabezpečení v programu Windows Defender mají koncoví uživatelé přístup. Pokud správce IT skryje pilíř v aplikaci Centrum zabezpečení v programu Windows Defender, nezobrazují se v zařízení uživatele žádná oznámení související s skrytým pilířem.

Toto jsou pilíře, které mohou správci skrýt z nastavení profilu konfigurace zařízení v aplikaci Centrum zabezpečení v programu Windows Defender:
- Ochrana proti virům a ohrožením
- Výkon a stav zařízení
- Ochrana brány firewall a sítě
- Aplikace a ovládací prvek Prohlížeč
- Možnosti pro rodinu

Správci IT mohou také přizpůsobit výběr oznámení, která budou uživatelé dostávat. Můžete například nakonfigurovat, jestli uživatelé dostanou všechna oznámení vygenerovaná viditelnými pilíři WDSC nebo pouze závažná oznámení. Nezávažná oznámení zahrnují pravidelné přehledy aktivity nástroje Antivirová ochrana v programu Windows Defender a oznámení o času dokončení kontroly. Všechna další oznámení se považují za závažná. Kromě toho můžete také upravit samotný obsah oznámení. Například můžete přidat kontaktní informace oddělení IT, která se vloží do oznámení publikovaných v zařízeních uživatelů.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Podpora více konektorů pro zpracování certifikátů SCEP a PFX <!-- 1361755 -->

Zákazníci, kteří k doručení certifikátů do zařízení používají místní konektor NDES, teď můžou v jednom tenantovi nakonfigurovat více konektorů.

Tato nová funkce podporuje následující scénář:

- **Vysoká dostupnost**

Každý konektor NDES si vyžádá žádosti o certifikát z Intune.  Pokud jeden konektor NDES přejde do offline režimu, může další konektor dál zpracovávat žádosti.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Použití proměnné AAD_DEVICE_ID v názvu subjektu  <!-- 1468599 -->

Když v Intune vytvoříte profil certifikátu SCEP, můžete k vytvoření vlastního názvu subjektu použít proměnnou AAD_DEVICE_ID.   Pokud k vyžádání certifikátu použijete tento profil SCEP, nahradí se proměnná identifikátorem zařízení AAD, které požádalo o certifikát.


### <a name="device-management"></a>Správa zařízení

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Správa zařízení macOS zaregistrovaných v Jamf s modulem dodržování předpisů zařízení služby Intune <!-- 1592747 -->
K odeslání informací o stavu zařízení s macOS do Intune teď můžete použít i řešení Jamf, které je vyhodnotí na základě zásad dodržování předpisů definovaných v konzole Intune. Podle stavu dodržování předpisů zařízení a také dalších podmínek (třeba umístění, uživatelského rizika atd.) bude podmíněný přístup vynucovat dodržování předpisů pro zařízení macOS, které mají přístup ke cloudovým a místním aplikacím propojených s Azure AD, včetně Office 365. Další informace o [nastavení integrace řešení Jamf](conditional-access-integrate-jamf.md) a [dodržování předpisů u zařízení spravovaných v řešení Jamf](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Novou akci zařízení s Iosem   <!-- 1424701 -->

Kontrolovaná zařízení s iOSem 10.3 teď můžete vypnout. Tato akce vypne zařízení okamžitě, bez upozornění pro koncového uživatele. Akci **Vypnout (jen pod dohledem)** najdete ve vlastnostech zařízení, když zařízení vyberete v úloze **Zařízení**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Zakázání změn data/času na zařízení se systémem Samsung Knox <!-- 1468103 -->

Přidali jsme novou funkci, která v zařízeních se zabezpečením Samsung Knox umožňuje zablokovat změnu změny data a času. Najdete je zde: **Profily konfigurace zařízení** > **Omezení zařízení (Android)** > **Obecné**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Zařízení Surface Hub podpora účtu zdroje pro <!-- 1566442  -->

Přidali jsme novou akci zařízení, která správcům pomůže definovat a aktualizovat účet zdroje přidružený k Surface Hubu.

Surface Hub využívá účet zdroje k ověření přes Skype nebo Exchange, aby bylo možné se připojit ke schůzce. Můžete vytvořit jedinečný účet zdroje, takže se Surface Hub zobrazí ve schůzce jako konferenční místnost. Účet zdroje se například může zobrazit jako *Konferenční místnost B41/6233*. Účet zdroje (známý také jako účet zařízení) pro Surface Hub je obvykle potřeba nakonfigurovat pro umístění konferenční místnosti a v případě, kdy je nutné změnit další parametry účtu zdroje.

Pokud chtějí správci aktualizovat účet zdroje v zařízení, musí zadat aktuální přihlašovací údaje služby Active Directory nebo Azure Active Directory přidružené k tomuto zařízení. Pokud je na zařízení aktivní rotace hesla, musí správce přejít do Azure Active Directory a heslo najít.

> [!NOTE]
> Všechna pole se odešlou ve skupině a přepíšou všechna dříve nakonfigurovaná pole. Také prázdná pole mohou přepsat existující pole.

Správci mohou nakonfigurovat následující nastavení:

- **Účet zdroje**
   - **Uživatel služby Active Directory**

      Název_domény\uživatelské_jméno nebo hlavní název uživatele (UPN): user@domainname.com

   - **Heslo**

- **Volitelné parametry účtu zdroje** (musí se nastavit pomocí daného účtu zdroje)

   - **Interval rotace hesla**

     Zajišťuje, že Surface Hub automaticky aktualizuje heslo k účtu každý týden z bezpečnostních důvodů. Pokud chcete nakonfigurovat jakékoli parametry po zapnutí této možnosti, musíte nejprve resetovat heslo k účtu ve službě Azure Active Directory.

   - **Adresa SIP (Session Initiation Protocol)**

     Používá se pouze v případě nezdařeného automatického zjišťování.

   - **E-mailu**

     E-mailová adresu účtu zdroje nebo zařízení.

   - **Server Exchange**

     Je potřeba, pouze pokud se nezdaří automatické zjišťování.

   - **Synchronizace kalendáře**

     Určuje, zda je povolená synchronizace kalendáře a dalších služeb serveru Exchange. Například: synchronizace schůzek.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Instalace aplikací Office na zařízeních s macOS <!-- 1494311 -->
Teď můžete na zařízení macOS instalovat aplikace Office. Tento nový typ aplikace vám umožní nainstalovat Word, Excel, PowerPoint, Outlook a OneNote. Tyto aplikace jsou také dodávané prostřednictvím funkce Microsoft AutoUpdate (MAU). Je to kvůli jejich zabezpečení a aktuálnosti.

### <a name="app-management"></a>Správa aplikací

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Odstranění tokenu Volume Purchasing Program iOS <!-- 820879 -->
K odstranění tokenu programu Volume Purchasing Program (VPP) pro iOS můžete použít konzolu. To může být nutné v případě, že máte duplicitní instance tokenu VPP.

### <a name="intune-apps"></a>Aplikace Intune


### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Nová kolekce entit z názvem aktuální uživatel je omezená na data aktuálně aktivních uživatelů <!-- 1667026 -->

Kolekce entit **Uživatelé** obsahuje všechny uživatele Azure Active Directory (Azure AD), kteří mají v podniku přiřazené licence. Uživatel například může být přidaný do Intune a potom v průběhu posledního měsíce dojde k jeho odebrání. Přestože tento uživatel není v době vytvoření sestavy přítomen, existují data o uživateli a stavu. Můžete vytvořit sestavu, která ukazuje trvání historické přítomnosti uživatele ve vašich datech.

Naproti tomu nová kolekce entit **Aktuální uživatel** obsahuje pouze uživatele, kteří nebyli odebráni. Kolekce entit **Aktuální uživatel** obsahuje pouze aktuálně aktivní uživatele. Informace o kolekci entit **Aktuální uživatel** najdete v části [Referenční informace o entitě aktuálního uživatele](reports-ref-current-user.md).


### <a name="updated-graph-apis----1736360---"></a>Aktualizované Graph API <!-- 1736360 -->

V této verzi jsme aktualizovali několik rozhraní API služby Graph pro Intune. V této chvíli se jedná o beta verze. Další informace najdete v měsíčním [protokolu změn rozhraní API služby Graph](https://developer.microsoft.com/graph/docs/concepts/changelog).

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Intune podporuje aplikace zakázané Windows Information Protection (WIP) <!-- 1479103 -->
V Intune můžete zadat odepřené aplikace. Pokud je aplikace zakázaná, má zablokovaný přístup k podnikovým informacím. Je to v podstatě opak seznamu povolených aplikací. Další informace najdete v [doporučeném seznamu aplikací se zákazem pro Windows Information Protection](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).

<!-- ########################## -->
## <a name="november-2017"></a>Listopad 2017

### <a name="troubleshoot-enrollment-issues-----746324---"></a>Řešení problémů s registrací  <!-- 746324 -->

Pracovní prostor **Řešení potíží** teď zobrazuje problémy s registrací uživatelů. Podrobnosti o problému a navrhované nápravné kroky můžou správcům a pracovníkům technické podpory pomoct problém vyřešit. Některé problémy s registrací nejsou zaznamenané a k některým chybám nemusí návrhy k odstranění problému existovat.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Omezení registrace přiřazené skupinám <!-- 747598 -->

Jako správce Intune teď můžete [vytvořit vlastní omezení registrace typů a limitu počtu zařízení u skupin uživatelů](enrollment-restrictions-set.md).

Intune Azure Portal vám umožňuje vytvořit až 25 instancí každého typu omezení, které pak můžete přiřadit ke skupinám uživatelů. Omezení přiřazená ke skupinám přepíší výchozí omezení.

Všechny instance typů omezení se budou uchovávat v seznamu se striktním pořadím. Toto pořadí definuje hodnotu priority pro případ řešení konfliktů. U uživatele, na něhož se vztahuje více instancí omezení, se uplatní jenom instance s nejvyšší prioritou. Prioritu dané instance můžete změnit tak, že ji přetáhnete na jiné místo v seznamu.

Tato funkce bude vydána spolu s migrací nastavení Androidu for Work z nabídky registrace Androidu for Work do nabídky Omezení registrace. Tato migrace může trvat několik dnů, a proto je možné, že v rámci listopadové verze se nejprve upgradují jiné části vašeho účtu a teprve poté se u omezení registrace povolí přiřazení skupin.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Podpora více konektorů zápisu služby síťových zařízení (NDES) <!-- 1528104 -->

Služba zápisu síťových zařízení umožňuje, aby mobilní zařízení spuštěná bez doménových přihlašovacích údajů získala certifikáty založené na protokolu SCEP (Simple Certificate Enrollment Protocol).
Od této aktualizace se podporuje více konektorů NDES.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Správa Androidu for Work zařízení nezávisle na zařízení s Androidem <!-- 1490731 EEready-->

Intune podporuje správu registrace zařízení s Androidem for Work odděleně od platformy Android. Tato nastavení se spravují v části **Registrace zařízení** > **Omezení registrace** > **Omezení typů zařízení**. (Dříve se nacházela v části **Registrace zařízení** > **Registrace Androidu for Work** > **Nastavení registrace Android for Work**.)

Ve výchozím nastavení jsou nastavení zařízení s Androidem for Work stejná jako nastavení zařízení s Androidem. Po změně nastavení Androidu for Work tomu už tak nebude.

Pokud zablokujete registraci Androidu for Work u osobních zařízení, budou se jako Android for Work moct zaregistrovat jenom firemní zařízení s Androidem.

Při práci s těmito novými nastaveními vezměte v úvahu tyto informace:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Pokud jste ještě nikdy nepoužili registraci Androidu for Work

Nová platforma Android for Work je ve výchozím nastavení omezení typů zařízení zablokovaná. Jakmile začnete funkci používat, můžete zařízením povolit, aby se zaregistrovala v Androidu for Work. Uděláte to tak, že změníte výchozí omezení typu zařízení nebo vytvoříte nové, které bude mít přednost před výchozím omezením.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Pokud jste už registraci Androidu for Work použili

Pokud jste už platformu používali, závisí vaše situace na nastavení, která jste zvolili:

| Nastavení | Stav Androidu for Work ve výchozím omezení typu zařízení | Poznámky |
| --- | --- | --- |
| **Spravovat všechna zařízení jako Android for Work** | Blokováno | Všechna zařízení s Androidem se musí zaregistrovat bez Androidu for Work. |
| **Spravovat podporovaná zařízení jako Android for Work** | Povoleno | Všechna zařízení s Androidem, která podporují Android for Work, se musí zaregistrovat s Androidem for Work. |
| **Spravovat podporovaná zařízení pro uživatele v těchto skupinách jako Android for Work** | Blokováno | Vytvořila se samostatná zásada omezení typu zařízení, která přepíše výchozí zásadu. Tato zásada definuje skupiny, které jste dříve vybrali a povolili jim registraci Androidu for Work. Uživatelé ve vybraných skupinách budou moct dál zaregistrovat svoje zařízení s Androidem for Work. Žádní jiní uživatelé se v Androidu for Work nebudou moct zaregistrovat. |

Ve všech případech se vaše zamýšlená regulace zachová. K tomu, aby se zachovala možnost globálního používání Androidu for Work ve vašem prostředí nebo možnost používání této platformy konkrétními skupinami, nevyžadujeme z vaší strany žádnou akci.

### <a name="google-play-protect-support-on-android----908720---"></a>Podpora Google Play Protect na Androidu <!-- 908720 -->

S vydáním verze Android Oreo zavádí Google sadu bezpečnostních funkcí s názvem Google Play Protect, které uživatelům a organizacím umožňují provozovat zabezpečené aplikace a zabezpečené image Androidu. Intune teď podporuje funkce Google Play Protect, a to včetně vzdáleného ověření SafetyNet. Správci můžou nastavit požadavky na zásady dodržování předpisů, které vyžadují, aby funkce Google Play Protect byla nakonfigurovaná a funkční.
Nastavení **Ověření zařízení SafetyNet** vyžaduje, aby se zařízení připojilo ke službě Googlu, která ověří, že je zařízení v pořádku a není ohrožené. Správci můžou rovněž nastavením konfiguračního profilu pro Android for Work vyžádat, aby nainstalované aplikace byly ověřeny pomocí služeb Google Play. Pokud zařízení nesplňuje požadavky na Google Play Protect, může podmíněný přístup uživatelům zablokovat přístup k firemním prostředkům.

- Přečtěte si, [jak vytvořit zásadu dodržování předpisů zařízeními pro službu Google Play Protect](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Povolení textového protokolu ze spravovaných aplikací <!-- 1414050  -->

Aplikace spravované prostřednictvím sady Intune App SDK můžou posílat SMS zprávy.


### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Aplikace aktualizovaná sestava instalace zahrnuje stav instalace čeká <!-- 1249446 -->  

Sestava **Stav instalace aplikace** dostupná pro každou aplikaci v seznamu **Aplikace** v úloze **Klientské aplikace** teď obsahuje počet **čekajících instalací** uživatelů a zařízení.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>Inventář aplikací iOS 11 rozhraní API pro detekci hrozeb Mobile <!-- 1391759 -->

Intune shromažďuje informace o inventáři aplikací ze zařízení jak v osobním, tak i firemním vlastnictví, a zpřístupňuje je zprostředkovatelům služby ochrany před mobilními hrozbami, jako je třeba aplikace Lookout for Work. Inventář aplikací můžete shromažďovat od uživatelů zařízení s iOSem 11 a novějším.

**Inventář aplikací**  
Inventáře ze zařízení s iOSem 11 a novějším v osobním i firemním vlastnictví se posílají zprostředkovateli služby ochrany před mobilními hrozbami. Data v inventáři aplikací zahrnují tyto údaje:

 - ID aplikace
 - Verze aplikace
 - Krátká verze aplikace
 - Název aplikace
 - Velikost sady prostředků aplikace
 - Dynamická velikost aplikace
 - Zda je aplikace ověřena nebo ne
 - Zda je aplikace spravována nebo ne

### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Migrace hybridní uživatelů a zařízení MDM na samostatnou službu Intune <!-- 1463747 wnready -->
Pro přesun uživatelů a jejich zařízení z hybridní správy MDM do Intune na Azure Portalu jsou dostupné nové procesy a nástroje, které vám umožní:
- Kopírovat zásady a profily z konzoly Configuration Manageru do Intune na portálu Azure Portal
- Přesunout podmnožinu uživatelů do Intune na portálu Azure Portal a zbytek nechat v hybridním MDM
- Migrovat zařízení do Intune na portálu Azure Portal, aniž by bylo nutné je znovu zaregistrovat

Podrobnosti najdete v článku o [migraci uživatelů a zařízení hybridního MDM do samostatného Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Podpora vysoké dostupnosti místního konektoru Exchange  <!-- 676614 -->
Jakmile konektor Exchange vytvoří připojení k Exchangi pomocí určeného serveru CAS může zjišťovat další servery CAS. Pokud primární server CAS přestane být dostupný, při selhání převezme služby konektoru jiný server CAS (pokud je k dispozici), dokud primární server CAS nebude znovu dostupný. Podrobnosti najdete v článku [Podpora vysoké dostupnosti místního konektoru Exchange](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Vzdálené restartování zařízení s Iosem (jenom pod dohledem) <!-- 1424595 -->

Pomocí akce zařízení můžete teď aktivovat restartování zařízení s iOSem 10.3 a novějším, které je v režimu pod dohledem. Další informace o použití akce restartování zařízení najdete v tématu [Vzdálené restartování zařízení přes Intune](device-restart.md).

> [!Note]
> Tento příkaz vyžaduje, aby byla zařízení v režimu pod dohledem, a přístupová práva k **zámku zařízení**. Zařízení se restartuje okamžitě. Zařízení s iOSem zamčená pomocí hesla se po restartování k síti Wi-Fi znovu nepřipojí a je možné, že po restartování nebudou moct komunikovat se serverem.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Podpora jednotného přihlašování pro iOS <!-- 1333645 -->  

Pro uživatele iOSu můžete využít jednotné přihlašování. Díky této aktualizaci konfigurace datové části fungují aplikace pro iOS, které jsou naprogramovány tak, aby v datové části jednotného přihlašování hledaly přihlašovací údaje uživatele. Ke konfiguraci hlavního názvu a sféry můžete použít také hlavní název uživatele (UPN) a ID zařízení v Intune. Podrobnosti najdete v článku [Nakonfigurování Intune na jednotné přihlašování pro zařízení s iOSem](sso-ios.md).

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Přidat "Najít iPhone" pro osobní zařízení <!--1427287-->
Teď můžete zobrazit, jestli je u zařízení s iOSem zapnutý zámek aktivace. Tato funkce se dříve nacházela v Intune na portálu Classic.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Vzdálené uzamčení zařízení s macOS spravovaná pomocí Intune <!-- 1437691 -->

Ztracené zařízení s macOS můžete zamknout a nastavit pro ně 6místný číselný kód PIN pro obnovení. Když se zařízení zamkne, v okně **přehledu zařízení** se bude zobrazovat kód PIN, dokud se nepošle jiná akce zařízení.

Další informace si můžete přečíst v článku [Vzdálené uzamčení spravovaných zařízení přes Intune](device-remote-lock.md).

### <a name="new-scep-profile-details-supported----1559808---"></a>Podporované nových podrobností profilu SCEP <!-- 1559808 -->

Při vytváření profilu SCEP na platformách Windows, iOS, macOS a Android teď správci můžou nakonfigurovat další nastavení.  Správci můžou nastavit IMEI, sériové číslo nebo běžný název včetně e-mailu ve formátu názvu subjektu.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

### <a name="retain-data-during-a-factory-reset----1588489---"></a>Zachovat data během obnovení do výrobního nastavení  <!--1588489 -->
Při obnovení továrního nastavení ve Windows 10 verze 1709 a novější je dostupná nová funkce. Správci můžou určit, jestli se při obnovení továrního nastavení data registrace zařízení a další zřízená data v zařízení zachovají.

Při obnovení továrního nastavení se zachovají následující data:
- Uživatelské účty přidružené k zařízení
- Stav počítače (připojení k doméně, připojení ke službě Azure Active Directory)
- Registrace správy mobilních zařízení
- Aplikace nainstalované výrobcem OEM (aplikace ze Storu a aplikace Win32)
- Profil uživatele
- Uživatelská data mimo profil uživatele
- Automatické přihlášení uživatele

Nezachovají se následující data:
- Soubory uživatele
- Aplikace nainstalované uživatelem (aplikace ze Storu a aplikace Win32)
- Nevýchozí nastavení zařízení


### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Přiřazení aktualizačního kanálu Windows 10 se zobrazí. <!-- 1621837 -->
Při **řešení potíží** u aktuálně zobrazeného uživatele si můžete zobrazit veškerá přiřazení aktualizačních kanálů Windows 10.  

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Windows Defender Advanced Threat Protection nastavení četnosti hlášení  <!-- 1455974  -->
Služba Rozšířená ochrana před internetovými útoky v programu Windows Defender umožňuje správcům spravovat četnost hlášení u spravovaných zařízení. Pomocí nové možnosti **Zvýšit četnost hlášení telemetrie** služba Rozšířená ochrana před internetovými útoky v programu Windows Defender častěji shromažďuje a vyhodnocuje rizika. Výchozí nastavení hlášení optimalizuje rychlost a výkon. Zvýšení četnosti hlášení může být velmi cennou pomůckou pro zařízení s vysokým rizikem. Toto nastavení najdete v profilu **Ochrana ATP v programu Windows Defender** v části **Konfigurace zařízení**.

### <a name="audit-updates----1412961---"></a>Aktualizace auditu <!-- 1412961 -->  
Auditování Intune poskytuje záznam o operacích změn souvisejících s Intune.  Všechny operace vytvoření, aktualizace, odstranění a odebrání se zaznamenávají a uchovávají po dobu jednoho roku.  Azure Portal zobrazuje data auditování v každé úloze za posledních 30 dnů, která se dají filtrovat.  Příslušné rozhraní Graph API umožňuje načíst data auditování uložená za poslední rok.

Auditování najdete ve skupině **MONITOROVAT**. Pro každou úlohu existuje položka nabídky **Protokoly auditu**.

### <a name="company-portal-app-for-macos-is-available---1541700--"></a>Aplikace portál společnosti pro macOS je k dispozici <!--1541700-->
Portál společnosti Intune v systému macOS má aktualizované prostředí, které je optimalizované ke správnému zobrazení všech informací a oznámení o dodržování předpisů, což uživatelé potřebují pro všechna zaregistrovaná zařízení. Po nasazení Portálu společnosti Intune do zařízení v něm začne nástroj Microsoft AutoUpdate pro macOS zajišťovat aktualizace. Nový Portál společnosti Intune pro macOS můžete stáhnout po přihlášení na web Portál společnosti pro macOS ze zařízení macOS.

### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Aplikace Microsoft Planner je teď součástí seznamu schválených aplikací mobilní aplikace správy (MAM)  <!-- 1248473 -->
Aplikace Microsoft Planner pro iOS a Android je teď součástí schválených aplikací pro správu mobilních aplikací (MAM). Aplikaci lze nakonfigurovat prostřednictvím okna Intune App Protection na portálu Azure Portal pro všechny tenanty.
- Další informace najdete v [seznamu schválených aplikací MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Frekvence aktualizace požadavků sítě VPN pro jednotlivé aplikace na zařízeních s Iosem   <!-- 1547061 -->  
Správci mohou nyní v aplikacích zařízení s iOSem odebrat požadavky sítě VPN podle aplikace; dotčená zařízení to provedou po jejich dalším vrácení se změnami do Intune, které obvykle probíhá do 15 minut.  

### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Podpora pro System Center Operations Manager management pack pro konektor systému Exchange <!-- 885457 -->
Pro pomoc s analýzou protokolů Exchange Connectoru je nyní dostupná sada System Center Operations Manager (SCOM) Management Pack pro Exchange Connector. Při řešení problémů vám tato funkce poskytuje různé způsoby monitorování služby.

### <a name="co-management-for-windows-10-devices-----1243445---"></a>Spoluspráva pro zařízení s Windows 10  <!-- 1243445 -->
Společná správa je řešení, které představuje most mezi tradiční a moderní správou a poskytne vám cestu k přechodu pomocí přístupu ve fázích. V základu je společná správa řešením, kdy jsou zařízení s Windows 10 současně spravovaná pomocí Configuration Manageru a Microsoft Intune a také připojená k Active Directory (AD) a Azure Active Directory (Azure AD).  Tato konfigurace vám poskytne cestu k modernizaci v průběhu času a tempem, které je nejvhodnější pro vaši organizaci, pokud nemůžete přesunout všechno najednou.  

### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Omezení registrace Windows podle verze operačního systému <!-- 245498 -->
Jako správce Intune teď můžete pro registrace zařízení zadat minimální a maximální verzi Windows 10. Tato omezení můžete nastavit v okně **Konfigurace platforem**.

Intune dál podporuje registraci telefonů a počítačů s Windows 8.1. S minimální a maximální mezí se ale dají nastavit jenom verze Windows 10. Pokud chcete povolit registraci zařízení s Windows 8.1, nechte minimální mez prázdnou.

### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Oznámení pro Windows AutoPilot Nepřiřazená zařízení  <!-- 1631236 -->
Na stránce **Microsoft Intune** > **Registrace zařízení** > **Přehled** je k dispozici nové upozornění, které se týká zařízení s nepřiřazeným Windows AutoPilotem. Toto upozornění ukazuje, kolik zařízení z programu AutoPilot nemá přiřazené profily nasazení AutoPilotu. Na základě informací v upozornění můžete vytvořit profily a přiřadit je potřebným zařízením. Když na upozornění kliknete, zobrazí se úplný seznam zařízení Windows AutoPilotu a podrobné informace o zařízeních. Další informace najdete v článku [Registrace zařízení s Windows pomocí programu Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).


### <a name="refresh-button-for-devices-list-------1333581---"></a>Tlačítko pro seznam zařízení aktualizaci    <!-- 1333581 -->
Protože se seznam zařízení neaktualizuje automaticky, můžete zařízení, která se v seznamu zobrazují, aktualizovat pomocí nového tlačítka Aktualizovat.

### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Podpora pro Symantec Cloud certifikační autority (CA)  <!-- 1333638 -->    
Intune teď podporuje certifikační autoritu Symantec Cloud. To umožňuje, aby Intune Certificate Connector vystavoval zařízením spravovaným přes Intune certifikáty PKCS z certifikační autority Symantec Cloud. Pokud už Intune Certificate Connector používáte s certifikační autoritou Microsoft, můžete existující nastavení Intune Certificate Connectoru použít k přidání podpory pro certifikační autoritu Symantec.

### <a name="new-items-added-to-device-inventory-----1404455---"></a>Nové položky přidané do inventáře zařízení   <!--1404455 -->
V [inventáři, který pořizují zaregistrovaná zařízení](device-inventory.md), jsou teď dostupné následující nové položky:

- Adresa MAC pro Wi-Fi
- Celkové místo v úložišti
- Celkové volné místo
- MEID
- Poskytovatel služeb pro odběratele

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Nastavení přístupu pro aplikace pomocí opravy minimálního zabezpečení Androidu na zařízení<!-- 1278463 -->   
Správce může definovat minimální opravu zabezpečení Androidu, která musí být na zařízení nainstalovaná, aby zařízení pod spravovaným účtem získalo přístup ke spravované aplikaci.

> [!Note]  
> Tato funkce omezuje jenom opravy zabezpečení vydané společností Google na zařízeních s Androidem 6.0 a novějším.

### <a name="app-conditional-launch-support----1193313---"></a>Podpora podmíněného spouštění aplikací <!-- 1193313 -->
Správci IT teď můžou pomocí portálu pro správu Azure nastavit požadavek, aby se prostřednictvím správy mobilních aplikací (MAM) při spouštění aplikace místo číselného kódu PIN vynutilo heslo. Při takové konfiguraci musí uživatel po zobrazení výzvy nastavit a používat heslo, aby získal přístup k aplikacím s podporou MAM. Heslo je definované jako číselný kód PIN s aspoň jedním speciálním znakem nebo velkým/malým písmenem. Tato verze Intune tuto funkci povolí **jenom v iOSu**. Intune podporuje heslo podobným způsobem jako číselný kód PIN, stanovuje minimální délku a povoluje opakování znaků a sekvencí. Tato funkce vyžaduje, aby aplikace (to znamená WXP, Outlook, Managed Browser, Yammer) integrovaly sadu Intune App SDK s kódem této funkce místo vynucení nastavení hesla v cílových aplikacích.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Číslo verze aplikace pro obchodní v zařízení zprávě o stavu instalace <!-- 1233999 -->
Od této verze se ve zprávě o stavu instalace zařízení zobrazí u obchodních aplikací pro iOS a Android číslo verze aplikace. Tyto informace můžete využít k řešení potíží s aplikacemi nebo nalezení zařízení, na kterých běží zastaralé verze aplikací.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Správci teď můžou na nastavení brány Firewall konfigurovat na zařízení pomocí profilu konfigurace zařízení <!-- 951708 -->   
Správci můžou zapnout bránu firewall pro zařízení a také nakonfigurovat různé protokoly pro doménové, privátní a veřejné sítě.  Tato nastavení brány firewall najdete v profilu „Ochrana koncového bodu“.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Ochrana Application Guard Windows Defender pomáhá chránit zařízení před nedůvěryhodnými weby, jak je definováno ve vaší organizaci <!-- 958257 -->   
Správci můžou definovat weby jako „důvěryhodné“ nebo „podnikové“ pomocí pracovního postupu Windows Information Protection nebo nového profilu „Ohraničení sítě“ v konfiguracích zařízení. Weby, které na zařízení s 64bitovou verzí Windows 10 nejsou uvedené v důvěryhodném ohraničení sítě, se při zobrazení v prohlížeči Microsoft Edge místo toho otevřou v prohlížeči ve virtuálním počítači Hyper-V.

Application Guard najdete v konfiguračních profilech zařízení v profilu „Ochrana koncového bodu“. Tam můžou správci konfigurovat interakce mezi virtualizovaným prohlížečem a hostitelským počítačem, nedůvěryhodné a důvěryhodné weby a ukládání dat vygenerovaných ve virtualizovaném prohlížeči. Pokud chcete Application Guard na zařízení používat, musí se nejdříve nakonfigurovat ohraničení sítě. Je důležité, aby se pro zařízení definovalo jenom jedno ohraničení sítě.  

### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Řízení aplikací programu Windows Defender ve Windows 10 Enterprise poskytuje režim k důvěřování jenom autorizovaným aplikacím <!-- 1031096 -->    
Protože každý den vznikají tisíce nových škodlivých souborů, nemusí už boj proti malwaru pomocí antivirové ochrany využívající podpisy souborů poskytovat dostatečnou obranu před novými útoky. Pomocí Řízení aplikací v programu Windows Defender ve Windows 10 Enterprise můžete konfiguraci zařízení změnit z režimu, kdy jsou aplikace důvěryhodné, pokud nejsou blokované antivirovou ochranou nebo jiným řešením zabezpečení, na režim, kdy operační systém důvěřuje jenom aplikacím autorizovaným vaší organizací. Důvěryhodnost se aplikacím přiřazuje v Řízení aplikací v programu Windows Defender.

Pomocí Intune můžete zásady řízení aplikací nakonfigurovat v režimu „pouze audit“ nebo v režimu vynucení. Aplikace nejsou při spouštění v režimu „pouze audit“ blokované. Režim „pouze audit“ zapisuje všechny události do protokolů místního klienta. Můžete také nakonfigurovat, jestli je povolené spouštět jenom součásti Windows a aplikace pro Microsoft Store, nebo jestli se můžou spouštět i další aplikace s dobrou reputací, jak je definuje Intelligent Security Graph.

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Okno Defender Exploit Guard je nová sada funkcí ochrany před únikem informací neoprávněných vniknutí pro Windows 10 <!-- 1063615 -->   
Ochrana Exploit Guard v programu Windows Defender obsahuje vlastní pravidla pro snížení zneužitelnosti aplikací, brání hrozbám z maker skriptů, automaticky blokuje síťová připojení k IP adresám se špatnou reputací a může zabezpečit data před ransomwarem a neznámými hrozbami. Ochrana Exploit Guard v programu Windows Defender se skládá z těchto součástí:

- **Omezení možností útoků** poskytuje pravidla, která vám umožní zabránit hrozbám z maker, skriptů a e-mailů.
- **Řízený přístup ke složkám** automaticky blokuje přístup k obsahu chráněných složek.
- **Filtrování sítě** blokuje odchozí připojení z jakékoli aplikace k IP nebo doméně se špatnou reputací.
- **Ochrana Exploit Protection** poskytuje omezení paměti, toku řízení a zásad, která se dají využít k ochraně aplikace před zneužitím.

### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Správa powershellových skriptů v Intune u zařízení s Windows 10 <!-- 790537 -->

Rozšíření správy Intune umožňuje nahrát powershellové skripty do Intune, aby je bylo možné spouštět v zařízeních s Windows 10. Toto rozšíření doplňuje funkce správy mobilních zařízení (MDM) s Windows 10 a usnadňuje přechod na moderní správu. Podrobnosti najdete v článku [Správa powershellových skriptů v Intune u zařízení s Windows 10](intune-management-extension.md).

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nová nastavení omezení pro zařízení s Windows 10      <!-- 1308850 -->
-    Zasílání zpráv (jenom mobilní) – zakázání testování nebo zpráv MMS
-    Heslo – nastavení k povolení standardu FIPS a použití sekundárních zařízení Windows Hello k ověřování 
-    Zobrazit – nastavení k zapnutí nebo vypnutí škálování GDI pro starší verze aplikací

### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Omezení zařízení režimu veřejného terminálu Windows 10 <!-- 1308872 -->   
Uživatele zařízení s Windows 10 můžete omezit na režim veřejného terminálu, který uživatele omezuje na sadu předdefinovaných aplikací.  To uděláte tak, že vytvoříte profil omezení zařízení s Windows 10 a nastavíte režim Veřejný terminál.

Režim veřejného terminálu podporuje dva režimy: **s jednou aplikací** (umožňuje uživateli spustit jenom jednu aplikaci) nebo **s více aplikacemi** (povoluje přístup k sadě aplikací).  Definujete uživatelský účet a název zařízení a tím se určí podporované aplikace.  Když je uživatel přihlášený, je omezený na definované aplikace.  Další informace najdete v článku [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Režim veřejného terminálu vyžaduje:

- Intune musí být autoritou pro správu mobilních zařízení (MDM).
- Aplikace už musí být v cílovém zařízení nainstalované.
- Zařízení musí být [správně zřízené](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nový profil konfigurace zařízení pro vytvoření ohraničení sítě <!-- 1311967 -->   
Součástí jiných profilů konfigurace zařízení je nový profil konfigurace zařízení s názvem **Ohraničení sítě**. Tento profil slouží k definování online prostředků, které chcete, aby se považovaly za podnikové a důvěryhodné. Ohraničení sítě pro zařízení musíte definovat *před tím*, než na něm bude možné používat funkce jako ochrana Application Guard v programu Windows Defender a Windows Information Protection. Je důležité, aby se pro každé zařízení definovalo jenom jedno ohraničení sítě.

Můžete definovat podnikové cloudové prostředky, rozsahy IP adres a interní proxy servery, které se mají považovat za důvěryhodné. Po definování můžou ohraničení sítě využívat ostatní funkce jako ochrana Application Guard v programu Windows Defender a Windows Information Protection.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Další dvě nastavení pro antivirové ochrany v programu Windows Defender <!-- 1338409 -->  
**Úroveň blokování souborů**

| | |
|---|---|
| Nenakonfigurováno | Nastavení **Nenakonfigurováno** používá výchozí úroveň blokování Antivirové ochrany v programu Windows Defender a zajišťuje silnou detekci bez zvýšeného rizika detekování legitimních souborů. |
| Vysoká | Nastavení **Vysoká** aplikuje silnou úroveň zjišťování.
| Vysoká +  | Nastavení **Vysoká +** poskytuje vysokou úroveň s dalšími ochrannými opatřeními, která můžou mít vliv na výkon klienta.
| Žádná tolerance  | Nastavení **Žádná tolerance** blokuje všechny neznámé spustitelné soubory. |

I když je to nepravděpodobné, může nastavení **Vysoká** způsobit, že se detekují některé legitimní soubory.
Doporučujeme nastavit úroveň blokování souborů na výchozí hodnotu **Nenakonfigurováno**.

**Prodloužení časového limitu pro kontrolu souborů v cloudu**  

| | |
|--|--|
| Počet sekund (0–50) | Zadejte maximální dobu, po kterou má Antivirová ochrana v programu Windows Defender blokovat soubor při čekání na výsledek z cloudu. Výchozí doba je 10 sekund: dodatečná doba, kterou tady zadáte (až 50 sekund), se k těmto 10 sekundám přičte. Ve většině případů trvá kontrola mnohem kratší dobu než maximální. Prodloužení doby umožňuje, aby cloud podezřelé soubory důkladně prozkoumal. Doporučujeme, abyste toto nastavení povolili a zadali aspoň dalších 20 sekund. |

### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Přidáno Citrix VPN pro zařízení s Windows 10 <!-- 1512457 -->  
Pro zařízení s Windows 10 můžete nakonfigurovat Citrix VPN. Citrix VPN můžete zvolit ze seznamu *Vyberte typ připojení* v okně **Základní síť VPN** při konfiguraci VPN pro Windows 10 a novější.

> [!Note]
> Konfigurace Citrix existovala pro iOS a Android.

### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Připojení Wi-Fi podporují v Iosu předsdílené klíče <!-- 1550823 -->
Zákazníci můžou nakonfigurovat profily sítě Wi-Fi, aby mohli na zařízeních s iOSem používat předsdílené klíče (PSK) pro připojení typu WPA/WPA2-Personal. Tyto profily se doručí do zařízení uživatelů, když se zařízení zaregistruje v Intune.

Když je profil doručený do zařízení, bude další krok záviset na tom, jak je profil nakonfigurovaný.  Pokud je profil nastavený na automatické připojení, aktivuje se připojení automaticky, až bude příště potřeba síť.  Pokud je profil nastavený na ruční připojení, musí uživatel aktivovat připojení ručně.  

### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Přístup k protokolům spravovaných aplikací pro iOS <!-- 1469920 -->
Koncoví uživatelé, kteří mají nainstalovaný Managed Browser, teď můžou zobrazit stav správy všech aplikací publikovaných Microsoftem a posílat protokoly pro řešení problémů se spravovanými aplikacemi pro iOS.

Informace o tom, jak na zařízení s iOSem povolit v Managed Browseru režim pro řešení problémů, najdete v tématu [Jak se dostat k protokolům spravovaných aplikací pomocí Managed Browseru na zařízení s iOSem](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Vylepšení instalace zařízení pracovního postupu v aplikaci portál společnosti pro iOS verze 2.9.0 <!-- 1417174 -->

Pracovní postup instalace zařízení v aplikaci Portál společnosti pro iOS byl vylepšen. Jazyk je uživatelsky přívětivější a tam, kde to bylo možné, jsme také sjednotili obrazovky. Díky použití názvu vaší firmy všude v textu instalace je jazyk lépe přizpůsobený vaší firmě. Tento aktualizovaný pracovní postup uvidíte  [na stránce Co je nového v uživatelském rozhraní](whats-new-app-ui.md).


### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Entita uživatele obsahuje nejnovější uživatelská data v datovém modelu datového skladu <!-- 1544273 -->
První verze datového modelu datového skladu Intune obsahovala jenom poslední historická data Intune. Při vytváření sestav nebylo možné zachytit aktuální stav uživatele. V této aktualizaci se **entita uživatele** naplní nejnovějšími uživatelskými daty.

<!-- ########################## -->
## <a name="october-2017"></a>Říjen 2017

### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>iOS a je viditelné číslo verze – obchodní aplikace pro Android <!-- 1380712 -->

Aplikace v Intune teď zobrazují číslo verze obchodních aplikací pro iOS a Android. Číslo se zobrazuje na portálu Azure Portal v seznamu aplikací a v okně přehledu aplikace. Koncoví uživatelé uvidí číslo aplikace v aplikaci Portál společnosti a na webovém portálu.

__Číslo úplné verze:__ Číslo úplné verze identifikuje konkrétní vydanou verzi aplikace. Číslo se zobrazí jako _Verze_(_build_). Příklad: 2.2(2.2.17560800)

Celé číslo verze tvoří dvě části:

 - **Verze**  
   Číslo verze je čitelné číslo vydané verze aplikace. Koncovým uživatelům slouží k identifikaci různých vydaných verzí aplikace.

 - **Číslo buildu**  
    Číslo buildu je interní číslo, které může sloužit k rozpoznání aplikace a její programové správě. Číslo buildu se vztahuje k iteraci aplikace, která odkazuje na změny v kódu.

Další informace o číslech verzí a vývoji obchodních aplikací si přečtěte v článku [Začínáme s Microsoft Intune App SDK](app-sdk-get-started.md#line-of-business-app-version-numbers).

### <a name="device-and-app-management-integration----677972---"></a>Integrace správy zařízení a aplikací <!-- 677972 -->   
Když jsou teď správa mobilních zařízení (MDM) i správa mobilních aplikací (MAM) Intune přístupné z portálu Azure Portal, začala služba Intune integrovat způsoby práce IT správců týkající se správy aplikací a zařízení. Tyto změny jsou zaměřené na zjednodušení způsobu správy zařízení a aplikací.

Další informace o změnách MDM a MAM najdete na [blogu týmu podpory Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Nová upozornění registrace pro zařízení Apple <!-- 1471790 -->
Stránka s přehledem registrace bude správcům IT zobrazovat užitečná upozornění týkající se správy zařízení Apple. Upozornění se budou zobrazovat na stránce přehledu vždy, když se bude blížit konec platnosti certifikátu Apple MDM Push Certificate a tokenu Programu registrace zařízení nebo když už jejich platnost vypršela. Budou se zobrazovat také v případě, že v Programu registrace zařízení existují nepřiřazená zařízení.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Podpora nahrazování tokenů pro konfiguraci aplikací bez registrace zařízení <!-- 1080364 -->

U aplikací v zařízeních, která nejsou zaregistrovaná, můžete pro dynamické hodnoty v konfiguracích aplikací použít tokeny. Další informace najdete v článku [Přidání zásad konfigurace aplikací pro spravované aplikace bez registrace zařízení](app-configuration-policies-managed-app.md).

### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Aktualizace aplikace portál společnosti pro Windows 10 <!--1299474-->
Stránka Nastavení aplikace Portál společnosti pro Windows 10 je aktualizovaná, aby nastavení a zamýšlené akce uživatelů byly konzistentnější v rámci všech nastavení. Stránka také byla aktualizována tak, aby rozložením odpovídala jiným aplikacím pro Windows. Na stránce [Co je nového v uživatelském rozhraní aplikace](whats-new-app-ui.md) najdete obrázky aplikace před a po aktualizaci.

### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Informování koncovým uživatelům o tom, jaké informace o zařízení můžete zobrazit pro zařízení s Windows 10 <!--1337920-->
Na obrazovku Podrobnosti o zařízení v aplikaci Portál společnosti pro Windows 10 jsme přidali **Typ vlastnictví**. Uživatelům to umožní zjistit další informace o ochraně osobních údajů přímo z této stránky z dokumentace Intune pro koncové uživatele. Tyto informace najdou také na obrazovce s informacemi **o produktu**.

### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Výzvy k zadání názoru v aplikaci portál společnosti pro Android <!--1165249-->
Aplikace portál společnosti pro Android teď požaduje zpětnou vazbu koncového uživatele. Tato zpětná vazba se pošle přímo společnosti Microsoft a poskytne koncovým uživatelům příležitost zadat recenzi k aplikaci ve veřejném obchodě Google Play. Zpětná vazba není povinná a je možné ji snadno zrušit, takže uživatelé mohou dále používat aplikaci.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Pomoc uživatelům při samotné aplikaci portál společnosti pro Android <!-- 1573324, 1573150, 1558616, 1564878 -->

Aplikace Portál společnosti pro Android přidala pokyny pro koncové uživatele, které jim pomůžou porozumět novým případům použití a v případě potřeby i vyřešit problém vlastními silami.
- Koncoví uživatelé budou nasměrováni na [portál Azure Active Directory](https://account.activedirectory.windowsazure.com/r/#/profile), kde můžou zařízení odebrat v případě, že dosáhli maximálního počtu zařízení, která smí přidat.
- Koncovým uživatelům se zobrazí postup, aby mohli [opravit chyby aktivace na zařízeních se zabezpečením Samsung Knox](https://go.microsoft.com/fwlink/?linkid=859718) nebo [vypnout režim snížené spotřeby](/intune-user-help/power-saving-mode-android). Pokud ani jedno z řešení jejich problém nevyřeší, zobrazí se jim vysvětlení, jak mohou [odeslat protokoly do Microsoftu](/intune-user-help/send-logs-to-microsoft-android).

### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nový "Řešení" akce pro zařízení s Androidem <!-- 1583480 -->

Aplikace Portál společnosti pro Android představuje akci Vyřešit na stránce _Aktualizovat nastavení zařízení_. Výběrem této možnosti koncový uživatel přejde přímo na nastavení, které způsobuje, že jeho zařízení nevyhovuje předpisům. V současné době aplikace Portál společnosti pro Android podporuje tuto akci u [hesla zařízení](/intune-user-help/set-your-pin-or-password-android), [ladění USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android) a u nastavení [Neznámé zdroje](/intune-user-help/you-need-to-turn-off-unknown-sources-android).

### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Indikátor průběhu instalace zařízení v portálu společnosti pro Android <!-- 1565657 -->
Aplikace Portál společnosti pro Android zobrazuje indikátor průběhu instalace zařízení, když uživatel provádí registraci zařízení. Indikátor zobrazuje nové stavy, od „Nastavení zařízení...“, přes „Probíhá registrace zařízení...“ a „Dokončení registrace zařízení...“ a potom „Dokončení nastavení zařízení...“.

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Podpora ověřování na základě certifikátu na portál společnosti pro iOS <!--1029830-->
Přidali jsme podporu ověřování pomocí certifikátů v aplikaci Portál společnosti pro iOS. Uživatelé s ověřováním pomocí certifikátů zadají svoje uživatelské jméno a pak klepnou na odkaz „Přihlásit se pomocí certifikátu“. V aplikacích Portál společnosti pro Android a Windows je už ověřování pomocí certifikátů podporované. Další informace najdete na stránce o [přihlášení do aplikace Portál společnosti](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Aplikace, které jsou dostupné s registrací nebo bez registrace, lze nyní nainstalovat bez výzvy k registraci <!-- 1334712 -->

Firemní aplikace, které byly v aplikaci Portál společnosti pro Android dostupné s registrací nebo bez registrace, se teď můžou nainstalovat bez výzvy k registraci.

### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune----747617---"></a>Podpora programu Windows AutoPilot Deployment v Microsoft Intune  <!-- 747617  -->
Teď můžete Microsoft Intune používat s programem Windows AutoPilot Deployment, abyste uživatelům umožnili zřizovat firemní zařízení bez zapojení IT pracovníků. Můžete přizpůsobit software spouštěný při prvním zapnutí a nasměrovat uživatele k tomu, aby své zařízení připojili k Azure AD a zaregistrovali v Intune. Microsoft Intune a Windows AutoPilot společně eliminují potřebu nasazovat, udržovat a spravovat image operačního systému. Podrobnosti najdete v článku [Registrace zařízení s Windows pomocí programu Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="quick-start-for-device-enrollment----1425655---"></a>Rychlý start pro registraci zařízení  <!-- 1425655 --> 
V **Registraci zařízení** je teď dostupné rychlé zahájení, které poskytuje referenční tabulku pro správu platforem a konfiguraci procesu registrace. Stručný popis jednotlivých položek a odkazy na dokumentaci s podrobnými pokyny poskytují užitečnou dokumentaci, která zjednodušuje zahájení práce.

### <a name="device-categorization----1427491---"></a>Kategorizace zařízení <!-- 1427491 -->
Graf platforem zaregistrovaných zařízení v okně **Zařízení > Přehled** uspořádá zařízení podle platforem, včetně Androidu, iOSu, macOS, Windows a Windows Mobile.  Zařízení s jinými operačními systémy jsou seskupená do kategorie „Ostatní“.  Ta zahrnuje zařízení od výrobců Blackberry, NOKIA a dalších.  

Pokud chcete zjistit, která zařízení jsou ve vašem tenantovi ovlivněna, zvolte **Spravovat > Všechna zařízení** a pak pomocí **Filtrovat** omezte pole **OS**.

### <a name="zimperium---new-mobile-threat-defense-partner-----954681---"></a>Zimperium – nový partner ochrany před mobilními hrozbami   <!-- 954681 -->  
Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Zimperium. Je to řešení ochrany před mobilními hrozbami, které se integruje s Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak integrace s Intune funguje
Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých služba Zimperium běží. Zásady podmíněného přístupu EMS založené na posouzení rizika službou Zimperium můžete nakonfigurovat prostřednictvím zásad dodržování předpisů zařízení služby Intune, kterými můžete na základě odhalených hrozeb u zařízení, které nedodržují předpisy, povolit nebo zablokovat přístup k firemním prostředkům.

### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Nová nastavení pro profil omezení zařízení s Windows 10  <!--- 978575, 1308849, -->  
Do profilu omezení zařízení s Windows 10 v kategorii filtru SmartScreen v programu Windows Defender přidáváme nová nastavení.

Podrobnosti o profilu omezení zařízení s Windows 10 najdete v tématu [Nastavení omezení pro zařízení Windows 10 a novější]( device-restrictions-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Vzdálená podpora zařízení s Windows a Windows Mobile   <!-- 1070473 -->  
Intune vám teď pomocí samostatně zakoupeného softwaru [TeamViewer](https://www.teamviewer.com) umožňuje poskytovat vzdálenou pomoc uživatelům, kteří používají zařízení s Windows a Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988-1280990---"></a>Kontrola zařízení pomocí programu Windows Defender <!-- 1280988  1280990   -->
Na spravovaných zařízeních s Windows 10 teď můžete pomocí Antivirové ochrany v programu Windows Defender provádět **rychlou kontrolu**, **úplnou kontrolu** a **aktualizaci signatur**. V okně s přehledem zařízení zvolte akci, která se má na zařízení spustit. Před odesláním příkazu do zařízení budete vyzváni k potvrzení. 

**Rychlá kontrola**: Rychlé kontrole se kontrolují místa, kde Pokud chcete začít, jako jsou klíče registru a známé spouštěcí složky Windows registruje malwaru. Rychlá kontrola trvá průměrně pět minut. V kombinaci s nastavením **trvalé ochrany v reálném čase**, která soubory kontroluje při otevření, zavření a vždy, když uživatel přejde do nějaké složky, poskytuje rychlá kontrola ochranu před malwarem, který se může nacházet v systému nebo jádru. Uživatelé uvidí na svých zařízeních výsledky kontroly potom, co se dokončí. 

**Úplná kontrola**: Úplná kontrola může být užitečná u zařízení, která mají napadených malwarem, chcete-li určit, jestli nějaké neaktivní komponenty, které vyžadují důkladnější nahoru vyčistit a je užitečný ke spouštění kontrol na vyžádání. Úplná kontrola může trvat hodinu. Uživatelé uvidí na svých zařízeních výsledky kontroly potom, co se dokončí. 

**Aktualizaci signatur**: Tímto příkazem aktualizuje antivirové ochrany v programu Windows Defender definice a signatury malwaru. Tím se zajistí účinnost Antivirové ochrany v programu Windows Defender při zjišťování malwaru. Tato funkce je určená jen pro zařízení s Windows 10 a očekává, že je zařízení připojené k internetu. 

### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Bylo odebráno tlačítko Povolit/zakázat ze stránky certifikační autority Intune portálu Intune Azure portal  <!-- 1400455 -->
 Odstraňujeme nadbytečný krok při nastavení Certificate Connectoru v Intune. V současné době stáhnete Certificate Connector a pak ho povolíte v konzole Intune. Pokud ale konektor v konzole Intune zakážete, dál vydává certifikáty.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Od října už se tlačítko Povolit/Zakázat na stránce certifikační autority na portálu Azure Portal zobrazovat nebude. Funkce konektoru zůstává stejná. Do zařízení zaregistrovaných v Intune se budou certifikáty dál nasazovat. Certificate Connector můžete dál stáhnout a nainstalovat. Pokud chcete zastavit vydávání certifikátů, Certificate Connector teď místo zakázání odinstalujete.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Pokud máte Certificate Connector aktuálně zakázaný, měli byste ho odinstalovat.

### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Nová nastavení pro profil omezení zařízení s Windows 10 Team   <!--- 1308838 -->
V této verzi jsme přidali spoustu nových nastavení do profilu omezení zařízení s Windows 10 Team, která vám pomůžou ovládat zařízení Surface Hub.

Další informace o tomto profilu najdete v článku [Nastavení omezení zařízení s Windows 10 Team](device-restrictions-windows-10-teams.md).

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time----1333292---"></a>Uživatelům zařízení s Androidem zabránit ve změně data a času  <!-- 1333292 -->
Pomocí [vlastních zásad zařízení s Androidem](custom-settings-android.md) můžete uživatelům zabránit, aby na zařízení změnili datum a čas.

Uděláte to tak, že nakonfigurujete vlastní zásadu pro Android s identifikátorem URI nastavení ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange. Nastavte tuto zásadu na **TRUE** a pak ji přiřaďte požadovaným skupinám.

### <a name="bitlocker-device-configuration---1397398---"></a>Konfigurace zařízení s Bitlockerem <!-- 1397398 -->
Možnost **Šifrování Windows > Základní nastavení** obsahuje nové nastavení **Upozornění na jiné šifrování disku**, které vám umožní zakázat [výzvu s upozorněním](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) na jiné šifrování disku, které se na zařízení uživatele může používat.  Tato výzva s upozorněním vyžaduje souhlas koncového uživatele s nastavením BitLockeru na zařízení a toto nastavení blokuje, dokud ho koncový uživatel nepotvrdí.  Toto nové nastavení zakazuje upozornění koncového uživatele.


### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Programu Volume Purchase Program pro obchodní aplikace se teď budou synchronizovat s vaším Tenantem Intune <!-- 800882 -->  
Vývojáři třetích stran můžou soukromě distribuovat aplikace autorizovaným členům programu Volume Purchase Program (VPP) for Business, kteří jsou uvedeni ve službě iTunes Connect. Tito členové programu VPP for Business se mohou přihlásit do zvláštního App Storu pro tento program a aplikace si zakoupit.

Od této verze se teď začnou aplikace VPP for Business zakoupené koncovým uživatelem synchronizovat s jeho tenanty Intune.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Výběr regionálního Apple App storu pro synchronizaci aplikací VPP  <!-- 1332311 -->  
Při nahrávání tokenu VPP (Volume Purchase Program) můžete nakonfigurovat regionální VPP Store. Intune synchronizuje aplikace VPP pro všechna národní prostředí z určeného regionálního VPP Storu.

> [!NOTE]  
> V současnosti synchronizuje Intune jen aplikace VPP z regionálního VPP Storu, které se shodují s národním prostředím Intune, ve kterém byl tenant Intune vytvořen.


### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Blokování kopírování a vkládání mezi pracovními a osobními profily v Androidu for Work <!-- 1098994 -->
V této verzi můžete pracovní profil pro Android for Work nakonfigurovat tak, aby bylo zablokované kopírování a vkládání mezi pracovními a osobními aplikacemi. Toto nové nastavení najdete v profilu **Omezení zařízení** pro platformu **Android for Work** v **Nastavení pracovního profilu**.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Vytvoření aplikace omezených na určité regionální Apple App Storu pro iOS <!-- 1281692 -->
Během vytváření spravované aplikace pro Apple App Store budete moci určit národní prostředí země.

> [!Note]  
> V současnosti můžete vytvářet jen spravované aplikace pro Apple App Store, které se nacházejí v americkém App Storu.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Aktualizace iOS VPP uživatelů a zařízení licencované aplikace  <!-- 1305564 -->  
Token VPP pro iOS budete moci nakonfigurovat tak, aby se prostřednictvím služby Intune aktualizovaly všechny aplikace zakoupené pro tento token. Intune zjistí aktualizace aplikací VPP v App Storu a automaticky je nabídne zařízení, jakmile se zařízení ohlásí.

Pokyny k nastavení tokenu VPP a povolení automatických aktualizací najdete v článku [Správa aplikací pro systém iOS nakoupených prostřednictvím programu hromadného nákupu pomocí Microsoft Intune] (/intune/vpp-apps-ios).


### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Entitě přidružení zařízení uživatelů do datového modelu datového skladu Intune byla přidána kolekce <!-- 1187917 -->
Pomocí informací o přidružení uživatelů a zařízení, které přidružují kolekce entit uživatelů a zařízení, teď můžete vytvářet sestavy a vizualizace dat. Tento datový model lze zpřístupnit přes soubor Power BI (PBIX) načtený ze stránky Datový sklad v Intune, přes koncový bod OData nebo vývojem vlastního klienta.

### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Kontrola dodržování zásad pro aktualizační okruhy Windows 10 <!-- 1067886 -->
Sestavu se zásadami aktualizačních okruhů Windows 10 si můžete prohlédnout v nabídce Aktualizace softwaru > Stav nasazení podle kruhu aktualizace. Tato sestava zásad obsahuje stav nasazení pro nakonfigurované aktualizační okruhy. 

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions----1352223---"></a>Nová sestava obsahující seznam zařízení s Iosem se staršími verzemi Iosu   <!-- 1352223 -->
Sestava **zařízení se zastaralým iOSem** je k dispozici z pracovního prostoru **Aktualizace softwaru**. V sestavě můžete zobrazit seznam zařízení s iOSem pod dohledem, na která byla zacílena zásada aktualizace iOSu a pro která jsou k dispozici aktualizace. Pro každé zařízení můžete zobrazit stav, proč nebylo automaticky aktualizováno. 

### <a name="view-app-protection-policy-assignments-for-troubleshooting----1475003---"></a>Zobrazení přiřazených zásad ochrany aplikací pro řešení potíží <!--  1475003 -->
V této nadcházející verzi bude do rozevíracího seznamu **Přiřazení**, který je dostupný v okně pro řešení potíží, přidána možnost **Zásady ochrany aplikací**. Výběrem zásad ochrany aplikací teď můžete zobrazit zásady ochrany aplikací přiřazené vybraným uživatelům.



### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Vylepšení pro pracovní postup instalace zařízení v aplikaci portál společnosti <!--1490692-->
Vylepšili jsme pracovní postup instalace zařízení v aplikaci Portál společnosti pro Android. Jazyk je uživatelsky přívětivější a přizpůsobenější potřebám vaší společnosti. Tam, kde to bylo možné, jsme také zkombinovali obrazovky. Tato vylepšení najdete na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md#week-of-october-2-2017).

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Vylepšené pokyny týkající se žádosti o přístup ke kontaktům na zařízeních s Androidem <!--1484985-->

Aplikace Portál společnosti často po koncových uživatelích vyžaduje, aby přijali oprávnění Kontaktů. Pokud koncový uživatel tento přístup zamítne, zobrazí se mu nyní oznámení v aplikaci, které ho upozorní, aby aplikaci udělil podmíněný přístup. 

### <a name="secure-startup-remediation-for-android---1490712--"></a>Zabezpečené spuštění nápravy pro Android <!--1490712-->

Koncoví uživatelé, kteří používají zařízení s Androidem, budou moct v aplikaci Portál společnosti klepnout na důvod nedodržení předpisů. Pokud to bude možné, přejdou tímto klepnutím přímo do správného umístění v aplikaci Nastavení, aby mohli problém vyřešit. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Další nabízená oznámení pro koncové uživatele v aplikaci portál společnosti pro Android Oreo <!--1475932-->

Koncovým uživatelům se zobrazí další oznámení, která je upozorní, že aplikace Portál společnosti pro Android Oreo provádí úlohy na pozadí, třeba načítání zásad ze služby Intune. Pro koncové uživatele tak bude transparentnější, kdy Portál společnosti na jejich zařízení provádí úlohy správy. Jde o součást celkové [optimalizace uživatelského rozhraní Portálu společnosti](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) pro aplikaci Portál společnosti pro Android Oreo. 

Provedli jsme další optimalizace nových prvků uživatelského rozhraní, které jsou v Androidu Oreo povoleny.  Koncovým uživatelům se zobrazí další oznámení, která je upozorní, že Portál společnosti provádí úlohy na pozadí, třeba načítání zásad ze služby Intune.  Pro koncové uživatele tak bude transparentnější, kdy Portál společnosti na jejich zařízení provádí úlohy správy.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nové chování aplikace portál společnosti pro Android s pracovními profily <!-- 1485783 -->

Při registraci zařízení s Androidem for Work s pracovním profilem se o správu úloh na tomto zařízení stará aplikace Portál společnosti v pracovním profilu. 

Pokud v osobním profilu nepoužíváte nějakou aplikaci s podporou MAM, neslouží už aplikace Portál společnosti k žádnému účelu. Kvůli příjemnější práci v pracovním profilu Intune po úspěšné registraci pracovního profilu automaticky skryje osobní aplikaci Portál společnosti.

Aplikaci Portál společnosti pro Android můžete v osobním profilu kdykoli povolit tak, že přejdete na [Portál společnosti v Obchodě Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) a klepnete na **Povolit**.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Firemní portál pro Windows 8.1 a Windows Phone 8.1 přechází do udržovacího režimu <!--1428681-->

Počínaje říjnem 2017 přejdou aplikace Portál společnosti pro Windows 8.1 a Windows Phone 8.1 do udržovacího režimu. To znamená, že tyto aplikace a existující scénáře (například registrace a dodržování předpisů) budou pro tyto platformy nadále podporovány. Tyto aplikace budu pořád dostupné ke stažení přes existující vydávací kanály, jako je Microsoft Store. 

Jakmile tyto aplikace budou v udržovacím režimu, budou dostávat jen důležité aktualizace zabezpečení. Pro tyto aplikace se už nebudou vydávat další aktualizace ani funkce. Kvůli novým funkcím doporučujeme zařízení aktualizovat na Windows 10 nebo Windows 10 Mobile. 


### <a name="block-unsupported-samsung-knox-device-enrollment----1490695---"></a>Blokování registrace nepodporovaných zařízení Samsung Knox  <!-- 1490695 -->

Aplikace Portál společnosti se pokusí zaregistrovat pouze podporovaná zařízení Samsung Knox. Aby se předešlo chybám při aktivaci zabezpečením Knox, které brání registraci MDM, pokus o registraci proběhne jenom u těch zařízení, která jsou v [seznamu zařízení publikovaném společností Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Některá čísla modelů zařízení Samsung mohou podporovat Knox, ale jiná nemusí. Než si zařízení koupíte a nasadíte, ověřte si u prodejce, zda je vaše zařízení kompatibilní se systémem Knox. Kompletní seznam ověřených zařízení najdete v [nastavení zásad pro Android a Samsung Knox Standard](supported-devices-browsers.md#intune-supported-web-browsers).

### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Ukončení podpory pro Android verze 4.3 a nižší <!-- 1171126, 1326920 -->
Spravované aplikace a aplikace Portál společnosti pro Android budou pro přístup k firemním prostředkům vyžadovat operační systém Android 4.4 nebo novější. Od prosince budou všechna zaregistrovaná zařízení vyřazena, čímž dojde ke ztrátě přístupu k firemním prostředkům. Pokud používáte zásady ochrany aplikací bez správy mobilních zařízení MDM, aplikace nebudou získávat aktualizace a kvalita jejich činnosti bude časem upadat.

### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Koncové uživatele informovat, jaké informace o zařízení můžete zobrazit na zaregistrovaném zařízení <!--1165314-->
Na obrazovku Podrobnosti o zařízení ve všech aplikacích Portál společnosti přidáváme **Typ vlastnictví**. Uživatelům to umožní zjistit další informace o ochraně osobních údajů přímo z článku [Jaké informace moje společnost uvidí?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Tuto funkci budeme v blízké budoucnosti postupně zavádět ve všech aplikacích Portál společnosti. Pro iOS jsme implementaci této funkce oznámili v [září](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).

<!-- ########################## -->
## <a name="september-2017"></a>Září 2017

### <a name="intune-supports-ios-11---1428975--"></a>Intune podporuje iOS 11 <!--1428975-->
Intune podporuje iOS 11. Tuto podporu jsme již dříve oznámili na [blogu podpory Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

### <a name="end-of-support-for-ios-80----1164477---"></a>Ukončení podpory pro systém iOS 8.0 <!-- 1164477 -->
Spravované aplikace a aplikace Portál společnosti pro iOS budou pro přístup k firemním prostředkům vyžadovat operační systém iOS 9.0 nebo novější. Zařízení, která nebudou do tohoto září aktualizována, již nebudou mít k těmto aplikacím nebo k Portálu společnosti přístup. 

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Do aplikace portál společnosti pro Windows 10 byla přidána akce aktualizace <!--1132468-->
Aplikace Portál společnosti pro Windows 10 umožňuje uživatelům aktualizovat data v aplikaci, a to buď potažením prstem, nebo stisknutím klávesy F5 na počítačích.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Koncové uživatele informovat, jaké informace o zařízení můžete zobrazit v Iosu <!--739894-->

Přidali jsme **typ vlastnictví** na obrazovku podrobnosti o zařízení v aplikaci portál společnosti pro iOS. Uživatelům to umožní zjistit další informace o ochraně osobních údajů přímo z této stránky z dokumentace Intune pro koncové uživatele. Tyto informace najdou také na obrazovce s informacemi o produktu.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Povolit koncovým uživatelům přístup k aplikaci portál společnosti pro Android bez registrace <!---1169910--->

Koncoví uživatelé brzy nebudou muset svá zařízení registrovat, aby získali přístup k aplikaci Portál společnosti pro Android. Koncovým uživatelům v organizacích, které používají zásady ochrany aplikací, už nebudou při otevření aplikace Portál společnosti chodit výzvy k registraci jejich zařízení. Koncoví uživatelé budou také moct bez registrace zařízení z Portálu společnosti instalovat aplikace. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Snadněji pochopit formulace pro aplikaci portál společnosti pro Android <!---1396349--->  

Proces registrace aplikace Portál společnosti pro Android byl zjednodušen novým textem, který koncovým uživatelům umožňuje jednodušší registraci. Pokud máte vlastní dokumentaci k registraci, měli byste ji aktualizovat, aby odrážela nové obrazovky. Ukázkové obrázky najdete na naší stránce [aktualizací uživatelského rozhraní aplikací Intune pro koncové uživatele](whats-new-app-ui.md#week-of-september-11-2017).

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Aplikace portál společnosti pro Windows 10 přidat do služby Windows Information Protection povolit zásadu <!-- 677129 -->

Aplikace Portál společnosti pro Windows 10 byla aktualizována o podporu WIP (Windows Information Protection). Tuto aplikaci lze přidat do zásad povolení WIP. Díky této změně se už tato aplikace nemusí přidávat do seznamu **výjimek**.


<!-- ########################## -->
## <a name="august-2017"></a>Srpen 2017

### <a name="improvements-to-device-overview----1404453---"></a>Vylepšení přehledu zařízení <!-- 1404453 -->  
Ve vylepšeném přehledu zařízení se teď zobrazují registrovaná zařízení, jsou ale vyloučena zařízení spravovaná přes Exchange Active Sync. Zařízení Exchange ActiveSync nemají stejné možnosti správy jako registrovaná zařízení. Pokud chcete v Intune na Azure Portalu zjistit počet registrovaných zařízení a počet registrovaných zařízení podle platformy, přejděte na **Zařízení** > **Přehled**.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Vylepšení inventáře zařízení shromažďovaného službou Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
V této verzi jsme udělali následující vylepšení inventarizačních informací shromažďovaných zařízeními, která spravujete:
 
-   Pro zařízení s Androidem teď můžete do inventáře zařízení přidat sloupec, ve kterém se zobrazuje nejnovější úroveň opravy jednotlivých zařízení. Tento údaj zobrazíte, když do seznamu zařízení přidáte sloupec **Úroveň opravy zabezpečení**.
-   Zobrazení zařízení teď můžete filtrovat podle data registrace zařízení. Můžete například zobrazit jen zařízení, která byla zaregistrována po zadaném datu.
-   Vylepšili jsme filtr, který se používá u údaje **Datum posledního ohlášení**.
-   V seznamu zařízení si teď u zařízení ve vlastnictví firmy můžete zobrazit telefonní číslo.
Pomocí podokna filtru můžete navíc vyhledat zařízení podle telefonního čísla.

Další podrobnosti o inventáři zařízení najdete v článku [Jak zobrazit inventář zařízení spravovaných přes Intune](device-inventory.md).

### <a name="conditional-access-support-for-macos-devices"></a>Podpora podmíněného přístupu pro zařízení s macOS 
<!-- 720172 -->
Teď můžete nastavit zásady podmíněného přístupu, které po zařízeních Mac vyžadují registraci v Intune a soulad se zásadami dodržování předpisů pro zařízení. Uživatelé si mohou například stáhnout aplikaci Portál společnosti Intune pro macOS a zaregistrovat svá zařízení Mac ve službě Intune. Intune prostřednictvím požadavků, jako je kód PIN, šifrování, verze operačního systému a integrita systému, vyhodnotí, zda zařízení Mac předpisy dodržuje nebo ne.

- Přečtěte si další informace o [podpoře podmíněného přístupu pro zařízení s macOS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>Aplikace portál společnosti pro macOS je ve verzi public preview <!---1484796--->
Aplikace Portál společnosti pro macOS je teď k dispozici jako součást verze Public Preview pro podmíněný přístup v Enterprise Mobility + Security. Tato verze podporuje macOS 10.11 a novější. Můžete ji získat zde: [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Nová nastavení omezení pro zařízení s Windows 10    
<!--1063965, 1308850  -->
V této verzi jsme přidali nová nastavení pro [profil omezení zařízení s Windows 10](/intune/device-restrictions-windows-10) v následujících kategoriích:

-   Filtr SmartScreen v programu Windows Defender
-   App Store

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Aktualizace profilu zařízení ochrany koncových bodů Windows 10 o nastavení BitLockeru
<!--1459533 -->     V této verzi jsme udělali následující vylepšení seznamů nastavení Bitlockeru v profilu zařízení ochrany koncových bodů Windows 10:
 
-   Když jste dříve v **Nastavení BitLockeru pro jednotky s operačním systémem** vybrali u nastavení **BitLocker s nekompatibilním čipem TPM** možnost **Blokovat**, ve skutečnosti se BitLocker povolil. Teď je to opravené a při výběru této možnosti se BitLocker zablokuje.
-   V **Nastavení BitLockeru pro jednotky s operačním systémem** teď můžete pomocí nastavení **Agent obnovení dat založený na certifikátech** explicitně zablokovat agenta obnovení dat založeného na certifikátech. Standardně je ale tento agent povolený.
-   V **Nastavení BitLockeru pro jednotky s operačním systémem** teď můžete pomocí nastavení **Agent obnovení dat** explicitně zablokovat agenta obnovení dat.
Další informace najdete v tématu o [nastavení služby Endpoint Protection pro Windows 10 a novější](endpoint-protection-windows-10.md).


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nové prostředí přihlášení pro uživatele portálu společnosti pro Android a uživatele zásad ochrany aplikací <!-- 621669 -->
Koncoví uživatelé teď můžou pomocí aplikace Portál společnosti pro Android procházet aplikace, spravovat zařízení a zobrazit kontakt na IT oddělení, aniž by své zařízení s Androidem zaregistrovali. Pokud už koncový uživatel používá aplikaci chráněnou zásadami Intune App Protection a spustí Portál společnosti pro Android, už se mu navíc nezobrazí výzva k registraci zařízení.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nové nastavení v aplikaci portál společnosti pro Android k přepnutí optimalizace baterie <!--1405990-->
Stránka **Nastavení** v aplikaci Portál společnosti pro Android obsahuje nové nastavení, které uživatelům umožní snadno vypnout optimalizaci baterie pro aplikace Portál společnosti a Microsoft Authenticator. Název aplikace uvedený v nastavení se liší v závislosti na tom, která aplikace spravuje pracovní účet. Doporučujeme, aby uživatelé optimalizaci baterie vypnuli kvůli lepšímu výkonu pracovních aplikací, které synchronizují e-maily a data. 

### <a name="multi-identity-support-for-onenote-for-ios----1234281---"></a>Podpora více identit pro aplikaci OneNote pro iOS      <!-- 1234281 -->
Koncoví uživatelé teď můžou v Microsoft OneNotu pro iOS používat různé účty (pracovní a osobní). Na firemní data v pracovních poznámkových blocích lze uplatnit zásady ochrany aplikací, aniž to ovlivní osobní poznámkové bloky. Pomocí zásad můžete například uživateli povolit hledání informací v pracovních poznámkových blocích, ale zabránit v kopírování a vkládání firemních dat z pracovních do osobních poznámkových bloků.
 
- Přečtěte si další informace o aplikacích, které podporují [ochranu aplikací a více identit](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) s Intune.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Nová nastavení, která povolí nebo blokují aplikace na zařízeních se zabezpečením Samsung Knox Standard
<!-- 1305423 822899-->  
V této verzi přidáváme nová [nastavení omezení zařízení](device-restrictions-android.md), která vám umožní zadat následující seznamy aplikací:
 
- Aplikace, které mají uživatelé dovoleno instalovat.
- Aplikace, které mají uživatelé zakázáno spouštět.
- Aplikace, které jsou před uživatelem zařízení skryté. 
Aplikaci můžete zadat pomocí adresy URL, názvu balíčku nebo ze seznamu spravovaných aplikací.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Odkaz na nové uživatelské rozhraní zásad podmíněného přístupu na základě aplikací Azure AD z Intune
<!-- 1016201 -->
Správci IT teď můžou nastavit podmíněné zásady na základě aplikací prostřednictvím nového uživatelského rozhraní zásad podmíněného přístupu v úloze Azure AD. Podmíněný přístup na základě aplikací, který je v části Intune App Protection na portálu Azure Portal, prozatím zůstane a bude se vynucovat souběžně. Užitečný odkaz na nové uživatelské rozhraní zásad podmíněného přístup obsahuje také úloha Intune.

- Přečtěte si další informace o [podmíněném přístupu na základě aplikací v Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).

<!-- ########################## -->
## <a name="july-2017"></a>Červenec 2017

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version-----1333256-1245463----"></a>Omezit omezení registrace zařízení s Androidem a Iosem podle verze operačního systému  <!--- 1333256,  1245463 --->
Intune nyní podporuje omezení registrace iOSu a Androidu podle čísla verze operačního systému. V části **Omezení typu zařízení** teď správce IT může nastavit konfiguraci platformy tak, aby se registrace omezovala na rozsah mezi minimální a maximální hodnotou verze operačního systému. Verze operačního systému Android je nutné zadávat ve formátu Hlavní.Podverze.Sestavení.Revize, kde Podverze, Sestavení a Revize jsou nepovinné hodnoty. Verze iOS je nutné zadávat ve formátu Hlavní.Podverze.Sestavení, kde Podverze a Sestavení jsou nepovinné hodnoty. Přečtěte si další informace o [omezení registrace zařízení](enrollment-restrictions-set.md).

>[!NOTE]
>Neomezuje registrace prostřednictvím registračních programů Apple nebo nástroje Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment-----1333272-1333275-1245709---"></a>Omezují Android, iOS a macOS registrace zařízení v osobním vlastnictví zařízení  <!--- 1333272,  1333275, 1245709 --->
Intune může omezit registraci osobních zařízení tím, že kódy IMEI podnikových zařízení umístí do seznamu povolených. Intune teď tuto funkci rozšířil na iOS, Android a macOS na základě sériových čísel zařízení. Nahráním sériových čísel do Intune můžete zařízení předem deklarovat jako majetek společnosti. Registrační omezení umožňují zablokovat zařízení v osobním vlastnictví (BYOD), aby se mohla registrovat jenom zařízení patřící společnosti. Přečtěte si další informace o [omezení registrace zařízení](enrollment-restrictions-set.md).

Pokud chcete importovat sériová čísla, přejděte na **Registrace zařízení** > **Identifikátory podnikových zařízení**, klikněte na **Přidat** a potom nahrajte soubor CSV (žádné záhlaví a dva odstavce pro sériová čísla a podrobnosti jako čísla IMEI). Pokud chcete omezit zařízení v osobním vlastnictví, přejděte na **Registrace zařízení** > **Omezení registrace**. V části **Omezení typů zařízení** vyberte **Výchozí** a potom vyberte **Konfigurace platformy**. Zařízení se systémem iOS, Android a macOS v osobním vlastnictví můžete **povolit** nebo **zakázat**.


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nová akce zařízení, která zařízení donutí provést synchronizaci s Intune <!-- 711369 -->
V této verzi jsme přidali novou akci zařízení, která vynutí u vybraného zařízení okamžité ohlášení ve službě Intune. Jakmile se zařízení ohlásí, začne okamžitě přijímat veškeré čekající akce nebo zásady, které mu byly přiřazeny.  Tato akce vám může pomoct okamžitě ověřit přiřazené zásady nebo s těmito zásadami vyřešit potíže, aniž byste čekali na další naplánované ohlášení.
Podrobnosti najdete v části [Synchronizace zařízení](device-sync.md).

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Zařízení s Iosem pod dohledem, automaticky instalovat nejnovější dostupnou aktualizaci softwaru vynutit <!-- 777100 -->
V pracovním prostoru Aktualizace softwaru jsou dostupné nové zásady, které přinutí monitorovaná zařízení s iOSem automaticky instalovat nejnovější dostupnou aktualizaci softwaru. Podrobnosti najdete v článku [Konfigurace zásad aktualizací pro iOS](/intune/software-updates-ios).

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner----954651-1172027---"></a>Check Point SandBlast Mobile – nový partner ochrany před mobilními hrozbami  <!-- 954651, 1172027 -->
Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Check Point SandBlast Mobile. Jedná se o řešení ochrany před mobilními hrozbami integrované ve službě Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak integrace se službou Intune funguje?
Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých služba Check Point SandBlast Mobile běží. Na základě posouzení rizik aplikací Check Point SandBlast Mobile, které umožňují zásady dodržování předpisů v Intune, můžete nakonfigurovat zásady podmíněného přístupu EMS. Podle zjištěných hrozeb můžete u zařízení nesplňujících požadavky povolit nebo zakázat přístup k podnikovým prostředkům.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Nasazení aplikace jako k dispozici ve službě Microsoft Store pro firmy <!-- 748101 -->
V této verzi teď správci můžou Microsoft Store pro firmy přiřadit jako dostupný. Pokud to udělají, koncoví uživatelé si můžou aplikaci nainstalovat z aplikace nebo webu Portál společnosti, aniž by byli přesměrováni do Microsoft Storu.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Aktualizace uživatelského rozhraní na webu portál společnosti <!--1313244 part 1-->
Provedli jsme několik aktualizací uživatelského rozhraní [webu Portál společnosti](https://portal.manage.microsoft.com) k vylepšení prostředí pro koncové uživatele.

- __Vylepšení dlaždic aplikací__:  Ikony aplikací se teď budou zobrazovat s automaticky generovaným pozadím na základě dominantní barvy ikony (Pokud se dá zjistit). Tam, kde se toto pozadí použije, nahradí šedé ohraničení, které bylo dříve vidět na dlaždicích aplikací.

    Web Portál společnosti bude v nadcházející verzi zobrazovat velké ikony, kdykoli to bude možné. Doporučujeme, aby správci IT publikovali aplikace pomocí ikon s vysokým rozlišením a minimální velikostí 120 x 120 pixelů. 

- __Změny v navigaci__: Položky navigačního panelu se přesouvají do "hamburgerové" nabídky vlevo nahoře. Stránka Kategorie byla odebrána. Uživatelé teď můžou filtrovat obsah podle kategorií během procházení.

- __Aktualizace pro vybrané aplikace__: Přidali jsme na web vyhrazenou stránku, kde můžou uživatelé procházet aplikace, které jste speciálně vybrali, a upravili jsme uživatelské rozhraní sekce Vybrané na domovské stránce.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Podpora iBooks pro web portál společnosti <!--1231841-->
Na web Portál společnosti jsme přidali speciálně určenou stránku, která uživatelům umožňuje procházet a stahovat knihy iBooks. 


### <a name="additional-help-desk-troubleshooting-details-----applies-to-1263399-1326964-1341642----"></a>Další technické podpoře podrobnosti o řešení problémů <!---  Applies to 1263399, 1326964, 1341642 --->
Intune má aktualizované zobrazení pro řešení problémů, které je doplněné k informacím poskytovaným správcům a pracovníkům helpdesku. Teď si můžete zobrazit tabulku **Přiřazení**, ve které jsou shrnuta všechna přiřazení uživatele na základě členství ve skupinách. Tento seznam obsahuje:
- Mobilní aplikace
- Zásady dodržování předpisů
- Konfigurační profily

Tabulka **Zařízení** teď navíc obsahuje sloupce **Typ připojení ke službě Azure AD** a **Vyhovuje Azure AD**. Další informace najdete v článku [Pomoc uživatelům s řešením problémů](help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Datový sklad Intune (Public Preview)
Datový sklad Intune denně vzorkuje data, aby mohl poskytovat historický přehled vašeho tenanta. K datům můžete mít získat přístup pomocí souboru Power BI (soubor PBIX) a odkazu OData, který je kompatibilní s celou řadu analytických nástrojů, nebo prostřednictvím interakce s rozhraním REST API. Další informace najdete v tématu [Použití Datového skladu Intune](reports-nav-create-intune-reports.md).


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Světlé a tmavé režimy dostupné pro aplikaci portál společnosti pro Windows 10 <!---676547--->
Koncoví uživatelé budou mít možnost přizpůsobit barevný režim aplikace Portál společnosti pro Windows 10. Uživatel může změny provádět v sekci Nastavení aplikace Portál společnosti. Změna se zobrazí, jakmile uživatel aplikaci restartuje. Pro Windows 10 verze 1607 a novější se režim aplikace nastaví podle výchozího nastavení systému. Pro Windows 10 verze 1511 a starší se režim aplikace nastaví do světlého režimu.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Povolit koncovým uživatelům, aby označit svou skupinu zařízení v aplikaci portál společnosti pro Windows 10 <!---807046-->
Koncoví uživatelé teď můžou vybrat, do které skupiny jejich zařízení patří, když ho označí přímo v aplikaci Portál společnosti pro Windows 10.

<!-- ########################## -->
## <a name="june-2017"></a>Červen 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Nový přístup správy na základě role pro správce Intune   <!-- 1099990 -->  
Přidáváme novou roli správce podmíněného přístupu, která umožňuje zobrazit, vytvořit, upravit a odstranit zásady podmíněného přístupu Azure AD. Dříve měli toto oprávnění jenom globální správci a správci zabezpečení. Oprávnění této role se může udělit správcům Intune, kteří pak mají přístup k zásadám podmíněného přístupu.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Označení zařízení vlastněných společností pomocí sériového čísla <!-- 1215070 -->  
Intune nyní podporuje ukládání sériových čísel v systémech iOS, macOS a Android jako identifikátorů podnikových zařízení. Sériová čísla nemůžete používat k blokování registrace osobních zařízení, protože sériová čísla se při registraci neověřují. Blokování osobních zařízení podle sériového čísla bude dostupné v blízké budoucnosti.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>Nové vzdálené akce pro zařízení s Iosem <!-- 854689 -->
V této verzi jsme přidali dvě nové akce vzdáleného zařízení pro sdílené iPady, které spravují aplikaci Apple Classroom:

-   [Odhlásit aktuálního uživatele](device-logout-user.md) – odhlásí aktuálního uživatele na vybraném zařízení s iOSem.
-   [Odebrat uživatele](device-remove-user.md) – odstraní vybraného uživatele z místní mezipaměti zařízení s iOSem.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Podpora pro sdílené Ipady s aplikací Classroom pro iOS <!-- 1044681 -->
V této verzi jsme rozšířili podporu správy aplikace Classroom pro iOS tak, aby zahrnovala studenty, kteří se přihlásí do sdílených iPadů pomocí svých spravovaných Apple ID.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Změny integrovaných aplikací Intune <!-- 1332306 -->
Dříve služba Intune obsahovala řadu integrovaných aplikací, které jste mohli rychle přiřadit. Na základě vaší zpětné vazby jsme tento seznam odebrali a integrované aplikace už neuvidíte.
Pokud jste už ale nějaké integrované aplikace přiřadili, budou se v seznamu aplikací dál zobrazovat. Tyto aplikace můžete dál přiřazovat podle potřeby.
V pozdější verzi plánujeme přidat jednodušší způsob výběru a přiřazování integrovaných aplikací z Azure Portalu.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Snadnější instalace aplikací Office 365 <!--- 1121362 --->
Nový typ aplikace **Office 365 ProPlus** vám usnadní přiřazování aplikací Office 365 ProPlus 2016 na vámi spravovaná zařízení, na kterých běží nejnovější verze Windows 10. Pokud vlastníte příslušné licence, můžete si také nainstalovat Microsoft Project a Microsoft Visio. Požadované aplikace jsou spojeny dohromady a v seznamu aplikací v konzole Intune se zobrazují jako jedna aplikace.
Další informace najdete v tématu [Jak přidat aplikace Office 365 pro Windows 10](apps-add-office365.md).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>Podpora pro offline aplikace z Microsoft Store pro firmy <!--- 777044 --->
Aplikace Offline zakoupené v Microsoft Storu pro firmy se teď budou synchronizovat na Azure Portal. Tyto aplikace můžete nasadit pro skupiny zařízení nebo skupiny uživatelů. Offline aplikace bude instalovat služba Intune, nikoli Store.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Microsoft teams je nyní součástí seznamu schválených aplikací podmíněným Přístupem založeným na aplikaci   <!-- 1257019 -->
Aplikace Microsoft Teams pro iOS a Android je nyní součástí schválených aplikací pro zásady podmíněného přístupu podle aplikací pro Exchange a SharePoint Online. Aplikaci lze nakonfigurovat prostřednictvím okna Intune App Protection na portálu Azure Portal pro všechny tenanty aktuálně používající podmíněný přístup podle aplikací.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Spravovaný prohlížeč a integrace proxy aplikace <!-- 1287310 -->
Spravovaný prohlížeč Intune Managed Browser je nyní možné integrovat do služby Azure AD Application Proxy, což umožní uživatelům získat přístup k interním webům, i když pracují vzdáleně. Uživatelé prohlížeče jako obvykle zadají adresu URL webu a Managed Browser požadavek prostřednictvím webové brány proxy aplikace přesměruje. Další informace najdete v tématu [Správa přístupu k internetu pomocí zásad spravovaného prohlížeče](app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Nová nastavení konfigurace aplikace Intune Managed Browser <!-- 682951 -->
V této verzi jsme pro aplikaci Intune Managed Browser pro iOS a Android přidali další konfigurace. Pomocí zásad konfigurace aplikace nyní můžete prohlížeči nakonfigurovat výchozí domovskou stránku a záložky.
Další informace najdete v tématu [Správa přístupu k internetu pomocí zásad spravovaného prohlížeče](app-configuration-managed-browser.md).

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Nastavení Bitlockeru pro Windows 10  <!-- 951707 -->
Nyní můžete nastavení nástroje BitLocker konfigurovat pro zařízení s Windows 10 pomocí nového profilu zařízení Intune. Například můžete vyžadovat, aby se zařízení šifrovala, a také nakonfigurovat další nastavení, která se použijí při zapnutí nástroje BitLocker.
Další informace najdete v tématu o [nastavení služby Endpoint Protection pro Windows 10 a novější](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Nová nastavení pro profil omezení zařízení s Windows 10 <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
V této verzi jsme přidali nová nastavení pro profil omezení zařízení s Windows 10 v následujících kategoriích:

-  Windows Defender
-  Mobilní síť a připojení
-  Prostředí zamknuté obrazovky
-  Ochrana osobních údajů
-  Search
-  Windows Spotlight
-  Prohlížeč Microsoft Edge

Další informace o nastavení Windows 10 najdete v tématu [Nastavení omezení pro zařízení Windows 10 a novější](device-restrictions-windows-10.md).


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Aplikace portál společnosti pro Android má teď novou činnost koncového uživatele pro zásady ochrany aplikací <!--1305217-->
Na základě zpětné vazby od zákazníků jsme aplikaci Portál společnosti pro Android upravili tak, aby zobrazovala tlačítko **Přístup k obsahu společnosti**. Naším záměrem je předejít zbytečné registraci koncových uživatelů, když pouze potřebují přístup k aplikacím s podporou zásad ochrany aplikací – funkce správy mobilních aplikací Intune. Tyto změny najdete na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nová akce nabídky ke snadnému odebrání portálu společnosti <!--1164569-->
Na základě zpětné vazby od uživatelů jsme do aplikace Portál společnosti pro Android přidali novou akci nabídky k zahájení odebrání Portálu společnosti ze zařízení. Tato akce odebere zařízení ze správy Intune, aby uživatel mohl aplikaci ze zařízení odebrat. Tyto změny najdete na stránce [novinek v uživatelském rozhraní aplikace](whats-new-app-ui.md) a v [dokumentaci pro koncové uživatele Androidu](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Vylepšení synchronizace aplikace s Windows 10 Creators Update <!--676505-->
Aplikace Portál společnosti pro Windows 10 teď automaticky zahájí synchronizaci pro požadavky na instalaci zařízení s Windows 10 Creators Update (verze 1703). Omezí se tím potíže s pozastavením instalací aplikace ve stavu čekající synchronizace. Uživatelé navíc budou moct synchronizaci zahájit ručně uvnitř aplikace. Tyto změny najdete na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nové prostředí s asistencí pro portál společnosti pro Windows 10 <!---1058938--->
Aplikace Portál společnosti pro Windows 10 bude obsahovat návod s pokyny Intune pro zařízení, která nejsou identifikovaná nebo zaregistrovaná. Nové prostředí obsahuje podrobné pokyny, které provedou uživatele registrací do Azure Active Directory (která je nutná pro funkce podmíněného přístupu), a zápis do MDM (který je nutný pro funkce správy zařízení). Prostředí s asistencí bude přístupné z domovské stránky portálu společnosti. Uživatelé můžou aplikaci dál používat, i když registraci a zápis neprovedou, ale budou mít k dispozici omezené funkce.

Tato aktualizace se zobrazí pouze na zařízení s Windows 10 Anniversary Update (build 1607) a novějšími verzemi. Tyto změny najdete na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md).


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Konzoly správců Microsoft Intune a podmíněného přístupu jsou obecně dostupné
Oznamujeme obecnou dostupnost nové služby Intune v konzole správce Azure Portalu a v konzole správce podmíněného přístupu. Prostřednictvím Intune na Azure Portalu teď můžete spravovat všechny funkce Intune MAM a MDM v jednom sjednoceném prostředí pro správce a využívat seskupování a cílení služby Azure AD. Podmíněný přístup v Azure přináší bohaté možnosti v rámci Azure AD a Intune společně v jedné sjednocené konzole. A z prostředí pro správu vám přechod na platformu Azure umožňuje používat moderní prohlížeče.

Intune se teď na Azure Portalu na adrese portal.azure.com zobrazuje bez popisku **Preview**.

Pokud jste v centru zpráv nedostali některou z řady zpráv požadující provedení nějaké akce, abychom mohli migrovat vaše skupiny, nemusíte jako stávající zákazníci nic dělat. Možná jste také v centru zpráv dostali oznámení, že migrace trvá déle z důvodu chyb na naší straně. Usilovně pokračujeme v práci na migraci všech ovlivněných zákazníků.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Vylepšení dlaždic aplikací v aplikaci Portál společnosti pro iOS
Aktualizovali jsme vzhled dlaždic aplikací na domovské stránce tak, aby odrážely barvu brandingu nastavenou v Portálu společnosti. Další informace najdete v [novinkách v uživatelském rozhraní aplikace](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Pro aplikaci Portál společnosti pro iOS je teď dostupný výběr účtu
Uživatelům zařízení s iOSem se při přihlašování do Portálu společnosti může zobrazit náš nový výběr účtu, pokud k přihlašování do jiných aplikací Microsoftu používají svůj pracovní nebo školní účet. Další informace najdete v [novinkách v uživatelském rozhraní aplikace](whats-new-app-ui.md).

<!-- ########################## -->
## <a name="may-2017"></a>Květen 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Změna autority MDM bez zrušení registrace spravovaných zařízení <!--1103950-->
Autoritu pro správu mobilních zařízení teď můžete změnit, aniž byste museli kontaktovat podporu Microsoftu a zrušit registraci a provést novou registraci stávajících spravovaných zařízení. V konzole Configuration Manageru můžete [změnit autoritu pro správu mobilních zařízení](/sccm/mdm/deploy-use/change-mdm-authority) z Nastavit na nástroj Configuration Manager (hybridní) na Microsoft Intune (samostatné) a naopak.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Vylepšené oznámení pro spouštěcí PIN kódy Samsung Knox <!--1087143-->
Pokud koncoví uživatelé na zařízeních se zabezpečením Samsung Knox potřebují nastavit spouštěcí PIN, aby vyhovoval požadavkům na šifrování, přenese je oznámení, které se zobrazí po klepnutí, přímo na místo v aplikaci Nastavení.  Dříve oznámení odkázalo koncové uživatele na obrazovku pro změnu hesla.

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Podpora Apple School Manageru (ASM) se sdíleným Ipadem <!-- 748864, 770395-->

Pro první registraci zařízení s iOSem teď Intune místo programu Apple Device Enrollment Program podporuje použití Apple School Manageru (ASM). K použití aplikace Classroom pro sdílené iPady a k povolení synchronizace dat z ASM do Azure Active Directory prostřednictvím služby Synchronizace školních dat Microsoftu se vyžaduje zprovoznění ASM. Další informace najdete v tématu [Povolení registrace zařízení s iOSem pomocí Apple School Manageru](apple-school-manager-set-up-ios.md).

> [!NOTE]
> Konfigurace fungování sdílených iPadů s aplikací Classroom vyžaduje konfigurace iOS Education v Azure, které ještě nejsou k dispozici.  Tato funkce bude brzy přidána.

### <a name="device-management"></a>Správa zařízení

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Poskytnutí vzdálené pomoci pro zařízení s Androidem pomocí Teamvieweru <!-- 675418 -->

Intune vám teď pomocí softwaru [TeamViewer](https://www.teamviewer.com), který se prodává zvlášť, umožňuje poskytovat vzdálenou pomoc uživatelům používajícím zařízení s Androidem. Další informace najdete v článku o [poskytování vzdálené pomoci pro zařízení s Androidem, která se spravují přes Intune](device-profile-android-teamviewer.md).

### <a name="app-management"></a>Správa aplikací

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>Nové podmínky zásad ochrany aplikací pro MAM <!-- 679864 -->

Teď můžete nastavit požadavek pro MAM bez uživatelů registrace, který vynucuje tyto zásady:

- Minimální verzi aplikací
- Minimální verzi operačního systému
- Minimální verzi Intune APP SDK cílové aplikace (pouze iOS)

Tato funkce je k dispozici pro Android i iOS. Intune podporuje vynucení minimální verze pro verze platformy OS, verze aplikací a Intune APP SDK. V iOSu můžou aplikace s integrovanou sadou SDK také nastavit vynucení minimální veze na úrovni SDK. Pokud nebudou splněny minimální požadavky prostřednictvím zásad ochrany aplikace na třech různých úrovních uvedených výše, uživatel nebude moct k cílové aplikaci přistupovat. Uživatel teď může odebrat svůj účet (pro aplikace s více identitami), zavřít aplikaci nebo aktualizovat verzi operačního systému nebo aplikace.

Můžete také nakonfigurovat další nastavení, abyste poskytovali neblokující oznámení, které bude doporučovat upgrade operačního systému nebo aplikace. Toto oznámení se dá zavřít a aplikace se dá používat jako obvykle.

Další informace najdete v [Nastavení zásad ochrany aplikací pro iOS](app-protection-policy-settings-ios.md) a [Nastavení zásad ochrany aplikací pro Android](app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Konfigurace aplikací pro Android for Work <!-- 621621 -->
Některé aplikace pro Android z obchodu podporují možnosti spravované konfigurace, které správci IT umožňují řídit, jak aplikace běží v pracovním profilu. S Intune teď můžete zobrazit konfigurace podporované aplikací a nakonfigurovat je z Azure Portalu pomocí návrháře konfigurace nebo editoru JSON. Další informace najdete v článku o [používání konfigurací aplikací pro Android for Work](app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Nová možnost konfigurace aplikací pro MAM bez registrace <!-- 677969 -->
Teď můžete vytvářet zásady konfigurace aplikací prostřednictvím MAM bez kanálu registrace. Tato funkce je ekvivalentní zásadám konfigurace aplikací dostupným v konfiguraci aplikací ve správě mobilních zařízení (MDM). Příklad konfigurace aplikací pomocí MAM bez registrace najdete v článku o [správě přístupu k internetu pomocí zásad Managed Browseru v Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Konfigurace seznamů povolených a blokovaných adres URL pro Managed Browser <!-- 682960 -->
Teď můžete nakonfigurovat seznam povolených a blokovaných domén a adres URL pro Intune Managed Browser pomocí nastavení konfigurace aplikací na portálu Azure Portal. Tato nastavení jde nakonfigurovat bez ohledu na to, jestli se používá na spravovaném nebo nespravovaném zařízení. Další informace najdete v článku o [správě přístupu k internetu pomocí zásad Managed Browseru v Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Zobrazení helpdesku zásady ochrany aplikací <!-- 1069473 -->
Uživatelé IT Helpdesku teď můžou zkontrolovat stav licencí uživatelů a stav zásad ochrany aplikací přiřazených uživatelům v okně Řešení potíží. Podrobnosti najdete v tématu o [řešení potíží](./help-desk-operators.md).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Řízení navštěvování webů na zařízeních s Iosem <!-- 723832 -->
Můžete teď řídit, které webové stránky můžou uživatelé zařízení s iOSem navštívit, a to pomocí jedné z těchto dvou metod:

- Přidejte povolené a blokované adresy URL pomocí integrovaného filtru webového obsahu od společnosti Apple.

- Povolte přístup z prohlížeče Safari jenom k určeným webovým stránkám. V Safari se vytvoří záložky pro weby, které určíte.

Další informace najdete v článku o [nastavení filtru webového obsahu pro zařízení s iOSem](web-content-filter-settings-ios.md).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Konfigurace oprávnění zařízení pro Android pro pracovní aplikace <!-- 621614 -->
U aplikací nasazených do pracovních profilů zařízení Android for Work můžete teď nakonfigurovat stav oprávnění pro jednotlivé aplikace.  Aplikace pro Android, které vyžadují oprávnění zařízení, jako je například přístup k umístění nebo fotoaparátu zařízení, ve výchozím nastavení vyzvou uživatele, aby oprávnění přijali nebo odmítli.  Pokud například aplikace používá mikrofon zařízení, potom bude koncový uživatel vyzván, aby aplikaci udělil oprávnění používat mikrofon. Tato funkce umožňuje definovat oprávnění jménem koncového uživatele.  Můžete nakonfigurovat oprávnění k a) automatickému odmítnutí bez upozornění uživatele, b) automatickému schválení bez upozornění uživatele nebo c) vyzvání uživatele k přijmutí nebo odmítnutí. Další informace najdete v článku [Nastavení omezení pro zařízení s Androidem for Work v Microsoft Intune](device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Definovat PIN kódu aplikace pro Android pro pracovní zařízení <!-- 728976, 1102534 -->
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
Při vytváření profilu certifikátu SCEP je pro <strong>Formát názvu subjektu</strong> dostupná možnost <strong>Vlastní</strong> pro zařízení s iOSem, Androidem a Windows. Před touto aktualizací bylo pole <strong>Vlastní</strong> k dispozici jenom pro zařízení s iOSem. Další informace najdete v tématu [Vytvoření profilu certifikátu SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile).

Při vytváření profilu certifikátu PKCS je pro **Alternativní název subjektu** dostupná možnost **Vlastní atribut Azure AD**. Když vyberete **Vlastní atribut Azure AD**, je dostupná možnost **Oddělení**. Další informace najdete v tématu [Vytvoření profilu certifikátu PKCS](certficates-pfx-configure.md#create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Konfigurace víc aplikací, které můžete spustit, když je zařízení s Androidem v celoobrazovkovém režimu. <!-- 662059 -->
Když je zařízení s Androidem v režimu veřejného terminálu, mohli jste dřív konfigurovat jenom jednu aplikaci, která mohla být spuštěná. Teď můžete konfigurovat víc aplikací pomocí ID aplikace, adresy URL obchodu nebo výběrem aplikace pro Android, kterou už spravujete. Další informace najdete v tématu o [nastavení režimu veřejného terminálu (kiosku)](device-restrictions-android.md#kiosk).



<!-- ########################## -->
## <a name="april-2017"></a>Duben 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Podpora správy aplikace Apple Classroom
Na iPadech teď můžete spravovat aplikaci Classroom pro iOS. Nainstalujte aplikaci Classroom na iPady učitelů se správnými údaji o předmětu a studentech, pak nakonfigurujte iPady studentů zaregistrované k předmětu, abyste je mohli pomocí této aplikace ovládat.
Podrobnosti najdete v článku [Konfigurace nastavení iOS Education](education-settings-configure-ios.md).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Podpora možností spravované konfigurace aplikací pro Android <!-- 621621 -->
Aplikace Android v obchodu Play podporující možnosti spravované konfigurace se teď dají konfigurovat pomocí Intune.  Tato funkce umožňuje IT pracovníkům zobrazit seznam hodnot konfigurace podporovaných aplikací a poskytuje prvotřídní uživatelské rozhraní s asistencí, které jim umožňuje tyto hodnoty konfigurovat.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nové zásady Androidu pro komplexní kódy PIN <!-- 722069 -->
V profilu zařízení s Androidem 5.0 a vyšším teď můžete nastavit požadovaný typ [hesla](device-restrictions-android.md#password) na Číselné komplexní.  Pomocí tohoto nastavení můžete uživatelům zařízení zabránit ve vytvoření PINu, který obsahuje opakující se nebo po sobě jdoucí čísla jako 1111 nebo 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Další podpora pro zařízení s Androidem for Work
- **Spravovat nastavení hesla a pracovního profilu** <!-- 612808 -->

  Tato nová zásada omezení pro zařízení s Androidem for Work vám teď umožní spravovat nastavení hesla a pracovního profilu na zařízeních s Androidem for Work, která spravujete.

- **Povolit sdílení dat mezi pracovními a osobními profily** <!-- 1045102 -->

Tento profil pro omezení zařízení s Androidem for Work teď obsahuje nové možnosti, které vám pomůžou nakonfigurovat sdílení dat mezi pracovním a osobním profilem.

- **Omezit kopírování a vkládání mezi pracovními a osobními profily** <!-- 1046094 -->

  Nový vlastní profil zařízení pro zařízení s Androidem for Work teď umožňuje zakázat akce Kopírovat a Vložit mezi pracovními a osobními aplikacemi.

Další informace najdete v tématu o [omezeních zařízení pro Android for Work](device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Přiřazení obchodních aplikací pro iOS a androidem <!-- 1057568 -->
Uživatelům nebo zařízením teď můžete přiřadit obchodní aplikace pro [iOS](lob-apps-ios.md) (soubory .ipa) a [Android](lob-apps-android.md) (soubory .apk).


###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Nové zařízení zásady pro iOS <!-- 723774, 723815, 723826, 723830 -->
- **Aplikace na ploše** – určuje, které aplikace uživatelé uvidí na [ploše svého zařízení s iOSem](home-screen-settings-ios.md). Tato zásada změní rozložení plochy, ale nenasadí žádné aplikace.

- **Připojení k zařízením AirPrint** – určuje, ke kterým [zařízením AirPrint](air-print-settings-ios-macos.md) (síťovým tiskárnám) se můžou koncoví uživatelé zařízení s iOSem připojit.

- **Připojení k zařízením AirPlay** – určuje, ke kterým [zařízením AirPlay](airplay-settings-ios.md) (jako Apple TV) se můžou koncoví uživatelé zařízení s iOSem připojit.

- **Vlastní zpráva na zamčené obrazovce** – nakonfigurujte vlastní zprávu, která se zobrazí uživatelům na zamčené obrazovce jejich zařízení s iOSem místo výchozí zprávy. Další informace najdete v tématu [Aktivace režimu ztráty u zařízení s iOSem](device-lost-mode.md)

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Omezení nabízených oznámení pro aplikace pro iOS <!-- 723767 -->
V profilu omezení zařízení Intune teď můžete nakonfigurovat tato [nastavení oznámení](app-notification-settings-ios.md) pro zařízení s iOSem:

- Úplně zapnout nebo vypnout oznámení pro konkrétní aplikaci
- Zapnut nebo vypnout oznámení v centru oznámení pro konkrétní aplikaci
- Určit typ upozornění, a to buď **žádné**, **banner** nebo **modální upozornění**
- Určit, jestli jsou pro tuto aplikaci povolené odznaky
- Určit, jestli jsou povolené zvuky oznámení

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Konfigurace aplikací pro iOS autonomně spouštění v režimu jedné aplikace <!-- 737837 -->
Pomocí profilu zařízení Intune teď můžete nakonfigurovat, aby zařízení s iOSem spouštěla zadané aplikace v [autonomním režimu jedné aplikace](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only). Pokud je tento režim nakonfigurovaný a uživatel spustí aplikaci, v zařízení se zablokuje spuštění jakékoli další aplikace. Příkladem je nakonfigurování aplikace, která uživatelům umožňuje absolvovat na zařízení test. Když se akce aplikace dokončí nebo tuto zásadu odeberete, zařízení se vrátí do normálního stavu.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Konfigurace důvěryhodných domén pro e-mailu a procházení webu v zařízení s Iosem <!-- 723765 -->
V profilu omezení zařízení s iOSem teď můžete nakonfigurovat tato [nastavení domén](device-restrictions-ios.md#domains):

- **Zrušit označení e-mailových domén** – E-maily, které uživatel posílá nebo přijímá a které neodpovídají doménám zadaným tady, se označí jako nedůvěryhodné.

- **Spravované webové domény** – Dokumenty stažené z adres URL, které zadáte tady, se budou považovat za spravované (jenom Safari).  

- **Domény pro automatické vyplňování hesel v Safari**  – Uživatelé můžou ukládat hesla v Safari jenom z adres URL odpovídajících vzorům, které tady zadáte. Pokud toto nastavení chcete použít, musí být zařízení v režimu pod dohledem a nesmí být nakonfigurované pro více uživatelů. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>K dispozici v aplikaci portál společnosti pro iOS aplikace VPP <!-- 748782 -->
Multilicenční aplikace (VPP) pro iOS teď můžete koncovým uživatelům přiřadit jako **Dostupné** instalace. Koncoví uživatelé budou k instalaci aplikace potřebovat účet Apple Store.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Synchronizace elektronických knih z Apple VPP Store <!-- 800878 -->
Pomocí Intune můžete [synchronizovat knihy](vpp-apps-ios.md), které jste zakoupili z Apple Storu v rámci multilicenčního programu, a přiřadit je uživatelům.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Správa více uživatelů pro zařízení Samsung Knox Standard <!-- 971988 -->
U zařízení, která používají Samsung Knox Standard, je teď v Intune podporovaná [správa více uživatelů](android-enroll.md). To znamená, že koncoví uživatelé se můžou k zařízení přihlašovat a ze zařízení odhlašovat pomocí svých přihlašovacích údajů Azure Active Directory a zařízení je centrálně spravované bez ohledu na to, jestli se zrovna používá.  Když se koncoví uživatelé přihlásí, mají přístup k aplikacím a také se na ně vztahují všechny zásady. Po odhlášení uživatelů se všechna data aplikací vymažou.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Další nastavení omezení zařízení s Windows <!-- 818566 -->
Přidali jsme podporu dalších [nastavení omezení pro zařízení s Windows](device-restrictions-windows-10.md), jako je dodatečná podpora prohlížeče Edge, přizpůsobení zamykací obrazovky zařízení, přizpůsobení nabídky start, tapeta nastavená z vyhledávání ve Windows Spotlight a nastavení proxy serveru.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Podpora více uživatelů pro Windows 10 Creators Update <!-- 822547 -->
Přidali jsme podporu [správy více uživatelů](windows-enroll.md) pro zařízení s Windows 10 Creators Updatem připojená k doméně Azure Active Directory. To znamená, že když se k zařízení přihlásí různí standardní uživatelé pomocí svých přihlašovacích údajů Azure AD, dostanou všechny aplikace a zásady přiřazené k jejich uživatelskému jménu. Uživatelé v současnosti nemůžou používat Portál společnosti pro samoobslužné scénáře, například instalování aplikací.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Akce začít znovu pro počítače s Windows 10<!-- 1004830 -->
K dispozici je teď nová [akce zařízení Začít znovu](device-fresh-start.md) pro počítače s Windows 10.  Když tuto akci provedete, odeberou se všechny aplikace, které byly v počítači PC nainstalované, a počítač PC se automaticky aktualizuje na nejnovější verzi Windows. To se dá využít k odebrání aplikací předem nainstalovaných výrobcem, které se často dodávají s novým počítačem PC. Můžete nakonfigurovat, jestli se při provedení této akce mají zachovat uživatelská data.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Další cesty upgradu Windows 10 <!-- 903672 -->
Vytvořením [zásad upgradu edice teď můžete zařízení upgradovat](edition-upgrade-configure-windows-10.md) na následující další edice Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Hromadná registrace Windows 10 zařízení <!-- 747607 -->
K Azure Active Directory a Intune můžete teď pomocí Windows Configuration Designeru (WCD) připojit velký počet zařízení s Windows 10 Creators Updatem. Pokud chcete pro svého tenanta Azure AD povolit [hromadnou registraci MDM](windows-bulk-enroll.md), vytvořte zřizovací balíček, který zařízení k tenantovi Azure AD připojí pomocí Windows Configuration Designeru, a použijte balíček na zařízení ve vlastnictví firmy, která chcete hromadně zaregistrovat a spravovat. Po použití balíčku se zařízení připojí k Azure AD, zaregistrují v Intune a jsou připravená na přihlašování vašich uživatelů z Azure AD.  Uživatelé Azure AD jsou na těchto zařízeních standardními uživateli a obdrží přiřazené zásady a požadované aplikace. Samoobslužné scénáře a scénáře s Portálem společnosti v současnosti nejsou podporované.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Nová nastavení MAM pro PIN a spravovaná umístění úložiště <!-- 581122, 736644 -->
K dispozici jsou teď dvě nová nastavení aplikací, která vám pomůžou se scénáři správy mobilních aplikací (MAM):

- **Zakázat PIN kód aplikace, když je PIN kód zařízení spravovaný** – zjistí, jestli se na zaregistrovaném zařízení nachází PIN zařízení, a pokud ano, obchází PIN aplikace aktivovaný zásadami ochrany aplikací. Toto nastavení umožní snížit počet případů, kdy se uživatelům při spuštění aplikace s povolenou správou mobilních zařízení na zaregistrovaném zařízení zobrazí výzva k zadání PINu. Tato funkce je k dispozici pro Android i iOS.

- **Vyberte, do kterých služeb úložiště se můžou ukládat firemní data** – umožňuje určit umístění úložiště, do kterých se můžou ukládat firemní data. Uživatelé můžou ukládat do zvolených služeb umístění úložiště, takže všechny ostatní služby umístění úložiště, které nejsou uvedené, budou zablokované.

  Seznam podporovaných služeb umístění úložiště:

  - OneDrive
  - Business SharePoint Online
  - Místní úložiště

### <a name="help-desk-troubleshooting-portal----907448---"></a>Portál helpdesku pro řešení potíží <!-- 907448 -->
Nový [portál pro řešení potíží](help-desk-operators.md) umožňuje operátorům helpdesku a správcům Intune zobrazit uživatele a jejich zařízení a provádět úlohy k vyřešení technických problémů Intune.

<!-- ########################## -->
## <a name="march-2017"></a>Březen 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Podpora režimu ztráty pro iOS <!--431695-->
Pro zařízení s iOSem 9.3 nebo novějším je v Intune přidaná podpora pro **režim ztráty**. Teď máte možnost zařízení uzamknout, aby se nedalo používat, a na jeho zamykací obrazovce zobrazit zprávu a kontaktní telefonní číslo.

Koncový uživatel nebude moct zařízení odemknout, dokud správce režim ztráty nevypne. Když je režim ztráty zapnutý, můžete pomocí akce **Najít zařízení** zobrazit zeměpisnou polohu zařízení na mapě v konzole Intune.

Musí se jednat o zařízení s iOSem ve vlastnictví firmy, které je zaregistrované prostřednictvím programu DEP a je v režimu dohledu.

Další informace najdete v článku [Co je správa zařízení v Microsoft Intune](device-management.md).

### <a name="improvements-to-device-actions-report---677150--"></a>Vylepšení sestavy akce zařízení <!--677150-->
Sestavu Akce zařízení jsme vylepšili z hlediska výkonu. Tuto sestavu teď navíc můžete filtrovat podle stavu. Filtrováním sestavy můžete například zobrazit jen akce zařízení, které byly dokončeny.

### <a name="custom-app-categories---748805--"></a>Vlastní kategorie aplikací <!--748805-->
Teď můžete vytvářet, upravovat a přiřazovat kategorie pro aplikace, které přidáte do Intune. V současné době se kategorie dají zadávat jenom v angličtině.
Přečtěte si téma [Jak přidat aplikaci do Intune](apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Přiřazení obchodních aplikací pro uživatele s nezaregistrovanými zařízeními <!--748823-->
Obchodní aplikace a aplikace z obchodu teď můžete přiřazovat bez ohledu na to, jestli zařízení jsou, nebo nejsou zaregistrovaná do Intune. Pokud zařízení uživatele není zaregistrované v Intune, musí kvůli jeho instalaci přejít na web Portál společnosti, ne do aplikace Portál společnosti.

### <a name="new-compliance-reports---846671--"></a>Nové sestavy dodržování předpisů <!--846671-->
Teď máte k dispozici sestavy dodržování předpisů, ze kterých zjistíte, nakolik zařízení ve firmě dodržují předpisy, a které vám pomůžou rychle vyřešit problémy uživatelů související s dodržováním předpisů. Můžete zjistit:

- Celkový stav dodržování předpisů zařízeními
- Stav dodržování předpisů pro individuální nastavení
- Stav dodržování předpisů pro individuální zásadu

Tyto sestavy vám také umožňují přejít až k individuálnímu zařízení a zobrazit konkrétní nastavení a zásady, které se tohoto zařízení týkají.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Přímý přístup ke scénářům registrace Apple <!--951869-->
U účtů Intune vytvořených po lednu 2017 umožňuje Intune přímý přístup ke scénářům registrace Apple pomocí úlohy Registrovat zařízení na portálu Azure Portal. Náhled na registraci Apple byl předtím přístupný jen přes odkazy na Azure Portalu. Zpřístupnění těchto funkcí v Azure bude u účtů Intune vytvořených před lednem 2017 vyžadovat jednorázovou migraci. Plán této migrace zatím nebyl oznámen, podrobnosti ale budou zpřístupněny co nejdříve. Pokud váš existující účet nemá k tomuto náhledu přístup, k otestování tohoto nového prostředí důrazně doporučujeme vytvořit zkušební účet.


<!-- ########################## -->
## <a name="february-2017"></a>Únor 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Možnost omezení registrace mobilního zařízení <!--747600, 795782-->
Intune přidává nová omezení registrace řídící to, které platformy mobilních zařízení se mohou zaregistrovat. Intune odděluje platformy mobilních zařízení, jako je iOS, macOS, Android, Windows a Windows Mobile.

* Omezení registrace mobilních zařízení neomezuje registraci klienta pro počítače.  
* Pouze pro iOS a Android existuje další možnost blokování registrace osobních zařízení.

Pokud správce IT neoznačí nová zařízení jako vlastněná podnikem, Intune všechna nová zařízení označí jako osobní. Podrobnosti najdete v [tomto článku](device-enrollment.md).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Zobrazení všech akcí na spravovaných zařízeních <!--677150-->
V nové sestavě __Akce zařízení__ se zobrazí, kdo provedl vzdálené akce, jako je obnovení továrního nastavení zařízení, a dále stav dané akce. Viz [Co je správa zařízení?](device-management.md)

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Nespravovaná zařízení můžete přístup k přiřazeným aplikacím <!--664691-->
Jako součást změn v návrhu na webu Portál společnosti budou moci uživatelé iOSu a Androidu na svoje nespravovaná zařízení instalovat aplikace, které mají přiřazené jako dostupné bez registrace. S použitím přihlašovacích údajů pro Intune se budou moct uživatelé přihlásit na web Portál společnosti a zobrazit seznam aplikací, které mají přiřazené. Balíčky aplikací, které jsou dostupné bez registrace, jsou k dispozici ke stažení prostřednictvím webu Portál společnosti. Aplikace, které vyžadují registraci, aby je bylo možné nainstalovat, nejsou touto změnou ovlivněny, protože když budou chtít tyto aplikace uživatelé nainstalovat, zobrazí se jim výzva k registraci.

### <a name="custom-app-categories---748805--"></a>Vlastní kategorie aplikací <!--748805-->
Teď můžete vytvářet, upravovat a přiřazovat kategorie pro aplikace, které přidáte do Intune. V současné době se kategorie dají zadávat jenom v angličtině.
Přečtěte si téma [Jak přidat aplikaci do Intune](apps-add.md).

### <a name="display-device-categories---814654--"></a>Zobrazení kategorií zařízení <!--814654-->
Kategorie zařízení teď můžete zobrazit jako sloupec v seznamu zařízení. Kategorii můžete upravit také v části vlastností v okně vlastností zařízení. Přečtěte si téma [Jak přidat aplikaci do Intune](apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Konfigurace Windows Update pro firmy nastavení <!--776716-->

Windows jako služba je nový způsob poskytování aktualizací pro Windows 10. Od verze Windows 10 budou všechny nové aktualizace funkcí a aktualizace pro zvýšení kvality zahrnovat obsah všech předchozích aktualizací. To znamená, že pokud si nainstalujete nejnovější aktualizaci, máte jistotu, že jsou vaše zařízení s Windows 10 zcela aktuální. Na rozdíl od předchozích verzí Windows je teď nutné nainstalovat celou aktualizaci (a ne jenom její část).

Pomocí služby Windows Update pro firmy můžete zjednodušit správu aktualizací, abyste nemuseli schvalovat jednotlivé aktualizace pro skupiny zařízení. Můžete nakonfigurovat strategii zavádění aktualizací, abyste měli pod kontrolou řízení rizik ve vašem prostředí, a služba Windows Update zajistí, aby se aktualizace nainstalovaly ve správný čas. Prostřednictvím Microsoft Intune můžete na zařízeních nakonfigurovat nastavení aktualizací a pozdržet instalaci aktualizací. V Intune nejsou uložené samotné aktualizace, ale jenom přiřazení zásad aktualizací. Zařízení získávají aktualizace přímo ze služby Windows Update. Pomocí Intune můžete nakonfigurovat a spravovat **aktualizační kanály Windows 10**. Aktualizační kanál obsahuje skupinu nastavení, která konfigurují, kdy a jak se budou aktualizace Windows 10 instalovat. Podrobnosti najdete v článku [Konfigurace nastavení služby Windows Update pro firmy](windows-update-for-business-configure.md).
