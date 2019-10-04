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
ms.openlocfilehash: 19f398f58c643928497d8083c173f88862cb0c24
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940088"
---
# <a name="add-android-enterprise-system-apps-to-microsoft-intune"></a>Přidání aplikací pro Android Enterprise System do Microsoft Intune

Předtím, než aplikaci přiřadíte k zařízení nebo skupině uživatelů, musíte aplikaci nejprve přidat do Microsoft Intune. Systémové aplikace jsou podporované na zařízeních s Androidem Enterprise. Můžete povolit systémovou aplikaci pro [vyhrazená podniková zařízení s Androidem](../enrollment/android-kiosk-enroll.md) nebo [plně spravovaná zařízení](../enrollment/android-fully-managed-enroll.md).

## <a name="add-the-app"></a>Přidání aplikace

Aplikaci pro Android Enterprise System můžete do Intune přidat z Azure Portal tím, že provedete následující kroky:

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. V podokně **Intune** vyberte **klientské aplikace** > **aplikace** > **Přidat**.
3. V podokně **Přidat aplikaci** vyberte v části dostupné **jiné** typy možnost aplikace pro **Android Enterprise System**.
4. Pokud chcete nakonfigurovat informace o aplikaci, vyberte **Konfigurovat**a potom zadejte následující informace:
    - **Název aplikace**: zadejte název aplikace.
    - **Vydavatel**: zadejte název vydavatele aplikace.  
    - **Název balíčku**: zadejte název balíčku. Intune ověří, jestli je název balíčku platný.
5. Vyberte **OK**.
6. Vyberte **Přidat**.

> [!NOTE]
> Abyste mohli najít název balíčku aplikace, kterou chcete povolit nebo zakázat, budete muset pracovat s výrobcem OEM vašeho zařízení.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřadit ke skupinám, které vyberete. 

Aplikace pro Android Enterprise System umožní nebo zakážou aplikace, které už jsou součástí platformy. Pokud chcete aplikaci povolit, přiřaďte systémovou aplikaci podle **potřeby**. Pokud chcete aplikaci zakázat, přiřaďte systémovou aplikaci jako **odinstalaci**. Systémové aplikace nelze přiřadit uživateli, který je k dispozici.

> [!TIP]
> Vyvolejte, pokud můžete systémovou aplikaci povolit poté, co ji zakážete bez obnovení továrního nastavení.

## <a name="next-steps"></a>Další kroky

- [Přiřazení aplikací ke skupinám](apps-deploy.md)
