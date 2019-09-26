---
title: Vytvoření profilu zařízení se systémem iOS nebo macOS pomocí Microsoft Intune – Azure | Microsoft Docs
description: Přidejte nebo vytvořte profil zařízení se systémem iOS nebo macOS a pak nakonfigurujte nastavení pro průchozí tisk, rozložení domovské obrazovky, oznámení aplikací, sdílené zařízení, jednotné přihlašování a nastavení filtru webového obsahu v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: eefc444e4323db6677ee274d1ba28e8179e43df2
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71303608"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Přidání nastavení funkcí zařízení se systémem iOS nebo macOS v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune zahrnuje mnoho funkcí a nastavení, které správcům pomůžou řídit zařízení s iOS a macOS. Správci můžou například:

- Umožněte uživatelům přístup k tiskárnám pro tisk ve vaší síti.
- Přidávání aplikací a složek na domovskou obrazovku, včetně přidávání nových stránek
- Zvolit, jak a jak se zobrazují oznámení aplikací
- Konfigurace zamykací obrazovky pro zobrazení zprávy nebo inventárního štítku, zejména pro sdílená zařízení
- Poskytněte uživatelům zabezpečené jednotné přihlašování pro sdílení přihlašovacích údajů mezi aplikacemi.
- Filtrovat weby, které používají jazyk pro dospělé a povolují nebo blokují konkrétní weby

Intune používá konfigurační profily k vytvoření a přizpůsobení těchto nastavení potřebám vaší organizace. Po přidání těchto funkcí do profilu ho potom nahrajte nebo nasaďte do zařízení s iOS a macOS ve vaší organizaci.

Tento článek popisuje různé funkce, které můžete nakonfigurovat, a ukazuje, jak vytvořit profil konfigurace zařízení. Můžete si také prohlédnout všechna dostupná nastavení pro zařízení s [iOS](ios-device-features-settings.md) a [MacOS](macos-device-features-settings.md) .

## <a name="airprint"></a>AirPrint

Postupné tisku je funkce společnosti Apple, která umožňuje zařízením tisk do souborů přes bezdrátovou síť. V Intune můžete do zařízení přidat informace o prostředcích pro tisk.

