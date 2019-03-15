---
title: Co je Microsoft Intune
description: Zjistěte, jak Microsoft Intune je Správa mobilních zařízení (MDM) a mobilní aplikace správy (MAM) součástí Enterprise Mobility + Security řešení a jak vám může pomoct chránit firemní data.
keywords: co je Intune
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/26/2019
ms.topic: overview
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
search.appverid: MET150
ms.custom: get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 511e672193ec609f817c10572c99ac73831c54ae
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57460576"
---
# <a name="what-is-microsoft-intune"></a>Co je Microsoft Intune?

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Microsoft Intune je Cloudová služba v oboru enterprise mobility management (EMM), který umožňuje, aby vaši pracovníci byli produktivní a současně chrání vaše firemní data. Podobně jako jiné služby Azure je Microsoft Intune k dispozici na portálu Azure Portal. Intune vám umožňuje:
* Správa mobilních zařízení a počítačů, které vaši pracovníci používají pro přístup k firemním datům.
* Spravovat mobilní aplikace, které vaši pracovníci používají
* Chránit informace vaší společnosti díky řízení způsobu, jak k nim vaši pracovníci přistupují a jak je sdílejí
* Zajistit, aby zařízení a aplikace splňovaly požadavky společnosti na zabezpečení

## <a name="common-business-problems-that-intune-helps-solve"></a>Běžné obchodní problémy, které Intune pomáhá vyřešit

