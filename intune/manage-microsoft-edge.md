---
title: Správa webového přístupu pomocí Microsoft Edge s Microsoft Intune
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
ms.openlocfilehash: 147547577615c6e74a9c5b3dd8b200ba387bad79
ms.sourcegitcommit: 1b7ee2164ac9490df4efa83c5479344622c181b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/08/2019
ms.locfileid: "67648467"
---
# <a name="manage-web-access-by-using-microsoft-edge-with-microsoft-intune"></a>Správa webového přístupu pomocí Microsoft Edge s Microsoft Intune

Zásady ochrany aplikací pomocí Microsoft Edge pomáhá zajistit, že firemní websites vždy s Windows zabezpečených bezpečnostní opatření na místě. K dispozici jsou následující funkce enterprise Microsoft Edge povolené prostřednictvím zásad Intune:

- **Dual-Identity.** Uživatele můžete přidat pracovní účet, jakož i osobní účet, pro procházení. Je zcela oddělit mezi dvěma identity, které se podobá architektuře a zkušeností v Office 365 a Outlook. Správci Intune mohou nastavit požadované zásady pro chráněné procházení v rámci pracovního účtu.
- **Integrace zásad ochrany aplikací Intune.** Microsoft Edge je integrovaná se sadou Intune SDK, můžete zacílit zásady ochrany aplikací pro ochranu před únikem informací. Mezi tyto možnosti patří řídící vyjmutí, kopírování a vložení, prevence pořizování snímků obrazovky a zajištění, že uživatel vybral odkazy otevřít jenom v ostatních spravovaných aplikací.
- **Integrace Proxy aplikace služby Azure.** Můžete řídit přístup k softwaru jako služby (SaaS) aplikací a webové aplikace. To pomáhá zajistit, že aplikace založené na prohlížeči spustit pouze v zabezpečené prohlížeč Microsoft Edge, zda koncoví uživatelé připojit z podnikové sítě nebo z Internetu připojit.
- **Konfigurace aplikace.** Nastavení konfigurace aplikace můžete použít k posílení stavu zabezpečení vaší organizace a konfiguraci snadné použití funkcí pro koncové uživatele. Můžete například definovat záložky, místní domovské stránky, povolených nebo blokovaných webů a Proxy aplikací Azure Active Directory (Azure AD).

Zásady ochrany společnosti Microsoft Intune pro Microsoft Edge pomáhají chránit data vaší organizace a prostředky. Pomocí těchto zásad Microsoft Edge zajišťuje, že prostředkům vaší společnosti chráněni nejen v rámci nativně nainstalovaných aplikací, ale také při přístupu prostřednictvím webového prohlížeče.

## <a name="getting-started"></a>Začínáme

Vy a vaši koncoví uživatelé mohou stáhnout Microsoft Edge z veřejných obchodů s aplikacemi pro použití vaší organizace. Požadavky na operační systém pro zásady prohlížeče jsou následující:
- Android 4 a novější
- iOS 8.0 a novější

## <a name="application-protection-policies-for-microsoft-edge"></a>Zásady ochrany aplikací pro Microsoft Edge

Microsoft Edge je integrovaná se sadou Intune SDK, můžete použít zásady ochrany aplikací na ně.

Tato nastavení můžete použít na:
- Zařízení, která jsou zaregistrovaná v Intune.
- Zařízení, která jsou zaregistrovaná v jiném produktu pro správu mobilních zařízení.
- Nespravovaná zařízení.

Pokud Microsoft Edge není cílem zásad Intune, uživatelé nemůžou používat pro přístup k datům z jiných aplikací spravovaných pomocí Intune, jako jsou například aplikace Office. 

## <a name="conditional-access-for-microsoft-edge"></a>Podmíněný přístup pro Microsoft Edge

