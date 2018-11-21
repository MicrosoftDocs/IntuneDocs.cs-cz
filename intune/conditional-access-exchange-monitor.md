---
title: Monitorování podmíněného přístupu u Exchange v Microsoft Intune
titlesuffix: ''
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
ms.openlocfilehash: 20a99290d2a84c22bc2bee823d7a3bb42e43aced
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180574"
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

-   **Přehled:** Můžete zjistit vlastnosti zařízení, třeba verzi operačního systému, model zařízení, vlastnictví, sériové číslo, výrobce zařízení, telefonní číslo a čas, kdy se zařízení naposledy ohlásilo.

-   **Vlastnosti:** Můžete stanovit vlastnictví zařízení (Osobní nebo Firemní).

-   **Hardware:** Tady jsou informace, které vidíte v Přehledu, a také podrobnosti o úložišti (celkové místo a volné místo), o počítačové skříni, podrobnosti o síti, o síťové službě a další informace o blokování podmíněného přístupu.

-   **Zjištěné aplikace:** Tady se zobrazují všechny aplikace nainstalované na zařízení. Seznam nainstalovaných aplikací můžete exportovat do formátu CSV.

-   **Dodržování předpisů:** Tady se zobrazují všechny podrobnosti zásad dodržování předpisů u zařízení.

-   **Konfigurace zařízení:** Tady se zobrazují všechny podrobnosti o konfiguraci zařízení.

-   **Přístup k Exchangi:** Tady najdete další informace o stavu zařízení po použití zásad podmíněného přístupu.
