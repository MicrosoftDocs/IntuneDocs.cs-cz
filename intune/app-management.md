---
title: Co je správa aplikací v Microsoft Intune?
titleSuffix: ''
description: Další informace o funkcích správy, klient aplikace podle platformy pro Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3586822b16a7c04f16a1b6eb894f45aaf9106bef
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798564"
---
# <a name="what-is-microsoft-intune-app-management"></a>Co je správa aplikací v Microsoft Intune?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako správce IT můžete Microsoft Intune použít ke správě klientských aplikací, které používají pracovníci vaší společnosti. Tato funkce doplňuje správu zařízení a ochranu dat. Jednou z priorit správce je zajistit, aby koncoví uživatelé měli přístup k aplikacím, které potřebují ke své práci. To může být náročné z těchto důvodů:
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

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**.  
    Intune se nachází v části **Monitorování a správa**.
3. V podokně **Microsoft Intune** vyberte **Klientské aplikace**.

    ![Podokno úloh Klientské aplikace](./media/apps-workload.png)

Další čtyři části popisují možnosti dostupné v podokně **Klientské aplikace**.

### <a name="manage"></a>Správa
- **Aplikace**: Tuto možnost chcete přidat, zobrazit, přiřadit a monitorování aplikací používaných vašimi pracovníky. Další informace naleznete v tématu:
    - [Přidání aplikací](apps-add.md)
    - [Přiřazení aplikací](apps-deploy.md)
    - [Monitorování aplikací](apps-monitor.md)
- **Zásady Konfigurace aplikací**: Tuto možnost vyberte k poskytování nastavení, které mohou být vyžadovány, když uživatel spustí nějakou aplikaci. Další informace naleznete v tématu:
    - [Zásady konfigurace aplikací pro Intune](app-configuration-policies-overview.md)
        - [Zásady konfigurace aplikací pro iOS](app-configuration-policies-use-ios.md)
        - [Zásady konfigurace aplikací pro Android](app-configuration-policies-use-android.md)
- **Zásady ochrany aplikací**: Tuto možnost použijte k aplikaci přidružit nastavení a pomáhají chránit firemní data, které používá. Můžete například omezit možnosti komunikace aplikace s jinými aplikacemi nebo vyžadovat, aby uživatel při přístupu k firemní aplikaci zadal PIN kód. Další informace naleznete v tématu:
    - [Zásady ochrany aplikací](app-protection-policies.md)
- **Selektivní vymazání aplikace**: Vyberte tuto možnost, chcete-li odebrat jenom firemní data z vybraného uživatele zařízení. Další informace naleznete v tématu:
    - [Selektivní vymazání aplikace](apps-selective-wipe.md)
- **Zřizovací profily aplikací pro iOS**: Aplikace pro iOS obsahují zřizovací profil a kód, který je podepsaný certifikátem. Když tomuto certifikátu vyprší platnost, není možné aplikaci spustit. Intune poskytuje nástroje pro proaktivní přiřazení nových zásad zřizovacího profilu k zařízením s aplikacemi, kterým brzy vyprší platnost. Další informace naleznete v tématu:
    - [Zřizovací profily aplikací pro iOS](app-provisioning-profile-ios.md)

Další informace o této části najdete v tématu [Správa aplikací](app-management.md).

### <a name="monitor"></a>Monitorování
- **Licence aplikací**: Zobrazit, přiřadit a monitorovat aplikace hromadně zakoupené v obchodech. Další informace naleznete v tématu:
    - [Aplikace programu hromadných nákupů pro iOS](vpp-apps-ios.md)
    - [Aplikace hromadně zakoupené v Microsoft Storu pro firmy](windows-store-for-business.md)
- **Zjištěné aplikace**: Zobrazení aplikací, které byly přiřazeny přes Intune nebo nainstalované v zařízení. Další informace najdete v tématu [Zobrazení podrobností o zařízení v Intune](device-inventory.md).
- **Stav instalace aplikace**: Zobrazte stav přiřazení aplikace, kterou jste vytvořili. Další informace najdete v článku [Monitorování informací a přiřazení aplikace pomocí Microsoft Intune](apps-monitor.md#device-and-user-status-graphs).
- **Stav ochrany aplikace**: Zobrazte stav zásad ochrany aplikací pro vybraného uživatele.
- **Protokoly auditu**: Zobrazte aktivitu související s aplikacemi v Intune všech správců IT.

Další informace o této části najdete v tématu [Monitorování aplikací](apps-monitor.md).

### <a name="set-up"></a>Nastavení
- **tokeny VPP pro iOS**: Přiřazuje a zobrazuje licence Volume Purchase Program (VPP) pro iOS. Další informace naleznete v tématu:
    - [hromadně zakoupených aplikací pro iOS](vpp-apps-ios.md)
- **Certifikát Windows enterprise**: Použít nebo zobrazit stav certifikátu pro podepisování kódu, který se používá k distribuci-obchodních aplikací do spravovaných zařízení s Windows.
- **Certifikát Windows Symantec**: Použít nebo zobrazit stav certifikátu Symantec pro podepisování kódu, který je nutný k distribuci souborů appx XAP a WP8.x na zařízení Windows 10 Mobile.
- **Microsoft Store pro firmy**: Nastavení integrace do Microsoft Store pro firmy. Potom můžete zakoupené aplikace synchronizovat s Intune, přiřazovat je a sledovat využití licencí. Další informace naleznete v tématu:
    - [Aplikace hromadně zakoupené v Microsoft Storu pro firmy](windows-store-for-business.md)
- **Klíče pro instalaci bokem ve Windows**: Přidáte klíč pro zkušební načtení Windows, který slouží k instalaci aplikace přímo do zařízení místo publikování a stažení aplikace z Windows storu. Další informace naleznete v tématu:
    - [Instalace aplikace pro Windows bokem](app-sideload-windows.md)
- **Značky portálu společnosti**: Přizpůsobení portálu společnosti o značku své firmy. Další informace naleznete v tématu:
    - [Konfigurace Portálu společnosti](company-portal-app.md)
- **Kategorie aplikací**: Přidat, připnout a odstranit názvy kategorií aplikací.
- **Pracovní profil androidu**: Schválit a synchronizovat aplikace schválené pro vaši firmu. Další informace naleznete v tématu:
    - [Aplikace v pracovním profilu Androidu](apps-add-android-for-work.md)

### <a name="help-and-support"></a>Nápověda a podpora
- **Nápověda a podpora**: Řešení potíží, požádat o podporu nebo zobrazit stav Intune. Další informace naleznete v tématu:
    - [Odstraňování potíží](help-desk-operators.md)

## <a name="next-steps"></a>Další postup

- [Přidání aplikace do Microsoft Intune](apps-add.md)
