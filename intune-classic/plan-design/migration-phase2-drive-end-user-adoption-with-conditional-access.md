---
title: "Podpora přijetí koncovými uživateli pomocí podmíněného přístupu | Dokumentace Microsoftu"
description: "Cílem tohoto článku je poskytnout přehledné informace o tom, jak pomocí podmíněného přístupu zjednodušit registraci Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 55e437fa33af9d27223798cbac9f541b0bc1be2d
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="phase-2-drive-end-user-adoption-with-conditional-access"></a>Fáze 2: Podpora přijetí koncovými uživateli pomocí podmíněného přístupu

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

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

-   Další informace o [podmíněném přístupu](https://docs.microsoft.com/intune/conditional-access).

## <a name="task-list-for-conditional-access"></a>Seznam kroků pro podmíněný přístup

### <a name="task-1-get-ready-for-intune-conditional-access"></a>Krok 1: Příprava na podmíněný přístup Intune

-   Seznamte se s [postupem konfigurace podmíněného přístupu](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

### <a name="task-2-set-up-intune-conditional-access"></a>Krok 2: Nastavení podmíněného přístupu Intune

Pokud chcete zjistit více informací, vyberte si jeden z následujících typů zásad podmíněného přístupu:

-   [Exchange Online a nová verze Exchange Online Dedicated](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)

-   [Místní Exchange a starší verze Exchange Online Dedicated](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)

-   [SharePoint Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)

-   [Online Skype pro firmy](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)

-   [Dynamics CRM Online](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

-   [Ukázkové scénáře přístupu k e-mailu](/intune-classic/deploy-use/restrict-email-access-example-scenarios)

## <a name="next-steps"></a>Další kroky

[Fáze 2: Typický cyklus migrace](/intune-classic/plan-design/migration-phase2-typical-migration-cycle)

