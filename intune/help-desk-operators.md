---
title: Portál helpdesku pro řešení potíží
titlesuffix: Microsoft Intune
description: Pracovníci helpdesku používají portál pro řešení potíží, aby pomohli uživatelům s řešením technických problémů.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 239c8d5dc4143ba91c78b9b5c502c7a20b101417
ms.sourcegitcommit: 7afa90264a2098453885be3d37655ae1a32ca67d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/26/2018
ms.locfileid: "47229071"
---
# <a name="use-the-troubleshooting-portal-to-help-users-at-your-company"></a>Použití portálu pro řešení potíží k poskytování pomoci uživatelům ve vaší společnosti

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Portál pro řešení potíží umožňuje operátorům helpdesku a správcům Intune zobrazit informace o uživatelích a použít je k řešení jejich žádostí o pomoc. Organizace, které zahrnují helpdesk, můžou skupině uživatelů přiřadit **operátora helpdesku**. Role operátora helpdesku může používat podokno **Řešení potíží**.

V podokně **Řešení potíží** se zobrazují také problémy s registrací uživatelů. Podrobnosti o problému a navrhované nápravné kroky můžou správcům a pracovníkům technické podpory pomoct problém vyřešit. Některé problémy s registrací nejsou zaznamenané a k některým chybám nemusí návrhy k odstranění problému existovat.

Pokyny k přidání role operátora helpdesku najdete v článku [Řízení správy na základě rolí (RBAC) s Intune](/intune/role-based-access-control)

Když uživatel kontaktuje podporu ohledně technického problému s Intune, zadá operátor helpdesku jméno uživatele. Intune zobrazí užitečná data, která vám můžou pomoct s řešením řady problémů úrovně 1 včetně těchto:

- Stav uživatele
- Přiřazení
- Problémy se shodou
- Zařízení neodpovídá
- Zařízení nedokáže získat nastavení sítě VPN nebo Wi-Fi
- Instalace aplikace se nezdařila

## <a name="to-review-troubleshooting-details"></a>Kontrola podrobností o řešení potíží

Zvolením možnosti **Vybrat uživatele** v podokně pro řešení potíží zobrazíte informace o uživateli. Informace o uživateli vám mohou pomoci porozumět aktuálnímu stavu uživatelů a jejich zařízení.  

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Řešení potíží**.
4. Klikněte na **Vybrat** a vyberte uživatele, pro kterého chcete řešit potíže.
5. Vyberte uživatele zadáním jména nebo e-mailové adresy. Klikněte na **Vybrat**. Informace o řešení potíží pro uživatele se zobrazí v podokně Řešení potíží. Informace jsou vysvětlené v následující tabulce.

> [!Note]  
> Do podokna **řešení potíží** se dostanete také tak, že v prohlížeči přejdete na adresu: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="areas-of-troubleshooting-dashboard"></a>Oblasti řídicího panelu pro řešení potíží

V podokně **Řešení potíží** můžete zkontrolovat informace o uživateli.

![](/intune/media/troubleshooting-dash.png)

| Oblast | Název | Popis |
| ---  | ---  | ---         |
| 1.   | Stav účtu  | Zobrazuje stav aktuálního tenanta Intune, například **Aktivní** nebo **Neaktivní**.       |
| 2.   | Výběr uživatele  | Jméno aktuálně vybraného uživatele. Kliknutím na **Změnit uživatele** zvolíte nového uživatele.       |
| 3.   | Stav uživatele  | Zobrazí stav uživatelovy licence Intune, počet zařízení, dodržování předpisů u každého zařízení, počet aplikací a dodržování předpisů u aplikací.       |
| 4.   | Údaje uživatele  | Pomocí seznamu můžete vybrat podrobnosti, které chcete v podokně zkontrolovat. <br>Můžete vybrat: <ul><li>Klientské aplikace<li>Zásady dodržování předpisů<li> Zásady konfigurace<li>Zásady ochrany aplikace <li>Omezení registrace</ul>      |
| 5.   | Členství ve skupině  | Zobrazí aktuální skupiny, ve kterých je vybraný uživatel členem.       |

## <a name="client-apps-reference"></a>Informace o klientských aplikacích

Aplikace, které používají zařízení
- spravovaná přes Intune a Azure Active Directory (AD) 
- vlastněná uživateli spravovanými přes Intune a Azure Active Directory (AD)

### <a name="properties"></a>Vlastnosti

Vlastnosti klientských aplikací

