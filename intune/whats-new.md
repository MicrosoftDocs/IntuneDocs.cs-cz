---
title: Novinky v Microsoft Intune – Azure | Microsoft Docs
titlesuffix: ''
description: Zjistěte, jaké novinky přináší portál Intune Azure.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/08/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
/ms.custom: intune-azure
ms.openlocfilehash: 81e6dba8cabb9339c7c83a3ac95fd7cf7c0a1fa7
ms.sourcegitcommit: 698bd1488be3a269bb88c077eb8d99df6e552a9a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="whats-new-in-microsoft-intune"></a>Co je nového v Microsoft Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zjistěte, jaké novinky každý týden přináší Microsoft Intune. Můžete také získat informace o [nadcházejících změnách](#whats-coming), [důležitá oznámení](#notices) o službě a informace o [minulých verzích](whats-new-archive.md). Některé funkce můžou vycházet v průběhu několika týdnů a nemusí být k dispozici všem zákazníkům hned první týden.

> [!Note]
> Informace o nových funkcích v hybridní správě mobilních zařízení (MDM) najdete na [stránce s novinkami pro hybridní MDM](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### App management
  ### Device enrollment
  ### Device management
  ### Device configuration
  ### Intune apps
  ### Monitor and troubleshoot
  ### Role-based access control

-->   

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
Microsoft Intune bude poskytovat možnost instalace obchodních aplikací pro macOS z portálu Azure Portal. Do Intune budete moct přidat obchodní aplikaci pro masOS poté, co ji předběžně zpracoval nástroj dostupný v GitHubu. Na portálu Azure Portal v okně **Intune** zvolte **Mobilní aplikace**. V okně **Mobilní aplikace** zvolte **Aplikace** > **Přidat**. V okně **Přidat aplikaci** vyberte **Obchodní aplikace**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Předdefinované skupiny Všichni uživatelé a Všechna zařízení pro přiřazení aplikace pro Android for Work (AFW)<!-- 1813073 -->
K přiřazení aplikace AFW můžete použít integrované skupiny **Všichni uživatelé** a **Všechna zařízení**. Podrobnosti najdete v tématu [Zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune](apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Intune přeinstaluje požadované aplikace, které odinstalovali uživatelé <!-- 1947010 -->
Pokud koncový uživatel odinstaluje některou z povinných aplikací, Intune nečeká na sedmidenní cyklus vyhodnocení a během čtyřiadvaceti hodin ji automaticky znovu nainstaluje.

### <a name="device-configuration"></a>Konfigurace zařízení

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>Graf profilu zařízení a seznam stavů zobrazují všechna zařízení ve skupině <!-- 1449153 eeready -->
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

#### <a name="show-caller-id-in-personal-profile---android-for-work---1098984---"></a>Zobrazení ID volajícího v osobním profilu – Android for Work <!--1098984 -->
Při použití osobního profilu na zařízení nemusejí koncoví uživatelé vidět podrobnosti ID volajícího z pracovního kontaktu. 

Od této aktualizace je v části **Android for Work** > **Omezení zařízení** > **Nastavení pracovního profilu** k dispozici nové nastavení:
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
  - **Zabezpečené spouštění s přímým přístupem do paměti (DMA)**: Zapne VBS se zabezpečeným spouštěním a přímým přístupem k paměti. Ochrany DMA vyžadují hardwarovou podporu a povolí se jenom na správně nakonfigurovaných zařízeních. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Použití vlastního názvu subjektu u certifikátu SCEP <!-- 2064190 -->
V profilu certifikátu SCEP můžete u vlastního subjektu použít běžný název **OnPremisesSamAccountName**. Můžete například použít `CN={OnPremisesSamAccountName})`.

####  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>Blokování kamery a snímků obrazovky na Androidu for Work <!-- 1098977 eeready-->
Při konfiguraci omezení zařízení s Androidem jsou k dispozici dvě nové vlastnosti umožňující blokování: 
- Kamera: Blokování přístupu ke všem kamerám na zařízení
- Snímek obrazovky: Blokování vytváření snímků obrazovky a tím také ochrana obsahu před zobrazením na zobrazovacích zařízení, která nemají zabezpečený výstup videa

Platí pro Android for Work.


### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nové kroky registrace pro uživatele používající zařízení s macOS High Sierra 10.13.2+ <!--1734567 -->
Systém macOS high Sierra 10.13.2 představil nový koncept registrace MDM, který vyžaduje schválení uživatelem (User Approved). Schválené registrace umožňují v Intune spravovat některá citlivá nastavení zabezpečení. Další informace najdete v dokumentaci podpory Apple tady: https://support.apple.com/HT208019.

Zařízení zaregistrovaná v aplikaci Portál společnosti pro macOS se považují za neschválená uživatelem, dokud koncový uživatel neotevře předvolby systému a neschválí je ručně. Z tohoto důvodu nyní Portál společnosti pro macOS instruuje uživatele systému macOS 10.13.2 a novějšího, aby na konci procesu registrace přešli do příslušného umístění a ručně registraci schválili. Konzola správce Intune oznámí, zda je zaregistrované zařízení schváleno uživatelem.



### <a name="device-management"></a>Správa zařízení

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----eeready-1629303---"></a>Rozšířená ochrana před internetovými útoky (ATP) a Intune jsou plně integrované <!-- EEready 1629303 -->

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
Aplikace Portál společnosti Intune pro Windows 10 byla aktualizována o [navigační zobrazení systému návrhu FDS](https://docs.microsoft.com/en-us/windows/uwp/design/basics/navigation-basics). Po straně aplikace je statický svislý seznam všech hlavních stránek. Když na odkaz kliknete, stránka se rychle zobrazí nebo můžete mezi stránkami přepínat. Jde o první z řady aktualizací, které jsou výsledkem naší trvalé snahy o vytvoření přizpůsobivého, empatického a známého prostředí Intune. Pokud si chcete nový vzhled prohlédnout, přejděte na [Co je nového v uživatelském rozhraní aplikace](whats-new-app-ui.md).

## <a name="week-of-april-16-2018"></a>Týden od 16. dubna 2018

#### <a name="use-cisco-anyconnect-client-for-ios----eeready-1333708---"></a>Použití klienta Cisco AnyConnect pro iOS <!-- EEready 1333708 -->

Když vytváříte nový profil VPN pro iOS, jsou teď k dispozici dvě možnosti: **Cisco AnyConnect** a **Cisco Legacy AnyConnect**. Profily Cisco AnyConnect podporují verzi 4.0.7x a novější. Stávající profily VPN Cisco AnyConnect pro iOS jsou označené jako **Cisco Legacy AnyConnect** a budou dál fungovat s Cisco AnyConnect 4.0.5x stejně jako dnes.

> [!NOTE]
> Tato změna platí jen pro iOS. Pro platformy Android, Android for Work a macOS bude dál existovat jenom jedna možnost Cisco AnyConnect.

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

#### <a name="protect-on-premise-exchange-data-using-intune-app-and-ca----1056954---"></a>Ochrana místních dat systému Exchange pomocí zásad ochrany aplikací Intune a podmíněného přístupu <!-- 1056954 -->
Nově můžete chránit přístup k místním datům systému Exchange z Outlooku Mobile prostřednictvím zásad ochrany aplikací Intune a podmíněného přístupu. Pokud chcete na portálu Azure Portal přidat nebo upravit zásady ochrany aplikací, vyberte **Microsoft Intune** > **Mobilní aplikace** > **Zásady ochrany aplikací**. Ještě než začnete tuto funkci využívat, zkontrolujte, že splňujete [požadavky na Outlook pro iOS a Android](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx).

## <a name="week-of-march-26-2018"></a>Týden od 26. března 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Výstrahy k vypršení platnosti obchodních aplikací pro iOS v Microsoft Intune <!-- 748789 -->

Na portálu Azure Portal vás Intune upozorní na obchodní aplikace pro iOS, jejichž platnost brzy vyprší. Při nahrání nové verze obchodní aplikace pro iOS Intune oznámení o vypršení platnosti ze seznamu aplikací odebere. Toto oznámení o vypršení platnosti bude aktivní jen u nově nahraných obchodních aplikací pro iOS. 30 dní před vypršením platnosti profilu pro zřizování obchodních aplikací pro iOS se zobrazí upozornění. Potom se výstraha změní na Platnost vypršela.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Přizpůsobení motivů Portálu společnosti pomocí šestnáctkových kódů <!--1049561 -->

Pomocí šestnáctkových kódů si můžete přizpůsobit barvu motivu v aplikacích Portál společnosti. Když zadáte šestnáctkový kód, Intune určí barvu textu, která poskytuje nejvyšší úroveň kontrastu mezi barvou textu a barvou pozadí. Můžete si zobrazit náhled barvy textu a loga společnosti oproti barvě v části **Mobilní aplikace** > **Portál společnosti**.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Zahrnutí a vyloučení přiřazení aplikací na základě skupin pro Android Enterprise <!-- 1813081 -->

Android Enterprise (dříve Android for Work) umožňuje zahrnout nebo vyloučit skupiny, ale nepodporuje vytvořené integrované skupiny **Všichni uživatelé** a **Všechna zařízení**. Podrobnosti najdete v tématu [Zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune](apps-inc-exl-assignments.md).


### <a name="device-management"></a>Správa zařízení

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Vylepšení zabezpečení ve službě Intune <!-- 1637539 -->   

Do Intune v Azure jsme přidali přepínací tlačítko, pomocí kterého můžou zákazníci samostatné verze Intune zacházet se zařízením bez přiřazených zásad, jako by bylo **Vyhovující předpisům** (funkce zabezpečení vypnutá), nebo **Nevyhovující předpisům** (funkce zabezpečení zapnutá). To zajistí přístup k prostředkům až po vyhodnocení dodržování předpisů zařízením.

Dopad této funkce závisí na tom, zda už máte přiřazené zásady dodržování předpisů nebo nikoliv.

- Pokud patříte mezi nové nebo stávající účty a nemáte ke svým zařízením přiřazené žádné zásady dodržování předpisů, je tento přepínač automaticky nastaven na **Vyhovující předpisům**. V konzole bude je funkce ve výchozím nastavení vypnutá. Na koncové uživatele to nemá žádný vliv.
- Pokud patříte mezi stávající účty a máte nějaká zařízení, ke kterým jsou přiřazené zásady dodržování předpisů, je tento přepínač automaticky nastaven na **Nevyhovující předpisům**. Od zavedení březnové aktualizace je tato funkce ve výchozím nastavení zapnutá.

Pokud používáte zásady dodržování předpisů s podmíněným přístupem a tato funkce je zapnutá, jsou teď všechna zařízení bez alespoň jedné přiřazené zásady dodržování předpisů blokovaná podmíněným přístupem. Koncoví uživatelé přidružení k těmto zařízením, kteří měli předtím přístup k e-mailu, o tento přístup přijdou, dokud všem zařízením nepřiřadíte alespoň jednu zásadu dodržování předpisů.   

Mějte na paměti, že ačkoliv se výchozí stav tlačítka zobrazí v uživatelském rozhraní bezprostředně po březnových aktualizacích služby Intune, nevynutí se okamžitě. Veškeré provedené změny přepínacího tlačítka ovlivní dodržování předpisů zařízením až poté, co tlačítko na vašem účtu aktivujeme. Jakmile aktivaci dokončíme, informujeme vás prostřednictvím Centra zpráv. Po provedení březnových aktualizací to může trvat několik dní.

**Další informace**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Vylepšené zjišťování jailbreaků <!-- 846515 -->

Vylepšené zjišťování jailbreaků je novým nastavením dodržování předpisů, které zlepší způsob, jak Intune vyhodnocuje zařízení s jailbreakem. Toto nastavení způsobí, že se zařízení bude k Intune hlásit častěji. K tomu se využívají polohové služby a ovlivňuje to vybíjení baterie.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Resetování hesel pro zařízení s Androidem O <!-- 1238299 -->
U zaregistrovaných zařízení s Androidem 8.0 a pracovním profilem můžete resetovat hesla. Když do zařízení s Androidem 8.0 pošlete žádost o resetování hesla, nastaví se aktuálnímu uživateli nové heslo pro odemčení zařízení nebo výzva spravovaného profilu. Po zaslání se heslo nebo výzva okamžitě projeví.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Cílení zásad dodržování předpisů na zařízení ve skupinách zařízení <!--1307012 -->

Můžete cílit zásady dodržování předpisů na uživatele ve skupinách uživatelů. Od této aktualizace můžete cílit zásady dodržování předpisů na zařízení ve skupinách zařízení. Zařízení cílená jako součást skupiny zařízení nebudou přijímat akce při nedodržení předpisů.

#### <a name="new-management-name-column----1333586---"></a>Nový sloupec Název správy <!-- 1333586 -->
 V okně zařízení přibyl nový sloupec s názvem **Název správy**. Půjde o automaticky generovaný název bez možnosti úprav, který bude přiřazený podle zařízení na základě tohoto vzorce:
- Výchozí název pro všechna zařízení: <username><em><devicetype></em><enrollmenttimestamp>
- Pro hromadně přidaná zařízení: <PackageId/ProfileId><em><DeviceType></em><EnrollmentTime>

Je to volitelný sloupec v okně zařízení. Není k dispozici ve výchozím nastavení a přístup k němu je jen přes výběr sloupců. Na název zařízení nemá tento nový sloupec vliv.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837---"></a>Zařízením s iOSem se zobrazuje výzva k zadání PINu každých 15 minut <!--1550837 -->
Po použití zásad dodržování předpisů nebo konfigurace u zařízení s iOSem se uživatelům každých 15 minut zobrazí výzva k zadání PINu. Uživatelům se výzva zobrazuje tak dlouho, dokud PIN nenastaví.

#### <a name="schedule-your-automatic-updates---1805514---"></a>Plánování automatických aktualizací <!--1805514 -->
Pomocí [nastavení aktualizačního okruhu Windows](windows-update-for-business-configure.md) máte v Intune možnost řídit instalaci automatických aktualizací. Od této aktualizace můžete naplánovat opakované aktualizace na základě týdne, dne a času.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763---"></a>Použití plně rozlišujícího názvu jako subjektu certifikátu SCEP <!--2221763 -->
Při vytváření profilu certifikátu SCEP zadáváte název subjektu. Od této aktualizace můžete jako subjekt použít plně rozlišující název. Jako **Název subjektu** vyberte **Vlastní** a pak zadejte `CN={{OnPrem_Distinguished_Name}}`. Pokud chcete použít proměnnou `{{OnPrem_Distinguished_Name}}`, nezapomeňte synchronizovat atribut uživatele `onpremisesdistingishedname` pomocí služby [Azure Active Directory (AD) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) se službou Azure AD.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983---"></a>Povolení sdílení kontaktů přes Bluetooth – Android for Work <!--1098983 -->
Ve výchozím nastavení Android brání v synchronizaci kontaktů v pracovním profilu se zařízeními Bluetooth. V důsledku toho se kontakty pracovního profilu nezobrazují na ID volajícího u zařízení Bluetooth.

Od této aktualizace je v části **Android for Work** > **Omezení zařízení** > **Nastavení pracovního profilu** k dispozici nové nastavení:
- Sdílení kontaktů přes Bluetooth

Správce Intune může toto nastavení nakonfigurovat a povolit sdílení. Toto nastavení je užitečné při párování zařízení se zařízením Bluetooth do auta, které zobrazuje ID volajícího při použití hands-free. Pokud je nastavení povoleno, kontakty pracovního profilu se zobrazí. Pokud není nastavení povoleno, kontakty pracovního profilu se nezobrazí.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459---"></a>Konfigurace Gatekeepera ke kontrole nad zdrojem stahování aplikací pro macOS <!-- 1690459 -->

Můžete konfigurovat Gatekeepera, aby vaše zařízení chránil před aplikacemi díky kontrole nad tím, odkud je možné aplikace stahovat. Nakonfigurovat můžete tyto zdroje stahování: **Mac App Store**, **Mac App Store a identifikovaní vývojáři** nebo **Kdekoliv**. Kromě toho je možné nakonfigurovat, jestli uživatelé smí nainstalovat aplikaci kliknutím se stisknutou klávesou Control, které tuto kontrolu Gatekeepera přepíše.

Tato nastavení najdete v části **Konfigurace zařízení** -> **Vytvořit profil** -> **macOS** -> **Ochrana koncového bodu**.

#### <a name="configure-the-mac-application-firewall----1690461---"></a>Konfigurace brány firewall pro aplikace pro Mac <!-- 1690461 -->

Je možné nakonfigurovat bránu firewall pro aplikace pro Mac. Můžete to využít k řízení připojení na základě jednotlivých aplikací místo na základě portů. Díky tomu snadněji využijete výhod ochrany pomocí brány firewall a pomůže vám to zabránit nežádoucím aplikacím v převzetí kontroly nad síťovými porty otevřenými pro oprávněné aplikace.

Tuto funkci najdete v části **Konfigurace zařízení** -> **Vytvořit profil** -> **macOS** -> **Ochrana koncového bodu**.

Jakmile nastavení brány firewall povolíte, můžete ji nakonfigurovat pomocí dvou strategií:

- Blokovat všechna příchozí připojení

   Můžete blokovat všechna příchozí připojení u cílových zařízení. Pokud se k tomu rozhodnete, zablokují se příchozí připojení u všech aplikací.

- Povolit nebo blokovat konkrétní aplikace

   Můžete povolit nebo blokovat příjem příchozích připojení u konkrétních aplikací. Můžete také povolit neviditelný režim, který zabrání odpovědím na zjišťovací požadavky.

####  <a name="detailed-error-codes-and-messages----1376342---"></a>Podrobné kódy chyb a chybové zprávy <!-- 1376342 -->

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
V Intune máte možnost řídit [správu aktualizací softwaru]](windows-update-for-business-configure.md). Od této aktualizace je k dispozici vlastnost <strong>Kontroly při restartu</strong>, která je ve výchozím nastavení povolená. Pokud chcete přeskočit typické kontroly, které se provádí při restartu zařízení (například aktivní uživatelé, stav baterie a další), vyberte <strong>Přeskočit</strong>.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Nové kanály Windows 10 Insider Preview pro kanály nasazení <!-- 1746293 -->
Nově můžete při vytváření aktualizačního kanálu nasazení Windows 10 vybrat tyto kanály pro údržbu Windows 10 Insider Preview:
- Sestavení Windows Insider – Fast
- Sestavení Windows Insider – Slow
- Sestavení Windows Insider – Release 

Podrobnosti o těchto kanálech najdete v tématu [Správa sestavení Insider Preview](https://insider.windows.com/en-us/for-business-organization-admin/).   
Informace o vytváření kanálů nasazení v Intune najdete v tématu [Správa softwarových aktualizací v Intune](windows-update-for-business-configure.md).

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="company-portal-enrollment-improved----1874230-eeready--"></a>Vylepšená registrace pomocí Portálu společnosti <!-- 1874230 eeready-->
Uživatelé, kteří registrují zařízení pomocí Portálu společnosti ve Windows 10 sestavení 1703 a vyšším, teď můžou dokončit první krok registrace bez opuštění aplikace.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868---"></a>V seznamech zařízení <!--1725868 --> se teď zobrazují HoloLens a Surface Hub
Do aplikace Portál společnosti pro Android jsme přidali podporu zobrazení zařízení HoloLens a Surface Hub zaregistrovaných v Intune.

#### <a name="custom-book-categories-for-volume-purchase-progream-vpp-ebooks----1488911---"></a>Vlastní kategorie e-knih v rámci programu VPP (volume-purchase program) <!-- 1488911 -->
Můžete vytvářet vlastní kategorie e-knih a pak k nim přiřadit e-knihy v rámci programu VPP. Koncoví uživatelé pak uvidí nově vytvořené kategorie e-knih a knihy k nim přiřazené. Podrobnosti najdete v tématu [Správa aplikací a knih zakoupených v rámci multilicenčního programu pomocí Microsoft Intune](vpp-apps.md).  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option----2070166---"></a>Změny v podpoře pro možnost odeslání názoru v aplikaci Portál společnosti pro Windows <!-- 2070166 -->
Od 30. dubna 2018 bude možnost **Váš názor** v aplikaci Portál společnosti pro Windows fungovat pouze u zařízení se systémem Windows 10 Anniversary Update (1607) a novějším. Možnost odeslání názoru se už nebude podporovat při použití aplikace Portál společnosti pro Windows se systémem:  
- Windows 10, verze 1507  
- Windows 10, verze 1511  
- Windows Phone 8.1 

Pokud vaše zařízení používá Windows 10 RS1 nebo novější, stáhněte si nejnovější verzi aplikace Portál společnosti pro Windows ze Storu. Pokud používáte nepodporovanou verzi, odesílejte své názory prostřednictvím následujících kanálů: 
- Aplikace Centrum Feedback ve Windows 10
- E-mail WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nové nastavení Ochrany Application Guard v programu Windows Defender <!-- 1631890 -->

- **Enable graphics acceleration (Povolit akceleraci grafiky)**: Správci můžou pro Ochranu Application Guard v programu Windows Defender povolit virtuální grafický procesor. Toto nastavení umožní procesoru přesunout vykreslování grafiky na virtuální grafický procesor. Může zlepšit výkon při práci s graficky náročnými weby nebo při sledování videa v kontejneru.

- **SaveFilestoHost**: Správci můžou povolit předávání souborů z Microsoft Edge, který běží v kontejneru, do hostitelského souborového systému. Zapnutím tohoto nastavení umožníte uživatelům stahovat soubory z Microsoft Edge v kontejneru do hostitelského souborového systému.

#### <a name="mam-protection-policies-targeted-based-on-management-state----1665993---"></a>Cílení na zásady ochrany MAM na základě stavu správy <!-- 1665993 -->
Můžete cílit na zásady MAM na základě stavu správy zařízení:
- **Zařízení s Androidem**: Je možné cílit na nespravovaná zařízení, zařízení spravovaná v Intune a Android Enterprise Profiles spravované v Intune (dříve Android for Work).
- **Zařízení s iOS**: Je možné cílit na nespravovaná zařízení (jen MAM) nebo zařízení spravovaná v Intune.

    > [!NOTE]
    > - Podporu této funkce pro iOS budeme zavádět v průběhu dubna 2018.

Podrobnosti najdete v tématu [Cílení zásad ochrany aplikací na základě stavu správy zařízení](app-protection-policies.md).

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Vylepšení jazyka v aplikaci Portál společnosti pro Windows <!-- 1683758 -->
Vylepšili jsme jazyk v aplikaci Portál společnosti pro Windows 10 tak, aby byl uživatelsky přívětivější a lépe přizpůsobený vaší firmě. Obrázky s ukázkami změn najdete v tématu [Co je nového v uživatelském rozhraní aplikací](whats-new-app-ui.md).

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Nové dokumenty týkající se ochrany osobních údajů uživatelů <!-- 1440709 -->
V rámci naší snahy poskytnout koncovým uživatelům větší kontrolu nad jejich daty a ochranou osobních údajů jsme zaktualizovali naše dokumenty, v nichž vysvětlujeme, jak zobrazit a odebrat data lokálně uložená aplikacemi Portál společnosti. Tyto novinky najdete zde:

- **Android**: [Odebrání zařízení s Androidem z Intune](/intune-user-help/unenroll-your-device-from-intune-android.md)
- **Android, pokud uživatel odmítnul Podmínky použití**: [Odebrání správy zařízení, pokud jste odmítli Podmínky použití](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android.md)
- **iOS**: [Odebrání zařízení s iOSem z Intune](/intune-user-help/unenroll-your-device-from-intune-ios.md)
- **Windows**: [Odebrání zařízení s Windows z Intune](/intune-user-help/unenroll-your-device-from-intune-windows.md)

## <a name="week-of-march-19-2018"></a>Týden od 19. března 2018

### <a name="export-all-devices-into-csv-files-in-ie-edge-or-chrome----2258071---"></a>Export všech zařízení do souborů CSV v Internet Exploreru, Edge a Chromu <!-- 2258071 -->
V části **Zařízení** > **Všechna zařízení** můžete **exportovat** zařízení do seznamu ve formátu CSV. Uživatelé Internet Exploreru s více než 10 000 zařízeními můžou zařízení úspěšně vyexportovat do více souborů. Každý z nich může obsahovat až 10 000 zařízení.

Uživatelé prohlížečů Edge a Chrome s více než 30 000 zařízeními můžou zařízení úspěšně vyexportovat do více souborů. Každý z nich může obsahovat až 30 000 zařízení.

V tématu [Správa zařízení](device-management.md) se dozvíte podrobnosti o tom, co můžete se spravovanými zařízeními dělat.

## <a name="week-of-march-12-2018"></a>Týden od 12. března 2018

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Webové stránky Azure Active Directory můžou vyžadovat aplikaci Intune Managed Browser a podporovat jednotné přihlašování pro Managed Browser (Public Preview) <!-- 710595 -->

Pomocí Azure Active Directory (Azure AD) můžete přístup k webovým stránkám na mobilních zařízeních omezit na aplikaci Intune Managed Browser. V Managed Browseru zůstanou data webových stránek zabezpečená a oddělená od osobních dat koncových uživatelů. Kromě toho bude Managed Browser podporovat možnosti jednotného přihlašování pro weby chráněné pomocí Azure AD. Přihlášení k Managed Browseru nebo jeho používání na zařízení s jinou aplikací, kterou spravuje Intune, umožňuje, aby měl Managed Browser přístup k podnikovým webům chráněným pomocí Azure AD, aniž by uživatel musel zadávat své přihlašovací údaje. Tato funkce se vztahuje na weby jako Outlook Web Access (OWA) a SharePoint Online i na jiné podnikové weby jako prostředky v intranetu, ke kterým se přistupuje prostřednictvím proxy aplikace Azure. Další informace najdete v článku o [ovládacích prvcích přístupu u podmíněného přístupu Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Vizuální aktualizace aplikace Portál společnosti pro Android <!--976944 -->

Aktualizovali jsme aplikaci Portál společnosti pro Android v souladu s pokyny pro [Material Design](https://material.io/) Androidu. Obrázky nových ikon najdete v [novinkách v uživatelském rozhraní aplikací](whats-new-app-ui.md).

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Nové nastavení Ochrany Exploit Guard v programu Windows Defender <!-- 1631893 -->

Nově je k dispozici šest nových nastavení <strong>Omezení možností útoku</strong> a rozšířené možnosti <strong>Řízený přístup ke složkám: Ochrana složek</strong>. Tato nastavení najdete tady: Konfigurace zařízení\Profily\
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

Umožňuje chránit soubory a složky před neautorizovanými změnami od neznámých aplikací.<br><br>**Povolit**: Brání nedůvěryhodným aplikacím ve změnách nebo odstranění souborů v chráněných složkách a v zápisu do sektorů disku.<br><br>
**Block disk modification only** (Blokovat jenom změny disku):<br>Umožňuje zablokovat nedůvěryhodným aplikacím možnost zapisovat do sektorů disku. Nedůvěryhodné aplikace stále můžou změnit nebo odstranit soubory v chráněných složkách.|

## <a name="week-of-february-19-2018"></a>Týden od 19. února 2018

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Podpora Intune pro více účtů Apple DEP nebo Apple School Manager <!-- 747685 -->

Intune teď podporuje registraci zařízení z až 100 různých účtů [Apple Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) nebo [Apple School Manager](apple-school-manager-set-up-ios.md). Pro každý nahraný token lze profily registrace a zařízení spravovat samostatně. K jednotlivým nahraným tokenům DEP nebo School Manager lze automaticky přiřadit různé profily registrace. Pokud je nahraných více tokenů School Manager, může se v každém okamžiku sdílet pomocí služby Microsoft School Data Sync jenom jeden.

Po dokončení migrace už nebudou fungovat beta verze rozhraní Graph API a publikované skripty pro správu Apple DEP nebo ASM přes rozhraní Graph. Nové beta verze rozhraní Graph API jsou ve vývoji a budou se vydávat po dokončení migrace.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Nastavení omezení registrace na uživatele <!-- 1634444 eeready wnready -->
V okně **Řešení potíží** teď můžete zobrazit platná [omezení registrace](enrollment-restrictions-set.md) pro jednotlivé uživatele tak, že v seznamu **Přiřazení** vyberete **Omezení registrace**.

### <a name="device-management"></a>Správa zařízení
#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Sestavy stavu hrozby a stavu programu Windows Defender <!--854704 -->

Klíčem ke správě počítačů s Windows je pochopení stavu programu Windows Defender.  Touto aktualizací Intune přidá do stavu agenta Windows Defender nové sestavy a akce. Pomocí souhrnné sestavy stavu v [úloze dodržování předpisů zařízením](compliance-policy-monitor.md) zjistíte, která zařízení vyžadují:
- aktualizaci signatur,
- Restartovat
- ruční zásah,
- úplnou kontrolu,
- stavy ostatních agentů vyžadujících zásah.

Podrobná sestava pro jednotlivé kategorie stavu uvádí jednotlivé počítače, které vyžadují pozornost, nebo ty, které jsou **čisté**.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Nové nastavení ochrany osobních údajů pro omezení zařízení <!--1308926 -->
Pro zařízení jsou k dispozici [dvě nová nastavení ochrany osobních údajů](device-restrictions-windows-10.md#privacy):
- **Publikovat aktivity uživatele**: Tuto možnost nastavte na **Blokovat**, pokud chcete zabránit ve sdílení a zjišťování naposledy použitých prostředků při přepínání úloh.
- **Jen místní aktivity**: Tuto možnost nastavte na **Blokovat**, pokud chcete zabránit ve sdílení a zjišťování naposledy použitých prostředků při přepínání úloh jen u místní aktivity.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Nové nastavení prohlížeče Microsoft Edge <!--1469166 -->
Pro zařízení s prohlížečem Edge jsou teď k dispozici [dvě nová nastavení](device-restrictions-windows-10.md#edge-browser): **Path to favorites file** (Cesta k souboru oblíbených položek) a **Changes to Favorites** (Změny oblíbených položek).

### <a name="app-management"></a>Správa aplikací
#### <a name="protocol-exceptions-for-applications---1035509---"></a>Výjimky protokolu pro aplikace <!--1035509 -->

Můžete teď vytvořit výjimky ze zásady přenosu dat ve správě mobilních dat Intune, abyste mohli otevřít konkrétní nespravované aplikace. Tyto aplikace musí být pro IT důvěryhodné. Pokud zásady přenosu dat nastavíte **jenom na spravované aplikace**, bude kromě vytvořených výjimek přenos dat i nadále omezený jen na aplikace, které se spravují přes Intune. Tato omezení můžete vytvořit pomocí protokolů (iOS) nebo balíčků (Android).

Do zásad přenosu aplikací MAM můžete například přidat jako výjimku balíček Webex. To umožní, aby se odkazy Webex ve spravované outlookové e-mailové zprávě otevíraly přímo v aplikaci Webex. V ostatních nespravovaných aplikacích bude přenos dat i nadále omezen. Další informace najdete v tématu [Výjimky zásad přenosu dat pro aplikace](app-protection-policies-exception.md).

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Šifrovaná data Windows Information Protection (WIP) ve výsledcích hledání ve Windows <!-- 1469193 -->
Nastavení v zásadách Windows Information Protection (WIP) vám teď umožňuje řídit, jestli se mají do výsledků hledání ve Windows zahrnovat šifrovaná data WIP. Tuto možnost zásad ochrany aplikací nastavíte tak, že v zásadách Windows Information Protection v části **Upřesnit nastavení** vyberete **Povolit Windows Search Indexeru prohledávat šifrované položky**. Zásady ochrany aplikací musí být nastavené pro platformu *Windows 10* a možnost **Stav registrace** musí být nastavená na hodnotu **S registrací**. Další informace najdete v části týkající se možnosti [Povolit Windows Search Indexeru prohledávat šifrované položky](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Konfigurace automaticky aktualizovaných mobilních aplikací MSI <!-- 1740840 -->
Známou automaticky aktualizovanou mobilní aplikaci MSI můžete nakonfigurovat tak, aby ignorovala proces kontroly verzí. Tato možnost je užitečná, když chcete předejít konfliktu časování. K tomuto typu konfliktu časování může například dojít, když aplikaci automaticky aktualizuje vývojář a současně Intune. Jak vývojář, tak Intune můžou vynucovat verzi aplikace na klientovi Windows, což může způsobit konflikt. Pro tyto automaticky aktualizované aplikace MSI můžete v okně **Informace o aplikaci** nakonfigurovat nastavení **Ignorovat verzi aplikace**. Po přepnutí tohoto nastavení na **Ano** bude Microsoft Intune ignorovat verzi aplikace, která je nainstalovaná na klientovi Windows.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Podpora souvisejících sad licencí aplikací v Intune <!-- 1864117 -->
Intune na portálu Azure Portal teď podporuje související sady licencí aplikací jako jedinou položku aplikace v uživatelském rozhraní. Kromě toho všechny aplikace licencované offline a synchronizované z Microsoft Storu pro firmy se sloučí do jediné položky aplikace a všechny podrobnosti nasazení z jednotlivých balíčků se budou migrovat do jediné položky. Pokud se chcete podívat na související sady licencí aplikací na portálu Azure Portal, vyberte **Licence aplikací** v okně **Mobilní aplikace**.

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

Umožňuje chránit soubory a složky před neautorizovanými změnami od neznámých aplikací.<br><br>**Povolit**: Brání nedůvěryhodným aplikacím ve změnách nebo odstranění souborů v chráněných složkách a v zápisu do sektorů disku.<br><br>
**Block disk modification only** (Blokovat jenom změny disku):<br>Umožňuje zablokovat nedůvěryhodným aplikacím možnost zapisovat do sektorů disku. Nedůvěryhodné aplikace stále můžou změnit nebo odstranit soubory v chráněných složkách.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Další nastavení zabezpečení systému pro zásady dodržování předpisů pro Windows 10 a novější <!--1704133-->

Teď jsou dostupná další nastavení dodržování předpisů pro Windows 10, včetně vyžadování brány firewall a Antivirové ochrany v programu Windows Defender.


### <a name="role-based-access-control"></a>Řízení přístupu na základě role
### <a name="intune-apps"></a>Aplikace Intune
#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>Podpora pro offline aplikace z Microsoft Storu pro firmy <!--1222672-->
Aplikace Offline zakoupené v Microsoft Storu pro firmy se teď synchronizují na portálu Azure Portal. Tyto aplikace můžete nasadit pro skupiny zařízení nebo skupiny uživatelů. Offline aplikace instaluje Intune, nikoli Store.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Znemožněte koncovým uživatelům ruční přidávání nebo odebírání účtů v pracovním profilu <!-- 1728700 -->

Když nasadíte aplikaci Gmail do profilu Android for Work, můžete teď zabránit tomu, aby koncoví uživatelé ručně přidávali nebo odebírali účty v pracovním profilu s použitím nastavení **Přidat nebo odebrat účty** v profilu omezení pro zařízení s Androidem for Work.

## <a name="week-of-february-5-2018"></a>Týden od 5. února 2018

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Nová možnost ověřování uživatelů při hromadné registraci Apple <!-- 747625 eeready -->

> [!NOTE]
> U nových tenantů se projeví okamžitě. U stávajících tenantů bude tato funkce zavedena v průběhu dubna. Až do zavedení nemusíte mít k těmto novým funkcím přístup.

Intune teď nabízí možnost ověřovat zařízení pomocí aplikace Portál společnosti u těchto metod registrace:

- Program Apple Device Enrollment Program
- Apple School Manager
- Registrace Apple Configuratoru

Při použití možnosti Portálu společnosti lze vynutit vícefaktorové ověřování Azure Active Directory bez blokování těchto metod registrace.

Při použití možnosti Portálu společnosti pro registraci přidružení uživatelů přeskočí Intune ověřování uživatelů v Pomocníkovi s nastavením iOSu. To znamená, že zařízení se napřed zaregistruje jako zařízení bez uživatelů a neobdrží tedy konfigurace ani zásady pro skupiny uživatelů. Obdrží jenom konfigurace a zásady pro skupiny zařízení. Intune ale na toto zařízení automaticky nainstaluje aplikaci Portál společnosti. První uživatel, který aplikaci Portál společnosti spustí a přihlásí se do ní, se v Intune přidruží k tomuto zařízení. V tomto okamžiku pak obdrží konfigurace a zásady dané skupiny uživatelů. Přidružení uživatelů není možné změnit bez opětovné registrace.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Podpora Intune pro více účtů Apple DEP nebo Apple School Manager <!-- 747685 eeready -->

Intune teď podporuje registraci zařízení z až 100 různých účtů Apple DEP (Device Enrollment Program) nebo Apple School Manager. Pro každý nahraný token lze profily registrace a zařízení spravovat samostatně. K jednotlivým nahraným tokenům DEP nebo School Manager lze automaticky přiřadit různé profily registrace. Pokud je nahraných více tokenů School Manager, může se v každém okamžiku sdílet pomocí služby Microsoft School Data Sync jenom jeden.

Po dokončení migrace už nebudou fungovat beta verze rozhraní Graph API a publikované skripty pro správu Apple DEP nebo ASM přes rozhraní Graph. Nové beta verze rozhraní Graph API jsou ve vývoji a budou se vydávat po dokončení migrace.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Vzdálený tisk přes zabezpečenou síť <!-- 1709994  -->
Řešení PrinterOn pro bezdrátový mobilní tisk umožní uživatelům vzdáleně tisknout odkudkoli a kdykoli přes zabezpečenou síť. PrinterOn se integruje s Intune App SDK pro iOS i Android. Zásady ochrany aplikací budete moct cílit na tuto aplikaci pomocí okna **Zásady ochrany aplikací** v Intune v konzole pro správu. Koncoví uživatelé si budou moct stáhnout aplikaci PrinterOn for Microsoft prostřednictvím Obchodu Play nebo iTunes a pak ji používat ve svém ekosystému Intune.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Podpora registrací přes Správce registrace zařízení na Portálu společnosti v macOS <!-- 1352411 -->

Uživatelé teď můžou používat Správce registrace zařízení při registraci na Portálu společnosti v macOS.

## <a name="week-of-january-29-2018"></a>Týden od 29. ledna 2018

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Upozornění na tokeny, jejichž platnost vypršela nebo brzy vyprší <!-- 1639263 -->
Na stránce s přehledem se nyní zobrazují upozornění na tokeny, jejichž platnost vypršela nebo brzy vyprší. Když kliknete na upozornění pro jeden token, přejdete na stránku s podrobnostmi o daném tokenu.  Když kliknete na upozornění s více tokeny, přejdete na seznam všech tokenů s jejich stavem. Správci by měli tokeny obnovovat před datem vypršení jejich platnosti.

### <a name="device-management"></a>Správa zařízení

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>Podpora příkazu pro vzdálené vymazání v zařízeních s macOS <!-- 1438084 -->

Správci můžou vydat příkaz pro vzdálené vymazání zařízení s macOS.

> [!IMPORTANT]
> Příkaz pro vymazání se nedá vrátit zpět, a proto by se měl používat s rozvahou.

Příkaz pro vymazání odebere ze zařízení všechna data včetně operačního systému. Zároveň se tím dané zařízení odebere ze správy v Intune. Uživateli se nezobrazí žádné upozornění a mazání začne okamžitě po spuštění příkazu.

Je nutné nakonfigurovat 6místný PIN kód pro obnovení. Tento PIN kód lze použít k odemknutí vymazaného zařízení, po kterém se zahájí opětovná instalace operačního systému. Když mazání začne, zobrazí se PIN kód ve stavovém řádku v okně přehledu daného zařízení v Intune. PIN kód zůstane zobrazený, dokud probíhá mazání. Po dokončení mazání zařízení úplně zmizí ze správy Intune. Nezapomeňte si PIN kód pro obnovení poznamenat, aby se dal v případě potřeby použít k obnovení zařízení.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Odvolání licencí pro token Volume Purchase Program pro iOS <!-- 820870 -->
Pro daný token VPP můžete odvolat licenci všech aplikací pro iOS koupených přes Volume Purchase Program (VPP).

### <a name="app-management"></a>Správa aplikací

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Odvolání aplikací pro iOS koupených přes Volume Purchase Program <!-- 820863 -->
Pro dané zařízení, které má jednu nebo více aplikací pro iOS koupených přes Volume Purchase Program (VPP), můžete odvolat licenci aplikace přidruženou na základě zařízení. Odvoláním licence aplikace se příslušná aplikace VPP neodinstaluje ze zařízení. Pokud chcete odinstalovat aplikaci VPP, musíte nastavit akci přiřazení na **Odinstalovat**. Další informace najdete v tématu [Správa aplikací pro systém iOS nakoupených prostřednictvím programu hromadného nákupu pomocí Microsoft Intune](vpp-apps-ios.md).

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Přiřazení mobilních aplikací Office 365 k zařízením s iOSem a Androidem pomocí integrovaného typu aplikace <!-- 1332318 -->
**Integrovaný** typ aplikace usnadňuje vytvoření aplikací Office 365 a jejich přiřazení k zařízením s iOSem a Androidem, která spravujete. Mezi tyto aplikace O365 se řadí například Word, Excel, PowerPoint a OneDrive. K typu aplikace můžete přiřadit konkrétní aplikace a pak upravit konfiguraci informací o aplikaci.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Zahrnutí a vyloučení přiřazení aplikací na základě skupin <!-- 1406920 -->

Během přiřazování aplikací a po výběru typu přiřazení můžete vybrat skupiny, které se mají zahrnout, a také skupiny, které se mají vyloučit.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>Zásady konfigurace aplikace je možné přiřadit skupinám na základě zahrnutí a vyloučení přiřazení <!-- 1480316 -->.

Zásady konfigurace aplikace můžete přiřadit skupině uživatelů a zařízení s použitím kombinace zahrnutí a vyloučení přiřazení. Je možné zvolit přiřazení ve formě vlastního výběru skupin nebo virtuální skupiny. Virtuální skupina může zahrnovat možnosti **Všichni uživatelé**, **Všechna zařízení** nebo **Všichni uživatelé a všechna zařízení**.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Podpora zásad upgradu edice Windows 10 <!-- 903672(archived), 1119689 -->  
Můžete vytvořit zásady upgradu edice Windows 10, které zařízení s Windows 10 upgradují na Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education a Windows 10 Professional Education N. Podrobnosti o upgradech edicí Windows 10 najdete v článku [Jak nakonfigurovat upgrady edicí Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Zásady podmíněného přístupu pro Intune budou dostupné jenom z portálu Azure Portal <!-- 1737088 1634311 -->

Od této verze je možné zásady podmíněného přístupu konfigurovat a spravovat jenom na portálu [Azure Portal](https://portal.azure.com) v části **Azure Active Directory** > **Podmíněný přístup**. Na toto okno se také pohodlně dostanete z Intune na portálu Azure Portal přes **Intune** > **Podmíněný přístup**.

#### <a name="updates-to-compliance-emails---1637547---"></a>Aktualizace e-mailů týkajících se dodržování předpisů <!--1637547 -->

E-mail, ve kterém se odesílá hlášení o zařízení nesplňujícím požadavky, obsahuje podrobnosti o tomto zařízení.


## <a name="week-of-january-22-2018"></a>Týden od 22. ledna 2018

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Nová funkce pro akci Vyřešit pro zařízení s Androidem <!--1583480-->

Aplikace Portál společnosti pro Android rozšiřuje akci Vyřešit pro možnost **Aktualizovat nastavení zařízení** tak, aby bylo možné řešit [problémy se šifrováním zařízení](/intune-user-help/encrypt-your-device-android).

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Vzdálené uzamčení k dispozici v aplikaci Portál společnosti pro Windows 10 <!--676506-->
Koncoví uživatelé teď můžou vzdáleně uzamknout svoje zařízení z aplikace Portál společnosti pro Windows 10. To se nezobrazí pro místní zařízení, které aktivně používají.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Snadnější řešení problémů s dodržováním předpisů v aplikaci Portál společnosti pro Windows 10 <!--676546-->
Koncoví uživatelé, kteří používají zařízení s Windows, budou moct v aplikaci Portál společnosti klepnout na důvod nedodržení předpisů. Pokud to bude možné, přejdou tímto klepnutím přímo do správného umístění v aplikaci Nastavení, aby mohli problém vyřešit.

## <a name="week-of-december-11-2017"></a>Týden od 11. prosince 2017

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Nové nastavení automatického opětovného nasazení <!-- 1469168 -->
Nastavení **Automatické opětovné nasazení** umožňuje uživatelům s právy správce odstranit všechna uživatelská data a nastavení pomocí klávesové zkratky **CTRL+Win+R** na zamykací obrazovce zařízení. Zařízení se automaticky překonfiguruje a znovu zaregistruje ke správě. Toto nastavení najdete v části Windows 10 > Omezení zařízení > Obecné > Automatické opětovné nasazení. Podrobnosti popisuje článek [Nastavení omezení pro zařízení s Windows 10 v Intune](device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Podpora dalších zdrojových edic v zásadách upgradu edice Windows 10 <!-- 903672,  1119689 -->
Zásady upgradu edice Windows 10 teď můžete použít k upgradu z dalších edic Windows 10 (Windows 10 Pro, Windows 10 Pro Education, Windows 10 Cloud atd.). Před touto verzí bylo podporováno méně cest upgradu. Podrobné informace najdete v článku o [konfiguraci upgradů edice Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Nové nastavení v profilu konfigurace zařízení v aplikaci Centrum zabezpečení v programu Windows Defender (WDSC) <!-- 1335507 -->

Intune přidá nový oddíl nastavení profilu konfigurace zařízení v části Endpoint Protection s názvem **Centrum zabezpečení v programu Windows Defender**. Správci IT mohou nakonfigurovat, ke kterým pilířům aplikace Centrum zabezpečení v programu Windows Defender mají mít koncoví uživatelé přístup. Pokud správce IT skryje pilíř v aplikaci Centrum zabezpečení v programu Windows Defender, nezobrazují se v zařízení uživatele žádná oznámení související s skrytým pilířem.

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

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Použití proměnné AAD_DEVICE_ID v názvu subjektu <!-- 1468599 -->

Když v Intune vytvoříte profil certifikátu SCEP, můžete k vytvoření vlastního názvu subjektu použít proměnnou AAD_DEVICE_ID.   Pokud k vyžádání certifikátu použijete tento profil SCEP, nahradí se proměnná identifikátorem zařízení AAD, které požádalo o certifikát.


### <a name="device-management"></a>Správa zařízení

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Správa zařízení macOS zaregistrovaných v Jamf s modulem dodržování předpisů zařízení Intune <!-- 1592747 -->
K odeslání informací o stavu zařízení s macOS do Intune teď můžete použít i řešení Jamf, které je vyhodnotí na základě zásad dodržování předpisů definovaných v konzole Intune. Podle stavu dodržování předpisů zařízení a také dalších podmínek (třeba umístění, uživatelského rizika atd.) bude podmíněný přístup vynucovat dodržování předpisů pro zařízení macOS, které mají přístup ke cloudovým a místním aplikacím propojených s Azure AD, včetně Office 365. Další informace o [nastavení integrace řešení Jamf](conditional-access-integrate-jamf.md) a [dodržování předpisů u zařízení spravovaných v řešení Jamf](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Nová akce pro zařízení s iOSem  <!-- 1424701 -->

Kontrolovaná zařízení s iOSem 10.3 teď můžete vypnout. Tato akce vypne zařízení okamžitě, bez upozornění pro koncového uživatele. Akci **Vypnout (jen pod dohledem)** najdete ve vlastnostech zařízení, když zařízení vyberete v úloze **Zařízení**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Zakázání změn data/času u zařízení se zabezpečením Samsung Knox <!-- 1468103 -->

Přidali jsme novou funkci, která v zařízeních se zabezpečením Samsung Knox umožňuje zablokovat změnu změny data a času. Najdete je zde: **Profily konfigurace zařízení** > **Omezení zařízení (Android)** > **Obecné**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Podpora účtu zdroje pro Surface Hub <!-- 1566442  -->

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

   - **E-mail**

     E-mailová adresu účtu zdroje nebo zařízení.

   - **Server Exchange**

     Je potřeba, pouze pokud se nezdaří automatické zjišťování.

   - **Synchronizace kalendáře**

     Určuje, zda je povolená synchronizace kalendáře a dalších služeb serveru Exchange. Například: synchronizace schůzek.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Instalace aplikací Office na zařízeních macOS <!-- 1494311 -->
Teď můžete na zařízení macOS instalovat aplikace Office. Tento nový typ aplikace vám umožní nainstalovat Word, Excel, PowerPoint, Outlook a OneNote. Tyto aplikace jsou také dodávané prostřednictvím funkce Microsoft AutoUpdate (MAU). Je to kvůli jejich zabezpečení a aktuálnosti.

### <a name="app-management"></a>Správa aplikací

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Odstranění tokenu Volume Purchase Program pro iOS <!-- 820879 -->
K odstranění tokenu programu Volume Purchasing Program (VPP) pro iOS můžete použít konzolu. To může být nutné v případě, že máte duplicitní instance tokenu VPP.

### <a name="intune-apps"></a>Aplikace Intune


### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Nová kolekce entit z názvem Aktuální uživatel se omezuje na data aktuálně aktivních uživatelů <!-- 1667026 -->

Kolekce entit **Uživatelé** obsahuje všechny uživatele Azure Active Directory (Azure AD), kteří mají v podniku přiřazené licence. Uživatel například může být přidaný do Intune a potom v průběhu posledního měsíce dojde k jeho odebrání. Přestože tento uživatel není v době vytvoření sestavy přítomen, existují data o uživateli a stavu. Můžete vytvořit sestavu, která ukazuje trvání historické přítomnosti uživatele ve vašich datech.

Naproti tomu nová kolekce entit **Aktuální uživatel** obsahuje pouze uživatele, kteří nebyli odebráni. Kolekce entit **Aktuální uživatel** obsahuje pouze aktuálně aktivní uživatele. Informace o kolekci entit **Aktuální uživatel** najdete v části [Referenční informace o entitě aktuálního uživatele](reports-ref-current-user.md).


### <a name="updated-graph-apis----1736360---"></a>Aktualizované rozhraní API služby Graph <!-- 1736360 -->

V této verzi jsme aktualizovali několik rozhraní API služby Graph pro Intune. V této chvíli se jedná o beta verze. Další informace najdete v měsíčním [protokolu změn rozhraní API služby Graph](https://developer.microsoft.com/graph/docs/concepts/changelog).

## <a name="week-of-december-4-2017"></a>Týden od 4. prosince 2017

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Intune podporuje aplikace zakázané prostřednictvím Windows Information Protection (WIP)<!-- 1479103 -->
V Intune můžete zadat odepřené aplikace. Pokud je aplikace zakázaná, má zablokovaný přístup k podnikovým informacím. Je to v podstatě opak seznamu povolených aplikací. Další informace najdete v [doporučeném seznamu aplikací se zákazem pro Windows Information Protection](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).


## <a name="week-of-november-27-2017"></a>Týden od 27. listopadu 2017

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="troubleshoot-enrollment-issues-----746324---"></a>Řešení potíží s registrací  <!-- 746324 -->

Pracovní prostor **Řešení potíží** teď zobrazuje problémy s registrací uživatelů. Podrobnosti o problému a navrhované nápravné kroky můžou správcům a pracovníkům technické podpory pomoct problém vyřešit. Některé problémy s registrací nejsou zaznamenané a k některým chybám nemusí návrhy k odstranění problému existovat.

#### <a name="group-assigned-enrollment-restrictions----747598---"></a>Omezení registrace přiřazená ke skupinám <!-- 747598 -->

Jako správce Intune teď můžete [vytvořit vlastní omezení registrace typů a limitu počtu zařízení u skupin uživatelů](enrollment-restrictions-set.md).

Intune Azure Portal vám umožňuje vytvořit až 25 instancí každého typu omezení, které pak můžete přiřadit ke skupinám uživatelů. Omezení přiřazená ke skupinám přepíší výchozí omezení.

Všechny instance typů omezení se budou uchovávat v seznamu se striktním pořadím. Toto pořadí definuje hodnotu priority pro případ řešení konfliktů. U uživatele, na něhož se vztahuje více instancí omezení, se uplatní jenom instance s nejvyšší prioritou. Prioritu dané instance můžete změnit tak, že ji přetáhnete na jiné místo v seznamu.

Tato funkce bude vydána spolu s migrací nastavení Androidu for Work z nabídky registrace Androidu for Work do nabídky Omezení registrace. Tato migrace může trvat několik dnů, a proto je možné, že v rámci listopadové verze se nejprve upgradují jiné části vašeho účtu a teprve poté se u omezení registrace povolí přiřazení skupin.

#### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Podpora více konektorů Služby zápisu síťových zařízení (NDES) <!-- 1528104 -->

Služba zápisu síťových zařízení umožňuje, aby mobilní zařízení spuštěná bez doménových přihlašovacích údajů získala certifikáty založené na protokolu SCEP (Simple Certificate Enrollment Protocol).
Od této aktualizace se podporuje více konektorů NDES.

#### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Oddělená správa zařízení s Androidem for Work od zařízení s Androidem <!-- 1490731 EEready-->

Intune podporuje správu registrace zařízení s Androidem for Work odděleně od platformy Android. Tato nastavení se spravují v části **Registrace zařízení** > **Omezení registrace** > **Omezení typů zařízení**. (Dříve se nacházela v části **Registrace zařízení** > **Registrace Androidu for Work** > **Nastavení registrace Android for Work**.)

Ve výchozím nastavení jsou nastavení zařízení s Androidem for Work stejná jako nastavení zařízení s Androidem. Po změně nastavení Androidu for Work tomu už tak nebude.

Pokud zablokujete registraci Androidu for Work u osobních zařízení, budou se jako Android for Work moct zaregistrovat jenom firemní zařízení s Androidem.

Při práci s těmito novými nastaveními vezměte v úvahu tyto informace:

##### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Pokud jste ještě nikdy nepoužili registraci Androidu for Work

Nová platforma Android for Work je ve výchozím nastavení omezení typů zařízení zablokovaná. Jakmile začnete funkci používat, můžete zařízením povolit, aby se zaregistrovala v Androidu for Work. Uděláte to tak, že změníte výchozí omezení typu zařízení nebo vytvoříte nové, které bude mít přednost před výchozím omezením.

##### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Pokud jste už registraci Androidu for Work použili

Pokud jste už platformu používali, závisí vaše situace na nastavení, která jste zvolili:

| Nastavení | Stav Androidu for Work ve výchozím omezení typu zařízení | Poznámky |
| --- | --- | --- |
| **Spravovat všechna zařízení jako Android for Work** | Blokované | Všechna zařízení s Androidem se musí zaregistrovat bez Androidu for Work. |
| **Spravovat podporovaná zařízení jako Android for Work** | Povoleno | Všechna zařízení s Androidem, která podporují Android for Work, se musí zaregistrovat s Androidem for Work. |
| **Spravovat podporovaná zařízení pro uživatele v těchto skupinách jako Android for Work** | Blokované | Vytvořila se samostatná zásada omezení typu zařízení, která přepíše výchozí zásadu. Tato zásada definuje skupiny, které jste dříve vybrali a povolili jim registraci Androidu for Work. Uživatelé ve vybraných skupinách budou moct dál zaregistrovat svoje zařízení s Androidem for Work. Žádní jiní uživatelé se v Androidu for Work nebudou moct zaregistrovat. |

Ve všech případech se vaše zamýšlená regulace zachová. K tomu, aby se zachovala možnost globálního používání Androidu for Work ve vašem prostředí nebo možnost používání této platformy konkrétními skupinami, nevyžadujeme z vaší strany žádnou akci.

### <a name="app-management"></a>Správa aplikací

#### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Aktualizovaná sestava instalace aplikací teď zahrnuje stav Instalace čeká <!-- 1249446 -->  

Sestava **Stav instalace aplikace** dostupná pro každou aplikaci v seznamu **Aplikace** v úloze **Mobilní aplikace** teď obsahuje počet **čekajících instalací** uživatelů a zařízení.

#### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>Rozhraní API inventáře aplikací pro iOS 11 pro ochranu před mobilními hrozbami <!-- 1391759 -->

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


### <a name="device-management"></a>Správa zařízení

#### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Migrace uživatelů a zařízení hybridního MDM do samostatného Intune <!-- 1463747 wnready -->
Pro přesun uživatelů a jejich zařízení z hybridní správy MDM do Intune na Azure Portalu jsou dostupné nové procesy a nástroje, které vám umožní:
- Kopírovat zásady a profily z konzoly Configuration Manageru do Intune na portálu Azure Portal
- Přesunout podmnožinu uživatelů do Intune na portálu Azure Portal a zbytek nechat v hybridním MDM
- Migrovat zařízení do Intune na portálu Azure Portal, aniž by bylo nutné je znovu zaregistrovat

Podrobnosti najdete v článku o [migraci uživatelů a zařízení hybridního MDM do samostatného Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

#### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Podpora vysoké dostupnosti místního konektoru Exchange Connector  <!-- 676614 -->
Jakmile konektor Exchange vytvoří připojení k Exchangi pomocí určeného serveru CAS může zjišťovat další servery CAS. Pokud primární server CAS přestane být dostupný, při selhání převezme služby konektoru jiný server CAS (pokud je k dispozici), dokud primární server CAS nebude znovu dostupný. Podrobnosti najdete v článku [Podpora vysoké dostupnosti místního konektoru Exchange](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

#### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Vzdálené restartování zařízení s iOSem (jenom v režimu pod dohledem) <!-- 1424595 -->

Pomocí akce zařízení můžete teď aktivovat restartování zařízení s iOSem 10.3 a novějším, které je v režimu pod dohledem. Další informace o použití akce restartování zařízení najdete v tématu [Vzdálené restartování zařízení přes Intune](device-restart.md).

> [!Note]
> Tento příkaz vyžaduje, aby byla zařízení v režimu pod dohledem, a přístupová práva k **zámku zařízení**. Zařízení se restartuje okamžitě. Zařízení s iOSem zamčená pomocí hesla se po restartování k síti Wi-Fi znovu nepřipojí a je možné, že po restartování nebudou moct komunikovat se serverem.

#### <a name="single-sign-on-support-for-ios----1333645---"></a>Podpora jednotného přihlašování pro iOS <!-- 1333645 -->  

Pro uživatele iOSu můžete využít jednotné přihlašování. Díky této aktualizaci konfigurace datové části fungují aplikace pro iOS, které jsou naprogramovány tak, aby v datové části jednotného přihlašování hledaly přihlašovací údaje uživatele. Ke konfiguraci hlavního názvu a sféry můžete použít také hlavní název uživatele (UPN) a ID zařízení v Intune. Podrobnosti najdete v článku [Nakonfigurování Intune na jednotné přihlašování pro zařízení s iOSem](sso-ios.md).

#### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Přidání aplikace Najít iPhone pro osobní zařízení <!--1427287-->
Teď můžete zobrazit, jestli je u zařízení s iOSem zapnutý zámek aktivace. Tato funkce se dříve nacházela v Intune na portálu Classic.


#### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Vzdálené uzamčení spravovaných zařízení s macOS přes Intune <!-- 1437691 -->

Ztracené zařízení s macOS můžete zamknout a nastavit pro ně 6místný číselný kód PIN pro obnovení. Když se zařízení zamkne, v okně **přehledu zařízení** se bude zobrazovat kód PIN, dokud se nepošle jiná akce zařízení.

Další informace si můžete přečíst v článku [Vzdálené uzamčení spravovaných zařízení přes Intune](device-remote-lock.md).

#### <a name="new-scep-profile-details-supported----1559808---"></a>Podpora nových podrobností profilu SCEP <!-- 1559808 -->

Při vytváření profilu SCEP na platformách Windows, iOS, macOS a Android teď správci můžou nakonfigurovat další nastavení.  Správci můžou nastavit IMEI, sériové číslo nebo běžný název včetně e-mailu ve formátu názvu subjektu.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

#### <a name="retain-data-during-a-factory-reset----1588489---"></a>Zachování dat při obnovení továrního nastavení <!--1588489 -->
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

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží
#### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Zobrazení přiřazení aktualizačního kanálu Windows 10 <!-- 1621837 -->
Při **řešení potíží** u aktuálně zobrazeného uživatele si můžete zobrazit veškerá přiřazení aktualizačních kanálů Windows 10.  

#### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Nastavení četnosti hlášení Rozšířené ochrany před internetovými útoky v programu Windows Defender <!-- 1455974  -->
Služba Rozšířená ochrana před internetovými útoky v programu Windows Defender umožňuje správcům spravovat četnost hlášení u spravovaných zařízení. Pomocí nové možnosti **Zvýšit četnost hlášení telemetrie** služba Rozšířená ochrana před internetovými útoky v programu Windows Defender častěji shromažďuje a vyhodnocuje rizika. Výchozí nastavení hlášení optimalizuje rychlost a výkon. Zvýšení četnosti hlášení může být velmi cennou pomůckou pro zařízení s vysokým rizikem. Toto nastavení najdete v profilu **Ochrana ATP v programu Windows Defender** v části **Konfigurace zařízení**.

#### <a name="audit-updates----1412961---"></a>Aktualizace auditu <!-- 1412961 -->  
Auditování Intune poskytuje záznam o operacích změn souvisejících s Intune.  Všechny operace vytvoření, aktualizace, odstranění a odebrání se zaznamenávají a uchovávají po dobu jednoho roku.  Azure Portal zobrazuje data auditování v každé úloze za posledních 30 dnů, která se dají filtrovat.  Příslušné rozhraní Graph API umožňuje načíst data auditování uložená za poslední rok.

Auditování najdete ve skupině **MONITOROVAT**. Pro každou úlohu existuje položka nabídky **Protokoly auditu**.




## <a name="week-of-november-20-2017"></a>Týden od 20. listopadu 2017

### <a name="app-management"></a>Správa aplikací

#### <a name="google-play-protect-support-on-android----908720---"></a>Podpora Google Play Protect na Androidu <!-- 908720 -->

S vydáním verze Android Oreo zavádí Google sadu bezpečnostních funkcí s názvem Google Play Protect, které uživatelům a organizacím umožňují provozovat zabezpečené aplikace a zabezpečené image Androidu. Intune teď podporuje funkce Google Play Protect, a to včetně vzdáleného ověření SafetyNet. Správci můžou nastavit požadavky na zásady dodržování předpisů, které vyžadují, aby funkce Google Play Protect byla nakonfigurovaná a funkční.
Nastavení **Ověření zařízení SafetyNet** vyžaduje, aby se zařízení připojilo ke službě Googlu, která ověří, že je zařízení v pořádku a není ohrožené. Správci můžou rovněž nastavením konfiguračního profilu pro Android for Work vyžádat, aby nainstalované aplikace byly ověřeny pomocí služeb Google Play. Pokud zařízení nesplňuje požadavky na Google Play Protect, může podmíněný přístup uživatelům zablokovat přístup k firemním prostředkům.

- Přečtěte si, [jak vytvořit zásadu dodržování předpisů zařízeními pro službu Google Play Protect](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

#### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Povolení textového protokolu ze spravovaných aplikací <!-- 1414050  -->

Aplikace spravované prostřednictvím sady Intune App SDK můžou posílat SMS zprávy.

## <a name="week-of-november-13-2017"></a>Týden od 13. listopadu 2017

### <a name="intune-apps"></a>Aplikace Intune
#### <a name="company-portal-app-for-macos-is-available---1541700--"></a>Aplikace Portál společnosti pro macOS je k dispozici <!--1541700-->
Portál společnosti Intune v systému macOS má aktualizované prostředí, které je optimalizované ke správnému zobrazení všech informací a oznámení o dodržování předpisů, což uživatelé potřebují pro všechna zaregistrovaná zařízení. Po nasazení Portálu společnosti Intune do zařízení v něm začne nástroj Microsoft AutoUpdate pro macOS zajišťovat aktualizace. Nový Portál společnosti Intune pro macOS můžete stáhnout po přihlášení na web Portál společnosti pro macOS ze zařízení macOS.

#### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Microsoft Planner je teď součástí seznamu schválených aplikací pro správu mobilních aplikací (MAM) <!-- 1248473 -->
Aplikace Microsoft Planner pro iOS a Android je teď součástí schválených aplikací pro správu mobilních aplikací (MAM). Aplikaci lze nakonfigurovat prostřednictvím okna Intune App Protection na portálu Azure Portal pro všechny tenanty.
- Další informace najdete v [seznamu schválených aplikací MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Frekvence aktualizace požadavků sítě VPN podle aplikace na zařízeních s iOSem <!-- 1547061 -->  
Správci mohou nyní v aplikacích zařízení s iOSem odebrat požadavky sítě VPN podle aplikace; dotčená zařízení to provedou po jejich dalším vrácení se změnami do Intune, které obvykle probíhá do 15 minut.  

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží
#### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Podpora sady System Center Operations Manager Management Pack pro konektor Exchange Connector <!-- 885457 -->
Pro pomoc s analýzou protokolů Exchange Connectoru je nyní dostupná sada System Center Operations Manager (SCOM) Management Pack pro Exchange Connector. Při řešení problémů vám tato funkce poskytuje různé způsoby monitorování služby.

## <a name="week-of-november-6-2017"></a>Týden od 6. listopadu 2017

### <a name="device-enrollment"></a>Registrace zařízení
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Společná správa zařízení s Windows 10  <!-- 1243445 -->
Společná správa je řešení, které představuje most mezi tradiční a moderní správou a poskytne vám cestu k přechodu pomocí přístupu ve fázích. V základu je společná správa řešením, kdy jsou zařízení s Windows 10 současně spravovaná pomocí Configuration Manageru a Microsoft Intune a také připojená k Active Directory (AD) a Azure Active Directory (Azure AD).  Tato konfigurace vám poskytne cestu k modernizaci v průběhu času a tempem, které je nejvhodnější pro vaši organizaci, pokud nemůžete přesunout všechno najednou.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Omezení registrace zařízení s Windows podle verze operačního systému <!-- 245498 -->
Jako správce Intune teď můžete pro registrace zařízení zadat minimální a maximální verzi Windows 10. Tato omezení můžete nastavit v okně **Konfigurace platforem**.

Intune dál podporuje registraci telefonů a počítačů s Windows 8.1. S minimální a maximální mezí se ale dají nastavit jenom verze Windows 10. Pokud chcete povolit registraci zařízení s Windows 8.1, nechte minimální mez prázdnou.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Upozornění na zařízení, která nemají přiřazený Windows AutoPilot <!-- 1631236 -->
Na stránce **Microsoft Intune** > **Registrace zařízení** > **Přehled** je k dispozici nové upozornění, které se týká zařízení s nepřiřazeným Windows AutoPilotem. Toto upozornění ukazuje, kolik zařízení z programu AutoPilot nemá přiřazené profily nasazení AutoPilotu. Na základě informací v upozornění můžete vytvořit profily a přiřadit je potřebným zařízením. Když na upozornění kliknete, zobrazí se úplný seznam zařízení Windows AutoPilotu a podrobné informace o zařízeních. Další informace najdete v článku [Registrace zařízení s Windows pomocí programu Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="device-management"></a>Správa zařízení

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Tlačítko pro aktualizaci seznamu zařízení <!-- 1333581 -->
Protože se seznam zařízení neaktualizuje automaticky, můžete zařízení, která se v seznamu zobrazují, aktualizovat pomocí nového tlačítka Aktualizovat.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Podpora certifikační autority (CA) Symantec Cloud <!-- 1333638 -->    
Intune teď podporuje certifikační autoritu Symantec Cloud. To umožňuje, aby Intune Certificate Connector vystavoval zařízením spravovaným přes Intune certifikáty PKCS z certifikační autority Symantec Cloud. Pokud už Intune Certificate Connector používáte s certifikační autoritou Microsoft, můžete existující nastavení Intune Certificate Connectoru použít k přidání podpory pro certifikační autoritu Symantec.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Nové položky přidané do inventáře zařízení   <!--1404455 -->
V [inventáři, který pořizují zaregistrovaná zařízení](device-inventory.md), jsou teď dostupné následující nové položky:

- Adresa MAC pro Wi-Fi
- Celkové místo v úložišti
- Celkové volné místo
- MEID
- Poskytovatel služeb pro odběratele


### <a name="app-management"></a>Správa aplikací
#### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Nastavení přístupu pro aplikace pomocí opravy minimálního zabezpečení Androidu na zařízení<!-- 1278463 -->   
Správce může definovat minimální opravu zabezpečení Androidu, která musí být na zařízení nainstalovaná, aby zařízení pod spravovaným účtem získalo přístup ke spravované aplikaci.

> [!Note]  
> Tato funkce omezuje jenom opravy zabezpečení vydané společností Google na zařízeních s Androidem 6.0 a novějším.

#### <a name="app-conditional-launch-support----1193313---"></a>Podpora podmíněného spouštění aplikací <!-- 1193313 -->
Správci IT teď můžou pomocí portálu pro správu Azure nastavit požadavek, aby se prostřednictvím správy mobilních aplikací (MAM) při spouštění aplikace místo číselného kódu PIN vynutilo heslo. Při takové konfiguraci musí uživatel po zobrazení výzvy nastavit a používat heslo, aby získal přístup k aplikacím s podporou MAM. Heslo je definované jako číselný kód PIN s aspoň jedním speciálním znakem nebo velkým/malým písmenem. Tato verze Intune tuto funkci povolí **jenom v iOSu**. Intune podporuje heslo podobným způsobem jako číselný kód PIN, stanovuje minimální délku a povoluje opakování znaků a sekvencí. Tato funkce vyžaduje, aby aplikace (to znamená WXP, Outlook, Managed Browser, Yammer) integrovaly sadu Intune App SDK s kódem této funkce místo vynucení nastavení hesla v cílových aplikacích.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Číslo verze aplikace pro obchodní aplikace ve zprávě o stavu instalace zařízení <!-- 1233999 -->
Od této verze se ve zprávě o stavu instalace zařízení zobrazí u obchodních aplikací pro iOS a Android číslo verze aplikace. Tyto informace můžete využít k řešení potíží s aplikacemi nebo nalezení zařízení, na kterých běží zastaralé verze aplikací.


### <a name="device-configuration"></a>Konfigurace zařízení
#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Správci teď můžou konfigurovat nastavení brány firewall na zařízení pomocí profilu konfigurace zařízení <!-- 951708 -->   
Správci můžou zapnout bránu firewall pro zařízení a také nakonfigurovat různé protokoly pro doménové, privátní a veřejné sítě.  Tato nastavení brány firewall najdete v profilu „Ochrana koncového bodu“.

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Ochrana Application Guard v programu Windows Defender pomáhá chránit zařízení před nedůvěryhodnými weby, jak je definuje vaše organizace <!-- 958257 -->   
Správci můžou definovat weby jako „důvěryhodné“ nebo „podnikové“ pomocí pracovního postupu Windows Information Protection nebo nového profilu „Ohraničení sítě“ v konfiguracích zařízení. Weby, které na zařízení s 64bitovou verzí Windows 10 nejsou uvedené v důvěryhodném ohraničení sítě, se při zobrazení v prohlížeči Microsoft Edge místo toho otevřou v prohlížeči ve virtuálním počítači Hyper-V.

Application Guard najdete v konfiguračních profilech zařízení v profilu „Ochrana koncového bodu“. Tam můžou správci konfigurovat interakce mezi virtualizovaným prohlížečem a hostitelským počítačem, nedůvěryhodné a důvěryhodné weby a ukládání dat vygenerovaných ve virtualizovaném prohlížeči. Pokud chcete Application Guard na zařízení používat, musí se nejdříve nakonfigurovat ohraničení sítě. Je důležité, aby se pro zařízení definovalo jenom jedno ohraničení sítě.  

#### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Řízení aplikací v programu Windows Defender ve Windows 10 Enterprise poskytuje režim k důvěřování jenom autorizovaným aplikacím <!-- 1031096 -->    
Protože každý den vznikají tisíce nových škodlivých souborů, nemusí už boj proti malwaru pomocí antivirové ochrany využívající podpisy souborů poskytovat dostatečnou obranu před novými útoky. Pomocí Řízení aplikací v programu Windows Defender ve Windows 10 Enterprise můžete konfiguraci zařízení změnit z režimu, kdy jsou aplikace důvěryhodné, pokud nejsou blokované antivirovou ochranou nebo jiným řešením zabezpečení, na režim, kdy operační systém důvěřuje jenom aplikacím autorizovaným vaší organizací. Důvěryhodnost se aplikacím přiřazuje v Řízení aplikací v programu Windows Defender.

Pomocí Intune můžete zásady řízení aplikací nakonfigurovat v režimu „pouze audit“ nebo v režimu vynucení. Aplikace nejsou při spouštění v režimu „pouze audit“ blokované. Režim „pouze audit“ zapisuje všechny události do protokolů místního klienta. Můžete také nakonfigurovat, jestli je povolené spouštět jenom součásti Windows a aplikace pro Microsoft Store, nebo jestli se můžou spouštět i další aplikace s dobrou reputací, jak je definuje Intelligent Security Graph.

#### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Ochrana Exploit Guard v programu Windows Defender je nová sada funkcí pro prevenci neoprávněných vniknutí pro Windows 10 <!-- 1063615 -->   
Ochrana Exploit Guard v programu Windows Defender obsahuje vlastní pravidla pro snížení zneužitelnosti aplikací, brání hrozbám z maker skriptů, automaticky blokuje síťová připojení k IP adresám se špatnou reputací a může zabezpečit data před ransomwarem a neznámými hrozbami. Ochrana Exploit Guard v programu Windows Defender se skládá z těchto součástí:

- **Omezení možností útoků** poskytuje pravidla, která vám umožní zabránit hrozbám z maker, skriptů a e-mailů.
- **Řízený přístup ke složkám** automaticky blokuje přístup k obsahu chráněných složek.
- **Filtrování sítě** blokuje odchozí připojení z jakékoli aplikace k IP nebo doméně se špatnou reputací.
- **Ochrana Exploit Protection** poskytuje omezení paměti, toku řízení a zásad, která se dají využít k ochraně aplikace před zneužitím.


#### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Správa powershellových skriptů v Intune u zařízení s Windows 10 <!-- 790537 -->

Rozšíření správy Intune umožňuje nahrát powershellové skripty do Intune, aby je bylo možné spouštět v zařízeních s Windows 10. Toto rozšíření doplňuje funkce správy mobilních zařízení (MDM) s Windows 10 a usnadňuje přechod na moderní správu. Podrobnosti najdete v článku [Správa powershellových skriptů v Intune u zařízení s Windows 10](intune-management-extension.md).

#### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nová nastavení omezení pro zařízení s Windows 10      <!-- 1308850 -->
-    Zasílání zpráv (jenom mobilní) – zakázání testování nebo zpráv MMS
-    Heslo – nastavení k povolení standardu FIPS a použití sekundárních zařízení Windows Hello k ověřování 
-    Zobrazit – nastavení k zapnutí nebo vypnutí škálování GDI pro starší verze aplikací

#### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Omezení zařízení s Windows 10 na režim veřejného terminálu <!-- 1308872 -->   
Uživatele zařízení s Windows 10 můžete omezit na režim veřejného terminálu, který uživatele omezuje na sadu předdefinovaných aplikací.  To uděláte tak, že vytvoříte profil omezení zařízení s Windows 10 a nastavíte režim Veřejný terminál.

Režim veřejného terminálu podporuje dva režimy: **s jednou aplikací** (umožňuje uživateli spustit jenom jednu aplikaci) nebo **s více aplikacemi** (povoluje přístup k sadě aplikací).  Definujete uživatelský účet a název zařízení a tím se určí podporované aplikace.  Když je uživatel přihlášený, je omezený na definované aplikace.  Další informace najdete v článku [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Režim veřejného terminálu vyžaduje:

- Intune musí být autoritou pro správu mobilních zařízení (MDM).
- Aplikace už musí být v cílovém zařízení nainstalované.
- Zařízení musí být [správně zřízené](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

#### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nový profil konfigurace zařízení pro vytvoření ohraničení sítě <!-- 1311967 -->   
Součástí jiných profilů konfigurace zařízení je nový profil konfigurace zařízení s názvem **Ohraničení sítě**. Tento profil slouží k definování online prostředků, které chcete, aby se považovaly za podnikové a důvěryhodné. Ohraničení sítě pro zařízení musíte definovat *před tím*, než na něm bude možné používat funkce jako ochrana Application Guard v programu Windows Defender a Windows Information Protection. Je důležité, aby se pro každé zařízení definovalo jenom jedno ohraničení sítě.

Můžete definovat podnikové cloudové prostředky, rozsahy IP adres a interní proxy servery, které se mají považovat za důvěryhodné. Po definování můžou ohraničení sítě využívat ostatní funkce jako ochrana Application Guard v programu Windows Defender a Windows Information Protection.

####  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Další dvě nastavení pro Antivirovou ochranu v programu Windows Defender <!-- 1338409 -->  
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

#### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Přidáno Citrix VPN pro zařízení s Windows 10 <!-- 1512457 -->  
Pro zařízení s Windows 10 můžete nakonfigurovat Citrix VPN. Citrix VPN můžete zvolit ze seznamu *Vyberte typ připojení* v okně **Základní síť VPN** při konfiguraci VPN pro Windows 10 a novější.

> [!Note]
> Konfigurace Citrix existovala pro iOS a Android.

#### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Připojení Wi-Fi podporují u iOSu předsdílené klíče<!-- 1550823 -->
Zákazníci můžou nakonfigurovat profily sítě Wi-Fi, aby mohli na zařízeních s iOSem používat předsdílené klíče (PSK) pro připojení typu WPA/WPA2-Personal. Tyto profily se doručí do zařízení uživatelů, když se zařízení zaregistruje v Intune.

Když je profil doručený do zařízení, bude další krok záviset na tom, jak je profil nakonfigurovaný.  Pokud je profil nastavený na automatické připojení, aktivuje se připojení automaticky, až bude příště potřeba síť.  Pokud je profil nastavený na ruční připojení, musí uživatel aktivovat připojení ručně.  

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Přístup k protokolům spravovaných aplikací pro iOS <!-- 1469920 -->
Koncoví uživatelé, kteří mají nainstalovaný Managed Browser, teď můžou zobrazit stav správy všech aplikací publikovaných Microsoftem a posílat protokoly pro řešení problémů se spravovanými aplikacemi pro iOS.

Informace o tom, jak na zařízení s iOSem povolit v Managed Browseru režim pro řešení problémů, najdete v tématu [Jak se dostat k protokolům spravovaných aplikací pomocí Managed Browseru na zařízení s iOSem](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

#### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Vylepšení pracovního postupu instalace zařízení na Portálu společnosti pro iOS verze 2.9.0 <!-- 1417174 -->

Pracovní postup instalace zařízení v aplikaci Portál společnosti pro iOS byl vylepšen. Jazyk je uživatelsky přívětivější a tam, kde to bylo možné, jsme také sjednotili obrazovky. Díky použití názvu vaší firmy všude v textu instalace je jazyk lépe přizpůsobený vaší firmě. Tento aktualizovaný pracovní postup uvidíte  [na stránce Co je nového v uživatelském rozhraní](whats-new-app-ui.md).

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Entita uživatele obsahuje nejnovější uživatelská data v datovém modelu datového skladu<!-- 1544273 -->
První verze datového modelu datového skladu Intune obsahovala jenom poslední historická data Intune. Při vytváření sestav nebylo možné zachytit aktuální stav uživatele. V této aktualizaci se **entita uživatele** naplní nejnovějšími uživatelskými daty.


## <a name="notices"></a>Sdělení

### <a name="plan-for-change-new-windows-10-setting-for-kiosk-configuration-in-intune----1560072---"></a>Plánovaná změna: Nové nastavení ve Windows 10 pro konfiguraci veřejného terminálu v Intune <!-- 1560072 -->
Mění se způsob, jak a kde je možné nakonfigurovat plochu ve Windows 10 1709 a novějších (RS3 a novějších) na portálu Intune Azure.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená? 
Naše záznamy ukazují, že používáte nastavení Windows 10 > Omezení zařízení > Veřejný terminál (Preview). To se v uživatelském rozhraní v květnu přejmenuje na Windows 10 > Omezení zařízení > Veřejný terminál (zastaralé), aby uživatelé věděli, že se jeho použití už nedoporučuje. I nadále bude ale fungovat až do červnové aktualizace Intune. Potom se v back-endu změní na zastaralé a přestane být funkční. Jako alternativu představíme v květnu nový profil konfigurace zařízení (Windows 10 > Veřejný terminál), který bude obsahovat nastavení pro konfiguraci veřejného terminálu na Windows 10 RS4 a novějších.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?  
Po vydání květnové aktualizace služby Intune plánované ke konci května zveřejníme pokyny, jak si vyzkoušet a ověřit, že můžete migrovat konfiguraci veřejného terminálu z Windows 10 RS3 do Windows 10 RS4. Podle těchto pokynů můžete zařízení nakonfigurovat jako veřejné terminály s využitím nového konfiguračního profilu zařízení pro veřejné terminály.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Tato změna ovlivní jak zákazníky samostatné verze Intune, tak zákazníky hybridní verze (Intune s Configuration Managerem). Tato integrace pomůže zjednodušit práci se správou cloudu. Při správě skupin, zásad, aplikací a mobilních zařízení vám teď stačí přejít do jednoho okna v Azure, a sice do okna Intune.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Místo okna služby Intune App Protection si do oblíbených položek přidejte Intune a seznamte se s pracovním postupem zásad ochrany aplikací v okně Mobilní aplikace v Intune. Po krátkém období přesměrování okno App Protection odebereme. Nezapomeňte, že všechny zásady ochrany aplikací jsou už přenesené do Intune a kterékoli ze zásad podmíněného přístupu můžete upravit podle dokumentace, kterou najdete zde: [https://aka.ms/azuread_ca](https://aka.ms/azuread_ca).

**Další informace**: [https://aka.ms/intuneapppolicy](https://aka.ms/intuneapppolicy)

### <a name="plan-for-change-change-in-support-for-the-microsoft-intune-app-sdk-for-cordova-plugin"></a>Plánovaná změna: Změna v podpoře modulu plug-in Microsoft Intune App SDK Cordova
Intune ukončuje od 1. května 2018 podporu [modulu plug-in Microsoft Intune App SDK Cordova](app-sdk-cordova.md). Doporučujeme místo toho použít k přípravě aplikací využívajících Cordovu pro účely správy a dostupnosti v Intune nástroj Intune App Wrapping. Až tato změna vejde v platnost, nebude se už dále modul plug-in Microsoft Intune APP SDK Cordova udržovat a nebude ani přijímat aktualizace. Vývojáři aplikací nebudou moct tento modul plug-in používat. V Intune se dále počítá s podporou aplikací vytvořených s použitím Cordovy. Všechny aplikace vytvořené s použitím modulu plug-in Microsoft Intune APP SDK Cordova ale budou mít v Intune omezené funkce. Po zabalení s pomocí nástroje Intune App Wrapping Tool bude možné nasadit aplikace koncovým uživatelům jako obvykle. Aplikace pro Android využívající Cordovu vydané do obchodu Google Play:
- Koncovým uživatelům se při prvním spuštění zobrazí výzva k zadání přihlašovacích údajů, aby mohli přijmout zásady Intune.
- Aplikace by měly být vydány do obchodu s aplikacemi jako určené pro uživatele Intune, například Aplikace Contoso pro Intune.

Další informace o nástroji App Wrapping Tool najdete v tématech [Nástroj App Wrapping Tool pro iOS](app-wrapper-prepare-ios.md) a [Nástroj App Wrapping Tool pro Android](app-wrapper-prepare-android.md). S případnými problémy nebo dotazy se obraťte na [msintuneappsdk@microsoft.com](mailto:msintuneappsdk@microsoft.com).

### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Plánovaná změna: Ke správě MDM se teď používá Intune v Azure <!-- 1227338 -->
Před více než rokem jsme oznámili vydání [Intune ve verzi Public Preview na platformě Azure](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) a pak před šesti měsíci [obecnou dostupnost nového prostředí pro správu](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) Intune. Od 31. srpna 2018 vypínáme správu mobilních zařízení (MDM) v klasické konzole Silverlight pro zákazníky, kteří používají Intune samostatně. Místo toho můžete ke svým potřebám MDM používat [Intune v Azure](https://aka.ms/Intune_on_Azure). Pokud k MDM ještě používáte klasickou konzolu, přestaňte ji prosím používat a seznamte se s Intune v Azure. Neočekáváme, že tato změna bude mít nějaký dopad na koncové uživatele. Klasická správa počítačů zůstane v Silverlightu. Další informace o této změně a o jejím dopadu na vás najdete [tady](https://aka.ms/Intune_on_Azure_mdm).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Přímý přístup ke scénářům registrace Apple <!--951869-->
U účtů Intune vytvořených po lednu 2017 umožňuje Intune přímý přístup ke scénářům registrace Apple pomocí úlohy Registrovat zařízení na portálu Azure Portal. Náhled na registraci Apple byl předtím přístupný jen přes odkazy na klasickém portálu Intune. Zpřístupnění těchto funkcí v Azure vyžaduje u účtů Intune vytvořených před lednem 2017 jednorázovou migraci. Plán této migrace zatím nebyl oznámen, podrobnosti ale budou zpřístupněny co nejdříve. Pokud váš existující účet nemá k Azure Portalu přístup, k otestování tohoto nového prostředí důrazně doporučujeme vytvořit zkušební účet.

## <a name="whats-coming"></a>Co připravujeme

### <a name="local-device-security-option-settings----1251887---"></a>Nastavení možnosti místního zabezpečení zařízení <!-- 1251887 -->
Pomocí nového nastavení možnosti místního zabezpečení zařízení budete moct povolit nastavení zabezpečení na zařízeních s Windows 10. Tato nastavení najdete v kategorii Ochrana koncového bodu při vytváření zásad konfigurace zařízení s Windows 10.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968--"></a>Nová aktualizace uživatelského prostředí pro web Portál společnosti <!--2000968-->

V dubnu představíme nový web Portál společnosti, který bude mít aktualizované uživatelské prostředí, zjednodušené pracovní postupy a lepší přístupnost. Bude zahrnovat rozšíření orientované na zákazníka, jako je sdílení aplikací a vylepšený celkový výkon, která vám přinese lepší uživatelský zážitek.
Na základě zpětné vazby od zákazníků, jako jste vy, jsme přidali několik nových funkcí, které výrazně zlepší stávající funkčnost a použitelnost:

-   Vylepšení uživatelského rozhraní na celém webu
-   Možnost sdílet přímé odkazy na aplikace
- Vylepšený výkon u velkých katalogů aplikací

V rámci přípravy na tuto změnu nemusíte provádět žádnou akci. Jakmile bude aktualizovaný web Portál společnosti pro vás dostupný, dáme vám vědět. Je však možné, že nakonec budete muset dokumentaci pro koncové uživatele doplnit o aktualizované snímky obrazovky. Nezapomeňte, že možná bude nutné také aktualizovat dokumentaci pro aplikaci Portál společnosti v iOSu, protože web využívá část **Aplikace** v aplikaci pro iOS. Ukázkový obrázek těchto změn najdete na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md).

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple bude vyžadovat aktualizace ATS (Application Transport Security) <!--748318-->
Apple oznámil, že začne vynucovat specifické požadavky na ATS (Application Transport Security). ATS se používá k vynucení vyššího zabezpečení veškeré komunikace aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune, kteří používají aplikace Portál společnosti pro iOS. S podrobnostmi vás seznámíme na [blogu podpory Intune](https://aka.ms/compportalats).



## <a name="see-also"></a>Viz taky
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](https://www.microsoft.com/cloud-platform/roadmap)
* [Co je nového v uživatelském rozhraní Portálu společnosti](whats-new-app-ui.md)
* [Novinky v předchozích měsících](whats-new-archive.md)
