---
title: "Vytvoření a nasazení zásad MAM | Dokumentace Microsoftu"
description: "Podle podrobného postupu v tomto tématu můžete vytvořit a nasadit zásady správy mobilních aplikací."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1b9a343-1737-4a65-a9c6-aca48acad11c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: fbb41a8cf6fada76b72213b8cb04fdc0428515e9
ms.openlocfilehash: f4bc5a2092585c91e224c390eaae717985055b10


---

# <a name="create-and-deploy-app-protection-policies-with-microsoft-intune"></a>Vytvoření a nasazení zásad ochrany aplikací pomocí Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Toto téma popisuje proces vytváření zásad ochrany aplikací na **portálu Azure Portal**. Portál Azure Portal je nová konzola pro správu, která slouží k vytváření zásad ochrany aplikací, a doporučujeme tento portál při vytváření zásad ochrany aplikací používat. Portál Azure Portal podporuje následující scénáře MAM:

- Zařízení zaregistrovaná v Intune
- Zařízení spravovaná řešením MDM třetí strany
- Zařízení, která nejsou spravována žádným řešením MDM (BYOD).

>[!IMPORTANT]
Pokud při správě zařízení používáte **konzolu pro správu Intune**, zvažte toto:

> * Pomocí [konzoly pro správu Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) můžete vytvořit zásadu ochrany aplikací podporující aplikace pro zařízení zaregistrovaná v Intune.
> * Zásady ochrany aplikací vytvořené v konzole pro správu Intune se nedají importovat do portálu Azure Portal.  Zásady ochrany aplikací je potřeba znovu vytvořit na portálu Azure Portal.

> * V konzole pro správu Intune se nemusí zobrazovat všechna nastavení zásad ochrany aplikací. Azure Portal je nová konzola pro správu, kterou je možné používat k vytváření zásad ochrany aplikací.

> * Pro nasazení spravovaných aplikací musíte vytvořit zásady ochrany aplikací pomocí konzoly pro správu Intune. V takovém případě můžete chtít vytvořit zásady ochrany aplikací v konzole pro správu Intune i na portálu Azure Portal. V konzole proto, abyste si zajistili možnost nasazení spravovaných aplikací, a na portálu Azure Portal proto, že je to nová konzola pro správu obsahující všechna nastavení zásad ochrany aplikací.

> * Pokud vytvoříte zásady ochrany aplikací v konzole pro správu Intune i na portálu Azure Portal, pro aplikace se použije zásada z portálu Azure Portal.

Pokud chcete zobrazit seznam nastavení zásad, která jsou podporována pro platformy Android a iOS, vyberte jednu z následujících možností:

> [!div class="op_single_selector"]
- [Zásady pro iOS](ios-mam-policy-settings.md)
- [Zásady pro Android](android-mam-policy-settings.md)

