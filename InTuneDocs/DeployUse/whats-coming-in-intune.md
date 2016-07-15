---
title: "Co připravujeme | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 06/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
ms.sourcegitcommit: b203f51171d38f2b0fc2b46e556679322701d29b
ms.openlocfilehash: 77d2e74dcb032ff52808998c56de7d6b8847ebbe


---

# Co v Microsoft Intune připravujeme
Tyto informace jsou poskytovány na základě smlouvy o utajení (NDA) ve velmi omezené míře a mohou podléhat změnám. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a mohou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moci zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se prosím na příslušný kontakt (Intune/PM).

Tato stránka se pravidelně aktualizuje. Vracejte se na ni, abyste zjistili, jaké aktualizace připravujeme.

Následující změny v Intune jsou ve vývoji. Všechny tyto funkce budou také podporovány pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Správa aplikací
- **Vylepšení prostředí pro konfiguraci datových zásad systému Windows 10 Enterprise.** Vylepšili jsme prostředí pro konfiguraci datových zásad systému Windows 10 Enterprise související s vytvářením pravidel aplikací a zadáváním definice mezí sítě a dalších nastavení pro ochranu podnikových dat.
<!---TFS 1303011--->

- **Podmíněný přístup pro prohlížeč.** Bude moct nastavit zásady podmíněného přístupu pro Exchange Online a SharePoint Online, na základě kterých k nim bude možné získat přístup pouze ze spravovaných zařízení s iOS a s Androidem, která splňují pravidla zásad dodržování předpisů. Koncoví uživatelé, kteří se pokusí přihlásit k aplikaci Outlook Web Access (OWA) a webům služby SharePoint pomocí zařízení s iOS a Androidem, budou vyzváni, aby před přihlášením svoje zařízení zaregistrovali v Intune a opravili všechny problémy, kvůli kterým zařízení nesplňuje pravidla zásad dodržování předpisů.
<!---TFS 1175844--->

- **Dynamics CRM Online podporuje podmíněný přístup.** Zákazníci budou moci pro Dynamics CRM Online nastavit zásady podmíněného přístupu, aby k němu měla přístup pouze spravovaná a kompatibilní zařízení s iOS a Androidem. Koncovým uživatelům, kteří se pokusí přihlásit k mobilní aplikaci Dynamics CRM na iOS a Androidu, se zobrazí výzva, aby si před přihlášením zařízení zaregistrovali v Intune a aby vyřešili všechny problémy, kvůli kterým zařízení není v souladu s pravidly zásad dodržování předpisů v organizaci.
<!---TFS1295358--->

### Podpora pro Xamarin
Sada SDK pro aplikace pro Microsoft Intune bude podporovat aplikace vyvíjené v Xamarinu v těchto scénářích:

- Vytváření nových aplikací nebo změna kódu existující podnikových aplikací pomocí sady Intune SDK. Tento modul plug-in budete moci získat na stránce [Microsoft Intune Github](https://github.com/msintuneappsdk).
- Přidání podpory správy mobilních aplikací (MAM) do existujících podnikových aplikací pomocí nástroje Intune App Wrapping

Při rozhodování o tom, jakou metodu použít, vám pomůžou informace v tématu [Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->

## Správa zařízení
- **Nastavení zásad programu Windows Defender pro ochranu proti potenciálně nežádoucím aplikacím.** Do obecné konfigurace zásady pro Windows 10 Desktop a Mobile bylo přidáno nové nastavení programu Windows Defender nazvané **Detekce potenciálně nežádoucích aplikací**. Pomocí tohoto nastavení můžete ochránit zaregistrované stolní počítače s Windows před spuštěním softwaru, který Windows Defender klasifikuje jako potenciálně nežádoucí. Můžete nastavit ochranu před spuštěním těchto aplikací nebo pomocí režimu auditu upozornit, když se potenciálně nežádoucí aplikace nainstaluje.
<!---TFS 1244478--->

## Podmíněný přístup
**Zásady řízení přístupu k síti Cisco ISE pro Intune.**  Zákazníci, kteří používají Cisco Identity Service Engine (ISE) 2.1 a také Microsoft Intune, mohou v modulu ISE nastavit zásady řízení přístupu k síti.

Když se použijí tyto zásady, zařízení, která se připojují k síti pomocí WiFi nebo VPN, musí splňovat následující podmínky, jinak jim nebude povolen přístup:

* Musí být spravovaná pomocí Intune.
* Musí splňovat veškeré nasazené zásady dodržování předpisů Intune.

Koncovým uživatelům nevyhovujících zařízení se zobrazí výzva k registraci. Pokud chtějí získat přístup, musí všechny problémy s dodržováním předpisů vyřešit.
<!---TFS 1299144--->

## Portál společnosti
**Změny účtů Správců registrace zařízení v aplikaci Portál společnosti pro iOS.** Za účelem zvýšení výkonu a možností škálování již nebude Intune v aplikaci Portál společnosti pro iOS v podokně Moje zařízení zobrazovat všechna zařízení Správce registrace zařízení. Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to jenom v případě, že je zaregistrované prostřednictvím aplikace Portál společnosti. Uživatel Správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálená správa jiných zaregistrovaných zařízení se bude provádět jenom z konzoly správce Intune.  Kromě toho se v Intune místo účtů DEM začne používat buď program Apple DEP (Device Enrollment Program), nebo nástroj Apple Configurator. Obě tyto metody registrace již podporují registrace bez zásahu uživatele pro sdílená zařízení s iOS. Účty Správce registrace zařízení používejte pouze v případě, že registrace sdílených zařízení bez zásahu uživatele není dostupná.
<!---TFS 1233681--->

## Zastaralá služba
**Aplikace Portál společnosti pro Windows 8 a Windows Phone 8 se od září 2016 přestanou používat.** Od září 2016 přestane Microsoft Intune podporovat aplikace Portál společnosti Microsoft Intune pro platformy Windows Phone 8 a Windows 8. Pokud budete chtít do zařízení s těmito systémy dál distribuovat aplikace, aktualizujte si zařízení na Windows 8.1 a Windows Phone 8.1 a začněte používat odpovídající aplikaci Portál společnosti pro Windows 8.1 a Windows Phone 8.1.
<!---TFS 1255391--->

**Odebrání možnosti cílení pravidel oznámení na vlastní skupiny.**
Pravidla oznámení Intune definují, komu se budou z Intune odesílat e-mailové výstrahy. V současnosti můžete nakonfigurovat pravidla oznámení pro odesílání e-mailů všem uživatelům zařízení nebo skupině zařízení služby Intune, kterou jste vytvořili. Přibližně od 1. června 2016 se už cílení na uživatelsky vytvořené skupiny nebude podporovat.

Předběžná časová osa pro tuto změnu je následující:
- V srpnu 2016 se novým tenantům v Průvodci vytvořením pravidla oznámení nezobrazí krok 2. Stávající tenanty to neovlivní.
- Zhruba v září 2016 se některým tenantům v tomto průvodci nezobrazí možnost Vybrat skupiny zařízení.
- Přibližně od listopadu 2016 očekáváme, že se možnost Vybrat skupiny zařízení v tomto průvodci nezobrazí žádným tenantům.
<!---   TFS 1278864--->

**Změny v podpoře pro aplikaci Portál společnosti pro iOS.**
Od července se začne vyžadovat, aby všichni uživatelé aplikace Portál společnosti Microsoft Intune pro iOS používali její nejnovější verzi. Noví uživatelé si budou moct stáhnout jenom nejnovější verzi a aktuální uživatelé si budou muset aplikaci aktualizovat. Nejnovější verze vyžaduje iOS 8.0 nebo novější, takže zařízení se starší verzí iOS nebudou moct Portál společnosti používat ani nebudou moct zařízení zaregistrovat, dokud si v něm neaktualizují operační systém na iOS 8.0 nebo novější a následně neaktualizují i aplikaci Portál společnosti na nejnovější verzi. Zaregistrovaná zařízení se systémem iOS starším 8.0 se budou spravovat i nadále a budou se zobrazovat v konzole správce Intune.  

**Aplikace Intune Viewer.** V souvislosti s vydáním nové aplikace Sdílení RMS odebíráme od srpna 2016 následující aplikace Intune Viewer:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer pro Android z Google Play

Místo použití aplikací Intune Viewer vám doporučujeme používat novou aplikaci Rights Management (sdílení RMS) pro Android, která pro bezpečné prohlížení firemních souborů na zařízeních s Androidem umožňuje nasadit jednu aplikaci (namísto tří samostatných aplikací). Přečtěte si víc o aplikaci Sdílení RMS (s odkazem na dokumentaci).


### Související témata
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Jul16_HO1-->


