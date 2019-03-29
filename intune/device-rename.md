---
title: Přejmenování zařízení s Windows pomocí Microsoft Intune – Azure | Dokumentace Microsoftu
description: Přejmenování zařízení s Windows pomocí Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8dfdc3641d583fc045346034ee8543feff1e7cbf
ms.sourcegitcommit: 1144247aa7f042eb1b99d8fd8dd17b909eae38c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2019
ms.locfileid: "58567560"
---
# <a name="rename-a-windows-device-in-intune"></a>Přejmenování zařízení s Windows v Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

**Přejmenování zařízení** akce slouží k přejmenování vlastněných společností zařízení Windows, které je zaregistrované v Intune. Název zařízení se změní v Intune a na zařízení. 

Tato funkce v současné době nepodporuje přejmenování zařízení hybridní Windows Azure AD.

## <a name="rename-a-device"></a>Přejmenování zařízení

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **všechny služby**, vyfiltrujte **Intune**a zvolte **Microsoft Intune**.
3. Zvolte **zařízení** > **všechna zařízení** > zvolte zařízení s Windows > **Další** > **přejmenování zařízení**.
4. V **přejmenování zařízení** okno, zadejte nový název do textového pole. Můžete použít písmena, číslice a pomlčky. Název musí obsahovat alespoň jedno písmeno nebo pomlčkou.
5. Pokud chcete zařízení restartovat po jeho přejmenování, zvolte **Ano** vedle **restartování po přejmenování**.
6. Zvolte **přejmenovat**.



## <a name="next-steps"></a>Další postup

K zobrazení stavu **přejmenovat** akce zařízení, zkontrolujte **přehled** stránky pro zařízení.
