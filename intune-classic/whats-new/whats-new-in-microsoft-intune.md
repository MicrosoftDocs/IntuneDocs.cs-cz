---
title: "Co je nového | Dokumentace Microsoftu"
description: "Zjistěte, co je nového ve verzi Microsoft Intune z tohoto měsíce a v minulých verzích."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2e6452a066aa7eaeb295a3b531d83dc3b632bcf5
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---
# <a name="whats-new-in-microsoft-intune---april-2017"></a>Co je nového v Microsoft Intune – duben 2017
Zjistěte, co je nového v této verzi Microsoft Intune. Můžete také získat informace o nadcházejících změnách, se kterými byste měli počítat, a o minulých verzích.

> [!Note]
> Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nové funkce

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps k dispozici pro Managed Browser <!--822308, 822303-->

Microsoft MyApps teď mají lepší podporu v Managed Browseru. Uživatelé Managed Browseru, kteří nejsou cílem správy, budou přeneseni rovnou do služby MyApps, kde mají přístup k aplikacím SaaS, které jim zajistil správce. Uživatelé, kteří jsou cílem správy Intune, budou mít k MyApps dál přístup z integrované záložky Managed Browseru.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Nové ikony pro Managed Browser a Portál společnosti<!--918433, 918431, 971473-->

Managed Browser dostal aktualizované ikony pro verze aplikace pro Android i iOS. Nová ikona bude obsahovat aktualizovaný odznak Intune, aby byla konzistentnější s ostatními aplikacemi v Enterprise Mobility + Security (EM+S). Novou ikonu pro Managed Browser uvidíte na [stránce s novinkami v uživatelském rozhraní aplikace Intune](whats-new-in-intune-app-ui.md).

Portál společnosti také dostal aktualizované ikony pro verze aplikace pro Android, iOS i Windows, aby byly konzistentnější s ostatními aplikacemi v EM+S. Tyto ikony se budou postupně vydávat pro všechny platformy od dubna do konce května.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Ukazatel průběhu přihlášení v Portálu společnosti pro Android <!--953374-->

Aktualizace aplikace Portál společnosti pro Android zobrazuje indikátor průběhu přihlášení, když uživatel aplikaci spustí nebo pokračuje v jejím používání. Než uživatel získá přístup k aplikaci, indikátor postupně zobrazuje nové stavy od „Připojování...“ přes „Přihlašování...“ po „Kontrolují se požadavky na zabezpečení...“. Nové obrazovky pro aplikaci Portál společnosti pro Android uvidíte na [stránce s novinkami v uživatelském rozhraní aplikace Intune](whats-new-in-intune-app-ui.md).

### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Blokování přístupu aplikací k SharePointu Online <!-- 679339 -->

Nyní můžete vytvořit zásadu podmíněného přístupu založeného na aplikacích, abyste aplikacím, na které nejsou aplikované zásady ochrany aplikací, zablokovali přístup k [SharePointu Online](/intune-classic/deploy-use/mam-ca-for-sharepoint-online). V případě podmíněného přístupu na základě aplikací můžete pomocí portálu Azure Portal určit aplikace, které mají mít přístup k SharePointu Online.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Podpora jednotného přihlášení z Portálu společnosti pro iOS do Outlooku pro iOS <!--834012-->
Uživatelé už se nemusí přihlašovat k aplikaci Outlook, pokud jsou na stejném zařízení pomocí stejného účtu přihlášení k aplikaci Portál společnosti pro iOS. Při spuštění aplikace Outlook budou uživatelé moct zvolit svůj účet a přihlásit se automaticky. Pracujeme také na tom, abychom tuto funkci přidali i pro další aplikace Microsoftu.

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Vylepšené zprávy o stavu v aplikaci Portál společnosti pro iOS<!--744866-->
V aplikaci Portál společnosti pro iOS se teď budou zobrazovat nové a konkrétnější chybové zprávy poskytující přístupnější informace o tom, co se děje na zařízeních. Tyto případy chyb byly dříve součástí obecné chybové zprávy s názvem „Portál společnosti dočasně nedostupný“. Kromě toho, pokud uživatel aplikaci Portál společnosti spustí v iOSu, když chybí připojení k internetu, uvidí teď na domovské stránce trvalý stavový řádek s oznámením o tom, že chybí připojení k internetu.

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Vylepšený stav instalace aplikace pro aplikaci Portál společnosti ve Windows 10 <!--676495-->

Mezi nová vylepšení instalací aplikací uvedená v aplikaci Portál společnosti ve Windows 10 patří:
-    Rychlejší generování sestav o průběhu instalace pro balíčky MSI
-    Rychlejší generování sestav o průběhu instalace pro moderní aplikace na zařízeních s Windows 10 Anniversary Update a novějšími verzemi
-    Nový indikátor průběhu pro všechny instalace moderních aplikací na zařízeních s Windows 10 Anniversary Update a novějšími verzemi

Nový indikátor průběhu najdete na stránce[Co je nového v uživatelském rozhraní aplikací Intune](whats-new-in-intune-app-ui.md).

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Hromadná registrace zařízení s Windows 10 <!-- 747607 -->

Nově můžete připojit velký počet zařízení s Windows 10 Creators Update ke službě Azure Active Directory a Intune pomocí nástroje Windows Configuration Manager. /intune-classic/deploy-use/bulk-enroll-windows) pro tenanta Azure AD, vytvořte zřizovací balíček, který připojí zařízení k tenantovi Azure AD pomocí nástroje Windows Configuration Designer, a použijte balíček u firemních zařízení, která chcete hromadně zaregistrovat a spravovat. Po použití balíčku se zařízení připojí k Azure AD, zaregistrují v Intune a jsou připravená na přihlašování vašich uživatelů z Azure AD.  Uživatelé Azure AD jsou na těchto zařízeních standardními uživateli a obdrží přiřazené zásady a požadované aplikace. Samoobslužné scénáře a scénáře s Portálem společnosti v současnosti nejsou podporované.

