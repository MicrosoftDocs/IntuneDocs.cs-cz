---
title: Možnosti registrace pro zařízení spravovaná pomocí Microsoft Intune
titleSuffix: ''
description: Seznam možností registrace, které může nastavit správce pro zařízení spravovaná pomocí Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: cf4ad6d4-423f-4826-ab8d-6eb7a7cfb559
search.appverid: MET150
ms.custom: get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: b8c502bd42d3290bd03c0ce954d55de3073c3f2d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503215"
---
# <a name="enrollment-options-for-devices-managed-by-intune"></a>Možnosti registrace pro zařízení spravovaná pomocí Intune

Jako správce služby Intune můžete pomoct uživatelům tím, že nakonfigurujete registraci zařízení a povolíte funkce Intune.  V Intune jsou následující možnosti registrace:

## <a name="terms-and-conditions"></a>podmínky a ujednání

Můžete od uživatelů vyžadovat, aby před použitím Portálu společnosti k registraci svých zařízení a přístupu k prostředkům společnosti, jako jsou aplikace a e-mail, přijali podmínky společnosti. Konfigurace podmínek a ujednání je volitelná. Další informace o [podmínkách a ujednáních](terms-and-conditions-create.md).

## <a name="enrollment-restrictions"></a>Omezení registrace

Registrace zařízení můžete omezit s použitím následujících možností:
- Platforma zařízení
- Počet zařízení na uživatele
- Blokování osobních zařízení

Přečtěte si další informace o [omezení registrace](enrollment-restrictions-set.md).

## <a name="enable-apple-device-enrollment"></a>Povolení registrace zařízení Apple

Pro registraci zařízení s iOSem a macOS je nutný MDM Push Certificate. Přečtěte si [další informace o certifikátech MDM Push Certificate](apple-mdm-push-certificate-get.md).

## <a name="corporate-identifiers"></a>Podnikové identifikátory

Pro účely identifikace zařízení, která vlastní firma, můžete vytvořit seznam čísel IMEI a sériových čísel. Přečtěte si další informace o [podnikových identifikátorech](corporate-identifiers-add.md).
## <a name="multi-factor-authentication"></a>Vícefaktorové ověřování

Při registraci zařízení můžete uživatele požádat, aby použili dodatečnou metodu ověření, například telefon, PIN kód nebo biometrické údaje. Přečtěte si další informace o [vícefaktorovém ověřování](multi-factor-authentication.md).

## <a name="device-enrollment-manager"></a>správce registrace zařízení
Můžete nastavit uživatele jako správce registrace zařízení.  Uživatelé – správci registrace zařízení můžou registrovat velké počty mobilních zařízení s jediným uživatelským účtem. Účet správce registrace zařízení (DEM – Device Enrollment Manager) může zaregistrovat až 1 000 zařízení. Přečtěte si další informace o [správcích registrace zařízení](device-enrollment-manager-enroll.md).

## <a name="device-categories"></a>Kategorie zařízení

Můžete použít skupiny zařízení a automaticky přidávat zařízení do skupin na základě kategorií, které definujete. Když zařízení uspořádáte do skupin, budou se vám jednodušeji spravovat. Přečtěte si další informace o [kategoriích zařízení](device-group-mapping.md).
