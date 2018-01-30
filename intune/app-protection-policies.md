---
title: "Vytvoření a nasazení zásad ochrany aplikací"
titleSuffix: Azure portal
description: "Přečtěte si, jak mohou zásady ochrany aplikací pomoci při ochraně firemních dat, která používají vámi spravované aplikace."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4fbb9a1f6697a8339a2854e4352749ca04bb612e
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Vytvoření a přiřazení zásad ochrany aplikací

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="before-you-begin"></a>Před zahájením

Pokud hledáte pokyny na klasickém portálu Intune, přečtěte si, [jak vytvořit zásady ochrany aplikací](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).

Zásady ochrany aplikací je možné použít pro aplikace běžící na zařízeních, která může nebo nemusí spravovat Intune. Podrobnější popis, jak fungují zásady ochrany aplikací, a scénáře podporované zásadami ochrany aplikací Intune najdete v tématu [Co jsou zásady ochrany aplikací Microsoft Intune](app-protection-policy.md).

Pokud hledáte seznam aplikací s podporou MAM, přejděte na [seznam aplikací MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

##  <a name="create-an-app-protection-policy"></a>Vytvoření zásady ochrany aplikací
1.  V úloze **Mobilní aplikace** zvolte **Spravovat** > **Zásady ochrany aplikací**.

2.  Otevře se okno **Zásady ochrany aplikací**, kde můžete vytvářet nové zásady a upravovat zásady, které už existují. Zvolte **Přidat zásadu**.

  ![Snímek obrazovky okna Přidat zásadu](./media/app-protection-add-policy.png)

3.  Zadejte název zásady, přidejte stručný popis a vyberte, jestli se má zásada vytvořit pro platformu iOS nebo Android. Pro každou platformu můžete vytvořit několik zásad.

4.  Zvolením možnosti **Aplikace** otevřete **okno Aplikace**, kde se zobrazí seznam dostupných aplikací. Ze seznamu vyberte jednu nebo několik aplikací a přidružte je k zásadě, kterou vytváříte. Jakmile vyberete aplikace, uložte svůj výběr zvolením **Vybrat** v dolní části okna **Aplikace**.

    > [!IMPORTANT]
    > Při vytváření zásady musíte vybrat aspoň jednu aplikaci.

5.  V **okně Přidat zásadu** zvolte **Konfigurovat požadované nastavení**. Otevře se okno nastavení zásad.

    Existují dvě kategorie nastavení zásad, **Přemístění dat** a **Přístup**.  Zásady přemístění dat platí pro přesun dat do aplikace a z aplikace, zatímco zásady přístupu určují, jak koncový uživatel přistupuje k aplikaci v pracovním kontextu.
    Nastavením zásad jsou pro začátek přiřazené výchozí hodnoty. Pokud tyto výchozí hodnoty splňují vaše požadavky, nemusíte nic měnit.

    > [!TIP]
    > Tato nastavení zásad se vynutí jenom při použití aplikace v pracovním kontextu.  Když uživatel použije aplikaci k provedení osobní úlohy, tyto zásady ho neovlivní.



6.  Tuto konfiguraci uložíte zvolením tlačítka **OK**. A jste zpátky v okně **Přidat zásadu**. Zvolením možnosti **Vytvořit** vytvoříte zásadu a uložíte své nastavení.


Zásada není po vytvoření pomocí výš uvedeného postupu nasazená pro žádného uživatele. Pokud chcete nasadit zásadu, přečtěte si následující část „Nasazení zásady pro uživatele“.

## <a name="deploy-a-policy-to-users"></a>Nasazení zásady pro uživatele

1.  V okně **Zásada** zvolte **Skupiny uživatelů**. Otevře se okno **Skupiny uživatelů**. Zvolením možnosti **Přidat skupinu uživatelů** v okně **Skupiny uživatelů** otevřete okno **Přidat skupinu uživatelů**.

  ![Snímek obrazovky okna Skupiny uživatelů se zvýrazněnou možností nabídky Přidat skupinu uživatelů](./media/app-protection-policy-add-users.png)

2.  V okně **Přidat skupinu uživatelů** se zobrazí seznam skupin uživatelů. Je to seznam všech skupin zabezpečení v **Azure Active Directory**. Vyberte skupiny uživatelů, pro které chcete tuto zásadu použít, a pak zvolte **Vybrat**. Zvolením možnosti **Vybrat** nasadíte tuto zásadu uživatelům.
  ![Snímek obrazovky okna Přidat skupinu uživatelů zobrazující seznam uživatelů Azure Active Directory](./media/azure-ad-user-group-list.png)

Teď je zásada vytvořená a nasazená uživatelům.

Tyto zásady ovlivní jenom uživatele, kteří mají přiřazené licence Microsoft Intune. Na uživatele ve vybrané skupině zabezpečení, kteří nemají přiřazenou licenci Microsoft Intune, nebudou mít tyto zásady vliv.

>[!IMPORTANT]
> Pokud ke správě zařízení s iOSem a Androidem používáte Intune s Configuration Managerem, zásady se použijí jenom pro uživatele přímo ve skupinách, které jste vybrali. Členy podřízených skupin vnořených ve skupině, kterou jste vybrali, tyto zásady neovlivní.

Koncoví uživatelé můžou stahovat aplikace z App Storu nebo Google Play. Více informací najdete v následujících tématech:
* [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](app-protection-enabled-apps-android.md)
* [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a>Změna existujících zásad
Podle potřeby můžete upravit existující zásady a použít je pro cílové uživatele. Když ale změníte existující zásady, změny se uživatelům, kteří se už přihlásili k aplikacím, po dobu 8 hodin nezobrazí.

Pokud koncový uživatel chce, aby se změny zásady projevily hned, musí se odhlásit od aplikace a pak se k ní zase přihlásit.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Změna seznamu aplikací přidružených k zásadě

1.  V okně **Zásady aplikací** zvolte zásadu, kterou chcete změnit. Otevře se speciální okno pro právě vybranou zásadu.

2.  V okně zásady zvolte **Cílené aplikace**. Otevře se seznam aplikací.

3.  V seznamu odeberte nebo přidejte aplikace a zvolením ikony **Uložit** uložte změny, které jste provedli.

### <a name="to-change-the-list-of-user-groups"></a>Změna seznamu skupin uživatelů

1.  V okně **Zásady aplikací** zvolte zásadu, kterou chcete změnit. Otevře se speciální okno pro právě vybranou zásadu.

2.  V okně zásady zvolte **Skupiny uživatelů**. Otevře se okno **Skupiny uživatelů**, ve kterém se zobrazí seznam aktuálních skupin uživatelů s touto zásadou.

3.  Pokud chcete k zásadě přidat novou skupinu uživatelů, zvolte **Přidat skupinu uživatelů** a vyberte skupinu uživatelů. Zvolením možnosti **Vybrat** nasadíte zásadu do skupiny uživatelů, kterou jste vybrali.

4.  Pokud chcete skupinu uživatelů odstranit, zvýrazněte skupinu uživatelů, kterou chcete odebrat. Pak vyberte tři tečky (...) a zvolením **Odstranit** skupinu uživatelů odeberte.
  ![Snímek obrazovky s možností Odstranit](./media/app-protection-policy-delete-user.png)

### <a name="to-change-policy-settings"></a>Změna nastavení zásad

1.  V okně **Zásady aplikací** klikněte na zásadu, kterou chcete změnit. Otevře se speciální okno pro právě vybranou zásadu.


2.  Zvolením možnosti **Nastavení zásad** otevřete okno **Nastavení zásad**.

3.  Změňte nastavení a pak změny uložte zvolením ikony **Uložit**.

## <a name="policy-settings"></a>Nastavení zásad
Pokud chcete zobrazit úplný seznam nastavení zásad pro iOS a Android, vyberte jednu z následujících možností:

- [Zásady pro iOS](app-protection-policy-settings-ios.md)
- [Zásady pro Android](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Další kroky
[Monitorování stavu dodržování předpisů a uživatele](app-protection-policies-monitor.md)

### <a name="see-also"></a>Viz taky
* [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](app-protection-enabled-apps-android.md)
* [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](app-protection-enabled-apps-ios.md)
