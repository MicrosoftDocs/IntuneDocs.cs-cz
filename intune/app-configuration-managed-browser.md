---
title: "Správa webového přístupu pomocí aplikace Managed Browser"
titlesuffix: Azure portal
description: "Nasazením aplikace Managed Browser, můžete omezit procházení webu a přenos dat z webu do jiných aplikací."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e536a31443a7140785a1f30af6fe676451e6f62c
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/20/2017
---
# <a name="manage-internet-access-using-managed-browser-policies-with-microsoft-intune"></a>Správa přístupu k internetu pomocí zásad aplikace Managed Browser v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Managed Browser je aplikace k procházení webu, kterou můžete po stažení z některého z veřejných obchodů s aplikacemi využívat ve své organizaci. Po nakonfigurování se službou Intune můžete v aplikaci Managed Browser:
- Přistupovat k firemním webům a aplikacím SaaS jednotným přihlašováním prostřednictvím služby MyApps. Data webů přitom zůstávají chráněná.
- Předem nakonfigurovat seznam adres URL a domén a určit tak, na jaké weby smí uživatel ve firemním prostředí přejít.
- Předem nakonfigurovat domovskou stránku a záložky.

Vzhledem k tomu, že je tato aplikace integrovaná s Intune SDK, můžete u ní také použít zásady ochrany aplikací, včetně:
- Řízení použití operací vyjmutí, kopírování a vložení
- Prevence pořizování snímků obrazovky
- Zajištění, že odkazy na obsah, na které uživatelé klikají, se otevřou jedině v ostatních spravovaných aplikacích.

Podrobnosti najdete v článku [Co jsou zásady ochrany aplikací](/intune/app-protection-policy).

Tato nastavení můžete použít na:

- Zařízení, která jsou zaregistrovaná v Intune
- Zaregistrovaná pomocí jiného produktu MDM
- Nespravovaná zařízení

Pokud si uživatelé nainstalují aplikaci Managed Browser z obchodu s aplikacemi a služba Intune ji nebude spravovat, mohou ji používat jako základní webový prohlížeč s podporou jednotného přihlašování přes web Microsoft MyApps. Uživatelé jsou přesměrováni přímo na web MyApps, kde uvidí všechny své zřízené aplikace SaaS.
Pokud aplikace Managed Browser není spravovaná službou Intune, nemá přístup k datům jiných takto spravovaných aplikací. 

Aplikace Managed Browser nepodporuje kryptografický protokol Secure Sockets Layer ve verzi 3 (SSLv3).

Zásady aplikace Managed Browser můžete vytvořit pro následující typy zařízení:

-   Zařízení se systémem Android 4 nebo novější verzí

-   Zařízení se systémem iOS 8.0 nebo novější verzí

>[!IMPORTANT]
>Od října 2017 aplikace Intune Managed Browser pro Android podporuje jenom zařízení se systémem Android 4.4 a novějším. Aplikace Intune Managed Browser pro iOS bude podporovat jen zařízení se systémem iOS 9.0 a novější.
>Starší verze systému Android a iOS budou moct Managed Browser dál používat, ale nepůjde do nich nainstalovat nové verze této aplikace a nebudou mít přístup ke všem jejím možnostem. Doporučujeme vám tato zařízení aktualizovat na podporovanou verzi operačního systému.


Intune Managed Browser podporuje otevírání webového obsahu od [partnerů nabízejících aplikace pro Microsoft Intune](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx).

## <a name="create-a-managed-browser-app-configuration"></a>Vytvoření konfigurace aplikace Managed Browser

1.  Přihlaste se k portálu Azure Portal.
2.  Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3.  V okně **Mobilní aplikace** v seznamu Spravovat zvolte **Zásady konfigurace aplikací**.
4.  V okně **Zásady konfigurace aplikací** zvolte **Přidat**.
5.  V okně **Přidat konfiguraci aplikace** zadejte **název** a volitelný **popis** nastavení konfigurace aplikace.
6.  Jako typ **Registrace zařízení** zvolte **Spravovaná zařízení** nebo **Spravované aplikace**.
7.  Zvolte možnost **Vyberte požadované aplikace** a potom v okně **Cílové aplikace** zvolte **Managed Browser** pro iOS, Android nebo oba systémy.
8.  Kliknutím na **OK** se vraťte do okna **Přidat konfiguraci aplikace**.
9.  Zvolte **Nastavení konfigurace**. V okně **Konfigurace** definujte dvojice klíč-hodnota, které budou určovat nastavení aplikace Managed Browser. Informace o různých párech klíč a hodnota, které můžete definovat, najdete v dalších částech tohoto článku.
10. Když jste hotovi, klikněte na **OK**.
11. V okně **Přidat konfiguraci aplikace** vyberte možnost **Vytvořit**.
12. Vytvoří se nová konfigurace, která se zobrazí v okně **Konfigurace aplikací**.

