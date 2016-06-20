---
# required metadata

title: Připojení VPN | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Připojení VPN v Microsoft Intune
 Virtuální privátní sítě (VPN) umožňují uživatelům poskytovat zabezpečený vzdálený přístup k podnikové síti. Vzdálení uživatelé můžou pracovat, jako kdyby jejich zařízení bylo fyzicky připojené k síti. Zařízení používají profil připojení VPN k navázání připojení se serverem VPN. K nasazení nastavení VPN pro uživatele a zařízení v organizaci použijte **VPN profily** v Microsoft Intune. Nasazením těchto nastavení zjednodušíte koncovým uživatelům připojování k prostředkům v síti společnosti.

Chcete třeba zřizovat všechna zařízení s iOS s nastavením požadovaným pro připojení sdílené položky souboru v podnikové síti. Vytvoříte profil VPN s nastavením nezbytným pro připojování k podnikové síti a potom tento profil nasadíte u všech uživatelů se zařízeními iOS. Uživatelé uvidí připojení VPN v seznamu dostupných sítí a můžou se připojit s minimálním úsilím.

Profily sítě VPN můžete konfigurovat pro následující typy zařízení:

* Zařízení se systémem Android 4 nebo novější verzí
* Zařízení se systémem iOS 7.1 nebo novější verzí
* Zařízení se systémem Mac OS X 10.9 nebo novější verzí
* Zaregistrovaná zařízení se systémem Windows 8.1 a novějším
* Zařízení s Windows Phone 8.1 a novějším
* Zařízení s Windows 10 Desktop a Mobile

Možnosti konfigurace profilu VPN jsou různé podle vybraného typu zařízení.

## Typy připojení VPN

Intune podporuje vytváření profilů VPN, které používají následující typy připojení:




Typ připojení |iOS a Mac OS X  |Android  |Windows 8.1|Windows RT|Windows RT 8.1|Windows Phone 8.1  |Windows 10 Desktop a Mobile |
---------|---------|---------|---------|---------|---------
Cisco AnyConnect |Ano |Ano   |Ne    |     Ne    |Ne  |Ne    | Ano, (OMA-URI, jenom Mobile)|     
Pulse Secure |Ano  |Ano |Ano   |Ne  |Ano  |Ano| Ano|        
F5 Edge Client |Ano |Ano |Ano |Ne  |Ano  |   Ano |  Ano|   
Dell SonicWALL Mobile Connect |Ano |Ano |Ano |Ne  |Ano |Ano |Ano|         
CheckPoint Mobile VPN |Ano |Ano |Ano |Ano |Ano|Ano|Ano|




> [!IMPORTANT] Před použitím profilů VPN nasazených do zařízení je nutné nainstalovat příslušnou aplikaci VPN pro profil. Informace z tématu [Nasazení aplikací v Microsoft Intune](deploy-apps-in-microsoft-intune.md) vám můžou pomoct s nasazením správné aplikace pomocí Intune.  

 Postup vytváření vlastních profilů VPN pomocí nastavení URI najdete v tématu [Vlastní konfigurace pro profily VPN](custom-configurations-for-vpn-profiles.md).     

## Jak jsou zabezpečené profily VPN

Profily VPN můžou používat spoustu různých typů připojení a protokoly od různých výrobců. Tato připojení jsou obvykle zabezpečená jedním ze dvou způsobů:

### Certifikáty

Když vytváříte profil VPN, vybíráte profil certifikátu SCEP nebo .PFX, který jste předtím vytvořili v Intune.

Je známý jako certifikát identity a slouží k ověřování na základě důvěryhodného profilu certifikátu (neboli kořenového certifikátu), který jste vytvořili pro zajištění, že má zařízení uživatele dovoleno připojovat se. Důvěryhodný certifikát je nasazený na počítači, který ověřuje připojení VPN, většinou na serveru VPN.

Další informace o vytváření a používání profilů certifikátů v Intune najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů](secure-resource-access-with-certificate-profiles.md).

