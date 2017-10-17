---
title: "Monitorování zásad MAM pomocí Microsoft Intune"
description: "Podívejte se, kolik uživatelů má přiřazené zásady. Přechodem k podrobnostem zjistíte další informace."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b4b25c2ebe6fa8edf7ce954f68c22d4086fcaf7c
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2017
---
# <a name="monitor-app-protection-policies-with-microsoft-intune"></a>Sledování zásad ochrany aplikací pomocí Microsoft Intune
Stav dodržování zásad ochrany aplikací, které jste použili u uživatelů, můžete monitorovat. Budete moct vyhledat informace o uživatelích, na které se vztahují zásady ochrany aplikací, stavu dodržování zásad a všech problémech, se kterými se uživatelé můžou setkat.

Stav dodržování zásad můžete monitorovat na třech místech:

-   Souhrnné zobrazení

-   Podrobné zobrazení

-   Zobrazení vytváření sestav

## <a name="summary-view"></a>Souhrnné zobrazení

Souhrnné zobrazení otevřete následujícím postupem:

1. Přejděte na portál [Azure Portal](https://portal.azure.com) a zadejte přihlašovací údaje.
2. Zvolte **Další služby** a do textového pole filtru zadejte **Intune**.
3. Zvolte **Ochrana aplikací Intune**.

V okně **Správa mobilních aplikací Intune** si můžete prohlédnout souhrnné informace o stavu dodržování zásad:

![Dlaždice souhrnu okna Správa mobilních aplikací Intune](../media/mam-azure-portal-user-status-summary.png)

-   **Uživatelé**: celkový počet uživatelů ve společnosti, kteří používají aplikaci spojenou se zásadou v pracovním kontextu.

-   **SPRAVOVÁNO ZÁSADOU**: počet uživatelů, kteří použili aplikaci a je jim v pracovním kontextu přiřazena zásada.

-   **ŽÁDNÉ ZÁSADY**: počet uživatelů, kteří používají aplikaci, na kterou není v pracovním kontextu zamířena žádná zásada. Tyto uživatele případně můžete k zásadě přidat.
    > [!NOTE]
    > Pokud máte pro každou platformu víc zásad, bude uživatel považován za spravovaného zásadou, pokud je mu přiřazena aspoň jedna zásada.

- **Uživatelé označení příznakem:** Počet uživatelů, kteří mají problémy. V současnosti jsou v části **Uživatelé označení příznakem** jenom uživatelé zařízení, u kterých byla zrušena softwarová omezení (zařízení s jailbreakem).


## <a name="detailed-view"></a>Podrobné zobrazení
Pokud se chcete podívat na podrobnosti přehledu, zvolte dlaždici **Stav uživatele** (podle platformy operačního systému) a pak dlaždici **Uživatelé označení příznakem**.

### <a name="user-status"></a>Stav uživatele
Můžete vyhledat konkrétního uživatele a zkontrolovat u něj stav dodržování předpisů. V okně **Vytváření sestav aplikace** se zobrazují následující informace o vybraném uživateli:
- Zařízení přidružená k účtu uživatele

- Aplikace se zásadami ochrany aplikací na zařízení

- Stav:

  - **Zaregistrováno:** Zásada byla u uživatele nasazena a aplikace byla alespoň jednou použita v pracovním kontextu.

  - **Není zaregistrováno:** Zásada byla u uživatele nasazena, ale aplikace od té doby nebyla použita v pracovním kontextu.

>[!NOTE]
> Pokud uživatel, kterého jste hledali, nemá nasazené zásady ochrany aplikací, zobrazí se zpráva, že uživatel není cílem pro žádné zásady ochrany aplikací.

Pokud chcete zobrazit vytváření sestav pro uživatele, postupujte takto:

1.  Uživatele vyberte tak, že zvolíte dlaždici **Souhrn**.

    ![Snímek obrazovky 3](../media/MAM-reporting-6.png)

2. Otevře se okno **Vytváření sestav aplikace**. Zvolte **Vybrat uživatele** a najděte uživatele služby Azure Active Directory.

    ![Možnost výběru uživatele v okně Vytváření sestav aplikace](../media/MAM-reporting-2.png)

3. Vyberte uživatele ze seznamu. Zobrazí se podrobné informace o konkrétním uživateli a stavu dodržování předpisů.

### <a name="flagged-users"></a>Uživatelé označení příznakem
V podrobném přehledu se zobrazí chybová zpráva, otevíraná aplikace v okamžiku chyby, dotčená platforma operačního systému zařízení a časové razítko.

## <a name="reporting-view"></a>Zobrazení vytváření sestav

Najdete tady stejné sestavy jako v Podrobném zobrazení, ale i další sestavy, které vám pomůžou se stavem dodržování zásad ochrany aplikací:

![Snímek obrazovky 4](../media/MAM-reporting-7.png)

-   **Sestava uživatele ochrany aplikací:** Obsahuje stejné informace, které najdete v sestavě **Stav uživatele** v části Podrobné zobrazení výše.

-   **Sestava aplikace ochrany aplikací:** Poskytuje dva různé stavy ochrany aplikací, které správce může před generováním sestavy vybrat. Může vybrat chráněný nebo nechráněný stav.

    -   Stav uživatele pro spravovanou aktivitu MAM (chráněný): Tato sestava obsahuje aktivitu jednotlivých aplikací spravovaných prostřednictvím MAM podle jednotlivých uživatelů.

        -   Pro jednotlivé uživatele se zobrazí všechny aplikace, na které jsou zacílené zásady ochrany aplikací. Zobrazí se také rozdělení stavu jednotlivých aplikací podle toho, jak jsou zaregistrované v zásadách ochrany aplikací, nebo aplikací, na které jsou zacílené zásady ochrany aplikací, ale nebyly nikdy zaregistrované.
<br></br>
    -   Stav uživatele pro nespravovanou aktivitu MAM (nechráněný): Tato sestava obsahuje aktivitu jednotlivých aplikací povolených v MAM, které momentálně nejsou spravované, podle jednotlivých uživatelů. K tomu může dojít z následujících důvodů:

        -   Tyto aplikace používají uživatel nebo aplikace, na které momentálně nejsou zacílené žádné zásady ochrany aplikací.

        -   Všechny aplikace jsou zaregistrované, ale nejsou u nich použité žádné zásady ochrany aplikací.

![Snímek obrazovky 2](../media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Seskupování tabulek

Jakmile se zobrazí data **sestavy uživatele ochrany aplikací**, můžete je agregovat podle těchto možností:

- **Výsledek ověřování:** Data se zobrazí seskupená podle stavu ochrany aplikace, který může být selhání, upozornění nebo úspěch.
- **Název aplikace:** Data se zobrazí seskupená podle aplikací (skutečného názvu aplikace) se selháním, upozorněním nebo úspěchem.

## <a name="export-app-protection-activities-to-csv"></a>Export aktivit ochrany aplikace do souboru CSV

Všechny aktivity ochrany aplikací můžete vyexportovat do jediného souboru .csv. To může být užitečné při analýze všech stavů ochrany aplikací hlášených od uživatelů.

Pokud chcete vygenerovat sestavu ochrany aplikací, postupujte takto:

1. V okně správy mobilních aplikací Intune zvolte Sestava ochrany aplikací.

    ![Snímek obrazovky 6](../media/app-protection-report-csv-2.png)

2. Zvolte Ano, aby se vaše sestava uložila, a pak zvolte Uložit jako a vyberte složku, do které chcete sestavu uložit.

    ![Snímek obrazovky 7](../media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Související témata
[Správa přenosu dat mezi aplikacemi pro iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](/intune/end-user-mam-apps-android)
* [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](/intune/end-user-mam-apps-ios)
