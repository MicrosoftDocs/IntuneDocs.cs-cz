---
title: Přidat webové aplikace do Microsoft Intune
titleSuffix: ''
description: Přečtěte si, jak přidat webové aplikace (aplikace klient-server) do Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a8beb8291ede1bf2fde32014fadf9f8cd52da5b6
ms.sourcegitcommit: fc356fd69beaeb3d69982b47e2bdffb6f7127f8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/03/2019
ms.locfileid: "71830575"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Přidat webové aplikace do Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune podporuje různé typy aplikací, včetně webových aplikací. Webová aplikace je aplikace typu klient-server. Server poskytuje webovou aplikaci, která zahrnuje uživatelské rozhraní, obsah a funkce. Kromě toho moderní webové platformy pro hostování běžně nabízejí zabezpečení, Vyrovnávání zatížení a další výhody. Webová aplikace se samostatně udržuje na webu. Použijete Microsoft Intune k ukázání na tento typ aplikace. Přiřadíte také skupiny uživatelů, kteří mají přístup k této aplikaci. 

Než budete moct spravovat a přiřazovat aplikaci pro vaše uživatele, přidejte aplikaci do Intune. Intune vytvoří zástupce webové aplikace na domovské obrazovce zařízení uživatele.

> [!Note]
> Na zařízeních s pracovním profilem Androidu se webové aplikace nepodporují. Aby bylo možné spouštět webové aplikace, musí být na zařízení uživatele nainstalován prohlížeč.

## <a name="add-a-web-app-to-intune"></a>Přidání webové aplikace do Intune
Pokud chcete přidat aplikaci do Intune jako zástupce aplikace na webu, udělejte toto:

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** vyberte **klientské aplikace**.
4. V podokně úloh **klientské aplikace** vyberte v části **Spravovat**možnost **aplikace**.
5. V podokně **aplikace** vyberte **Přidat**.
6. V podokně **Přidat aplikaci** vyberte v rozevíracím seznamu **Typ aplikace** typ **webového odkazu** .
7. Vyberte **Konfigurovat**.
8. V podokně **informace o aplikaci** přidejte následující informace:
    - **Název**: zadejte název aplikace, který se zobrazí na portálu společnosti. 

        > [!NOTE]
        > Pokud po nasazení a instalaci aplikace změníte název aplikace pomocí portálu Intune Azure Portal, aplikace už nebude moct cílit na příkazy.

    - **Popis**: zadejte popis aplikace. Tento popis se zobrazí uživatelům na portálu společnosti.
    - **Vydavatel**: zadejte název vydavatele této aplikace.
    - **Adresa URL aplikace**: zadejte adresu URL webu, který hostuje aplikaci, kterou chcete přiřadit.
    - **Kategorie**: volitelně vyberte jednu nebo více předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Díky tomu můžou uživatelé aplikaci při procházení portálu společnosti snadněji najít.
    - **Zobrazit jako doporučenou aplikaci v portál společnosti**: tuto možnost vyberte, pokud chcete, aby se sada aplikací zobrazovala na hlavní stránce portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Pro otevření tohoto odkazu vyžadovat spravovaný prohlížeč**: tuto možnost vyberte, pokud chcete uživatelům přiřadit odkaz na web nebo webovou aplikaci, kterou můžou otevřít v prohlížeči spravovaném přes Intune. Tento prohlížeč musí být nainstalovaný na svém zařízení.
    - **Logo**: Nahrajte ikonu, která bude přidružená k aplikaci. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
9. Vyberte **OK**.
10. V podokně **Přidat aplikaci** vyberte **Přidat**.

> [!Note]
> Uživatelé musí přidat widget Intune na svou domovskou obrazovku a zobrazit tak webové aplikace, které jsou přiřazené k zařízením s Androidem.
>
> V současné době je nasazení webových aplikací Intune do zařízení se systémem iOS přidruženo k profilu správy a nelze je odebrat ručně. Typ nasazení můžete změnit na **odinstalovat** na portálu Intune, ve kterém se dá webová aplikace odebrat automaticky. Pokud ale odeberete nasazení před změnou záměru přiřazení aplikace k **Odinstalování**, bude webová aplikace na zařízení trvale na svém místě, dokud nebude zařízení neregistrované v Intune.

## <a name="next-steps"></a>Další kroky

Aplikace, kterou jste vytvořili, se zobrazí v seznamu aplikací, kde ji můžete přiřadit ke skupinám, které vyberete. Nápovědu najdete v článku [přiřazení aplikací do skupin](apps-deploy.md). 
