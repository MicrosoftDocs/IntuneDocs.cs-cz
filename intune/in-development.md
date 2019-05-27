---
title: Při vývoji – Microsoft Intune
titleSuffix: ''
description: Microsoft Intune nabízí ve vývoji
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: ca66a2fa331fe4dcc30c32d369db32a57ba9999c
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66047317"
---
# <a name="in-development-for-microsoft-intune---may-2019"></a>Při vývoji pro Microsoft Intune –. května 2019.

Pomáhat při vaší připravenosti a plánování, tato stránka seznamy uživatelské rozhraní Intune aktualizuje a funkce, které jsou ve vývoji, ale ještě není. Navíc platí:

- Pokud předpokládáme, že budete muset udělat před změnu, budeme publikovat doplňkové příspěvek Centru zpráv Office.
- Když funkce se spustí v produkčním prostředí, buď ve verzi preview nebo obecně k dispozici, popis funkce se přesune mimo tuto stránku a na [stránce s novinkami](whats-new.md).
- Na této stránce a [stránce s novinkami](whats-new.md) jsou pravidelně aktualizovány. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.
- Odkazovat [M365 plán](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) pro strategické dodávky a časovými osami.

> [!Note]
> Tyto položky odrážejí aktuální očekávání společnosti Microsoft o možnostech Intune v budoucí verzi. Data a jednotlivé funkce mohou změnit. Ne všechny položky ve vývoji mají popis funkce na této stránce.

**Informační kanál RSS**: Nechte se informovat Tato stránka se aktualizuje zkopírováním a vložením do informačního kanálu čtečky na následující adrese URL: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune na portálu Azure Portal


<!-- 1905 start-->


### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Hledat směrný plán podpory pro klíčové slovo  <!-- 3082036         -->
Při vytváření nebo úpravu profil standardních hodnot zabezpečení, které už brzy bude možné použít *hledání* vyfiltrujete nastavení, které zobrazují v konzole.   

### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Resetovat a vymazání zařízení hromadně pomocí rozhraní Graph API <!-- 3295288 -->
Budete moct resetovat a vymazání zařízení až 100 hromadně pomocí rozhraní Graph API.

<!-- 1904 start-->

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Uživatelé zařízení můžete zobrazit všechny spravované aplikace, které jste nainstalovaná nebo se pokusila o instalaci <!-- 2352913 -->
Portál společnosti pro Windows se zobrazí seznam všech spravovaných aplikací&ndash; povinné a k dispozici&ndash; které se instalují na zařízení uživatele. Uživatelé budou moct k pokusu o zobrazení a probíhající instalace aplikací a jejich aktuální stavy. Pokud vaše organizace nemá vytvořit obdobné aplikace vyžaduje nebo jsou dostupné, uživatelům se zobrazí se zpráva s vysvětlením, že nebyly nainstalovány žádné aplikace společnosti. Uživatelé budou také moct seřadíte nebo vyfiltrujete podle stavu instalace aplikace.

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Použijte "pravidla použitelnosti" při vytváření profilů konfigurace zařízení s Windows 10 <!-- 2549910 -->
Vytváření profilů konfigurace zařízení s Windows 10 (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **Windows 10** pro platformu). Budete moct vytvořit **pravidla použitelnosti** tak profil, který se vztahuje pouze na konkrétní edici nebo konkrétní verzi. Například vytvořit profil, který umožňuje některá nastavení nástroje BitLocker. Po přidání profilu použijte použije pravidlo použitelnosti, tak profil, který platí jenom pro zařízení s Windows 10 Enterprise.

Platí pro: 
- Windows 10 a novější



## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).


