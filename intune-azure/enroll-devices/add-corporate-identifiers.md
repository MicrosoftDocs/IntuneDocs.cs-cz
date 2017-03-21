---
title: "Přidání identifikátorů IMEI do Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si, jak přidat podnikové identifikátory (kódy IMEI) do Microsoft Intune. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: d8cb15d1b8c1c100f15084e43d2c3c4633fd64b5
ms.openlocfilehash: f12d538b1f4cd327b893d234f2b558185cdd9d85
ms.lasthandoff: 03/09/2017

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

> [!IMPORTANT]
> Některá zařízení s Androidem mají více kódů IMEI. Intune má v inventáři jeden kód IMEI pro každé zařízení. Pokud importujete kód IMEI, který ale není kódem IMEI, který má v inventáři služba Intune, bude zařízení označené jako osobní, a ne jako firemní. Pokud importujete více kódů IMEI pro jedno zařízení, zobrazí se u kódů, které nejsou v inventáři, stav registrace **Neznámý**.

**Odstranění seznamu firemních zařízení ve formátu .csv**

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Identifikátory podnikových zařízení**.

3. Zvolte **Odstranit**.

