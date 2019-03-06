---
title: Registrace programu Apple School Manager pro zařízení s Iosem
titleSuffix: Microsoft Intune
description: Přečtěte si, jak pomocí Intune nastavit registraci programu Apple School Manager pro zařízení s iOSem vlastněná společností.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/06/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4c35a23e-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2d99712cfb972ae346c9254aac54feb5f4173a28
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57390303"
---
# <a name="set-up-ios-device-enrollment-with-apple-school-manager"></a>Nastavení registrace zařízení s iOSem pomocí Apple School Manageru

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Můžete nastavit Intune pro registraci zařízení s Iosem zakoupená prostřednictvím [Apple School Manageru](https://school.apple.com/) programu. Pomocí Intune s Apple School Managerem můžete registrovat velký počet zařízení s iOSem, aniž byste je museli uchopit do ruky. Když student nebo učitel zařízení zapne, Pomocník s nastavením provede předem nakonfigurovaná nastavení a zařízení se zaregistruje ke správě.

Při povolení registrace přes Apple School Manager budete používat portál Intune i portál Apple School Manager. Abyste mohli zařízení přiřadit do Intune ke správě, potřebujete seznam sériových čísel nebo čísla nákupních objednávek. Vytvoříte registrační profily DEP obsahující nastavení aplikovaná na zařízení během registrace.

Registraci přes Apple School Manager nejde používat s [programem registrace zařízení (DEP) společnosti Apple](device-enrollment-program-enroll-ios.md) ani se [správcem registrace zařízení](device-enrollment-manager-enroll.md).

**Požadavky**
- [Certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- [Autorita pro správu mobilních zařízení (MDM)](mdm-authority-set.md)
- [Certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- Při použití ADFS vyžaduje přidružení uživatelů [koncový bod WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints). [Další informace](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- Zařízení zakoupená z programu [Apple School Management](http://school.apple.com)

## <a name="get-an-apple-token-and-assign-devices"></a>Získání tokenu Apple a přiřazení zařízení

Než budete moct registrovat zařízení s iOSem vlastněná společností pomocí Apple School Manageru, potřebujete získat soubor tokenu (.p7m) od společnosti Apple. Tento token umožňuje Intune synchronizovat informace o zařízeních v Apple School Manageru. Token také umožňuje Intune odesílat společnosti Apple registrační profily a přiřazovat k těmto profilům zařízení. Na portálu společnosti Apple můžete také přiřadit sériová čísla zařízení pro správu.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-an-apple-token"></a>Krok 1. Stáhněte si certifikát veřejného klíče Intune, který je potřebný k vytvoření tokenu Apple.

1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny Programu registrace** > **Přidat**.

   ![Stažení tokenu programu registrace zařízení](./media/device-enrollment-program-enroll-ios/image01.png)

2. V okně **Token Programu registrace** zvolte **Stáhnout veřejný klíč** a stáhněte a místně uložte soubor šifrovacího klíče (.pem). Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple School Manager.
     ![Podokno Token Programu registrace zařízení](./media/device-enrollment-program-enroll-ios/image02.png)

### <a name="step-2-download-a-token-and-assign-devices"></a>Krok 2. Stáhněte si token a přiřaďte zařízení.
1. Zvolte **Vytvořit token prostřednictvím Apple School Manageru** a přihlaste se k Apple School pomocí Apple ID vaší společnosti. Toto Apple ID můžete použít k obnovení tokenu Apple School Manageru.
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

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Krok 3. Uložte si Apple ID, které jste použili k vytvoření tohoto tokenu.

V Intune na portálu Azure Portal zadejte Apple ID pro budoucí použití.

![Snímek obrazovky s Apple ID použitým k vytvoření tokenu programu registrace a přechodem na token programu registrace](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Krok 4. Nahrajte token.
V poli **Token Apple** přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Vytvořit**. S certifikátem Push Certificate může Intune registrovat a spravovat zařízení s iOSem a vynucovat zásady na zaregistrovaných mobilních zařízeních. Intune automaticky synchronizuje vaše zařízení Apple School Manageru z portálu společnosti Apple.

## <a name="create-an-apple-enrollment-profile"></a>Vytvoření registračního profilu Apple
Po nainstalování tokenu můžete vytvořit registrační profil pro zařízení Apple School. Registrační profil zařízení definuje nastavení, která se během registrace použijí pro skupinu zařízení.

1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny Programu registrace**.
2. Vyberte token, zvolte **Profily** a potom zvolte **Vytvořit profil**.

3. V části **Vytvořit profil** zadejte **Název** a **Popis** profilu pro účely správy. Uživatelům se tyto údaje nezobrazí. Pole **Název** můžete využít k vytvoření dynamické skupiny v Azure Active Directory. Název profilu použijte k definování parametru enrollmentProfileName pro přiřazení zařízení s tímto registračním profilem. Přečtěte si další informace o [dynamických skupinách Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

    ![Název a popis profilu](./media/device-enrollment-program-enroll-ios/image05.png)

4. V části **Přidružení uživatele** zvolte, jestli se zařízení s tímto profilem musí registrovat s přiřazeným uživatelem nebo bez něj.
    - **Zaregistrovat s přidružením uživatele** – Tuto možnost zvolte pro zařízení, která patří uživatelům a chtějí pro služby, jako je instalace aplikací, používat portál společnosti. Tato možnost také umožňuje uživatelům ověřovat svoje zařízení pomocí portálu společnosti. Při použití ADFS vyžaduje přidružení uživatelů [koncový bod WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints). [Další informace](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).   Režim Sdílený iPad programu Apple School Manager vyžaduje registraci uživatele bez přidružení uživatele.

    - **Zaregistrovat bez přidružení uživatele** – Tuto možnost zvolte pro zařízení nespojená s jedním uživatelem, například sdílená zařízení. Použijte ji pro zařízení určená k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, jako je aplikace Portál společnosti, nefungují.

5. Pokud jste zvolili **Zaregistrovat s přidružením uživatele**, máte možnost povolit, aby se uživatelé ověřovali pomocí portálu společnosti místo v Průvodci nastavením společnosti Apple.

    ![Ověření pomocí portálu společnosti](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Pokud chcete provést některou z následujících akcí, nastavte možnost **ověření na Portálu společnosti místo v Průvodci nastavením Applu** na **Ano**.
    >    - Použít vícefaktorové ověřování.
    >    - Zobrazit výzvu uživatelům, pokud při prvním přihlášení potřebují změnit heslo.
    >    - Zobrazit výzvu uživatelům, aby při registraci resetovali neplatná hesla.
    >
    > Tato možnost není podporovaná, pokud se k ověření použije Průvodce nastavením společnosti Apple.

6. Zvolte **Nastavení správy zařízení** a vyberte, jestli mají být zařízení, která používají tento profil, pod dohledem nebo ne.
    U zařízení **pod dohledem** je ve výchozím nastavení víc možností správy a je zakázaný zámek aktivace. Microsoft doporučuje program DEP používat jako mechanismus pro povolení režimu Pod dohledem zejména organizacím, které nasazují velké množství zařízení s iOSem.

    Uživatelé se dozvědí, že jejich zařízení jsou pod dohledem, dvěma způsoby:

   - Zamykací obrazovce se zobrazí oznámení: "Tento iPhone spravuje Contoso."
   - **Nastavení** > **Obecné** > **o** obrazovce se zobrazí oznámení: "Tento iPhone je pod dohledem. Společnost Contoso může monitorovat internetové přenosy a zařízení vyhledat.“

     > [!NOTE]
     > Zařízení zaregistrované bez dohledu se dá resetovat do stavu pod dohledem jenom pomocí Apple Configuratoru. Resetování zařízení tímto způsobem vyžaduje připojení zařízení s iOSem k Macu pomocí kabelu USB. Další informace na toto téma získáte v [dokumentaci Apple Configuratoru](http://help.apple.com/configurator/mac/2.3).

7. Zvolte, jestli chcete pro zařízení, která používají tento profil, uzamčenou registraci. **Uzamčená registrace** zakáže nastavení iOSu, která umožňují odebrání profilu správy z nabídky **Nastavení**. Po registraci zařízení nemůžete toto nastavení změnit bez vymazání zařízení. Taková zařízení musí mít režim správy **Pod dohledem** nastavený na *Ano*. 

8. Pokud chcete umožnit, aby se k registrovaným iPadům přihlašovalo více uživatelů pomocí spravovaného Apple ID, zvolte v části **Sdílený iPad** možnost **Ano** (tato možnost vyžaduje možnost **Zaregistrovat bez přidružení uživatele** a režim **Pod dohledem** nastavené na **Ano**). Spravovaná Apple ID se vytváří na portálu Apple School Manager. Další informace o [sdíleném iPadu](education-settings-configure-ios-shared.md) a [požadavcích Applu na sdílený iPad](https://help.apple.com/classroom/ipad/2.0/#/cad7e2e0cf56)

9. Zvolte, jestli chcete, aby zařízení, která používají tento profil, mohla **Synchronizovat s počítači**. Pokud vyberete **Povolit Apple Configurator podle certifikátu**, musíte zvolit certifikát v části **Certifikáty Apple Configuratoru**.

10. Pokud jste v předchozím kroku zvolili **Povolit Apple Configurator podle certifikátu**, zvolte certifikát Apple Configuratoru, který se má importovat.

11. Zvolte **OK**.

12. Vyberte **Nastavení Průvodce nastavením** a nakonfigurujte následující nastavení profilu: ![Nastavení přizpůsobení průvodce nastavením.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


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
    |          <strong>Přiblížení</strong>           |                                                                 V případě povolení Průvodce nastavením zobrazí během aktivace výzvu pro tuto službu.                                                                 |
    |          <strong>Siri</strong>           |                                                                 V případě povolení Průvodce nastavením zobrazí během aktivace výzvu pro tuto službu.                                                                 |
    |     <strong>Diagnostická data</strong>     |                                                                 V případě povolení Průvodce nastavením zobrazí během aktivace výzvu pro tuto službu.                                                                 |


13. Zvolte **OK**.

14. Pokud chcete profil uložit, zvolte **Vytvořit**.

## <a name="connect-school-data-sync"></a>Připojení služby School Data Sync
(Volitelné) Apple School Manager podporuje synchronizaci třídních seznamů do Azure Active Directory (AD) pomocí služby Microsoft School Data Sync (SDS). Pomocí SDS můžete synchronizovat jenom jeden token. Pokud pomocí School Data Sync nastavíte další token, odebere se SDS z tokenu, který měl SDS předtím. Nové připojení nahradí aktuální token. Pokud chcete použít službu SDS k synchronizaci školních dat, proveďte následující kroky.

1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny Programu registrace**.
2. Vyberte token Apple School Manageru a potom zvolte **Synchronizace školních dat**.
3. V části **Synchronizace školních dat** zvolte **Povolit**. Toto nastavení umožňuje službě Intune propojení se službou SDS v Office 365.
4. Pokud chcete povolit připojení mezi Apple School Managerem a Azure AD, zvolte možnost **Nastavit Microsoft School Data Sync**. Další informace o [jak nastavit službu School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
5. Klikněte na **Uložit** > **OK**.

## <a name="sync-managed-devices"></a>Synchronizace spravovaných zařízení

Až ke službě Intune přiřadíte oprávnění ke správě zařízení Apple School Manageru, synchronizujte Intune se službou Apple, aby se spravovaná zařízení zobrazila v Intune.

V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny Programu registrace** > zvolte token v seznamu > **Zařízení** > **Synchronizovat**. ![Snímek obrazovky s vybraným uzlem Zařízení Programu registrace a vybraným odkazem pro synchronizaci](./media/device-enrollment-program-enroll-ios/image06.png)

  Kvůli dodržení podmínek společnosti Apple, které se týkají přijatelných přenosů při registraci v programu, platí v Intune následující omezení:
  - Úplná synchronizace se nesmí pouštět častěji než jednou za sedm dní. Během úplné synchronizace Intune aktualizuje všechna sériová čísla Apple přiřazená Intune. Pokud se o úplnou synchronizaci pokusíte do sedmi dnů od předchozí úplné synchronizace, aktualizuje Intune jenom sériová čísla, která ještě nejsou v Intune.
  - Každá žádost o synchronizaci má 15 minut na dokončení. Po tuto dobu nebo do úspěšného vykonání požadavku je tlačítko **Synchronizovat** neaktivní.
  - Intune synchronizuje nová a odebraná zařízení se společností Apple každých 24 hodin.

>[!NOTE]
>V okně **Zařízení Programu registrace** můžete také přiřadit sériová čísla Apple School Manageru k profilům.

## <a name="assign-a-profile-to-devices"></a>Přiřazení profilu k zařízením
Zařízením Apple School Manageru spravovaným v Intune musíte před registrací přiřadit registrační profil.

1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny Programu registrace** > zvolte token v seznamu.
2. Zvolte **Zařízení** > zvolte zařízení v seznamu > **Přiřadit profil**.
3. V části **Přiřadit profil** zvolte profil pro zařízení a potom zvolte **Přiřadit**.

## <a name="distribute-devices-to-users"></a>Distribuce zařízení uživatelům

Povolili jste správu a synchronizaci mezi společností Apple a Intune a přiřadili jste profil, který umožní registraci zařízení Apple School. Teď můžete zařízení rozdělit mezi uživatele. Pokud je zařízení Apple School Manageru s iOSem zapnuté, zaregistruje se pro správu službou Intune. Pokud bylo zařízení aktivováno a používá se, nelze profil použít, dokud se zařízení nevymaže.
