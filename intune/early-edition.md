---
title: "Časná edice"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 973408b292261b86f0a49bfaf4c786d6a6dacf28
ms.sourcegitcommit: b8d3f8da6d8c2bd5d6140d538193a02d5875aefb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="the-early-edition-for-microsoft-intune---october-2017"></a>Časná edice Microsoft Intune – říjen 2017

**Časná edice** poskytuje seznam funkcí, které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány v omezené míře a můžou podléhat změnám. Nesdílejte tyto informace mimo společnost. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a můžou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moct zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se na příslušný kontakt pro skupinu produktů společnosti Microsoft.

Tato stránka se pravidelně aktualizuje. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.

> [!Note]
>Následující změny v Intune jsou ve vývoji. Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->



## <a name="intune-in-the-azure-portal"></a>Intune na portálu Azure Portal

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Webové stránky Azure Active Directory můžou vyžadovat aplikaci Intune Managed Browser a podporovat jednotné přihlašování pro Managed Browser (Public Preview) <!-- 710595 -->   
Pomocí Azure Active Directory (Azure AD) budete moct přístup k webovým stránkám na mobilních zařízeních omezit na aplikaci Intune Managed Browser. V Managed Browseru zůstanou data webových stránek zabezpečená a oddělená od osobních dat koncových uživatelů. Kromě toho bude Managed Browser podporovat možnosti jednotného přihlašování pro weby chráněné pomocí Azure AD. Přihlášení k Managed Browseru nebo jeho používání na zařízení s jinou aplikací, kterou spravuje Intune, umožňuje, aby měl Managed Browser přístup k podnikovým webům chráněným pomocí Azure AD, aniž by uživatel musel zadávat své přihlašovací údaje. Tato funkce se vztahuje na weby jako Outlook Web Access (OWA) a SharePoint Online i na jiné podnikové weby jako prostředky v intranetu, ke kterým se přistupuje prostřednictvím proxy aplikace Azure.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Řešení potíží s registrací  <!--- 746324 --->  
Pracovní prostor Řešení potíží zobrazí problémy s registrací uživatelů. Podrobnosti o problému a navrhované nápravné kroky můžou správcům a pracovníkům technické podpory pomoct problém vyřešit. Některé problémy s registrací nejsou zaznamenané a k některým chybám nemusí návrhy k odstranění problému existovat.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Správci teď můžou konfigurovat nastavení brány firewall na zařízení pomocí profilu konfigurace zařízení <!-- 951708 -->   
Správci můžou zapnout bránu firewall pro zařízení a také nakonfigurovat různé protokoly pro doménové, privátní a veřejné sítě.  Tato nastavení brány firewall najdete v profilu „Ochrana koncového bodu“.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Ochrana Application Guard v programu Windows Defender pomáhá chránit zařízení před nedůvěryhodnými weby, jak je definuje vaše organizace <!-- 958257 -->   
Správci můžou definovat weby jako „důvěryhodné“ nebo „podnikové“ pomocí pracovního postupu Windows Information Protection nebo nového profilu „Ohraničení sítě“ v konfiguracích zařízení. Všechny weby, které nejsou uvedené v důvěryhodném ohraničení sítě zařízení s 64bitovovými Windows 10, se místo zobrazení v prohlížeči Microsoft Edge otevřou v prohlížeči virtuálního počítače Hyper-V.

Application Guard najdete v konfiguračních profilech zařízení v profilu „Ochrana koncového bodu“. Tam můžou správci konfigurovat interakce mezi virtualizovaným prohlížečem a hostitelským počítačem, nedůvěryhodné a důvěryhodné weby a ukládání dat vygenerovaných ve virtualizovaném prohlížeči. Pokud chcete Application Guard na zařízení používat, musí se nejdříve nakonfigurovat ohraničení sítě. Je důležité, aby se pro zařízení definovalo jenom jedno ohraničení sítě.  

### <a name="windows-defender-application-guard-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Ochrana Application Guard v programu Windows Defender ve Windows 10 Enterprise poskytuje režim k důvěřování jenom autorizovaným aplikacím <!-- 1031096 -->    
Protože každý den vznikají tisíce nových škodlivých souborů, nemusí už boj proti malwaru pomocí antivirové ochrany využívající podpisy souborů poskytovat dostatečnou obranu před novými útoky. Pomocí ochrany Application Guard v programu Windows Defender ve Windows 10 Enterprise můžete konfiguraci zařízení změnit z režimu, kdy jsou aplikace důvěryhodné, pokud nejsou blokované antivirovou ochranou nebo jiným řešením zabezpečení, na režim, kdy operační systém důvěřuje jenom aplikacím autorizovaným vaší organizací. Důvěryhodnost se aplikacím přiřazuje v ochraně Application Guard v programu Windows Defender.

