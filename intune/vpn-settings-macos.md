---
title: "Nastavení sítě VPN pro zařízení s macOS v Intune"
titleSuffix: Intune on Azure
description: "Přečtěte si o nastavení Intune, s jehož použitím můžete nakonfigurovat připojení VPN na zařízeních s macOSem."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d203a70d-37df-4195-85f7-ad5ef14ac2a1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 83e3776aacbddc37e5e7586d8fd7580143dead64
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="vpn-settings-for-macos-devices-in-microsoft-intune"></a>Nastavení sítě VPN pro zařízení s macOS v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

V závislosti na tom, jaká nastavení zvolíte, nebudou v níže uvedeném seznamu konfigurovatelné všechny hodnoty.

## <a name="base-vpn-settings"></a>**Základní nastavení sítě VPN**

**Název připojení** – zadejte název tohoto připojení. Tento název uživatelé uvidí, když budou na svém zařízení procházet seznamem dostupných připojení VPN.
- **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se budou zařízení připojovat. Příklady: **192.168.1.1**, **vpn.contoso.com**.
- **Metoda ověřování** – zvolte způsob, kterým se budou zařízení ověřovat u serveru VPN:
    - **Certifikáty** – v části **Ověřovací certifikát** vyberte profil certifikátu SCEP nebo PKCS, který jste vytvořili za účelem ověřování připojení. Další informace o profilech certifikátů najdete v článku [Konfigurace certifikátů](certificates-configure.md).
    - **Uživatelé jméno a heslo** – koncoví uživatelé musí zadat uživatelské jméno a heslo, aby se mohli přihlásit k VPN serveru.
- **Typ připojení** – z následujícího seznamu dodavatelů vyberte typ připojení VPN:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Vlastní VPN**
- **Rozdělit tunel** - tuto možnost můžete **povolit** nebo **zakázat**, aby se mohla zařízení rozhodnout, které připojení se má v závislosti na typech přenosů používat. Uživatel v hotelu například bude pro přístup k pracovním souborům používat připojení VPN, ale pro běžné procházení webu bude používat standardní síť hotelu.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](apps-deploy.md). --->

## <a name="custom-vpn-settings"></a>Vlastní nastavení sítě VPN

Pokud jste vybrali **Vlastní VPN**, nakonfigurujte tato další nastavení:

- **Identifikátor VPN** – jedná se o identifikátor aplikace VPN, kterou používáte. Získáte ho od poskytovatele připojení VPN.
- **Zadejte páry klíč-hodnota pro vlastní atributy VPN** – přidejte nebo naimportujte **klíče** a **hodnoty**, pomocí nichž si přizpůsobíte připojení VPN. Také tyto hodnoty vám obvykle dodá poskytovatel připojení VPN.


## <a name="proxy-settings"></a>Nastavení proxy serveru

- **Skript automatické konfigurace** – ke konfiguraci proxy serveru použijte konfigurační soubor. Zadejte **Adresu URL proxy serveru** (například **http://proxy.contoso.com**), na které se nachází konfigurační soubor.
- **Adresa** – zadejte adresu proxy serveru (jako IP adresu).
- **Číslo portu** – zadejte číslo portu přidruženého k proxy serveru.
