---
title: zahrnout soubor
description: zahrnout soubor
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 11/19/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 9aa82268fb02f5124e48eb303f19cf32be02c284
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912624"
---
Tato oznámení obsahují důležité informace, které vám pomůžou připravit se na budoucí změny a funkce Intune.

### <a name="updated-feature-new-rbac-role-coming-to-intune--4253397--"></a>Aktualizovaná funkce: nová role RBAC přicházející do Intune<!--4253397-->
V lednu aktualizace služby Intune plánujeme v Intune uvolnit novou roli zabezpečení. Tato role se zobrazí jako "Endpoint Security Manager" v Intune a tato role je rozšířením role správce zabezpečení z Azure AD.
 
#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
V současné době jsou ve službě Azure AD k dispozici tři role pro odborníky na zabezpečení:
- Role čtenář zabezpečení ve službě Azure AD, která poskytuje přístup jen pro čtení k Intune.
- Role operátora zabezpečení ve službě Azure AD, která poskytuje přístup jen pro čtení k Intune.
- Správce zabezpečení v Azure AD. Když Intune doprovází aktualizaci z ledna, spolu s oprávněním jen pro čtení Intune, jsou nová oprávnění poskytovaná rolí služby Endpoint Security Manager následující:
    - Čtení, vytváření, aktualizace, odstraňování a přiřazování zásad dodržování předpisů pro zařízení
    - Čtení, odstraňování a aktualizace spravovaných zařízení
    - Čtení, vytváření, aktualizace, odstranění a přiřazování standardních hodnot zabezpečení
    - Čtení a aktualizace úloh zabezpečení
 
### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Zkontrolujte své role RBAC v Intune ještě dnes. Pokud aktuálně máte jenom globální správce jako role, pak se nevyžadují žádné změny. Pokud používáte role a chcete členitost, kterou poskytuje Endpoint Security Manager, pak tuto roli přiřaďte, až bude k dispozici. Aktuální informace o verzi Intune najdete na stránce [co je nového](../fundamentals/whats-new.md) v Intune. 

### <a name="updated-support-statement-for-adobe-acrobat-reader-for-intune-mobile-app--5746776--"></a>Aktualizovaný příkaz Support pro mobilní aplikaci Adobe Acrobat Reader pro Intune<!--5746776-->
V MC188653 jsme na konci srpna sdíleli, že mobilní aplikace Adobe Acrobat Reader pro Intune dosáhla konce životnosti 1. prosince 2019 a že Adobe plánuje v rámci své hlavní aplikace Acrobat Readeru podporovat zásady ochrany aplikací v Intune. Od té doby jsme dostali zpětnou vazbu od zákazníků, kterou jsme potřebovali k tomu, aby bylo možné pokračovat ve povolování IT správců, a koncovým uživatelům začít používat aplikaci Adobe Acrobat Reader pro Intune. Vzhledem k vysokému využití aplikace Adobe Acrobat Reader pro Intune na zařízeních koncových uživatelů a jejich důležitosti v podnikových scénářích chceme zajistit, aby všechny zkušenosti splňovaly požadavky vaší organizace na ochranu aplikací. 

