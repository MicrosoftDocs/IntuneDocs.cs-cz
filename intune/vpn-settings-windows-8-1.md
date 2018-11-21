---
title: Nastavení sítě VPN pro zařízení s Windows 8.1 v Microsoft Intune
titleSuffix: ''
description: Zjistěte, jaká nastavení můžete v Intune použít ke konfiguraci připojení VPN na zařízeních s Windows 8.1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a94e8e88244ed76962a8664ca457fbc07ca06d73
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52183515"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-windows-81"></a>Nastavení sítě VPN v Microsoft Intune pro zařízení s Windows 8.1

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek popisuje, jaká nastavení můžete v Intune použít ke konfiguraci připojení VPN na zařízeních s Windows 8.1.

V závislosti na tom, jaká nastavení zvolíte, nebudou v následujícím seznamu konfigurovatelné všechny hodnoty.

## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN


- **Použít všechna nastavení jenom na Windows 8.1** – toto je nastavení, které můžete nakonfigurovat na klasickém portálu Intune. Na portálu Azure Portal toto nastavení nejde změnit. Pokud je nastavené na **Nakonfigurováno**, nastavení platí jenom pro zařízení s Windows 8.1. Pokud je nastavené na **Nenakonfigurováno**, platí nastavení také pro zařízení s Windows 10.
- **Název připojení** – zadejte název tohoto připojení. Tento název uživatelé vidí, když na svém zařízení procházejí seznamem dostupných připojení VPN.
- **Servery** – přidejte minimálně jeden VPN server, ke kterému se budou zařízení připojovat.
    - **Přidat** – otevře podokno **Přidat řádek**, ve kterém můžete zadat následující informace:
        - **Popis** – zadejte popisný název serveru, například **VPN server Contoso**.
        - **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se zařízení připojí. Příklady: **192.168.1.1**, **vpn.contoso.com**.
        - **Výchozí server** – povolí tento server jako výchozí server, který budou zařízení používat k navázání připojení. Jako výchozí server musí být nastavený jenom jeden server.
    - **Importovat** – vyhledejte soubor, který obsahuje seznam serverů oddělených čárkami ve formátu popis, IP adresa nebo plně kvalifikovaný název domény, výchozí server. Zvolte **OK** a naimportujte tak servery do seznamu **Servery**.
    - **Exportovat** – exportuje seznam serverů do textového souboru s oddělovači (CSV).

- **Typ připojení** – vyberte typ připojení VPN z tohoto seznamu dodavatelů:
- **Check Point Capsule VPN**
- **SonicWall Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Doména nebo skupina přihlášení** (jenom SonicWall Mobile Connect) – zadejte název domény nebo skupiny přihlášení, ke které se chcete připojit.

- **Role** (pouze Pulse Secure) – zadejte název role uživatele, která má přístup k tomuto připojení. Role uživatele definuje osobní nastavení a možnosti a povolí nebo zakáže určité funkce přístupu.

- **Sféra** (pouze Pulse Secure) – zadejte název sféry ověření, kterou chcete použít. Sféra ověření je seskupení prostředků ověření používaných typem připojení Pulse Secure.


- **Vlastní XML** – zadejte vlastní příkazy XML pro konfiguraci připojení VPN.

**Příklad pro Pulse Secure:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Příklad pro CheckPoint Mobile VPN:**
```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Příklad pro SonicWall Mobile Connect:**
```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Příklad pro F5 Edge Client:**

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Další informace o tom, jak psát vlastní příkazy XML, najdete v dokumentaci k síti VPN jednotlivých výrobců.


## <a name="proxy-settings"></a>Nastavení proxy serveru

- **Automaticky zjišťovat nastavení proxy serveru** – pokud VPN server vyžaduje pro připojení proxy server, zadejte, jestli mají zařízení automaticky zjišťovat nastavení připojení. Další informace najdete v dokumentaci k Windows Serveru.
- **Skript automatické konfigurace** – ke konfiguraci proxy serveru použijte konfigurační soubor. Zadejte **adresu URL proxy serveru** (třeba `**http://proxy.contoso.com**`), na které je konfigurační soubor.
- **Použít proxy server** – tuto možnost povolte, pokud chcete zadat nastavení proxy serveru ručně.
    - **Adresa** – zadejte adresu proxy serveru (jako IP adresu).
    - **Číslo portu** – zadejte číslo portu přidruženého k proxy serveru.
- **Obejít proxy server pro místní adresy** – pokud VPN server vyžaduje pro připojení proxy server, vyberte tuto možnost, když nechcete používat proxy server pro místní adresy, které zadáte. Další informace najdete v dokumentaci k Windows Serveru.
