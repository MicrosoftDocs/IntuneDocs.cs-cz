---
title: zahrnout soubor
description: zahrnout soubor
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 073115d33f9a4f22fe3706ef15860c2a8d8a68ee
ms.sourcegitcommit: 69aaf89140f82f344404e75a69dc59d8a1585b10
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675489"
---
Tato oznámení poskytují důležité informace, které vám pomohou připravit se na budoucí změny Intune a funkce. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Změnit v pracovním postupu registrace pomocí portálu společnosti Intune na zařízení se systémem iOS podnikové ověřování Pomocníka s nastavením <!-- 1927359 -->
Je chystanou změnou v pracovním postupu pro registraci zařízení s Iosem prostřednictvím jednoho z Apple podnikové způsoby registrace zařízení – Apple Configurator, obchodní ředitel společnosti Apple, Apple School Manager nebo Apple zařízení registrace programu (DEP), když pomocí instalačního programu Pomocník pro ověřování. Tato změna platí pouze pro zařízení zaregistrovaná s přidružením uživatele.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Když tuto změnu nasazení ~~března~~ dne, profily registrace v Intune na portálu Azure portal bude aktualizován, takže můžete určit, jak ověřovat zařízení a pokud se zobrazí v aplikaci portál společnosti. Bude Vylepšený pracovní postup registrace zařízení s Iosem pomocí výše uvedených metod. 

- Při registraci nového zařízení a ověřování s pomocníkem s nastavením, je budete moci rozhodnout, zda chcete automaticky nasadit aplikaci portál společnosti. Koncoví uživatelé uvidí už "Identifikovat vlastní zařízení" obrazovky a obrazovky "Potvrdit zařízení" v postupem registrace.  
- Na zařízení už zaregistrované prostřednictvím pomocníka prostřednictvím jednoho z metody registrace podnikového zařízení společnosti Apple je nutné provést akci, pokud chcete zapnout zásady podmíněného přístupu. Budete muset nakonfigurovat zásady Konfigurace aplikací s konkrétní xml tak, aby nabízel až do těchto zařízení aplikaci portál společnosti. Pokyny k tomu jsou v blogovém příspěvku v odkazu Další informace. Pokud se rozhodnete tak, aby nabízel portálu společnosti tímto způsobem, koncovým uživatelům se zobrazí už "Identifikovat vlastní zařízení" obrazovky a obrazovky "Potvrdit zařízení" v postupem registrace. 
- Po této změně nasazení, pokud jste nenasadili portál společnosti pomocí konfigurační profil aplikací uvedených výše, a pokud budete ke stažení koncovým uživatelům ukládat aplikace portál společnosti z aplikace, můžou zaregistrovat, ale zobrazí chybová zpráva. Nebudou moct používat aplikace pro podmíněný přístup. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Pokud máte v úmyslu používat upravenou pracovní postup, budete chtít aktualizovat označuje, že vaše pokyny pro koncové uživatele:

- Koncoví uživatelé nebudou moci zobrazit dvě obrazovky výše uvedené v postupem registrace. 
- Budete muset přihlásit do aplikace portál společnosti, když se automaticky nasadí a není si ho stáhnout z app storu. 

Můžete teď vytvořit zásady Konfigurace aplikací v případě potřeby během přípravy na tuto změnu. Při zavádění tohoto nového pracovního postupu se zobrazí aktualizovaná registrační profily z konzoly. Také jsme budete informovat o zavedení prostřednictvím Centra zpráv. Potom budete muset udělat tak, aby vaši koncoví uživatelé můžou prostřednictvím programu DEP zaregistrovat prostřednictvím pomocníka s nastavením a portál společnosti můžete použít pro podmíněný přístup.

Najdete v článku podpory blogovém příspěvku v odkazu Další informace pro další podrobnosti o této změně.

#### <a name="additional-information"></a>Další informace 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)

