---
title: Jak chránit zařízení s Androidem pomocí šifrování | Dokumentace Microsoftu
description: Postup při registraci zařízení s Androidem
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/14/2017
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
ms.openlocfilehash: 115025d60038daea6f43c97cbdc03a20d5b0bf59
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "55838168"
---
# <a name="how-to-protect-your-android-device-using-encryption"></a>Jak chránit zařízení s Androidem pomocí šifrování

Při šifrování zařízení balíte informace v zařízení do vrstvy ochranného kódu, který brání neoprávněným osobám v přístupu k nim. Jako další krok k zabezpečení vašich informací vyžaduje vaše organizace, abyste si zašifrovali zařízení s Androidem. Teprve pak budete mít přístup k firemním souborům, e-mailu nebo datům.

> [!Note]
> Určitá zařízení Android, včetně některých od výrobce Huawei, Vivo a OPPO, nelze zašifrovat. Další informace najdete [tady](your-device-appears-encrypted-but-cp-says-otherwise-android.md).

Pokud byste zrušili registraci telefonu, zůstane zašifrovaný.

1.  Zkontrolujte, že je pro vaše zařízení nastavený kód PIN nebo heslo zamykací obrazovky.

2.  V **Nastavení** zvolte **Zabezpečení** > **Šifrovat zařízení**.
    (Na některých telefonech budete muset najít možnost šifrování tak, že zvolíte **Úložiště** > **Šifrování úložiště** nebo **Úložiště** > **Zamykací obrazovka a zabezpečení** > **Další nastavení zabezpečení**.)

3.  Postupujte podle pokynů na obrazovce. Během šifrování se zařízení může několikrát restartovat.

### <a name="what-to-do-if-you-have-issues"></a>Co dělat v případě problémů
**Problém**: Vaše zařízení jste už zašifrovali a se zobrazí jedna z následujících akcí:

- Tlačítko pro šifrování je zakázané.
- Zobrazí se zpráva s informacemi o tom, že je stále nutné nastavit šifrování.
- Bude docházet k chybám při pokusu o použití aplikace Portál společnosti.

**Možná řešení**

- Ujistěte se, že je zařízení nabité a připojené k nabíječce.
- Zkontrolujte, že jste na zařízení nastavili PIN kód nebo heslo.
- Pokud jste na zařízení nastavili PIN nebo heslo, vyzkoušejte následující postup, který může firemní podpora vyžadovat kvůli většímu zabezpečení zařízení. Zobrazované názvy nabídek se mohou mírně lišit od názvů nabídek uvedených v postupech podle toho, jaký máte typ zařízení s Androidem.

    1. Přejděte na **Nastavení** > **Zamykací obrazovka a zabezpečení** > **Zámek obrazovky**. Potvrďte aktuální PIN kód nebo heslo.

    2. Na obrazovce **Vyberte zámek obrazovky** vyberte typ zámku obrazovky, který chcete použít. 

    3. Po zvolení zámku obrazovky se vraťte na obrazovku **Zamykací obrazovka a zabezpečení** a vyberte **Zabezpečené spuštění**. 
    
    4. Na obrazovce **Zabezpečené spuštění** klepněte na **Ke spuštění zařízení požadovat kód PIN** a pak na **Pokračovat**.

    5. Zvolte kód PIN (můžete zadat stejný jako ten, který jste zadali dříve) a klepněte na **Potvrďte kód PIN**.

    6. Otevřete Portál společnosti, vyberte své zařízení a klepněte na možnost **Kontrola dodržování předpisů**.

Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu (kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980)) nebo napište <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">týmu Microsoft Android</a>.
