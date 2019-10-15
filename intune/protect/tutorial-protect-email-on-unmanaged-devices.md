---
title: Kurz – Ochrana e-mailů Exchange Online na nespravovaných zařízeních
titleSuffix: Microsoft Intune
description: Naučte se zabezpečit Office 365 Exchange Online pomocí zásad ochrany aplikací Intune a podmíněného přístupu Azure AD.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/10/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7e0a01034bc35ddf8fd8eb1ede5fcf4c942dc735
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306803"
---
# <a name="tutorial-protect-exchange-online-email-on-unmanaged-devices"></a>Kurz: Ochrana e-mailů Exchange Online na nespravovaných zařízeních

Přečtěte si, jak používat zásady ochrany aplikací s podmíněným přístupem k ochraně Exchange Online, i když nejsou zařízení zaregistrovaná v řešení pro správu zařízení, jako je Intune. V tomto kurzu se naučíte: 

> [!div class="checklist"]
> * Vytvořte zásady ochrany aplikací Intune pro aplikaci Outlook. Můžete omezit, co může uživatel s daty aplikace dělat, a zabránit tak akcím Uložit jako a omezit operace vyjmutí, zkopírování a vložení. 
> * Vytvoření zásad podmíněného přístupu Azure Active Directory (Azure AD), které umožní přístup k firemnímu e-mailu v Exchange Online jenom aplikaci Outlook. Pro moderní ověřování klientů budete také vyžadovat vícefaktorové ověřování (MFA), jako je Outlook pro iOS a Android.

