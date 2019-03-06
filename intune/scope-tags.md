---
title: Filtrování zásad pomocí značek oboru v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí značek oboru můžete filtrovat konfigurační profily pro konkrétní role.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/29/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 50163b253cddadc5e18eef8f43199691117f14cd
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57394091"
---
# <a name="use-scope-tags-to-filter-policies"></a>Filtrování zásad pomocí značek oboru

Značky oboru vám umožňují filtrovat zásady pomocí značek, které sami vytvoříte. Můžete použít značky oboru role a aplikace.

Když správce vytvoří prostředek v Intune, všechny značky oboru přiřazeno, kterou správce se automaticky přiřadí nový prostředek.

Můžete například vytvořit značku oboru s názvem „Technické oddělení“ a přiřadit ji ke konfiguračním profilům týkajícím se právě tohoto oddělení. Následně ji přiřadíte k roli „Správci technického oddělení“. Těmto uživatelům se pak zobrazí jen zásady se značkou „Technické oddělení“.

## <a name="to-create-a-scope-tag"></a>Vytvoření značky oboru

Vyberte **Role** > **Obor (značky)** > **Vytvořit**.

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Přidaní značky oboru do konfiguračního profilu

Zvolte **Konfigurace zařízení** > **Profily** > vyberete profil > **Vlastnosti** > **Obor (značky)**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Přiřazení značky oboru k roli

Zvolte **Role** > **Všechny role** > **Správce zásad a profilů** > **Přiřazení** > **Obor (značky)**.

## <a name="to-assign-a-scope-tag-to-an-app"></a>Přiřadit značky oboru aplikace

Zvolte **klientské aplikace** > **aplikace** > zvolte aplikace > **vlastnosti** > **obor (značky)**  >  **Přidat** > zvolte značky > **vyberte** > **OK** > **Uložit**.


## <a name="next-steps"></a>Další postup

Spravujte [role](role-based-access-control.md) a [profily](device-profile-assign.md).

