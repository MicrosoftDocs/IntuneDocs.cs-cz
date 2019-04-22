---
title: Zásady dodržování předpisů zařízením v Microsoft Intune – Azure | Microsoft Docs
description: Začínáme se zásadami dodržování předpisů zařízení používá, přehled stavu a úrovně závažnosti, použití stav v období odkladu, práce s podmíněným přístupem, manipulace se zařízením bez přiřazených zásad a rozdíl v dodržování předpisů na portálu Azure portal a portál Classic v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: da0aa98774f25bf290391225c6ccae56a3859c22
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59896044"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Vytvoření zásad dodržování předpisů v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zásady dodržování předpisů pro zařízení jsou klíčovou funkcí Intune, která umožňuje chránit prostředky organizace. V Intune můžete vytvořit pravidla a nastavení, které zařízení musí splňovat, aby být považováno za dodržující předpisy, jako je například minimální verze operačního systému. Pokud zařízení nevyhovuje, můžete [podmíněným přístupem](conditional-access.md) zablokovat přístup k datům a prostředkům.

Můžete taky využít akce při nedodržení předpisů, jako je odeslání e-mailové oznámení pro uživatele. Přehled o čem zásady dodržování předpisů a jak se používají, najdete v části [Začínáme s dodržováním předpisů zařízeními](device-compliance-get-started.md).

V tomto článku najdete:

- Jsou uvedené požadavky a kroky k vytvoření zásady dodržování předpisů.
- Ukazuje, jak přiřadit zásady skupin uživatelů a zařízení.
- Popisuje další funkce, včetně značky oboru pro "filtrování" zásady a kroky, které si můžete na zařízeních, která nedodržují předpisy.
- Obsahuje aktualizace vrácení se změnami cyklus doby, kdy zařízení přijímat aktualizace zásad.

## <a name="before-you-begin"></a>Před zahájením

Chcete-li použít zásady dodržování předpisů zařízením, můžete:

- Použití následujících předplatných:

  - Intune
  - Pokud používáte podmíněný přístup, musíte edici Azure Active Directory (AD) Premium. [Ceny za Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/) uvádí, co všechno získáte s různými edicemi. Dodržování předpisů v Intune nevyžaduje, aby Azure AD.

- Použití podporované platformy:

  - Android
  - Android Enterprise
  - iOS
  - macOS (preview)
  - Windows 10
  - Windows 8.1
  - Windows Phone 8.1

- Registrace zařízení v Intune (vyžaduje se chcete podívat na stav dodržování předpisů)

- Registrace zařízení na jednoho uživatele nebo zaregistrovat bez primárního uživatele. Zařízení zaregistrovaná ve službě více uživatelů nejsou podporovány.

## <a name="create-the-policy"></a>Vytvoření zásad

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **Dodržování předpisů zařízením**. Máte následující možnosti:

    - **Přehled**: Zobrazí shrnutí a počet zařízení, která dodržují předpisy, není vyhodnocen, a tak dále. Obsahuje také seznam zásad a individuálních nastavení ve vašich zásad. [Monitorování zásad dodržování předpisů zařízení Intune](compliance-policy-monitor.md) určité správné informace.
    - **Správa**: Vytvoření zásady pro zařízení, odesílání [oznámení](quickstart-send-notification.md) a zařízení nedodržující předpisy, povolit [sítě monitorování geografických zón](use-network-locations.md).
    - **Monitorování**: Kontrola stavu dodržování předpisů zařízení a na úrovni nastavení a zásady. [Monitorování zásad dodržování předpisů zařízení Intune](compliance-policy-monitor.md) Dobrým zdrojem informací je. Zobrazit protokoly a zkontrolujte stav agenta hrozeb z vašich zařízení.
    - **Instalační program**: Použít [zásady dodržování předpisů integrované](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies), povolit [Rozšířená ochrana před internetovými útoky (ATP) programu Windows Defender](advanced-threat-protection.md), přidat [konektor mobile threat defense](mobile-threat-defense.md)a použijte [Jamf](conditional-access-integrate-jamf.md).

