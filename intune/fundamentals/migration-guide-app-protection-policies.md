---
title: Konfigurace zásad ochrany aplikací během migrace
titleSuffix: Microsoft Intune
description: Tento článek popisuje kroky potřebné k nastavení zásad ochrany aplikací během migrace Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 49246302cf71fc95d20cdb84099323ba9beffdb3
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940473"
---
# <a name="configure-app-protection-policies-optional"></a>Konfigurace zásad ochrany aplikací (volitelné)


Zásady ochrany aplikací umožňují:
* Šifrovat aplikace
* Definovat PIN kód při použití aplikace
* Zablokuje spouštění aplikací na zařízeních s jailbreak nebo rootem a mnoho dalších ochran.

Pokud dojde ke ztrátě nebo odcizení telefonu uživatele, můžete selektivně vymazat podniková data vzdáleně a ponechat si osobní údaje beze změny.

Zásady ochrany aplikací se týkají zabezpečení na úrovni aplikace a nevyžadují registraci zařízení. Můžete je použít u zařízení zaregistrovaných v Intune nebo ne. Můžete je také použít u zařízení zaregistrovaných do poskytovatele MDM třetí strany.

## <a name="app-protection-policies-with-lob-apps"></a>Zásady ochrany aplikací pomocí obchodních aplikací

Zásady ochrany mobilních aplikací můžete také rozšíříte do obchodních aplikací (LOB) pomocí [sady Microsoft Intune App SDK](../developer/app-sdk-get-started.md) nebo nástroje pro zabalení Microsoft Intune aplikací pro platformy iOS a Android. Další informace najdete v tématu [Nástroj pro zabalení aplikace pro iOS](../developer/app-wrapper-prepare-ios.md) a [Nástroj pro zabalení aplikace pro Android](./../developer/app-wrapper-prepare-android.md). Kromě toho si přečtěte téma [Příprava obchodních aplikací na ochranu aplikací](../developer/apps-prepare-mobile-application-management.md).

## <a name="how-do-app-protection-policies-help-during-migration"></a>Jak zásady ochrany aplikací při migraci pomůžou?

V případě migrace musíte zařízení odebrat ze starého poskytovatele MDM a zaregistrovat je do Intune. Měli byste si ho naplánovat a povzbudit koncové uživatele, aby starý poskytovatel MDM opustili a hned se zaregistrovali v Intune. Během migrace ale může dojít k uživatelům, kteří zpoždění dokončují proces registrace a jejichž zařízení nespravuje žádný poskytovatel MDM.

Tato doba může vaší organizaci lépe vymezit hrozbě krádeže zařízení a ztrátě firemních dat, pokud je přístup k podnikovým prostředkům stále povolený. Pokud je zablokovaný přístup k firemním prostředkům, může to také vést ke snížení produktivity uživatelů.

Intune může během migrace nabídnout ochranu podnikových dat, abyste mohli i nadále mít pokrytí zabezpečení pro vaše podniková data, i když nebude žádná Správa na úrovni zařízení.

Když zapnete podmíněný přístup ve starém poskytovateli MDM, můžou uživatelé pořád produktivní, zatímco jsou zaregistrované v Intune.

## <a name="task-list-for-app-protection-policies"></a>Seznam úkolů pro zásady ochrany aplikací

1. [Vytvoření zásady ochrany aplikací](../apps/app-protection-policies.md#create-an-app-protection-policy)
2. [Nasazení zásady](../apps/app-protection-policies.md#deploy-a-policy-to-users)


## <a name="next-steps"></a>Další kroky

[Speciální důležité migrace](migration-guide-considerations.md)
