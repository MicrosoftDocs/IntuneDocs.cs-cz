---
title: "Co je nového | Dokumentace Microsoftu"
description: "Zjistěte, co je nového ve verzi Microsoft Intune z tohoto měsíce a v minulých verzích."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: cb1679deda0ba325ee3bd7288713f12317489006
ms.openlocfilehash: 37d44dc2752815ef7abf47e5d4a658a126892a86
ms.lasthandoff: 02/18/2017


---
# <a name="whats-new-in-microsoft-intune---february-2017"></a>Co je nového v Microsoft Intune – únor 2017
Zjistěte, co je nového v této verzi Microsoft Intune. Můžete také získat informace o nadcházejících změnách, se kterými byste měli počítat, a o minulých verzích.

> [!Note]
> Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nové funkce

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizace webu Portál společnosti <!--753980-->
Web Portál společnosti bude podporovat aplikace zaměřené na uživatele, kteří nemají spravovaná zařízení. Tento web bude podobně jako ostatní produkty a služby Microsoftu používat nové kontrastní barevné schéma, dynamické ilustrace a „hamburgerovou“ nabídku ![Obrázek hamburgerové nabídky webu Portál společnosti, která je teď přidaná v levém horním rohu webu Portál společnosti](./media/CP_hamburger_menu.png), která bude obsahovat kontaktní údaje helpdesku a informace o existujících spravovaných zařízeních. Cílová stránka bude mít nové uspořádání, které zdůrazní aplikace dostupné uživatelům – s karusely pro Vybrané a Nedávno aktualizované aplikace. Obrázky před a po najdete na [stránce s aktualizacemi uživatelského rozhraní](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Nové prostředí s asistencí pro portál společnosti s Windows 10 <!--713927-->
Od března bude portál společnosti pro Windows 10 obsahovat návod s pokyny Intune pro zařízení, která nejsou identifikovaná nebo zaregistrovaná. Nové prostředí obsahuje podrobné pokyny přizpůsobené buildu uživatele Windows 10, které provedou uživatele registrací AAD (která je nutná k identifikaci pro funkce podmíněného přístupu) a registraci MDM (která je nutná pro funkce správy zařízení). Prostředí s asistencí bude přístupné z domovské stránky portálu společnosti a je volitelné. Uživatelé budou moct nadále aplikaci používat, pokud se nezaregistrují, ale některé funkce můžou být omezené.

## <a name="notices"></a>Sdělení

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Migrace skupin nevyžadují pro zařízení s iOSem žádné aktualizace skupin ani zásad <!--898837-->
Pro každou skupinu zařízení s Intune předem přiřazenou profilem registrace podnikového zařízení se během migrace do skupin zařízení Azure Active Directory vytvoří odpovídající dynamická skupina zařízení v adresáři AAD založená na názvu profilu registrace podnikového zařízení. Zajistí se tak, že se budou zařízení během registrace automaticky seskupovat a přijmou stejné zásady a aplikace jako původní skupina Intune.

Jakmile tenant zahájí proces migrace pro seskupování a zacílení, vytvoří Intune automaticky dynamickou skupinu AAD tak, aby odpovídala skupině Intune, na kterou je zacílený profil registrace podnikového zařízení. Pokud správce Intune odstraní cílovou skupinu Intune, neodstraní se odpovídající dynamická skupina AAD. Smažou se členové skupiny a dynamický dotaz, ale skupina samotná zůstane, dokud ji správce IT neodebere přes portál AAD.

Podobně, pokud správce IT změní to, která skupina Intune je cílem profilu registrace podnikového zařízení, vytvoří Intune novou dynamickou skupinu odrážející nové přiřazení profilu, ale neodebere se dynamická skupina vytvořená pro staré přiřazení.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Změna výchozího nastavení: Správa desktopových zařízení s Windows přes nastavení Windows <!--663050-->
Výchozí chování registrace stolních počítačů s Windows 10 se mění. Nové registrace se budou provádět obvyklým tokem registrace agenta MDM, nikoli přes agenta pro počítače. Web Portál společnosti bude uživatelům stolních počítačů s Windows 10 poskytovat pokyny k registraci, které je provedou procesem přidání stolních počítačů s Windows 10 jako mobilní zařízení. Tato změna nebude mít vliv na už zaregistrované počítače, a [pokud chcete](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune), může stolní počítače s Windows 10 vaše organizace pořád spravovat přes agenta pro počítače.

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Vylepšení podpory správy mobilních aplikací pro selektivní vymazávání <!--581242-->
Koncoví uživatelé získají podrobnější pokyny o tom, jak získat zpět přístup k pracovním nebo školním datům v případě, že se data automaticky odebrala kvůli zásadám Doba v offline režimu před vymazáním dat.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Otevírání odkazů Portálu společnosti pro iOS v aplikaci <!--665954-->
Odkazy v aplikaci Portálu společnosti pro iOS, včetně těch, které vedou na dokumentaci a aplikace, se budou otevírat přímo v aplikaci Portál společnosti pomocí integrovaného zobrazení Safari. Tato aktualizace se bude dodávat odděleně od aktualizace služby v lednu.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Nová adresa serveru MDM pro zařízení s Windows <!--893007-->
Uživatelům Windows a Windows Phone se při pokusu o registraci zařízení zobrazí chyba, pokud zadají jako adresu serveru MDM __manage.microsoft.com__ (když se zobrazí výzva). Adresa serveru MDM se mění z __manage.microsoft.com__ na __enrollment.manage.microsoft.com__. Upozorněte uživatele, že mají jako adresu serveru MDM použít __enrollment.manage.microsoft.com__, když se jim zobrazí výzva při registraci zařízení s Windows nebo zařízení Windows Phone. Nastavení CNAME nevyžaduje žádné změny. Další informace o této změně najdete na webu [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nové uživatelské prostředí aplikace Portál společnosti pro Android <!--621622-->
Od března bude aplikace Portál společnosti pro Android odpovídat [specifikacím Material Design](https://material.io/guidelines/material-design/introduction.html) a získá tak modernější vzhled a chování. Toto vylepšené uživatelské prostředí zahrnuje:

* __Barvy__: Záhlaví karet můžou mít barvy podle vaší vlastní palety barev.
* __Rozhraní__: Byla aktualizována tlačítka Vybrané aplikace a Všechny aplikace na kartě Aplikace. Tlačítko Hledat je nyní plovoucí tlačítko akce.
* __Navigace__: V části Všechny aplikace se teď zobrazují karty Doporučené, Vše a Kategorie, které zjednodušují navigaci.
* __Služba__: Zlepšila se čitelnost karet Moje zařízení a Kontaktovat IT.

Obrázky před a po najdete na [stránce s aktualizacemi uživatelského rozhraní](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Přidružení více nástrojů pro správu k Windows Storu pro firmy <!--926135-->
Pokud k nasazování aplikací pro Windows Store pro firmy používáte více než jeden nástroj pro správu, mohli jste k Windows Storu pro firmy dříve přidružit jenom jeden z nich. Teď už můžete ke Storu přidružit více nástrojů pro správu, například Intune a Configuration Manager. Podrobnosti najdete v článku [Správa aplikací koupených ve Windows Storu pro firmy v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Co je nového ve veřejné verzi Preview prostředí pro správu Intune v Azure<!--736542-->

Na začátku kalendářního roku 2017 provedeme migraci celého našeho prostředí pro správu do Azure, což umožní výkonnou a integrovanou správu základních pracovních postupů EMS na moderní platformě pro služby, která je rozšiřitelná pomocí rozhraní Graph API.

Noví zkušební tenanti se začnou objevovat ve veřejné verzi Preview nového prostředí pro správu na webu Azure Portal tento měsíc. Funkce a parita se stávající konzolou Intune se ve verzi Preview budou zavádět postupně.

Prostředí pro správu na webu Azure Portal bude využívat nové funkce seskupování a cílení, které už byly oznámeny. Při migraci vašeho stávajícího tenanta do nového prostředí seskupování se provede také vaše migrace do verze Preview nového prostředí pro správu vašeho tenanta. Pokud si chcete otestovat nebo prohlédnout některé nové funkce ještě před migrací vašeho tenanta, zaregistrujte si nový zkušební účet Intune nebo se podívejte na [novou dokumentaci](https://docs.microsoft.com/intune-azure/introduction/whats-new).

Pokud máte jakékoli dotazy k časovému plánu migrace vašeho tenanta, kontaktujte náš tým pro migraci na adrese [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Novinky ve verzi Intune v Azure najdete [zde](https://docs.microsoft.com/intune-azure/introduction/whats-new).

### <a name="see-also"></a>Viz taky
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co je nového v Azure Preview](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Co je nového v uživatelském rozhraní Portálu společnosti](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Co je nového – archiv](whats-new-archive.md)

