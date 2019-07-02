---
title: Časté otázky ke správě mobilních aplikací (MAM) a ochraně aplikací
description: Tento článek poskytuje odpovědi na některé časté otázky ke správě mobilních aplikací (MAM) Intune a ochraně aplikací Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ms.reviewer: erikre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 54511e29bd44b862a5ad06bdfda2067ed7248677
ms.sourcegitcommit: 116ef72b9da4d114782d4b8dd9f57556c9b01511
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2019
ms.locfileid: "67494285"
---
# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>Časté otázky ke správě mobilních aplikací (MAM) a ochraně aplikací

Tento článek poskytuje odpovědi na některé časté otázky ke správě mobilních aplikací (MAM) Intune a ochraně aplikací Intune.

## <a name="mam-basics"></a>Základní informace o MAM

**Co je MAM?**<br></br>
[Správa mobilních aplikací (MAM) Intune](/intune/app-lifecycle) představuje sadu funkcí Intune pro správu, s kterými můžete publikovat, doručovat, konfigurovat, zabezpečovat, monitorovat a aktualizovat mobilní aplikace pro uživatele.

**Jaké jsou výhody ochrany aplikací pomocí MAM?**<br></br>
MAM chrání data organizace v rámci aplikace. Díky funkci MAM bez registrace zařízení (MAM-WE) jde pracovní nebo školní aplikaci, která obsahuje citlivá data, spravovat prakticky na jakémkoliv zařízení, včetně osobních zařízení, která uživatelé používají pracovně (BYOD, bring-your-own-device). Mnoho kancelářských aplikací, například aplikace Microsoft Office, lze spravovat přes Intune MAM. Podívejte se do oficiálního seznamu [aplikací spravovaných přes Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps), který je veřejně přístupný.

**Jaké konfigurace zařízení MAM podporuje?**<br></br>
Intune MAM podporuje dvě konfigurace:
- **Intune MDM + MAM**: Správci IT můžou spravovat aplikace pomocí MAM a zásad ochrany aplikací jenom na zařízeních, která jsou zaregistrovaná ve správě mobilních zařízení Intune (MDM). Pokud zákazníci chtějí spravovat aplikace pomocí MDM + MAM, měli by používat konzolu Intune na portálu Azure Portal na https://portal.azure.com.

- **MAM bez registrace zařízení**: MAM bez registrace zařízení, neboli MAM-WE, umožňují správcům IT spravovat aplikace pomocí MAM a zásad ochrany aplikací na zařízeních nezaregistrovaných pomocí Intune MDM. To znamená, že aplikace je možné spravovat pomocí Intune na zařízeních, která jsou zaregistrovaná u jiných poskytovatelů EMM. Pokud zákazníci chtějí spravovat aplikace pomocí MAM-WE, měli by používat konzolu Intune na portálu Azure Portal na https://portal.azure.com. Aplikace je také možné spravovat pomocí Intune na zařízeních zaregistrovaných pomocí jiných poskytovatelů správy firemních mobilních zařízení (Enterprise Mobility Management (EMM)) nebo na zařízeních vůbec v MDM nezaregistrovaných.


## <a name="app-protection-policies"></a>Zásady ochrany aplikace

**Co jsou zásady ochrany aplikací?**<br></br>
Zásady ochrany aplikací jsou pravidla, která zajistí, že data organizace budou zabezpečená nebo vázaná ve spravované aplikaci. Zásada může být pravidlo, které je vynuceno, když se uživatel pokusí pracovat s firemními daty nebo je přesunout, nebo sada akcí, které jsou zakázané nebo monitorované, pokud je uživatel uvnitř aplikace.

**Jaké jsou příklady zásad ochrany aplikací?**<br></br>
Podrobné informace o každém nastavení zásad ochrany aplikací najdete v tématech [Nastavení zásad ochrany aplikací pro Android](app-protection-policy-settings-android.md) a [Nastavení zásad ochrany aplikací pro iOS](app-protection-policy-settings-ios.md).

**Je možné mít zásady MDM a MAM u stejného uživatele ve stejnou dobu pro různá zařízení? Pokud například uživatel může moct přistupovat k jejich pracovním prostředkům z vlastních počítači s podporou MAM, ale také přijdou do práce a použít zařízení spravovaná pomocí Intune MDM. Existují jakékoli upozornění pro tento nápad?**<br></br>
Pokud použijete zásady MAM pro uživatele bez nastavení stavu zařízení, uživatel dostane zásady MAM na zařízení BYOD a zařízení spravovaných pomocí Intune. Můžete také použít zásady MAM na základě spravovaného stavu. Takže když vytvoříte zásady ochrany aplikací, vedle cílit na všechny typy aplikací, vyberte Ne. Poté proveďte jednu z následujících akcí:
- Použít méně striktní zásady MAM pro zařízení spravovaná pomocí Intune a použít přísnější zásady MAM na jiné zařízení zaregistrovaná v MDM.
- Používejte zásady MAM na nezaregistrovaných zařízeních pouze.

