---
title: "Co je správa aplikací"
titleSuffix: Intune on Azure
description: "V tomto tématu se dozvíte základy správy aplikací pomocí Microsoft Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c05b2257fe03cd23ad5ba71a3fee217cd4802650
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/08/2017
---
# <a name="what-is-microsoft-intune-app-management"></a>Co je správa aplikací v Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Jako správce IT musíte zajistit, aby koncoví uživatelé měli přístup k aplikacím, které potřebují ke své práci. To může být náročné z těchto důvodů:
- Existuje široký sortiment platforem zařízení a typů aplikací.
- Potřebujete spravovat aplikace na firemních zařízeních i na zařízeních vlastněných uživateli.
- Musíte zajistit síť a data musí zůstat zabezpečená.

Navíc potřebujete přiřazovat a spravovat aplikace na zařízeních, která nejsou zaregistrovaná v Intune.

Intune nabízí celou řadu funkcí, které vám pomůžou zajistit, aby na požadovaných zařízeních byly potřebné aplikace.

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
|Zástupce pro instalaci aplikace na webu (webový klip)|Ano|Ano|Ano|Ano|
|Vlastní (obchodní) aplikace|Ano|Ano|Ne|Ne|
|Aplikace z obchodu|Ano|Ano|Ano|Ano|
|Aktualizace aplikací|Ano|Ano|Ano|Ano|

<sup>1</sup> Při ochraně aplikací na zařízeních s Windows 10 uvažujte o použití funkce [Windows Information Protection](windows-information-protection-configure.md).

<sup>2</sup> Platí jen pro zařízení spravovaná přes Intune.

## <a name="how-to-get-started"></a>Informace o tom, jak začít

Většinu toho, co souvisí s aplikacemi, najdete v úloze **Mobilní aplikace**, ke které se dostanete takto:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Mobilní aplikace**.

    ![Úloha Mobilní aplikace](./media/apps-workload.png)

### <a name="manage"></a>Správa
- **Aplikace** – v tomto uzlu budete přidávat, přiřazovat a monitorovat většinu aplikací.
    - [Přidání aplikací](apps-add.md)
    - [Přiřazení aplikací](apps-deploy.md)
    - [Monitorování aplikací](apps-monitor.md)
- **Zásady konfigurace aplikací** – zásady konfigurace aplikací umožňují určit nastavení, která se můžou požadovat, když uživatel spustí nějakou aplikaci.
    - [Zásady konfigurace aplikací pro iOS](app-configuration-policies-use-ios.md)
    - [Zásady konfigurace aplikací pro Android](app-configuration-policies-use-android.md)
- **Zásady ochrany aplikací** – zde můžete k aplikaci přidružit nastavení pomáhající chránit firemní data, která tato aplikace používá. Můžete například omezit možnosti komunikace aplikace s jinými aplikacemi nebo vyžadovat, aby uživatel při přístupu k firemní aplikaci zadal PIN kód.
    - [Zásady ochrany aplikací](app-protection-policies.md)
- **Selektivní vymazání aplikace** – umožňuje z vybraného zařízení uživatele vymazat jen firemní data.
    - [Selektivní vymazání aplikace](apps-selective-wipe.md)
- **Zřizovací profily iOS** – aplikace pro iOS obsahují zřizovací profil a kód, který je podepsaný certifikátem. Když tomuto certifikátu vyprší platnost, není možné aplikaci spustit. Intune poskytuje nástroje pro proaktivní přiřazení nových zásad zřizovacího profilu k zařízením s aplikacemi, kterým brzy vyprší platnost.
    - [Zřizovací profily aplikací pro iOS](app-provisioning-profile-ios.md)

### <a name="monitor"></a>Monitorování
- **Licencované aplikace** – zde můžete zobrazit, přiřadit a monitorovat aplikace hromadně zakoupené v obchodech s aplikacemi.
    - [Aplikace hromadně zakoupené v Microsoft Storu pro firmy](windows-store-for-business.md)
- **Zjištěné aplikace** – zobrazuje všechny aplikace přiřazené přes Intune a nainstalované v zařízení.
- **Stav instalace aplikace** – zobrazuje stav vytvořeného přiřazení aplikace.
- **Stav ochrany aplikací** – zobrazuje stav zásad ochrany aplikací pro vybraného uživatele.

Podrobnosti najdete v článku [Monitorování aplikací](apps-monitor.md).

### <a name="setup"></a>Nastavení
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](vpp-apps-ios.md) --->
- **Microsoft Store pro firmy** – integrace nastavení do Microsoft Storu pro firmy. Potom můžete zakoupené aplikace synchronizovat s Intune, přiřazovat je a sledovat využití licencí.
    - [Aplikace hromadně zakoupené v Microsoft Storu pro firmy](windows-store-for-business.md)
- **Značky Portálu společnosti** – Portál společnosti můžete přizpůsobit o značku své firmy.
    - [Konfigurace Portálu společnosti](company-portal-app.md)
