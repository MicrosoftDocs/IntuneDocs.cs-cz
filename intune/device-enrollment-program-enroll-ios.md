---
title: "Registrace zařízení s iOSem pomocí Programu registrace zařízení (DEP)"
titlesuffix: Microsoft Intune
description: "Naučte se registrovat zařízení s iOSem ve vlastnictví firmy pomocí Programu registrace zařízení (DEP)."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 24b1ffb1d89f52a51f21dc6c4a588324f3cd87d3
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="automatically-enroll-ios-devices-by-using-apples-device-enrollment-program"></a>Automatická registrace zařízení s iOSem pomocí Programu registrace zařízení společnosti Apple

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

> [!NOTE]
> ### <a name="temporary-user-interface-differences"></a>Dočasné rozdíly v uživatelském rozhraní
>
>Uživatelská rozhraní pro funkce popsané na této stránce se právě aktualizují. Tyto aktualizace se budou u všech uživatelských účtů zavádět postupně do konce dubna.
>
>Pokud vaše stránka **Registrace zařízení** vypadá jako na obrázku níže, váš účet se ještě neaktualizoval na nové uživatelské rozhraní a můžete použít tuto stránku nápovědy.
>
>![Původní uživatelské rozhraní Intune](./media/appleenroll-oldui.png)
>
>Pokud vaše stránka **Registrace zařízení** vypadá jako na obrázku níže, máte aktualizované uživatelské rozhraní.  Přejděte na [tuto stránku nápovědy](device-enrollment-program-enroll-ios-newui.md).
>
>![Nové uživatelské rozhraní Intune](./media/appleenroll-newui.png)

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

> [!NOTE]
> Při registraci v programu DEP pro přidružení uživatelů nefunguje vícefaktorové ověřování (MFA). Po registraci vícefaktorové ověřování na zařízeních funguje podle očekávání. Zařízení nemůžou vyzvat uživatele, kteří při prvním přihlášení potřebují změnit své heslo. Výzva k resetování hesla se během registrace nezobrazí ani uživatelům, kterým vypršela platnost hesla. Uživatelé musí heslo resetovat z jiného zařízení.

## <a name="get-the-apple-dep-token"></a>Získání tokenu DEP Apple

Abyste mohli zařízení s iOSem v programu DEP zaregistrovat, potřebujete od společnosti Apple token DEP (.p7m). Token umožňuje Intune synchronizovat informace o zařízeních v rámci DEP, která vaše společnost vlastní. Umožňuje také Intune odeslat společnosti Apple registrační profily a přiřazovat k těmto profilům zařízení.

Token DEP vytvoříte pomocí portálu DEP společnosti Apple. Pomocí portálu DEP také přiřadíte zařízení do Intune ke správě.

> [!NOTE]
> Když token odstraníte z klasického portálu Intune před migrací do Azure, může Intune obnovit odstraněný token DEP Apple. Token DEP můžete z portálu Azure Portal znovu odstranit. Token DEP můžete z portálu Azure Portal znovu odstranit.

**Krok 1: Stáhněte si certifikát veřejného klíče služby Intune, který je potřebný pro vytvoření tokenu DEP Apple.**<br>

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Token Programu registrace**.

  ![Podokno Token Programu registrace v pracovním prostoru Certifikáty Apple](./media/enrollment-program-token-add.png)

2. Vyberte **Stáhnout veřejný klíč** a stáhněte si a místně uložte soubor šifrovacího klíče (.pem). Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Device Enrollment Program.

  ![Podokno Token Programu registrace v pracovním prostoru Certifikáty Apple pro stažení veřejného klíče](./media/enrollment-program-token-download.png)

