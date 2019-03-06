---
title: Monitorování podmíněného přístupu Exchange v Microsoft Intune | Microsoft Intune
description: Monitorování dodržování předpisů podmíněného přístupu u místního Exchange a Exchange Online prostřednictvím portálu Intune Azure Portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 21e3d4b27348bc5ed64c192c8d6824af053a833b
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57397419"
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>Monitorování dodržování předpisů podmíněného přístupu u místního Exchange a Exchange Online v Intune

Počínaje verzí Intune 1704 můžou správci zobrazit sestavy s informacemi týkajícími se záznamů o zařízeních používajících protokol Exchange ActiveSync, která jsou synchronizovaná s Intune prostřednictvím místního konektoru Exchange Connector nebo konektoru Intune Service to Service Connector (konektoru Exchange Online). Sestavy dodržování předpisů místního přístupu poskytují přehled o zařízeních s různými stavy synchronizace:

-   **Povoleno**

-   **Blokováno**

-   **Karanténa**

## <a name="to-monitor-conditional-access-compliance"></a>Monitorování dodržování předpisů podmíněného přístupu

1.  Přejděte na portál [Azure Portal](https://portal.azure.com/) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

2.  Po úspěšném přihlášení se zobrazí **řídicí panel Azure**.

3.  V nabídce vlevo zvolte **Všechny služby** a do filtru textového pole pak zadejte **Intune**.

4.  Zvolte **Intune** a zobrazí se **řídicí panel Intune**.

5.  Zvolte **Podmíněný přístup** a pak zvolte **Přehled**.

6.  Zvolte jednu ze tří oblastí grafu (**Povoleno**, **Blokováno** nebo **Karanténa**), abyste zobrazili sestavu dodržování předpisů podmíněného přístupu.

    ![Obrázek řídicího panelu podmíněného přístupu](./media/CA-reporting-intune-1.png)

Po zvolení jedné z těchto oblastí uvidíte podrobnější informace o zařízeních, která jsou povolená, blokovaná nebo v karanténě.

Můžete také přecházet k podrobnostem o konkrétních zařízeních. Například zařízení zvolené na následujícím obrázku je blokované. Intune nabízí možnost z podokna sestavy dodržování předpisů odebrat firemní data.

![Obrázek podrobných informací o zařízení s podmíněným přístupem](./media/CA-reporting-intune-3.png)

V podokně podrobností o zařízení můžete zobrazit další informace:

-   **Přehled:** Můžete zobrazit vlastnosti zařízení, například: Verze operačního systému, model zařízení, vlastnictví, sériové číslo, výrobce zařízení, telefonní číslo a poslední čas zařízení se změnami.

-   **Vlastnosti:** Můžete nastavit vlastnictví zařízení (osobní nebo firemní).

-   **Hardware:** Poskytuje informace, které se zobrazí na přehled a také podrobnosti o úložišti (celkové místo a volné místo), počítačová skříň, podrobnosti o síti, síťové služby a další podmíněný přístup blokuje podrobnosti.

-   **Zjištěné aplikace:** Zobrazuje všechny aplikace nainstalované na zařízení. Seznam nainstalovaných aplikací můžete exportovat do formátu CSV.

-   **Dodržování předpisů:** Dodržování předpisů pro všechna zařízení zobrazuje podrobnosti zásad.

-   **Konfigurace zařízení:** Zobrazuje všechny podrobnosti o konfiguraci zařízení.

-   **Přístup k systému Exchange:** Tady najdete další informace o stavu zařízení po použití zásad podmíněného přístupu.
