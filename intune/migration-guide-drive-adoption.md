---
title: "Využití podmíněného přístupu k většímu přijetí koncovými uživateli"
description: "Cílem tohoto článku je poskytnout přehledné informace o tom, jak pomocí podmíněného přístupu zjednodušit registraci Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0b2fbcc1d63f229e1b63873841bc300bdde92fa3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2017
---
# <a name="drive-end-user-adoption-with-conditional-access"></a>Využití podmíněného přístupu k většímu přijetí koncovými uživateli

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Povolení funkcí podmíněného přístupu v Intune, například blokování e-mailu pro neregistrovaná zařízení, může zjednodušit registraci a dodržování předpisů, ale není podmínkou pro úspěšnou migraci. Úspěch by měly určovat vaše cíle přijetí migrace a požadavky na zabezpečení.

## <a name="migration-campaign-with-conditional-access"></a>Kampaň migrace pomocí podmíněného přístupu

Obvyklý postup, jak podpořit kampaň migrace pomocí podmíněného přístupu:

1.  Nastavte, aby byla pravidla podmíněného přístupu vynucena pro všechny uživatele, ne však pro ty, kteří potřebují migrovat od starého poskytovatele řešení MDM. Můžete vytvořit skupinu všech uživatelů Azure AD, kteří budou vyloučeni z podmíněného přístupu.

2.  V průběhu jejich migrace je můžete ze skupiny vyloučení podmíněného přístupu odebírat.

3.  Po dokončení migrace nakonfigurujte pro všechny zásady podmíněného přístupu blokování jako výchozí možnost, která se použije, pokud Intune neumožní přístup.

### <a name="advantages"></a>Výhody

-   Poskytuje řízení přístupu pro nové uživatelské účty nebo uživatelské účty, které nebyly spravované předchozím řešením.

-   Poskytuje uživatelům předchozího řešení období odkladu migrace.

-   Minimalizuje ztrátu produktivity.

### <a name="disadvantages"></a>Nevýhody

-   Dokud pro uživatele předchozího řešení nebude povolený podmíněný přístup, můžou k prostředkům přistupovat pomocí nespravovaných zařízení.

> [!TIP]
> Existuje i celá řada dalších přístupů. Můžete si zvolit jednodušší postup odložení veškerého podmíněného přístupu až do doby, kdy všechny fáze obdržely pokyn k registraci. Nebo přísnější postup vynucení podmíněného přístupu už od začátku, který bude vyžadovat úplné dodržování předpisů pro veškerý přístup.

-   Další informace o [podmíněném přístupu](/intune/conditional-access).

## <a name="task-list-for-conditional-access"></a>Seznam kroků pro podmíněný přístup

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Krok 1: Rozhodněte o způsobu implementace podmíněného přístupu

[Běžné způsoby použití podmíněného přístupu](/intune/conditional-access-intune-common-ways-use)

### <a name="task-2-set-up-intune-conditional-access"></a>Krok 2: Nastavení podmíněného přístupu Intune

Vyberte jednu z následujících možností:

-   [Konfigurace podmíněného přístupu v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [Instalace místního konektoru Exchange pomocí Intune](/intune/exchange-connector-install)

-   [Nastavení zásad podmíněného přístupu založeného na aplikacích pro Exchange Online](/intune/app-based-conditional-access-intune-exchange-online-create)

-   [Nastavení zásad podmíněného přístupu založeného na aplikacích pro SharePoint Online](/intune/app-based-conditional-access-intune-sharepoint-online-create)

-   [Blokování aplikací, které nepoužívají moderní ověřování (ADAL)](/intune/app-modern-authentication-block)

## <a name="next-steps"></a>Další kroky

[Typický cyklus migrace](migration-guide-cycle.md)
