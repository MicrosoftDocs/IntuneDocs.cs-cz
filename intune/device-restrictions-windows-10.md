---
title: Nastavení omezení zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na seznam všech nastavení a jejich popisů pro vytváření omezení zařízení v zařízeních s Windows 10 a novějším. Pomocí těchto nastavení můžete v konfiguračním profilu řídit snímky obrazovky, požadavky na heslo, nastavení veřejného terminálu, aplikace v obchodě, prohlížeči Microsoft Edge, Windows Defender, přístup ke cloudu, nabídce Start a další informace v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/13/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7c75930f3eee35146afbc5714135ececbe7c9643
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69550178"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>Nastavení zařízení s Windows 10 (a novějším) pro povolení nebo omezení funkcí pomocí Intune

Tento článek obsahuje seznam a popis všech různých nastavení, která můžete řídit na zařízeních s Windows 10 a novějším. V rámci řešení pro správu mobilních zařízení (MDM) pomocí těchto nastavení můžete povolit nebo zakázat funkce, nastavit pravidla pro hesla, upravit zamykací obrazovku, použít program Windows Defender a další.

Tato nastavení se přidají do konfiguračního profilu zařízení v Intune a pak se přiřadí nebo nasadí na vaše zařízení s Windows 10.

> [!Note]
> Ne všechny možnosti jsou k dispozici ve všech edicích systému Windows. Pokud chcete zobrazit podporované edice, přečtěte si téma [zásady CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) (otevře se další web společnosti Microsoft).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](device-restrictions-configure.md#create-the-profile).

## <a name="app-store"></a>App Store

Tato nastavení používají [zprostředkovatele CSP zásad ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement), který obsahuje také podporované edice Windows.

- **App Store** (jenom mobilní zařízení): **Není nakonfigurováno** (výchozí) umožňuje koncovým uživatelům přístup k obchodu s aplikacemi na mobilních zařízeních. **Blok** zabraňuje použití App Storu.
- **Automaticky aktualizovat aplikace ze Storu**: **Není nakonfigurováno** (výchozí) povolí automatickou aktualizaci aplikací nainstalovaných z Microsoft Store. **Blok** zabraňuje automatické instalaci aktualizací.
- **Instalace důvěryhodné aplikace**: Vyberte, jestli se dají nainstalovat aplikace, které neMicrosoft Store, označované taky jako zkušební načtení. Probíhá instalace zkušebního načtení a následné spuštění nebo otestování aplikace, která není certifikována Microsoft Store. Například aplikace, která je interní pro vaši společnost. Možnosti:
  - **Není nakonfigurováno** (výchozí): Používá výchozí operační systém.
  - **Blok**: Zabraňuje zkušebnímu načtení. NeMicrosoft Store aplikace se nedají nainstalovat.
  - **Povolení**: Umožňuje zkušební načtení. Je možné nainstalovat aplikace, které nejsou Microsoft Store.
- **Odemčení pro vývojáře**: Povolí vývojářům nastavení pro Windows, jako je například umožnění úprav aplikací zkušebně načtené koncovými uživateli. Možnosti:
  - **Není nakonfigurováno** (výchozí): Používá výchozí operační systém.
  - **Blok**: Znemožní vývojářský režim a aplikace pro zkušební načtení.
  - **Povolení**: Umožňuje vývojářský režim a aplikace pro zkušební načtení.

  [Povolit pro vývoj zařízení](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development) Další informace o této funkci.

- **Data sdílené uživatelské aplikace**: Vyberte možnost **umožňuje** sdílet data aplikací mezi různými uživateli na jednom zařízení a dalšími instancemi této aplikace. **Není nakonfigurováno** (výchozí) znemožní sdílet data s ostatními uživateli a dalšími instancemi stejné aplikace.
- **Použít pouze privátní úložiště**: **Povoluje** , aby se aplikace stáhly jenom z privátního úložiště a nestáhly se z veřejného úložiště, včetně maloobchodního katalogu. **Není nakonfigurováno** (výchozí) umožňuje, aby se aplikace stáhly z privátního úložiště a veřejného úložiště.
- **Spuštění aplikace pocházející ze Storu**: **Blokování** zakáže všechny aplikace, které byly v zařízení předem nainstalovány, nebo stažené z Microsoft Store. **Není nakonfigurováno** (výchozí) umožňuje, aby se tyto aplikace otevíraly.
- **Nainstalovat data aplikací na systémový svazek**: **Blok** zastaví aplikacím ukládat data na systémový svazek zařízení. **Není nakonfigurováno** (výchozí) umožňuje aplikacím ukládat data na svazek systémového disku.
- **Nainstalovat aplikace na systémovou jednotku**: **Blok** zabraňuje instalaci aplikací na systémovou jednotku na zařízení. **Není nakonfigurováno** (výchozí) umožňuje aplikacím instalovat na systémovou jednotku.
- **Zadvr hry** (jenom desktopové počítače): **Blok** zakáže záznam a vysílání her systému Windows. **Není nakonfigurováno** (výchozí) umožňuje zaznamenávání a vysílání her.
- **Jenom aplikace ze Storu**: Toto nastavení určuje uživatelské prostředí, když uživatelé nainstalují aplikace z jiných míst než z Microsoft Store. Možnosti:

  - **Není nakonfigurováno** (výchozí): Umožňuje koncovým uživatelům instalovat aplikace z jiných míst než z Microsoft Store, včetně aplikací definovaných v jiných nastaveních zásad.  
  - **Kdekoli**: Vypne doporučení pro aplikace a umožní uživatelům instalovat aplikace z libovolného místa.  
  - **Jenom úložiště**: Vynutí koncové uživatele instalovat aplikace z Microsoft Store.
  - **Doporučení**: Při instalaci aplikace z webu, který je k dispozici v Microsoft Store, se uživatelům zobrazí zpráva doporučující si ji stáhnout ze Storu.  
  - **Preferovat úložiště**: Upozorňuje uživatele, když instalují aplikace z jiných míst než z Microsoft Store.

  [Zprostředkovatel SmartScreen/EnableAppInstallControl CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen#smartscreen-enableappinstallcontrol)

- **Vynutit restartování aplikací při selhání aktualizace**: Při použití aplikace se nemusí aktualizovat. Pomocí tohoto nastavení vynutíte restartování aplikace. **Není nakonfigurováno** (výchozí) nevynutí restartování aplikací. **Vyžadovat** , aby správci vynutili restartování pro určité datum a čas, nebo podle plánu opakování. Pokud je nastaveno na **vyžadovat**, zadejte také:

  - **Datum a čas zahájení**: Vyberte konkrétní datum a čas pro restartování aplikací.
  - **Opakování**: Vyberte denní, týdenní nebo měsíční restart.

  [ApplicationManagement/ScheduleForceRestartForUpdateFailures CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

- **Uživatelský ovládací prvek pro instalaci**: Pokud je nastavené na Nenakonfigurováno (výchozí), Instalační služba systému Windows zabránit uživatelům měnit možnosti instalace obvykle rezervované pro správce systému, jako je například zadání adresáře pro instalaci souborů. **Blok** umožňuje uživatelům změnit tyto možnosti instalace a některé z instalační služba systému Windows funkcí zabezpečení jsou vynechány.

  [ApplicationManagement/MSIAllowUserControlOverInstall CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msiallowusercontroloverinstall)

- **Instalace aplikací se zvýšenými oprávněními**: Pokud nastavíte hodnotu Nenakonfigurováno (výchozí), systém použije oprávnění aktuálního uživatele při instalaci programů, které správce systému neinstaluje nebo nenabízí. Zablokuje Instalační služba systému Windows, aby při instalaci jakéhokoli programu do systému používal zvýšené oprávnění. Tato oprávnění se rozšiřují na všechny programy.

  [CSP ApplicationManagement/MSIAlwaysInstallWithElevatedPrivileges](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msialwaysinstallwithelevatedprivileges)

- **Aplikace po spuštění**: Zadejte seznam aplikací, které se otevřou, když se uživatel přihlásí k zařízení. Nezapomeňte použít středníkem oddělený seznam názvů (PFN) aplikací pro Windows, které jsou odděleny středníky. Aby tyto zásady fungovaly, musí manifest v aplikacích pro Windows používat úlohu po spuštění.

  [ApplicationManagement/LaunchAppAfterLogOn CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-launchappafterlogon)

Vyberte **OK** uložte provedené změny.

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení

Tato nastavení používají [zásady připojení](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) a zprostředkovatele kryptografických služeb sítě [Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) , které také uvádějí podporované edice Windows.

- [CSP zásad sítě Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi)

- **Mobilní datový kanál**: Vyberte, jestli koncoví uživatelé můžou používat data, jako je procházení webu, při připojení k mobilní síti. Možnosti:
  - **Není nakonfigurováno** (výchozí): Používá výchozí operační systém, který může umožňovat mobilní datový kanál. Koncoví uživatelé ji můžou vypnout.
  - **Blok**: Nepovolujte mobilní datový kanál. Koncoví uživatelé je nemůžou zapnout.
  - **Povoleno (není možné upravovat)** : Povoluje mobilní datový kanál. Koncoví uživatelé ji nemohou vypnout.

- **Roaming dat**: **Blok** zabraňuje roamingu mobilních dat na zařízení. **Není nakonfigurováno** (výchozí) umožňuje roaming mezi sítěmi při přístupu k datům.
- **VPN v mobilní síti**: **Blok** zabraňuje zařízení, aby při připojení k mobilní síti přistupovala k připojením VPN. **Není nakonfigurováno** (výchozí) umožňuje síti VPN používat jakékoli připojení, včetně mobilních.
- **Roaming VPN v mobilní síti**: **Blok** zabrání zařízení v přístupu k připojením VPN při roamingu v mobilní síti. **Není nakonfigurováno** (výchozí) povolí připojení VPN při roamingu.
- **Služba připojených zařízení**: **Blok** zakáže komponentu platformy připojených zařízení (CDP). CDP umožňuje zjišťování a připojení k ostatním zařízením (přes Bluetooth/LAN nebo Cloud), aby podporovala spouštění vzdálených aplikací, vzdálené zasílání zpráv, relace vzdálených aplikací a další prostředí pro různé zařízení. **Není nakonfigurováno** (výchozí) povolí službu připojená zařízení, která umožňuje zjišťování a připojování k ostatním zařízením Bluetooth.
- **NFC**: **Blok** zabraňuje schopnostem technologie NFC (Near Field Communication). **Není nakonfigurováno** (výchozí) umožňuje uživatelům povolit a konfigurovat funkce NFC na zařízení.
- **Wi-Fi**: **Blok** zabraňuje uživatelům v zařízení povolit, konfigurovat a používat připojení Wi-Fi. **Není nakonfigurováno** (výchozí) umožňuje připojení Wi-Fi.
- **Automaticky se připojovat k Wi-Fi hotspotům**: **Blokování** znemožňuje zařízení automaticky se připojovat k Wi-Fi hotspotům. **Není nakonfigurováno** (výchozí) umožňuje zařízením automaticky se připojovat k bezplatným Wi-Fi hotspotům a automaticky pro připojení přijímat jakékoli podmínky a ujednání.
- **Ruční konfigurace Wi-Fi**: **Blokování** brání zařízením v připojení k Wi-Fi mimo sítě instalované na MDM serveru. **Není nakonfigurováno** (výchozí) umožňuje koncovým uživatelům přidat a nakonfigurovat svoje vlastní síťové identifikátory SSID pro připojení Wi-Fi.
- **Interval prohledávání sítě Wi-Fi**: Zadejte, jak často zařízení hledají sítě Wi-Fi. Zadejte hodnotu od 1 (nejčastější) do 500 (nejméně časté). Výchozí hodnota `0` je (nula).

### <a name="bluetooth"></a>Bluetooth

Tato nastavení používají [poskytovatele zásad Bluetooth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth). Zobrazuje se taky podporované edice Windows.

- **Bluetooth**: **Blok** zabraňuje uživatelům povolit Bluetooth. **Není nakonfigurováno** (výchozí) povolí Bluetooth na zařízení.
- **Zjistitelnost Bluetooth**: **Blok** zabraňuje tomu, aby zařízení bylo zjistitelná jinými zařízeními podporujícími technologii Bluetooth. **Není nakonfigurováno** (výchozí) umožňuje zjistit zařízení pomocí jiných zařízení s podporou technologie Bluetooth, jako je například sluchátka s mikrofonem.
- **Předběžná párování Bluetooth**: **Blok** zabraňuje tomu, aby určitá zařízení Bluetooth byla automaticky spárována s hostitelským zařízením. **Není nakonfigurováno** (výchozí) umožňuje automatické párování s hostitelským zařízením.
- **Inzerce Bluetooth**: **Blok** zabraňuje tomu, aby zařízení odesílalo reklamy Bluetooth. **Není nakonfigurováno** (výchozí) povolí zařízení odesílat reklamy přes Bluetooth.
- **Povolené služby Bluetooth**: **Přidejte** seznam povolených služeb a profilů Bluetooth jako šestnáctkové řetězce, například `{782AFCFC-7CAA-436C-8BF0-78CD0FFBD4AF}`.

  [Průvodce používáním ServicesAllowedList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#servicesallowedlist-usage-guide) obsahuje další informace o seznamu služeb.

Vyberte **OK** uložte provedené změny.

## <a name="cloud-and-storage"></a>Cloud a úložiště

Tato nastavení používají [CSP v zásadách účtů](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts); Zobrazuje se taky podporované edice Windows.

- **Účet Microsoft**: **Blok** zabraňuje koncovým uživatelům v přidružení účet Microsoft k zařízení. **Není nakonfigurováno** (výchozí) umožňuje přidat a použít účet Microsoft.
- **Bez účet Microsoft**: **Blok** zabraňuje koncovým uživatelům v přidávání účtů mimo Microsoft pomocí uživatelského rozhraní. **Není nakonfigurováno** (výchozí) umožňuje uživatelům přidávat e-mailové účty, které nejsou přidružené k účet Microsoft.
- **Synchronizace nastavení pro účet Microsoft**: **Není nakonfigurováno** (výchozí) povolí synchronizaci nastavení zařízení a aplikací přidružených k účet Microsoft k synchronizaci mezi zařízeními. **Blok** zabraňuje této synchronizaci.
- **Pomocník pro přihlášení k účtu Microsoft**: Pokud je nastavené na Nenakonfigurováno (výchozí), koncoví uživatelé můžou spustit a zastavit službu **Microsoft account Signing Assistant** (wlidsvc). Tato služba operačního systému umožňuje uživatelům přihlašovat se k jejich účet Microsoft. **Disable** znemožní koncovým uživatelům řídit službu pomocníka pro přihlášení k Microsoftu (wlidsvc).

Vyberte **OK** uložte provedené změny.

## <a name="cloud-printer"></a>Cloudová tiskárna

Tato nastavení používají [zprostředkovatele CSP v zásadách EnterpriseCloudPrint](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-enterprisecloudprint). Zobrazuje se taky podporované edice Windows.

- **Adresa URL pro zjišťování tiskáren**: Zadejte adresu URL pro hledání cloudových tiskáren. Zadejte například `https://cloudprinterdiscovery.contoso.com`.
- **Adresa URL autority pro přístup k tiskárně**: Zadejte adresu URL koncového bodu ověřování, abyste získali tokeny OAuth. Zadejte například `https://azuretenant.contoso.com/adfs`.
- **GUID nativní klientské aplikace Azure**: Zadejte identifikátor GUID klientské aplikace, kterým se povoluje získat tokeny OAuth z OAuthAuthority. Zadejte například `E1CF1107-FF90-4228-93BF-26052DD2C714`.
- **Identifikátor URI prostředku tiskové služby**: Zadejte identifikátor URI prostředku OAuth pro tiskovou službu nakonfigurovanou v Azure Portal. Zadejte například `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Maximální počet tiskáren pro dotaz**: Zadejte maximální počet tiskáren, které mají být dotazovány. Výchozí hodnota je `20`.
- **Identifikátor URI prostředku služby zjišťování tiskáren**: Zadejte identifikátor URI prostředku OAuth pro službu zjišťování tiskáren nakonfigurovanou v Azure Portal. Zadejte například `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Po nastavení [tisku hybridního cloudu Windows serveru](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview)můžete tato nastavení nakonfigurovat a pak nasadit na vaše zařízení s Windows.

Vyberte **OK** uložte provedené změny.

## <a name="control-panel-and-settings"></a>Ovládací panely a nastavení

- **Aplikace nastavení**: **Blok** zabraňuje koncovým uživatelům v přístupu k aplikaci nastavení systému Windows. **Není nakonfigurováno** (výchozí) umožňuje uživatelům otevřít na zařízení aplikaci nastavení.
  - **Systém**: **Blok** znemožní přístup k systémové oblasti aplikace nastavení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
    - **Úprava nastavení napájení a režimu spánku** (jenom desktopové počítače): **Blok** znemožní koncovým uživatelům měnit nastavení napájení a režimu spánku na zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům změnit nastavení napájení a režimu spánku.
  - **Zařízení**: **Blok** znemožní přístup k oblasti zařízení v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Síť Internet**: **Blok** zabraňuje přístupu k síti & internetovou oblast aplikace nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Individuální nastavení**: **Blok** znemožní přístup k oblasti přizpůsobení aplikace nastavení v zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Aplikace**: **Blok** znemožní přístup k oblasti aplikace v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Účty**: **Blok** znemožní přístup k oblasti účtů aplikace nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Čas a jazyk**: **Blok** znemožní přístup k oblasti času & jazyka aplikace nastavení v zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
    - **Změna systémového času**: **Blok** znemožní koncovým uživatelům měnit nastavení data a času v zařízení. **Není nakonfigurováno** umožňuje uživatelům změnit tato nastavení.
    - **Úprava nastavení oblasti** (jenom desktopové počítače): **Blok** znemožní koncovým uživatelům měnit nastavení oblasti na zařízení. **Není nakonfigurováno** umožňuje uživatelům změnit tato nastavení.
    - **Změny nastavení jazyka (jenom desktopové verze)** : **Blok** znemožní koncovým uživatelům změnit nastavení jazyka v zařízení. **Není nakonfigurováno** umožňuje uživatelům změnit tato nastavení.

      [Zásady nastavení – CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings)

  - **Hraní her**: **Blok** znemožní přístup k herní oblasti aplikace nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Usnadnění přístupu**: **Blok** znemožní přístup k oblasti snadného přístupu v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Ochrana osobních údajů**: **Blok** znemožní přístup k oblasti soukromí v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Aktualizace a zabezpečení**: **Blok** zabraňuje přístupu k oblasti aktualizace & zabezpečení aplikace nastavení v zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.

Vyberte **OK** uložte provedené změny.

## <a name="display"></a>Zobrazit

Tato nastavení používají [zprostředkovatele CSP v zásadách zobrazení](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-display). Zobrazuje se taky podporované edice Windows.

Škálování DPI GDI umožňuje aplikacím, které nepodporují rozlišení DPI, přesměrovat na monitorované rozlišení DPI.

- **Zapnout ŠKÁLOVÁNÍ GDI pro aplikace**: **Přidejte** starší verze aplikací, u kterých chcete zapnout ŠKÁLOVÁNÍ dpi GDI. Zadejte například `filename.exe` nebo `%ProgramFiles%\Path\Filename.exe`.

  Měřítko DPI GDI je zapnuté pro všechny starší verze aplikací v seznamu.

- Vypnout **škálování GDI pro aplikace**: **Přidejte** starší verze aplikací, u kterých chcete ŠKÁLOVAT dpi GDI vypnuté. Zadejte například `filename.exe` nebo `%ProgramFiles%\Path\Filename.exe`.

  Měřítko DPI GDI je vypnuto pro všechny starší aplikace v seznamu.

Můžete také naimportovat soubor. CSV se seznamem aplikací.

Vyberte **OK** uložte provedené změny.

## <a name="general"></a>Obecné

Tato nastavení používají [poskytovatele cloudových zásad](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) Zobrazuje se taky podporované edice Windows. 

- **Snímek obrazovky** (jenom mobilní zařízení): **Blok** znemožní koncovým uživatelům získat na zařízení snímky obrazovky. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Kopírování a vkládání (jenom mobilní zařízení)** : **Blok** znemožní koncovým uživatelům používat kopírování a vkládání mezi aplikacemi na zařízení. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Ruční zrušení registrace**: **Blok** znemožní koncovým uživatelům odstranit pracovní účet pomocí ovládacích panelů na pracovišti na zařízení. **Není nakonfigurováno** (výchozí) povolí tuto funkci.

  Nastavení této zásady se nepoužije, pokud je počítač připojený k Azure AD a je povolená Automatická registrace.

- **Ruční instalace kořenového certifikátu** (jenom mobilní zařízení): **Blok** zabraňuje koncovým uživatelům v ruční instalaci kořenových certifikátů a zprostředkujících certifikátů Cap. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Kamera**: **Blok** znemožní koncovým uživatelům používat fotoaparát na zařízení. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Synchronizace souborů OneDrive**: **Blok** znemožní koncovým uživatelům synchronizovat soubory ze zařízení do OneDrivu. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Vyměnitelné úložiště**: **Blok** zabraňuje koncovým uživatelům v používání externích úložných zařízení, jako jsou karty SD se zařízením. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Zeměpisná poloha**: **Blok** zabraňuje koncovým uživatelům v zapínání služeb zjišťování polohy na zařízení. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Sdílení internetu**: **Blok** zabraňuje sdílení internetového připojení na zařízení. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Resetování telefonu**: **Blok** zabraňuje koncovým uživatelům v vymazání nebo obnovení továrního nastavení v zařízení. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Připojení USB**: **Blok** zabraňuje přístupu k externímu úložnému zařízení přes připojení USB na zařízení. **Není nakonfigurováno** (výchozí) povolí tuto funkci. Toto nastavení neovlivňuje zpoplatnění přes USB.
- **Režim** ochrany před krádeží (jenom mobilní zařízení): **Blok** znemožní koncovým uživatelům vybrat v zařízení preference režimu AntiTheft. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Cortana**: **Blok** zakáže hlasového asistenta Cortany na zařízení. Když je Cortana vypnutá, uživatelé můžou pořád vyhledávat položky v zařízení. **Není nakonfigurováno** (výchozí) umožňuje Cortana.
- **Záznam hlasu** (jenom mobilní zařízení): **Blok** znemožní koncovým uživatelům používat na zařízení záznam hlasu zařízení. **Není nakonfigurováno** (výchozí) umožňuje záznam hlasu pro aplikace.
- **Úprava názvu zařízení** (jenom mobilní zařízení): **Blok** znemožní koncovým uživatelům měnit název zařízení. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Přidat zřizovací balíčky**: **Blok** zabraňuje agentovi konfigurace běhu, který instaluje zřizovací balíčky na zařízení. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Odebrat zřizovací balíčky**: **Blok** zabraňuje agentovi konfigurace běhu, který ze zařízení odebírá zřizovací balíčky. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Zjišťování zařízení**: **Blok** zabraňuje tomu, aby se zařízení zjistilo jinými zařízeními. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Přepínání úloh** (jenom mobilní zařízení): **Blok** zabraňuje přepínání úloh na zařízení. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Chybový dialog SIM karty** (jenom mobilní zařízení): Zablokuje zobrazování chybových zpráv na zařízení, pokud se nezjistí žádná SIM karta. **Není nakonfigurováno** (výchozí) zobrazí chybové zprávy.
- **Pracovní prostor rukopisu**: Vyberte, jestli a jak má uživatel přístup k pracovnímu prostoru rukopisu. Možnosti:
  - **Není nakonfigurováno** (výchozí): Zapne pracovní prostor rukopisu a uživatel ho může používat nad zamykací obrazovkou.
  - **Zakázáno na zamykací obrazovce**: Pracovní prostor rukopisu je povolen a funkce je zapnutá. Ale uživatel k němu nemá přístup nad zamykací obrazovkou.
  - **Zakázáno**: Přístup k pracovnímu prostoru Ink je zakázán. Tato funkce je vypnutá.

  [CSP zásad WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace)

- **Automatické opětovné nasazení**: Vyberte **Povolit** , aby uživatelé s právy správce mohli odstranit všechna uživatelská data a nastavení pomocí **kombinace kláves Ctrl + Win + R** na zamykací obrazovce zařízení. Zařízení se automaticky překonfiguruje a znovu zaregistruje do správy. **Není nakonfigurováno** (výchozí) zabrání této funkci.
- **Vyžadovat, aby se uživatelé během instalace zařízení připojili k síti**: Vyberte možnost **vyžadovat** , aby se zařízení připojilo k síti před tím, než se během instalace systému Windows otevře stránka síť. **Není nakonfigurováno** (výchozí) umožňuje uživatelům přejít přes stránku síť, i když není připojen k síti.

  Nastavení se projeví při příštím vymazání nebo resetování zařízení. Stejně jako u jakékoli jiné konfigurace Intune musí být zařízení zaregistrované a spravované přes Intune, aby přijímalo nastavení konfigurace. Ale jakmile je zaregistrované, a když se dostávají zásady, zařízení resetuje nastavení v průběhu příští instalace Windows.

- **Přímý přístup do paměti**: **Blok** zabraňuje přímému přístupu do paměti (DMA) pro všechny PŘIPOJITELNÝCH portů PCI pro příjem po dobu, než se uživatel přihlásí do Windows. **Povoleno** (výchozí) umožňuje přístup k DMA i v případě, že uživatel není přihlášený.

  CSP: [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)

- **Ukončit procesy ze Správce úloh**: Toto nastavení určuje, zda mohou uživatelé bez oprávnění správce použít Správce úloh k ukončení úloh. **Blok** zabraňuje standardním uživatelům (bez správců) v používání Správce úloh k ukončení procesu nebo úlohy v zařízení. **Není nakonfigurováno** (výchozí) umožňuje standardním uživatelům ukončit proces nebo úlohu pomocí Správce úloh.

Vyberte **OK** uložte provedené změny.

## <a name="locked-screen-experience"></a>Prostředí zamknuté obrazovky

- **Oznámení centra akcí (jenom mobilní zařízení)** : **Blok** zabraňuje zobrazování oznámení centra akcí na zamykací obrazovce zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům zvolit, které aplikace budou zobrazovat oznámení na zamykací obrazovce.

  [AboveLock/AllowActionCenterNotifications CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowactioncenternotifications)

- **Adresa URL obrázku pro zamknutou obrazovku (jenom Desktop)** : Zadejte adresu URL obrázku ve formátu JPG, JPEG nebo PNG, který se používá jako tapeta zamykací obrazovky Windows. Zadejte například `https://contoso.com/image.png`. Toto nastavení zamkne obrázek a nedá se změnit.
- **Uživatelem konfigurovatelný časový limit obrazovky (jenom mobilní zařízení)** : Možnost **Allow** umožňuje uživatelům konfigurovat časový limit obrazovky. **Není nakonfigurováno** (výchozí) nedávají uživatelům tuto možnost.

  [DeviceLock/AllowScreenTimeoutWhileLockedUserConfig CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-allowscreentimeoutwhilelockeduserconfig)

- **Cortana na uzamčené obrazovce** (jenom desktopové počítače): **Blok** zabraňuje uživatelům v interakci s Cortana, když je zařízení na zamykací obrazovce. **Není nakonfigurováno** (výchozí) umožňuje interakci s Cortana.

  [AboveLock/AllowCortanaAboveLock CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowcortanaabovelock)

- **Informační zprávy na uzamčené obrazovce**: **Blok** zabraňuje zobrazování oznámení na zamykací obrazovce zařízení. **Není nakonfigurováno** (výchozí) Tato oznámení povolují.

  [CSP AboveLock/AllowToasts](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowtoasts)

- **Časový limit obrazovky (jenom mobilní zařízení)** : Nastavte dobu trvání (v sekundách) od zamknutí obrazovky po vypnutí obrazovky. Podporované hodnoty jsou 11-1800. Zadejte `300` například, pokud chcete nastavit tento časový limit na 5 minut.

  [CSP DeviceLock/ScreenTimeoutWhileLocked](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-screentimeoutwhilelocked)

Vyberte **OK** uložte provedené změny.

## <a name="messaging"></a>Omezován

Tato nastavení používají [zásady zasílání zpráv CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-messaging); Zobrazuje se taky podporované edice Windows.

- **Synchronizace zpráv (jenom mobilní zařízení)** : **Blok** zakáže zálohování a obnovování textových zpráv a synchronizaci zpráv mezi zařízeními s Windows. Vypnutí pomáhá zabránit ukládání informací na serverech mimo řízení organizace. **Není nakonfigurováno** (výchozí) umožňuje uživatelům měnit tato nastavení a synchronizovat jejich zprávy.
- **MMS (jenom mobilní zařízení)** : **Blok** zakáže na zařízení funkci posílání a přijímání MMS. V případě podniků použijte tuto zásadu k zakázání MMS na zařízeních v rámci požadavku auditování nebo správy. **Není nakonfigurováno** (výchozí) umožňuje odesílat a přijímat MMS.
- **RCS (jenom mobilní zařízení)** : **Blokování** zakazuje na zařízení funkce pro posílání a přijímání RCS (Rich Communication Services). V případě podniků použijte tuto zásadu k zakázání RCS na zařízeních v rámci požadavku auditování nebo správy. **Není nakonfigurováno** (výchozí) umožňuje RCS Odeslat a přijmout.

Vyberte **OK** uložte provedené změny.

## <a name="microsoft-edge-browser"></a>Prohlížeč Microsoft Edge

Tato nastavení používají [zprostředkovatele CSP zásad prohlížeče](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser), který také uvádí podporované edice systému Windows.

### <a name="use-microsoft-edge-kiosk-mode"></a>Použít celoobrazovkový režim Microsoft Edge

Dostupná nastavení se mění v závislosti na tom, co zvolíte. Možnosti:

- **Ne** (výchozí): Microsoft Edge není spuštěný v celoobrazovkovém režimu. Všechna nastavení Microsoft Edge jsou k dispozici pro změnu a konfiguraci.
- **Digitální a interaktivní podpis (veřejný terminál s jednou aplikací)** : Filtruje nastavení Microsoft Edge, která jsou platná pro digitální a interaktivní podpisový režim Microsoft Edge pro použití jenom v terminálech s jednou aplikací ve Windows 10. Toto nastavení vyberte, pokud chcete otevřít adresu URL na celé obrazovce a zobrazit jenom obsah na tomto webu. [Nastavení digitální znaménka](https://docs.microsoft.com/windows/configuration/setup-digital-signage) poskytuje další informace o této funkci.
- **Veřejné procházení InPrivate (veřejný terminál s jednou aplikací)** : Filtruje nastavení Microsoft Edge, která se vztahují ke službě InPrivate na veřejném režimu pro použití v terminálech s jednou aplikací ve Windows 10. Spustí více karet verze Microsoft Edge.
- **Normální režim (veřejný terminál s více aplikacemi)** : Filtruje nastavení Microsoft Edge, která platí pro běžný celoobrazovkový režim Microsoft Edge. Spustí plnou verzi Microsoft Edge se všemi funkcemi pro procházení.
- **Veřejné procházení (celoobrazovkový terminál s více aplikacemi)** : Filtruje nastavení Microsoft Edge, která se vztahují k veřejnému procházení veřejného terminálu pro více aplikací ve Windows 10.  Spustí na více kartách verzi Microsoft Edge InPrivate.

> [!TIP]
> Další informace o tom, co tyto možnosti dělají, najdete v článku [typy konfigurace celoobrazovkového režimu Microsoft Edge](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

Tento profil omezení zařízení přímo souvisí s profilem veřejného terminálu, který vytvoříte pomocí [Nastavení veřejného terminálu Windows](kiosk-settings-windows.md). Sumarizace:

1. Vytvořte profil [Nastavení veřejného terminálu Windows](kiosk-settings-windows.md) pro spuštění zařízení v celoobrazovkovém režimu. Jako aplikaci vyberte Microsoft Edge a v profilu veřejného terminálu nastavte celoobrazovkový režim Microsoft Edge.
2. Vytvořte profil omezení zařízení, který je popsaný v tomto článku, a nakonfigurujte konkrétní funkce a nastavení povolená v Microsoft Edge. Nezapomeňte zvolit stejný typ celoobrazovkového režimu Microsoft Edge, jak je vybraný v profilu veřejného terminálu ([Nastavení veřejného terminálu pro Windows](kiosk-settings-windows.md)). 

    [Nastavení podporovaného celoobrazovkového režimu](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-policies-for-kiosk-mode) je skvělý prostředek.

> [!IMPORTANT] 
> Ujistěte se, že tento profil Microsoft Edge přiřadíte ke stejným zařízením jako profil veřejného terminálu ([Nastavení veřejného terminálu pro Windows](kiosk-settings-windows.md)).

[ConfigureKioskMode CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)

### <a name="start-experience"></a>Úvodní prostředí

- **Spustit Microsoft Edge s**: Vyberte, které stránky se otevřou, když se spustí Microsoft Edge. Možnosti:
  - **Vlastní úvodní stránky**: Zadejte úvodní stránky, například `http://www.contoso.com`. Microsoft Edge načte úvodní stránky, které zadáte.
  - **Stránka Nová karta**: Microsoft Edge se naplní bez ohledu na nastavení **adresy URL nové karty** .
  - **Stránka poslední relace**: Microsoft Edge načte stránku poslední relace.
  - **Úvodní stránky v nastavení místní aplikace**: Microsoft Edge začíná výchozí úvodní stránkou definovanou operačním systémem.

- **Povolí uživateli měnit úvodní stránky**: **Ano** (výchozí) umožňuje uživatelům změnit úvodní stránky. Správci můžou použít `EdgeHomepageUrls` k zadání spouštěcích stránek, které se uživatelům zobrazí ve výchozím nastavení při otevření Microsoft Edge. **Žádní** uživatelé neblokují změnu úvodní stránky.
- **Stránka pro povolení webového obsahu na nové kartě**: Když nastavíte **Ano** (výchozí), Microsoft Edge otevře adresu URL zadanou v nastavení **Adresa URL nové karty** . Pokud je **Nová adresa URL karty** prázdná, Microsoft Edge otevře novou stránku karty uvedenou v nastavení Microsoft Edge. Uživatelé je mohou změnit. Pokud je nastavena na **ne**, Microsoft Edge otevře novou kartu s prázdnou stránkou. Uživatelé je nemůžou změnit.
- **Adresa URL nové karty**: Zadejte adresu URL, která se má otevřít na stránce Nová karta. Zadejte například `https://www.bing.com` nebo `https://www.contoso.com`.

- **Tlačítko domů**: Vyberte, co se stane, když je vybrané tlačítko domů. Možnosti:
  - **Úvodní stránky**: Otevře možnost, kterou jste zvolili v části **Spustit Microsoft Edge s** nastavením
  - **Stránka Nová karta**: Otevře adresu URL, kterou jste zadali v nastavení **Adresa URL nové karty** .
  - **Adresa URL pro tlačítko domů**: Zadejte adresu URL, která se má otevřít. Zadejte například `https://www.bing.com` nebo `https://www.contoso.com`.
  - **Skrýt tlačítko domů**: Skryje tlačítko domů.
- **Povolí uživatelům změnit tlačítko domů**: Možnost **Ano** umožňuje uživatelům změnit tlačítko domů. Změny uživatele přepíší všechna nastavení správce na tlačítko domů. **Ne** (výchozí) znemožní uživatelům měnit způsob, jakým Správce nakonfiguroval tlačítko domů.
- **Zobrazit stránku prvního spuštění (jenom mobilní zařízení)** : **Ano** (výchozí) zobrazuje úvodní stránku použití v Microsoft Edge. **No** zastaví zobrazování úvodní stránky při prvním spuštění Microsoft Edge. Tato funkce umožňuje podnikům, jako jsou například organizace zaregistrované v konfiguracích s nulovou emisemi, blokovat tuto stránku.
- **Umístění prvního seznamu adres URL prostředí pro spuštění** (Jenom Windows 10 Mobile): Zadejte adresu URL, která odkazuje na soubor XML obsahující adresy URL prvního spuštění stránky. Zadejte například `https://www.contoso.com/sites.xml`.

- **Aktualizovat prohlížeč po době nečinnosti**: Zadejte počet minut nečinnosti, než se prohlížeč aktualizuje, od 0-1440 minut. Výchozí hodnota `5` je minuty. Při nastavení na `0` hodnotu (nula) se prohlížeč po nečinnosti neaktualizuje.

  Toto nastavení je dostupné jenom v případě, že běží ve [veřejném procházení InPrivate (veřejný terminál s jednou aplikací)](#use-microsoft-edge-kiosk-mode).

- **Povolená automaticky otevíraná okna** (jenom desktopové počítače): **Ano** (výchozí) umožňuje automaticky otevíraná okna ve webovém prohlížeči. V prohlížeči nebrání automaticky otevíraná okna.
- **Odeslání intranetového provozu do Internet Exploreru** (Jenom desktopové počítače): **Ano** umožňuje uživatelům otevírat intranetové weby v Internet Exploreru místo Microsoft Edge. Toto nastavení je pro zpětnou kompatibilitu. **Ne** (výchozí) umožňuje uživatelům používat Microsoft Edge.
- **Umístění seznamu webů podnikového režimu** (Jenom desktopové počítače): Zadejte adresu URL, která odkazuje na soubor XML obsahující seznam webů, které se otevřou v podnikovém režimu. Uživatelé nemůžou tento seznam měnit. Zadejte například `https://www.contoso.com/sites.xml`.
- **Zpráva při otevírání webů v aplikaci Internet Explorer**: Pomocí tohoto nastavení můžete nastavit, aby Microsoft Edge zobrazoval oznámení předtím, než se web otevře v Internet Exploreru 11. Možnosti:
  - **Nezobrazovat zprávu**: Použije se výchozí chování operačního systému, které nemusí zobrazovat zprávu.
  - **Zobrazit zprávu, že web je otevřen v aplikaci Internet Explorer 11**: Zobrazit zprávu při otevírání webů v IE Weby otevřené v aplikaci IE. 
  - **Zobrazit zprávu s možností otevírat weby v Microsoft Edge**: Zobrazit zprávu při otevírání webů v Edge. Tato zpráva zahrnuje i **nadále odkaz na Microsoft Edge** , takže uživatelé můžou místo IE zvolit Microsoft Edge.

  > [!IMPORTANT]
  > Toto nastavení vyžaduje, abyste používali nastavení **umístění seznamu webů podnikového režimu** , nastavení **odesílat intranetový provoz do aplikace Internet Explorer** nebo obě nastavení.

- **Povolí seznam kompatibility Microsoftu**: **Ano** (výchozí) umožňuje používat seznam kompatibility Microsoftu. **Ne** zabraňuje seznamu kompatibility Microsoftu v Microsoft Edge. Tento seznam od Microsoftu pomáhá společnosti Microsoft Edge správně zobrazit lokality se známými problémy s kompatibilitou.
- **Úvodní stránky a stránka nové karty**: **Ano** (výchozí) používá výchozí chování operačního systému, které může být pro tyto stránky předem načteno. Předběžné načtení minimalizuje čas na spuštění Microsoft Edge a načítá nové karty. **Ne** znemožní Microsoft Edge z přednačtení počátečních stránek a nové stránky karty.
- **Úvodní stránky a stránka nové karty**: **Ano** (výchozí) používá výchozí chování operačního systému, které může být před spuštěním těchto stránek. Předběžná spuštění pomáhá s výkonem Microsoft Edge a minimalizuje dobu potřebnou ke spuštění Microsoft Edge. **Žádné** zabraňuje Microsoft Edge v předběžném spuštění stránek Start a nové karty.

Vyberte **OK** uložte provedené změny.

### <a name="favorites-and-search"></a>Oblíbené položky a hledání

- **Zobrazit panel oblíbených položek**: Vyberte, co se stane s panelem oblíbené položky na libovolné stránce Microsoft Edge. Možnosti:
  - **Na stránkách začátek a nová karta**: Zobrazí panel Oblíbené položky, když se spustí Microsoft Edge, a na všech stránkách karty. Koncoví uživatelé můžou toto nastavení změnit.
  - **Na všech stránkách**: Zobrazí panel Oblíbené na všech stránkách. Koncoví uživatelé nemůžou toto nastavení změnit.
  - **Skryté**: Skryje panel Oblíbené na všech stránkách. Koncoví uživatelé nemůžou toto nastavení změnit.
- **Povolí změny v oblíbených položkách**: **Ano** (výchozí) použije výchozí nastavení operačního systému, které umožňuje uživatelům změnit seznam. **Žádné** nebrání koncovým uživatelům v přidávání, importu, řazení a úpravách seznamu oblíbených položek.
  - **Seznam oblíbených položek**: Přidejte do souboru oblíbených položek seznam adres URL. Přidejte `http://contoso.com/favorites.html`například.
- **Synchronizace oblíbených položek mezi prohlížeči Microsoftu** (Jenom desktopové počítače): **Ano** vynutí, aby Windows synchronizoval oblíbené položky mezi Internet Explorerem a Microsoft Edgem. Přidání, odstranění, úpravy a změna pořadí oblíbených položek jsou sdíleny mezi prohlížeči.  **Ne** (výchozí) používá výchozí nastavení operačního systému, které může uživatelům umožnit synchronizaci oblíbených položek mezi prohlížeči.
- **Výchozí vyhledávací modul**: Vyberte výchozí vyhledávací web na zařízení. Koncoví uživatelé mohou tuto hodnotu kdykoli změnit. Možnosti:
  - Vyhledávací modul v nastavení klienta Microsoft Edge
  - Zjišťuje
  - Google
  - Yahoo
  - Vlastní hodnota: Do pole **Adresa URL XML OpenSearch**zadejte adresu URL protokolu HTTPS se souborem XML, který obsahuje krátký název a adresu URL vyhledávacího webu. Zadejte například `https://www.contoso.com/opensearch.xml`.
- **Zobrazit návrhy hledání**: **Ano** (výchozí) umožňuje vyhledávacímu webu navrhovat při psaní frází hledání na adresním řádku. Tato funkce **není** zabráněno.
- **Povolí změny vyhledávacího modulu**: **Ano** (výchozí) umožňuje uživatelům přidávat nové vyhledávací moduly nebo měnit výchozí vyhledávací web na Microsoft Edge. Pokud chcete uživatelům zabránit v přizpůsobení vyhledávacího modulu, klikněte na **ne** .

  Toto nastavení je dostupné, jenom když běží v [normálním režimu (veřejný terminál s více aplikacemi)](#use-microsoft-edge-kiosk-mode).

Vyberte **OK** uložte provedené změny.

### <a name="privacy-and-security"></a>Ochrana osobních údajů a zabezpečení

- **Povolí procházení InPrivate**: **Ano** (výchozí) povolí procházení InPrivate v Microsoft Edge. Po zavření všech karet InPrivate odstraní Microsoft Edge data procházení ze zařízení. **Žádné** zabraňuje koncovým uživatelům otevírat relace procházení InPrivate.
- **Uložit historii procházení**: **Ano** (výchozí) povolí ukládání historie procházení v Microsoft Edge. **No** nebrání ukládání historie procházení.
- **Vymazat údaje o procházení při ukončení** (jenom desktopové počítače): Hodnota **Ano** vymaže historii a data procházení, když uživatel ukončí Microsoft Edge. **Ne** (výchozí) používá výchozí operační systém, který může ukládat data procházení do mezipaměti.
- **Synchronizovat nastavení prohlížeče mezi zařízeními uživatele**: Vyberte, jak chcete synchronizovat nastavení prohlížeče mezi zařízeními. Možnosti:
  - **Povolení**: Povolí synchronizaci nastavení prohlížeče Microsoft Edge mezi zařízeními uživatele.
  - **Zablokovat a povolit přepsání uživatelem**: Blokuje synchronizaci nastavení prohlížeče Microsoft Edge mezi zařízeními uživatele. Uživatelé můžou toto nastavení přepsat.
  - **Blok**: Blokuje synchronizaci nastavení prohlížeče Microsoft Edge mezi zařízeními uživatelů. Uživatelé nemůžou toto nastavení přepsat.

Když je vybraná možnost blokovat a povolit uživatele, může přepsat označení správce.

- **Povolení správce hesel**: **Ano** (výchozí) umožňuje Microsoft Edge automaticky používat Správce hesel, který umožňuje uživatelům ukládat a spravovat hesla v zařízení. **No** zabrání Microsoft Edge v používání Správce hesel.
- **Soubory cookie**: Vyberte, jak se soubory cookie zpracovávají ve webovém prohlížeči. Možnosti:
  - **Povolení**: Soubory cookie jsou uloženy v zařízení.
  - **Blokovat všechny soubory cookie**: Soubory cookie nejsou uloženy v zařízení.
  - **Blokovat jenom soubory cookie třetích stran**: Soubory cookie třetích stran nebo partnerů nejsou uloženy v zařízení.
- **Povolí automatické vyplňování formulářů**: **Ano** (výchozí) umožňuje uživatelům změnit nastavení automatického dokončování v prohlížeči a automaticky naplnit pole formuláře. Funkce automatického vyplňování **není** na Microsoft Edge zakázaná.
- **Odesílat hlavičky do Not Track**: **Ano** pošle hlavičky do Not Track pro weby požadující informace o sledování (doporučeno). **Ne** (výchozí) neodesílají hlavičky, které umožňují webům sledovat uživatele. Uživatel může nakonfigurovat.
- **Zobrazit IP adresu WebRTC localhost**: **Ano** (výchozí) umožňuje zobrazení IP adresy místního hostitele uživatele při telefonování pomocí tohoto protokolu. Možnost **ne** zabrání zobrazení IP adresy místního hostitele uživatele. 
- **Povolení shromažďování dat živé dlaždice**: **Ano** (výchozí) umožňuje Microsoft Edge shromažďovat informace z živých dlaždic připnuté do nabídky Start. **Žádné** nebrání shromažďování těchto informací, což může uživatelům poskytnout omezené prostředí.
- **Uživatel může přepsat chyby certifikátu**: **Ano** (výchozí) umožňuje uživatelům přístup k webům s chybami protokolu SSL/TLS (SSL (Secure Sockets Layer)/Transport Layer Security). **Ne** (doporučeno pro zvýšené zabezpečení) znemožní uživatelům přístup k webům s chybami SSL nebo TLS.

Vyberte **OK** uložte provedené změny.

### <a name="additional"></a>Další

- **Povolí prohlížeč Microsoft Edge** . (jenom mobilní zařízení): **Ano** (výchozí) umožňuje používat webový prohlížeč Microsoft Edge na mobilním zařízení. Na zařízení nebrání použití Microsoft Edge. Pokud zvolíte **ne**, ostatní individuální nastavení platí pouze pro plochu.
- **Rozevírací nabídka povoleného panelu Adresa**: **Ano** (výchozí) umožňuje, aby Microsoft Edge zobrazoval rozevírací seznam s panelem Adresa se seznamem návrhů. V takovém případě se v rozevíracím seznamu při psaní nezastaví zobrazení seznamu návrhů v Microsoft Edge. Pokud je nastavena na **ne**, můžete:
  - Můžete minimalizovat šířku pásma sítě mezi Microsoft Edge a službami Microsoftu.
  - Zakažte možnost **Zobrazit hledání a návrhy webu při psaní** v nastavení Microsoft Edge >.
- **Povolený režim zobrazení na celé obrazovce**: **Ano** (výchozí) umožňuje, aby Microsoft Edge používal režim celé obrazovky, který zobrazuje jenom webový obsah a skrývá uživatelské rozhraní Microsoft Edge. V Microsoft Edge znemožní režim celoobrazovkového režimu.
- **Stránka pro povolení o příznacích**: **Ano** (výchozí) používá výchozí operační systém, který může umožňovat přístup k `about:flags` této stránce. Tato `about:flags` stránka umožňuje uživatelům změnit nastavení vývojáře a povolit experimentální funkce. **Žádné** zabrání koncovým uživatelům v `about:flags` přístupu k stránce v Microsoft Edge.
- **Povolení vývojářských nástrojů**: **Ano** (výchozí) umožňuje uživatelům pomocí nástrojů pro vývojáře F12 sestavovat a ladit webové stránky ve výchozím nastavení. **Žádné** nebrání koncovým uživatelům v používání vývojářských nástrojů F12.
- **Povolení JavaScriptu**: **Ano** (výchozí) umožňuje spouštění skriptů, jako je JavaScript, v prohlížeči Microsoft Edge. **Žádné** zabraňuje spuštění skriptů Java v prohlížeči.
- **Uživatel může nainstalovat rozšíření**: **Ano** (výchozí) umožňuje koncovým uživatelům instalovat na zařízení rozšíření Microsoft Edge. Nebrání instalaci.
- **Povolení zkušebního načtení rozšíření pro vývojáře**: **Ano** (výchozí) používá výchozí operační systém, který může umožňovat zkušební načtení. Zkušební načtení nainstaluje a spustí neověřená rozšíření. Možnost **nijak** nebrání Microsoft Edge ve zkušebním načtení pomocí funkce **rozšíření zatížení** . Nebrání rozšíření zkušebního načtení jiným způsobem, jako je například PowerShell.
- **Požadovaná rozšíření**: Vyberte, která rozšíření se koncovým uživatelům v Microsoft Edge nedají vypnout. Zadejte názvy rodin balíčků a vyberte **Přidat**. Některé doprovodné materiály poskytují [název rodiny balíčků (PFN)](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) .

  Můžete také **importovat** soubor CSV, který obsahuje názvy rodin balíčků. Případně **exportujte** názvy rodin balíčků, které zadáte.

Vyberte **OK** uložte provedené změny.

## <a name="network-proxy"></a>Síťový proxy server

Tato nastavení používají [zprostředkovatele CSP zásad NetworkProxy](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp), který obsahuje také podporované edice Windows.

- **Automaticky zjišťovat nastavení proxy serveru**: **Blok** zakáže, aby zařízení automaticky rozpoznalo skript automatické konfigurace proxy serveru (PAC). **Není nakonfigurováno** (výchozí) povolí tuto funkci. Pokud je tato možnost povolena, zařízení se pokusí najít cestu ke skriptu PAC.
- **Použít skript proxy serveru**: Chcete -li nakonfigurovat proxy server, vyberte možnost zadat cestu ke skriptu PAC. **Není nakonfigurováno** (výchozí) neumožňuje zadat adresu URL skriptu PAC.
  - Adresa **URL instalačního skriptu**: Zadejte adresu URL skriptu PAC, který chcete použít ke konfiguraci proxy server.
- **Použít ruční proxy server**: Vyberte možnost zadat ručně zadejte název nebo IP adresu a číslo portu TCP pro proxy server. **Není nakonfigurováno** (výchozí) neumožňuje ručně zadat podrobnosti o proxy server.
  - **Adresa**: Zadejte název nebo IP adresu proxy server.
  - **Číslo portu**: Zadejte číslo portu proxy server.
  - **Výjimky proxy serveru**: Zadejte všechny adresy URL, které nesmí proxy server použít. Jednotlivé položky oddělte středníkem.
  - **Obejít proxy server pro místní adresu**: **Není nakonfigurováno** (výchozí) zabraňuje použití proxy server pro místní adresy na vašem intranetu. Možnost **Allow** používá proxy server pro místní adresy.

Vyberte **OK** uložte provedené změny.

## <a name="password"></a>Heslo

Tato nastavení používají [zprostředkovatele CSP zásad DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock), který obsahuje také podporované edice Windows.

- **Heslo**: **Vyžaduje** , aby koncový uživatel zadal heslo pro přístup k zařízení. **Není nakonfigurováno** (výchozí) povolí přístup k zařízení bez hesla. Platí jenom pro místní účty. Hesla doménového účtu zůstávají nakonfigurovaná službou Active Directory (AD) a službou Azure AD.

  - **Požadovaný typ hesla**: Vyberte typ hesla. Možnosti:
    - Nenakonfigurováno: Heslo může obsahovat číslice a písmena.
    - **Číselná**: Heslo musí obsahovat jenom čísla.
    - **Alfanumerické znaky**: Heslo musí obsahovat kombinaci číslic a písmen.
  - **Minimální délka hesla**: Zadejte minimální požadovaný počet znaků nebo znaků od 4-16. Zadejte `6` například, pokud chcete, aby délka hesla vyžadovala alespoň šest znaků.
  
    > [!IMPORTANT]
    > Když se požadavek na heslo změní na plochu Windows, uživatelé budou mít vliv na jeho příštím přihlášení, protože to znamená, že zařízení přestane být aktivní. Uživatelům s hesly, kteří splňují požadavky, se stále zobrazí výzva ke změně hesla.
    
  - **Počet neúspěšných přihlášení před vymazáním zařízení**: Zadejte počet povolených selhání ověřování, než může být zařízení vymazáno, až 11. Platné číslo, které zadáte, závisí na edici. [DeviceLock/MAXDEVICEPASSWORDFAILEDATTEMPTS CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts) obsahuje seznam podporovaných hodnot. `0`(nula) může zakázat funkci vymazání zařízení.

    Toto nastavení má také jiný dopad v závislosti na edici. Konkrétní podrobnosti o tomto nastavení najdete v tématu [CSP pro DeviceLock/MaxDevicePasswordFailedAttempts](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts).

  - **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**: Zadejte dobu, po kterou musí být zařízení nečinné, než bude obrazovka uzamčena.
  - **Vypršení platnosti hesla (dny)** : Zadejte dobu ve dnech, kdy musí být heslo zařízení změněno, od 1-365. Zadejte `90` například platnost hesla po 90 dnech.
  - **Zakázat opakované použití předchozích hesel**: Zadejte počet dříve použitých hesel, která se nedají použít, od 1-24. Například zadejte `5` , že uživatelé nemůžou nastavit nové heslo na aktuální heslo ani na žádná z předchozích čtyř hesel.
  - **Vyžadovat heslo při návratu zařízení ze stavu nečinnosti** (Mobilní a holografická): Vyberte **vyžadovat** , aby museli uživatelé po nečinnosti zařízení odemknout. **Není nakonfigurováno** (výchozí) nevyžaduje PIN kód ani heslo, když se zařízení obnoví ze stavu nečinnosti.
  - **Jednoduchá hesla**: Nastavením zablokování znemožníte uživatelům vytvářet jednoduchá hesla, například `1234` nebo `1111`. Nastavte na Nenakonfigurováno (výchozí), aby uživatelé mohli vytvářet `1234` hesla `1111`, například nebo. Toto nastavení také povolí obrázková hesla Windows (nebo je zablokuje).
- **Automatické šifrování během AADJ**: **Blok** zabraňuje automatickému šifrování zařízení bitlockerem, když je zařízení připravené k prvnímu použití, když je zařízení připojené ke službě Azure AD. **Není nakonfigurováno** (výchozí) používá výchozí operační systém, který může šifrování povolit. Další informace o [šifrování zařízení nástrojem BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption).

  [Security/PreventAutomaticDeviceEncryptionForAzureADJoinedDevices CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-preventautomaticdeviceencryptionforazureadjoineddevices)

- **Zásada FIPS (Federal Information Processing Standard)** : Při použití této vlastnosti se používá zásada FIPS (Federal Information Processing Standard), což je standard pro státní správu USA pro šifrování, algoritmus hash a podepisování. **Není nakonfigurováno** (výchozí) používá výchozí operační systém, který nepoužívá FIPS.

  [Cryptography/AllowFipsAlgorithmPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-cryptography#cryptography-allowfipsalgorithmpolicy)

- **Ověřování zařízení Windows Hello**: **Umožňuje** uživatelům používat doprovodné zařízení Windows Hello, jako je telefon, autorita vhodnosti nebo zařízení IoT, pro přihlášení k počítači s Windows 10. **Není nakonfigurováno** (výchozí) používá výchozí operační systém, což může zabránit tomu, aby se doprovodná zařízení Windows Hello mohla ověřit ve Windows.

  [Authentication/AllowSecondaryAuthenticationDevice CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowsecondaryauthenticationdevice)

- **Webové přihlašování**: Povoluje přihlašování Windows pro federované zprostředkovatele bez služby ADFS (Active Directory Federation Services (AD FS)), jako je například Security Assertion Markup Language (SAML). SAML používá zabezpečené tokeny, které poskytují webovým prohlížečům jednotné přihlašování (SSO). Možnosti:

  - **Není nakonfigurováno** (výchozí): Používá výchozí operační systém na zařízení.
  - **Povoleno**: Poskytovatel přihlašovacích údajů webu je povolen pro přihlášení.
  - **Zakázáno**: Poskytovatel přihlašovacích údajů webu je pro přihlášení zakázán.

  [Ověřování/EnableWebSignIn CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-enablewebsignin)

- **Upřednostňovaná doména tenanta Azure AD**: Zadejte existující název domény v organizaci Azure AD. Když se uživatelé v této doméně přihlásí, nemusí zadávat název domény. Zadejte například `contoso.com`. Uživatelé v `contoso.com` doméně se můžou přihlásit pomocí svého uživatelského jména, `abby`jako je místo `abby@contoso.com`.

  [Authentication/PreferredAadTenantDomainName CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-preferredaadtenantdomainname)

Vyberte **OK** uložte provedené změny.

## <a name="per-app-privacy-exceptions"></a>Výjimky ze zásad ochrany osobních údajů pro jednotlivé aplikace

Můžete přidat aplikace, které by měly mít jiné chování ochrany osobních údajů než z toho, co definujete v části "výchozí ochrana osobních údajů".

- **Název balíčku**: Název řady balíčku aplikace
- **Název aplikace**: Název aplikace

### <a name="exceptions"></a>Výjimky

- **Informace o účtu**: Definujte, jestli tato aplikace bude mít přístup k uživatelskému jménu, obrázku a dalším kontaktním informacím.
- **Aplikace na pozadí**: Definujte, jestli tato aplikace může běžet na pozadí.
- **Kalendář**: Definujte, jestli tato aplikace bude mít přístup ke kalendáři.
- **Historie volání**: Definujte, jestli tato aplikace bude mít přístup k historii volání.
- **Kamera**: Definujte, jestli tato aplikace bude mít přístup ke kameře.
- **Kontakty**: Definujte, jestli tato aplikace bude mít přístup ke kontaktům.
- **E-mail**: Definujte, jestli tato aplikace bude mít přístup k e-mailu a odešle e-mail.
- **Umístění**: Definujte, jestli tato aplikace bude mít přístup k informacím o poloze.
- **Zasílání zpráv**: Definujte, jestli tato aplikace může číst nebo posílat textové zprávy nebo zprávy MMS.
- **Mikrofon**: Definujte, jestli tato aplikace může používat mikrofon.
- **Pohyb**: Definujte, jestli tato aplikace bude mít přístup k informacím o pohybu zařízení.
- **Oznámení**: Definujte, jestli tato aplikace bude mít přístup k oznámením.
- **Telefon**: Definujte, jestli tato aplikace bude mít přístup k telefonu.
- **Rozhlasové přijímače**: Některé aplikace používají rádiová zařízení (například Bluetooth) ve vašem zařízení k posílání a přijímání dat a potřebují zapnout nebo vypnout tyto radiostanice. Definujte, jestli tato aplikace může tyto moduly používat.
- **Úkoly**: Definujte, jestli tato aplikace bude mít přístup k vašim úkolům.
- **Důvěryhodná zařízení**: Vyberte, jestli tato aplikace může používat důvěryhodná zařízení. Důvěryhodná zařízení jsou hardware, který jste už připojili, nebo hardware, který se dodává se zařízením. Například používejte televizory, projektory a tak dále jako důvěryhodná zařízení.
- **Zpětná vazba a diagnostika**: Definujte, jestli tato aplikace bude mít přístup k diagnostickým informacím.
- **Synchronizovat se zařízeními**: Vyberte, jestli tato aplikace může automaticky sdílet a synchronizovat informace s bezdrátovými zařízeními, která se zařízením explicitně nespárují.

Vyberte **OK** uložte provedené změny.

## <a name="personalization"></a>Personalizace

Tato nastavení používají [zprostředkovatele kryptografických služeb v zásadách přizpůsobení](https://docs.microsoft.com/windows/client-management/mdm/personalization-csp), který obsahuje taky podporované edice Windows.

- **Adresa URL obrázku na pozadí plochy (jenom desktopové počítače)** : Zadejte adresu URL obrázku ve formátu. jpg,. jpeg nebo. png, který chcete použít jako tapetu plochy systému Windows. Uživatelé nemohou tento obrázek změnit. Zadejte například `https://contoso.com/logo.png`.

Vyberte **OK** uložte provedené změny.

## <a name="printer"></a>Tiskárně

- **Tiskárny**: Seznam místních tiskáren, které byly přidány.
- **Výchozí tiskárna**: Nastavte výchozí tiskárnu.
- **Přístup uživatelů k přidávání nových tiskáren**: Povolí nebo zablokuje používání místních tiskáren.

Vyberte **OK** uložte provedené změny.

## <a name="privacy"></a>Ochrana osobních údajů

Tato nastavení používají [CSP zásady ochrany osobních údajů](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy), který také uvádí podporované edice Windows.

- **Přizpůsobení vstupu**: **Blok** zabraňuje použití hlasu pro diktování a komunikaci s Cortana a dalšími aplikacemi, které využívají rozpoznávání řeči od Microsoftu. Je zakázaná a uživatelé nemůžou povolit online rozpoznávání řeči pomocí nastavení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům zvolit. Pokud povolíte tyto služby, může společnost Microsoft shromažďovat hlasová data pro zlepšení služby.
- **Automatické přijetí párování a výzev k souhlasu uživatele s ochranou osobních údajů**: Vyberte možnost **umožnit** , aby systém Windows mohl automaticky přijímat párování a zprávy o souhlasu s ochranou osobních údajů při spouštění aplikací. **Není nakonfigurováno** (výchozí) zabraňuje automatickému přijetí párování a okna souhlasu uživatele s ochranou osobních údajů při otevírání aplikací.
- **Publikování aktivit uživatelů**: **Blok** zabraňuje sdíleným prostředím a zjišťování naposledy použitých prostředků v kanálu aktivit. **Není nakonfigurováno** (výchozí) povolí tuto funkci, aby aplikace mohla publikovat aktivity koncového uživatele.
- **Pouze místní aktivity**: **Blok** zabraňuje sdíleným prostředím a zjišťování naposledy použitých prostředků v přepínání úloh na základě pouze místních aktivit. **Není nakonfigurováno** (výchozí) povolí tuto funkci.

Můžete nakonfigurovat informace, ke kterým mají přístup všechny aplikace na zařízení. Také definujte výjimky pro jednotlivé aplikace pomocí **výjimek ochrany osobních údajů pro jednotlivé aplikace**.

Vyberte **OK** uložte provedené změny.

### <a name="exceptions"></a>Výjimky

- **Informace o účtu**: Definujte, jestli tato aplikace bude mít přístup k uživatelskému jménu, obrázku a dalším kontaktním informacím.
- **Aplikace na pozadí**: Definujte, jestli tato aplikace může běžet na pozadí.
- **Kalendář**: Definujte, jestli tato aplikace bude mít přístup ke kalendáři.
- **Historie volání**: Definujte, jestli tato aplikace bude mít přístup k historii volání.
- **Kamera**: Definujte, jestli tato aplikace bude mít přístup ke kameře.
- **Kontakty**: Definujte, jestli tato aplikace bude mít přístup ke kontaktům.
- **E-mail**: Definujte, jestli tato aplikace bude mít přístup k e-mailu a odešle e-mail.
- **Umístění**: Definujte, jestli tato aplikace bude mít přístup k informacím o poloze.
- **Zasílání zpráv**: Definujte, jestli tato aplikace může číst nebo posílat textové zprávy nebo zprávy MMS.
- **Mikrofon**: Definujte, jestli tato aplikace může používat mikrofon.
- **Pohyb**: Definujte, jestli tato aplikace bude mít přístup k informacím o pohybu zařízení.
- **Oznámení**: Definujte, jestli tato aplikace bude mít přístup k oznámením.
- **Telefon**: Definujte, jestli tato aplikace bude mít přístup k telefonu.
- **Rozhlasové přijímače**: Některé aplikace používají rádiová zařízení (například Bluetooth) ve vašem zařízení k posílání a přijímání dat a potřebují zapnout nebo vypnout tyto radiostanice. Definujte, jestli tato aplikace může tyto moduly používat.
- **Úkoly**: Definujte, jestli tato aplikace bude mít přístup k vašim úkolům.
- **Důvěryhodná zařízení**: Vyberte, jestli tato aplikace může používat důvěryhodná zařízení. Důvěryhodná zařízení jsou hardware, který jste už připojili, nebo hardware, který je součástí zařízení. Například používejte televizory, projektory a tak dále jako důvěryhodná zařízení.
- **Zpětná vazba a diagnostika**: Vyberte, jestli tato aplikace bude mít přístup k diagnostickým informacím.
- **Synchronizovat se zařízeními** – Definujte, jestli tato aplikace může automaticky sdílet a synchronizovat informace s bezdrátovými zařízeními, která se explicitně nepárují s tímto počítačem, tabletem nebo telefonem.

Vyberte **OK** uložte provedené změny.

## <a name="projection"></a>Promítání

Tato nastavení používají [zprostředkovatele CSP zásad WirelessDisplay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wirelessdisplay), který obsahuje také podporované edice Windows.

- **Vstup uživatele z přijímačů bezdrátového zobrazení**: **Blok** zabraňuje vstupu uživatele z přijímačů bezdrátového zobrazení. **Není nakonfigurováno** (výchozí) umožňuje bezdrátové zobrazení odesílání klávesnice, myši, pera a dotykového vstupu zpátky na zdrojové zařízení.
- **Projekce na tento počítač**: **Blok** zabraňuje ostatním zařízením najít zařízení pro projekci. **Není nakonfigurováno** (výchozí) umožňuje, aby bylo zařízení zjistitelné a bylo možné ho promítnout do zařízení nad zamykací obrazovkou.
- **Vyžadovat pro párování kód PIN**: Pokud se připojujete k zařízení projekce, vyberte **vyžadovat** , aby se pro PIN kód vždycky zobrazila výzva. **Není nakonfigurováno** (výchozí) nevyžaduje PIN pro spárování zařízení se zařízením projekce.

Vyberte **OK** uložte provedené změny.

## <a name="reporting-and-telemetry"></a>Generování sestav a telemetrie

- **Sdílet data o využití**: Vyberte úroveň diagnostických dat, která byla odeslána. Možnosti:
  - Nenakonfigurováno: Nejsou sdílena žádná data.
  - **Zabezpečení**: Informace, které jsou potřebné k zajištění vyššího zabezpečení systému Windows, včetně údajů o nastavení komponenty prostředí s připojeným uživatelem a Telemetriem, nástroji pro odebrání škodlivého softwaru a programu Windows Defender.
  - **Základní**: Základní informace o zařízení, včetně dat týkajících se kvality, kompatibility aplikací, dat o využití aplikací a dat z úrovně zabezpečení.
  - **Rozšířené možnosti**: Další přehledy, včetně: jak se používají Windows, Windows Server, System Center a aplikace, jak provádějí, pokročilá data o spolehlivosti a data ze základní i úrovně zabezpečení.
  - **Úplné**: Veškerá data potřebná pro identifikaci a pomoc při řešení problémů a data ze zabezpečení, úrovně Basic a vylepšené úrovně.

  [CSP pro System/AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)

- **Odeslání dat procházení Microsoft Edge do Microsoft 365 Analytics**: Chcete-li použít tuto funkci, nastavte nastavení **sdílet data o využití** na hodnotu **Rozšířené** nebo **úplné**. Tato funkce řídí, jaká data Microsoft Edge odesílá Microsoft 365 analýze pro podniková zařízení s nakonfigurovaným komerčním ID. Možnosti:
  - Nenakonfigurováno: Používá výchozí operační systém, který nemusí odesílat žádná data historie procházení.
  - **Posílat jenom intranetová data**: Umožňuje správci odesílat historii dat intranetu.
  - **Odesílat pouze Internetová data**: Umožňuje správci odesílat historii internetových dat.
  - **Odesílat intranetová a Internetová data**: Umožňuje správci odeslat historii intranetových a internetových dat.

  [Browser/ConfigureTelemetryForMicrosoft365Analytics CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configuretelemetryformicrosoft365analytics)

- **Proxy server telemetrie**: Zadejte plně kvalifikovaný název domény (FQDN) nebo IP adresu proxy server pro přeposílání připojených uživatelských zkušeností a telemetrie pomocí připojení SSL (Secure Sockets Layer) (SSL). Formát pro toto nastavení je *server*:*port*. Pokud pojmenovaný proxy server selhává nebo pokud při povolování této zásady nezadá proxy server, neodesílají se data o prostředích a telemetrii připojené uživatele a zůstanou na místním zařízení.

  Příklady formátů:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

  [CSP pro System/TelemetryProxy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-telemetryproxy)

Vyberte **OK** uložte provedené změny.

## <a name="search"></a>Hledat

Tato nastavení používají [CSP v zásadách hledání](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search), ve kterém jsou uvedeny také podporované edice systému Windows. 

- **Bezpečné vyhledávání (jenom mobilní zařízení)** : Určuje, jak Cortana filtruje obsah pro dospělé ve výsledcích hledání. Možnosti:
  - **Definováno uživatelem**: Umožňuje koncovým uživatelům zvolit si vlastní nastavení.
  - **Striktní**: Nejvyšší filtrování obsahu pro dospělé
  - **Střední**: Střední filtrování obsahu pro dospělé Platné výsledky hledání nejsou filtrovány.
- **Zobrazit výsledky webu v hledání**: Když se nastaví **blokování**, uživatelé nemůžou vyhledávat a výsledky webu nejsou zobrazené ve vyhledávání. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vyhledávat na webu a výsledky se zobrazí na zařízení.

Vyberte **OK** uložte provedené změny.

## <a name="start"></a>Spustit

Tato nastavení používají [zprostředkovatele CSP zásad spuštění](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start), který také uvádí podporované edice systému Windows.  

- **Rozložení nabídky Start**: Přepište výchozí počáteční rozložení a upravte nabídku Start na stolních zařízeních. Nahrajte soubor XML, který obsahuje vaše vlastní nastavení, včetně pořadí, ve kterém jsou aplikace uvedené, a další. Uživatelé nemůžou měnit rozložení nabídky Start, které zadáte.
- **Připnout weby na dlaždice v nabídce Start**: Importujte obrázky z Microsoft Edge, které se zobrazují jako odkazy v nabídce Start systému Windows pro stolní zařízení.
- **Odepnout aplikace z panelu úloh**: **Blok** zabraňuje uživatelům v odpnutí aplikací z panelu úloh. **Není nakonfigurováno** (výchozí) umožňuje uživatelům odepnout aplikace na hlavním panelu.
- **Rychlé přepínání uživatelů**: **Blok** zabraňuje přepínání mezi uživateli, kteří jsou přihlášeni současně bez odhlášení. **Není nakonfigurováno** (výchozí) zobrazí **uživatele přepínače** na dlaždici uživatele.
- **Nejčastěji používané aplikace**: **Blok** skryje v nabídce Start nejčastěji používané aplikace. Zároveň se zakáže odpovídající přepínač v aplikaci Nastavení. **Není nakonfigurováno** (výchozí) zobrazí nejčastěji používané aplikace.
- **Nedávno přidané aplikace**: **Blok** skryje v nabídce Start naposledy přidané aplikace. Zároveň se zakáže odpovídající přepínač v aplikaci Nastavení. **Není nakonfigurováno** (výchozí) zobrazuje nedávno přidané aplikace v nabídce Start.
- **Režim úvodní obrazovky**: Vyberte, jak se zobrazí úvodní obrazovka. Možnosti:
  - **Definováno uživatelem**: Nenutí velikost začátku. Uživatelé můžou nastavit velikost.
  - **Celá obrazovka**: Vynutí celou velikost spuštění.
  - **Jiná než celá obrazovka**: Vynutí, aby byla necelá velikost začátku.
- **Naposledy otevřené položky v seznamech odkazů**: **Blok** skryje v nabídce Start a na hlavním panelu nedávný seznam odkazů. Zároveň se zakáže odpovídající přepínač v aplikaci Nastavení. **Není nakonfigurováno** (výchozí) zobrazí naposledy otevřené položky v seznamy odkazů.
- **Seznam aplikací**: Vyberte, jak se mají zobrazovat seznamy všech aplikací. Možnosti:
  - **Definováno uživatelem**: Žádné nastavení není vynuceno. Uživatelé zvolí, jak se na zařízení zobrazuje seznam aplikací.
  - **Sbalit**: Skrýt seznam všech aplikací
  - **Sbalení a zakázání aplikace nastavení**: Skrýt seznam všech aplikací a zakázat možnost **Zobrazit seznam aplikací v nabídce Start** v aplikaci nastavení.
  - **Odebere a zakáže aplikaci nastavení**: Umožňuje skrýt seznam všech aplikací, odebrat všechny aplikace a zakázat možnost **Zobrazit seznam aplikací v nabídce Start** v aplikaci nastavení.
- **Tlačítko napájení**: **Blok** skryje tlačítko napájení, které se zobrazí v nabídce Start. **Není nakonfigurováno** (výchozí) zobrazí tlačítko napájení.
- **Dlaždice uživatele**: **Blok** skryje dlaždici uživatele v zobrazení nabídky Start. **Není nakonfigurováno** (výchozí) zobrazí dlaždici uživatele a také nastaví následující nastavení:
  - **Zamknout**: **Blok** skryje možnost **zámku** na dlaždici uživatele v nabídce Start. **Není nakonfigurováno** (výchozí) zobrazí možnost **zámku** .
  - **Odhlásit**se: **Blok** skryje možnost **Odhlásit** se ze zobrazení na dlaždici uživatele v nabídce Start. **Není nakonfigurováno** (výchozí) zobrazí možnost **Odhlásit** se.
- **Vypnout**: **Blok** skryje na tlačítku napájení v nabídce Start možnost možnosti **aktualizace a vypnutí** a vypnutí. **Není nakonfigurováno** (výchozí) zobrazí tyto možnosti.
- **Režim spánku**: **Blok** skryje v nabídce Start možnost **režim spánku** , než se zobrazí na tlačítku napájení. **Není nakonfigurováno** (výchozí) zobrazí tuto možnost.
- **Režim hibernace**: **Blok** skryje možnost **Hibernace** , která se zobrazí na tlačítku napájení v nabídce Start. **Není nakonfigurováno** (výchozí) zobrazí tuto možnost.
- **Přepnout účet**: **Blok** skryje v nabídce Start na dlaždici uživatele zobrazení **účtu přepnutí** . **Není nakonfigurováno** (výchozí) zobrazí tuto možnost.
- **Možnosti restartování**:  **Blok** skryje na tlačítku napájení v nabídce Start možnost **aktualizace a restartování** a možnosti **restartování** . **Není nakonfigurováno** (výchozí) zobrazí tyto možnosti.
- **Dokumenty na začátku**: Umožňuje skrýt nebo zobrazit složku dokumenty v nabídce Start systému Windows. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení není vynuceno. Uživatelé mají možnost zobrazit nebo skrýt zástupce.
  - **Skrýt**: Zástupce je skrytý a v aplikaci nastavení se zakáže nastavení.
  - **Zobrazit**: Zobrazí se zástupce a v aplikaci nastavení se zakáže nastavení.
- **Soubory ke stažení na začátku**: Umožňuje skrýt nebo zobrazit složku stažené soubory v nabídce Start systému Windows. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení není vynuceno. Uživatelé mají možnost zobrazit nebo skrýt zástupce.
  - **Skrýt**: Zástupce je skrytý a v aplikaci nastavení se zakáže nastavení.
  - **Zobrazit**: Zobrazí se zástupce a v aplikaci nastavení se zakáže nastavení.
- **Průzkumník souborů na začátku**: V nabídce Start systému Windows skryjte nebo zobrazte Průzkumníka souborů. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení není vynuceno. Uživatelé mají možnost zobrazit nebo skrýt zástupce.
  - **Skrýt**: Zástupce je skrytý a v aplikaci nastavení se zakáže nastavení.
  - **Zobrazit**: Zobrazí se zástupce a v aplikaci nastavení se zakáže nastavení.
- **Domácí skupina v nabídce Start**: V nabídce Start systému Windows skryjte nebo zobrazte zástupce domácí skupiny. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení není vynuceno. Uživatelé mají možnost zobrazit nebo skrýt zástupce.
  - **Skrýt**: Zástupce je skrytý a v aplikaci nastavení se zakáže nastavení.
  - **Zobrazit**: Zobrazí se zástupce a v aplikaci nastavení se zakáže nastavení.
- **Hudba na začátku**: Umožňuje skrýt nebo zobrazit složku hudba v nabídce Start systému Windows. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení není vynuceno. Uživatelé mají možnost zobrazit nebo skrýt zástupce.
  - **Skrýt**: Zástupce je skrytý a v aplikaci nastavení se zakáže nastavení.
  - **Zobrazit**: Zobrazí se zástupce a v aplikaci nastavení se zakáže nastavení.
- **Síť při spuštění**: Umožňuje skrýt nebo zobrazit Síťové vstupy nabídce Windows Start. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení není vynuceno. Uživatelé mají možnost zobrazit nebo skrýt zástupce.
  - **Skrýt**: Zástupce je skrytý a v aplikaci nastavení se zakáže nastavení.
  - **Zobrazit**: Zobrazí se zástupce a v aplikaci nastavení se zakáže nastavení.
- **Osobní složka v nabídce Start**: V nabídce Start systému Windows skryjte nebo zobrazte osobní složku. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení není vynuceno. Uživatelé mají možnost zobrazit nebo skrýt zástupce.
  - **Skrýt**: Zástupce je skrytý a v aplikaci nastavení se zakáže nastavení.
  - **Zobrazit**: Zobrazí se zástupce a v aplikaci nastavení se zakáže nastavení.
- **Obrázky na začátku**: V nabídce Start systému Windows skryjte nebo zobrazte složku pro obrázky. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení není vynuceno. Uživatelé mají možnost zobrazit nebo skrýt zástupce.
  - **Skrýt**: Zástupce je skrytý a v aplikaci nastavení se zakáže nastavení.
  - **Zobrazit**: Zobrazí se zástupce a v aplikaci nastavení se zakáže nastavení.
- **Nastavení na začátku**: V nabídce Start systému Windows skryjte nebo zobrazte zástupce nastavení. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení není vynuceno. Uživatelé mají možnost zobrazit nebo skrýt zástupce.
  - **Skrýt**: Zástupce je skrytý a v aplikaci nastavení se zakáže nastavení.
  - **Zobrazit**: Zobrazí se zástupce a v aplikaci nastavení se zakáže nastavení.
- **Videa na začátku**: V nabídce Start systému Windows skryjte nebo zobrazte složku pro videa. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení není vynuceno. Uživatelé mají možnost zobrazit nebo skrýt zástupce.
  - **Skrýt**: Zástupce je skrytý a v aplikaci nastavení se zakáže nastavení.
  - **Zobrazit**: Zobrazí se zástupce a v aplikaci nastavení se zakáže nastavení.

Vyberte **OK** uložte provedené změny.

## <a name="windows-defender-smart-screen"></a>Filtr SmartScreen v programu Windows Defender

- **Filtr SmartScreen pro Microsoft Edge**: **Vyžaduje** vypínání filtru SmartScreen v programu Windows Defender a zabránění uživatelům v jeho zapnutí. **Není nakonfigurováno** (výchozí) zapne filtr SmartScreen. Pomáhá chránit uživatele před potenciálními hrozbami a zabránit uživatelům v jejich vypnutí.

  Microsoft Edge používá filtr SmartScreen v programu Windows Defender (zapnutý) k ochraně uživatelů před potenciálními podvodnými zprávami a škodlivým softwarem.

  [Browser/AllowSmartScreen CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)

- **Přístup ke škodlivému webu**: **Blok** zabraňuje uživatelům ignorovat upozornění filtru SmartScreen v programu Windows Defender a zablokuje je při přechodu na web. **Není nakonfigurováno** (výchozí) umožňuje uživatelům ignorovat upozornění a pokračovat v lokalitě.

  [Browser/PreventSmartScreenPromptOverride CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride)

- **Stahování neověřených souborů**: **Blok** zabraňuje uživatelům ignorovat upozornění filtru SmartScreen v programu Windows Defender a zablokuje stahování neověřených souborů. **Není nakonfigurováno** (výchozí) umožňuje uživatelům ignorovat upozornění a pokračovat v stahování neověřených souborů.

  [Browser/PreventSmartScreenPromptOverrideForFiles CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles)

Vyberte **OK** uložte provedené změny.

## <a name="windows-spotlight"></a>Windows Spotlight

Tato nastavení používají [zprostředkovatele kryptografických služeb (CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience)), který obsahuje taky podporované edice Windows.

- **Windows Spotlight**: **Blokování** vypne Windows Spotlight na zamykací obrazovce, tipy pro Windows, funkce Microsoftu pro uživatele a další související funkce. Pokud je vaším cílem minimalizovat síťový provoz ze zařízení, nastavte tuto hodnotu na **blokovat**. **Není nakonfigurováno** (výchozí) povolí funkce Windows Spotlight a můžou je řídit koncovými uživateli. Když je tato možnost povolená, můžete taky povolit nebo zablokovat následující nastavení:

  - **Windows Spotlight na zamykací obrazovce**: **Blokovat** zastaví zobrazování informací na zamykací obrazovce zařízení ve Windows Spotlightu. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
  - **Návrhy třetích stran ve Windows Spotlightu**: **Blok** zabraňuje systému Windows Spotlight navrhovat obsah, který není publikován společností Microsoft. **Není nakonfigurováno** (výchozí) umožňuje navrhovat aplikace a návrhy obsahu od vydavatelů partnerských softwaru ve funkcích Windows Spotlight, jako je Spotlight na zamykací obrazovce, navrhované aplikace v nabídce Start a tipy pro Windows.
  - **Uživatelské funkce**: **Blokování** vypne prostředí, která jsou typicky jenom pro příjemce, jako jsou návrhy spuštění, oznámení o členství, instalace aplikací po ukončení a přesměrovat dlaždice. **Není nakonfigurováno** (výchozí) tyto funkce povolují.
  - **Tipy pro systém Windows**: **Blok** zakáže automaticky otevíraná okna s tipy pro Windows. **Není nakonfigurováno** (výchozí) umožňuje zobrazit tipy pro Windows.
  - **Windows Spotlight v centru akcí**: **Blok** zabraňuje zobrazování oznámení Windows Spotlightu v centru akcí. **Není nakonfigurováno** (výchozí) mohou zobrazovat oznámení v centru akcí, které navrhují aplikace nebo funkce, které uživatelům pomůžou zvýšit produktivitu Windows.
  - **Přizpůsobení Windows Spotlightu**: **Blok** zabraňuje systému Windows používat diagnostická data k poskytování přizpůsobených prostředí uživateli. **Není nakonfigurováno** (výchozí) umožňuje Microsoftu používat diagnostická data k poskytování individuálních doporučení, tipů a nabídek k přizpůsobení Windows potřebám uživatelů.
  - **Prostředí uvítání systémem Windows**: **Blok** vypne funkci uvítání systémem Windows Spotlight Windows. Prostředí uvítání systémem Windows se nezobrazí, pokud jsou k dispozici aktualizace a změny ve Windows a jejích aplikacích. **Není nakonfigurováno** (výchozí) povolí prostředí uvítání systémem Windows, které zobrazuje informace o uživateli nových nebo aktualizovaných funkcích.

Vyberte **OK** uložte provedené změny.

## <a name="windows-defender-antivirus"></a>Antivirová ochrana v programu Windows Defender

Tato nastavení používají [zprostředkovatele CSP v zásadách Defenderu](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender), který obsahuje také podporované edice Windows.

- **Sledování v reálném čase**: **Možnost Povolit** zabrání v reálném čase vyhledávání malwaru, spywaru a dalšího nežádoucího softwaru. **Není nakonfigurováno** (výchozí) povolí tuto funkci.
- **Monitorování chování**: **Možnost Povolit** zabrání programu Defender kontrolovat v zařízeních určité známé vzorce podezřelé aktivity. **Není nakonfigurováno** (výchozí) umožňuje monitorování chování v programu Windows Defender.
- **Systém kontroly sítě (NIS)** : NIS pomáhá chránit zařízení před zneužitím prostřednictvím sítě. Používá signatury známých slabých míst z Centra Microsoftu pro ochranu koncových bodů ke zjištění a blokování škodlivého síťového provozu.
- **Kontrolovat všechna stahování**: Určuje, jestli bude Defender kontrolovat všechny soubory stahované z internetu.
- **Kontrolovat skripty načtené do webových prohlížečů Microsoftu**: **Není nakonfigurováno** (výchozí) umožňuje programu Defender kontrolovat skripty, které se používají v Internet Exploreru. **Možnost Povolit** zabrání této kontrole.
- **Přístup koncového uživatele k programu Defender**: **Blok** skryje uživatelské rozhraní programu Windows Defender před koncovými uživateli. Potlačí se také všechna oznámení v programu Windows Defender. **Není nakonfigurováno** (výchozí) umožňuje uživateli přístup k uživatelskému rozhraní programu Windows Defender. Když toto nastavení změníte, projeví se změna až při příštím restartování počítače koncovým uživatelem.
- **Interval aktualizace podpisu (v hodinách)** : Zadejte interval, ve kterém Defender kontroluje nové soubory signatury, od 0-24. Možnosti:

  - **Není nakonfigurováno** výchozí
  - **Nekontrolovat**: Defender nehledá nové soubory signatur.
  - **1-24**: `1` kontroluje každou hodinu, `2` kontroluje každé dvě hodiny `24` , kontroluje každý den atd.
- **Sledovat aktivitu souborů a programů**: Umožňuje Defenderu monitorování aktivity souborů a programů v zařízení.
- **Dny před odstraněním malwaru v karanténě**: Pokračovat v sledování vyřešeného malwaru po zadaný počet dní, abyste mohli ručně kontrolovat dříve ovlivněná zařízení. Pokud nastavíte počet dní na **0**, malware zůstane ve složce karanténa a automaticky se neodebere. Pokud je nastaveno `90`na, karanténní položky jsou uloženy po dobu 90 dnů v systému a poté odebrány.
- **Limit využití procesoru při kontrole**: Omezte počet PROCESORů, které mohou být využívány pomocí kontroly od **1** do **100**.
- **Kontrolovat archivní soubory**: **Možnost Povolit** zabrání programu Defender ve skenování archivovaných souborů, jako jsou soubory ZIP nebo CAB. **Není nakonfigurováno** (výchozí) umožňuje tuto kontrolu.
- **Kontrolovat příchozí e-mailové zprávy**: **Povolit** umožňuje programu Defender kontrolovat e-mailové zprávy při jejich doručení do zařízení. **Není nakonfigurováno** (výchozí) zabrání v kontrole e-mailů.
- **Kontrolovat vyměnitelné jednotky během úplného prohledávání**: **Možnost Povolit** zabrání kompletním kontrolám vyměnitelných jednotek. **Není nakonfigurováno** (výchozí) umožňuje programu Defender kontrolovat vyměnitelné jednotky, jako jsou USB hole.
- **Při úplné kontrole kontrolovat namapované síťové jednotky**: **Povolit** umožňuje programu Defender kontrolovat soubory na namapovaných síťových jednotkách. **Není nakonfigurováno** (výchozí) zabrání úplnému prohledávání. Pokud jsou soubory na disku jen pro čtení, Defender nemůže odebrat žádný malware, který v nich našel.
- **Kontrolovat soubory otevřené ze síťových složek**: **Není nakonfigurováno** (výchozí) umožňuje programu Defender kontrolovat soubory na sdílených síťových jednotkách, například k souborům přidaným z cesty UNC. **Možnost Povolit** zabrání této kontrole. Pokud jsou soubory na disku jen pro čtení, Defender nemůže odebrat žádný malware, který v nich našel.
- **Ochrana cloudu**: **Není nakonfigurováno** (výchozí) umožňuje služba Microsoft Active Protection Service přijímat informace o aktivitě malwaru ze zařízení, která spravujete. **Povolit** blokování této funkce
- **Dotázat se uživatele před odesláním vzorku**: Určuje, jestli jsou potenciálně škodlivé soubory, které by mohly vyžadovat další analýzu, automaticky odesílány společnosti Microsoft. Možnosti:
  - **Není nakonfigurováno**
  - **Vždycky se zeptat**
  - **Dotázat se před odesláním osobních údajů**
  - **Nikdy Neodesílat data**
  - **Poslat všechna data bez zobrazení výzvy**: Data se odesílají automaticky

- **Čas, kdy se má provést rychlá denní kontrola**: Vyberte hodinu spuštění každodenní rychlé kontroly. **Není nakonfigurováno** spustí denní kontrolu. Pokud chcete více úprav, nakonfigurujte **typ kontroly systému na provádění** .

  [Defender/ScheduleQuickScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime)

- **Typ Systémové kontroly, který se má provést**: Naplánujte kontrolu systému, včetně úrovně kontroly a dne a času, kdy se má kontrola spustit. Možnosti:
  - Nenakonfigurováno: Neplánuje kontrolu systému na zařízení. Koncoví uživatelé můžou na svých zařízeních ručně spouštět kontroly podle potřeby nebo na jejich zařízení.
  - **Zakázat**: Zakáže v zařízení kontrolu systémových souborů. Tuto možnost vyberte, pokud používáte řešení antivirové ochrany, které provádí kontrolu zařízení.
  - **Rychlá kontrola**: Hledá na běžných místech, kde by mohlo být zaregistrované malware, jako jsou klíče registru a známé spouštěcí složky Windows.
    - **Naplánovaný den**: Vyberte den, kdy se má kontrola spustit.
    - **Naplánovaný čas**: Vyberte hodinu spuštění kontroly.
  - **Úplná kontrola**: Hledá na běžných místech, kde může být zaregistrovaný malware, a také zkontroluje všechny soubory a složky v zařízení.
    - **Naplánovaný den**: Vyberte den, kdy se má kontrola spustit.
    - **Naplánovaný čas**: Vyberte hodinu spuštění kontroly.

  Toto nastavení může být v konfliktu s **časem provedení denního nastavení rychlého prohledávání** . Některá doporučení:

  - Pokud chcete spustit každodenní rychlé prověřování, nakonfigurujte **čas, kdy se má provést nastavení denního rychlého prohledávání** .
  - Pokud chcete spustit každodenní rychlou kontrolu a úplnou kontrolu každý týden, nakonfigurujte **čas k provedení každodenní rychlé kontroly**. Nastavte **typ Systémové kontroly, který se má provést** pro úplnou kontrolu pomocí dne a času.
  - Nekonfigurujte **dobu, kdy se má provést nastavení denní rychlé kontroly** současně s **typem kontroly systému, který má být proveden** pro **rychlé prohledání**. Tato nastavení mohou být v konfliktu a kontrola nemusí běžet.
  - Chcete-li spustit rychlou kontrolu každé úterý v 9:00, nakonfigurujte **typ kontroly systému, který má být proveden** .

  [Defender/ScanParameter CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter)  
  [Defender/ScheduleScanDay CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday)  
  [Defender/ScheduleScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime)

- **Zjistit potenciálně nežádoucí aplikace**: Vyberte úroveň ochrany, když systém Windows detekuje potenciálně nežádoucí aplikace. Možnosti:
  - **Není nakonfigurováno** (výchozí): Ochrana před potenciálně nežádoucími aplikacemi v programu Windows Defender je zakázaná.
  - **Blok**: Windows Defender detekuje potenciálně nežádoucí aplikace a zjištěné položky jsou blokované. Tyto položky se zobrazují v historii spolu s dalšími hrozbami.
  - **Audit**: Program Windows Defender detekuje potenciálně nežádoucí aplikace, ale neprovede žádnou akci. Můžete zkontrolovat informace o aplikacích, které Windows Defender provede, na základě akce. Vyhledejte například události vytvořené v programu Windows Defender v Prohlížeč událostí.

  Další informace o potenciálně nežádoucích aplikacích najdete v tématu [zjištění a blokování potenciálně nežádoucích aplikací](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).

- **Akce zjištěných malwarových hrozeb**: Vyberte akce, které má Defender provést pro každou úroveň hrozby, kterou zjistí: nízká, střední, vysoká a závažná. Pokud to není možné, Windows Defender zvolí nejlepší možnost, abyste zajistili, že dojde k nápravě hrozby. Možnosti:
  - **Vyčistit**
  - **Karanténa**
  - **Odebrat**
  - **Povoleno**
  - **Definováno uživatelem**
  - **Blokováno**

Vyberte **OK** uložte provedené změny.

### <a name="windows-defender-antivirus-exclusions"></a>Výjimky antivirové ochrany v programu Windows Defender

- **Soubory a složky, které se mají vyloučit z kontrol a ochrany v reálném čase**: Umožňuje do seznamu vyloučení přidat soubory a složky, například **C:\Cesta** nebo **%ProgramFiles%\Cesta\název_souboru.exe**. Tyto soubory a složky nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.
- **Přípony souborů, které se mají vyloučit z kontrol a ochrany v reálném čase**: Umožňuje do seznamu vyloučení přidat přípony souborů, například **jpg** nebo **txt**. Všechny soubory s těmito příponami nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.
- **Procesy, které se mají vyloučit z kontrol a ochrany v reálném čase**: Umožňuje do seznamu vyloučení přidat procesy typu **.exe**, **.com** nebo **.scr**. Tyto procesy nejsou zahrnuté do kontrol prováděných v reálném čase ani do plánovaných kontrol.

Vyberte **OK** uložte provedené změny.

## <a name="next-steps"></a>Další kroky

Další technické podrobnosti o jednotlivých nastaveních a podporovaných edicích Windows najdete v [referenčních informacích o poskytovateli konfiguračních služeb pro zásady (CSP) pro Windows 10](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).
