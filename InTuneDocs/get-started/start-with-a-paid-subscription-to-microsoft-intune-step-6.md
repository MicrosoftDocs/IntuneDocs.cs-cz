---
title: "Nasazení zásad a aplikací | Dokumentace Microsoftu"
description: "Můžete povolit nastavení zásad a nasadit aplikace, které se použijí hned po registraci zařízení pro správu."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 402475d87dc1c57d34669cc9553939521adcd146
ms.lasthandoff: 04/14/2017


---

# <a name="create-policies-and-publish-apps"></a>Vytvoření zásad a publikování aplikací

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

V tomto tématu najdou správci Intune informace o tom, jak vytvořit zásady a publikovat aplikace, které pak můžou nasadit do spravovaných zařízení.

Než začnete s registrací aplikací na Intune, můžete povolit nastavení zásad a aplikace, které se nasadí ihned, jak začne správa těchto zařízení. Intune nabízí nastavení, které pomáhá řídit nastavení zabezpečení na mobilních zařízeních, spravovat nastavení brány Windows Firewall a Endpoint Protection pro počítače a nasazovat aplikace. Můžete nakonfigurovat zásady, přidat aplikace a nasadit tyto aplikace tak, aby zařízení přijímala nastavení a aplikace ihned po registraci v Intune.

Zásady a aplikace jsou specifické pro platformu.

## <a name="manage-device-settings"></a>Správa nastavení zařízení

 Nastavení zásad zařízení se konfiguruje a spravuje podle platformy. Pod následujícími odkazy najdete seznamy dostupných nastavení pro příslušné platformy:

- [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android a Samsung KNOX Standard](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10 (počítače a mobilní zařízení)](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](https://docs.microsoft.com/intune/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](https://docs.microsoft.com/intune/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Tým systému Windows](https://docs.microsoft.com/intune/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [Počítače s Windows s klientem Intune](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

O [Správě nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) si můžete přečíst více.

## <a name="add-and-deploy-apps"></a>Přidání a nasazení aplikací

Do Intune můžete přidat aplikace a pak je nasadit na spravovaná zařízení dvěma způsoby:
- **Požadovaná instalace** – Aplikace automaticky nainstalují aplikaci na spravovaná zařízení.
- **Dostupná instalace** – Aplikace se zobrazí na Portálu společnosti Intune, aby uživatelé mohli zvolit, jestli si je na svá zařízení nainstalují.

### <a name="add-apps"></a>Přidání aplikací

Nejdříve je potřeba aplikace zpřístupnit na Intune jednou z následujících metod:
- [Přidání aplikací pro zaregistrovaná zařízení](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Přidání aplikací pro klientské počítače se softwarem Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>Nasazení aplikací

Teď je aplikace dostupná v Intune a vy ji můžete nasadit na spravovaná zařízení:
- [Nasazení aplikací na zařízení](https://docs.microsoft.com/intune/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- Nasazení hromadně zakoupených aplikací:
    - [iOS – program hromadného nákupu](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [Windows Store pro firmy](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](https://docs.microsoft.com/Intune/deploy-use/android-for-work-apps)

    Po nakonfigurování aplikací k nasazení můžete [nakonfigurovat aplikace](https://docs.microsoft.com/intune/deploy-use/update-apps-using-microsoft-intune) a [monitorovat aplikace](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Organizace uživatelů a zařízení**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Přizpůsobení portálu společnosti** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  

