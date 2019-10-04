---
title: Jak z aplikací vymazat jenom firemní data
titleSuffix: Microsoft Intune
description: Naučte se, jak selektivně vymazat jenom firemní data z aplikací spravovaných přes Intune pomocí Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 50ea427f1365285e08b6ad0e5a098b67421f941f
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940274"
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Jak z aplikací spravovaných pomocí Intune vymazat jenom firemní data

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Když dojde ke ztrátě nebo odcizení zařízení nebo pokud zaměstnanec odejde z vaší společnosti, chcete zajistit, aby ze zařízení byla odebrána data z firemních aplikací. Ale možná nebudete chtít z tohoto zařízení odebrat osobní údaje, zejména pokud je to zařízení vlastněné zaměstnancem.

>[!NOTE]
> Platformy iOS, Android a Windows 10 jsou jediné platformy, které jsou aktuálně podporované pro mazání podnikových dat ze spravovaných aplikací Intune. Spravované aplikace Intune jsou aplikace, které obsahují sadu Intune APP SDK a mají licencovaný uživatelský účet pro vaši organizaci. Nasazení zásad ochrany aplikací není nutné k povolení selektivního vymazání aplikace.

Pokud chcete selektivně odebrat data firemních aplikací, vytvořte žádost o vymazání pomocí kroků v tomto tématu. Až se žádost dokončí, při příštím spuštění aplikace na zařízení se firemní data z aplikace odeberou. Kromě vytvoření žádosti o vymazání můžete nakonfigurovat selektivní vymazání dat vaší organizace jako novou akci, pokud nejsou splněné podmínky nastavení přístupu k zásadám ochrany aplikací (APP). Tato funkce vám pomůže automaticky chránit a odebírat citlivá firemní data z aplikací na základě předem nakonfigurovaných kritérií.

>[!IMPORTANT]
> Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou. Kontakty synchronizované z nativního adresáře do jiného externího zdroje není možné vymazat. V současné době platí pouze pro aplikaci Microsoft Outlook.

## <a name="deployed-wip-policies-without-user-enrollment"></a>Nasazené zásady nedokončené výroby bez registrace uživatele
Zásady Windows Information Protection (NV) se dají nasadit, aniž by uživatelé MDM museli zaregistrovat svoje zařízení s Windows 10. Tato konfigurace umožňuje společnostem chránit své firemní dokumenty na základě konfigurace nedokončené výroby a zároveň umožňuje uživatelům spravovat správu vlastních zařízení s Windows. Po ochraně dokumentů pomocí zásad nedokončené výroby může být chráněná data selektivně smazána správcem služby Intune. Když vyberete uživatele a zařízení a odešlete žádost o vymazání, všechna data, která byla chráněná prostřednictvím zásad nedokončené výroby, se stanou nepoužitelná. Z Intune v Azure Portal vyberte **klientská aplikace** > **selektivní vymazání aplikace**. Další informace najdete v tématu [Vytvoření a nasazení zásad ochrany aplikací Windows Information Protection (NV) v Intune](windows-information-protection-policy-create.md).

## <a name="create-a-wipe-request"></a>Vytvoření žádosti o vymazání

1. Přihlaste se k [Azure Portal](https://portal.azure.com).

2. Zvolte **všechny služby**, do textového pole filtru zadejte **Intune** a vyberte **Intune**. Otevře se podokno Intune a vyberte podokno **klientské aplikace** .

    ![Snímek obrazovky s podoknem Microsoft Intune](./media/apps-selective-wipe/apps-selective-wipe01.png)

3. V **podokně klientské aplikace**vyberte **selektivní vymazání aplikace**.

4. Vyberte **nový požadavek na vymazání**. Otevře se podokno **Nová žádost o vymazání** .

    ![Snímek obrazovky s podoknem nové žádosti o vymazání](./media/apps-selective-wipe/AzurePortal_MAM_NewWipeRequest.png)

5. Zvolte uživatele a pak zvolte **Vybrat** a vyberte uživatele, jehož data aplikací chcete vymazat.

6. Potom v podokně **Nová žádost o vymazání** vyberte **zařízení** . Tím se otevře podokno **Vybrat zařízení** se seznamem všech zařízení přidružených k vybranému uživateli a zároveň se zobrazí dva sloupce, název zařízení, což je popisný název definovaný uživatelem, a typ zařízení, platforma zařízení. Vyberte zařízení, které chcete vymazat.

7. Nyní jste zpátky v podokně **Nová žádost o vymazání** . Kliknutím na **tlačítko OK** vytvořte žádost o vymazání.

Služba vytvoří a sleduje samostatnou žádost o vymazání pro každou chráněnou aplikaci na zařízení a uživatele přidruženého k žádosti o vymazání.

## <a name="monitor-your-wipe-requests"></a>Monitorování žádostí o vymazání

Můžete mít souhrnnou sestavu, která zobrazuje celkový stav žádosti o vymazání a zahrnuje počet nevyřízených žádostí a selhání. Další podrobnosti získáte pomocí následujících kroků:

1. V podokně **klientské aplikace – selektivní vymazání aplikace** můžete zobrazit seznam žádostí seskupených podle uživatelů. Vzhledem k tomu, že systém vytvoří žádost o vymazání pro každou chráněnou aplikaci spuštěnou na zařízení, může se zobrazit více požadavků pro uživatele. Stav označuje, zda je žádost o vymazání **čeká na vyřízení**, **selhala**nebo **byla úspěšná**.

    ![Snímek obrazovky se stavem žádosti o vymazání v podokně selektivní vymazání aplikace](./media/apps-selective-wipe/wipe-request-status-1.png)

Kromě toho se můžete podívat na název zařízení a jeho typ zařízení, což může být užitečné při čtení sestav.

>[!IMPORTANT]
> Uživatel musí aplikaci otevřít, aby vymazala, a vymazání může trvat až 30 minut od provedení žádosti.

## <a name="delete-a-wipe-request"></a>Odstranění žádosti o vymazání

Vymazání se stavem čekání se zobrazí, dokud je ručně neodstraníte. Ruční odstranění žádosti o vymazání:

1. V podokně **klientské aplikace – selektivní vymazání aplikace** .

2. V seznamu klikněte pravým tlačítkem na žádost o vymazání, kterou chcete odstranit, a zvolte **odstranit žádost o vymazání**.

    ![Snímek obrazovky se seznamem žádostí o vymazání v podokně selektivní vymazání aplikace](./media/apps-selective-wipe/delete-wipe-request.png)

3. Zobrazí se výzva k potvrzení odstranění, zvolte **Ano** nebo **ne**a pak klikněte na **OK**.

## <a name="see-also"></a>Viz také:
[Co jsou zásady ochrany aplikací](app-protection-policy.md)

[Co je Správa aplikací](app-management.md)
