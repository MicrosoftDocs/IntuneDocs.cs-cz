---
title: "Registrace zařízení s iOSem v Intune | Dokumentace Microsoftu"
description: "Popisuje registraci zařízení s iOSem v Intune."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope: User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 4d7ad138a8aa59ceeff00866469e59e2e1d19520
ms.sourcegitcommit: 2a6ad3c233d15a9fb441362105f64b2bdd550c34
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/13/2017
---
# <a name="enroll-your-ios-device-in-intune"></a>Registrace zařízení se systémem iOS do Intune

Pokud vaše společnost nebo škola používá Microsoft Intune, můžete svoje zařízení s iOSem zaregistrovat a získat tak přístup k e-mailům, souborům a dalším prostředkům společnosti. Když si svoje zařízení zaregistrujete, může vaše IT oddělení tyto pracovní nebo školní prostředky spravovat, udržovat je v bezpečí a zároveň vám umožnit, abyste k plnění úkolů používali zařízení, které preferujete. Další informace o registraci najdete v tématu [Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení v Intune?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md).

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment/player]

> [!NOTE]
> Pokud se snažíte zaregistrovat zařízení s macOS (například MacBook Pro nebo iMac), [vyzkoušejte místo toho tento postup](enroll-your-device-in-intune-macos.md).

**Než začnete:**

- Po zahájení tohoto postupu nezapomeňte registraci dokončit. Přerušení registrace na více než několik minut obvykle celý proces zastaví a bude vyžadovat jeho opětovné zahájení.
- Pokud se vaše registrace z jakéhokoli důvodu nezdaří, budete se muset vrátit do aplikace Portál společnosti a zkusit to znovu.
- Ověřte, že vám funguje Wi-Fi. V opačném případě registrace selže.
- Pokud jste v zařízení zablokovali Safari, odblokujte ho. Safari je součástí procesu registrace zařízení.


**Registrace zařízení s iOSem**

1.  Postupujte podle návodu v tématu [Instalace a přihlášení do aplikace Portál společnosti Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md).

2. Na stránce **Nastavení firemního přístupu** klepněte na **Začít**.

    ![ios-enroll-comp-access-setup-begin](./media/ios-enroll-1a-comp-access-setup.png)

3. Na obrazovce **Proč zařízení registrovat?** si přečtěte informace o tom, co vám registrace zařízení umožní, a potom klepněte na **Pokračovat**.

    ![ios-enroll-why-enroll](./media/ios-enroll-1b-why-enroll.png)

  > [!NOTE]
  > Žluté trojúhelníky neznamenají, že už došlo k chybě. Tyto ikony označují, že ještě existují kroky, které se musí v procesu registrace dokončit.

4. Prohlédněte si seznam toho, co váš správce IT uvidí nebo neuvidí ve vašem zařízení, a klepněte na **Pokračovat**.

    ![ios-enroll-what-it-can-see](./media/ios-enroll-1c-we-care-privacy.png)

5.  Na obrazovce **Co dál?** si přečtěte, co probíhá při registraci, a potom klepněte na **Registrovat**.

    ![ios-enroll-what-comes-next](./media/ios-enroll-1d-what-comes-next.png)

6.  Na obrazovce **Nainstalovat profil** klepněte na **Instalovat**, a pokud se zobrazí výzva, zadejte své heslo.

    ![ios-enroll-install-profile](./media/ios-enroll-2-mgt-profile-install.png)

7.  Klepněte na **Instalovat**.

    ![ios-enroll-tap-install](./media/ios-enroll-3-mgt-profile-install-2.png)    

8.  Klepnutím na **Instalovat** dejte najevo, že jste si přečetli upozornění.

    ![ios-enroll-tap-install-after-warning](./media/ios-enroll-4-warning.png)

9.  Klepněte na **Důvěřovat**.

    ![ios-enroll-tap-trust](./media/ios-enroll-5-trust.png)

10.  Po změně obrazovky a dokončení instalace profilu klepněte na **Hotovo**.

    ![ios-enroll-tap-done](./media/ios-enroll-6-done.png)

    Na obrazovce se objeví zpráva, že se „zařízení registruje“.

11.  Pokud se zobrazí zpráva s dotazem, jestli chcete otevřít stránku Portálu společnosti, klepněte na **Otevřít**.

    ![ios-enroll-open-comp-portal](./media/ios-enroll-7-open-cp.png)

12. Na obrazovce **Nastavení firemního přístupu** klepněte na **Pokračovat**. Na této obrazovce vidíte, jaké další požadavky může být nutné splnit, aby vaše zařízení vyhovovalo zásadám, jako je například nastavení hesla. Postupujte podle pokynů na obrazovce, dokud nesplníte všechny požadavky týkající se dodržování předpisů. Po dokončení se vrátíte na obrazovku nastavení firemního přístupu. Klepněte na **Pokračovat**.

    ![ios-enroll-comp-access-tap-continue](./media/ios-enroll-8-comp-access-setup-compliance.png)

13. Klepněte na **Hotovo**.

    ![ios-enroll-tap-done](./media/ios-enroll-9-comp-access-setup-complete.png)

Zařízení je nyní zaregistrováno v Intune a budete přesměrováni zpět do aplikace Portál společnosti.

> [!Note]
> K úplné registraci zařízení je potřeba dokončit ještě několik kroků. Přečtěte si další informace o [registraci zařízení s použitím softwaru pro správu telekomunikačních výdajů](enroll-your-device-with-telecom-expense-management-ios.md). Pokud vaše organizace používá program registrace zařízení společnosti Apple, přečtěte si další informace [tady](enroll-your-device-dep-ios.md).

Potřebujete ještě další pomoc? Obraťte se na správce IT. Kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).
