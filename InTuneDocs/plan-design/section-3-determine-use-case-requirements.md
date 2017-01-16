---
title: "Určení požadavků ve scénářích použití Intune | Dokumentace Microsoftu"
description: "Tento článek vám pomůže určit požadavky ve scénářích a dílčích scénářích použití při cloudové implementaci Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: 91b25fe35c6a1f8a554d543ca005cc3b482f22d7


---

# <a name="determine-intune-use-case-scenario-requirements"></a>Určení požadavků ve scénářích použití Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

V této části určíte požadavky každé organizační skupiny v daném scénáři použití. Tento postup vám pomůže lépe se připravit na ostatní oblasti plánování nasazení Intune, jako je architektura, návrh, registrace a spuštění. Pomůže vám také identifikovat možné mezery a problémy spojené s projektem nasazení Intune.

Každý scénář nebo dílčí scénář použití může mít jinou sadu požadavků a jiné přidružené organizační skupiny a platformy mobilních zařízení. Například ve scénáři firemního použití budete vyžadovat registraci zařízení do Intune s přísnějším nastavením (například šestimístný PIN, zakázané zálohování do cloudu) než ve scénáři použití vlastního zařízení (BYOD), kde nastavení nemusí být tak přísné (např. čtyřmístný PIN, povolené zálohování do cloudu).

Ve scénáři firemního použití také můžete mít organizační skupiny s různými sadami požadavků (např. nastavení kódu PIN, Wi-Fi, profilu VPN a nasazených aplikací). Požadavky také mohou být dány možnostmi platformy mobilního zařízení (např. čtečka otisku prstů, e-mailový profil).

Tady je několik příkladů požadavků na použití zařízení v organizaci. Najdete v nich různé sady požadavků pro každý scénář nebo dílčí scénář použití, organizační skupinu a platformu mobilního zařízení. Následující tabulku také můžete použít k zadání požadavků na použití ve vaší organizaci:

| **Případy použití** | **Dílčí případy použití** | **Skupiny** | **Platformy OS zařízení** | **Requirements** |
|:---:|:---:|:---:|:---:|:---:|
| Firemní | Pracovní proces informací | Personální, finanční oddělení | iOS | Zabezpečený e-mail, nastavení zařízení, profily, aplikace |                                                          
| Firemní | Vedení | Personální, finanční oddělení | iOS | Zabezpečený e-mail, nastavení zařízení, profily, aplikace |                                                         
| Firemní | Kiosk | Maloobchod | Android | Nastavení zařízení, profily, aplikace |
| Uživatelé s vlastním zařízením | Pracovní proces informací | Marketing, prodej | iOS | Zabezpečený e-mail, nastavení zařízení, profily, aplikace |                                                         
| Uživatelé s vlastním zařízením | Vedení | Marketing, prodej | iOS | Zabezpečený e-mail, nastavení zařízení, profily, aplikace |

## <a name="examples-of-requirements"></a>Příklady požadavků

Tady je pár dalších příkladů, které můžete použít ve sloupci Požadavky v předchozí tabulce:

- **Zabezpečený e-mail**
    - Podmíněný přístup pro Exchange Online / místní Exchange
    - Zásady ochrany aplikace Outlook
<br></br>
- **Nastavení zařízení**
    - Nastavení čtyřmístného nebo šestimístného kódu PIN
    - Zákaz zálohování do cloudu
<br></br>
- **Profily**
    - Wi-Fi
    - Síť VPN
    - E-mail (Windows 10 Mobile)
<br></br>
- **Aplikace**
    - Office 365 se zásadami ochrany aplikace
    - Obchodní aplikace se zásadami ochrany

## <a name="next-section"></a>Další část

V další části najdete pokyny pro [přípravu plánu spuštění Intune](section-4-develop-a-rollout-plan.md).



<!--HONumber=Dec16_HO5-->


