---
title: Registrace zařízení s iOSem – Program registrace zařízení
titleSuffix: Microsoft Intune
description: Naučte se registrovat zařízení s iOSem ve vlastnictví firmy pomocí Programu registrace zařízení (DEP).
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: db9f15fd021cecc3f160e85be7a1a6cb7d1656a6
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59897642"
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>Automatická registrace zařízení s iOSem pomocí Programu registrace zařízení společnosti Apple

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Můžete nastavit Intune pro registraci zařízení s Iosem zakoupená prostřednictvím Apple [programu registrace zařízení (DEP)](https://deploy.apple.com). Program DEP umožňuje vzdáleně registrovat velká množství zařízení bezkontaktně nikdy. Zařízení, jako jsou Iphony a Ipady můžete dodávají přímo uživatelům. Když uživatel zařízení zapne, Pomocník s nastavením provede předem nakonfigurovaná nastavení a zařízení se zaregistruje ke správě.

Registraci do programu DEP můžete povolit na portálu Intune i na portálu DEP společnosti Apple. Abyste mohli zařízení přiřadit do Intune ke správě, potřebujete seznam sériových čísel nebo čísla nákupních objednávek. Vytvoříte registrační profily DEP obsahující nastavení aplikovaná na zařízení během registrace.

Mimochodem registraci v programu DEP nefunguje při využití [správce registrace zařízení](device-enrollment-manager-enroll.md).

## <a name="what-is-supervised-mode"></a>Co je režim Pod dohledem?
Apple režim Pod dohledem představil v systému iOS 5. Zařízení s iOSem v režimu Pod dohledem je možné spravovat několika ovládacími prvky. V důsledku toho je obzvlášť užitečný pro zařízení vlastněná společností. Intune podporuje konfiguraci zařízení do režimu Pod dohledem v rámci programu registrace zařízení Apple (DEP). 

Podpora zařízení registrovaných v programu DEP, která nejsou pod dohledem, byla v iOS 11 ukončena. V iOS 11 a novějších verzích musí být zařízení nakonfigurovaná v programu DEP vždy pod dohledem. Příznak is_supervised programu DEP bude v příštích verzích iOS ignorován.

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
- [Autoritu pro správu (MDM) mobilních zařízení](mdm-authority-set.md)
- [Certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Získání tokenu DEP Apple

Abyste mohli zařízení s iOSem v programu DEP zaregistrovat, potřebujete od společnosti Apple token DEP (.p7m). Token umožňuje Intune synchronizovat informace o zařízeních v rámci DEP, která vaše společnost vlastní. Umožňuje také Intune odeslat společnosti Apple registrační profily a přiřazovat k těmto profilům zařízení.

Token DEP vytvoříte pomocí portálu DEP společnosti Apple. Pomocí portálu DEP také přiřadíte zařízení do Intune ke správě.

> [!NOTE]
> Když token odstraníte z klasického portálu Intune před migrací do Azure, může Intune obnovit odstraněný token DEP Apple. Token DEP můžete z portálu Azure Portal znovu odstranit.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Krok 1. Stáhněte si certifikát veřejného klíče Intune, který je potřebný k vytvoření tokenu.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace** > **Přidat**.

    ![Stažení tokenu programu registrace zařízení](./media/device-enrollment-program-enroll-ios/image01.png)

2. Výběrem možnosti **Souhlasím** udělte Microsoftu oprávnění k odesílání informací o uživatelích a zařízeních do společnosti Apple.

   ![Snímek obrazovky s podoknem Token Programu registrace v pracovním prostoru Certifikáty Apple pro stažení veřejného klíče](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Vyberte **Stáhnout veřejný klíč** a stáhněte si a místně uložte soubor šifrovacího klíče (.pem). Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Device Enrollment Program.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Krok 2. Pomocí klíče si stáhněte token od společnosti Apple.

1. Pokud chcete otevřít portál Programu registrace zařízení Apple (DEP), zvolte **Vytvořit token pro Program registrace zařízení Apple** a přihlaste se pomocí firemního Apple ID. Toto Apple ID můžete použít k obnovení tokenu DEP.
2.  Na [portálu společnosti Apple pro nasazení programů](https://deploy.apple.com) vyberte **Začínáme**. Otevře se **Program registrace zařízení**.

3. Na stránce pro **správu serverů** zvolte, že chcete **přidat server MDM**.
4. Zadejte **název serveru MDM** a zvolte **Další**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Není to název nebo adresu URL serveru pro Microsoft Intune.

5. Otevře se dialogové okno pro **přidání&lt;názvu serveru&gt;**, ve kterém se zobrazí výzva, abyste **nahráli svůj veřejný klíč**. Vyberte **zvolit soubor...** abyste mohli nahrát soubor .pem, a pak zvolte **Další**.

6. Přejděte na **Deployment Programs** (Programy nasazení) &gt; **Device Enrollment Program** (Program registrace zařízení) &gt; **Manage Devices** (Spravovat zařízení).
7. V části se **způsobem výběru zařízení** určete způsob identifikace zařízení:
    - **Sériové číslo**
    - **Číslo objednávky**
    - **Nahrát soubor CSV**

   ![Snímek obrazovky s výběrem zařízení podle sériového čísla, nastavením volby akce na přiřazení serveru a výběrem názvu serveru](./media/enrollment-program-token-specify-serial.png)

8. V možnosti **Vybrat akci** vyberte **Přiřadit k serveru**, vyberte &lt;název_serveru&gt; zadaný pro Microsoft Intune a pak zvolte **OK**. Portál Apple přiřadí daná zařízení k serveru Intune, aby bylo možné je spravovat, a pak zobrazí zprávu o **dokončení přiřazení**.

   Na portálu Apple přejděte na **Programy nasazení** &gt; **Program registrace zařízení** &gt; **Zobrazit historii přiřazení**. Zobrazí se seznam zařízení s přiřazeným serverem MDM.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Krok 3. Uložte si Apple ID, které jste použili k vytvoření tohoto tokenu.

V Intune na portálu Azure Portal zadejte Apple ID pro budoucí použití.

![Snímek obrazovky s Apple ID použitým k vytvoření tokenu programu registrace a přechodem na token programu registrace](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token-and-choose-scope-tags"></a>Krok 4. Nahrajte token a zvolte značky oboru.

1. V **token pro Apple** pole, vyhledejte soubor certifikátu (.pem), zvolte **otevřít**.
2. Pokud chcete použít [značky oboru](scope-tags.md) tento token DEP zvolte **obor (značky)** a vyberte značky oboru, které chcete. Značky oboru u tokenu zdědí profilů a zařízení přidat do tohoto tokenu.
3. Zvolte **Vytvořit**.

S certifikátem Push Certificate může Intune registrovat a spravovat zařízení s iOSem a vynucovat zásady na zaregistrovaných mobilních zařízeních. Intune se automaticky synchronizuje s Apple, aby bylo možné zobrazit účet registračního programu.

## <a name="create-an-apple-enrollment-profile"></a>Vytvoření registračního profilu Apple

Po nainstalování tokenu můžete vytvořit registrační profil pro zařízení DEP. Registrační profil zařízení definuje nastavení, která se během registrace použijí pro skupinu zařízení.

> [!NOTE]
> Zařízení se zablokuje, pokud nejsou k dispozici dostatek licencí portál společnosti pro VPP token, nebo pokud vypršela platnost tokenu. Intune se zobrazit upozornění, když token brzy vyprší platnost nebo není k dispozici dostatek licencí.
 

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace**.
2. Vyberte token, zvolte **Profily** a potom zvolte **Vytvořit profil**.

    ![Snímek obrazovky pro vytvoření profilu](./media/device-enrollment-program-enroll-ios/image04.png)

3. V části **Vytvořit profil** zadejte **Název** a **Popis** profilu pro účely správy. Uživatelé nezobrazuje tyto podrobnosti. Pole **Název** můžete využít k vytvoření dynamické skupiny v Azure Active Directory. Název profilu použijte k definování parametru enrollmentProfileName pro přiřazení zařízení s tímto registračním profilem. Přečtěte si další informace o [dynamických skupinách Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

    ![Název a popis profilu](./media/device-enrollment-program-enroll-ios/image05.png)

4. V části **Přidružení uživatele** zvolte, jestli se zařízení s tímto profilem musí registrovat s přiřazeným uživatelem nebo bez něj.
    - **Zaregistrovat s přidružením uživatele** – tuto možnost vyberte u zařízení patřících uživatelům, kteří chtějí Portál společnosti používat pro služby, jako je instalace aplikací. Pokud používáte ADFS a pokud je v registračním profilu možnost **ověření na Portálu společnosti místo v Průvodci nastavením Applu** nastavená na **Ne**, musí být zadané [uživatelské jméno koncového bodu WS-Trust 1.3 nebo koncový bod s kombinovaným režimem zabezpečení](https://technet.microsoft.com/library/adfs2-help-endpoints). [Další informace](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Zaregistrovat bez přidružení uživatele** – Tuto možnost zvolte pro zařízení nespojená s jedním uživatelem. Použijte ji pro zařízení určená k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, jako je aplikace Portál společnosti, nefungují.

5. Pokud jste zvolili **zaregistrovat s přidružením uživatele**, můžete nechat uživatelé ověřovali pomocí portálu společnosti místo Pomocníka pro instalaci Apple.

    ![Ověření pomocí portálu společnosti](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Pokud chcete provést některou z následujících akcí, nastavte možnost **ověření na Portálu společnosti místo v Průvodci nastavením Applu** na **Ano**.
    >    - Použít vícefaktorové ověřování.
    >    - Zobrazit výzvu uživatelům, pokud při prvním přihlášení potřebují změnit heslo.
    >    - Zobrazit výzvu uživatelům, aby při registraci resetovali neplatná hesla.
    >
    > Tato možnost není podporovaná, pokud se k ověření použije Průvodce nastavením společnosti Apple.

6. Pokud jste zvolili **Ano** pro **ověřování pomocí portálu společnosti místo Pomocníka pro nastavení Apple**, token Volume Purchase Program (VPP) můžete automaticky nainstalovat aplikaci portál společnosti na zařízení. V tomto případě uživatel nemá k zadání Apple ID. K instalaci Portálu společnosti pomocí tokenu VPP zvolte token v seznamu **Nainstalovat Portál společnosti pomocí VPP**. Dbejte na to, aby tokenu nevypršela platnost a abyste měli dost licencí zařízení pro aplikaci Portál společnosti. Pokud tokenu vyprší platnost nebo dojde licencí, Intune místo toho nainstaluje aplikaci portál společnosti App Store a vyzve k zadání Apple ID.

    ![Snímek obrazovky se nainstaloval portál společnosti s VPP.](./media/device-enrollment-program-enroll-ios/install-cp-with-vpp.png)

7. Pokud jste zvolili token **nainstalovat portál společnosti s VPP**, po dokončení pomocníka můžete zařízení uzamknout režim jedné aplikace (konkrétně v aplikaci portál společnosti) vpravo. Tuto možnost nastavíte volbou **Ano** u položky **Spustit Portál společnosti v režimu Jedna aplikace, dokud neproběhne ověření**. Než bude uživatel moct zařízení použít, musí se nejprve ověřit přihlášením na Portálu společnosti.
    Tato funkce je podporované jenom pro iOS 11.3.1 a novější.

   ![Snímek obrazovky režimu jedné aplikace.](./media/device-enrollment-program-enroll-ios/single-app-mode.png)

8. Zvolte **nastavení správy zařízení** a zvolte, pokud chcete, aby zařízení pod dohledem se používají tento profil.

    ![Snímek obrazovky s nastaveními správy zařízení](./media/device-enrollment-program-enroll-ios/devicemanagementsettingsblade.png)

    U zařízení **pod dohledem** je ve výchozím nastavení víc možností správy a je zakázaný zámek aktivace. Společnost Microsoft doporučuje program DEP používat jako mechanismus pro povolení režimu pod dohledem, zejména v případě, že nasazujete velký počet zařízení s Iosem.

    Uživatelé se dozvědí, že jejich zařízení jsou pod dohledem, dvěma způsoby:

   - Zamykací obrazovce se zobrazí oznámení: "Tento iPhone spravuje Contoso."
   - **Nastavení** > **Obecné** > **o** obrazovce se zobrazí oznámení: "Tento iPhone je pod dohledem. Společnost Contoso může monitorovat internetové přenosy a zařízení vyhledat.“

     > [!NOTE]
     > Zařízení zaregistrované bez dohledu se dá resetovat do stavu pod dohledem jenom pomocí Apple Configuratoru. Resetování zařízení tímto způsobem vyžaduje připojení zařízení s iOSem k Macu pomocí kabelu USB. Další informace na toto téma získáte v [dokumentaci Apple Configuratoru](http://help.apple.com/configurator/mac/2.3).

9. Zvolte, pokud chcete, uzamčená registrace pro zařízení s tímto profilem. **Uzamčená registrace** zakáže nastavení iOSu, která umožňují odebrání profilu správy z nabídky **Nastavení**. Po registraci zařízení nemůžete toto nastavení změnit bez vymazání obsahu zařízení. Taková zařízení musí mít režim správy **Pod dohledem** nastavený na *Ano*. 

10. Zvolte, jestli mají zařízení používají tento profil, abyste mohli **synchronizovat s počítači**. Pokud vyberete **Povolit Apple Configurator podle certifikátu**, musíte zvolit certifikát v části **Certifikáty Apple Configuratoru**.

11. Pokud jste v předchozím kroku zvolili **Povolit Apple Configurator podle certifikátu**, zvolte certifikát Apple Configuratoru, který se má importovat.

12. Můžete zadat formát názvů pro zařízení, který se automaticky použije, když zaregistrují. Chcete-li vytvořit šablonu pojmenování, vyberte **Ano** pod **použít šablonu název zařízení**. Potom v **šablony názvu zařízení** zadejte šablonu, kterou chcete použít pro tyto názvy, které používají tento profil. Můžete určit formát šablony, která obsahuje typ zařízení a sériové číslo.

13. Zvolte **OK**.

14. Zvolte **pomocníka pro nastavení přizpůsobení** a nakonfigurujte následující nastavení profilu: ![Nastavení přizpůsobení průvodce nastavením.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    | Nastavení oddělení | Popis |
    |---|---|
    | <strong>Název oddělení</strong> | Zobrazí se, když uživatelé klepnou při aktivaci na <strong>O konfiguraci</strong>. |
    |    <strong>Telefon na oddělení</strong>     | Zobrazí se, když uživatel při aktivaci klikne na tlačítko <strong>Potřebuji nápovědu</strong>. |

  Můžete skrýt nastavením obrazovky na zařízení během nastavení uživatele.
  - Pokud zvolíte **Skrýt**, obrazovka se při nastavování nezobrazí. Po nastavení zařízení může uživatel přejít do nabídky **Nastavení** a funkci nastavit tam.
  - Pokud zvolíte **Zobrazit**, obrazovka se při nastavování zobrazí. Uživatel může obrazovku někdy přeskočit a neudělat žádnou akci. Může ale později přejít do nabídky zařízení **Nastavení** a funkci nastavit tam. 


    | Nastavení na obrazovce Průvodce nastavením | Pokud zvolíte **Zobrazit**, zařízení při nastavování: |
    |------------------------------------------|------------------------------------------|
    | <strong>Heslo</strong> | Vyzve uživatele k zadání hesla. Vždy vyžaduje heslo pro zabezpečená zařízení, pokud se řídí přístup k jiným způsobem (třeba pomocí beznabídkového režimu, který omezuje zařízení na jednu aplikaci). |
    | <strong>Zjišťování polohy</strong> | Vyzve uživatele k poskytnutí polohy. |
    | <strong>Obnovení</strong> | Zobrazí obrazovku **Aplikace a data**. Tato obrazovka nabídne uživateli při nastavování zařízení možnost obnovit nebo přenést data ze zálohy v iCloudu. |
    | <strong>iCloud a Apple ID</strong> | Umožní uživateli přihlásit se pomocí svého **Apple ID** a používat **iCloud**.                         |
    | <strong>Podmínky a ujednání</strong> | Požaduje, aby uživatel přijal podmínky a ujednání společnosti Apple. |
    | <strong>Touch ID</strong> | Umožní uživateli nastavit pro zařízení identifikaci otiskem prstu. |
    | <strong>Apple Pay</strong> | Umožní uživateli nastavit na zařízení Apple Pay. |
    | <strong>Přiblížení</strong> | Umožní uživateli zvětšit zobrazení při nastavování zařízení. |
    | <strong>Siri</strong> | Umožní uživateli nastavit Siri. |
    | <strong>Diagnostická data</strong> | Zobrazí uživateli obrazovku **Diagnostická data**. Tato obrazovka umožní uživateli poslat společnosti Apple diagnostická data. |
    | <strong>Zobrazit tón</strong> | Umožnit uživateli zapnout tón zobrazení. |
    | <strong>Ochrana osobních údajů</strong> | Zobrazte na obrazovce o ochraně osobních údajů pro uživatele. |
    | <strong>Android Migration</strong> | Uživateli přidělit možnosti můžete migrovat data ze zařízení s Androidem. |
    | <strong>iMessage a FaceTime</strong> | Umožnit uživateli nastavit iMessage a FaceTime. |
    | <strong>Registrace</strong> | Zobrazit informační obrazovky registrace pro vzdělávání uživatelů, jako je například zahrnovat list a multitaskingu a Control Centeru. |
    | <strong>Podívejte se na migraci</strong> | Umožnit uživateli pro migraci dat ze zařízení kukátka. |
    | <strong>Čas obrazovky</strong> | Zobrazte obrazovku čas obrazovky. |
    | <strong>Aktualizace softwaru</strong> | Zobrazte obrazovku povinné softwarové aktualizace. |
    | <strong>Instalační program SIM</strong> | Umožnit uživateli přidat mobilní plánu. |

15. Zvolte **OK**.

16. Pokud chcete profil uložit, zvolte **Vytvořit**.

## <a name="sync-managed-devices"></a>Synchronizace spravovaných zařízení
Teď, když má Intune oprávnění spravovat vaše zařízení, můžete synchronizovat Intune s Apple, aby se spravovaná zařízení zobrazila v Intune na portálu Azure Portal.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny Programu registrace** > zvolte token v seznamu > **Zařízení** > **Synchronizovat**. ![Snímek obrazovky s uzlem zařízení programu registrace a odkazem synchronizaci.](./media/device-enrollment-program-enroll-ios/image06.png)

   Pokud chcete postupovat s podmínkami společnosti Apple pro přijatelné registrace programu provoz, Intune platí následující omezení:
   - Úplná synchronizace se nesmí pouštět častěji než jednou za sedm dní. Během úplné synchronizace načte Intune úplný aktualizovaný seznam sériových čísel přiřazených k serveru Apple MDM připojenému k Intune. Pokud zařízení s programem DEP se odstraní z portálu Intune, je potřeba zrušit z Apple MDM server na portálu programu DEP. Pokud není nepřiřazené, ji nebude možné importovat do Intune dokud spustit úplnou synchronizaci.   
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
Povolili jste správu a synchronizaci mezi společností Apple a Intune a přiřadili jste profil, který umožní registraci zařízení DEP. Teď můžete zařízení rozdělit mezi uživatele. U zařízení s přidruženými uživateli je potřeba, aby měl každý uživatel přiřazenu licenci Intune. Zařízení bez přidružení uživatele vyžadují licenci zařízení. Aktivované zařízení nemůže použít profil registrace, dokud se zařízení vymaže.

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
