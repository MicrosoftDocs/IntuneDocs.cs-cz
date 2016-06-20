---
# required metadata

title: Integrace Intune s cloudovými službami a produkty Microsoftu | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 49675811-08a3-408f-810b-89552ff404bd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Integrace Intune s cloudovými službami a produkty Microsoftu

Před nastavením [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] si přečtěte toto téma a další požadavky uvedené v tématu [Co potřebujete vědět, než začnete s Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).
##Integrace s jinými cloudovými službami Microsoftu


[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] sdílí společnou platformu s jinými cloudovými službami Microsoftu. Pokud používáte stejný účet pro přihlášení k odběru několika cloudových služeb, budou tyto služby používat stejnou infrastrukturu Microsoft Azure AD a budou klienty Azure AD. Azure AD poskytuje základní adresářové funkce a funkce správy identit pro cloudové služby Microsoftu.

Další informace o [správě Azure AD](http://technet.microsoft.com/library/hh967611.aspx) najdete v knihovně TechNet.

## Integrace s dalšími produkty Microsoftu
[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] můžete používat jako samostatnou cloudovou službu nebo jako cloudovou službu, která je integrovaná s ostatními produkty. V současné době se dá přímo integrovat jen [!INCLUDE[cmshort](../includes/cmshort_md.md)] s [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Rozhodnutí ohledně integrace [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] s [!INCLUDE[cmshort](../includes/cmshort_md.md)] je trvalou volbou, která vyžaduje, abyste nastavili autoritu správy mobilních zařízení z konzoly [!INCLUDE[cmshort](../includes/cmshort_md.md)] a nikoli z [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]. Po nastavení autority správy mobilních zařízení se tahle konfigurace nedá změnit ani zrušit.

Pokud používáte [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] s [!INCLUDE[cmshort](../includes/cmshort_md.md)], nepoužívejte [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] ke správě [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Použijte raději konzolu [!INCLUDE[cmshort](../includes/cmshort_md.md)]. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] dál používá své cloudové úložiště v Azure k hostování softwaru nasazeného na zařízení, která spravujete v [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Další informace najdete v článku [Správa mobilních zařízení přes Configuration Manager a Microsoft Intune](http://msdn.microsoft.com/library/2c6bd0e5-d436-41c8-bf38-30152d76be10) v dokumentaci k [!INCLUDE[cm5short](../includes/cm5short_md.md)] SP1.

### Související témata
[Co potřebujete vědět, než začnete s Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)

<!--HONumber=May16_HO1-->

