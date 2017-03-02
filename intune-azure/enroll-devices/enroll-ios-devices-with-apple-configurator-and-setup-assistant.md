---
title: "Registrace zařízení s iOSem – Apple Configurator – Pomocník s nastavením | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Přečtěte si, jak jde pomocí Apple Configuratoru registrovat zařízení s iOSem vlastněná společností s využitím Pomocníka s nastavením."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 888e7b7af7dcca4154f67a1de781eb7908d9a187
ms.lasthandoff: 02/15/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-setup-assistant"></a>Registrace zařízení s iOSem pomocí Apple Configuratoru a Pomocníka s nastavením 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune podporuje registraci zařízení s iOSem patřících společnosti pomocí [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) spuštěného na počítači Mac. Tento postup obnoví tovární nastavení zařízení a připraví ho ke spuštění Pomocníka s nastavením a k instalaci zásad společnosti pro nového uživatele zařízení.

>[!NOTE]
>Tato metoda registrace se nedá použít s metodou [správce registrace zařízení](enroll-devices-using-device-enrollment-manager.md).

Apple Configurator umožňuje obnovit na zařízení s iOSem tovární nastavení a připravit ho k nastavení pro nového uživatele. U tohoto způsobu je potřeba zařízení s iOSem připojit k počítači Mac přes USB, aby bylo možné nastavit firemní registraci. Předpokládá se použití Apple Configuratoru 2.0. K povolení aplikace Portál společnosti služby Intune většina scénářů vyžaduje, aby zásady použité na zařízení s iOSem zahrnovaly přidružení uživatele.

Další metody registrace zařízení s iOSem jsou popsané v článku [Volba způsobu registrace zařízení s iOSem v Intune](choose-ios-enrollment-method.md).

## <a name="prerequisites"></a>Požadavky

Před nastavením registrace zařízení s iOSem zajistěte splnění následujících požadavků:

