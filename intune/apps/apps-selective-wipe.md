---
title: Jak z aplikací vymazat jenom firemní data
titleSuffix: Microsoft Intune
description: Learn how to selectively wipe only corporate data from Intune-managed apps with Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0fafe7c17c698a5eb4e5ad6825bee0ae3fe874c2
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199233"
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Jak z aplikací spravovaných pomocí Intune vymazat jenom firemní data

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

V případě ztráty nebo odcizení zařízení nebo když zaměstnanec opouští společnost, je vhodné se ujistit, že byla ze zařízení odebraná firemní data. Nemusí ale být vhodné odebrat ze zařízení osobní data, zvlášť jestli je to zařízení, které vlastní zaměstnanec.

>[!NOTE]
> The iOS, Android, and Windows 10 platforms are the only platforms currently supported for wiping corporate data from Intune managed apps. Intune managed apps are applications that include the Intune APP SDK and have a licensed user account for your organization. Deployment of Application Protection Policies are not required to enable app selective wipe.

Pokud chcete selektivně odebrat data firemních aplikací, vytvořte žádost o vymazání pomocí kroků v tomto tématu. Po dokončení žádosti se při příštím spuštění aplikace na zařízení z aplikace odeberou firemní data. Kromě vytvoření žádosti o vymazání můžete nakonfigurovat selektivní vymazání dat organizace jako novou akci, když nejsou splněny podmínky nastavení přístupu zásad ochrany aplikací. Tato funkce umožňuje automaticky chránit a odebírat citlivá data organizace z aplikací na základě předem nakonfigurovaných kritérií.

>[!IMPORTANT]
> Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou. Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. V současnosti to platí jen pro aplikaci Microsoft Outlook.

## <a name="deployed-wip-policies-without-user-enrollment"></a>Deployed WIP policies without user enrollment
Windows Information Protection (WIP) policies can be deployed without requiring MDM users to enroll their Windows 10 device. Tato konfigurace umožňuje společnostem chránit jejich podnikové dokumenty na základě konfigurace WIP a zároveň umožňuje uživatelům uchovat si správu svých vlastních zařízení s Windows. Jakmile jsou dokumenty chráněny zásadami WIP, mohou být chráněná data selektivně vymazána správcem služby Intune. Výběrem uživatele a zařízení a odesláním žádosti o vymazání se veškerá data chráněná prostřednictvím zásad WIP stanou nepoužitelnými. From the Intune in the Azure portal, select **Client app** > **App selective wipe**. Další informace najdete v článku [Vytvoření a nasazení zásady ochrany aplikací WIP (Windows Information Protection) u Intune](windows-information-protection-policy-create.md).

## <a name="create-a-wipe-request"></a>Vytvoření žádosti o vymazání

1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. In the Intune pane, select **Client apps** > **App selective wipe** > **Create wipe request**.<br>
   The **Create wipe request** pane is displayed.
3. Click **Select the user**, choose the user whose app data you want to wipe, and click **Select** at the bottom of the **User** pane.
4. Click **Select the device**, choose the device, and click **Select** at the bottom of the **Select Device** pane.
5. Click **Create** to make a wipe request.

Služba vytvoří a sleduje samostatnou žádost o vymazání pro každou chráněnou aplikaci na zařízení a uživatele přidruženého k této žádosti o vymazání.

## <a name="monitor-your-wipe-requests"></a>Monitorování žádostí o vymazání

Můžete získat souhrnnou sestavu, která zobrazuje celkový stav žádostí o vymazání a také počet nevyřízených a neúspěšných žádostí. Další podrobnosti získáte tímto postupem:

1. V podokně **Klientské aplikace – Selektivní vymazání aplikace** si můžete prohlédnout seznam žádostí seskupených po uživatelích. Protože systém vytvoří žádost o vymazání pro každou chráněnou aplikaci spuštěnou na zařízení, může být u uživatele více žádostí. Stav označuje, jestli je žádost o vymazání **nevyřízená**, **selhala** nebo byla **úspěšná**.

    ![Snímek obrazovky se stavem žádosti o vymazání v podokně Selektivní vymazání aplikace](./media/apps-selective-wipe/wipe-request-status-1.png)

Uvidíte také název zařízení a jeho typ, což vám pomůže při orientaci v sestavách.

>[!IMPORTANT]
> Aby k vymazání došlo, musí uživatel otevřít aplikaci. Po zadání požadavku může vymazání samotné trvat až 30 minut.

## <a name="delete-a-wipe-request"></a>Odstranění žádosti o vymazání

Vymazání v čekajícím stavu se zobrazují, dokud je ručně neodstraníte. Ruční odstranění žádosti o vymazání:

1. Přejděte do podokna **Klientské aplikace – Selektivní vymazání aplikace**.

2. V seznamu klikněte pravým tlačítkem na žádost o vymazání, kterou chcete odstranit, a zvolte **Odstranit žádost o vymazání**.

    ![Snímek obrazovky se seznamem žádostí o vymazání v podokně Selektivní vymazání aplikace](./media/apps-selective-wipe/delete-wipe-request.png)

3. Zobrazí se výzva k potvrzení odstranění. Zvolte **Ano** nebo **Ne** a klikněte na **OK**.

## <a name="see-also"></a>Související témata
[Zásady ochrany aplikací](app-protection-policy.md)

[Co je správa aplikací?](app-management.md)
