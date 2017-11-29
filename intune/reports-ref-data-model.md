---
title: "Datový model datového skladu | Dokumentace Microsoftu"
description: "Datový sklad Intune denně vzorkuje data, aby mohl poskytovat historický přehled průběžně se měnícího mobilního prostředí."
keywords: "Datový sklad Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 29825c58febc813c7b11072699d06106725584d3
ms.sourcegitcommit: d26930f45ba9e6292a49bcb08defb5b3f14b704b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="data-warehouse-data-model"></a>Datový model datového skladu

Datový sklad Intune denně vzorkuje data, aby mohl poskytovat historický přehled průběžně se měnícího prostředí mobilních zařízení. Zobrazení se skládá z časově souvisejících věcí.

## <a name="things-entity-sets"></a>Věci: sady entit

Sklad zveřejňuje data v následujících oblastech vyšší úrovně:

  -  Aplikace se zapnutou ochranou aplikací a využití
  -  Zaregistrovaná zařízení, vlastnosti a inventář
  -  Inventář aplikací a softwaru
  -  Konfigurace zařízení a zásady dodržování předpisů

Tyto oblasti obsahují entity nebo věci, které mají smysl v daném prostředí Intune. V následujících tématech se můžete podívat na podrobnosti o sadách entit:

  -  [Aplikace](reports-ref-application.md)
  -  [Datum](reports-ref-date.md)
  -  [Zařízení](reports-ref-devices.md)
  -  [Intune Management Extension](reports-ref-intunemanagementextension.md)
  -  [Zásady](reports-ref-policy.md)
  -  [Správa mobilních aplikací (MAM)](reports-ref-mobile-app-management.md)
  -  [User](reports-ref-user.md)
  -  [Aktuální uživatel](reports-ref-current-user.md)
  -  [Přidružení zařízení uživatelů](reports-ref-user-device.md)

## <a name="relationships-star-schema-model"></a>Relace: Model hvězdicového schématu

Sklad uspořádává entity do relací využitelných v rámci typů otázek, které chcete položit. Můžete například zkontrolovat počet instalací interně vyvinuté aplikace pro Android. Struktura datového skladu umožňuje získat přehled o mobilním prostředí. Analytické nástroje, jako je Microsoft Power BI, můžou používat datový model datového skladu k vytvoření vizualizací a dynamických řídicích panelů.

Entity a relace používají model hvězdicového schématu. Hvězdicové schéma vytváří korelaci faktů v časové dimenzi. *Faktem* je v kontextu modelu kvantitativní míra, jako například počet zařízení, počet aplikací nebo čas registrace. V tabulkách faktů se ukládá velké množství dat. Protože mohou být velmi rozsáhlé, omezují obvykle množství informací na 30 dnů. *Dimenze* poskytuje kontext pro fakty. Zatímco fakt udává, co se stalo, dimenze určují, komu se to stalo. Tabulky dimenzí, jako je například tabulka **Uživatelé**, jsou menší a mohou uchovávat data za delší časové období než tabulky faktů. 

Model hvězdicového schématu je optimalizovaný pro flexibilitu a analýzu dat, abyste mohli vytvářet sestavy potřebné k pochopení vyvíjejícího se mobilního prostředí.

## <a name="time-daily-snapshots"></a>Čas: Denní snímky

Sklad je podřízený datům Intune. Intune pořizuje denní snímek o půlnoci v čase standardu UTC a ukládá ho do skladu. Doba uchování snímků může být u každé tabulky faktů jiná. Některé se udržují sedm dní, jiné 30 dní a některé i déle.

## <a name="next-steps"></a>Další kroky

 - Další informace o tom, jak datový sklad sleduje dobu života uživatele v Intune, získáte v článku věnovaném [reprezentaci doby života uživatele v datovém skladu Intune](reports-ref-user-timeline.md).
 - Další informace o práci s datovými sklady získáte v článku [Vytvoření prvního datového skladu](https://www.codeproject.com/Articles/652108/Create-First-Data-WareHouse).
 - Další informace o práci s Power BI a datovým skladem získáte v článku [Vytvoření nové sestavy Power BI importem sady dat](https://powerbi.microsoft.com/documentation/powerbi-service-create-a-new-report/). 
