---
title: Použití sestav Update Compliance pro aktualizace Windows v Microsoft Intune
titleSuffix: Microsoft Intune
description: Pomocí OMS Update Compliance můžete zobrazit data sestavy pro aktualizace Windows, které nasazujete v Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 55fa1109fde57e3104c8bb15e1f45761d661c735
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508727"
---
# <a name="intune-compliance-reports-for-updates"></a>Sestavy dodržování předpisů v Intune pro aktualizace
Když použijete Intune k nasazení služby Windows Update na zařízení s Windows 10, zobrazí se podrobnosti o kompatibilitě aktualizací pomocí Intune nebo bezplatného řešení s názvem *Update Compliance*, které je součástí Microsoft Operations Management Suite (OMS).

## <a name="use-intune"></a>Použití Intune
Chcete-li zkontrolovat sestavu zásad pro stav nasazení pro aktualizační kanály Windows 10, které jste nakonfigurovali: 
1. Přihlaste se k [portálu Azure](https://portal.azure.com/).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Aktualizace softwaru** > **Přehled**. Uvidíte obecné informace o stavu všech aktualizačních kanálů, které jste přiřadili.
4. Otevřete jednu z těchto sestav:  

   **Pro všechny aktualizační kanály nasazení**:
   1. V podokně **Aktualizace softwaru** > **Aktualizační kanály Windows 10**
   2. V **sekci Monitorování** zvolte **Stav nasazení podle kruhu aktualizace**.  

   **Pro konkrétní aktualizační kanály nasazení**:  

   1. V podokně **Aktualizace softwaru** > **Aktualizační kanály Windows 10** zvolte aktualizační kanál nasazení, který chcete zkontrolovat.  
   2. Pokud chcete zobrazit podrobnější informace o aktualizačním kanálu, v sekci **Monitorování** zvolte z těchto sestav:  
      - **Stav zařízení**  
      - **Stav uživatele**  

## <a name="use-update-compliance"></a>Použít Update Compliance
Uvádění Windows 10 Update můžete monitorovat pomocí [Update Compliance](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor)a řešení Windows Analytics. Update Compliance k dispozici prostřednictvím Azure Portal a jsou dostupné zdarma pro zařízení, která splňují [požadavky](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites).  

Když použijete toto řešení, nasadíte komerční ID do libovolného zařízení s Windows 10 spravovaných pomocí Intune, pro které chcete ohlásit dodržování předpisů pro aktualizace.  

V konzole Intune můžete pomocí nastavení OMA-URI vlastní zásady nakonfigurovat komerční ID. Podrobnosti najdete v článku [Nastavení zásad Intune pro zařízení s Windows 10 v Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).  

Cesta OMA-URI (s rozlišováním velkých a malých písmen) pro konfiguraci komerčního ID je: *./VENDOR/MSFT/DMCLIENT/Provider/MS DM Server/CommercialID*  

V nastavení **Přidat nebo upravit nastavení OMA-URI** můžete použít třeba následující hodnoty:
- **Název nastavení**: Komerční ID pro analýzu Windows
- **Popis nastavení**: Konfigurace komerčního ID pro řešení pro analýzu Windows
- **OMA-URI** (rozlišuje velká a malá písmena): *./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID*
- **Datový typ:** Řetězec
- **Hodnota**: \<použít identifikátor GUID zobrazený na kartě telemetrie Windows v pracovním prostoru OMS >
 
> [!NOTE]  
> Podrobnosti o MS DM Serveru najdete v tématu [Poskytovatel konfiguračních služeb DMClient]( https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="next-steps"></a>Další kroky
[Správa softwarových aktualizací v Intune](windows-update-for-business-configure.md)

