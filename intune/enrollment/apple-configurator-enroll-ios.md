---
title: registrace zařízení s iOS – Apple Configuratoru – Pomocník s nastavením
titleSuffix: Microsoft Intune
description: Naučte se používat Apple Configuratoru k registraci zařízení s iOS vlastněných společností pomocí Pomocníka s nastavením.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 671e4d76-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: a1c2acc2ebe5528e30c344a31c9551ac64bdf3ca
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306781"
---
# <a name="set-up-ios-device-enrollment-with-apple-configurator"></a>Nastavení registrace zařízení s iOS pomocí Apple Configuratoru

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune podporuje registraci zařízení s iOS pomocí [Apple Configuratoru](https://itunes.apple.com/app/apple-configurator-2/id1037126344) spuštěného na počítači Mac. Registrace pomocí Apple Configuratoru vyžaduje, abyste každé zařízení s iOS připojili k počítači Mac pomocí USB a nastavili firemní registraci. Zařízení můžete do Intune zaregistrovat pomocí Apple Configuratoru dvěma způsoby:
- **Registrace Pomocníka s nastavením** – vymaže zařízení a připraví ho k registraci během pomocníka s nastavením.
- **Přímá registrace** – nevymaže zařízení a zaregistruje zařízení prostřednictvím nastavení iOS. Tato metoda podporuje jenom zařízení bez **přidružení uživatele**.

Metody registrace Apple Configuratoru se nedají použít se [správcem registrace zařízení](device-enrollment-manager-enroll.md).

## <a name="prerequisites"></a>Předpoklady

- Fyzický přístup k zařízením s iOS
- [Nastavit autoritu MDM](../fundamentals/mdm-authority-set.md)
- [Certifikát Apple MDM push Certificate](apple-mdm-push-certificate-get.md)
- Sériová čísla zařízení (jenom registrace Pomocníka s nastavením)
- USB připojení kabelů
- macOS počítač se spuštěným [Apple configuratoru 2,0](https://itunes.apple.com/app/apple-configurator-2/id1037126344)

## <a name="create-an-apple-configurator-profile-for-devices"></a>Vytvoření profilu Apple Configuratoru pro zařízení

Profil registrace zařízení definuje nastavení použitá během registrace. Tato nastavení se aplikují jenom jednou. Pomocí těchto kroků vytvořte registrační profil pro registraci zařízení se systémem iOS pomocí Apple Configuratoru.

1. V [Intune](https://aka.ms/intuneportal)vyberte **registrace zařízení** > **registrace Apple** > **Apple Configuratoru** > **profily** > **vytvořit**.

    ![Vytvořit profil pro Apple Configuratoru](./media/apple-configurator-enroll-ios/apple-config-create-profile.png)

2. V části **vytvořit registrační profil**zadejte **název** a **Popis** profilu pro účely správy. Uživatelé tyto podrobnosti nevidí. Pomocí tohoto pole název můžete vytvořit dynamickou skupinu v Azure Active Directory. Pomocí názvu profilu definujte parametr enrollmentProfileName pro přiřazení zařízení s tímto registračním profilem. Přečtěte si další informace o Azure Active Directory dynamických skupinách.

    ![Snímek obrazovky vytvořit profil s vybranou možnost zaregistrovat s přidružením uživatele](./media/apple-configurator-enroll-ios/apple-configurator-profile-create.png)

3. V případě **spřažení uživatele**vyberte, jestli se zařízení s tímto profilem musí zaregistrovat s přiřazeným uživatelem nebo bez něj.

    - **Zaregistrovat s přidružením uživatele** – tuto možnost vyberte pro zařízení, která patří uživatelům a chtějí používat portál společnosti pro služby, jako je instalace aplikací. Zařízení musí mít přidruženého uživatele s pomocníkem s nastavením a může pak přistupovat k firemním datům a e-mailu. Podporuje se jenom pro registraci pomocníka s nastavením. Přidružení uživatele vyžaduje [uživatelské jméno/Smíšený Koncový bod WS-Trust 1,3](https://technet.microsoft.com/library/adfs2-help-endpoints). [Další informace](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Zaregistrovat bez přidružení uživatele** – tuto možnost vyberte pro zařízení, která nejsou přidružená k jednomu uživateli. Toto použijte u zařízení, která provádějí úlohy bez přístupu k místním uživatelským datům. Aplikace, které vyžadují přidružení uživatele (včetně aplikace Portál společnosti používané pro instalaci obchodních aplikací), nebudou fungovat. Vyžaduje se pro přímou registraci.

     > [!NOTE]
     > Když je vybraná možnost **zaregistrovat s přidružením uživatele** , ujistěte se, že je zařízení přidružené k uživateli s průvodcem nastavením během prvních 24 hodin zaregistrovaných zařízení. Jinak může registrace selhat a k registraci zařízení bude potřeba obnovení továrního nastavení.

4. Pokud jste zvolili možnost **registrovat s přidružením uživatele**, máte možnost umožnit uživatelům ověřování pomocí portál společnosti namísto pomocníka s nastavením Apple.

    > [!NOTE]
    > Pokud chcete provést některou z následujících akcí, nastavte **ověřování pomocí portál společnosti namísto pomocníka s nastavením Apple** na **Ano**.
    >    - použití vícefaktorového ověřování
    >    - vyzvat uživatele, kteří při prvním přihlášení potřebují změnit heslo
    >    - vyzvat uživatele k resetování hesel s vypršenou platností během registrace
    >
    > Tyto nejsou podporované při ověřování pomocí Pomocníka s nastavením Apple.


6. Kliknutím na **vytvořit** uložte profil.

## <a name="setup-assistant-enrollment"></a>Registrace Pomocníka s nastavením

### <a name="add-apple-configurator-serial-numbers"></a>Přidat sériová čísla Apple Configuratoru

1. Vytvořte seznam hodnot oddělených čárkami (. csv) bez záhlaví. Přidejte sériové číslo do levého sloupce a podrobnosti do pravého sloupce. Aktuální maximum pro seznam je 5 000 řádků. V textovém editoru vypadá seznam. csv takto:

    F7TLWCLBX196, podrobnosti o zařízení</br>
    DLXQPCWVGHMJ, podrobnosti o zařízení

   Přečtěte si, [Jak najít sériové číslo zařízení s iOS](https://support.apple.com/HT204073).
2. V [Intune](https://aka.ms/intuneportal)vyberte **registrace zařízení** > **registrace Apple** > **Apple Configuratoru** > **zařízení** > **Přidat**.

5. Vyberte **registrační profil** , který se má použít pro sériová čísla, která importujete. Pokud chcete, aby se nové informace o sériovém číslu přepsaly na všechny existující podrobnosti, vyberte možnost **přepsat podrobnosti pro existující identifikátory**.
6. V části **importovat zařízení**přejděte k souboru CSV se sériovými čísly a vyberte **Přidat**.

### <a name="reassign-a-profile-to-device-serial-numbers"></a>Opětovné přiřazení profilu k sériovým číslům zařízení

Registrační profil můžete přiřadit při importu sériových čísel iOS pro registraci Apple Configuratoru. Profily můžete také přiřadit ze dvou míst v Azure Portal:
- **Zařízení Apple Configuratoru**
- **Profily AC**

#### <a name="assign-from-apple-configurator-devices"></a>Přiřazení ze zařízení Apple Configuratoru
1. V [Intune](https://aka.ms/intuneportal)vyberte **registrace zařízení** > **registrace Apple** > **Apple Configuratoru** >  > vyberte sériová čísla > **přiřadit profil**.
2. V části **přiřadit profil**vyberte **Nový profil** , který chcete přiřadit, a pak zvolte **přiřadit**.

#### <a name="assign-from-profiles"></a>Přiřazení z profilů
1. V [Intune](https://aka.ms/intuneportal)klikněte na **registrace zařízení** > **registrace Apple** > **Apple Configuratoru** > **profily** > vyberte profil.
2. V profilu zvolte **přiřazená zařízení**a pak zvolte **přiřadit**.
3. Filtr pro vyhledání sériových čísel zařízení, které chcete přiřadit k profilu, vyberte zařízení a pak zvolte **přiřadit**.

### <a name="export-the-profile"></a>Exportovat profil
Po vytvoření profilu a přiřazení sériových čísel musíte profil z Intune exportovat jako adresu URL. Pak ho naimportujete do Apple Configuratoru na Macu pro nasazení do zařízení.

1. V [Intune](https://aka.ms/intuneportal)vyberte **registrace zařízení** > **registrace Apple** > **Apple Configuratoru** >  > vyberte profil, který chcete exportovat.
2. V profilu vyberte **exportovat profil**.
3. Zkopírujte **adresu URL profilu**. Pak ho můžete přidat do Apple Configuratoru, abyste definovali profil Intune používaný zařízeními iOS.

   Při dalším importu tohoto profilu do Apple Configuratoru v následujícím postupu můžete definovat profil Intune používaný zařízeními iOS.

### <a name="enroll-devices-with-setup-assistant"></a>Registrace zařízení pomocí Pomocníka s nastavením

1. V počítači Mac otevřete **Apple Configuratoru 2**. V řádku nabídek zvolte **Apple Configuratoru 2**a pak zvolte **Předvolby**.
    > [!WARNING]
    > Během procesu registrace se v zařízeních obnoví tovární konfigurace. Osvědčeným postupem je obnovit zařízení a zapnout ho. Zařízení by se měla nacházet na obrazovce **Hello** , když zařízení připojíte.
    > Pokud je zařízení už zaregistrované u účtu Apple ID, musí se před zahájením procesu registrace odstranit ze zařízení Apple iCloud. Chyba výzvy se zobrazí jako "nelze aktivovat [název zařízení]".

2. V podokně **Předvolby** vyberte **servery** a kliknutím na symbol plus (+) spusťte Průvodce serveru MDM. Zvolte **Další**.
3. V části registrace Průvodce nastavením pro zařízení s iOS pomocí Microsoft Intune zadejte **název hostitele nebo adresu URL** a **adresu URL pro registraci** serveru MDM. Jako adresu URL pro registraci zadejte adresu URL profilu pro registraci exportovanou z Intune. Zvolte **Další**.  
    Upozornění, že adresa URL serveru není ověřena, může být bez obav. Chcete-li pokračovat, klikněte na tlačítko **Další** až do dokončení průvodce.
4. Připojte mobilní zařízení iOS k počítači Mac pomocí adaptéru USB.
5. Vyberte zařízení s iOS, která chcete spravovat, a pak zvolte **připravit**. V podokně **připravit zařízení iOS** vyberte možnost **ručně**a potom klikněte na tlačítko **Další**.
6. V podokně **zaregistrovat v serveru MDM** vyberte název serveru, který jste vytvořili, a pak zvolte **Další**.
7. V podokně **dohled nad zařízeními** vyberte úroveň dohledu a pak klikněte na tlačítko **Další**.
8. V podokně **vytvořit organizaci** vyberte **organizaci** nebo vytvořte novou organizaci a pak zvolte **Další**.
9. V podokně **Konfigurovat pomocníka s nastavením pro iOS** vyberte kroky, které chcete uživateli předložit, a pak zvolte **připravit**. Pokud se zobrazí výzva, proveďte ověření, aby se aktualizovalo nastavení důvěryhodnosti.  
10. Až se dokončí příprava zařízení s iOS, odpojte kabel USB.  

### <a name="distribute-devices"></a>Distribuce zařízení
Zařízení jsou nyní připravena k registraci společnosti. Vypněte zařízení a distribuujte je uživatelům. Když uživatelé zařízení zapnou, spustí se Pomocník s nastavením.

Jakmile uživatelé dostanou svá zařízení, musí dokončit pomocníka s nastavením. Zařízení nakonfigurovaná s přidružením uživatele umožňují instalaci a spuštění aplikace Portál společnosti pro stahování aplikací a správu zařízení.

## <a name="direct-enrollment"></a>Přímá registrace
Při přímé registraci zařízení s iOS pomocí Apple Configuratoru můžete zaregistrovat zařízení bez získání sériového čísla zařízení. Můžete také pojmenovat zařízení pro účely identifikace předtím, než Intune zachytí název zařízení během registrace. Aplikace Portál společnosti není podporovaná přímo zaregistrovanými zařízeními. Tato metoda nevymaže zařízení.

Aplikace, které vyžadují přidružení uživatele, včetně aplikace Portál společnosti používané pro instalaci obchodních aplikací, se nedají nainstalovat.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Exportovat profil jako. mobileconfig do zařízení s iOS

1. V [Intune](https://aka.ms/intuneportal)vyberte **registrace zařízení** > **registrace Apple** > **Apple Configuratoru** >  > vyberte profil, který chcete exportovat > **exportovat profil**.
2. V části **Přímá registrace**vyberte **Stáhnout profil**a soubor uložte. Soubor registračního profilu je platný jenom po dobu dvou týdnů, po které ho budete muset znovu vytvořit.
3. Přeneste soubor do počítače Mac, na kterém běží [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) , a nahrajte ho přímo jako profil pro správu do zařízení s iOS.
4. Připravte zařízení pomocí Apple Configuratoru pomocí následujících kroků:
    1. V počítači Mac otevřete Apple Configuratoru 2,0.
    2. Připojte zařízení s iOS k počítači Mac pomocí kabelu USB. Zavřete fotky, iTunes a další aplikace, které se otevřou pro zařízení, když se zjistí zařízení.
    3. V Apple Configuratoru zvolte připojené zařízení se systémem iOS a pak klikněte na tlačítko **Přidat** . V rozevíracím seznamu se zobrazí možnosti, které se dají přidat do zařízení. Vyberte **profily**.

        ![Profil exportu snímku pro instalaci Průvodce nastavením s zvýrazněnou adresou URL profilu](./media/apple-configurator-enroll-ios/ios-apple-configurator-add-profile.png)

    4. Pomocí nástroje pro výběr souborů vyberte soubor. mobileconfig, který jste exportovali z Intune, a pak zvolte **Přidat**. Profil se přidá do zařízení. Pokud zařízení není pod dohledem, instalace vyžaduje přijetí na zařízení.
5. Pomocí následujících kroků nainstalujte profil na zařízení s iOS. Zařízení musí již mít průvodce nastavením, které je připraveno k použití. Pokud registrace zahrnuje nasazení aplikací, zařízení by mělo mít nastavené Apple ID, protože nasazení aplikace vyžaduje, abyste si v App Storu přihlásili Apple ID.
    1. Odemkněte zařízení s iOS.
    2. V dialogovém okně **instalovat profil** pro **Profil správy**klikněte na možnost **instalovat**.
    3. V případě potřeby zadejte heslo zařízení nebo Apple ID.
    4. Přijměte **Upozornění**a klikněte na tlačítko **nainstalovat**.
    5. Přijměte **vzdálené upozornění**a vyberte možnost **důvěřovat**.
    6. Když se v okně **profil nainstalován** potvrdí, že se profil nainstaloval, klikněte na **Hotovo**.

6. Na zařízení s iOS otevřete **Nastavení** a v části **Obecné**@no__t**Správa zařízení** > **profil pro správu**. Ověřte, že je v seznamu uvedená instalace profilu, a zkontrolujte omezení zásad iOS a nainstalované aplikace. Zobrazení omezení zásad a aplikací na zařízení může trvat až 10 minut.

7. Distribuujte zařízení. Zařízení s iOS je teď zaregistrované v Intune a spravované.





