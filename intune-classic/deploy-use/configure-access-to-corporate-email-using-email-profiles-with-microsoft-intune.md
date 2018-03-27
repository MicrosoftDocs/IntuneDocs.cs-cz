---
title: Přístup k podnikovému e-mailu pomocí e-mailových profilů
description: Nastavení e-mailového profilu se dá použít ke konfiguraci nastavení přístupu k e-mailům pro určité e-mailové klienty na mobilních zařízeních.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 04/19/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c55d8965d566074bddd23ea3973d22333fcc0980
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune"></a>Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Řada mobilních platforem zahrnuje nativního e-mailového klienta, který se dodává v rámci operačního systému. Někteří z těchto klientů se dají nastavit pomocí e-mailových profilů, jak popisuje toto téma.

Nastavení e-mailového profilu se dá použít k nastavení přístupu k e-mailům pro určité e-mailové klienty na mobilních zařízeních. Na podporovaných platformách se dají nativní e-mailoví klienti pomocí Microsoft Intune nastavit tak, aby uživatelům umožňovali přístup k firemnímu e-mailu z osobních zařízení bez jakékoli další konfigurace.

Pokud potřebujete další opatření před únikem informací, vyberte [Podmíněný přístup](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), který definuje přístup do poštovní schránky uživatele pro všechny e-mailové klienty, včetně nativních e-mailových klientů.

Správci IT nebo uživatelé si také můžou nainstalovat alternativní e-mailové klienty (třeba Microsoft Outlook pro Android nebo iOS). Tito e-mailoví klienti nemusí e-mailové profily podporovat a nejde je nastavit pomocí e-mailových profilů Microsoft Intune.  

E-mailové profily můžete použít ke konfiguraci nativních e-mailových klientů na těchto typech zařízení:
-   Windows Phone 8.1 nebo novější
-   Windows 10 (pro počítače), Windows 10 Mobile a novější
-   iOS 8.0 a novější
-   Samsung KNOX Standard (4.0 a novější)
-   Android for Work (e-mailové aplikace třetích stran, nativní e-mailová aplikace je pouze pro osobní profil)

Vedle samotného nastavení e-mailového účtu v zařízení můžete určit, kolik e-mailů se má synchronizovat, a v závislosti na zařízení také jaký typ obsahu se má synchronizovat.

Pokud uživatel nainstaloval e-mailový profil dřív, než profil nastavila služba Intune, výsledek nasazení e-mailového profilu Intune bude záviset na platformě zařízení:

**iOS**<br>Na základě názvu hostitele a e-mailové adresy se detekuje existující duplicitní e-mailový profil. Duplicitní e-mailový profil vytvořený uživatelem blokuje nasazení profilu Intune vytvořeného správcem. Tento problém je běžný, protože uživatelé s iOSem obvykle vytvoří e-mailový profil, a teprve potom se zaregistrují. Portál společnosti informuje uživatele o tom, že nesplňují požadavky kvůli ručně nakonfigurovanému e-mailovému profilu, a vyzve uživatele k jeho odebrání. Uživatel by měl svůj e-mailový profil odebrat, aby bylo možné nasadit profil Intune. Pokud chcete problémům zabránit, požádejte své uživatele, aby se zaregistrovali před instalací e-mailového profilu a aby Intune umožnili nastavení profilu.

**Windows**<br>Na základě názvu hostitele a e-mailové adresy se detekuje existující duplicitní e-mailový profil. Intune přepíše existující e-mailový profil vytvořený uživatelem.

**Samsung KNOX**<br>Na základě e-mailové adresy se detekuje existující duplicitní e-mailový profil a přepíše se profilem Intune. Pokud uživatel tento účet nakonfiguruje, profil Intune ho znovu přepíše. To může způsobit jisté zmatení uživatele.

Vzhledem k tomu, že Samsung KNOX nevyužívá k identifikaci profilu název hostitele, doporučujeme nevytvářet víc e-mailových profilů pro použití se stejnou e-mailovou adresou na různých hostitelích, protože by se vzájemně přepisovaly.

