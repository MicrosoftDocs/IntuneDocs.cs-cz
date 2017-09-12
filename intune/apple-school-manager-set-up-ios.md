---
title: "Nastavení registrace programu Apple School Manager pro zařízení s iOSem"
titlesuffix: Azure portal
description: "Přečtěte si, jak pomocí Intune nastavit registraci programu Apple School Manager pro zařízení s iOSem vlastněná společností.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b3ecc9af91d1a78f84dd6d4b8f47f0bf3e8c742
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Povolení registrace zařízení s iOSem pomocí Apple School Manageru

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Toto téma vám pomůže zprovoznit registraci zařízení s iOSem zakoupená prostřednictvím programu [Apple School Manager](https://school.apple.com/). Pomocí Intune s Apple School Managerem můžete registrovat velký počet zařízení s iOSem, aniž byste je museli uchopit do ruky. Když student nebo učitel zařízení zapne, Pomocník s nastavením provede předem nakonfigurovaná nastavení a zařízení se zaregistruje ke správě.

Při povolení registrace přes Apple School Manager budete používat portál Intune i portál Apple School Manager. Abyste mohli zařízení přiřadit do Intune ke správě, potřebujete seznam sériových čísel nebo čísla nákupních objednávek. Vytvoříte registrační profily DEP obsahující nastavení aplikovaná na zařízení během registrace.

Mimochodem registraci přes Apple School Manager nejde používat s [programem registrace zařízení (DEP) společnosti Apple](device-enrollment-program-enroll-ios.md) ani se [správcem registrace zařízení](device-enrollment-manager-enroll.md).

**Požadavky**
- [Certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- [Autorita pro správu mobilních zařízení (MDM)](mdm-authority-set.md)
- [Certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- Přidružení uživatelů vyžaduje [koncový bod WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints). [Přečtěte si další informace](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- Zařízení zakoupená z programu [Apple School Management](http://school.apple.com)

**Kroky registrace Apple School Manageru**
1. [Získání tokenu Apple School Manageru a přiřazení zařízení](#get-the-apple-token-and-assign-devices)
2. [Vytvoření registračního profilu](#create-an-apple-enrollment-profile)
3. [Připojení služby School Data Sync](#connect-school-data-sync) (volitelné)
4. [Synchronizace zařízení spravovaných Apple School Managerem](#sync-managed-devices)
5. [Přiřazení profilu Apple School Manageru k zařízením](#assign-a-profile-to-devices)
6. [Distribuce zařízení uživatelům](#distribute-devices-to-users)

>[!NOTE]
>Při registraci na zařízeních spravovaných Apple School Managerem s přidružením uživatelů nefunguje vícefaktorové ověřování (MFA). Po registraci vícefaktorové ověřování na těchto zařízeních funguje podle očekávání. Po registraci vícefaktorové ověřování na zařízeních funguje podle očekávání. Zařízení nemůžou vyzvat uživatele, kteří při prvním přihlášení potřebují změnit své heslo. Výzva k resetování hesla se během registrace nezobrazí ani uživatelům, kterým vypršela platnost hesla. Uživatelé musí heslo resetovat z jiného zařízení.


## <a name="get-the-apple-token-and-assign-devices"></a>Získání tokenu Apple a přiřazení zařízení

Než budete moct registrovat zařízení s iOSem vlastněná společností pomocí Apple School Manageru, potřebujete získat soubor tokenu (.p7m) od společnosti Apple. Tento token umožňuje Intune synchronizovat informace o zařízeních v Apple School Manageru. Token také umožňuje Intune odesílat společnosti Apple registrační profily a přiřazovat k těmto profilům zařízení. Na portálu společnosti Apple můžete také přiřadit sériová čísla zařízení pro správu.

**Krok 1: Stáhněte si certifikát veřejného klíče Intune, který je potřebný k vytvoření tokenu Apple.**<br>
1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** a pak zvolte **Token Programu registrace**.

  ![Snímek obrazovky s podoknem Token Programu registrace v pracovním prostoru Certifikáty Apple pro stažení veřejného klíče](./media/enrollment-program-token-download.png)

2. V okně **Token Programu registrace** zvolte **Stáhnout veřejný klíč** a stáhněte a místně uložte soubor šifrovacího klíče (.pem). Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple School Manager.

**Krok 2: Stáhněte si token a přiřaďte zařízení.**<br>
1. Zvolte **Vytvořit token prostřednictvím Apple School Manageru** a přihlaste se pomocí Apple ID vaší společnosti. Toto Apple ID můžete použít k obnovení tokenu Apple School Manageru.
2.  Na portálu [Apple School Manager](https://school.apple.com) přejděte na **MDM Servers** (MDM servery) a vpravo nahoře zvolte **Add MDM Server** (Přidat MDM server).
3.  Zadejte **název MDM serveru**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Není to název serveru Microsoft Intune ani jeho URL.
   ![Snímek obrazovky portálu Apple School Manager s vybranou možností Sériové číslo](./media/asm-server-assignment.png)

4.  Na portálu společnosti Apple zvolte **Upload File...** (Nahrát soubor...), vyhledejte soubor .pem a vpravo dole zvolte **Save MDM Server** (Uložit MDM server).
5.  Zvolte **Get Token** (Získat token) a stáhněte si soubor tokenu serveru (.p7m) do svého počítače.
6. Přejděte na **Device Assignments** (Přiřazení zařízení) a **vyberte zařízení** pomocí možností **Serial Numbers** (Sériová čísla), **Order Number** (Číslo objednávky) nebo **Upload CSV File** (Nahrát CSV soubor).
     ![Snímek obrazovky portálu Apple School Manager s vybranou možností Sériové číslo](./media/asm-device-assignment.png)
7.  Zvolte akci **Assign to Server** (Přiřadit k serveru) a zvolte **MDM Server**, který jste vytvořili.
8. Určete, jak **Vybrat zařízení**, a pak zadejte informace o zařízení a podrobnosti.
9. Zvolte **Přiřadit k serveru**, zvolte &lt;název_serveru&gt; zadaný pro Microsoft Intune a potom zvolte **OK**.

**Krok 3: Zadejte Apple ID, které jste použili k vytvoření tokenu Apple School Manageru.**<br>Toto ID se má použít k obnovení tokenu Apple School Manageru a je uloženo pro budoucí použití.

![Snímek obrazovky s Apple ID použitým k vytvoření tokenu programu registrace a přechodem na token programu registrace](./media/enrollment-program-token-apple-id.png)

**Krok 4: Vyhledejte a nahrajte svůj token.**<br>
Přejděte k souboru certifikátu (p7m), zvolte **Otevřít** a pak zvolte **Nahrát**. Intune automaticky synchronizuje vaše zařízení Apple School Manageru z portálu společnosti Apple.

## <a name="create-an-apple-enrollment-profile"></a>Vytvoření registračního profilu Apple
Registrační profil zařízení definuje nastavení, která se během registrace použijí pro skupinu zařízení.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** a pak zvolte **Registrace Apple**.
2. V části **Program registrace** zvolte **Profily Programu registrace**.
3. V okně **Profily Programu registrace** zvolte **Vytvořit**.
4. V okně **Vytvořit registrační profil** zadejte **název** a **popis** profilu, který se zobrazí v Intune.
5. V části **Přidružení uživatele** zvolte, jestli se zařízení s tímto profilem budou registrovat s přidružením uživatele nebo bez.

 - **Zaregistrovat s přidružením uživatele** – během instalace přidruží zařízení k uživateli.

  Režim Sdílený iPad programu Apple School Manager vyžaduje registraci uživatele bez přidružení uživatele.

 - **Zaregistrovat bez přidružení uživatele** – zvolte pro zařízení nespojená s jedním uživatelem, například nesdílená zařízení. Použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, jako je aplikace Portál společnosti, nefungují.

6. Zvolte **Nastavení správy zařízení**. Tyto položky jsou nastaveny při aktivaci a jejich změna vyžaduje obnovení továrního nastavení. nakonfigurujte následující nastavení profilu a potom zvolte **Uložit**:

  ![Snímek obrazovky s výběrem režimu správy. Zařízení má následující nastavení: Pod dohledem, Uzamčená registrace, Povolit párování nastaveno na Zamítnout vše. Možnost Certifikáty Apple Configuratoru je pro nový profil programu registrace zobrazena šedě.](./media/enrollment-program-profile-mode.png)

    - **Pod dohledem** – Režim, který nabízí více možností správy a ve výchozím nastavení má zakázaný zámek aktivace. Pokud políčko nezaškrtnete, budete mít omezené možnosti správy.

     - **Uzamčená registrace** – Vyžaduje režim správy Pod dohledem. Zakáže nastavení iOSu, která by mohla umožnit odebrání profilu správy. Pokud políčko nezaškrtnete, půjde profil správy odebrat z nabídky Nastavení.
   - **Sdílený iPad** – (Vyžaduje režimy **Zaregistrovat bez přidružení uživatele** a **Pod dohledem**.) Umožňuje více uživatelům přihlásit se k zaregistrovaným iPadům pomocí spravovaného Apple ID. Spravovaná Apple ID se vytváří na portálu Apple School Manager. Přečtěte si další informace o [sdíleném iPadu](education-settings-configure-ios-shared.md).
   >[!NOTE]
   >Pokud je **Přidružení uživatele** nastavené na **S přidružením uživatele** nebo je režim **Pod dohledem** nastavený na **Vypnuto**, je režim Sdílený iPad pro registrační profil zakázaný.

        - **Maximum Cached Users** - (Requires **Shared iPad** = **Yes**) Creates a partition on the device for each user. The recommended value is the number of students likely to use the device over a period of time. For example, if six students use the device regularly during the week, set this number to six.  

    - **Povolit párování** – Určuje, jestli se zařízení s iOSem můžou synchronizovat s počítači. Pokud vyberete **Povolit Apple Configurator podle certifikátu**, musíte zvolit certifikát v části **Certifikáty Apple Configuratoru**.

      - **Certifikáty Apple Configuratoru** – Pokud jste v části **Povolit párování** zvolili **Povolit Apple Configurator podle certifikátu**, vyberte certifikát Apple Configuratoru, který chcete importovat.

7. Zvolte **Nastavení Pomocníka s nastavením**, nakonfigurujte následující nastavení profilu a potom zvolte **Uložit**:

    - **Název oddělení** – Zobrazí se, když uživatelé klepnou při aktivaci na **O konfiguraci**.

    - **Telefon na oddělení** – Zobrazí se, když uživatel při aktivaci klikne na tlačítko Potřebuji nápovědu.
    - **Možnosti Pomocníka s nastavením** – Nastavení, která nebyla provedena v možnostech Pomocníka s nastavením, je možné nastavit později v nabídce **Nastavení** systému iOS.
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

8. Uložte nastavení profilu tak, že v okně **Vytvořit registrační profil** zvolíte **Vytvořit**.

## <a name="connect-school-data-sync"></a>Připojení služby School Data Sync
(Volitelné) Apple School Manager podporuje synchronizaci třídních seznamů do Azure Active Directory (AD) pomocí služby Microsoft School Data Sync (SDS). Pokud chcete použít službu SDS k synchronizaci školních dat, proveďte následující kroky.

1. V okně **Token Programu registrace** zvolte buď modrou informační zprávu, nebo možnost **Připojit SDS**.
2. Zvolte **Povolit službě Microsoft School Data Sync používat tento token** a nastavte hodnotu **Povolit**. Toto nastavení umožňuje službě Intune propojení se službou SDS v Office 365.
3. Pokud chcete povolit připojení mezi Apple School Managerem a Azure AD, zvolte možnost **Nastavit Microsoft School Data Sync**. Další informace o [jak nastavit službu School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Kliknutím na tlačítko **OK** uložte nastavení a pokračujte.

## <a name="sync-managed-devices"></a>Synchronizace spravovaných zařízení
Když jste službě Intune přiřadili oprávnění ke správě zařízení Apple School Manageru, můžete Intune synchronizovat se službou Apple, aby se spravovaná zařízení zobrazila v Intune.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** a pak zvolte **Registrace Apple**.
2. V části **Zařízení Programu registrace** vyberte **Synchronizovat**. Indikátor průběhu vám ukáže dobu, jakou budete muset počkat před dalším vyžádáním synchronizace.
3. V okně **Synchronizovat** vyberte **Požadovat synchronizaci**. Indikátor průběhu vám ukáže dobu, jakou budete muset počkat před dalším vyžádáním synchronizace.

  ![Snímek obrazovky synchronizačního okna s vybraným odkazem Požadovat synchronizaci](./media/enrollment-program-device-request-sync.png)

  Pro dosažení souladu s podmínkami společnosti Apple pro přijatelné přenosy platí v Intune následující omezení:
   -    Úplná synchronizace se nesmí pouštět častěji než jednou za sedm dní. Během úplné synchronizace Intune aktualizuje všechna sériová čísla, která společnost Apple přiřadila Intune, bez ohledu na jejich dřívější synchronizaci. Pokud se o úplnou synchronizaci pokusíte do sedmi dnů od předchozí úplné synchronizace, aktualizuje Intune jenom sériová čísla, která ještě nejsou v Intune.
   -    Každá žádost o synchronizaci má 15 minut na dokončení. Po tuto dobu nebo do úspěšného vykonání požadavku je tlačítko **Synchronizovat** neaktivní.

>[!NOTE]
>V okně **Zařízení Programu registrace** můžete také přiřadit sériová čísla Apple School Manageru k profilům.

## <a name="assign-a-profile-to-devices"></a>Přiřazení profilu k zařízením
Zařízením Apple School Manageru spravovaným v Intune musíte před registrací přiřadit registrační profil.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** a pak zvolte **Profily Programu registrace**.
2. V seznamu **Profily Programu registrace** zvolte profil, který chcete zařízením přiřadit, a pak zvolte **Přiřazení zařízení**.

 ![Snímek obrazovky přiřazení zařízení s vybranou možností Přiřadit.](./media/enrollment-program-device-assign.png)

3. Zvolte **Přiřadit** a pak zvolte zařízení Apple School Manageru, ke kterým chcete tento profil přiřadit. Dostupná zařízení můžete filtrovat:
  - **nepřiřazené**
  - **libovolné**
  - **&lt;název profilu&gt;**
4. Vyberte zařízení, která chcete přiřadit. Zaškrtávací políčko nad sloupcem umožňuje vybrat až 1 000 uvedených zařízení. Klikněte na tlačítko **Přiřadit**. Pokud chcete registrovat více než 1 000 zařízení, opakujte postup, dokud nebudou mít všechna zařízení přiřazený profil registrace.

  ![Snímek obrazovky s tlačítkem Přiřadit pro přiřazení profilu programu registrace v Intune](media/dep-profile-assignment.png)

## <a name="distribute-devices-to-users"></a>Distribuce zařízení uživatelům

Zařízení patřící společnosti teď můžete distribuovat uživatelům. Pokud je zařízení Apple School Manageru s iOSem zapnuté, zaregistruje se pro správu službou Intune. Pokud bylo zařízení aktivováno a používá se, nemůže být profil použit, dokud nebude zařízení obnoveno do továrního nastavení.
