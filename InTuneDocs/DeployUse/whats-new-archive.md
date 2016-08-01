---
title: Archiv novinek | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 805dfa1eeb81f4407066e27f203f315451937f8b
ms.openlocfilehash: acf502bdf73176450157535577047c9428aabfd1


---
## Prosinec 2015
### Změny a aktualizace Portálu společnosti Microsoft
V této verzi došlo k následujícím změnám Portálu společnosti.

**Aplikace Portál společnosti pro Android**

K zajištění souladu s novými požadavky Googlu se provedly následující změny. Na zařízeních se systémem Android 6.0 a vyšším se uživatelům zobrazují dvě nové zprávy:
* Povolit pro Portál společnosti telefonování a správu telefonních hovorů?
* Povolit pro Portál společnosti přístup k fotkám, médiím a souborům ve vašem zařízení?

Podrobnosti o těchto dvou zprávách najdete v následujících tabulkách.



Text zprávy  |Povolit pro Portál společnosti telefonování a správu telefonních hovorů?  
---------|---------
Význam zprávy     |  Povoluje odeslat IMEI a telefonní číslo zařízení uživatele službě Intune a zobrazit tyto informace v konzole pro správu na stránce Hardware.   </br></br>**POZNÁMKA: Aplikace Portál společnosti nikdy netelefonuje ani nespravuje telefonní hovory!** Text zprávy je pod kontrolu Googlu a nejde ho změnit. </br></br>Pokud chcete zobrazit stránku **Hardware**, použijte možnosti **Skupiny** > **Všechna mobilní zařízení** > **Zařízení**. Vyberte zařízení uživatele a pak použijte možnosti **Zobrazit vlastnosti** > **Hardware**.    
Kde a kdy se zpráva zobrazí  | Zpráva se zobrazí, když se uživatel poprvé přihlásí k aplikaci Portál společnosti a začne registrovat svoje zařízení.|         
Co se stane, když uživatel povolí přístup  |  IMEI a telefonní číslo zařízení se zobrazí v konzole pro správu na stránce Hardware. |         
Co se stane, když uživatel přístup odepře     | Může i dál používat aplikaci Portál společnosti a registrovat zařízení, ale IMEI a telefonní číslo jeho zařízení se na stránce Hardware v konzole pro správu nezobrazí.       </br></br> Při druhém přihlášení k aplikaci Portál společnosti po odepření přístupu se ve zprávě zobrazí zaškrtávací políčko **Příště se už neptat**, takže uživatel může určit, že se tato zpráva už nebude zobrazovat.</br></br>Pokud uživatel povolí přístup, ale později ho odepře, tato zpráva se zobrazí při přihlášení k aplikaci Portál společnosti, které následuje po registraci zařízení.</br></br>Pokud se uživatelé rozhodnou povolit přístup později, mohou přejít na **Nastavení** > **Aplikace** > **Portál společnosti** > **Oprávnění** > **Telefon** a toto oprávnění zapnout.
Další informace     |  Pro vaše uživatele: [Přihlášení do aplikace Portál společnosti](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>Pro profesionály v oblasti IT: Informace v této tabulce jsou uvedené taky v části [Jak uživatelům pomoct pochopit zprávy aplikace Portál společnosti](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   

Text zprávy  |Povolit pro Portál společnosti přístup k fotkám, médiím a souborům ve vašem zařízení?  
---------|---------
Význam zprávy     |  Povoluje, aby zařízení zapsalo datové protokoly na kartu SD zařízení, která umožňuje přesunutí protokolů pomocí kabelu USB.   </br></br>**POZNÁMKA: Aplikace Portál společnosti nikdy nemá přístup k fotografiím, médiím a souborům uživatele.** Text zprávy je pod kontrolu Googlu a nejde ho změnit.     
Kde a kdy se zpráva zobrazí  | Zpráva se zobrazí, když uživatel klepnutím na **Odeslat data** odešle datové protokoly příslušnému správci IT.|         
Co se stane, když uživatel povolí přístup  |  Protokoly se zkopírují na kartu SD. |         
Co se stane, když uživatel přístup odepře     | Může i dál posílat datové protokoly, ale tyto protokoly se nezkopírují na kartu SD zařízení.       </br></br> Při druhém přihlášení k aplikaci Portál společnosti po odepření přístupu se ve zprávě zobrazí zaškrtávací políčko **Příště se už neptat**, takže uživatel může určit, že se tato zpráva už nebude zobrazovat.</br></br>Pokud uživatel povolí přístup, ale později ho odepře, tato zpráva se zobrazí při příštím pokusu o odeslání protokolu.</br></br>Pokud se uživatelé rozhodnou povolit přístup později, mohou přejít na **Nastavení** > **Aplikace** > **Portál společnosti** > **Oprávnění** > **Úložiště** a toto oprávnění zapnout.
Další informace     |  Pro vaše uživatele: [Odeslání protokolů s diagnostickými daty e-mailem vašemu správci IT](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>Pro profesionály v oblasti IT: Informace v této tabulce jsou uvedené taky v části [Jak uživatelům pomoct pochopit zprávy aplikace Portál společnosti](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   


**Aplikace Portál společnosti pro iOS**
* Uživatelé teď můžou k odesílání diagnostických protokolů správci IT používat Microsoft Outlook nebo další poštovní aplikace. Dřív šlo použít jenom nativní aplikaci.
* Vylepšila se podpora programu DEP (Device Enrollment Program)  společnosti Apple a registrovaných podnikových zařízení. Podrobnosti najdete v tématu [Při pokusu o registraci se zobrazí výzva k identifikaci vašeho zařízení](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* V seznamu registrovaných zařízení uživatele se teď vedle zařízení, které uživatel právě používá, zobrazí zelené zaškrtnutí. Před přidáním tohoto zaškrtnutí uživatelé nemohli s jistotou určit, které registrované zařízení používají.

**Aplikace Portál společnosti pro Windows**

Microsoft automaticky shromažďuje anonymní informace o výkonu a využití portálu společnosti za účelem zlepšení svých produktů a služeb. Koncoví uživatelé můžou na svém zařízení shromažďování dat vypnout v nastavení dat o využití, ale správci nemají nad shromažďováním dat žádnou kontrolu a nemůžou toto nastavení koncového uživatele nijak změnit.



## Listopad 2015
### Správa aplikací
Intune podporuje zásady správy mobilních aplikací (MAM), které můžou pomoct zabránit v úniku firemních dat do uživatelských aplikací nebo služeb. Dřív se tyto zásady vynucovaly jenom v mobilních aplikacích spuštěných na zařízeních, která byla zároveň zaregistrovaná do správy mobilních zařízení (MDM) ve službě Intune.

V rámci aktualizace v tomto měsíci ale Intune rozšiřuje svoje funkce MAM na nové třídy zařízení. Vedle zařízení zaregistrovaných ve službě Intune teď můžete vynucovat zásady MAM i na těchto zařízeních:
* Zařízení nespravovaná žádným řešením správy mobilních zařízení (MDM)
* Zařízení nezaregistrovaná v žádném systému správy zařízení, většinou vlastní zařízení uživatelů

Další informace o těchto nových funkcích MAM najdete v těchto příspěvcích na blogu:
* [Zvýšení produktivity spravovaných mobilních zařízení](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Nové možnosti sady Enterprise Mobility](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Kromě toho existují také další zajímavosti a funkce o funkcích MAM ve službě Intune:
* Podniková data jsou v aplikacích určených pro Intune, včetně aplikací Office Mobile, aplikací jiných výrobců, které používají sadu Intune SDK, a obchodních aplikací začleněných do služby Intune, izolovaná od uživatelských dat.
* Podniková data se dají sdílet (**vyjmout/kopírovat/vložit**) v různých podnikových aplikacích a zároveň je možné zabránit jejich sdílení v osobních aplikacích. Další informace najdete v článku [Jak zásady MAM chrání data aplikací](https://technet.microsoft.com/library/mt627825.aspx). Ukázkový scénář [Použití aplikace Microsoft Word k pracovním a osobním úkolům](https://technet.microsoft.com/library/mt627827.aspx) vysvětluje, jak se dá zabránit sdílení podnikových dat v osobních aplikacích.
* Používají se zásady prevence ztráty klíčových dat, jako je kód PIN pro jednotlivé aplikace, ovládací prvky funkce Uložit jako a spravované sdílení dat mezi aplikacemi. Seznam všech zásad najdete v tématu [Vytvoření a nasazení zásad správy mobilních aplikací pomocí Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Těmito novými funkcemi jsou vybavené aplikace Word, Excel, PowerPoint, Outlook, OneNote a OneDrive pro firmy, takže se dají spravovat s registrací zařízení nebo bez ní. Standardní aplikace Office v obchodě Apple Store nebo Google Store mají nativně vestavěné funkce ochrany proti ztrátě dat a nevyžadují zabalení aplikace ani zkušební načtení před prodejem.
* O zahájení práce si můžete přečíst v tématu [Začínáme se zásadami správy mobilních aplikací na portálu Azure](https://technet.microsoft.com/library/mt627830.aspx). Pokud chcete zjistit, jak nakonfigurovat a nasadit zásady správy mobilních aplikací, přečtěte si téma [Vytvoření a nasazení zásad správy mobilních aplikací pomocí Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Pokud se koncoví uživatelé přihlásí do aplikace pomocí firemních přihlašovacích údajů, funkce ochrany proti ztrátě dat se nastaví automaticky. Téma [Činnost koncových uživatelů pro aplikace přidružené k zásadám správy mobilních aplikací Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx) obsahuje ukázkové scénáře přístupu k OneDrivu na zařízeních se systémy iOS a Android.
* Funguje na zařízeních se systémy iOS a Android.

Do seznamu [aplikací Microsoftu, které podporují zásady správy mobilních aplikací v Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx), přibyly nejnovější aplikace.

### Správa zařízení
 **Správa zařízení s Mac OS X** Intune teď umožňuje registraci a správu zařízení s Mac OS X. Se zařízeními s Mac OS X můžete provádět tyto úlohy:
* Registrovat zařízení pro správu pomocí Intune. Další informace najdete v tématu [Nastavení správy pro iOS a Mac pomocí Microsoft Intune](https://technet.microsoft.com/library/dn408185.aspx).
* Ovládat nastavení zařízení pomocí zásad obecné konfigurace. Informace najdete v tématu [Nastavení zásad konfigurace pro Mac OS X v Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx).
* Nasadit vytvořené nastavení systému Mac OS X pomocí nástroje Apple Configurator. Informace najdete v tématu [Nastavení vlastních zásad pro Mac OS X v Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx).
* Sestavit inventář hardwaru a softwaru ze zařízení s Mac OS X. Informace najdete v tématu [Seznámení se zařízeními s inventářem v Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx).
* Spustit nové sestavy, které zobrazují podrobnosti o spravovaných zařízeních se systémem Mac OS X. Informace najdete v tématu [Pochopení operací Microsoft Intune pomocí sestav](https://technet.microsoft.com/library/dn646977.aspx).

**Nové nastavení prohlížeče Edge pro zařízení s Windows 10** Do zásad obecné konfigurace systému Windows 10 přibyla nová nastavení, která umožňují spravovat nastavení a funkce prohlížeče Microsoft Edge. Informace najdete v tématu [Nastavení zásad konfigurace Windows 10 v Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx).

**E-mailové profily** Přibyla nová zásada e-mailových profilů pro stolní počítače s Windows 10 a mobilní zařízení s Windows 10. Informace najdete v tématu [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](https://technet.microsoft.com/library/dn646984.aspx).

**Nová nastavení zásad dodržování předpisů** Do seznamu zásad dodržování předpisů přibyla tato nová nastavení zabezpečení a systémových zásad:
* Pokud chcete mít jistotu, že zařízení se systémem Windows 8.1 nebo novějším, která přistupují k vašim podnikovým prostředkům, mají nainstalované nejnovější aktualizace, použijte nastavení **Vyžadovat automatické aktualizace**. Můžete také určit typ aktualizací, které se mají instalovat automaticky – buď se budou instalovat všechny aktualizace označené jako důležité, nebo všechny aktualizace označené jako důležité nebo doporučené. Úplný seznam nastavení zásad dodržování předpisů najdete v tématu [Správa zásad dodržování předpisů zařízeními pro Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx).
* Nové nastavení **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo** v kombinaci s existujícím nastavením **Počet minut nečinnosti před vyžádáním hesla** umožňuje vytvořit nastavení dodržování předpisů, které vyžaduje, aby koncový uživatel zadal heslo, pokud chce použít zařízení, které bylo nějakou dobu nečinné.

**Nové možnost zásad podmíněného přístupu** Nové i existující zásady podmíněného přístupu můžete použít na **všechny uživatele**. Všichni uživatelé s licencí pro Intune a Office 365 budou muset svoje zařízení zaregistrovat, a pokud Intune platformu zařízení nepodporuje, zablokuje se přístup ke klientským aplikacím pomocí [přihlášení založeného na ověření ve službě Active Directory (moderní ověřování)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/).

Můžete také určit, že se mají zásady podmíněného přístupu uplatňovat na **všechny platformy**.  Každá klientská aplikace používající [přihlášení založené na ověření ve službě Active Directory (moderní ověřování)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) podléhá zásadám podmíněného přístupu, a Intune momentálně nepodporuje danou platformu, dojde k jejímu zablokování.

### Změny a aktualizace Portálu společnosti Microsoft
V této verzi se provedly následující změny aplikací portálu společnosti:

* **Android**: V aplikaci Portál společnosti pro Android přibyla úvodní obrazovka, která pomáhá uživatelům pochopit účel aplikace Portál společnosti. Tato obrazovka má snížit počet stažení aplikace ze strany uživatelů, jejichž společnosti nemají předplatné Intune.

* **iOS**: Intune teď podporuje nasazení zařízení s Mac OS X pomocí [webu Portál společnosti](https://portal.manage.microsoft.com). Pokyny najdete v tématu [Registrace zařízení se systémem Mac OS X v Intune](https://technet.microsoft.com/library/mt598622.aspx).

* **Web Portál společnosti**: Uživatelé, kteří si zaregistrovali zařízení v Intune, teď ke změně hesla můžou použít možnost **Resetovat heslo** na webu Portál společnosti. Dřív mohli hesla uživatelů resetovat jenom správci IT. Možnost Resetovat heslo se nepodporuje v zařízeních s Windows 8.1 a Windows RT a zobrazuje se jenom, když jsou zařízení zaregistrovaná pomocí správy mobilních zařízení (MDM) nebo MDM s Exchange ActiveSync. Pokyny pro uživatele najdete v části [Obnovení hesla](https://technet.microsoft.com/library/mt590895.aspx).

### Změny licencí pro globální správce
V říjnu jsme oznámili, že globální správci (také označovaní jako správci klienta) by mohli dál vykonávat běžné úkony správy bez samostatné licence služby Intune nebo sady EMS (Enterprise Mobility Suite). Pokud ale chtějí globální správci službu používat, například zaregistrovat si svoje vlastní nebo firemní zařízení nebo používat portál společnosti Intune, budou potřebovat licenci služby Intune nebo sady EMS jako ostatní uživatelé. Níže najdete pár dalších podrobností.
* Portál společnosti Intune je místo, kde můžou koncoví uživatelé provádět tyto kroky:
    * Registrovat svoje zařízení
    * Zobrazit stav svého zařízení
    * Stáhnout si software, který globální správce nasadil v organizaci
    * Získat odkazy pro kontaktování oddělení IT, které zveřejnil globální správce.

    [Získejte informace o portálu společnosti](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) a [o tom, jak portál společnosti přizpůsobit](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* Osoba, která se zaregistruje k nákupu předplatného Intune nebo EMS jménem organizace, se automaticky stává prvním globálním správcem daného klienta. Na podzim služba Intune začala těmto prvním globálním správcům v rámci přechodu na [portál služeb Office 365](http://portal.office.com/) a vyřazení [portálu účtů Intune](http://account.manage.microsoft.com/) přidělovat licenci služby Intune nebo sady EMS. Každý další přidaný globální správce může pokračovat v každodenní správě bez samostatné licence služby Intune nebo sady EMS. Pokud by se začal chovat jako koncový uživatel a zaregistroval svoje vlastní (nebo firemní) zařízení nebo stáhl software z portálu společnosti, znamenalo by to, že už potřebuje licenci jako každý jiný uživatel.
* Tato změna se bude zavádět postupně a spustí se v lednu 2016.
* Pro partnery Microsoftu platí, že tato změna by neměla mít vliv na jejich schopnost spravovat službu pro potřeby jejich zákazníků. V případě úloh koncového uživatele bude uživatel potřebovat licenci služby Intune nebo sady EMS, aby mohl zaregistrovat zařízení a získat přístup k softwaru z portálu společnosti nebo ho stáhnout.

Pokud máte k této změně nějaké dotazy, obraťte se na tým podpory služby Intune:
* [Kanály podpory služby Microsoft Intune](https://technet.microsoft.com/library/jj839713.aspx)
* [Podpora komunity](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

Pokud chcete odeslat obecnou zpětnou vazbu ke službě Microsoft Intune, včetně vyplnění žádosti o změnu návrhu nebo oznámení chyb, navštivte stránku [Intune User Voice](https://microsoftintune.uservoice.com/).


### Co je nového v dokumentaci k Intune -- listopad 2015
**Nový obsah**
* [Nastavení zásad konfigurace systému Mac OS X v Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx): Určuje způsob ovládání nastavení a funkcí zařízení se systémem Mac OS X.
* [Nastavení vlastních zásad konfigurace systému Mac OS X v Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx): Určuje, jak nasadit nastavení zařízení se systémem Mac OS X, které jste vytvořili pomocí nástroje Apple Configurator.
* [Konfigurace zásad aplikací pro prevenci ztráty dat v Microsoft Intune](https://technet.microsoft.com/library/mt627825.aspx): Obsahuje informace o scénářích podporovaných zásadami správy mobilních aplikací a o tom, jak tyto zásady chrání data.
* [Začínáme se zásadami správy mobilní aplikace na portálu Azure](https://technet.microsoft.com/library/mt627830.aspx): Všechno, co potřebujete, abyste mohli začít používat portál Azure Preview pro zásady správy mobilních aplikací.
* [Vytvoření a nasazení zásad správy mobilních aplikací v Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx): Obsahuje podrobný návod, jak vytvořit zásady správy mobilních aplikací na portálu Azure Preview.
* [Monitorování zásad správy mobilních aplikací v Microsoft Intune](https://technet.microsoft.com/library/mt627824.aspx): Informace o tom, jak monitorovat zásady správy mobilních aplikací pomocí portálu Azure Preview.
* [Zásady správy mobilních aplikací v Microsoft Intune a funkce Open In systému iOS](https://technet.microsoft.com/library/mt627821.aspx): Informace o tom, jak zásady správy mobilních aplikací spolupracují s funkcí Open In systému iOS.
* [Činnost koncových uživatelů pro aplikace přidružené k zásadám správy mobilních aplikací Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx): Popisuje způsob práce koncového uživatele při použití aplikaci přidružených k určité zásadě správy mobilních aplikací.
* [Vymazání dat ze spravovaných firemních aplikací pomocí Microsoft Intune](https://technet.microsoft.com/library/mt627826.aspx): Popisuje, jak odebrat data z podnikových aplikací.

**Aktualizovaný obsah**
* [Nastavení zásad konfigurace Windows 10 v Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx): Přibylo nové nastavení prohlížeče Edge.
* [Nastavení správy pro iOS a Mac v Microsoft Intune](http://technet.microsoft.com/library/dn408185.aspx): Přibyly informace o registraci zařízení se systémem Mac OS X.
* [Pochopení vašeho zařízení s inventářem v Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx): Přibyly informace o inventáři shromážděném ze zařízení se systémem Mac OS X. Také došlo k aktualizaci tématu, takže teď obsahuje nejnovější informace o všech platformách zařízení.
* [Pochopení operací Microsoft Intune pomocí sestav](https://technet.microsoft.com/library/dn646977.aspx): Přibyly informace o dvou nových sestavách, které slouží k zobrazení informací o spravovaných zařízeních se systémem Mac OS X.
* [Správa zásad dodržování předpisů zařízeními pro Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx): Přibyly informace o nových zásadách dodržování předpisů, které se týkají vyžadování automatických aktualizací a vyžadování hesla při návratu zařízení ze stavu nečinnosti.
* [Správa přístupu k e-mailu v Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx): Přibyly informace o schopnosti uplatňovat zásady podmíněného přístupu na všechny platformy a uživatele.
* [Správa přístupu ke službě SharePoint Online v Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx): Přibyly informace o schopnosti uplatňovat zásady podmíněného přístupu na všechny platformy a uživatele.

## Říjen 2015

### Aktualizace podmíněného přístupu pro místní Exchange
**Teď můžete vyhovujícím zařízením zaregistrovaným v Intune povolit přístup k e-mailu protokolu Exchange Active Sync, pokud je globální pravidlo Exchange nastavené na blokování nebo karanténu** Až do této chvíle platilo, že pokud jste chtěli na zaregistrovaných a vyhovujících zařízeních povolit přístup k e-mailu, bylo potřeba nastavit výchozí globální pravidlo Exchange na **Povolit**.

Po této aktualizaci služby už toto nastavení není k podmíněnému přístupu nezbytné. Pokud vaše prostředí Exchange vyžaduje, abyste výchozí globální pravidlo nastavili na **Blokovat / Umístit do karantény**, stačí na stránce zásad podmíněného přístupu do místního prostředí Exchange zaškrtnout políčko **Přepsat výchozí pravidlo**. Další informace o pravidlech a výsledných oznámeních pro koncové uživatele najdete v tématu [Správa přístupu k e-mailu v Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx).

**Nové prostředí karantény přístupné jedním kliknutím** Zjednodušili jsme využití e-mailu o umístění do karantény, takže teď umožňuje registraci jedním kliknutím. Pomocí této aktualizace služby můžou koncoví uživatelé dokončit proces registrace v aplikaci Portál společnosti kliknutím na odkaz v e-mailu o umístění do karantény.
### Aktualizace správy mobilních zařízení a aplikací
**Android** Všechny funkce pro správu služby Intune teď podporují systém Android 6.0 (Marshmallow), jak se píše v tomto příspěvku na blogu: [Microsoft Intune nabízí podporu systému Android Marshmallow od nultého dne](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx).

**iOS** Už nemůžete vytvářet nová nasazení aplikací do zařízení iOS se starší verzí operačního systému než iOS 7.1. Všechna stávající nasazení aplikací do zařízení se starší verzí operačního systému než iOS 7.1 budou dál fungovat a bude je spravovat Intune.

**Windows 10** Intune teď podporuje nasazení univerzálních aplikací pro Windows 10 pomocí instalačního softwaru typu **balíček aplikací systému Windows**. Podrobnosti a požadavky najdete v tématu [Začínáme s nasazováním aplikací v Microsoft Intune](http://technet.microsoft.com/en-US/library/dn646955.aspx).


### Změny a aktualizace aplikací portálů společnosti Microsoft
V aplikacích Portál společnosti byly v této verzi provedeny následující změny: **iOS** Do aplikace Portál společnosti byla přidána nová tlačítka, která uživatelům usnadňují odesílání diagnostických protokolů správcům IT:

|Název tlačítka|Místo zobrazení|
|------------|---------------|
|Zpráva|Zprávy s chybovou výstrahou|
|Odeslat diagnostickou sestavu|Obrazovka O aplikaci v aplikaci Portál společnosti|



## Září 2015
### Aktualizace správy mobilních zařízení a aplikací
**Všechny funkce správy Intune pro iOS teď podporují iOS 9** Podrobnosti o možnostech správy v systému iOS 9 najdete v [tomto příspěvku na blogu](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx).

**Nové zásady konfigurace mobilních aplikací pro iOS** Nové zásady konfigurace mobilních aplikací umožňují automaticky zadat nastavení, které může aplikace systému iOS vyžadovat při spuštění. Můžete třeba zadat síťový port nebo uživatelské jméno. Podrobnosti najdete v tématu [Konfigurace aplikací pomocí zásad konfigurace mobilních aplikací v Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx).

**Snazší správa aplikací pro uživatele iOS 9**
 V této verzi můžete převést dříve nasazené aplikace pro uživatele systému iOS 9 pod správu Intune. U starších verzí systému iOS platí, že pokud nasazujete aplikaci a na zařízení je už nainstalovaná nespravovaná verze aplikace, budete nejdřív muset požádat uživatele, aby aplikaci ručně odinstaloval, a teprve potom bude moct služba Intune nainstalovat spravovanou aplikaci.

 Od této verze služby Intune ale můžete uživatele zařízení se systémem iOS 9 vyzvat, aby službě Intune umožnili převzít správu aplikace, a použít všechny příslušné zásady správy mobilních aplikací.

 **Správa systému Windows 10** Pomocí nové [obecné zásady konfigurace pro Windows 10](https://technet.microsoft.com/library/mt404697.aspx) můžete konfigurovat heslo, zařízení, prohlížeč a další nastavení pro zaregistrovaná zařízení se systémy Windows 10 a Windows 10 Mobile.

 **Vytváření a nasazení aplikací do zaregistrovaných zařízení s Windows 10** Nový typ instalačního programu softwaru, Instalační služba systému Windows přes MDM (&#42;.msi), umožňuje vytvářet a nasazovat aplikace Instalační služby systému Windows pro zaregistrovaná zařízení se systémem Windows 10. Podrobnosti najdete v tématu [Začínáme s nasazováním aplikací v Microsoft Intune](https://technet.microsoft.com/library/dn646955.aspx).

### Změny a aktualizace aplikací portálů společnosti Microsoft
V této verzi se provedly následující změny aplikací portálu společnosti:

**iOS**
* Microsoft automaticky shromažďuje anonymní informace o výkonu a využití portálu společnosti za účelem zlepšení svých produktů a služeb. Koncoví uživatelé můžou na svém zařízení shromažďování dat vypnout v nastavení dat o využití, ale správci nemají nad shromažďováním dat žádnou kontrolu a nemůžou toto nastavení koncového uživatele nijak změnit.
* Podpora rozlišení celoobrazovkového režimu na zařízeních iPhone 6 a 6 Plus
* Opravy chyb pro vylepšení zabezpečení

### Novinky v dokumentaci Intune – září 2015
**Nová témata**

|Název|Podrobnosti|
|----|--------|
|[Nastavení zásad konfigurace Windows 10 v Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx)|Toto je nová zásada konfigurace, která umožňuje spravovat nastavení a funkce v zařízeních se systémy Windows 10 a Windows 10 Mobile.
| [Konfigurace aplikací pomocí zásad konfigurace mobilních aplikací v Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)|Jedná se o nový typ zásady umožňující automaticky poskytovat zásady, které se můžou požadovat, když uživatel spustí aplikaci pro iOS. |

**Aktualizovaná témata**

|Název|Podrobnosti|
|----|-------|
|[Použití zásad ke správě počítačů a mobilních zařízení s Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)|Došlo k přidání nejnovějších informací, které vám pomůžou pochopit a vytvářet zásady.|

## Srpen 2015
### Aktualizace správy mobilních zařízení a aplikací
* **Podmínky a ujednání** pro registraci v rámci služby Intune a přístup společnosti [jsou teď spravované pomocí zásad](https://technet.microsoft.com/library/mt405893.aspx). Můžete zacílit různé sady podmínek a ujednání, které budou odpovídat požadavkům konkrétní skupiny uživatelů. Například můžete nasadit podmínky a ujednání v různých jazycích pro geograficky vymezené uživatelské skupiny. Můžete také [upravit podmínky a ujednání](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) a rozhodnout, jestli se má zvýšit číslo verze, a vyžádat si souhlas uživatelů s novými podmínkami a ujednáními před použitím portálu společnosti.
* **Řada zásad Intune byla přejmenovaná** , aby byly víc konzistentní v rámci celého produktu a snáz se vyhledávaly. Seznam všech dostupných zásad služby Intune najdete v tématu [Používání zásad ke správě počítačů a mobilních zařízení pomocí Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx).
* **Profily certifikátů PKCS #12 (.PFX)** jsou dostupné pro Android 4.0 nebo novější a pro Windows 10 (ve verzi pro stolní počítače i mobilní zařízení) a novější. Použití .PFX nevyžaduje server NDES. V tématu [Povolení přístupu k firemním prostředkům pomocí profilů certifikátů v Microsoft Intune](http://technet.microsoft.com/library/dn818904.aspx) se naučíte používat profily certifikátů .PFX.
* **Nastavení hranic podnikové sítě pro stolní počítače a mobilní zařízení s Windows 10** umožňuje podrobné nastavení sítě VPN, jak se píše v tématu [Pomoc uživatelům s připojením k práci pomocí profilů sítě VPN v Microsoft Intune](https://technet.microsoft.com/library/dn818905.aspx).
* **Aplikace OneDrive pro Android nově podporuje víc identit**. Tato a další aktualizace zásad správy mobilních aplikací jsou popsané [v seznamu aplikací Microsoftu, které můžete spravovat](https://technet.microsoft.com/library/dn708489.aspx).
* **Vyřazení zámku aktivace na zařízeních iOS**. Pokud je zařízení s iOS, které je majetkem společnosti, chráněné tzv. zámkem aktivace, musíte před vymazáním a opětovnou aktivací zařízení zadat Apple ID a heslo uživatele. To může být problém, pokud již uživatel ze společnosti odešel a vrátil zařízení vlastněné společností, aniž by zámek aktivace vypnul. Problém můžete vyřešit tak, že použijete funkci [Vynechat zámek aktivace služby Intune](https://technet.microsoft.com/library/mt414176.aspx).

### Podmíněný přístup pro osobní počítače
Nově můžete konfigurovat zásady podmíněného přístupu pro osobní počítače. To umožňuje desktopovým aplikacím Office přístup k online službám Exchange Online a SharePointu.
Pokud chcete povolit zásady podmíněného přístupu pro osobní počítače, počítač musí být buď připojený k doméně, nebo splňovat předpisy.
* V části **Začínáme** v tématu [Správa přístupu k e-mailu a službě SharePoint v Microsoft Intune](http://technet.microsoft.com/library/dn818907).aspx) najdete úplný seznam požadavků na povolení podmíněného přístupu pro počítače.
* Podmínky, které můžete nastavit pro povolení podmíněného přístupu pro přístup k e-mailu, najdete v tématu [Správa přístupu k e-mailu v Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx).
* Možnosti, které můžete nastavit pro povolení podmíněného přístupu do služby SharePoint Online, najdete v tématu [Správa přístupu ke službě SharePoint Online v Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx).

### Změny a aktualizace aplikací portálů společnosti Microsoft
V této verzi se provedly následující změny aplikací portálu společnosti:

**Android**

Uživatelům se teď po přihlášení zobrazí pokyny k registraci zařízení, pokud zařízení ještě nezaregistrovali pro správu.

### Novinky v dokumentaci Intune – srpen 2015
**Nová témata**

|Název|Podrobnosti|
|-----|-------|
|[Pomoc při ochraně zařízení s iOS pomocí funkce Vynechat zámek aktivace pro Microsoft Intune](https://technet.microsoft.com/library/mt414176.aspx)|Zjistěte, jak se pomocí Intune dá obejít na zařízeních iOS Zámek aktivace v případě, kdy uživatel odejde od společnosti a vrátí zařízení uzamčené.|

**Aktualizovaná témata**

|Název|Podrobnosti|
|-----|-------|
|[Aplikace Microsoftu, které můžete použít se zásadami správy mobilních aplikací služby Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx)|Doplněné o nejnovější informace o aplikacích, které můžete spravovat pomocí zásad správy mobilních aplikací.
|[Použití zásad ke správě počítačů a mobilních zařízení s Microsoft Intune](http://technet.microsoft.com/library/dn743712.aspx)|Aktualizované o nejnovější zásady přidané do služby Intune.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->



<!--HONumber=Jul16_HO3-->


