---
title: "Povolení ochrany před mobilními hrozbami Skycure ve službě Intune | Dokumentace Microsoftu"
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
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: a110f2ae4d8a101a7fb977aa651e5ce2c8828e7e
ms.lasthandoff: 03/22/2017


---

# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>Povolení ochrany před mobilními hrozbami Skycure ve službě Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pokud chcete ve službě Intune povolit připojení ochrany před mobilními hrozbami Skycure, měli byste už mít [konektor Intune v konzole Skycure](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune) nakonfigurovaný.

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>Postup povolení připojení ochrany před mobilními hrozbami Skycure ve službě Intune

1.  Přejděte na stránku [klasické konzoly Intune](https://manage.microsoft.com/) a zadejte své přihlašovací údaje.

2.  Zvolte **Admin** (Správce) &gt; **Third Party Service Integration** (Integrace služeb třetích stran), potom zvolte **Skycure Status** (Stav služby Skycure) a pomocí přepínacího tlačítka povolte možnost **Synchronization with MTD** (Synchronizace s ochranou před mobilními hrozbami).

    ![Povolení přepínacího tlačítka služby Skycure v klasické konzole Intune](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> Před vytvořením pravidel zásad dodržování předpisů a konfigurací podmíněného přístupu musíte nakonfigurovat aplikace Skycure. Tím zajistíte, že aplikace bude připravena a koncoví uživatelé ji budou moci nainstalovat, aby tím získali přístup k e-mailu a dalším firemním prostředkům.

Tím v konzole pro správu Intune dokončíte nastavení integrace služeb Skycure a Intune. Mezi několik dalších kroků při implementaci tohoto řešení patří nasazení aplikací Skycure for Work a nastavení zásad dodržování předpisů.

## <a name="next-steps"></a>Další kroky

[Vytvoření zásad dodržování předpisů pro ochranu před mobilními hrozbami Skycure](https://docs.microsoft.com/intune/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)

