---
title: Správa webového přístupu pomocí aplikace Managed Browser
titlesuffix: Microsoft Intune
description: Nasazením aplikace Managed Browser můžete omezit procházení webu a přenos dat z webu do jiných aplikací.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 742173c1ef53337dab35694c0c04cbca60dbb07c
ms.sourcegitcommit: 54fc806036f84a8667cf8f74086358bccd30aa7d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/20/2018
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

Podrobnosti najdete v článku [Co jsou zásady ochrany aplikací](/intune/app-protection-policy.md).

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


Intune Managed Browser podporuje otevírání webového obsahu od [partnerů nabízejících aplikace pro Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

## <a name="conditional-access-for-the-intune-managed-browser"></a>Podmíněný přístup pro aplikaci Intune Managed Browser

Managed Browser je nově schválenou klientskou aplikací pro podmíněný přístup. To znamená, že můžete omezit přístup mobilních prohlížečů k webovým aplikacím připojeným ke službě Azure AD tak, aby uživatelé mohli používat jenom Managed Browser, a blokovat přístup ze všech ostatních nechráněných prohlížečů, například Safari nebo Chrome. Tuto ochranu můžete použít u prostředků Azure, jako jsou Exchange Online a SharePoint Online, portál Office a dokonce místní weby, k nimž mají přístup externí uživatelé přes [Proxy aplikací Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). 

Pokud chcete webovým aplikacím připojeným ke službě Azure AD omezit možnost používání aplikace Intune Managed Browser na mobilních platformách, můžete vytvořit zásadu podmíněného přístupu Azure AD, která vyžaduje schválené klientské aplikace. 

1. Na portálu Azure Portal vyberte **Azure Active Directory** > **Podnikové aplikace** > **Podmíněný přístup** > **Nová zásada**. 
2. Potom v okně v části **Ovládací prvky přístupu** vyberte **Udělení**. 
3. Klikněte na **Vyžaduje se klientem schválená aplikace**. 
4. V okně **Udělení** klikněte na **Vybrat**. Tuto zásadu musíte přiřadit ke cloudovým aplikacím, které mají být dostupné jenom pro aplikaci Intune Managed Browser.

    ![Azure AD – zásada podmíněného přístupu pro Managed Browser](./media/managed-browser-conditional-access-01.png)

5. V části **Přiřazení** vyberte **Podmínky** > **Klientské aplikace**. Zobrazí se okno **Klientské aplikace**.
6. V části **Konfigurovat** klikněte na **Ano**, aby se zásada použila u konkrétních klientských aplikací.
7. Zkontrolujte, že je jako klientská aplikace vybraná možnost **Prohlížeč**.

    ![Azure AD – Managed Browser – Výběr klientských aplikací](./media/managed-browser-conditional-access-02.png)

    > [!NOTE]
    > Pokud chcete omezit to, které nativní (neprohlížečové) aplikace mají přístup k těmto cloudovým aplikacím, můžete také vybrat **Mobilní aplikace a desktopoví klienti**.

8. V části **Přiřazení** vyberte **Uživatelé a skupiny** a potom zvolte uživatele nebo skupiny, ke kterým chcete tuto zásadu přiřadit. 

    > [!NOTE]
    > Na uživatele musí také cílit zásady Intune App Protection. Další informace o vytváření zásad Intune App Protection najdete v tématu [Co jsou zásady ochrany aplikací?](app-protection-policy.md).

9. V části **Přiřazení** vyberte **Cloudové aplikace** a zvolte, které aplikace chcete chránit pomocí této zásady.

Jakmile nakonfigurujete výše uvedenou zásadu, budou uživatelé pro přístup k webovým aplikacím připojeným ke službě Azure AD, které chráníte pomocí této zásady, nuceni používat Intune Managed Browser. Pokud se uživatel pokusí v tomto scénáři použít nespravovaný prohlížeč, zobrazí se mu zpráva, že musí použít Intune Managed Browser.

##  <a name="single-sign-on-to-azure-ad-connected-web-apps-in-the-intune-managed-browser"></a>Jednotné přihlašování k webovým aplikacím připojeným ke službě Azure AD v aplikaci Intune Managed Browser

Aplikace Intune Managed Browser v iOSu a Androidu může nově využít výhod jednotného přihlašování ke všem webovým aplikacím (SaaS i místním), které jsou připojeny ke službě Azure AD. Když se v iOSu nebo na Portálu společnosti Intune v Androidu nachází aplikace Microsoft Authenticator, uživatelé aplikace Intune Managed Browser budou mít přístup k webovým aplikacím připojeným ke službě Azure AD bez nutnosti opakovaně zadávat svoje přihlašovací údaje.

Jednotné přihlašování v aplikaci Intune Managed Browser vyžaduje, aby bylo vaše zařízení zaregistrováno aplikací Microsoft Authenticator v iOSu nebo na Portálu společnosti Intune v Androidu. Uživatelům s aplikací Authenticator nebo Portálem společnosti Intune se zobrazí výzva, aby si zařízení zaregistrovali, když přejdou do webové aplikace připojené ke službě Azure AD v aplikaci Intune Managed Browser, pokud už nemají zařízení zaregistrováno jinou aplikací. Jakmile se zařízení zaregistruje pomocí účtu spravovaného přes Intune, bude mít tento účet povoleno jednotné přihlašování u webových aplikací připojených ke službě Azure AD. 

> [!NOTE]
> Registrace zařízení představuje jednoduché vrácení se změnami pomocí služby Azure AD. Nevyžaduje úplnou registraci zařízení a nedává pracovníkům IT žádná další oprávnění k zařízení.

## <a name="create-a-managed-browser-app-configuration"></a>Vytvoření konfigurace aplikace Managed Browser

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3.  V okně **Mobilní aplikace** v seznamu Spravovat zvolte **Zásady konfigurace aplikací**.
4.  V okně **Zásady konfigurace aplikací** vyberte možnost **Přidat**.
5.  V okně **Přidat zásady konfigurace** zadejte **Název** a volitelný **Popis** nastavení konfigurace aplikace.
6.  Jako typ **Registrace zařízení** zvolte **Spravované aplikace**.
7.  Zvolte **Vybrat požadovanou aplikaci** a potom v okně **Cílové aplikace** zvolte **Managed Browser** pro iOS, Android nebo oba systémy.
8.  Zvolte **OK** a vraťte se tak do okna **Přidat zásady konfigurace**.
9.  Zvolte **Nastavení konfigurace**. V okně **Konfigurace** definujte dvojice klíč-hodnota, které budou určovat nastavení aplikace Managed Browser. Informace o různých párech klíč a hodnota, které můžete definovat, najdete v dalších částech tohoto článku.
10. Když jste hotovi, klikněte na **OK**.
11. V okně **Přidat zásady konfigurace** zvolte **Přidat**.
12. Vytvoří se nová konfigurace, která se zobrazí v okně **Konfigurace aplikací**.

>[!IMPORTANT]
>V současné době aplikace Managed Browser spoléhá na automatickou registraci. Aby se konfigurace aplikace použily, musí už na zařízení být jiná aplikace spravovaná zásadami ochrany aplikací Intune.

## <a name="assign-the-configuration-settings-you-created"></a>Přiřazení vytvořeného nastavení aplikace

Nastavení přiřazujete skupinám uživatelů ve službě Azure AD. Pokud má daný uživatel aplikaci Managed Browser nainstalovanou, je spravována na základě vámi zadaného nastavení.

1. V okně **Mobilní aplikace** řídicího panelu správy mobilních aplikací Intune zvolte **Zásady konfigurace aplikací**.
2. V seznamu konfigurací aplikací vyberte tu, kterou chcete přiřadit.
3. V dalším okně zvolte **Přiřazení**.
4. V okně **Přiřazení** vyberte skupinu uživatelů ve službě Azure AD, kterým chcete přiřadit konfiguraci aplikace, a potom zvolte **OK**.


## <a name="how-to-configure-application-proxy-settings-for-the-managed-browser"></a>Postup konfigurace nastavení proxy aplikací pro Managed Browser

Aplikaci Intune Managed Browser a [Proxy aplikací Azure AD]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) lze použít společně za účelem podpory následujících scénářů pro uživatele zařízení s iOSem nebo Androidem:

