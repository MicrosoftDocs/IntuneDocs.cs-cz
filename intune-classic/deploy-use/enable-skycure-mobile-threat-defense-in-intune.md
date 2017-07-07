---
title: "Povolení ochrany před mobilními hrozbami Skycure ve službě Intune"
description: "Povolení ochrany před mobilními hrozbami Skycure v klasické konzole Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4dad45d15fec7189fdcf184839040b9e3f9a3a48
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>Povolení ochrany před mobilními hrozbami Skycure ve službě Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pokud chcete povolit ochranu před mobilními hrozbami Skycure, měli byste už mít konektor Intune v konzole Skycure nakonfigurovaný (/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune).

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>Postup povolení připojení ochrany před mobilními hrozbami Skycure ve službě Intune

1.  Přejděte na stránku [klasické konzoly Intune](https://manage.microsoft.com/) a zadejte své přihlašovací údaje.

2.  Zvolte **Admin** (Správce) &gt; **Third Party Service Integration** (Integrace služeb třetích stran), potom zvolte **Skycure Status** (Stav služby Skycure) a pomocí přepínacího tlačítka povolte možnost **Synchronization with MTD** (Synchronizace s ochranou před mobilními hrozbami).

    ![Povolení přepínacího tlačítka služby Skycure v klasické konzole Intune](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> Před vytvořením pravidel zásad dodržování předpisů a konfigurací podmíněného přístupu musíte nakonfigurovat aplikace Skycure. Tím zajistíte, že aplikace bude připravena a koncoví uživatelé ji budou moci nainstalovat, aby tím získali přístup k e-mailu a dalším firemním prostředkům.

Tím v konzole pro správu Intune dokončíte nastavení integrace služeb Skycure a Intune. Mezi několik dalších kroků při implementaci tohoto řešení patří nasazení aplikací Skycure for Work a nastavení zásad dodržování předpisů.

## <a name="next-steps"></a>Další kroky

[Vytvoření zásad dodržování předpisů pro ochranu před mobilními hrozbami Skycure](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
