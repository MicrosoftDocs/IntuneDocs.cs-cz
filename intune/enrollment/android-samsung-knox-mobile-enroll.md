---
title: Automatická registrace zařízení s Androidem pomocí mobilního zápisu pro Samsung KNOX
titleSuffix: Microsoft Intune
description: Přečtěte si, jak zaregistrovat zařízení s Androidem pomocí Samsung KME.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: ''
ms.date: 12/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 30df0f9e-6e9e-4d75-a722-3819e33d480d
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5f290370dd6ec05677a7073d9ca3edd854c9aa5e
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505585"
---
# <a name="automatically-enroll-android-devices-by-using-samsungs-knox-mobile-enrollment"></a>Automatická registrace zařízení s Androidem pomocí technologie Knox Mobile Enrollment od Samsungu

Toto téma vám pomůže s nastavením Intune pro registraci podporovaných zařízení s Androidem pomocí technologie Samsung Knox Mobile Enrollment (KME). Když použijete Intune se Samsung KME, můžete zaregistrovat velké počty zařízení s Androidem vlastněných společností při jejich prvním zapnutí koncovými uživateli a jejich připojení k síti Wi-Fi nebo mobilní síti. Zařízení se také dají zaregistrovat pomocí Bluetooth nebo NFC, když použijete aplikaci Knox Deployment App.

Pokud chcete povolit registraci Intune pomocí Samsung KME, použijte oba portály Intune i Samsung Knox v tomto pořadí:

