---
title: "Portál helpdesku pro řešení potíží"
titlesuffix: Microsoft Intune
description: "Pracovníci helpdesku používají portál pro řešení potíží, aby pomohli uživatelům s řešením technických problémů."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 7997bf0494ff52ad25b09301173b65f2478dca37
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="use-the-troubleshooting-portal-to-help-users-at-your-company"></a>Použití portálu pro řešení potíží k poskytování pomoci uživatelům ve vaší společnosti

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Portál pro řešení potíží umožňuje operátorům helpdesku a správcům Intune zobrazit informace o uživatelích a použít je k řešení jejich žádostí o pomoc. Organizace, které zahrnují helpdesk, můžou skupině uživatelů přiřadit **operátora helpdesku**. Role operátora helpdesku může používat okno **Řešení potíží**.

V okně **Řešení potíží** se zobrazují také problémy s registrací uživatelů. Podrobnosti o problému a navrhované nápravné kroky můžou správcům a pracovníkům technické podpory pomoct problém vyřešit. Některé problémy s registrací nejsou zaznamenané a k některým chybám nemusí návrhy k odstranění problému existovat. 

Pokyny k přidání role operátora helpdesku najdete v článku [Řízení správy na základě rolí (RBAC) s Intune](/intune/role-based-access-control)

Když uživatel kontaktuje podporu ohledně technického problému s Intune, zadá operátor helpdesku jméno uživatele. Intune zobrazí užitečná data, která vám můžou pomoct s řešením řady problémů úrovně 1 včetně těchto:

- Stav uživatele
- Přiřazení
- Problémy se shodou
- Zařízení neodpovídá
- Zařízení nedokáže získat nastavení sítě VPN nebo Wi-Fi
- Instalace aplikace se nezdařila

## <a name="to-review-troubleshooting-details"></a>Kontrola podrobností o řešení potíží

Zvolením možnosti **Vybrat uživatele** v okně pro řešení potíží zobrazíte informace o uživateli. Informace o uživateli vám mohou pomoci porozumět aktuálnímu stavu uživatelů a jejich zařízení.  

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Řešení potíží**.
4. Klikněte na **Vybrat uživatele**.
5. Vyberte uživatele zadáním jména nebo e-mailové adresy. Klikněte na **Vybrat**. Informace o řešení potíží pro uživatele se zobrazí v okně Řešení potíží. Informace jsou vysvětlené v následujících tabulkách.

> [!Note]  
> Do okna **řešení potíží**  se dostanete také tak, že v prohlížeči přejdete na: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="areas-of-troubleshooting-dashboard"></a>Oblasti řídicího panelu pro řešení potíží

V okně **Řešení potíží** můžete zkontrolovat informace o uživateli. 

![](/intune/media/troubleshooting-dash.png)

| Oblast | Název | Popis |
| ---  | ---  | ---         |
| 1.   | Stav účtu  | Zobrazuje stav aktuálního tenanta Intune, například **Aktivní** nebo **Neaktivní**.       |
| 2.   | Výběr uživatele  | Jméno aktuálně vybraného uživatele. Kliknutím na **Změnit uživatele** zvolíte nového uživatele.       |
| 3.   | Stav uživatele  | Zobrazí stav uživatelovy licence Intune, počet zařízení, dodržování předpisů u každého zařízení, počet aplikací a dodržování předpisů u aplikací.       |
| 4.   | Údaje uživatele  | Pomocí seznamu můžete vybrat podrobnosti, které chcete v okně zkontrolovat. <br>Můžete vybrat: <ul><li>Mobilní aplikace<li>Zásady ochrany aplikace<li>Zásady dodržování předpisů<li> Zásady konfigurace<li> Omezení registrace</ul>      |
| 5.   | Členství ve skupině  | Yadda       |

## <a name="mobile-apps-reference"></a>Informace o mobilních aplikacích

Aplikace, které jsou spuštěné na zařízeních, nebo zařízení, která patří uživatelům a jsou spravovaná pomocí Intune a Azure Active Directory (AD).

### <a name="properties"></a>Vlastnosti

Vlastnosti mobilních aplikací

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
| Vlastnictví          | Typ vlastnictví zařízení. Může být **Společnost**, **Osobní** a **Neznámý**.                                               |
| Vyhovuje Intune   | Název typu zařízení                                                                                                     |
| Vyhovuje Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Operační systém                 | Operační systém nainstalovaný v zařízení                                                                                       |
| Verze operačního systému         | Číslo verze operačního systému zařízení.                                                                                  |
| Poslední vrácení se změnami      | Název typu zařízení                                                                                                     |

### <a name="app-protection-status"></a>Stav ochrany aplikace

Pro mobilní aplikace, které se integrují s technologiemi Enterprise Mobility Solution (EMS), jsou k dispozici zásady ochrany aplikací. Tím vzniká základ ochrany dat společnosti po jejich stažení do mobilních aplikací, včetně mobilních aplikací Office. 

| Vlastnost    | Popis                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Stav      | Typ vlastnictví zařízení. Může být **Společnost**, **Osobní** a **Neznámý**. |
| Název aplikace    | Název aplikace                                                           |
| Název zařízení | Název typu zařízení                                                       |
| Typ zařízení | Název typu zařízení                                                       |
| Zásady    | Typ vlastnictví zařízení. Může být **Společnost**, **Osobní** a **Neznámý**. |
| Poslední synchronizace   | Časové razítko poslední synchronizace zařízení s Intune.                   |

## <a name="app-protection-policies-reference"></a>Informace o zásadách ochrany aplikací

