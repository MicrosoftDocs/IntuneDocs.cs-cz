---
title: "Nastavení autority pro správu mobilních zařízení | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Postup nastavení autority pro správu mobilních zařízení v Intune "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 3c0de501c172484f036aa2d812f0c40fcfa1d93f

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

1. Na portálu Azure Portal zvolte **Další služby**, do textového pole zadejte **Intune** a pak zvolte **Jiné** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Přehled**.

3. V okně **Začátek správy zařízení** zvolte **Nastavit autoritu MDM na Intune**. Zobrazí se zpráva, že jste úspěšně nastavili autoritu MDM na Intune.



<!--HONumber=Feb17_HO1-->


