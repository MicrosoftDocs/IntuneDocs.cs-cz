---
title: "Příprava Intune na správu mobilních zařízení | Dokumentace Microsoftu"
description: "Tento článek vám pomůže vyhodnotit před migrací do Intune technické požadavky vaší firmy."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 4bf9bd15f3f22e0609c4f56f5651454a62dbb7a8
ms.lasthandoff: 04/14/2017


---

# <a name="phase-1-prepare-intune-for-mobile-device-management-mdm"></a>Fáze 1: Příprava Intune na správu mobilních zařízení (MDM)

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Než začneme probírat podrobnosti nastavení Intune, zaměřme se na posouzení požadavků vaší organizace na správu mobilních zařízení. Doporučujeme, abyste spustili sestavy aktivních uživatelů u aktuálního poskytovatele řešení MDM a identifikovali kritické skupiny uživatelů. Potom můžete odpovědět na otázky [v části Vyhodnocení požadavků na MDM](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements).

## <a name="assess-mdm-requirements"></a>Vyhodnocení požadavků na MDM

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a>Jaké druhy zařízení potřebujete spravovat?

-   Pro které [platformy](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers) potřebujete podporu?

-   Jsou zařízení, která potřebujete podporovat, podniková nebo osobní (BYOD)?

-   Jaký druh připojení používáte? Wi-Fi, mobilní síť nebo VPN?

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a>Co vaši uživatelé potřebují dělat na spravovaných zařízeních?

-   Potřebujete zřizovat aplikace pro koncové uživatele?

-   Používáte vlastní obchodní aplikace? Nebo pracujete jen s veřejnými aplikacemi z obchodu?

-   Potřebujete zřizovat e-mailové účty?

### <a name="what-kinds-of-users"></a>O jaký druh uživatelů se jedná?

-   Kolik uživatelů bude používat jedno zařízení?

-   Jaké podmínky použití potřebujete?

    -   Zapojte do plánování včas právní oddělení.

    -   Jaké lokalizace budou potřeba?

-   Jsou uživatelé obeznámeni s technologiemi a IT obecně?

### <a name="what-is-your-device-security-policy"></a>Jaké jsou zásady zabezpečení vašeho zařízení?

-   Potřebujete šifrování na úrovni zařízení?

-   Jaké máte požadavky na hesla nebo pin kódy zařízení?

-   Potřebujete zakázat některé funkce zařízení nebo omezit určité chování zařízení?

    -   Pomocí profilů konfigurace zařízení můžete určovat různá nastavení specifická pro platformu, například zakázat fotoaparát nebo uzamknout zařízení do režimu jedné aplikace.
<br></br>
-   Jaký druh ověřování je potřeba podporovat?

    -   Pokud potřebujete ověřování na základě certifikátů, jaký druh certifikátů je potřeba poskytovat?

        -   Intune můžete poskytovat certifikáty s profily přístupu k prostředkům pro zaregistrovaná zařízení.
<br></br>
    -   Jaký typ infrastruktury veřejných klíčů (PKI) potřebujete podporovat?
<br></br>
-   Potřebujete podporovat virtuální privátní síť (VPN) na úrovni zařízení nebo aplikace?

    -   Intune může zřídit konfigurace sítě VPN i pro poskytovatele sítí VPN třetích stran.
<br></br>
-   Je možné zavést pro některé požadavky dočasné výjimky, aby se zabránilo výpadkům? Nebo musí zařízení s přístupem vždy splňovat všechny požadavky na zabezpečení?

## <a name="additional-information"></a>Další informace

-   Další podrobnější příklady najdete v těchto [případových studiích](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) z různých oborů, které jsou ukázkou toho, jak organizace vyhodnotily svoje požadavky na správu mobilních zařízení.

## <a name="next-steps"></a>Další kroky

[Fáze 1: Základní nastavení](https://docs.microsoft.com/intune/plan-design/migration-phase1-basic-setup)

