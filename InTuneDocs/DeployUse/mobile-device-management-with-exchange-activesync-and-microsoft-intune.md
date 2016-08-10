---
title: "Správa zařízení pomocí protokolu Exchange ActiveSync | Microsoft Intune"
description: "Správa mobilních zařízení pomocí správy protokolu Exchange ActiveSync (EAS) pomocí konektoru Exchange"
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: de3296e81c88b3ac04e3ba3f3d3ca222a59df7bd
ms.openlocfilehash: 96d8911dafe7897458297867ddfef97206fdfc9c


---

# Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Microsoft Intune
Aby služba Microsoft Intune mohla přímo spravovat mobilní zařízení, musí být tato zařízení [v Intune zaregistrovaná](get-ready-to-enroll-devices-in-microsoft-intune.md). Jako alternativu mohou správci povolit omezenější řešení správy, které využívá správu EAS (Exchange ActiveSync) s konektorem Exchange. Zařízení se dají spravovat pomocí místních serverů Exchange a Exchange Online s využitím Office 365. Intune podporuje pro každé předplatné jenom jedno připojení konektoru Exchange libovolného typu.

## Pravidla přístupu k Exchangi pro mobilní zařízení ##

Exchange potřebuje sadu pravidel definující, co se stane, když se mobilní zařízení pokusí o připojení k protokolu EAS. Tato pravidla se spravují v konzole pro správu Intune.

[Pravidla přístupu k Exchangi pro mobilní zařízení](exchange-access-rules-for-mobile-devices.md)

## Instalace konektoru Exchange Connector
Konektor Exchange Connector vám umožňuje spravovat nasazení Exchange v konzole Intune. Nejdřív musíte nainstalovat a nakonfigurovat příslušný konektor Intune–Exchange. Vyberte příslušnou možnost v závislosti na tom, jestli je váš Exchange místní nebo hostovaný jako služba v cloudu:

-   [Konfigurace Intune pro Exchange Online nebo nová prostředí Exchange Online Dedicated](intune-service-to-service-exchange-connector.md)
-   [Instalace konektoru Intune pro místní servery Exchange a starší prostředí Exchange Online Dedicated](intune-on-premises-exchange-connector.md)


## Použití zásad pro mobilní zařízení spravovaná Exchangem
Konzolu Intune je možné použít pro správu [nastavení zásad EAS](exchange-activesync-policy-settings-in-microsoft-intune.md) a [omezení přístupu k prostředkům společnosti](restrict-access-to-email-and-o365-services-with-microsoft-intune.md). Seznam nastavení zásad protokolu Exchange ActiveSync a funkcí podporovaných konkrétními mobilními zařízeními najdete v tématu [Srovnávací tabulka klientů protokolu Exchange ActiveSync](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Po připojení Intune k prostředí Microsoft Exchange budou mít všichni uživatelé spravovaní přes Intune svoje zásady EAS nastavené na aktuální výchozí zásady na serveru Microsoft Exchange (pokud nejsou v Intune definované nějaké specifičtější zásady).

## Vymazání podnikových dat z mobilních zařízení
Nakonec, když už se nepoužívají nebo došlo ke ztrátě nebo odcizení zařízení, můžete [vymazat podniková data z mobilních zařízení spravovaných protokolem EAS](wipe-for-exchange-managed-mobile-devices.md).



<!--HONumber=Jul16_HO5-->


