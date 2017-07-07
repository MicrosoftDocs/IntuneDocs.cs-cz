---
title: "Jak monitorovat zásady ochrany aplikací"
titleSuffix: Intune on Azure
description: "Podívejte se, kolik uživatelů má přiřazené zásady. Přechodem k podrobnostem zjistíte další informace."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: de40d149818b2655a8fc3b647a7e850973814165
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-monitor-app-protection-policies"></a>Jak monitorovat zásady ochrany aplikací
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Toto téma popisuje, [jak vytvořit zásady ochrany aplikací](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) v klasické konzole Intune, **pokud nejste na portálu Azure Portal**.


Můžete monitorovat stav dodržování zásad správy mobilních aplikací (MAM), které jste použili u uživatelů v okně ochrany aplikace Intune na portálu [Azure Portal](https://portal.azure.com). Budete moct vyhledat informace o uživatelích dotčených zásadami MAM, stavu dodržování zásad a všech problémech, se kterými se uživatelé mohou setkat.

Stav dodržování zásad můžete monitorovat na třech místech:

-   Souhrnné zobrazení

-   Podrobné zobrazení

-   Zobrazení vytváření sestav

## <a name="summary-view"></a>Souhrnné zobrazení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
4. V úloze **Mobilní aplikace** zvolte **Monitorovat** > **Stav uživatele ochrany aplikací**, abyste si zobrazili souhrnné zobrazení:

![Dlaždice souhrnu okna Správa mobilních aplikací Intune](./media/app-protection-user-status-summary.png)

-   **Uživatelé**: Celkový počet uživatelů ve společnosti, kteří používají aplikace spojené se zásadou.

-   **SPRAVOVÁNO ZÁSADOU:** Počet uživatelů, kteří použili aspoň jednu aplikaci v pracovním kontextu.

-   **ŽÁDNÉ ZÁSADY:** Počet uživatelů, kteří sice používají aplikace spojené se zásadou, ale zásada se na ně nevztahuje. Tyto uživatele případně můžete k zásadě přidat.

- **Uživatelé označení příznakem:** Počet uživatelů, kteří mají problémy. V současnosti jsou v části **Uživatelé označení příznakem** jenom uživatelé zařízení, u kterých byla zrušena softwarová omezení (zařízení s jailbreakem).


## <a name="detailed-view"></a>Podrobné zobrazení
Pokud se chcete podívat na podrobnosti přehledu, zvolte dlaždici **Stav uživatele** (podle platformy operačního systému) a pak dlaždici **Uživatelé označení příznakem**.

### <a name="user-status"></a>Stav uživatele
Můžete vyhledat konkrétního uživatele a zkontrolovat u něj stav dodržování předpisů. V okně **Vytváření sestav aplikace** se zobrazují následující informace o vybraném uživateli:
- Zařízení přidružená k účtu uživatele

- Aplikace se zásadou MAM u zařízení

- Stav:

  - **Zaregistrováno:** Zásada byla u uživatele nasazena a aplikace byla alespoň jednou použita v pracovním kontextu.

  - **Není zaregistrováno:** Zásada byla u uživatele nasazena, ale aplikace od té doby nebyla použita v pracovním kontextu.

>[!NOTE]
> Pokud uživatel, kterého jste hledali, nemá nasazené zásady MAM, zobrazí se zpráva, že uživatel není cílem žádné zásady MAM.

Pokud chcete zobrazit vytváření sestav pro uživatele, postupujte takto:

1.  Uživatele vyberte tak, že zvolíte dlaždici **Souhrn**.

    ![Snímek obrazovky 3](./media/MAM-reporting-6.png)

2. Otevře se okno **Vytváření sestav aplikace**. Zvolte **Vybrat uživatele** a najděte uživatele služby Azure Active Directory.

    ![Možnost výběru uživatele v okně Vytváření sestav aplikace](./media/MAM-reporting-2.png)

3. Vyberte uživatele ze seznamu. Zobrazí se podrobné informace o konkrétním uživateli a stavu dodržování předpisů.

### <a name="flagged-users"></a>Uživatelé označení příznakem
V podrobném přehledu se zobrazí chybová zpráva, otevíraná aplikace v okamžiku chyby, dotčená platforma operačního systému zařízení a časové razítko.

## <a name="reporting-view"></a>Zobrazení vytváření sestav

Najdete tady stejné sestavy jako v Podrobném zobrazení, ale i další sestavy, které vám pomůžou se stavem dodržování zásad MAM:

![Snímek obrazovky 4](./media/MAM-reporting-7.png)

-   **Sestava uživatele ochrany aplikací:** Obsahuje stejné informace, které najdete v sestavě **Stav uživatele** v části Podrobné zobrazení výše.

-   **Sestava aplikace ochrany aplikací:** Poskytuje dva různé stavy ochrany aplikací, které správce může před generováním sestavy vybrat. Může vybrat chráněný nebo nechráněný stav.

    -   Stav uživatele pro spravovanou aktivitu MAM (chráněný): Tato sestava obsahuje aktivitu jednotlivých aplikací spravovaných prostřednictvím MAM podle jednotlivých uživatelů.

        -   Zobrazuje všechny aplikace, které jsou cílem zásad MAM, pro jednotlivé uživatele. Zobrazuje také rozdělení stavu jednotlivých aplikací podle toho, jak jsou zaregistrované v zásadách MAM, nebo aplikací, které jsou cílem zásad MAM, ale nebyly nikdy zaregistrované.
<br></br>
    -   Stav uživatele pro nespravovanou aktivitu MAM (nechráněný): Tato sestava obsahuje aktivitu jednotlivých aplikací povolených v MAM, které momentálně nejsou spravované, podle jednotlivých uživatelů. K tomu může dojít z následujících důvodů:

        -   Tyto aplikace používá uživatel nebo aplikace, která momentálně není cílem žádné zásady MAM.

        -   Všechny aplikace jsou zaregistrované, ale nejsou u nich použité žádné zásady MAM.

![Snímek obrazovky 2](./media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Seskupování tabulek

Jakmile se zobrazí data **sestavy uživatele ochrany aplikací**, můžete je agregovat podle těchto možností:

- **Výsledek ověřování:** Data se zobrazí seskupená podle stavu ochrany aplikace, který může být selhání, upozornění nebo úspěch.
- **Název aplikace:** Data se zobrazí seskupená podle aplikací (skutečného názvu aplikace) se selháním, upozorněním nebo úspěchem.

## <a name="export-app-protection-activities-to-csv"></a>Export aktivit ochrany aplikace do souboru CSV

Všechny aktivity ochrany aplikací můžete vyexportovat do jediného souboru .csv. To může být užitečné při analýze všech stavů ochrany aplikací hlášených od uživatelů.

Pokud chcete vygenerovat sestavu ochrany aplikací, postupujte takto:

1. V okně správy mobilních aplikací Intune zvolte Sestava ochrany aplikací.

    ![Snímek obrazovky 6](./media/app-protection-report-csv-2.png)

2. Zvolte Ano, aby se vaše sestava uložila, a pak zvolte Uložit jako a vyberte složku, do které chcete sestavu uložit.

    ![Snímek obrazovky 7](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Související témata
[Správa přenosu dat mezi aplikacemi pro iOS](data-transfer-between-apps-manage-ios.md)

* [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](app-protection-enabled-apps-android.md)
* [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](app-protection-enabled-apps-ios.md)
