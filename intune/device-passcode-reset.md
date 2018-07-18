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
ms.openlocfilehash: a233c62b76901d9bad00aa6d8b2a8a4dd45dea96
ms.sourcegitcommit: 024cce10a99b12a13f32d3995b69c290743cafb8
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/14/2018
ms.locfileid: "39039297"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Resetování nebo odebrání hesla zařízení v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pokud chcete vytvořit nové heslo pro zařízení, použijte akci **Odebrat heslo**. Tato akce zobrazí výzvu k resetování PIN kódu pouze pro pracovní profil. Pracovní profily Androidu nepodporují resetování PIN kódu zařízení.

## <a name="work-profile-pin-reset-supported-platforms"></a>Platformy podporující resetování PIN kódu pracovního profilu

- Zařízení s Androidem zaregistrovaná s pracovním profilem, verze 8.0 nebo novější 
- Zařízení s Androidem, verze 6.0 nebo starší
- Zařízení s Androidem Enterprise v beznabídkovém režimu
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

Podporovaná zařízení s pracovním profilem Androidu obdrží nové heslo pro odemknutí spravovaného profilu nebo výzvu spravovaného profilu pro koncového uživatele. 

U zařízení s pracovním profilem Androidu 8.0 obdrží koncový uživatel oznámení s výzvou, aby ihned po dokončení registrace aktivoval resetování hesla. Oznámení se zobrazí, pokud je požadováno a nastaveno heslo pracovního profilu. Po zadání hesla se oznámení zavře.

## <a name="resetting-ios-passcodes"></a>Resetování hesla v iOSu

Ze zařízení s iOSem jsou hesla odebrána. Pokud jsou nastaveny zásady dodržování předpisů vyžadující heslo, zobrazí se v zařízení výzva, aby uživatel zadal nové heslo v nastavení. 

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v podokně **Zařízení** vyberete **Akce zařízení**.
