---
title: Jak monitorovat zásady ochrany aplikací
titleSuffix: Microsoft Intune
description: Toto téma popisuje, jak monitorovat stav dodržování zásad správy mobilních aplikací v Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cee1cbc05164a418148ecea8d93f6c8c45c73e01
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57394554"
---
# <a name="how-to-monitor-app-protection-policies"></a>Jak monitorovat zásady ochrany aplikací
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Můžete monitorovat stav dodržování zásad správy (MAM) mobilních aplikací, které jste použili u uživatelů v podokně Intune app protection v [webu Azure portal](https://portal.azure.com). Kromě toho může najít informace o uživatelích dotčených zásadami MAM, stav dodržování zásad MAM a všech problémech, které uživatelé můžou setkat.

Monitorovat stav dodržování zásad MAM třech místech:
-   Souhrnné zobrazení
-   Podrobné zobrazení
-   Zobrazení vytváření sestav

> [!NOTE]
> Informace o vytváření zásad ochrany aplikací najdete v článku [Vytvoření a přiřazení zásad ochrany aplikací](app-protection-policies.md).

## <a name="summary-view"></a>Souhrnné zobrazení

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V **klientské aplikace** zatížení, zvolte **stav ochrany aplikace** z **monitorování** části, a zobrazte tak souhrnné zobrazení:

![Dlaždice souhrnu podokna Správa mobilních aplikací Intune](./media/app-protection-user-status-summary.png)

- **Přiřazení uživatelé**: Celkový počet přiřazení uživatelé ve vaší společnosti, kteří používají aplikace, které je přidružené k zásadám v pracovním kontextu a jsou chráněné a licenci, a také přiřazení uživatelé, které jsou Nechráněno a nelicencováno
- **Uživatelé označení příznakem**: Počet uživatelů, kteří mají problémy. Zařízení s Jailbreakem jsou hlášeny v rámci **uživatelé označení příznakem**.
- **Stav uživatele pro iOS** a **stav uživatele pro Android**: Počet uživatelů, kteří použili aplikaci, kteří mají přiřazené k nim v pracovním kontextu pro platformu související zásady. Tyto informace zobrazují počet uživatelů, spravovat zásady, jakož i počet uživatelů, kteří používají aplikaci, která není cílem žádné zásady v pracovním kontextu. Tyto uživatele případně můžete k zásadě přidat.
- **TOP chráněné aplikace pro iOS**: Podle nejpoužívanější aplikace pro iOS, tyto informace zobrazují počet aplikací pro iOS chráněná a nechráněné.
- **Vybrané chráněné aplikace pro Android**: Podle nejpoužívanější aplikace pro Android, tyto informace zobrazují počet chráněných a nechráněné aplikace pro Android.
- **TOP aplikací bez registrace pro iOS nakonfigurováno**: Podle nejpoužívanějších aplikací iOS pro neregistrovaná zařízení, tyto informace zobrazují počet nakonfigurovaných iOS aplikací.
- **Nejčastěji konfigurované aplikace pro Android bez registrace**: Podle nejpoužívanější aplikace pro Android pro neregistrovaná zařízení, tyto informace zobrazují počet konfigurované aplikace pro Android.

    > [!NOTE]
    > Pokud máte každou platformu víc zásad, uživatel je považován za spravovaného zásadou, když je nutné splnit aspoň jednu zásadu je přiřadit k nim.

## <a name="detailed-view"></a>Podrobné zobrazení
Pokud se chcete podívat na podrobnosti přehledu, zvolte dlaždici **Stav uživatele** (podle platformy operačního systému) a pak dlaždici **Uživatelé označení příznakem**.

### <a name="user-status"></a>Stav uživatele
Můžete vyhledat konkrétního uživatele a zkontrolovat u něj stav dodržování předpisů. V podokně **Vytváření sestav aplikace** se zobrazují následující informace o vybraném uživateli:
- **Ikona**: Zobrazuje, zda je aktuální stav aplikace.
- **Název aplikace**: Název aplikace.
- **Název zařízení**: Zařízení, které jsou přidružené k účtu uživatele.
- **Typ zařízení**: Typ zařízení nebo operační systém běží zařízení.
- **Zásady**: Zásady přidružené k aplikaci.
- **Stav**:
  - **Vrátit se změnami**: Že byly zásady nasazeny uživateli, a aplikace byla alespoň jednou použita v pracovním kontextu.
  - **Není zaregistrováno**: Že byly zásady nasazeny uživateli, ale aplikace nebyla použita v pracovním kontextu od té doby.
- **Poslední synchronizace**: Pokud byla poslední synchronizace zařízení.

>[!NOTE]
> Pokud uživatel, kterého jste hledali, nemá nasazené zásady MAM, zobrazí se zpráva, že na uživatele není zacílená žádná zásada MAM.

Pokud chcete zobrazit vytváření sestav pro uživatele, postupujte takto:

1.  Chcete-li vybrat uživatele, zvolte **stav uživatele** dlaždici se souhrnem.

    ![Snímek obrazovky dlaždice souhrnu správy mobilních aplikací Intune](./media/MAM-reporting-6.png)

2. Otevře se podokno **Vytváření sestav aplikace**. Zvolte **Vybrat uživatele** a najděte uživatele služby Azure Active Directory.

    ![Snímek obrazovky s možností vybrat uživatele na podokno sestav aplikace](./media/MAM-reporting-2.png)

3. Vyberte uživatele ze seznamu. Zobrazí se podrobné informace o konkrétním uživateli a stavu dodržování předpisů.

### <a name="flagged-users"></a>Uživatelé označení příznakem
V podrobném přehledu se zobrazí chybová zpráva, otevíraná aplikace v okamžiku chyby, dotčená platforma operačního systému zařízení a časové razítko.

## <a name="reporting-view"></a>Zobrazení vytváření sestav

Stejné sestavy můžete najít v horní části **stav ochrany aplikace** okno.

> [!NOTE]
> Intune poskytuje další zařízení polí, včetně Id registrace aplikace, s Androidem výrobce, model a verzi opravy zabezpečení, jakož i modelu iOS, který pro vytváření sestav. V Intune najdete tato pole jsou dostupné tak, že vyberete **klientské aplikace** > **stav ochrany aplikace** a zvolíte **sestava ochrany aplikací: iOS, Android**. Kromě toho tyto parametry můžete nakonfigurovat **povolit** seznamu pro výrobce zařízení (Android), **povolit** seznam pro model zařízení (Android a iOS) a minimální opravu zabezpečení Androidu nastavení verze. 

Další sestavy jsou k dispozici, které vám pomůžou se stavem dodržování zásad MAM. Chcete-li zobrazit tyto sestavy, vyberte **klientské aplikace** > **stav ochrany aplikace** > **sestavy**. 

**Sestavy** okno nabízí několik sestav na základě uživatele a aplikace, včetně následujících:


- **Sestava uživatelů spadajících pod**: Tato sestava obsahuje stejné informace, které najdete v **stav uživatele** sestavy v rámci [podrobného zobrazení](app-protection-policies-monitor.md#detailed-view) výše uvedené části.

- **Sestava aplikací**: Kromě výběru platformy a aplikace, tato sestava poskytuje dva různé stavy ochrany aplikací, které můžete před generováním sestavy vybrat. Může být stavy **chráněné** nebo **Unprotected**.

    -   Stav uživatele pro spravovanou aktivitu MAM (**chráněné**): Tato sestava obsahuje aktivitu jednotlivých aplikací spravovaných prostřednictvím MAM na jednotlivé uživatele. Zobrazuje všechny aplikace, které jsou cílem zásad MAM, pro jednotlivé uživatele. Zobrazuje také rozdělení stavu jednotlivých aplikací podle toho, jak jsou zaregistrované v zásadách MAM, nebo aplikací, které jsou cílem zásad MAM, ale nebyly nikdy zaregistrované.
    -   Stav uživatele pro nespravovanou aktivitu MAM (**Unprotected**): Tato sestava obsahuje aktivitu aplikací aktivovaných pro MAM, které jsou aktuálně spravované, podle jednotlivých uživatelů. K tomu může dojít z následujících důvodů:
        -   Tyto aplikace používá uživatel nebo aplikace, která momentálně není cílem žádné zásady MAM.
        -   Všechny aplikace jsou zaregistrované, ale nejsou u nich použité žádné zásady MAM.

        ![Snímek obrazovky uživatele aplikace reporting okno s podrobnostmi o 3 aplikace](./media/MAM-reporting-4.png)

- **Sestava uživatelů spadajících pod konfiguraci**: Na základě vybrané uživatelem, tato sestava obsahuje podrobnosti o žádné konfigurace aplikací, které uživatel obdržel.
- **Sestava ke konfiguraci aplikace**: Základní na vybrané platformy a aplikace, tato sestava obsahuje podrobnosti o tom, které mají uživatelé obdrží konfigurace pro vybranou aplikaci.
- **Aplikace pro Windows Information Protection referát**: Tato sestava zobrazí aplikace, které se pokoušíte překračují hranice zásad.
- **Referát o webu pro Windows Information Protection**: Tato sestava zobrazí, které weby se pokoušíte překračují hranice zásad.

## <a name="table-grouping"></a>Seskupování tabulek

Jednou **sestava uživatele ochrany aplikací** se zobrazí data, můžete je agregovat podle následující:

- **Výsledek ověřování:** Data se zobrazí seskupená podle stavu ochrany aplikací, který může být selhání, upozornění nebo úspěch.
- **Název aplikace:** Data se zobrazí seskupená podle aplikací (skutečného názvu aplikace) se selháním, upozorněním nebo úspěch.

## <a name="export-app-protection-activities-to-csv"></a>Export aktivit ochrany aplikace do souboru CSV

Všechny vaše aktivity ochrany aplikací můžete vyexportovat do jediného *CSV* souboru. To může být užitečné při analýze všech stavů ochrany aplikací hlášených od uživatelů.

Pokud chcete vygenerovat sestavu ochrany aplikací, postupujte takto:

1. V podokně správy mobilních aplikací Intune zvolte **Sestava ochrany aplikací**.

    ![Snímek obrazovky se odkaz ke stažení App protection](./media/app-protection-report-csv-2.png)

2. Zvolte **Ano** sestavu uložit, klikněte na tlačítko **uložit jako** a vyberte složku, které chcete sestavu uložit.

    ![Snímek obrazovky pole pro potvrzení uložení sestavy](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Viz také:
- [Správa přenosu dat mezi aplikacemi pro iOS](data-transfer-between-apps-manage-ios.md)
- [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](app-protection-enabled-apps-android.md)
- [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](app-protection-enabled-apps-ios.md)
