---
title: "Nastavení sítě VPN pro zařízení s Androidem v Intune"
titlesuffix: Azure portal
description: "Přečtěte si informace o nastavení služby Intune, s jehož použitím můžete nakonfigurovat připojení VPN na zařízeních s Androidem."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 31d1e40c3cd352c00dd7a659f716b5690ea64ea1
ms.sourcegitcommit: 5877b650d93fc9a5e8f058f845acbdbfdff828b7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/22/2018
---
# <a name="vpn-settings-for-android-devices-in-microsoft-intune"></a>Nastavení sítě VPN pro zařízení s Androidem v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako správce služby Intune můžete nakonfigurovat nastavení sítě VPN pro tyto platformy:

- [Androidemem](#android-vpn-settings)
- [Android for Work](#android-for-work-vpn-settings)

V závislosti na tom, jaká nastavení zvolíte, nebudou všechny hodnoty v seznamu níže konfigurovatelné.

## <a name="android-vpn-settings"></a>Nastavení VPN v Androidu
**Název připojení** – zadejte název tohoto připojení. Tento název uživatelé uvidí, když budou na svém zařízení procházet seznamem dostupných připojení VPN.
- **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se budou zařízení připojovat. Příklady: **192.168.1.1**, **vpn.contoso.com**.
- **Metoda ověřování** – zvolte způsob, kterým se budou zařízení ověřovat u serveru VPN:
    - **Certifikáty** – vyberte profil certifikátu SCEP nebo PKCS, který jste vytvořili za účelem ověřování připojení. Další informace o profilech certifikátů najdete v článku [Konfigurace certifikátů](certificates-configure.md).
    - **Uživatelé jméno a heslo** – koncoví uživatelé musí zadat uživatelské jméno a heslo, aby se mohli přihlásit k VPN serveru.
- **Typ připojení** – z následujícího seznamu dodavatelů vyberte typ připojení VPN:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **Otisk prstu** (pouze Check Point Capsule VPN) – zadejte řetězec, například „Kód otisku prstu Contoso“, který se použije k ověření, že je možné VPN serveru důvěřovat. Otisk prstu se může odeslat klientovi, aby věděl, že může důvěřovat jakémukoli serveru, který při připojování nabízí ten samý otisk. Pokud zařízení ještě otisk prstu nemá, vyzve uživatele, aby důvěřoval VPN serveru, ke kterému se připojuje. Současně přitom zobrazuje otisk prstu (uživatel ho ručně ověří a rozhodne se důvěřovat připojení).
- **Zadejte páry klíč-hodnota pro atributy Citrix VPN** (pouze Citrix) – zadejte páry klíče a hodnoty, které poskytl Citrix, a nakonfigurujte vlastnosti připojení VPN.

## <a name="android-for-work-vpn-settings"></a>Nastavení VPN v Androidu for Work

**Název připojení** – zadejte název tohoto připojení. Tento název uživatelé uvidí, když budou na svém zařízení procházet seznamem dostupných připojení VPN.
- **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se budou zařízení připojovat. Příklady: **192.168.1.1**, **vpn.contoso.com**.
- **Metoda ověřování** – zvolte způsob, kterým se budou zařízení ověřovat u serveru VPN:
    - **Certifikáty** – vyberte profil certifikátu SCEP nebo PKCS, který jste vytvořili za účelem ověřování připojení. Další informace o profilech certifikátů najdete v článku [Konfigurace certifikátů](certificates-configure.md).
    - **Uživatelé jméno a heslo** – koncoví uživatelé musí zadat uživatelské jméno a heslo, aby se mohli přihlásit k VPN serveru.
- **Typ připojení** – z následujícího seznamu dodavatelů vyberte typ připojení VPN:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

