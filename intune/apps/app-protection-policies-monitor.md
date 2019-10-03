---
title: Jak monitorovat zásady ochrany aplikací
titleSuffix: Microsoft Intune
description: Toto téma popisuje, jak monitorovat zásady ochrany aplikací v Intune.
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
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0b4ab3369f241c9f33d4e0bddfd0dcf98c8ab915
ms.sourcegitcommit: fc356fd69beaeb3d69982b47e2bdffb6f7127f8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/03/2019
ms.locfileid: "71830600"
---
# <a name="how-to-monitor-app-protection-policies"></a>Jak monitorovat zásady ochrany aplikací
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Stav dodržování zásad správy mobilních aplikací (MAM), které jste použili pro uživatele, můžete monitorovat v podokně Ochrana aplikací Intune v [Azure Portal](https://portal.azure.com). Kromě toho můžete najít informace o uživatelích dotčených zásadami MAM, stavu dodržování zásad MAM a všech problémech, se kterými se uživatelé můžou setkat.

Existují tři různá místa, kde můžete monitorovat zásady ochrany aplikací:
- Souhrnné zobrazení
- Podrobné zobrazení
- Zobrazení sestav

> [!NOTE]
> Informace o vytváření zásad ochrany aplikací najdete v tématu [jak vytvořit a přiřadit zásady ochrany aplikací](app-protection-policies.md).

Doba uchování dat ochrany aplikací je 90 dní. Všechny instance aplikace, které se vrátily do služby MAM v posledních 90 dnech, se budou zahrnovat do sestavy stav ochrany aplikací. Instance aplikace je jedinečného uživatele + aplikace a zařízení. 

## <a name="summary-view"></a>Souhrnné zobrazení

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** vyberte **klientské aplikace**.
4. V úloze **klientské aplikace** vyberte v části **monitor** možnost **stav ochrany aplikací** , aby se zobrazilo souhrnné zobrazení:

![Dlaždice souhrnu v podokně Správa mobilních aplikací Intune](./media/app-protection-policies-monitor/app-protection-user-status-summary.png)

- **Přiřazení uživatelé**: celkový počet přiřazených uživatelů ve vaší společnosti, kteří používají aplikaci přidruženou k zásadě v pracovním kontextu a jsou chráněni a licencováni, a také přiřazení nechráněných uživatelů a jejich nelicencovaných uživatelů.
- **Uživatelé označení příznakem**: počet uživatelů, u kterých dochází k problémům. Zařízení s jailbreakem (iOS) a rootem (Android) se hlásí v části **Uživatelé označení příznakem**. Uživatelé se zařízeními, která jsou označená kontrolou ověření zařízení Google SafetyNet (Pokud je zapnutá správcem IT), jsou uvedená tady. 
- **Uživatelé s potenciálně škodlivými aplikacemi**: počet uživatelů, kteří můžou mít v zařízení s Androidem zjištěnou škodlivou aplikaci Google Play chránit. 
- **Stav uživatele pro iOS** a **stav uživatele pro Android**: počet uživatelů, kteří použili aplikaci, která má přiřazenou zásadu v pracovním kontextu pro související platformu. Tyto informace zobrazují počet uživatelů spravovaných zásadou a také počet uživatelů, kteří používají aplikaci, na kterou necílí žádné zásady v pracovním kontextu. Můžete zvážit přidání těchto uživatelů k zásadě.
- **Nejvyšší chráněné aplikace pro iOS**: na základě nejpoužívanějších aplikací pro iOS zobrazuje tyto informace počet chráněných a nechráněných aplikací pro iOS.
- **Nejvyšší chráněné aplikace pro Android**: na základě nejpoužívanějších aplikací pro Android zobrazuje tyto informace počet chráněných a nechráněných aplikací pro Android.
- **Hlavní nakonfigurované aplikace pro iOS bez registrace**: na základě nejpoužívanějších aplikací pro iOS u neregistrovaných zařízení zobrazuje tato informace počet nakonfigurovaných aplikací pro iOS.
- **Hlavní nakonfigurované aplikace pro Android bez registrace**: na základě nejpoužívanějších aplikací pro Android pro neregistrovaná zařízení se zobrazí tyto informace o počtu nakonfigurovaných aplikací pro Android.

    > [!NOTE]
    > Pokud máte pro každou platformu více zásad, bude uživatel považován za spravované pomocí zásad, když mají přiřazenou aspoň jednu zásadu.

## <a name="detailed-view"></a>Podrobné zobrazení
Podrobné zobrazení souhrnu získáte tak, že vyberete dlaždici **stav uživatele** (na platformě operačního systému zařízení), **uživatele s potenciálně škodlivými aplikacemi** a dlaždici uživatelé s **příznakem** .

### <a name="user-status"></a>Stav uživatele
Můžete vyhledat jednoho uživatele a ověřit stav dodržování předpisů pro tohoto uživatele. V podokně **vytváření sestav aplikace** se zobrazují následující informace o vybraném uživateli:
- **Ikona**: zobrazuje, jestli je stav aplikace aktuální.
- **Název aplikace**: název aplikace.
- **Název zařízení**: zařízení, která jsou přidružená k účtu uživatele.
- **Typ zařízení**: typ zařízení nebo operačního systému, na kterém zařízení běží.
- **Zásady**: zásady přidružené k aplikaci.
- **Stav**:
  - **Zaregistrováno**: zásada byla nasazena pro uživatele a aplikace byla alespoň jednou použita v pracovním kontextu.
  - **Není zaregistrováno**: zásada byla nasazena uživateli, ale aplikace nebyla od té doby použita v pracovním kontextu.
- **Poslední synchronizace**: čas poslední synchronizace aplikace s Intune. 

>[!NOTE]
> Sloupec ' poslední synchronizace ' představuje stejnou hodnotu jak ve zprávě o stavu uživatele v konzole, tak v [sestavě pro export](https://docs.microsoft.com/intune/app-protection-policies-monitor#export-app-protection-activities-to-csv)do zásad ochrany aplikací. csv. Rozdíl je malé zpoždění v rámci synchronizace mezi hodnotou v sestavách 2. 
>
> Čas, na který se odkazuje v části "poslední synchronizace", je čas, kdy se Intune naposledy viděl jako instance aplikace. Instance aplikace je jedinečnou kombinací aplikace + uživatele + zařízení. Když koncový uživatel spustí aplikaci, může nebo nemusí komunikovat se službou Intune App Protection v době spuštění, v závislosti na tom, kdy byla naposledy vrácena. Tato dokumentace vám pomůže objasnit [časy intervalu opakování při vracení se změnami zásad ochrany aplikací](https://docs.microsoft.com/en-us/intune/app-protection-policy-delivery). Takže pokud koncový uživatel nepoužil tuto konkrétní aplikaci v intervalu Poslední vrácení se změnami (což je obvykle 30 minut pro aktivní použití) a spustí aplikaci, pak:
>
> - Sestava ochrany aplikací exportovatelné. csv bude mít nejnovější čas do 1 minuty (obvykle minimálně) až 30 minut (maximální SLA je skutečně poskytována agregací SQL, kterou používá vytváření sestav Intune).
> - Zpráva o stavu uživatele bude mít nejnovější čas okamžitě.
>
> Představte si třeba cílového a licencovaného koncového uživatele, který spustí chráněnou aplikaci v 12:00. odp.:
> - Pokud se jedná o první přihlášení, znamená to, že se koncový uživatel před (neaktivním použitím) odhlásil, což by znamenalo, že v Intune nemá registraci instance aplikace. Jakmile se přihlásí, získá novou registraci instance aplikace a zaregistruje se hned po nepotížích s připojením. u budoucích vrácení se změnami se stejnou dobou zpoždění uvedená výše. Čas poslední synchronizace by tedy měl nahlásit jako 12:00 odp. v sestavě stav uživatele a 12:01 odp. (nebo 12:30 v horším případě ODP.) zásady ochrany aplikací. 
> - Pokud byla aplikace pouze spuštěna, bude čas poslední synchronizace záviset na tom, kdy byla naposledy vrácena.


Chcete-li zobrazit sestavy pro uživatele, postupujte podle následujících kroků:

1. Chcete-li vybrat uživatele, zvolte dlaždici souhrn **stavu uživatele** .

    ![Snímek obrazovky se souhrnem dlaždice Správa mobilních aplikací Intune](./media/app-protection-policies-monitor/MAM-reporting-6.png)

2. V podokně **vytváření sestav aplikací** zvolte **Vybrat uživatele** a vyhledejte uživatele Azure Active Directory.

    ![Snímek obrazovky s možností vybrat uživatele v podokně vytváření sestav aplikací](./media/app-protection-policies-monitor/MAM-reporting-2.png)

3. Vyberte uživatele ze seznamu. Můžete zobrazit podrobnosti o stavu dodržování předpisů pro tohoto uživatele.

>[!NOTE]
> Pokud uživatelé, které jste hledali, nemá nasazené zásady MAM, zobrazí se zpráva s oznámením, že uživatel není cílem žádné zásady MAM.

### <a name="flagged-users"></a>Uživatelé označení příznakem
V podrobném zobrazení se zobrazí chybová zpráva, aplikace, ke které došlo v okamžiku, kdy došlo k chybě, byla ovlivněna platforma operačního systému zařízení a časové razítko. Uživatelé se zařízeními, která jsou označena příznakem podmíněného spuštění ověření zařízení SafetyNet, se tady zobrazí v důsledku ohlášení Google.

### <a name="users-with-potentially-harmful-apps"></a>Uživatelé s potenciálně škodlivými aplikacemi
V podrobném zobrazení se zobrazuje uživatel, ID balíčku aplikace, pokud je aplikace MAM povolená, kategorie hrozeb, e-mail, název zařízení a časové razítko. Uživatelé se zařízeními, která jsou označena příznakem "vyžadovat kontrolu hrozeb u aplikací", jsou zde uvedena v kategorii hrozby, jak je uvedeno na webu Google. Pokud jsou v této sestavě nasazující aplikace, které se nasazují prostřednictvím Intune, kontaktujte vývojáře aplikace a/nebo odeberte aplikaci, která se přiřadí koncovým uživatelům. 

## <a name="reporting-view"></a>Zobrazení sestav

Stejné sestavy můžete najít v horní části okna **stavu ochrany aplikace** .

> [!NOTE]
> Intune poskytuje další pole pro vytváření sestav zařízení, včetně ID registrace aplikace, výrobce Androidu, modelu a verze opravy zabezpečení i modelu iOS. V Intune jsou tato pole k dispozici. Vyberte **klientské aplikace**@no__t**stav ochrany aplikace** -1 a zvolte **sestavu ochrana aplikací: iOS, Android**. Kromě toho vám tyto parametry pomůžou nakonfigurovat nastavení seznam **povolených** pro výrobce zařízení (Android), seznam **povolených** pro model zařízení (Android a iOS) a minimální verzi opravy zabezpečení Androidu. 

K dispozici jsou další sestavy, které vám pomůžou se stavem dodržování zásad MAM. Chcete-li zobrazit tyto sestavy, vyberte **klientské aplikace** > **zpráva**o**stavu ochrany aplikace** > . 

Okno **sestavy** obsahuje několik sestav založených na uživateli a aplikaci, včetně následujících:


- **Sestava uživatele**: Tato sestava obsahuje stejné informace, které najdete v sestavě **stav uživatele** v části [podrobné zobrazení](app-protection-policies-monitor.md#detailed-view) výše.

- **Sestava aplikace**: Kromě výběru platformy a aplikace poskytuje tato sestava dva různé stavy ochrany aplikací, které můžete vybrat před generováním sestavy. Stav může být **chráněný** nebo **nechráněný**.

  - Stav uživatele pro spravovanou aktivitu MAM (**chráněno**): Tato sestava popisuje aktivity každé spravované aplikace mam na základě jednotlivých uživatelů. Zobrazuje všechny aplikace, které jsou cílem zásad MAM pro jednotlivé uživatele, a rozdělují stav každé aplikace jako vrácené se změnami pomocí zásad MAM, nebo na které cílí zásady MAM, ale aplikace se nikdy nevrátila.
  - Stav uživatele pro nespravovanou aktivitu MAM (**Nechráněno**): Tato sestava popisuje aktivity aplikací s podporou mam, které jsou aktuálně nespravované, na základě jednotlivých uživatelů. K tomu může dojít z následujících důvodů:
    - Tyto aplikace používá uživatel nebo aplikace, které nejsou aktuálně cílem zásady MAM.
    - Všechny aplikace jsou zaregistrované, ale nezískávají žádné zásady MAM.

    ![Snímek obrazovky okna pro vytváření sestav aplikace uživatele s podrobnostmi pro 3 aplikace](./media/app-protection-policies-monitor/MAM-reporting-4.png)

- **Sestava konfigurace uživatele**: na základě vybraného uživatele Tato sestava obsahuje podrobnosti o všech konfiguracích aplikace, které uživatel přijal.
- **Sestava konfigurace aplikací**: základem pro vybranou platformu a aplikaci, Tato sestava obsahuje podrobnosti o tom, kteří uživatelé přijali konfigurace pro vybranou aplikaci.
- **Sestava výukového programu pro Windows Information Protection**: Tato sestava obsahuje informace o tom, které aplikace se pokoušejí přes hranice zásad.
- **Information Protection pro web**: Tato sestava obsahuje informace o tom, které weby se pokoušejí přes hranice zásad.

## <a name="table-grouping"></a>Seskupení tabulek

Jakmile se zobrazí data **sestavy uživatele ochrany aplikací** , můžete agregovat data následujícím způsobem:

- **Výsledek ověření:** Data se zobrazí seskupená podle stavu ochrany aplikace, což může být chyba, upozornění nebo úspěch.
- **Název aplikace:** Data se zobrazí seskupená podle aplikací (skutečný název aplikace) s chybou, upozorněním nebo úspěchem.

## <a name="export-app-protection-activities-to-csv"></a>Exportovat aktivity ochrany aplikací do sdíleného svazku clusteru

Všechny aktivity zásad ochrany aplikací můžete exportovat do jediného souboru *. csv* . To může být užitečné při analýze všech stavů ochrany aplikace hlášených uživateli.

Pomocí těchto kroků vygenerujte sestavu ochrany aplikací:

1. V podokně Správa mobilních aplikací Intune klikněte na možnost **Sestava ochrany aplikací**.

    ![Snímek obrazovky s odkazem ke stažení ochrany aplikace](./media/app-protection-policies-monitor/app-protection-report-csv-2.png)

2. Zvolte **Ano** , pokud chcete sestavu uložit, a pak zvolte **Uložit jako** a vyberte složku, do které chcete sestavu uložit.

    ![Snímek obrazovky s polem pro potvrzení uložení sestavy](./media/app-protection-policies-monitor/app-protection-report-csv-1.png)

## <a name="see-also"></a>Další informace najdete v tématech
- [Správa přenosu dat mezi aplikacemi pro iOS](data-transfer-between-apps-manage-ios.md)
- [Co očekávat, když je vaše aplikace pro Android spravovaná pomocí zásad ochrany aplikací](../fundamentals/end-user-mam-apps-android.md)
- [Co očekávat, když je vaše aplikace pro iOS spravovaná zásadami ochrany aplikací](../fundamentals/end-user-mam-apps-ios.md)
