---
ms.openlocfilehash: dc86f2c22410236368753acd4dd3b66698037241
ms.sourcegitcommit: 3c80028fd995675e7664b27d7e4051c9a9d0e669
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/11/2019
ms.locfileid: "57736852"
---

Tato oznámení poskytují důležité informace, které vám pomohou připravit se na budoucí změny Intune a funkce. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Změnit v pracovním postupu registrace pomocí portálu společnosti Intune na zařízení se systémem iOS podnikové ověřování Pomocníka s nastavením <!-- 1927359 -->
Je chystanou změnou v pracovním postupu pro registraci zařízení s Iosem prostřednictvím jednoho z Apple podnikové způsoby registrace zařízení – Apple Configurator, obchodní ředitel společnosti Apple, Apple School Manager nebo Apple zařízení registrace programu (DEP), když pomocí instalačního programu Pomocník pro ověřování. Tato změna platí pouze pro zařízení zaregistrovaná s přidružením uživatele.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Když tuto změnu nasazení ~~března~~ dne, profily registrace v Intune na portálu Azure portal bude aktualizován, takže můžete určit, jak ověřovat zařízení a pokud se zobrazí v aplikaci portál společnosti. Bude Vylepšený pracovní postup registrace zařízení s Iosem pomocí výše uvedených metod. Poznámka:

- Při registraci nového zařízení a ověřování s pomocníkem s nastavením, je budete moci rozhodnout, zda chcete automaticky nasadit aplikaci portál společnosti. Koncoví uživatelé uvidí už "Identifikovat vlastní zařízení" obrazovky a obrazovky "Potvrdit zařízení" v postupem registrace.  
- Na zařízení už zaregistrované prostřednictvím pomocníka prostřednictvím jednoho z metody registrace podnikového zařízení společnosti Apple je nutné provést akci, pokud chcete zapnout zásady podmíněného přístupu. Budete muset nakonfigurovat zásady Konfigurace aplikací s konkrétní xml tak, aby nabízel až do těchto zařízení aplikaci portál společnosti. Pokyny k tomu jsou v blogovém příspěvku v odkazu Další informace. Pokud se rozhodnete tak, aby nabízel portálu společnosti tímto způsobem, koncovým uživatelům se zobrazí už "Identifikovat vlastní zařízení" obrazovky a obrazovky "Potvrdit zařízení" v postupem registrace. 
- Po této změně nasazení, pokud jste nenasadili portál společnosti pomocí konfigurační profil aplikací uvedených výše, a pokud budete ke stažení koncovým uživatelům ukládat aplikace portál společnosti z aplikace, budete můžou zaregistrovat, ale zobrazí chybová zpráva. Nebudou moct používat aplikace pro podmíněný přístup. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Pokud máte v úmyslu používat upravenou pracovní postup, budete chtít aktualizovat označuje, že vaše pokyny pro koncové uživatele:

- Koncoví uživatelé nebudou moci zobrazit dvě obrazovky výše uvedené v postupem registrace. 
- Budete muset přihlásit do aplikace portál společnosti, když se automaticky nasadí a není si ho stáhnout z app storu. 

Můžete teď vytvořit zásady Konfigurace aplikací v případě potřeby během přípravy na tuto změnu. Při zavádění tohoto nového pracovního postupu se zobrazí aktualizovaná registrační profily z konzoly. Také jsme budete informovat o zavedení prostřednictvím Centra zpráv. Potom budete muset udělat tak, aby vaši koncoví uživatelé můžou prostřednictvím programu DEP zaregistrovat prostřednictvím pomocníka s nastavením a portál společnosti můžete použít pro podmíněný přístup.

Najdete v článku podpory blogovém příspěvku v odkazu Další informace pro další podrobnosti o této změně.

