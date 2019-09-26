---
title: Konfigurace nastavení Wi-Fi pro zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Vytvořte nebo přidejte konfigurační profil zařízení s připojením Wi-Fi pro zařízení s iOSem. Podívejte se na různá nastavení, včetně přidání certifikátů, volby typu protokolu EAP a výběru metody ověřování v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2358ec854e9cc78cbc36570c45a96b98d2844f5d
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71302582"
---
# <a name="add-wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>Přidání nastavení Wi-Fi pro zařízení s iOSem v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Můžete vytvořit profil s konkrétním nastavením Wi-Fi a potom ho nasadit na zařízení s iOSem. Microsoft Intune nabízí mnoho funkcí, například ověřování v síti, přidání certifikátu PKS nebo SCEP a další.

Tato nastavení sítě Wi-Fi jsou rozdělená do dvou kategorií: Základní nastavení a nastavení na podnikové úrovni.

Těmito nastaveními se zabývá tento článek.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil zařízení v Microsoft Intune](device-profile-create.md).

> [!NOTE]
> Tato nastavení jsou k dispozici pro všechny typy registrace. Další informace o typech registrace najdete v tématu Registrace zařízení se [systémem iOS](ios-enroll.md).

## <a name="basic-profiles"></a>Základní profily

- **Typ Wi-Fi**: Zvolte **Základní**.
- **Název sítě**: Zadejte název pro toto připojení Wi-Fi. Tato hodnota představuje název, který uživatelé na svém zařízení uvidí při procházení seznamu dostupných připojení.
- **IDENTIFIKÁTOR SSID**: Zkratka pro **identifikátor sady služeb**je krátký. Tato vlastnost je reálným názvem bezdrátové sítě, ke které se zařízení připojí. Název sítě, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Připojit automaticky**: Pokud je zařízení v dosahu, vyberte **Povolit** pro automatické připojení k této síti. Zvolte **Zakázat**, pokud chcete zařízením zabránit v automatickém připojování.
- **Skrytá síť**: Pokud se identifikátor SSID sítě nevysílá, vyberte **Povolit** . Pokud je SSID sítě všesměrové a viditelné, vyberte **Zakázat** .
- **Typ zabezpečení**: Vyberte protokol zabezpečení pro ověření v síti Wi-Fi. Možnosti:

  - **Otevřené (bez ověřování)** : Tuto možnost použijte pouze v případě, že síť není zabezpečená.
  - **WPA/WPA2 – osobní**: Zadejte heslo do **předsdíleného klíče**. Po nastavení nebo konfiguraci firemní sítě se nakonfiguruje také heslo nebo síťový klíč. Toto heslo nebo síťový klíč zadejte jako hodnotu PSK.
  - **WEP**

- **Nastavení proxy serveru**: Možnosti:
  - **Žádný**: Nejsou nakonfigurovaná žádná nastavení proxy serveru.
  - **Ruční**: Zadejte **adresu proxy serveru** jako IP adresu a **číslo portu**.
  - **Automaticky**: Pomocí souboru Nakonfigurujte proxy server. Zadejte **adresu URL proxy serveru** (například `http://proxy.contoso.com`), na které se nachází konfigurační soubor.

## <a name="enterprise-profiles"></a>Profily Enterprise

- **Typ Wi-Fi**: Vyberte **Enterprise**.
- **IDENTIFIKÁTOR SSID**: Zkratka pro **identifikátor sady služeb**je krátký. Tato vlastnost je reálným názvem bezdrátové sítě, ke které se zařízení připojí. Název sítě, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Připojit automaticky**: Pokud je zařízení v dosahu, vyberte **Povolit** pro automatické připojení k této síti. Zvolte **Zakázat**, pokud chcete zařízením zabránit v automatickém připojování.
- **Skrytá síť**: Zvolením možnosti **Povolit** skryjete tuto síť ze seznamu dostupných sítí na zařízení. Identifikátor SSID se všesměrově nevysílá. Zvolte **Zakázat**, pokud tuto síť chcete v seznamu dostupných sítí na zařízení zobrazit.

