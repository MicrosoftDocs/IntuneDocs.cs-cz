---
title: Nastavení podmíněného přístupu podle zařízení v Intune
titlesuffix: Microsoft Intune
description: Zjistěte, jak vytvořit zásadu podmíněného přístupu podle zařízení na základě dodržování předpisů zařízení v Microsoft Intune a správy mobilních aplikací.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7b94204d5d1b141218081d01a6daab0ec84d1693
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57392577"
---
# <a name="create-a-device-based-conditional-access-policy"></a>Vytvoření zásady podmíněného přístupu podle zařízení

S Intune můžete zvýšit podmíněného přístupu v Azure Active Directory tak, že přidáte dodržování předpisů pro mobilní zařízení k řízení přístupu. Po vytvoření zásady dodržování předpisů Intune, který definuje požadavky na zařízení, aby vyhovoval předpisům, můžete použít stav dodržování předpisů zařízení povolit nebo blokovat přístup k aplikacím a službám. Můžete to provést tak, že vytvoříte zásady podmíněného přístupu, který používá nastavení **vyžadovat, aby zařízení bylo označené jako vyhovující**.  

Zásady podmíněného přístupu určuje aplikace nebo služby, které chcete chránit, podmínky, za kterých aplikací nebo služeb je přístupný a uživatelé, kterým se zásady vztahují. Podmíněný přístup je funkce Azure AD premium, je možné konfigurovat ve službě Azure Active Directory, ale můžete také nastavit tyto stejné zásady z portálu Intune. Uzel podmíněného přístupu, ke kterému se přistupuje z *Intune*, je stejný uzel, ke kterému se přistupuje z *Azure AD*.  

> [!IMPORTANT]
> Před nastavením podmíněného přístupu, budete muset nastavit zásady dodržování předpisů zařízeními v Intune k vyhodnocení zařízení založené na tom, jestli splňují konkrétní požadavky. Zobrazit [Začínáme se zásadami dodržování předpisů zařízeními v Intune](device-compliance-get-started.md).

## <a name="create-conditional-access-policy"></a>Vytvoření zásad podmíněného přístupu

1.  Na portálu Intune vyberte **podmíněného přístupu** > **zásady** > **nové zásady**.
   
    ![Vytvořit novou zásadu podmíněného přístupu](media/create-conditional-access-intune/create-ca.png)
 
2.  V části **Přiřazení** vyberte **Uživatelé a skupiny**. 
3.  Na **zahrnout** kartu, identifikovat uživatele nebo skupiny, pro které chcete použít tyto zásady podmíněného přístupu. Jakmile jste se rozhodli, kterým chcete zahrnout, můžete použít **vyloučit** kartu, pokud jsou všechny uživatele, role nebo skupiny, které chcete vyloučit z této zásady.  
    - **Všichni uživatelé**: Vyberte tuto možnost, chcete-li dané zásady používaly pro všechny uživatele a skupiny, včetně hostů a interní uživatele.
  
    - **Vyberte uživatele a skupiny**: Vyberte tuto možnost, zadejte jeden nebo více z následujících možností:
  
      a. **Všichni uživatelé typu Host**: Tuto možnost použijte k zahrnutí nebo vyloučení externím uživatelům typu Host (například partnery, externí spolupracovníci)
       
      b. **Role adresáře**: Vyberte jednu nebo více rolí Azure AD pro zahrnutí nebo vyloučení uživatelů, kteří jsou přiřazeni pracovníci v těchto rolích.
      
      c. **Uživatelé a skupiny**: Vyberte tuto možnost, vyhledejte a vyberte jednotlivé uživatele nebo skupiny, které chcete zahrnout nebo vyloučit.
     
       > [!TIP]  
       > Testování zásady s menší skupinou uživatelů zkontrolujte, zda že vše funguje podle očekávání.
4.  Vyberte **Done** (Hotovo).
5.  V části **Přiřazení** vyberte **Cloudové aplikace**. 
6.  Na **– karta zahrnout**, identifikovat aplikací a služeb, které chcete chránit touto zásadou podmíněného přístupu. Můžete použít **vyloučit** kartu, pokud jsou všechny aplikace nebo služby, které chcete vyloučit z těchto zásad.
    - **Všechny cloudové aplikace**: Vyberte tuto možnost, chcete-li dané zásady používaly pro všemi aplikacemi.
      > [!IMPORTANT]  
      > Aplikace Microsoft Azure Management pro přístup k webu Azure portal je zahrnuta v tomto seznamu. Nezapomeňte použít **vyloučit** buď zde kartě nebo v **uživatelů a skupin** možnosti a ujistěte se, že jste (nebo uživatele nebo skupiny určíte) budete moct přihlásit k webu Azure portal. 

    - **Vyberte aplikace**: Vyberte tuto možnost, zvolte **vyberte**a potom v seznamu aplikací vyhledejte a vyberte aplikacím nebo službám, které chcete chránit.
    
      ![Vytvořit novou zásadu podmíněného přístupu](media/create-conditional-access-intune/create-ca-select-apps.png)

