---
title: "Zásady konfigurace aplikací v Intune | Microsoft Docs"
titlesuffix: Azure portal
description: "Přečtěte si, jak používat zásady konfigurace aplikací v Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 406d0faa1e03a41d20c1b584d2d37f9810ddbf32
ms.sourcegitcommit: ce35790090ebe768d5f75c108e8d5934fd19c8c7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="app-configuration-policies-for-intune"></a>Zásady konfigurace aplikací v Intune

Zásady konfigurace aplikací v Microsoft Intune umožňují poskytovat nastavení, když uživatelé spustí aplikaci pro iOS nebo Android. Aplikace může například vyžadovat, aby uživatelé zadali:

- Vlastní číslo portu
- Nastavení jazyka
- Nastavení zabezpečení
- Nastavení brandingu, jako je logo společnosti

Když tato nastavení zadají uživatelé špatně, můžete to zvýšit zatížení vašeho helpdesku a zpomalit přijímání nových aplikací.

Zásady konfigurace aplikací pomůžou tyto problémy eliminovat tím, že vám dovolí pomocí zásad přiřadit tato nastavení uživatelům dřív, než aplikaci spustí. Nastavení jsou pak zadaná automaticky a uživatelé nemusí provádět žádnou akci.

Tyto zásady nepřiřazujte přímo uživatelům a zařízením. Místo toho přidružíte zásadu k aplikaci a pak přiřadíte tuto aplikaci. Nastavení zásad se použije vždy, když je aplikace zkontroluje (obvykle při prvním spuštění).

K dispozici máte dvě možnosti použití konfigurací aplikací v Intune:
 - **Spravovaná zařízení**  
   Zařízení spravuje Intune jako zprostředkovatel správy mobilního zařízení (MDM).
 - **Spravované aplikace**  
   Aplikace se spravuje bez registrace zařízení.

## <a name="apps-that-support-app-configuration"></a>Aplikace podporující konfiguraci aplikací

Zásady konfigurace aplikací můžete používat u aplikací, které konfiguraci podporují. Aby bylo možné podporovat konfiguraci aplikací v Intune, musí být aplikace napsané tak, aby použití konfigurací aplikací podporovaly. Podrobnosti získáte od dodavatele aplikace.

Obchodní aplikace si můžete připravit buď tak, že sadu Intune App SDK začleníte přímo do aplikace, nebo po dokončení vývoje aplikaci zabalíte. Intune App SDK, dostupná pro iOS i Android, povoluje ve vaší aplikaci zásady ochrany aplikací Intune. Usiluje o minimalizaci nutných změn kódu, které musí vývojáře aplikace provádět. Další informace najdete v tématu [Přehled sady Intune App SDK](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Podpora Graph API pro konfiguraci aplikací

K provádění úloh konfigurace aplikací můžete použít také Graph API. Podrobnosti najdete v [referenčních informacích o cílové konfiguraci MAM pomocí Graph API](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="next-steps"></a>Další kroky

### <a name="managed-devices"></a>Spravovaná zařízení

 - Přečtěte si, jak používat konfiguraci aplikací u zařízení s iOSem.  Viz [Přidání zásad konfigurace aplikací pro spravovaná zařízení s iOSem](app-configuration-policies-use-ios.md).
 - Přečtěte si, jak používat konfiguraci aplikací u zařízení s Androidem.  Viz [Přidání zásad konfigurace aplikací pro spravovaná zařízení s Androidem](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Spravované aplikace

 - Přečtěte si, jak používat konfiguraci aplikací u spravovaných aplikací. Viz [Přidání zásad konfigurace aplikací pro spravované aplikace bez registrace zařízení](app-configuration-policies-managed-app.md).