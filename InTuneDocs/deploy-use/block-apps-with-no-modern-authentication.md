---
title: "Blokování aplikací bez moderního ověřování | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5083cb49e7a98f19ff21c1972149b00aee4ec93e
ms.openlocfilehash: 8c2718da6f90f18ffbaa6a977dfca7fbc9a1bb09


---

# Blokování aplikací, které nepoužívají moderní ověřování (ADAL)
Podmíněný přístup k aplikacím pomocí zásad MAM (MAM CA) spoléhá na aplikace, které používají [moderní ověřování](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), což je implementace protokolu OAuth2. Většina současných mobilních a desktopových aplikací Office moderní ověřování používá, existují ale aplikace třetích stran a starší aplikace Office, které používají jiné metody ověřování, například základní ověřování a ověřování na základě formulářů.

Pokud chcete přístup k těmto aplikacím zablokovat, doporučujeme následující postup:

* Instalační ADFS nastavuje pravidla pro blokování jiných než moderních ověřovacích protokolů. Podrobné pokyny jsou uvedené ve scénáři 3 – [Blokování veškerého přístupu k O365 kromě aplikací využívajících prohlížeč](https://technet.microsoft.com/library/dn592182.aspx).

>[!IMPORTANT]
>Podmíněný přístup MAM se nesmí používat s ověřováním na základě certifikátů Azure Active Directory (Azure AD). Současně můžete mít nakonfigurovanou jen jednu z těchto metod.



### Související témata
[Povolení přístupu ke službám O365 jenom aplikacím, které podporuje Intune](allow-policy-managed-apps-access-to-o365.md)



<!--HONumber=Oct16_HO4-->