Pomocí Intune můžete zásady řízení aplikací nakonfigurovat v režimu „pouze audit“ nebo v režimu vynucení. Aplikace spuštěné v režimu „pouze audit“ nebudou blokované. Režim „pouze audit“ zapisuje všechny události do protokolů místního klienta. Můžete také nakonfigurovat, jestli je povolené spouštět jenom součásti Windows a aplikace pro Windows Store, nebo jestli se budou moct spouštět i další aplikace s dobrou reputací, jak je definuje Intelligent Security Graph.

### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Nová stránka stavu registrace pro registrace Windows 10 <!--1063201-->    
Teď můžete nakonfigurovat pozdrav, který se zobrazí, když uživatelé zaregistrují zařízení s Windows 10. Pomocí **Obrazovky stavu registrace** nakonfigurujte vlastní zprávu a hypertextový odkaz, které se mají zobrazit koncovým uživatelům, když zaregistrují zařízení s Windows 10.  **Obrazovka stavu registrace** také koncové uživatele informuje o průběhu nastavení zásad, která se na jejich zařízení aplikují.  

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Ochrana Exploit Guard v programu Windows Defender je nová sada funkcí pro prevenci neoprávněných vniknutí pro Windows 10 <!-- 1063615 -->   
Ochrana Exploit Guard v programu Windows Defender obsahuje vlastní pravidla pro snížení zneužitelnosti aplikací, brání hrozbám z maker skriptů, automaticky blokuje síťová připojení k IP adresám se špatnou reputací a může zabezpečit data před ransomwarem a neznámými hrozbami. Ochrana Exploit Guard v programu Windows Defender se skládá z těchto součástí:

- **Omezení možností útoků** poskytuje pravidla, která vám umožní zabránit hrozbám z maker, skriptů a e-mailů.
- **Řízený přístup ke složkám** automaticky blokuje přístup k obsahu chráněných složek.
- **Filtrování sítě** blokuje odchozí připojení z jakékoli aplikace k IP nebo doméně se špatnou reputací.
- **Ochrana Exploit Protection** poskytuje omezení paměti, toku řízení a zásad, která se dají využít k ochraně aplikace před zneužitím.

### <a name="app-conditional-launch-support----1193313---"></a>Podpora podmíněného spouštění aplikací <!-- 1193313 -->
Správci IT teď můžou pomocí portálu pro správu Azure nastavit požadavek, aby se prostřednictvím správy mobilních aplikací (MAM) při spouštění aplikace místo číselného kódu PIN vynutilo heslo. Při takové konfiguraci bude uživatel muset po zobrazení výzvy nastavit a používat heslo, aby získal přístup k aplikacím s podporou MAM. Heslo je definované jako číselný kód PIN s aspoň jedním speciálním znakem nebo velkým/malým písmenem. Tato verze Intune tuto funkci povolí **jenom v iOSu**. Intune podporuje heslo podobným způsobem jako číselný kód PIN, stanovuje minimální délku a povoluje opakování znaků a sekvencí. Tato funkce vyžaduje zapojení aplikací (např. WXP, Outlook, Managed Browser, Yammer), aby integrovaly sadu Intune APP SDK s kódem pro tuto funkci místo vynucení nastavení hesla v cílových aplikacích.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Číslo verze aplikace pro obchodní aplikace ve zprávě o stavu instalace zařízení <!-- 1233999 -->  
Zpráva o stavu instalace zařízení zobrazí číslo verze aplikace u obchodních aplikací pro iOS a Android. Tyto informace můžete využít k řešení potíží s aplikacemi nebo nalezení zařízení, na kterých běží zastaralé verze aplikací.

