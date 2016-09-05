---
title: "Postup nasazení aplikací | Microsoft Intune"
description: "Informace v tomto tématu vám pomůžou nasadit aplikace pomocí Microsoft Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0c6f795031ec23ffe6f332b3510eea43d5fbdbcd
ms.openlocfilehash: 4c9f5b111fbd95f9e1c928cfaaa0c7ebf61dad2a

---
# Nasazení aplikací v Microsoft Intune

Informace v tomto tématu vám pomůžou nasadit aplikace pomocí Microsoft Intune.


## Nasazení aplikace
V tomto postupu nasadíte aplikaci pro vybrané skupiny zařízení nebo uživatelů.

### Postup nasazení aplikace

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) klikněte na **Aplikace** &gt; **Aplikace**. Zobrazí se seznam spravovaných aplikací.

2.  Vyberte aplikaci, kterou chcete nasadit, a potom klikněte na **Spravovat nasazení**.

3.  V dialogovém okně *&lt;název aplikace&gt;* na stránce **Vybrat skupiny** vyberte skupiny uživatelů nebo zařízení, kterým chcete aplikaci nasadit.

4.  Na stránce **Akce nasazení** nakonfigurujte toto nastavení:

    - **Schválení** – Zvolte, jestli je nasazení:
        - **Požadované** (povinná instalace)
        - **K dispozici** (uživatelé můžou instalovat aplikaci na vyžádání z portálu společnosti)
        - **Nelze použít** (aplikace není nainstalovaná nebo se na portálu společnosti nezobrazuje)
        - **Odinstalovat** (aplikace je z cílových zařízení odinstalovaná)
    - **Termín** – U povinných instalací vyberte, dokdy se má aplikace nasadit. Můžete si vybrat z předem definovaných hodnot nebo vybrat **Vlastní** a nakonfigurovat vlastní termín.

5. Pokud nasazujete aplikaci, která se dá nakonfigurovat pomocí zásad správy mobilní aplikace, zobrazí se stránka **Správa mobilních aplikací**. Na této stránce zvolte zásady správy mobilních aplikací, které chcete přidružit k této aplikaci.

    [Podívejte se, které aplikace Microsoftu jsou kompatibilní se zásadami správy mobilních aplikací.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. Pokud je aplikace, kterou nasazujete, kompatibilní s profily sítě VPN služby Intune, zobrazí se stránka **Profil VPN**. Na této stránce můžete nastavit přidružení aplikací pro iOS k profilu VPN, který jste nasadili. Připojení VPN se automaticky otevře při spuštění aplikace. Pokud chcete zpřístupnit profil VPN, musí mít povolené nastavení profilu **VPN pro aplikaci**.
 Informace o postupu při konfiguraci profilů VPN, včetně informací o přidružení profilů k aplikacím, najdete v tématu [Připojení VPN v Microsoft Intune](vpn-connections-in-microsoft-intune.md).

## Příklad

V tomto příkladu jste nasadili aplikace jako **K dispozici** do zařízení s iOS.
Aplikace se v zařízeních uživatelů zobrazí na portálu společnosti a uživatelé ji odtud můžou nainstalovat.

Například na tomto snímku obrazovky byla aplikace Bing for iOS nasazená pomocí typu instalace **Externí odkaz** s vlastní ikonou. Byla vybraná možnost **Zobrazit jako doporučenou aplikaci a upozornit na ni na portálu společnosti**.  
![Dostupná aplikace pro iOS](./media/available-install-on-iOS.png)

Pokud je aplikace nasazená jako **Požadovaná**, dostane uživatel oznámení, že je aplikace připravená k instalaci. Například na tomto snímku obrazovky je aplikace Work Folders for iOS nasazená pomocí typu instalace **Spravované aplikace pro iOS z App Storu**.
![Požadovaná aplikace pro iOS](./media/iOS-Required-install.PNG)

## Další kroky

Po nasazení aplikace můžete monitorovat její postup. Další informace najdete v tématu [Monitorování aplikací v Microsoft Intune](monitor-apps-in-microsoft-intune.md).



<!--HONumber=Jul16_HO5-->


