---
title: "Nastavení omezení registrace v Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Omezení registrace podle platformy a nastavení limitu počtů zařízení pro registraci zařízení v Intune "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: c4fa22fad4df9c0e4699cf258eb9518a1534bb94

---

# <a name="set-enrollment-restrictions"></a>Nastavení omezení registrace 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Můžete nastavit typy a maximální počet zařízení, jejichž registraci chcete povolit. V okně Omezení registrace můžete nastavit:

- Platformy, které mají mít povolenou registraci, a to, jestli chcete blokovat registraci zařízení s Androidem a iOSem v osobním vlastnictví

- Maximální počet zařízení, která může uživatel zaregistrovat

## <a name="set-device-type-restrictions"></a>Nastavení omezení typů zařízení

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování a správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Omezení registrace**.

3. V části **Omezení typů zařízení** vyberte **Výchozí**.

4. V okně **Všichni uživatelé** vyberte **Platformy**.

5. U platforem, kterým chcete povolit možnost registrace v Intune, vyberte **Povolit**. U platforem, pro které chcete možnost registrace zablokovat, vyberte **Blokovat**. Platformy mají standardně nastavenou možnost **Povolit**. 

    >[!NOTE]
    >Tato nastavení neplatí pro registrace zařízení s Windows používající softwarového klienta Intune. Mají vliv jenom na registrace používající správu mobilních zařízení. 

6. Vyberte **Uložit**.

7. Vyberte **Konfigurace platforem**.

8. Zvolte, jestli chcete **Povolit** nebo **Blokovat** registraci zařízení s Androidem a iOSem v osobním vlastnictví.

9. Vyberte **Uložit**.

## <a name="set-device-limit-restrictions"></a>Nastavení omezení limitů počtů zařízení

1. Na portálu Azure Portal zvolte **Další služby** > **Monitorování a správa** > **Intune**.

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Omezení registrace**.

3. V části **Omezení limitů počtů zařízení** vyberte **Výchozí**.

4. V okně **Všichni uživatelé** vyberte **Limit počtu zařízení**.

5. Vyberte maximální počet zařízení, která může uživatel zaregistrovat, a potom vyberte **Uložit**.



<!--HONumber=Feb17_HO3-->


