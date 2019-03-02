---
title: Rozhraní Graph API používaná při konfiguraci zařízení v Microsoft Intune – Azure | Dokumentace Microsoftu
titleSuffix: ''
description: Zobrazit seznam všech rozhraní Graph API s odpovídající zprostředkovatel kryptografických služeb Windows a posun identifikátoru URI na zařízení s Windows 10 a novější použité při konfiguraci zařízení v Microsoft Intune. Zobrazit odpovídající rozhraní API a zprostředkovatele kryptografických služeb pro sdílené počítače, služby endpoint protection, Windows Defender rozšířené ochrany před internetovými útoky, identity protection, Windows 10 týmy, beznabídkového režimu a Windows Update for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/01/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ccc46914e53e72d941cc726b6a32fa421e23ca4
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2019
ms.locfileid: "57232127"
---
# <a name="graph-apis-and-matching-windows-10-csps-used-in-intune"></a>Rozhraní Graph API a odpovídající CSP Windows 10 v Intune použít

Microsoft Intune používá [rozhraní Graph API](https://docs.microsoft.com/graph/api/resources/intune-graph-overview) ke konfiguraci zařízení (**Intune** > **konfigurace zařízení**) s Windows 10 a novější. Rozhraní Graph API používá poskytovatelů konfiguračních služeb (CSP), číst, nastavit, změnit nebo odstranit konfigurovat nastavení pro zařízení.

Tento seznam platí pro:

- Windows 10 a novější

Tento článek uvádí vlastnosti grafu a jejich odpovídající zprostředkovatele kryptografických služeb systému Windows 10 a posun identifikátorů URI.

## <a name="windows-10-csps"></a>Windows 10 CSPs

Další informace o poskytovatelů konfiguračních služeb systému Windows 10, najdete v článku [referencích poskytovatelů konfiguračních služeb](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).

## <a name="graph-api-properties-to-csp-mapping"></a>Vlastnosti rozhraní Graph API CSP mapování

V následujícím seznamu jsou uvedeny vlastnosti rozhraní Graph API používá Microsoft Intune pro konfiguraci zařízení Windows 10. Profil také ukazuje odpovídající CSP Windows 10 a posun identifikátoru URI.

#### <a name="editionupgradeconfigurationlicense"></a>EditionUpgradeConfiguration.License 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsLicensing  
**Posun identifikátoru URI**: /UpgradeEditionWithLicense

#### <a name="editionupgradeconfigurationlicensetype"></a>EditionUpgradeConfiguration.LicenseType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsLicensing  
**Posun identifikátoru URI**: /LicenseKeyType

#### <a name="editionupgradeconfigurationproductkey"></a>EditionUpgradeConfiguration.ProductKey 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsLicensing  
**Posun identifikátoru URI**: /UpgradeEditionWithProductKey

#### <a name="editionupgradeconfigurationwindowssmode"></a>EditionUpgradeConfiguration.WindowsSMode 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsLicensing  
**Posun identifikátoru URI**: / SMode/SwitchingPolicy

#### <a name="sharedpcconfigurationaccountmanagerpolicy"></a>SharedPCConfiguration.AccountManagerPolicy 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Offset URI**: /DeletionPolicy, /DiskLevelCaching, /InactiveThreshold, /DiskLevelDeletion

#### <a name="sharedpcconfigurationaccountmanagerpolicy-windows-holographic-for-business-edition-targeted-devices"></a>SharedPCConfiguration.AccountManagerPolicy (Windows Holographic for Business edition cílové zařízení) 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/AccountManagement  
**Offset URI**: /DeletionPolicy, /StorageCapacityStartDeletion, /StorageCapacityStopDeletion, /ProfileInactivityThreshold

#### <a name="sharedpcconfigurationallowedaccounts"></a>SharedPCConfiguration.AllowedAccounts 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Offset URI**: /AccountModel

#### <a name="sharedpcconfigurationallowlocalstorage"></a>SharedPCConfiguration.AllowLocalStorage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /RestrictLocalStorage

#### <a name="sharedpcconfigurationdisableaccountmanager"></a>SharedPCConfiguration.DisableAccountManager 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /EnableAccountManager

#### <a name="sharedpcconfigurationdisableedupolicies"></a>SharedPCConfiguration.DisableEduPolicies 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /SetEduPolicies

#### <a name="sharedpcconfigurationdisablepowerpolicies"></a>SharedPCConfiguration.DisablePowerPolicies 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /SetPowerPolicies

#### <a name="sharedpcconfigurationdisablesigninonresume"></a>SharedPCConfiguration.DisableSignInOnResume 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /SignInOnResume

#### <a name="sharedpcconfigurationenabled"></a>SharedPCConfiguration.Enabled 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /EnableSharedPCMode

#### <a name="sharedpcconfigurationidletimebeforesleepinseconds"></a>SharedPCConfiguration.IdleTimeBeforeSleepInSeconds 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /InactiveThreshold

#### <a name="sharedpcconfigurationkioskappdisplayname"></a>SharedPCConfiguration.KioskAppDisplayName 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Offset URI**: /KioskModeUserTileDisplayText

#### <a name="sharedpcconfigurationkioskappusermodelid"></a>SharedPCConfiguration.KioskAppUserModelId 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /KioskModeAUMID

#### <a name="sharedpcconfigurationlocalstorage"></a>SharedPCConfiguration.LocalStorage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /RestrictLocalStorage

#### <a name="sharedpcconfigurationmaintenancestarttime"></a>SharedPCConfiguration.MaintenanceStartTime 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /MaintenanceStartTime

#### <a name="sharedpcconfigurationsetaccountmanager"></a>SharedPCConfiguration.SetAccountManager
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /EnableAccountManager

#### <a name="sharedpcconfigurationsetedupolicies"></a>SharedPCConfiguration.SetEduPolicies 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /SetEduPolicies

#### <a name="sharedpcconfigurationsetpowerpolicies"></a>SharedPCConfiguration.SetPowerPolicies 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /SetPowerPolicies

#### <a name="sharedpcconfigurationsigninonresume"></a>SharedPCConfiguration.SignInOnResume 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SharedPC  
**Posun identifikátoru URI**: /SignInOnResume

#### <a name="windows10endpointconfigurationsmartscreenblockoverrideforfiles"></a>Windows10endpointconfiguration.smartScreenBlockOverrideForFiles 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/SmartScreen/PreventOverrideForFilesInShell

#### <a name="windows10endpointprotectionconfigurationapplicationguardallowfilesaveonhost"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowFileSaveOnHost 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Posun identifikátoru URI**: / Settings/SaveFilesToHost

#### <a name="windows10endpointprotectionconfigurationapplicationguardallowpersistence"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowPersistence 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Posun identifikátoru URI**: / Settings/AllowPersistence

#### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttolocalprinters"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowPrintToLocalPrinters 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Posun identifikátoru URI**: / Settings/PrintingSettings

#### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttonetworkprinters"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowPrintToNetworkPrinters 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Posun identifikátoru URI**: / Settings/PrintingSettings

#### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttopdf"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowPrintToPDF 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Posun identifikátoru URI**: / Settings/PrintingSettings

#### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttoxps"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowPrintToXPS 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Posun identifikátoru URI**: / Settings/PrintingSettings

#### <a name="windows10endpointprotectionconfigurationapplicationguardallowvirtualgpu"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowVirtualGPU 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Posun identifikátoru URI**: / Settings/AllowVirtualGPU

#### <a name="windows10endpointprotectionconfigurationapplicationguardblockclipboardsharing"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardBlockClipboardSharing 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Posun identifikátoru URI**: / Settings/ClipboardSettings

#### <a name="windows10endpointprotectionconfigurationapplicationguardblockfiletransfer"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardBlockFileTransfer 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Posun identifikátoru URI**: / Settings/ClipboardFileType

#### <a name="windows10endpointprotectionconfigurationapplicationguardblocknonenterprisecontent"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardBlockNonEnterpriseContent 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Posun identifikátoru URI**: / Settings/BlockNonEnterpriseContent

#### <a name="windows10endpointprotectionconfigurationapplicationguardenabled"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardEnabled 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Posun identifikátoru URI**: / Settings/AllowWindowsDefenderApplicationGuard

#### <a name="windows10endpointprotectionconfigurationapplicationguardforceauditing"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardForceAuditing 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Posun identifikátoru URI**: / auditu/AuditApplicationGuard

#### <a name="windows10endpointprotectionconfigurationbitlockerallowstandarduserencryption"></a>Windows10EndpointProtectionConfiguration.BitLockerAllowStandardUserEncryption 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/BitLocker  
**Posun identifikátoru URI**: /AllowStandardUserEncryption

#### <a name="windows10endpointprotectionconfigurationbitlockerdisablewarningforotherdiskencryption"></a>Windows10EndpointProtectionConfiguration.BitLockerDisableWarningForOtherDiskEncryption 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/BitLocker  
**Offset URI**: /AllowWarningForOtherDiskEncryption

#### <a name="windows10endpointprotectionconfigurationbitlockerenablestoragecardencryptiononmobile"></a>Windows10EndpointProtectionConfiguration.BitLockerEnableStorageCardEncryptionOnMobile 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/BitLocker  
**Posun identifikátoru URI**: /RequireStorageCardEncryption

#### <a name="windows10endpointprotectionconfigurationbitlockerencryptdevice"></a>Windows10EndpointProtectionConfiguration.BitLockerEncryptDevice 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/BitLocker  
**Posun identifikátoru URI**: /RequireDeviceEncryption

#### <a name="windows10endpointprotectionconfigurationbitlockerfixeddrivepolicy"></a>Windows10EndpointProtectionConfiguration.BitLockerFixedDrivePolicy 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/BitLocker  
**Posun identifikátoru URI**: /EncryptionMethodByDriveType, /FixedDrivesRequireEncryption, /FixedDrivesRecoveryOptions

#### <a name="windows10endpointprotectionconfigurationbitlockerremovabledrivepolicy"></a>Windows10EndpointProtectionConfiguration.BitLockerRemovableDrivePolicy 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/BitLocker  
**Posun identifikátoru URI**: /EncryptionMethodByDriveType, /RemovableDrivesRequireEncryption

#### <a name="windows10endpointprotectionconfigurationbitlockersystemdrivepolicy"></a>Windows10EndpointProtectionConfiguration.BitLockerSystemDrivePolicy 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/BitLocker  
**Posun identifikátoru URI**: /EncryptionMethodByDriveType /SystemDrivesRequireStartupAuthentication, /SystemDrivesMinimumPINLength, /SystemDrivesRecoveryMessage, /SystemDrivesRecoveryOptions

#### <a name="windows10endpointprotectionconfigurationclientconnectionencryptionlevel"></a>windows10endpointprotectionconfiguration.clientConnectionEncryptionLevel 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteDesktopServices/ClientConnectionEncryptionLevel

#### <a name="windows10endpointprotectionconfigurationconfiguresmbv1clientdriver"></a>windows10endpointprotectionconfiguration.configureSMBV1ClientDriver 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/MSSecurityGuide/ConfigureSMBV1ClientDriver

#### <a name="windows10endpointprotectionconfigurationconnectivitydownloadingofprintdriversoverhttp"></a>Windows10EndpointProtectionConfiguration.ConnectivityDownloadingOfPrintDriversOverHttp 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Connectivity/DisableDownloadingOfPrintDriversOverHTTP

#### <a name="windows10endpointprotectionconfigurationconnectivityhardeneduncpaths"></a>Windows10EndpointProtectionConfiguration.ConnectivityHardenedUncPaths 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Connectivity/HardenedUNCPaths

#### <a name="windows10endpointprotectionconfigurationconnectivityinternetdownloadforwebpublishingandonlineorderingwizards"></a>Windows10EndpointProtectionConfiguration.ConnectivityInternetDownloadForWebPublishingAndOnlineOrderingWizards 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Connectivity/DisableInternetDownloadForWebPublishingAndOnlineOrderingWizards

#### <a name="windows10endpointprotectionconfigurationconnectivityprintingoverhttp"></a>Windows10EndpointProtectionConfiguration.ConnectivityPrintingOverHttp 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Connectivity/DiablePrintingOverHTTP

#### <a name="windows10endpointprotectionconfigurationcredentialsuienumerateadministrators"></a>Windows10EndpointProtectionConfiguration.CredentialsUIEnumerateAdministrators 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/CredentialsUI/EnumerateAdministrators

#### <a name="windows10endpointprotectionconfigurationdefenderadditionalguardedfolders"></a>Windows10EndpointProtectionConfiguration.DefenderAdditionalGuardedFolders 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy/  
**Offset URI**: /Config/Defender/ControlledFolderAccessProtectedFolders

#### <a name="windows10endpointprotectionconfigurationdefenderadvancedransomewareprotectiontype"></a>Windows10EndpointProtectionConfiguration.DefenderAdvancedRansomewareProtectionType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules

#### <a name="windows10endpointprotectionconfigurationdefenderattacksurfacereductionexcludedpaths"></a>Windows10EndpointProtectionConfiguration.DefenderAttackSurfaceReductionExcludedPaths 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionOnlyExclusions

#### <a name="windows10endpointprotectionconfigurationdefenderemailcontentexecution"></a>Windows10EndpointProtectionConfiguration.DefenderEmailContentExecution 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowEmailScanning

#### <a name="windows10endpointprotectionconfigurationdefenderemailcontentexecutiontype"></a>Windows10EndpointProtectionConfiguration.DefenderEmailContentExecutionType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules (CSP/konfigurace vyžaduje vlastnosti grafu: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection / Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection / Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType , windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection / Configuration.defenderUntrustedUSBProcessType

#### <a name="windows10endpointprotectionconfigurationdefenderexploitprotectionxml"></a>Windows10EndpointProtectionConfiguration.DefenderExploitProtectionXml 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy/ **posun identifikátoru URI**: /Config/ExploitGuard/ExploitProtectionSettings

#### <a name="windows10endpointprotectionconfigurationdefenderexploitprotectionxmlfilename"></a>Windows10EndpointProtectionConfiguration.DefenderExploitProtectionXmlFileName 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ExploitGuard/ExploitProtectionSettings

#### <a name="windows10endpointprotectionconfigurationdefenderguardedfoldersallowedapppaths"></a>Windows10EndpointProtectionConfiguration.DefenderGuardedFoldersAllowedAppPaths 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy/  
**Posun identifikátoru URI**: /Config/Defender/ControlledFolderAccessAllowedApplications

#### <a name="windows10endpointprotectionconfigurationdefenderguardmyfolderstype"></a>Windows10EndpointProtectionConfiguration.DefenderGuardMyFoldersType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/EnableControlledFolderAccess

#### <a name="windows10endpointprotectionconfigurationdefendernetworkprotectiontype"></a>Windows10EndpointProtectionConfiguration.DefenderNetworkProtectionType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy/  
**Posun identifikátoru URI**: /Config/Defender/EnableNetworkProtection

#### <a name="windows10endpointprotectionconfigurationdefenderofficeappsexecutablecontentcreationorlaunch"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsExecutableContentCreationOrLaunch 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules

#### <a name="windows10endpointprotectionconfigurationdefenderofficeappsexecutablecontentcreationorlaunchtype"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsExecutableContentCreationOrLaunchType
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules (CSP/konfigurace vyžaduje vlastnosti grafu: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection / Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection / Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType , windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection / Configuration.defenderUntrustedUSBProcessType

#### <a name="windows10endpointprotectionconfigurationdefenderofficeappslaunchchildprocess"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsLaunchChildProcess 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules

#### <a name="windows10endpointprotectionconfigurationdefenderofficeappslaunchchildprocesstype"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsLaunchChildProcessType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules (CSP/konfigurace vyžaduje vlastnosti grafu: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection / Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection / Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType , windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection / Configuration.defenderUntrustedUSBProcessType

#### <a name="windows10endpointprotectionconfigurationdefenderofficeappsotherprocessinjection"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsOtherProcessInjection 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules

#### <a name="windows10endpointprotectionconfigurationdefenderofficeappsotherprocessinjectiontype"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsOtherProcessInjectionType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules (CSP/konfigurace vyžaduje vlastnosti grafu: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection / Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection / Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType , windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection / Configuration.defenderUntrustedUSBProcessType 

#### <a name="windows10endpointprotectionconfigurationdefenderofficemacrocodeallowwin32imports"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeMacroCodeAllowWin32Imports 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules

#### <a name="windows10endpointprotectionconfigurationdefenderofficemacrocodeallowwin32importstype"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeMacroCodeAllowWin32ImportsType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules (CSP/konfigurace vyžaduje vlastnosti grafu: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection / Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection / Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType , windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection / Configuration.defenderUntrustedUSBProcessType

#### <a name="windows10endpointprotectionconfigurationdefenderpreventcredentialstealingtype"></a>Windows10EndpointProtectionConfiguration.DefenderPreventCredentialStealingType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules (CSP/konfigurace vyžaduje vlastnosti grafu: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection / Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection / Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType , windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection / Configuration.defenderUntrustedUSBProcessType

#### <a name="windows10endpointprotectionconfigurationdefenderprocesscreation"></a>Windows10EndpointProtectionConfiguration.DefenderProcessCreation 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules

#### <a name="windows10endpointprotectionconfigurationdefenderprocesscreationtype"></a>Windows10EndpointProtectionConfiguration.DefenderProcessCreationType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules

#### <a name="windows10endpointprotectionconfigurationdefenderprotectagainstpotentiallyunwantedapplications"></a>Windows10EndpointProtectionConfiguration.DefenderProtectAgainstPotentiallyUnwantedApplications 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/MSSecurityGuide/TurnOnWindowsDefenderProtectionAgainstPotentiallyUnwantedApplications

#### <a name="windows10endpointprotectionconfigurationdefenderscriptdownloadedpayloadexecution"></a>Windows10EndpointProtectionConfiguration.DefenderScriptDownloadedPayloadExecution 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules

#### <a name="windows10endpointprotectionconfigurationdefenderscriptdownloadedpayloadexecutiontype"></a>Windows10EndpointProtectionConfiguration.DefenderScriptDownloadedPayloadExecutionType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules (CSP/konfigurace vyžaduje vlastnosti grafu: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection / Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection / Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType , windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection / Configuration.defenderUntrustedUSBProcessType

#### <a name="windows10endpointprotectionconfigurationdefenderscriptobfuscatedmacrocode"></a>Windows10EndpointProtectionConfiguration.DefenderScriptObfuscatedMacroCode 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules

#### <a name="windows10endpointprotectionconfigurationdefenderscriptobfuscatedmacrocodetype"></a>Windows10EndpointProtectionConfiguration.DefenderScriptObfuscatedMacroCodeType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules (CSP/konfigurace vyžaduje vlastnosti grafu: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection / Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection / Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType , windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection / Configuration.defenderUntrustedUSBProcessType

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterblockexploitprotectionoverride"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterBlockExploitProtectionOverride 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy/  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/DisallowExploitProtectionOverride

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisableaccountui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableAccountUI 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/DisableAccountProtectionUI

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisableappbrowserui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableAppBrowserUI 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/DisableAppBrowserUI

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablefamilyui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableFamilyUI 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/DisableFamilyUI

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablehealthui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableHealthUI 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/DisableHealthUI

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablenetworkui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableNetworkUI 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/DisableNetworkUI

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablesecurebootui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableSecureBootUI 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/HideSecureBoot

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisabletroubleshootingui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableTroubleshootingUI 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/HideTPMTroubleshooting

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablevirusui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableVirusUI 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/DisableVirusUI

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterhelpemail"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterHelpEmail 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/Email

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterhelpphone"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterHelpPhone 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/Phone

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterhelpurl"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterHelpURL 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/URL

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenteritcontactdisplay"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterITContactDisplay 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: EnableCustomizedToasts/WindowsDefenderSecurityCenter /, / WindowsDefenderSecurityCenter/EnableInAppCustomization

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenternotificationsfromapp"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterNotificationsFromApp 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/HideWindowsSecurityNotificationAreaControl

#### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterorganizationdisplayname"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterOrganizationDisplayName 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsDefenderSecurityCenter/CompanyName

#### <a name="windows10endpointprotectionconfigurationdefenderuntrustedexecutable"></a>Windows10EndpointProtectionConfiguration.DefenderUntrustedExecutable 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules

#### <a name="windows10endpointprotectionconfigurationdefenderuntrustedexecutabletype"></a>Windows10EndpointProtectionConfiguration.DefenderUntrustedExecutableType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules

#### <a name="windows10endpointprotectionconfigurationdefenderuntrustedusbprocess"></a>Windows10EndpointProtectionConfiguration.DefenderUntrustedUSBProcess 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules

#### <a name="windows10endpointprotectionconfigurationdefenderuntrustedusbprocesstype"></a>Windows10EndpointProtectionConfiguration.DefenderUntrustedUSBProcessType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AttackSurfaceReductionRules (CSP/konfigurace vyžaduje vlastnosti grafu: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection / Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection / Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType , windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection / Configuration.defenderUntrustedUSBProcessType

#### <a name="windows10endpointprotectionconfigurationdeviceguardenablesecurebootwithdma"></a>Windows10EndpointProtectionConfiguration.DeviceGuardEnableSecureBootWithDMA 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy/  
**Posun identifikátoru URI**: /Config/DeviceGuard/RequirePlatformSecurityFeatures

#### <a name="windows10endpointprotectionconfigurationdeviceguardenablevirtualizationbasedsecurity"></a>Windows10EndpointProtectionConfiguration.DeviceGuardEnableVirtualizationBasedSecurity 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy/  
**Posun identifikátoru URI**: /Config/DeviceGuard/EnableVirtualizationBasedSecurity

#### <a name="windows10endpointprotectionconfigurationdeviceguardlaunchsystemguard"></a>Windows10EndpointProtectionConfiguration.DeviceGuardLaunchSystemGuard 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy/  
**Posun identifikátoru URI**: /Config/DeviceGuard/ConfigureSystemGuardLaunch

#### <a name="windows10endpointprotectionconfigurationdeviceguardlocalsystemauthoritycredentialguardsettings"></a>Windows10EndpointProtectionConfiguration.DeviceGuardLocalSystemAuthorityCredentialGuardSettings 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy/  
**Offset URI**: /Config/DeviceGuard/LsaCfgFlags

#### <a name="windows10endpointprotectionconfigurationdmaguarddeviceenumerationpolicy"></a>Windows10EndpointProtectionConfiguration.DmaGuardDeviceEnumerationPolicy 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DmaGuard/DeviceEnumerationPolicy

#### <a name="windows10endpointprotectionconfigurationeventlogserviceapplicationlogmaximumfilesizeinkb"></a>Windows10EndpointProtectionConfiguration.EventLogServiceApplicationLogMaximumFileSizeInKb 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/EventLogService/SpecifyMaximumFileSizeApplicationLog

#### <a name="windows10endpointprotectionconfigurationeventlogservicesecuritylogmaximumfilesizeinkb"></a>Windows10EndpointProtectionConfiguration.EventLogServiceSecurityLogMaximumFileSizeInKb 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/EventLogService/SpecifyMaximumFileSizeSecurityLog

#### <a name="windows10endpointprotectionconfigurationeventlogservicesystemlogmaximumfilesizeinkb"></a>Windows10EndpointProtectionConfiguration.EventLogServiceSystemLogMaximumFileSizeInKb 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/EventLogService/SpecifyMaximumFileSizeSystemLog

#### <a name="windows10endpointprotectionconfigurationexplorerdataexecutionprevention"></a>Windows10EndpointProtectionConfiguration.ExplorerDataExecutionPrevention 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/FileExplorer/TurnOffDataExecutionPreventionForExplorer

#### <a name="windows10endpointprotectionconfigurationexplorerheapterminationoncorruption"></a>Windows10EndpointProtectionConfiguration.ExplorerHeapTerminationOnCorruption 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/FileExplorer/TurnOffHeapTerminationOnCorruption

#### <a name="windows10endpointprotectionconfigurationfirewallblockstatefulftp"></a>Windows10EndpointProtectionConfiguration.FirewallBlockStatefulFTP 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/Global/DisableStatefulFtp

#### <a name="windows10endpointprotectionconfigurationfirewallcertificaterevocationlistcheckmethod"></a>Windows10EndpointProtectionConfiguration.FirewallCertificateRevocationListCheckMethod 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Firewall  
**Offset URI**: /MdmStore/Global/CRLcheck

#### <a name="windows10endpointprotectionconfigurationfirewallidletimeoutforsecurityassociationinseconds"></a>Windows10EndpointProtectionConfiguration.FirewallIdleTimeoutForSecurityAssociationInSeconds 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/Global/SaIdleTime

#### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowdhcp"></a>Windows10EndpointProtectionConfiguration.FirewallIPSecExemptionsAllowDHCP 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/Global/IPsecExempt

#### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowicmp"></a>Windows10EndpointProtectionConfiguration.FirewallIPSecExemptionsAllowICMP 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/Global/IPsecExempt

#### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowneighbordiscovery"></a>Windows10EndpointProtectionConfiguration.FirewallIPSecExemptionsAllowNeighborDiscovery 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/Global/IPsecExempt

#### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowrouterdiscovery"></a>Windows10EndpointProtectionConfiguration.FirewallIPSecExemptionsAllowRouterDiscovery 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/Global/IPsecExempt

#### <a name="windows10endpointprotectionconfigurationfirewallmergekeyingmodulesettings"></a>Windows10EndpointProtectionConfiguration.FirewallMergeKeyingModuleSettings 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/Global/OpportunisticallyMatchAuthSetPerKM

#### <a name="windows10endpointprotectionconfigurationfirewallpacketqueueingmethod"></a>Windows10EndpointProtectionConfiguration.FirewallPacketQueueingMethod 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/Global/EnablePacketQueue

#### <a name="windows10endpointprotectionconfigurationfirewallpresharedkeyencodingmethod"></a>Windows10EndpointProtectionConfiguration.FirewallPreSharedKeyEncodingMethod 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/Global/PresharedKeyEncoding

#### <a name="windows10endpointprotectionconfigurationfirewallprofiledomain"></a>Windows10EndpointProtectionConfiguration.FirewallProfileDomain 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /EnableFirewall, /DisableStealthMode, / chráněné, /DisableUnicastResponsesToMulticastBroadcast /DisableInboundNotifications, /AuthAppsAllowUserPrefMerge, /GlobalPortsAllowUserPrefMerge, /AllowLocalPolicyMerge , /DefaultOutboundAction /DefaultInboundAction, /DisableStealthModeIpsecSecuredPacketExemption, /AllowLocalIpsecPolicyMerge

#### <a name="windows10endpointprotectionconfigurationfirewallprofiledomaininboundconnectionsblocked"></a>windows10endpointprotectionconfiguration.firewallProfileDomain.inboundConnectionsBlocked 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/DomainProfile/DefaultInboundAction

#### <a name="windows10endpointprotectionconfigurationfirewallprofiledomaininboundnotificationsblocked"></a>windows10endpointprotectionconfiguration.firewallProfileDomain.inboundNotificationsBlocked 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/DomainProfile/DisableInboundNotifications

#### <a name="windows10endpointprotectionconfigurationfirewallprofiledomaininboundnotificationsblocked"></a>windows10endpointprotectionconfiguration.firewallProfileDomain.inboundNotificationsBlocked 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/DomainProfile/EnableFirewall

#### <a name="windows10endpointprotectionconfigurationfirewallprofiledomainoutboundconnectionsblocked"></a>windows10endpointprotectionconfiguration.firewallProfileDomain.outboundConnectionsBlocked 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/DomainProfile/DefaultOutboundAction

#### <a name="windows10endpointprotectionconfigurationfirewallprofileprivate"></a>Windows10EndpointProtectionConfiguration.FirewallProfilePrivate 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /EnableFirewall, /DisableStealthMode, / chráněné, /DisableUnicastResponsesToMulticastBroadcast /DisableInboundNotifications, /AuthAppsAllowUserPrefMerge, /GlobalPortsAllowUserPrefMerge, /AllowLocalPolicyMerge , /DefaultOutboundAction /DefaultInboundAction, /DisableStealthModeIpsecSecuredPacketExemption, /AllowLocalIpsecPolicyMerge

#### <a name="windows10endpointprotectionconfigurationfirewallprofileprivatefirewallenabled"></a>windows10endpointprotectionconfiguration.firewallProfilePrivate.firewallEnabled 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/PrivateProfile/EnableFirewall

#### <a name="windows10endpointprotectionconfigurationfirewallprofileprivateinboundconnectionsblocked"></a>windows10endpointprotectionconfiguration.firewallProfilePrivate.inboundConnectionsBlocked 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/PrivateProfile/DefaultInboundAction

#### <a name="windows10endpointprotectionconfigurationfirewallprofileprivateinboundnotificationsblocked"></a>windows10endpointprotectionconfiguration.firewallProfilePrivate.inboundNotificationsBlocked 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/PrivateProfile/DisableInboundNotifications

#### <a name="windows10endpointprotectionconfigurationfirewallprofileprivateoutboundconnectionsblocked"></a>windows10endpointprotectionconfiguration.firewallProfilePrivate.outboundConnectionsBlocked 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/PrivateProfile/DefaultOutboundAction

#### <a name="windows10endpointprotectionconfigurationfirewallprofilepublic"></a>Windows10EndpointProtectionConfiguration.FirewallProfilePublic 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /EnableFirewall, /DisableStealthMode, / chráněné, /DisableUnicastResponsesToMulticastBroadcast /DisableInboundNotifications, /AuthAppsAllowUserPrefMerge, /GlobalPortsAllowUserPrefMerge, /AllowLocalPolicyMerge , /DefaultOutboundAction /DefaultInboundAction, /DisableStealthModeIpsecSecuredPacketExemption, /AllowLocalIpsecPolicyMerge

#### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicconnectionsecurityrulesfromgrouppolicymerged"></a>windows10endpointprotectionconfiguration.firewallProfilePublic.connectionSecurityRulesFromGroupPolicyMerged 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Offset URI**: /MdmStore/PublicProfile/AllowLocalIpsecPolicyMerge

#### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicfirewallenabled"></a>windows10endpointprotectionconfiguration.firewallProfilePublic.firewallEnabled 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/PublicProfile/EnableFirewall

#### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicinboundconnectionsblocked"></a>windows10endpointprotectionconfiguration.firewallProfilePublic.inboundConnectionsBlocked 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/PublicProfile/DefaultInboundAction

#### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicinboundnotificationsblocked"></a>windows10endpointprotectionconfiguration.firewallProfilePublic.inboundNotificationsBlocked 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/PublicProfile/DisableInboundNotifications

#### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicoutboundconnectionsblocked"></a>windows10endpointprotectionconfiguration.firewallProfilePublic.outboundConnectionsBlocked 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Posun identifikátoru URI**: /MdmStore/PublicProfile/DefaultOutboundAction

#### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicpolicyrulesfromgrouppolicymerged"></a>windows10endpointprotectionconfiguration.firewallProfilePublic.policyRulesFromGroupPolicyMerged 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Firewall  
**Offset URI**: /MdmStore/PublicProfile/AllowLocalPolicyMerge

#### <a name="windows10endpointprotectionconfigurationlanmanagerauthenticationlevel"></a>Windows10EndpointProtectionConfiguration.LanManagerAuthenticationLevel 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/NetworkSecurity\_LANManagerAuthenticationLevel

#### <a name="windows10endpointprotectionconfigurationlanmanagerworkstationdisableinsecureguestlogons"></a>Windows10EndpointProtectionConfiguration.LanManagerWorkstationDisableInsecureGuestLogons 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/LanmanWorkstation/EnableInsecureGuestLogons

#### <a name="windows10endpointprotectionconfigurationlanmanagerworkstationenableinsecureguestlogons"></a>Windows10EndpointProtectionConfiguration.LanManagerWorkstationEnableInsecureGuestLogons 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/LanmanWorkstation/EnableInsecureGuestLogons

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsadministratoraccountname"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAdministratorAccountName 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/LocalPoliciesSecurityOptions/Accounts\_RenameAdministratorAccount

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsadministratorelevationpromptbehavior"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAdministratorElevationPromptBehavior
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_BehaviorOfTheElevationPromptForAdministrators

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowanonymousenumerationofsamaccountsandshares"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowAnonymousEnumerationOfSAMAccountsAndShares 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/NetworkAccess\_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowpku2uauthenticationrequests"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowPKU2UAuthenticationRequests 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/NetworkSecurity\_AllowPKU2UAuthenticationRequests

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowremotecallstosecurityaccountsmanager"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowRemoteCallsToSecurityAccountsManager 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/NetworkAccess\_RestrictClientsAllowedToMakeRemoteCallsToSAM

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowremotecallstosecurityaccountsmanagerhelperbool"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowRemoteCallsToSecurityAccountsManagerHelperBool 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/NetworkAccess\_RestrictClientsAllowedToMakeRemoteCallsToSAM

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowsystemtobeshutdownwithouthavingtologon"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowSystemToBeShutDownWithoutHavingToLogOn 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/Shutdown\_AllowSystemToBeShutDownWithoutHavingToLogOn

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowuiaccessapplicationelevation"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowUIAccessApplicationElevation 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_AllowUIAccessApplicationsToPromptForElevation

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowuiaccessapplicationsforsecurelocations"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowUIAccessApplicationsForSecureLocations 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowundockwithouthavingtologon"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowUndockWithoutHavingToLogon 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/Devices\_AllowUndockWithoutHavingToLogon

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockmicrosoftaccounts"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsBlockMicrosoftAccounts 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/Accounts\_BlockMicrosoftAccounts

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockremotelogonwithblankpassword"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsBlockRemoteLogonWithBlankPassword 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/Accounts\_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockremoteopticaldriveaccess"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsBlockRemoteOpticalDriveAccess 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/LocalPoliciesSecurityOptions/Devices\_RestrictCDROMAccessToLocallyLoggedOnUserOnly

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockusersinstallingprinterdrivers"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsBlockUsersInstallingPrinterDrivers 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/Devices\_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsclearvirtualmemorypagefile"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsClearVirtualMemoryPageFile 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/Shutdown\_ClearVirtualMemoryPageFile

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsclientdigitallysigncommunicationsalways"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsClientDigitallySignCommunicationsAlways 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/LocalPoliciesSecurityOptions/MicrosoftNetworkClient\_DigitallySignCommunicationsAlways

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsclientsendunencryptedpasswordtothirdpartysmbservers"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsClientSendUnencryptedPasswordToThirdPartySMBServers 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/MicrosoftNetworkClient\_SendUnencryptedPasswordToThirdPartySMBServers

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdetectapplicationinstallationsandpromptforelevation"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDetectApplicationInstallationsAndPromptForElevation 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_DetectApplicationInstallationsAndPromptForElevation

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableadministratoraccount"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDisableAdministratorAccount 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/Accounts\_EnableAdministratorAccountStatus

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableclientdigitallysigncommunicationsifserveragrees"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDisableClientDigitallySignCommunicationsIfServerAgrees 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/MicrosoftNetworkClient\_DigitallySignCommunicationsIfServerAgrees

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableguestaccount"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDisableGuestAccount 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/Accounts\_EnableGuestAccountStatus

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableserverdigitallysigncommunicationsalways"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDisableServerDigitallySignCommunicationsAlways 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/LocalPoliciesSecurityOptions/MicrosoftNetworkServer\_DigitallySignCommunicationsAlways

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableserverdigitallysigncommunicationsifclientagrees"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDisableServerDigitallySignCommunicationsIfClientAgrees 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/MicrosoftNetworkServer\_DigitallySignCommunicationsIfClientAgrees

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdonotallowanonymousenumerationofsamaccounts"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDoNotAllowAnonymousEnumerationOfSAMAccounts 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/NetworkAccess\_DoNotAllowAnonymousEnumerationOfSAMAccounts

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdonotrequirectrlaltdel"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDoNotRequireCtrlAltDel 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_DoNotRequireCTRLALTDEL

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdonotstorelanmanagerhashvalueonnextpasswordchange"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDoNotStoreLANManagerHashValueOnNextPasswordChange 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/NetworkSecurity\_DoNotStoreLANManagerHashValueOnNextPasswordChange

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsenableadministratoraccount"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsEnableAdministratorAccount 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/Accounts\_EnableAdministratorAccountStatus

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsenableguestaccount"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsEnableGuestAccount 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/Accounts\_EnableGuestAccountStatus

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsformatandejectofremovablemediaalloweduser"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsFormatAndEjectOfRemovableMediaAllowedUser 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/Devices\_AllowedToFormatAndEjectRemovableMedia

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsguestaccountname"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsGuestAccountName 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/LocalPoliciesSecurityOptions/Accounts\_RenameGuestAccount

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionshidelastsignedinuser"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsHideLastSignedInUser 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_DoNotDisplayLastSignedIn

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionshideusernameatsignin"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsHideUsernameAtSignIn 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_DoNotDisplayUsernameAtSignIn

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsinformationdisplayedonlockscreen"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsInformationDisplayedOnLockScreen 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_DisplayUserInformationWhenTheSessionIsLocked

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsinformationshownonlockscreen"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsInformationShownOnLockScreen 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_DisplayUserInformationWhenTheSessionIsLocked

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionslogonmessagetext"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsLogOnMessageText 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_MessageTextForUsersAttemptingToLogOn

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionslogonmessagetitle"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsLogOnMessageTitle 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_MessageTitleForUsersAttemptingToLogOn

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsmachineinactivitylimit"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsMachineInactivityLimit 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_MachineInactivityLimit

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsmachineinactivitylimitinminutes"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsMachineInactivityLimitInMinutes 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_MachineInactivityLimit

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsminimumsessionsecurityforntlmsspbasedclients"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsMinimumSessionSecurityForNtlmSspBasedClients 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/NetworkSecurity\_MinimumSessionSecurityForNTLMSSPBasedClients

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsminimumsessionsecurityforntlmsspbasedservers"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsMinimumSessionSecurityForNtlmSspBasedServers 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/NetworkSecurity\_MinimumSessionSecurityForNTLMSSPBasedServers

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsonlyelevatesignedexecutables"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsOnlyElevateSignedExecutables 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_OnlyElevateExecutableFilesThatAreSignedAndValidated

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsrestrictanonymousaccesstonamedpipesandshares"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsRestrictAnonymousAccessToNamedPipesAndShares 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/NetworkAccess\_RestrictAnonymousAccessToNamedPipesAndShares

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionssmartcardremovalbehavior"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsSmartCardRemovalBehavior 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_SmartCardRemovalBehavior

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsstandarduserelevationpromptbehavior"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsStandardUserElevationPromptBehavior 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_BehaviorOfTheElevationPromptForStandardUsers

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsswitchtosecuredesktopwhenpromptingforelevation"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsSwitchToSecureDesktopWhenPromptingForElevation 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_SwitchToTheSecureDesktopWhenPromptingForElevation

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsuseadminapprovalmode"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsUseAdminApprovalMode 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_UseAdminApprovalMode

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsuseadminapprovalmodeforadministrators"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsUseAdminApprovalModeForAdministrators 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_RunAllAdministratorsInAdminApprovalMode

#### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsvirtualizefileandregistrywritefailurestoperuserlocations"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsVirtualizeFileAndRegistryWriteFailuresToPerUserLocations 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations

#### <a name="windows10endpointprotectionconfigurationnetworkicmpredirectsoverrideospfgeneratedroutes"></a>Windows10EndpointProtectionConfiguration.NetworkIcmpRedirectsOverrideOspfGeneratedRoutes 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/MSSLegacy/AllowICMPRedirectsToOverrideOSPFGeneratedRoutes

#### <a name="windows10endpointprotectionconfigurationnetworkignorenetbiosnamereleaserequestsexceptfromwinsservers"></a>Windows10EndpointProtectionConfiguration.NetworkIgnoreNetBiosNameReleaseRequestsExceptFromWinsServers 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/MSSLegacy/AllowTheComputerToIgnoreNetBIOSNameReleaseRequestsExceptFromWINSServers

#### <a name="windows10endpointprotectionconfigurationnetworkipsourceroutingprotectionlevel"></a>Windows10EndpointProtectionConfiguration.NetworkIpSourceRoutingProtectionLevel 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/MSSLegacy/IPSourceRoutingProtectionLevel

#### <a name="windows10endpointprotectionconfigurationnetworkipv6sourceroutingprotectionlevel"></a>Windows10EndpointProtectionConfiguration.NetworkIpV6SourceRoutingProtectionLevel 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/MSSLegacy/IPv6SourceRoutingProtectionLevel

#### <a name="windows10endpointprotectionconfigurationpasswordpinlogon"></a>Windows10EndpointProtectionConfiguration.PasswordPinLogOn 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/CredentialProviders/AllowPINLogon

#### <a name="windows10endpointprotectionconfigurationpowershellshellscriptblocklogging"></a>Windows10EndpointProtectionConfiguration.PowerShellShellScriptBlockLogging 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsPowerShell/TurnOnPowerShellScriptBlockLogging

#### <a name="windows10endpointprotectionconfigurationremoteassistancesolicitedsetting"></a>Windows10EndpointProtectionConfiguration.RemoteAssistanceSolicitedSetting 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Connectivity/HardenedUNCPaths

#### <a name="windows10endpointprotectionconfigurationremotedesktopservicesclientconnectionencryptionlevel"></a>Windows10EndpointProtectionConfiguration.RemoteDesktopServicesClientConnectionEncryptionLevel 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteDesktopServices/ClientConnectionEncryptionLevel

#### <a name="windows10endpointprotectionconfigurationremotedesktopservicesdriveredirection"></a>Windows10EndpointProtectionConfiguration.RemoteDesktopServicesDriveRedirection 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteDesktopServices/DoNotAllowDriveRedirection

#### <a name="windows10endpointprotectionconfigurationremotedesktopservicespasswordsaving"></a>Windows10EndpointProtectionConfiguration.RemoteDesktopServicesPasswordSaving 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteDesktopServices/DoNotAllowPasswordSaving

#### <a name="windows10endpointprotectionconfigurationremotedesktopservicespromptforpassworduponconnection"></a>Windows10EndpointProtectionConfiguration.RemoteDesktopServicesPromptForPasswordUponConnection 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteDesktopServices/PromptForPasswordUponConnection

#### <a name="windows10endpointprotectionconfigurationremotedesktopservicessecurerpccommunication"></a>Windows10EndpointProtectionConfiguration.RemoteDesktopServicesSecureRpcCommunication 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteDesktopServices/RequireSecureRPCCommunication

#### <a name="windows10endpointprotectionconfigurationremotehostdelegationofnonexportablecredentials"></a>Windows10EndpointProtectionConfiguration.RemoteHostDelegationOfNonExportableCredentials 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/CredentialsDelegation/RemoteHostAllowsDelegationOfNonExportableCredentials

#### <a name="windows10endpointprotectionconfigurationremotemanagementclientbasicauthentication"></a>Windows10EndpointProtectionConfiguration.RemoteManagementClientBasicAuthentication 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteManagement/AllowBasicAuthentication\_klienta

#### <a name="windows10endpointprotectionconfigurationremotemanagementclientdigestauthentication"></a>Windows10EndpointProtectionConfiguration.RemoteManagementClientDigestAuthentication 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteManagement/DisallowDigestAuthentication

#### <a name="windows10endpointprotectionconfigurationremotemanagementclientunencryptedtraffic"></a>Windows10EndpointProtectionConfiguration.RemoteManagementClientUnencryptedTraffic 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteManagement/AllowUnencryptedTraffic\_klienta

#### <a name="windows10endpointprotectionconfigurationremotemanagementservicebasicauthentication"></a>Windows10EndpointProtectionConfiguration.RemoteManagementServiceBasicAuthentication 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteManagement/AllowBasicAuthentication\_služby

#### <a name="windows10endpointprotectionconfigurationremotemanagementservicestoringrunascredentials"></a>Windows10EndpointProtectionConfiguration.RemoteManagementServiceStoringRunAsCredentials 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteManagement/DisallowStoringOfRunAsCredentials

#### <a name="windows10endpointprotectionconfigurationremotemanagementserviceunencryptedtraffic"></a>Windows10EndpointProtectionConfiguration.RemoteManagementServiceUnencryptedTraffic 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteManagement/AllowUnencryptedTraffic\_služby

#### <a name="windows10endpointprotectionconfigurationrpcunauthenticatedclientoptions"></a>Windows10EndpointProtectionConfiguration.RpcUnauthenticatedClientOptions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteProcedureCall/RestrictUnauthenticatedRPCClients

#### <a name="windows10endpointprotectionconfigurationsecurityguideapplyuacrestrictionstolocalaccountsonnetworklogon"></a>Windows10EndpointProtectionConfiguration.SecurityGuideApplyUacRestrictionsToLocalAccountsOnNetworkLogon 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/MSSecurityGuide/ApplyUACRestrictionsToLocalAccountsOnNetworkLogon

#### <a name="windows10endpointprotectionconfigurationsecurityguidesmbv1clientdriverstartconfiguration"></a>Windows10EndpointProtectionConfiguration.SecurityGuideSmbV1ClientDriverStartConfiguration 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/MSSecurityGuide/ConfigureSMBV1ClientDriver

#### <a name="windows10endpointprotectionconfigurationsecurityguidesmbv1server"></a>Windows10EndpointProtectionConfiguration.SecurityGuideSmbV1Server 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/MSSecurityGuide/ConfigureSMBV1Server

#### <a name="windows10endpointprotectionconfigurationsecurityguidestructuredexceptionhandlingoverwriteprotection"></a>Windows10EndpointProtectionConfiguration.SecurityGuideStructuredExceptionHandlingOverwriteProtection 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/MSSecurityGuide/EnableStructuredExceptionHandlingOverwriteProtection

#### <a name="windows10endpointprotectionconfigurationsecurityguidewdigestauthentication"></a>Windows10EndpointProtectionConfiguration.SecurityGuideWDigestAuthentication 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/MSSecurityGuide/WDigestAuthentication

#### <a name="windows10endpointprotectionconfigurationsmartscreenblockoverrideforfiles"></a>Windows10EndpointProtectionConfiguration.SmartScreenBlockOverrideForFiles 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy/  
**Posun identifikátoru URI**: /Config/DeviceGuard/RequirePlatformSecurityFeatures

#### <a name="windows10endpointprotectionconfigurationsmartscreenenableinshell"></a>Windows10EndpointProtectionConfiguration.SmartScreenEnableInShell 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy/  
**Posun identifikátoru URI**: /Config/SmartScreen/EnableSmartScreenInShell

#### <a name="windows10endpointprotectionconfigurationsolicitedremoteassistance"></a>windows10endpointprotectionconfiguration.solicitedRemoteAssistance 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/RemoteAssistance/SolicitedRemoteAssistance

#### <a name="windows10endpointprotectionconfigurationuserrightsaccesscredentialmanagerastrustedcaller"></a>Windows10EndpointProtectionConfiguration.UserRightsAccessCredentialManagerAsTrustedCaller 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/AccessCredentialManagerAsTrustedCaller

#### <a name="windows10endpointprotectionconfigurationuserrightsaccessfromnetwork"></a>windows10EndpointProtectionConfiguration.UserRightsAccessFromNetwork 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/UserRights/AccessFromNetwork

#### <a name="windows10endpointprotectionconfigurationuserrightsactaspartoftheoperatingsystem"></a>Windows10EndpointProtectionConfiguration.userRightsActAsPartOfTheOperatingSystem 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/UserRights/ActAsPartOfTheOperatingSystem

#### <a name="windows10endpointprotectionconfigurationuserrightsallowaccessfromnetwork"></a>Windows10EndpointProtectionConfiguration.UserRightsAllowAccessFromNetwork 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/UserRights/AccessFromNetwork

#### <a name="windows10endpointprotectionconfigurationuserrightsbackupdata"></a>Windows10EndpointProtectionConfiguration.UserRightsBackupData 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/BackupFilesAndDirectories

#### <a name="windows10endpointprotectionconfigurationuserrightsblockaccessfromnetwork"></a>Windows10EndpointProtectionConfiguration.UserRightsBlockAccessFromNetwork 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/DenyAccessFromNetwork

#### <a name="windows10endpointprotectionconfigurationuserrightschangesystemtime"></a>Windows10EndpointProtectionConfiguration.UserRightsChangeSystemTime 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/UserRights/ChangeSystemTime

#### <a name="windows10endpointprotectionconfigurationuserrightscreateglobalobjects"></a>Windows10EndpointProtectionConfiguration.UserRightsCreateGlobalObjects 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/UserRights/CreateGlobalObjects

#### <a name="windows10endpointprotectionconfigurationuserrightscreatepagefile"></a>Windows10EndpointProtectionConfiguration.UserRightsCreatePageFile 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/CreatePageFile

#### <a name="windows10endpointprotectionconfigurationuserrightscreatepermanentsharedobjects"></a>Windows10EndpointProtectionConfiguration.UserRightsCreatePermanentSharedObjects 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/UserRights/CreatePermanentSharedObjects

#### <a name="windows10endpointprotectionconfigurationuserrightscreatesymboliclinks"></a>Windows10EndpointProtectionConfiguration.UserRightsCreateSymbolicLinks 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/UserRights/CreateSymbolicLinks

#### <a name="windows10endpointprotectionconfigurationuserrightscreatetoken"></a>Windows10EndpointProtectionConfiguration.UserRightsCreateToken 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/CreateToken

#### <a name="windows10endpointprotectionconfigurationuserrightsdebugprograms"></a>Windows10EndpointProtectionConfiguration.UserRightsDebugPrograms 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/DebugPrograms

#### <a name="windows10endpointprotectionconfigurationuserrightsdelegation"></a>Windows10EndpointProtectionConfiguration.UserRightsDelegation 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/EnableDelegation

#### <a name="windows10endpointprotectionconfigurationuserrightsdenyaccessfromnetwork"></a>windows10EndpointProtectionConfiguration.UserRightsDenyAccessFromNetwork 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/DenyAccessFromNetwork

#### <a name="windows10endpointprotectionconfigurationuserrightsgeneratesecurityaudits"></a>Windows10EndpointProtectionConfiguration.UserRightsGenerateSecurityAudits 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/GenerateSecurityAudits

#### <a name="windows10endpointprotectionconfigurationuserrightsimpersonateclient"></a>Windows10EndpointProtectionConfiguration.UserRightsImpersonateClient 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/ImpersonateClient

#### <a name="windows10endpointprotectionconfigurationuserrightsincreaseschedulingpriority"></a>Windows10EndpointProtectionConfiguration.UserRightsIncreaseSchedulingPriority 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/IncreaseSchedulingPriority

#### <a name="windows10endpointprotectionconfigurationuserrightsloadunloaddrivers"></a>Windows10EndpointProtectionConfiguration.UserRightsLoadUnloadDrivers 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/LoadUnloadDeviceDrivers

#### <a name="windows10endpointprotectionconfigurationuserrightslocallogon"></a>Windows10EndpointProtectionConfiguration.UserRightsLocalLogOn 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/UserRights/AllowLocalLogOn

#### <a name="windows10endpointprotectionconfigurationuserrightslockmemory"></a>Windows10EndpointProtectionConfiguration.UserRightsLockMemory 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/LockMemory

#### <a name="windows10endpointprotectionconfigurationuserrightsmanageauditingandsecuritylogs"></a>Windows10EndpointProtectionConfiguration.UserRightsManageAuditingAndSecurityLogs 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/UserRights/ManageAuditingAndSecurityLog

#### <a name="windows10endpointprotectionconfigurationuserrightsmanagevolumes"></a>Windows10EndpointProtectionConfiguration.UserRightsManageVolumes 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/ManageVolume

#### <a name="windows10endpointprotectionconfigurationuserrightsmodifyfirmwareenvironment"></a>Windows10EndpointProtectionConfiguration.UserRightsModifyFirmwareEnvironment 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/ModifyFirmwareEnvironment

#### <a name="windows10endpointprotectionconfigurationuserrightsmodifyobjectlabels"></a>Windows10EndpointProtectionConfiguration.UserRightsModifyObjectLabels 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/UserRights/ModifyObjectLabel

#### <a name="windows10endpointprotectionconfigurationuserrightsprofilesingleprocess"></a>Windows10EndpointProtectionConfiguration.UserRightsProfileSingleProcess 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/ProfileSingleProcess

#### <a name="windows10endpointprotectionconfigurationuserrightsregisterprocessasservice"></a>Windows10EndpointProtectionConfiguration.UserRightsRegisterProcessAsService 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/DenyLocalLogOn

#### <a name="windows10endpointprotectionconfigurationuserrightsremotedesktopserviceslogon"></a>Windows10EndpointProtectionConfiguration.UserRightsRemoteDesktopServicesLogOn 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/UserRights/DenyRemoteDesktopServicesLogOn

#### <a name="windows10endpointprotectionconfigurationuserrightsremoteshutdown"></a>Windows10EndpointProtectionConfiguration.UserRightsRemoteShutdown 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/UserRights/RemoteShutdown

#### <a name="windows10endpointprotectionconfigurationuserrightsrestoredata"></a>Windows10EndpointProtectionConfiguration.UserRightsRestoreData 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/RestoreFilesAndDirectories

#### <a name="windows10endpointprotectionconfigurationuserrightstakeownership"></a>Windows10EndpointProtectionConfiguration.UserRightsTakeOwnership 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/UserRights/TakeOwnership

#### <a name="windows10endpointprotectionconfigurationwindowsconnectionmanagerconnectiontonondomainnetworks"></a>Windows10EndpointProtectionConfiguration.WindowsConnectionManagerConnectionToNonDomainNetworks 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/WindowsConnectionManager/ProhitConnectionToNonDomainNetworksWhenConnectedToDomainAuthenticatedNetwork

#### <a name="windows10endpointprotectionconfigurationwindowslogonsigninlastinteractiveuseraftersysteminitiatedrestart"></a>Windows10EndpointProtectionConfiguration.WindowsLogOnSignInLastInteractiveUserAfterSystemInitiatedRestart 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsLogon/SignInLastInteractiveUserAutomaticallyAfterASystemInitiatedRestart

#### <a name="windows10endpointprotectionconfigurationxboxservicesaccessorymanagementservicestartupmode"></a>Windows10EndpointProtectionConfiguration.XboxServicesAccessoryManagementServiceStartupMode 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/SystemServices/ConfigureXboxAccessoryManagementServiceStartupMode

#### <a name="windows10endpointprotectionconfigurationxboxservicesenablexboxgamesavetask"></a>Windows10EndpointProtectionConfiguration.XboxServicesEnableXboxGameSaveTask 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/TaskScheduler/EnableXboxGameSaveTask

#### <a name="windows10endpointprotectionconfigurationxboxservicesliveauthmanagerservicestartupmode"></a>Windows10EndpointProtectionConfiguration.XboxServicesLiveAuthManagerServiceStartupMode 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/SystemServices/ConfigureXboxLiveAuthManagerServiceStartupMode

#### <a name="windows10endpointprotectionconfigurationxboxserviceslivegamesaveservicestartupmode"></a>Windows10EndpointProtectionConfiguration.XboxServicesLiveGameSaveServiceStartupMode 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/SystemServices/XboxServicesLiveGameSaveServiceStartupMode

#### <a name="windows10endpointprotectionconfigurationxboxserviceslivenetworkingservicestartupmode"></a>Windows10EndpointProtectionConfiguration.XboxServicesLiveNetworkingServiceStartupMode 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/SystemServices/ConfigureXboxLiveNetworkingServiceStartupMode

#### <a name="windows10generalconfigurationaccountsblockaddingnonmicrosoftaccountemail"></a>Windows10GeneralConfiguration.AccountsBlockAddingNonMicrosoftAccountEmail 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Accounts/AllowAddingNonMicrosoftAccountsManually

#### <a name="windows10generalconfigurationantitheftmodeblocked"></a>Windows10GeneralConfiguration.AntiTheftModeBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Security/AntiTheftMode

#### <a name="windows10generalconfigurationappmanagementmsiallowusercontroloverinstall"></a>Windows10GeneralConfiguration.AppManagementMSIAllowUserControlOverInstall 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ApplicationManagement/MSIAllowUserControlOverInstall

#### <a name="windows10generalconfigurationappmanagementmsialwaysinstallwithelevatedprivileges"></a>Windows10GeneralConfiguration.AppManagementMSIAlwaysInstallWithElevatedPrivileges 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ApplicationManagement/MSIAlwaysInstallWithElevatedPrivileges

#### <a name="windows10generalconfigurationappsallowtrustedappssideloading"></a>Windows10GeneralConfiguration.AppsAllowTrustedAppsSideloading 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ApplicationManagement/AllowAllTrustedApps

#### <a name="windows10generalconfigurationappsblockwindowsstoreoriginatedapps"></a>Windows10GeneralConfiguration.AppsBlockWindowsStoreOriginatedApps 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ApplicationManagement/DisableStoreOriginatedApps

#### <a name="windows10generalconfigurationappsmicrosoftaccountsoptional"></a>Windows10GeneralConfiguration.AppsMicrosoftAccountsOptional 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/AppRuntime/AllowMicrosoftAccountsToBeOptional

#### <a name="windows10generalconfigurationassignedaccessmultimodeprofiles"></a>Windows10GeneralConfiguration.AssignedAccessMultiModeProfiles 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/AssignedAccess  
**Posun identifikátoru URI**: / Configuration

#### <a name="windows10generalconfigurationassignedaccesssinglemodeappusermodelid"></a>Windows10GeneralConfiguration.AssignedAccessSingleModeAppUserModelId 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/AssignedAccess  
**Posun identifikátoru URI**: / Configuration

#### <a name="windows10generalconfigurationassignedaccesssinglemodeusername"></a>Windows10GeneralConfiguration.AssignedAccessSingleModeUserName 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/AssignedAccess  
**Posun identifikátoru URI**: / Configuration

#### <a name="windows10generalconfigurationauthenticationallowfidodevice"></a>Windows10GeneralConfiguration.AuthenticationAllowFIDODevice 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/Authentication/AllowFidoDeviceSignon

#### <a name="windows10generalconfigurationauthenticationallowsecondarydevice"></a>Windows10GeneralConfiguration.AuthenticationAllowSecondaryDevice 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Authentication/AllowSecondaryAuthenticationDevice

#### <a name="windows10generalconfigurationauthenticationpreferredazureadtenantdomainname"></a>Windows10GeneralConfiguration.AuthenticationPreferredAzureADTenantDomainName 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/Authentication/PreferredAadTenantDomainName

#### <a name="windows10generalconfigurationauthenticationwebsignin"></a>Windows10GeneralConfiguration.AuthenticationWebSignIn 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Authentication/EnableWebSignIn

#### <a name="windows10generalconfigurationautoplaydefaultautorunbehavior"></a>Windows10GeneralConfiguration.AutoPlayDefaultAutoRunBehavior 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Autoplay/SetDefaultAutoRunBehavior

#### <a name="windows10generalconfigurationautoplayfornonvolumedevices"></a>Windows10GeneralConfiguration.AutoPlayForNonVolumeDevices 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Autoplay/DisallowAutoplayForNonVolumeDevices

#### <a name="windows10generalconfigurationautoplaymode"></a>Windows10GeneralConfiguration.AutoPlayMode 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Autoplay/TurnOffAutoPlay

#### <a name="windows10generalconfigurationbluetoothallowedservices"></a>Windows10GeneralConfiguration.BluetoothAllowedServices 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Bluetooth/ServicesAllowedList

#### <a name="windows10generalconfigurationbluetoothblockadvertising"></a>Windows10GeneralConfiguration.BluetoothBlockAdvertising 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Bluetooth/AllowAdvertising

#### <a name="windows10generalconfigurationbluetoothblockdiscoverablemode"></a>Windows10GeneralConfiguration.BluetoothBlockDiscoverableMode 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Bluetooth/AllowDiscoverableMode

#### <a name="windows10generalconfigurationbluetoothblocked"></a>Windows10GeneralConfiguration.BluetoothBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Connectivity/AllowBluetooth

#### <a name="windows10generalconfigurationbluetoothblockprepairing"></a>Windows10GeneralConfiguration.BluetoothBlockPrePairing 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Bluetooth/AllowPrepairing

#### <a name="windows10generalconfigurationbluetoothblockpromptedproximalconnections"></a>Windows10GeneralConfiguration.BluetoothBlockPromptedProximalConnections 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Bluetooth/AllowPromptedProximalConnections

#### <a name="windows10generalconfigurationbluetoothdevicename"></a>Windows10GeneralConfiguration.BluetoothDeviceName 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Bluetooth/LocalDeviceName

#### <a name="windows10generalconfigurationbootstartdriverinitialization"></a>windows10generalconfiguration.bootStartDriverInitialization 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/System/BootStartDriverInitialization

#### <a name="windows10generalconfigurationcamerablocked"></a>Windows10GeneralConfiguration.CameraBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Camera/AllowCamera

#### <a name="windows10generalconfigurationcellularblockdatawhenroaming"></a>Windows10GeneralConfiguration.CellularBlockDataWhenRoaming 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Connectivity/AllowCellularDataRoaming

#### <a name="windows10generalconfigurationcellularblockvpn"></a>Windows10GeneralConfiguration.CellularBlockVpn 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Connectivity/AllowVPNOverCellular

#### <a name="windows10generalconfigurationcellularblockvpnwhenroaming"></a>Windows10GeneralConfiguration.CellularBlockVpnWhenRoaming 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Connectivity/AllowVPNRoamingOverCellular

#### <a name="windows10generalconfigurationcellulardata"></a>Windows10GeneralConfiguration.CellularData 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Connectivity/AllowCellularData

#### <a name="windows10generalconfigurationcertificatesblockmanualrootcertificateinstallation"></a>Windows10GeneralConfiguration.CertificatesBlockManualRootCertificateInstallation 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Security/AllowManualRootCertificateInstallation

#### <a name="windows10generalconfigurationconnecteddevicesserviceblocked"></a>Windows10GeneralConfiguration.ConnectedDevicesServiceBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Connectivity/AllowConnectedDevices

#### <a name="windows10generalconfigurationcopypasteblocked"></a>Windows10GeneralConfiguration.CopyPasteBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowCopyPaste

#### <a name="windows10generalconfigurationcortanablocked"></a>Windows10GeneralConfiguration.CortanaBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/AboveLock/AllowCortanaAboveLock

#### <a name="windows10generalconfigurationcryptographyallowfipsalgorithmpolicy"></a>Windows10GeneralConfiguration.CryptographyAllowFipsAlgorithmPolicy 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Cryptography/AllowFipsAlgorithmPolicy

#### <a name="windows10generalconfigurationdataprotectionblockdirectmemoryaccess"></a>Windows10GeneralConfiguration.DataProtectionBlockDirectMemoryAccess 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DataProtection/AllowDirectMemoryAccess

#### <a name="windows10generalconfigurationdefenderblockenduseraccess"></a>Windows10GeneralConfiguration.DefenderBlockEndUserAccess 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowUserUIAccess

#### <a name="windows10generalconfigurationdefenderblockonaccessprotection"></a>Windows10GeneralConfiguration.DefenderBlockOnAccessProtection 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowOnAccessProtection

#### <a name="windows10generalconfigurationdefendercloudblocklevel"></a>Windows10GeneralConfiguration.DefenderCloudBlockLevel 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/CloudBlockLevel

#### <a name="windows10generalconfigurationdefendercloudextendedtimeout"></a>Windows10GeneralConfiguration.DefenderCloudExtendedTimeout 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/CloudExtendedTimeout

#### <a name="windows10generalconfigurationdefendercloudextendedtimeoutinseconds"></a>Windows10GeneralConfiguration.DefenderCloudExtendedTimeoutInSeconds 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/CloudExtendedTimeout

#### <a name="windows10generalconfigurationdefenderdaysbeforedeletingquarantinedmalware"></a>Windows10GeneralConfiguration.DefenderDaysBeforeDeletingQuarantinedMalware 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/DaysToRetainCleanedMalware

#### <a name="windows10generalconfigurationdefenderdetectedmalwareactions"></a>Windows10GeneralConfiguration.DefenderDetectedMalwareActions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/ThreatSeverityDefaultAction

#### <a name="windows10generalconfigurationdefenderfileextensionstoexclude"></a>Windows10GeneralConfiguration.DefenderFileExtensionsToExclude 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/ExcludedExtensions

#### <a name="windows10generalconfigurationdefenderfilesandfolderstoexclude"></a>Windows10GeneralConfiguration.DefenderFilesAndFoldersToExclude 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/ExcludedPaths

#### <a name="windows10generalconfigurationdefendermonitorfileactivity"></a>Windows10GeneralConfiguration.DefenderMonitorFileActivity 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowRealtimeMonitoring

#### <a name="windows10generalconfigurationdefenderpotentiallyunwantedappaction"></a>Windows10GeneralConfiguration.DefenderPotentiallyUnwantedAppAction 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/PUAProtection

#### <a name="windows10generalconfigurationdefenderpotentiallyunwantedappactionsetting"></a>Windows10GeneralConfiguration.DefenderPotentiallyUnwantedAppActionSetting 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/PUAProtection

#### <a name="windows10generalconfigurationdefenderprocessestoexclude"></a>Windows10GeneralConfiguration.DefenderProcessesToExclude 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/ExcludedProcesses

#### <a name="windows10generalconfigurationdefenderpromptforsamplesubmission"></a>Windows10GeneralConfiguration.DefenderPromptForSampleSubmission 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/SubmitSamplesConsent

#### <a name="windows10generalconfigurationdefenderrequirebehaviormonitoring"></a>Windows10GeneralConfiguration.DefenderRequireBehaviorMonitoring 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowBehaviorMonitoring

#### <a name="windows10generalconfigurationdefenderrequirecloudprotection"></a>Windows10GeneralConfiguration.DefenderRequireCloudProtection 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowCloudProtection

#### <a name="windows10generalconfigurationdefenderrequirenetworkinspectionsystem"></a>Windows10GeneralConfiguration.DefenderRequireNetworkInspectionSystem 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowIntrusionPreventionSystem

#### <a name="windows10generalconfigurationdefenderrequirerealtimemonitoring"></a>Windows10GeneralConfiguration.DefenderRequireRealTimeMonitoring 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowRealtimeMonitoring

#### <a name="windows10generalconfigurationdefenderscanarchivefiles"></a>Windows10GeneralConfiguration.DefenderScanArchiveFiles 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowArchiveScanning

#### <a name="windows10generalconfigurationdefenderscandownloads"></a>Windows10GeneralConfiguration.DefenderScanDownloads 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowIOAVProtection

#### <a name="windows10generalconfigurationdefenderscanincomingmail"></a>Windows10GeneralConfiguration.DefenderScanIncomingMail 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowScanningNetworkFiles

#### <a name="windows10generalconfigurationdefenderscanmappednetworkdrivesduringfullscan"></a>Windows10GeneralConfiguration.DefenderScanMappedNetworkDrivesDuringFullScan 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/Defender/AllowFullScanOnMappedNetworkDrives

#### <a name="windows10generalconfigurationdefenderscanmaxcpu"></a>Windows10GeneralConfiguration.DefenderScanMaxCpu 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AvgCPULoadFactor

#### <a name="windows10generalconfigurationdefenderscannetworkfiles"></a>Windows10GeneralConfiguration.DefenderScanNetworkFiles 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowScanningNetworkFiles

#### <a name="windows10generalconfigurationdefenderscanremovabledrivesduringfullscan"></a>Windows10GeneralConfiguration.DefenderScanRemovableDrivesDuringFullScan 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowFullScanRemovableDriveScanning

#### <a name="windows10generalconfigurationdefenderscanscriptsloadedininternetexplorer"></a>Windows10GeneralConfiguration.DefenderScanScriptsLoadedInInternetExplorer 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/AllowScriptScanning

#### <a name="windows10generalconfigurationdefenderscantype"></a>Windows10GeneralConfiguration.DefenderScanType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/ScanParameter

#### <a name="windows10generalconfigurationdefenderscheduledquickscantime"></a>Windows10GeneralConfiguration.DefenderScheduledQuickScanTime 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/ScheduleQuickScanTime

#### <a name="windows10generalconfigurationdefenderscheduledscantime"></a>Windows10GeneralConfiguration.DefenderScheduledScanTime 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/ScheduleScanTime

#### <a name="windows10generalconfigurationdefenderschedulescanday"></a>Windows10GeneralConfiguration.DefenderScheduleScanDay 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/ScheduleScanDay

#### <a name="windows10generalconfigurationdefendersignatureupdateintervalinhours"></a>Windows10GeneralConfiguration.DefenderSignatureUpdateIntervalInHours 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/SignatureUpdateInterval

#### <a name="windows10generalconfigurationdefendersubmitsamplesconsenttype"></a>Windows10GeneralConfiguration.DefenderSubmitSamplesConsentType 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/SubmitSamplesConsent

#### <a name="windows10generalconfigurationdefendersystemscanschedule"></a>Windows10GeneralConfiguration.DefenderSystemScanSchedule 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Defender/ScheduleScanDay

#### <a name="windows10generalconfigurationdeveloperunlocksetting"></a>Windows10GeneralConfiguration.DeveloperUnlockSetting 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ApplicationManagement/AllowDeveloperUnlock

#### <a name="windows10generalconfigurationdevicemanagementblockfactoryresetonmobile"></a>Windows10GeneralConfiguration.DeviceManagementBlockFactoryResetOnMobile 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/System/AllowUserToResetPhone

#### <a name="windows10generalconfigurationdevicemanagementblockmanualunenroll"></a>Windows10GeneralConfiguration.DeviceManagementBlockManualUnenroll 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowManualMDMUnenrollment

#### <a name="windows10generalconfigurationdiagnosticsdatasubmissionmode"></a>Windows10GeneralConfiguration.DiagnosticsDataSubmissionMode 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/System/AllowTelemetry

#### <a name="windows10generalconfigurationdisplayapplistwithgdidpiscalingturnedoff"></a>Windows10GeneralConfiguration.DisplayAppListWithGdiDPIScalingTurnedOff 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Display/TurnOffGdiDPIScalingForApps

#### <a name="windows10generalconfigurationdisplayapplistwithgdidpiscalingturnedon"></a>Windows10GeneralConfiguration.DisplayAppListWithGdiDPIScalingTurnedOn 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Display/TurnOnGdiDPIScalingForApps

#### <a name="windows10generalconfigurationedgeallowstartpagesmodification"></a>Windows10GeneralConfiguration.EdgeAllowStartPagesModification 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/HomePages

#### <a name="windows10generalconfigurationedgeblockaccesstoaboutflags"></a>Windows10GeneralConfiguration.EdgeBlockAccessToAboutFlags 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/Browser/PreventAccessToAboutFlagsInMicrosoftEdge

#### <a name="windows10generalconfigurationedgeblockaddressbardropdown"></a>Windows10GeneralConfiguration.EdgeBlockAddressBarDropdown 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowAddressBarDropdown

#### <a name="windows10generalconfigurationedgeblockautofill"></a>Windows10GeneralConfiguration.EdgeBlockAutofill 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowAutofill

#### <a name="windows10generalconfigurationedgeblockcompatibilitylist"></a>Windows10GeneralConfiguration.EdgeBlockCompatibilityList 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowMicrosoftCompatibilityList

#### <a name="windows10generalconfigurationedgeblockdevelopertools"></a>Windows10GeneralConfiguration.EdgeBlockDeveloperTools 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowDeveloperTools

#### <a name="windows10generalconfigurationedgeblocked"></a>Windows10GeneralConfiguration.EdgeBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowBrowser

#### <a name="windows10generalconfigurationedgeblockeditfavorites"></a>Windows10GeneralConfiguration.EdgeBlockEditFavorites 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/LockdownFavorites

#### <a name="windows10generalconfigurationedgeblockextensions"></a>Windows10GeneralConfiguration.EdgeBlockExtensions 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowExtensions

#### <a name="windows10generalconfigurationedgeblockfullscreenmode"></a>Windows10GeneralConfiguration.EdgeBlockFullScreenMode 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowFullScreenMode

#### <a name="windows10generalconfigurationedgeblockinprivatebrowsing"></a>Windows10GeneralConfiguration.EdgeBlockInPrivateBrowsing 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowInPrivate

#### <a name="windows10generalconfigurationedgeblocklivetiledatacollection"></a>Windows10GeneralConfiguration.EdgeBlockLiveTileDataCollection 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/PreventLiveTileDataCollection

#### <a name="windows10generalconfigurationedgeblockpasswordmanager"></a>Windows10GeneralConfiguration.EdgeBlockPasswordManager 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowPasswordManager

#### <a name="windows10generalconfigurationedgeblockpopups"></a>Windows10GeneralConfiguration.EdgeBlockPopups 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowPopups

#### <a name="windows10generalconfigurationedgeblockprelaunch"></a>Windows10GeneralConfiguration.EdgeBlockPrelaunch 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowPrelaunch

#### <a name="windows10generalconfigurationedgeblockprinting"></a>Windows10GeneralConfiguration.EdgeBlockPrinting 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowPrinting

#### <a name="windows10generalconfigurationedgeblocksavinghistory"></a>Windows10GeneralConfiguration.EdgeBlockSavingHistory 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowSavingHistory

#### <a name="windows10generalconfigurationedgeblocksearchsuggestions"></a>Windows10GeneralConfiguration.EdgeBlockSearchSuggestions 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/Browser/AllowSearchSuggestionsinAddressBar

#### <a name="windows10generalconfigurationedgeblocksendingdonottrackheader"></a>Windows10GeneralConfiguration.EdgeBlockSendingDoNotTrackHeader 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowDoNotTrack

#### <a name="windows10generalconfigurationedgeblocksendingintranettraffictointernetexplorer"></a>Windows10GeneralConfiguration.EdgeBlockSendingIntranetTrafficToInternetExplorer 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/SendIntranetTraffictoInternetExplorer

#### <a name="windows10generalconfigurationedgeblocksideloadingextensions"></a>Windows10GeneralConfiguration.EdgeBlockSideloadingExtensions 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowSideloadingOfExtensions

#### <a name="windows10generalconfigurationedgeblocktabpreloading"></a>Windows10GeneralConfiguration.EdgeBlockTabPreloading 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowTabPreloading

#### <a name="windows10generalconfigurationedgeblockwebcontentonnewtabpage"></a>Windows10GeneralConfiguration.EdgeBlockWebContentOnNewTabPage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowWebContentOnNewTabPage

#### <a name="windows10generalconfigurationedgeclearbrowsingdataonexit"></a>Windows10GeneralConfiguration.EdgeClearBrowsingDataOnExit 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/ClearBrowsingDataOnExit

#### <a name="windows10generalconfigurationedgecookiepolicy"></a>Windows10GeneralConfiguration.EdgeCookiePolicy 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowCookies

#### <a name="windows10generalconfigurationedgedisablefirstrunpage"></a>Windows10GeneralConfiguration.EdgeDisableFirstRunPage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/PreventFirstRunPage

#### <a name="windows10generalconfigurationedgeenterprisemodesitelistlocation"></a>Windows10GeneralConfiguration.EdgeEnterpriseModeSiteListLocation 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/EnterpriseSiteListServiceUrl

#### <a name="windows10generalconfigurationedgefavoritesbarvisibility"></a>Windows10GeneralConfiguration.EdgeFavoritesBarVisibility 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/ConfigureFavoritesBar

#### <a name="windows10generalconfigurationedgefavoriteslistlocation"></a>Windows10GeneralConfiguration.EdgeFavoritesListLocation 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/ProvisionFavorites

#### <a name="windows10generalconfigurationedgefirstrunurl"></a>Windows10GeneralConfiguration.EdgeFirstRunUrl 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/FirstRunURL

#### <a name="windows10generalconfigurationedgehomebuttonconfiguration"></a>Windows10GeneralConfiguration.EdgeHomeButtonConfiguration 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/SetHomeButtonURL

#### <a name="windows10generalconfigurationedgehomebuttonconfigurationenabled"></a>Windows10GeneralConfiguration.EdgeHomeButtonConfigurationEnabled 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/ConfigureHomeButton

#### <a name="windows10generalconfigurationedgehomepageurls"></a>Windows10GeneralConfiguration.EdgeHomepageUrls 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/SetHomeButtonURL

#### <a name="windows10generalconfigurationedgenewtabpageurl"></a>Windows10GeneralConfiguration.EdgeNewTabPageURL 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/SetNewTabPageURL

#### <a name="windows10generalconfigurationedgeopenswith"></a>Windows10GeneralConfiguration.EdgeOpensWith 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/ConfigureOpenMicrosoftEdgeWith

#### <a name="windows10generalconfigurationedgepreventcertificateerroroverride"></a>Windows10GeneralConfiguration.EdgePreventCertificateErrorOverride 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/PreventCertErrorOverrides

#### <a name="windows10generalconfigurationedgerequiresmartscreen"></a>Windows10GeneralConfiguration.EdgeRequireSmartScreen 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/AllowSmartScreen

#### <a name="windows10generalconfigurationedgesearchengine"></a>Windows10GeneralConfiguration.EdgeSearchEngine 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/SetDefaultSearchEngine

#### <a name="windows10generalconfigurationedgesendintranettraffictointernetexplorer"></a>Windows10GeneralConfiguration.EdgeSendIntranetTrafficToInternetExplorer 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/SendIntranetTraffictoInternetExplorer

#### <a name="windows10generalconfigurationedgeshowmessagewhenopeninginternetexplorersites"></a>Windows10GeneralConfiguration.EdgeShowMessageWhenOpeningInternetExplorerSites 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/ShowMessageWhenOpeningSitesInInternetExplorer

#### <a name="windows10generalconfigurationedgesyncfavoriteswithinternetexplorer"></a>Windows10GeneralConfiguration.EdgeSyncFavoritesWithInternetExplorer 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/SyncFavoritesBetweenIEAndMicrosoftEdge

#### <a name="windows10generalconfigurationedgetelemetryformicrosoft365analytics"></a>Windows10GeneralConfiguration.EdgeTelemetryForMicrosoft365Analytics 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/ConfigureTelemetryForMicrosoft365Analytics

#### <a name="windows10generalconfigurationenableautomaticredeployment"></a>Windows10GeneralConfiguration.EnableAutomaticRedeployment 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/CredentialProviders/DisableAutomaticReDeploymentCredentials

#### <a name="windows10generalconfigurationenterprisecloudprintdiscoveryendpoint"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintDiscoveryEndPoint 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/EnterpriseCloudPrint/CloudPrinterDiscoveryEndPoint

#### <a name="windows10generalconfigurationenterprisecloudprintdiscoverymaxlimit"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintDiscoveryMaxLimit 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Offset URI**: /Config/EnterpriseCloudPrint/DiscoveryMaxPrinterLimit

#### <a name="windows10generalconfigurationenterprisecloudprintmopriadiscoveryresourceidentifier"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintMopriaDiscoveryResourceIdentifier 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/EnterpriseCloudPrint/MopriaDiscoveryResourceId

#### <a name="windows10generalconfigurationenterprisecloudprintoauthauthority"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintOAuthAuthority 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Offset URI**: /Config/EnterpriseCloudPrint/CloudPrintOAuthAuthority

#### <a name="windows10generalconfigurationenterprisecloudprintoauthclientidentifier"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintOAuthClientIdentifier 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Offset URI**: /Config/EnterpriseCloudPrint/CloudPrintOAuthAuthority

#### <a name="windows10generalconfigurationenterprisecloudprintresourceidentifier"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintResourceIdentifier 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/EnterpriseCloudPrint/CloudPrintResourceId

#### <a name="windows10generalconfigurationexperienceblockconsumerspecificfeatures"></a>Windows10GeneralConfiguration.ExperienceBlockConsumerSpecificFeatures 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowWindowsConsumerFeatures

#### <a name="windows10generalconfigurationexperienceblockdevicediscovery"></a>Windows10GeneralConfiguration.ExperienceBlockDeviceDiscovery 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowDeviceDiscovery

#### <a name="windows10generalconfigurationexperienceblockerrordialogwhennosim"></a>Windows10GeneralConfiguration.ExperienceBlockErrorDialogWhenNoSIM 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowSIMErrorDialogPromptWhenNoSIM

#### <a name="windows10generalconfigurationexperienceblocktaskswitcher"></a>Windows10GeneralConfiguration.ExperienceBlockTaskSwitcher 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowTaskSwitcher

#### <a name="windows10generalconfigurationexperienceblockwindowsspotlight"></a>Windows10GeneralConfiguration.ExperienceBlockWindowsSpotlight 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowWindowsSpotlight

#### <a name="windows10generalconfigurationexperiencedonotsyncbrowsersettings"></a>Windows10GeneralConfiguration.ExperienceDoNotSyncBrowserSettings 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/DoNotSyncBrowserSettings

#### <a name="windows10generalconfigurationgamedvrblocked"></a>Windows10GeneralConfiguration.GameDvrBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ApplicationManagement/AllowGameDVR

#### <a name="windows10generalconfigurationhardwaredeviceinstallationbydeviceidentifiers"></a>Windows10GeneralConfiguration.HardwareDeviceInstallationByDeviceIdentifiers 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceInstallation/PreventInstallationOfMatchingDeviceIDs

#### <a name="windows10generalconfigurationhardwaredeviceinstallationbysetupclasses"></a>Windows10GeneralConfiguration.HardwareDeviceInstallationBySetupClasses 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceInstallation/PreventInstallationOfMatchingDeviceSetupClasses

#### <a name="windows10generalconfigurationinkworkspaceaccess"></a>Windows10GeneralConfiguration.InkWorkspaceAccess 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsInkWorkspace/AllowWindowsInkWorkspace

#### <a name="windows10generalconfigurationinkworkspaceaccessstate"></a>Windows10GeneralConfiguration.InkWorkspaceAccessState 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsInkWorkspace/AllowWindowsInkWorkspace

#### <a name="windows10generalconfigurationinkworkspaceblocksuggestedapps"></a>Windows10GeneralConfiguration.InkWorkspaceBlockSuggestedApps 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsInkWorkspace/AllowSuggestedAppsInWindowsInkWorkspace

#### <a name="windows10generalconfigurationinternetexploreractivexcontrolsinprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerActiveXControlsInProtectedMode 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/DoNotAllowActiveXControlsInProtectedMode

#### <a name="windows10generalconfigurationinternetexplorerautocomplete"></a>Windows10GeneralConfiguration.InternetExplorerAutoComplete 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/AllowAutoComplete

#### <a name="windows10generalconfigurationinternetexplorerblockoutdatedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerBlockOutdatedActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/DoNotBlockOutdatedActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerbypasssmartscreenwarnings"></a>Windows10GeneralConfiguration.InternetExplorerBypassSmartScreenWarnings 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/DisableBypassOfSmartScreenWarnings

#### <a name="windows10generalconfigurationinternetexplorerbypasssmartscreenwarningsaboutuncommonfiles"></a>Windows10GeneralConfiguration.InternetExplorerBypassSmartScreenWarningsAboutUncommonFiles 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/DisableBypassOfSmartScreenWarningsAboutUncommonFiles

#### <a name="windows10generalconfigurationinternetexplorercertificateaddressmismatchwarning"></a>Windows10GeneralConfiguration.InternetExplorerCertificateAddressMismatchWarning 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/AllowCertificateAddressMismatchWarning

#### <a name="windows10generalconfigurationinternetexplorercheckservercertificaterevocation"></a>Windows10GeneralConfiguration.InternetExplorerCheckServerCertificateRevocation 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/CheckServerCertificateRevocation

#### <a name="windows10generalconfigurationinternetexplorerchecksignaturesondownloadedprograms"></a>Windows10GeneralConfiguration.InternetExplorerCheckSignaturesOnDownloadedPrograms 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/CheckSignaturesOnDownloadedPrograms

#### <a name="windows10generalconfigurationinternetexplorercrashdetection"></a>Windows10GeneralConfiguration.InternetExplorerCrashDetection 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/DisableCrashDetection

#### <a name="windows10generalconfigurationinternetexplorerdisableprocessesinenhancedprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerDisableProcessesInEnhancedProtectedMode 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/DisableProcessesInEnhancedProtectedMode

#### <a name="windows10generalconfigurationinternetexplorerdownloadenclosures"></a>Windows10GeneralConfiguration.InternetExplorerDownloadEnclosures 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/DisableEnclosureDownloading

#### <a name="windows10generalconfigurationinternetexplorerencryptionsupport"></a>Windows10GeneralConfiguration.InternetExplorerEncryptionSupport 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/DisableEncryptionSupport

#### <a name="windows10generalconfigurationinternetexplorerenhancedprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerEnhancedProtectedMode 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/AllowEnhancedProtectedMode

#### <a name="windows10generalconfigurationinternetexplorerfallbacktossl3"></a>Windows10GeneralConfiguration.InternetExplorerFallbackToSsl3 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/AllowFallbackToSSL3

#### <a name="windows10generalconfigurationinternetexplorerignorecertificateerrors"></a>Windows10GeneralConfiguration.InternetExplorerIgnoreCertificateErrors 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/DisableIgnoringCertificateErrors

#### <a name="windows10generalconfigurationinternetexplorerincludeallnetworkpaths"></a>Windows10GeneralConfiguration.InternetExplorerIncludeAllNetworkPaths 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/IncludeAllNetworkPaths

#### <a name="windows10generalconfigurationinternetexplorerinternetzoneaccesstodatasources"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneAccessToDataSources 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowAccessToDataSources

#### <a name="windows10generalconfigurationinternetexplorerinternetzoneallowonlyapproveddomainstouseactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneAllowOnlyApprovedDomainsToUseActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowOnlyApprovedDomainsToUseActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerinternetzoneallowonlyapproveddomainstousetdcactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneAllowOnlyApprovedDomainsToUseTdcActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl

#### <a name="windows10generalconfigurationinternetexplorerinternetzoneallowvbscripttorun"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneAllowVBScriptToRun 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowVBScriptToRunInInternetExplorer

#### <a name="windows10generalconfigurationinternetexplorerinternetzoneautomaticpromptforfiledownloads"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneAutomaticPromptForFileDownloads 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowAutomaticPromptingForFileDownloads

#### <a name="windows10generalconfigurationinternetexplorerinternetzonecopyandpasteviascript"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneCopyAndPasteViaScript 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowCopyPasteViaScript

#### <a name="windows10generalconfigurationinternetexplorerinternetzonecrosssitescriptingfilter"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneCrossSiteScriptingFilter 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneEnableCrossSiteScriptingFilter

#### <a name="windows10generalconfigurationinternetexplorerinternetzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDoNotRunAntimalwareAgainstActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneDoNotRunAntimalwareAgainstActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerinternetzonedotnetframeworkreliantcomponents"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDotNetFrameworkReliantComponents 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowNETFrameworkReliantComponents

#### <a name="windows10generalconfigurationinternetexplorerinternetzonedownloadsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDownloadSignedActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/InternetZoneDownloadSignedActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerinternetzonedownloadunsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDownloadUnsignedActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneDownloadUnsignedActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerinternetzonedraganddroporcopyandpastefiles"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDragAndDropOrCopyAndPasteFiles 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/InternetZoneAllowDragAndDropCopyAndPasteFiles

#### <a name="windows10generalconfigurationinternetexplorerinternetzonedragcontentfromdifferentdomainsacrosswindows"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDragContentFromDifferentDomainsAcrossWindows 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows

#### <a name="windows10generalconfigurationinternetexplorerinternetzonedragcontentfromdifferentdomainswithinwindows"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDragContentFromDifferentDomainsWithinWindows 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows

#### <a name="windows10generalconfigurationinternetexplorerinternetzoneincludelocalpathwhenuploadingfilestoserver"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneIncludeLocalPathWhenUploadingFilesToServer 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneIncludeLocalPathWhenUploadingFilesToServer

#### <a name="windows10generalconfigurationinternetexplorerinternetzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneInitializeAndScriptActiveXControlsNotMarkedAsSafe 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneInitializeAndScriptActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerinternetzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneJavaPermissions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/InternetZoneJavaPermissions


#### <a name="windows10generalconfigurationinternetexplorerinternetzonelaunchapplicationsandfilesinaniframe"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneLaunchApplicationsAndFilesInAnIFrame 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/InternetZoneLaunchingApplicationsAndFilesInIFRAME

#### <a name="windows10generalconfigurationinternetexplorerinternetzonelessprivilegedsites"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneLessPrivilegedSites 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowLessPrivilegedSites

#### <a name="windows10generalconfigurationinternetexplorerinternetzoneloadingofxamlfiles"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneLoadingOfXamlFiles 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowLoadingOfXAMLFiles

#### <a name="windows10generalconfigurationinternetexplorerinternetzonelogonoptions"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneLogonOptions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneLogonOptions

#### <a name="windows10generalconfigurationinternetexplorerinternetzonenavigatewindowsandframesacrossdifferentdomains"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneNavigateWindowsAndFramesAcrossDifferentDomains 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneNavigateWindowsAndFrames

#### <a name="windows10generalconfigurationinternetexplorerinternetzonepopupblocker"></a>Windows10GeneralConfiguration.InternetExplorerInternetZonePopupBlocker 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/InternetZoneUsePopupBlocker

#### <a name="windows10generalconfigurationinternetexplorerinternetzoneprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneProtectedMode 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneEnableProtectedMode

#### <a name="windows10generalconfigurationinternetexplorerinternetzonerundotnetframeworkreliantcomponentssignedwithauthenticode"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneRunDotNetFrameworkReliantComponentsSignedWithAuthenticode 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneRunNETFrameworkReliantComponentsSignedWithAuthenticode

#### <a name="windows10generalconfigurationinternetexplorerinternetzonescriptingofwebbrowsercontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneScriptingOfWebBrowserControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowScriptingOfInternetExplorerWebBrowserControls

#### <a name="windows10generalconfigurationinternetexplorerinternetzonescriptinitiatedwindows"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneScriptInitiatedWindows 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowScriptInitiatedWindows

#### <a name="windows10generalconfigurationinternetexplorerinternetzonescriptlets"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneScriptlets 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/InternetZoneAllowScriptlets

#### <a name="windows10generalconfigurationinternetexplorerinternetzonesecuritywarningforpotentiallyunsafefiles"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneSecurityWarningForPotentiallyUnsafeFiles 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneShowSecurityWarningForPotentiallyUnsafeFiles

#### <a name="windows10generalconfigurationinternetexplorerinternetzonesmartscreen"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneSmartScreen 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowSmartScreenIE

#### <a name="windows10generalconfigurationinternetexplorerinternetzoneupdatestostatusbarviascript"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneUpdatesToStatusBarViaScript 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowUpdatesToStatusBarViaScript

#### <a name="windows10generalconfigurationinternetexplorerinternetzoneuserdatapersistence"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneUserDataPersistence 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/InternetZoneAllowUserDataPersistence

#### <a name="windows10generalconfigurationinternetexplorerintranetzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerIntranetZoneDoNotRunAntimalwareAgainstActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/IntranetZoneDoNotRunAntimalwareAgainstActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerintranetzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration.InternetExplorerIntranetZoneInitializeAndScriptActiveXControlsNotMarkedAsSafe 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/IntranetZoneInitializeAndScriptActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerintranetzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerIntranetZoneJavaPermissions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/IntranetZoneJavaPermissions

#### <a name="windows10generalconfigurationinternetexplorerlocalmachinezonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerLocalMachineZoneDoNotRunAntimalwareAgainstActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/LocalMachineZoneDoNotRunAntimalwareAgainstActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerlocalmachinezonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerLocalMachineZoneJavaPermissions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/LocalMachineZoneJavaPermissions

#### <a name="windows10generalconfigurationinternetexplorerlockeddowninternetzonesmartscreen"></a>Windows10GeneralConfiguration.InternetExplorerLockedDownInternetZoneSmartScreen 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/LockedDownInternetZoneAllowSmartScreenIE

#### <a name="windows10generalconfigurationinternetexplorerlockeddownintranetzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerLockedDownIntranetZoneJavaPermissions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/LockedDownIntranetJavaPermissions

#### <a name="windows10generalconfigurationinternetexplorerlockeddownlocalmachinezonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerLockedDownLocalMachineZoneJavaPermissions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/LockedDownLocalMachineZoneJavaPermissions

#### <a name="windows10generalconfigurationinternetexplorerlockeddownrestrictedzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerLockedDownRestrictedZoneJavaPermissions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/LockedDownRestrictedSitesZoneJavaPermissions

#### <a name="windows10generalconfigurationinternetexplorerlockeddownrestrictedzonesmartscreen"></a>Windows10GeneralConfiguration.InternetExplorerLockedDownRestrictedZoneSmartScreen 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/LockedDownRestrictedSitesZoneAllowSmartScreenIE

#### <a name="windows10generalconfigurationinternetexplorerlockeddowntrustedzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerLockedDownTrustedZoneJavaPermissions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/LockedDownTrustedSitesZoneJavaPermissions

#### <a name="windows10generalconfigurationinternetexplorerpreventmanagingsmartscreenfilter"></a>Windows10GeneralConfiguration.InternetExplorerPreventManagingSmartScreenFilter 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/PreventManagingSmartScreenFilter

#### <a name="windows10generalconfigurationinternetexplorerpreventperuserinstallationofactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerPreventPerUserInstallationOfActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/PreventPerUserInstallationOfActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerprocessesconsistentmimehandling"></a>Windows10GeneralConfiguration.InternetExplorerProcessesConsistentMimeHandling 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/ConsistentMimeHandlingInternetExplorerProcesses

#### <a name="windows10generalconfigurationinternetexplorerprocessesmimesniffingsafetyfeature"></a>Windows10GeneralConfiguration.InternetExplorerProcessesMimeSniffingSafetyFeature 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/MimeSniffingSafetyFeatureInternetExplorerProcesses

#### <a name="windows10generalconfigurationinternetexplorerprocessesmkprotocolsecurityrestriction"></a>Windows10GeneralConfiguration.InternetExplorerProcessesMKProtocolSecurityRestriction 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/MKProtocolSecurityRestrictionInternetExplorerProcesses

#### <a name="windows10generalconfigurationinternetexplorerprocessesnotificationbar"></a>Windows10GeneralConfiguration.InternetExplorerProcessesNotificationBar 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/NotificationBarInternetExplorerProcesses

#### <a name="windows10generalconfigurationinternetexplorerprocessesprotectionfromzoneelevation"></a>Windows10GeneralConfiguration.InternetExplorerProcessesProtectionFromZoneElevation 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/ProtectionFromZoneElevationInternetExplorerProcesses

#### <a name="windows10generalconfigurationinternetexplorerprocessesrestrictactivexinstall"></a>Windows10GeneralConfiguration.InternetExplorerProcessesRestrictActiveXInstall 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/RestrictActiveXInstallInternetExplorerProcesses

#### <a name="windows10generalconfigurationinternetexplorerprocessesrestrictfiledownload"></a>Windows10GeneralConfiguration.InternetExplorerProcessesRestrictFileDownload 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/RestrictFileDownloadInternetExplorerProcesses

#### <a name="windows10generalconfigurationinternetexplorerprocessesscriptedwindowsecurityrestrictions"></a>Windows10GeneralConfiguration.InternetExplorerProcessesScriptedWindowSecurityRestrictions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/ScriptedWindowSecurityRestrictionsInternetExplorerProcesses

#### <a name="windows10generalconfigurationinternetexplorerremoverunthistimebuttonforoutdatedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRemoveRunThisTimeButtonForOutdatedActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RemoveRunThisTimeButtonForOutdatedActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneaccesstodatasources"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneAccessToDataSources 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowAccessToDataSources

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneactivescripting"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneActiveScripting 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowActiveScripting

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneallowonlyapproveddomainstouseactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneAllowOnlyApprovedDomainsToUseActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowOnlyApprovedDomainsToUseActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneallowonlyapproveddomainstousetdcactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneAllowOnlyApprovedDomainsToUseTdcActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneallowvbscripttorun"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneAllowVBScriptToRun 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowVBScriptToRunInInternetExplorer

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneautomaticpromptforfiledownloads"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneAutomaticPromptForFileDownloads 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowAutomaticPromptingForFileDownloads

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonebinaryandscriptbehaviors"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneBinaryAndScriptBehaviors 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowBinaryAndScriptBehaviors

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonecopyandpasteviascript"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneCopyAndPasteViaScript 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowCopyPasteViaScript

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonecrosssitescriptingfilter"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneCrossSiteScriptingFilter 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneEnableCrossSiteScriptingFilter

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDoNotRunAntimalwareAgainstActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneDoNotRunAntimalwareAgainstActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedotnetframeworkreliantcomponents"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDotNetFrameworkReliantComponents 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowNETFrameworkReliantComponents

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedownloadsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDownloadSignedActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/RestrictedSitesZoneDownloadSignedActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedownloadunsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDownloadUnsignedActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneDownloadUnsignedActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedraganddroporcopyandpastefiles"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDragAndDropOrCopyAndPasteFiles 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowDragAndDropCopyAndPasteFiles

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedragcontentfromdifferentdomainsacrosswindows"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDragContentFromDifferentDomainsAcrossWindows 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedragcontentfromdifferentdomainswithinwindows"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDragContentFromDifferentDomainsWithinWindows 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonefiledownloads"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneFileDownloads 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowFileDownloads

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneincludelocalpathwhenuploadingfilestoserver"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneIncludeLocalPathWhenUploadingFilesToServer 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneIncludeLocalPathWhenUploadingFilesToServer

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneInitializeAndScriptActiveXControlsNotMarkedAsSafe 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneInitializeAndScriptActiveXControls

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneJavaPermissions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/RestrictedSitesZoneJavaPermissions

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonelaunchapplicationsandfilesinaniframe"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneLaunchApplicationsAndFilesInAnIFrame 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/RestrictedSitesZoneLaunchingApplicationsAndFilesInIFRAME

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonelessprivilegedsites"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneLessPrivilegedSites 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowLessPrivilegedSites

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneloadingofxamlfiles"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneLoadingOfXamlFiles 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowLoadingOfXAMLFiles

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonelogonoptions"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneLogonOptions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneLogonOptions

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonemetarefresh"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneMetaRefresh 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowMETAREFRESH

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonenavigatewindowsandframesacrossdifferentdomains"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneNavigateWindowsAndFramesAcrossDifferentDomains 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneNavigateWindowsAndFrames

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonepopupblocker"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZonePopupBlocker 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/RestrictedSitesZoneUsePopupBlocker

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneProtectedMode 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneTurnOnProtectedMode

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonerunactivexcontrolsandplugins"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneRunActiveXControlsAndPlugins 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneRunActiveXControlsAndPlugins

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonerundotnetframeworkreliantcomponentssignedwithauthenticode"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneRunDotNetFrameworkReliantComponentsSignedWithAuthenticode 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneRunNETFrameworkReliantComponentsSignedWithAuthenticode

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptactivexcontrolsmarkedsafeforscripting"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneScriptActiveXControlsMarkedSafeForScripting 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneScriptActiveXControlsMarkedSafeForScripting

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptingofjavaapplets"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneScriptingOfJavaApplets 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneScriptingOfJavaApplets

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptingofwebbrowsercontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneScriptingOfWebBrowserControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowScriptingOfInternetExplorerWebBrowserControls

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptinitiatedwindows"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneScriptInitiatedWindows 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowScriptInitiatedWindows

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptlets"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneScriptlets 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowScriptlets

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonesecuritywarningforpotentiallyunsafefiles"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneSecurityWarningForPotentiallyUnsafeFiles 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneShowSecurityWarningForPotentiallyUnsafeFiles

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzonesmartscreen"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneSmartScreen 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowSmartScreenIE

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneupdatestostatusbarviascript"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneUpdatesToStatusBarViaScript 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowUpdatesToStatusBarViaScript

#### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneuserdatapersistence"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneUserDataPersistence 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/RestrictedSitesZoneAllowUserDataPersistence

#### <a name="windows10generalconfigurationinternetexplorersecuritysettingscheck"></a>Windows10GeneralConfiguration.InternetExplorerSecuritySettingsCheck 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/DisableSecuritySettingsCheck

#### <a name="windows10generalconfigurationinternetexplorersecurityzonesuseonlymachinesettings"></a>Windows10GeneralConfiguration.InternetExplorerSecurityZonesUseOnlyMachineSettings 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/SecurityZonesUseOnlyMachineSettings

#### <a name="windows10generalconfigurationinternetexplorersoftwarewhensignatureisinvalid"></a>Windows10GeneralConfiguration.InternetExplorerSoftwareWhenSignatureIsInvalid 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/AllowSoftwareWhenSignatureIsInvalid

#### <a name="windows10generalconfigurationinternetexplorertrustedzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerTrustedZoneDoNotRunAntimalwareAgainstActiveXControls 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/TrustedSitesZoneDoNotRunAntimalwareAgainstActiveXControls

#### <a name="windows10generalconfigurationinternetexplorertrustedzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration.InternetExplorerTrustedZoneInitializeAndScriptActiveXControlsNotMarkedAsSafe 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/TrustedSitesZoneInitializeAndScriptActiveXControls

#### <a name="windows10generalconfigurationinternetexplorertrustedzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerTrustedZoneJavaPermissions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/InternetExplorer/TrustedSitesZoneJavaPermissions

#### <a name="windows10generalconfigurationinternetexploreruseactivexinstallerservice"></a>Windows10GeneralConfiguration.InternetExplorerUseActiveXInstallerService 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/SpecifyUseOfActiveXInstallerService

#### <a name="windows10generalconfigurationinternetexplorerusersaddingsites"></a>Windows10GeneralConfiguration.InternetExplorerUsersAddingSites 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/DoNotAllowUsersToAddSites

#### <a name="windows10generalconfigurationinternetexploreruserschangingpolicies"></a>Windows10GeneralConfiguration.InternetExplorerUsersChangingPolicies 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/InternetExplorer/DoNotAllowUsersToChangePolicies

#### <a name="windows10generalconfigurationinternetsharingblocked"></a>Windows10GeneralConfiguration.InternetSharingBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WiFi/AllowInternetSharing

#### <a name="windows10generalconfigurationlocationservicesblocked"></a>Windows10GeneralConfiguration.LocationServicesBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/System/AllowLocation

#### <a name="windows10generalconfigurationlockscreenallowtimeoutconfiguration"></a>Windows10GeneralConfiguration.LockScreenAllowTimeoutConfiguration 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/AllowScreenTimeoutWhileLockedUser/Config

#### <a name="windows10generalconfigurationlockscreenblockactioncenternotifications"></a>Windows10GeneralConfiguration.LockScreenBlockActionCenterNotifications 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/AboveLock/AllowActionCenterNotifications

#### <a name="windows10generalconfigurationlockscreenblockcortana"></a>Windows10GeneralConfiguration.LockScreenBlockCortana 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/AboveLock/AllowCortanaAboveLock

#### <a name="windows10generalconfigurationlockscreenblocktoastnotifications"></a>Windows10GeneralConfiguration.LockScreenBlockToastNotifications 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/AboveLock/AllowToasts

#### <a name="windows10generalconfigurationlockscreencamera"></a>Windows10GeneralConfiguration.LockScreenCamera 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/PreventEnablingLockScreenCamera

#### <a name="windows10generalconfigurationlockscreenhidenetworkselectionui"></a>Windows10GeneralConfiguration.LockScreenHideNetworkSelectionUI 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsLogon/DontDisplayNetworkSelectionUI

#### <a name="windows10generalconfigurationlockscreenslideshow"></a>Windows10GeneralConfiguration.LockScreenSlideShow 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/PreventLockScreenSlideShow

#### <a name="windows10generalconfigurationlockscreentimeoutinseconds"></a>Windows10GeneralConfiguration.LockScreenTimeoutInSeconds 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/ScreenTimeoutWhileLocked

#### <a name="windows10generalconfigurationlogonblockfastuserswitching"></a>Windows10GeneralConfiguration.LogonBlockFastUserSwitching 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsLogon/HideFastUserSwitching

#### <a name="windows10generalconfigurationmessagingblockmms"></a>Windows10GeneralConfiguration.MessagingBlockMMS 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Messaging/AllowMMS

#### <a name="windows10generalconfigurationmessagingblockrichcommunicationservices"></a>Windows10GeneralConfiguration.MessagingBlockRichCommunicationServices 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Messaging/AllowRCS

#### <a name="windows10generalconfigurationmessagingblocksync"></a>Windows10GeneralConfiguration.MessagingBlockSync 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Messaging/AllowMessageSync

#### <a name="windows10generalconfigurationmicrosoftaccountblocked"></a>Windows10GeneralConfiguration.MicrosoftAccountBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Accounts/AllowMicrosoftAccountConnection

#### <a name="windows10generalconfigurationmicrosoftaccountblocksettingssync"></a>Windows10GeneralConfiguration.MicrosoftAccountBlockSettingsSync 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowSyncMySettings

#### <a name="windows10generalconfigurationmicrosoftaccountsigninassistantsettings"></a>Windows10GeneralConfiguration.MicrosoftAccountSignInAssistantSettings 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Accounts  
**Offset URI**: /AllowMicrosoftAccountSignInAssistant

#### <a name="windows10generalconfigurationnetworkproxyapplysettingsdevicewide"></a>Windows10GeneralConfiguration.NetworkProxyApplySettingsDeviceWide 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/NetworkProxy  
**Offset URI**: /ProxySettingsPerUser

#### <a name="windows10generalconfigurationnetworkproxyautomaticconfigurationurl"></a>Windows10GeneralConfiguration.NetworkProxyAutomaticConfigurationUrl 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/NetworkProxy  
**Posun identifikátoru URI**: /SetupScriptUrl

#### <a name="windows10generalconfigurationnetworkproxydisableautodetect"></a>Windows10GeneralConfiguration.NetworkProxyDisableAutoDetect 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/NetworkProxy  
**Posun identifikátoru URI**: /AutoDetect

#### <a name="windows10generalconfigurationnetworkproxyserver"></a>Windows10GeneralConfiguration.NetworkProxyServer 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/NetworkProxy  
**Posun identifikátoru URI**: / proxyaddress, /Exceptions a /UseProxyForLocalAddresses

#### <a name="windows10generalconfigurationnfcblocked"></a>Windows10GeneralConfiguration.NfcBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Connectivity/AllowNFC

#### <a name="windows10generalconfigurationonedrivedisablefilesync"></a>Windows10GeneralConfiguration.OneDriveDisableFileSync 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/System/DisableOneDriveFileSync

#### <a name="windows10generalconfigurationpasswordblocksimple"></a>Windows10GeneralConfiguration.PasswordBlockSimple 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/AllowSimpleDevicePassword

#### <a name="windows10generalconfigurationpasswordexpirationdays"></a>Windows10GeneralConfiguration.PasswordExpirationDays 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/DevicePasswordExpiration

#### <a name="windows10generalconfigurationpasswordminimumageindays"></a>Windows10GeneralConfiguration.PasswordMinimumAgeInDays 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/MinimumPasswordAge

#### <a name="windows10generalconfigurationpasswordminimumcharactersetcount"></a>Windows10GeneralConfiguration.PasswordMinimumCharacterSetCount 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/MinDevicePasswordComplexCharacters

#### <a name="windows10generalconfigurationpasswordminimumlength"></a>Windows10GeneralConfiguration.PasswordMinimumLength 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/MinDevicePasswordLength

#### <a name="windows10generalconfigurationpasswordminutesofinactivitybeforescreentimeout"></a>Windows10GeneralConfiguration.PasswordMinutesOfInactivityBeforeScreenTimeout 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/MaxInactivityTimeDeviceLock

#### <a name="windows10generalconfigurationpasswordpreviouspasswordblockcount"></a>Windows10GeneralConfiguration.PasswordPreviousPasswordBlockCount 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/DevicePasswordHistory

#### <a name="windows10generalconfigurationpasswordrequired"></a>Windows10GeneralConfiguration.PasswordRequired 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/DevicePasswordEnabled

#### <a name="windows10generalconfigurationpasswordrequiredtype"></a>Windows10GeneralConfiguration.PasswordRequiredType 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/AlphanumericDevicePasswordRequired

#### <a name="windows10generalconfigurationpasswordrequirewhenresumefromidlestate"></a>Windows10GeneralConfiguration.PasswordRequireWhenResumeFromIdleState 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/AllowIdleReturnWithoutPassword

#### <a name="windows10generalconfigurationpasswordsigninfailurecountbeforefactoryreset"></a>Windows10GeneralConfiguration.PasswordSignInFailureCountBeforeFactoryReset 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceLock/MaxDevicePasswordFailedAttempts

#### <a name="windows10generalconfigurationpersonalizationdesktopimageurl"></a>Windows10GeneralConfiguration.PersonalizationDesktopImageUrl 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Personalization  
**Posun identifikátoru URI**: /DesktopImageUrl

#### <a name="windows10generalconfigurationpersonalizationlockscreenimageurl"></a>Windows10GeneralConfiguration.PersonalizationLockScreenImageUrl 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Personalization  
**Posun identifikátoru URI**: /LockScreenImageUrl

#### <a name="windows10generalconfigurationpowerrequirepasswordonwakewhileonbattery"></a>Windows10GeneralConfiguration.PowerRequirePasswordOnWakeWhileOnBattery 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Power/RequirePasswordWhenComputerWakesOnBattery

#### <a name="windows10generalconfigurationpowerrequirepasswordonwakewhilepluggedin"></a>Windows10GeneralConfiguration.PowerRequirePasswordOnWakeWhilePluggedIn 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Power/RequirePasswordWhenComputerWakesPluggedIn

#### <a name="windows10generalconfigurationpowerstandbystateswhensleepingwhileonbattery"></a>Windows10GeneralConfiguration.PowerStandbyStatesWhenSleepingWhileOnBattery 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Power/AllowStandbyStatesWhenSleepingOnBattery

#### <a name="windows10generalconfigurationpowerstandbystateswhensleepingwhilepluggedin"></a>Windows10GeneralConfiguration.PowerStandbyStatesWhenSleepingWhilePluggedIn 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Power/AllowStandbyWhenSleepingPluggedIn

#### <a name="windows10generalconfigurationpreventinstallationofmatchingdeviceids"></a>windows10generalconfiguration.preventInstallationOfMatchingDeviceIDs 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceInstallation/PreventInstallationOfMatchingDeviceIDs

#### <a name="windows10generalconfigurationpreventinstallationofmatchingdevicesetupclasses"></a>windows10generalconfiguration.preventInstallationOfMatchingDeviceSetupClasses 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeviceInstallation/PreventInstallationOfMatchingDeviceSetupClasses

#### <a name="windows10generalconfigurationprinterblockaddition"></a>Windows10GeneralConfiguration.PrinterBlockAddition 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Education/PreventAddingNewPrinters

#### <a name="windows10generalconfigurationprinterdefaultname"></a>Windows10GeneralConfiguration.PrinterDefaultName 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Education/DefaultPrinterName

#### <a name="windows10generalconfigurationprinternames"></a>Windows10GeneralConfiguration.PrinterNames 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Education/PrinterNames

#### <a name="windows10generalconfigurationprivacyadvertisingid"></a>Windows10GeneralConfiguration.PrivacyAdvertisingId 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Privacy/DisableAdvertisingID

#### <a name="windows10generalconfigurationprivacyautoacceptpairingandconsentprompts"></a>Windows10GeneralConfiguration.PrivacyAutoAcceptPairingAndConsentPrompts 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Offset URI**: /Config/Privacy/AllowAutoAcceptPairingAndPrivacyConsentPrompts

#### <a name="windows10generalconfigurationprivacyblockactivityfeed"></a>Windows10GeneralConfiguration.PrivacyBlockActivityFeed 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Privacy/EnableActivityFeed

#### <a name="windows10generalconfigurationprivacyblockinputpersonalization"></a>Windows10GeneralConfiguration.PrivacyBlockInputPersonalization 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Privacy/AllowInputPersonalization

#### <a name="windows10generalconfigurationprivacyblockpublishuseractivities"></a>Windows10GeneralConfiguration.PrivacyBlockPublishUserActivities 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Privacy/PublishUserActivities

#### <a name="windows10generalconfigurationsafesearchfilter"></a>Windows10GeneralConfiguration.SafeSearchFilter 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Search/SafeSearchPermissions

#### <a name="windows10generalconfigurationscreencaptureblocked"></a>Windows10GeneralConfiguration.ScreenCaptureBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowScreenCapture

#### <a name="windows10generalconfigurationsearchblockdiacritics"></a>Windows10GeneralConfiguration.SearchBlockDiacritics 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Search/AllowUsingDiacritics

#### <a name="windows10generalconfigurationsearchblockwebresults"></a>Windows10GeneralConfiguration.SearchBlockWebResults 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Search/DoNotUseWebResults

#### <a name="windows10generalconfigurationsearchdisableautolanguagedetection"></a>Windows10GeneralConfiguration.SearchDisableAutoLanguageDetection 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Search/AlwaysUseAutoLangDetection

#### <a name="windows10generalconfigurationsearchdisableindexerbackoff"></a>Windows10GeneralConfiguration.SearchDisableIndexerBackoff 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Search/DisableBackoff

#### <a name="windows10generalconfigurationsearchdisableindexingencrypteditems"></a>Windows10GeneralConfiguration.SearchDisableIndexingEncryptedItems 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Search/AllowIndexingEncryptedStoresOrItems

#### <a name="windows10generalconfigurationsearchdisableindexingremovabledrive"></a>Windows10GeneralConfiguration.SearchDisableIndexingRemovableDrive 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Search/DisableRemovableDriveIndexing

#### <a name="windows10generalconfigurationsearchdisablelocation"></a>Windows10GeneralConfiguration.SearchDisableLocation 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Search/AllowSearchToUseLocation

#### <a name="windows10generalconfigurationsearchdisableuselocation"></a>Windows10GeneralConfiguration.SearchDisableUseLocation 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Search/AllowSearchToUseLocation

#### <a name="windows10generalconfigurationsearchenableautomaticindexsizemanangement"></a>Windows10GeneralConfiguration.SearchEnableAutomaticIndexSizeManangement 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Search/PreventIndexingLowDiskSpaceMB

#### <a name="windows10generalconfigurationsearchenableremotequeries"></a>Windows10GeneralConfiguration.SearchEnableRemoteQueries 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Search/PreventRemoteQueries

#### <a name="windows10generalconfigurationsecurityblockazureadjoineddevicesautoencryption"></a>Windows10GeneralConfiguration.SecurityBlockAzureADJoinedDevicesAutoEncryption 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Security/PreventAutomaticDeviceEncryptionForAzureADJoinedDevices

#### <a name="windows10generalconfigurationsettingsblockaccountspage"></a>Windows10GeneralConfiguration.SettingsBlockAccountsPage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/PageVisibilityList

#### <a name="windows10generalconfigurationsettingsblockaddprovisioningpackage"></a>Windows10GeneralConfiguration.SettingsBlockAddProvisioningPackage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Security/AllowAddProvisioningPackage

#### <a name="windows10generalconfigurationsettingsblockappspage"></a>Windows10GeneralConfiguration.SettingsBlockAppsPage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/PageVisibilityList

#### <a name="windows10generalconfigurationsettingsblockchangelanguage"></a>Windows10GeneralConfiguration.SettingsBlockChangeLanguage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/AllowLanguage

#### <a name="windows10generalconfigurationsettingsblockchangepowersleep"></a>Windows10GeneralConfiguration.SettingsBlockChangePowerSleep 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/AllowPowerSleep

#### <a name="windows10generalconfigurationsettingsblockchangeregion"></a>Windows10GeneralConfiguration.SettingsBlockChangeRegion 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/AllowRegion

#### <a name="windows10generalconfigurationsettingsblockchangesystemtime"></a>Windows10GeneralConfiguration.SettingsBlockChangeSystemTime 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/AllowDateTime

#### <a name="windows10generalconfigurationsettingsblockdevicespage"></a>Windows10GeneralConfiguration.SettingsBlockDevicesPage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/PageVisibilityList

#### <a name="windows10generalconfigurationsettingsblockeaseofaccesspage"></a>Windows10GeneralConfiguration.SettingsBlockEaseOfAccessPage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/PageVisibilityList

#### <a name="windows10generalconfigurationsettingsblockeditdevicename"></a>Windows10GeneralConfiguration.SettingsBlockEditDeviceName 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/AllowEditDeviceName

#### <a name="windows10generalconfigurationsettingsblockgamingpage"></a>Windows10GeneralConfiguration.SettingsBlockGamingPage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/PageVisibilityList

#### <a name="windows10generalconfigurationsettingsblocknetworkinternetpage"></a>Windows10GeneralConfiguration.SettingsBlockNetworkInternetPage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/PageVisibilityList

#### <a name="windows10generalconfigurationsettingsblockpersonalizationpage"></a>Windows10GeneralConfiguration.SettingsBlockPersonalizationPage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/PageVisibilityList

#### <a name="windows10generalconfigurationsettingsblockprivacypage"></a>Windows10GeneralConfiguration.SettingsBlockPrivacyPage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/PageVisibilityList

#### <a name="windows10generalconfigurationsettingsblockremoveprovisioningpackage"></a>Windows10GeneralConfiguration.SettingsBlockRemoveProvisioningPackage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Security/AllowRemoveProvisioningPackage

#### <a name="windows10generalconfigurationsettingsblocksystempage"></a>Windows10GeneralConfiguration.SettingsBlockSystemPage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/PageVisibilityList

#### <a name="windows10generalconfigurationsettingsblocktimelanguagepage"></a>Windows10GeneralConfiguration.SettingsBlockTimeLanguagePage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/PageVisibilityList

#### <a name="windows10generalconfigurationsettingsblockupdatesecuritypage"></a>Windows10GeneralConfiguration.SettingsBlockUpdateSecurityPage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Settings/PageVisibilityList

#### <a name="windows10generalconfigurationshareduserappdataallowed"></a>Windows10GeneralConfiguration.SharedUserAppDataAllowed 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ApplicationManagement/AllowSharedUserAppData

#### <a name="windows10generalconfigurationsmartscreenblockpromptoverride"></a>Windows10GeneralConfiguration.SmartScreenBlockPromptOverride 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/PreventSmartScreenPromptOverride

#### <a name="windows10generalconfigurationsmartscreenblockpromptoverrideforfiles"></a>Windows10GeneralConfiguration.SmartScreenBlockPromptOverrideForFiles 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/PreventSmartScreenPromptOverrideForFiles

#### <a name="windows10generalconfigurationsmartscreenenableappinstallcontrol"></a>Windows10GeneralConfiguration.SmartScreenEnableAppInstallControl 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/SmartScreen/EnableAppInstallControl

#### <a name="windows10generalconfigurationstartblockunpinningappsfromtaskbar"></a>Windows10GeneralConfiguration.StartBlockUnpinningAppsFromTaskbar 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/NoPinningToTaskbar

#### <a name="windows10generalconfigurationstartmenuapplistvisibility"></a>Windows10GeneralConfiguration.StartMenuAppListVisibility 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HideAppList

#### <a name="windows10generalconfigurationstartmenuhidechangeaccountsettings"></a>Windows10GeneralConfiguration.StartMenuHideChangeAccountSettings 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HideChangeAccountSettings

#### <a name="windows10generalconfigurationstartmenuhidefrequentlyusedapps"></a>Windows10GeneralConfiguration.StartMenuHideFrequentlyUsedApps 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HideFrequentlyUsedApps

#### <a name="windows10generalconfigurationstartmenuhidehibernate"></a>Windows10GeneralConfiguration.StartMenuHideHibernate 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HideHibernate

#### <a name="windows10generalconfigurationstartmenuhidelock"></a>Windows10GeneralConfiguration.StartMenuHideLock 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HideLock

#### <a name="windows10generalconfigurationstartmenuhidepowerbutton"></a>Windows10GeneralConfiguration.StartMenuHidePowerButton 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HidePowerButton

#### <a name="windows10generalconfigurationstartmenuhiderecentjumplists"></a>Windows10GeneralConfiguration.StartMenuHideRecentJumpLists 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HideRecentJumplists

#### <a name="windows10generalconfigurationstartmenuhiderecentlyaddedapps"></a>Windows10GeneralConfiguration.StartMenuHideRecentlyAddedApps 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HideRecentlyAddedApps

#### <a name="windows10generalconfigurationstartmenuhiderestartoptions"></a>Windows10GeneralConfiguration.StartMenuHideRestartOptions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HideRestart

#### <a name="windows10generalconfigurationstartmenuhideshutdown"></a>Windows10GeneralConfiguration.StartMenuHideShutDown 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HideShutDown

#### <a name="windows10generalconfigurationstartmenuhidesignout"></a>Windows10GeneralConfiguration.StartMenuHideSignOut 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HideSignOut

#### <a name="windows10generalconfigurationstartmenuhidesleep"></a>Windows10GeneralConfiguration.StartMenuHideSleep 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HideSleep

#### <a name="windows10generalconfigurationstartmenuhideswitchaccount"></a>Windows10GeneralConfiguration.StartMenuHideSwitchAccount 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HideSwitchAccount

#### <a name="windows10generalconfigurationstartmenuhideusertile"></a>Windows10GeneralConfiguration.StartMenuHideUserTile 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/HideUserTile

#### <a name="windows10generalconfigurationstartmenulayoutedgeassetsxml"></a>Windows10GeneralConfiguration.StartMenuLayoutEdgeAssetsXml 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/ImportEdgeAssets

#### <a name="windows10generalconfigurationstartmenulayoutxml"></a>Windows10GeneralConfiguration.StartMenuLayoutXml 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/StartLayout

#### <a name="windows10generalconfigurationstartmenumode"></a>Windows10GeneralConfiguration.StartMenuMode 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/ForceStartSize

#### <a name="windows10generalconfigurationstartmenupinnedfolderdocuments"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderDocuments 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/AllowPinnedFolderDocuments

#### <a name="windows10generalconfigurationstartmenupinnedfolderdownloads"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderDownloads 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/AllowPinnedFolderDownloads

#### <a name="windows10generalconfigurationstartmenupinnedfolderfileexplorer"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderFileExplorer 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/AllowPinnedFolderFileExplorer

#### <a name="windows10generalconfigurationstartmenupinnedfolderhomegroup"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderHomeGroup 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/AllowPinnedFolderHomeGroup

#### <a name="windows10generalconfigurationstartmenupinnedfoldermusic"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderMusic 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/AllowPinnedFolderMusic

#### <a name="windows10generalconfigurationstartmenupinnedfoldernetwork"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderNetwork 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/AllowPinnedFolderNetwork

#### <a name="windows10generalconfigurationstartmenupinnedfolderpersonalfolder"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderPersonalFolder 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/AllowPinnedFolderPersonalFolder

#### <a name="windows10generalconfigurationstartmenupinnedfolderpictures"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderPictures 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/AllowPinnedFolderPictures

#### <a name="windows10generalconfigurationstartmenupinnedfoldersettings"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderSettings 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/AllowPinnedFolderSettings

#### <a name="windows10generalconfigurationstartmenupinnedfoldervideos"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderVideos 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Start/AllowPinnedFolderVideos

#### <a name="windows10generalconfigurationstorageblockremovablestorage"></a>Windows10GeneralConfiguration.StorageBlockRemovableStorage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/System/AllowStorageCard

#### <a name="windows10generalconfigurationstoragerequiremobiledeviceencryption"></a>Windows10GeneralConfiguration.StorageRequireMobileDeviceEncryption 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Security/RequireDeviceEncryption

#### <a name="windows10generalconfigurationstoragerestrictappdatatosystemvolume"></a>Windows10GeneralConfiguration.StorageRestrictAppDataToSystemVolume 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ApplicationManagement/RestrictAppDataToSystemVolume

#### <a name="windows10generalconfigurationstoragerestrictappinstalltosystemvolume"></a>Windows10GeneralConfiguration.StorageRestrictAppInstallToSystemVolume 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ApplicationManagement/RestrictAppToSystemVolume

#### <a name="windows10generalconfigurationsystembootstartdriverinitialization"></a>Windows10GeneralConfiguration.SystemBootStartDriverInitialization 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/System/BootStartDriverInitialization

#### <a name="windows10generalconfigurationsystemtelemetryproxyserver"></a>Windows10GeneralConfiguration.SystemTelemetryProxyServer 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/System/TelemetryProxy

#### <a name="windows10generalconfigurationtaskmanagerblockendtask"></a>Windows10GeneralConfiguration.TaskManagerBlockEndTask 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/TaskManager/AllowEndTask

#### <a name="windows10generalconfigurationtenantlockdownrequirenetworkduringoutofboxexperience"></a>Windows10GeneralConfiguration.TenantLockdownRequireNetworkDuringOutOfBoxExperience 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/TenantLockdown  
**Posun identifikátoru URI**: /RequireNetworkInOOBE

#### <a name="windows10generalconfigurationusbblocked"></a>Windows10GeneralConfiguration.UsbBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Connectivity/AllowUSBConnection

#### <a name="windows10generalconfigurationvoicerecordingblocked"></a>Windows10GeneralConfiguration.VoiceRecordingBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowVoiceRecording

#### <a name="windows10generalconfigurationwebrtcblocklocalhostipaddress"></a>Windows10GeneralConfiguration.WebRtcBlockLocalhostIpAddress 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/PreventUsingLocalHostIPAddressForWebRTC

#### <a name="windows10generalconfigurationwifiblockautomaticconnecthotspots"></a>Windows10GeneralConfiguration.WiFiBlockAutomaticConnectHotspots 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WiFi/AllowAutoConnectToWiFiSenseHotspots

#### <a name="windows10generalconfigurationwifiblocked"></a>Windows10GeneralConfiguration.WiFiBlocked 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Wifi/AllowWiFi

#### <a name="windows10generalconfigurationwifiblockmanualconfiguration"></a>Windows10GeneralConfiguration.WiFiBlockManualConfiguration 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WiFi/AllowManualWiFi/Configuration

#### <a name="windows10generalconfigurationwifiscaninterval"></a>Windows10GeneralConfiguration.WiFiScanInterval 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WiFi/WLANScanMode

#### <a name="windows10generalconfigurationwindowslogonlocalusersondomainjoinedcomputers"></a>Windows10GeneralConfiguration.WindowsLogOnLocalUsersOnDomainJoinedComputers 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WindowsLogon/EnumerateLocalUsersOnDomainJoinedComputers

#### <a name="windows10generalconfigurationwindowsspotlightblockconsumerspecificfeatures"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockConsumerSpecificFeatures 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowWindowsConsumerFeatures

#### <a name="windows10generalconfigurationwindowsspotlightblocked"></a>Windows10GeneralConfiguration.WindowsSpotlightBlocked 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowWindowsSpotlight

#### <a name="windows10generalconfigurationwindowsspotlightblockonactioncenter"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockOnActionCenter 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowWindowsSpotlightOnActionCenter

#### <a name="windows10generalconfigurationwindowsspotlightblocktailoredexperiences"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockTailoredExperiences 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowTailoredExperiencesWithDiagnosticData

#### <a name="windows10generalconfigurationwindowsspotlightblockthirdpartynotifications"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockThirdPartyNotifications 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowThirdPartySuggestionsInWindowsSpotlight

#### <a name="windows10generalconfigurationwindowsspotlightblockwelcomeexperience"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockWelcomeExperience 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowWindowsSpotlightWindowsWelcomeExperience

#### <a name="windows10generalconfigurationwindowsspotlightblockwindowstips"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockWindowsTips 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/AllowWindowsTips

#### <a name="windows10generalconfigurationwindowsspotlightconfigureonlockscreen"></a>Windows10GeneralConfiguration.WindowsSpotlightConfigureOnLockScreen 
**Zprostředkovatel kryptografických služeb**: ./User/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Experience/ConfigureWindowsSpotlightOnLockScreen

#### <a name="windows10generalconfigurationwindowsstoreblockautoupdate"></a>Windows10GeneralConfiguration.WindowsStoreBlockAutoUpdate 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ApplicationManagement/AllowAppStoreAutoUpdate

#### <a name="windows10generalconfigurationwindowsstoreblocked"></a>Windows10GeneralConfiguration.WindowsStoreBlocked 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ApplicationManagement/AllowStore

#### <a name="windows10generalconfigurationwindowsstoreenableprivatestoreonly"></a>Windows10GeneralConfiguration.WindowsStoreEnablePrivateStoreOnly 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ApplicationManagement/RequirePrivateStoreOnly

#### <a name="windows10generalconfigurationwirelessdisplayblockprojectiontothisdevice"></a>Windows10GeneralConfiguration.WirelessDisplayBlockProjectionToThisDevice 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WirelessDisplay/AllowProjectionToPC

#### <a name="windows10generalconfigurationwirelessdisplayblockuserinputfromreceiver"></a>Windows10GeneralConfiguration.WirelessDisplayBlockUserInputFromReceiver 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WirelessDisplay/AllowUserInputFromWirelessDisplayReceiver

#### <a name="windows10generalconfigurationwirelessdisplayrequirepinforpairing"></a>Windows10GeneralConfiguration.WirelessDisplayRequirePinForPairing 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/WirelessDisplay/RequirePINForPairing

#### <a name="windows10networkboundaryconfigurationwindowsnetworkisolationpolicy"></a>Windows10NetworkBoundaryConfiguration.WindowsNetworkIsolationPolicy 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/NetworkIsolation/EnterpriseCloudResources /Config/NetworkIsolation/EnterpriseIPRange, /Config/NetworkIsolation/EnterpriseIPRangesAreAuthoritative, / config/NetworkIsolation / EnterpriseInternalProxyServers /Config/NetworkIsolation/EnterpriseNetworkDomainNames /Config/NetworkIsolation/EnterpriseProxyServers, /Config/NetworkIsolation/EnterpriseProxyServersAreAuthoritative, / config/NetworkIsolation / NeutralResources

#### <a name="windows10policyoverrideconfigurationprefermdmovergrouppolicy"></a>Windows10PolicyOverrideConfiguration.PreferMdmOverGroupPolicy 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/ControlPolicyConflict/MDMWinsOverGP

#### <a name="windows10secureassessmentconfigurationallowprinting"></a>Windows10SecureAssessmentConfiguration.AllowPrinting 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SecureAssessment  
**Posun identifikátoru URI**: /RequirePrinting

#### <a name="windows10secureassessmentconfigurationallowscreencapture"></a>Windows10SecureAssessmentConfiguration.AllowScreenCapture 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SecureAssessment  
**Posun identifikátoru URI**: /AllowScreenMonitoring

#### <a name="windows10secureassessmentconfigurationallowtextsuggestion"></a>Windows10SecureAssessmentConfiguration.AllowTextSuggestion 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SecureAssessment  
**Posun identifikátoru URI**: /AllowTextSuggestions

#### <a name="windows10secureassessmentconfigurationconfigurationaccount"></a>Windows10SecureAssessmentConfiguration.ConfigurationAccount 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SecureAssessment  
**Offset URI**: /TesterAccount

#### <a name="windows10secureassessmentconfigurationconfigurationaccounttype"></a>Windows10SecureAssessmentConfiguration.ConfigurationAccountType 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SecureAssessment  
**Offset URI**: /TesterAccount

#### <a name="windows10secureassessmentconfigurationlaunchuri"></a>Windows10SecureAssessmentConfiguration.LaunchUri 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SecureAssessment  
**Posun identifikátoru URI**: /LaunchURI

#### <a name="windows10teamgeneralconfigurationazureoperationalinsightsblocktelemetry"></a>Windows10TeamGeneralConfiguration.AzureOperationalInsightsBlockTelemetry 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / MOMAgent/ID pracovního prostoru a/MOMAgent/WorkspaceKey

#### <a name="windows10teamgeneralconfigurationazureoperationalinsightsworkspaceid"></a>Windows10TeamGeneralConfiguration.AzureOperationalInsightsWorkspaceId 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / MOMAgent/ID pracovního prostoru

#### <a name="windows10teamgeneralconfigurationazureoperationalinsightsworkspacekey"></a>Windows10TeamGeneralConfiguration.AzureOperationalInsightsWorkspaceKey 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / MOMAgent/WorkspaceKey

#### <a name="windows10teamgeneralconfigurationconnectappblockautolaunch"></a>Windows10TeamGeneralConfiguration.ConnectAppBlockAutoLaunch 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: /InBoxApps/Connect/AutoLaunch

#### <a name="windows10teamgeneralconfigurationdeviceaccountblockexchangeservices"></a>Windows10TeamGeneralConfiguration.DeviceAccountBlockExchangeServices 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / DeviceAccount/e-mailu

#### <a name="windows10teamgeneralconfigurationdeviceaccountemailaddress"></a>Windows10TeamGeneralConfiguration.DeviceAccountEmailAddress 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / DeviceAccount/e-mailu

#### <a name="windows10teamgeneralconfigurationdeviceaccountexchangeserveraddress"></a>Windows10TeamGeneralConfiguration.DeviceAccountExchangeServerAddress 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / DeviceAccount/ExchangeServer

#### <a name="windows10teamgeneralconfigurationdeviceaccountrequirepasswordrotation"></a>Windows10TeamGeneralConfiguration.DeviceAccountRequirePasswordRotation 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / DeviceAccount/PasswordRotationEnabled

#### <a name="windows10teamgeneralconfigurationdeviceaccountsessioninitiationprotocoladdress"></a>Windows10TeamGeneralConfiguration.DeviceAccountSessionInitiationProtocolAddress 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / DeviceAccount/SipAddress

#### <a name="windows10teamgeneralconfigurationmaintenancewindowblocked"></a>Windows10TeamGeneralConfiguration.MaintenanceWindowBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: /MaintenanceHoursSimple/Hours/Duration a /MaintenanceHoursSimple/Hours/StartTime

#### <a name="windows10teamgeneralconfigurationmaintenancewindowdurationinhours"></a>Windows10TeamGeneralConfiguration.MaintenanceWindowDurationInHours 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: /MaintenanceHoursSimple/Hours/Duration

#### <a name="windows10teamgeneralconfigurationmaintenancewindowstarttime"></a>Windows10TeamGeneralConfiguration.MaintenanceWindowStartTime 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: /MaintenanceHoursSimple/Hours/StartTime

#### <a name="windows10teamgeneralconfigurationmiracastblocked"></a>Windows10TeamGeneralConfiguration.MiracastBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: /InBoxApps/WirelessProjection/Enabled

#### <a name="windows10teamgeneralconfigurationmiracastchannel"></a>Windows10TeamGeneralConfiguration.MiracastChannel 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: InBoxApps/WirelessProjection nebo kanálu

#### <a name="windows10teamgeneralconfigurationmiracastrequirepin"></a>Windows10TeamGeneralConfiguration.MiracastRequirePin 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: /InBoxApps/WirelessProjection/PINRequired

#### <a name="windows10teamgeneralconfigurationsettingsblockmymeetingsandfiles"></a>Windows10TeamGeneralConfiguration.SettingsBlockMyMeetingsAndFiles 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Offset URI**: /Properties/DoNotShowMyMeetingsAndFiles

#### <a name="windows10teamgeneralconfigurationsettingsblocksessionresume"></a>Windows10TeamGeneralConfiguration.SettingsBlockSessionResume 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / vlastnosti/AllowSessionResume

#### <a name="windows10teamgeneralconfigurationsettingsblocksigninsuggestions"></a>Windows10TeamGeneralConfiguration.SettingsBlockSigninSuggestions 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / vlastnosti/DisableSigninSuggestions

#### <a name="windows10teamgeneralconfigurationsettingsdefaultvolume"></a>Windows10TeamGeneralConfiguration.SettingsDefaultVolume 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / vlastnosti/DefaultVolume

#### <a name="windows10teamgeneralconfigurationsettingsscreentimeoutinminutes"></a>Windows10TeamGeneralConfiguration.SettingsScreenTimeoutInMinutes 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / vlastnosti/ScreenTimeout

#### <a name="windows10teamgeneralconfigurationsettingssessiontimeoutinminutes"></a>Windows10TeamGeneralConfiguration.SettingsSessionTimeoutInMinutes 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / vlastnosti/SessionTimeout

#### <a name="windows10teamgeneralconfigurationsettingssleeptimeoutinminutes"></a>Windows10TeamGeneralConfiguration.SettingsSleepTimeoutInMinutes 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: / vlastnosti/SleepTimeout

#### <a name="windows10teamgeneralconfigurationwelcomescreenbackgroundimageurl"></a>Windows10TeamGeneralConfiguration.WelcomeScreenBackgroundImageUrl 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: /InBoxApps/Welcome/CurrentBackgroundPath

#### <a name="windows10teamgeneralconfigurationwelcomescreenblockautomaticwakeup"></a>Windows10TeamGeneralConfiguration.WelcomeScreenBlockAutomaticWakeUp 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: /InBoxApps/Welcome/AutoWakeScreen

#### <a name="windows10teamgeneralconfigurationwelcomescreenmeetinginformation"></a>Windows10TeamGeneralConfiguration.WelcomeScreenMeetingInformation 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/SurfaceHub  
**Posun identifikátoru URI**: /InBoxApps/Welcome/MeetingInfoOption

#### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectionoffboardingblob"></a>WindowsDefenderAdvancedThreatProtectionConfiguration.AdvancedThreatProtectionOffboardingBlob 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection  
**Posun identifikátoru URI**: /Offboarding 

#### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectionoffboardingfilename"></a>WindowsDefenderAdvancedThreatProtectionConfiguration.AdvancedThreatProtectionOffboardingFilename
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection  
**Posun identifikátoru URI**: /Offboarding 

#### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectiononboardingblob"></a>WindowsDefenderAdvancedThreatProtectionConfiguration.AdvancedThreatProtectionOnboardingBlob 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection  
**Posun identifikátoru URI**: /Onboarding 

#### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectiononboardingfilename"></a>WindowsDefenderAdvancedThreatProtectionConfiguration.AdvancedThreatProtectionOnboardingFilename 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection  
**Posun identifikátoru URI**: /Onboarding 

#### <a name="windowsdefenderadvancedthreatprotectionconfigurationallowsamplesharing"></a>WindowsDefenderAdvancedThreatProtectionConfiguration.AllowSampleSharing 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection  
**Posun identifikátoru URI**: / Configuration/SampleSharing

#### <a name="windowsdefenderadvancedthreatprotectionconfigurationenableexpeditedtelemetryreporting"></a>WindowsDefenderAdvancedThreatProtectionConfiguration.EnableExpeditedTelemetryReporting 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection  
**Posun identifikátoru URI**: / Configuration/TelemetryReportingFrequency

#### <a name="windowsdeliveryoptimizationconfigurationdeliveryoptimizationmode"></a>WindowsDeliveryOptimizationConfiguration.DeliveryOptimizationMode 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeliveryOptimization/DODownloadMode

#### <a name="windowsidentityprotectionconfigurationenhancedantispoofingforfacialfeaturesenabled"></a>WindowsIdentityProtectionConfiguration.EnhancedAntiSpoofingForFacialFeaturesEnabled 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/PassportForWork  
**Posun identifikátoru URI**: / biometrika/FacialFeaturesUseEnhancedAntiSpoofing

#### <a name="windowsidentityprotectionconfigurationpinexpirationindays"></a>WindowsIdentityProtectionConfiguration.PinExpirationInDays 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/PassportForWork  
**Posun identifikátoru URI**: / {AADTenantId} / zásady/PINComplexity/vypršení platnosti

#### <a name="windowsidentityprotectionconfigurationpinlowercasecharactersusage"></a>WindowsIdentityProtectionConfiguration.PinLowercaseCharactersUsage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/PassportForWork  
**Posun identifikátoru URI**: / {AADTenantId} / zásady/PINComplexity/LowercaseLetters

#### <a name="windowsidentityprotectionconfigurationpinmaximumlength"></a>WindowsIdentityProtectionConfiguration.PinMaximumLength 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/PassportForWork  
**Posun identifikátoru URI**: / {AADTenantId} / zásady/PINComplexity/MaximumPINLength

#### <a name="windowsidentityprotectionconfigurationpinminimumlength"></a>WindowsIdentityProtectionConfiguration.PinMinimumLength 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/PassportForWork  
**Posun identifikátoru URI**: / {AADTenantId} / zásady/PINComplexity/MinimumPINLength

#### <a name="windowsidentityprotectionconfigurationpinpreviousblockcount"></a>WindowsIdentityProtectionConfiguration.PinPreviousBlockCount 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/PassportForWork  
**Posun identifikátoru URI**: / {AADTenantId} / zásady/PINComplexity/historie

#### <a name="windowsidentityprotectionconfigurationpinrecoveryenabled"></a>WindowsIdentityProtectionConfiguration.PinRecoveryEnabled 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/PassportForWork  
**Posun identifikátoru URI**: / {AADTenantId} / Policies/EnablePinRecovery

#### <a name="windowsidentityprotectionconfigurationpinspecialcharactersusage"></a>WindowsIdentityProtectionConfiguration.PinSpecialCharactersUsage 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/PassportForWork  
**Posun identifikátoru URI**: / {AADTenantId} / zásady/PINComplexity/SpecialCharacters

#### <a name="windowsidentityprotectionconfigurationpinuppercasecharactersusage"></a>WindowsIdentityProtectionConfiguration.PinUppercaseCharactersUsage
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/PassportForWork  
**Posun identifikátoru URI**: / {AADTenantId} / zásady/PINComplexity/UppercaseLetters

#### <a name="windowsidentityprotectionconfigurationsecuritydevicerequired"></a>WindowsIdentityProtectionConfiguration.SecurityDeviceRequired 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/PassportForWork  
**Posun identifikátoru URI**: / {AADTenantId} / Policies/RequireSecurityDevice

#### <a name="windowsidentityprotectionconfigurationunlockwithbiometricsenabled"></a>WindowsIdentityProtectionConfiguration.UnlockWithBiometricsEnabled 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/PassportForWork  
**Posun identifikátoru URI**: / biometrika/UseBiometrics

#### <a name="windowsidentityprotectionconfigurationusecertificatesforonpremisesauthenabled"></a>WindowsIdentityProtectionConfiguration.UseCertificatesForOnPremisesAuthEnabled 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/PassportForWork  
**Offset URI**: /{AADTenantId}/Policies/UseCertificateForOnPremAuth

#### <a name="windowsidentityprotectionconfigurationwindowshelloforbusinessblocked"></a>WindowsIdentityProtectionConfiguration.WindowsHelloForBusinessBlocked 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/PassportForWork  
**Posun identifikátoru URI**: / {AADTenantId} / Policies/UsePassportForWork

#### <a name="windowskioskconfigurationedgekioskenablepublicbrowsing"></a>WindowsKioskConfiguration.EdgeKioskEnablePublicBrowsing 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/ConfigureKioskMode

#### <a name="windowskioskconfigurationedgekioskresetafteridletimeinminutes"></a>WindowsKioskConfiguration.EdgeKioskResetAfterIdleTimeInMinutes 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Browser/ConfigureKioskResetAfterIdleTimeout

#### <a name="windowskioskconfigurationkioskbrowserblockedurlexceptions"></a>WindowsKioskConfiguration.KioskBrowserBlockedUrlExceptions 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/KioskBrowser/BlockedUrlExceptions

#### <a name="windowskioskconfigurationkioskbrowserblockedurls"></a>WindowsKioskConfiguration.KioskBrowserBlockedURLs 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/KioskBrowser/BlockedUrls

#### <a name="windowskioskconfigurationkioskbrowserdefaulturl"></a>WindowsKioskConfiguration.KioskBrowserDefaultUrl 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/KioskBrowser/DefaultUrl

#### <a name="windowskioskconfigurationkioskbrowserenableendsessionbutton"></a>WindowsKioskConfiguration.KioskBrowserEnableEndSessionButton 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/KioskBrowser/EnableEndSessionButton

#### <a name="windowskioskconfigurationkioskbrowserenablehomebutton"></a>WindowsKioskConfiguration.KioskBrowserEnableHomeButton 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/KioskBrowser/EnableHomeButton

#### <a name="windowskioskconfigurationkioskbrowserenablenavigationbuttons"></a>WindowsKioskConfiguration.KioskBrowserEnableNavigationButtons 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/KioskBrowser/EnableNavigationButtons

#### <a name="windowskioskconfigurationkioskbrowserrestartonidletimeinminutes"></a>WindowsKioskConfiguration.KioskBrowserRestartOnIdleTimeInMinutes 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/KioskBrowser/KioskBrowserRestartOnIdleTimeInMinutes

#### <a name="windowsupdateforbusinessconfigurationautomaticupdatemode"></a>WindowsUpdateForBusinessConfiguration.AutomaticUpdateMode 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/AllowAutoUpdate

#### <a name="windowsupdateforbusinessconfigurationautorestartnotificationdismissal"></a>WindowsUpdateForBusinessConfiguration.AutoRestartNotificationDismissal 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/AutoRestartRequiredNotificationDismissal

#### <a name="windowsupdateforbusinessconfigurationbusinessreadyupdatesonly"></a>WindowsUpdateForBusinessConfiguration.BusinessReadyUpdatesOnly 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/BranchReadinessLevel

#### <a name="windowsupdateforbusinessconfigurationdeliveryoptimizationmode"></a>WindowsUpdateForBusinessConfiguration.DeliveryOptimizationMode 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/DeliveryOptimization/DODownloadMode

#### <a name="windowsupdateforbusinessconfigurationdriversexcluded"></a>WindowsUpdateForBusinessConfiguration.DriversExcluded 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/ExcludeWUDriversInQualityUpdate

#### <a name="windowsupdateforbusinessconfigurationengagedrestartdeadlineforfeatureupdatesindays"></a>WindowsUpdateForBusinessConfiguration.EngagedRestartDeadlineForFeatureUpdatesInDays 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/EngagedRestartDeadlineForFeatureUpdates

#### <a name="windowsupdateforbusinessconfigurationengagedrestartdeadlineindays"></a>WindowsUpdateForBusinessConfiguration.EngagedRestartDeadlineInDays 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/EngagedRestartDeadline

#### <a name="windowsupdateforbusinessconfigurationengagedrestartsnoozescheduleforfeatureupdatesindays"></a>WindowsUpdateForBusinessConfiguration.EngagedRestartSnoozeScheduleForFeatureUpdatesInDays 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/Update/EngagedRestartSnoozeScheduleForFeatureUpdates

#### <a name="windowsupdateforbusinessconfigurationengagedrestartsnoozescheduleindays"></a>WindowsUpdateForBusinessConfiguration.EngagedRestartSnoozeScheduleInDays 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/EngagedRestartSnoozeSchedule

#### <a name="windowsupdateforbusinessconfigurationengagedrestarttransitionscheduleforfeatureupdatesindays"></a>WindowsUpdateForBusinessConfiguration.EngagedRestartTransitionScheduleForFeatureUpdatesInDays 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Offset URI**: /Config/Update/EngagedRestartTransitionScheduleForFeatureUpdates

#### <a name="windowsupdateforbusinessconfigurationengagedrestarttransitionscheduleindays"></a>WindowsUpdateForBusinessConfiguration.EngagedRestartTransitionScheduleInDays 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/EngagedRestartTransitionSchedule

#### <a name="windowsupdateforbusinessconfigurationfeatureupdatesdeferralperiodindays"></a>WindowsUpdateForBusinessConfiguration.FeatureUpdatesDeferralPeriodInDays 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/DeferFeatureUpdatesPeriodInDays

#### <a name="windowsupdateforbusinessconfigurationfeatureupdatespaused"></a>WindowsUpdateForBusinessConfiguration.FeatureUpdatesPaused 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/PauseFeatureUpdates

#### <a name="windowsupdateforbusinessconfigurationfeatureupdatespausestartdatetime"></a>WindowsUpdateForBusinessConfiguration.FeatureUpdatesPauseStartDateTime 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/PauseFeatureUpdatesStartTime

#### <a name="windowsupdateforbusinessconfigurationfeatureupdateswillberolledback"></a>WindowsUpdateForBusinessConfiguration.FeatureUpdatesWillBeRolledBack 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: / Rollback/FeatureUpdate

#### <a name="windowsupdateforbusinessconfigurationmicrosoftupdateserviceallowed"></a>WindowsUpdateForBusinessConfiguration.MicrosoftUpdateServiceAllowed 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/AllowMUUpdateService

#### <a name="windowsupdateforbusinessconfigurationpreviewbuildsetting"></a>WindowsUpdateForBusinessConfiguration.PreviewBuildSetting 
**Zprostředkovatel kryptografických služeb**: ./Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/ManagePreviewBuilds

#### <a name="windowsupdateforbusinessconfigurationqualityupdatesdeferralperiodindays"></a>WindowsUpdateForBusinessConfiguration.QualityUpdatesDeferralPeriodInDays 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/DeferQualityUpdatesPeriodInDays

#### <a name="windowsupdateforbusinessconfigurationqualityupdatespaused"></a>WindowsUpdateForBusinessConfiguration.QualityUpdatesPaused 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/PauseQualityUpdates

#### <a name="windowsupdateforbusinessconfigurationqualityupdatespausestartdatetime"></a>WindowsUpdateForBusinessConfiguration.QualityUpdatesPauseStartDateTime 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/PauseQualityUpdatesStartTime

#### <a name="windowsupdateforbusinessconfigurationqualityupdateswillberolledback"></a>WindowsUpdateForBusinessConfiguration.QualityUpdatesWillBeRolledBack 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: / Rollback/QualityUpdate

#### <a name="windowsupdateforbusinessconfigurationscheduleimminentrestartwarninginminutes"></a>WindowsUpdateForBusinessConfiguration.ScheduleImminentRestartWarningInMinutes 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/ScheduleImminentRestartWarning

#### <a name="windowsupdateforbusinessconfigurationschedulerestartwarninginhours"></a>WindowsUpdateForBusinessConfiguration.ScheduleRestartWarningInHours 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/ScheduleRestartWarning

#### <a name="windowsupdateforbusinessconfigurationskipchecksbeforerestart"></a>WindowsUpdateForBusinessConfiguration.SkipChecksBeforeRestart 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/SetEDURestart

#### <a name="windowsupdateforbusinessconfigurationupdateweeks"></a>WindowsUpdateForBusinessConfiguration.UpdateWeeks 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/ScheduledInstallEveryWeek /Config/Update/ScheduledInstallFirstWeek, /Config/Update/ScheduledInstallFourthWeek, /Config/Update/ScheduledInstallSecondWeek, / config/aktualizace / ScheduledInstallThirdWeek

#### <a name="windowsupdateforbusinessconfigurationuserpauseaccess"></a>WindowsUpdateForBusinessConfiguration.UserPauseAccess 
**Zprostředkovatel kryptografických služeb**: ./Device/Vendor/MSFT/Policy  
**Posun identifikátoru URI**: /Config/Update/SetDisablePauseUXAccess


## <a name="next-steps"></a>Další postup

- [Přehled konfigurace zařízení](device-profiles.md)
- [Referencích poskytovatelů konfiguračních služeb](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference)
