---
title: Nastavení sítě VPN pro zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
description: Projděte si nastavení konfigurace virtuální privátní sítě (VPN), která jsou dostupná v Microsoft Intune na zařízeních s iOSem, včetně podrobností o připojení, metod ověřování a děleného tunelového propojení v základním nastavení, nastavení vlastní sítě VPN s identifikátorem, párů klíč-hodnota, nastavení sítě VPN pro jednotlivé aplikace, která zahrnují adresy URL pro Safari, nastavení sítě VPN na vyžádání s SSID a doménami hledání DNS, nastavení proxy, která je potřeba zahrnout do konfiguračního skriptu, nastavení IP adresy nebo plně kvalifikovaného názvu domény a portu TCP.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: deb6a230573ff20237e6eee386052baba472832a
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313866"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-ios"></a>Nastavení sítě VPN v Microsoft Intune pro zařízení s iOSem

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek popisuje, jaká nastavení můžete v Intune použít ke konfiguraci připojení VPN na zařízeních s iOSem.

V závislosti na tom, jaká nastavení zvolíte, nebudou v následujícím seznamu konfigurovatelné všechny hodnoty.

## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN
Zobrazená nastavení ze seznamu níže určuje zvolený typ připojení VPN.  
- **Název připojení**: Tento název koncoví uživatelé vidí, když na svém zařízení procházejí seznamem dostupných připojení VPN.
- **Název vlastní domény** (jen Zscaler): Předem vyplní pole pro přihlášení doménou, do které patří vaši uživatelé. Pokud je například uživatelské jméno **Joe@contoso.net**, bude se při otevření aplikace v tomto poli staticky zobrazovat doména **contoso.net**. V případě, že název domény nezadáte, použije se doménová část hlavního názvu uživatele ve službě Azure Active Directory.
- **IP adresa nebo plně kvalifikovaný název domény**: IP adresa nebo plně kvalifikovaný název domény serveru VPN, ke kterému se zařízení připojí Zadejte například **192.168.1.1** nebo **vpn.contoso.com**. 
- **Název cloudu organizace** (jen Zscaler): Zadejte název cloudu, ve kterém je vaše organizace zřízena. Pokud název neznáte, vyhledejte adresu URL, kterou používáte k přihlášení k aplikaci Zscaler.  
- **Metoda ověřování**: Zvolte způsob, kterým se zařízení ověřují vůči serveru VPN. 
  - **Certifikáty**: V části **Ověřovací certifikát** vyberte existující profil certifikátu SCEP nebo PKCS pro ověřování připojení. V článku [Konfigurace certifikátů](certificates-configure.md) najdete pokyny k profilům certifikátů.
  - **Uživatelé jméno a heslo**: koncoví uživatelé musí zadat uživatelské jméno a heslo, aby se mohli přihlásit k serveru VPN.  

    > [!NOTE]
    > Pokud se jako metoda ověřování pro Cicso IPsec VPN používá uživatelské jméno a heslo, musí prostřednictvím vlastního profilu Apple Configuratoru poskytovat tajný kód SharedSecret.
  
