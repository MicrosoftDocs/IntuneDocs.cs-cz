---
title: "Běžné způsoby použití Intune | Dokumentace Microsoftu"
description: "Uvádí šest z nejčastějších úloh, při kterých Intune pomáhá."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/09/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: robstackmsft
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f8a47bef930e5e194f4543b0532b4585c0ebd5e9
ms.openlocfilehash: 514c1cee1137f6f658b0e887dd4f4a02f1cd0f21


---

# <a name="common-ways-to-use-intune"></a>Běžné způsoby použití Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Než začnete s úkoly implementace, je důležité sladit využívání podnikových mobilních zařízení ve společnosti všemi zúčastněnými stranami s firemními cíli vaší společnosti.  To je důležité v každém případě bez ohledu na to, jestli začínáte využívat své první podnikové řešení pro mobilní zařízení, nebo migrujete z jiného produktu.  

Potřeby se z hlediska využívání mobilních zařízení v podnikovém prostředí dynamicky vyvíjejí a jejich řešení od Microsoftu se v některých případech může lišit od ostatních řešení na trhu. Nejlepším způsobem, jak zajistit soulad s obchodními cíli, je vyjádřit cíle za pomoci scénářů, které chcete pro svoje zaměstnance, partnery a IT oddělení povolit.  

Níže najdete krátký přehled šesti nejběžnějších scénářů, pro které je zásadní využívání Intune, společně s odkazy na další informace o způsobech plánování a nasazení pro každý z nich.

