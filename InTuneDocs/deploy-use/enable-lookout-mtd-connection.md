---
title: "Povolení ochrany Lookout MTP v Intune | Dokumentace Microsoftu"
description: "Povolení ochrany proti mobilním hrozbám Lookout v konzole pro správu Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d42fa20a3bc6b6f4a74dd0872aae25cfb33067b9
ms.openlocfilehash: d2a10a0e14d9b0b4d2e3f8e2715b47d984e5aa66
ms.lasthandoff: 03/21/2017


---

# <a name="enable-lookout-mtd-connection-in-the-intune-classic-console"></a>Povolení připojení ochrany před mobilními hrozbami Lookout v klasické konzole Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pokud chcete ve službě Intune povolit připojení ochrany před mobilními hrozbami Lookout, měli byste už v konzole Lookout mít nakonfigurovaný konektor Intune.  Pokud jste to ještě neudělali, měli byste si [nastavit předplatné pro ochranu před mobilními hrozbami Lookout](set-up-your-subscription-with-lookout-mtp.md).

Pokud chcete povolit připojení Lookout MTP v Intune, na stránce **Správa** v [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte možnost **Integrace služeb třetích stran**. Vyberte možnost **Stav Lookoutu** a pomocí přepínacího tlačítka povolte **Synchronizace s MTP**.

![snímek obrazovky synchronizace Lookout se zvýrazněným přepínacím tlačítkem Povolit](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Před vytvořením pravidel zásad dodržování předpisů a konfigurací podmíněného přístupu **musíte** nakonfigurovat aplikaci Lookout for Work. Tím zajistíte, že aplikace bude připravena a koncoví uživatelé ji budou moci nainstalovat, aby tím získali přístup k e-mailu a dalším firemním prostředkům.

Tím dokončíte nastavení integrace služeb Lookout a Intune v konzole pro správu Intune.  Mezi několik dalších kroků při implementaci tohoto řešení patří nasazení [aplikací Lookout for Work](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-apps) a nastavení [zásad dodržování předpisů](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-policy).


## <a name="next-steps"></a>Další kroky
[Konfigurace aplikace Lookout for Work](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-apps)

