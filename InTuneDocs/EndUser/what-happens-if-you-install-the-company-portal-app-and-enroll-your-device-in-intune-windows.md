---
title: "Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení s Windows v Intune? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 7/8/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3a2daebdb781ce99aa103e7717ffa1b0297cb3a
ms.openlocfilehash: 840d985fd2c4771831f722cdff214026a383f606


---


# Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení s Windows v Intune?

Když nainstalujete aplikaci Portálu společnosti a pak ji použijete k registraci zařízení s Windows nebo Windows Phone, povolíte správci IT spravovat zařízení, aby byla data společnosti nebo školy udržována v bezpečí, jak je popsáno dál pro zařízení starší než Windows 10. Informace o zařízeních s Windows 10 najdete na [této stránce](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## Co se stane všem zařízením s Windows po registraci
Po registraci zařízení s Windows nebo Windows Phone v Intune získáte tyto možnosti:

-   Přístup k podnikové síti, e-mailu a dalším pracovním souborům

-   Získání firemních aplikací z webu Portál společnosti (u systémů Windows 7 a Vista můžete získat firemní aplikace jenom z webu Portál společnosti)

-   Automatická konfigurace e-mailového účtu vaší společnosti nebo školy

-   Obnovení továrního nastavení telefonu v případě ztráty nebo odcizení

Když zaregistrujete zařízení, udělujete správci IT oprávnění provést následující akce:

-   Obnovit v zařízení výchozí tovární nastavení. To je užitečné v případě ztráty nebo odcizení zařízení.

-   Odebrat veškerá firemní data a všechny nainstalované firemní aplikace. Vaše osobní údaje a nastavení se při tom neodeberou.

-   Správce IT může inventarizovat veškerý software nainstalovaný v počítači, včetně softwaru, který jste doinstalovali vy.

-   Požadovat, abyste si v zařízení nastavili heslo nebo PIN kód, přičemž v případě příliš velkého počtu chybných pokusů o zadání hesla může dojít k zablokování zařízení nebo obnovení zařízení do výchozího továrního nastavení.

-   Vynutit šifrování všech dat v zařízení, což pomáhá chránit data v případě ztráty nebo odcizení zařízení.

-   Vyžadovat, abyste přijali smluvní podmínky.

-   Může ve vašem počítači vynutit dodržování určitých zásad. Například může vyžadovat, abyste si v počítači nastavili heslo nebo PIN kód, přičemž v případě příliš velkého počtu chybných pokusů o zadání hesla může dojít k zablokování počítače nebo odstranění všech dat z pevného disku počítače.

-   Zakázat používání SD karet.

## Co se stane všem počítačům s Windows po registraci

-  Budete mít v počítači nainstalovaný software, prostřednictvím kterého bude moci správce IT počítač spravovat a díky kterému budete mít přístup k prostředkům společnosti, jako jsou aplikace a informace o podpoře. Správce IT může tento software automaticky aktualizovat.

-  V počítači může být nainstalovaná taky služba Intune Endpoint Protection. Tento software v počítači zjišťuje přítomnost virů a malwaru.

-  Správce IT může inventarizovat veškerý software nainstalovaný v počítači, včetně softwaru, který jste doinstalovali vy.

-  Může se vyžadovat, abyste přijali smluvní podmínky.

-  Správce IT může shromažďovat nebo odstraňovat data z pevného disku vašeho počítače. Může také odstranit celý obsah vašeho pevného disku.

-  Může do vašeho počítače instalovat aplikace a aktualizace.

-  Může ve vašem počítači vynutit dodržování určitých zásad. Například může vyžadovat, abyste si v počítači nastavili heslo nebo PIN kód, přičemž v případě příliš velkého počtu chybných pokusů o zadání hesla může dojít k zablokování počítače nebo odstranění všech dat z pevného disku počítače.


## Co se stane každých 8 hodin po registraci zařízení
Přibližně každých 8 hodin se na zaregistrovaných zařízeních provede následující:

-   Stažení všech zásad nebo aktualizací aplikací, které vám správce IT zpřístupnil.

-   Odeslání všech aktualizací inventáře hardwaru.

-   Odeslání všech aktualizací inventáře aplikací společnosti.

Kroky registrace najdete v tématu [Registrace zařízení s Windows v Intune](enroll-your-device-in-intune-windows.md). Informace o tom, co váš správce IT uvidí a neuvidí na vašem zařízení, najdete v části [Co všechno uvidí správce IT, když zaregistruji své zařízení do služby Intune?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

Pokud máte otázky, na které byste potřebovali odpověď, obraťte se na správce IT. Jeho kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).

### Související témata
[Použití zařízení Windows s Intune](using-your-windows-device-with-intune.md)



<!--HONumber=Aug16_HO4-->


