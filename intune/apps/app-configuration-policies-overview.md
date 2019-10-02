---
title: Zásady konfigurace aplikací v Microsoft Intune
titleSuffix: ''
description: Zjistěte, jak v Microsoft Intune používat zásady konfigurace aplikací pro zařízení s iOSem nebo Androidem.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/28/2019
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
ms.openlocfilehash: af81552942805bed07e818d6005231e9305b3460
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731450"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>Zásady konfigurace aplikací v Microsoft Intune

Zásady konfigurace aplikací vám pomůžou eliminovat problémy s instalací aplikací tím, že vám umožní přiřadit nastavení konfigurace k zásadě, která je přiřazená koncovým uživatelům před spuštěním aplikace. Nastavení se pak doplní automaticky, když je aplikace nakonfigurovaná na zařízeních koncových uživatelů a koncoví uživatelé nepotřebují provádět žádné akce. Nastavení konfigurace jsou pro každou aplikaci jedinečná. 

Zásady konfigurace aplikací můžete vytvářet a používat k poskytování nastavení konfigurace pro aplikace pro iOS i Android. Tato nastavení konfigurace umožňují přizpůsobit aplikaci pomocí konfigurace a správy aplikací. Nastavení zásad konfigurace se používají, když aplikace kontroluje tato nastavení, obvykle při prvním spuštění aplikace. 

Nastavení konfigurace aplikace může například vyžadovat, abyste zadali některé z následujících údajů:

- Vlastní číslo portu
- Nastavení jazyka
- Nastavení zabezpečení
- Nastavení brandingu, jako je logo společnosti

Pokud koncoví uživatelé museli místo toho zadat tato nastavení, můžou to udělat nesprávně. Zásady konfigurace aplikací můžou zajistit konzistenci napříč podnikem a snižovat volání helpdesku od koncových uživatelů, kteří se pokoušejí nakonfigurovat vlastní nastavení sami. Pomocí zásad konfigurace aplikací může být přijímání nových aplikací snazší a rychlejší.

Dostupné parametry konfigurace jsou v konečném rozhodování od vývojářů aplikace. Dokumentaci od dodavatele aplikace byste měli zkontrolovat, aby bylo možné zjistit, zda aplikace podporuje konfiguraci a jaké konfigurace jsou k dispozici. U některých aplikací Intune naplní dostupná nastavení konfigurace. 

