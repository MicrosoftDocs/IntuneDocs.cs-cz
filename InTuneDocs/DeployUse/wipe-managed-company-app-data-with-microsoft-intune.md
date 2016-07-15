---
title: "Vymazání dat spravovaných aplikací společnosti s Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ded7bd6c971a9448ad6e6492ebc5e42dfcb5d76e
ms.openlocfilehash: ebc83611679f5128df45e4ca6b2f3b745f47061d


---

# Vymazání data spravovaných aplikací společnosti s Microsoft Intune
V případě ztráty nebo odcizení zařízení nebo když zaměstnanec opouští společnost, je vhodné se ujistit, že byla ze zařízení odebraná firemní data. Nemusí ale být vhodné odebrat ze zařízení osobní data, zejména pokud se jedná o zařízení vlastněné zaměstnancem.

Pokud chcete provést selektivní vymazání dat aplikací společnosti, vytvořte žádost o vymazání pomocí kroků popsaných v části **Vytvoření žádosti o vymazání** v tomto tématu.  Po dokončení žádosti se při příštím spuštění aplikace na zařízení z aplikace odeberou data společnosti.
>[!NOTE]
> Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou. Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. To se v současné době vztahuje jenom na aplikaci Microsoft Outlook.



## Vytvoření žádosti o vymazání

1.  V okně **Správa mobilních aplikací Intune** vyberte dlaždici **Žádosti o vymazání**.

    ![Snímek obrazovky okna Správa mobilních aplikací Intune s dlaždicí souhrnu](../media/AppManagement/AzurePortal_MAM_WipeRequests.png)

2.  Vyberte **Nová žádost o vymazání**.

    ![Snímek obrazovky okna Nová žádost o vymazání](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

3.  V okně **Nová žádost o vymazání** výběrem možnosti **Uživatel** otevřete okno **Uživatel** a potom vyberte uživatele, jehož data aplikací chcete vymazat.

4.  Vyberte **Zařízení**.  Otevře se okno **Zařízení** , ve kterém jsou uvedena všechny zařízení přidružená k vybranému uživateli.  Vyberte zařízení, které chcete vymazat.

5.  Teď jste zpátky v okně **Nová žádost o vymazání**. Pokud chcete vytvořit žádost o vymazání, vyberte **OK**. Služba vytvoří a sleduje samostatnou žádost o vymazání pro každou chráněnou aplikaci na zařízení.


![Snímek obrazovky dlaždice Žádosti o vymazání ](../media/AppManagement/AzurePortal_MAM_WipeRequestsSummary.png)

## Monitorování žádostí o vymazání
Okno **Správa mobilních aplikací Intune** obsahuje souhrnnou sestavu o dlaždici **Žádost o vymazání** .  Zobrazí celkový stav a zahrnuje počet nevyřízených žádostí a selhání. Další podrobnosti získáte po provedení níže popsaných kroků:

1.  V okně **Správa mobilních aplikací Intune** výběrem dlaždice **Žádost o vymazání** otevřete okno **Žádost o vymazání**.

2.  V okně **Žádost o vymazání** můžete zobrazit seznam žádostí seskupených podle uživatele.  Protože systém vytvoří žádost o vymazání pro každou chráněnou aplikaci spuštěnou na zařízení, může být u uživatele více žádostí.  Stav označuje, zda je žádost **nevyřízená**, **selhala**nebo byla **úspěšná**.

### Viz taky
[Ochrana aplikačních dat pomocí zásad správy mobilních aplikací ](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Použití portálu Azure](azure-portal-for-microsoft-intune-mam-policies.md)



<!--HONumber=Jun16_HO4-->


