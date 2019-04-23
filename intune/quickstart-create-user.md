---
title: 'Rychlý start: Vytvoření uživatele v Intune'
description: 'Rychlý start: Vytvoření uživatele v Intune'
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 03/25/2019
ms.author: erikje
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: b49595493b5db3e5735e0a4717c27e91f058b8d8
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511351"
---
# <a name="quickstart-create-a-user-in-intune-and-assign-them-a-license"></a>Rychlý start: Vytvořte uživatele v Intune a přiřaďte mu licenci

V tomto rychlém startu vytvoříte uživatele a přiřadit je Intune. Při použití Intune, musí mít každou osobu, která mají mít přístup k firemním datům jejich vlastní uživatelský účet. Správce Intune můžete nakonfigurovat uživatele později ke správě řízení přístupu.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://aka.ms/intuneportal) jako [globální správce nebo správce služby Intune](users-add.md#types-of-administrators). Pokud jste vytvořili zkušební předplatné Intune, účet, z něhož jste toto předplatné vytvořili, je globálním správcem.

## <a name="create-a-user"></a>Vytvoření uživatele

Uživatelé musí mít uživatelský účet pro zápis do systému správy Intune zařízení. Chcete-li vytvořit nového uživatele:

1. V Intune zvolte **Uživatelé** > **Všichni uživatelé** > **Nový uživatel**.
![Prohlížeč](media/quickstart-create-user/create-user.png)
2. Do pole **Jméno** zadejte jméno, například *Dewey Kellum*.
3. Do pole **Uživatelské jméno** zadejte identifikátor uživatele, například Dewey@contoso.onmicrosoft.com.

    > [!NOTE]
    > Pokud jste nenakonfigurovali váš název domény zákazníků, použijte název ověřené domény, který jste použili k vytvoření předplatného Intune (nebo [bezplatnou zkušební verzi](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)). 

4. Zvolte **Zobrazit heslo** a poznamenejte si automaticky vygenerované heslo, abyste se mohli přihlásit k testovacímu zařízení.
5. Zvolte **Vytvořit**.

## <a name="assign-a-license-to-the-user"></a>Přiřazení licence uživateli

Po vytvoření uživatele, je nutné použít [centra pro správu služeb Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) přiřadit licenci pro Intune. Pokud uživatel není přiřadit licenci, budou moct zaregistrovat svá zařízení v Intune. 

Přiřazení licence Intune uživateli:

1. Přihlaste se k [centra pro správu služeb Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) pomocí stejných přihlašovacích údajů, které jste použili k přihlášení k Intune.
2. Zvolte **uživatelé** > **aktivní uživatelé** > a vyberte uživatele, který jste právě vytvořili.
3. Vedle možnosti **Licence na produkty** vyberte **Upravit**.
4. V části **Umístění** zvolte umístění pro daného uživatele.
5. Vedle licence na Intune (případně jiné licence, kterou máte a která zahrnuje Intune) klikněte na **Zapnuto**. Zobrazený [název produktu](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)** slouží jako plán služeb ve správě Azure. 

   > [!NOTE]
   > Toto nastavení použije pro tohoto uživatele jednu licenci. Pokud používáte zkušební prostředí, můžete tuto licenci později znovu přiřadit skutečnému uživateli v živém prostředí.
6. Zvolte **Uložit** > **Zavřít**.

U nového aktivního uživatele Intune se nyní zobrazí, že používá licenci **Intune**.

## <a name="clean-up-resources"></a>Vyčištění prostředků

Pokud tento uživatel víc nepotřebujete, můžete odstranit uživatele tak, že přejdete na [centra pro správu služeb Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) a zvolte **uživatelé** > **aktivní uživatelé**  >  *vyberte uživatele v seznamu* > **odstranění uživatele** > **odstranění uživatele** > **potvrzení změny** > **Zavřít**.

## <a name="next-steps"></a>Další postup

V tomto rychlém startu jste vytvořili uživatele a přiřazenou licenci Intune. Další informace o přidání uživatelů do Intune najdete v článku [Přidání uživatelů a udělení oprávnění pro správu v Intune](users-add.md).

Pokud chcete postupovat podle této série rychlých startů Intune, pokračujte k dalšímu rychlému startu.

> [!div class="nextstepaction"]
> [Rychlý start: Vytvoření skupiny pro správu uživatelů](quickstart-create-group.md)
