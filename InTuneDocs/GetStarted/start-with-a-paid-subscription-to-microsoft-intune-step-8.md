---
title: "Nastavení registrace zařízení | Microsoft Intune"
description: "Nastavte autoritu MDM a povolte registraci pro zařízení s iOS, Windows, Androidem a MacOS."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 149f3a3310907d131affeaad4bd372aa60be9206
ms.openlocfilehash: ca6e016927da1de6604b0c6a2924702ec90c9fab


---

# <a name="enroll-mobile-devices-and-install-an-app"></a>Registrace mobilních zařízení a instalace aplikace
Pokud chcete nastavit správu mobilních zařízení v Intune, je potřeba nejdříve nastavit *autoritu správy mobilních zařízení*, která identifikuje službu schopnou správy zařízení spojených s vaším účtem. V těchto pokynech se předpokládá, že budete místo System Center Configuration Manageru používat službu Intune. Po nastavení autority MDM můžete povolit správu platforem zařízení a zaregistrovat svá zařízení v aplikaci Portál společnosti.

## <a name="enable-device-enrollment"></a>Povolení registrace zařízení

1. **Nastavení Intune jako autority pro správu mobilního zařízení**
    V [konzole pro správu Intune](https://manage.microsoft.com/) zvolte **Správa** > **Správa mobilních zařízení** a v části **Úkoly** zvolte **Nastavit autoritu MDM**.  

2. V dialogovém okně Autorita MDM vyberte **Ano**.

    ![Konzola správce Nastavení MDM na Intune](./media/mdmAuthority.png)

## <a name="choose-how-to-enroll-devices"></a>Výběr způsobu registrace zařízení

Intune může spravovat zařízení různými způsoby podle požadavků vaší společnosti. Mezi pár dostupných příkladů registrace patří princip Uživatelé s vlastním zařízením (BYOD), zařízení vlastněná společností, dále princip Zvolte si své zařízení (CYOD) a zařízení s beznabídkovým režimem.

Podle následujícího postupu [si zvolte způsob registrace zařízení](choose-how-to-enroll-devices1.md).

## <a name="enable-mdm-for-your-device-platform"></a>Povolení MDM pro platformu zařízení
Pro zařízení s iOS, MacOS a Androidem for Work musí být povolena registrace k vytvoření vztahu mezi poskytovatelem platformy a tenantem Intune. Zařízení s Windows a Androidem nevyžadují žádné další kroky, ale pro zařízení s Windows můžete uživatelům zjednodušit registraci tak, že vytvoříte speciální položku registru DNS.

Povolte registraci zařízení pro platformu zařízení, kterou chcete spravovat. V závislosti na platformě je potřeba splnit různé požadavky:

-  [iOS a macOS](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune.md)
-  [Počítač s Windows](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)
-  [Windows 10 Mobile a Windows Phone](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work)

Po povolení registrace si uživatelé můžou stáhnout aplikaci Portál společnosti do svého zařízení a dokončit proces registrace zařízení.

### <a name="enable-company-owned-device-enrollment"></a>Povolení registrace zařízení vlastněných společností
Můžete také povolit řadu scénářů [registrace zařízení vlastněných společností](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices) včetně následujících:
- [Apple Device Enrollment Program](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Registrace Průvodce nastavení s Apple Configuratorem](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Registrace Průvodce nastavení s Apple Configuratorem](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [Správce registrace zařízení](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a>Další kroky
Gratulujeme! Právě jste dokončili poslední krok *úvodní příručky Intune* Teď, když je počáteční konfigurace dokončená, můžete zvážit povolení dalších funkcí MDM.

>[!div class="step-by-step"]

>[&larr; **Registrace zařízení**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Úlohy po konfiguraci** &rarr;](.\post-configuration-tasks.md)  



<!--HONumber=Nov16_HO4-->


