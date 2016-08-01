---
title: "Správa webového přístupu pomocí spravovaného prohlížeče | Microsoft Intune"
description: "Nasaďte aplikaci spravovaného prohlížeče, abyste omezili procházení webu a přenos dat z webu do jiných aplikací."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc946303-e09b-4d73-8bf4-87742299bc54
ms.reviewer: maxles
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c1850e89830de61ccdeb81cb6ee9cc0f0c1d237a
ms.openlocfilehash: 882042349c19ef0b688954577eb6519d0c0ac860


---

# Správa přístupu k internetu pomocí zásad spravované prohlížeče v Microsoft Intune
Spravovaný prohlížeč je aplikace procházení webu, kterou můžete nasadit v organizaci pomocí Microsoft Intune. Zásady spravovaného prohlížeče konfigurují seznam povolených nebo blokovaných webů. Tyto seznamy omezují weby, které můžou uživatelé spravovaného prohlížeče navštívit.

Vzhledem k tomu, že je tato aplikace spravovaná, můžete u ní použít taky zásady správy mobilních aplikací, jako je třeba řízení použití operací vyjmutí, kopírování a vložení, prevence pořizování snímků obrazovky nebo taky zajištění, že když uživatel klikne na odkaz, otevře se obsah v určených spravovaných aplikacích. Podrobnosti najdete v tématu [Konfigurace a nasazení zásad správy mobilních aplikací v konzole Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> [!IMPORTANT]
>Pokud uživatelé nainstalují spravovaný prohlížeč z App Storu a prohlížeč není spravován pomocí Intune, uplatňuje se následující chování: iOS – Aplikace spravovaného prohlížeče se dá používat jako základní webový prohlížeč, ale nebudou v ní dostupné některé funkce a nebude moct získat přístup k datům z jiných aplikací spravovaných pomocí Intune.
Android – Aplikace spravovaného prohlížeče se nedá používat.
Pokud uživatelé sami nainstalují spravovaný prohlížeč na zařízení s iOS starší verze než iOS 9, nebude spravovaný žádnými zásadami, které vytvoříte. Aby se zajistilo, že bude prohlížeč spravovat služba Intune, musí uživatelé aplikaci nejdřív odinstalovat a potom jim tuto aplikaci můžete nasadit jako spravovanou aplikaci. Pokud uživatel sám nainstaluje spravovaný prohlížeč v systému iOS 9 a novějším, zobrazí se mu výzva k povolení správy tohoto prohlížeče na základě zásad.

Zásady spravovaného prohlížeče můžete vytvořit pro následující typy zařízení:

-   Zařízení se systémem Android 4 nebo novější verzí

-   Zařízení se systémem iOS 7.1 nebo novější verzí

Intune Managed Browser podporuje otevírání webového obsahu od [partnerů aplikací Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

## Vytvoření zásady spravovaného prohlížeče

1.  V [konzole správce Microsoft Intune](https://manage.microsoft.com) klikněte na **Zásady** &gt; **Přidat zásadu**.

2.  Nakonfigurujte jeden z následujících typů zásad pro **Software** :

    -   **Zásady spravovaného prohlížeče (Android 4 a novější)**

    -   **Zásady spravovaného prohlížeče (iOS 7.1 a novější)**

    Další informace o vytvoření a nasazení zásad najdete v tématu [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  S konfigurací nastavení zásad spravovaného prohlížeče vám pomůže následující tabulka:

|Název nastavení|Podrobnosti|
    |----------------|--------------------|
    |**Název**|Zadejte jedinečný název zásady spravovaného prohlížeče, abyste ji mohli v konzole Intune snadno identifikovat.|
    |**Popis**|Zadejte popis, který bude shrnovat účel zásady spravovaného prohlížeče, a uveďte jakékoli další důležité informace, které vám pomůžou zásadu najít.|
    |**Povolte seznamu povolených nebo blokovaných webů omezovat adresy URL, které půjdou ve spravovaném prohlížeči otevřít.**|Vyberte jednu z následujících možností:<br /><br />**Povolit spravovanému prohlížeči otevření jenom dole vypsaných adres URL** – Určete seznam adres URL, které se dají ve spravovaném prohlížeči otevřít.<br /><br />**Blokovat spravovanému prohlížeči otevření dole vypsaných adres URL** – Určete seznam adres URL, které nepůjdou ve spravovaném prohlížeči otevřít z důvodu blokování. **Poznámka:** Do jedné zásady spravovaného prohlížeče nemůžete zahrnout seznam povolených i blokovaných adres URL.<br />Další informace o formátech adres URL, které se dají určit, najdete v části **Formát adres URL pro povolené a blokované adresy URL** v tomto tématu.|

4.  Po dokončení klikněte na **Uložit zásadu**.

Nová zásada se zobrazí v uzlu **Zásady konfigurace** pracovního prostoru **Zásady** .

## Vytvoření nasazení pro aplikaci spravovaného prohlížeče
Po vytvoření zásady spravovaného prohlížeče můžete vytvořit nasazení softwaru pro aplikaci spravovaného prohlížeče a přidružit ho k zásadě spravovaného prohlížeče, kterou jste vytvořili.

> [!IMPORTANT]
> Zásady spravovaného prohlížeče se nenasazují stejným způsobem jako ostatní zásady Intune. Tento typ zásad musí být přidružený k softwarovému balíčku spravovaného prohlížeče.

Nasaďte aplikaci a na stránce **Správa mobilních aplikací** vyberte zásadu spravovaného prohlížeče, kterou chcete k aplikaci přidružit.

Další informace o tom, jak nasadit aplikace, najdete v tématu [Nasazení aplikací v Microsoft Intune](deploy-apps-in-microsoft-intune.md).

## Zabezpečení a ochrana osobních údajů pro spravovaný prohlížeč

-   V zařízeních se systémem iOS se nedají otevřít weby, u kterých vypršela platnost certifikátu nebo které mají nedůvěryhodný certifikát.

-   Nastavení, která uživatelé vytvoří pro prohlížeče integrované na jejich zařízeních, spravovaný prohlížeč používat nebude. Důvodem je to, že spravovaný prohlížeč nemá k těmto nastavením přístup.

-   Pokud v zásadě správy mobilních aplikací přidružené ke spravovanému prohlížeči nakonfigurujete možnost **Požadovat pro přístup jednoduchý kód PIN** nebo **Požadovat pro přístup podnikové přihlašovací údaje** a uživatel klikne na stránce ověřování na odkaz nápovědy, bude moct na internetu přejít na libovolný web, i když bude tento web uvedený v zásadě spravovaného prohlížeče v seznamu blokovaných webů.

-   Spravovaný prohlížeč může blokovat přístup k webům jenom v případě, že se k nim přistupuje přímo. V případě, že se k webu přistupuje přes zprostředkující služby (třeba překladatelské služby), přístup blokovat nemůže.

-   Kvůli povolení ověřování a kvůli přístupu k dokumentaci Intune adresa **&#42;.microsoft.com** nefiguruje v nastavených seznamech povolených a blokovaných webů a je vždycky povolená.

### Vypnutí dat o využití
Microsoft automaticky shromažďuje anonymní informace o výkonu a využití spravovaného prohlížeče za účelem zlepšení svých produktů a služeb. Shromažďování dat ale můžou uživatelé vypnout v nastavení **Data o využití** na svém zařízení. Nad shromažďováním těchto dat nemáte žádnou kontrolu.

## Referenční informace

### Formát adresy URL pro povolené a blokované adresy URL
V následující části najdete informace o povolených formátech a zástupných znacích, které můžete použít při zadávání adres URL do seznamů povolených a blokovaných webů.

-   V souladu s pravidly uvedenými dole v seznamu povolených vzorů můžete použít zástupný znak **&#42;**.

-   Při zadávání adres URL do seznamu nezapomeňte u všech uvést předponu **http** nebo **https** .

-   V adrese můžete specifikovat čísla portů. Pokud nezadáte číslo portu, použijí se tyto hodnoty:

    -   Port 80 pro protokol HTTP

    -   Port 443 pro protokol HTTPS

    Použití zástupných znaků pro čísla portů se nepodporuje. Příklad: **http&colon;//www&period;contoso&period;com:*;** nebo **http&colon;//www&period;contoso&period;com: /*;**

-   Informace o povolených vzorech, které můžete použít při zadávání adres URL, najdete v následující tabulce:

|Adresa URL|Podrobnosti|Odpovídá|Neodpovídá|
    |-------|---------------|-----------|------------------|
    |http://www.contoso.com|Odpovídá jediné stránce|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
    |http://contoso.com|Odpovídá jediné stránce|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
    |http://www.contoso.com/&#42;|Odpovídá všem adresám URL začínajícím na www.contoso.com|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
    |http://&#42;.contoso.com/&#42;|Odpovídá všem dílčím doménám domény contoso.com|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
    |http://www.contoso.com/images|Odpovídá jediné složce|www.contoso.com/images|www.contoso.com/images/dogs|
    |http://www.contoso.com:80|Odpovídá jediné stránce používající číslo portu|http://www.contoso.com:80||
    |https://www.contoso.com|Odpovídá jediné zabezpečené stránce|https://www.contoso.com|http://www.contoso.com|
    |http://www.contoso.com/images/&#42;|Odpovídá jediné složce a všem podsložkám|www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats|www.contoso.com/videos|

-   Tady jsou uvedené příklady některých vstupních hodnot, které můžete zadat:

    -   &#42;.com

    -   &#42;.contoso/&#42;

    -   www.contoso.com/&#42;images

    -   www.contoso.com/&#42;images&#42;pigs

    -   www.contoso.com/page&#42;

    -   IP adresy

    -   https://&#42;

    -   http://&#42;

    -   http://www.contoso.com:&#42;

    -   http://www.contoso.com: /&#42;

### Řešení konfliktů mezi seznamy povolených a blokovaných webů
Pokud je na zařízení nasazených víc zásad spravovaného prohlížeče a dojde ke konfliktu nastavení, vyhodnotí se konflikty obou režimů (povoleného i blokovaného) a konflikty seznamů adres URL. V případě konfliktu platí následující pravidlo:

-   Pokud je u obou zásad stejný režim, ale liší se seznamy adres URL, příslušné adresy URL se na zařízení neuplatní.

-   Pokud má každá zásada jiný režim, ale seznamy adres URL jsou stejné, příslušné adresy URL se na zařízení neuplatní.

-   Pokud zařízení obdrží zásady spravovaného prohlížeče poprvé a dojde ke konfliktu dvou zásad, příslušné adresy URL se na zařízení neuplatní. K zobrazení konfliktů použijte uzel **Konflikty zásad** pracovního prostoru **Zásady** .

-   Pokud už zařízení zásady spravovaného prohlížeče obdrželo a nasazuje se druhá zásada s konfliktním nastavením, zůstanou na zařízení původní nastavení. K zobrazení konfliktů použijte uzel **Konflikty zásad** pracovního prostoru **Zásady** .



<!--HONumber=Jul16_HO3-->


