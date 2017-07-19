---
title: "Nastavení omezení registrace v Intune"
titleSuffix: Intune on Azure
description: "Omezení registrace podle platformy a nastavení limitu počtu zařízení pro registraci zařízení v Intune \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2dfcba8c788f262ce816dcd23dc2921fd57f331b
ms.sourcegitcommit: d1ad84edf4f03cb4c11fe55131556b43fc3a4500
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/05/2017
---
# <a name="set-enrollment-restrictions"></a>Nastavení omezení registrace

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako správce služby Intune můžete určit, která zařízení se mohou registrovat do systému správy pomocí Intune. Použijte portál Intune k nastavení následujících omezení pro registraci zařízení:

- Maximální počet zaregistrovaných zařízení
- Platformy zařízení, které se mohou zaregistrovat:
  - Android
  - iOS
  - macOS
  - Windows
- Omezení soukromých zařízení (pouze iOS a Android)

>[!NOTE]
>Omezení registrací nejsou funkcemi zabezpečení. Ohrožená zařízení mohou poskytovat zavádějící informace. Tato omezení jsou jen určitou bariérou pro uživatele bez zlých úmyslů.

## <a name="set-device-type-restrictions"></a>Nastavení omezení typů zařízení
Výchozí omezení registrace se vztahují na všechny uživatele, kteří nemají přiřazenou vyšší prioritu omezení registrace.  
1. Na portálu Intune zvolte **Registrace zařízení** a potom **Omezení registrace**.
![Snímek obrazovky pracovního prostoru Omezení zařízení s výchozími omezeními typu a počtu zařízení](media/device-restrictions-set-default.png)
2. V části **Omezení registrace** > **Omezení typů zařízení** vyberte **Výchozí**.
3. V části **Všichni uživatelé** vyberte **Platformy**. Zvolte u každé platformy **Povolit** nebo **Blokovat**:
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  Klikněte na **Uložit**.
4. V části **Všichni uživatelé** vyberte **Konfigurace platforem** a zvolte následující konfigurace:
  - **V osobním vlastnictví** – určete, zda **povolit** nebo **blokovat** zařízení s Androidem a iOSem.
  ![Snímek obrazovky pracovního prostoru Omezení zařízení s výchozími konfiguracemi platformy zařízení zobrazující konfiguraci nastavení pro osobní vlastnictví](media/device-restrictions-platform-configurations.png)
  Klikněte na **Uložit**.

>[!NOTE]
>Když zablokujete registraci zařízení s Androidem v osobním vlastnictví, zařízení s Androidem for Work půjde stále zaregistrovat.

## <a name="set-device-limit-restrictions"></a>Nastavení omezení limitů počtu zařízení
Výchozí omezení registrace se vztahují na všechny uživatele, kteří nemají přiřazenou vyšší prioritu omezení registrace.  
1. Na portálu Intune zvolte **Registrace zařízení** a potom **Omezení registrace**.
2. Zvolte **Omezení registrace** > **Omezení limitů počtů zařízení**.
3. V části **Všichni uživatelé** vyberte **Limit počtu zařízení**. Zadejte maximální počet zaregistrovaných zařízení na jednoho uživatele.  
![Snímek obrazovky okna Omezení limitů počtů zařízení s omezením limitu počtu zařízení](./media/device-restrictions-limit.png)

  Klikněte na **Uložit**.
