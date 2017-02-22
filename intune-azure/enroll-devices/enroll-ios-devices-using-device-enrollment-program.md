---
title: "Registrace zařízení s iOSem – Program registrace zařízení (DEP) | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Naučte se registrovat zařízení s iOSem ve vlastnictví firmy pomocí Programu registrace zařízení (DEP)."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: adb2fd27d7f2b3f0ef4dce6b26fcb20d74b69a00
ms.openlocfilehash: 2986e659d384eaa67b64af1ce3ae48a1ac81a600


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>Registrace zařízení s iOSem pomocí Programu registrace zařízení (DEP)

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune umožňuje nasadit registrační profil, který bezdrátově zaregistruje zařízení s iOSem zakoupená prostřednictvím programu DEP (Device Enrollment Program). Profil obsahuje nastavení správy, která chcete použít u zařízení. Registrační balíček může zahrnovat možnosti Pomocníka s nastavením pro zařízení. U zařízení zaregistrovaných prostřednictvím Programu registrace zařízení nemůžou uživatelé registraci zrušit.

>[!NOTE]
>Tato metoda registrace se nedá použít s metodou [správce registrace zařízení](enroll-devices-using-device-enrollment-manager.md).

Pokud chce organizace ke správě zařízení s iOS, která jsou v jejím vlastnictví, používat program DEP (Device Enrollment Program) společnosti Apple, musí se do tohoto programu zaregistrovat a získat zařízení jeho prostřednictvím. Podrobnosti o tomto procesu najdete na [https://deploy.apple.com](https://deploy.apple.com). Výhodou tohoto programu je bezobslužné nastavení zařízení bez připojení každého zařízení k počítači kabelem USB.

Abyste mohli pomocí programu DEP registrovat zařízení s iOSem ve vlastnictví firmy, musíte [získat token DEP](get-apple-dep-token.md) od společnosti Apple. Token umožňuje Intune synchronizovat informace o zařízeních vlastněných společností, která se účastní programu DEP. Token taky umožňuje Intune odesílat společnosti Apple registrační profil a přiřazovat k těmto profilům zařízení.

Další metody registrace zařízení s iOSem jsou popsané v článku [Volba způsobu registrace zařízení s iOSem v Intune](choose-ios-enrollment-method.md).

## <a name="prerequisites"></a>Požadavky

Před nastavením registrace zařízení s iOSem zajistěte splnění následujících požadavků:

- [Konfigurace domén](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Nastavení autority MDM](set-mdm-authority.md)
- [Vytvoření skupin](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- Přiřazení uživatelských licencí na [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Získání certifikátu Apple MDM push certificate](get-an-apple-mdm-push-certificate.md)
- [Získání tokenu Apple DEP](get-apple-dep-token.md)

## <a name="create-an-apple-dep-profile-for-devices"></a>Vytvoření profilu Apple DEP pro zařízení

Profil registrace zařízení definuje nastavení, která se použijí pro skupinu zařízení. Následující postup ukazuje, jak vytvořit profil registrace zařízení pro zařízení s iOSem registrovaná pomocí programu DEP.

1. Na portálu Azure Portal zvolte **Další služby**, do textového pole zadejte **Intune** a pak zvolte **Jiné** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Registrace Apple**.

3. V části **Spravovat nastavení Programu registrace zařízení (DEP) Apple** vyberte **Profily DEP**.

4. V okně **Profily DEP** vyberte **Vytvořit**.

5. V okně **Vytvořit registrační profil** zadejte název a popis profilu.

6. V části **Přidružení uživatele** zvolte, jestli se zařízení s tímto profilem budou registrovat s přidružením uživatele nebo bez.

 - **Zaregistrovat s přidružením uživatele** – Při počátečním nastavení musí mít zařízení přidruženého uživatele, aby mohlo dostat přístup k firemním datům a e-mailu. Přidružení uživatele zvolte pro zařízení spravovaná v programu DEP, která patří konkrétním uživatelům a potřebují používat portál společnosti kvůli službám, jako je instalace aplikací. Při registraci na zařízeních v programu DEP s přidružením uživatelů nefunguje vícefaktorové ověřování (MFA). Po registraci vícefaktorové ověřování na těchto zařízeních funguje podle očekávání.

    >[!NOTE]
    >Program DEP s přidružením uživatele vyžaduje aktivaci uživatelského jména / smíšeného koncového bodu WS-Trust 1.3, aby mohl požádat o token uživatele.

 - **Zaregistrovat bez přidružení uživatele** – K zařízení není přidružený žádný uživatel. Toto spřažení použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, které vyžadují přidruženého uživatele (včetně aplikace Portál společnosti používané k instalaci obchodních aplikací), nebudou fungovat.

7. Vyberte **Nastavení správy zařízení**, nakonfigurujte následující nastavení profilu a potom vyberte **Uložit**:

    - **Pod dohledem** – Režim, který nabízí více možností správy a ve výchozím nastavení má zakázaný zámek aktivace. Pokud políčko nezaškrtnete, budete mít omezené možnosti správy.

    - **Uzamčená registrace** – Vyžaduje režim správy Pod dohledem. Zakáže nastavení iOSu, která by mohla umožnit odebrání profilu správy. Pokud políčko nezaškrtnete, půjde profil správy odebrat z nabídky Nastavení. Tato položka se nastavuje při aktivaci a nedá se změnit bez obnovení továrního nastavení.

    - **Povolit párování** – Určuje, jestli se zařízení s iOSem můžou synchronizovat s počítači. Pokud vyberete **Povolit Apple Configurator podle certifikátu**, musíte zvolit certifikát v části **Certifikáty Apple Configuratoru**.

    - **Certifikáty Apple Configuratoru** – Pokud jste v části **Povolit párování** zvolili **Povolit Apple Configurator podle certifikátu**, vyberte certifikát Apple Configuratoru, který chcete importovat.

8. Vyberte **Nastavení Pomocníka s nastavením**, nakonfigurujte následující nastavení profilu a potom vyberte **Uložit**:

    - **Název oddělení** – Zobrazí se, když uživatelé klepnou při aktivaci na **O konfiguraci**.

    - **Telefon na oddělení** – Zobrazí se, když uživatel při aktivaci klikne na tlačítko Potřebuji nápovědu.
    - **Možnosti Pomocníka s nastavením** – Nastavení jsou volitelná a dají se nastavit později v nabídce **Nastavení** systému iOS.
        - **Heslo** – Při aktivaci se zobrazí výzva k zadání hesla. Vyžaduje vždy heslo, pokud zařízení nebude zabezpečené nebo nebude mít přístup kontrolovaný jiným způsobem (třeba pomocí celoobrazovkového režimu, který omezuje zařízení na jednu aplikaci).
        - **Zjišťování polohy** – Pokud je toto nastavení povolené, Pomocník s nastavením zobrazí při aktivaci výzvu služby.
        - **Obnovit** – Pokud je toto nastavení povolené, Pomocník s nastavením zobrazí při aktivaci výzvu k zálohování do úložiště iCloud.
        - **Apple ID** – Pokud je povolené, vyzve iOS uživatele při pokusu Intune o instalaci aplikace bez ID, aby zadali Apple ID. Apple ID je potřeba ke stahování aplikací pro iOS z App Storu, včetně těch instalovaných službou Intune.
        - **Podmínky a ujednání** – V případě povolení Pomocník nastavení vyzve uživatele k přijetí podmínek a ujednání společnosti Apple během aktivace.
        - **Dotykový identifikátor** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.
        - **Dotykový identifikátor** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.
        - **Zvětšení** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.
        - **Siri** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.
        - **Diagnostická data** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.

9. Uložte nastavení profilu tak, že v okně **Vytvořit registrační profil** zvolíte **Vytvořit**.

## <a name="assign-apple-dep-serial-numbers-to-your-mdm-server"></a>Přiřazení sériových čísel Apple DEP k vašemu serveru MDM

1. Přejděte na [portál programu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) a přihlaste se pomocí firemního Apple ID. 

2. Přejděte na **Deployment Program** (Program nasazení) &gt; **Device Enrollment Program** (Program registrace zařízení) &gt; **Manage Devices** (Spravovat zařízení). 

3. Určete, jak budete volit zařízení (**Choose Devices**), a zadejte podrobné informace o zařízení pomocí možností **Serial Number** (Sériové číslo), **Order Number** (Číslo objednávky) nebo **Upload CSV File** (Nahrát soubor CSV). 

4. Zvolte **Assign to Server** (Přiřadit k serveru), zvolte &lt;název serveru&gt; zadaný pro Microsoft Intune a potom zvolte **OK**.

## <a name="synchronize-dep-managed-devices"></a>Synchronizace zařízení spravovaných v rámci programu DEP

1. V okně Intune na portálu Azure Portal zvolte **Registrovat zařízení** a pak zvolte **Registrace Apple**.

2. V části **Spravovat nastavení Programu registrace zařízení (DEP) Apple** vyberte **Sériová čísla DEP**.

4. V okně **Sériová čísla Apple DEP** vyberte **Synchronizovat**.

5. V okně **Synchronizovat** vyberte **Požadovat synchronizaci**. Indikátor průběhu vám ukáže dobu, jakou budete muset počkat před dalším vyžádáním synchronizace.

    Pro dosažení souladu s podmínkami společnosti Apple pro přijatelné přenosy v rámci DEP platí v Intune následující omezení:
     -  Úplná synchronizace programu DEP se nesmí spouštět častěji než jednou za sedm dní. Během úplné synchronizace Intune aktualizuje všechna sériová čísla, která společnost Apple přiřadila Intune, bez ohledu na jejich dřívější synchronizaci. Pokud se o úplnou synchronizaci pokusíte do sedmi dnů od předchozí úplné synchronizace, aktualizuje Intune jenom sériová čísla, která ještě nejsou v Intune.
     -  Každá žádost o synchronizaci má 10 minut na dokončení. Po tuto dobu nebo do úspěšného vykonání požadavku je tlačítko **Synchronizovat** neaktivní.

>[!NOTE]
>Z okna **Sériová čísla Apple DEP** můžete také sériová čísla DEP přiřadit k profilům.

## <a name="distribute-devices-to-users"></a>Distribuce zařízení uživatelům

Zařízení patřící společnosti teď můžete distribuovat uživatelům. Pokud je zařízení s iOSem zapnuté, zaregistruje se jeho správa službou Intune.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Jak uživatelé instalují a používají aplikaci Portál společnosti na svých zařízeních

Zařízení nakonfigurovaná s přidružením uživatele umožňují instalaci a spuštění aplikace Portál společnosti, která slouží ke stahování aplikací a správě zařízení. Když uživatelé dostanou zařízení, musí provést další kroky popsané níže, aby dokončili postup Pomocníka s nastavením a nainstalovali aplikaci Portál společnosti.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Postup registrace zařízení s iOSem vlastněných společností s přidružením uživatele 

1. Když uživatel zapne své zařízení, zobrazí se výzva k dokončení postupu Pomocníka s nastavením. Během nastavování se uživateli zobrazí výzva k zadání přihlašovacích údajů. Uživatel musí použít přihlašovací údaje (tj. jedinečné osobní jméno nebo hlavní název uživatele) přidružené k jeho předplatnému Intune.

2. Během nastavování se uživateli zobrazí výzva k zadání Apple ID. Aby mohlo zařízení nainstalovat aplikaci Portál společnosti, musí uživatel zadat Apple ID. Po dokončení nastavení může uživatel zadat ID i z nabídky nastavení iOS.

3. Po dokončení nastavení si uživatel musí nainstalovat aplikaci Portál společnosti z App Storu.

4. Uživatel se může přihlásit k aplikaci Portál společnosti pomocí hlavního názvu uživatele, který použil při nastavování zařízení.

5. Po přihlášení se uživateli zobrazí výzva k registraci zařízení. Prvním krokem je identifikace zařízení. Aplikace zobrazí seznam zařízení s iOS, která jsou už ve společnosti registrovaná a mají přiřazený účet Intune uživatele. Uživatel by měl vybrat odpovídající zařízení. Pokud zařízení ještě není ve společnosti zaregistrované, uživatel by měl vybrat Nové zařízení a pokračovat standardním postupem registrace.

6. Na další obrazovce uživatel potvrdí sériové číslo nového zařízení. Udělá to pomocí odkazu, který se zobrazí. Odkaz spustí aplikaci Nastavení, která uživateli umožní ověřit jeho sériové číslo. Potom musí uživatel zadat poslední čtyři znaky sériového čísla do aplikace Portál společnosti.

   Tento krok ověřuje, jestli se jedná o firemní zařízení zaregistrované v Intune. Pokud sériové číslo zařízení neodpovídá, znamená to, že uživatel vybral nesprávné zařízení. Uživatel se musí vrátit na předchozí obrazovku a vybrat jiné zařízení.

7. Po ověření sériového čísla aplikace Portál společnosti přesměruje uživatele na web Portál společnosti, kde registraci dokončí. Potom web uživatele vyzve, aby se vrátil do aplikace.

Registrace je tím dokončená a uživatel může zařízení používat s úplnou sadou funkcí.



<!--HONumber=Feb17_HO1-->


