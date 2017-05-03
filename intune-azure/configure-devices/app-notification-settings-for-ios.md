---
title: "Nastavení oznámení aplikací pro zařízení s iOSem v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o nastaveních, pomocí kterých můžete řídit oznámení z aplikací na zařízeních s iOSem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: ea4a7a57b853b27008e42fbc635da2d9a14026fd
ms.lasthandoff: 04/19/2017


---

# <a name="intune-app-notifications-settings-for-ios-devices"></a>Nastavení oznámení aplikací pro zařízení s iOSem v Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Umožňuje konfigurovat, jak aplikace nainstalované v zařízení zasílají oznámení. Toto nastavení podporuje zařízení pod dohledem s iOSem 9.3 a novějším.

## <a name="configure-settings"></a>Konfigurace nastavení

1. V okně **Funkce zařízení** zvolte **Oznámení aplikací (jenom pod dohledem)**.
2. V okně **Oznámení aplikací** zvolte **Přidat**a pak nakonfigurujte tyto hodnoty:
    - **ID sady prostředků aplikace** –zadejte **ID sady prostředků aplikace**, kterou chcete konfigurovat. Pomůžou vám **Referenční informace o ID sady prostředků pro integrované aplikace pro iOS** dále v tomto tématu.
    - **Název aplikace** –zadejte název aplikace, kterou chcete konfigurovat. V zařízení se tato hodnota nezobrazuje a slouží ke snadnější identifikaci aplikace v seznamu.
    - **Vydavatel** –zadejte vydavatele, kterou chcete konfigurovat. V zařízení se tato hodnota nezobrazuje a slouží ke snadnější identifikaci aplikace v seznamu.
    - **Oznámení** – povolte nebo zakažte aplikaci zasílání oznámení v zařízení. Pokud toto nastavení zakážete, zakážou se i následující nastavení.
        - **Zobrazit v Centru oznámení** – povolením umožníte, aby aplikace zobrazovala oznámení v centru oznámení zařízení.
        - **Zobrazit na zamykací obrazovce** – povolením umožníte zobrazování oznámení z aplikace na zamykací obrazovce zařízení.
        - **Typ výstrahy** – vyberte požadovaný typ oznámení, když je zařízení odemčené, z těchto možností:
            - **Žádné** – nezobrazí se žádné oznámení.
            - **Informační zpráva** – krátce se zobrazí informační zpráva zobrazující oznámení.
            - **Modální** – zobrazí se oznámení a uživatel ho musí ručně zavřít, aby mohl pokračovat v používání zařízení.
        - **Odznáček na ikoně aplikace** – když tuto možnost povolíte, na ikonu aplikace se přidá odznáček udávající, že aplikace odeslala oznámení.
        - **Zvuky** – když tuto možnost povolíte, při doručení oznámení se přehraje zvuk.
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
|Zdraví|com.apple.Health|
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
