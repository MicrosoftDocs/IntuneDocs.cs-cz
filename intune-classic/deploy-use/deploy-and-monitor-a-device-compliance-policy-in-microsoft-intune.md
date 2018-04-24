---
title: Nasazení a monitorování zásady dodržování předpisů
description: Podrobné pokyny v tomto tématu slouží k nasazení a monitorování zásad dodržování předpisů pro zařízení.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7e3f67411a4eff357102756e785f4cbbff120d23
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune"></a>Nasazení a monitorování zásad dodržování předpisů zařízení v Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="deploy-a-compliance-policy"></a>Nasazení zásady dodržování předpisů
Nasaďte vámi [vytvořenou](create-a-device-compliance-policy-in-microsoft-intune.md) zásadu dodržování předpisů do jedné nebo několika skupin uživatelů ve vaší organizaci. Po nasazení zásady dodržování předpisů uživateli se u jeho zařízení kontroluje dodržování předpisů.

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a potom vyberte **Spravovat nasazení**.
![Snímek stránky zásad dodržování předpisů zobrazující možnosti nabídky Spravovat nasazení v horní části](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  V dialogu **Spravovat nasazení** vyberte jednu nebo více skupin, do kterých chcete zásadu nasadit, a potom vyberte **Přidat** > **OK**.
![Snímek obrazovky dialogového okna Spravovat nasazení](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png). Použijte skupiny služby Active Directory, které už jsou vytvořené a synchronizované s Intune, nebo tyto skupiny vytvořte ručně na konzole služby Intune. Další informace o nasazení zásad najdete v tématu [Nasazení zásady konfigurace](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Pomocí shrnutí stavu a výstrah na stránce **Přehled** v pracovním prostoru **Zásady** můžete identifikovat problémy se zásadami, které vyžadují vaši pozornost. Kromě toho se v pracovním prostoru **Řídicí panel** zobrazí shrnutí stavu.

> [!IMPORTANT]
> Pokud jste zásady dodržování předpisů nenasadili a povolíte zásady podmíněného přístupu Exchange, budou mít všechna cílová zařízení přístup.

## <a name="monitor-the-compliance-policy"></a>Monitorování zásady dodržování předpisů

#### <a name="to-view-devices-that-do-not-conform-to-a-compliance-policy"></a>Zobrazení zařízení, která nesplňují zásady dodržování předpisů

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Skupiny** > **Všechna zařízení**.

2.  Dvakrát klikněte na název zařízení v seznamu zařízení.

3.  Vyberte kartu **Zásady**, na které najdete seznam zásad pro dané zařízení.

4.  V rozevíracím seznamu **Filtry** zvolte **Nevyhovuje zásadám dodržování předpisů**.
![Snímek obrazovky zobrazující seznam možností v seznamu filtrů](./media/intune-sa-3e-view-device-noncompliance.png)

#### <a name="to-view-the-health-attestation-reports"></a>Postup zobrazení sestav Health Attestation

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Sestavy**.

2.  Na stránce **Sestava Health Attestation – Vytvoření nové sestavy** můžete zobrazit sestavu obsahující všechna data ověření stavu Windows 10 shromážděná službou Intune. Pomocí filtrů také můžete vytvořit sestavu obsahující jenom určitou podmnožinu dat. Filtry se můžou týkat typu zařízení, operačního systému nebo jenom určité podmnožiny datových bodů.

## <a name="how-intune-resolves-policy-conflicts"></a>Způsob řešení konfliktů zásad v Intune
Konflikty zásad můžou vzniknout, když se na zařízení použije více zásad Intune. Pokud se nastavení zásad překrývají, vyřeší Intune všechny konflikty s použitím následujících pravidel:

-   Pokud konfliktní nastavení pocházejí ze zásad konfigurace a dodržování předpisů služby Intune, bude mít nastavení v zásadách dodržování předpisů přednost před nastavením v zásadách konfigurace. Platí to i v situaci, kdy je nastavení v zásadách konfigurace bezpečnější.

-   Pokud jste nasadili více zásad dodržování předpisů, použije Intune ty nejbezpečnější z nich.

## <a name="next-steps"></a>Další kroky
Informace o použití zásad dodržování předpisů spolu se zásadami podmíněného přístupu k řízení přístupu ke službám ve vaší organizaci najdete v tématu [Omezení přístupu k e-mailu a službám O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).


### <a name="see-also"></a>Viz taky
[Úvod do zásad dodržování předpisů zařízení v Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md)
