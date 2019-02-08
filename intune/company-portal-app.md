---
title: Konfigurace aplikace Portál společnosti
titleSuffix: Microsoft Intune
description: Přečtěte si, jak je možné použít značku společnosti u aplikace Portál společnosti Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c5cf0504ab6a206508cbed4f09a131e5733eb54
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849053"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Konfigurace aplikace Portál společnosti služby Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Portál společnosti v Microsoft Intune je místo, odkud mají uživatelé přístup k firemním datům a kde můžou dělat běžné úkoly, jako je registrace zařízení, instalace aplikací nebo vyhledání informací pro oddělení IT v případě žádosti o podporu.        

> [!Tip]        
> Když si portál společnosti přizpůsobíte, bude se vaše konfigurace vztahovat na web portálu společnosti i na aplikace Portál společnosti. Všimněte si, že uživatelé musí mít pro přístup k webu portál společnosti přiřazenou licenci Intune.

Přizpůsobení Portálu společnosti pomáhá poskytnout známé a užitečné prostředí pro koncové uživatele. Postup: V úloze **Klientské aplikace** zvolte **Nastavení** > **Značky Portálu společnosti** a nakonfigurujte požadovaná nastavení.  

> [!Note]       
> Pokud používáte Azure Government, nabízí se protokoly aplikace koncovým uživatelům, aby se rozhodli o způsobu sdílení po inicializaci procesu získání pomoci s problémem. Pokud ale Azure Government nepoužíváte, Portál společnosti pro Windows 10 bude odesílat protokoly aplikace přímo Microsoftu, když uživatel iniciuje proces pro získání pomoci s problémem. Odesílání protokolů aplikace do Microsoftu usnadní řešení problémů. 

## <a name="company-information-and-privacy-statement"></a>Informace o společnosti a prohlášení o zásadách ochrany osobních údajů        
Název společnosti je zobrazen v záhlaví okna Portálu společnosti. Prohlášení o ochraně osobních údajů se zobrazí po kliknutí na odkaz na zásady ochrany osobních údajů.

Pole označená hvězdičkou (*) jsou povinná.       


| Název pole | Maximální délka | Další informace |
|---|---|---|
|**Název společnosti**| 40 | Tento název se zobrazí v záhlaví okna Portálu společnosti a bude se zobrazovat jako text během činnosti koncového uživatele Intune. |
| **Adresa URL prohlášení o zásadách ochrany osobních údajů** |     79     | Můžete přidat vlastní prohlášení o zásadách ochrany osobních údajů společnosti, které se uživatelům zobrazí po kliknutí na příslušné odkazy v Portálu společnosti. Musíte zadat platnou adresu URL ve formátu `<https://www.contoso.com>`. |

## <a name="support-information"></a>Informace o podpoře      
Zadejte informace o podpoře společnosti poskytnout vaši zaměstnanci mohli obrátit s dotazy související s Intune.          

|Název pole|Maximální délka|Další informace|
|---|---|---|
|**Jméno kontaktu** | 40 | Tento název se zobrazí na stránce **Kontakt na IT**. |
|**Telefonní číslo** | 20 | Toto číslo kontaktu se zobrazí na stránce **Kontaktovat IT**, aby vás zaměstnanci mohli kontaktovat se žádostí o podporu. |
|**E-mailová adresa**| 40 | Tato kontaktní adresa se zobrazí na stránce **Kontakt na IT**. Je potřeba zadat platnou e-mailovou adresu ve formátu `alias@domainname.com`. |
|**Název webu**| 40 | Toto je popisný název, který se zobrazí pro adresu URL webu podpory. Pokud zadáte adresu URL webu podpory bez popisného názvu, zobrazí se na stránce **Kontaktovat IT** na Portálu společnosti text Přejít na web IT. |
|**Adresa URL webu**| 150 | Pokud máte web podpory, který chcete, aby uživatelé používali, zadejte jeho adresu URL sem. Adresa URL musí být ve formátu `https://www.contoso.com`. Pokud adresu URL nezadáte, nezobrazí se na stránce **Kontakt na IT** v Portálu společnosti žádné informace o webu podpory. |
| **Další informace**| 120 | Zobrazí se na stránce **Kontakt na IT**. |


