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
translationtype: Human Translation
ms.sourcegitcommit: f2b364b2c57adab33df2a8e6b34c1f30c02988d3
ms.openlocfilehash: 9dbb44981c1525e6137dd8a469b1582731ee9719
ms.lasthandoff: 12/20/2016


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

Pak [zásadu nasaďte](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) jako obvykle.

## <a name="example-uri-settings"></a>Ukázková nastavení identifikátoru URI

Tato nastavení se dají použít k vytvoření vlastní konfigurace pro VPN ve fiktivní společnosti s názvem Contoso.
Všechny podrobnosti o všech dostupných nastaveních najdete v tématu [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx).

Nativní VPN Contoso (IKEv2): ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2 ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration &lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal** True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials** 1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address** 10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize** 8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn** true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id** %PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Další informace týkající se používání těchto nastavení a další podrobnosti o tom, co dělají, můžou zákazníci najít v dokumentaci poskytovatele konfigurační služby CSP: https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx.

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

