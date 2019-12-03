---
title: Určení požadavků na scénáře použití
titleSuffix: Microsoft Intune
description: Tento článek vám pomůže určit požadavky ve scénářích a dílčích scénářích použití při cloudové implementaci Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7c72cf963822284702f6b924ca506f8ec1157e91
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505141"
---
# <a name="determine-use-case-scenario-requirements"></a>Určení požadavků na scénáře použití

V této části určíte požadavky každé organizační skupiny při každém scénáři použití. Tento postup vám pomůže připravit se na další oblasti plánování nasazení Intune, jako je architektura, návrh, registrace a zavedení. Pomůže vám také identifikovat možné mezery a problémy spojené s projektem nasazení Intune.

Každý scénář nebo dílčí scénář použití může mít jinou množinu požadavků a jiné přidružené organizační skupiny a platformy mobilních zařízení. V požadavcích společnosti na určitý scénář použití například může být, že při registraci zařízení do Intune je potřeba použít přísnější sadu nastavení, která zahrnuje šestiznakový PIN nebo zákaz záloh do cloudu. Scénář použití pro uživatele s vlastním zařízením (BYOD) může být méně přísný, takže povolí čtyřznakový PIN a zálohování do cloudu.

Ve scénáři firemního použití také můžete mít organizační skupiny s různými sadami požadavků (např. nastavení kódu PIN, Wi-Fi, profilu VPN a nasazených aplikací). Požadavky také mohou být dány možnostmi platformy mobilního zařízení (např. čtečka otisku prstů nebo e-mailový profil).

Tady je několik příkladů scénářů použití v organizaci s různými sadami požadavků pro každý scénář nebo dílčí scénář použití, organizační skupinu a platformu mobilního zařízení. Požadavky na případy použití v organizaci také můžete zadat do následující tabulky:

| **Případy použití** | **Dílčí případy použití** | **SKUPINY** | **Platformy zařízení** | **požadavky** |
|:---:|:---:|:---:|:---:|:---:|
| Firemní | Informatik | Personalistika, finance | iOS | Zabezpečený e-mail, nastavení zařízení, profily, aplikace |                                                          
| Firemní | Vedení | Personalistika, finance | iOS | Zabezpečený e-mail, nastavení zařízení, profily, aplikace |                                                         
| Firemní | Kiosk | Maloobchod | Android | Nastavení zařízení, profily, aplikace |
| uživatelé s vlastním zařízením (BYOD) | Informatik | Marketing, prodej | iOS | Zabezpečený e-mail, nastavení zařízení, profily, aplikace |                                                         
| uživatelé s vlastním zařízením (BYOD) | Vedení | Marketing, prodej | iOS | Zabezpečený e-mail, nastavení zařízení, profily, aplikace |

Pokud chcete zadat požadavky na scénáře použití a dílčí scénáře použití ve vaší organizaci, [stáhněte si šablonu předchozí tabulky](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).


## <a name="examples-of-requirements"></a>Příklady požadavků

Tady jsou další příklady požadavků, které můžete použít ve sloupci Požadavky:

- **Zabezpečený e-mail**
  - Podmíněný přístup pro Exchange Online nebo místní Exchange
  - Zásady ochrany aplikace Outlook

- **Nastavení zařízení**
  - Nastavení čtyřmístného nebo šestimístného kódu PIN
  - Zákaz zálohování do cloudu

- **Profily**
  - Wi-Fi
  - Síť VPN
  - E-mail (Windows 10 Mobile)

- **Aplikace**
  - Office 365 se zásadami ochrany aplikace
  - Obchodní aplikace se zásadami ochrany

## <a name="next-steps"></a>Další kroky

V další části najdete pokyny pro [přípravu plánu spuštění Intune](planning-guide-rollout-plan.md).