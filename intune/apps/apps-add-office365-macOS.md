---
title: Instalace Office 365 pro macOS zařízení pomocí Microsoft Intune
titleSuffix: ''
description: Naučte se, jak můžete pomocí Microsoft Intune instalovat aplikace Office 365 na zařízeních s macOS.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 889cacbb56fb390b88c7db9c9516b8b43e4c3770
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940192"
---
# <a name="assign-office-365-to-macos-devices-with-microsoft-intune"></a>Přiřazení Office 365 k macOS zařízením pomocí Microsoft Intune

Tento typ aplikace usnadňuje přiřazení aplikací Office 365 2016 zařízením macOS. Pomocí tohoto typu aplikace můžete nainstalovat Word, Excel, PowerPoint, Outlook a OneNote. K zajištění bezpečnější a aktuálnosti aplikací jsou aplikace dodávány pomocí programu Microsoft AutoUpdate (MAU). Požadované aplikace se v seznamu aplikací v konzole Intune zobrazí jako jedna aplikace.


## <a name="before-you-start"></a>Než začnete

Než začnete přidávat Office 365 do zařízení macOS, pochopte následující podrobnosti:

- Na zařízeních, na která tyto aplikace nasazujete, musí běžet macOS 10,10 nebo novější.
- Intune podporuje přidávání aplikací Office, které jsou zahrnuté v sadě Office 2016 pro Mac.
- Pokud jsou při instalaci sady aplikací Intune otevřené nějaké aplikace Office, můžou uživatelé přijít o data z neuložených souborů.

## <a name="create-and-configure-the-app-suite"></a>Vytvoření a konfigurace sady aplikací

Do podokna **aplikace** přidejte sadu Office 365.
1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** vyberte **klientské aplikace**.
4. V podokně úloh **klientské aplikace** vyberte v části **Spravovat**možnost **aplikace**. 
5. Vyberte **Přidat**.
6. V seznamu **Typ aplikace** vyberte ve skupině sada **Office 365** možnost **MacOS**.
7. Pokud chcete získat informace o sadě aplikací, vyberte **informace o sadě aplikací**.  
    Tyto informace vám pomůžou identifikovat sadu aplikací v Intune a pomáhají uživatelům najít sadu aplikací na portálu společnosti.
8. Zadejte následující informace:
    - **Název sady**: zadejte název sady aplikací, který se zobrazí na portálu společnosti. Ujistěte se, že názvy všech používaných sad jsou jedinečné. Pokud stejný název sady App Suite existuje dvakrát, zobrazí se uživatelům na portálu společnosti jenom jedna z aplikací.
    - **Popis sady**: zadejte popis sady aplikací.
    - **Vydavatel**: jako vydavatel se zobrazí Microsoft.
    - **Kategorie**: vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Toto nastavení usnadňuje uživatelům vyhledání sady aplikací při procházení portálu společnosti.
    - **Zobrazit jako doporučenou aplikaci v portál společnosti**: tuto možnost vyberte, pokud chcete, aby se sada aplikací zobrazovala na hlavní stránce portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL ochrany osobních údajů**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o ochraně osobních údajů pro tuto aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář**: jako vývojář se zobrazí Microsoft.
    - **Vlastník**: jako vlastník se zobrazí Microsoft.
    - **Poznámky**: Volitelně můžete zadat všechny poznámky, které chcete přidružit k této aplikaci.
    - **Logo**: logo Office 365 se zobrazí spolu s aplikací, když uživatelé procházejí portál společnosti.
9. Vyberte **OK**.
10. V podokně **Přidat aplikaci** vyberte **Přidat**.  
    Sada se zobrazí v seznamu aplikací jako jedna položka.

## <a name="configure-app-assignments"></a>Konfigurace přiřazení aplikací

V tomto kroku nakonfigurujte přiřazení pro sadu aplikací. 

1. V seznamu aplikací vyberte sadu aplikací **sady office 365** . zobrazí se podokno přehled **sady Office 365** .
2. V podokně **Office 365** vyberte **přiřazení**.
3. Pokud chcete přidat skupinu, která bude používat sadu aplikací, vyberte **Přidat skupinu**.  
    Zobrazí se podokno **Přidat skupinu** .
4. Nastavte **Typ přiřazení** na **požadováno** nebo **k dispozici**.
5. Přiřaďte sadu vybraným skupinám. Další informace najdete v tématu [přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md).

    >[!Note]
    > Sadu aplikací Office 365 nemůžete odinstalovat přes Intune.

5. V podokně **přiřadit** vyberte **OK**.
6. V podokně **Přidat skupinu** vyberte **OK**.
7. Pokud chcete potvrdit přiřazení, vyberte **Uložit**.

## <a name="next-steps"></a>Další kroky

- Další informace o přidání aplikací Office 365 do zařízení s Windows 10 najdete v článku [přiřazení aplikací office 365 ProPlus 2016 zařízením s Windows 10 pomocí Microsoft Intune](apps-add-office365.md).
- Další informace o zahrnutí a vyloučení přiřazení aplikací ze skupin uživatelů najdete v tématu [zahrnutí a vyloučení přiřazení aplikací](apps-inc-exl-assignments.md).
