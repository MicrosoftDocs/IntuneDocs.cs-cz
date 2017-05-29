---
title: "Nastavení autority pro správu mobilních zařízení"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Postup nastavení autority pro správu mobilních zařízení v Intune "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c36ddef7e53d6f4f15c82c97dc6d18863e6859f1
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017

---

# <a name="set-the-mobile-device-management-authority"></a>Nastavení autority pro správu mobilních zařízení

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Nastavení autority pro správu mobilních zařízení (MDM) určuje způsob správy zařízení. Jako správce IT musíte nastavit autoritu MDM, aby uživatelé mohli registrovat zařízení pro správu.

Možné konfigurace:

- **Intune Standalone** – jedná se o pouze cloudovou správu, kterou můžete nakonfigurovat pomocí portálu Azure Portal. Zahrnuje celou sadu možností, které Intune nabízí. [Nastavte autoritu MDM v konzole Intune](#mdm-authority-set-to-intune).

- **Intune Hybrid** – jedná se o integraci cloudového řešení Intune se System Center Configuration Managerem. Intune můžete konfigurovat pomocí konzoly Configuration Manager. [Nastavte autoritu MDM v nástroji Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Správa mobilních zařízení pro Office 365** – jedná se o integraci Office 365 s cloudovým řešením Intune. Intune můžete konfigurovat z Centra pro správu Office 365. Zahrnuje dílčí sadu možností, které jsou dostupné s Intune Standalone. Nastavte autoritu MDM v Centru pro správu Office 365.

>[!IMPORTANT]
>Po nastavení autority pro správu mobilních zařízení budete muset kontaktovat [Podporu Microsoftu](https://docs.microsoft.com/intune-classic/troubleshoot/get-support), aby provedli změnu, takže vybírejte pečlivě.

## <a name="set-mdm-authority-to-intune"></a>Nastavení autority MDM na Intune

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.
  ![Snímek obrazovky s úlohou Řešení potíží Intune a s odkazem Vybrat uživatele](media/set-mdm-auth.png)
2. V okně Intune zvolte **Registrace zařízení** a pak zvolte **Přehled**.

3. V okně **Začátek správy zařízení** zvolte **Nastavit autoritu MDM na Intune**. Zobrazí se zpráva, že jste úspěšně nastavili autoritu MDM na Intune.

