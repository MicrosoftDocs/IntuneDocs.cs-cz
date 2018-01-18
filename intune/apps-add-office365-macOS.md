---
title: "Instalace Office 365 na zařízení s macOS pomocí Intune"
titlesuffix: Azure portal
description: "Zjistěte, jak můžete s Intune zjednodušit instalaci aplikací Office 365 na zařízení s macOS."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e0ad0b99a2c8a602b5e542530a1d437065461b2
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/12/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Přiřazení Office 365 zařízením s macOS v Microsoft Intune

Tento typ aplikace usnadňuje přiřazení aplikací Office 365 zařízením s macOS. Tento nový typ aplikace umožňuje instalovat Word, Excel, PowerPoint, Outlook a OneNote. Tyto aplikace jsou také dodávané prostřednictvím funkce Microsoft AutoUpdate (MAU). Je to kvůli jejich zabezpečení a aktuálnosti. Požadované aplikace se v seznamu aplikací v konzole Intune zobrazí jako jedna aplikace.


## <a name="before-you-start"></a>Než začnete

- Zařízení, na která tyto aplikace budete nasazovat, musí mít macOS 10.10 nebo novější.
- Intune umožňuje přidat jenom aplikace Office, které jsou součástí sady Office 2016 pro Mac.
- Pokud by při instalaci sady aplikací službou Intune byly některé aplikace Office otevřeny, mohou koncoví uživatelé přijít o data v neuložených souborech.


## <a name="get-started"></a>Začínáme
Přidejte Office 365. Použijte k tomu okno **Aplikace**.
1.  Přihlaste se k portálu Azure Portal.
2.  Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3.  V okně **Intune** zvolte **Mobilní aplikace**.
4.  V úloze **Mobilní aplikace** zvolte ve skupině **Spravovat** možnost **Aplikace**. Zvolte **Přidat**.
5.  V okně **Přidat aplikaci** zvolte **Office 365** > **macOS**.
6.  Vyberte **Přidat**.

## <a name="configure-the-app-suite"></a>Konfigurace sady aplikací

Zadejte informace o sadě aplikací. Tyto informace vám ji pomůžou identifikovat v Intune a uživatelům ji pomůžou najít v aplikaci Portál společnosti.

1.  V okně **Přidat aplikaci** zvolte možnost pro **informace o sadě aplikací**.
2.  Zadejte následující informace:
    - **Název sady** – zadejte název sady aplikací, který se zobrazí na portálu společnosti. Názvy všech používaných aplikací musí být jedinečné. Pokud stejný název sady aplikací existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis sady** – zadejte popis sady aplikací.
    - **Vydavatel** – jako vydavatel se zobrazí Microsoft.
    - **Kategorie** – můžete vybrat jednu nebo několik předdefinovaných kategorií nebo kategorii, kterou jste vytvořili. Uživatelé tak dokážou sadu aplikací při procházení portálu společnosti jednodušeji najít.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – sada aplikací se uživatelům, kteří hledají aplikace, zobrazí na výrazném místě na hlavní stránce Portálu společnosti.
    - **Adresa URL informací** – volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů** – volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář** – jako vývojář se zobrazí Microsoft.
    - **Vlastník** – jako vlastník se zobrazí Microsoft.
    - **Poznámky** – zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Nahrát ikonu** – nahrajte ikonu, která se zobrazí u aplikace, když uživatelé procházejí portál společnosti.
3.  Vyberte **OK**. Sada se zobrazí v seznamu aplikací jako jedna položka.

## <a name="configure-app-assignments"></a>Konfigurace přiřazení aplikací

V tomto kroku nakonfigurujte, jakým skupinám sadu aplikací přiřadíte. Typ dostupné aplikace teprve připravujeme.

1.  V seznamu aplikací vyberte jejich sadu a pak zvolte **Přiřazení**.
2.  Zvolte **Vybrat skupiny**.
3.  Přiřaďte sadu vybraným skupinám. Další informace najdete v článku [Jak přiřadit aplikace do skupin pomocí Microsoft Intune](/intune/apps-deploy).
4.  V každé skupině vyberte, že **vyžaduje instalaci**.
        >[!Note]
        > You cannot uninstall Office 365 through Intune.

5. Přiřazení potvrďte volbou **Uložit**.

## <a name="next-steps"></a>Další kroky

Další informace o přidání aplikací Office 365 do zařízení s Windows 10 najdete v článku [Přiřazení aplikací Office 365 ProPlus 2016 k zařízením s Windows 10 pomocí Microsoft Intune](/intune/apps-add-office365).
