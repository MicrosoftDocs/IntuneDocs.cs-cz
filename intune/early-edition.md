---
title: "Časná edice"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5eab3fb933b2999e23115091cf0ded3f140e114c
ms.sourcegitcommit: f5c6e8b218431dc9a8d85464d7f58adebd048866
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/06/2017
---
# <a name="the-early-edition-for-microsoft-intune---july-2017"></a>Časná edice Microsoft Intune – červenec 2017

**Časná edice** poskytuje seznam funkcí, které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány ve velmi omezené míře a můžou podléhat změnám. Nesdílejte tyto informace mimo společnost. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a můžou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moct zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se na příslušný kontakt pro skupinu produktů společnosti Microsoft.

Tato stránka se pravidelně aktualizuje. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.

> [!Note]
>Následující změny v Intune jsou ve vývoji. Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune on the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="whats-coming-to-intune-on-the-azure-portal"></a>Co připravujeme v Intune na portálu Azure Portal

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Snadnější instalace aplikací Office 365 <!--- 1121362 --->
Nový typ aplikace **Office 365 ProPlus** vám usnadní přiřazování aplikací Office 365 ProPlus na vámi spravovaná zařízení, na kterých běží nejnovější verze Windows 10. Pokud vlastníte příslušné licence, budete moct nainstalovat Microsoft Project a Microsoft Visio. Požadované aplikace jsou spojeny dohromady a v seznamu aplikací v konzole Intune se budou zobrazovat jako jedna aplikace.
 

### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nová akce zařízení, která zařízení donutí provést synchronizaci s Intune <!-- 711369 -->    
Přidáváme novou akci zařízení, která vybrané zařízení donutí se okamžitě ohlásit ve službě Intune. Jakmile se zařízení ohlásí, začne okamžitě přijímat veškeré čekající akce nebo zásady, které mu byly přiřazeny.  Tato akce vám může pomoct okamžitě ověřit přiřazené zásady nebo s těmito zásadami vyřešit potíže, aniž byste čekali na další naplánované ohlášení.

### <a name="actions-for-non-compliance----730266--"></a>Akce při nedodržení předpisů  <!--730266-->     
*Akce při nedodržení předpisů* je nová funkce zásad dodržování předpisů, která vám umožní provádět akce na zařízeních, které nedodržují předpisy. Můžete zadat jednu nebo více akcí a určit časové období, během kterého se tyto akce musí provést. Třeba uživatelům zařízení, která nedodržují předpisy, můžete poslat e-mailem oznámení, hned jak zařízení přestane předpisy dodržovat. Nebo pomocí podmíněného přístupu můžete takovým zařízením zablokovat přístup k prostředkům společnosti po 3denním období odkladu.

### <a name="new-app-configuration-settings-for-the-intune-managed-browser-----682951----"></a>Nová nastavení konfigurace aplikace pro Intune Managed Browser <!--- 682951 --->
Pro aplikaci Intune Managed Browser přidáme další konfigurace. Pomocí zásad konfigurace aplikace budete moct pro prohlížeč nakonfigurovat výchozí domovskou stránku a záložky.

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Omezení registrace zařízení s Androidem a iOSem podle verze operačního systému  <!--- 1333256,  1245463 --->  
Intune nyní podporuje omezení registrace iOSu a Androidu podle čísla verze operačního systému. V části **Intune** > **Omezení registrace** > **Omezení typu zařízení** > **Výchozí** > **Omezení platformy** může nyní správce IT nastavit konfiguraci platformy tak, aby se registrace omezovala na rozsah mezi minimální a maximální hodnotou verze operačního systému. Verze operačního systému Android je nutné zadávat ve formátu Hlavní.Podverze.Sestavení.Revize, kde Sestavení a Revize jsou nepovinné hodnoty. Verze iOS je nutné zadávat ve formátu Hlavní.Podverze.Sestavení, kde Sestavení je nepovinná hodnota.

