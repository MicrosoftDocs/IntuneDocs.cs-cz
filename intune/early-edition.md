---
title: "Časná edice"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7d54cb060dc44d29c95203138396f771abbb2325
ms.sourcegitcommit: 6d69403266dbcb31c879432719798935c94917fa
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2018
---
# <a name="the-early-edition-for-microsoft-intune---february-2018"></a>Časná edice pro Microsoft Intune – únor 2018

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


<!-- 1802 start -->

### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nový graf trendu neúspěšných registrací a tabulka důvodů selhání <!-- 1471783 -->

Na stránce s přehledem registrací uvidíte trend neúspěšných registrací a pět nejčastějších příčin selhání. Kliknutím na tento graf nebo tabulku můžete přejít k podrobnostem a najít rady pro řešení problémů a návrhy vedoucí k nápravě.

### <a name="prevent-end-users-from-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Znemožněte koncovým uživatelům přidávání nebo odebírání účtů v pracovním profilu <!-- 1728700 -->    
Když nasadíte aplikaci Gmail do profilu Android for Work, budete moct zabránit tomu, aby koncoví uživatelé přidávali nebo odebírali účty v pracovním profilu s použitím nastavení **Přidat nebo odebrat účty** v profilu omezení pro zařízení Android for Work.

### <a name="app-protection-policies-----679615---"></a>Zásady ochrany aplikací  <!-- 679615 -->
Zásady Intune App Protection nabízejí možnost vytvoření globálních výchozích zásad, které rychle aktivují ochranu přes všechny uživatele v celém tenantovi.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Podpora Intune pro více účtů Apple DEP nebo Apple School Manager <!-- 747685 -->

Intune podporuje registraci zařízení z až 100 různých účtů Apple DEP (Device Enrollment Program) nebo Apple School Manager. Pro každý nahraný token lze profily registrace a zařízení spravovat samostatně. K jednotlivým nahraným tokenům DEP nebo School Manager lze automaticky přiřadit různé profily registrace. Pokud je nahraných více tokenů School Manager, může se v každém okamžiku sdílet pomocí služby Microsoft School Data Sync jenom jeden.

Po dokončení migrace už nebudou fungovat beta verze rozhraní Graph API a publikované skripty pro správu Apple DEP nebo ASM přes rozhraní Graph. Nové beta verze rozhraní Graph API jsou ve vývoji a budou se vydávat po dokončení migrace.

### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Sestavy stavu hrozby a stavu programu Windows Defender <!--854704 -->

Klíčem ke správě počítačů s Windows je pochopení stavu programu Windows Defender.  Intune přidá do stavu agenta Windows Defender nové sestavy a akce. Pomocí souhrnné sestavy stavu v úloze dodržování předpisů zařízením zjistíte, která zařízení vyžadují:

- aktualizaci signatur,
- restartování,
- ruční zásah,
- úplnou kontrolu,
- stavy ostatních agentů vyžadujících zásah.

V určitých případech je možné provést vzdálené nápravné akce, například spustit aktualizaci signatury.  Sestava také uvádí počet počítačů, které jsou **čisté**.

Podrobná sestava pro jednotlivé kategorie stavu uvádí jednotlivé počítače, které vyžadují pozornost, nebo ty, které jsou **čisté**.

### <a name="protocol-exceptions-for-applications---1035509-eeready--"></a>Výjimky protokolu pro aplikace <!--1035509 eeready-->

Budete moct vytvořit výjimky ze zásady přenosu dat ve správě mobilních dat Intune, abyste mohli otevřít konkrétní nespravované aplikace. Tyto aplikace musí být pro IT důvěryhodné. Pokud zásady přenosu dat nastavíte **jenom na spravované aplikace**, bude kromě vytvořených výjimek přenos dat i nadále omezen jen na aplikace, které se spravují přes Intune. Tato omezení můžete vytvořit pomocí protokolů (iOS) nebo balíčků (Android).

