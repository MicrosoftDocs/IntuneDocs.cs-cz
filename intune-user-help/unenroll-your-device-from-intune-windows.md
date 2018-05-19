---
title: Odebrání zařízení s Windows z Intune
description: Popisuje odebrání zařízení s Windows z Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 018bda65-7238-41f5-b92a-e5f67b7fe085
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 1dd64250c1996c6b13c62f80572282d639112ba6
ms.sourcegitcommit: 8ee543c864097dc195b6f440471dca713fc21ed2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2018
---
# <a name="remove-your-windows-device-from-intune-management"></a>Odebrání zařízení s Windows ze systému správy Intune

Registrované zařízení s Windows můžete z Intune odebrat, pokud už nepotřebujete:  
* Používat zařízení pro práci nebo studium 
* Přistupovat k pracovním nebo školním e-mailům, aplikacím nebo jiným prostředkům

Jakmile zařízení odeberete, nebudete z něj moct přistupovat ke školním nebo pracovním prostředkům. Mezi zařízení s Windows, která můžete z Intune odebrat, patří:  
* Zařízení s Windows 10 
* Počítač s Windows 8.1
* Mobilní zařízení s Windows 8.1
 
Další informace o tom, co se stane, když zařízení odeberete ze systému správy Intune, najdete v tématu s informacemi o tom, [co se stane, když zařízení odeberete z Intune](what-happens-if-you-unenroll-your-device-from-intune-windows.md).

## <a name="remove-your-windows-10-device"></a>Odebrání zařízení s Windows 10
Provedením následujících kroků odeberte zařízení s Windows 10 z Intune.

### <a name="via-the-company-portal-app"></a>Prostřednictvím aplikace Portál společnosti

1. Otevřete aplikaci Portál společnosti.
2. Přihlaste se pomocí přihlašovacích údajů svého pracovního nebo školního účtu.
3. V části **Moje zařízení** vyberte zařízení, které chcete odebrat.
4. V pravém horním rohu aplikace vyberte ikonu **Více**.
5. Vyberte **Odebrat**. 
6. Odebrání zařízení potvrďte výběrem možnosti **Odebrat zařízení**.

### <a name="via-device-settings-app"></a>Prostřednictvím aplikace Nastavení zařízení
1. Otevřete aplikaci Nastavení. 
2. Vyberte **Účty** > **Přístup do práce nebo do školy**.
3. Vyberte připojený účet, který chcete odebrat > **Odpojit**.
4. Odebrání zařízení potvrďte výběrem možnosti **Ano**.

## <a name="remove-your-windows-81-computer"></a>Odebrání počítače s Windows 8.1
Provedením následujících kroků odeberte počítač s Windows 8.1 z Intune.

1.  Přejděte na **Nastavení počítače** > **Síť** > **Pracoviště**.
2.  V části **Připojení pracovního místa** vyberte **Odejít**.
3.  V části **Zapnout správu zařízení** vyberte **Vypnout**.
4.  V automaticky otevíraném okně, které se otevře, vyberte **Vypnout**.

## <a name="remove-your-windows-81-mobile-device"></a>Odebrání mobilního zařízení s Windows 8.1
Provedením následujících kroků odeberte mobilní zařízení s Windows 8.1 z Intune.

1.  Přejděte na **Nastavení** > **Pracoviště**.
2.  Klepněte na pracovní účet, jehož registraci chcete zrušit.
3.  V dolní části obrazovky klepněte na **Odstranit**.
4.  V dialogovém okně **Odstranit účet** klepněte na **Odstranit**.  
## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>Odebrání osobních údajů po odebrání aplikace Portál společnosti
Aplikace Portál společnosti ukládá do zařízení s Windows dva druhy dat:

-   **Diagnostické protokoly**: Standardní data o aktivitě aplikací, která shromažďuje Microsoft, se vymažou automaticky při odebrání zařízení z Portálu společnosti. Data o aktivitě aplikací jsou například data o tom, jak dlouho byla aplikace otevřena nebo jestli se chybově ukončila.
-   **Mezipaměť aplikace**: Podpůrné soubory, které aplikace potřebuje k práci, například ikony a nastavení.

K úplnému odstranění těchto informací je potřeba provést několik kroků.

1. Odinstalujte Portál společnosti. Když [odinstalujete aplikaci Portál společnosti](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs), odeberou se některá data aplikace uložená v zařízení.  

2. Pokud chcete obnovit uložená data aplikace, resetujte Portál společnosti. Otevřete aplikaci **Nastavení** a vyberte > **Aplikace** > **Portál společnosti** > **Upřesnit možnosti** > **Resetovat**. 

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://portal.manage.microsoft.com#HelpDeskDialog).