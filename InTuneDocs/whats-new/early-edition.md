---
title: "Časná edice | Dokumentace Microsoftu"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 5f172290d493717308446c4f9e2313a03ba8f3aa
ms.openlocfilehash: d7f25657fc7cfb9298809f76f198810718e58c39
ms.lasthandoff: 04/27/2017


---


# <a name="the-early-edition-for-microsoft-intune---april-2017"></a>Časná edice Microsoft Intune – duben 2017

**Časná edice** poskytuje seznam funkcí, které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány na základě smlouvy o utajení (NDA) ve velmi omezené míře a mohou podléhat změnám. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a mohou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moci zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se prosím na příslušný kontakt (Intune/PM).

Tato stránka se pravidelně aktualizuje. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.

> [!Note]
> Následující změny v Intune jsou ve vývoji. Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nové funkce

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Vylepšený stav instalace aplikace pro aplikaci Portál společnosti ve Windows 10 <!--676495-->

Aplikace Portál společnosti ve Windows 10 teď poskytne indikátor průběhu instalace aplikace pro všechny instalace moderních aplikací spuštěné z Portálu společnosti. Nové stavové zprávy pro aplikaci Portál společnosti pro Windows 10 uvidíte na [stránce s novinkami v uživatelském rozhraní aplikace Intune](whats-new-in-intune-app-ui.md).

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Vylepšené zprávy o stavu v aplikaci Portál společnosti pro iOS<!--744866-->

V aplikaci Portál společnosti pro iOS se teď budou zobrazovat nové a konkrétnější chybové zprávy poskytující přístupnější informace o tom, co se děje na zařízeních. Tyto případy chyb byly dříve součástí obecné chybové zprávy s názvem „Portál společnosti dočasně nedostupný“. Kromě toho, pokud uživatel aplikaci Portál společnosti spustí v iOSu, když chybí připojení k internetu, uvidí teď na domovské stránce trvalý stavový řádek s oznámením o tom, že chybí připojení k internetu.

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps k dispozici pro Managed Browser <!--822308, 822303-->

Microsoft MyApps teď mají lepší podporu v Managed Browseru. Uživatelé Managed Browseru, kteří nejsou cílem správy, budou přeneseni rovnou do služby MyApps, kde mají přístup k aplikacím SaaS, které jim zajistil správce. Uživatelé, kteří jsou cílem správy Intune, budou mít k MyApps dál přístup z integrované záložky Managed Browseru.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Nové ikony pro Managed Browser a Portál společnosti<!--918433, 918431-->

Managed Browser dostal aktualizované ikony pro verze aplikace pro Android i iOS. Nová ikona bude obsahovat aktualizovaný odznak Intune, aby byla konzistentnější s ostatními aplikacemi v Enterprise Mobility + Security (EM+S). Novou ikonu pro Managed Browser uvidíte na [stránce s novinkami v uživatelském rozhraní aplikace Intune](whats-new-in-intune-app-ui.md).

Portál společnosti také dostal aktualizované ikony pro verze aplikace pro Android, iOS i Windows, aby byly konzistentnější s ostatními aplikacemi v EM+S. Tyto ikony se budou postupně vydávat pro všechny platformy od dubna do konce května.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Podpora jednotného přihlášení z Portálu společnosti pro iOS do Outlooku pro iOS <!--834012-->

Uživatelé už se nemusí přihlašovat k aplikaci Outlook, pokud jsou na stejném zařízení pomocí stejného účtu přihlášení k aplikaci Portál společnosti pro iOS. Při spuštění aplikace Outlook budou uživatelé moct zvolit svůj účet a přihlásit se automaticky. Pracujeme také na tom, abychom tuto funkci přidali i pro další aplikace Microsoftu.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Ukazatel průběhu přihlášení v Portálu společnosti pro Android <!--953374-->

