---
title: Nastavení omezení zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Zobrazit seznam všech nastavení a jejich popisy pro vytvoření omezení zařízení v systému Windows 10 a novější zařízení. Chcete-li řídit snímky obrazovky, požadavky na heslo, nastavení beznabídkového režimu, aplikace ve storu, prohlížeč Microsoft Edge, program Windows defender, přístup do cloudu a nabídce start a další v Microsoft Intune pomocí těchto nastavení v profilu konfigurace.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: fe155c5b2a18b1931894b05694b53bbc2c497e0b
ms.sourcegitcommit: 116ef72b9da4d114782d4b8dd9f57556c9b01511
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2019
ms.locfileid: "67494490"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>Nastavení Windows 10 (a novějších) zařízení a povolení nebo zakázání funkcí pomocí Intune

Tento článek uvádí a popisuje všechny různých nastaveních, pomocí kterých můžete řídit na Windows 10 a novější zařízení. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete povolit nebo zakázat funkce, nastavit pravidla pro hesla, přizpůsobení zamykací obrazovka, použijte program Windows Defender a další.

Tato nastavení jsou přidány do konfiguračního profilu zařízení v Intune a potom přiřazené nebo nasazené na zařízení s Windows 10.

> [!Note]
> Některé možnosti jsou dostupné ve všech edicích systému Windows. Podporované edice zobrazíte najdete [zásad poskytovatele CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) (otevře jiný web společnosti Microsoft).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](device-restrictions-configure.md#create-the-profile).

## <a name="app-store"></a>App Store

Použijte tato nastavení [ApplicationManagement zásad CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement), který také obsahuje seznam podporovaných edicí Windows.

- **App store** (jenom mobilní verze): **Není nakonfigurováno** (výchozí) umožňuje koncovým uživatelům přístup k obchodu s aplikacemi na mobilních zařízeních. **Blok** brání použití app storu.
- **Automaticky aktualizovat aplikace ze storu**: **Není nakonfigurováno** (výchozí) umožňuje aplikací nainstalovaných z Microsoft Store automaticky aktualizovat. **Blok** brání automaticky se nainstalují aktualizace.
- **Instalace důvěryhodné aplikace**: Zvolte, pokud Microsoft Store aplikace je možné instalovat, označovaný také jako zkušební načtení před prodejem. Zkušební načtení před prodejem instalace a poté běží nebo testování aplikace, která není certifikovaná v Microsoft Store. Například aplikaci, která je pro vaši společnost pouze interní. Možnosti:
  - **Není nakonfigurováno** (výchozí): Použije výchozí nastavení operačního systému.
  - **Blok**: Zabraňuje zkušební načtení před prodejem. Microsoft Store bez aplikace se nedá nainstalovat.
  - **Povolit**: Umožňuje pro zkušební načtení. Je možné nainstalovat bez Microsoft Store aplikace.
- **Odemčení pro vývojáře**: Povolit nastavení pro vývojáře Windows, například můžete umožnit zkušebně načtené aplikace koncovým uživatelům provádět změny. Možnosti:
  - **Není nakonfigurováno** (výchozí): Použije výchozí nastavení operačního systému.
  - **Blok**: Zabraňuje režimem a pro zkušební načtení aplikací pro vývojáře.
  - **Povolit**: Umožňuje vývojáři režimem a pro zkušební načtení aplikací.

  [Aktivovat zařízení pro vývoj](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development) obsahuje další informace o této funkci.

- **Sdílená data aplikací uživatele**: Zvolte **povolit** sdílet data aplikací mezi různými uživateli na stejném zařízení a s jinými instancemi dané aplikace. **Není nakonfigurováno** (výchozí) zabraňuje sdílení dat s jinými uživateli a ostatní instance stejné aplikace.
- **Použít pouze privátní úložiště**: **Povolit** povoluje jenom aplikace ke stažení z privátního úložiště a nebyly staženy z veřejného obchodu, včetně katalogu maloobchodního prodeje. **Není nakonfigurováno** (výchozí) umožňuje stahování z privátního úložiště a veřejného úložiště aplikací.
- **Spuštění aplikace pocházející ze Store**: **Blok** zakáže všechny aplikace, které byly předem nainstalované na zařízení nebo stažených z Microsoft Store. **Není nakonfigurováno** (výchozí) umožňuje tyto aplikace otevřít.
- **Nainstalovat data aplikací na systémový svazek**: **Blok** zabrání aplikacím ukládat data na systémový svazek zařízení. **Není nakonfigurováno** (výchozí) umožňuje aplikacím ukládat data na svazku systémového disku.
- **Nainstalovat aplikace na systémovou jednotku**: **Blok** aplikacím bránit instalaci na systémovou jednotku zařízení. **Není nakonfigurováno** (výchozí) umožňuje aplikace k instalaci na systémovou jednotku.
- **Záznam ze hry** (jenom desktopové verze): **Blok** zakáže hru Windows záznam a vysílání. **Není nakonfigurováno** (výchozí) umožňuje záznam a vysílání z her.
- **Jen aplikace ze storu**: Toto nastavení určuje činnost koncového uživatele, když uživatelé nainstalují aplikace z jiných míst než Microsoft Store. Možnosti:

  - **Není nakonfigurováno** (výchozí): Umožňuje koncovým uživatelům instalovat aplikace odjinud než Microsoft Store, včetně aplikací, které jsou definovány v rámci jiných nastaveních zásad.  
  - **Kdekoli**: Vypne doporučování aplikací a umožňuje uživatelům instalovat aplikace z libovolného místa.  
  - **Pouze Store**: Vynutí koncoví uživatelé instalují jenom aplikace z Microsoft Store.
  - **Doporučení**: Při instalaci aplikace z webu, který je dostupný v Microsoft Store, uživatelům se zobrazí zpráva, že ho stáhnou z úložiště doporučujeme.  
  - **Preferovat Store**: Upozorní uživatele, když se instalovat aplikace odjinud než Microsoft Store.

  [SmartScreen/EnableAppInstallControl CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen#smartscreen-enableappinstallcontrol)

- **Vynutit restartování aplikace při selhání aktualizace**: Při použití aplikace nemusí aktualizovat. Pomocí tohoto nastavení můžete vynutit aplikaci restartovat. **Není nakonfigurováno** (výchozí) nebude vynucené restartování. **Vyžadovat** správcům umožňuje vynutit restartování na určité datum a čas, nebo podle plánu opakování. Pokud je nastavena na **vyžadují**, také zadejte:

  - **Počáteční datum/čas**: Vyberte určité datum a čas k restartování aplikace.
  - **Opakování**: Zvolte denních, týdenních nebo měsíčních restartovat.

  [ApplicationManagement/ScheduleForceRestartForUpdateFailures CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

- **Kontrola uživatele nad instalací**: Pokud je nastavena na **Nenakonfigurováno** (výchozí), instalační služby systému Windows zabrání uživatelům změnit možnosti instalace, obvykle vyhrazené pro správce systému, jako je zadání adresář pro instalaci souborů. **Blok** umožňuje uživatelům změnit tyto možnosti instalace, a některé z funkcí zabezpečení Instalační služby systému Windows se přeskočí.

  [ApplicationManagement/MSIAllowUserControlOverInstall CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msiallowusercontroloverinstall)

- **Instalace aplikací s vyššími oprávněními**: Pokud je nastavena na **Nenakonfigurováno** (výchozí), systém použije aktuální uživatel oprávnění při instalaci programy, které nemá správce systému nasadit nebo nabídky. **Blok** instruuje Instalační služby systému Windows použít zvýšenou úroveň oprávnění při instalaci libovolné aplikace v systému. Tato oprávnění jsou rozšířeny, aby všechny programy.

  [ApplicationManagement/MSIAlwaysInstallWithElevatedPrivileges CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msialwaysinstallwithelevatedprivileges)

- **Při spuštění aplikace**: Zadejte seznam aplikací spustíte po přihlášení uživatele k zařízení. Nezapomeňte použít seznam oddělený středníkem z balíčku oddělených (PFN) aplikace Windows. Pro tyto zásady fungují musíte použít manifest v aplikacích Windows úlohy po spuštění.

  [ApplicationManagement/LaunchAppAfterLogOn CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-launchappafterlogon)

Vyberte **OK** uložte provedené změny.

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení

Pomocí těchto nastavení [zásad připojení](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) a [zásady Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) CSP, které také seznam podporovaných edicí Windows.

- [Zásady sítě Wi-Fi CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi)

- **Mobilní datový kanál**: Zvolte, pokud se koncoví uživatelé mohou používat data, třeba k procházení webu, při připojení k mobilní síti. Možnosti:
  - **Není nakonfigurováno** (výchozí): Používá výchozí operační systém, což může umožnit mobilní datový kanál. Koncoví uživatelé ji můžete vypnout.
  - **Blok**: Nepovolit mobilní datový kanál. Koncoví uživatelé ji nelze zapnout.
  - **Povolit (nejde upravit)** : Umožňuje mobilní datový kanál. Koncoví uživatelé ji nelze vypnout.

- **Datový roaming**: **Blok** brání mobilní datový roaming v zařízení. **Není nakonfigurováno** (výchozí) povoluje roaming mezi sítěmi při přístupu k datům.
- **VPN přes mobilní síť**: **Blok** zařízení brání v přístupu k připojení k síti VPN při připojení k mobilní síti. **Není nakonfigurováno** (výchozí) umožňuje VPN použít jakékoli připojení, včetně mobilního.
- **VPN v mobilní síti v roamingu**: **Blok** zastaví zařízení při roamingu v mobilní síti získat přístup k připojení k síti VPN. **Není nakonfigurováno** (výchozí) umožňuje připojení VPN při roamingu.
- **Služba připojených zařízení**: **Blok** zakáže komponenty platformy připojené zařízení (CDP). Distribuční místo seznamu CRL umožňuje zjišťování a připojování dalších zařízení (přes Bluetooth/LAN nebo cloudu) pro podporu vzdálené spouštění aplikací, vzdálené zasílání zpráv, relací vzdálené aplikace a jiné prostředí pro různá zařízení. **Není nakonfigurováno** umožňuje služba připojených zařízení, která umožňuje zjišťování a připojování dalších zařízení Bluetooth (výchozí).
- **NFC**: **Blok** zabraňuje v možnosti komunikace (NFC) pole. **Není nakonfigurováno** (výchozí) umožňuje uživatelům povolit a konfigurovat funkce NFC na zařízení.
- **Wi-Fi**: **Blok** zabraňuje uživatelům a povolení, konfiguraci a použití připojení Wi-Fi na zařízení. **Není nakonfigurováno** (výchozí) umožňuje připojení Wi-Fi.
- **Automaticky se připojovat k Wi-Fi hotspotům**: **Blok** brání automatické připojení k Wi-Fi hotspotům zařízení. **Není nakonfigurováno** (výchozí) umožňuje zařízení automaticky se připojovat k volným Wi-Fi hotspotům a automaticky přijímat jakékoli podmínky a ujednání pro připojení.
- **Ruční konfigurace Wi-Fi**: **Blok** zařízení brání v připojení k Wi-Fi mimo MDM server nainstalován sítě. **Není nakonfigurováno** (výchozí) umožňuje koncovým uživatelům přidat a nakonfigurovat svoje vlastní Wi-Fi připojení sítě SSID.
- **Interval skenování Wi-Fi**: Zadejte, jak často zařízení skenují sítě Wi-Fi. Zadejte hodnotu od 1 (nejčastěji) na 500 (nejméně často). Výchozí hodnota je `0` (nula).

### <a name="bluetooth"></a>Bluetooth

Použijte tato nastavení [zásada pro Bluetooth CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth); které taky seznamy podporovaných edicí Windows.

- **Bluetooth**: **Blok** zabraňuje uživatelům možnost povolit Bluetooth. **Není nakonfigurováno** (výchozí) umožňuje Bluetooth na zařízení.
- **Zjistitelnost zařízení Bluetooth**: **Blok** brání zařízení zjistitelné jinými zařízeními podporujícími technologii Bluetooth. **Není nakonfigurováno** (výchozí) umožňuje další zařízeními podporujícími technologii Bluetooth, třeba sluchátka s mikrofonem ke zjištění zařízení.
- **Párování Bluetooth předem**: **Blok** brání určitých zařízení Bluetooth automatické párování s hostujícím zařízením. **Není nakonfigurováno** umožní automatické párování s hostujícím zařízením (výchozí).
- **Reklama přes Bluetooth**: **Blok** zabrání zařízení v odesílání reklamy přes Bluetooth. **Není nakonfigurováno** umožňuje zařízení odesílat reklamy přes Bluetooth (výchozí).
- **Povolené služby Bluetooth**: **Přidat** seznam povolených služeb a profilů Bluetooth jako hexadecimálních řetězců, jako `{782AFCFC-7CAA-436C-8BF0-78CD0FFBD4AF}`.

  [Použití Průvodce ServicesAllowedList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#servicesallowedlist-usage-guide) obsahuje další informace o seznamu služeb.

Vyberte **OK** uložte provedené změny.

## <a name="cloud-and-storage"></a>Cloud a úložiště

Tato nastavení použijte [účty zásad CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts); které taky seznamy podporovaných edicí Windows.

- **Účet Microsoft**: **Blok** zabrání koncovým uživatelům od přidružování zařízení účet Microsoft. **Není nakonfigurováno** (výchozí) umožňuje přidávání a pomocí účtu Microsoft.
- **Účet od jiných výrobců**: **Blok** zabrání koncovým uživatelům v přidávání jiných účtů než účtů Microsoft pomocí uživatelského rozhraní. **Není nakonfigurováno** (výchozí) umožňuje uživatelům přidávat e-mailové účty, které nejsou přidruženy k účtu Microsoft.
- **Synchronizace nastavení pro účet Microsoft**: **Není nakonfigurováno** (výchozí) umožňuje nastavení zařízení a aplikací přidružených k účtu Microsoft k synchronizaci mezi zařízeními. **Blok** , nebude tato synchronizace.
- **Microsoft Account Pomocníka pro přihlášení**: Pokud je nastavena na **Nenakonfigurováno** (výchozí), koncovým uživatelům můžete spustit a zastavit **účtu přihlášení pomocníka** service (wlidsvc). Tato služba operačního systému umožňuje uživatelům umožní přihlásit ke svému účtu Microsoft. **Zakázat** zabrání koncovým uživatelům řízení služby Pomocníka pro přihlášení společnosti Microsoft (wlidsvc).

Vyberte **OK** uložte provedené změny.

## <a name="cloud-printer"></a>Cloudová tiskárna

Použijte tato nastavení [EnterpriseCloudPrint zásad CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-enterprisecloudprint); které taky seznamy podporovaných edicí Windows.

- **Adresa URL pro zjišťování tiskáren**: Zadejte adresu URL pro hledání cloudových tiskáren. Zadejte například `https://cloudprinterdiscovery.contoso.com`.
- **Adresa URL autority pro přístup k tiskárnám**: Zadejte adresu URL koncového bodu ověřování k získání tokenů OAuth. Zadejte například `https://azuretenant.contoso.com/adfs`.
- **Nativní klientské aplikace Azure GUID**: Zadejte identifikátor GUID klientské aplikace k získání tokenů OAuth od OAuthAuthority povolené. Zadejte například `E1CF1107-FF90-4228-93BF-26052DD2C714`.
- **Služba identifikátor URI prostředku tiskové**: Zadejte identifikátor URI prostředku OAuth pro tiskovou službu nakonfigurované na webu Azure Portal. Zadejte například `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Maximální počet tiskáren dotazu**: Zadejte maximální počet tiskáren, na které chcete, aby se dalo dotazovat. Výchozí hodnota je `20`.
- **Identifikátor URI prostředku služby zjišťování tiskáren**: Zadejte identifikátor URI prostředku OAuth pro zjišťování tiskáren služba nakonfigurovaná na webu Azure Portal. Zadejte například `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Po nastavení [systému Windows Server hybridní Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview), můžete nakonfigurovat tato nastavení a pak nasadit do zařízení s Windows.

Vyberte **OK** uložte provedené změny.

## <a name="control-panel-and-settings"></a>Ovládací panely a nastavení

- **Nastavení aplikace**: **Blok** zabrání koncovým uživatelům v přístupu k aplikaci nastavení Windows. **Není nakonfigurováno** (výchozí) umožňuje uživatelům otevírat v aplikaci nastavení na zařízení.
  - **Systém**: **Blok** brání v přístupu k systémové oblasti v aplikaci nastavení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
    - **Změny nastavení napájení a režimu spánku** (jenom desktopové verze): **Blok** zabrání koncovým uživatelům možnost měnit nastavení napájení a režimu spánku na zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům změnit napájení a režimu spánku nastavení.
  - **zařízení**: **Blok** brání v přístupu k oblasti zařízení v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Network Internet**: **Blok** brání v přístupu k oblasti síť a Internet v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Přizpůsobení**: **Blok** brání v přístupu k oblasti přizpůsobení v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Aplikace**: **Blok** brání v přístupu k oblasti aplikace v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Účty**: **Blok** brání v přístupu k oblasti účtů v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Čas a jazyk**: **Blok** brání v přístupu k oblasti čas a jazyk v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
    - **Změny systémového času**: **Blok** zabrání koncovým uživatelům možnost měnit nastavení data a času na zařízení. **Není nakonfigurováno** umožňuje uživatelům změnit tato nastavení.
    - **Změny nastavení oblasti** (jenom desktopové verze): **Blok** zabrání koncovým uživatelům možnost měnit nastavení oblasti na zařízení. **Není nakonfigurováno** umožňuje uživatelům změnit tato nastavení.
    - **Změny nastavení jazyka (jenom desktopové verze)** : **Blok** zabrání koncovým uživatelům možnost měnit nastavení jazyka na zařízení. **Není nakonfigurováno** umožňuje uživatelům změnit tato nastavení.

      [Nastavení zásad CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings)

  - **Hraní her**: **Blok** brání v přístupu k oblasti hry v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Usnadnění přístupu**: **Blok** brání v přístupu k oblasti usnadnění přístupu v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Ochrana osobních údajů**: **Blok** brání v přístupu k oblasti soukromí v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.
  - **Aktualizace a zabezpečení**: **Blok** brání v přístupu k oblasti aktualizací a zabezpečení v aplikaci nastavení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup.

Vyberte **OK** uložte provedené změny.

## <a name="display"></a>Zobrazit

Použijte tato nastavení [zobrazení zásady CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-display); které taky seznamy podporovaných edicí Windows.

Škálování rozlišení DPI GDI umožňuje aplikacím, které nejsou rozpoznání nastavení DPI na zaregistrují za sledování DPI.

- **Zapnout GDI pro aplikace**: **Přidat** starší verze aplikací, které chcete, aby měřítka rozlišení DPI GDI zapnuté. Zadejte například `filename.exe` nebo `%ProgramFiles%\Path\Filename.exe`.

  Škálování rozlišení DPI GDI je zapnuté pro všechny starší verze aplikace v seznamu.

- **Vypnout GDI pro aplikace**: **Přidat** starší verze aplikací, které chcete, aby měřítka rozlišení DPI GDI vypnuté. Zadejte například `filename.exe` nebo `%ProgramFiles%\Path\Filename.exe`.

  Škálování rozlišení DPI GDI je vypnuté pro všechny starší verze aplikace v seznamu.

Můžete také **Import** soubor CSV obsahující seznam aplikací.

Vyberte **OK** uložte provedené změny.

## <a name="general"></a>Obecné

Použijte tato nastavení [prostředí zásad CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience); které taky seznamy podporovaných edicí Windows. 

- **Snímek obrazovky** (jenom mobilní verze): **Blok** zabrání koncovým uživatelům v přístupu snímky obrazovky na zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Kopírování a vložení (jenom mobilní verze)** : **Blok** koncovým uživatelům bránit v použití kopírování a vkládání mezi aplikacemi na zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Ruční zrušení zápisu**: **Blok** zabrání koncovým uživatelům odstranit pracovní účet, pomocí ovládacího panelu síti na pracovišti na zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.

  Nastavení této zásady neplatí, pokud je počítač připojený k Azure AD a je povolená Automatická registrace.

- **Ruční instalace kořenového certifikátu** (jenom mobilní verze): **Blok** zabrání koncovým uživatelům ruční instalaci kořenových certifikátů a zprostředkujících certifikátů CAP. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Camera**: **Blok** koncovým uživatelům bránit v použití fotoaparátu/kamery na zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Synchronizace souboru Onedrivu**: **Blok** zabrání koncovým uživatelům synchronizovat soubory na OneDrive ze zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Vyměnitelné úložiště**: **Blok** koncovým uživatelům bránit v použití zařízením externího úložiště, jako jsou karty SD. se zařízením. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Informace o zeměpisné poloze**: **Blok** zabrání koncovým uživatelům zapínali zjišťování polohy v zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Sdílení Internetu**: **Blok** zabraňuje sdílení internetového připojení na zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Obnovení továrního nastavení telefonu**: **Blok** koncovým uživatelům zabraňuje vymazání obsahu nebo udělat obnovení továrního nastavení v zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Připojení USB**: **Blok** brání v přístupu k zařízením externího úložiště prostřednictvím připojení USB na zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce. Toto nastavení nemá vliv účtování USB.
- **Režim antiTheft** (jenom mobilní verze): **Blok** zabrání koncovým uživatelům z výběru předvolby režim AntiTheft na zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Cortana**: **Blok** zakázat hlasového asistenta Cortany na zařízení. Když je Cortana vypnuté, uživatelé mohou stále Hledat pro vyhledání položek na zařízení. **Není nakonfigurováno** (výchozí) umožňuje Cortany.
- **Záznam hlasu** (jenom mobilní verze): **Blok** koncovým uživatelům bránit v použití hlasového záznamu zařízení v zařízení. **Není nakonfigurováno** (výchozí) umožňuje pro aplikace pro záznam hlasu.
- **Změny názvu zařízení** (jenom mobilní verze): **Blok** zabrání koncovým uživatelům možnost měnit název zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Přidávat zřizovací balíčky**: **Blok** brání agenta konfigurace modulu runtime, který instaluje zřizovací balíčky, které na zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Odebírání zřizovacích balíčků**: **Blok** brání agenta konfigurace modulu runtime, který odebírá zřizovací balíčky ze zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Zjišťování zařízení**: **Blok** zabrání zařízení v právě zjištěny jinými zařízeními. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Přepínání úloh** (jenom mobilní verze): **Blok** brání přepínání úloh na zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Chybový dialog SIM karty** (jenom mobilní verze): **Blok** chybové zprávy zobrazování na zařízení, pokud se zjistí nezjistí žádná SIM karta. **Není nakonfigurováno** (výchozí) se zobrazí chybové zprávy.
- **Pracovní prostor Ink**: Zvolte, jestli a jakým způsobem uživatel přístup k pracovnímu prostoru ink. Možnosti:
  - **Není nakonfigurováno** (výchozí): Zapne tento pracovní prostor a uživatel může používat nad zamykací obrazovkou.
  - **Zakázáno na zamykací obrazovce**: Tento pracovní prostor je povolen a je zapnutá funkce. Ale uživatel nemůže přejít nad zamykací obrazovkou.
  - **Zakázané**: Přístup k pracovní prostor ink je zakázaný. Tato funkce je vypnuta.

  [Zásady WindowsInkWorkspace CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace)

- **Automatické opětovné nasazení**: Zvolte **povolit** tak můžete uživatelům s právy správce odstranit všechna uživatelská data a nastavení pomocí **CTRL + Win + R** na zamykací obrazovce zařízení. Zařízení je automaticky překonfigurovat a znovu zaregistrovat do systému správy. **Není nakonfigurováno** této funkce zabraňuje (výchozí).
- **Vyžadovat, aby uživatelé pro připojení k síti během nastavování zařízení**: Zvolte **vyžadují** tak připojení zařízení k síti před přetáhli za stránka v síti během instalace Windows. **Není nakonfigurováno** (výchozí) umožňuje uživatelům přejít z stránky síť, i když není připojený k síti.

  Nastavení začne platit při příštím zařízení je vymazat nebo resetovat. Stejně jako jakoukoli jinou konfiguraci Intune musí být zařízení zaregistrovaných a spravovaných v Intune pro přijímání nastavení konfigurace. Ale jednou je zaregistrované a přijímá zásady, potom Resetuje zařízení vynucuje nastavení během další nastavení Windows.

- **Přímý přístup do paměti**: **Blok** brání přímý přístup do paměti (DMA) pro všechny aktivní modulární PCI podřízené porty, dokud se uživatel přihlásí do Windows. **Povolené** (výchozí) umožňuje přístup ke DMA, i v případě, že uživatel není přihlášený.

  CSP: [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)

- **Ukončit procesy ve Správci úloh**: Toto nastavení určuje, zda nejsou správci, můžete použít Správce úloh na ukončit úlohy. **Blok** brání použití Správce úloh k ukončení procesu nebo úlohy na zařízení uživatele se standardním oprávněním (bez oprávnění správce). **Není nakonfigurováno** (výchozí) umožňuje standardní uživatelé k ukončení procesu nebo úloh pomocí Správce úloh.

Vyberte **OK** uložte provedené změny.

## <a name="locked-screen-experience"></a>Prostředí zamknuté obrazovky

- **Oznámení Centra akcí (jenom mobilní verze)** : **Blok** brání oznámení Centra akcí z zobrazuje na zamykací obrazovce zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům zvolit, které aplikace zobrazovala oznámení na zamykací obrazovce.

  [AboveLock/AllowActionCenterNotifications CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowactioncenternotifications)

- **Obrázek adresa URL zamknutou obrazovku (jenom desktopové verze)** : Zadejte adresu URL obrázku ve formátu JPG, JPEG nebo PNG, který se použije jako tapeta zamknuté obrazovky Windows. Zadejte například `https://contoso.com/image.png`. Toto nastavení uzamkne bitovou kopii a nedá se změnit později.
- **Uživatel Konfigurovatelný časový limit obrazovky (jenom mobilní verze)** : **Povolit** umožňuje uživatelům konfigurovat časový limit obrazovky. **Není nakonfigurováno** (výchozí) nedává uživatelům tuto možnost.

  [DeviceLock/AllowScreenTimeoutWhileLockedUserConfig CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-allowscreentimeoutwhilelockeduserconfig)

- **Cortana na zamknuté obrazovce** (jenom desktopové verze): **Blok** zabraňuje uživatelům z pracovat s Cortanou, když je na zamykací obrazovce zařízení. **Není nakonfigurováno** (výchozí) umožňuje interakci s Cortanou.

  [AboveLock/AllowCortanaAboveLock CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowcortanaabovelock)

- **Informační zprávu oznámení na uzamčené obrazovce**: **Blok** brání informační zprávy z zobrazuje na zamykací obrazovce zařízení. **Není nakonfigurováno** (výchozí), umožňuje tato oznámení.

  [AboveLock/AllowToasts CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowtoasts)

- **Časový limit (jenom mobilní verze) obrazovky**: Nastavení doby trvání (v sekundách) od zamknutí obrazovky vypnutím obrazovky. Podporované hodnoty jsou 11 – 1800. Zadejte například `300` nastavit tento časový limit na 5 minut.

  [DeviceLock/ScreenTimeoutWhileLocked CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-screentimeoutwhilelocked)

Vyberte **OK** uložte provedené změny.

## <a name="messaging"></a>Zasílání zpráv

Použijte tato nastavení [zásad zprostředkovatele kryptografických služeb pro zasílání zpráv](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-messaging); které taky seznamy podporovaných edicí Windows.

- **Synchronizace (jenom mobilní verze) zpráv**: **Blok** zakáže textové zprávy, zálohovat a obnovit a synchronizaci zpráv mezi zařízením Windows. Zakázání pomáhá zabránit informace uložené na serverech mimo ovládací prvek pro organizaci. **Není nakonfigurováno** (výchozí) umožňuje uživatelům změnit nastavení a synchronizovat své zprávy.
- **MMS (jenom mobilní verze)** : **Blok** zakáže MMS odesílat a přijímat v zařízení. Pro podniky použijte tyto zásady k zakázání zpráv MMS na zařízeních v rámci požadavku auditování nebo vedení. **Není nakonfigurováno** (výchozí) umožňuje MMS odesílat a přijímat.
- **RCS (jenom mobilní verze)** : **Blok** zakáže Rich Communication Services (RCS) odesílat a přijímat v zařízení. Pro podniky použijte tyto zásady k zakázání RCS na zařízeních v rámci požadavku auditování nebo vedení. **Není nakonfigurováno** (výchozí) umožňuje RCS odesílat a přijímat.

Vyberte **OK** uložte provedené změny.

## <a name="microsoft-edge-browser"></a>Prohlížeč Microsoft Edge

Použijte tato nastavení [zásady prohlížeče CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser), který také obsahuje seznam podporovaných edicí Windows.

### <a name="use-microsoft-edge-kiosk-mode"></a>Režim veřejného terminálu použijte Microsoft Edge

Dostupná nastavení měnit v závislosti na volbách. Možnosti:

- **Ne** (výchozí): Microsoft Edge není spuštěn v režimu veřejného terminálu. Jsou k dispozici můžete změnit a nakonfigurovat všechna nastavení Microsoft Edge.
- **Digitální/Interaktivní značky (aplikace s jedním veřejný terminál)** : Nastavení Microsoft Edge filtry, které se dají použít pro digitální/Interaktivní značky Microsoft Edge celoobrazovkový režim pro použití pouze pro veřejné terminály s Windows 10 jedné aplikace. Toto nastavení chcete otevřít adresy URL zobrazení na celé obrazovce a zobrazit obsah pouze na daném webu. [Nastavit příznaky digitální](https://docs.microsoft.com/windows/configuration/setup-digital-signage) poskytuje další informace o této funkci.
- **Procházení se službou inPrivate veřejné (beznabídkového režimu jedné aplikace)** : Nastavení Microsoft Edge filtry, které se dají použít pro InPrivate veřejné procházení Microsoft Edge celoobrazovkový režim pro použití na veřejné terminály s Windows 10 jedné aplikace. Běží více karet verze Microsoft Edge.
- **Normální režim (veřejný terminál s více aplikacemi)** : Nastavení Microsoft Edge filtry, které se dají použít pro normální Microsoft Edge beznabídkový režim. Spouští se všemi funkcemi procházení plné verze Microsoft Edge.
- **Veřejné procházení (veřejný terminál s více aplikacemi)** : Nastavení Microsoft Edge filtry, které se dají použít pro veřejné procházení na jako veřejný terminál s více aplikacemi Windows 10.  Běží více karet verze InPrivate v Microsoft Edgi.

> [!TIP]
> Další informace o těchto možností k čemu najdete v tématu [typy konfigurace celoobrazovkového režimu Microsoft Edge](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

Tento profil omezení zařízení přímo souvisí s profil beznabídkového režimu vytvoříte pomocí [nastavení beznabídkového režimu Windows](kiosk-settings-windows.md). Shrnutí:

1. Vytvořte [nastavení beznabídkového režimu Windows](kiosk-settings-windows.md) profilu zařízení v beznabídkovém režimu spouštět. Vyberte Microsoft Edge jako aplikace a nastavení režimu veřejného terminálu Microsoft Edge v profil beznabídkového režimu.
2. Vytvořit profil omezení zařízení, který je popsaný v tomto článku a konfigurovat konkrétní funkce a nastavení povolená v Microsoft Edge. Zvolte stejný typ režimu veřejného terminálu Microsoft Edge jako vybrané v profilu aplikace veřejného terminálu ([nastavení beznabídkového režimu Windows](kiosk-settings-windows.md)). 

    [Nepodporuje nastavení celoobrazovkového režimu](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-policies-for-kiosk-mode) je skvělý prostředek.

> [!IMPORTANT] 
> Je potřeba přiřadit tento profil Microsoft Edge pro stejné zařízení jako váš profil beznabídkového režimu ([nastavení beznabídkového režimu Windows](kiosk-settings-windows.md)).

[ConfigureKioskMode CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)

### <a name="start-experience"></a>Počáteční zkušenosti

- **Spuštění Microsoft Edge s**: Zvolte, které stránky se otevře při spuštění Microsoft Edge. Možnosti:
  - **Vlastní úvodní stránky**: Zadejte počáteční stránky, jako například `http://www.contoso.com`. Microsoft Edge načte domovských stránkách, které zadáte.
  - **Nová stránka karty**: Microsoft Edge načíst cokoli, co je zadána v **novou adresu URL kartu** nastavení.
  - **Poslední stránka relace**: Microsoft Edge načte poslední stránka relace.
  - **Začít editaci v nastavení místní aplikace**: Spuštění Microsoft Edge s výchozí úvodní stránka určené operačního systému.

- **Povolit uživatelům změnit domovské stránky**: **Ano** (výchozí) umožňuje uživatelům změnit domovské stránky. Správci můžou použít `EdgeHomepageUrls` přejdete stránky, které se uživatelům zobrazí ve výchozím nastavení při otevření Microsoft Edge. **Ne** zablokuje uživatelům možnost měnit úvodních stránek.
- **Povolit webový obsah na nové záložce**: Pokud je nastavena na **Ano** (výchozí), Microsoft Edge se otevře v zadaná adresa URL **novou adresu URL kartu** nastavení. Pokud **novou adresu URL kartu** nastavení je prázdné, Microsoft Edge se otevře nové záložce uvedené v nastavení Microsoft Edge. Uživatelé mohou změnit ji. Pokud je nastavena na **ne**, Microsoft Edge otevře nová karta s prázdnou stránku. Uživatele nelze změnit.
- **Nová adresa URL karty**: Zadejte adresu URL otevřít na nové záložce. Zadejte například `https://www.bing.com` nebo `https://www.contoso.com`.

- **Tlačítko Domů**: Zvolte, co se stane, pokud je zaškrtnuto tlačítko Domů. Možnosti:
  - **Začít editaci**: Otevře se možnost, kterou jste zvolili v **spuštění Microsoft Edge s** nastavení
  - **Nová stránka karty**: Otevře se v zadané adresy URL **nová adresa URL karty** nastavení.
  - **Adresa URL tlačítka domácí**: Zadejte adresu URL pro otevření. Zadejte například `https://www.bing.com` nebo `https://www.contoso.com`.
  - **Tlačítko Domů skrýt**: Skryje tlačítko Domů
- **Umožní uživatelům změnit domovské tlačítko**: **Ano** umožňuje uživatelům změnit domovské tlačítko. Změny uživatele přepsání jakéhokoli nastavení správce na tlačítko Domů. **Ne** zablokuje uživatelům možnost měnit, jak správce nakonfiguruje tlačítko Domů (výchozí).
- **Zobrazit stránku prvního spuštění (jenom mobilní verze)** : **Ano** (výchozí) zobrazí první úvodní stránka použití v Microsoft Edge. **Ne** zastaví úvodní stránky zobrazují první čas spuštění Microsoft Edge. Tato funkce umožňuje podnikům, jako například organizace registrovaná v nulové emisí konfigurace, zablokovat tuto stránku.
- **První spuštění prostředí adresa URL seznamu umístění** (jenom Windows 10 Mobile): Zadejte adresu URL, která odkazuje na soubor XML obsahující první adres(y) URL spuštění stránky. Zadejte například `https://www.contoso.com/sites.xml`.

- **Aktualizujte prohlížeč po nečinnosti**: Zadejte počet nečinných počet minut, než se aktualizují v prohlížeči z 0 – 1 440 minut. Výchozí hodnota je `5` minut. Pokud je nastavena na `0` (nula) v prohlížeči neobnoví po nečinnosti.

  Toto nastavení je k dispozici pouze při spuštění v [procházení InPrivate veřejné (veřejný terminál s jednou aplikací)](#use-microsoft-edge-kiosk-mode).

- **Povolit automaticky otevíraná okna** (jenom desktopové verze): **Ano** (výchozí) umožňuje automaticky otevíraných oken ve webovém prohlížeči. **Ne** brání automaticky otevíraná okna v prohlížeči.
- **Odesílat intranetové přenosy do Internet Exploreru** (jenom desktopové verze): **Ano** umožňuje uživatelům otevírat intranetové weby v Internet Exploreru, ne Microsoft Edge. Toto nastavení slouží potřebám zpětné kompatibility. **Ne** (výchozí) umožňuje uživatelům používat Microsoft Edge.
- **Umístění seznamu webů využívajících režim rozlehlé sítě** (jenom desktopové verze): Zadejte adresu URL, která odkazuje na soubor XML, který obsahuje seznam webů, které se otevřou v podnikovém režimu. Uživatelé nemohou změnit tohoto seznamu. Zadejte například `https://www.contoso.com/sites.xml`.
- **Zpráva při otevírání webů v Internet Exploreru**: Pomocí tohoto nastavení můžete nakonfigurovat Microsoft Edge zobrazíte oznámení před otevřením webu v aplikaci Internet Explorer 11. Možnosti:
  - **Nezobrazovat zprávu**: Výchozí chování operačního systému se používá, které se nemusí zobrazit zprávu.
  - **Zobrazit zprávu, ke které lokalitě je otevřen v aplikaci Internet Explorer 11**: Zobrazit zprávu při otevírání webů v Internet Exploreru. Weby se otevřou v Internet Exploreru. 
  - **Zobrazit zprávu s možností Otevřít servery v Microsoft Edge**: Zobrazit zprávu při otevírání webů v Edgi. Zpráva obsahuje **dál pokračovat v Microsoft Edge** odkaz, takže uživatelé mohou Microsoft Edge místo Internet Exploreru.

  > [!IMPORTANT]
  > Toto nastavení vyžaduje, abyste použili **umístění seznamu webů využívajících režim rozlehlé sítě** nastavení, **odesílání intranetového provozu do Internet Exploreru** nastavení, nebo obě nastavení.

- **Povolí seznam kompatibility Microsoftu**: **Ano** (výchozí) umožňuje používat seznam kompatibility Microsoftu. **Ne** brání seznam kompatibility Microsoftu v Microsoft Edge. Tento seznam od Microsoftu pomáhá Microsoft Edge správně zobrazovat stránky, které se známými problémy s kompatibilitou.
- **Předběžné načtení úvodní stránky a stránky nové karty**: **Ano** (výchozí nastavení) použije výchozí chování operačního systému, který může být přednačtení tyto stránky. Předběžné načítání minimalizuje dobu spuštění Microsoft Edge a načtení nových kartách. **Ne** brání Microsoft Edge od předběžného načítání úvodních stránek a nové záložce.
- **Předběžné spuštění úvodní stránky a stránky nové karty**: **Ano** (výchozí) používá výchozí chování operačního systému, který může být na předběžné spuštění těchto stránek. Před spuštěním pomáhá výkonu Microsoft Edge a minimalizuje dobu potřebnou ke spuštění Microsoft Edge. **Ne** brání Microsoft Edge v předem spouštění úvodních stránek a nové záložce.

Vyberte **OK** uložte provedené změny.

### <a name="favorites-and-search"></a>Oblíbené a vyhledávání

- **Zobrazit panel Oblíbené**: Zvolte, co se stane, že k oblíbeným položkám na libovolné stránce Microsoft Edge. Možnosti:
  - **Na začátku a nové stránky karet**: Ukazuje, Oblíbené položky panelu při spuštění Microsoft Edge a na všech stránkách kartu. Koncoví uživatelé můžou toto nastavení změnit.
  - **Na všech stránkách**: Zobrazí panel Oblíbené položky na všech stránkách. Toto nastavení nejde změnit koncovým uživatelům.
  - **Skryté**: Skryje panel Oblíbené položky na všech stránkách. Toto nastavení nejde změnit koncovým uživatelům.
- **Povolit změny oblíbených položek**: **Ano** (výchozí) používá výchozí operační systém, což umožňuje uživatelům změnit seznam. **Ne** zabrání koncovým uživatelům přidávání, import, řazení nebo úpravy seznamu oblíbených položek.
  - **Seznam oblíbených položek**: Přidáte seznam adres URL k souboru oblíbených položek. Například přidejte `http://contoso.com/favorites.html`.
- **Synchronizovat Oblíbené položky mezi prohlížeči Microsoft** (jenom desktopové verze): **Ano** vynutí Windows synchronizovat Oblíbené položky mezi Internet Explorerem a Microsoft Edgem. Přidání, odstranění, změny a změny pořadí mezi oblíbené položky jsou sdíleny mezi prohlížeči.  **Ne** (výchozí) používá výchozí operační systém, což může uživatelům možnost k synchronizaci oblíbených položek mezi prohlížečů.
- **Výchozí vyhledávací web**: Zvolte výchozí vyhledávací web na zařízení. Koncoví uživatelé mohou tuto hodnotu kdykoli změnit. Možnosti:
  - Vyhledávací web v nastaveních klienta Microsoft Edge
  - Bing
  - Google
  - Yahoo
  - Vlastní hodnota: V **adresa URL Xml OpenSearch**, zadejte adresu URL HTTPS v souboru XML, který obsahuje krátký název a adresu URL na vyhledávací web minimálně. Zadejte například `https://www.contoso.com/opensearch.xml`.
- **Zobrazit návrhy hledání**: **Ano** (výchozí) umožňuje vyhledávací navrhoval weby web při psaní vyhledávání v panelu Adresa. **Ne** brání tuto funkci.
- **Povolit změny v modulu vyhledávání**: **Ano** (výchozí) umožňuje uživatelům přidání nového vyhledávací weby nebo změnit výchozí vyhledávací web v Microsoft Edge. Zvolte **ne** uživatelům zabránit v přizpůsobení vyhledávací web.

  Toto nastavení je k dispozici pouze při spuštění v [normálního režimu (veřejný terminál s více aplikacemi)](#use-microsoft-edge-kiosk-mode).

Vyberte **OK** uložte provedené změny.

### <a name="privacy-and-security"></a>Ochrana osobních údajů a zabezpečení

- **Povolit procházení InPrivate**: **Ano** (výchozí) umožňuje procházení InPrivate v Microsoft Edge. Po zavření všech kartách se službou InPrivate, odstraní Microsoft Edge procházení dat ze zařízení. **Ne** zabrání koncovým uživatelům v otevírání relací procházení InPrivate.
- **Uložit historie procházení**: **Ano** (výchozí) povolit ukládání historie procházení v Microsoft Edge. **Ne** zabrání ukládání historie procházení.
- **Vymazat údaje o ukončení procházení** (jenom desktopové verze): **Ano** vymaže historii a údaje o procházení při ukončení Microsoft Edge uživatelem. **Ne** používá výchozí operační systém, což může ukládat do mezipaměti procházení dat (výchozí).
- **Synchronizovat nastavení prohlížeče mezi zařízeními uživatelů**: Zvolte, jak chcete synchronizovat nastavení prohlížeče mezi zařízeními. Možnosti:
  - **Povolit**: Povolit synchronizaci nastavení prohlížeče Microsoft Edge mezi zařízeními uživatelů
  - **Blokovat a povolit přepsání uživatele**: Blokovat synchronizaci nastavení prohlížeče Microsoft Edge mezi zařízení uživatele. Toto nastavení můžou uživatelé potlačit.
  - **Blok**: Blokovat synchronizaci nastavení prohlížeče Microsoft Edge mezi zařízeními uživatelů. Toto nastavení nelze přepsat uživatelé.

Pokud je vybrána "blokovat a povolit přepsání uživatele", uživatel může přepsat označení správce.

- **Povolit správce hesel**: **Ano** (výchozí) umožňuje, aby automaticky heslo správce, který umožňuje uživatelům ukládat a spravovat hesla v zařízení používat Microsoft Edge. **Ne** Microsoft Edge bránit v použití hesla správce.
- **Soubory cookie**: Zvolte, jak se zpracovává soubory cookie ve webovém prohlížeči. Možnosti:
  - **Povolit**: Soubory cookie se ukládají na zařízení.
  - **Blokovat všechny soubory cookie**: Soubory cookie se ukládají na zařízení.
  - **Blokovat jenom soubory cookie třetích stran**: Třetích stran nebo partnera souborů cookie nejsou uloženy v zařízení.
- **Povolit automatické vyplňování ve formulářích**: **Ano** (výchozí) umožňuje uživatelům změnit nastavení automatického dokončování v prohlížeči a automaticky vyplnit pole formuláře. **Ne** zakáže funkci Automatické vyplňování v Microsoft Edge.
- **Odesílat hlavičky not track**: **Ano** odešle hlavičky not track na weby, které požadují trasovací informace (doporučeno). **Ne** (výchozí) neodesílá záhlaví která umožní webům sledovat uživatele. Uživatel může konfigurovat.
- **Zobrazit IP adresa localhost pro WebRTC**: **Ano** (výchozí) umožňuje IP adresy localhost uživatele zobrazený při telefonování pomocí tohoto protokolu. **Ne** brání IP adresy localhost uživatele před zobrazením. 
- **Povolit shromažďování dat pro živé dlaždice**: **Ano** (výchozí) umožňuje Microsoft Edge ke shromažďování informací z živé dlaždice připnuté do nabídky start. **Ne** zabrání shromažďování těchto informací, které mohou uživatelé poskytnout omezené možnosti.
- **Uživatel může přepsat chyby certifikátů**: **Ano** (výchozí) umožňuje uživatelům přístup k webům, které obsahují chyby Secure Sockets Layer/Transport Layer Security (SSL/TLS). **Ne** (doporučeno pro zvýšení zabezpečení) zabrání uživatelům v přístupu k webům s chybami protokolu SSL nebo TLS.

Vyberte **OK** uložte provedené změny.

### <a name="additional"></a>Další

- **Povolit prohlížeč Microsoft Edge** (jenom mobilní verze): **Ano** (výchozí) umožňuje pomocí webového prohlížeče Microsoft Edge na mobilním zařízení. **Ne** brání použití Microsoft Edge na zařízení. Pokud se rozhodnete **ne**, individuální nastavení platí jenom pro desktop.
- **Povolit rozevírací panel Adresa**: **Ano** (výchozí) umožňuje Microsoft Edge do adresního řádku zobrazit rozevírací seznam návrhů. **Ne** zastaví zobrazování seznamu návrhů v rozevíracím seznamu při psaní Microsoft Edge. Pokud je nastavena na **ne**, můžete:
  - Minimalizovat šířku pásma sítě mezi Microsoft Edge a služby Microsoftu.
  - Zakažte **zobrazovat návrhy vyhledávání a web při psaní** v Microsoft Edge > Nastavení.
- **Povolit režim zobrazení na celé obrazovce**: **Ano** (výchozí) umožňuje Microsoft Edge do celoobrazovkového režimu pro použití, která zobrazuje pouze webového obsahu a skryje uživatelské rozhraní Microsoft Edge. **Ne** brání celoobrazovkového režimu v Microsoft Edge.
- **Povolit příznaky stránka**: **Ano** (výchozí) používá výchozí operační systém, což může umožnit přístup k `about:flags` stránky. `about:flags` Stránky umožňuje uživatelům změnit nastavení vývojáře a povolit experimentální funkce. **Ne** zabrání koncovým uživatelům v přístupu k `about:flags` stránky v Microsoft Edge.
- **Povolit vývojářské nástroje**: **Ano** (výchozí) umožňuje uživatelům používat vývojářské nástroje F12 pomáhají vytvářet a ladit webové stránky ve výchozím nastavení. **Ne** koncovým uživatelům bránit v použití vývojářských nástrojů F12.
- **Povolit JavaScript**: **Ano** (výchozí) umožňuje skripty, jako je Javascript, ke spuštění v prohlížeči Microsoft Edge. **Ne** zabraňuje spuštění skriptů Java v prohlížeči.
- **Uživatel může nainstalovat rozšíření**: **Ano** (výchozí) umožňuje koncovým uživatelům pro instalaci rozšíření Microsoft Edge na zařízení. **Ne** zabrání instalaci.
- **Povolit zkušební načtení před prodejem rozšíření developer**: **Ano** (výchozí) používá výchozí operační systém, což může povolit zkušební načtení před prodejem. Zkušební načtení před prodejem nainstaluje a spustí neověřený rozšíření. **Ne** zabrání zkušební načtení před prodejem pomocí Microsoft Edge **načíst rozšíření** funkce. Nezabrání rozšíření zkušební načtení před prodejem pomocí jiné způsoby, třeba PowerShell.
- **Vyžaduje rozšíření**: Vyberte, jaká rozšíření, nejde ji vypnout koncovým uživatelům v Microsoft Edge. Zadejte název řady balíčku a vyberte **přidat**. [Najít název řady balíčku (PFN)](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) najdete pokyny k.

  Můžete také **Import** soubor CSV, který obsahuje název řady balíčku. Nebo, **exportovat** zadáte názvy řady balíčků.

Vyberte **OK** uložte provedené změny.

## <a name="network-proxy"></a>Síťový proxy server

Použijte tato nastavení [NetworkProxy zásad CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp), který také obsahuje seznam podporovaných edicí Windows.

- **Automaticky zjišťovat nastavení proxy serveru**: **Blok** zakáže zařízení z automatické zjišťování skript automatické konfigurace (PAC) proxy serveru. **Není nakonfigurováno** tuto funkci povolí (výchozí). Když povolené, zařízení se pokusí najít cestu ke skriptu PAC.
- **Použít skript proxy serveru**: Zvolte **povolit** k zadejte cestu ke skriptu PAC ke konfiguraci proxy serveru. **Není nakonfigurováno** neumožňuje (výchozí) zadejte adresu URL ke skriptu PAC.
  - **Nastavení adresy URL skriptu**: Zadejte adresu URL skriptu PAC, který chcete použít ke konfiguraci proxy serveru.
- **Použít ruční proxy server**: Zvolte **povolit** ručně zadat název nebo IP adresu a číslo portu TCP proxy serveru. **Není nakonfigurováno** (výchozí) neumožňuje zadat podrobnosti o proxy serveru ručně.
  - **Adresa**: Zadejte název nebo IP adresu proxy serveru.
  - **Číslo portu**: Zadejte číslo portu proxy serveru.
  - **Výjimky proxy serveru**: Zadejte všechny adresy URL, které nesmí používat proxy server. Jednotlivé položky oddělte středníkem.
  - **Obejít proxy server pro místní adresy**: **Není nakonfigurováno** (výchozí) brání použití proxy serveru pro místní adresy na vašem intranetu. **Povolit** používá proxy server pro místní adresy.

Vyberte **OK** uložte provedené změny.

## <a name="password"></a>Heslo

Použijte tato nastavení [DeviceLock zásad CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock), který také obsahuje seznam podporovaných edicí Windows.

- **Heslo**: **Vyžadovat** koncový uživatel zadal heslo pro přístup k zařízení. **Není nakonfigurováno** (výchozí) umožňuje přístup k zařízení bez hesla. Platí pro pouze místní účty. Hesla k účtům domény zůstanou konfigurace v rámci služby Active Directory (AD) a Azure AD.

  - **Vyžadovaný typ hesla**: Vyberte typ hesla. Možnosti:
    - **Není nakonfigurováno**: Heslo může obsahovat čísla a písmena.
    - **Číselné**: Heslo musí obsahovat pouze čísla.
    - **Alfanumerické**: Heslo musí obsahovat kombinaci čísel a písmen.
  - **Minimální délka hesla**: Zadejte minimální počet nebo znaků, z 4-16. Zadejte například `6` tak, aby vyžadovala minimálně šest znaků heslo.
  
    > [!IMPORTANT]
    > Pokud požadavek na heslo se změnilo na ploše Windows, uživatelů bylo ovlivněno při příštím přihlašování v jako, který má při, co zařízení projde z nečinnosti na aktivní. Uživatelé s heslem, které splňují tento požadavek se stále výzva ke změně hesla.
    
  - **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: Zadejte počet povolených předtím, než se zařízení může být vymaže, až 11 neúspěšných přihlášení. Platné číslo, které zadáte, závisí na edici. [Zprostředkovatel kryptografických služeb DeviceLock/MaxDevicePasswordFailedAttempts](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts) obsahuje seznam podporovaných hodnot. `0` (nula) může zakázat funkce vymazání zařízení.

    Toto nastavení má také jiný dopad, v závislosti na edici. Konkrétní podrobnosti o tomto nastavení najdete v tématu [DeviceLock/MaxDevicePasswordFailedAttempts CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts).

  - **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**: Zadejte dobu, kterou musí být zařízení nečinné, než se uzamkne jeho obrazovka.
  - **Vypršení platnosti hesla (dny)** : Zadejte dobu, kdy musí změnit heslo zařízení, z 1 – 365 dnů. Zadejte například `90` heslo vyprší po 90 dnech.
  - **Zakázat opakované použití předchozích hesel**: Zadejte počet dříve použitých hesel, která nejde použít, 1 – 24. Zadejte například `5` tak uživatelé nemohli nastavit nové heslo pro jejich aktuální heslo nebo některý z předchozí čtyři hesla.
  - **Vyžadovat heslo při návratu zařízení ze stavu nečinnosti** (Mobile a Holographic): Zvolte **vyžadují** , musí uživatelé zadat heslo k odemknutí zařízení po nečinnosti. **Není nakonfigurováno** (výchozí) nevyžaduje kód PIN nebo heslo při návratu zařízení ze stavu nečinnosti.
  - **Jednoduchá hesla**: Nastavte na **bloku** , uživatelé nemůžou vytvářet jednoduchá hesla, jako například `1234` nebo `1111`. Nastavte na **Nenakonfigurováno** (výchozí), umožníte uživatelům vytvářet hesla jako `1234` nebo `1111`. Toto nastavení také povolí obrázková hesla Windows (nebo je zablokuje).
- **Automatické šifrování během AADJ**: **Blok** zabraňuje automatické šifrování zařízení nástroj BitLocker, pokud zařízení je připravený pro první použití, když je zařízení připojeno k Azure AD. **Není nakonfigurováno** (výchozí) používá výchozí operační systém, což může povolit šifrování. Více o [šifrování nástrojem BitLocker zařízení](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption).

  [Security/PreventAutomaticDeviceEncryptionForAzureADJoinedDevices CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-preventautomaticdeviceencryptionforazureadjoineddevices)

- **Federální informace o zpracování Standard (FIPS) zásady**: **Povolit** používá zásady federální informace o zpracování Standard (FIPS), které je US government standard pro šifrování, hašování a podpisování. **Není nakonfigurováno** (výchozí) používá výchozí operační systém, který nepoužívá FIPS.

  [Cryptography/AllowFipsAlgorithmPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-cryptography#cryptography-allowfipsalgorithmpolicy)

- **Ověřování zařízení Windows Hello**: **Povolit** uživatelům používat Windows Hello doprovodná zařízení, například telefon, vhodnosti obsluhy vzdálené správy nebo zařízení IoT pro přihlášení k počítači s Windows 10. **Není nakonfigurováno** (výchozí) používá výchozí operační systém, což může zabránit ověřování pomocí Windows Windows Hello doprovodná zařízení.

  [Authentication/AllowSecondaryAuthenticationDevice CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowsecondaryauthenticationdevice)

- **Webové přihlášení**: Umožňuje Windows přihlášení podporu pro poskytovatele federované bez služby AD FS (Active Directory Federation Services), jako je zabezpečení kontrolního výrazu SAML (Markup Language). SAML využívá zabezpečené tokeny, které poskytují prostředí webového prohlížeče jednotné přihlašování (SSO). Možnosti:

  - **Není nakonfigurováno** (výchozí): Použije výchozí nastavení operačního systému v zařízení.
  - **Povolené**: Poskytovatel přihlašovacích údajů webu je povolen pro přihlášení.
  - **Zakázané**: Poskytovatel přihlašovacích údajů webu je zakázané pro přihlášení.

  [Ověřování/EnableWebSignIn CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-enablewebsignin)

- **Upřednostňovaný doména tenanta Azure AD**: Zadejte název domény ve vaší organizaci Azure AD. Při přihlášení uživatele v této doméně, nemají zadejte název domény. Zadejte například `contoso.com`. Uživatelé v `contoso.com` domény se můžete přihlásit pomocí své uživatelské jméno, například `abby`, namísto `abby@contoso.com`.

  [Authentication/PreferredAadTenantDomainName CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-preferredaadtenantdomainname)

Vyberte **OK** uložte provedené změny.

## <a name="per-app-privacy-exceptions"></a>Výjimky ze zásad ochrany osobních údajů pro jednotlivé aplikace

Můžete přidat aplikace, které by měly mít chování různých ochrany osobních údajů z definujete v "Výchozích zásadách".

- **Název balíčku**: Název řady balíčku aplikace.
- **Název aplikace**: Název aplikace.

### <a name="exceptions"></a>Výjimky

- **Informace o účtu**: Definujte, jestli tato aplikace přístup k uživatelským jménem, obrázku nebo dalším kontaktním informacím.
- **Aplikace na pozadí**: Definujte, jestli tato aplikace může běžet na pozadí.
- **Kalendář**: Definujte, jestli tato aplikace může přístup ke kalendáři.
- **Historie volání**: Definujte, jestli tato aplikace může mít přístup k historii volání.
- **Camera**: Definujte, jestli tato aplikace neměly přístup k fotoaparátu.
- **Kontakty**: Definujte, jestli tato aplikace může mít přístup ke kontaktům.
- **e-mailu**: Definujte, jestli tato aplikace může přistupovat k a odeslání e-mailu.
- **Umístění**: Definujte, jestli tato aplikace může přistupovat k informacím o poloze.
- **Zasílání zpráv**: Definujte, jestli tato aplikace může číst nebo posílat textové zprávy nebo zprávy MMS.
- **Mikrofon**: Definujte, jestli tato aplikace může používat mikrofon.
- **Pohybu**: Definujte, jestli tato aplikace může přistupovat k informacím o pohybu zařízení.
- **Oznámení**: Definujte, jestli tato aplikace může mít přístup k oznámením.
- **Phone**: Definujte, jestli tato aplikace může přistupovat k telefonu.
- **Radiostanice**: Některé aplikace používají bezdrátové (například Bluetooth) pomocí vašeho zařízení odesílat a přijímat data, a potřebují mít možnost vypnout zapnutí nebo vypnutí. Definujte, jestli tato aplikace může tyto moduly používat.
- **Úlohy**: Definujte, jestli tato aplikace mají přístup k úkolům.
- **Důvěryhodná zařízení**: Zvolte, pokud tato aplikace může používat důvěryhodná zařízení. Důvěryhodná zařízení jsou hardwaru, který už jste připojili nebo hardware, který je součástí zařízení. Například použijte jako důvěryhodná zařízení. televizory, projektory a tak dále.
- **Zpětná vazba a Diagnostika**: Definujte, jestli tato aplikace může přístup k diagnostickým informacím.
- **Synchronizace se zařízeními**: Zvolte, pokud tato aplikace může automaticky sdílet a synchronizovat informace s bezdrátovými zařízeními, které se explicitně nepárují s zařízení.

Vyberte **OK** uložte provedené změny.

## <a name="personalization"></a>Personalizace

Pomocí těchto nastavení [individuální nastavení zásad CSP](https://docs.microsoft.com/windows/client-management/mdm/personalization-csp), který také obsahuje seznam podporovaných edicí Windows.

- **Adresa URL obrázku na pozadí plochy (jenom desktopové verze)** : Zadejte adresu URL obrázku ve formátu .jpg, .jpeg nebo .png, který chcete použít jako tapeta na ploše Windows. Uživatelé nemohou tento obrázek změnit. Zadejte například `https://contoso.com/logo.png`.

Vyberte **OK** uložte provedené změny.

## <a name="printer"></a>Tiskárny

- **Tiskárny**: Seznam místních tiskáren, které byly přidány.
- **Výchozí tiskárna**: Nastaví výchozí tiskárnu.
- **Přístup uživatelů k přidávání nových tiskáren**: Povolí nebo zablokuje používání místních tiskáren.

Vyberte **OK** uložte provedené změny.

## <a name="privacy"></a>Ochrana osobních údajů

Použijte tato nastavení [zásady ochrany osobních údajů CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy), který také obsahuje seznam podporovaných edicí Windows.

- **Přizpůsobení vstupu**: **Blok** brání pomocí hlasu pro diktování a komunikovat s Cortanou a další aplikace používající rozpoznávání řeči založené na cloudu společnosti Microsoft. Je zakázané a uživatelům nelze povolit rozpoznávání řeči online pomocí nastavení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům zvolit. Pokud tyto služby povolíte, společnost Microsoft může shromažďovat hlasová data ke zkvalitnění služby.
- **Automatické přijetí párování a ochrana osobních údajů pokynů souhlasu uživatele**: Zvolte **povolit** tak Windows můžete automaticky přijetí párování a ochrana osobních údajů souhlas zpráv při spuštění aplikace. **Není nakonfigurováno** (výchozí) brání automatické přijetí párování a ochrana osobních údajů okno souhlasu uživatele při otevření aplikace.
- **Publikovat aktivity uživatele**: **Blok** zabraňuje sdílení a zjišťování naposledy použitých prostředků v aktivitě kanálu. **Není nakonfigurováno** (výchozí) umožňuje tato funkce, takže aplikace můžete publikovat činnosti koncového uživatele.
- **Jen místní aktivity**: **Blok** zabraňuje sdílení a zjišťování naposledy použitých prostředků při přepínání úloh jen na základě místní aktivity. **Není nakonfigurováno** tuto funkci povolí (výchozí).

Můžete nakonfigurovat informace, které můžete přístup všechny aplikace na zařízení. Navíc definovat výjimky na základě aplikaci pomocí **výjimky ochrany osobních údajů pro jednotlivé aplikace**.

Vyberte **OK** uložte provedené změny.

### <a name="exceptions"></a>Výjimky

- **Informace o účtu**: Definujte, jestli tato aplikace přístup k uživatelským jménem, obrázku nebo dalším kontaktním informacím.
- **Aplikace na pozadí**: Definujte, jestli tato aplikace může běžet na pozadí.
- **Kalendář**: Definujte, jestli tato aplikace může přístup ke kalendáři.
- **Historie volání**: Definujte, jestli tato aplikace může mít přístup k historii volání.
- **Camera**: Definujte, jestli tato aplikace neměly přístup k fotoaparátu.
- **Kontakty**: Definujte, jestli tato aplikace může mít přístup ke kontaktům.
- **e-mailu**: Definujte, jestli tato aplikace může přistupovat k a odeslání e-mailu.
- **Umístění**: Definujte, jestli tato aplikace může přistupovat k informacím o poloze.
- **Zasílání zpráv**: Definujte, jestli tato aplikace může číst nebo posílat textové zprávy nebo zprávy MMS.
- **Mikrofon**: Definujte, jestli tato aplikace může používat mikrofon.
- **Pohybu**: Definujte, jestli tato aplikace může přistupovat k informacím o pohybu zařízení.
- **Oznámení**: Definujte, jestli tato aplikace může mít přístup k oznámením.
- **Phone**: Definujte, jestli tato aplikace může přistupovat k telefonu.
- **Radiostanice**: Některé aplikace používají bezdrátové (například Bluetooth) pomocí vašeho zařízení odesílat a přijímat data, a potřebují mít možnost vypnout zapnutí nebo vypnutí. Definujte, jestli tato aplikace může tyto moduly používat.
- **Úlohy**: Definujte, jestli tato aplikace mají přístup k úkolům.
- **Důvěryhodná zařízení**: Zvolte, pokud tato aplikace může používat důvěryhodná zařízení. Důvěryhodná zařízení jsou hardwaru, který už jste připojili nebo hardware, který je součástí zařízení. Například použijte jako důvěryhodná zařízení. televizory, projektory a tak dále.
- **Zpětná vazba a Diagnostika**: Zvolte, pokud tuto aplikaci může přístup k diagnostickým informacím.
- **Synchronizovat se zařízeními** – Definujte, jestli tato aplikace může automaticky sdílet a synchronizovat informace s bezdrátovými zařízeními, která se explicitně nepárují s tímto počítačem, tabletem nebo telefonem.

Vyberte **OK** uložte provedené změny.

## <a name="projection"></a>Promítání

Použijte tato nastavení [WirelessDisplay zásad CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wirelessdisplay), který také obsahuje seznam podporovaných edicí Windows.

- **Uživatelský vstup z přijímačů bezdrátového zobrazení**: **Blok** brání uživatelský vstup z přijímačů bezdrátového zobrazení. **Není nakonfigurováno** (výchozí) umožňuje bezdrátový displej pro odesílání klávesnice, myš, pera a dotykového ovládání vstup zpátky do zdrojové zařízení.
- **Promítání na tento počítač**: **Blok** brání jiná zařízení v nalezení zařízení pro projekci. **Není nakonfigurováno** (výchozí) umožňuje zjistitelné a můžete projekt tak, aby zařízení nad zamykací obrazovkou zařízení.
- **Párování požadovat PIN kód**: Zvolte **vyžadují** vždy výzvu pro PIN kód při připojení k promítacímu zařízení. **Není nakonfigurováno** PIN kód zařízení k promítacímu zařízení spárovat se nevyžaduje, aby (výchozí).

Vyberte **OK** uložte provedené změny.

## <a name="reporting-and-telemetry"></a>Generování sestav a telemetrie

- **Sdílet data o využití**: Vyberte úroveň diagnostických dat, které je odeslána. Možnosti:
  - **Není nakonfigurováno**: Žádná data se sdílí.
  - **Zabezpečení**: Informace, které je potřeba zajistit, aby byl Windows bezpečnější, včetně dat o nastavení součásti připojené uživatelské prostředí a Telemetrie, nástroj pro odstranění škodlivého softwaru a programem Windows Defender.
  - **Základní**: Informace o základní zařízení, včetně týkající se kvality, kompatibilita aplikací, data o využití aplikace a data z úroveň zabezpečení.
  - **Vylepšené**: Další přehledy, včetně: jak se používají Windows, Windows Server, System Center a aplikací, jejich výkon, pokročilé spolehlivost dat a dat na úrovni Basic a úrovně zabezpečení.
  - **Úplné**: Všechna data potřebná k identifikaci a k řešení problémů, plus data z úrovní zabezpečení, základní a rozšířená.

  [Systém/AllowTelemetry CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)

- **Odeslat Microsoft Edge procházení dat pro Microsoft 365 Analytics**: Chcete-li tuto funkci používat, nastavte **sdílet data o využití** nastavení **rozšířená** nebo **úplné**. Tato funkce řídí, jaká data Microsoft Edge odesílá do Microsoftu 365 Analytics u podnikových zařízení nakonfigurované komerční ID. Možnosti:
  - **Není nakonfigurováno**: Používá výchozí operační systém, který nemůže posílat žádné procházení historie
  - **Odesílala jen data intranetu**: Umožňuje správci posílat intranetový data historie
  - **Odesílala jen internet data**: Umožňuje správci posílat data historie internet
  - **Odesílat intranetové a internetové data**: Umožňuje správci posílat data historie intranetu a Internetu

  [Browser/ConfigureTelemetryForMicrosoft365Analytics CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configuretelemetryformicrosoft365analytics)

- **Proxy server pro telemetrii**: Zadejte plně kvalifikovaný název domény (FQDN) nebo IP adresu proxy serveru pro předávání propojených uživatelských prostředí a Telemetrie požadavky, pomocí připojení vrstvy SSL (Secure Sockets). Formát pro toto nastavení je *server*:*port*. Pokud uvedený proxy server selže nebo pokud není zadán proxy server, při povolování těchto zásad, data propojených uživatelských prostředí a Telemetrie se neposílají a zůstane na místním zařízení.

  Příklady formátů:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

  [Systém/TelemetryProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-telemetryproxy)

Vyberte **OK** uložte provedené změny.

## <a name="search"></a>Search

Použijte tato nastavení [hledat zásady CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search), který také obsahuje seznam podporovaných edicí Windows. 

- **Bezpečné vyhledávání (jenom mobilní verze)** : Řídí, jak Cortana filtruje obsah pro dospělé ve výsledcích hledání. Možnosti:
  - **Uživatelem definované**: Povolit koncovým uživatelům vybrat vlastní nastavení.
  - **Striktní**: Největší filtrování obsahu pro dospělé.
  - **Střední**: Střední filtrování obsahu pro dospělé. Platné výsledky vyhledávání se nebudou filtrovat.
- **Zobrazovat webové výsledky ve vyhledávání**: Pokud je nastavena na **bloku**, nelze vyhledávat uživatele a nejsou zobrazeny webové výsledky ve vyhledávání. **Není nakonfigurováno** (výchozí) umožňuje uživatelům k vyhledávání na webu a výsledky se zobrazí na zařízení.

Vyberte **OK** uložte provedené změny.

## <a name="start"></a>Spustit

Použijte tato nastavení [spuštění zásad CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start), který také obsahuje seznam podporovaných edicí Windows.  

- **Rozložení nabídky Start**: Přepsat výchozí rozložení nabídky start a přizpůsobení nabídky start na desktopových zařízeních. Nahrajte soubor XML, který obsahuje vaše vlastní nastavení, včetně pořadí, ve kterém jsou uvedené aplikace a další. Uživatelé nemohou měnit rozložení nabídky start, které zadáte.
- **Připnout weby na dlaždice do nabídky Start**: Importovat Image z Microsoft Edge, které se zobrazují jako odkazy v nabídce Windows Start pro desktopové zařízení.
- **Odepínání aplikací z hlavního panelu**: **Blok** brání uživateli v odepínání aplikací z hlavního panelu. **Není nakonfigurováno** (výchozí) umožňuje uživatelům odepínání aplikací z hlavního panelu.
- **Rychlé přepínání uživatelů**: **Blok** zabrání přepnutí mezi uživatele, kteří jsou přihlášení současně bez odhlašování. **Není nakonfigurováno** (výchozí) ukazuje **Přepnout uživatele** na dlaždici uživatele.
- **Nejpoužívanější aplikace**: **Blok** se skryjí nejpoužívanější aplikace ze zobrazení v nabídce start. Zároveň se zakáže odpovídající přepínač v aplikaci Nastavení. **Není nakonfigurováno** (výchozí) zobrazí nejčastěji používané aplikace.
- **Naposledy přidané aplikace**: **Blok** skryje nedávno přidaných aplikací ze zobrazení v nabídce start. Zároveň se zakáže odpovídající přepínač v aplikaci Nastavení. **Není nakonfigurováno** (výchozí) zobrazí naposledy přidané aplikace v nabídce start.
- **Režim úvodní obrazovky**: Zvolte, jak je znázorněno na obrazovce start. Možnosti:
  - **Uživatelem definované**: Nelze vynutit velikost úvodní. Uživatelé můžou nastavit velikost.
  - **Zobrazení na celé obrazovce**: Vynutí velikost celé obrazovce Start.
  - **V okně**: Vynutit velikost – celá obrazovka Start.
- **Naposledy otevřené položky v seznamech odkazů**: **Blok** skryje poslední seznamy odkazů ze zobrazených v nabídce start a na hlavním panelu. Zároveň se zakáže odpovídající přepínač v aplikaci Nastavení. **Není nakonfigurováno** (výchozí) zobrazí naposledy otevřených položek v seznamy odkazů.
- **Seznam aplikací**: Zvolte, jak jsou uvedeny všechny seznamy aplikací. Možnosti:
  - **Uživatelem definované**: Žádné nastavení, je vynucena. Uživatelé vybrat, jak se zobrazí seznam aplikací na zařízení.
  - **Sbalit**: Skryjte seznam všech aplikací.
  - **Sbalit a zakázat aplikaci nastavení**: Skrýt seznam všech aplikací a zakažte **zobrazit seznam aplikací v nabídce Start** v aplikaci nastavení.
  - **Odebere a v aplikaci nastavení zakáže**: Skrýt seznam všech aplikací, tlačítko všechny aplikace odebrat a zakázat **zobrazit seznam aplikací v nabídce Start** v aplikaci nastavení.
- **Tlačítko napájení**: **Blok** skryje tlačítko napájení v nabídce start zobrazuje. **Není nakonfigurováno** (výchozí) zobrazí na tlačítku napájení.
- **Dlaždici uživatele**: **Blok** skryje dlaždice uživatele zobrazuje v nabídce start. **Není nakonfigurováno** (výchozí) zobrazí na dlaždici uživatele a také nastaví následující nastavení:
  - **Zámek**: **Blok** skryje **Zámek** možnost ukazující na dlaždici uživatele v nabídce start. **Není nakonfigurováno** (výchozí) ukazuje **Zámek** možnost.
  - **Odhlásit se**: **Blok** skryje **Odhlásit** možnost ukazující na dlaždici uživatele v nabídce start. **Není nakonfigurováno** (výchozí) ukazuje **Odhlásit** možnost.
- **Vypnout**: **Blok** skryje **aktualizace a provádějte vypnutí** a **vypnout** možnosti ze zobrazení na tlačítku napájení v nabídce start. **Není nakonfigurováno** (výchozí) zobrazí tyto možnosti.
- **Přejít do režimu spánku**: **Blok** skryje **přejít do režimu spánku** možnost ukazující na tlačítku napájení v nabídce start. **Není nakonfigurováno** zobrazí tato možnost (výchozí).
- **Do režimu hibernace**: **Blok** skryje **přejít do režimu hibernace** možnost ukazující na tlačítku napájení v nabídce start. **Není nakonfigurováno** zobrazí tato možnost (výchozí).
- **Přepnout účet**: **Blok** skryje **přepnout účet** ze zobrazení uživatele dlaždice do nabídky start. **Není nakonfigurováno** zobrazí tato možnost (výchozí).
- **Možnosti restartování**:  **Blok** skryje **aktualizovat a restartovat** a **restartovat** možnosti ze zobrazení na tlačítku napájení v nabídce start. **Není nakonfigurováno** (výchozí) zobrazí tyto možnosti.
- **Dokumenty v nabídce Start**: Skrýt nebo zobrazit složku Dokumenty v nabídce Windows Start. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení, je vynucena. Uživatelům se rozhodli zobrazit nebo skrýt klávesovou zkratku.
  - **Skrýt**: Zástupce je skrytá a zakáže nastavení v aplikaci nastavení.
  - **Zobrazit**: Zástupce je zobrazeny a nastavení v aplikaci nastavení se zakáže.
- **Soubory ke stažení v nabídce Start**: Skrýt nebo zobrazit složku stažené soubory v nabídce Windows Start. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení, je vynucena. Uživatelům se rozhodli zobrazit nebo skrýt klávesovou zkratku.
  - **Skrýt**: Zástupce je skrytá a zakáže nastavení v aplikaci nastavení.
  - **Zobrazit**: Zástupce je zobrazeny a nastavení v aplikaci nastavení se zakáže.
- **Průzkumník souborů v nabídce Start**: Skrytí nebo zobrazení Průzkumník souborů v nabídce Windows Start. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení, je vynucena. Uživatelům se rozhodli zobrazit nebo skrýt klávesovou zkratku.
  - **Skrýt**: Zástupce je skrytá a zakáže nastavení v aplikaci nastavení.
  - **Zobrazit**: Zástupce je zobrazeny a nastavení v aplikaci nastavení se zakáže.
- **Domácí skupina v nabídce Start**: Skrytí nebo zobrazení zástupce domácí skupina v nabídce Windows Start. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení, je vynucena. Uživatelům se rozhodli zobrazit nebo skrýt klávesovou zkratku.
  - **Skrýt**: Zástupce je skrytá a zakáže nastavení v aplikaci nastavení.
  - **Zobrazit**: Zástupce je zobrazeny a nastavení v aplikaci nastavení se zakáže.
- **Hudba v nabídce Start**: Skrýt nebo zobrazit složku Hudba v nabídce Windows Start. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení, je vynucena. Uživatelům se rozhodli zobrazit nebo skrýt klávesovou zkratku.
  - **Skrýt**: Zástupce je skrytá a zakáže nastavení v aplikaci nastavení.
  - **Zobrazit**: Zástupce je zobrazeny a nastavení v aplikaci nastavení se zakáže.
- **Síť v nabídce Start**: Skrýt nebo zobrazit síť v nabídce Windows Start. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení, je vynucena. Uživatelům se rozhodli zobrazit nebo skrýt klávesovou zkratku.
  - **Skrýt**: Zástupce je skrytá a zakáže nastavení v aplikaci nastavení.
  - **Zobrazit**: Zástupce je zobrazeny a nastavení v aplikaci nastavení se zakáže.
- **Složka Osobní v nabídce Start**: Skrýt nebo zobrazit složku Osobní v nabídce Windows Start. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení, je vynucena. Uživatelům se rozhodli zobrazit nebo skrýt klávesovou zkratku.
  - **Skrýt**: Zástupce je skrytá a zakáže nastavení v aplikaci nastavení.
  - **Zobrazit**: Zástupce je zobrazeny a nastavení v aplikaci nastavení se zakáže.
- **Obrázky v nabídce Start**: Skrýt nebo zobrazit složku s obrázky v nabídce Windows Start. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení, je vynucena. Uživatelům se rozhodli zobrazit nebo skrýt klávesovou zkratku.
  - **Skrýt**: Zástupce je skrytá a zakáže nastavení v aplikaci nastavení.
  - **Zobrazit**: Zástupce je zobrazeny a nastavení v aplikaci nastavení se zakáže.
- **Nastavení v nabídce Start**: Skrytí nebo zobrazení zástupce nastavení v nabídce Windows Start. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení, je vynucena. Uživatelům se rozhodli zobrazit nebo skrýt klávesovou zkratku.
  - **Skrýt**: Zástupce je skrytá a zakáže nastavení v aplikaci nastavení.
  - **Zobrazit**: Zástupce je zobrazeny a nastavení v aplikaci nastavení se zakáže.
- **Videa v nabídce Start**: Skrýt nebo zobrazit složku s videi v nabídce Windows Start. Možnosti:
  - **Není nakonfigurováno** (výchozí): Žádné nastavení, je vynucena. Uživatelům se rozhodli zobrazit nebo skrýt klávesovou zkratku.
  - **Skrýt**: Zástupce je skrytá a zakáže nastavení v aplikaci nastavení.
  - **Zobrazit**: Zástupce je zobrazeny a nastavení v aplikaci nastavení se zakáže.

Vyberte **OK** uložte provedené změny.

## <a name="windows-defender-smart-screen"></a>Filtr SmartScreen v programu Windows Defender

- **Filtr SmartScreen pro Microsoft Edge**: **Vyžadovat** vypne Windows Defender SmartScreen a zabrání uživatelům ho zapnout. **Není nakonfigurováno** (výchozí) zapnutí filtru SmartScreen. Pomáhá chránit uživatele před potenciálními hrozbami a zabrání uživatelům ho vypnout.

  Microsoft Edge používá Windows Defender SmartScreen (zapnuto) k ochraně uživatelů před podvodných potenciální a škodlivým softwarem.

  [Browser/AllowSmartScreen CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)

- **Přístup na škodlivý web**: **Blok** zabraňuje uživatelům možnost Ignorovat upozornění filtru Windows Defender SmartScreen a blokuje z přejít na daný web. **Není nakonfigurováno** (výchozí) umožňuje uživatelům ignorovat upozornění a pokračovat na příslušný web.

  [Browser/PreventSmartScreenPromptOverride CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride)

- **Stahování neověřených souborů**: **Blok** zabraňuje uživatelům možnost Ignorovat upozornění filtru Windows Defender SmartScreen a znemožní jim stahovat neověřené soubory. **Není nakonfigurováno** (výchozí) umožňuje uživatelům ignorovat upozornění a pokračovat ve stahování neověřených souborů.

  [Browser/PreventSmartScreenPromptOverrideForFiles CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles)

Vyberte **OK** uložte provedené změny.

## <a name="windows-spotlight"></a>Windows Spotlight

Pomocí těchto nastavení [prostředí zásad CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience), který také obsahuje seznam podporovaných edicí Windows.

- **Windows Spotlight**: **Blok** vypne Windows spotlight na zamykací obrazovce, tipy Windows, uživatelské funkce Microsoftu a jiné související funkce. Pokud je vaším cílem je minimalizovat síťový provoz ze zařízení, nastavte na **bloku**. **Není nakonfigurováno** (výchozí) umožňuje Windows spotlight funkce a může ovlivnit koncovými uživateli. Pokud povolená, můžete také povolit nebo blokovat následující nastavení:

  - **Windows Spotlight na zamykací obrazovce**: **Blok** Windows Spotlight zastaví zobrazování informací na zamykací obrazovce zařízení. **Není nakonfigurováno** tuto funkci povolí (výchozí).
  - **Návrhy třetích stran ve Windows Spotlightu**: **Blok** zabraňuje Windows Spotlightu návrhy obsahu, který nebyl vydán microsoftem. **Není nakonfigurováno** (výchozí) umožňuje aplikaci a návrhy obsahu vydavatelů softwaru partnera ve Windows spotlightu funkce, jako je spotlight zámek obrazovky, navrhované aplikace v nabídce Start a tipy Windows.
  - **Uživatelské funkce**: **Blok** vypne prostředí, která jsou obvykle jenom uživatelům, třeba návrhy nabídky start, oznámení o členství, mimo po instalaci aplikace pole prostředí a dlaždice pro přesměrování. **Není nakonfigurováno** (výchozí) umožňuje tyto funkce.
  - **Tipy Windows**: **Blok** zakáže automaticky otevíraných tipů Windows. **Není nakonfigurováno** (výchozí) umožňuje tipy Windows k zobrazení.
  - **Windows Spotlight v Centru akcí**: **Blok** brání oznámení Windows spotlightu ze zobrazení v Centru akcí. **Není nakonfigurováno** (výchozí) může zobrazit oznámení v Centru akcí, který návrh aplikace nebo funkce, které pomáhají uživatelům pomohly zvýšit produktivitu práce ve Windows.
  - **Přizpůsobení Windows Spotlightu**: **Blok** brání Windows používat diagnostická data k poskytování přizpůsobených prostředí uživateli. **Není nakonfigurováno** (výchozí) umožňuje společnosti Microsoft se použití diagnostických dat k zajištění individuální doporučení, tipy a nabídky přizpůsobit potřebám uživatele Windows.
  - **Prostředí uvítání Windows**: **Blok** funkce prostředí vypne Windows spotlight uvítání systémem Windows. Prostředí uvítání systémem Windows se nezobrazí, pokud nejsou aktualizace a změny do Windows a jeho aplikace. **Není nakonfigurováno** (výchozí) umožňuje Windows Vítejte v prostředí, které uživateli zobrazuje informace o nových nebo aktualizovaných funkcích.

Vyberte **OK** uložte provedené změny.

## <a name="windows-defender-antivirus"></a>Antivirová ochrana v programu Windows Defender

Pomocí těchto nastavení [zásady defender CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender), který také obsahuje seznam podporovaných edicí Windows.

- **Monitorování v reálném čase**: **Povolit** brání v reálném čase vyhledávání malwaru, spywaru a dalšího nežádoucího softwaru. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Monitorování chování**: **Povolit** brání programu Defender zjišťovat na zařízeních výskyt určitých známých vzorců podezřelých aktivit. **Není nakonfigurováno** (výchozí) umožňuje sledování chování Windows Defender.
- **Systém kontroly (NIS) sítě**: Systém NIS pomáhá chránit zařízení před zneužitím sítě. Používá signatury známých slabých míst z Centra Microsoftu pro ochranu koncových bodů ke zjištění a blokování škodlivého síťového provozu.
- **Kontrolovat všechna stahování**: Určuje, jestli bude Defender kontrolovat všechny soubory stahované z internetu.
- **Kontrolovat skripty načtené do webových prohlížečů Microsoftu**: **Není nakonfigurováno** (výchozí) umožňuje programu Defender kontrolovat skripty, které se používají v Internet Exploreru. **Povolit** brání toto vyhledávání.
- **Přístup koncového uživatele k Defenderu**: **Blok** skryje uživatelské rozhraní Windows Defenderu koncovým uživatelům. Všechna oznámení programu Windows Defender jsou potlačeny také. **Není nakonfigurováno** (výchozí) umožňuje uživateli přístup k rozhraní Windows Defenderu. Když toto nastavení změníte, projeví se změna až při příštím restartování počítače koncovým uživatelem.
- **Interval aktualizace podpisu (v hodinách)** : Zadejte interval, který Defender zkontroluje dostupnost nových souborů signatur z 0-24. Možnosti:

  - **Není nakonfigurováno** (výchozí)
  - **Nezaškrtávejte políčko**: Není Defender zjišťovat dostupnost nových souborů signatur.
  - **1 – 24**: `1` kontroluje každou hodinu `2` kontroluje každé dvě hodiny, `24` zkontroluje každý den a tak dále.
- **Monitorovat aktivitu souborů a programů**: Umožňuje Defenderu monitorování aktivity souborů a programů v zařízení.
- **Počet dní před odstraněním malwaru v karanténě**: Dál sledovat vyřešené problémy s malwarem pro počet dní, které zadáte, abyste mohli ručně zkontrolovat dříve zasažená zařízení. Pokud nastavíte počet dnů **0**, malware zůstane ve složce karantény a automaticky se neodebere. Pokud je nastavena na `90`, karantény položek se uchovávají po dobu 90 dní v systému a potom se odeberou.
- **Limit využití procesoru při kontrole**: Maximální procento využití procesoru, které můžou používat, kontroly z **1** k **100**.
- **Prohledat archivní soubory**: **Povolit** brání Defender z kontrolovat archivované soubory, jako jsou soubory Zip nebo Cab. **Není nakonfigurováno** (výchozí) umožňuje toto vyhledávání.
- **Kontrolovat příchozí e-mailové zprávy**: **Povolit** umožňuje programu Defender kontrolovat e-mailové zprávy při jejich doručení na zařízení. **Není nakonfigurováno** (výchozí) zabrání vyhledávání e-mailu.
- **Během úplné kontroly kontrolovat vyměnitelné jednotky**: **Povolit** brání úplné kontroly vyměnitelných jednotek. **Není nakonfigurováno** (výchozí) umožňuje programu Defender kontrolovat vyměnitelné jednotky, jako jsou USB Flash disky.
- **Kontrolovat namapované síťové jednotky během úplného prohledávání**: **Povolit** umožňuje programu Defender kontrolovat soubory na namapovaných síťových jednotkách. **Není nakonfigurováno** (výchozí) brání úplnou kontrolu. Pokud jsou soubory na disku jen pro čtení, nelze Defender odebrat žádný malware, který v nich najde.
- **Kontrolovat soubory otevřené ze síťových složek**: **Není nakonfigurováno** (výchozí) umožňuje programu Defender kontrolovat soubory na sdílených síťových jednotkách, jako jsou například soubory přistupuje pomocí cesty UNC. **Povolit** brání toto vyhledávání. Pokud jsou soubory na disku jen pro čtení, nelze Defender odebrat žádný malware, který v nich najde.
- **Cloudová ochrana**: **Není nakonfigurováno** (výchozí) umožňuje Microsoft Active Protection Service přijímat informace o činnosti malwaru ze zařízení, která spravujete. **Povolit** blokuje tuto funkci.
- **Dotázat se uživatele před odesláním vzorku**: Ovládací prvky, zda potenciálně škodlivých souborů, které by mohly vyžadovat další analýzu jsou automaticky odeslány společnosti Microsoft. Možnosti:
  - **Není nakonfigurováno**
  - **Vždycky se zeptat**
  - **Dotázat se před odesláním osobních údajů**
  - **Nikdy neodesílat data**
  - **Odeslat veškerá data bez zobrazení výzvy**: Data se automaticky odesílají.

- **Čas k provedení každodenní rychlou kontrolu**: Vyberte hodinu spustit denní rychlé prohledávání. **Není nakonfigurováno** každodenní kontrolu se nespustí. Pokud chcete větší míru přizpůsobení, konfigurace **typ systémové kontroly provádět** nastavení.

  [Defender/ScheduleQuickScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime)

  > [!WARNING]
  > Toto nastavení v Intune na portálu Azure portal může zobrazovat ve stavu selhalo. Jedná se o chybu pomocí funkce vytváření sestav. Po reprodukci chování a řešení potíží, produktové skupiny Intune potvrdit, že stav je ve skutečnosti úspěch. Vytváření sestav chyba bude opravena v nadcházející verzi. Jak změnit časové osy není aktuální odhadovaným časem doručení. Jsou všechny aktualizace této funkce oznámili v [ve vývoji pro Microsoft Intune](in-development.md).

- **Typ systémové kontroly provádět**: Naplánujte úplnou kontrolu, včetně úroveň prohledávání a datum a čas ke spuštění kontroly. Možnosti:
  - **Není nakonfigurováno**: Nelze naplánovat kontrolu systému na zařízení. Koncovým uživatelům můžete ručně spustit prohledávání jako potřebné nebo požadované na svých zařízeních.
  - **Zakázat**: Zakáže všechny systémy kontroly na zařízení. Tuto možnost zvolte, pokud používáte partnerského řešení antivirový program, který vyhledá zařízení.
  - **Rychlá kontrola**: Kontrolují společného místa, kde by mohl být malware zaregistrovaný, jako jsou klíče registru a známé spouštěcí složky Windows.
    - **Naplánovaný den**: Vyberte den, abyste mohli prohledávání.
    - **Naplánovaný čas**: Vyberte hodinu k prohledání.
  - **Úplná kontrola**: Kontrolují místa, běžné tam, kde může být malware zaregistrovaný a také kontroluje všech souborů a složek na zařízení.
    - **Naplánovaný den**: Vyberte den, abyste mohli prohledávání.
    - **Naplánovaný čas**: Vyberte hodinu k prohledání.

  Toto nastavení dojít ke konfliktu se **času provádění každodenní rychlou kontrolu** nastavení. Několik doporučení:

  - Spustit denní rychlé prověřování, pokud chcete nakonfigurovat **času provádění každodenní rychlou kontrolu** nastavení.
  - Spustit denní rychlé prohledávání a úplnou kontrolu každý týden, nakonfigurujte **času provádění každodenní rychlou kontrolu**. Nastavte **typ systémové kontroly provádět** na úplné prohledávání se datum a čas.
  - Nekonfigurujte **času provádění každodenní rychlou kontrolu** nastavení současně s **typ systémové kontroly provádět** nastavena na **Rychlá kontrola**. Tato nastavení dojít ke konfliktu a kontroly se možná nespustí.
  - Chcete-li spustit rychlé prověřování každé úterý v 6: 00, nakonfigurovat **typ systémové kontroly provádět** nastavení.

  [Defender/ScanParameter CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter)  
  [Defender/ScheduleScanDay CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday)  
  [Defender/ScheduleScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime)

  > [!WARNING]
  > Toto nastavení v Intune na portálu Azure portal může zobrazovat ve stavu selhalo. Jedná se o chybu pomocí funkce vytváření sestav. Po reprodukci chování a řešení potíží, produktové skupiny Intune potvrdit, že stav je ve skutečnosti úspěch. Vytváření sestav chyba bude opravena v nadcházející verzi. Jak změnit časové osy není aktuální odhadovaným časem doručení. Jsou všechny aktualizace této funkce oznámili v [ve vývoji pro Microsoft Intune](in-development.md).

- **Zjišťovat potenciálně nežádoucí aplikace**: Zvolte stupeň ochrany, pokud Windows zjistí potenciálně nežádoucí aplikace. Možnosti:
  - **Není nakonfigurováno** (výchozí): Program Windows Defender je ochrana potenciálně nežádoucí aplikace zakázaná.
  - **Blok**: Program Windows Defender zjistí potenciálně nežádoucí aplikace a jsou blokovány zjištěných položek. Tyto položky zobrazit v historii spolu s dalšími hrozbami.
  - **Audit**: Program Windows Defender zjistí potenciálně nežádoucí aplikace, ale neprovede žádnou akci. Můžete zkontrolovat informace o aplikacích, které program Windows Defender by Postavte se. Například vyhledejte události vytvořené programem Windows Defender v události prohlížeč.

  Další informace o potenciálně nežádoucích aplikacích najdete v tématu [detekovat a blokovat potenciálně nežádoucí aplikace](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).

- **Akce ohledně zjištěných malwarových hrozeb**: Vyberte akce, které má Defender provést na jednotlivých úrovních hrozeb detekuje: s nízkou, střední, vysoká a závažnost. Pokud není možné, program Windows Defender vybere nejlepší volbou, ujistěte se, že se hrozba vyřeší. Možnosti:
  - **Vyčistit**
  - **Karanténa**
  - **Odebrat**
  - **Povoleno**
  - **Definováno uživatelem**
  - **Blokováno**

Vyberte **OK** uložte provedené změny.

### <a name="windows-defender-antivirus-exclusions"></a>Výjimky antivirové ochrany v programu Windows Defender

- **Soubory a složky, které chcete vyloučit z kontrol a ochrany v reálném čase**: Umožňuje do seznamu vyloučení přidat soubory a složky, například **C:\Cesta** nebo **%ProgramFiles%\Cesta\název_souboru.exe**. Tyto soubory a složky nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.
- **Vyloučit z kontrol a ochrany v reálném čase přípony souborů**: Umožňuje do seznamu vyloučení přidat přípony souborů, například **jpg** nebo **txt**. Soubory s těmito příponami nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.
- **Procesy, které chcete vyloučit z kontrol a ochrany v reálném čase**: Umožňuje do seznamu vyloučení přidat procesy typu **.exe**, **.com** nebo **.scr**. Tyto procesy nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.

Vyberte **OK** uložte provedené změny.

## <a name="next-steps"></a>Další postup

Další technické podrobnosti o jednotlivých nastaveních a podporovaných edicích Windows najdete v [referenčních informacích o poskytovateli konfiguračních služeb pro zásady (CSP) pro Windows 10](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).
