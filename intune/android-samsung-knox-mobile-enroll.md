---
title: Automatická registrace zařízení s Androidem pomocí registrace mobilních společnosti Samsung Knox
titleSuffix: Microsoft Intune
description: Přečtěte si, jak zaregistrovat zařízení s Androidem pomocí Samsung KME.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: ''
ms.date: 12/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 30df0f9e-6e9e-4d75-a722-3819e33d480d
ms.reviewer: arnab
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 94c92f70844594fd8524f2e49c537f1afaadaf96
ms.sourcegitcommit: e6edfbfd63dd7c2500ce1123205aa2af9a7e8e2e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2019
ms.locfileid: "68783199"
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


Seznam identifikátorů zařízení (sériová čísla a čísla IMEI) se při nákupu zařízení od autorizovaných prodejců, kteří se účastní programu Knox Deployment Program, automaticky přidá na portál Knox.


## <a name="prerequisites"></a>Požadavky

Pokud chcete provést registraci do Intune pomocí KME, musíte nejprve zaregistrovat vaši společnost na portálu Samsung Knox pomocí tohoto postupu:
1. Ujistěte [se, že KME je k dispozici ve vaší zemi nebo oblasti](https://www.samsungknox.com/en/solutions/it-solutions/knox-configure/available-countries): KME je k dispozici ve více než 55 zemích nebo oblastech. Ujistěte se, že je vaše země nebo oblast nasazení podporovaná.

2. [Podporovaná zařízení](https://www.samsungknox.com/en/knox-platform/supported-devices/2.4+): KME je k dispozici na všech zařízeních Samsung s minimálně KNOX 2,4 pro registraci v Androidu a minimálně KNOX 2,8 pro registraci v Androidu Enterprise.

3. [Požadavky na síť](https://docs.samsungknox.com/KME-Getting-Started/Content/firewall_exceptions.htm): Ujistěte se, že jsou ve vaší síti povolená potřebná pravidla brány firewall a přístupu k síti.

4. [Zaregistrujte se na účet Samsung](https://www2.samsungknox.com/en/user/register): Účet Samsung je nutný k registraci a povolení KME a správě všech nároků v rámci Knox Enterprise na jednom místě.

5. Kontrola registrace: Po dokončení a odeslání profilu Samsung provede kontrolu vaší aplikace a buď ji schválí, nebo ji okamžitě schválí nebo umístí do stavu nedokončené revize pro další následné zpracování. Po schválení účtu můžete pokračovat dalšími kroky.

## <a name="create-mdm-profile"></a>Vytvoření profilu MDM

Když se vaše společnost úspěšně zaregistruje, můžete na portálu Knox pomocí níže uvedených informací vytvořit profil MDM pro Microsoft Intune. Na portálu Knox můžete vytvořit profily MDM jak pro Android, tak i Android Enterprise. 

### <a name="for-android-enterprise"></a>Android Enterprise

| Pole profilu MDM| Požadováno? | Hodnoty | 
|-------------------|-----------|-------| 
|MDM Server URI (URI serveru MDM)     | Ne        |Nechte prázdné. 
|Profile Name (Název profilu)       | Ano       |Zadejte libovolný název profilu. 
|Popis        | Ne        |Zadejte text popisující profil. 
|MDM Agent APK (APK Agent MDM)      | Ano       |https://aka.ms/intune_kme_deviceowner 
|Enable this app as a Google Device Owner (Povolit tuto aplikaci jako vlastníka zařízení Google) | Ano | Tuto možnost zvolte při registraci do Androidu Enterprise. 
|Supported MDM (Podpora MDM)      | Ano       |Microsoft Intune 
|Leave all system apps enabled (Ponechat všechny systémové aplikace povolené) | Ne | Tuto možnost zvolte, abyste zajistili, že jsou všechny aplikace povolené a pro profil dostupné. Pokud tuto možnost nevyberete, bude se v okně aplikací zařízení zobrazovat pouze velmi omezená sada systémových aplikací. Aplikace, jako je třeba e-mailová aplikace, zůstanou skryté. 
|Custom JSON (Vlastní JSON)        | Ne        |{"com. Google. Android. Apps. work. clouddpc. EXTRA_ENROLLMENT_TOKEN": Zadejte řetězec tokenu registrace v Intune. Přečtěte si, [jak vytvořit registrační profil](android-kiosk-enroll.md). 
| Add legal agreements (Přidat právní smlouvy) | Ne | Nechte prázdné. 

### <a name="for-android"></a>Pro Android

Podrobné pokyny najdete v tématu [Průvodce nastavením profilu Samsung KNOX](https://docs.samsungknox.com/KME-Getting-Started/Content/getting-started-wizard.htm) .

| Pole profilu MDM| Požadováno? | Hodnoty |
|-------------------|-----------|-------|
|MDM Server URI (URI serveru MDM)     | Ne        |Nechte prázdné.
|Profile Name (Název profilu)       | Ano       |Zadejte libovolný název profilu.
|description        | Ne        |Zadejte text popisující profil.
|MDM Agent APK (APK Agent MDM)      | Ano       |https://aka.ms/intune_kme
|Enable this app as a Google Device Owner (Povolit tuto aplikaci jako vlastníka zařízení Google) | Ne | Tuto možnost nechejte pro Android nezvolenou. Platí pouze pro Android Enterprise.
|Skip Setup wizard (Přeskočit průvodce nastavením)  | Ne        |Tuto možnost vyberte, pokud chcete přeskočit standardní výzvy k nastavení zařízení jménem koncového uživatele.
|Allow End User to Cancel Enrollment (Povolit koncovému uživateli zrušit registraci) | Ne | Tuto možnost vyberte, pokud chcete uživatelům povolit, aby zrušili KME.
|Custom JSON (Vlastní JSON)        | Ne        |Nechte prázdné.
| Add legal agreements (Přidat právní smlouvy) | Ne | Nechte prázdné.
Associate a Knox license with this profile (Přiřadit tomuto profilu licenci Knox) | Ne | Tuto možnost nechejte nezvolenou. Registrace do Intune pomocí KME nevyžaduje licenci Knox.

## <a name="add-devices"></a>Přidání zařízení

Abyste mohli zařízením přiřadit profily MDM, musí být na portál Knox přidána podporovaná zařízení Samsung Knox pomocí jedné z následujících metod:
- **Používání prodejců schválených společností Samsung:** Tuto metodu použijte, pokud si kupujete zařízení od některého z prodejců schválených společností Samsung. Prodejci za vás mohou po schválení automaticky odesílat zařízení. [Pokud chcete zjistit, jak přidat prodejce, přečtěte si uživatelskou příručku pro registraci Samsung Knox](https://docs.samsungknox.com/KME-Getting-Started/Content/Register_resellers.htm).

- **Použití aplikace pro nasazení Knox (KDA):** Tuto metodu použijte, pokud máte existující zařízení, která je potřeba zaregistrovat pomocí KME. Pro přidání zařízení na portál Knox můžete pomocí této metody použít Bluetooth nebo NFC. [Informace o použití aplikace KDA najdete v uživatelské příručce pro registraci Samsung Knox](https://docs.samsungknox.com/KME-Getting-Started/Content/add-device-info.htm).

## <a name="assign-an-mdm-profile-to-devices"></a>Přiřazení profilu MDM k zařízením
Přidaným zařízením na portálu Knox musíte přiřadit profil MDM dříve, než budou moct být zaregistrována. [Informace o konfiguraci zařízení najdete v uživatelské příručce pro registraci Samsung Knox](https://docs.samsungknox.com/KME-Getting-Started/Content/configure-devices.htm).

## <a name="configure-how-end-users-sign-in"></a>Konfigurace způsobu přihlašování koncových uživatelů

Pro zařízení zaregistrovaná v Intune pomocí KME pro Android můžete následujícím postupem nakonfigurovat způsob, jakým se přihlašuje koncový uživatel:

- **Bez přidružení uživatelského jména:** Na portálu Knox v části **Podrobnosti o zařízení**ponechte pole **ID uživatele** a **heslo** pro přidaná zařízení prázdná. Je nutné, aby koncový uživatel zadal při registraci do Intune uživatelské jméno i heslo.

- **S přidružením uživatelského jména:** Na portálu Knox v části **Podrobnosti o zařízení**zadejte **ID uživatele** (například uživatelské jméno pro přiřazeného uživatele nebo účet [správce registrace zařízení](https://docs.microsoft.com/intune/device-enrollment-manager-enroll) ) pro přidaná zařízení. Tento způsob předem vyplní uživatelské jméno a vyžaduje, aby koncový uživatel při registraci do Intune zadal heslo.

> [!NOTE]
>
>Přidružení uživatele se vztahuje pouze na registraci do Androidu. Jakmile je nadefinováno přiřazení uživatele, může zařízení pomocí KME zaregistrovat pouze přiřazený uživatel. Platí to i po obnovení zařízení do továrního nastavení. Pokud na portálu Knox není nadefinováno žádné přiřazení uživatele, může zařízení pomocí KME zaregistrovat jakýkoli uživatel s platnou licencí Intune.
>

## <a name="distribute-devices"></a>Distribuujte zařízení.

Jakmile vytvoříte a přiřadíte profil MDM, přiřadíte uživatelské jméno a identifikujete zařízení v Intune jako vlastněná společností, můžete zařízení distribuovat uživatelům.

Potřebujete ještě další pomoc? Podívejte se na celou [uživatelskou příručku pro KME](https://docs.samsungknox.com/KME-Getting-Started/Content/get-started.htm).

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

- **Podpora vlastníka zařízení:** Intune podporuje registraci zařízení jenom pro celoobrazovkový režim pomocí Androidu Enterprise. Další režimy vlastníka zařízení s Androidem Enterprise se budou podporovat, jakmile budou dostupné v Intune.

- **Nepodporují se pracovní profil:** KME je metoda registrace podnikového zařízení a zařízení zaregistrovaná v pracovním profilu Android, která zajišťují, že pracovní a osobní údaje jsou oddělené na osobních zařízeních. Registrace zařízení do pracovního profilu pomocí KME tedy není podporovaný scénář v Intune.

- **Obnovení továrního nastavení pro registraci do systému Android Enterprise:** Pokud zařízení ještě potřeba vyřadit, která už jsou nastavená, je potřeba při registraci do Androidu Enterprise obnovit tovární nastavení zařízení.

- **Aktualizace používající účet Google Play:** Google Play účet není nezbytný pro registraci zařízení do Microsoft Intune. Budoucí aktualizace aplikace Portál společnosti Intune mohou účet Google Play na zařízení vyžadovat. Při registraci do režimu vlastníka zařízení Google se účet Google Play nevyžaduje.

- **Pole heslo se ignoruje:** Pokud se pole **heslo** naplní v části **Podrobnosti o zařízení** na portálu KNOX, ignoruje se portál společnosti Intune aplikace při registraci Androidu. Aby se registrace zařízení dokončila, koncový uživatel musí heslo zadat na zařízení.


## <a name="getting-support"></a>Získání podpory
Přečtěte si další informace o tom, [jak získat podporu pro Samsung KME](https://docs.samsungknox.com/KME-Getting-Started/Content/to-get-kme-support.htm).


