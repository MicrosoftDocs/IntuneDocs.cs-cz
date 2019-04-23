---
title: Přidání nastavení sítě VPN do zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
description: K přidání nebo vytvoření konfiguračního profilu sítě VPN můžete použít nastavení konfigurace virtuální privátní sítě (VPN), která jsou dostupná v Microsoft Intune na zařízeních s iOSem, včetně podrobností o připojení, metod ověřování a děleného tunelového propojení v základním nastavení, nastavení vlastní sítě VPN s identifikátorem, párů klíč-hodnota, nastavení sítě VPN pro jednotlivé aplikace, která zahrnují adresy URL pro Safari, nastavení sítě VPN na vyžádání s SSID a doménami hledání DNS, nastavení proxy, která je potřeba zahrnout do konfiguračního skriptu, nastavení IP adresy nebo plně kvalifikovaného názvu domény a portu TCP.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/17/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d4221250f71df2a6c3c0d310ba25e7021269d1dc
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61515309"
---
# <a name="configure-vpn-settings-on-ios-devices-in-microsoft-intune"></a>Konfigurace nastavení sítě VPN na zařízeních s iOSem v Microsoft Intune

Microsoft Intune obsahuje řadu nastavení sítě VPN, které můžete nasadit do zařízení s iOSem. Tato nastavení se používají k vytvoření a konfiguraci připojení sítě VPN k síti vaší organizace. Těmito nastaveními se zabývá tento článek. Některá nastavení jsou dostupná jen pro určité klienty VPN, jako je Citrix, Zscaler a další.

## <a name="connection-type"></a>Typ připojení

Z následujícího seznamu dodavatelů vyberte typ připojení VPN:

