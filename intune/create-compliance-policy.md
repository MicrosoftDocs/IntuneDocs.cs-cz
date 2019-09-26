---
title: Zásady dodržování předpisů zařízením v Microsoft Intune – Azure | Microsoft Docs
description: Začněte používat zásady dodržování předpisů pro zařízení, Přehled stavů a úrovní závažnosti, použití stavu V období odkladu, práce s podmíněným přístupem, zpracování zařízení bez přiřazených zásad a rozdíly v dodržování předpisů v Azure Portal a klasický portál v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b7519b07b3ac2d40734c32b79466c6d7f4f5d4e8
ms.sourcegitcommit: 614c4c36cfe544569db998e17e29feeaefbb7a2e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2019
ms.locfileid: "71303961"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Vytvoření zásady dodržování předpisů v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zásady dodržování předpisů pro zařízení jsou klíčovou funkcí Intune, která umožňuje chránit prostředky organizace. V Intune můžete vytvořit pravidla a nastavení, která musí zařízení splňovat, aby se považovala za vyhovující, jako je třeba minimální verze operačního systému. Pokud zařízení nedodržuje předpisy, můžete zablokovat přístup k datům a prostředkům pomocí [podmíněného přístupu](conditional-access.md).

Můžete také provést akce při nedodržení předpisů, jako je například odeslání e-mailu s oznámením uživateli. Základní informace o tom, jaké zásady dodržování předpisů dělají a jak se používají, najdete v tématu [Začínáme s dodržováním předpisů zařízením](device-compliance-get-started.md).

V tomto článku najdete:

- Obsahuje seznam požadavků a kroků pro vytvoření zásady dodržování předpisů.
- Ukazuje, jak přiřadit zásady vašim skupinám uživatelů a zařízení.
- V této části najdete popis dalších funkcí, včetně tagů oboru pro filtrování zásad a kroků, které můžete provést na zařízeních, která nedodržují předpisy.
- Vypíše časy obnovení při vracení se změnami, když zařízení dostanou aktualizace zásad.

## <a name="before-you-begin"></a>Před zahájením

Pokud chcete používat zásady dodržování předpisů zařízením, ujistěte se, že jste:

