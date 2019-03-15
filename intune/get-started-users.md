---
title: Začínáme se správou uživatelů
titlesuffix: Microsoft Intune
description: Přidejte do Intune uživatele a přiřaďte jim licence, aby měli přístup k prostředkům společnosti z mobilních zařízení.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d7b584fe9d56cd02ce8ee066113c033d8b124559
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57461222"
---
# <a name="get-started-managing-users"></a>Začínáme se správou uživatelů

Zamyslete se nad všemi různými lidmi, kteří pracují ve vaší organizaci. Každý, kdo využívá firemní data, bude v Intune kvůli správě přístupu k těmto datům potřebovat uživatele.

## <a name="how-do-i-create-a-user"></a>Jak vytvořím uživatele?

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Po otevření podokna **Microsoft Intune** vyberte **Uživatelé**. Na stránce **Všichni uživatelé** vyberte **+ Nový uživatel**.
4. Zadejte podrobnosti o uživateli, například **Jméno** a **Uživatelské jméno**. Část uživatelského jména, která odpovídá názvu domény, musí být jedna z následujících domén:
    - počáteční výchozí název domény contoso.onmicrosoft.com, nebo
    - ověřený nefederovaný název domény, například contoso.com.
5. V části **Skupiny** zvolte [skupinu](get-started-groups.md), do které chcete uživatele přidat.
6. Uložte si automaticky vygenerované heslo uživatele, abyste ho mohli použít k přihlášení do testovacího zařízení. Toto heslo musíte dát uživatelům, aby ho mohli změnit na normální heslo, které si zapamatují.
7. V podokně **Uživatelé** vyberte **Vytvořit**.

## <a name="assigning-licenses-to-users"></a>Přiřazení licencí uživatelům

Po vytvoření uživatele, budete muset použít [centra pro správu služeb Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) přiřadit tomuto uživateli licenci Intune. Bez licence si uživatelé nemohou zaregistrovat své zařízení, aby bylo možné ho spravovat.

1. Přihlaste se k [centra pro správu služeb Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) pomocí stejných přihlašovacích údajů, které jste použili k přihlášení k Intune.
2. Vyberte **Uživatelé** > **Aktivní uživatelé** a vyberte uživatele, kterého jste vytvořili.
3. Možná budete muset chvilku počkat, než se načtou všechny informace o uživateli. Po načtení vyberte u uživatelských **licencí na produkty** možnost **Upravit**.
4. Přiřaďte uživateli **polohu** a přepněte Intune na **Zapnuto**.

   > [!NOTE]
   > Tím pro uživatele použijete jednu licenci. Pokud používáte živé prostředí, můžete používání této licence později vypnout, abyste ji mohli přiřadit skutečnému uživateli.

5. Vyberte **Uložit**.

## <a name="next-steps"></a>Další postup

[Začínáme se skupinami](get-started-groups.md) – když uživatele uspořádáte do skupin, usnadníte si správu zásad a aplikací, ke kterým mají přístup.
