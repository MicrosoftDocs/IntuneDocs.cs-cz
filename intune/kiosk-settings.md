---
title: Nastavení beznabídkového režimu pro Windows a holografické zařízení v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Konfigurace Windows 10 (a novější) a Windows Holographic for Business zařízení jako veřejné terminály jedné aplikace a s více aplikacemi, přizpůsobení nabídky start, přidejte aplikace, zobrazit na hlavním panelu a konfigurace webového prohlížeče v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e80bbbb87df88acc24a64a1bb0d977c91c970bb3
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57394445"
---
# <a name="windows-10-and-windows-holographic-for-business-device-settings-to-run-as-a-dedicated-kiosk-using-intune"></a>Windows 10 a Windows Holographic for Business nastavení zařízení pro spuštění jako vyhrazené veřejný terminál, pomocí Intune

Na zařízení s Windows 10 pomocí Intune můžete spustit zařízení jako veřejný terminál, někdy označovanou jako vyhrazená zařízení. Zařízení v celoobrazovkovém režimu, můžete spustit jednu aplikaci nebo spustit velký počet aplikací. Můžete zobrazit a přizpůsobit nabídku start, přidat různé aplikace, včetně aplikací Win32, přidejte konkrétní domovskou stránku webového prohlížeče a další. 

Tato funkce se vztahuje na zařízení se systémem:

- Windows 10 a novější
- Windows Holographic for Business

Intune podporuje jeden profil beznabídkového režimu v jednom zařízení. Pokud potřebujete více profilů beznabídkového režimu, můžete použít [vlastní OMA-URI](custom-settings-windows-10.md).

Intune používá "konfiguračních profily" vytvořit a přizpůsobit nastavení pro potřeby vaší organizace. Po přidání těchto funkcí v profilu nabízená nebo nasazení těchto nastavení do skupiny ve vaší organizaci.

V tomto článku se dozvíte, jak vytvořit profil konfigurace zařízení. Seznam všech nastavení, a co dělají, naleznete v tématu [nastavení beznabídkového režimu pro Windows 10](kiosk-settings-windows.md) a [Windows Holographic for Business nastavení beznabídkového režimu](kiosk-settings-holographic.md).

## <a name="create-the-profile"></a>Vytvoření profilu

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

   - **Název**: Zadejte popisný název pro nový profil.
   - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
   - **Platforma**: Vyberte **Windows 10 a novější**
   - **Typ profilu**: Vyberte **veřejného terminálu**

4. V **nastavení**, vyberte **celoobrazovkový režim**. **Beznabídkový režim** určuje typ režimu veřejného terminálu podporovaného zásadami. Vaše možnosti jsou:

    - **Není nakonfigurováno** (výchozí): Zásady neumožňuje beznabídkový režim.
    - **Aplikace s jedním, celoobrazovkového**: Zařízení používá jako jeden uživatelský účet a uzamkne ji proti k jedné aplikaci Store. Když se uživatel přihlásí, spustí se daná aplikace. Tento režim zároveň brání uživateli v otevírání nových aplikací nebo změně spuštěné aplikace.
    - **Veřejný terminál s více aplikacemi**: Zařízení spustí Store více aplikací, aplikací Win32 nebo aplikací Windows doručené pošty s ID modelu uživatele aplikace (AUMID). Na zařízení jsou dostupné pouze aplikace, které přidáte.

        Veřejný terminál s více aplikacemi, neboli zařízení s pevně stanoveným účelem, umožňuje poskytovat přehledné prostředí uživatelům, protože jim povoluje přístup pouze k aplikacím, které potřebují. Nezobrazuje jim aplikace, které nepotřebují.

    Seznam všech nastavení, a co dělají naleznete v tématu:
      - [Nastavení beznabídkového režimu pro Windows 10](kiosk-settings-windows.md)
      - [Windows Holographic for Business nastavení beznabídkového režimu](kiosk-settings-holographic.md)

5. Až to budete mít, vyberte **OK** > **Vytvořit** a změny uložte. 

Profil se vytvoří a zobrazí v seznamu profilů. Dále [přiřadit](device-profile-assign.md) profilu.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete vytvořit profily beznabídkového režimu pro zařízení s následujícími platformami:
- [Android](device-restrictions-android.md#kiosk)
- [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings)
- [Windows 10 a novější](kiosk-settings-windows.md)
- [Windows Holographic for Business](kiosk-settings-holographic.md)
