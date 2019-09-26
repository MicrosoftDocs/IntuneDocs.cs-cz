---
title: Nastavení sítě VPN pro Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Přečtěte si a přečtěte si informace o všech dostupných nastaveních sítě VPN v Microsoft Intune, k čemu se používají, a o tom, co dělají, včetně pravidel přenosů, podmíněného přístupu a nastavení DNS a proxy serveru pro zařízení s Windows 10 a Windows holografickým pro firmy.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.reviewer: tycast
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: a35ebcf6ecbaaa746a6da98c5bd5c13ca9a7b130
ms.sourcegitcommit: bd09decb754a832574d7f7375bad0186a22a15ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/19/2019
ms.locfileid: "71302728"
---
# <a name="windows-10-and-windows-holographic-device-settings-to-add-vpn-connections-using-intune"></a>Nastavení zařízení s Windows 10 a Windows holografické pro přidání připojení k síti VPN pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pomocí Microsoft Intune můžete přidat a nakonfigurovat připojení k síti VPN pro zařízení. Tento článek obsahuje seznam a popisuje běžně používaná nastavení a funkce při vytváření virtuálních privátních sítí (VPN). Tato nastavení a funkce sítě VPN se používají v profilech konfigurace zařízení v Intune, která jsou vložená nebo nasazená do zařízení. 

V rámci řešení pro správu mobilních zařízení (MDM) pomocí těchto nastavení můžete povolit nebo zakázat funkce, včetně použití dodavatele sítě VPN, povolení funkcí Always On, DNS, přidání proxy serveru a dalších.

Tato nastavení platí pro zařízení se systémem:

- Windows 10
- Windows Holographic for Business

V závislosti na tom, jaká nastavení zvolíte, nemusí být všechny uvedené hodnoty konfigurovatelné.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil konfigurace zařízení VPN](vpn-settings-configure.md).

## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN

- **Název připojení**: Zadejte název pro toto připojení. Tento název uživatelé vidí, když na svém zařízení procházejí seznamem dostupných připojení VPN.
- **Servery**: Přidejte jeden nebo více serverů VPN, ke kterým se zařízení připojují. Při přidání serveru zadáváte tyto informace:
  - **Popis**: Zadejte popisný název serveru, jako je **Contoso VPN server** .
  - **IP adresa nebo plně kvalifikovaný název domény**: Zadejte IP adresu nebo plně kvalifikovaný název domény (FQDN) serveru VPN, ke kterému se zařízení připojují, například **192.168.1.1** nebo **VPN.contoso.com** .
  - **Výchozí server**: Povolí tento server jako výchozí server, který budou zařízení používat k navázání připojení. Jako výchozí server nastavte jenom jeden server.
  - **Importovat**: Přejděte k souboru oddělenému čárkou, který obsahuje seznam serverů ve formátu popis, IP adresa nebo plně kvalifikovaný název domény, výchozí server. Pomocí **OK** servery naimportujte do seznamu **Servery**.
  - **Exportovat**: Exportuje seznam serverů do souboru s hodnotami oddělenými čárkami (CSV).

- **Zaregistrujte IP adresy pomocí interního serveru DNS**: Pokud chcete nakonfigurovat profil sítě VPN s Windows 10, aby se dynamicky registrovaly IP adresy přiřazené k rozhraní VPN pomocí interní služby DNS, vyberte **Povolit** . Pokud vyberete možnost **Zakázat**, IP adresy se nebudou dynamicky registrovat.

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
  - **Vždy zapnuto**: Vyberte **Povolit** pro automatické připojení k připojení VPN, když dojde k následujícím událostem: 
    - Při přihlášení uživatelů do zařízení
    - Při změně sítě na zařízení
    - Při opětovném zapnutí obrazovky na zařízení po vypnutí 

  - **Metoda ověřování**: Vyberte, jak chcete, aby se uživatelé ověřovali na serveru VPN. Používání **certifikátů** nabízí rozšířené funkce, třeba bezobslužné prostředí, VPN na vyžádání a VPN pro aplikaci.
  - **Pamatovat přihlašovací údaje při každém přihlašování**: Vyberte, chcete-li přihlašovací údaje pro ověřování ukládat do mezipaměti.
  - **Vlastní XML**: Zadejte libovolné vlastní příkazy XML, které konfigurují připojení VPN.
  - **XML protokolu EAP**: Zadejte všechny příkazy protokolu EAP XML, které konfigurují připojení VPN.

### <a name="pulse-secure-example"></a>Příklad pro Pulse Secure

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

### <a name="f5-edge-client-example"></a>Příklad pro F5 Edge Client

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

### <a name="sonicwall-mobile-connect-example"></a>Příklad pro SonicWALL Mobile Connect
**Doména nebo skupina přihlášení**: Tato vlastnost se nedá nastavit v profilu sítě VPN. Místo toho Mobile Connect tuto hodnotu analyzuje, když se zadá uživatelské jméno a doména ve formátu `username@domain` nebo `DOMAIN\username`.

