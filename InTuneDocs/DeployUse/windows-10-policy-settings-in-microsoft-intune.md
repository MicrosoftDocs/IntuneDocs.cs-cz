---
title: "Nastavení zásad pro Windows 10 | Microsoft Intune"
description: "Nastavení zásad, která jsou uvedena v tomto tématu, vám pomohou nakonfigurovat předdefinovaná a vlastní nastavení pro zaregistrované počítače s Windows 10 a zařízení Windows 10 Mobile."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b8522406a3c73746b09616c3ec917464cf751312
ms.openlocfilehash: 6e482beb5e2edce648ecb6f1821baa6214fa0f2f


---

# Nastavení zásad Intune pro zařízení s Windows 10 v Microsoft Intune

Informace v tomto tématu vám pomůžou pochopit nastavení zásad Intune, které lze použít ke správě zařízení s Windows 10. Po přečtení tématu a postupů na stránce [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) budete umět konfigurovat předdefinované a vlastní nastavení na zaregistrovaných počítačích s Windows 10 a zařízeních s Windows 10 Mobile. Zásady nejde použít pro počítače [s klientským softwarem Intune pro počítače](/intune/get-started/windows-pc-management-capabilities-in-microsoft-intune).

Můžete si vybrat ze dvou typů zásad:

- **Vlastní zásady** – Na Windows 10 a Windows 10 Mobile použijte **vlastní zásady**, pokud chcete nasadit nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier), s jehož pomocí se dají ovládat funkce na zařízeních. Řada nastavení je ve Windows 10 přístupná prostřednictvím [poskytovatele konfiguračních služeb pro zásady](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Obecné zásady konfigurace** – Tento typ zásad použijte, pokud chcete nastavení vybrat z předdefinovaného seznamu dodávaného s Microsoft Intune.

## Nastavení vlastních zásad

Při nastavení vlastních zásad zadejte tyto údaje:

## &nbsp;&nbsp;&nbsp;Obecné

Zadejte název a (volitelně) popis zásady, který vám pomůže při její identifikaci v konzole Intune.

## &nbsp;&nbsp;&nbsp;Nastavení OMA-URI

Ke každému nastavení OMA-URI, které chcete přidat, zadejte následující informace. Informace o použitelném nastavení se dočtete v části tohoto tématu [Nastavení Windows 10 URI](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings): 

- **Název nastavení** – Zadejte jedinečný název nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.
- **Popis nastavení** – Volitelně zadejte popis nastavení.
- **Datový typ** – Vybírejte z těchto typů:
    - **Řetězec**
    - **Řetězec (XML)**
    - **Datum a čas**
    - **Celé číslo**
    - **Číslo s plovoucí desetinnou čárkou**
    - **Logická hodnota**
- **OMA-URI (rozlišuje velká a malá písmena)** – Uveďte, který OMA-URI chcete nastavit.
- **Hodnota** – Zadejte hodnotu, která má být k uvedenému OMA-URI přidružena.

### Příklad
Na snímku obrazovky níže je nastavení **Connectivity/AllowVPNOverCellular** povolené. To umožňuje zařízení s Windows 10 spustit připojení VPN přes mobilní síť.

> ![Příklad vlastní zásady s nastavením VPN](./media/custom-policy-example.png)

## - Nastavení Windows 10 URI
V této části se dočtete o nastaveních OMA-URI, která můžete nakonfigurovat prostřednictvím **vlastních zásad pro Windows 10**.

## &nbsp;&nbsp;&nbsp;Zásady

|Název a URI zásady|Podrobnosti|
|---------------|------------|-----------|
|**Povolit automatickou aktualizaci**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Jen pro počítače<br>**Datový typ:** Celé číslo<br />**Hodnoty:** **0** - **5** (výchozí: **1**)|
|**Den plánované instalace**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Jen pro mobilní zařízení<br>**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Každý den (výchozí)<br>**1** – Neděle<br>**2** – Pondělí<br>**3** – Úterý<br>**4** – Středa<br>**5** – Čtvrtek<br>**6** – Pátek<br>**7** – Sobota|
|**Čas plánované instalace**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0**–**23** hodin (**0** je půlnoc) (výchozí: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Uživatel nemůže nastavovat časovač období odkladu hesla a hodnota je nastavená na „pokaždé“.<br>**1** – Uživatel může nastavovat časovač období odkladu hesla. (výchozí)|
|**Wi-Fi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Nepovolit **použití připojení Wi-Fi**<br>**1** – **Povolit použití připojení Wi-Fi**|
|**Wi-Fi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Pro počítače i mobilní zařízení<br>**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovolit sdílení internetu, **1** – Povolit sdílení internetu (výchozí)|
|**Wi-Fi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Wi-Fi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Nepovoluje se žádné Wi-Fi připojení mimo těch zřízených v MDM.<br>**1** – Povoluje se přidávání nových SSID sítí nad rámec těch, které jsou už zřízené v MDM.|
|**Systém/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Pro počítače i mobilní zařízení<br>**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – nepovoluje se (nastavení pouze v Enterprise)<br>**1** – omezená<br>**2** – úplná (výchozí)<br>**3** – úplná plus diagnostické informace|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – nepovoluje se<br>**1** – pouze nastavení (výchozí)<br>**2** – nastavení a experimentování|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – nepovolit režim Anti Theft<br>**1** – předvolba uživatele (výchozí)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – VPN přes mobilní síť se nepovoluje.<br>**1** – VPN může použít jakékoli připojení, včetně mobilního.|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Nepovolit uživateli zapnout Bluetooth.<br>**1** – Vyhrazeno. Uživatel můžete zapnout a konfigurovat Bluetooth (nepodporované ve Windows Phone 8.1 pro MDM, EAS, Windows 10 desktop a Windows 10 Mobile)<br>**2** – Povoleno. Uživatel můžete zapnout a nakonfigurovat Bluetooth (výchozí).|
|**Experience/AllowScreenCapture**<br>./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Experience/AllowTaskSwitcher**<br>./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Experience/AllowVoiceRecording**<br>./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Experience/AllowSyncMySettings**<br>./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovolí roaming. **1** – Povolí roaming. (výchozí)|
|**Experience/AllowManualMDMUnenrollment**<br>./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Accounts/AllowMicrosoftAccountConnection**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Security/AllowManualRootCertificateInstallation**<br>./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Security/AllowAddProvisioningPackages**<br>./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Search/DisableBackoff**<br>./Vendor/MSFT/Policy/Config/Search/DisableBackoff|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** (výchozí), **1**|
|**Search/PreventRemoteQueries**<br>./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0**, **1** (výchozí)|
|**Search/AllowUsingDiacritics**<br>./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** (výchozí), **1**|
|**Search/AlwaysUseAutoLangDetection**<br>./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** (výchozí), **1**|
|**Search/DisableRemovableDriveIndexing**<br>./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** (výchozí), **1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0**, **1** (výchozí)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** (výchozí), **1**|
|**Security/AllowRemoveProvisioningPackage**<br>./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Security/RequireProvisioningPackageSignature**<br>./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** (výchozí), **1**|
|**AboveLock/AllowActionCenterNotifications**<br>./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Nepovolit<br>Slovník Open Extended Dictionary je vypnutý.<br>Uživatel nemůže:<br>– přidat nový slovník Open Extended Dictionary,<br />– přidat nový soubor konfigurace integrace vyhledávání,<br>– používat funkci kandidáta cloudu,<br>– odesílat uživatelem registrované slovo.<br>**1** – Povolit<br>Slovník Open Extended Dictionary se může přidat a používat jako výchozí. Také funkce integrace vyhledávání se dá používat ve výchozím nastavení.<br>Uživatel může:<br>používat funkci kandidáta cloudu.|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Protokolování neúspěšných převodů je vypnuté.<br>**1** – Protokolování neúspěšných převodů je zapnuté. (výchozí)|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Nefiltrují se žádné znaky (výchozí).<br>**1** – Filtruje se všechno kromě znaků Shift JIS.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br />**0** – Nefiltrují se žádné znaky (výchozí).<br>**1** – Filtruje se všechno kromě znaků JIS0208.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Nefiltrují se žádné znaky (výchozí).<br>**1** – Filtruje se všechno kromě znaků JIS0208 nebo EUDC.|
|**TextInput/AllowInputPanel**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Bluetooth/AllowDiscoverableMode**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Bluetooth/AllowAdvertising**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Settings/AllowDataSense**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDataSense|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Settings/AllowVPN**<br>./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Settings/AllowWorkplace**<br>./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Settings/AllowDateTime**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDateTime|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Settings/AllowLanguage**<br>./Vendor/MSFT/Policy/Config/Settings/AllowLanguage|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Settings/AllowRegion**<br>./Vendor/MSFT/Policy/Config/Settings/AllowRegion|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Settings/AllowSignInOptions**<br>./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Settings/AllowYourAccount**<br>./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Settings/AllowPowerSleep**<br>./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Settings/AllowAutoPlay**<br>./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Experience/AllowCortana**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCortana|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Striktní, největší filtrování obsahu pro dospělé<br>**1** – Střední, střední filtrování obsahu pro dospělé (platné výsledky vyhledávání se nebudou filtrovat – výchozí)|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Force Start Size**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Povolit změnu velikosti uživatelem (výchozí)<br>**1** – Vynutit režim v okně<br>**2** – Vynutit celoobrazovkový režim|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0**: Neodkládat upgrade (zůstat v CB – výchozí)<br>**1**: Povolit odložení aktualizací a upgradů (zařízení postupuje podle pravidel aktuální větve pro podnikání, CBB)<br />Podrobnosti najdete v tématech:<br>[Úvod do údržby Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plán pro nasazení Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Pro počítače i mobilní zařízení<br>**Popis:** Zásada umožňující odložení aktualizací softwaru až o 4 týdny<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br> **0**: Použít aktualizace okamžitě (výchozí)<br>**1**-**4**: Počet týdnů odložení aktualizací softwaru<br />Podrobnosti najdete v tématech:<br>[Úvod do údržby Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plán pro nasazení Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Pro počítače i mobilní zařízení<br>**Popis:** Zásada umožňující odložení upgradu funkcí až o 8 měsíců<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0**: Použít aktualizace okamžitě (výchozí)<br>**1**-**8**: Počet měsíců odložení upgradu funkcí<br />Podrobnosti najdete v tématech:<br>[Úvod do údržby Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plán pro nasazení Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Pro počítače i mobilní zařízení<br>**Popis:** Umožňuje zařízení zastavit přijímání aktualizací a upgradů po dobu až 5 týdnů.<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0**: Použít aktualizace okamžitě (výchozí)<br>**1**: Pozastavit aktualizace a upgrady (platnost po 5 týdnech vyprší)|

## &nbsp;&nbsp;&nbsp;Windows Defender

|Název a URI zásady|Podrobnosti|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Monitorovat všechny soubory (výchozí)<br>**1** – Monitorovat příchozí soubory<br>**2** – Monitorovat odchozí soubory|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** - **90** – Představuje dobu, po kterou se bude uchovávat malware.<br>**Výchozí:** **0** – Uchová složku karantény navždy, automaticky se neodstraní.|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**1** – Rychlé prohledání (výchozí)<br>**2** – Úplné prohledání|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Každý den (výchozí)<br>**1** – Pondělí<br>**2** – Úterý<br>**3** – Středa<br>**4** – Čtvrtek<br>**5** – Pátek<br>**6** – Sobota<br>**7** – Neděle<br>**8** – Prohledání není naplánované|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – 12:00<br>**60** – 1:00<br>**120** – 2:00 (výchozí)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1381** – Časové období údržby|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Jen pro počítače<br>**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – 12:00<br>**60** – 1:00<br>**120** – 2:00 (výchozí)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1380** – 23:00|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** - **100** (výchozí: **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|Jen pro počítače<br />**Datový typ:** Celé číslo<br>**Hodnoty:** **0** – Nepovoleno (výchozí), **1** – Povoleno|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno (výchozí), **1** – Povoleno|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí) – Pokud je povoleno, spustí se také při zapnutém RTP.|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Nekontrolovat signatury v intervalu<br>**1** – Kontrolovat signatury každou hodinu<br>**2** – Kontrolovat každé dvě hodiny atd.<br>**24** – Kontrolovat každý den<br>**Výchozí hodnota:** 8 – Kontrolovat každých osm hodin|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Vždycky se zeptat (výchozí)<br>**1** – Posílat bezpečné vzorky automaticky<br>**2** – Nikdy neposílat<br>**3** – Posílat všechny vzorky automaticky|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|Jen pro počítače<br />**Datový typ:** Řetězec<br />**Hodnoty:**<br>*&lt;seznam přípon oddělený středníkem&gt;* Např. **obj;lib**<br>**Výchozí:** Nevylučují se žádné přípony.|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|Jen pro počítače<br />**Datový typ:** Řetězec<br />**Hodnoty:**<br />*&lt;seznam cest oddělený středníkem&gt;*<br />Příklad: **c:\test;c:\test1.exe**<br />**Výchozí hodnota:** Nevylučují se žádné cesty.|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|Jen pro počítače<br />**Datový typ:** Řetězec<br />**Hodnoty:**<br>*&lt;seznam cest oddělený středníkem&gt;*<br>Příklad: **c:\test.exe;c:\test1.exe**<br>**Výchozí hodnota:** Nevylučují se žádné procesy.|

## &nbsp;&nbsp;&nbsp;Prohlížeč Edge

|Název a URI zásady|Podrobnosti|
|---------------|------------|-----------|
|**Povolit prohlížeč**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0**: vypnuté prohlížení, **1**: zapnuté prohlížení (výchozí)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0**: nezobrazovat návrhy, **1**: zobrazovat návrhy (výchozí)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Zakázáno (otevřít intranetové servery v prohlížeči Microsoft Edge)<br>**1**– Povoleno (otevřít intranetové servery v Internet Exploreru)|
|**Povolit Do Not Track**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Vypnuto (DNT se neodesílá – výchozí), **1** – Zapnuto (odesílá DNT)|
|**Konfigurovat SmartScreen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**Povolit automaticky otevíraná okna**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Blokovat automaticky otevíraná okna (výchozí), **1** – Povolit automaticky otevíraná okna|
|**Povolit soubory cookie**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Povolit soubory cookie ze všech webů (výchozí)<br>**1** – Blokovat jenom soubory cookie třetích stran<br>**2** – Blokovat všechny soubory cookie|
|**Povolit uložení hesla**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Správce hesel je zakázaný. <br>**1** – Správce hesel je povolený (výchozí).|
|**Povolit automatické vyplňování**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Jen pro počítače<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Zakázáno (výchozí), **1** – Povoleno|
|**Konfigurovat seznam webů podnikového režimu**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Jen pro počítače<br />**Datový typ:** Řetězec<br />**Hodnoty:<br>**0** – Nekonfigurováno<br>**1** – Použít seznam webů režimu podnikové sítě, pokud je nakonfigurován (výchozí)<br>**2** – Zadat umístění seznamu webů podnikového režimu|

## Obecná nastavení zásad konfigurace

Ke konfiguraci nastavení pro zaregistrovaná zařízení se systémem Windows 10 Desktop a Windows 10 Mobile použijte **předdefinované zásady konfigurace** služby Microsoft Intune pro Windows 10. 

## &nbsp;&nbsp;&nbsp;Heslo

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|
|**Vyžadovat heslo k odemknutí zařízení**|-|
|**Vyžadovaný typ hesla**|Určuje, jestli musí být heslo složené jen z čísel, nebo z čísel a písmen.|
|**Vyžadovaný typ hesla** - **Minimální počet znakových sad**|Používají se čtyři znakové sady: malá písmena, velká písmena, číslice a symboly. Toto nastavení určuje, kolik z těchto sad musí být v hesle zahrnuto.|
|**Minimální délka hesla**|Platí jen pro Windows 10 Mobile.|
|**Počet povolených opakovaných neúspěšných přihlášení, než bude zařízení vymazáno**|Pro zařízení s Windows 10: Pokud má zařízení povolený nástroj BitLocker, přejde do režimu obnovení nástroje BitLocker v případě, že se nepovede určený počet pokusů o přihlášení. Pokud zařízení nemá povolený nástroj BitLocker, toto nastavení se na něj nevztahuje.<br>Pro zařízení s Windows 10: Jakmile se nepovede určený počet pokusů o přihlášení, zařízení bude vymazáno.|
|**Počet minut nečinnosti před vypnutím displeje**|Určuje dobu, kterou musí být zařízení v nečinnosti, než se uzamkne jeho obrazovka.|
|**Omezená platnost hesla (ve dnech)**|Toto nastavení určuje dobu, po jejímž uplynutí je třeba změnit heslo k zařízení.|
|**Pamatovat si historii hesel**|Určuje, jestli chcete uživatelům zabránit ve vytváření hesel, která používali dřív.|
|**Pamatovat si historii hesel** - **Zabránit opětovnému použití předchozích hesel**|Určuje počet dříve použitých hesel, která si zařízení zapamatuje.|
|**Po návratu zařízení ze stavu nečinnosti vyžadovat heslo**|Pokud je povoleno, musí uživatel zařízení odemknout zadáním hesla. (jenom Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;Encryption

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|
|**Vyžadovat šifrování u mobilního zařízení**|Povoluje šifrování na cílových zařízeních.<br>(jenom Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;Systému

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|
|**Povolit snímek obrazovky**|Umožňuje uživateli zachytit obrazovku zařízení v podobě obrázku. (jenom Windows 10 Mobile)|
|**Povolit manuální zrušení zápisu**|Umožňuje uživateli ze zařízení ručně odstranit pracovní účet.|
|**Umožnit ruční instalaci kořenového certifikátu**|Platí pro Windows 10 Mobile.|
|**Povolit odesílání diagnostických dat a dat o použití do Microsoftu**|Možné hodnoty:<br><br>**Ne:** Microsoftu se neodešlou žádná data.<br>**Základní:** Microsoftu se odešle omezené množství dat.<br>**Rozšířené:** Microsoftu se odešlou rozšířená data pro diagnostiku.<br>**Úplné (doporučeno):** Odešle stejná data jako možnost **Rozšířené** a k tomu navíc údaje o stavu zařízení.|


## &nbsp;&nbsp;&nbsp;Účet a synchronizace

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|---------------------|
|**Povolit účet Microsoft**|Umožňuje uživateli přidružit k zařízení účet Microsoft.|
|**Povolit ruční přidávání jiných účtů, než jsou účty Microsoft**|Umožní uživateli přidat do zařízení e-mailové účty, které nejsou přidružené k účtu Microsoft.|
|**Povolit synchronizaci nastavení u účtů Microsoft**|Povolí synchronizaci nastavení zařízení a aplikací přidružených k účtu Microsoft mezi zařízeními.|

## &nbsp;&nbsp;&nbsp;Microsoft Edge

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|
|**Povolit webový prohlížeč**|Umožňuje na zařízení používat webový prohlížeč Microsoft Edge.<br>(jenom Windows 10 Mobile)|
|**Povolit návrhy vyhledávání v panelu Adresa**|Umožňuje, aby vám vyhledávací web při psaní hledaného textu navrhoval weby.|
|**Povolit odesílání intranetového provozu do Internet Exploreru**|Umožňuje uživatelům otevírat intranetové weby v Internet Exploreru.<br>(jenom Windows 10 Desktop)|
|**Povolit Do Not Track**|Nakonfiguruje prohlížeč Microsoft Edge tak, aby se webům, které uživatelé navštíví, odesílaly hlavičky DNT (Do Not Track).|
|**Povolit SmartScreen**|-|
|**Povolit aktivní skriptování**|Umožňuje, aby se v prohlížeči Microsoft Edge mohly spustit skripty, například Javascripty.|
|**Povolit automaticky otevíraná okna**|Platí jen pro Windows 10 Desktop|
|**Povolit soubory cookie**|-|
|**Povolit automatické vyplňování**|Umožňuje uživatelům změnit nastavení automatického dokončování v prohlížeči.<br>(jenom Windows 10 Desktop)|
|**Povolit správce hesel**|Umožňuje povolit nebo zakázat funkci Povolit správce hesel.|
|**Umístění webů podnikového režimu**|Určuje, kde najít seznam webů, které se otevřou v podnikovém režimu. Uživatelé nemohou tento seznam upravovat.<br>(jenom Windows 10 Desktop)|

## &nbsp;&nbsp;&nbsp;Aplikace

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|---------------------|
|**Povolit obchod s aplikacemi**|Platí jen pro Windows 10 Mobile.|



## &nbsp;&nbsp;&nbsp;Mobilní služby

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|---------------------|
|**Povolit datový roaming**|Povoluje roaming mezi sítěmi při přístupu k datům.|
|**Povolit VPN v mobilní síti**|Určuje, jestli zařízení může při připojení k mobilní síti získat přístup k připojením VPN.|
|**Povolit VPN v mobilní síti v roamingu**|Určuje, jestli zařízení může při roamingu v mobilní síti získat přístup k připojením VPN.|

## &nbsp;&nbsp;&nbsp;Hardware

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|
|**Povolit fotoaparát**|-|
|**Povolit vyměnitelné úložiště**|Určuje, jestli je možné se zařízením použít zařízení externího úložiště, jako jsou SD karty.|
|**Povolit Wi-Fi**|Platí jen pro Windows 10 Mobile.|
|**Povolit sdílení internetu**|Povolí sdílení internetového připojení v zařízení.|
|**Povolit ruční konfiguraci připojení Wi-Fi**|Určuje, jestli může uživatel nakonfigurovat svoje vlastní Wi-Fi připojení nebo jestli může použít pouze připojení nakonfigurovaná v rámci profilu Wi-Fi sítě.<br>(jenom Windows 10 Mobile)|
|**Povolit automatické připojení k bezplatným Wi-Fi hotspotům**|Umožňuje zařízení automaticky se připojovat k volným Wi-Fi hotspotům a automaticky pro připojení přijímat jakékoli podmínky a ujednání.|
|**Povolit zeměpisnou polohu**|Určuje, jestli zařízení může používat informace služeb určování polohy.|
|**Povolit komunikaci NFC**|Umožňuje zařízení využívat jeho funkce NFC.|
|**Povolit Bluetooth**|-|
|**Povolit zjistitelný režim Bluetooth**|Umožňuje nastavit, aby bylo toto zařízení zjistitelné jinými zařízeními podporujícími technologii Bluetooth.|
|**Povolit reklamu přes Bluetooth**|Umožňuje zařízení přijímat reklamu přes Bluetooth.|
|**Povolit obnovení továrního nastavení telefonu**|Určuje, jestli uživatel může na svém zařízení obnovit tovární nastavení.|
|**Povolit připojení USB**|Určuje, jestli má zařízení přístup k zařízením externího úložiště prostřednictvím připojení USB.|
|**Povolit režim AntiTheft**|Umožňuje nakonfigurovat, jestli má být povolený režim Windows Antitheft.|

## &nbsp;&nbsp;&nbsp;Funkce:

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|----------------------|---------------------|
|**Povolit kopírování a vkládání**|Platí jen pro Windows 10 Mobile.|
|**Povolit záznam hlasu**|Platí jen pro Windows 10 Mobile.|
|**Povolit Cortanu**|Povolí nebo zakáže hlasového asistenta Cortany.|
|**Povolit oznámení centra akcí**|Povolí nebo zakáže oznámení Centra akcí na zamykací obrazovce zařízení.<br>(jenom Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;Windows Defender

Všechna nastavení jsou jenom pro Windows 10 Desktop.

|Název nastavení|Další informace (kde jsou potřeba)|
|-|-|
|**Povolit monitorování v reálném čase**|Umožňuje v reálném čase zjišťovat v počítači existenci malwaru, spywaru a dalšího nežádoucího softwaru.|
|**Povolit monitorování chování**|Umožňuje programu Defender zjišťovat výskyt určitých známých vzorců podezřelých aktivit na zařízeních.|
|**Povolit systém kontroly sítě**|Systém kontroly sítě (NIS) pomáhá chránit zařízení před zneužitím prostřednictvím sítě, a to pomocí signatur známých chyb zabezpečení z konzoly Microsoft Endpoint Protection Center. Tímto způsobem dokáže detekovat a blokovat škodlivý přenos dat.|
|**Kontrolovat všechny stahované soubory**|Určuje, jestli bude Defender kontrolovat všechny soubory stahované z internetu.|
|**Povolit kontrolu skriptů**|Umožňuje programu Defender kontrolovat skripty, které se používají v Internet Exploreru.|
|**Monitorovat aktivitu souborů a programů**|Povolením tohoto nastavení můžete programu Defender umožnit monitorování aktivity souborů a programů v zařízení.|
|**Kolik dnů sledovat rozpoznaný malware**|Umožňuje programu Defender dál sledovat rozpoznaný malware po vámi určený počet dní, aby bylo možné ručně zkontrolovat dříve zasažená zařízení. Pokud nastavíte počet dnů **0**, malware zůstane ve složce karantény a automaticky se neodebere. |
|**Umožnit přístup k uživatelskému rozhraní klienta**|Určuje, jestli se bude koncovým uživatelům zobrazovat uživatelské rozhraní Windows Defenderu.<br>Pokud toto nastavení změníte, projeví se při příštím restartování počítače koncového uživatele.|
|**Naplánovat každodenní rychlou kontrolu**|Umožňuje vám naplánovat rychlou kontrolu, ke kterému dochází denně v době, kterou vyberete.|
|**Naplánovat úplnou kontrolu**|Umožňuje naplánovat úplnou nebo rychlou systémovou kontrolu, která probíhá pravidelně v den a čas, který vyberete.|
|**Omezit využití procesoru při prověřování**|Umožňuje nastavit maximální procento využití procesoru, které je možné využívat k provádění kontrol (od **1** do **100**).|
|**Prohledat archivní soubory**|Umožňuje programu Defender zkontrolovat soubory archivu, jako jsou soubory Zip nebo Cab.|
|**Kontrolovat e-mailové zprávy**|Umožňuje programu Defender kontrolovat e-mailové zprávy při jejich doručování na zařízení.|
|**Kontrolovat vyměnitelné jednotky**|Umožňuje programu Defender kontrolovat vyměnitelné jednotky, jako jsou USB flash disky.|
|**Kontrolovat namapované síťové jednotky**|Umožňuje programu Defender kontrolovat soubory na namapované síťové jednotce.<br>Pokud jsou soubory na disku jen pro čtení, nebude z nich Defender schopen odebrat žádný malware, který v nich najde.|
|**Kontrolovat soubory otevřené ze síťových sdílených složek**|Umožňuje programu Defender zkontrolovat soubory na sdílených síťových jednotkách (například na těch, ke kterým se získává přístup pomocí cesty UNC).<br>Pokud jsou soubory na disku jen pro čtení, nebude z nich Defender schopen odebrat žádný malware, který v nich najde.|
|**Interval aktualizace signatur**|Zadejte interval, ve kterém bude Defender zjišťovat dostupnost nových souborů signatur.|
|**Povolit cloudovou ochranu**|Umožňuje službě Microsoft Active Protection Service povolit nebo blokovat příjem informací o činnosti malwaru ze zařízení, která spravujete. Tyto informace slouží k budoucímu vylepšování služby.|
|**Dotázat se uživatelů na odesílání vzorků**|Určuje, jestli se mají do Microsoftu automaticky odesílat soubory, které by mohly vyžadovat další analýzu, aby bylo určeno, zda jsou škodlivé.|
|**Detekce potenciálně nežádoucích aplikací**|Pomocí tohoto nastavení lze chránit zaregistrovaná stolní zařízení s Windows před spuštěním softwaru, který Windows Defender klasifikuje jako potenciálně nežádoucí. Můžete nastavit ochranu před spuštěním těchto aplikací nebo pomocí režimu auditu upozornit, když se potenciálně nežádoucí aplikace nainstaluje.|
|**Soubory a složky, které mají být vyloučeny z kontroly a ochrany v reálném čase**|Umožňuje do seznamu vyloučení přidat soubory a složky, například **C:\Cesta** nebo **%ProgramFiles%\Cesta\název_souboru.exe**. Tyto soubory a složky nebudou zahrnuty do kontrol probíhajících v reálném čase ani do plánovaných kontrol.|
|**Vyloučit přípony souborů při použití prověřování nebo ochrany v reálném čase**|Umožňuje do seznamu vyloučení přidat přípony souborů, například **jpg** nebo **txt**. Soubory s těmito příponami nebudou zahrnuty do kontrol probíhajících v reálném čase ani do plánovaných kontrol.|
|**Vyloučit procesy při použití prověřování nebo ochrany v reálném čase**|Umožňuje do seznamu vyloučení přidat procesy typu **.exe**, **.com** nebo **.scr**. Tyto procesy nebudou zahrnuty do kontrol probíhajících v reálném čase ani do plánovaných kontrol.| 


## &nbsp;&nbsp;&nbsp;Updates

|Název nastavení|Další informace (kde jsou potřeba)|
|----------------|---------------|
|**Povolit automatické aktualizace**|Toto nastavení povolte, pokud chcete povolit automatické aktualizace. Pak nakonfigurováním jedno z následujících nastavení můžete řídit chování aktualizací:<br />**Upozornění na stahování**<br />**Automaticky nainstalovat v době údržby**<br />**Automaticky nainstalovat a restartovat v době údržby**<br />**Automaticky nainstalovat a restartovat v plánovaném čase** **Poznámka:** Pokud je vybraná tato možnost, můžete také nakonfigurovat nastavení **Potlačit oznámení pro koncového uživatele** a **Definujte den instalace pro plánované aktualizace**.<br>(jenom Windows 10 Desktop)|
|**Povolit předběžné verze funkcí**|Umožňuje Microsoftu do zařízení nasadit předběžné funkce a nastavení do zařízení s Windows 10. Můžete vybrat, že se povolí jenom nastavení, nebo že se nainstalují všechny předběžné funkce a nastavení.|

### Viz taky
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)





<!--HONumber=Oct16_HO1-->


