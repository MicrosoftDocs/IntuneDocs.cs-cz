---
title: "Připojení Wi-Fi"
description: "Profily sítě Wi-Fi uživatelům usnadní připojení k vašim sítím Wi-Fi."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5d021abec31a38d7135828fbe06acd4a1a10ee42
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2017
---
# <a name="configure-devices-to-connect-to-your-corporate-wi-fi-networks"></a>Konfigurace zařízení pro připojení k podnikovým sítím Wi-Fi

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pomocí profilů Wi-Fi služby Intune můžete nasadit nastavení bezdrátové sítě pro uživatele a zařízení ve vaší organizaci. Při nasazování profilu Wi-Fi budou mít uživatelé přístup k vaší podnikové síti, aniž by ji museli konfigurovat sami.

Nainstalujete třeba novou síť Wi-Fi s názvem **Contoso Wi-Fi** a chcete nastavit všechna zařízení iOS pro připojení k této síti. Postup je následující:

![Shrnutí procesu profilu sítě Wi-Fi](..\media\wi-fi-process-diagram.png)

1.   Vytvoříte profil Wi-Fi obsahující nastavení požadovaná pro připojení k bezdrátové síti **Contoso Wi-Fi**.

2.   Nasadíte profil do skupiny uživatelů se zařízeními iOS.

3.   Uživatelé najdou novou síť **Contoso Wi-Fi** v seznamu bezdrátových sítí a můžou se k ní snadno připojit.


## <a name="create-a-wi-fi-profile"></a>Vytvoření profilu sítě Wi-Fi

Profily Wi-Fi můžete nasadit na následujících platformách:

-   Android 4.0 nebo novější

-   Android for Work   

-   iOS 8.0 a novější

-   Mac OS X 10.9 a novější

