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
ms.sourcegitcommit: 6f687a1db84b49bc173d2067ab95598b4485daa8
ms.openlocfilehash: 618819ff8dded925bc4745160dde8c9e75694faf


---

# <a name="enable-lookout-mtp-connection-in-the-intune-admin-console"></a>Povolení připojení Lookout MTP v konzole pro správu Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pokud chcete v Intune povolit připojení Lookout MTP (Malicious Threat Protection), měli byste už v konzole Lookout mít nakonfigurovaný konektor Intune.  Pokud ho ještě nemáte, měli byste [nastavit předplatné pro Lookout Mobile Threat Protection](set-up-your-subscription-with-lookout-mtp.md).

Pokud chcete povolit připojení Lookout MTP v Intune, na stránce **Správa** v [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte možnost **Integrace služeb třetích stran**. Vyberte možnost **Stav Lookoutu** a pomocí přepínacího tlačítka povolte **Synchronizace s MTP**.

![snímek obrazovky synchronizace Lookout se zvýrazněným přepínacím tlačítkem Povolit](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Před vytvořením pravidel zásad dodržování předpisů a konfigurací podmíněného přístupu **musíte** nakonfigurovat aplikaci Lookout for Work. Tím zajistíte, že aplikace bude připravena a koncoví uživatelé ji budou moci nainstalovat, aby tím získali přístup k e-mailu a dalším firemním prostředkům.

Tím dokončíte nastavení integrace služeb Lookout a Intune v konzole pro správu Intune.  Mezi několik dalších kroků při implementaci tohoto řešení patří nasazení [aplikací Lookout for Work](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-apps) a nastavení [zásad dodržování předpisů](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-policy).


## <a name="next-steps"></a>Další kroky
[Konfigurace aplikace Lookout for Work](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-apps)



<!--HONumber=Feb17_HO4-->


