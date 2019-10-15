---
title: Přidání podnikových identifikátorů do Intune
titleSuffix: ''
description: Přečtěte si, jak přidat podnikové identifikátory (metodu registrace, IMEI a sériová čísla) do Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: afc9d953e1d324adb3f00eb5209732a858bbbcda
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314676"
---
# <a name="identify-devices-as-corporate-owned"></a>Identifikace zařízení jako vlastněných společností

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Jako správce Intune můžete zařízení identifikovat jako ve vlastnictví firmy a upřesnit tak správu a identifikaci. Intune může provádět další úlohy správy a shromažďovat další informace, jako je celé telefonní číslo a inventář aplikací ze zařízení vlastněných společností. Můžete také nastavit omezení zařízení a zablokovat registraci zařízení, která nejsou ve vlastnictví firmy.

V době registrace Intune automaticky přiřazuje stav zařízení ve vlastnictví firmy do zařízení, která jsou:

- Zaregistrováno pomocí účtu [správce registrace zařízení](device-enrollment-manager-enroll.md) (všechny platformy)
- Zaregistrované ve službě Apple [program registrace zařízení](device-enrollment-program-enroll-ios.md), [Apple School Manager](apple-school-manager-set-up-ios.md)nebo [Apple Configuratoru](apple-configurator-enroll-ios.md) (jenom iOS)
- [Identifikováno jako ve vlastnictví firmy před](#identify-corporate-owned-devices-with-imei-or-serial-number) registrací s čísly IMEI (International Mobile Equipment Identifier) (všechny platformy s čísly IMEI) nebo sériovým číslem (iOS a Android)
- Připojí se k Azure Active Directory pomocí pracovních nebo školních přihlašovacích údajů. [Zařízení, která jsou Azure Active Directory registrována](https://docs.microsoft.com/azure/active-directory/devices/overview) , budou označena jako osobní.
- Nastavení jako firemní v [seznamu vlastností zařízení](#change-device-ownership)

Po registraci můžete [změnit nastavení vlastnictví](#change-device-ownership) mezi **osobními** a **firemními**.

## <a name="identify-corporate-owned-devices-with-imei-or-serial-number"></a>Identifikace zařízení vlastněných společností pomocí IMEI nebo sériového čísla

Jako správce Intune můžete vytvořit a importovat textový soubor s oddělovači (. csv), který obsahuje 14 číslic nebo sériová čísla o hodnotě IMEI. Intune tyto identifikátory používá k určení vlastnictví zařízení během registrace zařízení v podnikové síti. Každé číslo IMEI nebo sériové číslo může mít podrobnosti uvedené v seznamu pro účely správy.

Tato funkce je podporovaná pro následující platformy:

| Platforma | Čísla IMEI | Sériová čísla |
|---|---|---|
| Windows | Podporováno (Windows Phone) | Nepodporováno |
| iOS/macOS | Nepodporováno | Podporováno |
| V10 za účelem spravovaného operačního systému Android pro správu zařízení | Nepodporováno | Nepodporováno |
| Ostatní systémy Android | Nepodporováno | Podporováno |

<!-- When you upload serial numbers for corporate-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as corporate-owned. -->

[Přečtěte si, jak najít sériové číslo zařízení Apple](https://support.apple.com/HT204308).<br>
[Přečtěte si, jak zjistit sériové číslo zařízení s Androidem](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers-by-using-a-csv-file"></a>Přidání podnikových identifikátorů pomocí souboru. csv
Chcete-li vytvořit seznam, vytvořte seznam hodnot oddělených čárkami (. csv) bez záhlaví. Přidejte do levého sloupce číslo IMEI nebo sériová čísla a podrobnosti v pravém sloupci. V jednom souboru. CSV se dá importovat jenom jeden typ ID, IMEI nebo sériové číslo. Podrobnosti jsou omezeny na 128 znaků a jsou pouze pro administrativní použití. V zařízení se nezobrazují podrobnosti. Aktuální limit je 5 000 řádků na soubor. csv.

**Nahrajte soubor. CSV se sériovými čísly** – vytvořte seznam hodnot oddělených čárkami (. csv) bez záhlaví a omezte seznam na 5 000 zařízení nebo 5 MB na soubor. csv.

|||
|-|-|
|&lt;ID #1 &gt;|&lt;Device #1 podrobnosti @ no__t-1|
|&lt;ID #2 &gt;|&lt;Device #2 podrobnosti @ no__t-1|

Tento soubor. csv při zobrazení v textovém editoru vypadá takto:

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> Některá zařízení s Androidem a iOS mají několik čísel IMEI. Intune přečte jenom jedno číslo IMEI na zaregistrované zařízení. Pokud importujete číslo IMEI, ale nejedná se o IMEI v inventáři pomocí Intune, zařízení se klasifikuje jako osobní zařízení místo zařízení vlastněné společností. Pokud importujete více kódů IMEI pro zařízení, jedno čísla se zobrazí jako **neznámá** pro stav registrace.<br>
>Všimněte si také, že sériová čísla jsou doporučená forma identifikace pro zařízení s iOS.
>Sériová čísla Androidu nejsou zaručená jako jedinečná nebo současná. Obraťte se na dodavatele zařízení, abyste zjistili, jestli je sériové číslo ID spolehlivého zařízení.
>Sériová čísla hlášená zařízením do Intune nemusí odpovídat zobrazeným ID v nabídkách nastavení systému Android/o zařízení. Ověřte typ sériového čísla hlášené výrobcem zařízení.
>Pokus o nahrání souboru se sériovými čísly, která obsahují tečky (.), způsobí selhání nahrávání. Sériová čísla s tečkami nejsou podporovaná.

### <a name="upload-a-csv-list-of-corporate-identifiers"></a>Nahrajte seznam podnikových identifikátorů. csv.

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), vyberte **registrace zařízení** > **identifikátory podnikových zařízení** > **Přidat** **soubor CSV pro nahrávání** > .

   ![Pracovní prostor identifikátoru podnikového zařízení s zvýrazněným tlačítkem Přidat](./media/corporate-identifiers-add/add-corp-id.png)

2. V okně **Přidat identifikátory** zadejte typ identifikátoru: **IMEI** nebo **sériové**.

3. Klikněte na ikonu složky a zadejte cestu k seznamu, který chcete importovat. Přejděte do souboru. csv a vyberte **Přidat**. 

4. Pokud soubor. csv obsahuje podnikové identifikátory, které jsou už v Intune, ale mají jiné podrobnosti, zobrazí se místní nabídka **Zkontrolovat duplicitní identifikátory** . Vyberte identifikátory, které chcete do Intune přepsat, a kliknutím na **OK** přidejte identifikátory. Pro každý identifikátor bude porovnána pouze první duplicita.

## <a name="manually-enter-corporate-identifiers"></a>Ruční zadání podnikových identifikátorů

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), vyberte **registrace zařízení** > **identifikátory podnikových zařízení** > **Přidat** > **Zadejte ručně**.

2. V okně **Přidat identifikátory** zadejte typ identifikátoru: **IMEI** nebo **sériové**.

3. Zadejte **identifikátor** a **Podrobnosti** pro každý identifikátor, který chcete přidat. Až skončíte s zadáváním identifikátorů, klikněte na **Přidat**.

5. Pokud jste zadali podnikové identifikátory, které jsou už v Intune, ale mají různé podrobnosti, zobrazí se místní nabídka **Zkontrolovat duplicitní identifikátory** . Vyberte identifikátory, které chcete do Intune přepsat, a kliknutím na **OK** přidejte identifikátory. Pro každý identifikátor bude porovnána pouze první duplicita.

Kliknutím na **aktualizovat** můžete zobrazit nové identifikátory zařízení.

Importovaná zařízení nejsou nutně zaregistrovaná. Zařízení můžou mít stav buď **zaregistrované** , nebo **Nekontaktované**. **Nekontaktováno** znamená, že zařízení nikdy nekomunikovalo se službou Intune.

## <a name="delete-corporate-identifiers"></a>Odstranění podnikových identifikátorů

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), vyberte **registrace zařízení** > **identifikátory podnikových zařízení**.
2. Vyberte identifikátory zařízení, které chcete odstranit, a zvolte **Odstranit**.
3. Potvrďte odstranění.

Při odstranění podnikového identifikátoru zaregistrovaného zařízení se nezmění vlastnictví zařízení. Pokud chcete změnit vlastnictví zařízení **, přejděte na zařízení,** vyberte zařízení, zvolte **vlastnosti**a změňte **vlastnictví zařízení**.

## <a name="imei-specifications"></a>Specifikace IMEI
Podrobné informace o identifikátorech mezinárodních mobilních zařízení najdete v tématu [3GGPP TS 23,003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

## <a name="change-device-ownership"></a>Změna vlastnictví zařízení

U jednotlivých záznamů zařízení v Intune se u vlastností zařízení zobrazuje **vlastnictví** . Jako správce můžete zařízení zadat jako **osobní** nebo **firemní**.

**Změna vlastnictví zařízení:**
1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), otevřete **zařízení a vyberte zařízení.**
2. Zvolte **Properties** (Vlastnosti).
3. Zadejte **vlastnictví zařízení** jako **osobní** nebo **firemní**.

   ![Vlastnosti zařízení zobrazující možnosti kategorie zařízení a vlastnictví zařízení](./media/corporate-identifiers-add/device-properties.png)
