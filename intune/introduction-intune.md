---
title: Co je Microsoft Intune
description: "Zjistěte, jak Intune v rámci řešení Enterprise Mobility + Security funguje jako součást pro správu mobilních zařízení (MDM) a správu mobilních aplikací (MAM) a jak vám pomůže ochránit firemní data."
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
ms.openlocfilehash: 4946404a4bdb4968c47904549a581c9c39f6e9e0
ms.sourcegitcommit: bb1a1e4e0bc26543a9c8fb52cb208e298c6b8e3f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/19/2017
---
# <a name="what-is-intune"></a>Co je Intune?

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Intune je cloudová služba v oblasti správy mobility velkých organizací (EMM), která umožňuje, aby vaši pracovníci byli produktivní, a současně chrání vaše firemní data. Intune vám umožňuje:
* Spravovat mobilní zařízení, která vaši pracovníci používají pro přístup k datům společnosti
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
Intune je součást řešení Enterprise Mobility + Security (EMS), která slouží ke správě mobilních zařízení a aplikací. Úzce se integruje s jinými součástmi řešení EMS, jako je Azure Active Directory (Azure AD) pro účely řízení přístupu a identit, a Azure Information Protection pro účely ochrany dat. Při použití v kombinaci s Office 365 vašim pracovníkům umožňuje, aby byli produktivní na všech zařízeních, a současně chrání informace vaší organizace.

![Obrázek architektury Intune](./media/intunearch_sm.png)

Podívejte se na [větší verzi](./media/intunearchitecture.svg) diagramu architektury Intune.

Způsob využívání funkcí Intune pro správu zařízení a aplikací a ochrany dat EMS závisí na [obchodním problému, který se snažíte řešit](#common-business-problems-that-intune-helps-solve). Například:
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

Někdy se lidé domnívají, že **řízení přístupu k firemním datům** je funkcí správy zařízení. My to tak nevnímáme, protože to není něco, co by poskytoval mobilní operační systém. Spíše to zajišťuje poskytovatel identity. V našem případě je poskytovatelem identity Azure Active Directory (Azure AD), systém Microsoftu pro správu identity a přístupu.  

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

Termín „správa mobilních aplikací“ (MAM) se často používá k označení kterékoli z těchto jednotlivých věcí nebo jejich konkrétních kombinací. Lidé si především často spojují koncepci konfigurace aplikací s koncepcí zabezpečení firemních dat v mobilních aplikacích. Důvodem je, že některé mobilní aplikace nabízejí nastavení, která umožňují konfigurovat jejich funkce zabezpečení dat.

Když mluvíme o konfiguraci aplikací a Intune, máme tím na mysli konkrétně technologie, jako je [konfigurace spravovaných aplikací v systému iOS](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html).

Když Intune použijete s dalšími službami v EMS, můžete organizaci poskytnout zabezpečení mobilních aplikací daleko nad rámec toho, co poskytují mobilní operační systém a samotné mobilní aplikace prostřednictvím konfigurace aplikací. Aplikace, která je spravovaná pomocí EMS, má přístup k širší sadě ochran mobilních aplikací a dat, která zahrnuje:

* [Jednotné přihlašování](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)  
*   [Vícefaktorové ověřování](https://docs.microsoft.com/multi-factor-authentication/multi-factor-authentication)
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

Intune zajišťuje zabezpečení mobilních aplikací mimo jiné prostřednictvím funkce **zásad ochrany aplikací**. Zásady ochrany aplikací využívají identitu Azure AD k izolování firemních dat od osobních. Data, ke kterým se přistupuje pomocí firemních přihlašovacích údajů, dostanou dodatečnou firemní ochranu.

Když se například uživatel ke svému zařízení přihlásí pomocí firemních přihlašovacích údajů, jeho firemní identita mu umožní přístup k datům, která jsou jeho osobní identitě odepřená. Zásady ochrany aplikací určují, jak se při používání tato firemní data ukládají a sdílejí. Na data, ke kterým uživatel přistupuje po přihlášení k zařízení pomocí své osobní identity, se stejné ochrany nepoužívají. Tímto způsobem má IT kontrolu nad firemními daty, zatímco koncový uživatel si udržuje kontrolu a soukromí ve vztahu k osobním datům.

## <a name="emm-with-and-without-device-enrollment"></a>EMM s registrací a bez registrace zařízení
Většina řešení správy mobility velkých organizací podporuje základní technologie mobilních zařízení a mobilních aplikací. Ty jsou obvykle svázány se zařízením, které je zaregistrované v řešení správy mobilních zařízení (MDM) vaší organizace. Intune podporuje tyto scénáře a navíc také mnoho scénářů „bez registrace“.  

Organizace se liší v rozsahu, v jakém přijímají scénáře „bez registrace“. Některé organizace to používají jako standard. Některé to povolují u doplňkových zařízení, jako jsou osobní tablety. Jiné to nepodporují vůbec. I v tomto posledním případě, kdy organizace vyžaduje, aby všechna zařízení zaměstnanců byla zaregistrovaná v MDM, se scénáře „bez registrace“ zpravidla podporují pro dodavatele a jiná zařízení, která mají zvláštní výjimku.

Můžete dokonce technologii Intune „bez registrace“ používat i na registrovaných zařízeních. Zařízení zaregistrované v MDM může mít třeba ochranu „Otevřít v aplikaci“ poskytovanou mobilním operačním systémem. Ochrana „Otevřít v aplikaci“ je funkce iOS, která neumožňuje otevřít dokument z jedné aplikace (jako je Outlook) do jiné aplikace (jako je Word), pokud obě aplikace nejsou spravované poskytovatelem řešení MDM. Kromě toho může IT oddělení použít zásady ochrany aplikací na mobilní aplikace spravované pomocí EMS proto, aby řídilo možnost „uložit jako“ nebo zajistilo vícefaktorové ověřování.

Bez ohledu na postoj vaší organizace k zaregistrovaným a nezaregistrovaným mobilním zařízením a aplikacím obsahuje Intune jako součást EMS nástroje, které vám pomůžou zvýšit produktivitu zaměstnanců a současně ochránit firemní data.



### <a name="next-steps"></a>Další kroky
* Přečtěte si o některých [běžných způsobech použití Intune](common-scenarios.md).
* Seznamte se s tímto produktem [prostřednictvím 30denní zkušební verze Intune](free-trial-sign-up.md).
* Podrobně se seznamte s [technickými požadavky a možnostmi](supported-devices-browsers.md) služby Intune.
