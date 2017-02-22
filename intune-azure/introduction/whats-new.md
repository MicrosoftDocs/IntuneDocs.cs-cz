---
title: "Co je nového v Microsoft Intune Preview | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Zjistěte, jaké novinky přináší Intune Azure Preview."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/02/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e405363f9d0a89b1589b01d18ee8d2861b07ec60
ms.openlocfilehash: 70007f5501fba37964a0a54807c0e0f565510a74


---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Co je nového v Microsoft Intune Preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Zde vás budeme informovat o přidávání nových funkcí do veřejné verze Preview.

<!--## February 2017-->

<!--### Custom app categories <!--748805
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](/intune-azure/manage-apps/add-apps).-->

<!--### Display device categories <!--814654
You can now view the device category as a column in the device list. You can also edit the category from the properties section of the device properties blade.-->

## <a name="january-2017"></a>Leden 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Přiřazení obchodních aplikací bez ohledu na to, jestli jsou zařízení zaregistrovaná <!--748823-->
Teď můžete přiřazovat obchodní aplikace a aplikace ze Storu bez ohledu na to, jestli jsou zařízení zaregistrovaná do Intune, nebo ne. Pokud zařízení uživatele není v Intune zaregistrované, musí pro jeho instalaci přejít na web Portál společnosti, ne do aplikace Portál společnosti. Viz [Co je správa aplikací](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Řešení problému, kdy zařízení s iOSem nejsou aktivní nebo s nimi nemůže konzola správce komunikovat
Když zařízení uživatele ztratí kontakt s Intune, můžete uživateli poskytnout nový postup řešení potíží a pomoct mu tak znovu získat přístup k prostředkům společnosti. Viz [Zařízení nejsou aktivní nebo s nimi nemůže konzola správce komunikovat](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

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



<!--HONumber=Feb17_HO1-->


