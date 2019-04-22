---
title: Kurz – ochrana e-mailu Exchange Online na nespravovaných zařízeních
titleSuffix: Microsoft Intune
description: Zjistěte, jak zabezpečit Office 365 Exchange Online pomocí zásad ochrany aplikací Intune a podmíněného přístupu Azure AD.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/26/2019
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e6224a0dae7c0aa3d80d4e64331a668953220f65
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59894667"
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

Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo správce služby Intune. Intune najdete na webu Azure Portal, když zvolíte **Všechny služby** > **Intune**.

## <a name="create-the-app-protection-policy"></a>Vytvoření zásad ochrany aplikací
Pro účely tohoto kurzu nastavíme zásady ochrany aplikací Intune pro aplikaci Outlook do ochrany na místě na úrovni aplikace. Jsme budete požadovat PIN kód pro otevření aplikace v pracovním kontextu. Také vytvoříme omezit sdílení dat mezi aplikacemi a zabránit ukládání do osobního umístění dat společnosti.

1.  V Intune, vyberte **klientské aplikace** > **zásady ochrany aplikací** > **přidat zásadu**.
2.  V **název**, zadejte **test zásad aplikace Outlook**.
3.  V **popis**, zadejte **test zásad aplikace Outlook**.
4.  Vyberte **aplikace**. V seznamu aplikací vyberte **Outlook**a klikněte na tlačítko **vyberte**.
5.  Vyberte **nastavení**. 
6.  V části **přemístění dat**, v tomto kurzu vyberte tato nastavení:

    - Pro **povolit aplikaci posílat data do jiných aplikací**vyberte **žádný**.
    - Pro **povolit aplikaci přijímat data z jiných aplikací**vyberte **žádný**.
    - Pro **zabránit "Uložit jako"** vyberte **Ano**.
    - Pro **omezit vyjmutí, kopírování a vkládání v ostatních aplikacích**vyberte **blokováno**.
   
     ![Vyberte aplikaci Outlook nastavení zásad ochrany aplikací data přemístění](media/tutorial-protect-email-on-unmanaged-devices/outlook-app-data-relocation.png)
    
7.  V části **akce přístupu**, v tomto kurzu vyberte tato nastavení:

    - Pro **požadovat kód PIN pro přístup k**vyberte **Ano**.
    - Pro **vyžadovat pro přístup podnikové přihlašovací údaje**vyberte **Ano**.
    - Všechna ostatní nastavení ponechte jejich výchozí hodnoty.
 
     ![Vyberte akce Outlooku aplikaci ochrany zásady přístupu](media/tutorial-protect-email-on-unmanaged-devices/outlook-app-access-actions.png)

9.  Vyberte **OK**.
10. Vyberte **Vytvořit**.

Vytvoření zásady ochrany aplikací pro aplikaci Outlook. Můžete nyní nastavit podmíněný přístup tak, aby vyžadovala zařízení, aby používali aplikaci Outlook.

## <a name="create-conditional-access-policies"></a>Vytvořit zásady podmíněného přístupu
Teď vytvoříme dvě zásady podmíněného přístupu pro všechny platformy zařízení. První zásada požaduje, klienti moderního ověřování, jako je Outlook pro iOS a aplikace Outlook pro Android, použít schválenou aplikaci Outlook a vícefaktorové ověřování. Druhá zásada, bude vyžadovat klientům protokolu Exchange ActiveSync použít schválenou aplikaci Outlook. (V současné době protokolu Exchange Active Sync nepodporuje podmínky než platformu zařízení). V portálu Azure AD nebo na portálu Intune můžete nakonfigurovat zásady podmíněného přístupu. Vzhledem k tomu, že se už nacházíme na portálu Intune, vytvoříme zásadu zde.
### <a name="create-an-mfa-policy-for-modern-authentication-clients"></a>Vytvoření zásad vícefaktorového ověřování pro moderní ověřování klientů
1.  V Intune vyberte **Podmíněný přístup** > **Zásady** > **Nová zásada**.
1.  V **název**, zadejte **testování zásad pro klienty moderní ověřování**. 
3.  V části **Přiřazení** vyberte **Uživatelé a skupiny**. Na kartě **Zahrnout** vyberte **Všichni uživatelé** a vyberte **Hotovo**.

