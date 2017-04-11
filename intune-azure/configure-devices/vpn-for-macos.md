---
title: "Nastavení sítě VPN pro zařízení s macOS v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o nastavení Intune, pomocí kterých můžete nakonfigurovat připojení VPN na zařízeních s macOSem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d203a70d-37df-4195-85f7-ad5ef14ac2a1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 068dcd5209ff1cc2b2799919fe38bdfbf809423a
ms.lasthandoff: 02/18/2017


---

# <a name="vpn-settings-for-macos-devices-in-microsoft-intune"></a>Nastavení sítě VPN pro zařízení s macOS v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

V závislosti na tom, jaká nastavení zvolíte, nebudou v níže uvedeném seznamu konfigurovatelné všechny hodnoty.

## <a name="base-vpn-settings"></a>**Základní nastavení sítě VPN**

**Název připojení** – zadejte název tohoto připojení. Tento název uživatelé uvidí, když budou na svém zařízení procházet seznamem dostupných připojení VPN.
- **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se budou zařízení připojovat. Příklady: **192.168.1.1**, **vpn.contoso.com**.
- **Metoda ověřování** – zvolte způsob, kterým se budou zařízení ověřovat u serveru VPN:
    - **Certifikáty** – v části **Ověřovací certifikát** vyberte profil certifikátu SCEP nebo PKCS, který jste vytvořili za účelem ověřování připojení. Další informace o profilech certifikátů najdete v článku [Konfigurace certifikátů](how-to-configure-certificates.md).
    - **Uživatelé jméno a heslo** – koncoví uživatelé musí zadat uživatelské jméno a heslo, aby se mohli přihlásit k VPN serveru.
- **Typ připojení** – z následujícího seznamu dodavatelů vyberte typ připojení VPN:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Vlastní VPN**
- **Rozdělit tunel** – tuto možnost můžete **povolit** nebo **zakázat**, aby se mohla zařízení rozhodnout, které připojení se má v závislosti na typech přenosů používat. Uživatel v hotelu například bude pro přístup k pracovním souborům používat připojení VPN, ale pro běžné procházení webu bude používat standardní síť hotelu.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you deploy the software. For more information, see [How to deploy and monitor apps](/intune-azure/manage-apps/deploy-apps). --->

## <a name="custom-vpn-settings"></a>Vlastní nastavení sítě VPN

Pokud jste vybrali **Vlastní VPN**, nakonfigurujte tato další nastavení:

- **Identifikátor VPN** – jedná se o identifikátor aplikace VPN, kterou používáte. Získáte ho od poskytovatele připojení VPN.
- **Zadejte páry klíč-hodnota pro vlastní atributy VPN** – přidejte nebo naimportujte **klíče** a **hodnoty**, pomocí nichž si přizpůsobíte připojení VPN. Také tyto hodnoty vám obvykle dodá poskytovatel připojení VPN.


## <a name="proxy-settings"></a>Nastavení proxy serveru

- **Skript automatické konfigurace** – ke konfiguraci proxy serveru použijte konfigurační soubor. Zadejte **Adresu URL proxy serveru** (například **http://proxy.contoso.com**), na které se nachází konfigurační soubor.
- **Adresa** – zadejte adresu proxy serveru (jako IP adresu).
- **Číslo portu** – zadejte číslo portu přidruženého k proxy serveru.

