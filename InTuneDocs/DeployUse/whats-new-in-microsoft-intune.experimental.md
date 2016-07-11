---
experiment_id: lindavr-abtest-20160527
title: "Co je nového | Microsoft Intune"
description: "Zjistěte, co je nového v aktualizací služby Microsoft Intune v tomto měsíci nebo dříve"
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 06/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
ms.sourcegitcommit: d1fb04dbb8746637bf72c1e227f36fe589594ca0
ms.openlocfilehash: ae524a989e236e84a6ce9d8266fc648dd683a825


---

# Co je nového v Microsoft Intune
Zjistěte, co je nového v této verzi Microsoft Intune. Můžete také získat informace o nadcházejících změnách, se kterými byste měli počítat, a o minulých verzích.

Následující funkce jsou v této verzi nové. S výjimkou aktualizace nastavení zásad programu Windows Defender jsou všechny tyto funkce podporovány také pro hybridní nasazení u zákazníků (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Červen 2016
### Stav služby Intune
Informace o stavu služby pro Intune se přesouvají do centrálního umístění společně s ostatními službami Microsoftu. Tyto informace nyní najdete na portálu pro správu Office 365 v části věnované stavu služby. Další informace najdete v [tomto příspěvku blogu](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

## Správa aplikací
- **Vylepšení prostředí pro konfiguraci datových zásad systému Windows 10 Enterprise.** Vylepšili jsme možnosti konfigurace zásad ochrany podnikových dat systému Windows 10 souvisejících s vytvářením pravidel aplikací, určováním definice mezí sítě a dalších nastavení pro ochranu podnikových dat. Další informace najdete v tématu [Vytvoření zásady ochrany podnikových dat pomocí Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


## Správa zařízení
- **Nastavení zásad programu Windows Defender pro ochranu proti potenciálně nežádoucím aplikacím.** Do obecné konfigurace zásady pro Windows 10 Desktop a Mobile bylo přidáno nové nastavení programu Windows Defender nazvané **Detekce potenciálně nežádoucích aplikací**. Pomocí tohoto nastavení můžete ochránit zaregistrované stolní počítače s Windows před spuštěním softwaru, který Windows Defender klasifikuje jako potenciálně nežádoucí. Můžete nastavit ochranu před spuštěním těchto aplikací nebo pomocí režimu auditu upozornit, když se potenciálně nežádoucí aplikace nainstaluje. Další informace najdete v tématu [Nastavení zásad pro Windows 10 v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

## Podmíněný přístup
- **Zásady řízení přístupu k síti Cisco ISE pro Intune.**  Zákazníci, kteří používají Cisco Identity Service Engine (ISE) 2.1 a také Microsoft Intune, mohou v modulu ISE nastavit zásady řízení přístupu k síti.

    Když se použijí tyto zásady, zařízení, která se připojují k síti pomocí WiFi nebo VPN, musí splňovat následující podmínky, jinak jim nebude povolen přístup:

    * Musí být spravovaná pomocí Intune.
    * Musí splňovat veškeré nasazené zásady dodržování předpisů Intune.

 Koncovým uživatelům nevyhovujících zařízení se zobrazí výzva k registraci. Pokud chtějí získat přístup, musí všechny problémy s dodržováním předpisů vyřešit.
- **Podmíněný přístup pro prohlížeč.** Můžete nastavit zásady podmíněného přístupu pro [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) a [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md), na základě kterých k nim bude možné získat přístup pouze z podporovaných webových prohlížečů ve spravovaných a vyhovujících zařízeních. Koncoví uživatelé, kteří se pokusí přihlásit k aplikaci Outlook Web Access (OWA) a webům služby SharePoint pomocí zařízení s iOS a Androidem, budou vyzváni, aby před přihlášením svoje zařízení zaregistrovali v Intune a opravili všechny problémy, kvůli kterým zařízení nesplňuje pravidla zásad dodržování předpisů.
<!---TFS 1175844--->

- **Dynamics CRM Online podporuje podmíněný přístup.** Můžete pro [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md) nastavit zásady podmíněného přístupu, aby k němu měla přístup pouze spravovaná a vyhovující zařízení s iOS a s Androidem. Koncovým uživatelům, kteří se pokusí přihlásit k mobilní aplikaci Dynamics CRM na iOS a Androidu, se zobrazí výzva, aby si před přihlášením zařízení zaregistrovali v Intune a aby vyřešili všechny problémy, kvůli kterým zařízení není v souladu s pravidly zásad dodržování předpisů v organizaci.
<!---TFS1295358--->


## Aktualizace Portálu společnosti

### Aplikace Portál společnosti pro Android

- Když správci IT použijí nové zásady „Požadovat, aby zařízení nepovolovala instalaci aplikací z neznámých zdrojů (Android 4.0 +)“, koncovým uživatelům se zařízeními s Androidem 4.0 nebo novějším zařízení se zobrazí zpráva Musí se zakázat instalace z neznámých zdrojů. Uživatelé budou muset přejít do části **Nastavení** > **Zabezpečení** a vypnout nastavení **Neznámé zdroje**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) o zprávě a důvodu, proč se po nich vyžaduje vypnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Požadovat, aby zařízení měla povoleno vyhledávání bezpečnostních hrozeb v aplikacích (Android 4.0+)“, koncovým uživatelům se zařízeními s Androidem 4.0 nebo novějším se zobrazí zpráva Vyhledat v zařízení bezpečnostní hrozby. Uživatelé budou muset přejít do části **Nastavení** > **Google** > **Zabezpečení** a zapnout nastavení **Vyhledat v zařízení bezpečnostní hrozby**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o zprávě a důvodu, proč se po nich vyžaduje zapnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Požadovat, aby bylo zakázané ladění USB (Android 4.2+)“, koncovým uživatelům se zařízeními s Androidem 4.2 nebo novějším se zobrazí zpráva Musí se zakázat ladění USB. Uživatelé budou muset přejít do části **Nastavení** > **Možnosti pro vývojáře** a vypnout nastavení **Ladění USB**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) o zprávě a důvodu, proč se po nich vyžaduje vypnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Minimální úroveň oprav zabezpečení Androidu (Android 6.0 +)“, koncovým uživatelům se zařízeními s Androidem 6.0 nebo novějším se zobrazí zpráva Toto zařízení nesplňuje minimální úroveň oprav zabezpečení Androidu. Uživatelé budou muset nainstalovat požadovanou opravu zabezpečení. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat [informace](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o postupu při instalaci požadované opravy zabezpečení a zjistit, které opravy zabezpečení mají aktuálně nainstalovány.

### Aplikace Portál společnosti pro iOS

- Když budou koncoví uživatelé instalovat podnikové aplikace, bude se jim nyní zobrazovat vylepšené prostředí instalace aplikace. Pokud instalace aplikace trvá příliš dlouho, uživatelé si můžou zařízení synchronizovat ručně, aby se vynutilo pokračování procesu synchronizace. Pokud si chcete projít pokyny pro koncové uživatele, najdete je v tématu [Ruční synchronizace zařízení s iOS](/Intune/EndUser/sync-your-device-manually-ios.md).

- Aplikace Portál společnosti Microsoft Intune pro iOS je aktualizovaná tak, aby podporovala iOS verze 8.0 a novější. Aktualizace znamená, že můžou koncoví uživatelé nainstalovat aplikaci Portál společnosti a zaregistrovat nová zařízení v Intune, jenom když se na zařízení používá iOS verze 8.0 nebo novější. Uživatelé, kteří už mají zaregistrovaná zařízení používaná v nepodporované verzi iOS, můžou nadále používat aplikaci Firemní portál nainstalovanou na jejich zařízeních.


## Co připravujeme

### Průvodce cloudem
Udržujte si přehled o budoucích novinkách pro Intune díky [průvodci cloudovou platformou](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Zastaralá služba
- **Aplikace Intune Viewer.** V souvislosti s vydáním nové aplikace Sdílení RMS odebíráme od srpna 2016 následující aplikace Intune Viewer:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer pro Android z Google Play

  Místo použití aplikací Intune Viewer vám doporučujeme používat novou aplikaci Rights Management (sdílení RMS) pro Android, která pro bezpečné prohlížení firemních souborů na zařízeních s Androidem umožňuje nasadit jednu aplikaci (namísto tří samostatných aplikací). Přečtěte si víc o aplikaci Sdílení RMS (s odkazem na dokumentaci).

- **Odebrání možnosti cílení pravidel oznámení na vlastní skupiny.**
Pravidla oznámení Intune definují, komu se budou z Intune odesílat e-mailové výstrahy. V současnosti můžete nakonfigurovat pravidla oznámení pro odesílání e-mailů všem uživatelům zařízení nebo skupině zařízení služby Intune, kterou jste vytvořili. Přibližně od 1. června 2016 se už cílení na uživatelsky vytvořené skupiny nebude podporovat.

    Pokud byste v současnosti chtěli pravidlo oznámení cílit na skupinu, kterou jste vytvořili pomocí konzoly správce Microsoft Intune, použijete tyto kroky:

    V pracovním prostoru **Správa** klikněte na **Pravidla oznámení** > **Vytvořit nové pravidlo**.

    V kroku 2 Průvodce vytvořením pravidla oznámení vyberte skupiny zařízení, na které bude pravidlo cílit. Tento krok (Vybrat skupiny zařízení) z konzoly Intune odebíráme.

    Předběžná časová osa pro tuto změnu je následující:
    - V srpnu 2016 se novým tenantům v Průvodci vytvořením pravidla oznámení nezobrazí krok 2. Stávající tenanty to neovlivní.
    - Zhruba v září 2016 se některým tenantům v tomto průvodci nezobrazí možnost Vybrat skupiny zařízení.
    - Přibližně od listopadu 2016 očekáváme, že se možnost Vybrat skupiny zařízení v tomto průvodci nezobrazí žádným tenantům.


- **Změny v podpoře pro aplikaci Portál společnosti pro iOS**. Od července se začne vyžadovat, aby všichni uživatelé aplikace Portál společnosti Microsoft Intune pro iOS používali její nejnovější verzi. Noví uživatelé si budou moct stáhnout jenom nejnovější verzi a aktuální uživatelé si budou muset aplikaci aktualizovat. Nejnovější verze vyžaduje iOS 8.0 nebo novější, takže zařízení se starší verzí iOS nebudou moct Portál společnosti používat ani nebudou moct zařízení zaregistrovat, dokud si v něm neaktualizují operační systém na iOS 8.0 nebo novější a následně neaktualizují i aplikaci Portál společnosti na nejnovější verzi. Zaregistrovaná zařízení se systémem iOS starším 8.0 se budou spravovat i nadále a budou se zobrazovat v konzole správce Intune.





## Předchozí verze Intune
Informace o tom, co bylo vydáno v rámci Intune během posledních šest měsíců, najdete v článku [Předchozí verze Intune](previous-intune-releases.md).
> [!div class="op_single_selector"]
- [Duben 2016](previous-intune-releases.md)
- [Březen 2016](previous-intune-releases.md)
- [Únor 2016](previous-intune-releases.md)
- [Leden 2016](previous-intune-releases.md)
- [Prosinec 2015](previous-intune-releases.md)
- [Listopad 2015](previous-intune-releases.md)




### Související témata
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Jun16_HO4-->


