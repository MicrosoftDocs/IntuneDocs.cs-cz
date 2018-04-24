---
title: Registrace zařízení s macOS v Intune pomocí Portálu společnosti | Dokumentace Microsoftu
description: Popisuje postup registrace zařízení s macOS v Intune pomocí aplikace Portál společnosti.
keywords: Mac OS X, macOS, OS X
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: e3990c0670516de907ac048b844152014db5be57
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>Registrace zařízení s macOS v Intune pomocí aplikace Portál společnosti

Přístup k aplikacím, datům a prostředkům vaší organizace vám zjednodušuje práci. Ke [správě přístupu k těmto prostředkům](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md) používá vaše organizace službu Intune, která vyžaduje stažení aplikace Portál společnosti pro macOS. Tyto pokyny týkají zařízení s macOS využívající OS X El Capitan 10.11+.

> [!NOTE]
> Pokyny pro registraci zařízení s macOS využívající dřívější verze macOS najdete [tady](enroll-your-device-in-intune-macos-legacy.md).

1. V __Docku__ vyhledejte __Safari__ a otevřete nové okno. Potom otevřete [web Portál společnosti](https://portal.manage.microsoft.com).

2. Přihlaste se na web Portál společnosti přes svůj pracovní nebo školní účet.

   [!INCLUDE [wit_nextref](includes/end-user-password-guidance.md)]


3. Po přihlášení klikněte na **Nabídku** v levém horním rohu stránky a vyberte **Moje zařízení**.

   ![Snímek obrazovky s úvodní stránkou webového portálu se zobrazenými informacemi o tom, že se ještě nedají instalovat žádné aplikace, a s tlačítkem Moje zařízení zobrazeným níže](./media/macOS_enroll_001_landing_page.png)

4. Na stránce __Moje zařízení__ se zobrazí buď seznam zaregistrovaných zařízení, nebo informační zpráva. Závisí to na tom, jestli máte nějaká zaregistrovaná zařízení, macOS, nebo nikoli. Pokud chcete zaregistrovat zařízení, které není na seznamu, vyberte informační zprávu __Pokud je vaše zařízení na seznamu, identifikujte ho tak, že klepnete sem. Pokud zařízení uvedené není, můžete ho zaregistrovat klepnutím sem__. Pokud nemáte žádná zaregistrovaná zařízení, zobrazí se informační zpráva **Nemáte zaregistrované žádné zařízení. Toto můžete zaregistrovat klepnutím sem.**

    ![Snímek obrazovky se stránkou Moje zařízení s několika neidentifikovanými zařízeními zobrazenými nad výzvou k registraci zařízení, která nejsou v seznamu, nebo k identifikaci neidentifikovaných zařízení](./media/macOS_enroll_002_tap_here_banner.png)

5. Abyste mohli pokračovat v registraci, stáhněte si do zařízení s macOS aplikaci Portál společnosti.

    ![Oznámení obsahující výzvu pro uživatele, aby si stáhl aplikaci Portál společnosti pro macOS. Toto oznámení uvádí text pro daný krok nad tlačítkem Stáhnout, které se nachází v pravém dolním rohu.](./media/macOS_enroll_IWP_CP_app_notice.png)

6. Váš Mac ověří, že soubor ke stažení **CompanyPortal.pkg** můžete bezpečně otevřít. Spusťte instalační program a proveďte celý proces instalace.

7. Po dokončení instalačního programu otevřete složku **Aplikace** nebo **Launchpad** a potom otevřete **Portál společnosti**.

8. Na Macu se zobrazí zpráva o tom, že **Portál společnosti je aplikace stažená z internetu a jestli ji opravdu chcete otevřít.** Klikněte na **Otevřít**.

   > [!NOTE]
   > Intune potřebuje přístup k počítači pro ověření, že je vaše zařízení natolik bezpečné, že může mít přístup k prostředkům ve vaší organizaci. Pokud váš počítač odmítá aplikaci Portál společnosti otevřít, zkuste [vypnout Gatekeeper](https://support.apple.com/HT202491) a otevřít ji znovu.

9. Na první obrazovce vás aplikace Portál společnosti vyzve, abyste se **přihlásili** pomocí stejného pracovního nebo školního účtu, jako jste použili k přihlášení na web Portál společnosti.

10. Portál společnosti potvrdí informace o vašem účtu a zobrazí stav **registrace zařízení** a **dodržování předpisů zařízení**. Žluté trojúhelníky vás informují, že je potřeba provést akce, které zajistí, že váš Mac bude bezpečný pro použití v práci. Kliknutím na **Začít** zahájíte [registraci zařízení do systému správy](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).

11. Spustí se registrace vašeho Macu do systému správy. V průběhu tohoto procesu můžete být vyzváni k zadání přihlašovacích údajů počítače. Registrace může trvat několik minut. Během toho ale můžete s počítačem pracovat. Jakmile se dokončí nastavení přístupu společnosti, zobrazí se zpráva, že je vše hotovo.

Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu. Kontaktní informace správce najdete na [webu Portál společnosti](https://portal.manage.microsoft.com#HelpDeskDialog).