I když ve vašich zásadách stále doporučujeme cílit na obecnou mobilní aplikaci Acrobat Reader, protože mobilní aplikace Acrobat Reader podporuje zásady ochrany aplikací a integruje sadu Intune SDK, bude i nadále podporována aplikace Adobe Acrobat Reader pro Intune. do 31. března 2020. 

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Tuto zprávu dostáváte, protože naše generování sestav indikuje, že jedna nebo více zásad ve vaší organizaci cílí na aplikaci Adobe Acrobat Reader pro Intune nebo jste dostali předchozí konce ŘÁDKUou komunikaci. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Dejte koncovým uživatelům a helpdesku o této změně. K vytvoření kanálu pro otázky související s Intune můžete použít [funkci informace o podpoře portál společnosti](../apps/company-portal-app.md#support-information) .

#### <a name="additional-information"></a>Další informace
https://helpx.adobe.com/acrobat/kb/intune-app-end-of-life.html


### <a name="end-support-for-windows-phone-81--3544909--"></a>Koncová podpora pro Windows Phone 8,1<!--3544909-->
Hlavní podpora Microsoftu pro Windows Phone 8,1 skončila v červenci 2017 a rozšířená podpora skončila v červnu 2019. Aplikace Portál společnosti pro Windows Phone 8,1 byla v režimu Sustained od října 2017. Microsoft Intune bude nyní ukončena 20. února 2020 pro Windows Phone 8,1.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Po 20. února 2020 tato zařízení neobdrží žádné aktualizace zabezpečení a nebudete moct zaregistrovat žádná nová zařízení. Stávající zařízení Windows Phone 8,1 zůstanou zaregistrovaná (zásady, aplikace, vytváření sestav), ale Všimněte si, že po tomto datu se nebude podporovat jakékoli řešení potíží s existující registrací, protože celá řada komponent, jako jsou certifikáty třetích stran, už ukončila podporu pro platformy. Intune ukončí testování kompatibility s Intune a Windows Phone 8,1.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Můžete si prohlédnout sestavy Intune a zjistit, která zařízení nebo uživatelé to mohou mít vliv. Přejděte na Zařízení > Všechna zařízení a vyfiltrujte si je podle operačního systému. Můžete přidat další sloupce, které vám pomůžou určit, kdo ve vaší organizaci má zařízení s Windows Phone 8,1. Požádejte koncové uživatele, aby svá zařízení upgradovali na podporovanou verzi operačního systému.


### <a name="take-action-use-microsoft-edge-for-your-protected-intune-browser-experience--5728447--"></a>Provést akci: použití Microsoft Edge pro chráněné prostředí Intune Browser<!--5728447-->
Vzhledem k tomu, že jsme provedli sdílení v průběhu minulého roku, Microsoft Edge Mobile podporuje stejnou sadu funkcí správy jako Managed Browser a přitom nabízí mnohem lepší prostředí pro koncové uživatele. Pro zajištění robustních funkcí poskytovaných Microsoft Edgeem Intune Managed Browser vyřazení z provozu. Od 27. ledna 2020 už Intune nebude podporovat Intune Managed Browser.  

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená? 
Od 1. února 2020 už nebude Intune Managed Browser k dispozici v Obchod Google Play nebo v obchodě s aplikacemi pro iOS. V tuto chvíli budete mít i nadále na Intune Managed Browser zacílit nové zásady ochrany aplikací, i když noví uživatelé nebudou moct aplikaci Intune Managed Browser stáhnout. V systému iOS se navíc nové webové klipy, které se odešlou do zařízení zaregistrovaného na MDM, otevřou v Microsoft Edge místo Intune Managed Browser.  

Od března 31 2020 se Intune Managed Browser odebere z konzoly Azure. To znamená, že už nebudete moct vytvářet nové zásady pro Intune Managed Browser. Pokud jste nastavili existující zásady Intune Managed Browser, nebudou ovlivněny. Intune Managed Browser se v konzole zobrazí jako obchodní aplikace bez ikony a stávající zásady se budou zobrazovat jako cílené pro aplikaci. V tuto chvíli také odebereme možnost přesměrovat webový obsah do Intune Managed Browser v části Ochrana dat v zásadách ochrany aplikací.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit? 
K zajištění hladkého přechodu z Intune Managed Browser na Microsoft Edge doporučujeme proaktivně provést následující kroky: 

1. Zaměřte se na Microsoft Edge pro iOS a Android pomocí zásad ochrany aplikací (také označovaných jako MAM) a nastavení konfigurace aplikace. Můžete znovu použít zásady Intune Managed Browser pro Microsoft Edge tím, že tyto existující zásady zacílíte i na Microsoft Edge.  
2. Zajistěte, aby všechny aplikace chráněné MAM ve vašem prostředí měly zásadu ochrany aplikací s nastavením omezit přenos webového obsahu s ostatními aplikacemi nastavenou na prohlížeče spravované zásadami. 
3. Zaměřte se na všechna MAM chráněná nastavením konfigurace spravované aplikace "com. Microsoft. Intune. useEdge" nastavenou na hodnotu true. Počínaje dalším měsícem s vydáním 1911 budete moct provádět kroky 2 a 3 jednoduše tak, že v části Ochrana dat v zásadách ochrany aplikací nastavíte možnost omezit přenos webových obsahu na jiné aplikace. . 

Připravujeme podporu pro webové klipy v iOS a Androidu. Až se tato podpora uvolní, budete muset změnit cílení na existující webové klipy, abyste se ujistili, že se otevřou na Microsoft Edge místo Managed Browser. 

#### <a name="additional-information"></a>Další informace
Další informace najdete v našich dokumentech o [používání Microsoft Edge se zásadami ochrany aplikací](../apps/manage-microsoft-edge.md) , nebo si prohlédněte náš [příspěvek blogu o podpoře](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Use-Microsoft-Edge-for-your-Protected-Intune-Browser-Experience/ba-p/1004269).


### <a name="end-of-support-for-legacy-pc-management"></a>Konec podpory pro správu starších počítačů

Podpora starší verze správy počítačů od 15. října 2020. Upgradujte zařízení na Windows 10 a znovu je zaregistrujte jako zařízení pro správu mobilních zařízení (MDM), abyste je mohli spravovat přes Intune.

[Další informace](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator"></a>Snížení podpory pro správce zařízení s Androidem 
Správce zařízení s Androidem (někdy označovaný jako "starší verze" správy Androidu a vydaný s Androidem 2,2) je způsob, jak spravovat zařízení s Androidem. Vylepšené funkce správy jsou teď ale k dispozici v [Androidu Enterprise](../enrollment/connect-intune-android-enterprise.md) (vydané s androidem 5,0). V úsilí o přechod na moderní, bohatou a bezpečnější správu zařízení bude Google v nových verzích Androidu snížit podporu Správce zařízení.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Vzhledem k těmto změnám od společnosti Google budou mít uživatelé Intune tyto možnosti:  
- Intune bude moct poskytovat úplnou podporu pro zařízení s Androidem spravovaná pomocí Správce zařízení s Androidem 10 nebo novějším prostřednictvím nástroje Q2 CY2020. Zařízení spravovaná správcem zařízení, na kterých běží Android 10 nebo novější, se nebudou moct zcela spravovat. Zvláště ovlivněná zařízení nebudou dostávat nové požadavky na heslo.
    - V tomto období nebude mít vliv na zařízení Samsung KNOX, protože prostřednictvím integrace Intune s platformou Knox je zajištěná Rozšířená podpora. Získáte tak více času k naplánování přechodu mimo správu správy zařízení.    
- Zařízení s Androidem spravovaná správcem zařízení, která zůstávají ve verzích Androidu pod Androidem 10, nebudou ovlivněná a můžou se dál spravovat pomocí Správce zařízení.    
- Pro všechna zařízení s Androidem 10 nebo novějším má Google možnost agentů správy zařízení, jako je Portál společnosti získat přístup k informacím o identifikátoru zařízení. Toto omezení má vliv na následující funkce Intune po aktualizaci zařízení na Android 10 nebo novější:  
    - Řízení přístupu k síti pro VPN už nebude fungovat.   
    - Identifikace zařízení jako vlastněných společností pomocí IMEI nebo sériového čísla nebude automaticky označovat zařízení jako ve vlastnictví firmy.  
    - IMEI a sériové číslo se už nebudou zobrazovat správcům IT v Intune. 
        > [!NOTE]
        > To má vliv jenom na zařízení spravovaná správcem zařízení s Androidem 10 a novějším a nemá vliv na zařízení spravovaná jako Android Enterprise. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Abyste se vyhnuli omezení funkčnosti přicházejícím se do třetího CY2020, doporučujeme následující:
- Nepřidávejte nová zařízení do správy Správce zařízení.
- Pokud se očekává, že zařízení obdrží aktualizaci pro Android 10, migruje ji ze správy správců zařízení na zásady pro Android Enterprise Management a/nebo ochranu aplikací.

#### <a name="additional-information"></a>Další informace
- [Pokyny pro migraci ze strany správce zařízení na Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Dokumentace ke službě Google v plánu pro zařazování rozhraní API pro správce zařízení](https://developers.google.com/android/work/device-admin-deprecation)

### <a name="plan-for-change-intune-app-sdk-and-app-protection-policies-for-android-moving-to-support-android-50-and-higher-in-an-upcoming-release---4911065---"></a>Plánování změn: sada Intune App SDK a zásady ochrany aplikací pro Android, které se přesunou na podporu Android 5,0 a vyšší v nadcházející verzi <!--4911065 -->
V nadcházející verzi se Intune přesune na podporu Androidu 5. x (Lupa) a vyšší. Aktualizujte všechny zabalené aplikace pomocí nejnovější sady Intune App SDK a aktualizujte svá zařízení.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pokud nepoužíváte nebo plánujete použít sadu SDK nebo aplikaci pro Android, tato změna vás nijak neovlivní. Pokud používáte sadu Intune App SDK, nezapomeňte aktualizovat na nejnovější verzi a také aktualizovat zařízení na Android 5. x a vyšší. Pokud aktualizace neaktualizujete, nebudou aplikace dostávat aktualizace a kvalita jejich prostředí se v průběhu času bude zmenšovat.

Níže najdete seznam běžných zařízení zaregistrovaných v Intune, na kterých běží Android verze 4. x. Pokud máte jedno z těchto zařízení, proveďte příslušné kroky, abyste se ujistili, že toto zařízení bude podporovat Android verze 5,0 nebo vyšší nebo že bude nahrazeno zařízením, které podporuje Android verze 5,0 nebo novější. Tento seznam není vyčerpávající pro všechna zařízení, která může být potřeba vyhodnotit:

- Samsung SM – T561  
- Samsung SM – T365
- Samsung GT – I9195
- Samsung SM – G800F
- Samsung SM – G357FZ
- Společnost Motorola XT1080
- Samsung GT – I9305
- Samsung SM – T231

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Zabalte své aplikace pomocí nejnovější sady Intune App SDK. Můžete také nastavit podmíněné nastavení "vyžadovat minimální verzi operačního systému (pouze upozornění)", které upozorní koncové uživatele na osobní zařízení k upgradu.

### <a name="intune-plan-for-change-nearing-end-of-support-for-windows-7---3042987---"></a>Plán změny v Intune: blíží se konec podpory pro Windows 7.<!-- 3042987 -->
Stejně jako v MC148476, který jsme odeslali v, od poslední září 2018 a znovu v MC176794 zpátky v březnu 2019, Windows 7 dosáhne konce rozšířené podpory 14. ledna 2020. V tuto chvíli Intune vyřadí podporu pro zařízení s Windows 7, takže můžeme soustředit na naši investici do podpory novějších technologií a zajistit Skvělé nové prostředí pro koncové uživatele. Po tomto datu se v Intune už nebude k dispozici technická pomoc a automatické aktualizace, které vám pomůžou chránit počítač s Windows 7. Společnost Microsoft důrazně doporučuje přejít na Windows 10 před lednem 2020, aby nedocházelo k situaci, kdy potřebujete službu nebo podporu, která už není dostupná. Další informace o životním cyklu podpory pro Windows [najdete tady](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Tuto zprávu dostáváte, protože aktuálně spravujete počítače se systémem Windows 7 pomocí starší verze softwarového agenta Intune pro počítače. Vzhledem k tomu, že zbývá méně než rok, než je prodloužená podpora Windows 7, důrazně doporučujeme vaší organizaci začít upgradovat na Windows 10, jakmile to bude možné.  

Možnosti správy počítačů se vytvářejí přímo v operačním systému Windows 10 a už nemusíte instalovat klientského agenta, jako je softwarový klient Intune pro Windows 7. Od Windows 8.1 používá společnost Microsoft architekturu správy mobilních zařízení (MDM) ke zřízení, konfiguraci, aktualizaci a správě počítačů s Windows. Když nastavíte Intune, můžete zjednodušit registraci zařízení s Windows 10 tak, že [do Intune zaregistrujete počítače s Windows 10](..\windows-enroll.md) prostřednictvím kanálu MDM. Pro správu počítačů s Windows 10 doporučujeme použít toto řešení správy MDM bez agenta.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Doporučujeme, aby vaše organizace okamžitě zvážila tento akční plán:

- Naplánujte a upgradujte loďstev Windows 7 na Windows 10 do 14. ledna 2020.
- V článku [Podpora nasazení Windows 10](https://docs.microsoft.com/windows/deployment/) najdete další informace o tom, jak upgradovat stávající loďstvo počítačů s Windows 7 na Windows 10.
- Seznamte se s tím, jak [desktopová aplikace](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure?rtc=1) nabízí nabídku inFastTrack, která vám pomůže s příslibem kompatibility aplikací Microsoftu.
- Převeďte stávající starší verze zařízení spravovaná klientským softwarem Intune do řešení doporučeného společností Microsoft pro správu Windows 10 pomocí správy MDM. Zaregistrujte všechny nové počítače s Windows 10 pomocí správy MDM pro Intune v Azure Portal.

Další informace najdete v [blogovém příspěvku](https://aka.ms/Windows7_Intune).


