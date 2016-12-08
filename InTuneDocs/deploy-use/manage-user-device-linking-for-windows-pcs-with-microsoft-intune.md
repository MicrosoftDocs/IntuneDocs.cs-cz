---
title: "Správa propojení uživatelů se zařízeními u počítačů s Windows | Microsoft Intune"
description: "Jak propojit uživatele s počítačem s Windows spravovaným pomocí Intune"
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 39fec6a2ea8d8c0f4b6ea1460c76a8a6c652d614


---

# <a name="manage-user-device-linking-for-windows-pcs"></a>Správa propojení uživatelů se zařízeními u počítačů s Windows
Abyste mohli nasadit software pro uživatele, musíte uživatele propojit s počítačem. Uživatele můžete propojit s několika počítači, ale každý počítač může být propojený jenom s jedním uživatelem. Uživatelé jsou automaticky propojení se všemi počítači, které si přes portál společnosti zaregistrovali v Intune.

Propojení uživatele s počítačem:

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna zařízení** (nebo na jinou skupinu obsahující počítač, který chcete propojit s uživatelem).

2.  Vyberte počítač, který chcete propojit s uživatelem, a potom zvolte **Propojit uživatele**.

    V dialogovém okně **Propojit uživatele** se zobrazí seznam dostupných uživatelů včetně jejich zobrazovaného jména, ID a počtu počítačů, se kterými jsou aktuálně propojení. Pokud je s vybraným počítačem už nějaký uživatel propojený, je v části **Aktuální uživatel**zobrazené jeho jméno a ID. Když počítač není propojený s žádným uživatelem, tak se v části **Aktuální uživatel** zobrazuje **Žádný uživatel**.

3.  Udělejte jednu z těchto věcí:

    -   Pokud chcete nechat počítač propojený s aktuálním uživatelem, klikněte na **Zrušit**.

    -   Pokud chcete propojení s aktuálním uživatelem odebrat, zvolte **Odebrat odkaz **&gt; **OK**.

    -   Pokud chcete propojit počítač s novým uživatelem, vyberte uživatele v seznamu **Všichni uživatelé** . Potvrďte správnost údajů o uživateli a potom zvolte **OK**.

> [!TIP]
> Když chcete koncovým uživatelům omezit schopnosti propojení vlastních účtů s počítači, povolte možnost **Omezit schopnosti uživatelů propojit s počítači vlastní účet** v zásadách **Nastavení agenta Microsoft Intune**.

### <a name="see-also"></a>Související témata

[Běžné úlohy správy počítačů s Windows pomocí klientského softwaru Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)


<!--HONumber=Nov16_HO4-->


