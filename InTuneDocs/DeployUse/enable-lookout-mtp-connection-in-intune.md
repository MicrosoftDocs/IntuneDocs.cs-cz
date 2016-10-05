---
title: "Povolení ochrany Lookout MTP v Intune | Microsoft Intune"
description: "Povolení ochrany proti mobilním hrozbám Lookout v konzole pro správu Intune."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ceaeba74f8671caf4125252fce02fd06752c3fe8
ms.openlocfilehash: 2052aca24baa752bc4fad3bd7a75f8efa109e9e9


---

# Povolení připojení Lookout MTP v konzole pro správu Intune
V tomto tématu se dozvíte, jak povolit připojení Lookout MTP v Intune. Než přistoupíte k tomuto kroku, měli byste už mít v konzole Lookout nakonfigurovaný konektor Intune.  Pokud jste tak ještě neučinili, postupujte podle pokynů popsaných v tématu [Nastavení předplatného pro Lookout MTP](set-up-your-subscription-with-lookout-mtp.md).

Pokud chcete povolit připojení Lookout MTP v Intune, na stránce **Správa** v [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte možnost **Integrace služeb třetích stran**. Vyberte možnost **Stav Lookoutu** a pomocí přepínacího tlačítka povolte **Synchronizace s MTP**.

![snímek obrazovky synchronizace Lookout se zvýrazněným přepínacím tlačítkem Povolit](../media/mtp/lookout-intune-synchronization.png)

Tím dokončíte nastavení integrace služeb Lookout a Intune v konzole pro správu Intune.  Mezi několik dalších kroků při implementaci tohoto řešení patří nasazení [aplikací Lookout for Work](configure-and-deploy-lookout-for-work-apps.md) a nastavení [zásad dodržování předpisů](enable-device-threat-protection-rule-in-compliance-policy.md).

>[!IMPORTANT]
> Před vytvořením pravidel zásad dodržování předpisů a konfigurací podmíněného přístupu **musíte** nakonfigurovat aplikaci Lookout for Work. Tím zajistíte, že aplikace bude připravena a koncoví uživatelé ji budou moci nainstalovat, aby tím získali přístup k e-mailu a dalším firemním prostředkům.
## Další kroky
[Konfigurace aplikace Lookout for Work ](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Sep16_HO4-->


