---
title: "Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení s Windows v Intune? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
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
ms.sourcegitcommit: 4881d765a6a79d380ab6d3facdb55d9f0c81bf97
ms.openlocfilehash: ac4fdc73122fb5dc82771f174d9bd783c186bf9d


---


# Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení s Windows v Intune?

Když nainstalujete aplikaci Portál společnosti a pak přes ni zaregistrujete zařízení s Windows nebo Windows Phone, umožníte tím správci IT spravovat vaše zařízení a zajistit tak zabezpečení dat společnosti nebo školy, jak se pro zařízení starší než Windows 10 popisuje níže. Pokud máte zařízení s Windows 10, podívejte se na [tuto stránku](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## Co se stane všem zařízením s Windows po registraci
Registrace zařízení s Windows nebo Windows Phone v Intune nabízí tyto možnosti:

-   Přístup k podnikové síti, e-mailu a dalším pracovním souborům

-   Získání firemních aplikací z webu Portál společnosti (u systémů Windows 7 a Vista můžete získat firemní aplikace jenom z webu Portál společnosti)

-   Automatické nastavení e-mailového účtu vaší společnosti nebo školy

-   Obnovení továrního nastavení telefonu v případě ztráty nebo odcizení

Když zaregistrujete zařízení, udělujete správci IT oprávnění provést následující akce:

-   Obnovit v zařízení výchozí tovární nastavení. To je užitečné v případě ztráty nebo odcizení zařízení.

-   Odebrat obchodní aplikace a soubory, ale jenom takové, které jsou spojené se společností. **Vaše osobní údaje a nastavení se při tom neodeberou.**

-   Správce IT se může podívat na software nainstalovaný na zařízení a to i na software, který jste si nainstalovali sami.

-   Nastavit požadavky na zařízení, třeba mít heslo k zařízení nebo PIN kód k ochraně dat společnosti. Správce IT může taky omezit to, kolikrát můžete zadat špatné heslo. Když tento počet překročíte, může vám zařízení zablokovat.

-   Vyžadovat šifrování dat v zařízení kvůli ochraně dat společnosti v případě ztráty nebo odcizení zařízení. 

-   Vyžadovat, abyste přijali smluvní podmínky.

-   Zabránit pořizování snímků dat souvisejících se společností.

## Co se stane všem počítačům s Windows po registraci

-  Budete mít v počítači nainstalovaný software, prostřednictvím kterého bude moci správce IT počítač spravovat a díky kterému budete mít přístup k prostředkům společnosti, jako jsou aplikace a informace o podpoře. Správce IT může tento software automaticky aktualizovat.

-  V počítači může být nainstalovaná taky služba Intune Endpoint Protection. Tento software v počítači zjišťuje přítomnost virů a malwaru.

-  Správce IT může shromažďovat nebo odstraňovat data z pevného disku vašeho počítače.

-  Může do vašeho počítače instalovat aplikace a aktualizace.

## Co se stane každých 8 hodin po registraci zařízení
Přibližně každých osm hodin proběhne na zaregistrovaných zařízeních toto:

-   Stažení všech zásad nebo aktualizací aplikací, které vám správce IT zpřístupnil.

-   Odeslání všech aktualizací inventáře hardwaru.

-   Odeslání všech aktualizací inventáře aplikací společnosti.

Pokud máte otázky, na které byste potřebovali odpověď, obraťte se na správce IT. Jeho kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).




<!--HONumber=Sep16_HO4-->