### <a name="plan-for-change-user-experience-update-to-intune-company-portal-app-for-ios"></a>Plánovaná změna: Aktualizaci uživatelského prostředí aplikace portál společnosti Intune pro iOS
Jsme rádi, že Intune bude brzy k vydání důležitou aktualizaci uživatelského prostředí pro aplikaci portál společnosti pro iOS sdílet. Aktualizace se funkce vizuální Design domovské stránky s rozšířené filtry a rychlejší přístup k aplikací a knih.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Tato činnost koncového uživatele aktualizovat, zatímco Správa iOS aktuální funkce aplikace portál společnosti, bude funkce:
- Domovská stránka s vzhled nativní aplikace pro iOS 
- Možnosti filtrování obsahu seznamy a vyhledávání, včetně možnosti filtrovat podle typu obsahu (aplikace nebo e-knihy) a dostupnost (Správa zařízení povinné nebo dostupné bez registrace)
- Schopnost Hledat v e-knihy
- Historie hledání pro aplikace a e-knihy

Pokud jste součástí programu Apple TestFlight, budete upozorněni o předběžnou verzi aktualizované iOS v Intune aplikaci portál společnosti, až bude k dispozici. Pokud si nejste součástí programu Apple TestFlight, není příliš pozdě pro registraci. Registrace vám umožní použít aktualizované aplikace portál společnosti, než je k dispozici koncovým uživatelům. Můžete také poskytnout zpětnou vazbu přímo s týmem Intune.  

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Není nutné provádět žádnou akci; Tyto změny budou vydané v iOS nadcházející verzi CP aplikace. 

#### <a name="additional-information"></a>Další informace
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)

### <a name="check-your-delay-visibility-of-software-updates-setting-in-intune"></a>Zkontrolujte nastavení "Zpoždění viditelnost aktualizací softwaru" v Intune 

Jsme oznámili v MC171466, který jsme se přesouvat několik nastavení v konzole. Při Březnové aktualizaci do Intune úplně Odebereme nastavení "Zpoždění viditelnost softwarových aktualizací" v okně zásad aktualizace iOS. Tím nedojde ke změně způsobu, jakým vaše plánované aktualizace, ale může ovlivnit, jak dlouho je zpožděno Přehled aktualizace pro koncové uživatele. Budete muset provést akci do konce dne, pokud použijete toto nastavení. 

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Po aktualizaci služby Intune. února můžete si všimnout, že toto nastavení se zobrazí, že v profilech omezení zařízení v konzole a v iOS aktualizovat zásady v okně aktualizace softwaru. Až se tato změna projeví v konzole, zde je, co budete muset provést.

- Pro existující zásady aktualizací pro iOS: Pokud máte vlastní nakonfigurovat toto nastavení na jinou hodnotu než výchozí hodnota 30 dnů a vaší existující konfigurace pro nastavení viditelnosti zpoždění k pokračování používání na konci dne, budete muset vytvořit nový iOS profil omezení zařízení. Tady bude nutné mít stejné hodnoty jako existující zásady aktualizace Iosu a zacílit na stejné skupiny nastavení viditelnosti zpoždění. Po Březnové aktualizaci služby se již budete moci upravit hodnoty pro toto nastavení v existující zásady aktualizací pro iOS, protože se již nebudou viditelné v tomto okně. Můžete nakonfigurovat toto nastavení v nové profily místo.
  Pokud hodnota pro počet dní, můžete pozdržet viditelnost neodpovídá v obou umístěních nakonfigurované nastavení vlastní hodnoty, zpoždění viditelnost nastavení nebude fungovat, a koncovým uživatelům se zobrazí aktualizace na svých zařízeních, jako je k dispozici. Může to mít minimální vliv pro většinu zákazníků, protože ostatní nastavení v okně zásady aktualizace softwaru vždy převzal prioritu Toto nastavení v konzole.
- Pro nové zásady aktualizací pro iOS: Pokud se pokusíte vytvořit nové zásady v okně aktualizace softwaru po aktualizaci služby Intune. února, zobrazí se toto nastavení nejde aktivovat. Zobrazí se vám Poznámka: v konzole, pokud budete chtít odložit viditelnost aktualizací přesměrování do okna pro konfiguraci zařízení.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Není nutné provádět akci, pokud toto nastavení nepoužívají nebo nechcete, aby zpoždění viditelnost aktualizací softwaru pro koncové uživatele.

