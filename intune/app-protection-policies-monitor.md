---
title: Jak monitorovat zásady ochrany aplikací
titleSuffix: Microsoft Intune
description: Toto téma popisuje, jak monitorovat stav dodržování zásad správy mobilních aplikací v Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 11f1bee18dd0abc377f756e4c64e9a8bafda3530
ms.sourcegitcommit: 2ab41ce2c781fc7bd1140a82b4f44d4cd2fc07b1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/19/2019
ms.locfileid: "71304531"
---
# <a name="how-to-monitor-app-protection-policies"></a>Jak monitorovat zásady ochrany aplikací
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Stav dodržování zásad správy mobilních aplikací (MAM), které jste použili pro uživatele, můžete monitorovat v podokně Ochrana aplikací Intune v [Azure Portal](https://portal.azure.com). Kromě toho můžete najít informace o uživatelích dotčených zásadami MAM, stavu dodržování zásad MAM a všech problémech, se kterými se uživatelé můžou setkat.

Stav dodržování předpisů zásad MAM můžete monitorovat třemi různými místy:
- Souhrnné zobrazení
- Podrobné zobrazení
- Zobrazení vytváření sestav

> [!NOTE]
> Informace o vytváření zásad ochrany aplikací najdete v článku [Vytvoření a přiřazení zásad ochrany aplikací](app-protection-policies.md).

Doba uchování dat ochrany aplikací je 90 dní. Všechny instance aplikace, které se vrátily do služby MAM v posledních 90 dnech, se budou zahrnovat do sestavy stav ochrany aplikací. Instance aplikace je jedinečného uživatele + aplikace a zařízení. 

## <a name="summary-view"></a>Souhrnné zobrazení

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V úloze **klientské aplikace** vyberte v části **monitor** možnost **stav ochrany aplikací** , aby se zobrazilo souhrnné zobrazení:

![Dlaždice souhrnu podokna Správa mobilních aplikací Intune](./media/app-protection-user-status-summary.png)

- **Přiřazení uživatelé**: Celkový počet přiřazených uživatelů ve vaší společnosti, kteří používají aplikaci přidruženou k zásadě v pracovním kontextu a jsou chráněni a licencováni, a také přiřazení nechráněných a nelicencovaných uživatelů.
- **Uživatelé označení příznakem**: Počet uživatelů, u kterých dochází k problémům. Zařízení s jailbreakem (iOS) a rootem (Android) se hlásí v části **Uživatelé označení příznakem**. Uživatelé se zařízeními, která jsou označená kontrolou ověření zařízení Google SafetyNet (Pokud je zapnutá správcem IT), jsou uvedená tady. 
- **Uživatelé s potenciálně škodlivými aplikacemi**: Počet uživatelů, kteří mohou mít na svém zařízení s Androidem škodlivou aplikaci zjištěnou Google Play chránit. 
- **Stav uživatele pro iOS** a **stav uživatele pro Android**: Počet uživatelů, kteří použili aplikaci, která má přiřazenou zásadu v pracovním kontextu pro související platformu. Tyto informace zobrazují počet uživatelů spravovaných zásadou a také počet uživatelů, kteří používají aplikaci, na kterou necílí žádné zásady v pracovním kontextu. Tyto uživatele případně můžete k zásadě přidat.
- **Nejvyšší chráněné aplikace pro iOS**: V závislosti na nejpoužívanějších aplikacích pro iOS zobrazuje tato informace počet chráněných a nechráněných aplikací pro iOS.
- **Nejvyšší chráněné aplikace pro Android**: Na základě nejpoužívanějších aplikací pro Android zobrazuje tato informace počet chráněných a nechráněných aplikací pro Android.
- **Hlavní nakonfigurované aplikace pro iOS bez registrace**: V závislosti na nejpoužívanějších aplikacích pro iOS u neregistrovaných zařízení zobrazuje tato informace počet nakonfigurovaných aplikací pro iOS.
- **Hlavní nakonfigurované aplikace pro Android bez registrace**: Na základě nejpoužívanějších aplikací pro Android pro neregistrovaná zařízení se v těchto informacích zobrazuje počet nakonfigurovaných aplikací pro Android.

    > [!NOTE]
    > Pokud máte pro každou platformu více zásad, bude uživatel považován za spravované pomocí zásad, když mají přiřazenou aspoň jednu zásadu.

## <a name="detailed-view"></a>Podrobné zobrazení
Podrobné zobrazení souhrnu získáte tak, že vyberete dlaždici **stav uživatele** (na platformě operačního systému zařízení), **uživatele s potenciálně škodlivými aplikacemi** a dlaždici uživatelé s **příznakem** .

### <a name="user-status"></a>Stav uživatele
Můžete vyhledat konkrétního uživatele a zkontrolovat u něj stav dodržování předpisů. V podokně **Vytváření sestav aplikace** se zobrazují následující informace o vybraném uživateli:
- **Ikona**: Zobrazuje, jestli je stav aplikace aktuální.
- **Název aplikace**: Název aplikace
- **Název zařízení**: Zařízení, která jsou přidružená k účtu uživatele.
- **Typ zařízení**: Typ zařízení nebo operačního systému, na kterém je zařízení spuštěno.
- **Zásady**: Zásady přidružené k aplikaci
- **Stav**:
  - **Vráceno se změnami**: Zásady se nasadily na uživatele a aplikace se aspoň jednou použila v pracovním kontextu.
  - **Nevráceno se změnami**: Zásady se nasadily na uživatele, ale aplikace se od té doby nepoužila v pracovním kontextu.
- **Poslední synchronizace**: Čas poslední synchronizace zařízení.

>[!NOTE]
> Pokud uživatel, kterého jste hledali, nemá nasazené zásady MAM, zobrazí se zpráva, že na uživatele není zacílená žádná zásada MAM.

Pokud chcete zobrazit vytváření sestav pro uživatele, postupujte takto:

1. Chcete-li vybrat uživatele, zvolte dlaždici souhrn **stavu uživatele** .

    ![Snímek obrazovky se souhrnem dlaždice Správa mobilních aplikací Intune](./media/MAM-reporting-6.png)

2. Otevře se podokno **Vytváření sestav aplikace**. Zvolte **Vybrat uživatele** a najděte uživatele služby Azure Active Directory.

    ![Snímek obrazovky s možností vybrat uživatele v podokně vytváření sestav aplikací](./media/MAM-reporting-2.png)

3. Vyberte uživatele ze seznamu. Zobrazí se podrobné informace o konkrétním uživateli a stavu dodržování předpisů.

### <a name="flagged-users"></a>Uživatelé označení příznakem
V podrobném přehledu se zobrazí chybová zpráva, otevíraná aplikace v okamžiku chyby, dotčená platforma operačního systému zařízení a časové razítko. Uživatelé se zařízeními, která jsou označena příznakem podmíněného spuštění ověření zařízení SafetyNet, se tady zobrazí v důsledku ohlášení Google.

### <a name="users-with-potentially-harmful-apps"></a>Uživatelé s potenciálně škodlivými aplikacemi
V podrobném zobrazení se zobrazuje uživatel, ID balíčku aplikace, pokud je aplikace MAM povolená, kategorie hrozeb, e-mail, název zařízení a časové razítko. Uživatelé se zařízeními, která jsou označena příznakem "vyžadovat kontrolu hrozeb u aplikací" podmíněný, jsou zde uvedena v kategorii hrozby, jak je uvedeno na webu Google. Pokud jsou v této sestavě nasazující aplikace, které se nasazují prostřednictvím Intune, kontaktujte vývojáře aplikace a/nebo odeberte aplikaci, která se přiřadí koncovým uživatelům. 

## <a name="reporting-view"></a>Zobrazení vytváření sestav

Stejné sestavy můžete najít v horní části okna **stavu ochrany aplikace** .

> [!NOTE]
> Intune poskytuje další pole pro vytváření sestav zařízení, včetně ID registrace aplikace, výrobce Androidu, modelu a verze opravy zabezpečení i modelu iOS. V Intune jsou tato pole dostupná, a to tak, že vyberete **klientské aplikace** > **stav aplikace App Protection** a zvolíte **sestavu ochrana aplikací: iOS, Android**. Kromě toho tyto parametry můžete nakonfigurovat **povolit** seznamu pro výrobce zařízení (Android), **povolit** seznam pro model zařízení (Android a iOS) a minimální opravu zabezpečení Androidu nastavení verze. 

K dispozici jsou další sestavy, které vám pomůžou se stavem dodržování zásad MAM. Pokud chcete zobrazit tyto sestavy, vyberte **klientské aplikace** >  > **sestavy** **stavů aplikace App Protection**. 

Okno **sestavy** obsahuje několik sestav založených na uživateli a aplikaci, včetně následujících:


- **Sestava uživatele**: Tato sestava obsahuje stejné informace, které najdete v sestavě **stav uživatele** v části [podrobné zobrazení](app-protection-policies-monitor.md#detailed-view) výše.

- **Sestava aplikace**: Kromě výběru platformy a aplikace poskytuje tato sestava dva různé stavy ochrany aplikací, které můžete vybrat před generováním sestavy. Stav může být **chráněný** nebo **nechráněný**.

  - Stav uživatele pro spravovanou aktivitu MAM (**chráněno**): Tato sestava popisuje aktivity každé spravované aplikace MAM pro jednotlivé uživatele. Zobrazuje všechny aplikace, které jsou cílem zásad MAM, pro jednotlivé uživatele. Zobrazuje také rozdělení stavu jednotlivých aplikací podle toho, jak jsou zaregistrované v zásadách MAM, nebo aplikací, které jsou cílem zásad MAM, ale nebyly nikdy zaregistrované.
  - Stav uživatele pro nespravovanou aktivitu MAM (**Nechráněno**): Tato sestava popisuje aktivity aplikací s podporou MAM, které jsou aktuálně nespravované, na základě jednotlivých uživatelů. K tomu může dojít z následujících důvodů:
    - Tyto aplikace používá uživatel nebo aplikace, která momentálně není cílem žádné zásady MAM.
    - Všechny aplikace jsou zaregistrované, ale nejsou u nich použité žádné zásady MAM.

    ![Snímek obrazovky okna pro vytváření sestav aplikace uživatele s podrobnostmi pro 3 aplikace](./media/MAM-reporting-4.png)

- **Sestava konfigurace uživatele**: V závislosti na vybraném uživateli Tato sestava obsahuje podrobnosti o všech konfiguracích aplikace, které uživatel přijal.
- **Sestava konfigurace aplikace**: Základem pro vybranou platformu a aplikaci Tato sestava obsahuje podrobnosti o tom, kteří uživatelé přijali konfigurace pro vybranou aplikaci.
- **Sestava o studiu aplikací pro Windows Information Protection**: Tato sestava zobrazuje, které aplikace se pokoušejí o vzájemné hranice zásad.
- **Information Protection výuky webů pro Windows**: Tato sestava ukazuje, které weby se pokoušejí o vzájemné hranice zásad.

## <a name="table-grouping"></a>Seskupování tabulek

Jakmile se zobrazí data **sestavy uživatele ochrany aplikací** , můžete agregovat data následujícím způsobem:

- **Výsledek ověření:** Data se zobrazí seskupená podle stavu ochrany aplikace, což může být chyba, upozornění nebo úspěch.
- **Název aplikace:** Data se zobrazí seskupená podle aplikací (skutečný název aplikace) s chybou, upozorněním nebo úspěchem.

## <a name="export-app-protection-activities-to-csv"></a>Export aktivit ochrany aplikace do souboru CSV

Všechny aktivity zásad ochrany aplikací můžete exportovat do jediného souboru *. csv* . To může být užitečné při analýze všech stavů ochrany aplikací hlášených od uživatelů.

Pokud chcete vygenerovat sestavu ochrany aplikací, postupujte takto:

1. V podokně správy mobilních aplikací Intune zvolte **Sestava ochrany aplikací**.

    ![Snímek obrazovky s odkazem ke stažení ochrany aplikace](./media/app-protection-report-csv-2.png)

2. Zvolte **Ano** , pokud chcete sestavu uložit, a pak zvolte **Uložit jako** a vyberte složku, do které chcete sestavu uložit.

    ![Snímek obrazovky pole pro potvrzení uložení sestavy](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Viz také:
- [Správa přenosu dat mezi aplikacemi pro iOS](data-transfer-between-apps-manage-ios.md)
- [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](app-protection-enabled-apps-android.md)
- [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](app-protection-enabled-apps-ios.md)
