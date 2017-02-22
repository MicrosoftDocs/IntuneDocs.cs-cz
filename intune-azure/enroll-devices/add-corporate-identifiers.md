---
title: "Jak přidat do Intune identifikátory IMEI | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Přečtěte si, jak přidat podnikové identifikátory (kódy IMEI) do Microsoft Intune. "
keywords: 
author: staciebarker
ms.author: stabark
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: e134a6e3ff143dacce1d70ef0ab44ade0722ed57

---

# <a name="add-corporate-identifiers"></a>Přidání podnikových identifikátorů

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Pro účely identifikace zařízení vaší firmy můžete vytvořit seznam čísel IMEI (International Mobile Equipment Identity). Tato zařízení můžou nebo nemusí být zaregistrovaná a mají stav Zaregistrované nebo Nekontaktované. Nekontaktované znamená, že se zařízení nikdy neregistruje ve službě Intune.

Pokud chcete vytvořit seznam, vytvořte seznam hodnot oddělených čárkami se dvěma sloupci (.csv) bez záhlaví. Do levého sloupce přidejte identifikátor IMEI a v pravém sloupci uveďte podrobnosti. Aktuálně je maximální počet řádků v seznamu 500.

V textovém editoru vypadá seznam CSV přibližně takto:

01 234567 890123,podrobnosti o zařízení</br>
02 234567 890123,podrobnosti o zařízení

**Předání seznamu firemních zařízení ve formátu .csv**

1. Na portálu Azure Portal zvolte **Další služby**, do textového pole zadejte **Intune** a pak zvolte **Jiné** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Identifikátory podnikových zařízení**.

3. Pokud importujete soubor s novými podrobnostmi, které mají přepsat ty stávající, vyberte **Přepište podrobnosti u existujících identifikátorů** a nové podrobnosti nahradí stávající.

4. Přejděte do souboru IMEI CSV a vyberte **Přidat**.

**Odstranění seznamu firemních zařízení ve formátu .csv**

1. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Identifikátory podnikových zařízení**.

2. Zvolte **Odstranit**.



<!--HONumber=Feb17_HO1-->


