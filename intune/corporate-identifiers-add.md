---
title: "Přidání identifikátorů IMEI do Intune"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak přidat podnikové identifikátory (kódy IMEI) do Microsoft Intune. \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a9852759983a4bc68c596146e2f5691893376cfd
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2017
---
# <a name="add-corporate-identifiers"></a>Přidání podnikových identifikátorů

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako správce Intune můžete vytvořit a importovat textový soubor s oddělovači (CSV) se seznamem kódů IMEI (International Mobile Equipment Identity) nebo sériových čísel. Intune pomocí těchto identifikátorů určuje, která zařízení jsou ve vlastnictví firmy. Je možné deklarovat jenom čísla IMEI všech podporovaných platforem. Je možné deklarovat pouze sériová čísla zařízení s iOSem a Androidem. Každý kód IMEI nebo sériové číslo může mít v tomto seznamu uvedené podrobnosti pro účely správy.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Přečtete si, jak zjistit sériové číslo zařízení Apple](https://support.apple.com/HT204308).<br>
[Přečtete si, jak zjistit sériové číslo zařízení s Androidem](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers"></a>Přidání podnikových identifikátorů
Pokud chcete vytvořit seznam, vytvořte seznam hodnot oddělených čárkami se dvěma sloupci (.csv) bez záhlaví. Do levého sloupce přidejte kód IMEI nebo sériové číslo a v pravém sloupci uveďte podrobnosti. V rámci jednoho souboru .csv můžete importovat pouze jeden typ identifikačního čísla: buď IMEI, nebo sériové číslo. Podrobnosti jsou omezené na 128 znaků a používají se jenom pro účely správy. Na zařízení se podrobnosti nezobrazují. Současný limit jednoho souboru CSV je 500 řádků.

**Nahráním souboru .csv se sériovými čísly** – Vytvořte seznam oddělený čárkami (.csv), který bude mít dva sloupce, a nebude mít záhlaví. Soubor .csv může obsahovat maximálně 5000 zařízení, ale jeho velikost nesmí překročit 5 MB.

|||
|-|-|
|&lt;ID č. 1&gt;|&lt;Podrobnosti o zařízení č. 1&gt;|
|&lt;ID č. 2&gt;|&lt;Podrobnosti o zařízení č. 2&gt;|

V textovém editoru vypadá soubor .csv takhle:

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> Některá zařízení s Androidem mají více kódů IMEI. Intune dokáže přečíst jen jeden kód IMEI na každé zaregistrované zařízení. Pokud importujete kód IMEI, který ale není kódem IMEI v inventáři služby Intune, označí se zařízení jako osobní, a ne jako firemní. Pokud importujete více kódů IMEI pro jedno zařízení, zobrazí se u kódů, které nejsou v inventáři, stav registrace **Neznámý**.<br>
>Poznámka: Sériová čísla Androidu nemusí být jedinečná nebo existovat. Pokud chcete zjistit, jestli je sériové číslo spolehlivým identifikátorem zařízení, obraťte se na dodavatele zařízení.
>Sériová čísla, která službě Intune oznámí zařízení, se nemusí shodovat se zobrazenými identifikátory v nabídkách zařízení Nastavení/ O zařízení. Ověřte si typ sériového čísla oznámeného výrobcem zařízení.


**Předání seznamu firemních zařízení ve formátu .csv**

1. Na portálu Intune zvolte **Registrace zařízení** > **Omezení registrace**, zvolte **Identifikátory podnikových zařízení** a pak klikněte na **Přidat**.

 ![Snímek obrazovky pracovního prostoru s identifikátorem podnikového zařízení a zvýrazněným tlačítkem Přidat.](./media/add-corp-id.png)

2. V okně **Přidat identifikátory** zadejte typ identifikátoru: **IMEI** nebo **Sériové**. Můžete určit, jestli se má pro dříve importovaná čísla použít nastavení **Přepište podrobnosti u existujících identifikátorů**.

3. Klikněte na ikonu složky a určete cestu k seznamu, který chcete importovat. Přejděte do souboru .csv a vyberte **Přidat**. Pokud se chcete podívat na identifikátory nového zařízení, můžete kliknout na **Aktualizovat**.

Importovaná zařízení nemusí být nutně zaregistrovaná. Zařízení můžou mít stav **Zaregistrované** nebo **Nekontaktované**. **Nekontaktované** znamená, že toto zařízení nikdy se službou Intune nekomunikovalo.

## <a name="delete-corporate-identifiers"></a>Odstranění podnikových identifikátorů

1. Na portálu Intune zvolte **Registrace zařízení** > **Omezení registrace**, zvolte **Identifikátory podnikových zařízení** a pak zvolte **Odstranit**.

3. V okně **Odstranit identifikátory** přejděte na soubor .csv s identifikátory zařízení, které chcete odstranit, a pak klikněte na **Odstranit**.

## <a name="imei-specifications"></a>Specifikace IMEI
Podrobné specifikace o číslech IMEI najdete na stránce [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).