3. Vyberte **Zásady** > **Vytvořit zásadu**. Zadejte tyto vlastnosti:

    - **Název**: Zadejte popisný název pro zásadu. Zásady pojmenujte, abyste je později mohli snadno identifikovat. Například je název dobré zásady **iOS s jailbreakem zařízení označí jako nedodržující předpisy**.
    - **Popis**: Zadejte popis zásady. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Zvolte platformu zařízení. Možnosti:  

       - **Android**
       - **Android Enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 a novější**
       - **Windows 10 a novější**

    - **Nastavení**: V následujících článcích seznamu a popisu nastavení pro každou platformu:

        - [Android](compliance-policy-create-android.md)
        - [Android Enterprise](compliance-policy-create-android-for-work.md)
        - [iOS](compliance-policy-create-ios.md)
        - [macOS](compliance-policy-create-mac-os.md)
        - [Windows Phone 8.1, Windows 8.1 a novější](compliance-policy-create-windows-8-1.md)
        - [Windows 10 a novější](compliance-policy-create-windows.md)

4. Až budete hotovi, vyberte **OK** > **vytvořit** uložte provedené změny. Zásady je vytvořen a zobrazí v seznamu. Dále přiřaďte zásady skupiny.

## <a name="assign-user-groups"></a>Přiřazení skupin uživatelů

Jakmile zásadu vytvoříte, dalším krokem je přiřaďte zásady skupiny:

1. Vyberte zásady, kterou jste vytvořili. Existující zásady najdete v **Dodržování předpisů zařízením** > **Zásady**.
2. Vyberte zásady > **přiřazení**. Můžete zahrnout nebo vyloučit skupiny zabezpečení služby Azure Active Directory (AD).
3. Vyberte **Vybrané skupiny** a zobrazte skupiny zabezpečení Azure AD. Vyberte skupiny uživatelů, které chcete použít tyto zásady > zvolit **Uložit** zásadu nasadit pro uživatele.

Jste zásady uplatnili u uživatelů. U zařízení používaných uživateli, pro která platí nastavené zásady, se vyhodnocuje, jestli vyhovují.

### <a name="evaluate-how-many-users-are-targeted"></a>Vyhodnotit, kolik uživatelů cílí.

Když přiřadíte zásady, můžete také **vyhodnotit** kolik uživatelů se TOP týká. Tato funkce vypočítá uživatelů. nepočítá zařízení.

1. V Intune, vyberte **dodržování předpisů zařízením** > **zásady**.
2. Vyberte zásadu > **přiřazení** > **vyhodnotit**. Zprávy ukazuje, kolik uživatelů cílí tuto zásadu.

Pokud **vyhodnotit** tlačítko nejde aktivovat, ujistěte se, že je zásada přiřazena do jedné nebo více skupin.

## <a name="actions-for-noncompliance"></a>Akce při nedodržení předpisů

Pro zařízení, která nesplňují zásady dodržování předpisů můžete přidat posloupnost akcí použít automaticky. Pokud je zařízení označené jako nevyhovující, můžete plán třeba další den změnit. Můžete také nakonfigurovat druhou akci, která uživateli nevyhovujícího zařízení pošle e-mail.

Další informace, včetně návodu na vytvoření e-mailu s oznámením pro uživatele, najdete v článku o [přidání akcí pro nevyhovující zařízení](actions-for-noncompliance.md).

Pokud například používáte funkci Umístění, přidáte do zásady dodržování předpisů nějaké umístění a vyberete aspoň jedno umístění, použije se pro nevyhovující zařízení výchozí akce. Pokud zařízení není připojené k vybraným umístěním, považuje se hned za nevyhovující. Uživatelům můžete dát určitou lhůtu, třeba jeden den.

## <a name="scope-tags"></a>Značky oboru

Značky oboru jsou skvělý způsob, jak přiřadit zásady na konkrétní skupiny, jako je Sales, HR, zaměstnanci všechny USA-síťový adaptér, filtrovat a tak dále. Po přidání nastavení, můžete také přidat značky oboru do zásad dodržování předpisů. [Pomocí značky oboru filtru zásad](scope-tags.md) Dobrým zdrojem informací je.

## <a name="refresh-cycle-times"></a>Aktualizovat doby cyklů

Při kontrole dodržování předpisů, Intune používá stejný cyklus aktualizace jako konfigurační profily. Obecně platí časy jsou:

