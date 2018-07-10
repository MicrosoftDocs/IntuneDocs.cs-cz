---
title: Nastavení integrace služby Pradeo s Intune
titleSuffix: Intune on Azure
description: Integrace konektoru Pradeo do Intune
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 06/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 82872ba6-80f8-4cc9-adf4-0ccd8ff26dd2
ms.openlocfilehash: 223161bd12f40b3539ce2502599eb3324c7458ca
ms.sourcegitcommit: f70d6aaea59b52cd0d7bd3008afd243868967fd6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2018
ms.locfileid: "37067450"
---
# <a name="integrate-pradeo-with-intune"></a>Integrace služby Pradeo s Intune

Při integraci řešení Pradeo Mobile Threat Defense do Intune je potřeba provést následující kroky.

## <a name="before-you-begin"></a>Před zahájením

> [!NOTE]
> Následující kroky je potřeba provést v [konzole Pradeo Security](https://www.apps-security.com).

Před zahájením procesu integrace řešení Pradeo a Intune zkontrolujte, že máte následující:

-   Odběr služby Microsoft Intune

-   Přihlašovací údaje správce Azure Active Directory pro udělení následujících oprávnění:

    -   Přihlášení a čtení profilu uživatele

    -   Přístup k adresáři jako přihlášený uživatel

    -   Čtení dat z adresáře

    -   Odeslání informací o zařízení do Intune

-   Přihlašovací údaje správce pro přístup ke konzole Pradeo Security

### <a name="pradeo-app-authorization"></a>Autorizace aplikace Pradeo Security

Postup autorizace aplikace Pradeo:

-   Povolte službě Pradeo předávání informací, které se týkají stavu zařízení, zpět do Intune.

-   Pradeo se synchronizuje s členstvím skupiny registrace Azure AD, aby se mohla naplnit databáze zařízení.

-   Povolte u konzoly pro správu Pradeo použití jednotného přihlašování (SSO) k Azure AD.

-   Povolte aplikaci Pradeo přihlášení pomocí jednotného přihlašování k Azure AD.

## <a name="to-set-up-pradeo-integration"></a>Nastavení integrace služby Pradeo

1.  Přejděte do [konzoly Pradeo Security](https://www.apps-security.com) a přihlaste se pomocí přihlašovacích údajů.

2.  Z nabídky vyberte **Administration – Enterprise Mobility Management**.

3.  Vyberte **logo Intune**.

4.  V okně **EMM (Enterprise mobility management) – Intune** vyberte v části **Step 1** (Krok 1) tlačítko **Pradeo Connector** (konektor Pradeo). 

    ![Okno Pradeo EMM Intune](./media/pradeo_setup.png)

5. Do okna pro připojení Microsoft Intune zadejte přihlašovací údaje Intune.

5.  Otevře se webová stránka Pradeo. V části **Step 2** (Krok 2) vyberte tlačítko **Pradeo Device Health** (Stav zařízení Pradeo).

7. V okně Pradeo-Intune Connector vyberte **Accept** (Přijmout). 

8. V okně Pradeo device API connector (konektor rozhraní API zařízení Pradeo) vyberte **Accept** (Přijmout).

9. Otevře se webová stránka Pradeo. V části **Step 3** (Krok 3) vyberte tlačítko **Connect to Microsoft** (připojit k Microsoftu). 

10. Do okna pro ověřování Microsoft Intune zadejte přihlašovací údaje Intune.

11. Jakmile se objeví zpráva **Successful Integration** (integrace proběhla úspěšně), je integrace hotová.

## <a name="next-steps"></a>Další kroky

-   [Nastavení aplikací Pradeo](mtd-apps-ios-app-configuration-policy-add-assign.md)