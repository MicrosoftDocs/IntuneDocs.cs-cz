---
title: "Přidání aplikací pro Windows Store do Microsoft Intune"
titleSuffix: 
description: "Zjistěte, jak do Microsoft Intune přidat aplikace z Windows Storu."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2e2280ad72bbd353d80af316cde436e8ffc79d1f
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-windows-store-apps-to-microsoft-intune"></a>Přidání aplikací pro Windows Store do Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Než budete moct přiřadit, monitorovat, konfigurovat nebo chránit aplikace, musíte je přidat do Intune. Následující kroky umožňují přidat aplikaci z Windows Storu do Microsoft Intune.

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Na stránce **Intune** zvolte **Mobilní aplikace**.
4. V úloze **Mobilní aplikace** zvolte **Spravovat** > **Aplikace**.
5. Nad seznamem aplikací zvolte **Přidat**.
6. V podokně **Přidat aplikaci** vyberte jako **Typ aplikace** možnost **Windows** a zvolte **Informace o aplikaci**.
7. V podokně **Informace o aplikaci** nakonfigurujte následující údaje. Až skončíte, klikněte na **OK**. V závislosti na zvolené aplikaci můžou být některé hodnoty v tomto podokně vyplněné automaticky:
    - **Název** – zadejte název aplikace, který se zobrazí na portálu společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis** – zadejte popis aplikace, který se zobrazí uživatelům na portálu společnosti.
    - **Vydavatel** – zadejte název vydavatele aplikace.
    - **Adresa URL v obchodu s aplikacemi** – zadejte adresu URL v obchodu s aplikacemi pro aplikaci, kterou chcete vytvořit.
    - **Kategorie (nepovinné)** – vyberte jednu nebo více kategorií integrovaných aplikací, nebo vámi vytvořenou kategorii. Uživatelé pak při procházení portálu společnosti aplikaci snadněji najdou.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací** – volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů** – volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář** – volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník** – volitelně zadejte vlastníka aplikace, například **Personální oddělení**.
    - **Poznámky** – zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Logo** – nahrajte ikonu, která se přidruží k aplikaci. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
8. Až skončíte, zvolte v podokně **Přidat aplikaci** možnost **Přidat**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřadit ke zvoleným skupinám. 

## <a name="next-steps"></a>Další kroky

- [Postup přiřazení aplikací do skupin](apps-deploy.md)