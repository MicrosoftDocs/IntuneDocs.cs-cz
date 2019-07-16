---
title: Nastavení Wi-Fi pro zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Přidejte nebo vytvořte konfigurační profil pomocí nastavení Wi-Fi pro zařízení s Windows 10 nebo novější verzí v Microsoft Intune. Můžete nakonfigurovat základní nastavení nebo nastavení na podnikové úrovni.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/8/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.reviewer: tycast
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3bbd90b5a317629bd5b4d87b619d89023053518d
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "67884242"
---
# <a name="add-wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Přidání nastavení Wi-Fi pro zařízení s Windows 10 a novější verzí v Intune

Můžete vytvořit profil s konkrétním nastavením Wi-Fi a potom ho nasadit na zařízení s Windows 10 a novějšími verzemi. Microsoft Intune nabízí mnoho funkcí, například ověřování v síti, použití předsdíleného klíče a další.

Těmito nastaveními se zabývá tento článek.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil zařízení v Microsoft Intune](device-profile-create.md).

## <a name="basic-profile"></a>Základní profil

- **Typ Wi-Fi**: Zvolte **Základní**. 

- **Název sítě Wi-Fi (SSID)** : Zkratka pro identifikátor sady služeb je krátký. Tato hodnota je reálným názvem bezdrátové sítě, ke které se zařízení připojí. Nakonfigurovaný **Název připojení** ale uživatelé uvidí jen při volbě připojení.

- **Název připojení**: Zadejte uživatelsky přívětivý název pro toto připojení Wi-Fi. Zadaný text uživatelé uvidí na svém zařízení při procházení dostupných připojení.

- **Připojit automaticky, pokud je v rozsahu**: Pokud **Ano**, zařízení se automaticky připojí, když jsou v dosahu této sítě. Když nastavíte **Ne**, zařízení se automaticky připojovat nebudou.

  - **Připojit k preferovanější síti, je-li k dispozici**: Pokud jsou zařízení v dosahu upřednostňované sítě, zvolte **Ano** a použijte upřednostňovanou síť. Pokud chcete použít síť Wi-Fi v tomto konfiguračním profilu, zvolte **Ne**.

    Například můžete vytvořit síť Wi-Fi **ContosoCorp** a v rámci tohoto konfiguračního profilu **ContosoCorp** použít. V dosahu máte i Wi-Fi **ContosoGuest**. Když jsou v dosahu vaše podniková zařízení, budete chtít, aby se automaticky připojovala k síti **ContosoCorp**. V takové situaci vlastnost **Připojit k upřednostňovanější síti, pokud je k dispozici** nastavte na **Ne**.

  - **Připojte se k této síti i v případě, že nevysílá svůj identifikátor SSID**: Vyberte **Ano** , pokud se má konfigurační profil automaticky připojit k síti, i když je síť skrytá (tzn., že se identifikátor SSID nevysílá veřejně). Pokud nechcete, aby se tento konfigurační profil připojoval ke skryté síti, zvolte **Ne**.

- **Limit měřeného připojení**: Správce může zvolit způsob měření provozu sítě. Aplikace pak mohou na základě tohoto nastavení upravit svůj provoz v síti. Možnosti:

  - **Bez omezení**: Default (Výchozí). Toto připojení se neměří a provoz není nijak omezen.
  - **Opraveno**: Tuto možnost použijte, pokud je síť nakonfigurovaná s pevným limitem pro síťový provoz. Po dosažení limitu se přístup k síti zakáže.
  - **Proměnná**: Tato možnost se používá v případě, že se síťový provoz účtuje za bajt (náklady na bajt).

