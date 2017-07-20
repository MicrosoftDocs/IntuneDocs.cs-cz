---
title: "Povolení vlastních zařízení v Microsoft Intune"
description: 
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: 880b83a63eefe13a96ab8838c7092c185aa32cd0
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2017
---
# <a name="enable-byod-with-intune"></a>Přineste si vlastní zařízení s Intune

Toto téma obsahuje pracovní postup, který je důležitý pro nastavení služby Intune, aby bylo možné ve vaší organizaci povolit řešení umožňující přinést vlastní zařízení (BYOD). Uspořádává tuto úlohu do tří procesů a odkazuje na témata podpory s postupy.

Pracovní postup se dělí na tři následující procesy. Jednotlivé aspekty každého procesu můžete přizpůsobit požadavkům vaší organizace.

-   **[Registrace zařízení a kontrola dodržování předpisů](#enroll-devices-and-check-for-compliance)** popisuje, jak povolit uživatelům registraci vlastních zařízení do správy pomocí Intune. Intune spravuje zařízení s iOSem, macOS, Androidem a Windows. V této části najdete také popis toho, jak nasadit zásady na zařízení a zajistit, že splňují požadavky na základní zabezpečení.

- V části **[Poskytnutí přístupu k prostředkům společnosti](#provide-access-to-company-resources)** se dozvíte, jak může IT zajistit, že budou uživatelé získávat přístup k prostředkům společnosti snadno a zabezpečeně. Používá se k tomu nasazení přístupových profilů na spravovaná zařízení. V této části je vysvětlené také to, jak spravovat nasazení aplikací zakoupených v rámci multilicenčního programu s Intune.

-   Část **[Ochrana dat společnosti](#protect-company-data)** vám pomůže získat informace tom, jak poskytnout podmíněný přístup k podnikovým prostředkům, jak zajistit ochranu před únikem informací a jak odebrat podnikové aplikace a data ze zařízení, když už nejsou potřeba k práci nebo dojde k jejich ztrátě nebo odcizení.

[![Schéma základního pracovního postupu pro povolení vlastních zařízení s Microsoft Intune](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## <a name="before-you-begin"></a>Před zahájením
Než budou moct uživatelé zaregistrovat zařízení, je nejprve nutné připravit samotnou službu Intune. K tomu je potřeba [přiřadit licence uživatelům](licenses-assign.md) a [nastavit autoritu správy mobilních zařízení](mdm-authority-set.md).

S tím současně byste měli také [přizpůsobit portál společnosti](company-portal-customize.md). Přidání firemního brandingu a poskytnutí informací o podpoře uživatelům. Zajistíte jim tak důvěryhodné prostředí registrace a podpory.

## <a name="enroll-devices-and-check-for-compliance"></a>Registrace zařízení a kontrola splnění požadavků na zabezpečení

Po přípravě služby Intune je potřeba zajistit splnění různých požadavků na registraci pro různé typy zařízení, které chcete spravovat. Proces registrace zařízení do systému správy je jednoduchý, ale pro různé typy zařízení se mírně liší.

-   **Zařízení s iOSem a počítače Mac**: Aby bylo možné zaregistrovat iPady, iPhony nebo zařízení s MacOS, budete potřebovat [certifikát APNs (Apple Push Notification service)](apple-mdm-push-certificate-get.md). Až nahrajete certifikát APNs do Intune, můžou uživatelé [zaregistrovat zařízení s iOSem](/intune-user-help/enroll-your-device-in-intune-ios) pomocí aplikace Portál společnosti a na webu Portál společnosti můžou [zaregistrovat zařízení s MacOS](/intune-user-help/enroll-your-device-in-intune-macos).

-   **Zařízení s Androidem**: Pokud chcete zaregistrovat zařízení s Androidem, nemusíte službu Intune nijak připravovat. Stačí, když uživatelé [zapíšou svá zařízení s Androidem](/intune-user-help/enroll-your-device-in-intune-android.md) do systému správy pomocí aplikace Portál společnosti dostupné na Google Play.

-   **Zařízení Windows Phone a počítače PC**: Pro [server registrace byste měli nastavit alias DNS](windows-enroll.md#enable-windows-enrollment-without-azure-ad-premium) a usnadnit tak registraci zařízení s Windows. Jinak můžou uživatelé [zaregistrovat zařízení s Windows](/intune-user-help/enroll-your-w10-phone-or-w10-pc-windows) přidáním pracovního nebo školního účtu.

  - Pokud máte Azure AD Premium, usnadníte uživatelům registraci zařízení s Windows, když jim [umožníte automatickou registraci](windows-enroll.md). Tato funkce registruje zařízení do služby Intune automaticky, když uživatel přidá pracovní nebo školní účet, aby si zaregistroval osobní zařízení. Funguje i pro zařízení vlastněná společností, která se připojí k Azure AD ve vaší organizaci.


### <a name="make-sure-that-managed-devices-meet-basic-security-requirements"></a>Spravovaná zařízení musí splňovat základní požadavky na zabezpečení

Až si uživatelé zaregistrují zařízení v systému správy, musí IT pracovníci zajistit, že budou zařízení používaná pro přístup k podnikovým aplikacím a datům splňovat základní požadavky na zabezpečení. Mezi tyto pravidla může patřit používání kódu PIN pro přístup k zařízením a šifrování dat uložených na zařízeních. Sada těchto pravidel se označuje jako [zásady dodržování předpisů](device-compliance.md).

Když [nasadíte zásady dodržování předpisů](device-compliance-get-started.md) pro uživatele, zkontroluje Intune všechna zařízení, která spravuje, aby se zjistilo, jestli vyhovují základním požadavkům na zabezpečení, které jste definovali jako součást zásad Přineste si vlastní zařízení. Po vyhodnocení dodržování zásad se nahlásí stav zpátky do Intune. V některých případech můžou být uživatelé vyzváni k opravě nastavení, například PIN kódu nebo šifrování zařízení. Jindy aplikace Portál společnosti jednoduše upozorní uživatele na veškeré nastavení, které nevyhovuje zásadám.

## <a name="provide-access-to-company-resources"></a>Poskytnutí přístupu k podnikovým prostředkům

První věcí, kterou chce mít většina zaměstnanců na svých mobilních zařízeních, je přístup k podnikovému e-mailu a dokumentům. Navíc očekávají, že se nastavení obejde bez složitého postupu nebo volání na technickou podporu. Intune usnadňuje [vytvoření a nasazení nastavení e-mailu](conditional-access-intune-common-ways-use.md) pro nativní e-mailové aplikace, které jsou předem nainstalované na mobilních zařízeních.
<!--- this was old link: (https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune). check with Andre--->

> [!NOTE]
> Intune podporuje konfiguraci e-mailového profilu Android for Work pro e-mailové aplikace Gmail a Nine Work, které najdete v obchodě Google Play.

Intune také pomáhá řídit a chránit přístup k místním datům společnosti, když uživatelé pracují mimo pracoviště. Profily [Wi-Fi](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune), [VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) a e-mailu Intune společně pomáhají zajistit odkudkoli přístup k souborům a prostředkům, které uživatelé potřebují ke své práci. Webové aplikace vašeho podniku a služby hostované místně je možné bezpečně zobrazovat a chránit také pomocí proxy aplikace Azure Active Directory a podmíněného přístupu.

### <a name="manage-volume-purchased-apps"></a>Správa hromadně zakoupených aplikací
S Intune je možné snadno:
* Importovat informace o multilicencích svazku z libovolného obchodu s aplikacemi
* Sledovat počet použitých licencí
* Znemožnit uživatelům instalovat více kopií aplikace, než vlastníte
* [Dodávat aplikace ze obchodu na spravovaná zařízení](apps-deploy.md)
* Zacílit aplikace na nespravovaná zařízení s použitím webu portálu společnosti

Intune také umožňuje spravovat a nasazovat aplikace zakoupené v multilicenčních verzích z App Storu pro iOS a Windows Storu pro firmy. Můžete tak snížit administrativní režii při sledování hromadně zakoupených aplikací.

> [!TIP]
> Můžete [nakonfigurovat jednotné přihlašování (SSO) s použitím Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). Jednotné přihlašování umožňuje uživatelům přihlášení do aplikací s použitím doménového uživatelského jména a hesla, které používají místně. Kromě toho můžete [poskytnout internetový přístup k místně hostovaným webovým aplikacím](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) pomocí proxy aplikací služby Azure Active Directory.

-   [Správa hromadně koupených aplikací pro zařízení s iOSem](vpp-apps-ios.md). K hromadnému nákupu licencí pro aplikace iOS se používá program [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/). Je nutné vytvořit účet Apple VPP na webu Apple a nahrát do Intune token Apple VPP. Potom je možné synchronizovat informace o hromadném nákupu s Intune a sledovat využití aplikací, které jste tímto způsobem zakoupili.

-   [Správa aplikací koupených z Windows Storu pro firmy](windows-store-for-business.md) [Windows Store pro firmy](https://www.microsoft.com/business-store) je místo, kde můžete najít a zakoupit aplikace pro svoji organizaci, a to jednotlivě i hromadně. Pokud obchod propojíte s Intune, můžete spravovat hromadně zakoupené aplikace pomocí portálu Intune.

## <a name="protect-company-data"></a>Ochrana dat společnosti

Intune chrání firemní data prostřednictvím řady technologických vrstev. Ve vrstvě identity se s použitím podmíněného přístupu chrání přístup ke službám. Podmíněný přístup umožňuje přístup k firemním prostředkům jenom spravovaným a vyhovujícím zařízením. V klientské aplikační vrstvě zajišťuje správa mobilních aplikací (MAM) ochranu před únikem informací.  Zásady ochrany aplikací znemožňují přesun dat do nechráněných aplikací nebo umístění úložišť. Tyto zásady vám také umožní vymazat firemní data v případě ztráty nebo odcizení zařízení.

### <a name="enforce-conditional-access-to-company-resources"></a>Vynucení podmíněného přístupu k podnikovým prostředkům

Zásady dodržování předpisů a [zásady podmíněného přístupu](device-compliance.md) můžete kombinovat a to vám umožní kontrolovat, jestli zařízení splňují základní požadavky na zabezpečení vyžadované vašimi zásadami Přineste si vlastní zařízení. Pokud zařízení nesplňuje požadavky, vynutí se pravidla a odepře přístup, dokud zařízení nevyhoví požadavkům zásad. Zajistí se tak, že budou mít ze služeb, jako je Exchange ([místní Exchange](exchange-connector-install.md) nebo [Exchange Online](conditional-access-exchange-create.md)), SharePoint Online, Online Skype pro firmy a další, měla přístup k podnikovým datům jenom spravovaná a vyhovující zařízení.
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> Zásady podmíněného přístupu nebudou fungovat, pokud nebudou existovat zásady dodržování předpisů, které by dodržování předpisů ověřily.

### <a name="prevent-data-loss-of-company-data-with-application-protection-policies"></a>Ochrana před únikem informací z podnikových dat pomocí zásad ochrany aplikací

Se zásadami ochrany aplikací služby Intune si můžete zvolit, jakým způsobem se bude získávat přístup k datům – s registrací zařízení nebo bez ní. Tato univerzálnost umožňuje chránit firemní data, takže i přesto, že uživatel nezaregistruje svoje zařízení do Intune, bude mít k firemním datům zabezpečený přístup.

Pomocí [zásad ochrany aplikací služby Intune](app-protection-policies.md) můžete chránit podniková data, ke kterým uživatelé přistupují ze zařízení s iOSem a Androidem. Když používáte tyto zásady na úrovni aplikace, můžete řídit způsob, jakým zaměstnanci používají a sdílejí podniková data, i když samotné zařízení služba Intune nespravuje.

Pomocí [zásad WIP (Windows Information Protection)](app-protection-policies-configure-windows-10.md) můžete to samé dělat u spravovaných zařízení s Windows 10. Tyto zásady fungují, aniž by narušovaly činnost zaměstnanců. Nevyžadují změny prostředí vaší sítě ani jiných aplikací.

### <a name="wipe-company-data-while-leaving-personal-data-intact"></a>Vymazání podnikových dat a ponechání osobních dat beze změny

Pokud už zařízení není pro práci potřeba, mění se účel jeho používání nebo se prostě ztratilo, je nutné z něj odebrat podnikové aplikace a data. K tomu můžete použít možnosti služby Intune pro selektivní a úplné vymazání. Uživatelé také mohou vzdáleně vymazat svá vlastní zařízení z Portálu společnosti Intune, pokud jsou tato zařízení v Intune zaregistrovaná.

[Úplné vymazání](devices-wipe.md) obnoví v zařízení výchozí nastavení od výrobce a odebere uživatelská data a nastavení. [Selektivní vymazání](devices-wipe.md#selective-wipe) odebere ze zařízení jenom firemní data, ale osobní data uživatelů ponechá beze změn.

Po zahájení zařízení ihned spustí proces selektivního vymazání pro odebrání ze správy. Po dokončení procesu se všechna podniková data odstraní a název zařízení už se nebude zobrazovat v konzole pro správu služby Intune. Ukončí se tak životní cyklus správy zařízení.
