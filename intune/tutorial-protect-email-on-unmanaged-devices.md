---
title: Kurz – ochrana e-mailu Exchange Online na nespravovaných zařízeních
titleSuffix: Microsoft Intune
description: Zjistěte, jak zabezpečit Office 365 Exchange Online pomocí zásad ochrany aplikací Intune a podmíněného přístupu Azure AD.
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
ms.openlocfilehash: 624cc72ad9539659e1ce2c8b70f6a6698d5e7ba2
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67046285"
---
# <a name="tutorial-protect-exchange-online-email-on-unmanaged-devices"></a>Kurz: Ochrana Exchange Online e-mailu na nespravovaných zařízeních

Další informace o použití zásad ochrany aplikací s podmíněným přístupem pro ochranu Exchange Online i v případě, že zařízení nejsou zaregistrovaná v řešení pro správu zařízení, jako je Intune. V tomto kurzu se naučíte: 

> [!div class="checklist"]
> * Vytvořte zásady ochrany aplikací Intune pro aplikaci Outlook. Budete omezit, co může uživatel udělat s daty aplikace tak, že brání "Uložit jako" a omezit operace vyjmutí, kopírování a vložení akce. 
> * Vytvořte zásady podmíněného přístupu Azure Active Directory (Azure AD), které umožňují jen aplikace Outlook pro přístup k firemnímu e-mailu v Exchangi Online. Budete také potřebovat vícefaktorové ověřování (MFA) pro moderní ověřování klientů, jako je Outlook pro iOS a Android.

