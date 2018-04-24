---
title: Přidání webových aplikací do Microsoft Intune
titleSuffix: ''
description: Zjistěte, jak do Microsoft Intune přidat webové aplikace.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45253e061039198aee4aa49b2bf879a1b9929e35
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Přidání webových aplikací do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune podporuje různé typy aplikací, včetně webových. Webová aplikace představuje aplikaci klient-server. Server poskytuje webovou aplikaci, která zahrnuje uživatelské rozhraní, obsah a funkce. Moderní webové hostingové platformy dále běžně nabízejí zabezpečení, vyrovnávání zatížení a další výhody. Webová aplikace se samostatně udržuje na webu. Na tento typ aplikace se odkazuje pomocí Microsoft Intune. Můžete také určit, které skupiny uživatelů mají k této aplikaci přístup. 

Abyste mohli aplikaci spravovat a přiřazovat ji uživatelům, přidejte ji do Intune. Intune vytvoří zástupce webové aplikace na domovské obrazovce uživatelova zařízení.

> [!Note]
> Webové aplikace ale nejsou podporované na zařízeních s Androidem for Work a macOS.

Postup přidání aplikace do Intune v podobě zástupce aplikace na webu:

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Microsoft Intune** vyberte **Mobilní aplikace**.
4. V podokně **Mobilní aplikace** vyberte **Aplikace**.
5. Nad seznamem aplikací vyberte **Přidat**. Zobrazí se podokno **Přidat aplikaci**.
6. V podokně **Přidat aplikaci** vyberte v rozevíracím seznamu **Typ aplikace** typ **Webový odkaz**.
7. Vyberte možnost **Konfigurovat**. Zobrazí se podokno **Informace o aplikaci**.
8. V podokně **Informace o aplikaci** přidejte tyto údaje:
    - **Název** – zadejte název aplikace, který se zobrazí na Portálu společnosti.
    - **Popis** – zadejte popis aplikace. Popis se zobrazí koncovým uživatelům na Portálu společnosti.
    - **Vydavatel** – zadejte název vydavatele této aplikace.
    - **Adresa URL aplikace** – zadejte adresu URL webu hostujícího aplikaci, kterou chcete přiřadit.
    - **Kategorie (volitelné)** – vyberte jednu nebo několik předdefinovaných nebo vytvořených kategorií. Vybraná kategorie pomůže uživatelům najít aplikaci při procházení Portálu společnosti.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **K otevření tohoto odkazu vyžadovat spravovaný prohlížeč** – když uživatelům webu nebo webové aplikace přiřadíte odkaz, mohou ho otevřít v prohlížeči spravovaném v Intune. Tento prohlížeč musí být nainstalovaný na jejich zařízení.
    - **Logo** – nahrajte logo přiřazené aplikaci. Toto logo se zobrazí u aplikace, když uživatelé procházejí Portál společnosti.
9. Až budete hotovi, v podokně **Přidat informace** vyberte **Ok**.
10. Pak v podokně **Přidat aplikaci** vyberte **Přidat**.

> [!Note]
> Uživatelé si musí na domovskou obrazovku přidat widget Intune k zobrazení webových aplikací, které jsou k zařízení s Androidem přiřazené.

## <a name="next-steps"></a>Další kroky

- Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřazovat vybraným skupinám. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).