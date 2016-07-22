---
title: "Použití vzdáleného uzamčení a resetování hesla | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
translationtype: Human Translation
ms.sourcegitcommit: 6d9b79a09eef2546d78a19e061ba5cc3f24f645c
ms.openlocfilehash: 34379881b8299a2e3f9886b14b6d83e9dfe83373

---
# Chraňte svá zařízení pomocí vzdáleného zámku a resetování hesla
Microsoft Intune poskytuje možnosti pro vzdálený zámek i resetování hesla.

## Vzdálené zamknutí zařízení
Pokud uživatel zařízení ztratí, můžete ho vzdáleně zamknout. Následující tabulka uvádí, jak vzdálené uzamčení funguje na různých mobilních platformách.

|Platforma|Vzdálené uzamčení|
|------------|---------------|
|iOS|Podporováno|
|Android|Podporováno|
|Windows 10 Mobile|Podporováno|
|Windows Phone 8 a Windows Phone 8.1|Podporováno|
|Windows RT 8.1 a Windows RT|Podporované, pokud je aktuální uživatel zařízení stejný jako uživatel, který ho zaregistroval.|
|Windows 8.1|Podporované, pokud je aktuální uživatel zařízení stejný jako uživatel, který ho zaregistroval.|


### Vzdálené zamknutí mobilního zařízení pomocí konzoly Intune

1.  V [konzole správce Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna zařízení** &gt; **Všechna mobilní zařízení**.

2.  Zvolte **Všechna přímo spravovaná zařízení** (zobrazí se zařízení zaregistrovaná v Intune) nebo **Všechna zařízení spravovaná prostřednictvím protokolu Exchange ActiveSync**.

    > [!TIP]
    > Můžete taky přejít na zařízení podle uživatele. Vyberte **Všichni uživatelé**. Na stránce vlastností tohoto uživatele zvolte **Zařízení** a pak vyberte název mobilního zařízení, které chcete vymazat.

3.  V tomto seznamu vyberte zařízení, která chcete zamknout. Na hlavním panelu zvolte **Vzdálené úlohy** a vyberte **Vzdálené uzamčení**.

## Resetování hesla na zařízení
Pokud uživatel zapomene heslo, můžete mu pomoct odebráním hesla ze zařízení nebo vynucením nového dočasného hesla v zařízení. Následující tabulka uvádí, jak resetování hesla funguje na různých mobilních platformách.

|Platforma|Resetování hesla|
|------------|------------------|
|iOS|Je podporované vymazání hesla ze zařízení. Nevytvoří nové dočasné heslo.|
|Android|Je podporované a vytvoří se dočasné heslo.|
|Windows 10 Mobile|Podporováno|
|Windows Phone 8 a Windows Phone 8.1|Podporováno|
|Windows RT 8.1 a Windows RT|Není podporované|
|Windows 8.1|Není podporované|

### Resetování hesla:

1.  V [konzole správce Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna zařízení** &gt; **Všechna mobilní zařízení**.

2.  Zvolte **Všechna přímo spravovaná zařízení** (zobrazí se zařízení zaregistrovaná v Intune) nebo **Všechna zařízení spravovaná prostřednictvím protokolu Exchange ActiveSync**.

    > [!TIP]
    > Můžete taky přejít na zařízení podle uživatele. Klikněte na **Všichni uživatelé**. Na stránce vlastností tohoto uživatele klikněte na **Zařízení** a pak klikněte na název mobilního zařízení, které chcete vymazat.

3.  V tomto seznamu vyberte zařízení, která chcete zamknout. Na hlavním panelu zvolte **Vzdálené úlohy** a vyberte **Obnovení hesla**.


### Související témata
[Vyřazení zařízení](retire-devices-from-microsoft-intune-management.md)
[Selektivní vymazání ve Windows pro správu dat na zařízeních](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Jul16_HO3-->


