---
title: "Použití zásad konfigurace aplikací v Intune pro Android for Work"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak lze pomocí zásad konfigurace aplikací předávat konfigurační data do aplikace pro Android for Work při jejím spuštění."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f9ea697cafa0f277c176e55443250d32ca378dbb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-android-for-work"></a>Použití zásad konfigurace aplikací v Microsoft Intune pro Android for Work

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zásady konfigurace aplikací v Microsoft Intune slouží k poskytování nastavení, která mohou být k dispozici, když uživatel spustí aplikaci pro Android for Work. Ne všechny aplikace ale konfiguraci aplikací podporují. Zeptejte se vývojáře, jestli vaše aplikace zásady konfigurace aplikací podporuje.

Zásady konfigurace aplikací vám umožňují předem nakonfigurovat dostupná nastavení aplikace, ještě než ji uživatel spustí. Některé aplikace pro Android podporují možnosti spravované konfigurace, které můžete nastavit pomocí [návrháře konfigurace](#use-configuration-designer) v konzole Intune. Jiná nastavení konfigurace aplikací (například ta, která využívají typy sad) ale v návrháři zadávat nelze.  Pro tyto hodnoty je potřeba použít [editor JSON](#use-json-editor).   Nastavení se aplikaci poskytne automaticky při její instalaci.

Tyto zásady nepřiřazujte přímo uživatelům a zařízením. Místo toho přidružíte zásadu k aplikaci a pak přiřadíte tuto aplikaci. Nastavení zásad se použije, když je aplikace zkontroluje (obvykle při prvním spuštění).

## <a name="use-configuration-designer"></a>Použití návrháře konfigurace

1. Na portálu Intune vyberte **Mobilní aplikace**. V části **Spravovat** vyberte **Zásady konfigurace aplikací** a potom klikněte na **Přidat**.
2. Zadejte tyto podrobnosti:
    - **Název**: Název profilu, který se zobrazí v konzole Intune
    - **Popis**: Popis profilu, který se zobrazí v konzole Intune
    - **Platforma**: Vyberte **Android**.
    - **Typ registrace zařízení**: možnost **Zaregistrováno přes Intune** je předem vybraná.
3. Kliknutím na **Přidružená aplikace** přejděte na výběr aplikace, pro kterou chcete definovat zásadu konfigurace.  Ze seznamu vyberte některou z aplikací pro Android for Work, které jste schválili a synchronizovali s Intune.
4. Klikněte na **Nastavení konfigurace**.
5. U položky **Formát nastavení konfigurace** zvolte možnost **Použít návrháře konfigurace**.
6. Zvolte **Přidat**. Zobrazí se seznam dostupných nastavení konfigurace. Obsahuje tyto možnosti:
    - **Konfigurační klíče**: Název nastavení
    - **Typ hodnoty**: Nastavení, které lze nakonfigurovat, například **Logická hodnota** nebo **Řetězec**
    - **Popis**: Popis nastavení konfigurace
7. Zaškrtněte políčka u nastavení, která chcete u tohoto profilu nakonfigurovat, a klikněte na **OK**.
8. V seznamu vybraných nastavení se zobrazí dostupné **hodnoty konfigurace**. U každého z nastavení určete hodnotu a klikněte na **OK**.

## <a name="use-json-editor"></a>Použití editoru JSON

1. Na portálu Intune vyberte **Mobilní aplikace**. V části **Spravovat** vyberte **Zásady konfigurace aplikací** a potom klikněte na **Přidat**.
2. Zadejte tyto podrobnosti:
    - **Název**: Název profilu, který se zobrazí v konzole Intune
    - **Popis**: Popis profilu, který se zobrazí v konzole Intune
    - **Platforma**: Vyberte **Android**.
    - **Typ registrace zařízení**: možnost **Zaregistrováno přes Intune** je předem vybraná.
3. Kliknutím na **Přidružená aplikace** přejděte na výběr aplikace, pro kterou chcete definovat zásadu konfigurace.  Ze seznamu vyberte některou z aplikací pro Android for Work, které jste schválili a synchronizovali s Intune.
5. Vyberte **Nastavení konfigurace**.
6. U položky **Formát nastavení konfigurace** zvolte možnost pro **otevření editoru JSON**.
7. V editoru můžete definovat hodnoty JSON pro nastavení konfigurace. Výběrem možnosti **Stáhnout šablonu JSON** stáhnete vzorový soubor, který můžete následně nakonfigurovat.
8. Po dokončení vyberte **OK** a potom klikněte na **Přidat**.

Zásady se vytvoří a zobrazí se v okně se seznamem zásad.

Potom pokračujte s [přiřazením](apps-deploy.md) a [sledováním](apps-monitor.md) aplikace jako obvykle.

Spuštěná aplikace přiřazená zařízení se spustí s nastavením, které jste nakonfigurovali v zásadách konfigurace aplikací.

## <a name="preconfigure-permissions-grant-state-for-apps"></a>Konfigurace stavu udělení oprávnění aplikacím

Předem nakonfigurovat můžete také oprávnění aplikací k přístupu k funkcím zařízení s Androidem. Aplikace pro Android, které vyžadují oprávnění zařízení, jako je například přístup k umístění nebo fotoaparátu zařízení, ve výchozím nastavení vyzvou uživatele, aby oprávnění přijali nebo odmítli. Pokud například aplikace používá mikrofon zařízení, potom bude koncový uživatel vyzván, aby aplikaci udělil oprávnění používat mikrofon.

1. Na portálu Intune vyberte **Mobilní aplikace**. V části **Spravovat** vyberte **Zásady konfigurace aplikací** a potom klikněte na **Přidat**.
2. Zadejte tyto podrobnosti:
    - **Název**: Název profilu, který se zobrazí v konzole Intune
    - **Popis**: Popis profilu, který se zobrazí v konzole Intune
    - **Platforma**: Vyberte **Android**.
    - **Typ registrace zařízení**: možnost **Zaregistrováno přes Intune** je předem vybraná.
3. Kliknutím na **Přidružená aplikace** přejděte na výběr aplikace, pro kterou chcete definovat zásadu konfigurace.  Ze seznamu vyberte některou z aplikací pro Android for Work, které jste schválili a synchronizovali s Intune.
5. Klikněte na **Oprávnění** a potom na **Přidat**.
6. Ze seznamu vyberte příslušné oprávnění aplikace a klikněte na **OK**.
7. U každého oprávnění vyberte způsob, jakým se bude v rámci této zásady udělovat:
    - **Zeptat se**: Vyzve uživatele ke schválení nebo zamítnutí.
    - **Automaticky udělit**: Automaticky schválí bez upozornění uživatele.
    - **Automaticky odepřít**: Automaticky zamítne bez upozornění uživatele.
8. Přiřaďte zásadu konfigurace aplikace výběrem příslušné zásady, kliknutím na **Přiřazení** a potom na **Vybrat skupiny**.
9. Zvolte požadovanou skupinu uživatelů a potom klikněte na **Vybrat**.
10. Kliknutím na **Uložit** zásadu přiřaďte.
