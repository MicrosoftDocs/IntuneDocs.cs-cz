---
title: Zobrazit a opravit osobní údaje
titleSuffix: Microsoft Intune
description: Přečtěte si, jak zobrazit a opravit osobní údaje.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1ba77bc7-505e-4eca-a49e-dcdaa75d0043
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9b6ca291f55511be9e88b0ff898d9383691542bf
ms.sourcegitcommit: a2654f3642b43b29ab0e1cbb2dfa2b56aae18d0e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72310905"
---
# <a name="view-and-correct-personal-data"></a>Zobrazit a opravit osobní údaje

Správci Intune můžou na základě svých přístupových oprávnění zobrazit některá osobní data, ale jenom koncoví uživatelé můžou změnit svoje osobní údaje svého zařízení.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-dsr-and-stp-note.md)]


## <a name="view-personal-data"></a>Zobrazit osobní údaje

Správci můžou v uživatelském rozhraní Intune zobrazit osobní informace koncového uživatele v různých oknech. Následující články vysvětlují, co Správci informací dělají a nemají přístup k těmto akcím:
- V [části Podrobnosti o zařízení](../remote-actions/device-inventory.md) v Intune se dozvíte, jak můžete zkontrolovat podrobnosti o zařízení koncového uživatele.
- [Monitorování informací a přiřazení aplikace](../apps/apps-monitor.md) vysvětluje, jak zobrazit podrobnosti o aplikacích nainstalovaných na zařízení koncového uživatele.
- [Jaké informace může moje společnost vidět po registraci zařízení? článek](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) poskytuje koncovým uživatelům seznam dat, která jejich společnost uvidí a neuvidí. Je vhodné jasně říct uživatelům, jaký druh dat shromažďujete a proč je shromažďujete. Tento článek může být prvním krokem této transparentnosti.

### <a name="who-can-view-the-data"></a>Kdo může data zobrazit?

Společnost Microsoft používá přísné ovládací prvky pro řízení přístupu k zákaznickým datům. poskytuje nejnižší úroveň přístupu, která je nutná k dokončení klíčových úloh a odvolávání přístupu, pokud již nepotřebujete. 

Přístup k osobním údajům koncových uživatelů můžete zabezpečit a řídit pomocí řízení správy na základě rolí (RBAC). Další informace najdete v tématu [RBAC s Microsoft Intune](../fundamentals/role-based-access-control.md).

Další informace o praxi s daty společnosti Microsoft najdete v tématu [prohlášení o zásadách ochrany osobních údajů služby Microsoft Online Services](https://go.microsoft.com/fwlink/p/?linkid=131004&clcid=0x409). 

## <a name="correct-end-user-personal-data"></a>Opravit osobní údaje koncového uživatele

Správci nemůžou aktualizovat informace specifické pro zařízení nebo aplikace. Pokud chce koncový uživatel opravit jakákoli osobní data (například název zařízení), musí tak učinit přímo na svém zařízení. Tyto změny se synchronizují při příštím připojení k Intune.


## <a name="next-steps"></a>Další kroky

Zjistěte, jak v Intune [Auditovat, exportovat nebo odstraňovat](privacy-data-audit-export-delete.md) osobní údaje.
