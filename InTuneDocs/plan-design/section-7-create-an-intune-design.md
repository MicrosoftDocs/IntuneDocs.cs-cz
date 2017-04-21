---
title: "Vytvoření návrhu Intune | Dokumentace Microsoftu"
description: "Tento článek vám pomůže vytvořit a implementovat návrh cloudového řešení Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: ce51e92f9643ddc77e84e6b4c65825d397a37ddc
ms.lasthandoff: 04/14/2017


---

# <a name="create-an-intune-design"></a>Vytvoření návrhu Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Tuto část průvodce doporučujeme použít zároveň s dalšími tématy ve 2. části. Tento návrh vychází z dosavadních shromážděných informací a z vašich rozhodnutí při dokončování předchozích částí tohoto průvodce. V této části návrhu se zaměříme jenom na Intune, což je cloudová služba Microsoftu.

Přestože jsou požadavky na místní infrastrukturu minimální, je třeba zpracovat plán návrhu, který bude zárukou správného řešení pro správu mobilních zařízení a bude odpovídat vašim cílům, úkolům a požadavkům.

V implementační a testovací fázi se návrh často mění. Nezapomeňte tyto změny průběžně dokumentovat, včetně úvah, které k nim vedly. Budeme mluvit o následujících oblastech:

-   Současné prostředí

-   Možnosti nasazení Intune

-   Požadavky na identitu u externích závislostí

-   Informace o platformě zařízení

-   Závazné požadavky  

Pojďme se na každou z těchto oblastí podívat podrobněji. 

## <a name="record-your-environment"></a>Záznam prostředí

První krok před vytvořením návrhu spočívá v zaznamenání současného prostředí. Současné prostředí ovlivňuje vaše rozhodování o návrhu. Proto když rozhodujete o návrhu Intune, měli byste svá rozhodnutí dokumentovat a vytvořit na ně odkazy. Tady je několik příkladů poznámek o současném prostředí:

-   **Identita v cloudu**

    -   Používáte DirSync nebo Azure Active Directory (AAD) Connect?

    -   Je vaše prostředí federované?

    -   Je zapnuté vícefaktorové ověřování?

-   **Prostředí e-mailu**

    -   Používáte místní nebo cloudový Exchange?

    -   Probíhá u vás projekt migrace Exchange do cloudu?

-   **Současné řešení pro správu mobilních zařízení (MDM)**

    -   Používáte v současnosti nějaká jiná řešení MDM?

    -   Jaká řešení MDM máte nasazená ve scénářích použití firemních zařízení a ve scénářích BYOD?

    -   Jaké používáte funkce (např. nastavení zařízení aplikace, konfigurace Wi-Fi atd.)?

    -   Jaké platformy zařízení jsou podporované?

    -   Jaké skupiny a kolik uživatelů používá řešení MDM?

-   **Řešení pro certifikáty**

    -   Implementovali jste řešení pro certifikáty?

    -   Jaké typy certifikátů používáte?

-   **Správa systémů**

    -   Jak spravujete počítačové a serverové prostředí?

    -   Používáte System Center Configuration Manager? Používáte platformu pro správu systémů od jiného výrobce?

-   **Řešení VPN**

    -   Jaké máte řešení VPN?

    -   Používáte ho ve scénářích použití firemních zařízení i ve scénářích BYOD?

Při popisu současného prostředí MDM nezapomeňte poznamenat probíhající projekty a jiné plány na změnu prostředí. Následující příklad ukazuje, jak popsat současné prostředí. Tento popis vám pomůže při vytváření vlastního návrhu Intune:

| **Oblast řešení** | **Současné prostředí** | **Komentář** |
|:---:|:---:|:---:|
| **Identita** | Azure AD, Azure AD Connect, nefederované, bez MFA | Probíhá projekt, který umožní koncem roku začít používat MFA. |                 
| **Prostředí e-mailu** | Místní Exchange, Exchange Online | V současnosti se místní Exchange migruje na Exchange Online. Už je migrovaných 75 % poštovních schránek. Zbývajících 25 % bude migrováno do začátku pilotního nasazení Intune. |                
| **SharePoint** | Místní SharePoint | Plány přechodu na SharePoint Online neexistují. |  
| **Současné řešení MDM** | Exchange ActiveSync |  |
| **Řešení pro certifikáty** | Microsoft Server 2012 R2, AD Certificate Services | Infrastruktura veřejných klíčů se používá jen pro webové servery. |
| **Správa systému** | System Center Configuration Manager CB 1606 | Zájem o hybridní řešení Intune |
| **Řešení VPN** | Cisco AnyConnect |  |

