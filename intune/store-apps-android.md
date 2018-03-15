---
title: "Přidání aplikací z obchodu pro Android do Microsoft Intune"
titleSuffix: 
description: "Zjistěte, jak do Microsoft Intune přidat aplikace z obchodu pro Android."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/13/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c2cbc68aa3ea11e3b5593597a94aa059dd2927ed
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="how-to-add-android-store-apps-to-microsoft-intune"></a>Přidání aplikací z obchodu pro Android do Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Před přiřazením aplikace k zařízení nebo skupině uživatelů je nejprve potřeba danou aplikaci přidat do Microsoft Intune. Aplikaci z obchodu pro Android přidáte do Intune z portálu Azure Portal následujícím postupem.

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Microsoft Intune** zvolte **Mobilní aplikace**.
4. V úloze **Mobilní aplikace** zvolte v oddílu **Spravovat** možnost **Aplikace**.
5. Nad seznamem aplikací zvolte **Přidat**.
6. V okně **Přidat aplikaci** vyberte v dostupných typech **Aplikace pro Store** možnost **Android**.
7. Vyberte **Konfigurovat** a nakonfigurujte následující informace o aplikaci. Některé hodnoty v tomto okně můžou být v závislosti na zvolené aplikaci automaticky vyplněné:
    - **Název** – zadejte název aplikace, který se zobrazí na portálu společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis** – zadejte popis aplikace. Tento popis se zobrazí uživatelům na portálu společnosti.
    - **Vydavatel** – zadejte název vydavatele aplikace.
    - **Adresa URL v obchodu s aplikacemi** – zadejte adresu URL v obchodu s aplikacemi pro aplikaci, kterou chcete vytvořit.
    - **Minimální operační systém** – v seznamu zvolte minimální verzi operačního systému, na kterou jde aplikaci nainstalovat. Pokud aplikaci přiřadíte k zařízení se starším operačním systémem, nenainstaluje se.
    - **Kategorie (volitelné)** – vyberte jednu nebo několik předdefinovaných nebo vytvořených kategorií aplikací. Uživatelé ji budou moct při procházení portálu snáz najít.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací** (volitelné) – zadejte adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů** (volitelné) – zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář** (volitelné) – zadejte jméno vývojáře aplikace.
    - **Vlastník** (volitelné) – zadejte vlastníka aplikace, například **Personální oddělení**.
    - **Poznámky** (volitelné) – zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Logo** (volitelné) – nahrajte ikonu, která se přidruží k aplikaci. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
8. Po dokončení nastavení informací o aplikaci klikněte na **OK**.
9. Pokud chcete tuto aplikaci přidat, klikněte na **Přidat**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřazovat vybraným skupinám. 

##<a name="next-steps"></a>Další kroky

- [Postup přiřazení aplikací do skupin](apps-deploy.md)