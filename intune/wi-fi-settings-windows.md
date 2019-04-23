---
title: Nastavení Wi-Fi pro zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Přidejte nebo vytvořte konfigurační profil pomocí nastavení Wi-Fi pro zařízení s Windows 10 nebo novější verzí v Microsoft Intune. Můžete nakonfigurovat základní nastavení nebo nastavení na podnikové úrovni.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/8/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.reviewer: tycast
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 880a81b49a78e7afd83aca510f85133e91416cf4
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61514765"
---
# <a name="add-wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Přidání nastavení Wi-Fi pro zařízení s Windows 10 a novější verzí v Intune

Můžete vytvořit profil s konkrétním nastavením Wi-Fi a potom ho nasadit na zařízení s Windows 10 a novějšími verzemi. Microsoft Intune nabízí mnoho funkcí, například ověřování v síti, použití předsdíleného klíče a další.

Těmito nastaveními se zabývá tento článek.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil zařízení v Microsoft Intune](device-profile-create.md).

## <a name="basic-profile"></a>Základní profil

- **Typ Wi-Fi**: Zvolte **Základní**. 

- **Název sítě Wi-Fi (SSID)**: Identifikátor zkratka pro service set. Tato hodnota je reálným názvem bezdrátové sítě, ke které se zařízení připojí. Nakonfigurovaný **Název připojení** ale uživatelé uvidí jen při volbě připojení.

- **Název připojení**: Zadejte popisný název pro toto připojení Wi-Fi. Zadaný text uživatelé uvidí na svém zařízení při procházení dostupných připojení.

- **Připojit automaticky, pokud je v dosahu**: Když **Ano**, zařízení připojit automaticky, pokud jsou v dosahu této sítě. Když nastavíte **Ne**, zařízení se automaticky připojovat nebudou.

  - **Připojit k upřednostňovanější síti, pokud je k dispozici**: Pokud zařízení jsou v rozsahu preferovanější síti, klikněte na tlačítko **Ano** používat upřednostňované síti. Pokud chcete použít síť Wi-Fi v tomto konfiguračním profilu, zvolte **Ne**.

    Například můžete vytvořit síť Wi-Fi **ContosoCorp** a v rámci tohoto konfiguračního profilu **ContosoCorp** použít. V dosahu máte i Wi-Fi **ContosoGuest**. Když jsou v dosahu vaše podniková zařízení, budete chtít, aby se automaticky připojovala k síti **ContosoCorp**. V takové situaci vlastnost **Připojit k upřednostňovanější síti, pokud je k dispozici** nastavte na **Ne**.

  - **Připojení k této síti i v případě, že nevysílá svůj identifikátor SSID**: Zvolte **Ano** pro konfigurační profil, automaticky se připojovat k vaší síti, i v případě, že síť je skrytý (to znamená, SSID není veřejně všesměrového vysílání). Pokud nechcete, aby se tento konfigurační profil připojoval ke skryté síti, zvolte **Ne**.

- **Měření podle objemu limitu připojení**: Může správce zvolit, jak se měří síťový provoz. Aplikace pak mohou na základě tohoto nastavení upravit svůj provoz v síti. Možnosti:

  - **Neomezené**: Default (Výchozí). Toto připojení se neměří a provoz není nijak omezen.
  - **Oprava**: Tuto možnost použijte, pokud síť má nakonfigurovanou pevný limit pro síťový provoz. Po dosažení limitu se přístup k síti zakáže.
  - **Proměnné**: Použít tuto možnost, pokud síťový provoz se účtuje za bajtů (náklady na bajt).

