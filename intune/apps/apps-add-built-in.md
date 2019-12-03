---
title: Přidání integrovaných aplikací na mobilní zařízení pomocí Microsoft Intune
titleSuffix: ''
description: Zjistěte, jak můžete s Intune zjednodušit instalaci na mobilní zařízení s integrovanými aplikacemi.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a92699ccce4f0b2590e526b3442cd45bfda6407c
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563604"
---
# <a name="add-built-in-apps-to-microsoft-intune"></a>Přidání integrovaných aplikací do Microsoft Intune

*Integrovaný* typ aplikace usnadňuje přiřazení kurátorovaných spravovaných aplikací, jako jsou například aplikace Office 365, k zařízením s iOSem a Androidem. Pro tento typ aplikace můžete přiřadit konkrétní aplikace, jako jsou například Excel, OneDrive, Outlook, Skype a další. Po přidání aplikace se zobrazí typ aplikace jako *Integrovaná aplikace pro iOS* nebo *Integrovaná aplikace pro Android*. Když použijete integrovaný typ aplikace, můžete vybrat, které z těchto aplikací chcete publikovat do zařízení uživatelů.

Ve starších verzích konzoly Intune bylo v Intune několik výchozích spravovaných aplikací Office 365, jako je Outlook a OneDrive. Typ aplikace se u těchto spravovaných aplikací označoval jako *Spravovaná aplikace z obchodu pro iOS* nebo *Spravovaná aplikace z obchodu pro Android*. Místo těchto aplikací doporučujeme použít integrovaný typ aplikace. Tyto aplikace poskytují větší flexibilitu pro úpravy a odstraňování aplikací Office 365.

>[!NOTE]
>Výchozí aplikace Office 365, které jsou označené jako *Spravovaná aplikace z obchodu pro iOS* a *Spravovaná aplikace z obchodu pro Android*, se při odstranění všech přiřazení ze seznamu aplikací odeberou.

## <a name="add-a-built-in-app"></a>Přidání integrované aplikace

Postup přidání integrované aplikace k aplikacím dostupným v Microsoft Intune je následující:
1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **aplikace** > **všechny aplikace** > **Přidat**.
3. V podokně **Přidat aplikace** vyberte v seznamu **Typ aplikace** možnost **Integrovaná aplikace**.
4. Zvolte **Vybrat aplikaci**.
5. V podokně **Integrovaná aplikace** vyberte aplikace, které chcete zahrnout.
6. V podokně **Přidat aplikaci** zvolte **Přidat**.


## <a name="configure-app-information"></a>Konfigurace informací o aplikaci

Informace o integrované aplikaci můžete upravit. Tyto informace vám pomůžou identifikovat aplikaci v Intune a také pomůžou uživatelům, aby ji našli na portálu společnosti.
1. Vyberte **aplikace** > **všechny aplikace** a vyberte vestavěnou aplikaci, kterou chcete upravit.  
   Zobrazí se podokno pro integrovanou aplikaci.
2. Vyberte **vlastnosti** > **nakonfigurovat**.
4. V podokně **Informace o aplikaci** je možné upravit následující údaje:
    - **Název**: Zadejte název integrované aplikace, který se zobrazí na portálu společnosti. Všechny používané názvy musí být jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis**: Zadejte popis aplikace. 
    - **Vydavatel**: Zadejte název vydavatele aplikace.
    - **Kategorie**: Volitelně vyberte jednu nebo více kategorií integrovaných aplikací. Nastavením této možnosti uživatelům usnadníte vyhledání aplikace při procházení portálu společnosti.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci**: Když uživatelé vyhledávají aplikace, zobrazí se daná aplikace na význačném místě hlavní stránky portálu společnosti.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů**: Volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář**: Volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník**: Volitelně zadejte vlastníka aplikace, například *Personální oddělení*.
    - **Poznámky**: Zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Nahrát ikonu**: Nahrajte ikonu, která se zobrazí u aplikace, když uživatelé procházejí portál společnosti.
4. Vyberte **OK**.
5. V podokně **Vlastnosti** vyberte **Uložit**.

## <a name="next-steps"></a>Další kroky

- Nyní můžete přiřadit aplikace do skupin podle vlastního výběru. Podrobnosti najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).