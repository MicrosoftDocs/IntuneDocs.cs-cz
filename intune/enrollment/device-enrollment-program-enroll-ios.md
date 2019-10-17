---
title: Registrace zařízení s iOSem – Program registrace zařízení
titleSuffix: Microsoft Intune
description: Naučte se registrovat zařízení s iOSem ve vlastnictví firmy pomocí Programu registrace zařízení (DEP).
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 339f6b9476dae438d898b97abcaf3c1759fe9cfc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503327"
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>Automatická registrace zařízení s iOSem pomocí Programu registrace zařízení společnosti Apple

Můžete nastavit Intune k registraci zařízení s iOS zakoupených prostřednictvím programu Apple [program registrace zařízení (DEP)](https://deploy.apple.com). DEP umožňuje registrovat velké počty zařízení, aniž byste je museli přitýkat. Zařízení jako iPhone a iPady můžou být dodávána přímo uživatelům. Když uživatel zařízení zapne, Pomocník s nastavením provede předem nakonfigurovaná nastavení a zařízení se zaregistruje ke správě.

Registraci do programu DEP můžete povolit na portálu Intune i na portálu DEP společnosti Apple. Abyste mohli zařízení přiřadit do Intune ke správě, potřebujete seznam sériových čísel nebo čísla nákupních objednávek. Vytvoříte registrační profily DEP obsahující nastavení aplikovaná na zařízení během registrace.

Zápis DEP se způsobem nepracuje se [správcem registrace zařízení](device-enrollment-manager-enroll.md).

> [!NOTE]
> DEP nastaví konfigurace zařízení, které nemůže koncový uživatel odebrat. Před [migrací na DEP](../fundamentals/migration-guide-considerations.md)se proto musí zařízení vymazat, aby se vrátilo do předem připraveného (nového) stavu.

## <a name="dep-and-the-company-portal"></a>DEP a Portál společnosti

Registrace DEP nejsou kompatibilní s verzí aplikace Portál společnosti App Storu. Uživatelům můžete poskytnout přístup k aplikaci Portál společnosti na zařízení DEP. Pokud jim chcete udělit přístup, nahrajte aplikaci do zařízení pomocí **portál společnosti instalace** pomocí programu VPP (Volume purchase program) v profilu DEP. Další informace najdete v tématu [Automatická registrace zařízení s iOS pomocí program registrace zařízení společnosti Apple](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile).

 Aplikaci Portál společnosti můžete nainstalovat na zařízení, která jsou už zaregistrovaná pomocí programu DEP. Provedete to tak, že nasadíte aplikaci Portál společnosti přes Intune s použitými [zásadami konfigurace aplikace](../apps/app-configuration-policies-use-ios.md) .

## <a name="what-is-supervised-mode"></a>Co je režim Pod dohledem?

Apple režim Pod dohledem představil v systému iOS 5. Zařízení s iOSem v režimu Pod dohledem je možné spravovat několika ovládacími prvky. To je zvlášť užitečné pro zařízení vlastněná firmou. Intune podporuje konfiguraci zařízení do režimu Pod dohledem v rámci programu registrace zařízení Apple (DEP).

Podpora zařízení registrovaných v programu DEP, která nejsou pod dohledem, byla v iOS 11 ukončena. V iOS 11 a novějších verzích musí být zařízení nakonfigurovaná v programu DEP vždy pod dohledem. Příznak is_supervised programu DEP bude v příštích verzích iOS ignorován.

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Požadované součásti
- Zařízení zakoupená v [Programu registrace zařízení společnosti Apple](http://deploy.apple.com)
- [Autorita pro správu mobilních zařízení (MDM)](../fundamentals/mdm-authority-set.md)
- [Certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Získání tokenu DEP Apple

Abyste mohli zařízení s iOSem v programu DEP zaregistrovat, potřebujete od společnosti Apple token DEP (.p7m). Token umožňuje Intune synchronizovat informace o zařízeních v rámci DEP, která vaše společnost vlastní. Umožňuje také Intune odeslat společnosti Apple registrační profily a přiřazovat k těmto profilům zařízení.

Token DEP vytvoříte pomocí portálu DEP společnosti Apple. Pomocí portálu DEP také přiřadíte zařízení do Intune ke správě.

> [!NOTE]
> Když token odstraníte z klasického portálu Intune před migrací do Azure, může Intune obnovit odstraněný token DEP Apple. Token DEP můžete z portálu Azure Portal znovu odstranit.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Krok 1: Stáhněte si certifikát veřejného klíče Intune, který je potřebný k vytvoření tokenu.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace** > **Přidat**.

    ![Stažení tokenu programu registrace zařízení](./media/device-enrollment-program-enroll-ios/image01.png)

2. Výběrem možnosti **Souhlasím** udělte Microsoftu oprávnění k odesílání informací o uživatelích a zařízeních do společnosti Apple.

   ![Snímek obrazovky s podoknem Token Programu registrace v pracovním prostoru Certifikáty Apple pro stažení veřejného klíče](./media/device-enrollment-program-enroll-ios/add-enrollment-program-token-pane.png)

3. Vyberte **Stáhnout veřejný klíč** a stáhněte si a místně uložte soubor šifrovacího klíče (.pem). Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Device Enrollment Program.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Krok 2: Pomocí klíče si stáhněte token od společnosti Apple.

1. Pokud chcete otevřít portál Programu registrace zařízení Apple (DEP), zvolte **Vytvořit token pro Program registrace zařízení Apple** a přihlaste se pomocí firemního Apple ID. Toto Apple ID můžete použít k obnovení tokenu DEP.
2. Na [portálu společnosti Apple pro nasazení programů](https://deploy.apple.com) vyberte **Začínáme**. Otevře se **Program registrace zařízení**.

3. Na stránce pro **správu serverů** zvolte, že chcete **přidat server MDM**.
4. Zadejte **název serveru MDM** a zvolte **Další**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Nejedná se o název nebo adresu URL serveru Microsoft Intune.

5. Otevře se dialogové okno pro **přidání&lt;názvu serveru&gt;** , ve kterém se zobrazí výzva, abyste **nahráli svůj veřejný klíč**. Vyberte **zvolit soubor...** abyste mohli nahrát soubor .pem, a pak zvolte **Další**.

6. Přejděte na **Deployment Programs** (Programy nasazení) &gt; **Device Enrollment Program** (Program registrace zařízení) &gt; **Manage Devices** (Spravovat zařízení).
7. V části se **způsobem výběru zařízení** určete způsob identifikace zařízení:
    - **Sériové číslo**
    - **Číslo objednávky**
    - **Nahrát soubor CSV**

   ![Snímek obrazovky s výběrem zařízení podle sériového čísla, nastavením volby akce na přiřazení serveru a výběrem názvu serveru](./media/device-enrollment-program-enroll-ios/enrollment-program-token-specify-serial.png)

8. V možnosti **Vybrat akci** vyberte **Přiřadit k serveru**, vyberte &lt;název_serveru&gt; zadaný pro Microsoft Intune a pak zvolte **OK**. Portál Apple přiřadí daná zařízení k serveru Intune, aby bylo možné je spravovat, a pak zobrazí zprávu o **dokončení přiřazení**.

   Na portálu Apple přejděte na **Programy nasazení** &gt; **Program registrace zařízení** &gt; **Zobrazit historii přiřazení**. Zobrazí se seznam zařízení s přiřazeným serverem MDM.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Krok 3: Uložte si Apple ID, které jste použili k vytvoření tohoto tokenu.

V Intune na portálu Azure Portal zadejte Apple ID pro budoucí použití.

![Snímek obrazovky s Apple ID použitým k vytvoření tokenu programu registrace a přechodem na token programu registrace](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token-and-choose-scope-tags"></a>Krok 4: Nahrajte token a vyberte značky oboru.

1. V poli **token Apple** vyhledejte soubor certifikátu (. pem), vyberte **otevřít**.
2. Pokud chcete pro tento token DEP použít [značky oboru](../fundamentals/scope-tags.md) , zvolte **rozsah (značky)** a vyberte požadované značky oboru. Značky oboru použité u tokenu budou děděny profily a zařízeními přidanými do tohoto tokenu.
3. Zvolte **Vytvořit**.

S certifikátem Push Certificate může Intune registrovat a spravovat zařízení s iOSem a vynucovat zásady na zaregistrovaných mobilních zařízeních. Intune se automaticky synchronizuje s Apple, aby bylo možné zobrazit účet registračního programu.

## <a name="create-an-apple-enrollment-profile"></a>Vytvoření registračního profilu Apple

Po nainstalování tokenu můžete vytvořit registrační profil pro zařízení DEP. Registrační profil zařízení definuje nastavení, která se během registrace použijí pro skupinu zařízení. Na token DEP je stanovený limit 100 profilů zápisu.

> [!NOTE]
> Zařízení se zablokuje, pokud není k dispozici dostatek Portál společnosti licencí pro token VPP, nebo pokud vypršela platnost tokenu. Intune zobrazí výstrahu, když se brzo vyprší platnost tokenu nebo dojde k nedostatku licencí.
 

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace**.
2. Vyberte token, zvolte **profily** > **vytvořit profil** > **iOS**.

    ![Snímek obrazovky pro vytvoření profilu](./media/device-enrollment-program-enroll-ios/image04.png)

3. Na stránce **základy** zadejte **název** a **Popis** profilu pro účely správy. Uživatelé tyto podrobnosti nevidí. Pole **Název** můžete využít k vytvoření dynamické skupiny v Azure Active Directory. Název profilu použijte k definování parametru enrollmentProfileName pro přiřazení zařízení s tímto registračním profilem. Přečtěte si další informace o [dynamických skupinách Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices).

    ![Název a popis profilu](./media/device-enrollment-program-enroll-ios/image05.png)

4. Vyberte **Další: nastavení správy zařízení**.

5. V části **Přidružení uživatele** zvolte, jestli se zařízení s tímto profilem musí registrovat s přiřazeným uživatelem nebo bez něj.
    - **Zaregistrovat s přidružením uživatele** – tuto možnost vyberte u zařízení patřících uživatelům, kteří chtějí Portál společnosti používat pro služby, jako je instalace aplikací. Pokud používáte ADFS a pokud je v registračním profilu možnost **ověření na Portálu společnosti místo v Průvodci nastavením Applu** nastavená na **Ne**, musí být zadané [uživatelské jméno koncového bodu WS-Trust 1.3 nebo koncový bod s kombinovaným režimem zabezpečení](https://technet.microsoft.com/library/adfs2-help-endpoints). [Další informace](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Zaregistrovat bez přidružení uživatele** – Tuto možnost zvolte pro zařízení nespojená s jedním uživatelem. Tuto možnost použijte pro zařízení, která nemají přístup k místním uživatelským datům. Aplikace, jako je aplikace Portál společnosti, nefungují.

5. Pokud jste zvolili možnost **registrovat s přidružením uživatele**, můžete uživatelům povolit ověřování pomocí portál společnosti namísto pomocníka s nastavením Apple.

    ![Ověření pomocí portálu společnosti](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Pokud chcete provést některou z následujících akcí, nastavte **možnost vybrat, kde se musí uživatelé ověřit** , aby **portál společnosti**.
    >    - Použít vícefaktorové ověřování.
    >    - Zobrazit výzvu uživatelům, pokud při prvním přihlášení potřebují změnit heslo.
    >    - Zobrazit výzvu uživatelům, aby při registraci resetovali neplatná hesla.
    >
    > Ty nejsou podporované při ověřování pomocí Pomocníka s nastavením Apple.

6. Pokud jste zvolili **portál společnosti** pro **Vyberte, kde se uživatelé musí ověřit**, můžete k automatické instalaci portál společnosti na zařízení použít token VPP. V takovém případě nemusí uživatel zadávat Apple ID. K instalaci Portálu společnosti pomocí tokenu VPP zvolte token v seznamu **Nainstalovat Portál společnosti pomocí VPP**. Vyžaduje, aby byla Portál společnosti již přidána do tokenu VPP. Nekonfigurujte zásadu, která bude vyžadovat aplikaci pro uživatele, Intune automaticky nainstaluje Portál společnosti do zařízení s tímto profilem registrace. Dbejte na to, aby tokenu nevypršela platnost a abyste měli dost licencí zařízení pro aplikaci Portál společnosti. Pokud vyprší platnost tokenu nebo dojde k nedostatku licencí, Intune nainstaluje místo toho Portál společnosti App Storu a zobrazí výzvu k zadání Apple ID. 

    > [!NOTE]
    > Když vyberete, aby se **Uživatelé musí ověřit** , **portál společnosti**, ujistěte se, že se proces registrace zařízení provádí během prvních 24 hodin od stažení portálu společnosti do zařízení DEP. Jinak může registrace selhat a k registraci zařízení bude potřeba obnovení továrního nastavení.
    
    ![Snímek obrazovky s instalací portálu společnosti pomocí programu VPP](./media/device-enrollment-program-enroll-ios/install-cp-with-vpp.png)

7. Pokud jste zvolili **Pomocníka s nastavením** pro **Vyberte, kde se uživatelé musí ověřit**, ale také chcete použít podmíněný přístup nebo nasadit firemní aplikace na zařízení, musíte na zařízení nainstalovat portál společnosti. Pokud to chcete udělat, vyberte pro **instalaci portál společnosti** **Ano** .  Pokud chcete, aby uživatelé přijímali Portál společnosti bez nutnosti ověřování do App Storu, zvolte možnost **nainstalovat portál společnosti pomocí programu VPP** a vybrat token VPP. Ujistěte se, že platnost tokenu nevyprší a že máte dost licencí na zařízení, aby mohla aplikace Portál společnosti správně nasadit.

8. Pokud jste zvolili token pro **instalaci portál společnosti pomocí programu VPP**, můžete zařízení uzamknout v režimu jedné aplikace (konkrétně portál společnosti aplikace) hned po dokončení Průvodce nastavením. Tuto možnost nastavíte volbou **Ano** u položky **Spustit Portál společnosti v režimu Jedna aplikace, dokud neproběhne ověření**. Než bude uživatel moct zařízení použít, musí se nejprve ověřit přihlášením na Portálu společnosti.

    Multi-Factor Authentication se nepodporuje v jednom zařízení uzamčeném v režimu jedné aplikace. Toto omezení existuje, protože zařízení nemůže přepnout na jinou aplikaci, aby bylo možné dokončit druhý faktor ověřování. Proto pokud chcete vícefaktorové ověřování na jednom zařízení v režimu aplikace, druhý faktor musí být na jiném zařízení.

    Tato funkce je podporována pouze pro iOS 11.3.1 a novější.

   ![Snímek obrazovky režimu jedné aplikace](./media/device-enrollment-program-enroll-ios/single-app-mode.png)

9. Pokud chcete, aby byla zařízení s tímto profilem pod dohledem, klikněte na **tlačítko Ano** pro **pod dohledem**.

    ![Snímek obrazovky s nastaveními správy zařízení](./media/device-enrollment-program-enroll-ios/supervisedmode.png)

    U zařízení **pod dohledem** je ve výchozím nastavení víc možností správy a je zakázaný zámek aktivace. Microsoft doporučuje používat DEP jako mechanismus pro povolení režimu pod dohledem, obzvláště pokud nasazujete velký počet zařízení s iOS.

    Uživatelé se dozvědí, že jejich zařízení jsou pod dohledem, dvěma způsoby:

   - Na zamykací obrazovce se zobrazí oznámení: „Tento iPhone spravuje Contoso.“
   - Na obrazovce **Nastavení** > **Obecné** > **O produktu** je uvedeno: „Tento iPhone je pod dohledem. Společnost Contoso může monitorovat internetové přenosy a zařízení vyhledat.“

     > [!NOTE]
     > Zařízení zaregistrované bez dohledu se dá resetovat do stavu pod dohledem jenom pomocí Apple Configuratoru. Resetování zařízení tímto způsobem vyžaduje připojení zařízení s iOSem k Macu pomocí kabelu USB. Další informace na toto téma získáte v [dokumentaci Apple Configuratoru](http://help.apple.com/configurator/mac/2.3).

10. Vyberte, jestli chcete pro zařízení, která používají tento profil, uzamčenou registraci. **Uzamčená registrace** zakáže nastavení iOSu, která umožňují odebrání profilu správy z nabídky **Nastavení**. Po registraci zařízení toto nastavení nemůžete změnit bez vymazání zařízení. Taková zařízení musí mít režim správy **Pod dohledem** nastavený na *Ano*. 

11. Vyberte, jestli chcete, aby zařízení, která používají tento profil, mohla **synchronizovat s počítači**. Pokud vyberete **Povolit Apple Configurator podle certifikátu**, musíte zvolit certifikát v části **Certifikáty Apple Configuratoru**.

12. Pokud jste v předchozím kroku zvolili **Povolit Apple Configurator podle certifikátu**, zvolte certifikát Apple Configuratoru, který se má importovat.

13. Můžete zadat formát pojmenování pro zařízení, která se při registraci a při každém úspěšném vrácení se změnami automaticky používají. Chcete-li vytvořit šablonu pro pojmenování, vyberte možnost **Ano** v části **použít šablonu názvu zařízení**. Pak v poli **šablona názvu zařízení** zadejte šablonu, která se má použít pro názvy používané tímto profilem. Můžete zadat formát šablony, který zahrnuje typ zařízení a sériové číslo. 

14. Klikněte na tlačítko **Další: přizpůsobení pomocníka s nastavením**.

15. Na stránce **vlastní nastavení Pomocníka s nastavením** nakonfigurujte následující nastavení profilu: ![Setup Assistant Customization. ](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    | Nastavení oddělení | Description |
    |---|---|
    | <strong>Název oddělení</strong> | Zobrazí se, když uživatelé klepnou při aktivaci na <strong>O konfiguraci</strong>. |
    |    <strong>Telefon na oddělení</strong>     | Zobrazí se, když uživatel při aktivaci klikne na tlačítko <strong>Potřebuji nápovědu</strong>. |

    Během instalace uživatele můžete skrýt obrazovky pomocníka s nastavením na zařízení.
    - Pokud zvolíte **Skrýt**, obrazovka se při nastavování nezobrazí. Po nastavení zařízení může uživatel přejít do nabídky **Nastavení** a funkci nastavit tam.
    - Pokud zvolíte **Zobrazit**, obrazovka se při nastavování zobrazí. Uživatel může obrazovku někdy přeskočit a neudělat žádnou akci. Může ale později přejít do nabídky zařízení **Nastavení** a funkci nastavit tam. 


    | Nastavení na obrazovce Průvodce nastavením | Pokud zvolíte **Zobrazit**, zařízení při nastavování: |
    |------------------------------------------|------------------------------------------|
    | <strong>Heslo</strong> | Vyzve uživatele k zadání hesla. Vždy vyžadovat heslo pro nezabezpečená zařízení, pokud není přístup kontrolován jiným způsobem (například celoobrazovkový režim, který zařízení omezuje na jednu aplikaci). |
    | <strong>Zjišťování polohy</strong> | Vyzve uživatele k poskytnutí polohy. |
    | <strong>Obnovení</strong> | Zobrazí obrazovku aplikace & data. Tato obrazovka nabídne uživateli při nastavování zařízení možnost obnovit nebo přenést data ze zálohy v iCloudu. |
    | <strong>iCloud a Apple ID</strong> | Poskytněte uživateli možnosti přihlašovat se pomocí Apple ID a používat iCloud.                         |
    | <strong>Podmínky a ujednání</strong> | Požaduje, aby uživatel přijal podmínky a ujednání společnosti Apple. |
    | <strong>Touch ID</strong> | Umožní uživateli nastavit pro zařízení identifikaci otiskem prstu. |
    | <strong>Apple Pay</strong> | Umožní uživateli nastavit na zařízení Apple Pay. |
    | <strong>Lupa</strong> | Umožní uživateli zvětšit zobrazení při nastavování zařízení. |
    | <strong>Siri</strong> | Umožní uživateli nastavit Siri. |
    | <strong>Diagnostická data</strong> | Zobrazit obrazovku diagnostiky uživateli Tato obrazovka umožní uživateli poslat společnosti Apple diagnostická data. |
    | <strong>Zobrazit tónový displej</strong> | Poskytněte uživateli možnost zapnout tónový displej. |
    | <strong>Důvěrnost</strong> | Zobrazit obrazovku ochrany osobních údajů uživateli. |
    | <strong>Migrace pro Android</strong> | Poskytněte uživateli možnost migrovat datum ze zařízení s Androidem. |
    | <strong>iMessage a FaceTime</strong> | Poskytněte uživateli možnost nastavit iMessage a FaceTime. |
    | <strong>Registrace</strong> | Zobrazuje informační obrazovky pro vzdělávání uživatelů, jako je například titulní stránka a multitasking a řídicí centrum. |
    | <strong>Sledovat migraci</strong> | Poskytněte uživateli možnost migrovat data ze sledovacího zařízení. |
    | <strong>Čas obrazovky</strong> | Zobrazí obrazovku čas obrazovky. |
    | <strong>Aktualizace softwaru</strong> | Zobrazte povinnou obrazovku aktualizace softwaru. |
    | <strong>Nastavení SIM</strong> | Poskytněte uživateli možnost Přidat plán pro mobilní síť. |
    | <strong>Příznaky</strong> | Zobrazit obrazovku vzhled pro uživatele |
    | <strong>Jazyk Express</strong>| Zobrazit obrazovku jazyka Express pro uživatele |
    | <strong>Preferovaný jazyk</strong> | Poskytněte uživateli možnost zvolit si **preferovaný jazyk**. |
    | <strong>Migrace zařízení do zařízení</strong> | Poskytněte uživateli možnost migrovat data ze starého zařízení do tohoto zařízení.|
    

16. Kliknutím na tlačítko **Další** přejdete na stránku **Revize + vytvořit** .

17. Pokud chcete profil uložit, zvolte **Vytvořit**.

## <a name="sync-managed-devices"></a>Synchronizace spravovaných zařízení
Teď, když má Intune oprávnění spravovat vaše zařízení, můžete synchronizovat Intune s Apple, aby se spravovaná zařízení zobrazila v Intune na portálu Azure Portal.

1. V Intune v Azure Portal vyberte **registrace zařízení** > registrace **Apple** > **tokeny programu registrace** > v seznamu > **zařízení** > **synchronizace**vyberte token. @no__t – 8Screenshot uzlu zařízení programu registrace a odkazu na synchronizaci. ](./media/device-enrollment-program-enroll-ios/image06.png)

   Pokud chcete dodržovat podmínky společnosti Apple pro přijatelný provoz programu registrace, Intune ukládá tato omezení:
   - Úplná synchronizace se nesmí pouštět častěji než jednou za sedm dní. Během úplné synchronizace načte Intune úplný aktualizovaný seznam sériových čísel přiřazených k serveru Apple MDM připojenému k Intune. Pokud se zařízení DEP z portálu Intune odstraní, měl by být na portálu DEP na serveru Apple MDM nepřiřazený. Pokud není přiřazená, nebude se znovu naimportovat do Intune, dokud se nespustí Úplná synchronizace.   
   - Synchronizace se spouští automaticky každých 24 hodin. Můžete ji také spustit kliknutím na tlačítko **Synchronizovat** (ne častěji než jednou za 15 minut). Každá žádost o synchronizaci má 15 minut na dokončení. Tlačítko **Synchronizovat** bude deaktivované, dokud se synchronizace nedokončí. Při synchronizaci se zaktualizuje stav existujících zařízení a naimportují se nová zařízení přiřazená k serveru Apple MDM.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Přiřazení profilu registrace zařízením
Než se můžou zařízení zaregistrovat, musíte přiřadit profil programu registrace.

>[!NOTE]
>Sériová čísla můžete profilům také přiřadit v okně **sériových čísel Apple**.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny Programu registrace** > zvolte token v seznamu.
2. Zvolte **Zařízení** > zvolte zařízení v seznamu > **Přiřadit profil**.
3. V části **Přiřadit profil** zvolte profil pro zařízení > **Přiřadit**.

### <a name="assign-a-default-profile"></a>Přiřazení výchozího profilu

Můžete si vybrat výchozí profil, který se má použít pro všechna zařízení, která se registrují s konkrétním tokenem.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny Programu registrace** > zvolte token v seznamu.
2. Zvolte **Nastavit výchozí profil**, v rozevíracím seznamu zvolte profil a potom zvolte **Uložit**. Tento profil se použije pro všechna zařízení, která se registrují s tímto tokenem.

## <a name="distribute-devices"></a>Distribuujte zařízení.
Povolili jste správu a synchronizaci mezi společností Apple a Intune a přiřadili jste profil, který umožní registraci zařízení DEP. Teď můžete zařízení rozdělit mezi uživatele. U zařízení s přidruženými uživateli je potřeba, aby měl každý uživatel přiřazenu licenci Intune. Zařízení bez přidružení uživatele vyžadují licenci zařízení. Aktivované zařízení nemůže použít registrační profil, dokud se zařízení nevymaže.

Přečtěte si téma [Registrace zařízení s iOSem v Intune pomocí programu registrace zařízení](/intune-user-help/enroll-your-device-dep-ios).

## <a name="renew-a-dep-token"></a>Obnovení tokenu DEP  
1. Přejděte na deploy.apple.com.  
2. V části **Manage Servers** (Spravovat servery) zvolte server MDM přidružený k souboru tokenu, který chcete obnovit.
3. Zvolte **Generate New Token** (Vygenerovat nový token).

    ![Snímek obrazovky s možností Generate New Token (Vygenerovat nový token)](./media/device-enrollment-program-enroll-ios/generatenewtoken.png)

4. Zvolte **Your Server Token** (Token vašeho serveru).  
5. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace zařízení Apple** > **Tokeny programu registrace** a zvolte token.
    ![Snímek obrazovky s možností Tokeny programu registrace](./media/device-enrollment-program-enroll-ios/enrollmentprogramtokens.png)

6. Vyberte možnost **Obnovit token** a zadejte Apple ID, které jste použili k vytvoření původního tokenu.  
    ![Snímek obrazovky s možností Generate New Token (Vygenerovat nový token)](./media/device-enrollment-program-enroll-ios/renewtoken.png)

8. Nahrajte nově stažený token.  
9. Zvolte **Obnovit token**. Zobrazí se potvrzení, že se token obnovil.   
    ![Snímek obrazovky s potvrzením](./media/device-enrollment-program-enroll-ios/confirmation.png)
