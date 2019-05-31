---
title: Běžné zprávy ochrany koncového bodu v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zobrazit běžné zprávy a možné řešení při použití a řešení problémů aplikace endpoint protection a programem Windows Defender v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a4f749ab85d283ed9743d227476f8229dc1cf7c3
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402648"
---
# <a name="endpoint-protection-issues-and-possible-solutions-in-microsoft-intune"></a>Problémy s Endpoint protection a možná řešení v Microsoft Intune

Tento článek uvádí a popisuje možné příčiny a řešení pro některé chyby a upozornění. Použijte informace k řešení problémů při používání aplikace endpoint protection.

## <a name="windows-defender-error-codes"></a>Kódy chyb v programu Windows Defender

Zkontrolujte protokoly událostí a kódy chyb [řešení potíží s antivirová ochrana v programu Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

## <a name="common-intune-errors-and-possible-resolutions"></a>Běžné chyby Intune a jejich možná řešení

#### <a name="endpoint-protection-engine-unavailable"></a>Modul služby Endpoint Protection není k dispozici.

**Možnou příčinou**: Modul Endpoint Protection služby Intune je poškozený nebo odstraněný.

**Možná řešení**:

- Pokud řešení endpoint protection je poškozený nebo se neaktualizuje, pak aktualizujte nebo přeinstalujte program.
- Vynuťte okamžitou aktualizaci. V programu klienta ochrany koncového bodu (pravděpodobně na hlavním panelu) zvolte **aktualizace**.
- V okně Ovládací panely > programy, vyberte **Microsoft Intune Endpoint Protection Agent**. Tuto aplikaci odinstalujte.
- Při další synchronizaci aktualizací zjistí program Microsoft Online Management Update Manager chybějící program a v další naplánované době pro instalace ho nainstaluje znova.

#### <a name="features-are-disabled"></a>Funkce jsou zakázané.

Může zobrazit zpráva, že některé funkce jsou zakázány. Tyto zprávy se může stát, když Intune endpoint protection nebo programu Windows Defender zakázal správce pomocí konfiguračního profilu. Nebo je zakázaný koncový uživatel na zařízení. Je to možné zprávy:

`Endpoint Protection disabled`  
`Real-time protection disabled`  
`Download scanning disabled`  
`File and program activity monitoring disabled`  
`Behavior monitoring disabled`  
`Script scanning disabled`  
`Network Inspection System disabled`  

**Možná řešení**: Tyto funkce povolte. Pokyny najdete v tématu:

- [Přidat nastavení služby endpoint protection](endpoint-protection-configure.md)
- [Antivirová ochrana v programu Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus)
- [Koncoví uživatelé: Zapnout ochranu v reálném čase přístup k prostředkům společnosti](/intune-user-help/turn-on-defender-windows)

#### <a name="malware-definitions-out-of-date"></a>Definice malwaru nejsou aktuální

Tento stav se zobrazí, když jsou definice malwaru v zařízení aktuální 14 dnů a víc. Zprávy mohou například zobrazit, pokud zařízení je odpojené od Internetu nebo jsou zastaralé definice malwaru.

**Možná řešení**: Pokud jsou definice malwaru zastaralé, aktualizujte definice pomocí [antivirové ochrany v programu Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus).

#### <a name="full-scan-overdue-or-quick-scan-overdue"></a>Zpožděna úplná kontrola nebo zpožděná Rychlá kontrola

Úplná kontrola nebo rychlou kontrolu nebyla dokončena po dobu 14 dnů. Tomuto scénáři může dojít, pokud se zařízení restartuje při spuštění úplné kontroly.

**Možná řešení**: Pokud je kontrola zpožděná, můžete spustit jednorázovou kontrolu nebo naplánovat v konzole. Viz [antivirová ochrana v programu Windows Defender](device-restrictions-windows-10.md#windows-defender-antivirus).

#### <a name="another-endpoint-protection-application-running"></a>Je spuštěna jiná aplikace ochrany koncových bodů.

Je spuštěna jiná aplikace ochrany koncových bodů a zařízení je v pořádku.

**Možná řešení**: Pokud je nainstalovaná jiná aplikace ochrany koncových bodů a Intune tuto aplikaci rozpozná, zařízení může stát nestabilní.

## <a name="next-steps"></a>Další postup

Získat [podpory Microsoftu](get-support.md), nebo použijte [komunitní fóra](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
