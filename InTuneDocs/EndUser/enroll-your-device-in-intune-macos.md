---
title: "Registrace zařízení s macOS v Intune | Dokumentace Microsoftu"
description: "Popisuje postup registrace zařízení s macOS do Intune."
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope:
- User help
ROBOTS: 
ms.reviewer: mamoriss
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: e2a507ff6f803cf022536824ca2f12f6d6a64d75
ms.openlocfilehash: 4b532299070bdb8ddf0e9de1e6b598e8dcd8ffb3
ms.lasthandoff: 02/24/2017


---

# <a name="enroll-your-macos-device-in-intune"></a>Registrace zařízení s macOS do Intune

Přístup k aplikacím, datům a prostředkům vaší organizace vám umožňuje dělat vaši práci. Pokud pro práci používáte zařízení s macOS, znamená to instalaci __profilu správy__. To je soubor, který nastavuje váš správce IT a který načítá informace o nastaveních a přístupu do vašeho Macu. Chcete se dozvědět více? Zjistěte, [co se stane, když nainstalujete aplikaci Portál společnosti a zaregistrujete své zařízení do Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md).

  > [!NOTE]
  > Pokud se snažíte zařízení s iOSem (jako iPhone nebo iPad) skutečně zaregistrovat, [vyzkoušejte místo toho tyto pokyny](enroll-your-device-in-intune-ios.md).

1. V __Docku__ vyhledejte __Safari__ a otevřete nové okno. Potom otevřete [web Portál společnosti](http://portal.manage.microsoft.com).
2. Přihlaste se na web Portál společnosti přes svůj pracovní nebo školní účet.

  [!INCLUDE[wit_nextref](../includes/end-user-password-guidance.md)]

3. Po přihlášení se zobrazí dostupné karty __Domů__, __Aplikace__ a __Kategorie__. Na této stránce se zobrazí dostupné aplikace, které si můžete nainstalovat. Pokud ještě nemáte zaregistrovaná žádná zařízení, zobrazí se oznámení **Nemůžeme zobrazit žádné aplikace**. Můžete pokračovat výběrem možnosti __Moje zařízení__.

 ![Snímek obrazovky s úvodní stránkou webového portálu se zobrazenými informacemi o tom, že se ještě nedají instalovat žádné aplikace, a s tlačítkem Moje zařízení zobrazeným níže](./media/macOS_enroll_001_landing_page.png)

4. Na stránce __Moje zařízení__ se zobrazí buď seznam zaregistrovaných zařízení, nebo informační zpráva. Závisí to na tom, jestli máte nějaká zaregistrovaná zařízení, macOS, nebo nikoli. Pokud chcete zaregistrovat zařízení, které není na seznamu, vyberte informační zprávu __Pokud je vaše zařízení na seznamu, identifikujte ho tak, že klepnete sem. Pokud zařízení uvedené není, můžete ho zaregistrovat klepnutím sem.__.

  ![Snímek obrazovky se stránkou Moje zařízení s několika neidentifikovanými zařízeními zobrazenými nad výzvou k registraci zařízení, která nejsou v seznamu, nebo k identifikaci neidentifikovaných zařízení](./media/macOS_enroll_002_tap_here_banner.png)

5. Otevře se místní okno se stručným vysvětlením, proč máte __toto zařízení identifikovat nebo zaregistrovat__. Přečtěte si je a pokračujte kliknutím na __Zaregistrovat__.

 ![Identifikace nebo registrace tohoto zařízení s macOS](./media/macOS_enroll_003_IDenroll_popup.png)

6. Otevře se druhé místní okno se stručným vysvětlením, co se stane, když __toto zařízení zaregistrujete__. Přečtěte si je a pokračujte kliknutím na __Nainstalovat__.

 ![Registrace tohoto zařízení s macOS](./media/macOS_enroll_004_enroll_popup.png)

  > [!NOTE]
  > Intune potřebuje přístup k počítači pro ověření, že je vaše zařízení natolik bezpečné, že může mít přístup k prostředkům ve vaší organizaci. Zjistěte, [co se stane, když své zařízení zaregistrujete v Intune](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).

7. Otevře se okno __Předvolby systému__ s dotazem, jestli chcete __nainstalovat profil pro správu__. Pokračujte kliknutím na __Nainstalovat__. Pokud chcete získat více podrobností, klikněte na __Zobrazit profil__.

 ![Instalace profilu pro správu](./media/macOS_enroll_005_sysprefs_mgmt_profile.png)

8. Otevře se místní okno macOS. Potvrďte, že chcete provést změny. Uděláte to tak, že nejdříve zadáte __uživatelské jméno__ a __heslo__ pro svůj počítač a potom kliknete na __OK__. Tím se váš profil pro správu nainstaluje na váš Mac.

 ![Místní okno Instalace profilu macOS](./media/macOS_enroll_006_sysprefs_admin_login.png)

9. Můžou se zobrazovat nějaké další zprávy z Macu s dalšími podrobnostmi o profilu nebo o tom, jestli jste si jistí, že chcete profil __nainstalovat__. V těchto zprávách klikejte na __Pokračovat__ a __Nainstalovat__, abyste se dostali dál. Po dokončení instalace se můžete podívat na nově nainstalovaný __profil pro správu__ v seznamu __Profily zařízení__.

 ![Profil nainstalovaný na macOS](./media/macOS_enroll_007_sysprefs_installed_profile.png)

Potřebujete ještě další pomoc? Poraďte se se správcem IT. Kontaktní informace správce najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).

