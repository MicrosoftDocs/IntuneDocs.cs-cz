---
title: "Profily certifikátů pro přístup k prostředkům"
description: "Zabezpečte sítě VPN, Wi-Fi a přístup k e-mailu pomocí certifikátu nainstalovaného na každé zařízení uživatele."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d20be5a701204fa3f41b051f21c967096f68d337
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2017
---
# <a name="secure-resource-access-with-certificate-profiles-in-microsoft-intune"></a>Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Když uživatelům poskytnete přístup k podnikovým prostředkům prostřednictvím sítě VPN, Wi-Fi nebo e-mailových profilů, máte možnost zabezpečit tento přístup pomocí certifikátu, který je nainstalovaný na všech uživatelských zařízeních. Funguje to takhle:

1. Ujistěte se, že máte zavedenou správnou infrastrukturu certifikátů, jak popisují témata [Konfigurace infrastruktury certifikátů pro SCEP](configure-certificate-infrastructure-for-scep.md) nebo [Konfigurace infrastruktury certifikátů pro PFX](configure-certificate-infrastructure-for-pfx.md).

2. Na každé zařízení nainstalujte kořenový certifikát nebo certifikát zprostředkující certifikační autority (CA), aby zařízení rozpoznalo legitimitu vaší certifikační autority. K tomuto účelu vytvořte a nasaďte **profil důvěryhodného certifikátu**. Když tento profil nasadíte, budou zařízení, která spravujete v Intune, požadovat a přijímat kořenový certifikát. Pro každou platformu budete muset vytvořit samostatný profil. **Profil důvěryhodného certifikátu** je dostupný pro tyto platformy:
 -  iOS 8.0 a novější
 -  Mac OS X 10.9 a novější
 -  Android 4.0 nebo novější
 -  Android for Work
 -  Windows 8.1 a vyšší
 -  Windows Phone 8.1 nebo novější

3. Vytvořte profily certifikátů. Zařízení si vyžádají certifikát, který se má používat k ověření přístupu k VPN, Wi-Fi a e-mailu, jak je popsáno v tématu [Konfigurace profilů certifikátů Intune](configure-intune-certificate-profiles.md). Můžete vytvořit a nasadit **Profil certifikátu PKCS #12 (.PFX)***nebo* **Profil certifikátu SCEP** pro zařízení s těmito platformami:

  -  iOS 8.0 a novější
  -  Android 4.0 a novější
  -  Android for Work
  -  Windows 10 (Desktop a Mobile) a novější

  **Profil certifikátu SCEP** použijte pro zařízení s těmito platformami:
    -   Mac OS X 10.9 a novější
    -   Windows Phone 8.1

Pro každou platformu musíte vytvořit samostatný profil. Při vytváření profil přidružíte k **profilu důvěryhodného kořenového certifikátu**, který jste vytvořili dřív.

> [!NOTE]           
> - Pokud nemáte certifikační autoritu organizace, musíte ji vytvořit.
>- Pokud se na základě platforem zařízení rozhodnete použít profil SCEP (Simplified Certificate Enrollment Protocol), musíte taky nakonfigurovat server Služby zápisu síťových zařízení (NDES).
>-  Bez ohledu na to, jestli plánujete používat profily SCEP, nebo .PFX, musíte stáhnout a nakonfigurovat Microsoft Intune Certificate Connector.
>-  Konfigurace veškerých požadovaných služeb je popsaná v tématech [Konfigurace infrastruktury certifikátů pro SCEP](configure-certificate-infrastructure-for-scep.md) a [Konfigurace infrastruktury certifikátů pro PFX](configure-certificate-infrastructure-for-pfx.md).

### <a name="next-steps"></a>Další kroky
- [Konfigurace infrastruktury certifikátů pro SCEP](configure-certificate-infrastructure-for-scep.md)
- [Konfigurace infrastruktury certifikátů pro PFX](configure-certificate-infrastructure-for-pfx.md)
- [Konfigurace profilů certifikátů Intune](configure-intune-certificate-profiles.md)