- [Konfigurace domén](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Nastavení autority MDM](set-mdm-authority.md)
- [Vytvoření skupin](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Konfigurace aplikace Portál společnosti](/intune-azure/manage-apps/company-portal-app.md)
- Přiřazení uživatelských licencí na [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Získání certifikátu Apple MDM push certificate](get-an-apple-mdm-push-certificate.md)
- Ujistěte se, že máte k zařízením s iOSem fyzický přístup.
- Připravte si sériová čísla zařízení – viz článek o [zjištění sériového čísla zařízení s iOSem](https://support.apple.com//HT204308).
- Připravte si propojovací kabely USB.
- Ujistěte se, že máte počítač Mac s nainstalovaným [Apple Configuratorem 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).
- [Přidání sériových čísel Apple Configuratoru](add-apple-configurator-serial-numbers.md)


## <a name="create-an-apple-configurator-profile-for-devices"></a>Vytvoření profilu Apple Configuratoru pro zařízení

Profil registrace zařízení definuje nastavení, která se použijí pro skupinu zařízení. Následující postup ukazuje, jak vytvořit profil registrace zařízení s iOSem zaregistrovaného v Apple Configuratoru.

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Registrace Apple**.

3. V části **Spravovat nastavení registrace Apple Configuratoru** vyberte **Profily AC**.

4. V okně **Registrační profily Apple Configuratoru** vyberte **Vytvořit**.

5. V okně **Vytvořit registrační profil** zadejte název a popis profilu.

6. V části **Přidružení uživatele** zvolte, jestli se zařízení s tímto profilem budou registrovat s přidružením uživatele nebo bez.

   - **Zaregistrovat s přidružením uživatele** – Při počátečním nastavení musí mít zařízení přidruženého uživatele, aby mohlo dostat přístup k firemním datům a e-mailu. Přidružení uživatele by se mělo nastavit pro zařízení spravovaná v programu DEP, která patří konkrétním uživatelům a potřebují používat portál společnosti kvůli službám, jako je instalace aplikací.

   - **Zaregistrovat bez přidružení uživatele** – K zařízení není přidružený žádný uživatel. Toto spřažení použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, které vyžadují přidruženého uživatele (včetně aplikace Portál společnosti používané k instalaci obchodních aplikací), nebudou fungovat.

7. Uložte profil pomocí tlačítka **Vytvořit**.

## <a name="assign-serial-numbers-to-an-apple-configurator-profile"></a>Přiřazení sériových čísel k profilu Apple Configuratoru

Po vytvoření profilů Apple Configuratoru k nim můžete přiřadit sériová čísla zařízení. Abyste mohli přiřadit sériová čísla, musíte je napřed přidat do Intune podle kroků v článku [Přidání sériových čísel Apple Configuratoru](add-apple-configurator-serial-numbers.md).

### <a name="assign-serial-numbers-to-apple-configurator-profiles"></a>Přiřazení sériových čísel k profilům Apple Configuratoru

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně **Registrační profily Apple Configuratoru** vyberte profil, ke kterému chcete přiřadit sériová čísla.

3. V okně profilu vyberte **Sériová čísla** > **Přiřadit**.

4. Vyberte sériová čísla, která chcete přiřadit k profilu, a pak zvolte tlačítko **Přiřadit**.

## <a name="export-the-profile-to-ios-devices"></a>Export profilu do zařízení s iOSem

Po vytvoření profilu a přiřazení sériových čísel musíte exportovat profil z Intune, a to buď jako adresu URL, nebo jako soubor ve formátu popsaném níže. Pak ho ručně naimportujete do programu Apple Configurator na Macu a potom ho program Apple Configurator nasadí do zařízení.

### <a name="export-a-profile-using-setup-assistant-enrollment"></a>Export profilu pomocí registrace Pomocníka s nastavením

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně **Registrační profily Apple Configuratoru** zvolte profil, který chcete exportovat.

3. V okně profilu vyberte **Exportovat profil**.

4. Zkopírujete adresu URL profilu do [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) s připojeným zařízením s iOSem. Později URL odešlete do Apple Configuratoru, abyste definovali profil Intune používaný zařízeními iOS.

  Podpora Apple Configuratoru 2 vyžaduje úpravu adresy URL profilu 2.0. Uděláte to tak, že tento kód:
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    Nahradíte tímto kódem:

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   V následujícím postupu odešlete tuto adresu URL profilu do služby Apple DEP pomocí Apple Configuratoru, abyste definovali profil Intune používaný zařízeními s iOS.

5. Nahrajte tuto adresu URL profilu do služby Apple DEP pomocí Apple Configuratoru, abyste definovali profil Intune používaný zařízeními s iOSem.


    1.  Na počítači Mac otevřete **Apple Configurator 2**. V panelu nabídek vyberte **Apple Configurator 2** a potom **Předvolby**.

         > [!WARNING]
         > V průběhu registrace bude v zařízeních obnovená tovární konfigurace. Doporučuje se zařízení resetovat a zapnout ho. Zařízení by při připojení měla mít nastavenou **úvodní obrazovku**.

    2. V **podokně předvoleb** vyberte **Servery** a znaménkem plus (+) spusťte průvodce serveru MDM. Vyberte **Další**.

    3. Zadejte **název** a **adresu URL pro registraci** serveru MDM z 6. kroku – Registrace pomocníka s nastavením pro zařízení s iOSem v Microsoft Intune. Jako adresu URL pro registraci zadejte adresu URL profilu pro registraci exportovanou z Intune. Vyberte **Další**.  

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

## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Jak uživatelé instalují a používají aplikaci Portál společnosti na svých zařízeních

Zařízení nakonfigurovaná s přidružením uživatele umožňují instalaci a spuštění aplikace Portál společnosti, která slouží ke stahování aplikací a správě zařízení. Když uživatelé dostanou zařízení, musí provést další kroky popsané níže, aby dokončili postup Pomocníka s nastavením a nainstalovali aplikaci Portál společnosti.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Postup registrace zařízení s iOSem vlastněných společností s přidružením uživatele

1. Když uživatel zapne své zařízení, zobrazí se výzva k dokončení postupu Pomocníka s nastavením. Během nastavování se uživateli zobrazí výzva k zadání přihlašovacích údajů. Uživatel musí použít přihlašovací údaje (tj. jedinečné osobní jméno nebo hlavní název uživatele) přidružené k jeho předplatnému Intune.

2. Během nastavování se uživateli zobrazí výzva k zadání Apple ID. Aby mohlo zařízení nainstalovat aplikaci Portál společnosti, musí uživatel zadat Apple ID. Po dokončení nastavení můžou ID zadat i z nabídky nastavení iOS.

3. Po dokončení nastavení musí zařízení s iOSem nainstalovat aplikaci Portál společnosti z App Storu.

4. Uživatel se teď může přihlásit ke službě Portál společnosti pomocí hlavního názvu uživatele, který použil při nastavování zařízení.

5. Po přihlášení se uživateli zobrazí výzva k registraci zařízení. Prvním krokem je identifikace zařízení. Aplikace zobrazí seznam zařízení s iOS, která jsou už ve společnosti registrovaná a mají přiřazený účet Intune uživatele. Uživatel by měl vybrat odpovídající zařízení. Pokud zařízení ještě není ve společnosti zaregistrované, uživatel by měl vybrat Nové zařízení a pokračovat standardním postupem registrace.

6. Na další obrazovce musí uživatel potvrdit sériové číslo nového zařízení. Uživatel může klepnout na odkaz pro potvrzení sériového čísla. Tím se spustí aplikace Nastavení, která sériové číslo ověří. Potom musí uživatel zadat poslední čtyři znaky sériového čísla do aplikace Portál společnosti.

    Tento krok ověřuje, jestli se jedná o firemní zařízení zaregistrované v Intune. Pokud sériové číslo zařízení neodpovídá, znamená to, že došlo k výběru nesprávného zařízení. Uživatel se musí vrátit na předchozí obrazovku a vybrat jiné zařízení.

7. Po ověření sériového čísla aplikace Portál společnosti přesměruje uživatele na web Portál společnosti, kde registraci dokončí. Potom web uživatele vyzve, aby se vrátil do aplikace.

Registrace je tím dokončená a uživatel může zařízení používat s úplnou sadou funkcí.

