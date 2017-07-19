---
title: "Registrace zařízení s iOSem – Apple Configurator – Pomocník s nastavením"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak jde pomocí Apple Configuratoru registrovat zařízení s iOSem vlastněná společností s využitím Pomocníka s nastavením.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1d74fbcebfe89bbafc545d11dd6316cb602db8ee
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>Registrace zařízení s iOSem pomocí Apple Configuratoru

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune podporuje registraci zařízení s iOSem patřících společnosti pomocí [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) spuštěného na počítači Mac. Registrace pomocí Apple Configuratoru vyžaduje, abyste každé zařízení s iOSem připojili prostřednictvím USB k počítači Mac a nastavili registraci pro podniky. Zařízení můžete do služby Intune registrovat pomocí Apple Configuratoru dvěma způsoby:
- **Registrace Pomocníka s nastavením** – Obnoví tovární nastavení zařízení a připraví ho ke spuštění Pomocníka s nastavením a k instalaci zásad společnosti pro nového uživatele zařízení. K povolení aplikace Portál společnosti služby Intune většina scénářů vyžaduje, aby zásady použité na zařízení s iOSem zahrnovaly přidružení uživatele.
- **Přímá registrace** – Neobnoví tovární nastavení zařízení a zaregistruje ho s předdefinovanými zásadami. Tato metoda je vhodná pro zařízení **bez přidružení uživatele**.

>[!NOTE]
>Tato metoda registrace se nedá použít s metodou [správce registrace zařízení](device-enrollment-manager-enroll.md).

Další metody registrace zařízení s iOSem jsou popsané v článku [Volba způsobu registrace zařízení s iOSem v Intune](enrollment-method-choose-ios.md).

## <a name="prerequisites"></a>Požadavky

Před nastavením registrace zařízení s iOSem zajistěte splnění následujících požadavků:

- [Certifikát Apple MDM push certificate](apple-mdm-push-certificate-get.md)
- Fyzický přístup k zařízením s iOS
- Sériová čísla zařízení (viz článek [Zjištění sériového čísla zařízení s iOSem](https://support.apple.com//HT204308))
- Propojovací kabely USB
- Počítač Mac s [Apple Configuratorem 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)
- [Přidání sériových čísel Apple Configuratoru](apple-configurator-serial-numbers-add.md)

## <a name="setup-assistant-enrollment"></a>Registrace Pomocníka s nastavením

### <a name="create-an-apple-configurator-profile-for-devices"></a>Vytvoření profilu Apple Configuratoru pro zařízení

Profil registrace zařízení definuje nastavení, která se použijí pro skupinu zařízení. Následující postup ukazuje, jak vytvořit profil registrace zařízení s iOSem zaregistrovaného v Apple Configuratoru.

1. Na portálu Intune zvolte **Registrace zařízení** a pak zvolte **Registrace Apple**.
2. V části **Spravovat nastavení registrace Apple Configuratoru** vyberte **Profily AC**.
3. V okně **Registrační profily Apple Configuratoru** vyberte **Vytvořit**.
4. V okně **Vytvořit registrační profil** zadejte název a popis profilu.
5. V části **Přidružení uživatele** zvolte, jestli se zařízení s tímto profilem budou registrovat s přidružením uživatele nebo bez.

   - **Zaregistrovat s přidružením uživatele** – Při počátečním nastavení musí mít zařízení přidruženého uživatele, aby mohlo dostat přístup k firemním datům a e-mailu. Přidružení uživatele by se mělo nastavit pro spravovaná zařízení, která patří konkrétním uživatelům a potřebují používat portál společnosti kvůli službám, jako je instalace aplikací.
   - **Zaregistrovat bez přidružení uživatele** – K zařízení není přidružený žádný uživatel. Toto spřažení použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, které vyžadují přidruženého uživatele (včetně aplikace Portál společnosti používané k instalaci obchodních aplikací), nebudou fungovat.

6. Uložte profil pomocí tlačítka **Vytvořit**.

### <a name="add-apple-configurator-serial-numbers"></a>Přidání sériových čísel Apple Configuratoru

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Tento postup použijte, pokud chcete přidat sériová čísla k Intune, když chcete [zaregistrovat zařízení se systémem iOS vlastněná firmou pomocí Apple Configuratoru s Průvodcem nastavením](apple-configurator-setup-assistant-enroll-ios.md). Sériová čísla můžete přidávat postupně nebo můžete nahrát soubor se sériovými čísly ve formátu CSV. K přidaným číslům můžete přiřadit profil. Profil obsahuje specifická nastavení správy, která chcete použít u zařízení.

Další metody registrace zařízení s iOSem jsou popsané v článku [Volba způsobu registrace zařízení s iOSem v Intune](enrollment-method-choose-ios.md).

**Přidání sériových čísel Apple Configuratoru k Intune**

1. Vytvořte seznam hodnot oddělených čárkami se dvěma sloupci (.csv) bez záhlaví. Do levého sloupce přidejte identifikátor IMEI a v pravém sloupci uveďte podrobnosti. Aktuálně je maximální počet řádků v seznamu 500. V textovém editoru vypadá seznam CSV přibližně takto:

    F7TLWCLBX196,podrobnosti o zařízení</br>
    DLXQPCWVGHMJ,podrobnosti o zařízení

2. Na portálu Azure Portal zvolte **Registrace zařízení** a pak zvolte **Registrace Apple**.
3. V části **Spravovat nastavení registrace Apple Configuratoru** vyberte **Sériová čísla Apple Configuratoru**.
4. V okně **Sériová čísla Apple Configuratoru** vyberte **Přidat**.
5. V okně **Přidat sériová čísla** vyberte profil, který chcete použít pro sériová čísla při importu. Pokud importujete soubor s novými podrobnostmi, které mají přepsat ty stávající, vyberte Přepište podrobnosti u existujících identifikátorů a nové podrobnosti nahradí stávající.
6. Přejděte k souboru .csv se sériovými čísly a vyberte **Přidat**.

### <a name="assign-a-profile-to-specific-serial-numbers"></a>Přiřazení čísel ke specifickým sériovým číslům

Intune umožňuje přiřadit profily ze dvou různých míst na portálu Azure Portal. Můžete přiřadit profil Apple Configuratoru, nebo můžete přiřadit zařízení.

#### <a name="assign-by-devices"></a>Přiřazení podle zařízení
1. Na portálu Intune zvolte **Registrace zařízení** a pak zvolte **Registrace Apple**.
3. V okně **Zařízení Apple Configuratoru** vyberte sériová čísla, ke kterým chcete přiřadit profil, a potom vyberte **Přiřadit profil**.
4. V okně **Přiřadit profil** vyberte profil, který chcete přiřadit, a potom klepněte na **Přiřadit**.

#### <a name="assign-by-profiles"></a>Přiřazení podle profilů
1. Na portálu Intune zvolte **Registrace zařízení** a pak zvolte **Registrace Apple**.
2. Zvolte **Profily AC**a vyberte profil, ke kterému chcete přiřadit sériová čísla.
3. V okně profilu vyberte **Sériová čísla** > **Přiřadit**.
4. Vyberte sériová čísla, která chcete přiřadit k profilu, a pak zvolte tlačítko **Přiřadit**.

### <a name="export-the-profile-to-ios-devices"></a>Export profilu do zařízení s iOSem
Po vytvoření profilu a přiřazení sériových čísel musíte exportovat profil z Intune, a to buď jako adresu URL, nebo jako soubor ve formátu popsaném níže. Pak ho ručně naimportujete do programu Apple Configurator na Macu a potom ho program Apple Configurator nasadí do zařízení.

1. Na portálu Intune zvolte v okně **Registrační profily Apple Configuratoru** profil, který chcete exportovat.
2. V okně profilu vyberte **Exportovat profil**.
3. Zkopírujete adresu URL profilu do [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) s připojeným zařízením s iOSem. Později URL odešlete do Apple Configuratoru, abyste definovali profil Intune používaný zařízeními s iOSem.

  V následujícím postupu odešlete tuto adresu URL profilu do služby Apple pomocí Apple Configuratoru, abyste definovali profil Intune používaný zařízeními s iOSem.
4. Nahrajte tuto adresu URL profilu do služby Apple pomocí Apple Configuratoru, abyste definovali profil Intune používaný zařízeními s iOSem.
 1.  Na počítači Mac otevřete **Apple Configurator 2**. V panelu nabídek vyberte **Apple Configurator 2** a potom **Předvolby**.
  > [!WARNING]
  > V průběhu registrace bude v zařízeních obnovená tovární konfigurace. Doporučuje se zařízení resetovat a zapnout ho. Zařízení by při připojení měla mít nastavenou **úvodní obrazovku**.
  2. V podokně **předvoleb** vyberte **Servery** a znaménkem plus (+) spusťte průvodce serveru MDM. Vyberte **Další**.
  3. V části registrace Průvodce nastavením zařízení s iOSem v Microsoft Intune zadejte **název hostitele nebo adresu URL** a **adresu URL pro registraci** serveru MDM. Jako adresu URL pro registraci zadejte adresu URL profilu pro registraci exportovanou z Intune. Vyberte **Další**.  

    Upozornění na neověřenou adresu URL serveru můžete ignorovat. Vyberte **Další** a pokračujte až do konce průvodce.
  4.  Mobilní zařízení s iOSem připojte kabelem USB k počítači Mac.
  > [!WARNING]
  > V průběhu registrace bude v zařízeních obnovená tovární konfigurace. Doporučuje se zařízení resetovat a zapnout ho. Při spuštění pomocníka s nastavením by zařízení měla mít nastavenou **úvodní obrazovku**.
  5.  Zvolte **Prepare** (Připravit). V podokně **Prepare iOS Device** (Připravit zařízení s iOSem) vyberte **Manual** (Ručně) a pak zvolte **Next** (Další).
  6. V podokně **Enroll in MDM Server** (Registrovat na serveru MDM) vyberte název vytvořeného serveru a zvolte **Next** (Další).
  7. V podokně **Supervise Devices** (Dohled nad zařízeními) vyberte úroveň dohledu a pak zvolte **Next** (Další).
  8. V podokně **Create an Organization** (Vytvořit organizaci) zvolte **organizaci** nebo vytvořte novou organizaci a pak zvolte **Next** (Další).
  9. V podokně **Configure iOS Setup Assistant** (Konfigurovat Pomocníka s nastavením iOSu) vyberte kroky, které se budou zobrazovat uživateli, a pak zvolte **Prepare** (Připravit). Pokud se zobrazí výzva, proveďte ověření, aby se aktualizovalo nastavení důvěry.  
  10. Až se dokončí příprava zařízení s iOSem, můžete odpojit kabel USB.  
6.  **Distribuujte zařízení.**
    Zařízení jsou připravená na registraci ve společnosti. Vypněte zařízení a rozdejte je uživatelům. Když uživatelé zařízení zapnou, spustí se pomocník s nastavením.

## <a name="direct-enrollment"></a>Přímá registrace
Při přímé registraci zařízení s iOSem pomocí Apple Configuratoru můžete zařízení zaregistrovat i bez získání jeho sériového čísla. Můžete také zařízení pro potřeby identifikace pojmenovat před tím, než Intune zachytí název zařízení během registrace. U zařízení zaregistrovaných přímo není podporovaná aplikace Portál společnosti. Tyto pokyny předpokládají, že používáte Apple Configurator 2.0 na počítači Mac.

1. Na portálu Intune zvolte **Registrace zařízení**, **Registrace Apple** a pak zvolte **Profily AC**.
2. V okně **Registrační profily Apple Configuratoru** vyberte **Vytvořit**.
3. V okně **Vytvořit registrační profil** zadejte název a popis profilu.
4. V části **Přidružení uživatele** zvolte **Zaregistrovat bez přidružení uživatele**, aby zařízení nebylo přidružené k uživateli. Toto spřažení použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, které vyžadují přidruženého uživatele (včetně aplikace Portál společnosti používané k instalaci obchodních aplikací), nebudou fungovat.
5. Uložte profil pomocí tlačítka **Vytvořit**.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Export profilu jako souboru .mobileconfig do zařízení s iOSem

1. V okně **Exportovat profil** stáhněte registrační profil do [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), aby se dal přímo připojenému zařízení s iOSem nabídnout jako profil pro správu. Při této metodě není nutné resetovat zařízení do továrního nastavení.
2. Připravte zařízení pomocí Apple Configuratoru podle následujících kroků.
  1. Na počítači Mac otevřete Apple Configurator 2.0.
  2. Zařízení s iOSem připojte k počítači Mac pomocí kabelu USB. Zavřete Fotky, iTunes a další aplikace, které se otevřou při zjištění zařízení.
  3. V Apple Configuratoru zvolte připojené zařízení s iOSem a potom zvolte tlačítko **Přidat**. V rozevíracím seznamu se zobrazí možnosti, které se dají přidat do zařízení. Vyberte **Profily**.
  4. Pomocí nástroje pro výběr souborů vyberte soubor .mobileconfig, který jste exportovali z Intune, a zvolte **Přidat**. Profil se přidá do zařízení. Pokud má zařízení nastavenou možnost Bez dohledu, instalace bude vyžadovat přijetí na zařízení.
3. Nainstalujte profil na zařízení s iOSem podle následujících kroků. Je potřeba, aby už byl v zařízení dokončený Pomocník s nastavením a aby bylo připravené k použití. Pokud registrace zahrnuje nasazení aplikací, zařízení by mělo mít nastavené Apple ID, protože při nasazení aplikace bude potřeba přihlásit se do obchodu App Store pomocí Apple ID.
   1. Odemkněte zařízení s iOSem.
   2. V dialogovém okně **Nainstalovat profil** pro **Profil správy** zvolte **Instalovat**.
   3. V případě potřeby zadejte heslo zařízení nebo Apple ID.
   4. Potvrďte **upozornění** a zvolte **Instalovat**.
   5. Potvrďte **vzdálené upozornění** a zvolte **Důvěřovat**.
   6. Jakmile okno **Profil nainstalován** potvrdí, že se profil nainstaloval, zvolte **Hotovo**.

    4. Na zařízení s iOSem otevřete **Nastavení** a přejděte na **Obecné** > **Správa zařízení** > **Profil pro správu**. Potvrďte, že je zde instalace profilu uvedená, a zkontrolujte omezení zásad iOS a nainstalované aplikace. Zobrazení omezení vyplývajících ze zásad a aplikací na zařízení může trvat až 10 minut.

    5. Distribuujte zařízení. Zařízení s iOSem je teď zaregistrované v Intune a spravované.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Jak uživatelé instalují a používají aplikaci Portál společnosti na svých zařízeních

Zařízení nakonfigurovaná s přidružením uživatele umožňují instalaci a spuštění aplikace Portál společnosti, která slouží ke stahování aplikací a správě zařízení. Když uživatelé dostanou zařízení, musí provést další kroky popsané níže, aby dokončili postup Pomocníka s nastavením a nainstalovali aplikaci Portál společnosti.
