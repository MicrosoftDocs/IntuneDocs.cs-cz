---
title: Protokoly auditu pro aktivity v Intune
description: "Přečtěte si, jak kontrolovat protokoly auditu se zaznamenanými aktivitami Intune."
keywords: 
author: dougeby
manager: dougeby
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
ms.openlocfilehash: 9f514e6d2dec268efe99f682bc3ef4e63ec53c02
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2018
---
# <a name="audit-logs-for-intune-activities"></a>Protokoly auditu pro aktivity v Intune
Protokoly auditu obsahují zaznamenané aktivity, které v Microsoft Intune generují změnu. Vytváření, aktualizace (úpravy), odstraňování, přiřazování akcí nebo vzdálené úlohy generují události protokolu, které můžete kontrolovat. V protokolech auditu můžete kontrolovat většinu úloh Intune. Auditování je ve výchozím nastavení povolené pro všechny zákazníky a nedá se zakázat. Události auditu se začaly zaznamenávat od data vydání této součásti v prosinci 2017. Dřívější události nejsou dostupné.

## <a name="who-can-access-the-data"></a>Kdo má k těmto datům přístup?
Protokoly auditu mohou kontrolovat uživatelé s tímto oprávněním:
- Globální správce
- Správce služby Intune
- Správci s přiřazenou rolí Intune a oprávněními pro **data auditu** - **čtení**.

## <a name="audit-logs-for-intune-workloads"></a>Protokoly auditu pro úlohy Intune
Ve skupině Monitorování můžete kontrolovat protokoly auditu o každé úloze Intune.  
1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte úlohu, jejíž protokoly auditu chcete kontrolovat.
4. Ve skupině **Monitorování** zvolte u úlohy **Protokoly auditu**.

## <a name="review-audit-events"></a>Kontrola událostí auditu
![Protokoly událostí](./media/monitor-audit-logs.png "Protokoly událostí")

Protokol událostí zobrazí výchozí seznam s následujícími položkami:    

- Datum a čas výskytu
- Iniciátor (actor)
- Aktivita
- Cíle
- Kategorie
- Stav

Když v seznamu kliknete na položku, získáte o ní všechny dostupné informace.

![Protokoly auditu](./media/monitor-audit-log-detail.png "Protokoly auditu")

> [!Note]    
> V oddílu **Iniciátor (actor)** jsou v protokolu auditu informace o uživateli, který aktivitu provedl, a o tom, odkud byla provedena. Pokud aktivitu Intune provedete na webu Azure Portal, bude ve sloupci **Aplikace** vždy uvedeno, že jde o **rozšíření portálu Microsoft Intune** a jako **ID aplikace** se vždy použije stejný identifikátor GUID. 
>    
> Oddíl **Cíle** může obsahovat více změněných cílů a vlastností.  


## <a name="filter-audit-events"></a>Filtrování událostí auditu
Každá úloha má položku nabídky, která předem vyfiltruje kategorii událostí auditu spojených s tímto oknem. Samostatná volba ve filtru umožňuje změnit kategorii na jinou. V dané kategorii také můžete změnit podrobnosti zaznamenané akce. Hledat můžete podle UPN (například uživatel, který akci provedl). Filtr časového rozsahu nabízí tyto možnosti: 24 hodin, 7 dní nebo 30 dní. Ve výchozím nastavení se zobrazují události auditu za posledních 30 dní.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Použití rozhraní API služby Graph k načtení událostí auditu
Podrobnosti o použití rozhraní API služby Graph k načtení událostí auditu až za jeden rok najdete v článku o [vytvoření seznamu událostí auditu s použitím objektů auditEvent](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list).