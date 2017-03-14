---
title: "Co je správa aplikací"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: V tomto tématu se dozvíte základy správy aplikací pomocí Microsoft Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 33def827fc7417930338e56c650d01df4dad85fb
ms.lasthandoff: 02/18/2017


---

# <a name="what-is-microsoft-intune-app-management"></a>Co je správa aplikací v Microsoft Intune?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Jako správce IT máte pravděpodobně za úkol zajistit, aby koncoví uživatelé měli přístup k aplikacím, které potřebují ke své práci. To může být náročné z těchto důvodů:
- Existuje široký sortiment platforem zařízení a typů aplikací.
- Potřebujete spravovat aplikace na firemních zařízeních i na zařízeních vlastněných uživateli.
- Zároveň s tím musíte zajistit, aby vaše síť a data zůstaly zabezpečené. 

Navíc potřebujete přiřazovat a spravovat aplikace na zařízeních, která nejsou zaregistrovaná v Intune.

Intune nabízí celou řadu funkcí, které vám pomůžou zajistit, aby na požadovaných zařízeních byly potřebné aplikace.

## <a name="app-management-capabilities-by-platform"></a>Funkce správy aplikací podle platformy

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|Přidání a přiřazení aplikací zařízením a uživatelům|Ano|Ano|Ano|Ano|
|Přiřazení aplikací k zařízením nezaregistrovaným v Intune|Ano|Ano|Ne|Ne|
|Určení chování aplikací při spuštění pomocí zásad konfigurace aplikací|Ne|Ano|Ne|Ne|
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

<sup>1</sup> Při ochraně aplikací na zařízeních s Windows 10 uvažujte o použití funkce [Windows Information Protection](/intune-azure/configure-devices/how-to-configure-windows-information-protection).

<sup>2</sup> Platí jen pro zařízení spravovaná přes Intune.


## <a name="how-to-get-started"></a>Informace o tom, jak začít

Většinu toho, co souvisí s aplikacemi, najdete v úloze **Mobilní aplikace**, ke které se dostanete takto:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Spravovat aplikace**.

    ![Úloha Mobilní aplikace](./media/apps-workload.png)

### <a name="manage"></a>Správa
- **Aplikace** – zde budete přidávat, přiřazovat a monitorovat většinu aplikací. 
    - [Přidání aplikací](add-apps.md)
    - [Přiřazení aplikací](deploy-apps.md)
    - [Monitorování aplikací](monitor-apps.md)
- **Licencované aplikace** – zde můžete zobrazit, nasadit a monitorovat aplikace hromadně zakoupené v obchodech s aplikacemi.
    - [Aplikace hromadně zakoupené ve Windows Storu pro firmy](wsfb-apps.md)
- **Zásady konfigurace aplikací** – zásady konfigurace aplikací umožňují určit nastavení, která se můžou požadovat, když uživatel spustí nějakou aplikaci. Podrobnosti najdete v tématech:
    - [Zásady konfigurace aplikací](app-configuration-policies.md)
- **Zásady ochrany aplikací** – zde můžete k aplikaci přidružit nastavení pomáhající chránit firemní data, která tato aplikace používá. Můžete například omezit možnosti komunikace aplikace s jinými aplikacemi nebo vyžadovat, aby uživatel při přístupu k firemní aplikaci zadal PIN kód.
    - [Zásady ochrany aplikací](app-protection-policies.md)
- **Selektivní vymazání aplikace** – umožňuje z vybraného zařízení uživatele vymazat jen firemní data.
    - [Selektivní vymazání aplikace](app-selective-wipe.md)

### <a name="monitor"></a>Monitorování
- **Zjištěné aplikace** – zobrazuje všechny aplikace přiřazené přes Intune a nainstalované v zařízení.
- **Stav instalace aplikace** – zobrazuje stav vytvořeného přiřazení aplikace.
- **Stav uživatele ochrany aplikací** – zobrazuje stav zásad ochrany aplikací pro vybraného uživatele.

Podrobnosti najdete v článku [Monitorování aplikací](monitor-apps.md).

### <a name="setup"></a>Nastavení
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](ios-vpp-apps.md) --->
- **Windows Store pro firmy** – integrace nastavení do Windows Storu pro firmy. Až to uděláte, můžete zakoupené aplikace synchronizovat s Intune, přiřazovat je a sledovat využití licencí. 
    - [Aplikace hromadně zakoupené ve Windows Storu pro firmy](wsfb-apps.md)
- **Značky Portálu společnosti** – Portál společnosti můžete přizpůsobit o značku své firmy. 
    - [Konfigurace Portálu společnosti](company-portal-app.md)

