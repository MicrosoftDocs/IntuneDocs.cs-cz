---
title: Upgrade Windows 10 a nastavení režimu S v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zobrazit seznam všech nastavení a co dělají, při upgradu edice Windows 10 na zařízení nebo povolit režim S na zařízení pomocí profilu konfigurace zařízení v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 24f763cf3231bd76a01870d889cb7637f2f36532
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849671"
---
# <a name="windows-10-and-newer-device-settings-to-upgrade-editions-or-enable-s-mode-in-intune"></a>Windows 10 (a novější) nastavení upgradu edice nebo povolit S režimu v Intune

Microsoft Intune zahrnuje mnoho nastavení, která pomáhá spravovat a chránit vaše zařízení. Tento článek uvádí a popisuje nastavení upgradu edice nebo povolit S režimu na zařízeních s Windows 10. Tato nastavení se vytvoří v profilu konfigurace upgradem v Intune, které jsou vloženy nebo nasadit do zařízení.

Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete řídit edition a S možností režimu pro zařízení s Windows 10.

Další informace o této funkci najdete v tématu [edice upgradovat Windows 10 nebo režim povolit S](edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvoření profilu](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Upgrade edice

- **Upgrade edice na**: Vyberte, který upgradujete na edici Windows 10. Zařízení, pro která zásada platí, se upgradují na vámi vybranou edici.
- **Kód Product Key**: Zadejte kód product key, který jste získali od Microsoftu. Po vytvoření zásady s kódem Product Key nepůjde kód aktualizovat. Kód je také z bezpečnostních důvodů skrytý. Pokud chcete kód Product Key změnit, zadejte ho celý znovu.
- **Soubor s licencí**: Pro **Windows 10 Holographic pro firmy** nebo **edice Windows 10 Mobile**, zvolte **Procházet** a vyberte licenční soubor, který jste získali od Microsoftu. Tento licenční soubor obsahuje informace o licencích pro edice, kterou upgradujete zařízení.

## <a name="mode-switch"></a>Přepnout režim

- **Žádná konfigurace**: Zařízení v režimu S zůstane v režimu S. Koncový uživatel může zařízení přepnout z režimu S.
- **Zachovat v režimu S**: Zakáže koncovému uživateli přepínání z režimu S zařízení.
- **Přepínač**: Přepne z režimu S zařízení.

## <a name="next-steps"></a>Další postup

Vytvoření profilu, ale to nemusí být teď zrovna nic nedělá ještě. Nezapomeňte [přiřadit profil](device-profile-assign.md), a [monitorování jejího stavu](device-profile-monitor.md).

Můžete také vytvořit vydání upgradu profily pro [Windows Holographic for Business](holographic-upgrade.md) zařízení.