| Vlastnost      | Popis                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Název          | Název aplikace                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Operační systém            | Operační systém nainstalovaný v zařízení                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Typ          | Můžete zvolit typ přiřazení pro každou aplikaci.  <br> **K dispozici** – Uživatelé instalují aplikaci z aplikace nebo webu Portál společnosti.  <br> **Nelze použít** – Aplikace není nainstalovaná nebo se na Portálu společnosti nezobrazuje. <br> **Odinstalovat** – Aplikace se odinstaluje ze zařízení ve vybraných skupinách.  <br> **K dispozici s registrací i bez ní** – Přiřadí tuto aplikaci do skupin uživatelů, jejichž zařízení nejsou zaregistrovaná v Intune. |
| Datum poslední změny | Název typu zařízení                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### <a name="devices"></a>Zařízení

Zařízení spravovaná pomocí Intune nebo uživateli, kteří jsou spravovaní pomocí Intune nebo Azure AD.

| Vlastnost           | Popis                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Název zařízení        | Název typu zařízení                                                                                                     |
| Spravuje         | Časové razítko změny zásad                                                                                              |
| Typ připojení ke službě Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Vlastnictví          | Typ vlastnictví zařízení (**Společnost**, **Osobní** nebo **Neznámé**)                                               |
| Vyhovuje Intune   | Název typu zařízení                                                                                                     |
| Vyhovuje Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Operační systém                 | Operační systém nainstalovaný v zařízení                                                                                       |
| Verze operačního systému         | Číslo verze operačního systému zařízení.                                                                                  |
| Poslední vrácení se změnami      | Název typu zařízení                                                                                                     |

### <a name="app-protection-status"></a>Stav ochrany aplikace

Pro mobilní aplikace, které se integrují s technologiemi Enterprise Mobility Solution (EMS), jsou k dispozici zásady ochrany aplikací. Tyto zásady poskytují základ ochrany dat společnosti po jejich stažení do mobilních aplikací, včetně mobilních aplikací Office. 

| Vlastnost    | Popis                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Stav      | Typ vlastnictví zařízení (**Společnost**, **Osobní** nebo **Neznámé**) |
| Název aplikace    | Název aplikace                                                           |
| Název zařízení | Název typu zařízení                                                       |
| Typ zařízení | Název typu zařízení                                                       |
| Zásady    | Typ vlastnictví zařízení (**Společnost**, **Osobní** nebo **Neznámé**) |
| Poslední synchronizace   | Časové razítko poslední synchronizace zařízení s Intune.                   |

## <a name="app-protection-policies-reference"></a>Informace o zásadách ochrany aplikací

Pro mobilní aplikace, které se integrují s technologiemi EMS, jsou k dispozici zásady ochrany aplikací. Tyto zásady poskytují základ ochrany dat společnosti po jejich stažení do mobilních aplikací, včetně mobilních aplikací Office. 

### <a name="properties"></a>Vlastnosti

Tabulka shrnuje stav zásad ochrany aplikací pro zařízení spravovaná pomocí Intune.

| Vlastnost    | Popis                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Název        | Název aplikace                                                                                                        |
| Nasazeno    | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Platforma    | Typ vlastnictví zařízení (**Společnost**, **Osobní** nebo **Neznámé**)                                               |
| Registrace  | Název typu zařízení                                                                                                     |
| Poslední aktualizace | Časové razítko změny zásad                                                                                              |

### <a name="devices"></a>Zařízení

Zařízení spravovaná pomocí Intune nebo uživateli, kteří jsou spravovaní pomocí Intune nebo Azure AD.

| Vlastnost           | Text                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Název zařízení        | Název typu zařízení                                                                                                     |
| Spravuje         | Časové razítko změny zásad                                                                                              |
| Typ připojení ke službě Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Vlastnictví          | Typ vlastnictví zařízení (**Společnost**, **Osobní** nebo **Neznámé**)                                               |
| Vyhovuje Intune   | Název typu zařízení                                                                                                     |
| Vyhovuje Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Vyhovuje Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Operační systém                 | Operační systém nainstalovaný v zařízení                                                                                       |
| Verze operačního systému         | Číslo verze operačního systému zařízení.                                                                                  |
| Poslední vrácení se změnami      | Název typu zařízení                                                                                                     |

## <a name="compliance-policies-reference"></a>Informace o zásadách dodržování předpisů

Tyto zásady zajišťují, že zařízení používaná k přístupu k firemním aplikacím a datům dodržují určitá pravidla, například že přístup k zařízení je chráněný kódem PIN a data ukládaná do zařízení jsou šifrována.

