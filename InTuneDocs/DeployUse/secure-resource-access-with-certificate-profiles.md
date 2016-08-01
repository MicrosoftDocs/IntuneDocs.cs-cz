---
title: "Profily certifikátů pro přístup k prostředkům | Microsoft Intune"
description: "Zabezpečte sítě VPN, Wi-Fi a přístup k e-mailu pomocí certifikátu nainstalovaného na každé zařízení uživatele."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: c8158b6a54347f6bec1008142eed44daca8946d0


---

# Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune
Když povolíte přístup k podnikovým prostředkům prostřednictvím sítě VPN, Wi-Fi nebo e-mailových profilů, máte možnost zabezpečit tento přístup pomocí certifikátu nainstalovaného na každém uživatelském zařízení. Funguje to takhle:

1. Ujistěte se, že máte zavedenou správnou infrastrukturu certifikátů, jak je popsáno v tématu [Konfigurace infrastruktury certifikátů pro SCEP](configure-certificate-infrastructure-for-scep.md) nebo [Konfigurace infrastruktury certifikátů pro PFX](configure-certificate-infrastructure-for-pfx.md).

2. Na každé zařízení nainstalujete kořenový certifikát (nebo certifikát zprostředkující certifikační autority), aby zařízení rozpoznalo legitimitu vaší certifikační autority. To provedete tak, že vytvoříte a nasadíte **profil důvěryhodného certifikátu**. Když tento profil nasadíte, budou zařízení, která spravujete v Intune, požadovat a přijímat kořenový certifikát. Pro každou platformu budete muset vytvořit samostatný profil. **Profil důvěryhodného certifikátu** je dostupný pro tyto platformy:
 -  iOS 7.1 nebo novější
 -  Mac OS X 10.9 a novější
 -  Android 4.0 nebo novější
 -  Windows 8.1 a vyšší
 -  Windows Phone 8.1 nebo novější

3. Nechte každé zařízení vyžádat si certifikát, který se má používat k ověření přístupu k e-mailu, síti VPN a síti Wi-Fi, jak je popsáno v tématu [Konfigurace profilů certifikátů Intune](configure-intune-certificate-profiles.md). Můžete vytvořit a nasadit **Profil certifikátu PKCS #12 (.PFX)** nebo **Profil certifikátu SCEP** pro zařízení na těchto platformách:

-  Android 4.0 nebo novější
-  iOS 7.1 nebo novější
-  Windows 10 (Desktop a Mobile) a novější

Použijte **Certifikát profilu SCEP** pro:
-   Mac OS X 10.9 a novější
-   Windows Phone 8.1 nebo novější

Pro každou platformu budete muset vytvořit samostatný profil. Při vytváření profil přidružíte k **profilu důvěryhodného kořenového certifikátu**, který jste vytvořili předtím.

> [!NOTE]           
> -    Pokud nemáte certifikační autoritu organizace, musíte ji vytvořit.
>- Pokud se na základě platforem zařízení rozhodnete použít profil protokolu SCEP (Simplified Certificate Enrollment Protocol), musíte taky nakonfigurovat server Služby zápisu síťových zařízení.
>-  Bez ohledu na to, jestli plánujete používat profily SCEP, nebo .PFX, musíte stáhnout a nakonfigurovat konektor Microsoft Intune Certificate Connector.
> Veškerá konfigurace je popsaná v tématech [Konfigurace infrastruktury certifikátů pro SCEP](configure-certificate-infrastructure-for-scep.md) a [Konfigurace infrastruktury certifikátů pro PFX](configure-certificate-infrastructure-for-pfx.md).

### Další kroky
- [Konfigurace infrastruktury certifikátů pro SCEP](configure-certificate-infrastructure-for-scep.md)
- [Konfigurace infrastruktury certifikátů pro PFX](configure-certificate-infrastructure-for-pfx.md)
- [Konfigurace profilů certifikátů Intune](configure-intune-certificate-profiles.md)



<!--HONumber=Jul16_HO3-->


