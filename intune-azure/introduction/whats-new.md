---
title: "Co je nového v Microsoft Intune Preview"
titleSuffix: Intune Azure preview
description: "Zjistěte, jaké novinky přináší Intune Azure Preview."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/17/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 671d862c8d9a98e02f33d96cf6ceba712e740dec
ms.openlocfilehash: 586bdab54ee60ba8d620857ab3506aa27622d17a
ms.lasthandoff: 03/17/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Co je nového v Microsoft Intune Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Zde vás budeme informovat o přidávání nových funkcí do veřejné verze Preview.

> [!Note]
> Zavádíme změny uvedené na této stránce pro Azure Portal Preview. Změny ale nemusí být hned dostupné. Důvodem je způsob, jakým se služba Intune aktualizuje.  Několik součástí služby se musí aktualizovat postupně, než budou nové funkce portálu k dispozici. Tyto změny si budete moct prohlédnout, až budou v průběhu tohoto měsíce zavedené.

## <a name="march-2017"></a>Březen 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Podpora režimu ztráty pro iOS <!--431695-->

Pro zařízení s iOSem 9.3 nebo novějším je v Intune přidaná podpora pro **režim ztráty**. Teď máte možnost zařízení uzamknout, aby se nedalo používat, a na jeho zamykací obrazovce zobrazit zprávu a kontaktní telefonní číslo.

Koncový uživatel nebude moct zařízení odemknout, dokud správce režim ztráty nevypne. Když je režim ztráty zapnutý, můžete pomocí akce **Najít zařízení** zobrazit zeměpisnou polohu zařízení na mapě v konzole Intune.

Musí se jednat o zařízení s iOSem ve vlastnictví firmy, které je zaregistrované prostřednictvím programu DEP a je v režimu dohledu.

Další informace najdete v článku [Co je správa zařízení v Microsoft Intune](/intune-azure/manage-devices/what-is).

### <a name="improvements-to-device-actions-report---677150--"></a>Vylepšení sestavy Akce zařízení <!--677150-->

Sestavu Akce zařízení jsme vylepšili z hlediska výkonu. Tuto sestavu teď navíc můžete filtrovat podle stavu. Filtrováním sestavy můžete například zobrazit jen akce zařízení, které byly dokončeny.

### <a name="actions-for-non-compliance---730266--"></a>Akce při nedodržení předpisů <!--730266-->

**Akce při nedodržení předpisů** je nová funkce zásad dodržování předpisů, která umožňuje provádět akce na zařízeních, které nedodržují předpisy. Můžete zadat jednu nebo více akcí a určit časové období, během kterého se tyto akce musí provést. Třeba uživatelům zařízení, která nedodržují předpisy, můžete poslat e-mailem oznámení, hned jak zařízení přestane předpisy dodržovat. Nebo pomocí podmíněného přístupu můžete takovým zařízením zablokovat přístup k prostředkům společnosti po 3denním období odkladu.

### <a name="custom-app-categories---748805--"></a>Vlastní kategorie aplikací <!--748805-->

Teď můžete vytvářet, upravovat a přiřazovat kategorie pro aplikace, které přidáte do Intune. V současné době se kategorie dají zadávat jenom v angličtině.
Přečtěte si téma [Jak přidat aplikaci do Intune](/intune-azure/manage-apps/add-apps).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Přiřazování obchodních aplikací uživatelům s neregistrovanými zařízeními <!--748823-->

Obchodní aplikace a aplikace z obchodu teď můžete přiřazovat bez ohledu na to, jestli zařízení jsou nebo nejsou zaregistrovaná do Intune. Pokud zařízení uživatele není zaregistrované v Intune, musí kvůli jeho instalaci přejít na web Portál společnosti, ne do aplikace Portál společnosti.

### <a name="new-compliance-reports---846671--"></a>Nové sestavy dodržování předpisů <!--846671-->

Teď máte k dispozici sestavy dodržování předpisů, ze kterých zjistíte, nakolik zařízení ve firmě dodržují předpisy, a které vám pomůžou rychle vyřešit problémy uživatelů související s dodržováním předpisů. Můžete zjistit:

- Celkový stav dodržování předpisů zařízeními
- Stav dodržování předpisů pro individuální nastavení
- Stav dodržování předpisů pro individuální zásadu

Tyto sestavy vám také umožňují přejít až k individuálnímu zařízení a zobrazit konkrétní nastavení a zásady, které mají na toto zařízení vliv.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Přímý přístup ke scénářům registrace Apple <!--951869-->

