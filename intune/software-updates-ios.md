---
title: "Konfigurace zásad aktualizace iOS v Microsoft Intune"
titlesuffix: 
description: "Zásady aktualizací pro iOS můžete nakonfigurovat tak, že donutíte zařízení s iOSem, která jsou pod dohledem, aby automaticky instalovala nejnovější dostupnou aktualizaci softwaru."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.openlocfilehash: 6ba354fb3b39544f09363651abfd9e1a5c0f6154
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Konfigurace zásad aktualizace iOS v Microsoft Intune
Zásady aktualizací pro iOS můžete aktualizovat tak, abyste mohli zařízení s iOSem, která jsou pod dohledem, donutit automaticky instalovat nejnovější dostupnou aktualizaci softwaru. Máte možnost nakonfigurovat dny a časy, kdy nechcete, aby zařízení instalovala aktualizace.

## <a name="configure-the-ios-update-policy"></a>Konfigurace zásad aktualizací pro iOS
1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
2. V podokně **Intune** zvolte **Aktualizace softwaru** > **Zásady aktualizace iOSu**.
4. V podokně se zásadami zvolte **Vytvořit** a potom zadejte název a popis zásady.
5. Vyberte **Nastavení** > **Konfigurovat** a zadejte podrobnosti o časech, kdy nechcete u zařízení s iOSem vynucovat instalaci nejnovějších aktualizací.
6. Tuto konfiguraci uložíte zvolením tlačítka **OK**. A jste zpátky v podokně **Vytvořit zásady aktualizace**. Zvolením možnosti **Vytvořit** vytvoříte zásadu a uložíte své nastavení.

Zásada se vytvoří a zobrazí se v podokně se seznamem zásad aktualizací pro iOS.

## <a name="assign-an-ios-update-policy-to-users"></a>Přiřazení zásad aktualizací pro iOS uživatelům
Pokud chcete přiřadit zásady aktualizací pro iOS uživatelům, vyberte zásady, které jste nakonfigurovali. Existující zásady najdete v podokně **Aktualizace softwaru** > **Zásady aktualizace iOSu**.
1. Vyberte zásady, které chcete přiřadit uživatelům, a zvolte **Přiřazení**. Otevře se podokno, kde můžete vybrat skupiny zabezpečení Azure Active Directory a přiřadit je k zásadám.
2. Zvolte **Vybrat skupiny** a otevřete tak podokno, kde se zobrazí skupiny zabezpečení v Azure AD.
3. Volbou **Uložit** zásady nasadíte u určených uživatelů.

Tím jste zásady uplatnili u uživatelů. U zařízení používaných uživateli, na které zásady cílí, se vyhodnotí dodržování předpisů pro aktualizace.

## <a name="change-the-restricted-days-for-the-policy"></a>Změna počtu dnů s omezeným přístupem u zásady
1. V podokně **Aktualizace softwaru** zvolte **Zásady aktualizace iOSu**.
2. Vyberte zásady, které chcete aktualizovat.
3. Vyberte **Vlastnosti** > **Nastavení** a upravte informace o počtu dnů s omezeným přístupem.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>Sledování zařízení se staršími verzemi iOSu
<!-- 1352223 -->
Sestava **zařízení se zastaralým iOSem** je k dispozici v podokně **Aktualizace softwaru** > **Zásady aktualizace iOSu**. V sestavě můžete zobrazit seznam zařízení s iOSem pod dohledem, na která byla zacílena zásada aktualizace iOSu a která se nepodařilo aktualizovat. Pro každé zařízení můžete zobrazit stav, proč nebylo automaticky aktualizováno.
