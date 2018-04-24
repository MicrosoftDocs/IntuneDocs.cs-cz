---
title: Časná edice
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b6ca8108924c6c062da0d0ef56ab5b68635dd9ca
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="the-early-edition-for-microsoft-intune---april-2018"></a>Časná edice Microsoft Intune – duben 2018

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

<!-- 1804 start -->

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802--"></a>Nové nastavení Ochrany Credential Guard v programu Windows Defender přidaná do nastavení ochrany koncového bodu <!--1102252 --><!--from 1802-->

Do části **Konfigurace zařízení** > **Profily** > **Ochrana koncového bodu** se přidají nová nastavení [Ochrany Credential Guard v programu Windows Defender](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard). Budou přidána následující nastavení:

- Úroveň zabezpečení platformy: Zadejte, zda se při příštím restartování povolí úroveň zabezpečení platformy. Zabezpečení na základě virtualizace vyžaduje Zabezpečené spuštění. Zabezpečení na základě virtualizace je možné volitelně povolit s použitím ochran přímého přístupu do paměti (DMA). Ochrany DMA vyžadují hardwarovou podporu a povolí se jenom na správně nakonfigurovaných zařízeních.
- Zabezpečení na základě virtualizace: Zadejte, zda se při příštím restartování povolí zabezpečení na základě virtualizace.
- Ochrana Credential Guard v programu Windows Defender: Zapněte ochranu Credential Guard se zabezpečením na základě virtualizace, abyste pomohli ochránit přihlašovací údaje při příštím restartování v případě, že jsou povoleny úroveň zabezpečení platformy se Zabezpečeným spuštěním a zabezpečení na základě virtualizace. Dostupné možnosti zahrnují **Zakázáno**, **Povoleno s uzamčením UEFI**, **Povoleno bez uzamčení** a **Nenakonfigurováno**.
  - Možnost Zakázáno vzdáleně vypne ochranu Credential Guard, pokud byla dříve zapnutá pomocí možnosti Povoleno bez uzamčení.

  - Možnost Povoleno s uzamčením UEFI zajistí, že ochranu Credential Guard nebude možné zakázat pomocí klíče registru nebo pomocí zásad skupiny. Pokud chcete zakázat ochranu Credential Guard po použití tohoto nastavení, musíte zásady skupiny nastavit na Zakázáno a odebrat funkci zabezpečení z jednotlivých počítačů za osobní přítomnosti uživatele, aby bylo možné vymazat konfiguraci trvale uloženou v UEFI. Dokud je konfigurace UEFI trvale uložena, je ochrana Credential Guard povolena.

  - Možnost Povoleno bez uzamčení umožní vzdálené zakázání ochrany Credential Guard pomocí zásad skupiny. Na zařízeních s tímto nastavením musí běžet přinejmenším Windows 10 (verze 1511).

  - Možnost Nenakonfigurováno ponechá nastavení zásad nedefinované. Zásady skupiny nezapíšou nastavení zásad do registru, a proto počítače ani uživatele nijak neovlivní. Pokud v registru existuje aktuální nastavení, zůstane beze změny.

### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Podpora hesla pro kód PIN MAM na Androidu<!-- 1438086 -->

Správci Intune budou moct nastavit požadavek na spuštění aplikace a vynutit tak heslo místo číselného kódu PIN MAM. Při takové konfiguraci bude uživatel muset po zobrazení výzvy nastavit a používat heslo, aby získal přístup k aplikacím s podporou MAM. Heslo je definované jako číselný kód PIN s aspoň jedním speciálním znakem nebo velkým/malým písmenem. Intune podporuje heslo podobným způsobem jako existující číselný kód PIN, umožňuje stanovit minimální délku a povoluje opakování znaků a sekvencí prostřednictvím konzoly pro správu. Tato funkce vyžaduje nejnovější verzi Portálu společnosti na Androidu. Tato funkce je už k dispozici pro iOS.

###  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>Blokování kamery a snímků obrazovky na Androidu for Work <!-- 1098977 eeready-->
Pro blokování při konfiguraci omezení zařízení na zařízeních s Androidem budou k dispozici nové vlastnosti: 
- Kamera: Blokování přístupu ke všem kamerám na zařízení
- Snímek obrazovky: Blokování vytváření snímků obrazovky a tím také ochrana obsahu před zobrazením na zobrazovacích zařízení, která nemají zabezpečený výstup videa

Platí pro Android for Work.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Podpora obchodních aplikací (LOB) pro macOS <!-- 1473977 -->
Microsoft Intune bude poskytovat možnost instalace obchodních aplikací pro macOS z portálu Azure Portal. Do Intune budete moct přidat obchodní aplikaci pro masOS poté, co ji předběžně zpracoval nástroj dostupný v GitHubu. Na portálu Azure Portal v okně **Intune** zvolte **Mobilní aplikace**. V okně **Mobilní aplikace** zvolte **Aplikace** > **Přidat**. V okně **Přidat aplikaci** vyberte **Obchodní aplikace**. 

