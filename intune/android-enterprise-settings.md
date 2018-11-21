---
title: Nastavení beznabídkového režimu Androidu v Microsoft Intune – Azure | Microsoft Docs
description: Konfigurace zařízení s Androidem Enterprise v beznabídkovém režimu
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 9/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: c4db49b6727a430696d6ade3bc8eb8f4600ebe3e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52190281"
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
    - **Automaticky**: Aktualizace se instalují automaticky bez zásahu uživatele. Po nastavení této zásady se hned nainstalují všechny čekající aktualizace.
    - **Odloženo**: Aktualizace se odloží o 30 dní. Po 30 dnech Android uživatele vyzve k instalaci aktualizace. Výrobci zařízení nebo mobilní operátoři mohou zakázat (vyloučit) odklad důležitých aktualizací zabezpečení. Vynechaná aktualizace zobrazí uživateli zařízení zprávu systému. 
    - **Časové období údržby**: Aktualizace se instalují automaticky během časového období údržby, které nastavíte v Intune. Pokus o instalaci se opakuje každý den po dobu 30 dní. Instalace může selhat kvůli nedostatku místa nebo slabé baterii. Po 30 dnech Android uživateli zobrazí výzvu k instalaci. Toto okno se také používá k instalaci aktualizací aplikací Play. Tato možnost se doporučuje u vyhrazených zařízení, jako jsou veřejné terminály, protože veřejné terminály s jedinou aplikací, která běží v popředí, mohou být aktualizovány. 

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

## <a name="next-steps"></a>Další postup
[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).