**Android for Work**<br>Intune poskytuje dva e-mailové profily pro Android for Work – jeden pro každou z e-mailových aplikací Gmail a Nine Work. Tyto aplikace jsou dostupné v obchodě Google Play a můžete je nainstalovat do pracovního profilu zařízení, aby nedošlo k vytvoření duplicitních profilů. Obě aplikace podporují připojení k Exchangi. Pokud chcete umožnit připojení k e-mailu, nasaďte jednu z těchto e-mailových aplikací do zařízení uživatelů a pak vytvořte a nasaďte příslušný e-mailový profil. E-mailové aplikace, jako je Nine Work, nemusí být bezplatné. Přečtěte si podrobné informace o licencování aplikace nebo se v případě dotazů obraťte na společnost, která aplikaci vytvořila.

## <a name="secure-email-profiles"></a>Zabezpečení e-mailových profilů
E-mailové profily se dají zabezpečit certifikátem nebo heslem.

### <a name="certificates"></a>Certifikáty
Když vytváříte e-mailový profil, vyberete profil certifikátu, který jste předtím vytvořili v Intune. Ten se označuje jako certifikát identity a slouží k ověřování na základě důvěryhodného profilu certifikátu (neboli kořenového certifikátu), který potvrzuje, že má zařízení uživatele dovoleno připojovat se. Důvěryhodný certifikát se nasadí do počítače, který ověří e-mailové připojení. Většinou se jedná o nativní poštovní server.

Další informace o vytváření a používání profilů certifikátů v Intune najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů](secure-resource-access-with-certificate-profiles.md).

### <a name="user-name-and-password"></a>Uživatelské jméno a heslo
Uživatel se ověřuje na nativním poštovním serveru zadáním uživatelského jména a hesla.

Heslo není součástí e-mailového profilu, uživatel ho tedy musí zadat při připojování k e-mailu.

### <a name="create-an-email-profile"></a>Vytvoření e-mailového profilu

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Zásady** &gt; **Přidat zásadu**.

2.  Nastavte jeden z následujících typů zásad:

    -   **E-mailový profil pro Samsung Knox Standard (4.0 nebo novější)**

    -   **E-mailový profil (iOS 8.0 a novější)**

    -   **E-mailový profil (Windows Phone 8.1 a novější)**

    -   **E-mailový profil (Windows 10 Desktop a Mobile a novější)**

    -   **E-mailový profil (Android for Work – Gmail)**

    -   **E-mailový profil (Android for Work – Nine Work)**

    Můžete vytvořit a nasadit jenom vlastní zásadu e-mailového profilu. Doporučená nastavení nejsou dostupná.

3.  S nastavením e-mailového profilu vám pomůže následující tabulka:

