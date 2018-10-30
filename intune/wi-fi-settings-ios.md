---
title: Konfigurace nastavení Wi-Fi pro zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Vytvořte nebo přidejte konfigurační profil zařízení s připojením Wi-Fi pro zařízení s iOSem. Podívejte se na různá nastavení, včetně přidání certifikátů, volby typu protokolu EAP a výběru metody ověřování v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fa81e8979f48a0b027f4860cfc5d2a88e3b30772
ms.sourcegitcommit: cff65435df070940da390609d6376af6ccdf0140
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2018
ms.locfileid: "49425236"
---
# <a name="add-wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>Přidání nastavení Wi-Fi pro zařízení s iOSem v Microsoft Intune

Můžete vytvořit profil s konkrétním nastavením Wi-Fi a potom ho nasadit na zařízení s iOSem. Microsoft Intune nabízí mnoho funkcí, například ověřování v síti, přidání certifikátu PKS nebo SCEP a další.

Tato nastavení Wi-Fi jsou rozdělena do dvou kategorií: základní nastavení a nastavení Enterprise.

Těmito nastaveními se zabývá tento článek.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil zařízení v Microsoft Intune](device-profile-create.md).

## <a name="basic-profiles"></a>Základní profily

- **Typ Wi-Fi**: Zvolte **Základní**.
- **Název sítě**: Zadejte název pro toto připojení Wi-Fi. Tato hodnota představuje název, který uživatelé na svém zařízení uvidí při procházení seznamu dostupných připojení.
- **SSID**: Zkratka pro **Service Set Identifier**. Tato vlastnost je reálným názvem bezdrátové sítě, ke které se zařízení připojí. Název sítě, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Připojovat automaticky**: Zvolte **Povolit**, pokud se chcete automaticky připojovat k této síti, když je zařízení v rozsahu. Zvolte **Zakázat**, pokud chcete zařízením zabránit v automatickém připojování.
- **Skrytá síť**: Zvolte **Povolit**, pokud chcete tuto síť skrýt v seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.
- **Typ zabezpečení**: Vyberte protokol zabezpečení, který se má použít k ověření sítě Wi-Fi. Možnosti:

  - **Otevřené (bez zabezpečení):** tuto možnost použijte jenom v případě, že síť není zabezpečená.
  - **WPA/WPA2-osobní**: Zadejte heslo do pole **Předsdílený klíč**. Po nastavení nebo konfiguraci firemní sítě se nakonfiguruje také heslo nebo síťový klíč. Toto heslo nebo síťový klíč zadejte jako hodnotu PSK.
  - **WEP**

- **Nastavení proxy**: Máte tyto možnosti:
  - **Žádné:** nenakonfiguruje se žádné nastavení proxy.
  - **Ručně**: Zadejte **adresu proxy serveru** ve formě IP adresy a její **číslo portu**.
  - **Automaticky**: Ke konfiguraci proxy serveru použijte soubor. Zadejte **adresu URL proxy serveru** (například `http://proxy.contoso.com`), na které se nachází konfigurační soubor.

## <a name="enterprise-profiles"></a>Profily Enterprise

- **Typ Wi-Fi**: Zvolte **Enterprise**.
- **SSID**: Zkratka pro **Service Set Identifier**. Tato vlastnost je reálným názvem bezdrátové sítě, ke které se zařízení připojí. Název sítě, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Připojovat automaticky**: Zvolte **Povolit**, pokud se chcete automaticky připojovat k této síti, když je zařízení v rozsahu. Zvolte **Zakázat**, pokud chcete zařízením zabránit v automatickém připojování.
- **Skrytá síť**: Zvolte **Povolit**, pokud chcete tuto síť skrýt v seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.

