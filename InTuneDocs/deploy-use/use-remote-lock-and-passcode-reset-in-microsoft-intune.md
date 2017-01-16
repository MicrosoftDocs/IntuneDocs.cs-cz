---
title: "Vzdálené uzamčení a resetování hesla | Dokumentace Microsoftu"
description: "Intune poskytuje možnosti pro vzdálený zámek i resetování hesla."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 11/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ms.reviewer: chrisgre
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 641ca955c2790dc3029e8408d32a66b7b0418a12

---
# <a name="help-protect-your-devices-with-remote-lock-and-passcode-reset"></a>Chraňte svá zařízení pomocí vzdáleného zámku a resetování hesla
Microsoft Intune poskytuje možnosti pro vzdálený zámek i resetování hesla.

## <a name="lock-a-device-remotely"></a>Vzdálené zamknutí zařízení
Pokud uživatel ztratí zařízení, můžete ho vzdáleně zamknout. Následující tabulka uvádí, jak vzdálené uzamčení funguje na různých mobilních platformách.

|Platforma|Vzdálené uzamčení|
|------------|---------------|
|macOS|Není podporované|
|iOS|Podporováno|
|Android|Podporováno|
|Windows 10 a Windows 10 Mobile|Podporováno|
|Windows Phone 8 a Windows Phone 8.1|Podporováno|
|Windows RT 8.1 a Windows RT|Podporované, pokud je aktuální uživatel zařízení stejný jako uživatel, který ho zaregistroval.|
|Windows 8.1|Podporované, pokud je aktuální uživatel zařízení stejný jako uživatel, který ho zaregistroval.|

Vzdálené uzamčení není podporované u počítačů s Windows, které jsou registrované pomocí klientského softwaru Intune.

### <a name="lock-a-mobile-device-remotely-through-the-intune-console"></a>Vzdálené uzamčení mobilního zařízení prostřednictvím konzoly Intune

1.  V [konzole správce Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna zařízení** &gt; **Všechna mobilní zařízení**.

2.  Zvolte **Všechna přímo spravovaná zařízení** (zobrazí se zařízení zaregistrovaná v Intune) nebo **Všechna zařízení spravovaná prostřednictvím protokolu Exchange ActiveSync**.

    > [!TIP]
    > Můžete taky přejít na zařízení podle uživatele. Vyberte **Všichni uživatelé**. Na stránce vlastností daného uživatele zvolte **Zařízení** a vyberte název mobilního zařízení, které chcete zamknout.

3.  V tomto seznamu vyberte zařízení, která chcete zamknout. Na hlavním panelu zvolte **Vzdálené úlohy** a vyberte **Vzdálené uzamčení**.

## <a name="reset-the-passcode-on-a-device"></a>Resetování hesla na zařízení
Pokud uživatel zapomene heslo, můžete mu pomoct tím, že heslo ze zařízení odeberete nebo na zařízení vynutíte nové dočasné heslo. Následující tabulka uvádí, jak resetování hesla funguje na různých mobilních platformách.

|Platforma|Resetování hesla|
|------------|------------------|
|macOS|Není podporované|
|iOS|Je podporované vymazání hesla ze zařízení. Nevytvoří nové dočasné heslo.|
|Android|Podporováno ve verzích starších než Android 7.0. Vytvoří dočasné heslo.|
|Windows 10 Mobile|Podporováno|
|Windows Phone 8 a Windows Phone 8.1|Podporováno|
|Windows RT 8.1|Není podporované|
|Windows 8.1|Není podporované|
|Stolní počítač s Windows 10|Není podporované|

Resetování hesla není podporované u počítačů s Windows, které jsou registrované pomocí klientského softwaru Intune.

### <a name="reset-a-passcode"></a>Resetování hesla

1.  V [konzole správce Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna zařízení** &gt; **Všechna mobilní zařízení**.

2.  Zvolte **Všechna přímo spravovaná zařízení** (zobrazí se zařízení zaregistrovaná v Intune) nebo **Všechna zařízení spravovaná prostřednictvím protokolu Exchange ActiveSync**.

    > [!TIP]
    > Můžete taky přejít na zařízení podle uživatele. Klikněte na **Všichni uživatelé**. Na stránce vlastností tohoto uživatele klikněte na **Zařízení** a pak klikněte na název mobilního zařízení, které chcete vymazat.

3.  V tomto seznamu vyberte zařízení, která chcete zamknout. Na hlavním panelu zvolte **Vzdálené úlohy** a vyberte **Resetování hesla**.


### <a name="see-also"></a>Související témata
[Vyřazení zařízení](retire-devices-from-microsoft-intune-management.md) a [Selektivní vymazání ve Windows pro správu dat na zařízeních](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Dec16_HO2-->