>[!NOTE]
>Toto nastavení neomezuje registraci prostřednictvím programů registrace Apple, mezi které patří programy Apple Device Enrollment Program, Apple School Manager a Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Omezení registrace zařízení v osobním vlastnictví se systémem Android, iOS a macOS  <!--- 1333272,  1333275, 1245709 --->
Intune nyní podporuje omezení registrace zařízení v osobním vlastnictví se systémem Android, iOS a macOS prostřednictvím sériových čísel zařízení. Některá zařízení sériová čísla nehlásí. Ohledně podrobností se obraťte na výrobce zařízení. Nahráním sériových čísel do Intune můžete zařízení předem deklarovat jako majetek společnosti. Pomocí omezení registrace můžete blokovat zařízení v osobním vlastnictví (BYOD) a umožnit registraci pouze zařízením ve vlastnictví společnosti.

Pokud chcete importovat sériová čísla do portálu Intune, přejděte na **Registrace zařízení** > **Identifikátory podnikových zařízení**, klikněte na **Přidat** a potom nahrajte soubor CSV (žádné záhlaví a dva odstavce pro sériová čísla a podrobnosti jako čísla IMEI).  Pokud chcete omezit zařízení v osobním vlastnictví, přejděte na **Registrace zařízení** > **Omezení registrace**. V části **Omezení typů zařízení** vyberte **Výchozí** a potom vyberte **Konfigurace platformy**. Zařízení se systémem iOS, Android a macOS v osobním vlastnictví můžete **povolit** nebo **zakázat**. 

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Donucení zařízení s iOSem, která jsou pod dohledem, aby automaticky instalovaly nejnovější dostupnou aktualizaci softwaru <!-- 777100 -->   
V pracovním prostoru aktualizací softwaru budou dostupné nové zásady, které donutí zařízení s iOSem, která jsou pod dohledem, automaticky instalovat nejnovější dostupnou aktualizaci softwaru. Budete si také moct zobrazit novou sestavu se seznamem zařízení s iOSem, které mají starší verzi, a souhrn vysvětlující proč nejsou aktuální.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices-----822899--1305423--"></a>Povolení a blokování aplikací na zařízeních se Samsung KNOX Standard pomocí nových nastavení  <!-- 822899,  1305423-->   
Přidáváme nová [nastavení omezení zařízení](device-restrictions-android.md), která vám umožní zadat následující seznamy aplikací:
  - Aplikace, které mají uživatelé dovoleno instalovat.
  - Aplikace, které mají uživatelé zakázáno spouštět.
  - Aplikace, které jsou před uživatelem zařízení skryté.  

Aplikaci můžete zadat pomocí adresy URL, názvu balíčku nebo ze seznamu spravovaných aplikací.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Podpora Androidu for Work pro Lookout <!-- 1087312 -->   
Při použití aplikace Lookout for Work bude konektor Intune s Lookoutem podporovat zařízení s Androidem for Work. Aplikaci Lookout bude možné nasadit uvnitř nebo vně kontejneru.


### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651--and--1172027----"></a>Check Point SandBlast Mobile – Nový partner ochrany před mobilními hrozbami  <!-- 954651  and  1172027 ? -->  
Přístup mobilních zařízení k podnikovým prostředkům budete moct regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Check Point SandBlast Mobile. Je to řešení ochrany před mobilními hrozbami integrované ve službě Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak integrace se službou Intune funguje?
Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých služba Check Point SandBlast Mobile běží. Na základě posouzení rizik aplikací Check Point SandBlast Mobile, které umožňují zásady dodržování předpisů v Intune, můžete nakonfigurovat zásady podmíněného přístupu EMS. Přístup k podnikovým prostředkům ze zařízení nesplňujících požadavky můžete na základě zjištěných hrozeb povolit nebo zakázat.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – nový partner ochrany před mobilními hrozbami   <!-- 954681 -->
Přístup mobilních zařízení k podnikovým prostředkům budete moct regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Zimperium. Je to řešení ochrany před mobilními hrozbami integrované ve službě Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak integrace se službou Intune funguje?
Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých služba Zimperium běží. Zásady podmíněného přístupu EMS založené na posouzení rizika službou Zimperium můžete nakonfigurovat prostřednictvím zásad dodržování předpisů zařízení služby Intune, kterými můžete na základě odhalených hrozeb u zařízení, které nedodržují předpisy, povolit nebo zablokovat přístup k firemním prostředkům.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Podpora vysoké dostupnosti místního konektoru Exchange Connector  <!-- 676614 -->   
U místního konektoru Exchange Connector získáte možnost mít několik rolí serveru pro klientský přístup (CAS). Například pokud hlavní server pro klientský přístup selže, konektor Exchange Connector obdrží výzvu, aby využíval jiné servery pro klientský přístup. Tato funkce zajišťuje, že se služba nepřeruší.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Sada System Center Operations Manager Management Pack pro konektor Exchange Connector <!-- 885457 -->   
Pro pomoc s analýzou protokolů konektoru Exchange Connector bude dostupná sada System Center Operations Manager Management Pack pro konektor Exchange Connector. V případě potřeby řešení potíží tak budete mít různé možnosti monitorování Intune.

