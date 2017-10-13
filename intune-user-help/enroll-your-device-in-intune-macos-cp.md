---
title: "Registrace zařízení s macOS v Intune pomocí Portálu společnosti | Dokumentace Microsoftu"
description: "Popisuje postup registrace zařízení s macOS v Intune pomocí aplikace Portál společnosti."
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope: User help
ROBOTS: 
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: b40801633a130ac79b0ae5b4e1669320c70909e2
ms.sourcegitcommit: db7a7bbead3a3fa78c4d643607f709a2909eb608
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/28/2017
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>Registrace zařízení s macOS v Intune pomocí aplikace Portál společnosti

[!INCLUDE[macos-preview-1708](./includes/macos-preview-1708.md)]

Přístup k aplikacím, datům a prostředkům vaší organizace vám zjednodušuje práci. Ke [správě přístupu k těmto prostředkům](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md) používá vaše organizace službu Intune, která vyžaduje stažení aplikace Portál společnosti pro macOS. Tyto pokyny týkají zařízení s macOS využívající OS X El Capitan 10.11+.

  > [!NOTE]
  > Pokud chcete zaregistrovat zařízení s iOS, jako je iPhone nebo iPad, [vyzkoušejte místo toho tyto pokyny](enroll-your-device-in-intune-ios.md).

1.  V __doku__ najděte __Safari__ a přejděte na adresu [aka.ms/macoscompanyportal](https://aka.ms/macoscompanyportal). 

2. Stáhněte si aplikaci. Váš Mac ověří, že soubor ke stažení **CompanyPortal.dmg** můžete bezpečně otevřít. Po jeho otevření ze složky **Stahování** přetáhněte aplikaci **Portál společnosti** do složky **Aplikace**.

3. Otevřete složku **Aplikace** nebo **Launchpad** a potom otevřete **Portál společnosti**.

4. Na Macu se zobrazí zpráva o tom, že **Portál společnosti je aplikace stažená z internetu a jestli ji opravdu chcete otevřít.** Klikněte na **Otevřít**.

  > [!NOTE]
  > Intune potřebuje přístup k počítači pro ověření, že je vaše zařízení natolik bezpečné, že může mít přístup k prostředkům ve vaší organizaci. Pokud váš počítač odmítá aplikaci Portál společnosti otevřít, zkuste [vypnout Gatekeeper](https://support.apple.com/HT202491) a otevřít ji znovu.

6. Na první obrazovce vás aplikace Portál společnosti vyzve, abyste se **přihlásili** pomocí stejného pracovního nebo školního účtu, jako jste použili k přihlášení na web Portál společnosti.

7. Portál společnosti potvrdí informace o vašem účtu a zobrazí stav **registrace zařízení** a **dodržování předpisů zařízení**. Žluté trojúhelníky vás informují, že je potřeba provést akce, které zajistí, že bude Mac bezpečný pro použití v práci. Kliknutím na **Začít** zahájíte [registraci zařízení do systému správy](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).

8. Spustí se registrace vašeho Macu do systému správy. V průběhu tohoto procesu můžete být vyzváni k zadání přihlašovacích údajů počítače. Registrace může trvat několik minut. Během toho ale můžete s počítačem pracovat. Jakmile se dokončí nastavení přístupu společnosti, zobrazí se zpráva, že je vše hotovo.

Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu. Kontaktní informace správce najdete na [webu Portál společnosti](https://portal.manage.microsoft.com).
