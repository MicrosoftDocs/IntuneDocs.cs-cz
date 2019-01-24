---
title: Nastavení optimalizace doručení pro Windows 10 v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Konfigurujte způsob doručování aktualizací softwaru do zařízení s Windows 10 a novější zařízení využívají cloudové služby optimalizace doručení k dispozici. V Intune vytvořte profil konfigurace zařízení k instalaci aktualizace z Internetu. Také zjistit, jak nahradit existující aktualizačních kanálů s profilem optimalizace doručení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a59cab5f709897e064b315193b292cb46dc2f2e
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831543"
---
# <a name="windows-10-and-newer-delivery-optimization-settings-in-microsoft-intune"></a>Nastavení optimalizace doručení 10 (a novějších) systému Windows v Microsoft Intune

> [!NOTE]
> **Aktualizace softwaru – aktualizační kanály Windows 10** nahrazují **optimalizace doručení** nastavení. Použít lze změnit existující aktualizační okruhy **optimalizace doručení** nastavení. [Přesunout existující aktualizační okruhy optimalizace doručení](#move-existing-update-rings-to-delivery-optimization) (v tomto článku) jsou uvedené kroky. 


Tato funkce platí pro následující platformy:

- Windows 10 a novější

Tento článek uvádí a popisuje všechny nastavení optimalizace doručení, která můžete konfigurovat pro zařízení s Windows 10. Tato nastavení jsou přidány do konfiguračního profilu zařízení a potom přiřazené nebo nasazené do zařízení pomocí Microsoft Intune.

[Optimalizace doručení aktualizací](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) je skvělý prostředek pro další informace o optimalizace doručení ve Windows 10.

## <a name="create-the-profile"></a>Vytvoření profilu

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.

2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.

3. Zadejte tyto vlastnosti:

    - **Název**: Zadejte popisný název pro nový profil.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Vyberte platformu:  

        - **Windows 10 a novější**

    - **Typ profilu**: Vyberte **optimalizace doručení**.
    - **Nastavení**: Zvolte, jak chcete aktualizace stáhnout. Možnosti: 

        - **Není nakonfigurováno**: Koncoví uživatelé aktualizovat svá zařízení pomocí vlastní metody, které lze použít **aktualizací Windows** nebo **optimalizace doručení** nastavení k dispozici s operačním systémem.
        - **Jen HTTP bez partnerů**: Získáte aktualizace pouze z Internetu. Není aktualizován z jiných počítačů v síti (označované jako partnerského vztahu nebo peer-to-peer).
        - **HTTP v kombinaci s partnery za stejným překladem NAT**: Získejte aktualizace z Internetu a z jiných počítačů v síti. 
        - **HTTP v kombinaci s partnery v privátní skupině**: Partnerský vztah dochází na zařízeních ve stejné lokality služby Active Directory (pokud existuje) nebo stejné domény. Pokud je vybraná tato možnost, partnerský vztah překročí překlad síťových adres (NAT) IP adresy.
        - **HTTP v kombinaci s internetovými partnery**: Získejte aktualizace z Internetu a z jiných počítačů v síti.
        - **Jednoduchý režim stahování bez partnerů**: Získá aktualizace z Internetu, přímo z aktualizace vlastníka, jako je Microsoft. Nekontaktuje cloudové služby pro optimalizaci doručení.
        - **Režim vynechání**: Pokud chcete získat aktualizace pomocí služby inteligentního přenosu na pozadí (BITS). Nepoužívejte optimalizace doručení.

4. Až budete hotovi, vyberte **OK** > **vytvořit** uložte provedené změny.

Profil se vytvoří a zobrazí v seznamu. Dále [přiřadit profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Přesunout existující aktualizační okruhy optimalizace doručení

**Aktualizace softwaru – aktualizační kanály Windows 10** nahrazují **optimalizace doručení** nastavení. Existující aktualizační okruhy můžete snadno změnit používat **optimalizace doručení** nastavení. Pomocí následujících kroků:

1. Vytvořte profil konfigurace optimalizace doručení:

    1. V Intune, vyberte **konfigurace zařízení** > **profily** > **vytvořit profil**.
    2. Zadejte tyto vlastnosti:

        - **Název**: Zadejte popisný název pro nový profil.
        - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
        - **Platforma**: Vyberte **Windows 10 a novější**.
        - **Typ profilu**: Vyberte **optimalizace doručení**.
        - **Nastavení**: Pro **režim stahování pro optimalizaci doručení**, vyberte stejný režim používá existující aktualizační kanál softwaru. Možnosti:
            - **Není nakonfigurováno**
            - **Jen HTTP bez partnerů**
            - **HTTP v kombinaci s partnery za stejným překladem NAT**
            - **HTTP v kombinaci s partnery v privátní skupině**
            - **HTTP v kombinaci s internetovými partnery**
            - **Jednoduchý režim stahování bez partnerů**
            - **Režim vynechání**

2. Tento nový profil přiřadíte ke stejné zařízení a uživatele jako existující software aktualizační kanál. [Přiřaďte profil](device-profile-assign.md) jsou uvedené kroky.

3. Zrušit konfiguraci stávající aktualizační kanál, který software:
    1. V Intune, přejděte na **aktualizace softwaru** > aktualizační kanály Windows 10.
    2. V seznamu vyberte aktualizační kanál.
    3. V nastavení, nastavte **režim stahování pro optimalizaci doručení** k **Nenakonfigurováno**.
    4. **OK** > **Uložit** provedené změny.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md) její stav.
