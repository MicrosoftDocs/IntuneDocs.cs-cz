---
title: "Nastavení zásad pro Mac OS X | Microsoft Intune"
description: "Intune poskytuje řadu předdefinovaných obecných nastavení, která můžete konfigurovat v zařízeních s Mac OS X. Navíc můžete použít nástroj Apple Configurator k vytvoření vlastních nastavení, která nejsou k dispozici prostřednictvím Intune."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 98b2f19b-bee8-42d7-a215-a716d56a25a3
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 90eee9515696f049194515fb6bed280564d0f923


---

# Nastavení zásad konfigurace pro Mac OS X v Microsoft Intune

Intune poskytuje řadu předdefinovaných obecných nastavení, která můžete konfigurovat v zařízeních s Mac OS X. Navíc můžete použít nástroj Apple Configurator k vytvoření vlastních nastavení, která nejsou k dispozici prostřednictvím Intune.

## Obecná nastavení zásad konfigurace

Pomocí **obecných zásad konfigurace pro Mac OS X** v Microsoft Intune můžete nakonfigurovat nastavení pro:

-   **Nastavení zabezpečení zařízení** – Vyberte některou možnost ze seznamu předdefinovaných nastavení, která umožňují kontrolovat rozsah vlastností a funkcí zařízení.

-   **Seznam aplikací dodržujících a nedodržujících předpisy** – Určete seznam aplikací, které splňují nebo nesplňují předpisy ve vaší společnosti. Sestavu aplikací nesplňujících požadavky můžete použít k zobrazení shody aplikací, které zadáte v seznamu, s aplikacemi, které si uživatelé nainstalovali (sestava neslouží ke skutečnému zablokování instalace aplikací).

Pokud se hledané nastavení v seznamu nezobrazí, můžete k jeho vytvoření použít vlastní zásady systému Mac OS X, které umožňují importovat nastavení vytvořená v nástroji Apple Configurator. Další informace najdete v tématu **Nastavení vlastních zásad** dál v tomto tématu.

### Nastavení hesla

|Název nastavení|Podrobnosti|
|----------------|---------------|
|**Vyžadovat heslo k odemknutí zařízení**|Určuje, jestli uživatel musí pro přístup k počítači Mac použít heslo. **Důležité:** Na rozdíl od zařízení iOS se na zařízení Mac OS X uživateli hned nezobrazí upozornění, že si má aktualizovat heslo, aby byla tato zásada dodržená.|
|**Vyžadovaný typ hesla**|Určuje, jestli je možné použít jenom číselné heslo nebo je potřeba použít **alfanumerické** heslo (obsahuje písmena i číslice). **Důležité:** Toto nastavení je podporované jenom v Mac OS X 10.10.3 a v novějších verzích.|
|**Počet složitých znaků požadovaných v hesle**|Určuje požadovaný počet složitých znaků v hesle (**0** - **4**).<br /><br />Složitý znak je třeba otazník (**?**).|
|**Minimální délka hesla**|Určuje minimální délku hesla ( **4** až **14** znaků).|
|**Povolit jednoduchá hesla**|Dovoluje jednoduchá hesla, jako je „**0000**“ nebo „**1234**“.|
|**Počet minut nečinnosti před vyžadováním hesla**|Určuje, jak dlouho musí být počítač neaktivní, aby k jeho odemčení bylo potřeba heslo.|
|**Omezená platnost hesla (ve dnech)**|Určuje, jak dlouho si může uživatel nechat stejné heslo, než ho bude muset změnit (**1** - **255** dnů).|
|**Pamatovat si historii hesel**|Nastavení brání uživateli, aby opakovaně použil už jednou použité heslo. Pokud nastavení použijete, můžete taky nastavit **Zakázat opakované použití předchozích hesel** a zadat počet použitých hesel, která se nesmí znova použít (**1** - **24**).|
|**Počet minut nečinnosti před aktivací šetřiče obrazovky**|Určuje, jak dlouho musí být počítač nečinný, než se aktivuje šetřič obrazovky.|

### Nastavení pro aplikace dodržující a nedodržující předpisy
V seznamu **kompatibilních a nekompatibilních aplikací pro Mac OS X** aktivujte **Spravované nastavení pro zařízení** a pak zadejte seznam kompatibilních a nekompatibilních aplikací. Můžete použít následující informace:

> [!NOTE]
> Jedna zásada může obsahovat seznam jenom kompatibilních, nebo jenom nekompatibilních aplikací. Nejde zadat oba seznamy v jedné zásadě.
> 
> Intune umožňuje generovat sestavu zařízení s nekompatibilními aplikacemi. Služba neblokuje instalaci nekompatibilních aplikací, ani je neodebírá.

