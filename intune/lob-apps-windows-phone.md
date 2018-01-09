---
title: "Přidání obchodních aplikací pro Windows Phone do Intune"
titlesuffix: Azure portal
description: "Podívejte se, jak do Intune přidat obchodní aplikace pro Windows Phone."
keywords: 
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 93bb2f6b0515febf4b85cb5d11dee379cad46bf5
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/04/2018
---
# <a name="how-to-add-windows-phone-line-of-business-lob-apps-to-microsoft-intune"></a>Přidání obchodních aplikací pro Windows Phone do Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a>Krok 1 – určení instalačního souboru softwaru

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** + **Intune**.
3. V okně **Intune** zvolte **Spravovat aplikace**.
4. V úloze **Mobilní aplikace** zvolte **Spravovat** > **Aplikace**.
5. Nad seznamem aplikací zvolte **Přidat**.
6. V okně **Přidat aplikaci** zvolte **Obchodní aplikace**.

## <a name="step-2---configure-the-app-package-file"></a>Krok 2 – konfigurace souboru balíčku aplikace

1. V okně **Přidat aplikaci** zvolte **Soubor balíčku aplikace**.
2. V okně **Soubor balíčku aplikace** klikněte na tlačítko Procházet a vyberte instalační soubor Windows Phone s příponou **.xap**.
3. Po dokončení zvolte **OK**.


## <a name="step-3---configure-app-information"></a>Krok 3 – konfigurace informací o aplikaci

1. V okně **Přidat aplikaci** zvolte **Soubor balíčku aplikace**.
2. V okně **Informace o aplikaci** nakonfigurujte následující informace o aplikaci. V závislosti na zvolené aplikaci mohou být některé hodnoty v tomto okně vyplněny automaticky:
    - **Název** – zadejte název aplikace, který se zobrazí na portálu společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis** – zadejte popis aplikace. Popis se uživatelům zobrazí na portálu společnosti.
    - **Vydavatel** – zadejte název vydavatele aplikace.
    - **Kategorie** – vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste si vytvořili sami. S použitím kategorií budou moct uživatelé aplikaci při procházení portálu společnosti jednodušeji najít.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací** – volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů** – volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář** – volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník** – volitelně zadejte vlastníka aplikace, například **Personální oddělení**.
    - **Poznámky** – zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Logo** – nahrajte ikonu, která se přidruží k aplikaci. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
3. Po dokončení zvolte **OK**.

## <a name="step-4---finish-up"></a>Krok 4 – dokončení

1. V okně **Přidat aplikaci** zkontrolujte správnost nakonfigurovaných informací.
2. Zvolte **Přidat** a nahrajte aplikaci do Intune.

## <a name="next-steps"></a>Další kroky

Aplikace, kterou jste vytvořili, se zobrazí v seznamu aplikací. Nyní ji můžete přiřadit do požadované skupiny. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).

Zjistěte, jakými způsoby můžete monitorovat vlastnosti a přiřazení aplikace. Další informace najdete v tématu [Postup monitorování informací a přiřazení aplikace](apps-monitor.md).

Zjistěte více o kontextu své aplikace v Intune. Další informace najdete v tématu [Přehled životních cyklů zařízení a aplikací](introduction-device-app-lifecycles.md).
