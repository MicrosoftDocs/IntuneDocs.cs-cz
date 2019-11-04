---
title: Vytvoření a nasazení zásad ochrany aplikací
titleSuffix: Microsoft Intune
description: Toto téma popisuje, jak vytvořit a přiřadit Microsoft Intune zásady ochrany aplikací (aplikace).
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0c9fdd5e34f87c2dd02b886f97fa86c4823a318f
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414718"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Vytvoření a přiřazení zásad ochrany aplikací

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Naučte se vytvářet a přiřazovat Microsoft Intune zásady ochrany aplikací (APP) pro uživatele vaší organizace. Toto téma také popisuje, jak změnit existující zásady.

## <a name="before-you-begin"></a>Před zahájením

Zásady ochrany aplikací lze použít pro aplikace běžící na zařízeních, která může nebo nemusí spravovat Intune. Podrobnější popis, jak fungují zásady ochrany aplikací, a scénáře, které jsou podporované zásadami ochrany aplikací Intune, najdete v tématu [Co jsou zásady ochrany aplikací Microsoft Intune](app-protection-policy.md).

Pokud hledáte seznam aplikací s podporou MAM, přejděte na [seznam aplikací MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Informace o přidání obchodních aplikací organizace do Microsoft Intune kvůli přípravě na zásady ochrany aplikací najdete v tématu [Přidání aplikací do Microsoft Intune](apps-add.md).

V současné době se tok procesu vytváření zásad ochrany aplikací liší v závislosti na platformě:
- Zásady ochrany aplikací pro iOS/iPadOS a aplikace pro Android
- Zásady ochrany aplikací pro aplikace pro Windows 10

## <a name="app-protection-policies-for-iosipados-and-android-apps"></a>Zásady ochrany aplikací pro iOS/iPadOS a aplikace pro Android

Když vytvoříte zásady ochrany aplikací pro iOS/iPadOS a aplikace pro Android, budete postupovat podle moderního toku procesu Intune, který má za následek novou zásadu ochrany aplikací.

### <a name="create-an-iosipados-or-android-app-protection-policy"></a>Vytvoření zásad ochrany aplikací pro iOS/iPadOS nebo Android
1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. V portálu Intune vyberte **klientské aplikace**  > **Zásady ochrany aplikací**. Po výběru této možnosti se zobrazí detaily **Zásady ochrany aplikací**, kde můžete vytvářet nové zásady a upravovat stávající.
3. Vyberte **vytvořit zásadu** a vyberte možnost **iOS/iPadOS** nebo **Android**. Zobrazí se okno **vytvořit zásadu** .
4. Na stránce **základy** přidejte následující hodnoty:

    | Hodnota | Description |
    |--------------|------------------------------------------------|
    | Název | Název této zásady ochrany aplikací |
    | Description | Volitelné Popis této zásady ochrany aplikací |


    Hodnota **platformy** je nastavená na základě výše zvolené možnosti.

    ![Snímek obrazovky se stránkou základy v okně vytvořit zásadu](~/apps/media/app-protection-policies/app-protection-add-policies-01.png)

5. Kliknutím na **Další** zobrazte stránku **aplikace** .<br>
    Stránka **aplikace** umožňuje zvolit, jak chcete tyto zásady použít pro aplikace na různých zařízeních. Musíte přidat alespoň jednu aplikaci.<p>
    
    | Hodnota/možnost | Description |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Cíl pro aplikace na všech typech zařízení | Tuto možnost použijte, pokud chcete zásady zaměřit na aplikace na zařízeních libovolného stavu správy. Pokud chcete cílit aplikace na konkrétní typy zařízení, vyberte **ne** . |
    |     Typy zařízení | Tuto možnost použijte, pokud chcete určit, jestli se tato zásada vztahuje na zařízení spravovaná MDM nebo na nespravovaná zařízení. V případě zásad aplikací pro iOS vyberte možnost z **nespravovaných** a **spravovaných** zařízení. V případě zásad aplikací pro Android vyberte z **nespravovaného**, **Správce zařízení s Androidem**a **Android Enterprise**.  |
    | Veřejné aplikace | Klikněte na **Vybrat veřejné aplikace** a vyberte aplikace, které se mají cílit. |
    | Vlastní aplikace | Klikněte na **Vybrat vlastní aplikace** a vyberte vlastní aplikace, které chcete cílit na základě ID sady prostředků. |
    
    Vybrané aplikace se zobrazí v seznamu veřejné a vlastní aplikace. 
6. Kliknutím na **Další** zobrazte stránku **Ochrana dat** .<br>
    Tato stránka poskytuje nastavení pro řízení ochrany před únikem informací (DLP), včetně omezení pro vyjmutí, kopírování, vložení a uložení. Tato nastavení určují, jak uživatelé pracují s daty v aplikacích, které tato zásada ochrany aplikací používá.

    **Nastavení ochrany dat**:<br>
    - **iOS/iPadOS data Protection** – informace najdete v tématu [nastavení zásad ochrany aplikací pro iOS – ochrana dat](~/apps/app-protection-policy-settings-ios.md#data-protection).
    - **Ochrana dat v Androidu** – informace najdete v tématu [nastavení zásad ochrany aplikací pro Android – ochrana dat](~/apps/app-protection-policy-settings-android.md#data-protection).

7. Kliknutím na **Další** zobrazte stránku **požadavky na přístup** .<br>
    Tato stránka poskytuje nastavení, která umožňují nakonfigurovat požadavky na kód PIN a přihlašovací údaje, které uživatelé musí splnit, aby měli přístup k aplikacím v pracovním kontextu. 
 
    **Nastavení požadavků na přístup**:<br>
    - **požadavky na přístup k iOS/iPadOS** – informace najdete v tématu [nastavení zásad ochrany aplikací pro iOS – požadavky na přístup](~/apps/app-protection-policy-settings-ios.md#access-requirements).
    - **Požadavky na přístup k Androidu** – informace najdete v tématu [nastavení zásad ochrany aplikací pro Android – požadavky na přístup](~/apps/app-protection-policy-settings-android.md#access-requirements).

8. Kliknutím na **Další** zobrazte **podmíněný spouštěcí** stránku.<br>
    Tato stránka poskytuje nastavení pro nastavení požadavků na zabezpečení přihlášení pro zásady ochrany aplikací. Vyberte **Nastavení** a do sloupce **Hodnota** zadejte hodnotu, kterou uživatelé musí splnit, aby se přihlásili k firemní aplikaci. Pak vyberte **akci** , kterou chcete provést, pokud uživatelé nesplňují vaše požadavky. V některých případech lze pro jedno nastavení nakonfigurovat více akcí.

    **Nastavení podmíněného spuštění**:<br>
    - **podmíněné spuštění iOS/iPadOS** – informace najdete v tématu [nastavení zásad ochrany aplikací pro iOS – podmíněné spuštění](~/apps/app-protection-policy-settings-ios.md#conditional-launch).
    - **Podmíněné spuštění Androidu** – informace najdete v tématu [nastavení zásad ochrany aplikací pro Android – podmíněné spuštění](~/apps/app-protection-policy-settings-android.md#conditional-launch).

7. Kliknutím na tlačítko **Další** zobrazíte stránku **přiřazení** .<br>
   Na stránce **přiřazení** můžete nastavit zásady ochrany aplikací pro skupiny uživatelů. 
8. Klikněte na **Další: zkontrolovat + vytvořit** a zkontrolujte hodnoty a nastavení, které jste zadali pro tyto zásady ochrany aplikací.
9. Až skončíte, klikněte na **vytvořit** a vytvořte zásadu ochrany aplikací v Intune. 

## <a name="app-protection-policies-for-windows-10-apps"></a>Zásady ochrany aplikací pro aplikace pro Windows 10

Když vytvoříte zásady ochrany aplikací pro aplikace pro Windows 10, budete mít klasický průběh procesu Intune.

### <a name="create-a-windows-10-app-protection-policy"></a>Vytvoření zásad ochrany aplikací pro Windows 10
1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. V portálu Intune vyberte **klientské aplikace**  > **Zásady ochrany aplikací**. Po výběru této možnosti se zobrazí detaily **Zásady ochrany aplikací**, kde můžete vytvářet nové zásady a upravovat stávající.
3. Vyberte **vytvořit zásadu**.

    <img alt="Screenshot of the 'Create policy' blade for Windows 10" src="~/apps/media/app-protection-policies/app-protection-add-policy.png" width="350">

4. Zadejte název zásady, přidejte stručný popis a vyberte pro zásadu typ platformy. Pro každou platformu můžete vytvořit několik zásad.

4. Můžete se rozhodnout, že budete **cílit na všechny typy aplikací**. Tato možnost umožňuje zaměřit vaši zásadu na aplikace na zařízeních libovolného stavu správy. Během řešení konfliktů zásad bude toto nastavení nahrazeno, pokud má uživatel zásadu zaměřenou na určitý stav správy. Podrobnosti najdete v tématu [Cílení zásad ochrany aplikací na základě stavu správy zařízení](~/apps/app-protection-policies.md#target-app-protection-policies-based-on-device-management-state).

5. Výběrem možnosti **Aplikace** otevřete okno **Aplikace**, kde se zobrazí seznam dostupných aplikací. Ze seznamu vyberte jednu nebo několik aplikací a přidružte je k zásadě, kterou vytváříte. Při vytváření zásady vyberte alespoň jednu aplikaci.  

6. Jakmile vyberete aplikace, uložte vybrané možnosti volbou **Vybrat**.

7. V okně **Přidat zásadu** vyberte **Konfigurovat požadovaná nastavení**. Otevře se **Nastavení**.

   Existují tři kategorie nastavení zásad:
   - **Ochrana dat** – Tato skupina obsahuje ovládací prvky ochrany před únikem informací (DLP), jako jsou omezení pro vyjmutí, kopírování, vložení a uložení. Tato nastavení určují, jak uživatelé pracují s daty v aplikacích.
   - **Požadavky na přístup** – tato skupina obsahuje možnosti kódu PIN pro jednotlivé aplikace, které určují, jak koncový uživatel získá přístup k aplikacím v pracovním kontextu.  
   - **Podmíněné spouštění** – tato skupina obsahuje nastavení, jako je minimální verze operačního systému, detekce zařízení s jailbreakem a rootem a období odkladu pro offline režim.

   Nastavením zásad jsou pro začátek přiřazené výchozí hodnoty. Pokud tyto výchozí hodnoty splňují vaše požadavky, nemusíte nic měnit.

   > [!TIP]
   > Tato nastavení zásad se vynutí jenom při použití aplikace v pracovním kontextu. Když koncový uživatel použije aplikaci k provedení osobní úlohy, nebudou mít tyto zásady na ni vliv. Upozorňujeme, že když vytvoříte nový soubor, považuje se za osobní soubor. 

8. Uložte tuto konfiguraci výběrem tlačítka **OK**. A jste zpátky v okně **Přidat zásadu**.
9. Výběrem možnosti **Vytvořit** vytvořte zásadu a uložte nastavení.

Nové zásady Windows 10, které vytvoříte, nejsou přiřazené k žádným uživatelům, dokud to neuděláte explicitně. Postup přiřazení zásady pro Windows 10 najdete v tématu [přiřazení zásad pro Windows 10 uživatelům](~/apps/app-protection-policies.md#assign-a-windows-10-policy-to-users) .

### <a name="assign-a-windows-10-policy-to-users"></a>Přiřazení zásady pro Windows 10 uživatelům 

1. V podokně **Zásady ochrany aplikací** vyberte zásadu.

2. V podokně ***Intune App Protection** otevřete výběrem možnosti **Přiřazení** podokno **Intune App Protection – Přiřazení**. Na kartě *Zahrnout* zvolte **Vybrat skupiny, které se zahrnou**. 

   ![Snímek obrazovky podokna přiřazení se nabídkami vybrat skupiny, které se mají zahrnout](./media/app-protection-policies/app-protection-policy-add-users.png)

3. Zobrazí se seznam všech skupin zabezpečení ve službě **Azure Active Directory**. Vyberte skupiny uživatelů, pro které chcete tuto zásadu použít, a pak zvolte **Vybrat**. 

    ![Snímek obrazovky s podoknem přidat skupinu uživatelů se seznamem uživatelů Azure AD](./media/app-protection-policies/azure-ad-user-group-list.png)

4. Po zahrnutí a vyloučení skupin vyberte **Uložit** a uložte konfiguraci a Nasaďte zásadu pro uživatele. Pokud vyberete možnost **Zrušit** před uložením konfigurace, zahodí se všechny změny, které jste provedli na kartách *zahrnutí* a *vyloučení* .   
 
     ![Snímek obrazovky s možnostmi Uložit a zahodit](./media/app-protection-policies/save-assignment.png)
  
Teď je zásada vytvořená a nasazená u uživatelů.

Tyto zásady ovlivní jenom uživatele, kteří mají přiřazené licence Microsoft Intune. Nemají vliv na uživatele ve vybrané skupině zabezpečení, kteří nemají přiřazenou licenci pro Intune.

>[!IMPORTANT]
> Pokud ke správě zařízení používáte Intune s Configuration Managerem, použijí se zásady jenom pro uživatele přímo ve skupinách, které jste vybrali. Na členy podřízených skupin vnořených ve skupině, kterou jste vybrali, tyto zásady nemají vliv.

Koncoví uživatelé můžou stahovat aplikace z App Storu nebo Google Play. Více informací najdete v následujících tématech:
* [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](../fundamentals/end-user-mam-apps-android.md)
* [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](../fundamentals/end-user-mam-apps-ios.md)

### <a name="change-existing-windows-10-policies"></a>Změna stávajících zásad pro Windows 10
Podle potřeby můžete upravit existující zásady a použít je pro cílové uživatele. Když ale změníte existující zásady, neprojeví se tyto změny po dobu osmi hodin uživatelům, kteří se už přihlásili k aplikacím.

Aby se změny projevily hned, musí se koncový uživatel odhlásit od aplikace a pak se k ní zase přihlásit.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Změna seznamu aplikací přidružených k zásadě

1. V podokně **Zásady ochrany aplikací** vyberte zásadu, kterou chcete změnit.

2. V podokně *Intune App Protection* otevřete výběrem možnosti **Cílové aplikace** seznam aplikací.

3. V tomto seznamu odeberte nebo přidejte aplikace a výběrem ikony **Uložit** uložte provedené změny.

#### <a name="to-change-the-list-of-user-groups"></a>Změna seznamu skupin uživatelů

1. V podokně **Zásady ochrany aplikací** vyberte zásadu, kterou chcete změnit.

2. V podokně *Intune App Protection* otevřete výběrem možnosti **Přiřazení** podokno **Intune App Protection – Přiřazení** se seznamem aktuálních skupin uživatelů, kteří mají tuto zásadu.

3. Pokud chcete přidat k zásadě novou skupinu uživatelů, zvolte na kartě *Zahrnout* možnost **Vybrat skupiny, které se zahrnou** a vyberte skupinu uživatelů. Zvolte **možnost vybrat** a přidejte skupinu. 

4. Pokud chcete vyloučit skupinu uživatelů, zvolte na kartě *vyloučit* **možnost vybrat skupiny, které se mají vyloučit**a vyberte skupinu uživatelů. Skupinu uživatelů odeberte pomocí možnosti **Vybrat**.  

5. Pokud chcete odstranit skupiny, které jste dříve přidali, vyberte na kartách *Zahrnout* nebo *vyloučit* tři tečky (...) a vyberte **Odstranit**. 

5. Až budou změny v přiřazení připravené, vyberte **Uložit** a uložte konfiguraci a Nasaďte zásadu na novou skupinu uživatelů. Pokud vyberete možnost **Zrušit** před uložením konfigurace, zahodí se všechny změny, které jste provedli na kartách *zahrnutí* a *vyloučení* .

### <a name="to-change-windows-10-policy-settings"></a>Změna nastavení zásad pro Windows 10

1. V podokně **Zásady ochrany aplikací** zvolte zásadu, kterou chcete změnit.

2. V podokně *Intune App Protection* otevřete výběrem možnosti **Vlastnosti** seznam oblastí upravitelných nastavení. 

3. Vyberte oblast s nastaveními, která chcete změnit, například **Přemístění dat** nebo **Požadavky na přístup**. Pak tato nastavení změňte na nové hodnoty.

4. Výběrem ikony **Uložit** uložte provedené změny. Opakováním tohoto postupu vyberte jinou oblast nastavení, udělejte změny a pak je uložte, dokud nebudou všechny změny hotové. Pak můžete podokno *Intune App Protection – Vlastnosti* zavřít. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Cílení zásad ochrany aplikací na základě stavu správy zařízení
Mnoho organizací běžně umožňuje koncovým uživatelům používat jak zařízení spravovaná přes Intune MDM (Mobile Device Management), například zařízení ve vlastnictví společnosti, tak i nespravovaná zařízení chráněná pouze zásadami ochrany aplikací Intune. Nespravovaná zařízení se často označují jako BYOD (Bring Your Own Devices).

Protože zásady ochrany aplikací Intune cílí na identitu uživatele, mohou nastavení ochrany pro uživatele platit jak pro zaregistrovaná zařízení (ve správě MDM), tak pro nezaregistrovaná zařízení (bez správy MDM). Zásady ochrany aplikací Intune proto můžete zacílit na zařízení s iOSem nebo Androidem zaregistrovaná i nezaregistrovaná v Intune. Můžete mít jednu zásadu ochrany pro nespravovaná zařízení, ve kterých jsou zavedené ovládací prvky ochrany před únikem informací (DLP), a samostatné zásady ochrany pro zařízení spravovaná pomocí MDM, kde můžou být ovládací prvky ochrany před únikem informací trochu uvolněné. Další informace o tom, jak funguje na osobních zařízeních s Androidem Enterprise, najdete v tématu [Zásady ochrany aplikací a pracovní profily](android-deployment-scenarios-app-protection-work-profiles.md).

Tyto zásady vytvoříte tak, že v konzole Intune přejdete na **Klientské aplikace** > **Zásady ochrany aplikací** a kliknete na **Přidat zásadu**. Můžete také upravit existující zásadu ochranu aplikací. Pokud chcete, aby se zásady ochrany aplikací nastavily u spravovaných i nespravovaných zařízení, přejděte na stránku **aplikace** a ověřte, že **cíl pro aplikace na všech typech zařízení** je nastavená na **Ano**, což je výchozí hodnota. Pokud chcete členit přiřazení na základě stavu správy, nastavte **cíl pro aplikace na všech typech zařízení** na **ne**. 

![Snímek obrazovky okna Přidat zásadu s cílem pro všechny typy aplikací](./media/app-protection-policies/app-protection-policies-target-all.png)

### <a name="app-types"></a>Typy aplikací

- **Aplikace na nespravovaných zařízeních**: nespravovaná zařízení jsou zařízení, ve kterých se nezjistila Správa služby Intune MDM. Patří sem dodavatelé MDM třetích stran.
- **Aplikace na zařízeních spravovaných pomocí Intune**: spravovaná zařízení se spravují přes Intune MDM.
- **Aplikace v pracovním profilu Android**: spravovaná zařízení, která byla zaregistrovaná jako zařízení s Androidem Enterprise Work Profile.

> Poznámka: zařízení s Androidem se zobrazí výzva k instalaci aplikace Portál společnosti Intune bez ohledu na to, který typ aplikace je vybraný. Pokud například vyberete aplikace na zařízeních spravovaných pomocí Intune, zobrazí se jim i uživatelé s nespravovanými zařízeními s Androidem.

Pro iOS se pro nastavení zásad ochrany aplikací na zařízeních zaregistrovaných v Intune vyžaduje další nastavení konfigurace aplikace:

- **IntuneMAMUPN** musí být nakonfigurované pro všechny aplikace spravované pomocí správy mobilních zařízení (MDM). Další informaci získáte v článku o [správě přenosu dat mezi aplikacemi pro iOS pomocí Microsoft Intune](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).
- **IntuneMAMDeviceID** musí být nakonfigurované pro všechny aplikace třetích stran a obchodní aplikace pod správou mobilních zařízení. **IntuneMAMDeviceID** by mělo být nakonfigurované na token ID zařízení. Například `key=IntuneMAMDeviceID, value={{deviceID}}`. Další informace najdete v tématu [Přidání zásad konfigurace aplikací pro spravovaná zařízení s iOSem](app-configuration-policies-use-ios.md).
- Pokud je nakonfigurované jenom **IntuneMAMDeviceID**, Intune APP bude zařízení považovat za nespravované.

> [!NOTE]
> Konkrétní informace o podpoře zásad ochrany aplikací pro iOS na základě stavu správy zařízení najdete v tématu [Zásady ochrany MAM zacílené podle stavu správy](../fundamentals/whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state).

## <a name="policy-settings"></a>Nastavení zásad
Pokud chcete zobrazit úplný seznam nastavení zásad pro iOS a Android, vyberte jeden z následujících odkazů:

- [Zásady pro iOS](app-protection-policy-settings-ios.md)
- [Zásady pro Android](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Další kroky
[Monitorování stavu dodržování předpisů a uživatele](app-protection-policies-monitor.md)

## <a name="see-also"></a>Související témata
* [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](../fundamentals/end-user-mam-apps-android.md)
* [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](../fundamentals/end-user-mam-apps-ios.md)
