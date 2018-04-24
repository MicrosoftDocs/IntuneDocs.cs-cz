---
title: Jak nakonfigurovat nastavení e-mailu v Microsoft Intune
titleSuffix: ''
description: Naučte se nakonfigurovat v Microsoft Intune připojení k podnikovému e-mailu na zařízeních, která spravujete.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f51854bfb198ca65cc5fc82bad0e3b3befbb173a
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-email-settings-in-microsoft-intune"></a>Jak nakonfigurovat nastavení e-mailu v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pomocí e-mailových profilů můžete na spravovaných zařízeních konfigurovat nastavení, která jsou potřebná pro připojení k podnikovému e-mailu a jeho synchronizaci. To může pomoct zajistit, abyste měli na všech zařízeních standardní nastavení, a také přispět ke snížení počtu volání podpory ze strany koncových uživatelů, kteří nevědí, jak si správně nastavit e-mail.

Na většině platforem se podporuje integrovaný poštovní klient. Většina e-mailových aplikací třetích stran se v současné době nepodporuje.

E-mailové profily můžete použít ke konfiguraci nativních e-mailových klientů na těchto typech zařízení:

- Android Samsung Knox Standard 4.0 a novější
- Android for Work
- iOS 8.0 a novější
- Windows Phone 8.1 a novější
- Windows 10 (pro stolní počítače) a Windows 10 Mobile

Informace v tomto článku vás seznámí se základy konfigurace e-mailového profilu. Pak si můžete přečíst další témata pro jednotlivé platformy, abyste zjistili zvláštnosti zařízení.

## <a name="create-a-device-profile-containing-email-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení e-mailu

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Konfigurace zařízení**.
2. V podokně **Konfigurace zařízení** v části **Spravovat** zvolte **Profily**.
3. V podokně profilů zvolte **Vytvořit profil**.
4. V podokně **Vytvořit profil** zadejte **název** a **popis** e-mailového profilu.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete použít nastavení e-mailu. V současné době můžete pro nastavení e-mailu na zařízení zvolit jednu z následujících platforem:
    - **Android** (jenom Samsung Android Knox Standard)
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **E-mail**.
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobnosti o nastaveních na jednotlivých platformách najdete v následujících tématech:
    - [Nastavení Androidu for Work a platformy Samsung Knox Standard](email-settings-android.md)
    - [Nastavení iOSu](email-settings-ios.md)
    - [Nastavení Windows Phone 8.1](email-settings-windows-phone-8-1.md)
    - [Nastavení Windows 10](email-settings-windows-10.md)
8. Až to budete mít, vraťte se do podokna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v podokně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).

## <a name="further-information"></a>Další informace

### <a name="remove-an-email-profile"></a>Odebrání e-mailového profilu

Pokud byste chtěli e-mailový profil ze zařízení odebrat, upravte přiřazení a odeberte všechny skupiny, ve kterých je zařízení členem. Pokud se jedná o jediný e-mailový profil na zařízení, nemůžete tento profil takto odebrat.

### <a name="securing-email-access"></a>Zabezpečení přístupu k e-mailu

E-mailové profily se dají zabezpečit jedním ze dvou způsobů:

1. **Certifikáty** – Při vytváření e-mailového profilu zvolíte profil certifikátu, který jste předtím vytvořili v Intune. Ten se označuje jako certifikát identity a slouží k ověřování na základě důvěryhodného profilu certifikátu (neboli kořenového certifikátu), který potvrzuje, že má zařízení uživatele dovoleno připojovat se. Tento důvěryhodný certifikát se přiřadí počítači, který ověřuje e-mailové připojení. Zpravidla se jedná o nativní poštovní server.
Další informace o vytváření a používání profilů certifikátů v Intune najdete v tématu [Jak konfigurovat certifikáty pomocí Intune](certificates-configure.md).
2. **Uživatelské jméno a heslo** – Uživatel se ověřuje na nativním poštovním serveru zadáním uživatelského jména a hesla.
Heslo není součástí e-mailového profilu, uživatel ho tedy musí zadat při připojování k e-mailu.


### <a name="how-intune-handles-existing-email-accounts"></a>Jak Intune nakládá s existujícími e-mailovými účty

Pokud má už uživatel nakonfigurovaný e-mailový účet, pak výsledek přiřazení e-mailového profilu v Intune závisí na platformě zařízení:

- **iOS:** Na základě názvu hostitele a e-mailové adresy se detekuje existující duplicitní e-mailový profil. Duplicitní e-mailový profil zablokuje přiřazení profilu Intune. Portál společnosti v tomto případě informuje uživatele o tom, že nesplňuje požadavky, a vyzve ho k odebrání ručně nakonfigurovaného profilu. Pokud chcete tomuto problému zabránit, požádejte uživatele, aby se zaregistrovali před instalací e-mailového profilu, čímž se umožní, aby profil nastavila služba Intune.
- **Windows:** Na základě názvu hostitele a e-mailové adresy se detekuje existující duplicitní e-mailový profil. Intune přepíše existující e-mailový profil vytvořený uživatelem.
- **Android Samsung Knox Standard:** Na základě e-mailové adresy se zjistí přítomnost duplicitního e-mailového profilu, který se přepíše profilem Intune.
Vzhledem k tomu, že Android nevyužívá k identifikaci profilu název hostitele, doporučujeme nevytvářet více e-mailových profilů pro použití se stejnou e-mailovou adresou na různých hostitelích, protože by se vzájemně přepisovaly.
- **Android for Work:** Intune poskytuje dva e-mailové profily pro Android for Work – jeden pro každou z e-mailových aplikací Gmail a Nine Work. Tyto aplikace jsou dostupné v obchodě Google Play a můžete je nainstalovat do pracovního profilu zařízení, aby nedošlo k vytvoření duplicitních profilů. Obě aplikace podporují připojení k Exchangi. Pokud chcete umožnit připojení k e-mailu, nasaďte jednu z těchto e-mailových aplikací do zařízení uživatelů a pak vytvořte a nasaďte příslušný e-mailový profil. E-mailové aplikace, jako je Nine Work, nemusí být bezplatné. Přečtěte si podrobné informace o licencování aplikace nebo se v případě dotazů obraťte na společnost, která aplikaci vytvořila.

### <a name="update-an-email-profile"></a>Aktualizace e-mailového profilu

Pokud provedete změny e-mailového profilu, který jste předtím přiřadili, koncovým uživatelům se může zobrazit zpráva s požadavkem, aby schválili rekonfiguraci nastavení e-mailu.