### <a name="co-management-for-windows-10-devices-----124445---"></a>Společná správa zařízení s Windows 10  <!-- 124445 -->
Společná správa je řešení, které představuje most mezi tradiční a moderní správou a poskytne vám cestu k přechodu pomocí přístupu ve fázích. V základu je společná správa řešením, kdy jsou zařízení s Windows 10 současně spravovaná pomocí Configuration Manageru a Microsoft Intune a také připojená k Active Directory (AD) a Azure Active Directory (Azure AD).  Tato konfigurace vám poskytne cestu k modernizaci v průběhu času a tempem, které je nejvhodnější pro vaši organizaci, pokud nemůžete přesunout všechno najednou.  

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Nastavení přístupu pro aplikace pomocí opravy minimálního zabezpečení Androidu na zařízení<!-- 1278463 -->   
Správce bude moct definovat minimální opravu zabezpečení Androidu, která musí být na zařízení nainstalovaná, aby zařízení pod spravovaným účtem získalo přístup ke spravované aplikaci.

> [!Note]  
> Tato funkce omezuje jenom opravy zabezpečení vydané společností Google na zařízeních s Androidem 6.0 a novějším.

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nová nastavení omezení pro zařízení s Windows 10      <!-- 1308850 -->
-    Zasílání zpráv (jenom mobilní) – zakázání testování nebo zpráv MMS
-    Heslo – nastavení k povolení standardu FIPS a použití sekundárních zařízení Windows Hello k ověřování 
-    Zobrazit – nastavení k zapnutí nebo vypnutí škálování GDI pro starší verze aplikací


### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Omezení zařízení s Windows 10 na režim veřejného terminálu <!-- 1308872 -->   
Uživatele zařízení s Windows 10 budete moct omezit na režim veřejného terminálu, který uživatele omezuje na sadu předdefinovaných aplikací.  To uděláte tak, že vytvoříte profil omezení zařízení s Windows 10 a nastavíte režim Veřejný terminál.

