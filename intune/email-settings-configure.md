---
title: "Jak nakonfigurovat nastavení e-mailu v Intune"
titleSuffix: Azure portal
description: "Naučte se nakonfigurovat v Intune připojení k podnikovému e-mailu na zařízeních, která spravujete."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 484bd9b0-fbf1-4f4f-940c-6b12fa07e228
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9de8eed31a93fc1360eb1a62b1d9328b42853d74
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-configure-email-settings-in-microsoft-intune"></a>Jak nakonfigurovat nastavení e-mailu v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pomocí e-mailových profilů můžete na spravovaných zařízeních konfigurovat nastavení, která jsou potřebná pro připojení k podnikovému e-mailu a jeho synchronizaci. To může pomoct zajistit, abyste měli na všech zařízeních standardní nastavení, a také přispět ke snížení počtu volání podpory ze strany koncových uživatelů, kteří nevědí, jak si správně nastavit e-mail.

Na většině platforem se podporuje integrovaný poštovní klient. Většina e-mailových aplikací třetích stran se v současné době nepodporuje.

E-mailové profily můžete použít ke konfiguraci nativních e-mailových klientů na těchto typech zařízení:

- Zařízení, na kterém běží Android Samsung KNOX Standard 4.0 nebo novější
- Android for Work
- iOS 8.0 a novější
- Windows Phone 8.1 a novější
- Windows 10 (pro stolní počítače) a Windows 10 Mobile

Informace v tomto tématu vás seznámí se základy konfigurace e-mailového profilu. Pak si můžete přečíst další témata pro jednotlivé platformy, kde najdete podrobnosti o specifikách různých zařízení.

## <a name="create-a-device-profile-containing-email-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení e-mailu

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **název** a **popis** e-mailového profilu.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete použít nastavení e-mailu. V současné době můžete pro nastavení e-mailu na zařízení zvolit jednu z následujících platforem:
    - **Android** (jenom Samsung Android KNOX Standard)
    - **Android for Work**
    - **iOS**
    - **Windows Phone 8.1**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **E-mail**.
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobnosti o nastaveních na jednotlivých platformách najdete v následujících tématech:
    - [Nastavení Androidu for Work a Samsung KNOX Standard](email-settings-android.md)
    - [Nastavení iOSu](email-settings-ios.md)
    - [Nastavení Windows Phone 8.1](email-settings-windows-phone-8-1.md)
    - [Nastavení Windows 10](email-settings-windows-10.md)
8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).

## <a name="further-information"></a>Další informace

### <a name="remove-an-email-profile"></a>Odebrání e-mailového profilu

Pokud byste chtěli e-mailový profil ze zařízení odebrat, upravte přiřazení a odeberte všechny skupiny, ve kterých je zařízení členem. Nezapomeňte, že pokud se jedná o jediný e-mailový profil na zařízení, nemůžete tento profil takto odebrat.

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
- **Android Samsung KNOX Standard:** Na základě e-mailové adresy se detekuje existující duplicitní e-mailový profil a přepíše se profilem Intune.
Vzhledem k tomu, že Android nevyužívá k identifikaci profilu název hostitele, doporučujeme nevytvářet více e-mailových profilů pro použití se stejnou e-mailovou adresou na různých hostitelích, protože by se vzájemně přepisovaly.
- **Android for Work:** Intune poskytuje dva e-mailové profily pro Android for Work – jeden pro každou z e-mailových aplikací Gmail a Nine Work. Tyto aplikace jsou dostupné v obchodě Google Play a můžete je nainstalovat do pracovního profilu zařízení, aby nedošlo k vytvoření duplicitních profilů. Obě aplikace podporují připojení k Exchangi. Pokud chcete umožnit připojení k e-mailu, nasaďte jednu z těchto e-mailových aplikací do zařízení uživatelů a pak vytvořte a nasaďte příslušný e-mailový profil. E-mailové aplikace, jako je Nine Work, nemusí být bezplatné. Přečtěte si podrobné informace o licencování aplikace nebo se v případě dotazů obraťte na společnost, která aplikaci vytvořila.

### <a name="update-an-email-profile"></a>Aktualizace e-mailového profilu

Pokud provedete změny e-mailového profilu, který jste předtím přiřadili, koncovým uživatelům se může zobrazit zpráva s požadavkem, aby schválili rekonfiguraci nastavení e-mailu.
