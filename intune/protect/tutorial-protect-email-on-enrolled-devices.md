---
title: 'Kurz: Ochrana e-mailu Exchange Online na zařízeních spravovaných v Intune'
titleSuffix: Microsoft Intune
description: Naučte se zabezpečit Exchange Online pomocí zásad dodržování předpisů Intune pro iOS a podmíněného přístupu Azure AD, abyste mohli vyžadovat spravovaná zařízení a aplikaci Outlook.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/26/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a2d6f14b4b3e1e981cce789664203b74523b2474
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732414"
---
# <a name="tutorial-protect-exchange-online-email-on-managed-devices"></a>Kurz: Ochrana e-mailu Exchange Online na spravovaných zařízeních
Přečtěte si, jak používat zásady dodržování předpisů pro zařízení s podmíněným přístupem, abyste se ujistili, že zařízení se systémem iOS mají přístup k e-mailu Exchange Online jenom v případě, že jsou spravovaná pomocí Intune 

V tomto kurzu se naučíte: 
> [!div class="checklist"]
> * Vytvořit zásadu dodržování předpisů zařízením s iOSem v Intune. Tato zásada nastaví podmínky, které zařízení musí splnit, než bude považováno za vyhovující.
> * Vytvořte zásadu podmíněného přístupu Azure Active Directory (Azure AD), která vyžaduje, aby se zařízení s iOS zaregistrovala do Intune, dodržovala zásady Intune a používala schválenou mobilní aplikaci Outlooku k přístupu k e-mailu Exchange Online.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadované součásti
- Pro účely tohoto kurzu budete potřebovat testovacího tenanta s následujícími předplatnými:
  - Azure Active Directory Premium ([bezplatná zkušební verze](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
  - Předplatné Office 365 Business, které zahrnuje Exchange ([bezplatná zkušební verze](https://go.microsoft.com/fwlink/p/?LinkID=510938))
- Než začnete, vytvořte si testovací profil pro zařízení s iOSem podle postupu uvedeného v článku [Rychlý start: Vytvoření e-mailového profilu zařízení pro iOS](../configuration/quickstart-email-profile.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo správce služby Intune. Pokud jste vytvořili zkušební předplatné Intune, účet, z něhož jste toto předplatné vytvořili, je globálním správcem.

## <a name="create-the-ios-device-compliance-policy"></a>Vytvoření zásady dodržování předpisů zařízením s iOSem
Nastavte zásadu dodržování předpisů zařízením s iOSem v Intune a nastavte podmínky, které zařízení musí splnit, než bude považováno za vyhovující. Pro účely tohoto kurzu vytvoříme zásadu dodržování předpisů pro zařízení s iOSem. Zásady dodržování předpisů jsou pro jednotlivé platformy specifické, a proto potřebujete samostatnou zásadu dodržování předpisů pro každou platformu zařízení, kterou chcete vyhodnotit.

1. V Intune vyberte **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**.
2. Jako **Název** zadejte **Test dodržování předpisů zařízením s iOSem**. 
3. Jako **Popis** zadejte **Test dodržování předpisů zařízením s iOSem**.
4. U možnosti **Platforma** vyberte **iOS**. 
5. Vyberte **Nastavení** > **E-mail**. 
     
    1. Vedle možnosti **Vyžadovat, aby mobilní zařízení měla spravovaný e-mailový profil** vyberte **Vyžadovat**.
    2. Vyberte **OK**.

    ![Nastavení zásad dodržování předpisů e-mailem, které vyžadují spravovaný e-mailový profil](./media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-email.png)
    
6. Vyberte **Stav zařízení**. Vedle možnosti **Zařízení s jailbreakem** vyberte **Blokovat** a potom vyberte **OK**.
7. Vyberte **Zabezpečení systému** a zadejte nastavení **hesla**. Pro účely tohoto kurzu vyberte následující doporučená nastavení:
     
    - U možnosti **Vyžadovat heslo k odemknutí mobilních zařízení** vyberte **Vyžadovat**.
    - U možnosti **Jednoduchá hesla** vyberte **Blokovat**.
    - U možnosti **Minimální délka hesla** zadejte **4**.
    - Jako **Požadovaný typ hesla** zvolte **Alfanumerické**.
    - U možnosti **Maximální počet minut po uzamčení obrazovky, po kterém bude nutné zadat heslo**, zvolte **Okamžitě**.
    - U možnosti **Konec platnosti hesla (dny)** zadejte **41**.
    - U možnosti **Počet předchozích hesel, která se nesmí použít znovu** zadejte **5**.
 
    ![Nastavení hesla pro zásady dodržování předpisů e-mailem](./media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-system-security.png)

8. Vyberte **OK** a potom znovu vyberte **OK**.
9. Vyberte **Vytvořit**.

## <a name="create-the-conditional-access-policy"></a>Vytvoření zásady podmíněného přístupu
Nyní vytvoříme zásadu podmíněného přístupu, která vyžaduje, aby všechny platformy zařízení registrovaly do Intune a dodržovaly zásady dodržování předpisů Intune předtím, než budou mít přístup k Exchangi Online. Pro přístup k e-mailu budeme také vyžadovat aplikaci Outlook. Zásady podmíněného přístupu se dají nakonfigurovat buď na portálu Azure AD, nebo na portálu Intune. Vzhledem k tomu, že se už nacházíme na portálu Intune, vytvoříme zásadu zde.
1. V Intune vyberte zásady **podmíněného přístupu**@no__t-1  > **nové zásady**.
1. Jako **Název** zadejte **Testovací zásada pro e-mail Office 365**. 
3. V části **Přiřazení** vyberte **Uživatelé a skupiny**. Na kartě **Zahrnout** vyberte **Všichni uživatelé** a vyberte **Hotovo**.

4. V části **Přiřazení** vyberte **Cloudové aplikace**. Protože chceme chránit e-mail Office 365 se službou Exchange Online, vybereme ho následujícím postupem:
     
    1. Na kartě **Zahrnout** zvolte **Vybrat aplikace**.
    2. Zvolte **Vybrat**. 
    3. V seznamu aplikací vyberte **Office 365 se službou Exchange Online** a potom zvolte **Vybrat**. 
    4. Vyberte **Hotovo**.
  
    ![Výběr aplikace Office 365 se službou Exchange Online](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-apps.png)

5. V části **Přiřazení** vyberte **Podmínky** > **Platformy zařízení**.
     
    1. V části **Konfigurovat** vyberte **Ano**.
    2. Na kartě **Zahrnout** vyberte **libovolné zařízení**a potom vyberte **Hotovo**. 
    3. Znovu vyberte **Hotovo**.
   
    ![Výběr aplikace Office 365 se službou Exchange Online](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-device-platforms.png)

6. V části **Přiřazení** vyberte **Podmínky** > **Klientské aplikace**.
     
    1. V části **Konfigurovat** vyberte **Ano**.
    2. Pro účely tohoto kurzu vyberte **Mobilní aplikace a desktopoví klienti** a **Klienti moderního ověřování** (týká se aplikací, jako jsou Outlook pro iOS a Outlook pro Android). Zaškrtnutí všech ostatních políček zrušte.
    3. Vyberte **Hotovo** a potom znovu vyberte **Hotovo**.
    
    ![Výběr aplikace Office 365 se službou Exchange Online](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-client-apps.png)

7. V části **Ovládací prvky přístupu** zvolte **Udělení**. 
     
    1. V podokně **Udělení** vyberte **Udělit přístup**.
    2. Vyberte **Vyžadovat, aby zařízení bylo označené jako vyhovující**. 
    3. Vyberte **Vyžaduje se klientem schválená aplikace**.
    4. V části **Pro více ovládacích prvků** vyberte **Vyžadovat všechny vybrané ovládací prvky**. Toto nastavení zajistí, že se při přístupu zařízení k e-mailu oba vybrané požadavky vynutí.
    5. Zvolte **Vybrat**.
     
    ![Výběr aplikace Office 365 se službou Exchange Online](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-grant-access.png)

8. V části **Povolit zásadu** vyberte **Zapnuto**.
     
    ![Výběr aplikace Office 365 se službou Exchange Online](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-enable-policy.png)

9. Vyberte **Vytvořit**.

## <a name="try-it-out"></a>Vyzkoušejte si to
S vytvořenými zásadami se budou všechna zařízení s iOSem, která se pokusí o přihlášení k e-mailu Office 365, muset zaregistrovat v Intune a používat mobilní aplikaci Outlook pro iOS. Pokud chcete tento scénář otestovat na zařízení s iOSem, zkuste se přihlásit k Exchangi Online pomocí přihlašovacích údajů uživatele v testovacím tenantovi. Zobrazí se výzva k registraci zařízení a k instalaci mobilní aplikace Outlook.
1. Pokud si chcete zásady otestovat na iPhonu, přejděte na **Nastavení** > **Hesla a účty** > **Přidat účet** > **Exchange**.
2. Zadejte e-mailovou adresu uživatele v testovacím tenantovi a stiskněte **Další**.
3. Stiskněte **Přihlásit se**.
4. Zadejte heslo testovacího uživatele a stiskněte **Přihlásit se**.
5. Zobrazí se zpráva, že zařízení musí být spravováno, aby mohlo prostředek použít, spolu s možností registrace. 

## <a name="clean-up-resources"></a>Vyčištění prostředků
Pokud už testovací zásady nepotřebujete, můžete je odebrat.
1. Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo správce služby Intune.
2. Vyberte **Dodržování předpisů zařízením** > **Zásady**.
3. V seznamu **Název zásady** vyberte u testovací zásady místní nabídku ( **...** ) a potom vyberte **Odstranit**. Vyberte **OK**. Tím akci potvrdíte.
4. Vyberte **Podmíněný přístup** > **Zásady**.
5. V seznamu **Název zásady** vyberte u testovací zásady místní nabídku ( **...** ) a potom vyberte **Odstranit**. Kliknutím na **tlačítko Ano** potvrďte akci.

## <a name="next-steps"></a>Další kroky 
V tomto kurzu jste vytvořili zásady, které vyžadují, aby se zařízení s iOSem zaregistrovala v Intune a používala aplikaci Outlook pro přístupu k e-mailu Exchange Online. Další informace o použití Intune s podmíněným přístupem k ochraně dalších aplikací a služeb, včetně klientů Exchange ActiveSync pro Office 365 Exchange Online, najdete v tématu [nastavení podmíněného přístupu](conditional-access.md).
