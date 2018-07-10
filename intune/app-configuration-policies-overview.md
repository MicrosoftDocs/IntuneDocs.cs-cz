---
title: Zásady konfigurace aplikací v Microsoft Intune
titlesuffix: ''
description: Zjistěte, jak v Microsoft Intune používat zásady konfigurace aplikací pro zařízení s iOSem nebo Androidem.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6c04d2d8fa2e302c4d11760d3660a0a67e8b3695
ms.sourcegitcommit: b47fad133ef8ef1eb65484463431c6c53f6a638a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35291542"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>Zásady konfigurace aplikací v Microsoft Intune

V Microsoft Intune se zásady konfigurace aplikací používají k nastavení konfigurace aplikací pro iOS nebo Android. Nastavení konfigurace umožňuje přizpůsobit aplikaci. Tyto konfigurační zásady se nepřiřazují přímo uživatelům ani zařízením, ale spojíte je s aplikací a pak přiřazujete tuto aplikaci. Nastavení zásad konfigurace se použije, když ho aplikace zjistí (obvykle při prvním spuštění aplikace).

Pokud chcete zásadu konfigurace aplikace přiřadit skupině uživatelů a zařízení, použijte kombinaci zahrnujících a vylučovacích přiřazení. Jakmile přidáte zásady konfigurace aplikace, můžete u těchto zásad konfigurace aplikací nastavit přiřazení. Když nastavíte přiřazení zásad, můžete zahrnout a vyloučit skupiny uživatelů, na které se zásady vztahují. Když zvolíte možnost zahrnout jednu nebo více skupin, můžete zahrnout konkrétní nebo integrované skupiny. Integrované skupiny jsou **Všichni uživatelé**, **Všechna zařízení** a **Všichni uživatelé a všechna zařízení**.

Aplikace může například požadovat zadání následujících podrobných informací:

- Vlastní číslo portu
- Nastavení jazyka
- Nastavení zabezpečení
- Nastavení brandingu, jako je logo společnosti

Když tato nastavení zadají uživatelé špatně, můžete to zvýšit zatížení vašeho helpdesku a zpomalit přijímání nových aplikací.

Zásady konfigurace aplikací pomůžou tyto problémy eliminovat tím, že vám dovolí pomocí zásad přiřadit tato nastavení uživatelům dřív, než aplikaci spustí. Nastavení jsou pak zadaná automaticky a uživatelé nemusí provádět žádnou akci.

Nastavení konfigurace se použije, když ho aplikace zjistí. Nastavení konfigurace aplikace se většinou kontroluje při prvním spuštění aplikace uživatelem.

K dispozici máte dvě možnosti použití konfigurací aplikací v Intune:
 - **Spravovaná zařízení** – Intune spravuje zařízení jako poskytovatel správy mobilních zařízení (MDM).
 - **Spravované aplikace** – správa aplikace je možná i bez registrace zařízení.

## <a name="apps-that-support-app-configuration"></a>Aplikace podporující konfiguraci aplikací

Zásady konfigurace aplikací můžete používat u aplikací, které konfiguraci podporují. Aby bylo možné podporovat konfiguraci aplikací v Intune, musí být aplikace napsané tak, aby použití konfigurací aplikací podporovaly. Podrobnosti získáte od dodavatele aplikace.

Obchodní aplikace si můžete připravit buď tak, že sadu Intune App SDK začleníte přímo do aplikace, nebo po dokončení vývoje aplikaci zabalíte. Sada Intune App SDK, která je k dispozici pro iOS a Android, povolí pro vaši aplikaci zásady konfigurace aplikace pomocí Intune. Usiluje o minimalizaci nutných změn kódu, které musí vývojáře aplikace provádět. Další informace najdete v tématu [Přehled sady Intune App SDK](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Podpora Graph API pro konfiguraci aplikací

K provádění úloh konfigurace aplikací můžete použít také Graph API. Podrobnosti najdete v [referenčních informacích o cílové konfiguraci MAM pomocí Graph API](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="next-steps"></a>Další kroky

### <a name="managed-devices"></a>Spravovaná zařízení

 - Přečtěte si, jak používat konfiguraci aplikací u zařízení s iOSem.  Viz [Přidání zásad konfigurace aplikací pro spravovaná zařízení s iOSem](app-configuration-policies-use-ios.md).
 - Přečtěte si, jak používat konfiguraci aplikací u zařízení s Androidem.  Viz [Přidání zásad konfigurace aplikací pro spravovaná zařízení s Androidem](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Spravované aplikace

 - Přečtěte si, jak používat konfiguraci aplikací u spravovaných aplikací. Viz [Přidání zásad konfigurace aplikací pro spravované aplikace bez registrace zařízení](app-configuration-policies-managed-app.md).
