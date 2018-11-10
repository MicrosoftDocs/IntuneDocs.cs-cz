---
title: Integrace řešení pro řízení přístupu k síti (NAC) do Microsoft Intune – Azure | Microsoft Docs
description: Řešení pro řízení přístupu k síti (NAC) kontrolují u zařízení s Intune stav registrace a dodržování předpisů. Řešení NAC zahrnují určitá chování a pracují s podmíněným přístupem. Prohlédněte si postup, který vám pomůže začít je využívat, a seznam partnerských řešení.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e1adfdba49ab8ac5ae55f792e71a99f4aef4c8a6
ms.sourcegitcommit: 5c2a70180cb69049c73c9e55d36a51e9d6619049
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2018
ms.locfileid: "50236148"
---
# <a name="network-access-control-nac-integration-with-intune"></a>Integrace řešení pro řízení přístupu k síti (NAC) do Intune

Intune spolupracuje s partnery, kteří řeší přístup k síti, aby organizacím pomohlo zabezpečit firemní data, když se zařízení pokoušejí o přístup k místním prostředkům.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Jak Intune a řešení NAC pomáhají chránit prostředky organizace?

Řešení NAC kontrolují registrace zařízení a stav dodržování předpisů v Intune a podporují tak rozhodování o přístupu. Pokud zařízení není zaregistrované, nebo je zaregistrované, ale neodpovídá zásadám dodržování předpisů Intune, musí být přesměrováno do Intune, kde proběhne jeho registrace nebo kontrola z hlediska dodržování předpisů.

### <a name="example"></a>Příklad

Pokud je zařízení zaregistrované a kompatibilní s Intune, mělo by řešení NAC povolit zařízení přístup k prostředkům společnosti. Uživatelům může být třeba povolen nebo zakázán přístup k firemní síti Wi-Fi nebo VPN.

## <a name="feature-behaviors"></a>Chování funkce

Zařízení, která se aktivně synchronizují do Intune, nemohou přejít ze stavu **Vyhovující předpisům** / **Nevyhovující předpisům** do stavu **Nesynchronizované** (nebo **Neznámé**). Stav **Neznámé** je rezervovaný pro nově registrovaná zařízení, u kterých ještě neproběhla kontrola dodržování předpisů.

Pokud mají zařízení zablokovaný přístup k prostředkům, musí blokační služba přesměrovat všechny uživatele na [portál pro správu](https://portal.manage.microsoft.com), aby bylo možné zjistit důvod zablokování zařízení.  Když uživatelé tuto stránku navštíví, zároveň se znovu vyhodnotí, zda zařízení dodržuje předpisy.

## <a name="nac-and-conditional-access"></a>NAC a podmíněný přístup

Řízení přístupu k síti (NAC) funguje s podmíněným přístupem při rozhodování o řízení přístupu. Podrobnější informace najdete v článku o [nejčastějších způsobech použití podmíněného přístupu v Intune](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>Jak funguje integrace NAC

Následující seznam obsahuje přehled fungování řešení pro řízení přístupu k síti (NAC) při integraci do Intune. První tři kroky (1–3) vysvětlují proces připojování. Kroky 4–9 popisují další provoz řešení NAC po jeho integraci do Intune.

![Jak funguje NAC s Intune](./media/ca-intune-common-ways-2.png)

1. Partnerské řešení NAC zaregistrujte v Azure Active Directory (AAD) a přidělte rozhraní API řešení NAC integrovanému do Intune delegovaná oprávnění.
2. U partnerského řešení NAC nakonfigurujte příslušná nastavení, včetně adresy URL Intune pro zjišťování.
3. U partnerského řešení NAC nakonfigurujte ověřování certifikátů.
4. Uživatel se připojí k firemnímu přístupovému bodu Wi-Fi nebo požádá o připojení k síti VPN.
5. Partnerské řešení NAC předá informace o zařízení Intune a zeptá se na registraci zařízení a stav dodržování předpisů.
6. Pokud zařízení nedodržuje předpisy nebo není zaregistrované, dá partnerské řešení NAC uživateli pokyn, aby zařízení zaregistroval nebo opravil nedostatky v dodržování předpisů.
7. Ve vhodný okamžik se zařízení pokusí znovu ověřit dodržování předpisů a stav registrace.
8. Jakmile je zařízení zaregistrované a odpovídá předpisům, dostane partnerské řešení NAC z Intune informaci o stavu.
9. Připojení se úspěšně naváže, aby zařízení mělo přístup k firemním prostředkům.

## <a name="use-nac-on-your-ios-devices"></a>Použití řešení NAC u zařízení s iOSem

Řízení přístupu k síti není momentálně podporované u následujících klientů VPN v iOSu:
-   Cisco AnyConnect
-   F5 Access
-   Citrix SSO  

Ve spolupráci s našimi partnery se chystáme vydat řešení NAC pro tyto novější klienty. Až budou tato řešení připravená, aktualizujeme tento článek o další podrobnosti. 


## <a name="next-steps"></a>Další kroky

- [Integrace řešení Cisco ISE do Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)
- [Integrace řešení Citrix NetScaler do Intune](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)
- [Integrace řešení HP Aruba ClearPass do Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=31271)
- [Integrace řešení secRMM (Squadra security Removable Media Manager) do Intune](http://www.squadratechnologies.com/StaticContent/ProductDownload/secRMM/9.9.0.0/secRMMIntuneAccessControlSetupGuide.pdf)
