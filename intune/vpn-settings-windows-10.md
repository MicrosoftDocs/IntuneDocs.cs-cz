---
title: Nastavení sítě VPN ve Windows 10 v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Další informace a přečtěte si informace o všech dostupných VPN nastavení v Microsoft Intune, jaké používají a co dělají, včetně pravidel přenosů, podmíněného přístupu a nastavení DNS a proxy serveru pro Windows 10 a Windows Holographic for Business zařízení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.reviewer: tycast
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c62e170c6645b3158ae6086ecff46860032a3cc
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2019
ms.locfileid: "57237176"
---
# <a name="windows-10-and-windows-holographic-device-settings-to-add-vpn-connections-using-intune"></a>Windows 10 a Windows Holographic nastavení zařízení, které chcete přidat připojení k síti VPN pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Můžete přidat a nakonfigurovat připojení VPN pro zařízení pomocí Microsoft Intune. Tento článek uvádí a popisuje běžně používaná nastavení a funkcí při vytváření virtuální privátní sítě (VPN). Tato nastavení sítě VPN a funkce se používají v konfiguračních profilů zařízení v Intune, které jsou vloženy nebo nasadit do zařízení. 

Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete povolit nebo zakázat funkce, včetně použití dodavatel sítě VPN, vždy povoluje na, pomocí DNS, přidání proxy serveru a dalších.

Tato nastavení platí pro zařízení se systémem:

- Windows 10
- Windows Holographic for Business

V závislosti na tom, jaká nastavení zvolíte, nemusí být všechny uvedené hodnoty konfigurovatelné.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení VPN](vpn-settings-configure.md).

## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN

- **Název připojení**: Zadejte název pro toto připojení. Tento název uživatelé vidí, když na svém zařízení procházejí seznamem dostupných připojení VPN.
- **Servery**: Přidejte jeden nebo více serverů VPN, které se zařízení připojí. Při přidání serveru zadáváte tyto informace:
  - **Popis**: Zadejte popisný název serveru, jako například **Contoso VPN server**
  - **IP adresa nebo plně kvalifikovaný název domény**: Zadejte IP adresu nebo plně kvalifikovaný název domény (FQDN) serveru VPN, který se zařízení připojí, jako například **192.168.1.1** nebo **vpn.contoso.com**
  - **Výchozí server**: Povolí tento server jako výchozí server, který zařízení používat k navázání připojení. Jako výchozí server nastavte jenom jeden server.
  - **Import**: Přejděte na soubor oddělený čárkami, který obsahuje seznam serverů ve formátu: popis, IP adresa nebo plně kvalifikovaný název domény, výchozí server. Pomocí **OK** servery naimportujte do seznamu **Servery**.
  - **Export**: Exportuje seznam serverů do souboru s čárkou hodnot oddělených čárkami (csv)

- **Zaregistrovat interního serveru DNS IP adresy**: Vyberte **povolit** konfigurace profilu sítě VPN ve Windows 10 pro dynamickou registraci IP adresy přiřazené k rozhraní sítě VPN s interní DNS. Pokud vyberete možnost **Zakázat**, IP adresy se nebudou dynamicky registrovat.

- **Typ připojení**: Z následujícího seznamu dodavatelů vyberte typ připojení VPN:

  - **Pulse Secure**
  - **F5 Edge Client**
  - **SonicWALL Mobile Connect**
  - **Check Point Capsule VPN**
  - **Citrix**
  - **Palo Alto Networks GlobalProtect**
  - **Automaticky**
  - **IKEv2**
  - **L2TP**
  - **PPTP**

  Když zvolíte typ připojení VPN, můžete být také vyzváni k zadání těchto nastavení:  
    - **Always On**: Zvolte **povolit** automaticky se připojovat k připojení k síti VPN, když dojde k následujícím událostem: 
      - Při přihlášení uživatelů do zařízení
      - Při změně sítě na zařízení
      - Při opětovném zapnutí obrazovky na zařízení po vypnutí 

    - **Metoda ověřování**: Vyberte, jak chcete, aby uživatelé ověřovat vůči serveru VPN. Používání **certifikátů** nabízí rozšířené funkce, třeba bezobslužné prostředí, VPN na vyžádání a VPN pro aplikaci.
    - **Pamatovat přihlašovací údaje při každém přihlašování**: Zvolte možnost pro ukládání do mezipaměti přihlašovací údaje pro ověřování.
    - **Vlastní XML**: Zadejte vlastní příkazy XML pro konfiguraci připojení VPN.
    - **EAP Xml**: Zadejte všechny příkazy XML pro EAP, které konfigurují připojení VPN

#### <a name="pulse-secure-example"></a>Příklad pro Pulse Secure

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

#### <a name="f5-edge-client-example"></a>Příklad pro F5 Edge Client

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

