---
title: "Základní nastavení Intune"
description: "Tento článek popisuje nezbytné kroky nastavení Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c3129b2a8d93e91493455da5f3e5fd1a59dd77bb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="basic-setup"></a>Základní nastavení

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Když jste zhodnotili prostředí, je čas na nastavení Intune.

## <a name="external-dependencies-for-an-intune-deployment"></a>Externí závislosti pro nasazení Intune

### <a name="identity"></a>Identita

Intune vyžaduje, aby identitu a seskupování uživatelů poskytovala služba Azure Active Directory (AAD).

-   Další informace o [požadavcích na identitu](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Další informace o [požadavcích na synchronizaci adresáře](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Další informace o [požadavcích na vícefaktorové ověřování](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

-   Další informace o [plánování skupin uživatelů a zařízení](/intune/users-permissions-add).

-   Další informace o [vytváření skupin uživatelů a zařízení](/intune/groups-get-started).

Pokud už organizace používá Office 365, je důležité, aby služba Intune používala stejné prostředí Azure Active Directory.

### <a name="pki-optional"></a>PKI (volitelné)

Pokud plánujete, že budete v Intune používat ověřování profilů VPN, Wi-Fi nebo e-mailových profilů pomocí certifikátů, musíte ověřit, jestli [máte infrastrukturu PKI](/intune/certificates-configure) a jestli je připravená k vytvoření a nasazení profilů certifikátů.

Další informace o konfiguraci certifikátů v Intune najdete níže.

-   [Jak konfigurovat infrastrukturu certifikátů pro SCEP](/intune/certificates-scep-configure)

-   [Jak konfigurovat infrastrukturu certifikátů pro PFX](/intune/certficates-pfx-configure)


## <a name="task-list-for-an-intune-setup"></a>Seznam kroků instalace Intune

### <a name="task-1-intune-subscription"></a>Krok 1: Předplatné Intune

Ještě než začnete s migrací do Intune, potřebujete předplatné Intune.

-   Můžete navštívit [tuto stránku](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), kde najdete pokyny, jak:

    -   Vytvořit nové předplatné Intune propojené s novým tenantem AAD

    -   Propojit předplatné Intune přihlášením k existujícímu tenantovi AAD

### <a name="task-2-assign-intune-user-licenses"></a>Krok 2: Přiřazení uživatelských licencí pro Intune

-   Podívejte se, [jak přiřadit uživatelské licence pro Intune](licenses-assign.md).

-   Pokud jste vytvořili nového tenanta Azure Active Directory, podívejte se, [jak vytvořit nové uživatele nebo synchronizovat uživatele z místní služby Active Directory (AD).](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Krok 3: Nastavení autority MDM na Intune

Ke správě Intune můžete použít portál Azure Portal nebo konzolu Current Branch Configuration Manageru. Pokud nepotřebujete integrovat Intune v nasazení Current Branch Configuration Manageru, doporučujeme spravovat Intune z [portálu Azure Portal](https://portal.azure.com).

Nastavte autoritu MDM na **Intune** a povolte tak portál Azure Portal pro Intune. Díky použití jiné autority MDM může Intune přenést správu MDM na alternativní konzoly správy Microsoftu. Tyto případy nejsou obvyklé.

> [!IMPORTANT]
> Pokud přenášíte správu mobilního zařízení na Intune poprvé, měli byste nastavit autoritu MDM na Intune.

-   Podívejte se, [jak nastavit autoritu pro správu mobilních zařízení](/intune/mdm-authority-set).

## <a name="next-step"></a>Další krok

[Konfigurace zásad pro správu zařízení a aplikací](migration-guide-configure-policies.md)