## <a name="notices"></a>Sdělení

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

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Co je nového ve veřejné verzi Preview prostředí pro správu Intune v Azure<!--736542-->

Na začátku kalendářního roku 2017 provedeme migraci celého našeho prostředí pro správu do Azure, což umožní výkonnou a integrovanou správu základních pracovních postupů EMS na moderní platformě pro služby, která je rozšiřitelná pomocí rozhraní Graph API.

Noví zkušební tenanti se začnou objevovat ve veřejné verzi Preview nového prostředí pro správu na webu Azure Portal tento měsíc. Funkce a parita se stávající konzolou Intune se ve verzi Preview budou zavádět postupně.

Prostředí pro správu na webu Azure Portal bude využívat nové funkce seskupování a cílení, které už byly oznámeny. Při migraci vašeho stávajícího tenanta do nového prostředí seskupování se provede také vaše migrace do verze Preview nového prostředí pro správu vašeho tenanta. Pokud si chcete otestovat nebo prohlédnout některé nové funkce ještě před migrací vašeho tenanta, zaregistrujte si nový zkušební účet Intune nebo se podívejte na [novou dokumentaci](/intune/whats-new).

> [!Note]
> Pro Azure Portal Preview zavádíme aktualizace pro tento měsíc. Změny ale nemusí být hned dostupné. Důvodem je způsob, jakým se služba Intune aktualizuje.  Několik součástí služby se musí aktualizovat postupně, než budou nové funkce portálu k dispozici. Vyhledejte změny na portálu Azure Portal Preview, až je v průběhu tohoto měsíce zavedeme. Úplný seznam změn najdete v článku [Co je nového v Microsoft Intune Preview](/intune/whats-new).

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Nahrazení rolí správy na portálu Azure Portal

Existující role pro správu mobilních aplikací (MAM) (Přispěvatel, Vlastník a Jen pro čtení) používané v klasickém portálu Intune (Silverlight) byly na portálu Azure Portal pro Intune nahrazeny celou řadou nových možností řízení přístupu na základě role (RBAC). Jakmile migrujete na portál Azure Portal, bude potřeba, abyste svým správcům přiřadili tyto nové role správy. Další informace o RBAC a nových rolích najdete v článku [Řízení přístupu na základě role pro Microsoft Intune](/intune/role-based-access-control).

## <a name="whats-coming"></a>Co připravujeme

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Vylepšené přihlašování k aplikacím Portál společnosti na všech platformách <!--User Story 1132123-->

Avizujeme změnu, kterou uvedeme během několika nadcházejících měsíců a která vylepší přihlašování k aplikacím Portál společnosti Intune v systémech Android, iOS a Windows. Nové uživatelské prostředí se automaticky zobrazí na všech platformách pro aplikaci Portál společnosti, až Azure AD tuto změnu provede. Kromě toho se teď uživatelé můžou k Portálu společnosti přihlašovat z jiného zařízení pomocí vygenerovaného kódu na jedno použití. To se hodí hlavně v případech, kdy se uživatelé potřebují přihlásit bez přihlašovacích údajů.

Snímky obrazovky předchozího způsobu přihlašování, nového způsobu přihlašování pomocí přihlašovacích údajů a nového způsobu přihlašování z jiného zařízení najdete na stránce s [novinkami v uživatelském rozhraní aplikací](whats-new-in-intune-app-ui.md).

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Plánovaná změna: Intune mění způsob fungování portálu Intune Partner Portal<!-- 1050016 -->

Počínaje aktualizací služby v polovině května 2017 odstraníme stránku Intune Partner z manage.microsoft.com.  

Pokud jste partnerským správcem, nebude už moct stránku Intune Partner zobrazit a provádět z ní jménem vašich zákazníků kroky, ale místo toho se budete muset přihlásit k jednomu ze dvou dalších partnerských portálů Microsoftu.

K účtům zákazníků, které spravujete, se budete moct přihlásit z [Partnerského centra Microsoftu](https://partnercenter.microsoft.com/) a [Centra pro partnerskou správu Office 365](https://portal.office.com/). V budoucnu jako partneři prosím ke správě svých zákazníků používejte jeden z těchto webů.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple bude vyžadovat aktualizace ATS (Application Transport Security) <!--748318-->

Apple oznámil, že začne vynucovat specifické požadavky na ATS (Application Transport Security). ATS se používá k vynucení vyššího zabezpečení veškeré komunikace aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune, kteří používají aplikace Portál společnosti pro iOS.

Prostřednictvím programu Apple TestFlight, který vynucuje nové požadavky na ATS, jsme zpřístupnili verzi aplikace Portál společnosti pro iOS. Pokud si ji chcete vyzkoušet a otestovat, jestli ATS dodržujete, napište nám na adresu <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> zprávu s vaším jménem a příjmením, e-mailovou adresou a názvem společnosti. Další podrobnosti najdete v [blogu podpory služby Intune](https://aka.ms/compportalats).

### <a name="see-also"></a>Viz taky
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co je nového v Azure Preview](https://docs.microsoft.com/intune/whats-new)
* [Co je nového v uživatelském rozhraní Portálu společnosti](/intune-classic/whats-new/whats-new-in-company-portal-ui)
* [Co je nového – archiv](whats-new-archive.md)