U zařízení, na kterých běží desktopové nebo mobilní operační systémy Windows 8.1 nebo Windows 10, můžete importovat konfigurační profil Wi-Fi, který jste si předtím vyexportovali do souboru. Podrobnosti najdete v tématu [Export nebo import konfiguračního profilu Wi-Fi pro zařízení se systémem Windows](#export-or-import-a-wi-fi-configuration-profile-for-windows-devices).

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Zásady** &gt; **Přidat zásadu**.

2.  Vyberte jeden z následujících typů zásad a potom zvolte **Vytvořit zásadu**:

    -   Profil Wi-Fi (Android 4 a novější)

    -   Profil Wi-Fi (Android for Work)

    -   Profil Wi-Fi (iOS 8.0 a novější)

    -   Profil Wi-Fi (Mac OS X 10.9 a novější)


Pro tento typ zásad nejsou žádná doporučená nastavení. Je potřeba vytvořit vlastní zásadu.

3.  Zadejte název a popis profilu.

4. Zadejte hodnoty **síťových připojení**.
 - **Identifikátor SSID (Service Set Identifier)**: Tuto možnost vyberte, pokud se má uživatelům zobrazovat název sítě a ne identifikátor SSID.
 - **Připojit se, když síť nevysílá svůj název (SSID)**:Tuto možnost vyberte, pokud chcete zařízením povolit, aby se připojovala k síti, když tato síť není zobrazená v seznamu sítí (protože je skrytá a nevysílá svůj název).

5. Nakonfigurujte **Nastavení zabezpečení** pro vybranou platformu. Dostupná nastavení závisí na typu zabezpečení, které vyberete. Jejich popis najdete v části [Nastavení zabezpečení](#security-settings).

6. Nakonfigurujte **nastavení proxy serveru** (jenom iOS a MAC OS X).

    |Název nastavení|Další informace|Kdy ji použít|
    |----------------|-------------------|-------------|
    |**Nastavení proxy serveru pro toto připojení Wi-Fi**|Zvolte typ nastavení proxy serveru:<br /><br />-   **Žádné** (výchozí)<br />-   **Ruční** – zadejte ručně adresu URL a číslo portu proxy serveru.<br />-   **Automatické** – ke konfiguraci proxy serveru použijte konfigurační soubor.|Vždy|
    |**Adresa proxy serveru** a **číslo portu**|Zadejte adresu URL a číslo portu proxy serveru.|**Nastavení proxy serveru pro toto připojení Wi-Fi** je **Ruční**|
    |**URL proxy serveru**|Zadejte adresu URL souboru, který obsahuje nastavení proxy serveru.|**Nastavení proxy serveru pro toto připojení Wi-Fi** je **Automatické**|

7.  Uložení profilu Wi-Fi

Nová zásada se zobrazí v uzlu **Zásady konfigurace** pracovního prostoru **Zásady**. Další informace o nasazení služby najdete v části **Další kroky**.

## <a name="export-or-import-a-wi-fi-configuration-profile-for-windows-devices"></a>Export nebo import konfiguračního profilu Wi-Fi pro zařízení se systémem Windows

U zařízení, na kterých běží desktopové nebo mobilní operační systémy Windows 8.1 nebo Windows 10, můžete importovat konfigurační profil Wi-Fi, který jste si předtím vyexportovali do souboru.

### <a name="export-a-wi-fi-profile"></a>Export profilu Wi-Fi
Ve Windows můžete pomocí nástroje **netsh wlan** exportovat stávající profil Wi-Fi do souboru XML, který dokáže Intune přečíst. Na počítači s Windows, který už má nainstalovaný požadovaný profil WiFi, postupujte takto:

1.  Vytvořte místní složku pro exportované profily Wi-Fi. Vytvořte třeba složku nazvanou **c:\WiFi.**

2.  Otevřete příkazový řádek jako správce.

3.  Spusťte příkaz `netsh wlan show profiles` a uveďte název profilu, který chcete exportovat.  V tomto příkladu je název profilu **WiFiNázev**.

4.  Spusťte tento příkaz: `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Ten vytvoří v cílové složce soubor profilu Wi-Fi s názvem **Wi-Fi-WiFiNázev.xml**.

### <a name="import-a-wi-fi-profile"></a>Import profilu Wi-Fi
Pomocí **Zásady importu Wi-Fi pro Windows** importujte sadu nastavení Wi-Fi, kterou pak můžete nasadit do požadovaných skupin uživatelů nebo zařízení.


1.  V [konzole správce Microsoft Intune](https://manage.microsoft.com) klikněte na **Zásady** &gt; **Přidat zásadu**.

2.  Nakonfigurujte zásady typu **Windows** &gt; **Import Wi-Fi (Windows 8.1 a novější)**.

    Tuto zásadu je možné použít na zařízeních s desktopovými a mobilními operačními systémy Windows 8.1 a Windows 10.

    Vytvářet a nasazovat můžete jenom *vlastní* zásady importu Wi-Fi pro Windows. Doporučená nastavení nejsou dostupná.

3.  Zadejte následující obecné hodnoty pro nastavení Zásady importu Wi-Fi pro Windows:

    |Název nastavení|Další informace|
    |----------------|--------------------|
    |**Název**|Zadejte jedinečný název profilu Wi-Fi, podle kterého ho v konzole služby Intune poznáte.|
    |**Popis**|Zadejte popis profilu Wi-Fi a další důležité informace, které vám pomůžou ho najít.|

4.  Pod nadpisem **Vlastní profil Wi-Fi** zadejte následující hodnoty:

    |Název nastavení|Další informace|
    |----------------|--------------------|
    |**Soubor konfiguračního profilu**|Klikněte na **Importovat** a vyberte soubor XML obsahující nastavení profilu Wi-Fi, které chcete importovat do Intune.|
    |**Název vlastního konfiguračního profilu (zobrazí se uživatelům)**|Zvolte, jak zobrazit název konfiguračního profilu Wi-Fi tak, jak se bude zobrazovat uživatelům na jejich zařízení.|
    |**Podrobnosti konfiguračního profilu**|Zvolte, jak zobrazit kód XML pro konfigurační profil, který jste vybrali.|

5.  Po dokončení klikněte na **Uložit zásadu**.

6.  Nová zásada se zobrazí v uzlu **Zásady konfigurace** pracovního prostoru **Zásady**.

## <a name="deploy-the-profile"></a>Nasaďte profil

Profil je typ zásad, proto ho nasaďte přes pracovní prostor **Zásady**.

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a potom vyberte **Spravovat nasazení**.

2.  V dialogovém okně **Spravovat nasazení** :

    -   **Postup nasazení zásady:** Vyberte jednu nebo více skupin, do kterých chcete zásadu nasadit. Potom klikněte na **Přidat** &gt; **OK**.

    -   **Pokud chcete dialogové okno zavřít bez nasazení zásady**, klikněte na **Zrušit**.


Na stránce **Přehled** v pracovním prostoru **Zásady** se zobrazují problémy se zásadami, které vyžadují vaši pozornost. Kromě toho se v pracovním prostoru Řídicí panel zobrazí shrnutí stavu.

## <a name="security-settings"></a>Nastavení zabezpečení
Tyto tabulky obsahují podrobné informace o nastavení zabezpečení, které je k dispozici pro profily sítě Wi-Fi pro Android, iOS a Mac OS X.

### <a name="security-settings-for-android-devices"></a>Nastavení zabezpečení pro zařízení Android

  |Název nastavení|Další informace|Kdy ji použít|
|----------------|--------------------|-------------|
|**Typ zabezpečení**|Vyberte protokol zabezpečení bezdrátové sítě:<br /><br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **Bez ověřování (otevřené)**, pokud síť není zabezpečená.|Vždy|
|**Typ protokolu EAP**|Zvolte typ protokolu EAP pro ověřování zabezpečených bezdrátových připojení:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TTLS**|Pokud jste vybrali typ zabezpečení **WPA-Enterprise/WPA2-Enterprise**.|
|**Vyberte kořenové certifikáty pro ověření serveru**|Klikněte na **Vybrat** a pak zvolte profil důvěryhodných kořenových certifikátů pro ověření připojení. Další informace o vytvoření profilu důvěryhodných kořenových certifikátů najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů](secure-resource-access-with-certificate-profiles.md).|Pokud jste vybrali jakýkoli **typ protokolu EAP**.|
|**Metoda ověřování**|Vyberte metodu ověřování používanou u připojení:<br /><br />-   **Certifikáty** – pokud chcete zadat klientský certifikát.<br />-   **Uživatelské jméno a heslo** – pokud chcete zadat jinou metodu ověřování.|**Typ protokolu EAP** je **PEAP** nebo **EAP-TTLS**.|
|**Vyberte jinou metodu ověření než EAP (vnitřní identita)**|Vyberte metodu ověřování připojení:<br /><br />-   **Žádné**<br />-   **Nezašifrované heslo (PAP)**<br />-   **Protokol CHAP (Challenge Handshake Authentication Protocol)**<br />-   **Protokol Microsoft CHAP (MS-CHAP)**<br />-   **Protokol Microsoft CHAP verze 2 (MS-CHAP v2)**<br /><br />Dostupné možnosti závisí na typu EAP, který jste vybrali.|**Metoda ověřování** je **Uživatelské jméno a heslo**.|
|**Povolit ochranu osobních údajů v rámci identity (vnější identita)**|Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota. Během ověřování se nejdříve odešle tato anonymní identita. Skutečná identifikace se pak odešle přes zabezpečené tunelové propojení.|Typ protokolu **EAP** je **PEAP** nebo **EAP-TTLS**.|
|**Vyberte klientský certifikát pro ověření klienta (certifikát identity)**|Klikněte na **Vybrat** a pak zvolte profil certifikátu SCEP pro ověření připojení. Další informace o vytvoření profilu certifikátu SCEP najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů](secure-resource-access-with-certificate-profiles.md).|Typ zabezpečení je **WPA-Enterprise/WPA2-Enterprise** a je vybraný jakýkoliv **typ protokolu EAP**.|

### <a name="security-settings-for-ios-and-mac-os-x-devices"></a>Nastavení zabezpečení pro zařízení iOS a Mac OS X

  |Název nastavení|Další informace|Kdy ji použít|
|----------------|--------------------|-------------|
|**Typ zabezpečení**|Vyberte protokol zabezpečení bezdrátové sítě:<br /><br />-   **WPA-Personal/WPA2-Personal**<br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **WEP**<br />-   **Bez ověřování (otevřené)**, pokud síť není zabezpečená.|Vždy|
|**Typ protokolu EAP**|Zvolte typ protokolu EAP pro ověřování zabezpečených bezdrátových připojení:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TLS**<br />-   **EAP-AST**<br />-   **LEAP**<br />-   **EAP-SIM**|Vybrali jste typ zabezpečení **WPA-Enterprise/WPA2-Enterprise**.|
|**Názvy důvěryhodných certifikátů serveru**|Vyberte profil důvěryhodných kořenových certifikátů použitých pro ověření připojení. Další informace o vytvoření profilu důvěryhodných kořenových certifikátů najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů](secure-resource-access-with-certificate-profiles.md).|Vybrali jste typ protokolu EAP **EAP-TLS**, **PEAP**, **EAP-TTLS** nebo **EAP-FAST**.|
|**Použít PAC (Protected Access Credential)**|Toto nastavení vyberte, pokud chcete použít přihlašovací údaje chráněného přístupu k navázání ověřeného tunelového propojení mezi klientem a serverem ověřování. Použije se stávající soubor PAC, pokud je dostupný.|**Typ protokolu EAP** je **EAP-FAST**.|
|**Zřídit PAC**|Nastaví na vašich zařízeních profil PAC.<br /><br />Pokud použijete toto nastavení, můžete také vybrat **Zřídit PAC anonymně** , aby se soubor PAC mohl nastavovat bez ověřování serveru.|Je vybraný typ zabezpečení **Použít ověření PAC (Protected Access Credential)**.|
|**Metoda ověřování**|Vyberte metodu ověřování používanou u připojení:<br /><br /><ul><li>**Certifikáty** – pokud chcete zadat klientský certifikát.</li><li>**Uživatelské jméno a heslo** – pokud chcete zadat jednu z následujících metod ověřování bez protokolu EAP (označuje se taky jako vnitřní identita):<br /><br /><ul><li>**Žádné**</li><li>**Nezašifrované heslo (PAP)**</li><li>**Protokol CHAP (Challenge Handshake Authentication Protocol)**</li><li>**Protokol Microsoft CHAP (MS-CHAP)**</li><li>**Protokol Microsoft CHAP verze 2 (MS-CHAP v2)**</li><li>**EAP-TLS**</li></ul></li></ul>|Typ protokolu **EAP** je **PEAP** nebo **EAP-TTLS**.|
|**Vyberte klientský certifikát pro ověření klienta (certifikát identity)**|Vyberte profil certifikátu SCEP, který se používá k ověření připojení. Další informace o vytvoření profilu certifikátu SCEP najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů](secure-resource-access-with-certificate-profiles.md).|Typ zabezpečení je **WPA-Enterprise/WPA2-Enterprise** a **Typ protokolu EAP** je **EAP-TLS**, **protokol PEAP** nebo **EAP-TTLS**.|
|**Povolit ochranu osobních údajů v rámci identity (vnější identita)**|Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota.<br /><br />Během ověřování se nejdříve odešle tato anonymní identita. Skutečná identifikace se pak odešle přes zabezpečené tunelové propojení.|**Typ protokolu EAP** je nastavený na **PEAP**, **EAP-TTLS** nebo **EAP-FAST**.|


### <a name="see-also"></a>Související témata
Postup vytvoření profilu Wi-Fi s předsdíleným klíčem najdete v tématu věnovaném [vytvoření profilu Wi-Fi s předsdíleným klíčem](pre-shared-key-wi-fi-profile.md).
