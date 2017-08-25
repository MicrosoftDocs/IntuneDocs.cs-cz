---
title: "Začínáme s uživateli"
titleSuffix: Intune on Azure
description: "Přidáním uživatele do Intune mu povolíte přístup k firemním prostředkům na mobilních zařízeních."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1559a265b28627281b484c8250d1c597d2f094c6
ms.sourcegitcommit: 45204e0fb8cb4cce449e65f2f1d7bb6f6ac4ccf5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2017
---
# <a name="get-started-with-managing-users"></a>Začínáme se správou uživatelů

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
