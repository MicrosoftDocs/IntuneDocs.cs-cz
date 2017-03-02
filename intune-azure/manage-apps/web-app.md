---
title: "Přidání webových aplikací do Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si informace o přidání webových aplikací do Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: c2e54d3e57a4b02ba277b88cc672d5587c449281
ms.lasthandoff: 02/18/2017

---

# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Přidání webových aplikací do Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Spravovat aplikace**.
4. V úloze **Mobilní aplikace** zvolte **Spravovat** > **Aplikace**.
5. Nad seznamem aplikací zvolte **Přidat**.
6. V okně **Přidat aplikaci** zvolte **Informace o aplikaci**.
7. V okně **Upravit aplikaci** nakonfigurujte následující údaje. Až skončíte, klikněte na **Přidat**:
    - **Adresa URL aplikace** – zadejte adresu URL webu hostujícího aplikaci, kterou chcete nasadit.
    - **Název aplikace** – zadejte název aplikace, který se zobrazí na portálu společnosti.
    - **Popis aplikace** – zadejte popis aplikace. Zobrazí se koncovým uživatelům na portálu společnosti.
    - **Vydavatel** – zadejte název vydavatele této aplikace.
    - **Kategorie (volitelné)** – vyberte jednu nebo několik předdefinovaných nebo vytvořených kategorií. Uživatelé ji budou moct při procházení portálu snáz najít.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **K otevření tohoto odkazu vyžadovat spravovaný prohlížeč** – když nasadíte odkaz na web nebo do webové aplikace pro uživatele, budou ho moct otevřít jen v prohlížeči spravovaném přes Intune. Tento prohlížeč musí být nainstalovaný na jejich zařízení.
    - **Nahrát ikonu** – nahrajte ikonu, která bude spojená s aplikací. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
8. Až skončíte, zvolte v okně **Přidat aplikaci** možnost **Uložit**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřadit ke zvoleným skupinám. Nápovědu najdete v článku [Přiřazení aplikací do skupin](/intune-azure/manage-apps/deploy-apps).
