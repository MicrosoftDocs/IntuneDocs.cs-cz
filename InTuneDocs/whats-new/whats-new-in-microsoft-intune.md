---
title: "Co je nového | Microsoft Intune"
description: "Zjistěte, co je nového v aktualizaci služby Microsoft Intune v tomto měsíci nebo dříve"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9fd309a10d9eb020795c5ce46df124b13dc1a006
ms.openlocfilehash: d117c929fbde4dd0a39503b8da695aa9c9ea91ad


---
# <a name="whats-new-in-microsoft-intune---december-2016"></a>Co je nového v Microsoft Intune – prosinec 2016
Zjistěte, co je nového v této verzi Microsoft Intune. Můžete také získat informace o nadcházejících změnách, se kterými byste měli počítat, a o minulých verzích.

> [!Note]
> Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure--736542--"></a>Veřejná verze Preview nového prostředí pro správu Intune v Azure<!--736542-->
Na začátku kalendářního roku 2017 provedeme migraci celého našeho prostředí pro správu do Azure, což umožní výkonnou a integrovanou správu základních pracovních postupů EMS na moderní platformě pro služby, která je rozšiřitelná pomocí rozhraní Graph API. Před všeobecnou dostupností tohoto portálu pro všechny tenanty Intune s radostí oznamujeme, že později tento měsíc začneme vybraným tenantům zavádět verzi Preview tohoto nového prostředí pro správce.

