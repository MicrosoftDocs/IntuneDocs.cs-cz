---
title: "Jak nakonfigurovat nastavení e-mailu v Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Naučte se nakonfigurovat v Intune připojení k podnikovému e-mailu na zařízeních, která spravujete."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 484bd9b0-fbf1-4f4f-940c-6b12fa07e228
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 66c189ed45b8b5226e36ef4769c0872c428646bb
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-configure-email-settings-in-microsoft-intune"></a>Jak nakonfigurovat nastavení e-mailu v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Pomocí nastavení e-mailového profilu můžete na spravovaných zařízeních konfigurovat nastavení, která jsou potřebná pro připojení k podnikovému e-mailu a jeho synchronizaci. To může pomoct zajistit, abyste měli na všech zařízeních standardní nastavení, a také přispět ke snížení počtu volání podpory ze strany koncových uživatelů, kteří nevědí, jak si správně nastavit e-mail.

Na většině platforem se podporuje integrovaný poštovní klient. Většina e-mailových aplikací třetích stran se v současné době nepodporuje.

E-mailové profily můžete použít ke konfiguraci nativních e-mailových klientů na těchto typech zařízení:

- Android 4.0 a novější
- iOS 8.0 a novější
- Windows Phone 8.1 a novější
- Windows 10 (pro stolní počítače) a Windows 10 Mobile

Informace v tomto tématu vás seznámí se základy konfigurace e-mailového profilu. Pak si můžete přečíst další témata pro jednotlivé platformy, kde najdete podrobnosti o specifikách různých zařízení.

## <a name="create-a-device-profile-containing-email-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení e-mailu

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Konfigurovat zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **název** a **popis** e-mailového profilu.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete použít nastavení e-mailu. V současné době můžete pro nastavení e-mailu na zařízení zvolit jednu z následujících platforem:
    - **Android**
    - **iOS**
    - **Windows Phone 8.1**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **E-mail**.
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobnosti o nastaveních na jednotlivých platformách najdete v následujících tématech:
    - [Nastavení Androidu](email-profile-settings-for-android.md)
    - [Nastavení iOSu](email-profile-settings-for-ios.md)
    - [Nastavení Windows Phone 8.1](email-profile-settings-for-windows-phone-8-1.md)
    - [Nastavení Windows 10](email-profile-settings-for-windows-10.md)
8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](how-to-assign-device-profiles.md).

## <a name="further-information"></a>Další informace

### <a name="remove-an-email-profile"></a>Odebrání e-mailového profilu

Pokud byste chtěli e-mailový profil ze zařízení odebrat, upravte přiřazení a odeberte všechny skupiny, ve kterých je zařízení členem. Nezapomeňte, že pokud se jedná o jediný e-mailový profil na zařízení, nemůžete tento profil takto odebrat.

### <a name="securing-email-access"></a>Zabezpečení přístupu k e-mailu

E-mailové profily se dají zabezpečit jedním ze dvou způsobů:

1. **Certifikáty** – Při vytváření e-mailového profilu zvolíte profil certifikátu, který jste předtím vytvořili v Intune. Ten se označuje jako certifikát identity a slouží k ověřování na základě důvěryhodného profilu certifikátu (neboli kořenového certifikátu), který potvrzuje, že má zařízení uživatele dovoleno připojovat se. Důvěryhodný certifikát se nasadí do počítače, který ověří e-mailové připojení. Většinou se jedná o nativní poštovní server.
Další informace o vytváření a používání profilů certifikátů v Intune najdete v tématu [Jak konfigurovat certifikáty pomocí Intune](/intune-azure/configure-devices/how-to-configure-certificates).
2. **Uživatelské jméno a heslo** – Uživatel se ověřuje na nativním poštovním serveru zadáním uživatelského jména a hesla.
Heslo není součástí e-mailového profilu, uživatel ho tedy musí zadat při připojování k e-mailu.


### <a name="how-intune-handles-existing-email-accounts"></a>Jak Intune nakládá s existujícími e-mailovými účty

Pokud má už uživatel nakonfigurovaný e-mailový účet, pak výsledek přiřazení e-mailového profilu v Intune závisí na platformě zařízení:

- **iOS:** Na základě názvu hostitele a e-mailové adresy se detekuje existující duplicitní e-mailový profil. Duplicitní e-mailový profil zablokuje přiřazení profilu Intune. Portál společnosti v tomto případě informuje uživatele o tom, že nesplňuje požadavky, a vyzve ho k odebrání ručně nakonfigurovaného profilu. Pokud chcete tomuto problému zabránit, požádejte uživatele, aby se zaregistrovali před instalací e-mailového profilu, čímž se umožní, aby profil nastavila služba Intune.
- **Windows:** Na základě názvu hostitele a e-mailové adresy se detekuje existující duplicitní e-mailový profil. Intune přepíše existující e-mailový profil vytvořený uživatelem.
- **Android:** Na základě e-mailové adresy se detekuje existující duplicitní e-mailový profil a přepíše se profilem Intune.
Vzhledem k tomu, že Android nevyužívá k identifikaci profilu název hostitele, doporučujeme nevytvářet více e-mailových profilů pro použití se stejnou e-mailovou adresou na různých hostitelích, protože by se vzájemně přepisovaly.

