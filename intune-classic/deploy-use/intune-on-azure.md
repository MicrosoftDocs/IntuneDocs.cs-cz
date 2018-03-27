---
title: Co je třeba zvážit při správě zařízení Windows pomocí Intune v Azure
description: Pokyny týkající se použití Intune v Azure ke správě zařízení Windows ve vaší organizaci.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 71effb587bfb82ecae18afda67b05fffd2127052
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="intune-on-azure-console-and-legacy-intune-pc-client"></a>Konzola Intune v Azure a starší verze klienta Intune v osobním počítači

Intune v nedávné době přešel na architekturu aplikačních služeb SaaS založenou na Azure. Azure poskytuje významná vylepšení ve škálování, kapacitě a výkonu. Tento přechod také nabízí lepší prostředí pro správu Intune a optimalizované pracovní postupy na portálu Azure Portal. 

Při použití Intune v Azure ke správě zařízení Windows ve vaší organizaci zvažte následující body:

## <a name="legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Funkce starší verze klienta v osobním počítači jsou dostupné jenom v konzole Silverlight.

Pracovní postupy správy klienta Intune v osobním počítači používají [konzolu pro správu Intune založenou na technologii Silverlight](https://manage.microsoft.com/), což má následující důsledky:

- Pro všechny úkoly správy bez skupin s využitím klienta Intune v osobním počítači musíte používat konzolu Silverlight.
- Při správě skupin je nutné použít [Intune na portálu Azure Portal](https://portal.azure.com/). Tento požadavek existuje, protože nyní Intune místo starší verze skupin Intune používá skupiny Azure AD. 

Z důvodu přechodu na skupiny Azure AD se trochu změnilo filtrování podle skupin v zobrazení řídicího panelu konzoly Silverlight. Pokud chcete filtrovat v aktualizovaném uživatelském rozhraní Silverlight, postupujte takto:

1. Vyberte zobrazení.
2. V okně **Filtry** zadejte název skupiny, podle které chcete filtrovat, a stiskněte Enter. Vyfiltruje se zobrazení seznamu zařízení v dané skupině.

   ![](media/intune_on_azure/image01.png)

## <a name="manage-windows-10-devices-by-using-mdm"></a>Správa zařízení s Windows 10 pomocí MDM

Doporučujeme vám použít [Mobile Device Management (MDM) ke správě zařízení s Windows 10](https://docs.microsoft.com/intune/device-restrictions-windows-10) místo starší verze klienta Intune v osobním počítači. Funkce správy Windows 10 pomocí MDM je k dispozici v Intune na portálu Azure Portal. Správa Windows 10 MDM poskytuje mnoho nových funkcí správy a zabezpečení, které nejsou k dispozici ve starší verzi klienta Intune v osobním počítači.

## <a name="continue-to-manage-windows-7-by-using-intune-pc-client"></a>Správa Windows 7 i nadále pomocí klienta Intune v osobním počítači

Pro systém Windows 7, který nelze spravovat pomocí MDM, budeme nadále podporovat existující funkce klienta Intune v osobním počítači jen v konzole Silverlight. Zvažte přechod na správu MDM při upgradu na Windows 10.

## <a name="mdm-capabilities"></a>Funkce MDM

Podrobné porovnání možností klienta v osobním počítači a MDM najdete v tématu [Porovnání správy počítačů s Windows jako osobních počítačů nebo jako mobilních zařízení](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison). Aktualizace MDM budou nadále přinášet nové možnosti správy zařízení s Windows 10 zaregistrovaných v MDM včetně vyhodnocení možnosti pro aplikace Win 32. V tématu [Co je nového](https://docs.microsoft.com/intune/whats-new) najdete nejnovější funkce přidané do služby.

## <a name="switch-from-pc-client-to-mdm"></a>Přechod z klienta v počítači na MDM

Pokud chcete ve správě zařízení s Windows 10 přejít z klienta Intune v osobním počítači na správu pomocí MDM, postupujte takto:

1. V konzole Silverlight proveďte **selektivní vymazání**, abyste zrušili registraci zařízení klienta v osobním počítači.
  ![](media/intune_on_azure/image02.png)
2. Zařízení znovu zaregistrujte pomocí [MDM (nebo Azure AD Join)](https://docs.microsoft.com/intune/windows-enroll). 

## <a name="next-steps"></a>Další kroky
[Registrace zařízení s Windows](https://docs.microsoft.com/intune/windows-enroll)

 
