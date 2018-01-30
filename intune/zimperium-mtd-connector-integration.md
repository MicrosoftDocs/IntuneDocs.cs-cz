---
title: "Integrace řešení Zimperium do Intune"
titleSuffix: Intune on Azure
description: "Integrace Intune s řešením Zimperium"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4759bab0c302f758f3f0a4af5ca333a5f560f3b3
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="integrate-zimperium-with-intune"></a>Integrace řešení Zimperium do Intune

Při integraci řešení Zimperium Mobile Threat Defense do Intune je potřeba provést následující kroky.

## <a name="before-you-begin"></a>Před zahájením

> [!NOTE]
> Následující kroky je potřeba provést v [konzole Zimperium MTD](https://staging2-console.zimperium.com).

Před zahájením procesu integrace řešení Zimperium a Intune zkontrolujte, že máte následující:

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

-   Zimperium se synchronizuje s členstvím skupiny registrace Azure AD, aby se mohla naplnit databáze zařízení.

-   Povolte u konzoly pro správu Zimperium použití jednotného přihlašování (SSO) k Azure AD.

-   Povolte aplikaci Zimperium přihlášení pomocí jednotného přihlašování k Azure AD.

## <a name="to-set-up-zimperium-integration"></a>Nastavení integrace řešení Zimperium

1.  Přejděte do [konzoly Zimperium MTD](https://staging2-console.zimperium.com) a přihlaste se pomocí přihlašovacích údajů.

2.  Zvolte z levé nabídky možnost **Management** (Správa).

3.  Vyberte kartu **MDM settings** (Nastavení MDM).

4.  Zvolte **Add MDM** (Přidat MDM) a pak vyberte **Microsoft Intune** ze seznamu **MDM provider** (Zprostředkovatel MDM).

5.  Po nastavení Microsoft Intune jako služby MDM se zobrazí okno pro **konfiguraci Microsoft Intune**. Zvolte **Přidat uživatele Azure Active Directory** pro každou z těchto možností: **Zimperium zConsole** a **zIPS pro iOS a Android**. Tím povolíte, aby řešení Zimperium komunikovalo s Intune a Azure AD prostřednictvím jednotného přihlašování Azure AD.

    > [!IMPORTANT]
    > Pro dokončení procesu integrace s Intune je nutné přidat aplikace zConsole Zimperium a zIPS pro iOS a Android.

6.  Volbou **Accept** (Přijmout) povolte komunikaci aplikace Zimperium s Intune a Azure Active Directory.

7.  Po přidání aplikací **Zimperium zConsole** a **zIPS pro iOS a Android** do Azure AD přidejte skupiny zabezpečení Azure AD, aby Zimperium mohlo příslušnou skupinu zabezpečení Azure AD synchronizovat se svou službou.

8.  Volbou **Finish** (Dokončit) uložte konfiguraci a spusťte první synchronizaci skupiny zabezpečení Azure AD.

## <a name="next-steps"></a>Další kroky

-   [Nastavení aplikací Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
