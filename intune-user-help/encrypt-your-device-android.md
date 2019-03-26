---
title: Šifrování zařízení s Androidem pro portál společnosti Intune | Dokumentace Microsoftu
description: Postup zapnutí šifrování zařízení na zařízení s Androidem
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ad953049b9d2efd6f7a828ee70b5e1cede4ee68
ms.sourcegitcommit: d0749cbc68df41893742f5187ac378a5ade824f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/25/2019
ms.locfileid: "58406251"
---
# <a name="encrypt-your-android-device"></a>Šifrování zařízení s Androidem

Šifrování zařízení chrání své soubory a složky před neoprávněným přístupem, pokud dojde ke ztrátě nebo odcizení zařízení. Po zapnutí šifrování zařízení pouze uživatelé, kteří mají správné heslo nebo PIN kód bude moct přihlásit k zařízení. 

Pro přístup k pracovním nebo školním prostředkům, vaše organizace může vyžadovat šifrování zařízení s Androidem. Některé novější zařízení s Androidem se šifrují ve výchozím nastavení, out-of-the-box.  

Pokud se zobrazí zpráva v aplikaci portál společnosti, které potřebujete k zašifrování zařízení, proveďte následující kroky. 

> [!Note]
> Některá zařízení s Androidem od Huawei Vivo a OPPO nelze zašifrovat. Další informace najdete [tady](your-device-appears-encrypted-but-cp-says-otherwise-android.md).  

1.  Nastavte zámek obrazovky zařízení.  
    a. Přejděte na **nastavení** > **zamykací obrazovka a zabezpečení** > **typ zámku obrazovky**.  
    b. Vyberte buď **PIN**, **heslo**, nebo **vzor**.  
    c. Postupujte podle pokynů na obrazovce konfigurace svůj zámek obrazovky.  

2. Přejděte zpět na **zamykací obrazovka a zabezpečení** a vyberte **zabezpečené spuštění**.
3. Zvolte **vyžadovat PIN, když zařízení Zapne** > **OK**.
4. Zadejte svůj PIN kód k potvrzení a k šifrování zařízení.
5. Otevřete aplikaci portál společnosti, vyberte zařízení a klepněte na **zkontrolovat nastavení zařízení**.  

Pravděpodobně nemáte zařízení s Androidem 4.4 nebo starší **zabezpečené spuštění** možnost. V takovém případě proveďte následující kroky k zašifrování zařízení.

1. Přejděte na **nastavení** > **zabezpečení** > **šifrování zařízení**. Na obrazovce popisky se liší mezi zařízení s Androidem. Pokud se nezobrazí **šifrování zařízení** možnost, vrátit se změnami:
    * **Úložiště** > **šifrování úložiště**
    * **Úložiště** > **zamykací obrazovka a zabezpečení** > **další nastavení zabezpečení** 

2. Postupujte podle pokynů na obrazovce. Během šifrování se může několikrát restartovat zařízení.
3. Otevřete aplikaci portál společnosti, vyberte zařízení a klepněte na **zkontrolovat nastavení zařízení**.  

## <a name="troubleshoot"></a>Řešení potíží  
**Problém**: Jste už zašifrovali zařízení a

- Tlačítko pro šifrování je zakázané.
- Zobrazí se zpráva s informacemi o tom, že je stále nutné nastavit šifrování.
- Bude docházet k chybám při pokusu o použití aplikace Portál společnosti.

**Možná řešení**

- Ujistěte se, že je zařízení nabité a připojené k nabíječce.  
- Zkontrolujte, že jste na zařízení nastavili PIN kód nebo heslo.  

Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu (kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980)) nebo napište <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">týmu Microsoft Android</a>.  
