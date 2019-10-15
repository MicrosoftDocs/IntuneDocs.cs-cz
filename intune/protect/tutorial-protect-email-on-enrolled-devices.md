---
title: Kurz – Ochrana e-mailů Exchange Online na spravovaných zařízeních
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
ms.openlocfilehash: c20c0c1543cd8fcbf7345a02295486aaaa6ddcea
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306862"
---
# <a name="tutorial-protect-exchange-online-email-on-managed-devices"></a>Kurz: Ochrana e-mailů Exchange Online na spravovaných zařízeních
Přečtěte si, jak používat zásady dodržování předpisů pro zařízení s podmíněným přístupem, abyste se ujistili, že zařízení se systémem iOS mají přístup k e-mailu Exchange Online jenom v případě, že jsou spravovaná pomocí Intune 

V tomto kurzu se naučíte: 
> [!div class="checklist"]
> * Vytvořením zásad dodržování předpisů pro zařízení s iOS v Intune můžete nastavit podmínky, které zařízení musí splňovat, aby se dalo považovat za vyhovující.
> * Vytvořte zásadu podmíněného přístupu Azure Active Directory (Azure AD), která vyžaduje, aby se zařízení s iOS zaregistrovala do Intune, dodržovala zásady Intune a používala schválenou mobilní aplikaci Outlooku k přístupu k e-mailu Exchange Online.

