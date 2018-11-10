---
title: 'Rychlý start: Vytvoření a přiřazení vlastní role v Intune'
description: 'Rychlý start: Vytvoření a přiřazení vlastní role pro správce vzdáleného zařízení'
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 33c0d4f3ee3b29be47540c92425f76a3f1dcc044
ms.sourcegitcommit: 9d08545727543b434dd270371fa50233470f2bce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2018
ms.locfileid: "50410765"
---
# <a name="quickstart-create-and-assign-a-custom-role"></a>Rychlý start: Vytvoření a přiřazení vlastní role

V tomto rychlém startu pro Intune vytvoříte vlastní roli se specifickými oprávněními pro oddělení operací zabezpečení. Potom tuto roli přiřadíte skupině příslušných operátorů. Existuje několik výchozích rolí, které se dají okamžitě použít. Vytvořením vlastních rolí, jako je tato, však můžete přesně řídit přístup ke všem částem systému pro správu mobilních zařízení.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadavky

- Abyste mohli projít tento rychlý start, je nutné [vytvořit skupinu](quickstart-create-group.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo správce služby Intune.

## <a name="create-a-custom-role"></a>Vytvoření vlastní role

Když vytvoříte vlastní roli, můžete nastavit oprávnění pro širokou škálu akcí. Pro roli Operace zabezpečení nastavíme několik oprávnění ke čtení tak, aby příslušný operátor mohl kontrolovat konfigurace a zásady zařízení.

1. V Intune zvolte **Role** > **Všechny role** > **Přidat**.
![Prohlížeč](media/quickstart-create-custom-role/add-custom-role.png)
2. V části **Přidat vlastní roli** do pole **Název** zadejte *Operace zabezpečení*.
3. Do pole **Popis** zadejte *Tato role umožňuje operátorovi zabezpečení monitorovat konfiguraci zařízení a informace o dodržování předpisů.*
4. Zvolte **Konfigurovat** > **Identifikátory podnikových zařízení** > **Ano** vedle možnosti **Číst** > **OK**.
![Prohlížeč](media/quickstart-create-custom-role/corp-device-id-read.png)
5. Zvolte **Zásady dodržování předpisů zařízení** > **Ano** vedle možnosti **Číst** > **OK**.
6. Zvolte **Konfigurace zařízení** > **Ano** vedle možnosti **Číst** > **OK**.
7. Zvolte **Organizace** > **Ano** vedle možnosti **Číst** > **OK**.
8. Zvolte **OK** > **Vytvořit**.

## <a name="assign-the-role-to-a-group"></a>Přiřazení role skupině

Operátor zabezpečení může použít nová oprávnění až poté, co danou roli přiřadíte skupině obsahující uživatele zabezpečení.

1. V Intune zvolte **Role** > **Všechny role** > **Operace zabezpečení**.
2. V části **Role Intune** zvolte **Přiřazení** > **Přiřadit**.
3. Do pole **Název přiřazení** zadejte *Operace zabezpečení*.
4. Zvolte **Členové (Skupiny)** > **Přidat**.
5. Zvolte skupinu **Testeři Contoso**.
6. Zvolte **Vybrat** > **OK**.
7. Zvolte **Rozsah (Skupiny)** > **Vybrat skupiny, které se zahrnou** > **Testeři Contoso**.
8. Zvolte **Vybrat** > **OK** > **OK**.

Teď jsou všichni členové dané skupiny členy role *Operace zabezpečení* a můžou kontrolovat následující informace o zařízení: identifikátory podnikových zařízení, zásady dodržování předpisů zařízením, konfigurace zařízení a informace o organizaci.

## <a name="clean-up-resources"></a>Vyčištění prostředků

Pokud už nechcete novou vlastní roli dále používat, můžete ji odstranit. Zvolte **Role** > **Všechny role** > vyberte tři tečky vedle příslušné role > **Odstranit**.

## <a name="next-steps"></a>Další kroky

V tomto rychlém startu jste vytvořili vlastní roli pro operace zabezpečení a přiřadili jste ji skupině. Další informace o záležitostech týkajících se zabezpečení najdete v následujícím článku.

> [!div class="nextstepaction"]
> [Začínáme se zásadami dodržování předpisů zařízeními](device-compliance-get-started.md)
