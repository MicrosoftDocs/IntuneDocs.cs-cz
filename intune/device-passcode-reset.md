---
title: Resetování hesel u zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Odeberte nebo resetujte heslo pomocí akce Odebrat heslo na zařízeních v Intune, která spravujete nebo monitorujete.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9eb46a557dfbd21d45ab3b395ccaf169d187bf1f
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71303505"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Resetování nebo odebrání hesla zařízení v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento dokument popisuje jak resetování hesla na úrovni zařízení, tak resetování hesla pracovního profilu v Androidu Enterprise (dříve nazývaném zařízení s Androidem for Work nebo AfW). Je důležité si uvědomit, že tento rozdíl mezi požadavky se může lišit. Při resetování hesla na úrovni zařízení se resetuje heslo celého zařízení. Při resetování hesla pracovního profilu se na zařízeních se systémem Android Enterprise resetuje jenom heslo pracovního profilu uživatele.

## <a name="supported-platforms-for-device-level-passcode-reset"></a>Platformy podporované při resetování hesla zařízení

| Platforma | Podporovaná |
| ---- | ---- |
| Zařízení s Androidem verze 6.x nebo starší | Ano |
| Zařízení s Androidem Enterprise v beznabídkovém režimu | Ano |
| Zařízení se systémem iOS | Ano |
| zařízení s iOS zaregistrovaná pomocí zápisu uživatelů | Ne |
| Zařízení s Androidem zaregistrovaná s pracovním profilem | Ne |
| Zařízení s Androidem, verze 7.0 nebo novější | Ne |
| macOS | Ne |
| Windows | Ne |

U zařízení s Androidem to znamená, že obnovení hesla na úrovni zařízení se podporuje jenom na zařízeních s 6. x nebo starším nebo na zařízeních s Androidem Enterprise spuštěnou v celoobrazovkovém režimu. Důvodem je rozhodnutí Googlu o zrušení podpory resetování přístupového kódu/hesla u zařízení s Androidem 7 v aplikacích používaných správci zařízení, které platí pro všechny dodavatele MDM.

## <a name="supported-platforms-for-android-enterprise-work-profile-passcode-reset"></a>Platformy podporované při resetování hesla pracovního profilu Androidu Enterprise

| Platforma | Podporovaná |
| ---- | ---- |
| Zařízení s Androidem Enterprise zaregistrovaná s pracovním profilem a se spuštěnou verzí 8.0 nebo novější | Ano |
| Zařízení s Androidem Enterprise zaregistrovaná s pracovním profilem a se spuštěnou verzí 7.x nebo starší | Ne |
| Zařízení s Androidem se spuštěnou verzí 7.x nebo starší | Ne |

K vytvoření nového hesla pracovního profilu použijte akci Resetovat heslo. Touto akcí vyzvete uživatele k resetování hesla a vytvoření nového, dočasného hesla, které je jenom pro pracovní profil. 

## <a name="reset-a-passcode"></a>Resetování hesla


1. Přihlaste se k [Azure Portal](https://portal.azure.com) pomocí kterékoli z následujících rolí: Azure Active Directory globální správce, Azure Active Directory Správce služby Intune, pracovník helpdesku nebo správce rolí.
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a potom vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** a potom **Všechna zařízení**.
4. Ze seznamu zařízení, která spravujete, vyberte zařízení a vyberte **...Další**. Pak zvolte vzdálenou akci zařízení **Odebrat heslo**.

## <a name="reset-android-work-profile-passcodes"></a>Resetování hesel pracovních profilů Androidu

Podporovaná zařízení s Androidem Enterprise zaregistrovaná s pracovním profilem dostanou nové heslo k odemknutí spravovaného profilu nebo se koncovému uživateli zobrazí výzva spravovaného profilu.

U zařízení s Androidem Enterprise, na kterých běží verze 8.x nebo novější a mají zaregistrovaný pracovní profil, se koncovým uživatelům ihned po registraci zobrazí výzva k aktivaci resetovaného hesla. Oznámení se zobrazí, pokud je nastavené povinné heslo pracovního profilu. Po zadání hesla se oznámení zavře.


## <a name="remove-ios-passcodes"></a>Odebrání hesel z iOS

Místo resetování stačí hesla ze zařízení s iOS jenom odebrat. Pokud jsou nastavené zásady dodržování předpisů vyžadující heslo, zobrazí se uživateli zařízení výzva, aby v Nastavení zadal nové heslo.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v podokně **Zařízení** vyberete **Akce zařízení**.