Pokud nemáte předplatné Intune, [Zaregistrujte si bezplatný zkušební účet](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Předpoklady
- Pro tento kurz budete potřebovat testovacího tenanta s následujícími předplatnými:
  - Azure Active Directory Premium ([bezplatná zkušební verze](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
  - Předplatné Office 365 Business, které zahrnuje Exchange ([bezplatná zkušební verze](https://go.microsoft.com/fwlink/p/?LinkID=510938))
- Než začnete, vytvořte profil testovacího zařízení pro zařízení s iOS podle kroků v části [rychlý Start: vytvoření profilu e-mailového zařízení pro iOS](../configuration/quickstart-email-profile.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo správce služby Intune. Pokud jste vytvořili zkušební předplatné Intune, účet, se kterým jste předplatné vytvořili, je globální správce.

## <a name="create-the-ios-device-compliance-policy"></a>Vytvoření zásad dodržování předpisů pro zařízení s iOS
Nastavte zásady dodržování předpisů zařízením v Intune, abyste nastavili podmínky, které zařízení musí splňovat, aby bylo považováno za vyhovující. Pro tento kurz vytvoříme zásady dodržování předpisů pro zařízení s iOS. Zásady dodržování předpisů jsou specifické pro konkrétní platformu, takže potřebujete samostatné zásady dodržování předpisů pro každou platformu zařízení, kterou chcete vyhodnotit.

1. V Intune vyberte**zásady**@no__t **dodržování předpisů zařízením**– 1  > **vytvořit zásadu**.
2. Do **název**zadejte **test zásad dodržování předpisů pro iOS**. 
3. V **popisu**zadejte **test zásad dodržování předpisů pro iOS**.
4. V části **platforma**vyberte **iOS**. 
5. Vyberte **nastavení** > **e-mail**. 
     
    1. Vedle vyžadovat, aby **mobilní zařízení měla spravovaný e-mailový profil**, vyberte **vyžadovat**.
    2. Vyberte **OK**.

    ![Nastavení zásad dodržování předpisů e-mailem pro vyžadování spravovaného e-mailového profilu](./media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-email.png)
    
6. Vyberte **stav zařízení**. V poli **zařízení s jailbreakem**vyberte **blokovat**a pak vyberte **OK**.
7. Vyberte **zabezpečení systému** a zadejte nastavení **hesla** . Pro tento kurz vyberte následující doporučená nastavení:
     
    - Pro možnost **vyžadovat heslo k odemknutí mobilních zařízení**vyberte **vyžadovat**.
    - V případě **jednoduchých hesel**vyberte **blokovat**.
    - Pro **minimální délku hesla**zadejte **4**.
    - V případě **požadovaného typu hesla**vyberte možnost **alfanumerické**.
    - **Po maximálním počtu minut po uzamknutí obrazovky před zadáním hesla**vyberte možnost **okamžitě**.
    - Do **vypršení platnosti hesla (dny)** zadejte **41**.
    - Pokud **chcete zabránit opakovanému použití, zadejte pro počet předchozích hesel** **5**.
 
    ![Nastavení hesla pro zásady dodržování předpisů e-mailu](./media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-system-security.png)

8. Vyberte **OK**a pak znovu vyberte **OK** .
9. Vyberte **Create** (Vytvořit).

## <a name="create-the-conditional-access-policy"></a>Vytvoření zásady podmíněného přístupu
Nyní vytvoříme zásadu podmíněného přístupu, která vyžaduje, aby všechny platformy zařízení registrovaly do Intune a dodržovaly zásady dodržování předpisů Intune předtím, než budou mít přístup k Exchangi Online. Pro přístup k e-mailu budeme taky potřebovat aplikaci Outlook. Zásady podmíněného přístupu se dají nakonfigurovat buď na portálu Azure AD, nebo na portálu Intune. Vzhledem k tomu, že už jsme na portálu Intune, vytvoříme tady zásadu.
1. V Intune vyberte zásady **podmíněného přístupu**@no__t-1  > **nové zásady**.
1. Do **název**zadejte **zásady testu pro e-maily Office 365**. 
3. V části **přiřazení**vyberte **Uživatelé a skupiny**. Na kartě **Zahrnout** vyberte **Všichni uživatelé**a potom vyberte **Hotovo**.

4. V části **přiřazení**vyberte **cloudové aplikace**. Vzhledem k tomu, že chceme chránit e-maily Office 365 Exchange Online, vybereme je pomocí následujících kroků:
     
    1. Na kartě **Zahrnout** zvolte **vybrat aplikace**.
    2. Zvolte **Vybrat**. 
    3. V seznamu aplikace vyberte možnost **Office 365 Exchange Online**a pak zvolte **možnost vybrat**. 
    4. Vyberte **Done** (Hotovo).
  
    ![Vyberte aplikaci Office 365 Exchange Online.](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-apps.png)

5. V části **přiřazení**vyberte **podmínky**@no__t**platformy zařízení**-2.
     
    1. V části **Konfigurovat**vyberte **Ano**.
    2. Na kartě **Zahrnout** vyberte **libovolné zařízení**a potom vyberte **Hotovo**. 
    3. Vyberte **Hotovo** .
   
    ![Zahrnout všechna zařízení](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-device-platforms.png)

6. V části **přiřazení**vyberte **podmínky** > **klientské aplikace**.
     
    1. V části **Konfigurovat**vyberte **Ano**.
    2. V tomto kurzu vyberte **mobilní aplikace a klienti klasické pracovní plochy** a **klienti moderních ověřování** (což odkazuje na aplikace, jako je Outlook pro iOS a Outlook pro Android). Zrušte zaškrtnutí všech ostatních políček.
    3. Vyberte **Hotovo**a potom vyberte **Hotovo** .
    
    ![Výběr aplikací a klientů](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-client-apps.png)

7. V části **řízení přístupu**vyberte **udělit**. 
     
    1. V podokně **udělení** vyberte **udělit přístup**.
    2. Vyberte **vyžadovat, aby zařízení bylo označené jako vyhovující**. 
    3. Vyberte **vyžadovat aplikaci schválenou klienta**.
    4. V části **pro více ovládacích prvků**vyberte **vyžadovat všechny vybrané ovládací prvky**. Toto nastavení zajistí, že obě vybrané požadavky budou vynutily, když se zařízení pokusí o přístup k e-mailu.
    5. Zvolte **Vybrat**.
     
    ![Vybrat conrols](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-grant-access.png)

8. V části **Povolit zásadu** vyberte **Zapnuté**.
     
    ![Povolit zásadu](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-enable-policy.png)

9. Vyberte **Create** (Vytvořit).

## <a name="try-it-out"></a>Vyzkoušet
Se zásadami, které jste vytvořili, se musí zařízení se systémem iOS, která se pokusí přihlásit k Office 365, zaregistrovat v Intune a používat mobilní aplikaci Outlook pro iOS. Pokud chcete tento scénář vyzkoušet na zařízení s iOS, zkuste se přihlásit k Exchangi Online s použitím přihlašovacích údajů pro uživatele v testovacím tenantovi. Zobrazí se výzva k registraci zařízení a instalaci mobilní aplikace Outlook.
1. Chcete-li provést test na iPhonu, použijte **nastavení** > **hesla & účty** > **přidejte účet** > **Exchange**.
2. Zadejte e-mailovou adresu uživatele v testovacím tenantovi a potom stiskněte tlačítko **Další**.
3. Stiskněte tlačítko **Přihlásit se**.
4. Zadejte heslo testovacího uživatele a stiskněte tlačítko **Přihlásit**se.
5. Zobrazí se zpráva s informacemi o tom, že vaše zařízení musí být spravované pro přístup k prostředku, spolu s možností zápisu. 

## <a name="clean-up-resources"></a>Vyčištění prostředků
Pokud již nepotřebujete zásady testu, můžete je odebrat.
1. Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo správce služby Intune.
2. Vyberte**zásady**@no__t **dodržování předpisů zařízením**– 1.
3. V seznamu **název zásady** vyberte kontextovou nabídku ( **...** ) pro vaši zásadu testování a pak vyberte **Odstranit**. Kliknutím na **OK** potvrďte.
4. Vyberte**zásady** **podmíněného přístupu** > .
5. V seznamu **název zásady** vyberte kontextovou nabídku ( **...** ) pro vaši zásadu testování a pak vyberte **Odstranit**. Výběrem **Ano** potvrďte.

## <a name="next-steps"></a>Další kroky 
V tomto kurzu jste vytvořili zásady, které vyžadují, aby se zařízení s iOS zaregistrovala do Intune a používala Outlook App k přístupu k e-mailu Exchange Online. Další informace o použití Intune s podmíněným přístupem k ochraně dalších aplikací a služeb, včetně klientů Exchange ActiveSync pro Office 365 Exchange Online, najdete v tématu [nastavení podmíněného přístupu](conditional-access.md).
