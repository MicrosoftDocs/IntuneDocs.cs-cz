---
title: "Vyřazení zařízení | Microsoft Intune"
description: "Při odebírání zařízení ze správy Intune podporuje tato služba selektivní i úplné vymazání, přičemž se odeberou příslušné zásady a portál společnosti."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: 42b723f99c34f03060140e5f280b87287d108ae1


---

# Vyřazení zařízení ze správy Intune

Ať jsou zařízení vlastněná firmou nebo v osobním vlastnictví, existuje chvíle, kdy musí být spravované zařízení vyřazené ze správy v Intune. Vyřazení zařízení je poměrně jednoduché, můžete provést buď selektivní vymazání nebo úplné vymazání.
## Vymazání dat a aplikací ze zařízení
Selektivní vymazání i úplné vymazání odebere zařízení ze správy Intune odebráním zásad a portálu společnosti, což znamená, že zařízení už nemá pověřovací údaje potřebné k přihlášení k firemním prostředkům, jako je Microsoft SharePoint, e-mail nebo Office 365.

[Selektivní vymazání](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) by se mělo upřednostňovat u zaměstnanců, kteří mají v Intune zaregistrované své vlastní zařízení, protože vymazání dat se v tomto případě nedotkne osobních údajů uložených na zařízení. Odeberou se jenom firemní data.

Pro zařízení vlastněná společností můžete také použít [úplné vymazání](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), které resetuje zařízení do továrního nastavení.

## Odvolání přístupu k síti společnosti
V případě, že vyřazujete zařízení, protože zaměstnanec odchází ze společnosti a nevrátil hardware vlastněný společností, můžete zařízení také [vzdáleně uzamknout](use-remote-lock-and-passcode-reset-in-microsoft-intune.md). Tím se zajistí, že budou jak informace společnosti, tak i její hardware chráněny před zneužitím, i když může být nutné zařízení odepsat jako ztrátu.

Také můžete chtít odvolat licenci pro uživatelský účet Intune zaměstnance. Tím se licence uvolní a je možné ji přiřadit novému uživatelskému účtu.

## Vyřazení zařízení
V některých případech zařízení samotné dosáhne konce své životnosti. V takových případech [obnovením zařízení do továrního nastavení](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) s plným vymazáním odeberete všechna data a také odebere zařízení ze služby Intune. Pak můžete hardware vyřadit z evidence podle zásad vaší společnosti.

### Související témata
[Lepší ochrana dat s využitím úplného nebo selektivního vymazání](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


