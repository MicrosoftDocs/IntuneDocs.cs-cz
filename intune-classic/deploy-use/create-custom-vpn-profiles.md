---
title: "Vlastní konfigurace pro profily VPN | Dokumentace Microsoftu"
description: "Vlastní konfigurace slouží k vytvoření profilů VPN v Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 5216730e9736ff4b20abfb19058e82b995d82813
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="custom-configurations-for-microsoft-intune-vpn-profiles"></a>Vlastní konfigurace pro profily Microsoft Intune VPN

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="create-a-custom-configuration"></a>Vytvoření vlastní konfigurace
Vlastní konfigurace Intune můžete použít k vytvoření profilů VPN pro:

* Zařízení se systémem Android 4 nebo novější verzí
* Zařízení se systémem Android for Work
* Zaregistrovaná zařízení se systémem Windows 8.1 a novějším
* Zařízení s Windows Phone 8.1 a novějším
* Zaregistrovaná zařízení s desktopovým systémem Windows 10
* Zařízení s Windows 10 Mobile

Tento typ zásad může být užitečný v případě, že standardní zásady Intune VPN neobsahují nastavení, které chcete použít.

## <a name="to-create-a-custom-configuration-policy"></a>Vytvoření vlastní zásady konfigurace:

   1. V [konzole správce Intune](https://manage.microsoft.com) zvolte **Zásady** > **Přidat zásadu** > *Rozbalit platformu* > **Vlastní konfigurace** > **Vytvořit zásadu**.
   2. Zadejte název pro tuto zásadu.
   3. U každého nastavení identifikátoru URI, které chcete zadat, zvolte **Přidat** a zadejte požadované informace. Tady je příklad:

   ![Dialogové okno vlastní konfigurace profilu VPN](./media/Intune_Add_VPN_URI.png)

   4.  Po zadání všech nastavení identifikátorů URI zvolte **Uložit zásadu** a potom zásadu nasaďte.

Pak [zásadu nasaďte](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) jako obvykle.

## <a name="example-uri-settings"></a>Ukázková nastavení identifikátoru URI

Tato nastavení se dají použít k vytvoření vlastní konfigurace pro VPN ve fiktivní společnosti s názvem Contoso.
Všechny podrobnosti o všech dostupných nastaveních najdete v tématu [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx).

**Nativní VPN Contoso (IKEv2):**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

**vpn.contoso.com**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

**SplitTunnel**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

**Eap**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration
``` xml
<EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
   <EapMethod>
      <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
      <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
      <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
      <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
   </EapMethod>
   <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
      <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
         <Type>13</Type>
         <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
            <CredentialsSource>
               <CertificateStore>
                  <SimpleCertSelection>true</SimpleCertSelection>
               </CertificateStore>
            </CredentialsSource>
            <ServerValidation>
               <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
               <ServerNames></ServerNames>
            </ServerValidation>
            <DifferentUsername>false</DifferentUsername>
            <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </PerformServerValidation>
            <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </AcceptServerName>
         </EapType>
      </Eap>
   </Config>
</EapHostConfig>
```
**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**<br />
Pravda

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**<br />
1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**<br />
10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**<br />
8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**<br />
true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**<br />
%PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Další informace týkající se používání těchto nastavení a další podrobnosti o tom, co dělají, najdou uživatelé v [dokumentaci poskytovatele konfiguračních služeb](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).

## <a name="uri-settings-for-android-per-app-vpn-on-pulsesecure"></a>Nastavení identifikátorů URI pro VPN pro aplikace pro Android na PulseSecure
### <a name="custom-uri-for-package-list"></a>VLASTNÍ IDENTIFIKÁTORY URI PRO SEZNAM BALÍKŮ
-  Datový typ = Řetězec
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList
-  Hodnota = Seznam balíčků oddělený oddělovači.
   - Oddělovače: středník (;), dvojtečka (:), čárka (,), svislá čára (|)

Příklady:
- com.android.chrome
- com.android.chrome;com.android.browser

### <a name="custom-uri-for-mode-optional"></a>VLASTNÍ IDENTIFIKÁTOR URI PRO REŽIM (VOLITELNÉ)
- Datový typ = Řetězec
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode

> Poznámky
> - Použijte stejný *název*, který jste přiřadili k vlastními profilu.
> - Možné hodnoty: *GLOBAL*, *WHITELIST*, *BLACKLIST*
> - Pokud není poskytnutá žádná hodnota PackageList, výchozí hodnota je *GLOBAL* (zpětná kompatibilita se systémovými profily).
> - Pokud je poskytnutá hodnota PackageList, výchozí hodnota je *WHITELIST*.


### <a name="see-also"></a>Viz taky
[Připojení VPN v Microsoft Intune](vpn-connections-in-microsoft-intune.md)

