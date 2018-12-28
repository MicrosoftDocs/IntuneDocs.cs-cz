---
title: Přidání aplikací pro App Store (iOS) do Microsoft Intune
titlesuffix: ''
description: Zjistěte, jak do Microsoft Intune přidat aplikace z obchodu pro iOS. Můžete přiřadit aplikace pomocí této metody, pokud aplikace jsou zadarmo dostupné v App Store.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5f1423b0f2f216f65026d2b1a7bf52dda39c9f88
ms.sourcegitcommit: 4e69a8664c289263490daa4c02bc6b81c33196e5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53642502"
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>Přidání aplikací pro App Store (iOS) do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Informace v tomto článku vám pomůžou přidat do Intune aplikace z obchodu pro iOS. Aplikace z App Storu (iOS) jsou aplikace, které Intune instaluje na zařízení uživatelů. Uživatel je jeden ze zaměstnanců společnosti. Aplikace z obchodu pro iOS se automaticky aktualizují.

>[!NOTE]
>Uživatelé zařízení s iOSem můžou odebrat některé integrované aplikace pro iOS, jako jsou například aplikace Akcie a Mapy, nemůžou je ale s použitím Intune znovu nasadit. Pokud uživatel tyto aplikace odstraní, musí si je znovu ručně nainstalovat z App Storu.

## <a name="before-you-start"></a>Než začnete

Pomocí této metody můžete aplikace přiřazovat jen v případě, že jsou v App Storu bezplatné. Pokud chcete pomocí Intune přiřazovat placené aplikace, zvažte použití [programu Volume Purchase Program (Program hromadných nákupů) pro iOS](vpp-apps-ios.md).

>[!NOTE]
>Při práci s Microsoft Intune doporučujeme používat prohlížeč Microsoft Edge nebo Google Chrome.

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**.  
    Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V podokně úloh **Klientské aplikace** vyberte v části **Spravovat** možnost **Aplikace**.
5. V podokně **Aplikace** vyberte **Přidat**.
6. V seznamu **Typ aplikace** vyberte z typů **Aplikace pro Store** možnost **iOS**.
7. Vyberte **Hledat v App Storu**.
8. V podokně **Hledat v App Storu** vyberte národní prostředí App Storu.
9. Do **vyhledávacího** pole zadejte název (nebo část názvu) aplikace.  
    Intune prohledá Store a vrátí seznam relevantních výsledků.
10. V seznamu výsledků vyberte požadovanou aplikaci a pak vyberte **Vybrat**.
11. V podokně **Přidat aplikaci** zvolte **Informace o aplikaci** a nakonfigurujte aplikaci.
12. V podokně **Informace o aplikaci** přidejte informace o aplikaci. V závislosti na zvolené aplikaci můžou být některé hodnoty v tomto podokně vyplněné automaticky:
    - **Název**: Zadejte název aplikace, jak je zobrazený na portálu společnosti. Ujistěte se, že používaný název aplikace je jedinečný. Pokud je název aplikace duplicitní, zobrazí se uživatelům na Portálu společnosti pouze jeden název.
    - **Popis**: Zadejte popis aplikace. Tento popis se uživatelům zobrazí na Portálu společnosti.
    - **Vydavatel**: Zadejte název vydavatele aplikace.
    - **Adresa URL obchodu**: Zadejte adresu URL aplikace App Store aplikace, kterou chcete vytvořit.
    - **Minimální verzi operačního systému**: V seznamu vyberte nejstarší verzi operačního systému, na které můžete aplikaci nainstalovat. Pokud aplikaci přiřadíte k zařízení se starším operačním systémem, nenainstaluje se.
    - **Použitelný typ zařízení**: V seznamu vyberte zařízení, která používají aplikaci.
    - **Kategorie**: Volitelně vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Uživatelé tak při procházení Portálu společnosti najdou aplikaci snadněji.
    - **Zobrazit tuto aplikaci jako doporučenou aplikaci portálu společnosti**: Vyberte tuto možnost, chcete-li zobrazit sadu aplikací výrazném místě na hlavní stránce portálu společnosti když uživatelé vyhledávají aplikace.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Soukromá adresa URL**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Pro vývojáře**: Volitelně zadejte jméno vývojáře aplikace. Toto pole je viditelné jen pro správce, uživatelé ho nevidí.
    - **Vlastník**: Volitelně zadejte jméno vlastníka aplikace, například *Personální oddělení*. Toto pole je viditelné jen pro správce, uživatelé ho nevidí.
    - **Poznámky k**: Volitelně zadejte jakékoli poznámky, které chcete přidružit k této aplikaci. Toto pole vidí jenom správce a koncoví uživatelé je neuvidí.
    - **Logo**: Volitelně nahrajte ikonu, která bude spojená s aplikací. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
13. Vyberte **OK**.
14. Vyberte **Přidat**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřazovat vybraným skupinám.

## <a name="next-steps"></a>Další postup

- [Přiřazení aplikací skupinám](apps-deploy.md)
