---
title: Správa webového přístupu pomocí Microsoft Edge v Microsoft Intune
titleSuffix: ''
description: Ujistěte se, že firemní websites jsou vždycky přistupovat pomocí bezpečnostní opatření na místě pomocí zásad ochrany aplikací Intune s Microsoft Edge.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3fb2f050-ec94-42ab-be05-c3d4101148bb
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 50574a2d3dc4ba5731b1a90f563ddd1a08e7f833
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2019
ms.locfileid: "67529634"
---
# <a name="manage-web-access-using-microsoft-edge-with-microsoft-intune"></a>Správa webového přístupu pomocí Microsoft Edge v Microsoft Intune

Zásady ochrany aplikací pomocí Microsoft Edge můžete Ujistěte se, že firemní websites jsou vždycky přistupovat pomocí bezpečnostní opatření na místě. K dispozici jsou následující funkce enterprise Microsoft Edge povolené prostřednictvím zásad v Intune. Tyto podnikové funkce patří:

1. **Dual-Identity** – uživatelé můžou přidávat i pracovní účet, stejně jako osobní účet, pro procházení. Je zcela oddělit mezi dvěma identity, které se podobá architektuře a zkušeností v Office 365 a Outlook. Správci Intune budou moct nastavit zásady požadovaného pro chráněné procházení v rámci pracovního účtu.
2. **Integrace zásad ochrany aplikací Intune** – od Microsoft Edge je integrovaná se sadou Intune SDK, můžete cílit na zásady ochrany aplikací pro zajištění ochrany před ztrátou dat. Mezi tyto možnosti patří ovládací prvek operací vyjmutí, kopírování, vložení, prevenci obrazovky zachytí a zajistit, že uživatel vybral odkazy otevřít jenom v ostatních spravovaných aplikací.
3. **Integrace Azure Application Proxy** – můžete řídit přístup k aplikacím SaaS a webových aplikací, což pomáhá zaručit založené na prohlížeči jenom aplikace spusťte v zabezpečené prohlížeč Microsoft Edge, koncoví uživatelé připojit z podnikové sítě nebo připojení z Internetu .
4. **Konfigurace aplikace** – můžete využít nastavení konfigurace aplikace k posílení stavu zabezpečení organizace a konfiguraci snadné použití funkcí pro koncové uživatele. Můžete například definovat záložky, místní domovské stránky, povoleno/zablokováno servery, Proxy aplikací Azure a další.
Zásady ochrany společnosti Microsoft Intune pro Microsoft Edge pomáhají chránit data vaší organizace a prostředky. Pomocí těchto zásad Microsoft Edge zajišťuje, že prostředkům vaší společnosti chráněni nejen v rámci nativně nainstalovaných aplikací, ale také při přístupu prostřednictvím webového prohlížeče.

## <a name="getting-started"></a>Začínáme

Vy a vaši koncoví uživatelé mohou stáhnout Microsoft Edge z veřejných obchodů s aplikacemi pro použití vaší organizace. Požadavky na operační systém pro zásady prohlížeče:
- Android 4 a novější nebo
- iOS 8.0 a novější

## <a name="application-protection-policies-for-microsoft-edge"></a>Zásady ochrany aplikací pro Microsoft Edge

Microsoft Edge je integrovaná se sadou Intune SDK, můžete použít zásady ochrany aplikací na ně, včetně:
- Řízení použití operací vyjmutí, kopírování a vložení
- Prevence pořizování snímků obrazovky
- Možnost otevírání podnikových odkazů jenom ve spravovaných aplikacích a prohlížečích

Podrobnosti najdete v tématu Co jsou zásady ochrany aplikací?
Tato nastavení můžete použít na:
- Zařízení, která jsou zaregistrovaná v Intune
- Zaregistrovaná pomocí jiného produktu MDM
- Nespravovaná zařízení

Pokud Microsoft Edge není cílem zásad Intune, uživatelé nemůžou používat pro přístup k datům z jiných aplikací spravovaných pomocí Intune, jako jsou například aplikace Office. 

## <a name="conditional-access-for-microsoft-edge"></a>Podmíněný přístup pro Microsoft Edge

