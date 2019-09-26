---
title: Konfigurace nastavení sítě VPN pro zařízení s iOS v Microsoft Intune – Azure | Microsoft Docs
description: K přidání nebo vytvoření konfiguračního profilu sítě VPN můžete použít nastavení konfigurace virtuální privátní sítě (VPN), která jsou dostupná v Microsoft Intune na zařízeních s iOSem, včetně podrobností o připojení, metod ověřování a děleného tunelového propojení v základním nastavení, nastavení vlastní sítě VPN s identifikátorem, párů klíč-hodnota, nastavení sítě VPN pro jednotlivé aplikace, která zahrnují adresy URL pro Safari, nastavení sítě VPN na vyžádání s SSID a doménami hledání DNS, nastavení proxy, která je potřeba zahrnout do konfiguračního skriptu, nastavení IP adresy nebo plně kvalifikovaného názvu domény a portu TCP.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 696e335e422ed45af7b7c53db9e91dead5ea8502
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71302766"
---
# <a name="add-vpn-settings-on-ios-devices-in-microsoft-intune"></a>Přidat nastavení sítě VPN na zařízení s iOS v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune obsahuje řadu nastavení sítě VPN, které můžete nasadit do zařízení s iOSem. Tato nastavení se používají k vytvoření a konfiguraci připojení sítě VPN k síti vaší organizace. Těmito nastaveními se zabývá tento článek. Některá nastavení jsou dostupná jen pro určité klienty VPN, jako je Citrix, Zscaler a další.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](vpn-settings-configure.md).

> [!NOTE]
> Tato nastavení jsou k dispozici pro všechny typy registrace. Další informace o typech registrace najdete v tématu Registrace zařízení se [systémem iOS](ios-enroll.md).

## <a name="connection-type"></a>Typ připojení

Z následujícího seznamu dodavatelů vyberte typ připojení VPN:

- **Check Point Capsule VPN**
- **AnyConnect Cisco Legacy**: Platí pro [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) app verze 4.0.5 x a starší.
- **Cisco AnyConnect**: Platí pro [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) app verze 4.0.7 x a novější.
- **SonicWall Mobile Connect**
- **Starší verze přístupu F5**: Platí pro aplikaci F5 Access verze 2,1 a starší.
- **Přístup F5**: Platí pro aplikaci F5 Access verze 3,0 a novější.
- **Palo Alto Networks GlobalProtect (starší verze)** : Platí pro Palo Alto Networks GlobalProtect app verze 4,1 a starší.
- **Palo Alto Networks GlobalProtect**: Platí pro Palo Alto Networks GlobalProtect app verze 5,0 a novější.
- **Pulse Secure**
- **Cisco (IPSec)**
- **Citrix VPN**
- **Citrix SSO**
- **Zscaler**: Pokud chcete použít podmíněný přístup nebo chcete uživatelům dovolit, aby si Zscaler přihlašovací obrazovku, musíte Zscaler Private Access (ZPA) integrovat s vaším účtem Azure AD. Podrobné pokyny najdete v [dokumentaci k aplikaci Zscaler](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad). 
- **IKEv2**: [Nastavení IKEv2](#ikev2-settings) (v tomto článku) popisuje vlastnosti.
- **Vlastní VPN**

> [!NOTE]
> Společnosti Cisco, Citrix, F5 a Palo Alto oznámily, že v iOSu 12 nebudou starší klienti fungovat. Co nejdříve byste tak měli provést migraci do nových aplikací. Další informace najdete na [blogu technické podpory pro Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409).

## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN

Nastavení, která jsou v následujícím seznamu, jsou ovlivněná zvoleným typem připojení k síti VPN.  

- **Název připojení**: Tento název koncoví uživatelé vidí, když na svém zařízení procházejí seznamem dostupných připojení VPN.
- **Vlastní název domény** (Jenom Zscaler): Předem nasaďte přihlašovací pole aplikace Zscaler k doméně, do které uživatelé patří. Například pokud je uživatelské jméno `Joe@contoso.net`, zobrazí se při otevření aplikace v poli statická doména `contoso.net`. Pokud nezadáte název domény, použije se v Azure Active Directory (AD) doménová část hlavního názvu uživatele (UPN).
- **IP adresa nebo plně kvalifikovaný název domény**: IP adresa nebo plně kvalifikovaný název domény (FQDN) serveru VPN, ke kterému se zařízení připojují. Zadejte například `192.168.1.1` nebo `vpn.contoso.com`.
- **Název cloudu organizace** (Jenom Zscaler): Zadejte název cloudu, ve kterém je vaše organizace zřízená. Název je v adrese URL, kterou používáte k přihlášení do aplikace Zscaler.  
- **Metoda ověřování**: Vyberte, jak se zařízení ověřují na serveru VPN. 
  - **Certifikáty**: V části **ověřovací certifikát**vyberte existující profil certifikátu SCEP nebo PKCS pro ověření připojení. V článku [Konfigurace certifikátů](certificates-configure.md) najdete pokyny k profilům certifikátů.
  - **Uživatelské jméno a heslo**: Koncoví uživatelé musí zadat uživatelské jméno a heslo, aby se mohli přihlásit k serveru VPN.  

    > [!NOTE]
    > Pokud se jako metoda ověřování pro Cicso IPsec VPN používá uživatelské jméno a heslo, musí prostřednictvím vlastního profilu Apple Configuratoru poskytovat tajný kód SharedSecret.

- **Vyloučené adresy URL** (Jenom Zscaler): Po připojení k síti VPN Zscaler jsou uvedené adresy URL přístupné mimo Cloud Zscaler. 

- **Dělené tunelové propojení**: **Povolte** nebo **zakažte** , aby se zařízení rozhodla, která připojení se mají použít, v závislosti na provozu. Uživatel v hotelu například pro přístup k pracovním souborům použije připojení VPN, ale pro běžné procházení webu bude používat standardní síť hotelu.

- **Identifikátor VPN** (Vlastní VPN, Zscaler a Citrix): Identifikátor aplikace VPN, kterou používáte, a kterou poskytuje poskytovatel sítě VPN.
  - **Zadejte páry klíč/hodnota pro vlastní atributy sítě VPN vaší organizace**: Přidejte nebo importujte **klíče** a **hodnoty** , které přizpůsobují připojení k síti VPN. Nezapomeňte, že tyto hodnoty obvykle dodá poskytovatel připojení VPN.

- **Povolit řízení přístupu k síti (NAC)** (Přístup k Citrix SSO, F5): Když zvolíte souhlasím **, ID**zařízení je zahrnuté v profilu sítě VPN. Toto ID se dá použít k ověřování sítě VPN pro povolení nebo zákaz přístupu k síti.

  **Při použití přístupu F5**nezapomeňte:

  - Potvrďte, že používáte F5 BIG-IP 13.1.1.5. BIG-IP 14 se nepodporuje.
  - Integrujte BIG-IP s Intune for NAC. Podívejte se [na Přehled: Konfigurace APM pro stav kontrol zařízení pomocí Průvodce pro správu](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89) koncových bodů v systému F5.
  - Povolí NAC v profilu sítě VPN.

  **Při použití jednotného přihlašování pro Citrix s bránou**nezapomeňte:

  - Potvrďte, že používáte 12.0.59 nebo novější bránu Citrix Gateway.
  - Potvrďte, že uživatelé mají na svých zařízeních nainstalovaný Citrix SSO 1.1.6 nebo novější.
  - Integrujte bránu Citrix s Intune pro NAC. Podívejte se na téma [integration Microsoft Intune/Enterprise Mobility Suite with NetScaler (scénář LDAP + heslem)](https://www.citrix.com/content/dam/citrix/en_us/documents/guide/integrating-microsoft-intune-enterprise-mobility-suite-with-netscaler.pdf) příručka pro nasazení Citrix.
  - Povolí NAC v profilu sítě VPN.

  **Důležité podrobnosti**:  

  - Když je povolený NAC, síť VPN se každých 24 hodin odpojí. SÍŤ VPN se může okamžitě znovu připojit.
  - ID zařízení je součástí profilu, ale v Intune se nezobrazuje. Microsoft toto ID nikde neukládá, ani ho nesdílí.

  Když partneři sítě VPN podporují ID zařízení, může ID získat klient sítě VPN, jako je například Citrix SSO. Pak se může dotazovat Intune, aby zkontroloval, jestli je zařízení zaregistrované, a jestli profil VPN vyhovuje nebo nedodržuje předpisy.

  - Pokud chcete toto nastavení odebrat, znovu profil vytvořte, ale nevybírejte při tom **Souhlasím**. Pak profil znovu přiřaďte.

## <a name="ikev2-settings"></a>Nastavení IKEv2

Tato nastavení se použijí, když zvolíte **typ** > připojení**IKEv2**.

- **Vzdálený identifikátor**: Zadejte síťovou IP adresu, plně kvalifikovaný název domény, UserFQDN nebo ASN1DN serveru IKEv2. Zadejte například `10.0.0.3` nebo `vpn.contoso.com`. Obvykle zadáváte stejnou hodnotu jako [**název připojení**](#base-vpn-settings) (v tomto článku). Ale závisí na nastavení serveru IKEv2.

- **Typ ověřování klienta**: Vyberte způsob, jakým se klient VPN ověřuje pro síť VPN. Možnosti:
  - **Ověřování uživatelů** (výchozí): Přihlašovací údaje uživatele se ověřují na síti VPN.
  - **Ověřování počítače**: Ověření přihlašovacích údajů zařízení k síti VPN.

- **Metoda ověřování**: Vyberte typ přihlašovacích údajů klienta, které chcete odeslat na server. Možnosti:
  - **Certifikáty**: K ověření připojení k síti VPN používá existující profil certifikátu. Ujistěte se, že tento profil certifikátu je už přiřazený uživateli nebo zařízení. V opačném případě se připojení VPN nezdařilo.
    - **Typ certifikátu**: Vyberte typ šifrování používaný certifikátem. Ujistěte se, že je server VPN nakonfigurován tak, aby přijímal tento typ certifikátu. Možnosti:
      - **RSA** výchozí
      - **ECDSA256**
      - **ECDSA384**
      - **ECDSA521**

  - **Uživatelské jméno a heslo** (Pouze ověřování uživatelů): Když se uživatelé připojí k síti VPN, zobrazí se jim výzva k zadání uživatelského jména a hesla.
  - **Sdílený tajný klíč** (Pouze ověřování počítače): Umožňuje zadat sdílený tajný klíč, který se odešle na server VPN.
    - **Sdílený tajný klíč**: Zadejte sdílený tajný klíč, který se označuje také jako předsdílený klíč (PSK). Ujistěte se, že hodnota odpovídá sdílenému tajnému kódu nakonfigurovanému na serveru VPN.

- **Běžný název vystavitele certifikátu serveru**: Umožňuje serveru VPN ověřování pro klienta VPN. Zadejte běžný název vystavitele certifikátu (CN) certifikátu serveru VPN, který je odeslán klientovi VPN na zařízení. Ujistěte se, že hodnota CN odpovídá konfiguraci na serveru VPN. V opačném případě se připojení VPN nezdařilo.
- **Běžný název certifikátu serveru**: Zadejte CN pro samotný certifikát. Pokud je ponecháno prázdné, použije se hodnota vzdáleného identifikátoru.

- **Rychlost detekce mrtvého partnera**: Vyberte, jak často klient sítě VPN kontroluje, jestli je tunelové připojení VPN aktivní. Možnosti:
  - Nenakonfigurováno: Používá výchozí systém iOS, který se může shodovat s volbou **střední**.
  - **Žádný**: Zakáže detekci mrtvého partnera.
  - **Nízká úroveň**: Každých 30 minut pošle zprávu o prohození.
  - **Střední** (výchozí): Každých 10 minut pošle zprávu o prohození.
  - **Vysoká**: Odešle zprávu kontroly kontroly a oznámení každých 60 sekund.

- **Minimální rozsah verze TLS**: Zadejte minimální verzi protokolu TLS, kterou chcete použít. Zadejte `1.0`, `1.1`nebo .`1.2` Pokud necháte pole prázdné, použije se výchozí `1.0` hodnota.
- **Maximální rozsah verze TLS**: Zadejte maximální verzi protokolu TLS, kterou chcete použít. Zadejte `1.0`, `1.1`nebo .`1.2` Pokud necháte pole prázdné, použije se výchozí `1.2` hodnota.
- **Perfect Forward Secrecy**: Pokud chcete zapnout metodu PFS (Perfect Forward Secrecy), vyberte **Povolit** . PFS je funkce zabezpečení protokolu IP, která snižuje dopad v případě ohrožení zabezpečení klíče relace. **Zakázat** (výchozí) nepoužívá metodu PFS.
- **Ověření odvolání certifikátu**: Výběrem možnosti **Povolit** zajistěte, aby se certifikáty odvolaly, než povolíte úspěšné připojení k síti VPN. Tato kontroler je nejlepší úsilí. Pokud vyprší časový limit serveru VPN před zjištěním, jestli je certifikát odvolaný, udělí se přístup. **Zakázat** (výchozí) nekontroluje odvolání certifikátů.

- **Konfigurovat parametry přidružení zabezpečení**: **Není nakonfigurováno** (výchozí) používá výchozí systém iOS. Pokud chcete zadat parametry používané při vytváření přidružení zabezpečení se serverem VPN, vyberte **Povolit** .
  - **Šifrovací algoritmus**: Vyberte algoritmus, který chcete:
    - DES
    - ŠIFROVÁNÍ
    - AES-128
    - AES-256 (výchozí)
    - AES-128 – GCM
    - AES-256-GCM
  - **Algoritmus integrity**:  Vyberte algoritmus, který chcete:
    - SHA1-96
    - SHA1 – 160
    - SHA2-256 (výchozí)
    - SHA2 – 384
    - SHA2 – 512
  - **Skupina Diffie-Hellman**: Vyberte skupinu, kterou chcete. Výchozí hodnota je `2`skupina.
  - **Doba života** (minuty): Vyberte, jak dlouho zůstane přidružení zabezpečení aktivní, dokud se klíče neotáčí. Zadejte celou hodnotu v rozsahu `10` a `1440` (1440 minut je 24 hodin). Výchozí hodnota je `1440`.

- **Konfigurace samostatné sady parametrů pro podřízená přidružení zabezpečení**: iOS umožňuje konfigurovat samostatné parametry pro připojení IKE a všechna podřízená připojení. 

  **Není nakonfigurováno** (výchozí) používá hodnoty, které zadáte do nastavení předchozí **Konfigurace parametrů přidružení zabezpečení** . Pokud chcete zadat parametry používané při vytváření *podřízených* přidružení zabezpečení se serverem VPN, vyberte **Povolit** .
  - **Šifrovací algoritmus**: Vyberte algoritmus, který chcete:
    - DES
    - ŠIFROVÁNÍ
    - AES-128
    - AES-256 (výchozí)
    - AES-128 – GCM
    - AES-256-GCM
  - **Algoritmus integrity**:  Vyberte algoritmus, který chcete:
    - SHA1-96
    - SHA1 – 160
    - SHA2-256 (výchozí)
    - SHA2 – 384
    - SHA2 – 512
  - **Skupina Diffie-Hellman**: Vyberte skupinu, kterou chcete. Výchozí hodnota je `2`skupina.
  - **Doba života** (minuty): Vyberte, jak dlouho zůstane přidružení zabezpečení aktivní, dokud se klíče neotáčí. Zadejte celou hodnotu v rozsahu `10` a `1440` (1440 minut je 24 hodin). Výchozí hodnota je `1440`.

## <a name="automatic-vpn-settings"></a>Automatické nastavení sítě VPN

- **Síť VPN pro jednotlivé aplikace**: Povoluje síť VPN pro jednotlivé aplikace. Při otevření určitých aplikací automaticky aktivuje připojení VPN. Aplikace také můžete přidružit k danému profilu sítě VPN. Podrobnější informace najdete v [pokynech pro nastavení sítě VPN pro aplikaci pro iOS](vpn-setting-configure-per-app.md).
  - **Typ poskytovatele**: K dispozici pouze pro Pulse Secure a vlastní síť VPN.
  - Pokud používáte profily **VPN pro jednotlivé aplikace** pro iOS s typem Pulse Secure nebo Vlastní VPN, zvolte tunelování v aplikační vrstvě (proxy aplikace) nebo na úrovni paketů (tunel pro pakety). U tunelování v aplikační vrstvě nastavte hodnotu **ProviderType** na **app-proxy**, u tunelování na úrovni paketů na **packet-tunnel**. Pokud si nejste jistí, jakou hodnotu použít, podívejte se do dokumentace poskytovatele připojení VPN.
  - **Adresy URL Safari, které aktivují tuto síť VPN**: Přidejte jednu nebo více adres URL webu. Při návštěvě těchto adres URL pomocí prohlížeče Safari na zařízení se automaticky naváže připojení k VPN.

- **Síť VPN na vyžádání**: Nakonfigurujte Podmíněná pravidla, která řídí, kdy se má spustit připojení VPN. Můžete třeba vytvořit podmínku, že se připojení VPN použije, jen pokud zařízení není připojené k firemní síti Wi-Fi. Nebo vytvořte podmínku. Pokud například zařízení nemá přístup k zadané doméně hledání DNS, pak se připojení VPN nespustí.

  - **Identifikátory SSID nebo domény hledání DNS**: Vyberte, zda se v této podmínce používají **identifikátory SSID**bezdrátové sítě nebo **domény hledání DNS**. Zvolte **Přidat** a nakonfigurujte minimálně jeden identifikátor SSID nebo doménu hledání.
  - **Test řetězce adresy URL**: Volitelný parametr. Zadejte adresu URL, kterou pravidlo použije pro účely testování. Pokud zařízení s tímto profilem přistupuje k této adrese URL bez přesměrování, spustí se připojení VPN. A zařízení se připojí k cílové adrese URL. Uživatel neuvidí testovací web řetězce adresy URL. Příkladem testu řetězce adresy URL je adresa auditujícího webového serveru, který zkontroluje dodržování předpisů zařízením předtím, než ho připojí k VPN. Další možností je, že adresa URL otestuje schopnost sítě VPN připojit se k webu předtím, než se zařízení připojí k cílové adrese URL přes síť VPN.
  - **Akce domény**: Vyberte jednu z následujících položek:
    - Připojit v případě potřeby
    - Nepřipojovat
  - **Akce**: Vyberte jednu z následujících položek:
    - Připojit
    - Vyhodnotit připojení
    - Ignorovat
    - Dobu

## <a name="proxy-settings"></a>Nastavení proxy serveru

Pokud používáte proxy server, nakonfigurujte následující nastavení. Nastavení proxy serveru nejsou k dispozici pro připojení VPN typu Zscaler.  

- **Skript automatické konfigurace**: Pomocí souboru Nakonfigurujte proxy server. Zadejte **adresu URL proxy serveru** (například `http://proxy.contoso.com`), na které je konfigurační soubor.
- **Adresa**: Zadejte IP adresu plně kvalifikovaného názvu hostitele proxy server.
- **Číslo portu**: Zadejte číslo portu přidruženého k proxy server.

## <a name="next-steps"></a>Další kroky

Profil je vytvořený, ale zatím se nepoužívá. Dále [Přiřaďte profil](device-profile-assign.md) a [sledujte jeho stav](device-profile-monitor.md).

Nakonfigurujte nastavení sítě VPN na zařízeních se systémem [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [MacOS](vpn-settings-macos.md)a [Windows 10](vpn-settings-windows-10.md) .
