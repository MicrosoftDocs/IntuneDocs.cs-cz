---
title: Použití sestav dodržování předpisů pro aktualizace pro aktualizace Windows v Microsoft Intune | Dokumentace Microsoftu
description: Chcete-li zobrazit data sestavy pro aktualizace Windows můžete nasadit pomocí Intune pomocí OMS informace o kompatibilitě.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/12/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa549e90e9c0066ae10772728f097b5951284959
ms.sourcegitcommit: e262b0ad8df610e25eb9421b9ebc2673bcf1020e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/11/2019
ms.locfileid: "55986953"
---
# <a name="intune-compliance-reports-for-updates"></a>Sestavy dodržování předpisů Intune pro aktualizace
Při použití Intune k nasazení Windows update pro zařízení s Windows 10, zobrazení podrobností o dodržování předpisů pro aktualizace pomocí Intune nebo pomocí bezplatného řešení volána *Update Compliance*, která je součástí sady Microsoft Operations Management Suite (OMS).

## <a name="use-intune"></a>Pomocí Intune
Chcete-li zkontrolovat sestavu zásad pro aktualizační okruhy Windows 10, které jste nakonfigurovali stav nasazení: 
1. Přihlaste se k webu [Azure Portal](https://portal.azure.com/).
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

## <a name="use-update-compliance"></a>Použijte informace o kompatibilitě
Zavádění aktualizací Windows 10 můžete sledovat pomocí [Update Compliance](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor), řešení Windows Analytics. Dodržování předpisů pro aktualizace je dostupná prostřednictvím webu Azure portal a je k dispozici zdarma pro zařízení, která splňují jeho [požadavky](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites).  

Při použití tohoto řešení můžete nasadit komerční ID k některému z Intune spravovat zařízení s Windows 10 pro které chcete sestavu dodržování předpisů pro aktualizace.  

V konzole Intune použít nastavení OMA-URI vlastní zásady pro konfiguraci komerčního ID. Podrobnosti najdete v článku [Nastavení zásad Intune pro zařízení s Windows 10 v Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).  

Cesta OMA-URI (rozlišuje velikost písmen) pro konfiguraci komerčního ID je: *./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID*  

V nastavení **Přidat nebo upravit nastavení OMA-URI** můžete použít třeba následující hodnoty:
- **Název nastavení**: Komerční ID pro analýzu Windows
- **Popis nastavení**: Konfigurace řešení pro komerční ID pro analýzu Windows
- **OMA-URI** (rozlišuje velikost písmen): *./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID*
- **Datový typ**: Řetězec
- **Hodnota**: \<Identifikátor GUID zobrazený na kartě Telemetrie Windows v pracovním prostoru OMS použít >
 
> [!NOTE]  
> Podrobnosti o MS DM Serveru najdete v tématu [Poskytovatel konfiguračních služeb DMClient]( https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="next-steps"></a>Další postup
[Správa softwarových aktualizací v Intune](windows-update-for-business-configure.md)

