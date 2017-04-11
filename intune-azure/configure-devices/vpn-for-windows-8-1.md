---
title: "Nastavení Intune VPN pro zařízení s Windows 8.1"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o nastavení Intune, pomocí kterých můžete nakonfigurovat připojení VPN na zařízeních s Windows 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: f38526a3e60f2a6628e61ffca5f5d179a2718e9b


---

# <a name="vpn-settings-for-windows-81-devices-in-microsoft-intune"></a>Nastavení sítě VPN pro zařízení s Windows 8.1 v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

V závislosti na tom, jaká nastavení zvolíte, nebudou v níže uvedeném seznamu konfigurovatelné všechny hodnoty.

## <a name="base-vpn-settings"></a>Základní nastavení sítě VPN


- **Použít všechna nastavení jenom na Windows 8.1** – toto je nastavení, které můžete nakonfigurovat v klasickém portálu Intune. Na portálu Azure Portal toto nastavení nejde změnit. Pokud je nastavené na **Nakonfigurováno**, budou tato nastavení platit jenom pro zařízení s Windows 8.1. Pokud je nastavené na **Nenakonfigurováno**, budou tato nastavení platit také pro zařízení s Windows 10.
- **Název připojení** – zadejte název pro toto připojení. Tento název uživatelé uvidí, když budou na svém zařízení procházet seznamem dostupných připojení VPN.
- **Servery** – přidejte jeden nebo více serverů VPN, ke kterým se budou zařízení připojovat.
    - **Přidat** – otevře okno **Přidat řádek**, ve kterém můžete zadat tyto informace:
        - **Popis** – zadejte popisný název serveru, například **Contoso – server VPN**.
        - **IP adresa nebo plně kvalifikovaný název domény** – zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se budou zařízení připojovat. Příklady: **192.168.1.1**, **vpn.contoso.com**.
        - **Výchozí server** – povolí tento server jako výchozí server, který budou zařízení používat k navázání připojení. Jako výchozí server musí být nastavený jenom jeden server.
    - **Importovat** – přejděte k souboru, který obsahuje seznam serverů oddělených čárkami ve formátu popis, IP adresa nebo plně kvalifikovaný název domény, výchozí server. Zvolte **OK** a naimportujte tak servery do seznamu **Servery**.
    - **Exportovat** – exportuje seznam serverů do textového souboru s oddělovači (CSV).

- **Typ připojení** – vyberte typ připojení VPN z tohoto seznamu dodavatelů:
- **Check Point Capsule VPN**
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Doména nebo skupina přihlášení** (jenom pro Dell SonicWALL Mobile Connect) – zadejte název domény nebo skupiny přihlášení, ke které se chcete připojit.

- **Role** (jenom pro Pulse Secure) – zadejte název role uživatele, která má přístup k tomuto připojení. Role uživatele definuje osobní nastavení a možnosti a povolí nebo zakáže určité funkce přístupu.

- **Sféra** (jenom pro Pulse Secure) – zadejte název sféry ověření, kterou chcete použít. Sféra ověření je seskupení prostředků ověření používaných typem připojení Pulse Secure.


- **Vlastní XML** – zadejte vlastní příkazy XML pro konfiguraci připojení VPN.

**Příklad pro Pulse Secure:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>

```

**Příklad pro Check Point Capsule VPN:**
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

- **Automaticky zjišťovat nastavení proxy serveru** – pokud server VPN vyžaduje pro připojení proxy server, zadejte, jestli mají zařízení automaticky zjišťovat nastavení připojení. Další informace najdete v dokumentaci k Windows Serveru.
- **Skript automatické konfigurace** – ke konfiguraci proxy serveru použijte konfigurační soubor. Zadejte **Adresu URL proxy serveru** (například **http://proxy.contoso.com**), na které je konfigurační soubor.
- **Použít proxy server** – tuto možnost povolte, pokud chcete zadat nastavení proxy serveru ručně.
    - **Adresa** – zadejte adresu proxy serveru (jako IP adresu).
    - **Číslo portu** – zadejte číslo portu přidruženého k proxy serveru.
- **Obejít proxy server pro místní adresy** – pokud server VPN vyžaduje pro připojení proxy server, vyberte tuto možnost, když nechcete používat proxy server pro místní adresy, které zadáte. Další informace najdete v dokumentaci k Windows Serveru.



<!--HONumber=Feb17_HO3-->


