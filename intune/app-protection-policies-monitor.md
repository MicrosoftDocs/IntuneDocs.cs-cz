---
title: Jak monitorovat zásady ochrany aplikací
titleSuffix: Microsoft Intune
description: Toto téma popisuje, jak monitorovat stav dodržování zásad správy mobilních aplikací v Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/08/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0dd0ce79f6bbb381523a92855f38ad6b7f372ac2
ms.sourcegitcommit: 8943848d47d5d5d6e44c74d414c34c5e3457862b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56655319"
---
# <a name="how-to-monitor-app-protection-policies"></a>Jak monitorovat zásady ochrany aplikací
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Monitorujte stav dodržování zásad správy mobilních aplikací (MAM), které jste použili u uživatelů v podokně ochrany aplikace Intune na portálu [Azure Portal](https://portal.azure.com). Najděte informace o uživatelích dotčených zásadami MAM, stavu dodržování zásad a všech problémech, se kterými se uživatelé můžou setkat.

Stav dodržování zásad můžete monitorovat na třech místech:

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

-   **Přiřazení uživatelé**: Celkový počet přiřazení uživatelé ve vaší společnosti, kteří používají aplikace, které je přidružené k zásadám v pracovním kontextu a jsou chráněné a licenci, a také přiřazení uživatelé, které jsou Nechráněno a nelicencováno
-   **Uživatelé označení příznakem**: Počet uživatelů, kteří mají problémy. Zařízení s Jailbreakem jsou hlášeny v rámci **uživatelé označení příznakem**.
-   **Stav uživatele pro iOS** a **stav uživatele pro Android**: Počet uživatelů, kteří použili aplikaci, kteří mají přiřazené k nim v pracovním kontextu pro platformu související zásady. Tyto informace zobrazují počet uživatelů, spravovat zásady, jakož i počet uživatelů, kteří používají aplikaci, která není cílem žádné zásady v pracovním kontextu. Tyto uživatele případně můžete k zásadě přidat.

    > [!NOTE]
    > Pokud máte pro každou platformu více zásad, bude se uživatel považovat za spravovaného zásadou, pokud má přiřazenou minimálně jednu zásadu.

## <a name="detailed-view"></a>Podrobné zobrazení
Pokud se chcete podívat na podrobnosti přehledu, zvolte dlaždici **Stav uživatele** (podle platformy operačního systému) a pak dlaždici **Uživatelé označení příznakem**.

### <a name="user-status"></a>Stav uživatele
Můžete vyhledat konkrétního uživatele a zkontrolovat u něj stav dodržování předpisů. V podokně **Vytváření sestav aplikace** se zobrazují následující informace o vybraném uživateli:
- Zařízení přidružená k účtu uživatele

- Aplikace se zásadou MAM u zařízení

- Stav:

  - **Vrátit se změnami**: Že byly zásady nasazeny uživateli, a aplikace byla alespoň jednou použita v pracovním kontextu.

  - **Není zaregistrováno**: Že byly zásady nasazeny uživateli, ale aplikace nebyla použita v pracovním kontextu od té doby.

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

Stejné sestavy v můžete najít **stav ochrany aplikace** okno.

> [!NOTE]
> Intune poskytuje další zařízení polí, včetně Id registrace aplikace, s Androidem výrobce, model a verzi opravy zabezpečení, jakož i modelu iOS, který pro vytváření sestav. V Intune najdete tato pole jsou dostupné tak, že vyberete **klientské aplikace** > **stav ochrany aplikace** a zvolíte **sestava ochrany aplikací: iOS, Android**. Kromě toho tyto parametry můžete nakonfigurovat **povolit** seznamu pro výrobce zařízení (Android), **povolit** seznam pro model zařízení (Android a iOS) a minimální opravu zabezpečení Androidu nastavení verze. 

Další sestavy jsou k dispozici, které vám pomůžou se stavem dodržování zásad MAM. Chcete-li zobrazit tyto sestavy, vyberte **klientské aplikace** > **stav ochrany aplikace** > **sestavy**. 

**Sestavy** okno nabízí několik sestav na základě uživatele a aplikace, včetně následujících:


-   **Sestava uživatelů spadajících pod**: Tato sestava obsahuje stejné informace můžete najít **stav uživatele** sestavy ve výše uvedeném oddílu podrobné zobrazení.

-   **Sestava aplikací**: Tato sestava poskytuje dva různé stavy ochrany aplikací, které správce může před generováním sestavy vybrat. Může vybrat chráněný nebo nechráněný stav.

    -   Stav uživatele pro spravovanou aktivitu MAM (chráněný): Tato sestava obsahuje aktivitu jednotlivých aplikací spravovaných prostřednictvím MAM na jednotlivé uživatele.

        -   Zobrazuje všechny aplikace, které jsou cílem zásad MAM, pro jednotlivé uživatele. Zobrazuje také rozdělení stavu jednotlivých aplikací podle toho, jak jsou zaregistrované v zásadách MAM, nebo aplikací, které jsou cílem zásad MAM, ale nebyly nikdy zaregistrované.
<br><br>
    -   Stav uživatele pro nespravovanou aktivitu MAM (nechráněný): Tato sestava obsahuje aktivitu aplikací aktivovaných pro MAM, které jsou aktuálně spravované, podle jednotlivých uživatelů. K tomu může dojít z následujících důvodů:

        -   Tyto aplikace používá uživatel nebo aplikace, která momentálně není cílem žádné zásady MAM.

        -   Všechny aplikace jsou zaregistrované, ale nejsou u nich použité žádné zásady MAM.

![Snímek obrazovky uživatele aplikace reporting okno s podrobnostmi o 3 aplikace](./media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Seskupování tabulek

Jakmile se zobrazí data **sestavy uživatele ochrany aplikací**, můžete je agregovat podle těchto možností:

- **Výsledek ověřování:** Data se zobrazí seskupená podle stavu ochrany aplikací, který může být selhání, upozornění nebo úspěch.
- **Název aplikace:** Data se zobrazí seskupená podle aplikací (skutečného názvu aplikace) se selháním, upozorněním nebo úspěch.

## <a name="export-app-protection-activities-to-csv"></a>Export aktivit ochrany aplikace do souboru CSV

Všechny aktivity ochrany aplikací můžete vyexportovat do jediného souboru .csv. To může být užitečné při analýze všech stavů ochrany aplikací hlášených od uživatelů.

Pokud chcete vygenerovat sestavu ochrany aplikací, postupujte takto:

1. V podokně správy mobilních aplikací Intune zvolte **Sestava ochrany aplikací**.

    ![Snímek obrazovky se odkaz ke stažení App protection](./media/app-protection-report-csv-2.png)

2. Zvolte Ano, aby se vaše sestava uložila, a pak zvolte Uložit jako a vyberte složku, do které chcete sestavu uložit.

    ![Snímek obrazovky pole pro potvrzení uložení sestavy](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Viz také:
[Správa přenosu dat mezi aplikacemi pro iOS](data-transfer-between-apps-manage-ios.md)

* [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](app-protection-enabled-apps-android.md)
* [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](app-protection-enabled-apps-ios.md)