### <a name="properties"></a>Vlastnosti

Vlastnosti zásad dodržování předpisů.

| Vlastnost      | Popis                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Přiřazení    | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Název          | Název aplikace                                                                                                        |
| Operační systém            | Operační systém nainstalovaný v zařízení                                                                                       |
| Typ zásad   | Typ vlastnictví zařízení (**Společnost**, **Osobní** a **Neznámé**)                                               |
| Datum poslední změny | Název typu zařízení                                                                                                     |

### <a name="devices"></a>Zařízení

Zařízení spravovaná pomocí Intune nebo uživateli, kteří jsou spravovaní pomocí Intune nebo Azure AD.

| Vlastnost           | Popis                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Název zařízení        | Název typu zařízení                                                                                                     |
| Spravuje         | Časové razítko změny zásad                                                                                              |
| Typ připojení ke službě Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Vlastnictví          | Typ vlastnictví zařízení (**Společnost**, **Osobní** a **Neznámé**)                                               |
| Vyhovuje Intune   | Název typu zařízení                                                                                                     |
| Vyhovuje Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Operační systém                 | Operační systém nainstalovaný v zařízení                                                                                       |
| Verze operačního systému         | Číslo verze operačního systému zařízení.                                                                                  |
| Poslední vrácení se změnami      | Název typu zařízení                                                                                                     |

### <a name="app-protection-policies"></a>Zásady ochrany aplikace

Pro mobilní aplikace, které se integrují s technologiemi EMS, jsou k dispozici zásady ochrany aplikací. Tyto zásady poskytují základ ochrany dat společnosti po jejich stažení do mobilních aplikací, včetně mobilních aplikací Office. 

| Vlastnost    | Popis                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Stav      | Typ vlastnictví zařízení (**Společnost**, **Osobní** nebo **Neznámé**) |
| Název aplikace    | Název aplikace                                                           |
| Název zařízení | Název typu zařízení                                                       |
| Typ zařízení | Název typu zařízení                                                       |
| Zásady    | Typ vlastnictví zařízení (**Společnost**, **Osobní** nebo **Neznámé**) |
| Poslední synchronizace   | Časové razítko poslední synchronizace zařízení s Intune.                   |

## <a name="configuration-policies-reference"></a>Informace o zásadách konfigurace

Pro mobilní aplikace se specifickou konfigurací podle dodavatele jsou k dispozici zásady konfigurace aplikací. 

### <a name="properties"></a>Vlastnosti

Vlastnosti zásad konfigurace.

| Vlastnost      | Popis                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Přiřazení    | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Název          | Název aplikace                                                                                                        |
| Operační systém            | Operační systém nainstalovaný v zařízení                                                                                       |
| Typ zásad   | Typ vlastnictví zařízení (**Společnost**, **Osobní** nebo **Neznámé**)                                               |
| Datum poslední změny | Název typu zařízení                                                                                                     |

### <a name="devices"></a>Zařízení

Zařízení spravovaná pomocí Intune nebo uživateli, kteří jsou spravovaní pomocí Intune nebo Azure AD.

| Vlastnost           | Popis                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Název zařízení        | Název typu zařízení                                                                                                     |
| Spravuje         | Časové razítko změny zásad                                                                                              |
| Typ připojení ke službě Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Vlastnictví          | Typ vlastnictví zařízení (**Společnost**, **Osobní** nebo **Neznámé**)                                               |
| Vyhovuje Intune   | Název typu zařízení                                                                                                     |
| Vyhovuje Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Operační systém                 | Operační systém nainstalovaný v zařízení                                                                                       |
| Verze operačního systému         | Číslo verze operačního systému zařízení.                                                                                  |
| Poslední vrácení se změnami      | Název typu zařízení                                                                                                     |


### <a name="app-protection-policies"></a>Zásady ochrany aplikace

Pro mobilní aplikace, které se integrují s technologiemi EMS, jsou k dispozici zásady ochrany aplikací. Tyto zásady poskytují základ ochrany dat společnosti po jejich stažení do mobilních aplikací, včetně mobilních aplikací Office. 

| Vlastnost    | Popis                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Stav      | Typ vlastnictví zařízení (**Společnost**, **Osobní** nebo **Neznámé**) |
| Název aplikace    | Název aplikace                                                           |
| Název zařízení | Název typu zařízení                                                       |
| Typ zařízení | Název typu zařízení                                                       |
| Zásady    | Typ vlastnictví zařízení (**Společnost**, **Osobní** nebo **Neznámé**) |
| Poslední synchronizace   | Časové razítko poslední synchronizace zařízení s Intune.                   |

