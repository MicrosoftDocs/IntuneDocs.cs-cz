---
title: Nastavení rozložení domovské obrazovky Microsoft Intune pro zařízení s iOSem
titleSuffix: ''
description: Přečtěte si o nastaveních v Microsoft Intune, pomocí kterých si můžete přizpůsobit domovskou obrazovku a Dock na zařízeních s iOSem.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3361ce41dfa95de0cb1a7a3bdbdbd74e7d6d5edf
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31832557"
---
# <a name="microsoft-intune-home-screen-layout-settings-for-devices-running-ios"></a>Nastavení rozložení domovské obrazovky Microsoft Intune pro zařízení s iOSem

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pomocí těchto nastavení můžete konfigurovat rozložení aplikací a složky v Docku a na domovské obrazovce zařízení s iOSem.

Zařízení s iOSem, ke kterým přiřadíte profil, musí být v režimu pod dohledem a musí používat iOS 9.3 nebo novější verzi.

1. Z [Intune na portálu Azure Portal](https://portal.azure.com) přejděte na [**Funkce zařízení** v oblasti konfigurace zařízení](device-features-configure.md).
2. V podokně **Funkce zařízení** zvolte **Rozložení domovské obrazovky (jenom pod dohledem)**.
3. V podokně **Rozložení domovské obrazovky (jenom pod dohledem)** zvolte, jestli chcete nakonfigurovat rozložení **Ukotvit** nebo **Stránky**.

## <a name="add-items-to-the-dock"></a>Přidání položek do Docku

V podokně **Ukotvit** můžete přidat až šest položek nebo složek do Docku obrazovky iOSu. Mnoho zařízení však podporuje méně položek – zařízení iPhone například podporují maximálně čtyři položky. V takovém případě se na zařízení zobrazí jenom první čtyři položky, které nakonfigurujete.

1. Zvolte **Přidat** a přidejte položku do Docku.
2. V podokně **Přidat řádek** zvolte, jestli chcete přidat **Aplikaci** nebo **Složku**.
3. Pomocí informací v tomto tématu nakonfigurujte aplikace a složky, které se mají zobrazit v Docku.
4. Přidejte další položky podle potřeby. Až skončíte s přidáváním položek, klikněte v každém podokně na **OK**, dokud se nevrátíte do podokna **Vytvořit profil**. Zvolte **Vytvořit**.

>[!TIP]
> Přetažením položek na kterékoli domovské obrazovce a v seznamech stránek můžete změnit jejich položek.

### <a name="example"></a>Příklad

V tomto příkladu jste nakonfigurovali obrazovku Docku tak, aby se na ní zobrazovaly aplikace Safari, Mail a Stocks. Na následujícím obrázku je pro ilustraci vlastností vybraná aplikace Mail:

![Ukázkové nastavení Docku iOSu](./media/FfFiUcP.png)

Když přiřadíte zásady k iPhonu, výsledkem bude Dock, který se podobá tomuto snímku obrazovky:

![Ukázkové rozložení Docku iOSu na iPhonu](./media/bAgCe8F.png)

## <a name="add-home-screen-pages"></a>Přidání stránek domovské obrazovky

Přidejte stránky, které se mají zobrazovat na domovské obrazovce, a aplikace, které se zobrazí na jednotlivých stránkách. Aplikace, které přidáte na stránku, jsou seřazené zleva doprava v pořadí, v jakém jsou uvedeny v seznamu. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se na další stránku.

1. V podokně **Stránky** zvolte **Přidat**.
2. V podokně **Přidat řádek** zadejte **Název stránky**. Tento název slouží pro referenci na Azure Portalu, přičemž na zařízení s iOSem *se nezobrazuje*.
3. Zvolte **Přidat** a potom vyberte, zda na stránku chcete přidat **Aplikaci** nebo **Složku**.
4. Pomocí informací v tomto tématu nakonfigurujte aplikace a složky, které se mají zobrazit na stránce.

### <a name="example"></a>Příklad

V tomto příkladu jste nakonfigurovali novou stránku s názvem **Contoso**. Na stránce se zobrazují jenom aplikace Najít přátele a Nastavení. Na následujícím obrázku je pro ilustraci vlastností vybraná aplikace Nastavení:

![Příklad nastavení domovské obrazovky iOSu](./media/Jc2OxyX.png)

Když přiřadíte zásady k iPhonu, výsledkem bude stránka, která se podobá tomuto snímku obrazovky:

![Zařízení s iOSem se změněnou domovskou obrazovkou](./media/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a>Přidání aplikace do seznamu

1. Zadejte **Název aplikace**. Tento název slouží pro referenci na Azure Portalu, přičemž na zařízení s iOSem *se nezobrazuje*.
2. Zadejte **ID sady prostředků aplikace**, kterou chcete zobrazit. Pomůžou vám **Referenční informace o ID sady prostředků pro integrované aplikace pro iOS** dále v tomto tématu.
3. Klikněte na **OK** a podle potřeby přidejte další položky, maximálně ale **6** pro Dock zařízení a **60** pro stránku zařízení.
4. Po skončení klikněte na tlačítko **OK**.

## <a name="how-to-add-a-folder-to-the-list"></a>Přidání složky do seznamu

Aplikace, které přidáte na stránku ve složce, jsou seřazené zleva doprava v pořadí, v jakém jsou uvedeny v seznamu. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se na další stránku.

1. Zadejte **Název složky**. Tento název se uživatelům zobrazí na jejich zařízení.
2. Zvolte **Přidat** a vytvořte ve složce stránku. Můžete přidat až 20 stránek.
3. V podokně **Přidat řádek** zadejte název stránky. Tento název slouží pro referenci na Azure Portalu, přičemž na zařízení s iOSem *se nezobrazuje*.
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