- Použití následujících předplatných:

  - Intune
  - Pokud používáte podmíněný přístup, budete potřebovat Azure Active Directory (AD) Premium Edition. [Azure Active Directory Price](https://azure.microsoft.com/pricing/details/active-directory/) uvádí, co se vám s různými edicemi dostanou. Dodržování předpisů v Intune nevyžaduje Azure AD.

- Použití podporované platformy:

  - Android
  - Android Enterprise
  - iOS
  - macOS (preview)
  - Windows 10
  - Windows 8.1
  - Windows Phone 8.1

- Registrace zařízení v Intune (vyžaduje se pro zobrazení stavu dodržování předpisů)

- Zaregistrujte zařízení jednomu uživateli nebo se zaregistrujte bez primárního uživatele. Zařízení zaregistrovaná pro více uživatelů nejsou podporovaná.

## <a name="create-the-policy"></a>Vytvoření zásady

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Dodržování předpisů zařízením**. Máte následující možnosti:

    - **Přehled**: Zobrazuje souhrn a počet zařízení, která jsou v souladu s předpisy, nejsou vyhodnocena a tak dále. Obsahuje také seznam zásad a individuálních nastavení zásad. [Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md) nabízí nějaké dobré informace.
    - **Spravovat**: Vytvořte zásady zařízení, zasílejte [oznámení](quickstart-send-notification.md) na zařízení, která nedodržují předpisy, a povolte [síťové oplocení](use-network-locations.md).
    - **Monitorování**: Ověřte stav dodržování předpisů vašich zařízení a na úrovni zásad nastavení a zásady. [Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md) je dobrým prostředkem. Podívejte se také na protokoly a zkontrolujte stav agenta hrozeb vašich zařízení.
    - **Nastavení**: Použijte [předdefinované zásady dodržování předpisů](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies), povolte [Microsoft Defender Advanced Threat Protection (ATP)](advanced-threat-protection.md), přidejte [konektor ochrany před mobilními hrozbami](mobile-threat-defense.md)a použijte [Jamf](conditional-access-integrate-jamf.md).

3. Vyberte **Zásady** > **Vytvořit zásadu**. Zadejte tyto vlastnosti:

    - **Název**: Zadejte popisný název zásady. Své zásady pojmenujte, abyste je později mohli snadno identifikovat. Například dobrým názvem zásady je **zařízení s jailbreakem pro iOS označena jako nevyhovující předpisům**.
    - **Popis**: Zadejte popis zásady. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Vyberte platformu zařízení. Možnosti:  

       - **Android**
       - **Android Enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 a novější**
       - **Windows 10 a novější**

    - **Nastavení**: Následující seznam článků popisuje nastavení pro jednotlivé platformy:

        - [Android](compliance-policy-create-android.md)
        - [Android Enterprise](compliance-policy-create-android-for-work.md)
        - [iOS](compliance-policy-create-ios.md)
        - [macOS](compliance-policy-create-mac-os.md)
        - [Windows Phone 8,1, Windows 8.1 a novější](compliance-policy-create-windows-8-1.md)
        - [Windows 10 a novější](compliance-policy-create-windows.md)

4. Po dokončení klikněte na **tlačítko OK** > **vytvořit** a uložte provedené změny. Zásada se vytvoří a zobrazí se v seznamu. Potom tyto zásady přiřaďte do skupin.

## <a name="assign-user-groups"></a>Přiřazení skupin uživatelů

Po vytvoření zásady je dalším krokem přiřazení těchto zásad ke skupinám:

1. Vyberte zásadu, kterou jste vytvořili. Existující zásady najdete v **Dodržování předpisů zařízením** > **Zásady**.
2. Vyberte zásady > **přiřazení**. Můžete zahrnout nebo vyloučit skupiny zabezpečení služby Azure Active Directory (AD).
3. Vyberte **Vybrané skupiny** a zobrazte skupiny zabezpečení Azure AD. Vyberte skupiny uživatelů, pro které chcete tuto zásadu použít > zvolte **Uložit** , aby se zásady nasadily uživatelům.

Zásadu jste použili pro uživatele. U zařízení používaných uživateli, pro která platí nastavené zásady, se vyhodnocuje, jestli vyhovují.

### <a name="evaluate-how-many-users-are-targeted"></a>Vyhodnocení počtu cílových uživatelů

Když přiřadíte zásady, můžete také **vyhodnotit** , kolik uživatelů je ovlivněno. Tato funkce vypočítává uživatele. nepočítá zařízení.

1. V Intune vyberte**zásady** **dodržování předpisů** > zařízením.
2. Vyberte zásadu >**vyhodnotit** **přiřazení** > . Zobrazí se zpráva o tom, kolik uživatelů cílí na tyto zásady.

Pokud je tlačítko **vyhodnotit** šedé, ujistěte se, že je zásada přiřazena jedné nebo více skupinám.

## <a name="actions-for-noncompliance"></a>Akce při nedodržení předpisů

U zařízení, která nevyhovují zásadám dodržování předpisů, můžete přidat posloupnost akcí, které se mají použít automaticky. Pokud je zařízení označené jako nevyhovující, můžete plán třeba další den změnit. Můžete také nakonfigurovat druhou akci, která uživateli nevyhovujícího zařízení pošle e-mail.

Další informace, včetně návodu na vytvoření e-mailu s oznámením pro uživatele, najdete v článku o [přidání akcí pro nevyhovující zařízení](actions-for-noncompliance.md).

Pokud například používáte funkci Umístění, přidáte do zásady dodržování předpisů nějaké umístění a vyberete aspoň jedno umístění, použije se pro nevyhovující zařízení výchozí akce. Pokud zařízení není připojené k vybraným umístěním, považuje se hned za nevyhovující. Uživatelům můžete dát určitou lhůtu, třeba jeden den.

## <a name="scope-tags"></a>Značky oboru

Značky oboru jsou skvělým způsobem, jak přiřadit a filtrovat zásady pro konkrétní skupiny, jako je například prodej, HR, všichni zaměstnanci US-NC a tak dále. Po přidání nastavení můžete také přidat značku oboru do zásad dodržování předpisů. [Použití značek oboru k filtrování zásad](scope-tags.md) je dobrým prostředkem.

## <a name="refresh-cycle-times"></a>Aktualizovat časy cyklů

Intune používá ke kontrole aktualizací zásad dodržování předpisů různé aktualizační cykly. Pokud se zařízení nedávno zaregistrovalo, vrácení se změnami se spouští častěji. V [cyklech aktualizace zásad a profilů](device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) se zobrazí odhadované časy aktualizace.

V každém okamžiku můžou uživatelé aplikaci Portál společnosti otevřít a synchronizovat zařízení, aby se aktualizace zásad hned zkontrolovaly.

### <a name="assign-an-ingraceperiod-status"></a>Přiřazení stavu V období odkladu

Stav V období odkladu u zásad dodržování předpisů představuje hodnotu. Tuto hodnotu určuje kombinace období odkladu a skutečný stav daných zásad dodržování předpisů u zařízení.

Konkrétně, pokud má zařízení pro přiřazené zásady dodržování předpisů stav Nevyhovující předpisům a:

- K zařízení není přiřazené žádné období odkladu, ale přiřazená hodnota zásady dodržování předpisů není kompatibilní.
- Zařízení má období odkladu, které vypršelo, takže přiřazená hodnota zásady dodržování předpisů není kompatibilní.
- Zařízení má období odkladu, které je v budoucnu, takže přiřazená hodnota pro zásady dodržování předpisů je V období odkladu.

V následující tabulce najdete souhrnný přehled těchto bodů:

|Skutečný stav dodržování předpisů|Hodnota přiřazeného období odkladu|Účinný stav dodržování předpisů|
|---------|---------|---------|
|Nevyhovující předpisům |Bez přiřazeného období odkladu |Nevyhovující předpisům |
|Nevyhovující předpisům |Včerejší datum|Nevyhovující předpisům|
|Nevyhovující předpisům |Zítřejší datum|V období odkladu|

Další informace o monitorování zásad dodržování předpisů zařízením najdete v článku [Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md).

### <a name="assign-a-resulting-compliance-policy-status"></a>Přiřazení výsledného stavu zásad dodržování předpisů

Pokud má nějaké zařízení několik zásad dodržování předpisů a pro dvě nebo více z nich má různé stavy dodržování předpisů, přiřadí se mu jediný výsledný stav dodržování předpisů. Toto přiřazení vychází z koncepční úrovně závažnosti přiřazené jednotlivých stavům dodržování předpisů. Jednotlivé stavy dodržování předpisů mají následující úroveň závažnosti:

|Stav  |severity  |
|---------|---------|
|Neznámé     |1|
|NotApplicable     |2|
|Odpovídající|3|
|InGracePeriod|4|
|NonCompliant|5|
|Chyba|6|

Pokud má zařízení více zásad dodržování předpisů, přiřadí se mu nejvyšší úroveň závažnosti ze všech zásad.

Například zařízení má přiřazené tři zásady dodržování předpisů: jeden neznámý stav (závažnost = 1), jeden stav kompatibility (závažnost = 3) a jeden stav V období odkladu (závažnost = 4). Stav V období odkladu má nejvyšší úroveň závažnosti. To znamená, že všechny tři zásady mají stav dodržování předpisů V období odkladu.

## <a name="next-steps"></a>Další kroky

[Monitorujte své zásady](compliance-policy-monitor.md).