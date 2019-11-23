---
title: Wi-Fi settings for Android Enterprise and kiosk devices - Microsoft Intune | Microsoft Docs
description: Vytvořte nebo přidejte konfigurační profil zařízení s připojením Wi-Fi pro Android Enterprise a beznabídkový režim Androidu. Podívejte se na různá nastavení, včetně přidání certifikátů, volby typu protokolu EAP a výběru metody ověřování v Microsoft Intune. U zařízení s beznabídkovým režimem zadejte také předsdílený klíč sítě.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/08/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: maholdaa
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04d35f49f9e07cb72a1fea92210b05e0a95ec256
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390808"
---
# <a name="add-wi-fi-settings-for-android-enterprise-dedicated-and-fully-managed-devices-in-microsoft-intune"></a>Add Wi-Fi settings for Android Enterprise dedicated and fully managed devices in Microsoft Intune

You can create a profile with specific Wi-Fi settings, and then deploy this profile to your Android Enterprise fully managed and dedicated devices. Microsoft Intune nabízí mnoho funkcí, například ověřování v síti, použití předsdíleného klíče a další.

Těmito nastaveními se zabývá tento článek. [Use Wi-Fi on your devices](wi-fi-settings-configure.md) includes more information about the Wi-Fi feature in Microsoft Intune.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil zařízení v Microsoft Intune](wi-fi-settings-configure.md#create-a-device-profile).

## <a name="device-owner-only"></a>Device owner only

Select this option if you are deploying to an Android Enterprise dedicated or fully managed device.  Android Enterprise dedicated and fully managed devices currently support SCEP certificate deployment, but not PKCS.

### <a name="basic"></a>Basic

- **Typ Wi-Fi**: Zvolte **Základní**.
- **Název sítě**: Zadejte název pro toto připojení Wi-Fi. End users see this name when they browse their device for available Wi-FI connections. For example, enter **Contoso WiFi**.
- **SSID**: Enter the **service set identifier**, which is the real name of the wireless network that devices connect to. **Název sítě**, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Skrytá síť**: Zvolte **Povolit**, pokud chcete tuto síť skrýt v seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.
- **Typ Wi-Fi**: Vyberte protokol zabezpečení, který se má použít k ověření sítě Wi-Fi. Možnosti:

  - **Otevřené (bez zabezpečení):** tuto možnost použijte jenom v případě, že síť není zabezpečená.
  - **Předsdílený klíč WEP**: Zadejte heslo do pole **Předsdílený klíč**. Po nastavení nebo konfiguraci firemní sítě se nakonfiguruje také heslo nebo síťový klíč. Toto heslo nebo síťový klíč zadejte jako hodnotu PSK.
  - **Předsdílený klíč WPA**: Zadejte heslo do pole **Předsdílený klíč**. Po nastavení nebo konfiguraci firemní sítě se nakonfiguruje také heslo nebo síťový klíč. Toto heslo nebo síťový klíč zadejte jako hodnotu PSK.

### <a name="enterprise"></a>Enterprise

- **Typ Wi-Fi**: Zvolte **Enterprise**.
- **SSID**: Enter the **service set identifier**, which is the real name of the wireless network that devices connect to. **Název sítě**, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Skrytá síť**: Zvolte **Povolit**, pokud chcete tuto síť skrýt v seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.
- **Typ EAP**: Zvolte typ protokolu EAP (Extensible Authentication Protocol) pro ověřování zabezpečených bezdrátových připojení. Možnosti:

  - **EAP-TLS**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** – **Kořenový certifikát pro ověřování serveru**: Zvolte existující profil důvěryhodného kořenového certifikátu. When the client connects to the network, this certificate is presented to the server, and authenticates the connection.

    - **Client Authentication** - **Client certificate for client authentication (Identity certificate)** : Choose the SCEP client certificate profile that is also deployed to the device. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

    - **Ochrana identity (vnější identita)** : Zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

  - **EAP-TTLS**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** – **Kořenový certifikát pro ověřování serveru**: Zvolte existující profil důvěryhodného kořenového certifikátu. When the client connects to the network, this certificate is presented to the server, and authenticates the connection.

    - **Client Authentication**: Choose an **Authentication method**. Možnosti:

      - **Uživatelské jméno a heslo**: Zobrazí uživateli výzvu k zadání uživatelského jména a hesla pro ověření připojení. Dále zadejte:
        - **Metoda bez protokolu EAP (vnitřní identita)** : Zvolte, jak chcete připojení ověřovat. Nezapomeňte vybrat stejný protokol, který je nakonfigurovaný u sítě Wi-Fi. Možnosti:

          - **Nezašifrované heslo (PAP)**
          - **Protokol Microsoft CHAP (MS-CHAP)**
          - **Protokol Microsoft CHAP verze 2 (MS-CHAP v2)**

      - **Certificates**: Choose the SCEP client certificate profile that is also deployed to the device. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

      - **Ochrana identity (vnější identita)** : Zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

  - **PEAP**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** – **Kořenový certifikát pro ověřování serveru**: Zvolte existující profil důvěryhodného kořenového certifikátu. When the client connects to the network, this certificate is presented to the server, and authenticates the connection.

    - **Client Authentication**: Choose an **Authentication method**. Možnosti:

      - **Uživatelské jméno a heslo**: Zobrazí uživateli výzvu k zadání uživatelského jména a hesla pro ověření připojení. Dále zadejte:
        - **Ověřování metodou bez protokolu EAP (vnitřní identita)** : Zvolte, jak chcete připojení ověřovat. Nezapomeňte vybrat stejný protokol, který je nakonfigurovaný u sítě Wi-Fi. Možnosti:

          - **Žádné**
          - **Protokol Microsoft CHAP verze 2 (MS-CHAP v2)**

      - **Certificates**: Choose the SCEP client certificate profile that is also deployed to the device. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

      - **Ochrana identity (vnější identita)** : Zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

## <a name="work-profile-only"></a>Pouze pracovní profil

### <a name="basic"></a>Basic

- **Typ Wi-Fi**: Zvolte **Základní**.
- **SSID**: Enter the **service set identifier**, which is the real name of the wireless network that devices connect to. **Název sítě**, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Skrytá síť**: Zvolte **Povolit**, pokud chcete tuto síť skrýt v seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.

### <a name="enterprise"></a>Enterprise

- **Typ Wi-Fi**: Zvolte **Enterprise**.
- **SSID**: Enter the **service set identifier**, which is the real name of the wireless network that devices connect to. **Název sítě**, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Skrytá síť**: Zvolte **Povolit**, pokud chcete tuto síť skrýt v seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.
- **Typ EAP**: Zvolte typ protokolu EAP (Extensible Authentication Protocol) pro ověřování zabezpečených bezdrátových připojení. Možnosti:

  - **EAP-TLS**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** – **Kořenový certifikát pro ověřování serveru**: Zvolte existující profil důvěryhodného kořenového certifikátu. When the client connects to the network, this certificate is presented to the server, and authenticates the connection.

    - **Ověřování klientů** – **Klientský certifikát pro ověření klienta (certifikát identity)** : Zvolte profil klientského certifikátu SCEP nebo PKCS, který je také nasazený na zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

    - **Ochrana identity (vnější identita)** : Zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

  - **EAP-TTLS**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** – **Kořenový certifikát pro ověřování serveru**: Zvolte existující profil důvěryhodného kořenového certifikátu. When the client connects to the network, this certificate is presented to the server, and authenticates the connection.

    - **Client Authentication**: Choose an **Authentication method**. Možnosti:

      - **Uživatelské jméno a heslo**: Zobrazí uživateli výzvu k zadání uživatelského jména a hesla pro ověření připojení. Dále zadejte:
        - **Metoda bez protokolu EAP (vnitřní identita)** : Zvolte, jak chcete připojení ověřovat. Nezapomeňte vybrat stejný protokol, který je nakonfigurovaný u sítě Wi-Fi. Možnosti:

          - **Nezašifrované heslo (PAP)**
          - **Protokol Microsoft CHAP (MS-CHAP)**
          - **Protokol Microsoft CHAP verze 2 (MS-CHAP v2)**

      - **Certifikáty**: Zvolte profil klientského certifikátu SCEP nebo PKCS, který je také nasazený na zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

      - **Ochrana identity (vnější identita)** : Zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

  - **PEAP**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** – **Kořenový certifikát pro ověřování serveru**: Zvolte existující profil důvěryhodného kořenového certifikátu. When the client connects to the network, this certificate is presented to the server, and authenticates the connection.

    - **Client Authentication**: Choose an **Authentication method**. Možnosti:

      - **Uživatelské jméno a heslo**: Zobrazí uživateli výzvu k zadání uživatelského jména a hesla pro ověření připojení. Dále zadejte:
        - **Ověřování metodou bez protokolu EAP (vnitřní identita)** : Zvolte, jak chcete připojení ověřovat. Nezapomeňte vybrat stejný protokol, který je nakonfigurovaný u sítě Wi-Fi. Možnosti:

          - **Žádné**
          - **Protokol Microsoft CHAP verze 2 (MS-CHAP v2)**

      - **Certifikáty**: Zvolte profil klientského certifikátu SCEP nebo PKCS, který je také nasazený na zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

      - **Ochrana identity (vnější identita)** : Zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

## <a name="next-steps"></a>Další kroky

Profil se vytvoří, ale nic nedělá. Next, [assign this profile](device-profile-assign.md) and [monitor its status.](device-profile-monitor.md).

You can also create Wi-Fi profiles for [Android](wi-fi-settings-android.md), [iOS](wi-fi-settings-ios.md), [macOS](wi-fi-settings-macos.md), [Windows 10](wi-fi-settings-windows.md), and [Windows 8.1](wi-fi-settings-import-windows-8-1.md) devices.
