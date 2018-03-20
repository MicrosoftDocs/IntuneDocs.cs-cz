---
title: "Konfigurace nastavení Wi-Fi v Microsoft Intune pro zařízení s iOSem"
titleSuffix: 
description: "Zjistěte, jak v Intune konfigurovat nastavení Wi-Fi pro zařízení s iOSem"
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fcb21657d8abe1c966aa924993f733b039302268
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>Nastavení Wi-Fi pro zařízení s iOSem v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Tento článek ukazuje nastavení Wi-Fi, která můžete nakonfigurovat v Microsoft Intune pro zařízení s iOSem.

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Nastavení Wi-Fi pro základní a podnikové profily

- **Název sítě** – zadejte název pro toto připojení Wi-Fi. Jedná se o název, který uživatelé na svém zařízení uvidí při procházení seznamu dostupných připojení.
- **SSID** – zkratka pro Service Set Identifier. Jedná se o reálný název bezdrátové sítě, ke které se zařízení připojí. Název sítě, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
- **Připojovat automaticky** – nastaví, aby se zařízení připojilo, kdykoli je v dosahu této sítě.
- **Skrytá síť** – zabrání zobrazování této sítě v seznamu dostupných sítí na zařízení.
- **Předsdílený klíč** - 
- **Nastavení proxy** – zvolte z těchto možností:
    - **Žádné** – nenakonfiguruje se žádné nastavení proxy.
    - **Ručně** – zadejte **adresu proxy serveru** (ve formě IP adresy) a její přidružené **číslo portu**.
    - **Automaticky** – ke konfiguraci proxy serveru se použije soubor. Zadejte **Adresu URL proxy serveru** (například **http://proxy.contoso.com**), na které se nachází konfigurační soubor.

## <a name="wi-fi-settings-for-basic-profiles-only"></a>Nastavení Wi-Fi jenom pro základní profily

- **Typ zabezpečení** – vyberte protokol zabezpečení, který se má použít k ověření sítě Wi-Fi:
    - **Otevřené (bez zabezpečení)** – tuto možnost použijte jenom v případě, že síť není zabezpečená.
    - **WPA/WPA2 – Osobní**
    - **WEP**

## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Nastavení Wi-Fi jenom pro podnikové profily

- **Typ EAP** – zvolte typ protokolu EAP (Extensible Authentication Protocol) použitý k ověřování zabezpečených bezdrátových připojení:
    - **EAP-FAST**
    - **EAP-SIM**
    - **EAP-TLS**
    - **EAP-TTLS**
    - **LEAP**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>Další možnosti při volbě typu EAP


|Název nastavení|Další informace|Kdy použít|
|--------------|-------------|----------|
|**Nastavení PAC (Protected Access Credential)**|Toto nastavení vyberte, pokud chcete použít přihlašovací údaje chráněného přístupu k navázání ověřeného tunelového propojení mezi klientem a serverem ověřování. Vyberte jednu z těchto možností:<br>- **Používat PAC** – použije se stávající soubor PAC, pokud je dostupný.<br>- **Používat a zřídit PAC** – v zařízeních se zřídí soubor PAC.<br>- **Používat a zřídit PAC anonymně** – v zařízeních se zřídí soubor PAC a zajistí se, aby se soubor PAC zřídil bez ověření serveru.|Typ EAP je **EAP-FAST**.|

#### <a name="server-trust"></a>Vztah důvěryhodnosti serveru


|Název nastavení|Další informace|Kdy použít|
|--------------|-------------|----------|
|**Názvy certifikačních serverů**|Zadejte jeden nebo více běžných názvů použitých v certifikátech, které vystavuje vaše důvěryhodná certifikační autorita. Když tento údaj zadáte, můžete obejít dialog dynamického vztahu důvěryhodnosti, který se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.|Typ EAP je **EAP-TLS**, **EAP-TTLS** nebo **PEAP**.|
|**Kořenový certifikát pro ověřování serveru**|Zvolte profil důvěryhodného kořenového certifikátu pro ověření připojení. |Typ EAP je **EAP-TLS**, **EAP-TTLS** nebo **PEAP**.|
|**Ochrana identity (vnější identita)**|Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.|Typ EAP je **PEAP**.|


#### <a name="client-authentication"></a>Ověření klienta


|Název nastavení|Další informace|Kdy použít|
|--------------|-------------|----------|
|**Klientský certifikát pro ověření klienta (certifikát identity)**|Zvolte profil certifikátu SCEP nebo PKCS použitý k ověření připojení.|Typ EAP je **EAP-TLS**.|
|**Metoda ověřování**|Vyberte metodu ověřování připojení:<br>- **Certifikáty** – pokud chcete vybrat klientský certifikát SCEP nebo PKCS, který je certifikátem identity předloženým serveru.<br><br>- **Uživatelské jméno a heslo** – pokud chcete zadat jinou metodu ověřování. <br><br>Při výběru možnosti **Uživatelské jméno a heslo** nakonfigurujte tyto údaje:<br><br>-  **Metoda bez protokolu EAP (vnitřní identita)**, pak vyberte, jak se bude připojení ověřovat:<br>- **Žádné**<br>- **Nezašifrované heslo (PAP)**<br>- **Protokol CHAP (Challenge Handshake Authentication Protocol)**<br>- **Protokol Microsoft CHAP (MS-CHAP)**<br>- **Protokol Microsoft CHAP verze 2 (MS-CHAP v2)**<br>Dostupné možnosti závisí na typu EAP, který jste vybrali.<br><br>**a**<br><br>- **Ochrana identity (vnější identita)** – zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.|Typ EAP je **EAP-TTLS** nebo *.
