---
title: Zobrazení zařízení pomocí Microsoft Intune – Azure | Microsoft Docs
description: Zobrazte si podrobnosti o zařízení, včetně operačních systémů, místa v úložišti, výrobce a modelu. Microsoft Intune v Azure vám umožňuje získat seznam nainstalovaných aplikací, zkontrolovat zásady dodržování předpisů a nastavit TeamViewer. Jedná se o podobný princip jako při zobrazení inventáře zařízení, která spravujete.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eaaf3e9807a8eab66c24f4d1bb3c3c5ea9f4cfe0
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="see-device-details-in-intune"></a>Zobrazení podrobností o zařízení v Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Funkce **Zařízení** poskytuje další podrobnosti o zařízení, která spravujete, včetně jejich hardwaru a nainstalovaných aplikací. 

V tomto článku se dozvíte, jak si můžete zobrazit všechna zařízení a jejich vlastnosti na portálu Azure Portal.

## <a name="view-your-device-details"></a>Zobrazení podrobností o zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Zařízení**. V rámci Zařízení máte několik možností:

   - **Přehled**: Získáte informace o zaregistrovaných zařízeních a operačních systémech na jednotlivých zařízeních.
   - **Spravovat**: Pokud chcete zobrazit seznam všech zařízení, která spravujete, zvolte **Všechna zařízení** nebo **Zařízení Azure AD**.
    V seznamu vyberte jedno ze zařízení. Tímto krokem otevřete **přehled** zařízení <*název zařízení*> , kde můžete vybrat následující možnosti:
     - **Přehled**: Zobrazí název zařízení, jeho vlastníka, zda se jedná o vlastní zařízení uživatele (BYOD), kdy se ohlásilo a další podrobnosti.
     - **Hardware**: Zobrazí volný úložný prostor, model, výrobce a další podrobnosti o zařízení.
     - **Zjištěné aplikace**: Zobrazí seznam všech nainstalovaných aplikací, které služba Intune na zařízení našla.
     - **Dodržování předpisů zařízením**: Zobrazí stav všech zásad dodržování předpisů, které se týkají zařízení.
     - **Konfigurace zařízení**: Zobrazí stav dodržování předpisů všech zásad konfigurace zařízení, které se týkají daného zařízení.
   - **Monitorování**: Volbou možnosti **Akce zařízení** zobrazíte seznam akcí, které byly na spravovaných zařízeních provedeny, a jejich aktuální stav. **Protokoly auditu** – zobrazí stav různých úloh.
   - **Nastavení** > **Konektor pro TeamViewer** : Umožňuje konfiguraci vzdálené správy na zařízeních pomocí softwaru TeamViewer. Další informace najdete v tématu [Poskytování vzdálené pomoci pro zařízení s Androidem, která se spravují přes Intune](device-profile-android-teamviewer.md).

Intune shromažďuje seznam aplikací jenom na zařízeních vlastněných společností. Na osobních zařízeních se aplikace nekontrolují. V případě počítačů s Windows 10 se uvádí jenom moderní aplikace na zařízeních vlastněných společností. Intune neshromažďuje informace o aplikacích Win32 na zařízeních. V závislosti na operátorovi, kterého zařízení používají, se některé aplikace nemusí shromažďovat.

## <a name="next-steps"></a>Další kroky
Podívejte se, jaké další akce [správy zařízení](device-management.md) můžete provádět pomocí Intune.
