---
title: Optimalizace výkonu brání přístupu k e-mailům | Dokumentace Microsoftu
description: Přečtěte si informace, jak vypnout optimalizaci u Androidu a zajistit si tak dostupnost e-mailů.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 07/07/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ad713f18-40a9-421f-aa2b-f8c21028d57c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 663da92e11befeae1f65467e887870a52640cbeb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31020567"
---
# <a name="outlook-wont-sync-managed-email-when-battery-optimization-for-android-is-turned-on"></a>V Outlooku se nesynchronizují spravované e-maily, když je zapnutá optimalizace baterie pro Android

> [!IMPORTANT]
> Tento problém jsme tady popsali, protože nás o něm informuje řada zákazníků. Pokud budete mít tento problém dál, i když se ho pokusíte vyřešit podle uvedeného postupu, požádejte o další pomoc [svou firemní podporu](https://portal.manage.microsoft.com#HelpDeskDialog).

Po registraci zařízení v Intune získáte přístup k prostředkům společnosti. Jedním z nejčastěji používaných prostředků je přístup k e-mailu. K problému, který se objevuje při přístupu k e-mailu prostřednictvím Outlooku pro zařízení s Androidem, dochází po zapnutí optimalizace baterie. Optimalizace baterie se může zapnout automaticky, aby mohlo být vaše zařízení napájeno po nejdelší možnou dobu. Optimalizace baterie k tomu může částečně pomoct, protože se pokouší zastavit automatické stahování e-mailů.

Tým Microsoft Intune na řešení tohoto problému aktivně pracuje. Jedním ze způsobů, jak zabránit přechodu zařízení do režimu snížené spotřeby energie je zajistit, že se úroveň nabití baterie nedostane pod 30 %. Pokud chcete zabránit vzniku tohoto problému při přechodu do režimu snížené spotřeby energie, musíte odebrat ze seznamu aplikací, na které má vliv optimalizace baterie a nastavení řízení spotřeby, Portál společnosti a Outlook.

Existuje mnoho zařízení s Androidem, která vyrábí celá řada výrobců. Nemůžeme zdokumentovat přesné pokyny pro každé zařízení. Je možné, že tuto akci bude nutné provést jenom v nastavení systému, ale může také být potřeba ji provést v některých nastaveních, která jsou specifická pro daného výrobce. Uvádíme několik běžných příkladů, jak tento problém můžete vyřešit na zařízeních s Androidem.

## <a name="unmodified-android-devices"></a>Neupravená zařízení s Androidem

Řada výrobců provádí u zařízení s Androidem úpravy. Můžou se tak změnit určité způsoby interakce se zařízením, jako jsou motivy a oznámení. Google obecně typy úprav telefonů neprovádí. Například na zařízení Google Pixel se systémem Android 7.0 nebo vyšším byste tyto aplikace odebrali z optimalizace baterie takto:

1. Otevřete **Nastavení**.
2. Klepněte na **Baterie** > **Další** > **Optimalizace baterie**.
3. Klepněte na šipku dolů a vyberte **Neoptimalizováno**.
4. Vyberte aplikace Portál společnosti a Outlook a vypněte optimalizaci baterie.

## <a name="samsung-devices"></a>Zařízení Samsung

U jiných typů zařízení s Androidem, jako jsou například zařízení Samsung se systémem Android 7.0 nebo vyšším, byste museli k odebrání aplikací Portál společnosti a Outlook z optimalizace baterie použít jiný postup.

1. Otevřete **Nastavení**.
2. Klepněte na **Nabídka (...)** > **Speciální přístup** > **Optimalizace výdrže baterie**.
3. V rozevíracím seznamu vyberte **Všechny aplikace**.
4. **Vypnutím** přepínače u aplikací Portál společnosti a Outlook vypněte optimalizaci baterie.

Pokud máte zařízení Samsung s nižší verzí Androidu, bude potřeba odebrat tyto aplikace z režimu úspory energie podle následujících pokynů.

1. Otevřete **Nastavení**.
2. Klepněte na **Údržba zařízení** > **Baterie** > **Nemonitorované aplikace**.
3. Klepněte na **Přidat aplikace**.
4. Vyberte aplikace Portál společnosti a Outlook a klepněte na **Hotovo**.

## <a name="oneplus-devices"></a>Zařízení OnePlus

Jako příklad dalšího způsobu, jak najít tato nastavení, je možné uvést vyhledání v nastavení systému. U zařízení OnePlus 3 s Androidem 7.1.1 byste postupovali takto: 

1. Otevřete **Nastavení systému**. 
2. Klepněte na tlačítko **Hledat**. Vypadá jako lupa napravo nahoře na obrazovce. 
3. Do pole pro hledání napište **optimalizace baterie** a vyberte možnost **Optimalizace baterie** na obrazovce **Nastavení** obrazovky, která se zobrazí. 
4. Klepněte na **Baterie** > **Optimalizace baterie**.
5. Vyberte aplikace Portál společnosti a Outlook a možnost **Neoptimalizovat**. Klepněte na **Hotovo**.

<!--On a OnePlus 5 device with Android 7.1.1, you would follow these steps to remove these apps from battery optimization:
1. Open **Settings**.
2. Tap **Battery** > **Battery optimization**.
3. Select the Company Portal and Outlook apps, then select **Don’t optimize**. Tap **Done**.-->

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Jeho kontaktní údaje najdete na [webu Portál společnosti](https://portal.manage.microsoft.com#HelpDeskDialog).
