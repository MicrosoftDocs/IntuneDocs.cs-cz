---
title: "Nastavení omezení registrace v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Omezení registrace podle platformy a nastavení limitu počtu zařízení pro registraci zařízení v Intune "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d99f7ca5b5e96a7ab113a14d36f0fef474411836
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017

---

# <a name="set-enrollment-restrictions"></a>Nastavení omezení registrace 

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Můžete nastavit typy a maximální počet zařízení, jejichž registraci chcete povolit. V okně Omezení registrace můžete nastavit:

- Platformy, které mají mít povolenou registraci, a to, jestli chcete blokovat registraci zařízení s Androidem a iOSem v osobním vlastnictví

- Maximální počet zařízení, která může uživatel zaregistrovat

## <a name="set-device-type-restrictions"></a>Nastavení omezení typů zařízení

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování a správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Omezení registrace**.

3. V části **Omezení typů zařízení** vyberte **Výchozí**.

4. V okně **Všichni uživatelé** vyberte **Platformy**.

5. U platforem, kterým chcete povolit možnost registrace v Intune, vyberte **Povolit**. U platforem, u nichž chcete možnost registrace zablokovat, vyberte **Blokovat**. Platformy mají standardně nastavenou možnost **Povolit**. 

    >[!NOTE]
    >Tato nastavení neplatí pro registrace zařízení s Windows používající softwarového klienta Intune. Mají vliv jenom na registrace používající správu mobilních zařízení. 

6. Vyberte **Uložit**.

7. Vyberte **Konfigurace platforem**.

8. Zvolte, jestli chcete **Povolit** nebo **Blokovat** registraci zařízení s Androidem a iOSem v osobním vlastnictví.

9. Vyberte **Uložit**.

## <a name="set-device-limit-restrictions"></a>Nastavení omezení limitů počtu zařízení

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování a správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Omezení registrace**.

3. V části **Omezení limitů počtu zařízení** vyberte **Výchozí**.

4. V okně **Všichni uživatelé** vyberte **Limit počtu zařízení**.

5. Vyberte maximální počet zařízení, která uživatel může zaregistrovat, a potom vyberte **Uložit**.