Další informace najdete v tématu [jak monitorovat zásady ochrany aplikací](app-protection-policies-monitor.md).

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Aplikace, které se dají spravovat pomocí zásad ochrany aplikací

**Které aplikace se dají spravovat pomocí zásad ochrany aplikací?**<br></br>
Zásadami ochrany aplikací Intune se dá spravovat každá aplikace integrovaná sadou [Intune App SDK](/intune/app-sdk) nebo zabalená nástrojem [Intune App Wrapping](/intune/apps-prepare-mobile-application-management). Podívejte se do oficiálního seznamu [aplikací spravovaných přes Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps), který je veřejně přístupný.

**Jaké jsou základní požadavky na používání zásad ochrany aplikací v aplikaci spravované přes Intune?**

- Koncový uživatel musí mít účet Azure Active Directory (AAD). Pokud se chcete dozvědět, jak se vytvářejí uživatelé Intune v Azure Active Directory, přečtěte si [Přidání uživatelů a udělení oprávnění pro správu v Intune](/intune/users-permissions-add).

- Koncový uživatel musí mít ke svému účtu Azure Active Directory přiřazenou licenci pro Microsoft Intune. Informace o tom, jak se přiřazují licence Intune koncovým uživatelům, najdete v článku [Správa licencí Intune](/intune/licenses-assign).

