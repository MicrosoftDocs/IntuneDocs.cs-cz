---
title: "Nastavení autority pro správu mobilních zařízení"
titlesuffix: Azure portal
description: "Přečtěte si, jak v Intune nastavit autoritu pro správu mobilních zařízení. \""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fc0634f5e5f4648dabaa371c3ab94f070a941057
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="set-the-mobile-device-management-authority"></a>Nastavení autority pro správu mobilních zařízení

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Nastavení autority pro správu mobilních zařízení (MDM) určuje způsob správy zařízení. Jako správce IT musíte nastavit autoritu MDM, aby uživatelé mohli registrovat zařízení pro správu.

Možné konfigurace:

- **Intune Standalone** – jedná se o pouze cloudovou správu, kterou můžete nakonfigurovat pomocí portálu Azure Portal. Zahrnuje celou sadu možností, které Intune nabízí. [Nastavte autoritu MDM v konzole Intune](#set-mdm-authority-to-intune).

- **Intune Hybrid** – jedná se o integraci cloudového řešení Intune se System Center Configuration Managerem. Intune můžete konfigurovat pomocí konzoly Configuration Manager. [Nastavte autoritu MDM v nástroji Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Správa mobilních zařízení pro Office 365** – jedná se o integraci Office 365 s cloudovým řešením Intune. Intune můžete konfigurovat z Centra pro správu Office 365. Zahrnuje dílčí sadu možností, které jsou dostupné s Intune Standalone. Nastavte autoritu MDM v Centru pro správu Office 365.

>[!IMPORTANT]    
V Configuration Manageru verze 1610 a vyšší a v Microsoft Intune verze 1705 můžete změnit autoritu pro správu mobilních zařízení bez kontaktování podpory Microsoftu a bez rušení registrace a následné nové registrace stávajících spravovaných zařízení. Podrobnosti najdete v článku [Co dělat, když zvolíte nesprávné nastavení autority pro správu mobilních zařízení (MDM)](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

## <a name="set-mdm-authority-to-intune"></a>Nastavení autority MDM na Intune

1. Na [Azure Portalu](https://portal.azure.com) zvolte **Další služby** > **Monitorování a správa** > **Intune**.
2. Výběrem oranžové informační zprávy otevřete nastavení **Autorita pro správu mobilních zařízení**.
3. V oblasti **Autorita pro správu mobilních zařízení** zvolte některou autoritu MDM z následujících možností:
  - **Autorita MDM Intune**
  - **Autorita MDM Configuration Manageru**
  - **Žádné**

  ![Snímek obrazovky Intune s nastavením autority pro správu mobilních zařízení](media/set-mdm-auth.png)

  Zobrazí se zpráva, že jste úspěšně nastavili autoritu MDM na Intune.

## <a name="enable-device-enrollment"></a>Povolení registrace zařízení

Když jako autoritu MDM nastavíte Intune, můžou si uživatelé zaregistrovat zařízení v osobním vlastnictví a získat přístup k prostředkům, jako je e-mail, pokud si nainstalují Portál společnosti (iOS a Android), přidají pracovní přihlašovací údaje (Windows) nebo přejdou na web Portál společnosti (iOS, Android, macOS).

Různé platformy mají následující požadavky, které umožňují nebo zjednodušují registraci:
- **iOS** – (povinné) [opatřete si certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md) a pak [povolte registraci pro zařízení s iOS vlastněná firmou](ios-enroll.md) (nepovinné).
- **Android** – (nepovinné) [povolte pracovní profily Androidu](android-enroll.md).
- **Windows** – (nepovinné) povolte [automatickou registraci](windows-enroll.md) nebo [hromadnou registraci](windows-bulk-enroll.md).
- **macOS** – žádné požadavky


## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Vyčištění mobilních zařízení po vypršení platnosti certifikátu MDM

Certifikát MDM se obnovuje automaticky, když mobilní zařízení komunikují se službou Intune. Když se mobilní zařízení vymažou nebo se jim po určitou dobu nedaří komunikovat se službou Intune, certifikát MDM se neobnoví. Zařízení se z portálu Azure Portal odebere po uplynutí 180 dnů od vypršení platnosti certifikátu MDM.
