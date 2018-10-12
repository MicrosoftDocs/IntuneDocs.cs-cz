---
title: 'Rychlý start: Vytvoření skupiny pro správu uživatelů'
titlesuffix: Microsoft Intune
description: V tomto rychlém startu použijete Microsoft Intune k vytvoření skupiny ze stávajících uživatelů.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3a4468f2e6919349095d934790740afc8c347282
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581584"
---
# <a name="quickstart-create-a-group-to-manage-users"></a>Rychlý start: Vytvoření skupiny pro správu uživatelů

V tomto rychlém startu použijete Intune k vytvoření skupiny ze stávajících uživatelů. Skupiny se používají ke správě uživatelů a řídí přístup zaměstnanců k firemním prostředkům. Tyto prostředky mohou být částí firemního intranetu nebo může jít o externí prostředky, jako jsou weby SharePointu, aplikace SaaS nebo webové aplikace.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

>[!NOTE]
>V Intune máte v konzole pohodlně k dispozici předem vytvořené skupiny **Všichni uživatelé** a **Všechna zařízení** s integrovanými optimalizacemi.

## <a name="prerequisites"></a>Požadavky

- K dokončení tohoto rychlého startu potřebujete [vytvořit uživatele](quickstart-create-user.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo jako správce služby Intune. Intune najdete na webu Azure Portal, když zvolíte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.

## <a name="create-a-group"></a>Vytvoření skupiny
1. Po otevření podokna **Microsoft Intune** vyberte **Skupiny** > **Nová skupina**.
2. V podokně **Skupina** vyberte **Typ skupiny** > **Zabezpečení**.
3. V poli **Název** nastavte „Contoso Testers“ a přidejte **popis** skupiny.
4. **Typ členství** nastavte na **Přiřazené**. 
5. Klikněte na **Členové** a ze seznamu vyberte skupinu **Členové**.

    ![Snímek obrazovky s vytvořením skupiny v Microsoft Intune](./media/quickstart-use-groups-01.png)

6. Klikněte na **Vybrat**.
7. Klikněte na **Vytvořit**.

Pokud se vám podařilo skupinu vytvořit, zobrazí se v seznamu **Všechny skupiny**. 

## <a name="next-steps"></a>Další kroky

V tomto rychlém startu jste použili Intune k vytvoření skupiny ze stávajících uživatelů.

> [!div class="nextstepaction"]
> [Vytvoření zásad dodržování předpisů pro zařízení](quickstart-create-policy.md)
