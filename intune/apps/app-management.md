---
title: Co je správa aplikací v Microsoft Intune?
titleSuffix: ''
description: Seznamte se s možnostmi správy klientských aplikací podle platformy pro Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/27/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: c22fafce6583dd1e58d61e3fa8e6077b70998588
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77781781"
---
# <a name="what-is-microsoft-intune-app-management"></a>Co je správa aplikací v Microsoft Intune?


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Jako správce IT můžete Microsoft Intune použít ke správě klientských aplikací, které používají pracovníci vaší společnosti. Tato funkce doplňuje správu zařízení a ochranu dat. Jednou z priorit správce je zajistit, aby koncoví uživatelé měli přístup k aplikacím, které potřebují ke své práci. To může být náročné z těchto důvodů:
- Existuje široký sortiment platforem zařízení a typů aplikací.
- Potřebujete spravovat aplikace na firemních zařízeních i na osobních zařízeních uživatelů.
- Musíte zajistit zabezpečení sítě a dat.

Navíc potřebujete přiřazovat a spravovat aplikace na zařízeních, která nejsou zaregistrovaná v Intune.

## <a name="mobile-application-management-mam-basics"></a>Základní informace o správě mobilních aplikací (MAM)

[Správa mobilních aplikací (MAM) Intune](app-lifecycle.md) představuje sadu funkcí Intune pro správu, s kterými můžete publikovat, doručovat, konfigurovat, zabezpečovat, monitorovat a aktualizovat mobilní aplikace pro uživatele.

