---
title: Přidání aplikací pro Windows Phone 8.1 ze Storu do Microsoft Intune
titleSuffix: ''
description: Toto téma popisuje, jak přidat aplikace Windows Phone 8,1 Storu do Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4a95e575-2c63-4bfc-b9c4-f0a132eef618
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6f749371a6fe2410386ba0cc10e043699e841d2f
ms.sourcegitcommit: c8cb314256c4896e838918f015ffaefb8f00ace5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/23/2019
ms.locfileid: "71302916"
---
# <a name="add-windows-phone-81-store-apps-to-microsoft-intune"></a>Přidání aplikací pro Windows Phone 8.1 ze Storu do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Před přiřazením aplikace k zařízení nebo skupině uživatelů je nejprve potřeba danou aplikaci přidat do Microsoft Intune. 

## <a name="add-an-app-to-intune"></a>Přidání aplikace do Intune
Aplikaci pro Windows Phone 8.1. ze Storu můžete přidat do Intune z portálu Azure Portal následujícím postupem:

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V podokně úloh **Klientské aplikace** vyberte v části **Spravovat** možnost **Aplikace**.
5. V podokně **Aplikace** vyberte **Přidat**.
6. V podokně **Přidat aplikaci** vyberte jako **Typ aplikace** možnost **Windows Phone 8.1** a zvolte **Informace o aplikaci**.
7. V podokně **Informace o aplikaci** přidejte informace o aplikaci. V závislosti na zvolené aplikaci můžou být některé hodnoty v tomto podokně vyplněné automaticky:
    - **Název**: Zadejte název aplikace, který se zobrazí na portálu společnosti. Ujistěte se, že používaný název aplikace je jedinečný. Pokud je název aplikace duplicitní, zobrazí se uživatelům na Portálu společnosti pouze jeden název.
    - **Popis**: Zadejte popis aplikace. Tento popis se uživatelům zobrazí na Portálu společnosti.
    - **Vydavatel**: Zadejte název vydavatele aplikace.
    - **Adresa URL AppStore**: Zadejte adresu URL obchodu s aplikacemi pro aplikaci, kterou chcete vytvořit.
    - **Kategorie**: Volitelně můžete vybrat jednu nebo více předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Uživatelé tak při procházení Portálu společnosti najdou aplikaci snadněji.
    - **Zobrazit jako doporučenou aplikaci v portál společnosti**: Tuto možnost vyberte, pokud chcete, aby se sada aplikací zobrazovala na hlavní stránce portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL ochrany osobních údajů**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář**: Volitelně můžete zadat název vývojáře aplikace.
    - **Vlastník**: Volitelně můžete zadat jméno vlastníka této aplikace, například *personální oddělení*.
    - **Poznámky**: Volitelně můžete zadat všechny poznámky, které chcete k této aplikaci přidružit.
    - **Logo**: Volitelně nahrajte ikonu, která bude přidružená k aplikaci. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
8. Vyberte **OK**.
9. Vyberte **Přidat**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřazovat vybraným skupinám.

## <a name="next-steps"></a>Další kroky

- [Přiřazení aplikací skupinám](apps-deploy.md)
