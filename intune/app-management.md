---
title: Co je správa aplikací v Microsoft Intune
titlesuffix: ''
description: Naučte se základy správy aplikací pomocí Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 86cb0dfb67e81a7abbdc8f38dcbf5539b9855adb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="what-is-microsoft-intune-app-management"></a>Co je správa aplikací v Microsoft Intune?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune vám jakožto správci IT umožňuje spravovat mobilní aplikace, které používají pracovníci vaší společnosti. Tato funkce doplňuje správu zařízení a ochranu dat. Jednou z vašich priorit v rámci této funkce je zajistit, aby koncoví uživatelé měli přístup k aplikacím, které potřebují k práci. To může být náročné z těchto důvodů:
- Existuje široký sortiment platforem zařízení a typů aplikací.
- Potřebujete spravovat aplikace na firemních zařízeních i na zařízeních vlastněných uživateli.
- Musíte zajistit zabezpečení sítě a dat.

Navíc potřebujete přiřazovat a spravovat aplikace na zařízeních, která nejsou zaregistrovaná v Intune.

Intune nabízí celou řadu funkcí, které vám pomůžou zajistit, aby na požadovaných zařízeních byly potřebné aplikace. Následující tabulka nabízí souhrn funkcí správy aplikací. Pod tabulkou jsou informace o tom, jak začít rozumět službě Microsoft Intune na portálu Azure Portal.

## <a name="app-management-capabilities-by-platform"></a>Funkce správy aplikací podle platformy

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|Přidání a přiřazení aplikací zařízením a uživatelům|Ano|Ano|Ano|Ano|
|Přiřazení aplikací k zařízením nezaregistrovaným v Intune|Ano|Ano|Ne|Ne|
|Určení chování aplikací při spuštění pomocí zásad konfigurace aplikací|Ne|Ano|Ne|Ne|
|Obnovení aplikací s vypršenou platností pomocí zásad zřizování mobilních aplikací|Ne|Ano|Ne|Ne|
|Ochrana firemních dat v aplikacích pomocí zásad ochrany aplikací|Ano|Ano|Ne|Ne<sup>1</sup>|
|Odebrání pouze firemních dat z nainstalovaných aplikací (selektivní vymazání aplikací)|Ano|Ano|Ano|Ano|
|Monitorování přiřazení aplikací|Ano|Ano|Ano|Ano|
|Přiřazení a sledování aplikací hromadně zakoupených v obchodu s aplikacemi|Ne|Ne|Ne|Ano|
|Nařízená instalace aplikací na zařízení (povinná)<sup>2</sup>|Ano|Ano|Ano|Ano|
|Nepovinná instalace na zařízení z Portálu společnosti (dostupná instalace)|Ano|Ano|Ano|Ano|
|Zástupce pro instalaci aplikace na webu (webový odkaz)|Ano|Ano|Ano|Ano|
|Vlastní (obchodní) aplikace|Ano|Ano|Ne|Ano|
|Aplikace z obchodu|Ano|Ano|Ano|Ano|
|Aktualizace aplikací|Ano|Ano|Ano|Ano|

<sup>1</sup> Při ochraně aplikací na zařízeních s Windows 10 uvažujte o použití funkce [Windows Information Protection](windows-information-protection-configure.md).

<sup>2</sup> Platí jen pro zařízení spravovaná přes Intune.

## <a name="how-to-get-started"></a>Informace o tom, jak začít

Většinu toho, co souvisí s aplikacemi, najdete v úloze **Mobilní aplikace**, ke které se dostanete takto:

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V okně **Intune** zvolte **Mobilní aplikace**.

    ![Úloha Mobilní aplikace](./media/apps-workload.png)

Níže uvedené informace odpovídají možnostem dostupným v okně **Mobilní aplikace**.

### <a name="manage"></a>Správa
- **Aplikace** – tuto možnost vyberte pro přidávání, zobrazení, přiřazování a monitorování aplikací používaných vašimi pracovníky. Další informace najdete v následujících článcích:
    - [Přidání aplikací](apps-add.md)
    - [Přiřazení aplikací](apps-deploy.md)
    - [Monitorování aplikací](apps-monitor.md)
- **Zásady konfigurace aplikací** – zásady konfigurace aplikací umožňují určit nastavení, která se můžou požadovat, když uživatel spustí nějakou aplikaci. Další informace najdete v následujících článcích:
    - [Zásady konfigurace aplikací pro Intune](app-configuration-policies-overview.md)
        - [Zásady konfigurace aplikací pro iOS](app-configuration-policies-use-ios.md)
        - [Zásady konfigurace aplikací pro Android](app-configuration-policies-use-android.md)
