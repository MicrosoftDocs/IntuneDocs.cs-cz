---
title: "Vytvoření vlastních profilů VPN s Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Vlastní konfigurace slouží k vytvoření profilů VPN v Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 132844bb1d1119390b7f55cca58cecbd5b8ee90a
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Vytvoření vlastních profilů VPN v Microsoft Intune

## <a name="create-a-custom-configuration"></a>Vytvoření vlastní konfigurace
Vlastní konfigurace Intune můžete použít k vytvoření profilů VPN pro:

* Zařízení se systémem Android 4 nebo novější verzí
* Zaregistrovaná zařízení se systémem Windows 8.1 a novějším
* Zařízení s Windows Phone 8.1 a novějším
* Zaregistrovaná zařízení s desktopovým systémem Windows 10 
* Zařízení, která používají Windows 10 Mobile

Tento typ zásad může být užitečný v případě, že standardní zásady Intune VPN neobsahují nastavení, které chcete použít.

## <a name="to-create-a-custom-configuration-policy"></a>Vytvoření vlastní zásady konfigurace:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Konfigurovat zařízení**.
4. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
5. V okně profilů zvolte **Vytvořit profil**.
6. V okně **Vytvořit profil** zadejte **Název** a **Popis** profilu VPN.
7. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete použít nastavení VPN. V současné době můžete pro vlastní nastavení zařízení zvolit jednu z následujících platforem:
    - **Android**
    - **iOS** (konfigurace pomocí souboru, který jste exportovali z Apple Configuratoru)
    - **macOS** (konfigurace pomocí souboru, který jste exportovali z Apple Configuratoru)
    - **Windows Phone 8.1**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **Vlastní**.
7. V okně **Vlastní nastavení OMA-URI** zvolte pro každé nastavení URI, které chcete zadat, možnost **Přidat**, zadejte požadované informace a zvolte **OK**. Tady je příklad:

   ![Dialogové okno vlastní konfigurace profilu VPN](./media/Intune_Add_VPN_URI.png)

4.  Po zadání všech potřebných nastavení URI zvolte **OK** a pak v okně **Vytvořit profil** zvolte **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](how-to-assign-device-profiles.md).

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




