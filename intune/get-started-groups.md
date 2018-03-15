---
title: "Vytvoření skupiny v Microsoft Intune"
titleSuffix: 
description: "Když uživatele uspořádáte do skupin, usnadníte si správu zásad a aplikací, ke kterým mají přístup."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e052f7c8d5742859d009816473fe97a98c499b17
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="create-a-group-to-manage-your-users-and-data-access"></a>Vytvoření skupiny pro správu uživatelů a přístupu k datům

Skupiny se používají ke správě uživatelů a řídí přístup zaměstnanců k firemním prostředkům. Tyto prostředky můžou být součástí vašeho adresáře, nebo se může jednat o externí prostředky, jako jsou aplikace SaaS nebo sharepointové weby.

Microsoft Intune používá ke správě přístupu k firemním prostředkům službu Azure Active Directory (Azure AD). Ke kontrole přístupu slouží role v adresáři. Intune pak spravuje přístup mobilních zařízení, aby členové příslušné skupiny měli přístup k prostředkům.

## <a name="how-do-i-create-a-group"></a>Jak vytvořím skupinu?

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. V části **Hledat prostředky** vyhledejte **Intune**.
3. Po otevření okna **Microsoft Intune** vyberte **Skupiny**.
4. V okně **Uživatelé a skupiny – Všechny skupiny** vyberte příkaz **Nová skupina**.
5. V okně **Skupina** přidejte **Název** a **Popis** skupiny.
6. **Typ členství** nastavte na **Přiřazené**. Testovací skupině **nepovolujte funkce Office**.
7. Klikněte na **Vytvořit**.

Pokud jste úspěšně vytvořili skupinu, měla by se zobrazit v seznamu **Všechny skupiny**. Pokud tam není, zkuste vytvořit jinou skupinu.

## <a name="next-steps"></a>Další kroky

[Začínáme se zásadami](get-started-policies.md) – vytvořením zásad zabráníte uživatelům, aby se svými zařízeními dělali něco neoprávněného.

## <a name="learn-more"></a>Další informace

* [Nastavení omezení registrace pomocí skupin v Intune](groups-add.md)
* [Správa přístupu k firemním prostředkům pomocí skupin ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
