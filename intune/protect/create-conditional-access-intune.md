---
title: Nastavení podmíněného přístupu na základě zařízení s Intune
titleSuffix: Microsoft Intune
description: Naučte se vytvářet zásady podmíněného přístupu na základě zařízení, které jsou založené na Microsoft Intune dodržování předpisů zařízením a správu mobilních aplikací.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b775bb09c289733cdc2837984874b7c1c7e286bc
ms.sourcegitcommit: 1a5b185acd27954b10b6d59409d82eb80fd71284
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/21/2019
ms.locfileid: "72681371"
---
# <a name="create-a-device-based-conditional-access-policy"></a>Vytvoření zásady podmíněného přístupu na základě zařízení

S Intune můžete vylepšit podmíněný přístup v Azure Active Directory tím, že do ovládacích prvků přístupu přidáte dodržování předpisů pro mobilní zařízení. Jakmile vytvoříte zásady dodržování předpisů Intune, které definují požadavky na dodržování předpisů pro zařízení, můžete použít stav dodržování předpisů zařízení, abyste povolili nebo zablokovali přístup k vašim aplikacím a službám. Můžete to udělat tak, že vytvoříte zásadu podmíněného přístupu, která používá nastavení **vyžadovat, aby zařízení bylo označené jako vyhovující**.  

Zásady podmíněného přístupu určují aplikace nebo služby, které chcete chránit, podmínky, za kterých se mají přistupovat k aplikacím nebo službám, a uživatele, na které se zásady vztahují. Podmíněný přístup je funkce Azure AD Premium, která se dá nakonfigurovat v Azure Active Directory, ale můžete si na portálu Intune nastavit i stejné zásady. Uzel podmíněného přístupu, ke kterému se přistupuje z *Intune*, je stejný uzel, ke kterému se přistupuje z *Azure AD*.  

> [!IMPORTANT]
> Před nastavením podmíněného přístupu budete muset nastavit zásady dodržování předpisů zařízením v Intune, které budou vyhodnocovat zařízení na základě toho, jestli splňují konkrétní požadavky. Přečtěte si téma Začínáme [se zásadami dodržování předpisů zařízeními v Intune](device-compliance-get-started.md).

## <a name="create-conditional-access-policy"></a>Vytvořit zásady podmíněného přístupu

1. Na portálu Intune vyberte**zásady** **podmíněného přístupu** >   > **nové zásady**.
   
    ![Vytvořit nové zásady podmíněného přístupu](./media/create-conditional-access-intune/create-ca.png)
 
2. V části **Přiřazení** vyberte **Uživatelé a skupiny**. 
3. Na kartě **Zahrnout** Určete uživatele nebo skupiny, kterým chcete uplatnit tyto zásady podmíněného přístupu. Jakmile se rozhodnete, kterou chcete zahrnout, můžete použít kartu **vyloučit** , pokud existují uživatelé, role nebo skupiny, které chcete vyloučit z těchto zásad.  
    - **Všichni uživatelé**: tuto možnost vyberte, pokud chcete zásady použít pro všechny uživatele a skupiny, včetně interních uživatelů a uživatelů typu Host.
  
    - **Vyberte uživatelé a skupiny**: Vyberte tuto možnost a zadejte jednu nebo více z následujících možností:
  
      a. **Všichni uživatelé typu Host**: tuto možnost vyberte, pokud chcete zahrnout nebo vyloučit externí uživatele typu Host (například partneři, externí spolupracovníci).
       
      b. **Role adresáře**: vyberte jednu nebo více rolí Azure AD, chcete-li zahrnout nebo vyloučit uživatele, kteří jsou přiřazeni k těmto rolím.
      
      c. **Uživatelé a skupiny**: tuto možnost vyberte, pokud chcete hledat a vybrat jednotlivé uživatele nebo skupiny, které chcete zahrnout nebo vyloučit.
     
       > [!TIP]  
       > Otestujte zásadu s menší skupinou uživatelů, abyste se ujistili, že funguje podle očekávání.
4. Vyberte **Hotovo**.
5. V části **Přiřazení** vyberte **Cloudové aplikace**. 
6. Na **kartě zahrnout**určete aplikace a služby, které chcete chránit pomocí těchto zásad podmíněného přístupu. Pak můžete použít kartu **vyloučit** , pokud existují nějaké aplikace nebo služby, které chcete z této zásady vyloučit.
    - **Všechny cloudové aplikace**: tuto možnost vyberte, pokud chcete zásady použít pro všechny aplikace.
      > [!IMPORTANT]  
      > V tomto seznamu je obsažena aplikace Microsoft Azure Management pro přístup k Azure Portal. Nezapomeňte použít kartu **vyloučit** buď zde, nebo v možnostech **uživatelů a skupin** , abyste se ujistili, že jste (nebo uživatelé nebo skupiny, které určíte), se budou moci přihlásit k Azure Portal. 

    - **Vybrat aplikace**: Vyberte tuto možnost, zvolte **Vybrat**a pak pomocí seznamu aplikace vyhledejte a vyberte aplikace nebo služby, které chcete chránit.
    
      ![Konfigurace přiřazení pro zásady podmíněného přístupu](./media/create-conditional-access-intune/create-ca-select-apps.png)

