---
title: Časná edice
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ad49b983bd5dc72a3355cba5645192456a555e38
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321250"
---
# <a name="the-early-edition-for-microsoft-intune---july-2018"></a>Časná edice Microsoft Intune – červenec 2018

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


### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Hromadné odstranění zařízení v okně Zařízení <!-- 1793693 -->
V okně Zařízení bude možné odstranit více zařízení najednou. Zvolte **Zařízení** > **Všechna zařízení** > vyberte zařízení, která chcete odstranit > **Odstranit**. U zařízení, která nejde odstranit, se zobrazí upozornění.

### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Nový konfigurační profil Wi-Fi zařízení pro Windows 10 a novější <!-- 1879077 -->
V současné době můžete importovat a exportovat profily Wi-Fi pomocí souborů XML. Nově bude možné vytvořit konfigurační profil Wi-Fi zařízení přímo v Intune, podobně jako na některých jiných platformách.

Pokud chcete vytvořit profil, otevřete položku **Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** > **Wi-Fi**. 

Platí pro Windows 10 a novější.

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
