---
title: nastavení funkcí zařízení macOS v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na nastavení pro konfiguraci zařízení macOS pro Protisk a přizpůsobení okna přihlášení k zobrazení nebo skrytí tlačítek napájení v Microsoft Intune. Podívejte se na postup, jak získat IP adresu, cestu a nastavení portu tiskového serveru v síti. Pomocí těchto nastavení můžete nakonfigurovat funkce zařízení macOS v profilu konfigurace zařízení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 63f2832dd321425efe8092f1bb12dd0d479ef71b
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69549931"
---
# <a name="macos-device-feature-settings-in-intune"></a>nastavení funkcí zařízení macOS v Intune

Intune obsahuje některá vestavěná nastavení pro přizpůsobení funkcí na zařízeních macOS. Tento článek uvádí tato nastavení a popisuje, co jednotlivé nastavení dělá. V této části najdete taky postup pro získání IP adresy, cesty a portu pro tiskárny pro práci na tiskárně pomocí Terminálové aplikace (emulátor).

Tato funkce platí pro:

- macOS

V rámci řešení pro správu mobilních zařízení (MDM) můžete pomocí těchto nastavení vytvořit banner, zvolit způsob přihlášení uživatelů, přidat server pro přenos a další.

Tato nastavení se přidají do konfiguračního profilu zařízení v Intune a pak se přiřadí nebo nasadí do zařízení macOS.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil konfigurace zařízení MacOS](device-features-configure.md).

## <a name="airprint"></a>AirPrint

