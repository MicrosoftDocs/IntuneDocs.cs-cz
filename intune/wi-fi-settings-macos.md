---
title: Konfigurace nastavení Wi-Fi pro zařízení macOS v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Vytvořte nebo přidejte konfigurační profil zařízení s připojením Wi-Fi pro zařízení s macOS. Podívejte se na různá nastavení, včetně přidání certifikátů, volby typu protokolu EAP a výběru metody ověřování v Microsoft Intune.
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
ms.openlocfilehash: fe04a66ee8ac8aa346d131321910c291f88e9754
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57391624"
---
# <a name="add-wi-fi-settings-for-macos-devices-in-microsoft-intune"></a>Přidání nastavení Wi-Fi pro zařízení s macOS v Microsoft Intune

Můžete vytvořit profil s konkrétním nastavením Wi-Fi a potom ho nasadit na zařízení s macOS. Microsoft Intune nabízí mnoho funkcí, například ověřování v síti, přidání certifikátu PKS nebo SCEP a další.

Tato nastavení Wi-Fi jsou v oddělené do dvou kategorií: Základní nastavení a nastavení na podnikové úrovni.

Těmito nastaveními se zabývá tento článek.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil zařízení v Microsoft Intune](device-profile-create.md).

## <a name="basic-profiles"></a>Základní profily

- **Typ Wi-Fi**: Zvolte **Základní**.
- **Název sítě**: Zadejte název pro toto připojení Wi-Fi. Tato hodnota představuje název, který uživatelé na svém zařízení uvidí při procházení seznamu dostupných připojení.
- **SSID**: Zkratka pro **identifikátor service set**. Tato vlastnost je reálným názvem bezdrátové sítě, ke které se zařízení připojí. Název sítě, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Připojit automaticky,**: Zvolte **povolit** automaticky se připojovat k této síti, když je zařízení v rozsahu. Zvolte **Zakázat**, pokud chcete zařízením zabránit v automatickém připojování.
- **Skrytá síť**: Zvolte **povolit** skrýt tuto síť ze seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.
- **Typ zabezpečení**: Vyberte protokol zabezpečení pro ověřování sítě Wi-Fi. Možnosti:

  - **Otevřené (bez ověření)**: Tuto možnost použijte pouze v případě, že síť není zabezpečená.
  - **WPA/WPA2 - osobní**: Zadejte heslo **předsdílený klíč**. Po nastavení nebo konfiguraci firemní sítě se nakonfiguruje také heslo nebo síťový klíč. Toto heslo nebo síťový klíč zadejte jako hodnotu PSK.
  - **WEP**

- **Nastavení proxy serveru**: Možnosti:
  - **Žádný**: Žádné nastavení proxy serveru jsou nakonfigurované.
  - **Ruční**: Zadejte **adresa Proxy serveru** jako IP adresu a jeho **číslo portu**.
  - **Automatické**: Pomocí souboru konfigurace proxy serveru. Zadejte **adresu URL proxy serveru** (například `http://proxy.contoso.com`), na které se nachází konfigurační soubor.

## <a name="enterprise-profiles"></a>Profily Enterprise

- **Typ Wi-Fi**: Zvolte **Enterprise**.
- **SSID**: Zkratka pro **identifikátor service set**. Tato vlastnost je reálným názvem bezdrátové sítě, ke které se zařízení připojí. Název sítě, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Připojit automaticky,**: Zvolte **povolit** automaticky se připojovat k této síti, když je zařízení v rozsahu. Zvolte **Zakázat**, pokud chcete zařízením zabránit v automatickém připojování.
- **Skrytá síť**: Zvolte **povolit** skrýt tuto síť ze seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.

