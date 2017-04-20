---
title: "Přidání identifikátorů IMEI do Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si, jak přidat podnikové identifikátory (kódy IMEI) do Microsoft Intune. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 4ebd74c77145464574a1fed878ec4dbc2eb3c271
ms.openlocfilehash: 7bb8168c442a3340e8c185f1908acd9be15cab05
ms.lasthandoff: 04/05/2017

---

# <a name="add-corporate-identifiers"></a>Přidání podnikových identifikátorů

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Jako správce IT můžete vytvořit a importovat textový soubor s oddělovači (CSV) se seznamem čísel IMEI (International Mobile Equipment Identity), který vám umožní identifikovat zařízení ve vlastnictví firmy. Každé číslo IMEI může mít v tomto seznamu uvedené podrobnosti pro účely správy.

Sériová čísla pro zařízení s iOSem ve vlastnictví firmy se při nahrávání musí spárovat s firemním registračním profilem. Zařízení se pak musí zaregistrovat pomocí programu registrace zařízení (DEP) společnosti Apple nebo Apple Configuratoru, aby se zobrazovala jako zařízení ve vlastnictví firmy. 

## <a name="create-a-csv-file"></a>Vytvoření souboru CSV
Pokud chcete vytvořit seznam, vytvořte seznam hodnot oddělených čárkami se dvěma sloupci (.csv) bez záhlaví. Do levého sloupce přidejte identifikátor IMEI a v pravém sloupci uveďte podrobnosti. Podrobnosti jsou omezené na 128 znaků. Současný limit jednoho souboru CSV je 500 řádků.

**Nahráním souboru .csv se sériovými čísly** – Vytvořte seznam oddělený čárkami (.csv), který bude mít dva sloupce, a nebude mít záhlaví. Soubor .csv může obsahovat maximálně 5000 zařízení, ale jeho velikost nesmí překročit 5 MB.

|||
|-|-|
|&lt;IMEI č. 1&gt;|&lt;Podrobnosti o zařízení č. 1&gt;|
|&lt;IMEI č. 2&gt;|&lt;Podrobnosti o zařízení č. 2&gt;|

    This .csv file when viewed in a text editor appears as:

    ```
    01 234567 890123,device details
    02 234567 890123,device details
    ```

**Předání seznamu firemních zařízení ve formátu .csv**

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Identifikátory podnikových zařízení**.

3. Pokud importujete soubor s novými podrobnostmi, které mají přepsat ty stávající, vyberte **Přepište podrobnosti u existujících identifikátorů** a nové podrobnosti nahradí stávající.

4. Přejděte do souboru IMEI CSV a vyberte **Přidat**.

> [!IMPORTANT]
> Některá zařízení s Androidem mají více kódů IMEI. Intune má v inventáři jeden kód IMEI pro každé zařízení. Pokud importujete kód IMEI, který ale není kódem IMEI, který má v inventáři služba Intune, bude zařízení označené jako osobní, a ne jako firemní. Pokud importujete více kódů IMEI pro jedno zařízení, zobrazí se u kódů, které nejsou v inventáři, stav registrace **Neznámý**.

Jakmile bude import hotový, tato zařízení mohou nebo nemusí být zaregistrována a mohou získat stav buď **Zaregistrované**, nebo **Nekontaktované**. **Nekontaktované** znamená, že toto zařízení nikdy se službou Intune nekomunikovalo.

## <a name="delete-a-csv-list"></a>Odstranění seznamu CSV

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Identifikátory podnikových zařízení**.

3. Zvolte **Odstranit**.

Podrobné specifikace o číslech IMEI najdete na stránce [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

