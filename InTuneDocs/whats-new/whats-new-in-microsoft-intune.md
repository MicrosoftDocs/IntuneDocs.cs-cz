---
title: "Co je nového | Dokumentace Microsoftu"
description: "Zjistěte, co je nového ve verzi Microsoft Intune z tohoto měsíce a v minulých verzích."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: 2a602b351cf7f345bd56f20394943ea25f2d2060
ms.lasthandoff: 03/15/2017


---
# <a name="whats-new-in-microsoft-intune---march-2017"></a>Co je nového v Microsoft Intune – březen 2017
Zjistěte, co je nového v této verzi Microsoft Intune. Můžete také získat informace o nadcházejících změnách, se kterými byste měli počítat, a o minulých verzích.

> [!Note]
> Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nové funkce

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nové uživatelské prostředí aplikace Portál společnosti pro Android <!--621622-->

Kvůli modernějšímu vzhledu a chování a lepšímu uživatelskému prostředí bude aktualizováno uživatelské rozhraní aplikace Portál společnosti pro Android. K významným aktualizacím patří:

- Barvy: IT oddělení může v záhlaví karet aplikace Portál společnosti definovat firemní barvy.
- Aplikace: Na kartě **Aplikace** jsou aktualizovaná tlačítka **Vybrané aplikace** a **Všechny aplikace**.
- Hledání: Na kartě **Aplikace** má tlačítko **Hledat** podobu plovoucího tlačítka akce.
- Navigace mezi aplikacemi: Zobrazení **Všechny aplikace** obsahuje karty **Doporučené**, **Vše** a **Kategorie**, které zjednodušují navigaci.
- Podpora: Karty **Moje zařízení** a **Kontaktovat IT** jsou aktualizované tak, aby byly zřetelnější.

