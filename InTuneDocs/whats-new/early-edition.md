---
title: "Časná edice | Dokumentace Microsoftu"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 68c7a23dc8769330c14f74e6aebb07eeb188a991
ms.openlocfilehash: 4bc9a2799bcce035c6847b7b2884ee24160426da


---


# <a name="the-early-edition-for-microsoft-intune---february-2017"></a>Časná edice pro Microsoft Intune – únor 2017

**Časná edice** poskytuje seznam funkcí, které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány na základě smlouvy o utajení (NDA) ve velmi omezené míře a mohou podléhat změnám. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a mohou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moci zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se prosím na příslušný kontakt (Intune/PM).

Tato stránka se pravidelně aktualizuje. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.

> [!Note]
> Následující změny v Intune jsou ve vývoji. Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nové funkce

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizace webu Portál společnosti <!--753980-->
Web Portál společnosti bude podporovat aplikace zaměřené na uživatele, kteří nemají spravovaná zařízení. Tento web bude podobně jako ostatní produkty a služby Microsoftu používat nové kontrastní barevné schéma, dynamické ilustrace a „hamburgerovou“ nabídku ![Obrázek hamburgerové nabídky webu Portál společnosti, která je teď přidaná v levém horním rohu webu Portál společnosti](./media/CP_hamburger_menu.png), která bude obsahovat kontaktní údaje helpdesku a informace o existujících spravovaných zařízeních. Cílová stránka bude mít nové uspořádání, které zdůrazní aplikace dostupné uživatelům – s karusely pro Vybrané a Nedávno aktualizované aplikace. Obrázky před a po najdete na [stránce s aktualizacemi uživatelského rozhraní](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Nové prostředí s asistencí pro portál společnosti s Windows 10 <!--713927-->
Od března bude portál společnosti pro Windows 10 obsahovat návod s pokyny Intune pro zařízení, která nejsou identifikovaná nebo zaregistrovaná. Nové prostředí obsahuje podrobné pokyny přizpůsobené buildu uživatele Windows 10, které provedou uživatele registrací AAD (která je nutná k identifikaci pro funkce podmíněného přístupu) a registraci MDM (která je nutná pro funkce správy zařízení). Prostředí s asistencí bude přístupné z domovské stránky portálu společnosti a je volitelné. Uživatelé budou moct nadále aplikaci používat, pokud se nezaregistrují, ale některé funkce můžou být omezené.

###

## <a name="notices"></a>Sdělení

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Migrace skupin nevyžadují pro zařízení s iOSem žádné aktualizace skupin ani zásad <!--898837-->
Pro každou skupinu zařízení s Intune předem přiřazenou profilem registrace podnikového zařízení se během migrace do skupin zařízení Azure Active Directory vytvoří odpovídající dynamická skupina zařízení v adresáři AAD založená na názvu profilu registrace podnikového zařízení. Zajistí se tak, že se budou zařízení během registrace automaticky seskupovat a přijmou stejné zásady a aplikace jako původní skupina Intune.

Jakmile tenant zahájí proces migrace pro seskupování a zacílení, vytvoří Intune automaticky dynamickou skupinu AAD tak, aby odpovídala skupině Intune, na kterou je zacílený profil registrace podnikového zařízení. Pokud správce Intune odstraní cílovou skupinu Intune, neodstraní se odpovídající dynamická skupina AAD. Smažou se členové skupiny a dynamický dotaz, ale skupina samotná zůstane, dokud ji správce IT neodebere přes portál AAD.

Podobně, pokud správce IT změní to, která skupina Intune je cílem profilu registrace podnikového zařízení, vytvoří Intune novou dynamickou skupinu odrážející nové přiřazení profilu, ale neodebere se dynamická skupina vytvořená pro staré přiřazení.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Nová adresa serveru MDM pro zařízení s Windows <!--893007-->
Uživatelům Windows a Windows Phone se při pokusu o registraci zařízení zobrazí chyba, pokud zadají jako adresu serveru MDM __manage.microsoft.com__ (když se zobrazí výzva). Adresa serveru MDM se mění z __manage.microsoft.com__ na __enrollment.manage.microsoft.com__. Upozorněte uživatele, že mají jako adresu serveru MDM použít __enrollment.manage.microsoft.com__, když se jim zobrazí výzva při registraci zařízení s Windows nebo zařízení Windows Phone. Tato aktualizace bude vyžadovat, aby byl každý záznam CNAME ve službě DNS, který přesměrovává z adresy __EnterpriseEnrollment.contoso.com__ na adresu __manage.microsoft.com__, nahrazen záznamem CNAME ve službě DNS, který přesměrovává z adresy __EnterpriseEnrollment.contoso.com__ na adresu __EnterpriseEnrollment-s.manage.microsoft.com__. Další informace o této změně najdete na webu [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nové uživatelské prostředí aplikace Portál společnosti pro Android <!--621622-->
Od března bude aplikace Portál společnosti pro Android odpovídat [specifikacím Material Design](https://material.io/guidelines/material-design/introduction.html) a získá tak modernější vzhled a chování. Toto vylepšené uživatelské prostředí zahrnuje:

* __Barvy__: Záhlaví karet můžou mít barvy podle vaší vlastní palety barev.
* __Rozhraní__: Byla aktualizována tlačítka Vybrané aplikace a Všechny aplikace na kartě Aplikace. Tlačítko Hledat je nyní plovoucí tlačítko akce.
* __Navigace__: V části Všechny aplikace se teď zobrazují karty Doporučené, Vše a Kategorie, které zjednodušují navigaci.
* __Služba__: Zlepšila se čitelnost karet Moje zařízení a Kontaktovat IT.

Obrázky před a po najdete na [stránce s aktualizacemi uživatelského rozhraní](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Přidružení více nástrojů pro správu k Windows Storu pro firmy <!--926135-->
Pokud k nasazování aplikací pro Windows Store pro firmy používáte více než jeden nástroj pro správu, mohli jste k Windows Storu pro firmy dříve přidružit jenom jeden z nich. Teď už můžete ke Storu přidružit více nástrojů pro správu, například Intune a Configuration Manager. Podrobnosti najdete v článku [Správa aplikací koupených ve Windows Storu pro firmy v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Veřejná verze Preview nového prostředí pro správu Intune v Azure <!--736542-->

Na začátku kalendářního roku 2017 provedeme migraci celého našeho prostředí pro správu do Azure, což umožní výkonnou a integrovanou správu základních pracovních postupů EMS na moderní platformě pro služby, která je rozšiřitelná pomocí rozhraní Graph API.

Noví zkušební tenanti se začnou objevovat ve veřejné verzi Preview nového prostředí pro správu na webu Azure Portal tento měsíc. Funkce a parita se stávající konzolou Intune se ve verzi Preview budou zavádět postupně.

Prostředí pro správu na webu Azure Portal bude využívat nové funkce seskupování a cílení, které už byly oznámeny. Při migraci vašeho stávajícího tenanta do nového prostředí seskupování se provede také vaše migrace do verze Preview nového prostředí pro správu vašeho tenanta. Pokud si chcete otestovat nebo prohlédnout některé nové funkce ještě před migrací vašeho tenanta, zaregistrujte si nový zkušební účet Intune nebo se podívejte na [novou dokumentaci](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune).

Pokud máte jakékoli dotazy k časovému plánu migrace vašeho tenanta, kontaktujte náš tým pro migraci na adrese [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="february-2017"></a>Únor 2017

#### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Možnost omezení registrace mobilních zařízení <!--747600, 795782-->
Intune přidává nová omezení registrace řídící to, které platformy mobilních zařízení se mohou zaregistrovat. Intune odděluje platformy mobilních zařízení, jako je iOS, macOS, Android, Windows a Windows Mobile.

* Omezení registrace mobilních zařízení neomezuje registraci klienta pro počítače.  
* Pouze pro iOS a Android existuje další možnost blokování registrace osobních zařízení.

Pokud správce IT neoznačí nová zařízení jako vlastněná podnikem, Intune všechna nová zařízení označí jako osobní. Podrobnosti najdete v [tomto článku](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

#### <a name="view-all-actions-on-managed-devices---677150--"></a>Zobrazení všech akcí na spravovaných zařízeních <!--677150-->
V nové sestavě __Akce zařízení__ se zobrazí, kdo provedl vzdálené akce, jako je obnovení továrního nastavení zařízení, a dále stav dané akce.

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Nespravovaná zařízení mají přístup k přiřazeným aplikacím <!--664691-->
Jako součást změn v návrhu na webu Portál společnosti budou moci uživatelé iOSu a Androidu na svoje nespravovaná zařízení instalovat aplikace, které mají přiřazené jako dostupné bez registrace. S použitím přihlašovacích údajů pro Intune se budou moct uživatelé přihlásit na web Portál společnosti a zobrazit seznam aplikací, které mají přiřazené. Balíčky aplikací, které jsou dostupné bez registrace, jsou k dispozici ke stažení prostřednictvím webu Portál společnosti. Aplikace, které vyžadují registraci, aby je bylo možné nainstalovat, nejsou touto změnou ovlivněny, protože když budou chtít tyto aplikace uživatelé nainstalovat, zobrazí se jim výzva k registraci.

#### <a name="custom-app-categories---748805--"></a>Vlastní kategorie aplikací <!--748805-->
Teď můžete vytvářet, upravovat a přiřazovat kategorie pro aplikace, které přidáte do Intune. V současné době se kategorie dají zadávat jenom v angličtině.
Přečtěte si téma [Jak přidat aplikaci do Intune](/intune-azure/manage-apps/add-apps).

#### <a name="display-device-categories---814654--"></a>Zobrazení kategorií zařízení <!--814654-->
Kategorie zařízení teď můžete zobrazit jako sloupec v seznamu zařízení. Kategorii můžete upravit také v části vlastností v okně vlastností zařízení.

### <a name="january-2017"></a>Leden 2017

#### <a name="custom-app-categories---748805--"></a>Vlastní kategorie aplikací <!--748805-->
Teď můžete vytvářet, upravovat a přiřazovat kategorie pro aplikace, které přidáte do Intune. V současné době se kategorie dají zadávat jenom v angličtině.

#### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748803--"></a>Přiřazení obchodních aplikací bez ohledu na to, jestli jsou zařízení zaregistrovaná <!--748803-->
Teď můžete přiřazovat obchodní aplikace a aplikace ze Storu bez ohledu na to, jestli jsou zařízení zaregistrovaná do Intune, nebo ne. Pokud zařízení uživatele není v Intune zaregistrované, musí pro jeho instalaci přejít na web Portál společnosti, ne do aplikace Portál společnosti.

### <a name="december-2016"></a>Prosinec 2016

#### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integrace se službami Telecom Expense Management na webu Azure Portal ve veřejné verzi Preview<!--747605-->
Ve verzi Preview teď začínáme na webu Azure Portal zavádět integraci se službami TEM (Telecom Expense Management) třetích stran. Pomocí Intune můžete uplatňovat limity na využívání domácích a roamingových dat. Tyto integrace začínáme zavádět s řešením [Saaswedo](http://www.saaswedo.com). Pokud chcete povolit tuto funkci ve zkušební verzi tenanta, [obraťte se prosím na podporu Microsoftu](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="see-also"></a>Související témata
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Feb17_HO2-->


