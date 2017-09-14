---
title: "Stažení zásad konfigurace aplikace Skycure pro iOS pro použití s Intune"
titlesuffix: Azure portal
description: "Stáhněte si zásady konfigurace aplikace Skycure pro iOS pro použití s Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1bdc2ecf-32d0-4b6a-80b4-dbcdb9909010
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 296d5545530e8001c0648bafac3101b94f45529d
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Stažení zásad konfigurace aplikace Skycure pro iOS

## <a name="before-you-begin"></a>Před zahájením

K provedení dalších kroků je potřeba, abyste se přihlásili do konzoly pro správu Skycure.

> [!TIP] 
> Pokud používáte Microsoft Internet Explorer 11 nebo Edge, budete možná muset otevřít konzolu pro správu Skycure v anonymním okně prohlížeče.

## <a name="to-download-the-ios-app-configuration-policy"></a>Postup stažení zásad konfigurace aplikace pro iOS

1.  Přejděte do [konzoly pro správu Skycure](https://aad.skycure.com).

2.  Zadejte své **přihlašovací údaje správce Skycure** a potom klikněte na **Continue** (Pokračovat).

    ![Přihlášení do konzoly pro správu Skycure](./media/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > Uživatelské jméno správce Skycure je e-mailový účet, který musí být platným uživatelským účtem služby Azure Active Directory, jinak se přihlášení nezdaří. Služba Skycure k ověření uživatelského jména správce používá službu Azure Active Directory a jednotné přihlašování (SSO).

3.  Přejděte do **Settings** (Nastavení ) &gt; **Device Management Integrations** (Integrace správy zařízení) &gt; **EMM Integration Selection** (Volba integrace EMM), vyberte **Microsoft Intune** a potom svou volbu uložte.

4.  Klikněte na odkaz **Integration setup files** (Integrační soubory nastavení) a vygenerovaný soubor \*.zip uložte. Soubor .zip obsahuje soubor **skycure\_configuration.plist**, který se použijte k vytvoření zásad konfigurace aplikace pro iOS na klasickém portálu Intune.

![Integrační soubory nastavení služby Skycure](./media/skycure-ios-app-2.png)

## <a name="next-steps"></a>Další kroky

[Přidání aplikací Skycure, aplikace Microsoft Authenticator a zásad konfigurace aplikace pro iOS](mtd-apps-ios-app-configuration-policy-add-assign.md)
