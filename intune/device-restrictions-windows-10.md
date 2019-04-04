---
title: Nastavení omezení zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Zobrazit seznam všech nastavení a jejich popisy pro vytvoření omezení zařízení v systému Windows 10 a novější zařízení. Chcete-li řídit snímky obrazovky, požadavky na heslo, nastavení beznabídkového režimu, aplikace ve storu, prohlížeč Microsoft Edge, program Windows defender, přístup do cloudu a nabídce start a další v Microsoft Intune pomocí těchto nastavení v profilu konfigurace.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/03/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 51c1ee388c6930c328aff23cc6fc6db730097b86
ms.sourcegitcommit: 699427f36dbf31dc7921fb75da647b736eafd79b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/03/2019
ms.locfileid: "58899066"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>Nastavení Windows 10 (a novějších) zařízení a povolení nebo zakázání funkcí pomocí Intune

Tento článek uvádí a popisuje všechny různých nastaveních, pomocí kterých můžete řídit na Windows 10 a novější zařízení. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete povolit nebo zakázat funkce, nastavit pravidla pro hesla, přizpůsobení zamykací obrazovka, použijte program Windows Defender a další.

Tato nastavení jsou přidány do konfiguračního profilu zařízení v Intune a potom přiřazené nebo nasazené na zařízení s Windows 10.

