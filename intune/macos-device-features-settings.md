---
title: nastavení funkce zařízení s macOS v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Podívejte se na nastavení konfigurace zařízení s macOS k tiskárnám a přizpůsobit přihlašovací okno k zobrazení nebo skrytí tlačítka napájení v Microsoft Intune. Podívejte se na postup, chcete-li získat IP adresu, cestu a nastavení portu serveru AirPrint ve vaší síti. Pomocí těchto nastavení v profilu konfigurace zařízení ke konfiguraci funkcí na zařízeních s macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/23/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8858848d12ca3f5839741fc15d87e1cd66e9fad0
ms.sourcegitcommit: bc1bdd63725e62253fcb2daecc41df128bd320f7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/24/2019
ms.locfileid: "63452836"
---
# <a name="macos-device-feature-settings-in-intune"></a>nastavení funkce zařízení s macOS v Intune

Intune zahrnuje několik předdefinovaných nastavení pro přizpůsobení funkcí v zařízeních s macOS. Tento článek uvádí tato nastavení a popisuje, co dělá jednotlivých nastavení. Jsou také uvedené kroky k získání IP adresy, cesta a port AirPrint tiskárny, které používají aplikaci terminál (emulátor).

Tato funkce platí pro:

- macOS

Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete vytvořit banner, vyberte, jakým způsobem se uživatelé přihlásit, přidání serveru AirPrint a další.

Tato nastavení jsou přidány do konfiguračního profilu zařízení v Intune a potom přiřazené nebo nasazené na zařízení s macOS.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení s macOS](device-features-configure.md).

## <a name="airprint"></a>AirPrint

