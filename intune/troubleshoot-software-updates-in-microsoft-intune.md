---
title: Řešení potíží s aktualizacemi softwaru v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Řešte problémy s aktualizacemi softwaru ve službě Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: d17b70f4-17b4-4d89-88fd-70fa4f34fbea
ROBOTS: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: ee5ed6339efff4b3e32a9c10ac756d7f8bec6260
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402624"
---
# <a name="troubleshoot-software-updates-in-microsoft-intune"></a>Řešení potíží s aktualizacemi softwaru ve službě Microsoft Intune

Vyřešit problémy s aktualizacemi softwaru v Microsoft Intune. Chcete-li zobrazit seznam kódů chyb a popisy, přejděte na [kódy chyb agenta aktualizací softwaru v Microsoft Intune](software-update-agent-error-codes.md).

## <a name="windows-7-devices-with-many-superseded-updates-stop-reporting-to-intune"></a>Zařízení s Windows 7 s mnoha nahrazených aktualizací zastavit odesílajících sestavy do Intune

Microsoft Intune klientů může docházet k jedné nebo více z následujících příznaků:

- Zařízení náhle přestanou předávat hlášení do Intune.  
- Zařízení docházet k vysoké využití procesoru.
- Aplikace se instalují pomalu po instalaci přes Intune.
- Microsoft Intune Center se zobrazuje následující chyba: `An error occurred while updating your computer. Error found: Code 0x800705b4`.
- V konzole správce Intune > skupiny > všechna zařízení > ukazuje stav: `One or more agents that are installed on this computer have errors. The information for this computer may not be accurate or up-to-date.`

Tomuto problému může dojít, pokud nahrazené, že se aktualizace (aktualizace jsou nahrazeny jinou aktualizací) nebyly odmítnuty po delší dobu. Během některých procesů, například při instalaci aplikace Windows kontroluje všechny Nahrazené aktualizace v pořadí tak, aby správně mapovat aktualizace a jejich následníky. Pokud seznam nahrazených aktualizací získá příliš velký, tato kontrola může způsobit vysoké využití procesoru z důvodu zatížení a potřebného času. Tento problém se týká především zařízení s Windows 7 z důvodu velký počet nahrazených aktualizací, které jsou k dispozici pro Windows 7. Novější operační systémy nemusí mít k dispozici tolik nahrazených aktualizací a nemusí být náchylné k tomuto problému.

**Řešení**

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **aktualizace softwaru**.
3. Zamítněte všechny Nahrazené aktualizace, které se můžou vztahovat na Windows 7 nebo k aplikacím, jako je například Microsoft Office, které byly nainstalovány na příslušné klienty.
4. Restartujte příslušné klienty.

Pokud používáte systém Windows 7, ujistěte se, že je nainstalovaná aktualizace:[3050265 Windows Update Client pro Windows 7: Červen 2015](https://support.microsoft.com/kb/3050265).

## <a name="next-steps"></a>Další postup

Získat [podpory Microsoftu](get-support.md), nebo použijte [komunitní fóra](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).