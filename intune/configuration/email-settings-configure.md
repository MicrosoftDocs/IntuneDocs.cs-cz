---
title: Konfigurace nastavení e-mailu v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Vytvořte v Microsoft Intune e-mailový profil a nasaďte ho do zařízení s Androidem Enterprise, iOSem a Windows. Pomocí e-mailového profilu můžete na spravovaných zařízeních nakonfigurovat běžná nastavení e-mailu, například e-mailový server a metodu ověřování při připojení k firemnímu e-mailu.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 110db564dce5ad68d3c2a26b85e60ecbe99e7335
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059426"
---
# <a name="add-email-settings-to-devices-using-intune"></a>Přidání nastavení e-mailu do zařízení pomocí Intune

Microsoft Intune obsahuje různá nastavení e-mailu, která můžete nasadit do zařízení ve vaší organizaci. Správce IT vytvoří e-mailové profily se specifickým nastavením pro připojení k poštovnímu serveru, jako je například Office 365 a gmail. Koncoví uživatelé pak propojí, ověřují a synchronizují e-mailové účty organizace na svých mobilních zařízeních. Vytvořením a nasazením e-mailového profilu můžete potvrdit, že nastavení jsou standardně v mnoha zařízeních. Zároveň vám to pomůže omezit žádosti o podporu od koncových uživatelů, kteří neznají správná nastavení e-mailu.

E-mailové profily umožňují nakonfigurovat nastavení integrovaného e-mailu na následujících zařízeních:

- Android Samsung Knox Standard 4.0 a novější
- Android Enterprise
- iOS 8.0 a novější
- Windows Phone 8.1 a novější
- Windows 10 (pro stolní počítače) a Windows 10 Mobile

V tomto článku se dozvíte, jak vytvořit e-mailový profil v Microsoft Intune. Obsahuje také odkazy na různé platformy s podrobnějším nastavením.

## <a name="create-a-device-profile"></a>Vytvoření profilu zařízení

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **zařízení** > **konfiguračních profilech** > **vytvořit profil**.
3. Zadejte následující vlastnosti:

    - **Název**: zadejte popisný název zásady. Své zásady pojmenujte, abyste je později mohli snadno identifikovat. Dobrý název zásady je například **Nastavení e-mailu pro všechna zařízení s Windows**.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: vyberte platformu zařízení. Možnosti:

        - **Android** (jenom Samsung Android Knox Standard)
        - **Android Enterprise**
        - **iOS/iPadOS**
        - **Windows Phone 8.1**
        - **Windows 10 a novější**

    - **Typ profilu**: vyberte **e-mail**.

4. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Pro podrobnější nastavení vyberte platformu:

    - [Nastavení Android Samsung KNOX Standard](../email-settings-android.md)
    - [Nastavení Androidu Enterprise](../email-settings-android-enterprise.md)
    - [nastavení pro iOS/iPadOS](email-settings-ios.md)
    - [Nastavení Windows Phone 8.1](email-settings-windows-phone-8-1.md)
    - [Nastavení Windows 10](email-settings-windows-10.md)

5. Až to budete mít, vyberte **OK** > **Vytvořit** a změny uložte.

Po zadání nastavení a vytvoření profilu se tento profil zobrazí v seznamu profilů. Dále [tento profil přiřaďte některým skupinám](../device-profile-assign.md).

## <a name="remove-an-email-profile"></a>Odebrání e-mailového profilu

E-mailové profily se nepřiřazují skupinám uživatelů, ale skupinám zařízení. Existují různé způsoby, jak ze zařízení odebrat e-mailový profil, i když je v zařízení jenom jeden profil:

- **Možnost 1**: Otevřete e-mailový profil (**zařízení** > **konfigurační profily** > vyberte svůj profil) a zvolte **přiřazení**. Na kartě **Zahrnout** jsou skupiny, které jsou k profilu přiřazené. Klikněte na skupinu pravým tlačítkem > **Odebrat**. Nezapomeňte změny uložit kliknutím na **Uložit**.

