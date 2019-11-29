---
title: Přidání webových aplikací do Microsoft Intune
titleSuffix: ''
description: Přečtěte si, jak přidat webové aplikace (aplikace klient-server) do Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 514977be976c83f5cd8dcb8d56ab5c232ff0d193
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/27/2019
ms.locfileid: "74562483"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Přidání webových aplikací do Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune podporuje různé typy aplikací, včetně webových. Webová aplikace představuje aplikaci klient-server. Server poskytuje webovou aplikaci, která zahrnuje uživatelské rozhraní, obsah a funkce. Moderní webové hostingové platformy dále běžně nabízejí zabezpečení, vyrovnávání zatížení a další výhody. Webová aplikace se samostatně udržuje na webu. Na tento typ aplikace se odkazuje pomocí Microsoft Intune. Můžete také určit, které skupiny uživatelů mají k této aplikaci přístup. 

Abyste mohli aplikaci spravovat a přiřazovat ji uživatelům, přidejte ji do Intune. 

Intune vytvoří zástupce webové aplikace na zařízení uživatele. V případě zařízení se systémem iOS se na domovskou obrazovku přidá zástupce webové aplikace. V případě zařízení se systémem Android se zástupce webové aplikace přidá do widgetu portálu společnosti Intune a pomůcka musí být připnuté ručně uživatelem. V případě zařízení s Windows je zástupce webové aplikace umístěný v nabídce Start.

> [!Note]
> Aby bylo možné spouštět webové aplikace, musí být na zařízení uživatele nainstalován prohlížeč. 

## <a name="add-a-web-app-to-intune"></a>Přidání webové aplikace do Intune
Pokud chcete přidat aplikaci do Intune v podobě zástupce aplikace na webu, postupujte takto:

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **aplikace** > **všechny aplikace** > **Přidat**.
3. V podokně **Přidat aplikaci** vyberte v rozevíracím seznamu **Typ aplikace** typ **Webový odkaz**.
4. Vyberte **Konfigurovat**.
5. V podokně **Informace o aplikaci** přidejte tyto údaje:
    - **Název**: Zadejte název aplikace, který se zobrazí na Portálu společnosti. 

        > [!NOTE]
        > Pokud po nasazení a instalaci aplikace změníte název aplikace pomocí Intune na portálu Azure Portal, nebude už možné na tuto aplikaci cílit příkazy.

    - **Popis**: Zadejte popis aplikace. Tento popis se uživatelům zobrazí na Portálu společnosti.
    - **Vydavatel**: Zadejte název vydavatele této aplikace.
    - **Adresa URL aplikace**: Zadejte adresu URL webu hostujícího aplikaci, kterou chcete přiřadit.
    - **Kategorie**: Volitelně můžete vybrat jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Uživatelé tak při procházení Portálu společnosti najdou aplikaci snadněji.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci:** Vybráním této možnosti se sada aplikací zobrazí uživatelům, kteří hledají aplikace, na výrazném místě na hlavní stránce Portálu společnosti.
    - **K otevření tohoto odkazu vyžadovat spravovaný prohlížeč**: Tuto možnost vyberte, pokud chcete uživatelům webu nebo webové aplikace přiřadit odkaz, který mohou otevřít v prohlížeči spravovaném v Intune. Tento prohlížeč musí být nainstalovaný na jejich zařízení.
    - **Logo**: Nahrajte ikonu, která se přidruží k aplikaci. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
6. Vyberte **OK**.
7. V podokně **Přidat aplikaci** zvolte **Přidat**.

> [!Note]
> Uživatelé si musí na domovskou obrazovku přidat widget Intune k zobrazení webových aplikací, které jsou k zařízení s Androidem přiřazené.
>
> V současnosti jsou webové aplikace nasazené do zařízení s iOS v Intune přidružené k profilu pro správu, takže nejdou odebrat ručně. Na portálu Intune můžete typ nasazení změnit na **Odinstalovat**. V tom případě můžete webovou aplikaci odebrat automaticky. Pokud byste, ještě než změníte přiřazení aplikace na **Odinstalovat**, odebrali nasazení, zůstane webová aplikace trvale v zařízení, dokud v Intune nezrušíte jeho registraci.

Koncoví uživatelé mohou spouštět webové aplikace přímo z aplikace Portál společnosti Windows výběrem webové aplikace a výběrem možnosti **otevřít v prohlížeči**. Publikovaná webová adresa URL se otevře přímo ve webovém prohlížeči. 

## <a name="next-steps"></a>Další kroky

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřazovat vybraným skupinám. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md). 
