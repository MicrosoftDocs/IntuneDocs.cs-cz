---
title: "Registrace mobilních zařízení testování | Microsoft Intune"
description: "Registrace mobilních zařízení a instalace aplikace při registraci bezplatné 30denní zkušební verze Intune"
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 2424d52f800ae61dbadc0a3ae73c2b3f24d936c3


---

# Registrace mobilních zařízení testování a instalace aplikace
Abyste v Intune nastavili správu mobilních zařízení, musíte nejdřív nastavit autoritu pro správu mobilního zařízení, povolit správu pro platformu zařízení a zaregistrovat svoje zařízení v aplikaci Portál společnosti. Pak můžete nasadit aplikaci Microsoft Skype, kterou jste publikovali.

## Připravte službu na správu zařízení

1.  **Nastavení Intune jako autority pro správu mobilního zařízení**

    V [konzole pro správu Intune](https://manage.microsoft.com/) zvolte **Správce** &gt; **Správa mobilních zařízení**. Vyberte **Úlohy** > **Nastavit autoritu MDM** a potom vyberte **Ano** v dialogovém okně **Autorita MDM**.

2.  **Povolení MDM pro platformu zařízení**

    Povolte správu mobilních zařízení pro platformu zařízení, kterou chcete spravovat. V závislosti na platformě je potřeba splnit různé požadavky:

    -   **iOS a Mac OS X**: Další informace najdete v tématu [Nastavení správy pro iOS a Mac pomocí Microsoft Intune](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Android**: Mobilní zařízení s Androidem umožňují uživatelům registraci pomocí aplikace Portál společnosti dostupné na webu Google Play. Žádná další konfigurace v Intune se nevyžaduje.

    -   **Windows Phone**: Další informace najdete v tématu [Nastavení správy pro zařízení Windows Phone v Microsoft Intune](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune).

## Registrace testovacích zařízení

### iOS a Mac OS X
Nainstalujte si aplikaci **Portál společnosti služby Microsoft Intune** od Microsoft Corporation dostupnou na App Storu a přihlaste se pomocí uživatelských přihlašovacích údajů Intune přidaných nahoře. Abyste přidali svoje zařízení, zobrazte **Registrovaná zařízení** .

### Android
Nainstalujte si aplikaci **Portál společnosti Intune** od Microsoft Corporation dostupnou na [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) a přihlaste se pomocí uživatelských přihlašovacích údajů Intune přidaných nahoře.

### Windows Phone 8.1
Uživatelé si instalují aplikaci **Portál společnosti** od Microsoft Corporation dostupnou na Windows Phone Storu a přihlašují se pomocí uživatelských přihlašovacích údajů Intune přidaných nahoře.  Abyste přidali svoje zařízení, zobrazte **Registrovaná zařízení** .

 ### Windows Phone 8.0
 Uživatelé kliknou na **Nastavení systému** &gt; **Firemní aplikace** a přihlásí se pomocí uživatelských přihlašovacích údajů Intune přidaných výše. Aplikace Portál společnosti se nasadí na váš telefon.

Pokud se vám zobrazí výzva, abyste zadali **adresu serveru**, zadejte manage.microsoft.com.


## Instalace dříve nasazené aplikace
Na mobilním zařízení otevřete portál společnosti, zvolte **Aplikace** a pak nainstalujte **Microsoft Skype**.

Další informace o správě mobilních zařízení pomocí Intune najdete v tématu [Příprava registrace zařízení v Microsoft Intune](/Intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune).

### Další kroky
Gratulujeme! Právě jste dokončili krok 5 příručky pro *testování Microsoft Intune*.

>[!div class="step-by-step"]

>[&larr;**Vytváření zásad**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)     [**Možnosti a funkce** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)  



<!--HONumber=Jul16_HO3-->


