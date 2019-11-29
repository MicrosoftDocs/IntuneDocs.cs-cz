---
title: Přidání aplikací z Microsoft Storu do Microsoft Intune
titleSuffix: ''
description: Zjistěte, jak do Microsoft Intune přidat aplikace z Microsoft Storu (Windows Storu).
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3c13d7960c0bb5c73908a0a574ab7d6c169d6460
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563425"
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Přidání aplikací z Microsoft Storu do Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Než budete moct přiřadit, monitorovat, konfigurovat nebo chránit aplikace, musíte je přidat do Intune. 

## <a name="add-an-app-to-intune"></a>Přidání aplikace do Intune
Aplikaci z Microsoft Storu můžete do Intune přidat následujícím postupem:

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **aplikace** > **všechny aplikace** > **Přidat**.
3. V podokně **Přidat aplikaci** vyberte jako **Typ aplikace** možnost **Windows** a potom vyberte **Informace o aplikaci**.
4. V podokně **Informace o aplikaci** přidejte informace o aplikaci. V závislosti na zvolené aplikaci můžou být některé hodnoty v tomto podokně vyplněné automaticky:
    - **Název**: Zadejte název aplikace, který se zobrazí na Portálu společnosti. Ujistěte se, že používaný název aplikace je jedinečný. Pokud je název aplikace duplicitní, zobrazí se uživatelům na Portálu společnosti pouze jeden název.
    - **Popis**: Zadejte popis aplikace. Tento popis se uživatelům zobrazí na Portálu společnosti.
    - **Vydavatel**: Zadejte název vydavatele aplikace.
    - **Adresa URL v obchodu s aplikacemi**: Zadejte adresu URL v obchodu s aplikacemi pro aplikaci, kterou chcete vytvořit. Adresu URL najdete tak, že na [Microsoft Store](https://store.microsoft.com) vyhledáte požadovanou aplikaci. Použijte adresu URL z panelu Adresa v prohlížeči.
    - **Kategorie**: Volitelně můžete vybrat jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Uživatelé tak při procházení Portálu společnosti najdou aplikaci snadněji.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci:** Vybráním této možnosti se sada aplikací zobrazí uživatelům, kteří hledají aplikace, na výrazném místě na hlavní stránce Portálu společnosti.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů**: Volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář**: Volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník**: Volitelně zadejte vlastníka aplikace, například *Personální oddělení*.
    - **Poznámky**: Volitelně zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Logo**: Volitelně nahrajte ikonu, která se přidruží k aplikaci. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
5. Vyberte **OK**.
6. Vyberte **Přidat**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřazovat vybraným skupinám. Aplikace z Microsoft Storu můžete přiřadit jenom skupinám s typem přiřazení **K dispozici zaregistrovaným zařízením** (uživatelé si aplikaci instalují z aplikace Portál společnosti nebo z webu Portál společnosti).

## <a name="next-steps"></a>Další kroky
- [Přiřazení aplikací skupinám](apps-deploy.md)
