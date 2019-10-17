---
title: 'Rychlý start: Vytvoření uživatele v Intune'
description: 'Rychlý start: Vytvoření uživatele v Intune'
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 03/25/2019
ms.author: erikje
ms.manager: dougeby
ms.assetid: 820fcb18-0927-4ebd-be79-dce92b51c261
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 75a875fc3ff11eb1e3befad425c16a710544f781
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509881"
---
# <a name="quickstart-create-a-user-in-intune-and-assign-them-a-license"></a>Rychlý Start: vytvoření uživatele v Intune a přiřazení licence

V tomto rychlém startu vytvoříte uživatele a pak jim přiřadíte licenci Intune. Při používání Intune musí mít všichni uživatelé, kteří mají přístup k firemním datům, svůj vlastní uživatelský účet. Správci Intune můžou nakonfigurovat uživatele později, aby mohli spravovat řízení přístupu.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://aka.ms/intuneportal) jako [globální správce nebo správce služby Intune](users-add.md#types-of-administrators). Pokud jste vytvořili zkušební předplatné Intune, účet, se kterým jste předplatné vytvořili, je globální správce.

## <a name="create-a-user"></a>Vytvoření uživatele

Uživatelé musí mít uživatelský účet k registraci do správy zařízení v Intune. Vytvoření nového uživatele:

1. V Intune zvolte **Uživatelé** > **Všichni uživatelé** > **Nový uživatel**.
![Prohlížeč](./media/quickstart-create-user/create-user.png)
2. Do pole **Jméno** zadejte jméno, například *Dewey Kellum*.
3. Do pole **Uživatelské jméno** zadejte identifikátor uživatele, například Dewey@contoso.onmicrosoft.com.

    > [!NOTE]
    > Pokud jste nenakonfigurovali název domény zákazníka, použijte ověřený název domény, který jste použili k vytvoření předplatného Intune (nebo [bezplatné zkušební verze](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)). 

4. Zvolte **Zobrazit heslo** a poznamenejte si automaticky vygenerované heslo, abyste se mohli přihlásit k testovacímu zařízení.
5. Zvolte **Vytvořit**.

## <a name="assign-a-license-to-the-user"></a>Přiřazení licence uživateli

Po vytvoření uživatele musíte použít [Centrum pro správu Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) k přiřazení licence Intune. Pokud uživateli nepřiřazujete licenci, nebude se moct zaregistrovat do Intune. 

Přiřazení licence Intune uživateli:

1. Přihlaste se k [centru pro správu Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) pomocí stejných přihlašovacích údajů, které jste použili pro přihlášení k Intune.
2. Vyberte možnost **uživatelé** > **aktivní uživatelé** > a vyberte uživatele, kterého jste právě vytvořili.
3. Vedle možnosti **Licence na produkty** vyberte **Upravit**.
4. V části **Umístění** zvolte umístění pro daného uživatele.
5. Klikněte **na** vedle licence Intune (nebo jiné licence, kterou máte v Intune). Zobrazený [název produktu](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)** slouží jako plán služeb ve správě Azure. 

   > [!NOTE]
   > Toto nastavení použije pro tohoto uživatele jednu licenci. Pokud používáte zkušební prostředí, můžete tuto licenci později znovu přiřadit skutečnému uživateli v živém prostředí.
6. Zvolte **Uložit** > **Zavřít**.

Nový aktivní uživatel Intune teď zobrazí, že používá licenci **Intune** .

## <a name="clean-up-resources"></a>Vyčištění prostředků

Pokud tento uživatel již nepotřebujete, můžete uživatele odstranit tak, že přejdete do [centra pro správu Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) a zvolíte možnost **Uživatelé** > **aktivní uživatelé** > *Vyberte uživatele v seznamu* > **Odstranit uživatele** > . **Odstranit uživatele**@no__t – 10**potvrzení změn**2**Zavřít**.

## <a name="next-steps"></a>Další kroky

V tomto rychlém startu jste vytvořili uživatele a přiřadili mu licenci Intune. Další informace o přidání uživatelů do Intune najdete v článku [Přidání uživatelů a udělení oprávnění pro správu v Intune](users-add.md).

Pokud chcete postupovat podle této série rychlých startů Intune, pokračujte k dalšímu rychlému startu.

> [!div class="nextstepaction"]
> [Rychlý start: Vytvoření skupiny pro správu uživatelů](../quickstart-create-group.md)
