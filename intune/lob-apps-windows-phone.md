---
title: Přidání obchodní aplikace pro Windows Phone do Microsoft Intune
titlesuffix: ''
description: Podívejte se, jak do Intune přidávat obchodní aplikace pro Windows Phone.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: d0a20ad2934163826c017fc0ae8b9ade6e80fcdc
ms.sourcegitcommit: 8019bdd8117806c6a3a73a8c6d40af1a3def6d90
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/11/2018
ms.locfileid: "53247199"
---
# <a name="add-a-windows-phone-line-of-business-app-to-microsoft-intune"></a>Přidání obchodní aplikace pro Windows Phone do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Informace v tomto článku vám pomůžou přidat obchodní aplikaci pro Windows Phone do Microsoft Intune. Obchodní aplikace je aplikace, kterou do Intune přidáte z instalačního souboru aplikace. Tento typ aplikace zpravidla vzniká interně. Intune nainstaluje obchodní aplikaci na zařízení uživatele. 

## <a name="step-1-specify-the-software-setup-file"></a>Krok 1: Určení instalačního souboru softwaru

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V úloze **Klientské aplikace** vyberte **Spravovat** > **Aplikace**.
5. Nad seznamem aplikací vyberte **Přidat**.
6. V podokně **Přidat aplikaci** vyberte **Obchodní aplikace**.

## <a name="step-2-configure-the-app-package-file"></a>Krok 2: Konfigurace souboru balíčku aplikace

1. V podokně **Přidat aplikaci** zvolte **Soubor balíčku aplikace**.
2. V podokně **Soubor balíčku aplikace** vyberte tlačítko Procházet. Potom vyberte instalační soubor Windows Phone s příponou **.xap**.
3. Až to budete mít, vyberte **OK**.


## <a name="step-3-configure-app-information"></a>Krok 3: Konfigurace informací o aplikaci

1. V podokně **Přidat aplikaci** vyberte **Informace o aplikaci**.
2. V podokně **Informace o aplikaci** nakonfigurujte následující informace o aplikaci. V závislosti na zvolené aplikaci můžou být některé hodnoty v tomto podokně vyplněné automaticky:
    - **Název**: Zadejte název aplikace, zobrazí se v aplikaci portál společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti jen jedna z aplikací.
    - **Popis**: Zadejte popis aplikace. Popis se zobrazí na portálu společnosti.
    - **Vydavatel**: Zadejte název vydavatele aplikace.
    - **Kategorie**: Vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Díky kategoriím uživatelé aplikaci při procházení portálu společnosti snadněji najdou.
    - **Zobrazit tuto aplikaci jako doporučenou aplikaci portálu společnosti**: Když uživatelé hledají aplikace, zobrazí se aplikace výrazně na hlavní stránce portálu společnosti.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Soukromá adresa URL**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Pro vývojáře**: Volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník**: Volitelně zadejte jméno vlastníka této aplikace. Zadat můžete například **Personální oddělení**.
    - **Poznámky k**: Zadejte jakékoli poznámky, které chcete přidružit k této aplikaci.
    - **Logo**: Nahrajte ikonu, která je spojená s aplikací. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
3. Až to budete mít, vyberte **OK**.

## <a name="step-4-finish-up"></a>Krok 4: Dokončení

1. V podokně **Přidat aplikaci** zkontrolujte správnost nakonfigurovaných informací.
2. Pomocí možnosti **Přidat** nahrajte aplikaci do Intune.

## <a name="next-steps"></a>Další postup

- Aplikace, kterou jste vytvořili, se zobrazí v seznamu aplikací. Teď ji můžete přiřadit do požadovaných skupin. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).

- Zjistěte, jakými způsoby můžete monitorovat vlastnosti a přiřazení aplikace. Viz [Postup monitorování informací a přiřazení aplikace](apps-monitor.md).

- Zjistěte více o kontextu své aplikace v Intune. Viz [Přehled životních cyklů zařízení a aplikací](introduction-device-app-lifecycles.md).