- Uživatel stáhne aplikaci Microsoft Outlook a přihlásí se do ní. Zásady ochrany aplikací Intune se automaticky použijí. Zašifrují uložená data a zablokují uživateli možnost přesouvat firemní soubory do nespravovaných aplikací nebo umístnění na zařízení. Když uživatel potom v Outlooku klikne na odkaz směřující na intranetový server, můžete nastavit, aby takový odkaz otevřel místo běžného prohlížeče aplikaci Managed Browser. Prohlížeč Managed Browser rozpozná, že tento intranetový server byl uživateli zpřístupněn prostřednictvím proxy aplikací. Uživatel je automaticky přesměrován prostřednictvím proxy aplikací, aby před zpřístupněním intranetového serveru provedl ověření pomocí příslušného vícefaktorového ověřování a podmíněného přístupu. Tento server, který nebylo dříve možné najít, když byl uživatel vzdálený, je nyní dostupný a odkaz v Outlooku funguje podle očekávání.
- Vzdálený uživatel otevře prohlížeč Managed Browser a přejde na intranetový server pomocí interní adresy URL. Prohlížeč Managed Browser rozpozná, že tento intranetový server byl uživateli zpřístupněn prostřednictvím proxy aplikací. Uživatel je automaticky přesměrován prostřednictvím proxy aplikací, aby před zpřístupněním intranetového serveru provedl ověření pomocí příslušného vícefaktorového ověřování a podmíněného přístupu. Tento server, který nebylo možné najít, když byl uživatel vzdálený, je nyní dostupný.

