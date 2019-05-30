---
title: Vytvoření profilu zařízení se systémem iOS nebo macOS pomocí Microsoft Intune – Azure | Microsoft Docs
description: Přidejte nebo vytvořte profil zařízení s Iosem nebo macOS a pak nakonfigurujte nastavení pro AirPrint, rozložení domovské obrazovky, oznámení aplikací, sdílené zařízení, jednotné přihlašování a nastavení filtru webového obsahu v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1a5c85c936e49c277b54b542f372f97b247d6a37
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66373806"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Přidání nastavení funkcí zařízení se systémem iOS nebo macOS v Intune

Intune obsahuje mnoho funkcí a nastavení, které pomáhají správcům řídit zařízení s Iosem a macOS. Například správci můžou:

- Povolit uživatelům přístup k tiskárnám ve vaší síti
- Přidejte aplikace a složky na domovskou obrazovku, včetně přidání nové stránky
- Zvolte, jestli a jakým způsobem se zobrazí oznámení aplikace
- Konfigurace zamykací obrazovce zobrazit zprávu nebo inventární štítek, zejména pro sdílená zařízení
- Uživatelům zabezpečené prostředí s jednotným přihlašování sdílet přihlašovací údaje mezi aplikacemi
- Filtrovat webové servery, které používají jazyk pro dospělé a povolit nebo blokovat konkrétní webové stránky

Tyto funkce jsou dostupné v Intune a jsou konfigurovatelné správcem. Intune používá "konfiguračních profily" vytvořit a přizpůsobit nastavení pro potřeby vaší organizace. Po přidání těchto funkcí v profilu, můžete pak push nebo nasadit profil pro zařízení s Iosem a macOS ve vaší organizaci.

V tomto článku se dozvíte, jak vytvořit profil konfigurace zařízení. Můžete také zobrazit všechna nastavení, které jsou k dispozici pro [iOS](ios-device-features-settings.md) a [macOS](macos-device-features-settings.md) zařízení.

## <a name="create-a-device-profile"></a>Vytvoření profilu zařízení

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

    - **Název**: Zadejte popisný název pro nový profil.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Vyberte vaši platformu:
        - **iOS**
        - **macOS**
    - **Typ profilu**: Vyberte **funkcí na zařízeních**.
    - **Nastavení**: Zadejte nastavení, které chcete konfigurovat. Seznam všech nastavení, a co dělají naleznete v tématu:

        - [iOS](ios-device-features-settings.md)
        - [macOS](macos-device-features-settings.md)

4. Až skončíte, vyberte **OK** a zvolte **Vytvořit**. Provedené změny tak uložíte.

Profil se vytvoří a zobrazí v seznamu. Nezapomeňte [přiřadit profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).

## <a name="next-steps"></a>Další postup

Po vytvoření profilu je připraven k přiřazení. Dále [přiřadit profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).

Zobrazit všechna nastavení funkce zařízení pro [iOS](ios-device-features-settings.md) a [macOS](macos-device-features-settings.md) zařízení.
