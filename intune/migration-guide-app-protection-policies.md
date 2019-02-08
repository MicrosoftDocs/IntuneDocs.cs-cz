---
title: Konfigurace zásad ochrany aplikací při migraci do Intune
titlesuffix: Microsoft Intune
description: Tento článek popisuje nezbytné kroky postupu k nastavení zásad ochrany aplikací během migrace do Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: fa9df81c363099cc487497fdd4503df8c91ea4a5
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55837029"
---
# <a name="configure-app-protection-policies-optional"></a>Konfigurace zásad ochrany aplikací (volitelné)


Zásady ochrany aplikací umožňují:
* Šifrovat aplikace
* Definovat PIN kód při přístupu k aplikaci
* Blokovat spuštění aplikací na zařízeních s jailbreakem nebo rootem a použít mnoho dalších způsobů ochrany

Pokud uživatel ztratí telefon nebo je mu telefon odcizen, můžete vzdáleně vymazat firemní data, zatímco osobní data uživatele zůstanou nedotčena.

Zásady ochrany aplikací používají zabezpečení na úrovni aplikace, takže zařízení není potřeba registrovat. Dají se použít pro všechna zařízení, ať už jsou zaregistrovaná v Intune nebo ne. Můžete je použít také u zařízení zaregistrovaných u jiných poskytovatelů MDM.

## <a name="app-protection-policies-with-lob-apps"></a>Zásady ochrany obchodních aplikací

Zásady ochrany mobilních aplikací můžete rozšířit také na obchodní aplikace (LOB), když využijete [Microsoft Intune App SDK](app-sdk-get-started.md) nebo nástroj Microsoft Intune App Wrapping pro platformy iOS i Android. Další informace najdete v článcích [Nástroj App Wrapping Tool pro iOS](app-wrapper-prepare-ios.md) a [Nástroj App Wrapping Tool pro Android](app-wrapper-prepare-android.md). Dále se můžete podívat na článek [Příprava obchodních aplikací na ochranu aplikací](apps-prepare-mobile-application-management.md).

## <a name="how-do-app-protection-policies-help-during-migration"></a>Jak zásady ochrany aplikací pomáhají při migraci?

Při migraci je potřeba odebrat zařízení od předchozího poskytovatele MDM a ihned ho zaregistrovat do Intune. Tyto kroky je potřeba naplánovat a domluvit s koncovými uživateli, aby svá zařízení odebrali od předchozího poskytovatele MDM a ihned je zaregistrovali do Intune. Během migrace se ale někteří uživatelé můžou zpozdit s dokončením registrace, takže jejich zařízení nebude spravovat žádný poskytovatel MDM.

V tomto období může být vaše organizace vystavena většímu nebezpečí úniku firemních dat při odcizení zařízení, pokud zůstane povolený přístup k firemním prostředkům. Při zablokování přístupu k firemním prostředkům se může také snížit produktivita uživatelů.

Intune vám může poskytnout ochranu firemních dat i během migrace, takže tato data zůstanou v bezpečí, i když nebudete používat žádnou správu na úrovni zařízení.

Když zakážete podmíněný přístup u předchozího poskytovatele MDM, uživatelé můžou být dál produktivní, i když ještě není dokončená registrace do Intune.

## <a name="task-list-for-app-protection-policies"></a>Seznam kroků pro zásady ochrany aplikací

1. [Vytvoření zásady ochrany aplikace](app-protection-policies.md#create-an-app-protection-policy)
2. [Nasazení zásady](app-protection-policies.md#deploy-a-policy-to-users)


## <a name="next-steps"></a>Další postup

[Speciální aspekty migrace](migration-guide-considerations.md)
