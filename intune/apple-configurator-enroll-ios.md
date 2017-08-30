---
title: "Registrace zařízení s iOSem – Apple Configurator – Pomocník s nastavením"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak jde pomocí Apple Configuratoru registrovat zařízení s iOSem vlastněná společností s využitím Pomocníka s nastavením.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fb3ea2fbd8d710bcb8eccac9b4512ce8ba941fc2
ms.sourcegitcommit: 7674efb7de5ad54390801165364f5d9c58ccaf84
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2017
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>Registrace zařízení s iOSem pomocí Apple Configuratoru

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune podporuje registraci zařízení s iOSem pomocí [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) spuštěných na počítačích Mac. Registrace pomocí Apple Configuratoru vyžaduje, abyste každé zařízení s iOSem připojili prostřednictvím USB k počítači Mac a nastavili registraci pro podniky. Zařízení můžete do služby Intune registrovat pomocí Apple Configuratoru dvěma způsoby:
- **Registrace v průvodci nastavením** – Obnoví tovární nastavení zařízení a připraví ho k registraci v průvodci nastavením.
- **Přímá registrace** – Neobnoví tovární nastavení zařízení a zaregistruje ho pomoci nastavení iOS. Tato metoda podporuje jenom **zařízení bez přidružení uživatele**.

Metoda registrace pomocí Apple Configuratoru se nedá použít se [Správcem registrace zařízení](device-enrollment-manager-enroll.md).

## <a name="prerequisites"></a>Předpoklady

- Fyzický přístup k zařízením s iOSem
- [Nastavení autority pro správu mobilních zařízení (MDM)](mdm-authority-set.md)
- [Certifikát Apple MDM push certificate](apple-mdm-push-certificate-get.md)
- Sériová čísla zařízení (jenom u registrace Pomocníka s nastavením)
- Propojovací kabely USB
- Počítač Mac s [Apple Configuratorem 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)

## <a name="create-an-apple-configurator-profile-for-devices"></a>Vytvoření profilu Apple Configuratoru pro zařízení

Profil registrace zařízení definuje nastavení, která se během registrace použijí. Tato nastavení se použijí jenom jednou. Tímto postupem vytvoříte profil k registraci zařízení s iOSem pomocí Apple Configuratoru.

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. Zvolte **Registrace zařízení** > **Registrace Apple**.
4. V části **Spravovat nastavení registrace Apple Configuratoru** vyberte **Profily AC**.
5. V okně **Registrační profily Apple Configuratoru** vyberte **Vytvořit**.
6. Zadejte **Název** a **Popis** profilu pro účely správy. Uživatelům se tyto údaje nezobrazí. Pole Název můžete využít k vytvoření dynamické skupiny v Azure Active Directory. Název profilu použijte k definování parametru enrollmentProfileName, který slouží k přiřazení zařízení s tímto registračním profilem. Přečtěte si další informace o dynamických skupinách Azure Active Directory.

  ![Snímek obrazovky Vytvořit profil s vybranou volbou Zaregistrovat s přidružením uživatele](./media/apple-configurator-profile-create.png)

7. Určete **Přidružení uživatele**:
   - **Zaregistrovat s přidružením uživatele** – Zařízení musí mít přidruženého uživatele (pomocí Průvodce nastavením), aby mohlo dostat přístup k firemním datům a e-mailu. Přidružení uživatele se vyžaduje u spravovaných zařízení, která patří konkrétním uživatelům a potřebují používat portál společnosti kvůli službám, jako je instalace aplikací.
   - **Zaregistrovat bez přidružení uživatele** – K zařízení není přidružený žádný uživatel. Toto spřažení použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, které vyžadují přidruženého uživatele (včetně aplikace Portál společnosti používané k instalaci obchodních aplikací), nebudou fungovat. Vyžaduje se pro přímou registraci.

6. Uložte profil pomocí tlačítka **Vytvořit**.

## <a name="setup-assistant-enrollment"></a>Registrace Pomocníka s nastavením

### <a name="add-apple-configurator-serial-numbers"></a>Přidání sériových čísel Apple Configuratoru

**Přidání sériových čísel Apple Configuratoru k Intune**

