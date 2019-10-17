---
title: Nastavení zásad podmíněného přístupu na základě aplikace v Intune
titleSuffix: Microsoft Intune
description: Zjistěte, jak vytvořit zásadu podmíněného přístupu na základě aplikace v Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 94e9fcc77f8260c4a63150b5d0aef033677c524a
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509674"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Nastavení zásad podmíněného přístupu na základě aplikace v Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Nastavte zásady podmíněného přístupu na základě aplikací pro aplikace, které jsou součástí seznamu schválených aplikací. Na seznamu schválených aplikací jsou aplikace, které testoval Microsoft.

> [!IMPORTANT]
> Tento článek vás provede jednotlivými kroky přidání zásady podmíněného přístupu na základě aplikace. Stejný postup použijte, když ze seznamu schválených aplikací přidáváte aplikace, jako je SharePoint Online, Microsoft Teams nebo Microsoft Exchange Online.

## <a name="create-app-based-conditional-access-policies"></a>Vytvoření zásad podmíněného přístupu na základě aplikace
Podmíněný přístup je technologie Azure Active Directory (Azure AD). Uzel podmíněného přístupu, ke kterému se přistupuje z *Intune*, je stejný uzel, ke kterému se přistupuje z *Azure AD*. To znamená, že nemusíte pro konfiguraci zásad přepínat mezi Intune a Azure AD.

> [!IMPORTANT]
> Abyste mohli vytvořit zásady podmíněného přístupu na portálu Intune, musíte mít licenci Azure AD Premium.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Vytvoření zásady podmíněného přístupu na základě aplikace

> [!IMPORTANT]
> Než použijete zásady podmíněného přístupu na základě aplikace, musíte mít pro vaše aplikace použité [Zásady ochrany aplikací Intune](../apps/app-protection-policies.md) .

1. Na **řídicím panelu Intune**vyberte **podmíněný přístup**.

2. V podokně **zásady** vytvořte novou zásadu podmíněného přístupu na základě aplikace výběrem možnosti **Nová zásada** .

4. Zadejte název zásady a nakonfigurujte nastavení dostupná v části **Přiřazení** a potom v části **Ovládací prvky přístupu** zvolte **Přiřazení**.

5. Zvolte **Vyžadovat klientem schválenou aplikaci**, klikněte na **Vybrat** a potom novou zásadu uložte kliknutím na **Vytvořit**.

## <a name="next-steps"></a>Další kroky
[Blokování aplikací, které nepoužívají moderní ověřování](app-modern-authentication-block.md)

## <a name="see-also"></a>Související témata

[Ochrana dat aplikací pomocí zásad ochrany aplikací](../apps/app-protection-policies.md)
[Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
