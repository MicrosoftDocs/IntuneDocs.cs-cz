---
title: Nastavení zásad podmíněného přístupu na základě aplikace v Intune
description: Zjistěte, jak vytvořit zásadu podmíněného přístupu na základě aplikace.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2d6d67454409cf8a8749d28cba6ac76f591da9e3
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2018
ms.locfileid: "48231283"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Nastavení zásad podmíněného přístupu na základě aplikace v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek popisuje, jak pro aplikace, které jsou na seznamu schválených aplikací, nastavit zásady podmíněného přístupu na základě aplikace. Na seznamu schválených aplikací jsou aplikace, které testoval Microsoft.

> [!IMPORTANT]
> Tento článek vás provede postupem přidání zásad podmíněného přístupu na základě aplikace. Všimněte si, že aplikace ze seznamu schválených aplikací, jako jsou SharePoint Online, Microsoft Teams a Microsoft Exchange Online, můžete přidat stejným postupem.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Vytvoření zásad podmíněného přístupu na základě aplikace v úloze Azure AD

Správci IT můžou vytvářet zásady podmíněného přístupu na základě aplikace v úloze Azure AD. Má to tu výhodu, že není potřeba přepínat mezi úlohami Azure a Intune.

> [!IMPORTANT]
> Abyste mohli vytvořit zásady podmíněného přístupu Azure AD na portálu Intune Azure Portal, musíte mít licenci Azure AD Premium.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Vytvoření zásady podmíněného přístupu na základě aplikace

> [!IMPORTANT]
> Než začnete využívat zásady podmíněného přístupu na základě aplikace, je potřeba použít pro vaše aplikace [zásady ochrany aplikací Intune](app-protection-policies.md).

1. Na **řídicím panelu Intune** zvolte **Podmíněný přístup**.

2. V podokně **Zásady** vytvořte novou zásadu podmíněného přístupu na základě aplikace výběrem možnosti **Nová zásada**.

4. Zadejte název zásady a nakonfigurujte nastavení dostupná v části **Přiřazení** a potom v části **Ovládací prvky přístupu** zvolte **Přiřazení**.

5. Zvolte **Vyžadovat klientem schválenou aplikaci**, klikněte na **Vybrat** a potom novou zásadu uložte kliknutím na **Vytvořit**.

## <a name="next-steps"></a>Další kroky
[Blokování aplikací, které nepoužívají moderní ověřování](app-modern-authentication-block.md)

### <a name="see-also"></a>Viz taky

[Ochrana dat aplikací pomocí zásad ochrany aplikací](app-protection-policies.md)
[Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
