---
title: "Monitorování zásad MAM s Microsoft Intune | Dokumentace Microsoftu"
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
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 22c30f51bf83219053f97310ed1830ad9e01acd8
ms.openlocfilehash: bd270cd4b04894d4824487d36ea4f0c1929dd568


---

# <a name="monitor-mobile-app-management-policies-with-microsoft-intune"></a>Monitorování zásad správy mobilních aplikací s Microsoft Intune
Můžete monitorovat stav dodržování zásad správy mobilních aplikací (MAM), které jste použili u uživatelů. Budete moct vyhledat informace o uživatelích dotčených zásadami MAM, stavu dodržování zásad a všech problémech, se kterými se uživatelé mohou setkat.

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

    ![Snímek obrazovky 3](../media/MAM-reporting-6.png)

2. Otevře se okno **Vytváření sestav aplikace**. Zvolte **Vybrat uživatele** a najděte uživatele služby Azure Active Directory.

    ![Možnost výběru uživatele v okně Vytváření sestav aplikace](../media/MAM-reporting-2.png)

3. Vyberte uživatele ze seznamu. Zobrazí se podrobné informace o konkrétním uživateli a stavu dodržování předpisů.

### <a name="flagged-users"></a>Uživatelé označení příznakem
V podrobném přehledu se zobrazí chybová zpráva, otevíraná aplikace v okamžiku chyby, dotčená platforma operačního systému zařízení a časové razítko.

## <a name="reporting-view"></a>Zobrazení vytváření sestav

Najdete tady stejné sestavy jako v Podrobném zobrazení, ale i další sestavy, které vám pomůžou se stavem dodržování zásad MAM:

![Snímek obrazovky&4;](../media/MAM-reporting-7.png)

-   **Sestava uživatele ochrany aplikací:** Obsahuje stejné informace, které najdete v sestavě **Stav uživatele** v části Podrobné zobrazení výše.

-   **Sestava aplikace ochrany aplikací:** Poskytuje dva různé stavy ochrany aplikací, které správce může před generováním sestavy vybrat. Může vybrat chráněný nebo nechráněný stav.

    -   Stav uživatele pro spravovanou aktivitu MAM (chráněný): Tato sestava obsahuje aktivitu jednotlivých aplikací spravovaných prostřednictvím MAM podle jednotlivých uživatelů.

        -   Zobrazuje všechny aplikace, které jsou cílem zásad MAM, pro jednotlivé uživatele. Zobrazuje také rozdělení stavu jednotlivých aplikací podle toho, jak jsou zaregistrované v zásadách MAM, nebo aplikací, které jsou cílem zásad MAM, ale nebyly nikdy zaregistrované.
<br></br>
    -   Stav uživatele pro nespravovanou aktivitu MAM (nechráněný): Tato sestava obsahuje aktivitu jednotlivých aplikací povolených v MAM, které momentálně nejsou spravované, podle jednotlivých uživatelů. K tomu může dojít z následujících důvodů:

        -   Tyto aplikace používá uživatel nebo aplikace, která momentálně není cílem žádné zásady MAM.

        -   Všechny aplikace jsou zaregistrované, ale nejsou u nich použité žádné zásady MAM.

![Snímek obrazovky&2;](../media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Seskupování tabulek

Jakmile se zobrazí data **sestavy uživatele ochrany aplikací**, můžete je agregovat podle těchto možností:

- **Výsledek ověřování:** Data se zobrazí seskupená podle stavu ochrany aplikace, který může být selhání, upozornění nebo úspěch.
- **Název aplikace:** Data se zobrazí seskupená podle aplikací (skutečného názvu aplikace) se selháním, upozorněním nebo úspěchem.

## <a name="export-app-protection-activities-to-csv"></a>Export aktivit ochrany aplikace do souboru CSV

Všechny aktivity ochrany aplikací můžete vyexportovat do jediného souboru .csv. To může být užitečné při analýze všech stavů ochrany aplikací hlášených od uživatelů.

Pokud chcete vygenerovat sestavu ochrany aplikací, postupujte takto:

1. V okně správy mobilních aplikací Intune zvolte Sestava ochrany aplikací.

    ![Snímek obrazovky&6;](../media/app-protection-report-csv-2.png)

2. Zvolte Ano, aby se vaše sestava uložila, a pak zvolte Uložit jako a vyberte složku, do které chcete sestavu uložit.

    ![Snímek obrazovky&7;](../media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Viz taky
[Správa přenosu dat mezi aplikacemi pro iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Co očekávat, když ke správě své aplikace pro Android používáte zásady MAM](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Co očekávat, když ke správě své aplikace pro iOS používáte zásady MAM](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Feb17_HO2-->


