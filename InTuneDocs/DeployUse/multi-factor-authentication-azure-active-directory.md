---
title: "Vícefaktorové ověřování pomocí Azure AD | Microsoft Intune"
description: "Jak vyžadovat vícefaktorové ověřování ve službě Azure AD pro registraci zařízení"
keywords: 
author: nbigman
manager: angerobe
ms.date: 09/22/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: NOINDEX,NOFOLLOW
translationtype: Human Translation
ms.sourcegitcommit: a7cced90c482498b5f5af424165f8dcf77b79b75
ms.openlocfilehash: ccd55cc8637ebccfdbddd05c4f6b182c7923a2ab


---

# Vícefaktorové ověřování pro Microsoft Intune

Intune integruje vícefaktorové ověřování (MFA) služby Azure AD pro registraci zařízení a pomáhá zabezpečit prostředky společnosti. MFA vyžaduje kromě uživatelských jmen a hesel také faktory ověřování, jako je ověřování textu. Podporuje se pro zařízení se systémem iOS, Android, Windows 8.1 nebo novějším a Windows Phone 8.1 nebo novějším.

> [!NOTE]
>
> Ve starších verzích Configuration Manageru (do verze 1610) se nastavení MFA stále zobrazuje v konzole správce Configuration Manageru. Nepokoušejte se ale konfigurovat MFA v konzole správce Configuration Manager, protože nebude fungovat. MFA nakonfigurujte podle pokynů v tomto tématu.

### Konfigurace služby Intune tak, aby při registraci zařízení vyžadovala vícefaktorové ověřování
Pokud chcete při registraci zařízení vyžadovat MFA, postupujte takto:

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



<!--HONumber=Sep16_HO4-->


