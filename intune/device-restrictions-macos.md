---
title: nastavení pro zařízení s macOS v Microsoft Intune – Azure | Dokumentace Microsoftu
titlesuffix: ''
description: Přidat, nakonfigurovat nebo vytvořit nastavení na zařízení s macOS omezení funkcí, včetně nastavení požadavky na heslo, ovládací prvek na uzamčené obrazovce, použijte integrované aplikace, přidejte s omezením pomocí specifikátoru nebo schválené aplikace, zpracovávat zařízeními bluetooth, připojit ke cloudu k zálohování a úložiště, povolte režim veřejného terminálu, přidejte domény a řídit, jak uživatelé pracují s webovým prohlížečem Safari v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 190facae36127a15f6df9f5fecfec9332ca06670
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742308"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>nastavení zařízení s macOS k povolení nebo zakázání funkcí pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek uvádí a popisuje různá nastavení, které můžete řídit na zařízeních s macOS. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete povolit nebo zakázat funkce, nastavte pravidla pro hesla, povolení nebo zakázání konkrétní aplikace a další.

Tato nastavení jsou přidány do konfiguračního profilu zařízení v Intune a potom přiřazené nebo nasazené na zařízení s macOS.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení omezení](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Obecné

- **Blokování ukládání obsahu do mezipaměti**: Zvolte **Nenakonfigurováno** (výchozí) povolit ukládání obsahu do mezipaměti. Ukládání obsahu do mezipaměti ukládá data aplikací, data webového prohlížeče, soubory ke stažení a další místně na zařízení. Vyberte **bloku** zabránit tato data ukládat do mezipaměti.

  Další informace o ukládání obsahu do mezipaměti v systému macOS najdete v tématu [spravovat ukládání obsahu do mezipaměti na počítači Mac](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (otevře jiný web).

  Tato funkce platí pro:  
  - macOS 10.13 a novější

- **Odložení aktualizací softwaru (jenom pod dohledem)**: Pokud je nastavena na **Nenakonfigurováno** (výchozí), aktualizací softwaru jsou zobrazeny na zařízení s Apple je uvolní. Například pokud aktualizace macOS získá vydané společností Apple v konkrétní den, pak tuto aktualizaci přirozeně zobrazuje v zařízení po datu vydání.

  **Povolit** umožňuje zpoždění při zobrazení aktualizací softwaru na zařízení z 0 – 90 dní. Toto nastavení nemá pod kontrolou, pokud aktualizace jsou nebo nejsou nainstalovány. 

  - **Zpoždění viditelnost aktualizací softwaru**: Zadejte hodnotu od 0 – 90 dní. Když vyprší platnost zpoždění, uživatelé získají oznámení, které nejstarší verzi operačního systému k dispozici při aktivaci zpoždění.

    Například, pokud je k dispozici v systému macOS aktualizace **1. ledna**, a **zpoždění viditelnost** je nastavena na **5 dní**, aktualizace není zobrazena jako k dispozici aktualizace na zařízení. Na **šestý den** po vydání, že je k dispozici aktualizace a koncoví uživatelé ji můžou nainstalovat.

    Tato funkce platí pro:  
    - macOS 10.13.4 a novější

## <a name="password"></a>Heslo

- **Heslo**: Vyžaduje, aby koncový uživatel zadal heslo pro přístup k zařízení.
  - **Vyžadovaný typ hesla**: Určete, jestli heslo můžete použít jenom číselné nebo je potřeba použít alfanumerické znaky (obsahuje písmena i číslice). Toto nastavení je podporované jenom v systému Mac OS X 10.10.3 a v novějších verzích.
  - **Počet nealfanumerických znaků v hesle**: Určete požadovaný počet složitých znaků v hesle (**0** až **4**).<br>Složitý znak je symbol, například **?**.
  - **Minimální délka hesla**: Zadejte minimální délku hesla uživatel musí nakonfigurovat (mezi **4** a **16** znaků).
  - **Jednoduchá hesla**: Umožněte použít jednoduchá hesla, jako je **0000** nebo **1234**.
  - **Maximální počet minut po uzamčení obrazovky před vyžádáním hesla**: Určete, jak dlouho musí být počítač neaktivní, aby k jeho odemčení bylo potřeba heslo.
  - **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**: Zadejte dobu, která musí být počítač nečinný, než se zamkne obrazovka.
  - **Vypršení platnosti hesla (dny)**: Určete, jak dlouho si může uživatel nechat stejné heslo, než ho bude muset změnit (**1** až **255** dnů).
  - **Zakázat opakované použití předchozích hesel**: Zadejte počet dříve použitých hesel, která se nesmí znovu použít, z **1** k **24**.

- **Heslo blokovat automatické vyplňování**: Zvolte **bloku** zabránit pomocí funkce Automatické vyplňování hesel v systému macOS. Výběr **bloku** má také následující dopadu:

  - Uživatelé vyzváni k použít heslo uložené v prohlížeči Safari nebo v jakékoli aplikace.
  - Automatické silná hesla jsou zakázána a silná hesla nejsou navržené pro uživatele.

  **Není nakonfigurováno** povoluje tyto funkce.

- **Blokovat požadavky blízkosti heslo**: Zvolte **bloku** tak zařízení uživatele není žádat hesla blízkými zařízeními. **Není nakonfigurováno** umožňuje tyto požadavky na heslo.

- **Blokovat sdílení hesla**: **Blok** zabraňuje sdílení hesla mezi zařízení pomocí AirDrop. **Není nakonfigurováno** umožňuje hesla ke sdílení.

## <a name="restricted-apps"></a>Omezené aplikace

V seznamu omezených aplikací můžete nakonfigurovat jeden z následujících seznamů:

- A **zakázané aplikace** seznamu: Seznam aplikací, nejsou spravované přes Intune, které nemají uživatelé dovolené nainstalovat a spustit. Uživatelé nebudou moct instalace zakázané aplikace, ale v takovém případě nahlásí se na správce.
- **Schválené aplikace** seznamu: Zobrazí seznam aplikací, které mají uživatelé dovoleno instalovat. Uživatelé nesmí instalovat aplikace, které nejsou uvedené. Aplikace, které spravuje Intune, jsou povolené automaticky. Uživatelé budou moci nainstalovat aplikaci, která není na seznamu schválených. Ale v takovém případě nahlásí se na správce.

Jestli chcete nakonfigurovat seznam, klikněte na **Přidat**, zadejte nějaký název, případně i vydavatele aplikace, a ID sady prostředků aplikace (například *com.apple.calculator*).

## <a name="domains"></a>Domény

### <a name="unmarked-email-domains"></a>Zrušení označení e-mailových domén

V poli **Adresa URL e-mailové domény** přidejte do seznamu minimálně jednu adresu URL. Když uživatelé dostanou e-mail z jiné domény než z té, kterou jste nakonfigurovali, označí se v aplikaci Mail v MacOS daný e-mail jako nedůvěryhodný.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Funkce a nastavení zařízení můžete taky omezit na [iOS](device-restrictions-ios.md) zařízení.