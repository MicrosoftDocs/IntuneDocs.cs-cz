---
title: "Nastavení zásad pro Mac OS X | Dokumentace Microsoftu"
description: "Intune poskytuje řadu předdefinovaných obecných nastavení, která můžete konfigurovat v zařízeních s Mac OS X. Navíc můžete použít nástroj Apple Configurator k vytvoření vlastních nastavení, která nejsou k dispozici prostřednictvím Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 98b2f19b-bee8-42d7-a215-a716d56a25a3
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: 58dc1d872e7e12978652542d80061dd7ed86aeb2
ms.lasthandoff: 12/30/2016


---

# <a name="mac-os-x-configuration-policy-settings-in-microsoft-intune"></a>Nastavení zásad konfigurace pro Mac OS X v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune poskytuje řadu předdefinovaných obecných nastavení, která můžete konfigurovat v zařízeních s Mac OS X. Navíc můžete použít nástroj Apple Configurator k vytvoření vlastních nastavení, která nejsou k dispozici prostřednictvím Intune.

## <a name="general-configuration-policy-settings"></a>Obecná nastavení zásad konfigurace

Pomocí **obecných zásad konfigurace pro Mac OS X** v Microsoft Intune můžete nakonfigurovat nastavení pro:

-   **Nastavení zabezpečení zařízení**. Vyberte některou možnost ze seznamu předdefinovaných nastavení, která umožňují kontrolovat celou řadu vlastností a funkcí zařízení.

-   **Kompatibilní a nekompatibilní aplikace**. Určete seznam aplikací pro iOS, které vyhovují nebo nevyhovují předpisům ve vaší společnosti. Sestavu aplikací nesplňujících požadavky můžete použít k zobrazení shody aplikací, které zadáte v seznamu, s aplikacemi, které si uživatelé nainstalovali (sestava neslouží ke skutečnému zablokování instalace aplikací).

Pokud se hledané nastavení v seznamu nezobrazí, můžete k jeho vytvoření použít vlastní zásady systému Mac OS X, které umožňují importovat nastavení vytvořená v nástroji Apple Configurator. Další informace najdete v části Nastavení vlastních zásad dál v tomto tématu.

### <a name="password-settings"></a>Nastavení hesla

|Název nastavení|Podrobnosti|
|----------------|---------------|
|**Vyžadovat heslo k odemknutí zařízení**|Určete, jestli uživatel musí pro přístup k počítači Mac použít heslo. **Důležité:** Na rozdíl od zařízení iOS se na zařízení Mac OS X uživateli hned nezobrazí upozornění, že si má aktualizovat heslo, aby byla tato zásada dodržená.|
|**Vyžadovaný typ hesla**|Určete, jestli je možné použít jenom **číselné** heslo nebo jestli je potřeba použít **alfanumerické** heslo (obsahuje písmena i číslice). **Důležité:** Toto nastavení je podporované jenom v systému Mac OS X 10.10.3 a v novějších verzích.|
|**Požadovaný počet složitých znaků v hesle**|Určete požadovaný počet složitých znaků v hesle (**0** až **4**).<br /><br />Složitý znak je symbol, jako třeba **?**.|
|**Minimální délka hesla**|Zadejte minimální délku hesla (**4** až **14** znaků).|
|**Povolit jednoduchá hesla**|Umožněte použít jednoduchá hesla, jako je **0000** nebo **1234**.|
|**Počet minut nečinnosti před vyžádáním hesla**|Určete, jak dlouho musí být počítač neaktivní, aby k jeho odemčení bylo potřeba heslo.|
|**Vypršení platnosti hesla (dny)**|Určete, jak dlouho si může uživatel nechat stejné heslo, než ho bude muset změnit (**1** až **255** dnů).|
|**Pamatovat si historii hesel**|Zabraňte uživateli, aby opakovaně použil už jednou použité heslo. Pokud nastavení použijete, můžete taky nastavit **Zakázat opakované použití předchozích hesel** a zadat počet použitých hesel, která se nesmí znova použít (**1** až **24**).|
|**Počet minut nečinnosti před aktivací šetřiče obrazovky**|Určete, jak dlouho musí být počítač nečinný, než se aktivuje šetřič obrazovky.|

### <a name="settings-for-compliant-and-noncompliant-apps"></a>Nastavení pro aplikace dodržující a nedodržující předpisy
V seznamu **kompatibilních a nekompatibilních aplikací pro Mac OS X** aktivujte **Spravované nastavení pro zařízení** a pak zadejte seznam kompatibilních a nekompatibilních aplikací. Můžete použít následující informace.

> [!NOTE]
> Jedna zásada může obsahovat seznam jenom kompatibilních aplikací, nebo jenom nekompatibilních aplikací. Nejde zadat oba seznamy v jedné zásadě.
>
> Intune umožňuje generovat sestavu zařízení s nekompatibilními aplikacemi. Služba neblokuje instalaci nekompatibilních aplikací, ani je neodebírá.

