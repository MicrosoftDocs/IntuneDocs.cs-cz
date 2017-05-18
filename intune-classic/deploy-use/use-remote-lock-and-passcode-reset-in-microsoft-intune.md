---
title: "Vzdálené uzamčení a resetování hesla | Dokumentace Microsoftu"
description: "Intune poskytuje možnosti pro vzdálený zámek i resetování hesla."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ms.reviewer: chrisgre
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f0a477c9eb1ed0580314e79135e377809eaab197
ms.openlocfilehash: 9b0ae19b211373548061e2c2979620739a0bf0a0
ms.lasthandoff: 04/17/2017

---
# <a name="help-protect-your-devices-with-remote-lock-and-passcode-reset"></a>Chraňte svá zařízení pomocí vzdáleného zámku a resetování hesla

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune poskytuje možnosti pro vzdálený zámek i resetování hesla.

## <a name="lock-a-device-remotely"></a>Vzdálené zamknutí zařízení
Pokud uživatel ztratí zařízení, můžete ho vzdáleně zamknout. Než budete moct zařízení vzdáleně uzamknout, musíte u něj nastavit PIN kód nebo heslo.

Následující tabulka uvádí, jak vzdálené uzamčení funguje na různých mobilních platformách.

|Platforma|Vzdálené uzamčení|
|------------|---------------|
|macOS|Není podporované|
|iOS|Podporováno|
|Android|Podporováno|
|Android for Work|Podporováno|
|Windows 10 (Mobile)|Podporováno|
|Windows 10 (Desktop)|Není podporované|
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
|Android for Work|Není podporované|
|Windows 10 Mobile|Podporováno pro verzi Windows 10 Creator a novější mobilní zařízení, která jsou připojená k Azure AD.|
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