- **Typ zabezpečení bezdrátové sítě**: Zadejte protokol zabezpečení, který se používá k ověřování zařízení v síti. Máte tyto možnosti:
  - **Otevřené (bez ověřování)** : Tuto možnost použijte pouze v případě, že síť není zabezpečená.
  - **WPA/WPA2 – osobní**: Bezpečnější možnost a často se používá pro připojení Wi-Fi. Z důvodu dalšího zvýšení zabezpečení můžete zadat také heslo předsdíleného klíče nebo síťový klíč. 

    - **Předsdílený klíč** (PSK): Volitelné. Tato možnost se zobrazí, pokud jako typ zabezpečení vyberete **WPA/WPA2-osobní**. Po nastavení nebo konfiguraci firemní sítě se nakonfiguruje také heslo nebo síťový klíč. Toto heslo nebo síťový klíč zadejte jako hodnotu PSK. Zadejte řetězec, jehož délka je 8 až 64 znaků. Pokud mají vaše heslo nebo síťový klíč 64 znaků, zadejte šestnáctkové znaky.
    
      > [!NOTE]
      > Při uložení profilu Wi-Fi se zadaná hodnota PSK z bezpečnostních důvodů nezobrazuje. Ve vodoznaku předsdíleného klíče se pořád zobrazuje **Nenakonfigurováno**, i když je hodnota PSK uložená v profilu. Pokud chcete hodnotu PSK změnit, zadejte nový klíč a uložte profil. Když hodnotu PSK uložíte, upravíte zásadu a necháte hodnotu PSK prázdnou, bude se pořád používat existující hodnota PSK.

- **Nastavení proxy společnosti**: Vyberte, že se má používat nastavení proxy serveru v rámci vaší organizace. Možnosti:
  - **Žádný**: Nejsou nakonfigurovaná žádná nastavení proxy serveru.
  - **Ručně konfigurovat**: Zadejte **IPaddress proxy serveru** a **číslo portu**.
  - **Automaticky konfigurovat**: Zadejte adresu URL odkazující na skript PAC (proxy AutoConfiguration). Zadejte například `http://proxy.contoso.com/proxy.pac`.

Vyberte **OK** > **Vytvořit** a změny uložte. Profil se vytvoří a zobrazí se v seznamu profilů.

## <a name="enterprise-profile"></a>Profil Enterprise

- **Typ Wi-Fi**: Vyberte **Enterprise**. 

- **Název sítě Wi-Fi (SSID)** : Zkratka pro identifikátor sady služeb je krátký. Tato hodnota je reálným názvem bezdrátové sítě, ke které se zařízení připojí. Nakonfigurovaný **Název připojení** ale uživatelé uvidí jen při volbě připojení.

- **Název připojení**: Zadejte uživatelsky přívětivý název pro toto připojení Wi-Fi. Zadaný text uživatelé uvidí na svém zařízení při procházení dostupných připojení.

- **Připojit automaticky, pokud je v rozsahu**: Pokud **Ano**, zařízení se automaticky připojí, když jsou v dosahu této sítě. Když nastavíte **Ne**, zařízení se automaticky připojovat nebudou.
  - **Připojit k preferovanější síti, je-li k dispozici**: Pokud jsou zařízení v dosahu upřednostňované sítě, zvolte **Ano** a použijte upřednostňovanou síť. Pokud chcete použít síť Wi-Fi v tomto konfiguračním profilu, zvolte **Ne**.

    Například můžete vytvořit síť Wi-Fi **ContosoCorp** a v rámci tohoto konfiguračního profilu **ContosoCorp** použít. V dosahu máte i Wi-Fi **ContosoGuest**. Když jsou v dosahu vaše podniková zařízení, budete chtít, aby se automaticky připojovala k síti **ContosoCorp**. V takové situaci vlastnost **Připojit k upřednostňovanější síti, pokud je k dispozici** nastavte na **Ne**.

  - **Připojte se k této síti i v případě, že nevysílá svůj identifikátor SSID**: Vyberte **Ano** , pokud se má konfigurační profil automaticky připojit k síti, i když je síť skrytá (tzn., že se identifikátor SSID nevysílá veřejně). Pokud nechcete, aby se tento konfigurační profil připojoval ke skryté síti, zvolte **Ne**.

