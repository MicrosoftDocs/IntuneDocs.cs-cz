---
# required metadata

title: Nasazení aplikací | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Nasazení aplikací s Microsoft Intune

Toto téma vysvětluje některé koncepce, kterým je třeba porozumět před zahájením nasazování aplikací s Microsoft Intune.

## Vydavatel softwaru Intune
Když přidáváte nebo odebíráte aplikace pomocí konzoly pro správu Microsoft Intune, spouští se **Vydavatel softwaru Microsoft Intune**. Od vydavatele vyberete a nakonfigurujete typ instalačního programu, který bude buď nahrávat aplikace (pro počítače nebo pro mobilní zařízení) k uložení do cloudového úložiště Intune, nebo bude odkazovat na online obchod s aplikacemi nebo webovou aplikaci.

### Požadavky
Než začnete používat vydavatele softwaru Microsoft Intune, musíte nainstalovat plnou verzi [rozhraní Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851). Po instalaci může být nutný restart počítače, aby se Vydavatel softwaru otevřel správně.

## Prostor v cloudovém úložišti
Všechny aplikace, které nasazujete pomocí instalace typu instalační program softwaru, musí být zabalené a nahrané do cloudového úložiště Microsoft Intune. Zkušební předplatné Intune zahrnuje 2 gigabajty (GB) cloudového úložiště, které se používá k ukládání spravovaných aplikací a aktualizací. Placené předplatné zahrnuje 20 GB s možností přikoupit dodatečný prostor.

Objem využitého úložiště a možnost zakoupení dalšího prostoru jsou dostupné v uzlu **Využití úložiště** uzlu **Admin** pracovního prostoru.

Při nákupu dalšího cloudového úložiště pro Intune platí následující pravidla:

-   Nákup dalšího úložiště vyžaduje aktivní placené předplatné.

-   Další úložiště můžou nakupovat jenom správci fakturace nebo globální správci služby Microsoft Online Service přes portál účtů Intune. Tyto správce může přidávat, odstraňovat nebo spravovat jenom globální správce přihlášený k portálu účtů Intune.

-   Pokud jste zákazník s multilicenční smlouvou, který si koupil Intune nebo doplněk Microsoft Intune v rámci smlouvy Enterprise, zeptejte se na informace o cenách a možnost přikoupení úložiště account manažera nebo partnera Microsoftu.

#### Požadavky na cloudové úložiště

-   Všechny soubory přidružené k aplikaci musí být na stejném místě a přístupné službě Intune.

-   Maximální velikost kteréhokoli nahraného souboru je 2 GB.

-   Pro nahrávání souborů je vyžadována minimální rychlost připojení k internetu 768 kb/s.

## Akce nasazení aplikace
Při nasazování aplikací můžete zvolit jednu z následujících akcí nasazení:

-   **Požadovaná instalace** – Aplikace se nainstaluje do zařízení bez nutnosti zásahu koncového uživatele.

    > [!TIP]
    > Pro zařízení s iOS, která nejsou v dohledovém režimu, a pro všechna zařízení s Androidem, musí uživatel aplikaci před instalací přijmout.
    >
    > Už nemůžete vytvářet nová nasazení aplikací do zařízení iOS se starší verzí operačního systému než iOS 7.1. Všechna stávající nasazení aplikací do zařízení se starší verzí operačního systému než iOS 7.1 budou dál fungovat a bude je spravovat Intune.

-   **Dostupná instalace** – Aplikace se zobrazuje na podnikovém portálu a koncoví uživatelé ji můžou instalovat na vyžádání.

-   **Odinstalace** – Aplikace se ze zařízení odinstaluje.

-   **Není k dispozici** – Aplikace se nezobrazuje na podnikovém portálu a není nainstalovaná na žádném zařízení.

#### Porozumění akcím, které jsou dostupné pro jednotlivé typy instalačních programů

|Typ instalačního programu|Požadovaná instalace|Dostupná instalace|Odinstalace|Není k dispozici|
|------------------|--------------------|---------------------|-------------|------------------|
|Balíček aplikací pro Windows (nasazený pro skupinu uživatelů)|Ano|Ano|Ano|Ano|
|Balíček aplikací pro Windows (nasazený pro skupinu zařízení)|Ano|Ne|Ano|Ano|
|Balíček aplikace pro mobilní zařízení (nasazený pro skupinu uživatelů)|Ano|Ano|Ano|Ano|
|Balíček aplikace pro mobilní zařízení (nasazený pro skupinu zařízení)|Ano|Ne|Ano|Ano|
|Instalační služba systému Windows (nasazené pro skupinu uživatelů)|Ne|Ano|Ne|Ano|
|Instalační služba systému Windows (nasazené pro skupinu zařízení)|Ano|Ne|Ano|Ano|
|Externí odkaz (nasazený pro skupinu uživatelů)|Ne|Ano|Ne|Ano|
|Externí odkaz (nasazený pro skupinu zařízení)|Ne|Ne|Ne|Ne|
|Spravovaná aplikace pro iOS z App Storu (nasazené pro skupinu uživatelů)|Ano|Ano|Ano|Ano|
|Spravovaná aplikace pro iOS z App Storu (nasazené pro skupinu zařízení)|Ano|Ne|Ano|Ano|
> [!TIP]
> Když nasazujete aplikace a vyberete jak skupiny uživatelů, tak zařízení, můžete aplikaci nasadit jenom jako **Dostupná instalace**..

## Konflikty nasazení
Při dvou nasazeních platí při přijetí stejné akce nasazení na zařízení následující pravidla:

-   Nasazení pro skupinu zařízení má přednost před nasazením pro skupinu uživatelů. Pokud je ale aplikace nasazená pro skupinu uživatelů pomocí akce nasazení **Dostupné** a v případě, že je stejná aplikace nasazená taky pro skupinu zařízení pomocí akce nasazení **Není k dispozici**, aplikace bude dostupná na podnikovém portálu a uživatelé si ji můžou nainstalovat.

-   Záměr správce IT má přednost před uživatelem.

-   Akce instalace má přednost před akcí odinstalace.

-   Pokud zařízení přijme požadovanou i dostupnou instalaci, akce se zkombinují (aplikace je požadovaná i dostupná).


## Další kroky

Přečtěte si, jak [nasazovat aplikace v Microsoft Intune](deploy-apps-in-microsoft-intune.md)..

<!--HONumber=May16_HO1-->


