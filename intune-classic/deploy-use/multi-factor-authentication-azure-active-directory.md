---
title: "Vícefaktorové ověřování pro registraci zařízení v Intune"
description: "Jak vyžadovat vícefaktorové ověřování ve službě Azure AD pro registraci zařízení"
keywords: 
author: arob98
ms.author: angrobe
manager: angerobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: 6d8a13033486256da171847646bd95fe77c978c8
ms.sourcegitcommit: f9bfdaed6037bd76f8715fa7ca15a3457d26370a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/17/2017
---
# <a name="multi-factor-authentication-for-intune-device-enrollments"></a>Vícefaktorové ověřování pro registraci zařízení v Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune integruje vícefaktorové ověřování (MFA) služby Azure AD pro registraci zařízení a pomáhá zabezpečit prostředky společnosti.

Vícefaktorové ověřování funguje tak, že vyžaduje jakékoliv dvě nebo více z následujících metod ověřování: 

- Něco, co víte (obvykle heslo nebo PIN).
- Něco, co máte (důvěryhodné zařízení, které není lehké duplikovat, jako je telefon).
- Nějaká část vašeho těla (biometrika).

Podporuje se pro zařízení se systémem iOS, Android, Windows 8.1 nebo novějším a Windows Phone 8.1 nebo novějším.

> [!NOTE]
> Ve starších verzích Configuration Manageru (do verze 1610) se nastavení MFA stále zobrazuje v konzole správce Configuration Manageru. Nepokoušejte se ale konfigurovat MFA v konzole správce Configuration Manager, protože nebude fungovat. MFA nakonfigurujte podle pokynů v tomto tématu.

### <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Konfigurace služby Intune tak, aby při registraci zařízení vyžadovala vícefaktorové ověřování
K vynucení vícefaktorového ověřování při registraci zařízení slouží tento postup:

1. Přihlaste se pomocí svých přihlašovacích údajů správce na web [Microsoft Azure Portal](https://manage.windowsazure.com).
2. Zvolte tenanta.
2. Vyberte kartu **Aplikace**. Zobrazí se seznam služeb, pro které můžete nakonfigurovat funkce zabezpečení Azure AD.
3. Zvolte **registraci s Microsoft Intune**.
4. Zvolte **Konfigurace**. 
5. V části **vícefaktorového ověřování a pravidel přístupu na základě umístění** můžete:
    
    -  Povolit pravidla přístupu.
    -  Zvolit, jestli se pravidla mají použít pro všechny uživatele, nebo jenom pro konkrétní skupiny zabezpečení Azure AD.
    -  Vyžadovat vícefaktorové ověřování k registraci všech zařízení.
    -  Vyžadovat vícefaktorové ověřování k registraci, pokud zařízení není v práci.
    -  Pokud chcete zabránit registraci zařízení, která nejsou připojená k firemní síti, zvolte **Block access to corporate resources** (Blokovat přístup k podnikovým prostředkům). 
4. Můžete také kliknout na odkaz pro **definování nebo úpravu pracovního síťového umístění** a nakonfigurovat požadavky síťového připojení pro registraci zařízení.

> [!IMPORTANT]
> 
> Pro registraci s Microsoft Intune nekonfigurujte **pravidla přístupu na základě zařízení**.
