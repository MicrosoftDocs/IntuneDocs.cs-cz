---
title: Auditování změn a událostí v Microsoft Intune – Azure | Microsoft Docs
description: Přečtěte si, jak kontrolovat protokoly auditu se zaznamenanými aktivitami Microsoft Intune.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: b4be1755a07e6ec304edb7bceba8041d5b58263e
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72510000"
---
# <a name="use-audit-logs-to-track-and-monitor-events-in-microsoft-intune"></a>Sledování a monitorování událostí v Microsoft Intune pomocí protokolů auditu

Protokoly auditu obsahují záznam aktivit, které generují změnu v Microsoft Intune. Vytváření, aktualizace (úpravy), odstraňování, přiřazování a vzdálené akce všechny události vytváření auditu, které můžou správci zkontrolovat pro většinu úloh Intune. Ve výchozím nastavení je auditování povolené pro všechny zákazníky. Nedá se zakázat.

> [!NOTE]
> Události auditu se zahájily zaznamenáváním do vydání funkce prosince 2017. Předchozí události nejsou k dispozici.

## <a name="who-can-access-the-data"></a>Kdo má k těmto datům přístup?

Protokoly auditu mohou kontrolovat uživatelé s tímto oprávněním:

- Globální správce
- Správce služby Intune
- Správci s přiřazenou rolí Intune a oprávněními pro **data auditu** - **čtení**.

## <a name="audit-logs-for-intune-workloads"></a>Protokoly auditu pro úlohy Intune

Protokoly auditu můžete zkontrolovat ve skupině monitorování pro každou úlohu Intune:

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte úlohu, kterou chcete zkontrolovat v protokolech auditu. Vyberte například **zařízení**.
3. V části **monitorování**vyberte **protokoly auditu**.

## <a name="route-logs-to-azure-monitor"></a>Směrování protokolů do Azure Monitor

Protokoly auditu a provozní protokoly je také možné směrovat na Azure Monitor. V **protokolech auditu**vyberte **nastavení exportovat data**:

![Export dat protokolu do služby Azure monitor výběrem možnosti Exportovat data v Intune](./media/monitor-audit-logs/audit-logs-export-data-settings.png)

Další informace o této funkci najdete v tématu [odeslání dat protokolu do úložiště, centra událostí nebo Log Analytics](review-logs-using-azure-monitor.md).

## <a name="review-audit-events"></a>Kontrola událostí auditu

![V Intune vyberte protokoly auditu, kde se zobrazí akce a datum, kdy došlo k událostem.](./media/monitor-audit-logs/monitor-audit-logs.png "Protokoly auditu")

Protokol událostí zobrazí výchozí seznam s následujícími položkami:

- Datum a čas výskytu
- Iniciátor (actor)
- Název aplikace
- Aktivita
- Cíle
- Category
- Stav

Chcete-li zobrazit konkrétnější informace o události, vyberte položku v seznamu:

![Získat konkrétnější informace o tom, kdo z protokolů auditu v Intune pracoval](./media/monitor-audit-logs/monitor-audit-log-detail.png "Podrobnosti protokolu auditu")

> [!NOTE]
> **Iniciované uživatelem (actor)** obsahuje informace o tom, kdo úlohu spustil a kde byla spuštěna. Pokud například spustíte aktivitu v Intune v Azure Portal, **aplikace** vždy vypíše seznam **Microsoft Intune portálu** a **ID aplikace** vždy používá stejný identifikátor GUID.
> 
> V části **cíle (y)** je uveden seznam více cílů a vlastností, které byly změněny.  

## <a name="filter-audit-events"></a>Filtrování událostí auditu

Každá úloha má položku nabídky, která předem vyfiltruje kategorii událostí auditu spojených s tímto podoknem. Samostatná volba ve filtru umožňuje změnit kategorii na jinou. V dané kategorii také můžete změnit podrobnosti zaznamenané akce. Můžete hledat podle hlavního názvu uživatele (UPN), jako je například uživatel, který tuto akci provedl. Filtr časového rozsahu nabízí tyto možnosti: 24 hodin, 7 dní nebo 30 dní. Ve výchozím nastavení se zobrazí posledních 30 dnů událostí auditu.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Použití rozhraní API služby Graph k načtení událostí auditu

Podrobnosti o používání rozhraní Graph API k získání až jednoho roku událostí auditu najdete v článku [auditEvents](https://docs.microsoft.com/graph/api/intune-auditing-auditevent-list?view=graph-rest-1.0).

## <a name="next-steps"></a>Další kroky

[Odešlete data protokolu do úložiště, centra událostí nebo Log Analytics](review-logs-using-azure-monitor.md).

[Kontrola protokolů ochrany klientských aplikací](../apps/app-protection-policy-settings-log.md).
