---
# required metadata

title: Nejčastější dotazy | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a8126cca-9ec4-454b-a20b-dc1bb6797327

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Nejčastější dotazy k Microsoft Intune
Tento článek obsahuje odpovědi na některé nejčastější dotazy týkající se služby Intune. Pokud zde nevidíte odpověď na svoji otázku, [dejte nám vědět](https://microsoftintune.uservoice.com/)..

## Běžné problémy

-   **Jak poznám, kdy se služba Intune aktualizovala?**

    Přihlaste se k svému účtu na adrese manage.microsoft.com. V části Přehled správy vyberte **Zobrazit stav služby**. Zobrazí se umístění vašeho tenanta a plán údržby. Další informace o aktualizacích služby najdete v článku [Co je nového](/intune/deploy-use/whats-new-in-microsoft-intune).

-   **Pokud uživatel přejmenuje zařízení v aplikaci Portál společnosti, změní se tento název taky v Intune nebo v Configuration Manageru?**

    Ne, tato změna názvu jenom usnadňuje práci uživatele v aplikaci.

-   **Zahrnuje Intune funkce vzdálené pomoci pro mobilní zařízení?**

    Ne. Mohly by se vám hodit aplikace nezávislých dodavatelů, jako jsou [Bomgar](http://www.bomgar.com/) nebo [TeamViewer](https://www.teamviewer.com/).

## Účty

-   **Pokud si pořídím zkušební verzi Intune a vytvořím pro ni nového tenanta, můžu pro stejného tenanta přidat taky zkušební verzi Office 365?**

    Ano. Stačí jenom, když se přihlásíte pomocí účtu globálního správce ze svého tenanta/předplatného Intune, například *globaladmin@&lt;společnost&gt;.onmicrosoft.com*..

-   **Když ve zkušebním předplatném Intune přiřadím autoritu MDM, znesnadní mi to přechod na službu jiné společnosti, pokud by se mi Intune nelíbilo?**

    Věříme tomu, že se rozhodnete u Intune zůstat, ale volba autority MDM když tak nijak nebrání tomu, abyste přešli na jinou službu. Při této volbě jde jenom o to, jestli si zvolíte Intune nebo Intune se System Center Configuration Managerem.

-   **Můžeme pro účet Intune použít náš stávající název domény v Office 365?**

    Ano. Je k tomu jenom potřeba, abyste se při vytváření zkušební verze Intune nebo aktivaci licencí přihlásili přes ID vaší organizace, které je přidružené k existujícímu tenantu Office 365 a ověřené doméně.

    Intune pak bude používat stejnou doménu, uživatele a další věci jako ve vašem účtu Office 365. Upozorňujeme ale, že jednotliví uživatelé Office 365 se musí aktivovat jako uživatelé Intune pomocí licence na Intune. Toto musí udělat globální správce, který spravuje tenanta.

## Registrace

-   **Kde můžou naši uživatelé zjistit, jak si můžou zaregistrovat svoje zařízení?**

    Můžete použít nebo si přizpůsobit informace z [pokynů k registraci koncových uživatelů služby Intune pro správce IT](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a)..

-   **Jak můžu vyřešit potíže s registrací zařízení?**

    Způsoby řešení běžných problémů s registrací jsou popsané v tématu [Řešení potíží s registrací do služby Intune](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune)..

-   **Jak můžu shromáždit protokoly registrace, když má nějaký uživatel problém s registrací?**

    Postupujte podle [těchto pokynů](http://www.microsoft.com/en-us/download/46391)..

## Správa mobilních zařízení

-   **Obecná správa mobilních zařízení**

    -   **Dokáže Intune zjistit, jestli má zařízení jailbreak?**

        Ano, u některých operačních systémů. Informace o správě zařízení s jailbreakem najdete v článku tématu [Vytváření zásad dodržování předpisů pro zařízení](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune.md)..

    -   **Můžu selektivně vymazat podniková data ze zařízení?**

        Ano. Informace o selektivním vymazání najdete v tématu [Chraňte svá data pomocí vzdáleného vymazání, vzdáleného zámku nebo resetování hesla](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune.md)..

    -   **Existuje způsob, jak prostřednictvím Intune blokovat určité weby v prohlížeči mobilního zařízení?**

        V nativním prohlížeči neexistuje na žádné platformě. Můžete ale povolit nebo blokovat adresy URL, pokud jste nasadili webový prohlížeč spravovaný službou Intune v zařízeních s iOS a Androidem. Další informace najdete v tématu [Správa přístupu k internetu pomocí zásad spravovaného prohlížeče](/intune/Deploy-Use/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md)..

    -   **Můžeme uživateli znemožnit odinstalaci aplikace?**

        Obecně ne. Na zařízeních iOS, která máte pod dohledem, ale můžete uživatelům bránit v odinstalaci aplikací distribuovaných přes Apple Configurator. 

    -   **Existuje způsob, jak spravovat využití mobilní dat?**

        Ne přímo, ale můžete zajistit, aby Wi-Fi bylo upřednostňovanou metodou pro připojení, když do zařízení zavedete profily Wi-Fi podle popisu v tématu [Pomoc uživatelům s připojením k sítím společnosti pomocí Wi-Fi profilů](/intune/Deploy-Use/wi-fi-connections-in-microsoft-intune.md). Některé platformy (třeba iOS a Android KNOX) taky umožňují určit nastavení pro hlasový a datový roaming.

    -   **Existuje způsob, jak uživateli zabránit v zrušení registrace zařízení? Co když jde o zařízení, které vlastní naše společnost?**

        Obecně to možné není. Pomocí vlastních nastavení systému Windows Phone ale můžete zabránit zrušení registrace uživatelů ve Windows Phone 8.1. Zabránit uživateli v zrušení registrace zařízení je taky možné u zařízení iOS, která jsou pod dohledem a zaregistrovaná v programu Apple DEP (Device Enrollment Program).

    -   **Můžeme si přepnout zvolenou autoritu MDM?**

        V některých situacích ano. Pokud to chcete udělat, kontaktujte podporu podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](/intune/Troubleshoot/How-to-get-support-for-Microsoft-Intune.md). Následující tabulka popisuje, jaké změny jsou možné. Po změnách autority MDM se musí znovu registrovat zařízení.

        ||**Na:** Intune!**Na:** O365|**Na:** Configuration Manager s Intune|
        |**Z:** Intune| |Ano&#42;|Ano|
        |**Z:** O365||Ano&#42;|Ano|
        |**Z:** Configuration Manager s Intune|Ano|Ano| |
        
        &#42;Autority MDM v O365 a Intune můžou existovat společně, takže nebudete muset znovu registrovat mobilní zařízení.



-   **Windows**

    -   **Můžu si zkušebně načíst aplikaci z Windows Storu?**

        Veřejně dostupné aplikace se nedají zkušebně načíst. Můžete si sice stáhnout soubor XAP, ale nemůžete ho nahrát do Intune, protože jde o veřejný soubor XAP, který je šifrovaný a podepsaný pomocí certifikátu vývojáře pro podepisování kódu. Zkušebně načíst si můžete jenom aplikace, které jste sami vyvinuli a podepsali vlastním certifikátem pro podepisování kódu.

    -   **Je u aplikací z Windows Phone Storu distribuovaných přes Portál společnosti nutné, aby měl koncový uživatel účet Microsoft?**

        Ano, bez účtu Microsoft nebude moct koncový uživatel aplikace získat. Výjimkou jsou zkušebně načtené, privátní obchodní aplikace, které jde do zařízení nasadit bez účtu Microsoft.

    -   **Vyžaduje se účet Microsoft v zařízení s Windows Phone 8.1, aby se mohlo spravovat přes Intune?**

        Ne. Je ale potřebný k instalaci většiny aplikací z veřejného obchodu.

        **Proč Windows Phone vyžaduje certifikát Symantecu pro správu?**
        Windows Phone určuje, jak můžete instalovat aplikace. Každý uživatel s účtem Microsoft může instalovat aplikace z Windows Phone Storu nebo si společnost může nainstalovat nebo zkušebně načíst svoje interně vyvinuté obchodní (LOB) aplikace během speciálního procesu popsaného v dokumentaci k Windows Phone. Při instalaci obchodních aplikací zařízení s Windows Phone důvěřují jenom jednomu speciálnímu typu certifikátu, který vydal Symantec. Nejde použít žádný jiný komerčně nebo soukromě vygenerovaný certifikát. Tento požadavek neplatí jen pro Intune, ale pro všechna řešení pro správu mobilních zařízení.

        Certifikát Symantec vytvoří token zápisu aplikace (AET). AET se může instalovat na zařízení, které je registrované pro správu mobilních zařízení, nebo se může instalovat vzdáleně ze zabezpečeného webu nebo z přílohy e-mailu. Správci musí podepsat každou obchodní aplikaci certifikátem Symantec pomocí nástrojů sady [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=268439). Když se uživatelé pokusí instalovat obchodní aplikace, operační systém Windows Phone ověří podpis v AET s podpisem na aplikaci. Pokud se podpisů shodují, může instalace pokračovat. Pokud se AET nedá ověřit, instalace se nezdaří. Tady je několik důvodů, proč nemusí dojít k ověření AET:

        -   AET nebyl nikdy na zařízení nainstalovaný.

        -   Vypršela platnost AET.

        -   AET nebyl vytvořený stejným certifikátem Symantec použitým k podepsání aplikace.

        Windows Phone nevyžaduje, aby byl AET dostupný při registraci MDM. Před vydáním verze v listopadu 2014 ale Intune vyžadovalo AET a podepsaný soubor ssp.xap, protože kromě registrace nebyl jiný způsob, jak AET a ssp.xap nainstalovat.

    **Jak se vytváří AET pro uživatele Intune?**
  Pokud správci nahrají pro svůj certifikát Symantec soubor .pfx, Intune automaticky vytvoří AET a nasadí ho na registrovaná zařízení Windows Phone. Správce Intune nemusí používat nástroj AET Generator v sadě Windows Phone SDK.

      > [!IMPORTANT]
        > Intune nepodporuje ruční vytvoření AET a jeho vzdálené nasazení.

    **Jaké změny přispěly ke snížení požadavku na certifikát Symantec?**
       U verze Intune z listopadu 2014 jsou změny, které umožní použít scénáře, kdy společnosti nemají certifikát Symantec.

       -   Firemní portál pro Windows Phone 8.1 se dá instalovat z Windows Store, takže se nemusí podepisovat certifikátem Symantec a ověřovat s AET. Místo toho se aplikace ověřuje jako součást procesu publikování na Windows Store.

        -   Zařízení Windows Phone 8.1 můžete zaregistrovat s nebo bez AET v telefonu. Pokud je AET dostupný, nainstaluje se při první synchronizaci zařízení s Intune. Pokud není dostupný žádný AET, zařízení můžete dál spravovat přes Intune a uživatelé můžou instalovat firemní portál z Windows Store a používat k podepisování aplikací většinu funkcí firemního portálu bez certifikátu Symantec.

        Požadavek Symantecu pro zařízení Windows Phone 8 se nemění. Zařízení Windows Phone 8 musí mít podepsaný soubor ssp.xap a při registraci musí použít AET, jinak se jejich registrace zablokuje.

        **Jaké funkce jsou podporované, když se registruje zařízení Windows Phone 8.1 bez certifikátu Symantec?**
        Pokud registrujete zařízení Windows Phone 8.1, ale nemáte žádný certifikát Symantec, můžete udělat tohle:

        -   Vytvořit zásady a vložit je na zařízení

        -   Nakonfigurovat kontaktní informace oddělení IT, které se zobrazí na firemním portálu

        -   Vytvořit přímé odkazy na Windows Store a nasadit je na firemní portál

        -   Vytvořit odkazy na webové stránky a nasadit je na firemní portál

        -   Vytvořit podmínky, které musí uživatelé před používáním firemního portálu přijmout

        Bez certifikátu Symantec ale nejdou nasazovat obchodní aplikace.

        > [!IMPORTANT]
        > Intune Software Publisher neověřuje, jestli jsou aplikace při nahrávání podepsané. Pokud nasazujete nepodepsané aplikace a uživatelé se je pokusí nainstalovat, bude instalace neúspěšná.

        **Co můžou uživatelé dělat, když firemní mají portál bez certifikátu Symantec?**
        Zařízení Windows Phone 8.1 se můžou registrovat až potom, co si uživatelé nainstalují firemní portál z Windows Store. Pokud není zařízení zaregistrované, zobrazí se uživatelům výzva k registraci. Když uživatelé klepnou na tuto výzvu na firemním portálu, přesměruje je to přímo na **Nastavení / Pracovní plocha**, kde si můžou svoje zařízení zaregistrovat.

        I bez registrace zařízení můžou uživatelé na firemním portálu nainstalovaném z Windows Store dělat tohle:

        -   Přijmout nebo odmítnout podmínky nakonfigurované správcem. Pokud uživatelé tyhle podmínky odmítnou, firemní portál se ukončí.

        -   Zobrazit kontaktní informace oddělení IT

        -   Zobrazit zaregistrovaná zařízení, včetně zařízení s iOS, Androidem a Windows

        -   Používat přímé odkazy na aplikace ve Windows Store

        -   Používat webové odkazy k otevírání webových stránek

        Zaregistrované zařízení můžou uživatelé vidět v seznamu **Moje zařízení** . Po registraci se na zařízení vztahují všechny nasazené zásady Intune. Abyste mohli získat AET a instalovat obchodní aplikace, musí být zařízení registrované. Když se pokusíte na nezaregistrovaném zařízení o instalaci obchodní aplikace, přesměruje vás to na registraci.

        Pokud nemá společnost certifikát Symantec, může jen instalovat obchodní aplikace nasazené správcem.

        **Naše společnost už má certifikát a registruje zařízení Windows Phone 8.1. Musím udělat něco jinak, když je teď ve Windows Store dostupný firemní portál?**
        Na zařízeních Windows Phone 8.1 pořád funguje aktuální soubor ssp.xap z webu Stažení softwaru. Můžete dál navádět uživatele, aby se zaregistrovali a získali během instalace firemní portál.

        **Jaké výhody a nevýhody přinese uživatelům stažení firemního portálu z Windows Store?**
        Výhody:

        -   Uživatelé získají přímé a webové odkazy, i když nebudou mít zaregistrované zařízení Windows Phone 8.1.

        -   Když Microsoft aktualizuje firemní portál, aplikace z Windows Store se automaticky aktualizuje, aniž byste museli stahovat, podepisovat a znovu nasazovat soubor ssp.xap

        -   Dokumentace je pro uživatele Windows Phone 8.1, iOS, Androidu a Windows konzistentní: „Přejděte na Windows Store a nainstalujte si Portál společnosti.“

        -   Uživatelé vidí aplikaci, když se instaluje, a po jejím otevření získají pokyny k registraci.

        Nevýhody:

        -   Uživatelé vidí zaškrtávací políčko pro instalaci**firemního centra**, ale v seznamu aplikací v zařízení není nic, co by je odkazovalo na firemní portál.

        -   Uživatelé můžou přijmout vlastní podmínky až po otevření firemního portálu.

        V následujících případech můžete dál odkazovat uživatele na registraci a během ní instalovat soubor ssp.xap:

        -   Pokud společnost blokuje ze zařízení Windows Phone přístup k Windows Store, musíte si při registraci nainstalovat soubor ssp.xap.

        -   Pokud uživatelé nemají na svých zařízeních Windows Phone nakonfigurovaný účet Microsoft, nebudou moct z Windows Store instalovat firemní portál.

        -   Pokud se ve stávající dokumentaci pro registraci Windows Phone uvádí, aby uživatelé nejdřív přešli na Nastavení > Pracovní plocha, může chvíli trvat, než se aktualizují dokumenty a uživatelé budou moct přejít do Windows Store.

        **Jaký je rozdíl mezi ssp.xap na webu Stažení softwaru a aplikací ve Windows Store?**

        -   K instalaci firemního portálu z Windows Store ho nemusíte podepisovat certifikátem Symantec.

        -   Firemní portál ve Windows Store zobrazí uživateli podmínky, ale ssp.xap na webu Stažení softwaru ne.

        -   Firemní portál ve Windows Store je souborem .appx, nikoli .xap.

        **Můžu si stáhnout soubor aplikace Portál společnosti a poslat ho přímo svým uživatelům a neodkazovat je na Windows Store?**
        Ano. Aplikace Portál společnosti se dá na webu Stažení softwaru stáhnout pro tyto operační systémy:

        -   Windows Phone 8.1: [http://go.microsoft.com/fwlink/?LinkId=615799](http://go.microsoft.com/fwlink/?LinkId=615799)

        -   Windows Phone 8.0 : [http://go.microsoft.com/fwlink/?LinkId=268440](http://go.microsoft.com/fwlink/?LinkId=268440)

        -   Windows 8.1: [http://go.microsoft.com/fwlink/?LinkId=615800](http://go.microsoft.com/fwlink/?LinkId=615800)

        **Můžou společnosti i nadále používat nástroj podpory pro správu zkušební verze Windows Phone ve Windows Intune, i když nemají certifikát Symantec a jejich uživatelé si chtějí nainstalovat firemní portál z Windows Store?**
        Ano. Pokud musíte udělat testování konceptu, které zahrnuje instalaci obchodních aplikací, bude nástroj pro správu zkušební verze fungovat s verzí firemního portálu z Windows Store. I když už k registraci zařízení Windows Phone 8.1 nepotřebujete AET z certifikátu Symantec, společnosti můžou otestovat instalaci aplikace přímými odkazy na aplikace ve Windows Store.

        Nástroj podpory pro správu zkušební verze Windows Phone ve Windows Intune slouží jen pro zkušební předplatné Intune.

        > [!IMPORTANT]
        > K testování používejte jen nástroj pro správu zkušební verze. Pokud už není pro nástroj pro správu zkušební verze dostupný certifikát Symantec nebo pokud společnost získá svůj vlastní certifikát Symantec pro podepisování aplikací, musí se zařízení zaregistrovaná přes AET z nástroje pro správu zkušební verze znova zaregistrovat.

        **Můžou společnosti začít s instalací bez certifikátu Symantec a později ho přidat, i když už budou zařízení Windows Phone 8.1 zaregistrovaná?**
        Ano. I když jsou už zařízení Windows Phone 8.1 zaregistrovaná, můžete získat certifikát Symantec, podepsat soubor ssp.xap a nahrát ho spolu se souborem .pfx. Intune pak vygeneruje AET. Zařízení Windows Phone 8.1 získají AET při své další synchronizaci během osmi hodin. Mezi nahráním souborů .xap a .pfx a nasazením obchodních aplikací nechte aspoň osm hodin.


-   **Android**

    -   **Jak dlouho trvá šifrování zařízení s Androidem?**

        To závisí hlavně na rychlosti procesoru a celkovém objemu paměti a množství využité paměti v zařízení a není to funkcí Intune.

-   **iOS**

    -   **Pokud se při nasazování aplikací pro iOS přes Intune načte soubor IPA a soubor manifestu aplikace, musí se pro zařízení zadat Apple ID, aby se mohlo pokračovat v instalaci?**

        Ne. Pokud bity poskytuje Intune (soubor IPA je načtený do Intune), aplikace se zkušebně načítají a nevyžadují Apple ID.

    -   **Existuje způsob, jak povolit instalaci aplikací do iOS bez povolení přístupu k Apple Storu?**

        Ne, ale můžete povolit App Store a pomocí povolených a blokovaných aplikací v iOS dohlížet na to, co uživatelé dělají. Zkušebně načtené obchodní aplikace nevyžadují přístup k Apple App Storu.

    -   **Je u aplikací z Apple Storu distribuovaných přes Portál společnosti nutné, aby měl koncový uživatel účet iTunes?**

        Ano, bez účtu iTunes nebude moct koncový uživatel aplikace získat.

    -   **Můžeme App Store zablokovat?**

        Ano, můžete, ale zablokují se tím všechny instalace a aktualizace aplikací z App Storu, ne jenom instalace a aktualizace iniciované koncovým uživatelem. To znamená, že by ani nešlo nainstalovat žádné aplikace z veřejného App Storu, které byste chtěli nasadit z Intune.

## Nasazení aplikací

-   **Jak můžu přidat doporučenou aplikaci?**

    V Intune se používá označení „vybrané aplikace“ a píše se o nich v tématu [Nasazení aplikací v Microsoft Intune](/Intune/Deploy-Use/deploy-apps-in-microsoft-intune.md)..

-   **Můžu získat dodatečné cloudové úložiště pro aplikace, které chci nasadit?**

    Ano. Můžete si o tom přečíst v tématu [Nasazení aplikací](/Intune/Deploy-Use/deploy-apps.md) v části *Požadavky na cloudové úložiště*..

## Zabezpečení

-   **Může Intune vynucovat použití BitLockeru?**

    Agent OMA-DM ve Windows 8.1/RT umožňuje přečíst (zjistit) stav šifrování. Nejde ho ale nastavit. To platí nejen pro Intune, ale i jiné služby pro správu mobilních zařízení.

-   **Pokud tablet s Windows 8 šifruji pomocí BitLockeru, můžu vynutit úplné vymazání zařízení v případě, že se uživateli několikrát po sobě nepodaří přihlásit se?**

    V zařízeních s Windows 8.1/RT není žádná možnost pro úplné vymazání v žádné službě pro správu mobilních zařízení včetně Intune. Intune pro tato zařízení poskytuje selektivní vymazání. Další informace o vymazání / selektivním vymazání v Intune najdete v tématu [Ochrana dat a aplikací pomocí Microsoft Intune](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md)..

## Portál společnosti

-   **Je možné přizpůsobení Portálu společnosti?**

    Ano. V konzole správce Intune najdete tato nastavení v sekci **Správce&gt;Portál společnosti**.

## Microsoft Intune s Configuration Managerem

-   **Když se používá Configuration Manager s Intune, kde se spravují zařízení?**

    Spravujte všechny vaše zařízení z konzoly Configuration Manageru, i přes to, že zařízení s instalovaným agentem Intune se zobrazí v konzole Intune. Mobilní zařízení se v konzole Intune nezobrazí.

-   **Jde na zařízeních provést selektivní vymazání?**

    Pokud společně s Intune používáte System Center 2012 R2 Configuration Manager nebo novější, můžete provést selektivní vymazání, kterým se odeberou firemní data. Další informace najdete v tématu [Ochrana dat a aplikací pomocí Microsoft Intune](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md)..

-   **Pokud používám Configuration Manager s Intune, můžu dál používat portál pro správu Intune?**

    Ano, ale z tohoto portálu bude možné spravovat jenom počítače s nainstalovaným agentem Intune. Na portálu jsou taky některé další užitečné informace týkající se výstrah o službě, stavu služby atd., ale žádné nastavení správy zařízení z něj nebude platit pro registrovaná zařízení.



<!--HONumber=May16_HO1-->


