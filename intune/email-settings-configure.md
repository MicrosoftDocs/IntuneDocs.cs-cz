---
title: Konfigurace nastavení e-mailu v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Vytvořte v Microsoft Intune e-mailový profil a nasaďte ho do zařízení s Androidem Enterprise, iOSem a Windows. Pomocí e-mailového profilu můžete na spravovaných zařízeních nakonfigurovat běžná nastavení e-mailu, například e-mailový server a metodu ověřování při připojení k firemnímu e-mailu.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 41f16cf0dacc059546a09145a0c241f7c2a4a076
ms.sourcegitcommit: 5c2a70180cb69049c73c9e55d36a51e9d6619049
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2018
ms.locfileid: "50236318"
---
# <a name="add-email-settings-to-devices-using-intune"></a>Přidání nastavení e-mailu do zařízení pomocí Intune

Microsoft Intune obsahuje různá nastavení e-mailu, která můžete nasadit do zařízení ve vaší organizaci. Správce IT může vytvořit e-mailové profily se specifickými nastaveními pro připojení k e-mailovému serveru, jako je Office 365 a Gmail. Uživatelé se pak připojí, ověří a synchronizují své e-mailové účty organizace na svých mobilních zařízeních. Vytvořením a nasazením e-mailového profilu můžete zajistit standardní nastavení na mnoha zařízeních. Zároveň vám to pomůže omezit žádosti o podporu od koncových uživatelů, kteří neznají správná nastavení e-mailu.

E-mailové profily umožňují nakonfigurovat nastavení integrovaného e-mailu na následujících zařízeních:

- Android Samsung Knox Standard 4.0 a novější
- Zařízení s pracovním profilem Androidu
- iOS 8.0 a novější
- Windows Phone 8.1 a novější
- Windows 10 (pro stolní počítače) a Windows 10 Mobile

V tomto článku se dozvíte, jak vytvořit e-mailový profil v Microsoft Intune. Obsahuje také odkazy na různé platformy s podrobnějším nastavením.

## <a name="create-a-device-profile"></a>Vytvoření profilu zařízení

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte **Název** a **Popis** e-mailového profilu.
4. V rozevíracím seznamu **Platforma** zvolte odpovídající možnost. Možnosti:

    - **Android** (jenom Samsung Android Knox Standard)
    - **Android Enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**

5. V rozevíracím seznamu **Typ profilu** zvolte **E-mail**.
6. Nastavení, která můžete konfigurovat, se mohou pro jednotlivé platformy lišit. Pro konkrétní nastavení zvolte svou platformu:

    - [Nastavení pracovního profilu Androidu a Samsung Knox Standard](email-settings-android.md)
    - [Nastavení iOSu](email-settings-ios.md)
    - [Nastavení Windows Phone 8.1](email-settings-windows-phone-8-1.md)
    - [Nastavení Windows 10](email-settings-windows-10.md)

Po zadání nastavení a vytvoření profilu se tento profil zobrazí v seznamu profilů. Dále [tento profil přiřaďte některým skupinám](device-profile-assign.md).

## <a name="remove-an-email-profile"></a>Odebrání e-mailového profilu

E-mailové profily se nepřiřazují skupinám uživatelů, ale skupinám zařízení. Existují různé způsoby, jak ze zařízení odebrat e-mailový profil, i když je v zařízení jenom jeden profil:

- **1. možnost:** Otevřete e-mailový profil (**Konfigurace zařízení** > **Profily**) a zvolte **Přiřazení**. Na kartě **Zahrnout** jsou skupiny, které jsou k profilu přiřazené. Klikněte na skupinu pravým tlačítkem > **Odebrat**. Nezapomeňte změny uložit kliknutím na **Uložit**.

- **2. možnost:** [Vymažte zařízení nebo ho vyřaďte](devices-wipe.md). Tyto akce můžete použít k selektivnímu nebo úplnému odebrání dat a nastavení.

## <a name="secure-email-access"></a>Zabezpečení přístupu k e-mailu

E-mailové profily můžete zabezpečit pomocí následujících možností:

- **Certifikáty:** Při vytváření e-mailového profilu zvolíte profil certifikátu dříve vytvořený v Intune. Tento certifikát se označuje jako certifikát identity. Provádí ověření vůči profilu důvěryhodného certifikátu nebo kořenovému certifikátu a potvrzuje, že se zařízení uživatele může připojit. Tento důvěryhodný certifikát je přiřazený počítači, který ověřuje připojení k e-mailu. Tímto počítačem je zpravidla nativní poštovní server.

  Další informace o vytváření a používání profilů certifikátů v Intune najdete v tématu [Jak konfigurovat certifikáty pomocí Intune](certificates-configure.md).

- **Uživatelské jméno a heslo:** Uživatel se ověřuje vůči nativnímu poštovnímu serveru zadáním uživatelského jména a hesla. Heslo v e-mailovém profilu neexistuje. Uživatel proto musí zadat heslo při připojování k e-mailu.

## <a name="how-intune-handles-existing-email-accounts"></a>Jak Intune nakládá s existujícími e-mailovými účty

Pokud si už uživatel e-mailový účet nakonfiguroval, přiřadí se e-mailový profil jinak, a to v závislosti na platformě.

- **iOS**: Je detekován existující duplicitní profil e-mailu na základě názvu hostitele a e-mailové adresy. Duplicitní e-mailový profil zablokuje přiřazení profilu Intune. V tomto případě aplikace Portál společnosti oznámí uživateli, že nedodržuje předpisy a vyzve ho k ručnímu odebrání nakonfigurovaného profilu. Pokud chcete této situaci zabránit, požádejte uživatele, aby se zaregistrovali *před* instalací e-mailového profilu, což službě Intune umožní nastavit tento profil.

- **Windows:** Na základě názvu hostitele a e-mailové adresy se detekuje existující duplicitní e-mailový profil. Intune přepíše existující e-mailový profil vytvořený uživatelem.

- **Android Samsung Knox Standard:** Na základě e-mailové adresy se zjistí přítomnost duplicitního e-mailového profilu, který se přepíše profilem Intune. Android nepoužívá k identifikaci profilu název hostitele. Nevytvářejte více e-mailových profilů se stejnou e-mailovou adresou na různých hostitelích. Tyto profily se vzájemně přepíšou.

- **Pracovní profily Androidu:** Intune poskytuje dva pracovní e-mailové profily pro Android: jeden pro aplikaci Gmail a jeden pro aplikaci Nine Work. Tyto aplikace jsou dostupné v obchodě Google Play a instalují se v pracovním profilu zařízení. Tyto aplikace nevytvoří duplicitní profily. Obě aplikace podporují připojení k Exchangi. Pokud chcete zajistit připojení k e-mailu, nasaďte do zařízení uživatelů jednu z těchto e-mailových aplikací. Pak vytvořte a nasaďte příslušný e-mailový profil. E-mailové aplikace, jako je Nine Work, nemusí být bezplatné. Přečtěte si podrobné informace o licencování aplikace nebo se v případě dotazů obraťte na společnost, která aplikaci vytvořila.

## <a name="changes-to-assigned-email-profiles"></a>Změny přiřazených e-mailových profilů

Pokud provedete změny e-mailového profilu, který jste předtím přiřadili, může se koncovým uživatelům zobrazit zpráva s žádostí, aby schválili rekonfiguraci nastavení e-mailu.

## <a name="next-steps"></a>Další kroky
Když je profil vytvořený, není ještě aktivní. Jako další krok [tento profil přiřaďte některým zařízením](device-profile-assign.md).