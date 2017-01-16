---
title: "Připojení VPN | Dokumentace Microsoftu"
description: "K nasazení nastavení VPN pro uživatele a zařízení ve vaší organizaci použijte profily VPN."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0ba06e1d698e051ba72e9f88a654d37041c57cf1
ms.openlocfilehash: cd9785889ca8b2a78a49ea2b04284d32b3fa8a65


---

# <a name="vpn-connections-in-microsoft-intune"></a>Připojení VPN v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Virtuální privátní sítě (VPN) umožňují uživatelům zabezpečený vzdálený přístup k firemní síti. K navázání připojení se serverem VPN používají zařízení *profil připojení VPN*. Pomocí *profilů VPN* v Microsoft Intune můžete uživatelům a zařízením v organizaci nasadit nastavení VPN, aby se mohli snadno a bezpečně připojit k síti.

Chcete třeba zřizovat všechna zařízení s iOSem s nastavením požadovaným pro připojení sdílené položky souboru v podnikové síti. Vytvoříte profil VPN s nastavením nezbytným pro připojování k podnikové síti, a potom tento profil nasadíte u všech uživatelů se zařízeními iOS. Uživatelé uvidí připojení VPN v seznamu dostupných sítí a můžou se připojit s minimálním úsilím.

Pomocí profilů VPN můžete konfigurovat následující typy zařízení:

* Zařízení se systémem Android 4 nebo novější verzí
* Zařízení se systémem Android for Work
* Zařízení se systémem iOS 8.0 nebo novější verzí
* Zařízení se systémem Mac OS X 10.9 nebo novější verzí
* Zaregistrovaná zařízení se systémem Windows 8.1 a novějším
* Zařízení s Windows Phone 8.1 a novějším
* Zařízení s Windows 10 Desktop a Mobile

Možnosti konfigurace profilu VPN se liší podle vybraného typu zařízení.

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

## <a name="vpn-connection-types"></a>Typy připojení VPN

Intune podporuje vytváření profilů VPN, které používají následující typy připojení:




Typ připojení |iOS a Mac OS X  |Android a Android for Work|Windows 8.1|Windows RT 8.1|Windows Phone 8.1|Windows 10 Desktop a Mobile |
----------------|------------------|-------|-----------|----------|--------------|-----------------|----------------------|
Cisco AnyConnect|Ano |Ano   |Ne    |Ne  |Ne    | Ano (OMA-URI, jenom Mobile)|     
Cisco (IPsec)|Ano |Ano   |Ne  |Ne  |Ne | Ne|
Citrix|Ano |Ne   |Ne  |Ne  |Ne | Ne|
Pulse Secure|Ano  |Ano |Ano   |Ano  |Ano| Ano|        
F5 Edge Client|Ano |Ano |Ano |Ano  |   Ano |  Ano|   
Dell SonicWALL Mobile Connect|Ano |Ano |Ano |Ano |Ano |Ano|         
CheckPoint Mobile VPN|Ano |Ano |Ano |Ano|Ano|Ano|
Protokol SSL společnosti Microsoft (SSTP)|Ne |Ne |Ne |Ne|Ne|VPNv1 OMA-URI*|
Automaticky pomocí technologie Microsoft|Ne |Ne |Ne |Ne|Ano (OMA-URI)|Ano|
IKEv2|Vlastní profil iOS|Ne |Ne |Ne|Ano (OMA-URI)|Ano|
PPTP|Vlastní profil iOS|Ne |Ne |Ne|Ne|Ano|
L2TP|Vlastní profil iOS|Ne |Ne |Ne|Ano (OMA-URI)|Ano|

\* Bez dalšího nastavení, které je jinak dostupné pro Windows 10.

> [!IMPORTANT]
> Před použitím profilů VPN nasazených do zařízení je nutné nainstalovat příslušnou aplikaci VPN pro profil. Informace z tématu [Nasazení aplikací v Microsoft Intune](deploy-apps-in-microsoft-intune.md) vám můžou pomoct s nasazením správné aplikace pomocí Intune.  

 Postup vytváření vlastních profilů VPN pomocí nastavení URI najdete v tématu [Vlastní konfigurace pro profily VPN](create-custom-vpn-profiles.md).     

## <a name="methods-of-securing-vpn-profiles"></a>Metody zabezpečení profilů VPN

Profily VPN můžou používat spoustu různých typů připojení a protokoly od různých výrobců. Tato připojení jsou obvykle zabezpečená jedním ze dvou způsobů.

### <a name="certificates"></a>Certifikáty

