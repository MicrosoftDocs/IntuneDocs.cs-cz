---
title: Registrace zařízení s iOSem pomocí Apple Configuratoru
titlesuffix: Microsoft Intune
description: Přečtěte si, jak jde pomocí Apple Configuratoru registrovat zařízení s iOSem vlastněná společností s využitím Pomocníka s nastavením.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5ecdd79a029bc3d434ebb0d8ba62ea0e65215f9e
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>Registrace zařízení s iOSem pomocí Apple Configuratoru

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

> [!NOTE]
> ### <a name="temporary-user-interface-differences"></a>Dočasné rozdíly v uživatelském rozhraní
>
>Uživatelská rozhraní pro funkce popsané na této stránce se právě aktualizují. Tyto aktualizace se budou u všech uživatelských účtů zavádět postupně do konce dubna.
>
>Pokud vaše stránka **Registrace zařízení** vypadá jako na obrázku níže, váš účet se ještě neaktualizoval na nové uživatelské rozhraní a můžete použít tuto stránku nápovědy.
>
>![Původní uživatelské rozhraní Intune](./media/appleenroll-oldui.png)
>
>Pokud vaše stránka **Registrace zařízení** vypadá jako na obrázku níže, máte aktualizované uživatelské rozhraní.  Přejděte na [tuto stránku nápovědy](apple-configurator-enroll-ios-newui.md).
>
>![Nové uživatelské rozhraní Intune](./media/appleenroll-newui.png)

