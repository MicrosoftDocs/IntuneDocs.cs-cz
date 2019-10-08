---
title: Automatická registrace zařízení s Androidem pomocí mobilního zápisu pro Samsung KNOX
titleSuffix: Microsoft Intune
description: Přečtěte si, jak zaregistrovat zařízení s Androidem pomocí Samsung KME
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
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b16dca0b6a73e7228e65c840bfbc91f3577bb59a
ms.sourcegitcommit: 29b1113dc04534c4c87c33c773c5a0e24266e042
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/07/2019
ms.locfileid: "71999288"
---
# <a name="automatically-enroll-android-devices-by-using-samsungs-knox-mobile-enrollment"></a>Automatická registrace zařízení s Androidem pomocí zápisu mobilních zařízení Samsung společnosti Samsung

Toto téma vám pomůže nastavit Intune pro registraci podporovaných zařízení s Androidem pomocí zápisu mobilních zařízení Samsung KNOX (KME). Pomocí Intune s Samsung KME můžete zaregistrovat velký počet zařízení s Androidem ve vlastnictví společnosti, když koncoví uživatelé poprvé zapnou svoje zařízení a připojí se k síti Wi-Fi nebo mobilní síti. Zařízení se taky můžou registrovat pomocí Bluetooth nebo NFC při použití aplikace nasazení Knox.

Pokud chcete povolit registraci v Intune pomocí Samsung KME, použijte portál Intune i Samsung KNOX v tomto pořadí:

1. Na portálu Knox:
    1. [Vytvořit profil MDM](#create-mdm-profile)
    2. [Přidat zařízení](#add-devices)
    3. [Přiřazení profilu MDM k zařízením](#assign-an-mdm-profile-to-devices)
2. Na portálu Knox [nakonfigurujte přihlášení koncového uživatele](#configure-how-end-users-sign-in).
3. [Distribuujte zařízení](#distribute-devices).


Seznam identifikátorů zařízení (sériová čísla a IMEI) se automaticky přidá na portál Knox při nákupu zařízení od autorizovaných prodejců, kteří se účastní programu pro nasazení Knox.


## <a name="prerequisites"></a>Požadavky

Pokud se chcete do Intune zaregistrovat pomocí KME, musíte nejdřív zaregistrovat svoji společnost na portálu Samsung KNOX pomocí následujících kroků:
1. Ujistěte [se, že KME je k dispozici ve vaší zemi nebo oblasti](https://www.samsungknox.com/en/solutions/it-solutions/knox-configure/available-countries): KME je k dispozici ve více než 55 zemích nebo oblastech. Ujistěte se, že je vaše země nebo oblast nasazení podporovaná.

2. [Podporovaná zařízení](https://www.samsungknox.com/en/knox-platform/supported-devices/2.4+): KME je k dispozici na všech zařízeních Samsung s minimálně KNOX 2,4 pro registraci v Androidu a minimálně KNOX 2,8 pro registraci v Androidu Enterprise.

3. [Požadavky na síť](https://docs.samsungknox.com/KME-Getting-Started/Content/firewall_exceptions.htm): Ujistěte se, že jsou v síti povolená potřebná pravidla brány firewall a přístupu k síti.

4. [Zaregistrujte se na účet Samsung](https://www2.samsungknox.com/en/user/register): účet Samsung je nutný k registraci a povolení KME a správě všech nároků v rámci Knox Enterprise na jednom místě.

5. Kontrola registrace: po dokončení a odeslání profilu Samsung přečte vaši aplikaci a buď ji schválí, nebo ji okamžitě schválí nebo zařadí do stavu čekání na kontrolu. Po schválení účtu můžete pokračovat dalšími kroky.

## <a name="create-mdm-profile"></a>Vytvořit profil MDM

Po úspěšné registraci vaší společnosti můžete vytvořit profil MDM pro Microsoft Intune na portálu Knox pomocí níže uvedených informací. Na portálu Knox můžete vytvořit profily MDM pro Android i Android Enterprise. 

### <a name="for-android-enterprise"></a>Pro Android Enterprise

| Pole profilu MDM| Povinné? | Hodnoty | 
|-------------------|-----------|-------| 
|Identifikátor URI serveru MDM     | Ne        |Nechte toto pole prázdné. 
|Název profilu       | Ano       |Zadejte název profilu dle vašeho výběru. 
|Popis        | Ne        |Zadejte text popisující profil. 
|APK agenta MDM      | Ano       |https://aka.ms/intune_kme_deviceowner 
|Povolit tuto aplikaci jako vlastníka zařízení Google | Ano | Tuto možnost vyberte, pokud se chcete zaregistrovat do systému Android Enterprise. 
|Podporovaná MDM      | Ano       |Microsoft Intune 
|Ponechte všechny systémové aplikace povolené. | Ne | Tuto možnost vyberte, pokud chcete zajistit, aby byly všechny aplikace povolené a dostupné pro daný profil. Pokud tuto možnost nevyberete, zobrazí se v zásobníku aplikace zařízení jenom omezená sada systémových aplikací. Aplikace, jako je e-mailová aplikace, zůstanou skryté. 
|Vlastní JSON        | Ne        |{"com. Google. Android. Apps. work. clouddpc. EXTRA_ENROLLMENT_TOKEN": "zadejte řetězec tokenu registrace v Intune"}. Naučte [se vytvořit profil zápisu](android-kiosk-enroll.md). 
| Přidat právní smlouvy | Ne | Nechte toto pole prázdné. 

### <a name="for-android"></a>Pro Android

Podrobné pokyny najdete v tématu [Průvodce nastavením profilu Samsung KNOX](https://docs.samsungknox.com/KME-Getting-Started/Content/getting-started-wizard.htm) .

| Pole profilu MDM| Povinné? | Hodnoty |
|-------------------|-----------|-------|
|Identifikátor URI serveru MDM     | Ne        |Nechte toto pole prázdné.
|Název profilu       | Ano       |Zadejte název profilu dle vašeho výběru.
|description        | Ne        |Zadejte text popisující profil.
|APK agenta MDM      | Ano       |https://aka.ms/intune_kme
|Povolit tuto aplikaci jako vlastníka zařízení Google | Ne | Tuto možnost nechte u Androidu nevybranou. Tato možnost se vztahuje jenom na Android Enterprise.
|Přeskočit průvodce instalací  | Ne        |Tuto možnost vyberte, pokud chcete pro koncového uživatele přeskočit výzvy pro instalaci standardních zařízení.
|Povolí koncovému uživateli zrušit registraci. | Ne | Tuto možnost vyberte, pokud chcete uživatelům dovolit, aby zrušili KME.
|Vlastní JSON        | Ne        |Nechte toto pole prázdné.
| Přidat právní smlouvy | Ne | Nechte toto pole prázdné.
Přidružit licenci Knox k tomuto profilu | Ne | Tuto možnost nechte nevybranou. Registrace do Intune pomocí KME nevyžaduje licenci Knox.

## <a name="add-devices"></a>Přidat zařízení

K přiřazení profilů MDM k zařízením je potřeba na portál Knox přidat podporovaná zařízení Samsung KNOX pomocí jedné z následujících metod:
- **Používání prodejců schválených společností Samsung:** Tuto metodu použijte, pokud si kupujete zařízení od některého z prodejců schválených společností Samsung. Prodejci můžou po schválení automaticky nahrávat zařízení. [Informace o tom, jak přidat prodejce, najdete v uživatelské příručce pro registraci Samsung KNOX](https://docs.samsungknox.com/KME-Getting-Started/Content/Register_resellers.htm).

- **Použití aplikace pro nasazení Knox (kDa):** Tuto metodu použijte, pokud máte existující zařízení, která je potřeba zaregistrovat pomocí KME. Pomocí této metody můžete k přidávání zařízení na portál Knox použít Bluetooth nebo NFC. [Informace o použití kDa najdete v uživatelské příručce pro registraci Samsung KNOX](https://docs.samsungknox.com/KME-Getting-Started/Content/add-device-info.htm).

## <a name="assign-an-mdm-profile-to-devices"></a>Přiřazení profilu MDM k zařízením
Předtím, než se dají zaregistrovat, musíte na portálu Knox přiřadit profil MDM. [Informace o konfiguraci zařízení najdete v uživatelské příručce pro registraci Samsung KNOX](https://docs.samsungknox.com/KME-Getting-Started/Content/configure-devices.htm).

## <a name="configure-how-end-users-sign-in"></a>Nakonfigurovat, jak se koncoví uživatelé přihlásí

U zařízení zaregistrovaných v Intune s využitím KME pro Android můžete nakonfigurovat, jak se koncový uživatel přihlásí následujícím způsobem:

- **Bez přidružení uživatelského jména:** Na portálu Knox v části **Podrobnosti o zařízení**ponechte pole **ID uživatele** a **heslo** pro přidaná zařízení prázdná. Tato možnost vyžaduje, aby koncový uživatel při registraci do Intune zadal uživatelské jméno i heslo.

- **S přidružením uživatelského jména:** Na portálu Knox v části **Podrobnosti o zařízení**zadejte **ID uživatele** (například uživatelské jméno pro přiřazeného uživatele nebo účet [správce registrace zařízení](device-enrollment-manager-enroll.md) ) pro přidaná zařízení. Tato možnost předem vyplní uživatelské jméno a vyžaduje, aby koncový uživatel zadal heslo při registraci do Intune.

> [!NOTE]
>
>Přidružení uživatele se vztahuje pouze na zápis Správce zařízení s Androidem. Když je definováno přidružení uživatele, může zařízení zaregistrovat jenom přidružený uživatel pomocí KME. To platí i po obnovení továrního nastavení zařízení. Pokud na portálu Knox není definovaná žádná asociace uživatelů, může zařízení zaregistrovat libovolný uživatel s platnou licencí k Intune pomocí KME.
>U zařízení se systémem Android Enterprise s plnou správou, i když je definováno přidružení uživatele, se nepředá zařízení uživateli nebo zařízení nespojí.
>

## <a name="distribute-devices"></a>Distribuce zařízení

Po vytvoření a přiřazení profilu MDM, přiřazení uživatelského jména a identifikaci zařízení jako vlastněných společností v Intune, můžete zařízení distribuovat uživatelům.

Ještě potřebujete pomáhat? Projděte si kompletní [uživatelskou příručku KME](https://docs.samsungknox.com/KME-Getting-Started/Content/get-started.htm).

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

- **Podpora vlastníka zařízení:**  - **Podpora vlastníka zařízení:** Intune podporuje registraci vyhrazených a plně spravovaných zařízení pomocí portálu KME. Ostatní režimy pro vlastní nastavení zařízení s Androidem Enterprise budou podporované, protože budou dostupné v Intune.

- **Nepodporují se pracovní profil:** KME je metoda registrace podnikového zařízení a zařízení zaregistrovaná v pracovním profilu Android, která zajišťují, že pracovní a osobní údaje jsou oddělené na osobních zařízeních. To znamená, že registrace zařízení do pracovního profilu pomocí KME není podporovaným scénářem v Intune.

- **Obnovení továrního nastavení pro registraci do systému Android Enterprise:** Pokud zařízení ještě potřeba vyřadit, která už jsou nastavená, je potřeba při registraci do Androidu Enterprise obnovit tovární nastavení zařízení.

- **Aktualizace používající účet Google Play:** Google Play účet není nutný k zaregistrování zařízení do Microsoft Intune. V případě registrace Správce zařízení s Androidem ale můžou budoucí aktualizace Portál společnosti Intune aplikace vyžadovat na zařízení Google Play účet. Google Play účet není při registraci do vlastníka zařízení Google vyžadován.

- **Pole heslo se ignoruje:** Pokud se pole **heslo** naplní v části **Podrobnosti o zařízení** na portálu KNOX, ignoruje se při registraci Androidu aplikace Portál společnosti Intune. Aby bylo možné dokončit registraci zařízení, musí koncový uživatel zadat do zařízení heslo.


## <a name="getting-support"></a>Získání podpory
Přečtěte si další informace o [tom, jak získat podporu pro Samsung KME](https://docs.samsungknox.com/KME-Getting-Started/Content/to-get-kme-support.htm).


