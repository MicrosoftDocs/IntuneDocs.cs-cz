---
title: Resetování hesel u zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Odeberte nebo resetujte heslo pomocí akce Odebrat heslo na zařízeních v Intune, která spravujete nebo monitorujete.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dd743bdb0eaf2e00c50aab85c497dd00aac773ed
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905151"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Resetování nebo odebrání hesla zařízení v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pokud chcete vytvořit nové heslo pro zařízení, použijte akci **Odebrat heslo**.

## <a name="supported-platforms"></a>Podporované platformy

- Zařízení s Androidem zaregistrovaná s pracovním profilem, verze 8.0 nebo novější
- Zařízení s Androidem, verze 6.0 nebo starší
- Zařízení s beznabídkovým režimem Androidu Enterprise
- iOS 
     
## <a name="unsupported-platforms"></a>Nepodporované platformy

- Zařízení s Androidem zaregistrovaná s pracovním profilem, verze 7.0 nebo starší
- Zařízení s Androidem, verze 7.0 nebo novější
- macOS
- Windows

## <a name="reset-a-passcode"></a>Resetování hesla

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a potom vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** a potom **Všechna zařízení**.
4. Ze seznamu zařízení, která spravujete, vyberte zařízení a vyberte **...Další**. Pak zvolte vzdálenou akci zařízení **Odebrat heslo**.

## <a name="resetting-android-work-profile-passcodes"></a>Resetování hesla pracovního profilu Androidu

Podporovaná zařízení s pracovním profilem Androidu obdrží nové heslo pro odemknutí spravovaného profilu nebo výzvu spravovaného profilu pro koncového uživatele. U zařízení s pracovním profilem Androidu 8.0 obdrží koncový uživatel oznámení s výzvou, aby ihned po dokončení registrace aktivoval resetování hesla. Oznámení se zobrazí, pokud je požadováno a nastaveno heslo pracovního profilu. Po zadání hesla se oznámení zavře.

## <a name="resetting-ios-passcodes"></a>Resetování hesla v iOSu

Ze zařízení s iOSem jsou hesla odebrána. Pokud jsou nastaveny zásady dodržování předpisů vyžadující heslo, zobrazí se v zařízení výzva, aby uživatel zadal nové heslo v nastavení. 

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v podokně **Zařízení** vyberete **Akce zařízení**.
