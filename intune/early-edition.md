---
title: "Časná edice"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: abb5612545174e3fd134c38fb763e02d379b50d0
ms.sourcegitcommit: b330045a4f9a807e6e2772c4ed4e1e1148e1f1f9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/13/2017
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
Správci IT teď můžou pomocí portálu pro správu Azure nastavit požadavek, aby se prostřednictvím správy mobilních aplikací (MAM) při spouštění aplikace místo číselného kódu PIN vynutilo heslo. Při takové konfiguraci bude uživatel muset po zobrazení výzvy nastavit a používat heslo, aby získal přístup k aplikacím s podporou MAM. Heslo je definované jako číselný kód PIN s aspoň jedním speciálním znakem nebo velkým/malým písmenem. Tato verze Intune tuto funkci povolí **jenom v iOSu**. Intune podporuje heslo podobným způsobem jako číselný kód PIN, stanovuje minimální délku a povoluje opakování znaků a sekvencí. Tato funkce vyžaduje zapojení aplikací (např. WXP, Outlook, Managed Browser, Yammer), aby integrovaly sadu Intune APP SDK s kódem pro tuto funkci místo nastavení hesla k vynucení v cílových aplikacích.

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


### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Vylepšení pracovního postupu instalace zařízení na Portálu společnosti <!--1490692-->  
Zlepšujeme pracovní postup instalace zařízení v aplikaci Portál společnosti pro Android. Jazyk bude uživatelsky přívětivější a přizpůsobenější potřebám vaší společnosti a tam, kde to bude možné, také zkombinujeme obrazovky. 

