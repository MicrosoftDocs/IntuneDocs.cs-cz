---
title: Vytvoření a nasazení zásad ochrany aplikací
titleSuffix: Microsoft Intune
description: Podívejte se, jak vytvořit a přiřadit zásady ochrany aplikací Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 368c804fa044dc303b22e2ae9cf8d273d6cd051a
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2018
ms.locfileid: "48231810"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Vytvoření a přiřazení zásad ochrany aplikací

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Podívejte se, jak vytvořit a přiřadit zásady ochrany aplikací Microsoft Intune k uživatelům. Toto téma také popisuje, jak změnit existující zásady.

## <a name="before-you-begin"></a>Před zahájením

Zásady ochrany aplikací je možné použít pro aplikace běžící na zařízeních, která může nebo nemusí spravovat Intune. Podrobnější popis, jak fungují zásady ochrany aplikací, a scénáře podporované zásadami ochrany aplikací Intune najdete v tématu [Co jsou zásady ochrany aplikací Microsoft Intune](app-protection-policy.md).

Pokud hledáte seznam aplikací s podporou MAM, přejděte na [seznam aplikací MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Informace o přidání obchodních aplikací organizace do Microsoft Intune kvůli přípravě na zásady ochrany aplikací najdete v tématu [Přidání aplikací do Microsoft Intune](apps-add.md).

##  <a name="create-an-app-protection-policy"></a>Vytvoření zásady ochrany aplikací
1. V úloze **Klientské aplikace** vyberte **Zásady ochrany aplikací** v oddíle **Správa**. Po výběru této možnosti se zobrazí detaily **Zásady ochrany aplikací**, kde můžete vytvářet nové zásady a upravovat stávající.
2. Zvolte **Přidat zásadu**.

   ![Snímek obrazovky okna Přidat zásadu](./media/app-protection-add-policy.png)

3. Zadejte název zásady, přidejte stručný popis a vyberte pro zásadu typ platformy. V případě potřeby je možné pro každou platformu vytvořit několik zásad.

4. Zvolte možnost **Aplikace** a otevřete tak okno **Aplikace**, kde se zobrazí seznam dostupných aplikací. Ze seznamu vyberte jednu nebo několik aplikací a přidružte je k zásadě, kterou vytváříte.
5. Jakmile vyberete aplikace, uložte vybrané možnosti volbou **Vybrat**.

    > [!IMPORTANT]
    > Při vytváření zásady musíte vybrat aspoň jednu aplikaci.

6. V okně **Přidat zásadu** zvolte **Konfigurovat požadované nastavení**. Otevře se **Nastavení**.

   Existují dvě kategorie nastavení zásad, **Přemístění dat** a **Přístup**.  Zásady přemístění dat platí pro přesun dat do aplikace a z aplikace. Zásady přístupu určují, jak získává koncový uživatel přístup k aplikacím v pracovním kontextu.
   Nastavením zásad jsou pro začátek přiřazené výchozí hodnoty. Pokud tyto výchozí hodnoty splňují vaše požadavky, nemusíte nic měnit.

   > [!TIP]
   > Tato nastavení zásad se vynutí jenom při použití aplikace v pracovním kontextu. Když koncový uživatel použije aplikaci k provedení osobní úlohy, nebudou mít tyto zásady na ni vliv. Upozorňujeme, že když vytvoříte nový soubor, považuje se za osobní soubor. 

7. Tuto konfiguraci uložíte zvolením tlačítka **OK**. A jste zpátky v okně **Přidat zásadu**.
8. Zvolením možnosti **Vytvořit** vytvoříte zásadu a uložíte své nastavení.

Zásada není po vytvoření pomocí výš uvedeného postupu nasazená pro žádného uživatele. Pokud chcete nasadit zásadu, přečtěte si téma [Nasazení zásady pro uživatele](app-protection-policies.md#deploy-a-policy-to-users).

## <a name="deploy-a-policy-to-users"></a>Nasazení zásady pro uživatele

1. V podokně **Zásady ochrany aplikací** vyberte zásadu.

2. V podokně **Zásada** vyberte **Přiřazení**. Otevře se podokno **Intune App Protection – Přiřazení**. Zvolte **Vybrat skupiny, které se zahrnou** v podokně **Přiřazení** a otevřete tak podokno **Vybrat skupiny, které se zahrnou**.

   ![Snímek obrazovky podokna Přiřazení se zvýrazněnou možností nabídky Vybrat skupiny, které se zahrnou](./media/app-protection-policy-add-users.png)

3.  V podokně **Přidat skupinu uživatelů** se zobrazí seznam skupin uživatelů. Je to seznam všech skupin zabezpečení v **Azure Active Directory**. Vyberte skupiny uživatelů, pro které chcete tuto zásadu použít, a pak zvolte **Vybrat**. Zvolením možnosti **Vybrat** nasadíte tuto zásadu uživatelům.

    ![Snímek obrazovky podokna Přidat skupinu uživatelů zobrazující seznam uživatelů Azure Active Directory](./media/azure-ad-user-group-list.png)

Teď je zásada vytvořená a nasazená u uživatelů.

Tyto zásady ovlivní jenom uživatele, kteří mají přiřazené licence Microsoft Intune. Nemají vliv na uživatele ve vybrané skupině zabezpečení, kteří nemají přiřazenou licenci pro Intune.

>[!IMPORTANT]
> Pokud ke správě zařízení používáte Intune s Configuration Managerem, použijí se zásady jenom pro uživatele přímo ve skupinách, které jste vybrali. Na členy podřízených skupin vnořených ve skupině, kterou jste vybrali, tyto zásady nemají vliv.

Koncoví uživatelé můžou stahovat aplikace z App Storu nebo Google Play. Více informací najdete v následujících tématech:
* [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](app-protection-enabled-apps-android.md)
* [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a>Změna existujících zásad
Podle potřeby můžete upravit existující zásady a použít je pro cílové uživatele. Když ale změníte existující zásady, nezobrazí se po dobu 8 hodin změny uživatelům, kteří se už přihlásili k aplikacím.

Pokud koncový uživatel chce, aby se změny projevily hned, musí se odhlásit od aplikace a pak se k ní zase přihlásit.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Změna seznamu aplikací přidružených k zásadě

1.  V podokně **Zásady ochrany aplikací** vyberte zásadu, kterou chcete změnit, a otevřete tak podokno specifické pro právě vybranou zásadu.

2.  V podokně zásady zvolte **Cílené aplikace**. Otevře se seznam aplikací.

3.  V seznamu odeberte nebo přidejte aplikace a zvolením ikony **Uložit** uložte změny, které jste provedli.

### <a name="to-change-the-list-of-user-groups"></a>Změna seznamu skupin uživatelů


1.  V podokně **Zásady ochrany aplikací** vyberte zásadu, kterou chcete změnit, a otevřete tak podokno specifické pro vybranou zásadu.

2.  V podokně zásady zvolte **Přiřazení** a otevřete tak podokno **Intune App Protection – Přiřazení** se seznamem aktuálních skupin uživatelů, kteří mají tuto zásadu.

3.  Pokud chcete přidat k zásadě novou skupinu uživatelů, zvolte na kartě **Zahrnout** možnost **Vybrat skupiny, které se zahrnou** a vyberte skupinu uživatelů. Zvolením možnosti **Vybrat** nasadíte zásadu do skupiny uživatelů, kterou jste vybrali.

4.  Pokud chcete odstranit skupinu uživatelů, zvolte na kartě **Vyjmout** možnost **Vybrat skupiny, které se vyloučí** a vyberte skupinu uživatelů. Skupinu uživatelů odeberte pomocí možnosti **Vybrat**.

### <a name="to-change-policy-settings"></a>Změna nastavení zásad

1.  V podokně **Zásady ochrany aplikací** vyberte zásadu, kterou chcete změnit, a otevřete tak podokno specifické pro právě vybranou zásadu.

2.  Zvolte možnost **Nastavení zásad** a otevřete tak podokno **Nastavení zásad**.

3.  Změňte nastavení a pak změny uložte zvolením ikony **Uložit**.

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Cílení zásad ochrany aplikací na základě stavu správy zařízení
Mnoho organizací běžně umožňuje koncovým uživatelům používat jak zařízení spravovaná přes Intune MDM (Mobile Device Management), například zařízení ve vlastnictví společnosti, tak i nespravovaná zařízení chráněná pouze zásadami ochrany aplikací Intune, jako jsou vlastní zařízení uživatelů (BYOD).

Vzhledem k tomu, že zásady ochrany aplikací Intune cílí na identitu uživatele, nastavení ochrany pro uživatele obvykle platí jak pro zaregistrovaná zařízení (ve správě MDM), tak i pro nezaregistrovaná zařízení (bez správy MDM). Z tohoto důvodu můžete zacílit zásady ochrany aplikací Intune jak na zařízení s iOSem nebo Androidem zaregistrovaná v Intune, tak i na nezaregistrovaná zařízení. Pro nespravovaná zařízení můžete zavést jednu zásadu ochrany, která bude používat přísné mechanismy ochrany před únikem informací, a pro zařízení spravovaná v MDM samostatnou zásadu, která bude používat mírnější mechanismy ochrany před únikem informací. 

Pokud chcete vytvořit tyto zásady, přejděte v konzole Intune na **Klientské aplikace** > **Zásady ochrany aplikací** a klikněte na **Přidat zásadu**. Můžete také upravit existující zásadu ochranu aplikací. Pokud chcete, aby zásada ochrany aplikací platila pro spravovaná i nespravovaná zařízení, zkontrolujte, že je možnost **Cílit na všechny typy aplikací** nastavena na výchozí hodnotu **Ano**. Pokud chcete zásady přiřazovat podrobněji na základě stavu správy, nastavte možnost **Cílit na všechny typy aplikací** na **Ne**. 

![Snímek obrazovky s oknem Přidat zásadu a vybranou možností Cílit na všechny typy aplikací](./media/app-protection-policies-target-all.png)

Aby bylo možné považovat aplikace pro iOS za „spravované“, musí být nastavení zásad konfigurace **IntuneMAMUPN** nasazené pro každou aplikaci. Další informaci získáte v článku o [správě přenosu dat mezi aplikacemi pro iOS pomocí Microsoft Intune](https://docs.microsoft.com/intune/data-transfer-between-apps-manage-ios#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).

> [!NOTE]
> Konkrétní informace o podpoře zásad ochrany aplikací pro iOS na základě stavu správy zařízení najdete v tématu [Zásady ochrany MAM zacílené podle stavu správy](whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state-).

## <a name="policy-settings"></a>Nastavení zásad
Pokud chcete zobrazit úplný seznam nastavení zásad pro iOS a Android, vyberte jeden z následujících odkazů:

- [Zásady pro iOS](app-protection-policy-settings-ios.md)
- [Zásady pro Android](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Další kroky
[Monitorování stavu dodržování předpisů a uživatele](app-protection-policies-monitor.md)

### <a name="see-also"></a>Viz taky
* [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](app-protection-enabled-apps-android.md)
* [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](app-protection-enabled-apps-ios.md)
