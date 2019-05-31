---
title: Konfigurace nastavení e-mailu v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Vytvořte v Microsoft Intune e-mailový profil a nasaďte ho do zařízení s Androidem Enterprise, iOSem a Windows. Pomocí e-mailového profilu můžete na spravovaných zařízeních nakonfigurovat běžná nastavení e-mailu, například e-mailový server a metodu ověřování při připojení k firemnímu e-mailu.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/10/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6a80ff2ca7c2265da358f57291032f59d47d22dd
ms.sourcegitcommit: 063177c6c365fef3642edd7c455790958469aad9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412337"
---
# <a name="add-email-settings-to-devices-using-intune"></a>Přidání nastavení e-mailu do zařízení pomocí Intune

Microsoft Intune obsahuje různá nastavení e-mailu, která můžete nasadit do zařízení ve vaší organizaci. Správce IT vytvoří e-mailové profily se specifickými nastaveními pro připojení k e-mailový server, jako je Office 365 nebo Gmail. Koncoví uživatelé pak připojení, ověření a synchronizovat své účty organizace e-mailu na mobilním zařízení. Vytvořením a nasazením e-mailový profil, můžete ověřit, že jsou standardní nastavení různých zařízení. Zároveň vám to pomůže omezit žádosti o podporu od koncových uživatelů, kteří neznají správná nastavení e-mailu.

E-mailové profily umožňují nakonfigurovat nastavení integrovaného e-mailu na následujících zařízeních:

- Android Samsung Knox Standard 4.0 a novější
- Android Enterprise
- iOS 8.0 a novější
- Windows Phone 8.1 a novější
- Windows 10 (pro stolní počítače) a Windows 10 Mobile

V tomto článku se dozvíte, jak vytvořit e-mailový profil v Microsoft Intune. Obsahuje také odkazy na různé platformy s podrobnějším nastavením.

## <a name="create-a-device-profile"></a>Vytvoření profilu zařízení

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte **Název** a **Popis** e-mailového profilu.
4. V rozevíracím seznamu **Platforma** zvolte odpovídající možnost. Možnosti:

    - **Android** (jenom Samsung Android Knox Standard)
    - **Android Enterprise**
    - **iOS**
    - **Windows Phone 8.1**
    - **Windows 10 a novější**

5. V rozevíracím seznamu **Typ profilu** zvolte **E-mail**.
6. Nastavení, která můžete konfigurovat, se mohou pro jednotlivé platformy lišit. Pro konkrétní nastavení zvolte svou platformu:

    - [Nastavení pro Android Samsung Knox Standard](email-settings-android.md)
    - [Nastavení androidu Enterprise](email-settings-android-enterprise.md)
    - [Nastavení iOSu](email-settings-ios.md)
    - [Nastavení Windows Phone 8.1](email-settings-windows-phone-8-1.md)
    - [Nastavení Windows 10](email-settings-windows-10.md)

Po zadání nastavení a vytvoření profilu se tento profil zobrazí v seznamu profilů. Dále [tento profil přiřaďte některým skupinám](device-profile-assign.md).

## <a name="remove-an-email-profile"></a>Odebrání e-mailového profilu

E-mailové profily se nepřiřazují skupinám uživatelů, ale skupinám zařízení. Existují různé způsoby, jak ze zařízení odebrat e-mailový profil, i když je v zařízení jenom jeden profil:

- **Možnost 1**: Otevřete e-mailový profil (**konfigurace zařízení** > **profily**) a zvolte **přiřazení**. Na kartě **Zahrnout** jsou skupiny, které jsou k profilu přiřazené. Klikněte na skupinu pravým tlačítkem > **Odebrat**. Nezapomeňte změny uložit kliknutím na **Uložit**.

- **Možnost 2**: [Vymazání nebo vyřazení zařízení](devices-wipe.md). Tyto akce můžete použít k selektivnímu nebo úplnému odebrání dat a nastavení.

## <a name="secure-email-access"></a>Zabezpečení přístupu k e-mailu

E-mailové profily můžete zabezpečit pomocí následujících možností:

- **Certifikáty**: Při vytváření e-mailový profil, vybíráte profil certifikátu předtím vytvořili v Intune. Tento certifikát se označuje jako certifikát identity. Provádí ověření vůči profilu důvěryhodného certifikátu nebo kořenovému certifikátu a potvrzuje, že se zařízení uživatele může připojit. Tento důvěryhodný certifikát je přiřazený počítači, který ověřuje připojení k e-mailu. Tímto počítačem je zpravidla nativní poštovní server.

  Další informace o vytváření a používání profilů certifikátů v Intune najdete v tématu [Jak konfigurovat certifikáty pomocí Intune](certificates-configure.md).

- **Uživatelské jméno a heslo**: Koncový uživatel se ověřuje na nativním poštovním serveru zadáním uživatelského jména a hesla. Heslo v e-mailovém profilu neexistuje. Ano koncový uživatel zadá heslo při připojování k e-mailu.

## <a name="how-intune-handles-existing-email-accounts"></a>Jak Intune nakládá s existujícími e-mailovými účty

Pokud si už uživatel e-mailový účet nakonfiguroval, přiřadí se e-mailový profil jinak, a to v závislosti na platformě.

- **iOS**: Na základě názvu hostitele a e-mailové adresy se detekuje existující duplicitní e-mailový profil. Duplicitní e-mailový profil zablokuje přiřazení profilu Intune. V tomto případě aplikace portál společnosti upozorní uživatele, aby nedodržují předpisy a vyzve koncového uživatele k odebrání ručně nakonfigurovaného profilu. Abyste předešli této situaci, říct koncovým uživatelům k registraci *před* instalace e-mailový profil, který umožňuje službě Intune profilu.

- **Windows:** Na základě názvu hostitele a e-mailové adresy se detekuje existující duplicitní e-mailový profil. Intune přepíše existující e-mailový profil vytvořený koncový uživatel.

- **Android Samsung Knox Standard**: Na základě e-mailové adresy se detekuje existující duplicitní e-mailový profil a přepíše se profilem Intune. Android nepoužívá k identifikaci profilu název hostitele. Nevytvářejte více e-mailových profilů se stejnou e-mailovou adresou na různých hostitelích. Profily by se vzájemně přepisovaly.

- **Pracovní profily androidu**: Intune poskytuje dva Android pracovní e-mailové profily: jeden pro aplikaci Gmail a Nine Work aplikace pro. Tyto aplikace jsou dostupné v obchodě Google Play a instalují se v pracovním profilu zařízení. Tyto aplikace nevytvářejí vytvoření duplicitních profilů. Obě aplikace podporují připojení k Exchangi. Pokud chcete zajistit připojení k e-mailu, nasaďte do zařízení uživatelů jednu z těchto e-mailových aplikací. Pak vytvořte a nasaďte příslušný e-mailový profil. E-mailové aplikace, jako je Nine Work, nemusí být bezplatné. Přečtěte si podrobné informace o licencování aplikace nebo se v případě dotazů obraťte na společnost, která aplikaci vytvořila.

## <a name="changes-to-assigned-email-profiles"></a>Změny přiřazených e-mailových profilů

Pokud provedete změny e-mailového profilu, který jste předtím přiřadili, může se koncovým uživatelům zobrazit zpráva s žádostí, aby schválili rekonfiguraci nastavení e-mailu.

## <a name="next-steps"></a>Další postup

Když je profil vytvořený, není ještě aktivní. Dále [některá zařízení přiřadit profil](device-profile-assign.md).
