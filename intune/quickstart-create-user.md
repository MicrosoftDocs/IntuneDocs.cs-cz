---
title: 'Rychlý start: Vytvoření uživatele v Intune'
description: 'Rychlý start: Vytvoření uživatele v Intune'
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 6a1d591e635dccd99551d9b8d40e099724a85d77
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581588"
---
# <a name="quickstart-create-a-user-and-assign-a-license-to-it"></a>Rychlý start: Vytvoření uživatele a přiřazení licence tomuto uživateli

V tomto rychlém startu vytvoříte uživatele a pak mu přiřadíte licenci. Při používání Intune musí mít uživatelský účet každý uživatel, který má mít přístup k firemním datům. Správci Intune pak můžou tyto uživatele nakonfigurovat a spravovat řízení přístupu.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo správce služby Intune.

## <a name="create-a-user"></a>Umožňuje vytvořit uživatele.

Aby se uživatelé mohli zaregistrovat do správy zařízení Intune, musí mít uživatelský účet.

1. V Intune zvolte **Uživatelé** > **Všichni uživatelé** > **Nový uživatel**.
![Prohlížeč](media/quickstart-create-user/create-user.png)
2. Do pole **Jméno** zadejte *Dewey Kellum*.
3. Do pole **Uživatelské jméno** zadejte *Dewey@contoso.onmicrosoft.com*.
4. Zvolte **Skupiny** > **Všichni** > **Vybrat**.
5. Zvolte **Zobrazit heslo** a poznamenejte si automaticky vygenerované heslo, abyste se mohli přihlásit k testovacímu zařízení.
6. Zvolte **Vytvořit**.

## <a name="assign-a-license-to-the-user"></a>Přiřazení licence uživateli

Po vytvoření uživatele musíte použít [portál Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), abyste na něm danému uživateli přiřadili licenci Intune. Bez přiřazení licence si uživatelé nemůžou svoje zařízení zaregistrovat do Intune. 

1. Přihlaste se k [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854). K přihlášení použijte stejné přihlašovací údaje jako pro Intune.
2. Zvolte **Uživatelé** > **Aktivní uživatelé** > vyberte uživatele, kterého jste právě vytvořili.
3. V části **Umístění** zvolte umístění pro daného uživatele.
3. Zvolte **Licence na produkty** a nastavte **Enterprise Mobility + Security E3** (nebo jinou vaši licenci, která zahrnuje Intune) na **Zapnuto**.
   > [!NOTE]
   > Tím pro uživatele použijete jednu licenci. Pokud používáte živé prostředí, můžete používání této licence později vypnout, abyste ji mohli přiřadit skutečnému uživateli.
5. Zvolte **Uložit**.

## <a name="clean-up-resources"></a>Vyčištění prostředků

Pokud už tohoto uživatele nepotřebujete, můžete ho odstranit tak, že zvolíte **Uživatelé** > **Všichni uživatelé** > vyberete daného uživatele v seznamu > **Odstranit uživatele** > **Ano**.

## <a name="next-steps"></a>Další kroky

V tomto rychlém startu jste vytvořili uživatele a pak jste mu přiřadili licenci. Teď můžete daného uživatele přiřadit do skupiny.

> [!div class="nextstepaction"]
> [Vytvoření skupiny](quickstart-create-group.md)