### <a name="conditional-access-support-for-mac-devices-----720172---"></a>Podpora podmíněného přístupu pro zařízení Mac  <!-- 720172 -->   
Brzy budete moct nastavit zásady podmíněného přístupu, které donutí zařízení Mac se zaregistrovat ve službě Intune a dodržovat její zásady dodržování předpisů pro zařízení. Uživatelé si mohou například stáhnout aplikaci Portál společnosti Intune pro macOS a zaregistrovat svá zařízení Mac ve službě Intune. Intune prostřednictvím požadavků, jako je kód PIN, šifrování, verze operačního systému a integrita systému, vyhodnotí, zda zařízení Mac předpisy dodržuje nebo ne.

### <a name="end-of-support-for-ios-80----1164477---"></a>Konec podpory pro systém iOS 8.0 <!---1164477--->
Spravované aplikace a aplikace Portál společnosti pro iOS budou pro přístup k firemním prostředkům vyžadovat operační systém iOS 9.0 nebo novější. Zařízení, která nebudou do tohoto září aktualizována, již nebudou mít k těmto aplikacím nebo k Portálu společnosti přístup. Od prosince jim bude zakázán veškerý přístup k firemním prostředkům včetně e-mailu. 

### <a name="end-of-support-for-android-43-and-lower----1171127---"></a>Konec podpory pro Android verze 4.3 a nižší <!---1171127--->
Spravované aplikace a aplikace Portál společnosti pro Android budou pro přístup k firemním prostředkům vyžadovat operační systém Android 4.4 nebo novější. Zařízení, která nebudou do začátku října aktualizována, již nebudou mít k těmto aplikacím nebo k Portálu společnosti přístup. Od prosince budou všechna zaregistrovaná zařízení vyřazena, čímž dojde ke ztrátě přístupu k firemním prostředkům. Pokud používáte zásady ochrany aplikací bez správy mobilních zařízení MDM, aplikace nebudou získávat aktualizace a kvalita jejich činnosti bude časem upadat.





### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Připomenutí podpory platformy: všeobecná podpora Windows Phone 8.1 končí 11. července 2017 <!-- 1327781 -->  
11. července 2017 končí všeobecná podpora platformy Windows Phone 8.1. Podporu počítačů s Windows 8.1 to neovlivní.

Na žádné zařízení s Windows Phone 8.1, které je spravováno službou Intune, to nebude mít okamžitý vliv. Zaregistrovaná zařízení budou nadále fungovat a všechny zásady, konfigurace a aplikace také. Všimněte si, že pro aplikaci Portál společnosti Windows Phone 8.1 ani pro platformu Windows Phone 8.1 v rámci služby Intune neexistují žádná cílená vylepšení.

Doporučujeme vám při nejbližší příležitosti způsobilá zařízení s Windows Phone 8.1 upgradovat na Windows 10 Mobile. 




## <a name="whats-coming-to-intune-apps"></a>Co připravujeme v aplikacích Intune

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Vylepšené přihlašování k aplikacím Portál společnosti na všech platformách <!--User Story 1132123-->    
Avizujeme změnu, kterou uvedeme během několika nadcházejících měsíců a která vylepší přihlašování k aplikacím Portál společnosti Intune v systémech Android, iOS a Windows. Nové uživatelské prostředí se automaticky zobrazí na všech platformách pro aplikaci Portál společnosti, až Azure AD tuto změnu provede. Kromě toho se teď uživatelé můžou k Portálu společnosti přihlašovat z jiného zařízení pomocí vygenerovaného kódu na jedno použití. To se hodí hlavně v případech, kdy se uživatelé potřebují přihlásit bez přihlašovacích údajů.