#### <a name="additional-information"></a>Další informace 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### <a name="company-portal-changes-for-ios-122-enrollment-in-intune"></a>Změny portálu společnosti pro iOS 12.2 registrace v Intune
Jsme oznámili v MC172534, který Apple oznámil některé změny související s registrací do služby správy mobilních zařízení (MDM) zařízení s Iosem. Tato změna se pravděpodobně projeví ve verzi iOS nárůst 2019. března, stejně jako všechny budoucí iOS verze. Některé aktualizace nyní v aplikaci portál společnosti tak, aby odrážely změny od společnosti Apple. 
 
#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pokud vaši koncoví uživatelé upgradovat svoje zařízení do systému iOS 12.2 a výše, vědět, že je upravený pracovního postupu a že musí podniknout další kroky dokončit registraci do Intune. Po Březnová aktualizace pro Intune tady je co budete dělat-  

- Proces registrace v aplikaci portál společnosti se stáhnout profil správy
- Přejděte na Nastavení > Obecné > profily a hledat red oznámení "BADGE" oznámení
- Vyberte správný profil a klikněte na tlačítko prostřednictvím k instalaci
- Vraťte se do portálu společnosti, aby prošel registrací

Další informace kliknutím získáte podrobné informace o postupem registrace.

Pokud se zruší se tím registrace a třeba novou registraci, zařízení, která jsou už zaregistrované a proveďte upgrade na iOS 12.2 a výše by neměla mít vliv. Prostředí pro registraci na zařízeních s Iosem 12,1 nebo starší nedojde ke změně v této nové verzi společností Apple. Zařízení zaregistrovaná pomocí jednoho nebo metody podnikové registrace od Applu (Device Enrollment Program, Apple School Manager nebo Apple obchodní ředitel) nebude mít vliv.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
By měly vy plánujete provést upgrade, dokumentaci a pokyny pro koncové uživatele. Můžete také nechat helpdesk vědět těchto změn. Budeme vás informovat prostřednictvím naší stránce s novinkami když se tato změna dostane za provozu. 

Pokud chcete využít výhod Zavádíme změny portálu společnosti, požádejte koncové uživatele, aby jejich zařízení po služby Březnová aktualizace pro Intune, když aktualizovat na novou verzi iOS portál společnosti verze aplikace 3.9.0. vydání.

Klikněte na další informace pro podporu blogový příspěvek se snímky obrazovky náhled změn portál společnosti.