Aktualizace aplikace Portál společnosti pro Android zobrazuje indikátor průběhu přihlášení, když uživatel aplikaci spustí nebo pokračuje v jejím používání. Než uživatel získá přístup k aplikaci, indikátor postupně zobrazuje nové stavy od „Připojování...“ přes „Přihlašování...“ po „Kontrolují se požadavky na zabezpečení...“. Nové obrazovky pro aplikaci Portál společnosti pro Android uvidíte na [stránce s novinkami v uživatelském rozhraní aplikace Intune](whats-new-in-intune-app-ui.md).


## <a name="notices"></a>Sdělení

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple bude vyžadovat aktualizace ATS (Application Transport Security) <!--748318-->

Apple oznámil, že od jara 2017 začne vynucovat specifické požadavky na ATS (Application Transport Security). ATS se používá k vynucení vyššího zabezpečení veškeré komunikace aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune, kteří používají aplikace Portál společnosti pro iOS. Další podrobnosti najdete v [blogu podpory služby Intune](https://aka.ms/compportalats).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Přímý přístup ke scénářům registrace Apple <!--951869-->

U účtů Intune vytvořených po lednu 2017 umožňuje Intune přímý přístup ke scénářům registrace Apple pomocí úlohy Registrovat zařízení na portálu Azure Preview. Náhled na registraci Apple byl předtím přístupný přes odkazy na portálu klasické služby Intune. Zpřístupnění těchto funkcí v Azure bude u účtů Intune vytvořených před lednem 2017 vyžadovat jednorázovou migraci. Plán této migrace zatím nebyl oznámen, podrobnosti ale budou zpřístupněny co nejdříve. Pokud váš existující účet nemá k tomuto náhledu přístup, k otestování tohoto nového prostředí důrazně doporučujeme vytvořit zkušební účet.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Co se chystá pro Appx v Intune na Azure <!-- 1000270 -->

V rámci migrace do Intune na Azure provádíme tři změny appx:

1. Přidání nového typu aplikace appx v klasické konzole Intune, který se dá nasadit jenom na zařízení zaregistrovaná v MDM
2. Změna účelu stávajícího typu aplikace appx, aby byl zacílený jenom na počítače PC spravované pomocí agenta Intune pro počítače PC
3. Převedení všech stávajících appx na appx MDM v rámci migrace

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?

Nebude to mít vliv na žádné z vašich stávajících nasazení do zařízení spravovaných pomocí agenta Intune pro počítače PC. Po migraci ale nebudete moct tyto migrované appx nasadit do žádných nových zařízení spravovaných pomocí agenta Intune pro počítače PC, pokud na ně předtím nebylo zacíleno.

#### <a name="what-action-do-i-need-to-take"></a>Co musím udělat

Pokud budete chtít provést nová nasazení do počítačů PC, budete muset po migraci znovu nahrát appx jako appx pro počítače PC. Další informace najdete v článku o [změnách appx v Intune na Azure](https://aka.ms/appxchange) na blogu týmu podpory Intune.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Veřejná verze Preview nového prostředí pro správu Intune v Azure <!--736542-->

Na začátku kalendářního roku 2017 provedeme migraci celého našeho prostředí pro správu do Azure, což umožní výkonnou a integrovanou správu základních pracovních postupů EMS na moderní platformě pro služby, která je rozšiřitelná pomocí rozhraní Graph API.

Noví zkušební tenanti se začnou objevovat ve veřejné verzi Preview nového prostředí pro správu na webu Azure Portal tento měsíc. Funkce a parita se stávající konzolou Intune se ve verzi Preview budou zavádět postupně.

Prostředí pro správu na webu Azure Portal bude využívat nové funkce seskupování a cílení, které už byly oznámeny. Při migraci vašeho stávajícího tenanta do nového prostředí seskupování se provede také vaše migrace do verze Preview nového prostředí pro správu vašeho tenanta. Pokud si chcete otestovat nebo prohlédnout některé nové funkce ještě před migrací vašeho tenanta, zaregistrujte si nový zkušební účet Intune nebo se podívejte na [novou dokumentaci](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Podpora možností spravované konfigurace pro aplikace Android <!-- 621621 -->

Aplikace Android v obchodu Play podporující možnosti spravované konfigurace se dají konfigurovat pomocí Intune.  Tato funkce umožňuje IT pracovníkům zobrazit seznam hodnot konfigurace podporovaných aplikací a poskytuje prvotřídní uživatelské rozhraní s asistencí, které jim umožňuje tyto hodnoty konfigurovat.

### <a name="remote-assistance-for-android-devices----675418---"></a>Vzdálená pomoc pro zařízení s Androidem <!-- 675418 -->

Microsoft Intune vám pomocí softwaru [TeamViewer](https://www.teamviewer.com), který se kupuje zvlášť, umožní poskytovat vzdálenou pomoc uživatelům, kteří používají zařízení s Androidem.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nové zásady Androidu pro komplexní kódy PIN <!-- 722069 -->

V profilu zařízení s Androidem 5.0 a vyšším můžete nastavit požadovaný typ hesla na Číselné komplexní.  Pomocí tohoto nastavení můžete uživatelům zařízení zabránit ve vytvoření PINu, který obsahuje opakující se nebo po sobě jdoucí čísla jako 1111 nebo 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Další podpora pro zařízení s Androidem for Work

- **Správa nastavení hesla a pracovního profilu** <!-- 612808 -->

  Přidali jsme novou zásadu omezení pro zařízení s Androidem for Work, která vám umožní spravovat nastavení hesla a pracovního profilu na zařízeních s Androidem for Work, která spravujete.

- **Povolení sdílení dat mezi pracovními a osobními profily** <!-- 1045102 -->

  Aktualizovali jsme nastavení **Sdílení dat mezi pracovními a osobními profily** v profilu omezení zařízení s Androidem for Work o nové možnosti, které vám pomůžou nakonfigurovat sdílení dat mezi pracovními a osobními profily.

- **Zakázaní kopírování a vkládání mezi pracovními a osobními profily** <!-- 1046094 -->

  Při správě zařízení s Androidem for Work pomocí Intune jsou akce kopírovat a vložit mezi pracovními a osobními aplikacemi povolené. Teď jsme přidali vlastní profil zařízení pro zařízení s Androidem for Work, který umožňuje akce Kopírovat a Vložit mezi pracovními a osobními aplikacemi zakázat.

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Přiřazení obchodních aplikací zařízením s iOSem a Androidem <!-- 1057568 -->

Obchodní aplikace pro iOS (soubory .ipa) a Android (soubory .apk) můžete přiřadit uživatelům nebo zařízením.

###  <a name="new-policies-for-ios-devices----723774-723815-723826-723830-723832---"></a>Nové zásady pro zařízení s iOSem <!-- 723774, 723815, 723826, 723830, 723832 -->

- **Aplikace na ploše** – můžete použít zásadu zařízení určující, které aplikace uživatelé uvidí na ploše svého zařízení s iOSem. Tato zásada změní rozložení plochy, ale nenasadí žádné aplikace, které jste určili, pokud nejsou nainstalované.

- **Připojení k zařízením AirPrint** – můžete pomocí zásady zařízení Intune určit, ke kterým zařízením AirPrint (síťovým tiskárnám) se můžou koncoví uživatelé zařízení s iOSem připojit.

- **Připojení k zařízením AirPlay** – můžete pomocí zásady zařízení Intune určit, ke kterým zařízením AirPlay (jako Apple TV) se můžou koncoví uživatelé zařízení s iOSem připojit.

- **Vlastní zpráva na zamčené obrazovce** – můžete nakonfigurovat vlastní zprávu, která se zobrazí uživatelům na zamčené obrazovce jejich zařízení s iOSem místo výchozí zprávy.

- **Filtr webového obsahu** – můžete řídit, které webové stránky můžou uživatelé zařízení s iOSem navštívit, a to pomocí jedné z těchto dvou metod:

  - Přidejte povolené a blokované adresy URL pomocí integrovaného filtru webového obsahu od společnosti Apple.
  - Povolte přístup z prohlížeče Safari jenom k určeným webovým stránkám. V prohlížeči Safari se vytvoří záložky pro weby, které určíte.


### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Omezení nabízených oznámení pro aplikace pro iOS <!-- 723767 -->

V profilu omezení zařízení Intune můžete nakonfigurovat tato nastavení oznámení pro zařízení s iOSem:

- Úplně zapnout nebo vypnout oznámení pro konkrétní aplikaci
- Zapnut nebo vypnout oznámení v centru oznámení pro konkrétní aplikaci
- Určit typ upozornění, a to buď **žádné**, **banner** nebo **modální upozornění**
- Určit, jestli jsou pro tuto aplikaci povolené odznaky
- Určit, jestli jsou povolené zvuky oznámení

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Konfigurace spouštění aplikací pro iOS autonomně v režimu jedné aplikace <!-- 737837 -->

Pomocí profilu zařízení Intune můžete nakonfigurovat, aby zařízení s iOSem spouštěla zadané aplikace v autonomním režimu jedné aplikace. Pokud je tento režim nakonfigurovaný a uživatel spustí aplikaci, v zařízení se zablokuje spuštění jakékoli další aplikace. Příkladem je nakonfigurování aplikace, která uživatelům umožňuje absolvovat na zařízení test. Když se akce aplikace dokončí nebo tuto zásadu odeberete, zařízení se vrátí do normálního stavu.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Konfigurace důvěryhodných domén pro e-mail a procházení webu v zařízeních s iOSem <!-- 723765 -->

V profilu omezení zařízení s iOSem můžete nakonfigurovat tato nastavení domén:

- **Zrušit označení e-mailových domén** – E-maily, které uživatel posílá nebo přijímá a které neodpovídají doménám zadaným tady, se označí jako nedůvěryhodné.

- **Spravované webové domény** – Dokumenty stažené z adres URL, které zadáte tady, se budou považovat za spravované (jenom Safari).  

- **Domény pro automatické vyplňování hesel v Safari**  – Uživatelé můžou ukládat hesla v Safari jenom z adres URL odpovídajících vzorům, které tady zadáte. Pokud toto nastavení chcete použít, musí být zařízení v režimu pod dohledem a nesmí být nakonfigurované pro více uživatelů. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Aplikace VPP, dostupné v Portálu společnosti pro iOS <!-- 748782 -->

Multilicenční aplikace (VPP) pro iOS můžete koncovým uživatelům přiřadit jako **Dostupné** instalace. Koncoví uživatelé budou k instalaci aplikace potřebovat účet Apple Store.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Synchronizace elektronických knih z Apple VPP Storu <!-- 800878 -->

Pomocí Intune můžete synchronizovat knihy, které jste zakoupili z Apple Storu v rámci multilicenčního programu, a přiřadit je uživatelům.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Správa více uživatelů pro zařízení se Samsung KNOX Standardem <!-- 971988 -->

U zařízení, která používají Samsung KNOX Standard, je teď podporována správa více uživatelů pomocí Intune. To znamená, že koncoví uživatelé se můžou k zařízení přihlašovat a ze zařízení odhlašovat pomocí svých přihlašovacích údajů Azure Active Directory a zařízení je centrálně spravované bez ohledu na to, jestli se zrovna používá.  Když se koncoví uživatelé přihlásí, mají přístup k aplikacím a také se na ně aplikují všechny zásady. Po odhlášení uživatelů se všechna data aplikací vymažou.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Další nastavení omezení pro zařízení s Windows <!-- 818566 -->

Přidali jsme podporu dalších nastavení omezení pro zařízení s Windows, jako je dodatečná podpora prohlížeče Edge, přizpůsobení zamykací obrazovky zařízení, přizpůsobení nabídky start, tapeta nastavená z vyhledávání ve Windows Spotlight a nastavení proxy serveru.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Podpora více uživatelů pro Windows 10 Creators Update <!-- 822547 -->

Přidali jsme podporu správy více uživatelů pro zařízení se systémem Windows 10 Creators Update připojená k doméně Azure Active Directory. To znamená, že když se k zařízení přihlásí různí standardní uživatelé pomocí svých přihlašovacích údajů Azure AD, dostanou všechny aplikace a zásady přiřazené jejich uživatelskému jménu. Uživatelé v současnosti nemůžou používat Portál společnosti pro samoobslužné scénáře, například instalování aplikací.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Akce Začít znovu pro počítače s Windows 10 <!-- 1004830 -->

V této verzi jsme přidali novou akci zařízení Začít znovu pro počítače s Windows 10.  Když tuto akci provedete, odeberou se všechny aplikace, které byly v počítači PC nainstalované, a počítač PC se automaticky aktualizuje na nejnovější verzi Windows. To se dá využít k odebrání aplikací předem nainstalovaných výrobcem, které se často dodávají s novým počítačem PC. Můžete nakonfigurovat, jestli se při provedení této akce mají zachovat uživatelská data.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Další možnosti upgradu na Windows 10 <!-- 903672 -->

Vytvořením zásad upgradu edice teď můžete zařízení upgradovat na následující další edice Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Hromadná registrace zařízení s Windows 10 <!-- 747607 -->

K Azure Active Directory a Intune můžete pomocí Windows Configuration Designeru (WCD) připojit velký počet zařízení se systémem Windows 10 Creators Update. Pokud chcete pro svého tenanta Azure AD povolit automatickou registraci MDM, vytvořte zřizovací balíček, který zařízení k tenantovi Azure AD připojí pomocí Windows Configuration Designeru, a použijte balíček na zařízení ve vlastnictví firmy, která chcete hromadně zaregistrovat a spravovat. Po použití balíčku se zařízení připojí k Azure AD, zaregistrují v Intune a jsou připravená na přihlašování vašich uživatelů z Azure AD.  Uživatelé Azure AD jsou na těchto zařízeních standardními uživateli a obdrží přiřazené zásady a požadované aplikace. Samoobslužné scénáře a scénáře s Portálem společnosti v současnosti nejsou podporované.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----58112-736644---"></a>Nová nastavení MAM pro PIN a spravovaná umístění úložiště<!-- 58112, 736644 -->

K dispozici jsou dvě nová nastavení aplikací, která vám pomůžou se scénáři správy mobilních aplikací (MAM):

- **Zakázat PIN kód aplikace, když je PIN kód zařízení spravovaný** – zjistí, jestli se na zaregistrovaném zařízení nachází PIN zařízení, a pokud ano, obchází PIN aplikace aktivovaný zásadami ochrany aplikací. Toto nastavení umožní snížit počet případů, kdy se uživatelům při spuštění aplikace s povolenou správou mobilních zařízení na zaregistrovaném zařízení zobrazí výzva k zadání PINu. Tato funkce je k dispozici pro Android i iOS.

- **Vyberte, do kterých služeb úložiště se můžou ukládat firemní data** – umožňuje určit umístění úložiště, do kterých se můžou ukládat firemní data. Uživatelé můžou ukládat do zvolených služeb umístění úložiště, takže všechny ostatní služby umístění úložiště, které nejsou uvedené, budou zablokované.

  Seznam podporovaných služeb umístění úložiště:

  - OneDrive
  - Business SharePoint Online
  - Místní úložiště


### <a name="see-also"></a>Související témata
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new-in-microsoft-intune.md).

