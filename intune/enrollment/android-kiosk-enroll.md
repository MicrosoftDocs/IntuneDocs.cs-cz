---
title: Setup Intune enrollment for Android Enterprise dedicated devices
titleSuffix: Microsoft Intune
description: Learn how to enroll Android Enterprise dedicated devices in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d4ff9126fec182d1e0d2f3eb75297ede8a632e2e
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390728"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-dedicated-devices"></a>Set up Intune enrollment of Android Enterprise dedicated devices

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Android Enterprise supports corporate-owned, single-use, kiosk-style devices with its dedicated devices solution set. Taková zařízení se používají k jednomu účelu, například jako zobrazovací zařízení na veřejných místech, k tisku vstupenek nebo k evidenci zásob. Správci omezí použití zařízení na omezenou sadu aplikací a webových odkazů. Uživatelé zároveň nemůžou na tomto zařízení přidávat jiné aplikace ani provádět jiné akce.

Intune helps you deploy apps and settings to Android Enterprise dedicated devices. For specific details about Android Enterprise, see [Android enterprise requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Zařízení, která se spravují tímto způsobem, jsou v Intune zaregistrovaná bez uživatelského účtu a nejsou přidružená k žádnému koncovému uživateli. Nejsou určená pro osobní používání aplikací, které závisejí na datech spojených s účtem konkrétního uživatele, jako je Outlook nebo Gmail.

## <a name="device-requirements"></a>Device requirements

Devices must meet these requirements to be managed as an Android Enterprise dedicated device:

- Verze operačního systému Android 5.1 a vyšší
- Zařízení musí používat distribuci Androidu s připojením ke službě GMS (Google Mobile Services). Zařízení musí mít dostupnou službu GMS a musí být schopna se k této službě připojit.

## <a name="set-up-android-enterprise-dedicated-device-management"></a>Set up Android Enterprise dedicated device management

To set up Android Enterprise dedicated device management, follow these steps:

1. Při přípravě na správu mobilních zařízení musíte [nastavit autoritu pro správu mobilních zařízení (MDM) na **Microsoft Intune**](../fundamentals/mdm-authority-set.md) podle pokynů. Tato možnost se nastavuje jenom jednou při prvním nastavování Intune pro správu mobilních zařízení.
2. [Connect your Intune tenant account to your Managed Google Play account](connect-intune-android-enterprise.md).
3. [Vytvořte registrační profil](#create-an-enrollment-profile).
4. [Vytvořte skupinu zařízení](#create-a-device-group).
5. [Enroll the dedicated devices](#enroll-the-dedicated-devices).

### <a name="create-an-enrollment-profile"></a>Create an enrollment profile

> [!NOTE]
> If a token has expired, the profile associated with it will not be displayed in **Device enrollment** > **Android enrollment** > **Corporate-owned dedicated devices**. To see all profiles associated with both active and inactive tokens, click on **Filter** and check the boxes for both "Active" and "Inactive" policy states. 

You must create an enrollment profile so that you can enroll your dedicated devices. Po vytvoření poskytne tento profil registrační token (náhodný řetězec) a kód QR. Depending on the Android OS and version of the device, you can use either the token or QR code to [enroll the dedicated device](#enroll-the-dedicated-devices).

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) and choose **Device enrollment** > **Android enrollment** > **Corporate-owned dedicated devices**.
2. Zvolte **Vytvořit** a vyplňte požadovaná pole.
    - **Název**: Zadejte název, který použijete při přiřazení tohoto profilu k dynamické skupině zařízení.
    - **Datum vypršení platnosti tokenu**: Datum, kdy vyprší platnost tokenu. Google vynucuje maximálně 90 dnů.
3. Uložte profil pomocí tlačítka **Vytvořit**.

### <a name="create-a-device-group"></a>Vytvoření skupiny zařízení

Aplikace a zásady můžete cílit buď na přiřazené, nebo dynamické skupiny zařízení. Následujícím postupem nakonfigurujete dynamické skupiny zařízení služby AAD tak, aby se automaticky naplnily zařízeními, která se zaregistrují s konkrétním registračním profilem:

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) and choose **Groups** > **All groups** > **New group**.
2. V okně **Skupina** vyplňte požadovaná pole následujícím způsobem:
    - **Typ skupiny**: Zabezpečení
    - **Název skupiny**: Zadejte výstižný název (například Zařízení závodu 1).
    - **Typ členství**: Dynamické zařízení
3. Zvolte **Přidat dynamický dotaz**.
4. V okně **Pravidla dynamického členství** vyplňte pole následujícím způsobem:
    - **Přidat dynamické pravidlo členství**: Jednoduché pravidlo
    - **Přidat zařízení, kde**: Název registračního profilu
    - In the middle box, choose **Equals**.
    - Do posledního pole zadejte název dříve vytvořeného registračního profilu.
    Další informace o pravidlech dynamického členství najdete v tématu [Pravidla dynamického členství pro skupiny v AAD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership). 
5. Zvolte **Přidat dotaz** > **Vytvořit**.

### <a name="replace-or-remove-tokens"></a>Nahrazení nebo odebrání tokenů

- **Nahrazení tokenu**: Příkazem Nahradit token můžete vygenerovat nový token nebo kód QR, pokud brzy vyprší platnost stávajícího.
- **Odvolání tokenu**: Platnost tokenu nebo kódu QR můžete nechat okamžitě vypršet. Od tohoto okamžiku nebude token nebo kód QR použitelný. Tuto možnost můžete použít, pokud:
  - Omylem nasdílíte token nebo kód QR s neautorizovanou stranou
  - Dokončíte všechny registrace a token nebo kód QR už nepotřebujete

Nahrazení nebo odvolání tokenu/kódu QR nebude mít žádný vliv na zařízení, která už jsou zaregistrovaná.

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) and choose **Device enrollment** > **Android enrollment** > **Coporate-owned dedicated devices**.
2. Zvolte profil, se kterým chcete pracovat.
3. Zvolte **Token**.
4. Pokud chcete token nahradit, zvolte **Nahradit token**.
5. Pokud chcete token odvolat, zvolte **Odvolat token**.

## <a name="enroll-the-dedicated-devices"></a>Enroll the dedicated devices

You can now [enroll your dedicated devices](android-dedicated-devices-fully-managed-enroll.md).

> [!NOTE]
> The **Microsoft Intune** app will be automatically installed during enrollment of a dedicated device.  This app is required for enrollment and cannot be uninstalled. 

## <a name="managing-apps-on-android-enterprise-dedicated-devices"></a>Managing apps on Android Enterprise dedicated devices

Only apps that have Assignment type [set to Required](../apps/apps-deploy.md#assign-an-app) can be installed on Android Enterprise dedicated devices. Apps are installed from the Managed Google Play store in the same manner as Android Enterprise work profile devices.

Když vývojář aplikace publikuje aktualizaci do obchodu Google Play, aktualizují se aplikace na spravovaných zařízeních automaticky.

To remove an app from Android Enterprise dedicated devices, you can do either of the following:
- Odstranění nasazení povinné aplikace
- Vytvoření nasazení odinstalace pro tuto aplikaci

## <a name="next-steps"></a>Další kroky
- [Deploy Android apps](../apps/apps-deploy.md)
- [Add Android configuration policies](../configuration/device-profiles.md)
