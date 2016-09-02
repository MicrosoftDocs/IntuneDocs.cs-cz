---
title: "Hledání identity aplikace (PFN) pro síť VPN pro aplikaci | Microsoft Intune"
description: "Najděte PFN, abyste mohli konfigurovat síť VPN pro aplikaci."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ms.reviewer: tycast
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3cc73e43f09709b71c78a81c73b044d92d4ef401
ms.openlocfilehash: 77977ea32ea37a54e9d67638bb0e4c3bb6841fb3


---

# Hledání identity aplikace (PFN) pro konfiguraci sítě VPN pro aplikaci

Existují dva způsoby jak zjistit PFN, abyste mohli konfigurovat síť VPN pro aplikaci.

## Hledání PFN pro aplikaci, která je nainstalovaná na počítači s Windows 10

Pokud pracujete s aplikací, která už je nainstalovaná v počítači s Windows 10, můžete k získání PFN použít rutinu PowerShellu [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx).

Syntaxe pro Get-AppxPackage:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> [!NOTE]
Pro získání PFN může být nutné spustit PowerShell jako správce.

Chcete-li například získat informace o všech univerzálních aplikacích nainstalovaných na počítače, použijte `Get-AppxPackage`.

Chcete-li získat informace o aplikaci, jejíž název nebo část názvu znáte, použijte `Get-AppxPackage *<app_name>`. Všimněte si použití zástupného znaku, které je zvláště užitečné, pokud si nejste jisti úplným názvem aplikace. Pokud chcete například získat informace pro aplikaci OneNote, použijte `Get-AppxPackage *OneNote`.


Zde jsou informace načtené pro OneNote:

`Name                   : Microsoft.Office.OneNote`

`Publisher              : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`

`Architecture           : X64`

`ResourceId             :`

`Version                : 17.6769.57631.0`

`PackageFullName        : Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`InstallLocation        : C:\Program Files\WindowsApps`

`\Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`IsFramework            : False`

**`PackageFamilyName      : Microsoft.Office.OneNote_8wekyb3d8bbwe`**

`PublisherId            : 8wekyb3d8bbwe`



## Hledání PFN, pokud aplikace není nainstalovaná na počítači

1.  Přejděte na adresu https://www.microsoft.com/en-us/store/apps.
2.  Zadejte název aplikace v panelu vyhledávání. V našem příkladu hledejte OneNote.
3.  Vyberte odkaz na aplikaci. Všimněte si, že adresa URL má na konci řadu písmen. V našem příkladu vypadá adresa URL takto: `https://www.microsoft.com/en-us/store/apps/onenote/9wzdncrfhvjl`.
4.  Na nové kartě vložte následující adresu URL: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`. Místo `<app id>` zadejte ID aplikace, které jste získali z adresy https://www.microsoft.com/en-us/store/apps – onu posloupnost písmen na konci adresy URL v kroku 3. V našem příkladu pro OneNote byste vložili adresu `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

Microsoft Edge zobrazí požadované informace přímo, v Internet Exploreru je zobrazíte výběrem **Otevřít**. Hodnota PFN je uvedena na prvním řádku. Tady jsou výsledky pro náš příklad:


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`



<!--HONumber=Aug16_HO3-->


