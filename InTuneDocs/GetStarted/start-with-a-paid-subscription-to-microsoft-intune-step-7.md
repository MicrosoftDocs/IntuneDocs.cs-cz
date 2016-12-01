---
title: "Přizpůsobení portálu společnosti | Microsoft Intune"
description: "Portál společnosti Intune uživatelům umožňuje provádění běžných úkolů, jako je registrace zařízení, instalace aplikací a vyhledávání informací o oddělení IT."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 15ef5c5b7f4c8aa2ceaa6867306e0e82a9835b02


---

# <a name="customize-the-company-portal"></a>Přizpůsobení portálu společnosti
Portál společnosti v Intune je místem, kde uživatelé přistupují k podnikovým datům a kde můžou dělat běžné úkoly, jako je registrace zařízení, instalace aplikací nebo vyhledání informací pro oddělení IT v případě žádosti o podporu.

Portál společnosti Intune nabízí uživatelům přístup k firemním datům a aplikacím. Portál společnosti je dostupný ve dvou formách:

-   **Aplikace Portál společnosti**: Aplikace, která je dostupná na zařízeních spravovaných službou Intune. Další informace o aplikacích Portál společnosti pro [Android](/Intune/EndUser/using-your-android-device-with-intune), [iOS](/Intune/EndUser/using-your-ios-or-mac-os-x-device-with-intune) a [Windows](/Intune/EndUser/using-your-windows-device-with-intune).


- **Web Portál společnosti**: Web, který koncovým uživatelům umožňuje provádět většinu úkolů, jaké můžou provádět z aplikace Portál společnosti. Adresa URL Portálu společnosti Intune je [http://portal.manage.microsoft.com](http://portal.manage.microsoft.com). Další informace o tomto webu najdete v tématu [Použití webu Portál společnosti Intune](/Intune/EndUser/using-the-intune-company-portal-website).

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

> [!NOTE]
> V některých zemích není aplikace Portál společnosti k dispozici.
> __iOS:__ Aplikace Portál společnosti pro iOS je vydaná ve [všech zemích, kde je dostupný](https://go.microsoft.com/fwlink/?linkid=831284) App Store pro zařízení Apple iOS.
> __Android__: Aplikace Portál společnosti pro Android v současnosti není dostupná v Číně. V těchto zemích použijte alternativní řešení, tzn. [nainstalujte aplikaci Portál společnosti ve verzi pro Android bokem](https://www.microsoft.com/en-us/download/details.aspx?id=49140).  

## <a name="customize-company-portal-settings"></a>Přizpůsobení nastavení Portálu společnosti
Přizpůsobení Portálu společnosti pomáhá poskytnout známé a užitečné prostředí pro koncové uživatele. Přihlaste se do [konzoly správce Microsoft Intune](https://manage.microsoft.com) jako tenant nebo správce služby, zvolte **Správce** &gt; **Portál společnosti** a nakonfigurujte nastavení portálu společnosti.

![admin-console-admin-workspace-comp-portal-settings](./media/companyportal.png)

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
    |Volba pozadí pro aplikaci portálu společnosti [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]|Toto nastavení má vliv jenom na pozadí aplikace Portál společnosti pro [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)].|


Po uložení změn můžete pomocí odkazů uvedených v dolní části stránky **Portál společnosti** v konzole pro správu zobrazit web Portál společnosti. Tyto odkazy se nedají změnit. Když se uživatel přihlásí, tyto odkazy zobrazí vaše předplatná v portálu společnosti.

### <a name="next-steps"></a>Další kroky
Gratulujeme! Právě jste dokončili krok 7 *úvodní příručky Intune*.
>[!div class="step-by-step"]

>[&larr; **Vytváření zásad a aplikací**](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)       [**Registrace zařízení** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)  



<!--HONumber=Nov16_HO4-->


