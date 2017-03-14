---
title: "Přidání obchodních aplikací pro iOS do Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Podívejte se, jak přidat do Intune obchodní aplikace pro iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 141207ac61aade0816a66eb6e672596416bc0906
ms.lasthandoff: 02/18/2017

---

# <a name="how-to-add-ios-line-of-business-lob-apps-to-microsoft-intune"></a>Přidání obchodních aplikací pro iOS do Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="step-1---specify-the-software-setup-file"></a>Krok 1 – určení instalačního souboru softwaru

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně Intune zvolte **Spravovat aplikace**.
4. V úloze **Mobilní aplikace** zvolte Spravovat > **Aplikace**.
5. Nad seznamem aplikací zvolte **Přidat**.
6. V okně **Přidat aplikaci** zvolte **Instalační soubor softwaru**.
7. V okně **Vybrat instalační soubor** klikněte na tlačítko pro procházení a přejděte na instalační soubor aplikace pro iOS (s příponou .ipa). Pak klikněte na **OK**.

## <a name="step-2---configure-app-information"></a>Krok 2 – konfigurace informací o aplikaci

1. V okně **Upravit aplikaci** nakonfigurujte následující údaje. Až skončíte, klikněte na **Přidat**. V závislosti na zvolené aplikaci mohou být některé hodnoty v tomto okně vyplněny automaticky:
    - **Název aplikace** – zadejte název aplikace, který se zobrazí na portálu společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis aplikace** – zadejte popis aplikace. Zobrazí se uživatelům na portálu společnosti.
    - **Vydavatel** – zadejte název vydavatele aplikace.
    - **Použitelný typ zařízení** – vyberte, jestli se dá tato aplikace nainstalovat na iPady, iPhony nebo na kompatibilní iPody.
    - **Minimální operační systém** – v seznamu zvolte minimální verzi operačního systému, na kterou lze aplikaci nainstalovat. Pokud aplikaci přiřadíte k zařízení se starším operačním systémem, nenainstaluje se.
    - **Kategorie (volitelné)** – vyberte jednu nebo několik předdefinovaných nebo vytvořených kategorií aplikací. Uživatelé ji budou moct při procházení portálu snáz najít.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací** – volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů** – volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář** – volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník** – volitelně zadejte vlastníka aplikace, například **Personální oddělení**.
    - **Poznámky** – zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Nahrát ikonu** – nahrajte ikonu, která bude spojená s aplikací. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
2. Až skončíte, zvolte v okně **Přidat aplikaci** možnost **Uložit**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřadit ke zvoleným skupinám. Nápovědu najdete v článku [Přiřazení aplikací do skupin](/intune-azure/manage-apps/deploy-apps).
