---
title: "Nastavení sítě VPN v Intune pro zařízení s Windows 8.1 | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Přečtěte si o nastavení Intune, pomocí kterých můžete nakonfigurovat připojení VPN na zařízeních s Windows 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aff935508551b45ee0a69f907506b0703290fddf
ms.openlocfilehash: 31a7779537062a63fac1fb512a7cf4b9033368f7


---

# <a name="vpn-settings-for-windows-81-devices-in-intune-azure-preview"></a>Nastavení sítě VPN pro zařízení s Windows 8.1 v Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

V závislosti na tom, jaká nastavení zvolíte, nebudou v níže uvedeném seznamu konfigurovatelné všechny hodnoty.

## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN


- **Použít všechna nastavení jenom na 8.1** – toto je nastavení, které můžete nakonfigurovat na portálu Classic služby Intune. Na portálu Azure Portal toto nastavení nejde změnit. Pokud je nastavené na **Nakonfigurováno**, použijí se všechna nastavení jenom na zařízení s Windows 8.1. Pokud je nastavené na **Nenakonfigurováno**, použijí se tato nastavení také na zařízení s Windows 10.
- **Název připojení** – zadejte název tohoto připojení. Tento název uživatelé uvidí, když budou na svém zařízení procházet seznamem dostupných připojení VPN.
- **Servery** – přidejte minimálně jeden VPN server, ke kterému se budou zařízení připojovat.
    - **Přidat** – otevře okno **Přidat řádek**, ve kterém můžete zadat následující informace:
        - **Popis** – zadejte popisný název serveru, například **VPN server Contoso**.
        - **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se budou zařízení připojovat. Příklady: **192.168.1.1**, **vpn.contoso.com**.
        - **Výchozí server** – povolí tento server jako výchozí server, který budou zařízení používat k navázání připojení. Jako výchozí server musí být nastavený jenom jeden server.
    - **Importovat** – vyhledejte soubor, který obsahuje seznam serverů oddělených čárkami ve formátu popis, IP adresa nebo plně kvalifikovaný název domény, výchozí server. Zvolte **OK** a naimportujte tak servery do seznamu **Servery**.
    - **Exportovat** – exportuje seznam serverů do textového souboru s oddělovači (CSV).

- **Typ připojení** – z následujícího seznamu dodavatelů vyberte typ připojení VPN:
- **Check Point Capsule VPN**
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Doména nebo skupina přihlášení** (pouze Dell SonicWALL Mobile Connect) – zadejte název domény nebo skupiny přihlášení, ke které se chcete připojit.

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

**Příklad pro Dell SonicWALL Mobile Connect:**
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
- **Skript automatické konfigurace** – ke konfiguraci proxy serveru použijte konfigurační soubor. Zadejte **Adresu URL proxy serveru** (například **http://proxy.contoso.com**), na které se nachází konfigurační soubor.
- **Použít proxy server** – tuto možnost povolte, pokud chcete zadat nastavení proxy serveru ručně.
    - **Adresa** – zadejte adresu proxy serveru (jako IP adresu).
    - **Číslo portu** – zadejte číslo portu přidruženého k proxy serveru.
- **Obejít proxy server pro místní adresy** – pokud VPN server vyžaduje pro připojení proxy server, vyberte tuto možnost, když nechcete používat proxy server pro místní adresy, které zadáte. Další informace najdete v dokumentaci k Windows Serveru.



<!--HONumber=Feb17_HO1-->


