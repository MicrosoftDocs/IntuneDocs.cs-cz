---
title: "Začínáme s uživateli"
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
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e711f32ebd77a83b17e6db468f8cb23a409c8d31
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/03/2017
---
# <a name="get-started-with-users"></a>Začínáme s uživateli

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Azure Active Directory spravuje v organizaci skupiny objektů, jako jsou zařízení, aplikace a také skupiny uživatelů. Abyste nemuseli spravovat jednotlivá zařízení, můžete uživatele nebo zařízení zařazovat do skupin. Skupiny vám umožní jednoduše přiřazovat aplikace a nastavení velkému počtu uživatelů a zařízení.

## <a name="how-do-i-create-a-user"></a>Jak vytvořím uživatele?

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. V části **Hledat prostředky** vyhledejte **Uživatelé a skupiny**.
3. Po otevření okna **Uživatelé a skupiny** vyberte **Všichni uživatelé** a pak vyberte **+ Nový uživatel**.
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
