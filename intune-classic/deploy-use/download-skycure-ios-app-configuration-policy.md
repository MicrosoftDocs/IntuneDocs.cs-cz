---
title: Stažení zásad konfigurace aplikace Skycure pro iOS
description: Stáhněte si zásady konfigurace aplikace Skycure pro iOS, které můžete použít s aplikací Skycure pro iOS nasazenou pro koncové uživatele.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d211b876-4d3a-473c-999f-843c0a16cd22
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f3cf3b2b18eeadf6779b7a8e96d75e569e6e3be
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Stažení zásad konfigurace aplikace Skycure pro iOS

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Před zahájením

K provedení dalších kroků je potřeba, abyste se přihlásili do konzoly pro správu Skycure.

> [!TIP] 
> Pokud používáte Microsoft Internet Explorer 11 nebo Edge, budete možná muset otevřít konzolu pro správu Skycure v anonymním okně prohlížeče.

## <a name="to-download-the-ios-app-configuration-policy"></a>Postup stažení zásad konfigurace aplikace pro iOS

1.  Přejděte do [konzoly pro správu Skycure](https://aad.skycure.com).

2.  Zadejte své **přihlašovací údaje správce Skycure** a potom klikněte na **Continue** (Pokračovat).

    ![Přihlášení do konzoly pro správu Skycure](../media/mtp/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > Uživatelské jméno správce Skycure je e-mailový účet, který musí být platným uživatelským účtem služby Azure Active Directory, jinak se přihlášení nezdaří. Služba Skycure k ověření uživatelského jména správce používá službu Azure Active Directory a jednotné přihlašování (SSO).

3.  Přejděte do **Settings** (Nastavení ) &gt; **Device Management Integrations** (Integrace správy zařízení) &gt; **EMM Integration Selection** (Volba integrace EMM), vyberte **Microsoft Intune** a potom svou volbu uložte.

2.  Klikněte na odkaz **Integration setup files** (Integrační soubory nastavení) a vygenerovaný soubor \*.zip uložte. Soubor .zip obsahuje soubor **skycure\_configuration.plist**, který se použijte k vytvoření zásad konfigurace aplikace pro iOS na klasickém portálu Intune.

![Integrační soubory nastavení služby Skycure](../media/mtp/skycure-ios-app-2.png)

## <a name="next-steps"></a>Další kroky

[Přidání aplikací Skycure, aplikace Microsoft Authenticator a zásad konfigurace aplikace pro iOS](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)