### Uživatelské jméno a heslo

Uživatel se ověřuje na serveru sítě VPN zadáním uživatelského jména a hesla.

## Vytvoření profilu sítě VPN

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com)klikněte na **Zásady > Přidat zásadu**..
2. Vyberte šablonu pro nové zásady rozšířením příslušného typu zařízení a potom vyberte profil sítě VPN pro toto zařízení:
    * **Profil VPN (Android 4 a novější)**
    * **Profil VPN (iOS 7.1 a novější)**
    * **Profil sítě VPN (Mac OS X 10.9 a novější)**
    * **Profil VPN (Windows Phone 8.1 a novější)**
    * **Profil VPN (Windows Phone 8.1 a novější)**
    * **Profil VPN (Windows 10 Desktop a Mobile a novější)**

    Můžete vytvořit a nasadit jenom vlastní zásadu profilu VPN. Doporučená nastavení nejsou dostupná.

3. S konfigurací nastavení profilu VPN vám pomůže následující tabulka:

Název nastavení  |Další informace  
---------|---------
**Název**     |Zadejte jedinečný název profilu sítě VPN, který vám pomůže ho v konzole Intune rozpoznat.         
**Popis**     |Zadejte popis, který bude shrnovat účel profilu VPN, a uveďte jakékoli další důležité informace, které vám pomůžou ho najít.         
**Název připojení VPN (zobrazený uživatelům)**     |Zadejte jméno nebo název profilu VPN. Toto je název, který se uživatelům zobrazí v seznamu dostupných připojení VPN na zařízeních.         
**Typ připojení**     |  Vyberte jeden z následujících typů připojení pro použití s profilem VPN: **Cisco AnyConnect** (není k dispozici pro Windows 8.1 nebo Windows Phone 8.1), **Pulse Secure**, **F5 Edge Client**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**.
**Popis serveru VPN**     | Zadejte popis serveru VPN, ke kterému se budou zařízení připojovat. **Příklad:** Contoso VPN Server. Pokud je typ připojení **F5 Edge Client**, použijte pro zadání seznamu popisů a IP adres serveru pole **Seznam serverů**.
**IP adresa nebo plně kvalifikovaný název domény (FQDN) serveru**    |Zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se bude zařízení připojovat. **Příklady:** 192.168.1.1, vpn.contoso.com.  Pokud je typ připojení **F5 Edge Client**, použijte pro zadání seznamu popisů a IP adres serveru pole **Seznam serverů**.         |         
**Seznam serverů**     |Kliknutím na **Přidat** přidejte nový server sítě VPN určený pro připojení k síti VPN. Můžete taky určit, který server bude pro připojení výchozí. Tato možnost se zobrazí, jenom když je typ připojení **F5 Edge Client**..         
**Odesílat veškerý přenos v síti prostřednictvím připojení VPN**     |Pokud vyberete tuto možnost, všechny síťové přenosy se budou odesílat prostřednictvím připojení VPN. Pokud tuto možnost nevyberete, klient bude dynamicky vyjednávat trasy pro dělené tunelové propojení při připojování k serveru sítě VPN třetí strany. Prostřednictvím tunelu VPN se odesílají pouze připojení k firemní síti. Tunelové propojení VPN se nepoužívá při připojení k prostředkům na Internetu.
**Metoda ověření**| Vyberte metodu ověřování používanou pro připojení VPN: **Certifikáty** nebo **Uživatelské jméno a heslo**. (Nastavení Uživatelské jméno a heslo není dostupné, pokud je typ připojení Cisco AnyConnect.) Možnost **Metoda ověřování** není dostupná pro Windows 8.1
**Pamatovat přihlašovací údaje uživatele při každém přihlašování**|Výběrem této možnosti zajistíte, že se přihlašovací údaje uživatele uloží, takže je uživatel nebude muset zadávat při každém navázání připojení.
**Vybrat klientský certifikát pro ověřování klientů (certifikát identity)**|Vyberte certifikát klienta SCEP, který jste dříve vytvořili a který se použije k ověření připojení VPN. Další informace o použití profilů certifikátů v Intune najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md) Tato možnost se zobrazí jenom v případě, že jste vybrali metodu ověřování **Certifikáty**.
**Role**| Zadejte název role uživatele, který má přístup k tomuto připojení. Role uživatele definuje osobní nastavení, možnosti a povolí nebo zakáže určité funkce přístupu. Tato možnost se zobrazí jenom v případě, že typ připojení je **Pulse Secure**..
**Sféra**|Zadejte název sféry ověření, kterou chcete použít. Sféra ověření je seskupení prostředků ověření používaných typem připojení Pulse Secure. Tato možnost se zobrazí jenom v případě, že typ připojení je **Pulse Secure**..
**Doména nebo skupina přihlášení**|Zadejte název domény nebo skupiny přihlášení, k níž se chcete připojit. Tato možnost se zobrazí jenom v případě, že se je typ připojení **Dell SonicWALL Mobile Connect**..
**Otisk prstu**|Zadejte řetězec, například Kód otisku prstu Contoso, který bude použit k ověření, že je možné serveru VPN důvěřovat. Otisk prstu se může odeslat klientovi, aby věděl, že může důvěřovat jakémukoli serveru, který při připojování nabízí ten samý otisk. Pokud zařízení ještě otisk prstu nemá, vyzve uživatele, aby důvěřoval serveru VPN, ke kterému se připojuje. Současně přitom zobrazuje otisk prstu (uživatel ho ručně ověří a klikne na možnost **důvěřovat** připojení). Tato možnost se zobrazuje jenom v případě, že je typ připojení **Kontrolní bod – mobilní síť VPN**..
**VPN na aplikaci**|Tuto možnost vyberte, pokud chcete toto připojení VPN přidružit k aplikaci pro iOS nebo Mac OS X tak, aby se připojení otevřelo při spuštění aplikace. Profil VPN je možné přidružit k aplikaci při nasazení softwaru. Další informace najdete v tématu [Nasazení aplikací v Microsoft Intune](deploy-apps-in-microsoft-intune.md)
**Automaticky zjišťovat nastavení proxy** (jenom iOS, Mac OS X, Windows 8.1 a Windows Phone 8.1)|Pokud VPN server vyžaduje pro připojení proxy server, zadejte, určete, jestli mají zařízení automaticky zjišťovat nastavení připojení. Další informace najdete v dokumentaci k Windows Serveru.
**Použít automatický konfigurační skript** (jenom iOS, Mac OS X, Windows 8.1 a Windows Phone 8.1)|Pokud server VPN vyžaduje pro připojení proxy server, určete, jestli chcete k definování nastavení použít automatický konfigurační skript, a pak zadejte adresu URL souboru, který obsahuje nastavení. Další informace najdete v dokumentaci k Windows Serveru.
**Použít proxy server** (jenom iOS, Mac OS X, Windows 8.1 a Windows Phone 8.1)|Pokud VPN server vyžaduje pro připojení proxy server, vyberte tuto možnost a potom zadejte adresu a číslo portu proxy serveru. Další informace najdete v dokumentaci k Windows Serveru.
**Nepoužívat nastavení proxy pro místní adresy** (jenom iOS, Mac OS X, Windows 8.1 a Windows Phone 8.1)|Pokud VPN server vyžaduje pro připojení proxy server, vyberte tuto možnost, když nechcete používat proxy server pro místní adresy, které zadáte. Další informace najdete v dokumentaci k Windows Serveru.
**Vlastní XML** (jenom Windows 8.1 a novější a Windows Phone 8.1 a novější)|Umožňuje zadat vlastní příkazy XML, které konfigurují připojení VPN. Příklady. Pro **Pulse Secure**: &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. Pro **CheckPoint Mobile VPN**: &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true"  debug="3" /&gt;. Pro **Dell SonicWALL Mobile Connect**: &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. Pro **F5 Edge Client**: &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;. Další informace o tom, jak psát vlastní příkazy XML, najdete v dokumentaci k síti VPN jednotlivých výrobců.
**Seznam hledání přípon DNS** (jenom Windows Phone 8.1)|Zadejte jednu příponu DNS na každém řádku. Každá zadaná přípona DNS se bude vyhledávat při připojení k webu pomocí krátkého názvu. Například když zadáte přípony DNS **domain1.contoso.com** a **domain2.contoso.com** a navštívíte adresu **http://mywebsite**, vyhledají se adresy **http://mywebsite.domain1.contoso.com** a **http://mywebsite.domain2.contoso.com**.
**Obcházet VPN při připojení k síti Wi-Fi společnosti** (jenom Windows Phone 8.1)|Určuje, že se připojení VPN nebude používat při připojení zařízení k podnikové síti Wi-Fi.
**Obcházet VPN při připojení k domácí síti Wi-Fi** (jenom Windows Phone 8.1)|Určuje, že se připojení VPN nebude používat při připojení zařízení k domácí síti Wi-Fi.

