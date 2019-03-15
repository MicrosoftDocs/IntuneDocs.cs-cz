---
title: Jaké informace vaše společnost uvidí při registraci zařízení?
description: Vysvětluje, co správce IT uvidí a neuvidí na vašem spravovaném zařízení.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 12655728-a1af-4d89-97bc-925fe36c0dc4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.collection: M365-identity-device-management
ms.openlocfilehash: 91ea3aab5cd04624bfa036615b8d7710573bcae1
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "55846974"
---
# <a name="what-information-can-my-organization-see-when-i-enroll-my-device"></a>Jaké informace moje organizace uvidí, když zaregistruji své zařízení?

Při registraci zařízení do Microsoft Intune nevidí organizace vaše osobní údaje. Při registraci zařízení dáváte organizaci svolení k zobrazení určitých informací o vašem zařízení, jako je model zařízení a sériové číslo. Tyto informace pomáhají vaší organizaci chránit firemní data v zařízení.

**Údaje, které vaše organizace nikdy neuvidí:**

- Historie volání a procházení webu
- Textové a e-mailové zprávy
- Kontakty
- Kalendář
-   Hesla
- Obrázky, včetně těch, které jsou ve fotografických aplikacích nebo mezi obrázky z fotoaparátu
- Soubory

**Údaje, které vaše organizace uvidí vždy:**

- Model zařízení, jako je Google Pixel
- Výrobce zařízení, například Microsoft
- Operační systém a jeho verzi, například iOS 12.0.1
- Názvy aplikací, například Microsoft Word: Na osobních zařízeních organizaci uvidí jenom vaše aplikace se správou inventáře. Na zařízeních ve firemním vlastnictví uvidí vaše organizace inventář všech aplikací.
- Vlastník zařízení
- Název zařízení
- Sériové číslo zařízení
- IMEI

**Údaje, které vaše organizace může vidět:**

-  Telefonní číslo: Pro **podnikové**– zařízení vlastněná společností, můžete zobrazit celé své telefonní číslo. U zařízení v **osobním** vlastnictví vidí organizace jen poslední čtyři číslice vašeho telefonního čísla. **Typ vlastnictví** jednotlivých zařízení zobrazíte tak, že otevřete stránku **Podrobnosti zařízení** určitého zařízení.
- Zařízení místo úložiště: Pokud nemůžete nainstalovat požadované aplikace, podívejte se na prostor úložiště vašeho zařízení zjistit, pokud je příliš málo místa vaší organizace.  
-  Umístění: Vaše organizace nikdy neuvidí polohu vašeho zařízení, pokud potřebujete obnovit zařízení ke ztrátě, pod dohledem s Iosem. Přejděte [dokumentaci Apple iOS](https://go.microsoft.com/fwlink/?linkid=853816) získat další informace o zařízeních pod dohledem.  
- Inventář aplikací: Pokud vaše organizace používá Mobile Threat Defense, bude moct zobrazit podrobností o aplikacích, které jsou na zařízení s Iosem. Přečtěte si další informace o [ochraně před mobilním hrozbami](you-are-prompted-to-install-mtd-ios.md).
- Informace o síti: Některé informace o připojení sítě pro zařízení s Androidem, může být k dispozici podpora vaší organizace. Pokud vaše organizace například vyžaduje, aby zařízení zůstala v určité budově, identifikuje vaše zařízení síť, ke které je připojené. 