- **Typ zabezpečení bezdrátové**: Zadejte protokol zabezpečení používá k ověření zařízení ve vaší síti. Možnosti jsou:
  - **Otevřené (bez ověření)**: Tuto možnost použijte pouze v případě, že síť není zabezpečená.
  - **WPA/WPA2-osobní**: Více bezpečnější možnost a se běžně používá pro připojení Wi-Fi. Z důvodu dalšího zvýšení zabezpečení můžete zadat také heslo předsdíleného klíče nebo síťový klíč. 

    - **Předsdílený klíč** (PSK): Volitelné. Tato možnost se zobrazí, pokud jako typ zabezpečení vyberete **WPA/WPA2-osobní**. Po nastavení nebo konfiguraci firemní sítě se nakonfiguruje také heslo nebo síťový klíč. Toto heslo nebo síťový klíč zadejte jako hodnotu PSK. Zadejte řetězec, jehož délka je 8 až 64 znaků. Pokud mají vaše heslo nebo síťový klíč 64 znaků, zadejte šestnáctkové znaky.
    
      > [!NOTE]
      > Při uložení profilu Wi-Fi se zadaná hodnota PSK z bezpečnostních důvodů nezobrazuje. Ve vodoznaku předsdíleného klíče se pořád zobrazuje **Nenakonfigurováno**, i když je hodnota PSK uložená v profilu. Pokud chcete hodnotu PSK změnit, zadejte nový klíč a uložte profil. Když hodnotu PSK uložíte, upravíte zásadu a necháte hodnotu PSK prázdnou, bude se pořád používat existující hodnota PSK.

- **Nastavení proxy serveru společnosti**: Zvolte nastavení proxy serveru v rámci vaší organizace. Možnosti:
  - **Žádný**: Žádné nastavení proxy serveru jsou nakonfigurované.
  - **Ruční konfigurace**: Zadejte **Proxy server IPaddress** a jeho **číslo portu**.
  - **Automaticky nakonfigurovat**: Zadejte adresu URL odkazující na skript automatické konfigurace (PAC) proxy serveru. Zadejte například `http://proxy.contoso.com/proxy.pac`.

Vyberte **OK** > **Vytvořit** a změny uložte. Profil se vytvoří a zobrazí se v seznamu profilů.

## <a name="enterprise-profile"></a>Profil Enterprise

- **Typ Wi-Fi**: Zvolte **Enterprise**. 

- **Název sítě Wi-Fi (SSID)**: Identifikátor zkratka pro service set. Tato hodnota je reálným názvem bezdrátové sítě, ke které se zařízení připojí. Nakonfigurovaný **Název připojení** ale uživatelé uvidí jen při volbě připojení.

- **Název připojení**: Zadejte popisný název pro toto připojení Wi-Fi. Zadaný text uživatelé uvidí na svém zařízení při procházení dostupných připojení.

- **Připojit automaticky, pokud je v dosahu**: Když **Ano**, zařízení připojit automaticky, pokud jsou v dosahu této sítě. Když nastavíte **Ne**, zařízení se automaticky připojovat nebudou.
  - **Připojit k upřednostňovanější síti, pokud je k dispozici**: Pokud zařízení jsou v rozsahu preferovanější síti, klikněte na tlačítko **Ano** používat upřednostňované síti. Pokud chcete použít síť Wi-Fi v tomto konfiguračním profilu, zvolte **Ne**.

    Například můžete vytvořit síť Wi-Fi **ContosoCorp** a v rámci tohoto konfiguračního profilu **ContosoCorp** použít. V dosahu máte i Wi-Fi **ContosoGuest**. Když jsou v dosahu vaše podniková zařízení, budete chtít, aby se automaticky připojovala k síti **ContosoCorp**. V takové situaci vlastnost **Připojit k upřednostňovanější síti, pokud je k dispozici** nastavte na **Ne**.

  - **Připojení k této síti i v případě, že nevysílá svůj identifikátor SSID**: Zvolte **Ano** pro konfigurační profil, automaticky se připojovat k vaší síti, i v případě, že síť je skrytý (to znamená, SSID není veřejně všesměrového vysílání). Pokud nechcete, aby se tento konfigurační profil připojoval ke skryté síti, zvolte **Ne**.

