---
title: "Přidání podnikových identifikátorů do Intune"
titleSuffix: Intune on Azure
description: "Zjistěte, jak můžete do Microsoft Intune přidat podnikové identifikátory (způsob registrace, číslo IMEI a sériové číslo). \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 03a278762401ee9697909cf45b3fe86212393e66
ms.sourcegitcommit: 0b164f806165d312acfc88815a60e325e3d02672
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/21/2017
---
# <a name="add-corporate-identifiers"></a>Přidání podnikových identifikátorů

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako správce Intune můžete zařízení ve firemním vlastnictví identifikovat různými způsoby. Ze zařízení ve firemním vlastnictví dokáže Intune shromažďovat dodatečné informace. U zařízení můžete také nastavit omezení a zabránit registraci zařízení, která nejsou ve firemním vlastnictví.

Zařízení se identifikuje jako ve vlastnictví firmy, pokud je splněná libovolná z následujících podmínek:

- Je registrované pomocí nějakého účtu [správce registrace zařízení](device-enrollment-manager-enroll.md) (všechny platformy)
- Je registrované přes [Program registrace zařízení](device-enrollment-program-enroll-ios.md) od Applu, [Apple School Manager](apple-school-manager-set-up-ios.md) nebo [Apple Configurator](apple-configurator-enroll-ios.md) (jen iOS)
- Je předem deklarované pomocí čísla IMEI (International Mobile Equipment Identifier) (všechny platformy s číslem IMEI) nebo sériového čísla (iOS a Android)
- Je registrované ve službě Azure Active Directory nebo Enterprise Mobility Suite jako zařízení s Windows 10 Enterprise (jen Windows 10)
- Je označené jako **Firemní** ve **vlastnostech** zařízení

V záznamech zařízení v Intune se u zařízení ve firemním vlastnictví zobrazuje ve sloupci **Vlastnictví** text **Firemní**. Zobrazíte je tak, že přejdete na **Zařízení** > **Všechna zařízení**.

## <a name="predeclare-a-device-with-imei-or-serial-number"></a>Předběžná deklarace zařízení pomocí čísla IMEI nebo sériového čísla

Jako správce Intune můžete vytvořit a naimportovat textový soubor s oddělovači (.csv) se seznamem čísel IMEI nebo sériových čísel. Intune pomocí těchto identifikátorů určuje, která zařízení jsou ve vlastnictví firmy. Můžete deklarovat čísla IMEI všech podporovaných platforem. Je možné deklarovat pouze sériová čísla zařízení s iOSem a Androidem. Každý kód IMEI nebo sériové číslo může mít v tomto seznamu uvedené podrobnosti pro účely správy.

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

### <a name="add-a-csv-list-of-corporate-identifiers"></a>Přidání seznamu podnikových identifikátorů ve formátu .csv

1. V Intune na Azure Portalu zvolte **Registrace zařízení** > **Identifikátory podnikových zařízení** a klikněte na **Přidat**.

 ![Snímek obrazovky pracovního prostoru s identifikátorem podnikového zařízení a zvýrazněným tlačítkem Přidat.](./media/add-corp-id.png)

2. V okně **Přidat identifikátory** zadejte typ identifikátoru: **IMEI** nebo **Sériové**. Můžete určit, jestli se má pro dříve importovaná čísla použít nastavení **Přepište podrobnosti u existujících identifikátorů**.

3. Klikněte na ikonu složky a určete cestu k seznamu, který chcete importovat. Přejděte do souboru .csv a vyberte **Přidat**. Pokud se chcete podívat na identifikátory nového zařízení, můžete kliknout na **Aktualizovat**.

Importovaná zařízení nemusí být nutně zaregistrovaná. Zařízení můžou mít stav **Zaregistrované** nebo **Nekontaktované**. **Nekontaktované** znamená, že toto zařízení nikdy se službou Intune nekomunikovalo.

## <a name="delete-corporate-identifiers"></a>Odstranění podnikových identifikátorů

1. V Intune na Azure Portalu zvolte **Registrace zařízení** > **Identifikátory podnikových zařízení**.
2. Vyberte identifikátory zařízení, které chcete odstranit, a zvolte **Odstranit**.
3. Potvrďte odstranění.

Při odstranění podnikového identifikátoru zaregistrovaného zařízení se nezmění vlastnictví zařízení. Pokud chcete změnit vlastnictví zařízení, přejděte na **Zařízení** > **Všechna zařízení**, vyberte zařízení, zvolte **Vlastnosti** a změňte **Vlastnictví zařízení**.

## <a name="imei-specifications"></a>Specifikace IMEI
Podrobné specifikace o číslech IMEI najdete na stránce [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).
