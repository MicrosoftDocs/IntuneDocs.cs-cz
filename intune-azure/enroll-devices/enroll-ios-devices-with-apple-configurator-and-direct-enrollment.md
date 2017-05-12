---
title: "Registrace zařízení s iOSem pomocí Apple Configuratoru a přímé registrace"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si, jak jde pomocí Apple Configuratoru registrovat zařízení s iOSem vlastněná společností s využitím přímé registrace."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 02675b6fe9872cb634d0515172f696cedc7e6463
ms.contentlocale: cs-cz
ms.lasthandoff: 05/10/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-direct-enrollment"></a>Registrace zařízení s iOSem pomocí Apple Configuratoru a přímé registrace 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune podporuje registraci zařízení s iOSem patřících společnosti pomocí [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) spuštěného na počítači Mac. Tento proces neprovede reset továrního nastavení zařízení a zaregistruje ho s předdefinovanými zásadami. Tento způsob registrace je určený pro zařízení **bez přidruženého uživatele** a vyžaduje, abyste zařízení s iOSem připojili přes USB k počítači Mac a nastavili firemní registraci.

>[!NOTE]
>Tato metoda registrace se nedá použít s metodou [správce registrace zařízení](enroll-devices-using-device-enrollment-manager.md).

Při přímé registraci zařízení s iOSem můžete zařízení zaregistrovat i bez získání jeho sériového čísla. Můžete také zařízení pro potřeby identifikace pojmenovat před tím, než Intune zachytí název zařízení během registrace. U zařízení zaregistrovaných přímo není podporovaná aplikace Portál společnosti. Tyto pokyny předpokládají, že používáte Apple Configurator 2.0 na počítači Mac.

Další metody registrace zařízení s iOSem jsou popsané v článku [Volba způsobu registrace zařízení s iOSem v Intune](choose-ios-enrollment-method.md).


## <a name="prerequisites"></a>Požadavky

Před nastavením registrace zařízení s iOSem zajistěte splnění následujících požadavků:

- [Konfigurace domén](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Nastavení autority MDM](set-mdm-authority.md)
- [Vytvoření skupin](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Konfigurace aplikace Portál společnosti](../manage-apps/company-portal-app.md)
- Přiřazení uživatelských licencí na [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Získání certifikátu Apple MDM push certificate](get-an-apple-mdm-push-certificate.md)
- Ujistěte se, že máte k zařízením s iOSem fyzický přístup.
- Připravte si sériová čísla zařízení – viz článek o [zjištění sériového čísla zařízení s iOSem](https://support.apple.com//HT204308).
- Připravte si propojovací kabely USB.
- Ujistěte se, že máte počítač Mac s nainstalovaným [Apple Configuratorem 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

## <a name="create-an-apple-configurator-profile-for-devices"></a>Vytvoření profilu Apple Configuratoru pro zařízení

Profil registrace zařízení definuje nastavení, která se použijí pro skupinu zařízení. Následující postup ukazuje, jak vytvořit profil registrace zařízení s iOSem zaregistrovaného v Apple Configuratoru.

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Registrace Apple**.

3. V části **Spravovat nastavení registrace Apple Configuratoru** vyberte **Profily AC**.

4. V okně **Registrační profily Apple Configuratoru** vyberte **Vytvořit**.

5. V okně **Vytvořit registrační profil** zadejte název a popis profilu.

6. V části **Přidružení uživatele** zvolte **Zaregistrovat bez přidružení uživatele**, aby zařízení nebylo přidružené k uživateli. Toto spřažení použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, které vyžadují přidruženého uživatele (včetně aplikace Portál společnosti používané k instalaci obchodních aplikací), nebudou fungovat.

7. Uložte profil pomocí tlačítka **Vytvořit**.

## <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Export profilu jako souboru .mobileconfig do zařízení s iOSem

1. V okně **Exportovat profil** stáhněte registrační profil do [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), aby se dal přímo připojenému zařízení s iOSem nabídnout jako profil pro správu. Při této metodě není nutné resetovat zařízení do továrního nastavení.

2. Připravte zařízení pomocí Apple Configuratoru podle následujících kroků.

   a. Na počítači Mac otevřete Apple Configurator 2.0.

   b. Zařízení s iOSem připojte k počítači Mac pomocí kabelu USB. Zavřete Fotky, iTunes a další aplikace, které se otevřou při zjištění zařízení.

   c. V Apple Configuratoru zvolte připojené zařízení s iOSem a potom zvolte tlačítko **Přidat**. V rozevíracím seznamu se zobrazí možnosti, které se dají přidat do zařízení. Vyberte **Profily**.

   d. Pomocí nástroje pro výběr souborů vyberte soubor .mobileconfig, který jste exportovali z Intune, a zvolte **Přidat**. Profil se přidá do zařízení. Pokud má zařízení nastavenou možnost Bez dohledu, instalace bude vyžadovat přijetí na zařízení.

3. Nainstalujte profil na zařízení s iOSem podle následujících kroků. Je potřeba, aby už byl v zařízení dokončený Pomocník s nastavením a aby bylo připravené k použití. Pokud registrace zahrnuje nasazení aplikací, zařízení by mělo mít nastavené Apple ID, protože při nasazení aplikace bude potřeba přihlásit se do obchodu App Store pomocí Apple ID.

   a. Odemkněte zařízení s iOS.

   b. V dialogovém okně **Nainstalovat profil** pro **Profil správy** zvolte **Instalovat**.

   c. V případě potřeby zadejte heslo zařízení nebo Apple ID.

   d. Potvrďte **upozornění** a zvolte **Instalovat**.

   e. Potvrďte **vzdálené upozornění** a zvolte **Důvěřovat**.

   f. Jakmile okno **Profil nainstalován** potvrdí, že se profil nainstaloval, zvolte **Hotovo**.

4. Na zařízení s iOSem otevřete **Nastavení** a přejděte na **Obecné** > **Správa zařízení** > **Profil pro správu**. Potvrďte, že je zde instalace profilu uvedená, a zkontrolujte omezení zásad iOS a nainstalované aplikace. Zobrazení omezení vyplývajících ze zásad a aplikací na zařízení může trvat až 10 minut.

5. Distribuujte zařízení. Zařízení s iOSem je teď zaregistrované v Intune a spravované.