Prostředí pro správu na webu Azure Portal bude využívat nové funkce seskupování a cílení, které už byly oznámeny. Při migraci vašeho stávajícího tenanta do nového prostředí seskupování se provede také vaše migrace do verze Preview nového prostředí pro správu vašeho tenanta. Zatím můžete zjistit další informace o tom, co pro Microsoft Intune na portálu Azure Portal chystáme, v naší [nové dokumentaci](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

Pokud máte jakékoli dotazy k časovému plánu migrace vašeho tenanta, kontaktujte náš tým pro migraci na adrese [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integrace se službami Telecom Expense Management na webu Azure Portal ve veřejné verzi Preview<!--747605-->
Ve verzi Preview teď začínáme na webu Azure Portal zavádět integraci se službami TEM (Telecom Expense Management) třetích stran. Pomocí Intune můžete uplatňovat limity na využívání domácích a roamingových dat. Tyto integrace začínáme zavádět s řešením [Saaswedo](http://www.saaswedo.com).

## <a name="new-capabilities"></a>Nové funkce

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Vícefaktorové ověřování na všech platformách <!--747590-->
Teď můžete vynutit vícefaktorové ověřování (MFA) u vybrané skupiny uživatelů při registraci jejich zařízení se systémem iOS, Android, Windows 8.1+ nebo Windows Phone 8.1+ tak, že na portálu pro správu Azure nakonfigurujete MFA v aplikaci pro registraci Microsoft Intune v Azure Active Directory.

<!--VSO 679339, awaiting chrisgre for go-live--><!--### Conditional access for MAM with SharePoint Online
Aplikacím, které nejsou podporované v zásadách správy mobilních aplikací (MAM) Intune, můžete přístup k SharePointu Online zablokovat.  Na webu Azure Portal můžete začít používat správu mobilních aplikací Intune. Vyhledejte v okně __Nastavení__ část __Podmíněný přístup__, ve které bude možnost pro SharePoint Online. Tato funkce se bude dodávat odděleně od zbývajících součástí vydání služby. Další informace o této nové funkci najdete [tady](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="ability-to-restrict-mobile-device-enrollment--747596--"></a>Možnost omezení registrace mobilního zařízení<!--747596-->
Intune přidává nová omezení registrace řídící to, které platformy mobilních zařízení se mohou zaregistrovat. Intune odděluje platformy mobilních zařízení, jako je iOS, macOS, Android, Windows a Windows Mobile.
* Omezení registrace mobilních zařízení neomezuje registraci klienta pro počítače.
* Pouze pro iOS existuje další možnost blokování registrace osobně vlastněných zařízení.

Pokud správce IT neoznačí nová zařízení jako vlastněná podnikem, Intune všechna nová zařízení označí jako osobní. Podrobnosti najdete v [tomto článku](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).


## <a name="notices"></a>Sdělení

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>Vícefaktorové ověřování při registraci se přesouvá na Azure Portal <!--VSO 750545-->
Dříve by správci při nastavování vícefaktorového ověřování pro registrace Intune přešli do konzoly Intune nebo do konzoly Configuration Manageru (verze dřívější než z října 2016). S touto aktualizovanou funkcí se teď budete pomocí přihlašovacích údajů Intune přihlašovat na [Microsoft Azure Portal](https://manage.windowsazure.com) a nakonfigurujete nastavení MFA pomocí služby Azure AD. Další informace o tom najdete [tady](https://aka.ms/mfa_ad).

### <a name="company-portal-app-for-android-now-available-in-china---vso-658093--"></a>Aplikace Portál společnosti pro Android je teď dostupná v Číně <!--VSO 658093-->
Publikujeme aplikaci Portál společnosti pro Android pro stahování v Číně. Vzhledem k absenci obchodu Google Play v Číně musí zařízení s Androidem získávat aplikace z čínských marketplace aplikací. Aplikace Portál společnosti pro Android bude dostupná ke stažení v těchto obchodech:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Ke komunikaci se službou Microsoft Intune používá aplikace Portál společnosti pro Android služby Google Play. Vzhledem k tomu, že služby Google Play ještě nejsou v Číně dostupné, může provádění kterékoli z následujících úloh trvat až 8 hodin. 

|Konzola správce Intune| Aplikace Portál společnosti Intune pro Android |Web Portál společnosti Intune|   
|---|---|---|
|Úplné vymazání| Odebrání vzdáleného zařízení| Odebrání zařízení (místní a vzdálené)|
|selektivní vymazání| Resetování zařízení| Resetování zařízení|
|Nasazení nových nebo aktualizovaných aplikací| Instalace dostupných obchodních aplikací| Resetování hesla zařízení|
|Vzdálené uzamčení|||
|Resetování hesla|||

## <a name="deprecations"></a>Vyřazení

### <a name="firefox-to-no-longer-support-silverlight--vso-tba--"></a>Firefox už nebude podporovat Silverlight<!--VSO TBA-->
Mozilla ve verzi 52 [prohlížeče Firefox](https://www.mozilla.org/firefox) přestává podporovat Silverlight s účinností od března 2017. V důsledku toho se už pomocí Firefoxu ve verzi vyšší než 51 nebudete moct přihlásit ke stávající konzole Intune. Doporučujeme pro přístup ke konzole pro správce používat Internet Explorer 10 nebo 11 nebo [verzi Firefoxu starší než 52](https://ftp.mozilla.org/pub/firefox/releases/). Přechod Intune na Azure Portal umožní podporu celé řady [moderních prohlížečů](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices) bez závislosti na Silverlightu.

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Odebrání zásad poštovní schránky mobilních zařízení Exchange Online <!--770687-->
Od prosince už správci nebudou moct zobrazit nebo nakonfigurovat zásady poštovní schránky mobilních zařízení Exchange Online (EAS) v konzole Intune. Tato změna se bude pro všechny tenanty Intune zavádět v průběhu prosince a ledna. Všechny stávající zásady zůstanou tak, jak jsou nakonfigurované. Ke konfiguraci nových zásad použijte prostředí Exchange Management Shell. Další informace o tom najdete [tady](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Aplikace Intune AV Player, Image Viewer a PDF Viewer se už v Androidu dále nepodporují<!--747553-->
Od poloviny prosince 2016 už uživatelé nebudou moct dál používat aplikace Intune AV Player, Image Viewer a PDF Viewer. Tyto aplikace nahrazuje aplikace Azure Information Protection. Další informace o aplikaci Azure Information Protection najdete [tady](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

### <a name="see-also"></a>Viz taky
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Předchozí verze Intune](whats-new-archive.md)



<!--HONumber=Dec16_HO2-->


