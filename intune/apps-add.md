---
title: "Přidání aplikací do Microsoft Intune | Dokumentace Microsoftu"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Tyto postupy vám pomůžou připravit vaše aplikace v Intune pro přiřazení uživatelům a zařízením. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 36cafd2b943ab1dd5045a8ed1fe1fcf1b28af385
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-add-an-app-to-microsoft-intune"></a>Přidání aplikací do Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Abyste mohli aplikace spravovat a přiřazovat uživatelům, je potřeba je přidat do Intune. Intune podporuje širokou škálu různých typů aplikací a možnosti se můžou pro jednotlivé typy lišit.

Intune umožňuje přidat a přiřadit tyto typy aplikací:

![Typy aplikací podporované v Intune](./media/app-types.png)

Podporují se následující platformy.

- Aplikace pro Android Store
- Obchodní aplikace (LOB) pro Android
- Aplikace pro iOS Store
- Obchodní aplikace (LOB) pro iOS
- Webové aplikace
- Aplikace pro Windows Phone 8.1 Store
- Obchodní aplikace pro Windows Phone (soubory .xap)
- Aplikace pro Windows Store
- Obchodní aplikace pro Windows (pouze soubory .msi)

>[!TIP]
> Obchodní aplikace (neboli LOB) je taková, která se neinstaluje z obchodu s aplikacemi, ale z instalačního souboru aplikace. Pokud třeba chcete nainstalovat obchodní aplikaci pro iOS, přidejte soubor archivu aplikace (s příponou .ipa). Obvykle jde o aplikace, které jste vytvořili interně.

## <a name="before-you-start"></a>Než začnete

Než začnete aplikace přidávat a přiřazovat, zvažte následující body.

- Pokud chcete přidat a přiřadit aplikaci z obchodu, musí mít koncoví uživatelé u tohoto obchodu zřízený účet, aby si aplikaci mohli nainstalovat.
- Některé aplikace nebo položky, které přiřadíte, můžou záviset na integrovaných aplikacích pro iOS. Pokud třeba přiřadíte knihu z obchodu pro iOS, musí být v zařízení aplikace iBooks. Pokud jste integrovanou aplikaci iBooks odebrali, nemůžete ji pomocí Intune obnovit.

## <a name="cloud-storage-space"></a>prostor v cloudovém úložišti
Všechny aplikace, které vytváříte pomocí instalace typu Instalační program softwaru (například obchodní aplikace), se zabalí a nahrají do cloudového úložiště Intune. Zkušební předplatné Intune zahrnuje 2 gigabajty (GB) cloudového úložiště, které se používá k ukládání spravovaných aplikací a aktualizací. Úplné předplatné zahrnuje 20 GB úložného prostoru.

Další úložiště pro Intune můžete zakoupit stejným způsobem jako u původního nákupu.  Pokud jste platili fakturou nebo platební kartou, navštivte [portál pro správu předplatných](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Jinak kontaktujte svého partnera nebo prodejního zástupce.

Požadavky na cloudové úložiště jsou následující:

-   Všechny instalační soubory musí být umístěné stejné složce.
-   Maximální velikost kteréhokoli nahraného souboru je 2 GB.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Jak vytvořit a upravit kategorie pro aplikace

Když aplikace seřadíte do kategorií, koncoví uživatelé je jednodušeji najdou na portálu společnosti. K aplikaci můžete přiřadit jednu kategorii i více, například **Aplikace pro vývojáře** nebo **Aplikace pro komunikaci**.
Když přidáte aplikaci do Intune, budete mít možnost vybrat požadovanou kategorii. Informace k přidání aplikací a přiřazení kategorií získáte v tématech pro jednotlivé platformy. Pokud chcete vytvořit a upravit vlastní kategorie, postupujte podle následujících pokynů:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
4. V úloze **Mobilní aplikace** zvolte **Spravovat** > **Kategorie aplikací**.
5. V okně **Kategorie aplikací** se zobrazí seznam aktuálních kategorií. Vyberte jednu z následujících akcí:
    - **Vytvořit kategorii**: V okně **Vytvořit kategorii** zadejte název nové kategorie. Názvy je možné zadat jenom v jednom jazyce a služba Intune je nepřekládá. Až skončíte, klikněte na **Vytvořit**.
    - **Upravit kategorii**: Pro jakoukoliv kategorii v seznamu, zvolte tlačítko se třemi tečkami (**...**). V okně **Vlastnosti** můžete zadat nový název pro kategorii nebo tady můžete kategorii odstranit.


## <a name="apps-added-automatically-by-intune"></a>Aplikace přidaní automaticky službou Intune

Následující aplikace, které jsou publikované Microsoftem, jsou v Intune integrované a připravené na přiřazení:

|||
|-|-|
|Název|Platforma|Typ aplikace|
|Azure Information Protection|Android|Spravovaná aplikace obchodu pro Android|
|Dynamics CRM pro telefony|Android|Spravovaná aplikace obchodu pro Android|
|Dynamics CRM pro tablety|Android|Spravovaná aplikace obchodu pro Android|
|Excel|iOS|Spravovaná aplikace obchodu pro iOS|
|Excel|Android|Spravovaná aplikace obchodu pro Android|
|spravovaný prohlížeč|Android|Spravovaná aplikace obchodu pro Android|
|spravovaný prohlížeč|iOS|Spravovaná aplikace obchodu pro iOS|
|Microsoft Dynamics CRM na telefonech|iOS|Spravovaná aplikace obchodu pro iOS|
|Microsoft Dynamics CRM na tabletech|iOS|Spravovaná aplikace obchodu pro iOS|
|Microsoft Power BI|iOS|Spravovaná aplikace obchodu pro iOS|
|Microsoft Power BI|Android|Spravovaná aplikace obchodu pro Android|
|Microsoft SharePoint|iOS|Spravovaná aplikace obchodu pro iOS|
|Microsoft SharePoint|Android|Spravovaná aplikace obchodu pro Android|
|Microsoft Teams|Android|Spravovaná aplikace obchodu pro Android|
|Microsoft Teams|iOS|Spravovaná aplikace obchodu pro iOS|
|OneDrive|iOS|Spravovaná aplikace obchodu pro iOS|
|OneDrive|Android|Spravovaná aplikace obchodu pro Android|
|OneNote|iOS|Spravovaná aplikace obchodu pro iOS|
|Outlook|Android|Spravovaná aplikace obchodu pro Android|
|Outlook|iOS|Spravovaná aplikace obchodu pro iOS|
|Outlook Groups|Android|Spravovaná aplikace obchodu pro Android|
|Outlook Groups|iOS|Spravovaná aplikace obchodu pro iOS|
|PowerPoint|iOS|Spravovaná aplikace obchodu pro iOS|

## <a name="next-steps"></a>Další kroky

Informace o tom, jak do Intune přidat aplikace pro jednotlivé platformy, najdete v příslušných tématech:

- [Aplikace pro Android Store](store-apps-android.md)
- [Obchodní aplikace pro Android](lob-apps-android.md)
- [Aplikace pro iOS Store](store-apps-ios.md)
- [Obchodní aplikace pro iOS](lob-apps-ios.md)
- [Webové aplikace (pro všechny platformy)](web-app.md)
- [Aplikace pro Windows Phone 8.1 Store](store-apps-windows-phone-8-1.md)
- [Obchodní aplikace pro Windows Phone](lob-apps-windows-phone.md)
- [Aplikace pro Windows Store](store-apps-windows.md)
- [Obchodní aplikace pro Windows](lob-apps-windows.md)

