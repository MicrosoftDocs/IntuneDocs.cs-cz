---
title: Kurz – konfigurace Slack chcete Intune používat pro konfigurace EMM a aplikace
titleSuffix: Microsoft Intune
description: V tomto kurzu nakonfigurujete Slack chcete Intune používat pro konfigurace EMM a aplikace.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 06/11/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 55db37c5-0da7-4d9c-8027-525afb1c6349
Customer intent: As an Intune admin, I want to learn how to configure Slack to use Intune for EMM and app configuration..
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: da6c9b544d86c9c4b09c061c0f1500ed8612a047
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2019
ms.locfileid: "67530701"
---
# <a name="tutorial-configure-slack-to-use-intune-for-emm-and-app-configuration"></a>Kurz: Konfigurace Slack chcete Intune používat pro konfigurace EMM a aplikace

Slack je aplikace pro spolupráci, který vám pomůže s Microsoft Intune.   

V tomto kurzu provedete následující:
> [!div class="checklist"]
> - Nastavení Intune jako zprostředkovatel Enterprise Mobility Management (EMM) na vaší mřížkou Enterprise Slack. Budete moct omezit přístup k pracovním prostorům mřížky plánu na zařízení spravovaná pomocí Intune.
> - Vytvoření zásady Konfigurace aplikací ke správě Slack EMM aplikace v Iosu a Slack aplikace pro zařízení s pracovním profilem.
> - Vytvořte zásady dodržování předpisů nastavit podmínky Android zařízení v Intune a musí zařízení s Iosem splňovat, aby být považováno za dodržující předpisy.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadavky
Pro účely tohoto kurzu budete potřebovat testovacího tenanta s následujícími předplatnými:
- Azure Active Directory Premium ([bezplatná zkušební verze](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
- Předplatné služby Intune ([bezplatnou zkušební verzi](free-trial-sign-up.md))

Budete také potřebovat [Slack Enterprise mřížky](https://get.slack.help/hc/articles/360004150931-What-is-Slack-Enterprise-Grid-) plánu.

## <a name="configure-your-slack-enterprise-grid-plan"></a>Konfigurace plánu Enterprise mřížky Slack
Zapnout EMM pro váš plán Enterprise mřížky Slack podle [pokyny pro Slack](https://get.slack.help/hc/articles/115002579426-Enable-Enterprise-Mobility-Management-for-your-org#step-2:-turn-on-emm) a [připojení služby Azure Active Directory](https://docs.microsoft.com/azure/active-directory/saas-apps/slack-tutorial) jako plánu mřížky zprostředkovatele identity (IDP).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune
Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) jako globální správce nebo správce služby Intune. Pokud jste vytvořili zkušební předplatné Intune, účet, z něhož jste toto předplatné vytvořili, je globálním správcem.

## <a name="set-up-slack-for-emm-on-ios-devices"></a>Nastavení Slack pro EMM na zařízeních s Iosem
Do svého tenanta Intune přidat aplikace pro iOS Slack pro EMM a vytvořte zásady Konfigurace aplikací iOS uživatelům vaší organizace pro přístup k Slack pomocí Intune jako zprostředkovatel EMM.

### <a name="add-slack-for-emm-to-intune"></a>Do Intune přidat Slack EMM
Přidání Slack pro EMM jako spravované iOS aplikace v Intune a přiřazení uživatelé Slack. Aplikace jsou specifické pro platformu, takže budete muset přidat samostatné aplikace Intune pro Slack uživatele na zařízeních s Androidem.
1. V Intune, vyberte **klientské aplikace** > **aplikace** > **přidat**.
2. V části Typ aplikace vyberte **Store app - iOS**.
3. Vyberte **Hledat v App Storu**. Zadejte hledaný termín "Slack pro EMM" a vyberte aplikaci.
4. Vyberte **informace o aplikaci** a konfigurovat všechny změny podle svých potřeb.
5. Vyberte **Přidat**.
6. Na panelu hledání zadejte "Slack pro EMM" a vyberte aplikaci, kterou jste právě přidali.
7. Spravovat, vyberte **přiřazení**.
8. Vyberte **přidat skupinu**. V závislosti na tom, kdo jste se rozhodli vliv, když jste zapnuli EMM pro Slack, v části **typ přiřazení** možná budete chtít vybrat:
    -  **K dispozici zaregistrovaným zařízením** Pokud jste zvolili "Všechny členy (včetně hostů)" nebo
    -  **K dispozici s registrací i bez** Pokud jste zvolili "Všechny členy (s výjimkou Hosté)" nebo "Volitelné".
9. Vyberte **zahrnutých skupin** a v části vytvořit tuto aplikaci k dispozici pro všechny uživatele vyberte **Ano**.
10. Klikněte na tlačítko **OK**a potom klikněte na tlačítko **OK** znovu.
11. Klikněte na **Uložit**.

### <a name="add-an-app-configuration-policy-for-slack-for-emm"></a>Přidat zásady Konfigurace aplikací pro Slack pro EMM
Přidáte zásady Konfigurace aplikací pro Slack pro EMM iOS. Zásady Konfigurace aplikací pro spravovaná zařízení jsou specifické pro platformu, takže budete muset přidat samostatné zásady pro Slack uživatele na zařízeních s Androidem.
1. V Intune, vyberte **klientské aplikace** > **zásady Konfigurace aplikací** > **přidat**.
2. Do pole Název zadejte test zásady Konfigurace aplikace Slack.
3. V části Typ registrace zařízení, vyberte **spravovaných zařízeních**.
4. V části platformy, vyberte **iOS**.
5. Vyberte **přidružené aplikace**.
6. Na panelu hledání zadejte "Slack pro EMM" a vyberte aplikaci.
7. Klikněte na tlačítko **OK**a pak vyberte **nastavení konfigurace**. 
    -   Informace o konfiguraci klíče a jejich hodnoty, najdete v dokumentaci na kartě "Technické" [webové stránky na Slack AppConfig](https://www.appconfig.org/company/slack/).
8. Vyberte **OK**a pak vyberte **přidat**.
9. Na panelu hledání zadejte "test zásady Konfigurace aplikace Slack" a vyberte zásadu, kterou jste právě přidali.
10. Spravovat, vyberte **přiřazení**.
11. V části přiřadit, vyberte **všichni uživatelé a všechna zařízení**.
12. Klikněte na **Uložit**.

### <a name="optional-create-an-ios-device-compliance-policy"></a>(Volitelné) Vytvoření zásad dodržování předpisů pro zařízení iOS
Nastavte zásadu dodržování předpisů zařízením s iOSem v Intune a nastavte podmínky, které zařízení musí splnit, než bude považováno za vyhovující. Pro účely tohoto kurzu vytvoříme zásadu dodržování předpisů pro zařízení s iOSem. Zásady dodržování předpisů jsou specifické pro platformu, takže budete muset vytvořit samostatné zásady pro Slack uživatele na zařízeních s Androidem.
1. V Intune vyberte **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**.
2. Do pole Název zadejte "testovací zásady dodržování předpisů iOS".
3. Do pole Popis zadejte "testovací zásady dodržování předpisů iOS".
4. V části platformy, vyberte **iOS**.
5. Vyberte **Stav zařízení**. U zařízení s Jailbreakem, vyberte **bloku**a pak vyberte **OK**.
6. Vyberte **zabezpečení systému** a zadejte nastavení hesla. Pro účely tohoto kurzu vyberte následující doporučená nastavení:
    -   Pro vyžadovat heslo k odemknutí mobilních zařízení, vyberte **vyžadují**.
    -   Jednoduchá hesla, vyberte **bloku**.
    -   Minimální délka hesla zadejte 4.
    -   Vyžadovaný typ hesla, zvolte **alfanumerické**.
    -   Maximální počet minut po uzamčení obrazovky, po před vyžádáním hesla, zvolte možnost **okamžitě**.
    -   Pro konec platnosti hesla (dny), zadejte 41.
    -   Počet předchozích hesel, která znovu použít, zadejte hodnotu 5.
7. Klikněte na tlačítko **OK**a pak vyberte **OK** znovu.
8. Klikněte na možnost **Vytvořit**.

## <a name="set-up-slack-on-android-work-profile-devices"></a>Nastavení na zařízení s pracovním profilem Slack
Přidat do svého tenanta Intune aplikaci Slack spravovaný obchod Google Play a vytvořte zásady Konfigurace aplikací umožňují vaše organizace uživatelům zařízení s Androidem přístup s Intune jako zprostředkovatel EMM Slack.

### <a name="add-slack-to-intune"></a>Do Intune přidat Slack
Přidáte Slack spravované Google play aplikace v Intune a přiřazení Slack uživatelů. Aplikace jsou specifické pro platformu, takže budete muset přidat samostatné aplikace Intune pro Slack uživatele na zařízeních s Iosem.
1. V Intune, vyberte **klientské aplikace** > **aplikace** > **přidat**.
2. V části Typ aplikace vyberte **app Store – spravovaný obchod Google Play**.
3. Vyberte **spravovaného obchodu Google Play – schválení**. Zadejte hledaný termín "Slack pro EMM" a vyberte aplikaci.
4. Vyberte **schválit**.
5. Na panelu hledání zadejte "Slack" a vyberte aplikaci, kterou jste právě přidali.
6. Spravovat, vyberte **přiřazení**.
7. Vyberte **přidat skupinu**. V závislosti na tom, kdo jste se rozhodli vliv, když jste zapnuli EMM pro Slack, v části **typ přiřazení** možná budete chtít vybrat:
    -   **K dispozici zaregistrovaným zařízením** Pokud jste zvolili "Všechny členy (včetně hostů)" nebo
    -   **K dispozici s registrací i bez** Pokud jste zvolili "Všechny členy (s výjimkou Hosté)" nebo "Volitelné".
8. Vyberte zahrnuté skupiny a v části vytvořit tuto aplikaci k dispozici pro všechny uživatele vyberte **Ano**.
9. Klikněte na tlačítko **OK**a potom klikněte na tlačítko **OK** znovu.
10. Klikněte na **Uložit**.

### <a name="add-an-app-configuration-policy-for-slack"></a>Přidat zásady Konfigurace aplikací pro Slack
Přidáte zásady Konfigurace aplikací pro Slack. Zásady Konfigurace aplikací pro spravovaná zařízení jsou specifické pro platformu, takže budete muset přidat samostatné zásady pro Slack uživatele na zařízeních s Iosem.
1. V Intune, vyberte **klientské aplikace** > **zásady Konfigurace aplikací** > **přidat**.
2. Do pole Název zadejte test zásady Konfigurace aplikace Slack.
3. V části Typ registrace zařízení, vyberte **spravovaných zařízeních**.
4. V části platformy, vyberte **Android**.
5. Vyberte **přidružené aplikace**.
6. Na panelu hledání zadejte "Slack" a vyberte aplikaci.
7. Vyberte **OK**a pak vyberte **nastavení konfigurace**.
    -   Informace o konfiguraci klíče a jejich hodnoty, najdete v dokumentaci na kartě "Technické" [webové stránky na Slack AppConfig](https://www.appconfig.org/company/slack/).
8. Klikněte na tlačítko **OK**a pak vyberte **přidat**.
9. Na panelu hledání zadejte "test zásady Konfigurace aplikace Slack" a vyberte zásadu, kterou jste právě přidali.
10. Spravovat, vyberte **přiřazení**.
11. V části přiřadit, vyberte **všichni uživatelé a všechna zařízení**.
12. Klikněte na **Uložit**.

### <a name="optional-create-an-android-device-compliance-policy"></a>(Volitelné) Vytvoření zásad dodržování předpisů zařízení s Androidem
Nastavte zásadu dodržování předpisů zařízením s iOSem v Intune a nastavte podmínky, které zařízení musí splnit, než bude považováno za vyhovující. V tomto kurzu vytvoříme zásadu dodržování předpisů pro zařízení s Androidem. Zásady dodržování předpisů jsou specifické pro platformu, takže budete muset vytvořit samostatné zásady pro Slack uživatele na zařízeních s Iosem.
1. V Intune vyberte **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**.
2. Do pole Název zadejte "testovací zásady dodržování předpisů pro Android".
3. Do pole Popis zadejte "testovací zásady dodržování předpisů pro Android".
4. V části platformy, vyberte **Androidu Enterprise**.
5. V části Typ profilu vyberte **pracovního profilu**.
6. Vyberte **Stav zařízení**. Vedle zařízením s Rootem, vyberte **bloku**a pak vyberte **OK**.
7. Vyberte **zabezpečení systému** a zadejte **nastavení hesla**. Pro účely tohoto kurzu vyberte následující doporučená nastavení:
    -   Pro vyžadovat heslo k odemknutí mobilních zařízení, vyberte **vyžadují**.
    -   Vyžadovaný typ hesla, vyberte **aspoň alfanumerické**.
    -   Minimální délka hesla zadejte 4.
    -   Maximální počet minut po uzamčení obrazovky, po před vyžádáním hesla, zvolte možnost **15 minut**.
    -   Pro konec platnosti hesla (dny), zadejte 41.
    -   Počet předchozích hesel, která znovu použít, zadejte hodnotu 5.
8. Klikněte na tlačítko **OK**a potom klikněte na tlačítko **OK** znovu.
9. Klikněte na možnost **Vytvořit**.

## <a name="launch-slack"></a>Spuštění Slack

Se zásadami, kterou jste právě vytvořili, všechny iOS nebo Android se pracovní profil zařízení, které se pokusí přihlásit k jednomu z vašich pracovních prostorů muset být zaregistrovaná v Intune. K otestování tohoto scénáře, zkuste Slack pro EMM na zařízení s Iosem zaregistrovaná v Intune nebo spouštění Slack na zařízení zaregistrovaná v Intune s pracovním profilu. 

## <a name="next-steps"></a>Další postup

V tomto kurzu:
- Nastavení Intune jako zprostředkovatel Enterprise Mobility Management (EMM) na vaší mřížkou Enterprise Slack. 
- Můžete vytvořit zásady Konfigurace aplikací ke správě Slack EMM aplikace v Iosu a Slack aplikace pro zařízení s pracovním profilem.
- Vytvoření zásady dodržování předpisů nastavit podmínky Android zařízení v Intune a musí zařízení s Iosem splňovat, aby být považováno za dodržující předpisy.

Další informace o zásadách konfigurace aplikací najdete v tématu [zásad Konfigurace aplikací pro Microsoft Intune](app-configuration-policies-overview.md). Další informace o vytváření zásad dodržování předpisů zařízení, najdete v článku [nastavování pravidel pro zařízení a povolení přístupu k prostředkům ve vaší organizaci pomocí Intune](device-compliance-get-started.md).