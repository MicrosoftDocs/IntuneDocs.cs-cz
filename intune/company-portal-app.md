---
title: Konfigurace aplikace Portál společnosti
titleSuffix: Microsoft Intune
description: Přečtěte si, jak je možné použít značku společnosti u aplikace Portál společnosti Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4535bdfa9b801c605c70c0a9dad900d76044eab4
ms.sourcegitcommit: c78923b0d5b320322c828b1bbea2deb9062e30d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/05/2018
ms.locfileid: "37844976"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Konfigurace aplikace Portál společnosti služby Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Portál společnosti v Microsoft Intune je místo, odkud mají uživatelé přístup k firemním datům a kde můžou dělat běžné úkoly, jako je registrace zařízení, instalace aplikací nebo vyhledání informací pro oddělení IT v případě žádosti o podporu.        

> [!Tip]        
> Když si portál společnosti přizpůsobíte, bude se vaše konfigurace vztahovat na web portálu společnosti i na aplikace Portál společnosti.       

Přizpůsobení Portálu společnosti pomáhá poskytnout známé a užitečné prostředí pro koncové uživatele. Postup: V úloze **Mobilní aplikace** zvolte **Nastavení** > **Značky Portálu společnosti** a nakonfigurujte požadovaná nastavení.  

> [!Note]       
> Portál společnosti pro Windows 10 teď odesílá protokoly aplikace přímo Microsoftu, když uživatel iniciuje pracovní postup pro získání pomoci s problémem. Usnadní se tak řešení problémů, které jsou předávány Microsoftu.  

## <a name="company-information-and-privacy-statement"></a>Informace o společnosti a prohlášení o zásadách ochrany osobních údajů        
Název společnosti je zobrazen v záhlaví okna Portálu společnosti. Prohlášení o ochraně osobních údajů se zobrazí po kliknutí na odkaz na zásady ochrany osobních údajů.

Pole označená hvězdičkou (*) jsou povinná.       


| Název pole | Maximální délka | Další informace |
|---|---|---|
|**Název společnosti**| 40 | Tento název se zobrazí v záhlaví okna Portálu společnosti a bude se zobrazovat jako text během činnosti koncového uživatele Intune. |
| **Adresa URL prohlášení o zásadách ochrany osobních údajů** |     79     | Můžete přidat vlastní prohlášení o zásadách ochrany osobních údajů společnosti, které se uživatelům zobrazí po kliknutí na příslušné odkazy v Portálu společnosti. Musíte zadat platnou adresu URL ve formátu `<https://www.contoso.com>`. |

## <a name="support-information"></a>Informace o podpoře      
Zadejte informace o podpoře vaší společnosti a poskytněte tak zaměstnanci kontakt, na který se může obrátit s dotazy o Intune.       

|Název pole|Maximální délka|Další informace|
|---|---|---|
|**Jméno kontaktu** | 40 | Tento název se zobrazí na stránce **Kontakt na IT**. |
|**Telefonní číslo** | 20 | Toto číslo kontaktu se zobrazí na stránce **Kontaktovat IT**, aby vás zaměstnanci mohli kontaktovat se žádostí o podporu. |
|**E-mailová adresa**| 40 | Tato kontaktní adresa se zobrazí na stránce **Kontakt na IT**. Je potřeba zadat platnou e-mailovou adresu ve formátu `alias@domainname.com`. |
|**Název webu**| 40 | Toto je popisný název, který se zobrazí pro adresu URL webu podpory. Pokud zadáte adresu URL webu podpory bez popisného názvu, zobrazí se na stránce **Kontaktovat IT** na Portálu společnosti text Přejít na web IT. |
|**Adresa URL webu**| 150 | Pokud máte web podpory, který chcete, aby uživatelé používali, zadejte jeho adresu URL sem. Adresa URL musí být ve formátu `https://www.contoso.com`. Pokud adresu URL nezadáte, nezobrazí se na stránce **Kontakt na IT** v Portálu společnosti žádné informace o webu podpory. |
| **Další informace**| 120 | Zobrazí se na stránce **Kontakt na IT**. |


## <a name="company-branding-customization"></a>Přizpůsobení obchodní značky       
Portál své společnosti si můžete přizpůsobit – můžete na něj umístit logo své společnosti, uvést na něm název své společnosti a použít na něm barevný motiv a pozadí podle svých představ.     

### <a name="theme-color"></a>Barva motivu
Přiřaďte barvu motivu pro Portál společnosti. Vyberte standardní barvu nebo zadejte šestimístný šestnáctkový kód pro vlastní barvu.

|Název pole|Další informace|
|---|---|
|**Typ barvy**| Vyberte barvu motivu, kterou chcete použít pro Portál společnosti. Můžete ji vybrat ze standardní barvy nebo zadat konkrétní šestnáctkový kód. |
|**Zvolte barvu** nebo **Šestnáctkový kód barvy**| Vyberte barvu motivu, kterou chcete použít pro Portál společnosti. Můžete ji vybrat ze standardní barvy nebo zadat konkrétní šestnáctkový kód. Tyto možnosti jsou dostupné na základě možnosti **Typ barvy**, kterou jste vybrali.  |

### <a name="company-logo"></a>Logo společnosti
Nahrajte logo vaší společnosti, které bude viditelné během činnosti koncového uživatele Intune.

|Název pole|Další informace|
|---|---|
|**Zobrazit logo společnosti**|Povolení této možnosti vám umožní nahrát vlastní logo společnosti, které se bude zobrazovat v Portálu společnosti. Můžete nahrát dvě loga – jedno, které se zobrazí, když bude pozadí Portálu společnosti bílé, a druhé, které se zobrazí, když se bude pro pozadí Portálu společnosti používat vybraná barva motivu. |
|**Nahrajte logo, které chcete použít na tmavém pozadí**| Tato možnost je dostupná, pokud jste zvolili zobrazení loga společnosti. Logo musí být ve formátu .png nebo .jpg o maximálním rozlišení 400 × 400 pixelů a nesmí být větší než 750 kB. |
|**Nahrajte logo, které chcete použít na světlém pozadí**| Tato možnost je dostupná, pokud jste zvolili zobrazení loga společnosti. Logo musí být ve formátu .png nebo .jpg o maximálním rozlišení 400 × 400 pixelů a nesmí být větší než 750 kB. |
|**Vedle loga zobrazit název společnosti**| Když vyberete tuto možnost, zobrazí se vedle nahraného loga název společnosti, který jste zadali. |

Po uložení změn můžete v horní části okna zvolit možnost **Podívejte se na náhled nastavení na webovém portálu Intune**, abyste viděli, jak bude konfigurace vypadat.
