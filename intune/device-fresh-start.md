---
title: Resetování zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí funkce Začít znovu můžete odebrat nebo odinstalovat aplikace z počítačů s Windows 10 s využitím Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 902ffbcd8f12ba6deb215a54ce378fae94d20426
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/20/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Resetování zařízení s Windows 10 přes Intune pomocí akce Začít znovu


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce zařízení **Začít znovu** odebere veškeré aplikace nainstalované na počítači s Windows 10 a aktualizací Creators Update. Potom počítač automaticky aktualizuje na nejnovější verzi Windows.

Tato akce pomáhá odebrat předinstalované aplikace (výrobců OEM), které se obvykle instalují na nový počítač. Pokud chcete zachovat obsah domovské složky a odebrat pouze aplikace a nastavení, použijte nastavení se zachováním dat uživatele`if user data is retained`.

> [!IMPORTANT]
> Akce Začít znovu zruší registraci zařízení v Intune, zařízení ale zůstává připojené v Azure Active Directory.

## <a name="use-fresh-start"></a>Použití akce Začít znovu

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** a potom **Všechna zařízení**.
4. V seznamu zařízení, která spravujete, zvolte zařízení s Windows 10 Desktop a potom vyberte **Začít znovu**.

## <a name="next-steps"></a>Další kroky

Pokud chcete zobrazit stav akce, vyberte **Akce zařízení** (**Microsoft Intune** > **Zařízení**).