## <a name="company-identity-branding-customization"></a>Přizpůsobení brandingu firemní identity      
Portál své společnosti si můžete přizpůsobit – můžete na něj umístit logo své společnosti, uvést na něm název své společnosti a použít na něm barevný motiv a pozadí podle svých představ.     

### <a name="theme-color-and-logo-in-the-company-portal"></a>Barva motivu a logo na Portálu společnosti
Přiřaďte barvu motivu pro Portál společnosti. Vyberte standardní barvu nebo zadejte šestimístný šestnáctkový kód pro vlastní barvu.

|Název pole|Další informace|
|---|---|
|**Vyberte standardní barvu, nebo zadejte šestičíselný šestnáctkový kód**| Zvolte **standardní** vizuálně výběr barvy. Zvolte **Vlastní**, pokud chcete vybrat konkrétní barvu podle hodnoty šestnáctkového kódu.|
|**Zvolit barvu motivu**| Vyberte barvu motivu, kterou chcete použít pro Portál společnosti. Můžete ji vybrat ze standardní barvy nebo zadat konkrétní šestnáctkový kód. |
|**Zobrazení**| Vyberte, zda chcete zobrazit **Logo a název firmy**, **Jen logo firmy** nebo **Jen název firmy**. |
|**Nahrát firemní logo**|Tato možnost vám umožní nahrát vlastní firemní logo, které se bude zobrazovat na Portálu společnosti. Všimněte si, že barva textu se automaticky zvolí tak, aby byl zajištěn nejvyšší kontrast. Pokud chcete dosáhnout nejlepšího vzhledu, nahrajte logo s transparentním pozadím.<p><ul><li>Maximální velikost obrázku: 400px x 400px</li><li>Maximální velikost souboru: VĚTŠÍ NEŽ 750KB</li><li>Typ souboru: PNG, JPG nebo JPEG</li></ul>|

Po nahrání loga se v oblasti náhledu zobrazí logo s barvou motivu. Pokud jste si zvolili zobrazení názvu firmy, zobrazí se název na Portálu společnosti v černé nebo bílé barvě. Barva se zvolí automaticky tak, aby byl zajištěn nejvyšší kontrast s ohledem na barvu motivu. V oblasti náhledu na obrazovce se název vaší firmy nezobrazí. 

### <a name="logo-to-use-on-white-or-light-backgrounds"></a>Logo, které se použije na bílých nebo světlých pozadích
Zvolte logo, které bude nejlépe vypadat na bílých nebo světlých pozadích.

|Název pole|Další informace|
|---|---|
|**Nahrát logo**| Tato možnost je dostupná, pokud jste zvolili zobrazení loga společnosti. Pokud chcete dosáhnout nejlepšího vzhledu, nahrajte logo s transparentním pozadím.<p><ul><li>Maximální velikost obrázku: 400px x 400px</li><li>Maximální velikost souboru: VĚTŠÍ NEŽ 750KB</li><li>Typ souboru: PNG, JPG nebo JPEG</li></ul>|

### <a name="brand-image-for-company-portal"></a>Firemní logo pro Portál společnosti

Zobrazte si firemní logo, které odráží značku vaší společnosti. Po uložení změn můžete v horní části okna zvolit možnost **Podívejte se na náhled nastavení** na webovém portálu Intune, abyste viděli, jak budou konfigurace vypadat. Všimněte si, že náhled firemního loga uvidíte jenom na zařízení s iOSem, ale ne na webovém portálu Intune. 

|Název pole|Další informace|
|---|---|
|**Nahrát firemní logo**| Prostřednictvím této možnosti můžete povolit zobrazení obrázku na pozadí na stránce profilu uživatele v aplikaci Portál společnosti.<p>*Poznámka*: Na obrázku, může se zobrazit odlišně pro různé platformy.<p><ul><li>Doporučená šířka obrázku: Menší než 1125px, ale není menší než 640 pixelů</li><li>Maximální velikost obrázku: 1.3 MB</li><li>Typ souboru: PNG, JPG nebo JPEG</li></ul>|

