---
title: "Nastavení oznámení aplikací pro zařízení s iOSem v Intune"
titlesuffix: Azure portal
description: "Přečtěte si o nastaveních, pomocí kterých můžete řídit oznámení z aplikací na zařízeních s iOSem."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 46b31be3cd05c0a5252589d2b25eb92b86a42733
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2017
---
# <a name="intune-app-notifications-settings-for-ios-devices"></a>Nastavení oznámení aplikací pro zařízení s iOSem v Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Umožňuje konfigurovat, jak aplikace nainstalované v zařízení zasílají oznámení. Tato nastavení podporují zařízení pod dohledem s iOSem 9.3 a novějším.

## <a name="configure-settings"></a>Konfigurace nastavení

1. V okně Funkce zařízení zvolte **Oznámení aplikací (jenom pod dohledem)**.
2. V okně **Oznámení aplikací** zvolte **Přidat**a pak nakonfigurujte tyto hodnoty:
    - **ID sady prostředků aplikace** –zadejte **ID sady prostředků aplikace**, kterou chcete konfigurovat. Pomůžou vám **Referenční informace o ID sady prostředků pro integrované aplikace pro iOS** dále v tomto tématu.
    - **Název aplikace** –zadejte název aplikace, kterou chcete konfigurovat. V zařízení se tento název nezobrazuje a slouží ke snadnější identifikaci aplikace v seznamu.
    - **Vydavatel** –zadejte vydavatele, kterou chcete konfigurovat. V zařízení se tento název vydavatele nezobrazuje a slouží pouze ke snadnější identifikaci aplikace v seznamu.
    - **Oznámení** – povolte nebo zakažte aplikaci zasílání oznámení v zařízení. Pokud toto nastavení zakážete, zakážou se i následující nastavení.
        - **Zobrazit v Centru oznámení** – povolením tohoto nastavení umožníte, aby aplikace zobrazovala oznámení v Centru oznámení zařízení.
        - **Zobrazit na zamykací obrazovce** – povolením tohoto nastavení umožníte zobrazování oznámení z aplikace na zamykací obrazovce zařízení.
        - **Typ výstrahy** – vyberte požadovaný typ oznámení, když je zařízení odemčené, z těchto možností:
            - **Žádné** – nezobrazí se žádné oznámení.
            - **Informační zpráva** – krátce se zobrazí informační zpráva zobrazující oznámení.
            - **Modální** – zobrazí se oznámení a uživatel ho musí ručně zavřít, aby mohl pokračovat v používání zařízení.
        - **Odznáček na ikoně aplikace** – když toto nastavení povolíte, na ikonu aplikace se přidá odznáček udávající, že aplikace odeslala oznámení.
        - **Zvuky** – když toto nastavení povolíte, při doručení oznámení se přehraje zvuk.
3. Přidejte tolik aplikací, kolik potřebujete. Po dokončení zvolte **OK**.
4. Zvolením **OK** se vraťte do okna **Vytvořit profil** a pak zvolte **Vytvořit**. 


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