- **Typ protokolu EAP**: Vyberte typ protokolu EAP (Extensible Authentication Protocol) používaný k ověřování zabezpečených bezdrátových připojení. Možnosti:

  - **EAP-FAST**: Zadejte **nastavení Protected Access Credential (PAC)** . Tato možnost používá přihlašovací údaje chráněného přístupu k vytvoření ověřeného tunelového propojení mezi klientem a serverem ověřování. Možnosti:
    - **Nepoužívat (PAC)**
    - **Použít (PAC)** : Pokud existující soubor PAC existuje, použijte ho.
    - **Použít a ZŘÍDIT PAC**: Vytvořte soubor PAC a přidejte ho do zařízení.
    - **Použít a ZŘÍDIT PAC anonymně**: Vytvořte a přidejte soubor PAC do zařízení bez ověřování na serveru.

  - **EAP-SIM**

  - **EAP-TLS**: Dále zadejte:

    - **Názvy důvěryhodných** - **certifikátů**serveru: **Přidejte** jeden nebo více běžných názvů používaných v certifikátech vydaných vaší důvěryhodnou certifikační autoritou (CA) na servery bezdrátové sítě pro přístup. Například přidejte `mywirelessserver.contoso.com` nebo `mywirelessserver`. Když tento údaj zadáte, můžete obejít okno dynamického vztahu důvěryhodnosti, které se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.
    - **Kořenový certifikát pro ověření serveru**: Vyberte existující profil důvěryhodného kořenového certifikátu. Tento certifikát umožňuje klientovi, aby důvěřoval certifikátu serveru pro přístup k bezdrátové síti.

    -  - **Klientský certifikát pro ověření klienta pro ověření klienta (certifikát identity)** : Vyberte profil certifikátu klienta SCEP nebo PKCS, který je také nasazený do zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

  - **EAP-TTLS**: Dále zadejte:

    - **Názvy důvěryhodných** - **certifikátů**serveru: **Přidejte** jeden nebo více běžných názvů používaných v certifikátech vydaných vaší důvěryhodnou certifikační autoritou (CA) na servery bezdrátové sítě pro přístup. Například přidejte `mywirelessserver.contoso.com` nebo `mywirelessserver`. Když tento údaj zadáte, můžete obejít okno dynamického vztahu důvěryhodnosti, které se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.
    - **Kořenový certifikát pro ověření serveru**: Vyberte existující profil důvěryhodného kořenového certifikátu. Tento certifikát umožňuje klientovi, aby důvěřoval certifikátu serveru pro přístup k bezdrátové síti.

    - **Ověřování klientů**: Zvolte **metodu ověřování**. Možnosti:

      - **Uživatelské jméno a heslo**: Pro ověření připojení vyzvat uživatele k zadání uživatelského jména a hesla. Dále zadejte:
        - **Metoda bez protokolu EAP (vnitřní identita)** : Vyberte způsob ověřování připojení. Nezapomeňte vybrat stejný protokol, který je nakonfigurovaný u sítě Wi-Fi.

          Možnosti: **Nešifrované heslo (PAP)** , **protokol CHAP (Challenge Handshake Authentication Protocol)** , **Microsoft CHAP (ms-CHAP)** nebo **Microsoft CHAP verze 2 (MS-CHAP v2)**

      - **Certifikáty**: Vyberte profil certifikátu klienta SCEP nebo PKCS, který je také nasazený do zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

      - **Ochrana identity (vnější identita)** : Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

  - **LEAP**

  - **PEAP**: Dále zadejte:

    - **Názvy důvěryhodných** - **certifikátů**serveru: **Přidejte** jeden nebo více běžných názvů používaných v certifikátech vydaných vaší důvěryhodnou certifikační autoritou (CA) na servery bezdrátové sítě pro přístup. Například přidejte `mywirelessserver.contoso.com` nebo `mywirelessserver`. Když tento údaj zadáte, můžete obejít okno dynamického vztahu důvěryhodnosti, které se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.
    - **Kořenový certifikát pro ověření serveru**: Vyberte existující profil důvěryhodného kořenového certifikátu. Tento certifikát umožňuje klientovi, aby důvěřoval certifikátu serveru pro přístup k bezdrátové síti.

    - **Ověřování klientů**: Zvolte **metodu ověřování**. Možnosti:

      - **Uživatelské jméno a heslo**: Pro ověření připojení vyzvat uživatele k zadání uživatelského jména a hesla. 

      - **Certifikáty**: Vyberte profil certifikátu klienta SCEP nebo PKCS, který je také nasazený do zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.

      - **Ochrana identity (vnější identita)** : Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

- **Nastavení proxy serveru**: Možnosti:
  - **Žádný**: Nejsou nakonfigurovaná žádná nastavení proxy serveru.
  - **Ruční**: Zadejte **adresu proxy serveru** jako IP adresu a **číslo portu**.
  - **Automaticky**: Pomocí souboru Nakonfigurujte proxy server. Zadejte **adresu URL proxy serveru** (například `http://proxy.contoso.com`), na které se nachází konfigurační soubor.

## <a name="next-steps"></a>Další kroky

Profil se vytvoří, ale nic nedělá. Dále [přiřaďte tento profil](device-profile-assign.md)a [sledujte jeho stav](device-profile-monitor.md).

Konfigurace nastavení Wi-Fi na zařízeních s [Androidem](wi-fi-settings-android.md), [Androidem Enterprise](wi-fi-settings-android-enterprise.md), [MacOS](wi-fi-settings-macos.md)a [Windows 10](wi-fi-settings-windows.md)
