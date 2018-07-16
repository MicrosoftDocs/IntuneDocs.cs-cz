---
title: Vytvoření profilů zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Můžete přidat nebo konfigurovat profil zařízení v Microsoft Intune, včetně výběru typu platformy a konfigurace nastavení na portálu Azure Portal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a9fb84fd15eb68f007e820e473dd9edf55b37777
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905015"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Vytvořte profil zařízení v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Vytvoření profilu
1. Na portálu [Azure Portal](https://portal.azure.com) vyberte **Všechny služby** a vyhledejte **Microsoft Intune**.

2. V **Microsoft Intune** vyberte **Konfigurace zařízení** a pak **Profily**. Pak vyberte **Vytvořit profil**.

3. Zadejte tyto vlastnosti:

   - **Název**: Zadejte popisný název nového profilu.
   - **Popis**: Zadejte popis profilu. (Ten je nepovinný, ale doporučuje se ho zadat.)
   - **Platforma**: Vyberte typ platformy:  

       - **Androidemem**
       - **Pracovní profily Androidu**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 a novější**
       - **Windows 10 a novější**

   - **Typ profilu**: Vyberte typ, který chcete vytvořit. Seznam závisí na platformě, kterou vyberete.
   - **Nastavení**: Informace o nastaveních pro jednotlivé typy profilů najdete v následujících tématech:

       -  [Funkce zařízení](device-features-configure.md)
       -  [Omezení zařízení](device-restrictions-configure.md)
       -  [Endpoint Protection](endpoint-protection-configure.md)
       -  [Veřejný terminál](kiosk-settings.md)
       -  [E-mail](email-settings-configure.md)
       -  [VPN](vpn-settings-configure.md)
       -  [Wi-Fi](wi-fi-settings-configure.md)
       -  Education pro [Windows 10](education-settings-configure.md) a [iOS](wi-fi-settings-ios.md)
       -  [Upgrade edice Windows 10](edition-upgrade-configure-windows-10.md)
       -  [Zásady aktualizací pro iOS](software-updates-ios.md)
       -  [Certifikáty](certificates-configure.md)
       -  [Windows Information Protection](windows-information-protection-configure.md)
       -  [Vlastní](custom-settings-configure.md)

     ![Snímek obrazovky znázorňující vytvoření profilu](./media/create-device-profile.png)

4. Po dokončení vyberte **Vytvořit**.

Profil se vytvoří a zobrazí se v seznamu.

## <a name="next-steps"></a>Další kroky
[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