U účtů Intune vytvořených po lednu 2017 umožňuje Intune přímý přístup ke scénářům registrace Apple pomocí úlohy Registrovat zařízení na portálu Azure Preview. Náhled na registraci Apple byl předtím přístupný přes odkazy na portálu klasické služby Intune. Zpřístupnění těchto funkcí v Azure bude u účtů Intune vytvořených před lednem 2017 vyžadovat jednorázovou migraci. Plán této migrace zatím nebyl oznámen, podrobnosti ale budou zpřístupněny co nejdříve. Pokud váš existující účet nemá k tomuto náhledu přístup, k otestování tohoto nového prostředí důrazně doporučujeme vytvořit zkušební účet.


## <a name="february-2017"></a>Únor 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Možnost omezení registrace mobilních zařízení <!--747600, 795782-->
Intune přidává nová omezení registrace řídící to, které platformy mobilních zařízení se mohou zaregistrovat. Intune odděluje platformy mobilních zařízení, jako je iOS, macOS, Android, Windows a Windows Mobile.

* Omezení registrace mobilních zařízení neomezuje registraci klienta pro počítače.  
* Pouze pro iOS a Android existuje další možnost blokování registrace osobních zařízení.

Pokud správce IT neoznačí nová zařízení jako vlastněná podnikem, Intune všechna nová zařízení označí jako osobní. Podrobnosti najdete v [tomto článku](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Zobrazení všech akcí na spravovaných zařízeních <!--677150-->
V nové sestavě __Akce zařízení__ se zobrazí, kdo provedl vzdálené akce, jako je obnovení továrního nastavení zařízení, a dále stav dané akce. Viz [Co je správa zařízení?](https://docs.microsoft.com/intune-azure/manage-devices/what-is)

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Nespravovaná zařízení mají přístup k přiřazeným aplikacím <!--664691-->
Jako součást změn v návrhu na webu Portál společnosti budou moci uživatelé iOSu a Androidu na svoje nespravovaná zařízení instalovat aplikace, které mají přiřazené jako dostupné bez registrace. S použitím přihlašovacích údajů pro Intune se budou moct uživatelé přihlásit na web Portál společnosti a zobrazit seznam aplikací, které mají přiřazené. Balíčky aplikací, které jsou dostupné bez registrace, jsou k dispozici ke stažení prostřednictvím webu Portál společnosti. Aplikace, které vyžadují registraci, aby je bylo možné nainstalovat, nejsou touto změnou ovlivněny, protože když budou chtít tyto aplikace uživatelé nainstalovat, zobrazí se jim výzva k registraci.

### <a name="custom-app-categories---748805--"></a>Vlastní kategorie aplikací <!--748805-->
Teď můžete vytvářet, upravovat a přiřazovat kategorie pro aplikace, které přidáte do Intune. V současné době se kategorie dají zadávat jenom v angličtině.
Přečtěte si téma [Jak přidat aplikaci do Intune](/intune-azure/manage-apps/add-apps).

### <a name="display-device-categories---814654--"></a>Zobrazení kategorií zařízení <!--814654-->
Kategorie zařízení teď můžete zobrazit jako sloupec v seznamu zařízení. Kategorii můžete upravit také v části vlastností v okně vlastností zařízení. Přečtěte si téma [Jak přidat aplikaci do Intune](/intune-azure/manage-apps/add-apps).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Konfigurace nastavení služby Windows Update pro firmy <!--776716-->

Windows jako služba je nový způsob poskytování aktualizací pro Windows 10. Od verze Windows 10 budou všechny nové aktualizace funkcí a aktualizace pro zvýšení kvality zahrnovat obsah všech předchozích aktualizací. To znamená, že pokud si nainstalujete nejnovější aktualizaci, máte jistotu, že jsou vaše zařízení s Windows 10 zcela aktuální. Na rozdíl od předchozích verzí Windows je teď nutné nainstalovat celou aktualizaci (a ne jenom její část).

Pomocí služby Windows Update pro firmy můžete zjednodušit správu aktualizací, abyste nemuseli schvalovat jednotlivé aktualizace pro skupiny zařízení. Můžete nakonfigurovat strategii zavádění aktualizací, abyste měli pod kontrolou řízení rizik ve vašem prostředí, a služba Windows Update zajistí, aby se aktualizace nainstalovaly ve správný čas. Prostřednictvím Microsoft Intune můžete na zařízeních nakonfigurovat nastavení aktualizací a pozdržet instalaci aktualizací. V Intune nejsou uložené samotné aktualizace, ale jenom přiřazení zásad aktualizací. Zařízení získávají aktualizace přímo ze služby Windows Update. Pomocí Intune můžete nakonfigurovat a spravovat **aktualizační kanály Windows 10**. Aktualizační kanál obsahuje skupinu nastavení, která konfigurují, kdy a jak se budou aktualizace Windows 10 instalovat. Podrobnosti najdete v článku [Konfigurace nastavení služby Windows Update pro firmy](/intune-azure/configure-devices/how-to-configure-windows-update-for-business).

## <a name="january-2017"></a>Leden 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Přiřazení obchodních aplikací bez ohledu na to, jestli jsou zařízení zaregistrovaná <!--748823-->
Teď můžete přiřazovat obchodní aplikace a aplikace ze Storu bez ohledu na to, jestli jsou zařízení zaregistrovaná do Intune, nebo ne. Pokud zařízení uživatele není v Intune zaregistrované, musí pro jeho instalaci přejít na web Portál společnosti, ne do aplikace Portál společnosti. Viz [Co je správa aplikací](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Řešení problému, kdy zařízení s iOSem nejsou aktivní nebo s nimi nemůže konzola pro správu komunikovat
Když zařízení uživatele ztratí kontakt s Intune, můžete uživateli poskytnout nový postup řešení potíží a pomoct mu tak znovu získat přístup k prostředkům společnosti. Viz [Zařízení nejsou aktivní nebo s nimi nemůže konzola pro správu komunikovat](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Prosinec 2016 (počáteční verze)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integrace se službami Telecom Expense Management na webu Azure Portal ve veřejné verzi Preview<!--747605-->
Ve verzi Preview teď začínáme na webu Azure Portal zavádět integraci se službami TEM (Telecom Expense Management) třetích stran. Pomocí Intune můžete uplatňovat limity na využívání domácích a roamingových dat. Tyto integrace začínáme zavádět s řešením [Saaswedo](http://www.saaswedo.com). Pokud chcete povolit tuto funkci ve zkušební verzi tenanta, [obraťte se prosím na podporu Microsoftu](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Nasazení a správa aplikací z obchodu na zařízeních s iOSem, Androidem a Windows
- Nasazení a správa obchodních aplikací na zařízeních s iOSem, Androidem a Windows
- Nasazení a správa hromadně zakoupených aplikací na zařízeních s iOSem a Windows
- Nasazení a správa webových aplikací pro zařízení s Androidem, iOSem a Windows
- Konfigurační profily spravovaných aplikací iOS
- Konfigurace zásad ochrany aplikací a nasazení obchodních aplikací do zařízení, která nejsou zaregistrovaná v Intune
- Profily sítě VPN, sítě VPN pro jednotlivé aplikace, profily Wi-Fi, e-mailu a certifikátu
- Zásady dodržování předpisů
- Podmíněný přístup pro Azure AD
- Podmíněný přístup pro místní Exchange
- Registrace zařízení
- Řízení přístupu na základě role

## <a name="deprecated-features-in-the-azure-portal"></a>Zastaralé funkce na portálu Azure Portal

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Podpora kontroly hardwarových identifikátorů po řádcích
Azure Portal nepodporuje kontrolu hardwarových identifikátorů pro čísla IMEI a sériová čísla Apple po řádcích. V konzole Intune Classic můžete podrobnosti naimportovat z textového souboru s oddělovači (.csv) a přepsat existující podrobnosti individuálních hardwarových identifikátorů. Azure Portal nabízí jednu optimalizovanou možnost, která automaticky přepíše podrobnosti všech hardwarových identifikátorů a ignoruje nové podrobnosti existujících identifikátorů.

#### <a name="how-this-affects-you"></a>Jak se vás tato změna týká
Na portálu Azure Portal nebudete moci řádek po řádku rozhodnout, která čísla IMEI (International Mobile Equipment Identity) zařízení se mají aktualizovat. Konzola Intune Classic bude tuto funkci nadále podporovat.

#### <a name="how-to-get-ready-for-this-change"></a>Jak se na tuto změnu připravit
Tuto informaci vám oznamujeme dopředu, abyste na tuto změnu mohli správce podpory upozornit, pokud se vás týká. Tato změna se bude krýt s přechodem na portál Azure Portal, který se očekává v první polovině roku 2017.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Podpora výchozích profilů registrace podnikových zařízení v programu Apple DEP
Azure Portal nepodporuje „výchozí“ profil registrace podnikového zařízení pro sériová čísla zařízení programu Apple DEP (Device Enrollment Program). Tato funkce, která je dostupná v konzole Intune Classic, se vyřazuje, aby nedocházelo k neúmyslně přiřazeným profilům. K sériovým číslům synchronizovaným z účtu Apple DEP nebude na portálu Azure Portal zpočátku přiřazený žádný profil registrace podnikového zařízení.

#### <a name="how-this-affects-you"></a>Jak se vás tato změna týká
Na portálu Azure Portal nebudete moci nastavit zásadu výchozího profilu pro všechna zařízení Apple. Konzola Intune Classic bude tuto funkci nadále podporovat.

#### <a name="how-to-get-ready-for-this-change"></a>Jak se na tuto změnu připravit
Tuto informaci vám oznamujeme dopředu, abyste na tuto změnu mohli správce podpory upozornit, pokud se vás týká. Tato změna se bude krýt s přechodem na portál Azure Portal, který se očekává v první polovině roku 2017.

