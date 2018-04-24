---
title: Zobrazení nastavení sítě VPN v Microsoft Intune – Azure | Microsoft Docs
description: Přečtěte si o dostupných nastaveních sítě VPN v Microsoft Intune, k čemu slouží a co dělají, včetně pravidel přenosů, podmíněného přístupu a nastavení DNS a proxy serveru pro zařízení s Windows 10 a Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/8/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.reviewer: tycast
ms.custom: intune-azure
ms.openlocfilehash: 9464b73acc43b9625560156617359c374d7100fb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="read-about-the-vpn-settings-in-intune"></a>Přečtěte si o nastaveních sítě VPN v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pomocí Intune můžete konfigurovat nastavení sítě VPN. Tento článek popisuje tato nastavení, pravidla přenosu, podmíněný přístup a nastavení DNS a proxy serveru.

Tato nastavení platí pro:

- Zařízení s Windows 10
- Zařízení s Windows Holographic for Business

V závislosti na tom, jaká nastavení zvolíte, nemusí být všechny uvedené hodnoty konfigurovatelné.

## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN

- **Název připojení**: zadejte název tohoto připojení. Tento název uživatelé vidí, když na svém zařízení procházejí seznamem dostupných připojení VPN.
- **Servery**: přidejte minimálně jeden VPN server, ke kterému se budou zařízení připojovat.
  - **Přidat**: otevře **Přidat řádek**, kde zadejte tyto informace:
    - **Popis**: zadejte popisný název serveru, třeba **VPN server Contoso**
    - **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se zařízení připojí, třeba **192.168.1.1** nebo **vpn.contoso.com**
    - **Výchozí server**: povolí tento server jako výchozí server, který budou zařízení používat k navázání připojení. Jako výchozí server nastavte jenom jeden server.
  - **Importovat**: vyhledejte soubor, který obsahuje seznam serverů oddělených čárkami ve formátu popis, IP adresa nebo plně kvalifikovaný název domény, výchozí server. Pomocí **OK** servery naimportujte do seznamu **Servery**.
  - **Exportovat**: exportuje seznam serverů do textového souboru s oddělovači (CSV).

**Typ připojení**: z následujícího seznamu dodavatelů vyberte typ připojení VPN:

- **Automaticky**
- **Check Point Capsule VPN**
- **Citrix VPN**
- **SonicWALL Mobile Connect**
- **F5 Edge Client**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**

**Doména nebo skupina přihlášení** (jenom SonicWALL Mobile Connect): tuto vlastnost v profilu sítě VPN nastavit nejde. Místo toho Mobile Connect tuto hodnotu analyzuje, když se zadá uživatelské jméno a doména ve formátu `username@domain` nebo `DOMAIN\username`.

**Vlastní XML**/**XML pro EAP**: zadejte vlastní příkazy XML pro konfiguraci připojení VPN.

**Příklad pro Pulse Secure:**

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Příklad pro CheckPoint Mobile VPN:**

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Příklad pro SonicWALL Mobile Connect:**

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Příklad pro F5 Edge Client:**

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Další informace o tom, jak psát vlastní příkazy XML, najdete v dokumentaci k síti VPN jednotlivých výrobců.

Další informace o vytváření vlastních dat XML protokolu EAP najdete v tématu [Konfigurace protokolu EAP](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

**Rozdělit tunel**: tuto možnost můžete **povolit** nebo **zakázat**, aby se zařízení mohla rozhodnout, které připojení se má v závislosti na typech přenosů používat. Uživatel v hotelu například pro přístup k pracovním souborům použije připojení VPN, ale pro běžné procházení webu bude používat standardní síť hotelu.
- **Rozdělit tunelové trasy pro toto připojení k síti VPN**: přidejte volitelné trasy pro externí poskytovatele připojení VPN. Pro každou trasu zadejte předponu cíle a velikost předpony.

## <a name="apps-and-traffic-rules"></a>Pravidla pro aplikace a síťové přenosy

**Omezit připojení ze sítě VPN k těmto aplikacím**: tuto možnost povolte, pokud chcete, aby toto připojení VPN používaly jenom některé aplikace.
**Přidružené aplikace**: zadejte seznam aplikací, které automaticky používají připojení VPN. Typ aplikace určuje identifikátor aplikace. Pro univerzální aplikace zadejte identitu aplikace (PFN). Pro desktopové aplikace zadejte cestu k souboru aplikace.

>[!IMPORTANT]
>Doporučujeme všechny seznamy aplikací vytvořené pro sítě VPN pro jednotlivé aplikace zabezpečit. Pokud seznam změní neoprávněný uživatel a vy seznam naimportujete do seznamu aplikací sítě VPN pro jednotlivé aplikace, potenciálně tím autorizujete přístup k síti VPN pro aplikace, které by přístup mít neměly. Jedním ze způsobů, jak zabezpečit seznamy aplikací, je použít seznam řízení přístupu (ACL).

**Pravidla síťových přenosů pro toto připojení k síti VPN**: vyberte protokoly a rozsahy místních a vzdálených portů a adres, které budou povolené pro připojení VPN. Když nevytvoříte pravidlo pro provoz sítě, budou povolené všechny protokoly, porty a rozsahy adres. Po vytvoření pravidla se pro připojení VPN použijí jenom protokoly, porty a rozsahy adres, které určíte v tomto pravidle.

## <a name="conditional-access"></a>Podmíněný přístup

**Podmíněný přístup pro toto připojení k síti VPN**: umožňuje, aby se dodržování předpisů zařízením přenášelo směrem od klienta. Když je tato funkce povolená, pokusí se klient sítě VPN komunikovat se službou Azure Active Directory a získat certifikát pro účely ověření. U sítě VPN by mělo být nastavené ověřování certifikátem a server VPN musí důvěřovat serveru, který mu vrátí služba Azure Active Directory.

**Jednotné přihlašování s alternativním certifikátem**: pro dodržování předpisů zařízením použijte pro ověřování protokolem Kerberos certifikát, který je odlišný od ověřovacího certifikátu sítě VPN. Tento certifikát zadejte pomocí těchto nastavení:

- **Rozšířené použití klíče**: název rozšířeného použití klíče (EKU)
- **Identifikátor objektu**: identifikátor objektu pro EKU
- **Hodnota hash vystavitele**: kryptografický otisk certifikátu pro jednotné přihlašování

## <a name="dns-settings"></a>Nastavení DNS

**Názvy a servery DNS pro toto připojení k síti VPN**: vyberte servery DNS, které toto připojení VPN použije po vytvoření připojení.
Pro každý server zadejte:
- **Název DNS**
- **Server DNS**
- **Proxy**

## <a name="proxy-settings"></a>Nastavení proxy serveru

- **Automaticky zjišťovat nastavení proxy serveru**: pokud VPN server vyžaduje pro připojení proxy server, zadejte, jestli mají zařízení automaticky zjišťovat nastavení připojení.
- **Skript automatické konfigurace**: ke konfiguraci proxy serveru použijte konfigurační soubor. Zadejte **Adresu URL proxy serveru**, například `http://proxy.contoso.com`, která obsahuje konfigurační soubor.
- **Použít proxy server**: tuto možnost povolte, pokud chcete zadat nastavení proxy serveru ručně.
  - **Adresa**: zadejte adresu proxy serveru (jako IP adresu).
  - **Číslo portu**: zadejte číslo portu přidruženého k proxy serveru.
- **Obejít proxy server pro místní adresy**: pokud VPN server vyžaduje pro připojení proxy server, vyberte toto nastavení, když nechcete používat proxy server pro místní adresy, které zadáte.
