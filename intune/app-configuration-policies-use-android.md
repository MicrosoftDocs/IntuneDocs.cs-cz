---
title: "Přidání zásad konfigurace aplikací pro spravovaná zařízení s Androidem | Dokumentace Microsoftu"
titlesuffix: Azure portal
description: "Přečtěte si, jak lze pomocí zásad konfigurace aplikací předávat konfigurační data do aplikace pro Android for Work při jejím spuštění."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4fbf1466b02da66e5c7d115d60aa43912322ebeb
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Přidání zásad konfigurace aplikací pro spravovaná zařízení s Androidem

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zásady konfigurace aplikací v Microsoft Intune slouží k poskytování nastavení, když uživatelé spustí aplikaci pro Android for Work. Tyto zásady nepřiřazujte přímo uživatelům a zařízením. Místo toho přidružíte zásadu k aplikaci a pak přiřadíte tuto aplikaci. Nastavení zásad se použijí, když je aplikace zjistí (obvykle při prvním spuštění).

> [!Note]  
> Některé aplikace konfiguraci aplikací nepodporují. Zeptejte se vývojáře, jestli vaše aplikace zásady konfigurace aplikací podporuje.

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** + **Intune**.
3. Zvolte úlohu **Mobilní aplikace**.
4. Ve skupině **Spravovat** zvolte **Zásady konfigurace aplikací** a pak **Přidat**.
5. Zadejte tyto podrobnosti:
    - **Název**  
      Název profilu, který se zobrazí na portálu Azure Portal
    - **Popis**  
      Popis profilu, který se zobrazí na portálu Azure Portal
    - **Typ registrace zařízení**  
      Zvolte **Spravovaná zařízení**.
6. V poli **Platforma** vyberte **Android**.
7. Kliknutím na **Přidružená aplikace** přejděte na výběr aplikace, pro kterou chcete definovat zásady konfigurace aplikací. Ze seznamu vyberte některou z aplikací pro Android for Work, které jste schválili a synchronizovali s Intune.
8. Klikněte na **Nastavení konfigurace**. K nastavení konfigurace můžete použít:
    - [Návrhář konfigurace](#Use-the-configuration-designer)
    - [Editor JSON](#Enter-the-JSON-editor)
9. Zvolte **OK** a pak **Přidat**.

## <a name="use-the-configuration-designer"></a>Použití návrháře konfigurace

Návrháře konfigurace můžete použít u aplikací jak v zařízeních, která jsou zaregistrovaná v Intune, tak i v zařízeních, která zaregistrovaná nejsou. Návrhář umožňuje nakonfigurovat konkrétní klíče a hodnoty konfigurace. Pro každou hodnotu musíte také zadat datový typ.

Pro každý klíč a hodnotu v konfiguraci nastavte:

  - **Konfigurační klíč**  
     Klíč, který jedinečně identifikuje konkrétní konfiguraci nastavení
  - **Typ hodnoty**  
    Datový typ konfigurační hodnoty. Mezi typy patří integer, real, string a boolean.
  - **Hodnota konfigurace**  
    Hodnota konfigurace 

## <a name="enter-the-json-editor"></a>Použití editoru JSON

Jiná nastavení konfigurace aplikací (například ta, která využívají typy sad) ale v návrháři zadávat nelze. Pro tyto hodnoty je potřeba použít editor JSON. Nastavení se aplikaci poskytne automaticky při její instalaci.

1. U položky **Formát nastavení konfigurace** zvolte možnost pro **otevření editoru JSON**.
2. V editoru můžete definovat hodnoty JSON pro nastavení konfigurace. Výběrem možnosti **Stáhnout šablonu JSON** stáhnete vzorový soubor, který můžete následně nakonfigurovat.
3. Zvolte **OK** a pak **Přidat**.

Zásady se vytvoří a zobrazí se v okně se seznamem zásad.

Když se přiřazená aplikace na zařízení spustí, použijí se nastavení, která jste nakonfigurovali v zásadách konfigurace aplikací.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Konfigurace stavu udělení oprávnění aplikacím

Předem nakonfigurovat můžete také oprávnění aplikací k přístupu k funkcím zařízení s Androidem. Aplikace pro Android, které vyžadují oprávnění zařízení, jako je například přístup k umístění nebo fotoaparátu zařízení, ve výchozím nastavení vyzvou uživatele, aby oprávnění přijali nebo odmítli. Pokud například aplikace používá mikrofon zařízení, zobrazí se uživateli výzva, aby aplikaci udělil oprávnění používat mikrofon.

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** + **Intune**.
3. Zvolte **Mobilní aplikace**. V části **Spravovat** zvolte **Zásady konfigurace aplikací** a pak **Přidat**.
4. Zadejte tyto podrobnosti:
    - **Název:** Název profilu, který se zobrazí na portálu Azure Portal
    - **Popis:** Popis profilu, který se zobrazí na portálu Azure Portal
    - **Platforma**: Vyberte **Android**.
    - **Typ registrace zařízení**: Možnost **Spravovaná zařízení** je předem vybraná.
5. Kliknutím na **Přidružená aplikace** přejděte na výběr aplikace, pro kterou chcete definovat zásadu konfigurace. Ze seznamu vyberte některou z aplikací pro Android for Work, které jste schválili a synchronizovali s Intune.
6. Klikněte na **Oprávnění** a potom na **Přidat**.
7. Ze seznamu vyberte příslušné oprávnění aplikace a klikněte na **OK**.
8. U každého oprávnění vyberte způsob, jakým se bude v rámci této zásady udělovat:
    - **Zeptat se**: Vyzval uživatele ke schválení nebo zamítnutí
    - **Automaticky udělit**: Automaticky schválí bez upozornění uživatele.
    - **Automaticky odepřít**: Automaticky zamítne bez upozornění uživatele.
9. Přiřaďte zásadu konfigurace aplikace výběrem příslušné zásady, kliknutím na **Přiřazení** a potom na **Vybrat skupiny**.
10. Zvolte požadovanou skupinu uživatelů a potom klikněte na **Vybrat**.
11. Kliknutím na **Uložit** zásadu přiřaďte.

## <a name="next-steps"></a>Další kroky

Pokračujte s [přiřazením](apps-deploy.md) a [sledováním](apps-monitor.md) aplikace.