Podmíněný přístup Azure AD slouží k přesměrování uživatelům přístup k podnikovému obsahu pouze prostřednictvím Microsoft Edge. To omezí přístup mobilních prohlížečů k Azure AD webovým aplikacím připojeným k chráněné zásad Microsoft Edge. Tato blokuje přístup ze všech ostatních nechráněných prohlížečů, například Safari nebo Chrome. Můžete použít podmíněný přístup k prostředkům Azure, jako je Exchange Online a SharePoint Online, centra pro správu služeb Microsoft 365 a dokonce místní weby, které mají přístup externí uživatelé přes [Proxy aplikací Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

Chcete-li omezit Azure AD webovým aplikacím připojeným k použití Microsoft Edge na zařízení s iOS a Android:
1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Pod uzlem Intune vyberte **podmíněného přístupu** > **nové zásady**.
3. Vyberte **udělení** z **ovládací prvky přístupu** části okna.
4. Vyberte **Vyžaduje se klientem schválená aplikace**.
5. Zvolte **vyberte** na **udělení** okno. Tuto zásadu musíte přiřadit ke cloudovým aplikacím, které mají být dostupné jenom pro aplikaci Intune Managed Browser.

    ![Snímek obrazovky s podmíněným přístupem zásady – udělení](./media/manage-microsoft-edge/manage-microsoft-edge-01.png)

6. V části přiřazení vyberte **podmínky** > **klientské aplikace**. **Klientské aplikace** otevře se okno.
7. V části **konfigurovat**vyberte **Ano** k dané zásady používaly pro konkrétní klientské aplikace.
8. Zkontrolujte, že je jako klientská aplikace vybraná možnost **Prohlížeč**.

    ![Snímek obrazovky s podmíněným přístupem zásad – výběr klientských aplikací](./media/manage-microsoft-edge/manage-microsoft-edge-02.png)

    > [!NOTE]
    > Pokud chcete omezit to, které nativní (neprohlížečové) aplikace mají přístup k těmto cloudovým aplikacím, můžete také vybrat **Mobilní aplikace a desktopoví klienti**.

9. V **přiřazení** vyberte **uživatelů a skupin**a pak zvolte uživatele nebo skupiny, kterou chcete přiřadit tuto zásadu.

    > [!NOTE]
    > Aby uživatelé mohli přijímat zásady konfigurace aplikací, musí na ně cílit také zásady ochrany aplikací Intune. Další informace o vytváření zásad Intune App Protection najdete v tématu [Co jsou zásady ochrany aplikací?](app-protection-policy.md).

10. V části **Přiřazení** vyberte **Cloudové aplikace** a zvolte, které aplikace chcete chránit pomocí této zásady.

Po nakonfigurování výše uvedenou zásadu jsou uživatelé nuceni používat Microsoft Edge pro přístup k Azure AD připojené webové aplikace, které chráníte pomocí této zásady. Pokud se uživatel pokusí v tomto scénáři použít nespravovaný prohlížeč, obdrží zprávu, že uživatel musí použít Microsoft Edge.

> [!TIP]
> Podmíněný přístup je technologie Azure AD. Uzlu podmíněný přístup k němu přistupovat z Intune je stejný uzel, protože k němu přistupovat z Azure AD.

## <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>Jednotné přihlašování k Azure AD webovým aplikacím připojeným v prohlížečích chráněné zásad

Microsoft Edge v iOS a Android můžete využít výhod jednotného přihlašování (SSO) ke všem webovým aplikacím (SaaS i místním), které jsou připojené AD Azure. Jednotné přihlašování umožňuje uživatelům přístup k Azure AD webovým aplikacím připojeným přes Microsoft Edge, aniž byste museli znovu zadat své přihlašovací údaje.

Jednotné přihlašování vyžaduje zařízení k registraci pomocí aplikace Microsoft Authenticator pro zařízení s Iosem nebo portálu společnosti Intune v Androidu. Uživatelé, kteří mají buď z nich, zobrazí se výzva k registraci jejich zařízení při otevření připojení AD webovou aplikaci Azure v prohlížeči chráněné zásad. (Toto je pouze hodnotu true, pokud jejich zařízení už registrovaný.) Jakmile je zařízení zaregistrované pomocí uživatelského účtu spravovaného službou Intune, má tento účet povoleno jednotné přihlašování u Azure AD – připojení webové aplikace.

> [!NOTE]
> Registrace zařízení představuje jednoduché vrácení se změnami pomocí služby Azure AD. Nevyžaduje úplnou registraci zařízení a nedává IT žádná další oprávnění na zařízení.

## <a name="create-a-protected-browser-app-configuration"></a>Vytvoření konfigurace aplikace chráněného prohlížeče

Pro konfigurace aplikace použily, uživatel je chráněný prohlížeče nebo jiné aplikace v zařízení musí již být spravován [zásady ochrany aplikací Intune](app-protection-policy.md).

Vytvoření konfigurace aplikace pro Microsoft Edge:

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **klientské aplikace** > **zásady Konfigurace aplikací** > **přidat**.
3. V okně **Přidat zásady konfigurace** zadejte **Název** a volitelný **Popis** nastavení konfigurace aplikace.
4. Jako typ **Registrace zařízení** zvolte **Spravované aplikace**.
5. Zvolte **vybrat požadovanou aplikaci**. Potom na **cílové aplikace** okno, vyberte **Managed Browser** nebo **Edge** pro iOS, Android nebo pro obojí.
6. Vyberte **OK** se vrátíte **přidat zásady konfigurace** okno.
7. Klikněte na **Nastavení konfigurace**. Na **konfigurace** okně určit dvojice klíče a hodnoty budou určovat nastavení aplikace pro Microsoft Edge. Informace o různých párech klíč a hodnota, které můžete definovat, najdete v dalších částech tohoto článku.

    > [!NOTE]
    > Microsoft Edge používá stejné dvojice klíč-hodnota jako Managed Browser. 

8. Jakmile budete hotovi, vyberte **OK**.
9. V okně **Přidat zásady konfigurace** zvolte **Přidat**.<br>
    Nová konfigurace se vytvoří a zobrazí na **konfigurace aplikace** okno.

## <a name="assign-the-configuration-settings-you-created"></a>Přiřazení vytvořeného nastavení aplikace 

Nastavení přiřazujete skupinám uživatelů ve službě Azure AD. Pokud má daný uživatel cílovou aplikaci chráněného prohlížeče nainstalovanou, spravuje se podle vámi zadaného nastavení.

1. Na **klientské aplikace** okno Intune mobilní aplikace správu řídicího panelu, vyberte **zásady Konfigurace aplikací**.
2. V seznamu konfigurací aplikací vyberte tu, kterou chcete přiřadit.
3. V dalším okně vyberte **přiřazení**.
4. Na **přiřazení** okno, vyberte Azure AD skupinu, ke kterému chcete přiřadit konfiguraci aplikace a pak vyberte **OK**.

## <a name="direct-users-to-microsoft-edge-instead-of-the-intune-managed-browser"></a>Požádejte uživatele, aby Microsoft Edge místo Intune Managed Browser 

Jak Intune Managed Browser a Microsoft Edge může sloužit jako chráněné zásady prohlížeče. Aby bylo zajištěno, že jsou vaši uživatelé směrování k používání aplikace správný prohlížeč, cílíte na všechny vaše aplikace spravované v Intune (třeba Outlook, OneDrive a SharePoint) s následujícím nastavením konfigurace:

|    Klíč    |    Value    |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.useEdge`    |    Hodnota `true` vás přesměrují vaši uživatelé můžou stáhnout a použít Microsoft Edge.<br>Hodnota `false` umožňuje uživatelům používat Intune Managed Browser.    |

Pokud je tato hodnota konfigurace aplikace **není** nastavena, podle následujícího postupu budou definovat webového prohlížeče se použije k otevření podnikové odkazů.

V Androidu:
- Intune Managed Browser spustí, pokud má uživatel Intune Managed Browser i na svém zařízení stáhnout Microsoft Edge. 
- Microsoft Edge se spustí, pokud jen pro Microsoft Edge se stáhne do zařízení a zaměřuje se zásadami Intune.
- Managed Browser spustí, pokud pouze spravovaný prohlížeč je v zařízení a je cílem zásad Intune.

V iOSu u aplikací, které mají integrovanou sadu Intune SDK pro iOS verze 9.0.9+:
- Intune Managed Browser spustí, pokud Managed Browser a Microsoft Edge na zařízení.  
- Microsoft Edge se spustí, pokud jen pro Microsoft Edge na zařízení a zaměřuje se zásadami Intune.
- Managed Browser spustí, pokud pouze spravovaný prohlížeč je v zařízení a je cílem zásad Intune.

## <a name="configure-application-proxy-settings-for-microsoft-edge"></a>Konfigurace nastavení Proxy aplikací pro Microsoft Edge

Můžete použít Microsoft Edge a [Proxy aplikací Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) společně můžete uživatelům udělit přístup pro intranetové servery v jejich mobilních zařízeních. 

Toto jsou některé příklady scénářů povolit Proxy aplikací Azure AD: 

- Uživatel je pomocí mobilní aplikace Outlook, který je chráněn službou Intune. Klikněte na odkaz na intranetový server v e-mailu a Microsoft Edge rozpozná, že tento intranetový server byl zpřístupněn prostřednictvím Proxy aplikací uživateli. Uživatel je automaticky přesměrován prostřednictvím Proxy aplikací, aby ověřoval jakékoli příslušného vícefaktorového ověřování a podmíněný přístup, před dosažením intranetový server. Uživatel se teď může přistupovat k interním webům, i na mobilních zařízeních, a odkaz v Outlooku funguje podle očekávání.
- Uživatel otevře Microsoft Edge na jejich iOS nebo zařízení s Androidem. Pokud je pak chráněn rozhraním Intune Microsoft Edge a Proxy aplikací je povoleno, uživatel přejít na intranetový server pomocí interní adresy URL se používají k. Microsoft Edge rozpozná, že tento intranetový server byl zpřístupněn prostřednictvím Proxy aplikací uživateli. Uživatel je automaticky přesměrován prostřednictvím Proxy aplikací k ověření před dosažením intranetový server. 

### <a name="before-you-start"></a>Než začnete

- Nastavte svoje interní aplikace prostřednictvím Proxy aplikací Azure AD.
    - Postup konfigurace proxy aplikací a publikování aplikací najdete v [dokumentaci k instalaci](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).
- Aplikace Microsoft Edge musí mít [zásady ochrany aplikací Intune](app-protection-policy.md) přiřazené.

> [!NOTE]
> Aktualizovaným datům přesměrování proxy aplikací může trvat až 24 hodin, než se projeví v aplikaci Managed Browser nebo Microsoft Edge.

#### <a name="step-1-enable-automatic-redirection-to-microsoft-edge-from-outlook"></a>Krok 1: Povolit automatické přesměrování z Outlooku pro Microsoft Edge
Zásady ochrany aplikací, který umožňuje nastavení konfigurace aplikace Outlook **sdílená složka webového obsahu pomocí zásad spravovaného prohlížeče**.

![Zásady ochrany aplikací – snímek obrazovky – sdílená složka webového obsahu se zásadami spravovaných prohlížečů](./media/manage-microsoft-edge/manage-microsoft-edge-03.png)

#### <a name="step-2-set-the-app-configuration-setting-to-enable-app-proxy"></a>Krok 2: Nastavení konfigurace aplikace pro povolení proxy aplikace
Cílová Microsoft Edge s následující dvojici klíč/hodnota k povolení Proxy aplikace pro Microsoft Edge:

|    Klíč    |    Value    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.AppProxyRedirection    |    true (pravda)    |

Další informace o tom, jak používat Microsoft Edge a Proxy aplikací Azure AD při vytvoření celostní pro bezproblémové (a chráněného) přístupu k místním webovým aplikacím, najdete v části [společně ještě lepší: Intune and Azure Active Directory team up to improve user access](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access) (Ve dvou se to lépe táhne: Intune a Azure Active Directory společně vylepšují uživatelský přístup). Tento blogový příspěvek odkazy Intune Managed Browser, ale obsah platí i pro Microsoft Edge.

## <a name="configure-a-homepage-shortcut-for-microsoft-edge"></a>Konfigurovat místní domovské stránky pro Microsoft Edge

Toto nastavení umožňuje nakonfigurovat domovskou stránku zástupce pro Microsoft Edge. Když uživatel otevře na nové kartě v Microsoft Edge, zobrazí se jako první ikona pod vyhledávacího zástupce domovské stránky, které nakonfigurujete. Uživatel nemůže upravit nebo odstranit tento zástupce v daném kontextu se spravované. Místní domovské stránce se zobrazí název vaší organizace, aby se odlišil. 

Ke konfiguraci místní domovské stránky použijte následující dvojici klíč/hodnota:

|    Klíč    |    Value    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.homepage   |    Zadejte platnou adresu URL. Nesprávné adresy URL se z bezpečnostních důvodů blokují.<br>**Příklad:**  <`https://www.bing.com`>
    |

## <a name="configure-managed-bookmarks-for-microsoft-edge"></a>Konfigurace spravovaných záložky pro Microsoft Edge

Pro usnadnění přístupu můžete nakonfigurovat záložek, které chcete vaši uživatelé měli k dispozici při používání Microsoft Edge. 

Tady jsou některé podrobnosti:

- Tyto záložky se zobrazí pouze pro uživatele, pokud uživatelé používají firemní režimu Microsoft Edge. 
- Tyto záložky nelze odstranit ani upravit uživatele.
- Tyto záložky se zobrazí v horní části seznamu. Všechny záložky vytvořené uživateli se zobrazí pod těmito záložkami.
- Pokud jste povolili přesměrování Proxy aplikací, můžete přidat Proxy aplikací webové aplikace pomocí jejich interní nebo externí adresy URL.

Ke konfiguraci spravovaných záložky použijte následující dvojici klíč/hodnota:

|    Klíč    |    Hodnota    |
|---------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.bookmarks    |    Hodnota pro tuto konfiguraci je seznam záložek. Každou záložku tvoří název záložky a adresa URL záložky. Oddělení název a adresu URL `|` znak.      Příklad:<br>`Microsoft Bing|https://www.bing.com`<br>Chcete-li nakonfigurovat více záložek, oddělte každý pár těmito dvěma znaky `||`.<p>Příklad:<br>`Microsoft Bing|https://www.bing.com||Contoso|https://www.contoso.com`    |

## <a name="display-myapps-within-microsoft-edge-bookmarks"></a>MyApps se zobrazí v rámci záložek Microsoft Edge

Ve výchozím nastavení se uživatelům zobrazí MyApps weby, které jsou nakonfigurované k nim v rámci složky uvnitř záložky Microsoft Edge. Složka je označen názvem vaší organizace.

|    Klíč    |    Value    |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.MyApps    |    **Hodnota TRUE** ukazuje MyApps v rámci záložek Microsoft Edge.<p>**False** skryje MyApps v rámci Microsoft Edge.    |

## <a name="specify-allowed-or-blocked-sites-list-for-microsoft-edge"></a>Zadejte seznam povolených nebo blokovaných webů pro Microsoft Edge
Konfigurace aplikací můžete použít k definování weby, které uživatelé přístup při používání jejich pracovního profilu. Pokud používáte seznam povolených, jsou vaši uživatelé jenom může přistupovat k webům, které jste uvedli explicitně. Pokud používáte seznam blokovaných aplikací, vaši uživatelé můžou používat všechny weby kromě těch, které jste explicitně blokovaný. By měl pouze kladou povolený nebo blokovaný seznamu, ne obojí. Pokud obě uložit, je na seznamu povolených dodržena.  

Pomocí následující dvojice klíč/hodnota můžete nakonfigurovat buď seznam povolených nebo blokovaných webů pro Microsoft Edge. 

|    Klíč    |    Value    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Vybírejte z těchto možností:<p>1. Určení povolených adres URL (povolené jsou pouze tyto adresy URL; na žádné jiné weby nebudou mít uživatelé přístup):<br>`com.microsoft.intune.mam.managedbrowser.AllowListURLs`<p>2. Určení blokovaných adres URL (na všechny ostatní weby budou mít uživatelé přístup):<br>`com.microsoft.intune.mam.managedbrowser.BlockListURLs`    |    Odpovídající hodnotou klíče je seznam adres URL. Zadejte všechny adresy URL, kterou chcete povolit nebo blokovat, jako jedinou hodnotu, která je oddělená znakem | `|` znak.<br>**Příklady:**<br>`URL1|URL2|URL3`<br>`http://.contoso.com/|https://.bing.com/|https://expenses.contoso.com`  |

### <a name="url-formats-for-allowed-and-blocked-site-list"></a>Formátech adres URL pro povolené a blokované seznam webů 
Různých formátech adres URL můžete použít k vytváření seznamů povolených/zakázaných webů. Tyto povolené vzory jsou podrobně popsané v následující tabulce. Několik poznámek před zahájením práce: 
- Při zadávání adres URL do seznamu nezapomeňte u všech uvést předponu **http** nebo **https**.
- Můžete použít zástupný znak (\*) podle pravidel v následujícím seznamu povolených vzorů.
- Zástupný znak odpovídá pouze celá součást název hostitele (oddělených tečkami) nebo celé části cesty (oddělené lomítkem). Například `http://*contoso.com` je **není** podporována.
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
    |    `http://www.contoso.com:80`    |    Odpovídá jediné stránce s použitím čísla portu    |    `http://www.contoso.com:80`    |         |
    |    `https://www.contoso.com`    |    Odpovídá jediné zabezpečené stránce    |    `https://www.contoso.com`    |    `http://www.contoso.com`    |
    |    `http://www.contoso.com/images/*`    |    Odpovídá jediné složce a všem podsložkám    |    `www.contoso.com/images/dogs`<br>`www.contoso.com/images/cats`    |    `www.contoso.com/videos`    |
  
- Následují příklady některých vstupních hodnot, které nelze zadat:
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
  
## <a name="define-behavior-when-users-try-to-access-a-blocked-site"></a>Definovat chování, když se uživatelé pokusí o přístup k zablokování webu

S modelem identity dvou součástí Microsoft Edge můžete povolit více flexibilní prostředí pro koncové uživatele, než bylo možné s Intune Managed Browser. Když uživatelé dostat blokované webu v Microsoft Edge, může vyzvat je tak, aby na odkaz v jejich osobní kontext místo jejich práci. Díky tomu k zajištění své ochrany, a zajistit přitom ochranu firemních prostředků bezpečné. Například pokud uživatel je odkazem na příspěvek prostřednictvím aplikace Outlook, mohou otevřít odkaz v daném kontextu se osobní nebo se službou InPrivate kartě. Jejich práci neumožňuje websites zprávy. Ve výchozím nastavení jsou povoleny tyto přechody.

Pokud chcete konfigurovat, jestli jsou povolené tyto softwarové přechody použijte následující dvojici klíč/hodnota:

|    Klíč    |    Hodnota    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock`    |    **Hodnota TRUE** Microsoft Edge umožňuje přechod uživatelům na jejich osobní kontext spuštěním blokovaných webů.<p>**Blok** brání přechod od uživatelů Microsoft Edge. Uživatelům se jednoduše zobrazí zprávu s informacemi o tom, že je blokované na webu, který se pokoušíte získat přístup.    |

## <a name="use-microsoft-edge-on-ios-to-access-managed-app-logs"></a>Použijte Microsoft Edge pro přístup k protokolům spravovaných aplikací v Iosu 

Uživatelé s Microsoft Edge nainstalovaný na zařízení s Iosem můžete zobrazit stav správy všech aplikací publikovaných Microsoftem. Můžou posílat protokoly kvůli řešení problémů se spravovanými aplikacemi pro iOS. Tady je postup:
1. Otevřete Microsoft Edge na zařízení s Iosem.
2. Do pole adresy zadejte `about:intunehelp`. 
3. Microsoft Edge spustí režim pro řešení problémů.

Seznam nastavení uložených v aplikačních protokolech najdete v tématu [Kontrola protokolů ochrany aplikace v aplikaci Managed Browser](app-protection-policy-settings-log.md).

Postup zobrazení protokolů na zařízeních s Androidem, najdete v sekci [odeslání protokolů správci IT e-mailem](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). 

## <a name="security-and-privacy-for-microsoft-edge"></a>Zabezpečení a ochrana osobních údajů pro Microsoft Edge

Následují další aspekty zabezpečení a ochrany osobních údajů pro Microsoft Edge:

- Microsoft Edge nespotřeboval nastavení, která uživatelům nastavit pro nativní prohlížeč na svých zařízeních, protože Microsoft Edge nemá přístup k nastavení.
- Můžete nakonfigurovat možnost **vyžadovat pro přístup jednoduchý PIN kód** nebo **vyžadovat pro přístup podnikové přihlašovací údaje** v Microsoft Edge přidružené zásady ochrany aplikací. Pokud uživatel vybere na stránce ověřování na odkaz nápovědy, mohli procházet libovolné weby bez ohledu na to, zda byly přidány na seznam blokovaných aplikací v zásadách.
- Microsoft Edge může blokovat přístup k webům, pouze v případě, že jsou k nim přistupuje přímo. Neblokuje přístup uživatelé budou používat pro přístup k webu přistupuje přes zprostředkující služby (třeba překladatelské služby).
- Povolení ověřování a přístup k dokumentaci k Intune * **. microsoft.com** se vyjímá z nastavení seznamu povolených nebo blokovaných. Je vždycky povolená.
- Uživatele můžete vypnout shromažďování dat. Microsoft automaticky shromažďuje anonymní informace o výkonu a využití aplikace Managed Browser za účelem zlepšení svých produktů a služeb. Uživatelé můžou shromažďování těchto dat na svých zařízeních vypnout pomocí nastavení **Data o využití**. Nad shromažďováním těchto dat nemáte žádnou kontrolu. V zařízení s Iosem se nedají otevřít weby, které uživatelé navštíví, s vypršenou platností nebo nedůvěryhodných certifikátů.

## <a name="next-steps"></a>Další postup

- [Co jsou zásady ochrany aplikací?](app-protection-policy.md) 