4.  V části **Přiřazení** vyberte **Cloudové aplikace**. Protože chceme chránit e-mail Office 365 se službou Exchange Online, vybereme ho následujícím postupem:
     
    1. Na kartě **Zahrnout** zvolte **Vybrat aplikace**.
    2. Zvolte **Vybrat**. 
    3. V seznamu aplikací vyberte **Office 365 se službou Exchange Online** a potom zvolte **Vybrat**. 
    4. Vyberte **Done** (Hotovo).
  
    ![Výběr aplikace Office 365 se službou Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-cloud-apps.png)

5.  V části **Přiřazení** vyberte **Podmínky** > **Platformy zařízení**.
     
    1. V části **Konfigurovat** vyberte **Ano**.
    2. Na **zahrnout** kartu, vyberte možnost **jakékoli zařízení**.
    1. Vyberte **Done** (Hotovo).
   
6.  Na **podmínky** vyberte **klientské aplikace**.
     
    1. V části **Konfigurovat** vyberte **Ano**.
    2. Vyberte **mobilní aplikace a desktopoví klienti** a **klienti moderního ověřování**.
    3. Zrušte zaškrtnutí ostatních políček.
    4. Vyberte **Hotovo** a potom znovu vyberte **Hotovo**.
    
    ![Výběr aplikace Office 365 se službou Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-client-apps.png)

7.  V části **Ovládací prvky přístupu** zvolte **Udělení**. 
     
    1. V podokně **Udělení** vyberte **Udělit přístup**.
    2. Vyberte **vyžadovat vícefaktorové ověřování**.
    4. Vyberte **Vyžaduje se klientem schválená aplikace**.
    5. V části **Pro více ovládacích prvků** vyberte **Vyžadovat všechny vybrané ovládací prvky**. Toto nastavení zajistí, že se při přístupu zařízení k e-mailu oba vybrané požadavky vynutí.
    6. Zvolte **Vybrat**.
     
    ![Výběr aplikace Office 365 se službou Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-mfa.png)

8.  V části **Povolit zásadu** vyberte **Zapnuto**.
     
    ![Výběr aplikace Office 365 se službou Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/enable-policy.png)

9.  Vyberte **Vytvořit**.

Vytvoření zásady podmíněného přístupu pro moderní ověřování klientů. Nově můžete vytvářet zásady pro klienty protokolu Exchange Active Sync.

### <a name="create-a-policy-for-exchange-active-sync-clients"></a>Vytvoření zásad pro klienty protokolu Exchange Active Sync
1.  V Intune vyberte **Podmíněný přístup** > **Zásady** > **Nová zásada**.
2.  V **název**, zadejte **testování zásad pro klienty EAS**. 
3.  V části **Přiřazení** vyberte **Uživatelé a skupiny**. Na kartě **Zahrnout** vyberte **Všichni uživatelé** a vyberte **Hotovo**.

4.  V části **Přiřazení** vyberte **Cloudové aplikace**. Vyberte Office 365 Exchange Online e-mailu pomocí těchto kroků:
     
    1. Na kartě **Zahrnout** zvolte **Vybrat aplikace**.
    2. Zvolte **Vybrat**. 
    3. V seznamu aplikací vyberte **Office 365 se službou Exchange Online** a potom zvolte **Vybrat**. 
    4. Vyberte **Done** (Hotovo).

5.  V části **Přiřazení** vyberte **Podmínky** > **Platformy zařízení**.
     
    1. V části **Konfigurovat** vyberte **Ano**.
    2. Na **zahrnout** kartu, vyberte možnost **jakékoli zařízení**a pak vyberte **provádí**. 
    3. Znovu vyberte **Hotovo**.

