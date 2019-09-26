---
title: Co je správa aplikací v Microsoft Intune?
titleSuffix: ''
description: Seznamte se s možnostmi správy klientských aplikací podle platformy pro Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 063e78fb716d27843ce017389da7a01f12fee70b
ms.sourcegitcommit: c8cb314256c4896e838918f015ffaefb8f00ace5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/23/2019
ms.locfileid: "71303763"
---
# <a name="what-is-microsoft-intune-app-management"></a>Co je správa aplikací v Microsoft Intune?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako správce IT můžete Microsoft Intune použít ke správě klientských aplikací, které používají pracovníci vaší společnosti. Tato funkce doplňuje správu zařízení a ochranu dat. Jednou z priorit správce je zajistit, aby koncoví uživatelé měli přístup k aplikacím, které potřebují ke své práci. To může být náročné z těchto důvodů:
- Existuje široký sortiment platforem zařízení a typů aplikací.
- Potřebujete spravovat aplikace na firemních zařízeních i na osobních zařízeních uživatelů.
- Musíte zajistit zabezpečení sítě a dat.

Navíc potřebujete přiřazovat a spravovat aplikace na zařízeních, která nejsou zaregistrovaná v Intune.

## <a name="mobile-application-management-mam-basics"></a>Základní informace o správě mobilních aplikací (MAM)

[Správa mobilních aplikací (MAM) Intune](app-lifecycle.md) představuje sadu funkcí Intune pro správu, s kterými můžete publikovat, doručovat, konfigurovat, zabezpečovat, monitorovat a aktualizovat mobilní aplikace pro uživatele.

