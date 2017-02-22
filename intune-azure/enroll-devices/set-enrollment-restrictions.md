---
title: "Nastavení omezení registrace v Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Omezení registrace podle platformy a nastavení limitu počtu zařízení pro registraci zařízení v Intune "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 1bdefce35c20ce24b94ee701a2d13b5408f435ce

---

# <a name="set-enrollment-restrictions"></a>Nastavení omezení registrace 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Můžete zadat povolené platformy a omezit tak typy zařízení, která se mohou zaregistrovat v Intune. Také můžete nastavit maximální počet zařízení, která uživatel může zaregistrovat.

## <a name="set-device-type-restrictions"></a>Nastavení omezení typů zařízení

1. Na portálu Azure Portal zvolte **Další služby**, do textového pole zadejte **Intune** a potom zvolte **Jiné** > **Intune**

2. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Omezení registrace**.

3. V části **Omezení typů zařízení** vyberte **Výchozí**.

4. V okně **Všichni uživatelé** vyberte **Platformy**.

5. U platforem, kterým chcete povolit možnost registrace v Intune, vyberte **Povolit**. U platforem, u nichž chcete možnost registrace zablokovat, vyberte **Blokovat**.

6. Vyberte **Uložit**.

7. Vyberte **Konfigurace platforem**.

8. Zvolte, zda chcete u soukromých zařízení s iOSem možnost registrace povolit nebo zablokovat.

9. Vyberte **Uložit**.

## <a name="set-device-limit-restrictions"></a>Nastavení omezení limitů počtu zařízení

1. V okně Intune na portálu Azure Portal zvolte **Registrovat zařízení** a potom zvolte **Omezení registrace**.

2. V části **Omezení limitů počtu zařízení** vyberte **Výchozí**.

3. V okně **Všichni uživatelé** vyberte **Limit počtu zařízení**.

4. Vyberte maximální počet zařízení, která uživatel může zaregistrovat, a potom vyberte **Uložit**.



<!--HONumber=Feb17_HO1-->


