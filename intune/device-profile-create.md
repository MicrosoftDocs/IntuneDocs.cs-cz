---
title: Vytvoření profilů zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Přidání nebo konfigurace profilu konfigurace zařízení v Microsoft Intune. Vyberte typ platformy, nakonfigurujte nastavení, přidejte značku oboru.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5adb094dad9c9e09874c83daecd39ce1d45156ed
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71303510"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Vytvořte profil zařízení v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profily zařízení umožňují přidat a nakonfigurovat nastavení a potom tato nastavení nasdílet do zařízení ve vaší organizaci. Použití [funkcí a nastavení na vašich zařízeních pomocí profilů zařízení](device-profiles.md) obsahuje více podrobností, včetně toho, co můžete dělat.

V tomto článku najdete:

- Seznam kroků pro vytvoření profilu.
- Ukazuje, jak přidat značku oboru do "Filter" Profile.
- Popisuje pravidla použitelnosti na zařízeních s Windows 10 a ukazuje, jak vytvořit pravidlo.
- Vypíše časy obnovení při vracení se změnami, když zařízení obdrží profily a všechny aktualizace profilu.

## <a name="create-the-profile"></a>Vytvoření profilu

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Vyberte **Konfigurace zařízení**. Máte následující možnosti:

    - **Přehled**: Zobrazuje stav profilů a poskytuje další podrobnosti o profilech, které jste přiřadili uživatelům a zařízením.
    - **Spravovat**: Vytvořte profily zařízení, nahrajte vlastní [skripty PowerShellu](intune-management-extension.md) , které se budou spouštět v rámci profilu, a přidejte do zařízení datové tarify pomocí [eSIM karty](esim-device-configuration.md).
    - **Monitorování**: Zkontrolujte stav profilu pro úspěch nebo neúspěch a také si prohlédněte protokoly v profilech.
    - **Nastavení**: Přidejte certifikační autoritu SCEP nebo PFX nebo povolte [správu telekomunikačních výdajů](telecom-expenses-monitor.md) v profilu.

3. Vyberte **profily** > **vytvořit profil**. Zadejte tyto vlastnosti:

   - **Název**: Zadejte popisný název profilu. Své profily pojmenujte, abyste je později mohli snadno identifikovat. Dobrým názvem profilu je například **e-mailový profil WP pro celou firmu**.
   - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
   - **Platforma**: Vyberte platformu zařízení. Možnosti:  

       - **Android**
       - **Android Enterprise**
       - **iOS/iPadOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 a novější**
       - **Windows 10 a novější**

   - **Typ profilu**: Vyberte typ nastavení, které chcete vytvořit. Zobrazený seznam závisí na zvolené **platformě** .
   - **Nastavení**: Informace o nastaveních pro jednotlivé typy profilů najdete v následujících článcích:

       - [Šablony pro správu](administrative-templates-windows.md)
       - [Vlastní](custom-settings-configure.md)
       - [Optimalizace doručení](delivery-optimization-windows.md)
       - [Funkce zařízení](device-features-configure.md)
       - [Omezení zařízení](device-restrictions-configure.md)
       - [Upgrade edice a přepínač režimu](edition-upgrade-configure-windows-10.md)
       - [Školení](education-settings-configure.md)
       - [E-mailu](email-settings-configure.md)
       - [Endpoint Protection](endpoint-protection-configure.md)
       - [Ochrana identit](identity-protection-configure.md)  
       - [Veřejný terminál](kiosk-settings.md)
       - [Certifikát PKCS](certficates-pfx-configure.md)
       - [Certifikát SCEP](certificates-scep-configure.md)
       - [Důvěryhodný certifikát](certificates-configure.md)
       - [Aktualizovat zásady](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Ochrana ATP v programu Windows Defender](advanced-threat-protection.md)
       - [Windows Information Protection](windows-information-protection-configure.md)

     Pokud třeba pro platformu vyberete **iOS/iPadOS** , možnosti typu vašeho profilu vypadají podobně jako v následujícím profilu:

     ![Vytvoření profilu iOS v Intune](./media/create-device-profile.png)

4. Po dokončení klikněte na **tlačítko OK** > **vytvořit** a uložte provedené změny. Profil se vytvoří a zobrazí se v seznamu.

## <a name="scope-tags"></a>Značky oboru

Po přidání nastavení můžete do profilu přidat také značku oboru. Značky oboru přiřazují a filtrují zásady pro konkrétní skupiny, jako je třeba HR nebo všichni zaměstnanci USA – NC.

Další informace o značkách oboru a o tom, co můžete dělat, najdete v tématu [použití značek RBAC a Scope pro distribuci](scope-tags.md).

### <a name="add-a-scope-tag"></a>Přidat značku oboru

1. Vyberte **obor (značky)** .
2. Vyberte **Přidat** a vytvořte novou značku oboru. Nebo vyberte ze seznamu existující značku oboru.
3. Vyberte **OK** uložte provedené změny.

