---
title: "Nastavení registrace programu Apple School Manager pro zařízení s iOSem"
titleSuffix: Intune on Azure
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
ms.openlocfilehash: 7079a22afc04b5674eb8f12a2833961e86939a28
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/03/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Povolení registrace zařízení s iOSem pomocí Apple School Manageru

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Toto téma pomáhá správcům IT povolit registraci zařízení s iOSem zakoupená prostřednictvím programu [Apple School Manager](https://school.apple.com/). Microsoft Intune umožňuje vzdáleně nasadit registrační profil, který zaregistruje zařízení Apple School Manageru pro správu. Správce se žádného spravovaného zařízení nemusí vůbec dotknout. Registrační profil obsahuje nastavení správy, která se v zařízeních použijí během registrace, včetně možností Pomocníka s nastavením.

**Kroky registrace Apple School Manageru**
1. [Získání tokenu Apple School Manageru a přiřazení zařízení](#get-the-apple-token-and-assign-devices)
2. [Vytvoření registračního profilu](#create-an-apple-enrollment-profile)
3. [Připojení služby School Data Sync](#connect-school-data-sync) (volitelné)
4. [Synchronizace zařízení spravovaných Apple School Managerem](#sync-managed-devices)
5. [Přiřazení profilu Apple School Manageru k zařízením](#assign-a-profile-to-devices)
6. [Distribuce zařízení uživatelům](#distribute-devices-to-users)

>[!NOTE]
>Registraci Apple School Manageru nejde použít s [DEP společnosti Apple](device-enrollment-program-enroll-ios.md) ani se [správcem registrace zařízení](device-enrollment-manager-enroll.md).

## <a name="get-the-apple-token-and-assign-devices"></a>Získání tokenu Apple a přiřazení zařízení

Než budete moct registrovat zařízení s iOSem vlastněná společností pomocí Apple School Manageru, potřebujete získat soubor tokenu (.p7m) od společnosti Apple. Tento token umožňuje Intune synchronizovat informace o zařízeních v Apple School Manageru. Token také umožňuje Intune odesílat společnosti Apple registrační profily a přiřazovat k těmto profilům zařízení. Na portálu společnosti Apple můžete také přiřadit sériová čísla zařízení pro správu.

**Požadavky**
- [Certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- Registrace do [Apple School Manageru](http://school.apple.com)

**Krok 1: Stáhněte si certifikát veřejného klíče Intune, který je potřebný k vytvoření tokenu Apple.**<br>
1. Na portálu [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** a pak vyberte **Token Programu registrace**.
2. V okně **Token Programu registrace** vyberte **Stáhnout veřejný klíč** a stáhněte a místně uložte soubor šifrovacího klíče (.pem). Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple School Manager.

**Krok 2: Stáhněte si token a přiřaďte zařízení.**<br>
Vyberte **Vytvořit token prostřednictvím Apple School Manageru** a přihlaste se pomocí Apple ID vaší společnosti. Toto Apple ID můžete použít k obnovení tokenu Apple School Manageru.

   1.  Na portálu [Apple School Manager](https://school.apple.com) přejděte na **MDM Servers** (MDM servery) a vpravo nahoře vyberte **Add MDM Server** (Přidat MDM server).
   2.  Zadejte **název MDM serveru**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Není to název serveru Microsoft Intune ani jeho URL.
   3.  Na portálu společnosti Apple vyberte **Upload File...** (Nahrát soubor...), vyhledejte soubor .pem a vpravo dole vyberte **Save MDM Server** (Uložit MDM server).
   4.  Vyberte **Get Token** (Získat token) a stáhněte si soubor tokenu serveru (.p7m) do svého počítače.
   5. Přejděte na **Device Assignments** (Přiřazení zařízení) a **vyberte zařízení** pomocí možností **Serial Numbers** (Sériová čísla), **Order Number** (Číslo objednávky) nebo **Upload CSV File** (Nahrát CSV soubor).
   6.   Vyberte akci **Assign to Server** (Přiřadit k serveru) a vyberte **MDM Server**, který jste vytvořili.
   7. Určete, jak **Vybrat zařízení**, a pak zadejte informace o zařízení a podrobnosti.
   8. Zvolte **Přiřadit k serveru**, zvolte &lt;název_serveru&gt; zadaný pro Microsoft Intune a potom zvolte **OK**.

**Krok 3: Zadejte Apple ID, které jste použili k vytvoření tokenu Apple School Manageru.**<br>Toto ID se má použít k obnovení tokenu Apple School Manageru a je uloženo pro budoucí použití.

**Krok 4: Vyhledejte a nahrajte svůj token.**<br>
Přejděte k souboru certifikátu (p7m), zvolte **Otevřít** a pak zvolte **Nahrát**. Intune automaticky synchronizuje vaše zařízení Apple School Manageru z portálu společnosti Apple.

## <a name="create-an-apple-enrollment-profile"></a>Vytvoření registračního profilu Apple
Registrační profil zařízení definuje nastavení, která se během registrace použijí pro skupinu zařízení.

1. Na portálu Intune zvolte **Registrace zařízení** a pak zvolte **Registrace Apple**.
2. V části **Program registrace** vyberte **Profily Programu registrace**.
3. V okně **Profily Programu registrace** vyberte **Vytvořit**.
4. V okně **Vytvořit registrační profil** zadejte **název** a **popis** profilu, který se zobrazí na portálu Intune.
5. V části **Přidružení uživatele** zvolte, jestli se zařízení s tímto profilem budou registrovat s přidružením uživatele nebo bez.

 - **Zaregistrovat s přidružením uživatele** – během instalace přidruží zařízení k uživateli.

 >[!NOTE]
 >Při registraci na zařízeních spravovaných Apple School Managerem s přidružením uživatelů nefunguje vícefaktorové ověřování (MFA). Po registraci vícefaktorové ověřování na těchto zařízeních funguje podle očekávání.

  Režim Sdílený iPad programu Apple School Manager vyžaduje registraci uživatele bez přidružení uživatele.

 >[!NOTE]
    >Apple School Manager s přidružením uživatele vyžaduje aktivaci [uživatelského jména / smíšeného koncového bodu WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints), aby mohl požádat o token uživatele. [Přečtěte si další informace o WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Zaregistrovat bez přidružení uživatele** – K zařízení není přidružený žádný uživatel. Toto spřažení použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, které vyžadují přidružení uživatele (včetně aplikace Portál společnosti používané k instalaci obchodních aplikací), nebudou fungovat.

6. Vyberte **Nastavení správy zařízení**. Tyto položky jsou nastaveny při aktivaci a jejich změna vyžaduje obnovení továrního nastavení. nakonfigurujte následující nastavení profilu a potom vyberte **Uložit**:

    - **Pod dohledem** – Režim, který nabízí více možností správy a ve výchozím nastavení má zakázaný zámek aktivace. Pokud políčko nezaškrtnete, budete mít omezené možnosti správy.

    - **Uzamčená registrace** – Vyžaduje režim správy Pod dohledem. Zakáže nastavení iOSu, která by mohla umožnit odebrání profilu správy. Pokud políčko nezaškrtnete, půjde profil správy odebrat z nabídky Nastavení.

  - **Sdílený iPad** – (Vyžaduje režimy **Zaregistrovat bez přidružení uživatele** a **Pod dohledem**.) Umožňuje více uživatelům přihlásit se k zaregistrovaným iPadům pomocí spravovaného Apple ID. Spravovaná Apple ID se vytváří na portálu Apple School Manager.

  >[!NOTE]
  >Pokud je **Přidružení uživatele** nastavené na **S přidružením uživatele** nebo je režim **Pod dohledem** nastavený na **Vypnuto**, je režim Sdílený iPad pro registrační profil zakázaný.

  - **Maximální počet uživatelů v mezipaměti** – (Vyžaduje režim **Sdílený iPad** = **Ano**) Vytvoří pro jednotlivé uživatele oddíl na zařízení. Doporučená hodnota je počet studentů, kteří budou pravděpodobně používat zařízení po určitou dobu. Pokud například zařízení běžně používá šest studentů týdně,nastavte toto číslo na šest.  

    - **Povolit párování** – Určuje, jestli se zařízení s iOSem můžou synchronizovat s počítači. Pokud vyberete **Povolit Apple Configurator podle certifikátu**, musíte zvolit certifikát v části **Certifikáty Apple Configuratoru**.

    - **Certifikáty Apple Configuratoru** – Pokud jste v části **Povolit párování** zvolili **Povolit Apple Configurator podle certifikátu**, vyberte certifikát Apple Configuratoru, který chcete importovat.

7. Vyberte **Nastavení Pomocníka s nastavením**, nakonfigurujte následující nastavení profilu a potom vyberte **Uložit**:

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

1. V okně **Token Programu registrace** vyberte buď modrou informační zprávu nebo možnost **Připojit SDS**.
2. Vyberte **Povolit službě Microsoft School Data Sync používat tento token** a nastavte hodnotu **Povolit**. Toto nastavení umožňuje službě Intune propojení se službou SDS v Office 365.
3. Pokud chcete povolit připojení mezi Apple School Managerem a Azure AD, vyberte možnost **Nastavit Microsoft School Data Sync**. Další informace o [jak nastavit službu School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Kliknutím na tlačítko **OK** uložte nastavení a pokračujte.

## <a name="sync-managed-devices"></a>Synchronizace spravovaných zařízení
Když jste službě Intune přiřadili oprávnění ke správě zařízení Apple School Manageru, můžete Intune synchronizovat se službou Apple, aby se spravovaná zařízení zobrazila na portálu Intune.

1. Na portálu Intune zvolte **Registrace zařízení** a pak zvolte **Registrace Apple**.
2. V části **Zařízení Programu registrace** vyberte **Synchronizovat**. Indikátor průběhu vám ukáže dobu, jakou budete muset počkat před dalším vyžádáním synchronizace.

    Pro dosažení souladu s podmínkami společnosti Apple pro přijatelné přenosy platí v Intune následující omezení:
     -  Úplná synchronizace se nesmí pouštět častěji než jednou za sedm dní. Během úplné synchronizace Intune aktualizuje všechna sériová čísla, která společnost Apple přiřadila Intune, bez ohledu na jejich dřívější synchronizaci. Pokud se o úplnou synchronizaci pokusíte do sedmi dnů od předchozí úplné synchronizace, aktualizuje Intune jenom sériová čísla, která ještě nejsou v Intune.
     -  Každá žádost o synchronizaci má 15 minut na dokončení. Po tuto dobu nebo do úspěšného vykonání požadavku je tlačítko **Synchronizovat** neaktivní.

>[!NOTE]
>V okně **Zařízení Programu registrace** můžete také přiřadit sériová čísla Apple School Manageru k profilům.

## <a name="assign-a-profile-to-devices"></a>Přiřazení profilu k zařízením
Zařízením Apple School Manageru spravovaným v Intune musíte před registrací přiřadit registrační profil.

1. Na portálu Intune zvolte **Registrace zařízení** > **Registrace Apple** a vyberte **Profily Programu registrace**.
2. V seznamu **profilů programu registrace** vyberte profil, který chcete přiřadit k zařízením, a potom vyberte **Přiřazení zařízení**.
3. Vyberte **Přiřadit** a pak vyberte zařízení Apple School Manageru, ke kterým chcete tento profil přiřadit. Dostupná zařízení můžete filtrovat:
  - **nepřiřazené**
  - **libovolné**
  - **&lt;Název profilu Apple School Manageru&gt;**
4. Vyberte zařízení, která chcete přiřadit. Zaškrtávací políčko nad sloupcem umožňuje vybrat až 1 000 uvedených zařízení. Klikněte na tlačítko **Přiřadit**. Pokud chcete registrovat více než 1 000 zařízení, opakujte postup, dokud nebudou mít všechna zařízení přiřazený profil registrace.

## <a name="distribute-devices-to-users"></a>Distribuce zařízení uživatelům

Zařízení patřící společnosti teď můžete distribuovat uživatelům. Pokud je zařízení Apple School Manageru s iOSem zapnuté, zaregistruje se pro správu službou Intune. Pokud bylo zařízení aktivováno a používá se, nemůže být profil použit, dokud nebude zařízení obnoveno do továrního nastavení.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Jak uživatelé instalují a používají aplikaci Portál společnosti na svých zařízeních

Zařízení nakonfigurovaná s přidružením uživatele umožňují instalaci a spuštění aplikace Portál společnosti, která slouží ke stahování aplikací a správě zařízení. Když uživatelé obdrží zařízení, musí spustit Pomocníka s nastavením a nainstalovat aplikaci Portál společnosti.
