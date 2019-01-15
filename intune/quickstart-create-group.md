---
title: 'Rychlý start: Vytvoření skupiny pro správu uživatelů'
titlesuffix: Microsoft Intune
description: V tomto rychlém startu použijete Microsoft Intune k vytvoření skupiny ze stávajících uživatelů.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/11/2019
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6f7d7ccb4c94300d00f02dcace5c3a089cd9f2a2
ms.sourcegitcommit: d54a12a836503f7e8b90346f16b7ad2d83b710dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/14/2019
ms.locfileid: "54270567"
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

Vytvoříte skupinu, kterou použijete později v tomto seriálu rychlých startů.

1. Po otevření podokna **Microsoft Intune** vyberte **Skupiny** > **Nová skupina**.
2. V rozevíracím seznamu **Typ skupiny** vyberte **Zabezpečení**.
3. V poli **Název** nastavte „Contoso Testers“ a přidejte **popis** skupiny.
4. **Typ členství** nastavte na **Přiřazeno**. 
5. Klikněte na **Členové** a ze seznamu vyberte pro skupinu alespoň jednoho člena.

    ![Snímek obrazovky s vytvořením skupiny v Microsoft Intune](./media/quickstart-use-groups-01.png)

6. Klikněte na **Vybrat** > **Vytvořit**.

Po úspěšném vytvoření se skupina zobrazí v seznamu **Všechny skupiny**. 

## <a name="next-steps"></a>Další postup

V tomto rychlém startu jste použili Intune k vytvoření skupiny ze stávajících uživatelů. Další informace o přidávání skupin do Intune najdete v článku [Přidání skupin pro uspořádání uživatelů a zařízení](groups-add.md).

Pokud chcete postupovat podle této série rychlých startů Intune, pokračujte k dalšímu rychlému startu.

> [!div class="nextstepaction"]
> [Rychlý start: Nastavení automatické registrace pro zařízení s Windows 10](quickstart-setup-auto-enrollment.md)
