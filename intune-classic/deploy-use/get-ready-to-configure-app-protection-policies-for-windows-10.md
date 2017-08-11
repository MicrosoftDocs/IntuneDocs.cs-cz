---
title: "Příprava na konfiguraci zásad ochrany aplikací pro Windows 10"
description: "Nastavení poskytovatele správy mobilních aplikací (MAM) v Azure AD"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebc7cfc8-40b9-47c2-8357-d392ebbb27c8
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d4c410913adb32a5957552e453b49de9c7cda097
ms.sourcegitcommit: 2ee1e8248814d74cef80b609a8e43f59fa0b2618
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2017
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Příprava na konfiguraci zásad ochrany aplikací pro Windows 10

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Než vytvoříte zásady ochrany aplikací pro Windows 10, musíte povolit správu mobilních aplikací (MAM) pro Windows 10 nastavením poskytovatele MAM v Azure AD. Tato konfigurace vám umožní definovat stav registrace při vytváření nových zásad WIP (Windows Information Protection) s Intune.

> [!NOTE]
> Stav registrace může být MAM nebo MDM (správa mobilních zařízení).

## <a name="to-configure-the-mam-provider"></a>Konfigurace poskytovatele MAM

1.  Přejděte na portál [Azure Portal](https://portal.azure.com/) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

2.  V nabídce vlevo zvolte **Azure Active Directory**.

    ![Konfigurace poskytovatele MAM](../media/AppManagement/mam-provider-sc-1.png)

3.  Otevře se okno **Azure AD**. Zvolte **Mobilita (MDM a MAM)** a potom klikněte na **Microsoft Intune**.

    ![Mobilita (MDM a MAM)](../media/AppManagement/mam-provider-sc-2.png)

4.  Otevře se konfigurační okno. Zvolte **Obnovit výchozí adresy URL MAM** a potom nakonfigurujte toto:

    a.  Obor uživatele MAM: Pomocí MAM můžete chránit firemní data u určité skupiny uživatelů používajících zařízení s Windows 10, nebo u všech uživatelů.

    b.  Adresa URL podmínek použití služby MAM: Je to adresa URL podmínek použití koncového bodu služby MAM. Slouží k zobrazení podmínek služby MAM koncovým uživatelům.

    c.  Adresa URL zjišťování MAM: Zařízení na této adrese URL hledají, když potřebují použít zásady ochrany aplikací.

    d.  Adresa URL s předpisy služby MAM:

5.  Až tato nastavení nakonfigurujete, zvolte **Uložit**.

## <a name="next-steps"></a>Další kroky

[Vytvoření zásad ochrany aplikací WIP](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune)
