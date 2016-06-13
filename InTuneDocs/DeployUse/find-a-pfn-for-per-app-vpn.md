---
# required metadata

title: Hledání identity aplikace (PFN) pro síť VPN pro aplikaci |Microsoft Intune|
description:
keywords:
author: nbigman
manager: [ALIAS]
ms.date: 05/10/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: [ALIAS]
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Hledání identity aplikace (PFN) pro konfiguraci sítě VPN pro aplikaci

Existují dva způsoby jak najít PFN, abyste mohli konfigurovat síť VPN pro aplikaci.

## Hledání PFN pro aplikaci, která je nainstalovaná na počítači s Windows 10 

Pokud pracujete s aplikací, která je již nainstalována v počítači s Windows 10, můžete k získání PFN použít rutinu PowerShellu [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx).

Syntaxe pro Get-AppxPackage:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> Poznámka: K načtení PFN bude pravděpodobně nutné spustit PowerShell jako správce.

Chcete-li například získat informace o všech univerzálních aplikacích nainstalovaných na počítače, použijte `Get-AppxPackage`.

Chcete-li získat informace o aplikaci, jejíž název nebo část názvu znáte, použijte `Get-AppxPackage *<app_name>`. Všimněte si použití zástupného znaku, které je zvláště užitečné, pokud si nejste jisti úplným názvem aplikace. Například chcete-li získat informace pro aplikaci OneNote, použijte `Get-AppxPackage *OneNote`.


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
3.  Klikněte na odkaz na aplikaci. Všimněte si, že adresa URL, ke které přistupujete, má na konci řadu písmen. V našem příkladu vypadá adresu URL takto:
`https://www.microsoft.com/en-us/store/apps/onenote/9wzdncrfhvjl`
4.  Na jiné kartě vložte následující adresu URL, `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`, ve které nahradíte `<app id>` pomocí ID aplikace, které jste získali z adresy https://www.microsoft.com/en-us/store/apps (to je ta řada písmen na konci adresy URL v kroku 3). V našem příkladu (pro OneNote) byste vložili adresu `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

V Edgi se požadované informace zobrazí, v Internet Exploreru je zobrazíte kliknutím na **Otevřít**. Hodnota PFN je uvedena na prvním řádku. Zde jsou uvedené výsledky pro náš příklad:
 

`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`



<!--HONumber=May16_HO3-->

