---
# required metadata

title: Co připravujeme | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/17/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Co v Microsoft Intune připravujeme
Tyto informace jsou poskytovány na základě smlouvy o utajení (NDA) ve velmi omezené míře a mohou podléhat změnám. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a mohou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moci zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se prosím na příslušný kontakt (Intune/PM).

Tato stránka se pravidelně aktualizuje. Vracejte se na ni, abyste zjistili, jaké aktualizace připravujeme.

Následující změny v Intune jsou ve vývoji. Všechny tyto funkce budou také podporovány pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Komunikace služby Intune
- **Informace o stavu služby Intune.** pro Intune se přesouvá do centrálního umístění společně s ostatními službami Microsoftu. Tyto informace nyní najdete na [portálu pro správu Office 365](https://portal.office.com/Admin/Default.aspx) v části věnované stavu služby. Další informace najdete v [tomto příspěvku blogu](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

- **Přechod k uživatelskému rozhraní centra zpráv** V rámci migrace Intune do [portálu pro správu Office 365](https://portal.office.com/) začneme pro oznamování nových funkcí a pro další oznámení využívat výhod Centra zpráv. Také můžete nainstalováním mobilní doprovodné aplikace Správce Office 365 dostávat oznámení na mobilní telefon a snadno všechny zprávy přeposílat uživatelům nebo na alias distribučního seznamu.
Centrum zpráv začneme používat od květnové verze. Oznámíme vám tímto způsobem, že byly dokončeny aktualizace, a přidáme také informace o nových a vylepšených funkcích Intune. Na Centrum zpráv se můžete podívat již dnes, a to tak, že se přihlásíte na [portál pro správu Office 365](https://portal.office.com/) a v levém navigačním podokně zvolíte **Centrum zpráv**.

## Správa aplikací
- **Pro správu pomocí zásad MAM jsou teď dostupné nové aplikace.** Na zařízeních, která nejsou zaregistrovaná v Intune, je teď možné přidružit k zásadám MAM aplikace Microsoft Word, Excel a PowerPoint pro Android. Úplný seznam podporovaných aplikací najdete v galerii mobilních aplikací Microsoft Intune na stránce [aplikací pro Microsoft Intune od partnerů](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


- **Podmíněný přístup pro prohlížeč.** Budete moci nastavit zásady podmíněného přístupu pro Exchange Online a SharePoint Online, na základě kterých k nim bude možné získat přístup pouze ze spravovaných zařízení s iOS a s Androidem, která splňují pravidla zásad dodržování předpisů. Koncoví uživatelé, kteří se pokusí přihlásit k aplikaci Outlook Web Access (OWA) a webům služby SharePoint pomocí zařízení s iOS a Androidem, budou vyzváni, aby před přihlášením svoje zařízení zaregistrovali v Intune a opravili všechny problémy, kvůli kterým zařízení nesplňuje pravidla zásad dodržování předpisů.
<!---TFS 1175844--->

- **MAM SDK: Podpora konfigurace délky PIN kódu.** Bude možné zadat délku PIN kódu pro aplikace MAM podobně, jako je tomu u PIN kódu zařízení. Bude tak nutné, aby koncoví uživatelé dodrželi nová omezení, která nastavíte. Zobrazí se jim mírně upravená obrazovka pro zadání PIN kódu, ve které je teď delší pole pro jeho zadání.
<!--- TFS 1104753--->

- **Skype pro firmy pro Android.** Správci Intune nyní mohou cílit na Skype pro firmy se správou mobilních aplikací (MAM) bez zásad registrace.  Jakmile se jejich uživatelé přihlásí, aplikují se zásady MAM.
<!--- TFS item 1248444 --->

- **Skype pro firmy pro iOS.** Správci Intune nyní mohou cílit na Skype pro firmy se správou mobilních aplikací (MAM) bez zásad registrace.  Jakmile se jejich uživatelé přihlásí, aplikují se zásady MAM.
<!--- TFS item 1248443 --->

### Podpora pro Xamarin
Sada SDK pro aplikace pro Microsoft Intune teď podporuje aplikace vyvíjené v Xamarinu v těchto scénářích:

- Vytváření nových aplikací nebo změna kódu existující obchodních aplikací pomocí sady Intune SDK. Tento modul plug-in můžete získat na stránce [Microsoft Intune Github](https://github.com/msintuneappsdk).
- Přidání podpory správy mobilních aplikací (MAM) do existujících obchodních aplikací pomocí nástroje Intune App Wrapping

Při rozhodování o tom, jakou metodu použít, vám pomůžou informace v tématu [Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->


## Správa zařízení
- **Relace vzdálené pomoci pro počítače s Windows.** Integrace TeamVieweru pro desktopové počítače s Windows spravované agentem vám umožní navázat relaci vzdálené pomoci s počítači s Windows spravovanými agentem v rámci podpory, kterou oddělení helpdesku poskytuje koncovým uživatelů. To zahrnuje systém Windows 7, 8, 8.1 a Windows 10.
<!--- TFS 1284856--->



## Portál společnosti

- **Informační zprávy pro koncové uživatele.** Koncoví uživatelé nyní uvidí informační zprávy aplikace Portál společnosti pro Android, když registrují svoje zařízení nebo je odebírají z portálu společnosti.
- **Informační zpráva s identifikací zařízení bude koncovým uživatelům poskytovat další informace.** Koncoví uživatelé dokážou snadno identifikovat zařízení, které vybrali při používání webu Portál společnosti. Pokud je vybrané nesprávné zařízení, budou moci vybrat správné zařízení klepnutím na odkaz Klepněte sem v informační zprávě domovské stránky.
<!--- TFS 1231157--->

- **Změny účtů správců registrace zařízení v aplikaci Portál společnosti pro Android.** Za účelem zvýšení výkonu a možností škálování již nebude Intune v aplikaci Portál společnosti pro Android v podokně **Moje zařízení** zobrazovat všechna zařízení správce registrace zařízení (DEM). Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to jenom v případě, že je zaregistrované prostřednictvím aplikace Portál společnosti. Uživatel DEM může na místním zařízení provádět různé akce, ale vzdálenou správu jiných zaregistrovaných zařízení může provádět jenom z konzoly správce Intune.

- **Změny účtů Správců registrace zařízení v aplikaci Portál společnosti pro iOS.** Za účelem zvýšení výkonu a možností škálování už Intune v aplikaci Portál společnosti v iOS v podokně Moje zařízení nezobrazuje všechna zařízení správce registrace zařízení (DEM). Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to jenom v případě, že je zaregistrované prostřednictvím aplikace Portál společnosti. Uživatel správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálenou správu jiných zaregistrovaných zařízení je možné provádět pouze z konzoly správce Intune.  Kromě toho se v Intune místo účtů DEM začne používat buď program Apple DEP (Device Enrollment Program), nebo nástroj Apple Configurator. Obě tyto metody registrace již pro sdílená zařízení s iOS podporují registrace bez zásahu uživatele.  Účty správce registrace zařízení používejte jenom v případě, že registrace sdílených zařízení bez zásahu uživatele není dostupná.



## Zastaralá služba
**Odebrání možnosti cílení pravidel oznámení na vlastní skupiny.**
Pravidla oznámení Intune definují, komu se budou z Intune odesílat e-mailové výstrahy. V současnosti můžete nakonfigurovat pravidla oznámení pro odesílání e-mailů všem uživatelům zařízení nebo skupině zařízení služby Intune, kterou jste vytvořili. Přibližně od 1. června 2016 se už cílení na uživatelsky vytvořené skupiny nebude podporovat.

Pokud byste v současnosti chtěli pravidlo oznámení cílit na skupinu, kterou jste vytvořili pomocí konzoly správce Microsoft Intune, použijete tyto kroky:

V pracovním prostoru **Správa** klikněte na **Pravidla oznámení** > **Vytvořit nové pravidlo**.

V kroku 2 Průvodce vytvořením pravidla oznámení vyberte skupiny zařízení, na které bude pravidlo cílit. Tento krok (Vybrat skupiny zařízení) z konzoly Intune odebíráme.

Předběžná časová osa pro tuto změnu je následující:
- V červnu 2016 se novým tenantům v Průvodci vytvořením pravidla oznámení nezobrazí krok 2. Stávající tenanty to neovlivní.
- Zhruba v srpnu 2016 se některým tenantům v tomto průvodci nezobrazí možnost Vybrat skupiny zařízení.
- Přibližně od října 2016 očekáváme, že se možnost Vybrat skupiny zařízení v tomto průvodci nezobrazí žádným tenantům.

<!---   TFS 1278864--->
**Změny v podpoře pro aplikaci Portál společnosti pro iOS.**
V nadcházejících měsících bude dostupná aktualizace aplikace Portál společnosti Microsoft Intune pro iOS, která bude podporovat jenom zařízení se systémem iOS 8.0 nebo novějším. Uživatelé si nebudou moci zaregistrovat nová zařízení se systémem starším než iOS 8.0. Zaregistrovaná zařízení se systémem starším než iOS 8.0 se budou spravovat i nadále a po omezenou dobu budou moci pokračovat v používání aplikace Portálu společnosti. Pro přístup k nejnovější verzi aplikace Portál společnosti ale zařízení musí používat iOS 8.0 nebo novější. Doporučujeme vám, abyste upozornili uživatele, že k plnému využití nových funkcí služby Intune musí aktualizovat na iOS 8.0 nebo novější.  

- **Aplikace Intune Viewer.** V souvislosti s vydáním nové aplikace Sdílení RMS odebíráme od srpna 2016 následující aplikace Intune Viewer:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer pro Android z Google Play

  Místo použití aplikací Intune Viewer vám doporučujeme používat novou aplikaci Rights Management (sdílení RMS) pro Android, která pro bezpečné prohlížení firemních souborů na zařízeních s Androidem umožňuje nasadit jednu aplikaci (namísto tří samostatných aplikací). Přečtěte si víc o aplikaci Sdílení RMS (s odkazem na dokumentaci).






### Související témata
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new-in-microsoft-intune.md).


<!--HONumber=May16_HO5-->


