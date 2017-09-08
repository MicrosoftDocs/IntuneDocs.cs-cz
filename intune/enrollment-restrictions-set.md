---
title: "Nastavení omezení registrace v Intune"
titleSuffix: Intune on Azure
description: "Omezení registrace podle platformy a nastavení limitu počtu zařízení pro registraci zařízení v Intune \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 47dc35e5b50670027a85f395f674345b934d377b
ms.sourcegitcommit: 7674efb7de5ad54390801165364f5d9c58ccaf84
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2017
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
- Verze operačního systému platformy (pouze iOS a Android)
  - Minimální verze
  - Maximální verze
- Omezení soukromých zařízení (pouze iOS, Android a macOS)

>[!NOTE]
>Omezení registrací nepatří k funkcím zabezpečení. Ohrožená zařízení mohou poskytovat zavádějící informace. Tato omezení jsou jen určitou bariérou pro uživatele bez zlých úmyslů.

## <a name="set-device-type-restrictions"></a>Nastavení omezení typů zařízení
Výchozí omezení registrace se použijí pro všechny registrace zařízení s uživateli i bez uživatelů.
1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. Zvolte **Registrace zařízení** > **Omezení registrace**.
4. V části **Omezení registrace** > **Omezení typů zařízení** vyberte **Výchozí**.
5. V části **Všichni uživatelé** vyberte **Platformy**. Zvolte u každé platformy **Povolit** nebo **Blokovat**:
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  Klikněte na **Uložit**.
6. V části **Všichni uživatelé** vyberte **Konfigurace platforem** a zvolte následující konfigurace. Pro každou z povolených platforem můžete nakonfigurovat následující možnosti:
  - **Verze** – Určete **minimální** a **maximální** verzi operačního systému platformy pro zařízení s Androidem a iOSem. Verze operačního systému se nevztahují na zařízení registrovaná v Programu registrace zařízení, pomocí Apple School Manageru ani v aplikaci Apple Configurator.
  - **V osobním vlastnictví** – Určete, jestli se mají **povolit**, nebo **blokovat** zařízení s Androidem, iOSem a macOS.
  ![Snímek obrazovky pracovního prostoru Omezení zařízení s výchozími konfiguracemi platformy zařízení zobrazující konfiguraci nastavení pro osobní vlastnictví](media/device-restrictions-platform-configurations.png)
  Klikněte na **Uložit**.

>[!NOTE]
>Když zablokujete registraci zařízení s Androidem v osobním vlastnictví, stále půjde zaregistrovat zařízení v osobním vlastnictví, která používají verzi Android for Work.

## <a name="set-device-limit-restrictions"></a>Nastavení omezení limitů počtu zařízení
Výchozí omezení registrace se použijí pro všechny uživatele.
1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. Zvolte **Registrace zařízení** > **Omezení registrace**.
4. Na portálu Intune zvolte **Registrace zařízení** a potom **Omezení registrace**.
5. Zvolte **Omezení registrace** > **Omezení limitů počtů zařízení**.
6. V části **Všichni uživatelé** vyberte **Limit počtu zařízení**. Zadejte maximální počet zaregistrovaných zařízení na jednoho uživatele.  
![Snímek obrazovky okna Omezení limitů počtů zařízení s omezením limitu počtu zařízení](./media/device-restrictions-limit.png)

  Klikněte na **Uložit**.