Pro mobilní aplikace, které se integrují s technologiemi EMS, jsou k dispozici zásady ochrany aplikací. Tím vzniká základ ochrany dat společnosti po jejich stažení do mobilních aplikací, včetně mobilních aplikací Office. 

### <a name="properties"></a>Vlastnosti

Tabulka shrnuje stav zásad ochrany aplikací pro zařízení spravovaná pomocí Intune.

| Vlastnost    | Popis                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Název        | Název aplikace                                                                                                        |
| Nasazeno    | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Platforma    | Typ vlastnictví zařízení. Může být **Společnost**, **Osobní** a **Neznámý**.                                               |
| Registrace  | Název typu zařízení                                                                                                     |
| Poslední aktualizace | Časové razítko změny zásad                                                                                              |

### <a name="devices"></a>Zařízení

Zařízení spravovaná pomocí Intune nebo uživateli, kteří jsou spravovaní pomocí Intune nebo Azure AD.

| Vlastnost           | Text                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Název zařízení        | Název typu zařízení                                                                                                     |
| Spravuje         | Časové razítko změny zásad                                                                                              |
| Typ připojení ke službě Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Vlastnictví          | Typ vlastnictví zařízení. Může být **Společnost**, **Osobní** a **Neznámý**.                                               |
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
| Typ zásad   | Typ vlastnictví zařízení. Může být **Společnost**, **Osobní** a **Neznámý**.                                               |
| Datum poslední změny | Název typu zařízení                                                                                                     |

### <a name="devices"></a>Zařízení

Zařízení spravovaná pomocí Intune nebo uživateli, kteří jsou spravovaní pomocí Intune nebo Azure AD.

| Vlastnost           | Popis                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Název zařízení        | Název typu zařízení                                                                                                     |
| Spravuje         | Časové razítko změny zásad                                                                                              |
| Typ připojení ke službě Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Vlastnictví          | Typ vlastnictví zařízení. Může být **Společnost**, **Osobní** a **Neznámý**.                                               |
| Vyhovuje Intune   | Název typu zařízení                                                                                                     |
| Vyhovuje Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Operační systém                 | Operační systém nainstalovaný v zařízení                                                                                       |
| Verze operačního systému         | Číslo verze operačního systému zařízení.                                                                                  |
| Poslední vrácení se změnami      | Název typu zařízení                                                                                                     |

### <a name="app-protection-policies"></a>Zásady ochrany aplikace

Pro mobilní aplikace, které se integrují s technologiemi EMS, jsou k dispozici zásady ochrany aplikací. Tím vzniká základ ochrany dat společnosti po jejich stažení do mobilních aplikací, včetně mobilních aplikací Office. 

| Vlastnost    | Popis                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Stav      | Typ vlastnictví zařízení. Může být **Společnost**, **Osobní** a **Neznámý**. |
| Název aplikace    | Název aplikace                                                           |
| Název zařízení | Název typu zařízení                                                       |
| Typ zařízení | Název typu zařízení                                                       |
| Zásady    | Typ vlastnictví zařízení. Může být **Společnost**, **Osobní** a **Neznámý**. |
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
| Typ zásad   | Typ vlastnictví zařízení. Může být **Společnost**, **Osobní** a **Neznámý**.                                               |
| Datum poslední změny | Název typu zařízení                                                                                                     |

### <a name="devices"></a>Zařízení

Zařízení spravovaná pomocí Intune nebo uživateli, kteří jsou spravovaní pomocí Intune nebo Azure AD.

| Vlastnost           | Popis                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Název zařízení        | Název typu zařízení                                                                                                     |
| Spravuje         | Časové razítko změny zásad                                                                                              |
| Typ připojení ke službě Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Vlastnictví          | Typ vlastnictví zařízení. Může být **Společnost**, **Osobní** a **Neznámý**.                                               |
| Vyhovuje Intune   | Název typu zařízení                                                                                                     |
| Vyhovuje Azure AD | Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**. |
| Operační systém                 | Operační systém nainstalovaný v zařízení                                                                                       |
| Verze operačního systému         | Číslo verze operačního systému zařízení.                                                                                  |
| Poslední vrácení se změnami      | Název typu zařízení                                                                                                     |


### <a name="app-protection-policies"></a>Zásady ochrany aplikace

Pro mobilní aplikace, které se integrují s technologiemi EMS, jsou k dispozici zásady ochrany aplikací. Tím vzniká základ ochrany dat společnosti po jejich stažení do mobilních aplikací, včetně mobilních aplikací Office. 

| Vlastnost    | Popis                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Stav      | Typ vlastnictví zařízení. Může být **Společnost**, **Osobní** a **Neznámý**. |
| Název aplikace    | Název aplikace                                                           |
| Název zařízení | Název typu zařízení                                                       |
| Typ zařízení | Název typu zařízení                                                       |
| Zásady    | Typ vlastnictví zařízení. Může být **Společnost**, **Osobní** a **Neznámý**. |
| Poslední synchronizace   | Časové razítko poslední synchronizace zařízení s Intune.                   |

## <a name="next-steps"></a>Další kroky

Můžete zjistit další informace o řízení správy na základě rolí (RBAC) k definování rolí v zařízení organizace, správě mobilních aplikací a úlohách ochrany dat. Další informace najdete v článku [Řízení správy na základě rolí (RBAC) s Intune](/intune/role-based-access-control).

Zjistěte další informace o známých problémech v Microsoft Intune. Ty najdete v článku [Známé problémy v Microsoft Intune](/intune/known-issues).

Zjistěte, jak vytvořit lístek podpory a získat pomoc, když ji potřebujete. [Získejte podporu](/intune/get-support).