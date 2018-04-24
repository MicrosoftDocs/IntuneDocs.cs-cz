---
title: Odebrání zařízení s Windows z Intune | Microsoft Docs
description: Popisuje odebrání zařízení s Windows z Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/28/2018
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
ms.openlocfilehash: 9f9051fb393c82031d581f7fec731a3b148cbf2e
ms.sourcegitcommit: 7f46e9990797bdfa669ccba2077721f1bc70c07e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/04/2018
---
# <a name="remove-your-windows-device-from-intune"></a>Odebrání zařízení s Windows z Intune

Pokud jste zařízení s Windows zaregistrovali do Intune, ale nechcete ho používat pro přístup k pracovnímu nebo školnímu e-mailu, aplikacím nebo jiným prostředkům, musíte ho odebrat ze správy. Jakmile zařízení odeberete z Intune, ztratíte k těmto prostředkům přístup. Další informace o tom, co se stane, když zařízení odeberete ze správy, najdete v tématu [Co se stane, když zrušíte registraci zařízení v Intune](what-happens-if-you-unenroll-your-device-from-intune-windows.md).

## <a name="remove-your-windows-10-device"></a>Odebrání zařízení s Windows 10

1.  V seznamu aplikací klepněte na aplikaci **Company Portal** .

2.  Přihlaste se pomocí přihlašovacích údajů svého pracovního nebo školního účtu.

3.  V části **Moje zařízení**vyberte zařízení, jehož registraci chcete zrušit.

4.  Klepněte na **Odebrat** &gt; **Odebrat**.

## <a name="remove-your-windows-81-computer"></a>Odebrání počítače s Windows 8.1

1.  Přejděte na **Nastavení počítače** &gt; **Síť** &gt; **Pracoviště**.

2.  V části **Připojení pracovního místa** vyberte **Odejít**.

3.  V části **Zapnout správu zařízení** vyberte **Vypnout**.

4.  V automaticky otevíraném okně, které se otevře, vyberte **Vypnout**.

## <a name="remove-your-windows-phone-81-mobile-device"></a>Odebrání mobilního zařízení Windows Phone 8.1

1.  Klepněte na **Nastavení** &gt; **Pracoviště**.

2.  Klepněte na pracovní účet, jehož registraci chcete zrušit.

3.  V dolní části obrazovky klepněte na **Odstranit**.

4.  V dialogovém okně **Odstranit účet** klepněte na **Odstranit**.

## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>Odebrání osobních údajů po odebrání aplikace Portál společnosti

Aplikace Portál společnosti ukládá do zařízení s Windows dva druhy dat:

-   **Diagnostické protokoly**: Standardní data o aktivitě aplikací, která shromažďuje Microsoft, třeba jak dlouho byla aplikace otevřena nebo jestli havarovala, se vymažou automaticky při odebrání zařízení z webu Portál společnosti.
-   **Mezipaměť aplikace**: Do ní se ukládají některé podpůrné soubory, které aplikace potřebuje k práci, například ikony a nastavení.

K úplnému odstranění těchto informací je potřeba provést několik kroků.

### <a name="uninstall-the-company-portal"></a>Odinstalace Portálu společnosti  

Když [odinstalujete aplikaci Portál společnosti](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs), odeberou se některá data aplikace uložená v zařízení.  

### <a name="reset-the-company-portal"></a>Resetování Portálu společnosti

Zbývající data aplikace Portál společnosti resetujete tím, že v Nastavení tuto aplikaci resetujete. Otevřete **Nastavení** > **Aplikace a funkce** > **Portál společnosti** > **Upřesnit možnosti** > **Resetovat**.

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://portal.manage.microsoft.com#HelpDeskDialog).