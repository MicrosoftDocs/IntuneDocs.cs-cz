---
title: Co je Microsoft Intune
description: "Přečtěte si o tom, jak je Intune komponentou správy mobilních zařízení v řešení Enterprise Mobility + Security a jak pomáhá chránit firemní data."
keywords: co je Intune
author: Lindavr
ms.author: lindavr
manager: angrobe
ms.date: 07/28/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
ms.custom: 
ms.openlocfilehash: 53115eba5e5150139b8ff0f359cde279df297d47
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/03/2017
---
# <a name="what-is-intune"></a>Co je Intune?

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Intune je cloudová služba pro správu mobility velkých organizací (EMM), která pomáhá tomu, aby vaši pracovníci byli produktivní, a současně chrání vaše firemní data. Intune vám umožňuje:
* Spravovat mobilní zařízení, která vaši pracovníci používají pro přístup k datům společnosti
* Spravovat mobilní aplikace, které vaši pracovníci používají
* Chránit informace vaší společnosti díky řízení způsobu, jak k nim vaši pracovníci přistupují a jak je sdílejí
* Zajistit, aby zařízení a aplikace splňovaly požadavky společnosti na zabezpečení

Intune se úzce integruje se službou Azure Active Directory (Azure AD) kvůli řízení přístupu a identit a se službou Azure Information Protection kvůli ochraně dat.

Dohromady pak Office 365 a EMS vašim pracovníkům umožňují, aby byli produktivní na všech zařízeních, a současně chrání informace vaší organizace. Office 365 s EMS je kompletní integrovaná sada nástrojů pro podnikovou mobilitu, která se zaměřuje na produktivitu, identitu, řízení přístupu, správu a ochranu dat. Nabízí efektivní způsob, jak nasadit a provozovat řešení mobility ve vaší organizaci.

## <a name="how-does-intune-work"></a>Jak Intune funguje?
Intune zajišťuje správu mobilních zařízení (MDM) a správu mobilních aplikací (MAM). Funkce MDM a MAM Intune pak pomáhají ve scénářích ochrany dat a dodržování předpisů v rámci sady EMS.  

