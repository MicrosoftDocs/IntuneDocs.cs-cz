---
title: Nastavení autority pro správu mobilních zařízení
titlesuffix: Microsoft Intune
description: Nastavte autoritu pro správu mobilních zařízení v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f903e9dfe5fb30f45806aac5694171814492f2e
ms.sourcegitcommit: 0f1a5d6e577915d2d748d681840ca04a0a2604dd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842267"
---
# <a name="set-the-mobile-device-management-authority"></a>Nastavení autority pro správu mobilních zařízení

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Nastavení autority pro správu mobilních zařízení (MDM) určuje způsob správy zařízení. Jako správce IT musíte nastavit autoritu MDM, aby uživatelé mohli registrovat zařízení pro správu.

Možné konfigurace:

- **Intune Standalone** – jedná se o pouze cloudovou správu, kterou můžete nakonfigurovat pomocí portálu Azure Portal. Zahrnuje celou sadu možností, které Intune nabízí. [Nastavte autoritu MDM v konzole Intune](#set-mdm-authority-to-intune).

- **Intune Hybrid** – jedná se o integraci cloudového řešení Intune se System Center Configuration Managerem. Intune můžete konfigurovat pomocí konzoly Configuration Manager. [Nastavte autoritu MDM v nástroji Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Správa mobilních zařízení pro Office 365** – jedná se o integraci Office 365 s cloudovým řešením Intune. Intune můžete konfigurovat z Centra pro správu Office 365. Zahrnuje dílčí sadu možností, které jsou dostupné s Intune Standalone. Nastavte autoritu MDM v Centru pro správu Office 365.

> [!IMPORTANT]
> V Configuration Manageru verze 1610 a vyšší a v Microsoft Intune verze 1705 můžete změnit autoritu pro správu mobilních zařízení bez kontaktování podpory Microsoftu a bez rušení registrace a následné nové registrace stávajících spravovaných zařízení. Podrobnosti najdete v článku [Co dělat, když zvolíte nesprávné nastavení autority pro správu mobilních zařízení (MDM)](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

## <a name="set-mdm-authority-to-intune"></a>Nastavení autority MDM na Intune

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Výběrem oranžové informační zprávy otevřete nastavení **Autorita pro správu mobilních zařízení**.
4. V oblasti **Autorita pro správu mobilních zařízení** zvolte některou autoritu MDM z následujících možností:
   - **Autorita MDM Intune**
   - **Autorita MDM Configuration Manageru**
   - **Žádné**

   ![Snímek obrazovky Intune s nastavením autority pro správu mobilních zařízení](media/set-mdm-auth.png)

   Zobrazí se zpráva, že jste úspěšně nastavili autoritu MDM na Intune.

## <a name="enable-device-enrollment"></a>Povolení registrace zařízení

Když jako autoritu MDM nastavíte Intune, můžou si uživatelé zaregistrovat zařízení v osobním vlastnictví a získat přístup k prostředkům, jako je e-mail, pokud si nainstalují Portál společnosti (iOS, macOS a Android), přidají pracovní přihlašovací údaje (Windows) nebo přejdou na web Portál společnosti (iOS, Android, macOS).

Různé platformy mají následující požadavky, které umožňují nebo zjednodušují registraci:
- **iOS** – (povinné) [opatřete si certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md) a pak [povolte registraci pro zařízení s iOS vlastněná firmou](ios-enroll.md) (nepovinné).
- **Android** – (nepovinné) [povolte pracovní profily Androidu](android-enroll.md).
- **Windows** – (nepovinné) povolte [automatickou registraci](windows-enroll.md) nebo [hromadnou registraci](windows-bulk-enroll.md).
- **macOS** – (povinné) [opatřete si certifikát Apple MDM Push Certificate](apple-mdm-push-certificate-get.md).

### <a name="workflow-of-intune-administration-ui"></a>Pracovní postup pro uživatelské rozhraní pro správu Intune
Pokud je povolená správa zařízení s Androidem nebo správa zařízení Apple, Intune odesílá informace o zařízení a uživateli kvůli zajištění integrace s těmito službami třetích stran a správy příslušných zařízení.

Mezi scénáře, pro které se přidává souhlas se sdílením dat, patří:
- Povolení Androidu for Work
- Povolení a nahrání certifikátů Apple MDM Push Certificate
- Povolení některé ze služeb Apple, jako jsou například Program registrace zařízení, School Manager a Volume Purchase Program

Souhlas se vždy týká výhradně používání služby pro správu mobilního zařízení, například potvrzení, že správce IT udělil zařízení Google nebo Apple oprávnění k registraci. Dokumentaci obsahující informace, které se po přechodu na nové pracovní postupy budou sdílet, najdete v následujících umístěních:
- [Data z Intune odesílaná Googlu](https://aka.ms/Data-intune-sends-to-google)
- [Data z Intune odesílaná Applu](https://aka.ms/data-intune-sends-to-apple)

Další informace o dodržování obecného nařízení o ochraně osobních údajů (GDPR) společností Microsoft najdete v [Centru zabezpečení v tématu Posouzení dodržování nařízení GDPR](https://aka.ms/trust_center_info).

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Vyčištění mobilních zařízení po vypršení platnosti certifikátu MDM

Certifikát MDM se obnovuje automaticky, když mobilní zařízení komunikují se službou Intune. Když se mobilní zařízení vymažou nebo se jim po určitou dobu nedaří komunikovat se službou Intune, certifikát MDM se neobnoví. Zařízení se z portálu Azure Portal odebere po uplynutí 180 dnů od vypršení platnosti certifikátu MDM.
