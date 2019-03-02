---
title: Integrace kontrola Point SandBlast MTD | Microsoft Intune
titlesuffix: Microsoft Intune
description: Jak nastavit Check Point SandBlast Mobile Threat Defense (MTD) s Intune za účelem regulace přístupu mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2017
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1e9b1576-b239-48cc-a672-da6b5fb7be0a
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8302bcf6f849ffb52313e68507c2b895f5401f7a
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2019
ms.locfileid: "57230580"
---
# <a name="integrate-check-point-sandblast-mobile-with-intune"></a>Integrace Check Point SandBlast Mobile a Intune

## <a name="before-you-begin"></a>Před zahájením

> [!NOTE] 
> Následující postup je třeba provést na [konzole Check Point SandBlast Mobile MTD](https://intune-4.eu1.locsec.net/).

Před zahájením procesu integrace Check Point SandBlast Mobile a Intune zkontrolujte, že máte následující:

-   Odběr služby Microsoft Intune

-   Přihlašovací údaje správce Azure Active Directory pro udělení následujících oprávnění:

    -   Přihlášení a čtení profilu uživatele

    -   Přístup k adresáři jako přihlášený uživatel

    -   Čtení dat z adresáře

    -   Odeslání informací o zařízení do Intune

-   Přihlašovací údaje správce pro přístup ke konzole Check Point SandBlast Mobile MTD

### <a name="check-point-sandblast-app-authorization"></a>Autorizace aplikace Check Point SandBlast

Proces autorizace aplikace Check Point SandBlast:

-   Povolte službě Check Point SandBlast Mobile předávání informací týkajících se stavu zařízení zpět do Intune.

-   CheckPoint SandBlast Mobile se synchronizuje s členstvím skupiny registrace Azure AD, aby se mohla naplnit databáze zařízení.

-   Povolte u konzoly pro správu Check Point SandBlast použití jednotného přihlašování (SSO) k Azure AD.

-   Povolte aplikaci Check Point SandBlast Mobile přihlášení pomocí jednotného přihlašování k Azure AD.

## <a name="to-set-up-check-point-sandblast-mobile-integration"></a>Nastavení integrace Check Point SandBlast Mobile

1.  Přejděte do [konzoly Check Point SandBlast Mobile MTD](https://intune-4.eu1.locsec.net/) a přihlaste se pomocí přihlašovacích údajů.

2.  Klikněte na kartu **Settings** (Nastavení).

3.  Zvolte **Device management** (Správa zařízení) a pak **Settings**.

4.  V rozevíracím seznamu **MDM Service** zvolte **Microsoft Intune**.

5.  Po nastavení Microsoft Intune jako služby MDM Service se zobrazí okno pro **konfiguraci Microsoft Intune**. U každé platformy zařízení: iOS, Android a Windows zvolte **Add to my organization** (Přidat do mojí organizace), aby bylo možné autorizovat komunikaci Check Point SandBlast Mobile s Intune a Azure AD.

    ![Obrázek znázorňující konfiguraci Check Point MTD v Intune](./media/checkpoint-MTD-1.PNG)

    > [!IMPORTANT]
    > Aby bylo možné pokračovat k dalšímu kroku, je nutné přidat platformy všech zařízení.

6.  Zvolte **Accept** (Přijmout) a autorizujte tak aplikaci Check Point SandBlast Mobile pro komunikaci s Intune a Azure Active Directory.

7.  Po povolení všech platforem zařízení je nutné zadat skupinu zabezpečení Azure AD.

8.  Zvolte **Verify** (Ověřit) a po úspěšném ověření skupiny zabezpečení zvolte **Save** (Uložit).

## <a name="next-steps"></a>Další postup

- [Nastavení aplikací Check Point SandBlast Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)
