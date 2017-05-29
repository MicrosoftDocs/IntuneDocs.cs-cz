---
title: "Přidání obchodních aplikací pro Windows do Intune | Dokumentace Microsoftu"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Zjistěte, jak do Intune přidat obchodní aplikace pro Windows."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 696c8f8e72e21c792474f5e52fad9054b3dfade9
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a>Přidání obchodních aplikací pro Windows do Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]


## <a name="step-1---specify-the-software-setup-file"></a>Krok 1 – určení instalačního souboru softwaru

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Spravovat aplikace**.
4. V úloze **Mobilní aplikace** zvolte **Spravovat** > **Aplikace**.
5. Nad seznamem aplikací zvolte **Přidat**.
6. V okně **Přidat aplikaci** zvolte **Obchodní aplikace**.

## <a name="step-2---configure-the-app-package-file"></a>Krok 2 – konfigurace souboru balíčku aplikace

1. V okně **Přidat aplikaci** zvolte **Soubor balíčku aplikace**.
2. V okně **Soubor balíčku aplikace** klikněte na tlačítko Procházet a vyberte instalační soubor Windows s příponou **.msi** (jiné typy instalačních souborů nejsou podporované).
3. Po dokončení zvolte **OK**.


## <a name="step-3---configure-app-information"></a>Krok 3 – konfigurace informací o aplikaci

1. V okně **Přidat aplikaci** zvolte **Soubor balíčku aplikace**.
2. V okně **Informace o aplikaci** nakonfigurujte následující údaje. V závislosti na zvolené aplikaci mohou být některé hodnoty v tomto okně vyplněny automaticky:
    - **Název** – zadejte název aplikace, který se zobrazí na portálu společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis** – zadejte popis aplikace. Zobrazí se uživatelům na portálu společnosti.
    - **Vydavatel** – zadejte název vydavatele aplikace.
    - **Kategorie** – vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste si vytvořili sami. Uživatelé ji budou moct při procházení portálu snáz najít.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací** – volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů** – volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Argumenty příkazového řádku** – volitelně zadejte jakékoli argumenty příkazového řádku, které chcete použít ke spuštění souboru .msi (například **/q**).
    - **Vývojář** – volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník** – volitelně zadejte vlastníka aplikace, například **Personální oddělení**.
    - **Poznámky** – zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Logo** – nahrajte ikonu, která se přidruží k aplikaci. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
3. Po dokončení zvolte **OK**.

## <a name="step-4---finish-up"></a>Krok 4 – dokončení

1. V okně **Přidat aplikaci** zkontrolujte správnost nakonfigurovaných informací.
2. Zvolte **Přidat** a nahrajte aplikaci do Intune.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřadit ke zvoleným skupinám. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).

