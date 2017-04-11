---
title: "Nastavení autority pro správu mobilních zařízení"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Postup nastavení autority pro správu mobilních zařízení v Intune "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 9d7a1a934188f0a40553d3c6b8b567ba8f6af034
ms.lasthandoff: 02/18/2017

---

# <a name="set-the-mobile-device-management-authority"></a>Nastavení autority pro správu mobilních zařízení 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Nastavení autority pro správu mobilních zařízení určuje způsob správy zařízení. Možné konfigurace:

- **Intune Standalone** – jedná se o pouze cloudovou správu, kterou můžete nakonfigurovat pomocí portálu Azure Portal. Zahrnuje celou sadu možností, které Intune nabízí.

- **Intune Hybrid** – jedná se o integraci cloudového řešení Intune se System Center Configuration Managerem. Intune můžete konfigurovat pomocí konzoly Configuration Manager.

- **Správa mobilních zařízení pro Office 365** – jedná se o integraci Office 365 s cloudovým řešením Intune. Intune můžete konfigurovat z Centra pro správu Office 365. Zahrnuje dílčí sadu možností, které jsou dostupné s Intune Standalone.

>[!IMPORTANT]
>Po nastavení autority pro správu mobilních zařízení budete muset kontaktovat [Podporu Microsoftu](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune), aby provedli změnu, takže vybírejte pečlivě.

**Nastavení autority pro správu mobilních zařízení:**

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování a správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Přehled**.

3. V okně **Začátek správy zařízení** zvolte **Nastavit autoritu MDM na Intune**. Zobrazí se zpráva, že jste úspěšně nastavili autoritu MDM na Intune.

