---
title: Vytvoření a nasazení zásad ochrany aplikací
titleSuffix: Microsoft Intune
description: Toto téma popisuje, jak vytvořit a přiřadit Microsoft Intune zásady ochrany aplikací (aplikace).
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
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
ms.openlocfilehash: 9b5f973e5ce169edcf6149b0588c905d8497cca2
ms.sourcegitcommit: 2506cdbfccefd42587a76f14ee50c3849dad1708
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/11/2020
ms.locfileid: "75885747"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Vytvoření a přiřazení zásad ochrany aplikací

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Naučte se vytvářet a přiřazovat Microsoft Intune zásady ochrany aplikací (APP) pro uživatele vaší organizace. Toto téma také popisuje, jak změnit existující zásady.

## <a name="before-you-begin"></a>Před zahájením

Zásady ochrany aplikací lze použít pro aplikace běžící na zařízeních, která může nebo nemusí spravovat Intune. Podrobnější popis, jak fungují zásady ochrany aplikací, a scénáře, které jsou podporované zásadami ochrany aplikací Intune, najdete v tématu [Co jsou zásady ochrany aplikací Microsoft Intune](app-protection-policy.md).

Pokud hledáte seznam aplikací s podporou MAM, přejděte na [seznam aplikací MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Informace o přidání obchodních aplikací organizace do Microsoft Intune kvůli přípravě na zásady ochrany aplikací najdete v tématu [Přidání aplikací do Microsoft Intune](apps-add.md).

## <a name="app-protection-policies-for-iosipados-and-android-apps"></a>Zásady ochrany aplikací pro iOS/iPadOS a aplikace pro Android

Když vytvoříte zásady ochrany aplikací pro iOS/iPadOS a aplikace pro Android, budete postupovat podle moderního toku procesu Intune, který má za následek novou zásadu ochrany aplikací.

### <a name="create-an-iosipados-or-android-app-protection-policy"></a>Vytvoření zásad ochrany aplikací pro iOS/iPadOS nebo Android
1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. V portálu Intune vyberte **aplikace** > **Zásady ochrany aplikací**. Po výběru této možnosti se zobrazí detaily **Zásady ochrany aplikací**, kde můžete vytvářet nové zásady a upravovat stávající.
3. Vyberte **vytvořit zásadu** a vyberte možnost **iOS/iPadOS** nebo **Android**. Zobrazí se podokno **vytvořit zásadu** .
4. Na stránce **základy** přidejte následující hodnoty:

    | Hodnota | Description |
    |--------------|------------------------------------------------|
    | Název | Název této zásady ochrany aplikací |
    | Description | Volitelné Popis této zásady ochrany aplikací |


    Hodnota **platformy** je nastavená na základě výše zvolené možnosti.

    ![Snímek stránky základy v podokně vytvořit zásadu](~/apps/media/app-protection-policies/app-protection-add-policies-01.png)

5. Kliknutím na **Další** zobrazte stránku **aplikace** .<br>
    Stránka **aplikace** umožňuje zvolit, jak chcete tyto zásady použít pro aplikace na různých zařízeních. Musíte přidat alespoň jednu aplikaci.<p>
    
    | Hodnota/možnost | Description |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Cíl pro aplikace na všech typech zařízení | Tuto možnost použijte, pokud chcete zásady zaměřit na aplikace na zařízeních libovolného stavu správy. Pokud chcete cílit aplikace na konkrétní typy zařízení, vyberte **ne** . Informace najdete v tématu [cílení zásad ochrany aplikací na základě stavu správy zařízení](#target-app-protection-policies-based-on-device-management-state) . |
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

9. Kliknutím na tlačítko **Další** zobrazíte stránku **přiřazení** .<br>
   Stránka **přiřazení** vám umožní přiřadit zásady ochrany aplikací skupinám uživatelů.

10. Klikněte na **Další: zkontrolovat + vytvořit** a zkontrolujte hodnoty a nastavení, které jste zadali pro tyto zásady ochrany aplikací.

11. Až skončíte, klikněte na **vytvořit** a vytvořte zásadu ochrany aplikací v Intune. 

    > [!TIP]
    > Tato nastavení zásad se vynutí jenom při použití aplikace v pracovním kontextu. Když koncový uživatel použije aplikaci k provedení osobní úlohy, nebudou mít tyto zásady na ni vliv. Upozorňujeme, že když vytvoříte nový soubor, považuje se za osobní soubor. 

Koncoví uživatelé můžou stahovat aplikace z App Storu nebo Google Play. Více informací najdete v následujících tématech:
* [Co očekávat, když ke správě svojí aplikace pro Android používáte zásady ochrany aplikací](../fundamentals/end-user-mam-apps-android.md)
* [Co očekávat, když ke správě aplikace pro iOS používáte zásady ochrany aplikací](../fundamentals/end-user-mam-apps-ios.md)

## <a name="change-existing-policies"></a>Změna existujících zásad
Podle potřeby můžete upravit existující zásady a použít je pro cílové uživatele. Když ale změníte existující zásady, neprojeví se tyto změny po dobu osmi hodin uživatelům, kteří se už přihlásili k aplikacím.

Aby se změny projevily hned, musí se koncový uživatel odhlásit od aplikace a pak se k ní zase přihlásit.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Změna seznamu aplikací přidružených k zásadě

1. V podokně **Zásady ochrany aplikací** vyberte zásadu, kterou chcete změnit.

2. V podokně *Intune App Protection* vyberte možnost **vlastnosti**.

3. Vedle části s názvem *aplikace*vyberte **Upravit**.

4. Stránka **aplikace** umožňuje zvolit, jak chcete tyto zásady použít pro aplikace na různých zařízeních. Musíte přidat alespoň jednu aplikaci.<p>
    
    | Hodnota/možnost | Description |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Cíl pro aplikace na všech typech zařízení | Tuto možnost použijte, pokud chcete zásady zaměřit na aplikace na zařízeních libovolného stavu správy. Pokud chcete cílit aplikace na konkrétní typy zařízení, vyberte **ne** . Informace najdete v tématu [cílení zásad ochrany aplikací na základě stavu správy zařízení](#target-app-protection-policies-based-on-device-management-state) . |
    |     Typy zařízení | Tuto možnost použijte, pokud chcete určit, jestli se tato zásada vztahuje na zařízení spravovaná MDM nebo na nespravovaná zařízení. V případě zásad aplikací pro iOS vyberte možnost z **nespravovaných** a **spravovaných** zařízení. V případě zásad aplikací pro Android vyberte z **nespravovaného**, **Správce zařízení s Androidem**a **Android Enterprise**.  |
    | Veřejné aplikace | Klikněte na **Vybrat veřejné aplikace** a vyberte aplikace, které se mají cílit. |
    | Vlastní aplikace | Klikněte na **Vybrat vlastní aplikace** a vyberte vlastní aplikace, které chcete cílit na základě ID sady prostředků. |

    Vybrané aplikace se zobrazí v seznamu veřejné a vlastní aplikace. 

5. Klikněte na tlačítko **zkontrolovat + vytvořit** a zkontrolujte aplikace vybrané pro tuto zásadu.

6. Až skončíte, klikněte na **Uložit** a aktualizujte Zásady ochrany aplikací.
 
#### <a name="to-change-the-list-of-user-groups"></a>Změna seznamu skupin uživatelů

1. V podokně **Zásady ochrany aplikací** vyberte zásadu, kterou chcete změnit.

2. V podokně *Intune App Protection* vyberte možnost **vlastnosti**.

3. Vedle části s názvem *přiřazení*vyberte **Upravit**.

4. Pokud chcete přidat k zásadě novou skupinu uživatelů, zvolte na kartě *Zahrnout* možnost **Vybrat skupiny, které se zahrnou** a vyberte skupinu uživatelů. Zvolte **možnost vybrat** a přidejte skupinu. 

5. Pokud chcete vyloučit skupinu uživatelů, zvolte na kartě *vyloučit* **možnost vybrat skupiny, které se mají vyloučit**a vyberte skupinu uživatelů. Skupinu uživatelů odeberte pomocí možnosti **Vybrat**.  

6. Pokud chcete odstranit skupiny, které jste dříve přidali, vyberte na kartách *Zahrnout* nebo *vyloučit* tři tečky (...) a vyberte **Odstranit**.

7. Kliknutím na tlačítko **zkontrolovat + vytvořit** zkontrolujte skupiny uživatelů vybrané pro tuto zásadu.

8. Až budou změny v přiřazení připravené, vyberte **Uložit** a uložte konfiguraci a Nasaďte zásadu na novou skupinu uživatelů. Pokud vyberete **Zrušit** před uložením konfigurace, zahodí se všechny změny, které jste udělali na kartách *zahrnutí* a *vyloučení* .

### <a name="to-change-policy-settings"></a>Změna nastavení zásad

1. V podokně **Zásady ochrany aplikací** vyberte zásadu, kterou chcete změnit.

2. V podokně *Intune App Protection* vyberte možnost **vlastnosti**.

3. Vedle oddílu, který odpovídá nastavení, které chcete změnit, vyberte **Upravit**. Pak tato nastavení změňte na nové hodnoty.

7. Kliknutím na tlačítko **zkontrolovat + vytvořit** zkontrolujte aktualizované nastavení pro tuto zásadu.

4. Kliknutím na **Uložit** uložte změny. Opakováním tohoto postupu vyberte jinou oblast nastavení, udělejte změny a pak je uložte, dokud nebudou všechny změny hotové. Pak můžete podokno *Intune App Protection – Vlastnosti* zavřít. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Cílení zásad ochrany aplikací na základě stavu správy zařízení
Mnoho organizací běžně umožňuje koncovým uživatelům používat jak zařízení spravovaná přes Intune MDM (Mobile Device Management), například zařízení ve vlastnictví společnosti, tak i nespravovaná zařízení chráněná pouze zásadami ochrany aplikací Intune. Nespravovaná zařízení se často označují jako BYOD (Bring Your Own Devices).

Protože zásady ochrany aplikací Intune cílí na identitu uživatele, mohou nastavení ochrany pro uživatele platit jak pro zaregistrovaná zařízení (ve správě MDM), tak pro nezaregistrovaná zařízení (bez správy MDM). Zásady ochrany aplikací Intune proto můžete zacílit na zařízení s iOSem nebo Androidem zaregistrovaná i nezaregistrovaná v Intune. Můžete mít jednu zásadu ochrany pro nespravovaná zařízení, ve kterých jsou zavedené ovládací prvky ochrany před únikem informací (DLP), a samostatné zásady ochrany pro zařízení spravovaná pomocí MDM, kde můžou být ovládací prvky ochrany před únikem informací trochu uvolněné. Další informace o tom, jak funguje na osobních zařízeních s Androidem Enterprise, najdete v tématu [Zásady ochrany aplikací a pracovní profily](android-deployment-scenarios-app-protection-work-profiles.md).

Pokud chcete vytvořit tyto zásady, přejděte do části **aplikace** > **Zásady ochrany aplikací** v konzole Intune a pak vyberte **vytvořit zásadu**. Můžete také upravit existující zásadu ochranu aplikací. Pokud chcete, aby se zásady ochrany aplikací nastavily u spravovaných i nespravovaných zařízení, přejděte na stránku **aplikace** a ověřte, že **cíl pro aplikace na všech typech zařízení** je nastavená na **Ano**, což je výchozí hodnota. Pokud chcete členit přiřazení na základě stavu správy, nastavte **cíl pro aplikace na všech typech zařízení** na **ne**. 

### <a name="device-types"></a>Typy zařízení

- **Nespravované**: nespravovaná zařízení jsou zařízení, ve kterých se nezjistila Správa služby Intune MDM. Patří sem zařízení, která spravuje dodavatel MDM třetích stran.
- **Zařízení spravovaná pomocí Intune**: spravovaná zařízení se spravují přes Intune MDM.
- **Správce zařízení s Androidem**: zařízení spravovaná přes Intune, která používají rozhraní API pro správu zařízení s Androidem.
- **Android Enterprise**: zařízení spravovaná pomocí Intune s využitím podnikových profilů Androidu nebo úplné správy zařízení s Androidem Enterprise.

> [!NOTE]
> Zařízení s Androidem se zobrazí výzva k instalaci aplikace Portál společnosti Intune bez ohledu na to, který typ zařízení je zvolený. Pokud například vyberete možnost Android Enterprise, budou se stále zobrazovat uživatelé s nespravovanými zařízeními s Androidem.

Pro iOS se pro nastavení zásad ochrany aplikací na zařízeních zaregistrovaných v Intune vyžaduje další nastavení konfigurace aplikace:

- **IntuneMAMUPN** musí být nakonfigurované pro všechny aplikace spravované pomocí správy mobilních zařízení (MDM). Další informaci získáte v článku o [správě přenosu dat mezi aplikacemi pro iOS pomocí Microsoft Intune](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).
- **IntuneMAMDeviceID** musí být nakonfigurované pro všechny aplikace spravované pro správu MDM od třetích stran. **IntuneMAMDeviceID** by mělo být nakonfigurované na token ID zařízení. Například `key=IntuneMAMDeviceID, value={{deviceID}}`. Další informace najdete v tématu [Přidání zásad konfigurace aplikací pro spravovaná zařízení s iOSem](app-configuration-policies-use-ios.md).
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
