---
title: "Instalace Office 365 na zařízení s macOS pomocí Microsoft Intune"
titlesuffix: 
description: "Zjistěte, jak můžete využít Microsoft Intune k instalaci aplikací Office 365 na zařízení s macOS."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8de14184c4d23adc79d5b519fdcf272f0d7f6804
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Přiřazení Office 365 zařízením s macOS v Microsoft Intune

Typ **Aplikace pro Store** usnadňuje přiřazení aplikací Office 365 zařízením s macOS. Tento typ aplikace umožňuje instalovat Word, Excel, PowerPoint, Outlook a OneNote. Tyto aplikace jsou také dodávané prostřednictvím funkce Microsoft AutoUpdate (MAU). Je to kvůli jejich zabezpečení a aktuálnosti. Požadované aplikace se v seznamu aplikací v konzole Intune zobrazí jako jedna aplikace.


## <a name="before-you-start"></a>Než začnete

Než začnete přidávat Office 365 do zařízení s macOS, musíte znát tyto podrobnosti:

- Zařízení, na která tyto aplikace budete nasazovat, musí mít macOS 10.10 nebo novější.
- Intune umožňuje přidat jenom aplikace Office, které jsou součástí sady Office 2016 pro Mac.
- Pokud by při instalaci sady aplikací službou Intune byly některé aplikace Office otevřeny, mohou koncoví uživatelé přijít o data v neuložených souborech.

## <a name="create-and-configure-the-app-suite"></a>Vytvoření a konfigurace sady aplikací

Přidejte Office 365. Použijte k tomu okno **Aplikace**.
1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Monitorování a správa** > **Intune**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
4. V úloze **Mobilní aplikace** zvolte v části **Spravovat** možnost **Aplikace**. 
5. Zvolte **Přidat**. Tím zobrazíte okno **Přidat aplikaci**.
6. V seznamu **Typ aplikace** vyberte **macOS** ve skupině **Sada Office 365**.
7. Vyberte **Informace o sadě aplikací** k poskytnutí informací o sadě aplikací. Tyto informace vám pomůžou sadu aplikací v Intune identifikovat a uživatelům ji pomůžou najít v aplikaci Portál společnosti.
8.  Zadejte následující informace:
    - **Název sady** – zadejte název sady aplikací, který se zobrazí na portálu společnosti. Názvy všech používaných aplikací musí být jedinečné. Pokud stejný název sady aplikací existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis sady** – zadejte popis sady aplikací.
    - **Vydavatel** – jako vydavatel se zobrazí Microsoft.
    - **Kategorie** – vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste si vytvořili sami. Díky tomuto nastavení uživatelé dokážou sadu aplikací při procházení portálu společnosti jednodušeji najít.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – sada aplikací se uživatelům, kteří hledají aplikace, zobrazí na výrazném místě na hlavní stránce Portálu společnosti.
    - **Adresa URL informací** (volitelné) – zadejte adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů** (volitelné) – zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář** – jako vývojář se zobrazí Microsoft.
    - **Vlastník** – jako vlastník se zobrazí Microsoft.
    - **Poznámky** (volitelné) – zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Logo** – logo Office 365 se zobrazí u aplikace, když uživatelé procházejí Portál společnosti.
9.  Klikněte v okně **Informace o aplikaci** na **OK**.
10. V okně **Přidat aplikaci** klikněte na **Přidat**.
    Sada se zobrazí v seznamu aplikací jako jedna položka.

## <a name="configure-app-assignments"></a>Konfigurace přiřazení aplikací

V tomto kroku nakonfigurujte, jakým skupinám sadu aplikací přiřadíte. 

1. Vybráním sady aplikací **Office 365** v seznamu aplikací zobrazte okno přehledu **Office 365**.
2. V okně **Office 365** klikněte na **Přiřazení**.
3. Kliknutím na **Přidat skupinu** přidejte skupinu k použití sady aplikací. Zobrazí se okno **Přidat skupinu**.
3. Nastavte **Typ přiřazení** na **Povinné**.
4. Přiřaďte sadu vybraným skupinám. Další informace najdete v článku [Jak přiřadit aplikace do skupin pomocí Microsoft Intune](apps-deploy.md).

    >[!Note]
    > V případě skupin, kde vyžadujete sadu aplikací Office 365, ji pomocí Microsoft Intune nemůžete odinstalovat.

5. V okně **Přiřadit** vyberte **OK**.
6. V okně **Přidat skupinu** vyberte **OK**.
7. Přiřazení potvrďte volbou **Uložit**.

## <a name="next-steps"></a>Další kroky

- Další informace o přidání aplikací Office 365 do zařízení s Windows 10 najdete v článku [Přiřazení aplikací Office 365 ProPlus 2016 k zařízením s Windows 10 pomocí Microsoft Intune](apps-add-office365.md).
- Informace o zahrnutí a vyloučení přiřazení aplikací ve skupinách uživatelů najdete v článku [Zahrnutí a vyloučení přiřazení aplikací](apps-inc-exl-assignments.md).
