---
title: "Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení v Intune? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e52ebdd62ca68f1d9226def654961075400184a8
ms.openlocfilehash: e2da1f39d0cfe05bb0ea1c149c91e5ff82312c01


---


# Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení v Intune?

Informace o tom, co se stane po instalaci aplikace Portál společnosti a registraci zařízení, získáte prostřednictvím odkazu, který je zobrazen výše v části V tomto článku a který odpovídá používanému zařízení. Informace o zařízeních s Windows 10 najdete na [této stránce](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## Windows 8.1 a Windows RT
Když nainstalujete aplikaci portálu společnosti a pak v ní zaregistrujete své zařízení se systémem Windows 8.1 Enterprise nebo Professional nebo Windows RT do služby Intune, můžete v aplikaci Portál společnosti provádět tyto kroky:

-   Přístup k podnikové síti, e-mailu a dalším pracovním souborům

-   Získání aplikací společnosti z Portálu společnosti

-   Automatická konfigurace e-mailového účtu vaší společnosti

-   Obnovení továrního nastavení telefonu v případě ztráty nebo odcizení

Kroky registrace najdete v tématu [Registrace zařízení s Windows v Intune](enroll-your-device-in-intune-windows.md). Informace o tom, co váš správce IT uvidí a neuvidí na vašem zařízení, najdete v části [Co všechno uvidí správce IT, když zaregistruji své zařízení do služby Intune?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

Když přidáte počítač:

-   Budete mít v počítači nainstalovaný software, prostřednictvím kterého bude moci správce IT počítač spravovat a díky kterému budete mít přístup k prostředkům společnosti, jako jsou aplikace a informace o podpoře. Správce IT může tento software automaticky aktualizovat.

-   V počítači může být nainstalovaná taky služba Intune Endpoint Protection. Tento software v počítači zjišťuje přítomnost virů a malwaru.

-   Správce IT může inventarizovat veškerý software nainstalovaný v počítači, včetně softwaru, který jste doinstalovali vy.

-   Může se vyžadovat, abyste přijali smluvní podmínky.

-   Správce IT může shromažďovat nebo odstraňovat data z pevného disku vašeho počítače. Může dokonce odstranit celý obsah vašeho pevného disku.

-   Může do vašeho počítače instalovat aplikace a aktualizace.

-   Může ve vašem počítači vynutit dodržování určitých zásad. Například může vyžadovat, abyste si v počítači nastavili heslo nebo PIN kód, přičemž v případě příliš velkého počtu chybných pokusů o zadání hesla může dojít k zablokování počítače nebo odstranění všech dat z pevného disku počítače.

## Windows Phone 8.1 a Windows Phone 8
Když nainstalujete aplikaci Portál společnosti a potom v ní zaregistrujete své zařízení se systémem Windows Phone 8.1 nebo Windows Phone 8 do služby Intune, můžete v aplikaci Portál společnosti provádět tyto kroky:

-   Přístup k podnikové síti, e-mailu a dalším pracovním souborům

-   Získání aplikací společnosti z Portálu společnosti

-   Automatická konfigurace e-mailového účtu vaší společnosti

-   Obnovení továrního nastavení telefonu v případě ztráty nebo odcizení

Kroky registrace najdete v tématu [Registrace zařízení s Windows v Intune](enroll-your-device-in-intune-windows.md). Informace o tom, co váš správce IT uvidí a neuvidí na vašem zařízení, najdete v části [Co všechno uvidí správce IT, když zaregistruji své zařízení do služby Intune?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

Když přidáte zařízení Windows Phone, udělujete správci IT oprávnění k přístupu k zařízení. Může provádět například následující akce:

-   Obnovit v zařízení výchozí tovární nastavení. To je užitečné v případě ztráty nebo odcizení zařízení.

-   Odebrat veškerá firemní data a všechny nainstalované firemní aplikace. Vaše osobní údaje a nastavení se při tom neodeberou.

-   Požadovat, abyste si v zařízení nastavili heslo nebo PIN kód, přičemž v případě příliš velkého počtu chybných pokusů o zadání hesla může dojít k zablokování zařízení nebo obnovení zařízení do výchozího továrního nastavení.

-   Vynutit šifrování všech dat v zařízení. Tím jsou data chráněna v případě ztráty nebo odcizení zařízení.

-   Vyžadovat, abyste přijali smluvní podmínky.

-   Zakázat používání SD karet.

-   Instalovat do zařízení aktualizace aplikací. Platí pouze pro aktualizace. Správce IT nemůže vynutit instalace nových aplikací do vašeho zařízení, můžete si však podle vlastního výběru nainstalovat aplikace, které vidíte na portálu společnosti.

-   Jakmile je zařízení přidáno na portál společnosti, pak přibližně každých 8 hodin proběhne následující:

    -   Stažení všech zásad nebo aktualizací aplikací, které vám správce IT zpřístupnil.

    -   Odeslání všech aktualizací inventáře hardwaru.

    -   Odeslání všech aktualizací inventáře aplikací společnosti.

## Windows 7 a Vista
Když nainstalujete aplikaci Portál společnosti a potom v ní zaregistrujete své zařízení se systémem Windows 7 nebo Vista do služby Intune, můžete v aplikaci Portál společnosti provádět tyto kroky:

-   Přístup k podnikové síti, e-mailu a dalším pracovním souborům

-   Získání aplikací společnosti z Portálu společnosti

-   Automatická konfigurace e-mailového účtu vaší společnosti

-   Obnovení továrního nastavení telefonu v případě ztráty nebo odcizení

Informace o tom, co váš správce IT uvidí a neuvidí na vašem zařízení, najdete v části [Co všechno uvidí správce IT, když zaregistruji své zařízení do služby Intune?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

Když přidáte počítač:

-   Budete mít v počítači nainstalovaný software, prostřednictvím kterého bude moci správce IT počítač spravovat a díky kterému budete mít přístup k prostředkům společnosti, jako jsou aplikace a informace o podpoře. Správce IT může tento software automaticky aktualizovat.

-   V počítači může být nainstalovaná taky služba Intune Endpoint Protection. Tento software v počítači zjišťuje přítomnost virů a malwaru.

-   Správce IT může inventarizovat veškerý software nainstalovaný v počítači, včetně softwaru, který jste doinstalovali vy.

-   Může se vyžadovat, abyste přijali smluvní podmínky.

-   Správce IT může shromažďovat nebo odstraňovat data z pevného disku vašeho počítače. Může dokonce odstranit celý obsah vašeho pevného disku.

-   Může do vašeho počítače instalovat aplikace a aktualizace.

-   Může ve vašem počítači vynutit dodržování určitých zásad. Například může vyžadovat, abyste si v počítači nastavili heslo nebo PIN kód, přičemž v případě příliš velkého počtu chybných pokusů o zadání hesla může dojít k zablokování počítače nebo odstranění všech dat z pevného disku počítače.

Pokud máte otázky, na které byste potřebovali odpověď, obraťte se na správce IT. Jeho kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).

### Související témata
[Použití zařízení Windows s Intune](using-your-windows-device-with-intune.md)



<!--HONumber=Jun16_HO5-->


