---
# required metadata

title: Nasazení aplikací | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---
# Nasazení aplikací v Microsoft Intune

Informace v tomto tématu vám pomůžou nasadit aplikace Microsoft Intune.


## Nasazení aplikace
V tomto postupu aplikaci nasadíte na vybraná zařízení nebo vybraným uživatelům.

### Postup nasazení aplikace

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) klikněte na **Aplikace** &gt; **Aplikace**. Zobrazí se seznam spravovaných aplikací.

2.  Vyberte aplikaci, kterou chcete nasadit, a potom klikněte na **Spravovat nasazení**.

3.  V dialogu *&lt;název aplikace&gt;* nejdřív na stránce **Vybrat skupiny** vyberte skupiny uživatelů nebo zařízení, pro které chcete aplikaci nasadit.

4.  Na stránce **Akce nasazení** nakonfigurujte toto nastavení:

    - **Schválení** – Zvolte, jestli je nasazení:
        - **Požadované** (povinná instalace)
        - **K dispozici** (uživatelé můžou instalovat aplikaci na vyžádání z portálu společnosti)
        - **Nelze použít** (aplikace není nainstalovaná nebo se na portálu společnosti nezobrazuje)
        - **Odinstalovat** (aplikace bude z cílových zařízení odinstalovaná)
    - **Termín** – U povinných instalací vyberte, do jaké doby se má aplikace nasadit. Můžete si vybrat z předem definovaných hodnot nebo vybrat **Vlastní** a nakonfigurovat vlastní termín.

5. Pokud nasazujete aplikaci, která se dá nakonfigurovat pomocí zásad správy mobilní aplikace, zobrazí se stránka **Správa mobilních aplikací**. Na této stránce zvolte zásady správy mobilní aplikace, které chcete přidružit k této aplikaci.

    [Podívejte se, které aplikace Microsoftu jsou kompatibilní se zásadami správy mobilních aplikací.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. Pokud je aplikace, kterou nasazujete, kompatibilní s profily sítě VPN služby Intune, zobrazí se stránka **Profil VPN**. Na této stránce můžete nastavit přidružení iOS aplikací k profilu sítě VPN, který jste nasadili. Připojení VPN se automaticky otevře při spuštění aplikace. Pokud chcete zpřístupnit profil VPN, musí mít povolené nastavení profilu **VPN pro aplikaci**.
 Informace o tom, jak nakonfigurovat profily sítě VPN, včetně podpory pro přidružení profilů k aplikacím, najdete v tématu [Pomoc uživatelům připojit se k práci pomocí profilů VPN v Microsoft Intune](vpn-connections-in-microsoft-intune.md).

## Příklad

V tomto příkladu jste nasadili aplikace jako **K dispozici** do zařízení s iOS.
Aplikace se zobrazí na portálu společnosti v zařízeních uživatelů, ze kterých můžou aplikaci nainstalovat. Například na tomto snímku obrazovky je aplikace Bing for iOS nasazená pomocí typu instalace **Externí odkaz**, s vlastní ikonou a vybranou možností **Zobrazit tuto aplikaci jako doporučenou aplikaci a zvýraznit ji na portálu společnosti**.
    ![Dostupná aplikace pro iOS](./media/available-install-on-iOS.png)

Pokud je aplikace nasazená jako **Požadovaná**, dostane uživatel oznámení, že je aplikace připravená k instalaci. Například na tomto snímku obrazovky je aplikace Work Folders for iOS nasazená pomocí typu instalace **Spravované aplikace pro iOS z App Storu**.
    ![Požadovaná aplikace pro iOS](./media/iOS-Required-install.PNG)

## Další kroky

Po nasazení aplikace můžete monitorovat její postup. Další informace najdete v tématu [Monitorování aplikací v Microsoft Intune](monitor-apps-in-microsoft-intune.md).


<!--HONumber=Jun16_HO2-->


