---
title: Kurz – použití Apple Business Manageru nebo Program registrace zařízení k registraci zařízení s iOS v Intune
titleSuffix: Microsoft Intune
description: V tomto kurzu nastavíte funkce registrace podnikových zařízení od společnosti Apple z ABM k registraci zařízení se systémem iOS v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Apple's corporate device enrollment features so that corporate devices can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: 83a9467065bb5c1d1cde2035df936541bb804ddc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503084"
---
# <a name="tutorial-use-apples-corporate-device-enrollment-features-in-apple-business-manager-abm-to-enroll-ios-devices-in-intune"></a>Kurz: použití funkcí registrace podnikových zařízení společnosti Apple v Apple Business Manageru (ABM) k registraci zařízení s iOS v Intune
Funkce registrace zařízení v Apple Business Manageru zjednodušují registraci zařízení. Intune podporuje také portál starší verze Program registrace zařízení (DEP) společnosti Apple, ale doporučujeme, abyste začali začít s Apple Business Managerem. Pomocí Microsoft Intune a registrace podnikových zařízení Apple se zařízení automaticky zaregistrují při prvním zapnutí zařízení uživatelem. Zařízení je proto možné dodávat mnoha uživatelům, aniž byste museli každé zařízení nastavovat samostatně. 

V tomto kurzu se naučíte:
> [!div class="checklist"]
> * Získání tokenu pro registraci zařízení Apple
> * Synchronizovat spravovaná zařízení s Intune
> * Vytvoření registračního profilu
> * Přiřazení registračního profilu k zařízením

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadované součásti
- Zařízení zakoupená v [Apple Business Manageru](https://business.apple.com) nebo [od společnosti Apple program registrace zařízení](http://deploy.apple.com)
- Nastavení [autority pro správu mobilních zařízení](../fundamentals/mdm-authority-set.md)
- Získání [certifikátu Apple MDM push Certificate](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-device-enrollment-token"></a>Získání tokenu pro registraci zařízení Apple
Před registrací zařízení se systémem iOS pomocí funkcí registrace společnosti Apple budete potřebovat soubor tokenu registrace zařízení Apple (. pem). Tento token umožňuje Intune synchronizovat informace o zařízeních Apple, která vaše společnost vlastní. Umožňuje také Intune odeslat společnosti Apple registrační profily a přiřazovat k těmto profilům zařízení.

Pomocí portálu ABM nebo DEP vytvoříte token pro zápis zařízení. Portály slouží také k přiřazování zařízení do Intune za účelem správy.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace** > **Přidat**.

2. Výběrem možnosti **Souhlasím** udělte Microsoftu oprávnění k odesílání informací o uživatelích a zařízeních do společnosti Apple.

   ![Snímek obrazovky s podoknem Token Programu registrace v pracovním prostoru Certifikáty Apple pro stažení veřejného klíče](./media/tutorial-use-device-enrollment-program-enroll-ios/add-enrollment-program-token-pane.png)

3. Vyberte **Stáhnout veřejný klíč** a stáhněte si a místně uložte soubor šifrovacího klíče (.pem). Soubor. pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu ABM nebo DEP.

4. Pokud chcete otevřít portál Programu registrace zařízení Apple (DEP), zvolte **Vytvořit token pro Program registrace zařízení Apple** a přihlaste se pomocí firemního Apple ID. Toto Apple ID můžete použít k obnovení tokenu DEP.

5. Na [portálu společnosti Apple pro nasazení programů](https://deploy.apple.com) vyberte **Začínáme**. Otevře se **Program registrace zařízení**. Váš proces může být mírně odlišný od následujících kroků v [Apple Business Manageru](https://business.apple.com).

4. Na stránce pro **správu serverů** zvolte, že chcete **přidat server MDM**.

5. Jako **název serveru MDM**zadejte *TestMDMServer* a pak klikněte na **Další**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Nejedná se o název nebo adresu URL serveru Microsoft Intune.

6. Otevře se dialogové okno pro **přidání&lt;názvu serveru&gt;** , ve kterém se zobrazí výzva, abyste **nahráli svůj veřejný klíč**. Vyberte **zvolit soubor...** abyste mohli nahrát soubor .pem, a pak zvolte **Další**.

6. Přejít do **programu pro nasazení** > **Program registrace zařízení** **Správa zařízení** > .
7. V části **zvolit zařízení podle**vyberte **sériové číslo**. <!--ask Tiffany about this-->

8. V možnosti **Vybrat akci** vyberte **Přiřadit k serveru**, vyberte &lt;název_serveru&gt; zadaný pro Microsoft Intune a pak zvolte **OK**. Portál Apple přiřadí daná zařízení k serveru Intune, aby bylo možné je spravovat, a pak zobrazí zprávu o **dokončení přiřazení**.

   Na portálu Apple přejděte na **Programy nasazení** &gt; **Program registrace zařízení** &gt; **Zobrazit historii přiřazení**. Zobrazí se seznam zařízení s přiřazeným serverem MDM.

9. Pro budoucí referenční informace v Intune v Azure Portal zadejte Apple ID použité k vytvoření tohoto tokenu.

    ![Snímek obrazovky s Apple ID použitým k vytvoření tokenu programu registrace a přechodem na token programu registrace](./media/tutorial-use-device-enrollment-program-enroll-ios/image03.png)

10. V poli **Token Apple** přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Vytvořit**. 

11. Pokud chcete použít značky oboru k omezení, kteří správci mají k tomuto tokenu přístup, vyberte obory.

## <a name="create-an-apple-enrollment-profile"></a>Vytvoření registračního profilu Apple
Teď, když máte nainstalovaný token, můžete vytvořit registrační profil pro zařízení s iOS vlastněná společností. Registrační profil zařízení definuje nastavení, která se během registrace použijí pro skupinu zařízení.

1. V Intune na portálu Azure Portal zvolte **Registrace zařízení** > **Registrace Apple** > **Tokeny programu registrace**.

2. Vyberte token, který jste právě nainstalovali, zvolte **profily** > **vytvořit profil**.

3. V části **vytvořit profil**zadejte *TestDEPProfile* pro **název** a *testování funkcí DEP pro zařízení s iOS* pro **Popis**. Uživatelům se tyto údaje nezobrazí.

4. V části **platforma**vyberte **iOS** .

5. Určete, jestli chcete, aby se vaše zařízení zaregistrovala s **přidružením uživatele**nebo bez. Přidružení uživatele je určené pro zařízení, která budou používat konkrétní uživatelé. Pokud budou uživatelé chtít použít Portál společnosti pro služby, jako je instalace aplikací, vyberte možnost **registrovat s přidružením uživatele**. Pokud vaši uživatelé nepotřebují Portál společnosti nebo chcete zařízení zřídit pro mnoho uživatelů, vyberte možnost **zaregistrovat bez přidružení uživatele**.

6. Pokud se rozhodnete zaregistrovat s přidružením uživatele, určete, jestli se má ověřit pomocí Portál společnosti nebo pomocníka s nastavením Apple. Pokud chcete použít Multi-Factor Authentication, umožníte uživatelům měnit hesla při prvním přihlášení, nebo vyzvat uživatele k resetování hesel po jejich vypršení platnosti během registrace, v části **ověřování pomocí portál společnosti místo instalace Apple vyberte Ano. Asistent**. Pokud jste obeznámeni s používáním základního ověřování protokolu HTTP od společnosti Apple prostřednictvím pomocníka s nastavením společnosti Apple, vyberte možnost **ne**.

7. Pokud se rozhodnete zaregistrovat s přidružením uživatele a ověřit pomocí Portál společnosti, určete, jestli chcete Portál společnosti nainstalovat pomocí programu Volume purchase program (VPP) společnosti Apple. Pokud nainstalujete Portál společnosti s tokenem VPP, uživatel nebude muset při registraci stáhnout Portál společnosti z App Storu a heslo. Zvolte **použít token:** v části **instalovat portál společnosti s VPP** vyberte token VPP, který má dostupné bezplatné licence portál společnosti. Pokud nechcete použít nástroj VPP k nasazení Portál společnosti, vyberte **Nepoužívat VPP** v části **instalovat portál společnosti pomocí programu VPP**. 

8. Pokud se rozhodnete zaregistrovat s přidružením uživatele, ověřit pomocí Portál společnosti a nainstalovat Portál společnosti pomocí programu VPP, rozhodněte se, jestli chcete spustit Portál společnosti v režimu jedné aplikace, dokud neproběhne ověřování. Toto nastavení umožňuje zajistit, že uživatel nebude mít přístup k jiným aplikacím, dokud nedokončí registraci v podnikové síti. Pokud chcete uživatele do tohoto toku omezit až do dokončení registrace, **v režimu spuštění portál společnosti v režimu jedné aplikace klikněte na** **tlačítko Ano** , dokud neproběhne ověřování. 

9. Vyberte **Nastavení správy zařízení** a v části **pod dohledem**vyberte **Ano** . Zařízení pod dohledem poskytují možnosti správy pro vaše podniková zařízení s iOS.

10. V části **zamčená registrace** vyberte **Ano** , aby uživatelé nemohli odebrat správu podnikového zařízení. 

11. Vyberte možnost v části **synchronizovat s počítači** a určete, jestli se zařízení s iOS budou moct synchronizovat s počítači.

12. Ve výchozím nastavení Apple pojmenuje zařízení s typem zařízení (např. iPad). Pokud chcete zadat jinou šablonu názvu, v části **použít šablonu názvu zařízení**vyberte **Ano** . Zadejte název, který chcete použít pro zařízení, kde řetězce *{{Serial}}* a *{{DeviceType}}* nahradí sériové číslo každého zařízení a typ zařízení. V opačném případě vyberte v části **použít šablonu názvu zařízení**možnost **ne** .

13. Vyberte **OK**.

14. Vyberte možnost **přizpůsobení pomocníka s nastavením** a jako **název oddělení**zadejte *oddělení kurzu* . Tento řetězec se uživatelům zobrazí při klepnutí na **konfiguraci** během aktivace zařízení.

15. V části **telefon do oddělení**zadejte telefonní číslo. Toto číslo se zobrazí, když uživatel při aktivaci klepne na tlačítko **Potřebuji Help** .

16. Během aktivace zařízení můžete **Zobrazit** nebo **Skrýt** nejrůznější obrazovky. Pro bezproblémové možnosti registrace nastavte všechny obrazovky, které chcete **Skrýt**.

17. Zvolte **OK** > **Vytvořit**.

## <a name="sync-managed-devices-to-intune"></a>Synchronizovat spravovaná zařízení s Intune

Až nastavíte token programu registrace s portálem ABM, ASM nebo DEP a přiřadíte zařízení do serveru MDM, můžete počkat, až se tato zařízení synchronizují se službou Intune, nebo ručně nasdílet synchronizaci. Bez ruční synchronizace může trvat až 24 hodin, než se v Azure Portal zobrazí.

1. V Intune v Azure Portal vyberte **registrace zařízení** >  registrace**Apple** > **tokeny programu registrace** > v seznamu > **zařízení** > **synchronizace**vyberte token.

## <a name="assign-an-enrollment-profile-to-ios-devices"></a>Přiřazení profilu registrace k zařízením s iOS

Než se můžou zařízení zaregistrovat, musíte přiřadit profil programu registrace. Tato zařízení se synchronizují s Intune od společnosti Apple a musí být přiřazená ke správnému tokenu MDM serveru na portálu ABM, ASM nebo DEP.

1. V Intune v Azure Portal klikněte na **registrace zařízení** >  registrace**Apple** > **tokeny programu registrace** > v seznamu vyberte svůj token.
2. Zvolte **Zařízení** > zvolte zařízení v seznamu > **Přiřadit profil**.
3. V části **Přiřadit profil** zvolte profil pro zařízení > **Přiřadit**.

## <a name="distribute-devices-to-users"></a>Distribuce zařízení uživatelům

Nastavili jste správu a synchronizaci mezi společností Apple a Intune a přiřadili jste profil, který umožní registraci zařízení DEP. Teď můžete zařízení rozdělit mezi uživatele. U zařízení s přidruženými uživateli je potřeba, aby měl každý uživatel přiřazenu licenci Intune.

## <a name="next-steps"></a>Další kroky

Můžete najít další informace o dalších možnostech, které jsou k dispozici pro registraci zařízení se systémem iOS.

> [!div class="nextstepaction"]
> [Podrobnější článek o registraci DEP pro iOS](device-enrollment-program-enroll-ios.md)

<!--commenting out because inaccurate>
## Clean up resources
<!--If you don't want to use iOS corporate enrolled devices anymore, you can delete them.>
<!--- If the devices are enrolled in Intune, you must first [delete them from the Azure Active Directory portal](../remote-actions/devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).>
