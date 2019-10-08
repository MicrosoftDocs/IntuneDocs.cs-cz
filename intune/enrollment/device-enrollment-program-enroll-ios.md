---
title: Registrace zařízení s iOS – Program registrace zařízení
titleSuffix: Microsoft Intune
description: Naučte se registrovat zařízení s iOS vlastněná společností pomocí Program registrace zařízení.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19389a21aa28f5fa957f62c988753f46bf1bc731
ms.sourcegitcommit: 46322ca7a92971e18dc0b230f436b9ca892b90c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/07/2019
ms.locfileid: "72008341"
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>Automatická registrace zařízení s iOS pomocí Program registrace zařízení společnosti Apple

Můžete nastavit Intune k registraci zařízení s iOS zakoupených prostřednictvím programu Apple [program registrace zařízení (DEP)](https://deploy.apple.com). DEP umožňuje registrovat velké počty zařízení, aniž byste je museli přitýkat. Zařízení jako iPhone a iPady můžou být dodávána přímo uživatelům. Když uživatel zařízení zapne, Pomocník s nastavením se spustí s předem nakonfigurovaným nastavením a zařízení se zaregistruje do správy.

Pokud chcete povolit registraci DEP, použijte portál Intune i Apple DEP. Vyžaduje se seznam sériových čísel nebo čísel nákupních objednávek, abyste mohli zařízení přiřadit k Intune za účelem správy. Vytvoříte profily zápisu DEP, které obsahují nastavení, která se v zařízeních nastavila během registrace.

Zápis DEP se způsobem nepracuje se [správcem registrace zařízení](device-enrollment-manager-enroll.md).

> [!NOTE]
> DEP nastaví konfigurace zařízení, které nemůže koncový uživatel odebrat. Před [migrací na DEP](../fundamentals/migration-guide-considerations.md)se proto musí zařízení vymazat, aby se vrátilo do předem připraveného (nového) stavu.

## <a name="dep-and-the-company-portal"></a>DEP a Portál společnosti

Registrace DEP nejsou kompatibilní s verzí aplikace Portál společnosti App Storu. Uživatelům můžete poskytnout přístup k aplikaci Portál společnosti na zařízení DEP. Pokud jim chcete udělit přístup, nahrajte aplikaci do zařízení pomocí **portál společnosti instalace** pomocí programu VPP (Volume purchase program) v profilu DEP. Další informace najdete v tématu [Automatická registrace zařízení s iOS pomocí program registrace zařízení společnosti Apple](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile).

 Aplikaci Portál společnosti můžete nainstalovat na zařízení, která jsou už zaregistrovaná pomocí programu DEP. Provedete to tak, že nasadíte aplikaci Portál společnosti přes Intune s použitými [zásadami konfigurace aplikace](../apps/app-configuration-policies-use-ios.md) .

## <a name="what-is-supervised-mode"></a>Co je režim pod dohledem?

Apple zavádí režim pod dohledem v iOS 5. Zařízení s iOS v režimu pod dohledem se dá spravovat s dalšími ovládacími prvky. To je zvlášť užitečné pro zařízení vlastněná firmou. Intune podporuje konfiguraci zařízení pro režim pod dohledem jako součást Apple Program registrace zařízení (DEP).

Podpora zařízení DEP, která nejsou pod dohledem, se v iOS 11 nepoužívá. V iOS 11 a novějších je potřeba, aby zařízení nakonfigurovaná programem DEP byla vždycky pod dohledem. Příznak is_supervised DEP se v budoucí verzi pro iOS bude ignorovat.

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Požadavky
- Zařízení zakoupená v [program registrace zařízení společnosti Apple](http://deploy.apple.com)
- [Autorita pro správu mobilních zařízení (MDM)](../fundamentals/mdm-authority-set.md)
- [Apple MDM push Certificate](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Získání tokenu DEP Apple

Než budete moct zaregistrovat zařízení s iOS pomocí programu DEP, potřebujete od společnosti Apple token DEP (. p7m). Tento token umožňuje Intune synchronizovat informace o zařízeních DEP, která vaše společnost vlastní. Umožňuje také Intune nahrávat profily zápisu do společnosti Apple a přiřazovat k těmto profilům zařízení.

Pomocí portálu Apple DEP vytvoříte token DEP. Pomocí portálu DEP taky přiřadíte zařízení ke správě do Intune.

> [!NOTE]
> Pokud token odstraníte z klasického portálu Intune před migrací do Azure, může Intune obnovit odstraněný token DEP Apple. Token DEP můžete z Azure Portal odstranit znovu.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Krok 1. Stáhněte si certifikát veřejného klíče Intune, který je potřebný k vytvoření tokenu.

1. V [Intune v Azure Portal](https://aka.ms/intuneportal)klikněte na **registrace zařízení** >  registrace**Apple** > **tokeny programu registrace** > **Přidat**.

    ![Získejte token programu registrace.](./media/device-enrollment-program-enroll-ios/image01.png)

2. Výběrem možnosti **Souhlasím**udělíte Microsoftu oprávnění k posílání informací o uživatelích a zařízeních do společnosti Apple.

   ![Snímek obrazovky s podoknem token programu registrace v pracovním prostoru certifikáty Apple pro stažení veřejného klíče](./media/device-enrollment-program-enroll-ios/add-enrollment-program-token-pane.png)

3. Vyberte **Stáhnout veřejný klíč** a stáhněte a uložte soubor šifrovacího klíče (. pem) místně. Soubor. pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Program registrace zařízení.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Krok 2. Pomocí svého klíče si stáhněte token od společnosti Apple.

1. Zvolením možnosti **vytvořit token pro program registrace zařízení** od společnosti Apple otevřete portál programu Apple Deployment Portal a přihlaste se pomocí firemního Apple ID. Toto Apple ID můžete použít k obnovení tokenu DEP.
2. Na [portálu programu pro nasazení](https://deploy.apple.com)společnosti Apple vyberte **Začínáme** pro **program registrace zařízení**.

3. Na stránce **Spravovat servery** vyberte **Přidat server MDM**.
4. Zadejte **název serveru MDM**a pak zvolte **Další**. Název serveru je určen pro váš odkaz k identifikaci serveru správy mobilních zařízení (MDM). Nejedná se o název nebo adresu URL serveru Microsoft Intune.

5. Otevře se dialogové okno **přidat &lt;ServerName @ no__t-2** , ve kterém se zobrazí zpráva o **nahrání veřejného klíče**. Vyberte **zvolit soubor...** pro nahrání souboru. pem a poté klikněte na tlačítko **Další**.

6. Přejít do **programu pro nasazení** &gt; **Program registrace zařízení** **Správa zařízení**&gt;.
7. V části **zvolit zařízení podle**zadejte způsob identifikace zařízení:
    - **Sériové číslo**
    - **Pořadové číslo**
    - **Nahrajte soubor CSV**.

   ![Snímek obrazovky s určením výběru zařízení podle sériového čísla, nastavením volby akce jako přiřadit serveru a výběrem názvu serveru](./media/device-enrollment-program-enroll-ios/enrollment-program-token-specify-serial.png)

8. V možnosti **Vybrat akci**zvolte **přiřadit k serveru**, zvolte &lt;ServerName @ no__t-3, kterou jste zadali pro Microsoft Intune a pak zvolte **OK**. Portál Apple přiřadí zadaná zařízení k serveru Intune pro správu a pak zobrazí **dokončení přiřazení**.

   Na portálu Apple přejděte do části **programy pro nasazení** &gt; **program registrace zařízení** &gt; **Zobrazit historii přiřazení** a zobrazte seznam zařízení a jejich přiřazení k serveru MDM.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Krok 3. Uložte Apple ID použité k vytvoření tohoto tokenu.

V Intune v Azure Portal zadejte Apple ID pro budoucí referenci.

![Snímek obrazovky s zadáním Apple ID použitého k vytvoření tokenu programu registrace a procházením tokenu programu registrace](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token-and-choose-scope-tags"></a>Krok 4. Nahrajte token a vyberte značky oboru.

1. V poli **token Apple** vyhledejte soubor certifikátu (. pem), vyberte **otevřít**.
2. Pokud chcete pro tento token DEP použít [značky oboru](../fundamentals/scope-tags.md) , zvolte **rozsah (značky)** a vyberte požadované značky oboru. Značky oboru použité u tokenu budou děděny profily a zařízeními přidanými do tohoto tokenu.
3. Vyberte **vytvořit**.

S certifikátem push Certificate může Intune registrovat a spravovat zařízení se systémem iOS tím, že zapisuje zásady do zaregistrovaných mobilních zařízení. Intune se automaticky synchronizuje s Apple, aby se zobrazil účet programu registrace.

## <a name="create-an-apple-enrollment-profile"></a>Vytvoření registračního profilu Apple

Teď, když máte nainstalovaný token, můžete vytvořit profil registrace pro zařízení DEP. Profil registrace zařízení definuje nastavení, která se při registraci mají použít pro skupinu zařízení. Na token DEP je stanovený limit 100 profilů zápisu.

> [!NOTE]
> Zařízení se zablokuje, pokud není k dispozici dostatek Portál společnosti licencí pro token VPP, nebo pokud vypršela platnost tokenu. Intune zobrazí výstrahu, když se brzo vyprší platnost tokenu nebo dojde k nedostatku licencí.
 

1. V Intune v Azure Portal vyberte **registrace zařízení** >  registrace**Apple** > **tokeny programu registrace**.
2. Vyberte token, zvolte **profily** > **vytvořit profil** > **iOS**.

    ![Vytvořte snímek obrazovky profilu.](./media/device-enrollment-program-enroll-ios/image04.png)

3. Na stránce **základy** zadejte **název** a **Popis** profilu pro účely správy. Uživatelé tyto podrobnosti nevidí. Pomocí tohoto pole **název** můžete vytvořit dynamickou skupinu v Azure Active Directory. Pomocí názvu profilu definujte parametr enrollmentProfileName pro přiřazení zařízení s tímto registračním profilem. Přečtěte si další informace o [Azure Active Directory dynamických skupinách](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices).

    ![Název a popis profilu](./media/device-enrollment-program-enroll-ios/image05.png)

4. Vyberte **Další: nastavení správy zařízení**.

5. V případě **spřažení uživatele**vyberte, jestli se zařízení s tímto profilem musí zaregistrovat s přiřazeným uživatelem nebo bez něj.
    - **Zaregistrovat s přidružením uživatele** – tuto možnost vyberte pro zařízení, která patří uživatelům a chtějí používat portál společnosti pro služby, jako je instalace aplikací. Pokud používáte službu AD FS a profil registrace se **ověřuje pomocí portál společnosti místo pomocníka s nastavením** nastaven na **ne**, vyžaduje se [pravidlo WS-Trust 1,3 uživatelské_jméno/Smíšený Koncový bod](https://technet.microsoft.com/library/adfs2-help-endpoints) [Další informace](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint) .

    - **Zaregistrovat bez přidružení uživatele** – tuto možnost vyberte, pokud chcete, aby zařízení nebyla přidružená jednomu uživateli. Tuto možnost použijte pro zařízení, která nemají přístup k místním uživatelským datům. Aplikace, jako je Portál společnosti aplikace, nefungují.

5. Pokud jste zvolili možnost **registrovat s přidružením uživatele**, můžete uživatelům povolit ověřování pomocí portál společnosti namísto pomocníka s nastavením Apple.

    ![Ověřování pomocí Portál společnosti.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Pokud chcete provést některou z následujících akcí, nastavte **možnost vybrat, kde se musí uživatelé ověřit** , aby **portál společnosti**.
    >    - použití vícefaktorového ověřování
    >    - vyzvat uživatele, kteří při prvním přihlášení potřebují změnit heslo
    >    - vyzvat uživatele k resetování hesel s vypršenou platností během registrace
    >
    > Ty nejsou podporované při ověřování pomocí Pomocníka s nastavením Apple.

6. Pokud jste zvolili **portál společnosti** pro **Vyberte, kde se uživatelé musí ověřit**, můžete k automatické instalaci portál společnosti na zařízení použít token VPP. V takovém případě nemusí uživatel zadávat Apple ID. Pokud chcete nainstalovat Portál společnosti s tokenem VPP, vyberte v části **instalace portál společnosti pomocí programu VPP**token. Vyžaduje, aby byla Portál společnosti již přidána do tokenu VPP. Nekonfigurujte zásadu, která bude vyžadovat aplikaci pro uživatele, Intune automaticky nainstaluje Portál společnosti do zařízení s tímto profilem registrace. Ujistěte se, že platnost tokenu nevyprší a že máte k dispozici dostatek licencí na zařízení pro aplikaci Portál společnosti. Pokud vyprší platnost tokenu nebo dojde k nedostatku licencí, Intune nainstaluje místo toho Portál společnosti App Storu a zobrazí výzvu k zadání Apple ID. 

    > [!NOTE]
    > Když vyberete, aby se **Uživatelé musí ověřit** , **portál společnosti**, ujistěte se, že se proces registrace zařízení provádí během prvních 24 hodin od stažení portálu společnosti do zařízení DEP. Jinak může registrace selhat a k registraci zařízení bude potřeba obnovení továrního nastavení.
    
    ![Snímek obrazovky s instalací portálu společnosti pomocí programu VPP](./media/device-enrollment-program-enroll-ios/install-cp-with-vpp.png)

7. Pokud jste zvolili **Pomocníka s nastavením** pro **Vyberte, kde se uživatelé musí ověřit**, ale také chcete použít podmíněný přístup nebo nasadit firemní aplikace na zařízení, musíte na zařízení nainstalovat portál společnosti. Pokud to chcete udělat, vyberte pro **instalaci portál společnosti** **Ano** .  Pokud chcete, aby uživatelé přijímali Portál společnosti bez nutnosti ověřování do App Storu, zvolte možnost **nainstalovat portál společnosti pomocí programu VPP** a vybrat token VPP. Ujistěte se, že platnost tokenu nevyprší a že máte dost licencí na zařízení, aby mohla aplikace Portál společnosti správně nasadit.

8. Pokud jste zvolili token pro **instalaci portál společnosti pomocí programu VPP**, můžete zařízení uzamknout v režimu jedné aplikace (konkrétně portál společnosti aplikace) hned po dokončení Průvodce nastavením. Pro možnost **spustit portál společnosti v režimu jedné aplikace** vyberte **Ano** , dokud nenastavíte možnost ověřování. Aby bylo možné použít zařízení, musí se uživatel nejdřív ověřit přihlášením pomocí Portál společnosti.

    Multi-Factor Authentication se nepodporuje v jednom zařízení uzamčeném v režimu jedné aplikace. Toto omezení existuje, protože zařízení nemůže přepnout na jinou aplikaci, aby bylo možné dokončit druhý faktor ověřování. Proto pokud chcete vícefaktorové ověřování na jednom zařízení v režimu aplikace, druhý faktor musí být na jiném zařízení.

    Tato funkce je podporována pouze pro iOS 11.3.1 a novější.

   ![Snímek obrazovky režimu jedné aplikace](./media/device-enrollment-program-enroll-ios/single-app-mode.png)

9. Pokud chcete, aby byla zařízení s tímto profilem pod dohledem, klikněte na **tlačítko Ano** pro **pod dohledem**.

    ![Snímek obrazovky nastavení správy zařízení](./media/device-enrollment-program-enroll-ios/supervisedmode.png)

    Zařízení **pod dohledem** poskytují více možností správy a jsou ve výchozím nastavení zakázané zámek aktivace. Microsoft doporučuje používat DEP jako mechanismus pro povolení režimu pod dohledem, obzvláště pokud nasazujete velký počet zařízení s iOS.

    Uživatelům se dozvíte, že jejich zařízení jsou pod dohledem dvěma způsoby:

   - Zamykací obrazovka uvádí: "Tento iPhone spravuje společnost Contoso."
   - **Nastavení** > **Obecné** > **o** obrazovce říká: "Tento iPhone je pod dohledem. Contoso může monitorovat internetový provoz a vyhledat toto zařízení.

     > [!NOTE]
     > Zařízení zaregistrované bez dohledu se dá resetovat jenom na pod dohledem pomocí Apple Configuratoru. Resetování zařízení tímto způsobem vyžaduje připojení zařízení s iOS k počítači Mac pomocí kabelu USB. Další informace najdete v [dokumentaci k Apple Configuratoru](http://help.apple.com/configurator/mac/2.3).

10. Vyberte, jestli chcete pro zařízení, která používají tento profil, uzamčenou registraci. **Uzamčená registrace** zakáže nastavení iOS, která umožňují odebrání profilu správy z nabídky **Nastavení** . Po registraci zařízení toto nastavení nemůžete změnit bez vymazání zařízení. Tato zařízení musí mít režim správy **pod dohledem** nastavený na *Ano*. 

11. Vyberte, jestli chcete, aby zařízení, která používají tento profil, mohla **synchronizovat s počítači**. Pokud zvolíte možnost **Povolení Apple Configuratoru podle certifikátu**, musíte zvolit certifikát v části **certifikáty Apple Configuratoru**.

12. Pokud jste v předchozím kroku zvolili možnost **Povolení Apple Configuratoru podle certifikátu** , vyberte certifikát Apple Configuratoru, který chcete importovat.

13. Můžete zadat formát pojmenování pro zařízení, která se při registraci a při každém úspěšném vrácení se změnami automaticky používají. Chcete-li vytvořit šablonu pro pojmenování, vyberte možnost **Ano** v části **použít šablonu názvu zařízení**. Pak v poli **šablona názvu zařízení** zadejte šablonu, která se má použít pro názvy používané tímto profilem. Můžete zadat formát šablony, který zahrnuje typ zařízení a sériové číslo. 

14. Klikněte na tlačítko **Další: přizpůsobení pomocníka s nastavením**.

15. Na stránce **vlastní nastavení Pomocníka s nastavením** nakonfigurujte následující nastavení profilu: ![Setup Assistant Customization. ](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    | Nastavení oddělení | Popis |
    |---|---|
    | <strong>Název oddělení</strong> | Zobrazí se, když uživatel během aktivace klepne na možnost <strong>Konfigurace</strong> . |
    |    <strong>Telefon na oddělení</strong>     | Zobrazí se, když uživatel při aktivaci klikne na tlačítko <strong>Potřebuji Help</strong> . |

    Během instalace uživatele můžete skrýt obrazovky pomocníka s nastavením na zařízení.
    - Zvolíte-li možnost **Skrýt**, obrazovka nebude zobrazena při instalaci. Po nastavení zařízení může uživatel stále přejít do nabídky **Nastavení** a tuto funkci nastavit.
    - Pokud zvolíte možnost **Zobrazit**, obrazovka se zobrazí během instalace. Uživatel může někdy obrazovku přeskočit bez provedení akce. Můžou je ale později přejít do nabídky **Nastavení** zařízení a tuto funkci nastavit. 


    | Nastavení obrazovky pomocníka s nastavením | Pokud zvolíte možnost **Zobrazit**, během instalace bude zařízení... |
    |------------------------------------------|------------------------------------------|
    | <strong>Kód</strong> | Vyzvat uživatele k zadání hesla Vždy vyžadovat heslo pro nezabezpečená zařízení, pokud není přístup kontrolován jiným způsobem (například celoobrazovkový režim, který zařízení omezuje na jednu aplikaci). |
    | <strong>Umístění služeb</strong> | Vyzvat uživatele k zadání jeho umístění. |
    | <strong>Obnovil</strong> | Zobrazí obrazovku aplikace & data. Tato obrazovka dává uživateli možnost obnovit nebo přenést data ze zálohy iCloud při nastavení zařízení. |
    | <strong>iCloud a Apple ID</strong> | Poskytněte uživateli možnosti přihlašovat se pomocí Apple ID a používat iCloud.                         |
    | <strong>Podmínky a ujednání</strong> | Vyžaduje, aby uživatel přijal podmínky a ujednání společnosti Apple. |
    | <strong>Touch ID</strong> | Poskytněte uživateli možnost nastavit pro zařízení identifikaci otisku prstu. |
    | <strong>Apple Pay</strong> | Poskytněte uživateli možnost nastavit Apple Pay na zařízení. |
    | <strong>Přibliž</strong> | Poskytněte uživateli možnost přiblížení zobrazení při nastavení zařízení. |
    | <strong>Siri</strong> | Poskytněte uživateli možnost nastavit Siri. |
    | <strong>Diagnostická data</strong> | Zobrazit obrazovku diagnostiky uživateli Tato obrazovka uživateli dává možnost Odeslat diagnostická data do Applu. |
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

17. Profil uložíte tak, že kliknete na **vytvořit**.

## <a name="sync-managed-devices"></a>Synchronizovat spravovaná zařízení
Když má Intune oprávnění ke správě vašich zařízení, můžete synchronizovat Intune s Apple, aby se spravovaná zařízení zobrazila v Intune v Azure Portal.

1. V Intune v Azure Portal vyberte **registrace zařízení** > registrace **Apple** > **tokeny programu registrace** > v seznamu > **zařízení** > **synchronizace**vyberte token. @no__t – 8Screenshot uzlu zařízení programu registrace a odkazu na synchronizaci. ](./media/device-enrollment-program-enroll-ios/image06.png)

   Pokud chcete dodržovat podmínky společnosti Apple pro přijatelný provoz programu registrace, Intune ukládá tato omezení:
   - Úplná synchronizace může běžet maximálně po dobu sedmi dnů. Během úplné synchronizace Intune Načte Úplný aktualizovaný seznam sériových čísel přiřazených k serveru Apple MDM připojenému k Intune. Pokud se zařízení DEP z portálu Intune odstraní, měl by být na portálu DEP na serveru Apple MDM nepřiřazený. Pokud není přiřazená, nebude se znovu naimportovat do Intune, dokud se nespustí Úplná synchronizace.   
   - Synchronizace se spouští automaticky každých 24 hodin. Synchronizaci můžete provést také kliknutím na tlačítko **synchronizovat** (ne více než jednou za 15 minut). Dokončení všech žádostí o synchronizaci je 15 minut. Tlačítko **synchronizovat** je zakázané, dokud se synchronizace nedokončí. Tato synchronizace obnoví stávající stav zařízení a importuje nová zařízení přiřazená k serveru Apple MDM.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Přiřazení registračního profilu k zařízením
Předtím, než se můžou zařízení zaregistrovat, musíte jim přiřadit profil programu registrace.

>[!NOTE]
>Můžete také přiřadit sériová čísla k profilům z okna **Apple sériových čísel** .

1. V Intune v Azure Portal klikněte na **registrace zařízení** >  registrace**Apple** > **tokeny programu registrace** > v seznamu vyberte token.
2. Vyberte **zařízení** > v seznamu vyberte zařízení > **přiřadit profil**.
3. V části **přiřadit profil**vyberte profil pro zařízení > **přiřadit**.

### <a name="assign-a-default-profile"></a>Přiřadit výchozí profil

Můžete vybrat výchozí profil, který se použije pro všechna zařízení zaregistrovaná pomocí konkrétního tokenu.

1. V Intune v Azure Portal klikněte na **registrace zařízení** >  registrace**Apple** > **tokeny programu registrace** > v seznamu vyberte token.
2. Zvolte **nastavit výchozí profil**, v rozevíracím seznamu vyberte profil a pak zvolte **Uložit**. Tento profil se použije pro všechna zařízení, která se registrují s tokenem.

## <a name="distribute-devices"></a>Distribuce zařízení
Povolili jste správu a synchronizaci mezi společností Apple a Intune a přiřadili jste profil, který umožní registraci zařízení DEP. Nyní můžete zařízení distribuovat uživatelům. Zařízení s přidružením uživatele vyžadují, aby každý uživatel měl přiřazenou licenci Intune. Zařízení bez přidružení uživatele vyžadují licenci na zařízení. Aktivované zařízení nemůže použít registrační profil, dokud se zařízení nevymaže.

Další informace najdete [v tématu Registrace zařízení se systémem iOS v Intune pomocí program registrace zařízení](/intune-user-help/enroll-your-device-dep-ios).

## <a name="renew-a-dep-token"></a>Prodloužit platnost tokenu DEP  
1. Přejít na deploy.apple.com.  
2. V části **Spravovat servery**vyberte server MDM přidružený k souboru tokenu, který chcete obnovit.
3. Vyberte možnost **generovat nový token**.

    ![Snímek obrazovky pro vygenerování nového tokenu](./media/device-enrollment-program-enroll-ios/generatenewtoken.png)

4. Vyberte **token serveru**.  
5. V [Intune v Azure Portal](https://aka.ms/intuneportal)klikněte na **registrace zařízení** >  registrace**Apple** > **tokeny programu registrace** > vyberte token.
    @no__t – 0Screenshot tokenů programu registrace. ](./media/device-enrollment-program-enroll-ios/enrollmentprogramtokens.png)

6. Vyberte **obnovit token** a zadejte Apple ID, které jste použili k vytvoření původního tokenu.  
    @no__t 0Screenshot generování nového tokenu. ](./media/device-enrollment-program-enroll-ios/renewtoken.png)

8. Nahrajte nově stažený token.  
9. Vyberte **obnovit token**. Zobrazí se potvrzení, že byl token obnoven.   
    @no__t – 0Screenshot potvrzení. ](./media/device-enrollment-program-enroll-ios/confirmation.png)
