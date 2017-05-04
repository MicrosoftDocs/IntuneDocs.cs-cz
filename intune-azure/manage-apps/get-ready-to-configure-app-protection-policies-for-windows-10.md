---
title: "Příprava na konfiguraci zásad ochrany aplikací pro Windows 10 | Dokumentace Microsoftu"
titleSuffix: Intune Azure preview
description: "Nastavení poskytovatele správy mobilních aplikací (MAM) v Azure AD"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 5f172290d493717308446c4f9e2313a03ba8f3aa
ms.openlocfilehash: 7cd202384eeb17f5ff5a2812fe87a2fffabe6eb0
ms.lasthandoff: 04/27/2017


---

# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Příprava na konfiguraci zásad ochrany aplikací pro Windows 10

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Než vytvoříte zásady ochrany aplikací pro Windows 10, musíte povolit správu mobilních aplikací (MAM) pro Windows 10 nastavením poskytovatele MAM v Azure AD. Tato konfigurace vám umožní definovat stav registrace při vytváření nových zásad WIP (Windows Information Protection) s Intune.

> [!NOTE]
> Stav registrace může být MAM nebo MDM (správa mobilních zařízení).

## <a name="to-configure-the-mam-provider"></a>Konfigurace poskytovatele MAM

1.  Přejděte na portál [Azure Portal](https://portal.azure.com/) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

2.  V nabídce vlevo zvolte **Azure Active Directory**.

    ![Konfigurace poskytovatele MAM](../media/AppManagement/mam-provider-sc-1.png)

3.  Otevře se okno **Azure AD**. Zvolte **Mobilita (MDM a MAM)** a potom klikněte na **Microsoft Intune**.

    ![Mobilita (MDM a MAM)](../media/AppManagement/mam-provider-sc-1.png)

4.  Otevře se konfigurační okno. Zvolte **Obnovit výchozí adresy URL MAM** a potom nakonfigurujte toto:

    a.  Obor uživatele MAM: Pomocí MAM můžete chránit firemní data u určité skupiny uživatelů používajících zařízení s Windows 10, nebo u všech uživatelů.

    b.  Adresa URL podmínek použití služby MAM: Je to adresa URL podmínek použití koncového bodu služby MAM. Slouží k zobrazení podmínek služby MAM koncovým uživatelům.

    c.  Adresa URL zjišťování MAM: Zařízení na této adrese URL hledají, když potřebují použít zásady ochrany aplikací.

    d.  Adresa URL s předpisy služby MAM:

5.  Až tato nastavení nakonfigurujete, zvolte **Uložit**.

## <a name="next-steps"></a>Další kroky

[Vytvoření zásad ochrany aplikací WIP](https://docs.microsoft.com/intune-azure/manage-apps/create-windows-information-protection-policy-with-intune)

