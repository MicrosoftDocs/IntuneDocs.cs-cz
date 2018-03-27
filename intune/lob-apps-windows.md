---
title: Přidání obchodních aplikací pro Windows do Microsoft Intune
titlesuffix: ''
description: Zjistěte, jak přidat obchodní aplikace pro Windows do Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f975f2018d2ce1d7affded3c3386c479e6877388
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a>Přidání obchodních aplikací pro Windows do Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Obchodní aplikace (LOB) je aplikace, kterou přidáte z instalačního souboru aplikace. Tyto typy aplikací obvykle vznikají interně. Následující kroky obsahují pokyny k přidání obchodní aplikace pro Windows do Microsoft Intune.

## <a name="step-1---specify-the-software-setup-file"></a>Krok 1 – určení instalačního souboru softwaru

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Na stránce **Intune** zvolte **Mobilní aplikace**.
4. V úloze **Mobilní aplikace** zvolte **Spravovat** > **Aplikace**.
5. Nad seznamem aplikací zvolte **Přidat**.
6. V podokně **Přidat aplikaci** zvolte **Obchodní aplikace**.

## <a name="step-2---configure-the-app-package-file"></a>Krok 2 – konfigurace souboru balíčku aplikace

1. V podokně **Přidat aplikaci** zvolte **Soubor balíčku aplikace**.
2. V podokně **Soubor balíčku aplikace** klikněte na tlačítko Procházet a vyberte instalační soubor Windows s příponou **.msi**, **.appx** nebo **.appxbundle**.
3. Po dokončení zvolte **OK**.


## <a name="step-3---configure-app-information"></a>Krok 3 – konfigurace informací o aplikaci

1. V podokně **Přidat aplikaci** zvolte **Soubor balíčku aplikace**.
2. V podokně **Informace o aplikaci** nakonfigurujte následující informace (některé hodnoty v tomto podokně můžou být vyplněné automaticky):
    - **Název** – zadejte název aplikace, který se zobrazí na portálu společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis** – zadejte popis aplikace. Popis se uživatelům zobrazí na portálu společnosti.
    - **Vydavatel** – zadejte název vydavatele aplikace.
    - **Ignorovat verzi aplikace** – nastavte na **Ano**, pokud aplikaci automaticky aktualizuje její vývojář.
    - **Kategorie** – vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste si vytvořili sami. S použitím kategorií budou moct uživatelé aplikaci při procházení portálu společnosti jednodušeji najít.
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

1. V podokně **Přidat aplikaci** zkontrolujte správnost nakonfigurovaných informací o aplikaci.
2. Zvolte **Přidat** a nahrajte aplikaci do Intune.

## <a name="step-5---update-a-line-of-business-app"></a>Krok 5 – aktualizace obchodní aplikace

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## <a name="configuring-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Konfigurace automaticky aktualizované mobilní aplikace MSI na ignorování procesu kontroly verzí

Známou automaticky aktualizovanou mobilní aplikaci MSI můžete nakonfigurovat tak, aby ignorovala proces kontroly verzí. Některé aplikace založené na instalační službě MSI automaticky aktualizuje vývojář aplikace. Pro tyto automaticky aktualizované aplikace MSI můžete v okně **Informace o aplikaci** nakonfigurovat nastavení **Ignorovat verzi aplikace**. Po přepnutí tohoto nastavení na **Ano** nebude Microsoft Intune vynucovat verzi aplikace instalovanou na klientovi Windows. Tato možnost je užitečná, když chcete předejít konfliktu časování. K tomuto typu konfliktu časování může například dojít, když aplikaci automaticky aktualizuje vývojář a současně Intune. Jak vývojář, tak Intune můžou vynucovat verzi aplikace na klientovi Windows, což může způsobit konflikt.

## <a name="next-steps"></a>Další kroky

- Aplikace, kterou jste vytvořili, se zobrazí v seznamu aplikací. Nyní ji můžete přiřadit do požadované skupiny. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).

- Zjistěte, jakými způsoby můžete monitorovat vlastnosti a přiřazení aplikace. Další informace najdete v tématu [Postup monitorování informací a přiřazení aplikace](apps-monitor.md).

- Zjistěte více o kontextu své aplikace v Intune. Další informace najdete v tématu [Přehled životních cyklů zařízení a aplikací](introduction-device-app-lifecycles.md).
