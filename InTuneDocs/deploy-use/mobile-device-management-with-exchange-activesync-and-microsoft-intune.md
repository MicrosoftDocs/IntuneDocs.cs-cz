---
title: "Správa zařízení pomocí protokolu Exchange ActiveSync | Microsoft Intune"
description: "Správa mobilních zařízení pomocí správy protokolu Exchange ActiveSync (EAS) pomocí konektoru Exchange"
keywords: 
author: staciebarker
ms.author: stabar
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
ms.sourcegitcommit: 289e6019aa1a17deb91b38ed32f0432af0902a9d
ms.openlocfilehash: 1b26e1298cf0b65f99219338b7ba59987e70c3ab


---

# <a name="exchange-activesync-mobile-device-management-with-microsoft-intune"></a>Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Microsoft Intune
Aby služba Microsoft Intune mohla přímo spravovat mobilní zařízení, musí být tato zařízení [v Intune zaregistrovaná](prerequisites-for-enrollment.md). Další možností je, že správci povolí omezenější řešení pro správu, které používá správu EAS (Exchange ActiveSync) s konektorem Exchange. Ke správě zařízení je možné použít buď místní servery Exchange, nebo Exchange Online s využitím Office 365. Intune podporuje pro každé předplatné jen jedno připojení konektoru Exchange libovolného typu.

## <a name="exchange-access-rules-for-mobile-devices"></a>Pravidla přístupu k Exchangi pro mobilní zařízení ##

Exchange potřebuje sadu pravidel definující, co se stane, když se mobilní zařízení pokusí o připojení k protokolu EAS. Tato pravidla se spravují v konzole pro správu Intune.

[Pravidla přístupu k Exchangi pro mobilní zařízení](exchange-access-rules-for-mobile-devices.md)

## <a name="install-the-exchange-connector"></a>Instalace konektoru Exchange Connector
Konektor Exchange Connector vám umožňuje spravovat nasazení Exchange v konzole Intune. Napřed musíte nainstalovat a nastavit odpovídající konektor Intune k Exchange. Vhodnou variantu vyberte podle toho, jestli je váš Exchange Server místní nebo je hostovaný jako služba v cloudu:

-   [Konfigurace Intune pro Exchange Online nebo pro nové prostředí Exchange Online Dedicated](intune-service-to-service-exchange-connector.md)
-   [Instalace konektoru Intune pro místní servery Exchange a starší prostředí Exchange Online Dedicated](intune-on-premises-exchange-connector.md)


## <a name="apply-policy-for-exchangemanaged-mobile-devices"></a>Použití zásad pro mobilní zařízení spravovaná Exchangem
Konzolu Intune je možné použít pro správu [nastavení zásad EAS](exchange-activesync-policy-settings-in-microsoft-intune.md) a [omezení přístupu k prostředkům společnosti](restrict-access-to-email-and-o365-services-with-microsoft-intune.md). Seznam nastavení zásad protokolu Exchange ActiveSync a funkcí podporovaných konkrétními mobilními zařízeními najdete ve [srovnávací tabulce klientů protokolu Exchange ActiveSync](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Po připojení Intune k prostředí Microsoft Exchange budou mít všichni uživatelé spravovaní přes Intune svoje zásady EAS nastavené na aktuální výchozí zásady na serveru Microsoft Exchange (pokud nejsou v Intune definované nějaké specifičtější zásady).

## <a name="wipe-company-data-from-mobile-devices"></a>Vymazání podnikových dat z mobilních zařízení
Nakonec, když už se nepoužívají nebo došlo ke ztrátě nebo odcizení zařízení, můžete [vymazat podniková data z mobilních zařízení spravovaných protokolem EAS](wipe-for-exchange-managed-mobile-devices.md).



<!--HONumber=Nov16_HO1-->


