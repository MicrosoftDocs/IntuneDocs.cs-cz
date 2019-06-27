---
title: Nastavení integrace ochrany před internetovými útoky Wandera Mobile s Intune
titleSuffix: Intune on Azure
description: Jak nastavit řešení ochrany před internetovými útoky Wandera mobilní zařízení pomocí Microsoft Intune pro řízení přístupu mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 76d5ca2d1f1c23a5d5aef4af3904fc8d9c76e947
ms.sourcegitcommit: 6bba9f2ef4d1ec699f5713a4da4f960e7317f1cd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2019
ms.locfileid: "67407723"
---
# <a name="integrate-wandera-mobile-threat-protection-with-intune"></a>Integrace ochrany před internetovými útoky Wandera Mobile s Intune  

Proveďte následující kroky pro integraci řešení Wandera Mobile Threat Defense s Intune.  

## <a name="before-you-begin"></a>Před zahájením  

Před zahájením procesu integrace Wandera s Intune, ujistěte se, že jsou splněné následující požadavky:
- Odběr služby Microsoft Intune  
- Přihlašovací údaje správce Azure Active Directory pro udělení následujících oprávnění:  
  - Přihlášení a čtení profilu uživatele  
  - Přístup k adresáři jako přihlášený uživatel  
  - Čtení dat z adresáře  
  - Odeslání informací o zařízení do Intune  

- Wandera předplatného:
  - Jeden nebo více Wandera účtů, které jsou licencované pro připojení EMM  
  - Účet s oprávněními superuživatele správce v Wandera  
 
### <a name="wandera-mobile-threat-defense-app-authorization"></a>Autorizace aplikace Wandera Mobile Threat Defense  

Proces autorizace aplikace Wandera Mobile Threat Defense:  
- Povolte službě Wandera Mobile Threat Defense informací týkajících se stavu zařízení zpět do Intune.  
- Wandera synchronizuje s členstvím skupiny registrace Azure AD a naplnit databáze zařízení.  
- Povolit na portálu pro správu této možnosti taky PŘEMÝŠLÍTE Wandera používat Azure AD jednotné přihlašování (SSO).  
- Povolte aplikaci Wandera Mobile Threat Defense pro přihlášení pomocí jednotného přihlašování Azure AD.  


## <a name="set-up-wandera-mobile-threat-defense-integration"></a>Nastavení integrace Wandera Mobile Threat Defense  
Nastavit *EMM připojení* Wandera vyžaduje jednorázovou konfiguraci procesu, který dokončíte v Intune a Wandera konzol. Proces konfigurace trvá přibližně 15 minut. Může dokončení konfigurace bez koordinace s vaším účtem technické Wandera nebo zástupce podpory.  

### <a name="enable-support-for-wandera-in-intune"></a>Povolení podpory pro Wandera v Intune
1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) a přejděte na **dodržování předpisů zařízením** > **Mobile Threat Defense** > a vyberte **přidat**.

2. Na **konektoru přidat** stránku, použijte rozevírací seznam a vyberte **Wandera**. A pak vyberte **vytvořit**.  

