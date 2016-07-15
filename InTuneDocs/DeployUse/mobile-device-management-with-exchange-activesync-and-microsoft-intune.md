---
title: "Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: d24395786daa7aec103ec754895868a75983e099


---

# Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Microsoft Intune
Aby mohl Microsoft Intune přímo spravovat mobilní zařízení, musí si uživatelé tato zařízení v Intune zaregistrovat. U mobilních zařízení, která uživatelé nezaregistrovali, můžete povolit správu pomocí protokolu Exchange ActiveSync (EAS) s použitím konektoru Exchange. Zařízení se dají spravovat na místních serverech Exchange i prostřednictvím hostovaného Exchange v Microsoft Office 365 v cloudu.

## Pravidla přístupu k Exchangi pro mobilní zařízení ##

Exchange potřebuje sadu pravidel definující, co se stane, když se mobilní zařízení pokusí o připojení k protokolu EAS. Tato pravidla se spravují v konzole pro správu Intune.

[Pravidla přístupu k Exchangi pro mobilní zařízení](exchange-access-rules-for-mobile-devices.md)

## Instalace konektoru Exchange Connector
Konektor Exchange Connector vám umožňuje spravovat nasazení Exchange v konzole Intune. Nejdřív musíte nainstalovat a nakonfigurovat příslušný konektor Intune–Exchange. Vyberte příslušnou možnost v závislosti na tom, jestli je váš Exchange místní nebo hostovaný jako služba v cloudu:

-   [Instalace konektoru Intune pro místní Exchange](intune-on-premises-exchange-connector.md)
-   [Konfigurace konektoru Intune Service to Service Connector pro hostovaný Exchange](intune-service-to-service-exchange-connector.md)

## Použití zásad pro mobilní zařízení spravovaná Exchangem
Nastavení zásad se dá použít prostřednictvím konzoly Intune. Podívejte se na téma [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Seznam nastavení zásad protokolu Exchange ActiveSync a funkcí podporovaných konkrétními mobilními zařízeními najdete v tématu [Srovnávací tabulka klientů protokolu Exchange ActiveSync](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Po připojení Intune k prostředí Microsoft Exchange budou mít všichni uživatelé spravovaní přes Intune svoje zásady EAS nastavené na aktuální výchozí zásady na serveru Microsoft Exchange (pokud nejsou v Intune definované nějaké specifičtější zásady).

## Vymazání podnikových dat z mobilních zařízení
Nakonec, když už se nepoužívají nebo došlo ke ztrátě nebo odcizení zařízení, můžete [vymazat podniková data z mobilních zařízení spravovaných protokolem EAS](wipe-for-exchange-managed-mobile-devices.md).



<!--HONumber=Jun16_HO4-->


