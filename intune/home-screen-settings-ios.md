---
title: "Nastavení rozložení domovské obrazovky pro zařízení s iOSem"
titlesuffix: Azure portal
description: "Přečtěte si o nastaveních, pomocí nichž si můžete přizpůsobit domovskou obrazovku a Dock na zařízeních s iOSem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6aba4491-afb9-43cd-9ccc-14e6a2a5a3b1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4a3f175337d521c92c909db9972d844ac6997cb0
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="intune-home-screen-layout-settings-for-ios-devices"></a>Nastavení rozložení domovské obrazovky pro zařízení s iOSem

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pomocí těchto nastavení můžete konfigurovat rozložení aplikací, složek a webových klipů v Docku a na domovské obrazovce iOSu.

Zařízení s iOSem, ke kterým přiřadíte profil, musí být v režimu pod dohledem a musí používat iOS 9.3 nebo novější.

1. V okně **Funkce zařízení** zvolte **Rozložení domovské obrazovky (jenom pod dohledem)**.
2. V okně **Rozložení domovské obrazovky (jenom pod dohledem)** zvolte, zda chcete nakonfigurovat rozložení **Ukotvit** nebo **Stránky**.

## <a name="add-items-to-the-dock"></a>Přidání položek do Docku

V okně **Ukotvit** můžete přidat až šest položek nebo složek do Docku obrazovky iOSu. Mnoho zařízení však podporuje méně položek – zařízení iPhone například podporují maximálně čtyři položky. V takovém případě se na zařízení zobrazí jenom první čtyři položky, které nakonfigurujete.

1. Zvolte **Přidat** a přidejte položku do Docku.
2. V okně **Přidat řádek** zvolte, zda chcete přidat **Aplikaci** nebo **Složku**.
3. Pomocí informací v tomto tématu nakonfigurujte aplikace a složky, které se mají zobrazit v Docku.
4. Přidejte další položky podle potřeby. Až skončíte s přidáváním položek, klikněte v jednotlivých oknech na **OK**, dokud se nevrátíte do okna **Vytvořit profil**. Zvolte **Vytvořit**.

>[!TIP]
> Přetažením položek na kterékoli domovské obrazovce a v seznamech stránek můžete změnit jejich položek. 

### <a name="example"></a>Příklad

V tomto příkladu jste nakonfigurovali obrazovku Docku tak, aby se na ní zobrazovaly aplikace Safari, Mail a Stocks. Na následujícím obrázku je pro ilustraci vlastností vybraná aplikace Mail:

![Ukázkové nastavení Docku iOSu](http://i.imgur.com/FfFiUcP.png)

Když přiřadíte zásady k iPhonu, výsledkem bude Dock, který se podobá tomuto snímku obrazovky:

![Ukázkové rozložení Docku iOSu na iPhonu](http://i.imgur.com/bAgCe8F.png)

## <a name="add-home-screen-pages"></a>Přidání stránek domovské obrazovky

Přidejte stránky, které se mají zobrazovat na domovské obrazovce, a aplikace, které se zobrazí na jednotlivých stránkách. Aplikace, které přidáte na stránku, jsou seřazené zleva doprava v pořadí, v jakém jsou uvedeny v seznamu. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se na další stránku.


1. V okně **Stránky** zvolte **Přidat**.
2. V okně **Přidat řádek** zadejte **Název stránky**. Tento název slouží pro referenci na Azure Portalu, přičemž na zařízení s iOSem *se nezobrazuje*.
3. Zvolte **Přidat** a potom vyberte, zda na stránku chcete přidat **Aplikaci** nebo **Složku**.
4. Pomocí informací v tomto tématu nakonfigurujte aplikace a složky, které se mají zobrazit na stránce.

### <a name="example"></a>Příklad

V tomto příkladu jste nakonfigurovali novou stránku s názvem **Contoso**. Na stránce se zobrazují jenom aplikace Najít přátele a Nastavení. Na následujícím obrázku je pro ilustraci vlastností vybraná aplikace Nastavení:

![Příklad nastavení domovské obrazovky iOSu](http://i.imgur.com/Jc2OxyX.png)

Když přiřadíte zásady k iPhonu, výsledkem bude stránka, která se podobá tomuto snímku obrazovky:

![Zařízení s iOSem se změněnou domovskou obrazovkou](http://i.imgur.com/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a>Přidání aplikace do seznamu

1. Zadejte **Název aplikace**. Tento název slouží pro referenci na Azure Portalu, přičemž na zařízení s iOSem *se nezobrazuje*.
2. Zadejte **ID sady prostředků aplikace**, kterou chcete zobrazit. Pomůžou vám **Referenční informace o ID sady prostředků pro integrované aplikace pro iOS** dále v tomto tématu.
3. Klikněte na **OK** a podle potřeby přidejte další položky, maximálně ale **6** pro Dock zařízení a **60** pro stránku zařízení.
4. Po skončení klikněte na tlačítko **OK**.

## <a name="how-to-add-a-folder-to-the-list"></a>Přidání složky do seznamu

Aplikace, které přidáte na stránku ve složce, jsou seřazené zleva doprava v pořadí, v jakém jsou uvedeny v seznamu. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se na další stránku.

1. Zadejte **Název složky**. Tento název se uživatelům zobrazí na jejich zařízení.
2. Zvolte **Přidat** a vytvořte ve složce stránku. Můžete přidat až 20 stránek.
3. V okně **Přidat řádek** zadejte název stránky. Tento název slouží pro referenci na Azure Portalu, přičemž na zařízení s iOSem *se nezobrazuje*.
3. Zadejte **Název aplikace**. Tento název slouží pro referenci na Azure Portalu, přičemž na zařízení s iOSem *se nezobrazuje*.
2. Zadejte **ID sady prostředků aplikace**, kterou chcete zobrazit. Nápovědu získáte v tématu **Přidání aplikace do seznamu**.
3. Zvolte **Přidat**. Můžete přidat až 60 položek.
4. Po skončení klikněte na tlačítko **OK**.


## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Referenční informace o ID sady prostředků pro integrované aplikace pro iOS

Tento seznam zobrazuje ID sady prostředků některých běžných integrovaných aplikací pro iOS. Pokud chcete najít ID sady prostředků jiných aplikací, obraťte se na dodavatele softwaru. 

|||
|-|-|
|Název aplikace|ID sady prostředků|
|App Store|com.apple.AppStore|
|Kalkulačka|com.apple.calculator|
|Kalendář|com.apple.mobilecal|
|Fotoaparát|com.apple.camera|
|Hodiny|com.apple.mobiletimer|
|Kompas|com.apple.compass|
|Kontakty|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Najít přátele|com.apple.mobileme.fmf1|
|Najít iPhone|com.apple.mobileme.fmip1|
|Herní centrum|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Stav|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|Mapy|com.apple.Maps|
|Zprávy|com.apple.MobileSMS|
|Hudba|com.apple.Music|
|News|com.apple.news|
|Poznámky|com.apple.mobilenotes|
|Numbers|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Fotky|com.apple.mobileslideshow|
|Podcasty|com.apple.podcasts|
|Připomínky|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Nastavení|com.apple.Preferences|
|Stocks|com.apple.stocks|
|Tipy|com.apple.tips|
|Videa|com.apple.videos|
|Diktafon|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Watch|com.apple.Bridge|
|Počasí|com.apple.weather|


## <a name="next-steps"></a>Další kroky

Nyní můžete profil zařízení přiřadit do požadované skupiny. Podrobnosti najdete v tématu [Přiřazení profilů zařízení](device-profile-assign.md).