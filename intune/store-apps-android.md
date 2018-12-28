---
title: Přidání aplikací z obchodu pro Android do Microsoft Intune
titleSuffix: ''
description: Zjistěte, jak přidat aplikace pro Android store do Microsoft Intune z obchodu Google Play.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2391f6ec7de5a9d1b4d544f1ca07fd9f4e58ace8
ms.sourcegitcommit: 4e69a8664c289263490daa4c02bc6b81c33196e5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53642401"
---
# <a name="add-android-store-apps-to-microsoft-intune"></a>Přidání aplikací z obchodu pro Android do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Před přiřazením aplikace k zařízení nebo skupině uživatelů je nejprve potřeba danou aplikaci přidat do Microsoft Intune. 

## <a name="add-an-app"></a>Přidání aplikace

Aplikaci z obchodu pro Android můžete přidat do Intune z portálu Azure Portal následujícím postupem:

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**.  
    Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V podokně úloh **Klientské aplikace** vyberte v části **Spravovat** možnost **Aplikace**.
5. Vyberte **Přidat**.
6. V podokně **Přidat aplikaci** vyberte v dostupných typech **aplikací pro Store** možnost **Android**.
7. Pokud chcete nakonfigurovat informace o aplikaci, vyberte **Konfigurovat** a zadejte následující informace. U aplikací pro Android přejděte na [obchod Google Play](https://play.google.com/store) a vyhledejte aplikaci, kterou chcete nasadit. Vyberte tuto aplikaci a poznačte si její podrobnosti. V závislosti na zvolené aplikaci můžou být některé hodnoty vyplněné automaticky.
    - **Název**: Zadejte název aplikace, jak je zobrazený na portálu společnosti. Ujistěte se, že používaný název aplikace je jedinečný. Pokud je název aplikace duplicitní, zobrazí se uživatelům na Portálu společnosti pouze jeden název.
    - **Popis**: Zadejte popis aplikace. Tento popis se uživatelům zobrazí na Portálu společnosti.
    - **Vydavatel**: Zadejte název vydavatele aplikace.
    - **Adresa URL obchodu**: Zadejte adresu URL obchodu aplikace, kterou chcete vytvořit.
    - **Minimální verzi operačního systému**: V seznamu vyberte nejstarší verzi operačního systému, na které můžete aplikaci nainstalovat. Pokud aplikaci přiřadíte k zařízení se starším operačním systémem, nenainstaluje se.
    - **Kategorie**: Volitelně vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Uživatelé tak při procházení Portálu společnosti najdou aplikaci snadněji.
    - **Zobrazit tuto aplikaci jako doporučenou aplikaci portálu společnosti**: Vyberte tuto možnost, chcete-li zobrazit sadu aplikací výrazném místě na hlavní stránce portálu společnosti když uživatelé vyhledávají aplikace.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Soukromá adresa URL**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Pro vývojáře**: Volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník**: Volitelně zadejte jméno vlastníka aplikace, například *Personální oddělení*.
    - **Poznámky k**: Volitelně zadejte jakékoli poznámky, které chcete přidružit k této aplikaci.
    - **Logo**: Volitelně nahrajte ikonu, která bude spojená s aplikací. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
1. Vyberte **OK**.
2. Vyberte **Přidat**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřazovat vybraným skupinám. 

## <a name="next-steps"></a>Další postup

- [Přiřazení aplikací skupinám](apps-deploy.md)
