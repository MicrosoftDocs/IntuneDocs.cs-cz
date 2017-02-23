---
title: "Nastavení sítě VPN v Intune pro zařízení s Windows 10 | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Přečtěte si o nastavení Intune, pomocí kterých můžete nakonfigurovat připojení VPN na zařízeních s Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 495e4ed6-b2ef-47cc-a110-13fa9b5f85a6
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aff935508551b45ee0a69f907506b0703290fddf
ms.openlocfilehash: 1d0459bc414ce43258aff6fdc2e9313784440f52


---

# <a name="vpn-settings-for-windows-10-devices-in-intune-azure-preview"></a>Nastavení sítě VPN pro zařízení s Windows 10 v Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

V závislosti na tom, jaká nastavení zvolíte, nebudou v níže uvedeném seznamu konfigurovatelné všechny hodnoty.


## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN


- **Název připojení** – zadejte název tohoto připojení. Tento název uživatelé uvidí, když budou na svém zařízení procházet seznamem dostupných připojení VPN.
- **Servery** – přidejte minimálně jeden VPN server, ke kterému se budou zařízení připojovat.
    - **Přidat** – otevře okno **Přidat řádek**, ve kterém můžete zadat následující informace:
        - **Popis** – zadejte popisný název serveru, například **VPN server Contoso**.
        - **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se budou zařízení připojovat. Příklady: **192.168.1.1**, **vpn.contoso.com**.
        - **Výchozí server** – povolí tento server jako výchozí server, který budou zařízení používat k navázání připojení. Jako výchozí server musí být nastavený jenom jeden server.
    - **Importovat** – vyhledejte soubor, který obsahuje seznam serverů oddělených čárkami ve formátu popis, IP adresa nebo plně kvalifikovaný název domény, výchozí server. Zvolte **OK** a naimportujte tak servery do seznamu **Servery**.
    - **Exportovat** – exportuje seznam serverů do textového souboru s oddělovači (CSV).

**Typ připojení** – z následujícího seznamu dodavatelů vyberte typ připojení VPN:
- **Pulse Secure**
- **F5 Edge Client**
- **Dell SonicWALL Mobile Connect**
- **Check Point Capsule VPN**
- **Automaticky**
- **IKEv2**
- **L2TP**
- **PPTP**

**Doména nebo skupina přihlášení** (pouze Dell SonicWALL Mobile Connect) – zadejte název domény nebo skupiny přihlášení, ke které se chcete připojit.

**Vlastní XML**/**XML pro EAP** – zadejte vlastní příkazy XML pro konfiguraci připojení VPN.

**Příklad pro Pulse Secure:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Příklad pro CheckPoint Mobile VPN:**

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Příklad pro Dell SonicWALL Mobile Connect:**

```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Příklad pro F5 Edge Client:**

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Další informace o tom, jak psát vlastní příkazy XML, najdete v dokumentaci k síti VPN jednotlivých výrobců.

**Rozdělit tunel** – tuto možnost můžete **povolit** nebo **zakázat**, aby se mohla zařízení rozhodnout, které připojení se má v závislosti na typech přenosů používat. Uživatel v hotelu například bude pro přístup k pracovním souborům používat připojení VPN, ale pro běžné procházení webu bude používat standardní síť hotelu.
- **Rozdělit tunelové trasy pro toto připojení k síti VPN** – přidejte volitelné trasy pro externí poskytovatele připojení VPN. Pro každou trasu zadejte předponu cíle a velikost předpony.

## <a name="apps-and-traffic-rules"></a>Pravidla pro aplikace a síťové přenosy

**Omezit připojení ze sítě VPN k těmto aplikacím** – tuto možnost povolte, pokud chcete, aby toto připojení VPN používaly jenom aplikace, které určíte.
**Přidružené aplikace** – zadejte seznam aplikací, které budou automaticky používat připojení VPN. Typ aplikace bude určovat identifikátor aplikace. Pro univerzální aplikace zadejte identitu aplikace (PFN). Pro desktopové aplikace zadejte cestu k souboru aplikace.

>[!IMPORTANT]
>Doporučujeme zabezpečit všechny seznamy aplikací, které zkompilujete pro použití v konfiguraci sítě VPN pro jednotlivé aplikace. Pokud seznam upraví neoprávněný uživatel a vy seznam naimportujete do seznamu aplikací sítě VPN pro jednotlivé aplikace, potenciálně tím autorizujete přístup k síti VPN pro aplikace, které by přístup mít neměly. Jedním ze způsobů, jak zabezpečit seznamy aplikací, je použít seznam řízení přístupu (ACL).

**Pravidla síťových přenosů pro toto připojení k síti VPN** – vyberte protokoly a rozsahy místních a vzdálených adres, které budou povolené pro připojení VPN. Když nevytvoříte pravidlo pro provoz sítě, budou povolené všechny protokoly, porty a rozsahy adres. Po vytvoření pravidla se pro připojení VPN použijí jenom protokoly, porty a rozsahy adres, které určíte v tomto pravidle.


## <a name="conditional-access"></a>Podmíněný přístup

**Podmíněný přístup pro toto připojení k síti VPN** – **Jednotné přihlašování s alternativním certifikátem** – **Rozšířené použití klíče** – **Hodnota hash vystavitele** -

## <a name="dns-settings"></a>Nastavení DNS

**Názvy a servery DNS pro toto připojení k síti VPN** – vyberte servery DNS, které bude toto připojení VPN používat po vytvoření připojení.
Pro každý server zadejte:
- **Název DNS**
- **Server DNS**
- **Proxy**

## <a name="proxy-settings"></a>Nastavení proxy serveru

- **Automaticky zjišťovat nastavení proxy serveru** – pokud VPN server vyžaduje pro připojení proxy server, zadejte, jestli mají zařízení automaticky zjišťovat nastavení připojení. Další informace najdete v dokumentaci k Windows Serveru.
- **Skript automatické konfigurace** – ke konfiguraci proxy serveru použijte konfigurační soubor. Zadejte **Adresu URL proxy serveru** (například **http://proxy.contoso.com**), na které se nachází konfigurační soubor.
- **Použít proxy server** – tuto možnost povolte, pokud chcete zadat nastavení proxy serveru ručně.
    - **Adresa** – zadejte adresu proxy serveru (jako IP adresu).
    - **Číslo portu** – zadejte číslo portu přidruženého k proxy serveru.
- **Obejít proxy server pro místní adresy** – pokud VPN server vyžaduje pro připojení proxy server, vyberte tuto možnost, když nechcete používat proxy server pro místní adresy, které zadáte. Další informace najdete v dokumentaci k Windows Serveru.



<!--HONumber=Feb17_HO1-->


