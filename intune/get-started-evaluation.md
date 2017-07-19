---
title: "Začínáme s Intune"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef58e46118a0a44609abba5de4986b5a1526a151
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2017
---
# <a name="what-is-microsoft-intune"></a>Co je Microsoft Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

![Microsoft Intune na portálu Azure Portal](./media/generic-intune-azure.png)

Microsoft Intune je jednou z nejnovějších služeb Azure. Nabízí nástroje pro správu podnikových mobilních zařízení, počítačů a [pravidelně aktualizovaných](whats-new.md) aplikací. Kromě moderní konzoly Azure můžete také použít klasickou konzolu Intune. Klasická konzola představuje první verzi Intune, kde stále můžete [spravovat počítače s Windows a softwarovým klientem Intune](/intune-classic/deploy-use/pc-management-comparison.md). Klasický portál vychází z technologie Silverlight a používá se pro menší počet úkolů. Všechno ostatní, včetně správy mobilních zařízení a aplikací, se provádí na portálu Azure Portal. Na začátku vás průvodce provede základními kroky, které jsou podmínkou úspěšného používání Intune na portálu Azure Portal.

![Okno Nápověda a podpora, které je k dispozici na konci seznamu akcí na levém bočním panelu Intune.](./media/intune-azure-help-support-closeup.png)

## <a name="what-does-intune-in-the-azure-portal-provide"></a>Co nabízí Intune na portálu Azure Portal?

Intune na portálu Azure Portal nabízí následující možnosti:

* Integrovaná konzola pro všechny [komponenty EMS (Enterprise Mobility + Security)](https://docs.microsoft.com/enterprise-mobility-security)
* Konzola HTML založená na webových standardech, která podporuje [moderní webové prohlížeče](supported-devices-browsers.md)
* [Skupiny Azure Active Directory](groups-get-started.md) pro zajištění kompatibility se všemi aplikacemi Azure
* Automatizace prostřednictvím rozhraní [Microsoft Graph API](intune-graph-apis.md)

## <a name="prerequisites"></a>Požadavky

Než začnete, musíte mít aktivovaný účet správce Intune a účet tenanta. Tyto účty si můžete zaregistrovat [zde](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20). Stávající odběratelé také mohou k těmto činnostem použít živého tenanta. Pracujte jenom na testovacích zařízeních!

Další podmínkou dokončení všech úkolů v tomto průvodci je, že musíte být globálními správci organizace.
