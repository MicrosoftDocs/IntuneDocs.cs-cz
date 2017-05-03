---
title: "Nastavení rozložení domovské obrazovky pro zařízení s iOSem"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o nastavení, pomocí nichž si můžete přizpůsobit domovskou obrazovku a Dock na zařízeních s iOSem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 4/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6aba4491-afb9-43cd-9ccc-14e6a2a5a3b1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 72bfde93389a060ed52062be0f2692b8bc35543a
ms.lasthandoff: 04/19/2017


---

# <a name="intune-home-screen-layout-settings-for-ios-devices"></a>Nastavení rozložení domovské obrazovky pro zařízení s iOSem

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Pomocí těchto nastavení můžete konfigurovat rozložení aplikací, složek a webových klipů v Docku a domovské obrazovce všech zařízení s iOSem, ke kterým přiřadíte zásady.

Zařízení s iOSem, ke kterým přiřadíte profil, musí být v režimu pod dohledem a musí používat iOS 9.3 nebo novější.

1. V okně **Funkce zařízení** zvolte **Rozložení domovské obrazovky (jenom pod dohledem)**.
2. V okně **Rozložení domovské obrazovky (jenom pod dohledem)** zvolte, zda chcete nakonfigurovat rozložení **Ukotvit** nebo **Stránky**.

## <a name="add-items-to-the-dock"></a>Přidání položek do Docku

V okně **Ukotvit** můžete přidat až 6 položek nebo složek do Docku v dolní části obrazovky iOSu. Mnoho zařízení však podporuje méně položek – zařízení iPhone podporují maximálně čtyři položky. V takovém případě se na zařízení zobrazí jenom první čtyři položky, které nakonfigurujete.

1. Zvolte **Přidat** a přidejte položku do Docku.
2. V okně **Přidat řádek** zvolte, zda chcete přidat **Aplikaci** nebo **Složku**.
3. Pomocí informací uvedených v části **Přidání aplikace do seznamu** a **Přidání složky do seznamu** v tomto tématu nakonfigurujte aplikace a složky, které se mají zobrazit v Docku.
4. Přidejte další položky podle potřeby. Až skončíte s přidáváním položek, klikněte v jednotlivých oknech na **OK**, dokud se nevrátíte do okna **Vytvořit profil**. Zvolte **Vytvořit**.

>[!TIP]
> Přetažením položek na kterékoli domovské obrazovce a v seznamech stránek můžete změnit jejich položek. 

### <a name="example"></a>Příklad

V tomto příkladu jste nakonfigurovali obrazovku Docku tak, aby se na ní zobrazovaly aplikace Safari, Mail a Stocks. Na následujícím obrázku je pro ilustraci vlastností vybraná aplikace Mail:

![Ukázkové nastavení Docku iOSu](http://i.imgur.com/FfFiUcP.png)

Když přiřadíte zásady k iPhonu, bude výsledkem Dock, který vypadá obdobně:

![Ukázkové rozložení Docku iOSu na iPhonu](http://i.imgur.com/bAgCe8F.png)

## <a name="add-home-screen-pages"></a>Přidání stránek domovské obrazovky

Přidejte stránky, které se mají zobrazovat na domovské obrazovce, a aplikace, které se budou zobrazovat na jednotlivých stránkách. Aplikace, které přidáte na stránku, jsou seřazené zleva doprava v pořadí, v jakém jsou uvedeny v seznamu. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se aplikace na další stránku.


1. V okně **Stránky** zvolte **Přidat**.
2. V okně **Přidat řádek** zadejte **Název stránky**. Název se použije pro referenci na portálu Intune a na zařízení s iOSem *se nebude zobrazovat*.
3. Zvolte **Přidat** a potom vyberte, zda na stránku chcete přidat **Aplikaci** nebo **Složku**.
4. Pomocí informací uvedených v části **Přidání aplikace do seznamu** a **Přidání složky do seznamu** v tomto tématu nakonfigurujte aplikace a složky, které se mají zobrazit na stránce.

### <a name="example"></a>Příklad

V tomto příkladu jste nakonfigurovali novou stránku s názvem **Contoso**. Na stránce se zobrazují jenom aplikace Najít přátele a Nastavení. Na následujícím obrázku je pro ilustraci vlastností vybraná aplikace Nastavení:

![Příklad nastavení domovské obrazovky iOSu](http://i.imgur.com/Jc2OxyX.png)

Když přiřadíte zásady k iPhonu, bude výsledkem stránka, která vypadá obdobně:

![Zařízení s iOSem se změněnou domovskou obrazovkou](http://i.imgur.com/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a>Přidání aplikace do seznamu

1. Zadejte **Název aplikace**. Název se použije pro referenci na portálu Intune a na zařízení s iOSem *se nebude zobrazovat*.
2. Zadejte **ID sady prostředků aplikace**, kterou chcete zobrazit. Pomůžou vám **Referenční informace o ID sady prostředků pro integrované aplikace pro iOS** dále v tomto tématu.
3. Klikněte na **OK** a podle potřeby přidejte další položky, maximálně ale **6** pro Dock zařízení a **60** pro stránku zařízení.
4. Po skončení klikněte na tlačítko **OK**.

## <a name="how-to-add-a-folder-to-the-list"></a>Přidání složky do seznamu

Aplikace, které přidáte na stránku ve složce, jsou seřazené zleva doprava v pořadí, v jakém jsou uvedeny v seznamu. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se aplikace na další stránku.

1. Zadejte **Název složky**. Tento název se bude zobrazovat uživatelům na zařízení.
2. Zvolte **Přidat** a vytvořte ve složce stránku. Můžete přidat až 20 stránek.
3. V okně **Přidat řádek** zadejte název stránky. Název se použije pro referenci na portálu Intune a na zařízení s iOSem *se nebude zobrazovat*.
3. Zadejte **Název aplikace**. Název se použije pro referenci na portálu Intune a na zařízení s iOSem *se nebude zobrazovat*.
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


