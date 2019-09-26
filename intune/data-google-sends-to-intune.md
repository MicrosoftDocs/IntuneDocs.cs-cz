---
title: Data odesílaná Googlem do Intune
titleSuffix: Microsoft Intune
description: Seznam dat, která Google odesílá do Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c379c8db-788a-454e-9098-665ea3bc7b56
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9163e449737973309410aa5dca87b759d38586ee
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "71303939"
---
# <a name="data-google-sends-to-intune"></a>Data odesílaná Googlem do Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pokud se na zařízení povolí správa zařízení s Androidem Enterprise, Microsoft Intune naváže spojení s Googlem a mezi Intune a Googlem se budou sdílet informace o uživateli a o zařízení. Aby mohla služba Microsoft Intune navázat spojení, je napřed nutné vytvořit účet Google.

Následující tabulka uvádí data, která Google odesílá do Intune, když je na daném zařízení povolená správa zařízení:


| Data odesílaná Googlem do Intune | Podrobnosti | Používá se pro | Příklad |
|:---:|:---:|:---:|:---:|
| Podniková data | Identifikátory společnosti zákazníka v Googlu | Propojí informace o zákazníkovi mezi Intune a Googlem. | Příklad **enterpriseId** : LC04eik8a6.<br>**Název**. Jméno správce zadané při konfiguraci Androidu Enterprise Příklad: Jana Smith.<br>**E-mail správce** YourAdmin@gmail.com, který se použil při konfiguraci Androidu Enterprise |
| Data aplikací | Data pro spravované aplikace Obchodu Play | Cílení aplikace na dostupné nebo vyžadované uživatele nebo zařízení | Příklad **názvu aplikace** : Aplikace pro inventář skladu společnosti Contoso.<br>Příklad **jedinečného identifikátoru reprezentujícího aplikaci**: app:com.Contoso.Warehouse.InventoryTracking |
| Účet služby | Jedinečný interní účet služby Google pro použití s voláními konkrétního uživatele | Používá se pro uskutečňování volání do Googlu jménem zákazníka (pro zobrazení aplikací, zařízení atd.). | Příklad **názvu**: InternalAccount@InternalService.com<br>Příklad **klíčů** : ServiceAccountPassword |


Pokud chcete ukončit používání správy zařízení s Androidem Enterprise v Microsoft Intune a odstranit data, je nutné deaktivovat správu zařízení s Androidem Enterprise v Microsoft Intune a také odstranit váš účet Google. Vyhledejte si v účtu Google postup pro správu účtu.


