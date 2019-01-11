---
title: Vytvoření profilů zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Můžete přidat nebo konfigurovat profil zařízení v Microsoft Intune, včetně výběru typu platformy a konfigurace nastavení na portálu Azure Portal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: cb6e3f0a9f62348d55b5dc2284c1007ea7faf088
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203208"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Vytvořte profil zařízení v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Vytvoření profilu

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.

2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.

3. Zadejte tyto vlastnosti:

   - **Název**: Zadejte popisný název pro nový profil.
   - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
   - **Platforma**: Vyberte typ platformy:  

       - **Android**
       - **Android Enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 a novější**
       - **Windows 10 a novější**

   - **Typ profilu**: Vyberte typ, který chcete vytvořit. Seznam závisí na platformě, kterou vyberete.
   - **Nastavení**: Informace o nastaveních pro jednotlivé typy profilů najdete v následujících článcích:

       -  [Funkce zařízení](device-features-configure.md)
       -  [Omezení zařízení](device-restrictions-configure.md)
       -  [Endpoint Protection](endpoint-protection-configure.md)
       -  [Ochrana identit](identity-protection-configure.md)  
       -  [Veřejný terminál](kiosk-settings.md)
       -  [E-mailu](email-settings-configure.md)
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

## <a name="next-steps"></a>Další postup
[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