- **Limit měřeného připojení**: Správce může zvolit způsob měření provozu sítě. Aplikace pak mohou na základě tohoto nastavení upravit svůj provoz v síti. Možnosti:

  - **Bez omezení**: Default (Výchozí). Toto připojení se neměří a provoz není nijak omezen.
  - **Opraveno**: Tuto možnost použijte, pokud je síť nakonfigurovaná s pevným limitem pro síťový provoz. Po dosažení limitu se přístup k síti zakáže.
  - **Proměnná**: Tato možnost se používá, pokud se síťový provoz účtuje na jeden bajt.

- **Jednotné přihlašování (SSO)** : Umožňuje nakonfigurovat jednotné přihlašování (SSO), kde jsou sdílené přihlašovací údaje pro počítač a přihlášení k síti Wi-Fi. Máte tyto možnosti:
  - **Zakázat**: Zakáže chování jednotného přihlašování. Uživatel se musí v síti ověřit zvlášť.
  - **Povolit, než se uživatel přihlásí do zařízení**: Pomocí jednotného přihlašování (SSO) se můžete k síti ověřit těsně před procesem přihlášení uživatele.
  - **Povolit po přihlášení uživatele do zařízení**: K ověření v síti hned po dokončení procesu přihlašování uživatele použijte jednotné přihlašování (SSO).
  - **Maximální doba pro ověření před časovým limitem**: Zadejte maximální počet sekund, po které se má počkat, než se ověří v síti, od 1-120 sekund.
  - **Povolí systému Windows Dotázat se na další přihlašovací údaje pro ověření**: Zvolíte-li možnost **Ano** , systém Windows může uživateli vyzvat k zadání dalších přihlašovacích údajů, pokud to vyžaduje metoda ověřování. Pokud chcete tyto výzvy skrýt, zvolte **Ne**.

- **Povolit ukládání klíče PMK (Pairwise Master Key) do mezipaměti**: Vyberte **Ano** , pokud chcete uložit do mezipaměti klíč PMK používaný při ověřování. Toto ukládání do mezipaměti obvykle ověřování k síti urychluje. Pokud chcete ověřovací signalizaci vynutit pokaždé, když se připojujete k síti Wi-Fi, zvolte **Ne**.

  - **Maximální doba, po kterou je klíč PMK uložený v mezipaměti**: Zadejte počet minut, po který je v mezipaměti uložen klíč PMK (Pairwise Master Key), od 5-1440 minut.
  - **Maximální počet PMKs uložených v mezipaměti**: Zadejte počet klíčů uložených v mezipaměti, od 1-255.

- **Povolit předběžné ověřování**: Před připojením umožňuje ověření profilu pro všechny přístupové body pro síť v profilu. Při přesouvání mezi přístupovými body, proběhne opětovné připojení uživatele nebo zařízení díky předběžnému ověření rychleji. Pokud chcete, aby profil provedl ověření u všech přístupových bodů, které jsou v dané síti v dosahu, zvolte **Ano**. Pokud vyžadujete, aby se uživatel nebo zařízení ověřovalo u každého přístupového bodu zvlášť, zvolte **Ne**.

  - **Maximální počet pokusů o předběžné ověření**: Zadejte počet pokusů, které se mají předběžně ověřit, od 1-16.