- **Check Point Capsule VPN**
- **Cisco Legacy AnyConnect**: Platí pro [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) aplikace verze 4.0.5x a starší.
- **Cisco AnyConnect**: Platí pro [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) aplikace verze 4.0.7x a novější.
- **SonicWall Mobile Connect**
- **F5 Přístup starší verze**: Platí pro verze aplikace F5 Access 2.1 a starší.
- **F5 Access**: Platí pro verze aplikace F5 Access 3.0 nebo novější.
- **Palo Alto Networks GlobalProtect (starší verze)**: Platí pro Palo Alto sítě GlobalProtect aplikace verze 4.1 a starší.
- **Palo Alto Networks GlobalProtect**: Platí pro Palo Alto sítě GlobalProtect aplikace verze 5.0 a novější.
- **Pulse Secure**
- **Cisco (IPSec)**
- **Citrix VPN**
- **Citrix SSO**
- **Zscaler**: Použití podmíněného přístupu, a umožňují uživatelům obejít Zscalerem přihlašovací obrazovka, pak musíte integrovat Zscalerem privátní přístup (ZPA) pomocí svého účtu Azure AD. Podrobné pokyny najdete v [dokumentaci k aplikaci Zscaler](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad#Azure_UserSSO). 
- **Vlastní VPN**



> [!NOTE]
> Společnosti Cisco, Citrix, F5 a Palo Alto oznámily, že v iOSu 12 nebudou starší klienti fungovat. Co nejdříve byste tak měli provést migraci do nových aplikací. Další informace najdete na [blogu technické podpory pro Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409).

## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN

Nastavení, která jsou v následujícím seznamu, jsou ovlivněná zvoleným typem připojení k síti VPN.  

- **Název připojení**: Tento název koncoví uživatelé vidí, když na svém zařízení procházejí seznamem dostupných připojení VPN.
- **Vlastní název domény** (Zscalerem pouze): Předvyplní aplikace Zscalerem pole s doménou, kterou uživatelé patří do. Například pokud je uživatelské jméno `Joe@contoso.net`, zobrazí se při otevření aplikace v poli statická doména `contoso.net`. Pokud nezadáte název domény, použije se v Azure Active Directory (AD) doménová část hlavního názvu uživatele (UPN).
- **IP adresa nebo plně kvalifikovaný název domény**: IP adresa nebo plně kvalifikovaný název domény (FQDN) serveru VPN, který napojení na zařízení. Zadejte například `192.168.1.1` nebo `vpn.contoso.com`.
- **Název organizace v cloudu** (Zscalerem pouze): Zadejte název cloudu, ve kterém je vaše organizace zřízený. Název je v adrese URL, kterou používáte k přihlášení do aplikace Zscaler.  
- **Metoda ověřování**: Zvolte, jak zařízení ověření vůči serveru VPN. 
  - **Certifikáty**: V části **ověřovací certifikát**, vyberte profil k ověření připojení existující SCEP nebo PKCS certifikátu. V článku [Konfigurace certifikátů](certificates-configure.md) najdete pokyny k profilům certifikátů.
  - **Uživatelské jméno a heslo**: Koncoví uživatelé musí zadat uživatelské jméno a heslo pro přihlášení k serveru VPN.  

    > [!NOTE]
    > Pokud se jako metoda ověřování pro Cicso IPsec VPN používá uživatelské jméno a heslo, musí prostřednictvím vlastního profilu Apple Configuratoru poskytovat tajný kód SharedSecret.

- **Vyloučené adresy URL** (Zscalerem pouze): Při připojení k síti VPN Zscalerem, jsou přístupné mimo cloud Zscalerem uvedených adres URL. 

- **Dělené tunelové propojení**: **Povolit** nebo **zakázat** do zařízení mohla rozhodnout, které připojení se má použít, v závislosti na provoz. Uživatel v hotelu například pro přístup k pracovním souborům použije připojení VPN, ale pro běžné procházení webu bude používat standardní síť hotelu.

- **Identifikátor VPN** (vlastní VPN, Zscalerem a Citrix): Identifikátor aplikace VPN používáte a získáte ho od poskytovatele připojení VPN.
  - **Zadejte páry klíč/hodnota pro vlastní atributy VPN vaší organizace**: Přidejte nebo naimportujte **klíče** a **hodnoty** , který nichž si přizpůsobíte připojení VPN. Nezapomeňte, že tyto hodnoty obvykle dodá poskytovatel připojení VPN.

- **Povolit řízení přístupu k síti (NAC)** (pouze Citrix SSO): Pokud zvolíte **souhlasím**, zařízení je ID zahrnutá v profilu sítě VPN. Toto ID můžete použít k ověření k síti VPN povolit nebo zakázat přístup k síti.

  **Při použití Citrix SSO s bránou**, nezapomeňte:

  - Potvrďte používáte bránu Citrix 12.0.59 nebo vyšší.
  - Potvrďte uživatelům jednotné přihlašování Citrix 1.1.6 nainstalována nebo vyšší na svých zařízeních.
  - Integrace Citrix brány s Intune pro NAC, jak je popsáno v [integraci Microsoft Intune nebo Enterprise Mobility Suite s NetScaler (LDAP + scénáře jednorázového HESLA)](https://www.citrix.com/content/dam/citrix/en_us/documents/guide/integrating-microsoft-intune-enterprise-mobility-suite-with-netscaler.pdf) Příručka pro nasazení Citrix.
  - Povolte NAC v profilu sítě VPN.

  Důležité informace:  

  - Když je povolené NAC, síť VPN se odpojí každých 24 hodin.
  - ID zařízení je součástí profilu, ale nebude zobrazen v Intune. Microsoft toto ID nikde neukládá, ani ho nesdílí. Jakmile ho budou partneři VPN toto ID podporovat, může ho získat klient VPN, jako je Citrix SSO, a požádat službu Intune o potvrzení registrace zařízení a vyhovujícího nebo nevyhovujícího profilu sítě VPN.
  - Pokud chcete toto nastavení odebrat, znovu profil vytvořte, ale nevybírejte při tom **Souhlasím**. Pak profil znovu přiřaďte.

## <a name="automatic-vpn-settings"></a>Automatické nastavení sítě VPN

- **Per-app VPN**: Umožňuje VPN pro jednotlivé aplikace. Při otevření určitých aplikací automaticky aktivuje připojení VPN. Aplikace také můžete přidružit k danému profilu sítě VPN. Podrobnější informace najdete v [pokynech pro nastavení sítě VPN pro aplikaci pro iOS](vpn-setting-configure-per-app.md).
  - **Typ zprostředkovatele**: K dispozici je pouze pro Pulse Secure a vlastní sítě VPN.
  - Pokud používáte profily **VPN pro jednotlivé aplikace** pro iOS s typem Pulse Secure nebo Vlastní VPN, zvolte tunelování v aplikační vrstvě (proxy aplikace) nebo na úrovni paketů (tunel pro pakety). U tunelování v aplikační vrstvě nastavte hodnotu **ProviderType** na **app-proxy**, u tunelování na úrovni paketů na **packet-tunnel**. Pokud si nejste jistí, jakou hodnotu použít, podívejte se do dokumentace poskytovatele připojení VPN.
  - **Adresy URL Safari, které aktivují tuto síť VPN**: Přidejte jeden nebo více adres URL webů. Při návštěvě těchto adres URL pomocí prohlížeče Safari na zařízení se automaticky naváže připojení k VPN.

- **VPN na vyžádání**: Nakonfigurujte podmíněná pravidla, která řídí zahájení připojení k síti VPN. Můžete třeba vytvořit podmínku, že se připojení VPN použije, jen pokud zařízení není připojené k firemní síti Wi-Fi. Nebo můžete vytvořit podmínku, která zajistí, že se připojení VPN neaktivuje, pokud zařízení nemá přístup k zadané doméně hledání DNS.

  - **Identifikátory SSID nebo domény hledání DNS**: Vyberte, jestli této podmínce používají bezdrátové sítě **SSID**, nebo **domény hledání DNS**. Zvolte **Přidat** a nakonfigurujte minimálně jeden identifikátor SSID nebo doménu hledání.
  - **Test řetězce adresy URL**: Volitelné. Zadejte adresu URL, kterou pravidlo použije pro účely testování. Pokud zařízení s tímto profilem otevře tuto adresu URL bez přesměrování, zahájí se připojení VPN. A zařízení se připojí k cílové adrese URL. Uživatel neuvidí testovací web řetězce adresy URL. Příkladem testu řetězce adresy URL je adresa auditujícího webového serveru, který zkontroluje dodržování předpisů zařízením předtím, než ho připojí k VPN. Další možností je, že adresa URL otestuje schopnost sítě VPN připojit se k webu předtím, než se zařízení připojí k cílové adrese URL přes síť VPN.
  - **Akce domény**: Zvolte jednu z následujících možností:
    - Připojit v případě potřeby
    - Nepřipojovat
  - **Akce**: Zvolte jednu z následujících možností:
    - Připojit
    - Vyhodnotit připojení
    - Ignorovat
    - Odpojení

## <a name="proxy-settings"></a>Nastavení proxy serveru

Pokud používáte proxy server, nakonfigurujte následující nastavení. Nastavení proxy serveru nejsou k dispozici pro připojení VPN typu Zscaler.  

- **Skript automatické konfigurace**: Pomocí souboru konfigurace proxy serveru. Zadejte **adresu URL proxy serveru** (například `http://proxy.contoso.com`), na které je konfigurační soubor.
- **Adresa**: Zadejte IP adresu plně kvalifikovaného názvu hostitele proxy serveru.
- **Číslo portu**: Zadejte číslo portu přidruženého k proxy serveru.

## <a name="next-step"></a>Další krok
[Vytváření profilů sítě VPN v Intune](vpn-settings-configure.md)  
