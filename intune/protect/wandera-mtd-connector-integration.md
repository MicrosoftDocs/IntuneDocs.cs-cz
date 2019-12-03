---
title: Nastavení integrace ochrany před mobilními hrozbami Wandera v Intune
titleSuffix: Intune on Azure
description: Jak nastavit řešení ochrany před mobilními hrozbami Wandera pomocí Microsoft Intune pro řízení přístupu mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: f42acb38d84394a6b61fa16072de6320b84a67b5
ms.sourcegitcommit: 1a5b185acd27954b10b6d59409d82eb80fd71284
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/21/2019
ms.locfileid: "72681296"
---
# <a name="integrate-wandera-mobile-threat-protection-with-intune"></a>Integrace ochrany před mobilními hrozbami Wandera pomocí Intune  

Provedením následujících kroků Integrujte řešení ochrany před mobilními hrozbami Wandera do Intune.  

> [!NOTE]
> Tento dodavatel ochrany před mobilními hrozbami není u neregistrovaných zařízení podporován.

## <a name="before-you-begin"></a>Před zahájením  

Než začnete s integrací Wandera do Intune, ujistěte se, že jsou splněné následující požadavky:
- Odběr služby Microsoft Intune  
- Přihlašovací údaje správce Azure Active Directory pro udělení následujících oprávnění:  
  - Přihlášení a čtení profilu uživatele  
  - Přístup k adresáři jako přihlášený uživatel  
  - Čtení dat z adresáře  
  - Odeslání informací o zařízení do Intune  

- Předplatné Wandera:
  - Jeden nebo více účtů Wandera, které mají licenci pro modul EMM Connect  
  - Účet s oprávněními superuživatele v Wandera  
 
### <a name="wandera-mobile-threat-defense-app-authorization"></a>Autorizace aplikace pro ochranu před mobilními hrozbami Wandera  

Proces autorizace aplikace ochrany před mobilními hrozbami Wandera:  
- Povolí službě ochrany před mobilními hrozbami Wandera komunikovat informace týkající se stavu zařízení zpátky do Intune.  
- Wandera se synchronizuje s členstvím skupiny registrace Azure AD, aby se naplnila databáze zařízení.  
- Povolte použití jednotného přihlašování (SSO) Azure AD na portálu Wandera pro správu PAPRSKů.  
- Povolí aplikaci ochrany před mobilními hrozbami Wandera přihlašovat se pomocí jednotného přihlašování Azure AD.  


## <a name="set-up-wandera-mobile-threat-defense-integration"></a>Nastavení integrace ochrany před mobilními hrozbami Wandera  
Nastavení modulu *EMM Connect* for Wandera vyžaduje jednorázový proces konfigurace, který dokončíte v konzolách Intune a Wandera. Proces konfigurace trvá přibližně 15 minut. Konfiguraci můžete dokončit bez koordinace s technickým účtem Wandera nebo zástupcem podpory.  

### <a name="enable-support-for-wandera-in-intune"></a>Povolení podpory pro Wandera v Intune
1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) a pokračujte na **dodržování předpisů zařízením**  > **ochrany před mobilními hrozbami** > a vyberte **Přidat**.

2. Na stránce **Přidat konektor** použijte rozevírací seznam a vyberte **Wandera**. A pak vyberte **vytvořit**.  

