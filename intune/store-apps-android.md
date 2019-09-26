---
title: Přidání aplikací z obchodu pro Android do Microsoft Intune
titleSuffix: ''
description: Přečtěte si, jak přidat aplikace z obchodu pro Android z Google Play Storu do Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/27/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 93ea735121432c99c93ffe35c96c344160de3e22
ms.sourcegitcommit: 6c74ff568267d85fd1d44fda75e3e24ead87cb2b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/28/2019
ms.locfileid: "71303146"
---
# <a name="add-android-store-apps-to-microsoft-intune"></a>Přidání aplikací z obchodu pro Android do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Před přiřazením aplikace k zařízení nebo skupině uživatelů je nejprve potřeba danou aplikaci přidat do Microsoft Intune. 

## <a name="add-an-app"></a>Přidání aplikace

Aplikaci z obchodu pro Android můžete přidat do Intune z portálu Azure Portal následujícím postupem:

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V podokně úloh **Klientské aplikace** vyberte v části **Spravovat** možnost **Aplikace**.
5. Vyberte **Přidat**.
6. V podokně **Přidat aplikaci** vyberte v dostupných typech **aplikací pro Store** možnost **Android**.
7. Pokud chcete nakonfigurovat informace o aplikaci, vyberte **Konfigurovat** a zadejte následující informace. U aplikací pro Android přejděte na [obchod Google Play](https://play.google.com/store) a vyhledejte aplikaci, kterou chcete nasadit. Vyberte tuto aplikaci a poznačte si její podrobnosti. V závislosti na zvolené aplikaci můžou být některé hodnoty vyplněné automaticky.
    - **Název**: Zadejte název aplikace, který se zobrazí na portálu společnosti. Ujistěte se, že používaný název aplikace je jedinečný. Pokud je název aplikace duplicitní, zobrazí se uživatelům na Portálu společnosti pouze jeden název.
    - **Popis**: Zadejte popis aplikace. Tento popis se uživatelům zobrazí na Portálu společnosti.
    - **Vydavatel**: Zadejte název vydavatele aplikace.
    - **Adresa URL AppStore**: Zadejte adresu URL obchodu s aplikacemi pro aplikaci, kterou chcete vytvořit.
    - **Minimální operační systém**: V seznamu vyberte nejstarší verzi operačního systému, na kterou se dá aplikace nainstalovat. Pokud aplikaci přiřadíte k zařízení se starším operačním systémem, nenainstaluje se.
    - **Kategorie**: Volitelně můžete vybrat jednu nebo více předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Uživatelé tak při procházení Portálu společnosti najdou aplikaci snadněji.
    - **Zobrazit jako doporučenou aplikaci v portál společnosti**: Tuto možnost vyberte, pokud chcete, aby se sada aplikací zobrazovala na hlavní stránce portálu společnosti, když uživatelé vyhledávají aplikace. Platí pro aplikace nasazené s dostupným záměrem.
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
