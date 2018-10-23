---
title: Výhody sady Intune App SDK
titlesuffix: Microsoft Intune
description: Sada Intune App SDK je dostupná pro platformy iOS i Android a umožňuje povolit funkce správy mobilních aplikací v Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fc49d7ba7cdc5b986c06f8a84ececc8339a812a2
ms.sourcegitcommit: cff65435df070940da390609d6376af6ccdf0140
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2018
ms.locfileid: "49425100"
---
# <a name="intune-app-sdk-overview"></a>Přehled sady Intune App SDK
Intune App SDK, dostupná pro iOS i Android, povoluje ve vaší aplikaci zásady ochrany aplikací Intune. Usiluje o minimalizaci nutných změn kódu, které musí vývojáře aplikace provádět. Zjistíte, že většinu funkcí sady SDK můžete povolit bez změny chování vaší aplikace. Za účelem zlepšení činnosti koncových uživatelů a správců IT můžete využít rozhraní API k přizpůsobení chování vaší aplikace pro funkce, které vyžadují zapojení vaší aplikace.

Jakmile v aplikaci povolíte zásady ochrany aplikací, můžou správci IT tyto zásady nasazovat, aby chránili firemní data v rámci dané aplikace.

## <a name="app-protection-features"></a>Funkce ochrany aplikací

Níže najdete příklady funkcí ochrany aplikací Intune, které se dají aktivovat pomocí sady SDK.

### <a name="control-users-ability-to-move-corporate-files"></a>Ovládání možnosti uživatelů přesouvat podnikové soubory
Správci IT můžou řídit, kam se dají přesouvat pracovní nebo školní data v aplikaci. Můžou třeba nasadit zásadu, která zakazuje aplikacím zálohovat podniková data do cloudu.

### <a name="configure-clipboard-restrictions"></a>Konfigurace omezení schránky
Správci IT můžou konfigurovat chování schránky v aplikacích spravovaných v Intune. Můžou například nasadit zásadu, která zabrání koncovým uživatelům vyjmout nebo zkopírovat data z aplikace a vložit je do nespravované osobní aplikace.

### <a name="enforce-encryption-on-saved-data"></a>Vynucení šifrování uložených dat
Správci IT můžou vynutit zásadu, která zajišťuje, aby data ukládaná aplikací do zařízení šifrovala.

### <a name="remotely-wipe-corporate-data"></a>Vzdálené vymazání podnikových dat
Správci IT můžou vzdáleně vymazat podniková data z aplikací spravovaných v Intune. Tato funkce je založená na identitě a odstraní jenom soubory přidružené k podnikové identitě koncového uživatele. Kvůli tomu funkce vyžaduje zapojení aplikace. Aplikace může určit identitu, u které má dojít k vymazání, na základě uživatelského nastavení. Když uvedená uživatelská nastavení v aplikaci chybí, výchozím chováním bude vymazání adresáře aplikace a upozornění koncového uživatele, že došlo k odebrání přístupu.

### <a name="enforce-the-use-of-a-managed-browser"></a>Vynucení používání spravovaného prohlížeče
Správce IT může vynutit, aby se webové odkazy v aplikaci otevíraly pomocí [aplikace Intune Managed Browser](app-configuration-managed-browser.md). Tato funkce zajistí, aby odkazy zobrazované v podnikovém prostředí zůstaly uchované v rámci aplikací spravovaných v Intune.

### <a name="enforce-a-pin-policy"></a>Vynucení zásady kódu PIN
Správce IT může po koncovém uživateli vyžadovat, aby před přístupem k podnikovým datům v aplikaci zadal PIN. Tím se zajistí, že uživatel, který aplikaci používá, je tím samým uživatelem, který se původně přihlásil pomocí pracovního nebo školního účtu. Když si koncoví uživatelé nakonfigurují PIN, sada Intune App SDK použije Azure Active Directory k ověření přihlašovacích údajů koncových uživatelů podle registrovaného účtu Intune.

