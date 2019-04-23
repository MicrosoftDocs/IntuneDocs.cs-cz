---
title: 'Rychlý start: Vytvoření skupiny pro správu uživatelů'
titleSuffix: Microsoft Intune
description: V tomto rychlém startu použijete Microsoft Intune k vytvoření skupiny ze stávajících uživatelů.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/25/2019
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7cbfe19e4f7aea28c16cae50c9b79336be81c8fa
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511394"
---
# <a name="quickstart-create-a-group-to-manage-users"></a>Rychlý start: Vytvoření skupiny pro správu uživatelů

V tomto rychlém startu použijete Intune k vytvoření skupiny ze stávajících uživatelů. Skupiny se používají ke správě uživatelů a řídí přístup zaměstnanců k firemním prostředkům. Tyto prostředky mohou být částí firemního intranetu nebo může jít o externí prostředky, jako jsou weby SharePointu, aplikace SaaS nebo webové aplikace.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

>[!NOTE]
>V Intune máte v konzole pohodlně k dispozici předem vytvořené skupiny **Všichni uživatelé** a **Všechna zařízení** s integrovanými optimalizacemi.

## <a name="prerequisites"></a>Požadavky

- K dokončení tohoto rychlého startu potřebujete [vytvořit uživatele](quickstart-create-user.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [portál Intune](https://aka.ms/intuneportal) jako [globální správce nebo správce služby Intune](users-add.md#types-of-administrators). Pokud jste vytvořili zkušební předplatné Intune, účet, z něhož jste toto předplatné vytvořili, je globálním správcem.

## <a name="create-a-group"></a>Vytvoření skupiny

Vytvoříte skupinu, kterou použijete později v tomto seriálu rychlých startů. Vytvoření skupiny:

1. Po otevření podokna **Microsoft Intune** vyberte **Skupiny** > **Nová skupina**.
2. V rozevíracím seznamu **Typ skupiny** vyberte **Zabezpečení**.
3. V **název skupiny** pole, zadejte název pro novou skupinu (například **testeři společnosti Contoso**).
4. Přidat **popis** pro skupinu.
5. **Typ členství** nastavte na **Přiřazeno**. 
6. Klikněte na tlačítko **členy** a vyberte jeden nebo více členů skupiny ze seznamu.

    ![Snímek obrazovky s vytvořením skupiny v Microsoft Intune](./media/quickstart-use-groups-01.png)

7. Klikněte na **Vybrat** > **Vytvořit**.

Po úspěšném vytvoření se skupina zobrazí v seznamu **Všechny skupiny**. 

## <a name="next-steps"></a>Další postup

V tomto rychlém startu jste použili Intune k vytvoření skupiny ze stávajících uživatelů. Další informace o přidávání skupin do Intune najdete v článku [Přidání skupin pro uspořádání uživatelů a zařízení](groups-add.md).

Pokud chcete postupovat podle této série rychlých startů Intune, pokračujte k dalšímu rychlému startu.

> [!div class="nextstepaction"]
> [Rychlý start: Nastavení automatické registrace pro zařízení s Windows 10](quickstart-setup-auto-enrollment.md)
