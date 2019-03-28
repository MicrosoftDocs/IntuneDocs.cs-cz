---
title: 'Rychlý start: Nastavení automatické registrace v Intune'
description: 'Rychlý start: Nastavení automatické registrace zařízení s Windows 10 v Intune.'
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 03/26/2019
ms.author: erikje
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3b81525034f69b43abeb60f562e4d6ee6a46b866
ms.sourcegitcommit: d38ca1bf44e17211097aea481e00b6c1e87effae
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/27/2019
ms.locfileid: "58514276"
---
# <a name="quickstart-set-up-automatic-enrollment-for-windows-10-devices"></a>Rychlý start: Nastavení automatické registrace pro zařízení s Windows 10

V tomto rychlém startu nastavíte v Microsoft Intune automatickou registraci zařízení, když se konkrétní uživatelé přihlásí k zařízením s Windows 10.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadavky

- Předplatné Microsoft Intune – [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).
- K dokončení tohoto rychlého startu potřebujete napřed [vytvořit uživatele](quickstart-create-user.md) a [vytvořit skupinu](quickstart-create-group.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo jako správce služby Intune. Pokud jste vytvořili zkušební předplatné Intune, účet, z něhož jste toto předplatné vytvořili, je globálním správcem.

## <a name="set-up-windows-10-automatic-enrollment"></a>Nastavení automatické registrace pro Windows 10

V tomto příkladu použijete registraci MDM, aby byla možná automatická registrace firemních zařízení i vlastních zařízení uživatelů. Zaregistrujete si bezplatné předplatné Azure Active Directory verze Premium.

1. V Azure zvolte **Azure Active Directory** > **Mobilita (MDM a MAM)**.
2. Vyberte možnost **Abyste mohli použít tuto funkci, získejte bezplatnou zkušební verzi Premium**. Její výběr vám umožní automatickou registraci pomocí bezplatné zkušební verze Premium služby Azure Active Directory. 

    ![Výběr bezplatné zkušební verze Premium služby Azure Active Directory](media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-01.png)

    Zvolte možnost bezplatné zkušební verze **Enterprise Mobility + Security E5**. Tuto bezplatnou zkušební verzi musíte navíc **Aktivovat**.

    ![Volba bezplatné zkušební verze Enterprise Mobility + Security E5](media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-02.png)

3. Vyberte **Microsoft Intune**. 

    ![Volba Microsoft Intune v seznamu](media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-03.png)

4. V seznamu **Obor uživatele MDM** vyberte **Někteří**. Automatická registrace MDM se tak použije ke správně podnikových dat na zaměstnaneckých zařízeních s Windows. Automatická registrace MDM se nakonfiguruje pro zařízení připojená ke službě AAD a vlastní zařízení uživatelů.

    ![Výběr možnosti Někteří v seznamu konfigurace](media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-04.png)

5. Jako přiřazenou skupinu zvolte **Vybrat skupiny** > **Testeři Contoso** > **Vybrat**.

    ![Výběr skupiny k registraci](media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-05.png)

6. V seznamu **Obor uživatele MDM** vyberte **Někteří**. Data se tak budou spravovat na zařízeních vašich zaměstnanců.
7. Jako přiřazenou skupinu zvolte **Vybrat skupiny** > **Testeři Contoso** > **Vybrat**. 
8. Pro zbývající konfigurační hodnoty použijte výchozí hodnoty.
9. Zvolte **Uložit**.

## <a name="clean-up-resources"></a>Vyčištění prostředků

Pokud chcete automatickou registraci v Intune změnit, zaškrtněte, že chcete [nastavit registraci zařízení s Windows](windows-enroll.md).

## <a name="next-steps"></a>Další postup

V tomto rychlém startu jste se naučili, jak nastavit automatickou registraci zařízení s Windows 10. Další informace o registraci zařízení najdete v článku [Co je registrace zařízení?](device-enrollment.md)

Pokud chcete postupovat podle této série rychlých startů Intune, pokračujte k dalšímu rychlému startu.

> [!div class="nextstepaction"]
> [Rychlý start: Registrace zařízení s Windows 10](quickstart-enroll-windows-device.md)