Když vytváříte profil VPN, vybíráte profil certifikátu SCEP nebo PFX, který jste předtím vytvořili v Intune. Označuje se jako certifikát identity. Slouží k ověřování vůči profilu důvěryhodného certifikátu (neboli *kořenového certifikátu*), jehož vytvořením jste potvrdili, že se zařízení uživatele může připojit. Důvěryhodný certifikát je nasazený na počítači, který ověřuje připojení VPN, většinou na serveru VPN.

Další informace o vytváření a používání profilů certifikátů v Intune najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů](secure-resource-access-with-certificate-profiles.md).

### <a name="user-name-and-password"></a>Uživatelské jméno a heslo

Uživatel se ověřuje na serveru sítě VPN zadáním uživatelského jména a hesla.

## <a name="create-a-vpn-profile"></a>Vytvoření profilu sítě VPN

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Zásady** > **Přidat zásadu**.
2. Vyberte šablonu pro nové zásady rozšířením příslušného typu zařízení a potom vyberte profil sítě VPN pro toto zařízení:
    * **Profil VPN (Android 4 a novější)**
    * **Profil VPN (Android for Work)**
    * **Profil VPN (iOS 8.0 a novější)**
    * **Profil VPN (Mac OS X 10.9 a novější)**
    * **Profil VPN (Windows Phone 8.1 a novější)**
    * **Profil VPN (Windows Phone 8.1 a novější)**
    * **Profil VPN (Windows 10 Desktop a Mobile a novější)**

 Můžete vytvořit a nasadit jenom vlastní zásadu profilu VPN. Doporučená nastavení nejsou dostupná.

> [!Note]
> Profil VPN pro zařízení s Androidem for Work umožní připojení VPN jenom aplikacím, které jsou nainstalované v pracovním profilu zařízení.
>
> Některé typy připojení VPN podporují VPN pro jednotlivé aplikace pro zařízení s Androidem for Work a povolují VPN pro jednotlivé aplikace u aplikací distribuovaných prostřednictvím služby Intune.  

3. S konfigurací nastavení profilu VPN vám pomůže následující tabulka:

