---
title: Data odesílaná Googlem do Intune
titleSuffix: Microsoft Intune
description: Seznam dat, která Google odesílá do Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c379c8db-788a-454e-9098-665ea3bc7b56
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 368205b63fcd360adf66f964c6cae087f6da3dfc
ms.sourcegitcommit: 2162ed46d939b4a9b85fa4e7e9943f2fb5948f1e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="data-google-sends-to-intune"></a>Data odesílaná Googlem do Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pokud se na zařízení povolí správa zařízení s Androidem Enterprise, Microsoft Intune naváže spojení s Googlem a mezi Intune a Googlem se budou sdílet informace o uživateli a o zařízení. Aby mohla služba Microsoft Intune navázat spojení, je napřed nutné vytvořit účet Google.

Následující tabulka uvádí data, která Google odesílá do Intune, když je na daném zařízení povolená správa zařízení:


| Data odesílaná Googlem do Intune | Podrobnosti | Používáno pro | Příklad |
|:---:|:---:|:---:|:---:|
| Podniková data | Identifikátory společnosti zákazníka v Googlu | Propojí informace o zákazníkovi mezi Intune a Googlem. | Příklad **enterpriseId**: LC04eik8a6<br>**Název:** Jméno správce zadané při konfiguraci Androidu Enterprise Příklad: Jan Novák<br>**E-mail správce** YourAdmin@gmail.com, který se použil při konfiguraci Androidu Enterprise |
| Data aplikací | Data pro spravované aplikace Obchodu Play | Cílení aplikace na dostupné nebo vyžadované uživatele nebo zařízení | Příklad **názvu aplikace**: Contoso Warehouse Inventory Application<br>Příklad **jedinečného identifikátoru reprezentujícího aplikaci**: app:com.Contoso.Warehouse.InventoryTracking |
| Účet služby | Jedinečný interní účet služby Google pro použití s voláními konkrétního uživatele | Používá se pro uskutečňování volání do Googlu jménem zákazníka (pro zobrazení aplikací, zařízení atd.). | Příklad **názvu**: InternalAccount@InternalService.com<br>Příklad **klíče**: ServiceAccountPassword |


Pokud chcete ukončit používání správy zařízení s Androidem Enterprise v Microsoft Intune a odstranit data, je nutné deaktivovat správu zařízení s Androidem Enterprise v Microsoft Intune a také odstranit váš účet Google. Vyhledejte si v účtu Google postup pro správu účtu.


