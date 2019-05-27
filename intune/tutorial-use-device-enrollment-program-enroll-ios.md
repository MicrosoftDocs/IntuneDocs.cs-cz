---
title: Kurz – použití Apple obchodní ředitel nebo programu Device Enrollment Program registrace zařízení s Iosem v Intune
titleSuffix: Microsoft Intune
description: V tomto kurzu které nastavíte funkcí pro registraci firemních zařízení společnosti Apple z ABM registrace zařízení s Iosem v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Apple's corporate device enrollment features so that corporate devices can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: faceee883194dbbdcec83f282806035ffc0432d1
ms.sourcegitcommit: 0f771585d3556c0af14500428d5c4c13c89b9b05
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66174179"
---
# <a name="tutorial-use-apples-corporate-device-enrollment-features-in-apple-business-manager-abm-to-enroll-ios-devices-in-intune"></a>Kurz: Použití funkce registrace podnikového zařízení společnosti Apple v Apple obchodní správce (ABM) k registraci zařízení s Iosem v Intune
Možnosti registrace zařízení v Apple obchodní ředitel usnadňuje registraci zařízení. Intune také podporuje starší portál programu registrace zařízení (DEP) společnosti Apple, ale doporučujeme vám začít pracovat s Apple manažera. S Microsoft Intune a Apple registrace podnikového zařízení jsou zařízení zaregistrovaná automaticky bezpečně okamžiku, kdy uživatel zařízení zapne. Proto můžete zaslat zařízení mnoha uživatelům bez nutnosti nastavit každé zařízení zvlášť. 

