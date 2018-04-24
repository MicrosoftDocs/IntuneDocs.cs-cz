---
title: Blokování aplikací bez moderního ověřování
description: ''
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 10/15/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e533dada76f5b996478a548af503d808831e3733
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Blokování aplikací, které nepoužívají moderní ověřování (ADAL)

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Podmíněný přístup založený na aplikaci pomocí zásad ochrany aplikací spoléhá na aplikace, které používají [moderní ověřování](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), což je implementace protokolu OAuth2. Většina současných mobilních a desktopových aplikací Office moderní ověřování používá, existují ale aplikace třetích stran a starší aplikace Office, které používají jiné metody ověřování, například základní ověřování a ověřování na základě formulářů.

Pokud chcete přístup k těmto aplikacím zablokovat, doporučujeme následující postup:

* Nastavte pravidla deklarací služby AD FS pro blokování jiných než moderních ověřovacích protokolů. Podrobné pokyny jsou uvedené ve scénáři 3 – [Blokování veškerého přístupu k O365 kromě aplikací využívajících prohlížeč](https://technet.microsoft.com/library/dn592182.aspx).
* V případě **SharePointu Online** zakažte jiné než moderní ověřování ve službě SharePoint Online pomocí rutiny PowerShellu [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx), která nastaví vlastnost starších verzí protokolů ověřování na hodnotu false:

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false
```


>[!IMPORTANT]
>Podmíněný přístup založený na aplikaci se nesmí používat s ověřováním na základě certifikátů Azure Active Directory (Azure AD). Současně můžete mít nakonfigurovanou jen jednu z těchto metod.

### <a name="see-also"></a>Související témata
[Povolení přístupu ke službám O365 jenom aplikacím, které podporuje Intune](allow-policy-managed-apps-access-to-o365.md)