## <a name="prerequisites"></a>Předpoklady
- Pro tento kurz budete potřebovat testovacího tenanta s následujícími předplatnými:
  - Azure Active Directory Premium ([bezplatná zkušební verze](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
  - Předplatné Intune ([bezplatná zkušební verze](../fundamentals/free-trial-sign-up.md))
  - Předplatné Office 365 Business, které zahrnuje Exchange ([bezplatná zkušební verze](https://go.microsoft.com/fwlink/p/?LinkID=510938))

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) jako globální správce nebo správce služby Intune. Intune se nachází v Azure Portal tím, že vyberete **všechny služby** > **Intune**.

## <a name="create-the-app-protection-policy"></a>Vytvoření zásad ochrany aplikací
V tomto kurzu nastavíme zásady ochrany aplikací Intune pro aplikaci Outlook, aby se na úrovni aplikace umístily ochrany. Pro otevření aplikace v pracovním kontextu budeme vyžadovat kód PIN. Také omezíme sdílení dat mezi aplikacemi a zabránění ukládání firemních dat do osobního umístění.

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) a pokračujte na **klientské aplikace** > **Zásady ochrany aplikací** > **vytvořit zásadu**.  
2. Nakonfigurujte následující nastavení:  
   - **Název**: zadejte **test zásad**aplikace pro Outlook.  
   - **Popis**: zadejte **test zásad**aplikace pro Outlook.  
   - **Platforma**: vyberte **iOS**.  
   - **Cílit na všechny typy aplikací**: vyberte **ne**a pak u **typů aplikací**zaškrtněte políčko pro **aplikace na nespravovaných zařízeních**.  
3. Vyberte **aplikace**. V seznamu aplikace vyberte možnost **Outlook**a pak zvolte **možnost vybrat**.
4. Výběrem **Nastavení** otevřete podokno nastavení. 
5. V podokně nastavení vyberte **Ochrana dat**. V podokně Ochrana dat níže *přenos dat*nakonfigurujte následující nastavení pro tento kurz:

   - Pro možnost **Odeslat organizační data do jiných aplikací**vyberte **None (žádné**).  
   - Pro **příjem dat z jiných aplikací**vyberte **None (žádné**).  
   - V **části uložit kopie organizačních dat**vyberte **blokovat**.  
   - Pokud chcete **Omezit vyjmutí, zkopírování a vložení mezi ostatními aplikacemi**, vyberte **blokované**. 
   - Ponechte všechna ostatní nastavení na jejich výchozích hodnotách. 
   
   ![Výběr nastavení přemístění dat v zásadách ochrany aplikací Outlook](./media/tutorial-protect-email-on-unmanaged-devices/data-protection-settings.png)

   Kliknutím na **tlačítko OK** se vraťte do podokna nastavení.  

6. Vyberte možnost **požadavky na přístup** a pak nakonfigurujte následující nastavení:  

   - V případě **kódu PIN pro přístup**vyberte **vyžadovat**.
   - V případě **přihlašovacích údajů pracovního nebo školního účtu pro přístup**vyberte **vyžadovat**.
   - Ponechte všechna ostatní nastavení na jejich výchozích hodnotách.
 
    ![Vybrat akce přístupu k zásadám ochrany aplikací Outlook](./media/tutorial-protect-email-on-unmanaged-devices/access-requirements-settings.png)

    Kliknutím na **tlačítko OK** se vraťte do podokna nastavení.  

7. V podokně nastavení vyberte **OK**a pak v podokně vytvořit zásadu vyberte **vytvořit**.

Vytvoří se zásady ochrany aplikací pro Outlook. V dalším kroku nastavíte podmíněný přístup, který bude vyžadovat, aby zařízení používalo Outlookovou aplikaci.

## <a name="create-conditional-access-policies"></a>Vytvoření zásad podmíněného přístupu
Nyní vytvoříme dvě zásady podmíněného přístupu, které pokrývají všechny platformy zařízení.  

- První zásada bude vyžadovat, aby klienti moderního ověřování používali schválenou aplikaci Outlook a službu Multi-Factor Authentication (MFA). Mezi klienty moderního ověřování patří Outlook pro iOS a Outlook pro Android.  

- Druhá zásada bude vyžadovat, aby klienti Exchange ActiveSync používali schválenou aplikaci Outlook. (V současné době Exchange Active Sync nepodporuje jiné podmínky než platforma zařízení). Zásady podmíněného přístupu můžete nakonfigurovat buď na portálu Azure AD, nebo na portálu Intune. Vzhledem k tomu, že už jsme na portálu Intune, vytvoříme tady zásadu.  

### <a name="create-an-mfa-policy-for-modern-authentication-clients"></a>Vytvoření zásady MFA pro klienty moderních ověřování  

1. V Intune vyberte zásady **podmíněného přístupu**@no__t-1  > **nové zásady**.  

2. Jako **název**zadejte **zásady testování pro klienty s moderním ověřováním**.  

3. V části **přiřazení**vyberte **Uživatelé a skupiny**. Na kartě **Zahrnout** vyberte **Všichni uživatelé**a potom vyberte **Hotovo**.

4. V části **přiřazení**vyberte **cloudové aplikace nebo akce**. Vzhledem k tomu, že chceme chránit e-maily Office 365 Exchange Online, vybereme je pomocí následujících kroků:  
     
   1. Na kartě **Zahrnout** zvolte **vybrat aplikace**.  
   2. Zvolte **Vybrat**.  
   3. V seznamu aplikace vyberte možnost **Office 365 Exchange Online**a pak zvolte **možnost vybrat**.  
   4. Vyberte **Hotovo** a vraťte se do podokna nové zásady.  
  
   ![Vyberte aplikaci Office 365 Exchange Online.](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-cloud-apps.png)

5. V části **přiřazení**vyberte **podmínky**@no__t**platformy zařízení**-2.  
   1. V části **Konfigurovat**vyberte **Ano**.  
   2. Na kartě **Zahrnout** vyberte **libovolné zařízení**.  
   3. Vyberte **Done** (Hotovo).  
   
6. V podokně **podmínky** vyberte **klientské aplikace**.  
   1. V části **Konfigurovat**vyberte **Ano**.  
   2. Vyberte **mobilní aplikace a klienti pro stolní počítače** a **moderní ověřování**.  
   3. Zrušte zaškrtnutí těchto políček.  
   4. Vyberte **hotovo** > **Hotovo** pro návrat do podokna nové zásady.  

   ![Vybrat mobilní aplikace a klienti](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-client-apps.png)

7. V části **řízení přístupu**vyberte **udělit**. 
     
   1. V podokně **udělení** vyberte **udělit přístup**.
   2. Vyberte **vyžadovat službu Multi-Factor Authentication**.
   3. Vyberte **vyžadovat aplikaci schválenou klienta**.
   4. V části **pro více ovládacích prvků**vyberte **vyžadovat všechny vybrané ovládací prvky**. Toto nastavení zajistí, že obě vybrané požadavky budou vynutily, když se zařízení pokusí o přístup k e-mailu.
   5. Zvolte **Vybrat**.
     
   ![Vybrat ovládací prvky](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-mfa.png)

7. V části **Povolit zásadu**vyberte **zapnuto**a pak vyberte **vytvořit**.  
     
    ![Vytvoření zásad](./media/tutorial-protect-email-on-unmanaged-devices/enable-policy.png)  

Vytvoří se zásada podmíněného přístupu pro klienty moderního ověřování. Nyní můžete vytvořit zásadu pro klienty Exchange Active Sync.

### <a name="create-a-policy-for-exchange-active-sync-clients"></a>Vytvoření zásady pro Exchange Active Sync klientů  
1. V Intune vyberte zásady **podmíněného přístupu**@no__t-1  > **nové zásady**.  
2. Jako **název**zadejte **zásady testování pro klienty EAS**.  
3. V části **přiřazení**vyberte **Uživatelé a skupiny**.  
4. Na kartě *Zahrnout* vyberte **Všichni uživatelé**a potom vyberte **Hotovo**.  

5. V části **přiřazení**vyberte **cloudové aplikace nebo akce**. Vyberte e-mailovou zprávu Office 365 Exchange Online s těmito kroky:  
   1. Na kartě *Zahrnout* zvolte **vybrat aplikace**.  
   2. Zvolte **Vybrat**.  
   3. V seznamu *aplikací*vyberte možnost **Office 365 Exchange Online**a pak klikněte na **Vybrat**a pak na **Hotovo**.  
  
6. V části **přiřazení**vyberte **podmínky**@no__t**platformy zařízení**-2.  
   1. V části **Konfigurovat**vyberte **Ano**.  
   2. Na kartě **Zahrnout** vyberte **libovolné zařízení**a potom vyberte **Hotovo**.  

7. V podokně **podmínky** vyberte **klientské aplikace**.  
   1. V části **Konfigurovat**vyberte **Ano**.  
   2. Vyberte **mobilní aplikace a klienti klasické pracovní plochy**.  
   3. Vyberte **klienti Exchange ActiveSync** a **použijte zásady jenom pro podporované platformy**.  
   4. Zrušte zaškrtnutí všech ostatních políček.  
   5. Vyberte **Hotovo**a potom vyberte **Hotovo** .  
    
   ![Platí pro podporované platformy](./media/tutorial-protect-email-on-unmanaged-devices/eas-client-apps.png)  

7. V části **řízení přístupu**vyberte **udělit**.  
   1. V podokně **udělení** vyberte **udělit přístup**.  
   2. Vyberte **vyžadovat aplikaci schválenou klienta**. Zrušte zaškrtnutí všech ostatních políček.  
   3. Zvolte **Vybrat**.  
     
   ![Vyžadovat klientskou aplikaci schválenou](./media/tutorial-protect-email-on-unmanaged-devices/eas-grant-access.png)  

8. V části **Povolit zásadu** vyberte **Zapnuté**.  

9. Vyberte **Create** (Vytvořit).  

Vaše zásady ochrany aplikací a podmíněný přístup teď fungují a jsou připravené k testování.  

## <a name="try-it-out"></a>Vyzkoušet  
Pomocí zásad, které jste vytvořili, se zařízení musí zaregistrovat v Intune a používat mobilní aplikaci Outlook k přístupu k e-mailu Office 365. Pokud chcete tento scénář vyzkoušet na zařízení s iOS, zkuste se přihlásit k Exchangi Online s použitím přihlašovacích údajů pro uživatele v testovacím tenantovi.  
1. Chcete-li provést test na iPhonu, použijte **nastavení** > **hesla & účty** > **přidejte účet** > **Exchange**.  
2. Zadejte e-mailovou adresu uživatele v testovacím tenantovi a potom stiskněte tlačítko **Další**.  
3. Stiskněte tlačítko **Přihlásit se**.  
4. Zadejte heslo testovacího uživatele a stiskněte tlačítko **Přihlásit**se.  
5. Zobrazí se **Další informace, které jsou požadovány** , což znamená, že se zobrazí výzva k nastavení vícefaktorového ověřování. Pokračujte a nastavte další metodu ověřování.  
6. V dalším kroku se zobrazí zpráva s informacemi o tom, že se snažíte otevřít tento prostředek, pomocí aplikace, která není schválená vaším IT oddělením. Zpráva znamená, že jste zablokovali používání aplikace v nativním e-mailu. Zrušte přihlášení.  
7. Otevřete Outlook App a vyberte **nastavení** > **Přidat účet** > **Přidat e-mailový účet**.  
8. Zadejte e-mailovou adresu uživatele v testovacím tenantovi a potom stiskněte tlačítko **Další**.  
9. Stiskněte tlačítko **Přihlásit se sadou Office 365**. Zobrazí se výzva k dodatečnému ověření a registraci. Po přihlášení můžete testovat akce, jako je vyjmutí, kopírování, vložení a uložit jako.  

## <a name="clean-up-resources"></a>Vyčištění prostředků  
Pokud již nepotřebujete zásady testu, můžete je odebrat.  
1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) jako globální správce nebo správce služby Intune.  
2. Vyberte**zásady**@no__t **dodržování předpisů zařízením**– 1.  
3. V seznamu **název zásady** vyberte kontextovou nabídku ( **...** ) pro vaši zásadu testování a pak vyberte **Odstranit**. Kliknutím na **OK** potvrďte.  
4. Vyberte**zásady** **podmíněného přístupu** > .  
5. V seznamu **název zásady** vyberte kontextovou nabídku ( **...** ) pro každou ze svých zásad testování a pak vyberte **Odstranit**. Výběrem **Ano** potvrďte.  

## <a name="next-steps"></a>Další kroky  
V tomto kurzu jste vytvořili zásady ochrany aplikací, abyste omezili to, co může uživatel dělat s aplikací Outlook, a vytvořili jste zásady podmíněného přístupu, které vyžadují aplikaci Outlook a vyžadují MFA pro klienty moderních ověřování. Další informace o používání Intune s podmíněným přístupem k ochraně dalších aplikací a služeb najdete v tématu [nastavení podmíněného přístupu](conditional-access.md).