- **Typ protokolu EAP**: Zvolte typ protokolu EAP (Extensible Authentication) pro ověřování zabezpečených bezdrátových připojení. Možnosti:

  - **EAP-FAST**: Zadejte **nastavení přihlašovacích údajů (PAC) přístup k chráněné**. Tato možnost používá přihlašovací údaje chráněného přístupu k vytvoření ověřeného tunelového propojení mezi klientem a serverem ověřování. Možnosti:
    - **Nepoužívat (PAC)**
    - **Používat PAC**: Pokud existuje stávající soubor PAC, použijte ji.
    - **Používat a zřídit PAC**: Vytvořit a přidat soubor PAC ve vašich zařízeních.
    - **Používat a zřídit PAC anonymně**: Vytvořit a přidat soubor PAC ve vašich zařízeních bez ověřování serveru.

  - **EAP-SIM**

  - **EAP-TLS**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** - **server zvy důvěryhodných certifikátů**: **Přidat** jeden nebo více běžných názvů použitých v certifikátech vystavených vaší důvěryhodné certifikační autority (CA). Když tento údaj zadáte, můžete obejít okno dynamického vztahu důvěryhodnosti, které se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.
    - **Kořenový certifikát pro ověření serveru**: Vyberte existující profil důvěryhodných kořenových certifikátů. Tento certifikát se předloží serveru při připojení klienta k síti a slouží k ověření připojení.

      Vyberte **OK** uložte provedené změny.

    - **Ověření klienta** - **klientský certifikát pro ověření klienta (certifikát Identity)**: Zvolte profil certifikátu, který je nasazená taky pro zařízení klienta SCEP nebo PKCS. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

      Vyberte **OK** uložte provedené změny.

  - **EAP-TTLS**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** - **server zvy důvěryhodných certifikátů**: **Přidat** jeden nebo více běžných názvů použitých v certifikátech vystavených vaší důvěryhodné certifikační autority (CA). Když tento údaj zadáte, můžete obejít okno dynamického vztahu důvěryhodnosti, které se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.
    - **Kořenový certifikát pro ověření serveru**: Vyberte existující profil důvěryhodných kořenových certifikátů. Tento certifikát se předloží serveru při připojení klienta k síti a slouží k ověření připojení.

      Vyberte **OK** uložte provedené změny.

    - **Ověřování klientů**: Zvolte **metodu ověřování**. Možnosti:

      - **Uživatelské jméno a heslo**: Zobrazit výzvu uživateli pro uživatelské jméno a heslo pro ověření připojení. Dále zadejte:
        - **Metoda bez protokolu EAP (vnitřní identita)**: Zvolte, jak se bude připojení ověřovat. Nezapomeňte vybrat stejný protokol, který je nakonfigurovaný u sítě Wi-Fi.

          Možnosti: **Nezašifrované heslo (PAP)**, **Challenge Handshake Authentication Protocol (CHAP)**, **Microsoft CHAP (MS-CHAP)**, nebo **2 Version Microsoft CHAP (MS-CHAP v2)**

      - **Certifikáty**: Zvolte profil certifikátu, který je nasazená taky pro zařízení klienta SCEP nebo PKCS. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

        Vyberte **OK** uložte provedené změny.

      - **Ochrana identity (vnější identita)**: Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

  - **LEAP**

  - **PEAP**: Dále zadejte:

    - **Vztah důvěryhodnosti serveru** - **server zvy důvěryhodných certifikátů**: **Přidat** jeden nebo více běžných názvů použitých v certifikátech vystavených vaší důvěryhodné certifikační autority (CA). Když tento údaj zadáte, můžete obejít okno dynamického vztahu důvěryhodnosti, které se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.
    - **Kořenový certifikát pro ověření serveru**: Vyberte existující profil důvěryhodných kořenových certifikátů. Tento certifikát se předloží serveru při připojení klienta k síti a slouží k ověření připojení.

      Vyberte **OK** uložte provedené změny.

    - **Ověřování klientů**: Zvolte **metodu ověřování**. Možnosti:

      - **Uživatelské jméno a heslo**: Zobrazit výzvu uživateli pro uživatelské jméno a heslo pro ověření připojení. 

      - **Certifikáty**: Zvolte profil certifikátu, který je nasazená taky pro zařízení klienta SCEP nebo PKCS. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

        Vyberte **OK** uložte provedené změny.

      - **Ochrana identity (vnější identita)**: Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

- **Nastavení proxy serveru**: Možnosti:
  - **Žádný**: Žádné nastavení proxy serveru jsou nakonfigurované.
  - **Ruční**: Zadejte **adresa Proxy serveru** jako IP adresu a jeho **číslo portu**.
  - **Automatické**: Pomocí souboru konfigurace proxy serveru. Zadejte **adresu URL proxy serveru** (například `http://proxy.contoso.com`), na které se nachází konfigurační soubor.

Vyberte **OK** > **Vytvořit** a změny uložte. Profil se vytvoří a zobrazí se v seznamu profilů.

## <a name="next-steps"></a>Další postup

Profil se vytvoří, ale nic nedělá. Dále [tento profil přiřaďte](device-profile-assign.md).

## <a name="more-resources"></a>Další materiály

[Přehled nastavení Wi-Fi](wi-fi-settings-configure.md), včetně dalších dostupných platforem