V tomto kurzu se naučíte:
> [!div class="checklist"]
> * Registrace zařízení společnosti Apple získat token
> * Synchronizace spravovaných zařízení do Intune
> * Vytvoření profilu registrace
> * Přiřadit profil registrace zařízení

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadavky
- Zařízení zakoupená v [Apple obchodní ředitel](https://business.apple.com) nebo [společnosti Apple Device Enrollment Program](http://deploy.apple.com)
- Nastavte [autoritu správy mobilních zařízení](mdm-authority-set.md)
- Získat [certifikátu Apple MDM Push certificate](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-device-enrollment-token"></a>Registrace zařízení společnosti Apple získat token
Před registrací zařízení s Iosem s funkcemi podnikové registrace od Applu, budete potřebovat soubor registrace zařízení společnosti Apple token (.pem). Tento token umožňuje Intune synchronizovat informace o zařízení Apple, které vaše společnost vlastní. Umožňuje také Intune odeslat společnosti Apple registrační profily a přiřazovat k těmto profilům zařízení.

Použití portálu ABM nebo zabránění spuštění dat k vytvoření tokenu registrace zařízení. Na portálech použijete také k přiřazení zařízení do Intune pro správu.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace** > **Přidat**.

2. Výběrem možnosti **Souhlasím** udělte Microsoftu oprávnění k odesílání informací o uživatelích a zařízeních do společnosti Apple.

   ![Snímek obrazovky s podoknem Token Programu registrace v pracovním prostoru Certifikáty Apple pro stažení veřejného klíče](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Vyberte **Stáhnout veřejný klíč** a stáhněte si a místně uložte soubor šifrovacího klíče (.pem). Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu ABM nebo DEP.

4. Pokud chcete otevřít portál Programu registrace zařízení Apple (DEP), zvolte **Vytvořit token pro Program registrace zařízení Apple** a přihlaste se pomocí firemního Apple ID. Toto Apple ID můžete použít k obnovení tokenu DEP.

5.  Na [portálu společnosti Apple pro nasazení programů](https://deploy.apple.com) vyberte **Začínáme**. Otevře se **Program registrace zařízení**. Může být mírně liší od následující kroky v procesu [Apple obchodní ředitel](https://business.apple.com).

4. Na stránce pro **správu serverů** zvolte, že chcete **přidat server MDM**.

5. Pro **název serveru MDM**, zadejte *TestMDMServer* a klikněte na tlačítko **Další**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Není to název nebo adresu URL serveru pro Microsoft Intune.

6. Otevře se dialogové okno pro **přidání&lt;názvu serveru&gt;** , ve kterém se zobrazí výzva, abyste **nahráli svůj veřejný klíč**. Vyberte **zvolit soubor...** abyste mohli nahrát soubor .pem, a pak zvolte **Další**.

6. Přejděte na **Deployment Programs** > **programu Device Enrollment Program** > **spravovat zařízení**.
7. V části **Choose Devices By**, zvolte **sériové číslo**. <!--ask Tiffany about this-->

8. V možnosti **Vybrat akci** vyberte **Přiřadit k serveru**, vyberte &lt;název_serveru&gt; zadaný pro Microsoft Intune a pak zvolte **OK**. Portál Apple přiřadí daná zařízení k serveru Intune, aby bylo možné je spravovat, a pak zobrazí zprávu o **dokončení přiřazení**.

   Na portálu Apple přejděte na **Programy nasazení** &gt; **Program registrace zařízení** &gt; **Zobrazit historii přiřazení**. Zobrazí se seznam zařízení s přiřazeným serverem MDM.

9. Pro budoucí použití v Intune na portálu Azure portal zadejte Apple ID použité k vytvoření tohoto tokenu.

    ![Snímek obrazovky s Apple ID použitým k vytvoření tokenu programu registrace a přechodem na token programu registrace](./media/device-enrollment-program-enroll-ios/image03.png)

10. V poli **Token Apple** přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Vytvořit**. 

11. Pokud chcete použít k omezení, které správci mají přístup k tomuto tokenu značky oboru, vyberte obory.

## <a name="create-an-apple-enrollment-profile"></a>Vytvoření registračního profilu Apple
Teď, když jste nainstalovali svůj token, můžete vytvořit registrační profil pro zařízení s Iosem vlastněných společností. Registrační profil zařízení definuje nastavení, která se během registrace použijí pro skupinu zařízení.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace**.

2. Vyberte token, který jste právě nainstalovali, zvolte **profily** > **vytvořit profil**.

3. V části **vytvořit profil**, zadejte *TestDEPProfile* pro **název** a *testování DEP pro zařízení s Iosem* pro **popis** . Uživatelům se tyto údaje nezobrazí.

4. Zvolte **iOS** pod **platformy**.

5. Určete, jestli chcete zařízení zaregistrovat i bez **spřažení**. Přidružení uživatele je určen pro zařízení, která se použije konkrétní uživatelé. Pokud budou vaši uživatelé chtějí používat portál společnosti pro služby, jako je instalace aplikací, zvolte **zaregistrovat s přidružením uživatele**. Pokud vaši uživatelé nemusí aplikaci portál společnosti nebo které chcete zřídit zařízení pro mnoho uživatelů, zvolte **zaregistrovat bez přidružení uživatele**.

6. Pokud jste se rozhodli zaregistrovat s přidružením uživatele, zjistěte, jestli chcete k ověřování pomocí aplikace portál společnosti nebo nastavením přístupu společnosti Apple. Pokud chcete používat ověřování Multi-Factor Authentication, umožnit uživatelům měnit hesla po prvním přihlášení nebo vyzvat uživatele k resetování hesel vypršela platnost během registrace, zvolte **Ano** pod **ověření Firemní portál místo Pomocníka pro nastavení Apple**. Pokud umíte používat Apple uživatele poskytované prostřednictvím Apple Pomocník základní ověřování protokolu HTTP, zvolte **ne**.

7. Pokud jste se rozhodli registrovat s přidružením uživatele a ověření pomocí portálu společnosti, určete, jestli chcete nainstalovat aplikaci portál společnosti s Apple Volume Purchase Program (VPP). Pokud nainstalujete aplikaci portál společnosti se VPP token, uživatel nebude mít k zadání Apple ID a hesla, stáhnout aplikaci portál společnosti z app storu během registrace. Zvolte **použijte Token:** pod **nainstalovat portál společnosti s VPP** vyberte token VPP, který má bezplatné licence k dispozici aplikace portál společnosti. Pokud už nechcete používat VPP nasadit portál společnosti, zvolte **nepoužívejte VPP** pod **nainstalovat portál společnosti s VPP**. 

8. Pokud jste se rozhodli zaregistrovat s přidružením uživatele, ověřování pomocí portálu společnosti a portál společnosti nainstalovat pomocí VPP, rozhodněte, jestli chcete spustit aplikaci portál společnosti v režimu jedné aplikace do ověřování. Toto nastavení umožňuje zajistit, aby že uživatel nebude mít přístup do jiných aplikací, dokud se nedokončí registrace podnikového. Pokud chcete zabránit uživatelům se tohoto toku až do dokončení registrace, zvolte **Ano** pod **spustit portál společnosti v režimu jedné aplikace do ověřování**. 

9. Zvolte **nastavení správy zařízení** a zvolte **Ano** pod **pod dohledem**. Dozorovaná zařízení získáte většinu možností správy pro vaše zařízení s Iosem podnikové.

10. Zvolte **Ano** pod **registrace uzamčeného** zajistit uživatelům nelze odebrat správu firemních zařízení. 

11. Vyberte možnosti v části **synchronizovat s počítači** k určení, pokud zařízení s iOS bude moct synchronizovat s počítači.

12. Ve výchozím nastavení Apple názvy zařízení s typem zařízení (například iPad). Pokud chcete zadat jiný název šablony, zvolte **Ano** pod **použít šablonu název zařízení**. Zadejte název, který chcete použít u zařízení, kde řetězce *{{SÉRIOVÉ}}* a *{{DEVICETYPE}}* nahradí každé zařízení sériové číslo a typ zařízení. Jinak klikněte na tlačítko **ne** pod **použít šablonu název zařízení**.

13. Zvolte **OK**.

14. Zvolte **pomocníka pro nastavení přizpůsobení** a zadejte *kurz oddělení* pro **název oddělení**. Tento řetězec představuje, co uživatelé uvidí, když se klepnutím na **o konfiguraci** při aktivaci zařízení.

15. V části **Telefon na oddělení**, zadejte telefonní číslo. Toto číslo se zobrazí, když uživatel klepnutím na **potřebujete pomoc s** tlačítko během aktivace.

16. Je možné **zobrazit** nebo **skrýt** různé obrazovky při aktivaci zařízení. Pro bezproblémové prostředí pro registraci, nastavte na všech obrazovkách **skrýt**.

17. Zvolte **OK** > **Vytvořit**.

## <a name="sync-managed-devices-to-intune"></a>Synchronizace spravovaných zařízení do Intune

Po nastavení tokenu programu registrace pomocí portálu DEP, ABM či ASM a přiřazení zařízení existuje serveru MDM, můžete čekat pro tato zařízení synchronizovat se službou Intune nebo ručně vložit synchronizaci. Bez ruční synchronizace zařízení může trvat až 24 hodin se zobrazí na webu Azure Portal.

1. V Intune na portálu Azure portal zvolte **registrace zařízení** > **registrace Apple** > **tokeny programu registrace** > zvolte token v v seznamu > **zařízení** > **synchronizace**.

## <a name="assign-an-enrollment-profile-to-ios-devices"></a>Přiřadit profil registrace zařízení s Iosem

Než se můžou zařízení zaregistrovat, musíte přiřadit profil programu registrace. Tato zařízení se synchronizují do Intune od společnosti Apple a správné token MDM serveru na portálu programu DEP, ABM či ASM se musí přiřadit.

1. V Intune na portálu Azure portal zvolte **registrace zařízení** > **registrace Apple** > **tokeny programu registrace** > zvolte token v seznamu.
2. Zvolte **Zařízení** > zvolte zařízení v seznamu > **Přiřadit profil**.
3. V části **Přiřadit profil** zvolte profil pro zařízení > **Přiřadit**.

## <a name="distribute-devices-to-users"></a>Distribuce zařízení uživatelům

Nastavili jste správu a synchronizaci mezi společností Apple a Intune a přiřadit profil, který umožní registraci zařízení DEP. Teď můžete zařízení rozdělit mezi uživatele. U zařízení s přidruženými uživateli je potřeba, aby měl každý uživatel přiřazenu licenci Intune.

## <a name="next-steps"></a>Další postup

Pro registraci zařízení s Iosem můžete najít další informace o dalších možnostech, které jsou k dispozici.

> [!div class="nextstepaction"]
> [Článek registrace DEP podrobné iOS](device-enrollment-program-enroll-ios.md)

<!--commenting out because inaccurate>
## Clean up resources
<!--If you don't want to use iOS corporate enrolled devices anymore, you can delete them.>
<!--- If the devices are enrolled in Intune, you must first [delete them from the Azure Active Directory portal](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).>
