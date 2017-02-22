---
title: "Vlastní nastavení v Intune pro zařízení s Windows 10 | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Podívejte se na nastavení, která je možné použít ve vlastním profilu Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0da8c0fe399f76f43439cc66eaecd12bb454f9a6
ms.openlocfilehash: 05856480f8bb76e561f2b459d4ab800f9909a40a


---

# <a name="custom-device-settings-for-windows-10-devices-in-intune-azure-preview"></a>Vlastní nastavení zařízení s Windows 10 v Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

 **Vlastní** profil Microsoft Intune pro Windows 10 a Windows 10 Mobile použijte, pokud chcete nasadit nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier), s jehož pomocí se dají ovládat funkce na zařízeních. Řada nastavení je ve Windows 10 přístupná prostřednictvím [poskytovatele konfiguračních služeb pro zásady](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](how-to-configure-custom-settings.md).
2. Pokud chcete přidat nastavení OMA-URI, vyberte v okně **Vytvořit profil** možnost **Nastavení**.
3. V okně **Vlastní nastavení OMA-URI** klikněte na tlačítko **Přidat**, abyste mohli přidat novou hodnotu. Můžete také kliknout na **Exportovat** a vytvořit seznam všech hodnot, které jste nakonfigurovali v souboru hodnot oddělených čárkami (CSV).
4. Ke každému nastavení OMA-URI, které chcete přidat, zadejte následující informace. Použijte informace v seznamu v tomto tématu, kde zjistíte, jaká nastavení můžete použít:
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
5. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.
Profil se vytvoří a zobrazí se v okně se seznamem profilů.

## <a name="example"></a>Příklad
Na snímku obrazovky níže je nastavení **Connectivity/AllowVPNOverCellular** povolené. To umožňuje zařízení s Windows 10 spustit připojení VPN přes mobilní síť.

> ![Příklad vlastní zásady s nastavením VPN](./media/custom-policy-example.png)


## <a name="policy-settings"></a>Nastavení zásad

|Název a URI zásady|Podrobnosti|
|---------------|------------|-----------|
|**Povolit automatickou aktualizaci**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Jen pro počítače<br>**Datový typ:** Celé číslo<br />**Hodnoty:** **0** - **5** (výchozí: **1**)|
|**Den plánované instalace**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Jen pro mobilní zařízení<br>**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Každý den (výchozí)<br>**1** – Neděle<br>**2** – Pondělí<br>**3** – Úterý<br>**4** – Středa<br>**5** – Čtvrtek<br>**6** – Pátek<br>**7** – Sobota|
|**Čas plánované instalace**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0**–**23** hodin (**0** je půlnoc) (výchozí: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Uživatel nemůže nastavovat časovač období odkladu hesla a hodnota je nastavená na „pokaždé“.<br>**1** – Uživatel může nastavovat časovač období odkladu hesla. (výchozí)|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Nepovolit **použití připojení Wi-Fi**<br>**1** – **Povolit použití připojení Wi-Fi**|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Pro počítače i mobilní zařízení<br>**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovolit sdílení internetu, **1** – Povolit sdílení internetu (výchozí)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Nepovoluje se žádné Wi-Fi připojení mimo těch zřízených v MDM.<br>**1** – Povoluje se přidávání nových SSID sítí nad rámec těch, které jsou už zřízené v MDM.|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:** **0** – Nepovoleno, **1** – Povoleno (výchozí)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Pro počítače i mobilní zařízení<br>**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – nepovoluje se (nastavení pouze v Enterprise)<br>**1** – omezená<br>**2** – Úplná (výchozí)<br>**3** – Úplná plus diagnostické informace|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Pro počítače i mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – Nepovoluje se<br>**1** – Pouze nastavení (výchozí)<br>**2** – Nastavení a experimentování|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Jen pro mobilní zařízení<br />**Datový typ:** Celé číslo<br />**Hodnoty:**<br>**0** – nepovolit režim Anti Theft<br>**1** – Předvolba uživatele (výchozí)|
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

## <a name="windows-defender-settings"></a>Nastavení programu Windows Defender

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

## <a name="edge-browser-settings"></a>Nastavení prohlížeče Edge

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



<!--HONumber=Feb17_HO1-->


