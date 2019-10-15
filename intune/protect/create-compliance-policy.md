---
title: Vytvoření zásad dodržování předpisů pro zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Vytvoření zásad dodržování předpisů pro zařízení, Přehled stavů a úrovní závažnosti, použití stavu V období odkladu, práce s podmíněným přístupem, zpracování zařízení bez přiřazené zásady a rozdíly v dodržování předpisů na portálu Azure Portal a Classic v nástroji Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0ec8003264c28ea40d53731c8fb8c3eddef7fded
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306579"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Vytvoření zásady dodržování předpisů v Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Zásady dodržování předpisů pro zařízení jsou klíčovou funkcí při použití Intune k ochraně prostředků vaší organizace. V Intune můžete vytvořit pravidla a nastavení, která musí zařízení splňovat, aby se považovala za vyhovující, jako je třeba minimální verze operačního systému. Pokud zařízení nedodržuje předpisy, můžete zablokovat přístup k datům a prostředkům pomocí [podmíněného přístupu](conditional-access.md).

Můžete také provést akce při nedodržení předpisů, jako je například odeslání e-mailu s oznámením uživateli. Základní informace o tom, jaké zásady dodržování předpisů dělají a jak se používají, najdete v tématu [Začínáme s dodržováním předpisů zařízením](device-compliance-get-started.md).

Tento článek:

- Obsahuje seznam požadavků a kroků pro vytvoření zásady dodržování předpisů.
- Ukazuje, jak přiřadit zásady vašim skupinám uživatelů a zařízení.
- V této části najdete popis dalších funkcí, včetně tagů oboru pro filtrování zásad a kroků, které můžete provést na zařízeních, která nedodržují předpisy.
- Vypíše časy obnovení při vracení se změnami, když zařízení dostanou aktualizace zásad.

## <a name="before-you-begin"></a>Než začnete

Pokud chcete používat zásady dodržování předpisů zařízením, ujistěte se, že jste:

