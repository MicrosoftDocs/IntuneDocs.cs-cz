---
title: Registrace zařízení s iOSem – Program registrace zařízení
titleSuffix: Microsoft Intune
description: Naučte se registrovat zařízení s iOSem ve vlastnictví firmy pomocí Programu registrace zařízení (DEP).
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b03de8b2c5fca0f41a792e5004d74fe82e4a861d
ms.sourcegitcommit: 0f1a5d6e577915d2d748d681840ca04a0a2604dd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>Automatická registrace zařízení s iOSem pomocí Programu registrace zařízení společnosti Apple

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Toto téma vám pomůže povolit registraci zařízení s iOSem zakoupených prostřednictvím [Programu registrace zařízení (DEP)](https://deploy.apple.com) společnosti Apple. Můžete povolit registraci pomocí DEP pro velký počet zařízení, aniž byste je měli fyzicky v rukou. Zařízení jako iPhony a iPady můžete distribuovat přímo uživatelům. Když uživatel zařízení zapne, Pomocník s nastavením provede předem nakonfigurovaná nastavení a zařízení se zaregistruje ke správě.

Registraci do programu DEP můžete povolit na portálu Intune i na portálu DEP společnosti Apple. Abyste mohli zařízení přiřadit do Intune ke správě, potřebujete seznam sériových čísel nebo čísla nákupních objednávek. Vytvoříte registrační profily DEP obsahující nastavení aplikovaná na zařízení během registrace.

Registrace DEP mimochodem se [správcem registrace zařízení](device-enrollment-manager-enroll.md) nefunguje.

## <a name="what-is-supervised-mode"></a>Co je režim Pod dohledem?
Apple režim Pod dohledem představil v systému iOS 5. Zařízení s iOSem v režimu Pod dohledem je možné spravovat několika ovládacími prvky. Proto je zvlášť užitečný pro zařízení vlastněná společností. Intune podporuje konfiguraci zařízení do režimu Pod dohledem v rámci programu registrace zařízení Apple (DEP). 

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Požadavky
- Zařízení zakoupená v [Programu registrace zařízení společnosti Apple](http://deploy.apple.com)
- [Autorita pro správu mobilních zařízení (MDM)](mdm-authority-set.md)
- [Certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Získání tokenu DEP Apple

Abyste mohli zařízení s iOSem v programu DEP zaregistrovat, potřebujete od společnosti Apple token DEP (.p7m). Token umožňuje Intune synchronizovat informace o zařízeních v rámci DEP, která vaše společnost vlastní. Umožňuje také Intune odeslat společnosti Apple registrační profily a přiřazovat k těmto profilům zařízení.

Token DEP vytvoříte pomocí portálu DEP společnosti Apple. Pomocí portálu DEP také přiřadíte zařízení do Intune ke správě.

> [!NOTE]
> Když token odstraníte z klasického portálu Intune před migrací do Azure, může Intune obnovit odstraněný token DEP Apple. Token DEP můžete z portálu Azure Portal znovu odstranit. Token DEP můžete z portálu Azure Portal znovu odstranit.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Krok 1: Stáhněte si certifikát veřejného klíče Intune, který je potřebný k vytvoření tokenu.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace** > **Přidat**.

    ![Stažení tokenu programu registrace zařízení](./media/device-enrollment-program-enroll-ios/image01.png)

2. Výběrem možnosti **Souhlasím** udělte Microsoftu oprávnění k odesílání informací o uživatelích a zařízeních do společnosti Apple.

   ![Snímek obrazovky s podoknem Token Programu registrace v pracovním prostoru Certifikáty Apple pro stažení veřejného klíče](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Vyberte **Stáhnout veřejný klíč** a stáhněte si a místně uložte soubor šifrovacího klíče (.pem). Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Device Enrollment Program.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Krok 2: Pomocí klíče si stáhněte token od společnosti Apple.

1. Pokud chcete otevřít portál Programu registrace zařízení Apple (DEP), zvolte **Vytvořit token pro Program registrace zařízení Apple** a přihlaste se pomocí firemního Apple ID. Toto Apple ID můžete použít k obnovení tokenu DEP.
2.  Na [portálu společnosti Apple pro nasazení programů](https://deploy.apple.com) vyberte **Začínáme**. Otevře se **Program registrace zařízení**.

3. Na stránce pro **správu serverů** zvolte, že chcete **přidat server MDM**.
4. Zadejte **název serveru MDM** a zvolte **Další**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Není to název serveru Microsoft Intune ani jeho URL.

5. Otevře se dialogové okno pro **přidání&lt;názvu serveru&gt;**, ve kterém se zobrazí výzva, abyste **nahráli svůj veřejný klíč**. Vyberte **Zvolit soubor**, abyste mohli nahrát soubor .pem, a pak zvolte **Další**.

6. Přejděte na **Deployment Programs** (Programy nasazení) &gt; **Device Enrollment Program** (Program registrace zařízení) &gt; **Manage Devices** (Spravovat zařízení).
7. V části se **způsobem výběru zařízení** určete způsob identifikace zařízení:
    - **Sériové číslo**
    - **Číslo objednávky**
    - **Nahrát soubor CSV**

   ![Snímek obrazovky s výběrem zařízení podle sériového čísla, nastavením volby akce na přiřazení serveru a výběrem názvu serveru](./media/enrollment-program-token-specify-serial.png)

8. V možnosti **Vybrat akci** vyberte **Přiřadit k serveru**, vyberte &lt;název_serveru&gt; zadaný pro Microsoft Intune a pak zvolte **OK**. Portál Apple přiřadí daná zařízení k serveru Intune, aby bylo možné je spravovat, a pak zobrazí zprávu o **dokončení přiřazení**.

   Na portálu Apple přejděte na **Programy nasazení** &gt; **Program registrace zařízení** &gt; **Zobrazit historii přiřazení**. Zobrazí se seznam zařízení s přiřazeným serverem MDM.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Krok 3: Uložte si Apple ID, které jste použili k vytvoření tohoto tokenu.

V Intune na portálu Azure Portal zadejte Apple ID pro budoucí použití.

![Snímek obrazovky s Apple ID použitým k vytvoření tokenu programu registrace a přechodem na token programu registrace](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Krok 4: Nahrajte token.
V poli **Token Apple** přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Vytvořit**. S certifikátem Push Certificate může Intune registrovat a spravovat zařízení s iOSem a vynucovat zásady na zaregistrovaných mobilních zařízeních. Intune se automaticky synchronizuje s Apple, aby bylo možné zobrazit účet registračního programu.

## <a name="create-an-apple-enrollment-profile"></a>Vytvoření registračního profilu Apple

Po nainstalování tokenu můžete vytvořit registrační profil pro zařízení DEP. Registrační profil zařízení definuje nastavení, která se během registrace použijí pro skupinu zařízení.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace**.
2. Vyberte token, zvolte **Profily** a potom zvolte **Vytvořit profil**.
    ![Snímek obrazovky s vytvořením profilu](./media/device-enrollment-program-enroll-ios/image04.png)
3. V části **Vytvořit profil** zadejte **Název** a **Popis** profilu pro účely správy. Uživatelům se tyto údaje nezobrazí. Pole **Název** můžete využít k vytvoření dynamické skupiny v Azure Active Directory. Název profilu použijte k definování parametru enrollmentProfileName pro přiřazení zařízení s tímto registračním profilem. Přečtěte si další informace o [dynamických skupinách Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).
    ![Název a popis profilu](./media/device-enrollment-program-enroll-ios/image05.png)

4. V části **Přidružení uživatele** zvolte, jestli se zařízení s tímto profilem musí registrovat s přiřazeným uživatelem nebo bez něj.
    - **Zaregistrovat s přidružením uživatele** – Tuto možnost zvolte pro zařízení, která patří uživatelům a chtějí pro služby, jako je instalace aplikací, používat portál společnosti. Tato možnost také umožňuje uživatelům ověřovat svoje zařízení pomocí portálu společnosti. Přidružení uživatelů vyžaduje [koncový bod WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints). [Přečtěte si další informace](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Zaregistrovat bez přidružení uživatele** – Tuto možnost zvolte pro zařízení nespojená s jedním uživatelem. Použijte ji pro zařízení určená k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, jako je aplikace Portál společnosti, nefungují.

5. Pokud jste zvolili **Zaregistrovat s přidružením uživatele**, máte možnost povolit, aby se uživatelé ověřovali pomocí portálu společnosti místo v Průvodci nastavením společnosti Apple.

    ![Ověření pomocí portálu společnosti](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Vícefaktorové ověřování nefunguje během registrace DEP, pokud máte vlastnosti profilu nastavené na **Zaregistrovat s přidružením uživatele**. Po registraci vícefaktorové ověřování na zařízeních funguje podle očekávání. Zařízení nemůžou vyzvat uživatele, kteří při prvním přihlášení potřebují změnit své heslo. Výzva k resetování hesla se během registrace nezobrazí ani uživatelům, kterým vypršela platnost hesla. Uživatelé musí heslo resetovat z jiného zařízení.

6. Zvolte **Nastavení správy zařízení** a vyberte, jestli mají být zařízení, která používají tento profil, pod dohledem nebo ne.
    U zařízení **pod dohledem** je ve výchozím nastavení víc možností správy a je zakázaný zámek aktivace. Microsoft doporučuje program DEP používat jako mechanismus pro povolení režimu Pod dohledem zejména organizacím, které nasazují velké množství zařízení s iOSem.

    Uživatelé se dozvědí, že jejich zařízení jsou pod dohledem, dvěma způsoby:

   - Na zamykací obrazovce se zobrazí oznámení: „Tento iPhone spravuje Contoso.“
   - Na obrazovce **Nastavení** > **Obecné** > **O produktu** je uvedeno: „Tento iPhone je pod dohledem. Společnost Contoso může monitorovat internetové přenosy a zařízení vyhledat.“

     > [!NOTE]
     > Zařízení zaregistrované bez dohledu se dá resetovat do stavu pod dohledem jenom pomocí Apple Configuratoru. Resetování zařízení tímto způsobem vyžaduje připojení zařízení s iOSem k Macu pomocí kabelu USB. Další informace na toto téma získáte v [dokumentaci Apple Configuratoru](http://help.apple.com/configurator/mac/2.3).

7. Zvolte, jestli chcete pro zařízení, která používají tento profil, uzamčenou registraci. **Uzamčená registrace** zakáže nastavení iOSu, která umožňují odebrání profilu správy z nabídky **Nastavení**. Po registraci zařízení nemůžete toto nastavení změnit bez obnovení továrního nastavení zařízení. Taková zařízení musí mít režim správy **Pod dohledem** nastavený na *Ano*. 

8. Zvolte, jestli chcete, aby zařízení, která používají tento profil, mohla **Synchronizovat s počítači**. Pokud vyberete **Povolit Apple Configurator podle certifikátu**, musíte zvolit certifikát v části **Certifikáty Apple Configuratoru**.

9. Pokud jste v předchozím kroku zvolili **Povolit Apple Configurator podle certifikátu**, zvolte certifikát Apple Configuratoru, který se má importovat.

10. Vyberte **OK**.

11. Zvolte **Nastavení Průvodce nastavením** a nakonfigurujte následující nastavení profilu: ![Přizpůsobení Průvodce nastavením](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png).


    |                 Nastavení                  |                                                                                               Popis                                                                                               |
    |------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |     <strong>Název oddělení</strong>     |                                                             Zobrazí se, když uživatelé klepnou při aktivaci na <strong>O konfiguraci</strong>.                                                              |
    |    <strong>Telefon na oddělení</strong>     |                                                          Zobrazí se, když uživatel při aktivaci klikne na tlačítko <strong>Potřebuji nápovědu</strong>.                                                          |
    | <strong>Možnosti Průvodce nastavením</strong> |                                                     Následující nastavení jsou volitelná a dají se nastavit později v nabídce <strong>Nastavení</strong> systému iOS.                                                      |
    |        <strong>Heslo</strong>         | Při aktivaci se zobrazí výzva k zadání hesla. Vyžaduje vždy heslo, pokud zařízení nebude zabezpečené nebo nebude mít přístup kontrolovaný jiným způsobem (třeba pomocí celoobrazovkového režimu, který omezuje zařízení na jednu aplikaci). |
    |    <strong>Zjišťování polohy</strong>    |                                                                 V případě povolení Průvodce nastavením zobrazí během aktivace výzvu pro tuto službu.                                                                  |
    |         <strong>Obnovení</strong>         |                                                                Pokud je toto nastavení povolené, Průvodce nastavením zobrazí při aktivaci výzvu k zálohování na iCloud.                                                                 |
    |   <strong>iCloud a Apple ID</strong>   |                         Pokud je toto nastavení povolené, Průvodce nastavením vyzve uživatele k přihlášení Apple ID a na obrazovce Aplikace a data bude možné obnovit zařízení ze zálohy na iCloudu.                         |
    |  <strong>Podmínky a ujednání</strong>   |                                                   V případě povolení Průvodce nastavením vyzve uživatele k přijetí podmínek a ujednání společnosti Apple během aktivace.                                                   |
    |        <strong>Touch ID</strong>         |                                                                 V případě povolení Průvodce nastavením zobrazí během aktivace výzvu pro tuto službu.                                                                 |
    |        <strong>Apple Pay</strong>        |                                                                 V případě povolení Průvodce nastavením zobrazí během aktivace výzvu pro tuto službu.                                                                 |
    |          <strong>Lupa</strong>           |                                                                 V případě povolení Průvodce nastavením zobrazí během aktivace výzvu pro tuto službu.                                                                 |
    |          <strong>Siri</strong>           |                                                                 V případě povolení Průvodce nastavením zobrazí během aktivace výzvu pro tuto službu.                                                                 |
    |     <strong>Diagnostická data</strong>     |                                                                 V případě povolení Průvodce nastavením zobrazí během aktivace výzvu pro tuto službu.                                                                 |


12. Vyberte **OK**.

13. Pokud chcete profil uložit, zvolte **Vytvořit**.

## <a name="sync-managed-devices"></a>Synchronizace spravovaných zařízení
Teď, když má Intune oprávnění spravovat vaše zařízení, můžete synchronizovat Intune s Apple, aby se spravovaná zařízení zobrazila v Intune na portálu Azure Portal.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny Programu registrace** > zvolte token v seznamu > **Zařízení** > **Synchronizovat**. ![Snímek obrazovky s vybraným uzlem Zařízení Programu registrace a vybraným odkazem pro synchronizaci](./media/device-enrollment-program-enroll-ios/image06.png)

   Kvůli dodržení podmínek společnosti Apple, které se týkají přijatelných přenosů při registraci v programu, platí v Intune následující omezení:
   - Úplná synchronizace se nesmí pouštět častěji než jednou za sedm dní. Během úplné synchronizace Intune aktualizuje všechna sériová čísla Apple přiřazená Intune. Pokud se o úplnou synchronizaci pokusíte do sedmi dnů od předchozí úplné synchronizace, aktualizuje Intune jenom sériová čísla, která ještě nejsou v Intune.
   - Každá žádost o synchronizaci má 15 minut na dokončení. Po tuto dobu nebo do úspěšného vykonání požadavku je tlačítko **Synchronizovat** neaktivní.
   - Intune synchronizuje nová a odebraná zařízení se společností Apple každých 24 hodin.

## <a name="assign-an-enrollment-profile-to-devices"></a>Přiřazení profilu registrace zařízením
Než se můžou zařízení zaregistrovat, musíte přiřadit profil programu registrace.

>[!NOTE]
>Sériová čísla můžete profilům také přiřadit v okně **sériových čísel Apple**.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny Programu registrace** > zvolte token v seznamu.
2. Zvolte **Zařízení** > zvolte zařízení v seznamu > **Přiřadit profil**.
3. V části **Přiřadit profil** zvolte profil pro zařízení a potom zvolte **Přiřadit**.

### <a name="assign-a-default-profile"></a>Přiřazení výchozího profilu

Můžete si vybrat výchozí profil, který se má použít pro všechna zařízení, která se registrují s konkrétním tokenem.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny Programu registrace** > zvolte token v seznamu.
2. Zvolte **Nastavit výchozí profil**, v rozevíracím seznamu zvolte profil a potom zvolte **Uložit**. Tento profil se použije pro všechna zařízení, která se registrují s tímto tokenem.

## <a name="distribute-devices"></a>Distribuujte zařízení.
Povolili jste správu a synchronizaci mezi společností Apple a Intune a přiřadili jste profil, který umožní registraci zařízení DEP. Teď můžete zařízení rozdělit mezi uživatele. U zařízení s přidruženými uživateli je potřeba, aby měl každý uživatel přiřazenu licenci Intune. Zařízení bez přidružení uživatele vyžadují licenci zařízení. Aktivované zařízení nemůže použít profil registrace, dokud se neprovede obnovení továrního nastavení zařízení.

Přečtěte si téma [Registrace zařízení s iOSem v Intune pomocí programu registrace zařízení](/intune-user-help/enroll-your-device-dep-ios).


