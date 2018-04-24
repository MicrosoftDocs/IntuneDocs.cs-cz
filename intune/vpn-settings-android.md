---
title: Nastavení sítě VPN v Microsoft Intune pro zařízení s Androidem
titlesuffix: ''
description: Zjistěte, jaká nastavení můžete v Intune použít ke konfiguraci připojení VPN na zařízeních s Androidem.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7c3b4964baec0ae957cfb392843ce527bf13934e
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-android"></a>Nastavení sítě VPN v Microsoft Intune pro zařízení s Androidem 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek popisuje, jaká nastavení můžete v Intune použít ke konfiguraci připojení VPN na zařízeních s Androidem.


Nastavení sítě VPN můžete nakonfigurovat pro tyto platformy:

- [Androidemem](#android-vpn-settings)
- [Android for Work](#android-for-work-vpn-settings)

V závislosti na tom, jaká nastavení zvolíte, nebudou konfigurovatelné všechny následující hodnoty.

## <a name="android-vpn-settings"></a>Nastavení VPN v Androidu
**Název připojení** – zadejte název tohoto připojení. Tento název uživatelé vidí, když na svém zařízení procházejí seznamem dostupných připojení VPN.
- **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se zařízení připojí. Příklady: **192.168.1.1**, **vpn.contoso.com**.
- **Metoda ověřování** – zvolte způsob, kterým se zařízení ověřují vůči serveru VPN:
    - **Certifikáty** – vyberte profil certifikátu SCEP nebo PKCS, který jste vytvořili za účelem ověřování připojení. Další informace o profilech certifikátů najdete v článku [Konfigurace certifikátů](certificates-configure.md).
    - **Uživatelé jméno a heslo** – koncoví uživatelé musí zadat uživatelské jméno a heslo, aby se mohli přihlásit k VPN serveru.
- **Typ připojení** – z následujícího seznamu dodavatelů vyberte typ připojení VPN:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **SonicWall Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **Otisk prstu** (pouze Check Point Capsule VPN) – zadejte řetězec, například „Kód otisku prstu Contoso“, který se použije k ověření, že je možné VPN serveru důvěřovat. Otisk prstu se může odeslat klientovi, aby věděl, že může důvěřovat jakémukoli serveru, který při připojování nabízí ten samý otisk. Pokud zařízení ještě otisk prstu nemá, vyzve uživatele, aby důvěřoval VPN serveru, ke kterému se připojuje. Současně přitom zobrazuje otisk prstu (uživatel ho ručně ověří a rozhodne se důvěřovat připojení).
- **Zadejte páry klíč-hodnota pro atributy Citrix VPN** (pouze Citrix) – zadejte páry klíče a hodnoty, které poskytl Citrix, a nakonfigurujte vlastnosti připojení VPN.

## <a name="android-for-work-vpn-settings"></a>Nastavení VPN v Androidu for Work

**Název připojení** – zadejte název tohoto připojení. Tento název uživatelé vidí, když na svém zařízení procházejí seznamem dostupných připojení VPN.
- **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se zařízení připojí. Příklady: **192.168.1.1**, **vpn.contoso.com**.
- **Metoda ověřování** – zvolte způsob, kterým se zařízení ověřují vůči serveru VPN:
    - **Certifikáty** – vyberte profil certifikátu SCEP nebo PKCS, který jste vytvořili za účelem ověřování připojení. Další informace o profilech certifikátů najdete v článku [Konfigurace certifikátů](certificates-configure.md).
    - **Uživatelé jméno a heslo** – koncoví uživatelé musí zadat uživatelské jméno a heslo, aby se mohli přihlásit k VPN serveru.
- **Typ připojení** – z následujícího seznamu dodavatelů vyberte typ připojení VPN:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **SonicWall Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

