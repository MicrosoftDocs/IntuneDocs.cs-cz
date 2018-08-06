---
title: Nastavení Wi-Fi pro zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Přidejte nebo vytvořte konfigurační profil pomocí nastavení Wi-Fi pro zařízení s Windows 10 nebo novější verzí v Microsoft Intune. Můžete nakonfigurovat základní nastavení nebo nastavení na podnikové úrovni.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f6532c63612b806f9824f5b9ca98f1ebbbc943f
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321623"
---
## <a name="wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Nastavení Wi-Fi pro zařízení s Windows 10 a novější verzí v Intune

Nastavení Wi-Fi se používají v konfiguračním profilu, který se vztahuje na zařízení s Windows 10 nebo novější verzí. Vaše možnosti jsou:

- Základní
- Enterprise

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil zařízení v Microsoft Intune](device-profile-create.md).

## <a name="settings-for-basic-and-enterprise-profiles"></a>Nastavení pro základní a podnikové profily

- **Název Wi-Fi (SSID):** zkratka pro Service Set Identifier. Tato hodnota je reálným názvem bezdrátové sítě, ke které se zařízení připojí. Nakonfigurovaný **Název připojení** ale uživatelé uvidí jen při volbě připojení.
- **Název připojení:** Zadejte popisný název připojení Wi-Fi. Zadaný text uživatelé uvidí na svém zařízení při procházení dostupných připojení.
- **Připojit se automaticky, pokud je v dosahu:** Když nastavíte **Ano**, zařízení se budou k této síti připojovat automaticky, když budou v dosahu. Když nastavíte **Ne**, zařízení se automaticky připojovat nebudou.
  - **Připojit k upřednostňovanější síti, pokud je k dispozici:** Pokud jsou zařízení v dosahu upřednostňovanější sítě, zvolte **Ano**, aby se k ní připojila. Pokud chcete použít síť Wi-Fi v tomto konfiguračním profilu, zvolte **Ne**.

    Například můžete vytvořit síť Wi-Fi **ContosoCorp** a v rámci tohoto konfiguračního profilu **ContosoCorp** použít. V dosahu máte i Wi-Fi **ContosoGuest**. Když jsou v dosahu vaše podniková zařízení, budete chtít, aby se automaticky připojovala k síti **ContosoCorp**. V takové situaci vlastnost **Připojit k upřednostňovanější síti, pokud je k dispozici** nastavte na **Ne**.

  - **Připojit se k této síti i v případě, že nevysílá svůj identifikátor SSID:** Pokud chcete, aby se konfigurační profil připojoval k vaší síti automaticky, i když je síť skrytá (její SSID se nevysílá veřejně), zvolte **Ano**. Pokud nechcete, aby se tento konfigurační profil připojoval ke skryté síti, zvolte **Ne**.

- **Nastavení firemního proxy:** Zvolte nastavení proxy v organizaci. Možnosti:
  - **Žádné:** nenakonfiguruje se žádné nastavení proxy.
  - **Nakonfigurovat ručně:** Zadejte **IP adresu proxy serveru** a **Číslo portu**.
  - **Automaticky nakonfigurovat:** Zadejte adresu URL, která odkazuje na skript PAC (automatická konfigurace proxy). Zadejte například `http://proxy.contoso.com/proxy.pac`.

## <a name="settings-for-basic-profiles-only"></a>Nastavení jenom pro základní profily

- **Typ zabezpečení bezdrátové sítě**: Zadejte protokol zabezpečení, který bude ověřovat zařízení v síti. Možnosti:
  - **Otevřené (bez zabezpečení):** tuto možnost použijte jenom v případě, že síť není zabezpečená.
  - **WPA/WPA2-osobní**

## <a name="settings-for-enterprise-profiles-only"></a>Nastavení jenom pro podnikové profily

- **Jednotné přihlašování:** Umožňuje vám nakonfigurovat jednotné přihlašování (SSO), u kterého se přihlašovací údaje k počítači i síti Wi-Fi sdílejí. Možnosti:
  - **Zakázat:** Jednotné přihlašování se zakáže. Uživatel se musí v síti ověřit zvlášť.
  - **Povolit dříve, než se uživatel přihlásí k zařízení:** Použití jednotného přihlašování k síti těsně předtím, než se uživatel přihlásí.
  - **Povolit, až se uživatel přihlásí k zařízení:** Použití jednotného přihlašování k síti hned poté, co se uživatel přihlásí.
  - **Maximální časový limit na ověření:** Zadejte maximální dobu, v rozmezí od 1 do 120 sekund, po kterou se bude čekat, než se provede ověření k síti.
  - **Povolit systému Windows zobrazit uživateli výzvu, aby zadal další přihlašovací údaje pro ověření:** Když zvolíte **Ano**, umožníte systému Windows vyzvat uživatele k zadání dalších přihlašovacích údajů, pokud to metoda ověřování vyžaduje. Pokud chcete tyto výzvy skrýt, zvolte **Ne**.

