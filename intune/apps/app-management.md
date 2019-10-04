---
title: Co je Správa aplikací v Microsoft Intune?
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
ms.openlocfilehash: 8b630709646b2f4489cbfea6284689c9436798ca
ms.sourcegitcommit: 78f9750712c254d8b123ef15b74f30ca999aa128
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/03/2019
ms.locfileid: "71916347"
---
# <a name="what-is-microsoft-intune-app-management"></a>Co je Správa aplikací Microsoft Intune?


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Jako správce IT můžete použít Microsoft Intune ke správě klientských aplikací, které používají zaměstnanci vaší společnosti. Tato funkce je navíc ke správě zařízení a ochraně dat. Jednou z priorit správce je zajistit, aby koncoví uživatelé měli přístup k aplikacím, které potřebují ke své práci. Tento cíl může být problematický z těchto důvodů:
- Existuje široké spektrum platforem zařízení a typů aplikací.
- Je možné, že budete muset spravovat aplikace na osobních zařízeních i v zařízeních uživatelů.
- Musíte zajistit, aby vaše síť a data zůstaly zabezpečené.

Kromě toho můžete chtít přiřadit a spravovat aplikace na zařízeních, která nejsou zaregistrovaná v Intune.

## <a name="mobile-application-management-mam-basics"></a>Základní informace o správě mobilních aplikací (MAM)

[Správa mobilních aplikací Intune](app-lifecycle.md) odkazuje na sadu funkcí správy Intune, které vám umožní publikovat, doručovat, konfigurovat, zabezpečovat, monitorovat a aktualizovat mobilní aplikace pro vaše uživatele.