- Použijte následující odběry:

  - Intune
  - Pokud používáte podmíněný přístup, budete potřebovat Azure Active Directory (AD) Premium Edition. [Azure Active Directory Price](https://azure.microsoft.com/pricing/details/active-directory/) uvádí, co se vám s různými edicemi dostanou. Dodržování předpisů v Intune nevyžaduje Azure AD.

- Použijte podporovanou platformu:

  - Android
  - Android Enterprise
  - iOS
  - macOS (Preview)
  - Windows 10
  - Windows 8.1
  - Windows Phone 8,1

- Registrace zařízení v Intune (vyžaduje se pro zobrazení stavu dodržování předpisů)

- Zaregistrujte zařízení jednomu uživateli nebo se zaregistrujte bez primárního uživatele. Zařízení zaregistrovaná pro více uživatelů nejsou podporovaná.

## <a name="create-the-policy"></a>Vytvoření zásady

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **dodržování předpisů zařízením**. Máte následující možnosti:

    - **Přehled**: zobrazuje souhrn a počet zařízení, která jsou kompatibilní, nejsou vyhodnocena a tak dále. Obsahuje také seznam zásad a individuálních nastavení zásad. [Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md) nabízí nějaké dobré informace.
    - **Správa**: vytváření zásad zařízení, posílání [oznámení](quickstart-send-notification.md) na nevyhovujících zařízeních a povolení [síťové oplocení](use-network-locations.md).
    - **Monitorování**: Ověřte stav dodržování předpisů vašich zařízení a na úrovni zásad nastavení a zásady. [Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md) je dobrým prostředkem. Podívejte se také na protokoly a zkontrolujte stav agenta hrozeb vašich zařízení.
    - **Nastavení**: použijte [předdefinované zásady dodržování předpisů](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies), povolte [Microsoft Defender Advanced Threat Protection (ATP)](advanced-threat-protection.md), přidejte [konektor ochrany před mobilními hrozbami](mobile-threat-defense.md)a použijte [Jamf](conditional-access-integrate-jamf.md).

3. Vyberte **zásady** > **vytvořit zásadu**. Zadejte následující vlastnosti:

    - **Název**: zadejte popisný název zásady. Své zásady pojmenujte, abyste je později mohli snadno identifikovat. Například dobrým názvem zásady je **zařízení s jailbreakem pro iOS označena jako nevyhovující předpisům**.
    - **Popis**: zadejte popis zásady. Toto nastavení je volitelné, ale doporučuje se.
    - **Platforma**: vyberte platformu zařízení. Vaše možnosti:  

       - **Android**
       - **Android Enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8,1**
       - **Windows 8.1 a novější**
       - **Windows 10 a novější**

    - **Nastavení**: Následující seznam článků popisuje nastavení pro jednotlivé platformy:

        - [Android](compliance-policy-create-android.md)
        - [Android Enterprise](compliance-policy-create-android-for-work.md)
        - [iOS](compliance-policy-create-ios.md)
        - [macOS](compliance-policy-create-mac-os.md)
        - [Windows Phone 8,1, Windows 8.1 a novější](compliance-policy-create-windows-8-1.md)
        - [Windows 10 a novější](compliance-policy-create-windows.md)

4. Po dokončení vyberte **OK** > **vytvořit** a uložte provedené změny. Zásada se vytvoří a zobrazí se v seznamu. Potom tyto zásady přiřaďte do skupin.

## <a name="assign-the-policy"></a>Přiřadit zásadu

Po vytvoření zásady je dalším krokem přiřazení těchto zásad ke skupinám:

1. Vyberte zásadu, kterou jste vytvořili. Stávající zásady jsou v**zásadách** **dodržování předpisů zařízením**@no__t 1.
2. Vyberte zásady > **přiřazení**. Můžete zahrnout nebo vyloučit skupiny zabezpečení Azure Active Directory (AD).
3. Zvolením možnosti **vybrané skupiny** zobrazíte skupiny zabezpečení služby Azure AD. Vyberte skupiny, které chcete použít pro tuto zásadu > klikněte na **Uložit** a zásadu nasaďte.

Uživatelé nebo zařízení, na které vaše zásada cílí, se vyhodnotí pro dodržování předpisů při jejich vrácení se změnami pomocí Intune.

### <a name="evaluate-how-many-users-are-targeted"></a>Vyhodnocení počtu cílových uživatelů

Když přiřadíte zásady, můžete také **vyhodnotit** , kolik uživatelů je ovlivněno. Tato funkce vypočítává uživatele. nepočítá zařízení.

1. V Intune vyberte**zásady**@no__t **dodržování předpisů zařízením**– 1.
2. Vyberte zásadu > **přiřazení** > **vyhodnotit**. Zobrazí se zpráva o tom, kolik uživatelů cílí na tyto zásady.

Pokud je tlačítko **vyhodnotit** šedé, ujistěte se, že je zásada přiřazena jedné nebo více skupinám.

## <a name="actions-for-noncompliance"></a>Akce při nedodržení předpisů

U zařízení, která nevyhovují zásadám dodržování předpisů, můžete přidat posloupnost akcí, které se mají použít automaticky. Plán můžete změnit, pokud je zařízení označeno jako nedodržující předpisy, například po jednom dni. Můžete také nakonfigurovat druhou akci, která uživateli pošle e-mail, když zařízení nedodržuje předpisy.

[Přidání akcí pro zařízení nedodržující předpisy](actions-for-noncompliance.md) obsahuje další informace, včetně vytvoření e-mailu s oznámením pro uživatele.

Například používáte funkci umístění a přidáte umístění do zásad dodržování předpisů. Výchozí akce při nedodržení předpisů se použije, když vyberete aspoň jedno umístění. Pokud zařízení není připojené k vybraným umístěním, okamžitě se považuje za nevyhovující. Uživatelům můžete poskytnout dobu odkladu, například jeden den.

## <a name="scope-tags"></a>Značky oboru

Značky oboru jsou skvělým způsobem, jak přiřadit a filtrovat zásady pro konkrétní skupiny, jako je například prodej, HR, všichni zaměstnanci US-NC a tak dále. Po přidání nastavení můžete také přidat značku oboru do zásad dodržování předpisů. [Použití značek oboru k filtrování zásad](../fundamentals/scope-tags.md) je dobrým prostředkem.

## <a name="refresh-cycle-times"></a>Aktualizovat časy cyklů

Intune používá ke kontrole aktualizací zásad dodržování předpisů různé aktualizační cykly. Pokud se zařízení nedávno zaregistrovalo, vrácení se změnami se spouští častěji. V [cyklech aktualizace zásad a profilů](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) se zobrazí odhadované časy aktualizace.

V každém okamžiku můžou uživatelé aplikaci Portál společnosti otevřít a synchronizovat zařízení, aby se aktualizace zásad hned zkontrolovaly.

### <a name="assign-an-ingraceperiod-status"></a>Přiřazení stavu V období odkladu

Stav V období odkladu pro zásady dodržování předpisů je hodnota. Tato hodnota je určena kombinací období odkladu zařízení a skutečným stavem zařízení pro tyto zásady dodržování předpisů.

Konkrétně platí, že pokud má zařízení nekompatibilní stav pro přiřazenou zásadu dodržování předpisů a:

- K zařízení není přiřazené žádné období odkladu, ale přiřazená hodnota zásady dodržování předpisů není kompatibilní.
- Zařízení má období odkladu, které vypršelo, takže přiřazená hodnota zásady dodržování předpisů není kompatibilní.
- Zařízení má období odkladu, které je v budoucnu, takže přiřazená hodnota pro zásady dodržování předpisů je V období odkladu.

Následující tabulka shrnuje tyto body:

|Skutečný stav dodržování předpisů|Hodnota přiřazeného období odkladu|Platný stav dodržování předpisů|
|---------|---------|---------|
|Nekompatibilních |Není přiřazené žádné období odkladu. |Nekompatibilních |
|Nekompatibilních |Včerejší datum|Nekompatibilních|
|Nekompatibilních |Zítřejší datum|V období odkladu|

Další informace o monitorování zásad dodržování předpisů zařízeními najdete v tématu [monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md).

### <a name="assign-a-resulting-compliance-policy-status"></a>Přiřazení výsledného stavu zásad dodržování předpisů

Pokud má zařízení více zásad dodržování předpisů a má jiné stavy dodržování předpisů pro dvě nebo více těchto zásad dodržování předpisů, bude přiřazen jediný výsledný stav dodržování předpisů. Toto přiřazení vychází z koncepční úrovně závažnosti přiřazené každému stavu dodržování předpisů. Každý stav dodržování předpisů má následující úroveň závažnosti:

|Stav  |Závažnost  |
|---------|---------|
|Není známo     |1\. místo|
|NotApplicable     |2|
|V souladu s předpisy|3|
|V období odkladu|4|
|Nekompatibilních|5|
|Chyba|6|

Pokud má zařízení více zásad dodržování předpisů, přiřadí se k tomuto zařízení nejvyšší úroveň závažnosti všech zásad.

Například zařízení má přiřazené tři zásady dodržování předpisů: jeden neznámý stav (závažnost = 1), jeden stav kompatibility (závažnost = 3) a jeden stav V období odkladu (závažnost = 4). Stav V období odkladu má nejvyšší úroveň závažnosti. To znamená, že všechny tři zásady mají stav dodržování předpisů V období odkladu.

## <a name="next-steps"></a>Další kroky

[Monitorujte své zásady](compliance-policy-monitor.md).
