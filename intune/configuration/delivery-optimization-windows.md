---
title: Nastavení optimalizace doručování pro Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Nakonfigurujte, jak zařízení s Windows 10 spravovaná pomocí služby Intune využívají optimalizaci doručování. V Intune vytvořte profil konfigurace zařízení pro instalaci aktualizací z Internetu. Přečtěte si taky, jak nahradit existující aktualizační kanály profilem Optimalizace doručení.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: kerimh
ms.openlocfilehash: 4357a3235386d9fd17c1df23004e9bc8ddeb28ca
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730846"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Nastavení Optimalizace doručení v Microsoft Intune

S Intune můžete použít nastavení optimalizace doručování pro zařízení s Windows 10 a snížit tak spotřebu šířky pásma, když tato zařízení stahují aplikace a aktualizace. Optimalizace doručování se konfiguruje jako součást vašich profilů konfigurace zařízení.  

Tento článek popisuje, jak nakonfigurovat nastavení Optimalizace doručení v rámci profilu konfigurace zařízení. Po vytvoření profilu ho přiřadíte nebo nasadíte do zařízení s Windows 10. 

Seznam nastavení Optimalizace doručení, která Intune podporuje, najdete v tématu [nastavení Optimalizace doručení pro Intune](../delivery-optimization-settings.md).  

Další informace o optimalizaci doručení ve Windows 10 najdete v tématu [aktualizace pro optimalizaci doručení](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) v dokumentaci k Windows.  


> [!NOTE]
> **Aktualizace softwaru – aktualizační kanály pro Windows 10** se nahrazují nastavením **Optimalizace doručení** . Existující aktualizační kanály můžete změnit tak, aby používaly nastavení **Optimalizace doručení** . [Přesunout existující aktualizační kanály do Optimalizace doručení](#move-existing-update-rings-to-delivery-optimization) (v tomto článku) 
## <a name="create-the-profile"></a>Vytvoření profilu

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.

3. Zadejte následující vlastnosti:

    - **Název**: Zadejte popisný název nového profilu.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: vyberte platformu:  

        - **Windows 10 a novější**

    - **Typ profilu**: vyberte **Optimalizace doručení**.
    - **Nastavení**: Nakonfigurujte nastavení, která definují, jak se mají aktualizace a aplikace stahovat. Informace o dostupných nastaveních najdete v tématu věnovaném [nastavení optimalizace doručování pro Intune](../delivery-optimization-settings.md).

4. Po dokončení vyberte **OK** > **vytvořit** a uložte provedené změny.

Profil se vytvoří a zobrazí se v seznamu. Dále [Přiřaďte profil](device-profile-assign.md) a [sledujte jeho stav](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Přesunout existující aktualizační kanály do Optimalizace doručení

Nastavení **Optimalizace doručení** nahrazuje **aktualizace softwaru – aktualizační kanály Windows 10**. Vaše existující aktualizační kanály můžete snadno změnit tak, aby používaly nastavení **optimalizace doručování** . Pokud chcete zachovat stejné nastavení při vytváření profilu optimalizace doručování, použijte stejný *režim stahování Optimalizace doručení* a pak nastavte stejné nastavení, jako jste už používali. Můžete ale zvolit překonfigurování nastavení Optimalizace doručení, aby bylo možné využít celé spektrum nastavení, které může profil Optimalizace doručení spravovat.

1. Vytvořit konfigurační profil Optimalizace doručení:

    1. V Intune vyberte **Konfigurace zařízení** > **profily** > **vytvořit profil**.
    2. Zadejte následující vlastnosti:

        - **Název**: Zadejte popisný název nového profilu.
        - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
        - **Platforma**: vyberte **Windows 10 a novější**.
        - **Typ profilu**: vyberte **Optimalizace doručení**.
        - **Nastavení**: **režim stahování pro optimalizaci doručení**vyberte stejný režim, který je používán existujícím kanálem aktualizace softwaru, pokud nechcete změnit nastavení, která se vztahují na vaše zařízení. Možnosti:
            - **Není nakonfigurováno**
            - **Jenom HTTP bez partnerských vztahů**
            - **HTTP se provedlo při vytváření partnerských vztahů za stejným NAT.**
            - **HTTP Blend s partnerským vztahem přes soukromou skupinu**
            - **HTTP Blend s partnerským vztahem na internetu**
            - **Jednoduchý režim stahování bez partnerských vztahů**
            - **Režim obcházení**
    3. Nakonfigurujte všechna další nastavení, která budete chtít spravovat.
1. Přiřaďte tento nový profil ke stejným zařízením a uživatelům jako stávající kanál aktualizace softwaru. [Přiřaďte profil](device-profile-assign.md) seznamu kroků.

3. Odkonfigurujte stávající softwarový kanál:
    1. V Intune navštivte **aktualizace softwaru** > aktualizačních kanálů Windows 10.
    2. V seznamu vyberte aktualizační kanál.
    3. V nastavení nastavte **režim stažení optimalizace doručování** na **Nenakonfigurováno**.
    4. **OK** > **Uložit** změny.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](device-profile-assign.md) a [Sledujte](device-profile-monitor.md) jeho stav.  
Zobrazit [nastavení Optimalizace doručení](../delivery-optimization-settings.md) pro Intune
