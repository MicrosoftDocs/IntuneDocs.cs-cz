---
title: Přidání obchodní aplikace pro iOS do Microsoft Intune
titlesuffix: ''
description: Přečtěte si o přidávání obchodních aplikací pro iOS do Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bbf02fc9633cca5059a6c58c3ef021f05469be60
ms.sourcegitcommit: f69f2663ebdd9c1def68423e8eadf30f86575f7e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2018
ms.locfileid: "49075589"
---
# <a name="add-an-ios-line-of-business-app-to-microsoft-intune"></a>Přidání obchodní aplikace pro iOS do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Informace v tomto článku vám pomůžou přidat do Microsoft Intune obchodní aplikaci pro iOS.

>[!NOTE]
>Uživatelé iOS zařízení můžou odebrat některé výchozí aplikace pro iOS, například Akcie nebo Mapy. Intune je ale neumožňuje znovu nasadit. Pokud uživatel tyto aplikace odstraní, musí si je znovu nainstalovat z App Storu.

## <a name="step-1-specify-the-software-setup-file"></a>Krok 1: Určení instalačního souboru softwaru

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V úloze **Klientské aplikace** vyberte **Spravovat** > **Aplikace**.
5. Nad seznamem aplikací vyberte **Přidat**.
6. V podokně **Přidat aplikaci** vyberte **Obchodní aplikace**.

## <a name="step-2-configure-the-app-package-file"></a>Krok 2: Konfigurace souboru balíčku aplikace

1. V podokně **Přidat aplikaci** zvolte **Soubor balíčku aplikace**.
2. V podokně **Soubor balíčku aplikace** vyberte tlačítko Procházet. Potom vyberte instalační soubor pro iOS s příponou **.ipa**.
3. Až to budete mít, vyberte **OK**.


## <a name="step-3-configure-app-information"></a>Krok 3: Konfigurace informací o aplikaci

1. V podokně **Přidat aplikaci** vyberte **Informace o aplikaci**.
2. V podokně **Informace o aplikaci** přidejte podrobnosti o aplikaci. V závislosti na zvolené aplikaci můžou být některé hodnoty v tomto podokně vyplněné automaticky:
    - **Název**: Zadejte název aplikace, který se zobrazí na portálu společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti jen jedna z aplikací.
    - **Popis**: Zadejte popis aplikace. Popis se zobrazí na portálu společnosti.
    - **Vydavatel**: Zadejte název vydavatele aplikace.
    - **Minimální operační systém**: V seznamu zvolte minimální verzi operačního systému, na kterou jde aplikaci nainstalovat. Pokud aplikaci přiřadíte k zařízení se starším operačním systémem, nenainstaluje se.
    - **Ignorovat verzi aplikace**: Nastavte na **Ano**, pokud aplikaci automaticky aktualizuje její vývojář.
    - **Kategorie**: Vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste si vytvořili sami. Díky kategoriím uživatelé aplikaci při procházení portálu společnosti snadněji najdou.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci**: Aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů**: Volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Vývojář**: Volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník**: Volitelně zadejte jméno vlastníka aplikace. Zadat můžete například **Personální oddělení**.
    - **Poznámky**: Zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Logo**: Nahrajte ikonu, která se k aplikaci přidruží. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
3. Až to budete mít, vyberte **OK**.

## <a name="step-4-finish-up"></a>Krok 4: Dokončení

1. V podokně **Přidat aplikaci** ověřte správnost podrobností o aplikaci.
2. Pomocí možnosti **Přidat** nahrajte aplikaci do Intune.

Aplikace, kterou jste vytvořili, se nyní zobrazí v seznamu aplikací. V tomto seznamu můžete aplikace přiřadit do vybraných skupin. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).

> [!NOTE]
> Zřizovací profily obchodních aplikací pro iOS mají lhůtu 30 dnů, pak jejich platnost vyprší.

## <a name="step-5-update-a-line-of-business-app"></a>Krok 5: Aktualizace obchodní aplikace

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

> [!NOTE]
> Aby služba Intune úspěšně nasadila nový soubor IPA do zařízení, musíte zvýšit hodnotu řetězce `CFBundleVersion` v souboru Info.plist v balíčku IPA.

## <a name="next-steps"></a>Další kroky

- Aplikace, kterou jste vytvořili, se zobrazí v seznamu aplikací. Teď ji můžete přiřadit do požadovaných skupin. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).

- Zjistěte, jakými způsoby můžete monitorovat vlastnosti a přiřazení aplikace. Viz [Postup monitorování informací a přiřazení aplikace](apps-monitor.md).

- Zjistěte více o kontextu své aplikace v Intune. Viz [Přehled životních cyklů zařízení a aplikací](introduction-device-app-lifecycles.md).
