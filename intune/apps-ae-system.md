---
title: Přidání aplikací pro Android Enterprise System do Microsoft Intune
titleSuffix: ''
description: Přečtěte si, jak přidat aplikace podnikového systému do Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6cf1694c22e748fd10bb016607b7ff38963e80b5
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71304159"
---
# <a name="add-android-enterprise-system-apps-to-microsoft-intune"></a>Přidání aplikací pro Android Enterprise System do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Před přiřazením aplikace k zařízení nebo skupině uživatelů je nejprve potřeba danou aplikaci přidat do Microsoft Intune. Systémové aplikace jsou podporované na zařízeních s Androidem Enterprise. Můžete povolit systémovou aplikaci pro [vyhrazená podniková zařízení s Androidem](android-kiosk-enroll.md) nebo [plně spravovaná zařízení](android-fully-managed-enroll.md). 

## <a name="add-the-app"></a>Přidání aplikace

Aplikaci pro Android Enterprise System můžete do Intune přidat z Azure Portal tím, že provedete následující kroky:

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. V podokně **Intune** vyberte **Klientské aplikace** > **Aplikace** > **Přidat**.
3. V podokně **Přidat aplikaci** vyberte v části dostupné **jiné** typy možnost aplikace pro **Android Enterprise System**.
4. Pokud chcete nakonfigurovat informace o aplikaci, vyberte **Konfigurovat**a potom zadejte následující informace:
    - **Název aplikace**: Zadejte název aplikace.
    - **Vydavatel**: Zadejte název vydavatele aplikace.  
    - **Název balíčku**: Zadejte název balíčku. Intune ověří, jestli je název balíčku platný.
5. Vyberte **OK**.
6. Vyberte **Přidat**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřazovat vybraným skupinám. 

Aplikace pro Android Enterprise System umožní nebo zakážou aplikace, které už jsou součástí platformy. Pokud chcete aplikaci povolit, přiřaďte systémovou aplikaci podle **potřeby**. Pokud chcete aplikaci zakázat, přiřaďte systémovou aplikaci jako **odinstalaci**. Systémové aplikace nelze přiřadit uživateli, který je k dispozici.

## <a name="next-steps"></a>Další kroky

- [Přiřazení aplikací skupinám](apps-deploy.md)
