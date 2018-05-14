---
title: Vlastní nastavení pro zařízení s Windows Holographic for Business v Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte si vlastní profil, abyste mohli použít nastavení OMA-URI pro zařízení s Windows Holographic for Business v Microsoft Intune. Můžete nakonfigurovat nastavení poskytovatele služeb konfigurace zásad (CSP) AllowFastReconnect, AllowVPN, AllowUpdateService, UpdateServiceURL, RequireUpdatesApproval, ApprovedUpdates a ApplicationLaunchRestrictions.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/26/2018
ms.article: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7272e8e088ae2c2ecad1756233281c42a80a279b
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
---
# <a name="custom-device-settings-for-devices-running-windows-holographic-for-business-in-intune"></a>Vlastní nastavení zařízení s Windows Holographic for Business v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

 **Vlastní** profil Microsoft Intune pro Windows Holographic for Business použijte, pokud chcete nasadit nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier), s jehož pomocí se dají ovládat funkce na zařízeních. Windows Holographic for Business zpřístupňuje řadu nastavení poskytovatelů konfiguračních služeb (CSP). Základní informace o CSP najdete v [úvodu o poskytovatelích konfiguračních služeb (CSP) pro IT specialisty](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Konkrétní poskytovatele CSP, které podporuje Windows Holographic, najdete v části [Poskytovatelé CSP podporovaní ve Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Pokud hledáte konkrétní nastavení, mějte na paměti, že [profil omezení zařízení s Windows Holographic for Business](device-restrictions-windows-holographic.md) obsahuje řadu integrovaných nastavení, která nevyžadují, abyste zadali vlastní hodnoty.

## <a name="create-the-custom-oma-uri-profile"></a>Vytvoření vlastního profilu OMA-URI

1. Začněte podle pokynů v tématu [Konfigurace vlastního nastavení zařízení v Microsoft Intune](custom-settings-configure.md).
2. Pokud chcete přidat jedno nebo více nastavení OMA-URI, v části **Vytvořit profil** zvolte **Nastavení**.
3. V části **Vlastní nastavení OMA-URI** klikněte na **Přidat**, abyste mohli přidat novou hodnotu. Můžete také kliknout na **Exportovat** a vytvořit seznam všech hodnot, které jste nakonfigurovali v souboru hodnot oddělených čárkami (CSV).
4. Ke každému nastavení OMA-URI, které chcete přidat, zadejte následující informace:
  - **Název nastavení**: Zadejte jedinečný název nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.
  - **Popis nastavení**: Volitelně zadejte popis nastavení.
  - **Datový typ**: Vybírejte z těchto typů:
    - **Řetězec**
    - **Řetězec (XML)**
    - **Datum a čas**
    - **Celé číslo**
    - **Číslo s plovoucí desetinnou čárkou**
    - **Logická hodnota**
  - **OMA-URI (rozlišuje velká a malá písmena)**: Zadejte, který OMA-URI chcete nastavit.
  - **Hodnota**: Zadejte hodnotu, kterou chcete přidružit k zadanému OMA-URI.
5. Až to budete mít, vraťte se do části **Vytvořit profil** a klikněte na **Vytvořit**. Profil se vytvoří a zobrazí se v seznamu profilů.

## <a name="recommended-custom-settings"></a>Doporučená vlastní nastavení

Následující nastavení jsou užitečná pro zařízení s Windows Holographic for Business.

### <a name="allowfastreconnecthttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-authenticationauthentication-allowfastreconnect"></a>[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)

> [!div class="mx-tableFixed"]
> |OMA-URI|Datový typ|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Celé číslo<br/>0 – Nepovoluje se.<br/>1 – Povoluje se (výchozí).|

### <a name="allowupdateservicehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-allowupdateservice"></a>[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)

> [!div class="mx-tableFixed"]
> |OMA-URI|Datový typ|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Celé číslo<br/>0 – Služba aktualizací se nepovoluje. <br/>1 – Služba aktualizací se povoluje (výchozí).|

### <a name="allowvpnhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-settingssettings-allowvpn"></a>[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)

> [!div class="mx-tableFixed"]
> |OMA-URI|Datový typ|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Celé číslo<br/>0 – Nepovoluje se.<br/>1 – Povoluje se (výchozí).|

### <a name="requireupdatesapprovalhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-requireupdateapproval"></a>[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)

> [!div class="mx-tableFixed"]
> |OMA-URI|Datový typ|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Celé číslo<br/>0 – Není nakonfigurováno. Zařízení nainstaluje všechny použitelné aktualizace.<br/>1 – Zařízení nainstaluje jenom aktualizace, které jsou použitelné a jsou také v seznamu schválených aktualizací. Pokud chce oddělení IT řídit nasazení aktualizací na zařízení, třeba když je před nasazením nutné testování, nastavte tuto zásadu na 1.|

### <a name="scheduledinstalltimehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-scheduledinstalltime"></a>[ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)

> [!div class="mx-tableFixed"]
> |OMA-URI|Datový typ|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Celé číslo 0–23, kde 0 = 12 dop. a 23 = 11 odp.<br/>Výchozí hodnota je 3.|

### <a name="updateserviceurlhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-updateserviceurl"></a>[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

> [!div class="mx-tableFixed"]
> |OMA-URI|Datový typ|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Řetězec<br/>URL – Zařízení vyhledá aktualizace na serveru WSUS na zadané adrese URL.<br/>Nenakonfigurováno – Zařízení vyhledá aktualizace ve službě Microsoft Update.|

### <a name="approvedupdateshttpsdocsmicrosoftcomwindowsclient-managementmdmupdate-csp"></a>[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Datový typ|
> |---|---|
> |./Vendor/MSFT/Update/ApprovedUpdates/*GUID*<br/><br/>**Důležité**<br/>Musíte si přečíst smlouvy EULA k aktualizacím a přijmout je jménem vašich koncových uživatelů. Pokud tak neučiníte, dojde k porušení právních nebo smluvních závazků.|Uzel pro schválení aktualizací a přijetí smlouvy EULA jménem koncového uživatele<br/><br/>Další informace naleznete v tématu [Update CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp).|

### <a name="applicationlaunchrestrictionshttpsdocsmicrosoftcomwindowsclient-managementmdmapplocker-csp"></a>[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Datový typ|
> |----|---|
> |./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br/><br/>**Důležité**<br/>V článku o AppLocker CSP se používají příklady XML, které obsahují pomocné řídicí znaky. Pokud chcete nakonfigurovat nastavení s vlastními profily Intune, je nutné použít prostý XML.|Řetězec<br/>Další informace najdete v článku o [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp).|

### <a name="deletionpolicyhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[DeletionPolicy](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Datový typ|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/DeletionPolicy|Celé číslo<br/>0 – dojde k okamžitému odstranění, když se zařízení vrátí do stavu, ve kterém nemá žádné aktuálně aktivní uživatele.<br/>1 – dojde k odstranění při dosažení prahové hodnoty kapacity úložiště (výchozí nastavení).<br/>2 – dojde k odstranění při dosažení prahové hodnoty kapacity úložiště a prahové hodnoty neaktivity profilu.|

### <a name="enableprofilemanagerhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[EnableProfileManager](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Datový typ|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/EnableProfileManager|Logická hodnota<br/>True – povoleno<br/>False – zakázáno (výchozí)|

### <a name="profileinactivitythresholdhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[ProfileInactivityThreshold](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Datový typ|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/ProfileInactivityThreshold|Celé číslo<br/>Výchozí hodnota je 30.|


### <a name="storagecapacitystartdeletionhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[StorageCapacityStartDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Datový typ|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStartDeletion|Celé číslo<br/>Výchozí hodnota je 25.|

### <a name="storagecapacitystopdeletionhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[StorageCapacityStopDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Datový typ|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStopDeletion|Celé číslo<br/>Výchozí hodnota je 50.|

## <a name="find-the-policies-you-can-configure"></a>Vyhledání zásad, které můžete nakonfigurovat

Úplný seznam všech poskytovatelů konfiguračních služeb (CSP), které Windows Holographic podporuje, najdete v části [Poskytovatelé CSP podporovaní ve Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Ne všechna nastavení jsou kompatibilní se všemi verzemi Windows Holographic. V tabulce v článku týkajícím se Windows zjistíte, které verze se pro jednotlivé CSP podporují.

Intune navíc nepodporuje všechna nastavení uvedená v tomto článku. Pokud chcete zjistit, jestli Intune podporuje vámi požadované nastavení, otevřete si článek týkající se daného nastavení. Jednotlivé stránky nastavení zobrazují podporované operace. Aby dané nastavení fungovalo s Intune, musí podporovat operace **Přidat** nebo **Nahradit**.