MAM umožňuje spravovat a chránit data vaší organizace v rámci aplikace. S **mam bez registrace** (MAM-We) je možné spravovat pracovní nebo školní aplikaci, která obsahuje citlivá data, a to téměř na jakémkoli [zařízení](app-management.md#app-management-capabilities-by-platform), včetně osobních zařízení ve scénářích **Přineste si vlastní zařízení** (BYOD). Mnoho kancelářských aplikací, například aplikace Microsoft Office, lze spravovat přes Intune MAM. Podívejte se na oficiální seznam [Microsoft Intune chráněných aplikací](apps-supported-intune-apps.md) , které jsou k dispozici pro veřejné použití.

Intune MAM podporuje dvě konfigurace:
- **MDM+MAM Intune**: Správci IT můžou spravovat aplikace pomocí MAM a zásad ochrany aplikací jenom na zařízeních, která jsou zaregistrovaná ve správě mobilních zařízení (MDM) Intune. Pokud zákazníci chtějí spravovat aplikace pomocí MDM + MAM, měli by používat konzolu Intune na portálu Azure Portal na https://portal.azure.com.
- **MAM bez registrace zařízení:** MAM bez registrace zařízení, neboli MAM-WE, umožňuje správcům IT spravovat aplikace pomocí MAM a zásad ochrany aplikací na zařízeních, která nejsou zaregistrovaná ve správě mobilních zařízení Intune. To znamená, že aplikace je možné spravovat pomocí Intune na zařízeních, která jsou zaregistrovaná u jiných poskytovatelů EMM. Pokud zákazníci chtějí spravovat aplikace pomocí MAM-WE, měli by používat konzolu Intune na portálu Azure Portal na https://portal.azure.com. Aplikace je také možné spravovat pomocí Intune na zařízeních zaregistrovaných pomocí jiných poskytovatelů správy firemních mobilních zařízení (Enterprise Mobility Management (EMM)) nebo na zařízeních vůbec v MDM nezaregistrovaných. Další informace o BYOD a EMS Microsoftu najdete v tématu o [technologických rozhodnutích pro povolení BYOD s Microsoft Enterprise mobility + Security (EMS)](../fundamentals/byod-technology-decisions.md).

## <a name="app-management-capabilities-by-platform"></a>Funkce správy aplikací podle platformy

Intune nabízí celou řadu funkcí, které vám pomůžou dostat požadované aplikace na zařízení, na kterých je chcete spouštět. Následující tabulka nabízí souhrn funkcí správy aplikací.

|  | Android/Android Enterprise | iOS/iPadOS | macOS | Windows 10 | Wvdows Phone 8.1 |
|-------------------------------------------------------------------------------------|---------|-----|-------|------------|-------------------|
| Přidání a přiřazení aplikací k zařízením a uživatelům | Ano | Ano | Ano | Ano | Ano |
| Přiřazení aplikací k zařízením nezaregistrovaným v Intune | Ano | Ano | Ne | Ne | Ne |
| Určení chování aplikací při spuštění pomocí zásad konfigurace aplikací | Ano | Ano | Ne | Ne | Ne |
| Obnovení aplikací s vypršelou platností pomocí zásad zřizování mobilních aplikací | Ne | Ano | Ne | Ne | Ne |
| Ochrana firemních dat v aplikacích pomocí zásad ochrany aplikací | Ano | Ano | Ne | Ne <sup>1</sup> | Ne |
| Odebrání pouze firemních dat z nainstalovaných aplikací (selektivní vymazání aplikací) | Ano | Ano | Ne | Ano | Ano |
| Monitorování přiřazení aplikací | Ano | Ano | Ano | Ano | Ano |
| Přiřazení a sledování aplikací hromadně zakoupených v obchodu s aplikacemi | Ne | Ne | Ne | Ano | Ne |
| Povinná instalace aplikací na zařízení (povinné) <sup>2</sup> | Ano | Ano | Ano | Ano | Ano |
| Nepovinná instalace na zařízení z Portálu společnosti (dostupná instalace) | Ano <sup>3</sup> | Ano | Ano | Ano | Ano |
| Zástupce pro instalaci aplikace na webu (webový odkaz) | Ano <sup>4</sup> | Ano | Ano | Ano | Ano |
| Vlastní (obchodní) aplikace | Ano | Ano | Ano | Ano | Ne |
| Aplikace z obchodu | Ano | Ano | Ne | Ano | Ano |
| Aktualizace aplikací | Ano | Ano | Ne | Ano | Ano |

<sup>1</sup> Při ochraně aplikací na zařízeních s Windows 10 uvažujte o použití funkce [Windows Information Protection](../protect/windows-information-protection-configure.md).<br>
<sup>2</sup> Platí jen pro zařízení spravovaná přes Intune.<br>
<sup>3</sup> Intune podporuje dostupné aplikace ze spravovaného Google Play Storu na zařízeních s Androidem Enterprise.<br>
<sup>4</sup> Intune neposkytuje instalaci zástupce aplikace jako webového odkazu na standardní zařízení s Androidem Enterprise. Podpora webových odkazů je ale k dispozici pro [vyhrazená podniková zařízení s Androidem pro více aplikací](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings). 


## <a name="get-started"></a>Začínáme

Většinu informací týkajících se aplikací najdete v úloze **aplikace** , ke kterým máte přístup pomocí následujících kroků:

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Vyberte **aplikace**.

    ![Podokno úloh aplikace](./media/app-management/apps-workload.png)

Následující čtyři části popisují možnosti, které jsou k dispozici v podokně **aplikace** .

### <a name="manage"></a>Správa
- **Aplikace**: Tuto možnost vyberte pro přidávání, zobrazení, přiřazování a monitorování aplikací používaných vašimi pracovníky. Více informací najdete v následujících tématech:
  - [Přidání aplikací](apps-add.md)
  - [Přiřazení aplikací](apps-deploy.md)
  - [Monitorování aplikací](apps-monitor.md)
- **Zásady konfigurace aplikací**: Tuto možnost vyberte k poskytování nastavení, která se můžou požadovat, když uživatel spustí aplikaci. Více informací najdete v následujících tématech:
  - [Zásady konfigurace aplikací pro Intune](app-configuration-policies-overview.md)
    - [zásady konfigurace aplikací pro iOS/iPadOS](app-configuration-policies-use-ios.md)
    - [Zásady konfigurace aplikací pro Android](app-configuration-policies-use-android.md)
- **Zásady ochrany aplikací**: Tuto možnost vyberte, pokud chcete aplikaci přidružit nastavení pomáhající chránit firemní data, která tato aplikace používá. Můžete například omezit možnosti komunikace aplikace s jinými aplikacemi nebo vyžadovat, aby uživatel při přístupu k firemní aplikaci zadal PIN kód. Více informací najdete v následujících tématech:
  - [Zásady ochrany aplikací](app-protection-policies.md)
- **Selektivní vymazání aplikace**: Tuto možnost vyberte, pokud chcete odebrat pouze firemní data z vybraného zařízení uživatele. Více informací najdete v následujících tématech:
  - [Selektivní vymazání aplikace](apps-selective-wipe.md)
- **zřizovací profily aplikací pro iOS**: aplikace pro iOS/iPadOS obsahují zřizovací profil a kód, který je podepsaný certifikátem. Když tomuto certifikátu vyprší platnost, není možné aplikaci spustit. Intune poskytuje nástroje pro proaktivní přiřazení nových zásad zřizovacího profilu k zařízením s aplikacemi, kterým brzy vyprší platnost. Více informací najdete v následujících tématech:
  - [profily zřizování aplikací pro iOS/iPadOS](app-provisioning-profile-ios.md).

Další informace o této části najdete v tématu [Správa aplikací](app-management.md).

### <a name="monitor"></a>Monitorování
- **Licence aplikací**: Tady můžete zobrazit, přiřadit a monitorovat aplikace hromadně zakoupené v obchodech s aplikacemi. Více informací najdete v následujících tématech:
  - [aplikace programu hromadných nákupů pro iOS/iPadOS (VPP)](vpp-apps-ios.md)
  - [Aplikace hromadně zakoupené v Microsoft Storu pro firmy](windows-store-for-business.md)
- **Zjištěné aplikace:** Můžete zobrazit aplikace přiřazené z Intune nebo nainstalované v zařízení. Další informace najdete v tématu [zjištěné aplikace Intune](app-discovered-apps.md).
- **Stav instalace aplikace**: Tady můžete zobrazit stav vytvořeného přiřazení aplikace. Další informace najdete v článku [Monitorování informací a přiřazení aplikace pomocí Microsoft Intune](apps-monitor.md#device-and-user-status-graphs).
- **Stav ochrany aplikací**: Tady můžete zobrazit stav zásad ochrany aplikací pro vámi vybraného uživatele.
- **Protokoly auditu**: Tady můžete zobrazit aktivity všech správců IT související s aplikacemi v Intune.

Další informace o této části najdete v tématu [Monitorování aplikací](apps-monitor.md).

### <a name="set-up"></a>Nastavení
- **tokeny VPP pro iOS**: použijte a zobrazte licence pro iOS/IPadOS Volume purchase program (VPP). Více informací najdete v následujících tématech:
  - [hromadně zakoupené aplikace pro iOS/iPadOS](vpp-apps-ios.md)
- **Certifikát Windows Enterprise**: Tady můžete použít nebo zobrazit stav certifikátu pro podepisování kódu, který se používá k distribuci obchodních aplikací do spravovaných zařízení s Windows.
- **Certifikát Windows Symantec**: Tady můžete použít nebo zobrazit stav certifikátu Symantec pro podepisování kódu, který je nutný k distribuci souborů appx pro XAP a WP8.x na zařízení s Windows 10 Mobile.
- **Microsoft Store pro firmy**: Tady můžete nastavit integraci do Microsoft Storu pro firmy. Potom můžete zakoupené aplikace synchronizovat s Intune, přiřazovat je a sledovat využití licencí. Více informací najdete v následujících tématech:
  - [Aplikace hromadně zakoupené v Microsoft Storu pro firmy](windows-store-for-business.md)
- **Klíče pro instalaci bokem ve Windows**: Přidejte klíč pro instalaci bokem ve Windows, který lze použít k instalaci aplikace přímo do zařízení (místo publikování aplikace a jejího stahování z Windows Storu). Více informací najdete v následujících tématech:
  - [Instalace aplikace pro Windows bokem](app-sideload-windows.md)
- **Značky Portálu společnosti**: Portál společnosti můžete přizpůsobit o značku své firmy. Více informací najdete v následujících tématech:
  - [Konfigurace Portálu společnosti](company-portal-app.md)
- **Kategorie aplikací**: Tady můžete přidat, připnout a odstranit názvy kategorií aplikací.
- **Pracovní profil Androidu**: Tady můžete schválit a synchronizovat aplikace schválené pro váš podnik. Více informací najdete v následujících tématech:
  - [Aplikace v pracovním profilu Androidu](apps-add-android-for-work.md)

### <a name="help-and-support"></a>Nápověda a podpora
- **Nápověda a podpora**: Tady můžete řešit potíže, požádat o podporu nebo zobrazit stav Intune. Více informací najdete v následujících tématech:
  - [Odstraňování potíží](../fundamentals/help-desk-operators.md)

## <a name="next-steps"></a>Další kroky

- [Přidání aplikace do Microsoft Intune](apps-add.md)
