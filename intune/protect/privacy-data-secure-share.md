---
title: Zabezpečení a sdílení dat v Intune
titleSuffix: Microsoft Intune
description: Přečtěte si, jak jsou osobní údaje zabezpečené a sdílené v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 68921fd6-5f50-456c-a3af-83d7bc4b134b
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 53480b7a2e008af46f4f8929cc6321e10b042b33
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306749"
---
# <a name="data-security-and-sharing-in-intune"></a>Zabezpečení a sdílení dat v Intune


## <a name="data-security"></a>Zabezpečení dat

Microsoft Intune je klíčovou součástí nabídky Microsoft Enterprise mobility a služby Security Suite. Pro podporu [strategie správy dat](https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx)se všechny cloudové služby Microsoftu vyvíjely s využitím [Microsoft ochrany osobních údajů](https://www.microsoft.com/en-us/trustcenter/privacy) a [zabezpečení Microsoftu](https://www.microsoft.com/en-us/trustcenter/security/) .  

Microsoft Intune se řídí stejnými technickými a organizačními mírami, které týmy služby Microsoft Azure využívají k zabezpečení před procesy porušení dat.

Další informace najdete na [portálu vztahu důvěryhodnosti služby](https://www.microsoft.com/en-us/TrustCenter/stp).

Intune používá techniky pro minimalizaci dat, jako např.

- agregovat
- volitelné shromažďování dat pro některé funkce
- data provedená méně přesná nebo citlivá

Intune také využívá techniky, jako je zabezpečení RBAC a JiT, pro incidenty podpory k zajištění ochrany dat ve výchozím nastavení. 

### <a name="data-breach-reporting"></a>Generování sestav o porušení dat

Když se zjistí bezpečnostní incident (CRSI) zákazníka, sdělí se zákazníkům. Tento proces zahrnuje práci s týmem Microsoft O365 k oznamování oznámení o porušení pro všechny zákazníky v Microsoft O365 pomocí Intune.

## <a name="data-sharing"></a>Sdílení dat

Když správci tenanta zapnou určitou funkci (například Apple Program registrace zařízení), Microsoft Intune získá souhlas správce pro sdílení dat s příslušnými třetími stranami. V takových případech může Intune sdílet osobní údaje s:

- Třetí strany fungují jako zástupci Microsoftu.
- Třetí strany nefungují jako zástupci Microsoftu, ale jenom když oprávnění k tomu udělí správci tenanta explicitně.

Všechny třetí strany fungující jako Microsoft agenti jsou součástí [seznamu subdodavatelů služeb Online Services](https://aka.ms/Online_Serv_Subcontractor_List).

Sdílení dat s těmito entitami se provádí v rámci podpory zákazníků a technické podpory, údržby služeb a dalších operací.

Smlouva tenanta s třetí stranou řídí osobní údaje Intune držené v rámci služby třetí strany. Také udělí Intune oprávnění k přenosu dat do služby třetí strany.  

Informace o datech, která se sdílí s určitými třetími stranami, najdete v následujících článcích:
- [Data Intune odesílají společnosti Apple](data-intune-sends-to-apple.md)
- [Data Intune odesílají do Google](data-intune-sends-to-google.md)
- [Data Apple odesílá do Intune](data-apple-sends-to-intune.md)
- [Data, která Google odesílá do Intune](data-google-sends-to-intune.md)
- [Data Jamf pro odesílá do Intune.](data-jamf-sends-to-intune.md)

### <a name="system-center-configuration-manager-data-sharing"></a>Sdílení dat System Center Configuration Manager

Microsoft Intune nesdílí žádná data s System Center Configuration Manager. System Center Configuration Manager je místní produkt nasazený, spravovaný a provozovaný přímo zákazníkem. Data o využití a diagnostika shromažďovaná nástrojem Configuration Manager jsou jenom pro zlepšení prostředí pro instalaci, kvality a zabezpečení budoucích verzí.

Další informace najdete v tématu [Diagnostika a data o využití pro SCCM](https://docs.microsoft.com/sccm/core/plan-design/diagnostics/diagnostics-and-usage-data). 


## <a name="next-steps"></a>Další kroky

Zjistěte [, jak zobrazit a opravit](privacy-data-view-correct.md) osobní údaje v Intune.
