---
title: "Začínáme se skupinami"
titleSuffix: Intune on Azure
description: "Když uživatele uspořádáte do skupin, usnadníte si správu zásad a aplikací, ke kterým mají přístup."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 276a594abdd3c92051041a5faa34d3ee7633e32c
ms.sourcegitcommit: 45204e0fb8cb4cce449e65f2f1d7bb6f6ac4ccf5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2017
---
# <a name="get-started-with-groups"></a>Začínáme se skupinami

Skupiny se používají ke správě uživatelů a určují přístup vašich zaměstnanců k firemním prostředkům. Tyto prostředky můžou být součástí vašeho adresáře, nebo se může jednat o externí prostředky, jako jsou aplikace SaaS nebo sharepointové weby.

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
