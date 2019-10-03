---
title: Co je nového v předchozích měsících v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Kontrola starších oznámení na stránce co je nového v Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 7/8/2019
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1af106227442e91121f6c8c653c261bd677f3a9f
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71814180"
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Co je nového v Microsoft Intune – předchozí měsíce

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

<!-- ########################## -->
## <a name="december-2018"></a>Prosinec 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="updates-for-application-transport-security----748318---"></a>Aktualizace pro zabezpečení přenosu aplikace <!-- 748318 -->

Microsoft Intune podporuje zabezpečení TLS (Transport Layer Security) 1.2 +, aby bylo zajištěno, že služba Intune je ve výchozím nastavení bezpečnější a že se bude v souladu s dalšími službami společnosti Microsoft, jako je systém Microsoft Office 365. Aby bylo možné tento požadavek splnit, portál společnosti pro iOS a macOS vynutilí aktualizované požadavky na ATS (Application Transport Security) společnosti Apple, které budou také vyžadovat protokol TLS 1.2 +. ATS se používá k prosazování přísnějšího zabezpečení pro veškerou komunikaci aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune, kteří používají aplikace Portál společnosti pro iOS a macOS. Další informace najdete v [blogu podpory pro Intune](https://aka.ms/compportalats).

#### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Sada Intune App SDK bude podporovat 256 bitů šifrovacích klíčů. <!-- 1832174 -->
Intune App SDK pro Android teď používá 256 šifrovacích klíčů, pokud je šifrování povolené zásadami ochrany aplikací. Sada SDK bude nadále poskytovat podporu 128 bitových klíčů pro kompatibilitu s obsahem a aplikacemi, které používají starší verze sady SDK.

#### <a name="microsoft-auto-update-version-450-required-for-macos-devices----3503442---"></a>Pro zařízení macOS se vyžaduje 4.5.0 verze automatického aktualizace od Microsoftu. <!-- 3503442 -->
Aby bylo možné pokračovat v přijímání aktualizací Portál společnosti a dalších aplikací Office, musí zařízení spravovaná službou Intune upgradovat na Microsoft 4.5.0 Update. Uživatelé už můžou mít tuto verzi pro svoje aplikace Office.

### <a name="device-management"></a>Správa zařízení

#### <a name="intune-requires-macos-1012-or-later----2827778---"></a>Intune vyžaduje macOS 10,12 nebo novější. <!-- 2827778 -->
Intune teď vyžaduje verzi macOS 10,12 nebo novější. Zařízení s předchozími verzemi macOS nemůžou použít Portál společnosti k registraci do Intune. Aby uživatelé mohli dostávat podporu a nové funkce, musí upgradovat svoje zařízení na macOS 10,12 nebo novější a upgradovat Portál společnosti na nejnovější verzi.

<!-- ########################## -->
## <a name="november-2018"></a>Listopadu 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Odinstalace aplikací ve vlastnictví zařízení iOS vlastněných společností <!-- 1281677 -->
Můžete odebrat libovolnou aplikaci na zařízeních s iOS, která jsou ve vlastnictví. Libovolnou aplikaci můžete odebrat tak, že se zacílíte na skupiny uživatelů nebo zařízení pomocí typu přiřazení **odinstalace** . U osobních nebo nekontrolovaných zařízení s iOS budete moct i nadále odebírat jenom aplikace, které se nainstalovaly přes Intune.

#### <a name="downloading-intune-win32-app-content----2617320---"></a>Stahuje se obsah aplikace Win32 pro Intune. <!-- 2617320 -->
Klienti s Windows 10 RS3 a novějšími stáhne obsah aplikace Intune Win32 pomocí součásti Optimalizace doručení v klientovi s Windows 10. Optimalizace doručení poskytuje funkce peer-to-peer, které jsou ve výchozím nastavení zapnuté. V současné době se Optimalizace doručení dá nakonfigurovat pomocí zásad skupiny. Další informace najdete v tématu [optimalizace doručování pro Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Nabídka obsahu zařízení a aplikace pro koncové uživatele <!-- 2771453 -->
Koncoví uživatelé teď můžou pomocí místní nabídky na zařízeních a aplikacích aktivovat běžné akce, jako je přejmenování zařízení nebo kontrola dodržování předpisů.

#### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Nastavení vlastního pozadí v aplikaci spravované na domovské obrazovce  <!-- 3041945 -->
Přidáváme nastavení, které vám umožní přizpůsobit vzhled aplikace spravované domovské obrazovky v zařízeních s Androidem Enterprise, multi-App a celoobrazovkovém režimu.  Pokud chcete nakonfigurovat **pozadí vlastní adresy URL**, přečtěte si v části Azure Portal > konfigurace zařízení Intune. Vyberte aktuální profil konfigurace zařízení nebo vytvořte nový, abyste mohli upravit jeho nastavení veřejného terminálu.
Nastavení veřejného terminálu najdete v tématu [omezení pro zařízení s Androidem Enterprise](../configuration/device-restrictions-android-for-work.md).

#### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Uložení a použití přiřazení zásad ochrany aplikací <!-- 3104570 -->
Teď máte lepší kontrolu nad [přiřazením zásad ochrany aplikací](../apps/app-protection-policies.md#deploy-a-policy-to-users). Když vyberete *přiřazení* pro nastavení nebo úpravu přiřazení zásady, musíte před použitím změny **Uložit** svou konfiguraci. Pomocí **zahození** zrušte zaškrtnutí všech změn, které provedete bez uložení změn do seznamů zahrnutí nebo vyloučení.  Když budete vyžadovat uložení nebo zahození, přiřadí se zásadám ochrany aplikací jenom uživatelé, kterým máte v úmyslu.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Nové nastavení prohlížeče Microsoft Edge pro Windows 10 a novější <!-- 3174639 -->
Tato aktualizace obsahuje nová nastavení, která vám pomůžou řídit a spravovat prohlížeč Microsoft Edge na vašich zařízeních. Seznam těchto nastavení najdete v tématu [omezení pro zařízení s Windows 10 (a novější)](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser).

#### <a name="new-apps-support-with-app-protection-policies----3330037---"></a>Podpora nových aplikací pomocí zásad ochrany aplikací <!-- 3330037 -->
Teď můžete spravovat tyto aplikace pomocí [zásad ochrany aplikací Intune](../apps/app-protection-policies.md):
- Stream (iOS)
- Postup (Android, iOS)
- PowerApps (Android, iOS)
- Tok (Android, iOS)

Zásady ochrany aplikací slouží k ochraně podnikových dat a řízení přenosu dat pro tyto aplikace, jako jsou jiné aplikace spravované zásadou Intune. Poznámka: Pokud tok ještě není viditelný v konzole, přidáte tok při vytváření nebo úpravách a zásadách ochrany aplikací. Provedete to tak, že použijete možnost **a další aplikace** a v poli vstupní pole zadáte *ID aplikace* pro tok. Pro Android použijte *com. Microsoft. Flow*a pro iOS použijte *com. Microsoft. procsimo*.


### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Podpora pro iOS 12 OAuth v e-mailových profilech iOS <!--2155106 -->
E-mailové profily pro iOS v Intune podporují iOS 12 Open Authorization (OAuth). Tuto funkci zobrazíte tak, že vytvoříte nový profil (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro > **platformu pro typ** profilu) nebo aktualizovat stávající e-mailový profil iOS. Pokud protokol OAuth povolíte v profilu, který už je pro uživatele nasazený, zobrazí se jim výzva k opětovnému ověření a stažení e-mailu.

[e-mailové profily iOS](../configuration/email-settings-ios.md) obsahují další informace o použití OAuth v e-mailovém profilu.

#### <a name="network-access-control-nac-support-for-citrix-sso-for-ios----3259404---"></a>Podpora sítě Access Control (NAC) pro Citrix SSO pro iOS <!-- 3259404 -->
Společnost Citrix vydala aktualizaci brány Citrix, která umožňuje síťové Access Control (NAC) pro Citrix SSO pro iOS v Intune. Můžete se rozhodnout, jestli chcete do služby Intune zahrnout ID zařízení v rámci profilu sítě VPN, a potom tento profil nasdílet do zařízení s iOS. Abyste mohli používat tuto funkci, budete muset nainstalovat nejnovější aktualizaci pro bránu Citrix.

[Konfigurace nastavení sítě VPN na zařízeních s iOS](../configuration/vpn-settings-ios.md#base-vpn-settings) nabízí další informace o používání NAC, včetně některých dalších požadavků. 

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown----1892471---"></a>zobrazí se čísla verzí iOS a macOS a čísla sestavení. <!-- 1892471 -->
V případě dodržování předpisů **zařízením**@no__t**dodržování předpisů zařízením**-1 se zobrazují verze operačních systémů iOS a MacOS a jsou dostupné pro použití v zásadách dodržování předpisů. Tato aktualizace zahrnuje číslo sestavení, které je možné konfigurovat pro obě platformy.
Při vydání aktualizací zabezpečení společnost Apple obvykle ponechá číslo verze tak, jak je, ale aktualizuje číslo buildu. Pomocí čísla sestavení v zásadách dodržování předpisů můžete snadno zjistit, jestli je nainstalovaná aktualizace ohrožení zabezpečení.
Pokud chcete tuto funkci použít, přečtěte si téma zásady dodržování předpisů pro [iOS](../protect/compliance-policy-create-ios.md#device-health) a [MacOS](../protect/compliance-policy-create-mac-os.md#device-properties) .

#### <a name="update-rings-are-being-replaced-with-delivery-optimization-settings-for-windows-10-and-later----2753807---"></a>Aktualizační kroužky se nahrazují nastavením Optimalizace doručení pro Windows 10 a novější. <!-- 2753807 -->
Optimalizace doručení je nový konfigurační profil pro Windows 10 a novější. Tato funkce poskytuje efektivnější možnosti pro doručování aktualizací softwaru do zařízení ve vaší organizaci. Tato aktualizace také pomáhá doručovat nastavení v nových a existujících aktualizačních zazvoněních pomocí konfiguračního profilu.
Pokud chcete nakonfigurovat konfigurační profil optimalizace doručování, přečtěte si téma [nastavení Optimalizace doručení Windows 10 (a novější)](../configuration/delivery-optimization-windows.md).

#### <a name="new-device-restriction-settings-added-to-ios-and-macos-devices----2827760---"></a>Nová nastavení omezení zařízení přidaná do zařízení se systémem iOS a macOS <!-- 2827760 -->
Tato aktualizace obsahuje nová nastavení pro zařízení s iOS a macOS, která jsou vydaná s iOS 12:

**Nastavení iOS**: 
- Obecné: blokování odebírání aplikací (jenom pod dohledem)
- Obecné: blokový režim s omezeným přístupem USB (jenom pod dohledem)
- Obecné: vynucení automatického data a času (jenom pod dohledem)
- Heslo: blokovat automatické vyplňování hesla (jenom pod dohledem)
- Heslo: zablokovat žádosti o blízkost hesla (jenom pod dohledem)
- Heslo: blokování sdílení hesel (jenom pod dohledem)

**MacOS nastavení**: 
- Heslo: blokovat automatické vyplňování hesla
- Heslo: zablokovat žádosti o blízkost hesla
- Heslo: blokování sdílení hesel

Další informace o těchto nastaveních najdete v tématu Nastavení omezení pro zařízení s [iOS](../configuration/device-restrictions-ios.md) a [MacOS](../configuration/device-restrictions-macos.md) .

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview----1048100--"></a>Podpora autopilotu pro zařízení připojená k hybridnímu Azure Active Directory (Preview) <!-- 1048100-->
Pomocí autopilotu teď můžete nastavit hybridní Azure Active Directory připojená zařízení. Aby bylo možné používat funkci Hybrid autopilot, musí být zařízení připojená k síti vaší organizace. Další informace najdete v tématu [nasazení hybridních zařízení připojených k Azure AD pomocí Intune a Windows autopilotu](../enrollment/windows-autopilot-hybrid.md).
Tato funkce se v průběhu několika dalších dnů zavádí v rámci uživatelské základny. Proto možná nebudete moct postupovat podle těchto kroků, dokud se nevrátíte k vašemu účtu.

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Výběr aplikací sledovaných na stránce stavu registrace<!-- 2531007 -->
Můžete si vybrat, které aplikace se budou sledovat na stránce Stav registrace. Dokud tyto aplikace nenainstalujete, uživatel nebude moct zařízení používat. Další informace najdete v tématu [nastavení stránky stavu registrace](../enrollment/windows-enrollment-status.md).

#### <a name="search-for-autopilot-device-by-serial-number---2595788---"></a>Vyhledat zařízení autopilotu podle sériového čísla <!--2595788 -->
Zařízení s autopilotem teď můžete vyhledávat podle sériového čísla. Provedete to tak, že zvolíte **registrace zařízení** > **zařízení** s**Windows registrace** >  > do pole **Hledat podle sériového čísla** zadejte sériové číslo > stiskněte klávesu ENTER.

#### <a name="track-installation-of-office-proplus---2620217---"></a>Sledovat instalaci Office ProPlus <!--2620217 -->
Uživatelé můžou sledovat průběh instalace [Office ProPlus](../apps/apps-add-office365.md) pomocí [stránky stavu registrace](../enrollment/windows-enrollment-status.md). Další informace najdete v tématu [nastavení stránky stavu registrace](../enrollment/windows-enrollment-status.md).

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Výstrahy pro vypršení platnosti tokenu VPP nebo licence na Portál společnosti s nízkým provozem <!-- 2237572 -->
Pokud používáte program Volume purchase program (VPP) k předběžnému zřízení Portál společnosti během registrace DEP, Intune vás upozorní, když se brzo vyprší platnost tokenu VPP a když jsou spuštěné licence pro Portál společnosti nízké.

#### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133---"></a>Podpora macOS Program registrace zařízení pro účty Apple School Manageru <!--3006133 -->
Intune teď podporuje použití Program registrace zařízení na zařízeních macOS pro účty Apple School Manageru.  Další informace najdete v tématu [Automatická registrace zařízení MacOS pomocí Apple School Manageru nebo program registrace zařízení](../enrollment/device-enrollment-program-enroll-macos.md).

#### <a name="new-intune-device-subscription-sku---3312071--"></a>Nová SKU předplatného zařízení Intune <!--3312071-->
Aby bylo možné snížit náklady na správu zařízení v podnicích, je nyní k dispozici nová SKU pro předplatné na základě zařízení. Tato SKU zařízení v Intune se po měsících licencují na každé zařízení. Ceny se liší podle licenčního programu. Je k dispozici přímo prostřednictvím centra pro správu Microsoft 365, a to prostřednictvím služby [smlouva Enterprise](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2) (EA), [smlouvy o poskytování produktů a služeb](https://www.microsoft.com/licensing/mpsa/default) (MPSA), [Microsoft Open Agreement](https://partner.microsoft.com/licensing/licensing-agreements)a [poskytovatele Cloud Solution Provider](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453) (CSP). .

### <a name="device-management"></a>Správa zařízení

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Dočasně pozastavit celoobrazovkový režim na zařízeních s Androidem a provést změny <!-- 3041935 -->
Pokud používáte zařízení s Androidem v celoobrazovkovém režimu s více aplikacemi, může být nutné, aby správce IT provedl změny v zařízení. Tato aktualizace zahrnuje nová nastavení veřejného terminálu s více aplikacemi, která správcům IT umožňuje dočasně pozastavit celoobrazovkový režim pomocí PIN kódu a získat přístup k celému zařízení.
Nastavení veřejného terminálu najdete v tématu [omezení pro zařízení s Androidem Enterprise](../configuration/device-restrictions-android-for-work.md).

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Povolit virtuální domovské tlačítko na zařízeních s Androidem Enterprise  <!-- 3042021 -->
Nové nastavení umožní uživatelům na svém zařízení klepnout na tlačítko s jemnou klávesou, aby přepnuli mezi aplikací spravované domovské obrazovky a dalšími přiřazenými aplikacemi na veřejném zařízení s více aplikacemi. Toto nastavení je užitečné zejména ve scénářích, kdy aplikace veřejného terminálu uživatele nereaguje správně na tlačítko zpět. Toto nastavení budete moct nakonfigurovat pro zařízení s Androidem, která jsou ve vlastnictví firmy. Pokud chcete povolit nebo zakázat **virtuální domovské tlačítko**, v Azure Portal > konfiguraci zařízení, přejít na Intune. Vyberte aktuální profil konfigurace zařízení nebo vytvořte nový, abyste mohli upravit jeho nastavení veřejného terminálu.
Nastavení veřejného terminálu najdete v tématu [omezení pro zařízení s Androidem Enterprise](../configuration/device-restrictions-android-for-work.md).




<!-- ########################## -->
## <a name="october-2018"></a>Říjen 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Přístup k vlastnostem klíčového profilu pomocí aplikace Portál společnosti <!-- 772203 -->
Koncoví uživatelé teď můžou přistupovat ke klíčovým vlastnostem a akcím účtu, jako je resetování hesla, z aplikace Portál společnosti. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>nastavení aplikací v iOS můžou blokovat klávesnice třetích stran. <!-- 1248481 -->
V zařízeních s iOS můžou správci Intune při přístupu k datům organizace v aplikacích chráněných podle zásad blokovat použití klávesnic třetích stran. Když je zásada ochrany aplikací (aplikace) nastavená tak, aby blokovala klávesnice třetích stran, uživatel zařízení obdrží zprávu při prvním použití klávesnice třetí strany při jejich interakci s firemními daty. Všechny možnosti, jiné než nativní klávesnice, se zablokují a uživatelé zařízení je uvidí. Uživatelům zařízení se zpráva zobrazí jenom jednou. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>Přístup uživatelských účtů k aplikacím Intune na spravovaných zařízeních s Androidem a iOS <!-- 1248496 -->
Jako správce Microsoft Intune můžete řídit, které uživatelské účty se přidají do systém Microsoft Office aplikací na spravovaných zařízeních. Můžete omezit přístup pouze na povolené uživatelské účty organizace a blokovat osobní účty na zaregistrovaných zařízeních. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>Zásady konfigurace aplikace Outlook pro iOS a Android <!--1828527 -->
Teď můžete vytvořit zásady konfigurace aplikace Outlook pro iOS a Android pro iOS a Android pro místní uživatele, kteří využívají základní ověřování s protokolem ActiveSync. Další nastavení konfigurace budou přidána, protože jsou povolená pro Outlook pro iOS a Android.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Jazykové sady pro sadu Office 365 pro plus <!-- 1833450 -->
Jako správce Intune budete moct nasadit další jazyky pro aplikace Office 365 pro plus spravované přes Intune. Seznam dostupných jazyků zahrnuje **typ** jazykové sady (jádro, částečný a kontrola pravopisu). V Azure Portal vyberte **Microsoft Intune** **aplikace** > **klienta aplikace** >   > **Přidat**. V seznamu **Typ aplikace** v okně **Přidat aplikaci** vyberte v části sada **Office 365**možnost **Windows 10** . V okně **nastavení sady App Suite** vyberte **jazyky** .

#### <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Obchodní aplikace (LOB) – přípony souborů aplikací pro Windows <!-- 1884873 -->
Přípony souborů pro obchodní aplikace Windows teď budou zahrnovat soubory *. msi*, *. appx*, *. appxbundle*, *. msix*a *. msixbundle*. Aplikaci můžete do Microsoft Intune přidat tak, že vyberete **klientské aplikace**@no__t **-1 @no__t**-3**Přidat**. Zobrazí se podokno **Přidat aplikaci** , které umožňuje výběr **typu aplikace**. U aplikací pro Windows LOB jako typ aplikace vyberte **obchodní** aplikaci, vyberte **soubor balíčku aplikace**a pak zadejte instalační soubor s odpovídajícím rozšířením.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Nasazení aplikací pro Windows 10 pomocí Intune <!-- 2309001 -->
V rámci stávající podpory obchodních aplikací a Microsoft Store pro obchodní aplikace můžou správci pomocí Intune nasadit většinu stávajících aplikací v organizaci pro koncové uživatele na zařízeních s Windows 10. Správci můžou přidat, nainstalovat a odinstalovat aplikace pro uživatele Windows 10 v nejrůznějších formátech, například MSIs, Setup. exe nebo MSP. Intune bude vyhodnocovat pravidla požadavků před stažením a instalací a oznamuje koncovým uživatelům požadavků na stav nebo restartování pomocí centra akcí Windows 10. Tato funkce bude efektivně odblokovat organizace, které zajímá přesunutí této úlohy do Intune a cloudu. Tato funkce je aktuálně ve verzi Public Preview a očekáváme, že do této funkce za několik následujících měsíců přidáme významné nové funkce. 

#### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Nastavení zásad ochrany aplikací (APP) pro webová data <!-- 2662995 -->
Nastavení zásad aplikací pro webový obsah na zařízeních s Androidem i iOS se budou aktualizovat tak, aby lépe zpracovávala webové odkazy http i HTTPS i přenos dat prostřednictvím univerzálních odkazů pro iOS a odkazů na aplikace pro Android. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Nabídka obsahu zařízení a aplikace pro koncové uživatele <!-- 2771453 -->
Koncoví uživatelé teď můžou pomocí místní nabídky na zařízeních a aplikacích aktivovat běžné akce, jako je přejmenování zařízení nebo kontrola dodržování předpisů. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>Klávesové zkratky pro Windows Portál společnosti <!-- 2771518 -->
Koncoví uživatelé teď budou moct aktivovat akce aplikace a zařízení ve Windows Portál společnosti pomocí klávesových zkratek (akcelerátory).

#### <a name="require-non-biometric-pin-after-a-specified-timeout----1506985---"></a>Po zadaném časovém limitu vyžadovat kód PIN, který není biometrické <!-- 1506985 -->
Díky tomu, že po vypršení časového limitu správce vyžaduje PIN kód, který není biometrické, poskytuje Intune vylepšené zabezpečení pro aplikace s podporou správy mobilních aplikací (MAM) tím, že omezuje použití biometrické identifikace pro přístup k podnikovým datům. Nastavení mají vliv na uživatele, kteří spoléhají na dotykové ID (iOS), ID obličeje (iOS), biometrické biometriky nebo jiné metody biometrického ověřování pro přístup k aplikacím, které podporují aplikace a MAM. Tato nastavení umožňují správcům Intune podrobnější kontrolu nad uživatelským přístupem a eliminují případy, kdy zařízení s více otisky prstů nebo jinými metodami biometrického přístupu může podniková data odhalit nesprávnému uživateli. V Azure Portal otevřete **Microsoft Intune**. Vyberte **klientské aplikace** > **zásady ochrany aplikací** > **přidejte** **Nastavení**zásad  > . Vyhledejte konkrétní nastavení v části věnované **přístupu** . Informace o nastavení přístupu najdete v tématu [Nastavení iOS](../apps/app-protection-policy-settings-ios.md#access-requirements) a [nastavení Androidu](../apps/app-protection-policy-settings-android.md#access-requirements).

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Nastavení přenosu dat aplikací v Intune na zařízeních zaregistrovaných pro iOS MDM <!-- 2244713 -->
Můžete oddělit řízení nastavení přenosu dat aplikací Intune na zařízeních zaregistrovaných pro iOS MDM od zadání identity zaregistrovaného uživatele, označovaného taky jako hlavní název uživatele (UPN). Správci, kteří nepoužívají IntuneMAMUPN, nebudou sledovat změny chování. Když je tato funkce k dispozici, správci používající IntuneMAMUPN k řízení chování přenosu dat na zaregistrovaných zařízeních by se měli podívat na nová nastavení a podle potřeby aktualizovat nastavení aplikace.

#### <a name="windows-10-win32-apps----2617325---"></a>Aplikace Win32 pro Windows 10 <!-- 2617325 -->
Aplikace Win32 můžete nakonfigurovat tak, aby byly nainstalované v uživatelském kontextu pro jednotlivé uživatele, a nainstalovat aplikaci pro všechny uživatele zařízení.

#### <a name="windows-win32-apps-and-powershell-scripts----2617330---"></a>Aplikace Windows Win32 a skripty PowerShellu <!-- 2617330 -->
Koncoví uživatelé už nemusí být přihlášení k zařízení, aby mohli instalovat aplikace Win32 nebo spouštět skripty PowerShellu. 

#### <a name="troubleshooting-client-app-installation----1363711---"></a>Řešení potíží s instalací klientské aplikace <!-- 1363711 -->
Úspěšnost instalace klientských aplikací můžete vyřešit pomocí kontroly sloupce s názvem **instalace aplikace** v okně **Poradce při potížích** . Pokud chcete zobrazit okno **řešení potíží** , na portálu Intune vyberte **řešení potíží** v části **pomoc a podpora**.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>Vytvoření přípon DNS v konfiguračních profilech sítě VPN na zařízeních s Windows 10<!-- 1333668 -->
Když vytvoříte profil konfigurace zařízení VPN (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** Platform > typu profilu **VPN** ), zadáte některá nastavení DNS. V rámci této aktualizace můžete do Intune zadat taky několik **přípon DNS** . Pokud používáte přípony DNS, můžete místo plně kvalifikovaného názvu domény (FQDN) vyhledat síťový prostředek pomocí jeho krátkého názvu. Tato aktualizace také umožňuje změnit pořadí přípon DNS v Intune.
[Nastavení sítě VPN pro Windows 10](../configuration/vpn-settings-windows-10.md#dns-settings) uvádí aktuální nastavení DNS.
Platí pro: zařízení s Windows 10

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Podpora pro pracovní profily s Androidem Enterprise v rámci vždycky zapnuté sítě VPN <!-- 1333705 -->
V této aktualizaci můžete na zařízeních s Androidem Enterprise se spravovanými pracovními profily použít připojení VPN typu Always On on. Připojení k síti VPN Always On zůstane připojené nebo se okamžitě znovu připojí, když uživatel odemkne své zařízení, když se zařízení restartuje nebo když se změní bezdrátová síť. Připojení můžete také umístit v režimu uzamčení, což blokuje veškerý provoz v síti, dokud nebude připojení VPN aktivní.
V nastavení **zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** pro > **omezení zařízení**@no__t **-8 můžete** povolit možnost vždycky zapnuté připojení k síti VPN.

#### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>Vystavení certifikátů SCEP pro zařízení bez uživatelů <!-- 1744554 -->
V současné době jsou certifikáty vydávány uživatelům. V této aktualizaci je možné certifikáty SCEP vystavovat zařízením, včetně zařízení bez uživatele, jako jsou veřejné terminály (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** pro platformu > **Certifikát SCEP** pro profil). Mezi další aktualizace patří:
- Vlastnost **Subject** v profilu SCEP je teď vlastním textovým polem a může obsahovat nové proměnné. 
- Vlastnost **alternativní název subjektu (San)** v profilu SCEP je teď formátem tabulky a může obsahovat nové proměnné. Správce může v tabulce přidat atribut a vyplnit hodnotu ve vlastním textovém poli. SÍŤ SAN bude podporovat tyto atributy: 
  - DNS
  - E-mailová adresa
  - NÁZVU

  Tyto nové proměnné lze přidat se statickým textem do textového pole vlastní hodnota. Atribut DNS se dá například přidat jako `DNS = {{AzureADDeviceId}}.domain.com`.

  > [!NOTE]
  > Složené závorky, středníky a symboly kanálu {}; | nebudou fungovat na statickém textu sítě SAN. Složené závorky musí obsahovat jenom jednu z nových proměnných certifikátu zařízení, které se mají přijmout `Subject` nebo `Subject alternative name`. 

Nové proměnné certifikátu zařízení:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
> - `{{FullyQualifiedDomainName}}` funguje pouze pro zařízení se systémem Windows a připojené k doméně. 
> - Při zadávání vlastností zařízení, jako je IMEI, sériové číslo a plně kvalifikovaného názvu domény v předmětu nebo síti SAN pro certifikát zařízení, mějte na paměti, že tyto vlastnosti může být falešné osobou, která má přístup k zařízení. 

Při vytváření konfiguračního profilu SCEP se [vytvoří profil certifikátu SCEP](../protect/certificates-profile-scep.md#create-a-scep-certificate-profile) se seznamem aktuálních proměnných. 

Platí pro: Windows 10 a novější a iOS, podporované pro Wi-Fi

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Vzdáleně uzamknout zařízení, která nedodržují předpisy <!-- 2064495 -->
Pokud zařízení nedodržuje předpisy, můžete vytvořit akci se zásadami dodržování předpisů, které zařízení zamkne vzdáleně. V Intune > **dodržování předpisů zařízením**, vytvořte novou zásadu nebo vyberte existující zásady > **vlastnosti**. Vyberte **Akce při nedodržení předpisů** > **Přidat**a zvolte možnost vzdálené uzamčení zařízení.
Podporováno v: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8,1 a novější 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>Vylepšení profilu veřejného terminálu Windows 10 a novějšího v Azure Portal <!-- 2748224 -->
Tato aktualizace zahrnuje následující vylepšení konfiguračního profilu zařízení s Windows 10 (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** pro platformu >  **Celoobrazovkový náhled** pro typ profilu): 
- V současné době můžete na jednom zařízení vytvořit více profilů na veřejném terminálu. V této aktualizaci bude Intune podporovat pro každé zařízení jenom jeden profil veřejného terminálu. Pokud pořád potřebujete víc profilů na veřejném terminálu na jednom zařízení, můžete použít vlastní identifikátor URI.
- V profilu veřejného **terminálu s více aplikacemi** můžete vybrat velikost a pořadí dlaždice aplikace pro **rozložení nabídky Start** v mřížce aplikace. Pokud dáváte přednost více přizpůsobením, můžete pokračovat v nahrávání souboru XML.
- Nastavení prohlížeče veřejného terminálu se přesouvá do nastavení veřejného **terminálu** . V současné době má nastavení **webového prohlížeče veřejného terminálu** svou vlastní kategorii v Azure Portal.
Platí pro: Windows 10 a novější

#### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>Výzva k zadání kódu PIN při změně otisků prstů nebo ID obličeje na zařízení s iOS  <!-- 2637704  -->
Uživatelům se nyní zobrazí výzva k zadání kódu PIN po provedení biometrických změn na zařízení s iOS. Patří sem změny registrovaných otisků prstů nebo ID obličeje. Načasování výzvy závisí na tom, jak konfigurace *překontrolují požadavky na přístup po (minuty)* vypršel časový limit.  Pokud není nastaven žádný kód PIN, zobrazí se uživateli výzva k jeho nastavení. 
 
Tato funkce je dostupná jenom pro iOS a vyžaduje zapojení aplikací, které integrují sadu Intune APP SDK pro iOS, verze 9.0.1 nebo novější. Integrace sady SDK je nezbytná, aby bylo možné chování vyhovět cílovým aplikacím. Tato integrace probíhá paušálně a závisí na konkrétních týmech aplikace. Mezi některé aplikace, které jsou součástí, patří WXP, Outlook, Managed Browser a Yammer.

#### <a name="network-access-control-support-on-ios-vpn-clients----1333693---"></a>Podpora řízení přístupu k síti u klientů VPN iOS <!-- 1333693 -->
V této aktualizaci je k dispozici nové nastavení pro povolení síťové Access Control (NAC) při vytváření konfiguračního profilu sítě VPN pro Cisco AnyConnect, F5 Access a Citrix SSO pro iOS. Toto nastavení umožňuje, aby ID NAC zařízení bylo zahrnuté v profilu sítě VPN. V současné době nejsou k dispozici žádné klienty VPN ani NAC Partnerská řešení, která podporují toto nové ID NAC, ale v [příspěvku blogu podpory](ttps://aka.ms/iOS12_and_vpn) vám budeme průběžně informovat.

Pokud chcete používat NAC, budete potřebovat:
1. Výslovný souhlas s povolením, aby Intune zahrnoval ID zařízení v profilech sítě VPN
2. Aktualizujte software nebo firmware poskytovatele NAC pomocí pokynů přímo od vašeho poskytovatele NAC.

Informace o tomto nastavení v profilu sítě VPN iOS najdete v tématu [Přidání nastavení sítě VPN na zařízeních s iOS v Microsoft Intune](../configuration/vpn-settings-ios.md). Další informace o řízení přístupu k síti najdete v tématu [integrace řízení přístupu k síti (NAC) s Intune](../protect/network-access-control-integrate.md). 

Platí pro: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>Odebrat e-mailový profil ze zařízení, i když je k dispozici jenom jeden e-mailový profil <!-- 1818139 -->
Dříve jste nedokázali e-mailový profil ze zařízení odebrat, *Pokud* jde o jediný e-mailový profil. V této aktualizaci se toto chování změní. Nyní můžete odebrat e-mailový profil, i když se jedná o jediný e-mailový profil na zařízení. Podrobnosti najdete v tématu [Přidání nastavení e-mailu do zařízení pomocí Intune](../configuration/email-settings-configure.md) .

#### <a name="powershell-scripts-and-aad----2309469---"></a>PowerShellové skripty a AAD <!-- 2309469 -->
Skripty PowerShellu v Intune můžou být cílené na skupiny zabezpečení zařízení AAD.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nové nastavení "požadovaný typ hesla" pro Android, Android Enterprise<!-- 2649963 -->
Když vytvoříte novou zásadu dodržování předpisů (**Intune** > **dodržování předpisů zařízením** > **zásady** > **vytvořit zásadu** > **Android** nebo **Android Enterprise** pro zabezpečení platformy > System), Výchozí hodnota pro **požadované změny typu hesla** :

Z: výchozí nastavení zařízení: aspoň číslice

Platí pro: Android, Android Enterprise

Pokud se chcete podívat na tato nastavení, přejděte na [Android](../protect/compliance-policy-create-android.md) a [Android Enterprise](../protect/compliance-policy-create-android-for-work.md).

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Použití předsdíleného klíče v profilu Wi-Fi s Windows 10 <!-- 2662938 -->
Pomocí této aktualizace můžete použít předsdílený klíč (PSK) s protokolem zabezpečení WPA/WPA2-Personal k ověření profilu konfigurace Wi-Fi pro Windows 10. Pro zařízení ve Windows 10 říjnu 2018 můžete také zadat konfiguraci nákladů pro monitorovanou síť.

V současné době musíte importovat profil sítě Wi-Fi nebo vytvořit vlastní profil pro použití předsdíleného klíče. [Nastavení Wi-Fi pro Windows 10](../configuration/wi-fi-settings-windows.md) obsahuje seznam aktuálních nastavení. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>Odebrání certifikátů PKCS a SCEP z vašich zařízení <!-- 3218390 -->
V některých scénářích zůstával certifikát PKCS a SCEP na zařízeních, i když odebíráte zásady ze skupiny, odstraňujete nasazení konfigurace nebo dodržování předpisů nebo správce aktualizuje stávající profil SCEP nebo PKCS. Tato aktualizace změní chování. Existují některé scénáře, kdy se ze zařízení odeberou certifikáty PKCS a SCEP, a některé scénáře, kde tyto certifikáty zůstanou v zařízení. V tématu [Odebrání certifikátů SCEP a PKCS v Microsoft Intune](../protect/remove-certificates.md) pro tyto scénáře.

#### <a name="use-gatekeeper-on-macos-devices-for-compliance----2504381---"></a>Použití serveru gatekeeper na zařízeních macOS pro dodržování předpisů <!-- 2504381 -->
Tato aktualizace zahrnuje macOS gatekeeper pro vyhodnocení dodržování předpisů u zařízení. Pro nastavení vlastnosti serveru gatekeeper [přidejte zásadu dodržování předpisů pro zařízení MacOS](../protect/compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Použít profil autopilotu pro zaregistrovaná zařízení s Windows 10, která ještě nejsou zaregistrovaná pro automatický pilotní <!-- 1558983 -->
Profily autopilotu můžete použít pro registrovaná zařízení s Windows 10, která ještě nejsou zaregistrovaná pro automatický pilotní nasazení. V profilu autopilotu klikněte na možnost **převést všechna cílová zařízení na autopilot** a automaticky zaregistrujte zařízení bez automatického pilotního nasazení pomocí služby automatického pilotního nasazení. Povolí zpracování registrace 48 hodin. Když je zařízení odregistrované a resetované, umožní vám ho znovu zřídit modul pro nasazení.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Vytvoření a přiřazení více profilů stránky stavu registrace do skupin Azure AD <!-- 2526564 -->
Nyní můžete [vytvořit a přiřadit](../enrollment/windows-enrollment-status.md) více profilů stránky stavu registrace do Azure Add groups.

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>Migrace z Program registrace zařízení do Apple Business Manageru v Intune <!--2748613-->
Apple Business Manager (ABM) funguje v Intune a vy můžete upgradovat účet z Program registrace zařízení (DEP) na ABM. Proces v Intune je stejný. Pokud chcete upgradovat účet Apple z DEP na ABM, otevřete [https://support.apple.com/HT208817]( https://support.apple.com/HT208817).

#### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Karty stavu výstrah a registrace na stránce Přehled registrace zařízení <!--2748656-->
Výstrahy a selhání registrace se teď zobrazují na samostatných kartách na stránce Přehled registrace zařízení.

#### <a name="enrollment-abandonment-report----1382924---"></a>Sestava opuštění registrace <!-- 1382924 -->
V části **registrace zařízení**@no__t**monitorování**-1 je k dispozici nová sestava, která poskytuje podrobnosti o opuštěné registraci. Další informace najdete v tématu [Sestava opuštění portálu společnosti](../enrollment/enrollment-report-company-portal-abandon.md).

#### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Nové funkce Azure Active Directory podmínek použití <!-- 2870393 -->
Azure Active Directory obsahuje podmínky použití funkcí, které můžete použít místo stávajících podmínek a ujednání Intune. Funkce Azure AD terms of use poskytuje větší flexibilitu, na které se zobrazují informace a kdy je můžete zobrazit, lepší podporu lokalizace, větší kontrolu nad tím, jak se vykreslují výrazy a vylepšily se generování sestav. Funkce Azure AD terms of use vyžaduje Azure Active Directory Premium P1, což je také součástí sady Enterprise Mobility + Security E3. Další informace najdete v článku věnovaném [správě podmínek a ujednání vaší společnosti pro přístup uživatelů](../enrollment/terms-and-conditions-create.md).

#### <a name="android-device-owner-mode-support---3188762--"></a>Podpora režimu vlastníka zařízení s Androidem <!--3188762-->
V případě registrace zařízení se zabezpečením Samsung KNOX teď Intune podporuje registraci zařízení do režimu správy zařízení s Androidem pro správu. Uživatelé v Wi-Fi nebo v mobilních sítích se můžou při prvním zapnutí svých zařízení zaregistrovat jenom na několik málo klepnutí. Další informace najdete v tématu [Automatická registrace zařízení se systémem Android pomocí zápisu mobilních zařízení Samsung společnosti Samsung](../enrollment/android-samsung-knox-mobile-enroll.md).

### <a name="device-management"></a>Správa zařízení
#### <a name="new-settings-for-software-updates------1907869---"></a>Nová nastavení pro aktualizace softwaru   <!-- 1907869 -->  
- Teď můžete nakonfigurovat některá oznámení, která upozorňují koncové uživatele na restarty, které jsou nutné k dokončení instalace nejnovějších aktualizací softwaru.   
- Nyní můžete nakonfigurovat výzvu k restartování pro restartování, ke kterým dochází mimo pracovní dobu, která podporuje BYOD scénáře.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Seskupení zařízení s Windows autopilotem zaregistrovaných podle ID korelace <!-- 2075110 -->
Intune teď podporuje seskupování zařízení s Windows pomocí IDENTIFIKÁTORu korelace, pokud je zaregistrované pomocí [autopilotního projektu pro existující zařízení](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) prostřednictvím Configuration Manager. ID korelace je parametrem konfiguračního souboru autopilotu. Intune automaticky nastaví [atribut zařízení Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) tak, aby enrollmentProfileName na hodnotu "OfflineAutopilotprofile-<correlator ID>". To umožňuje, aby se na základě IDENTIFIKÁTORu korelace pomocí atributu enrollmentprofileName pro offline registraci automatických pilotů mohli vytvořit libovolné dynamické skupiny Azure AD. Další informace najdete v tématu věnovaném [autopilotu Windows pro existující zařízení](../enrollment/enrollment-autopilot.md#windows-autopilot-for-existing-devices).

#### <a name="intune-app-protection-policies----2984657---"></a>Zásady ochrany aplikací Intune <!-- 2984657 -->
Zásady ochrany aplikací Intune umožňují konfigurovat různá nastavení ochrany dat pro aplikace chráněné aplikací Intune, jako je například Microsoft Outlook a Microsoft Word. Změnili jsme vzhled a chování těchto nastavení pro [iOS](../apps/app-protection-policy-settings-ios.md) i [Android](../apps/app-protection-policy-settings-android.md) , aby bylo snazší najít jednotlivá nastavení. Existují tři kategorie nastavení zásad:
- **Přemístění dat** – Tato skupina obsahuje ovládací prvky ochrany před únikem informací (DLP), jako jsou omezení pro vyjmutí, kopírování, vložení a uložení. Tato nastavení určují, jak uživatelé pracují s daty v aplikacích.
- **Požadavky na přístup** – Tato skupina obsahuje možnosti PIN kódu pro aplikaci, které určují, jak koncový uživatel přistupuje k aplikacím v pracovním kontextu.  
- **Podmíněné spuštění** – Tato skupina obsahuje nastavení, jako jsou minimální nastavení operačního systému, jailbreaků a detekce root zařízení a offline období odkladu.  
  
Funkce nastavení se nezmění, ale při práci v toku vytváření zásad bude snazší je najít.

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Omezí aplikace a zablokuje přístup k firemním prostředkům na zařízeních s Androidem. <!-- 2451462  -->  
V části **dodržování předpisů zařízením** > **zásady** > **Vytvoření zásady** > **zabezpečení systému** **Android**@no__t 7 je nové nastavení v oddílu *zabezpečení zařízení* s názvem **omezenými aplikacemi**. Nastavení **omezených aplikací** používá zásady dodržování předpisů k blokování přístupu k prostředkům společnosti, pokud jsou v zařízení nainstalované některé aplikace. Zařízení se považuje za nevyhovující, dokud se aplikace bez omezení neodeberou ze zařízení.
Týká se 
- Android

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps----1727158---"></a>Intune bude podporovat maximální velikost balíčku 8 GB pro obchodní aplikace. <!-- 1727158 -->
Intune zvýšila maximální velikost balíčku na 8 GB pro obchodní aplikace (LOB). Další informace najdete v tématu [Přidání aplikací do Microsoft Intune](../apps/apps-add.md).

#### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Přidat vlastní obrázek značky pro aplikaci Portál společnosti <!-- 1916266 -->
Jako správce Microsoft Intune můžete nahrát vlastní obrázek značky, který se zobrazí jako obrázek pozadí na stránce profilu uživatele v aplikaci pro iOS Portál společnosti. Další informace o konfiguraci aplikace Portál společnosti naleznete v tématu [How to Configure a Microsoft Intune portál společnosti App](../apps/company-portal-app.md).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Intune bude při aktualizaci Office na počítačích koncových uživatelů udržovat lokalizovaný jazyk Office. <!-- 2971030 -->
Když Intune nainstaluje Office na počítače koncového uživatele, koncoví uživatelé automaticky získají stejné jazykové sady jako v předchozím. Instalace Office MSI. Další informace najdete v tématu [přiřazení aplikací Office 365 k zařízením s Windows 10 pomocí Microsoft Intune](../apps/apps-add-office365.md).

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal----3076965---"></a>Nové prostředí podpory Intune na portálu pro správu zařízení Microsoft 365 <!-- 3076965 -->
Zavádíme novou nápovědu a možnosti podpory pro Intune na [portálu pro správu zařízení Microsoft 365]( http://devicemanagement.microsoft.com). Nové prostředí vám umožní popište svůj problém vlastními slovy a získat přehled o řešení problémů a webový obsah pro nápravu. Tato řešení jsou nabízená pomocí algoritmu strojového učení založeného na pravidlech, která se řídí dotazy uživatelů.  

Kromě pokynů specifických pro vydání můžete také použít pracovní postup vytvoření nového případu k otevření případu podpory e-mailem nebo telefonem.  

Pro zákazníky, kteří jsou součástí zavedení, nahrazuje toto nové prostředí nápovědu a podporu pro statickou sadu předem vybraných možností, které jsou založeny na oblasti konzoly nástroje, ve které jste v nástroji, když otevřete nápovědu a podporu.  

*Tato nová pomocná a podpůrná prostředí se navádějí na některé, ale ne všechny klienty a jsou k dispozici na portálu pro správu zařízení. Účastníci tohoto nového prostředí se náhodně vyberou z dostupných tenantů Intune. Do rozšiřování zavedení budou přidány noví klienti.*  

Další informace najdete v tématech [Nápověda a podpora](get-support.md#help-and-support-experience) v tématu Jak získat podporu pro Microsoft Intune.  

#### <a name="powershell-module-for-intune--preview-available----951068---"></a>Modul PowerShell pro Intune – náhled k dispozici <!-- 951068 -->
Nový modul PowerShellu, který poskytuje podporu rozhraní Intune API prostřednictvím Microsoft Graph, je teď k dispozici pro verzi Preview na [GitHubu](https://aka.ms/intunepowershell). Podrobnosti o tom, jak používat tento modul, najdete v souboru READme v tomto umístění.

<!-- ########################## -->
## <a name="september-2018"></a>Září 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="remove-duplication-of-app-protection-status-tiles----3083391---"></a>Odebrat duplicity dlaždic stavu ochrany aplikací <!-- 3083391 -->
**Stav uživatele pro iOS** a **stav uživatele pro dlaždice Androidu** byl přítomen jak na stránce **klientské aplikace – přehled** , tak i na stránce **klientské aplikace – stav ochrany aplikací** . Dlaždice stavu se odebraly ze stránky **klientské aplikace – přehled** , aby nedocházelo k duplicitám. 

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="support-for-more-third-party-certification-authorities-ca----3093107---"></a>Podpora dalších certifikačních autorit (CA) třetích stran <!-- 3093107 -->
Pomocí Simple Certificate Enrollment Protocol (SCEP) teď můžete vydávat nové certifikáty a obnovovat certifikáty na mobilních zařízeních pomocí Windows, iOS, Androidu a macOS.

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="intune-moves-to-support-ios-10-and-later----2454656---"></a>Intune se přesune na podporu iOS 10 a novější. <!-- 2454656 -->  
Registrace v Intune, Portál společnosti a spravovaný prohlížeč teď podporují jenom zařízení s iOS se systémem iOS 10 nebo novějším. Pokud chcete vyhledat zařízení nebo uživatele, které jsou v organizaci ovlivněné, přečtěte si v Intune v části Azure Portal > **zařízení** > **všechna zařízení**. Filtrujte podle OS a potom klikněte na **sloupce** . Podrobnosti o verzi operačního systému Surface. Požádejte tyto uživatele o upgrade svých zařízení na podporovanou verzi operačního systému.  

Pokud máte některá z níže uvedených zařízení nebo chcete zaregistrovat kterékoli ze zařízení uvedených níže, uvědomte si, že podporují jenom iOS 9 a starší.  Chcete-li pokračovat v přístupu k Portál společnosti Intune, je nutné upgradovat tato zařízení na zařízení, která podporují iOS 10 nebo novější:  

* iPhone 4S 
* iPod Touch  
* iPad 2 
* iPad (třetí generace) 
* iPad Mini (1. generace)  

### <a name="device-management"></a>Správa zařízení

#### <a name="microsoft-365-device-management-administration-center----3078424---"></a>Centrum pro správu správy zařízení Microsoft 365 <!-- 3078424 -->
Jednou z příslibů Microsoft 365 je zjednodušená správa a za rok jsme Microsoft 365 služby back-endu integrovaly do back-endové služby, které poskytují ucelené scénáře, jako je Intune a podmíněný přístup Azure AD. Nové [Centrum pro správu Microsoft 365](http://devicemanagement.microsoft.com) je místo pro konsolidaci, zjednodušení a integraci prostředí pro správu. Specializovaný pracovní prostor pro správu zařízení poskytuje snadný přístup ke všem informacím o správě zařízení a aplikací a k úlohám, které vaše organizace potřebuje. Očekáváme, že se to stane primárním pracovním prostorem cloudu pro výpočetní týmy podnikového koncového uživatele.


<!-- ########################## -->
## <a name="august-2018"></a>Srpen 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Podpora tunelového připojení paketů pro profily sítě VPN pro iOS pro vlastní typy a typy připojení Pulse Secure <!-- 1520957 -->
Při používání profilů sítě VPN pro iOS pro aplikace můžete zvolit použití tunelového připojení (App-proxy) aplikační vrstvy nebo tunelového propojení na úrovni paketů (pakety-Tunnel). Tyto možnosti jsou k dispozici s následujícími typy připojení:
- Vlastní síť VPN
- Pulse Secure Pokud si nejste jistí, která hodnota se má použít, Projděte si dokumentaci poskytovatele sítě VPN.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Zpoždění při zobrazení aktualizací softwaru iOS na zařízení <!-- 1949583 -->
V Intune > **aktualizace softwaru** > **zásady aktualizace pro iOS**můžete nakonfigurovat dny a časy, kdy nechcete, aby zařízení instalovala aktualizace. V budoucí aktualizaci se budete moci zpozdit, že se na zařízení zobrazuje aktualizace softwaru, a to po dobu 1-90 dnů. 
[Konfigurace zásad aktualizace pro iOS v Microsoft Intune](../protect/software-updates-ios.md) uvádí aktuální nastavení.

#### <a name="office-365-proplus-version----2213968---"></a>Verze sady Office 365 plus <!-- 2213968 -->
Při přiřazování aplikací Office 365 ProPlus do zařízení s Windows 10 pomocí Intune budete moct vybrat verzi Office. V Azure Portal vyberte **Microsoft Intune** **aplikace** >   > **Přidat aplikaci**. Pak v rozevíracím seznamu **typ** vyberte sadu **Office 365 ProPlus Suite (Windows 10)** . Vyberte **nastavení sady aplikací** , aby se zobrazilo přidružené okno. Nastavte **kanál aktualizace** na hodnotu, například **měsíčně**. Volitelně můžete odebrat jinou verzi Office (MSI) ze zařízení koncových uživatelů tak, že vyberete **Ano**. Vyberte možnost **specifické** pro instalaci konkrétní verze Office pro vybraný kanál na zařízeních koncových uživatelů. V tomto okamžiku můžete vybrat **konkrétní verzi** Office, která se má použít. Dostupné verze se v průběhu času mění. Proto při vytváření nového nasazení mohou být dostupné verze novější a nemají k dispozici některé starší verze. Aktuální nasazení budou pokračovat v nasazení starší verze, ale seznam verzí bude průběžně aktualizován na kanál. Další informace najdete v tématu [Přehled kanálů aktualizací pro Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Podpora pro registraci nastavení DNS pro síť VPN s Windows 10 <!-- 2282852 -->
Pomocí této aktualizace můžete nakonfigurovat profily sítě VPN s Windows 10 tak, aby dynamicky registrovaly IP adresy přiřazené k rozhraní VPN pomocí interního serveru DNS, aniž byste museli používat vlastní profily.
Informace o dostupných nastaveních profilu sítě VPN najdete v tématu [nastavení sítě VPN pro Windows 10](../configuration/vpn-settings-windows-10.md).

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name---2652728--"></a>Instalační služba macOS Portál společnosti nyní zahrnuje číslo verze v názvu souboru instalačního programu. <!--2652728-->

#### <a name="ios-automatic-app-updates----2729759---"></a>Automatické aktualizace aplikací pro iOS <!-- 2729759 -->
Automatické aktualizace aplikací fungují pro aplikace i uživatele licencované pro iOS verze 11,0 a vyšší.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Windows Hello bude cílit na uživatele a zařízení <!-- 1106609 -->
Když vytvoříte zásady [Windows Hello pro firmy](../protect/windows-hello.md) , platí to pro všechny uživatele v organizaci (v celém tenantovi). V této aktualizaci se zásady dají použít taky pro konkrétní uživatele nebo konkrétní zařízení pomocí zásad konfigurace zařízení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Identity Protection**@no __t-7**Windows Hello pro firmy**).
V Intune v Azure Portal existuje konfigurace a nastavení Windows Hello v **registraci zařízení** i v **konfiguraci zařízení**. **Registrace zařízení** cílí na celou organizaci (v celém tenantovi) a podporují Windows autopilot (OOBE). **Konfigurace zařízení** cílí na zařízení a uživatele pomocí zásad, které jste použili při vracení se změnami.
Tato funkce se týká:  
- Windows 10 a novější
- Windows Holografick pro firmy

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858---"></a>Zscaler je dostupné připojení pro profily sítě VPN v iOS. <!-- 1769858 -->
Když vytvoříte konfigurační profil zařízení VPN iOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** >  platforma**iOS** > typ profilu **VPN** ), je k dispozici několik typů připojení. včetně Cisco, Citrix a dalších. Tato aktualizace přidá Zscaler jako typ připojení. 
[Nastavení sítě VPN pro zařízení se systémem iOS](../configuration/vpn-settings-ios.md) vypisuje dostupné typy připojení.

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10----1879077---"></a>Režim FIPS pro profily firemní sítě Wi-Fi pro Windows 10 <!-- 1879077 -->
V Azure Portal Intune teď můžete povolit režim FIPS (Federal Information Processing Standards) pro profily sítě Wi-Fi pro Windows 10. Pokud ho povolíte v profilech sítě Wi-Fi, ujistěte se, že je povolený režim FIPS v infrastruktuře Wi-Fi.
[Nastavení Wi-Fi pro zařízení s Windows 10 a novějším v Intune](../configuration/wi-fi-settings-windows.md) vám ukáže, jak vytvořit profil sítě Wi-Fi.

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Řízení S režimem v zařízeních s Windows 10 a novějších verzích – Public Preview <!-- 1958649 -->
Pomocí této aktualizace funkcí můžete vytvořit konfigurační profil zařízení, který přepne zařízení S Windows 10 z režimu S nebo brání uživatelům v přepínání zařízení z režimu S. Tato funkce je v Intune > **konfiguracích zařízení** > **profily** >  **Windows 10 a novějších** **přepínačích pro upgrade a režim** > .
[Představujeme Windows 10 v režimu s](https://www.microsoft.com/windows/s-mode) nabízí další informace o režimu s.
Platí pro: poslední Build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (ve verzi Preview).

#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Konfigurační balíček ochrany ATP v programu Windows Defender se automaticky přidal do konfiguračního profilu. <!-- 2144658 -->
Při použití [rozšířené ochrany před internetovými útoky a připojování](../protect/advanced-threat-protection.md#onboard-devices-by-using-a-configuration-profile) zařízení v Intune jste předtím museli stáhnout konfigurační balíček a přidat ho do konfiguračního profilu. V rámci této aktualizace Intune automaticky načte balíček z Windows Defender Security Center a přidá ho do vašeho profilu.
Platí pro Windows 10 a novější.

#### <a name="require-users-to-connect-during-device-setup---2311457--"></a>Vyžadovat, aby se uživatelé připojili během instalace zařízení <!--2311457-->
Teď můžete nastavit profily zařízení tak, aby vyžadovaly, aby se zařízení připojilo k síti předtím, než se během instalace Windows 10 dokročí stránka síť. I když je tato funkce ve verzi Preview, je k použití tohoto nastavení nutná verze Windows Insider Build 1809 nebo novější.
Platí pro: poslední Build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (ve verzi Preview).

#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices----2451462---"></a>Omezí aplikace a zablokuje přístup k firemním prostředkům na zařízeních se systémy iOS a Android Enterprise. <!-- 2451462 -->
V **dodržování předpisů zařízením** > **zásady** > **vytvořit zásadu** > **zabezpečení systému** **iOS** >  je k dispozici nové nastavení **s omezenými aplikacemi** . Toto nové nastavení používá zásady dodržování předpisů k blokování přístupu k prostředkům společnosti, pokud jsou v zařízení nainstalované některé aplikace. Zařízení se považuje za nevyhovující, dokud se aplikace bez omezení neodeberou ze zařízení.
Platí pro: iOS

#### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Aktualizace moderní sítě VPN pro iOS <!-- 2459928, 1819876, and 2650856 -->
Tato aktualizace přidává podporu následujících klientů VPN iOS:
- Přístup přes F5 (verze 3.0.1 a vyšší)
- Citrix SSO
- Palo Alto Networks GlobalProtect verze 5,0 a vyšší také v této aktualizaci:
- Existující typ **přístupového připojení F5** se přejmenuje na **F5 Access Legacy** pro iOS.
- Stávající **Palo Alto Networks GlobalProtect** typ připojení se přejmenují na **Palo Alto Networks GlobalProtect (starší verze)** pro iOS.
Stávající profily s těmito typy připojení budou dál fungovat s příslušným starším klientem VPN. Pokud používáte Cisco Legacy AnyConnect, F5 Access Legacy, Citrix VPN nebo Palo Alto Networks GlobalProtect verze 4,1 a starší s iOS, měli byste přejít na nové aplikace. Co nejdříve to uděláte, abyste zajistili dostupnost přístupu k síti VPN pro zařízení s iOS při aktualizaci na iOS 12.
Další informace o profilech iOS 12 a VPN najdete na [blogu týmu podpory pro Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2013806).

#### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal----2469637---"></a>Exportujte zásady dodržování předpisů portálu Azure Classic, abyste tyto zásady znovu vytvořili v Intune Azure Portal <!-- 2469637 -->
Zásady dodržování předpisů vytvořené na portálu Azure Classic budou zastaralé. Můžete zkontrolovat a odstranit všechny existující zásady dodržování předpisů, ale nemůžete je aktualizovat. Pokud potřebujete migrovat zásady dodržování předpisů na aktuální Azure Portal Intune, můžete tyto zásady exportovat jako textový soubor s oddělovači (soubor *. csv* ). Pak pomocí podrobností v souboru tyto zásady znovu vytvořte v Azure Portal Intune.

> [!IMPORTANT]
> Když dojde k vynechání portálu Azure Classic, nebudete už mít přístup k zásadám dodržování předpisů ani k jejich zobrazení. Proto nezapomeňte tyto zásady vyexportovat a znovu je vytvořit v Azure Portal před odstraněním portálu Azure Classic.

#### <a name="better-mobile---new-mobile-threat-defense-partner----22662717---"></a>Lepší partner ochrany před mobilními hrozbami Mobile – nový <!-- 22662717 -->
Přístup mobilních zařízení k podnikovým prostředkům můžete řídit pomocí podmíněného přístupu na základě posouzení rizik, které provádí lépe mobilní, řešení ochrany před mobilními hrozbami, které se integruje s Microsoft Intune.

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Uzamknout portál společnosti v režimu jedné aplikace, dokud se uživatel přihlašuje <!--1067692 --> 
Teď máte možnost spustit Portál společnosti v režimu jedné aplikace, pokud během registrace DEP ověříte uživatele pomocí Portál společnosti namísto pomocníka s nastavením. Tato možnost zamkne zařízení hned po dokončení Průvodce nastavením, aby se uživatel musel k zařízení přihlašovat. Tento proces zajistí, že zařízení dokončí registraci, a není osamocené ve stavu bez zásahu uživatele.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Přiřazení uživatele a popisného názvu k zařízení autopilotu <!--1346521 -->
Nyní můžete [přiřadit uživatele k jednomu zařízení autopilotu](../enrollment/enrollment-autopilot.md). Správci budou moct při nastavování zařízení pomocí autopilotu uživatelům poskytnout popisné názvy.
Platí pro: poslední Build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (ve verzi Preview).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>Pomocí licencí zařízení VPP předem zajistěte Portál společnosti během registrace DEP. <!-- 1608345 -->
Nyní můžete použít licence zařízení VPP (Volume purchase program) k předběžnému poskytování Portál společnosti při registraci Program registrace zařízení (DEP). Pokud to chcete udělat, můžete při [vytváření nebo úpravách registračního profilu](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile)zadat token VPP, který chcete použít k instalaci portál společnosti. Ujistěte se, že platnost tokenu nevyprší a že máte k dispozici dostatek licencí pro aplikaci Portál společnosti. V případech, kdy vyprší platnost tokenu nebo se vyčerpá licence, Intune místo toho odešle App Storu Portál společnosti (zobrazí se výzva k zadání Apple ID).

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>K odstranění tokenu VPP, který se používá pro Portál společnosti předběžné zřizování, se vyžaduje potvrzení. <!-- 2237634 -->
K odstranění tokenu programu Volume purchase program (VPP), který se používá k předběžnému zřízení Portál společnosti během registrace DEP, se teď vyžaduje potvrzení.

#### <a name="block-windows-personal-device-enrollments----1849498---"></a>Blokovat registraci osobních zařízení Windows <!-- 1849498 -->
Pomocí [správy mobilních zařízení](../enrollment/windows-enroll.md) v Intune můžete [zablokovat osobní zařízení Windows](../enrollment/enrollment-restrictions-set.md) . U zařízení zaregistrovaných v [agentovi Intune PC agent](../manage-windows-pcs-with-microsoft-intune.md) nejde tuto funkci zablokovat. Tato funkce se zavede na další pár týdnů, takže je možné, že ji v uživatelském rozhraní neuvidíte hned.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Určení vzorů názvu počítače v profilu autopilotu <!--1849855-->
Můžete [určit šablonu názvu počítače](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) , která se má vygenerovat a nastavit [název počítače](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) při registraci automatického pilotního nasazení. Platí pro: poslední Build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (ve verzi Preview).

#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>Pro profily Windows autopilotu skryjte možnosti změnit účet na přihlašovací stránce společnosti a na chybové stránce domény. <!--1901669 -->
K dispozici jsou [nové možnosti profilu Windows autopilot](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) pro správce, které skryjí možnosti změny účtu na přihlašovacích stránkách společnosti a na chybových stránkách domény. Skrytím těchto možností se vyžaduje, aby se v Azure Active Directory nakonfigurovala firemní značka. Platí pro: poslední Build [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (ve verzi Preview).

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>Podpora macOS pro Apple Program registrace zařízení <!-- 747651 -->
Intune teď podporuje registraci zařízení macOS do Apple Program registrace zařízení (DEP). Další informace najdete v tématu [Automatická registrace zařízení MacOS pomocí program registrace zařízení společnosti Apple](../enrollment/device-enrollment-program-enroll-macos.md).

### <a name="device-management"></a>Správa zařízení

#### <a name="delete-jamf-devices----2653306--"></a>Odstranit zařízení Jamf <!-- 2653306-->
Zařízení spravovaná JAMF můžete odstranit tak, že na **zařízení** převedete > vyberte zařízení JAMF > **Odstranit**.

#### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Změna terminologie na vyřazení a vymazání <!-- 2175759 -->
Aby byla v souladu s Graph API, uživatelské rozhraní a dokumentace Intune změnily následující výrazy:
- **Odebrání firemních dat** se změní na vyřadit z provozu.
- **Obnovení továrního nastavení** se změní na **vymazání** .

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate----297909500--"></a>Potvrzovací dialog, pokud se správce pokusí odstranit MDM Push Certificate <!-- 297909500-->
Pokud se někdo pokusí odstranit certifikát Apple MDM push Certificate, dialogové okno pro potvrzení zobrazuje počet souvisejících zařízení s iOS a macOS. Pokud se certifikát odstraní, bude nutné tato zařízení znovu zaregistrovat.

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Další nastavení zabezpečení pro instalační službu systému Windows <!-- 2282430 -->
Uživatelům můžete dovolit řídit instalaci aplikací. Pokud je povoleno, instalace, které mohou být jinak zastaveny z důvodu narušení zabezpečení, by mohly pokračovat. Instalační službu systému Windows můžete nasměrovat tak, aby při instalaci jakéhokoli programu do systému používala zvýšená oprávnění. Kromě toho můžete povolit indexování položek Windows Information Protection (nedokončené výroby) a metadata o nich uložená v nešifrovaném umístění. Pokud je zásada zakázaná, položky chráněné nedokončené výroby nebudou indexovány a ve výsledcích v Cortana nebo Průzkumníkovi souborů se nezobrazují. Funkce pro tyto možnosti jsou ve výchozím nastavení zakázané. 

#### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nová aktualizace uživatelského prostředí pro Portál společnosti web <!--2000968 -->
Do Portál společnosti webu jsme přidali nové funkce založené na zpětné vazbě od zákazníků. Budete mít významné vylepšení stávajících funkcí a použitelnosti vašich zařízení. Oblasti webu @ no__t-0such jako podrobnosti o zařízení, zpětná vazba a podpora a Přehled zařízení @ no__t-1have obdržel nový, moderní a reagující návrh. Uvidíte také tyto informace:

- Zjednodušené pracovní postupy napříč všemi platformami zařízení
- Vylepšené identifikace zařízení a toky registrace
- Užitečnější chybové zprávy
- Příjemnější jazyk, méně tech žargonu
- Možnost sdílet přímé odkazy na aplikace
- Vylepšený výkon pro velké katalogy aplikací
- Zvýšení dostupnosti pro všechny uživatele  

[Dokumentace k Portál společnosti Intune webu](https://docs.microsoft.com/intune-user-help/using-the-intune-company-portal-website) se aktualizovala tak, aby odrážela tyto změny. Příklad vylepšení aplikace najdete v tématu [aktualizace uživatelského rozhraní pro aplikace Intune pro koncové uživatele](../whats-new-app-ui.md).  

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Vylepšené zjišťování jailbreaků v hlášení dodržování předpisů<!-- 2198738 -->
V konzole pro správu se teď v nástroji pro vytváření sestav dodržování předpisů zobrazuje stav rozšířené detekce jailbreaků.

### <a name="role-based-access-control"></a>Řízení přístupu založené na rolích

#### <a name="scope-tags-for-policies---1081974---"></a>Značky oboru pro zásady <!--1081974 -->
Můžete [vytvořit značky oboru](scope-tags.md) , které omezují přístup k prostředkům Intune. Přidejte značku oboru k přiřazení role a pak přidejte značku oboru do konfiguračního profilu. Role bude mít přístup pouze k prostředkům s konfiguračními profily, které mají odpovídající značky oboru (nebo žádné značky oboru).





<!-- ########################## -->
## <a name="july-2018"></a>Červenec 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>Obchodní podpora (LOB) pro macOS <!-- 1895847 -->
Microsoft Intune umožňuje nasazení obchodních aplikací v macOS podle **potřeby** nebo **k dispozici pro registraci**. Koncoví uživatelé mohou získat aplikace nasazené jako **dostupné** pomocí portál společnosti pro macOS nebo [portál společnosti webu](https://portal.manage.microsoft.com).

#### <a name="ios-built-in-app-support-for-kiosk-mode----2051098---"></a>Podpora integrované aplikace iOS pro celoobrazovkový režim <!-- 2051098 -->
Kromě aplikací pro Store a spravovaných aplikací teď můžete vybrat integrovanou aplikaci (například Safari), která běží v celoobrazovkovém režimu na zařízení s iOS.

#### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Úprava nasazení aplikace sady Office 365 pro plus <!-- 2150145 -->
Jako správce Microsoft Intune máte větší možnost upravovat nasazení aplikací pro Office 365 pro plus. Navíc už nemusíte odstraňovat nasazení, aby se změnily jakékoli vlastnosti sady. V Azure Portal vyberte **Microsoft Intune** **aplikace** > **klienta**aplikace  > . V seznamu aplikací vyberte sadu Office 365 pro plus.  

#### <a name="updated-intune-app-sdk-for-android-is-now-available----2744271--"></a>Aktualizovaná sada Intune App SDK pro Android je teď dostupná <!-- 2744271-->
K dispozici je aktualizovaná verze sady Intune App SDK pro Android, která podporuje verzi pro Android P. Pokud jste vývojář aplikací a používáte Intune SDK pro Android, musíte nainstalovat aktualizovanou verzi sady Intune App SDK, abyste zajistili, že funkce Intune v aplikacích pro Android budou dál fungovat podle očekávání na zařízeních s Androidem P. Tato verze sady Intune App SDK poskytuje integrovaný modul plug-in, který provádí aktualizace sady SDK. Nemusíte přepisovat veškerý stávající kód, který je integrovaný. Podrobnosti najdete v tématu [Intune SDK pro Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). Pokud používáte starý styl označení pro Intune, doporučujeme použít ikonu Aktovky. Podrobnosti o brandingu najdete v [tomto úložišti GitHubu](https://github.com/msintuneappsdk/intune-app-partner-badge).

#### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Další příležitosti synchronizace v aplikaci Portál společnosti pro Windows  
Aplikace Portál společnosti pro Windows teď umožňuje zahájit synchronizaci přímo z hlavního panelu Windows a nabídky Start. Tato funkce je užitečná hlavně v případě, že je jediným úkolem synchronizace zařízení a přístup k podnikovým prostředkům. Chcete-li získat přístup k nové funkci, klikněte pravým tlačítkem myši na ikonu portálu společnosti, která je připnuté na hlavní panel nebo nabídku Start. V nabídce Možnosti nabídky (také označované jako seznam odkazů) vyberte **Synchronizovat toto zařízení**. Portál společnosti se otevře na stránce **Nastavení** a zahájí synchronizaci. Pokud se chcete podívat na nové funkce, podívejte se, [co je nového v uživatelském rozhraní](../whats-new-app-ui.md).   

#### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Nové prostředí pro procházení v aplikaci Portál společnosti pro Windows  
Když teď v aplikaci Portál společnosti pro Windows procházíte nebo hledáte aplikace, můžete přepínat mezi existujícím zobrazením **dlaždic** a nově přidaným zobrazením **podrobností** . Nové zobrazení obsahuje seznam podrobností o aplikaci, jako je název, vydavatel, datum publikování a stav instalace.  

Zobrazení **nainstalované** stránky **aplikací** vám umožní zobrazit podrobnosti o dokončených a probíhajících instalacích aplikací. Chcete-li zjistit, jak vypadá nové zobrazení, přečtěte si téma [co je nového v uživatelském rozhraní](../whats-new-app-ui.md).  

#### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Vylepšené prostředí pro Portál společnosti aplikací pro správce registrace zařízení  
Když se správce registrace zařízení (DEM) přihlásí do aplikace Portál společnosti pro Windows, bude teď aplikace zobrazovat jenom aktuální, běžící zařízení DEM. Toto vylepšení snižuje časový limit, který dříve nastal, když se aplikace pokusila Zobrazit všechna zařízení zaregistrovaná v DEM.  

#### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Blokovat přístup k aplikaci na základě neschválených dodavatelů a modelů zařízení  <!-- 1425689 ! -->
Správce IT v Intune může vymáhat konkrétní seznam výrobců pro Android nebo modely iOS prostřednictvím zásad Intune App Protection. Správce IT může poskytnout seznam výrobců s odděleným středníkem pro zásady Androidu a modely zařízení pro zásady iOS. Zásady Intune App Protection jsou jenom pro Android a iOS. K dispozici jsou dvě samostatné akce, které je možné provést v zadaném seznamu:
- Blok z přístupu aplikace na zařízeních, která nejsou zadaná.
- Nebo selektivní vymazání podnikových dat na zařízeních, která nejsou zadaná. 

Uživatel nebude mít přístup k cílové aplikaci, pokud nejsou splněny požadavky prostřednictvím zásad. Na základě nastavení může být uživatel buď zablokován, nebo selektivně vymazat jejich firemní data v rámci aplikace. V zařízeních se systémem iOS Tato funkce vyžaduje zapojení aplikací (například WXP, Outlook, Managed Browser, Yammer) a integraci sady Intune APP SDK, aby se tato funkce vynutila cílovými aplikacemi. Tato integrace probíhá paušálně a závisí na konkrétních týmech aplikace. V Androidu Tato funkce vyžaduje nejnovější Portál společnosti. 

Na zařízeních koncových uživatelů provede klient Intune akci na základě jednoduchého porovnání řetězců uvedených v okně Intune pro zásady ochrany aplikací. To závisí výhradně na hodnotě, kterou zařízení hlásí. V takovém případě je doporučován správce IT, aby zajistil, že zamýšlené chování je přesné. To lze provést otestováním tohoto nastavení na základě různých výrobců zařízení a modelů, které jsou cílem malé skupiny uživatelů. V Microsoft Intune vyberte **klientské aplikace** > **Zásady ochrany aplikací** , abyste mohli zobrazit a přidat zásady ochrany aplikací. Další informace o zásadách ochrany aplikací najdete v tématu [co jsou zásady ochrany aplikací](../apps/app-protection-policy.md) a [selektivní vymazání dat pomocí akcí přístupu k zásadám ochrany aplikací v Intune](../apps/app-protection-policies-access-actions.md).

#### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>Přístup k macOS Portál společnosti předběžného vydání buildu <!-- 1734766 -->
Pomocí Microsoft AutoUpdate se můžete zaregistrovat k předčasnému získání buildů tím, že se připojíte k programu Insider. Registrace vám umožní používat aktualizované Portál společnosti před tím, než bude dostupný koncovým uživatelům. Další informace najdete na [blogu Microsoft Intune](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Vytvoření zásad dodržování předpisů pro zařízení pomocí nastavení brány firewall na zařízeních macOS <!-- 1497640 -->
Když vytváříte nové zásady dodržování předpisů pro macOS (**dodržování předpisů zařízením**@no__t **-1,**  > **vytvořit zásadu** > **platforma: MacOS**@no__t 7.**zabezpečení systému**), je k dispozici několik nových nastavení **brány firewall** . k dispozici 

- **Brána firewall**: Nakonfigurujte, jak se budou zpracovávat příchozí připojení ve vašem prostředí.
- **Příchozí připojení**: **blokovat** všechna příchozí připojení s výjimkou těch, která jsou nutná pro základní internetové služby, jako jsou DHCP, Bonjour a IPSec. Toto nastavení také blokuje všechny služby sdílení.
- **Režim utajení**: Pokud chcete zabránit tomu, aby zařízení reagovalo na požadavky na zjišťování, **Povolte** režim neviditelného režimu. Zařízení bude nadále odpovídat na příchozí požadavky na autorizované aplikace.

Platí pro: macOS 10,12 a novější

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Nový profil konfigurace zařízení Wi-Fi pro Windows 10 a novější <!-- 1879077 -->
V současné době můžete importovat a exportovat profily sítě Wi-Fi pomocí souborů XML. Pomocí této aktualizace můžete vytvořit profil konfigurace zařízení Wi-Fi přímo v Intune, stejně jako některé jiné platformy.

Profil vytvoříte tak, že otevřete **Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novějších** > **Wi-Fi**. 

Platí pro Windows 10 a novější.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>Veřejný terminál – zastaralý je šedý a nedá se změnit. <!-- 2149998 -->
Funkce veřejného terminálu (Preview) (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novějších** **omezení zařízení**@no__t 7) je zastaralá a nahrazuje se [nastavením veřejného terminálu pro Windows 10 a novější](../configuration/kiosk-settings.md). V této aktualizaci je funkce **zastaralá na terminálu** šedá a uživatelské rozhraní se nedá změnit ani aktualizovat. 

Pokud chcete povolit celoobrazovkový režim, přečtěte si téma [Nastavení veřejného terminálu pro Windows 10 a novější](../configuration/kiosk-settings.md).

Platí pro Windows 10 a novější, Windows Holografick pro firmy.

#### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>Rozhraní API pro používání certifikačních autorit třetích stran <!-- 2184013 -->
V této aktualizaci existuje rozhraní Java API, které umožňuje integraci certifikačních autorit třetích stran s Intune a SCEP. Pak uživatelé můžou certifikát SCEP přidat do profilu a použít ho na zařízení s použitím MDM.

V současné době podporuje Intune [požadavky SCEP pomocí služby AD CS (Active Directory Certificate Services](../protect/certificates-scep-configure.md)).

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>Přepnutím zobrazíte nebo nezobrazete tlačítko ukončit relaci v prohlížeči veřejného terminálu. <!-- 2455253 -->
Teď můžete nakonfigurovat, jestli se mají v prohlížečích veřejného terminálu zobrazovat tlačítka ukončit relaci. Ovládací prvek můžete zobrazit v části **Konfigurace zařízení**@no__t **-1 veřejný** **webový prohlížeč** > . Pokud je tato možnost zapnutá a uživatel klikne na tlačítko, aplikace vyzve k potvrzení ukončení relace. V případě potvrzení prohlížeč vymaže všechna data procházení a přejde zpátky na výchozí adresu URL.

#### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>Vytvoření profilu konfigurace mobilní sítě pro eSIM kartu <!-- 2564077 -->
V **konfiguraci zařízení**můžete vytvořit mobilní profil eSIM. Můžete importovat soubor, který obsahuje mobilní aktivační kódy poskytované mobilním operátorem. Pak můžete tyto profily nasadit na zařízení s Windows 10 s povolenou eSIM LTE, jako je například Surface LTE a jiná zařízení s podporou eSIM karty.

Zkontrolujte, jestli vaše [zařízení podporuje profily eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Platí pro Windows 10 a novější.

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>Výběr kategorií zařízení pomocí nastavení přístup do práce nebo do školy <!-- 1058963 eenotready --> 
Pokud jste povolili [mapování skupin zařízení](../enrollment/device-group-mapping.md), uživatelům ve Windows 10 se teď po registraci přes tlačítko **připojit** zobrazí v **nastavení** > **účty** > **přístup do práce nebo do školy**. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Jako uživatelské jméno účtu pro e-mailové profily použijte sAMAccountName. <!-- 1500307 -->
U e-mailových profilů pro Android, iOS a Windows 10 můžete použít místní uživatelské jméno účtu **sAMAccountName** . Doménu můžete taky získat z atributu `domain` nebo `ntdomain` v Azure Active Directory (Azure AD). Nebo zadejte vlastní statickou doménu.

Pokud chcete používat tuto funkci, musíte synchronizovat atribut `sAMAccountName` z místního prostředí Active Directory do Azure AD.

Platí pro [Android](../configuration/email-settings-android.md), [iOS](../configuration/email-settings-ios.md), [Windows 10 a novější](../configuration/email-settings-windows-10.md) .

#### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Zobrazit konfliktní profily konfigurace zařízení <!-- 1556983 -->
V části **Konfigurace zařízení**se zobrazí seznam existujících profilů. V této aktualizaci se přidá nový sloupec, který obsahuje podrobnosti o profilech, u kterých došlo ke konfliktu. Můžete vybrat konfliktní řádek a zobrazit nastavení a profil, který má konflikt. 

Další informace o [správě konfiguračních profilů](../configuration/device-profile-monitor.md#view-conflicts).

#### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Nový stav pro zařízení v dodržování předpisů zařízením <!-- 2308882 -->
V části**zásady** **dodržování předpisů zařízení** >  > vyberte zásadu > **Přehled**. přidají se tyto nové stavy:
- Úspěchu
- error
- Došlo
- Uložené
- Zobrazuje se také obrázek, který zobrazuje počet zařízení jiné platformy. Pokud například hledáte profil pro iOS, na nové dlaždici se zobrazuje počet zařízení bez iOS, která jsou také přiřazena k tomuto profilu. Podívejte se na téma [zásady dodržování předpisů pro zařízení](../protect/compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Dodržování předpisů zařízením podporuje antivirová řešení třetích stran. <!-- 2325484 -->
Při vytváření zásad dodržování předpisů pro zařízení (**zásady**dodržování předpisů pro**zařízení** >   > **vytvořit zásadu** > :**Nastavení** **Windows 10 a novějších** >   > **System Security**) jsou nové možnosti **[zabezpečení zařízení](../protect/compliance-policy-create-windows.md)** : 
- **Antivirová ochrana**: Pokud nastavíte možnost **vyžadovat**, můžete ověřit dodržování předpisů pomocí antivirových řešení, která jsou zaregistrovaná v systému Windows Security Center, například Symantec a Windows Defender. 
- **Antispywarový**program: Pokud nastavíte možnost **vyžadovat**, můžete ověřit dodržování předpisů pomocí antispywarových řešení, která jsou zaregistrovaná ve Windows Security Center, jako je například Symantec a Windows Defender. 

Platí pro: Windows 10 a novější 

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Automaticky označí zařízení s Androidem zaregistrovaná pomocí registrace Samsung KNOX Mobile jako "Corporate". <!-- 2404851 -->
Ve výchozím nastavení se zařízení s Androidem zaregistrovaná pomocí zápisu na mobilní zařízení Samsung KNOX teď v části **vlastnictví zařízení**označí jako **firemní** . Před registrací pomocí registrace pro Knox nemusíte ručně identifikovat firemní zařízení pomocí IMEI nebo sériových čísel.

#### <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens----1853904---"></a>Sloupec zařízení bez profilů v seznamu tokenů programu registrace <!-- 1853904 -->
V seznamu tokeny programu registrace je k dispozici nový sloupec se zobrazeným počtem zařízení bez přiřazeného profilu. To správcům pomáhá přiřadit profily k těmto zařízením před jejich předáním uživatelům. Nový sloupec zobrazíte tak, že přejdete na **registrace zařízení** >  registrace**Apple** > **tokeny programu registrace**.

### <a name="device-management"></a>Správa zařízení

#### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Okno hromadného odstranění zařízení v zařízeních <!-- 1793693 -->
Nyní můžete v okně zařízení odstranit více zařízení najednou. Zvolte **zařízení** > **všechna zařízení** > vyberte zařízení, která chcete odstranit > **Odstranit**. U zařízení, která se nedají odstranit, se zobrazí výstraha.

#### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Změny názvu Google pro Android for Work a Play for Work <!--842873 -->
Intune aktualizoval terminologii Android for Work, aby odrážela změny brandingu Google. Výrazy "Android for Work" a "Play for Work" již nebudou použity. V závislosti na kontextu se používá odlišná terminologie:
- "Android Enterprise" odkazuje na celkovou moderní sadu pro správu Androidu.
- "Pracovní profil" nebo "vlastník profilu" odkazuje na zařízení BYOD spravovaná pomocí pracovních profilů.
- "Spravovaný Google Play" odkazuje na Google App Store.

#### <a name="rules-for-removing-devices----1609459---"></a>Pravidla pro odebrání zařízení <!-- 1609459 -->
K dispozici jsou nová pravidla, která umožňují automaticky odebrat zařízení, která se nevrátila po dobu určitého počtu dnů. Pokud chcete nové pravidlo zobrazit, přejděte do podokna **Intune** , vyberte **zařízení**a vyberte pravidla pro **Vyčištění zařízení**.

#### <a name="corporate-owned-single-use-support-for-android-devices----1630973---"></a>Podpora pro zařízení s Androidem ve vlastnictví firmy <!-- 1630973 -->

Intune teď podporuje vysoce spravovaná a zamčená zařízení s Androidem ve stylu veřejného terminálu. To správcům umožňuje dále uzamknout používání zařízení do jedné nebo malé sady aplikací a zabránit uživatelům v povolení jiných aplikací nebo provádění dalších akcí na zařízení. Pokud chcete nastavit webtelefon s Androidem, přečtěte si v Intune > **registrace zařízení** > **registrace Androidu** >  veřejného**terminálu a registrace zařízení úloh**. Další informace najdete v tématu [Nastavení registrace firemních zařízení s Androidem](../enrollment/android-kiosk-enroll.md).

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794--"></a>Kontrola duplicitních identifikátorů podnikových zařízení v jednotlivých řádcích <!-- 2203794-->
Při nahrávání podnikových ID poskytuje Intune seznam všech duplicit a nabízí možnost nahradit nebo ponechat stávající informace. Tato sestava se zobrazí, pokud po výběru **registrace zařízení**@no__t**identifikátory podnikových zařízení** > **Přidat identifikátory**. 

#### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Ruční přidání identifikátorů podnikových zařízení <!-- 2203803 -->
Nyní můžete ručně přidat ID podnikových zařízení. Vyberte **registrace zařízení** > **identifikátory podnikových zařízení** > **Přidat**. 


<!-- ########################## -->
## <a name="june-2018"></a>Červen 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="microsoft-edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Podpora Microsoft Edge Mobile pro zásady ochrany aplikací Intune <!-- 1817882 -->
Prohlížeč Microsoft Edge pro mobilní zařízení teď podporuje zásady ochrany aplikací definované v Intune.

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Načtení ID uživatelského modelu přidružené aplikace (AUMID) pro aplikace Microsoft Store for Business v celoobrazovkovém režimu <!-- 1560077 ! -->
Intune teď může načíst ID uživatelských modelů aplikací (AUMIDs) pro aplikace Microsoft Store for Business (WSfB), aby poskytovala vylepšenou konfiguraci profilu veřejného terminálu.

Další informace o Microsoft Store pro obchodní aplikace najdete v tématu [Správa aplikací z Microsoft Store pro firmy](../apps/windows-store-for-business.md).

#### <a name="new-company-portal-branding-page----1916370---"></a>Nová stránka Portál společnosti brandingu <!-- 1916370 -->
Stránka Portál společnosti branding má nové rozložení, zprávy a popisy tlačítek.


### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="pradeo---new-mobile-threat-defense-partner----1169249---"></a>Pradeo – nový partner ochrany před mobilními hrozbami <!-- 1169249 -->
Přístup mobilních zařízení k podnikovým prostředkům můžete řídit pomocí podmíněného přístupu na základě posouzení rizik, které provádí Pradeo, řešení ochrany před mobilními hrozbami, které se integruje s Microsoft Intune.

#### <a name="use-fips-mode-with-the-ndes-certificate-connector----1333688---"></a>Použití režimu FIPS s certifikátem NDES Certificate Connector <!-- 1333688 -->
Když nainstalujete Certificate Connector pro NDES na počítač s povoleným režimem FIPS (Federal Information Processing Standard), vystavování a odvolávání certifikátů nefungovalo podle očekávání. V této aktualizaci je podpora standardu FIPS zahrnutá spolu s certifikátem NDES Certificate Connector. 

Tato aktualizace zahrnuje také:

- NDES Certificate Connector vyžaduje rozhraní .NET 4,5, které je automaticky součástí systémů Windows Server 2016 a Windows Server 2012 R2. Dříve byla minimální požadovaná verze rozhraní .NET 3,5 Framework.
- Součástí konektoru pro NDES Certificate Connector je podpora TLS 1,2. Takže pokud server s nainstalovaným Certificate Connectorem podporuje TLS 1,2, použije se TLS 1,2. Pokud server nepodporuje TLS 1,2, použije se TLS 1,1. V současné době se k ověřování mezi zařízeními a serverem používá protokol TLS 1,1.

Další informace najdete v tématech [Konfigurace a používání certifikátů SCEP](../protect/certificates-scep-configure.md) a [Konfigurace a používání certifikátů PKCS](../protect/certficates-pfx-configure.md).

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680----"></a>Podpora profilů sítě VPN v Palo Alto Networks GlobalProtect <!-- 1333680 ! -->
V této aktualizaci můžete zvolit Palo Alto Networks GlobalProtect jako typ připojení VPN pro profily VPN v Intune (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **typ profilu** >  VPN.). V této verzi jsou podporovány následující platformy: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Přidání nastavení možností místního zabezpečení zařízení <!-- 1403702 -->
Teď můžete nakonfigurovat další nastavení možností místního zabezpečení zařízení pro zařízení s Windows 10. Další nastavení jsou k dispozici v oblastech klienta sítě Microsoft, serveru sítě Microsoft, přístupu k síti a zabezpečení a interaktivního přihlašování. Při vytváření zásad konfigurace zařízení s Windows 10 najdete tato nastavení v kategorii Endpoint Protection.

#### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Povolit celoobrazovkový režim na zařízeních s Windows 10 <!-- 1560072 ! -->
Na zařízeních s Windows 10 můžete vytvořit konfigurační profil a povolit celoobrazovkový režim (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **omezení zařízení**s**Windows 10** >   >  Veřejný **terminál**). V této aktualizaci se nastavení veřejného **terminálu (Preview)** přejmenuje na veřejné **(zastaralé)** . Veřejný **terminál (zastaralé)** se už nedoporučuje používat, ale bude dál fungovat až do července Update. Veřejný **terminál (zastaralý)** se nahrazuje novým typem profilu veřejného **terminálu** (**vytvořit profil** > **Windows 10** >  veřejného**terminálu (Preview)** ), který bude obsahovat nastavení pro konfiguraci terminálů ve Windows 10 RS4 a novějších verzích.

Platí pro Windows 10 a novější.

#### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Graf grafického uživatele profilu zařízení je zpátky. <!-- 2160133 -->
Když se zlepšily číselné počty zobrazené v grafickém grafu profilu zařízení (**Konfigurace zařízení**@no__t –**1 >** vybrat stávající profil > **Přehled**), grafický uživatelský graf byl dočasně odebrán.

V této aktualizaci se grafický uživatelský graf vrátí zpátky a zobrazí se v Azure Portal.

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication----1165118---"></a>Podpora registrace Windows autopilotu bez ověření uživatele <!-- 1165118 -->
Intune teď podporuje registraci Windows autopilotu bez ověření uživatele. Toto je nová možnost v profilu nasazení Windows autopilotu "režim nasazení autopilotu" nastavený na "samoobslužné nasazení".  Na zařízení musí běžet Windows 10 Insider Preview build 17672 nebo novější a mít čip TPM 2,0 pro úspěšné dokončení tohoto typu registrace. Vzhledem k tomu, že není vyžadováno žádné ověření uživatele, měli byste tuto možnost přiřadit pouze zařízením, u kterých máte fyzickou kontrolu.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Nové nastavení jazyka nebo oblasti při konfiguraci POČÁTEČNÍho nasazení pro autopilot <!-- 1821766 -->
K dispozici je nové nastavení konfigurace pro nastavení jazyka a oblasti pro profily pro autopilotování při nedostatku prostředí. Chcete-li zobrazit nové nastavení, vyberte možnost **registrace zařízení** > **registrace Windows** > **profily nasazení** > **vytvořit profil** > **režim nasazení** =  –**samoobslužné nasazení**1 **Nakonfigurované výchozí hodnoty**.

#### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nové nastavení pro konfiguraci klávesnice zařízení <!-- 1821768 -->
Nové nastavení bude k dispozici pro konfiguraci klávesnice pro profily autopilotu během nedostatku prostředí. Chcete-li zobrazit nové nastavení, vyberte možnost **registrace zařízení** > **registrace Windows** > **profily nasazení** > **vytvořit profil** > **režim nasazení** =  –**samoobslužné nasazení**1 **Nakonfigurované výchozí hodnoty**.

#### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Profily autopilotu přesunu do cílení na skupinu <!-- 1877935 -->
Profily nasazení autopilotu se dají přiřadit ke skupinám Azure AD, které obsahují zařízení s autopilotem.

### <a name="device-management"></a>Správa zařízení

#### <a name="set-compliance-by-device-location----851881----"></a>Nastavit dodržování předpisů podle umístění zařízení <!-- 851881 ! -->
V některých situacích možná budete chtít omezit přístup k firemním prostředkům na konkrétní místo definované síťovým připojením. V závislosti na IP adrese zařízení teď můžete vytvořit zásadu dodržování předpisů (@no__t 1**umístění**pro**zařízení**). Pokud se zařízení přesune mimo rozsah IP adres, zařízení nemůže získat přístup k firemním prostředkům.

Platí pro: zařízení s Androidem 6,0 a vyšší s aktualizovanou Portál společnosti aplikací

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Zabránění uživatelským aplikacím a prostředím v zařízeních Windows 10 Enterprise RS4 autopilot<!-- 1621980 -->
V zařízeních Windows 10 Enterprise RS4 autopilot budete moci zabránit instalaci uživatelských aplikací a prostředí. Tuto funkci zobrazíte tak, že přejdete do služby **Intune** > **Konfigurace zařízení**-1  > **profily** > **vytvořit profil** **platformy** >   = **nebo novější**1**typu profilu**@no__ **omezení zařízení**t-13 5**Konfigurace**7**Windows Spotlight**9**spotřebitelské funkce**. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948---"></a>Odinstalujte nejnovější z aktualizací softwaru Windows 10 <!-- 1732948 -->
Pokud máte v počítačích s Windows 10 zjištěné problémy, můžete si odinstalaci (vrácení zpět) nejnovější aktualizace funkcí nebo nejnovější aktualizaci kvality. Odinstalace funkce nebo aktualizace kvality je dostupná jenom pro kanál pro údržbu, na kterém je zařízení zapnuté. Po odinstalaci se aktivuje zásada pro obnovení předchozí aktualizace na počítačích s Windows 10. V případě aktualizací funkcí můžete omezit čas od 2-60 dnů, po které lze použít odinstalaci nejnovější verze. Pokud chcete nastavit možnosti odinstalace aktualizace softwaru, v okně **Microsoft Intune** v Azure Portal vyberte **aktualizace softwaru** . Pak v okně **aktualizace softwaru** vyberte **aktualizační kanály Windows 10** . Pak můžete zvolit možnost **odinstalovat** v části **Přehled** .

#### <a name="search-all-devices-for-imei-and-serial-number----1793685---"></a>Vyhledat čísla IMEI a sériové číslo pro všechna zařízení <!-- 1793685 -->
V okně všechna zařízení teď můžete vyhledat IMEI a sériová čísla (e-mail, hlavní název uživatele, název zařízení a název správy jsou stále k dispozici). V Intune vyberte **zařízení** > **všechna zařízení** > zadejte do vyhledávacího pole.

#### <a name="management-name-field-will-be-editable----1875989---"></a>Pole název správy bude editovatelné. <!-- 1875989 -->
V okně **vlastností** zařízení teď můžete upravit pole název správy. Chcete-li upravit toto pole, vyberte možnost **zařízení** > **všechna zařízení** > vyberte **vlastnosti**> zařízení. K jednoznačné identifikaci zařízení můžete použít pole název správy.

#### <a name="new-all-devices-filter-device-category----1878520---"></a>Filtr nových zařízení – filtr: kategorie zařízení <!-- 1878520 -->
Teď můžete filtrovat seznam **všechna zařízení** podle kategorie zařízení. Provedete to tak, že vyberete **zařízení** > **všechna zařízení** > **Filtr** > **kategorie zařízení**.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>Použití TeamVieweru pro sdílení obrazovky zařízení s iOS a MacOS <!-- 1985547 -->
Správci se teď můžou připojit k [TeamVieweru](../remote-actions/teamviewer-support.md)a spustit relaci sdílení obrazovky se zařízeními s iOS a MacOS. Uživatelé pro iPhone, iPad a macOS můžou sdílet své obrazovky živě s jakýmkoli jiným počítačem nebo mobilním zařízením. 

#### <a name="multiple-exchange-connector-support----2070451---"></a>Podpora více konektorů Exchange <!-- 2070451 -->
Už nebudete mít omezení na jeden Microsoft Intune Exchange Connector pro každého tenanta. Intune teď podporuje několik konektorů Exchange, abyste mohli nastavit podmíněný přístup Intune s několika místními organizacemi Exchange.

Pomocí místního Exchange Connectoru v Intune můžete spravovat přístup zařízení k místním poštovním schránkám Exchange na základě toho, jestli je zařízení zaregistrované v Intune a vyhovuje zásadám dodržování předpisů zařízením v Intune. K nastavení konektoru si z Azure Portal stáhnete místní Exchange Connector Intune a nainstalujete ho na server v organizaci Exchange. Na řídicím panelu Microsoft Intune zvolte **místní přístup**a v části **Nastavení**zvolte **Exchange ActiveSync Connector**. Stáhněte si konektor Exchange On-Premises Connector a nainstalujte ho na server v organizaci Exchange. Pokud již nejste omezeni na jeden konektor Exchange pro každého tenanta, pokud máte další organizace Exchange, můžete stejný postup použít ke stažení a instalaci konektoru pro každou další organizaci Exchange.

#### <a name="new-device-hardware-detail-ccid----2156657---"></a>Podrobnosti o hardwaru nového zařízení: CCID <!-- 2156657 -->
Pro každé zařízení jsou nyní k dispozici informace o zařízení rozhraní čipové karty (CCID). Pokud se chcete podívat, vyberte **zařízení** > **všechna zařízení** > vyberte zařízení > **hardware**> zaškrtněte v části **Podrobnosti o síti**>.

#### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Přiřadit všechny uživatele a všechna zařízení jako skupiny oborů <!-- 2196803 -->
Teď můžete přiřadit všechny uživatele, všechna zařízení a všechny uživatele a všechna zařízení ve skupinách oborů. Provedete to tak, že zvolíte **role Intune** > **všechny role** >  –**zásady a správce profilů**@no__t-**5 > zvolit přiřazení >** **obor (skupiny)** .

#### <a name="udid-information-now-included-for-ios-and-macos-devices----2219806---"></a>Informace o UDID, které se teď zahrnují pro zařízení s iOS a macOS <!-- 2219806 -->
Pokud chcete zobrazit jedinečný identifikátor zařízení (UDID) pro zařízení s iOS a macOS, přejděte na **zařízení** > **všechna zařízení** > vyberte zařízení > **hardware**. UDID je k dispozici jenom pro podniková zařízení (nastavená v části **zařízení** > **všechna zařízení** > zvolit > **vlastnosti**zařízení  > **vlastnictví zařízení**).

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Vylepšené řešení potíží při instalaci aplikací <!-- 928990 -->
Na Microsoft Intune zařízeních spravovaných MDM se někdy můžou instalace aplikací zdařit. Při selhání instalace této aplikace může být obtížné pochopit důvod selhání nebo vyřešit problém. Dodáváme Public Preview našich funkcí řešení potíží s aplikacemi. Všimněte si nového uzlu v rámci každého zařízení, které se nazývá **spravované aplikace**. Zobrazí se seznam aplikací, které byly doručeny prostřednictvím správy mobilních zařízení (MDM) v Intune. Uvnitř uzlu se zobrazí seznam stavů instalace aplikací. Pokud vyberete jednotlivou aplikaci, zobrazí se pro danou konkrétní aplikaci zobrazení pro odstraňování potíží. V zobrazení pro řešení problémů uvidíte kompletní životní cyklus aplikace, například když byla aplikace vytvořena, upravena, cílena a dodávána do zařízení. Pokud se navíc instalace aplikace nezdařila, zobrazí se kód chyby a užitečná zpráva o příčině chyby. 

#### <a name="intune-app-protection-policies-and-microsoft-edge----1818968---"></a>Zásady ochrany aplikací Intune a Microsoft Edge <!-- 1818968 -->
Prohlížeč Microsoft Edge pro mobilní zařízení (iOS a Android) teď podporuje Microsoft Intune zásady ochrany aplikací. Uživatelé zařízení s iOS a Androidem, kteří se přihlásí pomocí podnikových účtů Azure AD v aplikaci Microsoft Edge, budou chráněni službou Intune. V zařízeních se systémem iOS budou zásady **vyžadovat spravované prohlížeče pro webový obsah** umožňovat uživatelům otevírání odkazů v Microsoft Edge při jejich správě.

<!-- ########################## -->
## <a name="may-2018"></a>Květen 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Konfigurace zásad ochrany aplikací <!-- 2144597 Part 2 -->

V Azure Portal místo přechodu na okno Intune App Protection služby teď stačí přejít na Intune. Pro zásady ochrany aplikací v Intune je teď jenom jedno místo. Všimněte si, že všechny zásady ochrany aplikací jsou v okně **mobilní aplikace** v Intune v části **Zásady ochrany aplikací**. Tato integrace pomáhá zjednodušit správu cloudového řízení. Nezapomeňte, že všechny zásady ochrany aplikací jsou už v Intune, a můžete upravit některou z dříve nakonfigurovaných zásad. Zásady ochrany zásad aplikací (APP) a podmíněného přístupu (CA) služby Intune jsou teď v rámci **podmíněného přístupu**, které najdete v části **správa** v okně **Microsoft Intune** nebo v části **zabezpečení** v **tématu. Okno Azure Active Directory** . Další informace o úpravách zásad podmíněného přístupu najdete [v tématu podmíněný přístup v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Další informace najdete v tématu [co jsou zásady ochrany aplikací?](../apps/app-protection-policy.md)

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Vyžadovat instalaci zásad, aplikací, certifikátů a profilů sítě <!-- 1553555 -->
Správci můžou koncovým uživatelům zablokovat přístup k počítači s Windows 10 RS4, dokud Intune nenainstaluje zásady, aplikace a profily certifikátů a síťových profilů během zřizování zařízení s autopilotem. Další informace najdete v tématu [nastavení stránky stavu registrace](../enrollment/windows-enrollment-status.md).

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Podpora registrace mobilních zařízení Samsung KNOX <!--1112863-->
Při používání Intune se službou Samsung KNOX pro registraci mobilních zařízení (KME) můžete registrovat velké počty zařízení s Androidem vlastněných společností. Uživatelé v Wi-Fi nebo v mobilních sítích se můžou při prvním zapnutí svých zařízení zaregistrovat jenom na několik málo klepnutí. Při použití aplikace pro nasazení Knox je možné zařízení zaregistrovat pomocí technologie Bluetooth nebo NFC. Další informace najdete v tématu [Automatická registrace zařízení se systémem Android pomocí zápisu mobilních zařízení Samsung společnosti Samsung](../enrollment/android-samsung-knox-mobile-enroll.md).

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží 

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Vyžádání pomoc v Portál společnosti pro Windows 10 <!-- 1874137 -->
Portál společnosti pro Windows 10 teď pošle protokoly aplikací přímo Microsoftu, když uživatel zahájí pracovní postup, aby mohl získat pomoc s problémem. To usnadňuje řešení potíží a řešení problémů, které jsou vyvolány společnosti Microsoft.

<!-- ########################## -->
## <a name="april-2018"></a>Duben 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Podpora hesla pro MAM PIN v Androidu<!-- 1438086 -->

Správci Intune můžou nastavit požadavek na spuštění aplikace, aby vynutil heslo místo číselného kódu PIN MAM. Pokud se nakonfiguruje, musí uživatel nastavit a používat heslo, když se zobrazí výzva, abyste měli přístup k aplikacím MAM-podporou. Heslo je definováno jako číselný kód PIN s alespoň jedním speciálním znakem nebo velkým/malým písmenem. Intune pro existující číselný kód PIN podporuje heslo podobným způsobem... schopnost nastavit minimální délku a povolit opakování znaků a sekvencí prostřednictvím konzoly pro správu. Tato funkce vyžaduje nejnovější verzi Portál společnosti v Androidu. Tato funkce je pro iOS už dostupná.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Obchodní podpora (LOB) pro macOS <!-- 1473977 -->
Microsoft Intune poskytne možnost instalovat obchodní aplikace z Azure Portal macOS. Až bude nástroj dostupný v GitHubu, budete moct do Intune přidat aplikaci macOS LOB. V Azure Portal v okně **Intune** vyberte **klientské aplikace** . V okně **klientské aplikace** vyberte **aplikace** > **Přidat**. V okně **Přidat aplikaci** vyberte **obchodní aplikace**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-enterprise-work-profile-app-assignment----1813073---"></a>Předdefinované skupiny všichni uživatelé a všechna zařízení pro přiřazení aplikace pracovního profilu Android Enterprise <!-- 1813073 -->
Můžete využít integrované skupiny **Všichni uživatelé** a **všechna zařízení** pro přiřazení aplikace pracovního profilu Android Enterprise. Další informace najdete v tématu [zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune](../apps/apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Intune znovu nainstaluje požadované aplikace odinstalované uživateli. <!-- 1947010 -->
Pokud koncový uživatel odinstaluje požadovanou aplikaci, Intune automaticky znovu nainstaluje aplikaci do 24 hodin, a ne čeká na 7. cyklus opakovaného vyhodnocení.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Aktualizace místa konfigurace zásad ochrany aplikací <!-- 2144597 -->

V Azure Portal v rámci služby Microsoft Intune vás dočasně přesměrujeme z okna **Intune App Protection** služby do okna **mobilní aplikace** . Všimněte si, že všechny vaše zásady ochrany aplikací se už nacházejí v okně **mobilní aplikace** v Intune v části Konfigurace aplikace. Místo toho, abyste přešli na Intune App Protection, stačí přejít na Intune. V dubnu 2018 zastavíme přesměrování a zcela odebereme okno **Intune App Protection** služby, takže v rámci Intune bude k dispozici jenom jedno umístění pro zásady ochrany aplikací. 

**Jak se to týká?**
Tato změna bude mít vliv na samostatné zákazníky Intune i na hybridní (Intune s Configuration Manager). Tato integrace vám pomůže zjednodušit správu cloudového řízení.

**Co je potřeba udělat, aby se tato změna připravila?**
Místo okna služby **Intune App Protection** a ujistěte se, že jste v okně **mobilní** aplikace v Intune označili pracovní postup zásad ochrany aplikací na oblíbenou položku **Intune** . Přesměrujeme Vás na krátkou dobu a pak se okno **App Protection** odebere. Nezapomeňte, že všechny zásady ochrany aplikací jsou už v Intune, a můžete upravit některé ze zásad podmíněného přístupu. Další informace o úpravách zásad podmíněného přístupu najdete [v tématu podmíněný přístup v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Další informace najdete v tématu [co jsou zásady ochrany aplikací?](../apps/app-protection-policy.md) 

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153---"></a>Graf profilu zařízení a seznam stavů Zobrazit všechna zařízení ve skupině <!-- 1449153 -->
Když konfigurujete profil zařízení (**Konfigurace zařízení** > **profily**), zvolíte profil zařízení, například iOS. Tento profil přiřadíte ke skupině, která zahrnuje zařízení s iOS a zařízení s jiným systémem než iOS. Počet grafických grafů znázorňuje, že se profil používá pro iOS *a* zařízení s jiným systémem než iOS (**Konfigurace zařízení**@no__t **-2 >** výběr existujícího profilu > **Přehled**). Po výběru grafického grafu na kartě **Přehled** se v seznamu **stav zařízení** zobrazí všechna zařízení ve skupině, nikoli jenom zařízení s iOS. 

V této aktualizaci se v grafickém grafu (**Konfigurace zařízení**@no__t-**1 >** vybrat stávající profil > **Přehled**) zobrazuje jenom počet pro konkrétní profil zařízení. Pokud se například konfigurační profil zařízení vztahuje na zařízení s iOS, v grafu se zobrazí jenom počet zařízení s iOS. Výběrem grafického grafu a otevřením **stavu zařízení** se zobrazí pouze zařízení se systémem iOS.

Během této aktualizace je graf grafického uživatele dočasně odebrán. 

#### <a name="always-on-vpn-for-windows-10---1333666---"></a>VPN Always On pro Windows 10 <!--1333666 -->

V současné [době se na](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) zařízeních s Windows 10 v současnosti dá používat vlastní profil VPN (Virtual Private Network) vytvořený pomocí OMA-URI.

V rámci této aktualizace můžou správci povolit funkci Always On pro profily sítě VPN s Windows 10 přímo v Intune v Azure Portal. Profily sítě VPN se vždycky budou automaticky připojovat, když:

- Uživatelé se přihlásí ke svým zařízením.
- Síť v zařízení se změní.
- Po vypnutí se obrazovka na zařízení znovu zapne.

#### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nová nastavení tiskárny pro vzdělávací profily <!-- 1308900 -->

V případě vzdělávacích profilů jsou nová nastavení dostupná v kategorii **tiskárny** : **tiskárny**, **výchozí tiskárna**, **Přidat nové tiskárny**.

#### <a name="show-caller-id-in-personal-profile---android-enterprise-work-profile---1098984---"></a>Zobrazit ID volajícího v osobním profilu – Android Enterprise Work Profile <!--1098984 -->
Při použití osobního profilu na zařízení nemusí koncoví uživatelé vidět podrobnosti ID volajícího z pracovního kontaktu. 

V této aktualizaci je nové nastavení v **Android Enterprise** > **omezení zařízení** > **Nastavení pracovního profilu**:
- Zobrazit v osobním profilu ID volajícího pracovního kontaktu

Pokud je povoleno (Nenakonfigurováno), zobrazí se v osobním profilu podrobnosti o volajícím pracovního kontaktu. Při zablokování se v osobním profilu nezobrazí číslo volajícího pracovního kontaktu. 

Platí pro: zařízení s pracovním profilem Android v systému Android OS v 6.0 a novějších

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Nová nastavení ochrany přihlašovacích údajů v programu Windows Defender přidaná do nastavení ochrany koncových bodů <!--1102252 --><!--from 1802 and 1804-->

V této aktualizaci zahrnuje ochrana [přihlašovacích údajů v programu Windows Defender](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Konfigurace zařízení** > **profily** > **Endpoint Protection**) následující nastavení: 

- **Ochrana Credential Guard v programu Windows Defender**: zapne ochranu Credential Guard se zabezpečením na základě virtualizace. Povolení této funkce pomáhá chránit přihlašovací údaje při příštím restartování, pokud je povolená **úroveň zabezpečení platformy se zabezpečeným spouštěním** a **zabezpečením na základě virtualizace** . Mezi možnosti patří:
  - **Zakázáno**: Pokud byla ochrana přihlašovacích údajů dříve zapnutá pomocí možnosti **Povolit bez zámku**, vypne se ochrana Credential Guard vzdáleně.

  - **Povoleno s zámkem UEFI**: zajistí, že ochranu Credential Guard nelze zakázat pomocí klíče registru nebo pomocí Zásady skupiny. Pokud chcete povolit ochranu Credential Guard po použití tohoto nastavení, musíte nastavit Zásady skupiny na Disabled (zakázáno). Pak odeberte funkce zabezpečení z každého počítače, který má fyzicky přítomného uživatele. Tyto kroky zruší konfiguraci trvale nastavenou v rozhraní UEFI. Pokud bude konfigurace UEFI dál trvat, je povolená ochrana Credential Guard.

  - **Povoleno bez zámku**: umožňuje vzdálené zakázání ochrany přihlašovacích údajů pomocí Zásady skupiny. Na zařízeních, která používají toto nastavení, musí běžet minimálně Windows 10 (verze 1511).

Při konfiguraci ochrany přihlašovacích údajů se automaticky povolí následující závislé technologie: 

- **Povolit zabezpečení na základě virtualizace (VBS)** : při příštím restartování zapne zabezpečení na základě virtualizace (VBS). Zabezpečení na základě virtualizace používá hypervisor Windows k poskytování podpory pro služby zabezpečení a vyžaduje zabezpečené spouštění.
- **Zabezpečené spouštění pomocí přímého přístupu do paměti (DMA)** : zapne vbs s zabezpečeným spouštěním a přímým přístupem k paměti. Ochrana DMA vyžaduje hardwarovou podporu a je povolená jenom na správně nakonfigurovaných zařízeních. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Použití vlastního názvu subjektu v certifikátu SCEP <!-- 2064190 -->
V profilu certifikátu SCEP můžete ve vlastním předmětu použít **OnPremisesSamAccountName** běžný název. Můžete například použít `CN={OnPremisesSamAccountName})`.

#### <a name="block-camera-and-screen-captures-on-android-enterprise-work-profiles----1098977---"></a>Blokování snímků a snímků obrazovky v pracovních profilech Android Enterprise <!-- 1098977 -->
Při konfiguraci omezení zařízení pro zařízení s Androidem jsou pro blokování k dispozici dvě nové vlastnosti: 
- Fotoaparát: blokuje přístup ke všem fotoaparátům na zařízení.
- Snímek obrazovky: blokuje snímek obrazovky a také zabraňuje zobrazení obsahu na zobrazovacích zařízeních, která nemají zabezpečený výstup videa.

Platí pro pracovní profily Android Enterprise.

#### <a name="use-cisco-anyconnect-client-for-ios----1333708---"></a>Použití klienta Cisco AnyConnect pro iOS <!-- 1333708 -->

Když vytváříte nový profil VPN pro iOS, teď jsou k dispozici dvě možnosti: **Cisco AnyConnect** a **Cisco Legacy AnyConnect**. Profily Cisco AnyConnect podporují 4.0.7 x a novější verze. Stávající profily sítě VPN Cisco AnyConnect pro iOS jsou označené **Cisco Legacy AnyConnect**a budou dál fungovat s Cisco AnyConnect 4.0.5 x a staršími verzemi, stejně jako dnes.

> [!NOTE]
> Tato změna platí jenom pro iOS. Pro Android, Android Enterprise Worker a macOS platformy bude i nadále existovat jenom jedna možnost Cisco AnyConnect.


### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nové kroky registrace pro uživatele na zařízeních s macOS vysokým Sierra 10.13.2 + <!--1734567 -->
macOS High Sierra 10.13.2 představil koncept registrace MDM "User Schváliled". Schválené registrace umožňují Intune spravovat některá nastavení citlivá na zabezpečení. Další informace najdete v dokumentaci podpory společnosti Apple zde: https://support.apple.com/HT208019.

Zařízení zaregistrovaná pomocí Portál společnosti macOS se považují za "neschváleného uživatele", pokud koncový uživatel neotevře Předvolby systému a ručně neposkytne schválení. K tomuto účelu Portál společnosti macOS nyní směruje uživatele na macOS 10.13.2 a výše a na konci procesu registrace ručně schválí jejich registraci. Konzola pro správu Intune bude hlásit, jestli je zaregistrované zařízení schválené uživatelem.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>Zařízení macOS zaregistrovaná v Jamf se teď můžou zaregistrovat v Intune. <!-- 2370684 -->
Verze 1,3 a 1,4 portálu společnosti macOS nezaregistrovaly zařízení Jamf v Intune úspěšně. Tento problém řeší 1.4.2 verze portálu macOS.

#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Aktualizované prostředí pro nápovědu v aplikaci Portál společnosti App pro Android <!-- 1631531 -->
Aktualizovali jsme prostředí pro usnadnění práce v aplikaci Portál společnosti pro Android, aby bylo možné zarovnat s osvědčenými postupy pro platformu Android. Když teď uživatelé narazí na problém v aplikaci, můžou klepnout na **nabídku** > **help** a:
- Nahrajte protokoly diagnostiky do Microsoftu.
- Odešlete e-mail s popisem problému a ID incidentu osobě firemní podpory.  

Pokud chcete získat informace o aktualizovaném prostředí pro usnadnění práce, přečtěte si [e-maily o odesílání protokolů](/intune-user-help/send-logs-to-your-it-admin-by-email-android) a [odeslání chyb společnosti Microsoft](/intune-user-help/send-logs-to-microsoft-android).


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nový graf trendu selhání registrace a tabulka důvodů selhání <!-- 1471783 -->
Na stránce Přehled registrace můžete zobrazit trend selhání registrace a pět nejčastějších příčin selhání. Kliknutím na graf nebo tabulku můžete přejít k podrobnostem a najít Rady pro řešení problémů a návrhy na nápravu.


### <a name="device-management"></a>Správa zařízení

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----1629303---"></a>Rozšířená ochrana před internetovými útoky (ATP) a Intune jsou plně integrované. <!-- 1629303 -->

[Rozšířená ochrana před internetovými útoky (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) zobrazuje úroveň rizika pro zařízení s Windows 10. V programu Windows Defender Security Center (portál ATP) můžete vytvořit připojení k Microsoft Intune. Po vytvoření se pomocí zásad dodržování předpisů Intune určí přijatelná úroveň hrozeb. Pokud dojde k překročení úrovně hrozby, zásada podmíněného přístupu Azure Active Directory (AD) pak může blokovat přístup k různým aplikacím v rámci vaší organizace.

Tato funkce umožňuje ATP kontrolovat soubory, zjišťovat hrozby a nahlásit veškerá rizika na zařízeních s Windows 10.

Viz [Povolení ATP pomocí podmíněného přístupu v Intune](../protect/advanced-threat-protection.md).

#### <a name="support-for-user-less-devices----1637553---"></a>Podpora pro zařízení bez uživatelů <!-- 1637553 -->
Intune podporuje možnost vyhodnotit dodržování předpisů u zařízení bez uživatele, jako je například Microsoft Surface Hub. Zásady dodržování předpisů mohou cílit na konkrétní zařízení. Proto je možné určit dodržování předpisů (a nedodržující předpisy) pro zařízení, která nemají přidruženého uživatele.

#### <a name="delete-autopilot-devices----1713650---"></a>Odstranit zařízení autopilotu <!-- 1713650 -->
Správci Intune můžou [Odstranit zařízení autopilotu](../enrollment/enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Vylepšené prostředí pro odstraňování zařízení <!--1832333 -->
Před [odstraněním zařízení z Intune](../remote-actions/devices-wipe.md#delete-devices-from-the-intune-portal)už nebudete muset odebrat firemní data nebo obnovit tovární nastavení zařízení.

Pokud se chcete podívat na nové prostředí, přihlaste se k Intune a vyberte **zařízení** > **všechna zařízení** > název > **Odstranit**.

Pokud stále chcete potvrdit vymazání/vyřazení, můžete použít standardní trasu životního cyklu zařízení tak, že před **odstraněním**vydáte **Odebrání firemních dat** a **obnovení továrního nastavení** . 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Přehrávání zvuků v systému iOS v režimu ztráty <!-- 1947769 -->
Pokud jsou zařízení se systémem iOS v [režimu ztráty](../remote-actions/device-lost-mode.md)MDM (Mobile Device Management), můžete [Přehrát zvuk](../remote-actions/device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**zařízení** > **všechna zařízení** > Vybrat > **Přehled** > **dalších**). Zvuk bude pokračovat, dokud se zařízení neodebere z režimu ztráty nebo když uživatel na zařízení zakáže zvuk. Platí pro zařízení s iOS 9,3 a novější.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Blokování nebo povolení výsledků hledání na webu v zařízení Intune <!--1972804-->

Správci teď můžou blokovat výsledky hledání na webu v zařízení.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Vylepšené zasílání zpráv o chybách pro Apple MDM Push Certificate chyba nahrávání <!-- 2172331 -->

Chybová zpráva vysvětluje, že při obnovení existujícího certifikátu MDM se musí použít stejné Apple ID.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>Testování Portál společnosti pro macOS na virtuálních počítačích <!-- 2216679 -->

Publikovali jsme doprovodné materiály, které správcům IT pomůžou otestovat Portál společnosti aplikaci pro macOS na virtuálních počítačích v paralelním prostředí pro stolní počítače a VMware Fusion. Další informace najdete v [zápisu virtuálních počítačů s MacOS pro účely testování](../enrollment/macos-enroll.md#enroll-virtual-macos-machines-for-testing).

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>Aktualizace uživatelského prostředí pro aplikaci Portál společnosti pro iOS <!--1412866 -->
V aplikaci Portál společnosti pro iOS jsme vydali velkou aktualizaci uživatelského prostředí. Tato aktualizace nabízí kompletní vzhled vizuálu, který obsahuje moderní vzhled a chování. Zachováváme funkčnost aplikace, ale zvýšili její použitelnost a přístupnost.  

Uvidíte také tyto informace:
- Podpora pro iPhone X.
- Rychlejší spouštění aplikací a načítání odpovědí, aby se ušetřil čas uživatelů
- Další indikátory průběhu, které uživatelům poskytují nejaktuálnější informace o stavu.
- Vylepšení způsobu, jakým uživatelé odesílají protokoly, takže pokud dojde k nějakému problému, je snazší ji vykázat.  

Pokud si chcete prohlédnout aktualizovaný vzhled, přejděte na téma [co je nového v uživatelském rozhraní aplikace](../whats-new-app-ui.md).

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca----1056954---"></a>Ochrana místních dat Exchange pomocí aplikace a certifikační autority Intune <!-- 1056954 -->
Teď můžete pomocí aplikace Intune App Policy Protection (APP) a podmíněného přístupu (CA) ochránit přístup k místním datům Exchange pomocí Outlooku Mobile. Chcete-li přidat nebo upravit zásady ochrany aplikací v rámci Azure Portal, vyberte možnost **Microsoft Intune** > **klientské aplikace** **Zásady ochrany aplikací** > . Před použitím této funkce se ujistěte, že splňujete [požadavky na Outlook pro iOS a Android](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx).


### <a name="user-interface"></a>Uživatelské rozhraní

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Vylepšené dlaždice zařízení ve Windows 10 Portál společnosti <!--2213364 -->

Dlaždice byly aktualizovány, aby byly k dispozici pro uživatele s nízkým zrakem a aby je bylo možné lépe používat pro nástroje pro čtení obrazovky.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Odesílání diagnostických sestav v aplikaci Portál společnosti pro macOS <!-- 2216677 -->
Portál společnosti aplikace pro zařízení macOS se aktualizovala, aby se vylepšilo, jak uživatelé nahlásili chyby související s Intune. Z aplikace Portál společnosti můžou vaši zaměstnanci:

- Odesílat diagnostické zprávy přímo týmu Microsoftu pro vývojáře.
- Odešlete ID incidentu e-mailem týmu podpory IT vaší společnosti.

Další informace najdete v tématu [odeslání chyb pro MacOS](/intune-user-help/send-errors-macos).

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010---"></a>V Portál společnosti aplikaci pro Windows 10 se Intune přizpůsobí systému pro návrh Fluent. <!-- 1195010 -->
Aplikace Portál společnosti Intune pro Windows 10 se aktualizovala pomocí [zobrazení navigace v systému pro návrh Fluent](https://docs.microsoft.com/windows/uwp/design/basics/navigation-basics). Podél strany aplikace si všimnete statického a svislého seznamu všech stránek na nejvyšší úrovni. Kliknutím na libovolný odkaz můžete rychle zobrazit a přepínat mezi stránkami. Toto je první z několika aktualizací, které se zobrazí v rámci naší průběžné snahy o vytvoření přizpůsobivého, empatickéhoého a známého prostředí v Intune. Pokud si chcete prohlédnout aktualizovaný vzhled, přejděte na téma [co je nového v uživatelském rozhraní aplikace](../whats-new-app-ui.md).

<!-- ########################## -->
## <a name="march-2018"></a>Březen 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Výstrahy na vypršení platnosti obchodních aplikací (LOB) pro iOS pro Microsoft Intune <!-- 748789 -->

V Azure Portal vás Intune upozorní na obchodní aplikace pro iOS, jejichž platnost brzy vyprší. Po nahrání nové verze obchodní aplikace pro iOS Intune odebere oznámení o vypršení platnosti ze seznamu aplikací. Toto oznámení o vypršení platnosti bude aktivní jenom pro nově nahrané obchodní aplikace pro iOS. Před vypršením platnosti zřizovacího profilu pro obchodní aplikace pro iOS se zobrazí upozornění 30 dní. Po vypršení platnosti se výstraha změní na vypršela platnost.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Přizpůsobení Portál společnostich motivů pomocí hexadecimálních kódů <!--1049561 -->

Barvy motivu v aplikacích Portál společnosti můžete přizpůsobit pomocí hexadecimálních kódů. Když zadáte šestnáctkový kód, Intune určí barvu textu, která poskytuje nejvyšší úroveň kontrastu mezi barvou textu a barvou pozadí. Můžete zobrazit náhled barvy textu i loga společnosti proti barvě v **klientských aplikacích** > **portál společnosti**.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Zahrnutí a vyloučení přiřazení aplikací na základě skupin pro Android Enterprise <!-- 1813081 -->

Android Enterprise (dříve označovaný jako Android for Work) podporuje zahrnutí skupin a jejich vyloučení, ale nepodporuje předem vytvořené předdefinované skupiny **Všichni uživatelé** a **všechna zařízení** . Další informace najdete v tématu [zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune](../apps/apps-inc-exl-assignments.md).


### <a name="device-management"></a>Správa zařízení

### <a name="export-all-devices-into-csv-files-in-ie-microsoft-edge-or-chrome----2258071---"></a>Export všech zařízení do souborů CSV v IE, Microsoft Edge nebo Chrome <!-- 2258071 -->
V **zařízeních** > **všechna zařízení**můžete **exportovat** do seznamu ve formátu CSV. Uživatelé aplikace Internet Explorer (IE) s > 10 000 zařízení mohou úspěšně exportovat zařízení do více souborů. Každý soubor má až 10 000 zařízení.

Uživatelé Microsoft Edge a Chrome s >mi 30000 zařízeními můžou zařízení úspěšně vyexportovat do více souborů. Každý soubor má až 30 000 zařízení.

[Správa zařízení](../remote-actions/device-management.md) poskytuje podrobnější informace o tom, co můžete dělat se zařízeními, která spravujete.

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Nová vylepšení zabezpečení ve službě Intune  <!-- 1637539 -->   

Zavedli jsme přepínací tlačítko v Intune v Azure, které můžou používat samostatné zákazníky Intune, aby pocházely s zařízeními bez jakýchkoli zásad přiřazených jako **kompatibilních** (funkce zabezpečení vypnuté), nebo aby tato zařízení považovala za **nekompatibilní** (funkce zabezpečení zapnuté) Tím se zajistí přístup k prostředkům až po vyhodnocení dodržování předpisů zařízením.

Tato funkce se liší v závislosti na tom, jestli už máte přiřazené zásady dodržování předpisů.

- Pokud jste nový nebo existující účet a nemáte žádné zásady dodržování předpisů přiřazené vašim zařízením, pak je přepínač automaticky nastaven na **vyhovující předpisům**. Tato funkce je ve výchozím nastavení v konzole vypnutá. Neexistuje žádný dopad na koncového uživatele.
- Pokud jste existující účet a máte všechna zařízení, která jsou jim přiřazena zásada dodržování předpisů, je přepínač automaticky nastaven na **nevyhovující**předpisům. Tato funkce je ve výchozím nastavení zapnutá, protože se aktualizuje aktualizace z března.

Pokud používáte zásady dodržování předpisů s podmíněným přístupem (CA) a máte zapnutou funkci, všechna zařízení, která nemají alespoň jednu přiřazenou zásadu dodržování předpisů, teď budou zablokovaná certifikační autoritou. Koncoví uživatelé přidružení k těmto zařízením, kteří měli dříve povolený přístup k e-mailu, ztratí přístup, pokud pro všechna zařízení nepřiřadíte alespoň jednu zásadu dodržování předpisů.   

Všimněte si, že i když je výchozí stav přepínání zobrazený v uživatelském rozhraní hned po aktualizacích služby Intune, tento stav přepnutí se hned neuplatní. Jakékoli změny provedené v přepínači nebudou mít vliv na dodržování předpisů zařízením, dokud si váš účet nebudete moct nechat mít k dispozici pracovní přepínač. Až dokončíme váš účet, informujte vás prostřednictvím centra zpráv. Může to trvat až několik dní od aktualizace služby Intune po dobu březen.

**Další informace**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Vylepšené zjišťování jailbreaků <!-- 846515 -->

Rozšířené zjišťování jailbreaků je nové nastavení dodržování předpisů, které zlepšuje způsob, jakým Intune vyhodnocuje zařízení s jailbreakem. Toto nastavení způsobí, že se zařízení bude v Intune vracet častěji, což používá služby zjišťování polohy zařízení a ovlivňuje využití baterie.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Resetování hesel pro zařízení s Androidem O <!-- 1238299 -->
U zaregistrovaných zařízení s Androidem 8,0 budete moct resetovat hesla pomocí pracovních profilů. Když do zařízení s Androidem 8,0 odešlete žádost o resetování hesla, nastaví se aktuálnímu uživateli nové heslo pro odemčení zařízení nebo výzva spravovaného profilu. Heslo nebo výzva se odešlou a okamžitě se projeví.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Zaměření zásad dodržování předpisů na zařízení ve skupinách zařízení <!--1307012 -->

Zásady dodržování předpisů můžete cílit na uživatele ve skupinách uživatelů. V této aktualizaci můžete cílit zásady dodržování předpisů na zařízení ve skupinách zařízení. Zařízení cílící jako součást skupin zařízení neobdrží žádné akce dodržování předpisů.

#### <a name="new-management-name-column----1333586---"></a>Nový sloupec pro název správy <!-- 1333586 -->
 V okně zařízení je k dispozici nový sloupec s názvem **název správy** . Toto je automaticky generovaný neupravitelný název na zařízení, který je založený na následujícím vzorci:
- Výchozí název pro všechna zařízení: <username> @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4
- Pro hromadně přidaná zařízení: < PackageId/ProfileId > <em> @ no__t-1 @ no__t-2 @ no__t-3

Toto je volitelný sloupec v okně zařízení. Ve výchozím nastavení není k dispozici a k němu můžete přistupovat pouze pomocí voliče sloupců. Název zařízení není tímto novým sloupcem ovlivněn.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837---"></a>zařízení se systémem iOS se zobrazí výzva k zadání kódu PIN každých 15 minut. <!--1550837 -->
Po použití zásady dodržování předpisů nebo zásad konfigurace na zařízení se systémem iOS se uživatelům zobrazí výzva k nastavení kódu PIN každých 15 minut. Uživatelům se průběžně zobrazuje výzva, dokud se nenastaví kód PIN.

#### <a name="schedule-your-automatic-updates---1805514---"></a>Naplánování automatických aktualizací <!--1805514 -->
Intune vám umožňuje řídit instalaci automatických aktualizací pomocí [nastavení web Windows Update Ring](../protect/windows-update-for-business-configure.md). V této aktualizaci můžete naplánovat opakované aktualizace, včetně týdne, dne a času.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763---"></a>Jako předmět certifikátu SCEP použijte plně rozlišující název. <!--2221763 -->
Když vytváříte profil certifikátu SCEP, zadáváte název subjektu. V této aktualizaci můžete jako předmět použít plně rozlišující název. Jako **název předmětu**vyberte **Custom (vlastní**) a potom zadejte `CN={{OnPrem_Distinguished_Name}}`. Pokud chcete použít proměnnou `{{OnPrem_Distinguished_Name}}`, synchronizujte atribut uživatele `onpremisesdistingishedname` pomocí [Azure Active Directory (AD) připojit](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) k Azure AD.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983---"></a>Povolení sdílení kontaktů přes Bluetooth – Android for Work <!--1098983 -->
Android standardně zabraňuje synchronizaci kontaktů v pracovním profilu se zařízeními Bluetooth. V důsledku toho se kontakty pracovního profilu nezobrazují na ID volajícího pro zařízení Bluetooth.

V této aktualizaci je nové nastavení v **Androidu for Work** > **omezení zařízení** > **Nastavení pracovního profilu**:
- Sdílení kontaktů přes Bluetooth

Správce Intune může nakonfigurovat tato nastavení tak, aby umožňovala sdílení. To je užitečné při párování zařízení se zařízením Bluetooth na bázi auta, které zobrazuje ID volajícího pro použití bez praktických výhod. Pokud je tato možnost povolená, zobrazí se kontakty pracovního profilu. Pokud není povolený, kontakty pracovního profilu se nezobrazí.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459---"></a>Konfigurace serveru gatekeeper pro řízení zdroje stahování aplikace macOS <!-- 1690459 -->

Server Gatekeeper můžete nakonfigurovat tak, aby chránil vaše zařízení před aplikacemi tím, že určuje, odkud se dají aplikace Stáhnout. Můžete nakonfigurovat tyto zdroje stahování: **Mac App Store**, **Mac App Store a identifikování vývojáři**nebo **kdekoli**. Můžete nakonfigurovat, jestli můžou uživatelé instalovat aplikaci pomocí ovládacího prvku – kliknutím můžete tyto ovládací prvky gatekeeper přepsat.

Tato nastavení najdete v části **Konfigurace zařízení** -> **vytvořit profil** -> **MacOS** -> **Endpoint Protection**.

#### <a name="configure-the-mac-application-firewall----1690461---"></a>Konfigurace brány firewall pro aplikace pro Mac <!-- 1690461 -->

Můžete nakonfigurovat bránu firewall pro aplikace pro Mac. Tuto možnost můžete použít k řízení připojení na základě jednotlivých aplikací, nikoli na základě jednotlivých portů. Díky tomu je snazší získat výhody ochrany brány firewall a pomáhá zabránit nežádoucím aplikacím v převzetí kontroly nad síťovými porty otevřenými pro legitimní aplikace.

Tuto funkci najdete v části **Konfigurace zařízení** -> **Vytvoření profilu** -> **MacOS** -> **Endpoint Protection**.

Jakmile povolíte nastavení brány firewall, můžete nakonfigurovat bránu firewall pomocí dvou strategií:

- Blokovat všechna příchozí připojení

   Můžete blokovat všechna příchozí připojení pro cílová zařízení. Pokud se tak rozhodnete, že se příchozí připojení zablokuje pro všechny aplikace.

- Povolí nebo zablokuje konkrétní aplikace.

   Pro příjem příchozích připojení můžete konkrétním aplikacím dovolit nebo blokovat. Můžete také povolit neviditelný režim a zabránit tak odezvy na požadavky na zjišťování.

#### <a name="detailed-error-codes-and-messages----1376342---"></a>Podrobné kódy a zprávy o chybách <!-- 1376342 -->

V konfiguraci zařízení jsou k dispozici podrobnější kódy chyb a chybové zprávy, které lze zobrazit. Toto vylepšené generování sestav zobrazuje nastavení, stav těchto nastavení a podrobnosti o řešení potíží.

##### <a name="more-information"></a>Další informace

- Blokovat všechna příchozí připojení

   Tím se zablokuje všechny služby sdílení (například sdílení souborů a sdílení obrazovky) od přijetí příchozích připojení. Systémové služby, u kterých je stále povolen příjem příchozích připojení, jsou:
  - config-implementuje službu DHCP a další služby konfigurace sítě.
  - mDNSResponder – implementuje Bonjour.
  - Racoon – implementuje protokol IPSec.

    Pokud chcete používat služby sdílení, ujistěte se, že jsou **příchozí připojení** nastavená na **nenakonfigurovaná** ( **neblokované**).

- Neviditelný režim

   Tuto možnost povolte, pokud chcete zabránit počítači v reakci na požadavky na zjišťování. Počítač stále odpoví na příchozí požadavky na autorizované aplikace. Neočekávané žádosti, jako je například ICMP (test), jsou ignorovány.

#### <a name="disable-checks-on-device-restart---1805490---"></a>Zakázat kontrolu restartování zařízení <!--1805490 -->
Intune poskytuje kontrolu nad [správou aktualizací softwaru](../protect/windows-update-for-business-configure.md). V této aktualizaci je k dispozici vlastnost <strong>restartovat kontroly</strong> a ve výchozím nastavení povolená. Pokud chcete přeskočit typické kontroly, ke kterým dojde po restartování zařízení (například aktivní uživatelé, úrovně baterie atd.), vyberte <strong>Přeskočit</strong>.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Nové kanály Windows 10 Insider Preview dostupné pro kroužky nasazení <!-- 1746293 -->
Při vytváření okruhu nasazení Windows 10 teď máte možnost vybrat následující kanály pro údržbu Windows 10 Insider Preview:
- Rychlé sestavení &#8208; Windows Insider
- Sestavení &#8208; programu Windows Insider je pomalé.
- Vydání buildu Windows Insider 

Další informace o těchto kanálech najdete v tématu [Správa buildů Insider Preview](https://insider.windows.com/for-business-organization-admin/).   
Další informace o vytváření kanálů nasazení v Intune najdete v tématu [Správa aktualizací softwaru v Intune](../protect/windows-update-for-business-configure.md).

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Nové nastavení ochrany zneužití v programu Windows Defender <!-- 1631893 -->

Šest nových nastavení <strong>omezení možností útoku</strong> a rozbalený <strong>řízený přístup ke složkám: možnosti ochrany složky</strong> jsou nyní k dispozici. Tato nastavení najdete tady: configuration\Profiles\ zařízení
Vytvořte profile\Endpoint protection\Windows Defender zneužití Guard.

#### <a name="attack-surface-reduction"></a>Omezení možností útoku

|Název nastavení  |Nastavení možností  |Popis  |
|---------|---------|---------|
|Rozšířená ochrana ransomwarem|Povoleno, audit, Nenakonfigurováno|Použijte agresivní ransomwarem Protection.|
|Označení krádeže přihlašovacích údajů ze subsystému místního úřadu zabezpečení systému Windows|Povoleno, audit, Nenakonfigurováno|Označení krádeže přihlašovacích údajů ze subsystému místního úřadu zabezpečení systému Windows (Lsass. exe).|
|Vytváření procesů z příkazů PSExec a WMI|Blokovat, audit, Nenakonfigurováno|Blokuje vytváření procesů, které pocházejí z příkazů PSExec a WMI.|
|Nedůvěryhodné a nepodepsané procesy, které se spouštějí z USB|Blokovat, audit, Nenakonfigurováno|Zablokovat nedůvěryhodné a nepodepsané procesy, které se spouštějí z USB.|
|Spustitelné soubory, které nesplňují kritéria prevalence, stáří nebo seznamu důvěryhodných souborů|Blokovat, audit, Nenakonfigurováno|Zablokovat spouštění spustitelných souborů, pokud nesplňují kritéria prevalence, stáří nebo seznamu důvěryhodných souborů.|

#### <a name="controlled-folder-access"></a>Řízený přístup ke složkám

|              Název nastavení               |                                                              Nastavení možností                                                              | Popis |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Ochrana složky (již implementováno) | Nenakonfigurováno, povolit, pouze audit (již implementováno)<br><br> <strong>New</strong><br>Zablokovat úpravu disku, auditovat úpravu disku |             |

Chránit soubory a složky před neoprávněnými změnami nepřátelskými aplikacemi<br><br>**Povolit**: zabránit nedůvěryhodným aplikacím v úpravách nebo odstraňování souborů v chráněných složkách a z zápisu do sektorů disku.<br><br>
**Zablokovat pouze změny disku**:<br>Blokuje nedůvěryhodné aplikace v zápisu do sektorů disku. Nedůvěryhodné aplikace mohou i nadále upravovat nebo odstraňovat soubory v chráněných složkách. |

### <a name="intune-apps"></a>Aplikace Intune

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory weby můžou vyžadovat aplikaci Intune Managed Browser a podporovat jednotné přihlašování pro Managed Browser (Public Preview). <!-- 710595 -->

Pomocí Azure Active Directory (Azure AD) teď můžete omezit přístup k webům na mobilních zařízeních do Intune Managed Browser aplikace. V Managed Browser zůstanou data webu zabezpečená a oddělená od osobních dat koncových uživatelů. Kromě toho Managed Browser podporuje možnosti jednotného přihlašování pro weby, které jsou chráněné službou Azure AD. Přihlášení k Managed Browser nebo použití Managed Browser na zařízení s jinou aplikací spravovanou službou Intune umožňuje Managed Browser přístup k firemním webům chráněným pomocí služby Azure AD, aniž by uživatel musel zadat své přihlašovací údaje. Tato funkce se vztahuje na weby, jako je Outlook Web Access (OWA) a SharePoint Online, jakož i na jiné firemní weby, jako jsou prostředky intranetu, ke kterým se přistupoval prostřednictvím služby Azure App proxy. Další informace najdete v tématu [řízení přístupu v Azure Active Directory podmíněný přístup](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Aplikace Portál společnosti pro Visual Update pro Android <!--976944 -->

Aktualizovali jsme Portál společnostiou aplikaci pro Android, která bude postupovat podle pokynů pro [Návrh materiálu](https://material.io/) v Androidu. V článku [co je nového v uživatelském rozhraní aplikace](../whats-new-app-ui.md) uvidíte obrázky nových ikon.

#### <a name="company-portal-enrollment-improved----1874230-eeready--"></a>Vylepšení registrace Portál společnosti <!-- 1874230 eeready-->
Uživatelé, kteří registrují zařízení pomocí Portál společnosti ve Windows 10 Build 1703 a teď můžou dokončit první krok registrace, aniž byste museli aplikaci opustit.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868---"></a>HoloLens a Surface Hub se nyní zobrazují v seznamech zařízení <!--1725868 -->
Přidali jsme podporu pro zobrazení HoloLens a Surface Hub zařízení zaregistrovaných v Intune do Portál společnosti aplikace pro Android.

#### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Vlastní kategorie knih pro e-knihy programu Volume-purchase program (VPP) <!-- 1488911 -->
Můžete vytvářet vlastní kategorie e-knih a pak jim přiřadit e-knihy VPP k těmto vlastním kategoriím e-knih. Koncoví uživatelé pak mohou vidět nově vytvořené kategorie a knihy e-knihy přiřazené k kategoriím. Další informace najdete v tématu [Správa hromadně zakoupených aplikací a knih pomocí Microsoft Intune](../apps/vpp-apps.md).  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option----2070166---"></a>Podpora změn pro možnost Odeslat názor z aplikace Portál společnosti pro Windows <!-- 2070166 -->
Od 30. dubna 2018 se možnost **odeslání zpětné vazby** v aplikaci Portál společnosti pro Windows bude pracovat jenom na zařízeních s Windows 10 výročí Update (1607) a novějším. Možnost odeslání zpětné vazby už není podporovaná, pokud používáte aplikaci Portál společnosti pro Windows s:  
- Windows 10, verze 1507  
- Windows 10, verze 1511  
- Windows Phone 8,1 

Pokud vaše zařízení běží na Windows 10 RS1 nebo novějším, Stáhněte si nejnovější verzi aplikace Portál společnosti pro Windows ze Storu. Pokud používáte nepodporovanou verzi, pokračujte prosím a pošlete nám svůj názor prostřednictvím následujících kanálů: 
- Aplikace centra Feedback ve Windows 10
- E-mail @no__t – 0  

#### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nové nastavení ochrany Application Guard v programu Windows Defender <!-- 1631890 -->

- **Povolit akceleraci grafiky**: Správci můžou povolit virtuální grafické procesory pro ochranu Application Guard v programu Windows Defender. Toto nastavení umožňuje procesoru přesměrování vykreslování grafiky na vGPU. To může zvýšit výkon při práci s výraznými weby s grafikou nebo při sledování videa v kontejneru.

- **SaveFilestoHost**: Správci můžou povolit předávání souborů z Microsoft Edge, který běží v kontejneru, do hostitelského souborového systému. Zapnutím této funkce umožníte uživatelům stahovat soubory z Microsoft Edge v kontejneru do hostitelského souborového systému.

#### <a name="mam-protection-policies-targeted-based-on-management-state----1665993---"></a>Cílení na zásady ochrany MAM na základě stavu správy <!-- 1665993 -->
Můžete cílit na zásady MAM na základě stavu správy zařízení:
- **Zařízení s Androidem** : můžete cílit na nespravovaná zařízení, zařízení spravovaná v Intune a profily Android Enterprise spravované přes Intune (dříve Android for Work).
- **zařízení se systémem iOS** – můžete cílit na nespravovaná zařízení (jenom mam) nebo spravovaná zařízení Intune.

    > [!NOTE]
    > - Podpora iOS pro tuto funkci je zavedená v průběhu dubna 2018.

Další informace najdete v tématu [cílení zásad ochrany aplikací na základě stavu správy zařízení](../apps/app-protection-policies.md).

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Vylepšení jazyka v aplikaci Portál společnosti pro Windows <!-- 1683758 -->
Vylepšili jsme jazyk v Portál společnosti pro Windows 10 tak, aby byl uživatelsky přívětivější a specifický pro vaši společnost. Pokud se chcete podívat na příklady imagí, co jsme udělali, přečtěte si téma [co je nového v uživatelském rozhraní aplikace](../whats-new-app-ui.md).

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Nové dodatky k naší dokumentaci o ochraně osobních údajů uživatelů <!-- 1440709 -->
V rámci naší snahy poskytnout koncovým uživatelům větší kontrolu nad jejich daty a ochranou osobních údajů jsme publikovali aktualizace našich dokumentů, které vysvětlují, jak zobrazit a odstranit data uložená místně pomocí aplikací Portál společnosti. Tyto aktualizace můžete najít v těchto umístěních:

- **Android**: [odebrání zařízení s Androidem z Intune](/intune-user-help/unenroll-your-device-from-intune-android)
- **Android, pokud uživatel odmítl používání podmínek použití**: [Odebrat správu zařízení, Pokud odmítnete "podmínkami použití"](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android)
- **iOS**: [odebrání zařízení se systémem iOS z Intune](/intune-user-help/unenroll-your-device-from-intune-ios)
- **Windows**: [odebrání zařízení s Windows z Intune](/intune-user-help/unenroll-your-device-from-intune-windows)

<!-- ########################## -->
## <a name="february-2018"></a>Únor 2018

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Podpora Intune pro víc účtů Apple DEP/Apple School Manageru <!-- 747685 -->

Intune teď podporuje registraci zařízení z až 100 různých účtů [apple program registrace zařízení (DEP)](../enrollment/device-enrollment-program-enroll-ios.md) nebo [Apple School Manager](../enrollment/apple-school-manager-set-up-ios.md) . Každý odeslaný token se dá spravovat samostatně pro profily a zařízení zápisu. K nahranému tokenu DEP nebo School Manageru se dá automaticky přiřadit jiný registrační profil. Pokud se nahrají víc tokenů School Manageru, dá se Microsoft School data Sync současně sdílet jenom jedna.

Po migraci nebudou rozhraní API beta verze a publikované skripty pro správu služby Apple DEP nebo ASM přes graf nadále fungovat. Nová rozhraní API beta verze jsou ve vývoji a budou se vydávat po migraci.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Viz omezení registrace na uživatele. <!-- 1634444 eeready wnready -->
V okně **řešení potíží** teď můžete zobrazit [platná omezení registrace](../enrollment/enrollment-restrictions-set.md) pro jednotlivé uživatele tak, že v seznamu **přiřazení** vyberete **omezení registrace** .

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Nová možnost pro ověřování uživatelů pro hromadnou registraci Apple <!-- 747625 eeready -->

> [!NOTE]
> Noví klienti to uvidí hned. U stávajících tenantů je tato funkce zahrnuta do dubna. Až do dokončení tohoto zavedení, možná nebudete mít k těmto novým funkcím přístup.

Intune teď nabízí možnost ověřovat zařízení pomocí aplikace Portál společnosti pro následující metody registrace:

- Apple Program registrace zařízení
- Apple School Manager
- Registrace Apple Configuratoru

Při použití možnosti Portál společnosti lze vyhovět Azure Active Directory Multi-Factor Authentication bez blokování těchto metod registrace.

Když použijete možnost Portál společnosti, přeskočí Intune ověřování uživatelů v Průvodci nastavením iOS pro zápis přidružení uživatele. To znamená, že se zařízení zpočátku zaregistrovalo jako zařízení bez uživatele, a proto nepřijímá konfigurace ani zásady pro skupiny uživatelů. Přijímá jenom konfigurace a zásady pro skupiny zařízení. Intune ale na zařízení automaticky nainstaluje aplikaci Portál společnosti. První uživatel, který se má spustit, a přihlaste se k aplikaci Portál společnosti bude přidružen k zařízení v Intune. V tomto okamžiku bude uživatel dostávat konfigurace a zásady pro skupiny uživatelů. Přidružení uživatele nelze změnit bez opětovné registrace.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Podpora Intune pro víc účtů Apple DEP/Apple School Manageru <!-- 747685 eeready -->

Intune teď podporuje registraci zařízení z až 100 různých účtů Apple Program registrace zařízení (DEP) nebo Apple School Manager. Každý odeslaný token se dá spravovat samostatně pro profily a zařízení zápisu. K nahranému tokenu DEP nebo School Manageru se dá automaticky přiřadit jiný registrační profil. Pokud se nahrají víc tokenů School Manageru, dá se Microsoft School data Sync současně sdílet jenom jedna.

Po migraci nebudou rozhraní API beta verze a publikované skripty pro správu služby Apple DEP nebo ASM přes graf nadále fungovat. Nová rozhraní API beta verze jsou ve vývoji a budou se vydávat po migraci.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Vzdálený tisk přes zabezpečenou síť <!-- 1709994  -->
Řešení bezdrátového mobilního tisku v PrinterOn umožní uživatelům vzdáleně tisknout odkudkoli přes zabezpečenou síť. PrinterOn se integruje se sadou Intune APP SDK pro iOS i Android. Do této aplikace budete moct cílit zásady ochrany aplikací prostřednictvím okna **Zásady ochrany aplikací** Intune v konzole pro správu. Koncoví uživatelé budou moct stáhnout aplikaci PrinterOn for Microsoft prostřednictvím Obchod Play nebo iTunes pro použití v rámci ekosystému Intune.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Podpora macOS Portál společnosti pro registrace, které používají správce registrace zařízení <!-- 1352411 -->

Uživatelé teď můžou používat správce registrace zařízení při registraci v macOS Portál společnosti.

### <a name="device-management"></a>Správa zařízení

#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Stavové zprávy o stavu hrozeb v programu Windows Defender <!--854704 -->

Klíč ke správě počítačů s Windows je porozumět stavu a stavu programu Windows Defender.  V rámci této aktualizace Intune přidává nové sestavy a akce do stavu a stavu agenta Windows Defenderu. Pomocí souhrnné sestavy stavu v úloze [dodržování předpisů zařízením](../protect/compliance-policy-monitor.md)můžete zobrazit zařízení, která potřebují následující:
- aktualizace signatury
- Restartování
- ruční zásah
- Úplná kontrola
- Další stavy agentů vyžadujících zásah

Sestava podrobností pro jednotlivé kategorie stavu uvádí jednotlivé počítače, které vyžadují pozornost, nebo ty, které se hlásí jako **čisté**.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Nové nastavení ochrany osobních údajů pro omezení zařízení <!--1308926 -->
Pro zařízení jsou nyní k dispozici [dvě nová nastavení ochrany osobních údajů](../configuration/device-restrictions-windows-10.md#privacy) :
- **Publikování aktivit uživatelů**: tuto možnost nastavte na **blokovat** , pokud chcete zabránit sdíleným prostředím a zjišťování naposledy použitých prostředků v přepínání úloh.
- **Pouze místní aktivity**: tuto možnost nastavte na **blokovat** , pokud chcete zabránit sdíleným prostředím a zjišťování naposledy použitých prostředků v přepínání úloh na základě místních aktivit.

#### <a name="new-settings-for-the-microsoft-edge-browser---1469166---"></a>Nová nastavení pro prohlížeč Microsoft Edge <!--1469166 -->
Pro zařízení s prohlížečem Microsoft Edge jsou teď k dispozici [dvě nová nastavení](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser) : **cesta k souboru oblíbených položek** a **změny oblíbených položek**.

### <a name="app-management"></a>Správa aplikací

#### <a name="protocol-exceptions-for-applications---1035509---"></a>Výjimky protokolu pro aplikace <!--1035509 -->

Nyní můžete vytvořit výjimky zásad přenosu dat ve správě mobilních aplikací (MAM) Intune a otevřít tak konkrétní nespravované aplikace. Takové aplikace musí být pro ně důvěryhodné. Kromě vytvořených výjimek se přenos dat pořád omezuje na aplikace, které jsou spravované pomocí Intune, když jsou zásady přenosu dat nastavené **jenom na spravované aplikace**. Omezení můžete vytvořit pomocí protokolů (iOS) nebo balíčků (Android).

Například můžete přidat balíček WebEx jako výjimku pro zásady přenosu dat MAM. To umožní, aby se odkazy WebEx ve spravované outlookové e-mailové zprávě otevíraly přímo v aplikaci WebEx. Přenos dat bude i nadále omezen v jiných nespravovaných aplikacích. Další informace najdete v tématu [výjimky zásad přenosu dat pro aplikace](../apps/app-protection-policies-exception.md).

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Zašifrovaná data Windows Information Protection (nedokončená výroba) ve výsledcích hledání ve Windows <!-- 1469193 -->
Nastavení v zásadách Windows Information Protection (nedokončené výroby) teď umožňuje určit, jestli se mají ve výsledcích hledání ve Windows zahrnout data zašifrovaná z výroby. Nastavte tuto možnost Zásady ochrany aplikací tak, že vyberete možnost **dovolit službě Windows Search indexer vyhledat šifrované položky** v části **Upřesnit nastavení** zásady Windows Information Protection. Zásady ochrany aplikací musí být nastavené na platformu *Windows 10* a **stav registrace** zásady aplikace musí být nastavený na **registraci**. Další informace najdete v tématu [Povolení vyhledávání šifrovaných položek ve Windows Search indexerem](../apps/windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Konfigurace automaticky aktualizované mobilní aplikace MSI <!-- 1740840 -->
Můžete nakonfigurovat známou automaticky aktualizovanou mobilní aplikaci MSI, aby ignorovala proces kontroly verzí. Tato možnost se hodí k tomu, abyste se vyhnuli sporům. K tomuto typu konfliktu časování může například dojít, když aplikaci automaticky aktualizuje vývojář aplikace a aktualizuje ji Intune. Obě se můžou pokusit vyhovět verzi aplikace na klientovi Windows, což může způsobit konflikt. Pro tyto automaticky aktualizované aplikace MSI můžete v okně **informace o aplikaci** nakonfigurovat nastavení **Ignorovat verzi aplikace** . Pokud je toto nastavení přepnuto na **Ano**, Microsoft Intune bude ignorovat verzi aplikace nainstalovanou na klientovi Windows.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Související sady licencí aplikací podporovaných v Intune <!-- 1864117 -->
Intune v Azure Portal teď podporuje související sady licencí aplikací jako jednu položku aplikace v uživatelském rozhraní. Kromě toho se všechny licencované aplikace, které jsou synchronizované z Microsoft Store pro firmy, konsolidují do jedné položky aplikace a všechny podrobnosti nasazení z jednotlivých balíčků se migrují do jediného záznamu. Pokud chcete zobrazit související sady licencí aplikací v Azure Portal, vyberte **licence aplikací** v okně **klientské aplikace** .

### <a name="device-configuration"></a>Konfigurace zařízení
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Přípony souborů Windows Information Protection (nedokončené výroby) pro automatické šifrování <!-- 1463582 -->
Nastavení v zásadách Windows Information Protection (nedokončené výroby) teď umožňuje určit, které přípony souborů se při kopírování ze sdílené složky SMB (Server Message Block) v rámci hranice podniku, jak jsou definované v zásadě nedokončené výroby, automaticky šifrují.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Konfigurace nastavení účtu prostředku pro Surface Hub

Teď můžete vzdáleně nakonfigurovat nastavení účtu prostředku pro Surface Hub.

Účet prostředku používá Surface Hub k ověřování proti Skypu nebo Exchangi, aby se mohl připojit ke schůzce.
Budete chtít vytvořit jedinečný účet zdroje, aby se Surface Hub mohl zobrazit na schůzce jako konferenční místnost.
Například účet zdroje, jako je například **konferenční místnost B41/6233**.

> [!NOTE]
> - Pokud pole necháte prázdné, přepíšete dříve nakonfigurované atributy na zařízení.
>
> - Vlastnosti účtu prostředku se můžou na Surface Hub dynamicky měnit. Například pokud je zapnuté otočení hesla. Proto je možné, že hodnoty v konzole Azure budou nějakou dobu trvat, aby odrážely realitu na zařízení.
>
>   Chcete-li zjistit, co je v Surface Hub aktuálně nakonfigurováno, mohou být informace o účtu prostředku zahrnuty v inventáři hardwaru (což již má 7 dní) nebo jako vlastnosti jen pro čtení. Chcete-li zvýšit přesnost po provedení vzdálené akce, můžete získat stav parametrů ihned po spuštění akce aktualizace účtu nebo parametrů na Surface Hub.

##### <a name="attack-surface-reduction"></a>Omezení možností útoku

|Název nastavení  |Nastavení možností  |Popis  |
|---------|---------|---------|
|Zpracování obsahu spustitelného souboru chráněného heslem z e-mailu|Blokovat, audit, Nenakonfigurováno|Zabránit spuštění spustitelných souborů chráněných heslem stažených přes e-mail|
|Rozšířená ochrana ransomwarem|Povoleno, audit, Nenakonfigurováno|Použijte agresivní ransomwarem Protection.|
|Označení krádeže přihlašovacích údajů ze subsystému místního úřadu zabezpečení systému Windows|Povoleno, audit, Nenakonfigurováno|Označení krádeže přihlašovacích údajů ze subsystému místního úřadu zabezpečení systému Windows (Lsass. exe).|
|Vytváření procesů z příkazů PSExec a WMI|Blokovat, audit, Nenakonfigurováno|Blokuje vytváření procesů, které pocházejí z příkazů PSExec a WMI.|
|Nedůvěryhodné a nepodepsané procesy, které se spouštějí z USB|Blokovat, audit, Nenakonfigurováno|Zablokovat nedůvěryhodné a nepodepsané procesy, které se spouštějí z USB.|
|Spustitelné soubory, které nesplňují kritéria prevalence, stáří nebo seznamu důvěryhodných souborů|Blokovat, audit, Nenakonfigurováno|Zablokovat spouštění spustitelných souborů, pokud nesplňují kritéria prevalence, stáří nebo seznamu důvěryhodných souborů.|

##### <a name="controlled-folder-access"></a>Řízený přístup ke složkám

|              Název nastavení               |                                                              Nastavení možností                                                              | Popis |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Ochrana složky (již implementováno) | Nenakonfigurováno, povolit, pouze audit (již implementováno)<br><br> <strong>New</strong><br>Zablokovat úpravu disku, auditovat úpravu disku |             |

Chránit soubory a složky před neoprávněnými změnami nepřátelskými aplikacemi<br><br>**Povolit**: zabránit nedůvěryhodným aplikacím v úpravách nebo odstraňování souborů v chráněných složkách a z zápisu do sektorů disku.<br><br>
**Zablokovat pouze změny disku**:<br>Blokuje nedůvěryhodné aplikace v zápisu do sektorů disku. Nedůvěryhodné aplikace mohou i nadále upravovat nebo odstraňovat soubory v chráněných složkách. |

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Přidání nastavení zabezpečení systému pro zásady dodržování předpisů pro Windows 10 a novější <!--1704133-->

K dispozici jsou teď dodatky nastavení dodržování předpisů pro Windows 10, včetně vyžadování brány firewall a antivirové ochrany v programu Windows Defender.

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>Podpora pro offline aplikace z Microsoft Store pro firmy <!--1222672-->
Offline aplikace, které jste zakoupili v Microsoft Store pro firmy, se teď synchronizují s Azure Portal. Tyto aplikace můžete nasadit na skupiny zařízení nebo skupiny uživatelů. Offline aplikace se instalují přes Intune, a ne do Storu.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Zabránit koncovým uživatelům v ručním přidávání a odebírání účtů v pracovním profilu <!-- 1728700 -->

Když nasadíte aplikaci Gmail do profilu Android for Work, teď můžete koncovým uživatelům zabránit v ručním přidávání a odebírání účtů v pracovním profilu pomocí nastavení **Přidat a odebrat účty** v profilu omezení pro zařízení s Androidem for Work.

<!-- ########################## -->
## <a name="january-2018"></a>Leden 2018

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Výstrahy na tokeny a tokeny, jejichž platnost brzy vyprší <!-- 1639263 -->
Stránka Přehled teď zobrazuje upozornění na tokeny, jejichž platnost vypršela, a tokeny, jejichž platnost brzy vyprší. Když kliknete na výstrahu pro jeden token, přejdete na stránku s podrobnostmi o tokenu.  Pokud kliknete na výstrahu s více tokeny, přejdete na seznam všech tokenů s jejich stavem. Správci by měli obnovit své tokeny před datem vypršení platnosti.

### <a name="device-management"></a>Správa zařízení

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>Podpora vzdáleného příkazu Erase pro zařízení macOS <!-- 1438084 -->

Správci můžou vzdáleně vydávat příkaz k vymazání pro zařízení macOS.

> [!IMPORTANT]
> Příkaz erase nejde vrátit zpět a měl by se používat opatrně.

Příkaz erase odebere ze zařízení všechna data, včetně operačního systému. Také zařízení odebere ze správy Intune. Uživateli není vydáno žádné upozornění a mazání probíhá ihned po vystavení příkazu.

Je nutné nakonfigurovat kód PIN pro obnovení na 6 číslic. Pomocí tohoto kódu PIN se dá odemknout smazáné zařízení, ve kterém se začne přeinstalovat operační systém. Po zahájení mazání se PIN kód zobrazí ve stavovém řádku v okně s přehledem zařízení v Intune. KÓD PIN zůstane tak dlouho, dokud se mazání provede. Po vymazání se zařízení zcela zmizí ze správy Intune. Nezapomeňte si poznamenat kód PIN pro obnovení, aby mohl i ten, který zařízení obnovuje, ho může používat.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Odvolání licencí pro token Volume purchase program pro iOS <!-- 820870 -->
Pro daný token VPP můžete odvolat licenci všech aplikací programu Volume purchase program (VPP) pro iOS.

### <a name="app-management"></a>Správa aplikací

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Odvolávání aplikací pro iOS Volume purchase program  <!-- 820863 -->
Pro dané zařízení, které má jednu nebo více aplikací pro iOS Volume purchase program (VPP), můžete odvolat přidruženou licenci aplikace založenou na zařízeních pro zařízení. Odvolání licence aplikace neodebere ze zařízení související aplikaci VPP. Chcete-li odinstalovat aplikaci VPP, je nutné změnit akci přiřazení pro **odinstalaci**. Další informace najdete v tématu [Správa aplikací pro iOS zakoupených prostřednictvím programu hromadného nákupu s Microsoft Intune](../apps/vpp-apps-ios.md).

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Přiřazení mobilních aplikací Office 365 k zařízením s iOS a Androidem pomocí integrovaného typu aplikace <!-- 1332318 -->
**Integrovaný** typ aplikace usnadňuje vytváření a přiřazování aplikací Office 365 zařízením s iOS a Androidem, která spravujete. Mezi tyto aplikace patří aplikace 0365, jako je Word, Excel, PowerPoint a OneDrive. K typu aplikace můžete přiřadit konkrétní aplikace a upravit konfiguraci informací o aplikaci.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Zahrnutí a vyloučení přiřazení aplikací na základě skupin <!-- 1406920 -->

Během přiřazování aplikací a po výběru typu přiřazení můžete vybrat skupiny, které se mají zahrnout, a také skupiny, které se mají vyloučit.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>Zásady konfigurace aplikací můžete přiřadit skupinám tak, že zahrnete a vyjmete jejich přiřazení.  <!-- 1480316 -->

Zásadu konfigurace aplikace můžete přiřadit skupině uživatelů a zařízení pomocí kombinace zahrnutí a vyloučení přiřazení. Přiřazení lze zvolit jako vlastní výběr skupin nebo jako virtuální skupinu. Virtuální skupina může zahrnovat **všechny uživatele**, **všechna zařízení**nebo **všechny uživatele a všechna zařízení**.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Podpora pro zásady upgradu edice Windows 10   <!-- 903672(archived), 1119689 -->  
Můžete vytvořit zásady upgradu edice Windows 10, které upgradují zařízení s Windows 10 na vzdělávání Windows 10, Windows 10 pro Windows 10, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional vzdělávání a Windows 10 Professional pro vzdělávání N. Podrobnosti o upgradech edice Windows 10 najdete v článku [jak nakonfigurovat upgrady edice Windows 10](../configuration/edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Zásady podmíněného přístupu pro Intune jsou dostupné jenom z Azure Portal  <!-- 1737088 1634311 -->

Od této verze musíte nakonfigurovat a spravovat zásady podmíněného přístupu v [Azure Portal](https://portal.azure.com) od **Azure Active Directory** **podmíněný přístup** > . Pro usnadnění přístupu k tomuto oknu můžete získat přístup také z Intune v Azure Portal v **Intune** > **podmíněný přístup**.

#### <a name="updates-to-compliance-emails---1637547---"></a>Aktualizace e-mailů dodržování předpisů <!--1637547 -->

Když se pošle e-mail, aby nahlásil zařízení, které nedodržuje předpisy, zahrne se podrobnosti o zařízení, které nedodržuje předpisy.

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Nová funkce pro akci vyřešit pro zařízení s Androidem <!--1583480-->

Aplikace Portál společnosti pro Android rozbalí akci vyřešit a **aktualizuje nastavení zařízení** , aby vyřešila [problémy s šifrováním zařízení](/intune-user-help/encrypt-your-device-android).

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Vzdálené uzamčení dostupné v aplikaci Portál společnosti pro Windows 10 <!--676506-->
Koncoví uživatelé teď můžou svoje zařízení vzdáleně zamknout z aplikace Portál společnosti pro Windows 10. Tato akce se nebude zobrazovat pro místní zařízení, které aktivně používají.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Jednodušší řešení potíží s dodržováním předpisů pro Portál společnosti aplikaci pro Windows 10 <!--676546-->
Koncoví uživatelé, kteří mají zařízení s Windows, budou moct v aplikaci Portál společnosti klepnout na důvod nedodržení předpisů. Pokud je to možné, přejdou je přímo do správného umístění v aplikaci nastavení, aby se problém vyřešil.

<!-- ########################## -->
## <a name="december-2017"></a>Prosince 2017

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Nové nastavení automatického opětovného nasazení <!-- 1469168 -->
Nastavení **automatického** opětovného nasazení umožňuje uživatelům s právy správce odstranit všechna uživatelská data a nastavení pomocí **kombinace kláves Ctrl + Win + R** na zamykací obrazovce zařízení. Zařízení se automaticky překonfiguruje a znovu zaregistruje do správy. Toto nastavení najdete v části omezení zařízení s Windows 10 > > Obecné > automatické opětovné nasazení. Podrobnosti najdete v tématu [Nastavení omezení pro zařízení s Windows 10 v Intune](../configuration/device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Podpora pro další zdrojové edice v zásadách upgradu edice Windows 10  <!-- 903672,  1119689 -->
Teď můžete použít zásady upgradu edice Windows 10 k upgradu z dalších edic Windows 10 (Windows 10 pro, Windows 10 pro pro vzdělávání, Cloud Windows 10 atd.). Před touto verzí byly podporované cesty upgradu edice s větším omezením. Podrobnosti najdete v článku [jak nakonfigurovat upgrady edice Windows 10](../configuration/edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Nové nastavení profilu konfigurace zařízení Security Center Windows Defenderu (WDSC) <!-- 1335507 -->

Intune přidá novou část nastavení profilu konfigurace zařízení pod Endpoint Protection s názvem **Security Center Windows Defender**. Správci IT můžou nakonfigurovat, ke kterým pilířům aplikace Security Center v programu Windows Defender mají přístup koncoví uživatelé. Pokud správce IT skryje pilíř v aplikaci Security Center Windows Defender, všechna oznámení týkající se skrytého pilíře se nezobrazují na zařízení uživatele.

Správci sloupků se můžou skrýt v nastavení profilu konfigurace zařízení Security Center programu Windows Defender:
- Ochrana před viry a hrozbami
- Výkon a stav zařízení
- Brána firewall a ochrana sítě
- Řízení aplikací a prohlížečů
- Možnosti řady

Správci IT můžou také přizpůsobit, která oznámení obdrží uživatelé. Můžete například nakonfigurovat, zda uživatelé obdrží všechna oznámení vygenerovaná viditelnými pilíři v WDSC nebo pouze kritická oznámení. Nekritická oznámení zahrnují pravidelné souhrny aktivity antivirové ochrany v programu Windows Defender a oznámení o dokončení kontroly. Všechna ostatní oznámení se považují za kritická. Kromě toho můžete také přizpůsobit samotný obsah oznámení, například můžete zadat kontaktní informace oddělení IT, které se mají vložit do oznámení, která se zobrazí na uživatelských zařízeních.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Podpora více konektorů pro zpracování certifikátů SCEP a PFX <!-- 1361755 -->

Zákazníci, kteří používají místní konektor NDES k doručování certifikátů do zařízení, teď můžou nakonfigurovat více konektorů v jednom tenantovi.

Tato nová funkce podporuje následující scénář:

- **Vysoká dostupnost**

Každý konektor NDES vyžádá žádosti o certifikát z Intune.  Pokud jeden konektor NDES přejde do režimu offline, může druhý konektor pokračovat ve zpracování požadavků.

#### <a name="customer-subject-name-can-use-aad_device_id-variable-----1468599---"></a>Název subjektu zákazníka může používat AAD_DEVICE_ID proměnnou.  <!-- 1468599 -->

Při vytváření profilu certifikátu SCEP v Intune teď můžete při vytváření vlastního názvu subjektu použít proměnnou AAD_DEVICE_ID.   Když se certifikát vyžádá pomocí tohoto profilu SCEP, nahradí se tato proměnná číslem ID zařízení AAD zařízení, které žádost o certifikát vydává.


### <a name="device-management"></a>Správa zařízení

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Správa zařízení macOS zaregistrovaných v Jamf s modulem dodržování předpisů pro zařízení v Intune <!-- 1592747 -->
Teď můžete použít Jamf k posílání informací o stavu zařízení macOS do Intune. tím se pak vyhodnotí pro dodržování zásad definovaných v konzole Intune. V závislosti na stavu dodržování předpisů zařízením a dalších podmínkách (například umístění, riziko pro uživatele atd.) bude podmíněný přístup vymáhat dodržování předpisů pro zařízení macOS s přístupem k cloudovým a místním aplikacím připojeným k Azure AD, včetně Office 365. Přečtěte si další informace o [Nastavení integrace Jamf](../protect/conditional-access-integrate-jamf.md) a [vynucování dodržování předpisů pro zařízení spravovaná Jamf](../protect/conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Nová akce zařízení s iOS   <!-- 1424701 -->

Teď můžete vypnout zařízení se systémem iOS 10,3 pod dohledem. Tato akce vypne zařízení hned bez upozornění koncovému uživateli. Akci **vypnout (jenom pod dohledem)** najdete ve vlastnostech zařízení, když vyberete zařízení v úloze **zařízení** .

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Zakázat změny data a času u zařízení se zabezpečením Samsung KNOX <!-- 1468103 -->

Přidali jsme novou funkci, která umožňuje zablokovat změny data a času na zařízeních se systémem Samsung KNOX. Najdete ho v **profilech konfigurace zařízení**@no__tch**omezení zařízení (Android)**  > **Obecné**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Surface Hub podporovaný účet prostředku <!-- 1566442  -->

Byla přidána nová akce zařízení, aby správci mohli definovat a aktualizovat účet zdroje přidružený k Surface Hub.

Účet prostředku používá Surface Hub k ověření pomocí Skypu nebo Exchange, aby se mohl připojit ke schůzce. Můžete vytvořit jedinečný účet zdroje, aby se Surface Hub na schůzi jako konferenční místnost. Účet prostředku se například může zobrazit jako *konferenční místnost B41/6233*. Účet prostředku (označovaný jako účet zařízení) pro Surface Hub obvykle musí být nakonfigurovaný pro umístění konferenční místnosti a pokud je potřeba změnit jiné parametry účtu prostředku.

Když správci chtějí aktualizovat účet prostředku v zařízení, musí zadat aktuální přihlašovací údaje služby Active Directory nebo Azure Active Directory přidružené k tomuto zařízení. Pokud je pro zařízení zapnuté otočení hesla, musí správci přejít na Azure Active Directory a najít heslo.

> [!NOTE]
> Všechna pole se odešlou ve svazku a přepíší se všechna dříve nakonfigurovaná pole. Prázdná pole také přepíší existující pole.

Tato nastavení můžou nakonfigurovat správci:

- **Účet prostředku**
  - **Uživatel služby Active Directory**

    Název_domény \ uživatelské_jméno nebo hlavní název uživatele (UPN): user@domainname.com

  - **Heslo**

- **Volitelné parametry účtu zdroje** (musí být nastavené pomocí zadaného účtu prostředku)

  - **Období rotace hesla**

    Zajistí, aby se heslo účtu automaticky aktualizovalo Surface Hub každý týden z bezpečnostních důvodů. Chcete-li nakonfigurovat parametry po povolení tohoto nastavení, musí mít účet v Azure Active Directory nejprve resetování hesla.

  - **Adresa protokolu SIP (protokol iniciace relace)**

    Používá se pouze v případě, že se automatické zjišťování nezdařilo.

  - **E-mail**

    E-mailová adresa účtu zařízení/prostředku

  - **Server Exchange**

    Vyžaduje se jenom v případě, že se nezdařila operace automatického zjišťování.

  - **Synchronizace kalendáře**

    Určuje, jestli jsou povolené synchronizace kalendáře a další služby Exchange serveru. Například: schůzka synchronizace.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Instalace aplikací Office na zařízení macOS <!-- 1494311 -->
Teď budete moct aplikace Office instalovat na zařízení macOS. Tento nový typ aplikace vám umožní nainstalovat Word, Excel, PowerPoint, Outlook a OneNote. Tyto aplikace se také dodávají s nástrojem Microsoft AutoUpdate (MAU), které vám pomůžou zajistit zabezpečení a aktuálnost vašich aplikací.

### <a name="app-management"></a>Správa aplikací

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Odstranění tokenu programu Volume purchase program pro iOS <!-- 820879 -->
Pomocí konzoly nástroje můžete odstranit token programu Volume purchase program (VPP) pro iOS. To může být nutné v případě, že máte duplicitní instance tokenu VPP.

### <a name="intune-apps"></a>Aplikace Intune


### <a name="role-based-access-control"></a>Řízení přístupu založené na rolích

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Nová kolekce entit s názvem aktuální uživatel je omezena na aktuálně aktivní uživatelská data. <!-- 1667026 -->

Kolekce entit **Uživatelé** obsahuje všechny uživatele Azure Active Directory (Azure AD) s přiřazenými licencemi ve vašem podniku. Uživatel může například přidat do Intune a pak ho v průběhu posledního měsíce odebrat. I když tento uživatel není v době, kdy se jedná o zprávu, přítomen v datech, je k dispozici uživatel a stav. Můžete vytvořit sestavu, která by zobrazila dobu trvání historické přítomnosti uživatele ve vašich datech.

Nová kolekce entit **aktuální uživatel** naopak obsahuje pouze uživatele, kteří nebyli odebráni. Kolekce entit **aktuální uživatel** obsahuje pouze aktuálně aktivní uživatele. Informace o kolekci entit **aktuální uživatel** najdete v tématu [referenční informace pro entitu aktuální uživatel](../developer/reports-ref-data-model.md).

### <a name="updated-graph-apis----1736360---"></a>Aktualizovaná rozhraní API grafu <!-- 1736360 -->

V této verzi jsme aktualizovali několik Graph API pro Intune, které jsou ve verzi beta. Další informace najdete v měsíčním protokolu [změn Graph API](https://developer.microsoft.com/graph/docs/concepts/changelog) .

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Intune podporuje aplikace Windows Information Protection (NV) – odepřené. <!-- 1479103 -->
V Intune můžete zadat zakázané aplikace. Pokud dojde k odepření aplikace, zablokuje se přístup k firemním informacím, takže se v seznamu povolených aplikací bude efektivně napisovat. Další informace najdete v tématu [doporučený seznam odepření pro Windows Information Protection](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).

<!-- ########################## -->
## <a name="november-2017"></a>Listopadu 2017

### <a name="troubleshoot-enrollment-issues-----746324---"></a>Řešení potíží s registrací  <!-- 746324 -->

Pracovní prostor pro **řešení potíží** teď zobrazuje problémy s registrací uživatelů. Podrobnosti o problému a navrhované nápravné kroky můžou správcům a operátorům helpdesku pomoct řešit problémy. Některé problémy s registrací nejsou zachyceny a některé chyby nemusí mít návrhy na nápravu.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Omezení registrace přiřazených skupině <!-- 747598 -->

Jako správce Intune teď můžete [pro skupiny uživatelů vytvořit vlastní omezení registrace typu zařízení a omezení počtu zařízení](../enrollment/enrollment-restrictions-set.md).

Azure Portal Intune vám umožňuje vytvořit až 25 instancí každého typu omezení, které pak můžete přiřadit ke skupinám uživatelů. Omezení přiřazená skupině přepisují výchozí omezení.

Všechny instance typu omezení se udržují v přesně seřazeném seznamu. Toto pořadí definuje hodnotu priority pro řešení konfliktů. Uživatel ovlivněný více než jednou instancí omezení je omezen pouze instancí s nejvyšší hodnotou priority. Prioritu dané instance můžete změnit přetažením na jiné místo v seznamu.

Tato funkce se uvolní s migrací nastavení Androidu for Work z nabídky registrace Androidu for Work do nabídky omezení registrace. Vzhledem k tomu, že tato migrace může trvat několik dní, může být váš účet upgradován pro jiné části listopadu vydané verze, než se v případě omezení registrace zpřístupní přiřazení skupiny.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Podpora více konektorů služby zápisu síťových zařízení (NDES) <!-- 1528104 -->

NDES umožňuje mobilním zařízením, která běží bez přihlašovacích údajů k doméně, získat certifikáty založené na Simple Certificate Enrollment Protocol (SCEP).
V této aktualizaci jsou podporovány více konektorů NDES.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Správa zařízení s Androidem for Work nezávisle na zařízeních s Androidem <!-- 1490731 EEready-->

Intune podporuje správu registrace zařízení s Androidem for Work nezávisle na platformě Android. Tato nastavení se spravují v části **registrace zařízení** > **omezení registrace** > **omezení typu zařízení**. (Dříve se nacházely v části **registrace zařízení** > **registrace Androidu for Work** > **Nastavení registrace Androidu for Work**.)

Ve výchozím nastavení jsou nastavení zařízení s Androidem for Work stejná jako nastavení pro zařízení s Androidem. Po změně nastavení Androidu for Work se však již nejedná o případ.

Pokud zablokujete registraci osobních zařízení s Androidem for Work, můžou se jako Android for Work zaregistrovat jenom firemní zařízení s Androidem.

Při práci s novými nastaveními Vezměte v úvahu následující body:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Pokud jste ještě nikdy nepřipojili registraci Androidu for Work

Nová platforma Android for Work je zablokovaná ve výchozím omezení typu zařízení. Po zprovoznění funkce můžete zařízením dovolit, aby se zaregistrovala v Androidu for Work. Provedete to tak, že změníte výchozí omezení typu zařízení nebo vytvoříte nové omezení typu zařízení, které nahradí výchozí omezení typu zařízení.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Pokud máte registraci Androidu for Work

Pokud jste se už dřív připojili, záleží na nastavení, které jste zvolili:

| Nastavení | Stav Androidu for Work ve výchozím omezení typu zařízení | Poznámky |
| --- | --- | --- |
| **Spravovat všechna zařízení jako Android** | Blokované | Všechna zařízení s Androidem se musí zaregistrovat bez Androidu for Work. |
| **Spravovat podporovaná zařízení jako Android for Work** | Povolené | Všechna zařízení s Androidem, která podporují Android for Work, se musí zaregistrovat v Androidu for Work. |
| **Spravovat podporovaná zařízení pro uživatele v těchto skupinách jako Android for Work** | Blokované | Byla vytvořena samostatná zásada omezení typu zařízení pro přepsání výchozí hodnoty. Tato zásada definuje skupiny, které jste dříve vybrali pro povolení registrace Androidu for Work. Uživatelům ve vybraných skupinách bude nadále povoleno registrovat svá zařízení s Androidem for Work. Všichni ostatní uživatelé budou mít při registraci v Androidu for Work omezený přístup. |

Ve všech případech se vaše zamýšlené nařízení zachová. V rámci vaší strany není nutné provádět žádnou akci, aby bylo možné zachovat globální nebo místní příspěvek pro Android for Work ve vašem prostředí.

### <a name="google-play-protect-support-on-android----908720---"></a>Google Play chránit podporu pro Android <!-- 908720 -->

S vydáním Androidu Oreo zavádí Google sadu funkcí zabezpečení, které se nazývají Google Play chránit, které umožňují uživatelům a organizacím spouštět zabezpečené aplikace a zabezpečené image pro Android. Intune teď podporuje Google Play ochraně funkcí, včetně vzdáleného ověření identity SafetyNet. Správci můžou nastavit požadavky na zásady dodržování předpisů, které vyžadují, aby byla nakonfigurovaná a v dobrém stavu Google Play chránit.
Nastavení **ověření zařízení SafetyNet** vyžaduje, aby se zařízení připojilo ke službě Google, aby ověřilo, jestli je zařízení v pořádku a není ohrožené. Správci mohou také nastavit konfigurační profil pro Android for Work, aby vyžadoval, aby byly nainstalované aplikace ověřeny službou Google Play Services. Pokud zařízení nedodržuje předpisy Google Play chránit požadavky, může podmíněný přístup zablokovat uživatelům přístup k podnikovým prostředkům.

- Naučte se [vytvářet zásady dodržování předpisů pro zařízení, které umožňují Google Play chránit](../protect/compliance-policy-create-android.md).

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Povolený textový protokol ze spravovaných aplikací <!-- 1414050  -->

Aplikace spravované sadou Intune App SDK můžou odesílat zprávy SMS.


### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Sestava instalace aplikace se aktualizovala tak, aby obsahovala stav čeká na instalaci. <!-- 1249446 -->  

Sestava **stav instalace aplikace** dostupná pro každou aplikaci v seznamu **aplikací** v úloze **klientské aplikace** teď obsahuje počet **probíhajících instalací** pro uživatele a zařízení.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>rozhraní API inventáře aplikace iOS 11 pro detekci mobilních hrozeb <!-- 1391759 -->

Intune shromažďuje informace o inventáři aplikací z osobních zařízení i ze zařízení vlastněných firmou a zpřístupňuje je pro poskytovatele MTD (Mobile Threat Detection) k načtení, jako je například Lookout for Work. Inventář aplikací můžete shromáždit od uživatelů zařízení se systémem iOS 11 +.

**Inventář aplikací**  
K poskytovateli služeb MTD se odešlou inventáře z firemního zařízení iOS 11 + i v osobním vlastnictví. Data v inventáři aplikací zahrnují:

- ID aplikace
- Verze aplikace
- Krátká verze aplikace
- Název aplikace
- Velikost sady prostředků aplikace
- Dynamická velikost aplikace
- Aplikace je ověřená nebo ne.
- Aplikace je spravovaná nebo ne.

### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Migrace hybridních uživatelů a zařízení MDM do samostatného Intune <!-- 1463747 wnready -->
Nyní jsou k dispozici nové procesy a nástroje pro přesun uživatelů a jejich zařízení z hybridního MDM do Intune v Azure Portal, což vám umožní provádět následující úlohy:
- Kopírování zásad a profilů z konzoly Configuration Manager do Intune v Azure Portal
- Přesunutí podmnožiny uživatelů do Intune v Azure Portal a zachování zbytku v hybridní MDM
- Migrace zařízení do Intune v Azure Portal, aniž byste je museli znovu zaregistrovat

Podrobnosti najdete v tématu [migrace hybridních uživatelů a zařízení MDM do samostatného Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Podpora vysoké dostupnosti místního Exchange Connectoru  <!-- 676614 -->
Když Exchange Connector vytvoří připojení k Exchangi pomocí zadaného serveru Client Access Server (CAS), konektor teď má možnost zjišťovat další servery CAS. Pokud primární certifikační autorita přestane být dostupná, konektor převezme služby při selhání jiné certifikační autority, pokud je k dispozici, dokud nebudou primární CA k dispozici. Podrobnosti najdete v tématu [podpora vysoké dostupnosti v místním Exchange Connectoru](../protect/exchange-connector-install.md#on-premises-intune-exchange-connector-high-availability-support).

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Vzdáleně restartovat zařízení s iOS (jenom pod dohledem) <!-- 1424595 -->

Teď můžete aktivovat zařízení s iOS 10.3 + pod dohledem a restartovat ho pomocí akce zařízení. Další informace o použití akce restartování zařízení najdete v tématu [vzdálené restartování zařízení s Intune](../remote-actions/device-restart.md).

> [!Note]
> Tento příkaz vyžaduje zařízení pod dohledem a přístupová práva k **zámku zařízení** . Zařízení se restartuje hned. Zařízení s iOS, která jsou zamčená heslem, se po restartování znovu nepřipojí k síti Wi-Fi. Po restartování nemusí být schopni komunikovat se serverem.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Podpora jednotného přihlašování pro iOS <!-- 1333645 -->  

Pro uživatele iOS můžete použít jednotné přihlašování. Aplikace pro iOS, které jsou kódované tak, aby hledaly přihlašovací údaje uživatele v datové části jednotného přihlašování, jsou funkční s touto aktualizací konfigurace datové části. K nakonfigurování hlavního názvu a sféry můžete použít také hlavní název uživatele (UPN) a ID zařízení v Intune. Podrobnosti najdete v tématu [Konfigurace služby Intune pro jednotné přihlašování zařízení s iOS](../configuration/ios-device-features-settings.md#single-sign-on).

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Přidat "Najít iPhone" pro osobní zařízení <!--1427287-->
Teď si můžete zobrazit, jestli Zámek aktivace zařízení s iOS zapnutá. Tuto funkci najdete dřív v Intune na klasickém portálu.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Vzdálené uzamčení spravovaných zařízení macOS pomocí Intune <!-- 1437691 -->

Můžete uzamknout ztracené zařízení macOS a nastavit kód PIN pro obnovení na 6 číslic. Když se uzamkne, zobrazí se v okně **Přehled zařízení** kód PIN, dokud se nepošle jiná akce zařízení.

Další informace najdete v tématu [vzdálené uzamčení spravovaných zařízení v Intune](../remote-actions/device-remote-lock.md).

### <a name="new-scep-profile-details-supported----1559808---"></a>Jsou podporovány nové podrobnosti profilu SCEP <!-- 1559808 -->

Správci teď můžou při vytváření profilu SCEP na platformách Windows, iOS, macOS a Androidu nastavit další nastavení.  Správci můžou nastavit IMEI, sériové číslo nebo běžný název včetně e-mailu ve formátu názvu subjektu.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

### <a name="retain-data-during-a-factory-reset----1588489---"></a>Zachovat data při obnovení továrního nastavení  <!--1588489 -->
Při obnovení továrního nastavení Windows 10 verze 1709 a novější je k dispozici nová funkce. Správci můžou určit, jestli se registrace zařízení a další zřízená data v zařízení zachovají prostřednictvím obnovení továrního nastavení.

Při obnovení továrního nastavení se zachovají následující data:
- Uživatelské účty přidružené k zařízení
- Stav počítače (připojení k doméně, Azure Active Directory – připojeno)
- Registrace MDM
- Nainstalované aplikace OEM (aplikace pro Store a Win32)
- Profil uživatele
- Uživatelská data mimo profil uživatele
- Automatické přihlašování uživatele

Následující data nejsou zachována:
- Uživatelské soubory
- Aplikace nainstalované uživatelem (aplikace pro Store a Win32)
- Jiné než výchozí nastavení zařízení


### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Zobrazí se přiřazení aktualizačního kruhu Window 10. <!-- 1621837 -->
Při **řešení potíží** pro uživatele, který si prohlížíte, si můžete prohlédnout jakákoli přiřazení aktualizačních kanálů Windows 10.  

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Nastavení četnosti vytváření sestav rozšířené ochrany před internetovými útoky v programu Windows Defender  <!-- 1455974  -->
Služba Rozšířená (Windows Defender Advanced Threat Protection) umožňuje správcům spravovat četnost generování sestav pro spravovaná zařízení. Díky nové možnosti **četnosti hlášení TELEMETRIE** rozšířená shromažďuje data a častěji vyhodnocuje rizika. Výchozí hodnota pro vytváření sestav optimalizuje rychlost a výkon. Zvýšení četnosti vytváření sestav může být výhodné pro zařízení s vysokým rizikem. Toto nastavení najdete v profilu ATP v **programu Windows Defender** v části **Konfigurace zařízení**.

### <a name="audit-updates----1412961---"></a>Aktualizace auditu <!-- 1412961 -->  
Auditování Intune poskytuje záznam operací změn souvisejících s Intune.  Všechny operace vytvoření, aktualizace, odstranění a vzdálené úlohy se zaznamenávají a uchovávají po dobu jednoho roku.  Azure Portal poskytuje zobrazení posledních 30 dnů auditních dat v jednotlivých úlohách a lze je filtrovat.  Odpovídající Graph API umožňuje načtení dat auditování uložených za poslední rok.

Auditování se nachází ve skupině **monitorování** . Pro každou úlohu je k dispozici položka nabídky **protokoly auditu** .

### <a name="company-portal-app-for-macos-is-available---1541700--"></a>K dispozici je Portál společnosti aplikace pro macOS. <!--1541700-->
Portál společnosti Intune na macOS má aktualizované prostředí, které je optimalizované pro čistě zobrazení všech informací a oznámení o dodržování předpisů, které uživatelé potřebují pro všechna zařízení, která zaregistrovali. A po nasazení Portál společnosti Intune do zařízení vám Microsoft AutoUpdate for macOS poskytne aktualizace. Novou Portál společnosti Intune pro macOS si můžete stáhnout tak, že se přihlásíte do Portál společnosti Intune webu ze zařízení macOS.

### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Microsoft Planner je teď součástí seznamu schválených aplikací pro správu mobilních aplikací (MAM).  <!-- 1248473 -->
Aplikace Microsoft Planner pro iOS a Android je teď součástí schválených aplikací pro správu mobilních aplikací (MAM). Aplikaci můžete nakonfigurovat pomocí okna Intune App Protection v Azure Portal pro všechny klienty.
- Další informace najdete v [seznamu mam schválených aplikací](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Frekvence aktualizace požadavků sítě VPN podle aplikace na zařízeních s iOS   <!-- 1547061 -->  
Správci teď můžou pro aplikace na zařízeních s iOS odebrat požadavky na síť VPN pro jednotlivé aplikace. ovlivněná zařízení budou po dalším vrácení se změnami Intune, která se většinou vyskytují do 15 minut.  

### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Podpora System Center Operations Manager Management Pack pro Exchange Connector <!-- 885457 -->
K dispozici je teď System Center Operations Manager Management Pack pro Exchange Connector, které vám pomůžou s analýzou protokolů Exchange Connectoru. Tato funkce poskytuje různé možnosti monitorování služby, když potřebujete řešit problémy.

### <a name="co-management-for-windows-10-devices-----1243445---"></a>Společná správa pro zařízení s Windows 10  <!-- 1243445 -->
Spoluspráva je řešení, které poskytuje most z tradičních na moderní správu a poskytuje cestu k převedení pomocí postupného přístupu. Ve své nadaci je společná Správa řešení, kde jsou zařízení s Windows 10 souběžně spravovaná pomocí Configuration Manager a Microsoft Intune a připojená ke službě Active Directory (AD) a Azure Active Directory (Azure AD).  Tato konfigurace poskytuje cestu, která se modernizovat v průběhu času, podle tempa, které je pro vaši organizaci nejvhodnější, pokud nemůžete přesunout vše najednou.  

### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Omezení registrace zařízení s Windows podle verze operačního systému <!-- 245498 -->
Jako správce Intune teď můžete pro registrace zařízení zadat minimální a maximální verzi Windows 10. Tato omezení můžete nastavit v okně **konfigurace platformy** .

Intune bude dál podporovat registraci Windows 8.1 počítačů a telefonů. Pouze verze Windows 10 je však možné nastavit s minimálním a maximálním limitem. Pokud chcete povolit registraci zařízení 8,1, nechte minimální limit prázdný.

### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Výstrahy pro zařízení s nepřiřazeným autopilotem Windows autopilot  <!-- 1631236 -->
K dispozici je nová výstraha pro Nepřiřazená zařízení Windows autopilot na stránce s**přehledem** **Microsoft Intune** > **registrace zařízení** > . Tato výstraha ukazuje, kolik zařízení z programu autopilotu nemají přiřazené profily nasazení autopilotu. Pomocí informací z výstrahy vytvořte profily a přiřaďte je nepřiřazeným zařízením. Když kliknete na výstrahu, zobrazí se úplný seznam zařízení s Windows autopilotem a podrobné informace o nich. Další informace najdete v tématu [registrace zařízení s Windows pomocí programu Windows autopilot Deployment](../enrollment/enrollment-autopilot.md).


### <a name="refresh-button-for-devices-list-------1333581---"></a>Tlačítko Aktualizovat pro seznam zařízení    <!-- 1333581 -->
Vzhledem k tomu, že se seznam zařízení automaticky neaktualizuje, můžete k aktualizaci zařízení, která se zobrazí v seznamu, použít nové tlačítko Aktualizovat.

### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Podpora certifikační autority (CA) Symantec Cloud  <!-- 1333638 -->    
Intune teď podporuje certifikační autoritu Symantec Cloud, která umožňuje konektoru Intune Certificate Connector vystavovat certifikáty PKCS od společnosti Symantec Cloud CA do spravovaných zařízení Intune. Pokud už Intune Certificate Connector používáte s certifikační autoritou (CA) Microsoftu, můžete existující nastavení Intune Certificate Connectoru použít k přidání podpory pro certifikační autoritu Symantec.

### <a name="new-items-added-to-device-inventory-----1404455---"></a>Nové položky přidané do inventáře zařízení   <!--1404455 -->
K dispozici jsou teď tyto nové položky inventáře, které jsou [Vybraná registrovanými zařízeními](../remote-actions/device-inventory.md):

- Adresa MAC pro Wi-Fi
- Celkové místo v úložišti
- Celkové volné místo
- MEID
- Operátor předplatitele

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Nastavení přístupu pro aplikace pomocí minimální opravy zabezpečení Androidu na zařízení<!-- 1278463 -->   
Správce může definovat minimální opravu zabezpečení Androidu, která musí být na zařízení nainstalovaná, aby získal přístup ke spravované aplikaci pod spravovaným účtem.

> [!Note]  
> Tato funkce omezuje jenom opravy zabezpečení vydané službou Google na zařízeních s Androidem 6.0 +.

### <a name="app-conditional-launch-support----1193313---"></a>Podpora podmíněného spuštění aplikace <!-- 1193313 -->
Správci IT teď můžou nastavit požadavek prostřednictvím portálu pro správu Azure k vystavování hesla místo číselného kódu PIN přes správu mobilních aplikací (MAM) při spuštění aplikace. Pokud se nakonfiguruje, musí uživatel nastavit a používat heslo, když se zobrazí výzva, abyste měli přístup k aplikacím MAM-podporou. Heslo je definováno jako číselný kód PIN s alespoň jedním speciálním znakem nebo velkým/malým písmenem. Tato verze Intune tuto funkci povolí **jenom v iOS**. Intune podporuje heslo podobným způsobem jako číselný kód PIN, nastavuje minimální délku a povoluje opakování znaků a sekvencí. Tato funkce vyžaduje zapojení aplikací (tj. WXP, Outlook, Managed Browser, Yammer) a integruje sadu Intune App SDK s kódem pro tuto funkci na místo, aby se nastavení hesla vynutilo v cílových aplikacích.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Číslo verze aplikace pro obchodní zařízení ve zprávě o stavu instalace zařízení <!-- 1233999 -->
V této verzi se v sestavě stav instalace zařízení zobrazuje číslo verze aplikace pro obchodní aplikace pro iOS a Android. Tyto informace můžete použít k řešení potíží s aplikacemi nebo k vyhledání zařízení, na kterých běží zastaralé verze aplikací.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Správci teď můžou nakonfigurovat nastavení brány firewall na zařízení pomocí profilu konfigurace zařízení. <!-- 951708 -->   
Správci můžou zapnout bránu firewall pro zařízení a také nakonfigurovat různé protokoly pro domény, privátní a veřejné sítě.  Tato nastavení brány firewall najdete v profilu "Endpoint Protection".

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Ochrana Application Guard v programu Windows Defender pomáhá chránit zařízení před nedůvěryhodnými weby podle definice vaší organizace. <!-- 958257 -->   
Správci můžou lokality definovat jako "důvěryhodné" nebo "podnikové" pomocí pracovního postupu Windows Information Protection nebo nového profilu "hranice sítě" v části Konfigurace zařízení. Pokud se zobrazují v Microsoft Edge, všechny lokality, které nejsou uvedené 64 na hranici důvěryhodné sítě zařízení s Windows 10, se místo toho otevřou v prohlížeči v rámci virtuálního počítače Hyper-V.

Ochranu Application Guard najdete v profilech konfigurace zařízení v profilu "Endpoint Protection". Odtud můžou správci nakonfigurovat interakci mezi virtualizovaným prohlížečem a hostitelským počítačem, nedůvěryhodnými lokalitami a důvěryhodnými lokalitami a ukládat data vygenerovaná ve virtualizovaném prohlížeči. Aby bylo možné používat ochranu Application Guard na zařízení, musí být nejprve nakonfigurované ohraničení sítě. Je důležité definovat jenom jednu hranici sítě pro zařízení.  

### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Řízení aplikací v programu Windows Defender ve Windows 10 Enterprise poskytuje režim pro důvěřování jenom autorizovaným aplikacím. <!-- 1031096 -->    
Díky detekci tisíců nových škodlivých souborů v každém dni pomocí rozpoznávání založeného na signaturách pomocí antivirové ochrany proti malwaru už nemusí docházet k dostatečné obrany proti novým útokům. Pomocí řízení aplikací v programu Windows Defender ve Windows 10 Enterprise můžete změnit konfiguraci zařízení z režimu, ve kterém jsou aplikace důvěryhodné, pokud nejsou blokované antivirovým programem nebo jiným řešením zabezpečení, do režimu, ve kterém operační systém důvěřuje jenom aplikacím autorizovaným nástrojem. Váš podnik. Důvěřujete aplikacím v řízení aplikací v programu Windows Defender.

Pomocí Intune můžete konfigurovat zásady řízení aplikací v režimu "pouze audit" nebo v režimu prosazování. Aplikace nejsou blokované při spuštění v režimu "pouze audit". Režim "jenom audit" protokoluje všechny události v protokolech místních klientů. Můžete také nakonfigurovat, jestli se smí spouštět jenom součásti Windows a aplikace Microsoft Store, nebo jestli se můžou spouštět i další aplikace s dobrou pověstí, jak je definuje Intelligent Security Graph.

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Ochrana před zneužitím v programu Windows Defender je nová sada funkcí prevence neoprávněných vniknutí pro Windows 10. <!-- 1063615 -->   
Ochrana před zneužitím v programu Windows Defender zahrnuje vlastní pravidla, která omezují zneužití aplikací, zabraňuje hrozbám maker a skriptů, automaticky blokuje síťová připojení k IP adresám s nízkou pověstí a může zabezpečit data z ransomwarem a neznámá. nejnovější. Ochrana před zneužitím v programu Windows Defender se skládá z následujících součástí:

- **Omezení možností útoku** vám poskytne pravidla, která umožňují zabránit hrozbám v makrech, skriptech a e-mailech.
- **Řízený přístup ke složkám** automaticky blokuje přístup k obsahu chráněným složkám.
- **Filtr sítě** blokuje odchozí připojení z libovolné aplikace k IP nebo doméně s malým zástupcem.
- **Ochrana před zneužitím** poskytuje omezení paměti, toku řízení a zásad, které se dají použít k ochraně aplikace před zneužitím.

### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Správa PowerShellových skriptů v Intune pro zařízení s Windows 10 <!-- 790537 -->

Rozšíření pro správu Intune umožňuje do Intune nahrávat skripty PowerShellu pro spouštění na zařízeních s Windows 10. Rozšíření doplňuje možnosti správy mobilních zařízení (MDM) s Windows 10 a usnadňuje přechod na moderní správu. Podrobnosti najdete v tématu [Správa powershellových skriptů v Intune pro zařízení s Windows 10](../apps/intune-management-extension.md).

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nová nastavení omezení pro zařízení s Windows 10      <!-- 1308850 -->
- Zasílání zpráv (jenom mobilní) – zakáže testování nebo zprávy MMS
- Heslo – nastavení pro povolení standardu FIPS a použití sekundárních zařízení zařízení Windows Hello pro ověřování 
- Zobrazení – nastavení pro zapnutí nebo vypnutí škálování GDI pro starší verze aplikací

### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Omezení zařízení v celoobrazovkovém režimu Windows 10 <!-- 1308872 -->   
Uživatele zařízení s Windows 10 můžete omezit na celoobrazovkový režim, který uživatele omezuje na sadu předdefinovaných aplikací.  Provedete to tak, že vytvoříte profil omezení zařízení s Windows 10 a nastavíte nastavení veřejného terminálu.

Celoobrazovkový režim podporuje dva režimy: **jednu aplikaci** (umožňuje uživateli spustit jenom jednu aplikaci) nebo **více aplikací** (povoluje přístup k sadě aplikací).  Definujete uživatelský účet a název zařízení, který určuje podporované aplikace.  Když je uživatel přihlášený, je omezený na definované aplikace.  Další informace najdete v tématu [ASSIGNEDACCESS CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Celoobrazovkový režim vyžaduje:

- Intune musí být Autorita MDM.
- Aplikace už musí být nainstalované na cílovém zařízení.
- Zařízení musí být [správně zřízené](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nový profil konfigurace zařízení pro vytváření hranic sítě <!-- 1311967 -->   
Nový profil konfigurace zařízení nazvaný **hranice sítě** najdete u ostatních profilů konfigurace zařízení. Tento profil použijte k definování online prostředků, které chcete považovat za podnikové a důvěryhodné. Aby bylo možné na zařízení *používat funkce,* jako je například ochrana Application Guard v programu Windows Defender a Windows Information Protection, je nutné definovat hranici sítě pro zařízení. Pro každé zařízení je důležité definovat jenom jednu hranici sítě.

Můžete definovat podnikové cloudové prostředky, rozsahy IP adres a interní proxy servery, které chcete považovat za důvěryhodné. Po definování může být hranice sítě spotřebována jinými funkcemi, jako je například ochrana Application Guard v programu Windows Defender a Windows Information Protection.

### <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Dvě další nastavení pro antivirovou ochranu v programu Windows Defender <!-- 1338409 -->  
**Úroveň blokování souborů**

| | |
|---|---|
| Není nakonfigurováno | **Nenakonfigurováno** používá výchozí úroveň blokování pro antivirovou ochranu v programu Windows Defender a poskytuje silné zjišťování bez zvýšení rizika detekce legitimních souborů. |
| Vysoký | **Vysoká** se aplikuje na silnou úroveň detekce.
| Vysoké +  | **Vysoká +** poskytuje vysokou úroveň s dalšími ochrannými opatřeními, které by mohly mít vliv na výkon klienta.
| Nulová tolerance  | **Nulová tolerance** blokuje všechny neznámé spustitelné soubory. |

V nepravděpodobném případě může nastavení **vysoké** způsobit zjištění některých legitimních souborů.
Doporučujeme nastavit úroveň blokování souborů na výchozí nastavení, **Nenakonfigurováno**.

**Rozšíření časového limitu pro kontrolu souborů v cloudu**  

| | |
|--|--|
| Počet sekund (0-50) | Zadejte maximální dobu, po kterou by antivirová ochrana v programu Windows Defender měla blokovat soubor, když se čeká na výsledek z cloudu. Výchozí hodnota je 10 sekund: do 10 sekund se přidá další čas zadaný tady (až 50 sekund). Ve většině případů hledání trvá mnohem kratší dobu než maximum. Prodloužení doby umožní cloudu důkladně prozkoumat podezřelé soubory. Doporučujeme povolit toto nastavení a zadat alespoň 20 dalších sekund. |

### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Přidaná síť Citrix VPN pro zařízení s Windows 10 <!-- 1512457 -->  
Pro svá zařízení s Windows 10 můžete nakonfigurovat Citrix VPN. Pokud konfigurujete síť VPN pro Windows 10 a novější, můžete vybrat síť Citrix VPN v seznamu *Vybrat typ připojení* v okně **základní síť VPN** .

> [!Note]
> Konfigurace systému Citrix existovala pro iOS a Android.

### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Připojení Wi-Fi podporují v iOS předem sdílené klíče. <!-- 1550823 -->
Zákazníci můžou nakonfigurovat profily sítě Wi-Fi, aby na zařízeních s iOS používaly pro osobní připojení WPA/WPA2 na zařízeních s iOS předsdílený klíč (PSK). Tyto profily se přiodesílají do zařízení uživatele, když se zařízení zaregistruje do Intune.

Po vložení profilu do zařízení bude další krok záviset na konfiguraci profilu.  Pokud je nastavené automatické připojení, provede to tak, že se síť bude dál potřebovat.  Pokud se profil připojuje ručně, musí uživatel ručně aktivovat připojení.  

### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Přístup k protokolům spravovaných aplikací pro iOS <!-- 1469920 -->
Koncoví uživatelé, kteří mají nainstalované spravované prohlížeče, teď můžou zobrazit stav správy všech aplikací publikovaných Microsoftem a odesílat protokoly pro řešení potíží se spravovanými aplikacemi pro iOS.

Naučte se, jak povolit režim řešení potíží v Managed Browser na zařízení s iOS, najdete v tématu [jak přistupovat k protokolům spravovaných aplikací pomocí Managed Browser v iOS](../apps/app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Vylepšení pracovního postupu instalace zařízení v Portál společnosti pro iOS ve verzi 2.9.0 <!-- 1417174 -->

V aplikaci Portál společnosti pro iOS byl vylepšen pracovní postup instalace zařízení. Jazyk je uživatelsky přívětivější a tam, kde je to možné, jsme spojili obrazovky. Jazyk je pro vaši společnost více specifický pomocí názvu vaší společnosti v celém textu nastavení. Tento aktualizovaný pracovní postup vidíte na [stránce novinky v uživatelském rozhraní aplikace](../whats-new-app-ui.md).


### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Entita uživatele obsahuje nejnovější uživatelská data v datovém modelu datového skladu. <!-- 1544273 -->
První verze datového modelu datového skladu Intune obsahovala jenom nedávná a historická data Intune. Tvůrci sestav se nepodařilo zachytit aktuální stav uživatele. V této aktualizaci se **entita uživatele** naplní nejnovějšími uživatelskými daty.

<!-- ########################## -->
## <a name="october-2017"></a>Říjen 2017

### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>číslo verze obchodní aplikace pro iOS a Android je viditelné. <!-- 1380712 -->

Aplikace v Intune teď zobrazují číslo verze pro obchodní aplikace pro iOS a Android. Číslo se zobrazí v Azure Portal v seznamu aplikací a v okně s přehledem aplikace. Koncoví uživatelé můžou číslo aplikace zobrazit v aplikaci Portál společnosti a na webovém portálu.

__Plné číslo verze__ Celé číslo verze identifikuje konkrétní verzi aplikace. Číslo se zobrazí jako _verze_(_sestavení_). Příklad: 2.2 (2.2.17560800)

Plné číslo verze má dvě součásti:

- **Verze**  
  Číslo verze je uživatelsky čitelné číslo verze aplikace. Tuto hodnotu používají koncoví uživatelé k identifikaci různých verzí aplikace.

- **Číslo buildu**  
  Číslo buildu je interní číslo, které se dá použít při detekci aplikací a při programové správě aplikace. Číslo sestavení odkazuje na iteraci aplikace, která odkazuje na změny v kódu.

Přečtěte si další informace o číslech verzí a vývoji obchodních aplikací v [části Začínáme s Microsoft Intune App SDK](../developer/app-sdk-get-started.md#line-of-business-app-version-numbers).

### <a name="device-and-app-management-integration----677972---"></a>Integrace správy zařízení a aplikací <!-- 677972 -->   
Teď, když je Správa mobilních zařízení (MDM) a Správa mobilních aplikací (MAM) v Intune dostupná jak z Azure Portal, Intune zahájil integraci prostředí pro správu IT v rámci správy aplikací a zařízení. Tyto změny jsou zaměřené na zjednodušené možnosti správy zařízení a aplikací.

Přečtěte si další informace o změnách MDM a MAM, které jsou oznámené na [blogu týmu podpory pro Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Nové výstrahy registrace pro zařízení Apple <!-- 1471790 -->
Stránka s přehledem pro registraci zobrazí užitečné výstrahy pro správce IT týkající se správy zařízení Apple. Když platnost certifikátu Apple MDM push Certificate vyprší nebo už vypršela, výstrahy se zobrazí na stránce s přehledem. Kdy platnost tokenu Program registrace zařízení vypršela nebo již vypršela; a když jsou v Program registrace zařízení Nepřiřazená zařízení.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Podpora nahrazení tokenu pro konfiguraci aplikace bez registrace zařízení <!-- 1080364 -->

Pro aplikace na zařízeních, která nejsou zaregistrovaná, můžete v konfiguracích aplikace použít tokeny pro dynamické hodnoty. Další informace najdete v tématu [Přidání zásad konfigurace aplikací pro spravované aplikace bez registrace zařízení](../apps/app-configuration-policies-managed-app.md).

### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Aktualizace aplikace Portál společnosti pro Windows 10 <!--1299474-->
Stránka nastavení v aplikaci Portál společnosti pro Windows 10 se aktualizovala tak, aby se nastavení a zamýšlené akce uživatele shodovaly napříč všemi nastaveními. Také se aktualizovala tak, aby odpovídala rozložení ostatních aplikací pro Windows. Obrázky před a po najdete na stránce [co je nového v uživatelském rozhraní aplikace](../whats-new-app-ui.md) .

### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Informování koncových uživatelů o tom, jaké informace o zařízení se dají zobrazit pro zařízení s Windows 10 <!--1337920-->
Do obrazovky s podrobnostmi o zařízení v aplikaci Portál společnosti pro Windows 10 jsme přidali **typ vlastnictví** . To umožní uživatelům zjistit další informace o ochraně osobních údajů přímo z této stránky z dokumentace pro koncové uživatele Intune. Budou také moci najít tyto informace na obrazovce **o produktu** .

### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Výzvy k zadání názoru pro aplikaci Portál společnosti pro Android <!--1165249-->
Aplikace Portál společnosti pro Android teď požaduje zpětnou vazbu koncového uživatele. Tato zpětná vazba se pošle přímo společnosti Microsoft a poskytne koncovým uživatelům příležitost ke kontrole aplikace ve veřejném Google Play Storu. Zpětná vazba není nutná a je možné ji snadno zrušit, aby uživatelé mohli aplikaci dál používat.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Pomoc uživatelům s aplikací Portál společnosti pro Android <!-- 1573324, 1573150, 1558616, 1564878 -->

Portál společnosti aplikace pro Android přidala pokyny pro koncové uživatele, které jim pomůžou pochopit, kde je to možné, a to v nových případech použití.
- Koncoví uživatelé budou k dispozici na [portálu Azure Active Directory](https://account.activedirectory.windowsazure.com/r/#/profile) , aby odebrali zařízení, pokud dosáhli maximálního počtu zařízení, která můžou přidat.
- Koncovým uživatelům se zobrazí postup, který jim umožní [opravit chyby aktivace na zařízeních Samsung KNOX](https://go.microsoft.com/fwlink/?linkid=859718) nebo vypnout [režim úspory napájení](/intune-user-help/power-saving-mode-android). Pokud žádná z těchto řešení nevyřešila svůj problém, poskytneme vám vysvětlení, jak [Odeslat protokoly společnosti Microsoft](/intune-user-help/send-logs-to-microsoft-android).

### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>K dispozici je nová akce vyřešit pro zařízení s Androidem. <!-- 1583480 -->

Portál společnosti aplikace pro Android zavádí akci vyřešit na stránce _aktualizovat nastavení zařízení_ . Výběrem této možnosti povedete koncovému uživateli přímo k nastavení, které způsobuje, že jejich zařízení nedodržuje předpisy. Aplikace Portál společnosti pro Android aktuálně podporuje tuto akci pro [heslo zařízení](/intune-user-help/set-your-pin-or-password-android), [ladění USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android)a nastavení [neznámých zdrojů](/intune-user-help/you-need-to-turn-off-unknown-sources-android) .

### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Indikátor průběhu instalace zařízení v Androidu Portál společnosti <!-- 1565657 -->
Aplikace Portál společnosti pro Android zobrazuje indikátor průběhu instalace zařízení, když uživatel zaregistruje své zařízení. Tento indikátor zobrazí nové stavy, od "nastavení zařízení...", pak "registrace zařízení..." a pak "dokončí registraci zařízení..." a pak "dokončí nastavení zařízení...".

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Podpora ověřování na základě certifikátů na Portál společnosti pro iOS <!--1029830-->
V aplikaci Portál společnosti pro iOS jsme přidali podporu ověřování na základě certifikátu (certifikátů). Uživatelé, kteří mají certifikátů, zadejte svoje uživatelské jméno a pak klepněte na odkaz Přihlásit se pomocí certifikátu. CERTIFIKÁTŮ se už podporuje v aplikacích Portál společnosti pro Android a Windows. Další informace najdete v části [přihlášení na stránku aplikace Portál společnosti](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) .

### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Aplikace, které jsou k dispozici s registrací nebo bez registrace, se teď dají nainstalovat bez výzvy k registraci. <!-- 1334712 -->

Firemní aplikace, které byly k dispozici s registrací v aplikaci pro Android Portál společnosti nebo bez ní, se teď dají nainstalovat bez výzvy k registraci.

### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Podpora programu Windows autopilot Deployment v Microsoft Intune  <!-- 747617  -->
Nyní můžete použít Microsoft Intune s programem Windows autopilot Deployment, abyste uživatelům poskytli možnost zřídit podniková zařízení bez nutnosti jejich zahrnutí. Můžete přizpůsobit prostředí spouštěné při prvním zapnutí a nastavit uživatele, aby se připojili ke svému zařízení do Azure AD a zaregistrovali v Intune. Při společném fungování Microsoft Intune a Windows autopilotní eliminují nutnost nasazovat, udržovat a spravovat image operačního systému. Podrobnosti najdete v tématu [registrace zařízení s Windows pomocí programu Windows autopilot Deployment](../enrollment/enrollment-autopilot.md).

### <a name="quickstart-for-device-enrollment-----1425655---"></a>Rychlý Start pro registraci zařízení  <!-- 1425655 --> 
V **zápisu zařízení** je nyní k dispozici rychlý Start a poskytuje tabulku odkazů pro správu platforem a konfiguraci procesu registrace. Stručný popis každé položky a odkazy na dokumentaci s podrobnými pokyny poskytují užitečnou dokumentaci, která usnadňuje zahájení práce.

### <a name="device-categorization----1427491---"></a>Kategorizace zařízení <!-- 1427491 -->
Graf Platform zaregistrovaných zařízení v okně **zařízení > přehled** organizuje zařízení podle platformy, včetně Androidu, iOS, MacOS, Windows a Windows Mobile.  Zařízení s jinými operačními systémy se seskupují do části "jiné".  Patří sem zařízení, která vyrábí BlackBerry, NOKIA a další.  

Pokud chcete zjistit, která zařízení jsou ve vašem tenantovi ovlivněná, zvolte **spravovat > všech zařízeních** a pak použijte **Filtr** k omezení pole **OS** .

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – nový partner ochrany před mobilními hrozbami   <!-- 954681 -->  
Přístup mobilních zařízení k podnikovým prostředkům můžete řídit pomocí podmíněného přístupu na základě posouzení rizik, které provádí Zimperium, řešení ochrany před mobilními hrozbami, které se integruje s Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak integrace s Intune funguje
Riziko se vyhodnocuje na základě telemetrie shromážděných ze zařízení s Zimperium. Zásady podmíněného přístupu EMS můžete nakonfigurovat na základě posouzení rizik s Zimperium, které jsou povolené prostřednictvím zásad dodržování předpisů zařízením Intune, které můžete použít k povolení nebo blokování nevyhovujících zařízení pro přístup k podnikovým prostředkům na základě zjištěných hrozeb.

### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Nová nastavení pro profil omezení zařízení s Windows 10  <!--- 978575, 1308849, -->  
Do profilu omezení zařízení s Windows 10 přidáváme nová nastavení v kategorii SmartScreen v programu Windows Defender.

Podrobnosti o profilu omezení zařízení s Windows 10 najdete v tématu [Nastavení omezení pro zařízení s Windows 10 a novějším](../configuration/device-restrictions-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Vzdálená podpora pro zařízení s Windows a Windows Mobile   <!-- 1070473 -->  
Intune teď může využívat software [TeamViewer](https://www.teamviewer.com) , který se kupuje samostatně, a umožňuje tak poskytovat vzdálenou pomoc uživatelům, kteří používají Windows a zařízení Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Kontrola zařízení pomocí programu Windows Defender <!-- 1280988  1280990   -->
Pomocí antivirové ochrany v programu Windows Defender na spravovaných zařízeních s Windows 10 teď můžete spustit **rychlou kontrolu**, **úplnou kontrolu**a **aktualizovat signatury** . V okně s přehledem zařízení vyberte akci, která se má na zařízení spustit. Před odesláním příkazu do zařízení se zobrazí výzva k potvrzení akce. 

**Rychlá kontrola**: Rychlá kontrola prohledává umístění, kde se zaregistrují malware, jako jsou klíče registru a známé spouštěcí složky Windows. Rychlá kontrola trvá průměrně pět minut. V kombinaci s nastavením **vždy aktivní ochrany v reálném čase** , které prohledává soubory při jejich otevření, zavření a kdykoli uživatel přejde do složky, zajišťuje Rychlá kontrola ochranu proti malwaru, který může být v systému nebo v jádru. Po dokončení uvidí uživatelé na svých zařízeních výsledky kontroly. 

**Úplná kontrola**: úplná kontrola může být užitečná na zařízeních s malwarem, který zjistil, jestli neexistují nějaké neaktivní komponenty, které vyžadují důkladnější vyčištění a jsou užitečné pro spouštění kontrol na vyžádání. Spuštění úplné kontroly může trvat hodinu. Po dokončení uvidí uživatelé na svých zařízeních výsledky kontroly. 

**Aktualizace podpisů**: příkaz Aktualizovat podpis aktualizuje definice a podpisy antivirové ochrany v programu Windows Defender. To pomáhá zajistit, aby antivirová ochrana v programu Windows Defender byla platná při zjišťování malwaru. Tato funkce se používá jenom pro zařízení s Windows 10, která čekají na připojení k Internetu zařízení. 

### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Na stránce certifikační autorita Intune služby Intune se odebere tlačítko Povolit/zakázat Azure Portal  <!-- 1400455 -->
 V části nastavení Certificate Connectoru v Intune odstraňujeme dodatečný krok. V současné době si stáhnete Certificate Connector a pak ho povolíte v konzole Intune. Pokud ale zakážete konektor v konzole Intune, zůstane konektor nadále vystavovat certifikáty.

#### <a name="how-does-this-affect-me"></a>Jak se to týká?
Od října se tlačítko Povolit/zakázat již nebude zobrazovat na stránce certifikační autorita v Azure Portal. Funkce konektoru zůstávají stejné. Certifikáty se pořád nasazují do zařízení zaregistrovaných v Intune. Můžete pokračovat stažením a instalací Certificate Connectoru. Pokud chcete zastavit vystavování certifikátů, odinstalujte ji místo toho Certificate Connectoru.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co je potřeba udělat, aby se tato změna připravila?
Pokud momentálně konektor Certificate Connector zakázán, měli byste ho odinstalovat.

### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Nová nastavení pro profil omezení zařízení s Windows 10 Team   <!--- 1308838 -->
V této verzi jsme přidali spoustu nových nastavení do profilu omezení zařízení s Windows 10 Team, která vám pomůžou řídit Surface Hub zařízení.

Další informace o tomto profilu najdete v tématu [Nastavení omezení pro zařízení s Windows 10 Team](../configuration/device-restrictions-windows-10-teams.md).

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Zabránit uživatelům zařízení s Androidem změnit datum a čas zařízení  <!-- 1333292 -->
Pomocí [vlastních zásad zařízení s Androidem](../configuration/custom-settings-android.md) můžete uživatelům zařízení s Androidem zabránit ve změně data a času zařízení.

Provedete to tak, že nakonfigurujete vlastní zásadu pro Android s identifikátorem URI./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange nastavte tuto **hodnotu na true**a pak ji přiřaďte požadovaným skupinám.

### <a name="bitlocker-device-configuration----1397398---"></a>Konfigurace zařízení BitLockeru <!-- 1397398 -->
**Základní nastavení Windows encryption >** zahrnuje nové nastavení **Upozornění na jiné šifrování disku** , které vám umožní zakázat výzvu s [upozorněním](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowwarningforotherdiskencryption) na jiné šifrování disku, které se na zařízení uživatele může používat.  Před nastavením BitLockeru na zařízení se zobrazí výzva k zadání výstrahy koncového uživatele a zablokuje nastavení BitLockeru až po potvrzení koncového uživatele.  Nové nastavení zakazuje upozornění koncového uživatele.


### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Aplikace Volume purchase program pro firmy se teď budou synchronizovat s vaším klientem Intune. <!-- 800882 -->  
Vývojáři třetích stran můžou soukromě distribuovat aplikace do autorizovaného programu Volume purchase program (VPP) pro obchodní členy zadané v iTunes Connect. Tito členové programu VPP pro firmy se můžou přihlásit k aplikaci Volume purchase program Store a koupit své aplikace.

V této verzi se aplikace VPP pro firmy zakoupené koncovým uživatelem začnou synchronizovat se svými klienty Intune.

### <a name="select-apple-countryregion-store-to-sync-vpp-apps-----1332311---"></a>Výběr země/oblasti obchodu Apple pro synchronizaci aplikací VPP  <!-- 1332311 -->  
Při nahrávání tokenu VPP můžete nakonfigurovat obchod země/oblasti programu Volume purchase program (VPP). Intune synchronizuje aplikace VPP pro všechna národní prostředí ze zadaného úložiště v zemi nebo oblasti VPP.

> [!NOTE]  
> V současné době Intune synchronizuje aplikace VPP jenom z obchodu VPP země/oblast, která se shoduje s národním prostředím Intune, ve kterém se vytvořil tenant Intune.


### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Blokování kopírování a vkládání mezi pracovními a osobními profily v Androidu for Work <!-- 1098994 -->
V této verzi budete moct nakonfigurovat pracovní profil pro Android for Work, aby blokoval kopírování a vkládání mezi pracovními a osobními aplikacemi. Toto nové nastavení najdete v profilu **omezení zařízení** pro platformu **Android for Work** v **Nastavení pracovního profilu**.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Vytváření aplikací pro iOS omezených na konkrétní místní obchody Apple App <!-- 1281692 -->
Během vytváření spravované aplikace pro Apple App Store budete moct zadat národní prostředí země nebo oblasti.

> [!Note]  
> V současné době můžete vytvářet jenom spravované aplikace Apple App Store, které jsou k dispozici v úložišti země/oblasti USA.

### <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Aktualizace licencovaných aplikací pro iOS VPP uživatelů a zařízení  <!-- 1305564 -->  
Pokud chcete aktualizovat všechny aplikace zakoupené pro daný token prostřednictvím služby Intune, budete moct nakonfigurovat token VPP pro iOS. Intune detekuje aktualizace aplikace VPP v App Storu a automaticky je po kontrole zařízení vyřadí do zařízení.

Postup nastavení tokenu VPP a povolení automatických aktualizací najdete v článku [Správa aplikací pro iOS zakoupených prostřednictvím programu hromadného nákupu pomocí Microsoft Intune] (/Intune/VPP-Apps-iOS).


### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Přidala se kolekce entit přidružení uživatelských zařízení do datového modelu datového skladu Intune. <!-- 1187917 -->
Nyní můžete vytvářet sestavy a vizualizace dat pomocí informací o přidružení uživatelských zařízení, které přidruží kolekce entit uživatelů a zařízení. K datovému modelu se dá získat pøístup prostřednictvím Power BI souboru (PBIX) načteného ze stránky Intune datového skladu, prostřednictvím koncového bodu OData nebo pomocí vývoje vlastního klienta.

### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Kontrola dodržování zásad pro aktualizační kanály Windows 10 <!-- 1067886 -->
Můžete zkontrolovat sestavu zásad pro aktualizační kanály Windows 10 z aktualizace softwaru > stav nasazení podle aktualizačního kruhu. Sestava zásad obsahuje stav nasazení pro aktualizační kanály, které jste nakonfigurovali. 

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nová sestava se seznamem zařízení s iOS se staršími verzemi iOS   <!-- 1352223 -->
Sestava **zařízení se zastaralým systémem iOS** je k dispozici v pracovním prostoru **aktualizace softwaru** . V sestavě můžete zobrazit seznam zařízení se systémem iOS, na která byla zacílena zásada aktualizace pro iOS a mít dostupné aktualizace. Pro každé zařízení můžete zobrazit stav, proč se zařízení neaktualizovalo automaticky. 

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Zobrazení přiřazení zásad ochrany aplikací pro řešení potíží <!--  1475003 -->
V této nadcházející verzi se možnost **Zásady ochrany aplikací** přidá do rozevíracího seznamu **přiřazení** , který je dostupný v okně řešení potíží. Teď můžete vybrat zásady ochrany aplikací a zobrazit zásady ochrany aplikací přiřazené vybraným uživatelům.



### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Vylepšení pracovního postupu instalace zařízení v Portál společnosti <!--1490692-->
Vylepšili jsme pracovní postup instalace zařízení v aplikaci Portál společnosti pro Android. Jazyk je uživatelsky přívětivější a specifické pro vaši společnost a tam, kde je to možné, jsme spojili obrazovky. Tyto informace najdete na stránce [co je nového v uživatelském rozhraní aplikace](whats-new-app-ui.md#week-of-october-2-2017) .

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Vylepšené pokyny k žádosti o přístup ke kontaktům na zařízeních s Androidem <!--1484985-->

Portál společnosti aplikace pro Android často vyžaduje, aby koncový uživatel přijal oprávnění kontakty. Pokud koncový uživatel tento přístup zamítne, zobrazí se mu nyní oznámení v aplikaci, které je upozorní na udělení podmíněného přístupu. 

### <a name="secure-startup-remediation-for-android---1490712--"></a>Zabezpečená náprava při spuštění pro Android <!--1490712-->

Koncoví uživatelé, kteří používají zařízení s Androidem, budou moct v aplikaci Portál společnosti klepnout na důvod nedodržení předpisů. Pokud je to možné, přejdou je přímo do správného umístění v aplikaci nastavení, aby se problém vyřešil. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Další nabízená oznámení pro koncové uživatele v aplikaci Portál společnosti pro Android Oreo <!--1475932-->

Koncovým uživatelům se zobrazí další oznámení v případě, že aplikace Portál společnosti pro Android Oreo provádí úlohy na pozadí, třeba načítání zásad ze služby Intune. Tím se zvyšuje transparentnost koncových uživatelů o tom, kdy Portál společnosti provádí úlohy správy na svém zařízení. Jedná se o součást celkové [optimalizace portál společnosti uživatelského rozhraní](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) pro portál společnosti aplikaci pro Android Oreo. 

K dispozici jsou další optimalizace pro nové prvky uživatelského rozhraní, které jsou povoleny v Android Oreo.  Koncovým uživatelům se zobrazí další oznámení, která jim poukazují, když Portál společnosti provádí úlohy na pozadí, jako je třeba načítání zásad ze služby Intune.  Tím se zvyšuje průhlednost koncových uživatelů o tom, kdy Portál společnosti provádí úlohy správy na zařízení.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nové chování pro aplikaci Portál společnosti pro Android s pracovními profily <!-- 1485783 -->

Když zaregistrujete zařízení s Androidem for Work s pracovním profilem, je Portál společnosti aplikace v pracovním profilu, který na zařízení provádí úlohy správy. 

Pokud v osobním profilu nepoužíváte aplikaci s podporou MAM, aplikace Portál společnosti pro Android už neobsluhuje žádné použití. Pro zlepšení prostředí pracovních profilů Intune po úspěšné registraci pracovního profilu automaticky skryje osobní Portál společnosti aplikace.

Aplikaci Portál společnosti pro Android můžete kdykoli povolit v osobním profilu procházením [portál společnosti v obchod Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) a klepnutím na **Povolit**.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Portál společnosti pro Windows 8.1 a Windows Phone 8,1 přesun do trvalého režimu <!--1428681-->

Od října 2017 se aplikace Portál společnosti pro Windows 8.1 a Windows Phone 8,1 přesunou do trvalého režimu. To znamená, že aplikace a stávající scénáře, jako je registrace a dodržování předpisů, budou na těchto platformách i nadále podporovány. Tyto aplikace budou dál k dispozici ke stažení prostřednictvím existujících kanálů vydávání verzí, jako je Microsoft Store. 

V trvalém režimu budou tyto aplikace přijímat jenom důležité aktualizace zabezpečení. Pro tyto aplikace se neuvolní žádné další aktualizace ani funkce. Pro nové funkce Doporučujeme aktualizovat zařízení na Windows 10 nebo Windows 10 Mobile. 


### <a name="block-unsupported-samsung-knox-device-enrollment-----1490695---"></a>Zablokovat nepodporovanou registraci zařízení Samsung KNOX  <!-- 1490695 -->

Aplikace Portál společnosti se pokusí zaregistrovat podporovaná zařízení Samsung KNOX. Aby se předešlo chybám aktivace KNOX, které brání v registraci MDM, pokusí se registrace zařízení jenom v případě, že se zařízení zobrazuje v [seznamu zařízení publikovaných pomocí Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Zařízení Samsung můžou mít čísla modelů, která podporují KNOX, a jiné ne. Před nákupem a nasazením ověřte kompatibilitu s produktem Knox s vaším prodejcem zařízení. Úplný seznam ověřených zařízení najdete v [nastavení zásad pro Android a Samsung KNOX Standard](supported-devices-browsers.md#intune-supported-web-browsers).

### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Konec podpory pro Android 4,3 a nižší <!-- 1171126, 1326920 -->
Spravované aplikace a aplikace Portál společnosti pro Android budou pro přístup k firemním prostředkům vyžadovat Android 4,4 a vyšší. Od prosince budou všechna zaregistrovaná zařízení vyřazení vynucená v prosinci, což vede ke ztrátě přístupu k firemním prostředkům. Pokud používáte zásady ochrany aplikací bez správy mobilních zařízení (MDM), aplikace nebudou dostávat aktualizace a kvalita jejich prostředí se v průběhu času bude zmenšovat.

### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Informování koncových uživatelů o tom, jaké informace o zařízení je možné zobrazit v zaregistrovaných zařízeních <!--1165314-->
Do obrazovky s podrobnostmi o zařízení na všech Portál společnostich aplikacích přidáváme **typ vlastnictví** . To umožní uživatelům zjistit další informace o ochraně osobních údajů přímo z [informací, které může vaše společnost zobrazit?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) článek. To se v blízké budoucnosti bude nacházet napříč všemi Portál společnosti aplikacemi. Toto jsme oznámili pro iOS v [září](#september-2017).

<!-- ########################## -->
## <a name="september-2017"></a>Září 2017

### <a name="intune-supports-ios-11---1428975--"></a>Intune podporuje iOS 11. <!--1428975-->
Intune podporuje iOS 11. Toto bylo dřív oznámeno na [blogu podpory Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

### <a name="end-of-support-for-ios-80----1164477---"></a>Konec podpory pro iOS 8,0 <!-- 1164477 -->
Spravované aplikace a aplikace Portál společnosti pro iOS budou pro přístup k firemním prostředkům vyžadovat iOS 9,0 a vyšší. Zařízení, která nejsou aktualizována před touto září, již nebudou mít přístup k Portál společnosti nebo těmto aplikacím. 

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Do aplikace Portál společnosti pro Windows 10 se přidala akce aktualizace. <!--1132468-->
Aplikace Portál společnosti pro Windows 10 umožňuje uživatelům aktualizovat data v aplikaci, a to buď pomocí přijetí změn, nebo na desktopech stisknutím klávesy F5.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Informování koncových uživatelů o tom, jaké informace o zařízení se dají zobrazit pro iOS <!--739894-->

Do obrazovky s podrobnostmi o zařízení v aplikaci Portál společnosti pro iOS jsme přidali **typ vlastnictví** . To umožní uživatelům zjistit další informace o ochraně osobních údajů přímo z této stránky z dokumentace pro koncové uživatele Intune. Budou také moci najít tyto informace na obrazovce o produktu.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Umožněte koncovým uživatelům přístup k aplikaci Portál společnosti pro Android bez registrace. <!---1169910--->

Koncoví uživatelé brzy nebudou muset zaregistrovat svoje zařízení pro přístup k aplikaci Portál společnosti pro Android. Koncoví uživatelé v organizacích, kteří používají zásady ochrany aplikací, už nebudou dostávat výzvy k registraci zařízení, když otevřou aplikaci Portál společnosti. Koncoví uživatelé budou také moct instalovat aplikace z Portál společnosti bez registrace zařízení. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Snadnější pochopení formulace pro Portál společnosti aplikaci pro Android <!---1396349--->  

Proces registrace pro aplikaci Portál společnosti pro Android je zjednodušený s novým textem, který koncovým uživatelům usnadňuje registraci. Pokud máte vlastní dokumentaci k registraci, budete ji chtít aktualizovat tak, aby odrážela nové obrazovky. Ukázkové obrázky najdete na naší stránce [aktualizace uživatelského rozhraní pro aplikace Intune pro koncové uživatele](whats-new-app-ui.md#week-of-september-11-2017) .

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Windows 10 Portál společnosti aplikace přidaná do Windows Information Protection zásady povolení <!-- 677129 -->

Aplikace Portál společnosti pro Windows 10 se aktualizovala tak, aby podporovala Information Protection Windows (NV). Aplikaci je možné přidat do zásady povolení nedokončené výroby. Tato změna umožňuje, aby se aplikace už nepřidala do seznamu **vyloučení** .


<!-- ########################## -->
## <a name="august-2017"></a>Srpen 2017

### <a name="improvements-to-device-overview----1404453---"></a>Vylepšení přehledu zařízení <!-- 1404453 -->  
Vylepšení zařízení přehled teď zobrazují registrovaná zařízení, ale nevylučují zařízení spravovaná přes Exchange ActiveSync. Zařízení Exchange ActiveSync nemají stejné možnosti správy jako zaregistrovaná zařízení. Pokud chcete zobrazit počet zaregistrovaných zařízení a počet registrovaných zařízení podle platformy v Intune v Azure Portal, přečtěte si @no__t **-1** **zařízení**.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Vylepšení inventáře zařízení shromážděného službou Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
V této verzi jsme provedli následující vylepšení informací o inventáři shromažďovaných zařízeními, která spravujete:
 
- Pro zařízení s Androidem teď můžete přidat sloupec do inventáře zařízení, který zobrazuje nejnovější úroveň oprav pro každé zařízení. Chcete-li se podívat, přidejte do seznamu zařízení sloupec **úroveň opravy zabezpečení** .
- Když filtrujete zobrazení zařízení, můžete teď filtrovat zařízení podle data registrace. Můžete například zobrazit pouze zařízení, která byla zaregistrována po určitém datu.
- Provedli jsme vylepšení filtru používaného poslední položkou **data vrácení se změnami** .
- V seznamu zařízení teď můžete zobrazit telefonní číslo zařízení vlastněných společností.
Navíc můžete použít podokno filtru a vyhledat zařízení podle telefonního čísla.

Další podrobnosti o inventáři zařízení najdete v tématu [Postup zobrazení inventáře zařízení v Intune](../remote-actions/device-inventory.md).

### <a name="conditional-access-support-for-macos-devices"></a>Podpora podmíněného přístupu pro zařízení macOS 
<!-- 720172 -->
Teď můžete nastavit zásadu podmíněného přístupu, která vyžaduje, aby se zařízení Mac zaregistrovala do Intune a vyhovovala zásadám dodržování předpisů zařízením. Uživatelé můžou například stáhnout aplikaci Portál společnosti Intune pro macOS a zaregistrovat svá zařízení Mac do Intune. Intune vyhodnocuje, jestli zařízení Mac splňuje požadavky, nebo ne, s požadavky, jako je PIN, šifrování, verze operačního systému a integrita systému.

- Přečtěte si další informace o [podpoře podmíněného přístupu pro zařízení MacOS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>Aplikace Portál společnosti pro macOS je ve verzi Public Preview. <!---1484796--->
Portál společnosti App for macOS je teď k dispozici jako součást veřejné verze Preview pro podmíněný přístup v Enterprise Mobility + Security. Tato verze podporuje macOS 10,11 a novější. Získáte ji [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Nová nastavení omezení pro zařízení s Windows 10    
<!--1063965, 1308850  -->
V této verzi jsme přidali nová nastavení pro [profil omezení zařízení s Windows 10](/intune/device-restrictions-windows-10) v následujících kategoriích:

- Filtr SmartScreen v programu Windows Defender
- App Store

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Aktualizace profilu zařízení ochrany koncových bodů Windows 10 pro nastavení BitLockeru
<!--1459533 -->    
V této verzi jsme provedli následující vylepšení, jak nastavení BitLockeru funguje v profilu zařízení s Windows 10 Endpoint Protection:
 
- V části **Nastavení jednotky s operačním systémem BitLocker**pro nastavení **BitLockeru s nekompatibilním čipem TPM**když vyberete **blokovat**, dříve to způsobí, že BitLocker bude skutečně povolený. Tuto možnost jsme teď opravili, aby se BitLocker při výběru zablokoval.
- V části **Nastavení jednotky s operačním systémem BitLocker**pro nastavení **agenta obnovení dat založeného na certifikátech**teď můžete explicitně zablokovat agenta obnovení dat založeného na certifikátech. Ve výchozím nastavení je ale agent povolený.
- V části **nastavení s pevným datovým diskem BitLocker**pro nastavení **agenta obnovení dat**teď můžete agenta obnovení dat explicitně zablokovat.
Další informace najdete v tématu [nastavení ochrany koncových bodů pro Windows 10 a novější](../protect/endpoint-protection-windows-10.md).


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nové přihlášené prostředí pro uživatele Androidu Portál společnosti a zásady ochrany aplikací <!-- 621669 -->
Koncoví uživatelé teď můžou procházet aplikace, spravovat zařízení a zobrazovat kontaktní údaje IT pomocí aplikace Portál společnosti pro Android bez registrace zařízení s Androidem. Navíc platí, že pokud koncový uživatel už používá aplikaci chráněnou zásadami Intune App Protection a spustí Portál společnosti pro Android, koncový uživatel už neobdrží výzvu k registraci zařízení.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nové nastavení v aplikaci pro Android Portál společnosti pro přepnutí optimalizace baterie <!--1405990-->
Stránka **Nastavení** v aplikaci Portál společnosti pro Android má nové nastavení, které uživatelům umožní snadno vypnout optimalizaci baterie pro aplikace Portál společnosti a Microsoft Authenticator. Název aplikace zobrazený v nastavení se liší v závislosti na tom, která aplikace spravuje pracovní účet. Pro zajištění lepšího výkonu pracovních aplikací, které synchronizují e-maily a data, doporučujeme uživatelům vypnout optimalizaci baterie. 

### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>Podpora více identit pro OneNote pro iOS      <!-- 1234281 -->
Koncoví uživatelé teď můžou používat různé účty (pracovní a osobní) s Microsoft OneNotem pro iOS. Zásady ochrany aplikací se dají aplikovat na firemní data v pracovních poznámkových blocích, aniž by to mělo vliv na osobní poznámkové bloky. Například zásada může uživateli dovolit najít informace v pracovních poznámkových blocích, ale zabrání uživateli v kopírování a vkládání firemních dat z pracovních poznámkových bloků do osobního poznámkového bloku.
 
- Přečtěte si další informace o aplikacích, které podporují [ochranu aplikací a více identit](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) s Intune.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Nové nastavení pro povolení a blokování aplikací na zařízeních se Samsung KNOX standardem
<!-- 1305423 822899-->  
V této verzi přidáváme nová [Nastavení omezení zařízení](../configuration/device-restrictions-android.md) , která vám umožní zadat následující seznamy aplikací:
 
- Aplikace, které můžou uživatelé instalovat
- Aplikace, které uživatelé zablokovali při spuštění
- Aplikace skryté uživateli na zařízení
 
Aplikaci můžete zadat podle adresy URL, názvu balíčku nebo ze seznamu spravovaných aplikací.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Nové propojení uživatelského rozhraní zásad podmíněného přístupu založeného na aplikaci Azure AD z Intune
<!-- 1016201 -->
Správci IT teď můžou nastavit podmíněné zásady na základě aplikací prostřednictvím nového uživatelského rozhraní zásad podmíněného přístupu v úloze Azure AD. Podmíněný přístup na základě aplikace, který je v části Intune App Protection v Azure Portal, zůstane v tomto časovém intervalu a bude využíván vedle sebe. Existuje také praktický odkaz na nové uživatelské rozhraní zásad podmíněného přístupu v rámci úlohy Intune.

- Přečtěte si další informace o [podmíněném přístupu na základě aplikace v Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).

<!-- ########################## -->
## <a name="july-2017"></a>Červenec 2017

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Omezení registrace zařízení s Androidem a iOS podle verze operačního systému  <!--- 1333256,  1245463 --->
Intune teď podporuje omezení registrace zařízení s iOS a Androidem podle čísla verze operačního systému. V části **omezení typu zařízení**teď může správce IT nastavit konfiguraci platformy tak, aby se omezil zápis mezi minimální a maximální hodnotou operačního systému. Verze operačního systému Android musí být zadány jako hlavní_verze. podverze. sestavení. rev, kde podverze, sestavení a revize jsou nepovinné. verze iOS musí být zadané jako hlavní_verze. podverze. sestavení, kde dílčí a Build jsou volitelné. Přečtěte si další informace o [omezení registrace zařízení](../enrollment/enrollment-restrictions-set.md).

>[!NOTE]
>Neomezuje registraci prostřednictvím programů registrace Apple ani Apple Configuratoru.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Omezení registrace zařízení v osobním vlastnictví zařízení s Androidem, iOS a macOS  <!--- 1333272,  1333275, 1245709 --->
Intune může omezit registraci osobních zařízení bílým seznamem čísel IMEI podnikových zařízení. Intune teď tuto funkci rozšířil na iOS, Android a macOS s využitím sériových čísel zařízení. Nahráním sériových čísel do Intune můžete předem deklarovat zařízení jako ve vlastnictví firmy. Pomocí omezení registrace můžete blokovat zařízení v osobním vlastnictví (BYOD) a povolit registraci jenom pro zařízení vlastněná společností. Přečtěte si další informace o [omezení registrace zařízení](../enrollment/enrollment-restrictions-set.md).

Pokud chcete importovat sériová čísla, přejděte na **registrace zařízení** > **identifikátory podnikových zařízení** a klikněte na **Přidat** a potom nahrajte. Soubor CSV (bez záhlaví, dva sloupce pro sériové číslo a podrobnosti jako čísla IMEI). Pokud chcete omezit zařízení v osobním vlastnictví, použijte **registraci zařízení** > **omezení registrace**. V části **omezení typů zařízení**vyberte **výchozí** a pak vyberte **konfigurace platformy**. V zařízeních s iOS, Androidem a macOS můžete zařízení v osobním vlastnictví **Zakázat** nebo **zablokovat** .


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nová akce zařízení pro vynucení synchronizace zařízení s Intune <!-- 711369 -->
V této verzi jsme přidali novou akci zařízení, která vybranému zařízení vynutí okamžité vrácení se změnami pomocí Intune. Jakmile se zařízení zablokuje, okamžitě obdrží všechny nedokončené akce nebo zásady, které mu byly přiřazeny.  Tato akce vám může pomoct okamžitě ověřit a řešit potíže se zásadami, které jste přiřadili, aniž byste čekali na další plánované vrácení se změnami.
Podrobnosti najdete v tématu [synchronizace zařízení](../remote-actions/device-sync.md) .

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Vynutit zařízení iOS pod dohledem k automatické instalaci nejnovější dostupné aktualizace softwaru <!-- 777100 -->
V pracovním prostoru aktualizace softwaru jsou k dispozici nové zásady, pomocí kterých můžete vynutit, aby zařízení s iOS pod dohledem automaticky nainstalovala nejnovější dostupnou aktualizaci softwaru. Podrobnosti najdete v tématu [Konfigurace zásad aktualizace pro iOS](/intune/software-updates-ios) .

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile – nový partner ochrany před mobilními hrozbami  <!-- 954651, 1172027 -->
Přístup mobilních zařízení k podnikovým prostředkům můžete řídit pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Checkpoint SandBlast Mobile, řešení ochrany před mobilními hrozbami, které se integruje s Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak integrace s Intune funguje?
Riziko se vyhodnocuje na základě telemetrie shromážděných ze zařízení s kontrolním bodem SandBlast Mobile. Pomocí zásad dodržování předpisů zařízením v Intune můžete nakonfigurovat zásady podmíněného přístupu EMS na základě kontrolního bodu SandBlastu mobilního rizika. V závislosti na zjištěných hrozbách můžete zařízením, která nedodržují předpisy zablokovat přístup k podnikovým prostředkům.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Nasazení aplikace jako dostupné ve Microsoft Store pro firmy <!-- 748101 -->
V této verzi teď správci můžou přiřadit Microsoft Store pro firmy jako k dispozici. Když se nastaví jako k dispozici, koncoví uživatelé můžou aplikaci nainstalovat z Portál společnosti aplikace nebo webu, aniž by se přesměrovala na Microsoft Store.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Aktualizace uživatelského rozhraní na web Portál společnosti <!--1313244 part 1-->
Provedli jsme několik aktualizací uživatelského rozhraní [portál společnosti webu](https://portal.manage.microsoft.com) za účelem vylepšení prostředí koncového uživatele.

- __Vylepšení dlaždic aplikací__: ikony aplikací se teď zobrazí s automaticky generovaným pozadím na základě dominantní barvy ikony (Pokud se dá detekovat). V případě potřeby toto pozadí nahradí šedé ohraničení, které bylo dříve vidět na dlaždicích aplikací.

    Web Portál společnosti zobrazuje v nadcházející verzi velké ikony, kdykoli to bude možné. Doporučujeme, aby správci IT publikovali aplikace pomocí ikon s vysokým rozlišením s minimální velikostí 120 x 120 pixelů. 

- __Navigační změny__: položky navigačního panelu se přesunou do nabídky hamburgerovou "v levém horním rohu. Odstraní se stránka kategorie. Uživatelé teď můžou filtrovat obsah podle kategorií při procházení.

- __Aktualizace vybraných aplikací__: Přidali jsme na web vyhrazenou stránku, kde můžou uživatelé procházet aplikace, které jste si zvolili, a udělali jsme některé uživatelské rozhraní na domovské stránce.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Podpora iBooks pro web Portál společnosti <!--1231841-->
Přidali jsme na web Portál společnosti vyhrazenou stránku, která umožňuje uživatelům procházet a stahovat iBooks. 


### <a name="additional-help-desk-troubleshooting-details------applies-to-1263399-1326964-1341642----"></a>Další podrobnosti o řešení potíží s oddělením technické podpory <!---  Applies to 1263399, 1326964, 1341642 --->
Intune aktualizoval displej pro odstraňování potíží a přidal ho k informacím, které poskytuje správcům a pracovníkům technické podpory. Teď můžete zobrazit tabulku **přiřazení** , která shrnuje všechna přiřazení pro uživatele na základě členství ve skupinách. Tento seznam obsahuje:
- Mobilní aplikace
- Zásady dodržování předpisů
- Konfigurační profily

Kromě toho tabulka **zařízení** nyní zahrnuje **Typ připojení Azure AD** a sloupce kompatibilní se službou **Azure AD** . Další informace najdete v tématu [pomoct uživatelům s řešením problémů](../help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Datový sklad Intune (Public Preview)
Datový sklad Intune denně vzorkuje data, aby mohl poskytovat historický přehled o vašem tenantovi. K datům můžete přistupovat pomocí souboru Power BI (PBIX), odkazu OData, který je kompatibilní s mnoha analytickými nástroji, nebo interakcí s REST API. Další informace najdete v tématu [použití datového skladu Intune](../developer/reports-nav-create-intune-reports.md).


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Světlé a tmavé režimy, které jsou k dispozici pro aplikaci Portál společnosti pro Windows 10 <!---676547--->
Koncoví uživatelé budou moci přizpůsobit režim barvy pro aplikaci Portál společnosti pro Windows 10. Uživatel může provést změnu v části nastavení aplikace Portál společnosti. Tato změna se zobrazí poté, co uživatel aplikaci restartuje. Pro Windows 10 verze 1607 a novější se režim aplikace nastaví na výchozí nastavení systému. Pro Windows 10 verze 1511 a novější se režim aplikace nastaví jako výchozí režim světla.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Povolit koncovým uživatelům označit skupinu zařízení v aplikaci Portál společnosti pro Windows 10 <!---807046-->
Koncoví uživatelé teď můžou vybrat, do které skupiny jejich zařízení patří, pomocí označení přímo v aplikaci Portál společnosti pro Windows 10.

<!-- ########################## -->
## <a name="june-2017"></a>Červeně 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Nový přístup pro správu na základě rolí pro správce Intune   <!-- 1099990 -->  
Přidávají se nové role správce podmíněného přístupu, která umožňuje zobrazovat, vytvářet, upravovat a odstraňovat zásady podmíněného přístupu Azure AD. Dříve měli toto oprávnění pouze globální správci a správci zabezpečení. Oprávnění této role se dají udělit správcům Intune, aby měli přístup k zásadám podmíněného přístupu.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Označení zařízení vlastněných společností pomocí sériového čísla <!-- 1215070 -->  
Intune teď podporuje nahrávání sériových čísel iOS, macOS a Androidu jako identifikátorů podnikových zařízení. Sériová čísla nemůžete použít k blokování registrace osobních zařízení v tuto chvíli, protože sériová čísla se při registraci neověřují. Blokování osobních zařízení podle sériového čísla se uvolní v blízké budoucnosti.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>Nové vzdálené akce pro zařízení s iOS <!-- 854689 -->
V této verzi jsme přidali dvě nové akce se vzdáleným zařízením pro sdílená zařízení iPad, která spravují aplikaci od třídy Apple:

- [Odhlásit aktuálního uživatele](../remote-actions/device-logout-user.md) – odhlásí aktuálního uživatele zařízení s iOS, které zvolíte.
- [Odebrat uživatele](../remote-actions/device-remove-user.md) – odstraní zvoleného uživatele z místní mezipaměti zařízení se systémem iOS.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Podpora sdílených iPady s aplikací učebny pro iOS <!-- 1044681 -->
V této verzi jsme rozšířili podporu pro správu aplikace učebny iOS, aby zahrnovala studenty, kteří se přihlašují ke sdíleným iPady pomocí svých spravovaných Apple ID.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Změny integrovaných aplikací Intune <!-- 1332306 -->
Dříve obsahovala Intune řadu integrovaných aplikací, které byste mohli rychle přiřadit. Na základě vaší zpětné vazby jsme tento seznam odebrali a nebudete už mít k dispozici integrované aplikace.
Pokud jste už ale nějaké integrované aplikace přiřadili, budou se v seznamu aplikací dál zobrazovat. Tyto aplikace můžete dál přiřazovat podle potřeby.
V novější verzi plánujeme přidat jednodušší metodu pro výběr a přiřazení integrovaných aplikací z Azure Portal.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Jednodušší instalace aplikací Office 365 <!--- 1121362 --->
Nový typ aplikace **office 365 ProPlus** usnadňuje přiřazení aplikací Office 365 proplus 2016 zařízením, která spravujete, na kterých běží nejnovější verze Windows 10. Kromě toho můžete také nainstalovat Microsoft Project a Microsoft Visio, pokud vlastníte licence pro ně. Požadované aplikace jsou společně seskupené a v seznamu aplikací v konzole Intune se zobrazí jako jedna aplikace.
Další informace najdete v tématu [Postup přidání aplikací Office 365 pro Windows 10](../apps/apps-add-office365.md).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>Podpora pro offline aplikace z Microsoft Store pro firmy <!--- 777044 --->
Offline aplikace zakoupené v Microsoft Store pro firmy se teď budou synchronizovat s Azure Portal. Pak můžete tyto aplikace nasadit do skupin zařízení nebo do skupin uživatelů. Offline aplikace se instalují přes Intune, a ne pro Store.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Microsoft Teams je teď součástí seznamu schválených aplikací pro certifikační autoritu na základě aplikace.   <!-- 1257019 -->
Aplikace Microsoft Teams pro iOS a Android je teď součástí schválených aplikací pro zásady podmíněného přístupu na základě aplikací pro Exchange a SharePoint Online. Aplikaci můžete nakonfigurovat pomocí okna Intune App Protection v Azure Portal pro všechny klienty, kteří aktuálně používají podmíněný přístup na základě aplikace.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Integrace spravovaného prohlížeče a proxy aplikací <!-- 1287310 -->
Intune Managed Browser se teď můžou integrovat se službou Azure Proxy aplikací služby AD a umožnit tak uživatelům přístup k interním webům i v případě, že pracují vzdáleně. Uživatelé prohlížeče jednoduše zadají adresu URL webu jako obvykle a Managed Browser směrují požadavek prostřednictvím webové brány proxy aplikace. Další informace najdete v tématu [Správa přístupu k Internetu pomocí zásad spravovaného prohlížeče](../apps/app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Nové nastavení konfigurace aplikace pro Intune Managed Browser <!-- 682951 -->
V této verzi jsme přidali další konfigurace pro aplikaci Intune Managed Browser pro iOS a Android. Pomocí zásad konfigurace aplikace teď můžete nakonfigurovat výchozí domovskou stránku a záložky pro prohlížeč.
Další informace najdete v tématu [Správa přístupu k Internetu pomocí zásad spravovaného prohlížeče](../apps/app-configuration-managed-browser.md) .

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Nastavení BitLockeru pro Windows 10  <!-- 951707 -->
Teď můžete nakonfigurovat nastavení BitLockeru pro zařízení s Windows 10 pomocí nového profilu zařízení Intune. Můžete třeba vyžadovat, aby zařízení byla zašifrovaná, a také nakonfigurovat další nastavení, která se používají, když je BitLocker zapnutý.
Další informace najdete v tématu [nastavení ochrany koncových bodů pro Windows 10 a novější](../protect/endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Nová nastavení pro profil omezení zařízení s Windows 10 <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
V této verzi jsme přidali nová nastavení pro profil omezení zařízení s Windows 10 v následujících kategoriích:

- Windows Defender
- Mobilní síť a připojení
- Prostředí uzamčené obrazovky
- Ochrana osobních údajů
- Hledat
- Windows Spotlight
- Prohlížeč Microsoft Edge

Další informace o nastavení Windows 10 najdete v tématu [Nastavení omezení pro zařízení s Windows 10 a novějším](../configuration/device-restrictions-windows-10.md).


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Portál společnosti aplikace pro Android teď má nové prostředí koncového uživatele pro zásady ochrany aplikací. <!--1305217-->
Na základě zpětné vazby od zákazníků jsme změnili aplikaci Portál společnosti App pro Android, aby zobrazila tlačítko pro **přístup k obsahu společnosti** . Cílem je zabránit tomu, aby koncoví uživatelé zbytečně prošli procesem registrace, když potřebují jenom přístup k aplikacím, které podporují zásady ochrany aplikací, funkce správy mobilních aplikací Intune. Tyto změny si můžete prohlédnout na stránce [novinky v uživatelském rozhraní aplikace](whats-new-app-ui.md) .

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nová akce nabídky pro snadné odebrání Portál společnosti <!--1164569-->
Na základě zpětné vazby od uživatele Portál společnosti aplikace pro Android přidala novou akci nabídky k zahájení odebrání Portál společnosti ze zařízení. Tato akce odebere zařízení ze správy Intune, takže uživatel může aplikaci odebrat ze zařízení. Tyto změny si můžete prohlédnout na stránce [novinky v uživatelském rozhraní aplikace](whats-new-app-ui.md) a v [dokumentaci pro koncové uživatele Androidu](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Vylepšení synchronizace aplikací s Windows 10 Creators Update <!--676505-->
Aplikace Portál společnosti pro Windows 10 teď automaticky zahájí synchronizaci žádostí o instalaci aplikací pro zařízení s Windows 10 Creators Update (verze 1703). Tím se sníží problém při instalaci aplikací během stavu "čeká na synchronizaci". Kromě toho budou moci uživatelé ručně zahájit synchronizaci v rámci aplikace. Tyto změny si můžete prohlédnout na stránce [novinky v uživatelském rozhraní aplikace](whats-new-app-ui.md) .

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nové prostředí s asistencí pro Windows 10 Portál společnosti <!---1058938--->
Aplikace Portál společnosti pro Windows 10 bude obsahovat návod s pokyny Intune pro zařízení, která nejsou identifikovaná nebo zaregistrovaná. Nové prostředí obsahuje podrobné pokyny, pomocí kterých se uživatel zaregistruje do Azure Active Directory (vyžaduje se pro funkce podmíněného přístupu) a pro registraci MDM (vyžaduje se pro funkce správy zařízení). Prostředí s asistencí bude přístupné z Portál společnosti domovské stránce. Uživatelé můžou aplikaci používat i v případě, že nedokončili registraci a registraci, ale budou mít jenom omezené funkce.

Tato aktualizace se zobrazuje jenom na zařízeních s Windows 10 – aktualizace pro výročí (Build 1607) nebo vyšší. Tyto změny si můžete prohlédnout na stránce [novinky v uživatelském rozhraní aplikace](whats-new-app-ui.md) .


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Konzoly pro správu Microsoft Intune a podmíněného přístupu jsou všeobecně dostupné
Oznamujeme obecnou dostupnost nové služby Intune v konzole pro správu Azure Portal a v konzole pro správu podmíněného přístupu. Prostřednictvím Intune v Azure Portal teď můžete spravovat všechny možnosti Intune MAM a MDM v rámci jednoho konsolidovaného prostředí pro správu a využívat seskupování a cílení služby Azure AD. Podmíněný přístup v Azure přináší v jedné sjednocené konzole bohatě funkční možnosti napříč Azure AD a Intune. A z prostředí pro správu umožňuje přechod na platformu Azure používat moderní prohlížeče.

Intune je teď vidět bez popisku **Preview** v Azure Portal na Portal.Azure.com.

Pro existující zákazníky není v tuto chvíli nutné provádět žádnou akci, pokud jste v centru zpráv neobdrželi jednu z řady zpráv požadujících, aby bylo možné migrovat vaše skupiny. Možná jste také obdrželi oznámení centra zpráv s oznámením, že migrace trvá déle z důvodu chyb na naší straně. Usilovně pokračujeme v práci na migraci všech ovlivněných zákazníků.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Vylepšení dlaždic aplikací v aplikaci Portál společnosti pro iOS
Aktualizovali jsme návrh dlaždic aplikace na domovské stránce, aby odrážely barvu značky, kterou jste nastavili pro Portál společnosti. Další informace najdete v tématu [co je nového v uživatelském rozhraní aplikace](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Pro aplikaci Portál společnosti pro iOS je teď dostupný nástroj pro výběr účtu
Uživatelé zařízení se systémem iOS můžou vidět náš nový výběr účtu, když se přihlásí k Portál společnosti, pokud používají svůj pracovní nebo školní účet k přihlášení k ostatním aplikacím Microsoftu. Další informace najdete v tématu [co je nového v uživatelském rozhraní aplikace](whats-new-app-ui.md).

<!-- ########################## -->
## <a name="may-2017"></a>Květen 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Změňte autoritu MDM, aniž byste museli zrušit registraci spravovaných zařízení. <!--1103950-->
Nyní můžete změnit autoritu MDM, aniž byste museli kontaktovat podpora Microsoftu a aniž byste museli zrušit registraci a znovu registrovat stávající spravovaná zařízení. V konzole Configuration Manager můžete [změnit autoritu MDM](/sccm/mdm/deploy-use/change-mdm-authority) z nastavení na Configuration Manager (hybridní) na Microsoft Intune (samostatně) nebo naopak.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Vylepšené oznámení pro spouštěcí PIN kódy Samsung KNOX <!--1087143-->
Když budou koncoví uživatelé potřebovat nastavit spouštěcí PIN kód na zařízeních Samsung KNOX, aby se staly kompatibilní se šifrováním, zobrazí se oznámení zobrazené koncovým uživatelům na přesné místo v aplikaci nastavení při klepnutí na oznámení.  Dříve oznámení vrátilo koncovému uživateli na obrazovku pro změnu hesla.

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Podpora Apple School Manageru (ASM) se sdíleným iPadem <!-- 748864, 770395-->

Intune teď podporuje použití Apple School Manageru (ASM) místo Apple Program registrace zařízení k poskytování předem připraveného zápisu zařízení s iOS. K použití aplikace učebny pro Shared iPady je nutná registrace ASM a je nutná k tomu, aby povolovala synchronizaci dat z ASM až po Azure Active Directory prostřednictvím služby Microsoft School data Sync (SDS). Další informace najdete v tématu [Povolení registrace zařízení s iOS pomocí Apple School Manageru](../enrollment/apple-school-manager-set-up-ios.md).

> [!NOTE]
> Konfigurace sdílených iPady pro práci s aplikací učebny vyžaduje konfigurace vzdělávání iOS v Azure, které ještě nejsou k dispozici.  Tato funkce bude brzy přidána.

### <a name="device-management"></a>Správa zařízení

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Poskytnutí vzdálené pomoci pro zařízení s Androidem pomocí TeamVieweru <!-- 675418 -->

Intune teď může využívat software [TeamViewer](https://www.teamviewer.com) , který se kupuje samostatně, a umožňuje tak poskytovat vzdálenou pomoc uživatelům, kteří používají zařízení s Androidem. Další informace najdete v tématu [poskytnutí vzdálené pomoci pro zařízení s Androidem spravovaná pomocí Intune](../remote-actions/teamviewer-support.md).

### <a name="app-management"></a>Správa aplikací

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>Nové podmínky zásad ochrany aplikací pro MAM <!-- 679864 -->

Nyní můžete nastavit požadavek pro MAM bez uživatelů registrace, který vynutil následující zásady:

- Minimální verze aplikace
- Minimální verze operačního systému
- Minimální verze sady Intune APP SDK cílové aplikace (jenom iOS)

Tato funkce je k dispozici pro Android i iOS. Intune podporuje vynucování minimálních verzí pro verze platforem operačních systémů, verze aplikací a sadu Intune APP SDK. V iOS můžou aplikace, které mají integrovanou sadu SDK, nastavit také minimální vynucování verzí na úrovni sady SDK. Pokud nejsou splněny minimální požadavky prostřednictvím zásad ochrany aplikací na třech různých úrovních uvedených výše, uživatel nebude moci získat přístup k cílové aplikaci. V tomto okamžiku může uživatel buď odebrat svůj účet (pro aplikace s více identitami), zavřít aplikaci nebo aktualizovat verzi operačního systému nebo aplikace.

Můžete také nakonfigurovat další nastavení, abyste poskytovali neblokující oznámení, které doporučuje upgrade operačního systému nebo aplikace. Toto oznámení lze zavřít a aplikace může být použita jako normální.

Další informace najdete v tématu [nastavení zásad ochrany aplikací pro iOS](../apps/app-protection-policy-settings-ios.md) a [nastavení zásad ochrany aplikací pro Android](../apps/app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Konfigurace konfigurace aplikací pro Android for Work <!-- 621621 -->
Některé aplikace pro Android z obchodu podporují možnosti spravované konfigurace, které správci IT umožňují řídit, jak aplikace běží v pracovním profilu. S Intune teď můžete zobrazit konfigurace podporované aplikací a nakonfigurovat je z Azure Portal pomocí návrháře konfigurace nebo editoru JSON. Další informace najdete v tématu [použití konfigurací aplikací pro Android for Work](../apps/app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Nová možnost konfigurace aplikací pro MAM bez registrace <!-- 677969 -->
Nyní můžete vytvářet zásady konfigurace aplikací prostřednictvím MAM bez kanálu registrace. Tato funkce je ekvivalentní k zásadám konfigurace aplikace dostupným v konfiguraci aplikace pro správu mobilních zařízení (MDM). Příklad konfigurace aplikace pomocí MAM bez registrace najdete v tématu [Správa přístupu k Internetu pomocí zásad spravovaného prohlížeče v Microsoft Intune](../apps/app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Konfigurace povolených a blokovaných seznamů adres URL pro Managed Browser <!-- 682960 -->
Teď můžete nakonfigurovat seznam povolených a blokovaných domén a adres URL pro Intune Managed Browser pomocí nastavení konfigurace aplikace v Azure Portal. Tato nastavení se dají nakonfigurovat bez ohledu na to, jestli se používá na spravovaném nebo nespravovaném zařízení. Další informace najdete v tématu [Správa přístupu k Internetu pomocí zásad spravovaného prohlížeče v Microsoft Intune](../apps/app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Zobrazení helpdesku zásady ochrany aplikací <!-- 1069473 -->
Uživatelé IT helpdesku teď můžou zkontrolovat stav licence uživatele a stav aplikací zásady ochrany aplikací přiřazených uživatelům v okně řešení potíží. Podrobnosti najdete v tématu [řešení potíží](./help-desk-operators.md).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Řízení návštěv webu na zařízeních s iOS <!-- 723832 -->
Nyní můžete řídit, které webové stránky můžou uživatelé zařízení se systémem iOS navštívit, a to pomocí jedné z následujících dvou metod:

- Přidejte povolené a blokované adresy URL pomocí integrovaného filtru webového obsahu (jablek).

- Povoluje, aby k nim měl prohlížeč Safari pøístup jenom určené weby. Záložky se vytvářejí v prohlížeči Safari pro každý web, který zadáte.

Další informace najdete v tématu [nastavení filtru webového obsahu pro zařízení s iOS](../configuration/ios-device-features-settings.md#web-content-filter).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Předem nakonfigurovat oprávnění zařízení pro aplikace pro Android for Work <!-- 621614 -->
U aplikací nasazených do pracovních profilů zařízení Android for Work můžete teď nakonfigurovat stav oprávnění pro jednotlivé aplikace.  Aplikace pro Android, které vyžadují oprávnění zařízení, jako je například přístup k umístění nebo fotoaparátu zařízení, ve výchozím nastavení vyzve uživatele k přijetí nebo odmítnutí oprávnění.  Pokud například aplikace používá mikrofon zařízení, pak se koncovému uživateli zobrazí výzva, aby aplikaci udělil oprávnění používat mikrofon. Tato funkce umožňuje definovat oprávnění jménem koncového uživatele.  Můžete nakonfigurovat oprávnění pro) automatické odmítnutí bez upozorňování uživatele, b) automaticky schválit bez upozorňování uživatele, nebo c) vyzvat uživatele k přijetí nebo zamítnutí. Další informace najdete v tématu [Nastavení omezení pro zařízení s Androidem for Work v Microsoft Intune](../configuration/device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Definovat PIN kód pro zařízení s Androidem for Work specifický pro aplikaci <!-- 728976, 1102534 -->
Zařízení s Androidem 7,0 a novějším s pracovním profilem spravovaným jako zařízení s Androidem for Work umožňují správci definovat zásady hesla, které se vztahují jenom na aplikace v pracovním profilu.  Mezi možnosti patří:

- Definovat jenom zásady hesla pro celé zařízení – jedná se o heslo, které uživatel musí použít k odemknutí celého zařízení.
- Definovat jenom zásady hesla pracovního profilu – uživatelé budou vyzváni k zadání hesla při každém otevření jakékoli aplikace v pracovním profilu.
- Definujte zásady zařízení i pracovní profil – správce IT má možnost definovat jak zásady pro přístupový kód zařízení, tak zásady hesla pracovního profilu, které mají různou sílu (například PIN kód se čtyřmi číslicemi k odemknutí zařízení, ale kód PIN pro otevření jakékoli pracovní aplikace se šesti číslicemi).

Další informace najdete v tématu [Nastavení omezení pro zařízení s Androidem for Work v Microsoft Intune](../configuration/device-restrictions-android-for-work.md).

> [!NOTE]
> To je dostupné jenom pro Android 7,0 a novější.  Ve výchozím nastavení může koncový uživatel použít dva samostatně definované PIN kódy, nebo se může rozhodnout zkombinovat tyto dva nadefinované PIN kódy do nejpřísnější z těchto dvou.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Nová nastavení pro zařízení s Windows 10 <!-- 978585 -->
Přidali jsme nová [Nastavení omezení pro zařízení s Windows](../configuration/device-restrictions-windows-10.md) , která řídí funkce, jako jsou bezdrátové displeje, zjišťování zařízení, přepínání úloh a chybové zprávy SIM karty.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Aktualizace konfigurace certifikátu <!-- 918991 and 823198 -->
Při vytváření profilu certifikátu SCEP je pro <strong>Formát názvu subjektu</strong>k dispozici <strong>vlastní</strong> možnost pro zařízení s iOS, Androidem a Windows. Před touto aktualizací bylo <strong>vlastní</strong> pole k dispozici pouze pro zařízení se systémem iOS. Další informace najdete v tématu [Vytvoření profilu certifikátu SCEP](../protect/certificates-profile-scep.md).

Při vytváření profilu certifikátu PKCS pro **alternativní název subjektu**je k dispozici **vlastní atribut služby Azure AD** . Možnost **oddělení** je dostupná, když vyberete **vlastní atribut Azure AD**. Další informace najdete v tématu [Vytvoření profilu certifikátu PKCS](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Konfigurace více aplikací, které se dají spustit, když je zařízení s Androidem v celoobrazovkovém režimu <!-- 662059 -->
Když je zařízení s Androidem v celoobrazovkovém režimu, mohli byste dřív nakonfigurovat jenom jednu aplikaci, která byla povolená ke spuštění. Teď můžete nakonfigurovat víc aplikací pomocí ID aplikace, adresy URL obchodu nebo výběrem aplikace pro Android, kterou už spravujete. Další informace najdete v tématu [Nastavení celoobrazovkového režimu](../configuration/device-restrictions-android.md#kiosk).

<!-- ########################## -->
## <a name="april-2017"></a>Duben 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Podpora pro správu aplikace pro Apple učeben
Na zařízeních iPad teď můžete spravovat aplikaci učebny iOS. Nastavte aplikaci učebny na iPadu učitelů se správnými daty třídy a studenta a pak nakonfigurujte iPady pro studenty na třídu, abyste je mohli řídit pomocí aplikace.
Podrobnosti najdete v tématu [Konfigurace nastavení vzdělávání iOS](education-settings-configure-ios.md).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Podpora spravovaných možností konfigurace pro aplikace pro Android <!-- 621621 -->
Aplikace pro Android v obchodě Play, které podporují možnosti spravované konfigurace, se teď dají nakonfigurovat přes Intune.  Tato funkce umožňuje zobrazit seznam hodnot konfigurace podporovaných aplikací a poskytuje prostředí s asistencí pro první třídu, které jim umožní nakonfigurovat tyto hodnoty.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nové zásady Androidu pro komplexní PIN kódy <!-- 722069 -->
V profilu zařízení s Androidem pro zařízení s Androidem 5,0 a novějším teď můžete nastavit požadovaný typ [hesla](../configuration/device-restrictions-android.md#password) na číselné komplexní.  Pomocí tohoto nastavení můžete uživatelům zařízení zabránit v vytváření kódu PIN, který obsahuje opakující se nebo po sobě jdoucí čísla, například 1111 nebo 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Další podpora pro zařízení s Androidem for Work
- **Správa nastavení hesla a pracovního profilu** <!-- 612808 -->

  Tato nová zásada omezení pro zařízení s Androidem for Work teď umožňuje spravovat nastavení hesla a pracovního profilu na zařízeních s Androidem for Work, která spravujete.

- **Povolení sdílení dat mezi pracovními a osobními profily** <!-- 1045102 -->

Tento profil omezení pro zařízení s Androidem for Work má teď nové možnosti, které vám pomůžou nakonfigurovat sdílení dat mezi pracovními a osobními profily.

- **Omezit kopírování a vkládání mezi pracovními a osobními profily** <!-- 1046094 -->

  Nový vlastní profil zařízení pro zařízení s Androidem for Work teď umožňuje omezit, jestli jsou povolené akce kopírování a vkládání mezi pracovními a osobními aplikacemi.

Další informace najdete v tématu [omezení pro zařízení s Androidem for Work](../configuration/device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Přiřazení obchodních aplikací k zařízením s iOS a Androidem <!-- 1057568 -->
K uživatelům nebo zařízením teď můžete přiřazovat obchodní aplikace pro [iOS](../apps/lob-apps-ios.md) (soubory. IPA) a [Android](../apps/lob-apps-android.md) (soubory. apk).


### <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Nové zásady pro zařízení s iOS <!-- 723774, 723815, 723826, 723830 -->
- **Aplikace na domovské obrazovce** – určuje, které aplikace uživatelé uvidí na [domovské obrazovce zařízení s iOS](../configuration/ios-device-features-settings.md#home-screen-layout). Tato zásada změní rozložení domovské obrazovky, ale neimplementuje žádné aplikace.

- **Připojení k zařízením pro tisk přes tisk** – řídí, ke kterým zařízením pro průchozí [Tisk](../configuration/ios-device-features-settings.md#airprint) (síťové tiskárny) se můžou koncoví uživatelé zařízení se systémem iOS připojit.

- **Připojení k zařízením AirPlay** – řídí, ke kterým [AirPlay zařízením](../configuration/ios-device-features-settings.md) (jako Apple TV) se můžou koncoví uživatelé zařízení se systémem iOS připojit.

- **Vlastní zpráva zamykací obrazovky** – konfiguruje vlastní zprávu, kterou uživatelé uvidí na zamykací obrazovce zařízení s iOS, které nahradí výchozí zprávu zamykací obrazovky. Další informace najdete v tématu [Aktivace režimu ztráty na zařízeních s iOS](../remote-actions/device-lost-mode.md) .

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Omezení nabízených oznámení pro aplikace pro iOS <!-- 723767 -->
V profilu omezení zařízení v Intune teď můžete nakonfigurovat následující [Nastavení oznámení](../configuration/ios-device-features-settings.md#app-notifications) pro zařízení s iOS:

- Zcela zapnout nebo vypnout oznámení pro zadanou aplikaci.
- Zapněte nebo vypněte oznámení v centru oznámení pro zadanou aplikaci.
- Zadejte typ výstrahy, buď **žádný**, **banner**, nebo **modální výstrahu**.
- Určete, zda jsou pro tuto aplikaci povoleny badge.
- Určete, zda jsou povoleny zvukové oznámení.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Konfigurace aplikací pro iOS tak, aby se spouštěly samostatně v režimu jedné aplikace <!-- 737837 -->
Pomocí profilu zařízení v Intune teď můžete nakonfigurovat, aby zařízení s iOS spouštěla zadané aplikace v [autonomním režimu jedné aplikace](../configuration/device-restrictions-ios.md#autonomous-single-app-mode). Když je tento režim nakonfigurovaný a aplikace je spuštěná, zařízení je uzamčené, aby ji mohla spustit jenom aplikace. Příkladem je, že nakonfigurujete aplikaci, která umožní uživatelům provést test na zařízení. Až se akce aplikace dokončí nebo tuto zásadu odeberete, zařízení se vrátí do normálního stavu.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Konfigurace důvěryhodných domén pro e-mail a procházení webu na zařízeních s iOS <!-- 723765 -->
V profilu omezení zařízení s iOS teď můžete nakonfigurovat následující [nastavení domény](../configuration/device-restrictions-ios.md#domains):

- **Neoznačené e-mailové domény** – e-maily odeslané nebo přijímané uživatelem, které se neshodují s doménami, které tady zadáte, budou označeny jako nedůvěryhodné.

- **Spravované webové domény** – dokumenty stažené z adres URL, které zadáte tady, se budou považovat za spravované (jenom Safari).  

- **Domény pro automatické vyplňování hesel v Safari** – uživatelé můžou ukládat hesla v Safari jenom z adres URL, které odpovídají vzorům, které tady zadáte. Chcete-li použít toto nastavení, musí být zařízení v režimu pod dohledem a nesmí být nakonfigurováno pro více uživatelů. (iOS 9.3 +)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Aplikace VPP dostupné v iOS Portál společnosti <!-- 748782 -->
Nyní můžete přiřadit aplikace VPP (Volume koupené v iOS) jako **dostupné** instalace koncovým uživatelům. Koncoví uživatelé budou k instalaci aplikace potřebovat účet Apple Store.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Synchronizovat e-knihy z Apple VPP Storu <!-- 800878 -->
Teď můžete [Synchronizovat knihy](../apps/vpp-apps-ios.md) , které jste zakoupili z Apple Storu v rámci multilicenčního programu s Intune, a přiřadit je uživatelům.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Správa více uživatelů pro zařízení se Samsung KNOX standardem <!-- 971988 -->
U zařízení, která používají Samsung KNOX Standard, se teď podporuje [Správa více uživatelů](../enrollment/android-enroll.md) pomocí Intune. To znamená, že koncoví uživatelé se můžou přihlašovat a odhlásit ze zařízení pomocí přihlašovacích údajů Azure Active Directory a zařízení je centrálně spravované bez ohledu na to, jestli se používá.  Když se koncoví uživatelé přihlásí, mají přístup k aplikacím a na ně se vztahují všechny zásady. Když se uživatel odhlásí, všechna data aplikace se vymažou.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Další nastavení omezení pro zařízení s Windows <!-- 818566 -->
Přidali jsme podporu dalších [Nastavení omezení pro zařízení s Windows](../configuration/device-restrictions-windows-10.md) , jako je další podpora prohlížeče Microsoft Edge, přizpůsobení zamykací obrazovky zařízení, přizpůsobení nabídky Start, Tapeta sady vyhledávání ve Windows Spotlight a nastavení proxy serveru.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Podpora více uživatelů pro Windows 10 Creators Update <!-- 822547 -->
Přidali jsme podporu [správy více uživatelů](../enrollment/windows-enroll.md) pro zařízení, která používají Windows 10 Creators Update a jsou Azure Active Directory připojená k doméně. To znamená, že když se k zařízení přihlásí různí standardní uživatelé pomocí svých přihlašovacích údajů Azure AD, dostanou všechny aplikace a zásady přiřazené jejich uživatelskému jménu. Uživatelé teď nemůžou používat Portál společnosti pro samoobslužné scénáře, jako je instalace aplikací.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Nové spuštění pro počítače s Windows 10<!-- 1004830 -->
Nyní je k dispozici nová [Akce zařízení začít](../remote-actions/device-fresh-start.md) znovu pro počítače s Windows 10.  Když vydáte tuto akci, všechny aplikace, které byly nainstalovány v počítači, se odeberou a počítač se automaticky aktualizuje na nejnovější verzi Windows. To se dá využít k odebrání předem nainstalovaných aplikací pro výrobce OEM, které se často dodávají s novým počítačem. Můžete nakonfigurovat, jestli se při vydávání této akce zařízení budou uchovávat data uživatelů.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Další způsoby upgradu Windows 10 <!-- 903672 -->
Nyní můžete vytvořit [zásadu upgradu edice pro upgrade zařízení](../configuration/edition-upgrade-configure-windows-10.md) na následující další edice Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional – vzdělávání
- Windows 10 Professional – vzdělávání N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Hromadná registrace zařízení s Windows 10 <!-- 747607 -->
Teď můžete připojit velký počet zařízení s Windows 10 Creators Update, abyste Azure Active Directory a Intune s Windows Configuration designerem (WCD). Pokud chcete pro svého tenanta Azure AD povolit [hromadnou registraci MDM](../enrollment/windows-bulk-enroll.md) , vytvořte zřizovací balíček, který připojí zařízení k TENANTOVI Azure AD pomocí nástroje Windows Configuration Designer a nainstaluje balíček na zařízení ve vlastnictví firmy, která chcete hromadně zaregistrovat a spravovat. Po použití balíčku na vaše zařízení se připojí k Azure AD, zaregistrují se v Intune a budou připravení pro uživatele Azure AD, aby se přihlásili.  Uživatelé Azure AD jsou na těchto zařízeních standardními uživateli a obdrží přiřazené zásady a požadované aplikace. Scénáře samoobslužné a Portál společnosti se aktuálně nepodporují.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Nové nastavení MAM pro PIN a spravovaná umístění úložiště <!-- 581122, 736644 -->
K dispozici jsou teď dvě nová nastavení aplikací, která vám pomůžou se scénáři správy mobilních aplikací (MAM):

- **Zakázat PIN kód aplikace, když je PIN kód zařízení spravovaný** – zjistí, jestli se na zaregistrovaném zařízení nachází PIN kód zařízení, a pokud ano, vynechá PIN kód aplikace aktivovaný zásadami ochrany aplikací. Toto nastavení umožní, aby se snížil počet, kolikrát se zobrazí výzva k zadání kódu PIN uživatelům, kteří otevřou aplikaci s podporou MAM na zaregistrovaném zařízení. Tato funkce je k dispozici pro Android i iOS.

- **Vyberte, do kterých služeb úložiště se můžou ukládat firemní data** – umožní vám určit umístění úložiště, do kterých se mají ukládat podniková data. Uživatelé můžou ukládat do vybraných služeb umístění úložiště, což znamená, že všechny ostatní služby umístění úložiště, které nejsou uvedené, se zablokují.

  Seznam podporovaných služeb umístění úložiště:

  - OneDrive
  - Firemní SharePoint Online
  - Místní úložiště

### <a name="help-desk-troubleshooting-portal----907448---"></a>Portál helpdesku pro řešení potíží <!-- 907448 -->
Nový [portál pro řešení potíží](../help-desk-operators.md) umožňuje operátorům helpdesku a správcům Intune zobrazit uživatele a jejich zařízení a provádět úlohy, které vám pomůžou vyřešit technické problémy služby Intune.

<!-- ########################## -->
## <a name="march-2017"></a>Březen 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Podpora režimu ztráty iOS <!--431695-->
V případě zařízení se systémem iOS 9,3 a novějším Intune přidal podporu pro **režim ztráty**. Teď můžete zařízení uzamknout, aby se předešlo používání a zobrazilo se zprávy a kontaktní telefonní číslo na zamykací obrazovce zařízení.

Koncový uživatel nebude moct zařízení odemknout, dokud správce nezakáže režim ztráty. Když je režim ztráty zapnutý, můžete pomocí akce **Najít zařízení** zobrazit zeměpisnou polohu zařízení na mapě v konzole Intune.

Zařízení musí být zařízení s iOS vlastněné firmou, které je zaregistrované prostřednictvím programu DEP, které je v režimu pod dohledem.

Další informace najdete v tématu [co je Správa zařízení Microsoft Intune](../remote-actions/device-management.md)?

### <a name="improvements-to-device-actions-report---677150--"></a>Vylepšení sestavy akcí zařízení <!--677150-->
Provedli jsme vylepšení sestavy akcí zařízení za účelem zvýšení výkonu. Nyní můžete filtrovat sestavu podle stavu. Sestavu můžete například filtrovat tak, aby zobrazovala pouze akce zařízení, které byly dokončeny. "

### <a name="custom-app-categories---748805--"></a>Vlastní kategorie aplikací <!--748805-->
Pro aplikace, které přidáváte do Intune, teď můžete vytvářet, upravovat a přiřazovat kategorie. Kategorie se v současné době dají zadat jenom v angličtině.
Podívejte se, [jak přidat aplikaci do Intune](../apps/apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Přiřazení obchodních aplikací uživatelům s nezaregistrovanými zařízeními <!--748823-->
Obchodní aplikace teď můžete přiřazovat ze Storu uživatelům bez ohledu na to, jestli jsou jejich zařízení zaregistrovaná v Intune. Pokud zařízení uživatele není zaregistrované v Intune, musí se místo aplikace Portál společnosti nainstalovat na web Portál společnosti.

### <a name="new-compliance-reports---846671--"></a>Nové sestavy dodržování předpisů <!--846671-->
Nyní máte sestavy o dodržování předpisů, které vám poskytnou stav dodržování předpisů pro zařízení ve vaší společnosti, a umožní vám rychle řešit problémy související s dodržováním předpisů zjištěné vašimi uživateli. Můžete zobrazit informace o

- Celkový stav dodržování předpisů u zařízení
- Stav dodržování předpisů pro jednotlivá nastavení
- Stav dodržování předpisů pro jednotlivé zásady

Pomocí těchto sestav můžete také přejít k podrobnostem jednotlivých zařízení a zobrazit konkrétní nastavení a zásady, které mají vliv na toto zařízení.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Přímý přístup ke scénářům registrace Apple <!--951869-->
U účtů Intune vytvořených po lednu 2017 má Intune povolený přímý přístup ke scénářům registrace Apple pomocí úlohy registrace zařízení v Azure Portal. Dříve byl náhled registrace Apple dostupný jenom z odkazů v Azure Portal. Účty Intune vytvořené před lednem 2017 budou vyžadovat jednorázovou migraci, než budou tyto funkce k dispozici v Azure. Plán pro migraci se zatím neoznámil, ale podrobnosti budou k dispozici co nejrychleji. Pokud Váš existující účet nemá přístup k verzi Preview, důrazně doporučujeme vytvořit zkušební účet pro otestování nového prostředí.


<!-- ########################## -->
## <a name="february-2017"></a>Únor 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Možnost omezit registraci mobilního zařízení <!--747600, 795782-->
Intune přidává nová omezení registrace, která určují, které platformy mobilních zařízení se můžou registrovat. Intune odděluje platformy mobilních zařízení jako iOS, macOS, Android, Windows a Windows Mobile.

- Omezení Registrace mobilních zařízení neomezuje registraci klienta na počítači.  
- Jenom pro iOS a Android je k dispozici jedna další možnost blokování registrace zařízení v osobním vlastnictví.

Intune označí všechna nová zařízení jako osobní, pokud správce IT neprovede akci jejich označení jako vlastněná podnikem, jak je popsáno v [tomto článku](../enrollment/device-enrollment.md).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Zobrazit všechny akce na spravovaných zařízeních <!--677150-->
Nová sestava __akcí zařízení__ ukazuje, kdo provedl vzdálené akce, jako je obnovení továrního nastavení v zařízeních, a navíc zobrazuje stav této akce. Podívejte [se, co je Správa zařízení?](../remote-actions/device-management.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Nespravovaná zařízení mají přístup k přiřazeným aplikacím. <!--664691-->
V rámci změn v návrhu na Portál společnosti webu budou uživatelé iOS a Android moci instalovat aplikace, které jsou jim přiřazené, jako "k dispozici bez registrace" na nespravovaných zařízeních. Pomocí svých přihlašovacích údajů pro Intune se uživatelé budou moci přihlásit k webu Portál společnosti a zobrazit seznam aplikací, které jsou jim přiřazeny. Balíčky aplikací v aplikacích, které jsou k dispozici bez registrace, se dají stáhnout prostřednictvím webu Portál společnosti. U aplikací, které vyžadují registraci k instalaci, tato změna neovlivní, protože uživatelé budou vyzváni k registraci zařízení, pokud chtějí tyto aplikace nainstalovat.

### <a name="custom-app-categories---748805--"></a>Vlastní kategorie aplikací <!--748805-->
Pro aplikace, které přidáváte do Intune, teď můžete vytvářet, upravovat a přiřazovat kategorie. Kategorie se v současné době dají zadat jenom v angličtině.
Podívejte se, [jak přidat aplikaci do Intune](../apps/apps-add.md).

### <a name="display-device-categories---814654--"></a>Zobrazit kategorie zařízení <!--814654-->
Kategorii zařízení teď můžete zobrazit jako sloupec v seznamu zařízení. Kategorie můžete také upravit v části vlastnosti v okně vlastností zařízení. Podívejte se, [jak přidat aplikaci do Intune](../apps/apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Konfigurace nastavení web Windows Update pro firmy <!--776716-->

Windows jako služba představuje nový způsob poskytování aktualizací pro Windows 10. Od Windows 10 budou všechny nové aktualizace funkcí a aktualizace kvality obsahovat obsah všech předchozích aktualizací. To znamená, že pokud si nainstalujete nejnovější aktualizaci, zjistíte, že jsou vaše zařízení s Windows 10 úplně v aktuálním stavu. Na rozdíl od předchozích verzí Windows se teď musí nainstalovat celá aktualizace namísto části aktualizace.

Pomocí web Windows Update pro firmy můžete zjednodušit možnosti správy aktualizací, abyste nemuseli schvalovat jednotlivé aktualizace pro skupiny zařízení. Ve svých prostředích můžete stále spravovat rizika konfigurací strategie zavedení aktualizací a web Windows Update se ujistit, že jsou aktualizace nainstalované ve správnou dobu. Microsoft Intune poskytuje možnost konfigurovat nastavení aktualizací na zařízeních a poskytuje možnost odložit instalaci aktualizací. Intune aktualizace neukládá, ale pouze přiřazení zásad aktualizace. Zařízení přistupují web Windows Update přímo pro aktualizace. Pomocí Intune můžete konfigurovat a spravovat **aktualizační kanály Windows 10**. Aktualizační kanál obsahuje skupinu nastavení, která konfigurují, kdy a jak se budou aktualizace Windows 10 instalovat. Podrobnosti najdete v tématu [Konfigurace nastavení web Windows Update pro firmy](../protect/windows-update-for-business-configure.md).
