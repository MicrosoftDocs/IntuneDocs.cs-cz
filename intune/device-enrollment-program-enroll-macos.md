---
title: Registrace zařízení s macOS – Program registrace zařízení
titleSuffix: Microsoft Intune
description: Přečtěte si, jak k registraci zařízení s macOS, které je v majetku firmy, použít Program registrace zařízení (DEP).
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 18b4ab35627e1ccb694104f3f5800e5fb07dd1c7
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313422"
---
# <a name="automatically-enroll-macos-devices-with-apples-device-enrollment-program"></a>Automatická registrace zařízení s macOS do Programu registrace zařízení Apple

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek vám pomůže nastavit registraci zařízení s macOS koupených prostřednictvím [Programu registrace zařízení Apple (DEP)](https://deploy.apple.com). Registraci do programu DEP můžete nastavit pro velký počet zařízení, i když je nemáte fyzicky v rukou. Tato zařízení s macOS můžete dát rovnou uživatelům. Když uživatel zařízení zapne, Průvodce nastavením spustí předem nakonfigurovaná nastavení a zařízení se zaregistruje do správy v Intune.

K nastavení registrace do programu DEP můžete použít portál Intune nebo portál Programu registrace zařízení Apple (DEP). Vytvoříte registrační profily DEP obsahující nastavení aplikovaná na zařízení během registrace.

Registrace DEP mimochodem se [správcem registrace zařízení](device-enrollment-manager-enroll.md) nefunguje.

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
- Seznam sériových čísel nebo čísel nákupních objednávek 
- [Autorita pro správu mobilních zařízení (MDM)](mdm-authority-set.md)
- [Certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Získání tokenu DEP Apple

K registraci zařízení s macOS do programu DEP potřebujete od Applu soubor s tokenem DEP (.p7m). Token umožňuje Intune synchronizovat informace o zařízeních v rámci DEP, která vaše společnost vlastní. Umožňuje také Intune nahrát profily registrace do Applu a přiřadit tyto profily zařízením.

Token DEP vytvoříte pomocí portálu DEP společnosti Apple. Pomocí portálu DEP také přiřadíte zařízení do Intune ke správě.

> [!NOTE]
> Když token odstraníte z klasického portálu Intune před migrací do Azure, může Intune obnovit odstraněný token DEP Apple. Token DEP můžete z portálu Azure Portal znovu odstranit.

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
V poli **Token Apple** přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Vytvořit**. Certifikát Push Certificate umožňuje Intune registrovat a spravovat zařízení s macOS tím, že do registrovaných zařízení doručí zásady. Intune se automaticky synchronizuje s Apple, aby bylo možné zobrazit účet registračního programu.

## <a name="create-an-apple-enrollment-profile"></a>Vytvoření registračního profilu Apple

Po nainstalování tokenu můžete vytvořit registrační profil pro zařízení DEP. Registrační profil zařízení definuje nastavení, která se během registrace použijí pro skupinu zařízení.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace**.
2. Vyberte token, zvolte **Profily** a potom zvolte **Vytvořit profil**.

    ![Snímek obrazovky pro vytvoření profilu](./media/device-enrollment-program-enroll-ios/image04.png)

3. V části **Vytvořit profil** zadejte **Název** a **Popis** profilu pro účely správy. Uživatelům se tyto údaje nezobrazí. Pole **Název** můžete využít k vytvoření dynamické skupiny v Azure Active Directory. Název profilu použijte k definování parametru enrollmentProfileName pro přiřazení zařízení s tímto registračním profilem. Přečtěte si další informace o [dynamických skupinách Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

    ![Název a popis profilu](./media/device-enrollment-program-enroll-macos/createprofile.png)

4. Jako **platformu** zvolte **macOS**.

5. V části **Přidružení uživatele** vyberte, jestli zařízení s tímto profilem musí mít při registraci přiřazeného uživatele.
    - **Zaregistrovat s přidružením uživatele** – tuto možnost vyberte u zařízení patřících uživatelům, kteří chtějí aplikaci Portál společnosti používat pro služby, jako je instalace aplikací. Při použití ADFS vyžaduje přidružení uživatelů [koncový bod WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints). [Další informace](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint). Vícefaktorové ověřování nepodporují zařízení s macOS a přidružením uživatele zaregistrovaná v programu DEP.

    - **Zaregistrovat bez přidružení uživatele** – Tuto možnost zvolte pro zařízení nespojená s jedním uživatelem. Použijte ji pro zařízení určená k plnění úkolů, u kterých není potřeba přístup k místním uživatelským datům. Aplikace, jako je aplikace Portál společnosti, nefungují.

6. Zvolte **Nastavení správy zařízení** a vyberte, jestli chcete zařízením, která používají tento profil, povolit uzamčenou registraci. **Uzamčená registrace** zakáže nastavení macOS, která umožňují odebrání profilu správy z nabídky **Předvolby systému** nebo přes **Terminál**. Po registraci zařízení nemůžete toto nastavení změnit bez vymazání zařízení.

    ![Snímek obrazovky s nastaveními správy zařízení](./media/device-enrollment-program-enroll-macos/devicemanagementsettingsblade-macos.png)
 
7. Vyberte **OK**.

8. Zvolte **Nastavení Průvodce nastavením** a nakonfigurujte následující nastavení profilu: ![Přizpůsobení Průvodce nastavením](./media/device-enrollment-program-enroll-macos/setupassistantcustom-macos.png).

    | Nastavení oddělení | Popis |
    |---|---|
    | <strong>Název oddělení</strong> | Zobrazí se, když uživatelé klepnou při aktivaci na <strong>O konfiguraci</strong>. |
    | <strong>Telefon na oddělení</strong> | Zobrazí se, když uživatel při aktivaci klikne na tlačítko <strong>Potřebuji nápovědu</strong>. |

  Můžete zvolit, jestli se různé obrazovky Průvodce nastavením mají uživateli zobrazit nebo skrýt.
  - Pokud zvolíte **Skrýt**, obrazovka se při nastavování nezobrazí. Po nastavení zařízení může uživatel přejít do nabídky **Nastavení** a funkci nastavit tam.
  - Pokud zvolíte **Zobrazit**, obrazovka se při nastavování zobrazí. Uživatel může obrazovku někdy přeskočit a neudělat žádnou akci. Může ale později přejít do nabídky zařízení **Nastavení** a funkci nastavit tam. 


    | Nastavení na obrazovce Průvodce nastavením | Pokud zvolíte **Zobrazit**, zařízení při nastavování: |
    |------------------------------------------|------------------------------------------|
    | <strong>Heslo</strong> | Vyzve uživatele k zadání hesla. Vyžaduje vždy heslo, pokud zařízení nebude zabezpečené nebo nebude mít přístup kontrolovaný jiným způsobem (třeba pomocí celoobrazovkového režimu, který omezuje zařízení na jednu aplikaci). |
    | <strong>Zjišťování polohy</strong> | Vyzve uživatele k poskytnutí polohy. |
    | <strong>Obnovení</strong> | Zobrazí obrazovku **Aplikace a data**. Tato obrazovka nabídne uživateli při nastavování zařízení možnost obnovit nebo přenést data ze zálohy v iCloudu. |
    | <strong>iCloud a Apple ID</strong> | Umožní uživateli přihlásit se pomocí svého **Apple ID** a používat **iCloud**.                         |
    | <strong>Podmínky a ujednání</strong> | Požaduje, aby uživatel přijal podmínky a ujednání společnosti Apple. |
    | <strong>Touch ID</strong> | Umožní uživateli nastavit pro zařízení identifikaci otiskem prstu. |
    | <strong>Apple Pay</strong> | Umožní uživateli nastavit na zařízení Apple Pay. |
    | <strong>Lupa</strong> | Umožní uživateli zvětšit zobrazení při nastavování zařízení. |
    | <strong>Siri</strong> | Umožní uživateli nastavit Siri. |
    | <strong>Diagnostická data</strong> | Zobrazí uživateli obrazovku **Diagnostická data**. Tato obrazovka umožní uživateli poslat společnosti Apple diagnostická data. |
    | <strong>FileVault</strong> | Umožní uživateli nastavit šifrování FileVault. |
    | <strong>Diagnostika iCloudu</strong> | Umožní uživateli poslat společnosti Apple diagnostická data iCloudu. |
    | <strong>Registrace</strong>| Vyžaduje, aby uživatel zařízení zaregistroval. |

   

10. Vyberte **OK**.

11. Pokud chcete profil uložit, zvolte **Vytvořit**.

## <a name="sync-managed-devices"></a>Synchronizace spravovaných zařízení
Teď, když má Intune oprávnění spravovat vaše zařízení, můžete synchronizovat Intune s Apple, aby se spravovaná zařízení zobrazila v Intune na portálu Azure Portal.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny Programu registrace** > zvolte token v seznamu > **Zařízení** > **Synchronizovat**. ![Snímek obrazovky s vybraným uzlem Zařízení Programu registrace a vybraným odkazem pro synchronizaci](./media/device-enrollment-program-enroll-ios/image06.png)

   Kvůli dodržení podmínek společnosti Apple, které se týkají přijatelných přenosů při registraci v programu, platí v Intune následující omezení:
   - Úplná synchronizace se nesmí pouštět častěji než jednou za sedm dní. Během úplné synchronizace načte Intune úplný aktualizovaný seznam sériových čísel přiřazených k serveru Apple MDM připojenému k Intune. Pokud se zařízení v rámci programu registrace odstraní z portálu Intune, aniž by se zrušilo jeho přiřazení ze serveru MDM Apple na portálu DEP, nebude možné ho do Intune znovu naimportovat, dokud neproběhne úplná synchronizace.   
   - Synchronizace se spouští automaticky každých 24 hodin. Můžete ji také spustit kliknutím na tlačítko **Synchronizovat** (ne častěji než jednou za 15 minut). Každá žádost o synchronizaci má 15 minut na dokončení. Tlačítko **Synchronizovat** bude deaktivované, dokud se synchronizace nedokončí. Při synchronizaci se zaktualizuje stav existujících zařízení a naimportují se nová zařízení přiřazená k serveru Apple MDM.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Přiřazení profilu registrace zařízením
Než se můžou zařízení zaregistrovat, musíte přiřadit profil programu registrace.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny Programu registrace** > zvolte token v seznamu.
2. Zvolte **Zařízení** > zvolte zařízení v seznamu > **Přiřadit profil**.
3. V části **Přiřadit profil** zvolte profil pro zařízení > **Přiřadit**.

### <a name="assign-a-default-profile"></a>Přiřazení výchozího profilu

Můžete vybrat výchozí profil macOS a iOS, který se použije u všech zařízení, pokud při registraci použijí určitý token. 

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **registrace zařízení Apple** > **Tokeny Programu registrace** a vyberte v seznamu token.
2. Zvolte **Nastavit výchozí profil**, v rozevíracím seznamu zvolte profil a potom zvolte **Uložit**. Tento profil se použije pro všechna zařízení, která se registrují s tímto tokenem.

## <a name="distribute-devices"></a>Distribuujte zařízení.
Povolili jste správu a synchronizaci mezi společností Apple a Intune a přiřadili jste profil, který umožní registraci zařízení DEP. Teď můžete zařízení rozdělit mezi uživatele. U zařízení s přidruženými uživateli je potřeba, aby měl každý uživatel přiřazenu licenci Intune. Zařízení bez přidružení uživatele vyžadují licenci zařízení. Aktivované zařízení nemůže použít profil registrace, dokud se zařízení nevymaže.

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

## <a name="next-steps"></a>Další kroky

Jakmile zaregistrujete zařízení s macOS, můžete je začít [spravovat](device-management.md).