- **Měření podle objemu limitu připojení**: Může správce zvolit, jak se měří síťový provoz. Aplikace pak mohou na základě tohoto nastavení upravit svůj provoz v síti. Možnosti:

  - **Neomezené**: Default (Výchozí). Toto připojení se neměří a provoz není nijak omezen.
  - **Oprava**: Tuto možnost použijte, pokud síť má nakonfigurovanou pevný limit pro síťový provoz. Po dosažení limitu se přístup k síti zakáže.
  - **Proměnné**: Použít tuto možnost, pokud je síťový provoz placené na bajt.

- **Jednotné přihlašování (SSO)**: Umožňuje nakonfigurovat jednotné přihlašování (SSO), kde jsou sdílené přihlašovací údaje pro počítače a sítě Wi-Fi přihlášení. Možnosti jsou:
  - **Zakázat**: Zakáže chování jednotného přihlašování. Uživatel se musí v síti ověřit zvlášť.
  - **Povolit před uživatel přihlašuje k zařízení**: Použití jednotného přihlašování k ověřování sítě těsně před proces přihlášení uživatele.
  - **Povolit po uživatel přihlašuje k zařízení**: Pomocí jednotného přihlašování k ověření k síti ihned po dokončení procesu přihlášení uživatele.
  - **Maximální doba časový limit na ověření**: Zadejte maximální počet sekund se má provést ověřování v síti, 1 – 120 sekund.
  - **Umožňuje zobrazit výzvu uživateli pro dodatečné ověření přihlašovacích údajů Windows**: Výběr **Ano** umožňuje požádat uživatele o další přihlašovací údaje, pokud to vyžaduje metodu ověřování systému Windows. Pokud chcete tyto výzvy skrýt, zvolte **Ne**.

- **Povolit ukládání klíče PMK (Pairwise master), ukládání do mezipaměti**: Vyberte **Ano** pro ukládání do mezipaměti klíčů PMK používat pro ověřování. Toto ukládání do mezipaměti obvykle ověřování k síti urychluje. Pokud chcete ověřovací signalizaci vynutit pokaždé, když se připojujete k síti Wi-Fi, zvolte **Ne**.

  - **Maximální doba klíč PMK uložený v mezipaměti**: Zadejte počet minut, po které pairwise hlavního klíče (PMK) je uložen v mezipaměti od 5 až 1440 v minut.
  - **Maximální počet uložených v mezipaměti PMKs**: Zadejte počet klíčů uložených v mezipaměti, a to od 1 do 255.

- **Povolit předběžné ověření**: Předběžné ověření umožňuje profil, který chcete ověřit všechny přístupových bodů pro síť v profilu před připojením. Při přesouvání mezi přístupovými body, proběhne opětovné připojení uživatele nebo zařízení díky předběžnému ověření rychleji. Pokud chcete, aby profil provedl ověření u všech přístupových bodů, které jsou v dané síti v dosahu, zvolte **Ano**. Pokud vyžadujete, aby se uživatel nebo zařízení ověřovalo u každého přístupového bodu zvlášť, zvolte **Ne**.

  - **Maximální počet pokusů o předběžné ověření**: Zadejte počet pokusů preauthenticate z 1-16.

