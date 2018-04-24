---
title: Povolení Lookout MTP v Intune
description: Povolení ochrany proti mobilním hrozbám Lookout v konzole pro správu Intune.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/19/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4814bc053a27cf9fdf2694b6ae78884544b50c27
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="enable-lookout-mtd-connection-in-the-intune-classic-portal"></a>Povolení připojení ochrany před mobilními hrozbami Lookout na klasickém portálu Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Pokud chcete ve službě Intune povolit připojení ochrany před mobilními hrozbami Lookout, měli byste už v konzole Lookout mít nakonfigurovaný konektor Intune.  Pokud jste to ještě neudělali, měli byste si [nastavit předplatné pro ochranu před mobilními hrozbami Lookout](setup-your-lookout-mtd-subscription.md).

Pokud chcete povolit připojení Lookout MTP v Intune, na stránce **Správa** v [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte možnost **Integrace služeb třetích stran**. Vyberte možnost **Stav Lookoutu** a pomocí přepínacího tlačítka povolte **Synchronizace s MTP**.

![snímek obrazovky synchronizace Lookout se zvýrazněným přepínacím tlačítkem Povolit](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Před vytvořením pravidel zásad dodržování předpisů a konfigurací podmíněného přístupu **musíte** nakonfigurovat aplikaci Lookout for Work. Tím zajistíte, že aplikace bude připravena a koncoví uživatelé ji budou moci nainstalovat, aby tím získali přístup k e-mailu a dalším firemním prostředkům.

Tím dokončíte nastavení integrace služeb Lookout a Intune v konzole pro správu Intune.  Mezi několik dalších kroků při implementaci tohoto řešení patří nasazení zásad [aplikací Lookout for Work](/intune-classic/deploy-use/device-threat-protection-policy).


## <a name="next-steps"></a>Další kroky
[Konfigurace aplikace Lookout for Work](/intune-classic/deploy-use/device-threat-protection-apps)