Příklad:

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

### <a name="checkpoint-mobile-vpn-example"></a>Příklad pro CheckPoint Mobile VPN

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

### <a name="writing-custom-xml"></a>Psaní vlastních příkazů XML
Další informace o tom, jak psát vlastní příkazy XML, najdete v dokumentaci k síti VPN jednotlivých výrobců.

Další informace o vytváření vlastních dat XML protokolu EAP najdete v tématu [Konfigurace protokolu EAP](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

## <a name="apps-and-traffic-rules"></a>Pravidla pro aplikace a síťové přenosy

- **Přidružit NV nebo aplikace k této síti VPN**: Toto nastavení povolte, pokud chcete, aby jenom některé aplikace používaly připojení VPN. Možnosti:

  - **Přidružit NEdokončenou výrobu k tomuto připojení**: Zadejte **doménu NV pro toto připojení** .
  - **Přidružit aplikace k tomuto připojení**: Můžete **omezit připojení VPN k těmto aplikacím**a pak přidat **přidružené aplikace**. Aplikace, které zadáte, automaticky použijí připojení VPN. Typ aplikace určuje identifikátor aplikace. Pro univerzální aplikace zadejte identitu aplikace (PFN). Pro desktopové aplikace zadejte cestu k souboru aplikace.
  >[!IMPORTANT]
  >Doporučujeme všechny seznamy aplikací vytvořené pro sítě VPN pro jednotlivé aplikace zabezpečit. Pokud seznam změní neoprávněný uživatel a vy seznam naimportujete do seznamu aplikací sítě VPN pro jednotlivé aplikace, potenciálně tím autorizujete přístup k síti VPN pro aplikace, které by přístup mít neměly. Jedním ze způsobů, jak zabezpečit seznamy aplikací, je použít seznam řízení přístupu (ACL).

- **Pravidla síťových přenosů pro toto připojení k síti VPN**: Vyberte protokoly a místní & vzdálený port a rozsahy adres, které se mají povolit pro připojení k síti VPN. Když nevytvoříte pravidlo pro provoz sítě, budou povolené všechny protokoly, porty a rozsahy adres. Po vytvoření pravidla se pro připojení VPN použijí jenom protokoly, porty a rozsahy adres, které určíte v tomto pravidle.

## <a name="conditional-access"></a>Podmíněný přístup

- **Podmíněný přístup pro toto připojení k síti VPN**: Povolí z klienta tok dodržování předpisů zařízením. Když je tato funkce povolená, komunikuje klient sítě VPN se službou Azure Active Directory (AD), aby získal certifikát pro účely ověření. U sítě VPN by mělo být nastavené ověřování certifikátem a server VPN musí důvěřovat serveru, který mu vrátí služba Azure AD.

- **Jednotné přihlašování (SSO) s alternativním certifikátem**: V případě dodržování předpisů zařízením použijte pro ověřování protokolem Kerberos certifikát, který se liší od certifikátu ověřování sítě VPN. Tento certifikát zadejte pomocí těchto nastavení:

  - **Název**: Název rozšířeného použití klíče (EKU)
  - **Identifikátor objektu**: Identifikátor objektu pro rozšířené použití klíče
  - **Hodnota hash vystavitele**: Kryptografický otisk pro certifikát jednotného přihlašování

## <a name="dns-settings"></a>Nastavení DNS

- **Seznam hledání přípon DNS**: Do **přípon DNS**zadejte příponu DNS a **přidejte**. Můžete přidat mnoho přípon.

  Pokud použijete přípony DNS, můžete k vyhledání síťového prostředku použít jeho krátký název místo plně kvalifikovaného názvu domény (FQDN). Při hledání s použitím krátkého názvu se přípona automaticky určí serverem DNS. Například `utah.contoso.com` je v seznamu přípon DNS. Na `DEV-comp` použijte příkaz ping. V tomto scénáři se přeloží na `DEV-comp.utah.contoso.com`.

  Přípony DNS se překládají v uvedeném pořadí a toto pořadí lze měnit. Například `colorado.contoso.com` a `utah.contoso.com` jsou v seznamu přípon DNS a obě mají prostředek s názvem `DEV-comp`. Vzhledem k tomu, že `colorado.contoso.com` je v seznamu první, přeloží se jako `DEV-comp.colorado.contoso.com`.
  
  Pokud chcete pořadí změnit, klikněte na tečky vlevo od přípony DNS a pak přetáhněte příponu nahoru:

  ![Výběr tří teček a kliknutí a přetažení za účelem přesunutí přípony DNS](./media/vpn-settings-windows10-move-dns-suffix.png)

- **Pravidla tabulky zásad překladu IP adres (NRPT)**: Pravidla tabulky zásad překladu IP adres (NRPT) definují způsob, jakým DNS překládá názvy při připojení k síti VPN. Po navázání připojení VPN zvolíte, které servery DNS připojení VPN používá.

  Do tabulky můžete přidat pravidla, která zahrnují doménu, server DNS, proxy a další podrobnosti pro překlad domény, kterou zadáte. Připojení VPN používá tato pravidla, když se uživatelé připojí k doménám, které zadáte.

  Vyberte **Přidat** a přidejte nové pravidlo. Pro každý server zadejte:

  - **Doména**: Pokud chcete pravidlo použít, zadejte plně kvalifikovaný název domény (FQDN) nebo příponu DNS. Můžete také zadat tečku (.) na začátku pro příponu DNS. Zadejte například `contoso.com` nebo `.allcontososubdomains.com`.
  - **Servery DNS**: Zadejte IP adresu nebo server DNS, který tuto doménu vyřeší. Zadejte například `10.0.0.3` nebo `vpn.contoso.com`.
  - **Proxy**: Zadejte web proxy server, který vyřeší doménu. Zadejte například `http://proxy.com`.
  - **Automaticky připojit**: Pokud je tato možnost **povolená**, zařízení se automaticky připojí k síti VPN, když se zařízení připojí k doméně, `contoso.com`kterou zadáte, třeba. Pokud **není nakonfigurovaná** (výchozí), zařízení se k síti VPN automaticky nepřipojí.
  - **Trvalé**: Pokud je nastavené na **povoleno**, pravidlo zůstane v tabulce zásad překladu IP adres (NRPT), dokud se pravidlo ručně neodebere ze zařízení, a to ani po odpojení sítě VPN. Pokud je nastavené na **Nenakonfigurováno** (výchozí nastavení), pravidla NRPT v profilu sítě VPN se ze zařízení odeberou, když se síť VPN odpojí.

## <a name="proxy-settings"></a>Nastavení proxy serveru

- **Skript automatické konfigurace**: Pomocí souboru Nakonfigurujte proxy server. Zadejte **Adresu URL proxy serveru**, například `http://proxy.contoso.com`, která obsahuje konfigurační soubor.
- **Adresa**: Zadejte adresu proxy server, jako je například IP adresa nebo`vpn.contoso.com`
- **Číslo portu**: Zadejte číslo portu TCP používaného proxy server
- **Nepoužívat proxy server pro místní adresy**: Pokud nechcete použít proxy server pro místní adresy, zvolte Povolit. Toto nastavení platí, pokud server VPN vyžaduje pro připojení proxy server.

## <a name="split-tunneling"></a>Dělené tunelové propojení

- **Dělené tunelové propojení**: **Povolte** nebo **zakažte** , aby se zařízení rozhodlo, které připojení se má použít v závislosti na provozu. Uživatel v hotelu například pro přístup k pracovním souborům použije připojení VPN, ale pro běžné procházení webu bude používat standardní síť hotelu.
- **Rozdělit tunelové trasy pro toto připojení k síti VPN**: Přidejte volitelné trasy pro poskytovatele sítě VPN třetích stran. Pro každé připojení zadejte předponu cíle a velikost předpony.

## <a name="trusted-network-detection"></a>Zjištění důvěryhodné sítě

**Přípony protokolu DNS pro důvěryhodnou síť**: Pokud jsou uživatelé již připojeni k důvěryhodné síti, můžete zařízením zabránit v automatickém připojení k ostatním připojením k síti VPN.

V případě **přípon DNS**zadejte příponu DNS, kterou chcete důvěřovat, například contoso.com, a vyberte **Přidat**. Můžete přidat tolik přípon, kolik chcete.

Pokud je uživatel připojen k příponě DNS v seznamu, uživatel se nebude automaticky připojovat k jinému připojení VPN. Uživatel pokračuje v používání důvěryhodného seznamu přípon DNS, které zadáte. Důvěryhodná síť se pořád používá i v případě, že jsou nastavené automatické triggery.

Pokud je například uživatel již připojen k důvěryhodné příponě DNS, následující automatické triggery se ignorují. Konkrétně přípony DNS v seznamu zruší všechny ostatní automatické triggery připojení, včetně:

- Vždy zapnuto
- Aktivační událost na základě aplikace
- Automatické triggery DNS

## <a name="next-steps"></a>Další kroky

Profil je vytvořený, ale zatím se nepoužívá. Dále [Přiřaďte profil](device-profile-assign.md)a [sledujte jeho stav](device-profile-monitor.md).

Nakonfigurujte nastavení sítě VPN pro zařízení s [Androidem](vpn-settings-android.md), [iOS](vpn-settings-ios.md)a [MacOS](vpn-settings-macos.md) .
