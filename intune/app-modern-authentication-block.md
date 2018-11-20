---
title: Blokování aplikací bez moderního ověřování v Intune
titleSuffix: Microsoft Intune
description: Informace o blokování aplikací, které nepoužívají moderní ověřování (ADAL)
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cf8b323d6f7afa5fc7e3cfecbf04f61e0d11d9c5
ms.sourcegitcommit: 6ff5df63a2fff291d7ac5fed9c51417fe808650d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52167361"
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Blokování aplikací, které nepoužívají moderní ověřování (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Podmíněný přístup založený na aplikaci se zásadami ochrany aplikací spoléhá na aplikace pomocí [moderní ověřování](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), což je implementace protokolu oauth2. Většina současných mobilních a desktopových aplikací Office moderní ověřování používá. Nicméně existují aplikace třetích stran a starší aplikace Office, které používají jiné metody ověřování, například základní ověřování a ověřování pomocí formulářů.

Přístup k těmto aplikacím zablokovat, doporučujeme následující metody:

* Nastavte pravidla deklarací služby AD FS pro blokování jiných než moderních ověřovacích protokolů. Podrobné pokyny jsou uvedené ve scénáři 3 – [Blokování veškerého přístupu k O365 kromě aplikací využívajících prohlížeč](https://technet.microsoft.com/library/dn592182.aspx).
* Pro **Exchange a SharePoint Online** použijte podmíněný přístup Azure Active Directory a použijte rutinu PowerShellu Set-SPOTenant pro SharePoint Online. Podrobné pokyny najdete v tématu [Nastavení SharePointu Online a Exchange Online pro podmíněný přístup Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication#legacy-authentication-protocols).


>[!IMPORTANT]
>Podmíněný přístup založený na aplikaci se nesmí používat s ověřováním na základě certifikátů Azure Active Directory (Azure AD). Současně můžete mít nakonfigurovanou jen jednu z těchto metod.

### <a name="see-also"></a>Viz také
[Podmíněný přístup na základě aplikace s Intune](app-based-conditional-access-intune.md)
