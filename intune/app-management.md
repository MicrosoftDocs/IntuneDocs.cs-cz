---
title: Co je správa aplikací v Microsoft Intune?
titlesuffix: ''
description: Naučte se základy správy aplikací pomocí Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/20/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aebfea2f52540b4193811121334e3cebf916175b
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/31/2018
ms.locfileid: "43330139"
---
# <a name="what-is-microsoft-intune-app-management"></a>Co je správa aplikací v Microsoft Intune?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako správce IT můžete Microsoft Intune použít ke správě mobilních aplikací, které používají pracovníci vaší společnosti. Tato funkce doplňuje správu zařízení a ochranu dat. Jednou z priorit správce je zajistit, aby koncoví uživatelé měli přístup k aplikacím, které potřebují ke své práci. To může být náročné z těchto důvodů:
- Existuje široký sortiment platforem zařízení a typů aplikací.
- Potřebujete spravovat aplikace na firemních zařízeních i na osobních zařízeních uživatelů.
- Musíte zajistit zabezpečení sítě a dat.

Navíc potřebujete přiřazovat a spravovat aplikace na zařízeních, která nejsou zaregistrovaná v Intune.

Intune nabízí celou řadu funkcí, které vám pomůžou dostat požadované aplikace na zařízení, na kterých je chcete spouštět. Následující tabulka nabízí souhrn funkcí správy aplikací: 

## <a name="app-management-capabilities-by-platform"></a>Funkce správy aplikací podle platformy

|  | Android | iOS | macOS | Windows 10 | Windows Phone 8.1 |
|-------------------------------------------------------------------------------------|---------|-----|-------|------------|-------------------|
| Přidání a přiřazení aplikací k zařízením a uživatelům | Ano | Ano | Ano | Ano | Ano |
| Přiřazení aplikací k zařízením nezaregistrovaným v Intune | Ano | Ano | Ne | Ne | Ne |
| Určení chování aplikací při spuštění pomocí zásad konfigurace aplikací | Ne | Ano | Ne | Ne | Ne |
| Obnovení aplikací s vypršelou platností pomocí zásad zřizování mobilních aplikací | Ne | Ano | Ne | Ne | Ne |
| Ochrana firemních dat v aplikacích pomocí zásad ochrany aplikací | Ano | Ano | Ne | Ne1 | Ne |
| Odebrání pouze firemních dat z nainstalovaných aplikací (selektivní vymazání aplikací) | Ano | Ano | Ne | Ano | Ano |
| Monitorování přiřazení aplikací | Ano | Ano | Ano | Ano | Ano |
| Přiřazení a sledování aplikací hromadně zakoupených v obchodu s aplikacemi | Ne | Ne | Ne | Ano | Ne |
| Nařízená instalace aplikací na zařízení (povinná)2 | Ano | Ano | Ano | Ano | Ano |
| Nepovinná instalace na zařízení z Portálu společnosti (dostupná instalace) | Ano | Ano | Ano | Ano | Ano |
| Zástupce pro instalaci aplikace na webu (webový odkaz) | Ano | Ano | Ano | Ano | Ano |
| Vlastní (obchodní) aplikace | Ano | Ano | Ano | Ano | Ne |
| Aplikace z obchodu | Ano | Ano | Ne | Ano | Ano |
| Aktualizace aplikací | Ano | Ano | Ne | Ano | Ano |

<sup>1</sup> Při ochraně aplikací na zařízeních s Windows 10 uvažujte o použití funkce [Windows Information Protection](windows-information-protection-configure.md).

<sup>2</sup> Platí jen pro zařízení spravovaná přes Intune.

## <a name="get-started"></a>Začínáme

Většinu toho, co souvisí s aplikacemi, najdete v úloze **Klientské aplikace**, ke které se dostanete takto:

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**.  
    Intune se nachází v části **Monitorování a správa**.
3. V podokně **Microsoft Intune** vyberte **Klientské aplikace**.

    ![Podokno úloh Mobilní aplikace](./media/apps-workload.png)

Další čtyři části popisují možnosti dostupné v podokně **Klientské aplikace**.

