---
title: Odebrání zařízení s Androidem z Intune | Microsoft Docs
description: Popisuje zrušení registrace zařízení s Androidem v Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/23/2018
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
ms.openlocfilehash: ec3c0a1c8ce4e04f4d23fb01e7c2525d8f2eed5b
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-remove-your-android-device-from-intune"></a>Odebrání zařízení s Androidem z Intune

Pokud zařízení s Androidem odeberete z Intune, ztratí přístup k prostředkům společnosti.  Další informace o důsledcích odebrání zařízení ze správy najdete v tématu [Co se stane, když zrušíte registraci zařízení v Intune](what-happens-if-you-unenroll-your-device-from-intune-android.md).

## <a name="removing-the-device-from-the-company-portal-app"></a>Odebrání zařízení z aplikace Portál společnosti

K odebrání zařízení z Intune a z aplikace Portál společnosti použijte tento postup:

1. Klepnutím na tři svislé tečky v pravém horním rohu aplikace Portál společnosti otevřete **nabídku akcí**.

   ![Obrázek aplikace Portál společnosti pro Android s otevřenou nabídkou akcí v pravém horním rohu Nová možnost Odebrat Portál společnosti je k dispozici jako třetí pod možnostmi Můj profil a Nastavení a nad možnostmi Podmínky, Nápověda a váš názor a O produktu.](./media/android_remove_cp_menu_action_after_1705.png)

2. Klepněte na **Odebrat Portál společnosti**.

3. Zobrazí se potvrzení s dotazem, jestli opravdu chcete odebrat aplikaci Portál společnosti. Zobrazí se také informace o tom, co se stane, když registraci zařízení zrušíte. Po přečtení zprávy pokračujte klepnutím na **OK**. Tím aplikaci odeberete.

   ![Obrázek potvrzovacího okna, které se otevře, když v nabídce akcí vyberete možnost Odebrat Portál společnosti. V dialogovém okně se uživateli zobrazí zpráva, že pokud odebere Portál společnosti, nebude firemní podpora už moct jeho zařízení spravovat a může mu odebrat přístup k firemním datům, aplikacím a e-mailu. Pak uživatele vyzve, aby potvrdil, že chce aplikaci Portál společnosti skutečně odebrat. Pokud ji uživatel chce odebrat, vybere Ano.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="removing-data-collected-by-the-company-portal-app"></a>Odebrání dat shromažďovaných aplikací Portál společnosti

Postup odebrání všech dat, která do zařízení uložila aplikace Portál společnosti pro Android:

-   V Aplikacích vymažte data aplikace -> klikněte na aplikaci -> tlačítko Vymazat data.
-   Odstraňte složku „\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal“.

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://portal.manage.microsoft.com#HelpDeskDialog).
