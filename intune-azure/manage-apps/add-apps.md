---
title: "Jak přidat aplikace do Microsoft Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Tyto postupy vám pomůžou připravit vaše aplikace v Intune pro přiřazení uživatelům a zařízením. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 969ce8deae9142944f3481172277dc252baa5779
ms.openlocfilehash: a7838f57b2eb8bd36a875f7b5b001b12eafcbf8d

---

# <a name="how-to-add-an-app"></a>Přidání aplikace 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Abyste mohli aplikace spravovat a přiřazovat uživatelům, je potřeba je přidat do Intune. Intune podporuje širokou škálu různých typů aplikací a možnosti se můžou pro jednotlivé typy lišit.

Intune podporuje přidávání a přiřazování těchto typů aplikací:

![Typy aplikací podporované v Intune](./media/app-types.png)

Podporují se následující platformy. Pokud chcete získat další informace, jak přidat jednotlivé typy aplikací, klikněte na jedno z témat.

- [Android – obchodní aplikace](/intune-azure/manage-apps/android-lob-app)
- [Aplikace pro Android Store](/intune-azure/manage-apps/android-store-app)
- [iOS – obchodní aplikace](/intune-azure/manage-apps/ios-lob-app)
- [Aplikace pro iOS Store](/intune-azure/manage-apps/ios-store-app)
- [Webové aplikace (pro všechny platformy)](/intune-azure/manage-apps/web-app)
- [Aplikace pro Windows Phone 8.1 Store](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Aplikace pro Windows Store](/intune-azure/manage-apps/windows-store-app)

> [!NOTE]
> Pokud chcete přidat a nasadit aplikaci z obchodu, musí mít koncoví uživatelé u tohoto obchodu zřízený účet, aby si aplikaci mohli nainstalovat.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Jak vytvořit a upravit kategorie pro aplikace 

Když aplikace seřadíte do kategorií, koncoví uživatelé je jednodušeji najdou na portálu společnosti. K aplikaci můžete přiřadit jednu kategorii i více, například **Aplikace pro vývojáře** nebo **Aplikace pro komunikaci**. Když přidáte aplikaci do Intune, budete mít možnost vybrat požadovanou kategorii. Informace k přidání aplikací a přiřazení kategorií získáte v tématech pro jednotlivé platformy. Pokud chcete vytvořit a upravit vlastní kategorie, postupujte podle následujících pokynů: 

1. Přihlaste se k portálu Azure Portal. 
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**. 
3. V okně **Intune** zvolte **Spravovat aplikace**. 
4. V úloze **Mobilní aplikace** zvolte **Spravovat** > **Kategorie aplikací**. 
5. V okně **Kategorie aplikací** se zobrazí seznam aktuálních kategorií. Vyberte jednu z následujících akcí: 
    - **Vytvořit kategorii**: V okně **Vytvořit kategorii** zadejte název nové kategorie. Názvy je možné zadat jenom v jednom jazyce a služba Intune je nepřekládá. Až skončíte, klikněte na **Vytvořit**.
    - **Upravit kategorii**: Pro jakoukoliv kategorii v seznamu, zvolte tlačítko se třemi tečkami (**...**). V okně **Vlastnosti** můžete zadat nový název pro kategorii nebo tady můžete kategorii odstranit. --->






<!--HONumber=Feb17_HO1-->