>[!IMPORTANT]
>V současné době aplikace Managed Browser spoléhá na automatickou registraci. Aby se konfigurace aplikace použily, musí už na zařízení být jiná aplikace spravovaná zásadami ochrany aplikací Intune.

## <a name="assign-the-configuration-settings-you-created"></a>Přiřazení vytvořeného nastavení aplikace

Nastavení přiřazujete skupinám uživatelů ve službě Azure AD. Pokud má daný uživatel aplikaci Managed Browser nainstalovanou, je spravována na základě vámi zadaného nastavení.

1. V okně **Nastavení** na řídicím panelu Správa mobilních aplikací Intune zvolte **Konfigurace aplikací**.
2. V seznamu konfigurací aplikací vyberte tu, kterou chcete přiřadit.
3. V dalším okně vyberte možnost **Skupiny uživatelů**.
4. V okně **Skupiny uživatelů** vyberte skupinu uživatelů ve službě Azure AD, které chcete přiřadit konfiguraci aplikace, a potom klikněte na **OK**.


## <a name="how-to-configure-application-proxy-settings-for-the-managed-browser"></a>Postup konfigurace nastavení proxy aplikací pro Managed Browser

Aplikaci Intune Managed Browser a [Proxy aplikací Azure AD]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) lze použít společně za účelem podpory následujících scénářů pro uživatele zařízení s iOSem nebo Androidem:

- Uživatel stáhne aplikaci Microsoft Outlook a přihlásí se do ní. Zásady ochrany aplikací Intune se automaticky použijí. Zašifrují uložená data a zablokují uživateli možnost přesouvat firemní soubory do nespravovaných aplikací nebo umístnění na zařízení. Když uživatel potom v Outlooku klikne na odkaz směřující na intranetový server, můžete nastavit, aby takový odkaz otevřel místo běžného prohlížeče aplikaci Managed Browser. Prohlížeč Managed Browser rozpozná, že tento intranetový server byl uživateli zpřístupněn prostřednictvím proxy aplikací. Uživatel je automaticky přesměrován prostřednictvím proxy aplikací, aby před zpřístupněním intranetového serveru provedl ověření pomocí příslušného vícefaktorového ověřování a podmíněného přístupu. Tento server, který nebylo dříve možné najít, když byl uživatel vzdálený, je nyní dostupný a odkaz v Outlooku funguje podle očekávání.
- Vzdálený uživatel otevře prohlížeč Managed Browser a přejde na intranetový server pomocí interní adresy URL. Prohlížeč Managed Browser rozpozná, že tento intranetový server byl uživateli zpřístupněn prostřednictvím proxy aplikací. Uživatel je automaticky přesměrován prostřednictvím proxy aplikací, aby před zpřístupněním intranetového serveru provedl ověření pomocí příslušného vícefaktorového ověřování a podmíněného přístupu. Tento server, který nebylo možné najít, když byl uživatel vzdálený, je nyní dostupný.

### <a name="before-you-start"></a>Než začnete

- Nastavte svoje interní aplikace prostřednictvím proxy aplikací Azure AD.
    - Postup konfigurace proxy aplikací a publikování aplikací najdete v [dokumentaci k instalaci]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started#how-to-get-started). 
    - Musíte používat minimálně verzi 1.2.0 aplikace Managed Browser.
    - Uživatelé prohlížeče Managed Browser mají k této aplikaci přiřazené [zásady ochrany aplikací Intune]( app-protection-policy.md).

#### <a name="step-1-enable-automatic-redirection-to-the-managed-browser-from-outlook"></a>Krok 1: Zapněte automatické přesměrování z Outlooku do prohlížeče Managed Browser.
Outlook musí být nakonfigurován zásadami ochrany aplikací, které povolují nastavení **Omezit webový obsah tak, aby se spouštěl v Managed Browseru**.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-managed-browser"></a>Krok 2: Přiřaďte zásady konfigurace aplikací přiřazené prohlížeči Managed Browser.
Tento postup nakonfiguruje prohlížeč Managed Browser tak, aby používal přesměrování proxy aplikací. Pomocí postupu pro vytvoření konfigurace aplikace Managed Browser zadejte následující dvojici klíč-hodnota:

