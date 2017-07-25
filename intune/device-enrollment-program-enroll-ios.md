---
title: "Registrace zařízení s iOSem – Program registrace zařízení"
titleSuffix: Intune on Azure
description: "Naučte se registrovat zařízení s iOSem ve vlastnictví firmy pomocí Programu registrace zařízení (DEP)."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 654a19dd6f1e5f4fd2bda771b0df95b87944db75
ms.sourcegitcommit: 2a6ad3c233d15a9fb441362105f64b2bdd550c34
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/13/2017
---
# <a name="set-up-ios-device-enrollment-with-device-enrollment-program"></a>Nastavení registrace zařízení s iOSem pomocí Programu registrace zařízení

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Toto téma pomáhá správcům IT povolit registraci zařízení s iOSem zakoupených prostřednictvím [Programu registrace zařízení (DEP)](https://deploy.apple.com) společnosti Apple. Microsoft Intune může profil registrace nasadit do zařízení, která jste zakoupili prostřednictvím programu DEP, také „ze vzduchu“. Správce se žádného spravovaného zařízení nemusí vůbec dotknout. Profil DEP obsahuje nastavení správy, která se v zařízeních použijí během registrace, včetně možností Pomocníka s nastavením.

Registraci do programu DEP můžete povolit na portálu Intune i na portálu DEP společnosti Apple. Potřebujete také seznam ID nebo čísel objednávek, abyste je mohli zařadit do Intune a spravovat je na portálu Apple.

>[!NOTE]
>Registrace DEP se nedá použít se [správcem registrace zařízení](device-enrollment-manager-enroll.md).

**Postup povolení registračních programů od společnosti Apple**
1. [Získání tokenu DEP Apple a přiřazení zařízení](#get-the-apple-dep-token)
2. [Vytvoření registračního profilu](#create-an-apple-enrollment-profile)
3. [Synchronizace zařízení spravovaných v rámci programu DEP](#sync-managed-device)
4. [Přiřazení profilu DEP k zařízením](#assign-an-enrollment-profile-to-devices)
5. [Distribuce zařízení uživatelům](#end-user-experience-with-managed-devices)

## <a name="get-the-apple-dep-token"></a>Získání tokenu DEP Apple

Abyste mohli v Programu registrace zařízení (DEP) registrovat zařízení s iOSem vlastněná společností, potřebujete soubor s tokenem DEP (.p7m) od společnosti Apple. Token umožňuje Intune synchronizovat informace o zařízeních vlastněných společností, která se účastní programu DEP. Token také umožňuje Intune odesílat společnosti Apple registrační profily a přiřazovat k těmto profilům zařízení.

> [!NOTE]
> Když token odstraníte z konzoly Intune Classic před migrací do Azure, může Intune obnovit odstraněný token DEP Apple. Token DEP můžete z portálu Azure Portal znovu odstranit. Token DEP můžete z portálu Azure Portal znovu odstranit.

**Požadavky**
- [Certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- Registrace do [Programu registrace zařízení Apple (DEP)](http://deploy.apple.com)

**Krok 1: Stáhněte si certifikát veřejného klíče služby Intune, který je potřebný pro vytvoření tokenu DEP Apple.**<br>
1. Na portálu Intune zvolte **Registrace zařízení** a pak zvolte **Registrace Apple** a **Token Programu registrace**.

  ![Snímek obrazovky s podoknem Token Programu registrace v pracovním prostoru Certifikáty Apple](./media/enrollment-program-token-add.png)

2. Vyberte **Stáhnout certifikát veřejného klíče** a stáhněte si a místně uložte soubor šifrovacího klíče (.pem). Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Device Enrollment Program.

  ![Snímek obrazovky s podoknem Token Programu registrace v pracovním prostoru Certifikáty Apple pro stažení veřejného klíče](./media/enrollment-program-token-download.png)

**Krok 2: Vytvořte token DEP Apple a stáhněte si ho.**<br>
1. Pokud chcete otevřít portál Programu registrace zařízení Apple (DEP), vyberte **Vytvořit token prostřednictvím Programu registrace zařízení Apple** a přihlaste se pomocí firemního Apple ID. Toto Apple ID můžete použít k obnovení tokenu DEP.

  ![Snímek obrazovky s podoknem Token Programu registrace v pracovním prostoru Certifikáty Apple](./media/enrollment-program-token-create.png)

  ![Snímek obrazovky s podoknem Token Programu registrace v pracovním prostoru Certifikáty Apple pro stažení veřejného klíče](./media/enrollment-program-token-sign.png)
2.  Na [portálu společnosti Apple pro nasazení programů](https://deploy.apple.com) vyberte **Začínáme**. Otevře se **program registrace zařízení**.

   ![Snímek obrazovky s Programem registrace, který se otevře po kliknutí na Začínáme v Programu registrace zařízení](./media/enrollment-program-token-started.png)

3. Na stránce pro **správu serverů** zvolte, že chcete **přidat server MDM**.
4. Zadejte **název serveru MDM** a zvolte **Další**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Není to název serveru Microsoft Intune ani jeho URL.

   ![Snímek obrazovky s oknem pro přidání názvu serveru MDM pro program DEP – po přidání názvu klikněte na Další](./media/enrollment-program-token-add-server.png)

5. Otevře se dialogové okno pro **přidání&lt;názvu serveru&gt;**, ve kterém se zobrazí výzva, abyste **nahráli svůj veřejný klíč**. Vyberte **Zvolit soubor**, abyste mohli nahrát soubor .pem, a pak zvolte **Další**.

   ![Snímek obrazovky s výběrem tlačítka souboru veřejného klíče a následným kliknutím na Další](./media/enrollment-program-token-choose-file.png)
6.  V dialogovém okně **Přidat server &lt;název_serveru&gt;** se zobrazí odkaz s **tokenem vašeho serveru**. Stáhněte si soubor tokenu serveru (.p7m) do svého počítače a potom zvolte **Hotovo**.
   ![Snímek obrazovky s vybraným tlačítkem souboru veřejného klíče – potom klikněte na Další](./media/enrollment-program-token-your-token.png)
7. Přejděte na **Deployment Programs** (Programy nasazení) &gt; **Device Enrollment Program** (Program registrace zařízení) &gt; **Manage Devices** (Spravovat zařízení).
8. V části se **způsobem výběru zařízení** určete způsob identifikace zařízení:
    - **Sériové číslo**
    - **Číslo objednávky**
    - **Nahrát soubor CSV**

   ![Snímek obrazovky s výběrem zařízení podle sériového čísla, nastavením volby akce na přiřazení serveru a výběrem názvu serveru](./media/enrollment-program-token-specify-serial.png)

9. V nabídce **volby akce** vyberte **přiřazení k serveru**, vyberte &lt;název serveru&gt; zadaný pro Microsoft Intune a pak zvolte **OK**. Portál Apple přiřadí daná zařízení k serveru Intune, aby bylo možné je spravovat, a pak zobrazí zprávu o **dokončení přiřazení**.

   Na portálu Apple přejděte na **Programy nasazení** &gt; **Program registrace zařízení** &gt; **Zobrazit historii přiřazení**. Zobrazí se seznam zařízení s přiřazeným serverem MDM.

**Krok 3: Zadejte Apple ID použité k vytvoření tokenu programu registrace.**<br>Na portálu Intune zadejte Apple ID pro budoucí použití. Toto ID můžete použít k obnovení tokenu programu registrace, abyste nemuseli všechna zařízení registrovat znovu.

![Snímek obrazovky s Apple ID použitým k vytvoření tokenu programu registrace a přechodem na token programu registrace](./media/enrollment-program-token-apple-id.png)

**Krok 4: Přejděte k tokenu programu registrace, který chcete nahrát.**<br>
Přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Nahrát**. S certifikátem Push Certificate může Intune registrovat a spravovat zařízení s iOSem a vynucovat zásady na zaregistrovaných mobilních zařízeních. Intune se automaticky synchronizuje s Apple, aby bylo možné zobrazit účet registračního programu.

## <a name="create-an-apple-enrollment-profile"></a>Vytvoření registračního profilu Apple

Registrační profil zařízení definuje nastavení, která se během registrace použijí pro skupinu zařízení.

1. Na portálu Intune zvolte **Registrace zařízení** a pak zvolte **Registrace Apple**.
2. V části **Program registrace pro Apple** vyberte **Profily Programu registrace** a v okně **Profily Programu registrace** vyberte **Vytvořit**.

  ![Snímek obrazovky s výběrem odkazu pro vytvoření profilu nového programu registrace](./media/enrollment-program-profile-create.png)

3. V okně **Vytvořit registrační profil** zadejte **Název** a **Popis** profilu pro účely správy. Uživatelům se tyto údaje nezobrazí.

  ![Snímek obrazovky se zadáním názvu, popisu a volbou Zaregistrovat s přidružením uživatele v profilu nového programu registrace](./media/enrollment-program-profile-name.png)
V části **Přidružení uživatele** zvolte, jestli se zařízení s tímto profilem budou registrovat s přidružením uživatele nebo bez.

 - **Zaregistrovat s přidružením uživatele** – při nastavení musí mít zařízení přidružené uživatele, aby mohla mít přístup k firemním datům a e-mailu. U zařízení, která patří uživatelům a potřebují pro služby, jako je instalace aplikací, použít portál společnosti, zvolte **přidružení uživatele**.

 > [!NOTE]
 > Na zařízeních spravovaných v programu pro registraci zařízení s přidružením uživatele nefunguje při registraci vícefaktorové ověřování (MFA). Po registraci vícefaktorové ověřování na těchto zařízeních funguje podle očekávání. Novým uživatelům, kteří si při prvním přihlášení musejí změnit heslo, se během registrace na zařízení nezobrazí výzva. Výzva k resetování hesla se během registrace nezobrazí ani uživatelům, kterým vypršela platnost hesla. Tito uživatelé musí heslo resetovat z jiného zařízení.

 >[!NOTE]
 >Správa prostřednictvím programu registrace s přidružením uživatele vyžaduje aktivaci [uživatelského jména / smíšeného koncového bodu WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints), aby bylo možné požádat o token uživatele. [Přečtěte si další informace o WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Zaregistrovat bez přidružení uživatele** – K zařízení není přidružený žádný uživatel. Toto spřažení použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, které vyžadují přidruženého uživatele (včetně aplikace Portál společnosti používané k instalaci obchodních aplikací), nemůžou fungovat.

4. Vyberte **Nastavení správy zařízení** a nakonfigurujte následující nastavení profilu:

  ![Snímek obrazovky s výběrem režimu správy. Zařízení má následující nastavení: Pod dohledem, Uzamčená registrace, Povolit párování nastaveno na Zamítnout vše. Možnost Certifikáty Apple Configuratoru je pro nový profil programu registrace zobrazena šedě.](./media/enrollment-program-profile-mode.png)
    - **Pod dohledem** – Režim, který nabízí více možností správy a ve výchozím nastavení má zakázaný zámek aktivace. Pokud políčko nezaškrtnete, budete mít omezené možnosti správy.

    - **Uzamčená registrace** – Vyžaduje režim správy Pod dohledem. Zakáže nastavení iOSu, která by mohla umožnit odebrání profilu správy. Pokud políčko nezaškrtnete, půjde profil správy odebrat z nabídky Nastavení. Po registraci zařízení nemůžete toto nastavení změnit bez obnovení továrního nastavení zařízení.

    - **Povolit párování** – Určuje, jestli se zařízení s iOSem mohou synchronizovat s počítači. Pokud vyberete **Povolit Apple Configurator podle certifikátu**, musíte zvolit certifikát v části **Certifikáty Apple Configuratoru**.

    - **Certifikáty Apple Configuratoru** – Pokud jste v části **Povolit párování** zvolili **Povolit Apple Configurator podle certifikátu**, vyberte certifikát Apple Configuratoru, který chcete importovat.

  Vyberte **Uložit**.

5. Vyberte **Nastavení Průvodce nastavením** a nakonfigurujte následující nastavení profilu:

  ![Snímek obrazovky s výběrem nastavení konfigurace s dostupnými nastaveními pro nový profil programu registrace](./media/enrollment-program-profile-settings.png)
    - **Název oddělení** – Zobrazí se, když uživatelé klepnou při aktivaci na **O konfiguraci**.

    - **Telefon na oddělení** – Zobrazí se, když uživatel při aktivaci klikne na tlačítko **Potřebuji nápovědu**.
    - **Možnosti Pomocníka s nastavením** – Nastavení jsou volitelná a dají se nastavit později v nabídce **Nastavení** systému iOS.
        - **Heslo** – Při aktivaci se zobrazí výzva k zadání hesla. Vyžaduje vždy heslo, pokud zařízení nebude zabezpečené nebo nebude mít přístup kontrolovaný jiným způsobem. Třeba celoobrazovkový režim omezuje zařízení na jednu aplikaci.
        - **Zjišťování polohy** – Pokud je toto nastavení povolené, Pomocník s nastavením zobrazí při aktivaci výzvu služby.
        - **Obnovit** – Pokud je toto nastavení povolené, Pomocník s nastavením zobrazí při aktivaci výzvu k zálohování do úložiště iCloud.
        - **Apple ID** – Pokud je povolené, vyzve iOS uživatele při pokusu Intune o instalaci aplikace bez ID, aby zadali Apple ID. Apple ID je potřeba ke stahování aplikací pro iOS z App Storu, včetně aplikací instalovaných službou Intune.
        - **Podmínky a ujednání** – V případě povolení Pomocník nastavení vyzve uživatele k přijetí podmínek a ujednání společnosti Apple během aktivace.
        - **Dotykový identifikátor** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.
        - **Dotykový identifikátor** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.
        - **Zvětšení** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.
        - **Siri** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.
        - **Diagnostická data** – V případě povolení Pomocník s nastavením zobrazí během aktivace výzvu pro tuto službu.

    Vyberte **Uložit**.
9. Uložte nastavení profilu tak, že v okně **Vytvořit registrační profil** zvolíte **Vytvořit**. Profil registrace se zobrazí v programu registrace Apple v seznamu profilů registrace.

## <a name="sync-managed-devices"></a>Synchronizace spravovaných zařízení
Teď, když má Intune oprávnění spravovat vaše zařízení, můžete synchronizovat Intune s Apple, aby se spravovaná zařízení zobrazila na portálu Intune.

1. Na portálu Intune zvolte **Registrace zařízení** &gt; **Registrace Apple** &gt; **Zařízení Programu registrace**.
2. V části **Zařízení Programu registrace** vyberte **Synchronizovat**. Zobrazí se okno **Synchronizace**.

  ![Snímek obrazovky s vybraným uzlem Zařízení Programu registrace a vybraným odkazem pro synchronizaci](./media/enrollment-program-device-sync.png)
3. V okně **Synchronizovat** vyberte **Požadovat synchronizaci**. Indikátor průběhu vám ukáže dobu, jakou budete muset počkat před dalším vyžádáním synchronizace.

  ![Snímek obrazovky synchronizačního okna s vybraným odkazem Požadovat synchronizaci](./media/enrollment-program-device-request-sync.png)

  Kvůli dodržení podmínek společnosti Apple, které se týkají přijatelných přenosů při registraci v programu, platí v Intune následující omezení:
     -  Úplná synchronizace se nesmí pouštět častěji než jednou za sedm dní. Během úplné synchronizace Intune aktualizuje všechna sériová čísla Apple přiřazená Intune. Pokud se o úplnou synchronizaci pokusíte do sedmi dnů od předchozí úplné synchronizace, aktualizuje Intune jenom sériová čísla, která ještě nejsou v Intune.
     -  Každá žádost o synchronizaci má 15 minut na dokončení. Po tuto dobu nebo do úspěšného vykonání požadavku je tlačítko **Synchronizovat** neaktivní.
     - Intune synchronizuje nová a odebraná zařízení se společností Apple každých 24 hodin.
     
4. Pokud chcete zobrazit zařízení, zvolte v pracovním prostoru Programu registrace zařízení možnost **Aktualizovat**.

## <a name="assign-an-enrollment-profile-to-devices"></a>Přiřazení profilu registrace zařízením
Než se můžou zařízení zaregistrovat, musíte přiřadit profil programu registrace.

>[!NOTE]
>Sériová čísla můžete profilům také přiřadit v okně **sériových čísel Apple**.

1. Na portálu Intune zvolte **Registrace zařízení** > **Registrace Apple** a vyberte **Profily Programu registrace**.
2. V seznamu **Profily Programu registrace** vyberte profil, který chcete zařízením přiřadit, a pak vyberte **Přiřadit zařízení**.

 ![Snímek obrazovky synchronizačního okna s vybraným odkazem Požadovat synchronizaci](./media/enrollment-program-device-assign.png)

3. Vyberte **Přiřadit** a pak vyberte zařízení, kterým chcete tento profil přiřadit. Dostupná zařízení můžete filtrovat:
  - **nepřiřazené**
  - **libovolné**
  - **&lt;název profilu&gt;**
4. Vyberte zařízení, která chcete přiřadit. Zaškrtnutím políčka nad sloupcem můžete vybrat až 1000 zobrazených zařízení a potom klikněte na **Přiřadit**. Pokud chcete registrovat více než 1 000 zařízení, opakujte postup, dokud nebudou mít všechna zařízení přiřazený profil registrace.

  ![Snímek obrazovky s tlačítkem Přiřadit pro přiřazení profilu programu registrace na portálu Intune](media/dep-profile-assignment.png)

## <a name="end-user-experience-with-managed-devices"></a>Správa zařízení z pohledu koncového uživatele

Teď můžete zařízení rozdělit mezi uživatele. U zařízení s přidruženými uživateli je potřeba, aby měl každý uživatel přiřazenu licenci Intune. Aktivované zařízení nemůže použít profil registrace, dokud se neprovede obnovení továrního nastavení zařízení. Po zapnutí zařízení s iOSem spravovaného prostřednictvím programu registrace se uživateli na zařízení zobrazí následující možnosti:  

1. **Set Up iOS device** (Nastavit zařízení s iOS) – uživatelé mají na výběr z těchto možností:
  - **Set Up as New device** (Nastavit jako nové zařízení)
  - **Restore from iCloud Backup** (Obnovit ze zálohy v iCloudu)
  - **Restore from iCloud Backup** (Obnovit ze zálohy v iTunes)
2. Uživatelé budou informováni, že **&lt;vaše organizace&gt; bude zařízení automaticky konfigurovat.** K dispozici jsou také další podrobnosti o konfiguraci:

  **Configuration allows &lt;Your Organization&gt; to manage this device over the air. (Konfigurace umožňuje vaší organizaci spravovat toto zařízení bezdrátově.)**

  **An administrator can help you set up email and network accounts, install and configure apps, and manage settings remotely.** (Správce vám na dálku pomůže nastavit e-mailové a síťové účty, instalovat a konfigurovat aplikace a spravovat nastavení.)

  **An administrator may disable features, install and remove apps, monitor and restrict your Internet traffic and remotely erase this device.** (Správce může zakázat funkce, instalovat a odebírat aplikace, monitorovat a omezit váš internetový provoz nebo na dálku zařízení vymazat.)

  **Configuration is provided by:<br> (Konfiguraci zajišťuje:) &lt;Your organization&gt; iOS Team<br> (iOS tým vaší organizace) &lt;Address&gt; (Adresa)**

3. Uživatelům se zobrazí výzva k zadání uživatelského jména a hesla k pracovnímu nebo školnímu účtu.
4. Uživatelům se zobrazí výzva k zadání Apple ID. Apple ID je potřeba k instalaci aplikace Portál společnosti Intune a dalších aplikací. Po zadání přihlašovacích údajů se zařízení nainstaluje. Profil správy nebude možné odebrat. Profil správy v Intune se na zařízení zobrazí v **Nastavení** > **Obecné** > **Správa zařízení**.

Teď mohou uživatelé dokončit nastavení zařízení ve vlastnictví společnosti. Mohou použít Portál společnosti Intune nebo Pomocníka s nastavením Apple.