Pro desktopová a mobilní zařízení s Windows 10 jsou dostupná následující dodatečná nastavení.

Název nastavení  |Další informace  
---------|---------
**Pravidla pro provoz sítě**| Nastavte, které protokoly, místní a vzdálený port a rozsahy adres budou povolené pro připojení VPN. Když nevytvoříte pravidlo pro provoz sítě, budou povolené všechny protokoly, porty a rozsahy adres. Po vytvoření pravidla se pro připojení VPN použijí jenom protokoly, porty a rozsahy adres, které určíte v tomto pravidle nebo v dalších pravidlech.
**Trasy**|Které trasy budou používat připojení VPN.
**Servery DNS**| Které servery připojení VPN používá po vytvoření připojení.         
**Přidružené aplikace**     | Můžete zadat seznam aplikací, které budou automaticky používat připojení k síti VPN. Typ aplikace bude určovat identifikátor aplikace. Pro univerzální aplikace zadejte identitu aplikace (PFN) a pro desktopové aplikace zadejte cestu k souboru aplikace.          


Tady je příklad, kdy můžete použít nastavení podnikových hranic. Když chcete povolit VPN jenom pro vzdálenou plochu, vytvoříte pravidlo pro provoz sítě, které umožňuje přenos pro protokol číslo 27 na externím portu 3996. Žádný jiný provoz nebude síť VPN používat.

