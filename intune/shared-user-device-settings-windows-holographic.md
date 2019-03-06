---
title: Windows Holographic Business nastavení sdíleného zařízení – Microsoft Intune – Azure | Dokumentace Microsoftu
description: Přidat a používat Windows Holographic for Business ke konfiguraci zařízení, která jsou sdílená nebo použít víc uživatelů v Microsoft Intune. Zobrazit seznam nastavení pro správu účtu a co dělají na zařízeních, včetně Microsoft HoloLens.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: ea07b871872ecdf2f8cf4d71a1f0fda04bfad3c2
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57393013"
---
# <a name="windows-holographic-for-business-settings-to-manage-shared-devices-using-intune"></a>Windows Holographic for Business nastavení spravovat sdílená zařízení pomocí Intune

Windows Holographic for Business zařízení, jako je například Microsoft HoloLens můžete využívat více uživatelů. Zařízení, která mají více uživatelů se nazývají sdílené zařízení a jsou součástí správy mobilních zařízení (MDM) řešení.

Pomocí Microsoft Intune, uživatelé můžou přihlašovat do těchto sdílených zařízení pomocí účtu guest. Během používání zařízení, dostanou jenom přístup k funkcím, které povolíte.

Tento článek uvádí a popisuje, jaká nastavení můžete použít ve Windows Holographic for Business profil konfigurace zařízení. Při vytvoření profilu v Intune, můžete pak nasadit nebo přiřaďte profil ke skupinám zařízení ve vaší organizaci. Můžete také přiřadit tento profil pro skupinu zařízení s typy smíšené zařízení a verze operačního systému.

Další informace o této funkci v Intune najdete v tématu [ovládat přístup, účty a funkce power sdílené počítače nebo zařízení více uživatelů](shared-user-device-settings.md). Další informace o Windows CSP najdete v tématu [AccountManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp).

## <a name="before-your-begin"></a>Před vaše begin

[Vytvoření profilu](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Nastavení sdíleného zařízení s více uživateli

> [!NOTE]
> Zařízení se systémem Windows Holographic for Business, včetně Microsoft HoloLens, podporují pouze **správy účtů** nastavení. Pokud můžete konfigurovat další nastavení uvedená v Intune, včetně **režim sdíleného počítače**, nemá žádný vliv na tato zařízení.

- **Správa účtů**: Nastavte na **povolit** automaticky odstranit místní účty vytvořené Hosté a účtů v AD a Azure AD. Když se uživatel odhlásí vypnutí zařízení nebo když údržbu systému, jsou tyto účty odstranit. Pokud je povolená, taky nastavte:
  - **Odstranění účtu**: Zvolte, pokud dojde k odstranění účtu: **Na prahové hodnoty pro prostor úložiště**, **prahová hodnota pro prostor úložiště a neaktivní prahová hodnota**, nebo **ihned po odhlášení**. Dále zadejte:
    - **Spuštění odstranění threshold(%)**: Zadejte hodnotu v procentech (0 – 100) místa na disku. Pokud celkový disk nebo prostor úložiště se sníží pod hodnota, kterou zadáte, se odstraní účty v mezipaměti. Trvale odstraní účty pro uvolnění místa na disku. Účty, které jsou neaktivní nejdéle jsou jako první smazány.
    - **Zastavit odstraňování threshold(%)**: Zadejte hodnotu v procentech (0 – 100) místa na disku. Pokud celkový disk nebo prostor úložiště splňuje hodnota, kterou zadáte, odstraňuje se zastaví.

  Nastavte na **zakázat** zachovat místní AD a účty Azure AD, které jsou vytvořené hosté.

  > [!NOTE]
  > Zařízení Microsoft HoloLens podporují jenom **správy účtů** nastavení.

## <a name="next-steps"></a>Další postup

- [Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
- Podívejte se na nastavení pro [Windows 10 a novější](shared-user-device-settings-windows.md).
