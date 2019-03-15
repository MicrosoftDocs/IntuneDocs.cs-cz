---
title: Vytvoření a nasazení zásad ochrany aplikací
titleSuffix: Microsoft Intune
description: Toto téma popisuje, jak vytvořit a přiřadit zásady ochrany aplikací Microsoft Intune (aplikace).
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/28/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: db4f218f41dbbbdfbdde5cb32efd561a224222f3
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57400280"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Vytvoření a přiřazení zásad ochrany aplikací

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Podívejte se, jak vytvořit a přiřadit zásady ochrany aplikací Microsoft Intune k uživatelům. Toto téma také popisuje, jak změnit existující zásady.

## <a name="before-you-begin"></a>Před zahájením

Zásady ochrany aplikací lze použít pro aplikace běžící na zařízeních, která může nebo nemusí spravovat Intune. Podrobnější popis, jak fungují zásady ochrany aplikací, a scénáře, které jsou podporované zásadami ochrany aplikací Intune, najdete v tématu [Co jsou zásady ochrany aplikací Microsoft Intune](app-protection-policy.md).

Pokud hledáte seznam aplikací s podporou MAM, přejděte na [seznam aplikací MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Informace o přidání obchodních aplikací organizace do Microsoft Intune kvůli přípravě na zásady ochrany aplikací najdete v tématu [Přidání aplikací do Microsoft Intune](apps-add.md).

##  <a name="create-an-app-protection-policy"></a>Vytvoření zásady ochrany aplikací
1. Na portálu Intune přejděte na **Klientské aplikace** > **Zásady ochrany aplikací**. Po výběru této možnosti se zobrazí detaily **Zásady ochrany aplikací**, kde můžete vytvářet nové zásady a upravovat stávající.
2. Vyberte **Vytvořit zásadu**.

   ![Snímek obrazovky okna Přidat zásadu](./media/app-protection-add-policy.png)

3. Zadejte název zásady, přidejte stručný popis a vyberte pro zásadu typ platformy. Pro každou platformu můžete vytvořit několik zásad.

4. Výběrem možnosti **Aplikace** otevřete okno **Aplikace**, kde se zobrazí seznam dostupných aplikací. Ze seznamu vyberte jednu nebo několik aplikací a přidružte je k zásadě, kterou vytváříte. Při vytváření zásady vyberte alespoň jednu aplikaci.  

5. Jakmile vyberete aplikace, uložte vybrané možnosti volbou **Vybrat**.

6. V okně **Přidat zásadu** vyberte **Konfigurovat požadovaná nastavení**. Otevře se **Nastavení**.

   Existují tři kategorie nastavení zásad:
   - **Ochrana dat** – tato skupina obsahuje ztráty ochrany před únikem informací (DLP) ovládacích prvcích dat, jako je vyjmutí, kopírování a vložení a uložení – jako omezení. Tato nastavení určují, jak uživatelé pracují s daty v aplikacích.
   - **Požadavky na přístup** – tato skupina obsahuje možnosti kódu PIN pro jednotlivé aplikace, které určují, jak koncový uživatel získá přístup k aplikacím v pracovním kontextu.  
   - **Podmíněné spouštění** – tato skupina obsahuje nastavení, jako je minimální verze operačního systému, detekce zařízení s jailbreakem a rootem a období odkladu pro offline režim.

   Nastavením zásad jsou pro začátek přiřazené výchozí hodnoty. Pokud tyto výchozí hodnoty splňují vaše požadavky, nemusíte nic měnit.

   > [!TIP]
   > Tato nastavení zásad se vynutí jenom při použití aplikace v pracovním kontextu. Když koncový uživatel použije aplikaci k provedení osobní úlohy, nebudou mít tyto zásady na ni vliv. Upozorňujeme, že když vytvoříte nový soubor, považuje se za osobní soubor. 

7. Uložte tuto konfiguraci výběrem tlačítka **OK**. A jste zpátky v okně **Přidat zásadu**.
8. Výběrem možnosti **Vytvořit** vytvořte zásadu a uložte nastavení.

Nové zásady, které vytvoříte, se nenasadí žádným uživatelům, dokud to explicitně neuděláte. Pokud chcete nasadit zásadu, přečtěte si téma [Nasazení zásady pro uživatele](app-protection-policies.md#deploy-a-policy-to-users).

## <a name="deploy-a-policy-to-users"></a>Nasazení zásady pro uživatele

1. V podokně **Zásady ochrany aplikací** vyberte zásadu.

2. V podokně ***Intune App Protection** otevřete výběrem možnosti **Přiřazení** podokno **Intune App Protection – Přiřazení**. Na kartě *Zahrnout* zvolte **Vybrat skupiny, které se zahrnou**. 

   ![Snímek obrazovky podokna přiřazení se vybrané skupiny zahrnout nabídky](./media/app-protection-policy-add-users.png)

3.  Zobrazí se seznam všech skupin zabezpečení ve službě **Azure Active Directory**. Vyberte skupiny uživatelů, pro které chcete tuto zásadu použít, a pak zvolte **Vybrat**. 

    ![Snímek obrazovky podokna přidat skupinu uživatelů seznam uživatelů Azure AD](./media/azure-ad-user-group-list.png)

4.  Po zahrnutí a vyloučení skupin, vyberte **Uložit** uložte konfiguraci a nasazení zásad pro uživatele. Pokud vyberete **zahodit** před uložením konfiguraci se zahodí všechny změny, které jste udělali *zahrnout* a *vyloučit* karty.   
 
     ![Snímek obrazovky ukazující, ukládání a zahodit možnosti](./media/save-assignment.png)
  
Teď je zásada vytvořená a nasazená u uživatelů.

Tyto zásady ovlivní jenom uživatele, kteří mají přiřazené licence Microsoft Intune. Nemají vliv na uživatele ve vybrané skupině zabezpečení, kteří nemají přiřazenou licenci pro Intune.

>[!IMPORTANT]
> Pokud ke správě zařízení používáte Intune s Configuration Managerem, použijí se zásady jenom pro uživatele přímo ve skupinách, které jste vybrali. Na členy podřízených skupin vnořených ve skupině, kterou jste vybrali, tyto zásady nemají vliv.

Koncoví uživatelé můžou stahovat aplikace z App Storu nebo Google Play. Další informace naleznete v tématu:
* [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](app-protection-enabled-apps-android.md)
* [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a>Změna existujících zásad
Podle potřeby můžete upravit existující zásady a použít je pro cílové uživatele. Když ale změníte existující zásady, neprojeví se tyto změny po dobu osmi hodin uživatelům, kteří se už přihlásili k aplikacím.

Aby se změny projevily hned, musí se koncový uživatel odhlásit od aplikace a pak se k ní zase přihlásit.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Změna seznamu aplikací přidružených k zásadě

1.  V podokně **Zásady ochrany aplikací** vyberte zásadu, kterou chcete změnit.

2.  V podokně *Intune App Protection* otevřete výběrem možnosti **Cílové aplikace** seznam aplikací.

3.  V tomto seznamu odeberte nebo přidejte aplikace a výběrem ikony **Uložit** uložte provedené změny.

### <a name="to-change-the-list-of-user-groups"></a>Změna seznamu skupin uživatelů


1.  V podokně **Zásady ochrany aplikací** vyberte zásadu, kterou chcete změnit.

2.  V podokně *Intune App Protection* otevřete výběrem možnosti **Přiřazení** podokno **Intune App Protection – Přiřazení** se seznamem aktuálních skupin uživatelů, kteří mají tuto zásadu.

3.  Pokud chcete přidat k zásadě novou skupinu uživatelů, zvolte na kartě *Zahrnout* možnost **Vybrat skupiny, které se zahrnou** a vyberte skupinu uživatelů. Zvolte **vyberte** přidejte skupinu. 

4.  Vyloučit skupiny uživatelů, na *vyloučit* zvolte kartu **výběr skupin k vyloučení**a vyberte skupinu uživatelů. Skupinu uživatelů odeberte pomocí možnosti **Vybrat**.  

5.  Odstranění skupiny, které byly dříve přidány na buď *zahrnout* nebo *vyloučit* karty, vyberte tři tečky (...) a vyberte **odstranit**. 

5.  Po dokončení změn přiřazení připraveni, vyberte **Uložit** uložte konfiguraci a nasazení zásad pro novou skupinu uživatelů. Pokud vyberete **zahodit** před uložením konfiguraci se zahodí všechny změny, které jste udělali *zahrnout* a *vyloučit* karty.

### <a name="to-change-policy-settings"></a>Změna nastavení zásad

1.  V podokně **Zásady ochrany aplikací** zvolte zásadu, kterou chcete změnit.

2.  V podokně *Intune App Protection* otevřete výběrem možnosti **Vlastnosti** seznam oblastí upravitelných nastavení. 

3.  Vyberte oblast s nastaveními, která chcete změnit, například **Přemístění dat** nebo **Požadavky na přístup**. Pak tato nastavení změňte na nové hodnoty.

4.  Výběrem ikony **Uložit** uložte provedené změny. Opakováním tohoto postupu vyberte jinou oblast nastavení, udělejte změny a pak je uložte, dokud nebudou všechny změny hotové. Pak můžete podokno *Intune App Protection – Vlastnosti* zavřít. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Cílení zásad ochrany aplikací na základě stavu správy zařízení
Mnoho organizací běžně umožňuje koncovým uživatelům používat jak zařízení spravovaná přes Intune MDM (Mobile Device Management), například zařízení ve vlastnictví společnosti, tak i nespravovaná zařízení chráněná pouze zásadami ochrany aplikací Intune. Nespravovaná zařízení se často označují jako BYOD (Bring Your Own Devices).

Protože zásady ochrany aplikací Intune cílí na identitu uživatele, mohou nastavení ochrany pro uživatele platit jak pro zaregistrovaná zařízení (ve správě MDM), tak pro nezaregistrovaná zařízení (bez správy MDM). Zásady ochrany aplikací Intune proto můžete zacílit na zařízení s iOSem nebo Androidem zaregistrovaná i nezaregistrovaná v Intune. Pro nespravovaná zařízení můžete zavést jednu zásadu ochrany, která bude používat přísné mechanismy ochrany před únikem informací, a pro zařízení spravovaná v MDM samostatnou zásadu, která bude používat mírnější mechanismy ochrany před únikem informací. 

Tyto zásady vytvoříte tak, že v konzole Intune přejdete na **Klientské aplikace** > **Zásady ochrany aplikací** a kliknete na **Přidat zásadu**. Můžete také upravit existující zásadu ochranu aplikací. Aby zásada ochrany aplikací platila pro spravovaná i nespravovaná zařízení, zkontrolujte, že je možnost **Cílit na všechny typy aplikací** nastavena na výchozí hodnotu **Ano**. Pokud chcete zásady přiřazovat podrobněji na základě stavu správy, nastavte možnost **Cílit na všechny typy aplikací** na **Ne**. 

![Snímek obrazovky okna zásady přidat pomocí cílit na všechny typy aplikací](./media/app-protection-policies-target-all.png)

U iOSu jsou nutná další nastavení konfigurace aplikace, která mají cílit nastavení APP na aplikace na zařízeních zaregistrovaných v Intune:
- **IntuneMAMUPN** musí být nakonfigurované pro všechny aplikace spravované pomocí správy mobilních zařízení (MDM). Další informaci získáte v článku o [správě přenosu dat mezi aplikacemi pro iOS pomocí Microsoft Intune](https://docs.microsoft.com/intune/data-transfer-between-apps-manage-ios#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).
- **IntuneMAMDeviceID** musí být nakonfigurované pro všechny aplikace třetích stran a obchodní aplikace pod správou mobilních zařízení. **IntuneMAMDeviceID** by mělo být nakonfigurované na token ID zařízení. Například, `key=IntuneMAMDeviceID, value={{deviceID}}`. Další informace najdete v tématu [Přidání zásad konfigurace aplikací pro spravovaná zařízení s iOSem](https://docs.microsoft.com/intune/app-configuration-policies-use-ios).
- Pokud je nakonfigurované jenom **IntuneMAMDeviceID**, Intune APP bude zařízení považovat za nespravované.  

> [!NOTE]
> Konkrétní informace o podpoře zásad ochrany aplikací pro iOS na základě stavu správy zařízení najdete v tématu [Zásady ochrany MAM zacílené podle stavu správy](whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state-).

## <a name="policy-settings"></a>Nastavení zásad
Pokud chcete zobrazit úplný seznam nastavení zásad pro iOS a Android, vyberte jeden z následujících odkazů:

- [Zásady pro iOS](app-protection-policy-settings-ios.md)
- [Zásady pro Android](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Další postup
[Monitorování stavu dodržování předpisů a uživatele](app-protection-policies-monitor.md)

### <a name="see-also"></a>Viz také:
* [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](app-protection-enabled-apps-android.md)
* [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](app-protection-enabled-apps-ios.md)
