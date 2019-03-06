---
title: Základní nastavení Microsoft Intune
description: Tento článek popisuje nezbytné kroky nastavení Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: a9f16c563ff0416092abe3812b3505c2f6d92587
ms.sourcegitcommit: fb2ca28ab0cf89202c935da3f9d98adcea20566d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57459913"
---
# <a name="basic-setup"></a>Základní nastavení

Po vyhodnocení prostředí je čas nastavit Microsoft Intune.

## <a name="external-dependencies-for-an-intune-deployment"></a>Externí závislosti pro nasazení Intune

### <a name="identity"></a>Identita

Intune vyžaduje, aby identitu a seskupování uživatelů poskytovala služba Azure Active Directory (AAD). Další informace pro:

-  [Požadavky na identity](https://docs.microsoft.com/azure/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)

-   [Požadavky na synchronizaci adresáře](https://docs.microsoft.com/azure/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)

-   [Vícefaktorové ověřování (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

-   [Plánování skupin uživatelů a zařízení](users-add.md)

-   [Vytváření skupin uživatelů a zařízení](groups-get-started.md)

Pokud už používá organizace Office 365, musí služba Intune používat stejné prostředí Azure Active Directory.

### <a name="pki-optional"></a>PKI (volitelné)

Pokud plánujete, že budete v Intune používat ověřování profilů VPN, Wi-Fi nebo e-mailových profilů pomocí certifikátů, musíte ověřit, jestli [máte infrastrukturu PKI](certificates-configure.md) a jestli je připravená k vytvoření a nasazení profilů certifikátů. Další informace o konfiguraci certifikátů v Intune:

-   [Jak konfigurovat infrastrukturu certifikátů pro SCEP](/intune/certificates-scep-configure)

-   [Jak konfigurovat infrastrukturu certifikátů pro PFX](/intune/certficates-pfx-configure)


## <a name="task-list-for-an-intune-setup"></a>Seznam kroků instalace Intune

### <a name="task-1-intune-subscription"></a>Úloha 1: Předplatné služby Intune

Ještě než začnete s migrací do Intune, potřebujete předplatné Intune.

-   Můžete navštívit [tuto stránku](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), kde najdete pokyny, jak:

    -   Vytvořit nové předplatné Intune propojené s novým tenantem AAD

    -   Propojit předplatné Intune přihlášením k existujícímu tenantovi AAD

### <a name="task-2-assign-intune-user-licenses"></a>Úloha 2: Přiřazení uživatelských licencí pro Intune

-   Podívejte se, [jak přiřadit uživatelské licence pro Intune](licenses-assign.md).

-   Pokud jste vytvořili nového tenanta Azure Active Directory, podívejte se, [jak vytvořit nové uživatele nebo synchronizovat uživatele z místní služby Active Directory (AD).](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Úloha 3: Nastavte autoritu MDM na Intune

Ke správě Intune můžete použít portál Azure Portal nebo konzolu Current Branch Configuration Manageru. Pokud nepotřebujete integrovat Intune v nasazení Current Branch Configuration Manageru, doporučujeme spravovat Intune z [portálu Azure Portal](https://portal.azure.com).

Nastavte autoritu MDM na **Intune** a povolte tak portál Azure Portal pro Intune. Díky použití jiné autority MDM může Intune přenést správu MDM na alternativní konzoly správy Microsoftu. Tyto případy nejsou obvyklé.

> [!IMPORTANT]
> Pokud přenášíte správu mobilního zařízení na Intune poprvé, měli byste nastavit autoritu MDM na Intune.

Podívejte se, [jak nastavit autoritu pro správu mobilních zařízení](mdm-authority-set.md).

## <a name="next-step"></a>Další krok

Nakonfigurujte [zásady pro správu zařízení a aplikací](migration-guide-configure-policies.md).