7. Vyberte **Hotovo**.
8. V části **přiřazení**vyberte **podmínky**.
    - **Riziko přihlášení**: zvolte Ano, pokud chcete s touto zásadou Azure AD Identity Protection zjišťování rizik při přihlašování, a pak zvolte úrovně rizika přihlašování, na které se zásady mají vztahovat.
    - **Platformy zařízení**: na kartě **Zahrnout** určete platformy zařízení, pro které chcete tyto zásady podmíněného přístupu použít. K vyloučení platforem z této zásady použijte kartu **vyloučit** .
    - **Umístění**: na kartě **Zahrnout** určete, jestli se zásada vztahuje na jakékoli umístění, důvěryhodná síťová umístění, která jsou pod kontrolou vašeho oddělení IT, nebo specifická umístění v síti. Pomocí karty **vyloučit** z těchto zásad vylučte síťová umístění. 
    - **Klientské aplikace**: Pokud chcete určit, jestli se má zásada vztahovat na aplikace prohlížeče, mobilní aplikace a desktopové klienty, zvolte **Ano** . Můžete také vybrat **moderní ověřovací klienty** (například Outlook pro iOS nebo Outlook pro Android) a **klienty Exchange ActiveSync**.
    - **Stav zařízení**: zásady podmíněného přístupu se použijí na všechny stavy zařízení, pokud nevyberete Ano a výslovně vyloučíte stav zařízení, připojené k hybridní službě Azure AD nebo zařízení označené jako kompatibilní (nebo obojí).
    
      ![Nastavení podmínek pro zásady podmíněného přístupu](./media/create-conditional-access-intune/create-ca-device-platforms.png)

      > [!TIP]  
      > Pokud chcete chránit oba klienty pro **moderní ověřování** i **klienty Exchange ActiveSync**, vytvořte dvě samostatné zásady podmíněného přístupu, jednu pro každý typ klienta. I když Exchange ActiveSync podporuje moderní ověřování, jediná podmínka, kterou podporuje Exchange ActiveSync, je platforma. Další podmínky, včetně Multi-Factor Authentication, se nepodporují. Pokud chcete efektivně chránit přístup k Exchangi Online z Exchange ActiveSync, vytvořte zásadu podmíněného přístupu, která určuje cloudovou aplikaci Office 365 Exchange Online a klientskou aplikaci Exchange ActiveSync se zásadami použít jenom pro vybrané podporované platformy.

9. Vyberte **Hotovo**.
10. V části **Ovládací prvky přístupu** zvolte **Udělení**. Nakonfigurujte, co se stane na základě podmínek, které jste nastavili.  Můžete vybrat z následujících možností:
    - **Blokovat přístup**: uživatelům zadaným v této zásadě bude odepřen přístup k aplikacím za podmínek, které jste zadali.
    - **Udělení přístupu**: uživatelům zadaným v této zásadě se udělí přístup, ale můžete potřebovat některou z následujících akcí:
      - **Vyžadovat vícefaktorové ověřování**: uživatel bude muset provést další požadavky na zabezpečení, jako je telefonní hovor nebo text.
      - **Vyžadovat, aby zařízení bylo označené jako vyhovující**: zařízení musí být kompatibilní s Intune. Pokud zařízení nedodržuje předpisy, zobrazí se uživateli možnost zaregistrovat zařízení v Intune. 
      - **Vyžadovat zařízení připojené k hybridní službě Azure AD**: zařízení musí být připojená k hybridní službě Azure AD.
      - **Vyžadovat schválenou klientskou aplikaci**: zařízení musí používat schválené klientské aplikace. 
      - **Pro více ovládacích prvků**: vyberte **vyžadovat všechny vybrané ovládací prvky** , aby všechny výše uvedené požadavky byly vynucené, když se zařízení pokusí o přístup k aplikaci.
    
      ![Nastavení udělení řízení přístupu](./media/create-conditional-access-intune/create-ca-grant-access-settings.png)
 
11. V části **Povolit zásadu** vyberte **Zapnuto**.
     
     ![Povolit zásadu](./media/create-conditional-access-intune/enable-policy.png)

12. Vyberte **Vytvořit**.

## <a name="see-also"></a>Související témata
[Podmíněný přístup na základě aplikace s Intune](app-based-conditional-access-intune.md)

[Řešení potíží s podmíněným přístupem Intune](https://support.microsoft.com/help/4456106)
