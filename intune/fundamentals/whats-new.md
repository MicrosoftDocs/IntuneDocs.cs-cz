---
title: Novinky v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Zjistěte, jaké novinky přináší portál Intune Azure.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/09/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 311941c3981e5883d392359dc0919bb85156c4be
ms.sourcegitcommit: fb72b19986f34907d228c856d2e6949751ec02a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2020
ms.locfileid: "75920095"
---
# <a name="whats-new-in-microsoft-intune"></a>Co je nového v Microsoft Intune

Zjistěte, jaké novinky každý týden přináší Microsoft Intune. Můžete také najít [důležitá oznámení](#notices), [Minulá vydání](whats-new-archive.md)a informace o [tom, jak jsou aktualizace služby Intune vydané](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728). 

> [!Note]
> Zavedení každé [měsíční aktualizace](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) může trvat až tři dny a bude v tomto pořadí:
>
> - Den 1: Asie a Tichomoří (APAC)
> - Den 2: Evropa, Střední východ, Afrika (Evropa)
> - Den 3: Severní Amerika
>
> Některé funkce můžou vycházet v průběhu několika týdnů a nemusí být k dispozici všem zákazníkům hned první týden.
>
> Seznam nadcházejících funkcí ve verzi najdete na [stránce pro vývoj na webu](in-development.md) .

**Informační kanál RSS**: po aktualizaci této stránky se zobrazí upozornění zkopírováním a vložením následující adresy URL do čtečky informačních kanálů: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Device security
### Intune apps
### Monitor and troubleshoot
### Role-based access control
-->  

<!-- ########################## -->
## <a name="week-of-january-6-2020"></a>Týden od 6. ledna 2020

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Správa aplikací

#### <a name="smime-support-for-microsoft-outlook-for-ios---2669398---"></a>Podpora S/MIME pro Microsoft Outlook pro iOS<!-- 2669398 -->
Intune podporuje doručování podpisových a šifrovacích certifikátů S/MIME, které se dají používat s Outlookem pro iOS na zařízeních s iOS. Další informace najdete v tématu [citlivostní označování a ochrana v Outlooku pro iOS a Android](https://aka.ms/omsmime).

#### <a name="cache-win32-app-content-using-microsoft-connected-cache-server---6030314---"></a>Mezipaměť obsahu aplikace Win32 pomocí serveru s připojenou mezipamětí společnosti Microsoft<!-- 6030314 -->
Server Microsoft Connected cache můžete nainstalovat do distribučních bodů Configuration Manager pro ukládání obsahu aplikace Win32 v Intune. Další informace najdete v tématu věnovaném [podpoře aplikací pro Intune Win32 v Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/microsoft-connected-cache#bkmk_intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="windows-10-administrative-templates-admx-profiles-now-support-scope-tags---5137390-wnready--"></a>Profily šablon pro správu Windows 10 (ADMX) nyní podporují značky oboru <!--5137390 wnready-->
Nyní můžete přiřadit značky oboru k profilům šablony pro správu (ADMX). Provedete to tak, že přejdete na **zařízení** > **Intune** > **konfiguračních profilů** > vyberte profil šablon pro správu v seznamu > **vlastnosti** > **značky oboru**. Další informace o značkách oboru naleznete v tématu [přiřazení značek oboru jiným objektům](../fundamentals/scope-tags.md#assign-scope-tags-to-other-objects).

<!-- ########################## -->
## <a name="week-of-december-30-2019"></a>Týden od 30. prosince 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Správa aplikací

#### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices---4851745---"></a>Načtení osobního obnovovacího klíče ze zařízení s macOS šifrovaným zařízením MEM<!-- 4851745 -->
Koncoví uživatelé mohou načíst svůj osobní obnovovací klíč (klíč trezoru) pomocí aplikace Portál společnosti pro iOS. Zařízení, které má osobní obnovovací klíč, musí být zaregistrované v Intune a zašifrované pomocí trezoru služby prostřednictvím Intune. Pomocí aplikace Portál společnosti pro iOS může koncový uživatel na své šifrované zařízení macOS načíst svůj osobní obnovovací klíč tak, že klikne na **získat obnovovací klíč**. Obnovovací klíč můžete z Intune načíst taky tak, že vyberete **zařízení** > *šifrovaných a zaregistrovaných zařízení MacOS* > **získat obnovovací klíč**. Další informace o trezoru úložišť najdete v tématu [šifrování trezoru MacOS](~/protect/encrypt-devices.md#filevault-encryption-for-macos).

#### <a name="ios-and-ipados-user-licensed-vpp-apps---5619268---"></a>aplikace VPP pro iOS a iPadOS, které jsou pro uživatele licencované<!-- 5619268 -->
Pro uživatelem zaregistrovaná zařízení s iOS a iPadOS se koncovým uživatelům už nebudou prezentovat nově vytvořeným aplikacím VPP licencovaným na zařízení, které jsou nasazené jako dostupné. Koncoví uživatelé ale budou dál zobrazovat všechny aplikace VPP licencované uživateli v rámci Portál společnosti. Další informace o aplikacích VPP najdete v tématu [Správa aplikací pro iOS a MacOS zakoupených prostřednictvím Apple Volume purchase program s Microsoft Intune](~/apps/vpp-apps-ios.md).

<!-- ########################## -->
## <a name="week-of-december-23-2019"></a>Týden od 23. prosince 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Správa aplikací

#### <a name="notice---windows-10-1703-rs2-will-be-moving-out-of-support----5026679---"></a>Oznámení – systém Windows 10 1703 (RS2) se bude pohybovat mimo podporu. <!-- 5026679 -->
Od 9. října 2018 se Windows 10 1703 (RS2) přesunul z podpory platformy Microsoft pro edice Home, pro a pro Workstation. Pro edice Windows 10 Enterprise a školství se v systému Windows 10 1703 (RS2) přesunula podpora platformy 8. října 2019. Od 26. prosince 2019 budeme aktualizovat minimální verzi Windows Portál společnosti aplikace na Windows 10 1709 (RS3). Počítače s verzemi staršími než 1709 nebudou nadále získávat aktualizované verze aplikace z Microsoft Store. Tuto změnu jsme dřív komunikovali zákazníkům, kteří spravují starší verze Windows 10 prostřednictvím centra zpráv. Další informace najdete v tématu [seznam faktů pro životní cyklus systému Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

<!-- ########################## -->

## <a name="week-of-december-16-2019"></a>Týden od 16. prosince 2019

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="updates-to-administrative-templates-for-windows-10-devices----5941568---"></a>Aktualizace Šablony pro správu pro zařízení s Windows 10 <!-- 5941568 -->

Šablony ADMX v Microsoft Intune můžete použít k řízení a správě nastavení pro Microsoft Edge, Office a Windows. Šablony pro správu v Intune provedli následující aktualizace nastavení zásad:

- Přidání podpory pro Microsoft Edge verze 78 a 79.
- Obsahuje 11. listopadu 2019 soubory ADMX v [souborech šablon pro správu (ADMX/ADML) a nástroji pro přizpůsobení sady Office pro office 365 ProPlus, office 2019 a office 2016](https://www.microsoft.com/download/details.aspx?id=49030).

Další informace o šablonách ADMX v Intune najdete v tématu [použití šablon Windows 10 ke konfiguraci nastavení zásad skupiny v Microsoft Intune](../configuration/administrative-templates-windows.md).

Platí pro:

- Windows 10 a novější

## <a name="week-of-december-9-2019-1912-service-release"></a>Týden z 9. prosince 2019 (verze 1912 Service)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Správa aplikací

#### <a name="migrating-to-microsoft-edge-for-managed-browsing-scenarios---5173762---"></a>Migrace na Microsoft Edge pro spravované scénáře procházení<!-- 5173762 -->
Až se přiblížíme k odchodu Intune Managed Browser, provedli jsme změny v zásadách ochrany aplikací, abychom zjednodušili kroky potřebné k přesunu uživatelů do hraničních zařízení. Aktualizovali jsme možnosti nastavení zásad ochrany aplikací **omezit přenos webového obsahu s jinými aplikacemi** na jednu z těchto možností:

- Libovolná aplikace
- Intune Managed Browser
- Microsoft Edge
- Nespravovaný prohlížeč 

Když vyberete **Microsoft Edge**, koncovým uživatelům se zobrazí zpráva podmíněného přístupu s upozorněním, že pro spravované scénáře procházení se vyžaduje Microsoft Edge. Budou se vám zobrazovat výzvy ke stažení a přihlášení k Microsoft Edge pomocí svých účtů AAD, pokud se ještě neudělaly.  To bude odpovídat na cílení aplikací s povoleným MAM s nastavením konfigurace aplikace `com.microsoft.intune.useEdge` nastavenou na **hodnotu true**. Existující zásady ochrany aplikací, které používaly nastavení **prohlížeče spravované pomocí zásad** , budou teď **Intune Managed Browser** vybrané a v chování se zobrazí žádná změna. To znamená, že uživatelé uvidí zprávy o používání Microsoft Edge, pokud jste nastavili nastavení konfigurace aplikace **useEdge** na **hodnotu true**. Pro všechny zákazníky, kteří využívají spravované scénáře procházení, doporučujeme aktualizovat zásady ochrany aplikací tak, aby **omezili přenos webového obsahu s jinými aplikacemi** , aby uživatelům viděli správné pokyny k přechodu na Microsoft Edge bez ohledu na to, ze které aplikace spouští odkazy. 

#### <a name="configure-app-notification-content-for-organization-accounts---2576686----"></a>Konfigurace obsahu oznámení aplikace pro účty organizace<!-- 2576686  -->
Zásady ochrany aplikací Intune (aplikace) na zařízeních s Androidem a iOS umožňují řídit obsah oznámení aplikací pro účty org. Můžete vybrat možnost (povolení, blokování dat organizace nebo blokované) a určit, jak se budou zobrazovat oznámení pro účty organizace pro vybranou aplikaci. Tato funkce vyžaduje podporu aplikací a nemusí být k dispozici pro všechny aplikace s podporou aplikací. Toto nastavení bude podporovat Outlook pro iOS verze 4.15.0 (nebo novější) a Outlook pro Android 4.83.0 (nebo novější). Nastavení je k dispozici v konzole nástroje, ale funkce začnou platit až od 16. prosince 2019. Další informace o aplikaci najdete v tématu [co jsou zásady ochrany aplikací?](../apps/app-protection-policy.md).

#### <a name="microsoft-app-icons-update--4677605----"></a>Aktualizace ikon aplikace Microsoft<!--4677605  -->
Ikony používané pro aplikace Microsoftu v podokně cílení aplikace pro zásady ochrany aplikací a zásady konfigurace aplikací se aktualizovaly.

#### <a name="require-use-of-approved-keyboards-on-android--4761794----"></a>Vyžadovat použití schválených klávesnic v Androidu<!--4761794  -->
V rámci zásad ochrany aplikací můžete určit nastavení [**schválených klávesnic**](../apps/app-protection-policy-settings-android.md#data-protection) pro správu, které klávesnice pro Android se dají používat se spravovanými aplikacemi pro Android. Když uživatel otevře spravovanou aplikaci a ještě nepoužívá schválenou klávesnici pro tuto aplikaci, zobrazí se výzva k přepnutí na jednu ze schválených klávesnic, které už jsou na svém zařízení nainstalované. V případě potřeby se jim zobrazí odkaz pro stažení schválené klávesnice z Obchod Google Play, kterou si můžete nainstalovat a nastavit. Uživatel může upravit textová pole ve spravované aplikaci, když jejich aktivní klávesnice není jednou ze schválených klávesnic.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="updated-single-sign-on-experience-for-apps-and-websites-on-your-ios-ipados-and-macos-devices---4999578----"></a>Aktualizované prostředí jednotného přihlašování pro aplikace a weby na zařízeních s iOS, iPadOS a macOS<!-- 4999578  -->
Intune přidal pro zařízení s iOS, iPadOS a macOS další nastavení jednotného přihlašování (SSO). Teď můžete nakonfigurovat rozšíření aplikace jednotného přihlašování napsané vaší organizací nebo vaším poskytovatelem identity. Tato nastavení slouží ke konfiguraci bezproblémového jednotného přihlašování pro aplikace a weby, které používají moderní metody ověřování, jako je OAuth a typu Saml2. 

Tato nová nastavení se rozšíří na předchozí nastavení rozšíření aplikace jednotného přihlašování a integrovaného rozšíření protokolu Kerberos (**zařízení** > **Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS/iPadOS** nebo **MacOS** pro typ platformy > **funkce zařízení** pro typ profilu). 

Pokud chcete zobrazit celou škálu nastavení rozšíření aplikace jednotného přihlašování, přejděte na adresu [SSO v iOS](../configuration/ios-device-features-settings.md#single-sign-on-app-extension) a [jednotné přihlašování v MacOS](../configuration/macos-device-features-settings.md#single-sign-on-app-extension).

Platí pro:

- iOS/iPadOS
- macOS

#### <a name="we-have-updated-two-device-restriction-settings-for-ios-and-ipados-devices-to-correct-their-behavior---5701352-wnready-----"></a>Aktualizovali jsme dvě nastavení omezení pro zařízení s iOS a iPadOS, abyste mohli opravit jejich chování.<!-- 5701352 WNReady   -->
V případě zařízení se systémem iOS můžete vytvořit profily omezení zařízení, které **umožní dopředné aktualizace PKI** a **blokovat režim s omezeným přístupem USB** (**zařízení** > **konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS/iPadOS** pro omezení platformy > **zařízení** pro typ profilu). Před touto verzí bylo nastavení uživatelského rozhraní a popisy pro následující nastavení nesprávné a byly nyní opraveny. Od této verze je chování nastavení následující:

**Zablokovat vysoce Air aktualizace PKI**: **blok** znemožní uživatelům přijímat aktualizace softwaru, pokud není zařízení připojené k počítači. **Nenakonfigurováno** (výchozí): umožňuje zařízení přijímat aktualizace softwaru bez připojení k počítači.
- Dříve toto nastavení umožňuje nakonfigurovat ho jako: **Povolit**, které umožní uživatelům přijímat aktualizace softwaru bez připojení zařízení k počítači.
**Povolí příslušenství USB, když je zařízení zamknuté**: **umožňuje dovolit** , aby data Exchange příslušenství využívala zařízení, které je po celou hodinu uzamčené. **Nenakonfigurováno** (výchozí) neaktualizuje režim omezeného portu USB na zařízení a příslušenství USB bude zablokováno v přenosu dat ze zařízení, pokud je po celou hodinu uzamčené.
- Dříve toto nastavení umožňuje nakonfigurovat ho jako **blok** pro zakázání režimu omezeného na zařízení USB na zařízeních pod dohledem.

Další informace o nastavení, které můžete nakonfigurovat, najdete v tématu [nastavení zařízení s iOS a iPadOS, které umožňuje povolit nebo zakázat funkce využívající Intune](../configuration/device-restrictions-ios.md).

Tato funkce platí pro:

- Operační systém/iPadOS

#### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Profily konfigurace síťových zařízení s drátovou sítí pro zařízení macOS<!-- 3508686  -->
   > [!NOTE]
   > Tato funkce byla zpožděna, ale brzy bude vydána.

#### <a name="block-users-from-configuring-certificate-credentials-in-the-managed-keystore-on-android-enterprise-device-owner-devices---3311998---"></a>Zablokovat uživatelům nastavení přihlašovacích údajů certifikátu ve spravovaném úložišti klíčů na zařízeních s Androidem Enterprise Device Owner<!-- 3311998 -->
Na zařízeních pro vlastníka zařízení s Androidem Enterprise můžete nakonfigurovat nové nastavení, které uživatelům zablokuje konfiguraci svých přihlašovacích údajů k certifikátu ve spravovaném úložišti klíčů (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** for Platform > **Owner pouze > omezení zařízení** pro typ profilu > **Uživatelé a účty**).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Správa zařízení

#### <a name="protected-wipe-action-now-available--51150000---"></a>Nyní je k dispozici chráněná akce vymazání.<!--51150000 -->
Teď máte možnost použít akci vymazat zařízení k provedení chráněného vymazání zařízení. Chráněná vymazání jsou stejná jako standardní vymazání, s tím rozdílem, že je nelze obejít vypnutím zařízení. Chráněné vymazání bude pokračovat v pokusu o resetování zařízení, dokud nebylo úspěšné. V některých konfiguracích může tato akce opustit zařízení, protože se nemůže restartovat. Další informace najdete v tématu [vyřazení nebo vymazání zařízení](../remote-actions/devices-wipe.md).

#### <a name="device-ethernet-mac-address-added-to-devices-overview-page--5562275---"></a>Adresa MAC zařízení pro síť Ethernet přidaná na stránku Přehled zařízení<!--5562275 -->
Na stránce s podrobnostmi o zařízení se teď může zobrazit ethernetová adresa MAC zařízení (**zařízení** > **všechna zařízení** > zvolit **Přehled**> zařízení.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Zabezpečení zařízení

#### <a name="improved-experience-on-a-shared-device-when-device-based-conditional-access-policies-are-enabled---1734096----"></a>Vylepšené prostředí na sdíleném zařízení, když jsou povolené zásady podmíněného přístupu na základě zařízení<!-- 1734096  -->
Vylepšili jsme prostředí na sdíleném zařízení s více uživateli, kteří jsou cílem zásad podmíněného přístupu na základě zařízení, a to kontrolou nejnovějšího vyhodnocení dodržování předpisů pro uživatele při vynucování zásad. Další informace najdete v následujících článcích přehledu:
- [Přehled Azure pro podmíněný přístup](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Přehled dodržování předpisů zařízením v Intune](../protect/device-compliance-get-started.md)

#### <a name="use-pkcs-certificate-profiles-to-provision-devices-with-certificates---2317124-2317130-2317139-2340517-2340528-2340529----"></a>Použití profilů certifikátů PKCS ke zřízení zařízení s certifikáty<!-- 2317124, 2317130, 2317139, 2340517, 2340528, 2340529  -->
Profily certifikátů PKCS teď můžete používat k vystavování certifikátů na *zařízeních* s Androidem for Work, iOS a Windows, pokud jsou přidružená k profilům, jako jsou profily Wi-Fi a VPN. Dřív tyto tři platformy podporovaly jenom uživatelské certifikáty, přičemž podpora založená na zařízeních je omezená na macOS.

> [!NOTE]
> Profily certifikátů PKCS nejsou podporovány profily sítě Wi-Fi. Místo toho použijte profily certifikátů SCEP, když používáte [typ protokolu EAP](../configuration/wi-fi-settings-windows.md#enterprise-profile).

Pokud chcete použít certifikát založený na zařízení, při [vytváření profilu certifikátu PKCS](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile) pro podporované platformy vyberte **Nastavení**. Teď uvidíte nastavení **typ certifikátu**, který podporuje možnosti pro zařízení nebo uživatele.



<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="centralized-audit-logs--5603185-5697164---"></a>Centralizované protokoly auditu<!--5603185, 5697164 -->
Nové centralizované možnosti protokolu auditu teď shromažďují protokoly auditu pro všechny kategorie na jednu stránku. Protokoly můžete filtrovat a získat tak data, která hledáte. Protokoly auditu zobrazíte tak, že přejdete do části **Správa tenanta** > **protokoly auditu**. 

#### <a name="scope-tag-information-included-in-audit-log-activity-details--5763534---"></a>Podrobnosti o značce oboru obsažené v podrobnostech o aktivitě protokolu auditu<!--5763534 -->
Podrobnosti o aktivitě protokolu auditu teď zahrnují informace o značce oboru (pro objekty Intune, které podporují značky oboru). Další informace o protokolech auditu najdete v tématu [použití protokolů auditu ke sledování a monitorování událostí](monitor-audit-logs.md).


<!-- ########################## -->
## <a name="week-of-december-2-2019"></a>Týden od 2. prosince 2019

#### <a name="new-microsoft-endpoint-configuration-manager-co-management-licensing--5027281--"></a>Nové licencování pro spolupráci s Microsoft Endpoint Configuration Manager<!--5027281-->
K dispozici je nová licence, která umožňuje Configuration Manager zákazníkům se Software Assurance získat spolusprávu Intune pro počítače s Windows 10 bez nutnosti koupit další licenci Intune pro spolusprávu. Zákazníci už nepotřebují, abyste koncovým uživatelům přidělili jednotlivé licence Intune/EMS pro spolusprávu Windows 10.
- Zařízení spravovaná pomocí Configuration Manager a zaregistrovaná do spolusprávy mají skoro stejná práva jako samostatné počítače spravované MDM v Intune. Po obnovení se ale nedá znovu zřídit pomocí automatického pilotního nasazení.
- Zařízení s Windows 10 zaregistrovaná v Intune jiným způsobem vyžadují úplné licence Intune.
- Zařízení na jiných platformách stále vyžadují úplné licence Intune.

Další informace najdete v tématu [licenční podmínky](https://www.microsoft.com/en-us/Licensing/product-licensing/products).


<!-- ########################## -->
## <a name="week-of-november-18-2019-1911-service-release"></a>Týden od 18. listopadu 2019 (1911 Service Release)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Správa aplikací

#### <a name="ui-update-when-selectively-wiping-app-data---4102028---"></a>Aktualizace uživatelského rozhraní při selektivním vymazání dat aplikace<!-- 4102028 -->
Uživatelské rozhraní pro selektivní vymazání dat aplikací v Intune se aktualizovalo. Změny uživatelského rozhraní zahrnují:
- Zjednodušené prostředí pomocí formátu na úrovni Průvodce zúženého v jednom podokně.
- Aktualizace toku vytváření, který má být zahrnut do přiřazení
- Souhrnná stránka všech věcí nastavená při zobrazení vlastností, před vytvořením nové zásady nebo úpravou vlastnosti. Také při úpravách vlastností se v souhrnu zobrazí pouze seznam položek z kategorie upravovaných vlastností.

Další informace najdete v tématu [Jak z aplikací spravovaných pomocí Intune vymazat jenom firemní data](~/apps/apps-selective-wipe.md).

#### <a name="ios-and-ipados-third-party-keyboard-support---4922950---"></a>Podpora klávesnice třetích stran pro iOS a iPadOS<!-- 4922950 -->
V březnu 2019 jsme oznámili odebrání podpory nastavení zásad ochrany aplikací pro iOS na klávesnicích třetích stran. Funkce se vrátí do Intune s podporou iOS i iPadOS. Pokud chcete toto nastavení povolit, přejděte na kartu **Ochrana dat** v nové nebo existující zásadě ochrany aplikací pro iOS/iPadOS a vyhledejte v části **přenos dat**nastavení **klávesnic třetích stran** .

Chování nastavení této zásady se mírně liší od předchozí implementace. V aplikacích s více identitami, které používají sadu SDK verze 12.0.16 a novější, na které cílí zásady ochrany aplikací s tímto nastavením nakonfigurovaným na **blokování**, koncoví uživatelé nebudou moci na svých organizacích a osobních účtech souhlasit s klávesnicí třetích stran. Aplikace používající sady SDK verze 12.0.12 a dřívější budou dál vykazovat chování dokumentované v nadpisu blogového příspěvku [známý problém: klávesnice třetích stran nejsou v iOS pro osobní účty blokované](https://aka.ms/3rdparty_iOS_Intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="target-macos-user-groups-to-require-jamf-management---4061739----"></a>Cílové skupiny uživatelů macOS, které vyžadují správu Jamf<!-- 4061739  --> 
Můžete cílit na konkrétní skupiny uživatelů, kteří budou mít [zařízení MacOS spravovaná pomocí Jamf](../protect/conditional-access-integrate-jamf.md). Díky tomu můžete použít integraci Jamf dodržování předpisů pro podmnožinu zařízení macOS, zatímco jiná zařízení se spravují přes Intune. Pokud již používáte integraci Jamf, všichni uživatelé budou ve výchozím nastavení zaměřeni na integraci.

#### <a name="new-exchange-activesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices---4892824-----"></a>Nová nastavení Exchange ActiveSync při vytváření profilu konfigurace e-mailového zařízení na zařízeních s iOS<!-- 4892824   --> 
V zařízeních s iOS/iPadOS můžete nakonfigurovat připojení e-mailu v profilu konfigurace zařízení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS/iPadOS** **pro > pro** daný typ profilu). 

K dispozici jsou nová nastavení Exchange ActiveSync, včetně:
- **Data pro synchronizaci se systémem Exchange**: vyberte služby Exchange, které chcete synchronizovat (nebo blokovat synchronizaci) pro kalendář, kontakty, připomenutí, poznámky a e-mail.
- **Umožňuje uživatelům změnit nastavení synchronizace**: povoluje (nebo zablokuje) uživatelům změnu nastavení synchronizace pro tyto služby na svých zařízeních.  

Další informace o těchto nastaveních najdete [v nastavení e-mailového profilu pro zařízení s iOS v Intune](../configuration/email-settings-ios.md). 

Platí pro:

- iOS 13,0 a novější
- iPadOS 13,0 a novější

#### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-fully-managed-and-dedicated-devices---5353228-----"></a>Zabránit uživatelům v přidávání osobních účtů Google na plně spravovaná a vyhrazená zařízení s Androidem Enterprise<!-- 5353228   -->
U plně spravovaných a vyhrazených zařízení s Androidem Enterprise je k dispozici nové nastavení, které uživatelům brání v vytváření osobních účtů Google (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** pro **vlastníka zařízení > jenom > omezení zařízení** pro typ profilu > **Uživatelé a účty nastavení** > **osobní účty Google**).

Pokud chcete zobrazit nastavení, která můžete nakonfigurovat, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-android-for-work.md).

Platí pro:

- Zařízení se systémem Android Enterprise s plnou správou
- Zařízení se systémem Android Enterprise vyhrazená

#### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-iosipados-device-restrictions-profile----5468501-----"></a>Nastavení příkazů protokolování na straně serveru pro příkazy Siri se odebralo v profilu omezení zařízení s iOS/iPadOS. <!-- 5468501   -->
V zařízeních se systémy iOS a iPadOS se nastavení **protokolování na straně serveru pro příkazy Siri** odebere z konzoly pro správu Microsoft Endpoint Manageru **(konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS/IPadOS** pro > **omezení zařízení** pro typ profilu > **integrované aplikace**). 

Toto nastavení nemá na zařízeních žádný vliv. Chcete-li odebrat nastavení z existujících profilů, otevřete profil, proveďte změnu a potom profil uložte. Profil se aktualizuje a nastavení se odstraní ze zařízení.

Pokud chcete zobrazit všechna nastavení, která můžete konfigurovat, přečtěte si téma [nastavení zařízení s iOS a iPadOS, abyste mohli povolit nebo zakázat funkce využívající Intune](../configuration/device-restrictions-ios.md).

Platí pro:

- iOS/iPadOS

#### <a name="windows-10-feature-updates-public-preview---2384877---"></a>Aktualizace funkcí Windows 10 (verze Public Preview)<!-- 2384877 -->
Teď můžete nasadit [aktualizace funkcí Windows 10](../protect/windows-update-for-business-configure.md#windows-10-feature-updates) na zařízení s Windows 10. Aktualizace funkcí Windows 10 jsou novou zásadou aktualizace softwaru, která nastavuje verzi Windows 10, kterou chcete, aby se zařízení nainstalovala a zůstala v systému. Tento nový typ zásady můžete použít spolu s existujícími aktualizačními kanály Windows 10.

Zařízení, která přijímají zásady aktualizací funkcí Windows 10, budou instalovat určenou verzi Windows a pak zůstanou v této verzi, dokud se zásada neupraví nebo neodebere. Zařízení, na kterých běží novější verze Windows, zůstávají v aktuální verzi. Zařízení, která jsou držená v určité verzi Windows, můžou pořád instalovat aktualizace kvality a zabezpečení pro tuto verzi z aktualizačních kanálů Windows 10.

Tento nový typ zásad začíná v tomto týdnu pro klienty. Pokud tato zásada ještě není pro vašeho tenanta k dispozici, bude brzy.

#### <a name="add-and-change-key-information-in-plist-files-for-macos-applications---4736278---"></a>Přidání a změna klíčových informací v souborech plist pro aplikace macOS<!-- 4736278 -->
Na zařízeních macOS teď můžete vytvořit konfigurační profil zařízení, který nahraje soubor seznamu vlastností (. plist) přidružený k aplikaci nebo zařízení (**zařízení** > **Konfigurace profily** > **vytvořit profil** > pro **soubor předvoleb** **> pro typ** profilu).

Pouze některé aplikace podporují spravované předvolby a tyto aplikace vám nemusí umožňovat spravovat všechna nastavení. Nezapomeňte nahrát soubor seznamu vlastností, který nakonfiguruje nastavení kanálu zařízení, ne nastavení kanálu uživatele.

Další informace o této funkci najdete v tématu [Přidání souboru se seznamem vlastností do zařízení MacOS pomocí Microsoft Intune](../configuration/preference-file-settings-macos.md).

Platí pro:

- zařízení macOS se systémem 10,7 a novějším

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Správa zařízení

#### <a name="edit-device-name-value-for-autopilot-devices---2640074---"></a>Upravit hodnotu názvu zařízení pro zařízení s autopilotem<!-- 2640074 -->
Můžete upravit hodnotu název zařízení pro zařízení autopilotu připojená k Azure AD.  Další informace najdete v tématu [Úprava atributů zařízení autopilotu](../enrollment/enrollment-autopilot.md#edit-autopilot-device-attributes).

#### <a name="edit-group-tag-value-for-autopilot-devices---4816775-----"></a>Upravit hodnotu značky skupiny pro zařízení autopilotu<!-- 4816775   -->
Můžete upravit hodnotu značky skupiny pro zařízení autopilotu. Další informace najdete v tématu [Úprava atributů zařízení autopilotu](../enrollment/enrollment-autopilot.md#edit-autopilot-device-attributes).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="updated-support-experience---5012398---"></a>Aktualizované prostředí podpory<!-- 5012398 -->

Od dnešního dne se aktualizované a zjednodušené prostředí v konzole pro [Získání pomoci a podpory pro Intune](get-support.md) zavádět do klientů. Pokud toto nové prostředí zatím není k dispozici, bude brzy.

Vylepšili jsme vyhledávání v konzole a zpětnou vazbu pro běžné problémy a pracovní postup, pomocí kterého se obrátíte na podporu. Při otevírání problému podpory uvidíte odhady v reálném čase, kdy můžete očekávat zpětné volání nebo e-mailovou odpověď, a zákazníci s plánem Premier a Unified support můžou pro svůj problém snadno zadat závažnost, abyste mohli rychleji získat podporu.

#### <a name="improved-intune-reporting-experience-public-preview----3791418---"></a>Vylepšené prostředí Intune pro vytváření sestav (Public Preview) <!-- 3791418 -->
Intune teď nabízí vylepšené možnosti vytváření sestav, včetně nových typů sestav, lepších organizací sestav, pokročilejších zobrazení, vylepšených funkcí sestav a také konzistentních a včasných dat. Nové typy sestav se zaměřují na následující:
- **Provozní** – poskytuje nové záznamy s negativním důrazem na stav. 
- **Organizace** – poskytuje širší souhrn celkového stavu.
- **Historická** – poskytuje vzory a trendy v časovém intervalu.
- **Specialista** – umožňuje používat nezpracovaná data k vytváření vlastních sestav.

První sada nových sestav se zaměřuje na dodržování předpisů zařízením. Další informace najdete v tématu [Microsoft Intune pro vytváření sestav](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Reporting-Framework-Coming-to-Intune/ba-p/1009553) a [sestavy Intune](~/fundamentals/reports.md)v rámci blogů.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="duplicate-custom-or-built-in-roles----1081938-----"></a>Duplicitní vlastní nebo předdefinované role <!-- 1081938   -->
Nyní můžete kopírovat předdefinované a vlastní role. Další informace najdete v tématu [kopírování role](../fundamentals/create-custom-role.md#copy-a-role).

#### <a name="new-permissions-for-school-administrator-role----5621805----"></a>Nová oprávnění pro roli školního správce <!-- 5621805  -->  
Do role správce školy byly přidány dvě nová oprávnění, **přiřadí se profil** a **synchronizovat zařízení**> **oprávnění** > **registračních programů**. Oprávnění profil synchronizace umožňuje správcům skupin synchronizovat zařízení s Windows autopilotem. Oprávnění přiřadit profil umožňuje odstranit uživatelem inicializované profily registrace Apple. Poskytuje jim taky oprávnění ke správě přiřazení zařízení s autopilotem a přiřazení profilu nasazení autopilotu. Seznam všech oprávnění správce školy nebo skupiny správců najdete v tématu [přiřazení správců skupin](https://docs.microsoft.com/intune-education/group-admin-delegate). 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="security"></a>Zabezpečení

#### <a name="bitlocker-key-rotation---2564951----"></a>Střídání klíčů BitLockeru<!-- 2564951  -->
K vzdálenému [otočení klíčů pro obnovení BitLockeru](../protect/encrypt-devices.md#rotate-bitlocker-recovery-keys) pro spravovaná zařízení s Windows verze 1909 nebo novější můžete použít akci zařízení v Intune. Aby bylo možné získat oprávnění k otočení klíčů pro obnovení, musí být zařízení nakonfigurovaná tak, aby podporovala otočení obnovovacího klíče.  

#### <a name="updates-to-dedicated-device-enrollment-to-support-scep-device-certificate-deployment----5198878----"></a>Aktualizace vyhrazené registrace zařízení pro podporu nasazení certifikátu zařízení SCEP <!-- 5198878  -->
Intune teď podporuje nasazení certifikátu zařízení SCEP na vyhrazená zařízení s Androidem Enterprise pro přístup založený na certifikátech k profilům Wi-Fi. Aby mohlo nasazení fungovat, musí být aplikace Microsoft Intune na zařízení přítomná. V důsledku toho jsme aktualizovali možnosti registrace pro vyhrazená zařízení s Androidem Enterprise. Nové registrace stále začínají stejnou (s identifikátorem QR, NFC, nulovým dotykem nebo identifikátorem zařízení), ale teď mají krok, který vyžaduje, aby uživatelé nainstalovali aplikaci Intune. Stávající zařízení začnou aplikaci automaticky instalovat na určitou bázi.

#### <a name="intune-audit-logs-for-business-to-business-collaboration--5670211---"></a>Protokoly auditu Intune pro spolupráci mezi společnostmi<!--5670211 -->
Spolupráce B2B (Business-to-Business) umožňuje bezpečně sdílet aplikace a služby společnosti s uživateli typu host z jakékoli jiné organizace a přitom zachovat kontrolu nad vašimi podnikovými daty. Intune teď podporuje protokoly auditu pro uživatele typu Host B2B. Například když uživatelé typu Host provedou změny, Intune bude moct zachytit tato data prostřednictvím protokolů auditu. Další informace najdete v tématu [co je přístup uživatelů typu Host v Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) .


<!-- ########################## -->
## <a name="week-of-november-11-2019"></a>Týden od 11. listopadu 2019  

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Správa aplikací  

#### <a name="improved-macos-enrollment-experience-in-company-portal----5074349----"></a>Vylepšené možnosti registrace macOS v Portál společnosti <!-- 5074349  -->  
Portál společnosti pro zápis do macOS má jednodušší proces registrace, který se podrobněji zarovnává s Portál společnostim pro možnosti registrace v iOS. Uživatelé zařízení teď uvidí:  

* Elegantní uživatelské rozhraní.  
* Vylepšený kontrolní seznam pro registraci.  
* Informace o tom, jak zaregistrovat svá zařízení.  
* Vylepšené možnosti řešení potíží.  

#### <a name="web-apps-launched-from-the-windows-company-portal-app---5030972---"></a>Webové aplikace spouštěné z aplikace Portál společnosti pro Windows<!-- 5030972 -->
Koncoví uživatelé teď můžou spouštět webové aplikace přímo z aplikace Portál společnosti pro Windows. Koncoví uživatelé můžou webovou aplikaci vybrat a pak vybrat možnost **otevřít v prohlížeči**. Publikovaná webová adresa URL se otevře přímo ve webovém prohlížeči. Tato funkce bude zahrnuta v průběhu příštího týdne. Další informace o webových aplikacích najdete v tématu [Přidání webových aplikací do Microsoft Intune](~/apps/web-app.md).  


#### <a name="new-assignment-type-column-in-company-portal-for-windows-10----5459950----"></a>Sloupec nový typ přiřazení v Portál společnosti pro Windows 10 <!-- 5459950  -->
Sloupec **typu přiřazení** portál společnosti > **nainstalované aplikace** > byl přejmenován na **požadováno vaší organizací**.  V tomto sloupci se uživatelům zobrazí hodnota **Ano** nebo **ne** , která označuje, že je aplikace buď požadovaná, nebo povinná jejich organizací. Tyto změny byly provedeny, protože uživatelé zařízení byli zaměňováni o konceptu dostupných aplikací. Uživatelé můžou najít další informace o instalaci aplikací z Portál společnosti v [instalaci a sdílení aplikací na vašem zařízení](/intune-user-help/install-apps-cpapp-windows). Další informace o konfiguraci aplikace Portál společnosti pro uživatele naleznete v tématu [How to Configure a Microsoft Intune portál společnosti App](~/apps/company-portal-app.md).  

<!-- ########################## -->
## <a name="week-of-november-4-2019"></a>Týden od 4. listopadu 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Zabezpečení zařízení

#### <a name="security-baselines-are-supported-on-microsoft-azure-government---4062552---"></a>Základní hodnoty zabezpečení jsou podporovány v Microsoft Azure Government<!-- 4062552 -->

Instance Intune, které jsou hostované na *Microsoft Azure Government* , teď můžou používat [směrné plány zabezpečení](../protect/security-baselines.md) , které vám pomůžou zabezpečit a chránit vaše uživatele a zařízení.

<!-- ########################## -->
## <a name="week-of-october-28-2019"></a>Týden od 28. října 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Správa aplikací

#### <a name="improved-checklist-design-in-company-portal-app-for-android---5550857---"></a>Vylepšený návrh kontrolního seznamu v aplikaci Portál společnosti App pro Android<!-- 5550857 -->  
Kontrolní seznam nastavení v aplikaci Portál společnosti pro Android byl aktualizovaný s odlehčeným návrhem a novými ikonami. Změny se zarovnají s posledními aktualizacemi provedenými v aplikaci Portál společnosti pro iOS. Pro souběžné porovnání změn si přečtěte téma [co je nového v uživatelském rozhraní aplikace](whats-new-app-ui.md). Pokud se chcete podívat na aktualizované kroky registrace, přečtěte si téma [registrace v pracovním profilu Android](/intune-user-help/enroll-device-android-work-profile) a [registrace zařízení s Androidem](/intune-user-help/enroll-device-android-company-portal).  

#### <a name="win32-apps-on-windows-10-s-mode-devices---3747604---"></a>Aplikace Win32 na zařízeních S Windows 10 S v režimu<!-- 3747604 --> 
Aplikace Win32 můžete instalovat a spouštět na zařízeních spravovaných v režimu Windows 10 S. K tomu můžete vytvořit jednu nebo více doplňkových zásad pro režim S pomocí nástrojů PowerShellu pro řízení aplikací v programu Windows Defender (WDAC). Přihlaste doplňkové zásady pomocí registračního portálu pro ochranu zařízení a pak tyto zásady nahrajte a distribuujte prostřednictvím Intune. V Intune tuto možnost najdete tak, že vyberete **klientské aplikace** > **doplňkové zásady Windows 10 S**. Další informace najdete v tématu [Povolení aplikací Win32 na zařízeních s režimem S](~/apps/apps-win32-s-mode.md).

#### <a name="set-win32-app-availability-based-on-a-date-and-time---3510685---"></a>Nastavení dostupnosti aplikace Win32 na základě data a času<!-- 3510685 -->
Jako správce můžete nakonfigurovat čas zahájení a konečný termín pro požadovanou aplikaci Win32. V počátečním čase rozšíření pro správu Intune spustí stažení obsahu aplikace a uloží je do mezipaměti. Aplikace se nainstaluje v čase konečného termínu. V případě dostupných aplikací se čas spuštění určí, když se aplikace zobrazí v Portál společnosti. Další informace najdete v tématu [Správa aplikací Win32 v Intune](~/apps/apps-win32-app-management.md#set-win32-app-availability-and-notifications).

#### <a name="require-device-restart-based-on-grace-period-after-win32-app-install---3136567---"></a>Vyžadovat restart zařízení na základě období odkladu po instalaci aplikace Win32<!-- 3136567 -->
Můžete vyžadovat, aby se zařízení po úspěšném dokončení instalace aplikace Win32 restartovalo. Další informace najdete v tématu [Správa aplikací Win32 – konfigurace podrobností instalace aplikace](~/apps/apps-win32-app-management.md#step-4-configure-app-installation-details).

#### <a name="dark-mode-for-ios-company-portal---4911422---"></a>Tmavý režim pro iOS Portál společnosti<!-- 4911422 -->
Pro iOS Portál společnosti je k dispozici tmavý režim. Uživatelé můžou stahovat firemní aplikace, spravovat jejich zařízení a získávat v nich podporu v barevném schématu podle nastavení zařízení. Portál společnosti pro iOS bude automaticky odpovídat nastavení zařízení koncového uživatele pro tmavý nebo lehký režim. Další informace najdete v tématu [představení tmavého režimu Microsoft Intune portál společnosti pro iOS](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Introducing-dark-mode-on-Microsoft-Intune-Company-Portal-for-iOS/ba-p/918453). Další informace o Portál společnosti pro iOS najdete v tématu [Jak konfigurovat aplikaci Microsoft Intune portál společnosti](~/apps/company-portal-app.md).

#### <a name="android-company-portal-enforced-minimum-app-version---2378776---"></a>Minimální verze aplikace pro Android Portál společnosti vynutila<!-- 2378776 -->
Pomocí nastavení **Minimální verze portál společnosti** zásady ochrany aplikací můžete zadat konkrétní minimální verzi portál společnosti, která se vynutila na zařízení koncového uživatele. Toto nastavení podmíněného spuštění umožňuje **blokovat přístup**, **Vymazat data**nebo **upozorňovat** jako na možné akce, pokud není hodnota splněna. Možné formáty pro tuto hodnotu se řídí vzorem *[hlavní]. [ Vedlejší]* , *[hlavní]. [ Vedlejší]. [Build]* nebo *[hlavní]. [ Vedlejší]. [Build]. [Revize]* .

Nastavení **Minimální verze portál společnosti** , pokud je nakonfigurováno, bude mít vliv na každého koncového uživatele, který získá 5.0.4560.0 verze portál společnosti a jakékoli budoucí verze portál společnosti. Toto nastavení nebude mít žádný vliv na uživatele, kteří používají verzi Portál společnosti, která je starší než verze, ve které byla tato funkce vydána. Koncoví uživatelé, kteří používají automatické aktualizace aplikace na jejich zařízení, nejspíš neuvidí žádná dialogová okna této funkce, protože budou pravděpodobně na nejnovější verzi Portál společnosti. Toto nastavení platí jenom pro Android s ochranou aplikací pro zapsaná a neregistrovaná zařízení. Další informace najdete v tématu [nastavení zásad ochrany aplikací pro Android – podmíněné spuštění](~/apps/app-protection-policy-settings-android.md#conditional-launch).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->

### <a name="microsoft-365-device-management"></a>Správa zařízení Microsoft 365

#### <a name="introducing-endpoint-security-node-in-microsoft-365-device-management---5630102---"></a>Představujeme uzel zabezpečení koncového bodu v Microsoft 365 správě zařízení<!-- 5630102 -->

Uzel **zabezpečení koncového bodu** je teď v https://devicemanagement.microsoft.com všeobecně dostupný v Microsoft 365 pracovní prostor pro správu zařízení, který seskupuje možnosti pro zabezpečení koncových bodů, jako jsou:

- Směrné plány zabezpečení: předem nakonfigurovaná skupina nastavení, která vám pomůžou použít známou skupinu nastavení a výchozí hodnoty, které Microsoft doporučuje.

- Úkoly zabezpečení: Využijte výhod správy hrozeb a ohrožení zabezpečení ATPs v programu Microsoft Defender a použijte Intune k nápravě slabých míst koncových bodů.

- Microsoft Defender ATP: Integrovaná Rozšířená ochrana před internetovými útoky v programu Microsoft Defender (ATP), která umožňuje zabránit narušení zabezpečení.

Tato nastavení budou nadále přístupná z jiných použitelných uzlů, jako jsou zařízení, a aktuálně nakonfigurovaný stav bude stejný bez ohledu na to, kde máte přístup k těmto možnostem a tyto funkce povolíte.

Další informace o těchto vylepšeních najdete v [blogovém příspěvku o úspěchu pro zákazníky v Intune](https://aka.ms/Endpoint_security_node) na webu Microsoft Tech Community.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Správa zařízení

#### <a name="intune-supports-ios-11-and-later---4665324----"></a>Intune podporuje iOS 11 a novější.<!-- 4665324  -->

Registrace a Portál společnosti v Intune teď podporují iOS verze 11 a novější. Starší verze se nepodporují.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Zabezpečení zařízení

#### <a name="microsoft-edge-baseline-preview----3787164----"></a>Microsoft Edge – základní údaje (Preview)<!--  3787164  -->

Přidali jsme náhled základní úrovně zabezpečení pro [nastavení Microsoft Edge](../protect/security-baseline-settings-edge.md). 

<!-- ########################## -->
## <a name="week-of-october-21-2019-1910-service-release"></a>Týden od 21. října 2019 (1910 Service Release)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="microsoft-365-device-management"></a>Správa zařízení Microsoft 365

#### <a name="improved-administration-experience-in-microsoft-365-device-management---5551239---"></a>Vylepšené možnosti správy v Microsoft 365 správě zařízení<!-- 5551239 -->

Aktualizované a zjednodušené prostředí pro správu je teď všeobecně dostupné v pracovním prostoru specialista správy zařízení Microsoft 365 v [https://devicemanagement.microsoft.com](https://devicemanagement.microsoft.com), včetně těchto:

- **Aktualizovaná navigace**: najdou se Zjednodušená navigace na první úrovni, která logicky seskupuje funkce.
- **Nové filtry platformy**: můžete vybrat jednu platformu, která na stránkách zařízení a aplikace zobrazuje jenom zásady a aplikace pro vybranou platformu.
- **Nová Domovská stránka**: rychlé zobrazení stavu služby, stavu vašeho tenanta, zpráv atd. na nové domovské stránce.

Další informace o těchto vylepšeních najdete v [blogovém příspěvku Enterprise mobility + Security](https://go.microsoft.com/fwlink/?linkid=2109094) na webu Microsoft Tech Community.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Správa aplikací

#### <a name="add-mobile-threat-defense-apps-to-unenrolled-devices---3005337---"></a>Přidání aplikací ochrany před mobilními hrozbami do neregistrovaných zařízení<!-- 3005337 -->
Můžete vytvořit zásady ochrany aplikací Intune, které můžou blokovat nebo selektivně vymazat podniková data uživatelů na základě stavu zařízení. Stav zařízení se určí pomocí vašeho zvoleného řešení ochrany před mobilními hrozbami (MTD). Tato funkce existuje v současnosti se zaregistrovanými zařízeními Intune jako nastavením dodržování předpisů pro zařízení. Díky této nové funkci rozšiřujeme detekci hrozeb od dodavatele ochrany před mobilními hrozbami, aby fungovalo na nezaregistrovaných zařízeních. V Androidu Tato funkce vyžaduje nejnovější Portál společnosti na zařízení. V systému iOS bude tato funkce dostupná pro použití v případě, že aplikace integrují nejnovější sadu Intune SDK (v 12.0.15 +). V případě, že první aplikace přijme nejnovější sadu Intune SDK, aktualizujeme téma Co je nového. Zbývající aplikace budou k dispozici na určitou bázi. Další informace najdete v tématu [Vytvoření zásady ochrany aplikací ochrany před mobilními hrozbami v Intune](~/protect/mtd-app-protection-policy.md).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="new-device-firmware-configuration-interface-profile-for-windows-10-and-later-devices-public-preview---2266073----"></a>Nový profil rozhraní pro konfiguraci firmwaru zařízení pro zařízení s Windows 10 a novější verzí (Public Preview)<!-- 2266073  -->

V systému Windows 10 a novějších můžete vytvořit profil konfigurace zařízení pro řízení nastavení a funkcí (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** pro platformu). V této aktualizaci je k dispozici nový typ profilu rozhraní konfigurace firmwaru zařízení, který umožňuje Intune spravovat nastavení rozhraní UEFI (BIOS).

Další informace o této funkci najdete v tématu [použití profilů DFCI na zařízeních s Windows v Microsoft Intune](../configuration/device-firmware-configuration-interface-windows.md).

Platí pro:

- Windows 10 RS5 (1809) a novější v podporovaném firmwaru

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="toggle-to-only-show-enrollment-status-page-on-devices-provisioned-by-out-of-box-experience-oobe--3959566--"></a>Přepnout na zobrazení stránky stav registrace na zařízeních, která se zřídila při spuštění předpřipraveného prostředí (OOBE)<!--3959566-->
Nyní se můžete rozhodnout, že se stránka stavu registrace zobrazí jenom na zařízeních zřízených pomocí příkazu autopilot OOBE.

Pokud se chcete podívat na nový přepínač, vyberte > **Intune** **registrace zařízení** > **registrace Windows** > **stavová stránka** > **vytvořit profil** > **Nastavení** > **zobrazit jenom stránku na zařízeních, která se zřídila při prvním zapnutí prostředí (OOBE)** .


<!-- ########################## -->
## <a name="week-of-october-14-2019"></a>Týden od 14. října 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Správa aplikací 

#### <a name="available-google-play-app-reporting-for-android-work-profiles---3041956-----"></a>Dostupná Google Play vytváření sestav aplikací pro pracovní profily Androidu<!-- 3041956   -->
Pro instalaci dostupné aplikace na firemním profilu Androidu Enterprise, vyhrazená a plně spravovaná zařízení můžete zobrazit stav instalace aplikace a také nainstalovanou verzi spravovaných aplikací Google Play. Další informace najdete v tématu [monitorování zásad ochrany aplikací](~/apps/app-protection-policies-monitor.md), [Správa zařízení s pracovním profilem Androidu pomocí Intune](~/enrollment/android-enterprise-overview.md) a [spravovaného Google Play typu aplikace](~/apps/apps-add-android-for-work.md#managed-google-play-app-types).

#### <a name="microsoft-edge-version-77-and-later-for-windows-10-and-macos-public-preview---3872025-4678761----"></a>Microsoft Edge verze 77 a novější pro Windows 10 a macOS (Public Preview)<!-- 3872025, 4678761  -->
Microsoft Edge verze 77 a novější bude k dispozici pro nasazení na počítačích se systémy Windows 10 a macOS. 

Verze Public Preview nabízí **vývoj** a **beta** kanály pro Windows 10 a **beta** kanál pro MacOS. Nasazení je pouze anglické (EN), ale koncoví uživatelé mohou změnit jazyk zobrazení v prohlížeči v části **nastavení** > **jazyky**. Microsoft Edge je aplikace Win32 nainstalovaná v kontextu systému a jako architektury (aplikace x86 v operačním systému x86 a x64 v operačním systému x64). Automatické aktualizace prohlížeče jsou navíc ve výchozím nastavení **zapnuté** a Microsoft Edge nejde odinstalovat. Další informace najdete v tématu [Přidání Microsoft Edge pro Windows 10 do Microsoft Intune](~/apps/apps-windows-edge.md) a [dokumentace k Microsoft Edge](https://go.microsoft.com/fwlink/?linkid=2103823).

#### <a name="update-to-app-protection-ui-and-ios-app-provisioning-ui---4102027-4102029-----"></a>Aktualizace uživatelského rozhraní ochrany aplikací a uživatelského rozhraní pro zřizování aplikací pro iOS<!-- 4102027, 4102029   -->
Aktualizovali jsme uživatelské rozhraní pro vytváření a úpravu zásad ochrany aplikací a zřizovacích profilů aplikací pro iOS v Intune. Změny uživatelského rozhraní zahrnují:
- Zjednodušené prostředí pomocí formátu na úrovni Průvodce zúženého v jednom okně. 
- Aktualizace toku vytváření, který má být zahrnut do přiřazení
- Souhrnná stránka všech věcí nastavená při zobrazení vlastností, před vytvořením nové zásady nebo úpravou vlastnosti. Také při úpravách vlastností se v souhrnu zobrazí pouze seznam položek z kategorie upravovaných vlastností.

Další informace najdete v tématech [Vytvoření a přiřazení zásad ochrany aplikací](~/apps/app-protection-policies.md) a [používání zřizovacích profilů aplikací pro iOS](~/apps/app-provisioning-profile-ios.md).

#### <a name="intune-guided-scenarios---4850318-4831296-3610611----"></a>Scénáře s asistencí pro Intune<!-- 4850318, 4831296, 3610611  -->
Intune teď poskytuje scénáře s asistencí, které vám pomůžou dokončit konkrétní úkol nebo sadu úkolů v rámci Intune. Scénář s asistencí je přizpůsobený sled kroků (pracovní postup), který se nachází na středovém prostředí pro případ celého použití. Běžné scénáře jsou definovány na základě role, kterou správce, uživatel nebo zařízení přehrává ve vaší organizaci. Tyto pracovní postupy obvykle vyžadují kolekci pečlivě Orchestrované profily, nastavení, aplikace a řízení zabezpečení, které poskytují nejlepší uživatelské prostředí a zabezpečení. Mezi nové scénáře s asistencí patří:
- [Nasazení Microsoft Edge pro mobilní zařízení](~/fundamentals/guided-scenarios-edge.md)
- [Zabezpečené systém Microsoft Office mobilní aplikace](~/fundamentals/guided-scenarios-office-mobile.md) 
- [Moderní plocha spravovaná cloudem](~/fundamentals/guided-scenarios-cloud-managed-pc.md)

Další informace najdete v článku [Přehled scénářů s asistencí pro Intune](guided-scenarios-overview.md).

#### <a name="additional-app-configuration-variable-available---4969237-----"></a>Je dostupná další konfigurační proměnná aplikace.<!-- 4969237   -->
Při vytváření zásad konfigurace aplikací můžete zahrnout proměnnou konfigurace `AAD Device ID` jako součást nastavení konfigurace. V Intune vyberte **klientské aplikace** > **zásady konfigurace aplikací** > **Přidat**. Zadejte podrobnosti zásady konfigurace a vyberte **nastavení konfigurace** . zobrazí se okno **nastavení konfigurace** . Další informace najdete v tématu [zásady konfigurace aplikací pro spravovaná zařízení s Androidem Enterprise – použijte návrháře konfigurace](~/apps/app-configuration-policies-use-android.md#use-the-configuration-designer).


#### <a name="create-groups-of-management-objects-called-policy-sets---3762880----"></a>Vytvoření skupin objektů pro správu nazývaných sady zásad<!-- 3762880  -->
Sady zásad umožňují vytvořit sadu odkazů na již existující entity správy, které je třeba identifikovat, cílit a monitorovat jako jednu koncepční jednotku. Sady zásad nenahrazují existující koncepty ani objekty. V Intune můžete dál přiřazovat jednotlivé objekty a v rámci sady zásad můžete odkazovat na jednotlivé objekty. Proto se v sadě zásad projeví všechny změny těchto jednotlivých objektů.  V Intune vyberete **sady zásad** > **vytvořit** k vytvoření nové sady zásad. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="ui-update-for-creating-and-editing-windows-10-update-rings---4099089-----------"></a>Aktualizace uživatelského rozhraní pro vytváření a úpravy aktualizačních kanálů Windows 10<!-- 4099089         -->
Aktualizovali jsme prostředí uživatelského rozhraní pro [vytváření a úpravy aktualizačních kanálů Windows 10](../protect/windows-update-for-business-configure.md#create-and-assign-update-rings) pro Intune. Změny uživatelského rozhraní zahrnují:  
- Formát na úrovni průvodce je zúžený do jediného okna konzoly, ve kterém se při konfiguraci aktualizačních kanálů zobrazí okno neustálému zvětšování, které jste předtím viděli.   
- Revidovaný pracovní postup obsahuje přiřazení před dokončením počáteční konfigurace prstence.
- Souhrnná stránka, kterou můžete použít ke kontrole všech konfigurací, které jste provedli, před uložením a nasazením nového aktualizačního kanálu. Při úpravách aktualizačního kanálu zobrazuje souhrn pouze seznam položek nastavených v kategorii vlastností, které jste upravili.

#### <a name="ui-update-for-creating-and-editing-ios-software-update-policy---4099090---------"></a>Aktualizace uživatelského rozhraní pro vytváření a úpravy zásad aktualizace softwaru pro iOS<!-- 4099090       --> 
Aktualizovali jsme prostředí uživatelského rozhraní pro [vytváření](../protect/software-updates-ios.md#configure-the-policy) a [úpravu](../protect/software-updates-ios.md#edit-a-policy) zásad aktualizace softwaru iOS pro Intune.  Změny uživatelského rozhraní zahrnují:  
- Formát na úrovni průvodce je zhuštěný do jediného okna konzoly, ve kterém se při konfiguraci zásad aktualizace nezobrazuje okno neustálému zvětšování.   
- Revidovaný pracovní postup zahrnuje přiřazení před dokončením počáteční konfigurace zásady.
- Souhrnná stránka, kterou můžete použít ke kontrole všech konfigurací, které jste provedli, před uložením a nasazením nové zásady. V rámci úpravy zásady se v souhrnu zobrazí jenom seznam položek nastavených v kategorii vlastností, které jste upravili.

#### <a name="engaged-restart-settings-are-removed-from-windows-update-rings----4464404--------"></a>Nastavení připraveného restartování se z web Windows Updatech okruhů odeberou.<!--  4464404      -->
Jak už bylo oznámeno, aktualizační kanály Windows 10 v Intune teď [podporují nastavení pro konečné termíny](../protect/windows-update-settings.md) a už nepodporují *restart*. Nastavení pro probíhající *restart* již není k dispozici při konfiguraci nebo správě aktualizačních kroužků v Intune.  

Tato změna se zarovnává s posledními [změnami údržby Windows](https://docs.microsoft.com//windows/whats-new/whats-new-windows-10-version-1903#servicing) a na zařízeních s Windows 10 1903 nebo novějším, přičemž *termíny* nahrazují konfigurace pro *následné restartování*.

#### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-work-profile-devices---4760025-----"></a>Zabránit instalaci aplikací z neznámých zdrojů na zařízeních s pracovními profily Android Enterprise<!-- 4760025   -->
Na zařízeních s pracovním profilem Android Enterprise uživatelé nemůžou instalovat aplikace aplikací z neznámých zdrojů. V této aktualizaci se nachází nové nastavení – **Zakázat instalaci aplikací z neznámých zdrojů v osobním profilu**. Ve výchozím nastavení toto nastavení brání uživatelům v nasazování aplikací z neznámých zdrojů do osobního profilu na zařízení.

Pokud chcete zobrazit nastavení, které můžete nakonfigurovat, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-android-for-work.md).

Platí pro:

- Pracovní profil Android Enterprise

#### <a name="create-a-global-http-proxy-on-android-enterprise-device-owner-devices---4816339-----"></a>Vytvoření globálního proxy serveru HTTP na zařízeních s vlastníkem zařízení s Androidem Enterprise<!-- 4816339   -->
Na zařízeních s Androidem Enterprise můžete nakonfigurovat globální proxy server HTTP tak, aby odpovídal standardům procházení webu vaší organizace (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** for Platform > **>** pro typ profilu > **konektivita**zařízení. Po nakonfigurování budou všechny přenosy HTTP používat tento proxy server.

Pokud chcete tuto funkci nakonfigurovat a zobrazit všechna nakonfigurovaná nastavení, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-android-for-work.md).

Platí pro:

- Vlastník zařízení se systémem Android Enterprise

#### <a name="connect-automatically-setting-is-removed-in-wi-fi-profiles-on-android-device-administrator-and-android-enterprise---5021055-----"></a>Nastavení připojit automaticky se odebere v profilech sítě Wi-Fi na správce zařízení s Androidem a na Androidu Enterprise.<!-- 5021055   -->
Na zařízeních s Androidem pro správce zařízení a Androidem je možné vytvořit profil Wi-Fi pro konfiguraci různých nastavení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Správce zařízení s androidem** nebo **Android Enterprise** pro platformu > **Wi-Fi** pro typ profilu). V této aktualizaci se nastavení **Připojit automaticky** odebere, protože ho [nepodporuje Android](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29). 

Pokud použijete toto nastavení v profilu Wi-Fi, možná jste si všimli, že se **připojení automaticky** nepracuje. Nemusíte nic dělat, ale mějte na paměti, že toto nastavení se odebere v uživatelském rozhraní Intune.

Pokud chcete zobrazit aktuální nastavení, přejděte na nastavení [Androidu Wi-Fi](../configuration/wi-fi-settings-android.md) nebo [Nastavení Android Enterprise Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md).

Platí pro:

- Správce zařízení s Androidem 
- Android Enterprise


#### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices---5199328-----"></a>Nové nastavení konfigurace zařízení pro zařízení s iOS a iPadOS pod dohledem<!-- 5199328   -->
Na zařízeních se systémy iOS a iPadOS můžete vytvořit profil, který omezí funkce a nastavení na zařízeních (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS/iPadOS** pro **omezení** platformy > pro typ profilu). V této aktualizaci můžete řídit nová nastavení: 
- Přístup k síťové jednotce v aplikaci soubory  
- Přístup k jednotce USB v aplikaci soubory 
- Wi-Fi vždycky zapnuté 

Tato nastavení zobrazíte tak, že přejdete na [nastavení zařízení s iOS a povolíte nebo zakážete funkce využívající Intune](../configuration/device-restrictions-ios.md).

Platí pro:

- iOS 13,0 a novější
- iPadOS 13,0 a novější

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="specify-which-android-device-operating-system-versions-enroll-with-work-profile-or-device-administrator-enrollment---4350697-----"></a>Zadejte, které verze operačního systému zařízení s Androidem se mají zaregistrovat pomocí pracovního profilu nebo registrace Správce zařízení.<!-- 4350697   -->
Pomocí omezení typu zařízení v Intune můžete použít verzi operačního systému zařízení k určení toho, která zařízení uživatelů budou používat registraci pracovního profilu Android Enterprise nebo Správce zařízení s Androidem.  Další informace najdete v tématu [Nastavení omezení registrace](../enrollment/enrollment-restrictions-set.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Správa zařízení

#### <a name="new-restrictions-for-renaming-windows-devices---3478938----"></a>Nová omezení pro přejmenování zařízení s Windows<!-- 3478938  -->
Při přejmenování zařízení s Windows musíte dodržovat nová pravidla:
- maximálně 15 znaků (musí být menší než nebo rovno 63 bajtů, včetně koncové hodnoty NULL)
- Není null nebo prázdný řetězec
- Povolené znakové sady ASCII: písmena (a-z, A – Z), číslice (0-9) a spojovníky
- Povolené kódování Unicode: znaky > = 0x80, musí být platný UTF8, musí být možné mapovat na IDN (to znamená, že RtlIdnToNameprepUnicode je úspěšných, viz RFC 3492)
- Názvy nesmí obsahovat jenom číslice.
- Žádné mezery v názvu
- Nepovolené znaky: {|} ~ [\] ^ ':; < = >? & @! " # $ % ` ( ) + / , . _ *)

 Další informace najdete v tématu [přejmenování zařízení v Intune](../remote-actions/device-rename.md).

### <a name="new-android-report-on-devices-overview-page---4924364---"></a>Stránka Přehled nové sestavy pro Android na zařízeních<!-- 4924364 -->
Nová sestava na stránce Přehled zařízení zobrazuje počet zaregistrovaných zařízení s Androidem v jednotlivých řešeních pro správu zařízení. Tento graf zobrazuje počet zaregistrovaných zařízení v pracovním profilu, plně spravovaných, vyhrazených a správcích zařízení. Pokud chcete zobrazit sestavu, vyberte > **zařízení** **Intune** > **Přehled**.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Zabezpečení zařízení

#### <a name="pkcs-certificates-for-macos---1333650---------"></a>Certifikáty PKCS pro macOS<!-- 1333650       -->
[Certifikáty PKCS teď můžete používat s MacOS](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile). Můžete vybrat certifikát PKCS jako typ profilu pro macOS a nasadit certifikáty uživatelů a zařízení, které mají [přizpůsobená pole Předmět a alternativní název subjektu](../protect/certficates-pfx-configure.md#subject-name-format).  

Certifikát PKCS pro macOS podporuje také nové nastavení a _povoluje přístup všem aplikacím_. Pomocí tohoto nastavení můžete všem přidruženým aplikacím povolit přístup k privátnímu klíči certifikátu.  Další informace o tomto nastavení najdete v dokumentaci Apple na adrese https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf.

####   <a name="derived-credentials-to-provision-ios-mobile-devices-with-certificates----1736036-1736037-1772050-2777333-----------"></a>Odvozená pověření pro zřizování mobilních zařízení s iOS pomocí certifikátů<!--  1736036, 1736037, 1772050, 2777333         -->  
Intune podporuje použití [odvozených přihlašovacích údajů](../protect/derived-credentials.md) jako metody ověřování a pro podepisování a šifrování S/MIME pro zařízení S iOS. Odvozené přihlašovací údaje jsou implementací standardu *NIST (National Institute of Standards and Technology) 800-157* pro nasazení certifikátů do zařízení.  

Odvozené přihlašovací údaje spoléhají na použití osobního ověřování identity (PIV) nebo karty Common Access Card (CAC), jako je například čipová karta. Pokud chcete získat odvozené přihlašovací údaje pro své mobilní zařízení, uživatelé začnou v aplikaci Portál společnosti a dodržujte pracovní postup registrace, který je jedinečný pro poskytovatele, kterého používáte.  Společný pro všechny poskytovatele je požadavek na použití čipové karty v počítači k ověření pro odvozeného zprostředkovatele přihlašovacích údajů. Poskytovatel pak vydá certifikát zařízení, které je odvozeno od čipové karty uživatele.  

Intune podporuje následující odvozené zprostředkovatele přihlašovacích údajů:
- DISA purebred
- Entrust Datacard
- Intercede

Odvozené přihlašovací údaje použijete jako metodu ověřování pro profily konfigurace zařízení VPN, Wi-Fi a e-mailu. Můžete je také použít k ověřování aplikací a k podepisování a šifrování S/MIME.  

Další informace o standardu najdete v tématu [odvozené piv přihlašovací údaje](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) na adrese www.nccoe.nist.gov.

#### <a name="use-graph-api-to-specify-a-on-premises-user-principal-name-as-a-variable-for-scep-certificates----5437939----------"></a>Pomocí Graph API zadat hlavní název uživatele místního uživatele jako proměnnou pro certifikáty SCEP.<!--  5437939        -->  
Když použijete [Graph API Intune](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0), můžete jako proměnnou alternativní název subjektu (San) pro certifikáty SCEP zadat onPremisesUserPrincipalName.



<!-- ########################## -->

## <a name="week-of-september-23-2019"></a>Týden od 23. září 2019

#### <a name="ios-user-enrollment-in-preview---4817900---"></a>Registrace uživatele pro iOS ve verzi Preview<!-- 4817900 -->
Verze iOS 13,1 od společnosti Apple zahrnuje registraci uživatelů, novou formu zjednodušené správy pro zařízení s iOS. Dá se použít místo registrace zařízení nebo automatického zápisu zařízení (dříve Program registrace zařízení) pro osobní zařízení vlastněná společností. Intune Preview podporuje tuto sadu funkcí tím, že vám umožní:

- Registrace cílového uživatele pro skupiny uživatelů.
- Poskytněte koncovým uživatelům možnost výběru mezi jednodušším zápisem uživatele nebo silnějším zápisem zařízení při registraci svých zařízení.

Od verze 9/24/2019 s vydáním iOS 13,1 jsme v procesu zavedli tyto aktualizace všem zákazníkům a očekáváme, že budou dokončeny na konci příštího týdne.

Platí pro:

- iOS 13,1 a novější

#### <a name="intune-support-for-ipados-and-ios-131-devices--5439574--"></a>Podpora Intune pro zařízení iPadOS a iOS 13,1<!--5439574-->
Intune teď podporuje správu zařízení iPadOS i iOS 13,1. Další informace najdete v [tomto příspěvku blogu](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-1-and-iPadOS/ba-p/873094).

<!-- ########################## -->

## <a name="week-of-september-16-2019-1909-service-release"></a>Týden od 16. září 2019 (1909 vydání služby)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Správa aplikací 

#### <a name="managed-google-play-private-lob-apps---1464182----"></a>Spravované Google Play soukromé obchodní aplikace<!-- 1464182  -->
Intune teď umožňuje správcům IT publikovat soukromé obchodní aplikace pro Android do spravovaných Google Play prostřednictvím IFRAME vloženého v konzole Intune.  Dříve museli správci IT publikovat obchodní aplikace přímo do konzoly pro publikování Google, která vyžadovala několik kroků a byla časově náročná. Tato nová funkce umožňuje snadno publikovat obchodní aplikace s minimální sadou kroků, aniž byste museli opustit konzolu Intune.  Správci už nebudou muset ručně registrovat jako vývojáře s Google a nebude už muset platit poplatek za registraci Google $25.  Tato funkce může využít některý ze scénářů správy Android Enterprise, které používají spravované Google Play (pracovní profil, vyhrazená, plně spravovaná a neregistrovaná zařízení). V Intune vyberte **klientské aplikace** > **aplikace** > **Přidat**. Pak v seznamu **Typ aplikace** vyberte **spravovaná Google Play** . Další informace o spravovaných aplikacích Google Play najdete v tématu [Přidání spravovaných Google Play aplikací do zařízení s Androidem Enterprise v Intune](../apps/apps-add-android-for-work.md).

#### <a name="windows-company-portal-experience---1473353-3598357---"></a>Prostředí Windows Portál společnosti<!-- 1473353, 3598357 -->
Probíhá aktualizace Windows Portál společnosti. Na stránce aplikace v rámci Windows Portál společnosti budete moct používat víc filtrů. Stránka s podrobnostmi o zařízení se taky aktualizuje s vylepšeným uživatelským prostředím. Právě probíhá zavádění těchto aktualizací pro všechny zákazníky a očekává se dokončení na konci příštího týdne.

#### <a name="macos-support-for-web-apps---3174427---"></a>Podpora macOS pro webové aplikace<!-- 3174427 -->
Webové aplikace, které umožňují přidat zástupce na adresu URL na webu, lze nainstalovat do Docku pomocí Portál společnosti macOS. Koncoví uživatelé mohou získat přístup k akci **instalace** ze stránky s podrobnostmi o aplikaci pro webovou aplikaci ve MacOS portál společnosti. Další informace o typu aplikace **webový odkaz** najdete v tématu [přidání aplikací do Microsoft Intune](../apps/apps-add.md) a [Přidání webových aplikací do Microsoft Intune](../apps/web-app.md).

#### <a name="macos-support-for-vpp-apps---3173501----"></a>Podpora macOS pro aplikace VPP<!-- 3173501  -->
aplikace macOS, zakoupené pomocí Apple Business Manageru, se v konzole zobrazí, když se tokeny programu Apple VPP synchronizují v Intune. Pomocí konzoly služby Intune můžete přiřadit, odvolat a znovu přiřadit licence na zařízení a uživatele pro skupiny. Microsoft Intune pomáhá spravovat aplikace VPP zakoupené pro použití ve vaší společnosti:

- Vykazuje informace o licencích z App Storu.
- Sleduje počet použitých licencí.
- Pomůže vám zabránit instalaci více kopií aplikace, než na kolik máte licence.

Další informace o Intune a VPP najdete v tématu [Správa hromadně zakoupených aplikací a knih pomocí Microsoft Intune](../apps/vpp-apps.md).

#### <a name="managed-google-play-iframe-support---2871756----"></a>Podpora spravované Google Play IFRAME<!-- 2871756  -->
Intune teď poskytuje podporu pro přidávání a správu webových odkazů přímo v konzole Intune prostřednictvím spravovaného Google Play IFRAME.  To umožňuje správcům IT odeslat obrázek adresy URL a ikony a potom tyto odkazy nasadit na zařízení stejně jako běžné aplikace pro Android. Tato funkce může využít některý ze scénářů správy Android Enterprise, které používají spravované Google Play (pracovní profil, vyhrazená, plně spravovaná a neregistrovaná zařízení). V Intune vyberte **klientské aplikace** > **aplikace** > **Přidat**. Pak v seznamu **Typ aplikace** vyberte **spravovaná Google Play** . Další informace o spravovaných aplikacích Google Play najdete v tématu [Přidání spravovaných Google Play aplikací do zařízení s Androidem Enterprise v Intune](../apps/apps-add-android-for-work.md).

#### <a name="silently-install-android-lob-apps-on-zebra-devices---4252734----"></a>Tichá instalace obchodních aplikací pro Android na zařízeních Zebra<!-- 4252734  -->
Při instalaci obchodních aplikací (LOB) pro Android do [zařízení Zebra](../configuration/android-zebra-mx-overview.md)se místo výzvy ke stažení a instalaci obchodní aplikace budete moct aplikaci nainstalovat tiše. V Intune vyberte **klientské aplikace** > **aplikace** > **Přidat**. V podokně **Přidat aplikaci** vyberte **Obchodní aplikace**. Další informace najdete v tématu [Přidání obchodní aplikace pro Android do Microsoft Intune](../apps/lob-apps-android.md).

V současné době se po stažení aplikace LOB na zařízení uživatele zobrazí oznámení o **úspěšném stažení** . Oznámení se může zrušit jenom klepnutím na **Vymazat vše** v odstínu oznámení. Tento problém s oznámením bude opraven v nadcházející verzi a instalace bude zcela tichá bez vizuálních indikátorů.

#### <a name="read-and-write-graph-api-operations-for-intune-apps---5031704----"></a>Čtení a zápis Graph APIch operací pro aplikace Intune<!-- 5031704  -->
Aplikace můžou volat Graph API Intune s použitím identity čtení i zápisu pomocí identity aplikace bez přihlašovacích údajů uživatele. Další informace o přístupu k rozhraní Microsoft Graph API pro Intune najdete [v tématu práce s Intune v Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="protected-data-sharing-and-encryption-for-intune-app-sdk-for-ios---3586942----"></a>Chráněné sdílení a šifrování dat pro sadu Intune App SDK pro iOS<!-- 3586942  -->
Sady Intune App SDK pro iOS bude používat 256bitových šifrovacích klíčů, když je povoleno šifrování pomocí zásad ochrany aplikací. Aby bylo možné chráněné sdílení dat, bude nutné, aby všechny aplikace měly sadu SDK verze 8.1.1.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="support-for-ikev2-vpn-profiles-for-ios---1943438-----"></a>Podpora pro profily IKEv2 VPN pro iOS<!-- 1943438   -->
V této aktualizaci můžete vytvořit profily sítě VPN pro nativního klienta VPN iOS pomocí protokolu IKEv2. IKEv2 je nový typ připojení v **konfiguraci zařízení** > **profily** > **vytvořit profil** > **iOS** pro typ profilu > **VPN** pro typ profilu > **Typ připojení**.

Tyto profily sítě VPN konfigurují nativního klienta VPN, takže nebudou nainstalovány ani vloženy žádné klientské aplikace VPN do spravovaných zařízení. Tato funkce vyžaduje, aby byla zařízení zaregistrovaná v Intune (registrace MDM).

Aktuální nastavení sítě VPN, která můžete nakonfigurovat, najdete v tématu [Konfigurace nastavení sítě VPN na zařízeních s iOS](../configuration/vpn-settings-ios.md).

Platí pro:

- iOS

#### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type---4886161-----"></a>Funkce zařízení, omezení zařízení a profily rozšíření pro nastavení iOS a macOS se zobrazují podle typu registrace.<!-- 4886161   -->

V Intune vytvoříte profily pro zařízení s iOS a macOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** nebo **MacOS** pro **funkce zařízení**>, **omezení zařízení**nebo **rozšíření** pro typ profilu). 

V této aktualizaci jsou dostupná nastavení na portálu Intune zařazená do kategorie podle typu registrace, na který se vztahují:

- iOS
  - Registrace uživatele
  - Registrace zařízení
  - Automatický zápis zařízení (pod dohledem)
  - Všechny typy registrace

- macOS
  - Schválené uživatelem
  - Registrace zařízení
  - Automatický zápis zařízení
  - Všechny typy registrace

Platí pro:

- iOS

#### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode---4892835-----"></a>Nové nastavení ovládání hlasu pro zařízení s iOS běžící v celoobrazovkovém režimu<!-- 4892835   -->
V Intune můžete vytvářet zásady, které budou spouštět zařízení se systémem iOS pod dohledem jako veřejný terminál nebo vyhrazené zařízení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro > **omezení zařízení** pro typ profilu > veřejný **terminál**).

V této aktualizaci můžete řídit nová nastavení:
- **Ovládání hlasu**: povolí hlasové ovládání zařízení v celoobrazovkovém režimu.
- **Změna ovládání hlasu**: umožňuje uživatelům změnit nastavení hlasového ovládacího prvku v zařízení v celoobrazovkovém režimu.

Aktuální nastavení zobrazíte tak, že přejdete na [Nastavení veřejného terminálu iOS](../configuration/device-restrictions-ios.md#kiosk).

Platí pro:

- iOS 13,0 a novější

#### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices---4893175-----"></a>Použití jednotného přihlašování pro aplikace a weby na zařízeních s iOS a macOS<!-- 4893175   -->
V této aktualizaci je k dispozici několik nových nastavení jednotného přihlašování pro zařízení s iOS a macOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** nebo **MacOS** pro **funkce zařízení** > pro typ profilu).

Pomocí těchto nastavení můžete nakonfigurovat jednotné přihlašování, zejména pro aplikace a weby, které používají ověřování pomocí protokolu Kerberos. Můžete si vybrat mezi obecnými přihlašovacími údaji jednotného přihlašování aplikace a integrovaným rozšířením Kerberos společnosti Apple.

Pokud chcete zobrazit aktuální funkce zařízení, které můžete konfigurovat, přejděte na [funkce zařízení s iOS](../configuration/ios-device-features-settings.md) a [MacOS funkce zařízení](../configuration/macos-device-features-settings.md).

Platí pro:

- iOS 13,0 a novější
- macOS 10,15 a novější

#### <a name="associate-domains-to-apps-on-macos-1015-devices---4898079-----"></a>Přidružení domén k aplikacím na macOS 10.15 a zařízeních<!-- 4898079   -->
Na zařízeních macOS můžete konfigurovat různé funkce a nasdílet je do zařízení pomocí zásad (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **MacOS** pro **funkce zařízení** > pro typ profilu). V této aktualizaci můžete k aplikacím přidružit domény. Tato funkce pomáhá sdílet přihlašovací údaje s weby souvisejícími s vaší aplikací a lze ji použít s rozšířením jednotného přihlašování společnosti Apple, univerzálními odkazy a automatického vyplňování hesel. 

Pokud chcete zobrazit aktuální funkce, které můžete nakonfigurovat, přejděte na [Nastavení funkcí zařízení MacOS v Intune](../configuration/macos-device-features-settings.md).

Platí pro:

- macOS 10,15 a novější

#### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices---4928474-----"></a>Při zobrazování nebo skrývání aplikací na zařízeních s iOS pod dohledem použijte v adrese URL obchodu iTunes aplikace iTunes a aplikace.<!-- 4928474   --> 
V Intune můžete vytvořit zásady, které budou zobrazovat nebo skrývat aplikace na zařízeních s iOS pod dohledem (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro > **omezení zařízení** pro typ profilu > **Zobrazit nebo skrýt aplikace**). 

Můžete zadat adresu URL obchodu s aplikacemi iTunes, například `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`. V této aktualizaci lze v adrese URL použít jak `apps`, tak `itunes`, například:
- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Další informace o těchto nastaveních najdete v tématu [zobrazení nebo skrytí aplikací](../configuration/device-restrictions-ios.md#show-or-hide-apps).

Platí pro:
- iOS

#### <a name="windows-10-compliance-policy-password-type-values-are-clearer-and-match-csp---5138985---"></a>Hodnoty typu hesla zásad dodržování předpisů ve Windows 10 jsou jasné a neshodné s poskytovatelem CSP.<!-- 5138985 -->
V zařízeních s Windows 10 můžete vytvořit zásady dodržování předpisů, které vyžadují konkrétní funkce hesla ( **zásady** > **dodržování předpisů zařízením** > **vytvořit zásadu** > **Windows 10 a novější** pro zabezpečení platformy > **System**). V této aktualizaci:
- Hodnoty **typu hesla** jsou jasné a aktualizované tak, aby ODPOVÍDALy [zprostředkovateli DeviceLock/AlphanumericDevicePasswordRequired](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired).
- Nastavení **vypršení platnosti hesla (dny)** se aktualizuje, aby se povolily hodnoty z 1-730 dnů. 

Další informace o nastavení dodržování předpisů ve Windows 10 najdete v tématu [nastavení Windows 10 a novějších k označení zařízení jako odpovídajících nebo nevyhovujících](../protect/compliance-policy-create-windows.md)předpisům. 

Platí pro:
- Windows 10 a novější

 #### <a name="updated-ui-for-configuring-microsoft-exchange-on-premises-access---4092920---"></a>Aktualizované uživatelské rozhraní pro konfiguraci přístupu k místnímu systému Microsoft Exchange<!-- 4092920 -->  
Aktualizovali jsme konzolu, kde jste [nakonfigurovali přístup k místnímu přístupu Microsoft Exchange](../protect/conditional-access-exchange-create.md). Všechny konfigurace pro přístup k místnímu Exchangi jsou teď dostupné ve stejném podokně konzoly, kde můžete *Povolit řízení přístupu k místnímu Exchangi*.  

#### <a name="allow-or-restrict-adding-app-widgets-to-the-home-screen-on-android-enterprise-work-profile-devices---1109650----"></a>Povolení nebo omezení přidání widgetů aplikací na domovskou obrazovku na zařízeních s pracovními profily Android Enterprise<!-- 1109650  --> 
Na zařízeních s Androidem Enterprise můžete nakonfigurovat funkce v pracovním profilu (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** for Platform > **Work Profiles > jenom omezení zařízení** pro typ profilu). V této aktualizaci můžete uživatelům dovolit přidávat widgety, které jsou zpřístupněny aplikacemi pracovní profil na domovské obrazovce zařízení.

Pokud chcete zobrazit nastavení, která můžete nakonfigurovat, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-android-for-work.md).

Platí pro:
- Pracovní profil Android Enterprise

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="new-tenants-will-default-away-from-android-device-administrator-management---4869790-----"></a>Ve výchozím nastavení budou noví klienti pryč ze správy zařízení s Androidem.<!-- 4869790   -->
Možnosti Správce zařízení s Androidem jsou nahrazené Androidem Enterprise. Proto doporučujeme místo toho použít Android Enterprise pro nové registrace. V budoucí aktualizaci budou muset noví klienti v rámci registrace zařízení s Androidem v případě použití správy Správce zařízení provést následující nezbytné kroky: Přejít na **Intune** > **registrace zařízení** > **registrace Androidu** > **osobních a firemních zařízení s oprávněními** Správce zařízení > **ke správě zařízení použít Správce zařízení**.

Stávající klienti nebudou mít ve svých prostředích žádné změny.

Další informace o Správci zařízení s Androidem v Intune najdete v tématu [registrace Správce zařízení s Androidem](https://docs.microsoft.com/intune/android-enroll-device-administrator).

#### <a name="list-of-dep-devices-associated-with-a-profile---5012045-idmiss---"></a>Seznam zařízení DEP přidružených k profilu<!-- 5012045 idmiss -->
Teď můžete zobrazit stránkovaný seznam zařízení Apple automatizované Program registrace zařízení (DEP), která jsou přidružená k profilu. Seznam můžete vyhledat na libovolné stránce v seznamu. Pokud chcete zobrazit seznam, přejděte na **Intune** > **registrace zařízení** > registrace **Apple** > **tokeny programu registrace** > vyberte profily >ch **profilů** > vyberte profil > **přiřazená zařízení** (v části **monitor**).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Správa zařízení

#### <a name="more-android-fully-managed-support---3464667-4631425-4631440-5227935-4062195-----"></a>Další plně spravovaná podpora Androidu<!-- 3464667, 4631425, 4631440, 5227935, 4062195   -->
Přidali jsme následující podporu pro plně spravovaná zařízení s Androidem:

- Certifikáty SCEP pro plně spravovanou Android jsou k dispozici pro ověřování certifikátů na zařízeních spravovaných jako vlastník zařízení. Certifikáty SCEP jsou už na zařízeních pracovního profilu podporované.  Pomocí certifikátů SCEP pro vlastníka zařízení budete moct: <!-- 5227935 -->
    - Vytvoření profilu SCEP v části DO v Androidu Enterprise
    - propojení certifikátů SCEP s profilem Wi-Fi pro ověřování
    - propojení certifikátů SCEP a provádění profilů sítě VPN pro ověřování
    - propojení certifikátů SCEP pro ověřování e-mailových profilů (přes AppConfig)
- Systémové aplikace jsou podporované na zařízeních s Androidem Enterprise. V Intune přidejte aplikaci systému Android Enterprise, a to tak, že vyberete **klientské aplikace** > **aplikací** > **Přidat**. V seznamu **Typ aplikace** vyberte aplikace pro **Android Enterprise System**. Další informace najdete v tématu [Přidání aplikací pro Android Enterprise System do Microsoft Intune](../apps/apps-ae-system.md). <!-- 4062195 -->
- V části **dodržování předpisů zařízením** > **vlastníka zařízení**pro **Android Enterprise** > můžete vytvořit zásady dodržování předpisů, které nastaví úroveň ověření Google SafetyNet.   <!-- 4631425 -->
- Na zařízeních s plnou správou Androidu Enterprise se podporují poskytovatelé ochrany před mobilními hrozbami. V **dodržování předpisů zařízením** > **vlastníka zařízení**s **Androidem Enterprise** > můžete vybrat přijatelnou úroveň hrozeb. <!-- 4631440 --> [Nastavení Androidu Enterprise k označení zařízení jako kompatibilních nebo nekompatibilních s použitím Intune](../protect/compliance-policy-create-android-for-work.md#device-owner) seznam aktuálních nastavení.
- Na zařízeních s plnou správou Androidu Enterprise se teď dá nakonfigurovat aplikace spouštěče Microsoftu prostřednictvím zásad konfigurace aplikací, které umožňují standardizované prostředí koncového uživatele na plně spravovaném zařízení. K přizpůsobení zařízení s Androidem se dá použít aplikace Microsoft spouštěče. Pomocí aplikace spolu s účet Microsoft nebo pracovním nebo školním účtem máte přístup k vašemu kalendáři, dokumentům a posledním aktivitám v přizpůsobeném kanálu. <!-- 5334044 -->

V této aktualizaci jsme spokojeni s oznámením, že podpora Intune pro plně spravovanou platformu Android Enterprise je teď všeobecně dostupná.

Platí pro:

- Zařízení se systémem Android Enterprise s plnou správou

#### <a name="send-custom-notifications-to-a-single-device---4928910---"></a>Odesílání vlastních oznámení na jedno zařízení<!-- 4928910 -->
Teď můžete vybrat jedno zařízení a pak použít akci vzdáleného zařízení k [odeslání vlastního oznámení jenom na toto zařízení](../remote-actions/custom-notifications.md#send-a-custom-notification-to-a-single-device).

#### <a name="wipe-and-passcode-reset-actions-arent-available-for-ios-devices-that-are-enrolled-by-using-user-enrollment---4950491---"></a>Akce vymazání a resetování hesla nejsou k dispozici pro zařízení s iOS, která jsou zaregistrovaná pomocí zápisu uživatelů.<!-- 4950491 -->
Zápis uživatele je nový typ registrace zařízení Apple. Při registraci zařízení pomocí registrace uživatele nebudou pro taková zařízení k dispozici vzdálené akce resetování a resetování hesla.

#### <a name="intune-support-for-ios-13-and-macos-catalina-devices---4665317---"></a>Podpora Intune pro zařízení s iOS 13 a macOS Catalina<!-- 4665317 -->
Intune teď podporuje správu zařízení se systémem iOS 13 i macOS Catalina.
Další informace najdete v [příspěvku na blogu Microsoft Intune podpoře pro iOS 13 a iPadOS](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-and-iPadOS/ba-p/861998).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Zabezpečení zařízení

#### <a name="bitlocker-support-for-client-driven-recovery-password-rotation----3444125---"></a>Podpora BitLockeru pro otočení hesla pro obnovení na základě klienta<!--  3444125 -->
Použijte nastavení Endpoint Protection Intune ke konfiguraci [rotace hesla pro obnovení](../protect/endpoint-protection-windows-10.md#windows-encryption) na zařízeních s Windows verze 1909 nebo novějším na základě klienta.

Toto nastavení inicializuje obnovení hesla na základě klienta po obnovení jednotky operačního systému (buď pomocí programu Bootmgr nebo WinRE) a odemknutí hesla pro obnovení na pevné datové jednotce. Toto nastavení aktualizuje specifické heslo pro obnovení, které bylo použito, a jiná nepoužívaná hesla na svazku zůstanou beze změny. Další informace najdete v dokumentaci k nástroji BitLocker CSP pro [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp).

#### <a name="tamper-protection-for-windows-defender-antivirus---4705448----------"></a>Ochrana proti úmyslné ochraně pro antivirovou ochranu v programu Windows Defender<!-- 4705448        -->
Použijte Intune ke správě *ochrany před zneužitím antivirové ochrany* v programu Windows Defender. Pokud použijete konfigurační profily zařízení pro Windows 10 Endpoint Protection, najdete [nastavení pro ochranu proti falšování](../protect/endpoint-protection-windows-10.md#microsoft-defender-security-center) ve skupině Security Center programu Microsoft Defender. Ochranu proti neoprávněným nastavením ochrany proti chybám můžete *nastavit tak, aby se* zapnulo omezení ochrany před odesláním, nastavení *zakázáno* pro jejich vypnutí, nebo nastavit, aby se zařízení*nenakonfigurovalo* jako aktuální konfigurace.  

Další informace o ochraně před zneužitím najdete v dokumentaci k Windows v tématu [zabránění změnám nastavení zabezpečení pomocí ochrany před neoprávněnými](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) změnami.

#### <a name="advanced-settings-for-windows-defender-firewall-are-now-generally-available----5317392---------"></a>Rozšířená nastavení pro firewall v programu Windows Defender jsou teď všeobecně dostupná.<!--  5317392       -->  
[Vlastní pravidla brány firewall v programu Windows Defender pro službu Endpoint Protection](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices), která konfigurujete jako součást profilu konfigurace zařízení, jsou ve verzi Public Preview a jsou všeobecně dostupná (GA).  Tato pravidla můžete použít k určení příchozího a odchozího chování aplikací, síťových adres a portů. Tato pravidla byla vydaná v červenci jako verze Public Preview. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="scope-tags-now-support-terms-of-use-policies---2358863-idmiss---"></a>Značky oboru teď podporují zásady používání podmínek použití<!-- 2358863 idmiss -->
Nyní můžete přiřadit [značky oboru](scope-tags.md) k zásadám použití. Provedete to tak, že přejdete na **Intune** > **registrace zařízení** > **podmínky** > vyberte položku v seznamu > **vlastnosti** > **značky oboru** > vyberte značku oboru.

## <a name="week-of-september-9-2019"></a>Týden od 9. září 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="updates-to-microsoft-intune-app---4997846---"></a>Aktualizace aplikace Microsoft Intune<!-- 4997846 -->
Microsoft Intune aplikace pro Android se aktualizovala s následujícími vylepšeními:
- Aktualizace a vylepšení rozložení tak, aby obsahovalo Dolní navigační údaje nejdůležitějších akcí.
- Přidala se další stránka, která zobrazuje profil uživatele.
- Do aplikace pro uživatele se přidalo zobrazování oznámení s možnou akcí, například nutnost aktualizovat nastavení zařízení.
- Přidali jsme zobrazení vlastních nabízených oznámení a zarovnejte aplikaci s podporou, která byla nedávno přidaná v aplikaci Portál společnosti pro iOS a Android. Další informace najdete v tématu [odesílání vlastních oznámení v Intune](../remote-actions/custom-notifications.md).

#### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal---4394993---"></a>Pro zařízení s iOS si Přizpůsobte obrazovku ochrana osobních údajů procesu registrace Portál společnosti<!-- 4394993 -->
Pomocí Markdownu můžete přizpůsobit obrazovku osobních údajů Portál společnosti, kterou koncoví uživatelé uvidí během registrace iOS. Konkrétně budete moct přizpůsobit seznam věcí, které vaše organizace nemůže zobrazit nebo dělat na zařízení. Další informace najdete v tématu [Konfigurace aplikace Portál společnosti Intune](../apps/company-portal-app.md#privacy-statement-customization).


## <a name="week-of-september-2-2019"></a>Týden od 2. září 2019

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="intune-user-interface-update--tenant-status-dashboard---5273210----"></a>Aktualizace uživatelského rozhraní Intune – řídicí panel stavu tenanta<!-- 5273210  -->
Uživatelské rozhraní pro řídicí panel stavu tenanta se aktualizovalo tak, aby bylo zarovnané na styly uživatelského rozhraní Azure. Další informace najdete v tématu [stav tenanta](../tenant-status.md).

## <a name="week-of-august-26-2019"></a>Týden od 26. srpna 2019

### <a name="configure-microsoft-edge-settings-using-administrative-templates-for-windows-10-and-newer---5228061---"></a>Konfigurace nastavení Microsoft Edge pomocí šablon pro správu pro Windows 10 a novější<!-- 5228061 -->

V zařízeních s Windows 10 a novějších můžete vytvořit šablony pro správu a nakonfigurovat nastavení zásad skupiny v Intune. V této aktualizaci můžete nakonfigurovat nastavení, která se vztahují na Microsoft Edge verze 77 a novější.

Další informace o šablonách pro správu najdete v tématu [použití šablon Windows 10 ke konfiguraci nastavení zásad skupiny v Intune](../configuration/administrative-templates-windows.md).

Platí pro:

- Windows 10 a novější (Windows RS4 +)

## <a name="week-of-august-12-2019-1908-service-release"></a>Týden od 12. srpna 2019 (1908 Service Release)

### <a name="app-management"></a>Správa aplikací

#### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment---3504144-----"></a>Řízení chování při odinstalaci aplikace pro iOS při zrušení registrace zařízení<!-- 3504144   -->
Správci mohou spravovat, zda je aplikace v zařízení odebrána nebo udržována v případě, že je zařízení odregistrováno na úrovni uživatele nebo skupiny zařízení. 

#### <a name="categorize-microsoft-store-for-business-apps---3926922---"></a>Kategorizace Microsoft Store pro obchodní aplikace<!-- 3926922 -->
Microsoft Store pro obchodní aplikace můžete zařadit do kategorií. Provedete to tak, že v **Intune** > **klientských aplikacích** > **aplikace** > vyberete **kategorii**> **informace o aplikaci** Microsoft Store pro obchodní aplikace > . V rozevírací nabídce přiřaďte kategorii.

#### <a name="customized-notifications-for-microsoft-intune-app-users---4843354----"></a>Přizpůsobená oznámení pro uživatele aplikací Microsoft Intune<!-- 4843354  -->
Microsoft Intune aplikace pro Android teď podporuje zobrazení vlastních nabízených oznámení a jejich vyrovnání s podporou, která se nedávno přidala v Portál společnosti aplikacích pro iOS a Android. Další informace najdete v tématu [odesílání vlastních oznámení v Intune](../remote-actions/custom-notifications.md).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode---3755304-3041943-3041946-----"></a>Nové funkce pro vyhrazená zařízení s Androidem Enterprise v režimu více aplikací<!-- 3755304 3041943 3041946   -->

V Intune můžete ovládat funkce a nastavení pomocí veřejného terminálu na vyhrazených zařízeních s Androidem Enterprise (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** pro vlastní platformu > jenom pro **vlastníka zařízení, omezení zařízení** pro typ profilu).

V této aktualizaci se přidávají následující funkce:

- **Vyhrazená zařízení** > **více aplikacemi**: **tlačítko virtuální domů** se dá na zařízení zobrazit roztažením nahoru nebo plovoucí na obrazovce, aby ho uživatelé mohli přesunout.
- **Vyhrazená zařízení** > **více aplikacemi**: **přístup svítící** umožňuje uživatelům používat svítící. 
- **Vyhrazená zařízení** > **více aplikacemi**: **ovládání hlasitosti médií** umožňuje uživatelům řídit hlasitost média zařízení pomocí posuvníku. 
- **Vyhrazená zařízení** > **více aplikacemi**: **Povolte šetřič obrazovky**, nahrajte vlastní obrázek a ovládací prvek, když se zobrazí spořič obrazovky.

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

Platí pro:

- Zařízení se systémem Android Enterprise vyhrazená

#### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices---3574215-3574238-3574235-3574232-----"></a>Nové aplikace a konfigurační profily pro zařízení s plnou správou pro Android Enterprise<!-- 3574215 3574238 3574235 3574232   -->
Pomocí profilů můžete nakonfigurovat nastavení, která použijí nastavení sítě VPN, e-mailu a Wi-Fi, na zařízení s vlastníkem zařízení s Androidem Enterprise (plně spravovaná). V této aktualizaci můžete:

- Pomocí [zásad konfigurace aplikací](../apps/app-configuration-policies-use-android.md) nasaďte nastavení Outlooku, Gmail a devět pracovních e-mailů.
- Pomocí profilů konfigurace zařízení nasaďte [Nastavení důvěryhodných kořenových certifikátů](../protect/certificates-configure.md).
- Pomocí profilů konfigurace zařízení nasaďte nastavení [sítě VPN](../configuration/vpn-settings-android-enterprise.md) a [Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md) .

> [!IMPORTANT]
> S touto funkcí se uživatelé ověřují pomocí svého uživatelského jména a hesla pro profily sítě VPN, Wi-Fi a e-mailu. V současné době není ověřování založené na certifikátech k dispozici.

Platí pro:  
- Vlastník zařízení se systémem Android Enterprise (plně spravovaný)

#### <a name="control-the-apps-files-documents-and-folders-that-open-when-users-sign-in-to-macos-devices--3914202-----"></a>Řízení aplikací, souborů, dokumentů a složek, které se otevřou, když se uživatelé přihlásí k zařízením macOS<!--3914202   -->
Můžete povolit a nakonfigurovat funkce na zařízeních macOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **MacOS** pro **funkce zařízení** > pro typ profilu). 

V této aktualizaci se nachází nové nastavení přihlašovacích položek, které určuje, které aplikace, soubory, dokumenty a složky se otevřou, když se uživatel přihlásí k zaregistrovanému zařízení. 

Pokud chcete zobrazit aktuální nastavení, přejděte na [Nastavení funkcí zařízení MacOS v Intune](../configuration/macos-device-features-settings.md).

Platí pro:  
- macOS

#### <a name="deadlines-replace-engaged-restart-settings-for-windows-update-rings---4464404----------"></a>Konečné termíny nahrazují nastavení opětovného spuštění pro web Windows Update okruhy<!-- 4464404        -->
Pro zajištění souladu s nejnovějšími [změnami údržby Windows](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903#servicing)teď aktualizační kanály Windows 10 v Intune [podporují nastavení pro konečné termíny](../protect/windows-update-settings.md). *Konečné termíny* určují, kdy zařízení nainstaluje funkce a aktualizace zabezpečení.  V zařízeních se systémem Windows 10 1903 nebo novějším mají *termíny* přednost před konfiguracemi pro *následné restartování*.  V budoucnu se *konečné termíny* *nahrazují i v dřívějších* verzích Windows 10.  

Když nebudete konfigurovat *konečné termíny*, budou se zařízení dál používat s nastavením jejich nastavení, ale Intune bude v budoucí aktualizaci zastaralá o podporu *pro nastavení.*  

Naplánujte použití *konečných termínů* pro všechna vaše zařízení s Windows 10. Po nastavení *konečných termínů* můžete změnit konfigurace Intune, aby se *restarty* nenakonfigurovaly. Pokud je nastavené na Nenakonfigurováno, Intune zastaví správu těchto nastavení na zařízeních, ale neodebere poslední konfigurace nastavení ze zařízení. Poslední konfigurace, které byly nastavené pro probíhající *restart* , zůstávají aktivní a používají se na zařízeních, dokud se tato nastavení neupraví jinou metodou než Intune. Později, když se změní verze Windows, nebo když se u *konečných termínů* podpora Intune dokončí rozšíření zařízení na verzi Windows, začne používat nové nastavení, které už jsou na svém místě.

#### <a name="support-for-multiple-microsoft-intune-certificate-connectors-----4704642--------"></a>Podpora více Microsoft Intunech konektorů certifikátů<!--   4704642      -->
Intune teď podporuje instalaci a používání více [Microsoft Intunech konektorů certifikátů pro operace PKCS](../protect/certficates-pfx-configure.md). Tato změna podporuje vyrovnávání zatížení a vysokou dostupnost konektoru. Každá instance konektoru může zpracovávat žádosti o certifikát z Intune.  Pokud jeden konektor není k dispozici, ostatní konektory pokračují v zpracování požadavků.

Chcete-li použít více konektorů, nemusíte upgradovat na nejnovější verzi softwaru konektoru.  

#### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices---4867699-4867709-----"></a>Nové nastavení a změny stávajících nastavení pro omezení funkcí v zařízeních s iOS a macOS<!-- 4867699 4867709   -->
Můžete vytvořit profily k omezení nastavení na zařízeních s iOS a macOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** nebo **MacOS** pro typ platformy > **omezení zařízení**). Tato aktualizace obsahuje následující funkce:

- V **macOS** > **omezení zařízení** > **cloudu a úložišti**, **použijte nové nastavení** pro překládání, které uživatelům zabrání ve spouštění práce na jednom zařízení macOS a pokračujte v práci na jiném zařízení MacOS nebo iOS.

  Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení MacOS a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-macos.md).

- V případě zařízení se **systémem iOS** > **omezení zařízení**existuje několik změn:

  - **Integrované aplikace** > **Najít iPhone (jenom pod dohledem)** : nové nastavení, které tuto funkci blokuje v funkci najít aplikaci. 
  - **Integrované aplikace** > **Najít přátele (jenom pod dohledem)** : nové nastavení, které tuto funkci blokuje v funkci najít aplikaci. 
  - **Bezdrátová** > **Změna stavu Wi-Fi (jenom pod dohledem)** : nové nastavení, které uživatelům brání v zapnutí nebo vypnutí Wi-Fi na zařízení.
  - **Klávesnice a slovník** > **QuickPath (jenom pod dohledem)** : nové nastavení, které blokuje funkci QuickPath.
  - **Cloud a úložiště**: **pokračování aktivity** se přejmenovalo na **odevzdání**.

  Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s iOS, abyste mohli povolit nebo zakázat funkce využívající Intune](../configuration/device-restrictions-ios.md).

Platí pro:  
- macOS 10,15 a novější
- iOS 13 a novější

#### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release---4867809-----"></a>Některá z nesledovaných omezení zařízení s iOS se budou pod dohledem – jenom s vydáním iOS 13,0.<!-- 4867809   -->
V této aktualizaci se některá nastavení vztahují na zařízení, která jsou jenom pod dohledem, pomocí verze iOS 13,0. Pokud jsou tato nastavení nakonfigurovaná a přiřazená k zařízením, která nejsou pod dohledem před vydáním iOS 13,0, nastavení se pořád aplikují na tato zařízení, která nejsou pod dohledem. I nadále platí i po upgradu zařízení na iOS 13,0. Tato omezení se odeberou na nekontrolovaných zařízeních, která se zálohují a obnovují.

Nastavení zahrnuje tyto položky:

- App Store, zobrazování dokumentů, hraní her
  - App Store
  - Explicitní obsah iTunes, hudba, podcast nebo zprávy
  - Přidání přátel Game Center
  - Hry pro víc hráčů
- Integrované aplikace
  - Fotoaparát
    - FaceTime
  - Safari
    - Automatické vyplnění
- Cloud a úložiště
  - Zálohování do iCloud
  - Zablokovat synchronizaci dokumentů iCloud
  - Blokovat synchronizaci řetězce klíčů iCloud

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s iOS, abyste mohli povolit nebo zakázat funkce využívající Intune](../configuration/device-restrictions-ios.md).

Platí pro:  
- iOS 13,0 a novější

#### <a name="improved-device-status-for-macos-filevault-encryption---4944983-----------"></a>Vylepšený stav zařízení pro šifrování trezoru macOS<!-- 4944983         -->
Aktualizovali jsme několik zpráv o [stavu zařízení](../protect/encryption-monitor.md#device-encryption-status) pro šifrování trezoru úložiště na zařízeních MacOS.

#### <a name="some-windows-defender-antivirus-scan-settings-in-the-reporting-show-a-failed-status---5119229---"></a>Některá nastavení kontroly antivirové ochrany v programu Windows Defender v hlášení zobrazují stav selhání<!-- 5119229 -->
V Intune můžete vytvořit zásady, které budou používat antivirovou ochranu v programu Windows Defender ke skenování zařízení s Windows 10 (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** pro > **omezení zařízení** pro typ profilu > **antivirová ochrana v programu Windows Defender**). Čas, kdy **má probíhat každodenní Rychlá kontrola** a **typ Systémové kontroly k provedení** sestav, zobrazuje stav selhání, pokud je ve skutečnosti stav úspěch. 

V této aktualizaci je toto chování opraveno. Takže když se nastavení úspěšně dokončí, zobrazí se při úspěšném prověřování stav úspěch a v případě, že se nastavení nepovede, zobrazí se stav úspěšného provedení **každodenní rychlé kontroly** a **typ kontroly prováděné systémem** .

Další informace o nastavení antivirové ochrany v programu Windows Defender najdete v tématu [nastavení zařízení s Windows 10 (a novější) k povolení nebo omezení funkcí v Intune](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="default-scope-tags---3702875----"></a>Výchozí značky oboru<!-- 3702875  -->
Nově integrovaná značka výchozího oboru je nyní k dispozici. Všechny neoznačené objekty Intune, které podporují značky oboru, se automaticky přiřazují k výchozí značce oboru. **Výchozí** značka oboru je přidána do všech existujících přiřazení rolí, aby bylo udržování parity s prostředím pro správu v současnosti. Pokud nechcete, aby správce viděli objekty Intune s výchozím označením oboru, odeberte z přiřazení role výchozí značku oboru. Tato funkce je podobná funkci obory zabezpečení v Configuration Manager. Další informace najdete v tématu [použití značek RBAC a Scope k distribuci](scope-tags.md).

#### <a name="android-enrollment-device-administrator-support---4869749-----"></a>Podpora Správce zařízení registrace Androidu<!-- 4869749   -->
Do registrační stránky pro Android se přidala možnost registrace Správce zařízení s Androidem ( > **registrace zařízení** v**Intune** > **registraci v Androidu**). Správce zařízení s Androidem bude ve výchozím nastavení pro všechny klienty stále povolen.  Další informace najdete v tématu [registrace Správce zařízení s Androidem](../enrollment/android-enroll-device-administrator.md).

#### <a name="skip-more-screens-in-setup-assistant---4877451----"></a>Přeskočit další obrazovky v Průvodci nastavením <!--4877451  -->
Můžete nastavit Program registrace zařízení profily pro přeskočení následujících obrazovek pomocníka s nastavením:
- Pro iOS
    - Vzhled
    - Jazyk Express
    - Preferovaný jazyk
    - Migrace zařízení do zařízení
- Pro macOS
    - Čas obrazovky
    - Nastavení Touch ID

Další informace o přizpůsobení pomocníka s nastavením najdete v tématu [vytvoření registračního profilu Apple pro iOS](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) a [vytvoření registračního profilu Apple pro MacOS ](../enrollment/device-enrollment-program-enroll-macos.md#create-an-apple-enrollment-profile).

#### <a name="add-a-user-column-to-the-autopilot-device-csv-upload-process---3823054---"></a>Přidání uživatelského sloupce do procesu nahrání souboru CSV pro zařízení s autopilotem<!-- 3823054 -->
Nyní můžete přidat uživatelský sloupec do nahrávání sdíleného svazku clusteru pro zařízení s autopilotem. To vám umožní hromadně přiřazovat uživatele v době, kdy naimportujete sdílený svazek clusteru. Další informace najdete v tématu [registrace zařízení s Windows v Intune pomocí automatických pilotů Windows](../enrollment/enrollment-autopilot.md).


### <a name="device-management"></a>Správa zařízení

#### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days--4231059----"></a>Nakonfigurujte automatický časový limit pro vyčištění zařízení na 30 dní.<!--4231059  -->
Můžete nastavit automatický časový limit pro vyčištění zařízení, který je kratší než 30 dní (místo předchozího limitu 90 dní) po posledním přihlášení. Provedete to tak, že přejdete na **zařízení** > **Intune** > **Nastavení** > **pravidla čištění zařízení**.

#### <a name="build-number-included-on-android-device-hardware-page---4461910-----"></a>Číslo sestavení zahrnuté na stránce hardware pro zařízení s Androidem<!-- 4461910   -->
Nová položka na stránce hardware pro každé zařízení s Androidem zahrnuje číslo buildu operačního systému daného zařízení. Další informace najdete v tématu [zobrazení podrobností o zařízení v Intune](../remote-actions/device-inventory.md).


<!-- ########################## -->

## <a name="week-of-august-5-2019"></a>Týden od 5. srpna 2019

### <a name="zebra-technologies-is-a-supported-oem-for-oemconfig-on-android-enterprise-devices---4843713---"></a>Technologie Zebra je podporovaným výrobcem OEM pro OEMConfig na zařízeních s Androidem Enterprise.<!-- 4843713 -->

V Intune můžete vytvořit profily konfigurace zařízení a použít nastavení pro zařízení s Androidem Enterprise pomocí OEMConfig (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** for Platform > **OEMConfig** pro typ profilu).

V této aktualizaci je Zebra technologie podporovaným výrobcem OEM (Original Equipment Manufacturer) pro OEMConfig. Další informace o OEMConfig najdete v tématu [použití a Správa zařízení s Androidem Enterprise pomocí OEMConfig](../configuration/android-oem-configuration-overview.md).

Platí pro:  
- Android Enterprise

<!-- ########################## -->

## <a name="week-of-july-22-2019-1907-service-release"></a>Týden od 22. července 2019 (1907 Service Release)

### <a name="app-management"></a>Správa aplikací

#### <a name="customized-notifications-for-users-and-groups---16766574------------"></a>Přizpůsobená oznámení pro uživatele a skupiny<!-- 16766574          -->
Odešlete vlastní nabízená oznámení z aplikace Portál společnosti uživatelům na zařízeních s iOS a Androidem, která spravujete pomocí Intune. Tato mobilní nabízená oznámení jsou vysoce přizpůsobitelná s bezplatným textem a lze je použít pro libovolný účel. Můžete je cílit na různé skupiny uživatelů ve vaší organizaci. Další informace najdete v tématu [vlastní oznámení](../remote-actions/custom-notifications.md).

#### <a name="googles-device-policy-controller-app---3041950----"></a>Aplikace kontroleru zásad zařízení Google<!-- 3041950  -->
Aplikace spravované domovské obrazovky teď poskytuje přístup k aplikaci zásad zařízení s Androidem. Spravovaná aplikace pro domovskou obrazovku je vlastní spouštěč používaný pro zařízení zaregistrovaná v Intune jako vyhrazená zařízení Android Enterprise (AE) pomocí celoobrazovkového režimu s více aplikacemi. K aplikaci zásad pro zařízení s Androidem můžete získat přístup, nebo se uživatelé k aplikaci zásad zařízení s Androidem pořídit pro účely podpory a ladění. Tato funkce je k dispozici v době, kdy se zařízení zaregistruje a zamkne do spravované domovské obrazovky. K použití této funkce nejsou potřeba žádné další instalace.

#### <a name="outlook-protection-settings-for-ios-and-android-devices---3212619---"></a>Nastavení ochrany Outlooku pro zařízení s iOS a Androidem<!-- 3212619 -->
Pro Outlook pro iOS a Android teď můžete nakonfigurovat obecná nastavení konfigurace aplikací a ochrany dat, a to pomocí jednoduchých ovládacích prvků pro správu Intune bez registrace zařízení. Obecné nastavení konfigurace aplikací poskytuje paritu nastavení správci můžou povolit při správě Outlooku pro iOS a Android na zaregistrovaných zařízeních. Další informace o nastavení aplikace Outlook najdete v tématu [nasazení aplikace Outlook pro iOS a nastavení konfigurace aplikací pro Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910-eeready------"></a>Při vytváření profilů konfigurace zařízení s Windows 10 použít pravidla použitelnosti <!-- 2549910 eeready    -->

Vytvoříte profily konfigurace zařízení s Windows 10 (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10** pro **pravidla použitelnosti**platformy >). V této aktualizaci můžete vytvořit **pravidlo použitelnosti** , aby se profil mohl vztahovat jenom na konkrétní edici nebo konkrétní verzi. Můžete například vytvořit profil, který povolí některá nastavení nástroje BitLocker. Po přidání profilu použijte pravidlo použitelnosti, aby se profil mohl vztahovat jenom na zařízení s Windows 10 Enterprise.

Pokud chcete přidat pravidlo použitelnosti, přečtěte si téma [pravidla použitelnosti](../configuration/device-profile-create.md#applicability-rules).

Platí pro: Windows 10 a novější

#### <a name="use-tokens-to-add-device-specific-information-in-custom-profiles-for-ios-and-macos-devices---3330008----"></a>Použití tokenů k přidání informací specifických pro zařízení v uživatelských profilech pro zařízení s iOS a macOS<!-- 3330008  -->
Pomocí vlastních profilů na zařízeních s iOS a macOS můžete nakonfigurovat nastavení a funkce, které nejsou integrované do Intune (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** nebo **MacOS** pro Platform > **Custom** pro typ profilu). V této aktualizaci můžete do souborů `.mobileconfig` přidat tokeny a přidat informace specifické pro zařízení. Můžete například přidat `Serial Number: {{serialnumber}}` do konfiguračního souboru, aby se zobrazilo sériové číslo zařízení.

Pokud chcete vytvořit vlastní profil, přečtěte si téma [vlastní nastavení pro iOS](../configuration/custom-settings-ios.md) nebo [MacOS vlastní nastavení](../configuration/custom-settings-macos.md).

Platí pro:
- iOS
- macOS

#### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise---3712769-----"></a>Nový Návrhář konfigurace při vytváření profilu OEMConfig pro Android Enterprise<!-- 3712769   -->
V Intune můžete vytvořit konfigurační profil zařízení, který používá aplikaci OEMConfig (konfigurace zařízení > Profily > vytvořit profil > Android Enterprise for Platform > OEMConfig pro typ profilu). Když to uděláte, otevře se Editor JSON se šablonou a hodnotami, které můžete změnit. 

Tato aktualizace obsahuje návrháře konfigurace s vylepšeným uživatelským prostředím, které zobrazuje podrobnosti vložené do aplikace včetně nadpisů, popisů a dalších. Editor JSON je stále k dispozici a zobrazuje všechny změny, které provedete v Návrháři konfigurace.

Pokud chcete zobrazit aktuální nastavení, přejděte na [používání a Správa zařízení s Androidem Enterprise pomocí OEMConfig](../configuration/android-oem-configuration-overview.md).

Platí pro: Android Enterprise

#### <a name="updated-ui-for-configuring-windows-hello---4089576--------------"></a>Aktualizované uživatelské rozhraní pro konfiguraci Windows Hello<!-- 4089576            -->
Aktualizovali jsme konzolu, ve které [nakonfigurujete Intune tak, aby používala Windows Hello pro firmy](../protect/windows-hello.md). Všechna nastavení konfigurace jsou nyní k dispozici ve stejném podokně konzoly, kde povolíte podporu pro Windows Hello.

#### <a name="intune-powershell-sdk---4924113---"></a>Sada Intune PowerShell SDK<!-- 4924113 --> 
Sada Intune PowerShell SDK, která poskytuje podporu pro rozhraní Intune API prostřednictvím Microsoft Graph, se aktualizovala na verzi 6.1907.1.0. Sada SDK teď podporuje následující:
- Funguje s Azure Automation.
- Podporuje operace čtení jenom pro aplikace. 
- Podporuje popisné zkrácené názvy jako aliasy.
- Vyhovuje konvencím pojmenování PowerShellu. Konkrétně byl parametr `PSCredential` (na rutině `Connect-MSGraph`) přejmenován na `Credential`.
- Při použití rutiny `Invoke-MSGraphRequest` podporuje Ruční určení hodnoty hlavičky `Content-Type`.

Další informace najdete v tématu [sada PowerShell SDK pro Microsoft Intune Graph API](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune).


### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="updates-for-enrollment-restrictions---2871968---"></a>Aktualizace pro omezení registrace<!-- 2871968 -->
Byla aktualizována omezení registrace pro nové klienty, aby byly ve výchozím nastavení povoleny pracovní profily Android Enterprise. Stávající klienti nebudou mít žádné změny. Pokud chcete používat pracovní profily Android Enterprise, musíte [svůj účet Intune připojit k vašemu spravovanému účtu Google Play](../enrollment/connect-intune-android-enterprise.md).

#### <a name="ui-updates-for-apple-enrollment-and-enrollment-restrictions--4089575-4089579----"></a>Aktualizace uživatelského rozhraní pro registrace Apple a omezení registrace<!--4089575, 4089579  -->
Oba následující procesy používají uživatelské rozhraní ve stylu Průvodce:
- Registrace zařízení Apple. Další informace najdete v tématu [Automatická registrace zařízení s iOS pomocí program registrace zařízení společnosti Apple](../enrollment/device-enrollment-program-enroll-ios.md).
- Vytvoření omezení registrace. Další informace najdete v tématu [Nastavení omezení registrace](../enrollment/enrollment-restrictions-set.md).

#### <a name="handling-pre-configuration-of-corporate-device-identifiers-for-android-q-devices---4711509--idmiss---"></a>Zpracování předběžné konfigurace identifikátorů podnikových zařízení pro zařízení s Androidem Q<!-- 4711509  idmiss -->
V Androidu Q (v10 za účelem) bude Google odebrat možnost agentů MDM na starších zařízeních s Androidem spravovaná (Správce zařízení), aby shromáždila informace o identifikátoru zařízení.  Intune obsahuje funkci, která správcům IT umožňuje [předem nakonfigurovat seznam sériových čísel zařízení nebo IMEI](../enrollment/corporate-identifiers-add.md#identify-corporate-owned-devices-with-imei-or-serial-number) , aby tato zařízení mohla automaticky označovat jako vlastněná společností. Tato funkce nebude fungovat pro zařízení s Androidem Q, která jsou spravovaná správcem zařízení.  Bez ohledu na to, jestli se sériové číslo nebo IMEI zařízení nahraje, se při registraci v Intune vždycky považuje za osobní.  Po registraci můžete vlastnictví ručně přepínat na podnik.  To má vliv pouze na nové registrace a stávající zaregistrovaná zařízení ovlivněna nebudou.  Tato změna nemá vliv na zařízení s Androidem spravovaná pomocí pracovních profilů a bude dál fungovat, jak ještě dnes.  Zařízení se systémem Android Q zaregistrovaná jako správce zařízení už navíc nebudou moct v konzole Intune hlásit sériové číslo nebo IMEI jako vlastnosti zařízení.

#### <a name="icons-have-changed-for-android-enterprise-enrollments-work-profile-dedicated-devices-and-fully-managed-devices---4977730---"></a>Změnily se ikony pro registrace Android Enterprise (pracovní profil, vyhrazená zařízení a plně spravovaná zařízení).<!-- 4977730 -->
Změnili jsme ikony profilů registrace pro Android Enterprise. Pokud chcete zobrazit nové ikony, přejděte na **Intune** > **registrace** > **registraci v Androidu** > v části **profily zápisu**.


#### <a name="windows-diagnostic-data-collection-change---4113859---"></a>Změna shromažďování diagnostických dat Windows<!-- 4113859 -->
Výchozí hodnota pro shromažďování diagnostických dat se změnila pro zařízení s Windows 10 verze 1903 a novější. Počínaje systémem Windows 10 1903 je shromažďování diagnostických dat ve výchozím nastavení povoleno. Diagnostická data systému Windows jsou důležitá technická data ze zařízení s Windows poskytující informace o příslušném zařízení a o tom, jak funguje systém Windows a související software. Další informace najdete v tématu [Konfigurace diagnostických dat Windows ve vaší organizaci](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization). V případě, že se v profilu autopilotu pomocí [System/AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)nenastavuje jinak, zařízení autopilotu se také přihlásí do "plné" telemetrie.

### <a name="device-management"></a>Správa zařízení

#### <a name="improve-device-location---3855417----"></a>Vylepšit umístění zařízení<!-- 3855417  -->
Pomocí akce **Najít zařízení** můžete přiblížit přesnou souřadnici zařízení. Další informace o vyhledání ztracených zařízení s iOS najdete v tématu [vyhledání ztracených zařízení s iOS](../remote-actions/device-locate.md).

### <a name="device-security"></a>Zabezpečení zařízení

#### <a name="advanced-settings-for-windows-defender-firewall--public-preview----1311949-------"></a>Rozšířená nastavení pro firewall v programu Windows Defender (Public Preview)<!--  1311949     -->  
Pomocí Intune můžete spravovat [vlastní pravidla brány firewall jako součást profilu konfigurace zařízení](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) pro službu Endpoint Protection ve Windows 10. Pravidla mohou určovat příchozí a odchozí chování aplikací, síťových adres a portů. 

#### <a name="updated-ui-for-managing-security-baselines---4091125-------"></a>Aktualizované uživatelské rozhraní pro správu standardních hodnot zabezpečení<!-- 4091125     -->
Aktualizovali jsme [prostředí pro vytváření a úpravy](../protect/security-baselines.md#create-the-profile) v konzole Intune pro naše základní směry zabezpečení. Změny zahrnují:

Jednodušší formát ve stylu průvodce, který je zúžený na jedno okno. v jednom okně. Tento nový návrh se zapíná s oknem neustálému zvětšování, který vyžaduje, aby odborníci na IT přešli do několika samostatných podoken.  
Nyní můžete vytvářet přiřazení v rámci prostředí vytváření a úprav, aniž byste se museli vracet později, aby bylo možné přiřadit směrné plány. Přidali jsme souhrn nastavení, která můžete zobrazit před vytvořením nového směrného plánu a úpravou stávajícího. Při úpravách zobrazuje souhrn pouze seznam položek, které jsou nastaveny v rámci jedné kategorie upravovaných vlastností.

<!-- ########################## -->

## <a name="week-of-july-15-2019"></a>Týden od 15. července 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="managed-home-screen-and-managed-settings-icons---4918107---"></a>Ikony spravované domovské obrazovky a spravovaného nastavení<!-- 4918107 -->
Ikona spravované aplikace na domovské obrazovce a ikona **spravovaného nastavení** se aktualizovaly. Spravovaná aplikace pro domovskou obrazovku se používá jenom u zařízení zaregistrovaných v Intune jako vyhrazená zařízení s Androidem Enterprise (AE) a provozovaná v celoobrazovkovém režimu s více aplikacemi. Další informace o spravované aplikaci pro domovskou obrazovku najdete v tématu [Konfigurace aplikace pro domovskou obrazovku spravované Microsoftem pro Android Enterprise](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="android-device-policy-on-android-enterprise-dedicated-devices---4918136---"></a>Zásady zařízení s Androidem na vyhrazených zařízeních s Androidem Enterprise<!-- 4918136 -->
Přístup k aplikaci zásad zařízení s Androidem můžete získat z obrazovky ladění aplikace pro správu domácí obrazovky. Spravovaná aplikace pro domovskou obrazovku se používá jenom u zařízení zaregistrovaných v Intune jako vyhrazená zařízení s Androidem Enterprise (AE) a provozovaná v celoobrazovkovém režimu s více aplikacemi. Další informace najdete v tématu [Konfigurace aplikace pro domovskou obrazovku spravované Microsoftem pro Android Enterprise](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="ios-company-portal-updates---3902931---"></a>aktualizace pro iOS Portál společnosti<!-- 3902931 -->
Název vaší společnosti při výzvě ke správě aplikací pro iOS nahradí aktuální text "i.manage.microsoft.com". V případě, že se uživatel pokusí nainstalovat aplikaci pro iOS z Portál společnosti nebo když uživatelé povolí správu aplikace, uvidí například název společnosti namísto "i.manage.microsoft.com". Tato akce bude zahrnuta pro všechny zákazníky za několik následujících dní.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="manage-filevault-for-macos----3858502--4557986--1210104----"></a>Správa trezoru pro macOS<!--  3858502 + 4557986 + 1210104  -->
Pomocí Intune můžete [Spravovat šifrování klíčů trezoru úložiště pro zařízení MacOS](../protect/encrypt-devices.md). K šifrování zařízení použijte konfigurační profil zařízení Endpoint Protection.

Naše podpora pro trezor souborů obsahuje šifrování nešifrovaných zařízení, v úschově zařízení pro osobní obnovení, automatické nebo ruční střídání osobních šifrovacích klíčů a načtení klíčů pro podniková zařízení. Koncoví uživatelé můžou k získání osobního obnovovacího klíče pro svá zašifrovaná zařízení použít taky web Portál společnosti.

Také jsme rozšířili sestavu šifrování tak, aby obsahovala informace o souběžných informacích [o trezoru úložiště](../protect/encryption-monitor.md) pro BitLocker, takže můžete zobrazit všechny podrobnosti o šifrování zařízení na jednom místě.

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="windows-autopilot-reset-removes-the-devices-primary-user---4156123---"></a>Resetování Windows autopilotu odebere primárního uživatele zařízení.<!-- 4156123 -->
Když se na zařízení používá resetování autopilotního projektu, primární uživatel zařízení se odebere. Další uživatel, který se přihlásí po obnovení, se nastaví jako primární uživatel. Tato funkce bude zahrnuta pro všechny zákazníky za několik následujících dní.

## <a name="week-of-july-8-2019"></a>Týden od 8. července 2019

### <a name="new-office-windows-and-onedrive-settings-in-windows-10-administrative-templates----3510695---"></a>Nové nastavení Office, Windows a OneDrivu v šablonách pro správu Windows 10 <!-- 3510695 -->

V Intune můžete vytvořit šablony pro správu, které napodobují místní správu zásad skupiny ( > **profily** pro**správu zařízení** > **vytvořit profil** > **Windows 10 a novější** pro **šablonu** pro typ profilu >).

Tato aktualizace zahrnuje další nastavení Office, Windows a OneDrivu, která můžete přidat do šablon. S těmito novými nastaveními teď můžete nakonfigurovat více než 2500 nastavení, která jsou na bázi 100% cloudu.

Další informace o této funkci najdete v tématu [použití šablon Windows 10 ke konfiguraci nastavení zásad skupiny v Intune](../configuration/administrative-templates-windows.md).

Platí pro: Windows 10 a novější

## <a name="week-of-july-1-2019"></a>Týden od 1. července 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="aad-and-app-on-android-enterprise-devices---3574267---"></a>AAD a aplikace na zařízeních s Androidem Enterprise<!-- 3574267 -->
Při připojování plně spravovaných zařízení s Androidem Enterprise se uživatelé teď při počátečním nastavení nového zařízení nebo obnovení továrního nastavení registrují s Azure Active Directory (AAD). Předtím, než se pro plně spravované zařízení dokončí, musí uživatel ručně spustit aplikaci Microsoft Intune a spustit registraci AAD. Když se teď uživatel při počátečním nastavení zaregistruje na domovské stránce zařízení, zařízení se zaregistruje i zaregistruje.

Kromě aktualizací AAD se teď podporují zásady ochrany aplikací Intune (aplikace) na plně spravovaných podnikových zařízeních s Androidem. Tato funkce bude k dispozici, jakmile ji nasadíme. Další informace najdete v tématu [Přidání spravovaných Google Play aplikací do zařízení s Androidem Enterprise pomocí Intune](../apps/apps-add-android-for-work.md).

## <a name="week-of-june-24-2019-1906-service-release"></a>Týden od 24. června 2019 (vydání služby 1906)

### <a name="app-management"></a>Správa aplikací

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data---3145939---"></a>Nakonfigurovat, který prohlížeč smí propojit s daty organizace<!-- 3145939 -->
Zásady Intune App Protection (aplikace) na zařízeních s Androidem a iOS teď umožňují přenášet webové odkazy organizace na konkrétní prohlížeč mimo Intune Managed Browser nebo Microsoft Edge.  Další informace o aplikaci najdete v tématu [co jsou zásady ochrany aplikací?](../apps/app-protection-policy.md).

#### <a name="all-apps-page-identifies-onlineoffline-microsoft-store-for-business-apps--4089647---"></a>Stránka všechny aplikace identifikuje online nebo offline Microsoft Store pro obchodní aplikace.<!--4089647 -->
Stránka **všechny aplikace** teď obsahuje popis, který identifikuje aplikace Microsoft Store pro firmy (MSFB) jako online nebo offline aplikace. Každá aplikace MSFB teď obsahuje příponu pro **online** nebo **offline**. Stránka s podrobnostmi o aplikaci zahrnuje také **typ licence** a **podporuje instalaci kontextu zařízení** (pouze offline licencované aplikace).

#### <a name="company-portal-app-on-windows-shared-devices--4393553---"></a>Portál společnosti aplikace na sdílených zařízeních s Windows<!--4393553 -->
Uživatelé teď můžou k aplikaci Portál společnosti přistupovat na sdílených zařízeních se systémem Windows. Koncovým uživatelům se na dlaždici zařízení zobrazí **sdílený** popisek. To platí pro Windows Portál společnosti app verze 10.3.45609.0 a novější.

#### <a name="view-all-installed-apps-from-new-company-portal-web-page---4224326---"></a>Zobrazit všechny nainstalované aplikace z nové Portál společnosti webové stránky<!-- 4224326 -->
Stránka Portál společnosti nové **nainstalované aplikace** na webu obsahuje seznam všech spravovaných aplikací (požadovaných i dostupných), které jsou nainstalovány na zařízeních uživatele. Kromě typu přiřazení uživatelé uvidí vydavatele aplikace, datum publikování a aktuální stav instalace. Pokud jste neudělali žádné aplikace, které uživatelé potřebují nebo nejsou k dispozici, zobrazí se zpráva s vysvětlením, že nebyly nainstalovány žádné aplikace společnosti. Pokud chcete zobrazit novou stránku na webu, přejděte na [web portál společnosti](https://portal.manage.microsoft.com) a klikněte na **nainstalované aplikace**.  

#### <a name="new-view-lets-app-users-see-all-managed-apps-installed-on-device---2352913---"></a>Nové zobrazení umožňuje uživatelům aplikace zobrazit všechny spravované aplikace nainstalované na zařízení.<!-- 2352913 -->  
Aplikace Portál společnosti pro Windows teď obsahuje seznam všech spravovaných aplikací (požadovaných i dostupných), které jsou nainstalované na zařízení uživatele. Uživatelé můžou také zobrazit pokusy o instalaci aplikací a jejich aktuální stavy. Pokud jste neudělali aplikace, které uživatelé potřebují nebo k nim nejsou k dispozici, zobrazí se zpráva s vysvětlením, že nebyly nainstalovány žádné aplikace společnosti. Chcete-li zobrazit nové zobrazení, přejděte do navigačního podokna Portál společnosti a vyberte **aplikace** > **nainstalované aplikace**.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices---2043024---"></a>Konfigurace nastavení pro rozšíření jádra na zařízeních macOS<!-- 2043024 -->
Na zařízeních macOS můžete vytvořit konfigurační profil zařízení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > zvolit **MacOS** pro platformu). Tato aktualizace zahrnuje novou skupinu nastavení, která vám umožní nakonfigurovat a používat na svých zařízeních rozšíření jádra. Můžete přidat konkrétní rozšíření nebo povolíte všechna rozšíření od konkrétního partnera nebo vývojáře.

Další informace o této funkci najdete v tématu [Přehled rozšíření jádra](../configuration/kernel-extensions-overview-macos.md) a [nastavení rozšíření jádra](../configuration/kernel-extensions-settings-macos.md).

Platí pro: macOS 10.13.2 a novější

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options---2697002---"></a>Aplikace z nastavení jenom pro Store pro zařízení s Windows 10 obsahují další možnosti konfigurace.<!-- 2697002 -->
Když vytváříte profil omezení zařízení pro zařízení s Windows, můžete použít **aplikace z nastavení jenom úložiště** , aby uživatelé mohli instalovat jenom aplikace z Windows App Storu (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** pro > **omezení zařízení** pro typ profilu). V této aktualizaci je toto nastavení rozšířeno na podporu více možností.

Nové nastavení zobrazíte tak, že přejdete na [nastavení zařízení s Windows 10 (a novější) a povolíte nebo zakážete funkce](../configuration/device-restrictions-windows-10.md#app-store).

Platí pro: Windows 10 a novější

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group---4089955---"></a>Nasazení více profilů zařízení rozšíření Zebra mobility na zařízení, stejnou skupinu uživatelů nebo stejnou skupinu zařízení<!-- 4089955 -->
V Intune můžete použít rozšíření Zebra mobility (MX) v profilu konfigurace zařízení k přizpůsobení nastavení pro Zebra zařízení, která nejsou integrovaná do Intune. V současné době můžete nasadit jeden profil na jedno zařízení. V této aktualizaci můžete nasadit několik profilů do:
- Stejná skupina uživatelů
- Stejná skupina zařízení
- Jedno zařízení

[Používání a Správa zařízení Zebra pomocí rozšíření Zebra mobility v Microsoft Intune](../configuration/android-zebra-mx-overview.md) ukazuje, jak používat MX v Intune.

Platí pro: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow---4404075----"></a>Některá nastavení veřejného terminálu na zařízeních s iOS se nastavují pomocí Block, kde se nahrazuje "povolení".<!-- 4404075  -->
Když vytvoříte profil omezení zařízení na zařízeních s iOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro > **omezení zařízení** pro typ profilu > veřejný **terminál**), nastavíte **automaticky zámek**, **přepínač vyzvánění**, **otočení obrazovky**, **tlačítko režimu spánku obrazovky**a **tlačítka hlasitosti**.

V této aktualizaci jsou hodnoty **zablokované** (blokuje funkci) a **nejsou nakonfigurované** (umožňuje funkci). Nastavení zobrazíte tak, že přejdete na [nastavení zařízení s iOS a povolíte nebo zakážete funkce](../configuration/device-restrictions-ios.md#kiosk).

Platí pro: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices---4490704---"></a>Použití ID obličeje pro ověřování hesla na zařízeních s iOS<!-- 4490704 -->
Když vytvoříte profil omezení zařízení pro zařízení s iOS, můžete pro heslo použít otisk prstu. V této aktualizaci nastavení hesla otisku prstu taky povoluje rozpoznávání obličeje (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro > **omezení zařízení** pro typ profilu > **heslo**). V důsledku toho se změnila následující nastavení:

- **Odemčení otiskem prstu** je teď **dotykové ID a odemknutí ID obličeje**.
- **Úprava otisku prstu (jenom pod dohledem)** je teď **dotykové ID a úprava ID obličeje (jenom pod dohledem)** .

ID obličeje je dostupné v iOS 11,0 a novějších verzích. Nastavení zobrazíte tak, že přejdete na [nastavení zařízení s iOS a povolíte nebo zakážete funkce využívající Intune](../configuration/device-restrictions-ios.md#password).

Platí pro: iOS

#### <a name="restricting-gaming-and-app-store-features-on-ios-devices-is-now-dependent-on-ratings-region---4593948---"></a>Omezení her a funkcí pro obchod s aplikacemi na zařízeních s iOS je teď závislé na oblasti hodnocení.<!-- 4593948 -->
Na zařízeních se systémem iOS můžete povolit nebo zakázat funkce týkající se her, App Storu a zobrazení dokumentů (**Konfigurace zařízení** > **profily** > **vytvoření profilu** > **iOS** pro > **omezení zařízení** pro typ profilu > **App Store, zobrazování dokumentů, hry**). Můžete také zvolit oblast hodnocení, například USA.

V této aktualizaci se funkce **aplikace** přesune, aby byla podřízená **oblasti hodnocení**a byla závislá na **oblasti hodnocení**. Nastavení zobrazíte tak, že přejdete na [nastavení zařízení s iOS a povolíte nebo zakážete funkce využívající Intune](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Platí pro: iOS

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="windows-autopilot-support-for-hybrid-azure-ad-join---4809146--"></a>Podpora Windows autopilotu pro hybridní službu Azure AD JOIN<!-- 4809146-->
Windows autopilot pro stávající zařízení teď podporuje hybridní připojení ke službě Azure AD (kromě stávající podpory Azure AD JOIN). Platí pro zařízení s Windows 10 verze 1809 a novější. Další informace najdete v tématu věnovaném [autopilotu Windows pro existující zařízení](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices).

### <a name="device-management"></a>Správa zařízení

#### <a name="see-the-security-patch-level-for-android-devices---4461911---"></a>Zobrazit úroveň opravy zabezpečení pro zařízení s Androidem<!-- 4461911 -->
Teď můžete zobrazit úroveň opravy zabezpečení pro zařízení s Androidem. Pokud to chcete udělat, vyberte **zařízení** > **Intune** > **všechna zařízení** > vyberte **hardware**> zařízení.
Úroveň opravy je uvedena v části **operační systém** .

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group---3173810---"></a>Přiřadit značky oboru všem spravovaným zařízením ve skupině zabezpečení<!-- 3173810 -->
Nyní můžete přiřadit značky oboru ke skupině zabezpečení a všechna zařízení ve skupině zabezpečení budou také přidružena k těmto značkám oboru. Všechna zařízení v těchto skupinách budou mít také přiřazenou značku oboru. Tagy oboru nastavené touto funkcí přepíší sadu značek oboru s aktuálním tokem značek oboru zařízení. Další informace najdete v tématu [použití značek RBAC a Scope pro distribuci](scope-tags.md).

### <a name="device-security"></a>Zabezpečení zařízení

#### <a name="use-keyword-search-with-security-baselines------"></a>Použití hledání klíčových slov pomocí standardních hodnot zabezpečení<!--  -->
Když vytváříte nebo upravujete [profily standardních hodnot zabezpečení](../protect/security-baselines.md#create-the-profile), můžete zadat klíčová slova na novém panelu *hledání* a vyfiltrovat dostupné skupiny nastavení na ty, které obsahují vaše kritéria hledání.

#### <a name="the-security-baselines-feature-is-now-generally-available---3785395---"></a>Funkce standardních hodnot zabezpečení je teď všeobecně dostupná.<!-- 3785395 -->
Funkce **standardních hodnot zabezpečení** není ve verzi Preview a je teď obecně dostupná (GA).  To znamená, že funkce je připravena k použití v produkčním prostředí. Jednotlivé základní šablony ale mohou zůstat ve verzi Preview a jsou vyhodnoceny a vydány pro GA na základě vlastních plánů.

#### <a name="the-mdm-security-baseline-template-is-now-generally-available---3794072-4217151--3534649---"></a>Šablona standardních hodnot zabezpečení MDM je teď všeobecně dostupná.<!-- 3794072, 4217151,  3534649 -->
Šablona základní hodnoty zabezpečení MDM se přesunula z verze Preview a teď je všeobecně dostupná (GA). Šablona GA je **pro květen 2019**označena jako základní hodnota zabezpečení MDM.  Jedná se o novou šablonu, která není upgradem z verze Preview.  Jako novou šablonu budete muset zkontrolovat nastavení, která [obsahuje](../protect/security-baseline-settings-mdm.md), a pak vytvořit nové profily, pomocí kterých šablonu nasadíte do svého zařízení. Další šablony standardních hodnot zabezpečení mohou zůstat ve verzi Preview. Seznam dostupných směrných plánů najdete v tématu [dostupné standardní hodnoty zabezpečení](../protect/security-baselines.md#available-security-baselines).  

Kromě nové šablony obsahuje *základní plán zabezpečení MDM pro květen 2019* dvě nastavení, která jsme nedávno oznámili v našem vývojovém článku:  
- Nad zámkem: hlas – aktivovat aplikace z uzamčené obrazovky  
- DeviceGuard: při příštím restartování zařízení použijte zabezpečení na základě virtualizace (VBS).  

*Základní hodnota zabezpečení MDM pro květen 2019* obsahuje také přidání několika nových nastavení, odebrání ostatních a revizi výchozí hodnoty jednoho nastavení. Podrobný seznam změn z verze Preview na GA najdete v tématu **co se změnilo v nové šabloně**.

#### <a name="security-baseline-versioning---3194322---"></a>Základní verze zabezpečení<!-- 3194322 -->
Standardní hodnoty zabezpečení pro Intune podporují správu verzí. V rámci této podpory platí, že při vydání nových verzí jednotlivých standardních hodnot zabezpečení můžete aktualizovat stávající základní profily zabezpečení tak, aby používaly novější základní verzi bez nutnosti opětovného vytvoření a nasazení nového směrného plánu od začátku. Kromě toho můžete v konzole Intune zobrazit informace o jednotlivých standardních hodnotách, jako je počet jednotlivých profilů, u kterých používáte základní hodnoty, kolik z různých základních verzí vaše profily používá a kdy nejnovější vydání konkrétního zabezpečení. směrný plán byl.  Další informace najdete v tématu **základní hodnoty zabezpečení**.

#### <a name="the-use-security-keys-for-sign-in-setting-has-moved---4501151---"></a>Bylo přesunuto nastavení použít klíče zabezpečení pro přihlášení.<!-- 4501151 -->
Nastavení konfigurace zařízení pro ochranu identity s názvem **použít klíče zabezpečení pro přihlášení** se už nenašlo jako dílčí nastavení *Konfigurace Windows Hello pro firmy*. Teď je to nastavení nejvyšší úrovně, které je vždycky dostupné, a to i v případě, že nepovolíte používání Windows Hello pro firmy. Další informace najdete v tématu [Identita Protection](../protect/identity-protection-windows-settings.md).

### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="new-permissions-for-assigned-group-admins---4504437-----"></a>Nová oprávnění pro přiřazené správce skupiny<!-- 4504437   -->
Integrovaná role školního správce Intune teď má oprávnění k vytváření, čtení, aktualizaci a odstraňování (CRUD) pro spravované aplikace. Tato aktualizace znamená, že pokud jste přihlášeni jako správce skupiny v Intune for Education, můžete teď vytvářet, zobrazovat, aktualizovat a odstraňovat MDM Push Certificate iOS, tokeny MDM serveru iOS a tokeny VPP pro iOS společně se [všemi stávajícími oprávněními](https://docs.microsoft.com/intune-education/group-admin-delegate#group-admin-permissions), která máte. Pokud chcete některou z těchto akcí provést, přečtěte si **Nastavení tenanta** > **správu zařízení s iOS**.  

#### <a name="applications-can-use-the-graph-api-to-call-read-operations-without-user-credentials---4655885---"></a>Aplikace můžou použít Graph API k volání operací čtení bez přihlašovacích údajů uživatele.<!-- 4655885 -->
Aplikace můžou volat Intune Graph API operace čtení pomocí identity aplikace bez přihlašovacích údajů uživatele. Další informace o přístupu k rozhraní Microsoft Graph API pro Intune najdete [v tématu práce s Intune v Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="apply-scope-tags-to-microsoft-store-for-business-apps---4392555---"></a>Použití značek oboru na Microsoft Store pro obchodní aplikace<!-- 4392555 -->
Pro Microsoft Store pro obchodní aplikace teď můžete použít značky oboru. Další informace o značkách oboru najdete v tématu [použití řízení přístupu na základě role (RBAC) a značek oboru pro distribuci](scope-tags.md).

## <a name="week-of-june-17-2019"></a>Týden od 17. června 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="new-features-in-microsoft-intune-app"></a>Nové funkce v aplikaci Microsoft Intune App
Přidali jsme nové funkce do aplikace Microsoft Intune (Preview) pro Android. Uživatelé na plně spravovaných zařízeních s Androidem teď můžou:  

* Umožňuje zobrazit a spravovat zařízení, která zaregistrovali prostřednictvím aplikace Portál společnosti Intune nebo Microsoft Intune.
* Pro podporu se obraťte na svou organizaci.
* Poslat svůj názor Microsoftu.
* Zobrazit podmínky a ujednání, pokud je nastavila jejich organizace.

## <a name="week-of-june-10-2019"></a>Týden od 10. června 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github---2653471---"></a>Nové ukázkové aplikace ukazující integraci sady Intune SDK dostupnou na GitHubu<!-- 2653471 -->
Účet GitHub msintuneappsdk přidal nové ukázkové aplikace pro iOS (SWIFT), Android, Xamarin. iOS, Xamarin Forms a Xamarin. Android. Tyto aplikace jsou určeny k doplnění naší stávající dokumentace a poskytnutí ukázek, jak integrovat sadu Intune APP SDK do vašich vlastních mobilních aplikací. Pokud jste vývojář aplikací, který potřebuje další pokyny pro sadu Intune SDK, přečtěte si následující propojené ukázky:
- [Chat](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App) – nativní aplikace pro zasílání rychlých zpráv pro iOS (SWIFT), která pro zprostředkované ověřování používá službu Azure Active Directory Authentication Library (ADAL).
- [Tasker](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App) – nativní aplikace seznamu úkolů pro Android, která používá ADAL pro zprostředkované ověřování.
- [Tasker](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps) – aplikace seznamu úkolů Xamarin. Android, která používá ADAL pro zprostředkované ověřování, toto úložiště má také aplikaci Xamarin. Forms.
- [Ukázková aplikace Xamarin. iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) – ukázková aplikace Barebones Xamarin. iOS

## <a name="week-of-may-27-2019"></a>Týden od 27. května 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices---4223162---"></a>Vytváření sestav pro potenciálně škodlivé aplikace na zařízeních s Androidem<!-- 4223162 -->
Intune teď poskytuje další informace o potenciálně škodlivých aplikacích na zařízeních s Androidem. 

## <a name="week-of-may-20-2019"></a>Týden od 20. května 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="windows-company-portal-app---3316993---"></a>Aplikace Portál společnosti pro Windows<!-- 3316993 -->
Aplikace pro Windows Portál společnosti teď bude mít novou stránku označenou jako **zařízení**. Na stránce **zařízení** se zobrazí koncoví uživatelé všechna zaregistrovaná zařízení. Uživatelům se tato změna v Portál společnosti uvidí, když používají verzi 10.3.4291.0 a novější. Informace o konfiguraci Portál společnosti naleznete v tématu [How to Configure a Microsoft Intune portál společnosti App](../apps/company-portal-app.md).

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>Název atributu KódObjednávky zařízení pro Autopilot se změnil na značku Group <!-- 4659453 -->

Aby byl název atributu **KódObjednávky** v zařízeních pro autopiloti intuitivnější, byl změněn na **značku Group**. Při použití CSV k nahrávání informací o zařízeních autopilotu je nutné použít značku skupiny jako záhlaví sloupce, nikoli ČísloObjednávky.  

## <a name="week-of-may-13-2019-1905-service-release"></a>Týden od 13. května 2019 (1905 Service Release)

### <a name="app-management"></a>Správa aplikací

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation---1927359----"></a>Zásady služby Intune aktualizují metodu ověřování a instalaci aplikace Portál společnosti.<!-- 1927359  -->
V zařízeních, která jsou už zaregistrovaná prostřednictvím pomocníka s nastavením prostřednictvím některého z metod registrace podnikových zařízení společnosti Apple, Intune už nebude podporovat Portál společnosti, když je ručně nainstalují koncoví uživatelé z App Storu. Tato změna platí pouze v Apple Pomocníka s nastavením ověřování během registrace. Tato změna ovlivní také pouze zařízení s Iosem zaregistrovaná prostřednictvím:  
* Apple configurator

* Obchodní ředitel společnosti Apple

* Apple School Manager

* Program registrace zařízení Apple (DEP)

Pokud je uživatelé nainstalovat aplikaci portál společnosti z App storu a potom se pokuste registraci těchto zařízení jeho prostřednictvím, dojde k chybě. U těchto zařízení se očekává, že bude používat jenom Portál společnosti, když ho služba Intune po registraci automaticky dokončí. Profily registrace v Intune na portálu Azure portal bude aktualizován, takže můžete určit, jak ověřovat zařízení a pokud se zobrazí v aplikaci portál společnosti. Pokud chcete, aby uživatelé zařízení DEP budou používat aplikaci portál společnosti, musíte zadat předvolby v registrační profil. 

Kromě toho se odebírá obrazovka **identifikace zařízení** v iOS portál společnosti. Proto správci, kteří chtějí povolit podmíněný přístup nebo nasazovat firemní aplikace, musí aktualizovat profil zápisu DEP. Tento požadavek platí jenom v případě, že se registrace DEP ověřuje pomocí Pomocníka s nastavením. V takovém případě musíte Portál společnosti do zařízení vložit. Provedete to tak, že v **Intune** > **registraci zařízení** > zápisu **Apple** > **tokeny programu registrace** > **zvolíte profily > profilů** > vyberte profil > **vlastnosti** > nastavte **instalovat portál společnosti** na **Ano**.

Pokud chcete Portál společnosti nainstalovat do již zaregistrovaných zařízení DEP, budete muset přejít na > klientských aplikací Intune a vložit ho jako spravovanou aplikaci se zásadami konfigurace aplikace. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy---3568384---"></a>Konfigurace způsobu, jakým koncoví uživatelé aktualizují obchodní aplikaci (LOB) pomocí zásad ochrany aplikací<!-- 3568384 -->
Teď můžete nakonfigurovat, kde můžou koncoví uživatelé získat aktualizovanou verzi obchodní aplikace (LOB). Koncovým uživatelům se tato funkce zobrazí v dialogovém okně pro podmíněné spuštění podmíněné **verze aplikace** , ve kterém se koncovým uživatelům zobrazí výzva k aktualizaci na minimální verzi aplikace LOB. Tyto podrobnosti o aktualizaci musíte zadat v rámci zásad ochrany aplikací LOB (aplikace). Tato funkce je dostupná v iOS a Androidu. V systému iOS Tato funkce vyžaduje, aby byla aplikace integrovaná (nebo zabalená pomocí nástroje pro zabalení) se sadou Intune SDK pro iOS v. 10.0.7 nebo vyšší. V Androidu by tato funkce vyžadovala nejnovější Portál společnosti. Pokud chcete nakonfigurovat, jak koncový uživatel aktualizuje obchodní aplikaci, potřebuje, aby se do této aplikace poslala zásada konfigurace spravované aplikace s klíčem, `com.microsoft.intune.myappstore`. Hodnota odeslané bude určovat, ze kterého Storu bude koncový uživatel aplikaci stahovat. Pokud je aplikace nasazená prostřednictvím Portál společnosti, musí být hodnota `CompanyPortal`. Pro jakékoli jiné úložiště musíte zadat úplnou adresu URL.

#### <a name="intune-management-extension-powershell-scripts---3734186----"></a>Skripty PowerShellu pro rozšíření správy Intune<!-- 3734186  -->
Skripty PowerShellu můžete nakonfigurovat tak, aby se spouštěly s oprávněními správce uživatele v zařízení. Další informace najdete v tématu [použití skriptů PowerShellu na zařízeních s Windows 10 v Intune a ve](../apps/intune-management-extension.md) [správě aplikací Win32](../apps/app-management.md).

#### <a name="android-enterprise-app-management---4459905---"></a>Správa firemních aplikací pro Android<!-- 4459905 -->
Aby správci IT usnadnili konfiguraci a používání správy Android Enterprise managementu, Intune do konzoly pro správu Intune automaticky přidá čtyři běžné aplikace pro Android Enterprise. Čtyři aplikace pro Android Enterprise jsou tyto aplikace:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** – používá se pro plně spravované scénáře pro Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** – vám pomůže se přihlašovat k vašim účtům, pokud použijete dvojúrovňové ověřování.
- **[Portál společnosti Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** – používá se pro scénáře zásad ochrany aplikací (App) a Android Enterprise Work Profile.
- [Spravovaná Domovská obrazovka](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) – používá se pro scénáře podnikových scénářů nebo veřejného terminálu pro Android.

Dříve museli správci IT v rámci instalace ručně najít a schválit tyto aplikace v rámci [spravovaného Google Play Storu](https://play.google.com/store/apps) . Tato změna odstraní výše popsané kroky, aby zákazníci usnadnili používání Enterprise managementu v Androidu, aby je bylo snazší a rychlejší.

Správci uvidí tyto čtyři aplikace automaticky přidané do jejich seznamu aplikací Intune v době, kdy poprvé připojí svého tenanta Intune ke spravovaným Google Play. Další informace najdete v tématu [připojení účtu Intune ke spravovanému účtu Google Play](../enrollment/connect-intune-android-enterprise.md). Pro klienty, kteří už připojili svého tenanta nebo kteří už používají Android Enterprise, nemusíte dělat žádné správce. Tyto čtyři aplikace se automaticky zobrazí do 7 dnů od dokončení zavedení služby květen 2019.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---1533038---"></a>Aktualizovaný konektor certifikátu PFX pro Microsoft Intune<!-- 1533038 -->
Vydali jsme aktualizaci [konektoru PFX Certificate Connector pro Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors) , která řeší problém, kdy se stávající certifikáty PFX budou dál zpracovávat, což způsobí, že konektor přestane zpracovávat nové požadavky.

#### <a name="intune-security-tasks-for-defender-atp-in-public-preview---3208597---"></a>Úkoly zabezpečení Intune pro program Defender ATP (ve verzi Public Preview)<!-- 3208597 -->
Ve verzi Public Preview můžete pomocí Intune spravovat [úlohy zabezpečení pro Microsoft Defender Advanced Threat Protection (ATP)](../protect/atp-manage-vulnerabilities.md). Tato integrace s ATP a přináší přístup založený na riziku pro zjišťování, stanovení priorit a nápravu chyb zabezpečení koncových bodů a chybných konfigurací a zároveň zkracuje dobu mezi zjišťováním a omezením jejich zmírnění.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy---3617671-----"></a>Zjištění sady čipů TPM v zásadách dodržování předpisů pro zařízení s Windows 10<!-- 3617671   -->
Mnoho zařízení s Windows 10 a novějším má čipové sady TPM (Trusted Platform Module). Tato aktualizace obsahuje nové nastavení dodržování předpisů, které kontroluje verzi čipu TPM v zařízení.

Toto nastavení popisuje [nastavení zásad dodržování předpisů pro Windows 10 a novější](../protect/compliance-policy-create-windows.md#device-security) .

Platí pro: Windows 10 a novější

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices---4097904-----"></a>Zabránit koncovým uživatelům v úpravách jejich osobního HotSpotu a zakázat přihlašování Siri serveru na zařízeních s iOS<!-- 4097904   -->  
Vytvoříte profil omezení zařízení na zařízení s iOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro **zařízení > omezení** pro typ profilu). Tato aktualizace obsahuje nová nastavení, která můžete nakonfigurovat:

- **Integrované aplikace**: protokolování na straně serveru pro příkazy Siri
- **Bezdrátové**: Změna uživatele osobní hotspotu (jenom pod dohledem)

Tato nastavení zobrazíte tak, že přejdete na [integrovaná nastavení aplikace pro iOS](../configuration/device-restrictions-ios.md#built-in-apps) a [nastavení bezdrátové sítě pro iOS](../configuration/device-restrictions-ios.md#wireless).

Platí pro: iOS 12,2 a novější

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices---4097905-----"></a>Nová nastavení omezení pro zařízení macOS v aplikaci učeben<!-- 4097905   --> 
Pro zařízení macOS můžete vytvořit profily konfigurace zařízení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **MacOS** pro **omezení** platformy > pro typ profilu). Tato aktualizace zahrnuje nová nastavení aplikace učebny, možnost blokovat snímky obrazovky a možnost zakázat knihovnu fotografií iCloud.

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení MacOS a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-macos.md).

Platí pro: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>Heslo pro iOS pro přístup k nastavení obchodu s aplikacemi se přejmenuje.<!-- 4557891  -->
**Heslo pro přístup k nastavení obchodu s aplikacemi** je přejmenované na **vyžadovat heslo pro úložiště iTunes pro všechny nákupy** (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro > **omezení zařízení** pro typ profilu > **App Store, zobrazování dokumentů a hry**).

Dostupná nastavení zobrazíte tak, že přejdete do [App Storu, zobrazení dokumentů a herního nastavení iOS](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Platí pro: iOS

#### <a name="microsoft-defender-advanced-threat-protection--baseline--preview----3754134---"></a>Směrný plán Microsoft Defender Advanced Threat Protection (Preview)<!--  3754134 -->
Přidali jsme náhled základní úrovně zabezpečení pro nastavení [rozšířené ochrany před internetovými útoky v programu Microsoft Defender](../protect/security-baseline-settings-defender-atp.md) . Tato standardní hodnota je dostupná, když vaše prostředí splňuje požadavky na používání [rozšířené ochrany před internetovými útoky v programu Microsoft Defender](../protect/advanced-threat-protection.md#prerequisites).

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available---3605348---"></a>Stránka stavu registrace systému Windows (ESP) je nyní obecně dostupná.<!-- 3605348 -->
Stránka stavu registrace je nyní mimo verzi Preview. Další informace najdete v tématu [nastavení stránky stavu registrace](../enrollment/windows-enrollment-status.md).


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation---4593669---"></a>Aktualizace uživatelského rozhraní Intune – vytvoření profilu registrace autopilotu<!-- 4593669 -->
Uživatelské rozhraní pro vytvoření profilu registrace autopilotu se aktualizovalo tak, aby bylo zarovnané na styly uživatelského rozhraní Azure. Další informace najdete v tématu [Vytvoření profilu registrace autopilotu](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile). Další scénáře Intune se budou aktualizovat na tento nový styl uživatelského rozhraní.

#### <a name="enable-autopilot-reset-for-all-windows-devices---4225665---"></a>Povolit resetování autopilotu pro všechna zařízení s Windows<!-- 4225665 -->
Automatické vynulování pilotního nasazení teď funguje pro všechna zařízení s Windows, i když nejsou nakonfigurovaná na použití stránky stavu registrace. Pokud se stránka stavu registrace pro zařízení nenakonfigurovala při počáteční registraci zařízení, bude po přihlášení zařízení po přihlášení přímo na plochu. Synchronizace a zobrazení kompatibility v Intune může trvat až osm hodin. Další informace najdete v tématu [resetování zařízení pomocí vzdálené správy Windows autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote).

#### <a name="exact-imei-format-not-required-when-searching-all-devices--30407680---"></a>Při hledání všech zařízení se nevyžaduje přesný formát IMEI.<!--30407680 -->
Při hledání **všech zařízení**nebudete muset vkládat mezery do čísel IMEI.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal--2489996---"></a>Odstranění zařízení na portálu Apple se projeví na portálu Intune.<!--2489996 -->
Pokud se zařízení odstraní z portálu od společnosti Apple Program registrace zařízení nebo z portálu Apple Business Manager, zařízení se během další synchronizace automaticky odstraní z Intune.

### <a name="the-enrollment-status-page-now-tracks-win32-apps---2714451---"></a>Stránka stavu registrace teď sleduje aplikace Win32.<!-- 2714451 -->
To platí jenom pro zařízení s Windows 10 verze 1903 a novější. Další informace najdete v tématu [nastavení stránky stavu registrace](../enrollment/windows-enrollment-status.md).

### <a name="device-management"></a>Správa zařízení

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api---3295288---"></a>Hromadné resetování a vymazání zařízení pomocí Graph API<!-- 3295288 -->
Při hromadném obnovení a vymazání zařízení 100 můžete použít Graph API.

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="the-encryption-report-is-out-of-public-preview---4587546--------"></a>Zpráva o šifrování není Public Preview.<!-- 4587546      -->
[Sestava pro šifrování nástrojem BitLocker a zařízení](../protect/encryption-monitor.md) je nyní všeobecně dostupná a již není součástí verze Public Preview.

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices---4050557---"></a>Podpis Outlooku a biometrické nastavení pro zařízení s iOS a Androidem<!-- 4050557 -->
Teď můžete určit, jestli je výchozí podpis povolený v Outlooku na zařízeních s iOS a Androidem. Kromě toho můžete zvolit, aby uživatelé mohli měnit nastavení biometriky v Outlooku v iOS.

## <a name="week-of-may-6-2019"></a>Týden od 6. května 2019

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices---4500808---"></a>Podpora NAC (Network Access Control) pro přístup F5 pro zařízení s iOS<!-- 4500808 -->

F5 vydala aktualizaci BIG-IP 13, která umožňuje funkci NAC pro přístup F5 v systému iOS v Intune. Chcete-li použít tuto funkci:

- Aktualizujte BIG-IP na 13.1.1.5 Refresh. BIG-IP 14 se nepodporuje.
- Integrujte BIG-IP s Intune for NAC. Postup v článku [Přehled: Konfigurace APM pro zařízení stav kontrol pomocí systémů správy koncových bodů](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html).
- Zaškrtněte nastavení **povolit Access Control sítě (NAC)** v profilu sítě VPN v Intune.

Dostupná nastavení zobrazíte tak, že přejdete na [Konfigurace nastavení sítě VPN na zařízeních s iOS](../configuration/vpn-settings-ios.md).

Platí pro: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---doc-vso-1521237----"></a>Aktualizovaný konektor certifikátu PFX pro Microsoft Intune<!-- doc-vso 1521237  -->  
Vydali jsme aktualizaci [konektoru certifikátů PFX pro Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors) , který předává interval dotazování od 5 minut do 30 sekund.




## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](../includes/intune-notices.md)]
