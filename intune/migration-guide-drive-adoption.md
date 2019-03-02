---
title: Využití podmíněného přístupu k většímu přijetí koncovými uživateli
titlesuffix: Microsoft Intune
description: Naučte se využít podmíněný přístup k řízení registrací v Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2bf8f43d3fa530eab4aac1ea7bb46fdc56a9763f
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2019
ms.locfileid: "57229169"
---
# <a name="drive-end-user-adoption-with-conditional-access-in-microsoft-intune"></a>Využití podmíněného přístupu v Microsoft Intune pro účely přijetí koncovými uživateli

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

-   Dokud nebudou mít uživatelé předchozího řešení povolený podmíněný přístup, můžou k prostředkům získávat přístup pomocí nespravovaných zařízení.


Existuje i celá řada dalších přístupů. Můžete si zvolit jednodušší postup odložení veškerého podmíněného přístupu až do doby, kdy všechny fáze obdržely pokyn k registraci. Nebo přísnější postup vynucení podmíněného přístupu už od začátku, který bude vyžadovat úplné dodržování předpisů pro veškerý přístup.

-   Další informace o [podmíněném přístupu](conditional-access.md).

## <a name="task-list-for-conditional-access"></a>Seznam kroků pro podmíněný přístup

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Úloha 1: Rozhodněte, jak chcete implementovat podmíněný přístup

[Běžné způsoby použití podmíněného přístupu](conditional-access-intune-common-ways-use.md)

### <a name="task-2-set-up-intune-conditional-access"></a>Úloha 2: Nastavení podmíněného přístupu v Intune

Vyberte jednu z následujících možností:

-   [Konfigurace podmíněného přístupu v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [Instalace místního konektoru Exchange pomocí Intune](exchange-connector-install.md)

-   [Nastavení zásad podmíněného přístupu založeného na aplikacích pro Exchange Online](app-based-conditional-access-intune-create.md)

-   [Nastavení zásad podmíněného přístupu založeného na aplikacích pro SharePoint Online](app-based-conditional-access-intune-create.md)

-   [Blokování aplikací, které nepoužívají moderní ověřování (ADAL)](app-modern-authentication-block.md)

## <a name="next-steps"></a>Další postup

Přečtěte si další informace o [typickém cyklu migrace](migration-guide-cycle.md).
