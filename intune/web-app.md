---
title: "Přidání webových aplikací do Intune"
titleSuffix: Azure portal
description: "Zjistěte, jak do Intune přidat webové aplikace"
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cfa70879a460826d22eb6fab2e0d08603e567d6e
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Přidání webových aplikací do Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Abyste mohli aplikaci spravovat a přiřazovat ji uživatelům, přidejte ji do Intune. Intune podporuje různé typy aplikací, včetně webových.

> [!Note]
> Webové aplikace ale nejsou podporované na zařízeních se systémem Android for Work.

Postup přidání aplikace do Intune v podobě zástupce aplikace na webu:

1. Přihlaste se k portálu Azure Portal.
2. Použijte **Další materiály**, najděte a vyberte **Intune**.
3. V okně **Microsoft Intune** vyberte **Mobilní aplikace**.
4. V okně **Mobilní aplikace** vyberte **Aplikace**.
5. Nad seznamem aplikací vyberte **Přidat**. Zobrazí se okno **Přidat aplikaci**.
6. V okně **Přidat aplikaci** vyberte v rozevíracím seznamu **Typ aplikace** typ **Webová aplikace**.
7. Vyberte možnost **Konfigurovat**. Zobrazí se okno **Informace o aplikaci**.
8. V okně **Informace o aplikaci** přidejte následující údaje:
    - **Název** – zadejte název aplikace, který se zobrazí na Portálu společnosti.
    - **Popis** – zadejte popis aplikace. Popis se zobrazí koncovým uživatelům na Portálu společnosti.
    - **Vydavatel** – zadejte název vydavatele této aplikace.
    - **Adresa URL aplikace** – zadejte adresu URL webu hostujícího aplikaci, kterou chcete přiřadit.
    - **Kategorie (volitelné)** – vyberte jednu nebo několik předdefinovaných nebo vytvořených kategorií. Vybraná kategorie pomůže uživatelům najít aplikaci při procházení Portálu společnosti.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **K otevření tohoto odkazu vyžadovat spravovaný prohlížeč** – když uživatelům webu nebo webové aplikace přiřadíte odkaz, mohou ho otevřít v prohlížeči spravovaném v Intune. Tento prohlížeč musí být nainstalovaný na jejich zařízení.
    - **Logo** – nahrajte logo přiřazené aplikaci. Toto logo se zobrazí u aplikace, když uživatelé procházejí Portál společnosti.
9. Až budete hotovi, v okně **Přidat informace** vyberte **Ok**.
10. Pak v okně **Přidat aplikaci** vyberte **Přidat**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřazovat vybraným skupinám. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).