MAM umožňuje spravovat a chránit data vaší organizace v rámci aplikace. S **mam bez registrace** (MAM-We) je možné spravovat pracovní nebo školní aplikaci, která obsahuje citlivá data, a to téměř na jakémkoli [zařízení](app-management.md#app-management-capabilities-by-platform), včetně osobních zařízení ve scénářích **Přineste si vlastní zařízení** (BYOD). Mnoho kancelářských aplikací, například aplikace Microsoft Office, lze spravovat přes Intune MAM. Podívejte se na oficiální seznam [Microsoft Intune chráněných aplikací](apps-supported-intune-apps.md) , které jsou k dispozici pro veřejné použití.

Intune MAM podporuje dvě konfigurace:
- **Intune MDM + mam**: Správci IT můžou spravovat aplikace pomocí MAM a zásad ochrany aplikací jenom na zařízeních, která jsou zaregistrovaná ve správě mobilních zařízení Intune (MDM). Pokud zákazníci chtějí spravovat aplikace pomocí MDM + MAM, měli by používat konzolu Intune na portálu Azure Portal na https://portal.azure.com.
- **Mam bez registrace zařízení**: MAM bez registrace zařízení nebo MAM-WE umožňuje správcům IT spravovat aplikace pomocí MAM a zásad ochrany aplikací na zařízeních, která nejsou zaregistrovaná v Intune MDM. To znamená, že aplikace je možné spravovat pomocí Intune na zařízeních, která jsou zaregistrovaná u jiných poskytovatelů EMM. Pokud zákazníci chtějí spravovat aplikace pomocí MAM-WE, měli by používat konzolu Intune na portálu Azure Portal na https://portal.azure.com. Aplikace je také možné spravovat pomocí Intune na zařízeních zaregistrovaných pomocí jiných poskytovatelů správy firemních mobilních zařízení (Enterprise Mobility Management (EMM)) nebo na zařízeních vůbec v MDM nezaregistrovaných. Další informace o BYOD a EMS Microsoftu najdete v tématu o [technologických rozhodnutích pro povolení BYOD s Microsoft Enterprise mobility + Security (EMS)](byod-technology-decisions.md).

## <a name="app-management-capabilities-by-platform"></a>Funkce správy aplikací podle platformy

Intune nabízí celou řadu funkcí, které vám pomůžou dostat požadované aplikace na zařízení, na kterých je chcete spouštět. Následující tabulka nabízí souhrn funkcí správy aplikací.

|  | Android/Android Enterprise | iOS | macOS | Windows 10 | Windows Phone 8.1 |
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

<sup>1</sup> Při ochraně aplikací na zařízeních s Windows 10 uvažujte o použití funkce [Windows Information Protection](windows-information-protection-configure.md).<br>
<sup>2</sup> Platí jen pro zařízení spravovaná přes Intune.<br>
<sup>3</sup> Intune podporuje dostupné aplikace ze spravovaného Google Play Storu na zařízeních s Androidem Enterprise.<br>
<sup>4</sup> Intune neposkytuje instalaci zástupce aplikace jako webového odkazu na standardní zařízení s Androidem Enterprise. Podpora webových odkazů je ale k dispozici pro [vyhrazená podniková zařízení s Androidem pro více aplikací](device-restrictions-android-for-work.md#dedicated-device-settings). 


## <a name="get-started"></a>Začínáme

Většinu toho, co souvisí s aplikacemi, najdete v úloze **Klientské aplikace**, ke které se dostanete takto:

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Microsoft Intune** vyberte **Klientské aplikace**.

    ![Podokno úloh Klientské aplikace](./media/apps-workload.png)

Další čtyři části popisují možnosti dostupné v podokně **Klientské aplikace**.

### <a name="manage"></a>Správa
- **Aplikace**: Tuto možnost vyberte, pokud chcete přidat, zobrazit, přiřadit a monitorovat aplikace, které vaše zaměstnanci používají. Další informace naleznete v tématu:
  - [Přidání aplikací](apps-add.md)
  - [Přiřazení aplikací](apps-deploy.md)
  - [Monitorování aplikací](apps-monitor.md)
- **Zásady konfigurace aplikací**: Tuto možnost vyberte, pokud chcete zadat nastavení, která se můžou požadovat, když uživatel spustí aplikaci. Další informace naleznete v tématu:
  - [Zásady konfigurace aplikací pro Intune](app-configuration-policies-overview.md)
    - [Zásady konfigurace aplikací pro iOS](app-configuration-policies-use-ios.md)
    - [Zásady konfigurace aplikací pro Android](app-configuration-policies-use-android.md)
- **Zásady ochrany aplikací**: Tuto možnost vyberte, pokud chcete k aplikaci přidružit nastavení a zajistit ochranu firemních dat, která používá. Můžete například omezit možnosti komunikace aplikace s jinými aplikacemi nebo vyžadovat, aby uživatel při přístupu k firemní aplikaci zadal PIN kód. Další informace naleznete v tématu:
  - [Zásady ochrany aplikací](app-protection-policies.md)
- **Selektivní vymazání aplikace**: Tuto možnost vyberte, pokud chcete ze zařízení vybraného uživatele odebrat jenom firemní data. Další informace naleznete v tématu:
  - [Selektivní vymazání aplikace](apps-selective-wipe.md)
- **Zřizovací profily aplikací pro iOS**: Aplikace pro iOS obsahují zřizovací profil a kód, který je podepsaný certifikátem. Když tomuto certifikátu vyprší platnost, není možné aplikaci spustit. Intune poskytuje nástroje pro proaktivní přiřazení nových zásad zřizovacího profilu k zařízením s aplikacemi, kterým brzy vyprší platnost. Další informace naleznete v tématu:
  - [Zřizovací profily aplikací pro iOS](app-provisioning-profile-ios.md)

Další informace o této části najdete v tématu [Správa aplikací](app-management.md).

### <a name="monitor"></a>Monitorování
- **Licence k aplikacím**: Zobrazit, přiřadit a monitorovat aplikace hromadně zakoupené v obchodech s aplikacemi. Další informace naleznete v tématu:
  - [Aplikace programu hromadných nákupů pro iOS](vpp-apps-ios.md)
  - [Aplikace hromadně zakoupené v Microsoft Storu pro firmy](windows-store-for-business.md)
- **Zjištěné aplikace**: Zobrazení aplikací, které byly přiřazeny přes Intune nebo nainstalované na zařízení. Další informace najdete v tématu [zjištěné aplikace Intune](app-discovered-apps.md).
- **Stav instalace aplikace**: Zobrazte stav přiřazení aplikace, které jste vytvořili. Další informace najdete v článku [Monitorování informací a přiřazení aplikace pomocí Microsoft Intune](apps-monitor.md#device-and-user-status-graphs).
- **Stav ochrany aplikace**: Zobrazuje stav zásad ochrany aplikací pro uživatele, kterého jste vybrali.
- **Protokoly auditu**: Zobrazit činnost všech správců IT v rámci aplikace Intune

Další informace o této části najdete v tématu [Monitorování aplikací](apps-monitor.md).

### <a name="set-up"></a>Nastavení
- **tokeny VPP pro iOS**: Použijte a zobrazte si licence VPP (Volume purchase program) pro iOS. Další informace naleznete v tématu:
  - [hromadně zakoupené aplikace pro iOS](vpp-apps-ios.md)
- **Certifikát Windows Enterprise**: Použijte nebo zobrazte stav certifikátu pro podepisování kódu, který se používá k distribuci obchodních aplikací do spravovaných zařízení s Windows.
- **Certifikát Windows Symantec**: Použijte nebo zobrazte stav certifikátu Symantec pro podepisování kódu, který je nutný k distribuci souborů appx XAP a WP8. x na zařízení s Windows 10 Mobile.
- **Microsoft Store pro firmy**: Nastavte integraci na Microsoft Store pro firmy. Potom můžete zakoupené aplikace synchronizovat s Intune, přiřazovat je a sledovat využití licencí. Další informace naleznete v tématu:
  - [Aplikace hromadně zakoupené v Microsoft Storu pro firmy](windows-store-for-business.md)
- **Klíče pro zkušební načtení ze strany systému Windows**: Přidejte klíč pro instalaci ze strany Windows, který se dá použít k instalaci aplikace přímo do zařízení, a ne publikování a stažení aplikace z Windows Storu. Další informace naleznete v tématu:
  - [Instalace aplikace pro Windows bokem](app-sideload-windows.md)
- **Portál společnosti branding**: Přizpůsobte Portál společnosti, abyste mu poskytovali značku vaší společnosti. Další informace naleznete v tématu:
  - [Konfigurace Portálu společnosti](company-portal-app.md)
- **Kategorie aplikací**: Přidat, připnout a odstranit názvy kategorií aplikací.
- **Pracovní profil Androidu**: Schvalte a synchronizujte aplikace, které jste schválili pro váš podnik. Další informace naleznete v tématu:
  - [Aplikace v pracovním profilu Androidu](apps-add-android-for-work.md)

### <a name="help-and-support"></a>Nápověda a podpora
- **Pomoc a podpora**: Vyřešte potíže, požádejte o podporu nebo zobrazte stav Intune. Další informace naleznete v tématu:
  - [Odstraňování potíží](help-desk-operators.md)

## <a name="next-steps"></a>Další kroky

- [Přidání aplikace do Microsoft Intune](apps-add.md)
