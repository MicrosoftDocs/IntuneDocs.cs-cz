---
title: Přidání podnikových identifikátorů do Intune
titlesuffix: ''
description: Zjistěte, jak přidat podnikové identifikátory (způsob registrace, IMEI a sériová čísla) do Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd5e3220e54c33fd545e708689403b566088bdd5
ms.sourcegitcommit: 464cf677e3746eaba46836dedfb94572a75032f9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/21/2019
ms.locfileid: "58330429"
---
# <a name="identify-devices-as-corporate-owned"></a>Identifikace zařízení jako vlastněných společností

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako správce Intune můžete identifikovat zařízení jako ve vlastnictví firmy, aby se zlepšila jejich správa a identifikace. Intune můžete provádět další úlohy správy a sbírat další informace, třeba celé telefonní číslo a inventář aplikací ze zařízení ve vlastnictví firmy. Můžete také nastavit omezení zařízení a blokovat tak registraci zařízení, které ve vlastnictví firmy nejsou.

Během registrace Intune automaticky přiřadí některým zařízením stav, který označuje, že tato zařízení jsou ve vlastnictví firmy. Týká se to každého zařízení, které:

- Je registrované pomocí nějakého účtu [správce registrace zařízení](device-enrollment-manager-enroll.md) (všechny platformy)
- Je registrované přes [Program registrace zařízení](device-enrollment-program-enroll-ios.md) od Applu, [Apple School Manager](apple-school-manager-set-up-ios.md) nebo [Apple Configurator](apple-configurator-enroll-ios.md) (jen iOS)
- [Před registrací je identifikované jako ve vlastnictví firmy](#identify-corporate-owned-devices-with-imei-or-serial-number) pomocí čísla IMEI (International Mobile Equipment Identifier) (všechny platformy s čísly IMEI) nebo sériového čísla (iOS a Android)
- Je připojené k Azure Active Directory jako zařízení s Windows 10 Enterprise.
- Je na [seznamu vlastností zařízení](#change-device-ownership) označené jako firemní

Po registraci můžete [měnit nastavení vlastnictví](#change-device-ownership) na **Osobní** a **Firemní**.

## <a name="identify-corporate-owned-devices-with-imei-or-serial-number"></a>Identifikace zařízení ve vlastnictví firmy pomocí čísla IMEI nebo sériového čísla

Jako správce Intune můžete vytvořit a importovat soubor hodnot oddělených čárkami (.csv) obsahující seznam 14 číslic čísla IMEI nebo sériová čísla. Intune pomocí těchto identifikátorů během registrace určuje, že zařízení je ve vlastnictví firmy. Můžete deklarovat čísla IMEI všech podporovaných platforem. Je možné deklarovat pouze sériová čísla zařízení s iOSem, macOSem a Androidem. Každý kód IMEI nebo sériové číslo může mít v tomto seznamu uvedené podrobnosti pro účely správy.

<!-- When you upload serial numbers for corporate-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as corporate-owned. -->

[Přečtete si, jak zjistit sériové číslo zařízení Apple](https://support.apple.com/HT204308).<br>
[Přečtete si, jak zjistit sériové číslo zařízení s Androidem](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers-by-using-a-csv-file"></a>Přidání podnikových identifikátorů pomocí souboru .csv
Pokud chcete vytvořit seznam, vytvořte seznam hodnot oddělených čárkami se dvěma sloupci (.csv) bez záhlaví. V levém sloupci a podrobnosti v pravém sloupci přidáte 14 číslic čísla IMEI nebo sériová čísla. V rámci jednoho souboru .csv můžete importovat pouze jeden typ identifikačního čísla: buď IMEI, nebo sériové číslo. Podrobnosti jsou omezené na 128 znaků a používají se jenom pro účely správy. Na zařízení se podrobnosti nezobrazují. Současný limit jednoho souboru CSV je 5 000 řádků.

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
> Některá zařízení s Androidem a iOS mají více kódů IMEI. Intune dokáže přečíst jen jeden kód IMEI na každé zaregistrované zařízení. Pokud naimportujete čísla IMEI, ale není kódem IMEI v inventáři služba Intune, označí se zařízení jako osobní zařízení místo zařízení vlastněných společností. Pokud importujete více kódů IMEI pro jedno zařízení, zobrazí se u kódů, které nejsou v inventáři, stav registrace **Neznámý**.<br>
>Všimněte si také: Doporučený způsob identifikace pro zařízení s Iosem jsou sériová čísla.
>Sériová čísla androidu nemusí být jedinečná nebo existovat. Pokud chcete zjistit, jestli je sériové číslo spolehlivým identifikátorem zařízení, obraťte se na dodavatele zařízení.
>Sériová čísla, která službě Intune oznámí zařízení, se nemusí shodovat se zobrazenými identifikátory v nabídkách zařízení Nastavení/ O zařízení. Ověřte si typ sériového čísla oznámeného výrobcem zařízení.
>Pokus o nahrání souborů se sériovými čísly, které obsahují tečky (.), způsobí selhání nahrávání. Sériová čísla s tečkami nejsou podporovaná.

### <a name="upload-a-csv-list-of-corporate-identifiers"></a>Nahrání seznamu podnikových identifikátorů ve formátu .csv

1. V [Intune na portálu Azure Portal](https://portal.azure.com) zvolte **Registrace zařízení** > **Identifikátory podnikových zařízení** > **Přidat** > **Nahrát soubor CSV**.

   ![Pracovní prostor s identifikátory podnikových zařízení a zvýrazněným tlačítkem Přidat](./media/add-corp-id.png)

2. V **přidat identifikátory** okně zadejte typ identifikátoru: **IMEI** nebo **sériového portu**.

3. Klikněte na ikonu složky a určete cestu k seznamu, který chcete importovat. Přejděte do souboru .csv a zvolte **Přidat**. 

4. Pokud soubor .csv obsahuje podnikové identifikátory, které už v Intune jsou, ale mají jiné podrobnosti, zobrazí se automaticky otevírané okno **Zkontrolovat duplicitní identifikátory**. Vyberte identifikátory, které chcete v Intune přepsat, a výběrem **OK** tyto identifikátory přidejte. U každého identifikátoru se porovná jenom první duplicita.

## <a name="manually-enter-corporate-identifiers"></a>Ruční zadání podnikových identifikátorů

1. V [Intune na portálu Azure Portal](https://portal.azure.com) zvolte **Registrace zařízení** > **Identifikátory podnikových zařízení** > **Přidat** > **Zadat ručně**.

2. V **přidat identifikátory** okně zadejte typ identifikátoru: **IMEI** nebo **sériového portu**.

3. Pro každý identifikátor, který chcete přidat, zadejte **Identifikátor** a **Podrobnosti**. Až zadávání identifikátorů dokončíte, zvolte **Přidat**.

5. Pokud jste zadali podnikové identifikátory, které už v Intune jsou, ale mají jiné podrobnosti, zobrazí se automaticky otevírané okno **Zkontrolovat duplicitní identifikátory**. Vyberte identifikátory, které chcete v Intune přepsat, a výběrem **OK** tyto identifikátory přidejte. U každého identifikátoru se porovná jenom první duplicita.

Pokud se chcete podívat na identifikátory nového zařízení, můžete kliknout na **Aktualizovat**.

Importovaná zařízení nemusí být nutně zaregistrovaná. Zařízení můžou mít stav **Zaregistrované** nebo **Nekontaktované**. **Nekontaktované** znamená, že toto zařízení nikdy se službou Intune nekomunikovalo.

## <a name="delete-corporate-identifiers"></a>Odstranění podnikových identifikátorů

1. V [Intune na portálu Azure Portal](https://portal.azure.com) zvolte **Registrace zařízení** > **Identifikátory podnikových zařízení**.
2. Vyberte identifikátory zařízení, které chcete odstranit, a zvolte **Odstranit**.
3. Potvrďte odstranění.

Při odstranění podnikového identifikátoru zaregistrovaného zařízení se nezmění vlastnictví zařízení. Pokud chcete změnit vlastnictví zařízení, přejděte na **Zařízení**, vyberte zařízení, zvolte **Vlastnosti** a změňte **Vlastnictví zařízení**.

## <a name="imei-specifications"></a>Specifikace IMEI
Podrobné specifikace o číslech IMEI najdete na stránce [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

## <a name="change-device-ownership"></a>Změna vlastnictví zařízení

U každého záznamu zařízení v Intune se ve vlastnostech zařízení zobrazuje **Vlastnictví**. Jako správce můžete zařízení označit jako **Osobní** nebo **Firemní**.

**Vlastnictví zařízení změníte takto:**
1. V [Intune na portálu Azure Portal](https://portal.azure.com) přejděte na **Zařízení** a zvolte požadované zařízení.
2. Zvolte **vlastnosti**.
3. Určete **Vlastnictví zařízení** jako **Osobní** nebo **Firemní**.

   ![Vlastnosti zařízení s možnostmi Kategorie zařízení a Vlastnictví zařízení](./media/device-properties.png)
