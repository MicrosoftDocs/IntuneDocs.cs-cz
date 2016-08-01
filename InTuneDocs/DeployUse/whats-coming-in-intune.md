---
title: "Co připravujeme | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 9b536372623632b609433c49991a8bdc70e6da49


---

# Co v Microsoft Intune připravujeme – červenec
Tyto informace jsou poskytovány na základě smlouvy o utajení (NDA) ve velmi omezené míře a mohou podléhat změnám. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a mohou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moci zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se prosím na příslušný kontakt (Intune/PM).

Tato stránka se pravidelně aktualizuje. Vracejte se na ni, abyste zjistili, jaké aktualizace připravujeme.

Následující změny v Intune jsou ve vývoji. Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Správa aplikací
### Vylepšení prostředí aktualizace zřizovacího profilu aplikace
Mobilní obchodní aplikace pro Apple iOS obsahují zřizovací profil a kód podepsaný certifikátem. Když se taková aplikace spustí na zařízení s iOS, iOS potvrdí její integritu a vynutí zásady jejím definované zřizovacím profilem.

Podpisový certifikát společnosti, který se používá k podepisování aplikací, má obvykle platnost 3 roky. Platnost zřizovacího profilu ale vyprší už po jednom roce. Prostřednictvím této aktualizace vám Intune poskytne nástroje pro proaktivní nasazení nových zásad zřizovacích profilů do zařízení, ve kterých se aplikace blíží vypršení data platnosti, ale certifikát je stále platný.
<!--- TFS 1280247--->

### Podpora pro Xamarin
Sada SDK pro aplikace pro Microsoft Intune bude podporovat aplikace vyvíjené v Xamarinu v těchto scénářích:

- Vytváření nových aplikací nebo změna kódu existující podnikových aplikací pomocí sady Intune SDK. Tento modul plug-in budete moci získat na stránce [Microsoft Intune Github](https://github.com/msintuneappsdk).
- Přidání podpory správy mobilních aplikací (MAM) do existujících podnikových aplikací pomocí nástroje Intune App Wrapping

Při rozhodování o tom, jakou metodu použít, vám pomůžou informace v tématu [Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).

<!--- TFS 1061478 & TFS 1152340--->

## Správa zařízení
### Zvýšené limity pro registraci zařízení
Služba Intune zvýší maximální limit pro registraci zařízení z 5 na 15 zařízení na uživatele.
<!---TFS 1289896 --->

## Správa skupin
### Přechod od skupin Intune ke skupinám Azure Active Directory od srpna 2016
Intune vytváří nové prostředí pro správu skupin, které využívá skupiny zabezpečení Azure Active Directory (AAD) a skupiny uživatelů a zařízení v Intune. Tyto skupiny se budou využívat pro veškerou správu skupin a nasazování zásad a profilů, **až zavedeme nový portál pro správu Intune s využitím Azure**.

Toto nové prostředí vás zbaví nutnosti mít mezi službami duplicitní skupiny, **umožní přístup k některým novým funkcím skupin Azure Active Directory Premium (AADP)** a zajistí možnosti rozšíření prostřednictvím PowerShellu a Graphu. Sjednotí se tak i prostředí správy skupin napříč správou podnikové mobility.

Pro zajištění přechodu ke skupinám zabezpečení dojde v **aktuální konzole pro správu** k určitým úpravám. **Tyto změny a také použití skupin zabezpečení AAD budou popsané v dokumentaci k Intune**.

Zákazníci, kteří s Intune začínají, se s **některými změnami skupin zabezpečení setkají dříve než aktuální tenanti**.

Kromě změn ve správě skupin se také **přestanou používat následující funkce**:
- Vyloučení členů nebo skupin při vytvoření nové skupiny
- Správa skupin v roli Správce služby
- Vlastní výstrahy na základě skupin pro pravidla oznámení
- Přesun skupin v sestavách


## Portál společnosti

### Přidání oznámení na Portál společnosti pro Android
V srpnu vydáváme aktualizaci Portálu společnosti pro Android, která zavádí novou ikonu **Oznámení** na domovské stránce. Klepnutí na tuto ikonu zpřístupní stránku **Oznámení**, kde se koncovým uživatelům zobrazí všechny položky, které v aplikaci Portál společnosti vyžadují pozornost, jako je třeba to, že zařízení nedodržuje předpisy, aktualizace nebo aktivace registrace. Pokud používáte také aplikaci Portál společnosti pro iOS, už jste se s těmito oznámeními setkali. Po zavedení stránky **Oznámení** se při každém spuštění nebo obnovení Portálu společnosti pro Android už nezobrazí stránka **Nastavení firemního přístupu**, pokud je zařízení už zaregistrované. Slyšeli jsme, že celá řada z vás vytvořila pokyny pro koncové uživatele a oceníte, pokud vás předem upozorníme, že vaše pokyny nebo snímky obrazovky mohou vyžadovat aktualizaci. Proveďte prosím aktualizaci dokumentace tak, aby tuto chystanou změnu odrážela. Aktualizované snímky obrazovky najdete tady: https://aka.ms/androidcpupdate.  

### Pomoc při řešení potíží s registrací, když se nepovede Workplace Join
Na webu Portál společnosti byly zjednodušené kroky registrace pro Windows 8.1, Windows 10 Desktop a Windows 10 Mobile při použití podmíněného přístupu pro koncové uživatele, u kterých dojde k chybě Workplace Join (WPJ). Když se dřív koncoví uživatelé pokusili zaregistrovat a všechny kroky registrace se provedly úspěšně s výjimkou WPJ, zaregistrované zařízení se nezobrazilo v seznamu zařízení a uživatele to mátlo. Uživatelům se nyní zobrazí samostatné kroky Registrace zařízení a Workplace Join. Snáz tak zjistí stav svého zařízení a dokončí celý proces po chybě WPJ. Očekává se, že tyto samostatné kroky také zjednoduší proces řešení potíží pro správce IT.

### Změny účtů Správců registrace zařízení v aplikaci Portál společnosti pro iOS
Za účelem zvýšení výkonu a možností škálování již nebude Intune v aplikaci Portál společnosti pro iOS v podokně Moje zařízení zobrazovat všechna zařízení Správce registrace zařízení. Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to jenom v případě, že je zaregistrované prostřednictvím aplikace Portál společnosti. Uživatel Správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálená správa jiných zaregistrovaných zařízení se bude provádět jenom z konzoly správce Intune.  Kromě toho se v Intune místo účtů DEM začne používat buď program Apple DEP (Device Enrollment Program), nebo nástroj Apple Configurator. Obě tyto metody registrace již podporují registrace bez zásahu uživatele pro sdílená zařízení s iOS. Účty Správce registrace zařízení používejte pouze v případě, že registrace sdílených zařízení bez zásahu uživatele není dostupná.
<!---TFS 1233681--->
### Omezení instalací zkušebně načtených aplikací jenom na registrovaná zařízení s Androidem
Zařízení s Androidem už nemohou instalovat aplikace prostřednictvím webu Portál společnosti, pokud nejsou v Intune zaregistrovaná pomocí aplikace Portál společnosti Intune pro Android.
<!---TFS 1299082--->

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



<!--HONumber=Jul16_HO4-->