|||
|-|-|
|Klíč|Hodnota|
|**com.microsoft.intune.mam.managedbrowser.AppProxyRedirection**|**true**|


## <a name="how-to-configure-the-homepage-for-the-managed-browser"></a>Postup konfigurace domovské stránky prohlížeče Managed Browser

Toto nastavení vám umožňuje nakonfigurovat domovskou stránku, kterou uživatelé uvidí, když prohlížeč Managed Browser spustí nebo když otevřou novou kartu. Pomocí postupu pro vytvoření konfigurace aplikace Managed Browser zadejte následující dvojici klíč-hodnota:

|||
|-|-|
|Klíč|Hodnota|
|**com.microsoft.intune.mam.managedbrowser.homepage**|Zadejte platnou adresu URL. Nesprávné adresy URL se z bezpečnostních důvodů blokují.<br>Příklad: **https://www.bing.com**|


## <a name="how-to-configure-bookmarks-for-the-managed-browser"></a>Postup konfigurace záložek prohlížeče Managed Browser

Toto nastavení vám umožňuje nakonfigurovat sadu záložek, které budou uživatelům prohlížeče Managed Browser k dispozici.

- Tyto záložky nemohou uživatelé odstranit ani upravit.
- Tyto záložky se zobrazí v horní části seznamu. Všechny záložky vytvořené uživateli se zobrazí pod těmito záložkami.
- Pokud jste povolili přesměrování Proxy aplikací, můžete přidat webové aplikace Proxy aplikací pomocí jejich interní nebo externí adresy URL.

Pomocí postupu pro vytvoření konfigurace aplikace Managed Browser zadejte následující dvojici klíč-hodnota:

|||
|-|-|
|Klíč|Hodnota|
|**com.microsoft.intune.mam.managedbrowser.bookmarks**|Hodnotou pro tuto konfiguraci je seznam záložek. Každou záložku tvoří název záložky a adresa URL záložky. Název a adresu URL oddělte znakem **&#124;**.<br><br>Příklad: **Microsoft Bing&#124;https://www.bing.com**<br><br>Pokud chcete nakonfigurovat více záložek, oddělte každý pár těmito dvěma znaky: **&#124;&#124;**.<br><br>Příklad: **Bing&#124;https://www.bing.com&#124;&#124;Contoso&#124;https://www.contoso.com**|

## <a name="how-to-specify-allowed-and-blocked-urls-for-the-managed-browser"></a>Určení povolených a blokovaných adres URL v aplikaci Managed Browser

Pomocí postupu pro vytvoření konfigurace aplikace Managed Browser zadejte následující dvojici klíč-hodnota:

|||
|-|-|
|Klíč|Hodnota|
|Vybírejte z těchto možností:<br><br>– Určení povolených adres URL (povoleny budou pouze tyto adresy a na jiné weby nebudou mít uživatelé přístup): **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br>– Určení blokovaných adres URL (na všechny ostatní weby budou mít uživatelé přístup): <br><br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**|Odpovídající hodnotou klíče je seznam adres URL. Zadejte všechny adresy, které chcete povolit nebo blokovat, jako jedinou hodnotu oddělenou znaky svislé čáry **&#124;**.<br><br>Příklady:<br><br>-**URL1&#124;URL2&#124;URL3**<br>-**http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com**|

>[!IMPORTANT]
>Nezadávejte oba klíče. Pokud budou oba klíče cílit na stejného uživatele, použije se klíč pro určení povolených adres, protože představuje nejvíce omezující možnost.
>Dále také zkontrolujte, že nejsou blokovány důležité weby, jako například webové stránky vaší organizace.

### <a name="url-format-for-allowed-and-blocked-urls"></a>Formát adresy URL pro povolené a blokované adresy URL
V následující části najdete informace o povolených formátech a zástupných znacích, které můžete použít při zadávání adres URL v seznamech povolených a blokovaných webů:

