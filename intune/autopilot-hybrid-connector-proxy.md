---
title: Konfigurace nastavení proxy serveru pro konektor Intune pro službu Active Directory
description: Popisuje postup při konfiguraci konektoru Intune pro službu Active Directory pro práci s existující místní proxy servery.
keywords: ''
author: master11218
ms.author: tanvira
manager: smantri
ms.date: 4/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tanvira
ms.suite: ems
search.appverid: ''
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c47a7413d98467fffc26dee098a64cfeac770e4
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66043549"
---
# <a name="work-with-existing-on-premises-proxy-servers"></a>Práce s existující místní proxy servery

Tento článek vysvětluje postup při konfiguraci konektoru Intune pro službu Active Directory pro práci s odchozí proxy servery. Je určená pro zákazníky pomocí síťových prostředí, které mají existující proxy servery.

Další informace o tom, jak fungují konektory najdete v tématu [pochopit Azure AD Application Proxy konektory](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-connectors).

## <a name="bypass-outbound-proxies"></a>Odchozí proxy jednorázové přihlášení

Konektory mají základní komponenty operačního systému, které umožňují odchozí požadavky. Tyto součásti se automaticky pokusí vyhledat proxy server v síti pomocí Proxy Auto-Discovery WPAD (Web).

Součásti operačního systému došlo k pokusu o nalezení provádí vyhledávání DNS pro wpad.domainsuffix proxy server. Pokud vyhledávání ve službě DNS, IP adresu pro wpad.dat je potom k požadavku HTTP. Tento požadavek se změní na skript konfigurace proxy serveru ve vašem prostředí. Konektor používá tento skript k výběru odchozího proxy serveru. Ale konektor provoz nemusí stále procházejí, z důvodu další nastavení konfigurace na proxy serveru.

Můžete nakonfigurovat konektor obejít vaše místní proxy a zajistit, aby používal přímé připojení ke službám Azure. Tento přístup, doporučujeme tak dlouho, dokud zásady sítě umožňuje, protože znamená, že máte jeden menší konfiguraci udržovat.

Chcete-li zakázat použití odchozího proxy serveru pro konektor, upravte: \Program Files\Microsoft Intune\ODJConnector\ODJConnectorUI\ODJConnectorUI.exe.config a přidejte adresu proxy serveru a port proxy serveru v části uvedené v této ukázce kódu:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <runtime>
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
            <dependentAssembly>
                <assemblyIdentity name="mscorlib" publicKeyToken="b77a5c561934e089" culture="neutral"/>
                <bindingRedirect oldVersion="0.0.0.0-2.0.0.0" newVersion="4.6.0.0" />
            </dependentAssembly>
        </assemblyBinding>
    </runtime>
    <startup> 
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="SignInURL" value="https://portal.manage.microsoft.com/Home/ClientLogon"/>
        <add key="LocationServiceEndpoint" value="RestUserAuthLocationService/RestUserAuthLocationService/ServiceAddresses"/>
    </appSettings>
</configuration>
```
Ujistěte se, že service Connector Updater také obchází proxy serveru, proveďte podobné změny C:\Program Files\Microsoft Intune\ODJConnector\ODJConnectorSvc\ODJConnectorSvc.exe.config.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <startup>
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="BaseServiceAddress" value="https://manage.microsoft.com/" />
    </appSettings>
</configuration>
```

Nezapomeňte si vytvořte kopie původního souborů v případě, že budete potřebovat obnovit v souborech .config výchozí.

Jakmile konfigurační soubory byly změněny, je potřeba restartovat službu Intune Connector service. 

1. Otevřít **services.msc**.
2. Vyhledejte a vyberte **služby Intune konektor Odj**.
3. Vyberte **restartovat**.

![Snímek obrazovky restart služby](media/autopilot-hybrid-connector-proxy/service-restart.png)


## <a name="next-steps"></a>Další postup

[Správa zařízení](device-management.md)