Pokud chcete zpoždění viditelnost aktualizace, spusťte konfiguraci nastavení v nové profily konfigurace zařízení v okně v části v rámci omezení zařízení > Obecné. Pokud máte toto vlastní nastavení nakonfigurovaná v Iosu existující zásady aktualizace, vytvořte nový profil omezení zařízení ekvivalentní se stejnou hodnotou pro "days" zpoždění Přehled aktualizace pro vaše uživatele, po z února aktualizací nebo před březnovém zavede. 

Můžete chtít aktualizovat vaše IT Pro pokyny a informujte helpdesk.

Najdete v našem blogu podpory podrobnosti o tom, jak nakonfigurovat toto nastavení můžete publikovat na další informace.

#### <a name="additional-information"></a>Další informace 
[https://aka.ms/Delay_visibility_setting_iOS](https://aka.ms/Delay_visibility_setting_iOS)

### <a name="plan-for-change-upcoming-fix-for-windows-10-email-profiles-in-intune---3904031--"></a>Plánovaná změna: Chystané opravě pro Windows 10 e-mailové profily v Intune <!--3904031-->
Aktualizujeme tak, jak Intune zapíše e-mailové profily pro Windows 10 v dubnu aktualizace služby Intune k opravě chyby a aby bylo zajištěno, že se e-mailové profily pokračovat v práci v budoucích verzích Windows 10. Se akce, které je potřeba provést po nasazení této opravy.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Tato změna ovlivní Pokud používáte Windows 10 e-mailových profilů pomocí
- Nativní klient e-mailu na stolních počítačů s Windows 10 nebo
- E-mailového klienta Outlook na Windows 10 Mobile

To má vliv i zákazníky Intune samostatnou a hybridní správy mobilních zařízení (MDM).

Po aktualizaci dubna vidíme, budete muset znovu vytvořit tyto profily v konzole Intune (v konzole správce nástroje Configuration Manager, pokud používáte hybridní MDM).

Pokud neprovedete akce, zde je, co uvidíte pro profily vytvořené před aktualizací dne:

- Existující e-mailové profily se zobrazí v chybovém stavu v konzole pro Intune nebo v konzole pro správu nástroje Configuration Manager, ale koncoví uživatelé budou mít dál přístup k e-mailu. Po zavádění následné aktualizace Windows nebudou fungovat těchto profilů. Koncoví uživatelé na zařízeních s cílem těchto profilů ztratí přístup k e-mailu.
- Úpravy profilů po. dubna se neprojeví v cílových zařízení.
- Selektivní vymazání nebude fungovat pro odebrání těchto profilů i po opravy nasazení v dubnu na trh.

Je-li provést akci a znovu vytvořte e-mailové profily, koncoví uživatelé muset projít kroky, které jsou podobné těm, při prvním nasazení e-mailový profil. E-mailu bude blokovat synchronizaci, dokud nepřijme aktualizace, která se použije nový profil.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Je potřeba provést akci, až po opravy nasazení aktualizace. dubna. Budeme pro vás prostřednictvím Centra zpráv když tuto změnu dostane za provozu, abyste je mohli začít znovu vytvořit vaše profily v Intune.

Pokud používáte Windows 10 e-mailové profily v Intune, budete muset provést následující kroky:

1. Zachycení existujících nastavení profilu Windows 10
2. Zrušit nebo odstranit existující profily
3. Vytváření nových profilů pomocí zachycené nastavení a přiřaďte nové profily ke stejným skupinám

Budete muset informovat koncové uživatele a nechat helpdesk vědět této změny. Najdete podporu blogový příspěvek na další informace o podrobnosti o chybě a pokyny k opakovaným vytvářením těchto profilů.

#### <a name="additional-information"></a>Další informace
https://aka.ms/Win10EmailProfiles

