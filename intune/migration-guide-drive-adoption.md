---
title: Podpora přijetí koncovými uživateli pomocí podmíněného přístupu
titleSuffix: Microsoft Intune
description: Další informace o použití podmíněného přístupu zjednodušit registraci v Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40e78d85c215bbb5cc126705f26041ce4f7786f4
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2019
ms.locfileid: "67549457"
---
# <a name="drive-end-user-adoption-with-conditional-access-in-microsoft-intune"></a>Podpora přijetí koncovými uživateli pomocí podmíněného přístupu v Microsoft Intune

Povolení funkcí podmíněného přístupu v Intune, například blokování e-mailu pro neregistrovaná zařízení, můžete zjednodušit registraci a dodržování předpisů, ale nejsou vyžadovány pro úspěšnou migraci. Úspěch by měly určovat vaše cíle přijetí migrace a požadavky na zabezpečení.

## <a name="migration-campaign-with-conditional-access"></a>Kampaň migrace pomocí podmíněného přístupu

Tady je obvyklý postup, jak podpořit kampaň migrace pomocí podmíněného přístupu:

1. Nastavte pravidla podmíněného přístupu vynucena pro všechny uživatele, ale výslovně vyloučit uživatele, kteří potřebují migrovat od předchozího poskytovatele MDM. Můžete vytvořit novou skupinu uživatelů Azure AD se všemi uživateli podmíněného přístupu vyloučené.

2. Při migraci uživatelů, můžete ho odeberte ze skupiny vyloučení podmíněného přístupu.

3. Po dokončení migrace nakonfigurujte všechny zásady podmíněného přístupu blokování jako výchozí, pokud Intune neumožní přístup.

### <a name="advantages"></a>Výhody

- Poskytuje řízení přístupu pro nové uživatelské účty nebo uživatelské účty, které nebyly spravované předchozím řešením.

- Poskytuje uživatelům předchozího řešení období odkladu migrace.

- Minimalizuje ztrátu produktivity.

### <a name="disadvantages"></a>Nevýhody

- Uživatelé předchozího řešení může potenciálně přístup k prostředkům pomocí nespravovaných zařízení, dokud nebude povolený podmíněný přístup pro tyto uživatele.


Existuje i celá řada dalších přístupů. Můžete zvolit jednodušší postup, který odkládá veškerého podmíněného přístupu až po každé fáze obdržely pokyn k registraci nebo přísnější postup vynucení podmíněného přístupu už od začátku a vyžadovat úplné dodržování předpisů pro veškerý přístup.

- Další informace o [podmíněném přístupu](conditional-access.md).

## <a name="task-list-for-conditional-access"></a>Seznam kroků pro podmíněný přístup

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Úloha 1: Rozhodněte, jak chcete implementovat podmíněný přístup

[Běžné způsoby použití podmíněného přístupu](conditional-access-intune-common-ways-use.md).

### <a name="task-2-set-up-intune-conditional-access"></a>Úloha 2: Nastavení podmíněného přístupu v Intune

Vyberte jednu z následujících možností:

- [Konfigurace podmíněného přístupu v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

- [Instalace místního konektoru Exchange pomocí Intune](exchange-connector-install.md)

- [Nastavení zásad podmíněného přístupu na základě aplikace pro Exchange Online](app-based-conditional-access-intune-create.md)

- [Nastavení zásad podmíněného přístupu na základě aplikace pro SharePoint Online](app-based-conditional-access-intune-create.md)

- [Blokování aplikací, které nepoužívají moderní ověřování (ADAL)](app-modern-authentication-block.md)

## <a name="next-steps"></a>Další postup

Přečtěte si další informace o [typickém cyklu migrace](migration-guide-cycle.md).
