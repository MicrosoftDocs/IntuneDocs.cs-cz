---
title: "Nastavení Wi-Fi v Intune pro zařízení s Androidem | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Zjistěte, jaká nastavení Intune můžete použít ke konfiguraci připojení Wi-Fi na zařízeních s Androidem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 103e17a4-2993-4359-b340-73e2acf4cf7d
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ac907e4cb63e4175dafc4c50239d3e0cbe581ad9
ms.openlocfilehash: 03227912dd8a51342c71505746f087bf6b6a4da0


---

# <a name="intune-wi-fi-settings-for-android-devices-in-intune-azure-preview"></a>Nastavení Wi-Fi pro zařízení s Androidem v Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Nastavení Wi-Fi pro základní a podnikové profily

- **Název sítě** – zadejte název pro toto připojení Wi-Fi. Jedná se o název, který uživatelé na svém zařízení uvidí při procházení seznamu dostupných připojení.
- **SSID** – zkratka pro Service Set Identifier. Jedná se o reálný název bezdrátové sítě, ke které se zařízení připojí. Název sítě, který jste vytvořili předtím, ale uživatelé uvidí jen při volbě připojení.
- **Připojovat automaticky** – nastaví, aby se zařízení připojilo, kdykoli je v dosahu této sítě.
- **Skrytá síť** – zabrání zobrazování této sítě v seznamu dostupných sítí na zařízení.


## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Nastavení Wi-Fi jenom pro podnikové profily

- **Typ EAP** – zvolte typ protokolu EAP (Extensible Authentication Protocol) použitý k ověřování zabezpečených bezdrátových připojení:
    - **EAP-TLS**
    - **EAP-TTLS**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>Další možnosti při volbě typu EAP

#### <a name="server-trust"></a>Vztah důvěryhodnosti serveru



|Název nastavení|Další informace|Kdy použít|
|-------------|---------------|-----------|
|**Názvy certifikačních serverů**|Zadejte jeden nebo více běžných názvů použitých v certifikátech, které vystavuje vaše důvěryhodná certifikační autorita. Když tento údaj zadáte, můžete obejít dialog dynamického vztahu důvěryhodnosti, který se zobrazí na zařízeních koncových uživatelů při připojování k Wi-Fi síti.|Typ EAP je **EAP-TLS** nebo **EAP-TTLS**.|
|**Kořenový certifikát pro ověřování serveru**|Zvolte profil důvěryhodného kořenového certifikátu pro ověření připojení. |Typ EAP je **EAP-TLS**, **EAP-TTLS** nebo **PEAP**.|
|**Ochrana identity (vnější identita)**|Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.|Typ EAP je **PEAP**.|


#### <a name="client-authentication"></a>Ověření klienta


|Název nastavení|Další informace|Kdy použít|
|----------|--------------|----------|
|**Klientský certifikát pro ověření klienta (certifikát identity)**|Zvolte profil certifikátu SCEP nebo PKCS použitý k ověření připojení.|Typ EAP je **EAP-TLS**.|
|**Metoda ověřování**|Vyberte metodu ověřování připojení:<br>- **Certifikáty** – pokud chcete vybrat klientský certifikát SCEP nebo PKCS, který je certifikátem identity předloženým serveru.<br><br>- **Uživatelské jméno a heslo** – pokud chcete zadat jinou metodu ověřování. <br><br>Při výběru možnosti **Uživatelské jméno a heslo** nakonfigurujte tyto údaje:<br><br>-  **Metoda bez protokolu EAP (vnitřní identita)** a pak vyberte, jak se bude připojení ověřovat:<br>- **Žádné**<br>- **Nezašifrované heslo (PAP)**<br>- **Protokol CHAP (Challenge Handshake Authentication Protocol)**<br>- **Protokol Microsoft CHAP (MS-CHAP)**<br>- **Protokol Microsoft CHAP verze 2 (MS-CHAP v2)**<br>Dostupné možnosti závisí na typu EAP, který jste vybrali.<br><br>**a**<br><br>- **Ochrana identity (vnější identita)** – zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.|Typ EAP je **EAP-TTLS** nebo **PEAP**.|



<!--HONumber=Feb17_HO1-->


