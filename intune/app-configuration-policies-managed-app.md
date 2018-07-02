---
title: Zásady konfigurace aplikací pro spravované aplikace bez registrace zařízení
titlesuffix: Microsoft Intune
description: Přečtěte si, jak nakonfigurovat zásady pro spravované aplikace bez registrace zařízení.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ce8791eaf72f5fda969401c19e72c6cc8b538d6
ms.sourcegitcommit: b47fad133ef8ef1eb65484463431c6c53f6a638a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35291457"
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Přidání zásad konfigurace aplikací pro spravované aplikace bez registrace zařízení

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zásady konfigurace aplikací můžete používat se spravovanými aplikacemi, které podporují sadu Intune App SDK, i na nezaregistrovaných zařízeních. 

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
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
    
Aplikace s povolenou sadou Intune App SDK podporují konfigurace v párech klíč-hodnota. Nahlédněte do dokumentace k jednotlivým aplikacím, kde zjistíte, které konfigurace klíč-hodnota se podporují. Připomínáme, že můžete používat tokeny, které se budou dynamicky plnit daty generovanými aplikací. Informace o nastavení zásad konfigurace aplikace Outlook pro iOS najdete v článku [Správa konfigurace aplikace Outlook pro iOS pomocí Microsoft Intune](https://technet.microsoft.com/en-us/library/mt813789(v=exchg.150).aspx).

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
