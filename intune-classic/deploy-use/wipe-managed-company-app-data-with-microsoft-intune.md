---
title: Vymazání data spravovaných aplikací společnosti
description: Přečtěte si, jak můžete selektivně odebrat firemní data ze zařízení vzdáleně.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/25/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8d946b551118441b737335f6bd8c4603a49e0dd2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="wipe-company-app-data-with-intune-mam"></a>Vymazání dat firemních aplikací pomocí správy mobilních aplikací Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

V případě ztráty nebo odcizení zařízení nebo když zaměstnanec opouští společnost, je vhodné se ujistit, že byla ze zařízení odebraná firemní data. Nemusí ale být vhodné odebrat ze zařízení osobní data, zvlášť jestli je to zařízení, které vlastní zaměstnanec.

Pokud chcete selektivně odebrat data firemních aplikací, vytvořte žádost o vymazání pomocí kroků v tomto tématu. Po dokončení žádosti se při příštím spuštění aplikace na zařízení z aplikace odeberou firemní data.

>[!IMPORTANT]
> Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou. Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. V současnosti to platí jen pro aplikaci Microsoft Outlook.

## <a name="create-a-wipe-request"></a>Vytvoření žádosti o vymazání

1.  Přihlaste se k [portálu Azure Portal](https://portal.azure.com).

2.  Zvolte **Další služby**, do textového pole filtru zadejte **Intune** a vyberte **Intune App Protection**. Otevře se okno Správa mobilních aplikací Intune.

    ![Snímek obrazovky okna Nová žádost o vymazání](../media/AppManagement/wipe-request-mam-main-blade.png)

2.  V okně **Nastavení** zvolte **Žádosti o vymazání**.

3.  Zvolte **Nová žádost o vymazání**. Otevře se okno **Nová žádost o vymazání**.

    ![Snímek obrazovky okna Nová žádost o vymazání](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

4.  Vyberte **Uživatel** k otevření okna **Uživatel** a vyberte uživatele, jehož data aplikací chcete vymazat.

5.  Vyberte **Zařízení**. Otevře se okno **Zařízení** se seznamem všech zařízení přidružených k vybranému uživateli. Jeho součástí jsou dva sloupce s názvem zařízení, což je popisný název definovaný uživatelem, a s typem zařízení, který označuje jeho platformu. Vyberte zařízení, které chcete vymazat.

6.  Teď jste zpátky v okně **Nová žádost o vymazání**. Pokud chcete vytvořit žádost o vymazání, vyberte **OK**. 

Služba vytvoří a sleduje samostatnou žádost o vymazání pro každou chráněnou aplikaci na zařízení a uživatele přidruženého k této žádosti o vymazání.

>[!NOTE]
> **Žádosti o vymazání** můžete vytvořit také kliknutím na **dlaždici Žádost o vymazání** v okně Správa mobilních aplikací Intune.

## <a name="monitor-your-wipe-requests"></a>Monitorování žádostí o vymazání

Můžete získat souhrnnou sestavu, která zobrazuje celkový stav žádostí o vymazání a také počet nevyřízených a neúspěšných žádostí. Další podrobnosti získáte tímto postupem:

1.  V okně Správa mobilních aplikací Intune klikněte na dlaždici **Žádosti o vymazání**.

2.  V okně **Žádost o vymazání** zvolte dlaždici **Žádost o vymazání** a otevřete okno **Žádost o vymazání**.

3.  V okně **Žádost o vymazání** můžete zobrazit seznam žádostí seskupených podle uživatele. Protože systém vytvoří žádost o vymazání pro každou chráněnou aplikaci spuštěnou na zařízení, může být u uživatele více žádostí. Stav označuje, jestli je žádost o vymazání **nevyřízená**, **selhala** nebo byla **úspěšná**.

    ![Snímek obrazovky okna Nová žádost o vymazání](../media/AppManagement/wipe-request-status-1.png)

Uvidíte také název zařízení a jeho typ, což vám pomůže při orientaci v těchto sestavách.

>[!IMPORTANT]
> Aby k vymazání došlo, musí uživatel otevřít aplikaci. Po zadání požadavku může vymazání samotné trvat až 30 minut.

## <a name="delete-a-wipe-request"></a>Odstranění žádosti o vymazání

Vymazání v čekajícím stavu se zobrazují, dokud je ručně neodstraníte.  Ruční odstranění žádosti o vymazání

1.  V okně Správa mobilních aplikací Intune klikněte na dlaždici **Žádosti o vymazání**.

2.  V okně **Žádost o vymazání** zvolte dlaždici **Žádost o vymazání** a otevřete okno **Žádost o vymazání**.

3.  Klikněte pravým tlačítkem na žádost o vymazání, kterou chcete odstranit, a zvolte **Odstranit žádost o vymazání**.

    ![Snímek obrazovky okna Nová žádost o vymazání](../media/AppManagement/delete-wipe-request.png)

4.  Zobrazí se výzva k potvrzení odstranění. Zvolte **Ano** nebo **Ne** a klikněte na **OK**.


### <a name="see-also"></a>Viz taky
[Ochrana dat aplikací pomocí zásad správy mobilních aplikací](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Použití portálu Azure Portal](azure-portal-for-microsoft-intune-mam-policies.md)