## <a name="prerequisites"></a>Požadavky
  - Pro účely tohoto kurzu budete potřebovat testovacího tenanta s následujícími předplatnými:
    - Azure Active Directory Premium ([bezplatná zkušební verze](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
    - Předplatné služby Intune ([bezplatnou zkušební verzi](free-trial-sign-up.md))
    - Předplatné Office 365 Business, které zahrnuje Exchange ([bezplatná zkušební verze](https://go.microsoft.com/fwlink/p/?LinkID=510938))

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) jako globální správce nebo správce služby Intune. Intune najdete na webu Azure Portal, když zvolíte **Všechny služby** > **Intune**.

## <a name="create-the-app-protection-policy"></a>Vytvoření zásad ochrany aplikací
Pro účely tohoto kurzu nastavíme zásady ochrany aplikací Intune pro aplikaci Outlook do ochrany na místě na úrovni aplikace. Jsme budete požadovat PIN kód pro otevření aplikace v pracovním kontextu. Také vytvoříme omezit sdílení dat mezi aplikacemi a zabránit ukládání do osobního umístění dat společnosti.

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) a přejděte na **klientské aplikace** > **zásady ochrany aplikací** > **vytvořit zásadu**.  
2. Nakonfigurujte následující nastavení:  
   - **Název**: Zadejte **test zásad aplikace Outlook**.  
   - **Popis**: Zadejte **test zásad aplikace Outlook**.  
   - **Platforma**: Vyberte **iOS**.  
   - **Cílit na všechny typy aplikací**: Vyberte **ne**a potom **typy aplikací**, zaškrtněte políčko pro **aplikace na nespravovaných zařízeních**.  
3. Vyberte **aplikace**. V seznamu aplikací vyberte **Outlook**a klikněte na tlačítko **vyberte**.
4. Vyberte **nastavení** a otevřete tak podokno nastavení. 
5. V podokně nastavení vyberte **ochranu dat**. V podokně Ochrana dat pod *přenosu dat*, nakonfigurujte následující nastavení pro účely tohoto kurzu:

   - Pro **organizace odesílat data do jiných aplikací**vyberte **žádný**.  
   - Pro **přijímat data z jiných aplikací**vyberte **žádný**.  
   - Pro **ukládat kopie dat organizace**vyberte **bloku**.  
   - Pro **omezit vyjmutí, zkopírování a vložení mezi aplikacemi pro ostatní**vyberte **blokováno**. 
   - Všechna ostatní nastavení ponechte jejich výchozí hodnoty. 
   
   ![Vyberte aplikaci Outlook nastavení zásad ochrany aplikací data přemístění](media/tutorial-protect-email-on-unmanaged-devices/data-protection-settings.png)

   Vyberte **OK** se vraťte do okna nastavení.  

6. Vyberte **požadavky na přístup** a nakonfigurujte následující nastavení:  

   - Pro **kód PIN pro přístup**vyberte **vyžadují**.
   - Pro **pracovní nebo školní přihlašovací údaje pro přístup k účtu**vyberte **vyžadují**.
   - Všechna ostatní nastavení ponechte jejich výchozí hodnoty.
 
    ![Vyberte akce Outlooku aplikaci ochrany zásady přístupu](media/tutorial-protect-email-on-unmanaged-devices/access-requirements-settings.png)

    Vyberte **OK** se vraťte do okna nastavení.  

7.  V podokně nastavení vyberte **OK**a potom v podokně zásady vytvořit zvolte **vytvořit**.

Vytvoření zásady ochrany aplikací pro aplikaci Outlook. Budete dále nastavit podmíněný přístup k vyžaduje zařízení, aby používali aplikaci Outlook.

## <a name="create-conditional-access-policies"></a>Vytvořit zásady podmíněného přístupu
Teď vytvoříme dvě zásady podmíněného přístupu pro všechny platformy zařízení.  

- První zásada požaduje, aby klienti moderního ověřování používat schválené aplikace Outlook aplikace a vícefaktorové ověřování (MFA). Moderní ověřování klienty patří aplikace Outlook pro iOS a aplikace Outlook pro Android.  

- Druhá zásada bude vyžadovat, aby klienti Exchange ActiveSync použít schválenou aplikaci Outlook. (V současné době protokolu Exchange Active Sync nepodporuje podmínky než platformu zařízení). V portálu Azure AD nebo na portálu Intune můžete nakonfigurovat zásady podmíněného přístupu. Vzhledem k tomu, že se už nacházíme na portálu Intune, vytvoříme zásadu zde.  

### <a name="create-an-mfa-policy-for-modern-authentication-clients"></a>Vytvoření zásad vícefaktorového ověřování pro moderní ověřování klientů  

1. V Intune, vyberte **podmíněného přístupu** > **zásady** > **nové zásady**.  

2. Pro **název**, zadejte **testování zásad pro klienty moderní ověřování**.  

3. V části **Přiřazení** vyberte **Uživatelé a skupiny**. Na kartě **Zahrnout** vyberte **Všichni uživatelé** a vyberte **Hotovo**.

4. V části **přiřazení**vyberte **cloudové aplikace nebo akce**. Protože chceme chránit e-mail Office 365 se službou Exchange Online, vybereme ho následujícím postupem:  
     
   1. Na kartě **Zahrnout** zvolte **Vybrat aplikace**.  
   2. Zvolte **Vybrat**.  
   3. V seznamu aplikací vyberte **Office 365 Exchange Online**a klikněte na tlačítko **vyberte**.  
   4. Vyberte **provádí** se vraťte do podokna nové zásady.  
  
   ![Výběr aplikace Office 365 se službou Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-cloud-apps.png)

5. V části **Přiřazení** vyberte **Podmínky** > **Platformy zařízení**.  
   1. V části **Konfigurovat** vyberte **Ano**.  
   2. Na **zahrnout** kartu, vyberte možnost **jakékoli zařízení**.  
   3. Vyberte **Done** (Hotovo).  
   
6. Na **podmínky** vyberte **klientské aplikace**.  
   1. V části **Konfigurovat** vyberte **Ano**.  
   2. Vyberte **mobilní aplikace a desktopoví klienti** a **klienti moderního ověřování**.  
   3. Zrušte zaškrtnutí ostatních políček.  
   4. Vyberte **provádí** > **provádí** se vraťte do podokna nové zásady.  

   ![Výběr aplikace Office 365 se službou Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-client-apps.png)

7. V části **Ovládací prvky přístupu** zvolte **Udělení**. 
     
   1. V podokně **Udělení** vyberte **Udělit přístup**.
   2. Vyberte **vyžadovat vícefaktorové ověřování**.
   3. Vyberte **Vyžaduje se klientem schválená aplikace**.
   4. V části **Pro více ovládacích prvků** vyberte **Vyžadovat všechny vybrané ovládací prvky**. Toto nastavení zajistí, že se při přístupu zařízení k e-mailu oba vybrané požadavky vynutí.
   5. Zvolte **Vybrat**.
     
   ![Výběr aplikace Office 365 se službou Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-mfa.png)

7. V části **povolit zásady**vyberte **na**a pak vyberte **vytvořit**.  
     
    ![Výběr aplikace Office 365 se službou Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/enable-policy.png)  

Vytvoření zásady podmíněného přístupu pro moderní ověřování klientů. Nově můžete vytvářet zásady pro klienty protokolu Exchange Active Sync.

### <a name="create-a-policy-for-exchange-active-sync-clients"></a>Vytvoření zásad pro klienty protokolu Exchange Active Sync  
1. V Intune, vyberte **podmíněného přístupu** > **zásady** > **nové zásady**.  
2. Pro **název**, zadejte **testování zásad pro klienty EAS**.  
3. V části **Přiřazení** vyberte **Uživatelé a skupiny**.  
4. Na kartě *Zahrnout* vyberte **Všichni uživatelé** a vyberte **Hotovo**.  

5. V části **přiřazení**vyberte **cloudové aplikace nebo akce**. Vyberte Office 365 Exchange Online e-mailu pomocí těchto kroků:  
   1. Na kartě *Zahrnout* zvolte **Vybrat aplikace**.  
   2. Zvolte **Vybrat**.  
   3. Ze seznamu *aplikací*vyberte **Office 365 Exchange Online**a klikněte na tlačítko **vyberte**a potom **provádí**.  
  
6. V části **Přiřazení** vyberte **Podmínky** > **Platformy zařízení**.  
   1. V části **Konfigurovat** vyberte **Ano**.  
   2. Na **zahrnout** kartu, vyberte možnost **jakékoli zařízení**a pak vyberte **provádí**.  

7. Na **podmínky** vyberte **klientské aplikace**.  
   1. V části **Konfigurovat** vyberte **Ano**.  
   2. Vyberte **mobilní aplikace a desktopoví klienti**.  
   3. Vyberte **klientů protokolu Exchange ActiveSync** a **použít zásady jenom na podporovaných platformách**.  
   4. Zaškrtnutí všech ostatních políček zrušte.  
   5. Vyberte **Hotovo** a potom znovu vyberte **Hotovo**.  
    
   ![Výběr aplikace Office 365 se službou Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/eas-client-apps.png)  

7. V části **Ovládací prvky přístupu** zvolte **Udělení**.  
   1. V podokně **Udělení** vyberte **Udělit přístup**.  
   2. Vyberte **Vyžaduje se klientem schválená aplikace**. Zaškrtnutí všech ostatních políček zrušte.  
   3. Zvolte **Vybrat**.  
     
   ![Výběr aplikace Office 365 se službou Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/eas-grant-access.png)  

8. V části **Povolit zásadu** vyberte **Zapnuto**.  

9. Vyberte **Vytvořit**.  

Zásady ochrany aplikací a podmíněný přístup se teď na místě a připravené k testování.  

## <a name="try-it-out"></a>Vyzkoušet  
Se zásadami, které jste vytvořili zařízení bude potřeba zaregistrovat v Intune a používat mobilní aplikaci Outlook pro přístup k e-mailu Office 365. Pokud chcete tento scénář otestovat na zařízení s iOSem, zkuste se přihlásit k Exchangi Online pomocí přihlašovacích údajů uživatele v testovacím tenantovi.  
1. Pokud si chcete zásady otestovat na iPhonu, přejděte na **Nastavení** > **Hesla a účty** > **Přidat účet** > **Exchange**.  
2. Zadejte e-mailovou adresu uživatele v testovacím tenantovi a stiskněte **Další**.  
3. Stiskněte **Přihlásit se**.  
4. Zadejte heslo testovacího uživatele a stiskněte **Přihlásit se**.  
5. Zpráva **jsou požadovány další informace** se zobrazí, což znamená, že se zobrazí se výzva k nastavení vícefaktorového ověřování. Pokračujte a nastavit další metodu ověřování.  
6. Dále uvidíte zprávu, která říká, že se pokoušíte otevřít tento prostředek aplikace, která není schválený pro vaše IT oddělení. Tato zpráva znamená, že jste se blokovat pomocí nativní poštovní aplikace. Zrušte přihlášení.  
7. Otevřete aplikaci Outlook a vyberte **nastavení** > **přidat účet** > **přidat e-mailový účet**.  
8. Zadejte e-mailovou adresu uživatele v testovacím tenantovi a stiskněte **Další**.  
9. Stisknutím klávesy **Přihlaste se pomocí Office 365**. Budete vyzváni k další ověřování a registraci. Jakmile se přihlásíte, můžete otestovat akce, jako je vyjmutí, kopírování, vložení a "Uložit jako".  

## <a name="clean-up-resources"></a>Vyčištění prostředků  
Pokud už testovací zásady nepotřebujete, můžete je odebrat.  
1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) jako globální správce nebo správce služby Intune.  
2. Vyberte **Dodržování předpisů zařízením** > **Zásady**.  
3. V seznamu **Název zásady** vyberte u testovací zásady místní nabídku ( **...** ) a potom vyberte **Odstranit**. Vyberte **OK**. Tím akci potvrdíte.  
4. Vyberte **Podmíněný přístup** > **Zásady**.  
5. V **Název_zásady** seznamu, vyberte příslušnou kontextovou nabídku ( **...** ) pro každý testovací zásady, a pak vyberte **odstranit**. Odstranění potvrďte výběrem **Ano**.  

 ## <a name="next-steps"></a>Další postup  
V tomto kurzu jste vytvořili zásady ochrany aplikací a omezit, co může uživatel provést s aplikací Outlook a vytvoříte zásady podmíněného přístupu a vyžadovat aplikace Outlook a vyžadovat vícefaktorové ověřování pro moderní ověřování klientů. Další informace o použití Intune k ochraně ostatním aplikacím a službám s podmíněným přístupem najdete v tématu [nastavit podmíněný přístup](conditional-access.md).
