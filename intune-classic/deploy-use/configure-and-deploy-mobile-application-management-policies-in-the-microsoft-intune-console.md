---
title: "Konfigurace zásad MAM v konzole Intune | Dokumentace Microsoftu"
description: "Zásady správy mobilních aplikací ve službě Microsoft Intune umožňují upravovat funkce aplikací, které nasazujete, a přizpůsobit je zásadám dodržování předpisů a zabezpečení vaší společnosti."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 65b2eb20aea4bbadba9d470590b6c344ac37b9f5
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console"></a>Configure and deploy mobile application management policies in the Microsoft Intune console

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Zásady správy mobilních aplikací (MAM) ve službě Microsoft Intune umožňují upravovat funkce aplikací, které nasazujete, a přizpůsobit je zásadám dodržování předpisů a zabezpečení vaší společnosti. Můžete třeba omezit operace vyjmutí, kopírování a vložení v rámci spravované aplikace nebo aplikaci nakonfigurovat tak, aby všechny webové odkazy otevírala ve spravovaném prohlížeči.

Podpora zásad správy mobilní aplikace:

-   Zařízení se systémem Android 4 nebo novější verzí

-   Zařízení, na kterých běží iOS 8.0 a novější

> [!TIP]
> Zásady správy mobilních zařízení podporují zařízení zaregistrovaná v Intune.
>
> Pokud hledáte informace o tom, jak vytvořit zásady správy aplikací pro zařízení, která nespravuje Intune, přečtěte si téma [Ochrana aplikačních dat pomocí zásad správy mobilních aplikací v Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

Na rozdíl od jiných zásad Intune nenasazujete zásadu správy mobilních aplikací přímo. Místo toho přidružíte zásadu k aplikaci, kterou chcete omezit. Při nasazení a instalaci aplikace na zařízení začne platit zadané nastavení.

Pokud chcete u aplikace použít omezení, musí aplikace obsahovat sadu Microsoft Intune App SDK. Tento typ aplikace se dá získat třemi způsoby:

-   **Použijte aplikaci spravovanou zásadami**. Aplikace spravovaná zásadami má integrovanou sadu App SDK. Pokud chcete tento typ aplikace přidat, zadáte odkaz na aplikaci z App Storu, jako je třeba iTunes Store nebo Google Play. Tento typ aplikace nevyžaduje žádné další zpracování. Další informace najdete v [seznamu aplikací, které můžete použít se zásadami správy mobilních aplikací služby Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

-   **Použijte zabalenou aplikaci**. Zabalená aplikace je aplikace, která je znovu zabalená, aby zahrnovala sadu App SDK, pomocí nástroje Microsoft Intune App Wrapping Tool. Tento nástroj se obvykle používá ke zpracování interně vytvořených podnikových aplikací. Nedá se použít ke zpracování aplikací stažených z App Storu. Další informace najdete v tématu [Příprava aplikací pro iOS na správu mobilních aplikací nástrojem Microsoft Intune App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) a [Příprava aplikací pro Android na správu mobilních aplikací nástrojem Microsoft Intune App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

- **Napište vlastní aplikaci, která zahrnuje sadu Intune App SDK**. Sada Intune App SDK umožňuje začlenit funkce správy aplikací do aplikace, kterou píšete. Další informace najdete v tématu [Přehled sady Intune App SDK](/intune-classic/develop/intune-app-sdk).

Při rozhodování mezi nástrojem App Wrapping Tool a sadou Intune App SDK vám pomůžou informace v tématu [Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

Některé spravované aplikace, třeba Outlook pro iOS a Android, podporují *víc identit*. To znamená, že Intune v dané aplikaci aplikuje nastavení správy jenom na podnikové účty nebo data.

Například v případě aplikace Outlook:

-   Pokud si uživatel nakonfiguruje podnikový e-mailový účet a osobní e-mailový účet, Intune aplikuje nastavení správy jenom na podnikový účet a osobní účet nespravuje.

-   Pokud je zařízení vyřazené nebo odregistrované, odeberou se z něj jenom firemní data Outlooku.

-   Podnikový účet musí být ten samý účet, který byl použitý k registraci zařízení v Intune.

> [!TIP]
> Pokud službu Intune používáte s nástrojem Configuration Manager, projděte si téma [Jak ovládat aplikace pomocí zásad správy mobilních aplikací v Configuration Manageru](https://technet.microsoft.com/library/mt131414.aspx).

## <a name="create-and-deploy-an-app-with-a-mobile-application-management-policy"></a>Vytvoření a nasazení aplikace pomocí zásady správy mobilní aplikace

-   **Krok 1:** Získejte odkaz na aplikaci spravovanou pomocí zásad, vytvořte zabalenou aplikaci nebo s využitím sady Intune App SDK napište aplikaci s podporou MAM.

-   **Krok 2:** Publikujte aplikaci do cloudového úložiště.

-   **Krok 3:** Vytvořte zásadu správy mobilní aplikace.

-   **Krok 4:** Přidružte aplikaci k zásadě správy mobilních aplikací a pak aplikaci nasaďte.

-   **Krok 5:** Monitorujte nasazení aplikace.

## <a name="step-1-get-the-link-to-a-policy-managed-app-create-a-wrapped-app-or-use-the-intune-app-sdk-to-write-a-mam-enabled-app"></a>Krok 1: Získání odkazu na aplikaci spravovanou pomocí zásad, vytvoření zabalené aplikace nebo napsání aplikace s podporou MAM s využitím sady Intune App SDK

V App Storu vyhledejte a poznamenejte si adresu URL aplikace spravované zásadami, kterou chcete nasadit. Adresa URL aplikace Microsoft Word pro iPad je třeba **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.


## <a name="step-2-publish-the-app-to-your-cloud-storage-space"></a>Krok 2: Publikování aplikace do cloudového úložiště
Když publikujete spravovanou aplikaci, postupy se liší v závislosti na tom, jestli publikujete aplikaci spravovanou zásadou nebo aplikaci zpracovanou pomocí nástroje Microsoft Intune App Wrapping Tool for iOS.

#### <a name="to-publish-a-policy-managed-app"></a>Publikování aplikace spravované zásadami

1.  Až budete připravení nahrát aplikaci do cloudového úložiště, postupujte podle pokynů v tématu [Přidání aplikací pro mobilní zařízení v Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

2.  U aplikací pro iOS vyberte **Spravovaná aplikace pro iOS App z App Storu** v části **Vyberte, jakým způsobem má být tento software zpřístupněn pro zařízení**.

    V případě aplikací pro Android vyberte **Externí odkaz**.

3.  V části **Zadejte adresu URL**zadejte adresu URL aplikace spravované zásadou, kterou jste si předtím poznamenali.

Po dokončení nahrávání se zobrazí **Ano** u **Zásad správy aplikace** na stránce **Vlastnosti softwaru** nahrané aplikace.

Po ověření úspěšného nahrání aplikace pokračujte krokem 3.

#### <a name="to-publish-an-app-that-was-processed-through-the-microsoft-intune-app-wrapping-tool"></a>Publikování aplikace zpracované pomocí nástroje Microsoft Intune App Wrapping Tool

1.  Až budete připravení nahrát aplikaci do cloudového úložiště, postupujte podle pokynů v tématu [Přidání aplikací pro mobilní zařízení v Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

2.  V části **Vyberte, jakým způsobem má být tento software zpřístupněn pro zařízení** vyberte možnost **Instalační program softwaru**.

3.  V části **Typ souboru instalačního programu softwaru** vyberte **Balíček aplikace pro systém iOS (soubor &#42.ipa)**.

Po dokončení nahrávání se zobrazí **Ano** u **Zásad správy aplikace** na stránce **Vlastnosti softwaru** nahrané aplikace.

Po ověření úspěšného nahrání aplikace pokračujte krokem 3.

## <a name="step-3-create-a-mobile-application-management-policy"></a>Krok 3: Vytvoření zásady správy mobilních aplikací

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Zásady** &gt; **Přehled** &gt; **Přidat zásadu**.

2.  Nakonfigurujte a nasaďte jednu z následujících zásad **Softwaru** v závislosti na typu zařízení, pro které chcete nakonfigurovat aplikace:

    -   **Zásady správy mobilních aplikací (Android 4 a novější)**

    -   **Zásady správy mobilních aplikací (iOS 8.0 a novější)**

    Můžete použít doporučená nastavení nebo nastavení upravit. Podrobnosti najdete v tématu [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Proveďte podle potřeby konfiguraci následujících nastavení. Možnosti se můžou lišit v závislosti na typu zařízení, pro které konfigurujete zásady.

|Název nastavení|Podrobnosti|
    |---------|--------------------|
    |**Název**|Zadejte název těchto zásad.|
    |**Popis**|V případě potřeby zadejte popis pro tuto zásadu.|
    |**Omezit zobrazování obsahu webu jenom na podnikový spravovaný prohlížeč**|Když je toto nastavení povolené, jakékoli odkazy v aplikaci se otevřou ve spravovaném prohlížeči. Aby tato možnost fungovala, musíte mít tuto aplikaci nasazenou na zařízeních.|
    |**Zabránit zálohám Androidu** nebo **Zabránit zálohám iTunes a iCloudu**|Toto nastavení zakáže zálohování jakýchkoliv informací z aplikace.|
    |**Povolit aplikaci přenos dat do ostatních aplikací**|Toto nastavení určuje aplikace, do kterých může tato aplikace může odesílat data. Můžete si vybrat, že nepovolíte přenos dat do žádné aplikace, povolíte přenos jenom do dalších spravovaných aplikací, nebo povolíte přenos do všech aplikací. <br /><br />Například když nepovolíte přenos dat, omezíte přenos dat na služby, jako je zasílání zpráv SMS, přiřazování obrázků kontaktům a publikování na Facebooku nebo Twitteru.<br /><br />Pro zařízení iOS platí, že aby se zabránilo přenosu dokumentu mezi spravovanými a nespravovanými aplikacemi, je nutné nakonfigurovat a nasadit taky zásady zabezpečení mobilního zařízení, které zakazují nastavení **Povolit spravované dokumenty v dalších nespravovaných aplikacích**. Pokud vyberete možnost povolit přenos jenom do ostatních spravovaných aplikací, použije se k otevření obsahu příslušného typu prohlížeč Intune PDF a prohlížeč obrázků (pokud je nasazený).<br /><br />Pokud nastavíte tuto možnost na hodnotu **Aplikace spravované podle zásad** nebo **Žádné**, bude blokovaná funkce iOS 9, která umožňuje vyhledávání Spotlight dat v rámci aplikací.<br><br>Toto nastavení neřídí použití funkce Otevřít v na mobilních zařízeních. Informace ke správě funkce Otevřít v najdete v tématu [Správa přenosu dat mezi aplikacemi pro iOS pomocí Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).|
    |**Povolit aplikaci, aby přijímala data z jiných aplikací**|Toto nastavení určuje aplikace, ze kterých může tato aplikace přijímat data. Můžete si vybrat, že nepovolíte přenos dat ze žádné aplikace, povolíte přenos jenom z dalších spravovaných aplikací, nebo povolíte přenos ze všech aplikací.<br /><br />Když uživatel získá přístup k datům z aplikace, kterou nespravují zásady správy mobilních aplikací, bude se s daty zacházet jako s podnikovými daty chráněnými zásadami. To platí pro aplikace pro iOS, které podporují víc identit (kde Intune v dané aplikaci aplikuje nastavení správy jenom na podnikové účty nebo data). Nebo to platí pro registrované zařízení s aplikovanou zásadou správy mobilních aplikací.|
    |**Zabránit možnosti Uložit jako**|Toto nastavení zakáže použití možnosti **Uložit jako** k uložení dat do osobního cloudového úložiště (třeba na OneDrive nebo na Dropbox) v jakékoli aplikaci, která tuto zásadu používá.|
    |**Omezit vyjmutí, kopírování a vkládání v ostatních aplikacích**|Toto nastavení určuje, jak se v aplikaci dají používat operace vyjmutí, kopírování a vložení. Vybírejte z těchto možností:<br /><br />**Blokované**. Nepovolujte operace vyjmutí, kopírování a vložení mezi touto a jinými aplikacemi.<br /><br />**Aplikace spravované podle zásad**. Povolí operace vyjmutí, kopírování a vložení jenom mezi touto a jinými spravovanými aplikacemi.<br /><br />**Aplikace s vložením spravované podle zásad**. Povolí vložení dat vyjmutých nebo zkopírovaných z této aplikace jenom do jiných spravovaných aplikací. Povolí vložení dat vyjmutých nebo zkopírovaných z jakékoliv aplikace do této aplikace.<br /><br />**Libovolná aplikace**. Nedává žádná omezení operací vyjímání, kopírování a vkládání v této aplikaci.<br /><br />Aby bylo možné kopírovat a vkládat data mezi spravovanými aplikacemi, musí mít obě aplikace nakonfigurované buď nastavení **Aplikace spravované podle zásad**, nebo nastavení **Aplikace s vložením spravované podle zásad**.|
    |**Požadovat jednoduchý kód PIN pro přístup**|Toto nastavení vyžaduje, aby uživatel zadal kód PIN, který určí pro použití této aplikace. Uživatel bude požádán o toto nastavení při prvním spuštění aplikace.|
    |**Počet pokusů o zadání před obnovení kódu PIN**|Zadejte počet pokusů o zadání kódu PIN, které může uživatel udělat před resetováním kódu PIN.|
    |**Vyžadovat podnikové přihlašovací údaje pro přístup**|Toto nastavení vyžaduje, aby uživatel zadal své podnikové přihlašovací informace před tím, než může aplikaci používat.|
    |**Vyžadovat kompatibilitu zařízení dodržováním podnikových zásad pro přístup**|Toto nastavení umožňuje použití aplikace, jenom když zařízení nemá jailbreak nebo root.|
    |**Znovu zkontrolovat požadavky na přístup po (minuty)**|V poli **Časový limit** určete časové období před dalším zkontrolováním požadavků na přístup po spuštění aplikace.|
    |**Období odkladu pro offline režim**|Pokud je zařízení offline, určete časové období před opakovaným zkontrolováním požadavků na přístup k aplikaci.|
    |**Zašifrovat data aplikací**|Toto nastavení určuje, že všechna data přidružená k této aplikaci budou zašifrovaná. To zahrnuje i data uložená externě, například na SD kartách.<br /><br />**Šifrování pro iOS**<br /><br />Pro aplikace, které jsou přidružené k zásadám správy mobilních aplikací Intune, jsou neaktivní uložená data zašifrovaná pomocí šifrování na úrovni zařízení poskytované operačním systémem. To zajišťuje zásada kódu PIN, kterou nastavuje správce IT. Když se vyžaduje kód PIN, budou data zašifrovaná podle nastavení v zásadách správy mobilních aplikací. Jak se uvádí v dokumentaci společnosti Apple, [moduly používané v iOSu mají certifikaci FIPS 140-2](http://support.apple.com/HT202739).<br /><br />**Šifrování pro Android**<br /><br />Pro aplikace, které jsou přidružené k zásadám správy mobilních aplikací Intune, zajišťuje šifrování Microsoft. Data jsou mezi vstupně-výstupními operacemi souborů synchronně šifrovaná.  Obsah v úložišti zařízení bude zašifrovaný vždycky. Metodou šifrování je FIPS 140-2, která je kompatibilní pouze se zařízeními Samsung KNOX.|
    |**Blokovat snímek obrazovky** (jenom zařízení s Androidem)|Toto nastavení určuje, že jsou při použití této aplikace zablokované možnosti snímku obrazovky zařízení.|

4. Po dokončení klikněte na **Uložit zásadu**.

Nová zásada se zobrazí v uzlu **Zásady konfigurace** pracovního prostoru **Zásady**.

## <a name="step-4-associate-the-app-with-a-mobile-application-management-policy-and-then-deploy-the-app"></a>Krok 4: Přidružení aplikace k zásadě správy mobilní aplikace a nasazení aplikace
Abyste přidružili zásadu správy mobilních aplikací k aplikaci, vyberte zásadu na stránce **Správa mobilních aplikací** dialogového okna **Spravovat nasazení**.

Podrobnosti najdete v tématu [Nasazení aplikací v Microsoft Intune](deploy-apps.md).

> [!IMPORTANT]
> Pokud se registrace zařízení v Intune zruší, zásady se z aplikací neodeberou. Aplikace, u kterých se použily zásady, si zachovají nastavení zásad i po jejich odinstalování a opětovném nainstalování.

### <a name="what-to-do-when-an-app-is-already-deployed-on-devices"></a>Postup v případě, že je aplikace už v zařízeních nasazená
Můžou nastat situace, kdy nasazujete aplikaci a jeden z cílových uživatelů nebo zařízení už má nainstalovanou nespravovanou verzi aplikace. Například si uživatel mohl nainstalovat Microsoft Word z obchodu s aplikacemi.

V takovém případě musíte požádat uživatele o ruční odinstalaci nespravované verze, aby se mohla nainstalovat spravovaná verze, kterou konfigurujete.

Pro zařízení se systémem iOS 9 a novějším ale Intune automaticky požádá uživatele o souhlas s převzetím správy stávající aplikace. Pokud souhlasí, stane se aplikace spravovanou aplikací služby Intune a použijí se taky všechny zásady správy mobilních aplikací přidružené aplikaci.

> [!TIP]
> Když je zařízení v dohledovém režimu, Intune převezme správu stávající aplikace bez předchozího souhlasu uživatele.

## <a name="step-5-monitor-the-app-deployment"></a>Krok 5: Sledování nasazení aplikace
Po vytvoření a nasazení aplikace přidružené k zásadě správy mobilních aplikací použijte následující postupy ke sledování aplikace a vyřešení případných konfliktů zásad.

#### <a name="to-view-the-status-of-the-deployment"></a>Zobrazení stavu nasazení

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Skupiny** &gt; **Přehled**.

2.  Proveďte jeden z následujících kroků:

    -   Vyberte **Všichni uživatelé** a potom dvakrát klikněte na uživatele, jehož zařízení chcete prověřit. Na stránce **Vlastnosti uživatele** vyberte **Zařízení** a dvakrát klikněte na zařízení, které chcete prověřit.

    -   Vyberte **Všechna zařízení** &gt; **Všechna mobilní zařízení**. Na stránce **Vlastnosti skupiny zařízení** vyberte **Zařízení** a dvakrát klikněte na zařízení, které chcete prověřit.

3.  Na stránce **Vlastnosti mobilního zařízení** výběrem možnosti **Zásada** zobrazte seznam zásad správy mobilní aplikace, které jsou na zařízení nasazené.

4.  Vyberte zásady správy mobilní aplikace, jejichž stav chcete zobrazit. Na podrobnosti o zásadě se můžete podívat v dolním podokně a rozbalit její uzel k zobrazení jejího nastavení.

5.  Ve sloupci **Stav** každé ze zásad správy mobilních aplikací se bude zobrazovat hodnota **Vyhovuje**, **Vyhovuje (čekání na schválení)**nebo **Chyba**. Pokud má vybraná zásada jedno nebo víc konfliktních nastavení, zobrazí se v tomto poli hodnota **Chyba**.

6.  Po zjištění konfliktu můžete nastavení konfliktní zásady zkontrolovat, jestli používá stejné nastavení, nebo můžete nasadit jednu zásadu pro aplikaci a uživatele.

### <a name="how-policy-conflicts-are-resolved"></a>Způsob řešení konfliktů zásad
Pokud nastal konflikt zásad správy mobilních aplikací při prvním nasazení u uživatele nebo zařízení, konkrétní konfliktní hodnota nastavení se odebere ze zásady nasazené v aplikaci. Aplikace bude používat integrovanou konfliktní hodnotu.

Pokud nastal konflikt zásady správy mobilních aplikací při pozdějších nasazeních aplikace nebo uživatele, konkrétní hodnota konfliktního nastavení se nebude aktualizovat na zásady správy mobilních aplikací nasazené do aplikace. Aplikace bude používat stávající hodnotu tohoto nastavení.

V případech, kdy zařízení nebo uživatel obdrží dvě konfliktní zásady, platí následující chování:

-   Pokud už byla zásada nasazená na zařízení, stávající nastavení zásad se nepřepíšou.

-   Pokud ještě na zařízení nebyla nasazená žádná zásada a nasadí se dvě konfliktní nastavení, použije se výchozí nastavení zařízení.

