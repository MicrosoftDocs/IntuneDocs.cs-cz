---
title: Konfigurace nastavení sítě VPN Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Přečtěte si o dostupných nastaveních sítě VPN v Microsoft Intune, k čemu slouží a co dělají, včetně pravidel přenosů, podmíněného přístupu a nastavení DNS a proxy serveru pro zařízení s Windows 10 a Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.reviewer: tycast
ms.custom: intune-azure
ms.openlocfilehash: 0b064c6f0eaa67157c5c50ddad3a8fd863295b8b
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2018
ms.locfileid: "43312846"
---
# <a name="windows-10-vpn-settings-in-intune"></a>Nastavení sítě VPN Windows 10 v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pomocí Intune můžete konfigurovat nastavení sítě VPN. Tento článek popisuje tato nastavení, pravidla přenosu, podmíněný přístup a nastavení DNS a proxy serveru.

Tato nastavení platí pro:

- Zařízení s Windows 10
- Zařízení s Windows Holographic for Business

V závislosti na tom, jaká nastavení zvolíte, nemusí být všechny uvedené hodnoty konfigurovatelné.

## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN

- **Název připojení**: zadejte název tohoto připojení. Tento název uživatelé vidí, když na svém zařízení procházejí seznamem dostupných připojení VPN.
- **Servery**: přidejte minimálně jeden VPN server, ke kterému se budou zařízení připojovat. Při přidání serveru zadáváte tyto informace:
  - **Popis**: zadejte popisný název serveru, třeba **VPN server Contoso**
  - **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se zařízení připojí, třeba **192.168.1.1** nebo **vpn.contoso.com**
  - **Výchozí server**: povolí tento server jako výchozí server, který budou zařízení používat k navázání připojení. Jako výchozí server nastavte jenom jeden server.
  - **Importovat**: vyhledejte soubor, který obsahuje seznam serverů oddělených čárkami ve formátu popis, IP adresa nebo plně kvalifikovaný název domény, výchozí server. Pomocí **OK** servery naimportujte do seznamu **Servery**.
  - **Exportovat**: exportuje seznam serverů do textového souboru s oddělovači (CSV).

- **Registrovat IP adresy v interní službě DNS**: výběrem možnosti **Povolit** nakonfigurujete profil sítě VPN s Windows 10 tak, aby dynamicky registroval IP adresy přiřazené k rozhraní sítě VPN pomocí interní služby DNS. Pokud vyberete možnost **Zakázat**, IP adresy se nebudou dynamicky registrovat.

- **Typ připojení**: z následujícího seznamu dodavatelů vyberte typ připojení VPN:

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
    - **Stálé připojení**: pokud tuto možnost povolíte, automaticky se naváže připojení k síti VPN v těchto situacích: 
      - Při přihlášení uživatelů do zařízení
      - Při změně sítě na zařízení
      - Při opětovném zapnutí obrazovky na zařízení po vypnutí 

    - **Metoda ověřování**: vyberte, jak chcete, aby se uživatelé vůči serveru VPN ověřovali. Používání **certifikátů** nabízí rozšířené možnosti, třeba bezobslužné prostředí, VPN na vyžádání a VPN pro aplikaci.
    - **Zapamatovat si přihlašovací údaje při každém přihlášení**: při zvolení této možnosti se přihlašovací údaje uloží do mezipaměti.
    - **Vlastní XML**: zadejte vlastní příkazy XML pro konfiguraci připojení VPN.
    - **EAP XML**: zadejte příkazy EAP XML pro konfiguraci připojení VPN.

#### <a name="pulse-secure-example"></a>Příklad pro Pulse Secure

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

#### <a name="f5-edge-client-example"></a>Příklad pro F5 Edge Client

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

#### <a name="sonicwall-mobile-connect-example"></a>Příklad pro SonicWALL Mobile Connect
**Doména nebo skupina přihlášení**: tuto vlastnost v profilu sítě VPN nastavit nejde. Místo toho Mobile Connect tuto hodnotu analyzuje, když se zadá uživatelské jméno a doména ve formátu `username@domain` nebo `DOMAIN\username`.

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

