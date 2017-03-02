---
title: "Konfigurace nastavení vzdělávání Intune pro iOS"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o nastavení Intune, pomocí kterých můžete řídit nastavení vzdělávání na zařízeních s iOSem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44c427f8-0f22-43c2-8c29-e0f9fa533b1f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 8d801c0b264e95348f55b1d4046c00e43ead5d10
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-configure-intune-education-settings-for-ios-devices-in-intune-azure-preview"></a>Konfigurace nastavení vzdělávání Intune pro zařízení s iOSem v Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="create-a-device-profile-containing-ios-education-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení vzdělávání pro iOS

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Konfigurovat zařízení**.
2. V okně **Konfigurace zařízení** vyberte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **Název** a **Popis** profilu pro upgrade edice.
5. Z rozevíracího seznamu **Platforma** zvolte **iOS**.
6. Z rozevíracího seznamu **Typ profilu** zvolte **Vzdělávání**.
7. V okně **Vzdělávání** vyberte následující:
    - **Soubor kořenového certifikátu učitele**
    - **Profil PKCS12/PFX učitele**
    - **Soubor kořenového certifikátu studenta**
    - **Profil PKCS12/PFX studenta**
8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.

