---
title: "Nasazení a monitorování zásad dodržování předpisů | Microsoft Intune"
description: "Podrobné pokyny v tomto tématu slouží k nasazení a monitorování zásad dodržování předpisů pro zařízení."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 711e650086d7528f26d9ba7b447ecb0185faff23
ms.openlocfilehash: 8658df1fb9932fb2cab984a13557aad684569df5


---

# Nasazení a monitorování zásad dodržování předpisů zařízení v Microsoft Intune
## Nasazení zásady dodržování předpisů
Nasaďte vámi [vytvořenou](create-a-device-compliance-policy-in-microsoft-intune.md) zásadu dodržování předpisů do jedné nebo několika skupin uživatelů ve vaší organizaci. Po nasazení zásady dodržování předpisů uživateli se u jeho zařízení kontroluje dodržování předpisů.

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a potom vyberte **Spravovat nasazení**.
![Snímek stránky zásad dodržování předpisů zobrazující možnosti nabídky Spravovat nasazení v horní části](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  V dialogu **Spravovat nasazení** vyberte jednu nebo víc skupin, do kterých chcete zásadu nasadit, a potom vyberte **Přidat > OK**.
![Snímek obrazovky dialogového okna Spravovat nasazení](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) Zásady dodržování předpisů můžete nasadit pro uživatele. Použijte skupiny služby Active Directory, které už máte vytvořené a synchronizované s Intune, nebo tyto skupiny vytvořte ručně v konzole služby Intune. Další informace o nasazení zásad najdete v tématu [Nasazení zásady konfigurace](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Pomocí shrnutí stavu a výstrah na stránce **Přehled** v pracovním prostoru **Zásady** můžete identifikovat problémy se zásadami, které vyžadují vaši pozornost. Kromě toho se v pracovním prostoru **Řídicí panel** zobrazí shrnutí stavu.

> [!IMPORTANT]
> Pokud jste zásady dodržování předpisů nenasadili a povolíte zásady podmíněného přístupu Exchange, budou mít všechna cílová zařízení přístup povolený.

## Způsob řešení konfliktů zásad Intune
Konflikty zásad můžou vzniknout kvůli použití více zásad Intune na zařízení. Pokud se nastavení zásad překrývají, Intune vyřeší všechny konflikty s použitím následujících pravidel:

-   Pokud jsou konfliktní nastavení ze zásad konfigurace a dodržování předpisů služby Intune, bude mít nastavení v zásadách kompatibility přednost před nastavením v zásadách konfigurace, a to i v případě, že je nastavení v zásadách konfigurace bezpečnější.

-   Pokud jste nasadili víc zásad dodržování předpisů, použijí se ty nejbezpečnější z nich.

## Monitorování zásady dodržování předpisů

#### Zobrazení zařízení, která nesplňují zásady dodržování předpisů

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Skupiny > Všechna zařízení**.

2.  Dvakrát klikněte na název zařízení v seznamu zařízení.

3.  Vyberte kartu **Zásady**, na které najdete seznam zásad pro dané zařízení.

4.  V rozevíracím seznamu **Filtry** vyberte **Nevyhovuje zásadám dodržování předpisů**.
![Snímek obrazovky zobrazující seznam možností v seznamu filtrů](./media/intune-sa-3e-view-device-noncompliance.png)

#### Postup zobrazení sestav Health Attestation

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Sestavy**.

2.  Na stránce **Sestava Health Attestation – Vytvoření nové sestavy** můžete zobrazit sestavu obsahující všechna data o ověření stavu Windows 10 shromážděná službou Intune. Pomocí filtrů taky můžete vytvořit sestavu obsahující jenom určitou podmnožinu dat. Filtry se můžou týkat typu zařízení, operačního systému nebo jenom určité podmnožiny datových bodů.


## Další kroky
Teď už můžete používat zásady dodržování předpisů spolu se zásadami podmíněného přístupu, abyste mohli řídit přístup ke službám ve vaší organizaci.

[Omezení přístupu k e-mailu a službám O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)


### Viz taky
[Úvod do zásad dodržování předpisů zařízení v Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md)



<!--HONumber=Aug16_HO3-->


