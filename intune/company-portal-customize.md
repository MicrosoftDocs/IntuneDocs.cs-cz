---
title: "Přizpůsobení portálu společnosti"
description: "Portál společnosti Intune uživatelům umožňuje provádění běžných úkolů, jako je registrace zařízení, instalace aplikací a vyhledávání informací o oddělení IT."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: e54f1a2ab0e62ab3ffcbf6fa1ae6f974c5f18717
ms.contentlocale: cs-cz
ms.lasthandoff: 06/08/2017


---

# <a name="customize-the-company-portal"></a>Přizpůsobení portálu společnosti

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

V tomto tématu najdou správci informace o tom, jak můžou přizpůsobit aplikaci a web Portál společnosti služby Intune.

Portál společnosti v Intune je místem, kde uživatelé přistupují k podnikovým datům a kde můžou dělat běžné úkoly, jako je registrace zařízení, instalace aplikací nebo vyhledání informací pro oddělení IT v případě žádosti o podporu.

Portál společnosti Intune nabízí uživatelům přístup k firemním datům a aplikacím. Portál společnosti je dostupný ve dvou formách:

-   **Aplikace Portál společnosti**: Aplikace, která je dostupná na zařízeních spravovaných službou Intune. Další informace o aplikacích Portál společnosti pro [Android](/intune-user-help/using-your-android-device-with-intune), [iOS](/intune-user-help/using-your-iOS-or-macOS-device-with-intune) a [Windows](/intune-user-help/using-your-windows-device-with-intune).


- **Web Portál společnosti**: Web, který koncovým uživatelům umožňuje provádět většinu úkolů, jaké můžou provádět z aplikace Portál společnosti. Adresa URL Portálu společnosti Intune je [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com). Další informace o tomto webu najdete v tématu [Použití webu Portál společnosti Intune](/intune-user-help/using-the-intune-company-portal-website).

> [!TIP]
> Když si portál společnosti přizpůsobíte, bude se vaše konfigurace vztahovat na web portálu společnosti i na aplikace Portál společnosti.

Některé úlohy, které uživatelé mohou provést na Portálu společnosti:

-   Registrovat zařízení
-   Zobrazit stav jejich zařízení
-   Resetovat svoje zařízení
-   Resetovat svoje heslo
-   Vzdáleně uzamknout svoje zařízení
-   Stahovat software nasazený vaší organizací
-   Kontaktovat oddělení IT se žádostí o podporu

## <a name="customize-company-portal-settings"></a>Přizpůsobení nastavení Portálu společnosti
Přizpůsobení Portálu společnosti pomáhá poskytnout známé a užitečné prostředí pro koncové uživatele. Přihlaste se do [konzoly správce Microsoft Intune](https://manage.microsoft.com) jako tenant nebo správce služby, zvolte **Správce** &gt; **Portál společnosti** a nakonfigurujte nastavení portálu společnosti.

## <a name="company-contact-information-and-privacy-statement"></a>Kontaktní informace společnosti a prohlášení o zásadách ochrany osobních údajů
Název společnosti je zobrazen v záhlaví okna Portálu společnosti. Kontaktní informace a podrobnosti se uživatelům zobrazí na obrazovce Kontakt na IT v Portálu společnosti. Prohlášení o ochraně osobních údajů se zobrazí po kliknutí na odkaz na zásady ochrany osobních údajů.

|Název pole|Maximální délka|Další informace|
    |----------|------------------------|----------------|
    |Název společnosti|40|Tento název se zobrazí v záhlaví okna Portálu společnosti.|
    |Jméno kontaktní osoby oddělení IT|40|Tento název se zobrazí na stránce **Kontakt na IT**.|
    |Telefonní číslo oddělení IT|20|Toto kontaktní číslo se zobrazí na stránce **Kontakt na IT**.|
    |E-mailová adresa oddělení IT|40|Tato kontaktní adresa se zobrazí na stránce **Kontakt na IT**. Je potřeba zadat platnou e-mailovou adresu ve formátu **alias@domainname.com**.|
    |Další informace|120|Zobrazí se na stránce **Kontakt na IT**.|
    |Adresa URL prohlášení o zásadách ochrany osobních údajů společnosti|79|Můžete přidat vlastní prohlášení o zásadách ochrany osobních údajů společnosti, které se uživatelům zobrazí po kliknutí na příslušné odkazy v Portálu společnosti. Pole musí obsahovat platnou adresu URL ve formátu https://www.contoso.com.|

## <a name="support-contacts"></a>Kontaktní údaje podpory
Web podpory je zobrazen uživatelům v Portálu společnosti, aby jim umožnil přístup k online podpoře.

|Název pole|Maximální délka|Další informace|
    |----------|------------------------|----------------|
    |Adresa URL webu podpory|150|Pokud máte web podpory, který chcete, aby uživatelé používali, zadejte jeho adresu URL sem. Adresa URL musí být ve formátu https://www.contoso.com. Pokud adresu URL nezadáte, nezobrazí se na stránce **Kontakt na IT** v Portálu společnosti žádné informace o webu podpory.|
    |Název webu|40|Toto je popisný název, který se zobrazí pro adresu URL webu podpory. Pokud zadáte adresu URL webu podpory bez popisného názvu, zobrazí se na stránce **Kontakt na IT** v Portálu společnosti text **Přejít na web IT**.|

## <a name="company-branding-customization"></a>Přizpůsobení obchodní značky
Portál své společnosti si můžete přizpůsobit – můžete na něj umístit logo své společnosti, uvést na něm název své společnosti a použít na něm barevný motiv a pozadí podle svých představ.

|Název pole|Další informace|
    |----------|----------------|
    |Barva motivu|Vyberte barvu motivu, kterou chcete použít pro Portál společnosti.|
    |Zahrnout logo společnosti|Povolení této možnosti vám umožní nahrát vlastní logo společnosti, které se bude zobrazovat v Portálu společnosti. Můžete nahrát dvě loga – jedno, které se zobrazí, když bude pozadí Portálu společnosti bílé, a druhé, které se zobrazí, když se bude pro pozadí Portálu společnosti používat vybraná barva motivu. Obě loga musí být ve formátu .png nebo .jpg o maximálním rozlišení 400 × 100 pixelů a nesmí být větší než 750 kB.|
    |Zvolit pozadí aplikace Portál společnosti pro Windows 8|Toto nastavení má vliv pouze na pozadí aplikace Portál společnosti pro Windows 8.|


Po uložení změn můžete pomocí odkazů uvedených v dolní části stránky **Portál společnosti** v konzole pro správu zobrazit web Portál společnosti. Tyto odkazy se nedají změnit. Když se uživatel přihlásí, tyto odkazy zobrazí vaše předplatná v Portálu společnosti.

