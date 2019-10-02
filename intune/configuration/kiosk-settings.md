---
title: Nastavení veřejného terminálu pro Windows a holografická zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Nakonfigurujte zařízení s Windows 10 (a novější) a zařízení s Windows holografickým pro firmy jako veřejné terminály s jednou aplikací a s více aplikacemi, přizpůsobte nabídku Start, přidejte aplikace, zobrazte panel úloh a nakonfigurujte webový prohlížeč v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19641a36cf429773a8c0e06a90ee279d2baa06f7
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730574"
---
# <a name="windows-10-and-windows-holographic-for-business-device-settings-to-run-as-a-dedicated-kiosk-using-intune"></a>Nastavení zařízení s Windows 10 a Windows holografickým pro firmy, která se mají používat jako vyhrazené veřejné terminály pomocí Intune

V zařízeních s Windows 10 můžete pomocí Intune spouštět zařízení jako veřejný terminál, někdy označovaný jako vyhrazené zařízení. Zařízení v celoobrazovkovém režimu může spouštět jednu aplikaci nebo spouštět mnoho aplikací. Můžete zobrazit a přizpůsobit nabídku Start, přidat různé aplikace, včetně aplikací Win32, přidat konkrétní domovskou stránku do webového prohlížeče a další. 

Tato funkce se vztahuje na zařízení se systémem:

- Windows 10 a novější
- Windows Holographic for Business

Intune podporuje jeden profil beznabídkového režimu v jednom zařízení. Pokud potřebujete více profilů beznabídkového režimu, můžete použít [vlastní OMA-URI](custom-settings-windows-10.md).

Intune používá konfigurační profily k vytvoření a přizpůsobení těchto nastavení potřebám vaší organizace. Po přidání těchto funkcí do profilu můžete tato nastavení nasdílet nebo nasadit do skupin ve vaší organizaci.

V tomto článku se dozvíte, jak vytvořit profil konfigurace zařízení. Seznam všech nastavení a jejich toho, co dělají, najdete v tématu Nastavení veřejného [terminálu Windows 10](kiosk-settings-windows.md) a [Nastavení veřejného terminálu pro Windows holografick pro firmy](kiosk-settings-holographic.md).

## <a name="create-the-profile"></a>Vytvoření profilu

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte následující vlastnosti:

   - **Název**: Zadejte popisný název nového profilu.
   - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
   - **Platforma**: Vyberte **Windows 10 a novější**.
   - **Typ profilu**: Vyberte veřejný **terminál** .

4. V **Nastavení**vyberte **celoobrazovkový režim**. **Beznabídkový režim** určuje typ režimu veřejného terminálu podporovaného zásadami. Vaše možnosti jsou:

    - **Není konfigurováno** (výchozí): Zásady nepovolují režim veřejného terminálu.
    - **Beznabídkový režim na celou obrazovku s jednou aplikací**: Zařízení se spustí jako účet jednoho uživatele a uzamkne ho pro jednu aplikaci pro Store. Když se uživatel přihlásí, spustí se daná aplikace. Tento režim zároveň brání uživateli v otevírání nových aplikací nebo změně spuštěné aplikace.
    - **Veřejný terminál s více aplikacemi**: Zařízení spustí více aplikací pro Store, aplikací Win32 nebo vnitřních aplikací pro Windows pomocí ID uživatele aplikace (AUMID). Na zařízení jsou dostupné pouze aplikace, které přidáte.

        Veřejný terminál s více aplikacemi, neboli zařízení s pevně stanoveným účelem, umožňuje poskytovat přehledné prostředí uživatelům, protože jim povoluje přístup pouze k aplikacím, které potřebují. Nezobrazuje jim aplikace, které nepotřebují.

    Seznam všech nastavení a o tom, co dělají, najdete v těchto tématech:
      - [Nastavení veřejného terminálu Windows 10](kiosk-settings-windows.md)
      - [Nastavení veřejného terminálu pro Windows Holografick pro firmy](kiosk-settings-holographic.md)

5. Až to budete mít, vyberte **OK** > **Vytvořit** a změny uložte. 

Profil se vytvoří a zobrazí se v seznamu profily. Dále [přiřaďte](device-profile-assign.md) profil.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Pro zařízení s následujícími platformami můžete vytvořit profily na veřejném terminálu:
- [Androidemem](device-restrictions-android.md#kiosk)
- [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings)
- [Windows 10 a novější](kiosk-settings-windows.md)
- [Windows Holographic for Business](kiosk-settings-holographic.md)
