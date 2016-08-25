---
# required metadata

title: Registrace mobilních zařízení a instalace aplikace | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrace mobilních zařízení a instalace aplikace
Abyste v Intune nastavili správu mobilních zařízení, musíte nejdřív nastavit autoritu pro správu mobilního zařízení, povolit správu pro platformu zařízení a zaregistrovat svoje zařízení v aplikaci portálu společnosti. Pak můžete nasadit aplikaci Microsoft Skype, kterou jste publikovali v kroku 6.

## Povolení správy zařízení a jejich registrace

1.  **Nastavení Intune jako autority pro správu mobilního zařízení**
    Spusťte průvodce [konzola pro správu Intune](https://manage.microsoft.com/)tak, že klikněte na **Správa** > **Správa mobilních zařízení** a potom vyberte **Nastavit autoritu MDM** v nabídce **Úlohy**.  V dialogovém okně Autorita MDM vyberte **Ano**.
    ![Konzola správce Nastavení MDM na Intune](./media/mdmAuthority.png)

2.  **Povolení MDM pro platformu zařízení**
    Povolte správu mobilních zařízení pro platformu zařízení, kterou chcete spravovat. V závislosti na platformě je potřeba splnit různé požadavky:

    -   **iOS a Mac OS X**: Viz [Nastavení správy pro iOS a Mac pomocí Microsoft Intune](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Windows Phone**: Viz [Nastavení správy pro zařízení Windows Phone v Microsoft Intune](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

    -   **Android**: Mobilní zařízení s Androidem umožňují uživatelům registraci pomocí aplikace Portál společnosti dostupné na webu [Google Play](https://play.google.com/store/apps/details?id=com.skype.raider). Žádná další konfigurace v Intune se nevyžaduje.

3.  **Registrovat zařízení**:

    -   **Android** – Nainstalujte si aplikaci **Portál společnosti Intune** od Microsoft Corporation dostupnou na [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) a přihlaste se pomocí uživatelských přihlašovacích údajů Intune přidaných nahoře.

    -   **iOS a Mac OS X** – Nainstalujte si aplikaci **Portál společnosti Microsoft Intune** od společnosti Microsoft Corporation, která je dostupná v App Storu, a pak použijte přihlašovací údaje uživatele Intune přidané v předchozím kroku. Abyste přidali svoje zařízení, zobrazte **Registrovaná zařízení** .

    -   **Windows Phone 8.1** – Uživatelé si instalují aplikaci **Portál společnosti** od Microsoft Corporation dostupnou na Windows Phone Storu a přihlašují se pomocí uživatelských přihlašovacích údajů Intune přidaných nahoře.  Abyste přidali svoje zařízení, zobrazte **Registrovaná zařízení** .

    -   **Windows Phone 8.0 ** – Uživatelé vyberou **Nastavení systému** &gt; **Firemní aplikace** a přihlásí se pomocí uživatelských přihlašovacích údajů Intune přidaných výše. Aplikace portálu společnosti se nasadí na váš telefon.

    Pokud se vám zobrazí výzva, abyste zadali **adresu serveru**, zadejte manage.microsoft.com.

## Instalace aplikace na registrované zařízení
V [kroku 6](start-with-a-paid-subscription-to-microsoft-intune-step-6.md) této úvodní příručky jste publikovali aplikaci Skype do vlastní uživatelské skupiny Intune. Teď nainstalujete aplikaci na nově registrovaná zařízení.

Na registrovaném mobilním zařízení otevřete portál společnosti, zvolte **Aplikace**a pak nainstalujte **Microsoft Skype**..

Další informace o správě mobilních zařízení pomocí [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] najdete v tématu [Příprava registrace zařízení v Microsoft Intune](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune).


### Další kroky
Gratulujeme! Právě jste dokončili poslední krok *úvodní příručky Intune* Teď, když je počáteční konfigurace dokončená, můžete zvážit povolení dalších funkcí MDM.

>[!div class="step-by-step"]

>[&larr; **Registrace zařízení**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Úlohy po konfiguraci** &rarr;](.\post-configuration-tasks.md)  


<!--HONumber=May16_HO1-->