Intune podporuje registraci zařízení s iOSem pomocí [Apple Configuratoru](https://itunes.apple.com/app/apple-configurator-2/id1037126344) spuštěných na počítačích Mac. Registrace pomocí Apple Configuratoru vyžaduje, abyste každé zařízení s iOSem připojili prostřednictvím USB k počítači Mac a nastavili registraci pro podniky. Zařízení můžete do služby Intune registrovat pomocí Apple Configuratoru dvěma způsoby:
- **Registrace Pomocníka s nastavením** – Obnoví tovární nastavení zařízení a připraví ho k registraci Pomocníka s nastavením.
- **Přímá registrace** – Neobnoví tovární nastavení zařízení a zaregistruje ho pomoci nastavení iOSu. Tato metoda podporuje jenom **zařízení bez přidružení uživatele**.

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

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Zvolte **Registrace zařízení** > **Registrace Apple**.
4. V části **Spravovat nastavení registrace Apple Configuratoru** vyberte **Profily AC**.
5. V **Registračních profilech Apple Configuratoru** vyberte **Vytvořit**.
6. Zadejte **Název** a **Popis** profilu pro účely správy. Uživatelům se tyto údaje nezobrazí. Pole Název můžete využít k vytvoření dynamické skupiny v Azure Active Directory. Název profilu použijte k definování parametru enrollmentProfileName, který slouží k přiřazení zařízení s tímto registračním profilem. Přečtěte si další informace o dynamických skupinách Azure Active Directory.


  ![Obrazovka Vytvořit profil s vybranou možností Zaregistrovat s přidružením uživatele](./media/apple-configurator-profile-create.png)

5. Určete **Přidružení uživatele**:
   - **Zaregistrovat s přidružením uživatele** – Zařízení musí mít přidruženého uživatele (pomocí Průvodce nastavením), aby mohlo dostat přístup k firemním datům a e-mailu. Přidružení uživatele se vyžaduje u spravovaných zařízení, která patří konkrétním uživatelům a potřebují používat Portál společnosti kvůli službám, jako je instalace aplikací. Tato možnost je podporovaná jenom pro registraci Pomocníka s nastavením. Přidružení uživatelů vyžaduje [koncový bod WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints). [Přečtěte si další informace](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

   > [!NOTE]
   > Při registraci s přidružením uživatelů nefunguje vícefaktorové ověřování (MFA). Po registraci vícefaktorové ověřování na zařízeních funguje podle očekávání. Zařízení nemůžou vyzvat uživatele, kteří při prvním přihlášení potřebují změnit své heslo. Výzva k resetování hesla se během registrace nezobrazí ani uživatelům, kterým vypršela platnost hesla. Uživatelé musí heslo resetovat z jiného zařízení.

   - **Zaregistrovat bez přidružení uživatele** – K zařízení není přidružený žádný uživatel. Toto spřažení použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, které vyžadují přidruženého uživatele (včetně aplikace Portál společnosti používané k instalaci obchodních aplikací), nebudou fungovat. Vyžaduje se pro přímou registraci.

6. Uložte profil pomocí tlačítka **Vytvořit**.

## <a name="setup-assistant-enrollment"></a>Registrace Pomocníka s nastavením

### <a name="add-apple-configurator-serial-numbers"></a>Přidání sériových čísel Apple Configuratoru

**Přidání sériových čísel Apple Configuratoru k Intune**

1. Vytvořte seznam hodnot oddělených čárkami se dvěma sloupci (.csv) bez záhlaví. Do levého sloupce přidejte sériové číslo a v pravém sloupci uveďte podrobnosti. Aktuálně je maximální počet řádků v seznamu 5 000. V textovém editoru vypadá seznam .csv takto:

   F7TLWCLBX196,podrobnosti o zařízení</br>
   DLXQPCWVGHMJ,podrobnosti o zařízení

   Přečtete si, [jak zjistit sériové číslo zařízení s iOSem](https://support.apple.com/HT204073).
2. V Intune na portálu [Azure Portal](https://portal.azure.com) zvolte **Registrace zařízení** a potom **Registrace Apple**.
3. V části **Spravovat nastavení registrace Apple Configuratoru** vyberte **Zařízení Apple Configuratoru**.
4. Vyberte **Přidat**.
5. Vyberte **profil registrace**, jehož prostřednictvím použijete importovaná sériová čísla. Pokud importujete soubor s novými podrobnostmi, kterými se přepíšou ty stávající, vyberte nastavení **Přepište podrobnosti u existujících identifikátorů**.
6. Přejděte k souboru CSV se sériovými čísly a vyberte **Přidat**.

### <a name="reassign-a-profile-to-device-serial-numbers"></a>Opětovné přiřazení profilu k sériovým číslům zařízení

Profil registrace se přiřazuje při importu sériových čísel zařízení s iOSem pomocí Apple Configuratoru. Intune navíc umožňuje přiřazovat profily ze dvou míst na portálu Azure Portal:
- **Zařízení Apple Configuratoru**
- **Profily AC**

#### <a name="assign-from-apple-configurator-devices"></a>Přiřazení v části Zařízení Apple Configuratoru

1. V Intune na portálu [Azure Portal](https://portal.azure.com) zvolte **Registrace zařízení** a potom **Registrace Apple**.
2. V **Zařízeních Apple Configuratoru** vyberte sériová čísla, ke kterým chcete přiřadit profil, a pak vyberte **Přiřadit profil**.
3. V možnosti **Přiřadit profil** vyberte **nový profil**, který chcete přiřadit, a pak zvolte **Přiřadit**.

#### <a name="assign-from-profiles"></a>Přiřazení z profilů
1. V Intune na portálu [Azure Portal](https://portal.azure.com) zvolte **Registrace zařízení** a potom **Registrace Apple**.
2. Zvolte **Profily AC** a vyberte profil, který chcete sériovým číslům přiřadit.
3. V profilu zvolte **Přiřazená zařízení**a pak **Přiřadit**.
4. Pomocí filtru vyhledejte sériová čísla zařízení, která chcete k profilu přiřadit, vyberte zařízení a zvolte **Přiřadit**.

### <a name="export-the-profile"></a>Export profilu
Po vytvoření profilu a přiřazení sériových čísel je potřeba profil exportovat z Intune jako adresu URL. Tu pak importujete do Apple Configuratoru na počítači Mac, odkud můžete profil nasadit do zařízení.

1. V Intune na portálu [Azure Portal](https://portal.azure.com) zvolte **Registrace zařízení** > **Registrace Apple** > **Profily AC** a potom vyberte profil, který chcete exportovat.
2. V profilu vyberte **Exportovat profil**.

   ![Obrazovka Exportovat profil pro registraci Pomocníka s nastavením se zvýrazněnou adresou URL profilu](./media/ios-apple-configurator-expor-sat.png)
3. Zkopírujte adresu URL profilu. Potom ji můžete přidat do Apple Configuratoru a definovat tak profil Intune používaný zařízeními s iOSem.

   V dalším kroku tento profil importujete do Apple Configuratoru a opět definujete profil Intune používaný zařízeními s iOSem.

### <a name="enroll-devices-with-setup-assistant"></a>Registrace zařízení s využitím Pomocníka s nastavením

1. Na počítači Mac otevřete **Apple Configurator 2**. V panelu nabídek vyberte **Apple Configurator 2** a potom **Předvolby**.
   > [!WARNING]
   > V průběhu registrace se v zařízeních obnoví tovární konfigurace. Doporučuje se zařízení resetovat a zapnout ho. Zařízení by při připojení měla mít nastavenou **úvodní obrazovku**.

2. V podokně **předvoleb** vyberte **Servery** a znaménkem plus (+) spusťte průvodce serveru MDM. Vyberte **Další**.
3. V části registrace Průvodce nastavením zařízení s iOSem v Microsoft Intune zadejte **název hostitele nebo adresu URL** a **adresu URL pro registraci** serveru MDM. Jako adresu URL pro registraci zadejte adresu URL profilu pro registraci exportovanou z Intune. Vyberte **Další**.  

   Upozornění na neověřenou adresu URL serveru můžete ignorovat. Vyberte **Další** a pokračujte až do konce průvodce.
4. Mobilní zařízení s iOSem připojte kabelem USB k počítači Mac.
5. Vyberte zařízení s iOSem, která chcete spravovat, a pak zvolte **Prepare** (Spravovat). V podokně **Prepare iOS Device** (Připravit zařízení s iOSem) vyberte **Manual** (Ručně) a pak zvolte **Next** (Další).
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
1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V části **Exportovat profil** pomocí možnosti **Stáhnout profil** stáhněte profil registrace.


  ![Obrazovka Exportovat profil pro registraci Pomocníka s nastavením se zvýrazněnou adresou URL profilu](./media/ios-apple-configurator-expor-de.png)

2. Soubor přeneste do počítače Mac se spuštěným [Apple Configuratorem](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12). Může se tak odeslat přímo jako profil správy do zařízení s iOSem.
3. Připravte zařízení pomocí Apple Configuratoru podle následujících kroků.
   1. Na počítači Mac otevřete Apple Configurator 2.0.
   2. Zařízení s iOSem připojte k počítači Mac pomocí kabelu USB. Zavřete Fotky, iTunes a další aplikace, které se otevřou při zjištění zařízení.
   3. V Apple Configuratoru zvolte připojené zařízení s iOSem a potom zvolte tlačítko **Přidat**. V rozevíracím seznamu se zobrazí možnosti, které se dají přidat do zařízení. Vyberte **Profily**.

      ![Obrazovka Exportovat profil pro registraci Pomocníka s nastavením se zvýrazněnou adresou URL profilu](./media/ios-apple-configurator-add-profile.png)

   4. Pomocí nástroje pro výběr souborů vyberte soubor .mobileconfig, který jste exportovali z Intune, a zvolte **Přidat**. Profil se přidá do zařízení. Pokud má zařízení nastavenou možnost Bez dohledu, vyžaduje instalace přijetí na zařízení.

4. Nainstalujte profil na zařízení s iOSem podle následujících kroků. Je potřeba, aby už byl v zařízení dokončený Pomocník s nastavením a aby bylo připravené k použití. Pokud registrace zahrnuje nasazení aplikací, zařízení by mělo mít nastavené Apple ID, protože při nasazení aplikace bude potřeba přihlásit se do App Storu pomocí Apple ID.
   1. Odemkněte zařízení s iOSem.
   2. V dialogovém okně **Nainstalovat profil** pro **Profil správy** zvolte **Instalovat**.
   3. V případě potřeby zadejte heslo zařízení nebo Apple ID.
   4. Potvrďte **upozornění** a zvolte **Instalovat**.
   5. Potvrďte **vzdálené upozornění** a zvolte **Důvěřovat**.
   6. Jakmile okno **Profil nainstalován** potvrdí, že se profil nainstaloval, zvolte **Hotovo**.

5. Na zařízení s iOSem otevřete **Nastavení** a přejděte na **Obecné** > **Správa zařízení** > **Profil pro správu**. Potvrďte, že je zde instalace profilu uvedená, a zkontrolujte omezení zásad iOS a nainstalované aplikace. Zobrazení omezení vyplývajících ze zásad a aplikací na zařízení může trvat až 10 minut.

6. Distribuujte zařízení. Zařízení s iOSem je teď zaregistrované v Intune a spravované.