## <a name="choose-an-intune-deployment-option"></a>Volba způsobu nasazení Intune

Intune nabízí dvě možnosti nasazení: samostatné a hybridní. Potřebujete se rozhodnout, jaká možnost vyhovuje požadavkům vašeho podniku. Samostatné znamená, že Intune běží v cloudu. Hybridní znamená integraci Intune do System Center Configuration Managera.

- Další informace o [volbě mezi samostatným řešením Microsoft Intune a hybridním řešením pro správu mobilních zařízení se System Center Configuration Managerem](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

## <a name="intune-tenant-location"></a>Umístění tenanta Intune

V případě mezinárodní organizace nezapomeňte při přihlášení k odběru služby naplánovat, kde se bude nacházet tenant. Země se definuje při prvním přihlášení ke službě Intune a mapuje se na následující oblasti rozmístěné po celém světě:

-   Severní Amerika

-   Evropa, Střední východ a Afrika

-   Asie a Tichomoří

>[!IMPORTANT]
> Umístění země/tenanta se později nedá změnit.

## <a name="external-dependencies"></a>Externí závislosti

Externí závislosti jsou služby a produkty, které jsou oddělené od Intune, a tato služba je vyžaduje nebo jsou do ní integrované. U externích závislostí je potřeba identifikovat požadavky a způsob konfigurace. Tady je několik příkladů nejčastějších externích závislostí:

-   Identita

-   Skupiny uživatelů a zařízení

-   INFRASTRUKTURY VEŘEJNÝCH KLÍČŮ

Pojďme se na nejčastější externí závislosti podívat podrobněji.

### <a name="identity"></a>Identita

Identita představuje způsob identifikace uživatelů, kteří patří do organizace a zaregistrují si zařízení. Intune vyžaduje, aby identitu uživatelů poskytovala služba Azure Active Directory (Azure AD). Pokud už tuto službu používáte, můžete stávající identitu využít v cloudu. Doporučeným nástrojem k synchronizaci místních identit uživatelů s cloudovými službami Microsoftu je Azure AD Connect. Pokud už organizace používá Office 365, je důležité, aby služba Intune používala stejné prostředí Azure Active Directory.

Tady jsou další informace o požadavcích na identitu v Intune:

-   Další informace o [požadavcích na identitu](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Další informace o [požadavcích na synchronizaci adresáře](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Další informace o [požadavcích na vícefaktorové ověřování](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

### <a name="user-and-device-groups"></a>Skupiny uživatelů a zařízení

Skupiny uživatelů a zařízení určují, kdo bude cílovým příjemcem nasazeného řešení. Nasazení může být zaměřené na zásady, aplikace a profily. Čistě cloudová služba Intune podporuje skupiny uživatelů a zařízení. Potřebujete tedy zjistit požadované skupiny uživatelů a zařízení. Doporučujeme všechny skupiny vytvořit v místním systému Active Directory a potom je synchronizovat s Azure Active Directory. Tady jsou další informace o plánování a vytváření skupin uživatelů a zařízení:

-   Další informace o [plánování skupin uživatelů a zařízení](https://docs.microsoft.com/intune/deploy-use/plan-your-user-and-device-groups).

-   Další informace o [vytváření skupin uživatelů a zařízení](https://docs.microsoft.com/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

### <a name="public-key-infrastructure-pki"></a>Infrastruktura veřejných klíčů (PKI)

Infrastruktura veřejných klíčů dodává certifikáty zařízením nebo uživatelům, aby je služba mohla bezpečně ověřit. Intune podporuje infrastrukturu veřejných klíčů Microsoftu. Mobilnímu zařízení, které splňuje požadavky ověřování založeného na certifikátech, můžete vydat certifikáty zařízení a uživatele. Před implementací certifikátů je potřeba zjistit, jestli je opravdu potřebujete, jestli síťová infrastruktura podporuje ověřování založené na certifikátech a jestli se certifikáty v současném prostředí používají.

Pokud plánujete, že budete v Intune používat certifikáty s profily VPN, Wi-Fi nebo s e-mailovými profily, musíte ověřit, jestli [máte infrastrukturu PKI](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles) a jestli je připravená k vytvoření a nasazení profilů certifikátů.

V případě vydání certifikátů SCEP musíte také určit, jaký server bude hostovat funkci NDES (Network Device Enrollment Service) a jak bude probíhat komunikace.

Další informace o konfiguraci certifikátů v Intune:

-   [Jak konfigurovat infrastrukturu certifikátů pro SCEP](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep)

-   [Jak konfigurovat infrastrukturu certifikátů pro PFX](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx)

-   [Jak konfigurovat profily certifikátů Intune](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles)

-   [Jak konfigurovat zásady přístupu k prostředkům](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune)

## <a name="device-platform-considerations"></a>Informace o platformě zařízení

K pochopení správné správy zařízení je potřeba se důkladněji podívat na spravovaná zařízení.

-   Určení podporovaných platforem zařízení

-   Zařízení

-   Vlastnictví zařízení

-   Hromadný zápis

Pojďme se na tyto oblasti podívat podrobněji.

### <a name="determine-supported-device-platforms"></a>Určení podporovaných platforem zařízení

Při vytváření návrhu potřebujete vědět, jaká zařízení budou v prostředí, a musíte ověřit, jestli je Intune podporuje nebo ne. Intune podporuje platformy iOS, Android a Windows.

-   Další informace o tom, jaká [zařízení Intune podporuje](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers).

### <a name="devices"></a>Zařízení

Intune slouží ke správě mobilních zařízení. Zabezpečuje firemní data a umožňuje koncovým uživatelům pracovat z více míst. Intune podporuje více platforem zařízení. Proto doporučujeme dokumentovat zařízení a platformy OS, která návrh ve vaší organizaci podporuje. Můžete vyjít ze zařízení a platforem vytvořených v části věnované požadavkům na použití.

Při kontrole funkcí zařízení podle platformy a verze OS se také doporučuje znát verze, na které seznam odkazuje. Zde najdete příklad:

| **Platforma zařízení** | **Verze OS** |
|:---:|:---:|
| iOS – iPhone | 9.0+ |                
| iOS – iPad | 8.0+ |               
| Android – Samsung Knox Standard | 4.0+ |
| Tablet s Windows 10 | 10+ |

### <a name="device-ownership"></a>Vlastnictví zařízení

Intune podporuje zařízení v majetku společnosti i uživatele s vlastním zařízením (BYOD). Zařízení se považuje za majetek společnosti, pokud ho zaregistruje správce registrace nebo je evidované v programu registrace zařízení. Zařízení třeba může být zaregistrované prostřednictvím programu Apple DEP, kde bude označené jako firemní, a bude zařazené do skupiny zařízení určené pro firemní zásady a aplikace.

Další informace o případech použití firemních zařízení a zařízení patřících uživatelům (BYOD) najdete v [části 3: Stanovení požadavků pro různé scénáře použití](section-3-determine-use-case-requirements.md).

### <a name="bulk-enrollment"></a>Hromadný zápis

Existují různé možnosti, jak zaregistrovat zařízení v Intune, které doplňují samoobslužnou registraci na portálu společnosti. Hromadná registrace může probíhat různě – záleží na konkrétní platformě. Pokud požadujete hromadnou registraci, napřed určete, jakým způsobem bude probíhat, a potom tento způsob zapracujte do svého návrhu. Níže najdete další informace o různých způsobech hromadné registrace.

-   Další informace o [hromadné registraci](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

## <a name="feature-requirements"></a>Funkční požadavky

V těchto oddílech si probereme následující funkce a možnosti, které odpovídají požadavkům podle různých scénářů použití:

-   Zásady pro podmínky a ujednání

-   Zásady konfigurace

-   Profily prostředků

-   Aplikace

-   Zásady dodržování předpisů

-   Podmíněný přístup

Pojďme se na každou z těchto oblastí podívat podrobněji.

### <a name="terms-and-conditions-policies"></a>Zásady pro podmínky a ujednání

Podmínky a ujednání je možné použít k vysvětlení zásad nebo podmínek, které musí uživatel před registrací přijmout. Intune podporuje možnost přidat a nasadit u skupin uživatelů různé zásady pro podmínky a ujednání. Musíte určit, jestli jsou zásady pro podmínky a ujednání potřeba. Pokud tomu tak je, kdo v organizaci odpovídá za poskytování těchto informací.

-   Přečtěte si, [jak v Intune vytvářet zásady pro podmínky a ujednání](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune). Následující příklad vysvětluje, jak dokumentovat zásadu pro podmínky a ujednání.

| **Název podmínek a ujednání** | **Případ použití** | **Cílová skupina** |
|:---:|:---:|:---:|
| Firemní podmínky a ujednání | Firemní | Firemní uživatelé |                 
| Podmínky a ujednání pro uživatele s vlastním zařízením | Uživatelé s vlastním zařízením | Uživatelé s vlastním zařízením |                

### <a name="configuration-policies"></a>Zásady konfigurace

Zásady konfigurace se používají ke správě nastavení zabezpečení a funkcí na zařízení. Při návrhu zásad konfigurace se podívejte na část věnovanou požadavkům pro různé případy použití, kde zjistíte požadovanou konfiguraci zařízení pro Intune. Poznamenejte si nastavení a způsob konfigurace zařízení. Poznamenejte si také, jakým uživatelům nebo skupinám zařízení je zásada konfigurace určena.

Měli byste vytvořit aspoň jednu zásadu konfigurace pro každou platformu. Pokud to bude potřeba, můžete pro každou platformu vytvořit více zásad konfigurace. Následující příklad ilustruje návrh čtyř různých zásad konfigurace pro různé platformy a scénáře použití.

| **Název zásady** | **Platforma zařízení** | **Nastavení** | **Cílová skupina** |   
|:---:|:---:|:---:|:---:|
| Firemní – iOS | iOS | PIN je povinný, délka 6 znaků, omezené zálohování do cloudu | Firemní zařízení |                                                           
| Firemní – Android | Android | PIN je povinný, délka 6 znaků, omezené zálohování do cloudu | Firemní zařízení |                                                           
| Vlastní zařízení uživatelů – iOS  | iOS | PIN je povinný, délka 4 znaky | Vlastní zařízení uživatelů |
| Vlastní zařízení uživatelů – Android  | Android | PIN je povinný, délka 4 znaky | Vlastní zařízení uživatelů |

### <a name="profiles"></a>Profily

Profily pomáhají koncovému uživateli, aby se mohl připojit k firemním datům. Intune podporuje různé typy profilů. Pokud chcete určit, kdy se budou [profily](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune) konfigurovat, podívejte se na případy použití a požadavky. Všechny profily zařízení jsou zařazené do kategorií podle typu platformy a měly by být součástí dokumentace k návrhu.

-   Profily certifikátů

-   Wi-Fi profil

-   profil VPN

-   e-mailový profil

Pojďme se podrobněji podívat na každý typ profilu.

##### <a name="certificate-profiles"></a>Profily certifikátů

Profily certifikátů umožňují službě Intune vydat certifikát uživateli nebo zařízení. Jaké certifikáty podporuje Intune:

-   Protokol SCEP (Simple Certificate Enrollment Protocol)

-   Důvěryhodný kořenový certifikát

-   Certifikát PFX

Doporučuje se dokumentovat, jaké skupiny uživatelů certifikát potřebují, kolik profilů certifikátů bude potřeba a jakým skupinám uživatelů budete profily zavádět.

>[!NOTE]
> Pamatujte, že certifikát SCEP vyžaduje důvěryhodný kořenový certifikát. Proto zajistěte, aby všichni uživatelé určení pro certifikát SCEP obdrželi i důvěryhodný kořenový certifikát. Pokud potřebujete certifikáty SCEP, navrhněte a popište, jaké šablony certifikátu SCEP budou potřeba.

Tady je příklad, jak při návrhu dokumentovat certifikáty:

| **Typ** | **Název profilu** | **Platforma zařízení** | **Případy použití** |   
|:---:|:---:|:---:|:---:|
| Kořenová CA | Firemní kořenová CA | Android, iOS, Windows Mobile | Firemní zařízení, vlastní zařízení uživatelů  |                                                           
| SCEP | Uživatelský certifikát | Android, iOS, Windows Mobile | Firemní zařízení, vlastní zařízení uživatelů |                                                           

##### <a name="wi-fi-profile"></a>Wi-Fi profil

Profily Wi-Fi se používají k automatickému připojení mobilního zařízení k bezdrátové síti. Intune podporuje nasazení profilů Wi-Fi pro všechny podporované platformy.

-   Přečtěte si další informace o tom, [jak Intune podporuje profily Wi-Fi.](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune)

Tady je příklad návrhu profilu Wi-Fi:

| **Typ** | **Název profilu** | **Platforma zařízení** | **Případy použití** |   
|:---:|:---:|:---:|:---:|
| Wi-Fi | Profil Wi-Fi pro Asii | Android | Firemní zařízení, vlastní zařízení uživatelů, oblast Asie|                                                           
| Wi-Fi | Profil Wi-Fi pro Severní Ameriku | Android, iOS, Windows 10 Mobile | Firemní zařízení, vlastní zařízení uživatelů, oblast Severní Amerika |                                                           

##### <a name="vpn-profile"></a>profil VPN

Profily VPN nabízejí uživatelům bezpečný přístup k síti ze vzdálených míst. Intune podporuje profily VPN nativních mobilních připojení VPN a externích dodavatelů.

-   Další informace o [profilech VPN a dodavatelích podporovaných službou Intune](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune).

Tady je příklad, jak dokumentovat návrh profilu VPN.

| **Typ** | **Název profilu** | **Platforma zařízení** | **Případy použití** |   
|:---:|:---:|:---:|:---:|
| Síť VPN | Profil VPN Cisco pro jakékoli připojení | Android, iOS, Windows 10 Mobile | Firemní zařízení, vlastní zařízení uživatelů, oblast Severní Amerika a Německo|                                                           
| Síť VPN | Pulse Secure | Android | Firemní zařízení, vlastní zařízení uživatelů, oblast Asie |                                                           

##### <a name="email-profile"></a>e-mailový profil

E-mailové profily umožňují e-mailovému klientovi automatické nastavení informací o připojení a nastavení e-mailové konfigurace. Intune podporuje e-mailové profily jen na některých zařízeních.

-   Další informace o [e-mailových profilech](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) a podporovaných platformách.

Tady je příklad, jak dokumentovat návrh e-mailových profilů:

| **Typ** | **Název profilu** | **Platforma zařízení** | **Případy použití** |   
|:---:|:---:|:---:|:---:|
| e-mailový profil | E-mailový profil pro iOS | iOS | Firemní – informatik (uživatel s vlastním zařízením) |                                                           
| e-mailový profil | E-mailový profil pro Android Knox | Android Knox | Uživatelé s vlastním zařízením |

### <a name="apps"></a>Aplikace

Intune podporuje různé způsoby poskytování aplikací uživatelům nebo zařízením. Typem poskytované aplikace mohou být aplikace se softwarovým instalačním programem, aplikace z veřejného obchodu, externí odkazy nebo spravované aplikace pro iOS. Kromě individuálně nasazených aplikací můžete spravovat a nasazovat i aplikace nakoupené hromadně prostřednictvím programů VPP (Volume Purchase Program) pro iOS a Windows. Tady jsou další informace o tom, jak služba Intune podporuje aplikace a programy VPP.

-   Další informace o [typech aplikací](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

-   Další informace o [programu VPP (Volume Purchase Program for Business) pro iOS](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune).

-   Další informace o [Windows Storu pro firmy](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune).

#### <a name="app-type-requirements"></a>Požadavky různých typů aplikací

Aplikace můžete nasazovat uživatelům a zařízením. Doporučujeme, abyste se rozhodli, jaké aplikace chcete v Intune spravovat. Při sestavování seznamu se pokuste odpovědět na následující otázky:

-   Vyžadují aplikace integraci s cloudovými službami?

-   Budou všechny aplikace dostupné uživatelům modelu BYOD?

-   Jaké jsou u těchto aplikací možnosti nasazení?

-   Potřebuje společnost pro své partnery zajistit přístup k datům aplikací SaaS (software jako služba)?

-   Vyžadují aplikace, aby zařízení uživatelů měla přístup k internetu?

-   Jsou aplikace veřejně dostupné v App Storu nebo jde o vlastní oborové aplikace?


>[!TIP]
> Podívejte se na [různé typy aplikací, které podporuje Intune](https://docs.microsoft.com/intune/deploy-use/add-apps).

#### <a name="app-protection-policies"></a>Zásady ochrany aplikace

Zásady ochrany aplikace minimalizují ztrátu dat tím, že definují, jak aplikace spravuje firemní data. Intune podporuje zásady ochrany pro každou aplikaci vytvořenou tak, aby fungovala se správou mobilních aplikací. Při návrhu zásad ochrany aplikace potřebujete určit, jaká omezení firemních dat u dané aplikace použijete. Doporučuje se kontrolovat, jak [zásady ochrany aplikace](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) fungují. Tady je příklad, jak dokumentovat stávající aplikace a jakou ochranu potřebují.

| **Aplikace** | **Účel** | **Platformy** | **Případ použití** | **Zásada ochrany aplikace** |
|:---:|:---:|:---:|:---:|:---:|
| Outlook Mobile  | K dispozici | iOS | Firemní – vedení | Nelze provést jailbreak, šifrování souborů |                                                         
| Word | K dispozici | iOS, Android – Samsung Knox, jiný systém než Knox, Windows 10 Mobile | Firemní zařízení, vlastní zařízení uživatelů | Nelze provést jailbreak, šifrování souborů |                                                         

#### <a name="compliance-policies"></a>Zásady slučitelnosti

Zásady dodržování předpisů určují, zda zařízení vyhovuje určitým požadavkům. Služba Intune používá zásady dodržování předpisů k tomu, aby zjistila, jestli zařízení vyhovuje nebo nevyhovuje. Stav dodržování předpisů je pak možné použít k omezení přístupu k prostředkům společnosti. Pokud je potřeba podmíněný přístup, doporučuje se navrhnout [zásady dodržování předpisů zařízení](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune). Pokud chcete zjistit, kolik zásad dodržování předpisů zařízení potřebujete a jaké skupiny uživatelů jsou cílové, přečtěte si požadavky a případy použití. Potřebujete také určit, jak dlouho smí být zařízení offline nezaregistrované, než se bude považovat za nevyhovující.

Tady je příklad návrhu zásad dodržování předpisů:

| **Název zásady** | **Platforma zařízení** | **Nastavení** | **Cílová skupina** |   
|:---:|:---:|:---:|:---:|
| zásady dodržování předpisů | iOS, Android – Samsung Knox, jiný systém než Knox, Windows 10 Mobile | PIN – povinný, nelze provést jailbreak | Firemní zařízení, vlastní zařízení uživatelů |

#### <a name="conditional-access-policies"></a>Zásady podmíněného přístupu

Podmíněný přístup se používá, když chcete přístup k firemním prostředkům povolit jenom vyhovujícím zařízením. Při kontrole přístupu k prostředkům společnosti funguje Intune s celým řešením EMS (Enterprise Mobility + Security). Musíte se rozhodnout, jestli je podmíněný přístup potřeba a co musí být zabezpečené.

-   Další informace o [podmíněném přístupu](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

U online přístupu je potřeba určit, na jaké platformy a skupiny uživatelů budou zásady podmíněného přístupu zaměřeny.

Musíte také rozhodnout, jestli potřebujete instalovat/konfigurovat konektor Intune Service to Service Connector pro Exchange Online nebo místní Exchange.

Další informace o instalaci a konfiguraci konektorů Intune Service to Service Connector:

-   [Exchange Online](https://docs.microsoft.com/intune/deploy-use/intune-service-to-service-exchange-connector)

-   [Místní Exchange](https://docs.microsoft.com/intune/deploy-use/intune-on-premises-exchange-connector)

Tady je příklad, jak dokumentovat zásady podmíněného přístupu:

| **Služba** | **Platformy moderního ověřování** | **Základní ověřování** | **Případy použití** |   
|:---:|:---:|:---:|:---:|
| Exchange Online | iOS, Android | Blokování nevyhovujících zařízení na platformách podporovaných službou Intune | Firemní zařízení, vlastní zařízení uživatelů |
| SharePoint Online | iOS, Android |  | Firemní zařízení, vlastní zařízení uživatelů |

## <a name="next-section"></a>Další část

Další část obsahuje pokyny k [procesu implementace Intune](section-8-onboarding-process.md).