|Název nastavení | Další informace|
| ----------- | --------------- |
    |**Název**|Jedinečný název emailového profilu.|
    |**Popis**|Popis, který vám pomůže tento profil identifikovat.|
    |**Hostitel**|Název hostitele serveru vaší společnosti, který hostuje vaši nativní e-mailovou službu.|
    |**Název účtu**|Zobrazovaný název e-mailového účtu tak, jak ho uvidí uživatelé na svých zařízeních.|
    |**Uživatelské jméno**|Toto je atribut v Active Directory (AD) nebo Azure AD, který se použije k vygenerování uživatelského jména pro tento e-mailový profil. Vyberte Primární adresu SMTP, třeba *user1@contoso.com*, nebo Hlavní název uživatele, třeba *uživatel1* nebo *user1@contoso.com*.|
    |**E-mailová adresa**|Způsob generování e-mailové adresy uživatele na každém zařízení. Pokud chcete k přihlášení do systému Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP**, nebo pokud chcete jako e-mailovou adresu používat celý hlavní název, vyberte **Hlavní název uživatele**.|
    |**Metoda ověřování** (Android for Work, Samsung KNOX a iOS)|Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**.|
    |**Vyberte klientský certifikát pro ověření klienta (certifikát identity)** (Android for Work, Samsung KNOX a iOS)|Vyberte certifikát klienta SCEP, který jste dříve vytvořili a který se použije k ověření připojení Exchange. Další informace o použití profilů certifikátů v Intune najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md). Tato možnost se zobrazí jenom v případě, že je metoda ověřování **Certifikáty**.|
    |**Použít S/MIME** (Samsung KNOX a iOS)|Posílá odchozí poštu s podpisovým certifikátem S/MIME.|
    |**Podpisový certifikát** (Samsung KNOX a iOS)|Vyberte podpisový certifikát, který se bude používat k podepsání odchozích e-mailů. Tato možnost se zobrazí jenom v případě, že jste vybrali **Použít S/MIME**.|
    |**Počet dnů, za které se mají e-maily synchronizovat**|Zadejte počet uplynulých dnů, za které se mají e-maily synchronizovat, nebo vyberte **Neomezený**, pokud chcete synchronizovat všechny dostupné e-maily.|
    |**Plán synchronizace** (Android for Work, Samsung KNOX, Windows Phone 8 a novější, Windows 10)|Vyberte plán, podle kterého budou zařízení synchronizovat data ze serveru Exchange. Můžete také vybrat **Při doručování zpráv**, aby se data synchronizovala hned po doručení, nebo **Ruční**, aby musel synchronizaci zahájit uživatel zařízení.|
    |**Použít protokol SSL**|Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer). U zařízení, na kterých běží Samsung KNOX 4.0 nebo novější, musíte exportovat certifikát SSL serveru Exchange a v Intune ho nasadit jako profil důvěryhodného certifikátu pro Android. Intune nepodporuje přístup k tomuto certifikátu, pokud je na serveru Exchange nainstalovaný jiným způsobem.|
    |**Typ obsahu, který se má synchronizovat** (všechny platformy s výjimkou Gmailu pro Android for Work)|Vyberte typy obsahu, které se mají na zařízeních synchronizovat.|
    |**Povolit odesílání e-mailů z aplikací jiných výrobců** (jenom iOS)|Můžete povolit uživateli, aby tento profil vybral jako výchozí účet pro odesílání e-mailů, a povolit aplikacím třetích stran otevírání e-mailů v nativních e-mailových aplikacích, například připojování souborů k e-mailům.|

> [!IMPORTANT]
>
> Pokud jste nasadili e-mailový profil a potom chcete změnit hodnoty nastavení **Hostitel** nebo **E-mailová adresa**, je potřeba odstranit stávající e-mailový profil a vytvořit nový s požadovanými hodnotami.

4.  Po dokončení klikněte na **Uložit zásadu**.

Nová zásada se zobrazí v uzlu **Zásady konfigurace** pracovního prostoru **Zásady** .

## <a name="deploy-the-policy"></a>Nasazení zásady

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a potom vyberte **Spravovat nasazení**.

2.  V dialogovém okně **Spravovat nasazení** :

    -   **Pokud chcete zásadu nasadit**, vyberte jednu nebo několik skupin, do kterých chcete zásady nasadit, a potom vyberte **Přidat** &gt; **OK**.

    -   **Pokud chcete dialogové okno zavřít bez nasazení zásady** – zvolte **Zrušit**.

Shrnutí stavu a výstrahy na stránce **Přehled** v pracovním prostoru **Zásady** identifikují problémy se zásadami, které vyžadují vaši pozornost. Kromě toho se v pracovním prostoru Řídicí panel zobrazí shrnutí stavu.

> [!NOTE]
> - V případě Androidu for Work nezapomeňte kromě příslušného e-mailového profilu nasadit také aplikace Gmail nebo Nine Work.
> - Pokud byste chtěli e-mailový profil ze zařízení odebrat, upravte nasazení a odeberte všechny skupiny, ve kterých je zařízení členem. Nezapomeňte, že pokud se jedná o jediný e-mailový profil na zařízení, nemůžete tento profil takto odebrat.
> - Pokud provedete změny e-mailového profilu, který jste předtím nasadili, koncovým uživatelům se může zobrazit zpráva s požadavkem, aby schválili rekonfiguraci nastavení e-mailu.
