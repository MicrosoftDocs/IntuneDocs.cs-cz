---
title: Správa propojení uživatelů se zařízeními u počítačů s Windows
titlesuffix: Microsoft Intune
description: Jak propojit uživatele s počítačem s Windows spravovaným pomocí Intune
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic-keep
ms.openlocfilehash: 0354bf10601ed9a31cdc3beba1bf6825896a2016
ms.sourcegitcommit: 116be0eaa44fd5518ff34780d39569224ef4746b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/21/2018
ms.locfileid: "36310942"
---
# <a name="manage-user-device-linking-for-windows-pcs"></a>Správa propojení uživatelů se zařízeními u počítačů s Windows

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Informace v tomto tématu se vztahují jenom na desktopové systémy Windows, které spravujete jako počítače (PC) pomocí softwarového klienta Intune. 

Abyste mohli nasadit software pro uživatele, musíte uživatele propojit s počítačem. Uživatele můžete propojit s několika počítači, ale každý počítač může být propojený jenom s jedním uživatelem. Uživatelé se automaticky propojí se všemi počítači, které si přes portál společnosti zaregistrovali v Intune.

Propojení uživatele s počítačem:

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna zařízení** (nebo jinou skupinu obsahující počítač, který chcete propojit s uživatelem).

2. Vyberte počítač, který chcete propojit s uživatelem, a potom zvolte **Propojit uživatele**.

   V dialogovém okně **Propojit uživatele** se zobrazí seznam dostupných uživatelů včetně jejich zobrazovaného jména, ID a počtu počítačů, se kterými jsou aktuálně propojení. Pokud je s vybraným počítačem už nějaký uživatel propojený, je v části **Aktuální uživatel** zobrazené jeho jméno a ID. Když počítač není propojený s žádným uživatelem, tak se v části **Aktuální uživatel** zobrazuje **Žádný uživatel**.

3. Udělejte jednu z těchto věcí:

   - Pokud chcete nechat počítač propojený s případným aktuálním uživatelem, klikněte na **Zrušit**.

   - Pokud chcete aktuálnímu uživateli odebrat odkaz (za předpokladu, že existuje), zvolte <strong>Odebrat odkaz**&gt; **OK</strong>.

   - Pokud chcete propojit počítač s novým uživatelem, vyberte uživatele v seznamu **Všichni uživatelé**. Potvrďte správnost údajů o uživateli a potom zvolte **OK**.

> [!TIP]
> Když chcete koncovým uživatelům omezit schopnost propojit se s počítači, povolte možnost **Omezit schopnosti uživatelů propojit s počítači vlastní účet** v zásadě **Nastavení agenta Microsoft Intune**.

### <a name="see-also"></a>Viz taky

[Běžné úlohy správy počítačů s Windows pomocí klientského softwaru Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)