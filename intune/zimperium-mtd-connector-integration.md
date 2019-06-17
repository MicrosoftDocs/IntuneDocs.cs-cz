---
title: Integrace služby Zimperium MTD s Microsoft Intune
titleSuffix: Microsoft Intune
description: Přečtěte si, jak integrovat řešení Zimperium Mobile Threat Defense s Microsoft Intune, abyste mohli regulovat přístup mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/04/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: db7f008e67c0523a373da24dd0a04f3556d9dd4c
ms.sourcegitcommit: 119962948045079022aa48f968dde3e961d7cd0c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2019
ms.locfileid: "67031378"
---
# <a name="integrate-zimperium-with-intune"></a>Integrace řešení Zimperium do Intune

Při integraci řešení Zimperium Mobile Threat Defense do Intune je potřeba provést následující kroky.

## <a name="before-you-begin"></a>Před zahájením

> [!NOTE]
> Následující kroky je potřeba provést v [konzole Zimperium MTD](https://www.zimperium.com/platform).

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

1.  Přejděte do [konzoly Zimperium MTD](https://www.zimperium.com/platform) a přihlaste se pomocí přihlašovacích údajů. K provedení instalačního procesu integrace řešení Zimperium, musíte se přihlásit pomocí Azure Active Directory uživatele, který má roli globálního správce. Tato operace jednorázová nastavení používá oprávnění globálního správce k udělení oprávnění ve vaší organizaci pro aplikace Zimperium s Intune komunikovat. 

2.  Zvolte z levé nabídky možnost **Management** (Správa).

3.  Vyberte kartu **MDM settings** (Nastavení MDM).

4.  Zvolte **Add MDM** (Přidat MDM) a pak vyberte **Microsoft Intune** ze seznamu **MDM provider** (Zprostředkovatel MDM).

5.  Po nastavení Microsoft Intune jako služby MDM **konfigurace v Microsoft Intune** okno otevře, zvolte **přidat Azure Active Directory** jednotlivých možností: **Zimperium zConsole**, **zIPS pro iOS a Android apps** řešení zimperium komunikovalo s Intune a Azure AD prostřednictvím Azure AD jednotného přihlašování.

    > [!IMPORTANT]  
    > Je nutné přidat Zimperium zConsole, zIPS pro iOS a Android k dokončení procesu integrace s Intune.

6.  Volbou **Accept** (Přijmout) povolte komunikaci aplikace Zimperium s Intune a Azure Active Directory.

7.  Po přidání **Zimperium zConsole** a **zIPS pro iOS a Android** aplikací do služby Azure AD přidejte skupiny zabezpečení Azure AD. Tím umožníte, aby aplikace Zimperium mohla příslušnou skupinu zabezpečení Azure AD synchronizovat se svou službou.

8.  Volbou **Finish** (Dokončit) uložte konfiguraci a spusťte první synchronizaci skupiny zabezpečení Azure AD.

9.  Odhlaste se z konzole Zimperium MTD.

## <a name="next-steps"></a>Další postup

-   [Nastavení aplikací Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