Definování tras v podnikových hranicích je užitečné, když typ připojení VPN neumožňuje určit, jak se provoz zpracovává při děleném tunelovém propojení. V takovém případě použijte **Trasy** k výpisu tras, které budou používat síť VPN.

Vytvořením vlastního nastavení OMA-URI můžete omezit využití sítě VPN zařízením Windows 10 na konkrétní aplikace.

Nová zásada se zobrazí v uzlu **Zásady konfigurace** pracovního prostoru **Zásady** .

## Nasazení zásady

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a potom klikněte na **Spravovat nasazení**..

2.  V dialogovém okně **Spravovat nasazení** :

    -   **Pokud chcete zásadu nasadit** – vyberte jednu nebo víc skupin, do kterých chcete zásady nasadit, a potom klikněte na **Přidat** &gt; **OK**..

    -   **Pokud chcete dialogové okno zavřít bez nasazení zásady** – klikněte na **Zrušit**..


Po úspěšné nasazení se uživatelům zobrazí název připojení VPN, který jste zadali v seznamu připojení VPN na jejich zařízeních.

Shrnutí stavu a výstrahy na stránce **Přehled** v pracovním prostoru **Zásady** identifikují problémy se zásadami, které vyžadují vaši pozornost. Kromě toho se v pracovním prostoru Řídicí panel zobrazí shrnutí stavu.



<!--HONumber=May16_HO1-->

