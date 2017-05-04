---
title: "Známé problémy v Microsoft Intune Preview"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si informace o známých problémech ve verzi Preview."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 08e2f65bcd600489f6599d37e5ef56c205176cd7
ms.lasthandoff: 04/25/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Známé problémy v Microsoft Intune Preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Toto téma vám pomůže dozvědět se více o známých problémech v Intune Preview.

Pokud chcete nahlásit chybu, která tu není uvedená, [otevřete žádost o podporu](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Pokud chcete zažádat o přidání nové funkce do Intune, zvažte vyplnění zprávy na webu [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Skupiny vytvořené pomocí Intune během migrace můžou ovlivnit funkčnost jiných produktů Microsoftu

Při migraci z klasického portálu Intune na portál Azure Portal se může zobrazit nová skupina s názvem **Všichni uživatelé – b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Všimněte si, že tato skupina obsahuje všechny uživatele ve vašem Azure Active Directory, ne jenom uživatele s licencí Intune. To může způsobit problémy s jinými produkty Microsoftu, pokud očekáváte, že někteří existující nebo noví uživatelé nebudou členem žádné skupiny.

### <a name="altering-groups-created-by-intune-during-migration-will-delay-migration"></a>Změna skupin vytvořených pomocí Intune během migrace zpozdí migraci

Během přípravy na migraci se skupiny zkopírují z Intune do Azure AD. Všechny další změny, které provedete v klasickém portálu Intune, se aktualizují ve skupině Azure AD. Žádné změny provedené v Azure AD se však nesynchronizují zpět do klasické konzoly Intune. Následkem toho se migrace na portál Azure Portal nemusí povést a může docházet ke zpožděním v migraci.

### <a name="compliance-policies-from-intune-will-not-show-up-in-new-console"></a>Zásady dodržování předpisů z Intune se v nové konzole nezobrazí 

Zásady dodržování předpisů, které jste vytvořili v klasickém portálu Intune, se migrují, ale na portálu Azure Portal se nezobrazí. Důvodem je změna návrhu na portálu Azure Portal. Zásady dodržování předpisů, které jste vytvořili v klasickém portálu Intune, se stále uplatňují, ale musíte je prohlížet a upravovat na klasické portálu.
A nové zásady dodržování předpisů, které vytvoříte na portálu Azure Portal, se nezobrazí v klasickém portálu.
Další informace najdete v článku [Co je dodržování předpisů zařízením](https://docs.microsoft.com/intune-azure/set-device-compliance/what-is-device-compliance).




### <a name="administration-and-accounts"></a>Správa a účty

Globální správci (také označovaní jako správci tenanta) mohou dál vykonávat běžné úkony správy bez samostatné licence služby Intune nebo sady EMS (Enterprise Mobility Suite). Pokud ale chtějí globální správci službu používat, například zaregistrovat si svoje vlastní nebo firemní zařízení nebo používat portál společnosti Intune, budou potřebovat licenci služby Intune nebo sady EMS jako ostatní uživatelé.

### <a name="apple-enrollment-profile-migration"></a>Migrace profilu registrace Apple
Během pár následujících měsíců vám Intune umožní spravovat vaše registrace v Apple Device Enrollment Programu a Apple Configuratoru prostřednictvím nového portálu Azure Portal. Pokud odstraníte token Apple Device Enrollment Programu a neodešlete aktualizovaný token, původní token se v rámci migrace vašeho účtu Intune na novém portálu Azure Portal obnoví. Pokud chcete tento token odebrat a zabránit registraci v programu DEP, stačí token odstranit z portálu Azure Portal. 