- **Typ protokolu EAP**: Zvolte typ protokolu EAP (Extensible Authentication) pro ověřování zabezpečených bezdrátových připojení. Možnosti:

  - **EAP-SIM**
  - **EAP-TLS**
  - **EAP-TTLS**
  - **Protokol PEAP** (Protected EAP)

    **Další nastavení EAP-TLS, EAP-TTLS a PEAP**:
    
    > [!NOTE]
    > V současné době jsou při použití typu protokolu EAP podporované pouze profily certifikátů SCEP. Profily certifikátů PKCS podporované nejsou. Kdykoli je uživatel vyzván k zadání certifikátu, nezapomeňte vybrat certifikát SCEP.

      - **Vztah důvěryhodnosti serveru**  

        **Server zvy důvěryhodných certifikátů**: Použití s **EAP-TLS**, **EAP-TTLS**, nebo **PEAP** typy protokolu EAP. Zadejte jeden nebo více běžných názvů použitých v certifikátech, které vystavuje vaše důvěryhodná certifikační autorita. Když tento údaj zadáte, můžete obejít dialog dynamického vztahu důvěryhodnosti, který se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.  

        **Kořenový certifikát pro ověření serveru**: Použití s **EAP-TLS**, **EAP-TTLS**, nebo **PEAP** typy protokolu EAP. Zvolte profil důvěryhodného kořenového certifikátu pro ověření připojení.  

        **Ochrana identity (vnější identita)**: Použití s **PEAP** typ protokolu EAP. Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.  

      - **Ověření klienta**

        **Klientský certifikát pro ověření klienta (certifikát Identity)**: Použití s **EAP-TLS** typ protokolu EAP. Vyberte profil certifikátu použitý k ověření připojení.

        **Metoda ověřování**: Použití s **EAP-TTLS** typ protokolu EAP. Vyberte metodu ověřování připojení:  

          - **Certifikáty**: Vyberte klientský certifikát, který je certifikátem identity předloženým serveru.
          - **Uživatelské jméno a heslo**: Zadejte **metoda bez protokolu EAP (vnitřní identita)** metodu ověřování. Možnosti:

            - **Nezašifrované heslo (PAP)**
            - **Protokol CHAP (Challenge Handshake)**
            - **Protokol Microsoft CHAP (MS-CHAP)**
            - **Protokol Microsoft CHAP verze 2 (MS-CHAP v2)**

        **Ochrana identity (vnější identita)**: Použití s **EAP-TTLS** typ protokolu EAP. Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

- **Nastavení proxy serveru společnosti**: Zvolte nastavení proxy serveru v rámci vaší organizace. Možnosti:
  - **Žádný**: Žádné nastavení proxy serveru jsou nakonfigurované.
  - **Ruční konfigurace**: Zadejte **Proxy server IPaddress** a jeho **číslo portu**.
  - **Automaticky nakonfigurovat**: Zadejte adresu URL odkazující na skript (PAC) pro automatické konfigurace proxy serveru. Zadejte například `http://proxy.contoso.com/proxy.pac`.

- **Vynutit profilu Wi-Fi, aby vyhovovala se informace o zpracování Standard FIPS (Federal)**: Zvolte **Ano** při ověřování proti FIPS 140-2 standard. Tento standard se vyžaduje od všech agentur federální vlády USA, které chrání citlivé, ale ne tajné digitálně ukládané informace pomocí bezpečnostních systémů založených na kryptografii. Pokud se nemá standard FIPS dodržovat, zvolte **Ne**.

Vyberte **OK** > **Vytvořit** a změny uložte. Profil se vytvoří a zobrazí se v seznamu profilů.

## <a name="use-an-imported-settings-file"></a>Importování souboru nastavení

Pro libovolné nastavení, které není v Intune k dispozici, můžete exportovat nastavení Wi-Fi z jiného zařízení s Windows. Tento export vytvoří soubor XML se všemi nastaveními. Potom tento soubor importujte do Intune a použijte ho jako profil Wi-Fi. Viz [Import nastavení Wi-Fi pro zařízení s Windows 8.1 a novější verzí v Microsoft Intune](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>Další postup

Profil se vytvoří, ale nic nedělá. Dále [tento profil přiřaďte](device-profile-assign.md).

## <a name="more-resources"></a>Další materiály

- Podívejte se na nastavení, která jsou dostupná pro [Windows 8.1](wi-fi-settings-import-windows-8-1.md).
- [Přehled nastavení Wi-Fi](wi-fi-settings-configure.md), včetně dalších platforem
