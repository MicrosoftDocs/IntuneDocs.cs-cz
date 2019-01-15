---
title: Konfigurace zásad ochrany aplikací pro Windows 10
titleSuffix: Microsoft Intune
description: Nastavení poskytovatele správy mobilních aplikací (MAM) v Azure AD
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 189afded0674958720234df86ed5d09c5cb8193d
ms.sourcegitcommit: e9ba1280b95565a5c5674b825881655d0303e688
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/15/2019
ms.locfileid: "54297329"
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Příprava na konfiguraci zásad ochrany aplikací pro Windows 10 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Povolte správu mobilních aplikací (MAM) pro Windows 10 nastavením zprostředkovatele MAM v Azure AD. Nastavení poskytovatele MAM v Azure AD vám umožní definovat stav registrace při vytváření nových zásad WIP (Windows Information Protection) s Intune. Stav registrace může být MAM nebo MDM (správa mobilních zařízení).

## <a name="to-configure-the-mam-provider"></a>Konfigurace poskytovatele MAM

1. Přihlaste se k portálu Azure Portal a vyberte **Azure Active Directory**.

2. Ve skupině **Spravovat** zvolte **Mobilita (MDM a MAM)**.

3. Klikněte na **Microsoft Intune**.

4. Nakonfigurujte nastavení ve skupině **Obnovit výchozí adresy URL MAM** v okně **Konfigurovat**.

   **Obor uživatele MAM**  
   Pomocí automatické registrace MAM můžete spravovat podniková data na zařízeních zaměstnanců, která používají Windows. Automatická registrace MAM se nakonfiguruje pro scénáře typu Přineste si vlastní zařízení.<ul><li>**Žádné**<br>Vyberte, pokud se do MAM nemůžou zaregistrovat žádní uživatelé.</li><li>**Některé**<br>Vyberte skupiny Azure AD obsahující uživatele, kteří budou zaregistrováni do MAM.</li><li>**Vše**<br>Vyberte, pokud se do MAM můžou zaregistrovat všichni uživatelé.</li></ul>

   **Adresa URL podmínek použití služby MAM**  
   Adresa URL podmínek použití služby MAM není pro Microsoft Intune podporovaná. Aby zásady ochrany platily, musí toto vstupní pole zůstat prázdné.

   **Adresa URL zjišťování MAM**  
   Adresa URL koncového bodu pro registraci do služby MAM. Koncový bod registrace se používá k registraci zařízení do správy službou MAM.

   **Adresa URL s předpisy služby MAM**  
   Adresa URL s předpisy služby MAM není pro Microsoft Intune podporovaná. Aby zásady ochrany platily, musí toto vstupní pole zůstat prázdné. 

5.  Klikněte na **Uložit**.

## <a name="next-steps"></a>Další postup

[Vytvoření zásad ochrany aplikací WIP](windows-information-protection-policy-create.md)
