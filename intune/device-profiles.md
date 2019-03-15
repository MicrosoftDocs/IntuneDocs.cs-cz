---
title: Zařízení funkcích a nastaveních v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Přehled různých profilů zařízení Microsoft Intune, včetně funkcí, omezení, e-mailu, Wi-Fi, VPN, vzdělávání, certifikátů, upgradu Windows 10, Bitlockeru a Windows defender, Windows Information Protection, šablony pro správu, a nastavení konfigurace vlastních zařízení na portálu Azure portal. Používání těchto profilů pro správu a ochranu dat a zařízení ve vaší společnosti.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: ad9b0fb2fc8814f04860793bb1210da17dbe2a65
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57395325"
---
# <a name="apply-features-and-settings-on-your-devices-using-device-profiles-in-microsoft-intune"></a>Použít nastavení a funkcí v zařízeních pomocí profilů zařízení v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune zahrnuje nastavení a funkcí můžete povolit nebo zakázat na různých zařízeních ve vaší organizaci. Tato nastavení a funkce se přidají do "konfiguračních profily". Můžete vytvořit profily pro různá zařízení, různé platformy, včetně iOS, Android, Windows a pak pomocí Intune použít profil pro zařízení ve vaší organizaci.

Jako součást řešení správy mobilních zařízení provádět různé úlohy, pomocí těchto konfiguračních profilů. Například:

- Na zařízeních s Windows 10 použijte šablonu profilu blokující ovládacích prvků ActiveX v Internet Exploreru.
- Na zařízení s Iosem a macOS umožnit uživatelům používat tiskárny s Airprintem ve vaší organizaci.
- Povolit nebo zakázat přístup k bluetooth na zařízení.
- Vytvoření profilu Wi-Fi nebo VPN, který dává různým zařízením přístup k vaší podnikové síti.
- Správa aktualizací softwaru, včetně toho, když se instalují.
- Spusťte jako vyhrazených veřejných terminálech, který můžete spustit jednu aplikaci, nebo spouštět aplikace pro řadu zařízení s Androidem.

V tomto článku jsou uvedené kroky k vytvoření profilu a poskytuje přehled o různých typů profilů, které lze vytvořit. Povolit nebo zakázat některé funkce na zařízeních, používání těchto profilů.

## <a name="create-the-profile"></a>Vytvoření profilu

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.

2. Vyberte **Konfigurace zařízení**. Máte následující možnosti:

    - **Přehled**: Zobrazí stav profilů a poskytuje další podrobnosti o profilech, které jste přiřadili uživatelům a zařízením.
    - **Správa**: Vytvoření profilů zařízení tím, že nahrajete vlastní [skripty prostředí PowerShell](intune-management-extension.md) ke spuštění v rámci profilu a přidejte datové tarify do zařízení pomocí [karty eSIM](esim-device-configuration.md).
    - **Monitorování**: Zkontrolovat stav profilu úspěchu nebo selhání a také zobrazit protokoly vašich profilů.
    - **Instalační program**: Přidat certifikační autoritu SCEP nebo PFX, nebo povolit [služby Telecom Expense Management](telecom-expenses-monitor.md) v profilu.

3. Vyberte **profily** > **vytvořit profil**. Zadejte tyto vlastnosti:

   - **Název**: Zadejte popisný název pro profil.
   - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
   - **Platforma**: Zvolte platformu zařízení. Možnosti:  

       - **Android**
       - **Android Enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 a novější**
       - **Windows 10 a novější**

   - **Typ profilu**: Vyberte typ nastavení, které chcete vytvořit. V zobrazeném seznamu závisí **platformy** zvolíte:

       - [Šablony pro správu](administrative-templates-windows.md)
       - [Vlastní](custom-settings-configure.md)
       - [Optimalizace doručení](delivery-optimization-windows.md)
       - [Funkce zařízení](device-features-configure.md)
       - [Omezení zařízení](device-restrictions-configure.md)
       - [Upgrade a režim přepínač Edition](edition-upgrade-configure-windows-10.md)
       - [Vzdělávání](education-settings-configure.md)
       - [E-mailu](email-settings-configure.md)
       - [Endpoint Protection](endpoint-protection-configure.md)
       - [Ochrana identit](identity-protection-configure.md)  
       - [Veřejný terminál](kiosk-settings.md)
       - [Certifikát PKCS](certficates-pfx-configure.md)
       - [Certifikát SCEP](certificates-scep-configure.md)
       - [Důvěryhodný certifikát](certificates-configure.md)
       - [Aktualizovat zásady](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Ochrana ATP v programu Windows Defender](advanced-threat-protection.md)
       - [Windows Information Protection](windows-information-protection-configure.md)

     Pokud vyberete třeba **iOS** pro platformu, možností typu profilu vypadat podobně jako následující:

     ![Vytvoření profilu iOS v Intune](./media/create-device-profile.png)