### <a name="block-unsupported-samsung-knox-device-activation------1490695----"></a>Blokování aktivace nepodporovaných zařízení Samsung KNOX  <!--- 1490695 --->  
Během registrace MDM se aplikace Portál společnosti pokusí aktivovat Samsung KNOX jenom v případě, že je zařízení uvedené v [seznamu podporovaných zařízení KNOX](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Toto omezení pomáhá předejít chybám aktivace KNOX, které brání v registraci MDM. Zařízení, která nepodporují aktivaci Samsung KNOX, se zaregistrují jako standardní zařízení s Androidem. Některá čísla modelů zařízení Samsung mohou podporovat KNOX, některá nemusí. Než zařízení Samsung koupíte a nasadíte, ověřte si u prodejce, jestli je kompatibilní se systémem Knox.

Následující modely zařízení Samsung nepodporují KNOX a aplikace Portál společnosti pro Android je nezaregistruje jako nativní zařízení s Androidem:

| **Název zařízení** | **Číslo modelu zařízení** |
| --- | --- |
| Galaxy A3 | SM-A300G<br>SM-A310Y<br>SM-A320FL |
| Galaxy A5 | SM-A500G |
| Galaxy Alpha | SM-G850M |
| Galaxy Avant | SM-G386T |
| Galaxy C9/C9 Pro | SM-C900F |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime | SM-G530M |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110F |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M<br>SM-J320W8 |
| Galaxy J5 | SM-J500G |
| Galaxy J7 | SM-J710F |
| Galaxy J7 Prime | SM-J727T1 |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 5 | SM-N920G<br>SM-N920I<br>SM-N920W8 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy NotePRO 12.2&quot; | SM-P902 |
| Galaxy On5 | SM-G570MSM-G570Y |
| Galaxy On7 | SM-G600FY<br>SM-G610M<br>SM-G610Y |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Active | GT-I9295 |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W<br>SM-G900M |
| Galaxy S5 Neo | SM-G903M |
| Galaxy S6 Edge | 404SCSM-G925I<br>SM-G928G |
| Galaxy Tab A 7.0&quot; | SM-T280SM-T285 |
| Galaxy Tab A 9.7&quot; | SM-P555M |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116SM-T210SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |


### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Přidáno Citrix VPN pro zařízení s Windows 10 <!-- 1512457 -->  
Zákazník bude moct pro svá zařízení s Windows 10 nakonfigurovat Citrix VPN. Citrix VPN můžete zvolit ze seznamu *Vyberte typ připojení* v okně **Základní síť VPN** při konfiguraci VPN pro Windows 10 a novější.

> [!Note]
> Konfigurace Citrix existovala pro iOS a Android.





<!-- the following are present prior to 1710 -->

### <a name="google-play-protect-support-on-android----908720----"></a>Podpora Google Play Protect na Androidu <!-- 908720  -->  
S vydáním verze Android Oreo zavádí Google sadu bezpečnostních funkcí s názvem Google Play Protect, které uživatelům a organizacím umožňují provozovat zabezpečené aplikace a zabezpečené image Androidu. Intune bude funkce Google Play Protect podporovat, a to včetně vzdáleného ověření SafetyNet.  Správci můžou nastavit požadavky na zásady dodržování předpisů, které vyžadují, aby funkce Google Play Protect byla nakonfigurovaná a funkční. Nastavení **Ověření zařízení SafetyNet** vyžaduje, aby se zařízení připojilo ke službě Googlu, která ověří, že je zařízení v pořádku a není ohrožené. Správci můžou rovněž nastavením konfiguračního profilu pro Android for Work vyžádat, aby nainstalované aplikace byly ověřeny pomocí služeb Google Play.  Podmíněný přístup může uživatelům zablokovat přístup k firemním prostředkům, pokud zařízení nesplňuje požadavky na Google Play Protect. 

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Uživatelům zařízení s Androidem lze zabránit ve změně data a času <!-- 1333292 -->
Pomocí [vlastních zásad zařízení s Androidem](custom-settings-android.md) můžete uživatelům zabránit, aby na zařízení změnili datum a čas.
Uděláte to tak, že nakonfigurujete vlastní zásadu pro Android s identifikátorem URI nastavení ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange. Nastavte tuto zásadu na **TRUE** a pak ji přiřaďte požadovaným skupinám.

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Zobrazení přiřazených zásad ochrany aplikací kvůli řešení problémů <!--  1475003 -->
V této nadcházející verzi bude do rozevíracího seznamu **Přiřazení**, který je dostupný v okně pro řešení potíží, přidána možnost **Zásady ochrany aplikací**. Výběrem zásad ochrany aplikací teď můžete zobrazit zásady ochrany aplikací přiřazené vybraným uživatelům.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Vytvoření aplikací pro iOS omezených na určité regionální Apple App Story <!-- 1281692 -->
Během vytváření spravované aplikace pro Apple App Store budete moci určit národní prostředí země.

> [!NOTE]  
> V současnosti můžete vytvářet jen spravované aplikace pro Apple App Store, které se nacházejí v americkém App Storu.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Výběr regionálního Apple App Storu pro synchronizaci aplikací VPP <!-- 1332311 -->  
Při nahrávání tokenu VPP (Volume Purchase Program) budete moct nakonfigurovat regionální VPP Store. Intune synchronizuje aplikace VPP pro všechna národní prostředí z určeného regionálního VPP Storu.

> [!NOTE]  
> V současnosti synchronizuje Intune jen aplikace VPP z regionálního VPP Storu, které se shodují s národním prostředím Intune, ve kterém byl tenant Intune vytvořen.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Aktualizace aplikací VPP pro iOS licencovaných pro uživatele a zařízení <!-- 1305564 -->  
Token VPP pro iOS budete moci nakonfigurovat tak, aby se prostřednictvím služby Intune aktualizovaly všechny aplikace zakoupené pro tento token. Intune zjistí aktualizace aplikací VPP v App Storu a automaticky je nabídne zařízení, jakmile se zařízení ohlásí.

### <a name="new-settings-for-windows-10-team-device-restriction-profile------1308838----"></a>Nová nastavení pro profil omezení zařízení s Windows 10 Team <!--- 1308838  -->
Přidáváme spoustu nových nastavení do profilu omezení zařízení s Windows 10 Team, která vám pomůžou ovládat zařízení Surface Hub.
Další informace o tomto profilu najdete v článku [Nastavení omezení zařízení s Windows 10 Team](device-restrictions-windows-10-teams.md).

### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Podpora zásad upgradu edice Windows 10 <!-- 903672(archived), 1119689 -->  
Budete moci vytvořit zásady upgradu edice Windows 10, které zařízení s Windows 10 upgradují na Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education a Windows 10 Professional Education N. Podrobnosti o upgradech edic Windows 10 najdete v článku [Jak nakonfigurovat upgrady edicí Windows 10](edition-upgrade-configure-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Vzdálená podpora zařízení s Windows a Windows Mobile <!-- 1070473 -->    
Intune vám pomocí samostatně zakoupeného softwaru [TeamViewer](https://www.teamviewer.com) umožní poskytovat vzdálenou pomoc uživatelům, kteří používají zařízení s Windows a Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Kontrola zařízení pomocí programu Windows Defender <!-- 1280988  1280990   -->
Na spravovaných zařízeních s Windows 10 budete pomocí Antivirové ochrany v programu Windows Defender moci provést **rychlou kontrolu**, **úplnou kontrolu** a **aktualizaci signatur**. V okně s přehledem zařízení zvolte akci, která se má na zařízení spustit. Před odesláním příkazu do zařízení budete vyzváni k potvrzení. 

**Rychlá kontrola:** Při rychlé kontrole se kontrolují místa, kde se registruje spuštění malwaru, jako jsou klíče registru a známé spouštěcí složky Windows. Rychlá kontrola trvá průměrně pět minut. V kombinaci s nastavením **trvalé ochrany v reálném čase**, která soubory kontroluje při otevření, zavření a vždy, když uživatel přejde do nějaké složky, poskytuje rychlá kontrola ochranu před malwarem, který se může nacházet v systému nebo jádru. Uživatelé uvidí na svých zařízeních výsledky kontroly potom, co se dokončí. 

**Úplná kontrola:** Úplnou kontrolu využijete u zařízení napadených malwarem, kdy umožňuje zjistit, jestli v zařízení nezůstaly nějaké neaktivní komponenty, které vyžadují důkladnější vyčištění. Slouží také ke spuštění kontrol na vyžádání. Úplná kontrola může trvat hodinu. Uživatelé uvidí na svých zařízeních výsledky kontroly potom, co se dokončí. 

**Aktualizace signatur:** Tímto příkazem se u Antivirové ochrany v programu Windows Defender aktualizují definice a signatury malwaru. Tím se zajistí účinnost Antivirové ochrany v programu Windows Defender při zjišťování malwaru. Tato funkce je určená jen pro zařízení s Windows 10 a očekává, že je zařízení připojené k internetu. 

### <a name="bitlocker-device-configuration----1397398---"></a>Konfigurace zařízení s BitLockerem <!-- 1397398 -->  
Možnost **Šifrování Windows > Základní nastavení** bude obsahovat nové nastavení **Upozornění na jiné šifrování disku**, které vám umožní zakázat [výzvu s upozorněním](https://docs.microsoft.com/en-us/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) na jiné šifrování disku, které se na zařízení uživatele může používat.  Tato výzva s upozorněním vyžaduje svolení uživatele před nastavením BitLockeru na zařízení a blokuje jeho nastavení, dokud není potvrzené koncovým uživatelem.  Toto nové nastavení zakazuje upozornění koncového uživatele.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Portál společnosti pro Windows 8.1 a Windows Phone 8.1 přechází do udržovacího režimu <!--1428681-->
Počínaje říjnem 2017 přejdou aplikace Portál společnosti pro Windows 8.1 a Windows Phone 8.1 do udržovacího režimu. To znamená, že tyto aplikace a existující scénáře (například registrace a dodržování předpisů) budou pro tyto platformy nadále podporovány. Tyto aplikace budu pořád dostupné ke stažení přes existující vydávací kanály, jako je Microsoft Store. 

Jakmile tyto aplikace budou v udržovacím režimu, budou dostávat jen důležité aktualizace zabezpečení. Pro tyto aplikace se už nebudou vydávat další aktualizace ani funkce. Kvůli novým funkcím doporučujeme zařízení aktualizovat na Windows 10 nebo Windows 10 Mobile. 

###  <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Blokování kopírování a vkládání mezi pracovním a osobním profilem pro Android for Work <!-- 1098994 -->   
Pracovní profil pro Android for Work budete moct nakonfigurovat tak, aby bylo zablokované kopírování a vkládání mezi pracovními a osobními aplikacemi. Toto nové nastavení najdete v profilu **Omezení zařízení** pro platformu **Android for Work** v **Nastavení pracovního profilu**.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nové chování aplikace Portál společnosti pro Android s pracovními profily <!---1485783--->
Při registraci zařízení s Androidem for Work s pracovním profilem se o správu úloh na tomto zařízení stará aplikace Portál společnosti v pracovním profilu. Pokud v osobním profilu nepoužíváte nějakou aplikaci s podporou MAM, neslouží už aplikace Portál společnosti k žádnému účelu. Kvůli příjemnější práci v pracovním profilu Intune po úspěšné registraci pracovního profilu automaticky skryje osobní aplikaci Portál společnosti.

Aplikaci Portál společnosti pro Android můžete v osobním profilu kdykoli povolit tak, že přejdete na [Portál společnosti v Obchodě Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) a klepnete na **Povolit**.

### <a name="intune-mam--outlook-for-android-add-ins-----1450688---"></a>Doplňky Intune MAM a Outlook pro Android <!-- 1450688 -->
V příštích týdnech oznámí tým Office doplňky pro Outlook na Androidu. Tato sada doplňkových funkcí už existuje v Outlooku pro Windows, iOS, web a Mac. Protože se doplňky spravují přes Exchange, budou uživatelé moci kopírovat a sdílet data a zprávy mezi Outlookem a nespravovanými doplňkovými aplikacemi, dokud správce Exchange přístup k doplňkům nevypne. 

Pokud chcete spravovat přístupová oprávnění uživatele k doplňkům, ve spolupráci se správcem Exchange zajistěte, aby se zásady ochrany dat MAM vztahovaly na doplňky.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pokud už máte zásady Exchange nastavené tak, že zakazují instalaci doplňků bokem nebo běžnou instalaci doplňků, nemusíte číst dál. Vaše zásady MAM se uplatní podle očekávání. Pokud ale máte zásady MAM nastavené tak, že zakazují operace vyjmutí, kopírování a vložení v Outlooku na Androidu a nenastavili jste zásady doplňků v Exchangi, měli byste vědět, že uživatelé budou moci do Outlooku instalovat doplňky. Tyto doplňky můžou mít přístup k textu, předmětu a jiným vlastnostem zprávy. Uživatelům můžete v instalaci doplňků zabránit tak, že správce Exchange požádáte o odebrání rolí Moje aplikace z Marketplace a Moje vlastní aplikace.

Tato změna nastavení v Exchangi se uplatní na Outlook pro Windows, iOS, web, Mac a mobilní zařízení. 

#### <a name="what-do-i-need-to-do"></a>Co musím udělat?
Ještě dnes zkontrolujte zásady Exchange. Informujte pracovníky IT oddělení a helpdesku. S konkrétními otázkami nebo obavami se obraťte na náš tým podpory. 

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Do datového modelu datového skladu Intune byla přidána kolekce entit přidružení uživatelů a zařízení <!-- 1187917 -->
Pomocí informací o přidružení uživatelů a zařízení, které přidružují kolekce entit uživatelů a zařízení, budete moci vytvářet sestavy a vizualizace dat. Tento datový model lze zpřístupnit přes soubor Power BI (PBIX) načtený ze stránky Datový sklad v Intune, přes koncový bod OData nebo vývojem vlastního klienta.




<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--846515---"></a>Akce při nedodržení předpisů  <!--730266  846515 -->     
*Akce při nedodržení předpisů* jsou novou funkcí zásad dodržování předpisů. Umožní vám provádět akce na zařízeních, která nedodržují předpisy. Můžete zadat jednu nebo více akcí a určit časové období, během kterého se tyto akce musí provést. Třeba uživatelům zařízení, která nedodržují předpisy, můžete poslat e-mailem oznámení, hned jak zařízení přestane předpisy dodržovat. Nebo pomocí podmíněného přístupu můžete takovým zařízením zablokovat přístup k prostředkům společnosti po 3denním období odkladu.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nová sestava obsahující seznam zařízení se staršími verzemi iOSu   <!-- 1352223 -->
Sestava **zařízení se zastaralým iOSem** bude k dispozici z pracovního prostoru **Aktualizace softwaru**. V sestavě můžete zobrazit seznam zařízení s iOSem pod dohledem, na která byla zacílena zásada aktualizace iOSu a pro která jsou k dispozici aktualizace. Pro každé zařízení můžete zobrazit stav, proč nebylo automaticky aktualizováno. 

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>Nová nastavení pro profil omezení zařízení s Windows 10
<!--- 978575, 1308849, -->
Do profilu omezení zařízení s Windows 10 v kategorii filtru SmartScreen v programu Windows Defender přidáváme nová nastavení.

Podrobnosti o profilu omezení zařízení s Windows 10 najdete v tématu [Nastavení omezení pro zařízení Windows 10 a novější]( device-restrictions-windows-10.md).

### <a name="android-for-work-support-for-lookout----1087312---"></a>Podpora Androidu for Work pro Lookout <!-- 1087312 -->   
Při použití aplikace Lookout for Work bude konektor Intune s Lookoutem podporovat zařízení s Androidem for Work. Aplikaci Lookout můžete nasadit uvnitř nebo vně kontejneru.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune App Protection a nástroje pro vývoj Citrix MDX <!-- 709185 -->
Můžete spravovat zařízení a aplikace s kombinací Citrix XenMobile MDX a Microsoft Intune. To umožňuje spravovat aplikace pomocí zásad ochrany aplikací Intune při použití technologie mVPN společnosti Citrix.

Můžete najít úložiště kódu, které obsahuje Intune App Wrapping Tool a sadu Intune App SDK pro iOS a Android, a využít integraci s technologií Citrix MDX mVPN.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – nový partner ochrany před mobilními hrozbami   <!-- 954681 -->
Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Zimperium. Je to řešení ochrany před mobilními hrozbami integrované v Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak integrace se službou Intune funguje?
Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých služba Zimperium běží. Zásady podmíněného přístupu EMS založené na posouzení rizika službou Zimperium můžete nakonfigurovat prostřednictvím zásad dodržování předpisů zařízení služby Intune, kterými můžete na základě odhalených hrozeb u zařízení, které nedodržují předpisy, povolit nebo zablokovat přístup k firemním prostředkům.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Podpora vysoké dostupnosti místního konektoru Exchange Connector  <!-- 676614 -->   
U místního konektoru Exchange Connector máte možnost mít několik rolí serveru pro klientský přístup (CAS). Například pokud hlavní server pro klientský přístup selže, konektor Exchange Connector obdrží výzvu, aby využíval jiné servery pro klientský přístup. Tato funkce zajišťuje, že se služba nepřeruší.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Sada System Center Operations Manager Management Pack pro konektor Exchange Connector <!-- 885457 -->   
Pro pomoc s analýzou protokolů konektoru Exchange Connector bude dostupná sada System Center Operations Manager Management Pack pro konektor Exchange Connector. Pokud potřebujete řešit potíže, tento Management Pack poskytuje různé možnosti monitorování Intune.


### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Konec podpory pro Android verze 4.3 a nižší <!---1171127, 1326920 --->
Spravované aplikace a aplikace Portál společnosti pro Android budou pro přístup k firemním prostředkům vyžadovat operační systém Android 4.4 nebo novější. Zařízení, která nebudou do začátku října aktualizována, již nebudou mít k těmto aplikacím nebo k Portálu společnosti přístup. Od prosince budou všechna zaregistrovaná zařízení vyřazena, čímž dojde ke ztrátě přístupu k firemním prostředkům. Pokud používáte zásady ochrany aplikací bez správy mobilních zařízení MDM, aplikace nebudou získávat aktualizace a kvalita jejich činnosti bude časem upadat.


## <a name="intune-apps"></a>Aplikace Intune

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Vylepšené pokyny týkající se žádosti o přístup ke kontaktům na zařízeních s Androidem <!--1484985-->   
Aplikace Portál společnosti často po koncových uživatelích vyžaduje, aby přijali oprávnění Kontaktů. Pokud koncový uživatel tento přístup zamítne, zobrazí se mu oznámení v aplikaci, které ho upozorní, aby aplikaci udělil podmíněný přístup.

### <a name="secure-startup-remediation-for-android---1490712--"></a>Odstranění problému spojeného se zabezpečeným spuštěním pro Android <!--1490712-->     
Koncoví uživatelé, kteří používají zařízení s Androidem, budou moct v aplikaci Portál společnosti klepnout na důvod nedodržení předpisů. Pokud to bude možné, přejdou tímto klepnutím přímo do správného umístění v aplikaci Nastavení, aby mohli problém vyřešit.


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Přesměrování uživatelů macOS na naši novou aplikaci Portál společnosti <!--1380728-->   
Když se koncový uživatel přihlásí k webu Portál společnosti, aby zaregistroval svoje zařízení s macOS, bude přesměrován na to, aby proces dokončil stažením nové aplikace Portál společnosti pro macOS. K tomu dojde na zařízeních s macOS používajících OS X El Capitan 10.11 nebo novější. 

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Podpora ověřování na základě certifikátu v Portálu společnosti pro iOS <!--1029830-->
Přidali jsme podporu ověřování pomocí certifikátů v aplikaci Portál společnosti pro iOS. Uživatelé s ověřováním pomocí certifikátů zadají svoje uživatelské jméno a pak klepnou na odkaz „Přihlásit se pomocí certifikátu“. V aplikacích Portál společnosti pro Android a Windows je už ověřování pomocí certifikátů podporované. Další informace najdete na stránce o [přihlášení do aplikace Portál společnosti](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

<!-- the following are present prior to 1710 -->

### <a name="search-improvements-to-the-company-portal-website---1331697--"></a>Vyhledání vylepšení pro web Portál společnosti <!--1331697-->  
Vylepšujeme schopnosti vyhledávání aplikací a začali jsme u [webu Portál společnosti](https://portal.manage.microsoft.com). Vyhledávání bude nyní možné provádět nejen podle polí Název a Popis, ale také na základě kategorií aplikací. Výsledky budou ve výchozím nastavení seřazeny v sestupném pořadí podle relevance. 

Jelikož je web Portál společnosti součástí aplikace Portál společnosti pro iOS, získají tuto změnu i uživatelé systému iOS. Aplikace Portál společnosti pro Android a Windows obdrží podobné aktualizace v nadcházejících měsících.

Stále ještě na vyhodnocení relevance pracujeme, tak nám prosím dejte prostřednictvím odkazu „Váš názor“ v dolní části webu Portál společnosti vědět, jak dobře toto vyhodnocení funguje.

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Do aplikace Portál společnosti pro Windows 10 byla přidána akce aktualizace <!--1132468-->  
Aplikace Portál společnosti pro Windows 10 umožní uživatelům aktualizovat data v aplikaci, a to buď potažením prstem, nebo stisknutím klávesy F5 na počítačích.


### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Aplikace, které jsou dostupné s registrací nebo bez registrace, lze nyní nainstalovat bez výzvy k registraci <!-- 1334712 -->
Firemní aplikace, které byly u aplikace Portál společnosti pro Android zpřístupněny s registrací nebo bez registrace, lze nainstalovat bez výzvy k registraci.

### <a name="ios-company-portal-display-large-icons----1454593---"></a>Portál společnosti pro iOS zobrazuje velké ikony <!-- 1454593 -->
Opravujeme známý problém s tím, jak Portál společnosti pro iOS zobrazuje ikony v dlaždici aplikace. Pokud nahrajete ikony aplikace o rozměru 120×120 pixelů nebo větší, zobrazí se teď na [webu Portálu společnosti] (https://portal.manage.microsoft.com) a na stránkách aplikací Portál společnosti pro iOS v plné velikosti dlaždice aplikace.

<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Podpora Intune Managed Browser pro iOS a Android <!-- 1374196 -->
Od října 2017 bude aplikace Intune Managed Browser pro Android podporovat jen zařízení se systémem Android 4.4 a novější. Aplikace Intune Managed Browser pro iOS bude podporovat jen zařízení se systémem iOS 9.0 a novější. Starší verze systému Android a iOS budou moct Managed Browser dál používat, ale nepůjde do nich nainstalovat nové verze této aplikace a nebudou mít přístup ke všem jejím možnostem. Doporučujeme vám tato zařízení aktualizovat na podporovanou verzi operačního systému.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Vylepšená chybová zpráva, když uživatel dosáhne maximálního povoleného počtu zařízení k registraci <!-- 1270370 -->
Místo obecné chybové zprávy se koncovým uživatelům zobrazí popisná chybová zpráva, na kterou se dá reagovat: „Zaregistrovali jste maximální počet zařízení, který povoluje váš IT správce. Odeberte prosím zaregistrované zařízení, nebo se obraťte s žádostí o pomoc na IT správce.“




## <a name="notices"></a>Sdělení

### <a name="device-and-app-management-integration----677972---"></a>Integrace správy zařízení a aplikací <!-- 677972 -->   
Když jsou teď správa mobilních zařízení (MDM) i správa mobilních aplikací (MAM) Intune přístupné z portálu Azure Portal, začala služba Intune integrovat způsoby práce IT správců týkající se správy aplikací a zařízení. Tyto změny jsou zaměřené na zjednodušení způsobu správy zařízení a aplikací.

Další informace o změnách MDM a MAM najdete na [blogu týmu podpory Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple bude vyžadovat aktualizace ATS (Application Transport Security) <!--748318-->   
Apple oznámil, že od jara 2017 začne vynucovat specifické požadavky na ATS (Application Transport Security). ATS se používá k vynucení vyššího zabezpečení veškeré komunikace aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune, kteří používají aplikace Portál společnosti pro iOS. Další podrobnosti najdete v [blogu podpory služby Intune](https://aka.ms/compportalats).


### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Nová cesta pro spravovaná zařízení v Graph API <!-- 1586728 -->  
V říjnové vydané verzi služby Intune měníme cestu používanou pro přístup ke spravovaným zařízením v beta verzi rozhraní Graph API.

| | |
|--|--|
| Aktuální cesta |  https://graph.microsoft.com/beta/managedDevices |
| Nová cesta | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Celý říjen budou fungovat obě cesty. Po říjnovém vydání verze služby bude fungovat jenom cesta nová.  Pokud používáte rozhraní Graph API pro přístup ke spravovaným zařízením, aktualizujte a ověřte své skripty a aplikace s novou cestou. Další změny najdete v měsíčním [protokolu změn Graph API](https://developer.microsoft.com/en-us/graph/docs/concepts/changelog).

### <a name="see-also"></a>Související témata
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).