3. V podokně Mobile Threat Defense, vyberte **Wandera** konektoru MTD ze seznamu konektorů a otevřete *upravit konektor* podokně. Vyberte **otevřete konzoly pro správu Wandera** otevřete [této možnosti taky PŘEMÝŠLÍTE](https://radar.wandera.com/login), Wandera konzoly pro správu a přihlaste se. 

4. Přejděte v konzole Wandera **nastavení** > **EMM Integration**a vyberte **EMM připojení** kartu. Použití *EMM dodavatele* rozevíracího seznamu a vyberte *Microsoft Intune*.

   ![Vyberte Intune](media/wandera-mtd-connector-integration/set-up-intune-in-radar.png)

5. Vyberte **udělit oprávnění** k otevření připojení k portálu Intune. Přihlaste se pomocí svých přihlašovacích údajů správce Intune, zaškrtněte políčko a potom **přijmout** požadavek na oprávnění.  

   ![Oprávnění](media/wandera-mtd-connector-integration/permissions.png) 

6. Wandera dokončení připojení a vrátíte se do konzoly pro správu této možnosti taky PŘEMÝŠLÍTE. Opakujte postup **udělení** přístup pro další konfigurace, podle potřeby.  

   ![Integrace a oprávnění](media/wandera-mtd-connector-integration/integrations-and-permissions.png) 

7. V konzole této možnosti taky PŘEMÝŠLÍTE, zkopírujte název **SyncOnly** skupinu, která se zobrazí pod **EMM popisek**. Tento název budete používat k synchronizaci se sadou Wandera konfigurace skupiny v Intune.

   ![Integrace a oprávnění](media/wandera-mtd-connector-integration/sync-group-name.png) 

8. Vraťte se [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) konzoly a upravit Wandera konektoru MTD. Nastavte dostupné přepíná na **na**a **Uložit** konfigurace.  

   ![Povolit Wandera](media/wandera-mtd-connector-integration/enable-wandera.png) 

Intune a Wandera připojení.  

## <a name="configure-the-wandera-applications-and-synchronization-group"></a>Nakonfigurujte Wandera aplikace a skupina synchronizace  
Pokud chcete nasadit Wandera, přidáte Wandera mobilní aplikace pro platformy (iOS a Android) pomocí Intune a přiřadit je ke konkrétní skupině synchronizace; *SyncOnly* skupiny. 

Následující části a postupy vás provede tento proces.

Další informace o tomto procesu od Wandera, přihlaste se k Wandera [této možnosti taky PŘEMÝŠLÍTE](https://radar.wandera.com/login). Přejděte na **nastavení** > **EMM Integration**, vyberte **aplikací bez vyžádání** kartu a potom vyberte **Microsoft Intune**. Aktualizace aplikací bez vyžádání kartu s pokyny, které jsou specifické pro Intune.  

### <a name="add-the-wandera-apps"></a>Přidání aplikací Wandera  
Vytváření klientských aplikací v Intune k nasazení aplikace Wandera na zařízeních s Androidem a iOS. Zobrazit [aplikací MTD přidat](mtd-apps-ios-app-configuration-policy-add-assign.md) postupy a vlastní podrobnosti specifické pro aplikace Wandera.  

Po vytvoření aplikace, vraťte se sem vytvořit skupinu synchronizace, a přiřadit aplikace.  


### <a name="create-the-synchronization-group-and-assign-the-apps"></a>Vytvořit skupinu synchronizace a přiřadit aplikace

1. Získejte název **SyncOnly** skupinu, která se zobrazí pod **EMM popisek** v PAPRSKOVÝ Wandera konzole. Tento název může mít uložit během kroku 7 při [povolení podpory pro Wandera v Intune](#enable-support-for-wandera-in-intune). Tento název jako název skupiny v Intune použijte pro Wandera synchronizace.  

2. V konzole Intune, přejděte na **skupiny** a vyberte **novou skupinu**. Zadejte následující příkaz pro konfiguraci použití Wandera skupiny synchronizace:
   - **Typ skupiny**: **Zabezpečení**
   - **Název skupiny**: Zadejte **SyncOnly** název, který jste získali z konzoly pro správu této možnosti taky PŘEMÝŠLÍTE Wandera.

   ![Konfigurovat skupinu synchronizace](media/wandera-mtd-connector-integration/configure-sync-group.png)

3. Vyberte **členy** a přiřazování skupin, které zahrnují chcete používat s Wandera zařízení s Androidem a iOS.

4. Vyberte **vytvořit** uložte skupinu.

Další informace najdete v tématu [nasazení aplikací](apps-deploy.md)

### <a name="assign-the-wandera-apps-to-the-synchronization-group"></a>Přiřazení aplikací Wandera do skupiny synchronizace  
Následující postup opakujte u Wandera aplikaci, kterou jste vytvořili pro iOS a Android.

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) a přejděte na **klientské aplikace** > **aplikace** a vyberte aplikaci Wandera.  

2. Vyberte **přiřazení** a potom **přidat skupinu**.  

3. Na *přidat skupinu* podokně pro *typ přiřazení* vyberte **vyžaduje**.

4. Vyberte **zahrnutých skupin**a potom **vybrat skupiny, které chcete zahrnout**. Zadejte skupinu, kterou jste vytvořili pro Wandera synchronizace a potom klikněte na tlačítko **vyberte** > **OK** > **OK**. Vyberte **Uložit** k dokončení přiřazení skupiny.  
 

## <a name="next-steps"></a>Další kroky  
Teď, když nakonfigurujete integraci, začněte konfiguraci zásad a nastavení podmíněného přístupu advanced. Zobrazit sestavy v konzole pro správu Wandera. Další informace o správě a konfiguraci Wandera, najdete v článku [Support Center – Příručka Začínáme](https://radar.wandera.com/?return_to=https://wandera.force.com/Customer/s/getting-started) v dokumentaci k Wandera.  
 