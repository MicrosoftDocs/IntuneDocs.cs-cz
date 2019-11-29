---
title: Přidání aplikací pro App Store (iOS) do Microsoft Intune
titleSuffix: ''
description: Zjistěte, jak do Microsoft Intune přidat aplikace z obchodu pro iOS. Pomocí této metody můžete přiřadit aplikace, pokud jsou aplikace zdarma v App Storu.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c5616b27b97d5623958ec872390e2a6de79db3c5
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563452"
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>Přidání aplikací pro App Store (iOS) do Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Informace v tomto článku vám pomůžou přidat do Intune aplikace z obchodu pro iOS. Aplikace z App Storu (iOS) jsou aplikace, které Intune instaluje na zařízení uživatelů. Uživatel je jeden ze zaměstnanců společnosti. Aplikace z obchodu pro iOS se automaticky aktualizují.

>[!NOTE]
>Uživatelé zařízení s iOSem můžou odebrat některé integrované aplikace pro iOS, jako jsou například aplikace Akcie a Mapy, nemůžou je ale s použitím Intune znovu nasadit. Pokud uživatel tyto aplikace odstraní, musí si je znovu ručně nainstalovat z App Storu.

## <a name="before-you-start"></a>Než začnete

Pomocí této metody můžete aplikace přiřazovat jen v případě, že jsou v App Storu bezplatné. Pokud chcete pomocí Intune přiřazovat placené aplikace, zvažte použití [programu Volume Purchase Program (Program hromadných nákupů) pro iOS](vpp-apps-ios.md).

>[!NOTE]
>Při práci s Microsoft Intune doporučujeme používat prohlížeč Microsoft Edge nebo Google Chrome.

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **aplikace** > **všechny aplikace** > **Přidat**.
3. V seznamu **Typ aplikace** vyberte z typů **Aplikace pro Store** možnost **iOS**.
4. Vyberte **Hledat v App Storu**.
5. V podokně **Hledat v App Storu** vyberte národní prostředí pro zemi nebo oblast obchodu App Store.
6. Do **vyhledávacího** pole zadejte název (nebo část názvu) aplikace.  
    Intune prohledá Store a vrátí seznam relevantních výsledků.
7. V seznamu výsledků vyberte požadovanou aplikaci a pak vyberte **Vybrat**.
8. V podokně **Přidat aplikaci** zvolte **Informace o aplikaci** a nakonfigurujte aplikaci.
9. V podokně **Informace o aplikaci** přidejte informace o aplikaci. V závislosti na zvolené aplikaci můžou být některé hodnoty v tomto podokně vyplněné automaticky:
    - **Název**: Zadejte název aplikace, který se zobrazí na Portálu společnosti. Ujistěte se, že používaný název aplikace je jedinečný. Pokud je název aplikace duplicitní, zobrazí se uživatelům na Portálu společnosti pouze jeden název.
    - **Popis**: Zadejte popis aplikace. Tento popis se uživatelům zobrazí na Portálu společnosti.
    - **Vydavatel**: Zadejte název vydavatele aplikace.
    - **Adresa URL v obchodu s aplikacemi**: Zadejte adresu URL v obchodu s aplikacemi pro aplikaci, kterou chcete vytvořit.
    - **Minimální operační systém**: V seznamu vyberte nejstarší verzi operačního systému, na kterou je možné aplikaci nainstalovat. Pokud aplikaci přiřadíte k zařízení se starším operačním systémem, nenainstaluje se.
    - **Použitelný typ zařízení**: V seznamu vyberte zařízení, která aplikace používá.
    - **Kategorie**: Volitelně můžete vybrat jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Uživatelé tak při procházení Portálu společnosti najdou aplikaci snadněji.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci:** Vybráním této možnosti se sada aplikací zobrazí uživatelům, kteří hledají aplikace, na výrazném místě na hlavní stránce Portálu společnosti.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů**: Volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář**: Volitelně zadejte jméno vývojáře aplikace. Toto pole je viditelné jen pro správce, uživatelé ho nevidí.
    - **Vlastník**: Volitelně zadejte vlastníka aplikace, například *Personální oddělení*. Toto pole je viditelné jen pro správce, uživatelé ho nevidí.
    - **Poznámky**: Volitelně zadejte jakékoli poznámky, které chcete k aplikaci přidružit. Toto pole vidí jenom správce a koncoví uživatelé je neuvidí.
    - **Logo**: Volitelně nahrajte ikonu, která se přidruží k aplikaci. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
10. Vyberte **OK**.
11. Vyberte **Přidat**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřazovat vybraným skupinám.

## <a name="next-steps"></a>Další kroky

- [Přiřazení aplikací skupinám](apps-deploy.md)