Způsob využívání funkcí MDM/MAM Intune a ochrany dat EMS závisí na [obchodním problému, který se snažíte řešit](#common-business-problems-that-intune-helps-solve). Například:
* MDM můžete hodně využít, pokud vytváříte fond jednoúčelových zařízení, která mají sdílet pracovníci střídající se na směnách v prodejně.
* O MAM a ochranu dat se můžete opřít, pokud pracovníkům povolujete pro přístup k firemním datům používat jejich osobní zařízení (model BYOD).  
* Pokud zaměstnancům pracujícím s informacemi poskytujete firemní telefony, můžete spoléhat na všechny uvedené technologie.

## <a name="intune-mobile-device-management-mdm-explained"></a>Vysvětlení správy mobilních zařízení (MDM) Intune
MDM využívá protokoly nebo rozhraní API, které jsou k dispozici v mobilních operačních systémech. Zahrnuje úlohy jako:
* Registrace zařízení do správy, aby IT oddělení mělo seznam zařízení, která přistupují k firemním službám
* Konfigurace zařízení, aby splňovala standardy společnosti z hlediska zabezpečení a stavu
* Poskytování certifikátů a profilů Wi-Fi/VPN pro přístup k firemním službám
* Hlášení a měření, jak zařízení dodržují firemní standardy
* Odebírání firemních dat ze spravovaných zařízení  

Občas se mezi lidmi objevuje názor, že **řízení přístupu k firemním datům** je funkce MDM. My to tak nevnímáme, protože to není něco, co by poskytoval mobilní operační systém. Spíše to zajišťuje poskytovatel identity. V našem případě je poskytovatelem identity Azure Active Directory (Azure AD), systém Microsoftu pro správu identity a přístupu.  

Intune se integruje s Azure AD a umožňuje širokou škálu scénářů řízení přístupu. Můžete třeba vyžadovat, aby mobilní zařízení splňovalo firemní standardy definované v Intune, než může získat přístup k podnikové službě, jako je Exchange. Podobně můžete přístup k podnikové službě omezit jenom na konkrétní sadu mobilních aplikací. Můžete třeba přístup k Exchangi Online omezit jenom na Outlook nebo Outlook Mobile.

## <a name="intune-mobile-app-management-mam-explained"></a>Vysvětlení správy mobilních aplikací (MAM) Intune
Když mluvíme o MAM, myslíme tím sadu věcí, které naše řešení umožňují IT odborníkům provádět s mobilními aplikacemi, třeba:
* Publikování mobilních aplikací zaměstnancům
* Konfigurace aplikací
* Řízení způsobů používání a sdílení firemních dat v mobilních aplikacích
* Odebírání firemních dat z mobilních aplikací   
* Aktualizace mobilních aplikací
* Hlášení o inventáři mobilních aplikací
* Sledování využití mobilních aplikací

MAM se často používá k označení kterékoli z těchto jednotlivých věcí nebo jejich konkrétních kombinací. Lidé zejména běžně spojují dohromady koncept konfigurace aplikací (tedy využívání technologií jako [spravované konfigurace aplikací v iOSu](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html)) s konceptem zabezpečení firemních dat v mobilních aplikacích. Důvodem je, že některé mobilní aplikace nabízejí nastavení, která umožňují konfigurovat jejich funkce zabezpečení dat.

To pak v kombinaci s funkcemi operačního systému pro ochranu dat (například funkcemi MDM, jako je Windows Information Protection ve Windows 10) zajišťuje výraznou ochranu dat na mobilních zařízeních.

Když Intune použijete s dalšími službami v EMS, můžete organizaci poskytnout zabezpečení mobilních aplikací daleko nad rámec toho, co poskytují mobilní operační systém a samotné mobilní aplikace prostřednictvím konfigurace aplikací. Aplikace, která je spravovaná pomocí EMS, má přístup k širší sadě ochran mobilních aplikací a dat, která zahrnuje:

* [Jednotné přihlašování](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)  
*   [Vícefaktorové ověřování](https://docs.microsoft.com/multi-factor-authentication/multi-factor-authentication)
* [Podmíněný přístup aplikací – povolení přístupu, pokud mobilní aplikace obsahuje firemní data](app-based-conditional-access-intune.md)
* [Izolování firemních dat od osobních dat uvnitř stejné aplikace](app-protection-policy.md)
* [Zásady ochrany aplikací (PIN, šifrování, uložit jako, schránka atd.)](app-protection-policies.md)
* [Vymazání firemních dat z mobilní aplikace](apps-selective-wipe.md)
* [Podpora správy přístupových práv](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

![Obrázek ukazující úrovně zabezpečení dat správy aplikací](./media/managing-mobile-apps.png)

### <a name="intune-mobile-app-security"></a>Zabezpečení mobilních aplikací Intune
Zajištění zabezpečení aplikací je součástí MAM, a když mluvíme o zabezpečení mobilních aplikací v Intune, myslíme tím:
* Jak zajistit, aby se k vašim osobním údajům nedostalo firemní IT oddělení
* Omezení akcí, které můžou uživatelé provádět s firemními informacemi, například kopírování, vyjmutí a vložení, uložení a zobrazení
* Odebrání firemních dat z mobilních aplikací, které se taky označuje jako selektivní vymazání nebo firemní vymazání

Intune zajišťuje zabezpečení mobilních aplikací mimo jiné prostřednictvím funkce **zásad ochrany aplikací**. Zásady ochrany aplikací využívají identitu Azure AD k izolování firemních dat od osobních. Data, ke kterým se přistupuje pomocí firemních přihlašovacích údajů, dostanou dodatečnou firemní ochranu.

Když se uživatel ke svému zařízení přihlásí pomocí svých firemních přihlašovacích údajů, jeho firemní identita mu umožní přístup k datům, který je jeho osobní identitě odepřený. Při používání firemních dat pak Intune společně s dalšími technologiemi EMS řídí, jak může uživatel data ukládat a sdílet. Na data, ke kterým uživatel přistupuje po přihlášení k zařízení pomocí své osobní identity, se stejné ochrany nepoužívají. Tímto způsobem má IT kontrolu nad firemními daty, zatímco koncový uživatel si udržuje kontrolu a soukromí ve vztahu k osobním datům.

## <a name="emm-with-and-without-device-enrollment"></a>EMM s registrací a bez registrace zařízení
Většina řešení správy mobility velkých organizací podporuje základní technologie mobilních zařízení a mobilních aplikací. Ty jsou obvykle svázány se zařízením, které je zaregistrované v řešení MDM vaší organizace. Intune podporuje tyto scénáře a navíc také mnoho scénářů „bez registrace“.  

Organizace se liší v rozsahu, v jakém přijímají scénáře „bez registrace“. Některé organizace to používají jako standard. Některé to povolují u doplňkových zařízení, jako jsou osobní tablety. Jiné to nepodporují vůbec. I v tomto posledním případě, kdy organizace vyžaduje, aby všechna zařízení zaměstnanců byla zaregistrovaná v MDM, tyto organizace obvykle scénáře „bez registrace“ podporují pro dodavatele a pro další zařízení, která mají zvláštní výjimku.

Můžete dokonce technologii Intune „bez registrace“ používat i na registrovaných zařízeních. Zařízení zaregistrované v MDM může mít třeba ochranu funkce „Otevřít v aplikaci“ poskytované mobilním operačním systémem. (Ochrana funkce „Otevřít v aplikaci“ je funkce iOS, která zabrání otevřít dokument z jedné aplikace (například z Outlook) do jiné aplikace (například do Wordu), pokud obě aplikace nejsou spravované poskytovatelem řešení MDM.) Kromě toho může IT oddělení použít zásady ochrany aplikací na mobilní aplikace spravované pomocí EMS proto, aby řídilo možnost „uložit jako“ nebo zajistilo vícefaktorové ověřování.

Bez ohledu na postoj vaší organizace k zaregistrovaným a nezaregistrovaným mobilním zařízením a aplikacím obsahuje Intune jako součást EMS nástroje, které vám pomůžou zvýšit produktivitu zaměstnanců a současně ochránit firemní data.

## <a name="common-business-problems-that-intune-helps-solve"></a>Běžné obchodní problémy, které Intune pomáhá vyřešit
Následující seznam obchodních problémů odkazuje na podrobnější informace o řešeních, která můžeme poskytnout. Jenom poslední položka vyžaduje jako součást řešení registraci v MDM:

* [Ochrana místních e-mailů a dat, aby se k nim mohlo přistupovat pomocí mobilních zařízení](common-scenarios.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Ochrana e-mailů a dat Office 365, aby se k nim mohlo bezpečně přistupovat pomocí mobilních zařízení](common-scenarios.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Poskytnutí firemních telefonů pracovníkům](common-scenarios.md#issue-corporate-owned-phones-to-your-employees)
* [Nabídnutí programu Přineste si vlastní zařízení (BYOD) nebo programu osobních zařízení všem zaměstnancům](common-scenarios.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Umožnění zabezpečeného přístupu zaměstnanců k Office 365 z nespravované veřejného terminálu](common-scenarios.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Poskytnutí sdílených tabletů s omezeným použitím pracovníkům, kteří provádějí konkrétní úlohy](common-scenarios.md#issue-limited-use-shared-tablets-to-your-employees)

### <a name="next-steps"></a>Další kroky
* Přečtěte si o některých [běžných způsobech použití Intune](common-scenarios.md).
* Seznamte se s tímto produktem [prostřednictvím 30denní zkušební verze Intune](free-trial-sign-up.md).
* Podrobně se seznamte s [technickými požadavky a možnostmi](supported-devices-browsers.md) služby Intune.
