---
title: "Přidání zásad konfigurace aplikací pro spravované aplikace bez registrace zařízení | Dokumentace Microsoftu"
titlesuffix: Azure portal
description: "Přečtěte si, jak přidat zásady konfigurace aplikací pro spravované aplikace bez registrace zařízení."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c2266e460d816dfdd908d6a68944c8c2cc5c0afc
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Přidání zásad konfigurace aplikací pro spravované aplikace bez registrace zařízení

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zásady konfigurace aplikací můžete používat se spravovanými aplikacemi, které podporují sadu Intune App SDK, i na nezaregistrovaných zařízeních. 

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** + **Intune**.
3. Zvolte úlohu **Mobilní aplikace**.
4. Ve skupině **Spravovat** zvolte **Zásady konfigurace aplikací** a pak **Přidat**.
5. Zadejte tyto podrobnosti:
    - **Název**  
      Název profilu, který se zobrazí na portálu Azure Portal
    - **Popis**  
      Popis profilu, který se zobrazí na portálu Azure Portal
    - **Typ registrace zařízení**  
      Zvolte **Spravovat aplikace**.
6. Vyberte **Přidružené aplikace** a zvolte aplikaci, kterou chcete nakonfigurovat. Ze seznamu vyberte některou z aplikací, kterou jste schválili a synchronizovali s Intune.
7. Pro každé nastavení konfigurace podporované aplikací zadejte položky **Název** a **Hodnota** a zvolte tři tečky (**…**).  
    Pokud chcete konfiguraci odstranit, zvolte tři tečky (**…**) a vyberte **Odstranit**.  
    Aplikace s povolenou sadou Intune App SDK podporují konfigurace v párech klíč-hodnota. Nahlédněte do dokumentace k jednotlivým aplikacím, kde zjistíte, které konfigurace klíč-hodnota se podporují.  
    Kromě toho můžete používat tokeny, které se budou dynamicky plnit daty generovanými aplikací.

## <a name="configuration-values-for-using-tokens"></a>Hodnoty konfigurace pro používání tokenů

Intune může určité tokeny vygenerovat a odeslat je do spravované aplikace. Pokud třeba konfigurace aplikace umožňuje používat nastavení e-mailu, můžete pomocí tokenu přidat dynamický e-mail. Do pole **Název** zadejte název, který aplikace očekává, a potom do pole **Hodnota** zadejte `\{\{mail\}\}`.

Intune podporuje v nastavení konfigurací následující typy tokenů:

- \{\{userprincipalname\}\} – například **John@contoso.com**
- \{\{mail\}\} – například **John@contoso.com**
- \{\{partialupn\}\} – například **John**
- \{\{accountid\}\} – například **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{userid\}\} – například **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\} – například **John Doe**
- \{\{PrimarySMTPAddress\}\} – například **testuser@ad.domain.com** 


> [!Note]  
> Znaky \{\{ a \}\} se používají jenom pro typy tokenů a nesmí se používat pro jiné účely.

## <a name="next-steps"></a>Další kroky

Pokračujte s [přiřazením](apps-deploy.md) a [sledováním](apps-monitor.md) aplikace jako obvykle.