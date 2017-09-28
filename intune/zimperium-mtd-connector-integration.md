---
title: "Integrace řešení Zimperium do Intune"
titleSuffix: Intune on Azure
description: "Integrace Intune s řešením Zimperium"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b4adb2db14c2e1c83be8e7b3644944c1910cb97
ms.sourcegitcommit: d434dfab7ef7a6c4082d675717fa22d5581b4f51
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/19/2017
---
# <a name="integrate-zimperium-with-intune"></a>Integrace řešení Zimperium do Intune

Pro integraci řešení Zimperium Mobile Threat Defense s Intune je třeba provést následující kroky.

## <a name="before-you-begin"></a>Před zahájením

> [!NOTE]
> Následující postup je třeba provést na [konzole Zimperium MTD](https://staging2-console.zimperium.com).

Před zahájením procesu integrace řešení Zimperium a Intune zkontrolujte, že máte následující:

-   Předplatné služby Microsoft Intune

-   Přihlašovací údaje správce Azure Active Directory pro udělení následujících oprávnění:

    -   Přihlášení a čtení profilu uživatele

    -   Přístup k adresáři jako přihlášený uživatel

    -   Čtení dat z adresáře

    -   Odeslání informací o zařízení do Intune

-   Přihlašovací údaje správce pro přístup ke konzole Zimperium MTD

### <a name="zimperium-app-authorization"></a>Autorizace aplikace Zimperium

Proces autorizace aplikace Zimperium:

-   Povolte službě Zimperium předávání informací týkajících se stavu zařízení zpět do Intune.

-   Zimperium se synchronizuje s členstvím skupiny registrace Azure AD, aby se mohla naplnit databáze zařízení.

-   Povolte u konzoly pro správu Zimperium použití jednotného přihlašování (SSO) k Azure AD.

-   Povolte aplikaci Zimperium přihlášení pomocí jednotného přihlašování k Azure AD.

## <a name="to-set-up-zimperium-integration"></a>Nastavení integrace řešení Zimperium

1.  Přejděte do [konzoly Zimperium MTD](https://staging2-console.zimperium.com) a přihlaste se pomocí přihlašovacích údajů.

2.  Zvolte z levé nabídky možnost **Management** (Správa).

3.  Vyberte kartu **MDM settings** (Nastavení MDM).

4.  Zvolte **Add MDM** (Přidat MDM) a pak vyberte **Microsoft Intune** ze seznamu **MDM provider** (Zprostředkovatel MDM).

5.  Po nastavení Microsoft Intune jako služby MDM se zobrazí okno pro **konfiguraci Microsoft Intune**. Zvolte **Add Azure Active Directory** (Přidat Azure Active Directory) pro každou z možností: **Zimperium zConsole** a **zIPS iOS and Android apps** (Aplikace zIPS pro iOS a Android). Tím povolíte komunikaci řešení Zimperium s Intune a Azure AD prostřednictvím jednotného přihlašování Azure AD.

    > [!IMPORTANT]
    > Pro dokončení procesu integrace s Intune je nutné přidat aplikace zConsole Zimperium a zIPS pro iOS a Android.

6.  Volbou **Accept** (Přijmout) povolte komunikaci aplikace Zimperium s Intune a Azure Active Directory.

7.  Až přidáte aplikace **Zimperium zConsole** a **zIPS pro iOS a Android** do Azure AD, musíte přidat skupiny zabezpečení Azure AD, aby Zimperium mohlo příslušnou skupinu zabezpečení Azure AD synchronizovat se svými službami.

8.  Volbou **Finish** (Dokončit) uložte konfiguraci a spusťte první synchronizaci skupiny zabezpečení Azure AD.

## <a name="next-steps"></a>Další kroky

-   [Nastavení aplikací Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
