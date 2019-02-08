---
title: Přidání webových aplikací do Microsoft Intune
titleSuffix: ''
description: Zjistěte, jak do Microsoft Intune přidat webové aplikace (klient server aplikace).
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0698a6b3010ad2177d4f593bf4d75ea2ff6a31dc
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55839190"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Přidání webových aplikací do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune podporuje různé typy aplikací, včetně webových. Webová aplikace představuje aplikaci klient-server. Server poskytuje webovou aplikaci, která zahrnuje uživatelské rozhraní, obsah a funkce. Moderní webové hostingové platformy dále běžně nabízejí zabezpečení, vyrovnávání zatížení a další výhody. Webová aplikace se samostatně udržuje na webu. Na tento typ aplikace se odkazuje pomocí Microsoft Intune. Můžete také určit, které skupiny uživatelů mají k této aplikaci přístup. 

Abyste mohli aplikaci spravovat a přiřazovat ji uživatelům, přidejte ji do Intune. Intune vytvoří zástupce webové aplikace na domovské obrazovce uživatelova zařízení.

> [!Note]
> Webové aplikace nejsou podporované na zařízeních s pracovním profilem Androidu a macOS.

## <a name="add-a-web-app-to-intune"></a>Přidání webové aplikace do Intune
Pokud chcete přidat aplikaci do Intune v podobě zástupce aplikace na webu, postupujte takto:

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**.  
    Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V podokně úloh **Klientské aplikace** vyberte v části **Spravovat** možnost **Aplikace**.
5. V podokně **Aplikace** vyberte **Přidat**.
6. V podokně **Přidat aplikaci** vyberte v rozevíracím seznamu **Typ aplikace** typ **Webový odkaz**.
7. Vyberte **Konfigurovat**.
8. V podokně **Informace o aplikaci** přidejte tyto údaje:
    - **Název**:  Zadejte název aplikace, jak je zobrazený na portálu společnosti. 
    
        > [!NOTE]
        > Pokud po nasazení a instalaci aplikace změníte název aplikace pomocí Intune na portálu Azure Portal, nebude už možné na tuto aplikaci cílit příkazy.
    
    - **Popis**: Zadejte popis aplikace. Tento popis se uživatelům zobrazí na Portálu společnosti.
    - **Publisher**: Zadejte název vydavatele této aplikace.
    - **Adresa URL aplikace**: Zadejte adresu URL webu hostujícího aplikaci, kterou chcete přiřadit.
    - **Kategorie**: Volitelně vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Uživatelé tak při procházení Portálu společnosti najdou aplikaci snadněji.
    - **Zobrazit tuto aplikaci jako doporučenou aplikaci portálu společnosti**: Vyberte tuto možnost, chcete-li zobrazit sadu aplikací výrazném místě na hlavní stránce portálu společnosti když uživatelé vyhledávají aplikace.
    - **Vyžadovat spravovaný prohlížeč k otevření tohoto odkazu**: Vyberte tuto možnost, chcete-li přiřadit uživatelům odkaz na web nebo webovou aplikaci, která lze otevřít v prohlížeči spravovaném přes Intune. Tento prohlížeč musí být nainstalovaný na jejich zařízení.
    - **Logo**: Nahrajte ikonu, která bude k aplikaci přidružená. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
9. Vyberte **OK**.
10. V podokně **Přidat aplikaci** zvolte **Přidat**.

> [!Note]
> Uživatelé si musí na domovskou obrazovku přidat widget Intune k zobrazení webových aplikací, které jsou k zařízení s Androidem přiřazené.
>
> V současnosti jsou webové aplikace nasazené do zařízení s iOS v Intune přidružené k profilu pro správu, takže nejdou odebrat ručně. Na portálu Intune můžete typ nasazení změnit na **Odinstalovat**. V tom případě můžete webovou aplikaci odebrat automaticky. Pokud byste, ještě než změníte přiřazení aplikace na **Odinstalovat**, odebrali nasazení, zůstane webová aplikace trvale v zařízení, dokud v Intune nezrušíte jeho registraci.

## <a name="next-steps"></a>Další postup

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřazovat vybraným skupinám. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md). 
