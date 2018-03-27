---
title: Jak nasadit aplikace
description: Informace v tomto tématu vám pomůžou nasadit aplikace pomocí Microsoft Intune.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ed098a22da1def82c90fbb159d54be9b1a369ba8
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="deploy-apps-in-microsoft-intune"></a>Nasazení aplikací v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Informace v tomto tématu vám pomůžou nasadit aplikace pomocí Microsoft Intune.


## <a name="deploy-an-app"></a>Nasazení aplikace
V tomto postupu nasadíte aplikaci pro vybrané skupiny zařízení nebo uživatelů.

### <a name="to-deploy-an-app"></a>Postup nasazení aplikace

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

    [Podívejte se, které aplikace Microsoftu jsou kompatibilní se zásadami správy mobilních aplikací.](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx)

6. Pokud je aplikace, kterou nasazujete, kompatibilní s profily sítě VPN služby Intune, zobrazí se stránka **Profil VPN**. Na této stránce můžete nastavit přidružení aplikací pro iOS k profilu VPN, který jste nasadili. Připojení VPN se automaticky otevře při spuštění aplikace. Pokud chcete zpřístupnit profil VPN, musí mít povolené nastavení profilu **VPN pro aplikaci**.
 Informace o postupu při konfiguraci profilů VPN, včetně informací o přidružení profilů k aplikacím, najdete v tématu [Připojení VPN v Microsoft Intune](vpn-connections-in-microsoft-intune.md).

<!---
>[!TIP]
>If an end user previously installed an iOS app and you now deploy it with a deployment action of **Available**, Intune will automatically begin to manage that app with no further action required by you, or the end-user.
--->

## <a name="example"></a>Příklad

V tomto příkladu jste nasadili aplikace jako **K dispozici** do zařízení s iOSem.
Aplikace se v zařízeních uživatelů zobrazí na portálu společnosti a uživatelé ji odtud můžou nainstalovat.

Například na tomto snímku obrazovky byla aplikace Bing for iOS nasazená pomocí typu instalace **Externí odkaz** s vlastní ikonou. Byla vybraná možnost **Zobrazit jako doporučenou aplikaci a upozornit na ni na portálu společnosti**.  
![Dostupná aplikace pro iOS](./media/available-install-on-iOS.png)

Pokud je aplikace nasazená jako **Požadovaná**, dostane uživatel oznámení, že je aplikace připravená k instalaci. Například na tomto snímku obrazovky je aplikace Work Folders for iOS nasazená pomocí typu instalace **Spravované aplikace pro iOS z App Storu**.  
![Požadovaná aplikace pro iOS](./media/iOS-Required-install.PNG)

## <a name="next-steps"></a>Další kroky

Po nasazení aplikace můžete monitorovat její postup. Další informace najdete v tématu [Monitorování aplikací v Microsoft Intune](monitor-apps-in-microsoft-intune.md).
