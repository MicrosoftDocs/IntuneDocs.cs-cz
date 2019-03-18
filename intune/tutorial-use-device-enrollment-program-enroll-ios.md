---
title: Kurz – použití programu Device Enrollment Program registrace zařízení s Iosem v Intune
titleSuffix: Microsoft Intune
description: V tomto kurzu nastavíte společnosti Apple DEP k registraci zařízení s Iosem v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/30/2019
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Device Enrollment Program so that users can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: 88fe825b75e7717740e5a5ca4af4c52e9bb21768
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57400394"
---
# <a name="tutorial-use-the-device-enrollment-program-to-enroll-ios-devices-in-intune"></a>Kurz: Registrace zařízení s Iosem v Intune pomocí programu registrace zařízení
Program registrace zařízení Apple (DEP) usnadňuje registraci zařízení. S Microsoft Intune a DEP zařízení automaticky proběhne okamžiku, kdy uživatel zařízení zapne. Proto můžete zaslat zařízení mnoha uživatelům bez nutnosti nastavit každé zařízení zvlášť. 

V tomto kurzu se naučíte:
> [!div class="checklist"]
> * Získání tokenu DEP Apple
> * Vytvoření skupiny zařízení Autopilot
> * Vytvořit profil nasazení Autopilotu
> * Přiřadit profil nasazení Autopilotu ke skupině zařízení
> * Distribuovat zařízení s Windows uživatelům

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadavky
- Zařízení zakoupená v [Programu registrace zařízení společnosti Apple](http://deploy.apple.com)
- Nastavte [autoritu správy mobilních zařízení](mdm-authority-set.md)
- Získat [certifikátu Apple MDM Push certificate](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Získání tokenu DEP Apple
Před registrací zařízení s Iosem pomocí programu DEP, potřebujete soubor DEP společnosti Apple token (.pem). Token umožňuje Intune synchronizovat informace o zařízeních v rámci DEP, která vaše společnost vlastní. Umožňuje také Intune odeslat společnosti Apple registrační profily a přiřazovat k těmto profilům zařízení.

Token DEP vytvoříte pomocí portálu DEP společnosti Apple. Pomocí portálu DEP také přiřadíte zařízení do Intune ke správě.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace** > **Přidat**.

2. Výběrem možnosti **Souhlasím** udělte Microsoftu oprávnění k odesílání informací o uživatelích a zařízeních do společnosti Apple.

   ![Snímek obrazovky s podoknem Token Programu registrace v pracovním prostoru Certifikáty Apple pro stažení veřejného klíče](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Vyberte **Stáhnout veřejný klíč** a stáhněte si a místně uložte soubor šifrovacího klíče (.pem). Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Device Enrollment Program.

4. Pokud chcete otevřít portál Programu registrace zařízení Apple (DEP), zvolte **Vytvořit token pro Program registrace zařízení Apple** a přihlaste se pomocí firemního Apple ID. Toto Apple ID můžete použít k obnovení tokenu DEP.

5.  Na [portálu společnosti Apple pro nasazení programů](https://deploy.apple.com) vyberte **Začínáme**. Otevře se **Program registrace zařízení**.

4. Na stránce pro **správu serverů** zvolte, že chcete **přidat server MDM**.

5. Pro **název serveru MDM**, zadejte *TestMDMServer* a klikněte na tlačítko **Další**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Není to název nebo adresu URL serveru pro Microsoft Intune.

6. Otevře se dialogové okno pro **přidání&lt;názvu serveru&gt;**, ve kterém se zobrazí výzva, abyste **nahráli svůj veřejný klíč**. Vyberte **Zvolit soubor**, abyste mohli nahrát soubor .pem, a pak zvolte **Další**.

6. Přejděte na **Deployment Programs** > **programu Device Enrollment Program** > **spravovat zařízení**.
7. V části **Choose Devices By**, zvolte **sériové číslo**. <!--ask Tiffany about this-->

8. V možnosti **Vybrat akci** vyberte **Přiřadit k serveru**, vyberte &lt;název_serveru&gt; zadaný pro Microsoft Intune a pak zvolte **OK**. Portál Apple přiřadí daná zařízení k serveru Intune, aby bylo možné je spravovat, a pak zobrazí zprávu o **dokončení přiřazení**.

   Na portálu Apple přejděte na **Programy nasazení** &gt; **Program registrace zařízení** &gt; **Zobrazit historii přiřazení**. Zobrazí se seznam zařízení s přiřazeným serverem MDM.

9. Pro budoucí použití v Intune na portálu Azure portal zadejte Apple ID použité k vytvoření tohoto tokenu.

    ![Snímek obrazovky s Apple ID použitým k vytvoření tokenu programu registrace a přechodem na token programu registrace](./media/device-enrollment-program-enroll-ios/image03.png)

10. V poli **Token Apple** přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Vytvořit**. 

## <a name="create-an-apple-enrollment-profile"></a>Vytvoření registračního profilu Apple
Po nainstalování tokenu můžete vytvořit registrační profil pro zařízení DEP. Registrační profil zařízení definuje nastavení, která se během registrace použijí pro skupinu zařízení.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace**.

2. Vyberte token, který jste právě nainstalovali, zvolte **profily** > **vytvořit profil**.

3. V části **vytvořit profil**, zadejte *TestDEPProfile* pro **název** a *testování DEP pro zařízení s Iosem* pro **popis** . Uživatelům se tyto údaje nezobrazí.

4. Pro **spřažení**, zvolte **zaregistrovat s přidružením uživatele**. Tato možnost je pro zařízení, která patří konkrétním uživatelům, které chcete používat aplikaci portál společnosti kvůli službám, jako je instalace aplikací.

5. Zvolte **ne** pod **ověřování pomocí portálu společnosti místo Pomocníka pro nastavení Apple**.

6. Zvolte **nastavení správy zařízení** a zvolte **ne** pod **pod dohledem**. Dozorovaná zařízení vám poskytnou víc možností správy, ale nebudeme je používat pro účely tohoto kurzu.

7. Zvolte **OK**.

8. Zvolte **pomocníka pro nastavení přizpůsobení** a zadejte *kurz oddělení* pro **název oddělení**. Tento řetězec představuje, co uživatelé uvidí, když se klepnutím na **o konfiguraci** při aktivaci zařízení.

9. V části **Telefon na oddělení**, zadejte telefonní číslo. Toto číslo se zobrazí, když uživatel klepnutím na **potřebujete pomoc s** tlačítko během aktivace.

10. Je možné **zobrazit** nebo **skrýt** různé obrazovky při aktivaci zařízení. Pro účely tohoto kurzu nastavte **hesla** k **zobrazit** a všechny ostatní na **skrýt**.

11. Zvolte **OK** > **Vytvořit**.

## <a name="sync-managed-devices"></a>Synchronizace spravovaných zařízení

Nyní můžete zobrazit, zařízení, která jsou přiřazeny k tomuto tokenu.

1. V Intune na portálu Azure portal zvolte **registrace zařízení** > **registrace Apple** > **tokeny programu registrace** > zvolte token v v seznamu > **zařízení** > **synchronizace**.

## <a name="assign-an-enrollment-profile-to-ios-devices"></a>Přiřadit profil registrace zařízení s Iosem

Než se můžou zařízení zaregistrovat, musíte přiřadit profil programu registrace.

1. V Intune na portálu Azure portal zvolte **registrace zařízení** > **registrace Apple** > **tokeny programu registrace** > zvolte token v seznamu.
2. Zvolte **Zařízení** > zvolte zařízení v seznamu > **Přiřadit profil**.
3. V části **Přiřadit profil** zvolte profil pro zařízení > **Přiřadit**.

## <a name="distribute-devices-to-users"></a>Distribuce zařízení uživatelům

Nastavili jste správu a synchronizaci mezi společností Apple a Intune a přiřadit profil, který umožní registraci zařízení DEP. Teď můžete zařízení rozdělit mezi uživatele. U zařízení s přidruženými uživateli je potřeba, aby měl každý uživatel přiřazenu licenci Intune.

## <a name="clean-up-resources"></a>Vyčištění prostředků

Pokud už nechcete používat zařízení Autopilot už, můžete je odstranit.

- Pokud jsou zařízení registrována v Intune, musíte je nejdřív [odstranit z portálu služby Azure Active Directory](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

<!--ask tiffany how to do this-->

## <a name="next-steps"></a>Další postup

Pro registraci zařízení s Iosem můžete najít další informace o dalších možnostech, které jsou k dispozici.

> [!div class="nextstepaction"]
> [Článek registrace DEP podrobné iOS](device-enrollment-program-enroll-ios.md)