Seznam nastavení, která můžete nakonfigurovat v Intune, najdete v článku o provedený [Tisk na iOS](ios-device-features-settings.md#airprint) a v [MacOS](macos-device-features-settings.md#airprint).

Další informace o protiskech najdete v tématu [o](https://support.apple.com/HT201311) prostudování na webu společnosti Apple.

Platí pro:

- iOS 7,0 a novější
- iPadOS 13,0 a novější
- macOS 10,10 a novější

## <a name="app-notifications"></a>Oznámení aplikací

Vyberte způsob, jakým aplikace na zařízeních s iOS a iPadem dostanou oznámení. Například z Intune můžete odesílat oznámení aplikací tak, aby se zobrazovala v centru oznámení, zobrazit na zamykací obrazovce nebo přehrát zvuk.

Seznam nastavení, která můžete nakonfigurovat v Intune, najdete v tématu [oznámení aplikací v systému iOS](ios-device-features-settings.md#app-notifications).

Další informace o této funkci najdete v tématu [oznámení](https://developer.apple.com/notifications/) na webu společnosti Apple.

Platí pro:

- iOS 9,3 a novější
- iPadOS 13,0 a novější

## <a name="associated-domains"></a>Přidružené domény

Přidružené domény umožňují vytvořit relaci mezi vašimi doménami, například `contoso.com`a vašimi aplikacemi. Tato funkce umožňuje:

- Sdílejte data a přihlaste přihlašovací údaje mezi aplikacemi a weby ve vaší organizaci.
- Používejte funkce aplikací, které jsou založené na vašem webu, jako je například rozšíření aplikace jednotného přihlašování, univerzální odkazy a automatické vyplňování hesel.

  Například vytvořte přidruženou doménu, aby bylo možné automatické vyplňování hesel doporučit, jako je například heslo, pro weby přidružené k vaší aplikaci.

Seznam nastavení, která můžete nakonfigurovat v Intune, najdete v tématu [přidružené domény v MacOS](macos-device-features-settings.md#associated-domains).

Další informace o této funkci najdete v tématu [nastavení přidružených domén aplikace](https://developer.apple.com/documentation/security/password_autofill/setting_up_an_app_s_associated_domains) na webu společnosti Apple.

Platí pro:

- macOS 10,15 a novější

## <a name="home-screen-layout"></a>Rozložení domovské obrazovky

Tato nastavení konfigurují rozložení a složky aplikace v Dock a na domácích obrazovkách na zařízeních s iOS a iPadOS. Můžete:

- K přidání aplikací nebo složek na obrazovku použijte nastavení **Dock** . V Docku zařízení můžete například zobrazit Safari a e-mailovou aplikaci.
- Přidejte **stránky** , které chcete zobrazit na domovské obrazovce, a aplikace, které chcete zobrazit na jednotlivých stránkách. Přidejte například stránku **Contoso** a na tuto stránku přidejte aplikaci nastavení.

Seznam nastavení, která můžete nakonfigurovat v Intune, najdete v tématu [rozložení domovské obrazovky v systému iOS](ios-device-features-settings.md#home-screen-layout).

Platí pro:

- iOS 9,3 a novější
- iPadOS 13,0 a novější

## <a name="lock-screen-message"></a>Zpráva zamykací obrazovky

Pomocí těchto nastavení můžete zobrazit vlastní zprávu nebo text v přihlašovacím okně a na zamykací obrazovce. Můžete například zadat "Pokud došlo ke ztrátě, vrátit se do..." zpráva a zobrazit informace o inventárním štítku.

Seznam nastavení, která můžete nakonfigurovat v Intune, najdete v tématu [Nastavení zpráv na zamykací obrazovce v iOS](ios-device-features-settings.md#lock-screen-message).

Další informace o zprávě zamykací obrazovky najdete v tématu [LockScreenMessage](https://developer.apple.com/documentation/devicemanagement/lockscreenmessage) na webu společnosti Apple.

Platí pro:

- iOS 9,3 a novější
- iPadOS 13,0 a novější

## <a name="login-items"></a>Přihlašovací položky

Pomocí této funkce můžete zvolit aplikace, vlastní aplikace, soubory a složky, které se otevřou, když se uživatelé přihlásí k zařízením. 

Seznam nastavení, která můžete nakonfigurovat v Intune, najdete v tématu [přihlášení k položkám v MacOS](macos-device-features-settings.md#login-items).

Platí pro:

- macOS 10,13 a novější

## <a name="login-window"></a>Přihlašovací okno

Můžete ovládat vzhled přihlašovací obrazovky a funkcí, které uživatelé budou mít k dispozici, než se přihlásí. Přidejte například hlavičku s vlastní zprávou, vyberte, zda je zobrazeno tlačítko režimu spánku a další.

Seznam nastavení, která můžete v Intune nakonfigurovat, najdete v tématu [přihlašovací okno v MacOS](macos-device-features-settings.md#login-window).

Platí pro:

- macOS 10,7 a novější

## <a name="single-sign-on"></a>Jednotné přihlašování

Většina obchodních aplikací vyžaduje z důvodu zabezpečení určitou úroveň ověřování uživatelů. V mnoha případech ověřování vyžaduje, aby uživatel zadal stejné přihlašovací údaje opakovaně. Pro zlepšení uživatelského prostředí můžou vývojáři vytvářet aplikace, které používají jednotné přihlašování (SSO). Použití jednotného přihlašování omezuje počet, kolikrát musí uživatel zadat přihlašovací údaje.

Pokud chcete použít jednotné přihlašování, ujistěte se, že máte:

- Aplikace, která je kódována tak, aby hledala úložiště přihlašovacích údajů uživatele v rámci jednotného přihlašování na zařízení.
- Nakonfigurování Intune na jednotné přihlašování pro zařízení s iOSem

![Podokno Jednotné přihlašování](./media/sso-blade.png)

Seznam nastavení, která můžete v Intune nakonfigurovat, najdete v tématu [jednotné přihlašování v iOS](ios-device-features-settings.md#single-sign-on).

Platí pro:

- iOS 7,0 a novější
- iPadOS 13,0 a novější

## <a name="single-sign-on-app-extension"></a>Rozšíření aplikace s jednotným přihlašováním

Tato nastavení konfigurují rozšíření aplikace, které umožňuje jednotné přihlašování (SSO) pro zařízení s iOS, iPadOS a macOS. Většina obchodních aplikací a webů organizace vyžaduje určitou úroveň zabezpečeného ověřování uživatelů. V mnoha případech ověřování vyžaduje, aby uživatelé opakovaně zadali stejné přihlašovací údaje. Jednotné přihlašování umožňuje uživatelům přístup k aplikacím a webům po zadání přihlašovacích údajů jednou. Po přihlášení uživatelé budou mít přístup k aplikacím a webům automaticky, nebo k získání přístupu použít ID obličeje, dotykové ID nebo Apple heslo.

Pomocí těchto nastavení můžete v Intune nakonfigurovat integrované rozšíření protokolu Kerberos společnosti Apple nebo nakonfigurovat rozšíření aplikace jednotného přihlašování vytvořené vaší organizací. Rozšíření aplikace jednotného přihlašování zpracovává ověřování pro vaše uživatele. Tato nastavení konfigurují rozšíření aplikace jednotného přihlašování typu přihlašovacích údajů, která jsou určená pro toky ověřování s výzvou a odpovědí. Můžete si vybrat z rozšíření přihlašovací údaje specifického pro protokol Kerberos, které poskytuje Apple, a obecné rozšíření přihlašovacích údajů.

Seznam nastavení, která můžete nakonfigurovat v Intune, najdete v tématu [rozšíření aplikace pro iOS SSO](ios-device-features-settings.md#single-sign-on-app-extension) a [rozšíření aplikace MacOS SSO](macos-device-features-settings.md#single-sign-on-app-extension).

Další informace o vývoji rozšíření aplikace jednotného přihlašování najdete na webu společnosti Apple v [rozšiřitelném podnikovém přihlašování](https://developer.apple.com/videos/play/tech-talks/301) .

> [!NOTE]
> Funkce **rozšíření aplikace jednotného přihlašování** se liší od funkce **jednotného přihlašování** :
>
> - Nastavení **rozšíření aplikace s jednotným přihlašováním** platí pro iPadOS 13,0 (a novější) a iOS 13,0 (a novější). Nastavení **jednotného přihlašování** platí pro iPadOS 13,0 (a novější) a iOS 7,0 a novější.
> - **Rozšíření aplikace s jednotným přihlašováním** zpracovává ověřování s operačním systémem. V rámci **jednotného přihlašování**konkrétní aplikace zpracovává ověřování.
> - Při používání **rozšíření aplikace s jednotným přihlašováním**se uživatelé přihlásí k aplikacím a webům v tichém režimu nebo s ID obličeje, dotykovým číslem nebo PINCODE nebo heslem společnosti Apple. Při použití **jednotného přihlašování**se uživatelé přihlásí k aplikacím a webům pomocí jiné aplikace.
>
>    **Rozšíření aplikace jednotného přihlašování** používá k ověření operační systém Apple. Proto může poskytovat lepší prostředí pro koncové uživatele.
>
> - V perspektivě vývoje může **rozšíření jednotného přihlašování** použít jakýkoliv typ ověřování SSO. S **jednotným přihlašováním**můžete použít jenom ověřování pomocí protokolu Kerberos SSO.  

Platí pro:

- iOS 13,0 a novější
- iPadOS 13,0 a novější
- macOS 10,15 a novější

## <a name="wallpaper"></a>Lock

Přidejte vlastní obrázek. png,. jpg nebo. jpeg do zařízení se systémem iOS pod dohledem. Pomocí Intune můžete například přidat logo společnosti do zamykací obrazovky na svých zařízeních.

Seznam nastavení, která můžete nakonfigurovat v Intune, najdete v tématu [Tapeta v iOS](ios-device-features-settings.md#wallpaper).

Platí pro:

- iOS
- iPadOS 13,0 a novější

## <a name="web-content-filter"></a>Filtr webového obsahu

Tato nastavení mohou použít vestavěný algoritmus automatického filtru společnosti Apple k vyhodnocení webových stránek a k blokování obsahu pro dospělé a pro dospělého. Můžete také vytvořit seznam povolených webových odkazů a omezených webových odkazů. Můžete například dovolit, aby se otevíraly jenom `contoso` weby.

Seznam nastavení, která můžete v Intune nakonfigurovat, najdete v tématu věnovaném [filtru webového obsahu v iOS](ios-device-features-settings.md#web-content-filter).

Platí pro:

- iOS 7,0 a novější
- iPadOS 13,0 a novější

## <a name="create-a-device-profile"></a>Vytvoření profilu zařízení

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

    - **Název**: Zadejte popisný název zásady. Své zásady pojmenujte, abyste je později mohli snadno identifikovat. Například dobrý název zásady je **MacOS: Nakonfiguruje přihlašovací**obrazovku.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Vyberte platformu zařízení. Možnosti:  
        - **iOS/iPadOS**
        - **macOS**
    - **Typ profilu**: Vyberte **funkce zařízení**.

4. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Pro podrobnější nastavení vyberte platformu:

    - [iOS/iPadOS](ios-device-features-settings.md)
    - [macOS](macos-device-features-settings.md)

5. Až to budete mít, vyberte **OK** > **Vytvořit** a změny uložte.

Profil se vytvoří a zobrazí se v seznamu profily. Nezapomeňte [profil přiřadit](device-profile-assign.md) a [monitorovat jeho stav](device-profile-monitor.md).

## <a name="next-steps"></a>Další kroky

Profil je po vytvoření připravený k přiřazení. Dále [Přiřaďte profil](device-profile-assign.md) a [sledujte jeho stav](device-profile-monitor.md).

Zobrazí všechna nastavení funkcí zařízení pro zařízení s [iOS](ios-device-features-settings.md) a [MacOS](macos-device-features-settings.md) .
