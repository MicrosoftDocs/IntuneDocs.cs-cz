---
title: "Co je nového | Dokumentace Microsoftu"
description: "Zjistěte, co je nového v aktualizaci služby Microsoft Intune v tomto měsíci nebo dříve"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3ab53e40f4b7ea67733127f445005ecb77a404f7
ms.openlocfilehash: 37031eed6efa48ff52ec37a942fa77af414f78fe


---
# <a name="whats-new-in-microsoft-intune---january-2017"></a>Co je nového v Microsoft Intune – leden 2017
Zjistěte, co je nového v této verzi Microsoft Intune. Můžete také získat informace o nadcházejících změnách, se kterými byste měli počítat, a o minulých verzích.

> [!Note]
> Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nové funkce

<!--### Actions for non-compliance <!--730266
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.-->

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Sestavy v konzole pro MAM bez registrace <!--677961-->
Pro registrovaná i nezaregistrovaná zařízení se přidaly nové sestavy pro ochranu aplikací. Další informace o tom, jak [monitorovat zásady správy mobilních aplikací pomocí Intune, najdete tady](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

<!--### Conditional access for MAM with SharePoint Online <!--679339
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Podpora pro Android 7.1.1 <!--694397-->
Intune teď plně podporuje a spravuje Android 7.1.1.

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Řešení problému, kdy zařízení s iOSem nejsou aktivní nebo s nimi nemůže konzola správce komunikovat <!--unknown-->
Když zařízení uživatele ztratí kontakt s Intune, můžete uživateli poskytnout nový postup řešení potíží a pomoct mu tak znovu získat přístup k prostředkům společnosti. Viz [Zařízení nejsou aktivní nebo s nimi nemůže konzola správce komunikovat](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="notices"></a>Sdělení

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Změna výchozího nastavení: Správa desktopových zařízení s Windows přes nastavení Windows <!--663050-->
Výchozí chování registrace stolních počítačů s Windows 10 se mění. Nové registrace se budou provádět obvyklým tokem registrace agenta MDM, nikoli přes agenta pro počítače.

Web Portál společnosti bude uživatelům stolních počítačů s Windows 10 poskytovat pokyny k registraci, které je provedou procesem přidání stolních počítačů s Windows 10 jako mobilní zařízení. Tato změna nebude mít vliv na už zaregistrované počítače, a [pokud chcete](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune), může stolní počítače s Windows 10 vaše organizace pořád spravovat přes agenta pro počítače.

<!--### Company Portal for iOS links open inside the app <!--665954
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.-->

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Vylepšení podpory správy mobilních aplikací pro selektivní vymazávání <!--581242-->
Koncoví uživatelé získají podrobnější pokyny o tom, jak získat zpět přístup k pracovním nebo školním datům v případě, že se data automaticky odebrala kvůli zásadám Doba v offline režimu před vymazáním dat.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizace webu Portál společnosti <!--753980-->
Od února bude web Portál společnosti podporovat aplikace zaměřené na uživatele, kteří nemají spravovaná zařízení. Tento web bude podobně jako ostatní produkty a služby Microsoftu používat nové kontrastní barevné schéma a „hamburgerovou“ nabídku ![Hamburgerová nabídka webu Portál společnosti](../media/CP_hamburger_menu.png), která bude obsahovat kontaktní údaje helpdesku a informace o existujících spravovaných zařízeních. Cílová stránka bude mít nové uspořádání, které zdůrazní aplikace dostupné uživatelům – s karusely pro Vybrané a Nedávno aktualizované aplikace. Obrázky starého a nového uspořádání najdete na stránce [Co je nového v uživatelském rozhraní Portálu společnosti](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui#January_2017).

### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nová dokumentace zásad ochrany aplikací <!--583398-->
Aktualizovali jsme naši dokumentaci pro správce a vývojáře aplikací, kteří chtějí ve svých aplikacích pro iOS a Android zapnout zásady ochrany aplikací (známé jako zásady MAM) pomocí nástroje Intune App Wrapping Tool nebo sady Intune App SDK.

Aktualizovaly se tyto články:

* [Rozhodování o způsobu přípravy aplikací na jejich správu v Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Příprava aplikací pro iOS na správu mobilních aplikací přes nástroj Intune App Wrapping](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Začínáme s Microsoft Intune App SDK](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [Intune App SDK pro iOS – Příručka pro vývojáře](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

Následující články jsou v knihovně dokumentů nové:

* [Modul plug-in Cordova sady Intune App SDK](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Komponenta Xamarin sady Intune App SDK](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

<!--### Progress bar when launching the Company Portal on iOS <!--665978
The Company Portal for iOS is introducing a progress bar on the launch screen to provide the user with information about the loading processes that occur. There will be a phased rollout of the progress bar to replace the spinner. This means that some of your users will see the new progress bar while others will continue to see the spinner.-->

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Co je nového ve veřejné verzi Preview prostředí pro správu Intune v Azure<!--736542-->

Na začátku kalendářního roku 2017 provedeme migraci celého našeho prostředí pro správu do Azure, což umožní výkonnou a integrovanou správu základních pracovních postupů EMS na moderní platformě pro služby, která je rozšiřitelná pomocí rozhraní Graph API.

Noví zkušební tenanti se začnou objevovat ve veřejné verzi Preview nového prostředí pro správu na webu Azure Portal tento měsíc. Funkce a parita se stávající konzolou Intune se ve verzi Preview budou zavádět postupně.

Prostředí pro správu na webu Azure Portal bude využívat nové funkce seskupování a cílení, které už byly oznámeny. Při migraci vašeho stávajícího tenanta do nového prostředí seskupování se provede také vaše migrace do verze Preview nového prostředí pro správu vašeho tenanta. Pokud si chcete otestovat nebo prohlédnout některé nové funkce ještě před migrací vašeho tenanta, zaregistrujte si nový zkušební účet Intune nebo se podívejte na [novou dokumentaci](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

Pokud máte jakékoli dotazy k časovému plánu migrace vašeho tenanta, kontaktujte náš tým pro migraci na adrese [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Novinky ve verzi Intune v Azure najdete [zde](https://docs.microsoft.com/intune-azure/introduction/whats-new).

### <a name="see-also"></a>Viz taky
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co je nového v Azure Preview](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Co je nového v uživatelském rozhraní Portálu společnosti](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Co je nového – archiv](whats-new-archive.md)



<!--HONumber=Jan17_HO4-->