Režim veřejného terminálu podporuje dva režimy: **s jednou aplikací** (umožňuje uživateli spustit jenom jednu aplikaci) nebo **s více aplikacemi** (povoluje přístup k sadě aplikací).  Definujete uživatelský účet a název zařízení a tím se určí podporované aplikace.  Když je uživatel přihlášený, je omezený na definované aplikace.  Další informace najdete v článku [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Režim veřejného terminálu vyžaduje:

- Intune musí být autoritou pro správu mobilních zařízení (MDM).
- Aplikace už musí být v cílovém zařízení nainstalované.
- Zařízení musí být [správně zřízené](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nový profil konfigurace zařízení pro vytvoření ohraničení sítě <!-- 1311967 -->   
Vytvořili jsme profil konfigurace zařízení nazvaný **Ohraničení sítě**, který najdete u ostatních profilů konfigurace zařízení. Tento profil slouží k definování online prostředků, které chcete, aby se považovaly za podnikové a důvěryhodné. Ohraničení sítě pro zařízení musíte definovat *před tím*, než na něm bude možné používat funkce jako ochrana Application Guard v programu Windows Defender a Windows Information Protection. Je důležité, aby se pro každé zařízení definovalo jenom jedno ohraničení sítě.

Můžete definovat podnikové cloudové prostředky, rozsahy IP adres a interní proxy servery, které se mají považovat za důvěryhodné. Po definování můžou ohraničení sítě využívat ostatní funkce jako ochrana Application Guard v programu Windows Defender a Windows Information Protection.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Další dvě nastavení pro Antivirovou ochranu v programu Windows Defender <!-- 1338409 -->  
**Úroveň blokování souborů**

| | |
|---|---|
| Nenakonfigurováno | Nastavení **Nenakonfigurováno** používá výchozí úroveň blokování Antivirové ochrany v programu Windows Defender a zajišťuje silnou detekci bez zvýšeného rizika detekování legitimních souborů. |
| Vysoká | Nastavení **Vysoká** aplikuje silnou úroveň zjišťování.
| Vysoká +  | Nastavení **Vysoká +** poskytuje vysokou úroveň s dalšími ochrannými opatřeními, která můžou mít vliv na výkon klienta.
| Žádná tolerance  | Nastavení **Žádná tolerance** blokuje všechny neznámé spustitelné soubory. |

I když je to nepravděpodobné, může nastavení **Vysoká** způsobit, že se detekují některé legitimní soubory.
Doporučujeme nastavit úroveň blokování souborů na výchozí hodnotu **Nenakonfigurováno**.

**Prodloužení časového limitu pro kontrolu souboru v cloudu**   

| | |
|--|--|
| Počet sekund (0–50) | Zadejte maximální dobu, po kterou má Antivirová ochrana v programu Windows Defender blokovat soubor při čekání na výsledek z cloudu. Výchozí doba je 10 sekund: dodatečná doba, kterou tady zadáte (až 50 sekund), se k těmto 10 sekundám přičte. Ve většině případů trvá kontrola mnohem kratší dobu než maximální. Prodloužení doby umožňuje, aby cloud podezřelé soubory důkladně prozkoumal. Doporučujeme, abyste toto nastavení povolili a zadali aspoň dalších 20 sekund. |


### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Podpora certifikační autority (CA) Symantec Cloud <!-- 1333638 -->    
Intune teď podporuje certifikační autoritu Symantec Cloud. To umožňuje, aby Intune Certificate Connector vystavil certifikáty PKCS z certifikační autority Symantec Cloud do zařízení spravovaných pomocí Intune. Pokud už Intune Certificate Connector používáte s certifikační autoritou (CA) Microsoft, můžete existující nastavení Intune Certificate Connectoru využít k přidání podpory pro certifikační autoritu Symantec.



### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Přidáno Citrix VPN pro zařízení s Windows 10 <!-- 1512457 -->  
Zákazník bude moct pro svá zařízení s Windows 10 nakonfigurovat Citrix VPN. Citrix VPN můžete zvolit ze seznamu *Vyberte typ připojení* v okně **Základní síť VPN** při konfiguraci VPN pro Windows 10 a novější.

> [!Note]
> Konfigurace Citrix existovala pro iOS a Android.





<!-- the following are present prior to 1710 -->

### <a name="google-play-protect-support-on-android----908720----"></a>Podpora Google Play Protect na Androidu <!-- 908720  -->  
S vydáním verze Android Oreo zavádí Google sadu bezpečnostních funkcí s názvem Google Play Protect, které uživatelům a organizacím umožňují provozovat zabezpečené aplikace a zabezpečené image Androidu. Intune bude funkce Google Play Protect podporovat, a to včetně vzdáleného ověření SafetyNet.  Správci můžou nastavit požadavky na zásady dodržování předpisů, které vyžadují, aby funkce Google Play Protect byla nakonfigurovaná a funkční. Nastavení **Ověření zařízení SafetyNet** vyžaduje, aby se zařízení připojilo ke službě Googlu, která ověří, že je zařízení v pořádku a není ohrožené. Správci můžou rovněž nastavením konfiguračního profilu pro Android for Work vyžádat, aby nainstalované aplikace byly ověřeny pomocí služeb Google Play.  Podmíněný přístup může uživatelům zablokovat přístup k firemním prostředkům, pokud zařízení nesplňuje požadavky na Google Play Protect. 


### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Podpora zásad upgradu edice Windows 10 <!-- 903672(archived), 1119689 -->  
Budete moci vytvořit zásady upgradu edice Windows 10, které zařízení s Windows 10 upgradují na Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education a Windows 10 Professional Education N. Podrobnosti o upgradech edic Windows 10 najdete v článku [Jak nakonfigurovat upgrady edicí Windows 10](edition-upgrade-configure-windows-10.md).





<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--846515---"></a>Akce při nedodržení předpisů  <!--730266  846515 -->     
*Akce při nedodržení předpisů* jsou novou funkcí zásad dodržování předpisů. Umožní vám provádět akce na zařízeních, která nedodržují předpisy. Můžete zadat jednu nebo více akcí a určit časové období, během kterého se tyto akce musí provést. Třeba uživatelům zařízení, která nedodržují předpisy, můžete poslat e-mailem oznámení, hned jak zařízení přestane předpisy dodržovat. Nebo pomocí podmíněného přístupu můžete takovým zařízením zablokovat přístup k prostředkům společnosti po 3denním období odkladu.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Podpora Androidu for Work pro Lookout <!-- 1087312 -->   
Při použití aplikace Lookout for Work bude konektor Intune s Lookoutem podporovat zařízení s Androidem for Work. Aplikaci Lookout můžete nasadit uvnitř nebo vně kontejneru.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune App Protection a nástroje pro vývoj Citrix MDX <!-- 709185 -->
Můžete spravovat zařízení a aplikace s kombinací Citrix XenMobile MDX a Microsoft Intune. To umožňuje spravovat aplikace pomocí zásad ochrany aplikací Intune při použití technologie mVPN společnosti Citrix.

Můžete najít úložiště kódu, které obsahuje Intune App Wrapping Tool a sadu Intune App SDK pro iOS a Android, a využít integraci s technologií Citrix MDX mVPN.

#### <a name="how-integration-with-intune-works"></a>Jak integrace s Intune funguje
Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých služba Zimperium běží. Zásady podmíněného přístupu EMS založené na posouzení rizika službou Zimperium můžete nakonfigurovat prostřednictvím zásad dodržování předpisů zařízení služby Intune, kterými můžete na základě odhalených hrozeb u zařízení, které nedodržují předpisy, povolit nebo zablokovat přístup k firemním prostředkům.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Podpora vysoké dostupnosti místního konektoru Exchange Connector  <!-- 676614 -->   
U místního konektoru Exchange Connector máte možnost mít několik rolí serveru pro klientský přístup (CAS). Například pokud hlavní server pro klientský přístup selže, konektor Exchange Connector obdrží výzvu, aby využíval jiné servery pro klientský přístup. Tato funkce zajišťuje, že se služba nepřeruší.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Sada System Center Operations Manager Management Pack pro konektor Exchange Connector <!-- 885457 -->   
Pro pomoc s analýzou protokolů konektoru Exchange Connector bude dostupná sada System Center Operations Manager Management Pack pro konektor Exchange Connector. Pokud potřebujete řešit potíže, tento Management Pack poskytuje různé možnosti monitorování Intune.


## <a name="intune-apps"></a>Aplikace Intune


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Přesměrování uživatelů macOS na naši novou aplikaci Portál společnosti <!--1380728-->   
Když se koncový uživatel přihlásí k webu Portál společnosti, aby zaregistroval svoje zařízení s macOS, bude přesměrován na to, aby proces dokončil stažením nové aplikace Portál společnosti pro macOS. K tomu dojde na zařízeních s macOS používajících OS X El Capitan 10.11 nebo novější. 

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Podpora ověřování na základě certifikátu v Portálu společnosti pro iOS <!--1029830-->
Přidali jsme podporu ověřování pomocí certifikátů v aplikaci Portál společnosti pro iOS. Uživatelé s ověřováním pomocí certifikátů zadají svoje uživatelské jméno a pak klepnou na odkaz „Přihlásit se pomocí certifikátu“. V aplikacích Portál společnosti pro Android a Windows je už ověřování pomocí certifikátů podporované. Další informace najdete na stránce o [přihlášení do aplikace Portál společnosti](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Aplikace, které jsou dostupné s registrací nebo bez registrace, lze nyní nainstalovat bez výzvy k registraci <!-- 1334712 -->
Firemní aplikace, které byly u aplikace Portál společnosti pro Android zpřístupněny s registrací nebo bez registrace, lze nainstalovat bez výzvy k registraci.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Podpora Intune Managed Browser pro iOS a Android <!-- 1374196 -->
Od října 2017 bude aplikace Intune Managed Browser pro Android podporovat jen zařízení se systémem Android 4.4 a novější. Aplikace Intune Managed Browser pro iOS bude podporovat jen zařízení se systémem iOS 9.0 a novější. Starší verze systému Android a iOS budou moct Managed Browser dál používat, ale nepůjde do nich nainstalovat nové verze této aplikace a nebudou mít přístup ke všem jejím možnostem. Doporučujeme vám tato zařízení aktualizovat na podporovanou verzi operačního systému.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Vylepšená chybová zpráva, když uživatel dosáhne maximálního povoleného počtu zařízení k registraci <!-- 1270370 -->
Místo obecné chybové zprávy se koncovým uživatelům zobrazí popisná chybová zpráva, na kterou se dá reagovat: „Zaregistrovali jste maximální počet zařízení, který povoluje váš IT správce. Odeberte prosím zaregistrované zařízení, nebo se obraťte s žádostí o pomoc na IT správce.“




## <a name="notices"></a>Sdělení

### <a name="device-and-app-management-integration----677972---"></a>Integrace správy zařízení a aplikací <!-- 677972 -->   
Když jsou teď správa mobilních zařízení (MDM) i správa mobilních aplikací (MAM) Intune přístupné z portálu Azure Portal, začala služba Intune integrovat způsoby práce IT správců týkající se správy aplikací a zařízení. Tyto změny jsou zaměřené na zjednodušení způsobu správy zařízení a aplikací.

Další informace o změnách MDM a MAM najdete na [blogu týmu podpory Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).




### <a name="see-also"></a>Související témata
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).
