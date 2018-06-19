---
title: Konfigurace nastavení Wi-Fi v Microsoft Intune pro zařízení s Androidem
titleSuffix: ''
description: Zjistěte, jak v Intune konfigurovat nastavení Wi-Fi pro zařízení s Androidem a Androidem for Work.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ee82da997a794bb2f65929a6fd9e0de0cc776a6e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31831057"
---
# <a name="configure-wi-fi-settings-in-microsoft-intune-for-devices-running-android-and-android-for-work"></a>Konfigurace nastavení Wi-Fi v Microsoft Intune pro zařízení s Androidem a Androidem for Work  

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek ukazuje nastavení Wi-Fi, která můžete nakonfigurovat v Microsoft Intune pro zařízení s Androidem a Androidem for Work.

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Nastavení Wi-Fi pro základní a podnikové profily

Pro zařízení s Androidem i Androidem for Work jdou dostupná tato nastavení Wi-Fi:

- **Název sítě** – zadejte název pro toto připojení Wi-Fi. Jedná se o název, který uživatelé na svém zařízení uvidí při procházení seznamu dostupných připojení.
- **SSID** – zkratka pro Service Set Identifier. Jedná se o reálný název bezdrátové sítě, ke které se zařízení připojí. Název sítě, který jste nakonfigurovali, ale uživatelé uvidí jen při zvolení připojení.
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
|**Názvy certifikačních serverů**|Zadejte jeden nebo více běžných názvů použitých v certifikátech, které vystavuje vaše důvěryhodná certifikační autorita. Když tento údaj zadáte, můžete obejít dialog dynamického vztahu důvěryhodnosti, který se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.|Typ EAP je **EAP-TLS** nebo **EAP-TTLS**.|
|**Kořenový certifikát pro ověřování serveru**|Zvolte profil důvěryhodného kořenového certifikátu pro ověření připojení. |Typ EAP je **EAP-TLS**, **EAP-TTLS** nebo **PEAP**.|
|**Ochrana identity (vnější identita)**|Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.|Typ EAP je **PEAP**.|


#### <a name="client-authentication"></a>Ověření klienta


|                                     Název nastavení                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Další informace                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                            Kdy použít                            |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| <strong>Klientský certifikát pro ověření klienta (certifikát identity)</strong> |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Zvolte profil certifikátu SCEP nebo PKCS použitý k ověření připojení.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |              Typ EAP je <strong>EAP-TLS</strong>.              |
|                        <strong>Metoda ověřování</strong>                        | Vyberte metodu ověřování připojení:<br>- <strong>Certifikáty</strong> – pokud chcete vybrat klientský certifikát SCEP nebo PKCS, který je certifikátem identity předloženým serveru.<br><br>- <strong>Uživatelské jméno a heslo</strong> – pokud chcete zadat jinou metodu ověřování. <br><br>Při výběru možnosti <strong>Uživatelské jméno a heslo</strong> nakonfigurujte tyto údaje:<br><br>-  <strong>Metoda bez protokolu EAP (vnitřní identita)</strong>, pak vyberte, jak se bude připojení ověřovat:<br>- <strong>Žádné</strong><br>- <strong>Nezašifrované heslo (PAP)</strong><br>- <strong>Protokol CHAP (Challenge Handshake Authentication Protocol)</strong><br>- <strong>Protokol Microsoft CHAP (MS-CHAP)</strong><br>- <strong>Protokol Microsoft CHAP verze 2 (MS-CHAP v2)</strong><br>Dostupné možnosti závisí na typu EAP, který jste vybrali.<br><br><strong>a</strong><br><br>- <strong>Ochrana identity (vnější identita)</strong> – zadejte text odeslaný v odpovědi na žádost o identitu EAP. Tento text může být libovolná hodnota. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení. | Typ EAP je <strong>EAP-TTLS</strong> nebo <strong>PEAP</strong>. |