1. Na portálu Knox:
    1. [Vytvoření profilu MDM](#create-mdm-profile)
    2. [Přidání zařízení](#add-devices)
    3. [Přiřazení profilu MDM zařízení](#assign-an-mdm-profile-to-devices)
2. Na portálu Knox [nakonfigurujte přihlášení koncového uživatele](#configure-how-end-users-sign-in).
3. [Distribuujte zařízení](#distribute-devices).


Seznam identifikátorů zařízení (sériová čísla a IMEI) se automaticky přidá na portál Knox při nákupu zařízení od autorizovaných prodejců, kteří se účastní programu pro nasazení Knox.


## <a name="prerequisites"></a>Požadované součásti

Pokud chcete provést registraci do Intune pomocí KME, musíte nejprve zaregistrovat vaši společnost na portálu Samsung Knox pomocí tohoto postupu:
1. Ujistěte [se, že KME je k dispozici ve vaší zemi nebo oblasti](https://www.samsungknox.com/en/solutions/it-solutions/knox-configure/available-countries): KME je k dispozici ve více než 55 zemích nebo oblastech. Ujistěte se, že je vaše země nebo oblast nasazení podporovaná.

2. [Podporovaná zařízení](https://www.samsungknox.com/en/knox-platform/supported-devices/2.4+): Technologie KME je dostupná na všech zařízeních Samsung, která používají minimálně Knox 2.4 pro registraci Androidu a minimálně Knox 2.8 v případě registrace Androidu Enterprise.

3. [Požadavky sítě](https://docs.samsungknox.com/KME-Getting-Started/Content/firewall_exceptions.htm): Ujistěte se, že jsou ve vaší síti povolena nezbytná pravidla firewallu a přístupu k síti.

4. [Registrace účtu Samsung](https://www2.samsungknox.com/en/user/register): K registraci a povolení KME a správě veškerých oprávnění Knox Enterprise na jednom místě se vyžaduje účet Samsung.

5. Kontrola registrace: po dokončení a odeslání profilu Samsung přečte vaši aplikaci a buď ji schválí, nebo ji okamžitě schválí nebo zařadí do stavu čekání na kontrolu. Po schválení účtu můžete pokračovat dalšími kroky.

## <a name="create-mdm-profile"></a>Vytvoření profilu MDM

Když se vaše společnost úspěšně zaregistruje, můžete na portálu Knox pomocí níže uvedených informací vytvořit profil MDM pro Microsoft Intune. Na portálu Knox můžete vytvořit profily MDM jak pro Android, tak i Android Enterprise. 

### <a name="for-android-enterprise"></a>Android Enterprise

| Pole profilu MDM| Požadované? | Hodnota | 
|-------------------|-----------|-------| 
|MDM Server URI (URI serveru MDM)     | Ne        |Nechte prázdné. 
|Profile Name (Název profilu)       | Ano       |Zadejte libovolný název profilu. 
|Description        | Ne        |Zadejte text popisující profil. 
|MDM Agent APK (APK Agent MDM)      | Ano       |https://aka.ms/intune_kme_deviceowner 
|Enable this app as a Google Device Owner (Povolit tuto aplikaci jako vlastníka zařízení Google) | Ano | Tuto možnost zvolte při registraci do Androidu Enterprise. 
|Supported MDM (Podpora MDM)      | Ano       |Microsoft Intune 
|Leave all system apps enabled (Ponechat všechny systémové aplikace povolené) | Ne | Tuto možnost zvolte, abyste zajistili, že jsou všechny aplikace povolené a pro profil dostupné. Pokud tuto možnost nevyberete, zobrazí se v zásobníku aplikace zařízení jenom omezená sada systémových aplikací. Aplikace, jako je třeba e-mailová aplikace, zůstanou skryté. 
|Custom JSON (Vlastní JSON)        | Ne        |{"com.google.android.apps.work.clouddpc.EXTRA_ENROLLMENT_TOKEN": "Zadejte řetězec tokenu registrace Intune"}. Přečtěte si, [jak vytvořit registrační profil](android-kiosk-enroll.md). 
| Add legal agreements (Přidat právní smlouvy) | Ne | Nechte prázdné. 

### <a name="for-android"></a>Pro Android

Podrobné pokyny najdete v tématu [Průvodce nastavením profilu Samsung KNOX](https://docs.samsungknox.com/KME-Getting-Started/Content/getting-started-wizard.htm) .

| Pole profilu MDM| Požadované? | Hodnota |
|-------------------|-----------|-------|
|MDM Server URI (URI serveru MDM)     | Ne        |Nechte prázdné.
|Profile Name (Název profilu)       | Ano       |Zadejte libovolný název profilu.
|description        | Ne        |Zadejte text popisující profil.
|MDM Agent APK (APK Agent MDM)      | Ano       |https://aka.ms/intune_kme
|Enable this app as a Google Device Owner (Povolit tuto aplikaci jako vlastníka zařízení Google) | Ne | Tuto možnost nechejte pro Android nezvolenou. Tato možnost se vztahuje jenom na Android Enterprise.
|Skip Setup wizard (Přeskočit průvodce nastavením)  | Ne        |Tuto možnost vyberte, pokud chcete pro koncového uživatele přeskočit výzvy pro instalaci standardních zařízení.
|Allow End User to Cancel Enrollment (Povolit koncovému uživateli zrušit registraci) | Ne | Tuto možnost vyberte, pokud chcete uživatelům povolit, aby zrušili KME.
|Custom JSON (Vlastní JSON)        | Ne        |Nechte prázdné.
| Add legal agreements (Přidat právní smlouvy) | Ne | Nechte prázdné.
Associate a Knox license with this profile (Přiřadit tomuto profilu licenci Knox) | Ne | Tuto možnost nechejte nezvolenou. Registrace do Intune pomocí KME nevyžaduje licenci Knox.

## <a name="add-devices"></a>Přidání zařízení

Abyste mohli zařízením přiřadit profily MDM, musí být na portál Knox přidána podporovaná zařízení Samsung Knox pomocí jedné z následujících metod:
- **Používání prodejců schválených společností Samsung:** Tuto metodu použijte, pokud si kupujete zařízení od některého z prodejců schválených společností Samsung. Prodejci za vás mohou po schválení automaticky odesílat zařízení. [Pokud chcete zjistit, jak přidat prodejce, přečtěte si uživatelskou příručku pro registraci Samsung Knox](https://docs.samsungknox.com/KME-Getting-Started/Content/Register_resellers.htm).

- **Prostřednictvím aplikace Knox Deployment App (KDA):** Tuto metodu použijte, pokud máte stávající zařízení, která je potřeba zaregistrovat pomocí KME. Pro přidání zařízení na portál Knox můžete pomocí této metody použít Bluetooth nebo NFC. [Informace o použití aplikace KDA najdete v uživatelské příručce pro registraci Samsung Knox](https://docs.samsungknox.com/KME-Getting-Started/Content/add-device-info.htm).

## <a name="assign-an-mdm-profile-to-devices"></a>Přiřazení profilu MDM k zařízením
Přidaným zařízením na portálu Knox musíte přiřadit profil MDM dříve, než budou moct být zaregistrována. [Informace o konfiguraci zařízení najdete v uživatelské příručce pro registraci Samsung Knox](https://docs.samsungknox.com/KME-Getting-Started/Content/configure-devices.htm).

## <a name="configure-how-end-users-sign-in"></a>Konfigurace způsobu přihlašování koncových uživatelů

Pro zařízení zaregistrovaná v Intune pomocí KME pro Android můžete následujícím postupem nakonfigurovat způsob, jakým se přihlašuje koncový uživatel:

- **Bez přiřazení uživatelského jména:** Na portálu Knox v části **Device details** (Podrobnosti zařízení) nechejte pole **User ID** (ID uživatele) a **Password** (Heslo) pro přidaná zařízená prázdná. Tato možnost vyžaduje, aby koncový uživatel při registraci do Intune zadal uživatelské jméno i heslo.

- **S přiřazením uživatelského jména:** Na portálu Knox v části **Device details** (Podrobnosti zařízení) zadejte **User ID** (ID uživatele) (například uživatelské jméno přiřazeného uživatele nebo účet [Správce registrace zařízení](device-enrollment-manager-enroll.md)) pro přidaná zařízení. Tato možnost předem vyplní uživatelské jméno a vyžaduje, aby koncový uživatel zadal heslo při registraci do Intune.

> [!NOTE]
>
>Přidružení uživatele se vztahuje pouze na zápis Správce zařízení s Androidem. Jakmile je nadefinováno přiřazení uživatele, může zařízení pomocí KME zaregistrovat pouze přiřazený uživatel. Platí to i po obnovení zařízení do továrního nastavení. Pokud na portálu Knox není nadefinováno žádné přiřazení uživatele, může zařízení pomocí KME zaregistrovat jakýkoli uživatel s platnou licencí Intune.
>U zařízení se systémem Android Enterprise s plnou správou, i když je definováno přidružení uživatele, se nepředá zařízení uživateli nebo zařízení nespojí.
>

## <a name="distribute-devices"></a>Distribuujte zařízení.

Jakmile vytvoříte a přiřadíte profil MDM, přiřadíte uživatelské jméno a identifikujete zařízení v Intune jako vlastněná společností, můžete zařízení distribuovat uživatelům.

Potřebujete ještě další pomoc? Projděte si kompletní [uživatelskou příručku KME](https://docs.samsungknox.com/KME-Getting-Started/Content/get-started.htm).

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

- **Podpora vlastníka zařízení:**  - **Podpora vlastníka zařízení:** Intune podporuje registraci vyhrazených a plně spravovaných zařízení pomocí portálu KME. Další režimy vlastníka zařízení s Androidem Enterprise se budou podporovat, jakmile budou dostupné v Intune.

- **Nepodporují se pracovní profil:** KME je metoda registrace podnikového zařízení a zařízení zaregistrovaná v pracovním profilu Android, která zajišťují, že pracovní a osobní údaje jsou oddělené na osobních zařízeních. To znamená, že registrace zařízení do pracovního profilu pomocí KME není podporovaným scénářem v Intune.

- **Obnovení továrního nastavení za účelem registrace do Androidu Enterprise**: Pokud chcete znovu použít zařízení, které už bylo jednou nastaveno, musíte ho obnovit do továrního nastavení, abyste ho mohli zaregistrovat do Androidu Enterprise.

- **Aktualizace používající účet Google Play:** Google Play účet není nutný k zaregistrování zařízení do Microsoft Intune. V případě registrace Správce zařízení s Androidem ale můžou budoucí aktualizace Portál společnosti Intune aplikace vyžadovat na zařízení Google Play účet. Google Play účet není při registraci do vlastníka zařízení Google vyžadován.

- **Pole heslo se ignoruje:** Pokud se pole **heslo** naplní v části **Podrobnosti o zařízení** na portálu KNOX, ignoruje se při registraci Androidu aplikace Portál společnosti Intune. Aby se registrace zařízení dokončila, koncový uživatel musí heslo zadat na zařízení.


## <a name="getting-support"></a>Získání podpory
Přečtěte si další informace o tom, [jak získat podporu pro Samsung KME](https://docs.samsungknox.com/KME-Getting-Started/Content/to-get-kme-support.htm).

