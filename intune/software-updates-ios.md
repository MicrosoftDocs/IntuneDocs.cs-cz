---
title: Konfigurace zásad aktualizace softwaru iOS v Microsoft Intune
titlesuffix: ''
description: Zásady aktualizací pro iOS můžete nakonfigurovat tak, že donutíte zařízení s iOSem, která jsou pod dohledem, aby automaticky instalovala nejnovější dostupnou aktualizaci softwaru.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.openlocfilehash: 39432d09bea822c25ca9e11181a11a1e2298dfef
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Konfigurace zásad aktualizace iOS v Microsoft Intune

Zásady aktualizací softwaru vám umožňují vynutit, aby se na zařízení s iOSem 10.3 a novějším, která jsou pod dohledem, automaticky instalovala nejnovější dostupná aktualizace softwaru. Tato funkce je dostupná jenom pro zařízení pod dohledem. Máte možnost nakonfigurovat dny a časy, kdy nechcete, aby zařízení instalovala aktualizace. 

Když se zařízení ohlásí a je dostupná aktualizace a není to v zakázaném čase, každých 8 hodin se zařízení pokusí stáhnout a nainstalovat nejnovější aktualizaci operačního systému. Pro aktualizaci zařízení nemusí uživatel nic udělat. Zásada nezabrání tomu, aby operační systém aktualizoval uživatel.

## <a name="configure-the-ios-update-policy"></a>Konfigurace zásad aktualizací pro iOS
1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Aktualizace softwaru** > **Zásady aktualizace iOSu**.
4. V podokně se zásadami zvolte **Vytvořit** a potom zadejte název a popis zásady.
5. Vyberte **Nastavení** > **Konfigurovat** a zadejte podrobnosti o časech, kdy nechcete u zařízení s iOSem vynucovat instalaci nejnovějších aktualizací. Můžete nakonfigurovat dny v týdnu, časové pásmo, počáteční čas a koncový čas.
6. Tuto konfiguraci uložíte zvolením tlačítka **OK**. A jste zpátky v podokně **Vytvořit zásady aktualizace**. Zvolením možnosti **Vytvořit** vytvoříte zásadu a uložíte své nastavení.

Zásada se vytvoří a zobrazí se v podokně se seznamem zásad aktualizací pro iOS. Apple MDM nepovoluje možnost vynutit, aby zařízení nainstalovalo aktualizaci do konkrétního času nebo data. 

## <a name="change-the-restricted-times-for-the-policy"></a>Změna časů s omezeným přístupem u zásady

1.  V okně **Aktualizace softwaru** zvolte **Zásady aktualizací pro iOS**.
2.  Vyberte zásady, které chcete aktualizovat.
3.  Vyberte **Vlastnosti** a upravte informaci o časech s omezeným přístupem.
4.  Vyberte dny v týdnu.
5.  Časové pásmo, ve kterém se tyto zásady použijí
6.  Počáteční a koncový čas pro zakázané hodiny

## <a name="assign-an-ios-update-policy-to-users"></a>Přiřazení zásad aktualizací pro iOS uživatelům

Pokud chcete přiřadit zásady aktualizací pro iOS uživatelům, vyberte zásady, které jste nakonfigurovali. Existující zásady najdete v podokně **Aktualizace softwaru** > **Zásady aktualizace iOSu**.

1. Vyberte zásady, které chcete přiřadit uživatelům, a zvolte **Přiřazení**. Otevře se podokno, kde můžete vybrat skupiny zabezpečení Azure Active Directory a přiřadit je k zásadám.
2. Zvolte **Vybrat skupiny** a otevřete tak podokno, kde se zobrazí skupiny zabezpečení v Azure AD. Pomocí přiřazení skupin k vyloučení i zahrnutí určete, kdo má k aplikaci přístup.
3. Volbou **Uložit** zásady nasadíte u určených uživatelů.

Tím jste zásady uplatnili na uživatele nebo zařízení. U zařízení používaných uživateli, na které zásady cílí, se vyhodnotí dodržování předpisů pro aktualizace. Tyto zásady podporují také zařízení bez uživatelů.

## <a name="monitor-ios-device-installation-failures"></a>Sledování selhání instalace na zařízeních s iOSem
<!-- 1352223 -->
Sestava **Chyby instalace pro zařízení s iOSem** je k dispozici z podokna **Aktualizace softwaru**. V sestavě můžete zobrazit seznam zařízení s iOSem pod dohledem, na která byla zacílena zásada aktualizace iOSu a která se pokusila o aktualizaci, ale aktualizovat se je nepodařilo. Pro každé zařízení můžete zobrazit stav, proč nebylo automaticky aktualizováno. Zařízení, která jsou v pořádku a aktuální, se v seznamu nezobrazí. Jako aktuální definujeme nejnovější aktualizaci, kterou může samotné zařízení podporovat.
