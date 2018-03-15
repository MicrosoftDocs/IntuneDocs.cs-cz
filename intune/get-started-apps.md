---
title: "Začínáme s aplikacemi v Microsoft Intune"
titlesuffix: 
description: "Najděte a přidejte aplikace do zařízení, aby mohli vaši pracovníci plnit úkoly."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0185eebbe436da73e1920d7cd834f0897a143894
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Začínáme s přidáváním aplikací v Microsoft Intune

Než budete moct přiřadit, monitorovat, konfigurovat nebo chránit aplikace, musíte je přidat do Intune. Intune podporuje několik různých typů aplikací. Dostupné možnosti se pro jednotlivé typy aplikací liší.

Intune umožňuje přidat a přiřadit k firemním zařízením tyto typy aplikací:
- **Aplikace ze Storu:** U aplikací dostupných v App Storu potřebujete použít další správu mobilních aplikací.
- **Interně napsané aplikace (obchodní):** Nahrajete soubor, který se stáhne do zařízení uživatelů.
- **Integrované aplikace:** K zařízením s iOSem a Androidem přiřadíte kurátorované spravované aplikace, jako jsou třeba aplikace Office 365. 
- **Aplikace na webu:** Intune vytvoří zástupce webové aplikace na domovské obrazovce zařízení.

## <a name="how-do-i-assign-a-public-store-app"></a>Jak přiřadím aplikaci z veřejného obchodu?

Následující příklad vás provede jednotlivými kroky přidání aplikace pro iOS v Microsoft Intune.

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
4. V úloze **Mobilní aplikace** zvolte v oddílu **Spravovat** možnost **Aplikace**.
5. Na pravé straně podokna **Aplikace** zvolte **Přidat**.
6. V seznamu **Typ aplikace** vyberte z typů **Aplikace pro Store** možnost **iOS**.
6. Zvolte **Hledat v App Storu**.
7. V okně **Hledat v App Storu** nejdříve vyberte národní prostředí App Storu.
8. Do vyhledávacího pole zadejte název (nebo část názvu). Intune prohledá Store a vrátí seznam relevantních výsledků.
9. V seznamu zvolte požadovanou aplikaci a pak klikněte na **Vybrat**.
10. Vyberte **Informace o aplikaci** a nakonfigurujte informace o aplikaci.
11. (Volitelné) Přidejte podrobnosti, které vám pomůžou aplikaci organizovat, jako je **Vlastník**, **Poznámky**, **Vývojář** a **Adresa URL informací o ochraně osobních údajů** (odkazující na zásady ochrany osobních údajů používané vaší společností).
12. Vyberte **Ano** pro možnost **Zobrazit na Portálu společnosti jako vybranou aplikaci**. 
13. Po přidání všech potřebných informací o aplikaci klikněte na **OK**.
14. V okně **Přidat aplikaci** klikněte na **Přidat**. Tím se dostanete na **Přehled** aplikace. 

## <a name="next-steps"></a>Další kroky

Teď, když jste aplikaci přidali do Intune, můžete přiřadit skupiny zaměstnanců, kteří budou moct tuto aplikaci zahrnout do svého zařízení.

- [Postup přiřazení aplikací do skupin](apps-deploy.md)
- 
## <a name="learn-more"></a>Další informace

* [Co je správa aplikací pomocí Intune?](app-management.md)
* [Přehled životního cyklu aplikace](app-lifecycle.md)
* [Co jsou zásady ochrany aplikací?](app-protection-policy.md)
