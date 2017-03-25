---
title: "Známé problémy v Microsoft Intune Preview"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si informace o známých problémech ve verzi Preview."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: ec3f87994b19591bda4ec201eac3c839798d634c
ms.lasthandoff: 03/15/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Známé problémy v Microsoft Intune Preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Toto téma vám pomůže dozvědět se více o známých problémech v Intune Preview.

Pokud chcete nahlásit chybu, která tu není uvedená, [otevřete žádost o podporu](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Pokud chcete zažádat o přidání nové funkce do Intune, zvažte vyplnění zprávy na webu [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## <a name="administration-and-accounts"></a>Správa a účty

- Globální správci (také označovaní jako správci tenanta) mohou dál vykonávat běžné úkony správy bez samostatné licence služby Intune nebo sady EMS (Enterprise Mobility Suite). Pokud ale chtějí globální správci službu používat, například zaregistrovat si svoje vlastní nebo firemní zařízení nebo používat portál společnosti Intune, budou potřebovat licenci služby Intune nebo sady EMS jako ostatní uživatelé.

## <a name="apple-enrollment-profile-migration"></a>Migrace profilu registrace Apple
- Během pár následujících měsíců vám Intune umožní spravovat vaše registrace v Apple Device Enrollment Programu a Apple Configuratoru prostřednictvím nového portálu Azure Portal. Pokud odstraníte token Apple Device Enrollment Programu a neodešlete aktualizovaný token, původní token se v rámci migrace vašeho účtu Intune na novém portálu Azure Portal obnoví. Pokud chcete tento token odebrat a zabránit registraci v programu DEP, stačí token odstranit z portálu Azure Portal. 

