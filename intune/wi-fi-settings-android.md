---
title: Konfigurace nastavení Wi-Fi pro zařízení s Androidem v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Vytvořte nebo přidejte konfigurační profil zařízení s připojením Wi-Fi pro Android. Podívejte se na různá nastavení, včetně přidání certifikátů, volby typu protokolu EAP a výběru metody ověřování v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/06/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1d341aeace950f62ae699aa7760a65c0fd2f74fa
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69550049"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Přidání nastavení Wi-Fi pro zařízení s Androidem v Microsoft Intune

Můžete vytvořit profil s konkrétním nastavením Wi-Fi a potom ho nasadit na zařízení s Androidem. Microsoft Intune nabízí mnoho funkcí, například ověřování v síti, přidání certifikátu PKS nebo SCEP a další.

Tato nastavení sítě Wi-Fi jsou rozdělená do dvou kategorií: Základní nastavení a nastavení na podnikové úrovni.

Těmito nastaveními se zabývá tento článek.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil zařízení v Microsoft Intune](device-profile-create.md).

## <a name="basic"></a>Basic

- **Typ Wi-Fi**: Zvolte **Základní**.
- **IDENTIFIKÁTOR SSID**: Zadejte **identifikátor sady služeb**, což je skutečný název bezdrátové sítě, ke které se zařízení připojují. **Název sítě**, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Připojit automaticky**: Pokud je zařízení v dosahu, vyberte **Povolit** pro automatické připojení k této síti. Zvolte **Zakázat**, pokud chcete zařízením zabránit v automatickém připojování.
- **Skrytá síť**: Zvolením možnosti **Povolit** skryjete tuto síť ze seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.

## <a name="enterprise"></a>Enterprise

- **Typ Wi-Fi**: Vyberte **Enterprise**.
- **IDENTIFIKÁTOR SSID**: Zadejte **identifikátor sady služeb**, což je skutečný název bezdrátové sítě, ke které se zařízení připojují. **Název sítě**, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Připojit automaticky**: Pokud je zařízení v dosahu, vyberte **Povolit** pro automatické připojení k této síti. Zvolte **Zakázat**, pokud chcete zařízením zabránit v automatickém připojování.
- **Skrytá síť**: Zvolením možnosti **Povolit** skryjete tuto síť ze seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.
- **Typ protokolu EAP**: Vyberte typ protokolu EAP (Extensible Authentication Protocol) používaný k ověřování zabezpečených bezdrátových připojení. Možnosti: 

  - **EAP-TLS**: Dále zadejte:

    -  - **Kořenový certifikát důvěryhodnosti serveru pro ověření serveru**: Vyberte existující profil důvěryhodného kořenového certifikátu. Tento certifikát je prezentován serveru, když se klient připojí k síti. Ověřuje připojení.

    -  - **Klientský certifikát pro ověření klienta pro ověření klienta (certifikát identity)** : Vyberte profil certifikátu klienta SCEP nebo PKCS, který je také nasazený do zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

    - **Ochrana identity (vnější identita)** : Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

  - **EAP-TTLS**: Dále zadejte:

    -  - **Kořenový certifikát důvěryhodnosti serveru pro ověření serveru**: Vyberte existující profil důvěryhodného kořenového certifikátu. Tento certifikát je prezentován serveru, když se klient připojí k síti. Ověřuje připojení.

    - **Ověřování klientů**: Vyberte **metodu ověřování**. Možnosti:

      - **Uživatelské jméno a heslo**: Pro ověření připojení vyzvat uživatele k zadání uživatelského jména a hesla. Dále zadejte:
        - **Metoda bez protokolu EAP (vnitřní identita)** : Vyberte způsob ověřování připojení. Nezapomeňte vybrat stejný protokol, který je nakonfigurovaný u sítě Wi-Fi. Možnosti:

          - **Nezašifrované heslo (PAP)**
          - **Protokol CHAP (Challenge Handshake Authentication Protocol)**
          - **Protokol Microsoft CHAP (MS-CHAP)**
          - **Protokol Microsoft CHAP verze 2 (MS-CHAP v2)**

      - **Certifikáty**: Vyberte profil certifikátu klienta SCEP nebo PKCS, který je také nasazený do zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

      - **Ochrana identity (vnější identita)** : Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

  - **PEAP**: Dále zadejte:

    -  - **Kořenový certifikát důvěryhodnosti serveru pro ověření serveru**: Vyberte existující profil důvěryhodného kořenového certifikátu. Tento certifikát je prezentován serveru, když se klient připojí k síti. Ověřuje připojení.

    - **Ověřování klientů**: Vyberte **metodu ověřování**. Možnosti:

      - **Uživatelské jméno a heslo**: Pro ověření připojení vyzvat uživatele k zadání uživatelského jména a hesla. Dále zadejte:
        - **Metoda bez protokolu EAP pro ověřování (vnitřní identita)** : Vyberte způsob ověřování připojení. Nezapomeňte vybrat stejný protokol, který je nakonfigurovaný u sítě Wi-Fi. Možnosti:

          - **Žádné**
          - **Protokol Microsoft CHAP verze 2 (MS-CHAP v2)**

      - **Certifikáty**: Vyberte profil certifikátu klienta SCEP nebo PKCS, který je také nasazený do zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

      - **Ochrana identity (vnější identita)** : Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

## <a name="next-steps"></a>Další kroky

Profil se vytvoří, ale nic nedělá. Dále [tento profil přiřaďte](device-profile-assign.md).

## <a name="more-resources"></a>Další materiály

- [Přehled nastavení Wi-Fi](wi-fi-settings-configure.md), včetně dalších platforem

- Používáte zařízení s Androidem Enterprise nebo beznabídkovým režimem Androidu? Pokud ano, podívejte se na [nastavení Wi-Fi pro zařízení s Androidem Enterprise a vyhrazenými zařízeními](wi-fi-settings-android-enterprise.md).