4. Vyberte **nastavení**. Nastavení jsou uspořádány podle kategorií. Vyberte kategorii zobrazíte seznam všech nastavení, která můžete konfigurovat.

5. Až budete hotovi, vyberte **OK** > **vytvořit** uložte provedené změny.

#### <a name="refresh-cycle-times"></a>Aktualizovat doby cyklů

Intune používá následující cyklů aktualizace kontrolu aktualizací konfigurace profilů:

| Platforma | Aktualizovat cyklu|
| --- | --- |
| iOS | Každých 6 hodin |
| macOS | Každých 6 hodin |
| Android | Každých 8 hodin |
| Počítače s Windows 10 zaregistrované jako zařízení | Každých 8 hodin |
| Windows Phone | Každých 8 hodin |
| Windows 8.1 | Každých 8 hodin |

Pokud zařízení zaregistrovalo nedávno, vrácení se změnami se spustí častěji:

| Platforma | Četnost |
| --- | --- |
| iOS | Prvních 6 hodin každých 15 minut a potom každých 6 hodin |  
| Mac OS X | Prvních 6 hodin každých 15 minut a potom každých 6 hodin | 
| Android | Prvních 15 minut každé 3 minuty, další 2 hodiny každých 15 minut a potom každých 8 hodin | 
| Windows Phone | Prvních 15 minut každých 5 minut, další 2 hodiny každých 15 minut a potom každých 8 hodin | 
| Počítače s Windows zaregistrované jako zařízení | Prvních 30 minut každé 3 minuty a potom každých 8 hodin | 

Kdykoli můžete uživatelům otevřete aplikaci portál společnosti a synchronizovat zařízení okamžitě zkontroloval aktualizace profilu.

### 
Další informace o odlišných typů profilů, přečtěte si další části tohoto článku.

## <a name="administrative-templates-preview"></a>Šablony pro správu (Preview)

[Šablony pro správu](administrative-templates-windows.md) zahrnuje stovky nastavení, která můžete nakonfigurovat pro aplikaci Internet Explorer, OneDrive, vzdálené plochy, Word, Excel a jiných aplikacích a spoustu dalších věcí.

Tyto šablony správce, kterým poskytuje snadný a zjednodušený přehled nastavení zásad skupiny podobné, ale jsou 100 % založené na cloudu. 

Tato funkce podporuje:

- Windows 10 a novější

## <a name="device-features"></a>Funkce zařízení

[Funkce zařízení](device-features-configure.md) ovládají funkce na zařízeních s Iosem a macOS, jako jsou AirPrint, oznámení a zprávy zámek obrazovky.

Tato funkce podporuje:

- iOS 
- macOS

## <a name="device-restrictions"></a>Omezení zařízení

[Omezení zařízení](device-restrictions-configure.md) řídí zabezpečení, hardware, sdílení dat a další nastavení na zařízeních. Můžete například vytvořit profil omezení zařízení, který uživatelům zařízení s iOSem zakazuje použít fotoaparát v zařízení. 

Tato funkce podporuje:

- Android
- Android enterprise
- iOS
- macOS
- Windows 10 a novější
- Windows 10 Team

## <a name="delivery-optimization"></a>Optimalizace doručení

[Optimalizace doručení](delivery-optimization-windows.md) poskytuje lepší prostředí pro doručování aktualizací softwaru. Tato nastavení jsou nahrazení **aktualizace softwaru** > **aktualizační kanál Windows 10** nastavení.