|Název nastavení|Podrobnosti|
|----------------|---------------|
|**Ohlásit nekompatibilitu, když uživatelé nainstalují aplikace ze seznamu**|Zobrazuje seznam aplikací pro Mac OS X, které uživatelé nesmí instalovat. Pokud si uživatelé některé z těchto aplikací nainstalují, objeví se na **sestavách aplikací nesplňujících požadavky**.|
|**Ohlásit nekompatibilitu, když uživatelé nainstalují aplikace, které nejsou na seznamu**|Zobrazuje seznam aplikací pro Mac OS X, které uživatelé můžou instalovat. Pokud si uživatelé nainstalují jakékoli jiné aplikace, objeví se na **sestavách aplikací nesplňujících požadavky**.|
|**Přidat**|Přidá aplikaci do vybraného seznamu. Zadejte vybraný název aplikace, můžete taky zadat jejího vydavatele a ID sady. **Tip:** Pokud chcete na počítači Mac s nainstalovanou aplikací zjistit ID sady, použijte následující postup:<ol><li>Otevřete složku, ve které je aplikace nainstalovaná (třeba **/Applications**).</li><li>Vyberte sadu *&lt;název aplikace&gt;***.app** a zvolte **Zobrazit obsah balíčku**.</li><li>Otevřete soubor **Info.plist**.</li><li>Zkontrolujte hodnotu přiřazenou klíči **CFBundleIdentifier**.</li></ol>Formát ID sady je **com.contoso.nazev_aplikace**.|
|**Importovat aplikace**|Naimportujte seznam aplikací, které jste zadali v souboru hodnot oddělených čárkami. V tomto souboru použijte tento formát: název aplikace, vydavatel a ID sady aplikace.|
|**Upravit**|Upravte název, vydavatele a ID sady vybrané aplikace.|
|**Odstranit**|Odstraňte vybranou aplikaci ze seznamu.|
> [!TIP]
> Další informace o sestavách Intune najdete v tématu [Pochopení operací Microsoft Intune pomocí sestav](understand-microsoft-intune-operations-by-using-reports.md).

> [!IMPORTANT]
> Když je zařízení Mac OS X v režimu spánku, zásady a profily nejdou doručovat ani inventarizovat. Konzola Intune tak může dočasně zobrazovat stav **Nastavení zásad obsahující chybu**, dokud se zařízení nevzbudí z režimu spánku.

### <a name="monitor-compliant-and-noncompliant-apps"></a>Monitorování aplikací, které splňují a nesplňují předpisy
Pokud chcete u zadaných aplikací zkontrolovat dodržování předpisů, použijte **sestavy aplikací nesplňujících požadavky**.

#### <a name="to-run-a-report"></a>Spuštění sestavy

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Sestavy** &gt; **Sestava aplikací nesplňujících požadavky**.

2.  Vyberte skupiny zařízení, které chcete zkontrolovat, určete, jestli se mají kontrolovat aplikace dodržující předpisy, aplikace nedodržující předpisy nebo obojí, a potom vyberte **Zobrazit sestavu**.

## <a name="mac-os-x-custom-policy-settings-in-microsoft-intune"></a>Nastavení vlastních zásad pro Mac OS X v Microsoft Intune
Pomocí **vlastní zásady konfigurace Mac OS X** služby Microsoft Intune nasaďte nastavení, které jste vytvořili pomocí [nástroje Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), do zařízení s Mac OS X. Pomocí tohoto nástroje se dá vytvořit spousta nastavení, která řídí provoz těchto zařízení, a exportovat je do konfiguračního profilu. Potom tento konfigurační profil můžete importovat do vlastní zásady Mac OS X Intune na zařízení a nasadit nastavení pro uživatele a zařízení ve svojí organizaci.

Díky této funkci můžete nasadit nastavení Mac OS X, která nejdou konfigurovat obecnými zásadami konfigurace Mac OS X služby Intune.

### <a name="prerequisites"></a>Požadavky
Než začnete, je potřeba nainstalovat Apple Configurator a vytvořit konfigurační soubor s nastaveními, která chcete nasadit pro uživatele nebo zařízení. Apple Configurator si můžete stáhnout z [Mac App Storu](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), kde o něm také najdete další informace.

> [!NOTE]
> Intune nevytváří sestavu dodržování předpisů individuálních nastavení ve vlastních zásadách pro Mac OS X. Vytvoří se ale sestava celkového dodržování zásad.

### <a name="general-settings"></a>Obecná nastavení

|Název nastavení|Podrobnosti|
    |----------------|--------------------|
    |**Název**|Zadejte jedinečný název vlastní zásady pro Mac OS X, abyste ji mohli v konzole Intune snadno identifikovat.|
    |**Popis**|Zadejte popis, který bude shrnovat účel vlastní zásady pro Mac OS X, a uveďte jakékoli další důležité informace, které vám pomůžou zásadu najít.|


### <a name="custom-settings"></a>Vlastní nastavení

|Název nastavení|Podrobnosti|
    |----------------|--------------------|
    |**Název vlastního konfiguračního profilu (zobrazí se uživatelům)**|Zadejte název zásady tak, jak se bude zobrazovat na zařízení a v sestavách zásad Intune.|
    |**Soubor konfiguračního profilu**|Vyberte **Importovat** a potom vyhledejte konfigurační profil, který jste vytvořili pomocí nástroje Apple Configurator. **Tip:** Nápovědu pro vytváření konfiguračního profilu najdete v části Vytvoření souboru konfiguračního profilu v tomto tématu.|
    |**Podrobnosti konfiguračního profilu**|Zobrazí kód XML pro konfigurační profil, který jste importovali.|



### <a name="how-to-create-a-configuration-profile-file"></a>Vytvoření souboru konfiguračního profilu
Soubor konfiguračního profilu používaný vlastními zásadami můžete vytvořit dvěma způsoby:

-   Exportujte soubor (s příponou **.mobileconfig**) z nástroje Apple Configurator.

-   Vytvořte soubor sami pomocí příslušného schématu z dokumentu [Apple Configuration Profile Key Reference](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html).


### <a name="see-also"></a>Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

