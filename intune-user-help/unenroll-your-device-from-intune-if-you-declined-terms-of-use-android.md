---
title: Odebrání zařízení ze správy při nepřijetí podmínek použití | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: dbf35b77c843b4dc084916b2c283b6c66d5f066d
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61505518"
---
# <a name="remove-your-device-from-management-if-you-declined-terms-of-use"></a>Odebrání zařízení ze správy při nepřijetí podmínek použití

Pokud při pokusu o přihlášení do aplikace Portál společnosti odmítnete přijmout podmínky použití, nebudou další pokusy o přihlášení k této aplikaci v budoucnosti možné. Proto musíte k odebrání zařízení z Intune použít alternativní postup.

Při odinstalaci aplikace Portál společnosti současně odebíráte zařízení z Intune. Vaše zařízení už nebude mít přístup k prostředkům společnosti. Další informace o tom, co se stane, když zařízení odeberete ze správy, najdete v tématu [Co se stane, když zrušíte registraci zařízení v Intune](what-happens-if-you-unenroll-your-device-from-intune-android.md).

Než odinstalujete aplikaci Portál společnosti, musíte přejít na nastavení **Správci zařízení** a vypnout **Portál společnosti**. Přesný postup se může mírně lišit v závislosti na tom, jako zařízení se systémem Android používáte.

## <a name="removing-the-device-from-the-company-portal-app"></a>Odebrání zařízení z aplikace Portál společnosti

Postup odebrání zařízení z Intune a odinstalace aplikace Portál společnosti:

1.  Přejděte na **Nastavení** &gt; **Zabezpečení &amp; Zamykací obrazovka** &gt; **Správci zařízení**.

    Provedením tohoto kroku okamžitě zrušíte registraci zařízení.

2.  Zrušte zaškrtnutí políčka vedle položky **Portál společnosti** nebo tuto položku vypněte.

    Teď můžete aplikaci Portál společnosti odinstalovat.

## <a name="removing-data-collected-by-the-company-portal-app"></a>Odebrání dat shromažďovaných aplikací Portál společnosti

Postup odebrání všech dat, která do zařízení uložila aplikace Portál společnosti pro Android:

  - V Aplikacích vymažte data aplikace -> klikněte na aplikaci -> tlačítko Vymazat data.
  - Odstraňte složku „\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal“.


Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu (kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980)) nebo napište <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">týmu Microsoft Android</a>.