Další podrobnosti o těchto změnách najdete v článku [Aktualizace uživatelského rozhraní pro aplikace Intune pro koncové uživatele](whats-new-in-intune-app-ui.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Nespravovaná zařízení mají přístup k přiřazeným aplikacím <!--664691-->

Jako součást změn v návrhu na webu Portál společnosti budou moci uživatelé iOSu a Androidu na svoje nespravovaná zařízení instalovat aplikace, které mají přiřazené jako dostupné bez registrace. S použitím přihlašovacích údajů pro Intune se budou moct uživatelé přihlásit na web Portál společnosti a zobrazit seznam aplikací, které mají přiřazené. Balíčky aplikací, které jsou dostupné bez registrace, jsou k dispozici ke stažení prostřednictvím webu Portál společnosti. Aplikace, které vyžadují registraci, aby je bylo možné nainstalovat, nejsou touto změnou ovlivněny, protože když budou chtít tyto aplikace uživatelé nainstalovat, zobrazí se jim výzva k registraci.

### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Podepisovací skript pro Portál společnosti pro Windows 10 <!--941642-->

Pokud potřebujete stáhnout aplikaci Portál společnosti pro Windows 10 a nainstalovat ji bokem, můžete použít skript, který zjednoduší a zefektivní proces podepisování aplikací ve vaší organizaci.   Informace o tom, jak tento skript stáhnout, a pokyny k jeho použití najdete v článku [Microsoft Intune Signing Script for Windows 10 Company Portal](https://aka.ms/win10cpscript) (Podepisovací skript Microsoft Intune pro Portál společnosti pro Windows 10) na webu TechNet. Další podrobnosti o tomto oznámení najdete v článku [Updating your Windows 10 Company Portal app](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) (Aktualizace aplikace Portál společnosti pro Windows 10) na blogu týmu podpory Intune.


## <a name="notices"></a>Sdělení

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Vylepšená podpora pro uživatele Androidu v Číně <!--720444-->

Vzhledem k absenci obchodu Google Play v Číně musí zařízení s Androidem získávat aplikace z čínských obchodů. Portál společnosti bude tuto situaci podporovat tím, že uživatele Androidu v Číně přesměruje na stažení aplikací Portál společnosti a Outlook z místních obchodů s aplikacemi. Tato změna vylepší uživatelské prostředí při povolených zásadách podmíněného přístupu, a to jak při správě mobilních zařízení, tak při správě mobilních aplikací. Aplikace Portál společnosti a Outlook pro Android jsou dostupné v následujících čínských obchodech s aplikacemi:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>Osvědčený postup: Ujistěte se, že aplikace Portál společnosti jsou aktuální. <!--879465-->

V prosinci 2016 jsme vydali aktualizaci umožňující vynucení pro vícefaktorové ověřování (MFA) u skupiny uživatelů, když zaregistrují zařízení s iOSem, Androidem, Windows 8.1+ nebo Windows Phone 8.1+. Tato funkce nefunguje bez některých základních verzí aplikace Portál společnosti pro Android (v5.0.3419.0+) a iOS (v2.1.17+).

Microsoft průběžně zdokonaluje Intune přidáváním nových funkcí do konzoly i do aplikací Portál společnosti na všech podporovaných platformách. Microsoft proto vydává opravy jenom pro problémy, které se vyskytly v aktuální verzi aplikace Portál společnosti. Aby se vám tedy s aplikacemi pracovalo co nejlépe, doporučujeme používat nejnovější verze aplikací Portál společnosti.

>[!Tip]
> Požádejte uživatele, aby si na svých zařízeních nastavili automatické aktualizace aplikací z příslušného obchodu s aplikacemi. Pokud jste ve sdílené síťové složce zpřístupnili aplikaci Portál společnosti pro Android, můžete její nejnovější verzi stáhnout z webu [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=49140).

### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>Aplikace Microsoft Teams jsou teď povolené pro správu mobilních aplikací (MAM) v iOSu a Androidu

Společnost Microsoft oznámila obecnou dostupnost aplikací Microsoft Teams. Aktualizované aplikace Microsoft Teams pro iOS a Android teď můžou využívat možnosti správy mobilních aplikací (MAM) v Intune. Vaše týmy tedy můžou spolupracovat na různých zařízeních a zároveň je zajištěná ochrana konverzací a firemních dat. Další podrobnosti najdete v [oznámení o Microsoft Teams](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) na blogu Enterprise Mobility and Security.


## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Co je nového ve veřejné verzi Preview prostředí pro správu Intune v Azure<!--736542-->

Na začátku kalendářního roku 2017 provedeme migraci celého našeho prostředí pro správu do Azure, což umožní výkonnou a integrovanou správu základních pracovních postupů EMS na moderní platformě pro služby, která je rozšiřitelná pomocí rozhraní Graph API.

Noví zkušební tenanti se začnou objevovat ve veřejné verzi Preview nového prostředí pro správu na webu Azure Portal tento měsíc. Funkce a parita se stávající konzolou Intune se ve verzi Preview budou zavádět postupně.

Prostředí pro správu na webu Azure Portal bude využívat nové funkce seskupování a cílení, které už byly oznámeny. Při migraci vašeho stávajícího tenanta do nového prostředí seskupování se provede také vaše migrace do verze Preview nového prostředí pro správu vašeho tenanta. Pokud si chcete otestovat nebo prohlédnout některé nové funkce ještě před migrací vašeho tenanta, zaregistrujte si nový zkušební účet Intune nebo se podívejte na [novou dokumentaci](https://docs.microsoft.com/intune-azure/introduction/whats-new).

> [!Note]
> Pro Azure Portal Preview zavádíme aktualizace pro tento měsíc. Změny ale nemusí být hned dostupné. Důvodem je způsob, jakým se služba Intune aktualizuje.  Několik součástí služby se musí aktualizovat postupně, než budou nové funkce portálu k dispozici. Vyhledejte změny na portálu Azure Portal Preview, až je v průběhu tohoto měsíce zavedeme. Úplný seznam změn najdete v článku [Co je nového v Microsoft Intune Preview](/intune-azure/introduction/whats-new).

## <a name="whats-coming"></a>Co připravujeme

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple bude vyžadovat aktualizace ATS (Application Transport Security) <!--748318-->

Apple oznámil, že od jara 2017 začne vynucovat specifické požadavky na ATS (Application Transport Security). ATS se používá k vynucení vyššího zabezpečení veškeré komunikace aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune, kteří používají aplikace Portál společnosti pro iOS. Další podrobnosti najdete v [blogu podpory služby Intune](https://aka.ms/compportalats).

### <a name="see-also"></a>Viz taky
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co je nového v Azure Preview](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Co je nového v uživatelském rozhraní Portálu společnosti](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Co je nového – archiv](whats-new-archive.md)