* [Ochrana místních e-mailů a dat, aby se k nim mohlo přistupovat pomocí mobilních zařízení](common-scenarios.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Ochrana e-mailů a dat Office 365, aby se k nim mohlo bezpečně přistupovat pomocí mobilních zařízení](common-scenarios.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Poskytnutí firemních telefonů pracovníkům](common-scenarios.md#issue-corporate-owned-phones-to-your-employees)
* [Nabídnutí programu Přineste si vlastní zařízení (BYOD) nebo programu osobních zařízení všem zaměstnancům](common-scenarios.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Umožnění zabezpečeného přístupu zaměstnanců k Office 365 z nespravované veřejného terminálu](common-scenarios.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Poskytnutí sdílených tabletů s omezeným použitím pracovníkům, kteří provádějí konkrétní úlohy](common-scenarios.md#issue-limited-use-shared-tablets-to-your-employees)


## <a name="how-does-intune-work"></a>Jak Intune funguje?
Intune je součástí Enterprise Mobility + Security (EMS) sada, která spravuje mobilní zařízení a aplikace od Microsoftu. Úzce se integruje s jinými součástmi řešení EMS, jako je Azure Active Directory (Azure AD) pro účely řízení přístupu a identit, a Azure Information Protection pro účely ochrany dat. Při použití v kombinaci s Office 365 vašim pracovníkům umožňuje, aby byli produktivní na všech zařízeních, a současně chrání informace vaší organizace.

![Obrázek architektury Intune](./media/intunearch_sm.png)

Podívejte se na [větší verzi](./media/intunearchitecture.svg) diagramu architektury Intune.

Způsob využívání funkcí Intune pro správu zařízení a aplikací a ochrany dat EMS závisí na [obchodním problému, který se snažíte řešit](#common-business-problems-that-intune-helps-solve). Příklad:
* Správu zařízení rozhodně využijete, pokud vytváříte fond jednoúčelových zařízení, která mají sdílet pracovníci střídající se na směnách v prodejně.
* O správu aplikací a ochranu dat se můžete opřít, pokud pracovníkům umožníte používat jejich osobní zařízení (BYOD) pro přístup k firemním datům.  
* Pokud zaměstnancům pracujícím s informacemi poskytujete firemní telefony, můžete spoléhat na všechny uvedené technologie.

## <a name="intune-device-management-explained"></a>Vysvětlení správy zařízení v Intune
Správa zařízení Intune využívá protokoly nebo rozhraní API, která jsou k dispozici v mobilních operačních systémech. Zahrnuje úlohy jako:
* Registrace zařízení ke správě, aby vaše IT oddělení mělo seznam zařízení s přístupem k firemním službám
* Konfigurace zařízení, aby splňovala standardy společnosti z hlediska zabezpečení a stavu
* Poskytování certifikátů a profilů Wi-Fi/VPN pro přístup k firemním službám
* Hlášení a měření, jak zařízení dodržují firemní standardy
* Odebírání firemních dat ze spravovaných zařízení  

Někdy se lidé domnívají **řízení přístupu k firemním datům** je funkcí správy zařízení. My to tak nevnímáme, protože to není něco, co by poskytoval mobilní operační systém. Spíše to zajišťuje poskytovatel identity. V našem případě je poskytovatelem identity Azure Active Directory (Azure AD), systém Microsoftu pro správu identity a přístupu.  

Intune se integruje s Azure AD a umožňuje širokou škálu scénářů řízení přístupu. Můžete třeba vyžadovat, aby mobilní zařízení vyhovovalo firemním standardům definovaným v Intune, než může získat přístup k firemní službě, jako je Exchange. Podobně můžete přístup k podnikové službě omezit jenom na konkrétní sadu mobilních aplikací. Můžete třeba přístup k Exchangi Online omezit jenom na Outlook nebo Outlook Mobile.

## <a name="intune-app-management-explained"></a>Vysvětlení správy aplikací v Intune
Pod termínem „správa aplikací“ se myslí:
* Přiřazování mobilních aplikací zaměstnancům
* Konfigurace aplikací pomocí standardních nastavení, která se používají při běhu aplikace
* Řízení způsobů používání a sdílení firemních dat v mobilních aplikacích
* Odebírání firemních dat z mobilních aplikací   
* Aktualizace aplikací
* Hlášení o inventáři mobilních aplikací
* Sledování využití mobilních aplikací

Termín „správa mobilních aplikací“ (MAM) se často používá k označení kterékoli z těchto jednotlivých věcí nebo jejich konkrétních kombinací. Zejména je běžně kombinovat koncepci konfigurace aplikací s koncepcí zabezpečení firemních dat v mobilních aplikacích. Důvodem je, že některé mobilní aplikace nabízejí nastavení, která umožňují konfigurovat jejich funkce zabezpečení dat.

Když mluvíme o konfiguraci aplikací a Intune, máme tím na mysli konkrétně technologie, jako je [konfigurace spravovaných aplikací v systému iOS](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html).

Když Intune použijete s dalšími službami v EMS, můžete organizaci poskytnout zabezpečení mobilních aplikací daleko nad rámec toho, co poskytují mobilní operační systém a samotné mobilní aplikace prostřednictvím konfigurace aplikací. Aplikace, která je spravovaná pomocí EMS, má přístup k širší sadě mobilní aplikace a funkce pro ochranu dat, která zahrnuje:

* [Jednotné přihlašování](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)  
*   [Vícefaktorové ověřování](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication)
* [Podmíněný přístup aplikací – povolení přístupu, pokud mobilní aplikace obsahuje firemní data](app-based-conditional-access-intune.md)
* [Izolování firemních dat od osobních dat uvnitř stejné aplikace](app-protection-policy.md)
* [Zásady ochrany aplikací (PIN, šifrování, uložit jako, schránka atd.)](app-protection-policies.md)
* [Vymazání firemních dat z mobilní aplikace](apps-selective-wipe.md)
* [Podpora správy přístupových práv](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

![Obrázek ukazující úrovně zabezpečení dat správy aplikací](./media/managing-mobile-apps.png)

### <a name="intune-app-security"></a>Zabezpečení aplikací v Intune
Zabezpečení aplikací je součástí správy aplikací, takže když mluvíme o zabezpečení mobilních aplikací v Intune, myslíme tím:
* Jak zajistit, aby se k vašim osobním údajům nedostalo firemní IT oddělení
* Omezení akcí, které můžou uživatelé provádět s firemními informacemi, například kopírování, vyjmutí a vložení, uložení a zobrazení
* Odebrání firemních dat z mobilních aplikací, které se taky označuje jako selektivní vymazání nebo firemní vymazání

Jedním ze způsobů, Intune zajišťuje zabezpečení mobilních aplikací, je prostřednictvím jeho **zásady ochrany aplikací** funkce. Zásady ochrany aplikací využívají identitu Azure AD k izolování firemních dat od osobních. Data, která se přistupuje pomocí firemních přihlašovacích údajů dostanou dodatečnou firemní ochranu.

Například při přihlášení uživatele k zařízení pomocí svých firemních přihlašovacích údajů, jeho firemní identita jim umožní přístup k datům, která jsou jeho osobní identitě. Zásady ochrany aplikací určují, jak se při používání tato firemní data ukládají a sdílejí. Tyto stejné ochrany nepoužívají k datům, která se využívají při přihlášení uživatele do jejich zařízení při jeho osobní identitě. Tímto způsobem IT má kontrolu nad firemní data, zatímco koncový uživatel udržuje kontrolu a soukromí přes jejich osobní údaje.

## <a name="emm-with-and-without-device-enrollment"></a>EMM s registrací a bez registrace zařízení
Většina řešení správy mobility velkých organizací podporuje základní technologie mobilních zařízení a mobilních aplikací. Ty jsou obvykle svázány se zařízením, které je zaregistrované v řešení správy mobilních zařízení (MDM) vaší organizace. Intune podporuje tyto scénáře a navíc také mnoho scénářů „bez registrace“.  

Organizace se liší v rozsahu, v jakém přijímají scénáře „bez registrace“. Některé organizace to používají jako standard. Některé to povolují u doplňkových zařízení, jako jsou osobní tablety. Jiné to nepodporují vůbec. I v tomto posledním případě, kdy organizace vyžaduje, aby všechna zařízení zaměstnanců byla zaregistrovaná v MDM, podporují obvykle scénáře "bez registrace" pro dodavatele, dodavatele a jiná zařízení, která mají zvláštní výjimku.

Můžete dokonce technologii Intune „bez registrace“ používat i na registrovaných zařízeních. Zařízení zaregistrované v MDM může mít třeba ochranu „Otevřít v aplikaci“ poskytovanou mobilním operačním systémem. Ochrana "Otevřít v aplikaci" je funkce Apple iOS, která zabrání otevřít dokument z jedné aplikace, jako je Outlook, do jiné aplikace, jako je Word, pokud obě aplikace nejsou spravované poskytovatelem řešení MDM. stejné. Navíc IT mohou použít zásady ochrany aplikací pro mobilní aplikace spravované pomocí EMS proto na ovládací prvek uložit – jako, nebo k poskytování služby Multi-Factor authentication.

Bez ohledu na postoj vaší organizace k zaregistrovaným a nezaregistrovaným mobilním zařízením a aplikacím obsahuje Intune jako součást EMS nástroje, které vám pomůžou zvýšit produktivitu zaměstnanců a současně ochránit firemní data.

## <a name="microsoft-intune-in-the-azure-portal"></a>Microsoft Intune na portálu Azure Portal

[Azure Portal](https://portal.azure.com) je místo, kde najdete službu Microsoft Intune.

Mezi nejdůležitější prvky prostředí Microsoft Intune na portálu Azure Portal patří:

- Integrovaná konzola pro všechny součásti EMS (Enterprise Mobility + Security)
- Konzola HTML postavená na webových standardech
- Podpora rozhraní Microsoft Graph API pro automatizaci mnoha akcí
- Skupiny Azure Active Directory (AD) pro zajištění kompatibility mezi všemi aplikacemi Azure
- Podpora většiny moderních prohlížečů

Stručný návod pro přizpůsobení prostředí portálu najdete v tématu [Začínáme s Intune na portálu Azure Portal](get-started-azure.md).

> [!NOTE]
> Pokud jste používali dřívější verzi Microsoft Intune, můžou pro vás být užitečné následující informace:
> * Téma [Kde v Azure najdu svoje funkce](ui-changes.md) obsahuje referenční informace, kde můžete vidět konkrétní pracovní postupy a uživatelská rozhraní, která se změnila s přechodem na Azure.
> * V tématu [Skupiny klasického Intune na portálu Azure](groups-get-started.md) je vysvětlené, jaký dopad má přechod na skupiny zabezpečení Azure Active Directory na správu skupin.

### <a name="before-you-start"></a>Než začnete

K použití Intune na portálu Azure Portal potřebujete účet správce a tenanta Intune. [Zaregistrujte si účet](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20), pokud ho ještě nemáte.

### <a name="supported-web-browsers-for-the-azure-portal"></a>Prohlížeče, které portál Azure Portal podporuje

Azure Portal funguje na většině moderních počítačů PC, Mac a tabletech. Mobilní telefony nejsou podporované.
V současnosti se podporují následující prohlížeče:

- Microsoft Edge (nejnovější verze)
- Microsoft Internet Explorer 11
- Safari (nejnovější verze, jen Mac)
- Chrome (nejnovější verze)
- Firefox (nejnovější verze)

Nejnovější informace o podporovaných prohlížečích najdete na portálu [Azure Portal](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices).

## <a name="next-steps"></a>Další postup
* Přečtěte si o některých [běžných způsobech použití Intune](common-scenarios.md).
* Seznamte se s tímto produktem [prostřednictvím 30denní zkušební verze Intune](free-trial-sign-up.md).
* Podrobně se seznamte s [technickými požadavky a možnostmi](supported-devices-browsers.md) služby Intune.
