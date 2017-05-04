---
title: "Monitorování dodržování předpisů podmíněného přístupu u místního Exchange a Exchange Online"
titleSuffix: Intune Azure preview
description: "Monitorování dodržování předpisů podmíněného přístupu u místního Exchange a Exchange Online prostřednictvím portálu Intune Azure Portal"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: c8715f96f532ee6bacda231e1147d03226ecbb48
ms.openlocfilehash: 9d5521de8709bf232dedfeeb1874f8db1898f2d0
ms.lasthandoff: 04/26/2017


---

# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune-azure-preview"></a>Monitorování dodržování předpisů podmíněného přístupu u místního Exchange a Exchange Online v Intune Azure Preview

Počínaje verzí Intune 1704 můžou správci zobrazit sestavy s informacemi týkajícími se záznamů o zařízeních používajících protokol Exchange ActiveSync, která jsou synchronizovaná s Intune prostřednictvím místního konektoru Exchange Connector nebo konektoru Intune Service to Service Connector (konektoru Exchange Online). Sestavy dodržování předpisů místního přístupu poskytují přehled o zařízeních s různými stavy synchronizace:

-   **Povoleno**

-   **Blokováno**

-   **Karanténa**

## <a name="to-monitor-conditional-access-compliance"></a>Monitorování dodržování předpisů podmíněného přístupu

1.  Přejděte na portál [Azure Portal](https://portal.azure.com/) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

2.  Po úspěšném přihlášení se zobrazí **řídicí panel Azure**.

3.  V nabídce vlevo zvolte **Další služby** a do filtru textového pole pak zadejte **Intune**.

4.  Zvolte **Intune** a zobrazí se **řídicí panel Intune**.

5.  Zvolte **Podmíněný přístup** a potom zvolte **Přehled**.

6.  Zvolte jednu ze tří oblastí grafu (**Blokováno**, **Karanténa** nebo **Povoleno**), abyste zobrazili sestavu dodržování předpisů podmíněného přístupu.

    ![Řídicí panel podmíněného přístupu](../media/CA-reporting-intune-1.png)

Po zvolení jedné z těchto oblastí uvidíte podrobnější informace o zařízeních, která jsou povolená, blokovaná nebo v karanténě.

Můžete také přecházet k podrobnostem o konkrétních zařízeních. Například zařízení zvolené na obrázku níže je blokované. Intune nabízí možnost z okna sestavy dodržování předpisů odebrat firemní data.

![Podrobné informace o zařízení s podmíněným přístupem](../media/CA-reporting-intune-3.png)

V okně podrobností o zařízení můžete zobrazit další informace:

-   **Přehled:** Můžete zjistit vlastnosti zařízení, například verzi operačního systému, model zařízení, vlastnictví, sériové číslo, výrobce zařízení, telefonní číslo a čas posledního vrácení zařízení se změnami.

-   **Vlastnosti:** Můžete stanovit vlastnictví zařízení (Osobní nebo Firemní).

-   **Hardware:** Tady jsou informace, které vidíte v Přehledu, a také podrobnosti o úložišti (celkové místo a volné místo), o počítačové skříni, podrobnosti o síti, o síťové službě a další informace o blokování podmíněného přístupu.

-   **Zjištěné aplikace:** Tady se zobrazují všechny aplikace nainstalované na zařízení. Seznam nainstalovaných aplikací můžete exportovat do formátu CSV.

-   **Dodržování předpisů:** Tady se zobrazují všechny podrobnosti zásad dodržování předpisů u zařízení.

-   **Konfigurace zařízení:** Tady se zobrazují všechny podrobnosti o konfiguraci zařízení.

-   **Přístup k Exchangi:** Tady najdete další informace o stavu zařízení po použití zásad podmíněného přístupu.

