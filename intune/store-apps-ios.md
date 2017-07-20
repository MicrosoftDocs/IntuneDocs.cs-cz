---
title: "Jak do Intune přidat aplikace pro App Store (iOS)"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak do Intune přidat aplikace pro App Store (iOS)."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 01f7d391939a5d79c5feb23960aec17e668013d0
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2017
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Přidání aplikací pro App Store (iOS) do Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Informace v tomto tématu vám pomůžou přidat do Intune aplikace z obchodu pro iOS.

>[!NOTE]
>Uživatelé zařízení s iOSem můžou odebrat některé integrované aplikace pro iOS, jako jsou například aplikace Akcie a Mapy, ale není možné tyto aplikace s použitím Intune znovu nasadit. Když koncoví uživatelé tyto aplikace odstraní, musí přejít do App Storu a znovu si je ručně nainstalovat.

## <a name="before-you-start"></a>Než začnete

Pomocí této metody můžete aplikace přiřazovat jen v případě, že jsou v obchodě s aplikacemi bezplatné. Pokud chcete pomocí Intune přiřazovat placené aplikace, zvažte použití [programu hromadného nákupu iOS](vpp-apps-ios.md).


## <a name="step-1---search-for-the-app-in-the-store"></a>Krok 1 – vyhledání aplikace ve Storu

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Spravovat aplikace**.
4. V úloze **Mobilní aplikace** zvolte **Spravovat** > Aplikace.
5. Nad seznamem aplikací zvolte **Přidat**.
6. V okně **Přidat aplikaci** zvolte **Hledat v App Storu**.
7. V okně **Hledat v App Storu** zadejte název (nebo část názvu) do vyhledávacího pole. Intune prohledá Store a vrátí seznam relevantních výsledků.
8. Ze seznamu zvolte aplikaci, kterou chcete přidat, a pak klikněte na **OK**.

## <a name="step-2---configure-app-information"></a>Krok 2 – konfigurace informací o aplikaci

1. V okně **Přidat aplikaci** zvolte **Informace o aplikaci**.
2. V okně **Upravit aplikaci** nakonfigurujte následující údaje. Až skončíte, klikněte na **Přidat**. V závislosti na zvolené aplikaci mohou být některé hodnoty v tomto okně vyplněny automaticky:
- **Název aplikace** – zadejte název aplikace, který se zobrazí na portálu společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis aplikace** – zadejte popis aplikace. Zobrazí se uživatelům na portálu společnosti.
- **Vydavatel** – zadejte název vydavatele aplikace.
- **Adresa URL obchodu s aplikacemi** – zadejte adresu URL obchodu s aplikacemi pro aplikaci, kterou chcete vytvořit.
- **Minimální operační systém** – v seznamu zvolte minimální verzi operačního systému, na kterou lze aplikaci nainstalovat. Pokud aplikaci přiřadíte k zařízení se starším operačním systémem, nenainstaluje se.
- **Kategorie** (volitelné). Vyberte jednu nebo několik předdefinovaných nebo vytvořených kategorií aplikací. Uživatelé ji budou moct při procházení portálu snáz najít.
- **Zobrazit na Portálu společnosti jako vybranou aplikaci** – aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
- **Adresa URL informací** – volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
- **Adresa URL informací o ochraně osobních údajů** – volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
- **Vývojář** – volitelně zadejte jméno vývojáře aplikace.
- **Vlastník** – volitelně zadejte vlastníka aplikace, například **Personální oddělení**.
- **Poznámky** – zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
- **Nahrát ikonu** – nahrajte ikonu, která bude spojená s aplikací. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
3. Až skončíte, zvolte v okně **Přidat aplikaci** možnost **Uložit**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřadit ke zvoleným skupinám. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).
