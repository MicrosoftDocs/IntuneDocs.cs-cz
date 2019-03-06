---
title: Konfigurace nastavení Wi-Fi pro zařízení s Androidem v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Vytvořte nebo přidejte konfigurační profil zařízení s připojením Wi-Fi pro Android. Podívejte se na různá nastavení, včetně přidání certifikátů, volby typu protokolu EAP a výběru metody ověřování v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 772a7f0e02691350a9c1feb16210a9390add3580
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57397879"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Přidání nastavení Wi-Fi pro zařízení s Androidem v Microsoft Intune

Můžete vytvořit profil s konkrétním nastavením Wi-Fi a potom ho nasadit na zařízení s Androidem. Microsoft Intune nabízí mnoho funkcí, například ověřování v síti, přidání certifikátu PKS nebo SCEP a další.

Tato nastavení Wi-Fi jsou v oddělené do dvou kategorií: Základní nastavení a nastavení na podnikové úrovni.

Těmito nastaveními se zabývá tento článek.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil zařízení v Microsoft Intune](device-profile-create.md).

## <a name="basic-profile"></a>Základní profil

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

    - **Vztah důvěryhodnosti serveru** - **kořenový certifikát pro ověření serveru**: Vyberte existující profil důvěryhodných kořenových certifikátů. Tento certifikát se předloží serveru při připojení klienta k síti a slouží k ověření připojení.

      Vyberte **OK** uložte provedené změny.

    - **Ověření klienta** - **klientský certifikát pro ověření klienta (certifikát Identity)**: Zvolte profil certifikátu, který je nasazená taky pro zařízení klienta SCEP nebo PKCS. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

      Vyberte **OK** uložte provedené změny.

  - **EAP-TTLS**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** - **kořenový certifikát pro ověření serveru**: Vyberte existující profil důvěryhodných kořenových certifikátů. Tento certifikát se předloží serveru při připojení klienta k síti a slouží k ověření připojení.

      Vyberte **OK** uložte provedené změny.

    - **Ověřování klientů**: Zvolte **metodu ověřování**. Možnosti:

      - **Uživatelské jméno a heslo**: Zobrazit výzvu uživateli pro uživatelské jméno a heslo pro ověření připojení. Dále zadejte:
        - **Metoda bez protokolu EAP (vnitřní identita)**: Zvolte, jak se bude připojení ověřovat. Nezapomeňte vybrat stejný protokol, který je nakonfigurovaný u sítě Wi-Fi.

          Možnosti: **Nezašifrované heslo (PAP)**, **Challenge Handshake Authentication Protocol (CHAP)**, **Microsoft CHAP (MS-CHAP)**, nebo **2 Version Microsoft CHAP (MS-CHAP v2)**

      - **Certifikáty**: Zvolte profil certifikátu, který je nasazená taky pro zařízení klienta SCEP nebo PKCS. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

        Vyberte **OK** uložte provedené změny.

      - **Ochrana identity (vnější identita)**: Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

  - **PEAP**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** - **kořenový certifikát pro ověření serveru**: Vyberte existující profil důvěryhodných kořenových certifikátů. Tento certifikát se předloží serveru při připojení klienta k síti a slouží k ověření připojení.

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

Profil se vytvoří, ale nic nedělá. Dále [tento profil přiřaďte](device-profile-assign.md).

## <a name="more-resources"></a>Další materiály

- [Přehled nastavení Wi-Fi](wi-fi-settings-configure.md), včetně dalších platforem

- Používáte zařízení s Androidem Enterprise nebo beznabídkovým režimem Androidu? Pokud ano, přečtěte si článek o [nastavení Wi-Fi pro zařízení s Androidem Enterprise a s beznabídkovým režimem Androidu](wi-fi-settings-android-enterprise.md).
