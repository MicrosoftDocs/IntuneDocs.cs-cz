---
title: "Časná edice | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f287a0ad082fa20a2e84abbf8f5585117aae6f57
ms.openlocfilehash: e604b8809bd444d9069d449a6c691a8444296623


---

# <a name="the-early-edition-for-microsoft-intune---december"></a>Časná edice pro Microsoft Intune – prosinec

**Časná edice** poskytuje seznam funkcí, které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány na základě smlouvy o utajení (NDA) ve velmi omezené míře a mohou podléhat změnám. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a mohou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moci zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se prosím na příslušný kontakt (Intune/PM).

Tato stránka se pravidelně aktualizuje. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.

Následující změny v Intune jsou ve vývoji. Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

<!--736542-->
## <a name="public-preview-of-the-new-intune-admin-experience-on-azure"></a>Veřejná verze Preview nového prostředí pro správu Intune v Azure

Na začátku kalendářního roku 2017 provedeme migraci celého našeho prostředí pro správu do Azure, což umožní výkonnou a integrovanou správu základních pracovních postupů EMS na moderní platformě pro služby, která je rozšiřitelná pomocí rozhraní Graph API.

Noví zkušební tenanti se začnou objevovat ve veřejné verzi Preview nového prostředí pro správu na webu Azure Portal tento měsíc. Funkce a parita se stávající konzolou Intune se ve verzi Preview budou zavádět postupně.

Prostředí pro správu na webu Azure Portal bude využívat nové funkce seskupování a cílení, které už byly oznámeny. Při migraci vašeho stávajícího tenanta do nového prostředí seskupování se provede také vaše migrace do verze Preview nového prostředí pro správu vašeho tenanta. Pokud si chcete otestovat nebo prohlédnout některé nové funkce ještě před migrací vašeho tenanta, zaregistrujte si nový zkušební účet Intune nebo se podívejte na novou dokumentaci.

Pokud máte jakékoli dotazy k časovému plánu migrace vašeho tenanta, kontaktujte náš tým pro migraci na adrese [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integrace se službami Telecom Expense Management na webu Azure Portal ve veřejné verzi Preview<!--747605-->
Ve verzi Preview teď začínáme na webu Azure Portal zavádět integraci se službami TEM (Telecom Expense Management) třetích stran. Pomocí Intune můžete uplatňovat limity na využívání domácích a roamingových dat. Tyto integrace začínáme zavádět s řešením [Saaswedo](http://www.saaswedo.com).

## <a name="new-capabilities"></a>Nové funkce

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Vícefaktorové ověřování na všech platformách <!--747590-->
Teď můžete vynutit vícefaktorové ověřování (MFA) u vybrané skupiny uživatelů při registraci jejich zařízení se systémem iOS, Android, Windows 8.1+ nebo Windows Phone 8.1+ tak, že na portálu pro správu Azure nakonfigurujete MFA v aplikaci pro registraci Microsoft Intune v Azure Active Directory.

### <a name="conditional-access-for-mam-with-sharepoint-online---vso-679339--"></a>Podmíněný přístup k SharePointu Online pro MAM <!--VSO 679339-->
Aplikacím, které nejsou podporované v zásadách správy mobilních aplikací (MAM) Intune, můžete přístup k SharePointu Online zablokovat.  Na webu Azure Portal můžete začít používat správu mobilních aplikací Intune. Vyhledejte v okně __Nastavení__ část __Podmíněný přístup__, ve které bude možnost pro SharePoint Online. Tato funkce se bude dodávat odděleně od zbývajících součástí vydání služby.

## <a name="notices"></a>Sdělení

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>Vícefaktorové ověřování při registraci se přesouvá na Azure Portal <!--VSO 750545-->
Dříve by správci při nastavování vícefaktorového ověřování pro registrace Intune přešli do konzoly Intune nebo do konzoly nástroje Configuration Manager (verze dřívější než 1610). S touto aktualizovanou funkcí se teď budete pomocí přihlašovacích údajů Intune přihlašovat na [Microsoft Azure Portal](https://manage.windowsazure.com) a nakonfigurujete nastavení MFA pomocí služby Azure AD. Další informace o tom najdete [tady](https://aka.ms/mfa_ad).

### <a name="company-portal-app-for-android-now-available-in-china---vso-658093--"></a>Aplikace Portál společnosti pro Android je teď dostupná v Číně <!--VSO 658093-->
Publikujeme aplikaci Portál společnosti pro Android pro stahování v Číně. Vzhledem k absenci obchodu Google Play v Číně musí zařízení s Androidem získávat aplikace z čínských marketplace aplikací. Aplikace Portál společnosti pro Android bude dostupná ke stažení na 360, Tencent, Xiaomi, Wandoujia a Huawei. 

Ke komunikaci se službou Microsoft Intune používá aplikace Portál společnosti pro Android služby Google Play. Vzhledem k tomu, že služby Google Play ještě nejsou v Číně dostupné, může provádění kterékoli z následujících úloh trvat až 8 hodin. 

|Konzola správce Intune| Aplikace Portál společnosti Intune pro Android |Web Portál společnosti Intune|   
|---|---|---|
|Úplné vymazání| Odebrání vzdáleného zařízení| Odebrání zařízení (místní a vzdálené)|
|selektivní vymazání| Resetování zařízení| Resetování zařízení|
|Nasazení nových nebo aktualizovaných aplikací| Instalace dostupných obchodních aplikací| Resetování hesla zařízení|
|Vzdálené uzamčení|||
|Resetování hesla|||

## <a name="deprecations"></a>Vyřazení

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Odebrání zásad poštovní schránky mobilních zařízení Exchange Online <!--770687-->
Od prosince už správci nebudou moct zobrazit nebo nakonfigurovat zásady poštovní schránky mobilních zařízení Exchange Online (EAS) v konzole Intune. Tato změna se bude pro všechny tenanty Intune zavádět v průběhu prosince a ledna. Všechny stávající zásady zůstanou tak, jak jsou nakonfigurované. Ke konfiguraci nových zásad použijte prostředí Exchange Management Shell. Další informace o tom najdete [tady](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Aplikace Intune AV Player, Image Viewer a PDF Viewer se už v Androidu dále nepodporují<!--747553-->
Od poloviny prosince 2016 už uživatelé nebudou moct dál používat aplikace Intune AV Player, Image Viewer a PDF Viewer. Tyto aplikace nahrazuje aplikace Azure Information Protection. Další informace o aplikaci Azure Information Protection najdete [tady](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

### <a name="see-also"></a>Související témata
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Nov16_HO4-->


