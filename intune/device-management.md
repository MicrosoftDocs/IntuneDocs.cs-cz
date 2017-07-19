---
title: "Správa zařízení v Intune"
titleSuffix: Intune on Azure
description: "Zjistěte, jak můžete zobrazit zařízení spravovaná přes Intune a provádět s nimi různé operace."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f066e62e323fffb7c6954d83b2b55ee63f4be46
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/06/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Co je správa zařízení v Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Úloha **Zařízení** vám poskytuje přehled o spravovaných zařízeních a umožňuje na nich vzdáleně provádět různé úlohy. Tuto úlohu zpřístupníte takto:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.

Nyní můžete provést následující akce:

- [Zobrazit inventář zařízení](device-inventory.md)
- Provádění akcí se vzdáleným zařízením:
    - [Odebrat firemní data](device-company-data-remove.md) 
    - [Obnovení továrního nastavení](device-factory-reset.md)
    - [Vzdálené uzamčení](device-remote-lock.md)
    - [Resetovat heslo](device-passcode-reset.md)
    - [Vynechat zámek aktivace](device-activation-lock-bypass.md)
    - [Začít znovu](device-fresh-start.md)
    - [Režim ztráty](device-lost-mode.md)
    - [Najít zařízení](device-locate.md)
    - [Restartovat](device-restart.md)
    - [Resetovat PIN kód ve Windows 10](device-windows-pin-reset.md)
    - [Vzdálené řízení pro Android](device-profile-android-teamviewer.md)


## <a name="support-for-each-device-action"></a>Podpora jednotlivých akcí zařízení

Použijte následující tabulku, abyste pochopili, jak jsou platformy zařízení podporovány jednotlivými akcemi.

|||||||
|-|-|-|-|-|-|
|Akce zařízení|Windows|Windows Phone|iOS|macOS|Android|
|**Odebrat firemní data**|Ano|Ano|Ano|Ano|Ano|
|**Obnovení továrního nastavení**|Windows 8.1 a novější (zařízení nespravovaná systémem EAS)|Ano|Ano|Ne|Android for Work není podporovaný.|
|**Odstranit**|Ano|Ano|Ano|Ano|Ano|
|**Vzdálené uzamčení**|Ne|Windows Phone 8.1 nebo novější|Ano|Ne|Ano|
|**Resetovat heslo**|Ne|Windows Phone 8.1 až Windows 10 Creators Update bez připojení k Azure AD, Windows 10 Creators Update a novější – vše|Ano|Ne|Systémy Android starší než verze 7 a Android for Work nejsou podporované|
|**Nové heslo** (pro zařízení s Windows 10)|Ne|Windows 10 Creators Update a novější (připojené k Azure AD)|Ne|Ne|Android for Work není podporovaný.|
|**Vynechat zámek aktivace**|Ne|Ne|Pouze zařízení ve vlastnictví firmy|Ne|Ne|
|**Režim ztráty**|Ne|Ne|Zařízení s iOSem 9.3 nebo novějším, pod dohledem a ve vlastnictví firmy|Ne|Ne|
|**Najít zařízení**|Ne|Ne|Režim ztráty zařízení s iOSem 9.3 nebo novějším, pod dohledem a ve vlastnictví firmy|Ne|Ne|
|**Odhlásit aktuálního uživatele**|Ne|Ne|Zařízení s iOSem 9.3 nebo novějším (pouze sdílené iPady)|Ne|Ne|
|**Restartovat**|Windows 8.1 a vyšší|Windows Phone 8.1 nebo novější|Ne|Ne|Ne|
|**Začít znovu**|Windows 10 Creators Update a novější|Ne|Ne|Ne|Ne|
|**Nová relace Vzdálené pomoci**|Ne|Ne|Ne|Ne|Ano|
|**Odebrat uživatele**|Ne|Ne|Zařízení s iOSem 9.3 nebo novějším (pouze sdílené iPady)|Ne|Ne|

## <a name="next-steps"></a>Další kroky

- Zvolte **Akce zařízení**, abyste si zobrazili stav provedených akcí na spravovaných zařízeních. 
![Monitorování akcí zařízení](./media/monitor-device-actions.png)