---
title: "Přidání integrovaných aplikací na mobilní zařízení pomocí Intune"
titlesuffix: Azure portal
description: "Zjistěte, jak můžete s Intune zjednodušit instalaci na mobilní zařízení s integrovanými aplikacemi."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 90bec6442084e46f499c57cf128e6ef57fe1ce9c
ms.sourcegitcommit: 0a5f424a8f683daa919b13b5c363173040d561c8
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/14/2018
---
# <a name="how-to-add-built-in-apps-to-microsoft-intune"></a>Přidání integrovaných aplikací do Microsoft Intune

**Integrovaný** typ aplikace usnadňuje přiřazení kurátorovaných spravovaných aplikací, jako jsou například aplikace Office 365, k zařízením s iOSem a Androidem. Pro tento typ aplikace můžete přiřadit konkrétní aplikace, jako je například Excel, Power BI, SharePoint, Teams, OneDrive, Outlook, Skype a další. Po přidání aplikace se zobrazí typ aplikace jako **Integrovaná aplikace pro iOS** nebo **Integrovaná aplikace pro Android**. Když použijete integrovaný typ aplikace, můžete vybrat, které z těchto konkrétních aplikací chcete publikovat do zařízení uživatelů.

 Ve starších edicích konzoly Intune bylo v Intune několik výchozích spravovaných aplikací Office 365, jako je Outlook a OneDrive. Typ aplikace se u těchto spravovaných aplikací označoval jako Spravovaná aplikace z obchodu pro iOS nebo jako Spravovaná aplikace z obchodu pro Android. Doporučujeme, abyste místo možnosti Spravovaná aplikace z obchodu pro iOS nebo Spravovaná aplikace z obchodu pro Android použili integrované typy aplikací, které poskytují větší flexibilitu při úpravách a odstraňování aplikací Office 365.

>[!NOTE]
>Výchozí aplikace Office 365 označené jako Spravovaná aplikace z obchodu pro iOS a Spravovaná aplikace z obchodu pro Android se při odstranění všech přiřazení této aplikace ze seznamu aplikací odeberou.

## <a name="add-built-in-app"></a>Přidání integrované aplikace

Následující postup umožňuje přidat integrovanou aplikaci k aplikacím, které jsou dostupné v Microsoft Intune.
1.  Přihlaste se k portálu Azure Portal.
2.  Zobrazte okno Microsoft Intune tak, že zvolíte **Další služby** > **Monitorování + správa** > **Intune**.
3.  V okně **Intune** zvolte **Mobilní aplikace**.
4.  V okně **Mobilní aplikace** zvolte ve skupině **Spravovat** možnost **Aplikace**.
5.  Vyberte **Přidat** a přidejte novou aplikaci.
6.  V okně aplikace **Přidat** vyberte ze seznamu **Typ aplikace** možnost **Integrovaná aplikace**.
7.  Klikněte na **Vybrat aplikaci** a vyberte integrované aplikace, které chcete zahrnout.
8.  V okně Integrovaná aplikace vyberte aplikace, které chcete zahrnout.
9.  Pokud chcete zahrnout aplikace, klikněte v okně **Přidat aplikaci** na tlačítko **Přidat**.


## <a name="configure-app-information"></a>Konfigurace informací o aplikaci

Informace o integrované aplikaci můžete upravit. Tyto informace vám pomůžou identifikovat aplikaci v Intune a také pomůžou uživatelům, aby ji našli v aplikaci Portál společnosti.
1.  V okně **Mobilní aplikace – Aplikace** vyberte integrovanou aplikaci, kterou chcete upravit. Zobrazí se okno pro integrovanou aplikaci.
2.  Ve skupině **Spravovat** vyberte možnost **Vlastnosti**.
3.  Pokud chcete upravit informace o integrované aplikaci, vyberte možnost **Konfigurovat**.
4.  V okně **Informace o aplikaci** můžete upravit následující údaje:
    -   **Název** – zadejte název integrované aplikace, který se zobrazí na portálu společnosti. Všechny používané názvy musí být jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    -   **Popis** – zadejte popis aplikace. 
    -   **Vydavatel** – zadejte název vydavatele aplikace.
    -   **Kategorie** – volitelně vyberte jednu nebo více kategorií integrovaných aplikací. Nastavením této možnosti uživatelům usnadníte vyhledání aplikace při procházení portálu společnosti.
    -   **Zobrazit na Portálu společnosti jako vybranou aplikaci** – aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    -   **Adresa URL informací** – volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    -   **Adresa URL informací o ochraně osobních údajů** – volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    -   **Vývojář** – volitelně zadejte jméno vývojáře aplikace.
    -   **Vlastník** – volitelně zadejte vlastníka aplikace, například Personální oddělení.
    -   **Poznámky** – zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    -   **Nahrát ikonu** – nahrajte ikonu, která se zobrazí u aplikace, když uživatelé procházejí portál společnosti.
3.  Až to budete mít, klikněte v okně **Informace o aplikaci** na **OK**.
4.  V okně **Vlastnosti** klikněte na **Uložit**.

## <a name="next-steps"></a>Další kroky

Nyní můžete přiřadit aplikace do skupin podle vlastního výběru. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).
