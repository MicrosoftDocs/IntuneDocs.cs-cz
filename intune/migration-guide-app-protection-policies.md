---
title: "Konfigurace zásad ochrany aplikací při migraci do Intune"
description: "Tento článek popisuje kroky potřebné k nastavení zásad ochrany aplikací během migrace do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cbe2c794a68ab37722c56448560a3c64f6087969
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="configure-app-protection-policies-optional"></a>Konfigurace zásad ochrany aplikací (volitelné)

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Zásady ochrany aplikací umožňují šifrovat aplikace, definovat kód PIN pro přístup k aplikacím, blokovat spouštění aplikací na zařízeních s jailbreakem nebo rootem a spoustu dalšího. Pokud uživatel ztratí nebo je mu odcizen telefon, můžete pomocí zásad ochrany mobilních aplikací vzdáleně vymazat firemní data, zatímco osobní data uživatele zůstanou nedotčena.

Zásady ochrany aplikací používají zabezpečení na úrovni aplikace, takže zařízení není potřeba registrovat. Dají se použít pro všechna zařízení, ať už jsou zaregistrovaná v Intune nebo ne. Včetně zařízení zaregistrovaných u jiných poskytovatelů MDM.

## <a name="app-protection-policies-with-lob-apps"></a>Zásady ochrany obchodních aplikací

Zásady ochrany mobilních aplikací můžete rozšířit také na vaše obchodní aplikace (LOB), když využijete [Microsoft Intune App SDK](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) nebo nástroj Microsoft Intune App Wrapping pro platformy [iOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) a [Android](https://www.microsoft.com/download/details.aspx?id=47267).

## <a name="how-do-app-protection-policies-help-during-migration"></a>Jak zásady ochrany aplikací pomáhají při migraci?

K migraci je potřeba odebrat zařízení od předchozího poskytovatele MDM a ihned je zaregistrovat do Intune. Tyto kroky je potřeba naplánovat a domluvit s koncovými uživateli, aby svá zařízení odebrali od předchozího poskytovatele MDM a ihned je zaregistrovali do Intune. Během migrace se ale někteří uživatelé můžou zpozdit s dokončením registrace, takže jejich zařízení nebude spravovat žádný poskytovatel MDM.

V tomto období může být vaše organizace vystavena většímu nebezpečí odcizení zařízení nebo ztráty firemních dat, pokud zůstane povolený přístup k firemním prostředkům, anebo snížení produktivity uživatelů, pokud bude přístup k firemním prostředkům zablokovaný.

Intune vám může poskytnout ochranu firemních dat i během migrace, takže tato data zůstanou v bezpečí, i když nebudete používat žádnou správu na úrovni zařízení.

Když zakážete podmíněný přístup u předchozího poskytovatele MDM, uživatelé můžou být dál produktivní, i když ještě není dokončená registrace do Intune.

## <a name="task-list-for-app-protection-policies"></a>Seznam kroků pro zásady ochrany aplikací

1. [Vytvoření zásady ochrany aplikace](/intune/app-protection-policies#create-an-app-protection-policy)
2. [Nasazení zásady](/intune/app-protection-policies#deploy-a-policy-to-users)


## <a name="next-steps"></a>Další kroky 

[Speciální aspekty migrace](migration-guide-considerations.md)
