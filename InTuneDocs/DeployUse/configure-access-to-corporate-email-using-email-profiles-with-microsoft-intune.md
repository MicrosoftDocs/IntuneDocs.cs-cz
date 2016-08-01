---
title: "Přístup k podnikovému e-mailu pomocí e-mailových profilů | Microsoft Intune"
description: "Nastavení e-mailového profilu se dá použít ke konfiguraci nastavení přístupu k e-mailům pro určité e-mailové klienty na mobilních zařízeních."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 07/021/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: c7a3ca7b0390a001624871342c9aa04802be27ff


---

# Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů v Microsoft Intune
Řada mobilních platforem zahrnuje *nativního* e-mailového klienta, který se dodává v rámci operačního systému.  Někteří z těchto klientů se dají nakonfigurovat pomocí e-mailových profilů, jak popisuje toto téma.

Pokud potřebujete další ochranu před únikem informací, vyberte [Podmíněný přístup](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), který určuje přístup do poštovní schránky uživatele pro všechny e-mailové klienty, včetně nativních e-mailových klientů.

Nastavení e-mailového profilu se dá použít ke konfiguraci nastavení přístupu k e-mailům pro určité e-mailové klienty na mobilních zařízeních. Většina mobilních platforem zahrnuje *nativního* e-mailového klienta, který se dodává v rámci operačního systému.  Na podporovaných platformách se dají nativní e-mailoví klienti nakonfigurovat v Microsoft Intune tak, aby uživatelům umožňovali přístup k firemnímu e-mailu z osobních zařízení bez jakéhokoli nastavování.  

Správci IT nebo uživatelé si také můžou nainstalovat alternativní e-mailové klienty, třeba Microsoft Outlook pro Android nebo iOS.  Tito e-mailoví klienti nemusí e-mailové profily podporovat a nemusí umožňovat konfiguraci pomocí e-mailových profilů Microsoft Intune.  

E-mailové profily můžete použít ke konfiguraci nativních e-mailových klientů na těchto typech zařízení:
-   Windows Phone 8 a novější
-   Windows 10 Desktop, Windows 10 Mobile a novější
-   iOS 7.1 nebo novější
-   Samsung KNOX Standard (4.0 a novější)


Kromě nakonfigurování e-mailového účtu na zařízení můžete taky nakonfigurovat nastavení synchronizace, jako třeba kolik e-mailů se má synchronizovat, a v závislosti na typu zařízení i typy synchronizovaného obsahu.

## Zabezpečení e-mailových profilů
E-mailové profily se dají zabezpečit jedním ze dvou způsobů:

### Certifikáty
Když vytváříte e-mailový profil, vyberete profil certifikátu, který jste předtím vytvořili v Intune. Ten se označuje jako certifikát identity a slouží k ověřování na základě důvěryhodného profilu certifikátu (neboli kořenového certifikátu), který potvrzuje, že má zařízení uživatele dovoleno připojovat se. Důvěryhodný certifikát se nasadí do počítače, který ověří e-mailové připojení. Většinou se jedná o nativní poštovní server.

Další informace o vytváření a používání profilů certifikátů v Intune najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů](secure-resource-access-with-certificate-profiles.md).

### Uživatelské jméno a heslo
Uživatel se ověřuje na nativním poštovním serveru zadáním uživatelského jména a hesla.

Heslo není součástí e-mailového profilu, uživatel ho tedy musí zadat při připojování k e-mailu.

### Vytvoření e-mailového profilu

