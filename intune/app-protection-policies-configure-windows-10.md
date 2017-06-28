---
title: "Příprava na konfiguraci zásad ochrany aplikací pro Windows 10"
titleSuffix: Intune on Azure
description: "Nastavení poskytovatele správy mobilních aplikací (MAM) v Azure AD"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 6f2f0b610b900bb41a3c2bd7416b6db28434a155
ms.openlocfilehash: bf56d3a80f0d167baa95e9dfdb20d08e02590984
ms.contentlocale: cs-cz
ms.lasthandoff: 06/13/2017


---

# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Příprava na konfiguraci zásad ochrany aplikací pro Windows 10

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Než vytvoříte zásady ochrany aplikací pro Windows 10, musíte povolit správu mobilních aplikací (MAM) pro Windows 10 nastavením poskytovatele MAM v Azure AD. Tato konfigurace vám umožní definovat stav registrace při vytváření nových zásad WIP (Windows Information Protection) s Intune.

> [!NOTE]
> Stav registrace může být MAM nebo MDM (správa mobilních zařízení).

## <a name="to-configure-the-mam-provider"></a>Konfigurace poskytovatele MAM

1.  Přejděte na portál [Azure Portal](https://portal.azure.com/) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

2.  V nabídce vlevo zvolte **Azure Active Directory**.

    ![Konfigurace poskytovatele MAM](./media/mam-provider-sc-1.png)

3.  Otevře se okno **Azure AD**. Zvolte **Mobilita (MDM a MAM)** a potom klikněte na **Microsoft Intune**.

    ![Mobilita (MDM a MAM)](./media/mam-provider-sc-1.png)

4.  Otevře se konfigurační okno. Zvolte **Obnovit výchozí adresy URL MAM** a potom nakonfigurujte toto:

    a.  Obor uživatele MAM: Pomocí MAM můžete chránit firemní data u určité skupiny uživatelů používajících zařízení s Windows 10, nebo u všech uživatelů.

    b.  Adresa URL podmínek použití služby MAM: Je to adresa URL podmínek použití koncového bodu služby MAM. Slouží k zobrazení podmínek služby MAM koncovým uživatelům.

    c.  Adresa URL zjišťování MAM: Zařízení na této adrese URL hledají, když potřebují použít zásady ochrany aplikací.

    d.  Adresa URL s předpisy služby MAM:

5.  Až tato nastavení nakonfigurujete, zvolte **Uložit**.

## <a name="next-steps"></a>Další kroky

[Vytvoření zásad ochrany aplikací WIP](windows-information-protection-policy-create.md)