### <a name="manage"></a>Správa
- **Aplikace**: Tuto možnost vyberte pro přidávání, zobrazení, přiřazování a monitorování aplikací používaných vašimi pracovníky. Více informací najdete v následujících tématech:
    - [Přidání aplikací](apps-add.md)
    - [Přiřazení aplikací](apps-deploy.md)
    - [Monitorování aplikací](apps-monitor.md)
- **Zásady konfigurace aplikací**: Tuto možnost vyberte k poskytování nastavení, která se můžou požadovat, když uživatel spustí aplikaci. Více informací najdete v následujících tématech:
    - [Zásady konfigurace aplikací pro Intune](app-configuration-policies-overview.md)
        - [Zásady konfigurace aplikací pro iOS](app-configuration-policies-use-ios.md)
        - [Zásady konfigurace aplikací pro Android](app-configuration-policies-use-android.md)
- **Zásady ochrany aplikací**: Tuto možnost vyberte, pokud chcete aplikaci přidružit nastavení pomáhající chránit firemní data, která tato aplikace používá. Můžete například omezit možnosti komunikace aplikace s jinými aplikacemi nebo vyžadovat, aby uživatel při přístupu k firemní aplikaci zadal PIN kód. Více informací najdete v následujících tématech:
    - [Zásady ochrany aplikací](app-protection-policies.md)
- **Selektivní vymazání aplikace**: Tuto možnost vyberte, pokud chcete odebrat pouze firemní data z vybraného zařízení uživatele. Více informací najdete v následujících tématech:
    - [Selektivní vymazání aplikace](apps-selective-wipe.md)
- **Zřizovací profily aplikací pro iOS**: Aplikace pro iOS obsahují zřizovací profil a kód, který je podepsaný certifikátem. Když tomuto certifikátu vyprší platnost, není možné aplikaci spustit. Intune poskytuje nástroje pro proaktivní přiřazení nových zásad zřizovacího profilu k zařízením s aplikacemi, kterým brzy vyprší platnost. Více informací najdete v následujících tématech:
    - [Zřizovací profily aplikací pro iOS](app-provisioning-profile-ios.md)

Další informace o této části najdete v tématu [Správa aplikací](app-management.md).

### <a name="monitor"></a>Monitorování
- **Licence aplikací**: Tady můžete zobrazit, přiřadit a monitorovat aplikace hromadně zakoupené v obchodech s aplikacemi. Více informací najdete v následujících tématech:
    - [Aplikace programu hromadných nákupů pro iOS](vpp-apps-ios.md)
    - [Aplikace hromadně zakoupené v Microsoft Storu pro firmy](windows-store-for-business.md)
- **Zjištěné aplikace**: Tady můžete zobrazit všechny aplikace přiřazené přes Intune a nainstalované v zařízení. Další informace najdete v článku [Monitorování informací a přiřazení aplikace pomocí Microsoft Intune](apps-monitor.md#device-and-user-status-graphs).
- **Stav instalace aplikace**: Tady můžete zobrazit stav vytvořeného přiřazení aplikace. Další informace najdete v článku [Monitorování informací a přiřazení aplikace pomocí Microsoft Intune](apps-monitor.md#device-and-user-status-graphs).
- **Stav ochrany aplikací**: Tady můžete zobrazit stav zásad ochrany aplikací pro vámi vybraného uživatele.
- **Protokoly auditu**: Tady můžete zobrazit aktivity všech správců IT související s aplikacemi v Intune.

Další informace o této části najdete v tématu [Monitorování aplikací](apps-monitor.md).

### <a name="set-up"></a>Nastavení
- **Tokeny VPP pro iOS**: Tady můžete použít a zobrazit licence programu VPP (Volume Purchase Program) pro iOS. Více informací najdete v následujících tématech:
    - [Multilicenční aplikace pro iOS](vpp-apps-ios.md)
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
    - [Odstraňování potíží](help-desk-operators.md)

## <a name="next-steps"></a>Další kroky

- [Přidání aplikace do Microsoft Intune](apps-add.md)