## <a name="applicability-rules"></a>Pravidla použitelnosti

Platí pro:

- Windows 10 a novější

Pravidla použitelnosti umožňují správcům cílit na zařízení ve skupině, která splňuje určitá kritéria. Například vytvoříte profil omezení zařízení, který se vztahuje na skupinu **všech zařízení s Windows 10** . A potřebujete jenom profil přiřazený k zařízením s Windows 10 Enterprise.

Chcete-li provést tuto úlohu, vytvořte **pravidlo použitelnosti**. Tato pravidla jsou ideální pro následující scénáře:

- Používáte Windows 10 školství (EDU). V Bellows školy chcete cílit na všechna zařízení s Windows 10 EDU mezi RS3 a RS4.
- Chcete cílit všechny uživatele v lidských zdrojích na společnosti Contoso, ale přejete si pouze zařízení se systémem Windows 10 Professional nebo Enterprise.

Pro přístup k těmto scénářům máte tyto možnosti:

- Vytvořte skupinu zařízení, která zahrnuje všechna zařízení na Bellows škole. V profilu přidejte pravidlo použitelnosti, aby se naplatilo, pokud je `16299` minimální verze operačního systému a maximální `17134`verze. Přiřaďte tento profil ke skupině zařízení Bellows školy.

  Po přiřazení se profil vztahuje na zařízení mezi minimální a maximální verzí, které zadáte. U zařízení, která nepatří mezi minimální a maximální verze, které zadáte, se jejich stav zobrazuje jako **nepoužitý**.

- Vytvořte skupinu uživatelů, která bude obsahovat všechny uživatele v lidských zdrojích (HR) ve společnosti Contoso. V profilu přidejte pravidlo použitelnosti, aby se používalo pro zařízení s Windows 10 Professional nebo Enterprise. Přiřaďte tento profil skupině uživatelů personální oddělení.

  Po přiřazení se profil vztahuje na zařízení s Windows 10 Professional nebo Enterprise. U zařízení, která nepoužívají tyto edice, se jejich stav zobrazuje jako **nepoužitý**.

- Pokud existují dva profily s přesným nastavením, použije se profil bez pravidla použitelnosti. 

  Například profilace cílí na skupinu zařízení s Windows 10, povolí BitLocker a nemá pravidlo použitelnosti. ProfileB cílí na stejnou skupinu zařízení s Windows 10, umožňuje BitLocker a má pravidlo použitelnosti, které profil použije jenom na Windows 10 Enterprise.

  Při přiřazení obou profilů se použije profilace, protože nemá pravidlo použitelnosti. 

Když přiřadíte profil ke skupinám, budou pravidla použitelnosti fungovat jako filtr a budou cílit jenom na zařízení, která splňují vaše kritéria.

### <a name="add-a-rule"></a>Přidat pravidlo

1. Vyberte **pravidla použitelnosti**. Můžete zvolit **pravidlo**, **vlastnost**a **edici OS**:

    ![Přidání pravidla použitelnosti do konfiguračního profilu zařízení v Microsoft Intune](./media/applicability-rules.png)

2. V možnosti **pravidlo**vyberte, jestli chcete zahrnout nebo vyloučit uživatele nebo skupiny. Možnosti:

    - **Přiřadit profil, pokud**: Zahrnuje uživatele nebo skupiny, které splňují zadaná kritéria.
    - **Nepřiřazujte profil, pokud**: Vyloučí uživatele nebo skupiny, které splňují zadaná kritéria.

3. V **vlastnosti**vyberte filtr. Možnosti: 

    - **Edice operačního systému**: V seznamu vyhledejte edice Windows 10, které chcete zahrnout (nebo vyloučit) ve vašem pravidle.
    - **Verze operačního systému**: Zadejte **minimální** a **maximální** číslo verze Windows 10, které chcete zahrnout (nebo vyloučit) ve vašem pravidle. Obě hodnoty jsou povinné.

      Můžete například zadat `10.0.16299.0` (RS3 nebo 1709) pro minimální verzi a `10.0.17134.0` (RS4 nebo 1803) pro maximální verzi. Nebo můžete být přesnější a zadat `10.0.16299.001` minimální `10.0.17134.319` a maximální verzi.

4. Pokud chcete změny uložit, vyberte **Přidat** .

## <a name="refresh-cycle-times"></a>Aktualizovat časy cyklů

Intune používá ke kontrole aktualizací konfiguračních profilů různé aktualizační cykly. Pokud se zařízení nedávno zaregistrovalo, vrácení se změnami se spouští častěji. V [cyklech aktualizace zásad a profilů](device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) se zobrazí odhadované časy aktualizace.

Uživatelé mohou kdykoli otevřít aplikaci Portál společnosti a synchronizovat zařízení, aby ihned kontrolovala aktualizace profilu.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
