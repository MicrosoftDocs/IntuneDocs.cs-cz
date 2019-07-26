---
title: Přidání ochrany koncových bodů s macOS v Microsoft Intune – Azure | Microsoft Docs
description: Na zařízeních s macOS můžete použít Gatekeeper k určení aplikací, které se smí instalovat, včetně aplikací z Mac App Storu. V Microsoft Intune také můžete určitým aplikacím povolit nebo nakonfigurovat průchod bránou firewall nebo můžete určité aplikace zablokovat, použít neviditelný režim utajení, případně blokovat určité typy příchozích připojení.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3a885abfdd7f23f453f03c63fdb0086bed40a7b1
ms.sourcegitcommit: c3a4fefbac8ff7badc42b1711b7ed2da81d1ad67
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/22/2019
ms.locfileid: "68375032"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Nastavení ochrany koncových bodů MacOS v Intune  

Tento článek ukazuje nastavení ochrany koncových bodů, která můžete nakonfigurovat pro zařízení s macOS. Tato nastavení nakonfigurujete pomocí profilu konfigurace zařízení macOS pro [Endpoint Protection](endpoint-protection-configure.md) v Intune.  

## <a name="gatekeeper"></a>Gatekeeper  

- **Povolí aplikace stažené z těchto umístění.**  
  Omezte aplikace, které může zařízení spustit, v závislosti na tom, odkud se aplikace stáhly. Záměrem je chránit zařízení před malwarem a dovolit aplikacím jenom ze zdrojů, kterým důvěřujete.  

  - **Není nakonfigurováno**  
  - **Mac App Store**  
  - **Mac App Store a identifikovaní vývojáři**  
  - **Kdekoliv**  

  **Výchozí**: Není nakonfigurováno  

- **Uživatel může přepsat server gatekeeper**  
  Zabrání uživatelům přepsat nastavení serveru gatekeeper a zabránit uživatelům v řízení kliknutí na instalaci aplikace. Pokud tuto možnost povolíte, uživatelé mohou stisknout klávesu Control a kliknutím na libovolnou aplikaci ji nainstalovat.  
 
  - Nenakonfigurováno – uživatelé můžou instalovat aplikace kliknutím na tlačítko.  
  - **Blok** – zabraňuje uživatelům v použití řízení – kliknutím instalovat aplikace.  

  **Výchozí**: Není nakonfigurováno  

## <a name="firewall"></a>Brána firewall  

Firewall slouží ke kontrole připojení aplikace, nikoli připojení k portu. Když použijete nastavení pro danou aplikaci, získáte snadno výhody ochrany branou firewall. Nežádoucím aplikacím také znemožníte převzetí kontroly nad síťovými porty otevřenými pro oprávněné aplikace.  

**Obecné**
- **Servery**  
  Povolte bránu firewall ke konfiguraci způsobu zpracování příchozích připojení ve vašem prostředí.  
  - **Není nakonfigurováno**  
  - **Aby**  

  **Výchozí**: Není nakonfigurováno  

- **Příchozí připojení**  
  Blokuje všechna příchozí připojení s výjimkou připojení požadovaných pro základní internetové služby, jako jsou DHCP, Bonjour a IPSec. Tato funkce také zablokuje všechny služby sdílení, jako je sdílení souborů nebo sdílení obrazovky. Pokud používáte služby sdílení, toto nastavení *nekonfigurujte*.  
  - **Není nakonfigurováno**  
  - **Blokováno**  

  **Výchozí**: Není nakonfigurováno  

**Povolí nebo zablokuje příchozí připojení pro konkrétní aplikace.**  

  - **Povolené aplikace**  
    Vyberte aplikace, které mají explicitně povolený příjem příchozích připojení.  

  - **Blokované aplikace**  
    Vyberte aplikace, které by měly blokovat příchozí připojení.  

  - **Neviditelný režim**  
    Chcete-li zabránit počítači v reakci na požadavky na zjišťování, Povolte režim utajení. Oprávněným aplikacím bude zařízení dále odpovídat na příchozí žádosti. Neočekávané požadavky, jako je ICMP (ping), se ignorují.  
    - **Není nakonfigurováno**  
    - **Aby**  

    **Výchozí**: Není nakonfigurováno  

## <a name="filevault"></a>FileVault  
Další informace o nastaveních úložišť Apple najdete v tématu [FDEFileVault](https://developer.apple.com/documentation/devicemanagement/fdefilevault) v obsahu pro vývojáře Apple. 

- **FileVault**  
  Pomocí XTS-AES 128 s trezorem pro zařízení, na kterých běží macOS 10,13 nebo novější, můžete *Povolit* úplné šifrování disku.  
  - **Není nakonfigurováno**  
  - **Aby**  

  **Výchozí**: Není nakonfigurováno  

  - **Typ obnovovacího klíče**  
    Pro zařízení se vytvoří klíče pro obnovení *osobních klíčů* . Pro osobní klíč nakonfigurujte následující nastavení.  

    - **Umístění klíče pro osobní obnovení** – zadejte krátkou zprávu pro uživatele, která vysvětluje, jak mohou načíst svůj osobní obnovovací klíč. Tento text je vložen do zprávy, kterou uživatel uvidí při povolování trezoru.  
      
    - **Střídání osobních obnovovacích klíčů** – určete, jak často se má otočit osobní obnovovací klíč pro zařízení. Můžete vybrat výchozí nastavení **není nakonfigurováno**nebo hodnota **1** až **12** měsíců.  

  - **Odložit trezor úložiště, dokud neproběhne odhlášení**  
    > [!NOTE]
    > Podpora trezoru úložišť je omezená až do chvíle, kdy se vydaná verze z července dokončí za několik dní. Pokud nakonfigurujete trezor úložiště, je třeba nastavit odložené *úložiště. až* do chvíle, kdy se zavedete k **Povolení**.   

    Trezor úložišť nebude povolený, dokud se uživatel odhlásí. Uživateli místního uživatele nebo mobilního účtu se zobrazí výzva k povolení trezoru úložišť při odhlášení nebo při příštím přihlášení.  
    - **Není nakonfigurováno**  
    - **Aby**  
    **Výchozí**: Není nakonfigurováno  



    - **Zakázat výzvu při odhlášení**  
      Zabrání uživateli zobrazit výzvu, aby povolila trezor úložiště při odhlášení.  
      - **Není nakonfigurováno**  
      - **Aby**  

      **Výchozí**: Není nakonfigurováno  

    - **Počet povolených pokusů o obejití**  
    Nastaví počet pokusů, které uživatel může ignorovat výzvy k povolení trezoru úložišť, aby se uživatel mohl přihlásit.  

      - **Není nakonfigurováno** – před povolením dalšího přihlášení je vyžadováno šifrování zařízení.  
      -  **1** až **10** – povolí uživateli ignorovat výzvu od 1 do 10 před tím, než se v zařízení vyžaduje šifrování.  
      - **Bez omezení, vždy** se zobrazí výzva – uživatel bude vyzván k povolení trezoru úložišť, ale šifrování není nikdy vyžadováno.  
 
      **Výchozí**: Není nakonfigurováno  