- **2. možnost:** [Vymažte zařízení nebo ho vyřaďte](../remote-actions/devices-wipe.md). Tyto akce můžete použít k selektivnímu nebo úplnému odebrání dat a nastavení.

## <a name="secure-email-access"></a>Zabezpečení přístupu k e-mailu

E-mailové profily můžete zabezpečit pomocí následujících možností:

- **Certifikáty:** Při vytváření e-mailového profilu zvolíte profil certifikátu dříve vytvořený v Intune. Tento certifikát se označuje jako certifikát identity. Provádí ověření vůči profilu důvěryhodného certifikátu nebo kořenovému certifikátu a potvrzuje, že se zařízení uživatele může připojit. Tento důvěryhodný certifikát je přiřazený počítači, který ověřuje připojení k e-mailu. Tímto počítačem je zpravidla nativní poštovní server.

  Další informace o vytváření a používání profilů certifikátů v Intune najdete v tématu [Jak konfigurovat certifikáty pomocí Intune](../protect/certificates-configure.md).

- **Uživatelské jméno a heslo**: koncový uživatel se ověřuje na nativním poštovním serveru zadáním uživatelského jména a hesla. Heslo v e-mailovém profilu neexistuje. Proto koncový uživatel zadá heslo při připojování k e-mailu.

## <a name="how-intune-handles-existing-email-accounts"></a>Jak Intune nakládá s existujícími e-mailovými účty

Pokud si už uživatel e-mailový účet nakonfiguroval, přiřadí se e-mailový profil jinak, a to v závislosti na platformě.

- **iOS**: Je detekován existující duplicitní profil e-mailu na základě názvu hostitele a e-mailové adresy. Duplicitní e-mailový profil zablokuje přiřazení profilu Intune. V takovém případě aplikace Portál společnosti upozorní uživatele, že nedodržují předpisy, a vyzve koncového uživatele k ručnímu odebrání nakonfigurovaného profilu. Aby se zabránilo tomuto scénáři, řekněte koncovým uživatelům, aby se zaregistrovali *před* instalací e-mailového profilu, který umožňuje službě Intune nastavit profil.

- **Windows:** Na základě názvu hostitele a e-mailové adresy se detekuje existující duplicitní e-mailový profil. Intune přepíše existující e-mailový profil vytvořený koncovým uživatelem.

- **Android Samsung Knox Standard:** Na základě e-mailové adresy se zjistí přítomnost duplicitního e-mailového profilu, který se přepíše profilem Intune. Android nepoužívá k identifikaci profilu název hostitele. Nevytvářejte více e-mailových profilů se stejnou e-mailovou adresou na různých hostitelích. Profily se vzájemně přepíší.

- **Pracovní profily Androidu**: Intune nabízí dva pracovní e-mailové profily pro Android: jednu pro aplikaci Gmail a jednu pro devět pracovních aplikací. Tyto aplikace jsou dostupné v obchodě Google Play a instalují se v pracovním profilu zařízení. Tyto aplikace nevytvářejí duplicitní profily. Obě aplikace podporují připojení k Exchangi. Pokud chcete zajistit připojení k e-mailu, nasaďte do zařízení uživatelů jednu z těchto e-mailových aplikací. Pak vytvořte a nasaďte příslušný e-mailový profil. E-mailové aplikace, jako je Nine Work, nemusí být bezplatné. Přečtěte si podrobné informace o licencování aplikace nebo se v případě dotazů obraťte na společnost, která aplikaci vytvořila.

## <a name="changes-to-assigned-email-profiles"></a>Změny přiřazených e-mailových profilů

Pokud provedete změny e-mailového profilu, který jste předtím přiřadili, může se koncovým uživatelům zobrazit zpráva s žádostí, aby schválili rekonfiguraci nastavení e-mailu.

## <a name="next-steps"></a>Další kroky

Když je profil vytvořený, není ještě aktivní. V dalším kroku [profil přiřadíte](../device-profile-assign.md).
