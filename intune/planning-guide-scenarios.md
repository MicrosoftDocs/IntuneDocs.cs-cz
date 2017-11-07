---
title: "Identifikace scénářů pro případy použití"
description: "Tento článek vám pomůže určit scénáře použití a dílčí scénáře použití při cloudové implementaci Microsoft Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 864f99f52e0c8b46307f1ec24d11da51d8f52662
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/01/2017
---
# <a name="identify-mobile-device-management-use-case-scenarios"></a>Identifikace scénářů použití při správě mobilních zařízení

Identifikace scénářů použití je důležitou součástí plánování úspěšného nasazení Intune. Scénáře použití jsou praktické, protože s nimi můžete uživatele rozdělit do lépe zvládnutelných skupin podle typu uživatele nebo role a vlastnictví uživatelského zařízení (například firemní nebo osobní vlastnictví).

Pojďme se podívat na některé příklady, které organizaci pomohou identifikovat nejen scénáře použití Intune, ale i organizační skupiny a platformy mobilních zařízení přidružené ke každému případu použití.

## <a name="device-ownership"></a>Vlastnictví zařízení
Můžete začít rekapitulací cílů a úkolů organizace při nasazení Intune, které vám pomohou identifikovat hlavní scénáře použití nasazeného řešení. Při sestavování plánu nasazení Intune si odpovězte na následující otázky:

-   Plánujete podporu zařízení patřících společnosti?

-   Plánujete podporu vlastních zařízení uživatelů (BYOD)?

Tyto možnosti se vzájemně nevylučují. Možná zjistíte, že ke splnění cílů organizace potřebujete podporovat obě formy vlastnictví zařízení. Dílčí případy použití vám pomohou vyjasnit, kde použít různé zásady správy zařízení.

### <a name="user-type-or-device-role"></a>Typ uživatele nebo role zařízení

Zjistěte, jestli každý scénář použití také obsahuje dílčí scénáře. Organizace například identifikuje požadavky na podporu scénáře firemního použití, který zahrnuje další, dílčí případy použití založené na typu uživatele nebo roli zařízení. Příklad:

-   Informatik

-   Vedení

-   Kiosk

Tady je několik příkladů scénářů použití a dílčích scénářů použití:

| **Případy použití** | **Dílčí případy použití** |
|:---:|:---:|
| Firemní | Informatik |              
| Firemní | Vedení |           
| Firemní | Kiosk |
| Uživatelé s vlastním zařízením | Informatik |           
| Uživatelé s vlastním zařízením | Vedení |

Pokud chcete zadat scénáře použití a dílčí scénáře použití ve vaší organizaci, můžete si [stáhnout šablonu předchozí tabulky](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

## <a name="organizational-groups-for-your-scenarios"></a>Organizační skupiny pro scénáře

Teď potřebujete určit organizační skupiny přidružené ke každému hlavnímu a dílčímu scénáři použití. Například:

| **Případy použití** | **Dílčí případy použití** | **Organizační skupiny** |
|:---:|:---:|:---:|
| Firemní | Informatik | Personalistika, finance |               
| Firemní | Vedení | Personalistika, finance |            
| Firemní | Kiosk | Maloobchod |
| Uživatelé s vlastním zařízením | Informatik | Marketing, prodej |            
| Uživatelé s vlastním zařízením | Vedení | Marketing, prodej |


## <a name="mobile-device-platforms-for-your-scenarios"></a>Platformy mobilních zařízení pro vaše scénáře

V dalším kroku budete identifikovat platformy mobilních zařízení přidružené ke každému scénáři použití. Může jich být více.

Scénář firemního použití může například podporovat platformy zařízení iOS a Android Samsung KNOX. Zásady pro uživatele s vlastním zařízením (BYOD) ale mohou zahrnovat podporu dalších platforem mobilních zařízení, jako je Android (jiný než Samsung KNOX) a Windows 10 Mobile. Pokud budeme vycházet z předchozích příkladů, přidružíme každému scénáři použití následující platformy mobilních zařízení.

| **Případy použití** | **Dílčí případy použití** | **Skupiny** | **Platformy zařízení** |   
|:---:|:---:|:---:|:---:|
| Firemní | Informatik | Personalistika, finance | iOS |                                                           
| Firemní | Vedení | Personalistika, finance | iOS |                                                           
| Firemní | Kiosk | Maloobchod | Android |
| Uživatelé s vlastním zařízením | Informatik | Marketing, prodej | iOS |                                                           
| Uživatelé s vlastním zařízením | Vedení | Marketing, prodej | iOS |

## <a name="next-steps"></a>Další kroky

V další části najdete pokyny, [jak identifikovat požadavky na Intune pro jednotlivé scénáře použití](planning-guide-requirements.md).