- **Typ EAP**: Zvolte typ protokolu EAP (Extensible Authentication Protocol) pro ověřování zabezpečených bezdrátových připojení. Možnosti:

  - **EAP-FAST**: Zadejte **nastavení PAC (Protected Access Credential)**. Tato možnost používá přihlašovací údaje chráněného přístupu k vytvoření ověřeného tunelového propojení mezi klientem a serverem ověřování. Možnosti:
    - **Nepoužívat (PAC)**
    - **Používat (PAC)**: Pokud existuje soubor PAC, použijte ho.
    - **Používat a zřídit PAC**: Vytvoří a přidá soubor PAC do zařízení.
    - **Používat a zřídit PAC anonymně**: Vytvoří a přidá soubor PAC do zařízení bez ověřování na serveru.

  - **EAP-SIM**

  - **EAP-TLS**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** – **Názvy certifikačních serverů**: **Přidejte** minimálně jeden název použitý v certifikátech, které vystavuje vaše důvěryhodná certifikační autorita. Když tento údaj zadáte, můžete obejít okno dynamického vztahu důvěryhodnosti, které se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.
    - **Kořenový certifikát pro ověřování serveru**: Zvolte existující profil důvěryhodného kořenového certifikátu. Tento certifikát se předloží serveru při připojení klienta k síti a slouží k ověření připojení.

      Výběrem **OK** uložte změny.

    - **Ověřování klientů** – **Klientský certifikát pro ověření klienta (certifikát identity)**: Zvolte profil klientského certifikátu SCEP nebo PKCS, který je také nasazený na zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

      Výběrem **OK** uložte změny.

  - **EAP-TTLS**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** – **Názvy certifikačních serverů**: **Přidejte** minimálně jeden název použitý v certifikátech, které vystavuje vaše důvěryhodná certifikační autorita. Když tento údaj zadáte, můžete obejít okno dynamického vztahu důvěryhodnosti, které se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.
    - **Kořenový certifikát pro ověřování serveru**: Zvolte existující profil důvěryhodného kořenového certifikátu. Tento certifikát se předloží serveru při připojení klienta k síti a slouží k ověření připojení.

      Výběrem **OK** uložte změny.

    - **Ověřování klientů**: Zvolte **metodu ověřování**. Možnosti:

      - **Uživatelské jméno a heslo**: Zobrazí uživateli výzvu k zadání uživatelského jména a hesla pro ověření připojení. Dále zadejte:
        - **Metoda bez protokolu EAP (vnitřní identita)**: Zvolte, jak chcete připojení ověřovat. Nezapomeňte vybrat stejný protokol, který je nakonfigurovaný u sítě Wi-Fi.

          Máte tyto možnosti: **Nešifrované heslo (PAP)**, **CHAP (Challenge Handshake Authentication Protocol)**, **Microsoft CHAP (MS-CHAP)** nebo **Microsoft CHAP verze 2 (MS-CHAP v2)**.

      - **Certifikáty**: Zvolte profil klientského certifikátu SCEP nebo PKCS, který je také nasazený na zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

        Výběrem **OK** uložte změny.

      - **Ochrana identity (vnější identita)**: Zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

  - **LEAP**

  - **PEAP**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** – **Názvy certifikačních serverů**: **Přidejte** minimálně jeden název použitý v certifikátech, které vystavuje vaše důvěryhodná certifikační autorita. Když tento údaj zadáte, můžete obejít okno dynamického vztahu důvěryhodnosti, které se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.
    - **Kořenový certifikát pro ověřování serveru**: Zvolte existující profil důvěryhodného kořenového certifikátu. Tento certifikát se předloží serveru při připojení klienta k síti a slouží k ověření připojení.

      Výběrem **OK** uložte změny.

    - **Ověřování klientů**: Zvolte **metodu ověřování**. Možnosti:

      - **Uživatelské jméno a heslo**: Zobrazí uživateli výzvu k zadání uživatelského jména a hesla pro ověření připojení. 

      - **Certifikáty**: Zvolte profil klientského certifikátu SCEP nebo PKCS, který je také nasazený na zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

        Výběrem **OK** uložte změny.

      - **Ochrana identity (vnější identita)**: Zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

- **Nastavení proxy**: Máte tyto možnosti:
  - **Žádné:** nenakonfiguruje se žádné nastavení proxy.
  - **Ručně**: Zadejte **adresu proxy serveru** ve formě IP adresy a její **číslo portu**.
  - **Automaticky**: Ke konfiguraci proxy serveru použijte soubor. Zadejte **adresu URL proxy serveru** (například `http://proxy.contoso.com`), na které se nachází konfigurační soubor.

Vyberte **OK** > **Vytvořit** a změny uložte. Profil se vytvoří a zobrazí se v seznamu profilů.

## <a name="next-steps"></a>Další kroky

Profil se vytvoří, ale nic nedělá. Dále [tento profil přiřaďte](device-profile-assign.md).

## <a name="more-resources"></a>Další zdroje

[Přehled nastavení Wi-Fi](wi-fi-settings-configure.md), včetně dalších dostupných platforem