## <a name="enrollment-failure-reference"></a>Informace o neúspěšných registracích

Tabulka Neúspěšné registrace obsahuje neúspěšné pokusy o registraci. Zařízení uvedená v níže uvedené tabulce se mohla následně během dalšího pokusu úspěšně zaregistrovat. Některé neúspěšné pokusy nemusí být uvedené. Informace o zmírnění dopadů nejsou k dispozici pro všechny chyby.

| Sloupec tabulky | Popis |
|-------------|----------|
| Stav registrace | Počáteční čas, kdy uživatel poprvé zahájil registraci |
| Operační systém | Operační systém zařízení |
| Verze operačního systému | Verze operačního systému zařízení |
| Chyba | Důvod chyby |

### <a name="failure-details"></a>Podrobnosti chyby

Po výběru řádku chyby se zobrazí další podrobnosti.

| Oddíl | Popis |
|-------------|----------|
| Podrobnosti chyby | Podrobnější vysvětlení chyby |
| Možná náprava | Navrhovaný postup k vyřešení chyby. Pro některé chyby nemusí být náprava uvedená. |
| Prostředky (volitelné) | Odkazy na další čtení nebo oblasti na portálu |

### <a name="enrollment-errors"></a>Chyby registrace

| Chyba | Podrobnosti |
|-------------|----------|
| Časový limit nebo chyba iOSu | Došlo k vypršení časového limitu relace mezi zařízením a Intune, protože uživateli trvala registrace moc dlouho. |
| Uživatel se nenašel nebo nemá licenci | Uživatel nemá licenci nebo je ze služby odebraný. |
| Zařízení je už zaregistrované | Někdo se pokusil o registraci zařízení pomocí Portálu společnosti na zařízení, které má zaregistrované jiný uživatel. |
| Nepřipojeno k Intune | Došlo k pokusu o registraci, když nebyla nakonfigurovaná autorita správy mobilních zařízení (MDM) Intune. |
| Ověřování registrace nebylo úspěšné | Došlo k pokusu o registraci pomocí staré verze Portálu společnosti. |
| Zařízení se nepodporuje | Zařízení nesplňuje minimální požadavky pro registraci v Intune. |
| Nesplnila se omezení registrace | Tato registrace se zablokovala kvůli omezení registrace, které nakonfiguroval správce. |
| Dosažení limitu zařízení | Tato registrace se zablokovala kvůli omezení počtu zařízení, které nakonfiguroval správce. |
| Onboarding Apple | Registrace všech zařízení s iOSem se v tuto chvíli zablokovala kvůli chybějícímu nebo prošlému certifikátu Apple MDM Push Certificate v Intune. |
| Zařízení se nezaregistrovalo předem | Zařízení se nezaregistrovalo předem jako podnikové a správce zablokoval všechny osobní registrace. |
| Funkce se nepodporuje | Uživatel se zřejmě pokusil o registraci prostřednictvím metody, která není kompatibilní s konfigurací Intune. |

## <a name="collect-available-data-from-mobile-device"></a>Shromažďování dostupných dat z mobilních zařízení

Pokud chcete shromažďovat data ze zařízení při řešení potíží se zařízením uživatele, použijte následující zdroje informací:
  - [Odeslání chyb registrace zařízení s iOSem správci IT](/intune-user-help/send-errors-to-your-it-admin-ios)
  - [Pomoc firemní podpoře s řešením problémů zařízení pomocí podrobného protokolování](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android)
  - [Odeslání protokolů Androidu firemní podpoře pomocí kabelu USB](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Odeslání protokolů s diagnostickými daty ze zařízení s Androidem správci IT e-mailem](/intune-user-help/send-logs-to-your-it-admin-by-email-android)
  - [Odeslání chyb registrace zařízení s Androidem správci IT](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)

## <a name="next-steps"></a>Další kroky

Můžete zjistit další informace o řízení správy na základě rolí (RBAC) k definování rolí v zařízení organizace, správě mobilních aplikací a úlohách ochrany dat. Další informace najdete v článku [Řízení správy na základě rolí (RBAC) s Intune](/intune/role-based-access-control).

Zjistěte další informace o známých problémech v Microsoft Intune. Ty najdete v článku [Známé problémy v Microsoft Intune](/intune/known-issues).

Zjistěte, jak vytvořit lístek podpory a získat pomoc, když ji potřebujete. [Získejte podporu](/intune/get-support).
