---
title: "Nastavení sítě VPN pro zařízení s iOSem v Intune"
titleSuffix: Intune on Azure
description: "Přečtěte si informace o nastavení Intune, s jehož použitím můžete nakonfigurovat připojení VPN na zařízeních s iOSem."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1447c123-ea33-4ea0-aab4-69577cdb8d00
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a6cc079b05037cc18b7d27dd0d2674e87e1d54d0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="vpn-settings-for-ios-devices-in-microsoft-intune"></a>Nastavení sítě VPN pro zařízení s iOSem v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

V závislosti na tom, jaká nastavení zvolíte, nebudou v níže uvedeném seznamu konfigurovatelné všechny hodnoty.

## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN


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
    - **Cisco (IPSec)**
    - **Citrix**
    - **Vlastní VPN**
- **Rozdělit tunel** – tuto možnost můžete **povolit** nebo **zakázat**, aby se mohla zařízení rozhodnout, které připojení se má v závislosti na typech přenosů používat. Uživatel v hotelu například bude pro přístup k pracovním souborům používat připojení VPN, ale pro běžné procházení webu bude používat standardní síť hotelu.


## <a name="custom-vpn-settings"></a>Vlastní nastavení sítě VPN

Pokud jste jako typ připojení vybrali **Vlastní VPN**, nakonfigurujte tato další nastavení:

- **Identifikátor VPN** – jedná se o identifikátor aplikace VPN, kterou používáte. Získáte ho od poskytovatele připojení VPN.
- **Zadejte páry klíč-hodnota pro vlastní atributy VPN** – přidejte nebo naimportujte **klíče** a **hodnoty**, pomocí nichž si přizpůsobíte připojení VPN. Také tyto hodnoty vám obvykle dodá poskytovatel připojení VPN.

## <a name="apps-per-app-vpn-settings"></a>Nastavení aplikací (VPN pro jednotlivé aplikace)

- **VPN pro jednotlivé aplikace** – tuto možnost povolte, pokud chcete adresy URL, které povolí připojení VPN, když na ně uživatel přejde v prohlížeči Safari. Pokud to chcete nakonfigurovat, musíte nejprve v základním nastavení sítě VPN jako metodu ověřování vybrat **Certifikáty**.
- **Adresy URL umožňují připojení k síti VPN pomocí prohlížeče Safari** – kliknutím na Přidat přidejte jednu nebo více adres URL webů. Pokud uživatel tyto adresy URL navštíví, povolí se připojení VPN.

- **Pravidla na vyžádání** – toto nastavení vám umožní nakonfigurovat podmíněná pravidla, která řídí, kdy se má aktivovat připojení VPN. Můžete například vytvořit podmínku, že se připojení VPN použije, pouze pokud zařízení není připojené k některé z firemních Wi-Fi sítí. Můžete také vytvořit podmínku, která zajistí, že se připojení VPN neaktivuje, pokud zařízení nemá přístup k zadané doméně hledání DNS.

    - **SSID nebo domény hledání DNS** – vyberte, zda se v této podmínce budou používat identifikátory **SSID** bezdrátové sítě nebo **domény hledání DNS**. Zvolte Přidat a nakonfigurujte minimálně jeden identifikátor SSID nebo doménu hledání.
    - **Test řetězce adresy URL** – volitelně můžete zadat také adresu URL, kterou bude pravidlo používat pro účely testování. Pokud zařízení, na kterém je tento profil nainstalovaný, má k této adrese URL přístup bez přesměrování, aktivuje se připojení VPN a zařízení se připojí k cílové adrese URL. Uživatel neuvidí web testu řetězce adresy URL. Příkladem testu řetězce adresy URL je adresa auditujícího webového serveru, který zkontroluje splnění bezpečnostních předpisů zařízením předtím, než ho připojí k VPN. Další možností je, že adresa URL otestuje schopnost VPN připojit se k webu předtím, než se zařízení připojí k cílové adrese URL skrze VPN.
    - **Akce domény** – zvolte jednu z následujících možností:
        - Připojit v případě potřeby – 
        - Nikdy nepřipojovat – 
    - **Akce** – zvolte jednu z následujících možností:
        - Připojit – 
        - Vyhodnotit připojení – 
        - Ignorovat – 
        - Odpojit – 


## <a name="proxy-settings"></a>Nastavení proxy serveru

- **Skript automatické konfigurace** – ke konfiguraci proxy serveru použijte konfigurační soubor. Zadejte **Adresu URL proxy serveru** (například **http://proxy.contoso.com**), na které se nachází konfigurační soubor.
- **Adresa** – zadejte adresu proxy serveru (jako IP adresu).
- **Číslo portu** – zadejte číslo portu přidruženého k proxy serveru.
