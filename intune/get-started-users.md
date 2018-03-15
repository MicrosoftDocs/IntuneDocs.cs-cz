---
title: "Začínáme se správou uživatelů"
titlesuffix: Microsoft Intune
description: "Přidejte do Intune uživatele a přiřaďte jim licence, aby měli přístup k prostředkům společnosti z mobilních zařízení."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e06b335c03caee0bd997748f9c48ed78d7d379b
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="get-started-managing-users"></a>Začínáme se správou uživatelů

Zamyslete se nad všemi různými lidmi, kteří pracují ve vaší organizaci. Každý, kdo využívá firemní data, bude v Intune kvůli správě přístupu k těmto datům potřebovat uživatele.

## <a name="how-do-i-create-a-user"></a>Jak vytvořím uživatele?

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. V části **Hledat prostředky** vyhledejte **Intune**.
3. Po otevření okna **Microsoft Intune** vyberte **Uživatelé**. Na stránce **Všichni uživatelé** vyberte **+ Nový uživatel**.
4. Zadejte podrobnosti o uživateli, jako je **Jméno** a **Uživatelské jméno**. Část uživatelského jména, která odpovídá názvu domény, musí být buď původní výchozí název domény „contoso.onmicrosoft.com“, nebo ověřený nefederovaný název domény, třeba „contoso.com“.
5. V části **Skupiny** zvolte testovací skupinu, do které chcete uživatele přidat.
6. Uložte si automaticky vygenerované heslo uživatele, abyste ho mohli použít k přihlášení do testovacího zařízení. Toto heslo musíte dát uživatelům, aby ho mohli změnit na normální heslo, které si zapamatují.
7. V okně **Uživatel** vyberte **Vytvořit**.

## <a name="assigning-licenses-to-users"></a>Přiřazení licencí uživatelům

Po vytvoření uživatele potřebujete použít [portál Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), abyste na něm danému uživateli přiřadili licenci Intune. Bez licence si uživatelé nemohou zaregistrovat své zařízení, aby bylo možné ho spravovat.

1. Přihlaste se k [portálu Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854). K přihlášení použijte stejné přihlašovací údaje jako pro Intune.
2. Vyberte **Uživatelé** > **Aktivní uživatelé** a vyberte uživatele, kterého jste vytvořili.
3. Možná budete muset chvilku počkat, než se načtou všechny informace o uživateli. Po načtení vyberte u uživatelských **licencí na produkty** možnost **Upravit**.
4. Přiřaďte uživateli **polohu** a přepněte Intune na **Zapnuto**.

 > [!NOTE]
 > Tím pro uživatele použijete jednu licenci. Pokud používáte živé prostředí, můžete používání této licence později vypnout, abyste ji mohli přiřadit skutečnému uživateli.

5. Vyberte **Uložit**.

## <a name="next-steps"></a>Další kroky

[Začínáme se skupinami](get-started-groups.md) – když uživatele uspořádáte do skupin, usnadníte si správu zásad a aplikací, ke kterým mají přístup.
