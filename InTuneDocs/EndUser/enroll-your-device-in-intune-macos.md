---
title: "Registrace zařízení s macOS do Intune | Microsoft Intune"
description: "Popisuje postup registrace zařízení s macOS do Intune."
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 162d176c5f272f5f19ba18cdd07fe815ac1bcce7
ms.openlocfilehash: fc0efceb8a0c3e1323f7d94625bc5f618d35bfd6


---

# <a name="enroll-your-macos-device-in-intune"></a>Registrace zařízení s macOS do Intune

Přístup k aplikacím, datům a prostředkům vaší organizace vám umožňuje dělat vaši práci. Pokud pro práci používáte zařízení s macOS, znamená to instalaci __profilu správy__. To je soubor, který nastavuje správce IT a který načítá informace o nastavení a přístupu do vašeho Macu. Chcete se dozvědět více? Zjistěte, [co se stane, když nainstalujete aplikaci Portál společnosti a zaregistrujete své zařízení do Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md).

  > [!NOTE]
  > Pokud se snažíte zařízení s iOS (jako iPhone nebo iPad) skutečně zaregistrovat, [vyzkoušejte místo toho tyto pokyny](enroll-your-device-in-intune-ios.md).

1. V __Docku__ vyhledejte __Safari__ a otevřete nové okno. Potom otevřete [web Portál společnosti](http://portal.manage.microsoft.com).
2. Přihlaste se na web Portál společnosti přes svůj pracovní nebo školní účet.

  [!INCLUDE[wit_nextref](../includes/end-user-password-guidance.md)]

3. Po přihlášení uvidíte všechny dostupné __aplikace__, __zařízení__ a __kontaktní informace__ zaměstnanců oddělení IT. V horní části stránky uvidíte upozornění **Toto zařízení není zaregistrované, nebo ho Portál společnosti nedokáže identifikovat. <u>Klepnutím sem</u> vyberete jiné zařízení.** Klikněte na __Klepnutím sem__.

 ![Úvodní stránka Portálu společnosti v macOS](./media/macOS_enroll_001_landing_page.png)

4. Otevře se místní okno se stručným vysvětlením, proč máte __toto zařízení identifikovat nebo zaregistrovat__. Přečtěte si je a pokračujte kliknutím na __Zaregistrovat__.

 ![Identifikace nebo registrace tohoto zařízení s macOS](./media/macOS_enroll_002_IDenroll_popup.png)

5. Otevře se druhé místní okno se stručným vysvětlením, co se stane, když __toto zařízení zaregistrujete__. Přečtěte si je a pokračujte kliknutím na __Nainstalovat__.

 ![Registrace tohoto zařízení s macOS](./media/macOS_enroll_003_enroll_popup.png)

  > [!NOTE]
  > Intune potřebuje přístup k počítači pro ověření, že je vaše zařízení natolik bezpečné, že může mít přístup k prostředkům ve vaší organizaci. Zjistěte, [co se stane, když své zařízení zaregistrujete v Intune](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios).

6. Otevře se okno __Předvolby systému__ s dotazem, jestli chcete __nainstalovat profil pro správu__. Pokračujte kliknutím na __Nainstalovat__. Pokud chcete získat více podrobností, klikněte na __Zobrazit profil__.

 ![Instalace profilu pro správu](./media/macOS_enroll_004_sysprefs_mgmt_profile.png)

7. Otevře se místní okno macOS. Potvrďte, že chcete provést změny. Uděláte to tak, že nejdříve zadáte __uživatelské jméno__ a __heslo__ pro svůj počítač a potom kliknete na __OK__. Tím se váš profil pro správu nainstaluje na váš Mac.

 ![Místní okno Instalace profilu macOS](./media/macOS_enroll_005_sysprefs_admin_login.png)

8. Můžou se zobrazovat nějaké další zprávy z Macu s dalšími podrobnostmi o profilu nebo o tom, jestli jste si jistí, že chcete profil __nainstalovat__. V těchto zprávách klikejte na __Pokračovat__ a __Nainstalovat__, abyste se dostali dál. Po dokončení instalace se můžete podívat na nově nainstalovaný __profil pro správu__ v seznamu __Profily zařízení__.

 ![Profil nainstalovaný na macOS](./media/macOS_enroll_006_sysprefs_installed_profile.png)

Potřebujete ještě další pomoc? Poraďte se se správcem IT. Kontaktní informace správce najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).



<!--HONumber=Nov16_HO4-->