- **Typ protokolu EAP**: Vyberte typ protokolu EAP (Extensible Authentication Protocol) pro ověřování zabezpečených bezdrátových připojení. Možnosti:

  - **EAP-SIM**
  - **EAP-TLS**
  - **EAP-TTLS**
  - **Protokol PEAP** (Protected EAP)

    **Další nastavení EAP-TLS, EAP-TTLS a PEAP**:
    
    > [!NOTE]
    > V současné době jsou při použití typu protokolu EAP podporované pouze profily certifikátů SCEP. Profily certifikátů PKCS podporované nejsou. Kdykoli je uživatel vyzván k zadání certifikátu, nezapomeňte vybrat certifikát SCEP.

    - **Vztah důvěryhodnosti serveru**  

      **Názvy certifikačních serverů**: Použijte s typy EAP **-TLS**, **EAP-TTLS**nebo **PEAP** EAP. Zadejte jeden nebo více běžných názvů použitých v certifikátech, které vystavuje vaše důvěryhodná certifikační autorita. Když tento údaj zadáte, můžete obejít dialog dynamického vztahu důvěryhodnosti, který se zobrazí na zařízeních uživatelů při připojování k Wi-Fi síti.  

      **Kořenový certifikát pro ověření serveru**: Použijte s typy EAP **-TLS**, **EAP-TTLS**nebo **PEAP** EAP. Zvolte profil důvěryhodného kořenového certifikátu pro ověření připojení.  

      **Ochrana identity (vnější identita)** : Použijte s typem **PEAP** EAP. Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.  

    - **Ověření klienta**

      **Klientský certifikát pro ověření klienta (certifikát identity)** : Použijte s typem ověřování EAP **-TLS** . Vyberte profil certifikátu použitý k ověření připojení.

      **Metoda ověřování**: Použijte s typem EAP **-TTLS** EAP. Vyberte metodu ověřování připojení:  

      - **Certifikáty**: Vyberte certifikát klienta, který je certifikátem identity prezentovaný serveru.
      - **Uživatelské jméno a heslo**: Zadejte metodu **(vnitřní identitu) metody bez protokolu EAP** pro ověřování. Možnosti:

        - **Nezašifrované heslo (PAP)**
        - **Protokol CHAP (Challenge Handshake)**
        - **Protokol Microsoft CHAP (MS-CHAP)**
        - **Protokol Microsoft CHAP verze 2 (MS-CHAP v2)**

      **Ochrana identity (vnější identita)** : Použijte s typem EAP **-TTLS** EAP. Zadejte text odeslaný v odpovědi na požadavek identity EAP. Tento text může být libovolná hodnota. Při ověřování se nejdřív pošle tato anonymní identita a po ní následuje skutečná identifikace poslaná přes zabezpečené tunelové propojení.

- **Nastavení proxy společnosti**: Vyberte, že se má používat nastavení proxy serveru v rámci vaší organizace. Možnosti:
  - **Žádný**: Nejsou nakonfigurovaná žádná nastavení proxy serveru.
  - **Ručně konfigurovat**: Zadejte **IPaddress proxy serveru** a **číslo portu**.
  - **Automaticky konfigurovat**: Zadejte adresu URL odkazující na skript automatické konfigurace proxy serveru (PAC). Zadejte například `http://proxy.contoso.com/proxy.pac`.

- **Vynutit, aby profil Wi-Fi byl kompatibilní se standardem FIPS (Federal Information Processing Standard)** : Při ověřování pomocí standardu FIPS 140-2 vyberte **Ano** . Tento standard se vyžaduje od všech agentur federální vlády USA, které chrání citlivé, ale ne tajné digitálně ukládané informace pomocí bezpečnostních systémů založených na kryptografii. Pokud se nemá standard FIPS dodržovat, zvolte **Ne**.

Vyberte **OK** > **Vytvořit** a změny uložte. Profil se vytvoří a zobrazí se v seznamu profilů.

## <a name="use-an-imported-settings-file"></a>Importování souboru nastavení

Pro libovolné nastavení, které není v Intune k dispozici, můžete exportovat nastavení Wi-Fi z jiného zařízení s Windows. Tento export vytvoří soubor XML se všemi nastaveními. Potom tento soubor importujte do Intune a použijte ho jako profil Wi-Fi. Viz [Import nastavení Wi-Fi pro zařízení s Windows 8.1 a novější verzí v Microsoft Intune](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>Další postup

Profil se vytvoří, ale nic nedělá. Dále [tento profil přiřaďte](device-profile-assign.md).

## <a name="more-resources"></a>Další materiály

- Podívejte se na nastavení, která jsou dostupná pro [Windows 8.1](wi-fi-settings-import-windows-8-1.md).
- [Přehled nastavení Wi-Fi](wi-fi-settings-configure.md), včetně dalších platforem
