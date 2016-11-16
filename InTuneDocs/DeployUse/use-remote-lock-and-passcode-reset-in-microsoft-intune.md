---
title: "Resetování vzdáleného uzamčení a hesla | Microsoft Intune"
description: "Intune poskytuje možnosti pro vzdálený zámek i resetování hesla."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ms.reviewer: chrisgre
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: b32ef59aa33205e5687d951d50dfd605a6b071f2

---
# Chraňte svá zařízení pomocí vzdáleného zámku a resetování hesla
Microsoft Intune poskytuje možnosti pro vzdálený zámek i resetování hesla.

## Vzdálené zamknutí zařízení
Pokud uživatel ztratí zařízení, můžete ho vzdáleně zamknout. Následující tabulka uvádí, jak vzdálené uzamčení funguje na různých mobilních platformách.

|Platforma|Vzdálené uzamčení|
|------------|---------------|
|iOS|Podporováno|
|Android|Podporováno|
|Windows 10 a Windows 10 Mobile|Podporováno|
|Windows Phone 8 a Windows Phone 8.1|Podporováno|
|Windows RT 8.1 a Windows RT|Podporované, pokud je aktuální uživatel zařízení stejný jako uživatel, který ho zaregistroval.|
|Windows 8.1|Podporované, pokud je aktuální uživatel zařízení stejný jako uživatel, který ho zaregistroval.|

Vzdálené uzamčení není podporované u počítačů s Windows, které jsou registrované pomocí klientského softwaru Intune.

### Vzdálené uzamčení mobilního zařízení prostřednictvím konzoly Intune

1.  V [konzole správce Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna zařízení** &gt; **Všechna mobilní zařízení**.

2.  Zvolte **Všechna přímo spravovaná zařízení** (zobrazí se zařízení zaregistrovaná v Intune) nebo **Všechna zařízení spravovaná prostřednictvím protokolu Exchange ActiveSync**.

    > [!TIP]
    > Můžete taky přejít na zařízení podle uživatele. Vyberte **Všichni uživatelé**. Na stránce vlastností daného uživatele zvolte **Zařízení** a vyberte název mobilního zařízení, které chcete zamknout.

3.  V tomto seznamu vyberte zařízení, která chcete zamknout. Na hlavním panelu zvolte **Vzdálené úlohy** a vyberte **Vzdálené uzamčení**.

## Resetování hesla na zařízení
Pokud uživatel zapomene heslo, můžete mu pomoct tím, že heslo ze zařízení odeberete nebo na zařízení vynutíte nové dočasné heslo. Následující tabulka uvádí, jak resetování hesla funguje na různých mobilních platformách.

|Platforma|Resetování hesla|
|------------|------------------|
|iOS|Je podporované vymazání hesla ze zařízení. Nevytvoří nové dočasné heslo.|
|Android|Podporováno. Vytvoří dočasné heslo.|
|Windows 10 Mobile|Podporováno|
|Windows Phone 8 a Windows Phone 8.1|Podporováno|
|Windows RT 8.1 a Windows RT|Není podporované|
|Windows 8.1|Není podporované|

Resetování hesla není podporované u počítačů s Windows, které jsou registrované pomocí klientského softwaru Intune.

### Resetování hesla

1.  V [konzole správce Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna zařízení** &gt; **Všechna mobilní zařízení**.

2.  Zvolte **Všechna přímo spravovaná zařízení** (zobrazí se zařízení zaregistrovaná v Intune) nebo **Všechna zařízení spravovaná prostřednictvím protokolu Exchange ActiveSync**.

    > [!TIP]
    > Můžete taky přejít na zařízení podle uživatele. Klikněte na **Všichni uživatelé**. Na stránce vlastností tohoto uživatele klikněte na **Zařízení** a pak klikněte na název mobilního zařízení, které chcete vymazat.

3.  V tomto seznamu vyberte zařízení, která chcete zamknout. Na hlavním panelu zvolte **Vzdálené úlohy** a vyberte **Resetování hesla**.


### Související témata
[Vyřazení zařízení](retire-devices-from-microsoft-intune-management.md) a [Selektivní vymazání ve Windows pro správu dat na zařízeních](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Oct16_HO4-->