### <a name="before-you-start"></a>Než začnete

- Nastavte svoje interní aplikace prostřednictvím proxy aplikací Azure AD.
    - Postup konfigurace proxy aplikací a publikování aplikací najdete v [dokumentaci k instalaci]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started#how-to-get-started). 
- Musíte používat minimálně verzi 1.2.0 aplikace Managed Browser.
- Uživatelé prohlížeče Managed Browser mají k této aplikaci přiřazené [zásady ochrany aplikací Intune]( app-protection-policy.md).

    > [!NOTE]
    > Aktualizovaným datům přesměrování proxy aplikace může trvat až 24 hodin, než se projeví v aplikaci Managed Browser.


#### <a name="step-1-enable-automatic-redirection-to-the-managed-browser-from-outlook"></a>Krok 1: Zapněte automatické přesměrování z Outlooku do prohlížeče Managed Browser.
Outlook musí být nakonfigurován zásadami ochrany aplikací, které povolují nastavení **Omezit webový obsah tak, aby se spouštěl v Managed Browseru**.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-managed-browser"></a>Krok 2: Přiřaďte zásady konfigurace aplikací přiřazené prohlížeči Managed Browser.
Tento postup nakonfiguruje prohlížeč Managed Browser tak, aby používal přesměrování proxy aplikací. Pomocí postupu pro vytvoření konfigurace aplikace Managed Browser zadejte následující dvojici klíč-hodnota:

|||
|-|-|
|Klíč|Hodnota|
|**com.microsoft.intune.mam.managedbrowser.AppProxyRedirection**|**true**|

Další informace o tom, jak lze aplikaci Managed Browser a Proxy aplikací Azure AD používat společně za účelem bezproblémového (a chráněného) přístupu k místním webovým aplikacím, najdete v blogovém příspěvku Enterprise Mobility + Security s názvem[Better together: Intune and Azure Active Directory team up to improve user access](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access) (Ve dvou se to lépe táhne: Intune a Azure Active Directory společně vylepšují uživatelský přístup).

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
|Vybírejte z těchto možností:<br><br>– Určení povolených adres URL (povoleny budou pouze tyto adresy a na jiné weby nebudou mít uživatelé přístup): **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br>– Určení blokovaných adres URL (na všechny ostatní weby budou mít uživatelé přístup): <br><br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**|Odpovídající hodnotou klíče je seznam adres URL. Zadejte všechny adresy, které chcete povolit nebo blokovat, jako jedinou hodnotu oddělenou znaky svislé čáry **&#124;**.<br><br>Příklady:<br><br>**URL1&#124;URL2&#124;URL3**<br>**http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com**|

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

## <a name="how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios"></a>Jak se dostat k protokolům spravovaných aplikací pomocí Managed Browseru na zařízení s iOSem

Koncoví uživatelé, kteří mají na zařízení s iOSem nainstalovaný prohlížeč Managed Browser, můžou zobrazit stav správy všech aplikací publikovaných Microsoftem. Můžou posílat protokoly kvůli řešení problémů se spravovanými aplikacemi pro iOS.

1. Otevřete **Nastavení** pro iOS.
2. Vyberte nastavení aplikace **Managed Browser**.
3. Přepněte **Povolit diagnostiku Intune** a nastavte tak prohlížeč do režimu pro řešení problémů.
4. Otevřete **Managed Browser**. Klikněte na **Zobrazit stav aplikace v Intune** a zkontrolujte nastavení zásad pro jednotlivé aplikace.
5. Stiskněte **Začínáme** a **Sdílet protokoly** nebo **Odeslat protokoly do Microsoftu** a pošlete protokoly pro řešení problémů správci IT nebo Microsoftu.

Prohlížeč Managed Browser můžete otevřít v režimu pro řešení problémů také z aplikace.

1. Otevřete Managed Browser.
2. Do pole adresy zadejte `about:intunehelp`.
Prohlížeč Managed Browser spustí režim pro řešení problémů.

Seznam nastavení uložených v aplikačních protokolech najdete v tématu [Kontrola protokolů ochrany aplikace v aplikaci Managed Browser](app-protection-policy-settings-log.md).

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

## <a name="next-steps"></a>Další kroky

- [Co jsou zásady ochrany aplikací?](app-protection-policy.md)