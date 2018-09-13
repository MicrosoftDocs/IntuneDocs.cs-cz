---
title: Nastavení beznabídkového režimu Androidu v Microsoft Intune – Azure | Microsoft Docs
description: Konfigurace zařízení s Androidem Enterprise v beznabídkovém režimu
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e43ab0d088edc87e814ad2c4317d7b7336d34d5
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2018
ms.locfileid: "43312892"
---
# <a name="android-enterprise-kiosk-settings-in-intune"></a>Nastavení beznabídkového režimu Androidu Enterprise v Intune

Profily Androidu v beznabídkovém režimu podporují následující nastavení konfigurace. Při vytváření profilu se tato nastavení objeví, když zvolíte **Typ profilu** > **Jen vlastník zařízení** > **Omezení zařízení**. Tato nastavení zobrazíte tak, že v profilu omezení zařízení s Androidem Enterprise zvolíte **Vlastnosti** a pak **Konfigurovat**.

## <a name="general-settings"></a>Obecná nastavení

- **Snímek obrazovky**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v pořizování snímků obrazovky zařízení.
- **Kamera**: Zvolte **Blokovat**, pokud chcete zakázat kameru zařízení.
- **Výchozí zásady oprávnění**: Toto nastavení definuje výchozí zásady oprávnění pro žádosti o oprávnění za běhu. Mezi možné hodnoty patří:
    - **Výchozí ze zařízení**: Použije se výchozí nastavení zařízení.
    - **Zeptat se**: Uživateli se zobrazí výzva ke schválení oprávnění.
    - **Automaticky udělit**: Oprávnění jsou udělena automaticky.
    - **Automaticky odepřít**: Oprávnění jsou odepřena automaticky.
- **Změny hlasitosti**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit ve změně hlasitosti zařízení.
- **Vymazat**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit ve vymazání zařízení.
- **Bezpečné spuštění**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v restartování zařízení do nouzového režimu.
- **Stavový řádek**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v přístupu ke stavovému řádku včetně oznámení a rychlých nastavení.
- **Změny nastavení Wi-Fi**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit ve změně konfigurací Wi-Fi vytvořených vlastníkem zařízení. Uživatelé mohou vytvářet své vlastní konfigurace Wi-Fi.
- **Konfigurace přístupového bodu Wi-Fi**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit ve vytvoření nebo úpravě jakýchkoli konfigurací Wi-Fi.
- **Funkce ladění**: Zvolte **Povolit**, pokud chcete uživatelům umožnit použití funkcí ladění.
- **Úprava mikrofonu**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v nastavení hlasitosti nebo ztlumení mikrofonu.
- **E-maily pro ochranu před vymazáním**: Zvolte **E-mailové adresy účtů Google**, pokud chcete definovat e-mailové adresy (oddělené středníkem), které mohou zařízení po vymazání odemknout. Pokud není e-mail zadaný, může zařízení po vymazání odemknout kdokoli.
- **Dočasné síťové připojení**: Zvolte **Povolit**, pokud chcete zapnout funkci dočasného síťového připojení. Pokud během spouštění nelze vytvořit připojení k síti, vyzve tato funkce uživatele k dočasnému připojení k síti kvůli aktualizaci zásad zařízení. Po uplatnění zásad se tato dočasná síť zapomene a zařízení pokračuje ve spouštění. Tím se zabrání situaci, kdy se nelze připojit k síti, pokud v posledních zásadách neexistuje žádná vhodná síť a v zařízení se spustí aplikace v zablokovaném režimu, nebo když se uživatel nemůže dostat k nastavení zařízení.
- **Povolit instalaci z neznámých zdrojů**: Zvolte **Povolit**, pokud uživatelům chcete umožnit instalaci z neznámých zdrojů.
- **Aktualizace systému**: Zvolením některé možnosti určete, jak má zařízení zpracovat aktualizace OTA (Over The Air):
    - **Výchozí ze zařízení**: Použije se výchozí nastavení zařízení.
    - **Automaticky**: Aktualizace se nainstalují automaticky.
    - **Odloženo**: Aktualizace se odloží na pozdější datum.
    - **Časové období údržby**: V časovém období údržby jsou uživatelé vyzváni ke schválení aktualizace.

## <a name="kiosk-settings"></a>Nastavení veřejného terminálu

- **Beznabídkový režim**: Definuje, jestli v zařízení může běžet jedna nebo několik aplikací. Další informace najdete v článku o [nastavení beznabídkového režimu zařízení s Androidem](android-kiosk-settings.md).
    - **Veřejný terminál s jednou aplikací**: Uživatelé mají přístup jen k jedné aplikaci.
    - **Beznabídkový režim s více aplikacemi**: Uživatelé mají přístup k omezené sadě aplikací.

## <a name="device-password-settings"></a>Nastavení hesla zařízení

- **Keyguard**: Zvolte **Zakázat**, pokud chcete uživatelům zabránit v použití Keyguardu na zařízení.
- **Požadovaný typ hesla**: Definujte typ hesla požadovaného pro zařízení.
- **Minimální délka hesla**: Definujte minimální délku hesla požadovanou pro zařízení.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: Definujte počet neúspěšných přihlášení, ke kterým musí dojít, než se zařízení vymaže.

## <a name="power-settings"></a>Nastavení napájení

- **Čas do zamknutí obrazovky**: Nastavte dobu nečinnosti, po jejímž uplynutí se zařízení uzamkne.
- **Zapnutá obrazovka, když se zařízení napájí ze sítě**: Zvolte zdroje napájení, při jejichž použití zůstane obrazovka zařízení zapnutá.

## <a name="users-and-accounts-settings"></a>Nastavení uživatelů a účtů

- **Přidat nové uživatele**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v přidávání nových uživatelů.
- **Odebírání uživatelů**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v odebírání uživatelů.
- **Změny účtu**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v úpravě účtů.

## <a name="next-steps"></a>Další kroky
[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).



