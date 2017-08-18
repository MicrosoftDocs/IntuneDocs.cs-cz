---
title: "Konfigurace zásad aktualizací pro iOS"
titleSuffix: Intune on Azure
description: "Zásady aktualizací pro iOS můžete nakonfigurovat tak, že donutíte zařízení s iOSem, která jsou pod dohledem, aby automaticky instalovala nejnovější dostupnou aktualizaci softwaru."
keywords: 
author: dougeby
manager: dougeby
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6334421-85e1-4457-9c44-e5db8d4ee00e
ms.openlocfilehash: d4af2d58ec21c54362cf451eac1a33b2088885d5
ms.sourcegitcommit: 7674efb7de5ad54390801165364f5d9c58ccaf84
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2017
---
# <a name="configure-ios-update-policies"></a>Konfigurace zásad aktualizací pro iOS
Zásady aktualizací pro iOS můžete aktualizovat tak, abyste mohli zařízení s iOSem, která jsou pod dohledem, donutit automaticky instalovat nejnovější dostupnou aktualizaci softwaru. Máte možnost nakonfigurovat dny a časy, kdy nechcete, aby zařízení instalovala aktualizace.

## <a name="configure-the-ios-update-policy"></a>Konfigurace zásad aktualizací pro iOS
1. Přejděte na portálu Azure Portal do okna Intune.
2. V okně **Intune** zvolte **Aktualizace softwaru** > **Zásady aktualizací pro iOS**.
4. V okně Zásady zvolte **Vytvořit**a zadejte název a popis zásady.
5. Vyberte **Nastavení** > **Konfigurovat**a zadejte podrobnosti o časech, kdy nechcete u zařízení s iOSem vynucovat instalaci nejnovějších aktualizací.
6. Tuto konfiguraci uložíte zvolením tlačítka **OK**. A jste zpátky v okně **Vytvořit zásadu aktualizace**. Zvolením možnosti **Vytvořit** vytvoříte zásadu a uložíte své nastavení.

Zásada se vytvoří a zobrazí se v okně se seznamem zásad aktualizací pro iOS.

## <a name="assign-an-ios-update-policy-to-users"></a>Přiřazení zásad aktualizací pro iOS uživatelům
Pokud chcete přiřadit zásady aktualizací pro iOS uživatelům, vyberte zásady, které jste nakonfigurovali. Existující zásady najdete v okně **Aktualizace softwaru** > **Zásady aktualizace pro iOS**.
1. Vyberte zásady, které chcete přiřadit uživatelům, a zvolte **Přiřazení**. Otevře se okno, kde můžete vybrat skupiny zabezpečení Azure Active Directory a přiřadit je k zásadám.
2. Zvolte **Vybrat skupiny** a otevřete tak okno, ve kterém se zobrazí skupiny zabezpečení v Azure AD. Volbou **Vybrat** zásady nasadíte u určených uživatelů.

Tím jste zásady uplatnili u uživatelů. U zařízení používaných uživateli, na které zásady cílí, se bude vyhodnocovat dodržování předpisů pro aktualizace.

## <a name="change-the-restricted-days-for-the-policy"></a>Změna počtu dnů s omezeným přístupem u zásady
1. V okně **Aktualizace softwaru** zvolte **Zásady aktualizací pro iOS**.
2. Vyberte zásady, které chcete aktualizovat.
3. Vyberte **Vlastnosti** a upravte informaci o počtu dnů s omezeným přístupem.
