---
title: "Obnovení zařízení s iOS spravovaných přes Intune ze zálohy | Microsoft Intune"
description: "Nabídněte koncovým uživatelům pokyny, jak svoje zařízení po obnovení ze zálohy znovu zaregistrují."
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 612b0954a81de1ee8d4a1e96c7440239437dec14
ms.openlocfilehash: 5fc4423f8fd0c5829be5fe6c96949e126991e430


---

# Obnovení zařízení s iOS spravovaných přes Intune ze zálohy

Občas budete vy nebo vaši uživatelé potřebovat obnovit zařízení s iOS ze zálohy, třeba když uživatel dostane nové zařízení. Toto téma vysvětluje dodatečný postup, který budete muset udělat, abyste po obnovení zařízení nastavili správu přes Intune.

## Obnovení záloh do stejného zařízení

Pokud zálohu obnovujete do stejného zařízení, obnoví se zároveň stav registrace tohoto zařízení. Nemusíte dělat nic dalšího.

## Obnovení záloh do jiných zařízení

Pokud zálohu obnovujete do jiného zařízení, neobnoví se v novém zařízení automaticky stav registrace. Uživatelé musí v aplikaci Portál společnosti verze 2.1.22 nebo novější standardním postupem [zaregistrovat své zařízení s iOS do Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

> [!NOTE]
> Pokud na koncové uživatele uplatňujete zásady podmíněného přístupu, budou mít k firemnímu e-mailu přístup až po opětovné registraci.

> [!TIP]
> Tady je příklad sdělení pro vaše uživatele: Pokud chcete svoje nové zařízení zaregistrovat, ověřte, že používáte aplikaci Portál společnosti verze 2.1.22 nebo novější. Verzi zkontrolujete tak, že otevřete aplikaci Portál společnosti, klepnete na tlačítko Nabídka vpravo nahoře a pak klepnete na O produktu. Pokud používáte starší verzi, ukončete aplikaci Portál společnosti a otevřete App Store. Klepněte na tlačítko Aktualizace v pravém dolním rohu a pak klepněte na tlačítko Aktualizovat vedle položky Portál společnosti v seznamu. Po dokončení aktualizace spusťte aplikaci Portál společnosti a [zaregistrujte zařízení s iOS do Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).



<!--HONumber=Oct16_HO2-->


