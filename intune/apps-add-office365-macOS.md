---
title: Instalace Office 365 na zařízení s macOS pomocí Microsoft Intune
titleSuffix: ''
description: Zjistěte, jak můžete využít Microsoft Intune k instalaci aplikací Office 365 na zařízení s macOS.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/28/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2104d35a179c324bda8455f27e090cadbcaf5e8c
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59894814"
---
# <a name="assign-office-365-to-macos-devices-with-microsoft-intune"></a>Přiřazení Office 365 zařízením s macOS v Microsoft Intune

Tento typ aplikace usnadňuje přiřazení aplikací Office 365 2016 zařízením s macOS. Pomocí tohoto typu aplikace nainstalujete Word, Excel, PowerPoint, Outlook a OneNote. Tyto aplikace jsou dodávané prostřednictvím funkce Microsoft AutoUpdate (MAU). Je to kvůli jejich zabezpečení a aktuálnosti. Požadované aplikace se v seznamu aplikací v konzole Intune zobrazí jako jedna aplikace.


## <a name="before-you-start"></a>Než začnete

Než začnete přidávat Office 365 do zařízení s macOS, seznamte se s těmito podrobnostmi:

- Zařízení, na která tyto aplikace budete nasazovat, musí mít macOS 10.10 nebo novější.
- Intune umožňuje přidat jenom aplikace Office, které jsou součástí sady Office 2016 pro Mac.
- Pokud jsou při instalaci sady aplikací službou Intune spuštěné nějaké aplikace Office, můžou uživatelé přijít o data z neuložených souborů.

## <a name="create-and-configure-the-app-suite"></a>Vytvoření a konfigurace sady aplikací

Z podokna **Aplikace** přidejte Office 365.
1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby** > **Monitorování a správa** > **Intune**.
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V podokně úloh **Klientské aplikace** vyberte v části **Spravovat** možnost **Aplikace**. 
5. Vyberte **Přidat**.
6. V seznamu **Typ aplikace** vyberte ve skupině **Sada Office 365** **macOS**.
7. Informace o sadě aplikací získáte vybráním možnosti **Informace o sadě aplikací**.  
    Tyto informace vám pomůžou sadu aplikací identifikovat v Intune a uživatelům ji pomůžou najít na portálu společnosti.
8. Zadejte následující informace:
    - **Název sady**: Zadejte název sady aplikací, který se zobrazí v aplikaci portál společnosti. Názvy všech používaných sad musí být jedinečné. Pokud stejný název sady aplikací existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis sady**: Zadejte popis sady aplikací.
    - **Publisher**: Jako vydavatel se zobrazí Microsoft.
    - **Kategorie**: Vyberte jednu nebo několik předdefinovaných nebo vytvořených kategorií aplikací. Díky tomuto nastavení uživatelé dokážou sadu aplikací při procházení portálu společnosti jednodušeji najít.
    - **Zobrazit tuto aplikaci jako doporučenou aplikaci portálu společnosti**: Vyberte tuto možnost, chcete-li zobrazit sadu aplikací výrazném místě na hlavní stránce portálu společnosti když uživatelé vyhledávají aplikace.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Soukromá adresa URL**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Pro vývojáře**: Jako vývojář se zobrazí Microsoft.
    - **Vlastník**: Jako vlastník se zobrazí Microsoft.
    - **Poznámky k**: Volitelně zadejte jakékoli poznámky, které chcete přidružit k této aplikaci.
    - **Logo**: Logo Office 365 se zobrazí u aplikace, když uživatelé procházejí portál společnosti.
9. Vyberte **OK**.
10. V podokně **Přidat aplikaci** vyberte **Přidat**.  
    Sada se zobrazí v seznamu aplikací jako jedna položka.

## <a name="configure-app-assignments"></a>Konfigurace přiřazení aplikací

V tomto kroku nakonfigurujte, jakým skupinám sadu aplikací přiřadíte. 

1. Vybráním sady aplikací **Office 365** v seznamu aplikací zobrazte podokno přehledu **Office 365**.
2. V podokně **Office 365** vyberte **Přiřazení**.
3. Pokud chcete přidat skupinu, která použije sadu aplikací, vyberte **Přidat skupinu**.  
    Zobrazí se podokno **Přidat skupinu**.
4. **Typ přiřazení** nastavte na **Povinné** nebo **K dispozici**.
5. Přiřaďte sadu vybraným skupinám. Další informace najdete v článku [Přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md).

    >[!Note]
    > Sadu aplikací Office 365 nelze odinstalovat pomocí Intune.

5. V podokně **Přiřadit** vyberte **OK**.
6. V podokně **Přidat skupinu** vyberte **OK**.
7. Přiřazení potvrďte volbou **Uložit**.

## <a name="next-steps"></a>Další postup

- Další informace o přidání aplikací Office 365 do zařízení s Windows 10 najdete v článku [Přiřazení aplikací Office 365 ProPlus 2016 k zařízením s Windows 10 pomocí Microsoft Intune](apps-add-office365.md).
- Informace o zahrnutí a vyloučení přiřazení aplikací ze skupin uživatelů najdete v článku [Zahrnutí a vyloučení přiřazení aplikací](apps-inc-exl-assignments.md).
