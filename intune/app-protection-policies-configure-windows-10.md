---
title: Příprava na konfiguraci zásad ochrany aplikací pro Windows 10
titleSuffix: Microsoft Intune
description: Nastavení poskytovatele správy mobilních aplikací (MAM) v Azure AD
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a394b3b218613459d993b84fcb0ea7a37d4ac4dd
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/17/2018
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Příprava na konfiguraci zásad ochrany aplikací pro Windows 10 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Povolte správu mobilních aplikací (MAM) pro Windows 10 nastavením zprostředkovatele MAM v Azure AD. Nastavení poskytovatele MAM v Azure AD vám umožní definovat stav registrace při vytváření nových zásad WIP (Windows Information Protection) s Intune. Stav registrace může být MAM nebo MDM (správa mobilních zařízení).

> [!NOTE]
> Zařízení se stavem registrace MAM musí být připojená k Azure AD.

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

## <a name="next-steps"></a>Další kroky

[Vytvoření zásad ochrany aplikací WIP](windows-information-protection-policy-create.md)