**Krok 2: Vytvořte token DEP Apple a stáhněte si ho.**<br>
1. Pokud chcete otevřít portál Programu registrace zařízení Apple (DEP), vyberte **Vytvořit token prostřednictvím Programu registrace zařízení Apple** a přihlaste se pomocí firemního Apple ID. Toto Apple ID můžete použít k obnovení tokenu DEP.
2.  Na [portálu společnosti Apple pro nasazení programů](https://deploy.apple.com) vyberte **Začínáme**. Otevře se **Program registrace zařízení**.

3. Na stránce pro **správu serverů** zvolte, že chcete **přidat server MDM**.
4. Zadejte **název serveru MDM** a zvolte **Další**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Není to název serveru Microsoft Intune ani jeho URL.

   ![Přidání názvu serveru MDM pro program DEP a následné kliknutí na tlačítko Další](./media/enrollment-program-token-add-server.png)

5. Otevře se dialogové okno pro **přidání&lt;názvu serveru&gt;**, ve kterém se zobrazí výzva, abyste **nahráli svůj veřejný klíč**. Vyberte **Zvolit soubor**, abyste mohli nahrát soubor .pem, a pak zvolte **Další**.  

6. Přejděte na **Deployment Programs** (Programy nasazení) &gt; **Device Enrollment Program** (Program registrace zařízení) &gt; **Manage Devices** (Spravovat zařízení).
7. V části se **způsobem výběru zařízení** určete způsob identifikace zařízení:
    - **Sériové číslo**
    - **Číslo objednávky**
    - **Nahrát soubor CSV**

   ![Výběr zařízení podle sériového čísla, nastavení volby akce na přiřazení serveru a výběr názvu serveru](./media/enrollment-program-token-specify-serial.png)

8. V možnosti **Vybrat akci** vyberte **Přiřadit k serveru**, vyberte &lt;název_serveru&gt; zadaný pro Microsoft Intune a pak zvolte **OK**. Portál Apple přiřadí daná zařízení k serveru Intune, aby bylo možné je spravovat, a pak zobrazí zprávu o **dokončení přiřazení**.

   Na portálu Apple přejděte na **Programy nasazení** &gt; **Program registrace zařízení** &gt; **Zobrazit historii přiřazení**. Zobrazí se seznam zařízení s přiřazeným serverem MDM.

**Krok 3: Zadejte Apple ID použité k vytvoření tokenu programu registrace.**<br>V Intune na portálu Azure Portal zadejte Apple ID pro budoucí použití.

![Zadání Apple ID použitého k vytvoření tokenu programu registrace a přechod na token programu registrace](./media/enrollment-program-token-apple-id.png)

**Krok 4: Přejděte k tokenu programu registrace, který chcete nahrát.**<br>
Přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Nahrát**. S certifikátem Push Certificate může Intune registrovat a spravovat zařízení s iOSem a vynucovat zásady na zaregistrovaných mobilních zařízeních. Intune se automaticky synchronizuje s Apple, aby bylo možné zobrazit účet registračního programu.

## <a name="create-an-apple-enrollment-profile"></a>Vytvoření registračního profilu Apple

Po nainstalování tokenu můžete vytvořit registrační profil pro zařízení DEP. Registrační profil zařízení definuje nastavení, která se během registrace použijí pro skupinu zařízení.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple**.
2. V části **Program registrace pro Apple** vyberte **Profily Programu registrace** > **Vytvořit**.
3. V části **Vytvořit registrační profil** zadejte **Název** a **Popis** profilu pro účely správy. Uživatelům se tyto údaje nezobrazí. Pole **Název** můžete využít k vytvoření dynamické skupiny v Azure Active Directory. Název profilu použijte k definování parametru enrollmentProfileName pro přiřazení zařízení s tímto registračním profilem. Přečtěte si další informace o [dynamických skupinách Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

  V části **Přidružení uživatele** zvolte, jestli se zařízení s tímto profilem budou registrovat s přiřazeným uživatelem nebo bez.

 - **Zaregistrovat s přidružením uživatele** – zvolte u zařízení, která patří uživatelům a potřebují pro služby, jako je instalace aplikací, použít portál společnosti. Přidružení uživatelů vyžaduje [koncový bod WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints). [Přečtěte si další informace](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Zaregistrovat bez přidružení uživatele** – zvolte pro zařízení nespojená s jedním uživatelem. Použijte u zařízení určených k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, jako je aplikace Portál společnosti, nefungují.

4. Vyberte **Nastavení správy zařízení** a nakonfigurujte následující nastavení profilu:

  ![Výběr režimu správy](./media/enrollment-program-profile-mode.png)
  - **Pod dohledem** – Režim, který nabízí více možností správy a ve výchozím nastavení má zakázaný zámek aktivace. Pokud políčko nezaškrtnete, budete mít omezené možnosti správy. Microsoft doporučuje program DEP používat jako mechanismus pro povolení režimu Pod dohledem zejména organizacím, které nasazují velké množství zařízení s iOSem.

 > [!NOTE]
 > Jakmile se zařízení zaregistruje, není už možné pomocí Intune provést konfiguraci zařízení do režimu Pod dohledem. Jediným způsobem, jak režim Pod dohledem po registraci povolit, je připojit zařízení s iOSem k Macu pomocí USB kabelu a použít Apple Configurator. Tím se zařízení resetuje a proběhne konfigurace do režimu Pod dohledem. Další informace na toto téma získáte v [dokumentaci Apple Configuratoru](http://help.apple.com/configurator/mac/2.3). U zařízení pod dohledem se na zamykací obrazovce zobrazí zpráva „Tento iPhone spravuje společnost Contoso.“ a zpráva „Tento iPhone je pod dohledem. Společnost Contoso může monitorovat internetové přenosy a zařízení vyhledat.“ je uvedená v **Nastavení** > **Obecné** > **Informace**.

  - **Uzamčená registrace** – (Vyžaduje režim správy Pod dohledem.) Zakáže nastavení iOSu, která by mohla umožnit odebrání profilu správy. Pokud políčko nezaškrtnete, půjde profil správy odebrat z nabídky Nastavení. Po registraci zařízení nemůžete toto nastavení změnit bez obnovení továrního nastavení zařízení.

  - **Povolit sdílený iPad** – Program registrace zařízení společnosti Apple sdílený iPad nepodporuje.

  - **Povolit párování** – Určuje, jestli se zařízení s iOSem mohou synchronizovat s počítači. Pokud vyberete **Povolit Apple Configurator podle certifikátu**, musíte zvolit certifikát v části **Certifikáty Apple Configuratoru**.

  - **Certifikáty Apple Configuratoru** – Pokud jste v části **Povolit párování** zvolili **Povolit Apple Configurator podle certifikátu**, vyberte certifikát Apple Configuratoru, který chcete importovat.

  Zvolte **Uložit**.

5. Vyberte **Nastavení Průvodce nastavením** a nakonfigurujte následující nastavení profilu:

  ![Výběr nastavení konfigurace s dostupnými nastaveními pro nový profil programu registrace](./media/enrollment-program-profile-settings.png)
  - **Název oddělení** – Zobrazí se, když uživatelé klepnou při aktivaci na **O konfiguraci**.

  - **Telefon na oddělení** – Zobrazí se, když uživatel při aktivaci klikne na tlačítko **Potřebuji nápovědu**.
    - **Možnosti Pomocníka s nastavením** – Nastavení jsou volitelná a dají se nastavit později v nabídce **Nastavení** systému iOS.
        - **Heslo**
        - **Zjišťování polohy**
        - **Obnovení**
        - **Apple ID**
        - **Podmínky a ujednání**
        - **Touch ID**
        - **Apple Pay**
        - **Lupa**
        - **Siri**
        - **Diagnostická data**

    Zvolte **Uložit**.

9. Uložte nastavení profilu tak, že v okně **Vytvořit registrační profil** zvolíte **Vytvořit**. Profil registrace se zobrazí v programu registrace Apple v seznamu profilů registrace.

## <a name="sync-managed-devices"></a>Synchronizace spravovaných zařízení
Teď, když má Intune oprávnění spravovat vaše zařízení, můžete synchronizovat Intune s Apple, aby se spravovaná zařízení zobrazila v Intune na portálu Azure Portal.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Zařízení Programu registrace** > **Synchronizovat**. Indikátor průběhu vám ukáže dobu, jakou budete muset počkat před dalším vyžádáním synchronizace.

  ![Vybraný uzel Zařízení Programu registrace a vybraný odkaz Synchronizovat](./media/enrollment-program-device-sync.png)
  
2. V okně **Synchronizovat** vyberte **Požadovat synchronizaci**. Indikátor průběhu vám ukáže dobu, jakou budete muset počkat před dalším vyžádáním synchronizace.

   ![Okno Synchronizovat s vybraným odkazem Požadovat synchronizaci](./media/enrollment-program-device-request-sync.png)

   Kvůli dodržení podmínek společnosti Apple, které se týkají přijatelných přenosů při registraci v programu, platí v Intune následující omezení:
     -  Úplná synchronizace se nesmí pouštět častěji než jednou za sedm dní. Během úplné synchronizace Intune aktualizuje všechna sériová čísla Apple přiřazená Intune. Pokud se o úplnou synchronizaci pokusíte do sedmi dnů od předchozí úplné synchronizace, aktualizuje Intune jenom sériová čísla, která ještě nejsou v Intune.
     -  Každá žádost o synchronizaci má 15 minut na dokončení. Po tuto dobu nebo do úspěšného vykonání požadavku je tlačítko **Synchronizovat** neaktivní.
     - Intune synchronizuje nová a odebraná zařízení se společností Apple každých 24 hodin.

3. Pokud chcete zobrazit zařízení, zvolte v pracovním prostoru Programu registrace zařízení možnost **Aktualizovat**.

## <a name="assign-an-enrollment-profile-to-devices"></a>Přiřazení profilu registrace zařízením
Než se můžou zařízení zaregistrovat, musíte přiřadit profil programu registrace.

>[!NOTE]
>Sériová čísla můžete profilům také přiřadit v okně **sériových čísel Apple**.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** a potom **Profily Programu registrace**.
2. V seznamu **Profily Programu registrace** vyberte profil, který chcete zařízením přiřadit, a pak vyberte **Přiřadit zařízení**.

 ![Přiřazení zařízení s vybranou možností Přiřadit](./media/enrollment-program-device-assign.png)

3. Vyberte **Přiřadit** a pak vyberte zařízení, kterým chcete tento profil přiřadit. Dostupná zařízení můžete filtrovat:
  - **nepřiřazené**
  - **libovolné**
  - **&lt;název profilu&gt;**
4. Vyberte zařízení, která chcete přiřadit. Zaškrtnutím políčka nad sloupcem můžete vybrat až 1000 zobrazených zařízení a potom klikněte na **Přiřadit**. Pokud chcete registrovat více než 1 000 zařízení, opakujte postup, dokud nebudou mít všechna zařízení přiřazený profil registrace.

  ![Tlačítko Přiřadit pro přiřazení profilu programu registrace v Intune](media/dep-profile-assignment.png)

## <a name="distribute-devices"></a>Distribuujte zařízení.
Povolili jste správu a synchronizaci mezi společností Apple a Intune a přiřadili jste profil, který umožní registraci zařízení DEP. Teď můžete zařízení rozdělit mezi uživatele. U zařízení s přidruženými uživateli je potřeba, aby měl každý uživatel přiřazenu licenci Intune. Zařízení bez přidružení uživatele vyžadují licenci zařízení. Aktivované zařízení nemůže použít profil registrace, dokud se neprovede obnovení továrního nastavení zařízení.

Přečtěte si téma [Registrace zařízení s iOSem v Intune pomocí programu registrace zařízení](/intune-user-help/enroll-your-device-dep-ios). 


