---
title: "Konfigurace zásad aktualizace iOS v Microsoft Intune"
titlesuffix: 
description: "Zásady aktualizací pro iOS můžete nakonfigurovat tak, že donutíte zařízení s iOSem, která jsou pod dohledem, aby automaticky instalovala nejnovější dostupnou aktualizaci softwaru."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.openlocfilehash: 2062f9cd551ec6d7f42449041e6c8de837221631
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Konfigurace zásad aktualizace iOS v Microsoft Intune
Zásady aktualizací pro iOS můžete aktualizovat tak, abyste mohli zařízení s iOSem, která jsou pod dohledem, donutit automaticky instalovat nejnovější dostupnou aktualizaci softwaru. Máte možnost nakonfigurovat dny a časy, kdy nechcete, aby zařízení instalovala aktualizace.

## <a name="configure-the-ios-update-policy"></a>Konfigurace zásad aktualizací pro iOS
1. Přejděte na portálu Azure Portal na stránku Intune.
2. Na stránce **Intune** zvolte **Aktualizace softwaru** > **Zásady aktualizací pro iOS**.
4. Na stránce se zásadami zvolte **Vytvořit** a zadejte název a popis zásady.
5. Vyberte **Nastavení** > **Konfigurovat** a zadejte podrobnosti o časech, kdy nechcete u zařízení s iOSem vynucovat instalaci nejnovějších aktualizací.
6. Tuto konfiguraci uložíte zvolením tlačítka **OK**. A jste zpátky na stránce **Vytvořit zásadu aktualizace**. Zvolením možnosti **Vytvořit** vytvoříte zásadu a uložíte své nastavení.

Zásada se vytvoří a zobrazí se na stránce se seznamem zásad aktualizací pro iOS.

## <a name="assign-an-ios-update-policy-to-users"></a>Přiřazení zásad aktualizací pro iOS uživatelům
Pokud chcete přiřadit zásady aktualizací pro iOS uživatelům, vyberte zásady, které jste nakonfigurovali. Existující zásady najdete na stránce **Aktualizace softwaru** > **Zásady aktualizace pro iOS**.
1. Vyberte zásady, které chcete přiřadit uživatelům, a zvolte **Přiřazení**. Otevře se stránka, kde můžete vybrat skupiny zabezpečení Azure Active Directory a přiřadit je k zásadám.
2. Zvolte **Vybrat skupiny** a otevřete tak stránku, na které se zobrazí skupiny zabezpečení v Azure AD. Volbou **Vybrat** zásady nasadíte u určených uživatelů.

Tím jste zásady uplatnili u uživatelů. U zařízení používaných uživateli, na které zásady cílí, se vyhodnotí dodržování předpisů pro aktualizace.

## <a name="change-the-restricted-days-for-the-policy"></a>Změna počtu dnů s omezeným přístupem u zásady
1. Na stránce **Aktualizace softwaru** zvolte **Zásady aktualizací pro iOS**.
2. Vyberte zásady, které chcete aktualizovat.
3. Vyberte **Vlastnosti** a upravte informaci o počtu dnů s omezeným přístupem.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>Sledování zařízení se staršími verzemi iOSu 
<!-- 1352223 -->
Stránka **zařízení se zastaralým iOSem** je k dispozici v okně **Aktualizace softwaru** > **Zásady aktualizace iOSu**. V sestavě můžete zobrazit seznam zařízení s iOSem pod dohledem, na která byla zacílena zásada aktualizace iOSu a která se nepodařilo aktualizovat. Pro každé zařízení můžete zobrazit stav, proč nebylo automaticky aktualizováno.