7.  Vyberte **Done** (Hotovo).
8.  V části **přiřazení**vyberte **podmínky**.
    - **Riziko přihlášení**: Zvolte Ano. Pokud chcete použít detekce rizik přihlašování Azure AD Identity Protection k této zásadě a klikněte na tlačítko úrovně rizika přihlášení, které mají zásady platit na.
    - **Platformy zařízení**: Na **zahrnout** kartu, identifikovat chcete tuto zásadu podmíněného přístupu platí pro platformy zařízení. Použití **vyloučit** kartu z této zásady vyloučit platformy.
    - **Umístění**: Na **zahrnout** kartu, zadejte, jestli zásady platí pro jakékoli umístění, důvěryhodný síťových umístěních, která jsou pod kontrolou vašeho oddělení IT nebo konkrétní síťová umístění. Použití **vyloučit** kartu z této zásady vyloučit umístění v síti. 
    - **Klientské aplikace**: Zvolte **Ano** zadat, pokud mají zásady platit do prohlížečových aplikací, mobilní aplikace a desktopoví klienti. Můžete také vybrat **klienti moderního ověřování** (jako je Outlook pro iOS nebo Outlook pro Android) a **klientů protokolu Exchange ActiveSync**.
    - **Stav zařízení**: Zásady podmíněného přístupu se použije na všechny stavy zařízení, pokud vyberte Ano a výslovně vyloučit stavy připojená k hybridní službě Azure AD. zařízení nebo zařízení označené jako vyhovující (nebo obojí).
    
      ![Vytvořit novou zásadu podmíněného přístupu](media/create-conditional-access-intune/create-ca-device-platforms.png)

      > [!TIP]  
      > Pokud chcete chránit i **moderní ověřování** klientů a **klientů protokolu Exchange ActiveSync**, vytvořte dva samostatné zásady podmíněného přístupu pro každý typ klienta. I když Exchange ActiveSync podporuje moderní ověřování, je pouze podmínku, která je podporované protokolem Exchange ActiveSync platformy. Další podmínky, včetně služby Multi-Factor authentication, nejsou podporovány. Účinně chránit přístup k Exchangi Online z protokolu Exchange ActiveSync, vytvoření zásady podmíněného přístupu, který určuje cloudové aplikace Office 365 Exchange Online a klientské aplikace Exchange ActiveSync s použít zásady jenom na podporovaných platformách vybrali.

9.  Vyberte **Done** (Hotovo).
10. V části **Ovládací prvky přístupu** zvolte **Udělení**. Nakonfigurujte, co se stane, na základě podmínek, které jste nastavili.  Můžete vybrat jednu z následujících možností:
    - **Blokovat přístup**: Uživatelé, kteří jsou uvedeni v těchto zásadách bude odepřen přístup k aplikacím v rámci podmínek, které jste zadali.
    - **Udělení přístupu**: Uživatelé, kteří jsou uvedeni v těchto zásadách bude udělen přístup, ale můžete vyžadovat, aby všechny následující další akce:
      - **Vyžadovat vícefaktorové ověřování**: Uživatel bude muset provést další požadavky na zabezpečení, třeba prostřednictvím telefonátu nebo textové.
      - **Vyžadovat, aby zařízení bylo označené jako vyhovující**: Zařízení musí dodržovat předpisy Intune. Pokud zařízení nedodržuje předpisy, uživatel bude mít možnost registrace zařízení v Intune. 
      - **Vyžadovat zařízení připojené k hybridní službě Azure AD**: Zařízení musí být připojená k hybridní Azure AD.
      - **Vyžadovat klientem schválenou aplikaci**: Zařízení musí používat klientem schválených aplikací. 
      - **Pro více ovládacích prvků**: Vyberte **vyžadovat všechny vybrané ovládací prvky** tak, aby všechny výše uvedené požadavky se vynucují, když se zařízení pokusí o přístup k aplikaci.
    
      ![Udělení nastavení řízení přístupu](media/create-conditional-access-intune/create-ca-grant-access-settings.png)
 
11. V části **Povolit zásadu** vyberte **Zapnuto**.
     
     ![Povolení zásady](media/create-conditional-access-intune/enable-policy.png)

12. Vyberte **Vytvořit**.

## <a name="see-also"></a>Viz také:
[Podmíněný přístup na základě aplikace s Intune](app-based-conditional-access-intune.md)
