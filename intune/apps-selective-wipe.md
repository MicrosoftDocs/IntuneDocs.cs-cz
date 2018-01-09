---
title: "Jak z aplikací vymazat jenom firemní data"
titleSuffix: Azure portal
description: "Přečtěte si, jak selektivně vymazat data z aplikací v Microsoft Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a1c6085ddf07c70eaaf81b6e043b6da35544388
ms.sourcegitcommit: 9fabf1a8db53842f7b00762374de5b137158ee25
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Jak z aplikací spravovaných pomocí Intune vymazat jenom firemní data

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

V případě ztráty nebo odcizení zařízení nebo když zaměstnanec opouští společnost, je vhodné se ujistit, že byla ze zařízení odebraná firemní data. Nemusí ale být vhodné odebrat ze zařízení osobní data, zvlášť jestli je to zařízení, které vlastní zaměstnanec.

>[!NOTE]
> Dvěma platformami, na kterých se v současnosti mazání podnikových dat z aplikací spravovaných v Intune podporuje, jsou iOS a Android.

Pokud chcete selektivně odebrat data firemních aplikací, vytvořte žádost o vymazání pomocí kroků v tomto tématu. Po dokončení žádosti se při příštím spuštění aplikace na zařízení z aplikace odeberou firemní data.

>[!IMPORTANT]
> Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou. Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. V současnosti to platí jen pro aplikaci Microsoft Outlook.

## <a name="create-a-wipe-request"></a>Vytvoření žádosti o vymazání

1.  Přihlaste se k [portálu Azure Portal](https://portal.azure.com).

2.  Zvolte **Další služby**, do textového pole filtru zadejte **Intune** a vyberte **Intune**. Otevře se okno v Intune. Zvolte **Mobilní aplikace**.

    ![Snímek obrazovky s oknem Microsoft Intune](./media/apps-selective-wipe01.png)

3.  V okně **Mobilní aplikace** zvolte **Selektivní vymazání aplikace**.

4.  Zvolte **Nová žádost o vymazání**. Otevře se okno **Nová žádost o vymazání**.

    ![Snímek obrazovky okna Nová žádost o vymazání](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  Vyberte **Uživatel** k otevření okna **Uživatel** a vyberte uživatele, jehož data aplikací chcete vymazat.

6.  Potom v okně **Nová žádost o vymazání** zvolte **Zařízení**. Otevře se okno **Vybrat zařízení** se seznamem všech zařízení přidružených k vybranému uživateli. Jeho součástí jsou dva sloupce: jeden s názvem zařízení, což je popisný název definovaný uživatelem, a jeden s typem zařízení, který označuje jeho platformu. Vyberte zařízení, které chcete vymazat.

7.  Teď jste zpátky v okně **Nová žádost o vymazání**. Pokud chcete vytvořit žádost o vymazání, vyberte **OK**.

Služba vytvoří a sleduje samostatnou žádost o vymazání pro každou chráněnou aplikaci na zařízení a uživatele přidruženého k této žádosti o vymazání.

## <a name="monitor-your-wipe-requests"></a>Monitorování žádostí o vymazání

Můžete získat souhrnnou sestavu, která zobrazuje celkový stav žádostí o vymazání a také počet nevyřízených a neúspěšných žádostí. Další podrobnosti získáte tímto postupem:

1.  V okně **Mobilní aplikace – Selektivní vymazání aplikace** můžete zobrazit seznam žádostí seskupených podle uživatele. Protože systém vytvoří žádost o vymazání pro každou chráněnou aplikaci spuštěnou na zařízení, může být u uživatele více žádostí. Stav označuje, jestli je žádost o vymazání **nevyřízená**, **selhala** nebo byla **úspěšná**.

    ![Snímek obrazovky se stavem žádosti o vymazání v okně Selektivní vymazání aplikace](./media/wipe-request-status-1.png)

Uvidíte také název zařízení a jeho typ, což vám pomůže při orientaci v těchto sestavách.

>[!IMPORTANT]
> Aby k vymazání došlo, musí uživatel otevřít aplikaci. Po zadání požadavku může vymazání samotné trvat až 30 minut.

## <a name="delete-a-wipe-request"></a>Odstranění žádosti o vymazání

Vymazání v čekajícím stavu se zobrazují, dokud je ručně neodstraníte.  Ruční odstranění žádosti o vymazání:

1.  Přejděte do okna **Mobilní aplikace – Selektivní vymazání aplikace**.

2.  V seznamu klikněte pravým tlačítkem na žádost o vymazání, kterou chcete odstranit, a zvolte **Odstranit žádost o vymazání**.

    ![Snímek obrazovky se seznamem žádostí o vymazání v okně Selektivní vymazání aplikace](./media/delete-wipe-request.png)

3.  Zobrazí se výzva k potvrzení odstranění. Zvolte **Ano** nebo **Ne** a klikněte na **OK**.

### <a name="see-also"></a>Viz taky
[Zásady ochrany aplikací](app-protection-policy.md)

[Co je správa aplikací?](app-management.md)