- **Typ připojení**: z následujícího seznamu dodavatelů vyberte typ připojení VPN:
  - **Check Point Capsule VPN**
  - **Cisco Legacy AnyConnect**: Určeno pro aplikaci [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) verze 4.0.5x a starší.
  - **Cisco AnyConnect**: Určeno pro aplikaci [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) verze 4.0.7x a novější.
  - **SonicWall Mobile Connect**
  - **Starší verze F5 Access**: Určeno pro aplikaci F5 Access verze 2.1 a starší.
  - **F5 Access**: Určeno pro aplikaci F5 Access verze 3.0 a novější.
  - **Palo Alto Networks GlobalProtect (starší verze)**: Určeno pro aplikaci Palo Alto Networks GlobalProtect verze 4.1 a starší.
  - **Palo Alto Networks GlobalProtect**: Určeno pro aplikaci Palo Alto Networks GlobalProtect verze 5.0 a novější.
  - **Pulse Secure**
  - **Cisco (IPSec)**
  - **Citrix VPN**
  - **Citrix SSO**
  - **Zscaler**: Vyžaduje integraci služby Zscaler Private Access s vaším účtem Azure Active Directory. Podrobné pokyny najdete v [dokumentaci k aplikaci Zscaler](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad#Azure_UserSSO). 
  - **Vlastní VPN**    

    > [!NOTE]
    > Cisco, Citrix, F5 a Palo Alto oznámili, že jejich starší klienti nebudou v nadcházející verzi iOS 12 fungovat. Co nejdříve byste tak měli provést migraci do nových aplikací. Další informace najdete na [blogu technické podpory pro Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409).

* **Vyloučené adresy URL** (jen Zscaler): Pokud jsou uvedené adresy URL připojené k síti VPN Zscaleru, jsou k dispozici i mimo cloud Zscaler. 

- **Rozdělit tunel**: tuto možnost můžete **povolit** nebo **zakázat**, aby se zařízení mohla rozhodnout, které připojení se má v závislosti na typech přenosů používat. Uživatel v hotelu například pro přístup k pracovním souborům použije připojení VPN, ale pro běžné procházení webu bude používat standardní síť hotelu.   

## <a name="custom-vpn-settings"></a>Vlastní nastavení sítě VPN

Pokud jste jako typ připojení vybrali **Vlastní VPN**, nakonfigurujte také následující nastavení. Tato nastavení jsou viditelná i pro připojení typu Zscaler a Citrix.

- **Identifikátor VPN**: jedná se o identifikátor aplikace VPN, kterou používáte. Získáte ho od poskytovatele připojení VPN.
- **Zadejte páry klíč-hodnota pro vlastní atributy VPN vaší organizace**: Přidejte nebo naimportujte **klíče** a **hodnoty**, pomocí nichž si přizpůsobíte připojení VPN. Také tyto hodnoty vám obvykle dodá poskytovatel připojení VPN.

## <a name="automatic-vpn-settings"></a>Automatické nastavení sítě VPN

- **VPN pro aplikaci**: Výběrem této možnosti se povolí VPN pro aplikace. To umožní, aby se připojení k síti VPN automaticky aktivovalo při otevření konkrétních aplikací. Kromě výběru této možnosti musíte také přiřadit aplikace k tomuto profilu VPN. Další podrobnosti najdete v [pokynech pro nastavení VPN pro aplikaci pro iOS](vpn-setting-configure-per-app.md). 
  - Nastavení **Typ zprostředkovatele** je k dispozici jen pro Pulse Secure a Vlastní VPN.
  - Pokud používáte profily **VPN pro jednotlivé aplikace** pro iOS s typem Pulse Secure nebo Vlastní VPN, můžete použít tunelování v aplikační vrstvě (proxy aplikace) nebo na úrovni paketů (tunel pro pakety). U tunelování v aplikační vrstvě nastavte hodnotu **ProviderType** na **app-proxy**, u tunelování na úrovni paketů na **packet-tunnel**. Pokud si nejste jistí, kterou hodnotu použít, vyhledejte informace v dokumentaci poskytovatele připojení VPN. 
  - **Adresy URL Safari, které aktivují tuto síť VPN**: Tuto možnost vyberte, pokud chcete přidat jednu nebo více adres URL webu. Při návštěvě těchto adres URL pomocí prohlížeče Safari na zařízení se automaticky naváže připojení k VPN.

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
Pokud používáte proxy server, nakonfigurujte následující nastavení. Nastavení proxy serveru nejsou k dispozici u připojení VPN typu Zscaler.  

- **Skript automatické konfigurace**: ke konfiguraci proxy serveru použijte konfigurační soubor. Zadejte **adresu URL proxy serveru** (například **http://proxy.contoso.com**), na které se nachází konfigurační soubor.
- **Adresa**: Zadejte IP adresu plně kvalifikovaného názvu hostitele proxy serveru.
- **Číslo portu**: Zadejte číslo portu přidruženého k proxy serveru.

## <a name="next-step"></a>Další krok
[Vytváření profilů sítě VPN v Intune](vpn-settings-configure.md)  