1.  V [konzole správce Microsoft Intune](https://manage.microsoft.com) klikněte na **Zásady** &gt; **Přidat zásadu**.

2.  Nakonfigurujte jeden z následujících typů zásad:

    -   **E-mailový profil pro standard Samsung KNOX (4.0 nebo novější)**

    -   **E-mailový profil (iOS 7.1 a novější)**

    -   **E-mailový profil (Windows Phone 8 a novější)**

    -   **E-mailový profil (Windows 10 Desktop a Mobile a novější)**

    Můžete vytvořit a nasadit jenom vlastní zásadu e-mailového profilu. Doporučená nastavení nejsou dostupná.

3.  S konfigurací nastavení e-mailového profilu vám pomůže následující tabulka:
    |Název nastavení|Další informace|
    |----------------|-----------------------------------------------------------------------------|
    |**Název**|Jedinečný název emailového profilu.|
    |**Popis**|Popis, který vám pomůže tento profil identifikovat.|
    |**Hostitel**|Název hostitele serveru vaší společnosti, který je hostitelem nativní e-mailové služby.|
    |**Název účtu**|Zobrazovaný název e-mailového účtu tak, jak ho uvidí uživatelé na svých zařízeních.|
    |**Uživatelské jméno**|Způsob získání uživatelského jména pro e-mailový účet. V případě místního serveru Exchange vyberte **Uživatelské jméno** a v případě služeb Office 365 vyberte **Hlavní název uživatele**.|
    |**E-mailová adresa**|Způsob generování e-mailové adresy uživatele na každém zařízení. Pokud chcete k přihlášení do systému Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP**, nebo pokud chcete jako e-mailovou adresu používat celý hlavní název, vyberte **Hlavní název uživatele**.|
    |**Metoda ověřování** (Samsung KNOX a iOS)|Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**.|
    |**Vyberte klientský certifikát pro ověření klienta (certifikát identity)** (Samsung KNOX a iOS)|Vyberte certifikát klienta SCEP, který jste dříve vytvořili a který se použije k ověření připojení Exchange. Další informace o použití profilů certifikátů v Intune najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md).<br /><br />Tato možnost se zobrazí jenom v případě, že je metoda ověřování **Certifikáty**.|
    |**Použít S/MIME** (Samsung KNOX a iOS)|Posílá odchozí poštu s šifrováním S/MIME.|
    |**Podpisový certifikát** (Samsung KNOX a iOS)|Vyberte podpisový certifikát, který se bude používat k podepsání odchozích e-mailů.<br /><br />Tato možnost se zobrazí jenom v případě, že jste vybrali **Použít S/MIME**.|
    |**Počet dnů, za které se mají e-maily synchronizovat**|Vyberte počet dnů, za který se mají e-maily synchronizovat, nebo vyberte **Neomezený**, pokud chcete synchronizovat všechny dostupné e-maily.|
    |**Plán synchronizace** (Samsung KNOX, Windows Phone 8 a novější, Windows 10)|Vyberte plán, podle kterého budou zařízení synchronizovat data z Exchange Serveru. Můžete taky vybrat **Při doručování zpráv**, aby se data synchronizovala hned po doručení, nebo **Ruční**, aby musel synchronizaci zahájit uživatel zařízení.|
    |**Použít protokol SSL**|Při posílání a přijímání e-mailů a komunikaci se Exchange Serverem použijte komunikaci SSL (Secure Sockets Layer).<br /><br />U zařízení, na kterých běží Samsung KNOX 4.0 nebo novější, musíte exportovat certifikát SSL Exchange Serveru a v Intune ho nasadit jako profil důvěryhodného certifikátu pro Android. Intune nepodporuje přístup k tomuto certifikátu, pokud je na Exchange Serveru nainstalovaný jiným způsobem.|
    |**Typ obsahu, který se má synchronizovat**|Vyberte typy obsahu, které se mají na zařízeních synchronizovat.| 
    |**Povolit odesílání e-mailů z aplikací jiných výrobců** (jenom iOS)|Můžete povolit uživateli, aby tento profil vybral jako výchozí účet pro odesílání e-mailů, a povolit aplikacím třetích stran otevírání e-mailů v nativních e-mailových aplikacích, například připojování souborů k e-mailům.|

    > [!IMPORTANT]
    > Pokud jste nasadili e-mailový profil a potom chcete změnit hodnoty nastavení **Hostitel** nebo **E-mailová adresa**, je potřeba odstranit stávající e-mailový profil a vytvořit nový s požadovanými hodnotami.

4.  Po dokončení klikněte na **Uložit zásadu**.

Nová zásada se zobrazí v uzlu **Zásady konfigurace** pracovního prostoru **Zásady** .

## Nasazení zásady

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a pak klikněte na **Spravovat nasazení**.

2.  V dialogovém okně **Spravovat nasazení** :

    -   **Pokud chcete zásadu nasadit** – vyberte jednu nebo víc skupin, do kterých chcete zásady nasadit, a pak klikněte na **Přidat** &gt; **OK**.

    -   **Pokud chcete dialogové okno zavřít bez nasazení zásady** – klikněte na **Zrušit**.

Shrnutí stavu a výstrahy na stránce **Přehled** v pracovním prostoru **Zásady** identifikují problémy se zásadami, které vyžadují vaši pozornost. Kromě toho se v pracovním prostoru Řídicí panel zobrazí shrnutí stavu.

> [!NOTE]
> Pokud byste chtěli e-mailový profil ze zařízení odebrat, upravte nasazení a odeberte všechny skupiny, ve kterých je zařízení členem.





<!--HONumber=Jul16_HO3-->


