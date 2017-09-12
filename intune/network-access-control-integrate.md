---
title: "Integrace řešení pro řízení přístupu k síti (NAC) do Intune"
titlesuffix: Azure portal
description: "Integrace řešení pro řízení přístupu k síti (NAC) do Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6d75d996f4166fb2a760d1ccb518ca7a228c1a0d
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="network-access-control-nac-integration-with-intune"></a>Integrace řešení pro řízení přístupu k síti (NAC) do Intune

Intune spolupracuje s partnery, kteří řeší přístup k síti, aby organizacím pomohlo zabezpečit firemní data, když se zařízení pokoušejí o přístup k místním prostředkům.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Jak Intune a řešení NAC pomáhají chránit prostředky organizace?

Řešení NAC odpovídají za kontrolu registrace zařízení a stav dodržování předpisů v Intune, aby bylo možné rozhodovat o přístupu. Pokud zařízení není zaregistrované, nebo registrované sice je, ale neodpovídá zásadám dodržování předpisů pro zařízení, musí být přesměrováno do Intune, kde proběhne registrace a/nebo kontrola zařízení z hlediska dodržování předpisů.

### <a name="example"></a>Příklad

Pokud je zařízení zaregistrované a kompatibilní s Intune, mělo by řešení NAC povolit zařízení přístup k prostředkům společnosti. Uživatelům může být třeba povolen nebo zakázán přístup k firemní síti Wi-Fi nebo VPN.

## <a name="nac-and-conditional-access"></a>NAC a podmíněný přístup

Při rozhodování o udělení nebo zakázání přístupu NAC pracuje s podmíněným přístupem.

- Podrobnější informace najdete v článku o [běžných způsobech použití podmíněného přístupu v Intune](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>Jak funguje integrace NAC

Tady je přehled, jak funguje integrace NAC do Intune. První tři kroky vysvětlují postup uvedení do provozu. Jakmile je řešení NAC integrované do Intune, popisují kroky 4–9 nepřetržitý provoz.

![Jak funguje NAC s Intune](./media/ca-intune-common-ways-2.png)

1.  Partnerské řešení NAC zaregistrujte v Azure Active Directory (AAD) a přidělte rozhraní API řešení NAC integrovanému do Intune delegovaná oprávnění.

2.  U partnerského řešení NAC nakonfigurujte příslušná nastavení, včetně adresy URL Intune pro zjišťování.

3.  U partnerského řešení NAC nakonfigurujte ověřování certifikátů.

4.  Uživatel se připojí k firemnímu přístupovému bodu Wi-Fi nebo požádá o připojení k síti VPN.

5.  Partnerské řešení NAC předá informace o zařízení Intune a zeptá se na registraci zařízení a stav dodržování předpisů.

6.  Pokud zařízení neodpovídá nebo není zaregistrované, dá partnerské řešení NAC uživateli pokyn, aby zařízení zaregistroval nebo opravil nedostatky v dodržování předpisů.

7.  Zařízení se znovu pokusí ověřit, jestli vyhovuje předpisům a/nebo je zaregistrované.

8.  Jakmile je zařízení zaregistrované a odpovídá předpisům, dostane partnerské řešení NAC z Intune informaci o stavu.

9.  Připojení se úspěšně naváže, aby zařízení mělo přístup k firemním prostředkům.

## <a name="next-steps"></a>Další kroky

-   [Integrace řešení Cisco ISE do Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)

-   [Integrace řešení Citrix NetScaler do Intune](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)

-   [Integrace řešení HP Aruba Clear Pass do Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
