---
title: Časná edice
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: fbe8cc0fc3e835ee5807dfbe56ea1aa3c728547e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184722"
---
# <a name="the-early-edition-for-microsoft-intune---november-2018"></a>Časná edice Microsoft Intune – listopad 2018

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

<!-- 1811 start -->

### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Odinstalace aplikací na zařízeních s iOSem ve vlastnictví společnosti pod dohledem <!-- 1281677 -->
Na zařízeních s iOSem ve vlastnictví společností pod dohledem budete moci odebrat libovolnou aplikaci. Libovolnou aplikaci můžete odebrat, když cílem přiřazení typu **Odinstalovat** budou skupiny uživatelů nebo zařízení. U zařízení s iOSem, která jsou osobní nebo nejsou pod dohledem, budete nadále moci odebrat jen aplikace, které byly nainstalované pomocí Intune.

### <a name="track-installation-of-office-proplus---2620217--"></a>Sledování instalace Office ProPlus <!--2620217-->
Pomocí [stránky se stavem registrace](windows-enrollment-status.md) budete moci sledovat průběh instalace [Office ProPlus](apps-add-office365.md).

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133--"></a>Podpora Programu registrace zařízení s macOS pro účty Apple School Manageru <!--3006133-->
Intune bude pro účty Apple School Manageru podporovat použití Programu registrace zařízení na zařízeních s macOS.

### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Dočasné pozastavení beznabídkového režimu na zařízeních s Androidem kvůli provedení změn <!-- 3041935 -->
Při používání zařízení s Androidem v beznabídkovém režimu s více aplikacemi může správce IT potřebovat udělat v zařízení změny. Nové nastavení beznabídkového režimu s více aplikacemi umožní správcům IT dočasně pozastavit tento režim pomocí kódu PIN a získat tak přístup k celému zařízení.
Aktuální nastavení beznabídkového režimu najdete v článku [Nastavení beznabídkového režimu Androidu](android-kiosk-settings.md).

### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Nastavení vlastního pozadí v aplikaci Managed Home Screen <!-- 3041945 -->
Přidáme nastavení, které vám umožní přizpůsobit vzhled pozadí aplikace Managed Home Screen na zařízeních s Androidem Enterprise v beznabídkovém režimu s více aplikacemi.  Pokud chcete nakonfigurovat **vlastní adresu URL pozadí**, na webu Azure Portal přejděte na Intune > Konfigurace zařízení. Vyberte aktuální profil konfigurace zařízení nebo vytvořte nový a upravte nastavení beznabídkového režimu.

### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Povolení virtuálního tlačítka Domů na zařízeních s Androidem Enterprise v beznabídkovém režimu <!-- 3042021 -->
Nové nastavení umožní uživatelům klepnutím na softwarové tlačítko přepínat mezi aplikací Managed Home Screen a jinými přiřazenými aplikacemi na zařízení v beznabídkovém režimu s více aplikacemi. Toto nastavení je zvláště užitečné v situacích, kdy beznabídková aplikace uživatele nereaguje správně na tlačítko Zpět. Toto nastavení budete moci nakonfigurovat pro zařízení s Androidem ve vlastnictví firmy pro použití s jednou aplikací. Pokud chcete nakonfigurovat **Virtuální tlačítko Domů**, na webu Azure Portal přejděte na Intune > Konfigurace zařízení. Vyberte aktuální profil konfigurace zařízení nebo vytvořte nový a upravte nastavení beznabídkového režimu.

### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Uložení a použití přiřazení zásad ochrany aplikací <!-- 3104570 -->
Nad přiřazeními zásad ochrany aplikací budete mít lepší kontrolu. Protože přiřazení zásad ochrany aplikací budete moci uložit a použít, budou zásadami ochrany aplikací přímo ovlivněni jen zamýšlení uživatelé.

### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Nová nastavení prohlížeče Microsoft Edge pro Windows 10 a novější <!-- 3174639 -->
Bude přidáno nové nastavení, které umožní řídit a spravovat prohlížeč Microsoft Edge v zařízeních. Seznam aktuálních nastavení najdete v článku o [omezení zařízení s Windows 10 (a novějšími verzemi)](device-restrictions-windows-10.md#microsoft-edge-browser).

### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Výběr aplikací sledovaných na stránce se stavem registrace<!-- 2531007 -->
Budete moci zvolit, které aplikace se sledují na stránce se stavem registrace.

### <a name="intune-app-protection-policies-ui-update----3251427---"></a>Aktualizace uživatelského rozhraní zásad ochrany aplikací Intune <!-- 3251427 -->

Zásady ochrany aplikací Intune umožňují pro aplikace chráněné přes Intune (například Microsoft Outlook a Word) nakonfigurovat různá nastavení ochrany dat. Popisky těchto nastavení a tlačítek měníme tak, aby byly srozumitelnější. Tyto ovládací prvky se změní z typu **ano**/**ne** primárně na typ **blokovat**/**povolit** a **zakázat**/**povolit** a rovněž se vylepší srozumitelnost popisků. Také formát těchto nastavení se změní tak, aby nastavení a popisek byly v ovládacím prvku vedle sebe, což zlepší navigaci. Výchozí nastavení a mnohá další nastavení zůstanou nedotčená, tato změna ale umožní uživatelům snadnější pochopení, navigaci a využití těchto nastavení při aplikování vybraných zásad ochrany aplikací.



<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Použití Microsoftem doporučených nastavení se standardními hodnotami zabezpečení <!-- 2055484 -->
Intune se integruje s dalšími službami, které se zaměřují na zabezpečení, včetně Ochrany ATP v programu Windows Defender a Ochrany ATP v Office 365. Zákazníci požadují ve službách Microsoft 365 společnou strategii a soudržnější sadu ucelených bezpečnostních pracovních postupů. Naším cílem je srovnat strategie tak, abychom mohli vytvářet řešení přemosťující operace zabezpečení a běžné úlohy správy. V Intune se snažíme tohoto cíle dosáhnout prostřednictvím publikování sady Standardních hodnot zabezpečení doporučených Microsoftem (**Intune** > **Standardní hodnoty zabezpečení**).  Správce bude moct vytvářet zásady zabezpečení přímo z těchto standardních hodnot a potom je nasazovat svým uživatelům. Doporučení osvědčených postupů může upravit tak, aby vyhovovala potřebám jeho organizace. Intune zajišťuje, že zařízení zůstávají v souladu s těmito standardními hodnotami, a upozorní správce, pokud uživatelé nebo zařízení tyto hodnoty nedodržují.

### <a name="scope-tags-for-apps---1081941---"></a>Značky oboru pro aplikace <!--1081941 -->
Budete moct vytvářet značky oboru a omezovat s jejich pomocí přístup k prostředkům Intune. Přidejte značku oboru k přiřazení role a poté přidejte značku oboru ke konfiguračnímu profilu. Daná role bude mít přístup pouze k prostředkům s konfiguračními profily, které mají odpovídající značky oboru (nebo žádnou značku oboru).
Pokud chcete vytvořit značku oboru, vyberte **Role Intune** > **Obor (značky)** > **Vytvořit**.
Značku oboru přidáte k přiřazení role tak, že zvolíte **Role Intune** > **Všechny role** > **Správce zásad a profilů** > **Přiřazení** > **Obor (značky)**.
Ke konfiguračnímu profilu přidáte značku oboru tak, zvolíte **Konfigurace zařízení** > **Profily** > vyberete profil > **Vlastnosti** > **Obor (značky)**.

### <a name="tenant-health-dashboard----1124854---"></a>Řídicí panel Stav tenanta <!-- 1124854 -->
Stránka Stav tenanta v Intune vám poskytne informace o stavu tenanta na jednom místě. Stránka je rozdělená do 4 částí:  
- **Podrobnosti o tenantovi**: obsahuje informace, jako je například autorita MDM, celkový počet zařízení zaregistrovaných ve vašem tenantovi a počet vašich licencí. Tato část také obsahuje aktuální vydanou verzi služby pro vašeho tenanta.
- **Stav konektoru**: obsahuje informace pro nakonfigurované konektory, jako je třeba Apple VPP, Windows Store pro firmy a konektory Certificate Connectors. Na základě jejich aktuálního stavu jsou konektory označené jako *V pořádku*, *Upozornění* nebo *Není v pořádku*.
- **Stav služby Intune**: obsahuje aktivní incidenty nebo výpadky vašeho tenanta. Informace v této části se načítají přímo z centra zpráv Office ([https://portal.office.com](https://portal.office.com)).
- **Novinky v Intune**: obsahuje aktivní zprávy pro vašeho tenanta, které zahrnují například oznámení, že váš tenant obdržel nejnovější funkce Intune. Informace v této části se načítají přímo z centra zpráv Office ([https://portal.office.com](https://portal.office.com)).


### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Nasazené zásady WIP bez registrace uživatele <!-- 1434452 -->
Zásady Windows Information Protection (WIP) budou k dispozici pro nasazení, aniž by se vyžadovalo, aby si uživatelé MDM zaregistrovali svá zařízení s Windows 10. Tato konfigurace umožňuje společnostem chránit jejich podnikové dokumenty na základě konfigurace WIP a zároveň umožňuje uživatelům uchovat si správu svých vlastních zařízení s Windows. Jakmile jsou dokumenty chráněny zásadami WIP, mohou být chráněná data selektivně vymazána správcem služby Intune. Výběrem uživatele a zařízení a odesláním žádosti o vymazání se veškerá data chráněná prostřednictvím zásad WIP stanou nepoužitelnými. V Intune na portálu Azure Portal vyberte **Mobilní aplikace** > **Selektivní vymazání aplikace**.


<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Nastavení zásady ochrany aplikací (APP) pro webová data <!-- 2662995 -->
Nastavení zásad ochrany aplikací (APP) pro webový obsah na zařízeních s Androidem a iOS bude aktualizované, aby lépe pracovalo s webovými odkazy http a https a také s přenosy dat prostřednictvím univerzálních odkazů iOS a odkazů aplikací pro Android.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token Apple VPP používá jiný produkt MDM <!-- 1488946 -->
Intune rozpozná situaci, kdy se token programu hromadných nákupů (VPP) společnosti Apple používá v Intune a zároveň v jiném produktu MDM, a zobrazí podrobnosti.

### <a name="ios-and-macos-version-numbers-and-build-numbers-are-available-in-compliance-policies----1892471---"></a>V zásadách dodržování předpisů jsou dostupná čísla verzí a buildů pro iOS a macOS <!-- 1892471 -->
V oblasti **Dodržování předpisů zařízením** > **Dodržování předpisů zařízením** se zobrazují verze operačního systému iOS a macOS, která lze použít v zásadách dodržování předpisů. V některé z budoucích aktualizací půjde u obou platforem nakonfigurovat i číslo buildu.

Při vydání aktualizací zabezpečení společnost Apple obvykle ponechává stávající číslo verze, ale aktualizuje číslo buildu. Pomocí čísla buildu v zásadách dodržování předpisů můžete snadno zkontrolovat, jestli je nainstalovaná aktualizace řešící ohrožení zabezpečení.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Vyřazená zařízení na řídicím panelu Dodržování předpisů zařízením <!-- 1981119 -->
V budoucí aktualizaci se z řídicího panelu Dodržování předpisů zařízením odeberou vyřazená zařízení. Změní se tím číselné údaje týkající se dodržování předpisů.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Změna v procesu aktualizace pro místní konektory <!-- 2277554 -->
Na základě zpětné vazby od zákazníků se změní způsob, jak se aktualizují místní konektory. Po prvotní instalaci místního konektoru budou aktualizace probíhat automaticky. Tato změna začne s novým konektor certifikátu PFX pro Microsoft Intune a následně bude zavedena u dalších typů místních konektorů. 

<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Kontrola Configuration Manageru z hlediska dodržování předpisů <!-- 2192052 -->
Budoucí aktualizace bude obsahovat nové nastavení pro dodržování předpisů System Center Configuration Manageru (**Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**  > **Windows 10**). Configuration Manager bude posílat signály funkci dodržování předpisů v Intune. V Intune můžete nastavit požadavek, aby všechny signály Configuration Manageru hlásily vyhovující stav.

Můžete například vyžadovat, aby v zařízeních byly nainstalované všechny aktualizace softwaru. V Configuration Manageru má tento požadavek stav Nainstalováno. Pokud některé programy v zařízení budou v neznámém stavu, bude se zařízení v Intune považovat za nevyhovující předpisům.

Platí pro Windows 10 a novější.

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Upozornění na vypršení platnosti tokenu VPP nebo docházející licence pro aplikaci Portál společnosti <!-- 2237572 -->
Jestliže pomocí programu VPP (Volume Purchase Program) předběžně zřizujete portál společnosti během registrace do programu DEP, Intune vás upozorní, pokud se bude blížit konec platnosti tokenu VPP nebo pokud bude docházet počet licencí pro aplikaci Portál společnosti.



<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Sdělení

V současné době nejsou aktivní žádná sdělení.

### <a name="see-also"></a>Viz také
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).