| Platforma | Aktualizovat cyklu|
| --- | --- |
| iOS | Každých 6 hodin |
| macOS | Každých 6 hodin |
| Android | Každých 8 hodin |
| Počítače s Windows 10 zaregistrované jako zařízení | Každých 8 hodin |
| Windows Phone | Každých 8 hodin |
| Windows 8.1 | Každých 8 hodin |

Pokud zařízení zaregistrovalo nedávno, se změnami dodržování předpisů se spustí častěji:

| Platforma | Četnost |
| --- | --- |
| iOS | Prvních 6 hodin každých 15 minut a potom každých 6 hodin |  
| macOS | Prvních 6 hodin každých 15 minut a potom každých 6 hodin | 
| Android | Prvních 15 minut každé 3 minuty, další 2 hodiny každých 15 minut a potom každých 8 hodin | 
| Počítače s Windows 10 zaregistrované jako zařízení | Prvních 30 minut každé 3 minuty a potom každých 8 hodin | 
| Windows Phone | Prvních 15 minut každých 5 minut, další 2 hodiny každých 15 minut a potom každých 8 hodin | 
| Windows 8.1 | Prvních 15 minut každých 5 minut, další 2 hodiny každých 15 minut a potom každých 8 hodin | 

Kdykoli můžete uživatelům otevřete aplikaci portál společnosti a synchronizovat zařízení okamžitě zkontroloval zásady.

### <a name="assign-an-ingraceperiod-status"></a>Přiřazení stavu V období odkladu

Stav V období odkladu u zásad dodržování předpisů představuje hodnotu. Tuto hodnotu určuje kombinace období odkladu a skutečný stav daných zásad dodržování předpisů u zařízení.

Konkrétně, pokud má zařízení pro přiřazené zásady dodržování předpisů stav Nevyhovující předpisům a:

- k zařízení není přiřazené žádné období odkladu, přiřadí se zásadám dodržování předpisů hodnota Nevyhovující předpisům.
- zařízení má období odkladu, které vypršelo, přiřadí se zásadám dodržování předpisů hodnota Nevyhovující předpisům.
- zařízení má období odkladu, které je v budoucnosti, přiřadí se zásadám dodržování předpisů hodnota V období odkladu.

V následující tabulce najdete souhrnný přehled těchto bodů:

|Skutečný stav dodržování předpisů|Hodnota přiřazeného období odkladu|Účinný stav dodržování předpisů|
|---------|---------|---------|
|Nevyhovující předpisům |Bez přiřazeného období odkladu |Nevyhovující předpisům |
|Nevyhovující předpisům |Včerejší datum|Nevyhovující předpisům|
|Nevyhovující předpisům |Zítřejší datum|V období odkladu|

Další informace o monitorování zásad dodržování předpisů zařízením najdete v článku [Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md).

### <a name="assign-a-resulting-compliance-policy-status"></a>Přiřazení výsledného stavu zásad dodržování předpisů

Pokud má nějaké zařízení několik zásad dodržování předpisů a pro dvě nebo více z nich má různé stavy dodržování předpisů, přiřadí se mu jediný výsledný stav dodržování předpisů. Toto přiřazení vychází z koncepční úrovně závažnosti přiřazené jednotlivých stavům dodržování předpisů. Jednotlivé stavy dodržování předpisů mají následující úroveň závažnosti:

|Stav  |Severity  |
|---------|---------|
|Neznámé     |1|
|NotApplicable     |2|
|Odpovídající|3|
|InGracePeriod|4|
|NonCompliant|5|
|Chyba|6|

Pokud má zařízení více zásad dodržování předpisů, přiřadí se mu nejvyšší úroveň závažnosti ze všech zásad.

Například má zařízení přiřazené tři zásady dodržování předpisů: jedna má stav neznámé (závažnost = 1), jedna má stav vyhovuje (závažnost = 3) a jeden stav v období odkladu (závažnost = 4). Stav v období odkladu má nejvyšší úroveň závažnosti. Proto mají všechny tři zásady stav dodržování předpisů v období odkladu.

## <a name="next-steps"></a>Další postup

[Monitorovat zásady](compliance-policy-monitor.md).