Správné firemní logo může zvýšit důvěru uživatelů v aplikaci Portál společnosti tím, že prezentuje silný smysl pro vaši firemní značku. Nabízíme vám několik tipů, nad kterými byste se mohli zamyslet při pořizování, výběru a optimalizaci loga pro Portál společnosti. 

- Obraťte se na marketingové nebo kreativní oddělení. Možná už mají schválenou sadu značku Image. Mohli by vám také pomoci při optimalizaci obrázků. 

- Zvažte kompozici v orientaci jak na šířku, tak i na výšku. Ústřední bod obrázku by mělo obklopovat dostatečně velké pozadí. Na obrázku může oříznutí různě v závislosti na velikosti zařízení, orientace a platformu. 

- Nepoužívejte obecné obrázky převzaté z fotobanky. Obrázek by měl odrážet vaši firemní značku a měl by být pro uživatele srozumitelný. Pokud žádný obrázek nemáte, je lepší nepoužívat žádný, než použít obecný, který pro uživatele nemá žádný význam. 

- Odeberte nepotřebná metadata. Soubor obrázku může obsahovat metadata, jako jsou profil fotoaparátu, zeměpisná poloha, název, popisek a další. Pomocí nástroje pro optimalizaci obrázků tyto informace odstraňte, abyste zachovali kvalitu, ale vešli se do velikostního limitu souboru. 

Po image značky je přidán nebo změnili v Intune, nezobrazí koncového uživatele na zařízeních s Iosem změnu, dokud rozpoznal změnit v nabídce start se portál společnosti a potom byl restartován, a zobrazte obrázek značky. 

### <a name="brand-image-examples"></a>Příklady značky obrázku

Obrázek přizpůsobení prostředí značce pro iPad příklad na následujícím obrázku:

![Snímek obrazovky zařízení iPhone například obrázek přizpůsobení prostředí značce](media/company-portal-app/company-portal-app-03.png)

Obrázek přizpůsobení prostředí značce pro iPhone příklad na následujícím obrázku:

![Snímek obrazovky příklad iPad obrázek přizpůsobení prostředí značce](media/company-portal-app/company-portal-app-02.png)

## <a name="windows-company-portal-keyboard-shortcuts"></a>Klávesové zkratky v Portálu společnosti pro Windows

Koncoví uživatelé může aktivovat akce navigace, aplikace a zařízení v aplikaci portál společnosti Windows pomocí klávesových zkratek (akcelerátory).

V aplikaci Portál společnosti pro Windows jsou k dispozici následující klávesové zkratky.

| Oblast | Popis | Klávesová zkratka |
|:------------------:|:--------------:|:-----------------:|
| Navigační nabídka | Navigace | Alt+M |
|  | Domů | Alt+H |
|  | Všechny aplikace | ALT + A |
|  | Nainstalované aplikace | Alt+I |
|  | Váš názor | Alt+F |
|  | Můj profil | Alt+U |
|  | Nastavení | Alt+T |
| Úvodní stránka – dlaždice Zařízení | Přejmenovat | F2 |
|  | odebrat | Ctrl+D nebo Delete |
|  | Zkontrolovat přístup | Ctrl+M nebo F9 |
| Podrobnosti o zařízení | Přejmenovat | F2 |
|  | odebrat | Ctrl+D nebo Delete |
|  | Zkontrolovat přístup | Ctrl+M nebo F9 |
| Podrobnosti aplikace | Instalace | Ctrl+I |

Koncoví uživatelé budou také moct zobrazit dostupné klávesové zkratky v aplikaci portál společnosti pro Windows.

![Snímek obrazovky k dispozici klávesových zkratek v aplikaci portál společnosti Windows](media/company-portal-app/company-portal-app-01.png)

## <a name="next-steps"></a>Další postup

- [Ruční přidání aplikace Portál společnosti pro Windows 10 pomocí Microsoft Intune](store-apps-company-portal-app.md)