Pomocí těchto nastavení můžete řídit, jak se aktualizace softwaru se stáhnou do zařízení ve vaší organizaci. Například můžete umožnit uživatelům získat vlastní aktualizace nebo aktualizace pomocí cloudových služeb, která optimalizace doručování v profilu zařízení.

Tato funkce podporuje:

- Windows 10 a novější

## <a name="endpoint-protection"></a>Ochrana koncového bodu

[Nastavení služby Ochrana koncového bodu pro Windows 10](endpoint-protection-windows-10.md) konfiguruje nastavení pro BitLocker a Windows Defender pro zařízení s Windows 10.

Informace o zařazení rozšířené ochrany před internetovými útoky v programu Windows Defender pomocí Microsoft Intune najdete v článku o [konfiguraci koncových bodů pomocí nástrojů pro správu mobilních zařízení (MDM)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection).

Tato funkce podporuje:

- Windows 10 a novější

## <a name="identity-protection"></a>Ochrana identit

[Ochrana identit](identity-protection-configure.md) řídí prostředí Windows Hello pro firmy na zařízeních s Windows 10 a Windows 10 Mobile. Konfigurací těchto nastavení můžete zpřístupnit Windows Hello pro firmy uživatelům a zařízením a specifikovat požadavky na PIN kódy a gesta zařízení.  

Tato funkce podporuje:  

- Windows 10 a novější
- Windows Holographic for Business  

## <a name="kiosk"></a>Kiosk

[Nastavení celoobrazovkového](kiosk-settings.md) profilu konfiguruje zařízení běžela jedna aplikace nebo spustit velký počet aplikací. Na svém veřejném terminálu si můžete přizpůsobit i další funkce, například úvodní nabídku a webový prohlížeč.

Tato funkce podporuje:

- Windows 10 a novější

