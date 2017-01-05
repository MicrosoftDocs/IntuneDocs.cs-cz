---
title: "Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení s Androidem v Intune? | Dokumentace Microsoftu"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d22f5aea-7be4-419b-b51b-a522ca037b69
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: d0e244659f8a78504ffa2a0b8a6579c829e3642b


---


# <a name="what-happens-if-you-install-the-company-portal-app-and-enroll-your-android-device-in-intune"></a>Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení s Androidem v Intune?

Když nainstalujete aplikaci Portál společnosti a potom v ní zaregistrujete své zařízení s Androidem v Intune, můžete v aplikaci Portál společnosti provádět tyto kroky:

-   Přístup k podnikové síti, e-mailu a pracovním souborům

-   Získání aplikací společnosti z Portálu společnosti

-   Automatické nastavení e-mailového účtu vaší společnosti

-   Obnovení továrního nastavení telefonu v případě ztráty nebo odcizení

Když zaregistrujete zařízení se systémem Android, udělujete správci IT oprávnění pro přístup k zařízení. Může provádět například následující akce:

-   Obnovit v zařízení výchozí tovární nastavení. To je užitečné v případě ztráty nebo odcizení zařízení.

-   Odebrat všechna data týkající se společnosti. Vaše osobní údaje a nastavení se při tom neodeberou.

-   Nastavit požadavky na zařízení, třeba vyžadovat heslo k zařízení nebo PIN kód a tím lépe chránit data společnosti. Správce IT může také omezit počet možných zadání nesprávného hesla. Když se tento počet překročí, může se zařízení zablokovat.

-   Vyžadovat, abyste přijali smluvní podmínky.

-   Zakázat používání fotoaparátu (jenom v zařízeních Samsung Knox, v zařízeních Nexus to nejde) a znemožnit vám tak pořizovat snímky důvěrných pracovních materiálů, které se nesmí sdílet.

-   Vynutit šifrování všech dat v zařízení a tím je lépe chránit v případě ztráty nebo odcizení zařízení.

Po přidání zařízení do aplikace Portál společnosti se přibližně každých 8 hodin provedou tyto akce:

-   Stažení všech zásad nebo aktualizací aplikací, které vám správce IT zpřístupnil

-   Odeslání všech aktualizací inventáře hardwaru. (Tyto aktualizace neobsahují osobní informace.)

-   Odeslání všech aktualizací inventáře aplikací společnosti. (Tyto aktualizace neobsahují osobní informace.)

Potřebujete pomoc? Obraťte se na správce IT (kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com)) nebo napište [týmu Microsoft Android](mailto:wintunedroidfbk@microsoft.com).



<!--HONumber=Dec16_HO2-->