- Podrobnější popis toho, jak zásady ochrany aplikací fungují, a scénáře podporované zásadami ochrany aplikací Intune najdete v tématu o [ochraně dat aplikací pomocí zásady ochrany aplikací](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

##  <a name="create-an-app-protection-policy"></a>Vytvoření zásady ochrany aplikací
Zásady ochrany aplikací se vytvářejí na portálu Azure Portal. Pokud portál Azure Portal používáte poprvé, přečtěte si článek [Portál Azure Portal pro zásady ochrany aplikací v Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md) a seznamte se s portálem Azure Portal důkladněji. Před vytvořením zásady ochrany aplikací si projděte informace o [požadavcích a podpoře](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).

Při vytváření zásad ochrany aplikací postupujte takto:

1. Přejděte na portál [Azure Portal](http://portal.azure.com) a zadejte přihlašovací údaje.

2. Zvolte **Další služby** a zadejte „Intune“.

3. Zvolte **Ochrana aplikací Intune**.

4. Zvolte **Správa mobilních aplikací Intune &gt; Nastavení** a otevřete tak okno **Všechna nastavení**.

    ![Snímek obrazovky okna Správa mobilních aplikací Intune](../media/AppManagement/AzurePortal_MAM_Mainblade-2.png)

2.  V okně **Všechna nastavení** zvolte **Zásady aplikací**. Otevře se okno **Zásady aplikací**, kde můžete vytvářet nové zásady a upravovat zásady, které už existují. Zvolte **Přidat zásadu**.

    ![Snímek obrazovky okna Přidat zásadu se zvýrazněnou možností nabídky Přidat zásadu ](../media/AppManagement/AzurePortal_MAM_AddPolicy.png)

3.  Zadejte název zásady, přidejte stručný popis a vyberte, jestli se má zásada vytvořit pro platformu iOS nebo Android. Pro každou platformu můžete vytvořit několik zásad.

    ![Snímek obrazovky okna Přidat zásadu](../media/AppManagement/AzurePortal_MAM_AddPolicy_only.png)

4.  Zvolením možnosti **Aplikace** otevřete **okno Aplikace**, kde se zobrazí seznam dostupných aplikací. Ze seznamu vyberte jednu nebo několik aplikací a přidružte je k zásadě, kterou vytváříte. Jakmile vyberete aplikace, uložte svůj výběr zvolením **Vybrat** v dolní části okna **Aplikace**.

    > [!IMPORTANT]
    > Při vytváření zásady musíte vybrat aspoň jednu aplikaci.

5.  V **okně Přidat zásadu** zvolte **Konfigurovat požadované nastavení**. Otevře se okno nastavení zásad.

    Existují dvě kategorie nastavení zásad, **Přemístění dat** a **Přístup**.  Zásady přemístění dat platí pro přesun dat do aplikace a z aplikace, zatímco zásady přístupu určují, jak koncový uživatel přistupuje k aplikaci v pracovním kontextu.
    Nastavením zásad jsou pro začátek přiřazené výchozí hodnoty. Pokud tyto výchozí hodnoty splňují vaše požadavky, nemusíte nic měnit.

    > [!TIP]
    > Tato nastavení zásad se vynutí jenom při použití aplikace v pracovním kontextu.  Když uživatel použije aplikaci k provedení osobní úlohy, tyto zásady ho neovlivní.

    ![Snímek obrazovky okna nastavení společně s oknem Přidat zásadu](../media/AppManagement/AzurePortal_MAM_PolicySettings.png)

6.  Tuto konfiguraci uložíte zvolením tlačítka **OK**. A jste zpátky v okně **Přidat zásadu**. Zvolením možnosti **Vytvořit** vytvoříte zásadu a uložíte své nastavení.

    ![Snímek obrazovky okna Přidat zásadu znázorňující, že byly nakonfigurovány aplikace a nastavení](../media/AppManagement/AzurePortal_MAM_CreatePolicy.png)



Zásada není po vytvoření pomocí výš uvedeného postupu nasazená pro žádného uživatele. Pokud chcete nasadit zásadu, přečtěte si následující část „Nasazení zásady pro uživatele“.

> [!IMPORTANT]
> Pokud jste zásadu ochrany aplikací vytvořili pomocí konzoly pro správu Intune i pomocí portálu Azure Portal, dostane přednost zásada vytvořená na portálu Azure Portal. Při generování sestav v konzole Configuration Manageru nebo Intune se ale použijí nastavení zásad vytvořená v konzole pro správu Intune. Například:
>
> -   V konzole pro správu Intune jste vytvořili zásadu ochrany aplikací, která blokuje kopírování z aplikace.
> -   V konzole Azure jste vytvořili zásadu ochrany aplikací, která umožňuje kopírování z aplikace.
> -   Obě tyto zásady jste přidružili ke stejné aplikaci.
> -   Zásada vytvořená pomocí v konzole Azure bude mít přednost a kopírování bude povolené.
> -   Stav a sestavy v konzole Intune budou ale nesprávně indikovat, že kopírování je blokované.

## <a name="deploy-a-policy-to-users"></a>Nasazení zásady pro uživatele

1.  V okně **Zásada** zvolte **Skupiny uživatelů**. Otevře se okno **Skupiny uživatelů**. Zvolením možnosti **Přidat skupinu uživatelů** v okně **Skupiny uživatelů** otevřete okno **Přidat skupinu uživatelů**.

    ![Snímek obrazovky okna Skupiny uživatelů se zvýrazněnou možností nabídky Přidat skupinu uživatelů](../media/AppManagement/AzurePortal_MAM_AddUserstoPolicy.png)

2.  V okně **Přidat skupinu uživatelů** se zobrazí seznam skupin uživatelů. Je to seznam všech skupin zabezpečení v **Azure Active Directory**. Vyberte skupiny uživatelů, pro které chcete tuto zásadu použít, a pak zvolte **Vybrat**. Zvolením možnosti **Vybrat** nasadíte tuto zásadu uživatelům.

    ![Snímek obrazovky okna Přidat skupinu uživatelů zobrazující seznam uživatelů Azure Active Directory](../media/AppManagement/AzurePortal_MAM_SelectUserstoDeploy.png)

    Teď je zásada vytvořená a nasazená uživatelům.

Tyto zásady ovlivní jenom uživatele, kteří mají přiřazené licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Uživatele, kteří jsou ve skupinách zabezpečení, které jste vybrali, a kteří nemají přiřazenou licenci [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], tyto zásady neovlivní.

>[!IMPORTANT]
> Pokud ke správě zařízení s iOSem a Androidem používáte Intune s Configuration Managerem, zásady se použijí jenom pro uživatele přímo ve skupinách, které jste vybrali. Členy podřízených skupin vnořených ve skupině, kterou jste vybrali, tyto zásady neovlivní.

Koncoví uživatelé můžou stahovat aplikace z App Storu nebo Google Play. Více informací najdete v následujících tématech:
* [Co očekávat, když ke správě své aplikace pro Android používáte zásady ochrany aplikací](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Co očekávat, když ke správě své aplikace pro iOS používáte zásady ochrany aplikací](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

##  <a name="change-existing-policies"></a>Změna existujících zásad
Podle potřeby můžete upravit existující zásady a použít je pro cílové uživatele. Když ale změníte existující zásady, změny se uživatelům, kteří se už přihlásili k aplikacím, po dobu 8 hodin nezobrazí.

Pokud koncový uživatel chce, aby se změny zásady projevily hned, musí se odhlásit od aplikace a pak se k ní zase přihlásit.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Změna seznamu aplikací přidružených k zásadě

1.  V okně **Zásady aplikací** zvolte zásadu, kterou chcete změnit. Otevře se speciální okno pro právě vybranou zásadu.

    ![Snímek obrazovky existující zásady otevřené v samostatném okně](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  V okně zásady zvolte **Cílové aplikace**. Otevře se seznam aplikací.

3.  V seznamu odeberte nebo přidejte aplikace a zvolením ikony **Uložit** uložte změny, které jste provedli.

### <a name="to-change-the-list-of-user-groups"></a>Změna seznamu skupin uživatelů

1.  V okně **Zásady aplikací** zvolte zásadu, kterou chcete změnit. Otevře se speciální okno pro právě vybranou zásadu.

2.  V okně zásady zvolte **Skupiny uživatelů**. Otevře se okno **Skupiny uživatelů**, ve kterém se zobrazí seznam aktuálních skupin uživatelů s touto zásadou.

3.  Pokud chcete k zásadě přidat novou skupinu uživatelů, zvolte **Přidat skupinu uživatelů** a vyberte skupinu uživatelů. Zvolením možnosti **Vybrat** nasadíte zásadu do skupiny uživatelů, kterou jste vybrali.

    ![Snímek obrazovky okna Přidat skupinu uživatelů se dvěma vybranými skupinami uživatelů](../media/AppManagement/AzurePortal_MAM_ChangePolicy_SelectUser.png)

4.  Pokud chcete skupinu uživatelů odstranit, zvýrazněte skupinu uživatelů, kterou chcete odebrat. Pak vyberte tři tečky (...) a zvolením **Odstranit** skupinu uživatelů odeberte.

    ![Snímek obrazovky s možností Odstranit ](../media/AppManagement/AzurePortal_MAM_ChangePolicy_DeleteUser.png)

### <a name="to-change-policy-settings"></a>Změna nastavení zásad

1.  V okně **Zásady aplikací** klikněte na zásadu, kterou chcete změnit. Otevře se speciální okno pro právě vybranou zásadu.

    ![Snímek obrazovky existující zásady otevřené v samostatném okně ](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  Zvolením možnosti **Nastavení zásad** otevřete okno **Nastavení zásad**.

3.  Změňte nastavení a pak změny uložte zvolením ikony **Uložit**.

    ![Snímek obrazovky okna Nastavení zásad znázorňující nahoře možnost Uložit](../media/AppManagement/AzurePortal_MAM_ChangePolicy_ChangeSettings.png)

## <a name="policy-settings"></a>Nastavení zásad
Pokud chcete zobrazit úplný seznam nastavení zásad pro iOS a Android, vyberte jednu z následujících možností:

> [!div class="op_single_selector"]
- [Zásady pro iOS](ios-mam-policy-settings.md)
- [Zásady pro Android](android-mam-policy-settings.md)

## <a name="next-steps"></a>Další kroky
[Monitorování stavu dodržování předpisů a uživatele](monitor-mobile-app-management-policies-with-microsoft-intune.md)

### <a name="see-also"></a>Související témata
* [Co očekávat, když ke správě své aplikace pro Android používáte zásady ochrany aplikací](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Co očekávat, když ke správě své aplikace pro iOS používáte zásady ochrany aplikací](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Feb17_HO2-->