- **IP adresa**: Zadejte adresu protokolu IPv4 nebo IPv6 tiskárny. Pokud k identifikaci tiskáren používáte názvy hostitelů, můžete získat IP adresu pomocí příkazového testu tiskárny v aplikaci Terminal. [Získat IP adresu a cestu](#get-the-ip-address-and-path) (v tomto článku) najdete další podrobnosti.
- **Cesta**: Zadejte cestu k tiskárně. Cesta je typicky `ipp/print` pro tiskárny v síti. [Získat IP adresu a cestu](#get-the-ip-address-and-path) (v tomto článku) najdete další podrobnosti.
- **Port** (iOS 11,0 a novější): Zadejte port naslouchání cíle přenosu. Pokud necháte tuto vlastnost prázdnou, použije se při tisku výchozí port.
- Protokol **TLS** (iOS 11,0 a novější): Vyberte **Povolit** , pokud chcete zabezpečit připojení přes tisk pomocí protokolu TLS (Transport Layer Security).

**Přidat** Server pro Protisk. Můžete přidat spoustu tiskových serverů.

- **Importovat** (volitelné): Můžete taky **importovat** textový soubor s oddělovači (. csv), který obsahuje seznam tiskáren pro průchozí tisk. Po přidání tiskáren pro tisk do Intune můžete také **exportovat** tento seznam.

Kliknutím na **OK** uložte nastavení.

### <a name="get-the-ip-address-and-path"></a>Získat IP adresu a cestu

Chcete-li přidat servery s modulem pro tisk, budete potřebovat IP adresu tiskárny, cestu k prostředku a port. Následující kroky ukazují, jak tyto informace získat.

1. Na Macu, který je připojený ke stejné místní síti (podsíti) jako tiskárny pro Protisk, otevřete **terminál** (z **/aplikace/Utility**).
2. V aplikaci Terminal App zadejte `ippfind`a vyberte Enter.

    Poznamenejte si informace o tiskárně. Například může vracet něco podobného jako `ipp://myprinter.local.:631/ipp/port1`. První část je název tiskárny. Poslední část (`ipp/port1`) je cesta prostředku.

3. V terminálu zadejte `ping myprinter.local`a vyberte Enter.

   Poznamenejte si IP adresu. Například může vracet něco podobného jako `PING myprinter.local (10.50.25.21)`.

4. Použijte hodnoty IP adresy a prostředku cesty. V tomto příkladu je IP adresa `10.50.25.21`a `/ipp/port1`cesta k prostředku.

## <a name="login-items"></a>Přihlašovací položky

- **Soubory, složky a vlastní aplikace**: **Přidejte** cestu k souboru, složce, vlastní aplikaci nebo systémové aplikaci, kterou chcete otevřít, když se uživatel přihlásí k zařízení. Systémové aplikace nebo aplikace sestavené nebo přizpůsobené pro vaši organizaci jsou obvykle ve `Applications` složce s cestou `/Applications/AppName.app`podobnou. 

  Můžete přidat mnoho souborů, složek a aplikací. Zadejte například:  
  
  - `/Applications/Calculator.app`
  - `/Applications`
  - `/Applications/Microsoft Office/root/Office16/winword.exe`
  - `/Users/UserName/music/itunes.app`
  
  Při přidávání libovolné aplikace, složky nebo souboru Nezapomeňte zadat správnou cestu. Ne všechny položky jsou ve `Applications` složce. Pokud uživatel přesune položku z jednoho umístění do druhé, cesta se změní. Tato přesunutá položka nebude otevřena, když se uživatel přihlásí.

## <a name="login-window"></a>Přihlašovací okno

### <a name="window-layout"></a>Rozložení okna

- **Zobrazit další informace v řádku nabídek**: Když je vybraná časová oblast na panelu nabídek, možnost zobrazit zobrazuje název hostitele a verzi MacOS. **Není nakonfigurováno** (výchozí) nezobrazuje tyto informace na řádku nabídek.
- **Banner**: Zadejte zprávu, která se zobrazí na přihlašovací obrazovce zařízení. Zadejte například informace o vaší organizaci, uvítací zprávu, ztracené a zjištěné informace atd.
- **Vyberte formát přihlášení**: Vyberte, jak se uživatelé k zařízení přihlásí. Možnosti:
  - **Vyzvat k zadání uživatelského jména a hesla** (výchozí): Vyžaduje, aby uživatelé zadali uživatelské jméno a heslo.
  - **Seznam všech uživatelů, výzva k zadání hesla**: Vyžaduje, aby uživatelé vybrali své uživatelské jméno ze seznamu uživatelů, a pak zadali heslo. Také konfigurovat:

    - **Místní uživatelé**: Při **skrytí** se nezobrazí místní uživatelské účty v seznamu uživatelů, které mohou zahrnovat účty Standard a admin. Zobrazují se jenom účty uživatelů sítě a systému. **Není nakonfigurováno** (výchozí) zobrazí v seznamu uživatelů místní uživatelské účty.
    - **Mobilní účty**: Při **skrytí** se nezobrazí mobilní účty v seznamu uživatelů. **Není nakonfigurováno** (výchozí) zobrazí mobilní účty v seznamu uživatelů. Některé mobilní účty se můžou zobrazovat jako síťoví uživatelé.
    - **Uživatelé sítě**: Výběrem **Zobrazit zobrazíte** seznam uživatelů sítě v seznamu uživatelů. **Není nakonfigurováno** (výchozí) nezobrazí účty uživatelů sítě v seznamu uživatelů.
    - **Uživatelé s oprávněními správce**: Při **skrytí** se v seznamu uživatelů nezobrazují uživatelské účty správců. **Není nakonfigurováno** (výchozí) zobrazí účty uživatelů správce v seznamu uživatelů.
    - **Jiní uživatelé**: Vyberte **Zobrazit k zobrazení** seznamu **ostatní...** uživatelé v seznamu uživatelů. **Není nakonfigurováno** (výchozí) nezobrazuje ostatní uživatelské účty v seznamu uživatelů.

### <a name="login-screen-power-settings"></a>Nastavení napájení přihlašovací obrazovky

- **Tlačítko vypnout**: Při **skrytí** se na přihlašovací obrazovce nezobrazí tlačítko vypnout. **Není nakonfigurováno** (výchozí) zobrazí tlačítko vypnout.
- **Tlačítko pro restartování**: Při **skrytí** se na přihlašovací obrazovce nezobrazí tlačítko restartovat. **Není nakonfigurováno** (výchozí) zobrazí tlačítko restartovat.
- **Tlačítko pro režim spánku**: Při **skrytí** se na přihlašovací obrazovce nezobrazí tlačítko režimu spánku. **Není nakonfigurováno** (výchozí) zobrazí tlačítko režimu spánku.

### <a name="other"></a>Ostatní

- **Zakázat přihlášení uživatele z konzoly**: **Disable Disable** skryje příkaz MacOS, který se používá pro přihlášení. V případě typických uživatelů toto nastavení zakažte. **Není nakonfigurováno** (výchozí) umožňuje pokročilým uživatelům, aby se přihlásili pomocí příkazového řádku macOS. Chcete-li přejít do režimu konzoly `>console` , uživatelé zadají do pole uživatelské jméno a musí se ověřit v okně konzoly.

### <a name="apple-menu"></a>Nabídka Apple

Až se uživatelé přihlásí k zařízením, následující nastavení budou mít vliv na to, co můžou dělat.

- **Zakázat vypnutí**: Možnost **Zakázat** : uživatelům zabránit v výběru možnosti **vypnutí** po přihlášení uživatele. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat položku nabídky **vypnutí** na zařízení.
- **Zakázat restart**: Možnost **Zakázat** : uživatelům zabránit v výběru možnosti **restartování** po přihlášení uživatele. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat položku nabídky **restartovat** na zařízení.
- **Zakázat**vypnutí: Při výběru možnosti **Zakázat** budou uživatelé moci vybrat možnost vypnutí po přihlášení uživatele. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat položku nabídky **napájení** v zařízení.
- **Zakázat odhlásit** se (macOS 10,13 a novější): Možnost **Zakázat** : uživatelům brání v výběru možnosti odhlášení po přihlášení uživatele. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat položku nabídky **Odhlásit** se na zařízení.
- **Zakázat zamykací obrazovku** (macOS 10,13 a novější): Při výběru možnosti **Zakázat** budou uživatelé moci po přihlášení uživatele vybrat možnost **zamykací obrazovky** . **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat položku nabídky **zamykací obrazovky** na zařízení.

Kliknutím na **OK** uložte nastavení.

## <a name="next-steps"></a>Další postup

- Zobrazí všechna nastavení pro zařízení s [iOS](ios-device-features-settings.md) .
- [Přiřaďte tento profil](device-profile-assign.md) ke skupinám a [sledujte jeho stav](device-profile-monitor.md).
