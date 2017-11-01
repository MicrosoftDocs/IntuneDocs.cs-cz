---
title: "Příprava na konfiguraci zásad ochrany aplikací pro Windows 10"
titlesuffix: Azure portal
description: "Nastavení poskytovatele správy mobilních aplikací (MAM) v Azure AD"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 09f3edbe8b53371514ae4826246c99201c005762
ms.sourcegitcommit: b5692ee05e8be1842cb1007facf80c9bce972dc4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2017
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
      Pomocí automatické registrace MAM můžete spravovat podniková data na zařízeních zaměstnanců, která používají Windows. Automatická registrace MAM se nakonfiguruje pro scénáře typu Přineste si vlastní zařízení.<ul><li>**Žádné**<br>Vyberte, pokud se do MAM můžou zaregistrovat všichni uživatelé.</li><li>**Některé**<br>Vyberte skupiny Azure AD obsahující uživatele, kteří budou zaregistrováni do MAM.</li><li>**Vše**<br>Vyberte, pokud se do MAM můžou zaregistrovat všichni uživatelé.</li></ul>

    **Adresa URL podmínek použití služby MAM**  
     Adresa URL koncového bodu podmínek použití služby MAM. Koncový bod podmínek použití slouží k zobrazení podmínek služby koncovým uživatelům před tím, než se jejich zařízení zaregistruje ke správě. Text podmínek použití poskytuje uživatelům informace o zásadách, které se budou pro mobilní zařízení vynucovat.

    **Adresa URL zjišťování MAM**  
    Adresa URL koncového bodu pro registraci do služby MAM. Koncový bod registrace se používá k registraci zařízení do správy službou MAM.

    **Adresa URL s předpisy služby MAM**  
      Adresa URL koncového bodu dodržování předpisů služby MAM. Když se uživateli zamítne přístup k prostředku ze zařízení, které nedodržuje předpisy, zobrazí se mu adresa URL, kterou hostuje služba MAM. Na té uživatel najde informace o tom, proč jeho zařízení neodpovídá předpisům. Navíc uživatelé můžou spustit proces samoobslužné nápravy, aby jejich zařízení předpisy dodržovalo a oni měli dál přístup k prostředkům.

5.  Klikněte na **Uložit**.

## <a name="next-steps"></a>Další kroky

[Vytvoření zásad ochrany aplikací WIP](windows-information-protection-policy-create.md)
