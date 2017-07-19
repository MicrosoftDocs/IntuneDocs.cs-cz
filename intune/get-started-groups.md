---
title: "Začínáme se skupinami"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 04843a918a3c661ab69dfa711f4d22a8feedf5f3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2017
---
# <a name="get-started-with-groups"></a>Začínáme se skupinami

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[](./media/generic-users-groups.png)

Microsoft Intune používá ke [správě přístupu k prostředkům společnosti](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups) službu Azure Active Directory (Azure AD). Ke kontrole přístupu slouží role v adresáři. Intune pak spravuje přístup mobilních zařízení, aby členové příslušné skupiny měli přístup k prostředkům.

__Jak vytvořím skupinu?__

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. V části **Hledat prostředky** vyhledejte **Uživatelé a skupiny**.
3. Po otevření okna **Uživatelé a skupiny** vyberte **Všechny skupiny**.
4. V okně **Uživatelé a skupiny – Všechny skupiny** vyberte příkaz **Nová skupina**.
5. V okně **Skupina** přidejte **Název** a **Popis** skupiny.
6. **Typ členství** nastavte na **Přiřazené**. Testovací skupině **nepovolujte funkce Office**.
7. Klikněte na **Vytvořit**.

Pokud jste úspěšně vytvořili skupinu, měla by se zobrazit v seznamu **Všechny skupiny**. Pokud tam není, zkuste vytvořit jinou skupinu.
