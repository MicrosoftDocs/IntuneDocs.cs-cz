---
title: Odebrání zařízení s Androidem z Intune | Microsoft Docs
description: Popisuje zrušení registrace zařízení s Androidem v Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f40aab26-7613-48cc-a74e-de83df9465a4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: d932005c955afed7f16e9766b559b77b2cd43182
ms.sourcegitcommit: 604b29c480b24270b5debc3e5f3141c8149ee6ed
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/24/2018
ms.locfileid: "49959481"
---
# <a name="unenroll-your-android-device-from-management"></a>Zrušení správy registrovaného zařízení s Androidem  

Pokud organizace nechce zaregistrované zařízení s Androidem dále spravovat, může ho odebrat. V tomto článku je popsané, jak zařízení odebrat z aplikace Portál společnosti. Po odebrání zařízení:  

* Zařízení ztratí přístup k chráněným datům a prostředkům organizace.
* Zařízení se přestane zobrazovat na Portálu společnosti.
* Z Portálu společnosti nebude možné instalovat aplikace.
* Už nebudou platit nastavení, která se v zařízení změnila od jeho přidání (třeba zakázání fotoaparátu/kamery nebo vyžadování určité délky hesla).  

1. Na Portálu společnosti přejděte do pravého horního rohu a klepněte na tři svislé tečky. Otevře se nabídka akcí.

   ![Obrázek aplikace Portál společnosti pro Android s otevřenou nabídkou akcí v pravém horním rohu. Nová možnost Odebrat Portál společnosti je k dispozici jako třetí pod možnostmi Můj profil a Nastavení a nad možnostmi Podmínky, Nápověda a váš názor a O produktu.](./media/android_remove_cp_menu_action_after_1705.png)

2. Klepněte na **Odebrat Portál společnosti**.  

3. Zobrazí se zpráva s informacemi o tom, co se stane, když zrušíte registraci zařízení. Pokud chcete potvrdit, že chcete zařízení z Portálu společnosti odebrat, klepněte na **OK**.

   ![Obrázek potvrzovacího okna, které se otevře, když v nabídce akcí vyberete možnost Odebrat Portál společnosti. V dialogovém okně se uživateli zobrazí zpráva, že pokud odebere Portál společnosti, nebude firemní podpora už moct jeho zařízení spravovat a může mu odebrat přístup k firemním datům, aplikacím a e-mailu. Pak uživatele vyzve, aby potvrdil, že chce aplikaci Portál společnosti skutečně odebrat. Pokud ji uživatel chce odebrat, vybere Ano.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="removing-data-collected-by-the-company-portal-app"></a>Odebrání dat shromažďovaných aplikací Portál společnosti  

Postup odebrání všech dat, která do zařízení uložila aplikace Portál společnosti pro Android:

-   V Aplikacích vymažte data aplikace -> klikněte na aplikaci -> tlačítko Vymazat data.
-   Odstraňte složku „\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal“.

## <a name="uninstall-the-company-portal-app"></a>Odinstalace aplikace Portál společnosti  
Portál společnosti je aplikace, která slouží ke správě zařízení. Tuto aplikaci nemůžete odinstalovat, dokud [nezrušíte registraci spravovaného zařízení](unenroll-your-device-from-intune-android.md#unenroll-your-android-device-from-management). Jakmile registraci zrušíte, klepněte na ikonu aplikace Portál společnosti a podržte ji, dokud se nezobrazí **Odinstalovat**. Klepněte na **Odinstalovat** a aplikaci ze zařízení odeberte.  

Můžete také klepnout na **Nastavení** > **Aplikace** > **Portál společnosti** > **Odinstalovat**.  

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).