Název nastavení  |Další informace  
---------|---------
**Název**     |Zadejte jedinečný název profilu sítě VPN, který vám pomůže ho v konzole Intune rozpoznat.         
**Popis**     |Zadejte popis, který bude shrnovat účel profilu VPN, a uveďte jakékoli další důležité informace, které vám pomůžou ho najít.         
**Název připojení VPN (zobrazený uživatelům)**     |Zadejte jméno nebo název profilu VPN. Toto je název, který se uživatelům zobrazí v seznamu dostupných připojení VPN na zařízeních.         
**Typ připojení**     |  Vyberte jeden z následujících typů připojení pro použití s profilem VPN: **Cisco AnyConnect** (není k dispozici pro Windows 8.1 nebo Windows Phone 8.1), **Pulse Secure**, **Citrix**, **F5 Edge Client**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**.
**Popis serveru VPN**     | Zadejte popis serveru VPN, ke kterému se budou zařízení připojovat. Příklad: **Contoso VPN Server**. Pokud je typ připojení **F5 Edge Client**, použijte pro zadání seznamu popisů a IP adres serveru pole **Seznam serverů**.
**IP adresa nebo plně kvalifikovaný název domény (FQDN) serveru**    |Zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se bude zařízení připojovat. Příklady: **192.168.1.1**, **vpn.contoso.com**.  Pokud je typ připojení **F5 Edge Client**, použijte pro zadání seznamu popisů a IP adres serveru pole **Seznam serverů**.         |         
**Seznam serverů**     |Zvolením možnosti **Přidat** přidejte nový server sítě VPN určený pro připojení k síti VPN. Můžete taky určit, který server bude pro připojení výchozí. Tato možnost se zobrazí, jenom když je typ připojení **F5 Edge Client**.         
**Odesílat veškerý přenos v síti prostřednictvím připojení VPN**     |Pokud vyberete tuto možnost, všechny síťové přenosy se budou odesílat prostřednictvím připojení VPN. Pokud tuto možnost nevyberete, klient bude dynamicky vyjednávat trasy pro dělené tunelové propojení při připojování k serveru sítě VPN jiného výrobce. Prostřednictvím tunelu VPN se odesílají pouze připojení k firemní síti. Tunelové propojení VPN se nepoužívá při připojení k prostředkům na Internetu.
**Metoda ověřování**| Vyberte metodu ověřování používanou pro připojení VPN: **Certifikáty** nebo **Uživatelské jméno a heslo**. (Nastavení **Uživatelské jméno a heslo** není dostupné, pokud je typ připojení Cisco AnyConnect.) Možnost **Metoda ověřování** není dostupná pro Windows 8.1.
**Zapamatovat si přihlašovací údaje při každém přihlášení**|Výběrem této možnosti zajistíte, že se přihlašovací údaje uživatele uloží, takže je uživatel nebude muset zadávat při každém navázání připojení.
**Vyberte klientský certifikát pro ověření klienta (certifikát identity)**|Vyberte certifikát klienta SCEP, který jste dříve vytvořili a který se použije k ověření připojení VPN. Další informace o použití profilů certifikátů v Intune najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md). Tato možnost se zobrazí jenom v případě, že je metoda ověřování **Certifikáty**.
**Role**| Zadejte název role uživatele, který má přístup k tomuto připojení. Role uživatele definuje osobní nastavení a možnosti a povolí nebo zakáže určité funkce přístupu. Tato možnost se zobrazí jenom v případě, že typ připojení je **Pulse Secure** nebo **Citrix**.
**Sféra**|Zadejte název sféry ověření, kterou chcete použít. Sféra ověření je seskupení prostředků ověření používaných typem připojení Pulse Secure nebo Citrix. Tato možnost se zobrazí jenom v případě, že typ připojení je **Pulse Secure** nebo **Citrix**.
**Doména nebo skupina přihlášení**|Zadejte název domény nebo skupiny přihlášení, k níž se chcete připojit. Tato možnost se zobrazí jenom v případě, že se je typ připojení **Dell SonicWALL Mobile Connect**.
**Otisk prstu**|Zadejte řetězec, například „Kód otisku prstu Contoso“, který se použije k ověření, že je možné serveru VPN důvěřovat. Otisk prstu se může odeslat klientovi, aby věděl, že může důvěřovat jakémukoli serveru, který při připojování nabízí ten samý otisk. Pokud zařízení ještě otisk prstu nemá, vyzve uživatele, aby důvěřoval serveru VPN, ke kterému se připojuje. Současně přitom zobrazuje otisk prstu. (Uživatel ho ručně ověří a zvolí **důvěryhodnost** připojení.) Tato možnost se zobrazuje jenom v případě, že je typ připojení **Kontrolní bod – mobilní síť VPN**.
**VPN na aplikaci**|Tuto možnost vyberte, pokud chcete toto připojení VPN přidružit k aplikaci pro iOS nebo Mac OS X tak, aby se připojení otevřelo při spuštění aplikace. Profil VPN je možné přidružit k aplikaci při nasazení softwaru. Další informace najdete v tématu [Nasazení aplikací v Microsoft Intune](deploy-apps-in-microsoft-intune.md).
**VPN na vyžádání**|VPN na vyžádání můžete nastavit pro zařízení s iOSem 8.0 a novější verzí. Pokyny pro toto nastavení jsou uvedené v článku [VPN na vyžádání pro zařízení s iOS](#on-demand-vpn-for-ios-devices).
**Automaticky zjišťovat nastavení proxy** (jenom iOS, Mac OS X, Windows 8.1 a Windows Phone 8.1)|Pokud server VPN vyžaduje pro připojení proxy server, zadejte, určete, jestli mají zařízení automaticky zjišťovat nastavení připojení. Další informace najdete v dokumentaci k Windows Serveru.
**Použít automatický konfigurační skript** (jenom iOS, Mac OS X, Windows 8.1 a Windows Phone 8.1)|Pokud server VPN vyžaduje pro připojení proxy server, určete, jestli chcete k definování nastavení použít automatický konfigurační skript, a pak zadejte adresu URL souboru, který obsahuje nastavení. Další informace najdete v dokumentaci k Windows Serveru.
**Použít proxy server** (jenom iOS, Mac OS X, Windows 8.1 a Windows Phone 8.1)|Pokud server VPN vyžaduje pro připojení proxy server, vyberte tuto možnost a potom zadejte adresu a číslo portu proxy serveru. Další informace najdete v dokumentaci k Windows Serveru.
**Nepoužívat nastavení proxy pro místní adresy** (jenom iOS, Mac OS X, Windows 8.1 a Windows Phone 8.1)|Pokud VPN server vyžaduje pro připojení proxy server, vyberte tuto možnost, když nechcete používat proxy server pro místní adresy, které zadáte. Další informace najdete v dokumentaci k Windows Serveru.
**Vlastní XML** (jenom Windows 8.1 a novější a Windows Phone 8.1 a novější)|Zadejte vlastní příkazy XML, které konfigurují připojení VPN. Příklad pro **Pulse Secure**: &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. Příklad pro **CheckPoint Mobile VPN**: &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true"  debug="3" /&gt;. Příklad pro **Dell SonicWALL Mobile Connect**: &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. Příklad pro **F5 Edge Client**: &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;. Další informace o tom, jak psát vlastní příkazy XML, najdete v dokumentaci k síti VPN jednotlivých výrobců.
**Seznam hledání přípon DNS** (jenom Windows Phone 8.1)|Zadejte jednu příponu DNS na každém řádku. Každá zadaná přípona DNS se bude vyhledávat při připojení k webu pomocí krátkého názvu. Například když zadáte přípony DNS **domain1.contoso.com** a **domain2.contoso.com** a navštívíte adresu **http://mywebsite**, vyhledají se adresy **http://mywebsite.domain1.contoso.com** a **http://mywebsite.domain2.contoso.com**.
**Obcházet VPN při připojení k síti Wi-Fi společnosti** (jenom Windows Phone 8.1)|Výběrem této možnosti určíte, že se připojení VPN nebude používat při připojení zařízení k podnikové síti Wi-Fi.
**Obcházet VPN při připojení k domácí síti Wi-Fi** (jenom Windows Phone 8.1)|Výběrem této možnosti určíte, že se připojení VPN nebude používat při připojení zařízení k domácí síti Wi-Fi.

Pro desktopová a mobilní zařízení s Windows 10 jsou dostupná následující dodatečná nastavení.

Název nastavení  |Další informace  
---------|---------
**Pravidla pro provoz sítě**|Vyberte, které protokoly a které rozsahy místních a vzdálených portů a adres budou povolené pro připojení VPN. Když nevytvoříte pravidlo pro provoz sítě, budou povolené všechny protokoly, porty a rozsahy adres. Po vytvoření pravidla se pro připojení VPN použijí jenom protokoly, porty a rozsahy adres, které určíte v tomto pravidle.
**Trasy**|Vyberte, které trasy budou používat připojení VPN.
**Servery DNS**| Vyberte, které servery DNS bude připojení VPN po vytvoření připojení.         
**Přidružené aplikace**|Zadejte seznam aplikací, které budou automaticky používat připojení VPN. Typ aplikace bude určovat identifikátor aplikace. Pro univerzální aplikace zadejte identitu aplikace (PFN). Pro desktopové aplikace zadejte cestu k souboru aplikace.          


> [!IMPORTANT]
> Doporučujeme zabezpečit všechny seznamy aplikací, které zkompilujete pro použití v konfiguraci sítě VPN pro jednotlivé aplikace. Pokud seznam upraví neoprávněný uživatel a vy seznam naimportujete do seznamu aplikací sítě VPN pro jednotlivé aplikace, potenciálně tím autorizujete přístup k síti VPN pro aplikace, které by přístup mít neměly. Jedním ze způsobů, jak zabezpečit seznamy aplikací, je použít seznam řízení přístupu (ACL).

Tady je příklad, kdy můžete použít nastavení podnikových hranic. Když chcete povolit VPN jenom pro vzdálenou plochu, vytvořte pravidlo pro provoz sítě, které umožňuje přenos pro protokol 27 na externím portu 3996. Žádný jiný provoz nebude síť VPN používat.

Definování tras v podnikových hranicích je užitečné, když typ připojení VPN neumožňuje určit, jak se provoz zpracovává při děleném tunelovém propojení. V takovém případě použijte **Trasy** k výpisu tras, které budou používat síť VPN.

Vytvořením vlastního nastavení OMA-URI můžete omezit využití sítě VPN zařízením s Windows 10 na konkrétní aplikace.

Nová zásada se zobrazí v uzlu **Zásady konfigurace** pracovního prostoru **Zásady**.

### <a name="on-demand-vpn-for-ios-devices"></a>VPN na vyžádání pro zařízení s iOS
VPN na vyžádání můžete konfigurovat pro zařízení s iOSem 8.0 a novější verzí.

> [!NOTE]
>  
> VPN pro aplikaci a VPN na vyžádání nemůžete použít ve stejných zásadách.

1. Na stránce konfigurace zásad najděte **Pravidla pro připojení na vyžádání pro toto připojení VPN**. Sloupce jsou označeny **Shoda** – podmínka, kterou pravidla kontrolují, a **Akce** – akce, kterou zásady spustí při splnění podmínky.
2. Zvolte **Přidat** a vytvořte pravidlo. Existují dva typy shod, které v pravidle můžete nastavit. V jednotlivém pravidle můžete konfigurovat pouze jeden z těchto typů.
  - **SSID**, který odkazuje na bezdrátové sítě.
  - **Domény pro hledání DNS**, které jsou...  Můžete použít plně kvalifikované názvy domény, například *team. corp.contoso.com*, nebo můžete použít domény, například *contoso.com*, které jsou obdobou použití * *.contoso.com*.
3. Volitelné: Zadejte test řetězce adresy URL, což je adresa URL, kterou pravidlo používá jako test. Pokud zařízení, na kterém je tento profil nainstalovaný, má k této adrese URL přístup bez přesměrování, naváže se připojení VPN a zařízení se připojí k cílové adrese URL. Uživatel neuvidí web testu řetězce adresy URL. Příkladem testu řetězce adresy URL je adresa auditujícího webového serveru, který zkontroluje splnění bezpečnostních předpisů zařízením předtím, než ho připojí k VPN. Další možností je, že adresa URL otestuje schopnost VPN připojit se k webu předtím, než se zařízení připojí k cílové adrese URL skrze VPN.
4. Vyberte jednu z těchto akcí:
  - **Připojit**
  - **Vyhodnotit připojení**, která má tři nastavení. a. **Akce domény** – zvolte **Připojit v případě potřeby** nebo **Nikdy nepřipojovat**.
     b. **Čárkami oddělený seznam domén** – Toto konfigurujete jenom v případě, že zvolíte **Akce domény** v možnosti **Připojit v případě potřeby**. 
     c. **Požadovaný test řetězce adresy URL** – Adresa URL protokolu HTTP nebo HTTPS (upřednostňováno), například *https://vpntestprobe.contoso.com*. Pravidlo zkontroluje, jestli z této adresy přichází odezva. Pokud ne a **Akce domény** je nastavená na **Připojit v případě potřeby**, spustí se VPN.
     > [!TIP]
     >
     >Příkladem použití této akce je situace, kdy některé weby v podnikové síti vyžadují přímé připojení nebo VPN připojení k podnikové síti, ale jiné to nepožadují. Pokud v **Čárkami odděleném seznamu domén pro hledání DNS** uvedete *corp.contoso.com*, můžete zvolit **Připojit v případě potřeby** a potom uvést seznam konkrétních webů v rámci této sítě, které mohou vyžadovat VPN, například *sharepoint.corp.contoso.com*. Pravidlo potom zkontrolujte dostupnost adresy *vpntestprobe.contoso.com*. V případě nedostupnosti se aktivuje VPN pro daný web SharePoint.
  - **Ignorovat** – Způsobí ignorování jakýchkoli změn v připojení VPN. Pokud je VPN připojená, nechat ji připojenou, pokud není připojená, nepřipojovat. Můžete mít například pravidlo, které připojuje VPN pro všechny interní podnikové weby, ale chcete jeden z těchto interních webů zpřístupnit jenom v případě, kdy je zařízení skutečně připojené k podnikové síti. V takovém případě vytvoříte pravidlo ignorování pro tento jeden web.
  - **Odpojit** – Při splnění podmínek odpojí zařízení od VPN. Do pole **SSID** můžete například uvést podnikové bezdrátové sítě a vytvořit pravidlo, které zařízení odpojí od VPN, když se připojí k jedné z těchto sítí.

Pravidla pro konkrétní domény se vyhodnocují před pravidly pro všechny domény.


## <a name="deploy-the-policy"></a>Nasazení zásady

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a potom vyberte **Spravovat nasazení**.

2.  V dialogovém okně **Spravovat nasazení** :

    -   Pokud chcete zásadu nasadit, vyberte jednu nebo několik skupin, do kterých chcete zásady nasadit, a potom vyberte **Přidat** &gt; **OK**.

    -   Pokud chcete dialogové okno zavřít bez nasazení zásady, zvolte **Zrušit**.


Po úspěšné nasazení se uživatelům zobrazí název připojení VPN, který jste zadali v seznamu připojení VPN na jejich zařízeních.

Shrnutí stavu a výstrahy na stránce **Přehled** v pracovním prostoru **Zásady** identifikují problémy se zásadami, které vyžadují vaši pozornost. Kromě toho se v pracovním prostoru Řídicí panel zobrazí shrnutí stavu.





<!--HONumber=Dec16_HO3-->