3. V podokně obrana proti mobilním hrozbám vyberte konektor **Wandera** MTD ze seznamu konektorů a otevřete tak podokno *Upravit konektor* . Vyberte **otevřít konzolu pro správu Wandera** , otevřete [paprskový](https://radar.wandera.com/login), konzolu pro správu Wandera a přihlaste se. 

4. V konzole Wandera přejděte na **nastavení** > **integrace**modulu EMM a vyberte kartu **EMM Connect** . použijte rozevírací seznam dodavatel modulu *EMM* a vyberte možnost *Microsoft Intune*.

   ![Výběr Intune](./media/wandera-mtd-connector-integration/set-up-intune-in-radar.png)

5. Vyberte **udělit oprávnění** k otevření připojení k portálu Intune. Přihlaste se pomocí přihlašovacích údajů správce Intune, zaškrtněte políčko a pak **přijměte** žádost o oprávnění.  

   ![Přijmout oprávnění](./media/wandera-mtd-connector-integration/permissions.png) 

6. Wandera dokončí připojení a vrátí se do konzoly pro správu PAPRSKů. Opakujte postup pro **udělení** přístupu k dalším konfiguracím podle potřeby.  

   ![Integrace a oprávnění](./media/wandera-mtd-connector-integration/integrations-and-permissions.png) 

7. V konzole PAPRSKů zkopírujte název skupiny **SyncOnly** , která se zobrazuje pod **popiskem EMM**. Tento název použijete ke konfiguraci skupiny v Intune pro synchronizaci s Wandera.

   ![Skupina synchronizace](./media/wandera-mtd-connector-integration/sync-group-name.png) 

8. Vraťte se do konzoly [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) a upravte konektor Wandera MTD. Nastavte přepínač k dispozici na **zapnuto**a **uložte** konfiguraci.  

   ![Povolit Wandera](./media/wandera-mtd-connector-integration/enable-wandera.png) 

Intune a Wandera jsou teď připojené.  

## <a name="configure-the-wandera-applications-and-synchronization-group"></a>Konfigurace aplikací a skupin synchronizace Wandera  
K nasazení Wandera přidáte mobilní aplikace Wandera pro platformy, které používáte (iOS a Android), do Intune a přiřadíte je ke konkrétní skupině pro synchronizaci. skupina *SyncOnly* 

Tento postup vás provede následujícími oddíly a postupy.

Další informace o tomto procesu z Wandera se přihlaste k Wandera [paprsku](https://radar.wandera.com/login). Přejít na **nastavení** > **Integrace modulu EMM**, vyberte kartu **Push aplikace** a pak vyberte **Microsoft Intune**. Karta nabízených oznámení aplikací se aktualizuje pomocí pokynů, které jsou specifické pro Intune.  

### <a name="add-the-wandera-apps"></a>Přidání aplikací Wandera  
Vytvořte klientské aplikace v Intune, abyste mohli nasadit aplikaci Wandera na zařízení s Androidem a iOS. Další informace najdete v tématu [Přidání aplikací MTD](mtd-apps-ios-app-configuration-policy-add-assign.md) pro postupy a vlastní podrobnosti specifické pro aplikace Wandera.  

Po vytvoření aplikací se sem vraťte, abyste vytvořili skupinu synchronizace a přiřadíte aplikace.  


### <a name="create-the-synchronization-group-and-assign-the-apps"></a>Vytvořte synchronizační skupinu a přiřaďte aplikace.

1. Získá název skupiny **SyncOnly** , která se zobrazí pod **popiskem EMM** v konzole Wandera paprsky. Tento název jste mohli uložit během kroku 7 při [povolování podpory Wandera v Intune](#enable-support-for-wandera-in-intune). Použijte tento název jako název skupiny v Intune for Wandera Synchronization.  

2. V konzole Intune klikněte na **skupiny** a vyberte **Nová skupina**. Chcete-li nakonfigurovat skupinu synchronizace pro použití v Wandera, zadejte následující:
   - **Typ skupiny**: **zabezpečení**
   - **Název skupiny**: zadejte název **SyncOnly** , který jste získali z konzoly pro správu Wandera pro paprsky.

   ![Konfigurovat skupinu synchronizace](./media/wandera-mtd-connector-integration/configure-sync-group.png)

3. Vyberte **členy** a přiřaďte skupiny, které zahrnují zařízení s Androidem a iOS, která chcete používat s Wandera.

4. Vyberte **vytvořit** a uložte skupinu.

Další informace najdete v tématu [nasazení aplikací](../apps/apps-deploy.md) .

### <a name="assign-the-wandera-apps-to-the-synchronization-group"></a>Přiřaďte aplikace Wandera ke skupině synchronizace.  
Pro aplikaci Wandera, kterou jste vytvořili pro iOS a Android, opakujte následující postup.

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) a přečtěte si **klientské aplikace** > **aplikace** a vyberte aplikaci Wandera.  

2. Vyberte **přiřazení** a pak **Přidat skupinu**.  

3. V podokně *Přidat skupinu* pro *Typ přiřazení* vyberte **požadované**.

4. Vyberte **zahrnuté skupiny**a pak **Vyberte skupiny, které chcete zahrnout**. Určete skupinu, kterou jste vytvořili pro Wandera synchronizaci, a potom klikněte na **vybrat** > **OK** > **OK**. Kliknutím na **Uložit** dokončete přiřazení skupiny.  
 

## <a name="next-steps"></a>Další kroky  
Teď, když jste nakonfigurovali integraci, můžete začít konfigurovat zásady, nastavit pokročilý podmíněný přístup a zobrazovat sestavy v konzole pro správu Wandera. Další informace o správě a konfiguraci Wandera najdete v tématu [průvodce Začínáme Support Center](https://radar.wandera.com/?return_to=https://wandera.force.com/Customer/s/getting-started) v dokumentaci k Wandera.  
 