- Koncový uživatel musí patřit do skupiny zabezpečení, která je cílem zásady ochrany aplikace. Stejná zásada ochrany aplikace musí mít za cíl konkrétní používanou aplikaci. Zásady ochrany aplikací se dají vytvářet a nasazovat v konzole Intune na [portálu Azure](https://portal.azure.com). Skupiny zabezpečení se aktuálně dají vytvářet v [centra pro správu služeb Microsoft 365](https://admin.microsoft.com).

- Koncový uživatel se musí do aplikace přihlásit pomocí svého účtu AAD.

**Co když chci povolit aplikace pomocí Intune App Protection, ale nepoužívá vývojovou platformu z podporovaných aplikací?** 

Vývojový tým Intune SDK aktivně testuje a udržuje podporu pro aplikace vytvořené pomocí nativní Android, iOS (Obj-C, Swift), Cordova, Xamarin a Xamarin.Forms platformy. Když někteří zákazníci měli úspěchu díky integraci sady Intune SDK jiných platforem, jako je například React Native a NativeScript neposkytujeme explicitní pokyny nebo moduly plug-in pro vývojáře aplikací pomocí nic jiného než naše podporovaných platforem.

**Podporuje sada Intune App SDK knihovnu MSAL (Microsoft Authentication Library) nebo účty sociálních sítí?**<br></br>
Sada Intune App SDK používá některé pokročilé možnosti ADAL (Active Directory Authentication Library) pro výchozí verze sady SDK i pro verze třetích stran. Proto knihovna MSAL příliš dobře nespolupracuje s mnoha našimi hlavními scénáři, jako je ověřování ve službě Intune App Protection nebo podmíněné spuštění. Vzhledem k tomu, že celkové pokyny od týmu služby identit společnosti Microsoft se přepnout na MSAL pro všechny aplikace Microsoft Office, sady Intune SDK bude časem nutné pro její podporu, ale nejsou žádné plány ještě dnes.

**Jaké jsou další požadavky na používání [mobilní aplikace Outlook](https://products.office.com/outlook)?**

- Koncový uživatel musí mít v zařízení nainstalovanou mobilní aplikaci Outlook.

- Koncový uživatel musí mít poštovní schránku [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) a licenci propojenou se svým účtem Azure Active Directory.

  >[!NOTE]
  > Mobilní aplikace Outlook aktuálně podporuje pouze Intune App Protection pro Microsoft Exchange Online a [Exchange Server s hybridním moderním ověřováním](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx) a nepodporuje Exchange v Office 365 Dedicated.

**Jaké jsou další požadavky na používání aplikací [Word, Excel a PowerPoint](https://products.office.com/business/office)?**

- Koncový uživatel musí mít licenci pro [Office 365 Business nebo Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) propojenou se svým účtem Azure Active Directory. Předplatné musí obsahovat aplikace Office na mobilních zařízeních a může obsahovat účet pro ukládání do cloudu přes [OneDrive pro firmy](https://onedrive.live.com/about/business/). Licence na Office 365 můžete přiřadit [centra pro správu služeb Microsoft 365](https://admin.microsoft.com) těchto [pokyny](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

- Koncový uživatel musí mít spravované umístění nakonfigurované pomocí podrobné funkce Uložit jako v nastavení zásad ochrany aplikace Zakázat možnost Uložit jako. Pokud je spravovaným umístěním třeba OneDrive, musí být v aplikaci Word, Excel nebo PowerPoint koncového uživatele nakonfigurovaná aplikace [OneDrive](https://onedrive.live.com/about/).

- Pokud je spravovaným umístěním OneDrive, musí být aplikace cílem pro zásadu ochrany aplikace nasazenou pro koncového uživatele.

  >[!NOTE]
  > Mobilní aplikace Office aktuálně podporují jenom SharePoint Online a ne místní SharePoint.

**Proč je pro Office potřeba spravované umístění (jako OneDrive)?**<br></br>
Intune označuje veškerá data v aplikaci jako podniková (firemní) nebo osobní. Data se považují za podniková, když pocházejí z firemního umístění. U aplikací Office považuje Intune za firemní následující umístění: e-mail (Exchange) nebo cloudové úložiště (aplikace OneDrive s účtem OneDrive pro firmy).

**Jaké jsou další požadavky na používání Skypu pro firmy?**<br></br>
Viz licenční požadavky [Skypu pro firmy](https://products.office.com/skype-for-business/it-pros). Informace o hybridních a místních konfiguracích Skypu pro firmy najdete v článcích [Hybridní moderní ověřování pro Skype pro firmy a Exchange bude všeobecně dostupné](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Hybrid-Modern-Auth-for-SfB-and-Exchange-goes-GA/ba-p/134756) a [Moderní ověřování pro Skype pro firmy v místním prostředí s AAD](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Modern-Auth-for-SfB-OnPrem-with-AAD/ba-p/180910).

## <a name="app-protection-features"></a>Funkce ochrany aplikací

**Co je podpora více identit?**<br></br>
Podpora více identit je schopnost sady Intune App SDK použít zásady ochrany aplikací jenom na pracovní nebo školní účet přihlášený k aplikaci. Pokud se k aplikaci přihlásí osobní účet, zůstanou data nedotčená.

**Co je účelem podpory více identit?**<br></br>
Podpora více identit umožňuje, aby se aplikace pro podnikové i běžné zákazníky (tj. aplikace Office) vydávaly veřejně s funkcemi ochrany aplikací Intune pro podnikové účty.

**Jak je na tom aplikace Outlook s více identitami?**<br></br>
Outlook má kombinované zobrazení osobních a podnikových e-mailů, proto při spuštění zobrazí výzvu k zadání PINu Intune.

**Co je PIN aplikace Intune?**<br></br>
Osobní identifikační číslo (PIN) je heslo, kterým se ověřuje, že s daty organizace pracuje v aplikaci správný uživatel.

- **Když je uživatel vyzván k zadání PINu?**<br></br> Intune vyzve uživatele k zadání PINu aplikace, když se uživatel chystá pracovat s podnikovými daty. V aplikacích s více identitami, jako Word, Excel a PowerPoint, bude uživatel vyzván k zadání PINu při pokusu o otevření podnikového souboru nebo dokumentu. V aplikacích s jednou identitou, například obchodní aplikace spravované přes nástroj Intune App Wrapping, se PIN vyžaduje při spuštění, protože sada Intune App SDK ví, že prostředí uživatele v aplikaci bude vždy podnikové.

- **Jak často se uživateli zobrazí výzva k zadání kódu PIN Intune?**<br></br> Správce IT může v konzole pro správu Intune definovat nastavení zásad ochrany aplikací Překontrolovat požadavky na přístup za (minuty). Toto nastavení určuje dobu, než se v zařízení zkontrolují požadavky na přístup a znovu se zobrazí obrazovka pro kód PIN aplikace. Četnost, s jakou se budou uživateli zobrazovat výzvy, ale ovlivňují důležité detaily týkající se kódu PIN: 

    - **Kód PIN sdílí mezi aplikacemi stejného vydavatele použitelnosti:** V Iosu se kód PIN jedné aplikace sdílí mezi všemi aplikacemi **stejného vydavatele aplikace**. V Androidu se kód PIN jedné aplikace sdílí mezi všemi aplikacemi.
    - **Chování "překontrolovat požadavky na přístup po (minuty)' po restartování zařízení:** Časovač"PIN" sleduje počet minut nečinnosti, které určují, kdy zobrazíte další PIN aplikace Intune. V systému iOS nemá restart zařízení na časovač kódu PIN vliv. Proto restart zařízení nemá vliv na počet minut, během kterých byl uživatel v aplikaci pro iOS se zásadou pro PIN nečinný. V systému Android restartování zařízení časovač kódu PIN vynuluje. Proto aplikace pro Android se zásadou pro PIN budou pravděpodobně **po restartu zařízení** vyžadovat PIN aplikace bez ohledu na hodnotu nastavení „Překontrolovat požadavky na přístup za (minuty)“.  
    - **Kolísavost časovače přidruženého ke kódu PIN:** Po zadání kódu PIN pro přístup k aplikaci (aplikace A) a aplikace přestane zobrazovat na popředí (hlavní fokus) na zařízení, vynuluje se časovač tohoto kódu PIN. Jakákoli aplikace (aplikace B), která tento kód PIN sdílí, nevyzve uživatele k jeho zadání, protože časovač se vynuloval. Tato výzva se zobrazí znovu, jakmile je opět splněna hodnota nastavení Překontrolovat požadavky na přístup za (minuty).

Na zařízeních s iOSem platí, že i když stejný PIN používají aplikace od různých vydavatelů, zobrazí se výzva znovu po splnění hodnoty nastavení **Znovu zkontrolovat požadavky na přístup po (minuty)** u aplikace, která se nenachází v hlavním fokusu. Představte si například, že má uživatel aplikaci _A_ od vydavatele _X_ a aplikaci _B_ od vydavatele _Y_ a na obou se používá stejný PIN. Uživatel se zaměřuje na aplikaci _A_ (popředí), aplikace _B_ se minimalizuje. Když se splní hodnota **Znovu zkontrolovat požadavky na přístup po (minuty)** a uživatel přepne na aplikaci _B_, bude vyžadován PIN.

  >[!NOTE] 
  > Kvůli častějšímu ověřování požadavků na přístup uživatele (například výzvy k zadání PINu) doporučujeme zmenšit hodnotu nastavení Překontrolovat požadavky na přístup za (minuty), a to především u často používaných aplikací. 
      
- **Jak PIN kód Intune funguje s integrovanými PIN kódy aplikace pro Outlook a OneDrive?**<br></br>
PIN kód Intune funguje na základě nečinnosti podle časovače (neboli hodnoty „Překontrolovat požadavky na přístup za (minuty)“). Proto se výzvy PIN kódu Intune zobrazují nezávisle na výzvách integrovaných PIN kódů aplikace pro Outlook a OneDrive, které jsou většinou ve výchozím nastavení svázané se spuštěním aplikace. Pokud se uživateli zobrazí obě výzvy PIN kódu najednou, měl by mít přednost PIN kód Intune. 

- **Je PIN bezpečný?**<br></br> PIN slouží k tomu, aby v aplikaci povolil pracovat s daty organizace jenom správnému uživateli. Proto se koncový uživatel musí přihlásit s pracovním nebo školním účtem, aby si mohl nastavit nebo resetovat PIN pro aplikaci Intune. Toto ověření zpracovává Azure Active Directory prostřednictvím zabezpečené výměny tokenu a sada Intune App SDK do procesu nevidí. Z hlediska zabezpečení je nejlepší ochranou pracovních nebo školních dat jejich šifrování. Šifrování nesouvisí s PINem aplikace, ale jde o vlastní zásadu ochrany aplikace.

- **Jak Intune chrání PIN před útoky hrubou silou?**<br></br> Jako součást zásady pro PIN aplikace může správce IT nastavit maximální počet pokusů, které uživatel má k ověření PINu před uzamčením aplikace. Po vyčerpání pokusů může sada Intune App SDK vymazat podniková data v aplikaci.
  
- **Proč musím v aplikacích od stejného vydavatele dvakrát zadávat PIN?**<br></br> MAM (v iOSu) aktuálně umožňuje PIN na úrovni aplikace s alfanumerickými a speciálními znaky (nazývaný „heslo“), který vyžaduje zapojení aplikací (jako WXP, Outlook, Managed Browser, Yammer) k integraci sady Intune APP SDK pro iOS. Bez toho se nastavení hesla pro cílové aplikace správně nevynutí. Tato funkce byla vydána v Intune SDK pro iOS verze 7.1.12. <br><br> Aby mohla být tato funkce podporována a byla zajištěna zpětná kompatibilita s předchozími verzemi sady Intune SDK pro iOS, budou se všechny kódy PIN (číselné nebo v podobě hesla) od verze 7.1.12 zpracovávat odděleně od číselných kódů PIN používaných v předchozích verzích SDK. Pokud jsou v zařízení aplikace od stejného vydavatele, které používají sadu Intune SDK pro iOS ve verzích před 7.1.12 A SOUČASNĚ po 7.1.12, bude potřeba nastavit dva kódy PIN. <br><br> Tyto dva kódy PIN (pro každou aplikaci jeden) spolu nijak nesouvisejí, tzn. že musejí vyhovovat zásadám ochrany aplikace platným pro danou aplikaci. Uživatel smí nastavit stejný PIN dvakrát *jen tehdy*, když aplikace A a B používají stejné zásady (platné pro PIN). <br><br> Uvedené chování je specifické pro PIN aplikací pro iOS povolených ve správě mobilních aplikací v Intune. Jak si budou aplikace postupně osvojovat novější verze sady Intune SDK pro iOS, přestane být dvojí nastavování kódu PIN u aplikací od stejného vydavatele takový problém. V následující poznámce uvádíme příklad.

  >[!NOTE]
  > Pokud k vytvoření aplikace A byla použita verze před 7.1.12 a k vytvoření aplikace B od stejného vydavatele byla použita verze vyšší nebo rovna 7.1.12, musí koncový uživatel nastavit PIN zvlášť pro aplikaci A i B, pokud jsou na zařízení s iOSem nainstalované obě aplikace. <br><br> Pokud na toto zařízení nainstalujete aplikaci C se sadou SDK 7.1.9, bude mít stejný PIN jako aplikace A. <br><br> Aplikace D vytvořená s použitím verze 7.1.14 bude mít stejný PIN jako aplikace B. <br><br> Pokud na zařízení nainstalujete jenom aplikace A a C, stačí nastavit jenom jeden PIN. To samé platí, i pokud jsou na zařízení nainstalované aplikace B a D.

**A co šifrování?**<br></br>
Správci IT můžou nasadit zásadu ochrany aplikace, která vyžaduje šifrování dat aplikace. Jako součást této zásady může správce IT také určit, kdy se obsah bude šifrovat.

- **Jak Intune šifruje data?**<br></br> Podrobné informace o nastavení zásady ochrany aplikace šifrováním najdete v tématech [Nastavení zásad ochrany aplikací pro Android](app-protection-policy-settings-android.md) a [Nastavení zásad ochrany aplikací pro iOS](app-protection-policy-settings-ios.md).

- **Co se šifruje?**<br></br> Šifrují se jenom data označená jako podniková, a to podle zásady ochrany aplikace správce IT. Data se považují za podniková, když pocházejí z firemního umístění. U aplikací Office považuje Intune za firemní následující umístění: e-mail (Exchange) nebo cloudové úložiště (aplikace OneDrive s účtem OneDrive pro firmy). U obchodních aplikací spravovaných nástrojem Intune App Wrapping se za podniková považují všechna data aplikace.

**Jak může Intune vzdáleně smazat data?**<br></br>
Intune může data aplikace smazat třemi způsoby: úplným vymazáním zařízení, selektivním vymazáním pro MDM nebo selektivním vymazáním pro MAM. Další informace o vzdáleném vymazání pro správu mobilních zařízení (MDM) najdete v článku věnovaném [odebrání zařízení pomocí vymazání nebo vyřazení](devices-wipe.md). Další informace o selektivním vymazání pomocí MAM najdete v části [Vyřazení](devices-wipe.md#retire) a v článku [Jak z aplikací vymazat jenom firemní data](apps-selective-wipe.md).

- **Co je vymazání?**<br></br> [Vymazání](devices-wipe.md) odebere veškerá uživatelská data a nastavení ze **zařízení** obnovením jeho výchozího továrního nastavení. Zařízení se odebere ze služby Intune.
  >[!NOTE]
  > Vymazání jde dosáhnout jen na zařízeních zaregistrovaných ve správě mobilních zařízení (MDM) Intune.

- **Co je selektivní vymazání pro MDM?**<br></br> V článku [Odebrání zařízení – část Vyřazení](devices-wipe.md#retire) najdete informace o odebírání firemních dat.

- **Co je selektivní vymazání pro MAM?**<br></br> Selektivní vymazání pro MAM jednoduše odebere data aplikace společnosti z aplikace. Žádost se inicializuje pomocí portálu Intune Azure Portal. Informace o zahájení žádosti o vymazání najdete v článku [Jak z aplikací vymazat jenom firemní data](apps-selective-wipe.md).

- **Jak rychle selektivní vymazání pro MAM proběhne?**<br></br> Pokud uživatel používá aplikaci, když je zahájeno selektivní vymazání, sada Intune App SDK kontroluje každých 30 minut žádost o selektivní vymazání ze služby Intune MAM. Selektivní vymazání také kontroluje tehdy, když uživatel spustí aplikaci poprvé a přihlásí se pomocí pracovního nebo školního účtu.

**Proč místní služby nepracují s aplikacemi chráněnými službou Intune?**<br></br>
Ochrana aplikací Intune závisí na identitě uživatele, aby byla konzistentní mezi aplikací a sadou Intune App SDK. Jediná cesta, která to může zaručit, je moderní ověřování. Jsou situace, kdy aplikace můžou fungovat s místní konfigurací, ale nejsou konzistentní ani nic nezaručují.

**Existuje bezpečný způsob, jak otevírat webové odkazy ze spravovaných aplikací?**<br></br>
Ano. Správce IT může nasadit a nastavit zásadu ochrany aplikace pro [aplikaci Intune Managed Browser](app-configuration-managed-browser.md), což je webový prohlížeč vyvinutý týmem Microsoft Intune, který se dá snadno spravovat přes Intune. Správce IT může vyžadovat, aby se všechny webové odkazy v aplikacích spravovaných přes Intune otvíraly v aplikaci Managed Browser.



## <a name="app-experience-on-android"></a>Prostředí aplikací na Androidu

**Proč je potřeba aplikace Portál společnosti, aby ochrana aplikací Intune fungovala na zařízeních s Androidem?**<br></br>
Většina funkcí ochrany aplikací je integrovaná do aplikace Portál společnosti. I když aplikace Portál společnosti se vždycky vyžaduje, registrace zařízení se _nevyžaduje_. U správy mobilních aplikací bez registrace (MAM-WE) je jenom nutné, aby měl koncový uživatel aplikaci Portál společnosti na zařízení nainstalovanou.

**Jak na Androidu funguje více nastavení přístupu k ochraně aplikací Intune, která jsou nakonfigurovaná na stejnou sadu aplikací a uživatelů?**<br></br>
Zásady ochrany aplikací Intune pro přístup se na zařízení koncových uživatelů, která se pokusí o přístup k cílové aplikaci z firemního účtu, použijí v konkrétním pořadí. Obecně má přednost blokování, pak upozornění, které se dá zavřít. Například pokud se aplikuje na konkrétního uživatele nebo aplikaci, nastavení minimální verze opravy Androidu, které uživatele upozorňuje, aby provedl upgrade opravy, se použije po nastavení minimální verze opravy Androidu, které uživateli zablokuje přístup. Proto ve scénáři, kde správce IT nakonfiguruje minimální verzi opravy Androidu na 2018-03-01 a minimální verzi opravy Androidu (pouze upozornění) na 2018-02-01, zatímco zařízení pokoušející se o přístup k aplikaci má verzi opravy 2018-01-01, by byl koncový uživatel zablokován na základě přísnějšího nastavení pro minimální verzi opravy Androidu, která vede k zablokování přístupu. 

Při zpracování různých typů nastavení by měl přednost požadavek na verzi aplikace. Následoval by požadavek na verzi operačního systému Android a pak požadavek na verzi opravy Androidu. Pak se ve stejném pořadí kontrolují všechna upozornění pro všechny typy nastavení.

**Zásady ochrany aplikací Intune poskytuje funkce pro správce vyžadují zařízení koncových uživatelů k předání ověření SafetyNet společnosti Google pro zařízení s Androidem. Jak často se nový výsledek ověření SafetyNet odesílají do služby?** <br><br> Nové určení služby Google Play se ohlásí Správci IT v intervalu určit přes službu Intune. Jak často je uskutečněn hovor služby je omezena z důvodu zatížení, proto tato hodnota se zachová interně a nelze ji konfigurovat. Jakékoli správce IT nakonfiguroval akce pro ověření SafetyNet Google nastavení se provedou na základě na poslední oznámený výsledek do služby Intune v době podmíněnému spouštění. Pokud není k dispozici žádná data, přístup povolen v závislosti na žádné jiné kontroly podmíněného spuštění neúspěšné a Google Play služby "umožňujícím zpětnou transformaci" pro určení ověření výsledky začínají v back-end, který se asynchronně vyzve uživatele, pokud zařízení se nezdařilo. Pokud existuje zastaralá data, přístup se blokované nebo povolené v závislosti na poslední oznámený výsledek a podobně, služby Google Play "zpětná" pro určení výsledky ověření zahájíme a asynchronně vyzve uživatele, pokud zařízení se nezdařilo.

**Zásady ochrany aplikací Intune poskytuje funkce pro správce vyžadují zařízení koncových uživatelů můžete posílat signály prostřednictvím API Apps ověřte Googlu pro zařízení s Androidem. Jak může koncový uživatel zapnout skenování aplikace tak, že nemáte zablokovaný přístup z toho důvodu?**<br><br> Pokyny, jak to udělat mírně lišit podle zařízení. Obecný postup zahrnuje přejít Google Play Store a klikněte na položku **Moje aplikace a hry**, pak kliknete na výsledek posledního skenování aplikací, které se dostanete do nabídky Play Protect. Zajištění přepínač **vyhledat v zařízení bezpečnostní hrozby** přepnutí na on.

**Co rozhraní API ověření SafetyNet společnosti Google skutečně zkontrolovat na zařízeních s Androidem? Jaký je rozdíl mezi hodnotami konfigurovatelné kontrola základní integritu a "Kontrola základní integritu a certifikovaná zařízení'?** <br><br>
Intune využívá Google Play chránit SafetyNet rozhraní API pro přidání do naší stávající zjišťování kontroly kořenové pro neregistrovaná zařízení. Google se vyvíjí a udržuje toto rozhraní API pro aplikace pro Android na přijmout, pokud nechcete své aplikace spouštět na zařízením s rootem. Aplikace Android platit doplnil, např. Zatímco Google veřejně sdílet rozsahu zjišťování kontroly kořenové, ke kterým dochází, Očekáváme, že tato rozhraní API pro detekci uživatelé, kteří mají svá zařízení s rootem. Tito uživatelé můžou potom blokovat přístup k nebo jejich podnikové účty ze své zásady v aplikacích s podporou. 'Zkontrolovat základní integritu' vás informuje o obecné integrity zařízení. Root zařízení, emulátory, virtuální zařízení a zařízení s příznaky manipulaci základní integrity navrácení služeb po. 'Kontrola základní integritu a certifikovaná zařízení' vás informuje o kompatibility zařízení se službami od Googlu. Pouze bez úprav zařízení, které byly ověřeny Google, můžete předat tuto kontrolu. Zařízení, která se nezdaří, patří:
* Zařízení, které nesplní základní integritu
* Zařízení s odemknout zaváděcího programu pro spouštění
* Zařízení s vlastní systém image/ROM
* Zařízení u kterých nebyla výrobce platí pro, nebo předejte certifikační služby Google 
* Zařízení s bitovou kopii systému vytvořené přímo ze zdrojových souborů s Androidem otevřete zdrojový Program
* Zařízení s bitovou kopii systému beta/developer preview

Zobrazit [dokumentace Googlu na ověření SafetyNet](https://developer.android.com/training/safetynet/attestation) technické podrobnosti.

**Existují dvě podobné kontroly sekce podmíněného spuštění, při vytváření zásady ochrany aplikací Intune pro zařízení s Androidem. By měl být vyžadující, nastavení ověření zařízení SafetyNet nebo "zařízení s jailbreakem/rootem zařízení" nastavení?** <br><br>
Google Play Protect kontroly SafetyNet rozhraní API vyžaduje, koncový uživatel je zařízení online, alespoň po dobu trvání čas, kdy "zpětná" pro určení výsledky ověření provádí. Pokud koncový uživatel je v režimu offline, správce IT může stále očekávat, že výsledek ze "zařízení s jailbreakem/rootem zařízení" nastavení vynucení. Tento říká, pokud koncový uživatel byl příliš dlouhý offline, "období odkladu pro Offline' Hodnota vstupu do play a všechny přístup k práci nebo školních dat je blokován, jakmile je dosaženo této hodnoty časovače, dokud nebude k dispozici přístup k síti. Zapnutí obě nastavení umožňuje vrstveného přístupu k udržování koncový uživatel zařízení v pořádku, což je důležité, když se koncoví uživatelé přístup fungovat nebo školních dat na mobilních zařízeních. 

**Nastavení zásad ochrany aplikací, které využívají Google Play ochrana rozhraní API vyžadují služby Google Play na funkci. Co když aplikace služby Google Play nejsou povoleny v místě, kde může být koncový uživatel?**<br><br>
Ověření zařízení SafetyNet i "Kontrola ohrožení aplikací" nastavení vyžadují Google určit verzi správné fungování služby Google Play. Protože jde o nastavení, které spadají v oblasti zabezpečení, bude koncový uživatel zablokován, zaměřuje s těmito nastaveními a nesplňují příslušnou verzi služby Google Play nebo nemají přístup k služby Google Play. 

## <a name="app-experience-on-ios"></a>Prostředí aplikací v iOS
**Co se stane, když v zařízení přidám nebo odeberu otisk prstu nebo tvář?**<br></br>
Zásady ochrany aplikací Intune umožňují řídit přístup k aplikacím jen uživatelům s licencí na Intune. Jedním ze způsobů, jak řídit přístup k aplikacím, je vyžadovat na podporovaných zařízeních Touch ID nebo Face ID od Applu. Intune se chová tak, že když se v zařízení změní databáze biometrických údajů, vyzve uživatele k zadání kódu PIN, pokud je splněna hodnota časového limitu nečinnosti. Ke změnám biometrických údajů patří přidání nebo odebrání otisku prstu nebo tváře. Pokud uživatel Intune nemá nastavený kód PIN, je nasměrován na nastavení kódu PIN pro Intune.
 
Záměrem tohoto chování je nadále udržovat data organizace v aplikaci zabezpečená a chráněná na úrovni aplikace. Tato funkce je dostupná jen pro iOS a vyžaduje zapojení aplikací, které integrují sadu Intune APP SDK pro iOS verze 9.0.1 nebo novější. Integrace této sady SDK je nezbytná kvůli vynucení tohoto chování u cílových aplikací. K této integraci dochází průběžně a závisí na týmech konkrétních aplikací. Mezi zapojené aplikace patří například WXP, Outlook, Managed Browser a Yammer. 
  
**Můžu pomocí rozšíření pro sdílení v iOS otevírat pracovní nebo školní data v nespravovaných aplikacích, i když je zásada přenosu dat nastavená na „jenom spravované aplikace“ nebo „žádné aplikace“. Nemůže při tom dojít k úniku dat?**<br></br>
Zásady ochrany aplikací pro Intune nemůžou ovládat rozšíření pro sdílení v iOS, když dané zařízení nespravují. Proto Intune _**podniková data před jejich sdílením mimo příslušnou aplikaci zašifruje**_ . Můžete si to ověřit tak, že si zkusíte otevřít podnikový soubor mimo spravovanou aplikaci. Měl by být zašifrovaný a mimo spravovanou aplikaci by ho nemělo být možné otevřít.

**Jak v iOSu funguje více nastavení přístupu k ochraně aplikací Intune, která jsou nakonfigurovaná na stejnou sadu aplikací a uživatelů?**<br></br>
Zásady ochrany aplikací Intune pro přístup se na zařízení koncových uživatelů, která se pokusí o přístup k cílové aplikaci z firemního účtu, použijí v konkrétním pořadí. Obecně má přednost vymazání, pak blokování, a pak upozornění, které se dá zavřít. Například pokud se aplikuje na konkrétního uživatele nebo aplikaci, nastavení minimální verze operačního systému iOS, které uživatele upozorňuje, aby svou verzi iOSu aktualizoval, se použije po nastavení minimální verze operačního systému, které uživateli zablokuje přístup. Proto ve scénáři, kde správce IT nakonfiguruje minimální operační systém iOS na 11.0.0.0 a minimální operační systém iOS (pouze upozornění) na 11.1.0.0, zatímco zařízení pokoušející se o přístup k aplikaci má iOS 10, by byl koncový uživatel zablokován na základě přísnějšího nastavení pro minimální verzi operačního systému iOS, které vede k zablokování přístupu.

Při zpracování různých typů nastavení by měl přednost požadavek na verzi Intune App SDK. Následoval by požadavek na verzi aplikace a pak požadavek na verzi operačního systému iOS. Pak se ve stejném pořadí kontrolují všechna upozornění pro všechny typy nastavení. Doporučujeme nakonfigurovat verzi Intune App SDK jenom po pokynu od produktového týmu Intune pro základní scénáře blokování.


## <a name="see-also"></a>Viz také:
- [Implementace plánu Intune](planning-guide-onboarding.md)
- [Testování a ověřování Intune](planning-guide-test-validation.md)
- [Nastavení zásad správy mobilních aplikací pro Android v Microsoft Intune](app-protection-policy-settings-android.md)
- [Nastavení zásad správy mobilních aplikací pro iOS](app-protection-policy-settings-ios.md)
- [Aktualizace zásad zásady ochrany aplikací](app-protection-policy-delivery.md)
- [Ověření zásad ochrany aplikací](app-protection-policy-delivery.md)
- [Přidání zásad konfigurace aplikací pro spravované aplikace bez registrace zařízení](app-configuration-policies-managed-app.md)
- [Jak získat podporu pro Microsoft Intune](get-support.md)
