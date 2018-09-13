---
title: Filtrování zásad pomocí značek oboru v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí značek oboru můžete filtrovat konfigurační profily pro konkrétní role.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 000505df3c0898ed0939244dfe1b075c64097611
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329423"
---
# <a name="use-scope-tags-to-filter-policies"></a>Filtrování zásad pomocí značek oboru

Značky oboru vám umožňují filtrovat zásady pomocí značek, které sami vytvoříte.

Můžete například vytvořit značku oboru s názvem „Technické oddělení“ a přiřadit ji ke konfiguračním profilům týkajícím se právě tohoto oddělení. Následně ji přiřadíte k roli „Správci technického oddělení“. Těmto uživatelům se pak zobrazí jen zásady se značkou „Technické oddělení“.

## <a name="to-create-a-scope-tag"></a>Vytvoření značky oboru

Vyberte **Role** > **Obor (značky)** > **Vytvořit**.

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Přidaní značky oboru do konfiguračního profilu

Zvolte **Konfigurace zařízení** > **Profily** > vyberete profil > **Vlastnosti** > **Obor (značky)**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Přiřazení značky oboru k roli

Zvolte **Role** > **Všechny role** > **Správce zásad a profilů** > **Přiřazení** > **Obor (značky)**.

## <a name="next-steps"></a>Další kroky

Spravujte [role](role-based-access-control.md) a [profily](device-profile-assign.md).