### <a name="support-for-user-less-devices----1637553---"></a>Podpora pro zařízení bez určeného uživatele <!-- 1637553 -->
Intune bude podporovat možnost vyhodnocení dodržování předpisů u zařízení bez určeného uživatele, jako je Microsoft Surface Hub. Zásady dodržování předpisů mohou cílit na konkrétní zařízení. Dodržování (a nedodržování) předpisů je tedy možné stanovit i u zařízení, která nemají přiřazené uživatele.

### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Další nastavení možností místního zabezpečení zařízení <!-- 1403702 -->
U zařízení s Windows 10 budete moct nakonfigurovat další nastavení možností místního zabezpečení zařízení. Další nastavení budou dostupná v oblasti Klienta sítě Microsoft, Serveru sítě Microsoft, zabezpečení sítě a přístupu k ní a interaktivního přihlášení. Tato nastavení najdete v kategorii Ochrana koncového bodu při vytváření zásad konfigurace zařízení s Windows 10.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Nutnost instalace zásad, aplikací a profilů certifikátů a sítí <!-- 1553555 -->
Správci budou moct koncovým uživatelům zablokovat přístup k desktopu Windows 10 RS4, dokud Intune nenainstaluje zásady, aplikace a profily certifikátů a sítí při zřizování zařízení AutoPilot.

### <a name="rules-for-removing-devices----1609459---"></a>Pravidla odebírání zařízení <!-- 1609459 -->
Budou k dispozici nová pravidla, která vám umožní automaticky odebrat zařízení, která nebyla vrácena se změnami po uplynutí nastaveného počtu dnů. Pokud se na nové pravidlo chcete podívat, přejděte do okna **Intune** vyberte **Zařízení** a vyberte **Device removal rules** (Pravidla pro odebrání zařízení).

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Blokování uživatelských aplikací a prostředí na zařízeních Windows 10 Enterprise RS4 AutoPilot<!-- 1621980 -->
Budete moct zabránit v instalaci uživatelských aplikací a prostředí na zařízeních Windows 10 Enterprise RS4 AutoPilot. Pokud se chcete podívat na tuto funkci, přejděte na **Intune** > **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily Windows AutoPilot** > **Vytvořit nový** > **Nastavení registrace**. 