K dispozici i jako omezení zařízení pro nastavení celoobrazovkového [Android](device-restrictions-android.md#kiosk), [Androidu Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings), a [ios](device-restrictions-ios.md#kiosk-supervised-only).

## <a name="email"></a>Email

[Nastavení e-mailu](email-settings-configure.md) vytvoří, přiřadí a sleduje nastavení e-mailu protokolu Exchange ActiveSync na zařízeních. E-mailové profily pomoc s konzistencí, omezíte volání podpory a umožní koncovým uživatelům přístup k firemnímu e-mailu na jejich osobních zařízení bez nutnosti něco nastavovat jejich část. 

Tato funkce podporuje: 

- Android
- iOS
- Windows Phone 8.1
- Windows 10 a novější

## <a name="vpn"></a>Síť VPN

[Nastavení VPN](vpn-settings-configure.md) přiřadí uživatelům a zařízením v organizaci profily sítě VPN, aby se mohli snadno a bezpečně připojit k síti. 

Virtuální privátní sítě (VPN) umožňují uživatelům zabezpečený vzdálený přístup k firemní síti. Zařízení používají profil připojení VPN k navázání připojení se serverem VPN. 

Tato funkce podporuje: 

- Android
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 a novější

## <a name="wi-fi"></a>Wi-Fi

[Nastavení Wi-Fi](wi-fi-settings-configure.md) přiřadí uživatelům a zařízením nastavení bezdrátové sítě. Po přiřazení profilu Wi-Fi získají uživatelé přístup k vaší podnikové síti, aniž by ji museli konfigurovat sami. 

Tato funkce podporuje: 

- Android
- iOS
- macOS
- Windows 8.1 (pouze import)
- Windows 10 a novější

## <a name="esim-cellular---public-preview"></a>Mobilní profily eSIM ve verzi Public Preview

[mobilní profily karty eSIM](esim-device-configuration.md) umožňuje správcům nakonfigurovat mobilní datové tarify pro vaše spravovaná zařízení pro přístup k Internetu a data. Po získání aktivační kódy od mobilního operátora, použijte k importu těchto aktivační kódy a zařaďte do zařízení s podporou karty eSIM Intune.

Tato funkce podporuje:
- Windows 10 Fall Creators Update a novější

## <a name="education"></a>Vzdělávání

[Nastavení vzdělávání – Windows 10](education-settings-configure.md) konfiguruje možnosti pro [aplikaci Windows Zkuste si test](https://education.microsoft.com/gettrained/win10takeatest). Když tyto možnosti nakonfigurujete, žádnou jinou aplikaci nepůjde na zařízení spustit, dokud nebude test dokončen.

[Nastavení vzdělávání – iOS](education-settings-configure-ios-shared.md) používá aplikaci Classroom pro systém iOS, která umožňuje vést výuku a ovládat zařízení studentů v učebně. Zařízení iPad můžete nakonfigurovat tak, že mnoho studentů můžou sdílet jedno zařízení.

## <a name="edition-upgrade"></a>Upgrade edice

[Upgrady edice Windows 10](edition-upgrade-configure-windows-10.md) automaticky upgradují zařízení s některými verzemi Windows 10 na novější edici.

Tato funkce podporuje: 
- Windows 10 a novější

## <a name="update-policies"></a>Zásady aktualizací

[Zásady aktualizací pro iOS](software-updates-ios.md) ukazují, jak vytvořit a přiřadit zásady pro iOS k instalaci aktualizací softwaru na zařízení s iOSem. Můžete také zkontrolovat stav instalace.

Aktualizace zásad na zařízeních s Windows, naleznete v tématu [optimalizace doručení](delivery-optimization-windows.md). 

Tato funkce podporuje:
- iOS

## <a name="certificates"></a>Certifikáty

[Certifikáty](certificates-configure.md) nakonfiguruje považuje za důvěryhodnou, SCEP a PKCS certifikáty, které je přiřazený k zařízením a používá k ověřování Wi-Fi, VPN a e-mailové profily.

Tato funkce podporuje: 

- Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 a novější

## <a name="windows-information-protection-profile"></a>Profil Windows Information Protection

[Služba Windows Information Protection](windows-information-protection-configure.md) pomáhá chránit před únikem dat, aniž by zasahovala do možností zaměstnanců. Pomáhá také chránit podnikové aplikace a data před náhodnými úniky dat na firemních zařízeních a osobních zařízeních, která zaměstnanci používají v práci. Pomocí Windows Information Protection nevyžaduje změny prostředí nebo jiných aplikací.

Tato funkce podporuje:

- Windows 10 a novější

## <a name="shared-multi-user-device"></a>Sdílené zařízení s více uživateli

[Windows 10](shared-user-device-settings-windows.md) a [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md) zahrnuje nastavení pro správu zařízení s více uživateli, označované také jako sdílená zařízení nebo sdílené počítače. Když se uživatel přihlásí k zařízení, zvolíte-li uživatel může změnit možnosti Přejít do režimu spánku nebo uložit soubory v zařízení. Například můžete vytvořit profil, který odstraní neaktivní přihlašovacích údajů ze zařízení HoloLens Windows pro úsporu místa.

Tato nastavení sdílených více uživateli zařízení umožňují správcům řídit některé funkce zařízení a spravovat tyto sdílené zařízení přes Intune.

Tato funkce podporuje:

- Windows 10 a novější
- Windows Holographic for Business

## <a name="custom-profile"></a>Profil Vlastní

[Vlastní nastavení](custom-settings-configure.md) umožňuje správcům přiřadit nastavení zařízení, která nejsou předdefinovaná v Intune. Například na zařízení s Androidem, můžete zadat hodnoty OMA-URI. U zařízení s iOSem můžete naimportovat konfigurační soubor, který jste vytvořili v nástroji Apple Configurator. 

Tato funkce podporuje:

- Android
- iOS
- macOS
- Windows Phone 8.1

## <a name="manage-and-troubleshoot"></a>Správa a řešení problémů

[Při správě profilů](device-profile-monitor.md) můžete zjistit stav zařízení a přiřazené profily. Zobrazením nastavení, která způsobují konflikt, a profilů, které tato nastavení obsahují, si můžete pomoci při řešení konfliktů. [Běžné problémy a řešení](device-profile-troubleshoot.md) poskytuje funkce Q & A usnadňují práci s profily, včetně toho, co se stane po odstranění profilu, která způsobí, že oznámení k odeslání do zařízení a další.

## <a name="next-steps"></a>Další postup

Zvolte vaši platformu a začít pracovat.