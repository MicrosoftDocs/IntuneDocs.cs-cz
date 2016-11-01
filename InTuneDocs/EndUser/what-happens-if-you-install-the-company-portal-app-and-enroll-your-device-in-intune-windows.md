---
title: "Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení s Windows v Intune? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fd54ec104a26ebae845dfe3942dac2e8d9dae4a9
ms.openlocfilehash: 678ef01b215442e3d767a38388a579c6ee329975


---


# Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení s Windows v Intune?

Když nainstalujete aplikaci Portál společnosti a pak přes ni zaregistrujete zařízení s Windows nebo Windows Phone, umožníte tím správci IT spravovat vaše zařízení a zajistit tak vyšší zabezpečení dat společnosti. Toto téma popisuje, co se stane u zařízení se systémem starším než Windows 10. Informace pro zařízení s Windows 10 najdete v [souvisejícím tématu](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## Co se stane všem zařízením s Windows po registraci
Registrace zařízení s Windows nebo Windows Phone v Intune nabízí tyto možnosti:

-   Přístup k podnikové síti, e-mailu a pracovním souborům

-   Získání aplikací společnosti z webu Portál společnosti (Aplikace společnosti pro systém Windows 7 a Windows Vista je možné získat jenom z webu Portál společnosti.)

-   Automatické nastavení e-mailového účtu vaší společnosti nebo školy

-   Obnovení továrního nastavení telefonu v případě ztráty nebo odcizení

Když zaregistrujete zařízení, udělujete správci IT oprávnění provést následující akce:

-   Obnovit v zařízení výchozí tovární nastavení. To je užitečné v případě ztráty nebo odcizení zařízení.

-   Odebrat obchodní aplikace a soubory, ale jenom takové, které jsou spojené se společností. *Vaše osobní údaje a nastavení se při tom neodeberou.*

-   Správce IT může vidět software nainstalovaný v zařízení, a to i software, který jste si nainstalovali sami.

-   Nastavit požadavky na zařízení, třeba vyžadovat heslo k zařízení nebo PIN kód a tím lépe chránit data společnosti. Správce IT může také omezit počet možných zadání nesprávného hesla. Když se tento počet překročí, může se zařízení zablokovat.

-   Vyžadovat šifrování dat v zařízení kvůli ochraně dat společnosti v případě ztráty nebo odcizení zařízení.

-   Vyžadovat, abyste přijali smluvní podmínky.

-   Zabránit pořizování snímků dat souvisejících se společností.

## Co se stane všem počítačům s Windows po registraci

-  Do vašeho počítače se nainstaluje software, který správci IT umožní spravovat daný počítač a vám umožní přístup k prostředkům společnosti, jako jsou aplikace a informace o podpoře. Správce IT může tento software automaticky aktualizovat.

-  Do vašeho počítače se může nainstalovat služba Intune Endpoint Protection. Tento software vyhledává viry a malware.

-  Správce IT může shromažďovat nebo odstraňovat data z pevného disku vašeho počítače.

-  Správce IT může do vašeho počítače instalovat aplikace a aktualizace.

## Co se stane každých 8 hodin po registraci zařízení
Přibližně každých osm hodin proběhne na zaregistrovaných zařízeních toto:

-   Stažení všech zásad nebo aktualizací aplikací, které vám správce IT zpřístupnil

-   Odeslání všech aktualizací inventáře hardwaru.

-   Odeslání všech aktualizací inventáře aplikací společnosti.

Pokud máte otázky, na které byste potřebovali odpověď, obraťte se na správce IT. Jeho kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).



<!--HONumber=Oct16_HO2-->