### <a name="advanced-threat-protection-integrated-with-intune----1629303---"></a>Integrace rozšířené ochrany před internetovými útoky s Intune <!-- 1629303 -->
[Rozšířená ochrana před internetovými útoky (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) zobrazuje úroveň rizika u zařízení s Windows 10. Když Intune vyhodnotí stav dodržování předpisů u zařízení s Windows 10, skóre rizika ATP se do tohoto vyhodnocení také zahrne. Podmíněný přístup ATP můžete využít k ochraně sítě.

### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nové kroky registrace pro uživatele používající zařízení s macOS High Sierra 10.13.2+ <!--1734567 -->
Systém macOS high Sierra 10.13.2 představil nový koncept registrace MDM, který vyžaduje schválení uživatelem (User Approved). V budoucnu schválené registrace umožní službě Intune spravovat některá nastavení týkající se zabezpečení. Další informace najdete v dokumentaci podpory Apple tady: https://support.apple.com/HT208019.

Zařízení zaregistrovaná pomocí Portálu společnosti pro macOS se budou považovat za zařízení neschválená uživatelem, pokud koncový uživatel neotevře předvolby systému a ručně neposkytne schválení. Z tohoto důvodu nyní Portál společnosti pro macOS instruuje uživatele systému macOS 10.13.2 a novějšího, aby na konci procesu registrace přešli do příslušného umístění a ručně registraci schválili. Konzola správce Intune oznámí, zda je zaregistrované zařízení schváleno uživatelem.

### <a name="delete-autopilot-devices----1713650---"></a>Odstranění zařízení AutoPilot <!-- 1713650 -->
Správci Intune budou moct odstraňovat zařízení AutoPilot.

### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Předdefinované skupiny Všichni uživatelé a Všechna zařízení pro přiřazení aplikace pro Android for Work (AFW)<!-- 1813073 -->
Pro přiřazení aplikace pro AFW budete moct využít předdefinovaných skupin **Všichni uživatelé** a **Všechna zařízení**. Podrobnosti najdete v tématu [Zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune](apps-inc-exl-assignments.md).

### <a name="improved-device-deletion-experience---1832333---"></a>Vylepšené prostředí pro odstraňování zařízení <!--1832333 -->
Nadále už nebudete muset před odstraněním zařízení z Intune odebírat firemní data ani obnovovat zařízení do továrního nastavení.

Pokud se chcete podívat na nové prostředí, přihlaste se k Intune a vyberte **Zařízení** > **Všechna zařízení** > název zařízení > **Odstranit**.

 Pokud i nadále chcete potvrzovat vymazání nebo vyřazení, můžete použít standardní cestu životního cyklu zařízení a před **odstraněním** vybrat možnost **Odebrat firemní data** a **Obnovení továrního nastavení**. 

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Přesunutí profilů AutoPilot do cílení na skupinu <!-- 1877935 -->
V současné době je možné profily nasazení AutoPilot přiřadit vybraným zařízení. Ke konci dubna bude způsob přiřazení těchto profilů vypadat takto:
- Vytvoření skupin (Azure AD), které obsahují zařízení AutoPilot.
- Přiřazení požadovaných profilů ke skupině Azure AD. Profil AutoPilot se nyní přiřadí k zařízení AutoPilot v dané skupině.

### <a name="play-sounds-on-ios-when-in-lost-mode----1629303---"></a>Přehrávání zvuků v iOSu v režimu ztráty <!-- 1629303 -->
Pokud zařízení s iOSem pod dohledem jsou v [režimu ztráty](device-lost-mode.md) MDM (Mobile Device Management), můžete přehrát zvuk (**Zařízení** > **Všechna zařízení** > vyberte zařízení s iOSem > **Přehled** > **Další**). Zvuk se bude přehrávat tak dlouho, dokud je u zařízení režim ztráty aktivní nebo dokud uživatel zvuk na zařízení nevypne. Platí pro zařízení s iOSem 9.3 nebo novějším.

### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Použití vlastního názvu subjektu u certifikátu SCEP <!-- 2064190 -->
U profilu certifikátu SCEP budete moct ve vlastním subjektu použít běžný název (**OnPremisesSamAccountName**). Můžete například použít `CN={OnPremisesSamAccountName})`.

### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Odesílání diagnostických hlášení v aplikaci Portál společnosti pro macOS <!-- 2216677 -->
Aplikace Portál společnosti pro zařízení s macOS budou aktualizovány, aby se vylepšil způsob, jakým uživatelé nahlašují chyby Intune. Z aplikace Portál společnosti budou vaši zaměstnanci moct:
- Posílat diagnostická hlášení přímo vývojovému týmu Microsoft.
- Posílat e-mailem ID incidentů týmu IT podpory vaší společnosti.

### <a name="always-on-vpn-for-windows-10---1333666---"></a>VPN Always On pro Windows 10 <!--1333666 -->

V současné době je možné [Always On](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) použít na zařízeních s Windows 10 prostřednictvím vlastního profilu VPN vytvořeného pomocí OMA-URI.

S touto aktualizací budou správci moct povolit Always On pro profily VPN Windows 10 přímo v Intune na portálu Azure Portal. Profily VPN Always On se automaticky připojí v těchto případech:

- Při přihlášení uživatelů do zařízení
- Při změně sítě na zařízení
- Při opětovném zapnutí obrazovky na zařízení po vypnutí

### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Vylepšené zasílání chybových zpráv při chybě odeslání certifikátu Apple MDM Push Certificate <!-- 2172331 -->

Chybová zpráva bude obsahovat vysvětlení, že při obnovení existujícího certifikátu MDM je třeba použít stejné Apple ID.

###  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>Graf profilu zařízení a seznam stavů zobrazují všechna zařízení ve skupině <!-- 1449153 eeready -->
Při konfiguraci profilu zařízení (**Konfigurace zařízení** > **Profily**) vyberete profil zařízení, například iOS. Tento profil přiřadíte ke skupině, která obsahuje zařízení s iOSem a zařízení s jiným systémem. Počet v grafu zobrazuje, že profil je použitý u zařízení s iOSem *a* u zařízení s jiným systémem (**Konfigurace zařízení** > **Profily** > vyberte existující profil > **Přehled**). Když vyberete graf na kartě **Přehled** zobrazí se v části **Stav zařízení** seznam všech zařízení ve skupině, nikoli pouze seznam zařízení s iOSem. 

Po této aktualizaci bude graf (**Konfigurace zařízení** > **Profily** > vyberte existující profil > **Přehled**) zobrazovat pouze počet pro konkrétní profil zařízení. Pokud například konfigurační profil zařízení platí pro zařízení s iOSem, zobrazí se v grafu pouze počet zařízení s iOSem. Když vyberete graf a otevřete **Stav zařízení**, zobrazí se pouze zařízení s iOSem.

Během přípravy této aktualizace je uživatelský graf dočasně nedostupný. 


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

<!-- 1802 start -->

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nové nastavení tiskárny pro vzdělávací profily <!-- 1308900 -->

Pro vzdělávací profily bude nové nastavení k dispozici v kategorii **Tiskárny**: **Tiskárny**, **Výchozí tiskárna**, **Přidat nové tiskárny**.

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


