---
title: "Konfigurace a nasazení zásad správy mobilních aplikací v konzole Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f33a86c51320c75ce74d20e0cac2b9581990ecec
ms.openlocfilehash: a140a2f634397440b35786e7afb3165dccc7d93e


---

# Configure and deploy mobile application management policies in the Microsoft Intune console
Zásady správy mobilních aplikací ve službě Microsoft Intune umožňují upravovat funkce aplikací, které nasazujete, a přizpůsobit je zásadám dodržování předpisů a zabezpečení vaší společnosti. Můžete třeba omezit operace vyjmutí, kopírování a vložení v rámci spravované aplikace nebo aplikaci nakonfigurovat tak, aby všechny webové odkazy otevírala ve spravovaném prohlížeči.

Podpora zásad správy mobilní aplikace:

-   Zařízení se systémem Android 4 nebo novější verzí

-   Zařízení se systémem iOS 7 nebo novější verzí

> [!TIP]
> Zásady správy mobilních zařízení podporují zařízení zaregistrovaná v Intune.
>
> Pokud hledáte informace o tom, jak vytvořit zásady správy aplikací pro zařízení, která nespravuje Intune, přečtěte si téma [Ochrana aplikačních dat pomocí zásad správy mobilních aplikací v Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

Na rozdíl od jiných zásad Intune nenasazujete zásadu správy mobilních aplikací přímo. Místo toho přidružíte zásadu k aplikaci, kterou chcete omezit. Při nasazení a instalaci aplikace na zařízení začne platit zadané nastavení.

Pokud chcete u aplikace použít omezení, musí aplikace obsahovat sadu Microsoft Intune App SDK. Tento typ aplikace se dá získat třemi způsoby:

-   **Použití aplikace se správou zásad** – Má integrovanou sadu App SDK. Pokud chcete tento typ aplikace přidat, zadáte odkaz na aplikaci z App Storu, jako je třeba iTunes Store nebo Google Play. Tento typ aplikace nevyžaduje žádné další zpracování. Podívejte se do seznamu [aplikací, které můžete použít se zásadami správy mobilních aplikací služby Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

-   **Použití „zabalené“ aplikace** – Aplikace, které jsou znovu zabalené, aby používaly sadu App SDK, pomocí nástroje **Microsoft Intune App Wrapping Tool**. Tento nástroj se obvykle používá ke zpracování interně vytvořených podnikových aplikací. Nedá se použít ke zpracování aplikací stažených z App Storu. Projděte si témata [Příprava aplikací pro iOS na správu mobilních aplikací nástrojem Microsoft Intune App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) a [Příprava aplikací pro Android na správu mobilních aplikací nástrojem Microsoft Intune App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

- **Napsání vlastní aplikace, která zahrnuje sadu Inune App SDK** – Sada Intune App SDK umožňuje začlenit funkce správy aplikací do aplikace, kterou píšete. Další informace najdete v tématu [Přehled sady Intune App SDK](/intune/develop/intune-app-sdk).

Při rozhodování mezi nástrojem App Wrapping Tool a sadou Intune App SDK vám pomůžou informace v tématu [Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

Některé spravované aplikace, třeba Outlook pro iOS a Android, podporují **víc identit**. To znamená, že Intune v dané aplikaci aplikuje nastavení správy jenom na podnikové účty nebo data.

Například v případě aplikace Outlook:

-   Pokud si uživatel nakonfiguruje podnikový a osobní e-mailový účet, Intune aplikuje nastavení správy jenom na podnikový účet a osobní účet nespravuje.

-   Pokud je zařízení vyřazené nebo odregistrované, odeberou se z něj jenom firemní data Outlooku.

-   Použitý podnikový účet musí být ten samý účet, který byl použitý k registraci zařízení v Intune.

> [!TIP]
> Pokud službu Intune používáte s nástrojem Configuration Manager, projděte si téma [Jak ovládat aplikace pomocí zásad správy mobilních aplikací v Configuration Manageru](https://technet.microsoft.com/library/mt131414.aspx).

## Vytvoření a nasazení aplikace pomocí zásady správy mobilní aplikace

-   **Krok 1:** Získejte odkaz na aplikaci spravovanou pomocí zásad, vytvořte zabalenou aplikaci nebo s využitím sady Intune App SDK napište aplikaci s podporou MAM.

-   **Krok 2:** Publikujte aplikaci do cloudového úložiště.

-   **Krok 3:** Vytvořte zásadu správy mobilní aplikace.

-   **Krok 4:** Nasaďte aplikaci a vyberte k tomu možnost přidružení aplikace pomocí zásad správy mobilní aplikace.

-   **Krok 5:** Monitorujte nasazení aplikace.

## **Krok 1:** Získejte odkaz na aplikaci spravovanou pomocí zásad, vytvořte zabalenou aplikaci nebo s využitím sady Intune App SDK napište aplikaci s podporou MAM.

-   **Pokud chcete získat odkaz na aplikaci spravovanou zásadou z obchodu s aplikacemi** – V obchodě s aplikacemi vyhledejte a poznamenejte si adresu URL aplikace spravované zásadou, kterou chcete nasadit.

    Adresa URL aplikace Microsoft Word pro iPad je třeba **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**


## **Krok 2:** Publikování aplikace do cloudového úložiště
Když publikujete spravovanou aplikaci, postupy se liší v závislosti na tom, jestli publikujete aplikaci spravovanou zásadou nebo aplikaci zpracovanou pomocí nástroje Microsoft Intune App Wrapping Tool for iOS.

#### Publikování aplikace spravované zásadami

1.  Až budete připravení nahrát aplikaci do cloudového úložiště, postupujte podle pokynů v tématu [Přidání aplikací pro mobilní zařízení v Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

2.  U aplikací pro iOS vyberte **Spravovaná aplikace pro iOS App z App Storu**v části **Vyberte, jakým způsobem má být tento software zpřístupněn pro zařízení**.

    V případě aplikací pro Android vyberte **Externí odkaz**.

3.  V části **Zadejte adresu URL**zadejte adresu URL aplikace spravované zásadou, kterou jste si předtím poznamenali.

Po dokončení nahrávání se zobrazí **Ano** u **Zásad správy aplikace** na stránce **Vlastnosti softwaru** nahrané aplikace.

Po ověření úspěšného nahrání aplikace pokračujte krokem 3.

#### Publikování aplikace zpracované pomocí nástroje Microsoft Intune App Wrapping Tool

1.  Až budete připravení nahrát aplikaci do cloudového úložiště, postupujte podle pokynů v tématu [Přidání aplikací pro mobilní zařízení v Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

2.  V části **Vyberte, jakým způsobem má být tento software zpřístupněn pro zařízení**vyberte možnost **Software Installer**.

3.  V části **Typ souboru instalačního programu softwaru** vyberte **Balíček aplikace pro systém iOS (soubor &#42.ipa)**.

Po dokončení nahrávání se zobrazí **Ano** u **Zásad správy aplikace** na stránce **Vlastnosti softwaru** nahrané aplikace.

Po ověření úspěšného nahrání aplikace pokračujte krokem 3.

## **Krok 3:** Vytvoření zásady správy mobilní aplikace

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Zásady** &gt; **Přehled** &gt; **Přidat zásadu**.

2.  Nakonfigurujte a nasaďte jednu z následujících zásad **Softwaru** v závislosti na typu zařízení, pro které chcete nakonfigurovat aplikace:

    -   **Zásady správy mobilních aplikací (Android 4 a novější)**

    -   **Zásady správy mobilních aplikací (iOS 7 a novější)**

    Můžete použít doporučená nastavení nebo nastavení upravit. Podrobnosti najdete v tématu [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Proveďte podle potřeby konfiguraci následujících nastavení. Možnosti se můžou lišit v závislosti na typu zařízení, pro které konfigurujete zásady.

|Název nastavení|Podrobnosti|
    |---------|--------------------|
    |**Název**|Zadejte název těchto zásad.|
    |**Popis**|V případě potřeby zadejte popis pro tuto zásadu.|
    |**Omezit zobrazování obsahu webu jenom na podnikový spravovaný prohlížeč**|Když je toto nastavení povolené, otevřou se ve spravované prohlížeči jakékoli odkazy v aplikaci. Aby tato možnost fungovala, musíte mít tuto aplikaci nasazenou na zařízeních.|
    |**Zabránit zálohám Androidu** nebo **Zabránit zálohám iTunes a iCloudu**|Zakáže zálohování jakýchkoliv informací z aplikace.|
    |**Povolit aplikaci přenos dat do ostatních aplikací**|Určuje aplikace, do kterých může tato aplikace může odesílat data. Můžete si vybrat, že nepovolíte přenos dat do žádné aplikace, povolíte přenos jenom do dalších spravovaných aplikací, nebo povolíte přenos do všech aplikací. Toto nastavení neřídí použití funkce **Otevřít v** na mobilních zařízeních.<br /><br />Například když nepovolíte přenos dat, omezíte přenos dat na služby, jako je zasílání zpráv SMS, přiřazování obrázků kontaktům a publikování na Facebooku nebo Twitteru.<br /><br />Pro zařízení s iOS platí, že aby se zabránilo přenosu dokumentu mezi spravovanými a nespravovanými aplikacemi, je potřeba nakonfigurovat a nasadit taky zásady zabezpečení mobilních zařízení, které zakazují nastavení **Povolit spravované dokumenty v jiných nespravovaných aplikacích**. Pokud vyberete možnost povolit jenom přenos do ostatních spravovaných aplikací, použije se k otevření obsahu příslušného typu prohlížeč Intune PDF a prohlížeč obrázků (pokud je nasazený).<br /><br />Pokud nastavíte tuto možnost na hodnotu **Aplikace spravované podle zásad** nebo **Žádné**, zablokuje se funkce iOS 9, která umožňuje vyhledávání dat Spotlight Search v rámci aplikací.|
    |**Povolit aplikaci, aby přijímala data z jiných aplikací**|Určuje aplikace, ze kterých může tato aplikace přijímat data. Můžete si vybrat, že nepovolíte přenos dat ze žádné aplikace, povolíte přenos jenom z dalších spravovaných aplikací, nebo povolíte přenos ze všech aplikací.<br /><br />Pro aplikace iOS, které podporují víc identit (kde Intune uplatňuje nastavení správy jenom na podnikové účty nebo data v aplikaci), v zaregistrovaných zařízeních s použitými zásadami správy mobilních aplikací platí, že když uživatel získá přístup k datům z aplikace, kterou nespravují zásady správy mobilních aplikací, bude se s daty zacházet jako s podnikovými daty chráněnými zásadami.|
    |**Zabránit možnosti Uložit jako**|Zakáže použít možnost **Uložit jako** k uložení dat do osobního cloudového úložiště (třeba na osobní OneDrive nebo na Dropbox) v jakékoli aplikaci, která tuto zásadu používá.|
    |**Omezit vyjmutí, kopírování a vkládání v ostatních aplikacích**|Určuje, jak se v aplikaci dají používat operace vyjmutí, kopírování a vložení. Vybírejte z těchto možností:<br /><br />**Blokované** – Nepovolujte operace vyjmutí, kopírování a vložení mezi touto a jinými aplikacemi.<br /><br />**Aplikace spravované podle zásad** – Povolí jenom operace vyjmutí, kopírování a vložení mezi touto a jinými spravovanými aplikacemi.<br /><br />**Aplikace s vložením spravované podle zásad** – Povolí vložení dat vyjmutých nebo zkopírovaných z této aplikace jenom do jiných spravovaných aplikací. Povolí vložení dat vyjmutých nebo zkopírovaných z jakékoliv aplikace do této aplikace.<br /><br />**Libovolná aplikace** – Žádná omezení operací vyjímání, kopírování a vkládání v této aplikaci.<br /><br />Aby bylo možné kopírovat a vkládat data mezi spravovanými aplikacemi, musí mít obě aplikace nakonfigurované buď nastavení **Aplikace spravované podle zásad**, nebo nastavení **Aplikace s vložením spravované podle zásad**.|
    |**Požadovat jednoduchý kód PIN pro přístup**|Vyžaduje, aby uživatel zadal číslo kódu PIN, které určí pro použití této aplikace. Uživatel bude požádán o toto nastavení při prvním spuštění aplikace.|
    |**Počet pokusů o zadání před obnovení kódu PIN**|Zadejte počet pokusů o zadání kódu PIN, které může uživatel udělat před resetováním kódu PIN.|
    |**Vyžadovat podnikové přihlašovací údaje pro přístup**|Vyžaduje, aby uživatel zadal své podnikové přihlašovací informace před tím, než může aplikaci používat.|
    |**Vyžadovat kompatibilitu zařízení dodržováním podnikových zásad pro přístup**|Umožňuje použití jenom aplikace, která se má použít, když se na zařízení nepoužil jailbreak nebo root.|
    |**Znovu zkontrolovat požadavky na přístup po (minuty)**|V poli **Časový limit** určete časové období před dalším zkontrolováním požadavků na přístup po spuštění aplikace.|
    |**Offline období odkladu**|Pokud je zařízení offline, určete časové období před opakovaným zkontrolováním požadavků na přístup k aplikaci.|
    |**Zašifrovat data aplikací**|Určuje, že všechna data přidružená k této aplikaci budou zašifrovaná, včetně data uložených externě, například na SD kartách.<br /><br />**Šifrování pro iOS**<br /><br />Pro aplikace, které jsou přidružené k zásadám správy mobilní aplikace Intune, jsou data zašifrovaná přinejmenším pomocí šifrování na úrovni zařízení poskytované operačním systémem. To zajišťuje zásada kódu PIN, kterou musí nastavit správce IT. Když se vyžaduje kód PIN, budou data zašifrovaná podle nastavení v zásadách správy mobilní aplikace. Jak uvádí dokumentace Apple, [moduly používané v iOS 7 mají certifikaci FIPS 140-2](http://support.apple.com/en-us/HT202739).<br /><br />**Šifrování pro Android**<br /><br />Pro aplikace, které jsou přidružené k zásadám správy mobilních aplikací Intune, zajišťuje šifrování Microsoft. Data jsou mezi vstupně-výstupními operacemi souborů synchronně šifrovaná.  Obsah v úložišti zařízení bude zašifrovaný vždycky. Metoda šifrování nemá certifikaci FIPS 140-2.|
    |**Blokovat snímek obrazovky** (jenom zařízení s Androidem)|Určuje, že jsou při použití této aplikace zablokované možnosti snímku obrazovky zařízení.|

4.  Po dokončení klikněte na **Uložit zásadu**.

Nová zásada se zobrazí v uzlu **Zásady konfigurace** pracovního prostoru **Zásady** .

## **Krok 4:** Přidružení aplikace k zásadě správy mobilní aplikace a nasazení aplikace
Nasaďte aplikaci a na stránce **Správa mobilních aplikací** vyberte zásadu správy mobilní aplikace, kterou chcete k aplikaci přidružit.

Podrobnosti najdete v tématu [Nasazení aplikací v Microsoft Intune](deploy-apps.md).

> [!IMPORTANT]
> Pro zařízení, která používají operační systémy starší než iOS 7.1, nebudou při odinstalaci aplikace přidružené zásady odebrané.
>
> Pokud zrušíte registraci zařízení v Intune, z aplikací se neodeberou zásady. Všechny aplikace s použitými zásadami si zachovají nastavení zásad i po odinstalaci a opakované instalaci aplikace.

### Postup v případě, že je aplikace už v zařízeních nasazená
Můžou nastat situace, kdy nasazujete aplikaci a jeden z cílových uživatelů nebo zařízení už má nainstalovanou nespravovanou verzi aplikace, například si uživatel nainstaloval Microsoft Word z obchodu s aplikacemi.

V takovém případě musíte požádat uživatele o ruční odinstalaci nespravované verze, aby se mohla nainstalovat spravovaná verze, kterou konfigurujete.

Pro zařízení se systémem iOS 9 a novějším ale Intune automaticky požádá uživatele o souhlas s převzetím správy stávající aplikace. Pokud souhlasí, stane se aplikace spravovanou aplikací služby Intune a použijí se taky všechny zásady správy mobilních aplikací přidružené aplikaci.

> [!TIP]
> Když je zařízení v dohledovém režimu, Intune převezme správu stávající aplikace bez předchozího souhlasu uživatele.

## **Krok 5:** Monitorujte nasazení aplikace.
Po vytvoření a nasazení aplikace přidružené k zásadě správy mobilní aplikace použijte následující postupy ke sledování aplikace a vyřešení konfliktů zásad.

#### Zobrazení stavu nasazení

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Skupiny** &gt; **Přehled**.

2.  Proveďte jeden z následujících kroků:

    -   Vyberte **Všichni uživatelé** a potom dvakrát klikněte na uživatele, jejichž zařízení chcete prověřit. Na stránce **Vlastnosti uživatele** vyberte **Zařízení** a dvakrát klikněte na zařízení, které chcete prověřit.

    -   Vyberte **Všechna zařízení** &gt; **Všechna mobilní zařízení**. Na stránce **Vlastnosti skupiny zařízení** vyberte **Zařízení** a dvakrát klikněte na zařízení, které chcete prověřit.

3.  Na stránce **Vlastnosti mobilního zařízení** výběrem možnosti **Zásada** zobrazte seznam zásad správy mobilní aplikace, které jsou na zařízení nasazené.

4.  Vyberte zásady správy mobilní aplikace, jejichž stav chcete zobrazit. Na podrobnosti o zásadě se můžete podívat v dolním podokně a rozbalit její uzel k zobrazení jejího nastavení.

5.  Ve sloupci **Stav** každé ze zásad správy mobilní aplikace se bude zobrazovat hodnota **Vyhovuje**, **Vyhovuje (čekání na schválení)**nebo **Chyba** . Pokud má vybraná zásada jedno nebo víc konfliktních nastavení, zobrazí se v tomto poli hodnota **Chyba** .

6.  Po zjištění konfliktu můžete nastavení konfliktní zásady zkontrolovat, jestli používá stejné nastavení, nebo můžete nasadit jednu zásadu pro aplikaci a uživatele.

### Způsob řešení konfliktů zásad
Pokud nastal konflikt zásad správy mobilní aplikace při prvním nasazení u uživatele nebo zařízení, konkrétní konfliktní hodnota nastavení se odebere ze zásady nasazené v aplikaci a aplikace bude používat integrovanou konfliktní hodnotu.

Pokud nastal konflikt zásady správy mobilní aplikace při pozdějších nasazeních aplikace nebo uživatele, konkrétní hodnota konfliktního nastavení se nebude aktualizovat na zásady správy mobilní aplikace nasazené do aplikace a aplikace bude používat stávající hodnotu tohoto nastavení.

V případech, kdy zařízení nebo uživatel obdrží dvě konfliktní zásady, platí následující chování:

-   Pokud už byla zásada nasazená na zařízení, stávající nastavení zásad se nepřepíšou.

-   Pokud ještě na zařízení nebyla nasazená žádná zásada a nasadí se dvě konfliktní nastavení, použije se výchozí nastavení zařízení.



<!--HONumber=Jun16_HO4-->