- **Zásady ochrany aplikací** – zásady ochrany aplikací umožňují aplikaci přidružit nastavení pomáhající chránit firemní data, která tato aplikace používá. Můžete například omezit možnosti komunikace aplikace s jinými aplikacemi nebo vyžadovat, aby uživatel při přístupu k firemní aplikaci zadal PIN kód. Další informace najdete v následujících článcích:
    - [Zásady ochrany aplikací](app-protection-policies.md)
- **Selektivní vymazání aplikace** – umožňuje z vybraného zařízení uživatele vymazat jen firemní data. Další informace najdete v následujících článcích:
    - [Selektivní vymazání aplikace](apps-selective-wipe.md)
- **Zřizovací profily aplikací pro iOS** – aplikace pro iOS obsahují zřizovací profil a kód, který je podepsaný certifikátem. Když tomuto certifikátu vyprší platnost, není možné aplikaci spustit. Intune poskytuje nástroje pro proaktivní přiřazení nových zásad zřizovacího profilu k zařízením s aplikacemi, kterým brzy vyprší platnost. Další informace najdete v následujících článcích:
    - [Zřizovací profily aplikací pro iOS](app-provisioning-profile-ios.md)

Další podrobnosti najdete v tématu [Správa aplikací](app-management.md).

### <a name="monitor"></a>Monitorování
- **Licence aplikací** – zde můžete zobrazit, přiřadit a monitorovat aplikace hromadně zakoupené v obchodech s aplikacemi. Další informace najdete v následujících článcích:
    - [Aplikace programu hromadných nákupů pro iOS](vpp-apps-ios.md)
    - [Aplikace hromadně zakoupené v Microsoft Storu pro firmy](windows-store-for-business.md)
- **Zjištěné aplikace** – zobrazuje všechny aplikace přiřazené přes Intune a nainstalované v zařízení.
- **Stav instalace aplikace** – zobrazuje stav vytvořeného přiřazení aplikace.
- **Stav ochrany aplikací** – zobrazuje stav zásad ochrany aplikací pro vybraného uživatele.
- **Protokoly auditu** – zobrazuje aktivity související s aplikacemi v Intune, které provedli všichni správci IT.

Další podrobnosti najdete v tématu [Monitorování aplikací](apps-monitor.md).

### <a name="setup"></a>Nastavení
- **Tokeny VPP pro iOS** – přiřazuje a zobrazuje licence programu VPP (Volume Purchase Program) pro iOS.
    - [Multilicenční aplikace pro iOS](vpp-apps-ios.md)
- **Certifikát Windows Enterprise** – přiřazuje a zobrazuje stav certifikátu pro podepisování kódu, který se používá k distribuci-obchodních aplikací do spravovaných zařízení s Windows.
- **Certifikát Windows Symantec** – přiřazuje a zobrazuje stav certifikátu Symantec pro podepisování kódu, který je nutný k distribuci souborů appx pro XAP a WP8.x na zařízení s Windows 10 Mobile.
- **Microsoft Store pro firmy** – integrace nastavení do Microsoft Storu pro firmy. Potom můžete zakoupené aplikace synchronizovat s Intune, přiřazovat je a sledovat využití licencí. Další informace najdete v následujících článcích:
    - [Aplikace hromadně zakoupené v Microsoft Storu pro firmy](windows-store-for-business.md)
- **Klíče pro instalaci bokem ve Windows** – můžete přidat klíč pro instalaci bokem ve Windows, který lze použít k instalaci aplikace přímo do zařízení (místo publikování aplikace a jejího stahování z Windows Storu). Další informace najdete v následujících článcích:
    - [Instalace aplikace pro Windows bokem](app-sideload-windows.md)
- **Značky Portálu společnosti** – Portál společnosti můžete přizpůsobit o značku své firmy. Další informace najdete v následujících článcích:
    - [Konfigurace Portálu společnosti](company-portal-app.md)
- **Kategorie aplikací** – zde můžete přidat, připnout a odstranit názvy kategorií aplikací.
- **Android for Work** – zde můžete schválit a synchronizovat aplikace schválené pro váš podnik. Další informace najdete v následujících článcích:
    - [Aplikace pro Android for Work](apps-add-android-for-work.md)

### <a name="help-and-support"></a>Nápověda a podpora
- **Nápověda a podpora** – zde můžete řešit potíže, požádat o podporu nebo zobrazit stav Intune. Další informace najdete v následujících článcích:
    - [Odstraňování potíží](help-desk-operators.md)

## <a name="next-steps"></a>Další kroky

- [Přidání aplikací do Microsoft Intune](apps-add.md)