6.  Na **podmínky** vyberte **klientské aplikace**.
     
    1. V části **Konfigurovat** vyberte **Ano**.
    2. Vyberte **mobilní aplikace a desktopoví klienti**.
    3. Vyberte **klientů protokolu Exchange ActiveSync** a **použít zásady jenom na podporovaných platformách**. 
    4. Zaškrtnutí všech ostatních políček zrušte.
    5. Vyberte **Hotovo** a potom znovu vyberte **Hotovo**.
    
    ![Výběr aplikace Office 365 se službou Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/eas-client-apps.png)

7.  V části **Ovládací prvky přístupu** zvolte **Udělení**. 
     
    1. V podokně **Udělení** vyberte **Udělit přístup**.
    4. Vyberte **Vyžaduje se klientem schválená aplikace**. Zaškrtnutí všech ostatních políček zrušte.
    6. Zvolte **Vybrat**.
     
    ![Výběr aplikace Office 365 se službou Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/eas-grant-access.png)

8.  V části **Povolit zásadu** vyberte **Zapnuto**.

9.  Vyberte **Vytvořit**.

Zásady ochrany aplikací a podmíněný přístup se teď na místě a připravené k testování. 

## <a name="try-it-out"></a>Vyzkoušet
Se zásadami, které jste vytvořili zařízení bude potřeba zaregistrovat v Intune a používat mobilní aplikaci Outlook pro přístup k e-mailu Office 365. Pokud chcete tento scénář otestovat na zařízení s iOSem, zkuste se přihlásit k Exchangi Online pomocí přihlašovacích údajů uživatele v testovacím tenantovi.
1. Pokud si chcete zásady otestovat na iPhonu, přejděte na **Nastavení** > **Hesla a účty** > **Přidat účet** > **Exchange**.
2. Zadejte e-mailovou adresu uživatele v testovacím tenantovi a stiskněte **Další**.
3. Stiskněte **Přihlásit se**.
4. Zadejte heslo testovacího uživatele a stiskněte **Přihlásit se**.
5. Zpráva **jsou požadovány další informace** se zobrazí, což znamená, že se zobrazí se výzva k nastavení vícefaktorového ověřování. Pokračujte a nastavit další metodu ověřování.
6. Dále uvidíte zprávu, která říká, že se pokoušíte otevřít tento prostředek aplikace, která vaše IT oddělení neschválilo. To znamená, že jste se blokovat pomocí nativní poštovní aplikace. Zrušte přihlášení.
7.  Otevřete aplikaci Outlook a vyberte **nastavení** > **přidat účet** > **přidat e-mailový účet**.
8. Zadejte e-mailovou adresu uživatele v testovacím tenantovi a stiskněte **Další**.
9. Stisknutím klávesy **Přihlaste se pomocí Office 365**. Budete vyzváni k další ověřování a registraci. Jakmile se přihlásíte, můžete otestovat akce, jako je vyjmutí, kopírování, vložení a "Uložit jako".

## <a name="clean-up-resources"></a>Vyčištění prostředků
Pokud už testovací zásady nepotřebujete, můžete je odebrat.
1. Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo jako správce služby Intune.
2. Vyberte **Dodržování předpisů zařízením** > **Zásady**.
3. V seznamu **Název zásady** vyberte u testovací zásady místní nabídku (**...**) a potom vyberte **Odstranit**. Vyberte **OK**. Tím akci potvrdíte.
4. Vyberte **Podmíněný přístup** > **Zásady**.
5. V **Název_zásady** seznamu, vyberte příslušnou kontextovou nabídku (**...** ) pro každý testovací zásady, a pak vyberte **odstranit**. Odstranění potvrďte výběrem **Ano**.

 ## <a name="next-steps"></a>Další postup 
V tomto kurzu jste vytvořili aplikaci zásady ochrany a omezit, co může uživatel provést s aplikací Outlook a vytvoříte zásady podmíněného přístupu a vyžadovat aplikace Outlook a vyžadovat vícefaktorové ověřování pro moderní ověřování klientů. Další informace o použití Intune k ochraně ostatním aplikacím a službám s podmíněným přístupem najdete v tématu [nastavit podmíněný přístup](conditional-access.md).
