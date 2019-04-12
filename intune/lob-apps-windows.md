---
title: Přidání obchodní aplikace pro Windows do Microsoft Intune
titleSuffix: ''
description: Zjistěte, jak přidat aplikace – obchodní (LOB) s Windows pomocí Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/10/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ca41e12136911cc0aecb6968a949fb738e2e2d77
ms.sourcegitcommit: d1116c70bd0f2382d590091e0e66095de3925324
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/11/2019
ms.locfileid: "59504557"
---
# <a name="add-a-windows-line-of-business-app-to-microsoft-intune"></a>Přidání obchodní aplikace pro Windows do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Obchodní aplikace (LOB) je aplikace, kterou přidáte z instalačního souboru aplikace. Tento typ aplikace zpravidla vzniká interně. Následující kroky obsahují pokyny k přidání obchodní aplikace pro Windows do Microsoft Intune.

## <a name="step-1-specify-the-software-setup-file"></a>Krok 1: Určení instalačního souboru softwaru

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V úloze **Klientské aplikace** vyberte **Spravovat** > **Aplikace**.
5. Nad seznamem aplikací vyberte **Přidat**.
6. V podokně **Přidat aplikaci** vyberte **Obchodní aplikace**.

## <a name="step-2-configure-the-app-package-file"></a>Krok 2: Konfigurace souboru balíčku aplikace

1. V podokně **Přidat aplikaci** zvolte **Soubor balíčku aplikace**.
2. V podokně **Soubor balíčku aplikace** vyberte tlačítko Procházet. Potom vyberte instalační soubor Windows s příponou **.msi**, **.appx** nebo **.appxbundle**.

    > [!NOTE]
    > Mezi přípony souborů aplikací pro Windows patří **.msi**, **.appx**, **.appxbundle**, **.msix** a **.msixbundle**.  

1. Až to budete mít, vyberte **OK**.


## <a name="step-3-configure-app-information"></a>Krok 3: Konfigurace informací o aplikaci

1. V podokně **Přidat aplikaci** vyberte **Informace o aplikaci**.
2. V podokně **Informace o aplikaci** nakonfigurujte následující údaje. Některé hodnoty v tomto podokně mohou být vyplněné automaticky.
    - **Název**: Zadejte název aplikace, zobrazí se v aplikaci portál společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti jen jedna z aplikací.
    - **Popis**: Zadejte popis aplikace. Popis se zobrazí na portálu společnosti.
    - **Publisher**: Zadejte název vydavatele aplikace.
    - **Ignorovat verzi aplikace**: Nastavte na **Ano** Pokud vývojáři aplikace automaticky aktualizuje aplikaci. Tato možnost platí jen pro mobilní aplikace .msi.
    - **Kategorie**: Vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Díky kategoriím uživatelé aplikaci při procházení portálu společnosti snadněji najdou.
    - **Zobrazit tuto aplikaci jako doporučenou aplikaci portálu společnosti**: Když uživatelé hledají aplikace, zobrazí se aplikace výrazně na hlavní stránce portálu společnosti.
    - **Adresa URL informací**: Volitelně zadejte adresu URL webu, který obsahuje informace o aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Soukromá adresa URL**: Volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů pro aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Argumenty příkazového řádku**: Volitelně zadejte jakékoli argumenty příkazového řádku, které chcete použít soubor .msi spuštění. Příkladem je **/q**.
    - **Pro vývojáře**: Volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník**: Volitelně zadejte jméno vlastníka této aplikace. Zadat můžete například **Personální oddělení**.
    - **Poznámky k**: Zadejte jakékoli poznámky, které chcete přidružit k této aplikaci.
    - **Logo**: Nahrajte ikonu, která je spojená s aplikací. Ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
3. Až to budete mít, vyberte **OK**.

## <a name="step-4-finish-up"></a>Krok 4: Dokončení

1. V podokně **Přidat aplikaci** zkontrolujte správnost nakonfigurovaných informací o aplikaci.
2. Pomocí možnosti **Přidat** nahrajte aplikaci do Intune.

## <a name="step-5-update-a-line-of-business-app"></a>Krok 5: Aktualizace – obchodní aplikace

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## <a name="configure-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Konfigurace automaticky aktualizované mobilní aplikace MSI na ignorování procesu kontroly verzí

Známou automaticky aktualizovanou mobilní aplikaci MSI můžete nakonfigurovat tak, aby ignorovala proces kontroly verzí. 

Některé aplikace založené na instalační službě MSI automaticky aktualizuje vývojář aplikace. Pro tyto automaticky aktualizované aplikace MSI můžete v podokně **Informace o aplikaci** nakonfigurovat nastavení **Ignorovat verzi aplikace**. Po přepnutí tohoto nastavení na **Ano** nebude Microsoft Intune vynucovat verzi aplikace instalovanou na klientovi Windows. 

Tato možnost je užitečná, když chcete předejít konfliktu časování. Ke konfliktu časování může například dojít, když aplikaci automaticky aktualizuje vývojář aplikace a také Intune. Jak vývojář, tak Intune můžou vynucovat verzi aplikace na klientovi Windows, což způsobí konflikt.

## <a name="next-steps"></a>Další postup

- Aplikace, kterou jste vytvořili, se zobrazí v seznamu aplikací. Teď ji můžete přiřadit do požadovaných skupin. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).

- Zjistěte, jakými způsoby můžete monitorovat vlastnosti a přiřazení aplikace. Viz [Postup monitorování informací a přiřazení aplikace](apps-monitor.md).

- Zjistěte více o kontextu své aplikace v Intune. Zobrazit [Přehled životního cyklu aplikací v Microsoft Intune](app-lifecycle.md).
