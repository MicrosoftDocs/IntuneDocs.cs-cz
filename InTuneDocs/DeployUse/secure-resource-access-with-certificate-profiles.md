---
title: "Profily certifikátů pro přístup k prostředkům | Microsoft Intune"
description: "Zabezpečte sítě VPN, Wi-Fi a přístup k e-mailu pomocí certifikátu nainstalovaného na každé zařízení uživatele."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c4ff2d245586d4803aab62ffb51ac21bdb8e3669
ms.openlocfilehash: 361e4d81b3d5dd807312a1c88cd9b5abaa5dc567


---

# Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune
Když uživatelům poskytnete přístup k podnikovým prostředkům prostřednictvím sítě VPN, Wi-Fi nebo e-mailových profilů, máte možnost zabezpečit tento přístup pomocí certifikátu, který je nainstalovaný na všech uživatelských zařízeních. Funguje to takhle:

1. Ujistěte se, že máte zavedenou správnou infrastrukturu certifikátů, jak popisují témata [Konfigurace infrastruktury certifikátů pro SCEP](configure-certificate-infrastructure-for-scep.md) nebo [Konfigurace infrastruktury certifikátů pro PFX](configure-certificate-infrastructure-for-pfx.md).

2. Na každé zařízení nainstalujte kořenový certifikát nebo certifikát zprostředkující certifikační autority (CA), aby zařízení rozpoznalo legitimitu vaší certifikační autority. K tomuto účelu vytvořte a nasaďte **profil důvěryhodného certifikátu**. Když tento profil nasadíte, budou zařízení, která spravujete v Intune, požadovat a přijímat kořenový certifikát. Pro každou platformu budete muset vytvořit samostatný profil. **Profil důvěryhodného certifikátu** je dostupný pro tyto platformy:
 -  iOS 7.1 nebo novější
 -  Mac OS X 10.9 a novější
 -  Android 4.0 nebo novější
 -  Windows 8.1 a vyšší
 -  Windows Phone 8.1 nebo novější

3. Vytvořte profily certifikátů. Zařízení si vyžádají certifikát, který se má používat k ověření přístupu k VPN, Wi-Fi a e-mailu, jak je popsáno v tématu [Konfigurace profilů certifikátů Intune](configure-intune-certificate-profiles.md). Můžete vytvořit a nasadit **Profil certifikátu PKCS #12 (.PFX)***nebo* **Profil certifikátu SCEP** pro zařízení s těmito platformami:

  -  iOS 7.1 nebo novější
  -  Android 4.0 nebo novější
  -  Windows 10 (Desktop a Mobile) a novější

  **Profil certifikátu SCEP** použijte pro zařízení s těmito platformami:
    -   Mac OS X 10.9 a novější
    -   Windows Phone 8.1 nebo novější

Pro každou platformu musíte vytvořit samostatný profil. Při vytváření profil přidružíte k **profilu důvěryhodného kořenového certifikátu**, který jste vytvořili dřív.

> [!NOTE]           
> - Pokud nemáte certifikační autoritu organizace, musíte ji vytvořit.
>- Pokud se na základě platforem zařízení rozhodnete použít profil SCEP (Simplified Certificate Enrollment Protocol), musíte taky nakonfigurovat server Služby zápisu síťových zařízení (NDES).
>-  Bez ohledu na to, jestli plánujete používat profily SCEP, nebo .PFX, musíte stáhnout a nakonfigurovat Microsoft Intune Certificate Connector.
>-  Konfigurace veškerých požadovaných služeb je popsaná v tématech [Konfigurace infrastruktury certifikátů pro SCEP](configure-certificate-infrastructure-for-scep.md) a [Konfigurace infrastruktury certifikátů pro PFX](configure-certificate-infrastructure-for-pfx.md).

### Další kroky
- [Konfigurace infrastruktury certifikátů pro SCEP](configure-certificate-infrastructure-for-scep.md)
- [Konfigurace infrastruktury certifikátů pro PFX](configure-certificate-infrastructure-for-pfx.md)
- [Konfigurace profilů certifikátů Intune](configure-intune-certificate-profiles.md)



<!--HONumber=Aug16_HO4-->


