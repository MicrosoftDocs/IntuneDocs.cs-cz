---
title: Nastavení Microsoft Intune
description: Požadavky a předpoklady k tomu, abyste se vaše předplatné Intune dalo začít používat
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: b5944f7bacd87e2ef1e1117dd44eb80b6fe572e6
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57391908"
---
# <a name="set-up-intune"></a>Nastavení Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Tento postup nastavení vám umožní povolit správu mobilních zařízení (MDM) pomocí Intune. Abyste mohli dát uživatelům přístup k firemním prostředkům nebo spravovat nastavení na jejich zařízeních, musí být jejich zařízení spravovaná.

Některé kroky, například nastavení předplatného Intune a nastavení autority pro správu mobilních zařízení, jsou ve většině situací povinné. Jiné kroky, například konfigurace vlastní domény nebo přidání aplikací, jsou nepovinné a závisejí na potřebách vaší firmy.

Pokud aktuálně používáte Microsoft System Center Configuration Manager ke správě počítačů a serverů, můžete si [připojení nástroje Configuration Manager cloudu s spolusprávy](https://docs.microsoft.com/sccm/comanage/overview).

>[!TIP]
>Pokud zakoupíte aspoň 150 licencí v rámci opravňujícího plánu Intune, můžete využít *zvýhodnění centra FastTrack*. Tato služba vám poskytne spolupráci se specialisty Microsoftu na připravení prostředí pro službu Intune. Přečtěte si téma [Zvýhodnění centra FastTrack pro Enterprise Mobility + Security (EMS)](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program).



| Kroky |                                                                                                                       Stav                                                                                                                       |
|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   1   |                                        [Podporované konfigurace](supported-devices-browsers.md) – všechno, co potřebujete vědět, než začnete. Sem patří podporované konfigurace a požadavky na síť.                                         |
|   2   |                                                                 [Přihlášení do Intune](account-sign-up.md) – přihlaste se ke zkušebnímu předplatnému nebo si vytvořte nové předplatné Intune.                                                                  |
|   3   |                [Konfigurace názvu domény](custom-domain-name-configure.md) – nastavte registraci DNS pro připojení k názvu domény vaší firmy pomocí Intune. Při připojování k Intune a využívání prostředků pak budou uživatelé používat známou doménu.                |
|   4   |                                   [Přidání uživatelů](users-add.md) – přidejte uživatele ručně, nebo připojte službu Active Directory pro synchronizaci uživatelů s Intune. Vyžaduje se, pokud vaše zařízení nepatří mezi veřejné terminály bez uživatelů.                                    |
|   5   |                                            [Přiřazení licencí ](licenses-assign.md) – dejte uživatelům oprávnění k používání služby Intune. Každé zařízení (s uživateli nebo bez uživatelů) vyžaduje licenci Intune, aby mělo k této službě přístup.                                             |
|   6   |                                               [Přidání skupin](groups-add.md) – použijte skupiny uživatelů a zařízení ke zjednodušení úloh správy. Skupiny se používají k přiřazování aplikací, nastavení a jiných prostředků.                                                |
|   7   |                                                                        [Přidání aplikací](apps-add.md) – aplikace je možné přiřadit ke skupinám a automaticky nebo volitelně nainstalovat.                                                                         |
|   8   | [Konfigurace zařízení](device-profiles.md) – nastavte profily, které slouží ke správě nastavení zařízení. Profily zařízení umožňují předem nakonfigurovat nastavení e-mailu, VPN, Wi-Fi a funkcí zařízení. Dokážou zařízení rovněž omezit, což pomůže chránit samotná zařízení i data. |
|   9   |       [Přizpůsobení Portálu společnosti](company-portal-app.md) – přizpůsobte Portál společnosti Intune, který uživatelé používají k registraci zařízení a instalaci aplikací. Tato nastavení se nacházejí jak v aplikaci Portál společnosti, tak na webu Portál společnosti Intune.       |
|  10   |                                [Povolení registrace zařízení](mdm-authority-set.md) – povolte správu zařízení se systémy iOS, Windows, Android a zařízení Mac v Intune nastavením autority pro správu mobilních zařízení a povolením konkrétních platforem.                                 |
|  11   |                                                        [Konfigurace zásad aplikací](app-protection-policy.md) – zadejte konkrétní nastavení na základě zásad ochrany aplikací v Microsoft Intune.                                                         |

