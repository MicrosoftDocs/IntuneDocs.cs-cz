---
title: Nastavení Wi-Fi pro zařízení s Androidem Enterprise a veřejného terminálu – Microsoft Intune | Dokumentace Microsoftu
description: Vytvořte nebo přidejte konfigurační profil zařízení s připojením Wi-Fi pro Android Enterprise a beznabídkový režim Androidu. Podívejte se na různá nastavení, včetně přidání certifikátů, volby typu protokolu EAP a výběru metody ověřování v Microsoft Intune. U zařízení s beznabídkovým režimem zadejte také předsdílený klíč sítě.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: cdc7be78ae12d8ab86788c3393da4f0c1425281b
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57398150"
---
# <a name="add-wi-fi-settings-for-devices-running-android-enterprise-and-android-kiosk-in-microsoft-intune"></a>Přidání nastavení Wi-Fi pro zařízení s Androidem Enterprise a s beznabídkovým režimem Androidu v Microsoft Intune

Můžete vytvořit profil s konkrétním nastavením Wi-Fi a potom ho nasadit na zařízení s Androidem Enterprise a na zařízení s beznabídkovým režimem Androidu. Microsoft Intune nabízí mnoho funkcí, například ověřování v síti, použití předsdíleného klíče a další.

Těmito nastaveními se zabývá tento článek. [Pomocí sítě Wi-Fi na zařízeních](wi-fi-settings-configure.md) obsahuje další informace o funkci sítě Wi-Fi v Microsoft Intune.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil zařízení v Microsoft Intune](wi-fi-settings-configure.md#create-a-device-profile).

## <a name="device-owner-only---kiosk"></a>Jen vlastník zařízení – beznabídkový režim

Tuto možnost vyberte, pokud používáte zařízení s Androidem Enterprise v beznabídkovém režimu.

- **Název sítě**: Zadejte název pro toto připojení Wi-Fi. Tato hodnota představuje název, který uživatelé na svém zařízení uvidí při procházení seznamu dostupných připojení.
- **SSID**: Zkratka pro **identifikátor service set**. Toto nastavení je reálným názvem bezdrátové sítě, ke které se zařízení připojí. **Název sítě**, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Připojit automaticky,**: Zvolte **povolit** automaticky se připojovat k této síti, když je zařízení v rozsahu. Zvolte **Zakázat**, pokud chcete zařízením zabránit v automatickém připojování.
- **Skrytá síť**: Zvolte **povolit** skrýt tuto síť ze seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.
- **Typ Wi-Fi**: Vyberte protokol zabezpečení pro ověřování sítě Wi-Fi. Možnosti:

  - **Otevřené (bez ověření)**: Tuto možnost použijte pouze v případě, že síť není zabezpečená.
  - **WEP předsdílený klíč**: Zadejte heslo **předsdílený klíč**. Po nastavení nebo konfiguraci firemní sítě se nakonfiguruje také heslo nebo síťový klíč. Toto heslo nebo síťový klíč zadejte jako hodnotu PSK.
  - **WPA-předsdílený klíč**: Zadejte heslo **předsdílený klíč**. Po nastavení nebo konfiguraci firemní sítě se nakonfiguruje také heslo nebo síťový klíč. Toto heslo nebo síťový klíč zadejte jako hodnotu PSK.

Vyberte **OK** uložte provedené změny.

## <a name="work-profile-only"></a>Pouze pracovní profil

### <a name="basic-settings"></a>Základní nastavení

- **Typ Wi-Fi**: Zvolte **Základní**.
- **SSID**: Zkratka pro **identifikátor service set**. Toto nastavení je reálným názvem bezdrátové sítě, ke které se zařízení připojí.
- **Připojit automaticky,**: Zvolte **povolit** automaticky se připojovat k této síti, když je zařízení v rozsahu. Zvolte **Zakázat**, pokud chcete zařízením zabránit v automatickém připojování.
- **Skrytá síť**: Zvolte **povolit** skrýt tuto síť ze seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.

## <a name="enterprise-profile"></a>Profil Enterprise

- **Typ Wi-Fi**: Zvolte **Enterprise**.
- **SSID**: Zkratka pro **identifikátor service set**. Toto nastavení je reálným názvem bezdrátové sítě, ke které se zařízení připojí.
- **Připojit automaticky,**: Zvolte **povolit** automaticky se připojovat k této síti, když je zařízení v rozsahu. Zvolte **Zakázat**, pokud chcete zařízením zabránit v automatickém připojování.
- **Skrytá síť**: Zvolte **povolit** skrýt tuto síť ze seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.
- **Typ protokolu EAP**: Zvolte typ protokolu EAP (Extensible Authentication) pro ověřování zabezpečených bezdrátových připojení. Možnosti: 

  - **EAP-TLS**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** - **kořenový certifikát pro ověření serveru**: Vyberte existující profil důvěryhodných kořenových certifikátů. Když se klient připojí k síti, tento certifikát se zobrazí na server a ověří připojení.

      Vyberte **OK** uložte provedené změny.

    - **Ověření klienta** - **klientský certifikát pro ověření klienta (certifikát Identity)**: Zvolte profil certifikátu, který je nasazená taky pro zařízení klienta SCEP nebo PKCS. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

      Vyberte **OK** uložte provedené změny.

  - **EAP-TTLS**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** - **kořenový certifikát pro ověření serveru**: Vyberte existující profil důvěryhodných kořenových certifikátů. Když se klient připojí k síti, tento certifikát se zobrazí na server a ověří připojení.

      Vyberte **OK** uložte provedené změny.

    - **Ověřování klientů**: Zvolte **metodu ověřování**. Možnosti:

      - **Uživatelské jméno a heslo**: Zobrazit výzvu uživateli pro uživatelské jméno a heslo pro ověření připojení. Dále zadejte:
        - **Metoda bez protokolu EAP (vnitřní identita)**: Zvolte, jak se bude připojení ověřovat. Nezapomeňte vybrat stejný protokol, který je nakonfigurovaný u sítě Wi-Fi.

          Možnosti: **Nezašifrované heslo (PAP)**, **Challenge Handshake Authentication Protocol (CHAP)**, **Microsoft CHAP (MS-CHAP)**, nebo **2 Version Microsoft CHAP (MS-CHAP v2)**

      - **Certifikáty**: Zvolte profil certifikátu, který je nasazená taky pro zařízení klienta SCEP nebo PKCS. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

        Vyberte **OK** uložte provedené změny.

      - **Ochrana identity (vnější identita)**: Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

  - **PEAP**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** - **kořenový certifikát pro ověření serveru**: Vyberte existující profil důvěryhodných kořenových certifikátů. Když se klient připojí k síti, tento certifikát se zobrazí na server a ověří připojení.

      Vyberte **OK** uložte provedené změny.

    - **Ověřování klientů**: Zvolte **metodu ověřování**. Možnosti:

      - **Uživatelské jméno a heslo**: Zobrazit výzvu uživateli pro uživatelské jméno a heslo pro ověření připojení. Dále zadejte:
        - **Metoda bez protokolu EAP pro ověřování (vnitřní identita)**: Zvolte, jak se bude připojení ověřovat. Nezapomeňte vybrat stejný protokol, který je nakonfigurovaný u sítě Wi-Fi.

          Možnosti: **Žádný** nebo **Microsoft CHAP verze 2 (MS-CHAP v2)**

      - **Certifikáty**: Zvolte profil certifikátu, který je nasazená taky pro zařízení klienta SCEP nebo PKCS. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

        Vyberte **OK** uložte provedené změny.

      - **Ochrana identity (vnější identita)**: Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

Vyberte **OK** > **Vytvořit** a změny uložte. Profil se vytvoří a zobrazí se v seznamu profilů.

## <a name="next-steps"></a>Další postup

Profil se vytvoří, ale nic nedělá. Dále [tento profil přiřadit](device-profile-assign.md) a [monitorování jejího stavu.](device-profile-monitor.md).

Můžete také vytvořit profily sítě Wi-Fi pro [Android](wi-fi-settings-android.md), [iOS](wi-fi-settings-ios.md), [macOS](wi-fi-settings-macos.md), [Windows 10](wi-fi-settings-windows.md), a [Windows 8.1](wi-fi-settings-import-windows-8-1.md)zařízení.