### <a name="require-users-to-sign-in-with-work-or-school-account-for-app-access"></a>Vyžadování, aby se uživatelé před přístupem k aplikaci přihlásili pomocí pracovního nebo školního účtu
Správci IT můžou vyžadovat, aby se uživatelé před přístupem k aplikaci přihlásili pomocí pracovního nebo školního účtu. Sada Intune App SDK použije Azure Active Directory k poskytnutí jednotného přihlašování, při kterém se jednou zadané přihlašovací údaje znovu použijí pro následující přihlášení. Také podporujeme ověřování řešení správy identity sdružených se službou Azure Active Directory.

### <a name="check-device-health-and-compliance"></a>Kontrola stavu zařízení a dodržování předpisů
Správci IT můžou před přístupem koncových uživatelů k aplikacím kontrolovat stav zařízení a dodržování zásad Intune. Na iOSu tato zásada kontroluje, jestli zařízení nemá jailbreak. Na Androidu tato zásada kontroluje, jestli zařízení nemá root.

### <a name="multi-identity-support"></a>Podpora více identit
Podpora více identit je funkce sady SDK umožňující koexistenci účtů spravovaných zásadou (podnikových) a nespravovaných (osobních) v jediné aplikaci.

Mnoho uživatelů si například v mobilních aplikacích Office pro iOS a Android konfiguruje podnikové i osobní e-mailové účty. Když uživatel pracuje s daty s podnikovým účtem, správce IT musí mít jistotu, že se použije zásada ochrany aplikací. Když ale uživatel přistupuje k osobnímu e-mailovému účtu, tato data by měla být mimo dosah správce IT. Sada Intune App SDK toho dosahuje tím, že v aplikaci cílí zásady ochrany aplikace **jenom** na podnikovou identitu.

Tato funkce více identit vám pomůže vyřešit problém s ochranou dat, se kterým se setkávají organizace s aplikacemi ze Storu, které podporují osobní i pracovní účty.
 
### <a name="app-protection-without-device-enrollment"></a>Ochrana aplikací bez registrace zařízení

>[!IMPORTANT]
>Intune App Protection bez registrace zařízení je dostupná v nástrojích Intune App Wrapping Tools a sadách Intune App SDK pro Android, Intune App SDK pro iOS a Xamarinových vazbách sady Intune App SDK.

Mnoho uživatelů s osobními zařízeními chce pracovat s podnikovými daty bez registrace svého osobního zařízení u poskytovatele správy mobilních zařízení (MDM). Registrace MDM vyžaduje globální kontrolu nad zařízením, proto uživatelé často váhají předat tuto kontrolu nad vlastním osobním zařízením podniku.

Ochrana aplikací bez registrace zařízení umožňuje službě Microsoft Intune nasadit zásady ochrany aplikací přímo na aplikaci, aby se nemusela spoléhat na nasazení zásad prostřednictvím kanálu pro správu zařízení.

### <a name="on-demand-application-vpn-connections-with-citrix-mvpn"></a>Připojení VPN aplikace na vyžádání pomocí Citrix mVPN 
Můžete spravovat zařízení a aplikace s kombinací Citrix XenMobile MDX a Microsoft Intune. Tato kombinace znamená, že při používání technologie mVPN od Citrixu můžete aplikace spravovat pomocí zásad ochrany aplikací Intune. Integrace s Citrixem je dostupná pro sadu Intune App SDK pro iOS a Android a při použití nástroje Intune App Wrapping Tool pro iOS a Android (s příznakem -citrix).
 
Další informace o Citrix MDX najdete v tématech, které pojednávají o [sadě nástrojů MDX](http://docs.citrix.com/en-us/mdx-toolkit/10/about-mdx-toolkit.html), [nástroji Citrix MDX App Wrapper pro iOS](https://docs.citrix.com/en-us/mdx-toolkit/10/xmob-mdx-kit-app-wrap-ios.html) a [nástroji Citrix MDX App Wrapper pro Android](https://docs.citrix.com/en-us/mdx-toolkit/10/xmob-mdx-kit-app-wrap-android.html).
