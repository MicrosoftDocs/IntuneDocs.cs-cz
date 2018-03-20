---
title: "Zobrazení zařízení pomocí Microsoft Intune – Azure | Microsoft Docs"
description: "Zobrazte si podrobnosti o zařízení, včetně operačních systémů, místa v úložišti, výrobce a modelu a dalších informací. Microsoft Intune v Azure vám umožňuje získat seznam nainstalovaných aplikací, zkontrolovat zásady dodržování předpisů, nastavit TeamViewer a provádět mnoho dalších akcí. Jedná se o podobný princip jako při zobrazení inventáře zařízení, která spravujete."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 934ba0853f8bee851f7027580c276a9fff911b7f
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="see-device-details-in-intune"></a>Zobrazení podrobností o zařízení v Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Funkce **Zařízení** poskytuje další podrobnosti o zařízení, která spravujete, včetně jejich hardwaru a nainstalovaných aplikací. 

V tomto článku se dozvíte, jak si můžete zobrazit všechna zařízení a jejich vlastnosti na portálu Azure Portal.

## <a name="view-your-device-details"></a>Zobrazení podrobností o zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Zařízení**. V rámci Zařízení máte několik možností:

  - **Přehled** – získáte informace o zaregistrovaných zařízeních a operačních systémech na jednotlivých zařízeních.
  - **Spravovat** – pokud chcete zobrazit seznam všech zařízení, která spravujete, zvolte **Všechna zařízení** nebo **Zařízení Azure AD**.
    V seznamu vyberte jedno ze zařízení. Tímto krokem otevřete **přehled** zařízení <*název zařízení*> , kde můžete vybrat následující možnosti:
    - **Přehled** – zobrazí název zařízení, jeho vlastníka, zda se jedná o vlastní zařízení uživatele (BYOD), kdy bylo vráceno se změnami a další podrobnosti.
    - **Hardware** – zobrazí volný úložný prostor, model, výrobce a další podrobnosti o zařízení.
    - **Zjištěné aplikace** – zobrazí seznam všech nainstalovaných aplikací, které služba Intune našla na zařízení.
    - **Dodržování předpisů zařízením** – zobrazí stav všech zásad dodržování předpisů, které se týkají zařízení.
    - **Konfigurace zařízení** – zobrazí stav dodržování předpisů všech zásad konfigurace zařízení, které se týkají daného zařízení.
- **Monitorování** – volbou možnosti **Akce zařízení** zobrazíte seznam akcí, které byly na spravovaných zařízeních provedeny, a jejich aktuální stav. **Protokoly auditu** – zobrazí stav různých úloh.
- **Nastavení** > **Konektor pro TeamViewer**  – umožňuje konfiguraci vzdálené správy na zařízeních pomocí softwaru TeamViewer. Další informace najdete v tématu [Poskytování vzdálené pomoci pro zařízení s Androidem, která se spravují přes Intune](device-profile-android-teamviewer.md).

Intune shromažďuje seznam aplikací jenom na zařízeních vlastněných společností. Na osobních zařízeních se aplikace nekontrolují. V případě počítačů s Windows 10 se uvádí jenom moderní aplikace na zařízeních vlastněných společností. Intune neshromažďuje informace o aplikacích Win32 na zařízeních. V závislosti na operátorovi, kterého zařízení používá, se některé aplikace nemusí shromažďovat.

## <a name="next-steps"></a>Další kroky
Podívejte se, jaké další akce [správy zařízení](device-management.md) můžete provádět pomocí Intune.
