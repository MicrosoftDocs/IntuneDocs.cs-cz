---
title: Nastavení sdílené nebo více uživatelů zařízení v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Přidat a používat Windows 10 a Windows Holographic for Business zařízení, která jsou sdílená nebo použít víc uživatelů v Microsoft Intune. Zobrazit seznam všech nastavení a co dělají na zařízeních, včetně Microsoft HoloLens. Řídit účty hostů, Správa účtů a odstranit neaktivní účty, povolit nebo zakázat ukládání do místního úložiště, nastavení napájení a režimu spánku možnosti, vyberte při aktualizace jsou nainstalovány a používat zařízení v prostředí education v profilu konfigurace zařízení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: dc1fca439f0edf4a5d4caaad4ff4f9e0bae5972b
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66374054"
---
# <a name="control-access-accounts-and-power-features-on-shared-pc-or-multi-user-devices-using-intune"></a>Řízení přístupu, účty a funkce power na sdílený počítač nebo zařízení více uživatelů pomocí Intune

Zařízení, která mají více uživatelů se nazývají sdílené zařízení a jsou běžné součástí sady řešení správy mobilních zařízení. Pomocí Microsoft Intune, můžete přizpůsobit sdílená zařízení s následujícími platformami:

- Windows 10 Professional a novější
- Windows 10 Enterprise a novější
- Windows Holographic for Business, jako je například HoloLens

Například škol mají zařízení, které jsou obvykle používány mnoho studentů. S tímto nastavením školním správcem Intune můžete zapnout funkci sdíleného počítače a umožňuje jeden uživatel v čase. Studenti nelze přepínat mezi různými účty přihlášení na zařízení. Po odhlášení studenta můžete také odebrat všechna uživatelská nastavení.

Koncovým uživatelům můžete přihlásit do těchto sdílených zařízení pomocí účtu guest. Po přihlášení uživatele, jsou přihlašovací údaje uložené v mezipaměti. Během používání zařízení, koncovým uživatelům pouze získáte přístup na funkce, které povolíte. Například zvolíte, když zařízení přejde do režimu spánku režim, pokud uživatelé můžete naleznete v tématu a uložit soubory místně, povolit nebo zakázat nastavení řízení spotřeby a další. Také určují, pokud účet guest odstraní, když uživatel příznaky vypnout nebo odstranit neaktivní účty po dosažení prahové hodnoty.

Tento článek ukazuje, jak vytvořit konfigurační profil a obsahuje odkazy na dostupná nastavení s jejich popisy.

Profil se vytvoří v Intune, nasazení nebo přiřaďte profil ke skupinám zařízení ve vaší organizaci. Můžete také přiřadit tento profil ke skupinám zařízení s typy smíšené zařízení a verze operačního systému (OS).

## <a name="create-the-profile"></a>Vytvoření profilu

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

   - **Název**: Zadejte popisný název pro nový profil.
   - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
   - **Platforma**: Vyberte **Windows 10 a novější**.
   - **Typ profilu**: Vyberte **sdílený více uživateli zařízení**.

4. Nakonfigurujte nastavení pro [Windows 10 a novější](shared-user-device-settings-windows.md) nebo [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).

5. Vyberte **OK** > **Vytvořit** a změny uložte.

Váš profil se vytvoří a zobrazí v seznamu, ale to není teď zrovna nic nedělá ještě. Nezapomeňte [přiřadit profil](device-profile-assign.md) skupinám zařízení ve vaší organizaci.

## <a name="next-steps"></a>Další postup

- Podívejte se na nastavení pro [Windows 10 a novější](shared-user-device-settings-windows.md) a [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).
- [Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
