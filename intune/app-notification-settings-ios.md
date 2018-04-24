---
title: Vytvoření oznámení aplikací pro zařízení s iOSem – Microsoft Intune – Azure | Microsoft Docs
description: Přidejte nebo vytvořte oznámení aplikací pro zařízení s iOSem v Microsoft Intune. Vyberte, které aplikace mají odesílat oznámení, nakonfigurujte nastavení oznámení na zamčené obrazovce, povolte zvuky, vyberte typ upozornění a přidejte oznámení v podobě odznaku.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 43068163c15c0588a8a6ef745d5b191f4547a94d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="configure-app-notifications-settings-on-ios-devices-in-intune"></a>Konfigurace nastavení oznámení aplikací pro zařízeních s iOSem v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Konfigurujte, jak aplikace nainstalované v zařízení s iOSem zasílají oznámení. Tato nastavení podporují zařízení pod dohledem s iOSem 9.3 a novějším.

## <a name="add-the-app-notification"></a>Přidání oznámení aplikace

1. Přihlaste se k portálu [Azure Portal](https://portal.azure.com).
2. Ve svém profilu iOSu nebo macOS vyberte **Funkce zařízení**. Postup pro vytvoření profilu najdete ve [funkcích zařízení s iOSem nebo macOS](device-features-configure.md).
3. Vyberte **Oznámení aplikací (jenom pod dohledem)** a pak vyberte **Přidat**: ![Přidání oznámení aplikací v profilu iOSu nebo macOS v Intune](./media/ios-macos-app-notifications.png)
4. Zadejte tyto vlastnosti:

   - **ID sady prostředků aplikace** –zadejte **ID sady prostředků aplikace**, kterou chcete konfigurovat. Pomůžou vám **Referenční informace o ID sady prostředků pro integrované aplikace pro iOS** (v tomto článku).
   - **Název aplikace** –zadejte název aplikace, kterou chcete konfigurovat. V zařízení se tento název nezobrazuje a slouží ke snadnější identifikaci aplikace v seznamu.
   - **Vydavatel** –zadejte vydavatele aplikace, kterou chcete konfigurovat. V zařízení se tento název vydavatele nezobrazuje a slouží pouze ke snadnější identifikaci aplikace v seznamu.
   - **Oznámení** – povolte nebo zakažte aplikaci zasílání oznámení v zařízení. Pokud toto nastavení zakážete, zakážou se i následující nastavení.
     - **Zobrazit v Centru oznámení** – povolením tohoto nastavení umožníte, aby aplikace zobrazovala oznámení v Centru oznámení zařízení.
     - **Zobrazit na zamykací obrazovce** – povolením tohoto nastavení umožníte zobrazování oznámení z aplikace na zamykací obrazovce zařízení.
     - **Typ výstrahy** – vyberte požadovaný typ oznámení, když je zařízení odemčené, z těchto možností:
       - **Žádné** – nezobrazí se žádné oznámení.
       - **Informační zpráva** – krátce se zobrazí informační zpráva zobrazující oznámení.
       - **Modální** – zobrazí se oznámení a uživatel ho musí ručně zavřít, aby mohl pokračovat v používání zařízení.
     - **Odznáček na ikoně aplikace** – když toto nastavení povolíte, na ikonu aplikace se přidá odznáček udávající, že aplikace odeslala oznámení.
     - **Zvuky** – když toto nastavení povolíte, při doručení oznámení se přehraje zvuk.

5. Přidejte tolik aplikací, kolik potřebujete. Až přidávání aplikací dokončíte, vyberte **OK**.
6. Uložte profil pomocí **Vytvořit**.

## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Referenční informace o ID sady prostředků pro integrované aplikace pro iOS

Tento seznam zobrazuje ID sady prostředků některých běžných integrovaných aplikací pro iOS. Pokud chcete najít ID sady prostředků jiných aplikací, je nejvhodnější obrátit se na dodavatele softwaru.

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

Přiřaďte profil zařízení do vybraných skupin. Postup najdete v [Přiřazení profilů zařízení](device-profile-assign.md).