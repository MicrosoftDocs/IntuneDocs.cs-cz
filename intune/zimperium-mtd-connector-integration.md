---
title: Integrace řešení Zimperium MTD s Microsoft Intune | Microsoft Intune
description: Přečtěte si, jak integrovat řešení Zimperium Mobile Threat Defense s Microsoft Intune, abyste mohli regulovat přístup mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b12cec7a01d809eb5a6b6523a73dd224c10c972e
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53817190"
---
# <a name="integrate-zimperium-with-intune"></a>Integrace řešení Zimperium do Intune

Při integraci řešení Zimperium Mobile Threat Defense do Intune je potřeba provést následující kroky.

## <a name="before-you-begin"></a>Před zahájením

> [!NOTE]
> Následující kroky je potřeba provést v [konzole Zimperium MTD](https://sso.zimperium.com/signon/aad/).

Před zahájením procesu integrace řešení Zimperium do Intune zkontrolujte, že máte následující předplatné a přihlašovací údaje:

-   Odběr služby Microsoft Intune

-   Azure Active Directory globálního správce přihlašovacích údajů správce udělit následující oprávnění:

    -   Přihlášení a čtení profilu uživatele

    -   Přístup k adresáři jako přihlášený uživatel

    -   Čtení dat z adresáře

    -   Odeslání informací o zařízení do Intune

-   Přihlašovací údaje správce pro přístup ke konzole Zimperium MTD

### <a name="zimperium-app-authorization"></a>Autorizace aplikace Zimperium

Postup autorizace aplikace Zimperium:

-   Udělení oprávnění služby Zimperium informací týkajících se stavu zařízení zpět do Intune. Udělení oprávnění, že je nutné použít přihlašovací údaje globálního správce. Udělení oprávnění se o jednorázovou operaci. Jakmile budou oprávnění udělena, nejsou potřebné přihlašovací údaje globálního správce pro každodenní operace.

-   Zimperium se synchronizuje s členstvím skupiny registrace Azure Active Directory (AD), aby se mohla naplnit databáze zařízení.

-   Povolte u konzoly pro správu Zimperium použití jednotného přihlašování (SSO) k Azure AD.

-   Povolte aplikaci Zimperium přihlášení pomocí jednotného přihlašování k Azure AD.

Další informace o souhlas a aplikace Azure Active Directory najdete v tématu [požádat o oprávnění od správce adresáře](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#request-the-permissions-from-a-directory-admin) v Azure Active Directory článku *oprávnění a vyjádření souhlasu v Azure Active Koncový bod v2.0 Directory*.


## <a name="to-set-up-zimperium-integration"></a>Nastavení integrace řešení Zimperium

1.  Přejděte na [konzole Zimperium MTD](https://sso.zimperium.com/signon/aad/) a přihlaste se pomocí svých přihlašovacích údajů. K provedení instalačního procesu integrace řešení Zimperium, musíte se přihlásit pomocí Azure Active Directory uživatele, který má roli globálního správce. Tato operace jednorázová nastavení používá oprávnění globálního správce k udělení oprávnění ve vaší organizaci pro aplikace Zimperium s Intune komunikovat. 

2.  Zvolte z levé nabídky možnost **Management** (Správa).

3.  Zvolte **nastavení MDM** kartu.

4.  Zvolte **Add MDM** (Přidat MDM) a pak vyberte **Microsoft Intune** ze seznamu **MDM provider** (Zprostředkovatel MDM).

5.  Po nastavení Microsoft Intune jako služby MDM **konfigurace v Microsoft Intune** okno otevře, zvolte **přidat Azure Active Directory** jednotlivých možností: **Zimperium zConsole**, **zIPS pro iOS a Android apps** řešení zimperium komunikovalo s Intune a Azure AD prostřednictvím Azure AD jednotného přihlašování.

    > [!IMPORTANT]  
    > Je nutné přidat Zimperium zConsole, zIPS pro iOS a Android k dokončení procesu integrace s Intune.

6.  Zvolte **přijmout** autorizovat aplikaci Zimperium komunikovalo s Intune a Azure Active Directory.

7.  Po přidání **Zimperium zConsole** a **zIPS pro iOS a Android** aplikací do služby Azure AD přidejte skupiny zabezpečení Azure AD. Tím umožníte, aby aplikace Zimperium mohla příslušnou skupinu zabezpečení Azure AD synchronizovat se svou službou.

8.  Zvolte **Dokončit** uložte konfiguraci a spusťte první synchronizaci skupiny zabezpečení Azure AD.

9.  Odhlaste se z konzole Zimperium MTD.

## <a name="next-steps"></a>Další postup

-   [Nastavení aplikací Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
