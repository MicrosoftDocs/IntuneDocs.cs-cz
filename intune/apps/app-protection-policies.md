---
title: Vytvoření a nasazení zásad ochrany aplikací
titleSuffix: Microsoft Intune
description: Toto téma popisuje, jak vytvořit a přiřadit Microsoft Intune zásady ochrany aplikací (aplikace).
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4958a35f3a83fecffacf26421e4c1d797f45ddaa
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940380"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Jak vytvořit a přiřadit zásady ochrany aplikací

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Naučte se vytvářet a přiřazovat Microsoft Intune zásady ochrany aplikací pro uživatele. V tomto tématu se také dozvíte, jak provádět změny stávajících zásad.

## <a name="before-you-begin"></a>Než začnete

Zásady ochrany aplikací se můžou vztahovat na aplikace běžící na zařízeních, která se můžou nebo nemusí spravovat přes Intune. Podrobnější popis toho, jak zásady ochrany aplikací fungují, a scénáře podporované zásadami ochrany aplikací Intune najdete v tématu [co jsou Microsoft Intune zásady ochrany aplikací?](app-protection-policy.md)

Pokud hledáte seznam podporovaných aplikací MAM, přečtěte si téma [seznam aplikací mam](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Informace o přidání obchodních aplikací (LOB) do vaší organizace pro Microsoft Intune Příprava na zásady ochrany aplikací najdete v tématu [Přidání aplikací do Microsoft Intune](apps-add.md).

## <a name="create-an-app-protection-policy"></a>Vytvoření zásady ochrany aplikací
1. V portálu Intune, přejít na **klientské aplikace** > **Zásady ochrany aplikací**. Tento výběr otevře podrobnosti **zásad ochrany aplikací** , kde můžete vytvářet nové zásady a upravovat stávající zásady.
2. Vyberte **vytvořit zásadu**.

   ![Snímek obrazovky okna Přidat zásadu](./media/app-protection-policies/app-protection-add-policy.png)

3. Zadejte název zásady, přidejte stručný popis a vyberte typ platformy pro zásady. Pro každou platformu můžete vytvořit více než jednu zásadu.

4. Výběrem **aplikace** otevřete okno **aplikace** , kde se zobrazí seznam dostupných aplikací. V seznamu vyberte jednu nebo více aplikací, které chcete přidružit k zásadě, kterou vytváříte. Pokud chcete vytvořit zásadu, vyberte aspoň jednu aplikaci.  

5. Po výběru aplikací zvolte **Vybrat** a uložte svůj výběr.

6. V okně **Přidat zásadu** vyberte **Konfigurovat požadované nastavení** . otevře se **Nastavení**.

   Existují tři kategorie nastavení zásad:
   - **Ochrana dat** – Tato skupina obsahuje ovládací prvky ochrany před únikem informací (DLP), jako jsou omezení pro vyjmutí, kopírování, vložení a uložení. Tato nastavení určují, jak uživatelé pracují s daty v aplikacích.
   - **Požadavky na přístup** – Tato skupina obsahuje možnosti PIN kódu pro aplikaci, které určují, jak koncový uživatel přistupuje k aplikacím v pracovním kontextu.  
   - **Podmíněné spuštění** – Tato skupina obsahuje nastavení, jako jsou minimální nastavení operačního systému, jailbreaků a detekce root zařízení a offline období odkladu.

   Pokud chcete začít, nastavení zásad má výchozí hodnoty. Pokud výchozí hodnoty splňují vaše požadavky, nemusíte provádět žádné změny.

   > [!TIP]
   > Tato nastavení zásad se vynutila jenom při používání aplikací v pracovním kontextu. Když koncoví uživatelé používají aplikaci k provedení osobní úlohy, tyto zásady na ně neovlivňují. Všimněte si, že když vytvoříte nový soubor, považuje se za osobní soubor. 

7. Tuto konfiguraci uložíte kliknutím na **OK** . Nyní jste zpátky v okně **Přidat zásadu** .
8. Výběrem možnosti **vytvořit** vytvořte zásadu a uložte nastavení.

Nové zásady, které vytvoříte, nebudou nasazeny pro žádné uživatele, dokud to neuděláte explicitně. Pokud chcete nasadit zásadu, přečtěte si téma [nasazení zásady pro uživatele](app-protection-policies.md#deploy-a-policy-to-users).

## <a name="deploy-a-policy-to-users"></a>Nasazení zásady pro uživatele

1. V podokně **Zásady ochrany aplikací** vyberte zásadu.

2. V podokně ***Intune App Protection** vyberte **přiřazení** a otevřete tak podokno **Intune App Protection-přiřazení** . Na kartě *Zahrnout* vyberte **Vybrat skupiny, které chcete zahrnout**. 

   ![Snímek obrazovky podokna přiřazení se nabídkami vybrat skupiny, které se mají zahrnout](./media/app-protection-policies/app-protection-policy-add-users.png)

3. Zobrazí se seznam všech skupin zabezpečení v **Azure Active Directory** . Vyberte skupiny uživatelů, pro které chcete tuto zásadu použít, a pak zvolte **Vybrat**. 

    ![Snímek obrazovky s podoknem přidat skupinu uživatelů se seznamem uživatelů Azure AD](./media/app-protection-policies/azure-ad-user-group-list.png)

4. Po zahrnutí a vyloučení skupin vyberte **Uložit** a uložte konfiguraci a Nasaďte zásadu pro uživatele. Pokud vyberete možnost **Zrušit** před uložením konfigurace, zahodí se všechny změny, které jste provedli na kartách *zahrnutí* a *vyloučení* .   
 
     ![Snímek obrazovky s možnostmi Uložit a zahodit](./media/app-protection-policies/save-assignment.png)
  
Nyní jste vytvořili zásadu a nasadili ji pro uživatele.

Zásady ovlivní jenom uživatele, kteří mají přiřazené licence Microsoft Intune. Nebudou ovlivněni uživatelé ve vybrané skupině zabezpečení, kteří nemají přiřazenou licenci Intune.

>[!IMPORTANT]
> Pokud ke správě zařízení používáte Intune s Configuration Manager, zásada se aplikuje jenom na uživatele přímo ve skupině, kterou jste vybrali. Členy podřízených skupin vnořených ve skupině, kterou jste vybrali, nejsou ovlivněny.

Koncoví uživatelé si můžou aplikace stáhnout z App Storu nebo Google Play. Další informace naleznete v tématu:
* [Co očekávat, když je vaše aplikace pro Android spravovaná pomocí zásad ochrany aplikací](../fundamentals/end-user-mam-apps-android.md)
* [Co očekávat, když je vaše aplikace pro iOS spravovaná zásadami ochrany aplikací](../fundamentals/end-user-mam-apps-ios.md)

## <a name="change-existing-policies"></a>Změna existujících zásad
Existující zásadu můžete upravit a použít ji pro cílové uživatele. Když ale změníte existující zásady, uživatelé, kteří se už přihlásili k aplikacím, neuvidí změny po dobu osmi hodin.

Aby se změny projevily hned, musí se koncový uživatel z aplikace odhlásit a pak se znovu přihlásit.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Změna seznamu aplikací přidružených k zásadě

1. V podokně **Zásady ochrany aplikací** vyberte zásadu, kterou chcete změnit.

2. V podokně *Intune App Protection* vyberte **cílené aplikace** . otevře se seznam aplikací.

3. V seznamu odeberte nebo přidejte aplikace a kliknutím na ikonu **Uložit** uložte změny.

### <a name="to-change-the-list-of-user-groups"></a>Změna seznamu skupin uživatelů


1. V podokně **Zásady ochrany aplikací** vyberte zásadu, kterou chcete změnit.

2. V podokně *Intune App Protection* vyberte **přiřazení** a otevřete tak podokno **Intune App Protection – přiřazení** , které zobrazuje seznam aktuálních skupin uživatelů s touto zásadou.

3. Pokud chcete do zásady Přidat novou skupinu uživatelů, zvolte na kartě *Zahrnout* **možnost vybrat skupiny, které se zahrnou**a vyberte skupinu uživatelů. Zvolte **možnost vybrat** a přidejte skupinu. 

4. Pokud chcete vyloučit skupinu uživatelů, zvolte na kartě *vyloučit* **možnost vybrat skupiny, které se mají vyloučit**a vyberte skupinu uživatelů. Chcete-li odebrat skupinu uživatelů, zvolte **možnost vybrat** .  

5. Pokud chcete odstranit skupiny, které jste dříve přidali, vyberte na kartách *Zahrnout* nebo *vyloučit* tři tečky (...) a vyberte **Odstranit**. 

5. Až budou změny v přiřazení připravené, vyberte **Uložit** a uložte konfiguraci a Nasaďte zásadu na novou skupinu uživatelů. Pokud vyberete možnost **Zrušit** před uložením konfigurace, zahodí se všechny změny, které jste provedli na kartách *zahrnutí* a *vyloučení* .

### <a name="to-change-policy-settings"></a>Změna nastavení zásad

1. V podokně **Zásady ochrany aplikací** vyberte zásadu, kterou chcete změnit.

2. V podokně *Intune App Protection* vyberte **vlastnosti** a otevřete tak seznam oblastí nastavení, které můžete upravovat. 

3. Vyberte oblast nastavení s nastavením, které chcete změnit, jako je třeba **přemístění dat** nebo **požadavky na přístup**. Pak změňte nastavení na nové hodnoty.

4. Kliknutím na ikonu **Uložit** uložte změny. Opakujte postup pro výběr oblasti nastavení a upravte a uložte změny, dokud nebudou všechny změny dokončeny. Pak můžete zavřít podokno *Intune App Protection-Properties (vlastnosti* ). 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Cílení zásad ochrany aplikací na základě stavu správy zařízení
V mnoha organizacích je běžné, že koncovým uživatelům umožníte používat zařízení spravovaná přes správu mobilních zařízení (MDM) Intune, jako jsou zařízení vlastněná podnikem, a nespravovaná zařízení chráněná jenom pomocí zásad ochrany aplikací Intune. Nespravovaná zařízení se často označují jako Přineste si vlastní zařízení (BYOD).

Vzhledem k tomu, že zásady ochrany aplikací Intune cílí na identitu uživatele, nastavení ochrany pro uživatele se může vztahovat na zaregistrovaná zařízení (spravovaná přes MDM) i na nezaregistrovaná zařízení (bez MDM). Proto můžete cílit na zásady ochrany aplikací Intune buď na zaregistrovaná zařízení s iOS nebo Androidem v Intune. Můžete mít jednu zásadu ochrany pro nespravovaná zařízení, ve kterých jsou zavedené ovládací prvky ochrany před únikem informací (DLP), a samostatné zásady ochrany pro zařízení spravovaná pomocí MDM, kde můžou být ovládací prvky ochrany před únikem informací trochu uvolněné. Další informace o tom, jak funguje na osobních zařízeních s Androidem Enteprise, najdete v tématu [Zásady ochrany aplikací a pracovní profily](android-deployment-scenarios-app-protection-work-profiles.md).

Pokud chcete vytvořit tyto zásady, přejděte do části **klientské aplikace** > **Zásady ochrany aplikací** v konzole Intune a pak vyberte **vytvořit zásadu**. Můžete také upravit existující zásady ochrany aplikací. Aby se zásady ochrany aplikací projevily na spravovaných i nespravovaných zařízeních, potvrďte, že **cíl pro všechny typy aplikací** je nastavený na **Ano**, což je výchozí hodnota. Pokud chcete podrobně přiřazovat základ pro stav správy, nastavte **cíl na všechny typy aplikací** na **ne**. 

![Snímek obrazovky okna Přidat zásadu s cílem pro všechny typy aplikací](./media/app-protection-policies/app-protection-policies-target-all.png)

### <a name="app-types"></a>Typy aplikací

- **Aplikace na nespravovaných zařízeních**: nespravovaná zařízení jsou zařízení, ve kterých se nezjistila Správa služby Intune MDM. Patří sem dodavatelé MDM třetích stran.
- **Aplikace na zařízeních spravovaných pomocí Intune**: spravovaná zařízení se spravují přes Intune MDM.
- **Aplikace v pracovním profilu Android**: spravovaná zařízení, která byla zaregistrovaná jako zařízení s Androidem Enterprise Work Profile.

> Poznámka: zařízení s Androidem se zobrazí výzva k instalaci aplikace Portál společnosti Intune bez ohledu na to, který typ aplikace je vybraný. Pokud například vyberete aplikace na zařízeních spravovaných pomocí Intune, zobrazí se jim i uživatelé s nespravovanými zařízeními s Androidem.

Pro iOS se pro nastavení zásad ochrany aplikací na zařízeních zaregistrovaných v Intune vyžaduje další nastavení konfigurace aplikace:

- **IntuneMAMUPN** musí být nakonfigurovaný pro všechny aplikace spravované MDM. Další informace najdete v tématu [Správa přenosu dat mezi aplikacemi pro iOS v Microsoft Intune](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).
- **IntuneMAMDeviceID** musí být nakonfigurovaná pro všechny aplikace třetích stran a LOB pro správu MDM. **IntuneMAMDeviceID** by měla být nakonfigurovaná na token ID zařízení. Například `key=IntuneMAMDeviceID, value={{deviceID}}`. Další informace najdete v tématu [Přidání zásad konfigurace aplikací pro spravovaná zařízení s iOS](app-configuration-policies-use-ios.md).
- Pokud je nakonfigurovaná jenom **IntuneMAMDeviceID** , aplikace Intune bude zařízení považovat za nespravované.

> [!NOTE]
> Konkrétní informace o podpoře pro iOS týkající se zásad ochrany aplikací na základě stavu správy zařízení najdete v tématu [Zásady ochrany mam cílené na základě stavu správy](../fundamentals/whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state-).

## <a name="policy-settings"></a>Nastavení zásad
Pokud chcete zobrazit úplný seznam nastavení zásad pro iOS a Android, vyberte jeden z následujících odkazů:

- [zásady pro iOS](app-protection-policy-settings-ios.md)
- [Zásady pro Android](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Další kroky
[Monitorování dodržování předpisů a stavu uživatele](app-protection-policies-monitor.md)

## <a name="see-also"></a>Viz také:
* [Co očekávat, když je vaše aplikace pro Android spravovaná pomocí zásad ochrany aplikací](../fundamentals/end-user-mam-apps-android.md)
* [Co očekávat, když je vaše aplikace pro iOS spravovaná zásadami ochrany aplikací](../fundamentals/end-user-mam-apps-ios.md)
