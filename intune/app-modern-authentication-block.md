---
title: Blokování aplikací bez moderního ověřování v Intune
titleSuffix: Microsoft Intune
description: Další informace o aplikaci a moderní ověřování (ADAL) pomocí Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/03/2019
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ca96f36f8813d80c7ebb07bfb3bd65f8aa0b392
ms.sourcegitcommit: 71314481e644025c005019b478b4cbeaf2390ea9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041677"
---
# <a name="block-apps-that-dont-use-modern-authentication-adal"></a>Blokování aplikací, které nepoužívají moderní ověřování (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Podmíněný přístup založený na aplikaci se zásadami ochrany aplikací spoléhá na aplikace pomocí [moderní ověřování](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), což je implementace protokolu oauth2. Většina současných mobilních a desktopových aplikací Office moderní ověřování používá. Nicméně existují aplikace třetích stran a starší aplikace Office, které používají jiné metody ověřování, například základní ověřování a ověřování pomocí formulářů.

## <a name="block-access-to-apps"></a>Zablokuje přístup k aplikacím

K blokování přístupu do aplikace, které nepoužívají moderní ověřování, implementace podmínku přístup pomocí zásad ochrany aplikací Intune. Další informace najdete v tématu [podmíněný přístup na základě aplikace s Intune](app-based-conditional-access-intune.md).

## <a name="additional-information"></a>Další informace

Další informace o podmíněného přístupu Azure AD najdete v následujících tématech:
- [Co je podmíněný přístup v Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Jak funguje podmíněný přístup založený na aplikaci](app-based-conditional-access-intune.md#how-app-based-conditional-access-works)
- [Nastavení Sharepointu Online a Exchange Online pro podmíněný přístup Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/conditional-access-for-exo-and-spo)

## <a name="next-steps"></a>Další postup

- [Podmíněný přístup na základě aplikace s Intune](app-based-conditional-access-intune.md)