Další informace [https://aka.ms/CP_changes_iOS12](https://aka.ms/CP_changes_iOS12)

### <a name="plan-for-change-workflow-changes-for-ios-12-enrollment-in-intune"></a>Plánovaná změna: Změny pracovního postupu pro iOS 12 registrace v Intune
Apple oznámil některé změny související s registrací do služby správy mobilních zařízení (MDM) zařízení s Iosem. Změny se pravděpodobně projeví v spring 2019 verzi iOS, jakož i všechny budoucí iOS verze.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pokud vaši koncoví uživatelé upgradovat svoje zařízení na této nové verzi iOS 12 udělali na jaře, vědět, že je upravený pracovního postupu a budete muset provést další kroky dokončit registraci do Intune. Když Apple zavádí tyto změny, koncoví uživatelé budou muset:

- Proces registrace v aplikaci portál společnosti se stáhnout profil správy
- Přejděte na Nastavení > Obecné > profily
- Vyberte správný profil a klikněte na tlačítko prostřednictvím k instalaci
- Vraťte se do portálu společnosti, aby prošel registrací 

Pokud se zruší se tím registrace a třeba novou registraci, zařízení, která jsou už zaregistrovaná a upgrade na novou verzi iOS by neměly být ovlivněny.

Prostředí pro registraci na zařízeních s Iosem 12,1 nebo starší nedojde ke změně v této nové verzi společností Apple.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
By měly vy plánujete provést upgrade, dokumentaci a pokyny pro koncové uživatele. Můžete také nechat helpdesk vědět těchto změn. Budeme vás informovat prostřednictvím Centra zpráv a naší stránce s novinkami když se tato změna dostane za provozu.

#### <a name="additional-information"></a>Další informace
[Podpora blogový příspěvek se snímky obrazovky a video s postupem registrace očekávané](https://aka.ms/iOS_enrollment_changes).

### <a name="plan-for-change-user-experience-update-to-intune-company-portal-app-for-ios"></a>Plánovaná změna: Aktualizaci uživatelského prostředí aplikace portál společnosti Intune pro iOS
Jsme rádi, že Intune bude brzy k vydání důležitou aktualizaci uživatelského prostředí pro aplikaci portál společnosti pro iOS sdílet. Aktualizace se funkce vizuální Design domovské stránky s rozšířené filtry a rychlejší přístup k aplikací a knih.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Tato činnost koncového uživatele aktualizovat, zatímco Správa iOS aktuální funkce aplikace portál společnosti, bude funkce:
- Domovská stránka s vzhled nativní aplikace pro iOS 
- Možnosti filtrování obsahu seznamy a vyhledávání, včetně možnosti filtrovat podle typu obsahu (aplikace nebo e-knihy) a dostupnost (Správa zařízení povinné nebo dostupné bez registrace)
- Schopnost Hledat v e-knihy
- Historie hledání pro aplikace a e-knihy

Pokud jste součástí programu Apple TestFlight, budete upozorněni o předběžnou verzi aktualizované iOS v Intune aplikaci portál společnosti, až bude k dispozici. Pokud si nejste součástí programu Apple TestFlight, není příliš pozdě pro registraci. Registrace vám umožní použít aktualizované aplikace portál společnosti, než je k dispozici koncovým uživatelům. Budete také zadáte zpětnou vazbu přímo s týmem Intune.  

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Není nutné provádět žádnou akci; Tyto změny budou vydané v iOS nadcházející verzi CP aplikace. 

#### <a name="additional-information"></a>Další informace
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)


### <a name="reminder-removal-of-existing-exchange-online-to-intune-connectors----3105122---"></a>Připomenutí: Odebrání existující Exchange Online, aby konektory Intune <!-- 3105122 -->
V MC165575 jsme oznámili, že jsme by odebírat Exchange Online funkce "Službami" konektor Intune v příští aktualizaci. S aktualizací update února do služby Intune Zakážeme tlačítko Nastavit nové konektory. Plánujeme odebrat všechny stávající Exchange Online, aby konektory Intune v březnu 2019.
 
#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Tuto zprávu jste obdrželi, protože naše záznamy ukazují, že využíváte funkci "Službami" konektor ve vašem prostředí. "Službami" konektor podporuje Intune správu Exchange Active Sync jenom zařízení pro Exchange Online a nepodporuje místní infrastrukturu. Tento konektor vzhledem ke způsobu se zobrazovat v konzole, se zobrazí nezbytné pro podmíněný přístup (CA), když ve skutečnosti není potřeba pro certifikační Autoritu. Pravděpodobně používáte tento konektor porozumět využití služby Exchange Online, než uplatňováním podmíněného přístupu. Tyto informace již poskytuje Centrum pro správu Microsoftu 365. Tady najdete poskytuje sestavy o využití pro Exchange Online včetně aplikace zadáte, se používají pro 7 až 180 dní. Další informace najdete v části [sestavy Office 365 v Centru pro správu – používání aplikace e-mailů](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage?view=o365-worldwide).  
 
Pokud používáte tento konektor ve vašem prostředí, nebude schopna monitorovat nebo vymazat Exchange Active Sync jenom zařízení v Intune až v únoru byly zakázány konektory. Během této změny neexistuje žádné předpokládaný dopad na koncové uživatele.
 
#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Pokud máte Service to Service connector nastavit a mít Exchange Active Sync jenom zařízení, přepněte na jiné metody správy zařízení. Máte následující možnosti:

- Registrace zařízení do správy mobilních zařízení (MDM) 
- Použití zásad ochrany aplikací Intune ke správě svých zařízení 
- Použití ovládacích prvků systému Exchange, jak je uvedeno v dokumentaci k [zde](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online) 

#### <a name="additional-information"></a>Další informace  
https://docs.microsoft.com/intune/exchange-service-connector-configure




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
