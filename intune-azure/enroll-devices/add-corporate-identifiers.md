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
ms.sourcegitcommit: 15415f9f31d520d66257df3a7e134e4b1de8467c
ms.openlocfilehash: 8c9e6b39ee01697d993e5738ec35e8a64fc8e236
ms.lasthandoff: 04/07/2017

---

# <a name="add-corporate-identifiers"></a>Přidání podnikových identifikátorů

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Jako správce IT můžete vytvořit a importovat textový soubor s oddělovači (CSV) se seznamem čísel IMEI (International Mobile Equipment Identity), který vám umožní identifikovat zařízení ve vlastnictví firmy. Každé číslo IMEI může mít v tomto seznamu uvedené podrobnosti pro účely správy.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

## <a name="add-corporate-identifiers"></a>Přidání podnikových identifikátorů
Pokud chcete vytvořit seznam, vytvořte seznam hodnot oddělených čárkami se dvěma sloupci (.csv) bez záhlaví. Do levého sloupce přidejte identifikátor IMEI a v pravém sloupci uveďte podrobnosti. Podrobnosti jsou omezené na 128 znaků a používají se jenom pro účely správy. Na zařízení se podrobnosti nezobrazují. Současný limit jednoho souboru CSV je 500 řádků.

**Nahráním souboru .csv se sériovými čísly** – Vytvořte seznam oddělený čárkami (.csv), který bude mít dva sloupce, a nebude mít záhlaví. Soubor .csv může obsahovat maximálně 5000 zařízení, ale jeho velikost nesmí překročit 5 MB.

|||
|-|-|
|&lt;IMEI č. 1&gt;|&lt;Podrobnosti o zařízení č. 1&gt;|
|&lt;IMEI č. 2&gt;|&lt;Podrobnosti o zařízení č. 2&gt;|

V textovém editoru vypadá soubor .csv takhle:

```
01 234567 890123,device details
02 234567 890123,device details
```


> [!IMPORTANT]
> Některá zařízení s Androidem mají více kódů IMEI. Intune má v inventáři jeden kód IMEI pro každé zařízení. Pokud importujete kód IMEI, který ale není kódem IMEI, který má v inventáři služba Intune, bude zařízení označené jako osobní, a ne jako firemní. Pokud importujete více kódů IMEI pro jedno zařízení, zobrazí se u kódů, které nejsou v inventáři, stav registrace **Neznámý**.

**Předání seznamu firemních zařízení ve formátu .csv**

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune zvolte **Registrace zařízení** > **Omezení registrace**, zvolte **Identifikátory podnikových zařízení** a pak klikněte na **Přidat**.

3. V okně **Přidat identifikátory** zadejte typ identifikátoru **IMEI**. Můžete určit, jestli se má pro dříve importovaná čísla použít nastavení **Přepište podrobnosti u existujících identifikátorů**.  

4. Klikněte na ikonu složky a určete cestu k seznamu, který chcete importovat. Přejděte do souboru IMEI CSV a vyberte **Přidat**.

Jakmile bude import hotový, tato zařízení mohou nebo nemusí být zaregistrována a mohou získat stav buď **Zaregistrované**, nebo **Nekontaktované**. **Nekontaktované** znamená, že toto zařízení nikdy se službou Intune nekomunikovalo.

## <a name="delete--corporate-identifiers"></a>Odstranění podnikových identifikátorů

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune zvolte **Registrace zařízení** > **Omezení registrace**, zvolte **Identifikátory podnikových zařízení** a pak zvolte **Odstranit**.

3. V okně **Odstranit identifikátory** přejděte na soubor .csv s identifikátory zařízení, které chcete odstranit, a pak klikněte na **Odstranit**.

## <a name="imei-specifications"></a>Specifikace IMEI
Podrobné specifikace o číslech IMEI najdete na stránce [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

