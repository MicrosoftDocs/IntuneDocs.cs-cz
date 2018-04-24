---
title: Konfigurace aplikace Portál společnosti
titleSuffix: Microsoft Intune
description: Přečtěte si, jak je možné použít značku společnosti u aplikace Portál společnosti Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aed2bec6e6fea40fdbd78bc487896d167d036f06
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Konfigurace aplikace Portál společnosti služby Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Portál společnosti v Microsoft Intune je místo, odkud mají uživatelé přístup k firemním datům a kde můžou dělat běžné úkoly, jako je registrace zařízení, instalace aplikací nebo vyhledání informací pro oddělení IT v případě žádosti o podporu.        

> [!Tip]        
> Když si portál společnosti přizpůsobíte, bude se vaše konfigurace vztahovat na web portálu společnosti i na aplikace Portál společnosti.       

Přizpůsobení Portálu společnosti pomáhá poskytnout známé a užitečné prostředí pro koncové uživatele. Postup: V úloze **Mobilní aplikace** zvolte **Nastavení** > **Značky Portálu společnosti** a nakonfigurujte požadovaná nastavení.      

## <a name="company-contact-information-and-privacy-statement"></a>Kontaktní informace společnosti a prohlášení o zásadách ochrany osobních údajů        
Název společnosti je zobrazen v záhlaví okna Portálu společnosti. Kontaktní informace a podrobnosti se uživatelům zobrazí na obrazovce **Kontaktovat IT** na Portálu společnosti. Prohlášení o ochraně osobních údajů se zobrazí po kliknutí na odkaz na zásady ochrany osobních údajů.        


|                   Název pole                   | Maximální délka |                                                                                                 Další informace                                                                                                 |
|------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         <strong>Název společnosti</strong>          |     40     |                                                                            Tento název se zobrazí v záhlaví okna Portálu společnosti.                                                                            |
|  <strong>Jméno kontaktní osoby oddělení IT</strong>   |     40     |                                                                         Tento název se zobrazí na stránce <strong>Kontakt na IT</strong>.                                                                          |
|  <strong>Telefonní číslo oddělení IT</strong>   |     20     |                                                                    Toto kontaktní číslo se zobrazí na stránce <strong>Kontakt na IT</strong>.                                                                     |
|  <strong>E-mailová adresa IT oddělení</strong>  |     40     |                       Tato kontaktní adresa se zobrazí na stránce <strong>Kontakt na IT</strong>. Je potřeba zadat platnou e-mailovou adresu ve formátu <strong>alias@domainname.com</strong>.                       |
|    <strong>Další informace</strong>     |    120     |                                                                                Zobrazí se na stránce <strong>Kontakt na IT</strong>.                                                                                |
| <strong>Adresa URL prohlášení o ochraně osobních údajů společnosti</strong> |     79     | Můžete přidat vlastní prohlášení o zásadách ochrany osobních údajů společnosti, které se uživatelům zobrazí po kliknutí na příslušné odkazy v Portálu společnosti. Pole musí obsahovat platnou adresu URL ve formátu <strong><https://www.contoso.com></strong>. |

## <a name="support-contacts"></a>Kontaktní údaje podpory     
Web podpory je zobrazen uživatelům v Portálu společnosti, aby jim umožnil přístup k online podpoře.        



|Název pole|Maximální délka|Další informace|        
|-|-|-|     
|**Adresa URL webu podpory**|150|Pokud máte web podpory, který chcete, aby uživatelé používali, zadejte jeho adresu URL sem. Adresa URL musí být ve formátu **https://www.contoso.com**. Pokud adresu URL nezadáte, nezobrazí se na stránce **Kontakt na IT** v Portálu společnosti žádné informace o webu podpory.|        
|**Název webu podpory**|40|Toto je popisný název, který se zobrazí pro adresu URL webu podpory. Pokud zadáte adresu URL webu podpory bez popisného názvu, zobrazí se na stránce **Kontaktovat IT** na Portálu společnosti text Přejít na web IT.       

## <a name="company-branding-customization"></a>Přizpůsobení obchodní značky       
Portál své společnosti si můžete přizpůsobit – můžete na něj umístit logo své společnosti, uvést na něm název své společnosti a použít na něm barevný motiv a pozadí podle svých představ.     



|Název pole|Další informace|       
|-|-|       
|**Barva motivu**|Vyberte barvu motivu, kterou chcete použít pro Portál společnosti. Můžete ji vybrat z editoru barev nebo zadat konkrétní šestnáctkový kód.|      
|**Zobrazit logo společnosti**|Povolení této možnosti vám umožní nahrát vlastní logo společnosti, které se bude zobrazovat v Portálu společnosti. Můžete nahrát dvě loga – jedno, které se zobrazí, když bude pozadí Portálu společnosti bílé, a druhé, které se zobrazí, když se bude pro pozadí Portálu společnosti používat vybraná barva motivu. Obě loga musí být ve formátu .png nebo .jpg o maximálním rozlišení 400 × 100 pixelů a nesmí být větší než 750 kB.<br>Vedle nahraného loga můžete zobrazit také název společnosti, který jste zadali.|      

Po uložení změn můžete zvolit možnost **Podívejte se na náhled nastavení na webovém portálu Intune**, abyste viděli, jak konfigurace vypadá.
