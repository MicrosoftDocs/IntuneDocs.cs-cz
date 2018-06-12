---
title: Nastavení sítě VPN pro zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
description: Projděte si nastavení konfigurace virtuální privátní sítě (VPN), která jsou dostupná v Microsoft Intune na zařízeních s iOSem, včetně podrobností o připojení, metod ověřování a děleného tunelového propojení v základním nastavení, nastavení vlastní sítě VPN s identifikátorem, párů klíč-hodnota, nastavení sítě VPN pro jednotlivé aplikace, která zahrnují adresy URL pro Safari, nastavení sítě VPN na vyžádání s SSID a doménami hledání DNS, nastavení proxy, která je potřeba zahrnout do konfiguračního skriptu, nastavení IP adresy nebo plně kvalifikovaného názvu domény a portu TCP.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 05d93f1518427201d9d96dbc22c772967fe4fa0f
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744563"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-ios"></a>Nastavení sítě VPN v Microsoft Intune pro zařízení s iOSem

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek popisuje, jaká nastavení můžete v Intune použít ke konfiguraci připojení VPN na zařízeních s iOSem.

V závislosti na tom, jaká nastavení zvolíte, nebudou v následujícím seznamu konfigurovatelné všechny hodnoty.

## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN

- **Název připojení**: zadejte název tohoto připojení. Tento název koncoví uživatelé vidí, když na svém zařízení procházejí seznamem dostupných připojení VPN.
- **IP adresa nebo plně kvalifikovaný název domény**: zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se zařízení připojí. Zadejte například **192.168.1.1** nebo **vpn.contoso.com**.
- **Metoda ověřování**: zvolte způsob, kterým se zařízení ověřují vůči serveru VPN:
  - **Certifikáty**: V části **Ověřovací certifikát** vyberte existující profil certifikátu SCEP nebo PKCS pro ověřování připojení. V článku [Konfigurace certifikátů](certificates-configure.md) najdete pokyny k profilům certifikátů.
  - **Uživatelé jméno a heslo**: koncoví uživatelé musí zadat uživatelské jméno a heslo, aby se mohli přihlásit k serveru VPN.

    > [!NOTE]
    > Pokud se jako metoda ověřování pro Cicso IPsec VPN používá uživatelské jméno a heslo, musí prostřednictvím vlastního profilu Apple Configuratoru poskytovat tajný kód SharedSecret.
  
- **Typ připojení**: z následujícího seznamu dodavatelů vyberte typ připojení VPN:
  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **Cisco Legacy AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Palo Alto Networks GlobalProtect**
  - **Pulse Secure**
  - **Cisco (IPSec)**
  - **Citrix**
  - **Vlastní VPN**

    > [!NOTE]
    > - Profily **Cisco Legacy AnyConnect VPN** jsou určeny pro aplikaci [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) verze 4.0.5x a starší verze.
    > - Profily **Cisco AnyConnect VPN** jsou určeny pro aplikaci [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) verze 4.0.7x a novější verze.

- **Rozdělit tunel**: tuto možnost můžete **povolit** nebo **zakázat**, aby se zařízení mohla rozhodnout, které připojení se má v závislosti na typech přenosů používat. Uživatel v hotelu například pro přístup k pracovním souborům použije připojení VPN, ale pro běžné procházení webu bude používat standardní síť hotelu.

## <a name="custom-vpn-settings"></a>Vlastní nastavení sítě VPN

Pokud jste jako typ připojení vybrali **Vlastní VPN**, nakonfigurujte také tato nastavení:

- **Identifikátor VPN**: jedná se o identifikátor aplikace VPN, kterou používáte. Získáte ho od poskytovatele připojení VPN.
- **Zadejte páry klíč-hodnota pro vlastní atributy VPN**: přidejte nebo naimportujte **klíče** a **hodnoty**, pomocí nichž si přizpůsobíte připojení VPN. Také tyto hodnoty vám obvykle dodá poskytovatel připojení VPN.

## <a name="apps-per-app-vpn-settings"></a>Nastavení aplikací (VPN pro jednotlivé aplikace)

- **VPN pro jednotlivé aplikace**: Tuto možnost povolte, pokud chcete používat adresy URL, které umožňují připojení VPN, když na ně uživatel přejde v prohlížeči Safari. Pokud chcete nakonfigurovat VPN pro jednotlivé aplikace, musíte nejprve v základním nastavení sítě VPN jako metodu ověřování vybrat **Certifikáty**.
  - **Adresy URL Safari, které aktivují tuto síť VPN**: Tuto možnost vyberte, pokud chcete přidat jednu nebo více adres URL webu. Při návštěvě těchto adres URL je aktivní připojení VPN.

- **Síť VPN na vyžádání**: Toto nastavení vám umožní nakonfigurovat podmíněná pravidla, která řídí, kdy se má aktivovat připojení VPN. Můžete například vytvořit podmínku, že se připojení VPN použije, pouze pokud zařízení není připojené k firemní Wi-Fi síti. Můžete také vytvořit podmínku, která zajistí, že se připojení VPN neaktivuje, pokud zařízení nemá přístup k zadané doméně hledání DNS.

  - **Identifikátory SSID nebo domény hledání DNS**: Vyberte, jestli se v této podmínce používají identifikátory **SSID** bezdrátové sítě nebo **domény hledání DNS**. Zvolte **Přidat** a nakonfigurujte minimálně jeden identifikátor SSID nebo doménu hledání.
  - **Test řetězce adresy URL**: Toto nastavení je volitelné. Zadejte adresu URL, kterou pravidlo použije pro účely testování. Pokud zařízení, na kterém je tento profil nainstalovaný, má k této adrese URL přístup bez přesměrování, aktivuje se připojení VPN a zařízení se připojí k cílové adrese URL. Uživatel neuvidí web testu řetězce adresy URL. Příkladem testu řetězce adresy URL je adresa auditujícího webového serveru, který zkontroluje dodržování předpisů zařízením předtím, než ho připojí k VPN. Další možností je, že adresa URL otestuje schopnost sítě VPN připojit se k webu předtím, než se zařízení připojí k cílové adrese URL přes síť VPN.
  - **Akce domény**: Zvolte jednu z následujících možností:
    - Připojit v případě potřeby
    - Nepřipojovat
  - **Akce**: Zvolte jednu z následujících možností:
    - Připojit
    - Vyhodnotit připojení
    - Přeskočit
    - Odpojit

## <a name="proxy-settings"></a>Nastavení proxy serveru

- **Skript automatické konfigurace**: ke konfiguraci proxy serveru použijte konfigurační soubor. Zadejte **adresu URL proxy serveru** (například **http://proxy.contoso.com**), na které se nachází konfigurační soubor.
- **Adresa**: Zadejte IP adresu plně kvalifikovaného názvu hostitele proxy serveru.
- **Číslo portu**: Zadejte číslo portu přidruženého k proxy serveru.

## <a name="next-step"></a>Další krok
[Vytváření profilů sítě VPN v Intune](vpn-settings-configure.md)
