---
title: Integrace služby Zimperium MTD s Microsoft Intune
titleSuffix: ''
description: Přečtěte si, jak integrovat řešení Zimperium Mobile Threat Defense s Microsoft Intune, abyste mohli regulovat přístup mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 68896a363cab37aabe9a597872da0fe75c44c473
ms.sourcegitcommit: 3903f20cb5686532ccd8c36aa43c5150cee7cca2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2018
ms.locfileid: "52267233"
---
# <a name="integrate-zimperium-with-intune"></a>Integrace řešení Zimperium do Intune

Při integraci řešení Zimperium Mobile Threat Defense do Intune je potřeba provést následující kroky.

## <a name="before-you-begin"></a>Před zahájením

> [!NOTE]
> Následující kroky je potřeba provést v [konzole Zimperium MTD](https://sso.zimperium.com/signon/aad/).

Před zahájením procesu integrace řešení Zimperium do Intune zkontrolujte, že máte následující předplatné a přihlašovací údaje:

-   Odběr služby Microsoft Intune

-   Přihlašovací údaje správce Azure Active Directory pro udělení následujících oprávnění:

    -   Přihlášení a čtení profilu uživatele

    -   Přístup k adresáři jako přihlášený uživatel

    -   Čtení dat z adresáře

    -   Odeslání informací o zařízení do Intune

-   Přihlašovací údaje správce pro přístup ke konzole Zimperium MTD

### <a name="zimperium-app-authorization"></a>Autorizace aplikace Zimperium

Postup autorizace aplikace Zimperium:

-   Povolte službě Zimperium předávání informací týkajících se stavu zařízení zpět do Intune.

-   Zimperium se synchronizuje s členstvím skupiny registrace Azure Active Directory (AD), aby se mohla naplnit databáze zařízení.

-   Povolte u konzoly pro správu Zimperium použití jednotného přihlašování (SSO) k Azure AD.

-   Povolte aplikaci Zimperium přihlášení pomocí jednotného přihlašování k Azure AD.

## <a name="to-set-up-zimperium-integration"></a>Nastavení integrace řešení Zimperium

1.  Přejděte na [konzole Zimperium MTD](https://sso.zimperium.com/signon/aad/) a přihlaste se pomocí svých přihlašovacích údajů.

2.  Zvolte z levé nabídky možnost **Management** (Správa).

3.  Zvolte **nastavení MDM** kartu.

4.  Zvolte **Add MDM** (Přidat MDM) a pak vyberte **Microsoft Intune** ze seznamu **MDM provider** (Zprostředkovatel MDM).

5.  Po nastavení Microsoft Intune jako služby MDM **konfigurace v Microsoft Intune** okno otevře, zvolte **přidat Azure Active Directory** jednotlivých možností:  **Zimperium zConsole**, **zIPS pro iOS a Android apps** řešení zimperium komunikovalo s Intune a Azure AD prostřednictvím Azure AD jednotného přihlašování.

    > [!IMPORTANT]
    > Pro dokončení procesu integrace s Intune je nutné přidat aplikace zConsole Zimperium a zIPS pro iOS a Android.

6.  Zvolte **přijmout** autorizovat aplikaci Zimperium komunikovalo s Intune a Azure Active Directory.

7.  Po přidání aplikací **Zimperium zConsole** a **zIPS pro iOS a Android** do Azure AD přidejte skupiny zabezpečení Azure AD. Tím umožníte, aby aplikace Zimperium mohla příslušnou skupinu zabezpečení Azure AD synchronizovat se svou službou.

8.  Zvolte **Dokončit** uložte konfiguraci a spusťte první synchronizaci skupiny zabezpečení Azure AD.

## <a name="next-steps"></a>Další postup

-   [Nastavení aplikací Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
