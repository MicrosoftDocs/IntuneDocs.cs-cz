---
title: "Odeslání protokolů s diagnostickými daty ze zařízení správci IT e-mailem | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 85c868e7-8d63-480c-9770-4e99614a5c94
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08eeb1f330ed8fcea5da41f71ded0ccf124da7c5
ms.openlocfilehash: 9446df0381a2b2a1a6322f8f59523ce78406f25a


---


# Odeslání protokolů s diagnostickými daty ze zařízení správci IT e-mailem

Pokud při práci se školními nebo podnikovými aplikacemi nebo s aplikací Portál společnosti dojde k chybě v zařízení s Androidem, můžete odeslat protokoly s diagnostickými daty, které vašemu správci IT pomůžou chybu pochopit a vyřešit. Pokud chcete do protokolů zahrnout všechny podrobnosti, které vašemu správci IT pomůžou problém pochopit, zapněte funkci Podrobné protokolování. O [podrobném protokolování](use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android.md) si můžete přečíst víc.

Zapnutí podrobného protokolování:

1.  Otevřete aplikaci Portál společnosti.

2.  Klepněte na **Nabídka** &gt; **Nastavení**.

    > [!NOTE]
    > Podle toho, jaké zařízení se systémem Android máte, může být **Nabídka** buď softwarové, nebo hardwarové tlačítko.

3.  V části **Diagnostická data** klepněte na **Odeslat data**.

    > [!NOTE]
    > **Jenom pokud používáte zařízení se systémem Android 6.0 nebo novějším:** Když klepnete na **Odeslat data**, zobrazí se zpráva **Povolit pro Portál společnosti přístup k fotkám, médiím a souborům ve vašem zařízení?**.

    Tato zpráva je zavádějící, protože **Microsoft nikdy nezískává přístup k fotografiím, médiím a souborům na vašem zařízení!** Text zprávy určuje společnost Google a Microsoft ho nemůže změnit.  Když povolíte přístup, povolíte na svém zařízení jenom zápis datových protokolů na kartu SD zařízení, takže tyto protokoly můžete přesouvat pomocí kabelu USB.

    Pokud přístup odepřete, při příštím klepnutí na **Odeslat data** se zpráva zobrazí znovu, ale další zprávy už můžete vypnout zaškrtnutím políčka **Příště se už neptat**.  Pokud se později rozhodnete povolit přístup, použijte možnost **Nastavení** &gt; **Aplikace** &gt; **Portál společnosti** &gt; **Oprávnění** &gt; **Úložiště** a pak tato oprávnění aktivujte.

4.  Podle pokynů vyberte e-mailovou aplikaci, pomocí které odešlete protokoly správci IT. Aplikace vytvoří předem adresovaný e-mail, ve kterém už budou jako přílohy připojené všechny protokoly.




<!--HONumber=Aug16_HO5-->


