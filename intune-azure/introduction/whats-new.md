---
title: "Co je nového v Microsoft Intune Preview"
titleSuffix: Intune Azure preview
description: "Zjistěte, jaké novinky přináší Intune Azure Preview."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: ffbc91edbdec4abbb5c3c9e28c3b44df03117492
ms.lasthandoff: 02/18/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Co je nového v Microsoft Intune Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Zde vás budeme informovat o přidávání nových funkcí do veřejné verze Preview.

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

## <a name="january-2017"></a>Leden 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Přiřazení obchodních aplikací bez ohledu na to, jestli jsou zařízení zaregistrovaná <!--748823-->
Teď můžete přiřazovat obchodní aplikace a aplikace ze Storu bez ohledu na to, jestli jsou zařízení zaregistrovaná do Intune, nebo ne. Pokud zařízení uživatele není v Intune zaregistrované, musí pro jeho instalaci přejít na web Portál společnosti, ne do aplikace Portál společnosti. Viz [Co je správa aplikací](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Řešení problému, kdy zařízení s iOSem nejsou aktivní nebo s nimi nemůže konzola pro správu komunikovat
Když zařízení uživatele ztratí kontakt s Intune, můžete uživateli poskytnout nový postup řešení potíží a pomoct mu tak znovu získat přístup k prostředkům společnosti. Viz [Zařízení nejsou aktivní nebo s nimi nemůže konzola pro správu komunikovat](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Prosinec 2016 (počáteční verze)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integrace se službami Telecom Expense Management na webu Azure Portal ve veřejné verzi Preview<!--747605-->
Ve verzi Preview teď začínáme na webu Azure Portal zavádět integraci se službami TEM (Telecom Expense Management) třetích stran. Pomocí Intune můžete uplatňovat limity na využívání domácích a roamingových dat. Tyto integrace začínáme zavádět s řešením [Saaswedo](http://www.saaswedo.com). Pokud chcete povolit tuto funkci ve zkušební verzi tenanta, [obraťte se prosím na podporu Microsoftu](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Nasazení a správa aplikací z obchodu na zařízeních s iOS, Androidem a Windows
- Nasazení a správa obchodních aplikací na zařízeních s iOS, Androidem a Windows
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

