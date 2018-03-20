---
title: "Nastavení Windows Information Protection v Microsoft Intune"
titleSuffix: 
description: "Přečtěte si o nastaveních Microsoft Intune, pomocí kterých můžete spravovat Windows Information Protection."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 1/18/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f2e5090eada373b83c3f8c390b7df6b31f6d1723
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>Konfigurace nastavení Windows Information Protection v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

S nárůstem počtu zařízení vlastněných zaměstnanci, která se v podnicích využívají, vzrůstá také riziko náhodných úniků dat prostřednictvím aplikací a služeb, jako jsou e-mail, sociální média a veřejný cloud, které jsou mimo kontrolu příslušného podniku. Jsou to situace, kdy uživatel například odešle nejnovější technické výkresy ze svého osobního e-mailového účtu, zkopíruje informace o produktu a vloží je do tweetu nebo uloží aktuální zprávu o prodeji do veřejného cloudového úložiště.

Služba **Windows Information Protection** pomáhá před těmito potenciálními úniky dat chránit, aniž by jinak zasahovala do činnosti zaměstnanců. Pomáhá také chránit podnikové aplikace a data před náhodnými úniky dat na zařízeních ve vlastnictví společnosti a osobních zařízeních, která si uživatelé přinesou do práce, a nevyžaduje přitom žádné změny prostředí nebo ostatních aplikací.

Tyto zásady Intune spravují seznam aplikací chráněných službou Windows Information Protection, umístění v podnikové síti, úroveň ochrany a nastavení šifrování.

>[!NOTE]
> Pokud chcete používat aplikaci Portál společnosti pro Windows 10 se službou Windows Information Protection, musíte přidat aplikaci Portál společnosti v režimu služby Windows Information Protection **Výjimka**. 

### <a name="next-steps"></a>Další kroky
Více informací najdete v následujících tématech:
-  [Ochrana podnikových dat pomocí sady Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip)
- [Vytvoření zásad pro Windows Information Protection (WIP) pomocí klasické konzoly pro Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune)
- [Vytvoření zásad pro Windows Information Protection (WIP) s MDM pomocí portálu Azure Portal pro Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
- [Vytvoření zásad pro Windows Information Protection (WIP) s MAM pomocí portálu Azure Portal pro Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-mam-intune-azure)