- **Povolit ukládání klíče PMK (Pairwise Master Key) do mezipaměti:** Pokud chcete klíč PMK používaný při ověřování ukládat do mezipaměti, zvolte **Ano**. Toto ukládání do mezipaměti obvykle ověřování k síti urychluje. Pokud chcete ověřovací signalizaci vynutit pokaždé, když se připojujete k síti Wi-Fi, zvolte **Ne**.

  - **Maximální doba, po kterou je klíč PMK uložený v mezipaměti:** Zadejte dobu, v rozmezí od 5 do 1440 minut, po kterou bude klíč PMK uložený v mezipaměti.
  - **Maximální počet klíčů PMK uložených v mezipaměti:** Zadejte počet klíčů, v rozmezí od 1 do 255, který se může uložit do mezipaměti.

- **Povolit předběžné ověření:** Předběžné ověření umožňuje profilu, který chcete ověřit, získat před připojením přístup ke všem přístupovým bodům sítě v profilu. Při přesouvání mezi přístupovými body, proběhne opětovné připojení uživatele nebo zařízení díky předběžnému ověření rychleji. Pokud chcete, aby profil provedl ověření u všech přístupových bodů, které jsou v dané síti v dosahu, zvolte **Ano**. Pokud vyžadujete, aby se uživatel nebo zařízení ověřovalo u každého přístupového bodu zvlášť, zvolte **Ne**.

  - **Maximální počet pokusů o předběžné ověření:** Zadejte počet pokusů, v rozmezí od 1 do 16, k předběžnému ověření.

- **Typ protokolu EAP:** Zvolte typ protokolu EAP pro ověřování zabezpečených bezdrátových připojení. Možnosti:

  - **EAP-SIM**
  - **EAP-TLS**
  - **EAP-TTLS**
  - **Protokol PEAP** (Protected EAP)

### <a name="more-options-when-you-choose-the-eap-type"></a>Více možnosti při volbě typu protokolu EAP

> [!NOTE]
> V současné době jsou při použití typu protokolu EAP podporované pouze profily certifikátů SCEP. Profily certifikátů PKCS podporované nejsou. Kdykoli je uživatel vyzván k zadání certifikátu, nezapomeňte vybrat certifikát SCEP.

#### <a name="server-trust"></a>Vztah důvěryhodnosti serveru

|Název nastavení|Další informace|Kdy použít|
|--------------|-------------|----------|
|**Názvy certifikačních serverů**|Zadejte jeden nebo více běžných názvů použitých v certifikátech, které vystavuje vaše důvěryhodná certifikační autorita. Když tento údaj zadáte, můžete obejít dialog dynamického vztahu důvěryhodnosti, který se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.|Typ EAP je **EAP-TLS**, **EAP-TTLS** nebo **PEAP**.|
|**Kořenový certifikát pro ověřování serveru**|Zvolte profil důvěryhodného kořenového certifikátu pro ověření připojení. |Typ EAP je **EAP-TLS**, **EAP-TTLS** nebo **PEAP**.|
|**Ochrana identity (vnější identita)**|Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.|Typ EAP je **PEAP**.|

#### <a name="client-authentication"></a>Ověření klienta

| Název nastavení | Další informace | Kdy použít |
|---|---|---|
| **Klientský certifikát pro ověření klienta (certifikát identity)** |  Vyberte profil certifikátu SCEP použitý k ověření připojení. | Typ EAP je **EAP-TLS**. |
| **Metoda ověřování** | Vyberte metodu ověřování připojení:<br><br>- **Certifikáty:** vyberte klientský certifikát SCEP, který je certifikátem identity předloženým serveru.<br><br>- **Uživatelské jméno a heslo:** Zadejte metodu ověřování **Metoda bez protokolu EAP (vnitřní identita)**. Možnosti:<br><br>- **Nezašifrované heslo (PAP)**<br>- **Protokol CHAP (Challenge Handshake)**<br>- **Protokol Microsoft CHAP (MS-CHAP)**<br>- **Protokol Microsoft CHAP verze 2 (MS-CHAP v2)**<br><br>- **Ochrana identity (vnější identita):** zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení. | Typ EAP je **EAP-TTLS**. |

## <a name="use-an-imported-settings-file"></a>Importování souboru nastavení

Pro libovolné nastavení, které není v Intune k dispozici, můžete exportovat nastavení Wi-Fi z jiného zařízení s Windows. Tento export vytvoří soubor XML se všemi nastaveními. Potom tento soubor importujte do Intune a použijte ho jako profil Wi-Fi. Viz [Import nastavení Wi-Fi pro zařízení s Windows 8.1 a novější verzí v Microsoft Intune](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>Další kroky
[Jak nakonfigurovat nastavení Wi-Fi v Microsoft Intune](wi-fi-settings-configure.md)
