---
title: Vytvoření skupiny v Microsoft Intune
titleSuffix: ''
description: Když uživatele uspořádáte do skupin, usnadníte si správu zásad a aplikací, ke kterým mají přístup.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: fcf6f3071e50304216a182a21dd542cace1b6390
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186456"
---
# <a name="create-a-group-to-manage-your-users-and-data-access"></a>Vytvoření skupiny pro správu uživatelů a přístupu k datům

Skupiny se používají ke správě uživatelů a řídí přístup zaměstnanců k firemním prostředkům. Tyto prostředky můžou být součástí vašeho adresáře, nebo se může jednat o externí prostředky, jako jsou aplikace SaaS nebo sharepointové weby.

Microsoft Intune používá ke správě přístupu k firemním prostředkům službu Azure Active Directory (Azure AD). Ke kontrole přístupu slouží role v adresáři. Intune pak spravuje přístup mobilních zařízení, aby členové příslušné skupiny měli přístup k prostředkům.

## <a name="how-do-i-create-a-group"></a>Jak vytvořím skupinu?

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Po otevření podokna **Microsoft Intune** vyberte **Skupiny**.
4. V podokně **Uživatelé a skupiny – Všechny skupiny** vyberte příkaz **Nová skupina**.
5. V podokně **Skupina** zvolte **Typ skupiny**.
5. Přidejte **název** a **popis** skupiny.
6. **Typ členství** nastavte na **Přiřazené**. Testovací skupině **nepovolujte funkce Office**.
7. Vyberte **členy** skupiny.
7. Klikněte na **Vytvořit**.

Pokud jste úspěšně vytvořili skupinu, měla by se zobrazit v seznamu **Všechny skupiny**. Pokud tam není, zkuste vytvořit jinou skupinu.

## <a name="next-steps"></a>Další postup

[Začínáme se zásadami](get-started-policies.md) – vytvořením zásad zabráníte uživatelům, aby se svými zařízeními dělali něco neoprávněného.

## <a name="learn-more"></a>Další informace

* [Nastavení omezení registrace pomocí skupin v Intune](groups-add.md)
* [Správa přístupu k firemním prostředkům pomocí skupin ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
