---
title: Monitorování podmíněného přístupu Exchange v Microsoft Intune | Microsoft Intune
description: Monitorování dodržování předpisů podmíněného přístupu u místního Exchange a Exchange Online prostřednictvím portálu Intune Azure Portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 8c9602dbe183501cc779fcb9b5d5a1e6e4bf6154
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816766"
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>Monitorování dodržování předpisů podmíněného přístupu u místního Exchange a Exchange Online v Intune

Počínaje verzí Intune 1704 můžou správci zobrazit sestavy informace související s Exchange ActiveSync zařízení záznamy, které se synchronizují s Intune prostřednictvím místního Exchange Connectoru nebo konektor Intune service to service connector (Exchange Online connector). Sestavy dodržování předpisů pro podmíněný přístup poskytuje přehled o zařízeních s různými stavy synchronizace:

-   **Povoleno**

-   **Blokováno**

-   **Karanténa**

## <a name="to-monitor-conditional-access-compliance"></a>Monitorování dodržování předpisů podmíněného přístupu

1.  Přejděte na portál [Azure Portal](https://portal.azure.com/) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

2.  Po úspěšném jste přihlášení, zobrazí **řídicím panelu Azure**.

3.  Zvolte **všechny služby** v levé nabídce zadejte **Intune** do filtru textového pole.

4.  Zvolte **Intune**, uvidíte **řídicí panel Intune**.

5.  Zvolte **Podmíněný přístup** a pak zvolte **Přehled**.

6.  Zvolte jednu ze tří oblastí grafu (**Povoleno**, **Blokováno** nebo **Karanténa**), abyste zobrazili sestavu dodržování předpisů podmíněného přístupu.

    ![Obrázek řídicího panelu podmíněného přístupu](./media/CA-reporting-intune-1.png)

Po zvolení jedné z těchto oblastí uvidíte podrobnější informace o zařízeních, která jsou povolená, blokovaná nebo v karanténě.

Můžete také procházet hierarchii konkrétních zařízeních zobrazíte další podrobnosti. Například zařízení zvolené na následujícím obrázku je blokované. Intune nabízí možnost z podokna sestavy dodržování předpisů odebrat firemní data.

![Obrázek podrobných informací o zařízení s podmíněným přístupem](./media/CA-reporting-intune-3.png)

V podokně podrobností o zařízení můžete zobrazit další informace:

-   **Přehled:** Můžete zobrazit vlastnosti zařízení, například: Verze operačního systému, model zařízení, vlastnictví, sériové číslo, výrobce zařízení, telefonní číslo a poslední čas zařízení se změnami.

-   **Vlastnosti:** Můžete nastavit vlastnictví zařízení (osobní nebo firemní).

-   **Hardware:** Poskytuje informace, které se zobrazí na přehled a také podrobnosti o úložišti (celkové místo a volné místo), počítačová skříň, podrobnosti o síti, síťové služby a další podmíněný přístup blokuje podrobnosti.

-   **Zjištěné aplikace:** Zobrazuje všechny aplikace nainstalované na zařízení. Seznam nainstalovaných aplikací můžete exportovat do formátu CSV.

-   **Dodržování předpisů:** Dodržování předpisů pro všechna zařízení zobrazuje podrobnosti zásad.

-   **Konfigurace zařízení:** Zobrazuje všechny podrobnosti o konfiguraci zařízení.

-   **Přístup k systému Exchange:** Tady najdete další informace o stavu zařízení po použití zásad podmíněného přístupu.