|Název nastavení|Podrobnosti|
|----------------|---------------|
|**Ohlásit nekompatibilitu, když uživatelé nainstalují aplikace ze seznamu**|Seznam aplikací pro Mac OS X, které uživatelé nesmí instalovat. Pokud si uživatelé některé z těchto aplikací nainstalují, objeví se na **sestavách aplikací nesplňujících požadavky**.|
|**Ohlásit nekompatibilitu, když uživatelé nainstalují aplikace, které nejsou na seznamu**|Seznam aplikací pro Mac OS X, které uživatelé smí instalovat. Pokud si uživatelé nainstalují nějaké jiné aplikace, objeví se na **sestavách aplikací nesplňujících požadavky**.|
|**Přidat**|Přidá aplikaci do vybraného seznamu. Zadejte vybraný název aplikace, můžete taky zadat jejího vydavatele a ID sady. **Tip:** Pokud chcete na počítači Mac s nainstalovanou aplikací zjistit ID sady, použijte následující postup:<ol><li>Otevřete složku, ve které je aplikace nainstalovaná (třeba **/Applikace**).</li><li>Vyberte sadu *&lt;název aplikace&gt;***.app** a zvolte **Zobrazit obsah balíčku**.</li><li>Otevřete soubor **Info.plist** .</li><li>Zkontrolujte hodnotu přiřazenou klíči **CFBundleIdentifier**.</li></ol>Formát ID sady je **com.contoso.nazevaplikace**.|
|**Importovat aplikace**|Importuje seznam aplikací, které jste zadali v souboru hodnot oddělených čárkami. Použije se formát, název aplikace, vydavatel a ID sady aplikace v souboru.|
|**Upravit**|Umožňuje upravit název, vydavatele a ID sady vybrané aplikace.|
|**Odstranit**|Odstraní vybranou aplikaci ze seznamu.|
> [!TIP]
> Další informace o sestavách Intune najdete v tématu [Pochopení operací Microsoft Intune pomocí sestav](understand-microsoft-intune-operations-by-using-reports.md).

> [!IMPORTANT]
> Když je zařízení Mac OS X v režimu spánku, zásady a profily nejdou doručovat ani inventarizovat. Konzola Intune tak může dočasně zobrazovat stav **Nastavení zásad obsahující chybu**, dokud se zařízení nevzbudí z režimu spánku.

### Monitorování aplikací, které splňují a nesplňují předpisy
Pokud se chcete podívat, jestli se dodržuje seznam zadaných aplikací, použijte **sestavy aplikací nesplňujících požadavky** .

#### Spuštění sestavy

1.  V [konzole správce Microsoft Intune](https://manage.microsoft.com) klikněte na **Sestavy** &gt; **Sestavy aplikací nesplňujících požadavky**.

2.  Vyberte skupiny zařízení, které chcete zkontrolovat, určete, jestli kontrolovat kompatibilní aplikace, nekompatibilní aplikace nebo obojí a pak klikněte na **Zobrazit sestavu**.

## Nastavení vlastních zásad pro Mac OS X v Microsoft Intune
Pomocí **vlastní zásady konfigurace Mac OS X** Microsoft Intune nasaďte nastavení, které jste vytvořili pomocí [nástroje Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), do zařízení s Mac OS X. Pomocí tohoto nástroje se dá vytvořit spousta nastavení, která řídí provoz těchto zařízení, a exportovat je do konfiguračního profilu. Potom tento konfigurační profil můžete importovat do vlastní zásady Mac OS X Intune na zařízení a nasadit nastavení pro uživatele a zařízení ve svojí organizaci.

Díky této vlastnosti můžete nasadit nastavení Mac OS X, která nejdou konfigurovat obecnými zásadami konfigurace Mac OS X Intune.

### Požadavky
Než začnete, je potřeba nainstalovat Apple Configurator a vytvořit konfigurační soubor s nastaveními, která chcete nasadit pro uživatele nebo zařízení. Apple Configurator si můžete stáhnout z [Mac App Storu](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), kde taky najdete informace o něm.

> [!NOTE]
> Intune nevytváří sestavu dodržování předpisů individuálních nastavení ve vlastních zásadách pro Mac OS X. Vytvoří se ale sestava celkového dodržování zásad.

### Obecná nastavení

|Název nastavení|Podrobnosti|
    |----------------|--------------------|
    |**Název**|Zadejte jedinečný název vlastní zásady pro Mac OS X, abyste ji mohli v konzole Intune snadno identifikovat.|
    |**Popis**|Zadejte popis, který bude shrnovat účel vlastní zásady pro Mac OS X, a uveďte jakékoli další důležité informace, které vám pomůžou zásadu najít.|


### Vlastní nastavení

|Název nastavení|Podrobnosti|
    |----------------|--------------------|
    |**Vlastní název konfiguračního profilu (zobrazený uživatelům)**|Zadejte název zásady tak, jak se bude zobrazovat na zařízení a v sestavách zásad Intune.|
    |**Soubor konfiguračního profilu**|Klikněte na **Importovat**a potom vyhledejte konfigurační profil, který jste vytvořili pomocí nástroje Apple Configurator. **Tip:** Nápovědu pro vytváření konfiguračního profilu najdete v tématu **Vytvoření souboru konfiguračního profilu**.|
    |**Podrobnosti konfiguračního profilu**|Zobrazí kód XML pro konfigurační profil, který jste importovali.|



### Vytvoření souboru konfiguračního profilu
Soubor konfiguračního profilu používaný vlastními zásadami můžete vytvořit dvěma způsoby:

-   Exportujte soubor (s příponou **.mobileconfig**) z nástroje Apple Configurator.

-   Vytvořte soubor sami pomocí příslušného schématu z dokumentu [Apple Configuration Profile Key Reference](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html).


> [!IMPORTANT]
> Když je zařízení Mac OS X v režimu spánku, zásady a profily nejdou doručovat ani inventarizovat. Konzola Intune tak může dočasně zobrazovat stav **Nastavení zásad obsahující chybu**, dokud se zařízení nevzbudí z režimu spánku.

### Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO3-->


