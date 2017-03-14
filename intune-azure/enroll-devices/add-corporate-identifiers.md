---
title: "Přidání identifikátorů IMEI do Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si, jak přidat podnikové identifikátory (kódy IMEI) do Microsoft Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 0d7c8eedbdad917a43d43d2e79ead5663e8e2871
ms.lasthandoff: 02/18/2017

---

# <a name="add-corporate-identifiers"></a>Přidání podnikových identifikátorů

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Pro účely identifikace zařízení vaší firmy můžete vytvořit seznam čísel IMEI (International Mobile Equipment Identity). Tato zařízení můžou nebo nemusí být zaregistrovaná a mají stav Zaregistrované nebo Nekontaktované. Nekontaktované znamená, že se zařízení nikdy neregistruje ve službě Intune.

Pokud chcete vytvořit seznam, vytvořte seznam hodnot oddělených čárkami se dvěma sloupci (.csv) bez záhlaví. Do levého sloupce přidejte identifikátor IMEI a v pravém sloupci uveďte podrobnosti. Aktuálně je maximální počet řádků v seznamu 500.

V textovém editoru vypadá seznam CSV přibližně takto:

01 234567 890123,podrobnosti o zařízení</br>
02 234567 890123,podrobnosti o zařízení

**Předání seznamu firemních zařízení ve formátu .csv**

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Identifikátory podnikových zařízení**.

3. Pokud importujete soubor s novými podrobnostmi, které mají přepsat ty stávající, vyberte **Přepište podrobnosti u existujících identifikátorů** a nové podrobnosti nahradí stávající.

4. Přejděte do souboru IMEI CSV a vyberte **Přidat**.

**Odstranění seznamu firemních zařízení ve formátu .csv**

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Identifikátory podnikových zařízení**.

3. Zvolte **Odstranit**.

