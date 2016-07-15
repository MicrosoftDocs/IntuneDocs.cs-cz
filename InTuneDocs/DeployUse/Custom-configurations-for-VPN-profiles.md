---
# required metadata

title: Vlastní konfigurace pro profily VPN | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Vlastní konfigurace pro profily VPN

## Vytvoření vlastní konfigurace
Vlastní konfigurace můžete použít k vytvoření profilů VPN v Intune. Vytvoření vlastní konfigurace:

   1. V konzole správce Intune vyberte **Zásady** -> **Přidat zásadu** -> *<Expand platform>* -> **Vlastní konfigurace** -> **Vytvořit zásadu**..
   2. Zadejte název pro tuto zásadu.
   3. U každého nastavení identifikátoru URI klikněte na **Přidat** a zadejte požadované informace. Tady je příklad:

   ![Dialogové okno vlastní konfigurace profilu VPN](intune/media/Intune_Add_VPN_URI.png)

   4.  Po zadání všech nastavení identifikátorů URI klikněte na **Uložit zásadu** a potom nasaďte zásadu.

## Nasazení zásady konfigurace

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a potom klikněte na **Spravovat nasazení**..

2.  V dialogovém okně **Spravovat nasazení** :

    -   **Pokud chcete zásadu nasadit** – vyberte jednu nebo víc skupin, do kterých chcete zásady nasadit, a potom klikněte na **Přidat** &gt; **OK**..

    -   **Pokud chcete dialogové okno zavřít bez nasazení zásady** – klikněte na **Zrušit**..

Když vyberete nasazenou zásadu, zobrazí se v dolní části seznamu zásad další informace o tomto nasazení.

##Příklad nastavení identifikátoru URI pro vlastní konfiguraci profilu VPN
Tady jsou příklady položek hodnot identifikátoru URI pro vytvoření vlastní konfigurace pro VPN ve fiktivní společnosti s názvem Contoso. Další informace, jako je datový typ jednotlivých položek, najdete v tématu [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx).

Nativní VPN Contoso (IKEv2):
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration
&lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**
Pravda

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**
1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**
10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**
8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**
true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**
%PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Další informace týkající se používání těchto nastavení a další podrobnosti o tom, co dělají, uživatelé najdou v dokumentaci CSP:
https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx

## Nastavení identifikátorů URI pro VPN pro aplikace pro Android na PulseSecure
### VLASTNÍ IDENTIFIKÁTORY URI PRO SEZNAM BALÍKŮ 
-  Datový typ = Řetězec
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/<Name>/PackageList 
-  Hodnota = Seznam balíčků oddělený oddělovači.
   - Oddělovače: středník (;), dvojtečka (:), čárka (,), svislá čára (|)

Příklady: 
- com.android.chrome
- com.android.chrome;com.android.browser

### VLASTNÍ IDENTIFIKÁTOR URI PRO REŽIM (VOLITELNÉ)
- Datový typ = Řetězec
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode 

> Poznámky
> - Použijte stejný *název*, který jste přiřadili k vlastními profilu.
> - Možné hodnoty: *GLOBAL*, *WHITELIST*, *BLACKLIST*
> - Pokud není poskytnutá žádná hodnota PackageList, výchozí hodnota je *GLOBAL* (zpětná kompatibilita se systémovými profily).
> - Pokud je poskytnutá hodnota PackageList, výchozí hodnota je *WHITELIST*.


### Související témata
(Připojení VPN v Microsoft Intune)[vpn-connections-in-microsoft-intune.md]


<!--HONumber=May16_HO1-->


