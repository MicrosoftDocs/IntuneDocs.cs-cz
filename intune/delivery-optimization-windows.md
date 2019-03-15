---
title: Nastavení optimalizace doručení pro Windows 10 v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Nakonfigurujte, jak zařízení s Windows 10, která spravujete přes Intune používat optimalizace doručení. V Intune vytvořte profil konfigurace zařízení k instalaci aktualizace z Internetu. Také zjistit, jak nahradit existující aktualizačních kanálů s profilem optimalizace doručení.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/12/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: kerimh
ms.openlocfilehash: 45d91766b3bbdcdd3528afd80d74a56a94e88a2c
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57399043"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Nastavení optimalizace doručení v Microsoft Intune

Nastavení optimalizace doručení pro zařízení s Windows 10 v Intune, slouží ke snížení využití šířky pásma, když tato zařízení stahovat aplikace a aktualizace. Optimalizace doručení je nakonfigurovaný jako součást vašich profilů konfigurace zařízení.  

Tento článek popisuje, jak nakonfigurovat nastavení optimalizace doručení jako součást profilu konfigurace zařízení. Až profil vytvoříte, můžete pak přiřadit nebo nasadit tento profil k zařízení s Windows 10. 

Seznam nastavení optimalizace doručení, které Intune podporuje, najdete v části [nastavení optimalizace doručení pro Intune](delivery-optimization-settings.md).  

Další informace o optimalizace doručení ve Windows 10 najdete v tématu [optimalizace doručení aktualizací](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) v dokumentaci k Windows.  


> [!NOTE]
> **Aktualizace softwaru – aktualizační kanály Windows 10** nahrazují **optimalizace doručení** nastavení. Použít lze změnit existující aktualizační okruhy **optimalizace doručení** nastavení. [Přesunout existující aktualizační okruhy optimalizace doručení](#move-existing-update-rings-to-delivery-optimization) (v tomto článku) 
## <a name="create-the-profile"></a>Vytvoření profilu

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.

2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.

3. Zadejte tyto vlastnosti:

    - **Název**: Zadejte popisný název pro nový profil.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Vyberte platformu:  

        - **Windows 10 a novější**

    - **Typ profilu**: Vyberte **optimalizace doručení**.
    - **Nastavení**: Nakonfigurujte nastavení, které definují, jak chcete, aktualizace a aplikace ke stažení. Informace o dostupných nastaveních najdete v tématu [nastavení optimalizace doručení pro Intune](delivery-optimization-settings.md).

4. Až budete hotovi, vyberte **OK** > **vytvořit** uložte provedené změny.

Profil se vytvoří a zobrazí v seznamu. Dále [přiřadit profil](device-profile-assign.md) a potom [monitorování jejího stavu](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Přesunout existující aktualizační okruhy optimalizace doručení

**Optimalizace doručení** nastavení nahrazení **aktualizace softwaru – aktualizační kanály Windows 10**. Existující aktualizační okruhy můžete snadno změnit používat **optimalizace doručení** nastavení. Pokud chcete zachovat stejné nastavení při vytváření profilu optimalizace doručení, použijte stejný *režim stahování pro optimalizaci doručení* a nastavte stejné nastavení jako vy už používá. Můžete však změnit konfiguraci nastavení optimalizace doručení, abyste mohli využívat celou škálu přidání nastavení, které můžete spravovat profil optimalizace doručení.

1. Vytvořte profil konfigurace optimalizace doručení:

    1. V Intune, vyberte **konfigurace zařízení** > **profily** > **vytvořit profil**.
    2. Zadejte tyto vlastnosti:

        - **Název**: Zadejte popisný název pro nový profil.
        - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
        - **Platforma**: Vyberte **Windows 10 a novější**.
        - **Typ profilu**: Vyberte **optimalizace doručení**.
        - **Nastavení**: Pro **režim stahování pro optimalizaci doručení**, vyberte stejný režim, který je používán existující aktualizační kanál software, pokud chcete změnit nastavení platí pro vaše zařízení. Možnosti:
            - **Není nakonfigurováno**
            - **Jen HTTP bez partnerů**
            - **HTTP v kombinaci s partnery za stejným překladem NAT**
            - **HTTP v kombinaci s partnery v privátní skupině**
            - **HTTP v kombinaci s internetovými partnery**
            - **Jednoduchý režim stahování bez partnerů**
            - **Režim vynechání**
    3. Nakonfigurujte veškerá další nastavení, které chcete spravovat.
1. Tento nový profil přiřadíte ke stejné zařízení a uživatele jako existující software aktualizační kanál. [Přiřaďte profil](device-profile-assign.md) jsou uvedené kroky.

3. Zrušit konfiguraci stávající aktualizační kanál, který software:
    1. V Intune, přejděte na **aktualizace softwaru** > aktualizační kanály Windows 10.
    2. V seznamu vyberte aktualizační kanál.
    3. V nastavení, nastavte **režim stahování pro optimalizaci doručení** k **Nenakonfigurováno**.
    4. **OK** > **Uložit** provedené změny.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md) její stav.  
Zobrazení [nastavení optimalizace doručení](delivery-optimization-settings.md) pro Intune.
