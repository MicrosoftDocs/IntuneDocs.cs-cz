---
title: Nastavení integrace Sophos Mobile s Intune
titleSuffix: Intune on Azure
description: Jak nastavit řešení Sophos Mobile v Microsoft Intune pro řízení přístupu mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: eeddbf39093210e640125db3be6ddd6bcad7d59b
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66045004"
---
# <a name="integrate-sophos-mobile-with-intune"></a>Integrace Sophos Mobile s Intune  

Proveďte následující kroky pro integraci řešení Sophos Mobile Threat Defense s Intune.  

## <a name="before-you-begin"></a>Před zahájením  

Před zahájením procesu integrace Sophos Mobile s Intune, ujistěte se, že máte následující:  
- Odběr služby Microsoft Intune  
- Přihlašovací údaje správce Azure Active Directory pro udělení následujících oprávnění:  
  - Přihlášení a čtení profilu uživatele  
  - Přístup k adresáři jako přihlášený uživatel  
  - Čtení dat z adresáře  
  - Odeslání informací o zařízení do Intune  
- Přihlašovací údaje správce pro přístup ke konzole pro správu Sophos Mobile.  


### <a name="sophos-mobile-app-authorization"></a>Autorizace Sophos mobilní aplikace  
  
Proces autorizace aplikace Sophos Mobile takto:  
- Povolte službě Sophos Mobile informací týkajících se stavu zařízení zpět do Intune.  
- Sophos Mobile se synchronizuje s členstvím skupiny registrace Azure AD a naplnit databáze zařízení.  
- Povolte mobilní zařízení Sophos konzoly pro správu k použít Azure AD jednotné přihlašování (SSO).  
- Povolte Sophos mobilní aplikace k přihlášení pomocí jednotného přihlašování k Azure AD.  


## <a name="to-set-up-sophos-mobile-integration"></a>Postup nastavení integrace Sophos Mobile  

1. Přihlaste se k [webu Azure portal]( https://portal.azure.com/)přejděte **Intune** > **dodržování předpisů zařízením** > **Mobile Threat Defense** > a vyberte **přidat**.  
2. Na **konektoru přidat** stránku, použijte rozevírací seznam a vyberte **Sophos**. A pak vyberte **vytvořit**.  
3. Vyberte odkaz *otevřete konzoly pro správu Sophos*.  
4. Přihlaste se k [konzoly pro správu Sophos](https://central.sophos.com/) pomocí svých přihlašovacích údajů Sophos.  
5. Přejděte na **Mobile** > **nastavení** > **nastavení** > **Sophos nastavení**.  
6. Na **Sophos nastavení** stránky, vyberte **Intune MTD** kartu.  
   ![Sophos instalace](./media/sophos-mtd-connector-integration/sophos-setup.png) 
 
7. Vyberte **svázat**a pak vyberte **Ano**. Sophos připojuje k Intune a vyžaduje, abyste se přihlásili k vašemu předplatnému Intune. 
8. V okně ověřování Microsoft Intune zadejte svoje přihlašovací údaje Intune a **přijmout** požadavek na oprávnění pro *vlákna Sophos mobilními*.  
   ![Ověřování Intune](./media/sophos-mtd-connector-integration/intune-authentication.png)

9. Na **Sophos nastavení** stránce **Uložit** dokončete konfigurace pro Intune:  
   ![Uložit nastavení Sophos](./media/sophos-mtd-connector-integration/save-sophos-configuration.png)  

1. Jakmile se objeví zpráva **Successful Integration** (integrace proběhla úspěšně), je integrace hotová.  
1. V konzole Intune je teď Sophos k dispozici.  


## <a name="next-steps"></a>Další kroky  
[Konfigurace Sophos klientských aplikací](mtd-apps-ios-app-configuration-policy-add-assign.md)
