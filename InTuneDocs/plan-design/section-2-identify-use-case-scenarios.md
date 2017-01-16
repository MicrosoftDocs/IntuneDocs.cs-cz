---
title: "Identifikace scénářů použití Intune | Dokumentace Microsoftu"
description: "Tento článek vám pomůže identifikovat hlavní a dílčí scénáře použití při implementaci cloudového řešení Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: c834b0282b8f9b47566ab1da2125d993ba8febdf


---

# <a name="identify-intune-use-case-scenarios"></a>Identifikace scénářů použití Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Scénáře použití správy mobilních zařízení popisují typy uživatelů nebo rolí a vlastnictví zařízení (např. firemní nebo soukromé). Scénáře použití zařízení umožňují rozdělit uživatele do skupin, které je možné spravovat. Identifikace scénářů použití je důležitou součástí plánování úspěšného nasazení Intune.

Pojďme se podívat na několik příkladů, které organizaci pomohou identifikovat nejen scénáře použití Intune, ale i organizační skupiny a platformy mobilních zařízení přidružené ke každému případu použití.

## <a name="use-case-scenarios"></a>Scénáře použití

Můžete začít rekapitulací cílů a úkolů organizace při nasazení Intune, které vám pomohou identifikovat hlavní scénáře použití nasazeného řešení. Při sestavování plánu nasazení Intune bude potřeba odpovědět na následující otázky:

-   Plánujete podporu zařízení patřících společnosti?

-   Plánujete podporu vlastních zařízení uživatelů (BYOD)?

### <a name="sub-use-case-scenarios"></a>Dílčí scénáře použití

Jakmile identifikujete hlavní scénáře použití, bude potřeba zjistit, jestli nezahrnují dílčí případy použití. Organizace například identifikuje požadavky na podporu scénáře firemního použití, který zahrnuje tyto dílčí případy použití:

-   Informatik

-   Vedení

-   Kiosk

Tady je několik příkladů scénářů použití a dílčích scénářů použití. Následující tabulku můžete použít k zadání scénářů a dílčích scénářů použití řešení ve vaší organizaci:

| **Případy použití** | **Dílčí případy použití** |
|:---:|:---:|
| Firemní | Informatik |              
| Firemní | Vedení |           
| Firemní | Kiosk |
| Uživatelé s vlastním zařízením | Informatik |           
| Uživatelé s vlastním zařízením | Vedení |

## <a name="identify-organizational-groups-associated-with-use-case-scenarios"></a>Identifikace organizačních skupin přidružených ke scénářům použití

Teď potřebujete identifikovat organizační skupiny přidružené ke každému hlavnímu a dílčímu scénáři použití. Tady je několik příkladů organizačních skupin přidružených k hlavním a dílčím scénářům použití, které můžete použít jako šablonu k zadání informací o vaší organizaci:

| **Případy použití** | **Dílčí případy použití** | **Organizační skupiny** |
|:---:|:---:|:---:|
| Firemní | Informatik | Personalistika, finance |               
| Firemní | Vedení | Personalistika, finance |            
| Firemní | Kiosk | Maloobchod |
| Uživatelé s vlastním zařízením | Informatik | Marketing, prodej |            
| Uživatelé s vlastním zařízením | Vedení | Marketing, prodej |

## <a name="identify-mobile-device-platforms-for-use-case-scenarios"></a>Identifikace platforem mobilních zařízení pro scénáře použití

Teď budete identifikovat platformy mobilních zařízení přidružené ke každému scénáři použití. Například scénář firemního použití může podporovat platformy zařízení iOS a Android Samsung KNOX a zásada pro vlastní zařízení uživatelů (BYOD) může zahrnovat i další platformy mobilních zařízení, jako je Android (jiný než Samsung KNOX) a Windows 10 Mobile. Tady je příklad platforem mobilních zařízení přidružených ke každému scénáři použití. Následující tabulku můžete použít k zadání platforem zařízení ve vaší organizaci přidružených ke scénářům použití:

| **Případy použití** | **Dílčí případy použití** | **Skupiny** | **Platformy zařízení** |   
|:---:|:---:|:---:|:---:|
| Firemní | Informatik | Personalistika, finance | iOS |                                                           
| Firemní | Vedení | Personalistika, finance | iOS |                                                           
| Firemní | Kiosk | Maloobchod | Android |
| Uživatelé s vlastním zařízením | Informatik | Marketing, prodej | iOS |                                                           
| Uživatelé s vlastním zařízením | Vedení | Marketing, prodej | iOS |

## <a name="next-section"></a>Další část

V další části najdete pokyny, [jak identifikovat požadavky na Intune pro jednotlivé scénáře použití](section-3-determine-use-case-requirements.md).



<!--HONumber=Dec16_HO5-->


