---
title: "Základní nastavení Intune | Dokumentace Microsoftu"
description: "Tento článek popisuje nezbytné kroky nastavení Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 0fce3edb43a147491465d8a58d1a9a4f009fba55
ms.lasthandoff: 04/14/2017


---

# <a name="phase-1-basic-setup"></a>Fáze 1: Základní nastavení

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Po zhodnocení vašeho prostředí je dalším krokem instalace Intune.

## <a name="external-dependencies-for-an-intune-deployment"></a>Externí závislosti pro nasazení Intune

### <a name="identity"></a>Identita

Intune vyžaduje, aby identitu a seskupování uživatelů poskytovala služba Azure Active Directory (AAD).

-   Další informace o [požadavcích na identitu](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Další informace o [požadavcích na synchronizaci adresáře](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Další informace o [požadavcích na vícefaktorové ověřování](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

-   Další informace o [plánování skupin uživatelů a zařízení](https://docs.microsoft.com/intune/deploy-use/plan-your-user-and-device-groups).

-   Další informace o [vytváření skupin uživatelů a zařízení](https://docs.microsoft.com/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

Pokud už organizace používá Office 365, je důležité, aby služba Intune používala stejné prostředí Azure Active Directory.

### <a name="pki-optional"></a>PKI (volitelné)

Pokud plánujete, že budete v Intune používat ověřování profilů VPN, Wi-Fi nebo e-mailových profilů pomocí certifikátů, musíte ověřit, jestli [máte infrastrukturu PKI](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles) a jestli je připravená k vytvoření a nasazení profilů certifikátů.

Další informace o konfiguraci certifikátů v Intune najdete níže.

-   [Jak konfigurovat infrastrukturu certifikátů pro SCEP](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep)

-   [Jak konfigurovat infrastrukturu certifikátů pro PFX](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx)

-   [Jak nakonfigurovat profily certifikátů Intune] (file:///C:/intune/deploy-use/ https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles).

-   [Jak konfigurovat zásady přístupu k prostředkům](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune)

## <a name="task-list-for-an-intune-setup"></a>Seznam kroků instalace Intune

### <a name="task-1-intune-subscription"></a>Krok 1: Předplatné Intune

Ještě než začnete s migrací do Intune, potřebujete předplatné Intune.

-   Můžete navštívit [tuto stránku](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), kde najdete pokyny, jak:

    -   Vytvořit nové předplatné Intune propojené s novým tenantem AAD

    -   Propojit předplatné Intune přihlášením k existujícímu tenantovi AAD

### <a name="task-2-assign-intune-user-licenses"></a>Krok 2: Přiřazení uživatelských licencí pro Intune

-   Podívejte se, [jak přiřadit uživatelské licence pro Intune](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4).

-   Pokud jste vytvořili nového tenanta Azure Active Directory, podívejte se, [jak vytvořit nové uživatele nebo synchronizovat uživatele z místní služby Active Directory (AD).](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Krok 3: Nastavení autority MDM na Intune

Intune můžete spravovat prostřednictvím portálu Azure Portal nebo konzoly Current Branch Configuration Manageru. Pokud nepotřebujete integrovat Intune v nasazení Current Branch Configuration Manageru, doporučujeme spravovat Intune z [portálu Azure Portal](https://portal.azure.com).

Nastavte autoritu MDM na **Intune** a povolte tak portál Azure Portal pro Intune. Díky použití jiné autority MDM může Intune přenést správu MDM na alternativní konzoly správy Microsoftu. Tyto případy nejsou obvyklé.

> [!IMPORTANT]
> Pokud přenášíte správu mobilního zařízení na Intune poprvé, měli byste nastavit autoritu MDM na Intune.

-   Podívejte se, [jak nastavit autoritu pro správu mobilních zařízení](https://docs.microsoft.com/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

## <a name="next-step"></a>Další krok

[Fáze 1: Konfigurace zásad pro správu zařízení a aplikací](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-device-and-app-management-policies)

