---
title: "Registrace zařízení s iOSem – Program registrace zařízení"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se registrovat zařízení s iOSem ve vlastnictví firmy pomocí Programu registrace zařízení (DEP)."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 5144b9e7c17a3323667b9ca68cb47829d69866c3
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>Registrace zařízení s iOSem pomocí Programu registrace zařízení (DEP)

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Toto téma pomáhá správcům IT registrovat zařízení s iOSem ve vlastnictví firmy zakoupená prostřednictvím [Programu registrace zařízení (DEP) společnosti Apple](https://deploy.apple.com). Microsoft Intune může nasadit registrační profil, který DEP registruje bezdrátově, takže správce žádné spravované zařízení nemusí mít fyzicky k dispozici. Profil DEP obsahuje nastavení správy, která chcete použít u zařízení během registrace. Registrační balíček může zahrnovat možnosti Pomocníka s nastavením pro zařízení.

>[!NOTE]
>Registrace DEP se nedá použít se [správcem registrace zařízení](device-enrollment-manager-enroll.md).
>Navíc platí, že pokud uživatelé svá zařízení s iOSem zaregistrují pomocí aplikace Portál společnosti a sériová čísla těchto zařízení se pak naimportují a přiřadí k profilu DEP, zruší se tím registrace zařízení v Intune.

**Kroky registrace DEP**
1. [Získání tokenu Apple DEP](#get-the-apple-dep-certificate)
2. [Vytvoření profilu DEP](#create-an-apple-dep-profile)
3. [Přiřazení sériových čísel Apple DEP k vašemu serveru Intune](#assign-apple-dep-serial-numbers-to-your-mdm-server)
4. [Synchronizace zařízení spravovaných v rámci programu DEP](#synchronize-dep-managed-devices)
5. [Přiřazení profilu DEP k zařízením](#assign-a-dep-profile-to-devices)
6. [Distribuce zařízení uživatelům](#distribute-devices-to-users)

## <a name="get-the-apple-dep-certificate"></a>Získání certifikátu Apple DEP
Abyste mohli v Programu registrace zařízení (DEP) registrovat zařízení s iOSem vlastněná společností, potřebujete od společnosti Apple certifikát DEP (.p7m). Token umožňuje Intune synchronizovat informace o zařízeních vlastněných společností, která se účastní programu DEP. Token také umožňuje Intune odesílat společnosti Apple registrační profily a přiřazovat k těmto profilům zařízení.

Pokud chcete zařízení s iOSem vlastněná společností spravovat pomocí Programu registrace zařízení (DEP) společnosti Apple, musí se vaše společnost do tohoto programu zaregistrovat a získat zařízení jeho prostřednictvím. Podrobnosti o tomto procesu najdete na https://deploy.apple.com. Výhodou tohoto programu je bezobslužné nastavení zařízení bez připojení každého zařízení k počítači kabelem USB.

> [!NOTE]
> Pokud byl váš tenant Intune migrován z klasické konzoly Intune do portálu Azure Portal a během doby migrace jste z konzoly pro správu Intune token Apple DEP odstranili, mohl být token DEP obnoven do vašeho účtu Intune. Token DEP můžete z portálu Azure Portal znovu odstranit.

**Krok 1: Stáhněte si certifikát veřejného klíče služby Intune, který je potřebný pro vytvoření tokenu DEP Apple.**<br>
1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**. V okně Intune zvolte **Registrace zařízení** > **Token DEP Apple**.
2. Vyberte **Stáhnout certifikát veřejného klíče** a stáhněte si a místně uložte soubor šifrovacího klíče (.pem). Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Device Enrollment Program.

**Krok 2: Stáhněte si token DEP Apple z příslušného webu Apple.**<br>
Vyberte [Vytvořit token DEP prostřednictvím Apple Deployment Programs](https://deploy.apple.com). Dostanete se na https://deploy.apple.com, kde se přihlaste svým firemním Apple ID. Toto Apple ID můžete použít k obnovení tokenu DEP.

   1.  Na [portálu programu DEP (Device Enrollment Program)](https://deploy.apple.com) společnosti Apple přejděte na **Program DEP (Device Enrollment Program)** &gt; **Spravovat servery** a pak zvolte **Přidat server MDM**.
   2.  Zadejte **název serveru MDM** a zvolte **Další**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Není to název serveru Microsoft Intune ani jeho URL.
   3.  Otevře se dialog **Přidat server &lt;název_serveru&gt;**. Vyberte **Zvolit soubor**, abyste mohli nahrát soubor .pem, a pak zvolte **Další**.
   4.  V dialogovém okně **Přidat server &lt;název_serveru&gt;** se zobrazí odkaz s **tokenem vašeho serveru**. Stáhněte si soubor tokenu serveru (.p7m) do svého počítače a potom zvolte **Hotovo**.

**Krok 3: Zadejte Apple ID, které jste použili k vytvoření tokenu Apple DEP. Toto ID můžete použít také k obnovení tokenu Apple DEP.**

**Krok 4: Procházením vyhledejte token Apple DEP, který chcete nahrát. Služba Intune se bude automaticky synchronizovat s vaším účtem DEP.**<br>
Přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Nahrát**. S certifikátem Push Certificate může Intune registrovat a spravovat zařízení s iOSem a vynucovat zásady na zaregistrovaných mobilních zařízeních.

## <a name="create-an-apple-dep-profile"></a>Vytvoření profilu Apple DEP

Profil registrace zařízení definuje nastavení, která se použijí pro skupinu zařízení. Následující postup ukazuje, jak vytvořit profil registrace zařízení pro zařízení s iOSem registrovaná pomocí programu DEP.

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.
2. V okně Intune zvolte **Registrace zařízení** a pak zvolte **Registrace Apple**.
3. V části **Spravovat nastavení Programu registrace zařízení (DEP) Apple** vyberte **Profily DEP**.
4. V okně **Profily DEP** vyberte **Vytvořit**.
5. V okně **Vytvořit registrační profil** zadejte název a popis profilu.
6. V části **Přidružení uživatele** zvolte, jestli se zařízení s tímto profilem budou registrovat s přidružením uživatele nebo bez.

 - **Zaregistrovat s přidružením uživatele** – Při počátečním nastavení musí mít zařízení přidruženého uživatele, aby mohlo dostat přístup k firemním datům a e-mailu. Přidružení uživatele zvolte pro zařízení spravovaná v programu DEP, která patří konkrétním uživatelům a potřebují používat portál společnosti kvůli službám, jako je instalace aplikací. Při registraci na zařízeních v programu DEP s přidružením uživatelů nefunguje vícefaktorové ověřování (MFA). Po registraci vícefaktorové ověřování na těchto zařízeních funguje podle očekávání. Novým uživatelům, kteří si musejí změnit heslo, když se poprvé přihlásí, se během registrace na zařízení DEP nezobrazí výzva. Také uživatelům, u jejichž hesel vypršela platnost, se během registrace DEP nezobrazí výzva k resetování hesla a budou muset heslo resetovat z jiného zařízení.

    >[!NOTE]
    >Program DEP s přidružením uživatele vyžaduje aktivaci [uživatelského jména / smíšeného koncového bodu WS-Trust 1.3](https://technet.microsoft.com/en-us/library/adfs2-help-endpoints), aby mohl požádat o token uživatele. [Přečtěte si další informace o WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

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
Na webovém portálu Apple DEP musíte k serveru MDM služby Intune přiřadit sériová čísla zařízení, aby služba Intune mohla tato zařízení spravovat.

1. Přejděte na [portál programu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) a přihlaste se pomocí firemního Apple ID.

2. Přejděte na **Deployment Program** (Program nasazení) &gt; **Device Enrollment Program** (Program registrace zařízení) &gt; **Manage Devices** (Spravovat zařízení).

3. Určete, jak budete volit zařízení (**Choose Devices**), a zadejte podrobné informace o zařízení pomocí možností **Serial Number** (Sériové číslo), **Order Number** (Číslo objednávky) nebo **Upload CSV File** (Nahrát soubor CSV).

4. Zvolte **Přiřadit k serveru**, zvolte &lt;název_serveru&gt; zadaný pro Microsoft Intune a potom zvolte **OK**.

## <a name="synchronize-dep-managed-devices"></a>Synchronizace zařízení spravovaných v rámci programu DEP
Když jste službě Intune přiřadili oprávnění ke správě zařízení DEP, můžete službu Intune synchronizovat se službou DEP, aby se spravovaná zařízení zobrazila na portálu Intune.

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune na portálu Azure Portal zvolte **Registrace zařízení** a pak zvolte **Registrace Apple**.

3. V části **Spravovat nastavení Programu registrace zařízení (DEP) Apple** vyberte **Sériová čísla DEP**.

4. V okně **Sériová čísla Apple DEP** vyberte **Synchronizovat**.

5. V okně **Synchronizovat** vyberte **Požadovat synchronizaci**. Indikátor průběhu vám ukáže dobu, jakou budete muset počkat před dalším vyžádáním synchronizace.

    Pro dosažení souladu s podmínkami společnosti Apple pro přijatelné přenosy v rámci DEP platí v Intune následující omezení:
     -    Úplná synchronizace programu DEP se nesmí spouštět častěji než jednou za sedm dní. Během úplné synchronizace Intune aktualizuje všechna sériová čísla, která společnost Apple přiřadila Intune, bez ohledu na jejich dřívější synchronizaci. Pokud se o úplnou synchronizaci pokusíte do sedmi dnů od předchozí úplné synchronizace, aktualizuje Intune jenom sériová čísla, která ještě nejsou v Intune.
     -    Každá žádost o synchronizaci má 10 minut na dokončení. Po tuto dobu nebo do úspěšného vykonání požadavku je tlačítko **Synchronizovat** neaktivní.

>[!NOTE]
>Z okna **Sériová čísla Apple DEP** můžete také sériová čísla DEP přiřadit k profilům.

## <a name="assign-a-dep-profile-to-devices"></a>Přiřazení profilu DEP k zařízením
Aby se zařízení DEP spravovaná službou Intune mohla registrovat, musíte jim přiřadit profil DEP.

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**.

2. V okně Intune na portálu Azure zvolte **Registrace zařízení** > **Registrace Apple** a potom vyberte **Profily DEP**.

3. V seznamu **Registrační profily programu Apple DEP** vyberte profil, který chcete přiřadit k zařízením, a potom vyberte **Přiřazení zařízení**.

4. Vyberte **Přiřadit** a pak vyberte zařízení DEP, ke kterým chcete tento profil přiřadit. Dostupná zařízení DEP můžete filtrovat:
  - **nepřiřazené**
  - **libovolné**
  - **&lt;název profilu DEP&gt;**

  ![Snímek obrazovky s tlačítkem Přiřadit pro přiřazení profilu DEP na portálu Intune](media/dep-profile-assignment.png)

5. Vyberte zařízení, která chcete přiřadit. Zaškrtnutím políčka nad sloupcem můžete vybrat až 1 000 zobrazených zařízení a potom můžete kliknout na **Přiřadit**. Pokud chcete registrovat více než 1 000 zařízení, opakujte postup přiřazení, dokud nebudou mít všechna zařízení přiřazený profil DEP.

## <a name="distribute-devices-to-users"></a>Distribuce zařízení uživatelům

Zařízení patřící společnosti teď můžete distribuovat uživatelům. Pokud je zařízení s iOSem zapnuté, zaregistruje se pro správu službou Intune. Pokud bylo zařízení aktivováno a používá se, nemůže být profil použit, dokud nebude zařízení obnoveno do továrního nastavení.

Viz [Co říct koncovým uživatelům o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune). Koncové uživatele také můžete nasměrovat na téma [Použití zařízení s iOSem nebo macOS s Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune). 

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Jak uživatelé instalují a používají aplikaci Portál společnosti na svých zařízeních

Zařízení nakonfigurovaná s přidružením uživatele umožňují instalaci a spuštění aplikace Portál společnosti, která slouží ke stahování aplikací a správě zařízení. Když uživatelé dostanou zařízení, musí provést další kroky popsané níže, aby dokončili postup Pomocníka s nastavením a nainstalovali aplikaci Portál společnosti.

