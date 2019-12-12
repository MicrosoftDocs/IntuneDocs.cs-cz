---
title: Konfigurace nastavení drátové sítě pro zařízení macOS v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Vytvořte nebo přidejte konfigurační profil zařízení s drátovou sítí pro zařízení macOS. Podívejte se na různá nastavení, včetně přidání certifikátů, volby typu protokolu EAP a výběru metody ověřování v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/4/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7dba36d03489bcdeee3c3c1f69a4995823dd21ee
ms.sourcegitcommit: df8e2c052fafb2d5d4e9b4fcd831ae0ecf7f8d16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/10/2019
ms.locfileid: "74994292"
---
# <a name="add-wired-network-settings-for-macos-devices-in-microsoft-intune"></a>Přidat nastavení pevné sítě pro zařízení macOS v Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Můžete vytvořit profil s konkrétními nastaveními drátové sítě a potom tento profil nasadit do zařízení macOS. Microsoft Intune nabízí mnoho funkcí, například ověřování v síti, přidání certifikátu PKS nebo SCEP a další. 

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil zařízení v Microsoft Intune](device-profile-create.md).

> [!NOTE]
> Tato nastavení jsou k dispozici pro všechny typy registrace. Další informace o typech registrace najdete v tématu [registrace MacOS](../enrollment/macos-enroll.md).

## <a name="profiles"></a>Profily

- **Typ profilu**: vyberte možnost **drátová síť**.
- **Síťové rozhraní**: 
- **Typ EAP**: Zvolte typ protokolu EAP (Extensible Authentication Protocol) pro ověřování zabezpečených bezdrátových připojení. Možnosti:
  - **EAP-FAST**: Zadejte **nastavení PAC (Protected Access Credential)** . Tato možnost používá přihlašovací údaje chráněného přístupu k vytvoření ověřeného tunelového propojení mezi klientem a serverem ověřování. Možnosti:
    - **Nepoužívat (PAC)**
    - **Používat (PAC)** : Pokud existuje soubor PAC, použijte ho.
    - **Používat a zřídit PAC**: Vytvoří a přidá soubor PAC do zařízení.
    - **Používat a zřídit PAC anonymně**: Vytvoří a přidá soubor PAC do zařízení bez ověřování na serveru.
  - **EAP-TLS**: Dále zadejte:
    - **Vztah důvěryhodnosti serveru** – **Názvy certifikačních serverů**: **Přidejte** minimálně jeden název použitý v certifikátech, které vystavuje vaše důvěryhodná certifikační autorita. Když tento údaj zadáte, můžete obejít okno dynamického vztahu důvěryhodnosti, které se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.
    - **Kořenový certifikát pro ověřování serveru**: Zvolte existující profil důvěryhodného kořenového certifikátu. Tento certifikát se předloží serveru při připojení klienta k síti a slouží k ověření připojení.
    - **Ověřování klientů** – **Klientský certifikát pro ověření klienta (certifikát identity)** : Zvolte profil klientského certifikátu SCEP nebo PKCS, který je také nasazený na zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.
  - **EAP-TTLS**: Dále zadejte:
    - **Vztah důvěryhodnosti serveru** – **Názvy certifikačních serverů**: **Přidejte** minimálně jeden název použitý v certifikátech, které vystavuje vaše důvěryhodná certifikační autorita. Když tento údaj zadáte, můžete obejít okno dynamického vztahu důvěryhodnosti, které se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.
    - **Kořenový certifikát pro ověřování serveru**: Zvolte existující profil důvěryhodného kořenového certifikátu. Tento certifikát se předloží serveru při připojení klienta k síti a slouží k ověření připojení.
    - **Ověřování klientů**: Zvolte **metodu ověřování**. Možnosti:
      - **Uživatelské jméno a heslo**: Zobrazí uživateli výzvu k zadání uživatelského jména a hesla pro ověření připojení. Dále zadejte:
        - **Metoda bez protokolu EAP (vnitřní identita)** : Zvolte, jak chcete připojení ověřovat. Nezapomeňte vybrat stejný protokol, který je nakonfigurovaný u sítě Wi-Fi.
          Máte tyto možnosti: **Nešifrované heslo (PAP)** , **CHAP (Challenge Handshake Authentication Protocol)** , **Microsoft CHAP (MS-CHAP)** nebo **Microsoft CHAP verze 2 (MS-CHAP v2)** .
      - **Certifikáty**: Zvolte profil klientského certifikátu SCEP nebo PKCS, který je také nasazený na zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.
      - **Ochrana identity (vnější identita)** : Zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.
  - **LEAP**
  - **PEAP**: Dále zadejte:
    - **Vztah důvěryhodnosti serveru** – **Názvy certifikačních serverů**: **Přidejte** minimálně jeden název použitý v certifikátech, které vystavuje vaše důvěryhodná certifikační autorita. Když tento údaj zadáte, můžete obejít okno dynamického vztahu důvěryhodnosti, které se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.
    - **Kořenový certifikát pro ověřování serveru**: Zvolte existující profil důvěryhodného kořenového certifikátu. Tento certifikát se předloží serveru při připojení klienta k síti a slouží k ověření připojení.
    - **Ověřování klientů**: Zvolte **metodu ověřování**. Možnosti:
      - **Uživatelské jméno a heslo**: Zobrazí uživateli výzvu k zadání uživatelského jména a hesla pro ověření připojení. 
      - **Certifikáty**: Zvolte profil klientského certifikátu SCEP nebo PKCS, který je také nasazený na zařízení. Tento certifikát představuje identitu, kterou zařízení předloží serveru pro ověření připojení.
      - **Ochrana identity (vnější identita)** : Zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota, například `anonymous`. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

## <a name="next-steps"></a>Další kroky

Profil se vytvoří, ale nic nedělá. Dále [přiřaďte tento profil](device-profile-assign.md) a [sledujte jeho stav](device-profile-monitor.md).

Konfigurace nastavení Wi-Fi na zařízeních s [Androidem](wi-fi-settings-android.md), [Androidem Enterprise](wi-fi-settings-android-enterprise.md), [iOS](wi-fi-settings-ios.md)a [Windows 10](wi-fi-settings-windows.md)
