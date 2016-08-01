---
title: "Řešení potíží s e-mailovými profily | Microsoft Intune"
description: "Problémy s e-mailovými profily a způsoby, jak je vyřešit"
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c1e215320168c659d5f838355f6350111d6979b0
ms.openlocfilehash: c695f39f128cf5ebee14b885b89ebe9833009ae9


---

# Řešení potíží s e-mailovými profily v Microsoft Intune
Tady najdete některé problémy s e-mailovými profily a způsoby, jak je vyřešit.

Pokud tyto informace váš problém nevyřeší, přečtěte si téma [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md), ve kterém najdete další způsoby, jak získat nápovědu.


## Z e-mailového účtu nelze odesílat obrázky
Uživatelé s automaticky nakonfigurovanými e-mailovými účty nemohou ze svých zařízení odesílat obrázky.
K tomu dojde, když není povolená možnost **Povolit odesílání e-mailů z aplikací třetí strany**.

### Řešení Intune

1.  Otevřete konzolu pro správu Microsoft Intune, vyberte úlohu **Zásady** &gt; **Zásady konfigurace**.

2.  Vyberte e-mailový profil a zvolte **Upravit**.

3.  Vyberte **Povolit odesílání e-mailů z aplikací třetí strany.**

### Configuration Manager integrovaný s řešením Intune

1.  Otevřete konzolu Configuration Manageru &gt;**Prostředky a kompatibilita**.

2.  Rozbalte **Přehled** -&gt; **Nastavení dodržování předpisů** -&gt; **Přístup k prostředkům společnosti** a vyberte **E-mailové profily**.

3.  Klikněte pravým tlačítkem na e-mailový profil a otevřete **Vlastnosti**.

4.  Na kartě **Nastavení synchronizace** vyberte **Povolit odesílání e-mailů z aplikací třetí strany**.

## Další kroky
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Jul16_HO3-->