Snímky obrazovky předchozího způsobu přihlašování, nového způsobu přihlašování pomocí přihlašovacích údajů a nového způsobu přihlašování z jiného zařízení najdete na stránce s [novinkami v uživatelském rozhraní aplikací](whats-new-app-ui.md).

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Světlé a tmavé režimy dostupné pro aplikaci Portál společnosti pro Windows 10 <!---676547--->
Koncoví uživatelé budou mít možnost přizpůsobit barevný režim aplikace Portál společnosti pro Windows 10. Uživatel může změny provádět v sekci Nastavení aplikace Portál společnosti. Změna se zobrazí, jakmile uživatel aplikaci restartuje. Pro Windows 10 verze 1607 a novější se režim aplikace nastaví podle výchozího nastavení systému. Pro stolní počítače se systémem Windows 10 verze 1511 a starší, bude výchozím režimem aplikace světlý režim.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Možnost pro koncové uživatele v aplikaci Portál společnosti pro Windows 10 označit svou skupinu zařízení <!---807046-->    
Koncoví uživatelé získají možnost vybrat si, do které skupiny jejich zařízení patří, když ho označí přímo v aplikaci Portál společnosti pro Windows 10.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Možnost pro koncové uživatele získat přístup k aplikaci Portál společnosti pro Android bez registrace <!---1169910--->  
Koncoví uživatelé brzy nebudou muset svá zařízení registrovat, aby získali přístup k aplikaci Portál společnosti pro Android. Koncovým uživatelům v organizacích, které používají zásady ochrany aplikací, už nebudou při otevření aplikace Portál společnosti chodit výzvy k registraci jejich zařízení. Koncoví uživatelé budou také moct bez registrace zařízení z Portálu společnosti instalovat aplikace. 

### <a name="users-who-are-signed-in-to-exchange-can-automatically-access-the-company-portal-website-on-windows-10-devices---1323204--"></a>Uživatelé přihlášení do Exchange mohou automaticky na zařízeních s Windows 10 získat přístup k webu Portál společnosti <!--1323204-->  
Uživatelé Windows 10, kteří provedli ověření v systému Exchange, dostali e-mail o karanténě podmíněného přístupu a klikli na odkaz v tomto e-mailu, se už před začátkem nastavení přístupu společnosti nemusí opakovaně ověřovat v prohlížeči.


## <a name="notices"></a>Sdělení

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple bude vyžadovat aktualizace ATS (Application Transport Security) <!--748318-->   
Apple oznámil, že od jara 2017 začne vynucovat specifické požadavky na ATS (Application Transport Security). ATS se používá k vynucení vyššího zabezpečení veškeré komunikace aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune, kteří používají aplikace Portál společnosti pro iOS. Další podrobnosti najdete v [blogu podpory služby Intune](https://aka.ms/compportalats).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Přímý přístup ke scénářům registrace Apple <!--951869-->   
U účtů Intune vytvořených po lednu 2017 umožňuje Intune přímý přístup ke scénářům registrace Apple pomocí úlohy Registrovat zařízení na portálu Azure Preview. Náhled na registraci Apple byl předtím přístupný přes odkazy na portálu klasické služby Intune. Zpřístupnění těchto funkcí v Azure bude u účtů Intune vytvořených před lednem 2017 vyžadovat jednorázovou migraci. Plán této migrace zatím nebyl oznámen, podrobnosti ale budou zpřístupněny co nejdříve. Pokud váš existující účet nemá k tomuto náhledu přístup, k otestování tohoto nového prostředí důrazně doporučujeme vytvořit zkušební účet.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Plánovaná změna: Intune mění způsob fungování portálu Intune Partner Portal<!-- 1050016 -->
Počínaje aktualizací služby v polovině května 2017 odstraníme stránku Intune Partner z manage.microsoft.com.  

Pokud jste partnerským správcem, nebude už moct stránku Intune Partner zobrazit a provádět z ní jménem vašich zákazníků kroky, ale místo toho se budete muset přihlásit k jednomu ze dvou dalších partnerských portálů Microsoftu.

K účtům zákazníků, které spravujete, se budete moct přihlásit z [Partnerského centra Microsoftu](https://partnercenter.microsoft.com/) a [Centra pro partnerskou správu Office 365](https://portal.office.com/). V budoucnu jako partneři prosím ke správě svých zákazníků používejte jeden z těchto webů.



### <a name="see-also"></a>Související témata
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).