> [!Note]
> Některé možnosti jsou dostupné ve všech edicích systému Windows. Podporované edice zobrazíte najdete [zásad poskytovatele CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) (otevře jiný web společnosti Microsoft).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](device-restrictions-configure.md#create-the-profile).

## <a name="app-store"></a>App Store

- **App storu (jenom mobilní verze)**: Povolí nebo zablokuje použití app storu na zařízeních s Windows 10 Mobile.
- **Automaticky aktualizovat aplikace ze storu**: Umožňuje aplikací nainstalovaných z Microsoft Store automaticky aktualizovat.
- **Instalace důvěryhodné aplikace**: Povolí aplikacím, které jsou podepsané důvěryhodným certifikátem instalovaly bokem.
- **Odemčení pro vývojáře**: Povolit nastavení pro vývojáře Windows, například můžete umožnit zkušebně načtené aplikace má být upraven koncový uživatel.
- **Sdílená data aplikací uživatele**: Povolí aplikacím sdílet data mezi různými uživateli na stejném zařízení.
- **Použít pouze privátní úložiště**: Povolte a Povolit jenom stahování aplikací z vašeho privátního úložiště koncovým uživatelům.
- **Spuštění aplikace pocházející ze Store**: Používá se k zakázání všech aplikací, které byly předem nainstalované na zařízení nebo stažených z Microsoft Store.
- **Nainstalovat data aplikací na systémový svazek**: Zabrání aplikacím ukládat data na systémový svazek zařízení.
- **Nainstalovat aplikace na systémovou jednotku**: Zabrání aplikacím ukládat data na systémovou jednotku zařízení.
- **(Jenom desktopové verze) záznam ze hry**: Nakonfiguruje, jestli je povolené záznam a vysílání z her.
- **Aplikace ze storu jenom**: Nakonfiguruje, jestli uživatelé můžou instalovat aplikace odjinud než v app storu.

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení

- **Mobilní datový kanál**: Zakáže uživatelům používat data, třeba k procházení webu, při připojení k mobilní síti. 
- **Datový roaming**: Povoluje roaming mezi sítěmi při přístupu k datům.
- **VPN přes mobilní síť**: Určuje, jestli zařízení může při připojení k mobilní síti získat přístup k připojením VPN.
- **VPN v mobilní síti v roamingu**: Určuje, jestli zařízení může při roamingu v mobilní síti získat přístup k připojením VPN.
- **Bluetooth**: Určuje, jestli uživatel může zapnout a konfigurovat Bluetooth na zařízení.
- **Zjistitelnost zařízení Bluetooth**: Umožňuje zařízení být zjištěny jinými zařízeními podporujícími technologii Bluetooth.
- **Párování Bluetooth předem**: Umožňuje konfigurovat automatické párování s hostujícím zařízením určitých zařízení Bluetooth.
- **Reklama přes Bluetooth**: Umožňuje zařízení přijímat reklamu přes Bluetooth.
- **Služba připojených zařízení**: Umožňuje zvolit, aby služba připojených zařízení, která umožňuje zjišťování a připojování dalších zařízení Bluetooth.
- **NFC**: Umožní uživateli povolit a konfigurovat téměř funkce pole komunikace (NFC) na zařízení.
- **Wi-Fi**: Umožní uživateli povolit a konfigurovat Wi-Fi na zařízení (jenom Windows 10 Mobile).
- **Automaticky se připojovat k Wi-Fi hotspotům**: Umožňuje zařízení automaticky se připojovat k volným Wi-Fi hotspotům a automaticky pro připojení přijímat jakékoli podmínky a ujednání.
- **Ruční konfigurace Wi-Fi**: Určuje, jestli může uživatel nakonfigurovat svoje vlastní Wi-Fi připojení, nebo jestli může použít jenom připojení nakonfigurovaná v rámci profilu Wi-Fi (jenom Windows 10 Mobile).
- **Interval skenování Wi-Fi**: Zadejte, jak často zařízení skenují sítě Wi-Fi. Zadejte hodnotu od 1 (nejčastěji) na 500 (nejméně často).
- **Povolené služby Bluetooth**: Zadejte jako hexadecimálních řetězců na seznam povolených služeb a profilů Bluetooth.

## <a name="cloud-and-storage"></a>Cloud a úložiště

- **Účet Microsoft**: Umožňuje uživateli přidružit k zařízení účet Microsoft.
- **Účet od jiných výrobců**: Umožňuje přidat do zařízení e-mailové účty, které nejsou přidružené k účtu Microsoft.
- **Synchronizace nastavení pro účet Microsoft**: Povolit nastavení zařízení a aplikací, které jsou přidružené k účtu Microsoft k synchronizaci mezi zařízeními.
- **Microsoft Account Pomocníka pro přihlášení**: Zvolte **zakázat** koncovým uživatelům zabránit řízení služby Pomocníka pro přihlášení společnosti Microsoft (wlidsvc), jako je například ručně zastavení nebo spuštění služby. Pokud je nastavena na **Nenakonfigurováno**, službu wlidsvc NT používá výchozí operační systém (OS), což může umožnit koncovým uživatelům spouštět a zastavovat služby. Tato služba používá operační systém umožňující uživatelům umožní přihlásit ke svému účtu Microsoft.

## <a name="cloud-printer"></a>Cloudová tiskárna

- **Adresa URL pro zjišťování tiskáren**: Zadejte adresu URL pro hledání cloudových tiskáren.
- **Adresa URL autority pro přístup k tiskárnám**: Zadejte adresu URL koncového bodu ověřování k získání tokenů OAuth. Zadejte třeba `https://login.microsoftonline.com/your Azure AD Tenant ID`.
- **Nativní klientské aplikace Azure GUID**: Zadejte identifikátor GUID klientské aplikace k získání tokenů OAuth od OAuthAuthority povolené.
- **Služba identifikátor URI prostředku tiskové**: Zadejte identifikátor URI prostředku OAuth pro tiskovou službu nakonfigurované na webu Azure Portal. Zadejte třeba `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Maximální počet tiskáren pro dotaz (jenom mobilní verze)**: Zadejte maximální počet tiskáren, na které chcete, aby se dalo dotazovat. Zadejte například `10`.
- **Identifikátor URI prostředku služby zjišťování tiskáren**: Zadejte identifikátor URI prostředku OAuth pro zjišťování tiskáren služba nakonfigurovaná na webu Azure Portal. Zadejte třeba `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Po nastavení [hybridního cloudového tisku Windows Serveru](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview) můžete tato nastavení nakonfigurovat a následně nasadit do zařízení s Windows.

## <a name="control-panel-and-settings"></a>Ovládací panely a nastavení

- **Nastavení aplikace**: Blokovat přístup k aplikaci nastavení Windows.
  - **Systém**: Blokuje přístup k systémové oblasti v aplikaci nastavení.
    - **Změny nastavení napájení a režimu spánku (jenom desktopové verze)**: Zabrání koncovému uživateli možnost měnit nastavení napájení a režimu spánku na zařízení.
  - **zařízení**: Zablokuje přístup k oblasti zařízení v aplikaci nastavení.
  - **Network Internet**: Zablokuje přístup k oblasti sítě a Internetu v aplikaci nastavení.
  - **Přizpůsobení**: Zablokuje přístup k oblasti přizpůsobení v aplikaci nastavení.
  - **Účty**: Blokuje přístup k oblasti účtů v aplikaci nastavení.
  - **Čas a jazyk**: Zablokuje přístup k oblasti času a jazyka v aplikaci nastavení.
    - **Změny systémového času**: Zabrání koncovému uživateli ve změně data a času.
    - **Změny nastavení oblasti (jenom desktopové verze)**: Zabrání změně nastavení oblasti na zařízení koncového uživatele.
    - **Změny nastavení jazyka (jenom desktopové verze)**: Zabrání uživateli ve změně nastavení jazyka na zařízení.
  - **Hraní her**: Zablokuje přístup k aplikaci hry v nastavení.
  - **Usnadnění přístupu**: Zablokuje přístup k oblasti usnadnění přístupu v aplikaci nastavení.
  - **Ochrana osobních údajů**: Zablokuje přístup k oblasti soukromí v aplikaci nastavení.
  - **Aktualizace a zabezpečení**: Zablokuje přístup k oblasti aktualizací a zabezpečení v aplikaci nastavení.

## <a name="display"></a>Zobrazit

- **Zapnout přizpůsobení rozlišení GDI pro aplikace**
- **Vypnout přizpůsobení rozlišení GDI pro aplikace**

  Rozlišení DPI GDI umožňuje aplikacím, které nejsou rozpoznání nastavení DPI k rozpoznání nastavení DPI podle monitoru. Zadejte starší verze aplikací, které mít rozlišení DPI GDI zapnuté. S DPI škálování GDI nakonfigurovaný tak, aby zapnout a vypnout nastavení v aplikaci je škálování pro aplikaci vypnuté.

## <a name="general"></a>Obecné

- **Snímek obrazovky (jenom mobilní)**: Umožňuje uživateli zachytit obrazovku zařízení v podobě obrázku.
- **Kopírování a vložení (jenom mobilní verze)**: Povolit kopírování a vkládání mezi aplikacemi na zařízení akce.
- **Ruční zrušení zápisu**: Umožňuje uživateli ze zařízení ručně odstranit pracovní účet.
  - Nastavení této zásady neplatí, pokud je počítač připojený k Azure AD a je povolená Automatická registrace. 
  - Nastavení této zásady neplatí pro počítače s Windows 10 Home.
- **Ruční instalace kořenového certifikátu (jenom mobilní verze)**: Zabrání uživateli v ruční instalaci kořenových certifikátů a zprostředkujících certifikátů CAP.

- **Camera**: Povolí nebo zablokuje použití fotoaparátu v zařízení.
- **Synchronizace souboru Onedrivu**: Zablokuje zařízení možnost synchronizovat soubory na OneDrive.
- **Vyměnitelné úložiště**: Určuje, jestli se zařízení můžete použít zařízení externího úložiště, jako jsou SD karty.
- **Informace o zeměpisné poloze**: Určuje, jestli zařízení může používat informace služeb určování polohy.
- **Sdílení Internetu**: Povolí sdílení internetového připojení v zařízení.
- **Obnovení továrního nastavení telefonu**: Určuje, jestli uživatel může vymazání na svém zařízení.
- **Připojení USB (jenom mobilní verze)**: Určuje, jestli má zařízení přístup k zařízením externího úložiště prostřednictvím připojení USB.
- **Režim antiTheft (jenom mobilní verze)**: Umožňuje nakonfigurovat, jestli má být povolený režim Windows Antitheft.
- **Cortana**: Povolí nebo zakáže hlasového asistenta Cortany.
- **Záznam hlasu (jenom mobilní verze)**: Povolí nebo zablokuje použití záznamu hlasu zařízení.
- **Změny názvu zařízení**: Zabrání koncovému uživateli ve změně názvu zařízení (jenom Windows 10 Mobile)
- **Přidávat zřizovací balíčky**: Blokuje agenta konfigurace modulu runtime, který instaluje zřizovací balíčky.
- **Odebírání zřizovacích balíčků**: Blokuje agenta konfigurace modulu runtime, který odebírá zřizovací balíčky.
- **Zjišťování zařízení**: Blokovat zařízení zjišťování jiných zařízení.
- **Přepínání (jenom mobilní verze) úloh**: Zablokuje přepínání úloh na zařízení.
- **Chybový dialog SIM karty (jenom mobilní verze)**: Zablokuje zobrazování na zařízení, pokud se nezjistí žádná SIM karta chybovou zprávu.
- **Pracovní prostor Ink**: Zablokuje uživatelům možnost přístupu k pracovnímu prostoru ink. **Není nakonfigurováno** zapne tento pracovní prostor a uživatel může používat nad zamykací obrazovkou.
- **Automatické opětovné nasazení**: Umožňuje uživatelům s právy správce odstranit všechna uživatelská data a nastavení pomocí **CTRL + Win + R** na zamykací obrazovce zařízení. Zařízení se automaticky překonfiguruje a znovu zaregistruje ke správě.
- **Vyžadovat, aby uživatelé pro připojení k síti během nastavování zařízení (jenom Windows Insider)**: Zvolte **vyžadují** tak připojení zařízení k síti před přetáhli za stránka v síti během instalace Windows 10. Tato funkce je ve verzi preview, sestavení Windows insider 1809 nebo novější je nutné pomocí tohoto nastavení.

  Pokud zařízení nemá připojení k síti během instalace Windows 10, toto nastavení není platné. Nastavení začne platit při příštím zařízení je vymazat nebo resetovat. Tedy nemusí vztahovat na zcela nové zařízení. Stejně jako jakoukoli jinou konfiguraci Intune musí být zařízení zaregistrovaných a spravovaných v Intune pro přijímání nastavení konfigurace. Ale jednou je zaregistrované a přijímá zásady, potom Resetuje zařízení vynucuje nastavení během další nastavení Windows.

- **Přímý přístup do paměti**: **Blok** brání přímý přístup do paměti (DMA) pro všechny aktivní modulární PCI podřízené porty, dokud se uživatel přihlásí do Windows. **Povolené** (výchozí) umožňuje přístup ke DMA, i v případě, že uživatel není přihlášený.

  CSP: [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)

- **Ukončit procesy ve Správci úloh**: Toto nastavení určuje, zda nejsou správci, můžete použít Správce úloh na ukončit úlohy. **Blok** brání použití Správce úloh k ukončení procesu nebo úlohy na zařízení uživatele se standardním oprávněním (bez oprávnění správce). **Není nakonfigurováno** (výchozí) umožňuje standardní uživatelé k ukončení procesu nebo úloh pomocí Správce úloh.

## <a name="locked-screen-experience"></a>Prostředí zamknuté obrazovky

- **Oznámení Centra akcí (jenom mobilní verze)**: Oznámení Centra akcí vám umožňuje zobrazit na zamykací obrazovce zařízení (jenom Windows 10 Mobile).
- **Obrázek adresa URL zamknutou obrazovku (jenom desktopové verze)**: Zadejte adresu URL obrázku ve formátu JPEG, který se použije jako tapeta zamknuté obrazovky Windows. Toto nastavení omezí na obrázku. Obrázek nelze později změnit.
- **Uživatel Konfigurovatelný časový limit obrazovky (jenom mobilní verze)**: Umožňuje uživatelům konfigurovat časový úsek 
- **Cortana na zamknuté obrazovce (jenom desktopové verze)**: Nepovolit uživatelům interakci s Cortanou, když je zařízení na zamykací obrazovce (jenom Windows 10 desktop).
- **Informační zprávu oznámení na uzamčené obrazovce**: Blokovat oznámení z zobrazuje na zamykací obrazovce zařízení.
- **Časový limit (jenom mobilní verze) obrazovky**: Určuje dobu v sekundách, po uzamčení obrazovky, když se vypne.

## <a name="messaging"></a>Zasílání zpráv

- **Synchronizace (jenom mobilní verze) zpráv**: Zakázat zasílání zpráv všude a textové zprávy zálohování a obnovení.
- **MMS (jenom mobilní verze)**: Zakáže funkci přijímání a odesílání zpráv MMS na zařízení.
- **RCS (jenom mobilní verze)**: Zakáže funkci přijímání a odesílání Rich Communication Services na zařízení.

## <a name="microsoft-edge-browser"></a>Prohlížeč Microsoft Edge

### <a name="use-microsoft-edge-kiosk-mode"></a>Režim veřejného terminálu použijte Microsoft Edge

Dostupná nastavení měnit v závislosti na volbách. Možnosti:

- **Ne** (výchozí): Microsoft Edge není spuštěn v režimu veřejného terminálu. Jsou k dispozici můžete změnit a nakonfigurovat všechna nastavení Microsoft Edge.
- **Digitální/Interaktivní značky (aplikace s jedním veřejný terminál)**: Nastavení Microsoft Edge filtry, které se dají použít pro digitální/Interaktivní značky Microsoft Edge celoobrazovkový režim pro použití pouze pro veřejné terminály s Windows 10 jedné aplikace. Toto nastavení chcete otevřít adresy URL zobrazení na celé obrazovce a zobrazit obsah pouze na daném webu. [Nastavit příznaky digitální](https://docs.microsoft.com/windows/configuration/setup-digital-signage) poskytuje další informace o této funkci.
- **Procházení se službou inPrivate veřejné (beznabídkového režimu jedné aplikace)**: Nastavení Microsoft Edge filtry, které se dají použít pro InPrivate veřejné procházení Microsoft Edge celoobrazovkový režim pro použití na veřejné terminály s Windows 10 jedné aplikace. Běží více karet verze Microsoft Edge.
- **Normální režim (veřejný terminál s více aplikacemi)**: Nastavení Microsoft Edge filtry, které se dají použít pro normální Microsoft Edge beznabídkový režim. Spouští se všemi funkcemi procházení plné verze Microsoft Edge.
- **Veřejné procházení (veřejný terminál s více aplikacemi)**: Nastavení Microsoft Edge filtry, které se dají použít pro veřejné procházení na jako veřejný terminál s více aplikacemi Windows 10.  Běží více karet verze InPrivate v Microsoft Edgi.

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
  - **Začít editaci**: Spuštění Microsoft Edge s výchozí úvodní stránku určené operačního systému
  - **Nová stránka karty**: Microsoft Edge načíst cokoli, co je definováno v **adresa URL stránky Nová karta** nastavení
  - **Poslední stránka relace**: Microsoft Edge načte poslední stránka relace 
  - **Vlastní úvodní stránku**: Na úvodní stránce určeného správcem IT načte Microsoft Edge
- **Uživatel může změnit počáteční stránky**: **Povolit** umožňuje uživatelům změnit domovské stránky. Správci můžou použít `EdgeHomepageUrls` přejdete stránky, které se uživatelům zobrazí ve výchozím nastavení při otevření Microsoft Edge. **Není nakonfigurováno** zablokuje uživatelům možnost měnit úvodních stránek.
- **Nová adresa URL stránky karty**: Zadejte adresu URL otevřít na nové záložce. Zadejte například `https://www.bing.com`.
- **Otevírání webového obsahu na stránce Nová karta**: Zvolte **bloku** zastavit Microsoft Edge otevírání webu na nové záložce. V případě blokování se nová karta otevřete prázdnou. **Není nakonfigurováno** použije výchozí chování operačního systému v zařízení, což může umožnit uživatelům si vybrat, jak je zobrazeno.
- **Tlačítko Domů**: Zvolte, co se stane, pokud je zaškrtnuto tlačítko Domů. Možnosti:
  - **Začít editaci**: Možnost jste vybrali **spuštění Microsoft Edge s** nastavení otevře
  - **Nová stránka karty**: Možnost jste vybrali **adresa URL stránky Nová karta** nastavení otevře
  - **Adresa URL vlastní domovské tlačítko**: Možnost jste vybrali **domácí adresa URL tlačítka** nastavení otevře
  - **Tlačítko Domů skrýt**: Skryje tlačítko Domů
- **Uživatel může změnit tlačítko Domů**: **Povolit** umožňuje uživatelům změnit domovské tlačítko. Změny uživatele přepsání jakéhokoli nastavení správce na tlačítko Domů. **Není nakonfigurováno** použije výchozí chování operačního systému v zařízení, který může zablokovat uživatelům možnost měnit, jak správce nakonfiguroval tlačítko Domů.
- **Zobrazit stránku prvního spuštění**: **Blok** zastaví úvodní stránky zobrazují první čas spuštění Microsoft Edge. Tato funkce umožňuje podnikům, třeba ty organizace registrovaná v konfiguracích s nulovými emisemi, zablokovat tuto stránku. **Není nakonfigurováno** ukazuje úvodní stránka.
  - **Prostředí URL při prvním spuštění**: Zadejte adresu URL stránky zobrazíte uživatele při prvním spuštění Microsoft Edge (jenom Windows 10 Mobile).
- **Aktualizujte prohlížeč po nečinnosti**: Zadejte počet nečinných počet minut, než se aktualizují v prohlížeči z 0 – 1 440 minut. Výchozí hodnota je `5` minut. Pokud je nastavena na `0` (nula) v prohlížeči neobnoví po nečinnosti.

  Toto nastavení je k dispozici pouze při spuštění v [procházení InPrivate veřejné (veřejný terminál s jednou aplikací)](#use-microsoft-edge-kiosk-mode).

  CSP: [ConfigureKioskResetAfterIdleTimeout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskresetafteridletimeout)

- **Automaticky otevíraná okna**: Zvolte **bloku** zastavení automaticky otevíraná okna v prohlížeči. Platí jen pro Windows 10 Desktop. **Není nakonfigurováno** umožňuje automaticky otevíraných oken ve webovém prohlížeči.
- **Odesílat intranetové přenosy do Internet Exploreru**: **Povolit** umožňuje uživatelům otevírat intranetové weby v Internet Exploreru, ne Microsoft Edge (jenom Windows 10 desktop). **Není nakonfigurováno** umožňuje uživatelům používat Microsoft Edge.
- **Umístění seznamu webů využívajících režim rozlehlé sítě**: Zadejte adresu URL, která obsahuje seznam webů, které se otevřou v podnikovém režimu. Uživatelé nemohou změnit tohoto seznamu. Platí jen pro Windows 10 Desktop.
- **Zpráva při otevírání webů v Internet Exploreru**: Pomocí tohoto nastavení můžete nakonfigurovat Microsoft Edge zobrazíte oznámení před otevřením webu v aplikaci Internet Explorer 11. Možnosti:
  - **Není nakonfigurováno**: Výchozí chování operačního systému se používá, které se nemusí zobrazit zprávu.
  - **Zobrazit zprávu bez možnosti otevřít servery v Microsoft Edge**: Zobrazit zprávu při otevírání webů v Internet Exploreru. Weby se otevřou v Internet Exploreru. Není k dispozici možnost otevření weby ve Microsoft Edge.
  - **Zobrazit zprávu při otevírání webů v Microsoft Edge**: Zobrazit zprávu při otevírání webů v Internet Exploreru. Zpráva obsahuje **dál pokračovat v Microsoft Edge** odkaz, takže uživatelé mohou Microsoft Edge místo Internet Exploreru.

  > [!IMPORTANT]
  > Toto nastavení vyžaduje, abyste zapnuli **konfigurovat seznam webů podnikového režimu** nastavení, **odeslat všechny weby v intranetu na Internet Explorer 11** nastavení, nebo obě nastavení.

- **Seznam kompatibility Microsoftu**: **Blok** brání seznam kompatibility Microsoftu v Microsoft Edge. Tento seznam od Microsoftu pomáhá Microsoft Edge správně zobrazovat stránky, které se známými problémy s kompatibilitou. **Není nakonfigurováno** umožňuje používat seznam kompatibility Microsoftu.
- **Předběžné načtení úvodní stránky a stránky nové karty**: Zvolte **bloku** aby Microsoft Edge od předběžného načítání úvodních stránek a nové záložce. Předběžné načítání minimalizuje dobu spuštění Microsoft Edge a načtení na nové kartě. **Není nakonfigurováno** použije výchozí chování operačního systému, který může být přednačtení tyto stránky.
- **Předběžné spuštění úvodní stránky a stránky nové karty**: Zvolte **bloku** zabránit před spuštěním úvodních stránek a nové záložce Microsoft Edge. Před spuštěním pomáhá výkonu Microsoft Edge a minimalizuje dobu potřebnou ke spuštění Microsoft Edge. **Není nakonfigurováno** použije výchozí chování operačního systému, který může být na předběžné spuštění těchto stránek.

### <a name="favorites-and-search"></a>Oblíbené a vyhledávání

- **Panel Oblíbené**: Zvolte, co se stane, že k oblíbeným položkám na libovolné stránce Microsoft Edge. Možnosti:
  - **Není nakonfigurováno**: Použije výchozí chování operačního systému, který může být skrýt panel Oblíbené položky na všech stránkách. Uživatel může změnit toto nastavení.
  - **Skrýt**: Skryje panel Oblíbené položky na všech stránkách. Uživatel nemůže změnit toto nastavení.
  - **Zobrazit**: Zobrazí panel Oblíbené položky na všech stránkách. Uživatel nemůže změnit toto nastavení.
- **Seznam oblíbených položek**: Přidáte seznam adres URL k souboru oblíbených položek. Například přidejte `http://contoso.com/favorites.html`.
- **Omezit změny oblíbených položek**: **Blok** zabránit uživatelům přidávat, import, řazení nebo úpravy seznamu oblíbených položek. **Není nakonfigurováno** používá výchozí operační systém, což může povolit uživatelům změnit seznam.
- **Synchronizovat Oblíbené položky mezi prohlížeči Microsoft (jenom desktopové verze)**: **Vyžadovat** vynutí Windows synchronizovat Oblíbené položky mezi Internet Explorerem a Microsoft Edgem. Přidání, odstranění, změny a změny pořadí mezi oblíbené položky jsou sdíleny mezi prohlížeči.  **Není nakonfigurováno** používá výchozí operační systém, což může uživatelům možnost k synchronizaci oblíbených položek mezi prohlížečů.
- **Výchozí vyhledávací web**: Zvolte výchozí vyhledávací web na zařízení. Koncoví uživatelé mohou tuto hodnotu kdykoli změnit. Možnosti:
  - Výchozí
  - Bing
  - Google
  - Yahoo
  - Vlastní hodnota
- **Návrhy hledání**: **Není nakonfigurováno** umožňuje vyhledávací navrhoval weby web při psaní vyhledávání v panelu Adresa. **Blok** brání tuto funkci.
- **Povolit změny v modulu vyhledávání**: **Ano** (výchozí) umožňuje uživatelům přidání nového vyhledávací weby nebo změnit výchozí vyhledávací web v Microsoft Edge. Zvolte **ne** uživatelům zabránit v přizpůsobení vyhledávací web.

  Toto nastavení je k dispozici pouze při spuštění v [normálního režimu (veřejný terminál s více aplikacemi)](#use-microsoft-edge-kiosk-mode).

  CSP: [AllowSearchEngineCustomization](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsearchenginecustomization)

### <a name="privacy-and-security"></a>Ochrana osobních údajů a zabezpečení

- **Procházení inPrivate**: **Blok** zabrání koncovým uživatelům v otevírání relací procházení InPrivate. **Není nakonfigurováno** této funkce.
- **Uložit historie procházení**: **Blok** zabrání v uložení historie procházení Microsoft Edge. **Není nakonfigurováno** povolení ukládání historie procházení.
- **Vymazat údaje o ukončení (jenom desktopové verze) procházení**: **Vyžadovat** vymaže historii a údaje o procházení při ukončení Microsoft Edge uživatelem. **Není nakonfigurováno** používá výchozí operační systém, což může procházení dat do mezipaměti.
- **Synchronizovat nastavení prohlížeče mezi zařízeními uživatelů**: Zvolte, jak chcete synchronizovat nastavení prohlížeče mezi zařízeními. Možnosti:
  - **Povolit**: Povolit synchronizaci nastavení prohlížeče Microsoft Edge mezi zařízeními uživatelů
  - **Blokovat a povolit přepsání uživatele**: Blokovat synchronizaci nastavení prohlížeče Microsoft Edge mezi zařízení uživatele. Toto nastavení můžou uživatelé potlačit.
  - **Blok**: Blokovat synchronizaci nastavení prohlížeče Microsoft Edge mezi zařízení uživatele. Toto nastavení nelze přepsat uživatelé.
- **Správce hesel**: **Blok** zakáže funkci správce hesel Microsoft Edge. **Není nakonfigurováno** této funkce.
- **Soubory cookie**: Zvolte, jak se zpracovává soubory cookie ve webovém prohlížeči. Možnosti:
  - **Povolit**: Soubory cookie se ukládají na zařízení.
  - **Blokovat všechny soubory cookie**: Soubory cookie se ukládají na zařízení.
  - **Blokovat jenom soubory cookie třetích stran**: Třetích stran nebo partnera souborů cookie nejsou uloženy v zařízení.
- **Automatické vyplňování**: **Blok** zakáže automatické vyplňování funkci na zařízení. **Není nakonfigurováno** umožňuje uživatelům změnit nastavení automatického dokončování v prohlížeči (jenom Windows 10 desktop).
- **Odesílat hlavičky not track**: **Není nakonfigurováno** vyžaduje, aby zařízení odesílat hlavičky not track na weby, které požadují trasovací informace (doporučeno). Zvolte **bloku** zabránit odesílání těchto hlaviček, což umožní webům sledovat uživatele zařízení.
- **IP adresa localhost pro WebRtc**: **Blok** brání IP adresy localhost uživatele při telefonování pomocí protokolu WEBRTC zobrazením. **Není nakonfigurováno** umožňuje uživatelům IP adresa localhost, které budou zobrazeny při telefonování pomocí tohoto protokolu.
- **Dlaždice shromažďování dat pro živé**: Zvolte **bloku** zastavit Windows shromažďování informací o lokalitě je připnutá. živé dlaždice do nabídky start z Microsoft Edge. **Není nakonfigurováno** umožňuje tyto informace, které se mají shromažďovat.
- **Uživatel může přepsat chyby certifikátů**: **Blok** zabraňuje uživatelům v přístupu k webům, které obsahují chyby SSL nebo TLS. **Není nakonfigurováno** umožňuje uživatelům přístup k těmto serverům.

### <a name="additional"></a>Další

- **Prohlížeč Microsoft Edge (jenom mobilní verze)**: Zvolte **bloku** k zabránění použití Microsoft Edge na zařízení. Pokud zablokujete Microsoft Edge, individuální nastavení platí jenom pro desktop. **Není nakonfigurováno** umožňuje pomocí webového prohlížeče Microsoft Edge na zařízení.
- **(Jenom desktopové verze) Rozevírání panelu Adresa**: **Blok** zastaví zobrazování seznamu návrhů v rozevíracím seznamu při psaní Microsoft Edge. Tato možnost se může minimalizovat šířku pásma sítě mezi Microsoft Edge a služby Microsoftu. **Není nakonfigurováno** umožňuje Microsoft Edge zobrazí seznam návrhů.
- **Zobrazení na celé obrazovce**: Zvolte **bloku** aby Microsoft Edge z pouze zobrazení webového obsahu a skrytí Microsoft Edge (režim celé obrazovky). **Není nakonfigurováno** používá výchozí operační systém, což umožňuje Microsoft Edge použít režim celé obrazovky.
- **Příznaky**: **Blok** zabrání koncovým uživatelům v přístupu k `about:flags` stránky v Microsoft Edge, která obsahuje vývojářské a experimentální nastavení. **Není nakonfigurováno** používá výchozí operační systém, což může umožnit přístup k `about:flags` stránky.
- **Nástroje pro vývojáře**: **Blok** koncovým uživatelům zabrání v otevření vývojářských nástrojů Microsoft Edge. **Není nakonfigurováno** umožňuje uživatelům otevírat nástroje pro vývojáře.
- **Rozšíření**: **Není nakonfigurováno** umožňuje koncovým uživatelům pro instalaci rozšíření Microsoft Edge na zařízení. **Blok** zabrání instalaci.
- **Rozšíření pro zkušební načtení před prodejem vývojáře**: **Blok** brání pro zkušební načtení, což nainstaluje a spustí neověřený pomocí rozšíření Microsoft Edge **načíst rozšíření** funkce. **Není nakonfigurováno** používá výchozí operační systém, což může povolit zkušební načtení před prodejem.
- **Vyžaduje rozšíření**: Vyberte, jaká rozšíření, nejde ji vypnout koncovým uživatelům v Microsoft Edge. Zadejte název řady balíčku a vyberte **přidat**. [Najít název řady balíčku (PFN)](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) zobrazí pokyny.

  Můžete také **Import** soubor CSV, který obsahuje název řady balíčku.

- **JavaScript**: Zvolte **bloku** zabránit skriptů Java v prohlížeči spuštěného v příslušném zařízení. **Není nakonfigurováno** umožňuje skripty, třeba Javascript pro spuštění v prohlížeči Microsoft Edge.

## <a name="network-proxy"></a>Síťový proxy server

- **Automaticky zjišťovat nastavení proxy serveru**: Když povolené, zařízení se pokusí najít cestu ke skriptu PAC.
- **Použít skript proxy serveru**: Vyberte tuto možnost, zadejte cestu ke skriptům PAC a nakonfigurovat proxy server.
  - **Nastavení adresy URL skriptu**: Zadejte adresu URL skriptu PAC, který chcete použít ke konfiguraci proxy serveru.
- **Použít ruční proxy server**: Výběrem této možnosti ručně zadat informace o proxy serveru.
  - **Adresa**: Zadejte název nebo IP adresu proxy serveru.
  - **Číslo portu**: Zadejte číslo portu proxy serveru.
  - **Výjimky proxy serveru**: Zadejte všechny adresy URL, které nesmí používat proxy server. Jednotlivé položky oddělte středníkem.
  - **Obejít proxy server pro místní adresy**: Tuto možnost povolte, pokud nechcete používat proxy server pro místní adresy na vašem intranetu.

## <a name="password"></a>Heslo

- **Heslo**: Vyžaduje, aby koncový uživatel zadal heslo pro přístup k zařízení.
  - **Vyžadovaný typ hesla**: Určuje, zda heslo musí být číselná hodnota pouze nebo alfanumerické znaky.
  - **Minimální délka hesla**: Platí jen pro Windows 10 Mobile.
  - **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: Pro zařízení s Windows 10: Pokud má zařízení povolený nástroj BitLocker, přejde do režimu obnovení nástroje BitLocker po přihlášení se nepovede určený počet případů, kdy jste zadali. Pokud zařízení není povolený nástroj BitLocker, toto nastavení neplatí. Pro zařízení s Windows 10 Mobile: Po přihlášení nepovede určený počet pokusů, které zadáte, bude zařízení vymazáno.
  - **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**: Určuje dobu, kterou musí být zařízení v nečinnosti, než se uzamkne jeho obrazovka.
  - **Vypršení platnosti hesla (dny)**: Toto nastavení určuje dobu, po jejímž uplynutí je třeba změnit heslo k zařízení.
  - **Zakázat opakované použití předchozích hesel**: Určuje počet dříve použitých hesel, která se na zařízení zapamatovávají.
  - **Vyžadovat heslo při návratu zařízení ze stavu nečinnosti (jenom mobilní verze)**: Určuje, že uživatel musí zadat heslo k odemknutí zařízení (jenom Windows 10 Mobile).
  - **Jednoduchá hesla**: Umožňuje povolit použití jednoduchých hesel, jako jsou 1111 nebo 1234. Toto nastavení také povolí obrázková hesla Windows (nebo je zablokuje).

## <a name="per-app-privacy-exceptions"></a>Výjimky ze zásad ochrany osobních údajů pro jednotlivé aplikace

Můžete přidat aplikace, které by měly mít jiné chování ochrany osobních údajů než to, které jste definovali ve výchozích zásadách.

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

## <a name="personalization"></a>Personalizace

- **Adresa URL obrázku na pozadí plochy (jenom desktopové verze)**: Zadejte adresu URL obrázku ve formátu JPEG, který chcete použít jako tapeta na ploše Windows. Uživatelé nemohou tento obrázek změnit.

## <a name="printer"></a>Tiskárny

- **Tiskárny**: Seznam místních tiskáren, které byly přidány.
- **Výchozí tiskárna**: Nastaví výchozí tiskárnu.
- **Přístup uživatelů k přidávání nových tiskáren**: Povolí nebo zablokuje používání místních tiskáren.

## <a name="privacy"></a>Ochrana osobních údajů

- **Přizpůsobení vstupu**: Nepovolit použití cloudových hlasových služeb pro Cortanu, diktování nebo Microsoft Store aplikace. Pokud tyto služby povolíte, může Microsoft kvůli vylepšení služby shromažďovat hlasová data.
- **Automatické přijetí párování a ochrana osobních údajů pokynů souhlasu uživatele**: Povolte Windows k automatické přijetí párování a ochrana osobních údajů souhlas zpráv při spuštění aplikace.
- **Publikovat aktivity uživatele**: **Blok** zabraňuje sdílení a zjišťování naposledy použitých prostředků v přepínání úloh.
- **Jen místní aktivity**: **Blok** zabraňuje sdílení a zjišťování naposledy použitých prostředků při přepínání úloh jen na základě místní aktivity.

Můžete nakonfigurovat informace, které můžete přístup všechny aplikace na zařízení. Navíc definovat výjimky na základě aplikaci pomocí **výjimky ochrany osobních údajů pro jednotlivé aplikace**.

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

## <a name="projection"></a>Promítání

- **Uživatelský vstup z přijímačů bezdrátového zobrazení**: Bloky uživatelský vstup z přijímačů bezdrátového zobrazení.
- **Promítání na tento počítač**: Zabrání ostatním zařízením hledání počítač pro promítání.
- **Párování požadovat PIN kód**: Při připojení k promítacímu zařízení požadovat kód PIN.

## <a name="reporting-and-telemetry"></a>Generování sestav a telemetrie

- **Sdílet data o využití**: Vyberte úroveň diagnostických dat, které je odeslána. Možnosti:
  - Zabezpečení
  - Basic
  - Rozšířené
  - Full
- **Odeslat Microsoft Edge procházení dat pro Microsoft 365 Analytics**: Chcete-li tuto funkci používat, nastavte **sdílet data o využití** nastavení **rozšířená** nebo **úplné**. Tato funkce řídí, jaká data Microsoft Edge odesílá do Microsoftu 365 Analytics u podnikových zařízení nakonfigurované komerční ID. Možnosti:
  - **Není nakonfigurováno**: Používá výchozí operační systém, který nemůže posílat žádné procházení historie
  - **Odesílala jen data intranetu**: Umožňuje správci posílat intranetový data historie
  - **Odesílala jen internet data**: Umožňuje správci posílat data historie internet
  - **Odesílat intranetové a internetové data**: Umožňuje správci posílat data historie intranetu a Internetu
- **Proxy server pro telemetrii**: Zadejte plně kvalifikovaný název domény (FQDN) nebo IP adresu proxy serveru pro předávání propojených uživatelských prostředí a Telemetrie požadavky, pomocí připojení vrstvy SSL (Secure Sockets). Formát pro toto nastavení je *server*:*port*. Pokud uvedený proxy server selže nebo pokud není zadán proxy server, při povolování těchto zásad, data propojených uživatelských prostředí a Telemetrie se neposílají a zůstane na místním zařízení.

  Příklady formátů:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

## <a name="search"></a>Search

- **Bezpečné vyhledávání (jenom mobilní verze)**: Řídí, jak Cortana filtruje obsah pro dospělé ve výsledcích hledání. Můžete vybrat možnost **Striktní**, **Pokročilé** nebo povolit koncovým uživatelům, aby si zvolili vlastní nastavení.
- **Zobrazovat webové výsledky ve vyhledávání**: Blokování nebo povolení webových výsledků hledání na zařízení.

## <a name="start"></a>Spustit

- **Rozložení nabídky Start**: Přizpůsobení nabídky start na desktopových zařízeních, můžete nahrát soubor XML, který obsahuje vaše vlastní nastavení, včetně pořadí, ve kterém jsou uvedené aplikace a další. Uživatelé nemohou měnit rozložení nabídky Start, které zadáte.
- **Připnout weby na dlaždice do nabídky Start**: Importovat Image z Microsoft Edge, které se zobrazují jako odkazy v nabídce Windows Start pro desktopové zařízení.
- **Odepínání aplikací z hlavního panelu**: Zvolte **bloku** zastavit uživateli v odepínání aplikací z hlavního panelu.
- **Rychlé přepínání uživatelů**: Zvolte **bloku** zabránit přepínání mezi uživatele, kteří jsou přihlášení současně bez odhlašování.
- **Nejpoužívanější aplikace**: Zvolte **bloku** skrýt nejpoužívanější aplikace v seznamu zobrazuje v nabídce start. Zároveň se zakáže odpovídající přepínač v aplikaci Nastavení.
- **Naposledy přidané aplikace**: Zvolte **bloku** skrýt naposledy přidané aplikace zobrazuje v nabídce start. Zároveň se zakáže odpovídající přepínač v aplikaci Nastavení.
- **Režim úvodní obrazovky**: Zvolte, jak je znázorněno na obrazovce start. Můžete zvolit možnosti **Celá obrazovka** nebo **V okně**.
- **Naposledy otevřené položky v seznamech odkazů**: Zvolte **bloku** skrýt poslední seznamy odkazů ze zobrazených v nabídce start a na hlavním panelu. Zároveň se zakáže odpovídající přepínač v aplikaci Nastavení.
- **Seznam aplikací**: Zvolte, jak je znázorněno v aplikaci nastavení. Možnosti: 
  - Sbalit
  - Sbalit a zakázat aplikaci Nastavení 
  - Odebere a zakáže aplikaci Nastavení.
- **Tlačítko napájení**: Zvolte **bloku** skrýt tlačítko napájení v nabídce start zobrazuje.
- **Dlaždici uživatele**: Zvolte **bloku** skrýt dlaždici uživatele ze zobrazení v nabídce start.
  - **Zámek**: Zvolte **bloku** skrýt `Lock` možnost ukazující na dlaždici uživatele v nabídce start.
  - **Odhlásit se**: Zvolte **bloku** skrýt `Sign out` možnost ukazující na dlaždici uživatele v nabídce start.
- **Vypnout**: Zvolte **bloku** skrýt `Update and shut down` a `Shut down` možnosti ze zobrazení na tlačítku napájení v nabídce start.
- **Přejít do režimu spánku**: Zvolte **bloku** skrýt `Sleep` možnost ukazující na tlačítku napájení v nabídce start.
- **Do režimu hibernace**: Zvolte **bloku** skrýt `Hibernate` možnost ukazující na tlačítku napájení v nabídce start.
- **Přepnout účet**: Zvolte **bloku** skrýt `Switch account` ze zobrazení uživatele dlaždice do nabídky start.
- **Možnosti restartování**:  Zvolte **bloku** skrýt `Update and restart` a `Restart` možnosti ze zobrazení na tlačítku napájení v nabídce start.
- **Dokumenty v nabídce Start**: Skrýt nebo zobrazit složku Dokumenty v nabídce Windows Start.
- **Soubory ke stažení v nabídce Start**: Skrýt nebo zobrazit složku stažené soubory v nabídce Windows Start.
- **Průzkumník souborů v nabídce Start**: Skrýt nebo zobrazit aplikaci Průzkumník souborů v nabídce Windows Start.
- **Domácí skupina v nabídce Start**: Skrýt nebo zobrazit složku domácí skupina v nabídce Windows Start.
- **Hudba v nabídce Start**: Skrýt nebo zobrazit složku Hudba v nabídce Windows Start.
- **Síť v nabídce Start**: Skrýt nebo zobrazit složku Síť v nabídce Windows Start.
- **Složka Osobní v nabídce Start**: Skrýt nebo zobrazit složku Osobní v nabídce Windows Start.
- **Obrázky v nabídce Start**: Skrýt nebo zobrazit složku s obrázky v nabídce Windows Start.
- **Nastavení v nabídce Start**: Skrýt nebo zobrazit aplikaci nastavení v nabídce Windows Start.
- **Videa v nabídce Start**: Skrýt nebo zobrazit složku s videi v nabídce Windows Start.

## <a name="windows-defender-smart-screen"></a>Filtr SmartScreen v programu Windows Defender

- **Filtr SmartScreen pro Microsoft Edge**: Povolte filtr SmartScreen Microsoft Edge pro přístup k webu a stahování souborů.
- **Přístup na škodlivý web**: Zablokuje uživatelům možnost Ignorovat upozornění filtru Windows Defender SmartScreen a znemožní jim přejít na daný web.
- **Stahování neověřených souborů**: Zablokuje uživatelům možnost Ignorovat upozornění filtru Windows Defender SmartScreen a znemožní jim stahovat neověřené soubory.

## <a name="windows-spotlight"></a>Windows Spotlight

- **Windows Spotlight**: Toto nastavení použijte k zablokování všech funkcí Windows Spotlight na zařízeních s Windows 10. Pokud toto nastavení zablokujete, nejsou k dispozici následující nastavení:
  - **Windows Spotlight na zamykací obrazovce**: Windows Spotlight zastaví zobrazování informací na zamykací obrazovce zařízení.
  - **Návrhy třetích stran ve Windows Spotlightu**: Zakázat Windows Spotlightu návrhy obsahu, který nebyl vydán microsoftem.
  - **Uživatelské funkce**: Spustit umožňuje zablokovat uživatelské funkce, jako jsou návrhy nabídky a oznámení o členství.
  - **Tipy Windows**: Umožňuje zablokovat zobrazování v Windows automaticky otevíraných tipů.
  - **Windows Spotlight v Centru akcí**: Nová aplikace nebo obsah v Centru akcí Windows týkající se zabezpečení, jako jsou návrhy blokovat Windows Spotlight.
  - **Přizpůsobení Windows Spotlightu**: Zastaví Windows Spotlightu přizpůsobování výsledků na základě využití zařízení.
  - **Prostředí uvítání Windows**: Zablokuje prostředí uvítání Windows, které uživateli zobrazuje informace o nových nebo aktualizovaných funkcích.

## <a name="windows-defender-antivirus"></a>Antivirová ochrana v programu Windows Defender

- **Monitorování v reálném čase**: Umožňuje v reálném čase zjišťovat v počítači existenci malwaru, spywaru a dalšího nežádoucího softwaru.
- **Monitorování chování**: Umožňuje programu Defender zjišťovat výskyt určitých známých vzorců podezřelých aktivit na zařízeních.
- **Systém kontroly (NIS) sítě**: Systém NIS pomáhá chránit zařízení před zneužitím sítě. Používá signatury známých slabých míst z Centra Microsoftu pro ochranu koncových bodů ke zjištění a blokování škodlivého síťového provozu.
- **Kontrolovat všechna stahování**: Určuje, jestli bude Defender kontrolovat všechny soubory stahované z internetu.
- **Kontrolovat skripty načtené do webových prohlížečů Microsoftu**: Umožňuje programu Defender kontrolovat skripty, které se používají v Internet Exploreru.
- **Přístup koncového uživatele k Defenderu**: Určuje, jestli se bude koncovým uživatelům zobrazovat uživatelské rozhraní Windows Defenderu. Když toto nastavení změníte, projeví se změna až při příštím restartování počítače koncovým uživatelem.
- **Interval aktualizace podpisu (v hodinách)**: Zadejte interval, ve kterém bude Defender zkontroluje dostupnost nových souborů signatur.
- **Monitorovat aktivitu souborů a programů**: Umožňuje Defenderu monitorování aktivity souborů a programů v zařízení.
- **Počet dní před odstraněním malwaru v karanténě**: Dál sledovat vyřešené problémy s malwarem pro počet dní, které zadáte, abyste mohli ručně zkontrolovat dříve zasažená zařízení. Pokud nastavíte počet dnů **0**, malware zůstane ve složce karantény a automaticky se neodebere.
- **Limit využití procesoru při kontrole**: Maximální procento využití procesoru, které můžou používat, kontroly z **1** k **100**.
- **Prohledat archivní soubory**: Umožňuje programu Defender zkontrolovat soubory archivu, jako jsou soubory Zip nebo Cab.
- **Kontrolovat příchozí e-mailové zprávy**: Umožňuje programu Defender kontrolovat e-mailové zprávy při jejich doručování na zařízení.
- **Během úplné kontroly kontrolovat vyměnitelné jednotky**: Umožňuje programu Defender kontrolovat vyměnitelné jednotky, jako jsou USB flash disky.
- **Kontrolovat namapované síťové jednotky během úplného prohledávání**: Umožňuje Defenderu kontrolovat soubory na namapované síťové jednotce.
  Pokud jsou soubory na disku jen pro čtení, nelze Defender odebrat žádný malware, který v nich najde.
- **Kontrolovat soubory otevřené ze síťových složek**: Umožňuje Defenderu zkontrolovat soubory na sdílených síťových jednotkách (například soubory se přistupuje pomocí cesty UNC). Pokud jsou soubory na disku jen pro čtení, nelze Defender odebrat žádný malware, který v nich najde.
- **Cloudová ochrana**: Umožňuje službě Microsoft Active Protection Service povolit nebo blokovat příjem informací o činnosti malwaru ze zařízení, která spravujete. Tyto informace služby zvyšuje v budoucnosti.
- **Dotázat se uživatele před odesláním vzorku**: Ovládací prvky, zda potenciálně škodlivých souborů, které by mohly vyžadovat další analýzu jsou automaticky odeslány společnosti Microsoft.
- **Čas k provedení každodenní rychlou kontrolu**: Vyberte hodinu spustit denní rychlé prohledávání. **Není nakonfigurováno** každodenní kontrolu se nespustí. Pokud chcete větší míru přizpůsobení, konfigurace **typ systémové kontroly provádět** nastavení.

  [Defender/ScheduleQuickScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime)
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
  - Spustit denní rychlé prohledávání a úplnou kontrolu každý týden, nakonfigurujte **času provádění každodenní rychlou kontrolu**a nastavte **typ systémové kontroly provádět** na úplné prohledávání se datum a čas.
  - Nekonfigurujte **času provádění každodenní rychlou kontrolu** nastavení současně s **typ systémové kontroly provádět** nastavena na **Rychlá kontrola**. Tato nastavení dojít ke konfliktu a kontroly se možná nespustí.
  - Chcete-li spustit rychlé prověřování každé úterý v 6: 00, nakonfigurovat **typ systémové kontroly provádět** nastavení.

  [Defender/ScanParameter CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter)  
  [Defender/ScheduleScanDay CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday)  
  [Defender/ScheduleScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime)

- **Zjišťovat potenciálně nežádoucí aplikace**: Zvolte stupeň ochrany pokud Windows zjistí potenciálně nežádoucí aplikace od:
  - **Blokováno**
  - **Audit** Další informace o potenciálně nežádoucích aplikacích najdete v tématu [detekovat a blokovat potenciálně nežádoucí aplikace](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
- **Akce ohledně zjištěných malwarových hrozeb**: Vyberte akce, které má Defender provést na jednotlivých úrovních hrozeb detekuje: s nízkou, střední, vysoká a závažnost. Možnosti:
  - **Vyčistit**
  - **Karanténa**
  - **Odebrat**
  - **Povoleno**
  - **Definováno uživatelem**
  - **Blokováno**

### <a name="windows-defender-antivirus-exclusions"></a>Výjimky antivirové ochrany v programu Windows Defender

- **Soubory a složky, které chcete vyloučit z kontrol a ochrany v reálném čase**: Umožňuje do seznamu vyloučení přidat soubory a složky, například **C:\Cesta** nebo **%ProgramFiles%\Cesta\název_souboru.exe**. Tyto soubory a složky nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.
- **Vyloučit z kontrol a ochrany v reálném čase přípony souborů**: Umožňuje do seznamu vyloučení přidat přípony souborů, například **jpg** nebo **txt**. Soubory s těmito příponami nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.
- **Procesy, které chcete vyloučit z kontrol a ochrany v reálném čase**: Umožňuje do seznamu vyloučení přidat procesy typu **.exe**, **.com** nebo **.scr**. Tyto procesy nejsou zahrnuté do kontrol probíhajících v reálném čase ani do plánovaných kontrol.

## <a name="next-steps"></a>Další postup

Další technické podrobnosti o jednotlivých nastaveních a podporovaných edicích Windows najdete v [referenčních informacích o poskytovateli konfiguračních služeb pro zásady (CSP) pro Windows 10](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).
