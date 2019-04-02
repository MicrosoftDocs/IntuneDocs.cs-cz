---
title: Nastavení zásad podmíněného přístupu na základě aplikace v Intune
titleSuffix: Microsoft Intune
description: Zjistěte, jak vytvořit zásadu podmíněného přístupu na základě aplikace.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1514fe9dfcd09e2b77967b0fed8c36fb7a06634f
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798461"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Nastavení zásad podmíněného přístupu na základě aplikace v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pro aplikace, které jsou na seznamu schválených aplikací, nastavte zásady podmíněného přístupu. Na seznamu schválených aplikací jsou aplikace, které testoval Microsoft.

> [!IMPORTANT]
> Tento článek vás provede postupem přidání zásad podmíněného přístupu na základě aplikace. Stejný postup použijte, když ze seznamu schválených aplikací přidáváte aplikace, jako je SharePoint Online, Microsoft Teams nebo Microsoft Exchange Online.

## <a name="create-app-based-conditional-access-policies"></a>Vytvoření zásady podmíněného přístupu na základě aplikace
Podmíněný přístup je technologie Azure Active Directory (Azure AD). Uzel podmíněného přístupu, ke kterému se přistupuje z *Intune*, je stejný uzel, ke kterému se přistupuje z *Azure AD*. To znamená, že nemusíte přepínat mezi Intune a Azure AD ke konfiguraci zásad.

> [!IMPORTANT]
> Musíte mít licenci Azure AD Premium k vytvoření zásady podmíněného přístupu z portálu Intune.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Vytvoření zásady podmíněného přístupu na základě aplikace

> [!IMPORTANT]
> Než začnete využívat zásady podmíněného přístupu na základě aplikace, je potřeba použít pro vaše aplikace [zásady ochrany aplikací Intune](app-protection-policies.md).

1. V **řídicí panel Intune**vyberte **podmíněného přístupu**.

2. V podokně **Zásady** vytvořte novou zásadu podmíněného přístupu na základě aplikace výběrem možnosti **Nová zásada**.

4. Zadejte název zásady a nakonfigurujte nastavení dostupná v části **Přiřazení** a potom v části **Ovládací prvky přístupu** zvolte **Přiřazení**.

5. Zvolte **Vyžadovat klientem schválenou aplikaci**, klikněte na **Vybrat** a potom novou zásadu uložte kliknutím na **Vytvořit**.

## <a name="next-steps"></a>Další postup
[Blokování aplikací, které nepoužívají moderní ověřování](app-modern-authentication-block.md)

### <a name="see-also"></a>Viz také:

[Ochrana dat aplikací pomocí zásad ochrany aplikací](app-protection-policies.md)
[Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