>[!NOTE]
>Chcete vědět, jak IT oddělení Microsoftu využívá Intune k tomu, aby měli zaměstnanci Microsoftu přístup k podnikovým prostředkům na mobilních zařízeních a současně podniková data zůstala chráněná? [Přečtěte si tuto technickou případovou studii](https://www.microsoft.com/itshowcase/Article/Content/588), kde najdete podrobné informace o tom, jak IT oddělení společnosti Microsoft používá Intune a další služby ke správě identit, zařízení, aplikací a dat.  

>[!IMPORTANT]
>Vzhledem k nedávným malwarovým útokům typu „Trident“ na zařízení s iOSem chceme zajistit, aby mobilní zařízení byla aktuální. Proto jsme publikovali blogový příspěvek o [aktualizaci mobilních zařízení pomocí Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/). Najdete v něm informace o různých způsobech, jak vám může Intune pomoct s tím, aby vaše zařízení zůstávala zabezpečená a aktuální.

## <a name="protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Ochrana místních e-mailů a dat, aby je mohli uživatelé bezpečně používat na mobilních zařízeních
Většina strategií z hlediska využívání mobilních zařízení v podnicích začíná plánem zajistit zabezpečený přístup k e-mailům pro zaměstnance s mobilními zařízeními, která se připojují k internetu. Celá řada organizací ještě v dnešní době využívá místní datové a aplikační servery, jako je Microsoft Exchange, které má hostované ve své podnikové síti.

Intune a Microsoft Enterprise Mobility + Security (EMS) poskytují jedinečně integrované [řešení podmíněného přístupu](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) pro Exchange Server, které zajišťuje, aby žádné mobilní aplikace neměly přístup k e-mailu, dokud zařízení není zaregistrované v Intune. To všechno můžete udělat bez nasazení dalšího počítače brány na hranici firemní sítě.

Intune podporuje také povolení přístupu k mobilním aplikacím, které vyžadují zabezpečený přístup k místním datům, třeba serverům obchodních aplikací. To se obvykle provádí pomocí [certifikátů spravovaných službou Intune](/intune/deploy-use/secure-resource-access-with-certificate-profiles) pro řízení přístupu v kombinaci se standardní bránou sítě VPN nebo proxy serverem v hraniční síti, například Microsoft Azure Active Directory Application Proxy.  

V takových případech je možné k podnikovým datům získat přístup jedině po zaregistrování zařízení v systému správy. Po zaregistrování zařízení pak systém pro správu zajišťuje, aby zařízení před přístupem k podnikovým datům splňovala vaše zásady.  Kromě toho můžou [nástroj Intune App Wrapping Tool a sada App SDK](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) pomoct zajistit, aby šlo firemní data využívat jenom v rámci dané podnikové aplikace a nešlo je předat zákaznickým aplikacím nebo službám.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->


## <a name="protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Ochrana vašich e-mailů a dat Office 365, aby je mohli uživatelé bezpečně používat na mobilních zařízeních
Ochrana podnikových dat (e-mailů, dokumentů, rychlých zpráv, kontaktů) v Office 365 je navržena tak, abyste ji mohli co nejjednodušeji nastavit a vaše uživatele nijak neomezovala v práci.

Intune a Microsoft Enterprise Mobility + Security (EMS) poskytují jedinečně integrované řešení podmíněného přístupu, které zajišťuje, že žádní uživatelé, aplikace ani zařízení nebudou mít přístup k datům Office 365, pokud nebudou splňovat požadavky stanovené vaší společností (bylo provedeno [vícefaktorové ověřování](/intune/deploy-use/protect-windows-devices-with-multi-factor-authentication), proběhla registrace do služby Intune, je používána spravovaná aplikace, používá se podporovaná verze OS, byl zadán PIN zařízení, nízký profil rizika pro uživatele atd.).

Mobilní aplikace Office v příslušných obchodech s aplikacemi jsou připravené na vynucování zásad zabránění úniku dat, které můžete nakonfigurovat přes Intune. To vám umožňuje chránit data před sdílením s aplikacemi (třeba s nativními e-mailovými aplikacemi) a umístěními úložiště (třeba Dropboxem), která nespravuje IT. Tato funkce je integrovaná v Office 365 a EMS. Tuto výhodu získáte bez nutnosti nasazovat další infrastrukturu.

Běžnou praxí při nasazování Office 365 je vyžadovat, aby se zařízení registrovala do systému správy, pokud je nutné jejich kompletní nastavení včetně konfigurací podnikových aplikací, certifikátů, Wi-Fi, VPN, což je běžný scénář pro zařízení ve vlastnictví společnosti.  

Pokud ale uživatelé potřebují jenom přístup k podnikovému e-mailu a dokumentům, což často platí pro vlastní zařízení zaměstnanců, můžete vyžadovat, aby používali mobilní aplikace Office (na které jste [aplikovali zásady zabránění úniku podnikových dat](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune)) a úplně se vynechá registrace zařízení.  

V každém případě budou data Office 365 zabezpečena zásadami, které jste definovali.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->


## <a name="offer-a-bring-your-own-device-program-to-all-employees"></a>Nabídněte všem zaměstnancům využívání programu Přineste si vlastní zařízení (BYOD)
Využívání tohoto přístupu v organizacích se těší čím dál větší oblibě. Je to pro ně způsob, jak omezit výdaje na hardware nebo pro zaměstnance rozšířit možnosti využívání mobilních zařízení. V dnešní době mají už skoro všichni vlastní telefon, proč jim tedy nutit další? Hlavní těžkostí vždy bylo přimět zaměstnance, aby si svoje vlastní zařízení zaregistrovali do systému správy, a to kvůli obavám, co by pak IT oddělení na jejich telefonech mohlo vidět nebo co by s nimi mohlo dělat.  

Jestliže registrace zařízení není vhodným řešením, nabízí Intune alternativní BYOD přístup, v rámci kterého se jednoduše [spravují pouze aplikace obsahující podniková data](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune).  Intune chrání podniková data i v případě, že daná aplikace přistupuje jak k podnikovým, tak k osobním datům, což je případ mobilních aplikací Office.  

Z pohledu správce můžete vyžadovat, aby uživatelé pro přístup k Office 365 využívali mobilní aplikace Office. Můžete také pro tyto aplikace nakonfigurovat zásady, které umožní zajistit, aby data zůstala chráněná (třeba šifrováním, ochranou pomocí PIN kódu atd.). Tyto zásady zabraňují úniku dat z nespravovaných aplikací a úložišť, a to jak v rámci těchto aplikací, tak mimo ně. Zásady například zabrání uživateli ve zkopírování textu z podnikového e-mailového profilu do soukromého e-mailového profilu, a to i v případě, že jsou oba profily nakonfigurované v rámci Outlooku Mobile. Podobné konfigurace můžou být nasazené i pro další služby a aplikace, které vaši uživatelé vyžadují v rámci programu BYOD.

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## <a name="issue-corporate-owned-phones-to-your-information-workers"></a>Zajištění telefonů ve vlastnictví podniku pro informační pracovníky
Většina informačních pracovníků je v dnešní době mobilní, což s sebou přináší nutnost, aby byli na těchto mobilních zařízeních stejně produktivní. Tito zaměstnanci potřebují snadný přístup ke všem podnikovým aplikacím a datům, a to kdykoli a bez ohledu na to, kde právě jsou. Je potřeba zajistit zabezpečení podnikových dat a udržet nízké náklady na správu.  

Intune nabízí [řešení hromadného zřizování a správy](/intune/deploy-use/manage-corporate-owned-devices), která jsou integrovaná s hlavními platformami pro správu firemních zařízení, které jsou dnes na trhu, včetně programu Apple Device Enrollment Program a platformy Samsung KNOX pro zabezpečení mobilních zařízení. Centralizované vytváření konfigurací zařízení prostřednictvím služby Intune pomáhá zřizování podnikových zařízení do značné míry zautomatizovat.  

Představte si tuto situaci: dáte zaměstnanci nerozbalenou krabičku s nových iPhonem. Zaměstnanec iPhone zapne a je proveden kroky nastavení specifickými pro vaši firmu, v rámci kterých se musí ověřit. Pro iPhone se v rámci toho nakonfigurují [zásady zabezpečení](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) (třeba zašifrování pevného disku a nastavení PIN kódu zařízení), [profily pro e-mail, Wi-Fi/VPN, certifikát](/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune) a sada standardních [aplikací](/intune/deploy-use/add-apps).

Zaměstnanec pak spustí aplikaci Portál společnosti Intune a přes tu se dostane k volitelným podnikovým aplikacím, které mu společnost zpřístupnila.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## <a name="issue-limited-use-shared-tablets-to-your-task-workers"></a>Pro pracovníky využívající počítač pouze na konkrétní operace používejte sdílené tablety s omezeným použitím
U těchto typů pracovníků je stále rozšířenější používání mobilní technologií. Zaměstnanci v maloobchodech například dnes běžně využívají sdílené tablety.  Ať už se tablety využívají ke zpracování prodeje, nebo k okamžitému zjištění dostupnosti zboží na skladě, umožňují pracovníkům často daleko rychleji reagovat na požadavky zákazníků.

V tomto případě je velmi důležitá jednoduchost uživatelského prostředí. Z uvedeného důvodu jsou tablety obvykle zaměstnancům předávány v režimu omezeného použití, kdy má zaměstnanec možnost na něm využívat pouze jednu jedinou podnikovou aplikaci. Intune vám umožňuje tyto sdílené tablety s [iOS](/intune/deploy-use/ios-policy-settings-in-microsoft-intune#general-configuration-policy-settings) a [Androidem](/intune/deploy-use/android-policy-settings-in-microsoft-intune#general-configuration-policy) hromadně zřizovat, zabezpečit a centrálně spravovat a nakonfigurovat je tak, aby je bylo možné využívat pouze v tomto režimu omezeného použití.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## <a name="enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk"></a>Umožnění zabezpečeného přístupu zaměstnanců k Office 365 z nespravované veřejného terminálu
Někdy budou muset vaši zaměstnanci použít zařízení, aplikace nebo prohlížeče, které nelze spravovat, například veřejné počítače na veletrzích nebo v hotelech.

Máte z nich zaměstnancům povolit přístup k podnikovému e-mailu? Se službami Intune a Microsoft Enterprise Mobility + Security <!--you have choices. The--> můžete jednoduše odpovědět „ne“ tím, že [omezíte přístup k e-mailu na ta zařízení, která jsou spravována vaší organizací](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).  <!-- Alternatively, you can choose to allow limited access to these untrusted computers by requiring multi-factor authentication and only allowing browser access (Outlook Web Access) in a mode where files cannot be downloaded (e.g. email attachments).--> Tím se zajistí, aby zaměstnanec, který prochází přísným ověřením, nenechal firemní data na nějakém nedůvěryhodném počítači.

<!-- Learn more about how to plan and deploy Intune to support kiosks. -->



<!--HONumber=Jan17_HO3-->