1. Vytvořte seznam hodnot oddělených čárkami se dvěma sloupci (.csv) bez záhlaví. Do levého sloupce přidejte sériové číslo a v pravém sloupci uveďte podrobnosti. Aktuálně je maximální počet řádků v seznamu 500. V textovém editoru vypadá seznam CSV přibližně takto:

    F7TLWCLBX196,podrobnosti o zařízení</br>
    DLXQPCWVGHMJ,podrobnosti o zařízení

   Přečtete si, [jak zjistit sériové číslo zařízení s iOSem](https://support.apple.com/HT204073).
2. V Intune na portálu Azure Portal zvolte **Registrace zařízení** a pak **Registrace Apple**.
3. V části **Spravovat nastavení registrace Apple Configuratoru** vyberte **Zařízení Apple Configuratoru**.
4. Vyberte **Přidat**.
5. Vyberte **profil registrace**, jehož prostřednictvím použijete importovaná sériová čísla. Pokud importujete soubor s novými podrobnostmi, kterými se přepíšou ty stávající, vyberte nastavení **Přepište podrobnosti u existujících identifikátorů**.
6. Přejděte k souboru CSV se sériovými čísly a vyberte **Přidat**.

### <a name="reassign-a-profile-to-device-serial-numbers"></a>Opětovné přiřazení profilu k sériovým číslům zařízení

Profil registrace se přiřazuje při importu sériových čísel zařízení s iOSem pomocí Apple Configuratoru. Intune navíc umožňuje přiřazovat profily ze dvou míst na portálu Azure Portal:
- **Zařízení Apple Configuratoru**
- **Profily AC**

#### <a name="assign-from-apple-configurator-devices"></a>Přiřazení v části Zařízení Apple Configuratoru
1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** a pak **Registrace Apple**.
3. V okně **Zařízení Apple Configuratoru** vyberte sériová čísla, ke kterým chcete přiřadit profil, a potom vyberte **Přiřadit profil**.
4. V okně **Přiřadit profil** vyberte **nový profil**, který chcete přiřadit, a potom zvolte **Přiřadit**.

#### <a name="assign-from-profiles"></a>Přiřazení z profilů
1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** a pak **Registrace Apple**.
2. Zvolte **Profily AC** a vyberte profil, který chcete sériovým číslům přiřadit.
3. V okně profilu zvolte **Přiřazená zařízení**a potom **Přiřadit**.
4. Pomocí filtru vyhledejte sériová čísla zařízení, která chcete k profilu přiřadit, vyberte zařízení a zvolte **Přiřadit**.

### <a name="export-the-profile"></a>Export profilu
Po vytvoření profilu a přiřazení sériových čísel je potřeba profil exportovat z Intune jako adresu URL. Tu pak importujete do Apple Configuratoru na počítači Mac, odkud můžete profil nasadit do zařízení.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > Registrace Apple** > **Profily AC** a vyberte profil, který chcete exportovat.
2. V okně profilu vyberte **Exportovat profil**.
3. Zkopírujte adresu URL profilu. Potom ji můžete přidat do Apple Configuratoru a definovat tak profil Intune používaný zařízeními s iOSem.

  V dalším kroku tento profil importujete do Apple Configuratoru a opět definujete profil Intune používaný zařízeními s iOSem.

### <a name="enroll-devices-with-setup-assistant"></a>Registrace zařízení s využitím Pomocníka s nastavením

1.  Na počítači Mac otevřete **Apple Configurator 2**. V panelu nabídek vyberte **Apple Configurator 2** a potom **Předvolby**.
  > [!WARNING]
  > V průběhu registrace se v zařízeních obnoví tovární konfigurace. Doporučuje se zařízení resetovat a zapnout ho. Zařízení by při připojení měla mít nastavenou **úvodní obrazovku**.

2. V podokně **předvoleb** vyberte **Servery** a znaménkem plus (+) spusťte průvodce serveru MDM. Vyberte **Další**.
3. V části registrace Průvodce nastavením zařízení s iOSem v Microsoft Intune zadejte **název hostitele nebo adresu URL** a **adresu URL pro registraci** serveru MDM. Jako adresu URL pro registraci zadejte adresu URL profilu pro registraci exportovanou z Intune. Vyberte **Další**.  

  Upozornění na neověřenou adresu URL serveru můžete ignorovat. Vyberte **Další** a pokračujte až do konce průvodce.
4.  Mobilní zařízení s iOSem připojte kabelem USB k počítači Mac.
5.  Zvolte **Prepare** (Připravit). V podokně **Prepare iOS Device** (Připravit zařízení s iOSem) vyberte **Manual** (Ručně) a pak zvolte **Next** (Další).
6. V podokně **Enroll in MDM Server** (Registrovat na serveru MDM) vyberte název vytvořeného serveru a zvolte **Next** (Další).
7. V podokně **Supervise Devices** (Dohled nad zařízeními) vyberte úroveň dohledu a pak zvolte **Next** (Další).
8. V podokně **Create an Organization** (Vytvořit organizaci) zvolte **organizaci** nebo vytvořte novou organizaci a pak zvolte **Next** (Další).
9. V podokně **Configure iOS Setup Assistant** (Konfigurovat Pomocníka s nastavením iOSu) vyberte kroky, které se budou zobrazovat uživateli, a pak zvolte **Prepare** (Připravit). Pokud se zobrazí výzva, proveďte ověření, aby se aktualizovalo nastavení důvěry.  
10. Až se dokončí příprava zařízení s iOSem, můžete odpojit kabel USB.  

### <a name="distribute-devices"></a>Distribuujte zařízení.
Zařízení jsou připravená na registraci ve společnosti. Vypněte zařízení a rozdejte je uživatelům. Když uživatelé zařízení zapnou, spustí se Pomocník s nastavením.

Po převzetí zařízení musí uživatelé projít postupem Pomocníka s nastavením. Zařízení nakonfigurovaná s přidružením uživatele umožňují instalaci a spuštění aplikace Portál společnosti, která slouží ke stahování aplikací a správě zařízení.

## <a name="direct-enrollment"></a>Přímá registrace
Při přímé registraci zařízení s iOSem pomocí Apple Configuratoru můžete zařízení zaregistrovat i bez získání jeho sériového čísla. Můžete také zařízení pro potřeby identifikace pojmenovat před tím, než Intune zachytí název zařízení během registrace. U zařízení zaregistrovaných přímo není podporovaná aplikace Portál společnosti. Při této metodě není nutné resetovat zařízení do továrního nastavení.

Aplikace, které vyžadují přidruženého uživatele (včetně aplikace Portál společnosti používané k instalaci obchodních aplikací), se nedají nainstalovat.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Export profilu jako souboru .mobileconfig do zařízení s iOSem
1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Exportovat profil** stáhněte registrační profil do [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), aby se dal zařízením s iOSem nabídnout jako profil pro správu.
4. Připravte zařízení pomocí Apple Configuratoru podle následujících kroků.
  1. Na počítači Mac otevřete Apple Configurator 2.0.
  2. Zařízení s iOSem připojte k počítači Mac pomocí kabelu USB. Zavřete Fotky, iTunes a další aplikace, které se otevřou při zjištění zařízení.
  3. V Apple Configuratoru zvolte připojené zařízení s iOSem a potom zvolte tlačítko **Přidat**. V rozevíracím seznamu se zobrazí možnosti, které se dají přidat do zařízení. Vyberte **Profily**.
  4. Pomocí nástroje pro výběr souborů vyberte soubor .mobileconfig, který jste exportovali z Intune, a zvolte **Přidat**. Profil se přidá do zařízení. Pokud má zařízení nastavenou možnost Bez dohledu, vyžaduje instalace přijetí na zařízení.
5. Nainstalujte profil na zařízení s iOSem podle následujících kroků. Je potřeba, aby už byl v zařízení dokončený Pomocník s nastavením a aby bylo připravené k použití. Pokud registrace zahrnuje nasazení aplikací, zařízení by mělo mít nastavené Apple ID, protože při nasazení aplikace bude potřeba přihlásit se do obchodu App Store pomocí Apple ID.
   1. Odemkněte zařízení s iOSem.
   2. V dialogovém okně **Nainstalovat profil** pro **Profil správy** zvolte **Instalovat**.
   3. V případě potřeby zadejte heslo zařízení nebo Apple ID.
   4. Potvrďte **upozornění** a zvolte **Instalovat**.
   5. Potvrďte **vzdálené upozornění** a zvolte **Důvěřovat**.
   6. Jakmile okno **Profil nainstalován** potvrdí, že se profil nainstaloval, zvolte **Hotovo**.

6. Na zařízení s iOSem otevřete **Nastavení** a přejděte na **Obecné** > **Správa zařízení** > **Profil pro správu**. Potvrďte, že je zde instalace profilu uvedená, a zkontrolujte omezení zásad iOS a nainstalované aplikace. Zobrazení omezení vyplývajících ze zásad a aplikací na zařízení může trvat až 10 minut.

7. Distribuujte zařízení. Zařízení s iOSem je teď zaregistrované v Intune a spravované.