Do zásad přenosu aplikací MAM můžete například přidat jako výjimku balíček Webex. To umožní, aby se odkazy Webex ve spravované outlookové e-mailové zprávě otevíraly přímo v aplikaci Webex. V ostatních nespravovaných aplikacích bude přenos dat i nadále omezen.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561-eeready--"></a>Přizpůsobení motivů Portálu společnosti pomocí šestnáctkových kódů <!--1049561 eeready-->

Pomocí šestnáctkových kódů si budete moct přizpůsobit barvu motivu v aplikacích Portál společnosti. Když zadáte šestnáctkový kód, Intune určí barvu textu, která poskytuje nejvyšší úroveň kontrastu mezi barvou textu a barvou pozadí podle [standardů WCAG 2.0](http://www.w3.org/TR/WCAG20). Můžete si zobrazit náhled barvy textu a loga společnosti oproti barvě v části **Mobilní aplikace** > **Portál společnosti**. 

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Nové nastavení Ochrany Credential Guard v programu Windows Defender přidaná do nastavení ochrany koncového bodu <!--1102252 --> 

Do části **Konfigurace zařízení** > **Profily** > **Ochrana koncového bodu** budou přidána nová nastavení [Ochrana Credential Guard v programu Windows Defender] (https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard). Budou přidána následující nastavení: 

- Úroveň zabezpečení platformy: Zadejte, zda se při příštím restartování povolí úroveň zabezpečení platformy. Zabezpečení na základě virtualizace vyžaduje Zabezpečené spuštění. Zabezpečení na základě virtualizace je možné volitelně povolit s použitím ochran přímého přístupu do paměti (DMA). Ochrany DMA vyžadují hardwarovou podporu a povolí se jenom na správně nakonfigurovaných zařízeních.
- Zabezpečení na základě virtualizace: Zadejte, zda se při příštím restartování povolí zabezpečení na základě virtualizace. 
- Ochrana Credential Guard v programu Windows Defender: Zapněte ochranu Credential Guard se zabezpečením na základě virtualizace, abyste pomohli ochránit přihlašovací údaje při příštím restartování v případě, že jsou povoleny úroveň zabezpečení platformy se Zabezpečeným spuštěním a zabezpečení na základě virtualizace. Dostupné možnosti zahrnují **Zakázáno**, **Povoleno s uzamčením UEFI**, **Povoleno bez uzamčení** a **Nenakonfigurováno**. 
  - Možnost Zakázáno vzdáleně vypne ochranu Credential Guard, pokud byla dříve zapnutá pomocí možnosti Povoleno bez uzamčení.

  - Možnost Povoleno s uzamčením UEFI zajistí, že ochranu Credential Guard nebude možné zakázat pomocí klíče registru nebo pomocí zásad skupiny. Pokud chcete zakázat ochranu Credential Guard po použití tohoto nastavení, musíte zásady skupiny nastavit na Zakázáno a odebrat funkci zabezpečení z jednotlivých počítačů za osobní přítomnosti uživatele, aby bylo možné vymazat konfiguraci trvale uloženou v UEFI. Dokud je konfigurace UEFI trvale uložena, je ochrana Credential Guard povolena.

  - Možnost Povoleno bez uzamčení umožní vzdálené zakázání ochrany Credential Guard pomocí zásad skupiny. Na zařízeních s tímto nastavením musí běžet přinejmenším Windows 10 (verze 1511).

  - Možnost Nenakonfigurováno ponechá nastavení zásad nedefinované. Zásady skupiny nezapíšou nastavení zásad do registru, a proto počítače ani uživatele nijak neovlivní. Pokud v registru existuje aktuální nastavení, zůstane beze změny.

### <a name="synchronize-and-deploy-sparsely-bundled-windows-store-for-business-apps---1222672---"></a>Synchronizace a nasazení často samostatně poskytovaných aplikací z Windows Storu pro firmy <!--1222672 -->
Offline aplikace zakoupené ve Windows Storu pro firmy se nyní budou synchronizovat na portálu Intune. Tyto aplikace můžete nasadit pro skupiny zařízení nebo skupiny uživatelů. Offline aplikace bude instalovat služba Intune, nikoli Store.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Resetování hesel pro zařízení s Androidem O <!-- 1238299 -->
U zaregistrovaných zařízení s Androidem O budete moct resetovat hesla. Když do zařízení s Androidem O pošlete žádost o resetování hesla, nastaví se aktuálnímu uživateli nové heslo pro odemčení zařízení nebo výzva spravovaného profilu. Heslo nebo výzva se pošle na základě toho, zda má zařízení vlastníka profilu nebo vlastníka zařízení, a projeví se okamžitě.

### <a name="local-device-security-option-settings----1251887---"></a>Nastavení možnosti místního zabezpečení zařízení <!-- 1251887 -->
Pomocí nového nastavení možnosti místního zabezpečení zařízení budete moct povolit nastavení zabezpečení na zařízeních s Windows 10. Tato nastavení najdete v kategorii Ochrana koncového bodu při vytváření zásad konfigurace zařízení s Windows 10.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nové nastavení tiskárny pro vzdělávací profily <!-- 1308900 -->

Pro vzdělávací profily bude nové nastavení k dispozici v kategorii **Tiskárny**: **Tiskárny**, **Výchozí tiskárna**, **Přidat nové tiskárny**. 

### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Nové nastavení ochrany osobních údajů pro omezení zařízení <!--1308926 -->

Pro zařízení budou k dispozici dvě nová nastavení ochrany osobních údajů:

- **Publikovat aktivity uživatele**: Tuto možnost nastavte na **Blokovat**, pokud chcete zabránit ve sdílení a zjišťování naposledy použitých prostředků při přepínání úloh.

- **Jen místní aktivity**: Tuto možnost nastavte na **Blokovat**, pokud chcete zabránit ve sdílení a zjišťování naposledy použitých prostředků při přepínání úloh jen u místní aktivity.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Podpora registrací přes Správce registrace zařízení na Portálu společnosti v macOS <!-- 1352411 -->

Uživatelé budou moct používat Správce registrace zařízení při registraci na Portálu společnosti v macOS.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Nové nastavení prohlížeče Edge <!--1469166 -->

Pro zařízení s prohlížečem Microsoft Edge budou k dispozici dvě nová nastavení: **Path to favorites file** (Cesta k souboru oblíbených položek) a **Changes to Favorites** (Změny oblíbených položek). 

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Šifrovaná data Windows Information Protection (WIP) ve výsledcích hledání ve Windows <!-- 1469193 -->

Nové nastavení v zásadách Windows Information Protection (WIP) vám umožní řídit, jestli se mají do výsledků hledání ve Windows zahrnovat šifrovaná data WIP.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Podpora obchodních aplikací (LOB) pro macOS <!-- 1473977 -->
Intune bude poskytovat možnost instalace obchodních aplikací pro macOS. Obchodní aplikace jsou aplikace, pro které poskytnete instalační soubor a pomocí Intune je nainstalujete na zařízení. V rámci podpory obchodních aplikací pro macOS musíte obchodní aplikace pro macOS předběžně zpracovat pomocí nástroje Microsoft Intune App Wrapping Tool pro macOS.

### <a name="configure-resource-account-settings-for-surface-hubs----1475674---"></a>Konfigurace nastavení účtu prostředku pro Surface Huby <!-- 1475674 -->

Budete moct vzdáleně nakonfigurovat nastavení účtu prostředku pro Surface Huby.

Surface Hub využívá účet prostředku k ověření u Skypu nebo Exchange, aby bylo možné se připojit ke schůzce. Můžete vytvořit jedinečný účet prostředku, aby se Surface Hub mohl zobrazit ve schůzce jako konferenční místnost. Účet prostředku se například může zobrazit jako **Konferenční místnost B41/6233**.

> [!NOTE]
> - Pokud pole ponecháte prázdná, přepíšete dříve nakonfigurované atributy na zařízení.
>
> - Vlastnosti účtu prostředku se můžou na Surface Hubu dynamicky měnit. Jedná se například o případ zapnutí rotace hesla. Proto je možné, že bude chvíli trvat, než se realita na zařízení promítne u hodnot v konzole Azure. 
>
>   Pokud chcete zjistit, co je aktuálně nakonfigurováno na Surface Hubu, můžete zahrnout informace o účtu prostředku do inventáře hardwaru (který už má sedmidenní interval) nebo jako vlastnosti jen pro čtení. Z důvodu vyšší přesnosti po provedení vzdálené akce můžete získat stav parametrů ihned po spuštění akce aktualizace účtu nebo parametrů na Surface Hubu.

### <a name="ios-app-provisioning-configuration----1581650---"></a>Konfigurace zřizování aplikací pro iOS <!-- 1581650 -->
Pomocí zahrnutí nebo vyloučení skupin zabezpečení budete moct přiřadit zřizovací profily aplikací pro iOS a zabránit tak vypršení platnosti aplikací.

### <a name="new-windows-defender-exploit-guard-settings----631893---"></a>Nové nastavení Ochrany Exploit Guard v programu Windows Defender <!-- 631893 -->

K dispozici bude šest nových nastavení **Omezení možností útoku** a rozšířené možnosti **Řízený přístup ke složkám: Ochrana složek**. Tato nastavení najdete tady: Konfigurace zařízení\Profily\
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

|Název nastavení  |Možnosti nastavení  |Popis  |
|---------|---------|---------|
|Ochrana složek (již implementováno)|Nenakonfigurováno, Povolit, Pouze audit (již implementováno)<br><br> **Nové**<br>Block disk modification (Blokovat změny disku), Audit disk modification (Auditovat změny disku)|
Umožňuje chránit soubory a složky před neautorizovanými změnami od neznámých aplikací.<br><br>**Povolit**: Brání nedůvěryhodným aplikacím ve změnách nebo odstranění souborů v chráněných složkách a v zápisu do sektorů disku.<br><br>
**Block disk modification only** (Blokovat jenom změny disku):<br>Umožňuje zablokovat nedůvěryhodným aplikacím možnost zapisovat do sektorů disku. Nedůvěryhodné aplikace stále můžou změnit nebo odstranit soubory v chráněných složkách.|

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nové nastavení Ochrany Application Guard v programu Windows Defender <!-- 1631890 -->

- **Enable graphics acceleration** (Povolit akceleraci grafiky)

Správci budou moct pro Ochranu Application Guard v programu Windows Defender povolit virtuální grafický procesor. Toto nastavení umožní procesoru přesunout vykreslování grafiky na virtuální grafický procesor. Může zlepšit výkon při práci s graficky náročnými weby nebo při sledování videa v kontejneru.

- **SaveFilestoHost**

Správci budou moct povolit předávání souborů z Microsoft Edge, který běží v kontejneru, do hostitelského souborového systému. Zapnutím tohoto nastavení umožníte uživatelům stahovat soubory z Microsoft Edge v kontejneru do hostitelského souborového systému.

### <a name="see-enrollment-restrictions-per-user----1634444---"></a>Nastavení omezení registrace na uživatele <!-- 1634444 -->
V okně řešení potíží si budete moct zobrazit omezení registrace, která platí pro jednotlivé uživatele.

### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Konfigurace automaticky aktualizovaných mobilních aplikací MSI <!-- 1740840 -->
Známou automaticky aktualizovanou mobilní aplikaci MSI budete moct nakonfigurovat tak, aby ignorovala proces kontroly verzí. Tato možnost je užitečná, když chcete předejít konfliktu časování. Ke konfliktu časování může například dojít, když aplikaci automaticky aktualizuje vývojář a současně Intune. Jak vývojář, tak Intune můžou vynucovat verzi aplikaci na klientovi Windows, což může způsobit konflikt.

### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133---"></a>Další nastavení zabezpečení systému pro zásady dodržování předpisů pro Windows 10 a novější <!--1704133 -->

Budou dostupná další nastavení dodržování předpisů pro Windows 10, včetně vyžadování brány firewall a Antivirové ochrany v programu Windows Defender.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Zahrnutí a vyloučení přiřazení aplikací na základě skupin pro Android Enterprise <!-- 1813081 -->
Během přiřazení aplikace a po výběru typu přiřazení bude Android Enterprise (dříve Android for Work) podporovat funkci vyloučení.


### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Podpora souvisejících sad licencí aplikací v Intune <!-- 1864117 -->
Intune na portálu Azure Portal bude podporovat související sady licencí aplikací jako jedinou položku aplikace v uživatelském rozhraní. Kromě toho všechny aplikace licencované offline a synchronizované z Microsoft Storu pro firmy se sloučí do jediné položky aplikace a všechny podrobnosti nasazení z jednotlivých balíčků se budou migrovat do jediné položky. Pokud se chcete podívat na související sady licencí aplikací na portálu Azure Portal, vyberte **Licence aplikací** v okně **Mobilní aplikace**.

<!-- the following are present prior to 1802 -->

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Nová možnost ověřování uživatelů při hromadné registraci Apple <!-- 747625 -->
Intune nabízí možnost ověřovat zařízení pomocí aplikace Portál společnosti u těchto metod registrace:

- Program Apple Device Enrollment Program
- Apple School Manager
- Registrace Apple Configuratoru

Při použití možnosti Portálu společnosti lze vynutit vícefaktorové ověřování Azure Active Directory bez blokování těchto metod registrace.

Při použití možnosti Portálu společnosti pro registraci přidružení uživatelů přeskočí Intune ověřování uživatelů v Pomocníkovi s nastavením iOSu. To znamená, že zařízení se napřed zaregistruje bez uživatelů a neobdrží tedy konfigurace ani zásady pro skupiny uživatelů. Obdrží jenom konfigurace a zásady pro skupiny zařízení. Intune ale na toto zařízení automaticky nainstaluje aplikaci Portál společnosti. První uživatel, který aplikaci Portál společnosti spustí a přihlásí se do ní, se v Intune přidruží k tomuto zařízení. V tomto okamžiku pak obdrží konfigurace a zásady dané skupiny uživatelů. Přidružení uživatelů není možné změnit bez opětovné registrace.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Podpora Intune pro více účtů Apple DEP nebo Apple School Manager <!-- 747685 -->
Intune podporuje registraci zařízení z až 100 různých účtů Apple DEP (Device Enrollment Program) nebo Apple School Manager. Pro každý nahraný token lze profily registrace a zařízení spravovat samostatně. K jednotlivým nahraným tokenům DEP nebo School Manager lze automaticky přiřadit různé profily registrace. Pokud je nahraných více tokenů School Manager, může se v každém okamžiku sdílet pomocí služby Microsoft School Data Sync jenom jeden.

Po dokončení migrace už nebudou fungovat beta verze rozhraní Graph API a publikované skripty pro správu Apple DEP nebo ASM přes rozhraní Graph. Nové beta verze rozhraní Graph API jsou ve vývoji a budou se vydávat po dokončení migrace.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963---"></a>Výběr kategorií zařízení pomocí nastavení Přístup do práce nebo do školy <!-- 1058963 -->
Pokud jste povolili [mapování skupin zařízení](https://docs.microsoft.com/intune/device-group-mapping), uživatelům s Windows 10 se po registraci prostřednictvím tlačítka **Připojit** v **Nastavení** > **Účty** > **Přístup do práce nebo do školy** nebo při prvním zapnutí počítače zobrazí výzva k výběru kategorie zařízení.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Cílení zásad dodržování předpisů na zařízení ve skupinách zařízení <!--1307012 -->

Budete moct cílit zásady dodržování předpisů na uživatele ve skupinách uživatelů. Budete moct cílit zásady dodržování předpisů na zařízení ve skupinách zařízení.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Šifrovaná data Windows Information Protection (WIP) ve výsledcích hledání ve Windows <!-- 1469193 -->

Nové nastavení v zásadách Windows Information Protection (WIP) vám umožní řídit, jestli se mají do výsledků hledání ve Windows zahrnovat šifrovaná data WIP.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Vzdálený tisk přes zabezpečenou síť <!-- 1709994  -->
Řešení PrinterOn pro bezdrátový mobilní tisk umožní uživatelům vzdáleně tisknout odkudkoli a kdykoli přes zabezpečenou síť. PrinterOn se integruje s Intune App SDK pro iOS i Android. Zásady ochrany aplikací budete moct cílit na tuto aplikaci pomocí okna **Zásady ochrany aplikací** v Intune v konzole pro správu. Koncoví uživatelé si budou moct stáhnout aplikaci PrinterOn for Microsoft prostřednictvím Obchodu Play nebo iTunes a pak ji používat ve svém ekosystému Intune.



### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>Rozhraní Microsoft Graph API pro Intune – obecná dostupnost <!-- 1833289 -->
Rozhraní Intune API v Microsoft Graphu budou poskytovat programový přístup k datům a metodám, aby se umožnila automatizace akcí správy služby Intune.  Díky **obecné dostupnosti** těchto rozhraní API budou moct zákazníci, partneři a vývojáři využívat tato rozhraní API k integraci s interními nebo komerčními řešeními, která vyžadují podporu Intune nebo jiných služeb Microsoftu, které jsou dostupné prostřednictvím Microsoft Graphu, nebo s těmito službami souvisejí.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Zásady ochrany aplikací  <!-- 679615 -->
Zásady Intune App Protection nabízejí možnost vytvoření globálních výchozích zásad, které rychle aktivují ochranu přes všechny uživatele v celém tenantovi.

### <a name="new-ios-device-action------1244701---"></a>Nová akce pro zařízení s iOSem  <!-- 1244701 -->
Zařízení s iOSem 10.3, která jsou pod dohledem, je možné vypnout. Tato akce vypne zařízení okamžitě, bez upozornění pro koncového uživatele. Akci **Vypnout (jen pod dohledem)** najdete ve vlastnostech zařízení, když zařízení vyberete v úloze **Zařízení**.

### <a name="intune-provides-the-account-move-operation-----1573558-1579830---"></a>Intune poskytuje operaci přesunutí účtu <!-- 1573558, 1579830 -->
Funkce **Přesunutí účtu** migruje tenanta z jedné jednotky škálování Azure (ASU) do jiné. Funkci **Přesunutí účtu** lze použít jak pro scénář zahájený zákazníkem, kdy o přesunutí požádáte tým podpory Intune, tak pro scénář řízený společností Microsoft, kdy musí Microsoft provést úpravy služby na straně back-end. Během **Přesunutí účtu** tenant přejde do režimu jen pro čtení (ROM). Operace služby, jako je registrace, přejmenování zařízení nebo aktualizuje stavu dodržování předpisů, se během režimu jen pro čtení nezdaří.

Změna řeší nejasnosti v případě, kdy je jedna aplikace přiřazena k více skupinám s různými záměry aplikace.

Pokud byste chtěli aplikaci zpřístupnit na portálu pro informační pracovníky a na Portálu společnosti před listopadovým vydáním služby, máte dvě možnosti:

1. Odeberte u skupiny přiřazení **Neužívá se**.
2. Vytvořte novou skupinu, která nezahrnuje členy s přiřazeným záměrem **Povinné a K dispozici**, a přiřaďte tuto skupinu jako **Neužívá se**.

Další informace najdete v článku [Jak přiřadit aplikace do skupin pomocí Microsoft Intune](apps-deploy.md).

> [!Note]
> Po vydání už nebudete moct v klasické konzole Intune zobrazit ani změnit přiřazení aplikací správy mobilních zařízení. K přiřazení aplikací ale můžete použít konzolu Azure nebo rozhraní Intune Graph API.

### <a name="configure-an-ios-app-pin----1586774---"></a>Konfigurace kódu PIN pro aplikaci pro iOS <!-- 1586774 -->
Už brzy budete moct u cílených aplikací pro iOS vyžadovat kód PIN. Na portálu Azure Portal můžete nakonfigurovat požadavek na kód PIN a datum vypršení jeho platnosti (ve dnech). V případě potřeby bude uživatel muset nastavit a použít nový kód PIN, aby se dostal k aplikaci pro iOS. Tuto funkci budou podporovat jenom aplikace pro iOS, u kterých je povolená ochrana aplikace pomocí sady Intune App SDK.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Aktualizace uživatelského prostředí aplikace Portál společnosti pro iOS <!--1412866-->

Připravujeme k vydání důležitou aktualizaci uživatelského prostředí aplikace Portál společnosti pro iOS. Tato aktualizace bude mít zcela přepracovaný vizuální design, který bude zahrnovat modernizaci vzhledu a chování a lepší použitelnost a přístupnost. Všechny aktuální funkce aplikace Portál společnosti pro iOS budou zachované.

V rámci programu Apple TestFlight vám nabízíme předprodejní verzi aktualizované aplikace Portál společnosti pro iOS, abyste si ji mohli vyzkoušet a sdělit nám svoje názory. Pro přístup k programu TestFlight se zaregistrujte na https://aka.ms/intune_ios_cp_testflight. 

![obrázky upoutávek na novou aplikaci Portál společnosti pro iOS](./media/ios-cp-app-redesign-1801-teaser.png)

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Webové stránky Azure Active Directory můžou vyžadovat aplikaci Intune Managed Browser a podporovat jednotné přihlašování pro Managed Browser (Public Preview) <!-- 710595 -->   
Pomocí Azure Active Directory (Azure AD) budete moct přístup k webovým stránkám na mobilních zařízeních omezit na aplikaci Intune Managed Browser. V Managed Browseru zůstanou data webových stránek zabezpečená a oddělená od osobních dat koncových uživatelů. Kromě toho bude Managed Browser podporovat možnosti jednotného přihlašování pro weby chráněné pomocí Azure AD. Přihlášení k Managed Browseru nebo jeho používání na zařízení s jinou aplikací, kterou spravuje Intune, umožňuje, aby měl Managed Browser přístup k podnikovým webům chráněným pomocí Azure AD, aniž by uživatel musel zadávat své přihlašovací údaje. Tato funkce se vztahuje na weby jako Outlook Web Access (OWA) a SharePoint Online i na jiné podnikové weby jako prostředky v intranetu, ke kterým se přistupuje prostřednictvím proxy aplikace Azure.

<!-- the following are present prior to 1709 -->
### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune App Protection a nástroje pro vývoj Citrix MDX <!-- 709185 -->
Můžete spravovat zařízení a aplikace s kombinací Citrix XenMobile MDX a Microsoft Intune. To umožňuje spravovat aplikace pomocí zásad ochrany aplikací Intune při použití technologie mVPN společnosti Citrix.

Můžete najít úložiště kódu, které obsahuje Intune App Wrapping Tool a sadu Intune App SDK pro iOS a Android, a využít integraci s technologií Citrix MDX mVPN.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-the-new-company-portal-app---1380728--"></a>Přesměrování uživatelů macOS na novou aplikaci Portál společnosti <!--1380728-->   
Když se koncový uživatel přihlásí k webu Portál společnosti, aby zaregistroval svoje zařízení s macOS, bude přesměrován na to, aby proces dokončil stažením nové aplikace Portál společnosti pro macOS. K tomu dojde na zařízeních s macOS používajících OS X El Capitan 10.11 nebo novější. 

<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Podpora Intune Managed Browser pro iOS a Android <!-- 1374196 -->
Od října 2017 bude aplikace Intune Managed Browser pro Android podporovat jen zařízení se systémem Android 4.4 a novější. Aplikace Intune Managed Browser pro iOS bude podporovat jen zařízení se systémem iOS 9.0 a novější. Starší verze systému Android a iOS budou moct Managed Browser dál používat, ale nepůjde do nich nainstalovat nové verze této aplikace a nebudou mít přístup ke všem jejím možnostem. Doporučujeme vám tato zařízení aktualizovat na podporovanou verzi operačního systému.

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Vylepšená chybová zpráva, když uživatel dosáhne maximálního povoleného počtu zařízení k registraci <!-- 1270370 -->
Místo obecné chybové zprávy se koncovým uživatelům používajícím zařízení s Androidem zobrazí popisná chybová zpráva, na kterou se dá reagovat: „Zaregistrovali jste maximální počet zařízení, který povoluje váš IT správce. Odeberte prosím zaregistrované zařízení, nebo se obraťte s žádostí o pomoc na IT správce.“



## <a name="notices"></a>Sdělení

V současné době nejsou aktivní žádná sdělení.



### <a name="see-also"></a>Viz taky
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).