MAM umožňuje spravovat a chránit data vaší organizace v rámci aplikace. S **mam bez registrace** (MAM-We) je možné spravovat pracovní nebo školní aplikaci, která obsahuje citlivá data, a to téměř na jakémkoli [zařízení](app-management.md#app-management-capabilities-by-platform), včetně osobních zařízení ve scénářích **Přineste si vlastní zařízení** (BYOD). Mnoho kancelářských aplikací, jako jsou systém Microsoft Office aplikace, je možné spravovat pomocí Intune MAM. Podívejte se na oficiální seznam [Microsoft Intune chráněných aplikací](apps-supported-intune-apps.md) , které jsou k dispozici pro veřejné použití.

Intune MAM podporuje dvě konfigurace:
- **Intune MDM + mam**: Správci IT můžou spravovat jenom aplikace využívající mam a zásady ochrany aplikací na zařízeních, která jsou zaregistrovaná ve správě mobilních zařízení (MDM) Intune. Pokud zákazníci chtějí spravovat aplikace pomocí MDM + MAM, měli by používat konzolu Intune v Azure Portal na https://portal.azure.com.
- **Mam bez registrace zařízení**: mam bez registrace zařízení nebo mam-We umožňuje správcům IT spravovat aplikace pomocí mam a zásad ochrany aplikací na zařízeních, která nejsou zaregistrovaná v Intune MDM. To znamená, že aplikace je možné spravovat pomocí Intune na zařízeních zaregistrovaných s poskytovateli EMM třetích stran. Pokud chcete spravovat aplikace pomocí MAM-WE, zákazníci by měli používat konzolu Intune v Azure Portal na https://portal.azure.com. Aplikace je také možné spravovat pomocí Intune na zařízeních zaregistrovaných s poskytovateli správy podnikových mobilních zařízení (EMM) od jiných výrobců, nebo nejsou zaregistrovaná ve službě MDM. Další informace o BYOD a EMS Microsoftu najdete v tématu o [technologických rozhodnutích pro povolení BYOD s Microsoft Enterprise mobility + Security (EMS)](../fundamentals/byod-technology-decisions.md).

## <a name="app-management-capabilities-by-platform"></a>Možnosti správy aplikací podle platformy

Intune nabízí řadu funkcí, které vám pomůžou získat aplikace, které potřebujete, na zařízeních, na kterých je chcete spouštět. Následující tabulka nabízí Souhrn funkcí správy aplikací.

|  | Android/Android Enterprise | iOS | macOS | Windows 10 | Windows Phone 8,1 |
|-------------------------------------------------------------------------------------|---------|-----|-------|------------|-------------------|
| Přidávání a přiřazování aplikací k zařízením a uživatelům | Ano | Ano | Ano | Ano | Ano |
| Přiřazení aplikací k zařízením, která nejsou zaregistrovaná v Intune | Ano | Ano | Ne | Ne | Ne |
| Použití zásad konfigurace aplikací k řízení chování při spouštění aplikací | Ano | Ano | Ne | Ne | Ne |
| Obnovení aplikací s vypršenou platností pomocí zásad zřizování mobilních aplikací | Ne | Ano | Ne | Ne | Ne |
| Ochrana firemních dat v aplikacích pomocí zásad ochrany aplikací | Ano | Ano | Ne | Ne <sup>1</sup> | Ne |
| Odebrání pouze firemních dat z nainstalované aplikace (selektivní vymazání aplikace) | Ano | Ano | Ne | Ano | Ano |
| Monitorování přiřazení aplikací | Ano | Ano | Ano | Ano | Ano |
| Přiřazení a sledování hromadně zakoupených aplikací z App Storu | Ne | Ne | Ne | Ano | Ne |
| Povinná instalace aplikací na zařízení (povinné) <sup>2</sup> | Ano | Ano | Ano | Ano | Ano |
| Volitelná instalace na zařízeních z Portál společnosti (dostupná instalace) | Ano <sup>3</sup> | Ano | Ano | Ano | Ano |
| Instalace zástupce na aplikaci na webu (webový odkaz) | Ano <sup>4</sup> | Ano | Ano | Ano | Ano |
| Interní (obchodní) aplikace | Ano | Ano | Ano | Ano | Ne |
| Aplikace ze Storu | Ano | Ano | Ne | Ano | Ano |
| Aktualizovat aplikace | Ano | Ano | Ne | Ano | Ano |

<sup>1</sup> zvažte použití [Information Protection Windows](../protect/windows-information-protection-configure.md) k ochraně aplikací na zařízeních s Windows 10.<br>
<sup>2</sup> platí jenom pro zařízení spravovaná přes Intune.<br>
<sup>3</sup> Intune podporuje dostupné aplikace ze spravovaného Google Play Storu na zařízeních s Androidem Enterprise.<br>
<sup>4</sup> Intune neposkytuje instalaci zástupce aplikace jako webového odkazu na standardní zařízení s Androidem Enterprise. Podpora webových odkazů je ale k dispozici pro [vyhrazená podniková zařízení s Androidem pro více aplikací](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings). 


## <a name="get-started"></a>Začínáme

Většinu informací o aplikacích můžete najít v úloze **klientských aplikací** , ke které máte přístup pomocí následujících kroků:

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Microsoft Intune** vyberte **klientské aplikace**.

    ![Podokno úloh klientské aplikace](./media/app-management/apps-workload.png)

Následující čtyři části popisují možnosti, které jsou k dispozici v podokně **klientské aplikace** .

### <a name="manage"></a>Správy
- **Aplikace**: tuto možnost vyberte, pokud chcete přidat, zobrazit, přiřadit a monitorovat aplikace, které vaše zaměstnanci používají. Další informace naleznete v tématu:
  - [Přidejte aplikace](apps-add.md).
  - [Přiřaďte aplikace](apps-deploy.md).
  - [Monitorujte aplikace](apps-monitor.md).
- **Zásady konfigurace aplikací**: tuto možnost vyberte, pokud chcete zadat nastavení, která se můžou požadovat, když uživatel spustí aplikaci. Další informace naleznete v tématu:
  - [Zásady konfigurace aplikací pro Intune](app-configuration-policies-overview.md)
    - [zásady konfigurace aplikací pro iOS](app-configuration-policies-use-ios.md)
    - [Zásady konfigurace aplikací pro Android](app-configuration-policies-use-android.md).
- **Zásady ochrany aplikací**: tuto možnost vyberte, pokud chcete k aplikaci přidružit nastavení a zajistit ochranu firemních dat, která používá. Můžete například omezit možnosti komunikace aplikace s jinými aplikacemi nebo může vyžadovat, aby uživatel zadal PIN pro přístup k aplikaci společnosti. Další informace naleznete v tématu:
  - [Zásady ochrany aplikací](app-protection-policies.md).
- **Selektivní vymazání aplikace**: tuto možnost vyberte, pokud chcete ze zařízení vybraného uživatele odebrat jenom firemní data. Další informace naleznete v tématu:
  - [Selektivní vymazání aplikace](apps-selective-wipe.md)
- **zřizovací profily aplikací pro iOS**: aplikace pro iOS obsahují zřizovací profil a kód, který je podepsaný certifikátem. Po vypršení platnosti certifikátu již nelze aplikaci spustit. Intune poskytuje nástroje pro proaktivní přiřazení nových zásad zřizovacího profilu k zařízením s aplikacemi, které se blíží vypršení platnosti. Další informace naleznete v tématu:
  - [zřizovací profily aplikací pro iOS](app-provisioning-profile-ios.md).

Další informace o této části najdete v tématu [Správa aplikací](app-management.md).

### <a name="monitor"></a>Sledován
- **Licence**k aplikacím: zobrazit, přiřadit a monitorovat aplikace hromadně zakoupené v obchodech s aplikacemi. Další informace naleznete v tématu:
  - [aplikace programu hromadných nákupů pro iOS (VPP)](vpp-apps-ios.md)
  - [Microsoft Store pro aplikace hromadně zakoupených aplikací](windows-store-for-business.md).
- **Zjištěné aplikace**: zobrazí aplikace, které byly přiřazeny přes Intune nebo nainstalované na zařízení. Další informace najdete v tématu [zjištěné aplikace Intune](app-discovered-apps.md).
- **Stav instalace aplikace**: Podívejte se na stav přiřazení aplikace, které jste vytvořili. Další informace najdete v tématu [monitorování informací a přiřazení aplikace pomocí Microsoft Intune](apps-monitor.md#device-and-user-status-graphs).
- **Stav ochrany aplikací**: zobrazuje stav zásad ochrany aplikací pro uživatele, kterého jste vybrali.
- **Protokoly auditu**: Prohlédněte si aktivity všech SPRÁVCů IT, které se týkají aplikace Intune.

Další informace o této části najdete v tématu [monitorování aplikací](apps-monitor.md).

### <a name="set-up"></a>Nastavit
- **tokeny VPP pro iOS**: použijte a ZOBRAZTE licence VPP (Volume purchase program) pro iOS. Další informace naleznete v tématu:
  - [hromadně zakoupené aplikace pro iOS](vpp-apps-ios.md)
- **Windows Enterprise Certificate**: použijte nebo zobrazte stav certifikátu pro podepisování kódu, který se používá k distribuci obchodních aplikací do spravovaných zařízení s Windows.
- **Certifikát Windows Symantec**: můžete použít nebo zobrazit stav certifikátu Symantec pro podepisování kódu, který je nutný k distribuci souborů appx XAP a WP8. x na zařízení s Windows 10 Mobile.
- **Microsoft Store pro firmy**: nastavte integraci do Microsoft Store pro firmy. Později můžete zakoupit zakoupené aplikace do Intune, přiřazovat je a sledovat využití licencí. Další informace naleznete v tématu:
  - [Microsoft Store pro aplikace hromadně zakoupených aplikací](windows-store-for-business.md).
- **Klíče pro nasazování ze strany Windows**: přidejte klíč pro instalaci ze strany Windows, který se dá použít k instalaci aplikace přímo do zařízení, a ne publikování a stažení aplikace z Windows Storu. Další informace naleznete v tématu:
  - [Načtěte aplikaci pro Windows stranou](app-sideload-windows.md).
- **Portál společnosti branding**: Upravte portál společnosti tak, aby poskytoval IT značky vaší společnosti. Další informace naleznete v tématu:
  - [Konfigurace portál společnosti](company-portal-app.md).
- **Kategorie aplikací**: přidat, připnout a odstranit názvy kategorií aplikací.
- **Pracovní profil Androidu**: schvalte a synchronizujte aplikace, které jste schválili pro váš podnik. Další informace naleznete v tématu:
  - [Aplikace pro pracovní profil Androidu](apps-add-android-for-work.md)

### <a name="help-and-support"></a>Pomoc a podpora
- **Pomoc a podpora**: řešení potíží, žádosti o podporu nebo zobrazení stavu Intune. Další informace naleznete v tématu:
  - [Řešení problémů](../fundamentals/help-desk-operators.md).

## <a name="next-steps"></a>Další kroky

- [Přidání aplikace do Microsoft Intune](apps-add.md)
