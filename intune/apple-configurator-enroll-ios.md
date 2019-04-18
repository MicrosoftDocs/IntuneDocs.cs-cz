---
title: registrace zařízení s Iosem – Apple Configurator – Pomocník pro instalaci
titleSuffix: Microsoft Intune
description: Přečtěte si, jak jde pomocí Apple Configuratoru registrovat zařízení s iOSem vlastněná společností s využitím Pomocníka s nastavením.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 671e4d76-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: ab4ecfe3f407082d0a51910b35ad8ac8d6724f9c
ms.sourcegitcommit: 47eb67df69f237121f5197b2ac904a177aab5400
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59671879"
---
# <a name="set-up-ios-device-enrollment-with-apple-configurator"></a>Nastavení registrace zařízení s Iosem pomocí Apple Configuratoru

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune podporuje registraci zařízení s iOSem pomocí [Apple Configuratoru](https://itunes.apple.com/app/apple-configurator-2/id1037126344) spuštěných na počítačích Mac. Registrace pomocí Apple Configuratoru vyžaduje, abyste každé zařízení s iOSem připojili prostřednictvím USB k počítači Mac a nastavili registraci pro podniky. Zařízení můžete do služby Intune registrovat pomocí Apple Configuratoru dvěma způsoby:
- **Registrace Pomocníka s nastavením** – Vymaže zařízení a připraví ho k registraci Pomocníka s nastavením.
- **Přímá registrace** – Nevymaže zařízení a zaregistruje ho pomocí nastavení iOSu. Tato metoda podporuje jenom **zařízení bez přidružení uživatele**.

Metoda registrace pomocí Apple Configuratoru se nedá použít se [Správcem registrace zařízení](device-enrollment-manager-enroll.md).

## <a name="prerequisites"></a>Požadavky

- Fyzický přístup k zařízením s iOSem
- [Nastavení autority pro správu mobilních zařízení (MDM)](mdm-authority-set.md)
- [Certifikát Apple MDM push certificate](apple-mdm-push-certificate-get.md)
- Sériová čísla zařízení (jenom u registrace Pomocníka s nastavením)
- Propojovací kabely USB
- Počítač s macOS s [Apple Configuratorem 2.0](https://itunes.apple.com/app/apple-configurator-2/id1037126344)

## <a name="create-an-apple-configurator-profile-for-devices"></a>Vytvoření profilu Apple Configuratoru pro zařízení

Profil registrace zařízení definuje nastavení, která se během registrace použijí. Tato nastavení se použijí jenom jednou. Tímto postupem vytvoříte profil k registraci zařízení s iOSem pomocí Apple Configuratoru.

1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Apple Configurator** > **Profily** > **Vytvořit**.

    ![Vytvoření profilu pro Apple Configurator](./media/apple-configurator-enroll-ios/apple-config-create-profile.png)

2. V části **Vytvořit registrační profil** zadejte **Název** a **Popis** profilu pro účely správy. Uživatelům se tyto údaje nezobrazí. Pole Název můžete využít k vytvoření dynamické skupiny v Azure Active Directory. Název profilu použijte k definování parametru enrollmentProfileName, který slouží k přiřazení zařízení s tímto registračním profilem. Přečtěte si další informace o dynamických skupinách Azure Active Directory.

    ![Snímek obrazovky Vytvořit profil s vybranou volbou Zaregistrovat s přidružením uživatele](./media/apple-configurator-profile-create.png)

3. V části **Přidružení uživatele** zvolte, jestli se zařízení s tímto profilem musí registrovat s přiřazeným uživatelem nebo bez něj.

    - **Zaregistrovat s přidružením uživatele** – Tuto možnost zvolte pro zařízení, která patří uživatelům a chtějí pro služby, jako je instalace aplikací, používat portál společnosti. Zařízení musí mít přidruženého uživatele (pomocí Průvodce nastavením), aby mohlo dostat přístup k firemním datům a e-mailu. Tato možnost je podporovaná jenom pro registraci Pomocníka s nastavením. Přidružení uživatelů vyžaduje [koncový bod WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints). [Další informace](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Zaregistrovat bez přidružení uživatele** – Tuto možnost zvolte pro zařízení nespojená s jedním uživatelem. Použijte ji pro zařízení určená k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, které vyžadují přidruženého uživatele (včetně aplikace Portál společnosti používané k instalaci obchodních aplikací), nebudou fungovat. Vyžaduje se pro přímou registraci.

4. Pokud jste zvolili **Zaregistrovat s přidružením uživatele**, máte možnost povolit, aby se uživatelé ověřovali pomocí portálu společnosti místo v Průvodci nastavením společnosti Apple.

    > [!NOTE]
    > Pokud chcete provést některou z následujících akcí, nastavte možnost **ověření na Portálu společnosti místo v Průvodci nastavením Applu** na **Ano**.
    >    - Použít vícefaktorové ověřování.
    >    - Zobrazit výzvu uživatelům, pokud při prvním přihlášení potřebují změnit heslo.
    >    - Zobrazit výzvu uživatelům, aby při registraci resetovali neplatná hesla.
    >
    > Tato možnost není podporovaná, pokud se k ověření použije Průvodce nastavením společnosti Apple.


6. Uložte profil pomocí tlačítka **Vytvořit**.

## <a name="setup-assistant-enrollment"></a>Registrace Pomocníka s nastavením

### <a name="add-apple-configurator-serial-numbers"></a>Přidání sériových čísel Apple Configuratoru

1. Vytvořte seznam hodnot oddělených čárkami se dvěma sloupci (.csv) bez záhlaví. Do levého sloupce přidejte sériové číslo a v pravém sloupci uveďte podrobnosti. Aktuálně je maximální počet řádků v seznamu 5 000. V textovém editoru vypadá seznam .csv takto:

    F7TLWCLBX196,podrobnosti o zařízení</br>
    DLXQPCWVGHMJ,podrobnosti o zařízení

   Přečtete si, [jak zjistit sériové číslo zařízení s iOSem](https://support.apple.com/HT204073).
2. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Apple Configurator** > **Zařízení** > **Přidat**.

5. Vyberte **profil registrace**, jehož prostřednictvím použijete importovaná sériová čísla. Pokud chcete, aby podrobnosti nového sériového čísla přepsaly všechny existující podrobnosti, zvolte **Přepište podrobnosti u existujících identifikátorů**.
6. V části **Importovat zařízení** přejděte k souboru CSV se sériovými čísly a vyberte **Přidat**.

### <a name="reassign-a-profile-to-device-serial-numbers"></a>Opětovné přiřazení profilu k sériovým číslům zařízení

Registrační profil můžete přiřadit při importu sériových čísel zařízení s iOSem pro registraci pomocí Apple Configuratoru. Profily můžete také přiřazovat ze dvou míst na portálu Azure Portal:
- **Zařízení Apple Configuratoru**
- **Profily AC**

#### <a name="assign-from-apple-configurator-devices"></a>Přiřazení v části Zařízení Apple Configuratoru
1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Apple Configurator** > **Zařízení** > zvolte sériová čísla > **Přiřadit profil**.
2. V části **Přiřadit profil** zvolte **nový profil**, který chcete přiřadit, a pak zvolte **Přiřadit**.

#### <a name="assign-from-profiles"></a>Přiřazení z profilů
1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Apple Configurator** > **Profily** > zvolte profil.
2. V profilu zvolte **Přiřazená zařízení** a pak **Přiřadit**.
3. Pomocí filtru vyhledejte sériová čísla zařízení, která chcete k profilu přiřadit, vyberte zařízení a zvolte **Přiřadit**.

### <a name="export-the-profile"></a>Export profilu
Po vytvoření profilu a přiřazení sériových čísel je potřeba profil exportovat z Intune jako adresu URL. Tu pak importujete do Apple Configuratoru na počítači Mac, odkud můžete profil nasadit do zařízení.

1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Apple Configurator** > **Profily** > zvolte profil, který chcete exportovat.
2. V profilu vyberte **Exportovat profil**.
3. Zkopírujte **adresu URL profilu**. Můžete ji potom přidat do Apple Configuratoru a definovat tak profil Intune používaný zařízeními s iOSem.

   V dalším kroku tento profil importujete do Apple Configuratoru a opět definujete profil Intune používaný zařízeními s iOSem.

### <a name="enroll-devices-with-setup-assistant"></a>Registrace zařízení s využitím Pomocníka s nastavením

1. Na počítači Mac otevřete **Apple Configurator 2**. V panelu nabídek vyberte **Apple Configurator 2** a potom **Předvolby**.
    > [!WARNING]
    > V průběhu registrace se v zařízeních obnoví tovární konfigurace. Doporučuje se zařízení resetovat a zapnout ho. Zařízení by při připojení měla mít nastavenou **úvodní obrazovku**.
    > Zařízení byl již zaregistrován pomocí Apple ID účtu, musí se odstranit zařízení ze serveru služby iCloud Apple před zahájením procesu registrace. Chyba výzvy se zobrazí jako "Nepodařilo se aktivovat [název]".

2. V podokně **předvoleb** vyberte **Servery** a znaménkem plus (+) spusťte průvodce serveru MDM. Zvolte **Další**.
3. V části registrace Průvodce nastavením zařízení s iOSem v Microsoft Intune zadejte **název hostitele nebo adresu URL** a **adresu URL pro registraci** serveru MDM. Jako adresu URL pro registraci zadejte adresu URL profilu pro registraci exportovanou z Intune. Zvolte **Další**.  
    Upozornění na neověřenou adresu URL serveru můžete ignorovat. Vyberte **Další** a pokračujte až do konce průvodce.
4.  Mobilní zařízení s iOSem připojte kabelem USB k počítači Mac.
5.  Vyberte zařízení s iOSem, která chcete spravovat, a pak zvolte **Prepare** (Spravovat). V podokně **Prepare iOS Device** (Připravit zařízení s iOSem) vyberte **Manual** (Ručně) a pak zvolte **Next** (Další).
6. V podokně **Enroll in MDM Server** (Registrovat na serveru MDM) vyberte název vytvořeného serveru a zvolte **Next** (Další).
7. V podokně **Supervise Devices** (Dohled nad zařízeními) vyberte úroveň dohledu a pak zvolte **Next** (Další).
8. V podokně **Create an Organization** (Vytvořit organizaci) zvolte **organizaci** nebo vytvořte novou organizaci a pak zvolte **Next** (Další).
9. V podokně **Configure iOS Setup Assistant** (Konfigurovat Pomocníka s nastavením iOSu) vyberte kroky, které se budou zobrazovat uživateli, a pak zvolte **Prepare** (Připravit). Pokud se zobrazí výzva, proveďte ověření, aby se aktualizovalo nastavení důvěry.  
10. Až se dokončí příprava zařízení s iOSem, můžete odpojit kabel USB.  

### <a name="distribute-devices"></a>Distribuujte zařízení.
Zařízení jsou připravená na registraci ve společnosti. Vypněte zařízení a rozdejte je uživatelům. Když uživatelé zařízení zapnou, spustí se Pomocník s nastavením.

Po převzetí zařízení musí uživatelé projít postupem Pomocníka s nastavením. Zařízení nakonfigurovaná s přidružením uživatele umožňují instalaci a spuštění aplikace Portál společnosti, která slouží ke stahování aplikací a správě zařízení.

## <a name="direct-enrollment"></a>Přímá registrace
Při přímé registraci zařízení s iOSem pomocí Apple Configuratoru můžete zařízení zaregistrovat i bez získání jeho sériového čísla. Můžete také zařízení pro potřeby identifikace pojmenovat před tím, než Intune zachytí název zařízení během registrace. U zařízení zaregistrovaných přímo není podporovaná aplikace Portál společnosti. Pomocí této metody se zařízení nevymaže.

Aplikace, které vyžadují přidruženého uživatele (včetně aplikace Portál společnosti používané k instalaci obchodních aplikací), se nedají nainstalovat.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Export profilu jako souboru .mobileconfig do zařízení s iOSem

1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Apple Configurator** > **Profily** > zvolte profil, který chcete exportovat > **Exportovat profil**.
2. V části **Přímá registrace** zvolte **Stáhnout profil** a soubor uložte. Soubor registračního profilu je platný jenom po dobu dvou týdnů, po které ho bude nutné znovu vytvořit.
3. Soubor přeneste do počítače Mac se spuštěným [Apple Configuratorem](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12). Může se tak odeslat přímo jako profil správy do zařízení s iOSem.
4. Připravte zařízení pomocí Apple Configuratoru podle následujících kroků:
    1. Na počítači Mac otevřete Apple Configurator 2.0.
    2. Zařízení s iOSem připojte k počítači Mac pomocí kabelu USB. Zavřete Fotky, iTunes a další aplikace, které se otevřou při zjištění zařízení.
    3. V Apple Configuratoru zvolte připojené zařízení s iOSem a potom zvolte tlačítko **Přidat**. V rozevíracím seznamu se zobrazí možnosti, které se dají přidat do zařízení. Vyberte **Profily**.

        ![Snímek obrazovky Exportovat profil pro registraci Pomocníka s nastavením se zvýrazněnou adresou URL profilu](./media/ios-apple-configurator-add-profile.png)

    4. Pomocí nástroje pro výběr souborů vyberte soubor .mobileconfig, který jste exportovali z Intune, a zvolte **Přidat**. Profil se přidá do zařízení. Pokud má zařízení nastavenou možnost Bez dohledu, vyžaduje instalace přijetí na zařízení.
5. Nainstalujte profil na zařízení s iOSem podle následujících kroků. Je potřeba, aby už byl v zařízení dokončený Pomocník s nastavením a aby bylo připravené k použití. Pokud registrace zahrnuje nasazení aplikací, zařízení by mělo mít nastavené Apple ID, protože při nasazení aplikace bude potřeba přihlásit se do App Storu pomocí Apple ID.
    1. Odemkněte zařízení s iOSem.
    2. V dialogovém okně **Nainstalovat profil** pro **Profil správy** zvolte **Instalovat**.
    3. V případě potřeby zadejte heslo zařízení nebo Apple ID.
    4. Potvrďte **upozornění** a zvolte **Instalovat**.
    5. Potvrďte **vzdálené upozornění** a zvolte **Důvěřovat**.
    6. Jakmile okno **Profil nainstalován** potvrdí, že se profil nainstaloval, zvolte **Hotovo**.

6. Na zařízení s iOSem otevřete **Nastavení** a přejděte na **Obecné** > **Správa zařízení** > **Profil pro správu**. Potvrďte, že je zde instalace profilu uvedená, a zkontrolujte omezení zásad iOS a nainstalované aplikace. Zobrazení omezení vyplývajících ze zásad a aplikací na zařízení může trvat až 10 minut.

7. Distribuujte zařízení. Zařízení s iOSem je teď zaregistrované v Intune a spravované.