Je možné využívat podmíněný přístup Azure AD pro přesměrování uživatelům přístup k podnikovému obsahu pouze prostřednictvím Microsoft Edge. To by omezit přístup mobilních prohlížečů k Azure AD webovým aplikacím připojeným k chráněné zásad Microsoft Edge, a to bude blokovat přístup ze všech ostatních nechráněných prohlížečů například Safari nebo Chrome. Podmíněný přístup je možné využít k prostředkům Azure, jako je Exchange Online a SharePoint Online, centra pro správu služeb Microsoft 365 a dokonce místní weby, které mají přístup externí uživatelé přes [Proxy aplikací Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

Pokud chcete omezit Azure AD webovým aplikacím připojeným k použití Microsoft Edge v Iosu a Androidu, postupujte podle následujících kroků:
1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Pod uzlem Intune vyberte **podmíněného přístupu** > **nové zásady**.
3. Potom v okně v části **Ovládací prvky přístupu** vyberte **Udělení**.
4. Klikněte na **Vyžaduje se klientem schválená aplikace**.
5. V okně **Udělení** klikněte na **Vybrat**. Tuto zásadu musíte přiřadit ke cloudovým aplikacím, které mají být dostupné jenom pro aplikaci Intune Managed Browser.

    ![Zásady podmíněného přístupu – udělení](./media/manage-microsoft-edge/manage-microsoft-edge-01.png)

6. V části přiřazení vybrat podmínky > klientské aplikace. Zobrazí se okno aplikace klienta.
7. V části Konfigurace dané zásady používaly pro konkrétní klientské aplikace, klikněte na tlačítko Ano.
8. Ověřte, že prohlížeč je zvolen jako klientskou aplikaci.

    ![Zásady podmíněného přístupu – výběr klientských aplikací](./media/manage-microsoft-edge/manage-microsoft-edge-02.png)

    > [!NOTE]
    > Pokud chcete omezit to, které nativní (neprohlížečové) aplikace mají přístup k těmto cloudovým aplikacím, můžete také vybrat **Mobilní aplikace a desktopoví klienti**.

9. V části **Přiřazení** vyberte **Uživatelé a skupiny** a potom zvolte uživatele nebo skupiny, ke kterým chcete tuto zásadu přiřadit.

    > [!NOTE]
    > Aby uživatelé mohli přijímat zásady konfigurace aplikací, musí na ně cílit také zásady ochrany aplikací Intune. Další informace o vytváření zásad Intune App Protection najdete v článku [Co jsou zásady ochrany aplikací](app-protection-policy.md).

10. V části **Přiřazení** vyberte **Cloudové aplikace** a zvolte, které aplikace chcete chránit pomocí této zásady.

Po nakonfigurování výše uvedenou zásadu uživatele si bude muset používat Microsoft Edge pro přístup k Azure AD připojené webové aplikace, které chráníte pomocí této zásady. Pokud se uživatel pokusí v tomto scénáři použít nespravovaný prohlížeč, zobrazí se zpráva, že uživatel musí použít Microsoft Edge.

> [!TIP]
> Podmíněný přístup je technologie Azure Active Directory (Azure AD). Uzlu podmíněný přístup k němu přistupovat z Intune je stejný uzel, protože k němu přistupovat z Azure AD.

## <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>Jednotné přihlašování k webovým aplikacím připojeným ke službě Azure AD v prohlížečích chráněných zásadami

Microsoft Edge v iOS a Android můžete využít výhod jednotného přihlašování ke všem webovým aplikacím (SaaS i v místním prostředí), které jsou připojené AD Azure. Jednotné přihlašování umožňuje uživatelům přístup k Azure AD webovým aplikacím připojeným přes Microsoft Edge, aniž byste museli znovu zadat své přihlašovací údaje.

Jednotné přihlašování vyžaduje zařízení k registraci pomocí aplikace Microsoft Authenticator pro zařízení s Iosem nebo portálu společnosti Intune v Androidu. Uživatelé, kteří mají aplikace Authenticator nebo portálem společnosti Intune, zobrazí se výzva k registraci jejich zařízení, když uživatel přejde do Azure AD připojené webové aplikace v prohlížeči chráněné zásad, pokud jejich zařízení nebyla registrována již ještě. Jakmile je zařízení zaregistrované pomocí uživatelského účtu spravovaného službou Intune, bude mít tento účet povoleno jednotné přihlašování u Azure AD – připojení webové aplikace.

> [!NOTE]
> Registrace zařízení představuje jednoduché vrácení se změnami pomocí služby Azure AD. Nevyžaduje úplnou registraci zařízení a nedává pracovníkům IT žádná další oprávnění k zařízení.

## <a name="create-a-protected-browser-app-configuration"></a>Vytvoření konfigurace aplikace chráněného prohlížeče

Pro konfigurace aplikace použily, uživatel je chráněný prohlížeče nebo jiné aplikace v zařízení musí již být spravován [zásady ochrany aplikací Intune](app-protection-policy.md).

Následující postup slouží k vytvoření konfigurace aplikace chráněné prohlížeče:

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **klientské aplikace** > **zásady Konfigurace aplikací** > **přidat**.
3. V okně **Přidat zásady konfigurace** zadejte **Název** a volitelný **Popis** nastavení konfigurace aplikace.
4. Jako typ **Registrace zařízení** zvolte **Spravované aplikace**.
5. Zvolte **Vybrat požadovanou aplikaci** a potom v okně **Cílové aplikace** zvolte **Managed Browser** nebo **Edge** pro iOS, Android nebo oba systémy.
6. Zvolte **OK** a vraťte se tak do okna **Přidat zásady konfigurace**.
7. Zvolte **Nastavení konfigurace**. Na **konfigurace** okně určit dvojice klíče a hodnoty budou určovat nastavení aplikace pro Microsoft Edge. Informace o různých párech klíč a hodnota, které můžete definovat, najdete v dalších částech tohoto článku.

    > [!NOTE]
    > Microsoft Edge používá stejné dvojice klíč-hodnota jako Managed Browser. 

8. Po dokončení klikněte na **OK**.
9. V okně **Přidat zásady konfigurace** zvolte **Přidat**.<br>
    Nová konfigurace se vytvoří a zobrazí na **konfigurace aplikace** okno.

## <a name="assign-the-configuration-settings-you-created"></a>Přiřazení vytvořeného nastavení aplikace 

Nastavení přiřazujete skupinám uživatelů ve službě Azure AD. Pokud má daný uživatel cílovou aplikaci chráněného prohlížeče nainstalovanou, spravuje se podle vámi zadaného nastavení.

1. V okně **Klientské aplikace** řídicího panelu správy mobilních aplikací Intune zvolte **Zásady konfigurace aplikací**.
2. V seznamu konfigurací aplikací vyberte tu, kterou chcete přiřadit.
3. V dalším okně zvolte **Přiřazení**.
4. V okně **Přiřazení** vyberte skupinu uživatelů ve službě Azure AD, kterým chcete přiřadit konfiguraci aplikace, a potom zvolte **OK**.

## <a name="how-to-configure-application-proxy-settings-for-protected-browsers"></a>Postup konfigurace nastavení proxy aplikací pro chráněné prohlížeče

Microsoft Edge a [Proxy aplikací Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) je možné společně můžete uživatelům udělit přístup pro intranetové servery v jejich mobilních zařízeních. 

Toto jsou některé příklady scénářů povolit Proxy aplikací služby AD: 

- Uživatel je pomocí mobilní aplikace Outlook, který je chráněn službou Intune. Klikněte na odkaz na intranetový server v e-mailu a Microsoft Edge rozpozná, že tento intranetový server byl zpřístupněn uživateli prostřednictvím Proxy aplikací. Uživatel je automaticky přesměrován prostřednictvím Proxy aplikací k ověření pomocí libovolné příslušného vícefaktorového ověřování a podmíněný přístup před dosažením intranetový server. Uživatelé se nyní může přistupovat k interním webům i na mobilních zařízeních, a odkaz v Outlooku funguje podle očekávání.
- Uživatel otevře Microsoft Edge na jejich iOS nebo zařízení s Androidem. Pokud Microsoft Edge je pak chráněn rozhraním Intune a proxy aplikací je povolen, uživatel můžete přejít na intranetový server pomocí interní adresy URL se používají k. Microsoft Edge rozpozná, že tento intranetový server byl zpřístupněn uživatele prostřednictvím Proxy aplikací a uživatel je automaticky přesměrován prostřednictvím Proxy aplikací k ověření před dosažením intranetový server. 

### <a name="before-you-start"></a>Než začnete

- Nastavte svoje interní aplikace prostřednictvím proxy aplikací Azure AD.
    - Postup konfigurace proxy aplikací a publikování aplikací najdete v [dokumentaci k instalaci](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).
- Aplikace Microsoft Edge musí mít [zásady ochrany aplikací Intune](app-protection-policy.md) přiřazené.

> [!NOTE]
> Aktualizovaným datům přesměrování proxy aplikací může trvat až 24 hodin, než se projeví v aplikaci Managed Browser nebo Microsoft Edge.

#### <a name="step-1-enable-automatic-redirection-to-a-protected-browser-from-outlook"></a>Krok 1: Zapněte automatické přesměrování z Outlooku do chráněného prohlížeče.
Outlook se musí nakonfigurovat zásady ochrany aplikací, který umožňuje nastavení **sdílená složka webového obsahu pomocí zásad spravovaného prohlížeče**.

![Zásady ochrany aplikací – sdílená složka webového obsahu pomocí zásad spravovaného prohlížeče](./media/manage-microsoft-edge/manage-microsoft-edge-03.png)

#### <a name="step-2-set-the-app-configuration-setting-to-enable-app-proxy"></a>Krok 2: Nastavení konfigurace aplikace pro povolení proxy aplikace
Microsoft Edge s cílit následující dvojici klíč/hodnota k povolení proxy aplikace pro Microsoft Edge:

|    Klíč    |    Value    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.AppProxyRedirection    |    true (pravda)    |

Další informace o jak Microsoft Edge a Azure AD Application Proxy můžete využít při vytvoření celostní k bezproblémového (a chráněného) přístupu k místním webovým aplikacím, najdete v článku řešení Enterprise Mobility + Security blogovém příspěvku [společně ještě lepší: Intune and Azure Active Directory team up to improve user access](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access) (Ve dvou se to lépe táhne: Intune a Azure Active Directory společně vylepšují uživatelský přístup). Tento blogový příspěvek odkazy Intune Managed Browser, ale obsah platí i pro Microsoft Edge.

## <a name="how-to-configure-a-homepage-shortcut-for-microsoft-edge"></a>Jak nakonfigurovat domovskou stránku zástupce pro Microsoft Edge

Toto nastavení umožňuje nakonfigurovat domovskou stránku zástupce pro Microsoft Edge.  Domovská stránka klávesovou zkratku, kterou nakonfigurujete se zobrazí jako první ikona pod panelu hledání při otevření nové záložky v Microsoft Edge. Uživatel nebude možné upravit nebo odstranit tento zástupce v daném kontextu se spravované. Zástupce domovské stránky bude za účelem odlišení zobrazovat název vaší organizace. 

Použití následující dvojici klíč/hodnota konfigurace místní domovské stránky:

|    Klíč    |    Value    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.homepage   |    Zadejte platnou adresu URL. Nesprávné adresy URL se z bezpečnostních důvodů blokují.<br>**Příklad:** `<https://www.bing.com`>
    |

## <a name="how-to-configure-managed-bookmarks-for-microsoft-edge"></a>Jak nakonfigurovat spravované záložky pro Microsoft Edge

Pro usnadnění přístupu můžete nakonfigurovat záložek, které chcete vaši uživatelé měli k dispozici při používání Microsoft Edge. Tady jsou některé podrobnosti:

- Tyto záložky se zobrazí pouze pro uživatele, pokud uživatelé používají firemní režimu Microsoft Edge. 
- Tyto záložky nelze odstranit ani upravit uživatele.
- Tyto záložky se zobrazí v horní části seznamu. Všechny záložky vytvořené uživateli se zobrazí pod těmito záložkami.
- Pokud jste povolili přesměrování Proxy aplikací, můžete přidat webové aplikace Proxy aplikací pomocí jejich interní nebo externí adresy URL.

Ke konfiguraci spravovaných záložky použijte následující dvojici klíč/hodnota:

|    Klíč    |    Value    |
|---------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.bookmarks    |    Hodnota pro tuto konfiguraci je seznam záložek. Každou záložku tvoří název záložky a adresa URL záložky. Oddělení název a adresu URL `|` znak.      **Příklad:**<br>`Microsoft Bing|https://www.bing.com`<br>Chcete-li nakonfigurovat více záložek, oddělte každý pár těmito dvěma znaky `||`.<p>**Příklad:**<br>`Microsoft Bing|https://www.bing.com||Contoso|https://www.contoso.com`    |

## <a name="how-to-display-myapps-within-microsoft-edge-bookmarks"></a>Jak zobrazit MyApps v rámci záložek Microsoft Edge

Ve výchozím nastavení se uživatelům zobrazí MyApps weby, které jsou nakonfigurované k nim v rámci složky uvnitř záložky Microsoft Edge. Složku se popisek s názvem vaší organizace.

|    Klíč    |    Hodnota    |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.MyApps    |    **Hodnota TRUE** ukazuje MyApps v rámci záložek Microsoft Edge.<p>**False** skryje MyApps v rámci Microsoft Edge.    |

## <a name="how-to-specify-allowed-or-blocked-sites-list-for-microsoft-edge"></a>Určení seznamu povolených nebo blokovaných webů pro Microsoft Edge
Konfigurace aplikací můžete použít k definování weby, které uživatelé přístup při používání jejich pracovního profilu. Pokud používáte seznam povolených, vaši uživatelé jenom se může přistupovat k webům, které jste uvedli explicitně. Pokud používáte seznam blokovaných aplikací, uživatelé budou mít přístup všechny weby kromě serverů, které jste explicitně blokovaný. Pouze byste měli uložit buď povolený nebo seznam, ne obojí. Pokud jsou obě cílící na dané zařízení, bude dodržet seznamu povolených aplikací.  

Můžete použít následující dvojice klíč/hodnota konfigurace buď seznam povolených nebo blokovaných webů pro Microsoft Edge. Pokračujte ve čtení pro další informace o platných formátů adresy URL. 

|    Klíč    |    Value    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Vybírejte z těchto možností:<p>1. Určení povolených adres URL (povolené jsou pouze tyto adresy URL; na žádné jiné weby nebudou mít uživatelé přístup):<br>`com.microsoft.intune.mam.managedbrowser.AllowListURLs`<p>2. Určení blokovaných adres URL (na všechny ostatní weby budou mít uživatelé přístup):<br>`com.microsoft.intune.mam.managedbrowser.BlockListURLs`    |    Odpovídající hodnotou klíče je seznam adres URL. Zadejte všechny adresy URL, kterou chcete povolit nebo blokovat, jako jedinou hodnotu, která je oddělená znakem | `|` znak.<br>**Příklady:**<br>`URL1|URL2|URL3`<br>`http://.contoso.com/|https://.bing.com/|https://expenses.contoso.com`  |

### <a name="url-formats-for-allowed-and-blocked-site-list"></a>Formátech adres URL pro povolené a blokované seznam webů 
Různých formátech adres URL můžete použít k vytváření seznamů povolených/zakázaných webů. Tyto povolené modely jsou podrobně popsané v následující tabulce. Několik poznámek před zahájením práce: 
- Při zadávání adres URL do seznamu nezapomeňte u všech uvést předponu **http** nebo **https**.
- Můžete použít zástupný znak (\*) podle pravidel v následujícím seznamu povolených vzorů.
- Zástupný znak odpovídá pouze celý compoment název hostitele (oddělených tečkami) nebo celé části cesty (oddělené lomítkem). Například `http://*contoso.com` je **není** podporována.
- V adrese můžete specifikovat čísla portů. Pokud nezadáte číslo portu, použijí se tyto hodnoty:
    - Port 80 pro protokol HTTP
    - Port 443 pro protokol HTTPS
- Použití zástupných znaků pro číslo portu je **není** podporována. Například `http://www.contoso.com:*` a `http://www.contoso.com:*/` podporované nejsou. 

    |    URL    |    Podrobnosti    |    Odpovídá    |    Neodpovídá    |
    |-------------------------------------------|--------------------------------------------------------|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
    |    `http://www.contoso.com`    |    Odpovídá jediné stránce    |    `www.contoso.com`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`contoso.com/`    |
    |    `http://contoso.com`    |    Odpovídá jediné stránce    |    `contoso.com/`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com`    |
    |    `http://www.contoso.com/&#42;`   |    Odpovídá všem adresám URL začínajícím na `www.contoso.com`    |    `www.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com/videos/tvshows`    |    `host.contoso.com`<br>`host.contoso.com/images`    |
    |    `http://*.contoso.com/*`    |    Odpovídá všem dílčím doménám domény `contoso.com`    |    `developer.contoso.com/resources`<br>`news.contoso.com/images`<br>`news.contoso.com/videos`    |    `contoso.host.com`    |
    |    `http://www.contoso.com/images`    |    Odpovídá jediné složce    |    `www.contoso.com/images`    |    `www.contoso.com/images/dogs`    |
    |    `http://www.contoso.com:80`    |    Odpovídá jediné stránce s použitím čísla portu    |    http://www.contoso.com:80    |         |
    |    `https://www.contoso.com`    |    Odpovídá jediné zabezpečené stránce    |    `https://www.contoso.com`    |    `http://www.contoso.com`    |
    |    `http://www.contoso.com/images/*`    |    Odpovídá jediné složce a všem podsložkám    |    `www.contoso.com/images/dogs`<br>`www.contoso.com/images/cats`    |    `www.contoso.com/videos`    |
  
- Tady jsou uvedené příklady některých vstupních hodnot, které nemůžete zadat:
    - `*.com`
    - `*.contoso/*`
    - `www.contoso.com/*images`
    - `www.contoso.com/*images*pigs`
    - `www.contoso.com/page*`
    - IP adresy
    - `https://*`
    - `http://*`
    - `https://*contoso.com`
    - `http://www.contoso.com:*`
    - `http://www.contoso.com: /*`
  
## <a name="defining-behavior-when-users-try-to-access-a-blocked-site"></a>Definuje chování, když se uživatelé pokusí o přístup k zablokování webu

S modelem identity dvou součástí Microsoft Edge můžete povolit více flexibilní prostředí pro koncové uživatele, které nebylo možné s Intune Managed Browser. Když uživatelé dostat blokované webu v Microsoft Edge, může být vyzve k otevření odkazu v jejich osobní kontext místo jejich práci, odkud můžou k zajištění své ochrany, a zajistit přitom ochranu firemních prostředků bezpečné. Například pokud uživatel je odkaz zpravodajskému článku prostřednictvím svého aplikace Outlook, se budou moct Otevřít odkaz v daném kontextu se osobní nebo se službou InPrivate kartě místo jejich práci, která news websites nepovoluje. Ve výchozím nastavení jsou povoleny tyto přechody.

Používá následující dvojici klíč/hodnota pro možnost nakonfigurujte, pokud jsou povolené tyto softwarové přechody:

|    Klíč    |    Value    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock`    |    **Hodnota TRUE** umožňuje přechod uživatelům na jejich osobní kontext spuštěním blokovaných webů Microsoft Edge<p>**Blok** brání přechod od uživatelů, Microsoft Edge a uživatelé jednoduše zobrazí zprávu s oznámením se snaží získat přístup k webu je blokován.    |

## <a name="directing-users-to-microsoft-edge-instead-of-the-intune-managed-browser"></a>Směruje uživatele do Microsoft Edge místo Intune Managed Browser 

Intune Managed Browser i Microsoft Edge jsou teď může sloužit jako chráněné zásady prohlížeče. Aby bylo zajištěno, že jsou vaši uživatelé směrování k používání aplikace správný prohlížeč, směrování všech vašich aplikací spravovaných pomocí Intune (např. Outlook, OneDrive a SharePoint) s následujícím nastavením konfigurace:

|    Klíč    |    Hodnota    |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.useEdge`    |    Hodnota `true` vás přesměrují vaši uživatelé můžou stáhnout a použít Microsoft Edge.<br>Hodnota `false` umožňuje uživatelům používat Intune Managed Browser.    |

Pokud je tato hodnota konfigurace aplikace **není** nastavena, podle následujícího postupu budou definovat webového prohlížeče se použije k otevření podnikové odkazů.

V Androidu:
- Intune Managed Browser spustí, pokud má uživatel Intune Managed Browser i na svém zařízení stáhnout Microsoft Edge. 
- Microsoft Edge se otevře, pokud jen pro Microsoft Edge se stáhne do zařízení a zaměřuje se zásadami Intune.
- Pokud pouze spravovaný prohlížeč je v zařízení a je cílem zásad Intune, otevře se Managed Browser.

V iOSu u aplikací, které mají integrovanou sadu Intune SDK pro iOS verze 9.0.9+:
- Intune Managed Browser spustí, pokud Managed Browser a Microsoft Edge na zařízení.  
- Microsoft Edge se spustí, pokud jen pro Microsoft Edge na zařízení a zaměřuje se zásadami Intune.
- Pokud pouze spravovaný prohlížeč je v zařízení a je cílem zásad Intune Managed Browser.

## <a name="using-microsoft-edge-on-ios-to-access-managed-app-logs"></a>Přístup k protokolům spravovaných aplikací pomocí Microsoft Edge v Iosu 

Koncoví uživatelé s Microsoft Edge nainstalovaný na zařízení s Iosem můžete zobrazit stav správy všech aplikací publikovaných Microsoftem. Můžou posílat protokoly kvůli řešení problémů se spravovanými aplikacemi pro iOS.
1. Otevřete Microsoft Edge na zařízení s Iosem.
2. Do pole adresy zadejte `about:intunehelp`. 
3. Řešení potíží s režimu bude spuštěn z v rámci Microsoft Edge.

Seznam nastavení uložených v aplikačních protokolech najdete v tématu [Kontrola protokolů ochrany aplikace v aplikaci Managed Browser](app-protection-policy-settings-log.md).

Postup zobrazení protokolů na zařízeních s Androidem, najdete v sekci [odeslání protokolů správci IT e-mailem](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). 

## <a name="security-and-privacy-for-microsoft-edge"></a>Zabezpečení a ochrana osobních údajů pro Microsoft Edge

Další požadavky na zabezpečení a ochrana osobních údajů pro Microsoft Edge:

- Microsoft Edge nespotřebovává nastavení, která uživatelům nastavit pro nativní prohlížeč na svých zařízeních, protože Microsoft Edge nemá přístup k těmto nastavením.
- Pokud nakonfigurujete možnost **vyžadovat pro přístup jednoduchý PIN kód** nebo **vyžadovat pro přístup podnikové přihlašovací údaje** v aplikaci zásady ochrany přidružené k Microsoft Edge a uživatel vybere na odkaz Nápověda ověřování stránky mohli procházet libovolné weby bez ohledu na to, zda byly přidány do seznamu blokovaných v zásadách.
- Microsoft Edge může blokovat přístup k webům, pouze v případě, že jsou k nim přistupuje přímo. V případě, že se k webu přistupuje přes zprostředkující služby (třeba překladatelské služby), aplikace přístup neblokuje.
- Povolení ověřování a přístup k dokumentaci k Intune * **. microsoft.com** se vyjímá z nastavení seznamu povolených nebo blokovaných. Je vždycky povolená.
Vypnutí dat o využití Microsoft automaticky shromažďuje anonymní data o výkonu a využití spravovaného prohlížeče za účelem zlepšení svých produktů a služeb. Uživatelé můžou shromažďování těchto dat na svých zařízeních vypnout pomocí nastavení **Data o využití**. Nad shromažďováním těchto dat nemáte žádnou kontrolu. V zařízeních se systémem iOS se nedají otevřít weby, u kterých vypršela platnost certifikátu nebo které mají nedůvěryhodný certifikát.

## <a name="next-steps"></a>Další postup

- [Co jsou zásady ochrany aplikací?](app-protection-policy.md) 
