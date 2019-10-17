---
title: Zásady konfigurace aplikací pro spravované aplikace bez registrace zařízení
titleSuffix: Microsoft Intune
description: Přečtěte si, jak nakonfigurovat zásady pro spravované aplikace bez registrace zařízení.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3a31a4777537db6f656dbf9eaf0b30a6e95412a8
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72499760"
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Přidání zásad konfigurace aplikací pro spravované aplikace bez registrace zařízení

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Zásady konfigurace aplikací můžete používat se spravovanými aplikacemi, které podporují sadu Intune App SDK, i na nezaregistrovaných zařízeních. 

> [!NOTE]
> Aby bylo možné přijímat zásady konfigurace aplikací, musí být aplikace cílem zásad Intune App Protection. Další informace o vytváření zásad Intune App Protection najdete v článku [Co jsou zásady ochrany aplikací](app-protection-policy.md).

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Zvolte úlohu **Klientské aplikace**.
4. Ve skupině **Spravovat** zvolte **Zásady konfigurace aplikací** a pak **Přidat**.
5. Zadejte tyto podrobnosti:
    - **Název**  
      Název profilu, který se zobrazí na portálu Azure Portal
    - **Popis**  
      Popis profilu, který se zobrazí na portálu Azure Portal
    - **Typ registrace zařízení**  
      Zvolte **Spravovat aplikace**.
6. Vyberte **Přidružené aplikace** a zvolte aplikaci, kterou chcete nakonfigurovat. Ze seznamu vyberte některou z aplikací, kterou jste schválili a synchronizovali s Intune.
7. Pro každé nastavení konfigurace podporované aplikací zadejte položky **Název** a **Hodnota** a zvolte tři tečky ( **…** ).  
    Pokud chcete konfiguraci odstranit, zvolte tři tečky ( **…** ) a vyberte **Odstranit**.  
    
Aplikace s povolenou sadou Intune App SDK podporují konfigurace v párech klíč-hodnota. Nahlédněte do dokumentace k jednotlivým aplikacím, kde zjistíte, které konfigurace klíč-hodnota se podporují. Připomínáme, že můžete používat tokeny, které se budou dynamicky plnit daty generovanými aplikací. Informace o nastavení zásad konfigurace aplikace Outlook pro iOS najdete v článku [Správa konfigurace aplikace Outlook pro iOS pomocí Microsoft Intune](https://technet.microsoft.com/library/mt813789(v=exchg.150).aspx).

## <a name="configuration-values-for-using-tokens"></a>Hodnoty konfigurace pro používání tokenů

Intune může určité tokeny vygenerovat a odeslat je do spravované aplikace. Pokud třeba konfigurace aplikace umožňuje používat nastavení e-mailu, můžete pomocí tokenu přidat dynamický e-mail. Do pole **Název** zadejte název, který aplikace očekává, a potom do pole **Hodnota** zadejte `\{\{mail\}\}`.

Intune podporuje v nastavení konfigurace následující typy tokenů. Jiné vlastní dvojice klíč/hodnota nejsou podporované.

- \{\{userprincipalname\}\} – například John@contoso.com.
- \{\{mail\}\} – například John@contoso.com.
- \{\{partialupn\}\} – například John.
- \{\{accountid\}\} – například fc0dc142-71d8-4b12-bbea-bae2a8514c81.
- \{\{userid\}\} – například 3ec2c00f-b125-4519-acf0-302ac3761822.
- \{\{username\}\} – například John Doe.
- \{\{PrimarySMTPAddress\}\} – například testuser@ad.domain.com.


> [!Note]  
> Znaky \{\{ a \}\} se používají jenom pro typy tokenů a nesmí se používat pro jiné účely.

## <a name="next-steps"></a>Další kroky

Pokračujte s [přiřazením](apps-deploy.md) a [sledováním](apps-monitor.md) aplikace jako obvykle.
