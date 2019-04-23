---
title: Auditovat změny a události v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Přečtěte si, jak kontrolovat protokoly auditu se zaznamenanými aktivitami Microsoft Intune.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 93072ba4730de0252f54d93fa1169062d496ce38
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61513166"
---
# <a name="use-audit-logs-to-track-and-monitor-events-in-microsoft-intune"></a>Použití protokolů auditu ke sledování a sledování událostí v Microsoft Intune

Protokoly auditu obsahují zaznamenané aktivity, které v Microsoft Intune generují změnu. Vytvoření, aktualizace (úpravy), odstranit, přiřadit a akce se vzdáleným vytvoření událostí auditu, které správce může zkontrolovat pro většinu úloh Intune. Ve výchozím nastavení je auditování povoleno pro všechny zákazníky. Nelze zakázat.

> [!NOTE]
> Události auditu spustit záznam na vydání funkce. prosince 2017. Dřívější události nejsou k dispozici.

## <a name="who-can-access-the-data"></a>Kdo má k těmto datům přístup?

Protokoly auditu mohou kontrolovat uživatelé s tímto oprávněním:

- Globální správce
- Správce služby Intune
- Správci s přiřazenou rolí Intune a oprávněními pro **data auditu** - **čtení**.

## <a name="audit-logs-for-intune-workloads"></a>Protokoly auditu pro úlohy Intune

Můžete kontrolovat protokoly auditu ve skupině monitorování o každé úloze Intune:

1. V [webu Azure portal](https://portal.azure.com/)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Zvolte úlohu, kterou chcete kontrolovat protokoly auditu. Vyberte například **zařízení**.
3. V části **monitorování**, zvolte **protokoly auditu**.

## <a name="route-logs-to-azure-monitor"></a>Směrování protokolů do Azure monitoru

Protokoly auditu a provozní protokoly je možné také směrovat do Azure monitoru. V **protokoly auditu**vyberte **exportovat nastavení dat**:

![Export protokolů dat do Azure monitoru výběrem možnosti Export dat nastavení v Intune](./media/audit-logs-export-data-settings.png)

Další informace o této funkci najdete v tématu [odeslat data protokolů do služby storage, služby event hubs nebo protokolování analytics](review-logs-using-azure-monitor.md).

## <a name="review-audit-events"></a>Kontrola událostí auditu

![Zvolte protokoly auditu v Intune, chcete-li zobrazit akce a data, kdy došlo k událostem](./media/monitor-audit-logs.png "protokoly auditu")

Protokol událostí zobrazí výchozí seznam s následujícími položkami:

- Datum a čas výskytu
- Iniciátor (actor)
- Název aplikace
- Aktivita
- Cíle
- Category
- Stav

Chcete-li zobrazit podrobnější informace o události, vyberte položku v seznamu:

![Získat podrobnější informace, na který nebyla, které v auditu protokoly do Intune](./media/monitor-audit-log-detail.png "podrobnosti protokolu auditu")

> [!NOTE]
> **Iniciátor (actor)** obsahuje informace o kdo spustil úlohu a ve kterém byl spuštěn. Například při spuštění aktivity v Intune na webu Azure Portal, pak **aplikace** vždy uvedeno **rozšíření portálu Microsoft Intune** a **ID aplikace** vždy používá stejný identifikátor GUID.
> 
> **Cíle** části je uveden seznam více cílů a vlastnosti, které byly změněny.  

## <a name="filter-audit-events"></a>Filtrování událostí auditu

Každá úloha má položku nabídky, která předem vyfiltruje kategorii událostí auditu spojených s tímto podoknem. Samostatná volba ve filtru umožňuje změnit kategorii na jinou. V dané kategorii také můžete změnit podrobnosti zaznamenané akce. Můžete vyhledávat podle UPN, jako je například uživatel, který akci provedl. Filtr časového rozsahu nabízí tyto možnosti: 24 hodin, 7 dní nebo 30 dní. Ve výchozím nastavení se zobrazí za posledních 30 dní událostí auditu.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Použití rozhraní API služby Graph k načtení událostí auditu

Podrobnosti o použití rozhraní graph API k získání událostí auditu až jednoho roku, naleznete v tématu [seznamu použitím objektů Auditevent](https://docs.microsoft.com/graph/api/intune-auditing-auditevent-list?view=graph-rest-1.0).

## <a name="next-steps"></a>Další postup

[Odeslat data protokolů do služby storage, služby event hubs nebo protokolování analytics](review-logs-using-azure-monitor.md).

[Kontrola protokolů ochrany aplikace klient](app-protection-policy-settings-log.md).
