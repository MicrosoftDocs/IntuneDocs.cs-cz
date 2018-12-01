---
title: Nastavení optimalizace doručení pro Windows 10 v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Konfigurujte způsob doručování aktualizací softwaru do zařízení s Windows 10 a novější zařízení využívají cloudové služby optimalizace doručení k dispozici. V Intune vytvořte profil konfigurace zařízení k instalaci aktualizace z Internetu. Také zjistit, jak nahradit existující aktualizačních kanálů s profilem optimalizace doručení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36cfb5ac05b2d69b5c7349f4ebc6054848a08fc8
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/01/2018
ms.locfileid: "52730105"
---
# <a name="windows-10-and-newer-delivery-optimization-settings-in-microsoft-intune"></a>Nastavení optimalizace doručení 10 (a novějších) systému Windows v Microsoft Intune

Tento článek uvádí a popisuje všechny nastavení optimalizace doručení, která můžete konfigurovat pro zařízení s Windows 10. Tato nastavení jsou přidány do konfiguračního profilu zařízení a potom přiřazené nebo nasazené do zařízení pomocí Microsoft Intune.

## <a name="settings"></a>Nastavení

**Režim stahování pro optimalizaci doručení**: Zvolte způsob doručování aktualizací do zařízení. Možnosti:

- **Není nakonfigurováno**: koncoví uživatelé aktualizovat svá zařízení pomocí vlastní metody, které lze použít **aktualizací Windows** nebo **optimalizace doručení** nastavení k dispozici s operačním systémem.
- **Jen HTTP bez partnerů**: aktualizace pouze z Internetu. Není aktualizován z jiných počítačů v síti (označované jako partnerského vztahu nebo peer-to-peer).
- **HTTP v kombinaci s partnery za stejné NAT HTTP v kombinaci s partnery v privátní skupině**: aktualizace z Internetu a z jiných počítačů v síti. Partnerský vztah dochází na zařízeních ve stejné lokality služby Active Directory (pokud existuje) nebo stejné domény. Pokud je vybraná tato možnost, partnerský vztah překročí překlad síťových adres (NAT) IP adresy.
- **HTTP v kombinaci s internetovými partnery**: aktualizace z Internetu a z jiných počítačů v síti.
- **Jednoduchý režim stahování bez partnerů**: získá aktualizace z Internetu, přímo z aktualizace vlastníka, jako je Microsoft. Nekontaktuje cloudové služby pro optimalizaci doručení.
- **Režim vynechání**: použití přenosu na pozadí Intelligent Service (BITS) má být aktualizován. Nepoužívejte optimalizace doručení.

## <a name="move-from-existing-update-rings-to-delivery-optimization"></a>Přesunout z existující aktualizační okruhy optimalizace doručení

**Aktualizace softwaru – aktualizační kanály Windows 10** nahrazují **optimalizace doručení** nastavení. Existující aktualizační okruhy můžete snadno změnit používat **optimalizace doručení** nastavení. Pomocí následujících kroků:

1. Vytvořte profil konfigurace optimalizace doručení:

    1. V Intune, vyberte **konfigurace zařízení** > **profily** > **vytvořit profil**.
    2. Zadejte **název** a **popis** profilu.
    3. Pro **platformy**, zvolte **Windows 10 a novější**. Pro **typ profilu**, zvolte **optimalizace doručení**.
    4. Vyberte **Nastavení**. Pro **režim stahování pro optimalizaci doručení**, vyberte stejný režim používá existující aktualizační kanál softwaru. Možnosti:
        - **Není nakonfigurováno**
        - **Jen HTTP bez partnerů**
        - **HTTP v kombinaci s partnery za stejným NAT HTTP v kombinaci s partnery v privátní skupině**
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