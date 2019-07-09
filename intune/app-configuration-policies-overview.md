---
title: Zásady konfigurace aplikací v Microsoft Intune
titleSuffix: ''
description: Zjistěte, jak v Microsoft Intune používat zásady konfigurace aplikací pro zařízení s iOSem nebo Androidem.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 10dad24ee41f63dcc304d95e9b733f7de3f1b71a
ms.sourcegitcommit: 1b7ee2164ac9490df4efa83c5479344622c181b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/08/2019
ms.locfileid: "67649026"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>Zásady konfigurace aplikací v Microsoft Intune

V Microsoft Intune se zásady konfigurace aplikací používají k nastavení konfigurace aplikací pro iOS nebo Android. Tato konfigurační nastavení umožní aplikaci přizpůsobit s využitím oborových standardní přístup k aplikaci konfigurace a správa. Nastavení zásad konfigurace se použije, když ho aplikace zjistí (obvykle při prvním spuštění aplikace).

Pokud chcete zásadu konfigurace aplikace přiřadit skupině uživatelů a zařízení, použijte kombinaci zahrnujících a vylučovacích přiřazení. Jakmile přidáte zásady konfigurace aplikace, můžete u těchto zásad konfigurace aplikací nastavit přiřazení. Když nastavíte přiřazení zásad, můžete zahrnout a vyloučit skupiny uživatelů, na které se zásady vztahují. Když zvolíte možnost zahrnout jednu nebo více skupin, můžete zahrnout konkrétní nebo integrované skupiny. Integrované skupiny jsou **Všichni uživatelé**, **Všechna zařízení** a **Všichni uživatelé a všechna zařízení**.

Nastavení, konfigurace aplikace například může vyžadovat lze zadat následující údaje:

- Vlastní číslo portu
- Nastavení jazyka
- Nastavení zabezpečení
- Nastavení brandingu, jako je logo společnosti

Pokud tato nastavení zadají uživatelé místo, může to udělají nesprávně, což může zvýšit zatížení vašeho helpdesku a zpomalit přijímání nových aplikací.

Zásady Konfigurace aplikací pomůžou eliminovat instalační program aplikace problémů s tím, že umožňuje přiřadit nastavení configation zásadu, která se přiřadí uživatelům dřív, než spustí aplikaci. Nastavení jsou pak zadaná automaticky a uživatelé nemusí provádět žádnou akci.

Nastavení konfigurace se použije, když ho aplikace zjistí. Nastavení konfigurace aplikace se většinou kontroluje při prvním spuštění aplikace uživatelem.

K dispozici máte dvě možnosti použití konfigurací aplikací v Intune:
 - **Spravovaná zařízení** – Intune spravuje zařízení jako poskytovatel správy mobilních zařízení (MDM).
 - **Spravované aplikace** – správa aplikace je možná i bez registrace zařízení.

> [!NOTE]
> Jako správce Microsoft Intune můžete řídit, které uživatelské účty se přidají do aplikací Microsoft Office na spravovaných zařízeních. Můžete omezit přístup jenom na povolené uživatelské účty organizace a zablokovat osobní účty na zaregistrovaných zařízeních. Podpůrné aplikace zpracují konfiguraci aplikace a odeberou a zablokují neschválené účty.

## <a name="apps-that-support-app-configuration"></a>Aplikace podporující konfiguraci aplikací

### <a name="managed-devices"></a>Spravovaná zařízení
Zásady konfigurace aplikací můžete používat u aplikací, které konfiguraci podporují. Chcete-li podporovat konfiguraci aplikací v Intune, aplikace musí mít napsány tak, aby podporují použití konfigurací aplikací v souladu s definicemi [Appconfig komunity](https://www.appconfig.org/members). Podrobnosti získáte od dodavatele aplikace.

### <a name="managed-apps"></a>Spravované aplikace
Obchodní aplikace si můžete připravit buď tak, že sadu Intune App SDK začleníte přímo do aplikace, nebo po dokončení vývoje aplikaci zabalíte. Intune App SDK, k dispozici pro iOS a Android, umožňuje aplikaci pro konfiguraci zásad ochrany aplikací Intune. Usiluje o minimalizaci nutných změn kódu, které musí vývojáře aplikace provádět. Další informace najdete v tématu [Přehled sady Intune App SDK](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Podpora Graph API pro konfiguraci aplikací

K provádění úloh konfigurace aplikací můžete použít také Graph API. Podrobnosti najdete v [referenčních informacích o cílové konfiguraci MAM pomocí Graph API](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="next-steps"></a>Další postup

### <a name="managed-devices"></a>Spravovaná zařízení

 - Přečtěte si, jak používat konfiguraci aplikací u zařízení s iOSem.  Zobrazit [přidání zásad Konfigurace aplikací pro spravovaná zařízení s Iosem](app-configuration-policies-use-ios.md).
 - Přečtěte si, jak používat konfiguraci aplikací u zařízení s Androidem.  Viz [Přidání zásad konfigurace aplikací pro spravovaná zařízení s Androidem](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Spravované aplikace

 - Přečtěte si, jak používat konfiguraci aplikací u spravovaných aplikací. Viz [Přidání zásad konfigurace aplikací pro spravované aplikace bez registrace zařízení](app-configuration-policies-managed-app.md).