> [!NOTE]
> Ve spravovaných Obchod Google Play budou aplikace, které podporují konfiguraci, označeny jako:
> 
> ![Snímek obrazovky nakonfigurované aplikace](./media/app-configuration-policies-overview/configured-app.png)
>
> V případě, že jako typ registrace pro zařízení s Androidem používáte spravovaná zařízení, uvidíte jenom aplikace ze [spravovaného Google Play Storu](https://play.google.com/work), ne z [úložiště Google Play](https://play.google.com/store/apps). Spravované Obchod Google Play, které můžete také znáte jako Android for Work (AfW) a Android Enterprise, jsou aplikace v pracovním profilu, které obsahují verze aplikací, které podporují konfiguraci aplikací.

Zásadu konfigurace aplikace můžete přiřadit skupině koncových uživatelů a zařízení pomocí kombinace [zahrnutí a vyloučení přiřazení](apps-inc-exl-assignments.md). Jakmile přidáte zásady konfigurace aplikace, můžete u těchto zásad konfigurace aplikací nastavit přiřazení. Když nastavíte přiřazení zásad, můžete zahrnout a vyloučit [skupiny](../fundamentals/groups-add.md) koncových uživatelů, pro které se zásady vztahují. Když zvolíte možnost zahrnout jednu nebo více skupin, můžete zahrnout konkrétní nebo integrované skupiny. Integrované skupiny jsou **Všichni uživatelé**, **Všechna zařízení** a **Všichni uživatelé a všechna zařízení**.

Zásady konfigurace aplikací se službou Intune můžete použít dvěma způsoby:
- **Spravovaná zařízení** – Intune spravuje zařízení jako poskytovatel správy mobilních zařízení (MDM). Aplikace musí být navržená tak, aby podporovala konfiguraci aplikace.
- **Spravované aplikace** – aplikace, která byla vyvinutá pro integraci sady Intune App SDK. Tato funkce se označuje jako Správa mobilních aplikací bez registrace ([mam-We](app-management.md#mobile-application-management-mam-basics)). Můžete také zabalit aplikaci, která implementuje a podporuje sadu Intune App SDK. Další informace o zabalení aplikace najdete v tématu [Příprava obchodních aplikací na zásady ochrany aplikací](../developer/apps-prepare-mobile-application-management.md).

    > [!NOTE]
    > Aplikace spravované v Intune se při nasazení v kombinaci se zásadami Intune App Protection nahlásí s intervalem 30 minut pro stav zásad konfigurace aplikací Intune. Pokud se k uživateli nepřiřazují zásady Intune App Protection, interval vrácení se změnami zásad konfigurace aplikace Intune se nastaví na 720 minut.

## <a name="apps-that-support-app-configuration"></a>Aplikace podporující konfiguraci aplikací

### <a name="managed-devices"></a>Spravovaná zařízení
Zásady konfigurace aplikací můžete použít pro aplikace, které ji podporují. Aby bylo možné podporovat konfiguraci aplikací v Intune, musí být aplikace napsané tak, aby podporovaly používání konfigurací aplikací definovaných operačním systémem. Podrobnosti o tom, které klíče konfigurace aplikace podporují, najdete v dodavateli vaší aplikace.

### <a name="managed-apps"></a>Spravované aplikace
Obchodní aplikace si můžete připravit buď tak, že [sadu Intune App SDK](../developer/app-sdk.md) zařadíte do aplikace, nebo po jejím vývoji aplikaci pomocí [Nástroje pro zabalení aplikace Intune](../developer/apps-prepare-mobile-application-management.md). Sada Intune App SDK se snaží minimalizovat množství změn v kódu, které vyžaduje vývojář aplikace. Další informace najdete v tématu [Přehled sady Intune App SDK](../developer/app-sdk.md). Porovnání mezi sadou Intune App SDK a nástrojem pro zabalení aplikace Intune najdete v tématu [Příprava obchodních aplikací na zásady ochrany aplikací](../developer/apps-prepare-mobile-application-management.md#feature-comparison).

Výběr **spravovaných aplikací** jako **typ registrace zařízení** konkrétně odkazuje na aplikace nakonfigurované zásadami konfigurace Intune na zařízení, které není zaregistrované ve správě zařízení, zatímco **spravovaná zařízení** se vztahují na nasazené aplikace. prostřednictvím kanálu MDM a proto je spravuje Intune. Podle těchto popisů vyberte vhodnou volbu. 

![Typ registrace zařízení](./media/app-configuration-policies-overview/device-enrollment-type.png)

> [!NOTE]
> Pro aplikace s více identitami, jako je Microsoft Outlook, se můžou zvážit uživatelské předvolby. Prioritní Doručená pošta, například, bude respektovat nastavení uživatele a nemění konfiguraci. Další parametry umožňují řídit, jestli uživatel může nebo nemůže změnit nastavení. Další informace najdete v tématu [nasazení aplikace Outlook pro iOS a nastavení konfigurace aplikací pro Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

## <a name="validate-the-applied-app-configuration-policy"></a>Ověření použitých zásad konfigurace aplikace

Zásady konfigurace aplikací můžete ověřit pomocí následujících tří metod:

   1. Viditelně na zařízení. Vykazuje cílová aplikace chování použité v zásadách konfigurace aplikace?
   2. Přes diagnostické protokoly (viz část diagnostické protokoly).
   3. Na portálu Intune. V části **monitorování** zásad může být zajištěn příslušný stav:

      ![První snímek stavu instalace zařízení](./media/app-configuration-policies-overview/device-install-status-1.png)

      ![Druhý snímek stavu instalace zařízení](./media/app-configuration-policies-overview/device-install-status-2.png)

      Kromě toho v části **Intune** -> **zařízení** -> **všechna zařízení** na levé straně obrazovky se v možnosti **Konfigurace aplikace** zobrazí všechny přiřazené zásady a jejich stav:

      ![Snímek obrazovky s konfigurací aplikace](./media/app-configuration-policies-overview/app-configuration.png)

## <a name="graph-api-support-for-app-configuration"></a>Podpora Graph API pro konfiguraci aplikací

K provádění úloh konfigurace aplikace můžete použít Graph API. Podrobnosti najdete v [referenčních informacích o cílové konfiguraci MAM pomocí Graph API](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="troubleshooting"></a>Odstraňování potíží

### <a name="using-logs-to-show-a-configuration-parameter"></a>Použití protokolů k zobrazení konfiguračního parametru
Když se v protokolech zobrazí parametr konfigurace, u kterého se potvrdí, že se má použít, ale zdá se, že nebude fungovat, může se jednat o problém s implementací konfigurace vývojářem aplikace. Vyzkoušejte si nejprve konkrétního vývojáře aplikace nebo ověřte jeho znalostní bázi, může vám pomoci s Microsoftem. Pokud se jedná o problém s tím, jak se konfigurace zpracovává v rámci aplikace, bude nutné ji vyřešit v budoucí aktualizované verzi této aplikace.

## <a name="next-steps"></a>Další kroky

### <a name="managed-devices"></a>Spravovaná zařízení

- Přečtěte si, jak používat konfiguraci aplikací u zařízení s iOSem.  Viz [Přidání zásad konfigurace aplikací pro spravovaná zařízení s iOS](app-configuration-policies-use-ios.md).
- Přečtěte si, jak používat konfiguraci aplikací u zařízení s Androidem.  Viz [Přidání zásad konfigurace aplikací pro spravovaná zařízení s Androidem](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Spravované aplikace

- Přečtěte si, jak používat konfiguraci aplikací u spravovaných aplikací. Viz [Přidání zásad konfigurace aplikací pro spravované aplikace bez registrace zařízení](app-configuration-policies-managed-app.md).