-   V souladu s následujícími pravidly můžete v seznamu povolených vzorů použít zástupný znak (**&#42;**).

-   Při zadávání adres URL do seznamu nezapomeňte u všech uvést předponu **http** nebo **https**.

-   V adrese můžete specifikovat čísla portů. Pokud nezadáte číslo portu, použijí se tyto hodnoty:

    -   Port 80 pro protokol HTTP

    -   Port 443 pro protokol HTTPS

    Použití zástupných znaků pro číslo portu se nepodporuje. Nepodporují se například **http&colon;//www&period;contoso&period;com:*;** a **http&colon;//www&period;contoso&period;com: /*;**.

-   Informace o povolených vzorech, které můžete použít při zadávání adres URL, najdete v následující tabulce:

|Adresa URL|Podrobnosti|Odpovídá|Neodpovídá|
|-------|---------------|-----------|------------------|
|http://www.contoso.com|Odpovídá jediné stránce|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
|http://contoso.com|Odpovídá jediné stránce|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
|http://www.contoso.com/&#42;|Odpovídá všem adresám URL začínajícím na www.contoso.com|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
|http://&#42;.contoso.com/&#42;|Odpovídá všem dílčím doménám domény contoso.com|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
|http://www.contoso.com/images|Odpovídá jediné složce|www.contoso.com/images|www.contoso.com/images/dogs|
|http://www.contoso.com:80|Odpovídá jediné stránce s použitím čísla portu|http://www.contoso.com:80|
|https://www.contoso.com|Odpovídá jediné zabezpečené stránce|https://www.contoso.com|http://www.contoso.com|
|http://www.contoso.com/images/&#42;|Odpovídá jediné složce a všem podsložkám|www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats|www.contoso.com/videos|

-   Tady jsou uvedené příklady některých vstupních hodnot, které nemůžete zadat:

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

## <a name="security-and-privacy-for-the-managed-browser"></a>Zabezpečení a ochrana osobních údajů v aplikaci Managed Browser

-   Aplikace Managed Browser nevyužívá nastavení, která uživatelé použijí pro prohlížeče integrované na jejich zařízeních. Aplikace Managed Browser nemá k těmto nastavením přístup.

-   Pokud v zásadách ochrany aplikací přidružených k prohlížeči Managed Browser nakonfigurujete možnost **Vyžadovat pro přístup jednoduchý PIN kód** nebo **Vyžadovat pro přístup podnikové přihlašovací údaje** a uživatel klikne na stránce ověřování na odkaz nápovědy, bude moct na internetu přejít na libovolný web, i když bude tento web v zásadách uvedený v seznamu blokovaných webů.

-   Aplikace Managed Browser může blokovat přístup k webům jen v případě, že se k nim přistupuje přímo. V případě, že se k webu přistupuje přes zprostředkující služby (třeba překladatelské služby), aplikace přístup neblokuje.

-   Kvůli povolení ověřování a přístupu k dokumentaci Intune adresa **&#42;.microsoft.com** v seznamech povolených a blokovaných webů nefiguruje. Je vždycky povolená.

### <a name="turn-off-usage-data"></a>Vypnutí dat o využití
Microsoft automaticky shromažďuje anonymní informace o výkonu a využití aplikace Managed Browser za účelem zlepšení svých produktů a služeb. Uživatelé můžou shromažďování těchto dat na svých zařízeních vypnout pomocí nastavení **Data o využití**. Nad shromažďováním těchto dat nemáte žádnou kontrolu.


-   V zařízeních se systémem iOS se nedají otevřít weby, u kterých vypršela platnost certifikátu nebo které mají nedůvěryhodný certifikát.
-   Aplikace Managed Browser nevyužívá nastavení, která uživatelé použijí pro prohlížeče integrované na jejich zařízeních. Aplikace Managed Browser nemá k těmto nastavením přístup.

-   Pokud v zásadách ochrany aplikací přidružených k prohlížeči Managed Browser nakonfigurujete možnost **Vyžadovat pro přístup jednoduchý PIN kód** nebo **Vyžadovat pro přístup podnikové přihlašovací údaje** a uživatel klikne na stránce ověřování na odkaz nápovědy, bude moct na internetu přejít na libovolný web, i když bude tento web v zásadách uvedený v seznamu blokovaných webů.

-   Aplikace Managed Browser může blokovat přístup k webům jen v případě, že se k nim přistupuje přímo. V případě, že se k webu přistupuje přes zprostředkující služby (třeba překladatelské služby), aplikace přístup neblokuje.

-   Kvůli povolení ověřování a přístupu k dokumentaci Intune adresa **&#42;.microsoft.com** v seznamech povolených a blokovaných webů nefiguruje. Je vždycky povolená.

### <a name="turn-off-usage-data"></a>Vypnutí dat o využití
Microsoft automaticky shromažďuje anonymní informace o výkonu a využití aplikace Managed Browser za účelem zlepšení svých produktů a služeb. Uživatelé můžou shromažďování těchto dat na svých zařízeních vypnout pomocí nastavení **Data o využití**. Nad shromažďováním těchto dat nemáte žádnou kontrolu.