- **Přidružit WIP nebo aplikace k této síti VPN**: tuto možnost povolte, pokud chcete, aby toto připojení VPN používaly jenom některé aplikace. Možnosti:

  - **Přidružit WIP k tomuto připojení**: zadejte **Doménu WIP pro toto připojení**.
  - **Přidružit aplikace k tomuto připojení**: můžete **Omezit připojení ze sítě VPN k těmto aplikacím** a pak přidat **Přidružené aplikace**. Aplikace, které zadáte, automaticky použijí připojení VPN. Typ aplikace určuje identifikátor aplikace. Pro univerzální aplikace zadejte identitu aplikace (PFN). Pro desktopové aplikace zadejte cestu k souboru aplikace.
  >[!IMPORTANT]
  >Doporučujeme všechny seznamy aplikací vytvořené pro sítě VPN pro jednotlivé aplikace zabezpečit. Pokud seznam změní neoprávněný uživatel a vy seznam naimportujete do seznamu aplikací sítě VPN pro jednotlivé aplikace, potenciálně tím autorizujete přístup k síti VPN pro aplikace, které by přístup mít neměly. Jedním ze způsobů, jak zabezpečit seznamy aplikací, je použít seznam řízení přístupu (ACL).

- **Pravidla síťových přenosů pro toto připojení k síti VPN**: vyberte protokoly a rozsahy místních a vzdálených portů a adres, které budou povolené pro připojení VPN. Když nevytvoříte pravidlo pro provoz sítě, budou povolené všechny protokoly, porty a rozsahy adres. Po vytvoření pravidla se pro připojení VPN použijí jenom protokoly, porty a rozsahy adres, které určíte v tomto pravidle.

## <a name="conditional-access"></a>Podmíněný přístup

- **Podmíněný přístup pro toto připojení k síti VPN**: umožňuje, aby se dodržování předpisů zařízením přenášelo směrem od klienta. Když je tato funkce povolená, pokusí se klient sítě VPN komunikovat se službou Azure Active Directory (AD) a získat certifikát pro účely ověření. U sítě VPN by mělo být nastavené ověřování certifikátem a server VPN musí důvěřovat serveru, který mu vrátí služba Azure AD.

- **Jednotné přihlašování s alternativním certifikátem**: pro dodržování předpisů zařízením použijte pro ověřování protokolem Kerberos certifikát, který je odlišný od ověřovacího certifikátu sítě VPN. Tento certifikát zadejte pomocí těchto nastavení:

  - **Název**: název rozšířeného použití klíče (EKU)
  - **Identifikátor objektu**: identifikátor objektu pro EKU
  - **Hodnota hash vystavitele**: kryptografický otisk certifikátu pro jednotné přihlašování

## <a name="dns-settings"></a>Nastavení DNS

**Domény a servery pro toto připojení VPN**: přidejte doménu a server DNS, které má síť VPN používat. Vybrat, které servery DNS bude připojení VPN používat, můžete po vytvoření připojení. Pro každý server zadejte:
- **Doména**
- **Server DNS**
- **Proxy**

## <a name="proxy-settings"></a>Nastavení proxy serveru

- **Skript automatické konfigurace**: ke konfiguraci proxy serveru použijte konfigurační soubor. Zadejte **Adresu URL proxy serveru**, například `http://proxy.contoso.com`, která obsahuje konfigurační soubor.
- **Adresa**: zadejte adresu proxy serveru, třeba IP adresu nebo `vpn.contoso.com`.
- **Číslo portu**: zadejte číslo portu TCP vašeho proxy serveru.
- **Obejít proxy server pro místní adresy**: pokud nechcete používat proxy server pro místní adresy, pak zvolte Povolit. Toto nastavení platí, pokud server VPN vyžaduje pro připojení proxy server.

## <a name="split-tunneling"></a>Dělené tunelové propojení

- **Rozdělit tunel**: tuto možnost můžete **povolit** nebo **zakázat**, aby se zařízení mohla rozhodnout, které připojení se má v závislosti na typech přenosů používat. Uživatel v hotelu například pro přístup k pracovním souborům použije připojení VPN, ale pro běžné procházení webu bude používat standardní síť hotelu.
- **Rozdělit tunelové trasy pro toto připojení k síti VPN**: přidejte volitelné trasy pro externí poskytovatele připojení VPN. Pro každé připojení zadejte předponu cíle a velikost předpony.
