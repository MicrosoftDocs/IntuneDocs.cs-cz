---
title: Blokování aplikací bez moderního ověřování v Intune
titleSuffix: Microsoft Intune
description: Informace o blokování aplikací, které nepoužívají moderní ověřování (ADAL) pomocí Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2019
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5717c7471b8fc003572b863c5f317abe1e66bf07
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742176"
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Blokování aplikací, které nepoužívají moderní ověřování (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Podmíněný přístup založený na aplikaci se zásadami ochrany aplikací spoléhá na aplikace pomocí [moderní ověřování](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), což je implementace protokolu oauth2. Většina současných mobilních a desktopových aplikací Office moderní ověřování používá. Nicméně existují aplikace třetích stran a starší aplikace Office, které používají jiné metody ověřování, například základní ověřování a ověřování pomocí formulářů.

## <a name="block-apps"></a>Blokování aplikací

Pokud chcete blokovat přístup k aplikacím, které nepoužívají moderní ověřování, doporučujeme následující metody:

- Nastavte pravidla deklarací služby AD FS pro blokování jiných než moderních ověřovacích protokolů. Podrobné pokyny jsou uvedené ve scénáři 3 – [Blokování veškerého přístupu k O365 kromě aplikací využívajících prohlížeč](https://technet.microsoft.com/library/dn592182.aspx).
- Pro **Exchange a SharePoint Online**, použití podmíněného přístupu a použít tuto rutinu prostředí PowerShell Set-SPOTenant pro službu SharePoint online. Podrobné pokyny najdete v tématu [Nastavení SharePointu Online a Exchange Online pro podmíněný přístup Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication#legacy-authentication-protocols).


>[!IMPORTANT]
>Podmíněný přístup založený na aplikaci se nesmí používat s ověřováním na základě certifikátů Azure Active Directory (Azure AD). Současně můžete mít nakonfigurovanou jen jednu z těchto metod.

## <a name="next-steps"></a>Další postup

- [Podmíněný přístup na základě aplikace s Intune](app-based-conditional-access-intune.md)
