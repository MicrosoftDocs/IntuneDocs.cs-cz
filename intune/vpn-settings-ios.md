---
title: "Nastavení sítě VPN pro zařízení s iOSem v Intune"
titlesuffix: Azure portal
description: "Přečtěte si informace o nastavení Intune, s jehož použitím můžete nakonfigurovat připojení VPN na zařízeních s iOSem."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 12/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1447c123-ea33-4ea0-aab4-69577cdb8d00
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d3db57b851c405758c9cccdc3e70c96ca9e76000
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="vpn-settings-for-ios-devices-in-microsoft-intune"></a>Nastavení sítě VPN pro zařízení s iOSem v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

V závislosti na tom, jaká nastavení zvolíte, nebudou v následujícím seznamu konfigurovatelné všechny hodnoty.

## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN


**Název připojení** – zadejte název tohoto připojení. Tento název uživatelé vidí, když na svém zařízení procházejí seznamem dostupných připojení VPN.
- **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se zařízení připojí. Příklady: **192.168.1.1**, **vpn.contoso.com**.
- **Metoda ověřování** – zvolte způsob, kterým se zařízení ověřují vůči serveru VPN:
    - **Certifikáty** – v části **Ověřovací certifikát** vyberte profil certifikátu SCEP nebo PKCS, který jste vytvořili za účelem ověřování připojení. Další informace o profilech certifikátů najdete v článku [Konfigurace certifikátů](certificates-configure.md).
    - **Uživatelé jméno a heslo** – koncoví uživatelé musí zadat uživatelské jméno a heslo, aby se mohli přihlásit k serveru VPN.
- **Typ připojení** – z následujícího seznamu dodavatelů vyberte typ připojení VPN:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Cisco (IPSec)**
    - **Citrix**
    - **Vlastní VPN**
- **Rozdělit tunel** - tuto možnost můžete **povolit** nebo **zakázat**, aby se zařízení mohla rozhodnout, které připojení se má v závislosti na typech přenosů používat. Uživatel v hotelu například pro přístup k pracovním souborům použije připojení VPN, ale pro běžné procházení webu bude používat standardní síť hotelu.


## <a name="custom-vpn-settings"></a>Vlastní nastavení sítě VPN

Pokud jste jako typ připojení vybrali **Vlastní VPN**, nakonfigurujte tato další nastavení:

- **Identifikátor VPN** – jedná se o identifikátor aplikace VPN, kterou používáte. Získáte ho od poskytovatele připojení VPN.
- **Zadejte páry klíč-hodnota pro vlastní atributy VPN** – přidejte nebo naimportujte **klíče** a **hodnoty**, pomocí nichž si přizpůsobíte připojení VPN. Také tyto hodnoty vám obvykle dodá poskytovatel připojení VPN.

## <a name="apps-per-app-vpn-settings"></a>Nastavení aplikací (VPN pro jednotlivé aplikace)

- **VPN pro jednotlivé aplikace** – tuto možnost povolte, pokud chcete používat adresy URL, které umožňují připojení VPN, když na ně uživatel přejde v prohlížeči Safari. Pokud to chcete nakonfigurovat, musíte nejprve v základním nastavení sítě VPN jako metodu ověřování vybrat **Certifikáty**.
- **Adresy URL, které umožňují připojení VPN při používání prohlížeče Safari** – kliknutím na Přidat přidejte jednu nebo více adres URL webů. Při návštěvě těchto adres URL je aktivní připojení VPN.

- **Pravidla na vyžádání** – toto nastavení vám umožní nakonfigurovat podmíněná pravidla, která řídí, kdy se má aktivovat připojení VPN. Můžete například vytvořit podmínku, že se připojení VPN použije, pouze pokud zařízení není připojené k některé z firemních Wi-Fi sítí. Můžete také vytvořit podmínku, která zajistí, že se připojení VPN neaktivuje, pokud zařízení nemá přístup k zadané doméně hledání DNS.

    - **Identifikátory SSID nebo domény hledání DNS** – vyberte, jestli se v této podmínce používají identifikátory **SSID** bezdrátové sítě nebo **domény hledání DNS**. Zvolte Přidat a nakonfigurujte minimálně jeden identifikátor SSID nebo doménu hledání.
    - **Test řetězce adresy URL** – volitelně můžete zadat také adresu URL, kterou bude pravidlo používat pro účely testování. Pokud zařízení, na kterém je tento profil nainstalovaný, má k této adrese URL přístup bez přesměrování, aktivuje se připojení VPN a zařízení se připojí k cílové adrese URL. Uživatel neuvidí web testu řetězce adresy URL. Příkladem testu řetězce adresy URL je adresa auditujícího webového serveru, který zkontroluje splnění bezpečnostních předpisů zařízením předtím, než ho připojí k VPN. Další možností je, že adresa URL otestuje schopnost sítě VPN připojit se k webu předtím, než se zařízení připojí k cílové adrese URL přes síť VPN.
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