- **IP adresa**: Zadejte adresu IPv4 nebo IPv6 tiskárny. Pokud k identifikaci tiskáren používáte názvy hostitelů, můžete získat IP adresu pomocí příkazu ping tiskáren v aplikaci terminál. [Získat IP adresu a cestu](#get-the-ip-address-and-path) (v tomto článku) poskytuje další podrobnosti.
- **Cesta**: Zadejte cestu k tiskárně. Cesta je obvykle `ipp/print` pro tiskárny ve vaší síti. [Získat IP adresu a cestu](#get-the-ip-address-and-path) (v tomto článku) poskytuje další podrobnosti.
- **Port** (Iosu 11.0 a novějších): Zadejte naslouchající port cíle AirPrint. Pokud tuto vlastnost nezadáte, AirPrint použije výchozí port.
- **Protokol TLS** (Iosu 11.0 a novějších): Vyberte **povolit** k zabezpečení připojení AirPrint pomocí zabezpečení TLS (Transport Layer).

**Přidat** The AirPrint serveru. Můžete přidat více serverů AirPrint.

- **Import** (volitelné): Můžete také **Import** soubor oddělených čárkou (.csv), který obsahuje seznam tiskárny s Airprintem. Po přidání tiskárny s Airprintem v Intune, můžete také **exportovat** tohoto seznamu.

Vyberte **OK** uložte nastavení.

### <a name="get-the-ip-address-and-path"></a>Získat IP adresu a cestu

Přidání serverů AirPrinter, potřebujete IP adresu z tiskárny, cestu prostředku a port. Následující kroky ukazují, jak získat tyto informace.

1. Na Macu, který je připojený ke stejné místní síti (stejná podsíť) jako tiskárny s Airprintem, otevřete **terminálu** (z **/aplikace/Utility**).
2. V aplikaci terminál, zadejte `ippfind`, a vyberte možnost enter.

    Poznámka: informace o tiskárně. Například může vrátit podobně jako `ipp://myprinter.local.:631/ipp/port1`. První část je název tiskárny. Poslední část (`ipp/port1`) je cesta prostředku.

3. V terminálu zadejte `ping myprinter.local`, a vyberte možnost enter.

   Poznamenejte si IP adresu. Například může vrátit podobně jako `PING myprinter.local (10.50.25.21)`.

4. Použijte hodnoty IP adres a prostředků cestu. V tomto příkladu je IP adresa `10.50.25.21`, a cesta prostředku je `/ipp/port1`.

## <a name="login-window"></a>Přihlašovací okno

### <a name="window-layout"></a>Rozložení oken

- **Zobrazit další informace v panelu nabídek**: Pokud je vybrána oblast času v řádku nabídek, **povolit** zobrazuje název a macOS verze hostitele. **Není nakonfigurováno** (výchozí) nezobrazí tyto informace v řádku nabídek.
- **Banner**: Zadejte zprávu, která se zobrazuje na přihlašovací obrazovku na zařízení. Například zadejte informace o vaší organizaci, zobrazení uvítací zprávy, ztráty a nálezy informace a tak dále.
- **Zvolte formát přihlášení**: Zvolte, jak se uživatelé přihlásí k zařízení. Možnosti:
  - **Příkazový řádek pro uživatelské jméno a heslo** (výchozí): Vyžaduje, aby uživatelé k zadání uživatelského jména a hesla.
  - **Zobrazit seznam všech uživatelů, výzvy pro heslo**: Vyžaduje, aby uživatelé ze seznamu uživatelů vyberte své uživatelské jméno a zadejte své heslo. Také nakonfigurujte:

    - **Místní uživatelé**: **Skrýt** místní uživatelské účty se nezobrazí v seznamu uživatelů, které mohou zahrnovat standard a správu účtů. Se zobrazují pouze sítě a systému uživatelské účty. **Není nakonfigurováno** (výchozí) zobrazí místní uživatelské účty v seznamu uživatelů.
    - **Mobilní účty**: **Skrýt** nezobrazí mobilní účty v seznamu uživatelů. **Není nakonfigurováno** (výchozí) zobrazuje mobilní účty v seznamu uživatelů. Některé mobilní účty se můžou zobrazovat jako síťoví uživatelé.
    - **Uživatelé sítě**: Vyberte **zobrazit** seznam síťoví uživatelé v seznamu uživatelů. **Není nakonfigurováno** (výchozí) nezobrazí síti uživatelských účtů v seznamu uživatelů.
    - **Správci**: **Skrýt** nezobrazí správce uživatelských účtů v seznamu uživatelů. **Není nakonfigurováno** (výchozí) zobrazí správce uživatelských účtů v seznamu uživatelů.
    - **Ostatní uživatelé**: Vyberte **zobrazit** do seznamu **Další...**  uživatele v seznamu uživatelů. **Není nakonfigurováno** (výchozí) ostatních zobrazených uživatelských účtech nezobrazí v seznamu uživatelů.

### <a name="login-screen-power-settings"></a>Nastavení napájení přihlašovací obrazovky

- **Vypnout tlačítko**: **Skrýt** nezobrazí tlačítko vypnutí na přihlašovací obrazovce. **Není nakonfigurováno** (výchozí): zobrazí tlačítko vypnutí.
- **Tlačítko Restartovat**: **Skrýt** nezobrazí na přihlašovací obrazovce na tlačítko Restartovat. **Není nakonfigurováno** (výchozí): zobrazí tlačítko Restartovat.
- **Tlačítko režimu spánku**: **Skrýt** nezobrazí tlačítko pro režim spánku na přihlašovací obrazovce. **Není nakonfigurováno** (výchozí): zobrazí tlačítko v režimu spánku.

### <a name="other"></a>Ostatní

- **Zakázat přihlášení uživatele z konzoly**: **Zakázat** skryje macOS příkazovým řádkem použitým k přihlášení. Pro typické uživatele **zakázat** toto nastavení. **Není nakonfigurováno** (výchozí) umožňuje pokročilé uživatele k přihlášení pomocí příkazového řádku s macOS. Do režimu konzoly, uživatelé zadat `>console` uživatelské jméno pole a musí ověřit v okně konzoly.

### <a name="apple-menu"></a>Nabídky Apple

Po přihlášení k zařízení, tato nastavení vliv, co můžete dělat.

- **Zakázat vypnout dolů**: **Zakázat** zabrání uživatelům vybrat **vypnutí** možnost po přihlášení uživatele. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat **vypnutí** položky nabídky na zařízení.
- **Zakázat restartování**: **Zakázat** zabrání uživatelům vybrat **restartovat** možnost po přihlášení uživatele. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat **restartovat** položky nabídky na zařízení.
- **Vypnout napájení vypnuto**: **Zakázat** zabrání uživatelům vybrat **vypnutí** možnost po přihlášení uživatele. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat **vypnutí** položky nabídky na zařízení.
- **Zakázat Odhlásit** (macOS 10.13 a novější): **Zakázat** zabrání uživatelům vybrat **Odhlásit** možnost po přihlášení uživatele. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat **Odhlásit** položky nabídky na zařízení.
- **Zakázat zamykací obrazovka** (macOS 10.13 a novější): **Zakázat** zabrání uživatelům vybrat **zamykací obrazovka** možnost po přihlášení uživatele. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat **zamykací obrazovka** položky nabídky na zařízení.

Vyberte **OK** uložte nastavení.

## <a name="next-steps"></a>Další postup

- Zobrazit všechna nastavení [iOS](ios-device-features-settings.md) zařízení.
- [Tento profil přiřadit](device-profile-assign.md) do skupin, a [monitorování jejího stavu](device-profile-monitor.md).
