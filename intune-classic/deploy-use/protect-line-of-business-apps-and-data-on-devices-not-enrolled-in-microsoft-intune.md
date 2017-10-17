---
title: "Ochrana obchodních aplikací na neregistrovaných zařízeních"
description: "Toto téma popisuje, jak můžete připravit své vlastní obchodní aplikace, abyste u nich mohli použít zásady správy mobilních aplikací, které můžou pomoci zabránit úniku informací."
keywords: 
author: mattbriggs
ms.author: mabriggs
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 447e019dde4781183323f29a35ed569926973351
ms.sourcegitcommit: f3b8fb8c47fd2c9941ebbe2c047b7d0a093e5a83
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/11/2017
---
# <a name="protect-line-of-business-apps-and-data-on-devices-that-are-not-enrolled-in-microsoft-intune"></a>Ochrana obchodních aplikací a dat na zařízeních, která nejsou zaregistrovaná v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Zásady správy mobilních aplikací (MAM) pomáhají chránit data společnosti tím, že omezují akce, které by mohly způsobit únik těchto dat, a vynucují požadavky pro přístup k datům, jako je například PIN aplikace. Pokud chcete zásady MAM použít u obchodních aplikací pro iOS nebo Android, musíte aplikace nejdřív zabalit pomocí nástroje Microsoft Intune App Wrapping. Proces zabalení aplikace je proces přiřazení vrstvy správy k mobilní aplikaci, aniž by bylo nutné v ní provádět změny, a její distribuce uživatelům.  

Toto téma vysvětluje kroky nutné k použití zásad MAM u aplikací, ke kterým zaměstnanci přistupují na **svých vlastních zařízeních, která nejsou spravovaná**, a na zařízeních, která jsou spravovaná pomocí **řešení správy mobilních zařízení (MDM) třetí strany**.  Příprava obchodních aplikací, které běží na **zařízeních zaregistrovaných v MDM Intune**, je popsaná v tématu [Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune](/intune/apps-prepare-mobile-application-management).


##  <a name="step-1-prepare-the-app"></a>Krok 1: Příprava aplikace

Před použitím zásad MAM u aplikace musíte aplikaci nejdřív zabalit pomocí nástroje Microsoft Intune App Wrapping pro [iOS](/intune/app-wrapper-prepare-ios) nebo [Android](/intune/app-wrapper-prepare-android) nebo ručně integrovat funkce Intune pro ochranu aplikací pomocí [sady Intune App SDK](/intune/app-sdk).

Další informace o použití nástroje App Wrapping nebo sady Intune App SDK najdete v tématu [Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune](/intune/apps-prepare-mobile-application-management).

## <a name="step-2-add-the-app"></a>Krok 2: Přidání aplikace

Pokud chcete ke svým obchodním aplikacím přidružit zásady MAM, musíte do předplatného nebo tenanta Intune přidat informace o aplikaci pomocí následujících kroků:

1. Na [portálu Azure Portal](https://portal.azure.com/) přejděte na **Správa mobilních aplikací Intune** > **Nastavení** a zvolte **Obchodní aplikace**.

  ![Snímek obrazovky s oknem Nastavení a možností Obchodní aplikace](../media/mam-azure-portal-lob-on-settings.png)

2. V okně **Obchodní aplikace** zvolte **Přidat vlastní aplikaci**.

  ![Snímek obrazovky s oknem obchodních aplikací, které v horní části obsahuje tlačítko Přidat vlastní aplikaci](../media/mam-azure-portal-add-lob-app-action.png)
3.  Zadejte název aplikace, identifikátor sady (do pole Identifikátor aplikace) a platformu (iOS nebo Android).

  ![Snímek obrazovky s oknem Přidat vlastní aplikaci](../media/mam-azure-portal-add-app-details.png)

  Tento krok vám pomůže vytvořit jedinečný popis aplikace. Aplikace se také zobrazí v seznamu Cílové aplikace pro zásady MAM vašeho tenanta, jak popisuje následující krok.

## <a name="step-3-apply-mam-policies"></a>Krok 3: Použití zásad MAM
Jakmile se metadata aplikace odešlou do služby, aplikace se zobrazí v seznamu aplikací. Nyní můžete [vytvořit novou zásadu nebo využít existující zásadu](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) a použít ji pro obchodní aplikaci, kterou jste přidali v kroku 2.

>[!IMPORTANT]
>Zásady MAM je potřeba cílit na uživatele, kteří budou zabalenou aplikaci používat.  Uživatelé, kteří tuto zásadu nemají nasazenou, nebudou moct aplikaci používat.


  ![Snímek obrazovky s oknem Cílové aplikace a zobrazenou novou obchodní aplikací](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## <a name="step-4-distribute-the-app"></a>Krok 4: Distribuce aplikace
Aplikace můžete uživatelům nasadit následujícími způsoby:
* U zařízení zaregistrovaných v řešení MDM třetí strany můžete k distribuci aplikací využít své řešení MDM.
* Pro zařízení, která nejsou spravována žádným řešením MDM, budete potřebovat vlastní řešení. Uživatelé si musí aplikaci stáhnout a nainstalovat do svého zařízení.

## <a name="change-the-metadata"></a>Změna metadat
Pokud potřebujete změnit podrobnosti o aplikaci, jako je třeba název aplikace nebo identifikátor sady, musíte [aplikaci odebrat](#remove-apps) a [přidat ji](#step-2-add-the-app) s novými metadaty.

##  <a name="remove-apps"></a>Odebrání aplikací
Obchodní aplikaci můžete ze seznamu aplikací odebrat. Tato akce odebere aplikaci ze seznamu a odebere přidružení se zásadami MAM, ale nezpůsobí odebrání nebo odinstalaci aplikace ze zařízení uživatele.  

1.  Na [portálu Azure Portal](https://portal.azure.com/) přejděte na **Správa mobilních aplikací Intune** > **Nastavení**. V okně **Nastavení** zvolte **Obchodní**. Otevře se seznam stávajících aplikací.  
2.  Zvolte aplikaci, kterou chcete odebrat, a zvolte **kontextovou nabídku (…)**.

  ![Snímek obrazovky s oknem obchodních aplikací se třemi tečkami](../media/mam-azure-portal-lob-context-menu.png)
3.  Pokud chcete aplikaci odstranit, zvolte **Odstranit aplikaci**.

  ![Snímek obrazovky s oknem obchodních aplikací s možností pro odstranění aplikace](../media/mam-azure-portal-delete-app.png)

  Tato akce odebere aplikaci ze seznamu obchodních aplikací a ze seznamu cílových aplikací v zásadách MAM.
