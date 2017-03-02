---
title: "Nastavení sítě VPN v Intune pro zařízení s Androidem | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Přečtěte si o nastavení Intune, pomocí kterých můžete nakonfigurovat připojení VPN na zařízeních s Androidem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: edf359b326626155a2e6acd01f72321c4cd0fe9c
ms.lasthandoff: 02/16/2017


---

# <a name="vpn-settings-for-android-devices-in-microsoft-intune"></a>Nastavení sítě VPN pro zařízení s Androidem v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

V závislosti na tom, jaká nastavení zvolíte, nebudou v níže uvedeném seznamu konfigurovatelné všechny hodnoty.

**Název připojení** – zadejte název tohoto připojení. Tento název uživatelé uvidí, když budou na svém zařízení procházet seznamem dostupných připojení VPN.
- **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se budou zařízení připojovat. Příklady: **192.168.1.1**, **vpn.contoso.com**.
- **Metoda ověřování** – zvolte způsob, kterým se budou zařízení ověřovat u serveru VPN:
    - **Certifikáty** – vyberte profil certifikátu SCEP nebo PKCS, který jste vytvořili za účelem ověřování připojení. Další informace o profilech certifikátů najdete v článku [Konfigurace certifikátů](how-to-configure-certificates.md).
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