#### <a name="sonicwall-mobile-connect-example"></a>Příklad pro SonicWALL Mobile Connect
**Doména nebo skupina přihlášení**: Tuto vlastnost nelze nastavit v profilu sítě VPN. Místo toho Mobile Connect tuto hodnotu analyzuje, když se zadá uživatelské jméno a doména ve formátu `username@domain` nebo `DOMAIN\username`.

Příklad:

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

#### <a name="checkpoint-mobile-vpn-example"></a>Příklad pro CheckPoint Mobile VPN

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

#### <a name="writing-custom-xml"></a>Psaní vlastních příkazů XML
Další informace o tom, jak psát vlastní příkazy XML, najdete v dokumentaci k síti VPN jednotlivých výrobců.

Další informace o vytváření vlastních dat XML protokolu EAP najdete v tématu [Konfigurace protokolu EAP](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

## <a name="apps-and-traffic-rules"></a>Pravidla pro aplikace a síťové přenosy

- **Přidružit WIP nebo aplikace k této síti VPN**: Toto nastavení povolte, pokud chcete jenom některé aplikace, které používají připojení VPN. Možnosti:

  - **Přidružit WIP k tomuto připojení**: Zadejte **doména WIP pro toto připojení**
  - **Přidružit aplikace k tomuto připojení**: Je možné **omezení sítě VPN k těmto aplikacím**a pak přidejte **přidružené aplikace**. Aplikace, které zadáte, automaticky použijí připojení VPN. Typ aplikace určuje identifikátor aplikace. Pro univerzální aplikace zadejte identitu aplikace (PFN). Pro desktopové aplikace zadejte cestu k souboru aplikace.
  >[!IMPORTANT]
  >Doporučujeme všechny seznamy aplikací vytvořené pro sítě VPN pro jednotlivé aplikace zabezpečit. Pokud seznam změní neoprávněný uživatel a vy seznam naimportujete do seznamu aplikací sítě VPN pro jednotlivé aplikace, potenciálně tím autorizujete přístup k síti VPN pro aplikace, které by přístup mít neměly. Jedním ze způsobů, jak zabezpečit seznamy aplikací, je použít seznam řízení přístupu (ACL).

- **Pravidla síťových přenosů pro toto připojení VPN**: Vyberte protokoly a které místních a vzdálených portů a rozsahy adres budou povolené pro připojení k síti VPN. Když nevytvoříte pravidlo pro provoz sítě, budou povolené všechny protokoly, porty a rozsahy adres. Po vytvoření pravidla se pro připojení VPN použijí jenom protokoly, porty a rozsahy adres, které určíte v tomto pravidle.

## <a name="conditional-access"></a>Podmíněný přístup

- **Podmíněný přístup pro toto připojení VPN**: Povolí tok dodržování předpisů zařízením z klienta. Když je tato funkce povolená, komunikuje klient sítě VPN se službou Azure Active Directory (AD), aby získal certifikát pro účely ověření. U sítě VPN by mělo být nastavené ověřování certifikátem a server VPN musí důvěřovat serveru, který mu vrátí služba Azure AD.

- **Jednotné přihlašování (SSO) s alternativním certifikátem**: Pro dodržování předpisů u zařízení použijte pro ověřování protokolem Kerberos certifikát odlišný od ověřovacího certifikátu sítě VPN. Tento certifikát zadejte pomocí těchto nastavení:

  - **Název**: Název rozšířeného použití klíče (EKU)
  - **Identifikátor objektu**: Identifikátor objektu pro EKU
  - **Hodnota hash vystavitele**: Kryptografický otisk certifikátu pro jednotné přihlašování

## <a name="dns-settings"></a>Nastavení DNS

- **Seznam hledání přípon DNS**: V **přípony DNS**, zadejte příponu DNS a **přidat**. Můžete přidat více přípon.

  Pokud použijete přípony DNS, můžete k vyhledání síťového prostředku použít jeho krátký název místo plně kvalifikovaného názvu domény (FQDN). Při hledání s použitím krátkého názvu se přípona automaticky určí serverem DNS. Například `utah.contoso.com` je v seznamu přípon DNS. Na `DEV-comp` použijte příkaz ping. V tomto scénáři se přeloží na `DEV-comp.utah.contoso.com`.

  Přípony DNS se překládají v uvedeném pořadí a toto pořadí lze měnit. Například `colorado.contoso.com` a `utah.contoso.com` jsou v seznamu přípon DNS a obě mají prostředek s názvem `DEV-comp`. Vzhledem k tomu, že `colorado.contoso.com` je v seznamu první, přeloží se jako `DEV-comp.colorado.contoso.com`.
  
  Pokud chcete pořadí změnit, klikněte na tečky vlevo od přípony DNS a pak přetáhněte příponu nahoru:

  ![Výběr tří teček a kliknutí a přetažení za účelem přesunutí přípony DNS](./media/vpn-settings-windows10-move-dns-suffix.png)

- **Název tabulky (IP adres NRPT) pravidla zásad řešení**: Název zásady překladu IP adres tabulky (IP adres NRPT) pravidla definují, jak DNS překládá názvy při připojení k síti VPN. Po navázání připojení k síti VPN, vybíráte servery DNS, připojení VPN používá.

  Pravidla můžete přidat do tabulky, které obsahují domény, DNS server, proxy server a další podrobnosti se přeložit doménu, kterou zadáte. Připojení VPN používá tato pravidla, když se uživatelé připojí k doménám, které zadáte.

  Vyberte **přidat** přidáte nové pravidlo. Pro každý server zadejte:

  - **Domény**: Zadejte název plně kvalifikované domény (FQDN) nebo příponu DNS, který chcete pravidlo použít. Můžete také zadat tečku (.) na začátku přípony DNS. Zadejte například `contoso.com` nebo `.allcontososubdomains.com`.
  - **Servery DNS**: Zadejte IP adresu nebo server DNS, který se přeloží domény. Zadejte například `10.0.0.3` nebo `vpn.contoso.com`.
  - **Proxy**: Zadejte webovým proxy serverem, který se přeloží domény. Zadejte například `http://proxy.com`.
  - **Automaticky se připojovat**: Když **povoleno**, zařízení se automaticky připojí k síti VPN, když se zařízení připojí k doméně, je třeba zadat `contoso.com`. Když **Nenakonfigurováno** (výchozí), zařízení nebude připojení automaticky k síti VPN
  - **Trvalé**: Pokud je nastavena na **povoleno**, pravidlo zůstane v tabulce Název zásady překladu IP adres (NRPT), dokud se pravidlo bude ručně odstraněn ze zařízení, i po VPN odpojí. Pokud je nastavena na **Nenakonfigurováno** (výchozí), pravidla tabulky NRPT v profilu sítě VPN se odebere ze zařízení při odpojení sítě VPN.

## <a name="proxy-settings"></a>Nastavení proxy serveru

- **Skript automatické konfigurace**: Pomocí souboru konfigurace proxy serveru. Zadejte **Adresu URL proxy serveru**, například `http://proxy.contoso.com`, která obsahuje konfigurační soubor.
- **Adresa**: Zadejte adresu proxy serveru, jako je například IP adresa nebo `vpn.contoso.com`
- **Číslo portu**: Zadejte číslo portu TCP používá proxy server
- **Obejít proxy server pro místní adresy**: Pokud už nechcete používat proxy server pro místní adresy a pak zvolte možnost povolit. Toto nastavení platí, pokud server VPN vyžaduje pro připojení proxy server.

## <a name="split-tunneling"></a>Dělené tunelové propojení

- **Dělené tunelové propojení**: **Povolit** nebo **zakázat** do zařízení mohla rozhodnout, které připojení se má použít v závislosti na provoz. Uživatel v hotelu například pro přístup k pracovním souborům použije připojení VPN, ale pro běžné procházení webu bude používat standardní síť hotelu.
- **Rozdělit tunelové trasy pro toto připojení VPN**: Přidejte volitelné trasy pro poskytovatelé VPN třetích stran. Pro každé připojení zadejte předponu cíle a velikost předpony.

## <a name="trusted-network-detection"></a>Detekce důvěryhodných sítí

**Důvěryhodné sítě přípony DNS**: Když uživatelé jsou již připojen k důvěryhodné síti, můžete zabránit zařízení automaticky připojení k jiná připojení VPN.

V **přípony DNS**, zadejte příponu DNS, který chcete důvěřovat, třeba contoso.com a vyberte **přidat**. Můžete přidat tolik přípony, jak chcete.

Pokud je uživatel připojen k příponě DNS v seznamu, pak uživatel nebude automaticky připojovat k jiným připojením VPN. Uživatel dál používat důvěryhodná seznam přípon DNS, které zadáte. Důvěryhodné sítě se stále používá, i v případě, že jsou nastaveny žádné autotriggers.

Například pokud uživatel je již připojen k příponu DNS pro důvěryhodného, pak následující autotriggers ignorovány. Přípony DNS v seznamu konkrétně zrušit všechny ostatní připojení autotriggers, včetně:

- Always on
- Aktivační událost na základě aplikace
- DNS autotrigger

## <a name="next-steps"></a>Další postup

Profil je vytvořený, ale zatím se nepoužívá. Dále [přiřadit profil](device-profile-assign.md), a [monitorování jejího stavu](device-profile-monitor.md).

Konfigurace nastavení sítě VPN na [Android](vpn-settings-android.md), [iOS](vpn-settings-ios.md), a [macOS](vpn-settings-macos.md) zařízení.
