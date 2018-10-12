---
title: 'Rychlý start: Nastavení automatické registrace v Intune'
description: 'Rychlý start: Nastavení automatické registrace zařízení s Windows 10 v Intune.'
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 3b713f090fb6ada884a269e286f55f6e1b1087c4
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581577"
---
# <a name="quickstart-set-up-automatic-enrollment-for-windows-10-devices"></a>Rychlý start: Nastavení automatické registrace zařízení s Windows 10

V tomto rychlém startu nastavíte v Microsoft Intune automatickou registraci zařízení, když se konkrétní uživatelé přihlásí k zařízením s Windows 10.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadavky

- K dokončení tohoto rychlého startu potřebujete napřed [vytvořit uživatele](quickstart-create-user.md) a [vytvořit skupinu](quickstart-create-group.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo jako správce služby Intune.

## <a name="set-up-windows-10-automatic-enrollment"></a>Nastavení automatické registrace pro Windows 10

V tomto příkladu použijete k registraci MDM, aby byla možná automatická registrace firemních zařízení i vlastních zařízení uživatelů.

1. V Azure zvolte **Azure Active Directory** > **Mobilita (MDM a MAM)** > **Microsoft Intune** > **Někteří**.
![Prohlížeč](media/quickstart-setup-auto-enrollment/setup-automatic-enrollment-win10.png)
2. Zvolte **Výběr skupin** > **Contoso Testers** > **Vybrat**.
3. Použijte výchozí hodnoty pro následující adresy URL:
    - Adresa URL podmínek použití MDM
    - Adresa URL zjišťování MDM
    - Adresa URL s předpisy služby MDM
4. Zvolte **Uložit**.
5. Na zařízení s Windows 10 se přihlaste jako uživatel skupiny a postupujte podle pokynů.

## <a name="clean-up-resources"></a>Vyčištění prostředků

Pokud chcete automatickou registraci v Intune změnit, zaškrtněte, že chcete [nastavit registraci zařízení s Windows](windows-enroll.md).

## <a name="next-steps"></a>Další kroky

V tomto rychlém startu jste se naučili, jak nastavit automatickou registraci zařízení s Windows 10. Teď se naučíte další způsoby registrace zařízení na všech platformách.

> [!div class="nextstepaction"]
> [Článek o registraci zařízení](device-enrollment.md)