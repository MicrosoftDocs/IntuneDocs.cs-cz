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
ms.openlocfilehash: fcf71015d292ea22be1c818e526bc723b1af7165
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31017610"
---
# <a name="remove-your-device-from-management-if-you-declined-terms-of-use"></a>Odebrání zařízení ze správy při nepřijetí podmínek použití

Pokud při pokusu o přihlášení do aplikace Portál společnosti odmítnete přijmout podmínky použití, nebudou další pokusy o přihlášení k této aplikaci v budoucnosti možné. Proto musíte k odebrání zařízení z Intune použít alternativní postup.

Při odinstalaci aplikace Portál společnosti současně odebíráte zařízení z Intune. Vaše zařízení už nebude mít přístup k prostředkům společnosti. Další informace o důsledcích odebrání zařízení ze správy najdete v tématu [Co se stane, když zrušíte registraci zařízení v Intune](what-happens-if-you-unenroll-your-device-from-intune-android.md).

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


Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu (kontaktní údaje najdete na [webu Portál společnosti](https://portal.manage.microsoft.com#HelpDeskDialog)) nebo napište <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">týmu Microsoft Android</a>.
